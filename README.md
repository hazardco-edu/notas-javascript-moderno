![Alt text](https://techdevised.files.wordpress.com/2021/01/javascript.png "a title")


 # Notas sobre Javascript moderno



**Índice**  
1. [Introducción](#id1)
2. [Template String](#id2)
3. [Funciones](#id3)
4. [Funciones anónimas](#id4)


<div id='id1'/>

## Introducción<a name="id1"></a>

<div id='id2'/>

## Template String

Las **template string** son una característica que permite formatear cadenas de texto de forma muy flexible. Para ello se utilizan backticks(`) en lugar de comillas dobles o comillas simples. En español se traduce este término como *acento grave inverso*.

Una **template string** puede contener expresiones contenidas dentro del marcador de posición, o *placeholder*, **${}**, que serán evaluadas e integradas dentro del texto. Esto hace muy sencillo concatenar cadenas de caracteres sin utilizar el operador **+**. 


```js
const nombre = "Juan Expósito"
const edad = "47"

const mensaje = `Mi nombre es ${nombre} y mi edad es ${edad}`

console.log(mensaje)

// La forma tradicional de hacerlo es la siguiente

const mensaje = "Mi nombre es " + nombre + " y mi edad es " + edad

console.log(mensaje)

```

En el ejemplo, las constantes **nombre** y **edad** se insertan en el texto a través de los *placeholders* que están dentro de los *backtips*.

**Template string** soporta múltiples líneas para que el texto sea lo más legible posible. Al final de cada línea se añade un salto de línea automáticamente.



```js
const nombre = "Juan Expósito"
const edad = "47"

const mensaje = `Mi nombre es ${nombre} 
                y mi edad es ${edad}`

console.log(mensaje)

// Salida:
// Mi nombre es Juan Expósito
// y mi edad 47

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