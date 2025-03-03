---
title: 'Operador await: referencia de C#'
ms.custom: seodec18
ms.date: 11/08/2019
f1_keywords:
- await_CSharpKeyword
helpviewer_keywords:
- await keyword [C#]
- await [C#]
ms.assetid: 50725c24-ac76-4ca7-bca1-dd57642ffedb
ms.openlocfilehash: 36cb4a5def6b75281edbe878d89af0c18ab226ec
ms.sourcegitcommit: fbb8a593a511ce667992502a3ce6d8f65c594edf
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/16/2019
ms.locfileid: "74140657"
---
# <a name="await-operator-c-reference"></a>Operador await (referencia de C#)

El operador `await` suspende la evaluación del método [async](../keywords/async.md) envolvente hasta que se completa la operación asincrónica representada por su operando. Cuando se completa la operación asincrónica, el operador `await` devuelve el resultado de la operación, si existe. Cuando el operador `await` se aplica al operando que representa la operación ya completada, devuelve el resultado de la operación inmediatamente sin suspender el método envolvente. El operador `await` no bloquea el subproceso que evalúa el método async. Cuando el operador `await` suspende el método async envolvente, el control vuelve al autor de la llamada del método.

En el ejemplo siguiente, el método <xref:System.Net.Http.HttpClient.GetByteArrayAsync%2A?displayProperty=nameWithType> devuelve la instancia `Task<byte[]>`, que representa una operación asincrónica que genera una matriz de bytes cuando se completa. Hasta que se complete la operación, el operador `await` suspende el método `DownloadDocsMainPageAsync`. Cuando se suspende `DownloadDocsMainPageAsync`, se devuelve el control `Main` al método, que es el autor de la llamada a `DownloadDocsMainPageAsync`. El método `Main` se ejecuta hasta que necesita el resultado de la operación asincrónica realizada por el método `DownloadDocsMainPageAsync`. Cuando <xref:System.Net.Http.HttpClient.GetByteArrayAsync%2A> obtiene todos los bytes, se evalúa el resto del método `DownloadDocsMainPageAsync`. Después, se evalúa el resto del método `Main`.

[!code-csharp[await example](~/samples/csharp/language-reference/operators/AwaitOperator.cs)]

En el ejemplo anterior se usa el método [async `Main`](../../programming-guide/main-and-command-args/index.md), lo que es posible a partir de C# 7.1. Para obtener más información, vea la sección [Operador await en el método Main](#await-operator-in-the-main-method).

> [!NOTE]
> Para obtener una introducción a la programación asincrónica, vea [Programación asincrónica con async y await](../../programming-guide/concepts/async/index.md). La programación asincrónica con `async` y `await` sigue el [modelo asincrónico basado en tareas](../../../standard/asynchronous-programming-patterns/task-based-asynchronous-pattern-tap.md).

El operador `await` se puede usar solamente en un método, una [expresión lambda](../../programming-guide/statements-expressions-operators/lambda-expressions.md) o un [método anónimo](delegate-operator.md) modificado por la palabra clave [async](../keywords/async.md). Dentro de un método async, no se puede usar el operador `await` en el cuerpo de una función sincrónica, dentro del bloque de una [instrucción lock](../keywords/lock-statement.md) y en un contexto [no seguro](../keywords/unsafe.md).

El operando del operador `await` suele ser de uno de los siguientes tipos de .NET: <xref:System.Threading.Tasks.Task>, <xref:System.Threading.Tasks.Task%601>, <xref:System.Threading.Tasks.ValueTask> o <xref:System.Threading.Tasks.ValueTask%601>. Aunque cualquier expresión con await puede ser el operando del operador `await`. Para obtener más información, vea la sección [Expresiones con await](~/_csharplang/spec/expressions.md#awaitable-expressions) de la [especificación del lenguaje C#](~/_csharplang/spec/introduction.md).

A partir C# 8.0, puede usar la instrucción `await foreach` para utilizar un flujo de datos asincrónico. Para obtener más información, consulte la sección [Secuencias asincrónicas](../../whats-new/csharp-8.md#asynchronous-streams) del artículo [Novedades de C# 8.0](../../whats-new/csharp-8.md).

El tipo de expresión `await t` es `TResult` si el tipo de expresión `t` es <xref:System.Threading.Tasks.Task%601> o <xref:System.Threading.Tasks.ValueTask%601>. Si el tipo de `t` es <xref:System.Threading.Tasks.Task> o <xref:System.Threading.Tasks.ValueTask>, el tipo de `await t` es `void`. En ambos casos, si `t` produce una excepción, `await t` vuelve a producir la excepción. Para obtener más información sobre cómo controlar las excepciones, vea la sección [Excepciones en métodos async](../keywords/try-catch.md#exceptions-in-async-methods) del artículo [Instrucción try-catch](../keywords/try-catch.md).

Las palabras clave `async` y `await` están disponibles en C# 5 y versiones posteriores.

## <a name="await-operator-in-the-main-method"></a>Operador await en el método Main

A partir C# 7.1, el [método `Main`](../../programming-guide/main-and-command-args/index.md), que es el punto de entrada de la aplicación, puede devolver `Task` o `Task<int>`, lo que le permite ser asincrónico para poder usar el operador `await` en su cuerpo. En versiones anteriores de C#, para tener la certeza de que el método `Main` espera a que finalice una operación asincrónica, puede recuperar el valor de la propiedad <xref:System.Threading.Tasks.Task%601.Result?displayProperty=nameWithType> de la instancia <xref:System.Threading.Tasks.Task%601> devuelta por el método async correspondiente. Para las operaciones asincrónicas que no generan un valor, puede llamar al método <xref:System.Threading.Tasks.Task.Wait%2A?displayProperty=nameWithType>. Para obtener información sobre cómo seleccionar la versión del lenguaje, vea [Control de versiones del lenguaje C#](../configure-language-version.md).

## <a name="c-language-specification"></a>Especificación del lenguaje C#

Para obtener más información, vea la sección [Expresiones await](~/_csharplang/spec/expressions.md#await-expressions) de la [especificación del lenguaje C#](~/_csharplang/spec/introduction.md).

## <a name="see-also"></a>Vea también

- [Referencia de C#](../index.md)
- [Operadores de C#](index.md)
- [async](../keywords/async.md)
- [Modelo de programación asincrónica de tareas](../../programming-guide/concepts/async/task-asynchronous-programming-model.md)
- [Programación asincrónica](../../async.md)
- [Async en profundidad](../../../standard/async-in-depth.md)
- [Tutorial: Acceso a la web con async y await](../../programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md)
- [Tutorial: Generación y uso de secuencias asincrónicas con C# 8.0 y .NET Core 3.0](../../tutorials/generate-consume-asynchronous-stream.md)
