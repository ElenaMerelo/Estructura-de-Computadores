**1. Ensamblador (0.3 puntos). Escriba la instrucción máquina (una sola)
necesaria para llevar a cabo cada una de las siguientes operaciones:**
a. (0.05) Quitar un entero de la cabecera de la pila y guardarlo en el reg. EAX:
`pop %eax`

b. (0.05) Sumar el valor del indicador de acarreo (CF) al registro ECX: `adc %ecx`

c. (0.05) Llamar a la función f: `call f`

d. (0.05) Copiar el carácter (byte) situado en la cabecera de la pila en el registro CL sin alterar la pila: `mov $ebx, %cl`

e. (0.05) Multiplicar el contenido del registro EAX por 5, dejando el resultado
en el mismo registro: `imul 5`

f. (0.05) Poner el registro EDX a cero sin usar la instrucción mov:

>All the following instructions do the same thing: set %eax to zero. The optimal is the one with xorl.
~~~
xorl   %eax, %eax
mov    $0, %eax
andl   $0, %eax
~~~

**2. Estructuras (0.8 puntos). Considerar las siguientes declaraciones de
estructuras en lenguaje C:**
~~~c
struct a{
  float* f;
  char c;
  int i;
  char z[4];
  double d;
  short s;
};

struct b {
  struct a a1;
  int j;
  struct a a2;
};
~~~
a. (0.2) Indicar cuántos bytes ocupa struct a en Linux gcc x86:
float * -> 4 bytes alineado, char-> 1, int-> 4, char de 4-> 4*4= 16, double->4, short-> 2 bytes, en total entonces: 4+1+4+16+4+2= **21bytes**.

b. (0.2) Indicar cuántos bytes ocupa struct a en Linux gcc x86-64:
float* -> 8, char-> 1, int->4, char de 4-> 16, double-> 8, short-> 2, total: **39 bytes**.
c. (0.2) Indicar cuántos bytes ocupa struct b en Linux gcc x86:

d. (0.2) Indicar cuántos bytes ocupa struct b en Linux gcc x86-64:

>Typical alignment of C structs on x86
Data structure members are stored sequentially in memory so that, in the structure below, the member Data1 will always precede Data2; and Data2 will always precede Data3:
~~~
struct MyData
{
    short Data1;
    short Data2;
    short Data3;
};
~~~

>If the type "short" is stored in two bytes of memory then each member of the data structure depicted above would be 2-byte aligned. Data1 would be at offset 0, Data2 at offset 2, and Data3 at offset 4. The size of this structure would be 6 bytes.

>The type of each member of the structure usually has a default alignment, meaning that it will, unless otherwise requested by the programmer, be aligned on a pre-determined boundary. The following typical alignments are valid for compilers from Microsoft (Visual C++), Borland/CodeGear (C++Builder), Digital Mars (DMC), and GNU (GCC) when compiling for 32-bit x86:

>A **char** (one byte) will be **1-byte aligned**.

>A **short**(two bytes) will be **2-byte aligned**.

>An **int** (four bytes) will be **4-byte aligned**.

>A **long** (four bytes) will be **4-byte aligned**.

>A **float** (four bytes) will be **4-byte aligned**.

>A **double** (eight bytes) will be **8-byte aligned on Windows** and **4-byte aligned on Linux** (8-byte with -malign-double compile time option).

>A **long long** (eight bytes) will be **4-byte aligned**.

>A **long double** (ten bytes with C++Builder and DMC, eight bytes with Visual C++, twelve bytes with GCC) will be 8-byte aligned with C++Builder, 2-byte aligned with DMC, 8-byte aligned with Visual C++, and **4-byte aligned with GCC**.

>Any **pointer** (four bytes) will be **4-byte aligned**. (e.g.: char*, int*)

>The only notable differences in alignment for an LP64 **64-bit** system when compared to a 32-bit system are:
    A **long** (eight bytes) will be **8-byte aligned**.
    A **double** (eight bytes) will be **8-byte aligned**.
    A **long long** (eight bytes) will be **8-byte aligned**.
    A **long double** (eight bytes with Visual C++, sixteen bytes with GCC) will be 8-byte aligned with Visual C++ and **16-byte aligned with GCC**.
    Any **pointer** (eight bytes) will be **8-byte aligned**.

>Some data types are dependent on the implementation.
Here is a structure with members of various types, totaling 8 bytes before compilation:
~~~c
struct MixedData{
    char Data1;
    short Data2;
    int Data3;
    char Data4;
};
~~~
After compilation the data structure will be supplemented with padding bytes to ensure a proper alignment for each of its members:
~~~c
struct MixedData{  /* After compilation in 32-bit x86 machine*/
    char Data1; /* 1 byte*/
    char Padding1[1]; /* 1 byte for the following 'short' to be aligned on a 2 byte boundary assuming that the address where structure begins is an even number*/
    short Data2; /* 2 bytes*/
    int Data3;  /* 4 bytes - largest structure member*/
    char Data4; /* 1 byte*/
    char Padding2[3]; /* 3 bytes to make total size of the structure 12 bytes*/
};
~~~

>The compiled size of the structure is now 12 bytes. It is important to note that the last member is padded with the number of bytes required so that the total size of the structure should be a multiple of the largest alignment of any structure member (alignment(int) in this case, which = 4 on linux-32bit/gcc)[citation needed].

>In this case 3 bytes are added to the last member to pad the structure to the size of a 12 bytes (alignment(int) × 3).
~~~c
struct FinalPad {
  float x;
  char n[1];
};
~~~
In this example the total size of the structure sizeof(FinalPad) == 8, not 5 (so that the size is a multiple of 4 (alignment of float)).
~~~c
struct FinalPadShort {
  short s;
  char n[3];
};
~~~
In this example the total size of the structure sizeof(FinalPadShort) == 6, not 5 (not 8 either) (so that the size is a multiple of 2 (alignment(short) = 2 on linux-32bit/gcc)).

>It is possible to change the alignment of structures to reduce the memory they require (or to conform to an existing format) by reordering structure members or changing the compiler’s alignment (or “packing”) of structure members.
~~~c
struct MixedData{  /* after reordering*/
    char Data1;
    char Data4;   /* reordered*/
    short Data2;
    int Data3;
};
~~~
The compiled size of the structure now matches the pre-compiled size of 8 bytes. Note that Padding1[1] has been replaced (and thus eliminated) by Data4 and Padding2[3] is no longer necessary as the structure is already aligned to the size of a long word.
