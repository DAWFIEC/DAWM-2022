---
theme: jekyll-theme-leap-day
---

## Guía 09

[Regresar](/DAWM-2022/)

### Contenidos

* Revisión de ejercicios previos: dudas y comentarios.
* Heroku es un [PaaS](https://www.ambit-bst.com/blog/definici%C3%B3n-de-iaas-paas-y-saas-en-qu%C3%A9-se-diferencian) enfocado en resolver el despliegue de una aplicación, permite manejar los servidores y sus configuraciones, escalamiento y la administración. Con Heroku solo deben indicar el lenguaje de backend estás utilizando o qué base de datos vas a utilizar, y solo debes ocuparte del desarrollo de tu aplicación.


### Actividades

* Previo a esta actividad, será necesario:
	+ Poseer una cuenta y un repositorio vacío/público en [Github](https://github.com/),
	+ Descargar e instalar [git](https://git-scm.com/downloads) en tu máquina local.
	+ Completar las actividades de la [guía 07](https://dawfiec.github.io/DAWM-2022/guias/guia07.html)  y [guía 08](https://dawfiec.github.io/DAWM-2022/guias/guia08.html).
	+ Tener una cuenta en [Heroku](https://www.heroku.com/).
	+ Descargar e instalar [heroku cli](https://devcenter.heroku.com/articles/heroku-cli#download-and-install) en tu máquina local.

* Git + Github

	+ En la línea de comandos, desde la ruta donde se encuentra la plantilla de un sitio básico:

		- Inicializa el repositorio localmente, con: ```git init .``` 
		- Agrega el URL de tu repositorio remoto, con:  ```git remote add origin https://github.com/repositorio-remoto.git```
		- Agrega todos los archivos al repositorio local, con: ```git add .```
		- Versiona todos los archivos con un comentario: ```git commit -m "mi primer comentario"```
		- Agrega la rama main a tu repositorio, con: ```git branch -M main```
		- Envía los cambios locales al repositorio remoto, en la rama main, con: ```git push -u origin main```

* Heroku

	+ Heroku permite manejar las aplicaciones desde la línea de comando o desde la interfaz web.

		- Obtén una cuentan en [Heroku](https://signup.heroku.com/login).
		- Descargar e instalar el [heroku-cli](https://devcenter.heroku.com/articles/heroku-cli#download-and-install).
		- Desde la línea de comandos en la ruta del sitio web, accede a Heroku, con: ```heroku login```

		Se le pedirá que presione cualquier tecla para ir a su navegador web y completar el inicio de sesión.
		![logindone.jpg](./imagenes/logindone.JPG)

		- Cree un proyecto, con: ```heroku create```

		![created-1](./imagenes/created-1.JPG)

		- Liste las rutas remotas. Verifique si aparece la ruta remota con heroku, use: ```git remote -v```

		![remoteurls](./imagenes/remoteurls.JPG)

		- **Opcional:** En caso que no aparezca la ruta remota para heroku. Agregue manualmente tu ruta con: ```git remote add heroku https://git.heroku.com/heroku-ruta.git```



* Buildpack

	+ Ahora, vamos a decirle a Heroku el ambiente de ejecución ([buildpacks](https://devcenter.heroku.com/articles/buildpacks)) de la aplicación. Heroku soporta ambientes de ejecución para Ruby, Python, Java, Clojure, Node.js, Scala, Go y PHP. 

		- Crea el archivo composer.json. Agregue como contenido al composer.json:

		```
		{}
		```

		- En este caso, el ambiente de ejecución será [PHP](https://devcenter.heroku.com/articles/buildpacks). Puede cambiar el paquete de compilación utilizado por una aplicación configurando el valor del paquete de compilación. La próxima vez que se envíe la aplicación, se usará el nuevo paquete de compilación.

		```heroku buildpacks:set heroku/php```

* Despliegue
	
	+ Desde la línea de comandos en la ruta del proyecto:

		- Agregue los cambios en `origin` y `heroku` con las instrucciones de *git*.

		```
		  git add .
		  git commit -m "composer.json"
		  git push origin main
		  git push heroku main
		```

		- Abra la aplicación, con: ```heroku open```


### Términos

`Paas`,`despliegue`

### Referencias

* Basic Git commands  Bitbucket Data Center and Server 7.18  Atlassian Documentation. (2021). Retrieved 14 November 2021, from https://confluence.atlassian.com/bitbucketserver/basic-git-commands-776639767.html 
* Git - Downloads. (2021). Retrieved 14 November 2021, from https://git-scm.com/downloads 
* Deploying PHP Apps on Heroku  Heroku Dev Center. (2021). Retrieved 14 November 2021, from https://devcenter.heroku.com/articles/deploying-php 
* Buildpacks |Heroku Dev Center. (2021). Retrieved 14 November 2021, from https://devcenter.heroku.com/articles/buildpacks

