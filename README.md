![Alt text](https://techdevised.files.wordpress.com/2021/01/javascript.png 'a title')

 # Notas sobre Javascript moderno

**Autores**: Equipo de élite de formación

**Organización**: Junta de Extremadura

**Índice**  
  
- [Notas sobre Javascript moderno](#notas-sobre-javascript-moderno)
  - [Introducción](#introducción)
  - [Template String](#template-string)
  - [Funciones](#funciones)
  - [Funciones anónimas](#funciones-anónimas)
  - [Funciones de flecha](#funciones-de-flecha)
  - [Objetos en Javascript](#objetos-en-javascript)
  - [Relaciones entre Objetos](#relaciones-entre-objetos)



<div id='id1'/>

## Introducción

JavaScript es uno de los lenguajes de programación más populares y versátiles del mundo. Se utiliza para construir aplicaciones web, móviles y de escritorio, así como para crear programas y scripts en el lado del servidor. Con la creciente demanda de aplicaciones web y móviles interactivas y dinámicas, JavaScript ha evolucionado rápidamente en los últimos años para convertirse en un lenguaje moderno y potente.

En estas notas te presentamos JavaScript moderno, una guía completa para las últimas características y herramientas de JavaScript que los desarrolladores necesitan conocer para crear aplicaciones web de alta calidad y con una gran experiencia de usuario.

En los apartados siguientes cubriremos los siguientes temas:

- Los fundamentos de JavaScript, incluyendo variables, tipos de datos, operadores, estructuras de control y funciones.
- Los conceptos avanzados de JavaScript, como la programación orientada a objetos, la manipulación del DOM, las promesas y el manejo de errores.
- Las características modernas de JavaScript, incluyendo funciones de flecha, clases, módulos, destructuring, spread syntax y async/await.
- Las bibliotecas y frameworks de JavaScript populares, como React, Angular y Vue.

Con estas notas proporcionamos una guía completa y actualizada para el mundo de JavaScript moderno, con ejemplos prácticos y aplicaciones útiles que te ayudarán a construir aplicaciones web modernas y escalables. ¡Comencemos!

<div id='id2'/>

## Template String

Las **template string** son una característica que permite formatear cadenas de texto de forma muy flexible. Para ello se utilizan backticks(`) en lugar de comillas dobles o comillas simples. En español se traduce este término como *acento grave inverso*.

Una **template string** puede contener expresiones contenidas dentro del marcador de posición, o *placeholder*, **${}**, que serán evaluadas e integradas dentro del texto. Esto hace muy sencillo concatenar cadenas de caracteres sin utilizar el operador **+**. 


```js
const nombre = 'Juan Expósito'
const edad = '47'

const mensaje = `Mi nombre es ${nombre} y tengo ${edad} años`

console.log(mensaje)

// La forma tradicional de hacerlo es la siguiente

const mensaje = 'Mi nombre es ' + nombre + ' y tengo ' + edad + ' años'

console.log(mensaje)

```

En el ejemplo, las constantes **nombre** y **edad** se insertan en el texto a través de los *placeholders* que están dentro de los *backtips*.

**Template string** soporta múltiples líneas para que el texto sea lo más legible posible. Al final de cada línea se añade un salto de línea automáticamente.



```js
const nombre = 'Juan Expósito'
const edad = '47'

const mensaje = `Mi nombre es ${nombre} 
                y tengo ${edad} años`

console.log(mensaje)

// Salida:
// Mi nombre es Juan Expósito
// y tengo 47 años

// La forma tradicional de hacerlo es la siguiente

```

<div id='id3'/>

## Funciones

Las funciones son bloques de código reutilizable que se pueden llamar en cualquier momento dentro de un programa. Las funciones se definen utilizando la palabra reservada **function** seguida del nombre de la función y paréntesis, donde se pueden añadir algunos parámetros de entrada. El cuerpo de la función debe ir entre llaves **{ }**.

```js
function sumar(a, b) {
    return a + b
}

const resultado = sumar(2, 3)
console.log(`El resultado es ${resultado}`)

//Salida:
//El resultado es 5

```
En este ejemplo, la función sumar toma los parámetros *a* y *b*, que se suman y se devuelve el resultado. Luego, se llama a la función pasando los valores 2 y 3 como argumentos y se guarda el resultado en la variable *resultado*.

<div id='id4'/>

## Funciones anónimas

Las funciones en JavaScript también pueden ser anónimas, lo que significa que no tienen un nombre definido y pueden ser asignadas a una variable. Aquí hay un ejemplo de una función anónima que devuelve el cuadrado de un número:

```js
const cuadrado = function(num) {
  return num * num
}

const resultado = cuadrado(5) 
console.log(`El resultado es ${resultado}`)

// Salida:
// El resultado es 25

```
En este ejemplo, se define una función anónima que se asigna a la variable *cuadrado*. La función toma un parámetro *num* y devuelve su cuadrado. Luego, se llama a la función pasando el valor 5 como argumento y se muestra el resultado.

Además, las funciones en JavaScript pueden ser declaradas dentro de otras funciones, lo que se conoce como funciones anidadas o *closures*. Estas funciones tienen acceso al ámbito (*scope*) de la función externa y pueden acceder a sus variables y parámetros.

<div id='id5'/>

## Funciones de flecha

Las funciones de flecha, o *arrow functions*, son una forma más concisa de escribir funciones en JavaScript. Se introdujeron en [ECMAScript 6](https://www.w3schools.com/js/js_es6.asp) y ofrecen algunas ventajas sobre las funciones tradicionales. Lo primero que hay que tener en cuenta es que son funciones anónimas, por lo tanto deben añadirse a una variable.

```js
const sumar = (a, b) => {
    return a + b
}

const resultado = sumar(2, 3)
console.log(`El resultado es ${resultado}`)

//Salida:
//El resultado es 5

```
Hemos convertido la función *sumar* en una función de flecha. Para ello, se elimina la palabra reservada *function* y se añade una flecha compuesta por los signos *igual* y *mayor*

Si la función solo contiene una línea se puede obviar la palabra reservada *return* y eliminar las llaves.

```js
const sumar = (a, b) => a + b

const resultado = sumar(2, 3)
console.log(`El resultado es ${resultado}`)

//Salida:
//El resultado es 5

```

<div id='id6'/>

## Objetos en Javascript

En JavaScript, un objeto es una entidad que contiene propiedades y métodos. Las propiedades son variables que almacenan datos, mientras que los métodos son funciones que realizan acciones. Los objetos son una parte fundamental de la programación en JavaScript y se utilizan para representar y manipular datos de una manera estructurada y organizada.

Los objetos se definen utilizando llaves *{ }* y pueden contener cualquier número de pares de clave-valor. La clave es una cadena que identifica la propiedad o el método, mientras que el valor es el contenido de la propiedad o la definición de la función del método. Aquí hay un ejemplo de un objeto simple en JavaScript:

```js
const persona = {
  nombre: 'Juan Expósito',
  edad: 47,
  saludar: function() {
    console.log(`Hola, mi nombre es ${this.nombre} y mi tengo ${this.edad} años`)
  }
}

persona.saludar(); 
// Salida:
// Hola, mi nombre es Juan Expósito y tengo 47 años
```

Las funciones creadas con *function* pueden utilizar la palabra reservada **this** para acceder a las variables del objeto. En cambio, si utilizáramos una función de flecha, el **this** se referirá al contexto global, por lo tanto habría que hacer referencia al nombre del objeto.

```js
const persona = {
  nombre: 'Juan Expósito',
  edad: 47,
  saludar: () => {
    // Lo siguiente daría error:
    console.log(`Hola, mi nombre es ${this.nombre} y mi tengo ${this.edad} años`)
    // Lo siguiente daría como resultado undefined en ambos casos:
    console.log(`Hola, mi nombre es ${this.nombre} y mi tengo ${this.edad} años`)
    // Lo siguiente daría el resultado correcto pero no sería muy acertado utilizarlo
    console.log(`Hola, mi nombre es ${persona.nombre} y mi tengo ${persona.edad} años`)

  }
}

```

Los objetos en JavaScript son dinámicos, lo que significa que se pueden agregar o eliminar propiedades y métodos en cualquier momento. También se pueden anidar objetos dentro de otros objetos para crear estructuras más complejas. Los objetos son una parte fundamental de JavaScript y se utilizan ampliamente en el desarrollo de aplicaciones web modernas.

<div id='id7'/>

## Relaciones entre Objetos

Algo con lo que nos vamos a encontrar en numerosas ocasiones son los objetos anidados u objetos dentro de otros objetos. 

```js
const factura = {
    id: 102023,
    concepto: 'Oracle Supremun License',
    fecha: new Date(),
    cliente: {
        id: 23,
        nombre: 'Juan Expósito',
        edad: 47
    },
    total: 1000000,
    saludar: function () {
        return `Hola ${this.cliente.nombre}`
    }
}

factura.total = 2000000
console.log(factura.saludar())
````
El objeto anterior muestra el objeto *factura* con un objeto *cliente* que forma parte de la propia estructura.