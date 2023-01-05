#  Comandos de Git y Github

### ¿Que es Git?

**GIT ES UN SISTEMA DE CONTROL DE VERSIONES**

Sirve para controlar las versiones de los programas, gracias a ello podras navegar a cualquier de tu programa y tener tu codigo a salvo.

------------


### comandos esenciales para Git

 	 Git Add  " Name Archivo" 
 Este comando sirve para agregar al area de desarollo de Git el proyecto en el que trabajas

	Git config -- global user user."email"    
	Git Git config -- global user user."name" 
esto configura tu Git para que reconosca quien eres

	 git commit - m "comentario"
 Esto toma una copia de tu proyecto y lo guarda para que puedas tenerlo como una version del proyecto como tal .
 
 	 git log 

Sirve para ver todo los commit que han echo te muetsra hora, fecha, quienhizo el commit y el comentario.

	 git checkout  -- "nombre del archivo"

sirve para regresar a los cambios del ultimo commit que has echo ej:  se borro una parte del code o hiciste algo que no te gusta puedes regresar.

	 git diff

Sirve pára ver las diferencias que tiene el codigo que has modificado y el ultimo commit que has realizado, te muestra que es lo que tenias antes y lo actualizado.

	git branch

Te muestra en la rama donde estas guardado el codigo.

	  git branch "nombre de rama"

Este comando sirve para crear una nueva rama para ser trabajada alli

	 git checkout "nombre de la rama "

Con este comando acedes a la rama creada para trabajar alli.

------------
#### Que es una rama?

Es donde esta hubicado el proyecto, nosotros como desarolladores podemos crear varias ramas para hacer cambios en un proyecto paralelo sin afectar lo que esta en otra rama.

------------

	.Gitignore

Es un archivo donde puedes escribir los nombres de archivos o carpetas de tu proyecto que quieres que no se te suban en un repositorio.
