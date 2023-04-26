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
  - [Atributos de tipo arreglo](#atributos-de-tipo-arreglo)
  - [Operador Spread](#operador-spread)
  - [Operador Optional Chaining](#operador-optional-chaining)
  - [Operador Ternario](#operador-ternario)
  - [Arreglos en Javascript y operador Spread](#arreglos-en-javascript-y-operador-spread)
  - [Desestructuración de Objetos](#desestructuración-de-objetos)
  - [Desestructuración de Arreglos](#desestructuración-de-arreglos)
  - [Método map de arreglos](#método-map-de-arreglos)
  - [Método find de arreglos](#método-find-de-arreglos)
  - [Método filter de arreglos](#método-filter-de-arreglos)
  - [Importar módulos de Javascript](#importar-módulos-de-javascript)
  - [Exportar valores en Javascript](#exportar-valores-en-javascript)
  - [Promesas](#promesas)
  - [Consumir API REST con Fetch API](#consumir-api-rest-con-fetch-api)
  - [Async / Await](#async--await)
  - [API DOM](#api-dom)



## Introducción

JavaScript es uno de los lenguajes de programación más populares y versátiles del mundo. Se utiliza para construir aplicaciones web, móviles y de escritorio, así como para crear programas y scripts en el lado del servidor. Con la creciente demanda de aplicaciones web y móviles interactivas y dinámicas, JavaScript ha evolucionado rápidamente en los últimos años para convertirse en un lenguaje moderno y potente.

En estas notas te presentamos JavaScript moderno, una guía completa para las últimas características y herramientas de JavaScript que los desarrolladores necesitan conocer para crear aplicaciones web de alta calidad y con una gran experiencia de usuario.

En los apartados siguientes cubriremos los siguientes temas:

- Los fundamentos de JavaScript, incluyendo variables, tipos de datos, operadores, estructuras de control y funciones.
- Los conceptos avanzados de JavaScript, como la programación orientada a objetos, la manipulación del DOM, las promesas y el manejo de errores.
- Las características modernas de JavaScript, incluyendo funciones de flecha, clases, módulos, destructuring, spread syntax y async/await.
- Las bibliotecas y frameworks de JavaScript populares, como React, Angular y Vue.

Con estas notas proporcionamos una guía completa y actualizada para el mundo de JavaScript moderno, con ejemplos prácticos y aplicaciones útiles que te ayudarán a construir aplicaciones web modernas y escalables. ¡Comencemos!

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
```

El objeto anterior muestra el objeto *factura* con un objeto *cliente* que forma parte de la propia estructura. El acceso al *cliente* se debe hacer a través de **this** y navegando entre objetos hasta llegar al atributo deseado, por ejemplo: **this.cliente.nombre**

## Atributos de tipo arreglo

También nos vamos a encontrar con estructuras que incluyen arreglos dentro de los objetos.

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
    items: [
        {
            producto: 'Oracle DB',
            precio: 500000,
            cantidad: 1
        },
                {
            producto: 'Oracle Bus Service',
            precio: 500000,
            cantidad: 1
        },
                {
            producto: 'Oracle inomini patri',
            precio: 1000000,
            cantidad: 1
        }
    ],
    moneda: '€',
    total: function () {
        let total = 0
        this.items.forEach( item => {
            total += item.precio * item.cantidad
        })
        return total
    },
    saludar: function () {
        return `Hola ${this.cliente.nombre}`
    }
}
console.log(`El total es: ${factura.total()} ${factura.moneda}`)
// Salida:
// El total es: 2000000 €

```
En el ejemplo se define un arreglo con el símbolo de corchetes **[ ]** y dentro de ellos se van añadiendo los objetos que se necesitan, en este caso líneas de detalle de una factura.

El método **total** utiliza es capaz de recorrer el arreglo de **items** e ir calculando el acumulado de las líneas de detalle.

## Operador Spread

Si igualamos una constante, o variable, a otra constante que contenga un objeto, no obtenemos un clon del objeto, lo que obtenemos es una referencia más a ese mismo objeto. (tendremos un nuevo puntero a la misma zona de memoria)

```js
const persona = {
  nombre: 'Juan Expósito',
  edad: 47,
}

const persona2 = persona

console.log(persona === persona2)
// Salida:
// true
```
El ejemplo evalúa, con el operador **===**, si los objetos son exactamente iguales. 
Si quisiéramos clonar el objeto **persona** en **persona2** tendríamos que utilizar el operador **spread** u operador de propagación, muy utilizado en Javascript moderno.

Este operador se utiliza para expandir los elementos de un arreglo o los pares clave-valor de un objeto en un nuevo arreglo u objeto.

La sintaxis del operador de propagación consiste en tres puntos consecutivos **...** seguidos del nombre del arreglo u objeto que se va a expandir.

```js
const persona = {
  nombre: 'Juan Expósito',
  edad: 47,
}

const persona2 = {...persona}

console.log(persona === persona2)
// Salida:
// false
```
Para crear el objeto persona2 primero decimos que estamos creando un objeto, añadiendo las llaves **{ }** y después propagamos el objeto completo con el operador **spread**. De esta forma obtenemos un objeto *distinto* (otra zona de memoria) pero con el mismo contenido que el objeto inicial.

## Operador Optional Chaining

// Por hacer

## Operador Ternario

// Por hacer

## Arreglos en Javascript y operador Spread

// Por hacer

## Desestructuración de Objetos

// Por hacer

## Desestructuración de Arreglos

// Por hacer

## Método map de arreglos

// Por hacer

## Método find de arreglos

// Por hacer

## Método filter de arreglos

// Por hacer

## Importar módulos de Javascript

// Por hacer

## Exportar valores en Javascript

// Por hacer

##  Promesas

// Por hacer

## Consumir API REST con Fetch API

// Por hacer

## Async / Await

// Por hacer

## API DOM

// Por hacer

