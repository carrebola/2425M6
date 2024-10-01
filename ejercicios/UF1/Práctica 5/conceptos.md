## `push()`, `pop()`, `shift()`, `unshift()` i `splice()`

Quan treballem amb arrays en JavaScript, hi ha diversos mètodes útils per afegir, eliminar o modificar elements. Aquests mètodes permeten gestionar fàcilment el contingut d'un array.

### **`push()`**
El mètode **`push()`** afegeix un o més elements al final d'un array i retorna la nova longitud de l'array.

### Sintaxi:
```javascript
array.push(element1, element2, ..., elementN);
```

### Exemple:
Afegir elements a un array:
```javascript
let fruits = ['poma', 'plàtan'];
fruits.push('taronja');
console.log(fruits);  // ['poma', 'plàtan', 'taronja']
```

### **`pop()`**
El mètode **`pop()`** elimina l'últim element d'un array i el retorna. Si l'array està buit, retorna `undefined`.

### Sintaxi:
```javascript
array.pop();
```

### Exemple:
Eliminar l'últim element d'un array:
```javascript
let fruits = ['poma', 'plàtan', 'taronja'];
let fruitEliminat = fruits.pop();
console.log(fruitEliminat);  // 'taronja'
console.log(fruits);  // ['poma', 'plàtan']
```

### **`shift()`**
El mètode **`shift()`** elimina el primer element d'un array i el retorna. Si l'array està buit, retorna `undefined`.

### Sintaxi:
```javascript
array.shift();
```

### Exemple:
Eliminar el primer element d'un array:
```javascript
let fruits = ['poma', 'plàtan', 'taronja'];
let primerFruit = fruits.shift();
console.log(primerFruit);  // 'poma'
console.log(fruits);  // ['plàtan', 'taronja']
```

### **`unshift()`**
El mètode **`unshift()`** afegeix un o més elements al principi d'un array i retorna la nova longitud de l'array.

### Sintaxi:
```javascript
array.unshift(element1, element2, ..., elementN);
```

### Exemple:
Afegir elements al principi d'un array:
```javascript
let fruits = ['plàtan', 'taronja'];
fruits.unshift('poma');
console.log(fruits);  // ['poma', 'plàtan', 'taronja']
```

### **`splice()`**
El mètode **`splice()`** modifica un array afegint, eliminant o substituint elements en una posició específica. Pot canviar la longitud de l'array.

### Sintaxi:
```javascript
array.splice(index, numEliminar, element1, ..., elementN);
```

- `index`: Posició inicial a partir de la qual es faran les modificacions.
- `numEliminar`: Nombre d'elements a eliminar des de la posició inicial.
- `element1, ..., elementN`: Elements que s'han d'afegir a partir de la posició inicial (opcional).

### Exemple:
Eliminar elements d'un array i afegir-ne de nous:
```javascript
let fruits = ['poma', 'plàtan', 'taronja'];
fruits.splice(1, 1, 'kiwi', 'mango');  // Elimina 'plàtan' i afegeix 'kiwi' i 'mango'
console.log(fruits);  // ['poma', 'kiwi', 'mango', 'taronja']
```

### Resum de mètodes:
- **`push()`**: Afegeix un o més elements al final de l'array.
- **`pop()`**: Elimina i retorna l'últim element de l'array.
- **`shift()`**: Elimina i retorna el primer element de l'array.
- **`unshift()`**: Afegeix un o més elements al principi de l'array.
- **`splice()`**: Afegeix, elimina o substitueix elements en una posició específica.

## Iterar arrays en JavaScript: `forEach()`
Quan treballem amb arrays en JavaScript, podem utilitzar diferents mètodes per recórrer o transformar els seus elements de manera eficient. Alguns dels mètodes més comuns són **`forEach()`**, **`map()`**, **`filter()`** i **`reduce()`**. A continuació t'explico com funcionen.

### **`forEach()`**
El mètode **`forEach()`** permet executar una funció per a cada element de l'array. No retorna cap valor i només serveix per executar operacions sobre els elements de l'array.

### Sintaxi:
```javascript
array.forEach(funció(element, índex, array));
```

- `element`: L'element actual de l'array.
- `índex` (opcional): La posició de l'element en l'array.
- `array` (opcional): L'array complet.

### Exemple:
Imprimir tots els elements d'un array:
```javascript
let fruits = ['poma', 'plàtan', 'taronja'];
fruits.forEach(function(fruit, index)

