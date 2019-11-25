---
title: Expresión de función
ms.date: 07/20/2015
helpviewer_keywords:
- Function expression [Visual Basic]
- functions [Visual Basic], function expressions
- lambda expressions [Visual Basic], function expression
ms.assetid: e8a47a45-4b8a-4f45-a623-7653625dffbc
ms.openlocfilehash: d14d7c9bc701b5e06c51202c07c3b79832aba7cc
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74331074"
---
# <a name="function-expression-visual-basic"></a><span data-ttu-id="e5f32-102">Expresión de función (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e5f32-102">Function Expression (Visual Basic)</span></span>
<span data-ttu-id="e5f32-103">Declares the parameters and code that define a function lambda expression.</span><span class="sxs-lookup"><span data-stu-id="e5f32-103">Declares the parameters and code that define a function lambda expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e5f32-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e5f32-104">Syntax</span></span>  
  
```vb  
Function ( [ parameterlist ] ) expression  
- or -  
Function ( [ parameterlist ] )  
  [ statements ]  
End Function  
```  
  
## <a name="parts"></a><span data-ttu-id="e5f32-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="e5f32-105">Parts</span></span>  
  
|<span data-ttu-id="e5f32-106">Término</span><span class="sxs-lookup"><span data-stu-id="e5f32-106">Term</span></span>|<span data-ttu-id="e5f32-107">de esquema JSON</span><span class="sxs-lookup"><span data-stu-id="e5f32-107">Definition</span></span>|  
|---|---|  
|`parameterlist`|<span data-ttu-id="e5f32-108">Opcional.</span><span class="sxs-lookup"><span data-stu-id="e5f32-108">Optional.</span></span> <span data-ttu-id="e5f32-109">A list of local variable names that represent the parameters of this procedure.</span><span class="sxs-lookup"><span data-stu-id="e5f32-109">A list of local variable names that represent the parameters of this procedure.</span></span> <span data-ttu-id="e5f32-110">The parentheses must be present even when the list is empty.</span><span class="sxs-lookup"><span data-stu-id="e5f32-110">The parentheses must be present even when the list is empty.</span></span> <span data-ttu-id="e5f32-111">See [Parameter List](../../../visual-basic/language-reference/statements/parameter-list.md).</span><span class="sxs-lookup"><span data-stu-id="e5f32-111">See [Parameter List](../../../visual-basic/language-reference/statements/parameter-list.md).</span></span>|  
|`expression`|<span data-ttu-id="e5f32-112">Requerido.</span><span class="sxs-lookup"><span data-stu-id="e5f32-112">Required.</span></span> <span data-ttu-id="e5f32-113">A single expression.</span><span class="sxs-lookup"><span data-stu-id="e5f32-113">A single expression.</span></span> <span data-ttu-id="e5f32-114">The type of the expression is the return type of the function.</span><span class="sxs-lookup"><span data-stu-id="e5f32-114">The type of the expression is the return type of the function.</span></span>|  
|`statements`|<span data-ttu-id="e5f32-115">Requerido.</span><span class="sxs-lookup"><span data-stu-id="e5f32-115">Required.</span></span> <span data-ttu-id="e5f32-116">A list of statements that returns a value by using the `Return` statement.</span><span class="sxs-lookup"><span data-stu-id="e5f32-116">A list of statements that returns a value by using the `Return` statement.</span></span> <span data-ttu-id="e5f32-117">(See [Return Statement](../../../visual-basic/language-reference/statements/return-statement.md).) The type of the value returned is the return type of the function.</span><span class="sxs-lookup"><span data-stu-id="e5f32-117">(See [Return Statement](../../../visual-basic/language-reference/statements/return-statement.md).) The type of the value returned is the return type of the function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e5f32-118">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e5f32-118">Remarks</span></span>  
 <span data-ttu-id="e5f32-119">A *lambda expression* is a function without a name that calculates and returns a value.</span><span class="sxs-lookup"><span data-stu-id="e5f32-119">A *lambda expression* is a function without a name that calculates and returns a value.</span></span> <span data-ttu-id="e5f32-120">You can use a lambda expression anywhere you can use a delegate type, except as an argument to `RemoveHandler`.</span><span class="sxs-lookup"><span data-stu-id="e5f32-120">You can use a lambda expression anywhere you can use a delegate type, except as an argument to `RemoveHandler`.</span></span> <span data-ttu-id="e5f32-121">For more information about delegates, and the use of lambda expressions with delegates, see [Delegate Statement](../../../visual-basic/language-reference/statements/delegate-statement.md) and [Relaxed Delegate Conversion](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md).</span><span class="sxs-lookup"><span data-stu-id="e5f32-121">For more information about delegates, and the use of lambda expressions with delegates, see [Delegate Statement](../../../visual-basic/language-reference/statements/delegate-statement.md) and [Relaxed Delegate Conversion](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md).</span></span>  
  
## <a name="lambda-expression-syntax"></a><span data-ttu-id="e5f32-122">Sintaxis de la expresión lambda</span><span class="sxs-lookup"><span data-stu-id="e5f32-122">Lambda Expression Syntax</span></span>  
 <span data-ttu-id="e5f32-123">The syntax of a lambda expression resembles that of a standard function.</span><span class="sxs-lookup"><span data-stu-id="e5f32-123">The syntax of a lambda expression resembles that of a standard function.</span></span> <span data-ttu-id="e5f32-124">The differences are as follows:</span><span class="sxs-lookup"><span data-stu-id="e5f32-124">The differences are as follows:</span></span>  
  
- <span data-ttu-id="e5f32-125">A lambda expression does not have a name.</span><span class="sxs-lookup"><span data-stu-id="e5f32-125">A lambda expression does not have a name.</span></span>  
  
- <span data-ttu-id="e5f32-126">Lambda expressions cannot have modifiers, such as `Overloads` or `Overrides`.</span><span class="sxs-lookup"><span data-stu-id="e5f32-126">Lambda expressions cannot have modifiers, such as `Overloads` or `Overrides`.</span></span>  
  
- <span data-ttu-id="e5f32-127">Lambda expressions do not use an `As` clause to designate the return type of the function.</span><span class="sxs-lookup"><span data-stu-id="e5f32-127">Lambda expressions do not use an `As` clause to designate the return type of the function.</span></span> <span data-ttu-id="e5f32-128">Instead, the type is inferred from the value that the body of a single-line lambda expression evaluates to, or the return value of a multiline lambda expression.</span><span class="sxs-lookup"><span data-stu-id="e5f32-128">Instead, the type is inferred from the value that the body of a single-line lambda expression evaluates to, or the return value of a multiline lambda expression.</span></span> <span data-ttu-id="e5f32-129">For example, if the body of a single-line lambda expression is `Where cust.City = "London"`, its return type is `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="e5f32-129">For example, if the body of a single-line lambda expression is `Where cust.City = "London"`, its return type is `Boolean`.</span></span>  
  
- <span data-ttu-id="e5f32-130">The body of a single-line lambda expression must be an expression, not a statement.</span><span class="sxs-lookup"><span data-stu-id="e5f32-130">The body of a single-line lambda expression must be an expression, not a statement.</span></span> <span data-ttu-id="e5f32-131">The body can consist of a call to a function procedure, but not a call to a sub procedure.</span><span class="sxs-lookup"><span data-stu-id="e5f32-131">The body can consist of a call to a function procedure, but not a call to a sub procedure.</span></span>  
  
- <span data-ttu-id="e5f32-132">Either all parameters must have specified data types or all must be inferred.</span><span class="sxs-lookup"><span data-stu-id="e5f32-132">Either all parameters must have specified data types or all must be inferred.</span></span>  
  
- <span data-ttu-id="e5f32-133">Optional and Paramarray parameters are not permitted.</span><span class="sxs-lookup"><span data-stu-id="e5f32-133">Optional and Paramarray parameters are not permitted.</span></span>  
  
- <span data-ttu-id="e5f32-134">Generic parameters are not permitted.</span><span class="sxs-lookup"><span data-stu-id="e5f32-134">Generic parameters are not permitted.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e5f32-135">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e5f32-135">Example</span></span>  
 <span data-ttu-id="e5f32-136">The following examples show two ways to create simple lambda expressions.</span><span class="sxs-lookup"><span data-stu-id="e5f32-136">The following examples show two ways to create simple lambda expressions.</span></span> <span data-ttu-id="e5f32-137">The first uses a `Dim` to provide a name for the function.</span><span class="sxs-lookup"><span data-stu-id="e5f32-137">The first uses a `Dim` to provide a name for the function.</span></span> <span data-ttu-id="e5f32-138">To call the function, you send in a value for the parameter.</span><span class="sxs-lookup"><span data-stu-id="e5f32-138">To call the function, you send in a value for the parameter.</span></span>  
  
 [!code-vb[VbVbalrLambdas#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#1)]  
  
 [!code-vb[VbVbalrLambdas#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#2)]  
  
## <a name="example"></a><span data-ttu-id="e5f32-139">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e5f32-139">Example</span></span>  
 <span data-ttu-id="e5f32-140">Alternatively, you can declare and run the function at the same time.</span><span class="sxs-lookup"><span data-stu-id="e5f32-140">Alternatively, you can declare and run the function at the same time.</span></span>  
  
 [!code-vb[VbVbalrLambdas#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#3)]  
  
## <a name="example"></a><span data-ttu-id="e5f32-141">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e5f32-141">Example</span></span>  
 <span data-ttu-id="e5f32-142">Following is an example of a lambda expression that increments its argument and returns the value.</span><span class="sxs-lookup"><span data-stu-id="e5f32-142">Following is an example of a lambda expression that increments its argument and returns the value.</span></span> <span data-ttu-id="e5f32-143">The example shows both the single-line and multiline lambda expression syntax for a function.</span><span class="sxs-lookup"><span data-stu-id="e5f32-143">The example shows both the single-line and multiline lambda expression syntax for a function.</span></span> <span data-ttu-id="e5f32-144">For more examples, see [Lambda Expressions](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="e5f32-144">For more examples, see [Lambda Expressions](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).</span></span>  
  
 [!code-vb[VbVbalrLambdas#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#14)]  
  
## <a name="example"></a><span data-ttu-id="e5f32-145">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e5f32-145">Example</span></span>  
 <span data-ttu-id="e5f32-146">Lambda expressions underlie many of the query operators in [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)], and can be used explicitly in method-based queries.</span><span class="sxs-lookup"><span data-stu-id="e5f32-146">Lambda expressions underlie many of the query operators in [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)], and can be used explicitly in method-based queries.</span></span> <span data-ttu-id="e5f32-147">The following example shows a typical [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] query, followed by the translation of the query into method format.</span><span class="sxs-lookup"><span data-stu-id="e5f32-147">The following example shows a typical [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] query, followed by the translation of the query into method format.</span></span>  
  
```vb  
Dim londonCusts = From cust In db.Customers  
                       Where cust.City = "London"  
                       Select cust  
  
' This query is compiled to the following code:  
Dim londonCusts = db.Customers.  
                  Where(Function(cust) cust.City = "London").  
                  Select(Function(cust) cust)  
```  
  
 <span data-ttu-id="e5f32-148">For more information about query methods, see [Queries](../../../visual-basic/language-reference/queries/index.md).</span><span class="sxs-lookup"><span data-stu-id="e5f32-148">For more information about query methods, see [Queries](../../../visual-basic/language-reference/queries/index.md).</span></span> <span data-ttu-id="e5f32-149">For more information about standard query operators, see [Standard Query Operators Overview](../../programming-guide/concepts/linq/standard-query-operators-overview.md).</span><span class="sxs-lookup"><span data-stu-id="e5f32-149">For more information about standard query operators, see [Standard Query Operators Overview](../../programming-guide/concepts/linq/standard-query-operators-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5f32-150">Vea también</span><span class="sxs-lookup"><span data-stu-id="e5f32-150">See also</span></span>

- [<span data-ttu-id="e5f32-151">Function (instrucción)</span><span class="sxs-lookup"><span data-stu-id="e5f32-151">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)
- [<span data-ttu-id="e5f32-152">Expresiones lambda</span><span class="sxs-lookup"><span data-stu-id="e5f32-152">Lambda Expressions</span></span>](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)
- [<span data-ttu-id="e5f32-153">Operadores y expresiones</span><span class="sxs-lookup"><span data-stu-id="e5f32-153">Operators and Expressions</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
- [<span data-ttu-id="e5f32-154">Instrucciones</span><span class="sxs-lookup"><span data-stu-id="e5f32-154">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
- [<span data-ttu-id="e5f32-155">Comparaciones de valores</span><span class="sxs-lookup"><span data-stu-id="e5f32-155">Value Comparisons</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md)
- [<span data-ttu-id="e5f32-156">Expresiones booleanas</span><span class="sxs-lookup"><span data-stu-id="e5f32-156">Boolean Expressions</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/boolean-expressions.md)
- [<span data-ttu-id="e5f32-157">If (operador)</span><span class="sxs-lookup"><span data-stu-id="e5f32-157">If Operator</span></span>](../../../visual-basic/language-reference/operators/if-operator.md)
- [<span data-ttu-id="e5f32-158">Conversión de delegado flexible</span><span class="sxs-lookup"><span data-stu-id="e5f32-158">Relaxed Delegate Conversion</span></span>](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)
