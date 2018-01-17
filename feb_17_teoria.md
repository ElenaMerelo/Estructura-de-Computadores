**1. ¿Cuál de las siguientes afirmaciones sobre el
benchmark SPEC CPU es falsa?**
a. La última versión es SPEC CPU2006 V1.2
de 2011 ~
 b. Se cronometran unos 12 tests de enteros
(CINT2006) y unos 17 tests de punto
flotante (CFP2006) ~
 c. Se usa como referencia un computador
UltraSPARC II 300MHz, y para cada test se
calcula el cociente entre el tiempo de
ejecución en el computador a testear y en el
de referencia ~
 **d. El resultado final es la media aritmética de
las (12 ó 17) velocidades, bien sea de
enteros ó de punto flotante (SPECint2006 ó
SPECfp2006)**

> La **SPEC2000**  provee cuatro medidas para cada componente (consistente en la media geométrica de los tiempos de ejecución de los programas). Esto es porque tiene dos clasificaciones. La primera es en cuanto a la optimización del compilador por el usuario:

>base ("conservadora"): sirve para encuadrar a los usuarios que compilan con las opciones de optimización generales ofrecidas por el compilador, de manera que tiene una serie de referencias establecidas para usar las opciones del compilador (por ej. deben usarse las mismas opciones en el mismo orden en todos los benchmarks de un mismo lenguaje, no más de cuatro opciones de optimización, y no deben usarse banderas de reivindicación).
    no base ("agresiva"): intenta encuadrar a los usuarios que intentan lograr el mejor rendimiento de sus programas. Son opcionales y tienen requerimientos mucho menos estrictos (por ej. pueden usarse diferentes opciones de compilación para distintos programas escritos en el mismo lenguaje)

>La segunda, se refiere a la cantidad de tareas que se corren al mismo tiempo:

>no rate (monotarea): corresponde a la velocidad de ejecución de una sola tarea.

>rate (multitarea): corresponde a la capacidad de la máquina de llevar a cabo un cierto número de tareas similares. Tradicionalmente usado para medir el rendimiento de multiprocesadores.

>La combinación de estas dos clasificaciones nos otorga 4 medidas distintas para el CINT2000 y 4 para el CFP2000. SPEC usa una Sun Ultra5 10 con un procesador de 300 MHz como máquina de referencia. Toma aproximadamente dos días hacer una ejecución conforme a SPEC (por lo menos tres repeticiones de cada benchmark para asegurar la validez de los resultados) de CINT2000 y CFP2000 en esta máquina.

>SPEC CPU2000 es un Benchmark producido por la SPEC. Fue creado con el fin de proveer una medida de rendimiento que pueda ser usado para comparar cargas de trabajo intensivas en cómputo en distintos sistemas de computadora. Contiene dos benchmark suites: CINT2000 para medir y comparar el rendimiento de computación intensiva de enteros, y CFP2000 para medir y compara el rendimiento de computación intensiva en flotantes.

>La "C" en CINT2000 y CFP2000 denotan que son benchmarks a nivel de componentes, en oposición a benchmarks de todo el sistema. Al ser intensivos en cómputos, miden el rendimiento del procesador de la computadora, la arquitectura de la memoria y el compilador. El CINT2000 y el CFP2000 no fuerzan la entrada/salida (unidades de disco), trabajo en red o gráficos. Si bien pueden utilizarse estos benchmarks para probar un sistema de forma tal que alguno de estos componentes afecte el rendimiento del equipo, no es ese el objetivo de estas suites.

> The **SPEC CPU® 2006** benchmark is SPEC's industry-standardized, CPU-intensive benchmark suite, stressing a system's processor, memory subsystem and compiler.
>This benchmark suite includes the SPECint® benchmarks and the SPECfp® benchmarks. The SPECint® 2006 benchmark contains 12 different benchmark tests and the SPECfp® 2006 benchmark contains 19 different benchmark tests.

>The SPEC CPU® 2006 benchmark has several different ways to measure computer performance. One way is to measure how fast the computer completes a single task; this is a speed measurement. Another way is to measure how many tasks a computer can accomplish in a certain amount of time; this is called a throughput, capacity or rate measurement.

>**The SPECfp2006 test suite contains 17 benchmark programs, designed to evaluate the floating point operations performance of a given system**. Three of these programs are written in C, four are written in C++, six are written in Fortran, and four are written in both C and Fortran. The suite was released on August 24, 2006[2] replacing SPECfp2000 as of February 2007

>**For SPEC CPU2006, the reference machine is a Sun Ultra Enterprise 2 workstation with a 296-MHz UltraSPARC II processor.**

Realmente la a) también es falsa, la última versión fue sacada en 2017. Leyendo lo anterior. La única afirmación verdadera es c)
d) es falsa ya que no es la media aritmética de las velocidades sino la geométrica.

**2. ¿En qué generación, dentro de la historia de
los computadores digitales, aparecieron la
microprogramación, la segmentación de
cauce, la memoria cache, los S.O.
multiusuario y la memoria virtual?**
2a generación (1955-65) ~
 **3a generación (1965-75)** ~
 4a generación (1975-85) ~
esas innovaciones se repartieron a lo largo
de varias generaciones, no sólo una.

>**The five generations of computers** ~
**First Generation: Vacuum Tubes (1940-1956)**

>The first computers used vacuum tubes for circuitry and magnetic drums for memory, and were often enormous, taking up entire rooms. These computers were very expensive to operate and in addition to using a great deal of electricity, the first computers generated a lot of heat, which was often the cause of malfunctions.

>First generation computers relied on machine language, the lowest-level programming language understood by computers, to perform operations, and they could only solve one problem at a time. It would take operators days or even weeks to set-up a new problem. Input was based on punched cards and paper tape, and output was displayed on printouts.

>The UNIVAC and ENIAC computers are examples of first-generation computing devices. The UNIVAC was the first commercial computer delivered to a business client, the U.S. Census Bureau in 1951.

>**Second Generation: Transistors (1956-1963)**

>The world would see **transistors** replace vacuum tubes in the second generation of computers. The transistor was invented at Bell Labs in 1947 but did not see widespread use in computers until the late 1950s.

>The transistor was far superior to the vacuum tube, allowing computers to become smaller, faster, cheaper, more energy-efficient and more reliable than their first-generation predecessors. Though the transistor still generated a great deal of heat that subjected the computer to damage, it was a vast improvement over the vacuum tube. Second-generation computers still relied on punched cards for input and printouts for output.

>Second-generation computers **moved from cryptic binary machine language to symbolic, or assembly, languages, which allowed programmers to specify instructions in words. High-level programming languages were also being developed at this time, such as early versions of COBOL and FORTRAN.** These were also the **first computers that stored their instructions in their memory, which moved from a magnetic drum to magnetic core technology**.

>**Third Generation: Integrated Circuits (1964-1971)**

>The development of the **integrated circuit** was the hallmark of the third generation of computers. Transistors were miniaturized and placed on silicon chips, called semiconductors, which drastically increased the speed and efficiency of computers.

>Instead of punched cards and printouts, users interacted with third generation computers through **keyboards** and **monitors** and interfaced with an **operating system**, which allowed the device to run many different applications at one time with a central program that monitored the memory. Computers for the first time became accessible to a mass audience because they were smaller and cheaper than their predecessors.


>**Fourth Generation:  Microprocessors (1971-Present)**

>The **microprocessor** brought the fourth generation of computers, as thousands of integrated circuits were built onto a single silicon chip. What in the first generation filled an entire room could now fit in the palm of the hand. The Intel 4004 chip, developed in 1971, located all the components of the computer—from the central processing unit and memory to input/output controls—on a single chip.

>In 1981 IBM introduced its **first computer for the home user**, and in 1984 Apple introduced the Macintosh. Microprocessors also moved out of the realm of desktop computers and into many areas of life as more and more everyday products began to use microprocessors.

>As these small computers became more powerful, they could be linked together to form networks, which eventually led to the development of the **Internet**. Fourth generation computers also saw the development of **GUIs**, the **mouse** and **handheld devices**.

>**Fifth Generation: Artificial Intelligence (Present and Beyond)**

>Fifth generation computing devices, based on artificial intelligence, are still in development, though there are some applications, such as voice recognition, that are being used today. The use of parallel processing and superconductors is helping to make artificial intelligence a reality. Quantum computation and molecular and nanotechnology will radically change the face of computers in years to come. The goal of fifth-generation computing is to develop devices that respond to natural language input and are capable of learning and self-organization.

**3. Respecto a tamaños de tipos integrales en
x86 y x86-64, la excepción es que:**
int pasa de 4 B (x86) a 8 B (x86-64) ~
**long int pasa de 4 B a 8 B** ~
 long long int pasa de 4 B a 8 B ~
 ninguna de las anteriores

 >en x86 int y long int ocupa 4B, long long int 8B mientras que en x86-64 int sigue siendo 4B, long int cambia a 8B y long int sigue siendo 8B.

 **4. Con el repertorio IA32 para sumar %eax y %ebx dejando el resultado en %ecx se podría hacer lo siguiente:**
lea %eax, %ebx, %ecx ~
 **lea (%eax, %ebx, 1), %ecx** ~
 lea %ecx, [%eax, %ebx] ~
 lea %ecx, %ebx, %eax

**5. Cuál de las instrucciones máquina siguientes
es incorrecta en x86-64:**
testl %edx, %edx ~
 **movl %r8, %eax** ~
 movl (%rdi,%rcx,4), %edx ~
 addq $1, %rcx

 **6. Si la variable val está almacenada en ebx y
la variable x está almacenada en eax, la
sentencia val ^= x; se puede traducir a
ensamblador como:**
xorl %ebx,%eax ~
 **xorl %eax,%ebx** ~
 andl %ebx,%eax ~
 testl %eax,%ebx

>Como val está en %ebx y queremos hacer xor con x que está en eax, modificando val, %ebx ha de ser el segundo argumento de la instrucción, y no es testl ya que ésta es equivalente a and, no a xor:

>The TEST instruction is the same as the AND instruction except that it does not store the result. It only modifies the flags. It modifies the following flags: sign, parity, zero, carry (always 0) and overflow (always 0).
~~~
testl %eax, %eax
jz    zeroLabel     ; jump if EAX is zero
js    negLabel      ; jump if EAX is negative
jns   posLabel      ; jump if EAX is positive
~~~

**7. Para poner a 1 el bit 5 del registro %edx sin
cambiar el resto de bits podemos usar la
instrucción máquina:**
and $32, %edx ~
 and $0x5, %edx ~
 or $0b101, %edx ~
 **or $0x20, %edx**

 >Ox20 en binario es 0010 0000. luego si empezamos a contar desde el 0 tiene un 1 en el bit 5, al hacer or con %edx si el bit 5 correspondiente está a 1 lo deja igual, si está a 0 lo cambia a 1, que es lo que queremos, por eso es correcto.

 **8. Si tenemos un número n, de 64 bits,
almacenado en la pareja de registros
EDX:EAX (EDX contiene los 32 bits más significativos y EAX los 32 bits menos
significativos) y queremos realizar la
división n / 2^32 entonces:**
a. Podemos quedarnos con EDX, pero sólo en
el caso de que n sea un número sin signo. ~
 **b. Podemos quedarnos con EDX tanto si n es
un número con signo como sin signo.** ~
 c. Podemos usar las instrucciones siguientes,
pero sólo en el caso de que n sea un número
sin signo:
mov $0x100000000,%ecx
div %ecx ~
 d. Podemos usar las instrucciones siguientes
tanto si n es un número con signo como sin
signo:
mov $0x100000000,%ecx
div %ecx

**9. ¿Dónde está ubicado el primer argumento a
una función (suponer código ensamblador
cdecl generado por gcc para Linux/x86)
imediatamente después de ejecutar la
instrucción call?**
%ebp + 0x4 ~
 %ebp - 0x4 ~
 **%esp + 0x4** ~
%esp - 0x4

**10. Dado el código C siguiente:**
~~~c
struct data {
  char str[16];
};

char *f(struct data *ptr) {
  return &(ptr->str[2]);
}
~~~
**la función se traducirá a ensamblador de
x86-64 como:**
a.
~~~
leaq 2(%rdi), %rax
ret
~~~
b.
~~~
movq (,%rdi,2), %rax
ret
~~~
c.
~~~
movq 2(%rdi), %rax
ret
~~~
d.
`leaq (,%rdi,2), %rax`

e.
`ret`

**a)** es la opción correcta.

**11. Respecto a requisitos de alineamiento de
structs en gcc/IA32 x86 y x86-64, alguna de
las siguientes afirmaciones es falsa:**
a. en x86 Linux alinea double a 4x (Windows
no)

b. en x86 Linux alinea long double a 4x
(Windows también)

c. en x86-64 Linux alinea double a 8x
(Windows también)

**d. en x86-64 Linux alinea float a 8x (Windows
también)**

**12. Si la estructura struct a ocupa un
espacio de 28 bytes en memoria, ¿cuántos
bytes ocupa la siguiente estructura struct
b cuando se compila en 64 bits?**
~~~c
struct b {
  struct a a1;
  int i;
  struct a a2;
};
~~~
24 bytes ~ **60 bytes**~
 **64 bytes** ~
 84 bytes

**13. Respecto a los términos microinstrucción y
microcódigo:**

a. Son equivalentes, llamamos microcódigo o
microinstrucción a una palabra de la
memoria de control

b. Una microinstrucción está programada en
microcódigo, que es un lenguaje para
programar señales de control

c. Un microcódigo controla una serie de
señales de control relacionadas (por
ejemplo, el código 000 para que la ALU
realice la suma), y varios microcódigos
juntos forman una microinstrucción

**d. Microcódigo es el contenido de la memoria
de control, y una microinstrucción es una
palabra de dicha memoria**

**14. ¿Cuál de las siguientes afirmaciones es
verdadera?**

**a. La unidad de control necesita como entrada
el registro de estado para poder controlar la
ejecución de las instrucciones de salto
condicional.**

b. El registro de instrucción es un registro de
propósito específico que contiene la
dirección de la siguiente instrucción a
ejecutar.

c. Las únicas instrucciones en las que algunas
de sus fases de ejecución conllevan un
acceso a memoria son las instrucciones load
y store.

d. El registro puntero de pila es un registro de
propósito general que suele contener tanto
direcciones como datos.

**15. Un procesador con una unidad de control
microprogramada tiene una memoria de
control de 300 palabras de 100 bits, de las
que 200 son diferentes. Si se rediseñara
como unidad de control nanoprogramada,
¿qué tamaño ocuparía la nanomemoria que
contiene las microinstrucciones completas
sin repeticiones?**

**20000 bits** ~
 21600 bits ~
 22400 bits ~
 30000 bits
>microinstrucciones completas sin repeticiones= palabras diferentes * bits memoria de control

**16. En el pseudocódigo usado para representar
las microinstrucciones, la expresión “goto
f(IR)”:**

a. Se utiliza para realizar un microsalto
condicional en función del registro de
estado.

b. Realiza una llamada a una microsubrutina.

**c. Salta a una dirección de memoria de control
que depende de la instrucción máquina
actual.**

d. Permite saltar a la dirección de memoria de
control del principio de un microbucle.

**17. Respecto a la predicción de saltos, alguna de
las siguientes afirmaciones es falsa:**

a. si se toma la misma decisión para cada tipo
de instrucción, se trata de "predicción
estática"

b. si la predicción cambia según la historia de
ejecución del programa, se trata de
"predicción dinámica"

**c. para predicción estática, es conveniente
decidir que los saltos hacia adelante
siempre se cumplen, y hacia atrás no**

d. para predicción dinámica, existen, entre
otros, algoritmos de dos o cuatro estados,
que requieren 1 o 2 bits por instrucción

**18. Respecto a los conceptos de procesamiento
segmentado y superescalar, una de las
siguientes afirmaciones es falsa:**

a. idealmente, con el segmentado se intenta
ejecutar una instrucción por ciclo, y con el
superescalar más de una por ciclo (al
combinarlo con segmentado)

**b. en cualquier procesador resulta ventajoso usar
una cola de instrucciones, pero es más
importante para uno segmentado (fundamental)
que para uno superescalar (conveniente)**

c. por definición, un procesador superescalar debe
tener varias unidades funcionales (más de una)

d. implícitamente, se presupone que un
procesador superescalar emitirá más de una
instrucción por ciclo

>Superescalar es el término utilizado para designar un tipo de microarquitectura de procesador capaz de ejecutar más de una instrucción por ciclo de reloj. El término se emplea por oposición a la microarquitectura escalar que sólo es capaz de ejecutar una instrucción por ciclo de reloj.

>La microarquitectura superescalar utiliza el paralelismo de instrucciones además del paralelismo de flujo, este último gracias a la estructura en pipeline. La estructura típica de un procesador superescalar consta de un pipeline con las siguientes etapas:

    >Lectura (fetch).
    Decodificación (decode).
    Lanzamiento (dispatch).
    Ejecución (execute).
    Escritura (writeback).
    Finalización (retirement).

>En un procesador superescalar, el procesador maneja más de una instrucción en cada etapa. El número máximo de instrucciones en una etapa concreta del pipeline se denomina grado, así un procesador superescalar de grado 4 en lectura (fetch) es capaz de leer como máximo cuatro instrucciones por ciclo. El grado de la etapa de ejecución depende del número y del tipo de las unidades funcionales.

>Un procesador superescalar suele tener unidades funcionales independientes de los tipos siguientes :

  >  Unidad aritmético lógica (ALU)
    Unidad de lectura/escritura en memoria (Load/Store Unit)
    Unidad de coma flotante (Floating Point Unit)
    Unidad de salto (Branch unit)

>Un procesador superescalar es capaz de ejecutar más de una instrucción simultáneamente únicamente si las instrucciones no presentan algún tipo de dependencia (hazard). Los tipos de dependencia entre instrucciones son :

    >Dependencia estructural, esta ocurre cuando dos instrucciones requieren el mismo tipo unidad funcional y su número no es suficiente.
    Dependencia de datos, esta ocurre cuando una instrucción necesita del resultado de otra instrucción para ejecutarse, por ejemplo R1<=R2+R3 y R4<=R1+5.
    Dependencia de escritura o falsa dependencia o nombre, esta ocurre cuando dos instrucciones necesitan escribir en la misma memoria, por ejemplo R1<=R2+R3 y R1<=R1+5.
    Dependencia de control, esta ocurre cuando una instrucción depende de una estructura de control y no se puede determinar el flujo correcto hasta la evaluación de la estructura de control, por ejemplo, if R1<R2 then R3<=R4+R5 else R6<=R7+5.

>La detección y resolución de las dependencias entre instrucciones puede ser estática (durante la compilación) o dinámica, es decir, a medida que se ejecuta un programa, generalmente durante la etapas de codificación y lanzamiento de las instrucciones.

>4.
Características de los procesadores segmentados.
La segmentación (
pipelining
) es una técnica empleada en el diseño de procesadores que trata de explotar
el paralelismo intrínseco que existe entre las instrucciones de un flujo secuencial.
Mediante la segmentación se puede solapar la ejecución de múltiples instrucciones. Cada etapa de la
segmentación
completa una parte de la tarea total. La salida de un segmento es la entrada del siguiente.
La segmentación puede procesar las subtareas de forma simultánea.
La
velocidad de emisión de tareas
 es el ritmo al que salen las tareas del procesador.
La profundidad de segmentación es el número de
n
 etapas en las que puede dividirse el procesamiento de
una instrucción.
Para que el tiempo de latencia del procesador segmentado sea el mínimo posible es necesario que el
procesador esté equilibrado.
El procesador está equilibrado si todas las subtareas en que se haya dividido la tarea total tarden en
procesarse el mismo tiempo. Las tareas no pueden avanzar a la etapa siguiente hasta que no se haya
terminado la subtarea más lenta, en el caso que el procesador no esté equilibrado las etapas más rápidas
estarán un tiempo sin hacer trabajo, disminuyendo el rendimiento total del procesador.
La
relación de precedencia
 de un conjunto de subtareas
T
1
,...,T
n
 que componen cierta area
T
, especifica
para cada subtarea
T
j
 que no puede comenzarse hasta que hayan terminado ciertas subtareas
T
i
.

**19. Respecto a los conceptos de interfaz de
dispositivo, controlador(a), puerto de E/S:**

**a. La controladora o interfaz contiene los
puertos necesarios para utilizar el
dispositivo**

b. Cada puerto o interfaz es una línea de
comunicación con el procesador. El
conjunto de ellos forma el controlador.

c. El puerto, o interfaz, contiene los
controladores necesarios para comunicar el
dispositivo con el procesador

d. El interfaz contiene las controladoras
necesarias para conectar los puertos con el
procesador

**20. Respecto a los conceptos de procesador de
E/S, canal de E/S, dispositivos de E/S:**

**a. Un procesador o canal tiene un repertorio
de instrucciones específico para manejar los
dispositivos E/S**

b. Cada canal es una línea de comunicación
entre el procesador y un dispositivo de E/S.

c. Al conjunto de conexiones entre el
procesador y los dispositivos se le
denomina canal de E/S (de ese ordenador)
d. La pregunta es capciosa, el procesador no
es E/S, son otros dos componentes von
Neumann distintos (ALU+UC)


**21. La E/S programada:**

a. Mejora las prestaciones globales del sistema
respecto a la E/S por interrupciones porque la
CPU tiene el control de toda la operación.

b. Mejora las prestaciones globales del sistema
respecto a la E/S por interrupciones porque la
CPU es más rápida que el controlador de
interrupciones y la interfaz del periférico.

c. Empeora las prestaciones globales del sistema
respecto a la E/S por interrupciones porque una
instrucción de transferencia individual de datos
con la interfaz del periférico (por ej. IN, OUT)
es más lenta en E/S programada que en E/S por
interrupciones.

**d. Empeora las prestaciones globales del sistema
respecto a la E/S por interrupciones porque la
CPU debe encargarse de la sincronización con
la interfaz del periférico haciendo una espera
activa.**


**22. Una puerta AND con 16 entradas conectada
a un bus de direcciones de 16 bits, con todos
los bits negados excepto A10 y A6, permite
seleccionar un dispositivo (con CS activa en
alta) en la dirección:**
0xFDDF ~
 0xFBBF ~
 0x0220 ~
 **0x0440**

>Escribimos 16 rallitas, desde 0 hasta 15, y ponemos a 1 las que están en la posición 6 y 10, el resto a 0, pasamos a hexadecimal lo resultante, 0000 0100 0100 0000, y obtenemos 0440.

**23. Un computador con 15 líneas de direcciones
tiene 3 módulos de memoria de 2^13 palabras
y utiliza E/S mapeada en memoria. ¿Cuál es
el número máximo de periféricos que
pueden conectarse, si cada uno de ellos
utiliza 8 direcciones?**
**2^10** ~
 2^12 ~
 2^11 ~
 2^13

 >La E/S mapeada en memoria usa el mismo bus de direcciones para memoria y dispositivos de E/S, y las instrucciones de la CPU usadas para acceder a la memoria son también usadas para acceder a los dispositivos. Para tener espacio para los dispositivos de E/S, las áreas del espacio direccionable por la CPU deben ser reservadas para E/S más que para memoria. Esta reserva puede ser temporal o permanente. Cada dispositivo de E/S monitoriza el bus de direcciones de la CPU y responde a cualquier acceso de esta al espacio de direcciones del dispositivo, conectando el bus de datos con la localización en memoria física del dispositivo deseado.

>La E/S independiente usa un tipo especial de instrucciones de la CPU para implementar E/S. Principalmente en microprocesadores Intel encontramos las instrucciones IN y OUT, que pueden leer y escribir un único byte en un dispositivo de E/S. Estos tienen un espacio de direcciones separadas de la memoria, llevado a cabo o bien por un pin “ E/S ”extra en la CPU o bien por un bus entero dedicado a E/S.

>Un dispositivo de acceso directo a memoria (DMA) no se ve afectado por estos métodos de comunicación CPU-dispositivo, especialmente por la E/S mapeada en memoria. Esto es porque, por definición, DMA es un método de comunicación memoria-dispositivo que evita la CPU.

>Una interrupción hardware es otro método de comunicación entre CPU y periféricos. No obstante, se trata siempre separadamente por múltiples razones. Es un iniciador de dispositivo, en oposición a los métodos iniciadores de CPU. Es también unidireccional, pues la información fluye solo del dispositivo a la CPU. Para terminar cada interrupción lleva consigo misma solo un bit de información con la única intención de notificar la interrupción.

**24. Un procesador accede en el instante de
tiempo t a una posición de memoria d(t).
Poco tiempo después (en el instante de
tiempo t+k) accede a la posición anterior
d(t)-1. Esos dos accesos son un ejemplo de...**

**a. Localidad espacial**

b. Localidad temporal

c. No tiene nombre, ese tipo de localidad con
incremento negativo (d(t)-1) no se ha
estudiado en clase

d. No es una localidad, esa condición no
guarda relación con el concepto de
localidad

>Los programas, durante su ejecución, no acceden con la
misma probabilidad a todos sus datos o instrucciones.

>Localidad espacial (en el espacio de direcciones):
Cuando un programa accede a una instrucción o a un
dato, existe una elevada probabilidad de que
instrucciones o datos cercanos sean accedidos pronto.

>Localidad temporal:
Cuando un programa accede a una instrucción o un
dato, existe una elevada probabilidad de que esa
misma instrucción o dato vuel
va a ser accedido pronto.

**25. Una jerarquía de memoria consta de una
cache con una tasa de aciertos del 92% y
4 ns de tiempo de acceso y una memoria
principal con una tasa de aciertos del 100%
y 100 ns de tiempo de acceso. ¿Cuál es el
tiempo promedio estimado de acceso a
memoria?**

a. 6 ns

b. 8 ns

c. 10 ns

**d. 12 ns**

**26. Una SRAM de 1Mx4bit (4Mbit) puede venir
organizada en 2048 filas, dedicando por
tanto al decodificador de columnas...**
6 bits ~
 7 bits ~
 8 bits ~
 **9 bits**

>2048/4 = 512 = 2^9, por eso precisa 9 bits

**27. Un sistema basado en un microprocesador
con un bus de datos de n bits y un bus de
direcciones de 16 bits direcciona la memoria
por palabras de n bits y dispone de una
memoria SRAM formada por dos módulos
de 16 K x n cada uno. ¿Qué porcentaje del
mapa de memoria está ocupado por la
SRAM?**
12,5% ~
 25% ~
 **50%** ~
 100%

>Si hubiera un solo módulo estaría ocupado al 100%, al haber dos se reparten mitad y mitad

 **28. Un módulo de memoria de 16 GB está
 formado por varios chips DRAM de
 1024Mx4. ¿Cuántos chips DRAM necesita
 el módulo?**

 4 ~
  8 ~
  16 ~
  **32**

>Chips de memoria SRAM: Tamaño 2^n * k siendo 2^n las palabras de k bits, con k = 1, 2, 4 u 8. Un chip de 2^n palabras de k bits se organiza como un
array de 2^n filas por k columnas.

>Chips de memoria DRAM: Tamaño 2^n * 1 ó 2^n * 4, organización (2-1)/(2-D)-> array 2^(n/2) * 2^(n/2) por bit.

**29. Una cache de 256 B asociativa por
conjuntos de 4-vías con líneas de 16 B
tendría:**
+ **4 conjuntos**
+ 16 conjuntos
+ 64 conjuntos
+ ningún conjunto

>256B/16B todo ello entre 4 que son las vías resulta 4, los conjuntos necesarios. Conjuntos> líneas> vías

**30. En un sistema con memoria de bytes, ¿cuál
sería el tamaño de una línea de cache, si la
cache del procesador fuera de 4MB,
asociativa por conjuntos de 16-vías, y
contuviera 4096 conjuntos?**
+ 16 B
+ 32 B
+ **64 B**
+ 128 B

> 4096 conjuntos/ 16 vías todo ello entre tamaño de la caché del procesador

>Para  implementar  el  mecanismo  de  actualización  de  la  caché  con  los  datos  con  mayor  
probabilidad de ser referenciados se divide la memoria principal en bloques de un número de bytes
(4,8,16  etc.)  y  la  caché  en  marcos  de  bloque  o  líneas  de  igual  tamaño.  El  **bloque**  será,  pues,  la  
**unidad de intercambio de información entre la memoria principal y la caché**, mientras que entre la
caché y la CPU sigue siendo la palabra. El
directorio
 contiene la información de qué bloques de
Mp
se encuentran ubicados en
Mc

>A  la  hora  de  diseñar  un  sistema  de  memoria  caché  hay  que  elegir  entre  una  serie  de  
alternativas para cada uno de los siguientes elementos de diseño:
+ Función  de  correspondencia:  determina  las  posibles  líneas  de  la  caché  (marcos  de  bloque)  en  las  que  se  puede  ubicar  un  determinado  bloque  de  la  memoria  principal  que  ha  sido  
referenciado por el programa y hay que llevarlo a memoria caché.
+ Algoritmo de sustitución: determina el bloque que hay que desubicar de una línea de la caché cuando ésta está llena y hay que ubicar un nuevo bloque.
+ Política de escritura: determina la forma de mantener la coherencia entre memoria caché y memoria principal cuando se realizan modificaciones (escrituras)
+ Política  de  búsqueda  de  bloques:  determina  la  causa  que  desencadena  la  llevada    de  un  bloque a la caché (normalmente un fallo en la referencia)
+ Cachés independientes para datos e instrucciones: frente a cachés unificadas.

>**Función de correspondencia**
  Existen tres funciones de correspondencia para definir la posible ubicación de un bloque de
memoria  principal  (Mp)  en  la  memoria  caché  (Mc):  
directa
,
asociativa
  y  
asociativa  por  conjuntos
.
En  el  primer  caso  un  bloque  de  Mp  sólo  puede  ubicarse  en  una  línea  de  la  caché,  aquella  que  
coincide  con  el  bloque  cuando  superponemos  Mc  sobre  Mp  respetando  fronteras  de  Mc,  es  decir,  
sobre  espacios  de  Mp  que  son  múltiplos  del  tamaño  de  Mc.  En  la  correspondencia  asociativa  un  
bloque  puede  ubicarse  en  cualquier  línea  de  Mc.  Finalmente,    la  correspondencia  asociativa  por  
conjuntos es una mezcla de las anteriores.

>**En la
correspondencia directa
 el bloque  
Bj
 de
Mp
 se puede ubicar sólo en el marco de bloque
o línea
MBi
 que cumple la siguiente relación
i = j mod m
, donde
m
 es el número total de líneas que
tiene  la  caché.**











#
