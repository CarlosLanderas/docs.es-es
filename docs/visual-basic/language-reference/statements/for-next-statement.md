---
title: For...Next (Instrucción)
ms.date: 07/20/2015
f1_keywords:
- vb.Step
- vb.Next
- vb.To
- vb.for
helpviewer_keywords:
- infinite loops
- Next keyword [Visual Basic], For...Next statements
- For keyword [Visual Basic], For...Next statements
- Step keyword [Visual Basic], For...Next statements
- operator overloading, For...Next statement
- To keyword [Visual Basic], For...Next statements
- endless loops
- loops, endless
- instructions, repeating
- Next statement [Visual Basic], For...Next
- For...Next statements
- loop structures [Visual Basic], For...Next
- loops, infinite
- Exit statement [Visual Basic], For...Next statements
- For statement [Visual Basic]
ms.assetid: f5fc0d51-67ce-4c36-9f09-31c9a91c94e9
ms.openlocfilehash: 3cae44abb8e790542f11e6c5a5f1e317675ff988
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351184"
---
# <a name="fornext-statement-visual-basic"></a><span data-ttu-id="f1a2f-102">Instrucción For...Next (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f1a2f-102">For...Next Statement (Visual Basic)</span></span>

<span data-ttu-id="f1a2f-103">Repeats a group of statements a specified number of times.</span><span class="sxs-lookup"><span data-stu-id="f1a2f-103">Repeats a group of statements a specified number of times.</span></span>

## <a name="syntax"></a><span data-ttu-id="f1a2f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f1a2f-104">Syntax</span></span>

```vb
For counter [ As datatype ] = start To end [ Step step ]
    [ statements ]
    [ Continue For ]
    [ statements ]
    [ Exit For ]
    [ statements ]
Next [ counter ]
```

## <a name="parts"></a><span data-ttu-id="f1a2f-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="f1a2f-105">Parts</span></span>

|<span data-ttu-id="f1a2f-106">Parte</span><span class="sxs-lookup"><span data-stu-id="f1a2f-106">Part</span></span>|<span data-ttu-id="f1a2f-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="f1a2f-107">Description</span></span>|
|----------|-----------------|
|`counter`|<span data-ttu-id="f1a2f-108">Required in the `For` statement.</span><span class="sxs-lookup"><span data-stu-id="f1a2f-108">Required in the `For` statement.</span></span> <span data-ttu-id="f1a2f-109">Numeric variable.</span><span class="sxs-lookup"><span data-stu-id="f1a2f-109">Numeric variable.</span></span> <span data-ttu-id="f1a2f-110">The control variable for the loop.</span><span class="sxs-lookup"><span data-stu-id="f1a2f-110">The control variable for the loop.</span></span> <span data-ttu-id="f1a2f-111">For more information, see [Counter Argument](#BKMK_Counter) later in this topic.</span><span class="sxs-lookup"><span data-stu-id="f1a2f-111">For more information, see [Counter Argument](#BKMK_Counter) later in this topic.</span></span>|
|`datatype`|<span data-ttu-id="f1a2f-112">Opcional.</span><span class="sxs-lookup"><span data-stu-id="f1a2f-112">Optional.</span></span> <span data-ttu-id="f1a2f-113">Data type of `counter`.</span><span class="sxs-lookup"><span data-stu-id="f1a2f-113">Data type of `counter`.</span></span> <span data-ttu-id="f1a2f-114">For more information, see [Counter Argument](#BKMK_Counter) later in this topic.</span><span class="sxs-lookup"><span data-stu-id="f1a2f-114">For more information, see [Counter Argument](#BKMK_Counter) later in this topic.</span></span>|
|`start`|<span data-ttu-id="f1a2f-115">Requerido.</span><span class="sxs-lookup"><span data-stu-id="f1a2f-115">Required.</span></span> <span data-ttu-id="f1a2f-116">Numeric expression.</span><span class="sxs-lookup"><span data-stu-id="f1a2f-116">Numeric expression.</span></span> <span data-ttu-id="f1a2f-117">Valor inicial de `counter`.</span><span class="sxs-lookup"><span data-stu-id="f1a2f-117">The initial value of `counter`.</span></span>|
|`end`|<span data-ttu-id="f1a2f-118">Requerido.</span><span class="sxs-lookup"><span data-stu-id="f1a2f-118">Required.</span></span> <span data-ttu-id="f1a2f-119">Numeric expression.</span><span class="sxs-lookup"><span data-stu-id="f1a2f-119">Numeric expression.</span></span> <span data-ttu-id="f1a2f-120">The final value of `counter`.</span><span class="sxs-lookup"><span data-stu-id="f1a2f-120">The final value of `counter`.</span></span>|
|`step`|<span data-ttu-id="f1a2f-121">Opcional.</span><span class="sxs-lookup"><span data-stu-id="f1a2f-121">Optional.</span></span> <span data-ttu-id="f1a2f-122">Numeric expression.</span><span class="sxs-lookup"><span data-stu-id="f1a2f-122">Numeric expression.</span></span> <span data-ttu-id="f1a2f-123">The amount by which `counter` is incremented each time through the loop.</span><span class="sxs-lookup"><span data-stu-id="f1a2f-123">The amount by which `counter` is incremented each time through the loop.</span></span>|
|`statements`|<span data-ttu-id="f1a2f-124">Opcional.</span><span class="sxs-lookup"><span data-stu-id="f1a2f-124">Optional.</span></span> <span data-ttu-id="f1a2f-125">One or more statements between `For` and `Next` that run the specified number of times.</span><span class="sxs-lookup"><span data-stu-id="f1a2f-125">One or more statements between `For` and `Next` that run the specified number of times.</span></span>|
|`Continue For`|<span data-ttu-id="f1a2f-126">Opcional.</span><span class="sxs-lookup"><span data-stu-id="f1a2f-126">Optional.</span></span> <span data-ttu-id="f1a2f-127">Transfers control to the next loop iteration.</span><span class="sxs-lookup"><span data-stu-id="f1a2f-127">Transfers control to the next loop iteration.</span></span>|
|`Exit For`|<span data-ttu-id="f1a2f-128">Opcional.</span><span class="sxs-lookup"><span data-stu-id="f1a2f-128">Optional.</span></span> <span data-ttu-id="f1a2f-129">Transfers control out of the `For` loop.</span><span class="sxs-lookup"><span data-stu-id="f1a2f-129">Transfers control out of the `For` loop.</span></span>|
|`Next`|<span data-ttu-id="f1a2f-130">Requerido.</span><span class="sxs-lookup"><span data-stu-id="f1a2f-130">Required.</span></span> <span data-ttu-id="f1a2f-131">Terminates the definition of the `For` loop.</span><span class="sxs-lookup"><span data-stu-id="f1a2f-131">Terminates the definition of the `For` loop.</span></span>|

> [!NOTE]
> <span data-ttu-id="f1a2f-132">The `To` keyword is used in this statement to specify the range for the counter.</span><span class="sxs-lookup"><span data-stu-id="f1a2f-132">The `To` keyword is used in this statement to specify the range for the counter.</span></span> <span data-ttu-id="f1a2f-133">You can also use this keyword in the [Select...Case Statement](../../../visual-basic/language-reference/statements/select-case-statement.md) and in array declarations.</span><span class="sxs-lookup"><span data-stu-id="f1a2f-133">You can also use this keyword in the [Select...Case Statement](../../../visual-basic/language-reference/statements/select-case-statement.md) and in array declarations.</span></span> <span data-ttu-id="f1a2f-134">For more information about array declarations, see [Dim Statement](../../../visual-basic/language-reference/statements/dim-statement.md).</span><span class="sxs-lookup"><span data-stu-id="f1a2f-134">For more information about array declarations, see [Dim Statement](../../../visual-basic/language-reference/statements/dim-statement.md).</span></span>

## <a name="simple-examples"></a><span data-ttu-id="f1a2f-135">Simple Examples</span><span class="sxs-lookup"><span data-stu-id="f1a2f-135">Simple Examples</span></span>

<span data-ttu-id="f1a2f-136">You use a `For`...`Next` structure when you want to repeat a set of statements a set number of times.</span><span class="sxs-lookup"><span data-stu-id="f1a2f-136">You use a `For`...`Next` structure when you want to repeat a set of statements a set number of times.</span></span>

<span data-ttu-id="f1a2f-137">In the following example, the `index` variable starts with a value of 1 and is incremented with each iteration of the loop, ending after the value of `index` reaches 5.</span><span class="sxs-lookup"><span data-stu-id="f1a2f-137">In the following example, the `index` variable starts with a value of 1 and is incremented with each iteration of the loop, ending after the value of `index` reaches 5.</span></span>

[!code-vb[VbVbalrStatements#111](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#111)]

<span data-ttu-id="f1a2f-138">In the following example, the `number` variable starts at 2 and is reduced by 0.25 on each iteration of the loop, ending after the value of `number` reaches 0.</span><span class="sxs-lookup"><span data-stu-id="f1a2f-138">In the following example, the `number` variable starts at 2 and is reduced by 0.25 on each iteration of the loop, ending after the value of `number` reaches 0.</span></span> <span data-ttu-id="f1a2f-139">The `Step` argument of `-.25` reduces the value by 0.25 on each iteration of the loop.</span><span class="sxs-lookup"><span data-stu-id="f1a2f-139">The `Step` argument of `-.25` reduces the value by 0.25 on each iteration of the loop.</span></span>

[!code-vb[VbVbalrStatements#112](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#112)]

> [!TIP]
> <span data-ttu-id="f1a2f-140">A [While...End While Statement](../../../visual-basic/language-reference/statements/while-end-while-statement.md) or [Do...Loop Statement](../../../visual-basic/language-reference/statements/do-loop-statement.md) works well when you don't know in advance how many times to run the statements in the loop.</span><span class="sxs-lookup"><span data-stu-id="f1a2f-140">A [While...End While Statement](../../../visual-basic/language-reference/statements/while-end-while-statement.md) or [Do...Loop Statement](../../../visual-basic/language-reference/statements/do-loop-statement.md) works well when you don't know in advance how many times to run the statements in the loop.</span></span> <span data-ttu-id="f1a2f-141">However, when you expect to run the loop a specific number of times, a `For`...`Next` loop is a better choice.</span><span class="sxs-lookup"><span data-stu-id="f1a2f-141">However, when you expect to run the loop a specific number of times, a `For`...`Next` loop is a better choice.</span></span> <span data-ttu-id="f1a2f-142">You determine the number of iterations when you first enter the loop.</span><span class="sxs-lookup"><span data-stu-id="f1a2f-142">You determine the number of iterations when you first enter the loop.</span></span>

## <a name="nesting-loops"></a><span data-ttu-id="f1a2f-143">Nesting Loops</span><span class="sxs-lookup"><span data-stu-id="f1a2f-143">Nesting Loops</span></span>

<span data-ttu-id="f1a2f-144">You can nest `For` loops by putting one loop within another.</span><span class="sxs-lookup"><span data-stu-id="f1a2f-144">You can nest `For` loops by putting one loop within another.</span></span> <span data-ttu-id="f1a2f-145">The following example demonstrates nested `For`...`Next` structures that have different step values.</span><span class="sxs-lookup"><span data-stu-id="f1a2f-145">The following example demonstrates nested `For`...`Next` structures that have different step values.</span></span> <span data-ttu-id="f1a2f-146">The outer loop creates a string for every iteration of the loop.</span><span class="sxs-lookup"><span data-stu-id="f1a2f-146">The outer loop creates a string for every iteration of the loop.</span></span> <span data-ttu-id="f1a2f-147">The inner loop decrements a loop counter variable for every iteration of the loop.</span><span class="sxs-lookup"><span data-stu-id="f1a2f-147">The inner loop decrements a loop counter variable for every iteration of the loop.</span></span>

[!code-vb[VbVbalrStatements#113](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#113)]

<span data-ttu-id="f1a2f-148">When nesting loops, each loop must have a unique `counter` variable.</span><span class="sxs-lookup"><span data-stu-id="f1a2f-148">When nesting loops, each loop must have a unique `counter` variable.</span></span>

<span data-ttu-id="f1a2f-149">You can also nest different kinds control structures within each other.</span><span class="sxs-lookup"><span data-stu-id="f1a2f-149">You can also nest different kinds control structures within each other.</span></span> <span data-ttu-id="f1a2f-150">For more information, see [Nested Control Structures](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md).</span><span class="sxs-lookup"><span data-stu-id="f1a2f-150">For more information, see [Nested Control Structures](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md).</span></span>

## <a name="exit-for-and-continue-for"></a><span data-ttu-id="f1a2f-151">Exit For and Continue For</span><span class="sxs-lookup"><span data-stu-id="f1a2f-151">Exit For and Continue For</span></span>

<span data-ttu-id="f1a2f-152">The `Exit For` statement immediately exits the `For`…`Next`</span><span class="sxs-lookup"><span data-stu-id="f1a2f-152">The `Exit For` statement immediately exits the `For`…`Next`</span></span> <span data-ttu-id="f1a2f-153">loop and transfers control to the statement that follows the `Next` statement.</span><span class="sxs-lookup"><span data-stu-id="f1a2f-153">loop and transfers control to the statement that follows the `Next` statement.</span></span>

<span data-ttu-id="f1a2f-154">The `Continue For` statement transfers control immediately to the next iteration of the loop.</span><span class="sxs-lookup"><span data-stu-id="f1a2f-154">The `Continue For` statement transfers control immediately to the next iteration of the loop.</span></span> <span data-ttu-id="f1a2f-155">For more information, see [Continue Statement](../../../visual-basic/language-reference/statements/continue-statement.md).</span><span class="sxs-lookup"><span data-stu-id="f1a2f-155">For more information, see [Continue Statement](../../../visual-basic/language-reference/statements/continue-statement.md).</span></span>

<span data-ttu-id="f1a2f-156">The following example illustrates the use of the `Continue For` and `Exit For` statements.</span><span class="sxs-lookup"><span data-stu-id="f1a2f-156">The following example illustrates the use of the `Continue For` and `Exit For` statements.</span></span>

[!code-vb[VbVbalrStatements#115](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#115)]

<span data-ttu-id="f1a2f-157">You can put any number of `Exit For` statements in a `For`…`Next`</span><span class="sxs-lookup"><span data-stu-id="f1a2f-157">You can put any number of `Exit For` statements in a `For`…`Next`</span></span> <span data-ttu-id="f1a2f-158">loop.</span><span class="sxs-lookup"><span data-stu-id="f1a2f-158">loop.</span></span> <span data-ttu-id="f1a2f-159">When used within nested `For`…`Next`</span><span class="sxs-lookup"><span data-stu-id="f1a2f-159">When used within nested `For`…`Next`</span></span> <span data-ttu-id="f1a2f-160">loops, `Exit For` exits the innermost loop and transfers control to the next higher level of nesting.</span><span class="sxs-lookup"><span data-stu-id="f1a2f-160">loops, `Exit For` exits the innermost loop and transfers control to the next higher level of nesting.</span></span>

<span data-ttu-id="f1a2f-161">`Exit For` is often used after you evaluate some condition (for example, in an `If`...`Then`...`Else` structure).</span><span class="sxs-lookup"><span data-stu-id="f1a2f-161">`Exit For` is often used after you evaluate some condition (for example, in an `If`...`Then`...`Else` structure).</span></span> <span data-ttu-id="f1a2f-162">You might want to use `Exit For` for the following conditions:</span><span class="sxs-lookup"><span data-stu-id="f1a2f-162">You might want to use `Exit For` for the following conditions:</span></span>

- <span data-ttu-id="f1a2f-163">Continuing to iterate is unnecessary or impossible.</span><span class="sxs-lookup"><span data-stu-id="f1a2f-163">Continuing to iterate is unnecessary or impossible.</span></span> <span data-ttu-id="f1a2f-164">An erroneous value or a termination request might create this condition.</span><span class="sxs-lookup"><span data-stu-id="f1a2f-164">An erroneous value or a termination request might create this condition.</span></span>

- <span data-ttu-id="f1a2f-165">A `Try`...`Catch`...`Finally` statement catches an exception.</span><span class="sxs-lookup"><span data-stu-id="f1a2f-165">A `Try`...`Catch`...`Finally` statement catches an exception.</span></span> <span data-ttu-id="f1a2f-166">You might use `Exit For` at the end of the `Finally` block.</span><span class="sxs-lookup"><span data-stu-id="f1a2f-166">You might use `Exit For` at the end of the `Finally` block.</span></span>

- <span data-ttu-id="f1a2f-167">You have an endless loop, which is a loop that could run a large or even infinite number of times.</span><span class="sxs-lookup"><span data-stu-id="f1a2f-167">You have an endless loop, which is a loop that could run a large or even infinite number of times.</span></span> <span data-ttu-id="f1a2f-168">If you detect such a condition, you can use `Exit For` to escape the loop.</span><span class="sxs-lookup"><span data-stu-id="f1a2f-168">If you detect such a condition, you can use `Exit For` to escape the loop.</span></span> <span data-ttu-id="f1a2f-169">For more information, see [Do...Loop Statement](../../../visual-basic/language-reference/statements/do-loop-statement.md).</span><span class="sxs-lookup"><span data-stu-id="f1a2f-169">For more information, see [Do...Loop Statement](../../../visual-basic/language-reference/statements/do-loop-statement.md).</span></span>

## <a name="technical-implementation"></a><span data-ttu-id="f1a2f-170">Implementación técnica</span><span class="sxs-lookup"><span data-stu-id="f1a2f-170">Technical Implementation</span></span>

<span data-ttu-id="f1a2f-171">When a `For`...`Next` loop starts, Visual Basic evaluates `start`, `end`, and `step`.</span><span class="sxs-lookup"><span data-stu-id="f1a2f-171">When a `For`...`Next` loop starts, Visual Basic evaluates `start`, `end`, and `step`.</span></span> <span data-ttu-id="f1a2f-172">Visual Basic evaluates these values only at this time and then assigns `start` to `counter`.</span><span class="sxs-lookup"><span data-stu-id="f1a2f-172">Visual Basic evaluates these values only at this time and then assigns `start` to `counter`.</span></span> <span data-ttu-id="f1a2f-173">Before the statement block runs, Visual Basic compares `counter` to `end`.</span><span class="sxs-lookup"><span data-stu-id="f1a2f-173">Before the statement block runs, Visual Basic compares `counter` to `end`.</span></span> <span data-ttu-id="f1a2f-174">If `counter` is already larger than the `end` value (or smaller if `step` is negative), the `For` loop ends and control passes to the statement that follows the `Next` statement.</span><span class="sxs-lookup"><span data-stu-id="f1a2f-174">If `counter` is already larger than the `end` value (or smaller if `step` is negative), the `For` loop ends and control passes to the statement that follows the `Next` statement.</span></span> <span data-ttu-id="f1a2f-175">Otherwise, the statement block runs.</span><span class="sxs-lookup"><span data-stu-id="f1a2f-175">Otherwise, the statement block runs.</span></span>

<span data-ttu-id="f1a2f-176">Each time Visual Basic encounters the `Next` statement, it increments `counter` by `step` and returns to the `For` statement.</span><span class="sxs-lookup"><span data-stu-id="f1a2f-176">Each time Visual Basic encounters the `Next` statement, it increments `counter` by `step` and returns to the `For` statement.</span></span> <span data-ttu-id="f1a2f-177">Again it compares `counter` to `end`, and again it either runs the block or exits the loop, depending on the result.</span><span class="sxs-lookup"><span data-stu-id="f1a2f-177">Again it compares `counter` to `end`, and again it either runs the block or exits the loop, depending on the result.</span></span> <span data-ttu-id="f1a2f-178">This process continues until `counter` passes `end` or an `Exit For` statement is encountered.</span><span class="sxs-lookup"><span data-stu-id="f1a2f-178">This process continues until `counter` passes `end` or an `Exit For` statement is encountered.</span></span>

<span data-ttu-id="f1a2f-179">The loop doesn't stop until `counter` has passed `end`.</span><span class="sxs-lookup"><span data-stu-id="f1a2f-179">The loop doesn't stop until `counter` has passed `end`.</span></span> <span data-ttu-id="f1a2f-180">If `counter` is equal to `end`, the loop continues.</span><span class="sxs-lookup"><span data-stu-id="f1a2f-180">If `counter` is equal to `end`, the loop continues.</span></span> <span data-ttu-id="f1a2f-181">The comparison that determines whether to run the block is `counter` <= `end` if `step` is positive and `counter` >= `end` if `step` is negative.</span><span class="sxs-lookup"><span data-stu-id="f1a2f-181">The comparison that determines whether to run the block is `counter` <= `end` if `step` is positive and `counter` >= `end` if `step` is negative.</span></span>

<span data-ttu-id="f1a2f-182">If you change the value of `counter` while inside a loop, your code might be more difficult to read and debug.</span><span class="sxs-lookup"><span data-stu-id="f1a2f-182">If you change the value of `counter` while inside a loop, your code might be more difficult to read and debug.</span></span> <span data-ttu-id="f1a2f-183">Changing the value of `start`, `end`, or `step` doesn't affect the iteration values that were determined when the loop was first entered.</span><span class="sxs-lookup"><span data-stu-id="f1a2f-183">Changing the value of `start`, `end`, or `step` doesn't affect the iteration values that were determined when the loop was first entered.</span></span>

<span data-ttu-id="f1a2f-184">If you nest loops, the compiler signals an error if it encounters the `Next` statement of an outer nesting level before the `Next` statement of an inner level.</span><span class="sxs-lookup"><span data-stu-id="f1a2f-184">If you nest loops, the compiler signals an error if it encounters the `Next` statement of an outer nesting level before the `Next` statement of an inner level.</span></span> <span data-ttu-id="f1a2f-185">However, the compiler can detect this overlapping error only if you specify `counter` in every `Next` statement.</span><span class="sxs-lookup"><span data-stu-id="f1a2f-185">However, the compiler can detect this overlapping error only if you specify `counter` in every `Next` statement.</span></span>

### <a name="step-argument"></a><span data-ttu-id="f1a2f-186">Step Argument</span><span class="sxs-lookup"><span data-stu-id="f1a2f-186">Step Argument</span></span>

<span data-ttu-id="f1a2f-187">The value of `step` can be either positive or negative.</span><span class="sxs-lookup"><span data-stu-id="f1a2f-187">The value of `step` can be either positive or negative.</span></span> <span data-ttu-id="f1a2f-188">This parameter determines loop processing according to the following table:</span><span class="sxs-lookup"><span data-stu-id="f1a2f-188">This parameter determines loop processing according to the following table:</span></span>

|<span data-ttu-id="f1a2f-189">**Step value**</span><span class="sxs-lookup"><span data-stu-id="f1a2f-189">**Step value**</span></span>|<span data-ttu-id="f1a2f-190">**Loop executes if**</span><span class="sxs-lookup"><span data-stu-id="f1a2f-190">**Loop executes if**</span></span>|
|--------------------|--------------------------|
|<span data-ttu-id="f1a2f-191">Positive or zero</span><span class="sxs-lookup"><span data-stu-id="f1a2f-191">Positive or zero</span></span>|`counter` <= `end`|
|<span data-ttu-id="f1a2f-192">Negativo</span><span class="sxs-lookup"><span data-stu-id="f1a2f-192">Negative</span></span>|`counter` >= `end`|

<span data-ttu-id="f1a2f-193">The default value of `step` is 1.</span><span class="sxs-lookup"><span data-stu-id="f1a2f-193">The default value of `step` is 1.</span></span>

### <a name="BKMK_Counter"></a> <span data-ttu-id="f1a2f-194">Counter Argument</span><span class="sxs-lookup"><span data-stu-id="f1a2f-194">Counter Argument</span></span>

<span data-ttu-id="f1a2f-195">The following table indicates whether `counter` defines a new local variable that’s scoped to the entire `For…Next` loop.</span><span class="sxs-lookup"><span data-stu-id="f1a2f-195">The following table indicates whether `counter` defines a new local variable that’s scoped to the entire `For…Next` loop.</span></span> <span data-ttu-id="f1a2f-196">This determination depends on whether `datatype` is present and whether `counter` is already defined.</span><span class="sxs-lookup"><span data-stu-id="f1a2f-196">This determination depends on whether `datatype` is present and whether `counter` is already defined.</span></span>

|<span data-ttu-id="f1a2f-197">Is `datatype` present?</span><span class="sxs-lookup"><span data-stu-id="f1a2f-197">Is `datatype` present?</span></span>|<span data-ttu-id="f1a2f-198">Is `counter` already defined?</span><span class="sxs-lookup"><span data-stu-id="f1a2f-198">Is `counter` already defined?</span></span>|<span data-ttu-id="f1a2f-199">Result (whether `counter` defines a new local variable that’s scoped to the entire `For...Next` loop)</span><span class="sxs-lookup"><span data-stu-id="f1a2f-199">Result (whether `counter` defines a new local variable that’s scoped to the entire `For...Next` loop)</span></span>|
|----------------------------|-----------------------------------|-------------------------------------------------------------------------------------------------------------|
|<span data-ttu-id="f1a2f-200">No</span><span class="sxs-lookup"><span data-stu-id="f1a2f-200">No</span></span>|<span data-ttu-id="f1a2f-201">Sí</span><span class="sxs-lookup"><span data-stu-id="f1a2f-201">Yes</span></span>|<span data-ttu-id="f1a2f-202">No, because `counter` is already defined.</span><span class="sxs-lookup"><span data-stu-id="f1a2f-202">No, because `counter` is already defined.</span></span> <span data-ttu-id="f1a2f-203">If the scope of `counter` isn't local to the procedure, a compile-time warning occurs.</span><span class="sxs-lookup"><span data-stu-id="f1a2f-203">If the scope of `counter` isn't local to the procedure, a compile-time warning occurs.</span></span>|
|<span data-ttu-id="f1a2f-204">No</span><span class="sxs-lookup"><span data-stu-id="f1a2f-204">No</span></span>|<span data-ttu-id="f1a2f-205">No</span><span class="sxs-lookup"><span data-stu-id="f1a2f-205">No</span></span>|<span data-ttu-id="f1a2f-206">Sí.</span><span class="sxs-lookup"><span data-stu-id="f1a2f-206">Yes.</span></span> <span data-ttu-id="f1a2f-207">The data type is inferred from the `start`, `end`, and `step` expressions.</span><span class="sxs-lookup"><span data-stu-id="f1a2f-207">The data type is inferred from the `start`, `end`, and `step` expressions.</span></span> <span data-ttu-id="f1a2f-208">For information about type inference, see [Option Infer Statement](../../../visual-basic/language-reference/statements/option-infer-statement.md) and [Local Type Inference](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).</span><span class="sxs-lookup"><span data-stu-id="f1a2f-208">For information about type inference, see [Option Infer Statement](../../../visual-basic/language-reference/statements/option-infer-statement.md) and [Local Type Inference](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).</span></span>|
|<span data-ttu-id="f1a2f-209">Sí</span><span class="sxs-lookup"><span data-stu-id="f1a2f-209">Yes</span></span>|<span data-ttu-id="f1a2f-210">Sí</span><span class="sxs-lookup"><span data-stu-id="f1a2f-210">Yes</span></span>|<span data-ttu-id="f1a2f-211">Yes, but only if the existing `counter` variable is defined outside the procedure.</span><span class="sxs-lookup"><span data-stu-id="f1a2f-211">Yes, but only if the existing `counter` variable is defined outside the procedure.</span></span> <span data-ttu-id="f1a2f-212">That variable remains separate.</span><span class="sxs-lookup"><span data-stu-id="f1a2f-212">That variable remains separate.</span></span> <span data-ttu-id="f1a2f-213">If the scope of the existing `counter` variable is local to the procedure, a compile-time error occurs.</span><span class="sxs-lookup"><span data-stu-id="f1a2f-213">If the scope of the existing `counter` variable is local to the procedure, a compile-time error occurs.</span></span>|
|<span data-ttu-id="f1a2f-214">Sí</span><span class="sxs-lookup"><span data-stu-id="f1a2f-214">Yes</span></span>|<span data-ttu-id="f1a2f-215">No</span><span class="sxs-lookup"><span data-stu-id="f1a2f-215">No</span></span>|<span data-ttu-id="f1a2f-216">Sí.</span><span class="sxs-lookup"><span data-stu-id="f1a2f-216">Yes.</span></span>|

<span data-ttu-id="f1a2f-217">The data type of `counter` determines the type of the iteration, which must be one of the following types:</span><span class="sxs-lookup"><span data-stu-id="f1a2f-217">The data type of `counter` determines the type of the iteration, which must be one of the following types:</span></span>

- <span data-ttu-id="f1a2f-218">A `Byte`, `SByte`, `UShort`, `Short`, `UInteger`, `Integer`, `ULong`, `Long`, `Decimal`, `Single`, or `Double`.</span><span class="sxs-lookup"><span data-stu-id="f1a2f-218">A `Byte`, `SByte`, `UShort`, `Short`, `UInteger`, `Integer`, `ULong`, `Long`, `Decimal`, `Single`, or `Double`.</span></span>

- <span data-ttu-id="f1a2f-219">An enumeration that you declare by using an [Enum Statement](../../../visual-basic/language-reference/statements/enum-statement.md).</span><span class="sxs-lookup"><span data-stu-id="f1a2f-219">An enumeration that you declare by using an [Enum Statement](../../../visual-basic/language-reference/statements/enum-statement.md).</span></span>

- <span data-ttu-id="f1a2f-220">Interfaz `Object`.</span><span class="sxs-lookup"><span data-stu-id="f1a2f-220">An `Object`.</span></span>

- <span data-ttu-id="f1a2f-221">A type `T` that has the following operators, where `B` is a type that can be used in a `Boolean` expression.</span><span class="sxs-lookup"><span data-stu-id="f1a2f-221">A type `T` that has the following operators, where `B` is a type that can be used in a `Boolean` expression.</span></span>

  `Public Shared Operator >= (op1 As T, op2 As T) As B`

  `Public Shared Operator <= (op1 As T, op2 As T) As B`

  `Public Shared Operator - (op1 As T, op2 As T) As T`

  `Public Shared Operator + (op1 As T, op2 As T) As T`

<span data-ttu-id="f1a2f-222">You can optionally specify the `counter` variable in the `Next` statement.</span><span class="sxs-lookup"><span data-stu-id="f1a2f-222">You can optionally specify the `counter` variable in the `Next` statement.</span></span> <span data-ttu-id="f1a2f-223">This syntax improves the readability of your program, especially if you have nested `For` loops.</span><span class="sxs-lookup"><span data-stu-id="f1a2f-223">This syntax improves the readability of your program, especially if you have nested `For` loops.</span></span> <span data-ttu-id="f1a2f-224">You must specify the variable that appears in the corresponding `For` statement.</span><span class="sxs-lookup"><span data-stu-id="f1a2f-224">You must specify the variable that appears in the corresponding `For` statement.</span></span>

<span data-ttu-id="f1a2f-225">The `start`, `end`, and `step` expressions can evaluate to any data type that widens to the type of `counter`.</span><span class="sxs-lookup"><span data-stu-id="f1a2f-225">The `start`, `end`, and `step` expressions can evaluate to any data type that widens to the type of `counter`.</span></span> <span data-ttu-id="f1a2f-226">If you use a user-defined type for `counter`, you might have to define the `CType` conversion operator to convert the types of `start`, `end`, or `step` to the type of `counter`.</span><span class="sxs-lookup"><span data-stu-id="f1a2f-226">If you use a user-defined type for `counter`, you might have to define the `CType` conversion operator to convert the types of `start`, `end`, or `step` to the type of `counter`.</span></span>

## <a name="example"></a><span data-ttu-id="f1a2f-227">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f1a2f-227">Example</span></span>

<span data-ttu-id="f1a2f-228">The following example removes all elements from a generic list.</span><span class="sxs-lookup"><span data-stu-id="f1a2f-228">The following example removes all elements from a generic list.</span></span> <span data-ttu-id="f1a2f-229">Instead of a [For Each...Next Statement](../../../visual-basic/language-reference/statements/for-each-next-statement.md), the example shows a `For`...`Next` statement that iterates in descending order.</span><span class="sxs-lookup"><span data-stu-id="f1a2f-229">Instead of a [For Each...Next Statement](../../../visual-basic/language-reference/statements/for-each-next-statement.md), the example shows a `For`...`Next` statement that iterates in descending order.</span></span> <span data-ttu-id="f1a2f-230">The example uses this technique because the `removeAt` method causes elements after the removed element to have a lower index value.</span><span class="sxs-lookup"><span data-stu-id="f1a2f-230">The example uses this technique because the `removeAt` method causes elements after the removed element to have a lower index value.</span></span>

[!code-vb[VbVbalrStatements#114](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#114)]

## <a name="example"></a><span data-ttu-id="f1a2f-231">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f1a2f-231">Example</span></span>

<span data-ttu-id="f1a2f-232">The following example iterates through an enumeration that's declared by using an [Enum Statement](../../../visual-basic/language-reference/statements/enum-statement.md).</span><span class="sxs-lookup"><span data-stu-id="f1a2f-232">The following example iterates through an enumeration that's declared by using an [Enum Statement](../../../visual-basic/language-reference/statements/enum-statement.md).</span></span>

[!code-vb[VbVbalrStatements#116](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#116)]

## <a name="example"></a><span data-ttu-id="f1a2f-233">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f1a2f-233">Example</span></span>

<span data-ttu-id="f1a2f-234">In the following example, the statement parameters use a class that has operator overloads for the `+`, `-`, `>=`, and `<=` operators.</span><span class="sxs-lookup"><span data-stu-id="f1a2f-234">In the following example, the statement parameters use a class that has operator overloads for the `+`, `-`, `>=`, and `<=` operators.</span></span>

[!code-vb[VbVbalrStatements#117](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#117)]

## <a name="see-also"></a><span data-ttu-id="f1a2f-235">Vea también</span><span class="sxs-lookup"><span data-stu-id="f1a2f-235">See also</span></span>

- <xref:System.Collections.Generic.List%601>
- [<span data-ttu-id="f1a2f-236">Estructuras de bucle</span><span class="sxs-lookup"><span data-stu-id="f1a2f-236">Loop Structures</span></span>](../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
- [<span data-ttu-id="f1a2f-237">While...End While (instrucción)</span><span class="sxs-lookup"><span data-stu-id="f1a2f-237">While...End While Statement</span></span>](../../../visual-basic/language-reference/statements/while-end-while-statement.md)
- [<span data-ttu-id="f1a2f-238">Do...Loop (instrucción)</span><span class="sxs-lookup"><span data-stu-id="f1a2f-238">Do...Loop Statement</span></span>](../../../visual-basic/language-reference/statements/do-loop-statement.md)
- [<span data-ttu-id="f1a2f-239">Estructuras de control anidadas</span><span class="sxs-lookup"><span data-stu-id="f1a2f-239">Nested Control Structures</span></span>](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)
- [<span data-ttu-id="f1a2f-240">Exit (instrucción)</span><span class="sxs-lookup"><span data-stu-id="f1a2f-240">Exit Statement</span></span>](../../../visual-basic/language-reference/statements/exit-statement.md)
- [<span data-ttu-id="f1a2f-241">Colecciones</span><span class="sxs-lookup"><span data-stu-id="f1a2f-241">Collections</span></span>](../../programming-guide/concepts/collections.md)
