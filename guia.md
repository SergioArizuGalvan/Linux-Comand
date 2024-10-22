Guia de Comandos Linux:
echo --> printar en pantalla
pwd --> Printar directorio actual
ls --> Printar contenido del directorio
cat nombre_archivo --> printar archivo por pantalla
cat > nombre_archivo --> Crear archivo vacio llamado "nombre_archivo"
tail -n nombre_archivo --> Printar las ultimas n lineas de un archivo
  Si se usa: +n --> printar des de la linea n

mkdir -p /dir1/dir2 --> Crear el/los directorio/s si todavia no existen.

cp archivo1 dir1 --> Copiar archivo a algun directorio
mv archivo1 dir1 --> Mover archivo a algun directorio

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



REDIRECCION DE SALIDA DE FICHERO

Si ">", el resultado se sobreescribe en el fichero. Si este NO EXISTE, se crea.
Si ">>", el resultado se añade al contenido del fichero. Si este NO existe, se crea.

Si "2>", si el comando da error, se sobreescribe el fichero con el error. Si este NO existe, se crea.
Si "2>>", si el comando da error, el resultado se añade al contenido del fichero. Si este no existe, se crea.

Si "&>", tanto si el comando se resuelve como si da error, se mandara al fichero siguiendo las normas previamente mencionadas.

Si "<", recibir la entrada de datos de otro lugar
Si "<<", los datos los recibe desde terminalk hasta llegar a la palabra de fin de coamndo.

Si "|", ejecución del 1r comando y lo concatena con el 2o comando.

*******************************************TEMA 2.2 ***********************************************************************
> [!NOTE]
> Caracteres:

comilla simple ' --> guarda tal cual el texto. NO interpreta caracteres
comillas dobles " --> guarda el texto interpretando caracteres
comillas inversas ` --> ejecutar comando entre `.

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

CONDICIONALES

if [condicion] ;
then
	...
else
	...
fi


los condicionales:
Para los numeros			No numéricos

-eq								=
-ne								!=
-lt								<
-gt								>
-le								<=
-ge								>=



case <variable> in
accion1)
	comandos accion1;;
accion2)
	comandos ...;
	comandos accion2;;
esac



while [conddicion]
do
	comandos
done

(until = hasta que)
until [condicion]
do
	comandos
done

for <variable> in <conjunto_valores>
do
	comandos
done



seq <empezar> <salto> <nºveces>
para usarlo en un for hay que ponerlo entre comillas inversas (`)





funciones****************************+

Funcion()
{
	....
}


Funcion (llamada a la funcion llamada Funcion)


Pasar valores a la funcion:
Funcion <valor1> <valor2>