---
title: Throw (Instrucción)
ms.date: 07/20/2015
f1_keywords:
- vb.Throw
helpviewer_keywords:
- structured exception handling, throw statements
- try-catch exception handling, throw statements
- throw statement [Visual Basic], about throw statements
- throwing exceptions, throw statement
- exception handling, throw statement
- On Error statement [Visual Basic], throwing exceptions
- throwing exceptions
- exception handling, unstructured
- throw statement [Visual Basic]
ms.assetid: a6e07406-5c8a-4498-87a2-8339f3651d62
ms.openlocfilehash: 147345990b625e034e651e69b322bc098d0bd8de
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352789"
---
# <a name="throw-statement-visual-basic"></a><span data-ttu-id="0e955-102">Throw (Instrucción, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0e955-102">Throw Statement (Visual Basic)</span></span>

<span data-ttu-id="0e955-103">Throws an exception within a procedure.</span><span class="sxs-lookup"><span data-stu-id="0e955-103">Throws an exception within a procedure.</span></span>

## <a name="syntax"></a><span data-ttu-id="0e955-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0e955-104">Syntax</span></span>

```vb
Throw [ expression ]
```

## <a name="part"></a><span data-ttu-id="0e955-105">Parte</span><span class="sxs-lookup"><span data-stu-id="0e955-105">Part</span></span>

`expression`\
<span data-ttu-id="0e955-106">Provides information about the exception to be thrown.</span><span class="sxs-lookup"><span data-stu-id="0e955-106">Provides information about the exception to be thrown.</span></span> <span data-ttu-id="0e955-107">Optional when residing in a `Catch` statement, otherwise required.</span><span class="sxs-lookup"><span data-stu-id="0e955-107">Optional when residing in a `Catch` statement, otherwise required.</span></span>

## <a name="remarks"></a><span data-ttu-id="0e955-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="0e955-108">Remarks</span></span>

<span data-ttu-id="0e955-109">The `Throw` statement throws an exception that you can handle with structured exception-handling code (`Try`...`Catch`...`Finally`) or unstructured exception-handling code (`On Error GoTo`).</span><span class="sxs-lookup"><span data-stu-id="0e955-109">The `Throw` statement throws an exception that you can handle with structured exception-handling code (`Try`...`Catch`...`Finally`) or unstructured exception-handling code (`On Error GoTo`).</span></span> <span data-ttu-id="0e955-110">You can use the `Throw` statement to trap errors within your code because Visual Basic moves up the call stack until it finds the appropriate exception-handling code.</span><span class="sxs-lookup"><span data-stu-id="0e955-110">You can use the `Throw` statement to trap errors within your code because Visual Basic moves up the call stack until it finds the appropriate exception-handling code.</span></span>

<span data-ttu-id="0e955-111">A `Throw` statement with no expression can only be used in a `Catch` statement, in which case the statement rethrows the exception currently being handled by the `Catch` statement.</span><span class="sxs-lookup"><span data-stu-id="0e955-111">A `Throw` statement with no expression can only be used in a `Catch` statement, in which case the statement rethrows the exception currently being handled by the `Catch` statement.</span></span>

<span data-ttu-id="0e955-112">The `Throw` statement resets the call stack for the `expression` exception.</span><span class="sxs-lookup"><span data-stu-id="0e955-112">The `Throw` statement resets the call stack for the `expression` exception.</span></span> <span data-ttu-id="0e955-113">If `expression` is not provided, the call stack is left unchanged.</span><span class="sxs-lookup"><span data-stu-id="0e955-113">If `expression` is not provided, the call stack is left unchanged.</span></span> <span data-ttu-id="0e955-114">You can access the call stack for the exception through the <xref:System.Exception.StackTrace%2A> property.</span><span class="sxs-lookup"><span data-stu-id="0e955-114">You can access the call stack for the exception through the <xref:System.Exception.StackTrace%2A> property.</span></span>

## <a name="example"></a><span data-ttu-id="0e955-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0e955-115">Example</span></span>

<span data-ttu-id="0e955-116">The following code uses the `Throw` statement to throw an exception:</span><span class="sxs-lookup"><span data-stu-id="0e955-116">The following code uses the `Throw` statement to throw an exception:</span></span>

[!code-vb[VbVbalrStatements#84](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#84)]

## <a name="see-also"></a><span data-ttu-id="0e955-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="0e955-117">See also</span></span>

- [<span data-ttu-id="0e955-118">Try...Catch...Finally (instrucción)</span><span class="sxs-lookup"><span data-stu-id="0e955-118">Try...Catch...Finally Statement</span></span>](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
- [<span data-ttu-id="0e955-119">On Error (instrucción)</span><span class="sxs-lookup"><span data-stu-id="0e955-119">On Error Statement</span></span>](../../../visual-basic/language-reference/statements/on-error-statement.md)
