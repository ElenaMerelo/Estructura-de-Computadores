# Resolución del examen de julio 2017~ Estructura de computadores
1. Respecto a direccionamiento a memoria en ensamblador IA32 (sintaxis AT&T), de la forma D(Rb, Ri, S), sólo una de las siguientes afirmaciones es FALSA.
¿Cuál?

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

2. La extensión de signo a m bits de un número original N de n bits, con m > n,
consiste en:

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

3. En IA32, ¿cuál de los siguientes fragmentos de programa tiene un efecto sobre los flags distinto al resto?

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

  Así, b) no modifica ningún flag, d) cambia el de signo, le está restando 1 a un registro en el que teníamos almacenado 0, c) está sumando 0 a un registro en el que tenemos -1, si eso modificaría también el flag de signo. La opción restante es **a)**, que resta a un registro él mismo, con lo que resultará 0 y ZF se activará, adc lee el bit de acarreo y lo consume, sumándoselo a %edi si tiene, sino no hace nada, cambian flags diferentes a los demás.

**4. Si %rsp vale 0xdeadbeefdeadd0d0, ¿cuál será su nuevo valor después de que se ejecute pushq %rbx?**

  a. 0xdeadbeefdeadd0d4

  b. 0xdeadbeefdeadd0d8

  c. 0xdeadbeefdeadd0cc

  d. 0xdeadbeefdeadd0c8







 #
