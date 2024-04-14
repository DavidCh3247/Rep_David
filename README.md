[MÚSICA] Imagina esto. Un colega nos pide ayuda para arreglar
un script llamado "disk_usage.py". El objetivo del script es saber cuánto
espacio en disco se utiliza actualmente, e imprimir un error si hay muy poco
espacio para el funcionamiento normal. Pero el script no está funcionando
porque tiene algunos errores. Le ayudaremos a arreglar esos errores
para mostrar cómo usar "diff" y "patch". Antes de cambiar nada, hagamos un par de copias del script. Añadiremos "_original" a una copia,
que mantendremos sin modificar y usaremos para comparar, y "_fixed" a la copia que
usaremos para hacer nuestro arreglo. Bien, ahora que tenemos nuestras
copias, editaremos la versión "_fixed" para arreglarla realmente. Este archivo tiene un montón de código. Antes de que intentemos
entender lo que hace y lo que está mal, vamos a ejecutarlo y ver qué conseguimos. El intérprete de Python no está muy contento. Se queja de que hay un retorno fuera de la función. Y si miramos el código, podemos ver claramente que hay un retorno
que no está dentro de ninguna función. Podrías recordar que en Python, sólo podemos usar declaraciones de
retorno dentro de las funciones. Entonces, ¿cómo arreglamos esto? Hay un par de opciones. Podríamos convertir el código actual en una función y después llamar a esa función desde
la parte principal de nuestro script. O podríamos usar sys.exit para crear el número de retorno del código de salida de nuestro script, que es el código que hace que un programa
termine con el valor de salida adecuado. Por ahora, vamos con la segunda opción. Bien, hemos hecho el cambio. Vamos a ejecutar esta nueva versión de nuestro script. No, arreglamos el error de sintaxis, pero ahora el script nos dice que
no tenemos suficiente espacio en el disco. Pero sabemos que en realidad
tenemos algo de espacio libre, ¿verdad? ¿Qué pasa con eso? Si miras de cerca el código, podrás notar que el script está
convirtiendo a gigabytes dos veces. La llamada a la función "check_disk_usage"
pasa 2 veces 2 estrellas dobles 30. Recuerda que el operador estrella doble
se usa para calcular las potencias. En este caso, 2 a la potencia de 30,
que es el número de bytes en un gigabyte. Así que, esto sería 2 gigabytes, pero eso es si la función
"check_disk_usage" esperaba un valor en bytes. Si miramos el código de la función, podemos ver que ya dividiendo la cantidad de bytes
libres entre 2 a la potencia de 30. En otras palabras, estamos haciendo
la conversión a gigabytes dos veces. Una vez al llamar a la función y una vez dentro de la función. Tenemos que deshacernos de una de ellas. Cambiemos la forma en que llamamos a la función. Bien, probemos de nuevo. Ahora funciona. Bien, ahora tenemos que enviar el arreglo a nuestro colega, para que pueda arreglar su script. Para hacerlo, usaremos la técnica que acabamos de aprender
para generar un archivo "diff", como este. Revisemos el contenido del diferencial
usando el comando "cat". Fantástico. Esto parece tener lo que queremos. Esto es lo que necesitamos enviar a
nuestro colega para que arregle su archivo. ¿Cómo lo harían? Deben ejecutar el comando "patch" de esta manera. Llamando a "patch" con el archivo de diferencias, hemos aplicado los cambios que eran
necesarios para corregir los errores. Comprobemos que disk_usage.py se ejecuta ahora con éxito. ¡ÉXITO! Hemos visto cómo buscar diferencias
entre archivos, generar archivos "diff" para reunir nuestros cambios, y luego
aplicar esos cambios usando "patch". Pero esto es todavía un proceso muy manual, donde los sistemas de control de
versiones pueden realmente ayudar. Pero antes de que saltemos a eso,
en la siguiente hoja de trucos, encontrarás un resumen de
los comandos que acabamos de cubrir. Entonces revísalos, y luego vas al examen de práctica para
asegurarte de que entiendes todo esto.