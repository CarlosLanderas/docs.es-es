---
title: -warnaserror
ms.date: 03/13/2018
helpviewer_keywords:
- warnaserror compiler option [Visual Basic]
- /warnaserror compiler option [Visual Basic]
- -warnaserror compiler option [Visual Basic]
ms.assetid: 49819f1d-a1bd-4201-affe-5afe6d9712e1
ms.openlocfilehash: f9ca5575e2a042d68fc490494f2e86991d58b80c
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351705"
---
# <a name="-warnaserror-visual-basic"></a><span data-ttu-id="e5eca-102">-warnaserror (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e5eca-102">-warnaserror (Visual Basic)</span></span>
<span data-ttu-id="e5eca-103">Causa que el compilador trate como un error la primera ocurrencia de una advertencia.</span><span class="sxs-lookup"><span data-stu-id="e5eca-103">Causes the compiler to treat the first occurrence of a warning as an error.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e5eca-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e5eca-104">Syntax</span></span>  
  
```console  
-warnaserror[+ | -][:numberList]  
```  
  
## <a name="arguments"></a><span data-ttu-id="e5eca-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="e5eca-105">Arguments</span></span>  
  
|<span data-ttu-id="e5eca-106">Término</span><span class="sxs-lookup"><span data-stu-id="e5eca-106">Term</span></span>|<span data-ttu-id="e5eca-107">Definición</span><span class="sxs-lookup"><span data-stu-id="e5eca-107">Definition</span></span>|  
|---|---|  
|<span data-ttu-id="e5eca-108">+ &#124; -</span><span class="sxs-lookup"><span data-stu-id="e5eca-108">+ &#124; -</span></span>|<span data-ttu-id="e5eca-109">Opcional.</span><span class="sxs-lookup"><span data-stu-id="e5eca-109">Optional.</span></span> <span data-ttu-id="e5eca-110">De forma predeterminada, se aplica `-warnaserror-`; las advertencias no impiden que el compilador genere un archivo de salida.</span><span class="sxs-lookup"><span data-stu-id="e5eca-110">By default, `-warnaserror-` is in effect; warnings do not prevent the compiler from producing an output file.</span></span> <span data-ttu-id="e5eca-111">La opción `-warnaserror`, que es la misma que `-warnaserror+`, causa que las advertencias se traten como errores.</span><span class="sxs-lookup"><span data-stu-id="e5eca-111">The `-warnaserror` option, which is the same as `-warnaserror+`, causes warnings to be treated as errors.</span></span>|  
|`numberList`|<span data-ttu-id="e5eca-112">Opcional.</span><span class="sxs-lookup"><span data-stu-id="e5eca-112">Optional.</span></span> <span data-ttu-id="e5eca-113">Lista delimitada por comas de los números de identificadores de advertencia a los que se aplica la opción `-warnaserror`.</span><span class="sxs-lookup"><span data-stu-id="e5eca-113">Comma-delimited list of the warning ID numbers to which the `-warnaserror` option applies.</span></span> <span data-ttu-id="e5eca-114">Si no se especifica ningún identificador de advertencia, la opción `-warnaserror` se aplica a todas las advertencias.</span><span class="sxs-lookup"><span data-stu-id="e5eca-114">If no warning ID is specified, the `-warnaserror` option applies to all warnings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e5eca-115">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e5eca-115">Remarks</span></span>  
 <span data-ttu-id="e5eca-116">La opción `-warnaserror` trata todas las advertencias como errores.</span><span class="sxs-lookup"><span data-stu-id="e5eca-116">The `-warnaserror` option treats all warnings as errors.</span></span> <span data-ttu-id="e5eca-117">Todos los mensajes que, por norma general, deberían notificarse como advertencias, en su lugar se registran como errores.</span><span class="sxs-lookup"><span data-stu-id="e5eca-117">Any messages that would ordinarily be reported as warnings are instead reported as errors.</span></span> <span data-ttu-id="e5eca-118">El compilador notifica como advertencias las ocurrencias posteriores de la misma advertencia.</span><span class="sxs-lookup"><span data-stu-id="e5eca-118">The compiler reports subsequent occurrences of the same warning as warnings.</span></span>  
  
 <span data-ttu-id="e5eca-119">De forma predeterminada, se aplica `-warnaserror-`, que da lugar a que las advertencias tengan solo carácter informativo.</span><span class="sxs-lookup"><span data-stu-id="e5eca-119">By default, `-warnaserror-` is in effect, which causes the warnings to be informational only.</span></span> <span data-ttu-id="e5eca-120">La opción `-warnaserror`, que es la misma que `-warnaserror+`, causa que las advertencias se traten como errores.</span><span class="sxs-lookup"><span data-stu-id="e5eca-120">The `-warnaserror` option, which is the same as `-warnaserror+`, causes warnings to be treated as errors.</span></span>  
  
 <span data-ttu-id="e5eca-121">Si desea que solo algunas advertencias específicas se traten como errores, puede especificar una lista separada por comas de números de advertencias que se deben tratar como errores.</span><span class="sxs-lookup"><span data-stu-id="e5eca-121">If you want only a few specific warnings to be treated as errors, you may specify a comma-separated list of warning numbers to treat as errors.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e5eca-122">La opción `-warnaserror` no controla cómo se muestran las advertencias.</span><span class="sxs-lookup"><span data-stu-id="e5eca-122">The `-warnaserror` option does not control how warnings are displayed.</span></span> <span data-ttu-id="e5eca-123">Use la opción [-nowarn](../../../visual-basic/reference/command-line-compiler/nowarn.md) para deshabilitar las advertencias.</span><span class="sxs-lookup"><span data-stu-id="e5eca-123">Use the [-nowarn](../../../visual-basic/reference/command-line-compiler/nowarn.md) option to disable warnings.</span></span>  
  
|<span data-ttu-id="e5eca-124">Para establecer -warnaserror a fin de tratar todas las advertencias como errores en el IDE de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="e5eca-124">To set -warnaserror to treat all warnings as errors in the Visual Studio IDE</span></span>|  
|---|  
|<span data-ttu-id="e5eca-125">1. tener un proyecto seleccionado en **Explorador de soluciones**.</span><span class="sxs-lookup"><span data-stu-id="e5eca-125">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="e5eca-126">En el menú **Proyecto**, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="e5eca-126">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="e5eca-127">2. Haga clic en la pestaña **compilar** .</span><span class="sxs-lookup"><span data-stu-id="e5eca-127">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="e5eca-128">3. Asegúrese de que la casilla **deshabilitar todas las advertencias** esté desactivada.</span><span class="sxs-lookup"><span data-stu-id="e5eca-128">3.  Make sure the **Disable all warnings** check box is unchecked.</span></span><br /><span data-ttu-id="e5eca-129">4. Active la casilla **tratar todas las advertencias como errores** .</span><span class="sxs-lookup"><span data-stu-id="e5eca-129">4.  Check the **Treat all warnings as errors** check box.</span></span>|  
  
|<span data-ttu-id="e5eca-130">Para establecer - warnaserror a fin de tratar advertencias específicas como errores en el IDE de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="e5eca-130">To set -warnaserror to treat specific warnings as errors in the Visual Studio IDE</span></span>|  
|---|  
|<span data-ttu-id="e5eca-131">1. tener un proyecto seleccionado en **Explorador de soluciones**.</span><span class="sxs-lookup"><span data-stu-id="e5eca-131">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="e5eca-132">En el menú **Proyecto**, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="e5eca-132">On the **Project** menu, click **Properties**.</span></span><br /><span data-ttu-id="e5eca-133">2. Haga clic en la pestaña **compilar** .</span><span class="sxs-lookup"><span data-stu-id="e5eca-133">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="e5eca-134">3. Asegúrese de que la casilla **deshabilitar todas las advertencias** esté desactivada.</span><span class="sxs-lookup"><span data-stu-id="e5eca-134">3.  Make sure the **Disable all warnings** check box is unchecked.</span></span><br /><span data-ttu-id="e5eca-135">4. Asegúrese de que la casilla **tratar todas las advertencias como errores** esté desactivada.</span><span class="sxs-lookup"><span data-stu-id="e5eca-135">4.  Make sure the **Treat all warnings as errors** check box is unchecked.</span></span><br /><span data-ttu-id="e5eca-136">5. Seleccione **error** en la columna **notificación** adyacente a la advertencia que se debe tratar como un error.</span><span class="sxs-lookup"><span data-stu-id="e5eca-136">5.  Select **Error** from the **Notification** column adjacent to the warning that should be treated as an error.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="e5eca-137">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e5eca-137">Example</span></span>  
 <span data-ttu-id="e5eca-138">El siguiente código compila `In.vb` y ordena al compilador que muestre un error para la primera ocurrencia de cada advertencia que encuentra.</span><span class="sxs-lookup"><span data-stu-id="e5eca-138">The following code compiles `In.vb` and directs the compiler to display an error for the first occurrence of every warning it finds.</span></span>  
  
```console
vbc -warnaserror in.vb  
```  
  
## <a name="example"></a><span data-ttu-id="e5eca-139">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e5eca-139">Example</span></span>  
 <span data-ttu-id="e5eca-140">El siguiente código compila `T2.vb` y trata como un error solo la advertencia para las variables locales no utilizadas (42024).</span><span class="sxs-lookup"><span data-stu-id="e5eca-140">The following code compiles `T2.vb` and treats only the warning for unused local variables (42024) as an error.</span></span>  
  
```console
vbc -warnaserror:42024 t2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="e5eca-141">Vea también</span><span class="sxs-lookup"><span data-stu-id="e5eca-141">See also</span></span>

- [<span data-ttu-id="e5eca-142">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e5eca-142">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="e5eca-143">Líneas de comandos de compilación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="e5eca-143">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [<span data-ttu-id="e5eca-144">Configuring Warnings in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e5eca-144">Configuring Warnings in Visual Basic</span></span>](/visualstudio/ide/configuring-warnings-in-visual-basic)
