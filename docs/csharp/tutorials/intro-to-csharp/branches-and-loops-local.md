---
title: 'Ramas y bucles: tutorial de introducción a C#'
description: En este tutorial sobre ramas y bucles, escribirá código de C# para explorar la sintaxis del lenguaje que admite ramas y bucles condicionales para ejecutar instrucciones de forma repetida.
ms.date: 10/31/2017
ms.custom: mvc
ms.openlocfilehash: 44b634e3c2120116ee7fd66770398a6b66c8ed8c
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2019
ms.locfileid: "73739129"
---
# <a name="learn-conditional-logic-with-branch-and-loop-statements"></a>Obtenga información sobre la lógica condicional con instrucciones de rama y bucle

En este tutorial se enseña a escribir código que analiza variables y cambia la ruta de acceso de ejecución en función de dichas variables. Escriba código de C# y vea los resultados de la compilación y la ejecución. El tutorial contiene una serie de lecciones en las que se analizan las construcciones de bifurcaciones y bucles en C#. En ellas se enseñan los aspectos básicos del lenguaje C#.

En este tutorial se supone que cuenta con una máquina que puede usar para el desarrollo. El tutorial de .NET [Hola mundo en 10 minutos](https://dotnet.microsoft.com/learn/dotnet/hello-world-tutorial/intro) cuenta con instrucciones para configurar el entorno de desarrollo local en Windows, Linux o macOS. En [Become familiar with the development tools](local-environment.md) (Familiarizarse con las herramientas de desarrollo) puede obtener información general sobre los comandos que usará, donde hay vínculos que amplían la información.

## <a name="make-decisions-using-the-if-statement"></a>Toma de decisiones con la instrucción `if`.

Cree un directorio denominado *branches-tutorial*. Conviértalo en el directorio actual y ejecute el siguiente comando:

```dotnetcli
dotnet new console -n BranchesAndLoops -o .
```

Este comando crea una nueva aplicación de consola de .NET Core en el directorio actual.

Abra *Program.cs* en su editor favorito y reemplace la línea `Console.WriteLine("Hello World!");` por el código siguiente:

```csharp
int a = 5;
int b = 6;
if (a + b > 10)
    Console.WriteLine("The answer is greater than 10.");
```

Pruebe este código escribiendo `dotnet run` en la ventana de la consola. Debería ver el mensaje "The answer is greater than 10" (La respuesta es mayor que 10) impreso en la consola.

Modifique la declaración de `b` para que el resultado de la suma sea menor que diez:

```csharp
int b = 3;
```

Escriba `dotnet run` de nuevo. Como la respuesta es menor que diez, no se imprime nada. La **condición** que está probando es false. No tiene ningún código para ejecutar porque solo ha escrito una de las bifurcaciones posibles para una instrucción `if`: la bifurcación true.

> [!TIP]
> Cuando explore C# o cualquier otro lenguaje de programación, cometerá errores al escribir código. El compilador buscará dichos errores y los notificará. Fíjese en la salida de error y en el código que generó el error. El error del compilador normalmente puede ayudarle a encontrar el problema.

En este primer ejemplo se muestran la potencia de `if` y los tipos booleanos. Un *booleano* es una variable que puede tener uno de estos dos valores: `true` o `false`. C# define un tipo especial `bool` para las variables booleanas. La instrucción `if` comprueba el valor de `bool`. Cuando el valor es `true`, se ejecuta la instrucción que sigue a `if`. De lo contrario, se omite.

Este proceso de comprobación de condiciones y ejecución de instrucciones en función de esas condiciones es muy eficaz.

## <a name="make-if-and-else-work-together"></a>Operaciones conjuntas con if y else

Para ejecutar un código distinto en las bifurcaciones true y false, cree una bifurcación `else` para que se ejecute cuando la condición sea false. Pruebe esto. Agregue las dos últimas líneas del código siguiente a su método `Main` (ya debe tener los cuatro primeros):

```csharp
int a = 5;
int b = 3;
if (a + b > 10)
    Console.WriteLine("The answer is greater than 10");
else
    Console.WriteLine("The answer is not greater than 10");
```

La instrucción que sigue a la palabra clave `else` se ejecuta solo si la condición de prueba es `false`. La combinación de `if` y `else` con condiciones booleanas ofrece toda la eficacia necesaria para administrar una condición `true` y `false` simultáneamente.

> [!IMPORTANT]
> La sangría debajo de las instrucciones `if` y `else` se utiliza para los lectores humanos.
> El lenguaje C# no considera significativos los espacios en blanco ni las sangrías.
> La instrucción que sigue a la palabra clave `if` o `else` se ejecutará en función de la condición. Todos los ejemplos de este tutorial siguen una práctica común para aplicar sangría a las líneas en función del flujo de control de las instrucciones.

Dado que la sangría no es significativa, debe usar `{` y `}` para indicar si desea que más de una instrucción forme parte del bloque que se ejecuta de forma condicional. Los programadores de C# suelen usar esas llaves en todas las cláusulas `if` y `else`. El siguiente ejemplo es igual al que acaba de crear. Modifique el código anterior para que coincida con el código siguiente:

```csharp
int a = 5;
int b = 3;
if (a + b > 10)
{
    Console.WriteLine("The answer is greater than 10");
}
else
{
    Console.WriteLine("The answer is not greater than 10");
}
```

> [!TIP]
> En el resto de este tutorial, todos los ejemplos de código incluyen las llaves, según las prácticas aceptadas.

Puede probar condiciones más complicadas. Agregue el código siguiente a su método `Main` después del código que ha escrito hasta ahora:

```csharp
int c = 4;
if ((a + b + c > 10) && (a == b))
{
    Console.WriteLine("The answer is greater than 10");
    Console.WriteLine("And the first number is equal to the second");
}
else
{
    Console.WriteLine("The answer is not greater than 10");
    Console.WriteLine("Or the first number is not equal to the second");
}
```

El símbolo `==` prueba la *igualdad*. Usar `==` permite distinguir la prueba de igualdad de la asignación, que verá en `a = 5`.

`&&` representa "y". Significa que ambas condiciones deben cumplirse para ejecutar la instrucción en la bifurcación true.  En estos ejemplos también se muestra que puede tener varias instrucciones en cada bifurcación condicional, siempre que las encierre entre `{` y `}`.

También puede usar `||` para representar "o". Agregue el código siguiente antes del que ha escrito hasta ahora:

```csharp
if ((a + b + c > 10) || (a == b))
{
    Console.WriteLine("The answer is greater than 10");
    Console.WriteLine("Or the first number is equal to the second");
}
else
{
    Console.WriteLine("The answer is not greater than 10");
    Console.WriteLine("And the first number is not equal to the second");
}
```

Modifique los valores de `a`, `b` y `c` y cambie entre `&&` y `||` para explorar. Obtendrá más conocimientos sobre el funcionamiento de los operadores `&&` y `||`.

Ha terminado el primer paso. Antes comenzar con la siguiente sección, se va a mover el código actual a un método independiente. Con este paso, resulta más fácil empezar con un nuevo ejemplo. Cambie el nombre del método `Main` por `ExploreIf` y escriba un método `Main` nuevo que llame a `ExploreIf`. Cuando termine, el código debe tener un aspecto similar al siguiente:

```csharp
using System;

namespace BranchesAndLoops
{
    class Program
    {
        static void ExploreIf()
        {
            int a = 5;
            int b = 3;
            if (a + b > 10)
            {
                Console.WriteLine("The answer is greater than 10");
            }
            else
            {
                Console.WriteLine("The answer is not greater than 10");
            }

            int c = 4;
            if ((a + b + c > 10) && (a > b))
            {
                Console.WriteLine("The answer is greater than 10");
                Console.WriteLine("And the first number is greater than the second");
            }
            else
            {
                Console.WriteLine("The answer is not greater than 10");
                Console.WriteLine("Or the first number is not greater than the second");
            }

            if ((a + b + c > 10) || (a > b))
            {
                Console.WriteLine("The answer is greater than 10");
                Console.WriteLine("Or the first number is greater than the second");
            }
            else
            {
                Console.WriteLine("The answer is not greater than 10");
                Console.WriteLine("And the first number is not greater than the second");
            }
        }

        static void Main(string[] args)
        {
            ExploreIf();
        }
    }
}
```

Convierta en comentario la llamada a `ExploreIf()`. De este modo la salida estará menos saturada a medida que trabaje en esta sección:

```csharp
//ExploreIf();
```

El `//` inicia un **comentario** en C#. Los comentarios son cualquier texto que desea mantener en el código fuente pero que no se ejecuta como código. El compilador no genera ningún código ejecutable a partir de comentarios.

## <a name="use-loops-to-repeat-operations"></a>Uso de bucles para repetir las operaciones

En esta sección se usan **bucles** para repetir las instrucciones. Pruebe este código en su método `Main`:

```csharp
int counter = 0;
while (counter < 10)
{
    Console.WriteLine($"Hello World! The counter is {counter}");
    counter++;
}
```

La instrucción `while` comprueba una condición y ejecuta la instrucción o el bloque de instrucciones que aparece después de `while`. La comprobación de la condición y la ejecución de dichas instrucciones se repetirán hasta que la condición sea false.

En este ejemplo aparece otro operador nuevo. El código `++` que aparece después de la variable `counter` es el operador de **incremento**. Suma un valor de uno al valor de `counter` y almacena dicho valor en la variable de `counter`.

> [!IMPORTANT]
> Asegúrese de que la condición del bucle `while` cambia a false mientras ejecuta el código. En caso contrario, se crea un **bucle infinito** donde nunca finaliza el programa. Esto no está demostrado en este ejemplo, ya que tendrá que forzar al programa a cerrar mediante **CTRL-C** u otros medios.

El bucle `while` prueba la condición antes de ejecutar el código que sigue a `while`. El bucle `do` ... `while` primero ejecuta el código y después comprueba la condición. Lo que ocurre con el bucle se muestra en el ejemplo de código siguiente:

```csharp
int counter = 0;
do
{
    Console.WriteLine($"Hello World! The counter is {counter}");
    counter++;
} while (counter < 10);
```

Este bucle `do` y el bucle `while` anterior generan el mismo resultado.

## <a name="work-with-the-for-loop"></a>Operaciones con el bucle for

El bucle **for** se utiliza con frecuencia en C#. Pruebe este código en su método Main():

```csharp
for (int index = 0; index < 10; index++)
{
    Console.WriteLine($"Hello World! The index is {index}");
}
```

Funciona de la misma forma que los bucles `while` y `do` que ya ha usado. La instrucción `for` consta de tres partes que controlan su funcionamiento.

La primera parte es el **inicializador de for**: `int index = 0;` declara que `index` es la variable de bucle y establece su valor inicial en `0`.

La parte central es la **condición de for**: `index < 10` declara que este bucle `for` debe continuar ejecutándose mientras que el valor del contador sea menor que diez.

La última parte es el **iterador de for**: `index++` especifica cómo modificar la variable de bucle después de ejecutar el bloque que sigue a la instrucción `for`. En este caso, especifica que `index` debe incrementarse en uno cada vez que el bloque se ejecuta.

Experimente con estas partes por su cuenta. Pruebe todos los pasos siguientes:

- Cambie el inicializador para que se inicie en un valor distinto.
- Cambie la condición para que se detenga en un valor diferente.

Cuando haya terminado, escriba algo de código para practicar con lo que ha aprendido.

## <a name="combine-branches-and-loops"></a>Combinación de ramas y bucles

Ahora que ya ha obtenido la información sobre el bucle `if` y las construcciones de bucles con el lenguaje C#, trate de escribir código de C# para obtener la suma de todos los enteros de uno a veinte que se puedan dividir entre tres.  Tenga en cuenta las siguientes sugerencias:

- El operador `%` proporciona el resto de una operación de división.
- La instrucción `if` genera la condición para saber si un número debe formar parte de la suma.
- El bucle `for` puede facilitar la repetición de una serie de pasos para todos los números comprendidos entre el uno y el veinte.

Pruébelo usted mismo. Después, revise cómo lo ha hecho. Debe obtener 63 como respuesta. Puede ver una respuesta posible mediante la [visualización del código completado en GitHub](https://github.com/dotnet/samples/tree/master/csharp/branches-quickstart/Program.cs#L46-L54).

Ha completado el tutorial "Bifurcaciones y bucles".

Puede continuar con el tutorial [Matrices y colecciones](arrays-and-collections.md) en su propio entorno de desarrollo.

Puede obtener más información sobre estos conceptos en los temas siguientes:

- [Instrucciones If y else](../../language-reference/keywords/if-else.md)
- [Instrucción while](../../language-reference/keywords/while.md)
- [Instrucción do](../../language-reference/keywords/do.md)
- [Instrucción for](../../language-reference/keywords/for.md)
