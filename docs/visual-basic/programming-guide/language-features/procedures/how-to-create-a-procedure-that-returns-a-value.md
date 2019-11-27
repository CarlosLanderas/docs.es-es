---
title: 'Cómo: Crear un procedimiento que devuelve un valor'
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- procedures [Visual Basic], returning a value
ms.assetid: 8ee19f95-a9ef-4033-963b-d224dca207c4
ms.openlocfilehash: 218dbb52abc0100724d38d10be91ef24252d5226
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349719"
---
# <a name="how-to-create-a-procedure-that-returns-a-value-visual-basic"></a><span data-ttu-id="e9cb9-102">Cómo: Crear un procedimiento que devuelve un valor (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e9cb9-102">How to: Create a Procedure that Returns a Value (Visual Basic)</span></span>
<span data-ttu-id="e9cb9-103">El procedimiento `Function` se usa para devolver un valor al código de llamada.</span><span class="sxs-lookup"><span data-stu-id="e9cb9-103">You use a `Function` procedure to return a value to the calling code.</span></span>  
  
### <a name="to-create-a-procedure-that-returns-a-value"></a><span data-ttu-id="e9cb9-104">Para crear un procedimiento que devuelve un valor</span><span class="sxs-lookup"><span data-stu-id="e9cb9-104">To create a procedure that returns a value</span></span>  
  
1. <span data-ttu-id="e9cb9-105">Fuera de cualquier otro procedimiento, use una instrucción `Function`, seguida de una instrucción `End Function`.</span><span class="sxs-lookup"><span data-stu-id="e9cb9-105">Outside any other procedure, use a `Function` statement, followed by an `End Function` statement.</span></span>  
  
2. <span data-ttu-id="e9cb9-106">En la instrucción `Function`, siga la palabra clave `Function` con el nombre del procedimiento y, a continuación, la lista de parámetros entre paréntesis.</span><span class="sxs-lookup"><span data-stu-id="e9cb9-106">In the `Function` statement, follow the `Function` keyword with the name of the procedure, and then the parameter list in parentheses.</span></span>  
  
3. <span data-ttu-id="e9cb9-107">Siga los paréntesis con una cláusula `As` para especificar el tipo de datos del valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="e9cb9-107">Follow the parentheses with an `As` clause to specify the data type of the returned value.</span></span>  
  
4. <span data-ttu-id="e9cb9-108">Coloque las instrucciones de código del procedimiento entre las instrucciones `Function` y `End Function`.</span><span class="sxs-lookup"><span data-stu-id="e9cb9-108">Place the procedure's code statements between the `Function` and `End Function` statements.</span></span>  
  
5. <span data-ttu-id="e9cb9-109">Use una instrucción `Return` para devolver el valor al código de llamada.</span><span class="sxs-lookup"><span data-stu-id="e9cb9-109">Use a `Return` statement to return the value to the calling code.</span></span>  
  
     <span data-ttu-id="e9cb9-110">En el procedimiento `Function` siguiente se calcula el lado más largo o la hipotenusa de un triángulo de la derecha, dados los valores de los otros dos lados.</span><span class="sxs-lookup"><span data-stu-id="e9cb9-110">The following `Function` procedure calculates the longest side, or hypotenuse, of a right triangle, given the values for the other two sides.</span></span>  
  
     [!code-vb[VbVbcnProcedures#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#1)]  
  
     <span data-ttu-id="e9cb9-111">En el ejemplo siguiente se muestra una llamada típica a `hypotenuse`.</span><span class="sxs-lookup"><span data-stu-id="e9cb9-111">The following example shows a typical call to `hypotenuse`.</span></span>  
  
     [!code-vb[VbVbcnProcedures#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="e9cb9-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="e9cb9-112">See also</span></span>

- [<span data-ttu-id="e9cb9-113">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="e9cb9-113">Procedures</span></span>](./index.md)
- [<span data-ttu-id="e9cb9-114">Subprocedimientos</span><span class="sxs-lookup"><span data-stu-id="e9cb9-114">Sub Procedures</span></span>](./sub-procedures.md)
- [<span data-ttu-id="e9cb9-115">Procedimientos de propiedades</span><span class="sxs-lookup"><span data-stu-id="e9cb9-115">Property Procedures</span></span>](./property-procedures.md)
- [<span data-ttu-id="e9cb9-116">Procedimientos de operadores</span><span class="sxs-lookup"><span data-stu-id="e9cb9-116">Operator Procedures</span></span>](./operator-procedures.md)
- [<span data-ttu-id="e9cb9-117">Argumentos y parámetros de procedimiento</span><span class="sxs-lookup"><span data-stu-id="e9cb9-117">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="e9cb9-118">Function (instrucción)</span><span class="sxs-lookup"><span data-stu-id="e9cb9-118">Function Statement</span></span>](../../../../visual-basic/language-reference/statements/function-statement.md)
- [<span data-ttu-id="e9cb9-119">Devolver un valor de un procedimiento</span><span class="sxs-lookup"><span data-stu-id="e9cb9-119">How to: Return a Value from a Procedure</span></span>](./how-to-return-a-value-from-a-procedure.md)
- [<span data-ttu-id="e9cb9-120">Llamar a un procedimiento que devuelve un valor</span><span class="sxs-lookup"><span data-stu-id="e9cb9-120">How to: Call a Procedure That Returns a Value</span></span>](./how-to-call-a-procedure-that-returns-a-value.md)
