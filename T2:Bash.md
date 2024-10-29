# Tema 2: Bash

echo --> printar en pantalla

pwd --> Printar directorio actual

ls --> Printar contenido del directorio

cat nombre_archivo --> printar archivo por pantalla
> [!NOTE]
>cat > nombre_archivo --> Crear archivo vacio llamado "nombre_archivo"

tail -n nombre_archivo --> Printar las ultimas n lineas de un archivo
> [!NOTE]
> Si se usa: +n --> printar des de la linea n

mkdir -p /dir1/dir2 --> Crear el/los directorio/s si todavia no existen.

cp archivo1 dir1 --> Copiar archivo a algun directorio

mv archivo1 dir1 --> Mover archivo a algun directorio
> [!NOTE]
> Tambien sirve para renombrar ficheros

ln -s ruta_archivo ruta_enlace --> Crear enlace simbolico (symlink)

rm <opcion> directorio/fichero_eliminar --> eliminar
  <opcion>
   |-> -f --> forzar borrado
   |-> -i --> Confirmar cada proceso de borrado
   |-> -r --> Eliminar tanto carpeta como contenidos
      (pueden combinarse)

*********Extra*******
si usamos * con rm, se eliminara todo con escepcion de lo que empiece con un punto (.). Si queremos eliminar estos archivos tambien, usamos .*
*************************

grep "palabra_buscar" nombre_archivo --> Para ver solo las lineas que contienen la "palabra_buscar" en el archivo "nombre_Archivo"

# Clase

pwd
ls
cd
echo
 --> \n --> Salto línia
 --> \c --> Mantener cursor en línia
 --> \b --> 
 --> \n --> 
# Directorios
mkdir --> crear directorio

rmdir --> borrar directorio

gedit (no instalado en parrot) = nano
gedit aaa.txt& (&-->ejecucion en backgroung permite seguir usando terminal sin cerrar ventana) 

##CARACTERES COMODÍN
```
* --> cualquier cosa
? --> cualquier cosa 1 caracter
[a,b,c] --> cualquier caracter entre a,b y c
[a-c] --> cualquier caracter entre los valores (a y c).
```
cp origen destino --> copiar de origen a destino
mv --> mover/renombrar archivo
rm --> eliminar fichero
cat --> printar fichero seguido
more --> printar fichero paginado


##PERMISOS
Primer caracter:
	- --> ficehro
	d --> directorio
	b,c --> especiales
	2-4 caracteres (u) = propietario
	5-7 caracteres (g)= grupo del propietario
	8-10 caracteres (o)= otros usuarios
	todos (a)
	
	significado letras:
		w --> write - escribir
		r --> read - leer
		x --> execution - ejecucion 

chmod [ugo/a] [+-] [rwx]--> cambiar permisos

Permisos se pueden dar en binario (normalmente se proporcionan así)
744 --> normalmente (rwx r-- r--)
777--> fichero sin problemas de permisos para nadie


head [-n] --> mostrar primeras líneas de un fichero (por defecto las 10 primeras, con n muestras un numero definido)
tail [-n] --> mostrar ultimas líneas de un fichero (por def 10)
tail [+n] --> desde la línia establecida hasta el final
grep [-v] "palabra_buscar" fichero --> buscar cosas en un fichero. Si se usa -v, se muestra todo menos palabra_buscada
	-. --> cualquier caracter diferente de final de linea
	-[abc] --> letra a, b o c
	-[^abc] --> letra diferente a a, b y c
	-[a-z] --> 
	-^ --> desde principio de linea
	-$ --> final de linea
	-* --> 0 o mas repeticiones del caracter anterior
	-^$ --> lineas vacias
paste [-d] fichero1 fichero2 --> concadenar ficheros de forma horizontal. Si se usa -d, se mustra el caracter posterior a -d entre las lineas de los ficheros.

sort [-k2] [-t<caracter>] --> mostrar por terminal el fichero de forma ordenada [A-Z]. Si se usa -kn, donde n es un número, se ordena por el campo n. (los campos se cuentan por espacios en blanco). SI se usa -t seguido de un caracter, en vez de usar los espacios en blanco se usara ekl caracter establecido.

cut [-d<caracter>] [-f2] --> mostrar por terminal campos de un fichero

wc --> contar cosas de un fichero.(lineas, palabras, caracteres, nombre fichero)

# REDIRECCION DE SALIDA DE FICHERO

Si "__>__" , el resultado se sobreescribe en el fichero. Si este NO EXISTE, se crea.

Si "__>>__" , el resultado se añade al contenido del fichero. Si este NO existe, se crea.

Si "__2>__" , si el comando da error, se sobreescribe el fichero con el error. Si este NO existe, se crea.

Si "__2>>__" , si el comando da error, el resultado se añade al contenido del fichero. Si este no existe, se crea.

Si "__&>__" , tanto si el comando se resuelve como si da error, se mandara al fichero siguiendo las normas previamente mencionadas.

Si "__<__" , recibir la entrada de datos de otro lugar.

Si "__<<__" , los datos los recibe desde terminalk hasta llegar a la palabra de fin de coamndo.

Si "__|__" , ejecución del 1r comando y lo concatena con el 2o comando.

*******************************************TEMA 2.2 ***********************************************************************
## Caracteres:

comilla simple ' --> guarda tal cual el texto. NO interpreta caracteres

comillas dobles " --> guarda el texto interpretando caracteres

comillas inversas ` --> ejecutar comando entre las comillas inversas.

Bash se guardan como nombre.sh

llamar a ejecucion un script:

bash nombre.sh

./nombre.sh


OPERACIONES CON NUMEROS ENTEROS

let <operacion>

Operaciones con decimales

bc <<< operacion

Operaciones guardadas en variables

resultado=$((<operacion>))


## CONDICIONALES

### IF
```
if [condicion] ;

then
	...
else
	...
fi
```

los condicionales:
| Para los numeros | No numéricos |
| :---: | :---: |
| -eq |	= |
| -ne | != |
| -lt | < |
| -gt | > |
| -le | <= |
| -ge |	>= |

### Switch
```
case <variable> in
accion1)
	comandos accion1;;
accion2)
	comandos ...;
	comandos accion2;;
esac
```

### While
```
while [condicion]
do
	comandos
done
```
### Until
```
(until = hasta que)
until [condicion]
do
	comandos
done
```
### For
```
for <variable> in <conjunto_valores>
do
	comandos
done
```


seq <empezar> <salto> <nºveces>
> [!NOTE]
> Para usarlo en un for hay que ponerlo entre comillas inversas (`)


## Funciones****************************+
```
Funcion()
{
	....
}
```
> [!NOTE]
> Para llamar a una funcion se usa el comando:
> Nombre_funcion

Funcion (llamada a la funcion llamada Funcion)


Pasar valores a la funcion:

Funcion <valor1> <valor2>
