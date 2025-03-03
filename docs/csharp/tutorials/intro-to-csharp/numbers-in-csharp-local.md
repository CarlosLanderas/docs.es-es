---
title: 'Números en C#: tutorial de introducción a C#'
description: Obtenga información sobre C# mediante la exploración de tipos numéricos, sus propiedades y métodos.
ms.date: 10/31/2017
ms.custom: mvc
ms.openlocfilehash: a06bc57e5c979b62e19407747cb2c8a2447ca114
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2019
ms.locfileid: "73739140"
---
# <a name="manipulate-integral-and-floating-point-numbers-in-c"></a>Manipular números enteros y de punto flotante en C\#

En este tutorial se explican los tipos numéricos en C# de manera interactiva. Escribirá pequeñas cantidades de código y luego compilará y ejecutará ese código. El tutorial contiene una serie de lecciones que ofrecen información detallada sobre los números y las operaciones matemáticas en C#. En ellas se enseñan los aspectos básicos del lenguaje C#.

En este tutorial se supone que cuenta con una máquina que puede usar para el desarrollo. El tutorial de .NET [Hola mundo en 10 minutos](https://dotnet.microsoft.com/learn/dotnet/hello-world-tutorial/intro) cuenta con instrucciones para configurar el entorno de desarrollo local en Windows, Linux o macOS. En [Become familiar with the development tools](local-environment.md) (Familiarizarse con las herramientas de desarrollo) puede obtener información general sobre los comandos que usará, donde hay vínculos que amplían la información.

## <a name="explore-integer-math"></a>Análisis de las operaciones matemáticas con enteros

Cree un directorio denominado *numbers-quickstart*. Conviértalo en el directorio actual y ejecute el siguiente comando:

```dotnetcli
dotnet new console -n NumbersInCSharp -o .
```

Abra *Program.cs* en su editor favorito y reemplace la línea `Console.WriteLine("Hello World!");` por lo siguiente:

```csharp
int a = 18;
int b = 6;
int c = a + b;
Console.WriteLine(c);
```

Ejecute este código escribiendo `dotnet run` en la ventana de comandos.

Ya ha visto una de las operaciones matemáticas fundamentales con enteros. El tipo `int` representa un **entero**, que puede ser cero o un número entero positivo o negativo. Use el símbolo `+` para la suma. Otros operadores matemáticos comunes con enteros son:

- `-` para resta
- `*` para multiplicación
- `/` para división

Comience por explorar esas operaciones diferentes. Agregue estas líneas después de la línea que escribe el valor de `c`:

```csharp

// subtraction
c = a - b;
Console.WriteLine(c);

// multiplication
c = a * b;
Console.WriteLine(c);

// division
c = a / b;
Console.WriteLine(c);
```

Ejecute este código escribiendo `dotnet run` en la ventana de comandos.

Si lo desea, también puede experimentar con la realización de varias operaciones matemáticas en la misma línea. Pruebe `c = a + b - 12 * 17;` por ejemplo. Se permite la combinación de variables y números constantes.

> [!TIP]
> Cuando explore C# o cualquier otro lenguaje de programación, cometerá errores al escribir código. El **compilador** buscará dichos errores y los notificará. Si la salida contiene mensajes de error, revise detenidamente el código de ejemplo y el código de la ventana para saber qué debe corregir.
> Este ejercicio le ayudará a aprender la estructura del código de C#.

Ha terminado el primer paso. Antes comenzar con la siguiente sección, se va a mover el código actual a un método independiente. Con este paso, resulta más fácil empezar con un nuevo ejemplo. Cambie el nombre del método `Main` por `WorkingWithIntegers` y escriba un método `Main` nuevo que llame a `WorkingWithIntegers`. Cuando termine, el código debe tener un aspecto similar al siguiente:

```csharp
using System;

namespace NumbersInCSharp
{
    class Program
    {
        static void WorkingWithIntegers()
        {
            int a = 18;
            int b = 6;
            
            // addition
            int c = a + b;
            Console.WriteLine(c);
            
            // subtraction
            c = a - b;
            Console.WriteLine(c);
            
            // multiplication
            c = a * b;
            Console.WriteLine(c);
            
            // division
            c = a / b;
            Console.WriteLine(c);
        }

        static void Main(string[] args)
        {
            WorkingWithIntegers();
        }
    }
}
```

## <a name="explore-order-of-operations"></a>Análisis sobre el orden de las operaciones

Convierta en comentario la llamada a `WorkingWithIntegers()`. De este modo la salida estará menos saturada a medida que trabaje en esta sección:

```csharp
//WorkingWithIntegers();
```

El `//` inicia un **comentario** en C#. Los comentarios son cualquier texto que desea mantener en el código fuente pero que no se ejecuta como código. El compilador no genera ningún código ejecutable a partir de comentarios.

El lenguaje C# define la prioridad de las diferentes operaciones matemáticas con reglas compatibles con las reglas aprendidas en las operaciones matemáticas.
La multiplicación y división tienen prioridad sobre la suma y resta.
Explórelo mediante la adición del código siguiente a su método `Main` y la ejecución de `dotnet run`:

```csharp
int a = 5;
int b = 4;
int c = 2;
int d = a + b * c;
Console.WriteLine(d);
 ```

La salida muestra que la multiplicación se realiza antes que la suma.

Puede forzar la ejecución de un orden diferente de las operaciones si la operación o las operaciones que realizó primero se incluyen entre paréntesis. Agregue las líneas siguientes y ejecute de nuevo:

```csharp
d = (a + b) * c;
Console.WriteLine(d);
```

Combine muchas operaciones distintas para indagar más. Agregue algo parecido a las líneas siguientes en la parte inferior del método `Main`. Pruebe `dotnet run` de nuevo.

```csharp
d = (a + b) - 6 * c + (12 * 4) / 3 + 12;
Console.WriteLine(d);
```

Puede que haya observado un comportamiento interesante de los enteros. La división de enteros siempre genera un entero como resultado, incluso cuando se espera que el resultado incluya un decimal o una parte de una fracción.

Si no ha observado este comportamiento, pruebe el código siguiente al final de su método `Main`.

```csharp
int e = 7;
int f = 4;
int g = 3;
int h = (e + f) / g;
Console.WriteLine(h);
```

Escriba `dotnet run` de nuevo para ver los resultados.

Antes de continuar, vamos a tomar todo el código que ha escrito en esta sección y a colocarlo en un nuevo método. Llame a ese nuevo método `OrderPrecedence`.
Deberían terminar con algo similar a esto:

```csharp
using System;

namespace NumbersInCSharp
{
    class Program
    {
        static void WorkingWithIntegers()
        {
            int a = 18;
            int b = 6;
            
            // addition
            int c = a + b;
            Console.WriteLine(c);
            
            // subtraction
            c = a - b;
            Console.WriteLine(c);
            
            // multiplication
            c = a * b;
            Console.WriteLine(c);
            
            // division
            c = a / b;
            Console.WriteLine(c);
        }

        static void OrderPrecedence()
        {
            int a = 5;
            int b = 4;
            int c = 2;
            int d = a + b * c;
            Console.WriteLine(d);

            d = (a + b) * c;
            Console.WriteLine(d);

            d = (a + b) - 6 * c + (12 * 4) / 3 + 12;
            Console.WriteLine(d);

            int e = 7;
            int f = 4;
            int g = 3;
            int h = (e  + f) / g;
            Console.WriteLine(h);
        }

        static void Main(string[] args)
        {
            WorkingWithIntegers();

            OrderPrecedence();

        }
    }
}
```

## <a name="explore-integer-precision-and-limits"></a>Información sobre los límites y la precisión de los enteros

En el último ejemplo se ha mostrado que la división de enteros trunca el resultado.
Puede obtener el **resto** con el operador de **módulo**, el carácter `%`. Pruebe el código siguiente en el método `Main`:

```csharp
int a = 7;
int b = 4;
int c = 3;
int d = (a + b) / c;
int e = (a + b) % c;
Console.WriteLine($"quotient: {d}");
Console.WriteLine($"remainder: {e}");
```

El tipo de entero de C# difiere de los enteros matemáticos en un aspecto: el tipo `int` tiene límites mínimo y máximo. Agregue este código a su método `Main` para ver esos límites:

```csharp
int max = int.MaxValue;
int min = int.MinValue;
Console.WriteLine($"The range of integers is {min} to {max}");
```

Si un cálculo genera un valor que supera los límites, se producirá una condición de **subdesbordamiento** o **desbordamiento**. La respuesta parece ajustarse de un límite al otro. Agregue estas dos líneas a su método `Main` para ver un ejemplo:

```csharp
int what = max + 3;
Console.WriteLine($"An example of overflow: {what}");
```

Tenga en cuenta que la respuesta está muy próxima al entero mínimo (negativo). Es lo mismo que `min + 2`.
La operación de suma **desbordó** los valores permitidos para los enteros.
La respuesta es un número negativo muy grande porque un desbordamiento "se ajusta" desde el valor de entero más alto posible al más bajo.

Hay otros tipos numéricos con distintos límites y precisiones que podría usar si el tipo `int` no satisface sus necesidades. Veámoslo a continuación.

Una vez más, vamos a mover el código que escribió en esta sección a un método independiente. Denomínelo `TestLimits`.

## <a name="work-with-the-double-type"></a>Operaciones con el tipo double

El tipo numérico `double` representa números de punto flotante de doble precisión. Puede que no esté familiarizado con estos términos. Un número de **punto flotante** resulta útil para representar números no enteros cuya magnitud puede ser muy grande o pequeña. **Doble precisión** significa que estos números se almacenan con mayor precisión que en el caso de la **precisión sencilla**. En los equipos modernos, es más habitual utilizar números con doble precisión que con precisión sencilla.
Comencemos a explorar. Agregue el siguiente código y observe el resultado:

```csharp
double a = 5;
double b = 4;
double c = 2;
double d = (a + b) / c;
Console.WriteLine(d);
```

Tenga en cuenta que la respuesta incluye la parte decimal del cociente. Pruebe una expresión algo más complicada con tipos double:

```csharp
double e = 19;
double f = 23;
double g = 8;
double h = (e + f) / g;
Console.WriteLine(h);
```

El intervalo de un valor double es mucho más amplio que en el caso de los valores enteros. Pruebe el código siguiente debajo del que ha escrito hasta ahora:

```csharp
double max = double.MaxValue;
double min = double.MinValue;
Console.WriteLine($"The range of double is {min} to {max}");
```

Estos valores se imprimen en notación científica. El número a la izquierda de `E` es la mantisa. El número a la derecha es el exponente, como una potencia de diez.

Al igual que sucede con los números decimales en las operaciones matemáticas, los tipos double en C# pueden presentar errores de redondeo. Pruebe este código:

```csharp
double third = 1.0 / 3.0;
Console.WriteLine(third);
```

Sabe que repetir `0.3` no es exactamente lo mismo que `1/3`.

***Desafío***

Pruebe otros cálculos con números grandes, números pequeños, multiplicaciones y divisiones con el tipo `double`. Intente realizar cálculos más complicados.

Una vez que haya invertido un tiempo en ello, tome el código que ha escrito y colóquelo en un nuevo método. Ponga a ese nuevo método el nombre `WorkWithDoubles`.

## <a name="work-with-fixed-point-types"></a>Operaciones con tipos de punto fijo

Hasta el momento ha visto los tipos numéricos básicos en C#: los tipos integer y double.  Sin embargo, hay otro tipo más que debe aprender: el tipo `decimal`. El tipo `decimal` tiene un intervalo más pequeño, pero mayor precisión que `double`. El término **punto fijo** significa que el punto decimal o el punto binario no se mueven. Observemos lo siguiente:

```csharp
decimal min = decimal.MinValue;
decimal max = decimal.MaxValue;
Console.WriteLine($"The range of the decimal type is {min} to {max}");
```

Tenga en cuenta que el intervalo es más pequeño que con el tipo `double`. Puede observar una precisión mayor con el tipo decimal si prueba el siguiente código:

```csharp
double a = 1.0;
double b = 3.0;
Console.WriteLine(a / b);

decimal c = 1.0M;
decimal d = 3.0M;
Console.WriteLine(c / d);
```

El sufijo `M` en los números es la forma de indicar que una constante debe usar el tipo `decimal`.

Observe que la expresión matemática con el tipo decimal tiene más dígitos a la derecha del punto decimal.

***Desafío***

Ahora que ya conoce los diferentes tipos numéricos, escriba código para calcular el área de un círculo cuyo radio sea de 2,50 centímetros. Recuerde que el área de un circulo es igual al valor de su radio elevado al cuadrado multiplicado por Pi. Sugerencia: .NET contiene una constante de Pi, <xref:System.Math.PI?displayProperty=nameWithType>, que puede usar para ese valor.

Debe obtener una respuesta entre 19 y 20.
Puede comprobar la respuesta si [consulta el ejemplo de código terminado en GitHub](https://github.com/dotnet/samples/tree/master/csharp/numbers-quickstart/Program.cs#L104-L106).

Si lo desea, pruebe con otras fórmulas.

Ha completado el inicio rápido "Números en C#". Puede continuar con la guía de inicio rápido [Ramas y bucles](branches-and-loops-local.md) en su propio entorno de desarrollo.

Puede obtener más información sobre los números en C# en los temas siguientes:

- [Tipos numéricos integrales](../../language-reference/builtin-types/integral-numeric-types.md)
- [Tipos numéricos de punto flotante](../../language-reference/builtin-types/floating-point-numeric-types.md)
- [Conversiones numéricas integradas](../../language-reference/builtin-types/numeric-conversions.md)
