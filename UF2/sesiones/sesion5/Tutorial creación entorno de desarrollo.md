# Tutorial para Configurar una Aplicación React con Vite, Bootstrap, ESLint, GitHub y Vercel

En este tutorial, aprenderás a crear una nueva aplicación React utilizando Vite, integrar Bootstrap para los estilos, configurar ESLint, subir el proyecto a GitHub y configurar el despliegue continuo en Vercel. Seguiremos paso a paso cada una de las tareas necesarias para lograrlo.

## Tareas a Realizar

1. **Instalar Node.js y Configurar el Entorno de Desarrollo**
2. **Crear una Nueva Aplicación React con Vite**
3. **Integrar Bootstrap en el Proyecto**
4. **Configurar ESLint**
5. **Crear un Repositorio en GitHub y Subir el Proyecto Inicial**
6. **Configurar Vercel para el Despliegue Continuo**

## Control de Versiones

- **Rama Git:** `historia-usuario-1-configuracion-inicial`
- **Commits:**
  - Tarea 1: Configura entorno de desarrollo con Node.js
  - Tarea 2: Crea aplicación React con Vite
  - Tarea 3: Integra Bootstrap en el proyecto
  - Tarea 4: Configura ESLint
  - Tarea 5: Inicia repositorio GitHub y sube el proyecto
  - Tarea 6: Configura despliegue continuo en Vercel
- **Pull Request:** Crear un pull request para fusionar `historia-usuario-1-configuracion-inicial` con `main`.

---

## Tarea 1: Instalar Node.js y Configurar el Entorno de Desarrollo

1. **Instalar Node.js**: Descarga la última versión estable de [Node.js](https://nodejs.org/).
2. **Verificar la Instalación**: Abre VSCode y utiliza el terminal integrado para verificar la instalación:
   ```bash
   node -v
   npm -v
   ```

## Tarea 2: Crear una Nueva Aplicación React con Vite

1. **Crear la Carpeta del Proyecto**: Crea una carpeta para tu proyecto y arrástrala a VSCode.
2. **Crear la Aplicación con Vite**: En el terminal de VSCode, ejecuta el siguiente comando:
   ```bash
   npm create vite@latest nombre-del-proyecto
   ```
3. **Instalar las Dependencias**:
   ```bash
   cd nombre-del-proyecto
   npm install
   ```
4. **Ejecutar la Aplicación**:
   ```bash
   npm run dev
   ```

## Tarea 3: Integrar Bootstrap en el Proyecto

1. **Instalar Bootstrap**: Utiliza el siguiente comando en el terminal para agregar Bootstrap al proyecto:
   ```bash
   npm install bootstrap@latest
   ```
2. **Importar Bootstrap**: Abre `src/main.jsx` o `src/main.tsx` e importa Bootstrap:
   ```javascript
   import 'bootstrap/dist/css/bootstrap.min.css';
   ```
3. **Verificar la Integración**: Añade algunas clases de Bootstrap a los componentes para verificar que funciona correctamente.

## Tarea 4: Configurar ESLint y VSCode para la Corrección Automática

**Nota de Seguridad:** Al utilizar enlaces con `target="_blank"`, asegúrate de añadir `rel="noreferrer"` o `rel="noopener"` para evitar problemas de seguridad en navegadores antiguos. Esto previene que la nueva página tenga acceso a la `window.opener` y potencialmente manipule la página de origen.

1. **Instalar ESLint**:
   ```bash
   npm install eslint@latest --save-dev
   ```
2. **Configurar ESLint**:
   ```bash
   npx eslint --init
   ```
3. **Opciones de Configuración**:
   - **Cómo usar ESLint**: Selecciona "To check syntax, find problems, and enforce code style".
   - **Framework**: Selecciona "React" ya que estamos trabajando en un proyecto React.
   - **Tipo de Módulos**: Elige "JavaScript modules (import/export)".
   - **Tipo de Framework**: Selecciona "JavaScript" o "TypeScript" según corresponda a tu proyecto.
   - **¿Dónde correrá tu código?**: Selecciona "Browser".
   - **Formato de Configuración**: Elige "JavaScript" para el archivo de configuración.
   - **Instalar Dependencias**: ESLint instalará automáticamente las dependencias necesarias.

4. **Configurar VSCode para la Corrección Automática**:
   - **Instalar la Extensión de ESLint**: En VSCode, instala la extensión oficial de ESLint desde la sección de extensiones.
   - **Actualizar Configuración de VSCode**: Añade la siguiente configuración para que ESLint se ejecute automáticamente al guardar los archivos. Abre el archivo de configuración de usuario de VSCode (`settings.json`) y agrega:
   ```json
   {
     "editor.codeActionsOnSave": {
       "source.fixAll.eslint": true
     },
     "eslint.validate": [
       "javascript",
       "javascriptreact",
       "typescript",
       "typescriptreact"
     ]
   }
   ```

**Nota de Seguridad:** Al utilizar enlaces con `target="_blank"`, asegúrate de añadir `rel="noreferrer"` o `rel="noopener"` para evitar problemas de seguridad en navegadores antiguos. Esto previene que la nueva página tenga acceso a la `window.opener` y potencialmente manipule la página de origen.

1. **Instalar ESLint**:
   ```bash
   npm install eslint@latest --save-dev
   ```
2. **Configurar ESLint**:
   ```bash
   npx eslint --init
   ```
3. **Opciones de Configuración**:
   - **Cómo usar ESLint**: Selecciona "To check syntax, find problems, and enforce code style".
   - **Framework**: Selecciona "React" ya que estamos trabajando en un proyecto React.
   - **Tipo de Módulos**: Elige "JavaScript modules (import/export)".
   - **Tipo de Framework**: Selecciona "JavaScript" o "TypeScript" según corresponda a tu proyecto.
   - **¿Dónde correrá tu código?**: Selecciona "Browser".
   - **Formato de Configuración**: Elige "JavaScript" para el archivo de configuración.
   - **Instalar Dependencias**: ESLint instalará automáticamente las dependencias necesarias.

## Ejemplos de Uso de ESLint

ESLint se encarga de verificar que tu código siga ciertas reglas de sintaxis y estilo, lo cual contribuye a mejorar la calidad del proyecto. A continuación, se muestran algunos ejemplos de cómo actúa ESLint y cómo debes usarlo en tu código.

### 1. Identificar Problemas de Sintaxis

**Código Incorrecto:**
```javascript
const nombre = 'Carlos'
console.log(nombre))
```
En este ejemplo, hay un paréntesis adicional al final de `console.log(nombre)`, lo cual es un error de sintaxis. ESLint lo marcará para que puedas corregirlo.

**Solución Correcta:**
```javascript
const nombre = 'Carlos';
console.log(nombre);
```

### 2. Aplicar Consistencia en el Estilo de Código

**Código Incorrecto:**
```javascript
function saludo() {
  console.log("Hola mundo")
}
```
Aquí, ESLint puede sugerir usar comillas simples en lugar de comillas dobles si la configuración seleccionada requiere consistencia con las comillas.

**Solución Correcta:**
```javascript
function saludo() {
  console.log('Hola mundo');
}
```

### 3. Uso de `const` y `let`

ESLint te indicará cuándo debes usar `const` en lugar de `let` si la variable no cambia de valor.

**Código Incorrecto:**
```javascript
let pi = 3.14;
```
Dado que `pi` no cambia, ESLint recomendará usar `const`.

**Solución Correcta:**
```javascript
const pi = 3.14;
```

### 4. Detectar Variables no Utilizadas

**Código Incorrecto:**
```javascript
const nombre = 'Carlos';
const edad = 30;
console.log(nombre);
```
En este ejemplo, `edad` no se usa en el código, por lo que ESLint marcará esta variable como innecesaria.

**Solución Correcta:**
```javascript
const nombre = 'Carlos';
console.log(nombre);
```

### 5. Uso de Enlaces con `target="_blank"`

Cuando se utilizan enlaces con `target="_blank"` en React o HTML, se recomienda añadir el atributo `rel="noreferrer"` o `rel="noopener"` para evitar vulnerabilidades de seguridad. Esto es especialmente importante en navegadores más antiguos, ya que sin estos atributos, la página abierta podría acceder a la página de origen a través de `window.opener`.

**Código Incorrecto:**
```javascript
<a href="https://example.com" target="_blank">Visita nuestro sitio</a>
```
En este ejemplo, el enlace abre una nueva pestaña sin ninguna protección, lo que podría representar un riesgo de seguridad.

**Solución Correcta:**
```javascript
<a href="https://example.com" target="_blank" rel="noreferrer">Visita nuestro sitio</a>
```
O también puedes usar `rel="noopener"` para evitar cualquier acceso a la `window.opener`.

### 6. Uso de Hooks en React

Si estás usando React, ESLint con el plugin de React también te ayudará a seguir las reglas específicas de los hooks, como la regla de que los hooks deben ser llamados siempre en el mismo orden y no dentro de bucles o condiciones.

**Código Incorrecto:**
```javascript
if (condicion) {
  const [estado, setEstado] = useState(false); // Esto no es correcto
}
```
**Solución Correcta:**
```javascript
const [estado, setEstado] = useState(false);
if (condicion) {
  // Lógica que utiliza el estado
}
```

### Ejecutar ESLint

Puedes ejecutar ESLint manualmente para analizar el código y verificar errores:
```bash
npx eslint . --ext .js,.jsx
```
Este comando analizará todos los archivos `.js` y `.jsx` en tu proyecto y mostrará los errores o advertencias que encuentre.

## Tarea 5: Crear un Repositorio en GitHub y Subir el Proyecto Inicial

1. **Abrir el Proyecto en VSCode**: Asegúrate de tener abierta la carpeta del proyecto en VSCode.
2. **Instalar la Extensión de GitHub para VSCode**: Ve a la sección de extensiones de VSCode e instala la extensión oficial de GitHub. Esto facilitará la integración con GitHub directamente desde el editor.
3. **Iniciar Sesión en GitHub desde VSCode**: Una vez instalada la extensión, inicia sesión en GitHub haciendo clic en el icono de GitHub en la barra lateral y sigue las instrucciones.
4. **Inicializar el Repositorio Git**:
   ```bash
   git init
   git add .
   git commit -m "Inicia repositorio con proyecto React creado con Vite"
   ```
5. **Crear un Repositorio en GitHub**: Puedes crear un repositorio desde la terminal o directamente desde VSCode. Si prefieres hacerlo desde VSCode, usa la opción de "Publish to GitHub" que aparece al inicializar el repositorio.
6. **Vincular el Repositorio Remoto**:
   ```bash
   git remote add origin URL_DEL_REPOSITORIO_GITHUB
   git branch -M historia-usuario-1-configuracion-inicial
   git push -u origin historia-usuario-1-configuracion-inicial
   ```

1. **Inicializar el Repositorio Git**:
   ```bash
   git init
   git add .
   git commit -m "Inicia repositorio con proyecto React creado con Vite"
   ```
2. **Crear un Repositorio en GitHub**: Ve a GitHub y crea un nuevo repositorio.
3. **Vincular el Repositorio Remoto**:
   ```bash
   git remote add origin URL_DEL_REPOSITORIO_GITHUB
   git branch -M historia-usuario-1-configuracion-inicial
   git push -u origin historia-usuario-1-configuracion-inicial
   ```

## Tarea 6: Configurar Vercel para el Despliegue Continuo

1. **Iniciar Sesión en Vercel**: Ve a [Vercel](https://vercel.com/) y crea una cuenta si no la tienes.
2. **Importar el Proyecto desde GitHub**: Importa el repositorio que acabas de crear.
3. **Configurar el Despliegue**: Vercel configurará automáticamente el proyecto y realizará un despliegue continuo cada vez que haya un nuevo commit en la rama principal (`main`).
4. **Fusionar la Rama**: Al finalizar las tareas, crea un Pull Request en GitHub para fusionar `historia-usuario-1-configuracion-inicial` con `main`.

## Conclusión

Has creado e inicializado una aplicación React utilizando Vite, integrado Bootstrap, configurado ESLint, versionado el código en GitHub y configurado un despliegue continuo en Vercel. Con este flujo de trabajo, puedes desarrollar y desplegar aplicaciones con una buena estructura y calidad de código.

