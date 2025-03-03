---
title: Expresiones lambda
ms.date: 07/20/2015
f1_keywords:
- vb.LambdaFunction
helpviewer_keywords:
- functions [Visual Basic], lambda expressions
- lambda expressions [Visual Basic]
- expressions [Visual Basic], lambda
- inline functions [Visual Basic]
ms.assetid: 137064b0-3928-4bfa-ba71-c3f9cbd951e2
ms.openlocfilehash: f3f963167e1b3633cc5fe6e1f435e374cd272cce
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345974"
---
# <a name="lambda-expressions-visual-basic"></a>Lambda (expresiones) (Visual Basic)

Una *expresión lambda* es una función o subrutina sin un nombre que se puede usar siempre que un delegado sea válido. Las expresiones lambda pueden ser funciones o subrutinas y pueden ser de una o varias líneas. Puede pasar valores del ámbito actual a una expresión lambda.

> [!NOTE]
> La instrucción `RemoveHandler` es una excepción. No se puede pasar una expresión lambda en el parámetro de delegado de `RemoveHandler`.

Las expresiones lambda se crean mediante la palabra clave `Function` o `Sub`, de la misma forma que se crea una función o subrutina estándar. Sin embargo, las expresiones lambda se incluyen en una instrucción.

El ejemplo siguiente es una expresión lambda que incrementa su argumento y devuelve el valor. En el ejemplo se muestra la sintaxis de la expresión lambda de una sola línea y varias líneas para una función.

[!code-vb[VbVbalrLambdas#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#14)]

El ejemplo siguiente es una expresión lambda que escribe un valor en la consola. En el ejemplo se muestra la sintaxis de la expresión lambda de una sola línea y varias líneas para una subrutina.

[!code-vb[VbVbalrLambdas#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#15)]

Observe que en los ejemplos anteriores las expresiones lambda se asignan a un nombre de variable. Siempre que se haga referencia a la variable, se invoca la expresión lambda. También puede declarar e invocar una expresión lambda al mismo tiempo, tal como se muestra en el ejemplo siguiente.

[!code-vb[VbVbalrLambdas#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#3)]

Se puede devolver una expresión lambda como valor de una llamada de función (como se muestra en el ejemplo de la sección de [contexto](#context) más adelante en este tema) o pasarla como argumento a un parámetro que toma un tipo de delegado, como se muestra en el ejemplo siguiente.

[!code-vb[VbVbalrLambdas#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class2.vb#8)]

## <a name="lambda-expression-syntax"></a>Sintaxis de la expresión lambda

La sintaxis de una expresión lambda es similar a la de una función o subrutina estándar. Las diferencias son las siguientes:

- Una expresión lambda no tiene un nombre.

- Las expresiones lambda no pueden tener modificadores, como `Overloads` o `Overrides`.

- Las funciones lambda de una sola línea no usan una cláusula `As` para designar el tipo de valor devuelto. En su lugar, el tipo se deduce del valor al que se evalúa el cuerpo de la expresión lambda. Por ejemplo, si el cuerpo de la expresión lambda es `cust.City = "London"`, su tipo de valor devuelto es `Boolean`.

- En las funciones lambda de varias líneas, puede especificar un tipo de valor devuelto mediante una cláusula `As` u omitir la cláusula `As` para que se deduzca el tipo de valor devuelto. Cuando se omite la cláusula `As` para una función lambda de varias líneas, se infiere que el tipo de valor devuelto es el tipo dominante de todas las instrucciones `Return` de la función lambda de varias líneas. El *tipo dominante* es un tipo único al que se pueden ampliar todos los demás tipos. Si no se puede determinar este tipo único, el tipo dominante es el tipo único al que se pueden restringir todos los demás tipos de la matriz. Si no se puede determinar ninguno de estos tipos únicos, el tipo dominante es `Object`. En este caso, si `Option Strict` se establece en `On`, se produce un error del compilador.

     Por ejemplo, si las expresiones proporcionadas a la instrucción `Return` contienen valores de tipo `Integer`, `Long`y `Double`, la matriz resultante es de tipo `Double`. Tanto `Integer` como `Long` amplían a `Double` y solo `Double`. Por lo tanto, `Double` es el tipo dominante. Para obtener más información, consulta [Widening and Narrowing Conversions](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).

- El cuerpo de una función de una sola línea debe ser una expresión que devuelva un valor, no una instrucción. No hay ninguna instrucción `Return` para las funciones de una sola línea. El valor devuelto por la función de una sola línea es el valor de la expresión en el cuerpo de la función.

- El cuerpo de una subrutina de una sola línea debe ser una instrucción de una sola línea.

- Las funciones de una sola línea y las subrutinas no incluyen una instrucción `End Function` o `End Sub`.

- Puede especificar el tipo de datos de un parámetro de expresión lambda mediante la palabra clave `As`, o bien se puede inferir el tipo de datos del parámetro. Todos los parámetros deben tener tipos de datos especificados o todos deben ser inferidos.

- no se permiten los parámetros `Optional` y `Paramarray`.

- No se permiten parámetros genéricos.

## <a name="async-lambdas"></a>Lambdas asincrónicas

Puede crear fácilmente expresiones e instrucciones lambda que incorporen el procesamiento asincrónico mediante las palabras clave [Async](../../../../visual-basic/language-reference/modifiers/async.md) y [Await Operator](../../../../visual-basic/language-reference/operators/await-operator.md) . Por ejemplo, en el siguiente ejemplo de formularios Windows Forms se incluye un controlador de eventos que llama y espera un método asincrónico, `ExampleMethodAsync`.

```vb
Public Class Form1

    Async Sub Button1_Click(sender As Object, e As EventArgs) Handles Button1.Click
        ' ExampleMethodAsync returns a Task.
        Await ExampleMethodAsync()
        TextBox1.Text = vbCrLf & "Control returned to button1_Click."
    End Sub

    Async Function ExampleMethodAsync() As Task
        ' The following line simulates a task-returning asynchronous process.
        Await Task.Delay(1000)
    End Function

End Class
```

Puede Agregar el mismo controlador de eventos mediante una expresión lambda asincrónica en una [instrucción AddHandler](../../../../visual-basic/language-reference/statements/addhandler-statement.md). Para agregar este controlador, agregue un modificador `Async` antes de la lista de parámetros lambda, como se muestra en el ejemplo siguiente.

```vb
Public Class Form1

    Private Sub Form1_Load(sender As Object, e As EventArgs) Handles MyBase.Load
        AddHandler Button1.Click,
            Async Sub(sender1, e1)
                ' ExampleMethodAsync returns a Task.
                Await ExampleMethodAsync()
                TextBox1.Text = vbCrLf & "Control returned to Button1_ Click."
            End Sub
    End Sub

    Async Function ExampleMethodAsync() As Task
        ' The following line simulates a task-returning asynchronous process.
        Await Task.Delay(1000)
    End Function

End Class
```

Para obtener más información sobre cómo crear y usar métodos asincrónicos, vea [programación asincrónica con Async y Await](../../../../visual-basic/programming-guide/concepts/async/index.md).

## <a name="context"></a>Context

Una expresión lambda comparte su contexto con el ámbito en el que se define. Tiene los mismos derechos de acceso que cualquier código escrito en el ámbito contenedor. Esto incluye el acceso a variables de miembro, funciones y subss, `Me`y parámetros y variables locales en el ámbito contenedor.

El acceso a las variables locales y los parámetros del ámbito contenedor puede extenderse más allá de la duración de ese ámbito. Siempre que un delegado que hace referencia a una expresión lambda no esté disponible para la recolección de elementos no utilizados, se conserva el acceso a las variables en el entorno original. En el ejemplo siguiente, la variable `target` es local a `makeTheGame`, el método en el que se define la expresión lambda `playTheGame`. Tenga en cuenta que la expresión lambda devuelta, asignada a `takeAGuess` en `Main`, todavía tiene acceso a la variable local `target`.

[!code-vb[VbVbalrLambdas#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class6.vb#12)]

En el ejemplo siguiente se muestra la amplia gama de derechos de acceso de la expresión lambda anidada. Cuando la expresión lambda devuelta se ejecuta desde `Main` como `aDel`, tiene acceso a estos elementos:

- Campo de la clase en la que se define: `aField`

- Propiedad de la clase en la que se define: `aProp`

- Parámetro del método `functionWithNestedLambda`, en el que se define: `level1`

- Una variable local de `functionWithNestedLambda`: `localVar`

- Parámetro de la expresión lambda en la que está anidado: `level2`

 [!code-vb[VbVbalrLambdas#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class3.vb#9)]

## <a name="converting-to-a-delegate-type"></a>Convertir a un tipo de delegado

Una expresión lambda se puede convertir implícitamente en un tipo de delegado compatible. Para obtener información sobre los requisitos generales de compatibilidad, consulte [conversión de delegado relajado](../../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md). Por ejemplo, en el ejemplo de código siguiente se muestra una expresión lambda que se convierte implícitamente en `Func(Of Integer, Boolean)` o en una firma de delegado correspondiente.

[!code-vb[VbVbalrLambdas#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#16)]

En el ejemplo de código siguiente se muestra una expresión lambda que se convierte implícitamente en `Sub(Of Double, String, Double)` o en una firma de delegado correspondiente.

[!code-vb[VbVbalrLambdas#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/class7.vb#23)]

Cuando se asignan expresiones lambda a los delegados o se pasan como argumentos a los procedimientos, se pueden especificar los nombres de los parámetros pero omitir sus tipos de datos, lo que permite tomar los tipos del delegado.

## <a name="examples"></a>Ejemplos

- En el ejemplo siguiente se define una expresión lambda que devuelve `True` si el argumento que acepta valores NULL tiene un valor asignado y `False` si su valor es `Nothing`.

     [!code-vb[VbVbalrLambdas#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#4)]

- En el ejemplo siguiente se define una expresión lambda que devuelve el índice del último elemento de una matriz.

     [!code-vb[VbVbalrLambdas#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#5)]

## <a name="see-also"></a>Vea también

- [Procedimientos](./index.md)
- [Introducción a LINQ en Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [Delegados](../../../../visual-basic/programming-guide/language-features/delegates/index.md)
- [Function (instrucción)](../../../../visual-basic/language-reference/statements/function-statement.md)
- [Sub (instrucción)](../../../../visual-basic/language-reference/statements/sub-statement.md)
- [Tipos de valor que aceptan valores NULL](../../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
- [Paso de procedimientos a otro procedimiento en Visual Basic](../../../../visual-basic/programming-guide/language-features/delegates/how-to-pass-procedures-to-another-procedure.md)
- [Crear una expresión lambda](./how-to-create-a-lambda-expression.md)
- [Conversión de delegado flexible](../../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)
