# Guia d'ús del hook `useEffect` en React

El hook `useEffect` és una de les eines més importants de React, ja que permet gestionar efectes secundaris en els components funcionals. Aquesta guia t'ensenyarà com utilitzar-lo i en quins casos és útil, amb exemples senzills per ajudar-te a entendre-ho.

---

## Què és `useEffect`?

`useEffect` és un hook que permet executar una funció després de renderitzar un component. S'utilitza per gestionar efectes secundaris com ara:

- Recuperar dades d'una API.
- Subscriure's a esdeveniments o serveis.
- Actualitzar el DOM manualment.
- Gestionar temporitzadors o intervals.

El format bàsic és el següent:

```javascript
import { useEffect } from 'react';

useEffect(() => {
  // L'efecte a executar
  return () => {
    // Cleanup (opcional)
  };
}, [dependències]);
```

---

## Com funciona?

### Paràmetres de `useEffect`

1. **Funció de callback:** La funció que React executarà després de renderitzar el component.
2. **Array de dependències:** Una llista de valors que React observa per determinar si cal tornar a executar l'efecte.

### Flux d'execució

- Si l'array de dependències està **buit (`[]`)**, l'efecte només s'executa una vegada després del primer renderitzat.
- Si conté **valors**, l'efecte s'executa sempre que algun d'aquests valors canviï.
- Si no hi ha **array de dependències**, l'efecte s'executa després de cada renderitzat.

---

## Exemples pràctics

### 1. Executar una vegada (similar a `componentDidMount`)

Utilitzem `useEffect` per carregar dades d'una API quan el component es renderitza per primera vegada.

```javascript
import { useEffect, useState } from 'react';

function App() {
  const [data, setData] = useState(null);

  useEffect(() => {
    fetch('https://api.example.com/data')
      .then((response) => response.json())
      .then((data) => setData(data));
  }, []); // Array buit: només s'executa un cop

  return (
    <div>
      <h1>Dades:</h1>
      {data ? <pre>{JSON.stringify(data, null, 2)}</pre> : <p>Carregant...</p>}
    </div>
  );
}

export default App;
```

### 2. Actualitzar un valor quan canvia una dependència

Podem utilitzar l'array de dependències per reaccionar a canvis específics.

```javascript
import { useEffect, useState } from 'react';

function Counter() {
  const [count, setCount] = useState(0);

  useEffect(() => {
    console.log(`El valor del comptador és: ${count}`);
  }, [count]); // Només s'executa quan 'count' canvia

  return (
    <div>
      <p>Comptador: {count}</p>
      <button onClick={() => setCount(count + 1)}>Incrementa</button>
    </div>
  );
}

export default Counter;
```

### 3. Detecció de tecles de fletxa

En aquest exemple, utilitzem `useEffect` per detectar quan l'usuari prem una tecla de fletxa i reaccionar en conseqüència.

```javascript
import { useEffect, useState } from 'react';

function ArrowKeyListener() {
  const [direction, setDirection] = useState('');

  useEffect(() => {
    const handleKeyDown = (event) => {
      switch (event.key) {
        case 'ArrowUp':
          setDirection('Amunt');
          break;
        case 'ArrowDown':
          setDirection('Avall');
          break;
        case 'ArrowLeft':
          setDirection('Esquerra');
          break;
        case 'ArrowRight':
          setDirection('Dreta');
          break;
        default:
          break;
      }
    };

    window.addEventListener('keydown', handleKeyDown);

    return () => {
      window.removeEventListener('keydown', handleKeyDown); // Neteja l'esdeveniment
    };
  }, []);

  return <p>Direcció: {direction}</p>;
}

export default ArrowKeyListener;
```

---

## Bones pràctiques

1. **Mantingues les dependències precises:** Només inclou al llistat les variables que l'efecte necessita realment.
2. **Evita efectes innecessaris:** Si pots calcular un valor dins del renderitzat, no cal utilitzar `useEffect`.
3. **Gestiona la neteja:** Sempre elimina temporitzadors, subscripcions, o qualsevol recurs quan el component es desmunti.

---

## Quan utilitzar `useEffect`?

Utilitza `useEffect` quan necessitis:

- Fer peticions a una API després de renderitzar el component.
- Configurar esdeveniments o subscripcions.
- Actualitzar el títol de la pàgina amb `document.title`.
- Gestionar temporitzadors o intervals.

Si no necessites efectes secundaris, evita utilitzar `useEffect` innecessàriament.

---

Amb aquesta guia, ja pots començar a treballar amb `useEffect` de manera eficient i estructurada!
