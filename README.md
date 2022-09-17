# PRACTICAS DE LA EE PROGRAMACION DE SISTEMAS
En este apartado estarán la diversas actividades analizadas y realizadas en el curso

## ENSAMBLADOR
### Historia
Para poder programar en Bajo nivel debemos conocer desde lo básico hasta lo mas complicado.
La primera computadora programable fue la ENIAC en 1946 pero se programaba mediante circuitos complejos que no eran nada funcionales. Después se empezó a utilizar el lenguaje maquina que son claves binaras que representan un CÓDIGO DE OPERACIÓN(OPCODE). Estas se almacenan en grupos de instrucciones llamados PROGRAMAS.

Esto llego a ser muy complicado debido a que se debían aprender series enormes de códigos binarios para realizar operaciones. Por ejemplo:
Para realizar la suma se tenia una instrucción binaria muy similar a "00101010010100101". Es por eso que se complicaba demasiado manejar este tipo de programación.

Actualmente manejamos lenguajes de Alto nivel que son relativamente sencillos a comparación con el lenguaje maquina. Pero no se llego al alto nivel desde el código binario, existe un lenguaje que nació para facilitar el binary code. Este se llama **"LENGUAJE ENSAMBLADOR"**.

### Sintaxis
Nombre de la instrucción Operando 1, Operando 2, Operando 3, Operando 4, Operando N. 
El nombre de la instrucción está formada por 2 o 3 letras, los operandos pueden ser registros, constantes o direcciones de memoria. La cantidad de operandos dependerá de la instrucción.

*Por ejemplo:*

MOV AL, [1000]

Esta instrucción indica que se copie el valor de la porción de la memoria que esté en la ubicación 1000 (En hexadecimal) a la parte baja del registro AX (AL). Cuando un operando es un valor de una dirección de memoria, ésta dirección se escribe entre corchetes, recordar que el operando 1 es el destino y el operando 2 es el origen. Y cuando es una constante dependerá del ensamblador, en el caso del debug (Un programa que sirve para crear y editar aplicaciones que viene con el DOS) se interpretarán como hexadecimales, en los siguientes ejemplos se interpretará que las constantes son números hexadecimales.

### LENGUAJE
Refleja directamente la arquitectura y las instrucciones en lenguaje de máquina de la CPU, y pueden ser muy diferentes de una arquitectura de CPU a otra.

Cada arquitectura de microprocesador tiene su propio lenguaje de máquina, y en consecuencia su propio lenguaje ensamblador ya que este se encuentra muy ligado a la estructura del hardware para el cual se programa. Los microprocesadores difieren en el tipo y número de operaciones que soportan; también pueden tener diferente cantidad de registros, y distinta representación de los tipos de datos en memoria. Aunque la mayoría de los microprocesadores son capaces de cumplir esencialmente las mismas funciones, la forma en que lo hacen difiere y los respectivos lenguajes ensamblador reflejan tal diferencia.

##### *PRACTICA 1*


## CARGADORES


## LIGADORES


## BIBLIOTECAS ESTATICAS


## BIBLIOTECAS DINAMICAS
