---
theme: jekyll-theme-leap-day
---

[Regresar](/DAWM-2022/)

Angular - Servicios
===================

<p align="center">
  <img width="330" height="150" src="imagenes/injector-injects.png">
</p>

Los componentes NO deben obtener o guardar datos directamente y no deben presentar datos falsos. Los componentes deben centrarse en presentar datos y delegar el acceso a los datos a un servicio.

Un servicio es un proveedor de datos, que mantiene lógica de acceso a ellos. Los servicios serán consumidos por los componentes, que delegarán en ellos la responsabilidad de acceder a la información y la realización de operaciones con los datos.

Servicio
========

Desde la raíz del proyecto con Angular

* Acceda desde la línea de comandos
* Cree el servicio **titular**, con: `ng generate service servicios/titular`
  + Se creará carpeta *servicios*, y 
  + Se crearán los archivos `titular.service.ts` y `titular.service.spec.ts`
  	
  <pre><code>
    import { Injectable } from '@angular/core';

	@Injectable({
	  providedIn: 'root'
	})
	export class TitularService {

	  constructor() { }
	}
  </code></pre>

  + Agregue la función `obtenerNombreSitio` que retorna un objeto JSON.

	<pre><code>
	  ...
	  constructor() { }

	  <b style="color:red">obtenerNombreSitio() {
	    let objeto = { cabecera: 'Album fotográfico' }
      return objeto
	  }</b>
	}
  </code></pre>


Inyección de dependencias
=========================

Las dependencias son servicios u objetos que una clase necesita para realizar su función. La [inyección de dependencia (DI)](https://docs.angular.lat/guide/architecture-services#inyecci%C3%B3n-de-dependencia-id) es un patrón de diseño en el que una clase solicita dependencias de fuentes externas en lugar de crearlas, para aumentar la flexibilidad y modularidad en sus aplicaciones. Angular proporciona dependencias a una clase en la creación de instancias.

Para inyectar una dependencia en un componente solo debes agregar un argumento (con el tipo de la dependencia) en el método constructor de la clase.

* En **app.component.ts**
	+ Agregue el _import_ al servicio
	+ Agregue el método _constructor_ de la clase
	+ Inyecte la dependencia como argumento en el constructor

  <pre><code>
    import { Component } from '@angular/core';
	<b>import { TitularService } from './servicios/titular.service';</b>

	@Component({
	  selector: 'app-root',
	  templateUrl: './app.component.html',
	  styleUrls: ['./app.component.css']
	})
	export class AppComponent {
	  title  = 'testAngular';

	  <b style="color:red">constructor(private titularService: TitularService) {}</b>
	}
  </code></pre>

  + Modifique el constructor para invocar la función `obtenerDatos()` del servicio

  <pre><code>
  	...
	  <b style="color:red">constructor(private titularService: TitularService) {
	      let objeto = titularService.obtenerNombreSitio()
	      this.title = objeto.cabecera
	  }</b>
	}
  </code></pre>

* A manera de prueba, interpole el atributo `title` en el **html** para ver los resultados

  ```
    <div>
    {% raw %} {{title}} {% endraw %} 
    </div>
  ```

* Actualice el navegador o (re)inicie el servidor
* El resultado en el navegador debería lucir algo similar

<p align="center">
  <img src="imagenes/angular_servicios_output.png">
</p>

Peticiones HTTP
===============

Las aplicaciones en el front-end necesitan comunicarse con un servidor a través del protocolo HTTP, para descargar o cargar datos y acceder a otros servicios back-end. Angular proporciona una API HTTP de cliente para aplicaciones Angular, la clase de servicio `HttpClient` en `@angular/common/http`.

* En **servicios/fotos.component.ts**, 
	+ Importe el módulo `HttpClient`
	+ Agregue el servicio `HttpClient` como inyección de dependencia en el método constructor.
	
	<pre><code>
	import { Injectable } from '@angular/core';
	<b style="color:red">import { HttpClient } from '@angular/common/http';</b>
	
  	
	@Injectable({
	  providedIn: 'root'
	})
	export class FotosService {

	  <b style="color:red">constructor(private http: HttpClient) { }</b>

	  ...
	}
	</code></pre>



Referencias 
===========

* * *

* Angular. (2022). Retrieved 18 July 2022, from https://angular.io/tutorial/toh-pt4
* Servicios en Angular. (2022). Retrieved 18 July 2022, from https://desarrolloweb.com/articulos/servicios-angular.html
* Angular. (2022). Retrieved 19 July 2022, from https://angular.io/guide/dependency-injection
* Inyección de dependencias. (2022). Retrieved 19 July 2022, from https://desarrolloweb.com/articulos/patron-diseno-contenedor-dependencias.html
* Angular. (2022). Retrieved 19 July 2022, from https://angular.io/guide/http