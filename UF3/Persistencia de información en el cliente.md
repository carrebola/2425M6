# Persistencia de información en el cliente

1. **JSON.stringify**  
2. **JSON.parse**  
3. **localStorage**  
4. **Cookies**  
   - Propósito general  
   - Ejemplos de creación, lectura y borrado  
   - Uso en autenticación y comparación con localStorage  

---

## 1. JSON: Formato y Métodos Principales

### 1.1 `JSON.stringify()`

- **Función**: Convierte un objeto o arreglo de JavaScript en una cadena de texto con formato JSON.  
- **Utilidad**:  
  - Enviar datos al servidor (por ejemplo, en un `fetch` o `XMLHttpRequest`).  
  - Guardar objetos complejos en sistemas de almacenamiento que solo aceptan cadenas (p. ej., `localStorage`).  

**Ejemplo**:
```js
const persona = {
  nombre: "Juan",
  edad: 30,
  habilidades: ["JavaScript", "HTML", "CSS"]
};

// Convertir objeto JS a cadena JSON
const personaJSON = JSON.stringify(persona);
console.log(personaJSON);
// Resultado: {"nombre":"Juan","edad":30,"habilidades":["JavaScript","HTML","CSS"]}
```

### 1.2 `JSON.parse()`

- **Función**: Hace lo inverso a `JSON.stringify()`: convierte una cadena con formato JSON en un objeto o arreglo de JavaScript.  
- **Utilidad**:  
  - Interpretar la respuesta de un servidor que envía datos en formato JSON.  
  - Recuperar información de `localStorage` y transformarla nuevamente en objeto.  

**Ejemplo**:
```js
const personaString = '{"nombre":"Juan","edad":30,"habilidades":["JavaScript","HTML","CSS"]}';
const personaObj = JSON.parse(personaString);

console.log(personaObj);         // { nombre: "Juan", edad: 30, habilidades: [...] }
console.log(personaObj.nombre);  // "Juan"
```

---

## 2. Almacenamiento en el Navegador: `localStorage`

`localStorage` es un mecanismo de almacenamiento proporcionado por los navegadores que permite guardar pares clave-valor de manera **persistente** (incluso si se cierra el navegador, hasta que el usuario borre los datos o se invoque un método de borrado).

### 2.1 Guardar datos en `localStorage`

- Se guardan solo **cadenas de texto**.  
- Para objetos complejos, primero debemos usar `JSON.stringify()`.  

```js
// Guardar un string simple
localStorage.setItem("nombre", "Juan");

// Guardar un objeto (primero convertimos a string JSON)
const usuario = {
  id: 1,
  nombre: "María",
  correo: "maria@example.com"
};

localStorage.setItem("usuario", JSON.stringify(usuario));
```

### 2.2 Obtener datos de `localStorage`

- Siempre se obtienen como **string**.  
- Si era un objeto, usa `JSON.parse()` para restaurarlo.  

```js
const nombre = localStorage.getItem("nombre");
console.log(nombre); // "Juan"

const usuarioJSON = localStorage.getItem("usuario");
if (usuarioJSON) {
  const usuarioObj = JSON.parse(usuarioJSON);
  console.log(usuarioObj.nombre); // "María"
}
```

### 2.3 Eliminar datos de `localStorage`

- `localStorage.removeItem("clave")`: elimina un elemento con la clave dada.  
- `localStorage.clear()`: elimina **todos** los datos del `localStorage`.  

```js
localStorage.removeItem("nombre");
localStorage.clear();
```

---

## 3. Cookies en JavaScript

Las **cookies** son pequeños fragmentos de datos que el navegador guarda y envía al servidor **en cada petición HTTP** al dominio asociado. Se suelen usar para:

1. **Autenticación y manejo de sesiones**: Mantener la sesión de usuario iniciada.
2. **Almacenamiento de preferencias**: Idioma, temas, configuraciones que el servidor puede leer.
3. **Carritos de compra**: En sitios sencillos, se puede guardar temporalmente un identificador o lista de productos.
4. **Analítica y rastreo**: Herramientas como Google Analytics usan cookies para identificar sesiones de usuario.
5. **Persistencia de estado entre visitas**: Permite al servidor “recordar” datos sin necesidad de iniciar sesión cada vez, mientras la cookie sea válida.

### 3.1 Crear (establecer) una cookie

Se utiliza la propiedad `document.cookie`, siguiendo la estructura:  
```
document.cookie = "clave=valor; expires=fecha; path=/; domain=dominio; secure; samesite=...";
```

**Ejemplo**:
```js
// Crear una cookie que expirará en 7 días
function setCookie(nombre, valor, dias) {
  const fecha = new Date();
  fecha.setDate(fecha.getDate() + dias);
  const expires = "expires=" + fecha.toUTCString();
  document.cookie = `${nombre}=${valor}; ${expires}; path=/`;
}

// Uso
setCookie("idioma", "ES", 7);
```

- `path=/` indica que la cookie es válida para todas las rutas del dominio.  
- Si no se define `expires`, la cookie expira al cerrar el navegador.  

### 3.2 Leer una cookie específica

Las cookies se devuelven todas juntas en `document.cookie`. Para leer una en concreto, podemos separarlas y buscar la que nos interesa:

```js
function getCookie(nombre) {
  const nameEQ = nombre + "=";
  const cookies = document.cookie.split(";");

  for (let i = 0; i < cookies.length; i++) {
    let c = cookies[i].trim();
    if (c.indexOf(nameEQ) === 0) {
      return c.substring(nameEQ.length, c.length);
    }
  }
  return null;
}

const idioma = getCookie("idioma");
console.log(idioma); // "ES"
```

### 3.3 Borrar (expirar) una cookie

Para eliminar una cookie, se establece una fecha de caducidad en el pasado:

```js
function deleteCookie(nombre) {
  document.cookie = `${nombre}=; expires=Thu, 01 Jan 1970 00:00:00 UTC; path=/;`;
}

deleteCookie("idioma");
```

La cookie deja de ser válida y el navegador la elimina.

### 3.4 Uso típico en autenticación (Ejemplo conceptual)

1. El usuario inicia sesión y el **servidor** envía una cookie con `sessionId` o un token:  
   ```js
   // En Node.js/Express, por ejemplo:
   res.cookie("sessionId", "abc123XYZ", {
     httpOnly: true,
     secure: true,
     sameSite: "Strict"
   });
   res.send({ mensaje: "Login exitoso" });
   ```
2. El **navegador** guarda automáticamente esa cookie.  
3. En cada solicitud posterior, el navegador envía la cookie `sessionId` al servidor, permitiendo “reconocer” al usuario sin pedir credenciales otra vez.

---

## 4. Comparativa rápida: Cookies vs `localStorage`

| Característica                | Cookies                                                                            | localStorage                                                                 |
|-------------------------------|-------------------------------------------------------------------------------------|------------------------------------------------------------------------------|
| **Envío al servidor**         | Sí, se envían automáticamente en cada petición HTTP al dominio correspondiente.     | No, solo están disponibles en el navegador y no se mandan al servidor.       |
| **Capacidad de almacenamiento** | Muy limitada (alrededor de 4 KB por cookie).                                       | Mucho mayor (entre 2.5 MB y 10 MB según el navegador).                        |
| **Expiración**                | Se definen fechas de expiración o se borran al cerrar el navegador si no se define. | Permanecen hasta que se borren o se invoque `removeItem()` o `clear()`.       |
| **Uso típico**                | Sesiones, autenticación, preferencias para servidor, rastreo.                       | Almacenamiento de datos del lado cliente (solo el usuario o la app los usa). |
| **Seguridad**                 | Pueden ser `httpOnly`, leídas por el servidor y enviadas en cada petición.          | Solo accesibles desde JS en el cliente, no se comparten automáticamente con el servidor. |

---

## Conclusión General

1. **`JSON.stringify()` y `JSON.parse()`**  
   - Permiten convertir objetos JavaScript a cadenas JSON y viceversa.  
   - Son fundamentales para enviar/recibir información con servidores o para almacenar datos complejos en `localStorage`.

2. **`localStorage`**  
   - Ideal para guardar datos en el navegador de manera persistente, **sin** enviarlos al servidor en cada request.  
   - Se usa comúnmente para preferencias del usuario, historial local de acciones o cacheo de información.

3. **Cookies**  
   - Son claves-valor que el navegador guarda y que se envían al servidor de forma automática con cada petición HTTP.  
   - Resultan esenciales en la **autenticación**, pues permiten mantener sesiones de usuario.  
   - Pueden usarse también para preferencias, rastreo y estados de corta duración (carritos de compra, etc.).

Saber cuándo y cómo usar cada mecanismo (localStorage, cookies o ambos) es clave para desarrollar aplicaciones web eficientes, seguras y orientadas a la experiencia del usuario.
