+ gcc -O0 compila sin optimización

+ El modificador (switch) de gcc que hace falta para compilar una aplicación de 32 bits en un sistema de 64 bits es **-m32**.

+ La etiqueta del punto de entrada a un programa ensamblador en el entorno de las prácticas 1 a 4 (GNU/as Linux x86) es: \_start

+ La siguiente línea en la sección de datos de un programa en ensamblador de IA32
`result: .int 0,0`: Reserva espacio para un único entero, inicializado a 0,0 // Reserva espacio para un entero, inicializado a 0, seguido de un dato de tamaño indefinido,también inicializado a 0 // **Reserva espacio para dos enteros, inicializados ambos a 0** // Reserva espacio para un único entero, inicializado a 0, en la posición de memoria 0.

+ El volcado mostrado abajo se ha obtenido con el comando... objdump -h p, objdump -d p, **objdump -d p2.o**, objdump -t p2.o
~~~
00000000 <main>:
0: 55
1: 89 e5
3: 83 e4 f0
6: 83 ec 10
9: c7 44 24 04 03
e: 00 00 00
11: c7 04 24 01 00
16: 00 00
18: e8 fc ff ff ff
1d: c9
1e: c3
(Segunda columna)
push %ebp
mov %esp,%ebp
and $-16,%esp
sub $0x10,%esp
movl $3, 4(%esp)
movl $0x1,(%esp)
call <main+0x19>
leave
ret
~~~
+ En la práctica "media" se desea invocar desde lenguaje ensamblador la función printf() de libC. Eso implica que este programa, como todo programa que use libC: es obligatorio que contenga main (y entonces
es más cómodo usar gcc para enlazar) // es obligatorio enlazarlo usando gcc (y entonces es más cómodo que contenga main) // es ventajoso para ensamblarlo que contenga main, y entonces es conveniente enlazarlo usando gcc (aunque ambas cosas son opcionales) // **es ventajoso para enlazarlo usar gcc, y
entonces es conveniente que contenga main (aunque ambas cosas son opcionales)**

+ En la práctica "media" se pide sumar una lista de 32 enteros SIN signo de 32 bits en una plataforma de 32 bits sin perder precisión, esto es, evitando perder acarreos. Un estudiante entrega la siguiente versión:

  ~~~
  # $lista en EBX, longlista en ECX
  suma:
  mov $0, %eax
  mov $0, %edx
  mov $0, %esi

  bucle:
  add (%ebx,%edx,4), %eax
  jnc seguir
  inc %edx

  seguir:
  inc %esi
  cmp %esi,%ecx
  jne bucle
  ret
  ~~~
  Esta función presenta una única diferencia frente a la solución recomendada en clase, relativa al indexado en el array. Esta función suma: Produce siempre el resultado correcto // Fallaría con lista: .int 1,1,1,1, 1,1,1,1, ... // **Fallaría con lista: .int 1,2,3,4, 1,2,3,4, ...** // No es correcta pero el error no se manifiesta en los ejemplos propuestos, o se manifiesta en ambos.

+ En la práctica "media" se pide sumar una lista de 32 enteros SIN signo de 32 bits en una plataforma de 32 bits sin perder precisión, esto es, evitando perder acarreos. De entre los siguientes, ¿cuál es el mínimo valor entero que repetido en toda la lista causaría acarreo con 32 bits (sin signo)? Se usa notación decimal y espacios como separadores de millares/millones/etc. 10 000 000 // 100 000 000 // **1 000 000 000** // 10 000 000 000 porque el 1 se encuentra en la posición 2^9, y 2^8 es 32.

+ En la práctica "media" se pide sumar una lista de 32 enteros CON signo de 32 bits en una plataforma de 32 bits sin perder precisión, esto es, evitando desbordamiento. De entre los siguientes, ¿cuál es el valor negativo más pequeño (en valor absoluto) que repetido en toda la lista causaría desbordamiento con 32 bits (en complemento a 2)? Se usa notación decimal y espacios como separadores de millares/millones/etc.-10 000 000 // **-100 000 000** // -1 000 000 000 // -10 000 000 000, ahora hay que considerar el bit del signo.

+ ¿Cuál es el popcount (peso Hamming, no de
bits activados) del número 19? 2 // **3** // 4 // 5

+ La práctica "popcount" debía calcular la suma de bits (peso Hamming) de los elementos de un array. Un estudiante entrega la siguiente versión de popcount3:
~~~c
int popcount3(unsigned* array, int len){
  int i, res = 0;
  unsigned x;
  for( i = 0; i < len; i++ ) {
    x = array[i];
    asm("ini3:
    \n"
    "shr %[x]
    \n"
    "adc $0, %[r]
    \n"
    "add $0, %[x]
    \n"
    "jne ini3
    \n"
    : [r] "+r" (res)
    : [x] "r" (x) );
  }
  return res;
}
~~~
Esta función sólo tiene una diferencia con la versión "oficial" recomendada en clase. En concreto, una instrucción máquina en la sección asm() es distinta. Esta función popcount3: **produce siempre el resultado correcto** // fallaría con array={0,1,2,3} // fallaría con array={1,2,4,8} // no es correcta pero el error no se manifiesta
en los ejemplos propuestos, o se manifiesta en ambos

+ La práctica "popcount" debía calcular la suma de bits (peso Hamming) de los elementos de un array. Un estudiante entrega la siguiente versión de popcount3:
~~~c
int popcount3(int* array, int len){
long val = 0;
int i;
unsigned x;
for (i=0; i<len; i++){
x= array[i];
do{
val += x & 0x1;
x >>= 1;
} while (x);
val += (val >> 16);
val += (val >> 8);
}
return val & 0xFF;
}
~~~







#
