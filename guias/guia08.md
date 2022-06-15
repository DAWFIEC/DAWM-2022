---
theme: jekyll-theme-leap-day
---

## Guía 08

[Regresar](/DAWM-2022/)

### Contenidos

* Revisión de ejercicios previos: dudas y comentarios.
* [DOM](https://javascript.info/dom-nodes). El DOM y su uso a través de ejemplos de etiquetas, anidamientos, autocorrección e inspección por la consola del navegador con sus [propiedades y métodos](https://developer.mozilla.org/es/docs/Web/API/Document).
* [Objeto](https://javascript.info/dom-navigation). Este objeto te permite manipular el DOM de cualquier página web.
* [Eventos](https://javascript.info/events). Cada elemento dentro del navegador responde a un conjunto de señales disparadas en el DOM.
* [Asincronía](https://lemoncode.net/lemoncode-blog/2018/1/29/javascript-asincrono). En este sitio encontrarás una descripción completa de los patrones de asincronía que maneja JavaScript.
* [AJAX](https://www.espai.es/blog/2019/07/ajax-con-fetch-api/). La tecnología de requerimientos asincrónicos que maneja JavaScript permite hacer requerimientos a terceros sin que necesite recargar todo el contenido de la página. El [API-fetch](https://www.javascripttutorial.net/javascript-fetch-api/) tiene una explicación clara de la estructura para requerimientos de [JSON](https://codetogo.io/how-to-fetch-json-in-javascript/) y [XML](https://codetogo.io/how-to-fetch-xml-in-javascript/).


### Actividades

* Descargue y descomprima el archivo [rappo.zip](../ejercicios/rappo.zip).
* Agregue el archivo `js/ejercicio.js` y la referencia en el `index.html`.
* Evento [_DOMContentLoaded_](https://developer.mozilla.org/en-US/docs/Web/API/Window/DOMContentLoaded_event)
	+ Agregue el *listener* al evento *DOMContentLoaded* del document.
	+ Agregue la funcion flecha `cargarDatos` y un mensaje de alerta.
	+ Dentro del listener del document, agregue la llamada a la función `cargarDatos`.
* Dentro de la función flecha `cargarDatos`
	+ Realice una petición asincrónica con el objeto [fetch](https://www.javascripttutorial.net/javascript-fetch-api/) al url <a href="https://dataserverdaw.herokuapp.com/escritores/xml">Escritores</a>
	+ Procese la respuesta de texto como un objeto [XML](https://codetogo.io/how-to-fetch-xml-in-javascript/) 
		- Por cada etiqueta `<escritor>` cree un elemento `<option>`
		- Use el texto de la etiqueta `<nombre>` como valor de la etiqueta `<option>`
		- Use el texto de la etiqueta `<id>`  como valor del atributo `value`
		- Agregue la etiqueta `<option>` dentro de la etiqueta `<select>`
		- Compruebe los resultados en el navegador.
* Evento [_Change_](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/change_event)
	+ Agregue el *listener* al evento *change* de la etiqueta `<select>`
	+ 

### Términos

`eventos`, listener, `AJAX`, `asincrónico`

### Referencias

* 