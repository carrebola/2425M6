## classList

L'objecte **`classList`** és una propietat dels elements del DOM que permet manipular de forma dinàmica les classes CSS associades als elements HTML. Proporciona mètodes per afegir, eliminar o alternar classes sense haver de modificar manualment l'atribut `class` de l'element.

### Principals mètodes de `classList`:

- **`add(classe)`**: Afegeix una o més classes a l'element.
  ```javascript
  element.classList.add('nou-classe');
  ```

- **`remove(classe)`**: Elimina una o més classes de l'element.
  ```javascript
  element.classList.remove('classe-a-eliminar');
  ```

- **`toggle(classe)`**: Alterna una classe. Si l'element ja té la classe, la elimina; si no, la afegeix.
  ```javascript
  element.classList.toggle('visible');
  ```

- **`contains(classe)`**: Verifica si l'element conté una classe específica. Retorna `true` o `false`.
  ```javascript
  if (element.classList.contains('actiu')) {
    // Fer alguna cosa
  }
  ```

- **`replace(classeAntiga, classeNova)`**: Substitueix una classe per una altra.
  ```javascript
  element.classList.replace('antiga-classe', 'nova-classe');
  ```

## querySelectorAll

El mètode **`querySelectorAll()`** selecciona tots els elements del DOM que coincideixen amb un selector CSS específic. Retorna una **NodeList**, que és una llista d'elements que permet iterar sobre ells.

### Sintaxi:
```javascript
document.querySelectorAll('selector');
```

- **`selector`**: Un string que representa un selector CSS vàlid com `.classe`, `#id`, o una etiqueta com `div`.
- El resultat és una **NodeList**, que es pot recórrer utilitzant `forEach()` o altres tècniques per iterar.

### Exemple:
Seleccionar tots els elements amb la classe `.div-point` i aplicar un bucle `forEach`:

```javascript
let elements = document.querySelectorAll('.div');
elements.forEach((element) => {
  console.log(element);  // Accedeix a cada element seleccionat
});
```

### Diferència entre `querySelector()` i `querySelectorAll()`:

- **`querySelector()`** retorna només el **primer** element que coincideix amb el selector.
- **`querySelectorAll()`** retorna **tots** els elements que coincideixen amb el selector en forma de NodeList.
