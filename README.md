<div align="center"> 
  <h1> JavaScript Profesional </h1>
</div>

## Contenido
- [Cómo llega un Script al navegador](#Como-llega-un-Script-al-navegador)
- [Scope](#Scope)
- [Closures](#Closures)


## Cómo llega un Script al navegador

El **DOM** es la representación que hace el navegador de un documento HTML.

El navegador interpreta el HTML transformandolo en el DOM, cuando este proceso termina 
se dispara el evento **DOMContentLoad**, esto significa que todo el documento esta
disponible para ser manipulado.

Todo el Script que carga una página  tiene un llamado y una ejecución. Tanto con async
como defer podemos hacer llamados asincronos, pero tiene ciertas diferencias:

- **async**: Con async podemos hacer llamadas asincronas y no detenemos la carga del DOM 
hasta que se haga la ejecución del código.
- **defer**: Este hace peticiones igual de asincronas que async, pero difiere en que este
ejecuta el código JavaScript hasta que termina la carga del documento.

**NOTA**: Es importante tener en cuenta que cuando carga una página y se encuentra un script a ejecutar toda la carga se detiene. Por eso se recomienda agregar tus scripts justo antes de cerrar el body para que todo el documento esté disponible.

## Scope

Es el alcance de las variables, es desde donde estan disponibles las variables en el proyecto;
o en otras palabras: es el tiempo de vida de una variable. Existen 4 diferentes scopes:

**Global Scope**
Variables disponobles de forma global, se utiliza la palabra recervada `var` para declarar dichas variables,
estas son accesibles por TODOS los scripts que se cargan en la página, por lo cual se corre el riesgo de sobreescribirla.

**Function Scope**
Variables declaradas dentro de una función y son solo visibles dentro de ella misma (esto incluye los argumentos que se pasen a la función).

**Block Scope**
Variables definidas dentro de un bloque, se utilizan las palabras recervadas `let` (para variables que cambiaran de valor) y `const` (para variables que su valor sera siempre el mismo). Un ejemplo del uso de Block Scope es cuando declaramos una variable dentro de un siclo while o for, o bien dentro de un if o una función.

**Module Scope**
Las variables son limitadas al archivo en el que están declaradas, esto se especifica en el script al indicarle que es un modulo `type="module"`


## Closures

Son funciones que regresan una función o un objeto con funciones que mantienen las variables que fueron declaradas fuera de su scope.

Los closures sirven para tener algo parecido a las variables privadas. Es decir encapsula variables que no pueden ser modificadas directamente por otros objetos, sólo por funciones.

#### `Ejemplo Scope Global`

```javascript
let color = 'red'

function printColor () {
  console.log(color)
}

```