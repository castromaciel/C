# programación - 2023

## Tabla de cont;enidos

2. [Unidad 0 - algoritmos](#algoritmos)22. [Unidad 1 - programación](#programación);
...
default:
  sentencias;
  break;
3. [Unidad 2 - lenguajes de programación](#lenguajes-de-programación)
4. [Unidad 3 - tipos de datos](#tipos-de-datos)

## Algoritmos

### ¿Qué es un algoritmo?

Un algoritmo es una descripción de la forma en la que se debe llevar a cabo una tarea o proceso, tiene una serie finita de pasos (Un comienzo y un fin).

El diseño del algoritmo se realiza usando PSEUDOCÓDIGO.

- Neutro: Es independiente al lenguaje a utilizar.
- Completo: Permite expresar cualquier idea computacional.

### Características del pseudocódigo

Cada algoritmo tiene:

- Un nombre que indica la tarea que resolverá
- Puede tener o no una entrada (Datos que necesitamos que el usuario ingrese)
- Tiene una salida (Datos que devuelve nuestro programa)
- Toda entrada se debe **LEER**. (Todos los datos "ingresados" por los usuarios se deben leer)
- Se puede asignar valores a las variables.
- Toda salida se debe **ESCRBIR**: (Todos los datos que obtenemos se deben "mostrar")
  \*Para indicar el final de un algoritmo, utilizamos **PARAR**

### Técnicas de diseño de algoritmos

- El proceso de adicionar más detalles a una solución de un problema se conoce como **REFINAMIENTO SUCESIVO.**

- El método **DIVIDE AND CONQUER** con la que se aborda un problema tiene la característica de ser una técnica **TOP-DOWN**. (Es una estrategia que permite descomponer un problema largo y complejo en subproblemas mas pequeños y fáciles de resolver).

#### Ejemplo 1:

La modalidad de pago de la factura de luz en una cierta ciudad es la siguiente: se establece una tarifa mensual para el consumo mínimo (hasta los 100 kwh) de $1200. Si se ha sobrepasado dicho consumo, se suma una tarifa de $125 por cada kwh adicional; pero si está vencida la factura, la tarifa que se usa ya no es de $125 sino de $210. Además en cualquier caso se hace un descuento del 5% al monto total, por pago de contado. Diseñe un algoritmo con niveles de refinamiento, que determine cuánto debe pagar cada cliente. Pruebe la misma para un número indefinido de clientes.

```
ALGORITMO: PAGO_LUZ
ENTRADAS:
  consumo: real,
  estaVencida: entero (0: no / 1: si),
  cliente: entero positivo,
  metodoDePago: entero (0: tarjeta / 1: contado),

SALIDA:
  importe: real

VAR. AUXILAR:
  excede: real

A1. LEER (cliente)
A2. calcular_importe
A3. PARAR
```

```
A2. calcular_importe
  MIENTRAS (cliente > 0)
    LEER(consumo, metodoDePago, estaVencida)

    SI (consumo <= 100) ENTONCES
      importe <- 1200
    SINO
      excede <- consumo - 100
      SI (estaVencida = 1) ENTONCES
        importe<- 1200 + excede * 210
      SINO
        importe<- 1200 + excede * 125
      FIN SI
    FIN SI

    SI (metodoDePago = 1) ENTONCES
      importe <- importe - (importe * 0.05)
    FIN SI

    ESCRIBIR (importe)
    LEER (cliente)
  FIN MIENTRAS
```

**[⬆ Volver arriba](#tabla-de-contenidos)**

## Programación

### El proceso de programación

- ¿Como se resuelve un problema del mundo real con una computadora?

- ¿Como se expresa la solución al problema planteado?

- ¿Como se reduce la complejidad de los problemas?

El programador debe realizar algunos procesos intelectuales.

```mermaid
  flowchart LR
    Model["Modelización
    del problema"]
    Especification["Especificación
    del problema"]
    Expression["Expresión de soluciones
    ejecutables en la computadora"]

    Abstracción --> Model
    Model --> Especification
    Especification --> Expression
```

#### Abstracción

Interpretar los aspectos esenciales de un problema y expresarlo en términos **precisos**.

#### Modelización del problema

Simplificar su expresión encontrando sus aspectos principales, los datos que se deben procesar y el contexto.

#### Especificación del problema real

Se deben determinar en forma clara y concreta el objetivo que se desea.

Por ejemplo el Algoritmo de la [unidad 0](#ejemplo-1)

```
ALGORITMO: PAGO_LUZ
ENTRADAS:
  consumo: real,
  estaVencida: entero (0: no / 1: si),
  cliente: entero positivo,
  metodoDePago: entero (0: tarjeta / 1: contado),

SALIDA:
  importe: real

VAR. AUXILAR:
  excede: real

A1. LEER (cliente)
A2. calcular_importe
A3. PARAR
```

```
A2. calcular_importe
  MIENTRAS (cliente > 0)
    LEER(consumo, metodoDePago, estaVencida)

    SI (consumo <= 100) ENTONCES
      importe <- 1200
    SINO
      excede <- consumo - 100
      SI (estaVencida = 1) ENTONCES
        importe<- 1200 + excede * 210
      SINO
        importe<- 1200 + excede * 125
      FIN SI
    FIN SI

    SI (metodoDePago = 1) ENTONCES
      importe <- importe - (importe * 0.05)
    FIN SI

    ESCRIBIR (importe)
    LEER (cliente)
  FIN MIENTRAS
```

#### Expresión de soluciones ejecutables en la PC

Realizar una solución ejecutable en una computadora usando un lenguaje de programación.

```C
/** Aqui se colocará la solución en lenguaje C*/
#include <stdio.h>

int main()
{

  return 0
}
```

### Etapas de resolución de problemas

```mermaid
  flowchart LR
    Analysis["Análisis
    del problema"]
    Design["Diseño de
    la solución"]
    Especific["Especificación
    del algoritmo"]
    Program["Escrituras
    de programas"]
    Test["Verificación"]

    Analysis --> Design
    Design --> Especific
    Especific --> Program
    Program --> Test
```

#### Análisis del problema

##### La importancia del contexto:

La definición del contexto es importante para analizar y diseñar la solución usando computadoras.

Impone restricciones y consideraciones.

#### Diseño de la solución

##### Descomposición - Modularización:

Se usará la metodología top-down (arriba-abajo) de descomposición de problemas para desarrollar el sistema de software.

Se obtendrán módulos que deberán estar ligados entre si para obtener la solución final.

#### Especificación del algoritmo

- Cada uno de los módulos deberá tener su propio algoritmo.

- La elección del algoritmo es importante, dado que de ella depende la eficiencia de la solución.

#### Escritura de programas

Un algoritmo es una especificación simbólica que debe convertirse a programa real sobre un lenguaje de programación concreto. (Ya sea C, pytho, JavaScript, etc.)

Programar no es lo mismo que codificar. La programación se trata de desarrollar una aplicación o máquina completa; mientras que la codificación trata de **traducir** un lenguaje a uno que una máquina pueda entender.

#### Verificación

Antes de dar por finalizada cualquier labor de programación, es fundamental preparar un conjunto de datos representativos del problema que permiten probar el programa cuando se ejecute, y así verificar los resultados. Para esto se realizan:

- Pruebas (testing)
- Depuración
- Alternativas de diseño y estilo.

> **Importante! :** Cuanto mas exhaustivas sean las pruebas, mayor seguridad se tendrá que el funcionamiento del programa es correcto, por lo tanto menor posibilidad de errores.

##### Verificación: Corrección, prueba y optimización

- **Los errores de ejecución:** Afectan la operación normal del programa. Son originados por el usuario (Proporcionar datos incorrectos, formato diferente al esperado, etc).

- **Errores de tipo logico:** Derivan de un mal diseño de los algoritmos, como ser: bucle infinito, resultados incorrectos, etc.

- **Errores de sintaxis:** Se generan por no cumplicar con las "normas" de escritura de un lenguaje, como ser: falta o mal uso de elementos separadores (comas(,), puntos y comas (;)) o incluso palabras mal escritas.

#### Documentación

Documentación interna:

- Tabulación en el código.
- Uso de los comentarios.

Documentación externa:

- Para el usuario.
- Para el programador.

### Conclusión

Un programador debe asociar inmediatamente el proceso de desarrollo de software con el proceso de refinamiento y abstracción que abarca desde el problema real hasta su solución algorítmica con un lenguaje de programación

**[⬆ Volver arriba](#tabla-de-contenidos)**

## Lenguajes de programación

### Definición de lenguaje

Es el sistema a través del cual el hombre comunica sus ideas, sentimientos, ya sea a través del habla, la escritura u otros signos.

### Lenguaje de programación

Un **Lenguaje de programación** es un lenguaje formal que proporciona una serie de instrucciones que permiten a un programador escribir secuencias de órdenes y algoritmos a modo de poder controlar el comportamiento físico y loógico de una computadora.

A todo este conjunto de órdenes y datos escritos mediante un lenguaje de programación, se le conoce como programa.

### Tipos de lenguajes

La máquina sólo entiende un lenguaje conocido como código binario o código máquina, consiste en ceros y unos. Es decir solo utiliza 0 y 1 para codificar cualquier acción.

**Existen dos tipos de lenguajes claramente diferenciados:**

- **Lenguaje de bajo nivel:** Son los más próximos a la arquitectura hardware.

- **Lenguaje de alto nivel:** Son aquellos que se encuentran más cercanos a los programadores y usuarios.

#### Lenguajes de bajo nivel 🤿:

Son lenguajes totalmente dependientes de la máquina, es decir que el programa que se realiza con este tipo de _lenguajes no se pueden migrar o utilizar en otras maquinas_.

Al estar prácticamente diseñados a medida del hardware, aprovechan al máximo las características del mismo.

Dentro de los lenguajes de bajo nivel se encuentran **El lenguaje maquina**, que consiste en combinaciones de 0's y 1;s para formar ordenes entendibles por el hardware de la máquina. Son mucho más rápidos, pero dificiles de manejar.

Por otro lado se encuentra el _Lenguaje ensamblador_, el cual es un derivado del lenguaje maquina y está formado por abreviaturas de letras y números llamados mnemotécnicos. Como ventaja respecto al código máquina es que los códigos fuentes son más cortos y los programas ocupan menos memoria. Pero al igual que antes, son dificiles de probar y mantener.

#### Lenguajes de alto nivel 🗻:

Son aquellos que se encuentran más cercanos al lenguaje natural que al lenguaje máquina. **_Se tratan de lenguajes independientes de la arquitectura del ordenador._** Por lo que un programa escrito en lenguajes de alto nivel se pueden migrar entre máquinas sin ningún problema.

También permiten al programador olvidarse del funcionamiento interno de la máquina, dado que solo necesitan un "traductor" que entienda el código fuente como las características de la máquina.

#### ¿Podemos llamar HTML como lenguaje de programación?

La respuesta es un retundo NO.

HTML es un lenguaje de etiquetas (tag) que comunican al navegador cuál es la información a mostrar por pantalla.

### La programación estructurada

Es un paradigma de programación orientado a mejorar la claridad, calidad y tiempo de desarrollo de un programa de computadora.

Propone segregar los procesos en estructuras elementales:

- Secuencia
- Selección
- Iteración

### Lenguaje C

Los laboratorios Bell lo desarrollaron a principios de la decada del 70.
Los autores son Brian Kernighan y Dennis Ritchie.

El objetivo de su creación fue para que los programadores de Bell pudieran redactar su sitema operativo UNIX para una nueva computadora.

Debido a que los otros lenguajes de alto nivel existentes en aquel tiempo (COBOL, FORTRAN, etc), eran demasiados lentos para ser utilizados en la codificación de un sistema operativo. Los programadores de laboratorios Bell decidieron desarrolla su propio lenguaje, basado en Algol y BCPL, dos eficientes lenguajes de alto nivel.

#### Características de C

- Es un lenguaje para la programación estructurada
- Es tipificado
- Contiene muy pocas palabras reservadas
- No contiene órdenes para trabajar con objetos compuestos (cadenas, registros, etc)
- Distingue entre mayúsculas y minúsculas

#### Ventajas

- Es el lenguaje más portado en la existencia, habiendo compiladores para casi todos los sistemas conocidos.
- Proporciona facilidades para realizar programas modulares y/o utilizar código o bibliotecas existentes.
- Lenguaje flexible, veloz y potente.
- Posibilita programación estructurada o modular.
- Acceso a memoria de bajo nivel mediante el uso de punteros.

#### Desventajas

- No tiene instrucciones propias para la asignación dinámica de memoria, ni instrucciones de entrada/salida.
- Se requiere más tiempo en conseguir el ejecutable, por que cada vez se compila todo el fichero.
- No dispone de sistemas de control automáticos y la seguridad depende casi exclusivamente de la experiencia del programador.

### En un programa intervienen

- Ordenes para el preprocesador
- Variables
- Constantes
- Aritmética
- Funciones
- Funciones de entrada y salida
- Comentarios

#### Ordenes para el preprocesador

Conceptualmente es un paso previo a la compilación, las pasa usadas son:
`#include`, `#define`. Se utiliza para inclusión de archivos.

```mermaid
stateDiagram
  direction LR
    s1 : Código fuente (.c)
    s2 : Ficheros de cabecera (.h)
    s3 : Código objeto (.o)

    s1 --> Compilacion
    s2 --> Compilacion

    state Compilacion {
      direction LR
        Preprocesador --> Compilador
    }

    Compilacion --> s3
```

#### Funciones

**_Un programa escrito en código C es una reunión de funciones._**

**main**: Función principal, debe estar presente en todos los programas escritos en C. Puede invocar a otras funciones.

- Un método para comunicar datos entre las funciones, es a través de argumentos.
- Las paréntesis después del nombre, están para encerraar una lista de valores que serán argumentos.
- Puede ocurrir que una función esté definida para no esperar argumentos.

#### Funciones de entrada y salida

La biblioteca stándar `stdio.h` provee al programador una extensa gama de funciones para lectura y escritura. Es necesario escribir una orden para el preprocesador para usar dichas funciones.

```C
#include <stdio.h>

int main()
{
  int num;
  printf("Ingrese un numero");
  scanf("%d", &num);
  printf("El numero ingresado fue %d", num);

  return 0;
}
```

#### Variables y constantes

- Son objetos sobre los que actúan las instrucciones que componen el programa.
- Deben ser declaradas.
- Deben tener un identificador asociado.
- El 1º caracter debe ser una letra.
- Debe indicarse el tipo de dato.
- Las variables pueden inicializarse de forma grupal.
- Las constantes se definen en una línea `#define`, que es una directiva del preprocesador.

  Por ej: `#define MAX 100`

- Las constantes pueden ser enteras, reales y de carácter.

#### Aritmética

- Interacción entre los operadores aritméticos y las variables y/o constantes declaradas (si el tipo es numérico).
- El tipo de operación permitido está ligado con el _tipo de dato_ con que fue declarada la variable y/o constante.
- Tipos de datos básicos: `int`,`float`,`char`,`short`,`long`,`double`.

#### Comentarios

Dos modos de comentar las acciones del código escrito:

```C
// Comentarios de una sola línea

/* Comentarios
  de varias
  lineas
*/
```

**[⬆ Volver arriba](#tabla-de-contenidos)**

### Compilador

El compilador para C del proyecto GNU se llama "gcc" y su nombre proviene de "GNU C Compiler" (O GNU Collection Compiler).

Un compilador, es un programa informático que traduce un programa de un lenguaje a otro, generando un lenguaje equivalente que la máquina será capaz de interpretar.

Este proceso de traducción se conoce como compilación.

### Código Fuente

El compilador gcc es capaz de compilar cualquier programa en lenguaje C, escrito en un archivo de texto convencional. Este archivo lleva el sufijo ".c" para identificar que su contenido corresponde al código de un programa escrito en lenguaje C.

Actualmente existen herramientas más especificas para escribir y editar código fuente de manera más eficaz que un simple editor de texto.

### Compilando un programa en C

```bash
gcc -Wall holaMundo.c -o holaMundo
```

El comando anterior compila el código fuente a código máquina y lo almacena en archivo ejecutable.

**_-Wall:_** Opción para activar las advertencias del compilador.

**_-o:_** Permite especificar el archivo de salida. Si este se omite, se crea uno por defecto 'a.exe'.

**_holaMundo.c:_** nombre del archivo fuente

**_holaMundo:_** nombre del archivo fuente

### Etapas de compilación

Cuando invocamos el comando `gcc`, normalmente se realizan los un **preprocesamiento**, **compilación**, **ensamblado** y **enlazado**.

Cada etapa tiene un código fuente como entrada y un código objeto como resultado. El codigo de las etapas intermedias sirve de fuente para la siguiente. Para las etapas, utilizaremso el siguiente ejemplo

#### Ejemplo 2:

```C
/** circulo.c */
#include <stdio.h>
#define PI 3.1416

int main()
{
  float area, radio;
  printf("Ingresar el radio del circulo: ");
  scanf("%f", &radio);
  area = PI * (radio * radio);
  printf("Area del circulo = %.2f", area);

  return 0
}
```

#### Preprocesamiento

Es realizado por el preprocesador. Esta primera etapa traduce el archivo fuente que es una forma apliada del lenguaje.

```sh
gcc -E circulo.c -o circulo.i
```

Luego del preprocesamiento, es posible ver en el archivo _circulo.i_, que la constante simbólica **PI**, definida con la directiva del preprocesador `#define`, es sustituida por su valor en todos los lugares donde aparece.

En esta etapa, se resuelven todas las directivas del preprocesador que aparezcan en el código fuente.

##### Opciones que se usaron para preprocesar el archivo de código fuente:

- **-E:** Opción para detener el proceso de compilación luego de realizado el preprocesamiento. La salida es en la forma de un archivo preprocesado. Los archivos que no requieren preprocesamiento son ignorados.
- **-o:** Opción para especificar el archivo de salida.
- **circulo.c:** Nombre del archivo de entrada a ser preprocesado.
- **circulo.i::** Nombre del archivo de salida. Se utiliza el sufijo _".i"_ para identificar a los archivos preprocesados.

#### Compilación

La compilación transforma el código C preprocesado en el lenguaje ensamblador propio del procesador de nuestra máquina.

```sh
gcc -S circulo.c
```

Con este comando se realizan las dos primeras etapas y se crea un archivo _"circulo.s"_.

- **-S:** Opción para detener luego de realizada la etapa de compilación, no realiza la etapa de ensamblado. La salida es en forma de código _assembly_.
- **circulo.c:** Nombre del archivo de entrada para ser compilado.

#### Ensamblado

Se traduce el programa escrito en lenguaje _assembly_, de la etapa anterior, a código binario en lenguaje de maquina entendible por el procesador.

```sh
gcc -c circulo.c
```

Con este comando se realizan las tres primeras etapas, creando el archivo _"circulo.o"_. Este archivo contiene código binario listo para ser enlazado en la próxima etapa.

- **-c:** Opción para detener luego de realizada la etapa de ensamblado.

#### Enlazado

Las funciones como `printf`, se encuentran compiladas y ensambladas en librerías existentes. Para que el archivo resultado del proceso de compilación completo sea ejecutable, es necesario incorporar el código binario de estas funciones en el lenguaje final.

```sh
gcc circulo.c -o circulo
```

Esta es la línea de comando que comúnmente se usará al compilar un archivo en C para obtener un archivo ejecutable.

**[⬆ Volver arriba](#tabla-de-contenidos)**

## Tipos de Datos

- Los lenguajes de alto nivel permiten hacer abstracciones e ignorar los detalles de la representación interna (propios de la máquina), usando el concepto de **_tipos de datos._**

  Así la información almacenada en memoria no es tratada como una secuencia de bits, si no, como valores enteros, reales, carácter, etc.

- Podemos clasificarlos en dos grandes grupos: datos simples y compuestos.

### Tipos de Datos Simples

Los especificadores de tipo de dato, determinan el tipo de dato o elemento de informacio4n que contendrá _el área de memoria reservada para las variables declaradas_ por medio de la declaración en proceso.

| Tipo                           | Palabra reservada |
| :----------------------------- | :---------------: |
| Carácter                       |       char        |
| Entero de longitud estándar    |        int        |
| Entero de longitud grande      |     long int      |
| Entero de longitud pequeña     |     short int     |
| Entero sin signo               |     unsigned      |
| Punto flotante (real)          |       float       |
| Punto flotante doble precisión |      double       |

#### Variables

Una variable es un objeto cuyo valor cambia durante la ejecución del programa. Tiene un _nombre_ y ocupa una cierta _posición de memoria_.

**_Todas las variables que se usan deben ser declaradas._** La declaración de la misma, se hace usando una **palabra reservada** del lenguaje. Por ejemplo, **int** es la palabra reservada que le avisa al compilador que la variable con la que se va a trabajar es de tipo entero.

Una palabra reservada es una palabra con significado especifico, predefinido por el lenguaje que se usará.

#### Constantes simbólicas

Una forma de evitar el uso de _"números mágicos"_, que aparecen en nuestro código sin ninguna explicación, es dándoles nombres significativos. una línea `#define`, define una constante simbólica. Por ejemplo:

```C
#define MAX 200
```

#### Entradas y salidas básicas.

- C no tiene instrucciones de entrada ni salida.
- El lenguaje C interpreta que la entrada proviene de stdin (dispositivo estándar de entrada).
- La salida es dirigida a la stdout (dispositivo estándar de salida).
- Ambos pueden redirigrse a otros dispositivos.

#### Función de salida: printf

Permite la presentación de valores numéricos, caracteres y cadenas de texto por el archivo estándar de salida (pantalla).

`printf(control, arg1, arg2...)`

**Control:** Aquí se indica la forma en la que se mostrarán los argumentos posteriores (Si los hubiere) y también se pueden escribir cadenas de texto (sin argumentos), o combinar ambas posibildades, así como secuencias de escape.

**args:** argumentos cuyos valores serán mostrados en la línea de salida. Si se utilizan argumentos, se debe indicar en la cadena de control, tantos caracteres de conversión (o modificadores) como argumentos se van a presentar.

#### Listado de modificadores

| Modificador | Detalle                                           |
| :---------: | ------------------------------------------------- |
|  **_%c_**   | Un único carácter \*                              |
|  **_%d_**   | Un entero con signo, en base decimal \*           |
|     %u      | Un entero sin signo, en base decimal              |
|     %o      | Un entero en base octal                           |
|     %x      | Un entero en base hexadecimal                     |
|     %e      | Un número real en coma flotante, con exponente    |
|  **_%f_**   | Un número real en coma flotante, sin exponente \* |
|     %s      | Una cadena de caracteres                          |
|     %p      | Un puntero o dirección de memoria                 |

> El formato completo de los modificadores es del tipo:
>
> `%[signo][longitud][.precisión][I/L]conversión`

- **Signo:**

  - **-:** Indica si el valor se ajustará a la izquierda.
  - **+:** Establece que el número siempre será impreso con signo.

- **longitud:** Especifica un ancho mínimo de campo. Si tiene menos caráccteres que el ancho de campo, será rellenado a la izquierda (normalmente con espacios).

- **precisión:** Indica el número máximo de decimales que tendra el valor.

- **I/L:** Utilizamos I cuando se trata de una variable de tipo long, y L cuando es de tipo double.

#### Secuencias de escape

Las secuencias de escape permiten expresar ciertos caracteres no imprimibles, a través de la combinación adecuada de algunos caracteres alfabéticos.

| Nombre                 | Secuencias de escape |
| :--------------------- | :------------------: |
| Nulo                   |          \0          |
| Retroceso              |          \b          |
| Tabulador              |          \t          |
| Salto de línea         |          \n          |
| Salto de página        |          \f          |
| Retorno de carro       |          \r          |
| Comillas               |         \\"          |
| Signo de interrogación |         \\?          |
| Barra invertida        |         \\\          |

#### Función de entrada: scanf

Permite ingresar la información o datos en posiciones de memoria a traves del archivo estándar de entrada (teclado).

`scanf(control, arg1, arg2...)`

**Control:** cadena de control que indica los modificadores que haran referencia al tipo de dato de los argumentos.

**args:** son los nombres o identificador es de los argumentos de entrada cuyos valores se incorporarán por teclado.

**_scanf_** "necesita conocer" la posición de la memoria en que se encuentra la variable para poder almacenar la informacio4n ingresada. Por eso se utiliza un operador unario de direción \*\*&(ampersand), que se coloca delante del nombre de cada variable.

`scanf("%d %d %d", &var1, &var2, &var3)'`

Si no se indica cual es la dirección interna de estas variables (la posición de memoria), el programa no podrá acceder luego a los valores tipiados desde el teclado.

```C
#include <stdio.h>

int main()
{
  char letra;

  scanf("%c", &letra);
  printf("%c", letra);

  return 0
}
```

### Datos

Podemos definir **dato** como una expresio4n general que describe los objetos con los cuales opera una computadora. A nivel hardware son representados como "tiras de bits" y son manejados por instrucciones propias del procesador.

Vovliendo a los [Tipos de Datos Simples](#tipos-de-datos-simples), son caracterizados por que sus componentes no se pueden descomponer en tipos más simples, es decir representan valores atómicos. Por ejemplo: entero, carácter.

```C
#include <stdio.h>

int main()
{
  printf("El tamanio de int es: %zu bytes\n", sizeof(int));
  printf("El tamanio de float es: %zu bytes\n", sizeof(float));
  printf("El tamanio de double es: %zu bytes\n", sizeof(double));
  printf("El tamanio de char es: %zu bytes\n", sizeof(char));

  return 0;
}
```

El `%zu` es un especificador para imprimir valores de tipo size_t.

size_t es un tipo de dato sin signo, que se utiliza comunmente para represntar tamaños de objetos o índices de arrglos.

El resultado por consola es el siguiente

```
El tamanio de int es: 4 bytes
El tamanio de float es: 4 bytes
El tamanio de double es: 8 bytes
El tamanio de char es: 1 bytes
```

#### Tipos de dato entero: tamaño, calificadores

**¿Cómo saber los valores que puede asumir una variable `int`?**

```C
#include <stdio.h>
#include <limits.h> // Biblioteca

int main()
{
  printf("Rango de representación de int: %d a %d\n", INT_MIN, INT_MAX);

  return 0;
}
```

```
Rango de representación de int: -2147483648 a 2147483647
```

Esta representación tiene que ver con la forma en que la máquina almacena los números (en forma binaria). El rango se calcula como $[-2^{(n-1)}, 2^{(n-1)} - 1]$

##### Calificadores

Existen algunos calificadores que se aplican a los tipos básicos. Sirve para proporcionar diferentes longitudes de enteros donde sea práctico.

```C
#include <stdio.h>
#include <limits.h>

int main()
{
  printf("Rango de representacion de int %d a %d\n", INT_MIN, INT_MAX);
  printf("Rango de representacion de short int %d a %d\n", SHRT_MIN, SHRT_MAX);
  printf("Rango de representacion de long int %ld a %ld\n", LONG_MIN, LONG_MAX);
}
```

El resultado por consola es el siguiente

```
Rango de representacion de int -2147483648 a 2147483647
Rango de representacion de short int -32768 a 32767
Rango de representacion de long int -9223372036854775808 a 9223372036854775807
```

Los números **unsigned** son siempre positivos o cero, obedecen al módulo $2^n$, con n número de bits. Los números **signed** pueden asumir valores menores

#### Tipos de dato float y double: tamaño, calificadores

El tipo float es un punto flotante de precisión normal, mientras que el tipo double es de precisión extendida.

> float < double < long double

Rango de valores posibles para float

```C
#include <stdio.h>
#include <float.h>

int main()
{
  printf("Valor minimo de float: %e\n", FLT_MIN);
  printf("Valor maximo de float: %e\n", FLT_MAX);

  return 0;
}
```

El resultado por consola es el siguiente

```
Valor minimo de float: 1.175494e-38
Valor maximo de float: 3.402823e+38
```

#### Operadores

##### Relacionales

|  C  | Descripción   |
| :-: | ------------- |
|  >  | Mayor         |
| >=  | Mayor o igual |
|  <  | Menor         |
| <=  | Menor o igual |
| ==  | Igual         |
| !=  | Diferente     |

##### Lógicos

|  C  | Descripción        |
| :-: | ------------------ |
| &&  | And, y, conjunción |
| ll  | Or, o, disyunción  |
|  !  | Not, no, negación  |

> Las ll representan el operador or ||

##### Asignación

|  C  | Descripción |
| :-: | ----------- |
|  =  | Asignación  |

##### Lógicos

|  C  | Descripción           |
| :-: | --------------------- |
|  +  | Suma                  |
|  -  | Resta                 |
| \*  | Producto              |
|  /  | Cociente              |
|  %  | Resto división entera |

##### Prioridades de Operadores

| Prioridad | Operadores     |
| --------- | -------------- |
| Más Alta  | ()             |
|           | !              |
|           | \* / %         |
|           | < <= > >=      |
|           | == !==         |
|           | &&             |
|           | ll             |
| Más baja  | = += -= \*= /= |

> Las ll representan el operador or ||

#### Conversiones y asignació para los tipos numéricos

En una expresión, cuando un operador tiene operandos de distintos tipos, ambos se conviernte a un tipo común. En general las conversiones son de tipo angosto a un tipo ancho sin pérdida de información.

`int < float < double < long double`

`operando1 = operando2`

Si son de distinto tipo, el `operando2` se convierte al tipo del operando 1.

`i = 34.567;` -> `i = 34;`

```C
#include <stdio.h>

int main()
{
  int entero;
  entero = 34.567;
  printf("El numero es: %d", entero);
  return 0;
}
```

El resultado por consola es el siguiente

```
El numero es: 34
```

**_El valor del punto flotante se trunca si se asigna a una variable entera._**

Ahora, si j es de tipo float:

`j = i + 100;`
`j = 34 + 100;`
`j = 134.00000;`

**_Los enteros se convierten a flotante._**

#### El operador ternario: ？

```C
#include <stdio.h>

int main()
{
  int num1 = 145, num2 = 56;
  int resultado;

  resultado = (num1 > num2) ? num1 : num2;
  printf("Resultado = %d", resultado);

  return 0;
}
```

#### Estructura de selección

En el lenguaje C se dispone de sentencias condicionales `if-else`, `switch` que permiten seleccionar una única alternativa entre varias para ser ejecutada.

Su equivalente en diseño de algoritmos es la estructura Si-sino:

```
SI condición ENTONCES
  Accion 1;
SINO
  Accion 2;
FIN SI
```

#### Sentencia if-else

Esta sentencia permite sleccionar el grupo de sentencias o bloques que serán ejecutados, de acuerdo al valor de una condición:

```C
if(expression)
{
  proposition1;
} else {
  proposition2;
}
```

**Expresión:** va entre ( ) y tiene que ser evaluada como VERDADERA (distinta de cero) o FALSO (Cero).

**Proposición:** puede ser simple o compuesta { }. 

Ejemplo 3:

Escribir un algoritmo que lea un carácter y determine si es consonante en minúsculas o no. Usar código ASCII.

```C
#include <stdio.h>

int main()
{
  char letra;

  printf("Ingrese una letra: ");
  scanf("%c", &letra);

  if (letra == 97 || letra == 101 || letra == 105 || letra == 111 || letra == 117)
  {
    printf("Es vocal");
  } else {
    printf("Es consonante");
  }

  return 0;
}
```

#### Sentencia Switch

**Expresión:** puede ser una expresión, un carácter alfanumérico, una constante o una variable.

**Const.:** caso o valores con el que se va a comparar la expresión.

**Sent.:** puede ser cualquier bloque de sentencias en C.

**default:** Es opcional, se usa cuando se estima que el case predeterminado va a ocurrir con mayor frecuencia.

**break:** Provoca una salida inmediata del switch. Los case solo sirven como etiquetas. Las formas más comunes de salir de un switch son **break** y **return.**

```C
switch(expression)
{
  case const1:
    sent1;
    break;
  case const2:
    sent2;
    break;
  ...
  default:
    sentencias;
    break;
}
```

**[⬆ Volver arriba](#tabla-de-contenidos)**
