
# Exercici 1 - Calculadora bàsica

L'objectiu d'aquests exercicis és que vagis desenvolupant la funcionalitat d'una calculadora bàsica pas a pas, utilitzant JavaScript. A mesura que avancis, utilitzaràs console.log() per anar comprovant el funcionament del teu codi i resoldre possibles errors.

![image](https://github.com/user-attachments/assets/576a35eb-949f-4478-bab1-8632a3013830)


## **Exercici 1: Configurar l'entorn**
**Objectiu**: Configurar la base de la calculadora amb l'HTML i afegir l'estructura inicial en JavaScript.

Crea un fitxer HTML amb una secció div per mostrar el resultat (pantalla) i un altre div per col·locar els botons de la calculadora (números de 0 a 9, sumes i restes, i el botó "=").

Després, en el fitxer de JavaScript, afegeix aquest codi:

```javascript
console.log("Calculadora inicialitzada!");
```


>[!NOTE]
   >
   >Aquest missatge apareixerà a la consola del navegador per confirmar que el JavaScript s'ha carregat correctament.

## **Exercici 2: Capturar clics en els botons**
**Objectiu**: Fer que cada botó numèric mostri el seu valor a la consola quan es clica.

Afegeix un addEventListener a cada botó dels números (0 a 9) per tal que quan es faci clic, es mostri el número a la consola.

Utilitza console.log() dins de l'esdeveniment per imprimir el valor del botó a la consola.

Codi suggerit:


```javascript
document.getElementById('btn1').addEventListener('click', function() {
  console.log('1');
});
```



>[!NOTE] Què s'espera obtenir: 
  >Quan facis clic al botó "1", hauries de veure el número 1 a la consola del navegador.

## Exercici 3: Mostrar números a la pantalla
**Objectiu**: Fer que en lloc d'imprimir els números a la consola, es mostrin en un div de la pantalla de la calculadora.

Crea un div a l'HTML amb un id="pantalla" on es mostrarà el número.

Canvia la funció perquè, en comptes d'imprimir a la consola, el número es mostri dins del div.

Codi suggerit:

```javascript

document.getElementById('btn1').addEventListener('click', function() {
  document.getElementById('pantalla').textContent = '1';
});
```

[!NOTE] 
  >Què s'espera obtenir: 
    >En fer clic a "1", el número 1 hauria d'aparèixer al div de la pantalla de la calculadora.

## Exercici 4: Afegir números consecutius
**Objectiu**: Fer que es puguin afegir números consecutius a la pantalla sense que es sobreescriguin.

Modifica la funció perquè quan es prem un altre número, aquest s'afegisca a la pantalla, en lloc de substituir el número anterior.

Utilitza la variable entradaActual per emmagatzemar els números i després mostrar-los.

Codi suggerit:


```javascript
let entradaActual = '';

document.getElementById('btn1').addEventListener('click', function() {
  entradaActual += '1';
  document.getElementById('pantalla').textContent = entradaActual;
});
```

>[!NOTE] Què s'espera obtenir: 
  >Ara, en prémer diversos botons numèrics, els números es concatenaran i es mostraran a la pantalla.

## Exercici 5: Afegir operadors
**Objectiu**: Permetre l'ús d'operadors com + i -.

Fes que els botons + i - també afegeixin l'operador a la variable entradaActual.

Mostra l'operació completa a la pantalla.

Codi suggerit:

```javascript
document.getElementById('btnSuma').addEventListener('click', function() {
  entradaActual += '+';
  document.getElementById('pantalla').textContent = entradaActual;
});
```
Què s'espera obtenir: Si prems 1 + 2, hauries de veure 1+2 a la pantalla de la calculadora.

## Exercici 6: Realitzar el càlcul
**Objectiu**: Fer que el botó = calculi el resultat i el mostri a la pantalla.

Utilitza la funció eval() per fer el càlcul quan es prem =.

Fes servir console.log() per mostrar a la consola el resultat abans de mostrar-lo a la pantalla, per assegurar-te que el càlcul és correcte.

Codi suggerit:

```javascript

document.getElementById('btnIgual').addEventListener('click', function() {
  const resultat = eval(entradaActual);
  console.log('Resultat:', resultat); // Testeja el resultat a la consola
  document.getElementById('pantalla').textContent = resultat;
});
```
>[NOTE!] Què s'espera obtenir: 
  >Quan es premin els botons 1 + 2 =, el resultat 3 apareixerà a la pantalla i a la consola.

## Exercici 7: Netejar la pantalla
**Objectiu**: Afegir la funcionalitat de netejar la pantalla amb el botó C.

Crea la funció que reiniciï la variable entradaActual i faci que la pantalla torni a mostrar 0.
Codi suggerit:

```javascript

document.getElementById('btnBorrar').addEventListener('click', function() {
  entradaActual = '';
  document.getElementById('pantalla').textContent = '0';
});
```

>[NOTE!]Què s'espera obtenir: 
  >En fer clic a C, la pantalla es buida i torna a mostrar 0.

## Exercici 8: Control d'errors
**Objectiu**: Afegir control d'errors per evitar que l'usuari introdueixi operacions no vàlides.

Abans de fer el càlcul amb eval(), comprova que l'operació sigui vàlida.

Per exemple, evita que hi hagi dos operadors consecutius o que es premi = sense cap número.

Codi suggerit (control d'errors bàsic):

```javascript

document.getElementById('btnIgual').addEventListener('click', function() {
  try {
    if (entradaActual !== '') {
      const resultat = eval(entradaActual);
      document.getElementById('pantalla').textContent = resultat;
    } else {
      console.log('No hi ha res a calcular');
    }
  } catch (error) {
    console.log('Error en l\'operació:', error);
    document.getElementById('pantalla').textContent = 'Error';
  }
});
```
>[NOTE!]Què s'espera obtenir: 
>Si hi ha un error en l'operació, es mostra un missatge d'error a la pantalla.
