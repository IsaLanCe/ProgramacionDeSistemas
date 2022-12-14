# PRACTICAS DE LA EE PROGRAMACION DE SISTEMAS
En este apartado estarán la diversas actividades analizadas y realizadas en el curso

## ENSAMBLADOR
### Historia
Para poder programar en Bajo nivel debemos conocer desde lo básico hasta lo mas complicado.
La primera computadora programable fue la ENIAC en 1946 pero se programaba mediante circuitos complejos que no eran nada funcionales. Después se empezó a utilizar el lenguaje maquina que son claves binaras que representan un CÓDIGO DE OPERACIÓN(OPCODE). Estas se almacenan en grupos de instrucciones llamados PROGRAMAS.

Esto llego a ser muy complicado debido a que se debían aprender series enormes de códigos binarios para realizar operaciones. Por ejemplo:
Para realizar la suma se tenia una instrucción binaria muy similar a "00101010010100101". Es por eso que se complicaba demasiado manejar este tipo de programación.

Actualmente manejamos lenguajes de Alto nivel que son relativamente sencillos a comparación con el lenguaje maquina. Pero no se llego al alto nivel desde el código binario, existe un lenguaje que nació para facilitar el binary code. Este se llama **"LENGUAJE ENSAMBLADOR"**.

![ENIAC](C:\Users\Landa Cervantes\Downloads\eniac2.jpg)
![The first computer Eniac!](/assets/Downloads/eniac2.jpg "Eniac")

### Traductor 
Un programa traductor lee un archivo en código fuente línea por línea, y escribe un archivo binario de instrucciones de maquina que realiza las acciones de computadora que el archivo de código fuente describe. Este archivo binario es llamado archivo de código objeto.

Un ensamblador es un tipo especial de compilador, también es un programa traductor que lee archivos en código fuente y proporciona como salida archivos en código objeto para ser ejecutados por el CPU. Sin embargo, un ensamblador es un traductor diseñado específicamente para traducir lo que llamamos lenguaje ensamblador en código objeto. Sin embargo tiene una característica muy importante que se pone aparte de los de los compiladores, y es: el control total sobre el código objeto. 

### Sintaxis
Nombre de la instrucción Operando 1, Operando 2, Operando 3, Operando 4, Operando N. 
El nombre de la instrucción está formada por 2 o 3 letras, los operandos pueden ser registros, constantes o direcciones de memoria. La cantidad de operandos dependerá de la instrucción.

*Por ejemplo:*

MOV AL, [1000]

Esta instrucción indica que se copie el valor de la porción de la memoria que esté en la ubicación 1000 (En hexadecimal) a la parte baja del registro AX (AL). Cuando un operando es un valor de una dirección de memoria, ésta dirección se escribe entre corchetes, recordar que el operando 1 es el destino y el operando 2 es el origen. Y cuando es una constante dependerá del ensamblador, en el caso del debug (Un programa que sirve para crear y editar aplicaciones que viene con el DOS) se interpretarán como hexadecimales, en los siguientes ejemplos se interpretará que las constantes son números hexadecimales.

### Lenguaje
Refleja directamente la arquitectura y las instrucciones en lenguaje de máquina de la CPU, y pueden ser muy diferentes de una arquitectura de CPU a otra.

Cada arquitectura de microprocesador tiene su propio lenguaje de máquina, y en consecuencia su propio lenguaje ensamblador ya que este se encuentra muy ligado a la estructura del hardware para el cual se programa. Los microprocesadores difieren en el tipo y número de operaciones que soportan; también pueden tener diferente cantidad de registros, y distinta representación de los tipos de datos en memoria. Aunque la mayoría de los microprocesadores son capaces de cumplir esencialmente las mismas funciones, la forma en que lo hacen difiere y los respectivos lenguajes ensamblador reflejan tal diferencia.

##### *PRACTICA*

El primer paso sera abrir un archivo de Notepad++ y copiar el contenido del archivo hola.asm y lo debemos de guardar con el tipo de *Asambly* y con el nombre que nosotros deseemos.
Cuando tengamos ese archivo en una carpeta, abrimos nuestra linea de comando e insertaremos la direccion donde se encuentra nuestro archivo ensamblador. Se pondra el comando: nasm -fwin32 con el nombre del archivo ensamblador.

Ejemplo: *nasm -fwin32 ./hola.asm* (al insertar la primera letra de nuestro archivo, podremos acompletarlo con la tecla TAB).

Al terminar este proceso se creara un archivo llamado del mismo nombre pero siendo de tipo *.obj*.
Teniendo nuestro archivo objeto, colocaremos el comando *gcc ./hola.obj -o "y colocamos el nombre que deseamos pero con extension ejecutable".

Ejemplo: *gcc ./hola.obj -o holaMundo.exe*

Con esto terminariamos el proceso de compilacion, desde un archivo ensamblador hasta tener un archivo ejecutable.



## CARGADORES


## LIGADORES
Es un programa que enlaza todos los programas o módulos obteniendo lo que denominamos programa ejecutable.

Es un programa que enlaza distintos módulos o programas que poseen subprogramas. Además incorporan las denominadas rutinas de librerías en caso de solicitarlas el propio programa.

La generación de un módulo ejecutable a partir de una colección de procedimientos traducidos independientemente requiere un ligador.

### Funcion
Los editores de ligado pueden efectuar varias funciones últimas a demás de la simple preparación de un programa objeto para su ejecución estos también se pueden utilizar para construir paquetes de subrutinas u otras secciones que suelen utilizar juntas. Esto puede ser útil al tratar con bibliotecas de subrutinas que manejan lenguajes de programación de alto nivel. Comparados con los cargadores de ligadores los editores de ligado en general tienden a ofrecer mayor flexibilidad y control con el correspondiente incremento e complejidad y sobrecarga.

## BIBLIOTECAS ESTATICAS
Una librería estática se carga al compilar el programa. Las funciones necesarias de esa librería se copian en tu ejecutable. Si te llevas el ejecutable de un ordenador a otro, el programa funcionará igualmente, aunque en el nuevo ordenador no esté la librería, ya que el ejecutable tiene su propia copia. El problema es que el ejecutable será más grande, ya que lleva copia de las funciones de la librería.

*PRACTICA*

En la seccion de readmi se encuentran los archivos que utilizaremos:

+ foo.h
+ foo.cpp
+ main.cpp

Crearemos una carpeta para guardar los archivos. Despues abriremos una pestaña de linea de comando en el cual enviaremos la direccion de nuestros archivos. Cuando tengamos eso, insertaremos el comando: *g++ -c foo.cpp*. Este generara un archivo con extension *.o* el cual es codigo objeto. 

Creamos la libreria estatica a partir del codigo objeto. Utilizamos el siguiente comando: *ar rcs libfoo.a foo.o*.

+ La r indica que se insertara objeto al archivo.
+ La c indica que se esta creando un archivo.
+ La s indica que se agrego un indice al aricho creado.
Por sintaxis de g++, el archivo creado debe de contener la palabra **lib**.

Ahora se ligara la biblioteca estatica con el programa principal: *g++ -c main.cpp*, el cual creara un archivo *main.o* en el que se estara convertido a codigo objeto.

Crearemos el archivo ejecutable a partir del codigo objeto. Utilizaremos el comando: *g++ -o main.exe main.o -L. -lfoo*. 
+ -L agrega el directorio actual a la ruta de busqueda del ligador.
+ -lfoo especifica el nombre de la biblioteca que va a ligarse.

Para finalizar la practica, solo compartiremos el archivo ejecutable con otro ordenador.


## BIBLIOTECAS DINAMICAS
Una librería dinámica se carga en el momento de la ejecución del programa, según las va necesitando. El ejecutable NO lleva copia de las funciones de la librería y necesita la librería para funcionar. Si te llevas el ejecutable a otro ordenador, debes llevarte también la librería o asegurarte que ya está allí. La ventaja es que el ejecutable suele ser más pequeño.

*PRACTICA*

En la seccion de readmi se encuentran los archivos que utilizaremos:

+ foo.h
+ foo.cpp
+ main.cpp

Se tiene que crear otra carpeta para guardar los archivos. Compilaremos la biblioteca utilizando el comando: *g++ -fPIC --shared -o foo.dll foo.cpp*.

El comando anterior compila *foo.cpp* como biblioteca compartida (-shared) con PIC (position independent code). El codigo objeto de la biblioteca se guarda en *foo.dll*.

Para explorar la biblioteca usamos el comando *nm foo.dll*. 

Para ligar la biblioteca compartida con el programa principal utilizamos el comando: *g++ -L. -lfoo -o main main.cpp*.

+ -L agrega el directorio actual a la ruta de busaqueda del ligador.
+ -lfoo especifica el nombre de la biblioteca que va a ligarse.

Para finalizar la practica, compartiremos el archivo ejecutable con otro ordenador.







