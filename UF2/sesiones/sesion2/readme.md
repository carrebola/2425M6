# Examen repaso conceptos SPA

1. Crea carpeta con nombre sesion3Examen
2. Crea proyecto
3. Crea repositorio y crea .gitignore
4. Instala dependencia lite-server 
5. Configura lite-server (mira la documentación) para ubicar archivos en carpeta scr
6. Crea spa con los siguientes componentes:
   - Componente header
     - Componente logo
     - Componente menu
   - Vista home
   - Vista about
   - Vista partidas
7. Pagina home y about solo con h1 y 'lorem ipsum'
8. Página partidas:
   
## Tasca 1: Utilitza el prototip adjunt per la vista partidas. Crea les funcions **pintaTabla()**. Aquesta ha d’injectar el codi html corresponent al div que conté la taula del prototip en la etiqueta `<div id=”partidas”>` respectivament.

## Tasca 2: Generant taula a partir d’un array de dades
- Crea un array amb nom partidas amb dades inventades de partides (en format json):
`javascript
const partidas = [
  {
    avatar: "🐉",
    nick: "DragonSlayer",
    puntos: 9999,
    fecha: "2024-11-01"
  },
  {
    avatar: "🧙‍♂️",
    nick: "WizardMaster",
    puntos: 8500,
    fecha: "2024-11-03"
  },
  {
    avatar: "🤖",
    nick: "RoboWarrior",
    puntos: 7230,
    fecha: "2024-11-05"
  },
  {
    avatar: "👽",
    nick: "AlienHunter",
    puntos: 6420,
    fecha: "2024-11-07"
  },
  {
    avatar: "🦄",
    nick: "UnicornSparkle",
    puntos: 5700,
    fecha: "2024-11-09"
  },
  {
    avatar: "👻",
    nick: "GhostChaser",
    puntos: 4930,
    fecha: "2024-11-10"
  },
  {
    avatar: "🦸‍♀️",
    nick: "SuperHeroGal",
    puntos: 4320,
    fecha: "2024-11-11"
  },
  {
    avatar: "🐱‍👤",
    nick: "NinjaKitty",
    puntos: 3890,
    fecha: "2024-11-12"
  },
  {
    avatar: "💀",
    nick: "SkullCrusher",
    puntos: 3450,
    fecha: "2024-11-13"
  },
  {
    avatar: "🦖",
    nick: "DinoDestroyer",
    puntos: 3120,
    fecha: "2024-11-14"
  }
];
`

- Actualitza la funció pintaTabla(partidas) de manera que injecti la taula generada a partir de les dades de l’array  que rep
Treu la taula per consola.
TEST: Si crides la funció passant-li l’array partides (pintaTabla(partidas)) s’hauria de mostrar igual que la tasca anterior pero amb les dades noves. 


## Tasca 3: Crea la funció insertaNuevaPartida(datosEjemploPartida) 
- Crea una funció capaç d’afegir un registre a l’array partides (fes servir push) amb l’objecte partida que rep.
- Treu el nou array per consola
- Crida a la funció pintaTabla(partidas)

## Tasca 4: Crea una funció amb nom pintaDatosPartida(partida) 
- Aquesta funció rep les dades d'una partida jugada i els mostra per consola i per pantalla fent servir una finestra de confirmació confirm() demanant si vols desar la partida.
  - Si la resposta es sí, ha de cridar a la funció insertaNuevaPartida(nuevaPartida) després ha de cridar a la funció pintaTabla(partidas)
  
  Exemple de partida:
  `
  const nuevaPartida = {
    avatar: "👽",
    nick: "Paco",
    puntos: 2,
    fecha: "2024-11-12"
  }
  `
TEST: Crida a la funció pintaDatosPartida(datosEjemploPartida)





