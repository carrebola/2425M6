# Tutorial de Iniciación a React con Vite

React es una biblioteca de JavaScript muy popular para construir interfaces de usuario. Vite, por otro lado, es una herramienta de compilación que hace que el desarrollo de aplicaciones modernas sea muy rápido y fluido, especialmente con React.

Este tutorial te guiará paso a paso sobre cómo empezar un proyecto React con Vite.

## 1. Prerrequisitos
Antes de empezar, asegúrate de tener Node.js y npm instalados. Puedes verificar si están instalados ejecutando los siguientes comandos en la terminal:

```bash
node -v
npm -v
```

Si no los tienes instalados, puedes descargarlos desde [nodejs.org](https://nodejs.org).

## 2. Crear el Proyecto React con Vite
Para empezar un nuevo proyecto de React con Vite, sigue estos pasos:

1. **Crea una carpeta para tu proyecto y arrástrala a VS Code**. Luego, abre una terminal integrada presionando `Ctrl + `` (acento grave) o yendo al menú **Ver > Terminal**.

2. **Ejecuta el siguiente comando** para crear un nuevo proyecto:
    
    ```bash
    npm create vite@latest .
    ```

3. **Nombre del proyecto**: Se te pedirá un nombre para el proyecto. Puedes llamarlo, por ejemplo, `mi-proyecto-react`.

4. **Seleccionar plantilla**: A continuación, elige una de las siguientes opciones según el tipo de proyecto que deseas crear:

   - `react`: Para un proyecto React básico.
   - `react-ts`: Para un proyecto React utilizando TypeScript.
   - `vue`: Para un proyecto con Vue.js.
   - `vue-ts`: Para un proyecto Vue.js utilizando TypeScript.
   - `svelte`: Para un proyecto con Svelte.
   - `svelte-ts`: Para un proyecto Svelte utilizando TypeScript.
   - `lit`: Para un proyecto con LitElement.

   Para este tutorial, selecciona `react` con `turbo` para tener optimizaciones adicionales.

## 3. Ejecutar el Proyecto
Una vez que hayas instalado las dependencias, puedes arrancar el servidor de desarrollo con:

```bash
npm run dev
```

Esto levantará un servidor local y te proporcionará una URL, normalmente `http://localhost:5173`, en la que podrás ver tu aplicación React.

## 4. Estructura del Proyecto
La estructura de tu proyecto se verá algo así:

```
mi-proyecto-react/
├── node_modules/
├── public/
├── src/
│   ├── App.jsx
│   ├── main.jsx
│   └── index.css
├── .gitignore
├── index.html
├── package.json
└── vite.config.js
```

### Archivos y Carpetas Importantes
- **`src/`**: Contiene el código fuente de tu aplicación.
  - **`App.jsx`**: Es el componente principal de tu aplicación.
  - **`main.jsx`**: Aquí es donde se monta la aplicación en el DOM.
- **`public/`**: Archivos estáticos que se sirven sin cambios.
- **`index.html`**: El archivo HTML principal.
- **`vite.config.js`**: Configuración de Vite.

## 5. Entender los Componentes Básicos
React está basado en componentes. En el archivo `App.jsx`, encontrarás algo similar a lo siguiente:

```jsx
import { useState } from 'react';
import './App.css';

function App() {
  const [count, setCount] = useState(0);

  return (
    <div className="App">
      <h1>Hola, React con Vite!</h1>
      <button onClick={() => setCount(count + 1)}>
        Count is {count}
      </button>
    </div>
  );
}

export default App;
```

Veamos qué está pasando:
- **`useState`**: Es un Hook que te permite añadir estado a un componente funcional.
- **`count`** y **`setCount`**: Son la variable de estado y la función para actualizarla.
- **`<button onClick={...}>`**: Este botón incrementa el contador cuando se hace clic.

En un componente de React, el **`return`** va entre paréntesis y se escribe directamente el código JSX, que se parece mucho al HTML. Para incluir variables o fragmentos de código JavaScript dentro del JSX, se utilizan **llaves `{}`**.

## 6. Editar tu Primer Componente
Vamos a modificar el archivo `App.jsx` para cambiar el texto y agregar un nuevo componente:

1. Abre **`App.jsx`** y edita el contenido del `h1`:
    
    ```jsx
    <h1>Bienvenido a React con Vite</h1>
    ```

2. Añade un nuevo componente llamado `Saludo` dentro de `src`:
    - Crea un archivo **`Saludo.jsx`**:
    
    ```jsx
    function Saludo({ nombre }) {
      return <p>¡Hola, {nombre}! Bienvenido a nuestra aplicación.</p>;
    }

    export default Saludo;
    ```

3. Importa y utiliza el componente `Saludo` en `App.jsx`:
    
    ```jsx
    import Saludo from './Saludo';

    function App() {
      const [count, setCount] = useState(0);

      return (
        <div className="App">
          <h1>Bienvenido a React con Vite</h1>
          <Saludo nombre="Mia" />
          <button onClick={() => setCount(count + 1)}>
            Count is {count}
          </button>
        </div>
      );
    }

    export default App;
    ```

## 7. Estilos en React
Los estilos se manejan de diversas maneras en React. Puedes usar CSS tradicional o CSS-in-JS. En este tutorial, usaremos el archivo CSS ya creado, **`index.css`** o **`App.css`**.

Por ejemplo, añade lo siguiente a **`App.css`**:

```css
.App {
  text-align: center;
  font-family: Arial, sans-serif;
}

button {
  background-color: #6200ea;
  color: white;
  border: none;
  padding: 10px 20px;
  cursor: pointer;
  font-size: 16px;
}

button:hover {
  background-color: #3700b3;
}
```

## 8. Construir el Proyecto para Producción
Cuando estés listo para construir el proyecto para producción, ejecuta:

```bash
npm run build
```

Esto generará una carpeta `dist/` con los archivos optimizados para desplegar.

## 9. Algunos Consejos
- **Componentes**: Intenta dividir tu aplicación en componentes pequeños y reutilizables.
- **Hooks**: Aprende a usar hooks como `useState`  para manejar el estados.
- **JSX**: Es la sintaxis que ves dentro de los componentes, que se parece a HTML. JSX permite crear interfaces de usuario de forma declarativa.

¡Y listo! Ahora tienes una aplicación básica de React creada con Vite.

