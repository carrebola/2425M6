# Resol aquests exercicis per aconseguir el teu codi de la caixa forta virtual

### 1. **Capturar clics amb `addEventListener()`**  
Crea una pàgina HTML amb tres botons. Fes que cada botó mostri un missatge diferent a la consola quan es faci clic.

**Pista**: Utilitza `addEventListener('click', ...)` per a cada botó.

```html
<button id="boton1">Botó 1</button>
<button id="boton2">Botó 2</button>
<button id="boton3">Botó 3</button>
```

---

### 2. **Manipulació del DOM amb `innerHTML`**  
Crea un element `div` en una pàgina HTML i escriu una funció que canviï el seu contingut HTML quan es faci clic en un botó.

**Pista**: Usa `innerHTML` per canviar el contingut dins del `div`.

```html
<div id="miDiv">Contingut original</div>
<button id="boton">Canviar Contingut</button>
```

---

### 3. **Mostrar/ocultar elements amb `style.display`**  
Crea un botó que alterni la visibilitat d'un `div`. Si el `div` està ocult, l'ha de mostrar, i si està visible, l'ha d'ocultar.

**Pista**: Comprova si `style.display` és `"none"` o `"block"`.

```html
<div id="miDiv">Text a mostrar/ocultar</div>
<button id="toggleButton">Mostrar/Ocultar</button>
```

---

### 4. **Generar números aleatoris amb `Math.random()`**  
Crea una funció que generi un número aleatori entre 1 i 100 cada vegada que es faci clic en un botó i mostri el resultat en un `div`.

**Pista**: Multiplica `Math.random()` per 100 i arrodoneix amb `Math.floor()`.

```html
<div id="resultat">Número aleatori: </div>
<button id="boton">Generar Número</button>
```

---

### 5. **Manipular atributs amb `setAttribute()`**  
Crea un element `img` i un botó. Escriu una funció que canviï la imatge mostrada quan es faci clic en el botó.

**Pista**: Utilitza `setAttribute('src', ...)` per canviar la imatge.

```html
<img id="imatge" src="imatge1.jpg" alt="Imatge inicial">
<button id="canviarImatge">Canviar Imatge</button>
```

---

### 6. **Afegir i eliminar classes amb `classList`**  
Crea un botó que afegeixi la classe `actiu` a un element quan es faci clic, i que la torni a eliminar si es fa clic una altra vegada.

**Pista**: Utilitza `classList.toggle()` per afegir o eliminar la classe.

```html
<div id="miElement">Aquest és l'element</div>
<button id="toggleClass">Canviar Classe</button>

<style>
  .actiu {
    color: red;
    font-weight: bold;
  }
</style>
```

---

### 7. **Recórrer un array amb `forEach()`**  
Escriu una funció que recorri un array de fruits i els mostri en una llista HTML.

**Pista**: Usa `forEach()` per recórrer els elements de l'array i crear elements `li`.

```html
<ul id="fruitList"></ul>
```

---

### 8. **Accedir a un array de dues dimensions**  
Crea un array de dues dimensions amb preguntes i respostes i mostra la primera pregunta i resposta en un `div`.

**Pista**: Accedeix als elements de l'array mitjançant `array[row][column]`.

```html
<div id="pregunta"></div>
<div id="resposta"></div>
```

---

### 9. **Funció per sumar dos números**  
Crea una funció que rebi dos números i retorni la seva suma. Mostra el resultat a la pantalla.

**Pista**: Defineix una funció que retorni `num1 + num2` i mostra el resultat amb `innerHTML`.

```html
<div id="resultat"></div>
<button id="botonSuma">Sumar</button>
```

---

### 10. **Validar una entrada buida**  
Crea una funció que comprovi si un camp de text està buit quan es prem un botó, i mostri un missatge d'error si està buit.

**Pista**: Comprova si la variable `entrada` és una cadena buida `""`.

```html
<input type="text" id="entrada">
<button id="botonValidar">Validar</button>
```

---

### 11. **Interacció amb `addEventListener()`**  
Crea un botó que mostri una alerta quan es faci clic.

**Pista**: Usa `alert()` dins del callback de l'`addEventListener`.

```html
<button id="botonAlerta">Mostrar Alerta</button>
```

---

### 12. **Control de flux amb `if...else`**  
Crea una funció que compari un número i mostri si és més gran o més petit que 10.

**Pista**: Utilitza condicions `if` per comparar el número.

```html
<button id="botonComparar">Comparar Número</button>
```

---

### 13. **Manipulació d'atributs amb `getAttribute()`**  
Crea una pàgina amb una imatge i un botó que mostri el valor de l'atribut `src` de la imatge en un `div`.

**Pista**: Usa `getAttribute('src')` per obtenir el valor.

```html
<img id="imatge" src="imatge1.jpg" alt="Imatge inicial">
<div id="resultat"></div>
<button id="mostrarSrc">Mostrar Atribut `src`</button>
```

---

### 14. **Eliminar l'atribut amb `removeAttribute()`**  
Crea una pàgina amb una imatge i un botó que elimini l'atribut `alt` de la imatge quan es fa clic.

**Pista**: Usa `removeAttribute('alt')` per eliminar l'atribut.

```html
<img id="imatge" src="imatge1.jpg" alt="Imatge inicial">
<button id="eliminarAlt">Eliminar Atribut `alt`</button>
```

---

### 15. **Mostrar números de forma condicional**  
Crea una funció que només mostri números parells d'un array.

**Pista**: Utilitza l'operador `mod` (`%`) per determinar si el número és parell.

```html
<div id="resultat"></div>
```


# Exercicis de JavaScript (Math)

## Exercici 1 - Valor absolut
Escriu una funció que rebi un número i retorni el seu valor absolut utilitzant `Math.abs`.

```javascript
function valorAbsolut(num) {
    // A completar
}

// Exemple d'ús:
console.log(valorAbsolut(-5)); // Retorna 5
console.log(valorAbsolut(3));  // Retorna 3
```

## Exercici 2 - Signe d'un número
Crea una funció que determini si un número és positiu, negatiu o zero, utilitzant `Math.sign`.

```javascript
function determinarSigne(num) {
    // A completar
}

// Exemple d'ús:
console.log(determinarSigne(-10)); // Retorna "El número és negatiu."
console.log(determinarSigne(0));   // Retorna "El número és zero."
console.log(determinarSigne(7));   // Retorna "El número és positiu."
```

## Exercici 3 - Màxim de tres números
Escriu una funció que rebi tres números i retorni el més gran utilitzant `Math.max`.

```javascript
function trobarMaxim(a, b, c) {
    // A completar
}

// Exemple d'ús:
console.log(trobarMaxim(5, 10, 3)); // Retorna 10
```

## Exercici 4 - Mínim d'un array
Crea una funció que rebi un array de números i retorni el menor valor utilitzant `Math.min` i l'operador de propagació.

```javascript
function trobarMinim(arrayNumeros) {
    // A completar
}

// Exemple d'ús:
var numeros = [3, 7, 2, 9, 4];
console.log(trobarMinim(numeros)); // Retorna 2
```

## Exercici 5 - Arrel quadrada
Escriu una funció que calculi l'arrel quadrada d'un número donat utilitzant `Math.sqrt`.

```javascript
function calcularArrelQuadrada(num) {
    // A completar
}

// Exemple d'ús:
console.log(calcularArrelQuadrada(16)); // Retorna 4
console.log(calcularArrelQuadrada(-9)); // Retorna "No es pot calcular l'arrel quadrada d'un número negatiu."
```

## Exercici 6 - Arrodonir un número a l'enter més proper
Escriu una funció que rebi un número decimal i l'arrodoneixi a l'enter més proper utilitzant `Math.round`.

```javascript
function arrodonirNumero(num) {
    // A completar
}

// Exemple d'ús:
console.log(arrodonirNumero(4.6)); // Retorna 5
console.log(arrodonirNumero(4.3)); // Retorna 4
```

## Exercici 7 - Arrodonir cap amunt
Crea una funció que arrodoneixi un número decimal cap amunt a l'enter més proper utilitzant `Math.ceil`.

```javascript
function arrodonirCapAmunt(num) {
    // A completar
}

// Exemple d'ús:
console.log(arrodonirCapAmunt(3.1)); // Retorna 4
console.log(arrodonirCapAmunt(7.9)); // Retorna 8
```

## Exercici 8 - Arrodonir cap avall
Escriu una funció que arrodoneixi un número decimal cap avall a l'enter més proper utilitzant `Math.floor`.

```javascript
function arrodonirCapAvall(num) {
    // A completar
}

// Exemple d'ús:
console.log(arrodonirCapAvall(5.8)); // Retorna 5
console.log(arrodonirCapAvall(2.2)); // Retorna 2
```

## Exercici 9 - Eliminar la part decimal d'un número
Crea una funció que elimini la part decimal d'un número i retorni només la part entera utilitzant `Math.trunc`.

```javascript
function truncarNumero(num) {
    // A completar
}

// Exemple d'ús:
console.log(truncarNumero(6.7));   // Retorna 6
console.log(truncarNumero(-6.7));  // Retorna -6
```

## Exercici 10 - Calcular el sinus d'un angle
Escriu una funció que rebi un angle en graus i retorni el seu sinus utilitzant `Math.sin`.

```javascript
function calcularSinus(angleGraus) {
    // A completar
}

// Exemple d'ús:
console.log(calcularSinus(30)); // Retorna 0.5
console.log(calcularSinus(90)); // Retorna 1
```

# Exercicis de JavaScript - Strings

## Exercici 1 - Interpolació de variables amb cometes obertes
Escriu una funció que mostri un missatge interpolant dues variables utilitzant cometes obertes (backticks).

```javascript
function interpolarVariables(nom, edat) {
    // A completar
}

// Exemple d'ús:
console.log(interpolarVariables("Joan", 25)); // Retorna "El meu nom és Joan i tinc 25 anys."
```

## Exercici 2 - `charAt`
Crea una funció que retorni el caràcter d'una cadena en una posició específica utilitzant `charAt`.

```javascript
function obtenirCaracter(cadena, posicio) {
    // A completar
}

// Exemple d'ús:
console.log(obtenirCaracter("Hola", 1)); // Retorna "o"
```

## Exercici 3 - `indexOf`
Escriu una funció que retorni la primera posició en què es troba un substring dins d'una cadena utilitzant `indexOf`.

```javascript
function trobarPosicio(cadena, subcadena) {
    // A completar
}

// Exemple d'ús:
console.log(trobarPosicio("JavaScript és genial", "genial")); // Retorna 13
```

## Exercici 4 - `repeat`
Crea una funció que repeteixi una cadena un cert nombre de vegades utilitzant `repeat`.

```javascript
function repetirCadena(cadena, vegades) {
    // A completar
}

// Exemple d'ús:
console.log(repetirCadena("Hola", 3)); // Retorna "HolaHolaHola"
```

## Exercici 5 - `substring`
Escriu una funció que extregui una part d'una cadena des d'una posició inicial fins a una final utilitzant `substring`.

```javascript
function obtenirSubstring(cadena, inici, fi) {
    // A completar
}

// Exemple d'ús:
console.log(obtenirSubstring("JavaScript", 0, 4)); // Retorna "Java"
```

## Exercici 6 - `substr`
Crea una funció que extregui una part d'una cadena començant des d'una posició i per una longitud determinada utilitzant `substr`.

```javascript
function obtenirSubstr(cadena, inici, longitud) {
    // A completar
}

// Exemple d'ús:
console.log(obtenirSubstr("JavaScript", 4, 6)); // Retorna "Script"
```

## Exercici 7 - `split`
Escriu una funció que divideixi una cadena en un array de subcadenes utilitzant `split`.

```javascript
function dividirCadena(cadena, separador) {
    // A completar
}

// Exemple d'ús:
console.log(dividirCadena("poma,pera,plàtan", ",")); // Retorna ["poma", "pera", "plàtan"]
```

## Exercici 8 - `startsWith`
Crea una funció que determini si una cadena comença amb un substring específic utilitzant `startsWith`.

```javascript
function comencaAmb(cadena, subcadena) {
    // A completar
}

// Exemple d'ús:
console.log(comencaAmb("JavaScript", "Java")); // Retorna true
```

## Exercici 9 - `endsWith`
Escriu una funció que comprovi si una cadena acaba amb un substring específic utilitzant `endsWith`.

```javascript
function acabaAmb(cadena, subcadena) {
    // A completar
}

// Exemple d'ús:
console.log(acabaAmb("JavaScript", "Script")); // Retorna true
```

## Exercici 10 - `includes`
Crea una funció que determini si una cadena conté un substring específic utilitzant `includes`.

```javascript
function contéSubcadena(cadena, subcadena) {
    // A completar
}

// Exemple d'ús:
console.log(contéSubcadena("JavaScript és genial", "genial")); // Retorna true
```

## Exercici 11 - `search`
Escriu una funció que busqui un substring dins d'una cadena i retorni la seva posició utilitzant `search`.

```javascript
function cercarCadena(cadena, subcadena) {
    // A completar
}

// Exemple d'ús:
console.log(cercarCadena("JavaScript és genial", "genial")); // Retorna 13
```

## Exercici 12 - `match`
Crea una funció que retorni les coincidències d'un patró dins d'una cadena utilitzant `match

`. Utilitza aquest patro: `/\d+/g`

```javascript
function buscarCoincidencies(cadena, patró) {
    // A completar
}

// Exemple d'ús:
console.log(buscarCoincidencies("Hola 123, adéu 456", /\d+/g)); // Retorna ["123", "456"]
```

## Exercici 13 - `replace`
Crea una funció que substitueixi la primera aparició d'un substring dins d'una cadena per un altre substring utilitzant `replace`.

```javascript
function substituirCadena(cadena, vellSubcadena, nouSubcadena) {
    // A completar
}

// Exemple d'ús:
console.log(substituirCadena("Hola món", "món", "JavaScript")); // Retorna "Hola JavaScript"
```

## Exercici 14 - `replaceAll`
Escriu una funció que substitueixi totes les aparicions d'un substring dins d'una cadena per un altre substring utilitzant `replaceAll`.

```javascript
function substituirTotes(cadena, vellSubcadena, nouSubcadena) {
    // A completar
}

// Exemple d'ús:
console.log(substituirTotes("Hola món, món", "món", "JavaScript")); // Retorna "Hola JavaScript, JavaScript"
```



## Exercici 15 - `toLowerCase`
Crea una funció que converteixi tots els caràcters d'una cadena en minúscules utilitzant `toLowerCase`.

```javascript
function convertirMinuscules(cadena) {
    // A completar
}

// Exemple d'ús:
console.log(convertirMinuscules("Hola Món")); // Retorna "hola món"
```

## Exercici 16 - `toUpperCase`
Escriu una funció que converteixi tots els caràcters d'una cadena en majúscules utilitzant `toUpperCase`.

```javascript
function convertirMajuscules(cadena) {
    // A completar
}

// Exemple d'ús:
console.log(convertirMajuscules("Hola Món")); // Retorna "HOLA MÓN"
```

## Exercici 17 - `trimStart`
Crea una funció que elimini els espais en blanc al principi d'una cadena utilitzant `trimStart`.

```javascript
function eliminarEspaisInicials(cadena) {
    // A completar
}

// Exemple d'ús:
console.log(eliminarEspaisInicials("   Hola Món")); // Retorna "Hola Món"
```

## Exercici 18 - `trimEnd`
Escriu una funció que elimini els espais en blanc al final d'una cadena utilitzant `trimEnd`.

```javascript
function eliminarEspaisFinals(cadena) {
    // A completar
}

// Exemple d'ús:
console.log(eliminarEspaisFinals("Hola Món   ")); // Retorna "Hola Món"
```

## Exercici 19 - `trim`
Crea una funció que elimini els espais en blanc tant al principi com al final d'una cadena utilitzant `trim`.

```javascript
function eliminarEspaisExtrems(cadena) {
    // A completar
}

// Exemple d'ús:
console.log(eliminarEspaisExtrems("   Hola Món   ")); // Retorna "Hola Món"
```