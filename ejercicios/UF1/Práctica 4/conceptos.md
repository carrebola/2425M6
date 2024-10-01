## getAttribute, setAttribute, removeAttribute i hasAttribute

Els mètodes **`getAttribute`**, **`setAttribute`**, **`removeAttribute`** i **`hasAttribute`** permeten treballar amb els atributs dels elements HTML des del DOM. Aquests mètodes permeten obtenir, establir, eliminar i verificar atributs en els elements.

### **getAttribute(attributeName)**

Aquest mètode retorna el valor de l'atribut especificat d'un element. Si l'atribut no existeix, retorna `null`.

### Sintaxi:
```
element.getAttribute('atribut');
```

### Exemple:
Obtenir el valor de l'atribut `src` d'una imatge:
```
let imgSrc = document.querySelector('img').getAttribute('src');
console.log(imgSrc);  // Mostra el valor de l'atribut src
```

### **setAttribute(attributeName, value)**

Aquest mètode estableix el valor d'un atribut en l'element. Si l'atribut no existeix, el crea i li assigna el valor indicat.

### Sintaxi:
```
element.setAttribute('atribut', 'valor');
```

### Exemple:
Establir o canviar el valor de l'atribut `src` d'una imatge:
```
document.querySelector('img').setAttribute('src', 'nova-imatge.jpg');
```

### **removeAttribute(attributeName)**

Aquest mètode elimina l'atribut especificat de l'element.

### Sintaxi:
```
element.removeAttribute('atribut');
```

### Exemple:
Eliminar l'atribut `alt` d'una imatge:
```
document.querySelector('img').removeAttribute('alt');
```

### **hasAttribute(attributeName)**

Aquest mètode verifica si un element té un atribut determinat. Retorna `true` si l'atribut existeix i `false` si no.

### Sintaxi:
```
element.hasAttribute('atribut');
```

### Exemple:
Comprovar si una imatge té l'atribut `alt`:
```
let teAlt = document.querySelector('img').hasAttribute('alt');
console.log(teAlt);  // Mostra true o false
```

### Resum de mètodes:

- **`getAttribute()`**: Obté el valor d'un atribut.
- **`setAttribute()`**: Estableix o modifica un atribut.
- **`removeAttribute()`**: Elimina un atribut.
- **`hasAttribute()`**: Comprova si un atribut existeix.

Aquests mètodes són útils per manipular elements HTML de forma dinà
