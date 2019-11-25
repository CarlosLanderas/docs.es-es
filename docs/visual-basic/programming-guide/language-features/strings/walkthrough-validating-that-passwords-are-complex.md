---
title: Validating Passwords Complexity
ms.date: 07/20/2015
helpviewer_keywords:
- String data type [Visual Basic], validation
ms.assetid: 5d9a918f-6c1f-41a3-a019-b5c2b8ce0381
ms.openlocfilehash: 6e8697379a6fbb5cc15b60291e5b822897c2c013
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348332"
---
# <a name="walkthrough-validating-that-passwords-are-complex-visual-basic"></a><span data-ttu-id="13761-102">Tutorial: Validar la complejidad de las contraseñas (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="13761-102">Walkthrough: Validating That Passwords Are Complex (Visual Basic)</span></span>
<span data-ttu-id="13761-103">This method checks for some strong-password characteristics and updates a string parameter with information about which checks the password fails.</span><span class="sxs-lookup"><span data-stu-id="13761-103">This method checks for some strong-password characteristics and updates a string parameter with information about which checks the password fails.</span></span>  
  
 <span data-ttu-id="13761-104">Passwords can be used in a secure system to authorize a user.</span><span class="sxs-lookup"><span data-stu-id="13761-104">Passwords can be used in a secure system to authorize a user.</span></span> <span data-ttu-id="13761-105">However, the passwords must be difficult for unauthorized users to guess.</span><span class="sxs-lookup"><span data-stu-id="13761-105">However, the passwords must be difficult for unauthorized users to guess.</span></span> <span data-ttu-id="13761-106">Attackers can use a *dictionary attack* program, which iterates through all of the words in a dictionary (or multiple dictionaries in different languages) and tests whether any of the words work as a user's password.</span><span class="sxs-lookup"><span data-stu-id="13761-106">Attackers can use a *dictionary attack* program, which iterates through all of the words in a dictionary (or multiple dictionaries in different languages) and tests whether any of the words work as a user's password.</span></span> <span data-ttu-id="13761-107">Weak passwords such as "Yankees" or "Mustang" can be guessed quickly.</span><span class="sxs-lookup"><span data-stu-id="13761-107">Weak passwords such as "Yankees" or "Mustang" can be guessed quickly.</span></span> <span data-ttu-id="13761-108">Stronger passwords, such as "?You'L1N3vaFiNdMeyeP@sSWerd!", are much less likely to be guessed.</span><span class="sxs-lookup"><span data-stu-id="13761-108">Stronger passwords, such as "?You'L1N3vaFiNdMeyeP@sSWerd!", are much less likely to be guessed.</span></span> <span data-ttu-id="13761-109">A password-protected system should ensure that users choose strong passwords.</span><span class="sxs-lookup"><span data-stu-id="13761-109">A password-protected system should ensure that users choose strong passwords.</span></span>  
  
 <span data-ttu-id="13761-110">A strong password is complex (containing a mixture of uppercase, lowercase, numeric, and special characters) and is not a word.</span><span class="sxs-lookup"><span data-stu-id="13761-110">A strong password is complex (containing a mixture of uppercase, lowercase, numeric, and special characters) and is not a word.</span></span> <span data-ttu-id="13761-111">This example demonstrates how to verify complexity.</span><span class="sxs-lookup"><span data-stu-id="13761-111">This example demonstrates how to verify complexity.</span></span>  
  
## <a name="example"></a><span data-ttu-id="13761-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="13761-112">Example</span></span>  
  
### <a name="code"></a><span data-ttu-id="13761-113">Código</span><span class="sxs-lookup"><span data-stu-id="13761-113">Code</span></span>  
 [!code-vb[VbVbcnRegEx#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnRegEx/VB/Class1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="13761-114">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="13761-114">Compiling the Code</span></span>  
 <span data-ttu-id="13761-115">Call this method by passing the string that contains that password.</span><span class="sxs-lookup"><span data-stu-id="13761-115">Call this method by passing the string that contains that password.</span></span>  
  
 <span data-ttu-id="13761-116">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="13761-116">This example requires:</span></span>  
  
- <span data-ttu-id="13761-117">Acceso a los miembros del espacio de nombres <xref:System.Text.RegularExpressions>.</span><span class="sxs-lookup"><span data-stu-id="13761-117">Access to the members of the <xref:System.Text.RegularExpressions> namespace.</span></span> <span data-ttu-id="13761-118">Agregue una instrucción `Imports` si no hay nombres de miembros completos en el código.</span><span class="sxs-lookup"><span data-stu-id="13761-118">Add an `Imports` statement if you are not fully qualifying member names in your code.</span></span> <span data-ttu-id="13761-119">Para obtener más información, consulte [Instrucción Imports (Tipo y espacio de nombres de .NET)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).</span><span class="sxs-lookup"><span data-stu-id="13761-119">For more information, see [Imports Statement (.NET Namespace and Type)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).</span></span>  
  
## <a name="security"></a><span data-ttu-id="13761-120">Seguridad</span><span class="sxs-lookup"><span data-stu-id="13761-120">Security</span></span>  
 <span data-ttu-id="13761-121">If you're moving the password across a network, you need to use a secure method for transferring data.</span><span class="sxs-lookup"><span data-stu-id="13761-121">If you're moving the password across a network, you need to use a secure method for transferring data.</span></span> <span data-ttu-id="13761-122">For more information, see [ASP.NET Web Application Security](https://docs.microsoft.com/previous-versions/aspnet/330a99hc(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="13761-122">For more information, see [ASP.NET Web Application Security](https://docs.microsoft.com/previous-versions/aspnet/330a99hc(v=vs.100)).</span></span>
  
 <span data-ttu-id="13761-123">You can improve the accuracy of the `ValidatePassword` function by adding additional complexity checks:</span><span class="sxs-lookup"><span data-stu-id="13761-123">You can improve the accuracy of the `ValidatePassword` function by adding additional complexity checks:</span></span>  
  
- <span data-ttu-id="13761-124">Compare the password and its substrings against the user's name, user identifier, and an application-defined dictionary.</span><span class="sxs-lookup"><span data-stu-id="13761-124">Compare the password and its substrings against the user's name, user identifier, and an application-defined dictionary.</span></span> <span data-ttu-id="13761-125">In addition, treat visually similar characters as equivalent when performing the comparisons.</span><span class="sxs-lookup"><span data-stu-id="13761-125">In addition, treat visually similar characters as equivalent when performing the comparisons.</span></span> <span data-ttu-id="13761-126">For example, treat the letters "l" and "e" as equivalent to the numerals "1" and "3".</span><span class="sxs-lookup"><span data-stu-id="13761-126">For example, treat the letters "l" and "e" as equivalent to the numerals "1" and "3".</span></span>  
  
- <span data-ttu-id="13761-127">If there is only one uppercase character, make sure it is not the password's first character.</span><span class="sxs-lookup"><span data-stu-id="13761-127">If there is only one uppercase character, make sure it is not the password's first character.</span></span>  
  
- <span data-ttu-id="13761-128">Make sure that the last two characters of the password are letter characters.</span><span class="sxs-lookup"><span data-stu-id="13761-128">Make sure that the last two characters of the password are letter characters.</span></span>  
  
- <span data-ttu-id="13761-129">Do not allow passwords in which all the symbols are entered from the keyboard's top row.</span><span class="sxs-lookup"><span data-stu-id="13761-129">Do not allow passwords in which all the symbols are entered from the keyboard's top row.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13761-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="13761-130">See also</span></span>

- <xref:System.Text.RegularExpressions.Regex>
- <span data-ttu-id="13761-131">[Seguridad de aplicaciones Web ASP.NET](https://docs.microsoft.com/previous-versions/aspnet/330a99hc(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="13761-131">[ASP.NET Web Application Security](https://docs.microsoft.com/previous-versions/aspnet/330a99hc(v=vs.100))</span></span>
