# TEMA 3: GIT
## GIT

# como configurar git
>[!note]
>Neceitamos un usuario y un email

git config --global user.name "Sariz"
git config --global user.email "email"

git init --> Iniciar git en el directoriodes de el que lo ejecutamos
>[!note]
>Hay que estar en el directorio que queremos GIT

git status --> ver estado del proyecto

git add <nombrefichero> --> Añadir fichero a git
git add . --> Añadir todo

git commit --> Instantania de guardado
>[!note]
>Se abrira un Vin par añadir el comentario

git commit -m "Mensaje" 
>[!Note]
> -m hace que podamos escribir directamente el mensaje

git log --> ver las instantaneas 

Estamos editando y no queremos guardar instantanea

git checkout <nombre-archivo>--> Para situarnos en la instantanea antes de editar

git reset --> ver última instancia y si hay modificaciones no guardadas

git log --graph --> ver el log como ramas

>[!Note]
>Para comandos muy repetidos podemos crear un alias

git config --global alias.<nombrealias> "<comando sin el git>"

git dif --> ver las diferencias de la última instantanea a la actual (sin instancia actual)


### MOVERSE ENTRE INSTANCIAS:

git checkout <hash_instantanea>
>[!Note]
>Revisar
git checkout HEAD --> Mueve el "puntero" HEAD a la ubicacion actual

git reset --hard <ID_instantania> --> Eliminar instantanea des de ID_instanta, esta NO se elimina

git reflog --> Ver todos los logs. Es decir, es el historial completo, donde NADA se elimina.
>[!Note]
>Si quisieramos recuperar una instantanea eliminada, hariamos otro hard reset pero con el ID de la que queramos recuperar

git tag "<nombre_tag>" --> poner etiquetas a las instantaneas

git tag --> listar tags

gti checkout tag/<nombre_tag> --> moverse a una instantanea de un tag

git branch <nombre_rama> --> Crear rama llamada nombre_rama

git branch -d <nombre-rama> --> Eliminar rama

git swith <nombre_rama> --> para moverme a la rama nombre_rama 

>[!Note]
>Para moverse con switch las instantaneas deben estar descargadas (checkout lñas descarga y te mueve)

git merge <rama_comprobar> --> Combinar rama_comprobar y mi rama en mi rama de trabajo actual 
>[!Note]
>Rama_comprobar no sufrirá cambios

>[!Note]
> Si hay conflicto (el conflicto es si hay modificaciones en las mismas lineas de un mismio archivo, no hay conflicto si se modifica un mismo archivo en distintas lineas), se mostrará las diferencias entre ramas



## GITHUB
