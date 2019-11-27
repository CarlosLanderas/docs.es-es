---
title: Yield (Instrucción)
ms.date: 07/20/2015
f1_keywords:
- vb.Yield
helpviewer_keywords:
- iterators, Yield statement [Visual Basic]
- iterators [Visual Basic]
- Yield statement [Visual Basic]
ms.assetid: f33126c5-d7c4-43e2-8e36-4ae3f0703d97
ms.openlocfilehash: 72a8dafdc5aa834a644e1e70a309cfc0827b5fdf
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352725"
---
# <a name="yield-statement-visual-basic"></a><span data-ttu-id="78be7-102">Yield (Instrucción) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="78be7-102">Yield Statement (Visual Basic)</span></span>
<span data-ttu-id="78be7-103">Envía el siguiente elemento de una colección a una instrucción `For Each...Next`.</span><span class="sxs-lookup"><span data-stu-id="78be7-103">Sends the next element of a collection to a `For Each...Next` statement.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="78be7-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="78be7-104">Syntax</span></span>  
  
```vb  
Yield expression  
```  
  
## <a name="parameters"></a><span data-ttu-id="78be7-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="78be7-105">Parameters</span></span>  
  
|<span data-ttu-id="78be7-106">Término</span><span class="sxs-lookup"><span data-stu-id="78be7-106">Term</span></span>|<span data-ttu-id="78be7-107">Definición</span><span class="sxs-lookup"><span data-stu-id="78be7-107">Definition</span></span>|  
|---|---|  
|`expression`|<span data-ttu-id="78be7-108">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="78be7-108">Required.</span></span> <span data-ttu-id="78be7-109">Una expresión que se pueda convertir implícitamente al tipo de la función de iterador o `Get` descriptor de acceso que contiene la instrucción `Yield`.</span><span class="sxs-lookup"><span data-stu-id="78be7-109">An expression that is implicitly convertible to the type of the iterator function or `Get` accessor that contains the `Yield` statement.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="78be7-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="78be7-110">Remarks</span></span>  
 <span data-ttu-id="78be7-111">La instrucción `Yield` devuelve un elemento de una colección a la vez.</span><span class="sxs-lookup"><span data-stu-id="78be7-111">The `Yield` statement returns one element of a collection at a time.</span></span> <span data-ttu-id="78be7-112">La instrucción `Yield` se incluye en una función de iterador o en un descriptor de acceso `Get`, que realiza iteraciones personalizadas en una colección.</span><span class="sxs-lookup"><span data-stu-id="78be7-112">The `Yield` statement is included in an iterator function or `Get` accessor, which perform custom iterations over a collection.</span></span>  
  
 <span data-ttu-id="78be7-113">Utilice una función de iterador mediante un [... Instrucción Next](../../../visual-basic/language-reference/statements/for-each-next-statement.md) o una consulta LINQ.</span><span class="sxs-lookup"><span data-stu-id="78be7-113">You consume an iterator function by using a [For Each...Next Statement](../../../visual-basic/language-reference/statements/for-each-next-statement.md) or a LINQ query.</span></span> <span data-ttu-id="78be7-114">Cada iteración del bucle `For Each` llama a la función de iterador.</span><span class="sxs-lookup"><span data-stu-id="78be7-114">Each iteration of the `For Each` loop calls the iterator function.</span></span> <span data-ttu-id="78be7-115">Cuando se alcanza una instrucción `Yield` en la función de iterador, se devuelve `expression` y se conserva la ubicación actual en el código.</span><span class="sxs-lookup"><span data-stu-id="78be7-115">When a `Yield` statement is reached in the iterator function, `expression` is returned, and the current location in code is retained.</span></span> <span data-ttu-id="78be7-116">La ejecución se reinicia desde esa ubicación la próxima vez que se llama a la función del iterador.</span><span class="sxs-lookup"><span data-stu-id="78be7-116">Execution is restarted from that location the next time that the iterator function is called.</span></span>  
  
 <span data-ttu-id="78be7-117">Debe existir una conversión implícita del tipo de `expression` de la instrucción `Yield` al tipo de valor devuelto del iterador.</span><span class="sxs-lookup"><span data-stu-id="78be7-117">An implicit conversion must exist from the type of `expression` in the `Yield` statement to the return type of the iterator.</span></span>  
  
 <span data-ttu-id="78be7-118">Puede usar una instrucción `Exit Function` o `Return` para finalizar la iteración.</span><span class="sxs-lookup"><span data-stu-id="78be7-118">You can use an `Exit Function` or `Return` statement to end the iteration.</span></span>  
  
 <span data-ttu-id="78be7-119">"Yield" no es una palabra reservada y tiene un significado especial solo cuando se utiliza en una función de `Iterator` o un descriptor de acceso `Get`.</span><span class="sxs-lookup"><span data-stu-id="78be7-119">"Yield" is not a reserved word and has special meaning only when it is used in an `Iterator` function or `Get` accessor.</span></span>  
  
 <span data-ttu-id="78be7-120">Para obtener más información sobre las funciones de iterador y los descriptores de acceso `Get`, vea [iteradores](../../programming-guide/concepts/iterators.md).</span><span class="sxs-lookup"><span data-stu-id="78be7-120">For more information about iterator functions and `Get` accessors, see [Iterators](../../programming-guide/concepts/iterators.md).</span></span>  
  
## <a name="iterator-functions-and-get-accessors"></a><span data-ttu-id="78be7-121">Funciones de iterador y obtener descriptores de acceso</span><span class="sxs-lookup"><span data-stu-id="78be7-121">Iterator Functions and Get Accessors</span></span>  
 <span data-ttu-id="78be7-122">La declaración de una función de iterador o `Get` descriptor de acceso debe cumplir los siguientes requisitos:</span><span class="sxs-lookup"><span data-stu-id="78be7-122">The declaration of an iterator function or `Get` accessor must meet the following requirements:</span></span>  
  
- <span data-ttu-id="78be7-123">Debe incluir un modificador de [iterador](../../../visual-basic/language-reference/modifiers/iterator.md) .</span><span class="sxs-lookup"><span data-stu-id="78be7-123">It must include an [Iterator](../../../visual-basic/language-reference/modifiers/iterator.md) modifier.</span></span>  
  
- <span data-ttu-id="78be7-124">El tipo de valor devuelto debe ser <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator> o <xref:System.Collections.Generic.IEnumerator%601>.</span><span class="sxs-lookup"><span data-stu-id="78be7-124">The return type must be <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator>, or <xref:System.Collections.Generic.IEnumerator%601>.</span></span>  
  
- <span data-ttu-id="78be7-125">No puede tener ningún parámetro `ByRef`.</span><span class="sxs-lookup"><span data-stu-id="78be7-125">It cannot have any `ByRef` parameters.</span></span>  
  
 <span data-ttu-id="78be7-126">Una función de iterador no puede aparecer en un evento, un constructor de instancia, un constructor estático o un destructor estático.</span><span class="sxs-lookup"><span data-stu-id="78be7-126">An iterator function cannot occur in an event, instance constructor, static constructor, or static destructor.</span></span>  
  
 <span data-ttu-id="78be7-127">Una función de iterador puede ser una función anónima.</span><span class="sxs-lookup"><span data-stu-id="78be7-127">An iterator function can be an anonymous function.</span></span> <span data-ttu-id="78be7-128">Para obtener más información, consulta [Iteradores](../../programming-guide/concepts/iterators.md).</span><span class="sxs-lookup"><span data-stu-id="78be7-128">For more information, see [Iterators](../../programming-guide/concepts/iterators.md).</span></span>  
  
## <a name="exception-handling"></a><span data-ttu-id="78be7-129">Control de excepciones</span><span class="sxs-lookup"><span data-stu-id="78be7-129">Exception Handling</span></span>  
 <span data-ttu-id="78be7-130">Una instrucción `Yield` puede estar dentro de un bloque `Try` de una instrucción [try... Detectar... Finally](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).</span><span class="sxs-lookup"><span data-stu-id="78be7-130">A `Yield` statement can be inside a `Try` block of a [Try...Catch...Finally Statement](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).</span></span> <span data-ttu-id="78be7-131">Un bloque `Try` que tiene una instrucción `Yield` puede tener bloques `Catch` y puede tener un bloque `Finally`.</span><span class="sxs-lookup"><span data-stu-id="78be7-131">A `Try` block that has a `Yield` statement can have `Catch` blocks, and can have a `Finally` block.</span></span>  
  
 <span data-ttu-id="78be7-132">Una instrucción `Yield` no puede estar dentro de un bloque de `Catch` o un bloque `Finally`.</span><span class="sxs-lookup"><span data-stu-id="78be7-132">A `Yield` statement cannot be inside a `Catch` block or a `Finally` block.</span></span>  
  
 <span data-ttu-id="78be7-133">Si el cuerpo de `For Each` (fuera de la función de iterador) produce una excepción, no se ejecuta un bloque de `Catch` en la función de iterador, pero se ejecuta un bloque de `Finally` en la función de iterador.</span><span class="sxs-lookup"><span data-stu-id="78be7-133">If the `For Each` body (outside of the iterator function) throws an exception, a `Catch` block in the iterator function is not executed, but a `Finally` block in the iterator function is executed.</span></span> <span data-ttu-id="78be7-134">Un bloque `Catch` dentro de una función de iterador solo detecta las excepciones que se producen dentro de la función de iterador.</span><span class="sxs-lookup"><span data-stu-id="78be7-134">A `Catch` block inside an iterator function catches only exceptions that occur inside the iterator function.</span></span>  
  
## <a name="technical-implementation"></a><span data-ttu-id="78be7-135">Implementación técnica</span><span class="sxs-lookup"><span data-stu-id="78be7-135">Technical Implementation</span></span>  
 <span data-ttu-id="78be7-136">El código siguiente devuelve un `IEnumerable (Of String)` de una función de iterador y, a continuación, recorre en iteración los elementos de la `IEnumerable (Of String)`.</span><span class="sxs-lookup"><span data-stu-id="78be7-136">The following code returns an `IEnumerable (Of String)` from an iterator function and then iterates through the elements of the `IEnumerable (Of String)`.</span></span>  
  
```vb  
Dim elements As IEnumerable(Of String) = MyIteratorFunction()  
    …  
For Each element As String In elements  
Next  
```  
  
 <span data-ttu-id="78be7-137">La llamada a `MyIteratorFunction` no ejecuta el cuerpo de la función.</span><span class="sxs-lookup"><span data-stu-id="78be7-137">The call to `MyIteratorFunction` doesn't execute the body of the function.</span></span> <span data-ttu-id="78be7-138">En su lugar, la llamada devuelve un valor `IEnumerable(Of String)` en la variable `elements`.</span><span class="sxs-lookup"><span data-stu-id="78be7-138">Instead the call returns an `IEnumerable(Of String)` into the `elements` variable.</span></span>  
  
 <span data-ttu-id="78be7-139">En una iteración del bucle `For Each`, se llama al método <xref:System.Collections.IEnumerator.MoveNext%2A> para `elements`.</span><span class="sxs-lookup"><span data-stu-id="78be7-139">On an iteration of the `For Each` loop, the <xref:System.Collections.IEnumerator.MoveNext%2A> method is called for `elements`.</span></span> <span data-ttu-id="78be7-140">Esta llamada ejecuta el cuerpo de `MyIteratorFunction` hasta que se alcanza la siguiente instrucción `Yield`.</span><span class="sxs-lookup"><span data-stu-id="78be7-140">This call executes the body of `MyIteratorFunction` until the next `Yield` statement is reached.</span></span> <span data-ttu-id="78be7-141">La instrucción `Yield` devuelve una expresión que determina no solo el valor de la variable `element` para su consumo por parte del cuerpo del bucle, sino también la propiedad <xref:System.Collections.Generic.IEnumerator%601.Current%2A> de los elementos, que es una `IEnumerable (Of String)`.</span><span class="sxs-lookup"><span data-stu-id="78be7-141">The `Yield` statement returns an expression that determines not only the value of the `element` variable for consumption by the loop body but also the <xref:System.Collections.Generic.IEnumerator%601.Current%2A> property of elements, which is an `IEnumerable (Of String)`.</span></span>  
  
 <span data-ttu-id="78be7-142">En cada iteración subsiguiente del bucle `For Each`, la ejecución del cuerpo del iterador continúa desde donde se dejó, deteniéndose de nuevo al alcanzar una instrucción `Yield`.</span><span class="sxs-lookup"><span data-stu-id="78be7-142">On each subsequent iteration of the `For Each` loop, the execution of the iterator body continues from where it left off, again stopping when it reaches a `Yield` statement.</span></span> <span data-ttu-id="78be7-143">El bucle de `For Each` se completa cuando se alcanza el final de la función de iterador o una instrucción `Return` o `Exit Function`.</span><span class="sxs-lookup"><span data-stu-id="78be7-143">The `For Each` loop completes when the end of the iterator function or a `Return` or `Exit Function` statement is reached.</span></span>  
  
## <a name="example"></a><span data-ttu-id="78be7-144">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="78be7-144">Example</span></span>  
 <span data-ttu-id="78be7-145">El ejemplo siguiente tiene una instrucción `Yield` que está dentro de un [... Siguiente](../../../visual-basic/language-reference/statements/for-next-statement.md) bucle.</span><span class="sxs-lookup"><span data-stu-id="78be7-145">The following example has a `Yield` statement that is inside a [For…Next](../../../visual-basic/language-reference/statements/for-next-statement.md) loop.</span></span> <span data-ttu-id="78be7-146">Cada iteración del cuerpo de la instrucción [for each](../../../visual-basic/language-reference/statements/for-each-next-statement.md) en `Main` crea una llamada a la función de iterador `Power`.</span><span class="sxs-lookup"><span data-stu-id="78be7-146">Each iteration of the [For Each](../../../visual-basic/language-reference/statements/for-each-next-statement.md) statement body in `Main` creates a call to the `Power` iterator function.</span></span> <span data-ttu-id="78be7-147">Cada llamada a la función de iterador prosigue con la siguiente ejecución de la instrucción `Yield`, que se produce durante la siguiente iteración del bucle `For…Next`.</span><span class="sxs-lookup"><span data-stu-id="78be7-147">Each call to the iterator function proceeds to the next execution of the `Yield` statement, which occurs during the next iteration of the `For…Next` loop.</span></span>  
  
 <span data-ttu-id="78be7-148">El tipo de valor devuelto del método iterador es <xref:System.Collections.Generic.IEnumerable%601>, un tipo de interfaz de iterador.</span><span class="sxs-lookup"><span data-stu-id="78be7-148">The return type of the iterator method is <xref:System.Collections.Generic.IEnumerable%601>, an iterator interface type.</span></span> <span data-ttu-id="78be7-149">Cuando se llama al método iterador, este devuelve un objeto enumerable que contiene las potencias de un número.</span><span class="sxs-lookup"><span data-stu-id="78be7-149">When the iterator method is called, it returns an enumerable object that contains the powers of a number.</span></span>  
  
 [!code-vb[VbVbalrStatements#98](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class2.vb#98)]  
  
## <a name="example"></a><span data-ttu-id="78be7-150">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="78be7-150">Example</span></span>  
 <span data-ttu-id="78be7-151">En el ejemplo siguiente se muestra un descriptor de acceso `Get` que es un iterador.</span><span class="sxs-lookup"><span data-stu-id="78be7-151">The following example demonstrates a `Get` accessor that is an iterator.</span></span> <span data-ttu-id="78be7-152">La declaración de propiedad incluye un modificador `Iterator`.</span><span class="sxs-lookup"><span data-stu-id="78be7-152">The property declaration includes an `Iterator` modifier.</span></span>  
  
 [!code-vb[VbVbalrStatements#99](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class2.vb#99)]  
  
 <span data-ttu-id="78be7-153">Para obtener más ejemplos, vea [iteradores](../../programming-guide/concepts/iterators.md).</span><span class="sxs-lookup"><span data-stu-id="78be7-153">For additional examples, see [Iterators](../../programming-guide/concepts/iterators.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78be7-154">Vea también</span><span class="sxs-lookup"><span data-stu-id="78be7-154">See also</span></span>

- [<span data-ttu-id="78be7-155">Instrucciones</span><span class="sxs-lookup"><span data-stu-id="78be7-155">Statements</span></span>](../../../visual-basic/language-reference/statements/index.md)
