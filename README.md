![Alt text](https://techdevised.files.wordpress.com/2021/01/javascript.png "a title")


 # Notas sobre Javascript moderno



**Índice**  
1. [Introducción](#id1)
2. [Template String](#id2)
3. [Funciones](#id3)
3. [Funciones de flecha](#id4)



## Introducción


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
