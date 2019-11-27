---
title: '#Directiva Const'
ms.date: 07/20/2015
f1_keywords:
- vb.#Const
- '#vb.Const'
- '#Const'
helpviewer_keywords:
- '#Const directive'
- conditional compilation [Visual Basic], directives
- Const directive (#Const)
- Visual Basic compiler, compiler directives
- constants [Visual Basic], Const directive
- constants [Visual Basic], declaring
- Const statement [Visual Basic], directive (#Const)
- 'declaring constants [Visual Basic], #const directive'
ms.assetid: 707669e5-23f9-4f17-8622-a0d534429386
ms.openlocfilehash: 278219edb1bb5d1c0bb015611d69cbe4ae70014b
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74343842"
---
# <a name="const-directive"></a><span data-ttu-id="2cbab-102">#Const (Directiva)</span><span class="sxs-lookup"><span data-stu-id="2cbab-102">#Const Directive</span></span>

<span data-ttu-id="2cbab-103">Define constantes de compilador condicionales para Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="2cbab-103">Defines conditional compiler constants for Visual Basic.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2cbab-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2cbab-104">Syntax</span></span>  
  
```vb  
#Const constname = expression  
```  
  
## <a name="parts"></a><span data-ttu-id="2cbab-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="2cbab-105">Parts</span></span>  

 `constname`  
 <span data-ttu-id="2cbab-106">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="2cbab-106">Required.</span></span> <span data-ttu-id="2cbab-107">Nombre de la constante que se está definiendo.</span><span class="sxs-lookup"><span data-stu-id="2cbab-107">Name of the constant being defined.</span></span>  
  
 `expression`  
 <span data-ttu-id="2cbab-108">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="2cbab-108">Required.</span></span> <span data-ttu-id="2cbab-109">Literal, otra constante del compilador condicional o cualquier combinación que incluya todos o todos los operadores aritméticos o lógicos excepto `Is`.</span><span class="sxs-lookup"><span data-stu-id="2cbab-109">Literal, other conditional compiler constant, or any combination that includes any or all arithmetic or logical operators except `Is`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2cbab-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="2cbab-110">Remarks</span></span>  

 <span data-ttu-id="2cbab-111">Las constantes de compilador condicionales siempre son privadas en el archivo en el que aparecen.</span><span class="sxs-lookup"><span data-stu-id="2cbab-111">Conditional compiler constants are always private to the file in which they appear.</span></span> <span data-ttu-id="2cbab-112">No se pueden crear constantes del compilador públicas mediante la Directiva `#Const`; solo puede crearlos en la interfaz de usuario o con la opción del compilador `/define`.</span><span class="sxs-lookup"><span data-stu-id="2cbab-112">You cannot create public compiler constants using the `#Const` directive; you can create them only in the user interface or with the `/define` compiler option.</span></span>  
  
 <span data-ttu-id="2cbab-113">Solo se pueden usar constantes y literales de compilador condicionales en `expression`.</span><span class="sxs-lookup"><span data-stu-id="2cbab-113">You can use only conditional compiler constants and literals in `expression`.</span></span> <span data-ttu-id="2cbab-114">El uso de una constante estándar definida con `Const` produce un error.</span><span class="sxs-lookup"><span data-stu-id="2cbab-114">Using a standard constant defined with `Const` causes an error.</span></span> <span data-ttu-id="2cbab-115">Por el contrario, puede usar constantes definidas con la palabra clave `#Const` solo para la compilación condicional.</span><span class="sxs-lookup"><span data-stu-id="2cbab-115">Conversely, you can use constants defined with the `#Const` keyword only for conditional compilation.</span></span> <span data-ttu-id="2cbab-116">Las constantes también pueden ser undefined, en cuyo caso tienen un valor de `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="2cbab-116">Constants can also be undefined, in which case they have a value of `Nothing`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2cbab-117">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="2cbab-117">Example</span></span>  

 <span data-ttu-id="2cbab-118">En este ejemplo se usa la directiva `#Const`.</span><span class="sxs-lookup"><span data-stu-id="2cbab-118">This example uses the `#Const` directive.</span></span>  
  
 [!code-vb[VbVbalrConditionalComp#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConditionalComp/VB/Class1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="2cbab-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="2cbab-119">See also</span></span>

- [<span data-ttu-id="2cbab-120">-define (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2cbab-120">-define (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/define.md)
- [<span data-ttu-id="2cbab-121">#If...Then...#Else (directivas)</span><span class="sxs-lookup"><span data-stu-id="2cbab-121">#If...Then...#Else Directives</span></span>](../../../visual-basic/language-reference/directives/if-then-else-directives.md)
- [<span data-ttu-id="2cbab-122">Const (instrucción)</span><span class="sxs-lookup"><span data-stu-id="2cbab-122">Const Statement</span></span>](../../../visual-basic/language-reference/statements/const-statement.md)
- [<span data-ttu-id="2cbab-123">Compilación condicional</span><span class="sxs-lookup"><span data-stu-id="2cbab-123">Conditional Compilation</span></span>](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
- [<span data-ttu-id="2cbab-124">If...Then...Else (instrucción)</span><span class="sxs-lookup"><span data-stu-id="2cbab-124">If...Then...Else Statement</span></span>](../../../visual-basic/language-reference/statements/if-then-else-statement.md)
