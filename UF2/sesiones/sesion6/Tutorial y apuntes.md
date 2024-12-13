# Tutorial Completo para Crear una Aplicación React SPA con Vite, ESLint, Bootstrap y Sass

En este tutorial aprenderás a configurar y desarrollar una aplicación de una sola página (SPA) en React utilizando herramientas modernas como Vite para el desarrollo rápido, ESLint para el control de la calidad del código, Bootstrap para el diseño responsivo y Sass para la gestión avanzada de estilos. La aplicación incluirá tres vistas principales: **Home**, **Acerca de** y **Contacto**. En la vista **Home**, crearás un formulario para registrar usuarios, mientras que en **Acerca de** mostrarás tarjetas informativas sobre personas. Además, aprenderás a usar Props, React Context y React Router para gestionar datos y navegación.

---

### Índice del Documento

1. [**Introducción**](#introducción) 📘
   - Descripción general del tutorial

2. [**Pasos a Seguir**](#pasos-a-seguir) 🛠️
   1. [**Crear y Configurar el Proyecto con Vite**](#1-crear-y-configurar-el-proyecto-con-vite) 📂
      - Crear la carpeta del proyecto
      - Configurar el proyecto en Visual Studio Code
      - Instalar dependencias
   2. [**Configurar ESLint**](#2-configurar-eslint) ✅
      - Instalación y configuración básica
   3. [**Instalar Bootstrap y Sass**](#3-instalar-bootstrap-y-sass) 🎨
      - Instalación de dependencias
      - Configuración de estilos personalizados
   4. [**Entender Props en React**](#4-entender-props-en-react) 📦
      - Concepto de Props
      - Uso y desestructuración de Props
   5. [**Utilizar React Context**](#5-utilizar-react-context) 🌐
      - Introducción al Context en React
      - Crear, proveer y consumir Context
   6. [**Configurar React Router**](#6-configurar-react-router) 🚦
      - Instalación de React Router
      - Configuración de rutas y navegación
   7. [**Crear las Vistas y Componentes**](#7-crear-las-vistas-y-componentes) 🖼️
      - Vista Home (Formulario para Usuario)
      - Vista Acerca de (Tarjetas de Personas)
      - Componente Reutilizable (CardPerson)
   8. [**Ejecutar la Aplicación**](#8-ejecutar-la-aplicación) ▶️
      - Iniciar el servidor de desarrollo

3. [**Conclusión**](#conclusión) 🎯
   - Resumen de los logros y próximos pasos

---

### Introducción

Este tutorial detalla los pasos necesarios para configurar una aplicación React SPA utilizando herramientas modernas. El objetivo es proporcionar una base sólida para proyectos futuros y desarrollar habilidades en React. Implementarás funcionalidades clave como la navegación entre vistas, el uso de componentes reutilizables y la gestión de estados globales con React Context.

---

### Pasos a Seguir

#### 1. Crear y Configurar el Proyecto con Vite

1. Abre tu terminal y crea una nueva carpeta para el proyecto:

   ```bash
   mkdir mi-app && cd mi-app
   ```

2. Abre la carpeta en Visual Studio Code:

   ```bash
   code .
   ```

3. Crea un proyecto React con Vite:

   ```bash
   npm create vite@latest
   ```

4. Selecciona el nombre del proyecto y elige **React** como plantilla. Si deseas usar JavaScript, selecciona **JavaScript**.

5. Accede a la carpeta del proyecto:

   ```bash
   cd <nombre-del-proyecto>
   ```

6. Instala las dependencias del proyecto:

   ```bash
   npm install
   ```

---

#### 2. Configurar ESLint

1. Instala ESLint y las dependencias necesarias:

   ```bash
   npm install eslint --save-dev
   ```

2. Inicializa ESLint:

   ```bash
   npx eslint --init
   ```

   - Selecciona: "To check syntax, find problems, and enforce code style".
   - Selecciona el módulo: "JavaScript modules (import/export)".
   - Elige: "React" como framework.
   - Indica que el código se ejecutará en el navegador.
   - Guarda la configuración en formato JSON.

3. Instala las dependencias sugeridas y ajusta el archivo `.eslintrc.json` según sea necesario.

---

#### 3. Instalar Bootstrap y Sass

1. Instala las dependencias:

   ```bash
   npm install bootstrap sass
   ```

2. Configura un archivo personalizado para estilos con variables y configuraciones. Crea el archivo `src/custom.scss`:

   ```scss
   // Variables personalizadas
   $primary-color: #007bff;
   $secondary-color: #6c757d;

   // Importa Bootstrap
   @import "~bootstrap/scss/bootstrap";

   body {
     padding-top: 60px;
     background-color: #f8f9fa;
   }

   .card-custom {
     margin: 20px;
     box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
   }
   ```

3. Importa los estilos en `src/main.jsx`:

   ```javascript
   import './custom.scss';
   ```

---

#### 4. Entender Props en React

Las **props** (abreviatura de "properties") son un mecanismo en React para pasar datos de un componente padre a un componente hijo. Son inmutables, lo que significa que no se pueden modificar dentro del componente que las recibe.

##### Cómo Funcionan:

1. **Pasar Datos**: Las props se pasan como atributos en las etiquetas del componente.

   ```javascript
   <MiComponente titulo="Hola Mundo" />
   ```

2. **Acceso a Props**: Dentro del componente, se accede a las props a través del objeto `props`.

   ```javascript
   const MiComponente = (props) => {
     return <h1>{props.titulo}</h1>;
   };
   ```

3. **Desestructuración**: Es común desestructurar las props para mejorar la legibilidad.

   ```javascript
   const MiComponente = ({ titulo }) => {
     return <h1>{titulo}</h1>;
   };
   ```

Las props son esenciales para crear componentes reutilizables y dinámicos.

---

#### 5. Utilizar React Context

El **Context** en React permite compartir datos entre componentes sin necesidad de pasar props manualmente a través de cada nivel del árbol de componentes. Esto es útil para manejar datos globales como temas o configuraciones de usuario.

##### Configuración del Contexto:

1. **Crear un Contexto**:

   ```javascript
   import React, { createContext } from 'react';
   const UserContext = createContext();
   export default UserContext;
   ```

2. **Proveer el Contexto**:

   ```javascript
   import React, { useState } from 'react';
   import UserContext from './UserContext';

   const UserProvider = ({ children }) => {
     const [usuario, setUsuario] = useState(null);
     const [tema, setTema] = useState('claro');

     return (
       <UserContext.Provider value={{ usuario, setUsuario, tema, setTema }}>
         {children}
       </UserContext.Provider>
     );
   };

   export default UserProvider;
   ```

3. **Consumir el Contexto**:

   ```javascript
   import React, { useContext } from 'react';
   import UserContext from './UserContext';

   const MiComponente = () => {
     const { usuario, setUsuario, tema } = useContext(UserContext);

     return (
       <div>
         <p>Tema actual: {tema}</p>
         <p>Usuario actual: {usuario ? usuario.nombre : 'No hay usuario'}</p>
         <button onClick={() => setUsuario({ nombre: 'Juan Pérez' })}>Iniciar Sesión</button>
       </div>
     );
   };

   export default MiComponente;
   ```

---

#### 6. Configurar React Router

1. Instala React Router:

   ```bash
   npm install react-router-dom
   ```

2. Configura las rutas en `src/App.jsx`:

   ```javascript
   import React from 'react';
   import { BrowserRouter as Router, Routes, Route, Link } from 'react-router-dom';
   import Home from './views/Home';
   import About from './views/About';
   import Contact from './views/Contact';

   const App = () => (
     <Router>
       <nav className="navbar navbar-expand-lg navbar-light bg-light fixed-top">
         <div className="container-fluid">
           <Link className="navbar-brand" to="/">MiApp</Link>
           <button className="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarNav">
             <span className="navbar-toggler-icon"></span>
           </button>
           <div className="collapse navbar-collapse" id="navbarNav">
             <ul className="navbar-nav">
               <li className="nav-item"><Link className="nav-link" to="/">Home</Link></li>
               <li className="nav-item"><Link className="nav-link" to="/about">Acerca de</Link></li>
               <li className="nav-item"><Link className="nav-link" to="/contact">Contacto</Link></li>
             </ul>
           </div>
         </div>
       </nav>
       <div className="container mt-4">
         <Routes>
           <Route path="/" element={<Home />} />
           <Route path="/about" element={<About />} />
           <Route path="/contact" element={<Contact />} />
         </Routes>
       </div>
     </Router>
   );

   export default App;
   ```

---

#### 7. Crear las Vistas y Componentes

1. **Vista Home (Formulario para Usuario):**

   ```javascript
   import React, { useContext, useState } from 'react';
   import UserContext from '../context/UserContext';

   const Home = () => {
     const { setUsuario } = useContext(UserContext);
     const [nombre, setNombre] = useState('');

     const manejarSubmit = (e) => {
       e.preventDefault();
       setUsuario({ nombre });
       setNombre('');
     };

     return (
       <div className="container">
         <h2>Introducir Usuario</h2>
         <form onSubmit={manejarSubmit}>
           <div className="mb-3">
             <label htmlFor="nombre" className="form-label">Nombre:</label>
             <input
               type="text"
               id="nombre"
               className="form-control"
               value={nombre}
               onChange={(e) => setNombre(e.target.value)}
               required
             />
           </div>
           <button type="submit" className="btn btn-primary">Guardar Usuario</button>
         </form>
       </div>
     );
   };

   export default Home;
   ```

2. **Vista Acerca de (Tarjetas de Personas):**

   ```javascript
   import React from 'react';
   import CardPerson from '../components/CardPerson';

   const About = () => {
     const personas = [
       { nombre: 'Juan Pérez', edad: 30, profesion: 'Desarrollador Web', foto: 'https://via.placeholder.com/150' },
       { nombre: 'Ana López', edad: 25, profesion: 'Diseñadora Gráfica', foto: 'https://via.placeholder.com/150' },
     ];

     return (
       <div className="container">
         <h2>Acerca de</h2>
         <div className="row">
           {personas.map((persona, index) => (
             <div key={index} className="col-md-4">
               <CardPerson nombre={persona.nombre} edad={persona.edad} profesion={persona.profesion} foto={persona.foto} />
             </div>
           ))}
         </div>
       </div>
     );
   };

   export default About;
   ```

3. **Componente Reutilizable (CardPerson):**

   ```javascript
   import React from 'react';

   const CardPerson = ({ nombre, edad, profesion, foto }) => (
     <div className="card card-custom" style={{ width: '18rem' }}>
       <img src={foto} className="card-img-top" alt={nombre} />
       <div className="card-body">
         <h5 className="card-title">{nombre}</h5>
         <p className="card-text">
           <strong>Edad:</strong> {edad} años<br />
           <strong>Profesín:</strong> {profesion}
         </p>
       </div>
     </div>
   );

   export default CardPerson;
   ```

---

#### 8. Ejecutar la Aplicación

1. Inicia el servidor de desarrollo:

   ```bash
   npm run dev
   ```

2. Abre el navegador en `http://localhost:3000` para ver la aplicación funcionando.

---

