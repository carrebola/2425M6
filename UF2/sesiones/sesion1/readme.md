# Crear una Single Page Application (SPA) con JavaScript y npm

Crear un proyecto JavaScript con npm y montar una Single Page Application (SPA) es una gran manera de comenzar a desarrollar aplicaciones web modernas. A continuación, te guío paso a paso para conseguirlo:

## Índice
- [Crear una Single Page Application (SPA) con JavaScript y npm](#crear-una-single-page-application-spa-con-javascript-y-npm)
  - [Índice](#índice)
  - [Pasos para crear el proyecto](#pasos-para-crear-el-proyecto)
    - [1. Instalar Node.js y npm](#1-instalar-nodejs-y-npm)
    - [2. Crear una carpeta para el proyecto](#2-crear-una-carpeta-para-el-proyecto)
    - [3. Inicializar el proyecto con npm](#3-inicializar-el-proyecto-con-npm)
    - [4. Instalar un servidor de desarrollo](#4-instalar-un-servidor-de-desarrollo)
    - [5. Crear la estructura básica de la SPA](#5-crear-la-estructura-básica-de-la-spa)
    - [6. Escribir el código HTML de la SPA](#6-escribir-el-código-html-de-la-spa)
    - [7. Agregar estilos CSS básicos](#7-agregar-estilos-css-básicos)
    - [8. Crear componentes para el header, footer y páginas](#8-crear-componentes-para-el-header-footer-y-páginas)
    - [9. Agregar la lógica JavaScript para la SPA](#9-agregar-la-lógica-javascript-para-la-spa)
    - [10. Ejecutar el proyecto](#10-ejecutar-el-proyecto)
  - [Explicación de los conceptos empleados](#explicación-de-los-conceptos-empleados)
    - [Node.js y npm](#nodejs-y-npm)
    - [SPA (Single Page Application)](#spa-single-page-application)
    - [npm init -y](#npm-init--y)
    - [lite-server](#lite-server)
    - [Estructura del proyecto](#estructura-del-proyecto)
    - [HTML y el elemento `root`](#html-y-el-elemento-root)
    - [CSS básico](#css-básico)
    - [Componentes (Header, Footer, HomePage, AboutPage)](#componentes-header-footer-homepage-aboutpage)
    - [`App()` y la estructura principal](#app-y-la-estructura-principal)
    - [`navigate()` y navegación entre páginas](#navigate-y-navegación-entre-páginas)
    - [`querySelector()` y manipulación del DOM](#queryselector-y-manipulación-del-dom)
    - [`addEventListener()`](#addeventlistener)
    - [`window.navigate`](#windownavigate)
    - [Servidor de desarrollo y ejecución del proyecto](#servidor-de-desarrollo-y-ejecución-del-proyecto)

## Pasos para crear el proyecto

### 1. Instalar Node.js y npm
Primero, asegúrate de tener Node.js y npm instalados. Puedes descargarlos desde [nodejs.org](https://nodejs.org/).

### 2. Crear una carpeta para el proyecto
Abre un terminal y crea una carpeta para tu proyecto. Por ejemplo:

```bash
mkdir my-spa-project
cd my-spa-project
```

### 3. Inicializar el proyecto con npm
Inicializa el proyecto con npm. Esto creará un archivo `package.json` que contendrá la información del proyecto y las dependencias:

```bash
npm init -y
```

El `-y` acepta la configuración predeterminada.

### 4. Instalar un servidor de desarrollo
Para una SPA, necesitaremos un servidor para servir los archivos. Utilizaremos `lite-server` por su simplicidad:

```bash
npm install lite-server --save-dev
```

Después de instalarlo, edita tu archivo `package.json` para agregar el siguiente script de servidor dentro de la sección `"scripts"`:

```json
"scripts": {
  "start": "lite-server"
}
```

Con esto, podremos arrancar nuestro servidor de desarrollo fácilmente.

### 5. Crear la estructura básica de la SPA
Crea la siguiente estructura de carpetas y archivos:

```
my-spa-project/
  ├── index.html
  ├── css/
  │   └── styles.css
  └── js/
      ├── app.js
      ├── components/
      │   ├── Header.js
      │   └── Footer.js
      └── views/
          ├── HomePage.js
          └── AboutPage.js
```

### 6. Escribir el código HTML de la SPA
Crea un archivo `index.html` con el siguiente contenido:

```html
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Mi SPA</title>
  <link rel="stylesheet" href="./css/styles.css">
</head>
<body>
  <div id="root"></div>
  <script type="module" src="./js/app.js"></script>
</body>
</html>
```

En este HTML, el contenido se cargará dinámicamente dentro del `div` con id `root`.

### 7. Agregar estilos CSS básicos
Crea el archivo `css/styles.css` para dar un estilo básico a la página:

```css
body {
  font-family: Arial, sans-serif;
}

header {
  background-color: #f8f8f8;
  padding: 10px;
  text-align: center;
  border-bottom: 1px solid #ddd;
}

nav {
  margin-bottom: 20px;
}

button {
  margin-right: 10px;
}

main {
  padding: 20px;
}

footer {
  background-color: #f8f8f8;
  padding: 10px;
  text-align: center;
  border-top: 1px solid #ddd;
  margin-top: 20px;
}
```

### 8. Crear componentes para el header, footer y páginas
Crea los siguientes archivos dentro de las carpetas `components/` y `views/` para definir los componentes del `header`, `footer`, y las páginas `home` y `about`.

**components/Header.js**:

```js
export function Header() {
  return `
    <header>
      <h1>Mi SPA Encabezado</h1>
      <nav>
        <button id="homeButton">Inicio</button>
        <button id="aboutButton">Acerca de</button>
      </nav>
    </header>
  `;
}
```

**components/Footer.js**:

```js
export function Footer() {
  return `
    <footer>
      <p>Mi SPA Pie de página</p>
    </footer>
  `;
}
```

**views/HomePage.js**:

```js
export function HomePage() {
  return `
    <h2>Bienvenido a la Página de Inicio</h2>
    <p>Esta es la página principal de nuestra SPA.</p>
  `;
}
```

**views/AboutPage.js**:

```js
export function AboutPage() {
  return `
    <h2>Acerca de Nosotros</h2>
    <p>Esta es la página de información. Aquí puedes encontrar más información sobre nosotros.</p>
  `;
}
```

### 9. Agregar la lógica JavaScript para la SPA
Ahora vamos a implementar la lógica para la navegación dentro del archivo `js/app.js`.

```js
import { Header } from './components/Header.js';
import { Footer } from './components/Footer.js';
import { HomePage } from './views/HomePage.js';
import { AboutPage } from './views/AboutPage.js';

function App() {
  return `
    ${Header()}
    <main id="content">
      <!-- El contenido cambiará dinámicamente -->
    </main>
    ${Footer()}
  `;
}

function navigate(page) {
  const content = document.querySelector('#content');

  if (page === 'home') {
    content.innerHTML = HomePage();
  } else if (page === 'about') {
    content.innerHTML = AboutPage();
  }
}

// Cargar la aplicación
document.querySelector('#root').innerHTML = App();

// Agregar eventos a los botones
const homeButton = document.querySelector('#homeButton');
const aboutButton = document.querySelector('#aboutButton');

homeButton.addEventListener('click', () => navigate('home'));
aboutButton.addEventListener('click', () => navigate('about'));

// Por defecto, mostramos la página de inicio
navigate('home');

// Exponer la función navigate al scope global para poder ser llamada desde el HTML
window.navigate = navigate;
```

Este código JavaScript ahora utiliza componentes para cada página (`HomePage` y `AboutPage`), de la misma manera que los componentes `Header` y `Footer`, haciendo que el código sea más modular y fácil de mantener.

### 10. Ejecutar el proyecto
Ahora que tenemos todo listo, puedes arrancar el servidor de desarrollo con:

```bash
npm start
```

Esto abrirá el navegador para acceder a tu SPA a través de `http://localhost:3000`.

Si tienes alguna pregunta o necesitas ayuda para agregar más funcionalidades, no dudes en preguntarme.

## Explicación de los conceptos empleados

### Node.js y npm
**Node.js** es un entorno de ejecución para JavaScript que permite ejecutar código del lado del servidor, fuera del navegador. **npm** (Node Package Manager) es el gestor de paquetes para Node.js que permite instalar bibliotecas y herramientas necesarias para los proyectos.

### SPA (Single Page Application)
Una **Single Page Application (SPA)** es un tipo de aplicación web que carga una sola página HTML y actualiza dinámicamente el contenido en la misma, sin necesidad de recargar la página completa. Esto permite una experiencia de usuario más rápida y fluida.

### npm init -y
El comando **`npm init -y`** se utiliza para inicializar un proyecto de Node.js, creando el archivo `package.json` con la configuración predeterminada del proyecto.

### lite-server
**`lite-server`** es un servidor de desarrollo ligero que se utiliza para servir aplicaciones web durante el desarrollo. Facilita la recarga automática del navegador cada vez que se hacen cambios en el código.

### Estructura del proyecto
Hemos dividido el proyecto en diferentes carpetas para organizar mejor el código:
- `components/`: contiene los componentes reutilizables como `Header` y `Footer`.
- `views/`: contiene las vistas de las diferentes páginas, como `HomePage` y `AboutPage`.
- `css/`: contiene los archivos de estilos CSS.
- `js/`: contiene toda la lógica de la aplicación, incluyendo los componentes, las vistas y el archivo principal `app.js`.

### HTML y el elemento `root`
En el archivo **`index.html`**, el elemento `<div id="root"></div>` es el contenedor principal donde se cargará dinámicamente toda la estructura de la aplicación utilizando JavaScript.

### CSS básico
Los estilos CSS proporcionados permiten una presentación sencilla de la página. Establecen un diseño básico para los elementos `header`, `nav`, `button`, `main` y `footer`.

### Componentes (Header, Footer, HomePage, AboutPage)
Los **componentes** son funciones que devuelven cadenas de HTML. Esto hace que el código sea más modular y fácil de mantener. En este proyecto, `Header`, `Footer`, `HomePage` y `AboutPage` se implementan como componentes.

### `App()` y la estructura principal
La función **`App()`** combina todos los componentes (`Header`, `main`, y `Footer`) y devuelve la estructura HTML completa que se inserta en el elemento `root`.

### `navigate()` y navegación entre páginas
La función **`navigate(page)`** se utiliza para cambiar el contenido de la página sin recargarla. Modifica el contenido del elemento `main` dependiendo de la página solicitada (`home` o `about`). Esta función es la clave para mantener la experiencia de una SPA.

### `querySelector()` y manipulación del DOM
**`document.querySelector()`** se utiliza para seleccionar elementos del DOM (Document Object Model). Se usa tanto para insertar el contenido dinámico (`#content`) como para seleccionar los botones para agregarles eventos de clic.

### `addEventListener()`
**`addEventListener()`** se utiliza para asociar un evento a un elemento del DOM. En este proyecto, se utiliza para que los botones `homeButton` y `aboutButton` llamen a la función `navigate()` cuando se hace clic en ellos.

### `window.navigate`
Para poder acceder a la función **`navigate()`** desde el navegador (por ejemplo, desde la consola del navegador), se la expone en el objeto **`window`**. Esto permite ejecutar `window.navigate('home')` o `window.navigate('about')` desde el contexto global.

### Servidor de desarrollo y ejecución del proyecto
El script `"start": "lite-server"` definido en `package.json` permite arrancar el servidor de desarrollo con el comando **`npm start`**. Esto abrirá automáticamente el navegador para que puedas ver y probar la aplicación en `http://localhost:3000`.
