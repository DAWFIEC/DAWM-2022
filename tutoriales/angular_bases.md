---
theme: jekyll-theme-leap-day
---

[Regresar](/DAWM-2022/)

Angular - Bases (Componentes y comunicación de una vía)
=======================================================


<p align="center">
  <img width="400" height="277" src="https://cms-assets.tutsplus.com/uploads/users/34/posts/22391/preview_image/angular-js-firebase.png">
</p>

Es un framework, en JavaScript, para crear aplicaciones web con html, css y typescript. Incorpora la combinación de plantillas, la inyección de dependencias, programación reactiva, directivas y más; mediante la aplicación buenas prácticas de programación. Las aplicaciones desarrolladas con Angular para la web, móvil o para escritorio.

Componentes
===========

* * *

Los componentes son las unidades básicas de una interfaz de usuario en una aplicación Angular. Estos componentes están asociados con una plantilla y un subconjunto de directivas.

![Componentes](https://www.simplilearn.com/ice9/free_resources_article_thumb/Components_Heirarchy-Angular_Components.PNG)

* Para crear un componente:

    + Desde la línea de comandos, en la ruta raíz del proyecto de Angular:
      ```
      ng g c <nombre del componente>
      ```

    + Se creará una carpeta con el nombre del componente, con los elementos: **.html**, **.css** y **.ts** (luego, Angular se encargará de convertir a **.js**).

    <p align="center">
      <img width="331" height="142" src="imagenes/angular_bases_componente.png">
    </p>
    
    + El mensaje de `update` indica que el componente creado está incluido en el arreglo de declaraciones del componente principal (`src/app.module.ts`).

* Para modificar (la vista) un componente:

    + Modifique las etiquetas html, en el archivo **.html** del componente.
    + Modifique el estilo de las etiquetas html con los selectores y propiedades css, en el archivo **.css** del componente.
    + Actualice el navegador o (re)inicie el servidor

* Para usar (renderizar) un componente dentro de otro componente:
    
    + Identifique el `selector` del componente hijo en el decorador de la clase:
      ```
      @Component({
          selector: 'app-cabecera',
          templateUrl: './cabecera.component.html',
          styleUrls: ['./cabecera.component.css']
      })
      export class CabeceraComponent {
      ```

    + Use el `selector` en el **.html** de cualquier otro componente
      ```
      <app-cabecera></app-cabecera>
      ``` 

    + Actualice el navegador o (re)inicie el servidor



Comunicación de una vía (one-way binding) 
=========================================

* * *

* En el **.ts** del componente

  + Agregue el atributo y su tipo dentro de la clase

    ```
    mensaje:string = "Este es un mensaje"
    ```
* En el **.html** del componente
  
  + Agregue las etiquetas HTML que sean necesarias y coloque como texto el atributo `mensaje` dentro de llaves dobles.
  
    `<div>` {% raw %} {{mensaje}} {% endraw %} `</div>`

* Actualice el navegador o (re)inicie el servidor
    


Referencias 
===========

* * *

* Angular. (2021). Retrieved 1 December 2021, from [https://angular.io/](https://angular.io/)
* Introduction to Angular Components and How to Implement It? (20202) https://www.simplilearn.com/tutorials/angular-tutorial/angular-components
* Guía de iniciación al data binding en Angular Qué es y cómo se utiliza. (2019). Retrieved 13 July 2022, from https://www.acontracorrientech.com/guia-practica-del-databinding-en-angular/