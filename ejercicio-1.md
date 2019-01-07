---
description: "¡Ha llegado el momento de hacer algo más rimbombante! Construyamos un videojuego \uD83D\uDE4C"
---

# 2. ¿Cuál es mayor? 🙌

## Introducción 🧠 <a id="1-introduccion"></a>

Este desafío consiste en construir un juego en el que el usuario debe seleccionar el mayor entre dos números generados aleatoriamente: [**¡Aquí puedes encontrar el demo!**](https://angular-zvms6e.stackblitz.io)\*\*\*\*

¿Estás lista?

**Por supuesto que estás lista, desde el día en que naciste 😝**

## Paso 1: Crear el título ⭐️

Lo primero que haremos será construir los títulos y los botones. Para ello simplemente iremos al archivo **app.component.html** y empezaremos reemplazando su contenido con el siguiente código:

{% code-tabs %}
{% code-tabs-item title="app.component.html" %}
```markup
<h1>¿Cuál es mayor? 🙌</h1>
```
{% endcode-tabs-item %}
{% endcode-tabs %}

Deberías ver algo así: 👇

![En Stackblitz no tienes que refrescar el navegador, &#xE9;l autom&#xE1;ticamente te muestra los cambios &#x270C;&#xFE0F;](.gitbook/assets/image%20%287%29.png)

## Paso 2: Agregar los botones 💻

Ahora vamos agregar **los botones.** Para hacerlo vamos a usar la etiqueta **&lt;button&gt;**:

{% code-tabs %}
{% code-tabs-item title="app.component.html" %}
```markup
<h1>¿Cuál es mayor? 🙌</h1>
<button>7</button>
<button>9</button>
```
{% endcode-tabs-item %}
{% endcode-tabs %}

Deberías ver algo así: 👇

![](.gitbook/assets/image%20%282%29.png)

## Paso 3: Agregar el score 🏁

¡Esta es tu oportunidad de brillar! Ayúdanos agregando el título de **Score** utilzando la etiqueta **&lt;h2&gt;.** Cuando lo hagas, debería verse así: 👇

![](.gitbook/assets/image%20%288%29.png)

## Paso 4: Agregar los estilos 💅

Nuestra intefaz luce bien, pero podría lucir mejor 😏. Vamos a agregar un poco de **CSS** para darle color a nuestro videojuego. Reemplaza el contenido de **app.component.css** con éste:

{% code-tabs %}
{% code-tabs-item title="app.component.css" %}
```css
* {
  font-family: Lato;
}

button {
  background: hotpink;
  border: 3px solid black;
  border-radius: 4rem;
  font-size: 3rem;
  width: 5rem;
  box-shadow: 2px 2px 10px 0px gray;
  margin: 1rem;
  outline: none;
  cursor: pointer;
  transition: box-shadown 2s;
}

button:hover {
  background: #ff409f;
}

button:active {
  box-shadow: inset 2px 2px 10px 0px black;
}
```
{% endcode-tabs-item %}
{% endcode-tabs %}

Ahora nuestra aplicación debería verse mucho mejor: 👇

![](.gitbook/assets/image%20%283%29.png)

¡Ya casi terminamos! 👏

## Paso 5: Generar los números 📱

¡Ahora es momento de pasar a la lógica! Nosotros utilizaremos TypeScript, que es lo mismo que JavaScript sólo que mejorado 🤝.

Lo primero que haremos es que definiremos las variables que vamos a usar en el archivo **app.component.ts**:

{% code-tabs %}
{% code-tabs-item title="app.component.ts" %}
```typescript
export class AppComponent {
  leftNumber;
  rightNumber;
  score = '';  
}
```
{% endcode-tabs-item %}
{% endcode-tabs %}

El segundo paso es inicializar los números. Para ello debemos empezar creando una función que genere números de manera aleatoria. La llamaremos **generateRandomNumber\(\):**

{% code-tabs %}
{% code-tabs-item title="app.component.ts" %}
```typescript
export class AppComponent {
  leftNumber;
  rightNumber;
  score = '';
  
  generateRandomNumber() {
    const maxNumber = 10;
    const randomDecimal = Math.random() * maxNumber;
    const randomNumber = Math.round(randomDecimal);
    return randomNumber;
  }
}
```
{% endcode-tabs-item %}
{% endcode-tabs %}

Échale un ojo por un momento. Analiza su funcionamiento. Trata de inferir cómo funciona 👆.

Listo? 😀

{% hint style="info" %}
**Por si tienes alguna duda. Aquí te explicamos cómo funciona:**  
  
**1.** Primero definimos una variable llamada **maxNumber.** Ésta almacenará el número más alto que deseamos generar al azar. Puedes cambiarlo por **100** o **1000. 👍**

**2.** En segundo lugar generamos el número aleatorio utilizando la función **Math.random\(\).** Ésta es una función propia de JavaScript y lo que hace es devolvernos un valor aleatorio entre **0** y **1.** Al multiplicarlo por **10** estamos generando un número al azar entre **0** y **10**. 😉

**3.** El úlltimo paso es remover los decimales adicionales. Ya que de otro modo tendríamos números como **6.3** o **1.5.** Para sólo basta con utilizar la función **Math.round\(\)** que nos permite redondear números. ⭐️
{% endhint %}

El último paso para generar los números aleatorios es el más sencillo. Sólo basta con que los asignemos:

{% code-tabs %}
{% code-tabs-item title="app.component.ts" %}
```typescript
export class AppComponent {
  leftNumber;
  rightNumber;
  score = '';
  
  generateNumbers() {
    this.leftNumber = this.generateRandomNumber();
    this.rightNumber = this.generateRandomNumber();
  }
  
  generateRandomNumber() {
    const maxNumber = 10;
    const randomDecimal = Math.random() * maxNumber;
    const randomNumber = Math.round(randomDecimal);
    return randomNumber;
  }
}
```
{% endcode-tabs-item %}
{% endcode-tabs %}

Como habrás notado simplemente creamos la función **generateNumbers\(\)** que se encarga de llamar la función que creamos y para cada número. 👍

Para ver el código funcionando simplemente debemos asegurarnos de llamar a la función que acabamos de crear. Para ello podemos usar el constructor:

{% code-tabs %}
{% code-tabs-item title="app.component.ts" %}
```typescript
export class AppComponent {
  leftNumber;
  rightNumber;
  score = '';
  
  constructor() {
    this.generateNumbers();
  }
  
  generateNumbers() {
    this.leftNumber = this.generateRandomNumber();
    this.rightNumber = this.generateRandomNumber();
  }
  
  generateRandomNumber() {
    const maxNumber = 10;
    const randomDecimal = Math.random() * maxNumber;
    const randomNumber = Math.round(randomDecimal);
    return randomNumber;
  }
}
```
{% endcode-tabs-item %}
{% endcode-tabs %}

¡Eso es todo! ¡Cada vez que recargues el navegador verás números generados de manera aleatoria! 🎉

## Paso 6: No repetir números 🖐

¡Parece ser que en algunas ocasiones los números se repiten! Debemos evitar esto \(porque de otro modo no podríamos jugar el juego 😝\).

Cuando ambos números generados aleatoriamente sean iguales vamos a buscar otros números aleatorios 👇

{% code-tabs %}
{% code-tabs-item title="app.component.ts" %}
```typescript
...
generateNumbers() {
  this.leftNumber = this.generateRandomNumber();
  this.rightNumber = this.generateRandomNumber();
  if (this.leftNumber === this.rightNumber) {
      this.generateNumbers();
  }
}
...
```
{% endcode-tabs-item %}
{% endcode-tabs %}

Fácil verdad? 😊



## Lo lograste 💪

{% hint style="success" %}
Has completado el **desafío \#1**, ahora vamos a el **desafío \#2 👇**
{% endhint %}

\*\*\*\*[**Aquí**](https://stackblitz.com/edit/greater-than?file=src%2Fapp%2Fapp.component.html) puedes encontrar el ejercicio resuelto.

