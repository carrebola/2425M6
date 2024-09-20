### Resum dels Conceptes

1. **`Math.random()` per generar números aleatoris**:
   - `Math.random()` genera un decimal aleatori entre 0 i 1. Per obtenir un enter en un rang determinat, es multiplica i es fa servir `Math.floor()` per arrodonir cap avall.
   - Exemple:
   ```javascript
   const randomNumber = Math.floor(Math.random() * 50); 
   console.log(randomNumber);
   ```
   Aquí es genera un nombre aleatori entre 0 i 49. Això és útil per seleccionar aleatòriament elements o per jocs que requereixen números inesperats.

2. **Manipulació del DOM amb `document.querySelector()` i `innerHTML`**:
   - `querySelector()` permet seleccionar el primer element que coincideixi amb un selector CSS, mentre que `innerHTML` permet modificar el contingut HTML d'aquest element.
   - Exemple:
   ```javascript
   document.querySelector('#miElement').innerHTML = "<b>Hola, món!</b>";
   ```
   Aquest codi selecciona l'element amb l'`id` `miElement` i canvia el seu contingut a "Hola, món!" amb format en negreta.

3. **Declaració i ús d'arrays**:
   - Un array és una col·lecció de valors. Els elements es poden accedir per la seva posició (índex).
   - Exemple:
   ```javascript
   const fruits = ["Poma", "Plàtan", "Taronja"];
   console.log(fruits[1]);  // Mostra "Plàtan"
   ```
   Aquí es crea un array `fruits` amb tres elements. Després, es mostra el segon element utilitzant l'índex 1.

4. **Arrays de dues dimensions**:
   - Un **array de dues dimensions** és com una taula, on cada fila conté diversos elements.
   - Exemple:
   ```javascript
   const quiz = [
     ["Quina és la capital de França?", "París", "Londres", "Berlín", "Madrid", 1],
     ["Quina és la capital d'Espanya?", "Lisboa", "Madrid", "Roma", "Atenes", 2],
     ["Quina és la capital d'Itàlia?", "Roma", "París", "Madrid", "Lisboa", 1]
   ];

   console.log(quiz[0][0]);  // Mostra "Quina és la capital de França?"
   console.log(quiz[1][2]);  // Mostra "Madrid" (segona pregunta, tercera resposta)
   console.log(quiz[2][1]);  // Mostra "Roma"
   ```
   En aquest exemple, es crea un array que conté preguntes i respostes, i es poden accedir les dades per la seva fila i columna. És útil per estructurar informació complexa de manera eficient.

5. **Funcions per modularitzar el codi**:
   - Les funcions encapsulen un bloc de codi que es pot reutilitzar múltiples vegades.
   - Exemple:
   ```javascript
   function saludar(nom) {
     return "Hola, " + nom + "!";
   }
   console.log(saludar("Joan"));
   ```
   Aquesta funció rep un paràmetre `nom` i retorna una salutació personalitzada. Les funcions ajuden a estructurar millor el codi.

6. **Afegir interaccions amb `addEventListener()`**:
   - `addEventListener()` és la manera estàndard d'afegir esdeveniments a elements HTML. Això evita sobrescriure esdeveniments anteriors.
   - Exemple:
   ```javascript
   document.querySelector('#boton').addEventListener('click', function() {
     alert("Has fet clic!");
   });
   ```
   En aquest exemple, quan l'usuari fa clic al botó amb `id="boton"`, es mostra una alerta amb el missatge "Has fet clic!".

7. **Control de flux amb `if...else`**:
   - `if...else` s'utilitza per executar diferents blocs de codi depenent d'una condició.
   - Exemple:
   ```javascript
   const temperatura = 30;
   if (temperatura > 25) {
     console.log("Fa calor");
   } else {
     console.log("Fa fred");
   }
   ```
   Si la temperatura és superior a 25 graus, es mostra el missatge "Fa calor", si no, "Fa fred".

8. **Comprovació de valors buits amb condicions**:
   - Comprovar si una variable està buida és important per validar entrades d'usuari.
   - Exemple:
   ```javascript
   const missatge = "";
   if (missatge === "") {
     console.log("El missatge està buit.");
   } else {
     console.log("Missatge vàlid.");
   }
   ```
   Aquí es comprova si la variable `missatge` està buida i es mostra un missatge d'error si és el cas.
