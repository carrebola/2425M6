# Uso de Parámetros en Rutas con React Router

Este tutorial te guiará paso a paso sobre cómo manejar parámetros en rutas con React Router. Aprenderás primero a usar un solo parámetro, luego a incluir múltiples parámetros y finalmente a compararlo con PHP.

## 1. Instalación de React Router
Si aún no tienes `react-router-dom` instalado en tu proyecto, puedes instalarlo con el siguiente comando:

```sh
npm install react-router-dom
```

## 2. Configuración de Rutas en `App.js`
Debemos definir nuestras rutas en `App.js` o donde estemos manejando la configuración de `react-router-dom`.

### Ejemplo con un solo parámetro

```jsx
import React from "react";
import { BrowserRouter as Router, Routes, Route } from "react-router-dom";
import ProductList from "./ProductList";
import ProductDetail from "./ProductDetail";

function App() {
  return (
    <Router>
      <Routes>
        <Route path="/" element={<ProductList />} />
        <Route path="/product/:id" element={<ProductDetail />} />
      </Routes>
    </Router>
  );
}

export default App;
```

Aquí la ruta `/product/:id` permite acceder a una vista de detalle basada en el identificador del producto.

### Ejemplo con dos parámetros

```jsx
function App() {
  return (
    <Router>
      <Routes>
        <Route path="/" element={<ProductList />} />
        <Route path="/product/:id/:style" element={<ProductDetail />} />
      </Routes>
    </Router>
  );
}
```

Se agrega un segundo parámetro `:style` para definir un estilo de visualización.

## 3. Crear la Lista de Productos (`ProductList.js`)

```jsx
import React from "react";
import { Link } from "react-router-dom";

const products = [
  { id: 1, name: "Producto 1" },
  { id: 2, name: "Producto 2" },
  { id: 3, name: "Producto 3" }
];

const ProductList = () => {
  return (
    <div>
      <h1>Lista de Productos</h1>
      <ul>
        {products.map(product => (
          <li key={product.id}>
            <Link to={`/product/${product.id}`}>{product.name}</Link>
          </li>
        ))}
      </ul>
    </div>
  );
};

export default ProductList;
```

Para incluir el parámetro `style`, los enlaces se generan de la siguiente manera:

```jsx
const styles = ["grid", "list"];

const ProductList = () => {
  return (
    <div>
      <h1>Lista de Productos</h1>
      <ul>
        {products.map(product => (
          <li key={product.id}>
            {styles.map(style => (
              <Link key={style} to={`/product/${product.id}/${style}`}>
                {product.name} ({style})
              </Link>
            ))}
          </li>
        ))}
      </ul>
    </div>
  );
};
```

## 4. Crear la Vista de Detalle (`ProductDetail.js`)

```jsx
import React from "react";
import { useParams } from "react-router-dom";

const products = [
  { id: 1, name: "Producto 1", description: "Descripción del producto 1" },
  { id: 2, name: "Producto 2", description: "Descripción del producto 2" },
  { id: 3, name: "Producto 3", description: "Descripción del producto 3" }
];

const ProductDetail = () => {
  const { id } = useParams();
  const product = products.find(p => p.id === parseInt(id));

  if (!product) {
    return <h2>Producto no encontrado</h2>;
  }

  return (
    <div>
      <h1>{product.name}</h1>
      <p>{product.description}</p>
    </div>
  );
};

export default ProductDetail;
```

Para manejar dos parámetros:

```jsx
const ProductDetail = () => {
  const { id, style } = useParams();
  const product = products.find(p => p.id === parseInt(id));

  if (!product) {
    return <h2>Producto no encontrado</h2>;
  }

  return (
    <div>
      <h1>{product.name}</h1>
      <p>{product.description}</p>
      <p>Estilo de visualización: {style}</p>
    </div>
  );
};
```

## 5. Comparación con PHP
En PHP, los parámetros de la URL se obtienen con `$_GET`. Por ejemplo, con una URL como `example.com/product.php?id=2&style=grid`:

```php
$id = $_GET['id'];
$style = $_GET['style'];
echo "El ID del producto es: " . $id . " y el estilo es: " . $style;
```

### Diferencias clave:
- **React Router** usa rutas estructuradas (`/product/:id/:style`), mientras que PHP emplea parámetros en la query string (`?id=2&style=grid`).
- **PHP** accede a los parámetros con `$_GET`, mientras que React Router los obtiene con `useParams()`.
- **React Router** funciona en el cliente, mientras que PHP lo hace en el servidor.

## 6. Conclusión
- Primero, implementamos una navegación con un solo parámetro `id`.
- Luego, ampliamos la lógica para manejar dos parámetros `id` y `style`.
- React Router facilita la gestión de rutas dinámicas con `useParams()`.
- Comparado con PHP, React Router usa una sintaxis más amigable para estructurar las rutas.


