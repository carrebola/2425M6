# Tutorial: Clases en JavaScript (ES6)

Las clases en JavaScript fueron introducidas con ECMAScript 2015 (ES6). Ofrecen una sintaxis más limpia y estructurada para trabajar con objetos y la herencia, aunque internamente siguen utilizando prototipos.

---

## Índice
1. [¿Qué es una clase?](#qué-es-una-clase)
2. [Declaración de una clase](#declaración-de-una-clase)
3. [El constructor](#el-constructor)
4. [Métodos de instancia](#métodos-de-instancia)
5. [Métodos estáticos](#métodos-estáticos)
6. [Herencia con clases](#herencia-con-clases)
7. [Ejemplo completo](#ejemplo-completo)

---

## ¿Qué es una clase?

Una **clase** es una plantilla que define cómo se crean objetos con propiedades y métodos específicos. En JavaScript, aunque todo se basa en prototipos, las clases proporcionan una sintaxis más intuitiva para definir y extender objetos.

Ejemplo simplificado:
```js
class Persona {
  constructor(nombre) {
    this.nombre = nombre;
  }

  saludar() {
    console.log(`Hola, soy ${this.nombre}`);
  }
}

const juan = new Persona("Juan");
juan.saludar(); // Hola, soy Juan
```

---

## Declaración de una clase

Las clases se definen utilizando la palabra clave `class`. Pueden contener un **constructor** y **métodos**.

```js
class Persona {
  constructor(nombre) {
    this.nombre = nombre;
  }

  saludar() {
    console.log(`Hola, soy ${this.nombre}`);
  }
}
```

- **`constructor`**: Método especial que inicializa propiedades.
- **`saludar`**: Método de instancia (se accede mediante una instancia de la clase).

---

## El constructor

El `constructor` es el método que se ejecuta automáticamente cuando se crea una nueva instancia de la clase.

```js
class Coche {
  constructor(marca, modelo) {
    this.marca = marca;
    this.modelo = modelo;
  }
}

const miCoche = new Coche("Toyota", "Corolla");
console.log(miCoche.marca); // Toyota
console.log(miCoche.modelo); // Corolla
```

---

## Métodos de instancia

Los **métodos de instancia** se definen dentro de la clase y se pueden invocar a través de una instancia.

```js
class Persona {
  constructor(nombre) {
    this.nombre = nombre;
  }

  saludar() {
    console.log(`Hola, soy ${this.nombre}`);
  }
}

const maria = new Persona("María");
maria.saludar(); // Hola, soy María
```

---

## Métodos estáticos

Los **métodos estáticos** pertenecen a la clase en sí misma, no a sus instancias. Se definen con la palabra clave `static`.

```js
class Matematica {
  static sumar(a, b) {
    return a + b;
  }
}

console.log(Matematica.sumar(3, 5)); // 8
```

---

## Herencia con clases

La **herencia** permite crear clases que extienden las funcionalidades de otra clase mediante la palabra clave `extends`. Se utiliza `super()` para llamar al constructor de la clase padre.

```js
class Persona {
  constructor(nombre) {
    this.nombre = nombre;
  }

  saludar() {
    console.log(`Hola, soy ${this.nombre}`);
  }
}

class Estudiante extends Persona {
  constructor(nombre, curso) {
    super(nombre); // Llama al constructor de Persona
    this.curso = curso;
  }

  estudiar() {
    console.log(`${this.nombre} está estudiando ${this.curso}`);
  }
}

const juan = new Estudiante("Juan", "JavaScript");
juan.saludar(); // Hola, soy Juan
juan.estudiar(); // Juan está estudiando JavaScript
```

---

## Ejemplo completo

```js
class Persona {
  constructor(nombre, edad) {
    this.nombre = nombre;
    this.edad = edad;
  }

  saludar() {
    console.log(`Hola, soy ${this.nombre} y tengo ${this.edad} años.`);
  }
}

class Profesor extends Persona {
  constructor(nombre, edad, materia) {
    super(nombre, edad);
    this.materia = materia;
  }

  enseñar() {
    console.log(`Enseño la materia de ${this.materia}.`);
  }
}

const pedro = new Profesor("Pedro", 40, "Matemáticas");
pedro.saludar(); // Hola, soy Pedro y tengo 40 años.
pedro.enseñar(); // Enseño la materia de Matemáticas.
```

---

## Conclusión

Las clases en ES6 facilitan la creación de objetos y herencias en JavaScript, proporcionando una sintaxis más limpia y estructurada que mejora la legibilidad y el mantenimiento del código.
