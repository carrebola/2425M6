# Taules usuaris

A partir de l'exercici anterior, hem de crear un script que permeti la següent funcionalitat:
- Cada vegada que premem el botó 'Crear fitxa' afegirem les dades de l'usuari a un array.
- A continuació, actualitzarem la taula amb tots els usuaris.

![image](https://github.com/user-attachments/assets/98d606ac-19c9-4ab2-9f20-f731a2d0da15)

## Procediment
Partint de l'exercici anterior, modifica la funció que has creat per introduir les dades a la fitxa afegint el següent:

1. Crea una variable amb nom 'bd' i declara-la com a array amb `[]`.
2. Crea una variable de tipus objecte (anomena-la 'usuari') amb la següent estructura:
   '''
   {
     nom,
     cognoms,
     dni,
     urlImatge
   }
   '''
   i guarda-hi els valors que has obtingut dels inputs.

3. Afegeix l'objecte a l'array utilitzant `.push()`.
4. Crea i crida la funció `pintaTaula` que, de moment, només mostrarà un missatge per consola.
5. Actualitza la funció `pintaTaula` perquè recorri l'array 'bd' i generi una taula amb les dades dels usuaris, i a continuació, la inyecti al div corresponent.

