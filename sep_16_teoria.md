**1. El conjunto de todos los atributos de un
sistema que son visibles para el programador
y son necesarios para programar en lenguaje
máquina se denomina:**
+ **arquitectura del computador**
+ conjunto de componentes físicos del
computador
+ organización del computador
+ repertorio de instrucciones máquina

**2. ¿Cuál de las siguientes afirmaciones es
cierta?**
+ la arquitectura Von Neumann de los
computadores tradicionales consiste en
tener almacenados los datos separados de
las instrucciones en memorias distintas
+ **el registro de estado (flags) es un registro de
propósito específico cuyo contenido puede
ser visto directa o indirectamente por el
usuario mediante el uso de ciertas
instrucciones específicas**
+ la unidad de control necesita como entrada
el registro contador de programa para saber
cuál es la instrucción que debe ejecutar a
continuación
+ el registro de direcciones de memoria es un
registro de propósito general que puede
contener tanto direcciones como datos

**3. En una máquina little-endian con memoria
de bytes y representación en complemento a
dos que permite accesos a memoria de
tamaño byte (1 B), media palabra (2 B) y
palabra (4 B), se almacenan a partir de la
posición 0xCAFEBAB0 cuatro palabras con
valores -1, -2, -3, -4. ¿Qué se obtendría al consultar la media palabra de la posición
0xCAFEBABE?**
+ **-1**
+ -4
+ no se puede saber, faltan datos
+ ninguna de las anteriores

**4. Se pretende almacenar una palabra de 4 B en
una memoria de bytes a partir de una
dirección determinada. ¿Cuál de las
siguientes es válida, si la palabra debe
quedar alineada?**
+ **0xFACEB00C**
+ 0xDEADBEEF
+ 0xCAFEBABE
+ 0xABADF00D

>Porque acaba en C, que en decimal es 12, múltiplo de 4.

**5. En una arquitectura de acumulador, la
instrucción LOAD X:**

+ transfiere el contenido del registro X a la
memoria
+ suma M(X) al acumulador
+ transfiere el contenido del acumulador a la
posición de memoria X
+ **transfiere el contenido de la posición de
memoria X al acumulador**

**6. Una instrucción máquina del tipo "Add
M,R" podría formar parte del repertorio de:**
+ una máquina pila
+ una máquina de acumulador
+ una máquina con arquitectura R/R
+ **una máquina con arquitectura M/M**

**7. ¿Cuál de los siguientes no es un modo de
direccionamiento IA-32?**
+ Registro
+ Memoria
+ **Cache**
+ Inmediato

**8. Un bus se compone de:**
+ líneas de datos y líneas de dirección
+ líneas de alimentación
+ líneas de estado y líneas de control
+ **líneas de control/estado, líneas de dirección
y líneas de datos**

**9. ¿Cuál de los siguientes no es un tipo de bus?**
+ **Secuencial**
+ Paralelo
+ E/S
+ Sistema

**10. Si en un bus de direcciones de 32 bits se
decodifica parcialmente la dirección de un
dispositivo de 32 posiciones usando 22 bits,
¿cuántas veces aparecerá repetido en el
mapa de memoria?**
+ 10
+ 16
+ **32**
+ 1024

**11. Para obtener una única velocidad
comparativa final, el benchmark SPEC CPU
combina las velocidades de ejecución de una
serie de tests, respecto a un ordenador de
referencia, usando la media...**
+ aritmética
+ **geométrica**
+ armónica
+ ponderada

**12. El primer computador electrónico basaba su
funcionamiento en:**
+ **tubos de vacío**
+ circuitos integrados LSI
+ amplificadores operacionales
+ núcleos de ferrita

**13. En Linux IA-32, si gcc usa la instrucción
leave se puede asegurar que en ese punto del
programa:**
+ correspondería emitir la secuencia de salida
pop/ret, pero leave hace lo mismo y ocupa
menos espacio
+ **ya no hay registros salva-invocado que
recuperar**
+ ya no hay variables locales que destruir
+ ya no se hacen llamadas anidadas y por
tanto no hay parámetros que ocupen espacio
en pila

**14. Usando el repertorio IA-32, para
intercambiar el valor de 2 variables (por
ejemplo A: .int 1 y B: .int 2) se pueden usar...**
+ dos instrucciones mov
+ una instrucción mov y una instrucción lea
+ 3 mov, no menos (se le llama "intercambio
circular")
+ **4 mov, no menos (debido a la arquitectura
R/M)**

**15. Respecto a registros base e índice en IA-32,
la excepción es que:**
+ EBP no puede ser registro base
+ EBP no puede ser registro índice
+ ESP no puede ser registro base
+ **ESP no puede ser registro índice**

**16. El registro SP / ESP / RSP...**
+ es un registro transparente al usuario y
contiene la instrucción que se está
ejecutando
+ **es un registro de propósito específico y
contiene la dirección de la cima de la pila**
+ es un registro transparente al usuario y
contiene la dirección de memoria a la que
se está accediendo
+ es un registro de propósito específico y
contiene la dirección de la siguiente
instrucción a ejecutar

**17. Diferencias gcc Linux IA-32/x86-64: marcar
la respuesta falsa**
+ los enteros largos (long) pasan de 32 a 64
bits
+ los punteros (void*) pasan de 32 a 64 bits
+ **el tipo double pasa de 4 B a 8 B**
+ long double pasa de 10/12 B a 16 B

**19. Si A y B son dos enteros almacenados
respectivamente en %eax y %ebx, ¿cuál de
las siguientes implementaciones de
if (!A && !B) {...then part...}
es incorrecta?**
a.
~~~
or
%ebx, %eax
jne not_true
...then part...
not_true:
...
~~~

b.
~~~
cmp $0, %eax
jne not_true
cmp $0, %ebx
jne not_true
...then part...
not_true:
...
~~~

**c.**
~~~
test %ebx, %eax
jne not_true
...then part...
not_true:
...
~~~

d.
~~~
test %eax, %eax
jne not_true
test %ebx, %ebx
jne not_true
...then part...
not_true:
...
~~~




#
