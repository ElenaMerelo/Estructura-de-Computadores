# Resolución del examen de julio 2017~ Estructura de computadores
**1. Respecto a direccionamiento a memoria en ensamblador IA32 (sintaxis AT&T), de la forma D(Rb, Ri, S), sólo una de las siguientes afirmaciones es FALSA.
¿Cuál?**

  a. El desplazamiento D puede ser una constante literal (1, 2 ó 4 bytes)

  b. EBP no se puede usar como registro base

  c. ESP no se puede usar como registro índice

  d. El factor de escala S puede ser 1, 2, 4, 8
> Modo de direccionamiento a memoria indexado: D(Rb,Ri,Fe) El operando esta en la direccion de memoria resultante de calcular: D+Rb+Ri*S. Donde:
D es el Desplazamiento, puede ser constante o variable;
Rb es el registro base, puede ser cualquier registro;
Ri: Registro ındice, Cualquier registro menos %esp;
S: Factor de escalacion: 1, 2, o 4
Si uno de ellos no aparece, por defecto: D=0, Rb=0, Ri=0 y Fe=1.

  Por ello a), c) y d) son verdaderas, **b)** es falsa ya que Rb puede ser cualquier registro base.

**2. La extensión de signo a m bits de un número original N de n bits, con m > n,
consiste en:**

  a. Realizar la operación 2 m – N

  b. Realizar la operación 2 m – N – 1

  c. Incrementar la cantidad de bits a m preservando el signo y el valor del número.

  d. Incrementar la cantidad de bits a m rellenando con unos por la izquierda.

  >La extensión de signo es la operación, dentro de la aritmética de computadoras, en la cual se incrementa la cantidad de bits de un número preservando el signo y el valor del número original. Es llevada a cabo mediante agregación de dígitos del lado más significativo del número, siguiendo ciertos procedimientos dependiendo de la representación particular utilizada.
  Por ejemplo, si se usan 6 bits para representar al número "00 1010" (diez positivo en decimal) y la operación de extensión de signo extiende el tamaño de la palabra a 16 bits, entonces la nueva representación es simplemente "0000 0000 0000 1010". De este modo, ambos, signo y módulo, se mantienen iguales con respecto al valor original.
  Si diez bits son utilizados para representar al número "11 1111 0001" (quince negativo en decimal) utilizando complemento a dos, y se extiende el signo hasta dieciséis bits, la nueva representación sería "1111 1111 1111 0001". De este modo, rellenando el lado más significativo con unos, el signo y módulo se mantienen iguales con respecto al valor original.
  En el conjunto de instrucciones de Intel x86, por ejemplo, existen dos maneras de realizar la extensión de signo:
  Usando las instrucciones cbw, cwd, cwde, y cdq: convierten byte a palabra, palabra a doble palabra, palabra a doble palabra extendida y palabra doble a cuádruple palabra respectivamente (en el contexto del x86, un byte equivalen a 8 bits, una palabra a 16 bits, doble palabra y doble palabra extendida a 32 bits y cuádruple palabra a 64 bits);
  Usando uno de los movimientos de extensión de signo, facilitados por la familia de instrucciones movsx (mover con extensión de signo).

  Basándonos en lo anterior, en el tercer párrafo específicamente, afirmamos que la opción correcta es **c)**.

**3. En IA32, ¿cuál de los siguientes fragmentos de programa tiene un efecto sobre los flags distinto al resto?**

  a. sub %edi, %edi
     adc $0xFFFFFFFF, %edi

  b. mov $-1, %edi

  c. mov $-1, %edi
     add $0, %edi

  d. mov $0, %edi
     sub $1, %edi

  >Z­ Zero Flag: This flag is set if the result of the computation or comparison performed by the previous instruction is zero
  -> C­ Carry Flag: This flag is set when there is a carry out of MSB in case of addition or a borrow in case of subtraction. Ranges of 8, 16, and 32 bit unsigned numbers are:
  8 bits 0 to 255 (28 ­ 1)
  16 bits 0 to 65,535 (216 ­ 1)
  32 bits 0 to 4,294,967,295 (232­1)
  -> S ­Sign Flag: Indicates the sign of the result of an operation, 0 for positive numbers and 1 for negative numbers.
  -> AC ­Auxilary Carry Flag: This is set if there is a carry from the lowest nibble, i.e, bit three during addition, or borrow for the lowest nibble, i.e, bit three, during subtraction.
  -> P­ Parity Flag: This flag is set to 1 if the lower byte of the result contains even number of 1’s
  -> O­ Over flow Flag: This flag is set if an overflow occurs, i.e, if the result of a signed operation is not large enough to accommodate in a destination register. Range of 8­, 16­, and 32­bit signed numbers size range are:
  8 bits (­ 128 to +127)
  16 bits (­ 32,768 to +32,767 215)
  32 bits (­2,147,483,648 to +2,147,483,647 231)
  Hence, the status flags are:
  CF = Carry Flag
  PF = Parity Flag
  ZF = Zero Flag
  SF = Sign Flag
  OF = Overflow Flag
  Not all instructions affect all status flags: add and sub affect all six flags; inc and dec affect all but the carry flag; mov, push and pop do not affect any flags.
  Assuming intel x86 assembler: Both ADD and ADC will set the Carry Flag on high-order bit carry or borrow and it will be cleared otherwise. Using ADC when the CF is 1 and there is no overflow, will result in CF=0.

  Así, b) no modifica ningún flag, d) cambia el de signo, le está restando 1 a un registro en el que teníamos almacenado 0, c) está sumando 0 a un registro en el que tenemos -1, si eso modificaría también el flag de signo. La opción restante es a), que resta a un registro él mismo, con lo que resultará 0 y ZF se activará, adc lee el bit de acarreo y lo consume, sumándoselo a %edi si tiene, sino no hace nada. Todas las instrucciones modifican los flags salvo **b)**, tiene pues un efecto sobre los flags diferente al resto, es la solución.

**4. Si %rsp vale 0xdeadbeefdeadd0d0, ¿cuál será su nuevo valor después de que se ejecute pushq %rbx?**

  a. 0xdeadbeefdeadd0d4

  b. 0xdeadbeefdeadd0d8

  c. 0xdeadbeefdeadd0cc

  d. 0xdeadbeefdeadd0c8

  >The terms used to describe sizes in the x86 architecture are:
    byte: 8 bits
    word: 2 bytes
    dword: 4 bytes (stands for "double word")
    qword: 8 bytes (stands for "quad word")


  La solución es **d)**, ya que estamos haciendo push de una quadword, que ocupa 8 bytes, y push decrementa el puntero de pila (ESP) el número de posiciones de memoria que ocupe el dato a insertar, posteriormente procede a escribir el dato en esas posiciones reservadas, a partir de donde apunta ESP ahora.

**5. ¿Cómo se devuelve en ensamblador x86-64 Linux gcc el valor de retorno de una función long int al terminar ésta?**

  a. La instrucción RET lo almacena en un registro especial de retorno.

  b. Por convención se guarda en %eax.

  c. Se almacena en pila justo encima de los argumentos de la función.

  d. Ninguna de esas formas es la correcta.

  >Una subrutina en ensamblador sería equivalente a una función en C. Básicamente, una subrutina es un conjunto de instrucciones que inician su ejecución en un punto de código identificado con una etiqueta que será el nombre de la subrutina, y finaliza con la ejecución de una instrucción ret, instrucción de retorno de subrutina, que provoca un salto a la instrucción siguiente desde donde se ha hecho la llamada (call).
  Consideraciones importantes a la hora de definir una subrutina:
  -> Debemos almacenar los registros modificados dentro de la subrutina para dejarlos en el mismo estado en el que se encontraban en el momento de hacer la llamada a la subrutina, salvo los registros que se utilicen para devolver un valor. Para almacenar los registros modificados utilizaremos la pila.
  -> Para mantener la estructura de una subrutina y para que el programa funcione correctamente, no se pueden efectuar saltos a instrucciones de la subrutina; siempre finalizaremos la ejecución de la subrutina con la instrucción ret.
  El retorno de resultados puede efectuarse por medio de registros o de la pila.
  Si queremos pasar parámetros y devolver resultados a una subrutina utilizando la pila, y una vez definidos los parámetros que queremos pasar y los que queremos retornar, hay que hacer lo siguiente:
  1)Antes de hacer la llamada a la subrutina: es necesario reservar espacio en la pila para los datos que queremos devolver y a continuación introducir los parámetros necesarios en la pila.
  2)Dentro de la subrutina: hay que acceder a los parámetros leyéndolos directamente de memoria, utilizando un registro que apunte a la cima de la pila. El registro apuntador de pila, RSP, siempre apunta a la cima de la pila y, por lo tanto, podemos acceder al contenido de la pila haciendo un direccionamiento a memoria que utilice RSP, pero si utilizamos la pila dentro de la subrutina, no se recomienda utilizarlo.
  El registro que se suele utilizar como apuntador para acceder a la pila es el
  registro RBP. Antes de utilizarlo, lo tendremos que almacenar en la pila para
  poder recuperar el valor inicial al final de la subrutina, a continuación se carga
  en RBP el valor de RSP.
  RBP no se debe cambiar dentro de la subrutina; al final de esta se copia el valor
  sobre RSP para restaurar el valor inicial.
  3)Después de ejecutar la subrutina: una vez fuera de la subrutina es necesario
  liberar el espacio utilizado por los parámetros de entrada y después recuperar
  los resultados del espacio que hemos reservado antes de hacer la llamada.
  Hay que tener presente que el procesador también utiliza la pila para almacenar los valores necesarios para poder efectuar un retorno de la subrutina de manera correcta. En concreto, siempre que se ejecuta una instrucción call, el procesador guarda en la cima de la pila la dirección de retorno (el valor actualizado del contador de programa RIP). Es importante asegurarse de que en el momento de hacer
  ret la dirección de retorno se encuentre en la cima de la pila; en caso contrario, se romperá la secuencia normal de ejecución.
  Eso se consigue si no se modifica el valor de RBP dentro de la subrutina y al
  final se ejecutan las instrucciones:
  mov rsp, rbp    ;Restauramos el valor inicial de RSP con RBP
  pop rbp         ;Restauramos el valor inicial de RBP
  The return value of a function is in eax. If you've called a C function from asm, you can read the return value from eax. If you're trying to return from an asm function to C, store the intended return value in eax.
  **Things get a little bit more complicated for returning floating point values, long long values, or structures**
  Return Value of a function in assembly
      Integers (of any size up to 32 bits) and pointers are returned in the %eax register.
      Floating point values are returned in the 387 top-of-stack register, st(0).
      Return values of type long long int are returned in %edx:%eax (the most significant word in %edx and the least significant in %eax).
      Returning a structure is complicated and rarely useful; try to avoid it. (Note that this is different from returning a pointer to a structure).
  If your function returns void (e.g. no value), the contents of these registers are not used.
  The ret instruction transfers control to the return address located on the stack. This address is usually placed on the stack by a call instruction. Issue the ret instruction within the called procedure to resume execution flow at the instruction following the call.
  The optional numeric (16- or 32-bit) parameter to ret specifies the number of stack bytes or words to be released after the return address is popped from the stack. Typically, these bytes or words are used as input parameters to the called procedure.

  En conclusión, por ser la función de tipo long int no se guarda en %eax, se devolverá la palabra más significativa por %edx y la menos por %eax, luego la opción b) es falsa. a) es falsa ya que ret no almacena en un registro especial de retorno, sino que recupera de la pila la dirección de retorno. Ninguna de las formas es pues correcta, y **d)** es verdadera.

**6. Comparando las convenciones de llamada de gcc Linux IA32 con x86-64 respecto a registros**

  a. En IA32 %ebx es salva-invocante, pero en x86-64 %rbx es salva-invocado

  b. En IA32 %ecx es salva-invocante, y en x86-64 %rcx es salva-invocante también

  c. En IA32 %esi es salva-invocado, y en x86-64 %rsi es salva-invocado también

  d. En IA32 %ebp es especial (marco de pila), y en x86-64 %rbp también

  >Convenciones de preservación de registros
  Cuando el procedimiento yoo llama a who:
  + yoo es el que llama (invocante, llamante)
  + who es el llamado (invocado)

  >¿Se puede usar un registro para almacenam. temp.? Convenciones:
  + “Salva Invocante”~ El que llama salva valores temporales en su marco antes de la llamada.
  + “Salva Invocado”~ El llamado salva valores temporales en su marco antes de reusar registros.

  >Uso de registros en IA32/Linux+Windows
  + %eax, %edx, %ecx- Invocante salva antes de llamada
  + %eax- tb. usado para devolver v. entero
  + %ebx, %esi, %edi- Invocado salva si quiere usarlos
  + %esp, %ebp- forma especial de invocado-salva. Restaurados a su valor original al salir del procedimiento.

  >**En definitiva, los registros temporales salva-invocante son %eax, %edx y %ecx, los temporales salva-invocado %ebx, %esi, %edi y los especiales %esp y %ebp, en IA32.**

  >Uso de registros en x86-64: Convenios de uso
  + %rax Valor retorno
  + %rsp Puntero de pila
  + Salva-invocados: %rbx, %rbp, %r12, %r13, %r14, %r15
  + Salva-invocantes: %r10, %r11
  + Argumentos: 1 %rdi, 2 %rsi, 3 %rdx, 4 %rcx, 5 %r8, 6 %r9. Estos registros pueden usarse también como salva-invocante

  Basándonos en lo anterior, a) es falsa, ya que en IA32 %ebx no es salva-invocante sino salva-invocado aunque en x86-64 %rbx sí sea salva-invocado. **b)** es verdadera, y en c) es cierto que en IA32 %esi es salva-invocado pero en x86-64 %rsi es usado para pasar argumento, luego salva-invocante. d) es falsa porque %rbp no es especial en x86-64.


**7.Son funciones de la unidad de control:**

  a. La codificación de las instrucciones máquina
  b. La lectura de memoria principal de la instrucción apuntada por el μPC
  c. El secuenciamiento de las instrucciones máquina
  d. Todas las respuestas son ciertas

  >Según las diapositivas, detecta señales de estado (eléctricas) procedentes de las distintas unidades, capta de la memoria una a una las instrucciones máquina del programa, y genera señales de control dirigidas a todas las unidades, monitorizando las operaciones que implican la ejecución de la instrucción. Contiene un reloj que sincroniza todas las operaciones elementales de la computadora. El periodo del reloj se denomina tiempo de ciclo (entre décimas de ns y varios μs). La frecuencia del reloj (MHz ó GHz) determina, en parte, la velocidad de funcionamiento del computador.

  >La UC interpreta y controla la ejecución de instrucciones leídas de memoria en dos fases:
  + Fase de captación de instrucción: leer la dirección de la instrucción a ejecutar, leerla de memoria, llevarla al registro adecuado para su ejecución e incrementar PC para que apunte a la siguiente instrucción.
  + Fase de ejecución: la instrucción se decodifica y ejecuta bajo el control de la UC y para ello se realizan las operaciones específicas correspondientes al código de operación (codop) de la instrucción captada y se generan las señales de control oportunas.

  >Unidad de control cableada: analiza o interpreta la instrucción máquina almacenada en IR y los valores de los biestables (FF, esp, ir) y genera las 29 señales de control que monitorizan el funcionamiento de los distintos elementos del computador. Estas señales de control (o microórdenes) producen microoperaciones en un orden predeterminado de forma sincronizada con un estado máquina.

  >Unidad de control microprogramada: genera, en cada pulso de reloj, un vector de 29 microórdenes (señales de control). Se pueden grabar en una memoria ROM, llamada memoria de control (MC), esos vectores. La UC microprogramada está formada por la memoria de control y una serie de circuitos denominado secuenciador de la memoria de control que genera las direcciones de las posiciones de las palabras de la memoria de control a leer.

  Conscuentemente, b) no es verdadera se lee la instrucción almacenada en IR, la UC no cofidifica instrucciones máquina sino que las decodifica en la fase de ejecución por lo que la a) es falsa también. La opción restante y verdadera es **c)**, la última frase del párrafo anterior lo confirma.

**8. Respecto a MDR y MAR**
  a. Ambos son accesibles por el programador
  b. MAR contiene el dato/instrucción que se leerá o escribirá en memoria
  c. MAR requiere menos señales de control que MBR
  d. Ambos permiten guardar información sobre el marco de pila

  >Registros
  + PC: contador de programa
  + RI: registro de instrucción
  + SP: puntero de pila
  + MAR: registro de direcciones de memoria
  + MBR: registro de datos de memoria
  + RE: registro de estado
  + Registros transparentes al usuario: RT1, RT2, RT3.
  + Otros registros de control y estado: MAR, MBR, PC, RE, RI

  >El Memory Address Register (MAR), Registro de Direcciones de Memoria, es un registro específico de alta velocidad, integrado en el microprocesador, que contiene la dirección del dato que se quiere leer o escribir. El registro está conectado con el bus de direcciones, y su contenido se refleja en éste.

  >Un registro de arranque principal, conocido también como registro de arranque maestro (por su nombre en inglés master boot record, MBR) es el primer sector de un dispositivo de almacenamiento de datos, como un disco duro. A veces, se emplea para el arranque del sistema operativo con bootstrap, otras veces es usado para almacenar una tabla de particiones y, en ocasiones, se usa sólo para identificar un dispositivo de disco individual, aunque en algunas máquinas esto último no se usa y es ignorado.

  >Libro Organización de computadores 5º edición Karl Hamacher,... cap 1.3-> Finalmente, dos registros facilitan la comunicación con la memoria. Son el registro de dirección de memoria(MAR) y el registro de datos de memoria(MDR). El MAR contiene la dirección de la posición a la que se va a acceder. El MDR contiene los datos que se van a escribir o que se han leído de la posición direccionada. Consoderemos ahora algunos pasos típicos de funcionamiento. Los programas residen en memoria, y usualmente llegan ahó a través de la unidad de entrada. La ejecución de un programa comienza cuando al PC se le dice que apunte a la primera instrucción del programa. El contenido del PC se transfiere al MAR y se envía a la memoria una señal de control de lectura. Después de que el tiempo requerido para acceder a la memoria pasa, la palabra direccionada se lee de la memoria y se carga en el MDR. Luego los contenidos del MDR se transfieren al IR. En este punto la instrucción está lista para ser decodificada y ejecutada.

  b) es falsa ya que MAR no contiene el dato sino la dirección que se leerá/escribirá en memoria, d) también ya que solo MAR guarda información sobre el marco de pila, ambas no son accesibles por el programador, luego a) es falsa también. **c)** es pues la opción verdadera.

**9. Una instrucción máquina puede desglosarse en las siguientes operaciones elementales: sp := sp – 1; m[sp] := pc; pc := x. Probablemente se trate de una instrucción de:** apilamiento // **llamada a subrutina** // carga local // almacenamiento local

**10. En una unidad de control microprogramada con formato de microinstrucciones vertical, un subcampo que deba especificar 16 señales de control codificadas de tal forma que pueda activarse sólo una o ninguna habrá de tener una anchura mínima de:**
4 bits ~ **5 bits** ~ 16 bits ~ 17 bits, son 5 bits ya que 2^4 es 16, necesitaremos desde 2^0 hasta él, que son 5 números.

**11. Dado un camino de datos concreto, un posible formato de microprogramación se caracteriza como horizontal o vertical según tenga más o menos (señalar la respuesta falsa):** codificación ~ solapamiento ~ **microbifurcaciones** ~ longitud relativa de microinstrucción

**12. El control residual se utiliza para:**
a. reducir el tiempo de ejecución de las
instrucciones máquina ~
b. eliminar los bits residuales de la
ejecución de las microinstrucciones ~
**c. reducir el tamaño de la memoria de
control** ~
d. ninguna de las anteriores es cierta

**13. Un procesador está segmentado en las
etapas F, D, E, M y W. Cada una de ellas
consume un tiempo t. La aceleración
ideal (si no hay riesgos) al ejecutar n
instrucciones respecto a un procesador no
segmentado será:**
**5n / (4+n)** ~
 (4+n) / 5t ~
 4n / (5+n) ~
 (5+n) / 4t

 **14. En un procesador con segmentación de
cauce, aumentar el número de etapas
(p.ej. de 2 a 4, o de 4 a 8), tiene en
general como consecuencia:**
**a. Un incremento de las prestaciones** ~
 b. Un mayor retraso en la ejecución de los
programas debido al incremento del
número de etapas ~
 c. Una disminución en la posible
dependencia de datos ~
 d. Una disminución de la máxima
frecuencia de reloj a la que puede operar
el cauce

**15. En la secuencia de instrucciones
siguiente, siendo el primer registro el
destino, ¿cuántos riesgos se dan?
sub r2,r1,r3
or r8,r6,r2**
a. Un riesgo estructural~
 **b. Un riesgo por dependencia de datos** ~
 c. Un riesgo estructural y dos por
dependencia de datos ~
 d. Dos riesgos por dependencia de datos y
uno de control

**16. La precaptación (cola de instrucciones)
está relacionada con...**
**a. Los riesgos estructurales (intenta evitar
el efecto de un fallo de cache)** ~
 b. Los riesgos de (dependencia de) datos
(intenta que el dato esté disponible
anticipadamente) ~
 c. Los riesgos de control (intenta
determinar de antemano el flujo de
control) ~
 d. Los riesgos de transferencia (intenta
agrupar las posibles transferencias de un
conjunto de instrucciones)

**17. Respecto a la segmentación, ¿cuál de las
siguientes afirmaciones es falsa?**
a. La técnica de register forwarding
habilita una serie de caminos (buses) que
se añaden al cauce para permitir que los
resultados de una etapa pasen como
entradas a la etapa donde son necesarias ~
 b. La reorganización del código y la
introducción de instrucciones nop
permite evitar dependencias de datos ~
 **c. Retrasar la fase de decisión saltar/no
saltar de las instrucciones de salto
condicional contribuye a mejorar el
rendimiento del procesador** ~
 d. Cuantas más etapas tenga un cauce, más
instrucciones se estarán ejecutando en
distintas fases y más posibilidades se
presentan de que existan riesgos entre
ellas

**18. ¿Cuál de los siguientes modos de
direccionamiento es menos preferible
para un procesador de 32 bits y con
tamaño de instrucción de 32 bits?**
registro ~
 indexado ~
 indirecto a través de registro ~
 **directo (o absoluto)**

**19. La conexión entre un dispositivo de E/S y el procesador mediante bus:**
a. Es difícil de expandir ~
 **b. Permite conectar en paralelo varios dispositivos** ~
 c. Requiere mucha circuitería ~
 d. Requiere multiplexores y
demultiplexores para las señales de datos

**20. El fragmento de código ensamblador de
un microprocesador de 8 bits**
~~~
lds IOBuf ; Apuntar puntero pila a
          ; ...área mem.intermedia
ldx Count ; Inicializar X-contador
poll lda a Status; Leer estado en A
bpl poll ; Signo(A)!=1 => repetir
lda a Data ; Leer dato en A
psh a ; Transferir dato a pila
dex ; Decrementar contador X
bne poll ; Seguir leyendo si X!=0
~~~
corresponde a:
**a. Entrada programada con consulta de
estado** ~
 b. Salida programada sin consulta de
estado ~
 c. Entrada programada sin consulta de
estado ~
 d. Salida programada con consulta de
estado

**21. En la E/S controlada por interrupciones:**
a. El controlador de DMA transfiere
bloques de datos por el bus del sistema. ~
 b. El controlador de DMA envía una
petición de interrupción a la CPU. ~
 c. La CPU lee y comprueba el estado de los
dispositivos de E/S (en el caso de
consulta de estado). ~
 **d. La CPU transfiere el control a una rutina
de servicio cuando recibe una
interrupción.**

**22. La instrucción máquina DI (Disable
Interrupts), conocida como CLI (Clear
Interrupt Flag) en x86, se utiliza para
desactivar:**
**a. Todas las interrupciones enmascarables** ~
 b. Las interrupciones de inferior o igual
prioridad a una dada ~
 c. Determinados niveles de interrupción de
forma selectiva ~
 d. Las interrupciones software

**23. Con nueve controladores de
interrupciones 8259 se pueden manejar
exactamente:**
8 niveles de prioridad ~
 16 niveles de prioridad ~
 24 niveles de prioridad ~
 **Ninguna de las anteriores es cierta**

**24. ¿Cuál de los siguientes es un registro de un controlador de DMA?**
IR (Instruction Register) ~
 PC (Program Counter) ~
 SP (Stack Pointer) ~
 **WC (Word Count)**

 **25. Respecto al refresco de memorias
DRAM, ¿cuál de las siguientes
afirmaciones es falsa?**
**a. Una operación de refresco consiste en
dar un impulso /CAS junto con una
dirección de columna.** ~
 b. Los chips DRAM refrescan
automáticamente la fila accedida en
cualquier ciclo de lectura o escritura. ~
 c. Se precisa una circuitería auxiliar,
externa al chip DRAM o integrada en él,
que produzca ciclos de refresco. ~
 d. Los ciclos de refresco deben producirse
cada pocos ms (milisegundos).

**26. La tasa de aciertos A i del nivel i de una
jerarquía de memoria no depende de:**
a. La capacidad (tamaño) s i del nivel i. ~
 b. La estrategia de administración de
memoria. ~
 c. La unidad de la transferencia de
información x i entre el nivel i y el i+1. ~
 **d. El ancho de banda b i del nivel i.**

**27. La política de correspondencia de una
memoria cache con 1 único conjunto es:**
a. Directa ~
 **b. Totalmente asociativa** ~
 c. Asociativa por conjuntos con una única
línea ~
 d. Asociativa por conjuntos de una única
vía

**28. La política de correspondencia de una memoria caché con la mitad de conjuntos que líneas es:**
**Asociativa por conjuntos de 2 vías** ~
 Totalmente asociativa de media vía ~
 Asociativa por conjuntos con 2 líneas ~
 Directa con 2 líneas

**29. Para construir una DRAM de 4GB con pastillas de 512MBx4bit hacen falta:**
8 pastillas ~
 **16 pastillas** ~
 32 pastillas ~
 64 pastillas

**30. Para diseñar una memoria con ancho de
palabra k*m (y mismo número palabras que
los módulos) a partir de módulos con
ancho de palabra m, se utilizan k
módulos**
a. repartiendo las líneas de datos entre los k
módulos: el primero se conecta a
D 0 ...D k-1 , el segundo a D k ...D 2k-1 , etc ~
 b. repartiendo las líneas de dirección: el 1o
se conecta a A 0 ...A k-1 , el 2o a A k ...A 2k-1 ,
etc ~
 **c. repartiendo líneas datos: el 1o se conecta
a D 0 ...D m-1 , el 2o a D m ...D 2m-1 , etc** ~
 d. repartiendo líneas dirección: el 1o se
conecta a A 0 ...A m-1 , el 2o a A m ...A 2m-1 ,
etc

>Pila IA32: Push
pushl Src
-> Capta el operando en Src
-> Decrementa %esp en 4
-> Escribe operando en dir. indicada por %esp
Pila IA32 : Pop
popl Dest
 Capta operando de dir. indicada por %esp
-> Incrementa %esp en 4
-> Escribe el operando en Dest


>Sufijos en x86: b->1 byte, w->2 bytes, l->4 bytes y q->8 bytes ocupa.
