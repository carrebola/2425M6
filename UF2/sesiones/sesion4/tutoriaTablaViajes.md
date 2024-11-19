# Crear un Proyecto con React y Vite

En este tutorial, aprenderemos a crear un proyecto con React utilizando Vite. Empezaremos creando una carpeta, abriéndola en Visual Studio Code y usando el comando `create vite@latest .` para inicializar el proyecto dentro de esa carpeta.

## Paso 1: Crear la Carpeta del Proyecto

1. **Crear la carpeta manualmente**

   - Primero, crea una carpeta donde se almacenará tu proyecto. Puedes hacerlo de forma manual:
     - En tu sistema de archivos, crea una carpeta con el nombre que prefieras, por ejemplo, `mi-proyecto-react`.

2. **Abrir Visual Studio Code (VS Code)**

   - Arrastra y suelta la carpeta que acabas de crear (`mi-proyecto-react`) en la ventana de VS Code. Esto abrirá la carpeta como tu directorio de trabajo.

## Paso 2: Inicializar el Proyecto con Vite

1. **Abrir el terminal integrado de VS Code**

   - En VS Code, abre el terminal integrado. Puedes hacer clic en `Terminal` en la barra superior y luego seleccionar `Nuevo Terminal` o usar el atajo `Ctrl + ñ` (en Windows/Linux) o `Cmd + ñ` (en Mac).

2. **Crear el proyecto con Vite**

   - Asegúrate de estar ubicado en la carpeta del proyecto (la misma que arrastraste a VS Code). En la terminal, ejecuta el siguiente comando:

   ```bash
   npm create vite@latest .
   ```

   - **Explicación del comando**:
     - `npm create vite@latest`: Esto instala Vite y crea un nuevo proyecto con la última versión.
     - El `.` indica que el proyecto se creará en la carpeta actual (la que abriste en VS Code).

3. **Elegir el template de React**

   - Vite te pedirá que elijas un framework. Selecciona `React` usando las teclas de flecha y pulsa `Enter`.
   - Luego, te pedirá que elijas entre JavaScript y TypeScript. Puedes elegir el que prefieras para tu proyecto.

4. **Instalar las dependencias**

   - Una vez completado el paso anterior, Vite habrá creado los archivos necesarios en la carpeta del proyecto. Ahora necesitas instalar las dependencias ejecutando:
   
   ```bash
   npm install
   ```

## Paso 3: Ejecutar el Proyecto

1. **Levantar el servidor de desarrollo**
   - Para probar que todo funciona correctamente, ejecuta el siguiente comando en la terminal:
   
   ```bash
   npm run dev
   ```
   
   - Vite levantará un servidor de desarrollo, y deberías ver una URL (generalmente algo como `http://localhost:5173`). Haz clic en el enlace o cópialo y pégalo en tu navegador para ver tu aplicación React en funcionamiento.

## Paso 4: Crear un Archivo con Datos de Viajes

1. **Crear un archivo de datos**

   - En la carpeta `src` de tu proyecto, crea un archivo llamado `viajes.json`.

2. **Agregar un array con datos de viajes**

   - Abre el archivo `viajes.json` y agrega el siguiente código para exportar un array con datos de viajes:

   ```json
   [
     {
       "id": 1,
       "destino": "París",
       "duracion": "5 días",
       "precio": 1200
     },
     {
       "id": 2,
       "destino": "Nueva York",
       "duracion": "7 días",
       "precio": 2000
     },
     {
       "id": 3,
       "destino": "Tokio",
       "duracion": "10 días",
       "precio": 3000
     }
   ]
   ```

   - Este archivo contiene un array de objetos, cada uno representando un viaje con propiedades como `id`, `destino`, `duracion` y `precio`.

## Deconstrucción en JavaScript

La deconstrucción es una característica poderosa de ES6 que te permite extraer valores de objetos o arrays y asignarlos a variables de una manera más conveniente. Esto hace que el código sea más limpio y fácil de leer, especialmente cuando trabajamos con objetos y arrays complejos.

### Deconstrucción de Objetos y Arrays

#### Deconstrucción de Objetos

Por ejemplo, si tienes un objeto `viaje` con varias propiedades, puedes deconstruirlo de la siguiente manera:

```javascript
const viaje = {
  id: 1,
  destino: 'París',
  duracion: '5 días',
  precio: 1200
};

// Deconstrucción del objeto
const { destino, duracion, precio } = viaje;
console.log(destino); // 'París'
console.log(duracion); // '5 días'
console.log(precio); // 1200
```

#### Deconstrucción de Arrays

También podemos deconstruir arrays para extraer elementos específicos:

```javascript
const numeros = [10, 20, 30, 40];

// Deconstrucción del array
const [primero, segundo, ...resto] = numeros;
console.log(primero); // 10
console.log(segundo); // 20
console.log(resto); // [30, 40]
```

En este ejemplo, `primero` y `segundo` obtienen los dos primeros elementos del array, mientras que `resto` obtiene el resto de los elementos en un nuevo array. Esto es especialmente útil cuando deseas trabajar solo con algunos elementos de un array sin necesidad de acceder a cada uno manualmente.

#### Deconstrucción en Importaciones

También puedes usar la deconstrucción al importar solo una parte específica de un módulo:

```javascript
import { useState, useEffect } from 'react';
```

En este ejemplo, estamos importando las funciones `useState` y `useEffect` desde React utilizando la deconstrucción. Esto te permite trabajar solo con las partes del módulo que necesitas, haciendo el código más eficiente y legible.

### Operador de Propagación (`...`)

El operador de propagación (`...`) se utiliza para crear copias de arrays o de objetos. Esto es especialmente importante cuando trabajas con estados en React, ya que evita la mutación directa del estado original, lo cual puede causar problemas no deseados.

Por ejemplo, para crear una copia de un array:

```javascript
const copiaNumeros = [...numeros];
```

Y para crear una copia de un objeto:

```javascript
const viajeCopia = { ...viaje };
```

Estas copias te permiten modificar el nuevo array u objeto sin afectar al original, lo cual es una buena práctica cuando trabajamos en aplicaciones con estados como en React.

## Trabajar con Datos en el Componente Principal

### Importar los Datos en la App Principal

En tu archivo principal (por ejemplo, `App.jsx`), importa los datos de viajes directamente para utilizarlos en tu aplicación:

```javascript
import viajes from './viajes.json';
import { useState } from 'react';

function App() {
  const [listaViajes, setListaViajes] = useState(viajes);
  const [ordenAscendente, setOrdenAscendente] = useState(true);

  // Función para ordenar y desordenar los viajes por precio
  function ordenarViajes() {
    const viajesOrdenados = [...listaViajes].sort((a, b) => {
      return ordenAscendente ? a.precio - b.precio : b.precio - a.precio;
    });
    setListaViajes(viajesOrdenados);
    setOrdenAscendente(!ordenAscendente);
  }

  // Función para eliminar un viaje específico
  function eliminarViaje(id) {
    const viajesActualizados = listaViajes.filter(viaje => viaje.id !== id);
    setListaViajes(viajesActualizados);
  }

  return (
    <div>
      <h1>Lista de Viajes</h1>
      <button onClick={ordenarViajes}>
        {ordenAscendente ? 'Ordenar por Precio Descendente' : 'Ordenar por Precio Ascendente'}
      </button>
      <table border="1">
        <thead>
          <tr>
            <th>Destino</th>
            <th>Duración</th>
            <th>Precio</th>
            <th>Acciones</th>
          </tr>
        </thead>
        <tbody>
          {listaViajes.map((viaje) => (
            <tr key={viaje.id}>
              <td>{viaje.destino}</td>
              <td>{viaje.duracion}</td>
              <td>${viaje.precio}</td>
              <td>
                <button onClick={() => eliminarViaje(viaje.id)}>Eliminar</button>
              </td>
            </tr>
          ))}
        </tbody>
      </table>
    </div>
  );
}

export default App;
```

### Explicación del Código

- **Crear la Tabla**: Se ha creado una tabla con los datos de los viajes, mostrando las columnas de `Destino`, `Duración`, `Precio`, y `Acciones`.
- **Botón para Ordenar**: Se ha añadido un botón que permite alternar entre ordenar los viajes por precio de manera ascendente o descendente.
- **Botón para Eliminar**: Cada viaje tiene un botón "Eliminar" que permite eliminarlo de la lista de forma dinámica.

¡Listo! Has creado un proyecto con React usando Vite en la carpeta que arrastraste a VS Code y has agregado un archivo con datos de viajes en formato JSON que puedes utilizar en tu aplicación. Además, aprendiste a usar varias funciones de arrays y la deconstrucción de objetos y arrays, que te ayudarán a escribir un código más limpio y eficaz.


