

## **Enunciado: Creación de una Aplicación de Cartelera de Películas con React y Vite**

### **Descripción General**

Desarrollarás una aplicación web utilizando **React** y **Vite** que muestra una cartelera de películas. La aplicación tendrá las siguientes características:

1. **Estructura de la Aplicación**: La aplicación contará con un **header**, un **main** y un **footer**.
2. **Visualización de Películas**: En el **main** se mostrará la cartelera con una serie de tarjetas de películas provenientes de un array de datos.
3. **Control de Entradas**: En el **main**, junto a las tarjetas de películas, aparecerán dos botones con un **"+"** y un **"-"**, y un div que indique: **Número de entradas**.
4. **Lógica de los Botones**: Al pulsar los botones, aumentará o disminuirá el número de entradas, que como mínimo será 0.
5. **Selección de Película**: Al hacer clic sobre una película, se mostrará junto al número de entradas el nombre de la película seleccionada.

### **Objetivos**

- Configurar un proyecto de React utilizando Vite.
- Instalar y configurar Bootstrap para estilos rápidos y responsivos.
  (Plantilla de bootstrap: https://getbootstrap.com/docs/5.0/examples/album/)
- Crear y estructurar componentes React para la aplicación.
- Implementar la lógica para controlar el número de entradas.
- Mostrar películas en tarjetas utilizando datos de un array.
- Implementar la funcionalidad de selección de película y mostrar el nombre en el **main**.
- Evitar la necesidad de pasar props o estados entre componentes.

---


### **Ejercicio 1: Configuración del Proyecto con Vite** *(1 punto)*

**1.1. Crear el Proyecto**

- Crea un nuevo proyecto de React con Vite llamado `movie-app`.
- Instala las dependencias necesarias y verifica que la aplicación funciona correctamente.

---

### **Ejercicio 2: Instalación y Configuración de Bootstrap** *(1 punto)*

**2.1. Instalar Bootstrap**

- Instala Bootstrap utilizando npm y configura el proyecto para que los estilos de Bootstrap estén disponibles en toda la aplicación.

---

### **Ejercicio 3: Crear la Estructura Básica de la Aplicación** *(1 punto)*

**3.1. Crear los Componentes Base**

- Dentro de la carpeta `src`, crea los componentes:
  - `Header.jsx`: Representará el encabezado de la aplicación y solo contendrá el logo o título de la cartelera.
  - `Main.jsx`: Contendrá las tarjetas de películas y los botones de control de entradas.
  - `Footer.jsx`: Mostrará el pie de página.

---

### **Ejercicio 4: Implementar el Componente Header** *(0.5 puntos)*

**4.1. Crear el Componente Header**

- En `Header.jsx`, crea un componente que incluya el logo o título de la aplicación centrado.

---

### **Ejercicio 5: Implementar el Componente Footer** *(0.5 puntos)*

**5.1. Crear el Componente Footer**

- En `Footer.jsx`, crea un componente sencillo que muestre un pie de página con algún texto, por ejemplo: **"© 2023 Cartelera de Películas"**.

---

### **Ejercicio 6: Crear el Array de Datos de Películas** *(1 punto)*

**6.1. Crear el Archivo de Datos**

- Crea un archivo `movies.js` que contenga un array de objetos con la información de las películas: `id`, `title`, `description` y `poster`.

---

### **Ejercicio 7: Crear el Componente MovieCard** *(1 punto)*

**7.1. Crear el Componente**

- En `MovieCard.jsx`, crea un componente que:
  - Reciba los datos de una película como props.
  - Muestre una tarjeta con la imagen del póster, el título y la descripción.
  - Detecte cuando el usuario hace clic en la tarjeta.
*PD: Si no sabes pasar parametros como props puedes hacerlo con cards de bootstrap directamente desde main*
---

### **Ejercicio 8: Mostrar las Películas en el Componente Main** *(1 punto)*

**8.1. Implementar el Componente Main**

- En `Main.jsx`:
  - Importa el array `movies` y el componente `MovieCard`.
  - Utiliza un método de mapeo para renderizar una lista de `MovieCard`.
  - Organiza las tarjetas y los botones de control de entradas en el mismo componente.

---

### **Ejercicio 9: Implementar la Lógica de Selección de Película y Control de Entradas** *(2 puntos)*

**9.1. Manejar la Selección de Película**

- En el componente `Main`, define un estado para almacenar el nombre de la película seleccionada.
- Al hacer clic en una tarjeta de película, actualiza el estado con el nombre de la película seleccionada.
- Muestra el nombre de la película seleccionada junto al número de entradas.

**9.2. Implementar la Lógica de los Botones**

- En el mismo componente `Main`, define un estado para el número de entradas.
- Implementa funciones para incrementar y decrementar el número de entradas al pulsar los botones "+" y "-", asegurándote de que el número no sea menor que 0.

---

### **Ejercicio 10: Pruebas y Depuración** *(1 punto)*

**10.1. Verificar la Funcionalidad y despliegue en producción**

- Prueba todas las características de la aplicación:
  - Al hacer clic en una película, su nombre se muestra junto al número de entradas.
  - Los botones de aumentar y disminuir entradas funcionan correctamente.
  - El número de entradas no puede ser menor que 0.
- Asegúrate de que no hay errores en la consola del navegador.

---
