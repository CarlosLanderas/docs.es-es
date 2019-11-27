---
title: 'Cómo: crear un procedimiento'
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- Visual Basic code, reusing
- procedure declarations
- procedures [Visual Basic], about procedures
ms.assetid: 4f779247-0b50-47e8-9e5c-ab5cf39ac0d2
ms.openlocfilehash: a831814c18f97991fca8067f1c9c8e491da1b665
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344910"
---
# <a name="how-to-create-a-procedure-visual-basic"></a><span data-ttu-id="58780-102">Cómo: Crear un procedimiento (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="58780-102">How to: Create a Procedure (Visual Basic)</span></span>

<span data-ttu-id="58780-103">Puede incluir un procedimiento entre una instrucción de declaración de inicio (`Sub` o `Function`) y una instrucción de declaración de finalización (`End Sub` o `End Function`).</span><span class="sxs-lookup"><span data-stu-id="58780-103">You enclose a procedure between a starting declaration statement (`Sub` or `Function`) and an ending declaration statement (`End Sub` or `End Function`).</span></span> <span data-ttu-id="58780-104">Todo el código del procedimiento se encuentra entre estas instrucciones.</span><span class="sxs-lookup"><span data-stu-id="58780-104">All the procedure's code lies between these statements.</span></span>

 <span data-ttu-id="58780-105">Un procedimiento no puede contener otro procedimiento, por lo que sus instrucciones de inicio y finalización deben estar fuera de cualquier otro procedimiento.</span><span class="sxs-lookup"><span data-stu-id="58780-105">A procedure cannot contain another procedure, so its starting and ending statements must be outside any other procedure.</span></span>

 <span data-ttu-id="58780-106">Si tiene código que realiza la misma tarea en distintos lugares, puede escribir la tarea una vez como un procedimiento y, a continuación, llamarla desde distintos lugares del código.</span><span class="sxs-lookup"><span data-stu-id="58780-106">If you have code that performs the same task in different places, you can write the task once as a procedure and then call it from different places in your code.</span></span>

### <a name="to-create-a-procedure-that-does-not-return-a-value"></a><span data-ttu-id="58780-107">Para crear un procedimiento que no devuelve un valor</span><span class="sxs-lookup"><span data-stu-id="58780-107">To create a procedure that does not return a value</span></span>

1. <span data-ttu-id="58780-108">Fuera de cualquier otro procedimiento, use una instrucción `Sub`, seguida de una instrucción `End Sub`.</span><span class="sxs-lookup"><span data-stu-id="58780-108">Outside any other procedure, use a `Sub` statement, followed by an `End Sub` statement.</span></span>

2. <span data-ttu-id="58780-109">En la instrucción `Sub`, siga la palabra clave `Sub` con el nombre del procedimiento y, a continuación, la lista de parámetros entre paréntesis.</span><span class="sxs-lookup"><span data-stu-id="58780-109">In the `Sub` statement, follow the `Sub` keyword with the name of the procedure, then the parameter list in parentheses.</span></span>

3. <span data-ttu-id="58780-110">Coloque las instrucciones de código del procedimiento entre las instrucciones `Sub` y `End Sub`.</span><span class="sxs-lookup"><span data-stu-id="58780-110">Place the procedure's code statements between the `Sub` and `End Sub` statements.</span></span>

### <a name="to-create-a-procedure-that-returns-a-value"></a><span data-ttu-id="58780-111">Para crear un procedimiento que devuelve un valor</span><span class="sxs-lookup"><span data-stu-id="58780-111">To create a procedure that returns a value</span></span>

1. <span data-ttu-id="58780-112">Fuera de cualquier otro procedimiento, use una instrucción `Function`, seguida de una instrucción `End Function`.</span><span class="sxs-lookup"><span data-stu-id="58780-112">Outside any other procedure, use a `Function` statement, followed by an `End Function` statement.</span></span>

2. <span data-ttu-id="58780-113">En la instrucción `Function`, siga la palabra clave `Function` con el nombre del procedimiento, la lista de parámetros entre paréntesis y, a continuación, una cláusula `As` que especifique el tipo de datos del valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="58780-113">In the `Function` statement, follow the `Function` keyword with the name of the procedure, then the parameter list in parentheses, and then an `As` clause specifying the data type of the return value.</span></span>

3. <span data-ttu-id="58780-114">Coloque las instrucciones de código del procedimiento entre las instrucciones `Function` y `End Function`.</span><span class="sxs-lookup"><span data-stu-id="58780-114">Place the procedure's code statements between the `Function` and `End Function` statements.</span></span>

4. <span data-ttu-id="58780-115">Use una instrucción `Return` para devolver el valor al código de llamada.</span><span class="sxs-lookup"><span data-stu-id="58780-115">Use a `Return` statement to return the value to the calling code.</span></span>

### <a name="to-connect-your-new-procedure-with-the-old-repetitive-blocks-of-code"></a><span data-ttu-id="58780-116">Para conectar el nuevo procedimiento con los bloques de código repetitivos anteriores</span><span class="sxs-lookup"><span data-stu-id="58780-116">To connect your new procedure with the old, repetitive blocks of code</span></span>

1. <span data-ttu-id="58780-117">Asegúrese de definir el nuevo procedimiento en un lugar donde el código anterior tenga acceso a él.</span><span class="sxs-lookup"><span data-stu-id="58780-117">Make sure you define the new procedure in a place where the old code has access to it.</span></span>

2. <span data-ttu-id="58780-118">En el bloque de código anterior, repetitivo, reemplace las instrucciones que realizan la tarea repetitiva con una única instrucción que llama al procedimiento `Sub` o `Function`.</span><span class="sxs-lookup"><span data-stu-id="58780-118">In your old, repetitive code block, replace the statements that perform the repetitive task with a single statement that calls the `Sub` or `Function` procedure.</span></span>

3. <span data-ttu-id="58780-119">Si el procedimiento es una `Function` que devuelve un valor, asegúrese de que la instrucción de llamada realiza una acción con el valor devuelto, como el almacenamiento en una variable, o bien se perderá el valor.</span><span class="sxs-lookup"><span data-stu-id="58780-119">If your procedure is a `Function` that returns a value, ensure that your calling statement performs an action with the returned value, such as storing it in a variable, or else the value will be lost.</span></span>

## <a name="example"></a><span data-ttu-id="58780-120">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="58780-120">Example</span></span>

 <span data-ttu-id="58780-121">En el procedimiento `Function` siguiente se calcula el lado más largo o la hipotenusa de un triángulo de la derecha, dados los valores de los otros dos lados:</span><span class="sxs-lookup"><span data-stu-id="58780-121">The following `Function` procedure calculates the longest side, or hypotenuse, of a right triangle, given the values for the other two sides:</span></span>

 [!code-vb[VbVbcnProcedures#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#1)]

## <a name="see-also"></a><span data-ttu-id="58780-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="58780-122">See also</span></span>

- [<span data-ttu-id="58780-123">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="58780-123">Procedures</span></span>](index.md)
- [<span data-ttu-id="58780-124">Subprocedimientos</span><span class="sxs-lookup"><span data-stu-id="58780-124">Sub Procedures</span></span>](sub-procedures.md)
- [<span data-ttu-id="58780-125">Procedimientos de función</span><span class="sxs-lookup"><span data-stu-id="58780-125">Function Procedures</span></span>](function-procedures.md)
- [<span data-ttu-id="58780-126">Procedimientos de propiedades</span><span class="sxs-lookup"><span data-stu-id="58780-126">Property Procedures</span></span>](property-procedures.md)
- [<span data-ttu-id="58780-127">Procedimientos de operadores</span><span class="sxs-lookup"><span data-stu-id="58780-127">Operator Procedures</span></span>](operator-procedures.md)
- [<span data-ttu-id="58780-128">Argumentos y parámetros de procedimiento</span><span class="sxs-lookup"><span data-stu-id="58780-128">Procedure Parameters and Arguments</span></span>](procedure-parameters-and-arguments.md)
- [<span data-ttu-id="58780-129">Procedimientos recursivos</span><span class="sxs-lookup"><span data-stu-id="58780-129">Recursive Procedures</span></span>](recursive-procedures.md)
- [<span data-ttu-id="58780-130">Sobrecarga de procedimientos</span><span class="sxs-lookup"><span data-stu-id="58780-130">Procedure Overloading</span></span>](procedure-overloading.md)
- [<span data-ttu-id="58780-131">Objetos y clases</span><span class="sxs-lookup"><span data-stu-id="58780-131">Objects and Classes</span></span>](../objects-and-classes/index.md)
- [<span data-ttu-id="58780-132">Programación orientada a objetos (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="58780-132">Object-Oriented Programming (Visual Basic)</span></span>](../../concepts/object-oriented-programming.md)
