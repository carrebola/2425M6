
# Pràctica 3 - Joc de Tauler amb Preguntes

L'objectiu d'aquest exercici és estendre el teu quiz interactiu afegint un joc de tauler. El jugador avança o retrocedeix segons les respostes encertades o fallades. A mesura que avancis, utilitzaràs `console.log()` per comprovar l'estat del codi i solucionar possibles errors.

![image](https://github.com/user-attachments/assets/f5a68d29-e5e5-427c-a37a-9dd11ae965ed)


### **Tasques a Realitzar**

#### **Tasca 1: Definir les variables principals**
**Objectiu**: Crear les variables necessàries per controlar la posició del jugador, el nombre d'encerts i errors.

1. **Defineix les següents variables:**
   - `posicioActual`: Variable que representa la casella actual del jugador (inicia en 1).
   - `encerts`: Variable que comptabilitza el nombre de respostes correctes (inicia en 0).
   - `errors`: Variable que comptabilitza el nombre de respostes incorrectes (inicia en 0).

2. **`console.log()`**: Mostra a la consola l'estat inicial de les variables per assegurar-te que estan inicialitzades correctament.
   
>[!NOTE]
   >**Què s'espera obtenir a la pantalla**: La consola hauria de mostrar:
   >``` 
   >Posició inicial: 1
   >Encerts: 0
   >Errors: 0
   >````

#### **Tasca 2: Controlar el moviment del jugador**
**Objectiu**: Crear les funcions per fer avançar o retrocedir el jugador en el tauler.

1. **Crea la funció `mouJugador(endavant)`**: Aquesta funció accepta un booleà que indica si el jugador ha encertat (true) o fallat (false).
   - Si `endavant` és `true`, incrementa la posició en 1.
   - Si `endavant` és `false`, resta 3 a la posició del jugador, però assegura't que no sigui inferior a 1.
   - Actualitza el color de la casella actual (vermell) i la casella anterior (blau).

2. **`console.log()`**: Mostra el resultat a la consola cada vegada que el jugador avança o retrocedeix, indicant la nova posició i si la resposta era correcta o incorrecta.

>[!NOTE]
   >**Què s'espera obtenir a la pantalla**: 
   >``` 
   >Resposta correcta! Nova posició: 2
   >Resposta incorrecta! Nova posició: 1
   >```

#### **Tasca 3: Comptabilitzar encerts i errors**
**Objectiu**: Comptabilitzar correctament les respostes encertades i fallades.

1. **Afegeix a la funció `mouJugador(endavant)`**:
   - Si `endavant` és `true`, incrementa la variable `encerts`.
   - Si `endavant` és `false`, incrementa la variable `errors`.

2. **`console.log()`**: Cada vegada que el jugador respongui, mostra el nombre total d'encerts i errors acumulats.

>[!NOTE]
   >**Què s'espera obtenir a la pantalla**: 
   >``` 
   >Encerts: 3
   >Errors: 2
   >```

#### **Tasca 4: Mostrar el final del joc**
**Objectiu**: Finalitzar el joc quan el jugador arribi a la casella 20 i mostrar un missatge amb el resultat final.

1. **Crea la funció `comprovaFinalJoc()`**:
   - Si el jugador arriba a la casella 20, mostra un missatge amb el nombre total d'encerts i errors.
   - Desactiva el botó "Siguiente Pregunta" perquè no es puguin fer més preguntes.

2. **`console.log()`**: Mostra un missatge de final de joc quan es completi.

>[!NOTE]
   >**Què s'espera obtenir a la pantalla**:
   >``` 
   >Has arribat a la casella 20! Encerts: 10, Errors: 5
   >```

#### **Tasca 5: Actualitzar la interfície gràfica**
**Objectiu**: Canviar el color de la casella actual i la casella anterior.

1. **Actualitza `mouJugador(endavant)` perquè la casella on es troba el jugador canviï a vermell (`.div-point`) i la casella anterior torni a blau.

2. **`console.log()`**: No cal missatge de consola per aquesta tasca, però comprova que visualment les caselles canviïn correctament a la pantalla.

---

### **Resum de Funcions i Variables:**

- **Variables**:
  - `posicioActual`: Casella actual del jugador.
  - `encerts`: Nombre total d'encerts.
  - `errors`: Nombre total d'errors.

- **Funcions**:
  - `mouJugador(endavant)`: Avança o retrocedeix el jugador i actualitza encerts/errors.
  - `comprovaFinalJoc()`: Comprova si el jugador ha arribat a la casella final i acaba el joc.




