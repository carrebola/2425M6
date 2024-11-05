# Pràctica 4 - Fitxa

A partir dels arxius d’aquesta carpeta, crea l’script necessari per implementar la següent funcionalitat:
- En prémer el botó 'Crear Fitxa' les dades del formulari s’han de mostrar a la fitxa de la columna de la dreta.

![image](https://github.com/user-attachments/assets/b792862a-b085-4f53-8257-6e7b1f4c45f1)


## Procediment
1. Crea un arxiu main.js i vincula'l amb l'index.html. (Verifica el seu funcionament amb un console.log())
2. Afegeix a l'html un valor per defecte als inputs. A continuació, captura en diferents variables el value d'aquests i mostra'ls per consola. 
3. Crea una funció que agrupi el codi anterior. Prova-la.
4. Captura el botó 'Crear fitxa' i afegeix-li un observador d'esdeveniments (addEventListener) que cridi la funció que acabes de crear quan facis clic.
5. Modifica el codi html afegint els ids necessaris per poder seleccionar les etiquetes on van les dades com nom, dni, imatge, etc.
6. Injecta (amb **innerHTML**) el contingut de les variables en els inputs de la fitxa.

NOTA: Per afegir la imatge tens dues opcions:
  - Opció 1: Crear un div que envolti l'etiqueta `<img>`, assignar-li un id, i injectar en aquest div el codi html corresponent a la imatge. És a dir: `<img src='... `
  - Opció 2: Modificar l'atribut **src** de la imatge amb **setAttribute()**
