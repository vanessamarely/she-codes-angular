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



## Lo lograste 💪

{% hint style="success" %}
Has completado el **desafío \#1**, ahora vamos a el **desafío \#2 👇**
{% endhint %}

\*\*\*\*[**Aquí**](https://stackblitz.com/edit/greater-than?file=src%2Fapp%2Fapp.component.html) puedes encontrar el ejercicio resuelto.

