# Resum Esquemàtic de la Pràctica de la Calculadora en JavaScript

## 1. Estructura HTML
- **Divs per pantalla**: Mostra els resultats i entrades de la calculadora.
- **Botons numèrics i operadors**: Números del `0` al `9`, operadors `+`, `-`, `=`, i un botó `C` per esborrar.

---

## 2. JavaScript - Passos clau
### 1. **Inicialització**:
   - Càrrega de JavaScript amb `console.log("Calculadora inicialitzada!");` per confirmar que el codi funciona.

### 2. **Capturar clics en botons**:
   - Ús de **`addEventListener()`** per gestionar esdeveniments de clic.
   - Exemple: Captura del valor d'un botó i ús de `console.log()` per mostrar-lo a la consola.

### 3. **Mostrar números a la pantalla**:
   - Assignar el valor dels botons al `div` de la pantalla amb **`textContent`**.
   - Concatenació de números amb una variable (`entradaActual`) per no sobreescriure els valors anteriors.

### 4. **Afegir operadors**:
   - Els operadors `+` i `-` també s'afegeixen a la variable `entradaActual` i es mostren a la pantalla.

### 5. **Realitzar càlculs amb `eval()`**:
   - Quan es prem el botó `=`, es realitza l'operació amb **`eval()`**.
   - Es mostra el resultat a la pantalla i es fa una comprovació prèvia amb `console.log()` per verificar el resultat.

### 6. **Netejar la pantalla**:
   - Botó `C` per reiniciar la variable d'entrada i tornar a mostrar `0` a la pantalla.

### 7. **Control d'errors**:
   - Ús d'un bloc **`try-catch`** per gestionar operacions no vàlides.
   - Mostrar missatge d'error a la consola i a la pantalla si es detecten errors en el càlcul.

---

## 3. Mètodes i Conceptes Usats
- **`addEventListener()`**: Per capturar esdeveniments com clics.
- **`textContent`**: Per mostrar contingut dins d'un element HTML.
- **Variables**:
  - **`entradaActual`**: Per emmagatzemar el valor actual de l'operació a mesura que es concatena.
  - **`resultat`**: Per emmagatzemar i mostrar el resultat del càlcul.
- **`eval()`**: Per executar la cadena com una expressió matemàtica.
- **`try-catch`**: Per controlar errors d'execució en el càlcul.

---

## 4. Testejar el codi amb `console.log()`
- S'utilitza **`console.log()`** per verificar els valors intermedis i assegurar-se que el comportament del codi és l'esperat a cada pas (mostrant valors dels botons, resultat del càlcul, etc.).

---

