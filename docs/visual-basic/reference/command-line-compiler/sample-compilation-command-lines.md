---
title: Líneas de comandos de compilación de ejemplo
ms.date: 03/13/2018
helpviewer_keywords:
- command line [Visual Basic], compilers
- compilation [Visual Basic], command-line
- command-line compilers
- compiling source code [Visual Basic], from command line
- Visual Basic compiler, sample command lines
ms.assetid: 5bfbb487-5f47-4267-969a-39dfb917beeb
ms.openlocfilehash: 27a20a5a3525353ffbced729b8ac9c98b3e48fc1
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350853"
---
# <a name="sample-compilation-command-lines-visual-basic"></a><span data-ttu-id="ad956-102">Líneas de comandos de compilación de ejemplo (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ad956-102">Sample compilation command lines (Visual Basic)</span></span>

<span data-ttu-id="ad956-103">Como alternativa a la compilación de programas Visual Basic desde Visual Studio, puede compilar desde la línea de comandos para generar archivos ejecutables (. exe) o archivos de biblioteca de vínculos dinámicos (. dll).</span><span class="sxs-lookup"><span data-stu-id="ad956-103">As an alternative to compiling Visual Basic programs from within Visual Studio, you can compile from the command line to produce executable (.exe) files or dynamic-link library (.dll) files.</span></span>

<span data-ttu-id="ad956-104">El compilador de línea de comandos de Visual Basic admite un conjunto completo de opciones que controlan los archivos de entrada y salida, los ensamblados y las opciones de depuración y preprocesador.</span><span class="sxs-lookup"><span data-stu-id="ad956-104">The Visual Basic command-line compiler supports a complete set of options that control input and output files, assemblies, and debug and preprocessor options.</span></span> <span data-ttu-id="ad956-105">Cada opción está disponible en dos formas intercambiables: `-option` y `/option`.</span><span class="sxs-lookup"><span data-stu-id="ad956-105">Each option is available in two interchangeable forms: `-option` and `/option`.</span></span> <span data-ttu-id="ad956-106">En esta documentación solo se muestra el formulario `-option`.</span><span class="sxs-lookup"><span data-stu-id="ad956-106">This documentation shows only the `-option` form.</span></span>

<span data-ttu-id="ad956-107">En la tabla siguiente se enumeran algunas líneas de comandos de ejemplo que puede modificar para su propio uso.</span><span class="sxs-lookup"><span data-stu-id="ad956-107">The following table lists some sample command lines you can modify for your own use.</span></span>

|<span data-ttu-id="ad956-108">Para</span><span class="sxs-lookup"><span data-stu-id="ad956-108">To</span></span>|<span data-ttu-id="ad956-109">Uso</span><span class="sxs-lookup"><span data-stu-id="ad956-109">Use</span></span>|
|--------|---------|
|<span data-ttu-id="ad956-110">Compile File. VB y cree File. exe</span><span class="sxs-lookup"><span data-stu-id="ad956-110">Compile File.vb and create File.exe</span></span>|`vbc -reference:Microsoft.VisualBasic.dll File.vb`|
|<span data-ttu-id="ad956-111">Compile File. VB y cree File. dll</span><span class="sxs-lookup"><span data-stu-id="ad956-111">Compile File.vb and create File.dll</span></span>|`vbc -target:library File.vb`|
|<span data-ttu-id="ad956-112">Compile File. VB y cree My. exe</span><span class="sxs-lookup"><span data-stu-id="ad956-112">Compile File.vb and create My.exe</span></span>|`vbc -out:My.exe File.vb`|
|<span data-ttu-id="ad956-113">Compile File. VB y cree una biblioteca y un ensamblado de referencia denominado File. dll.</span><span class="sxs-lookup"><span data-stu-id="ad956-113">Compile File.vb and create both a library and a reference assembly named File.dll</span></span>|`vbc -target:library -ref:.\debug\bin\ref\file.dll File.vb`|
|<span data-ttu-id="ad956-114">Compilar todos los archivos Visual Basic en el directorio actual, con optimizaciones en y el símbolo de `DEBUG` definido, produciendo archivo2. exe</span><span class="sxs-lookup"><span data-stu-id="ad956-114">Compile all Visual Basic files in the current directory, with optimizations on and the `DEBUG` symbol defined, producing File2.exe</span></span>|`vbc -define:DEBUG=1 -optimize -out:File2.exe *.vb`|
|<span data-ttu-id="ad956-115">Compilar todos los archivos Visual Basic en el directorio actual, generando una versión de depuración de archivo2. dll sin mostrar el logotipo o las advertencias</span><span class="sxs-lookup"><span data-stu-id="ad956-115">Compile all Visual Basic files in the current directory, producing a debug version of File2.dll without displaying the logo or warnings</span></span>|`vbc -target:library -out:File2.dll -nowarn -nologo -debug *.vb`|
|<span data-ttu-id="ad956-116">Compilar todos los archivos Visual Basic del directorio actual en un archivo. dll</span><span class="sxs-lookup"><span data-stu-id="ad956-116">Compile all Visual Basic files in the current directory to Something.dll</span></span>|`vbc -target:library -out:Something.dll *.vb`|

> [!TIP]
> <span data-ttu-id="ad956-117">Al compilar un proyecto mediante el IDE de Visual Studio, puede mostrar información sobre el comando de **VBC** asociado con sus opciones del compilador en la ventana salida.</span><span class="sxs-lookup"><span data-stu-id="ad956-117">When you build a project by using the Visual Studio IDE, you can display information about the associated **vbc** command with its compiler options in the output window.</span></span> <span data-ttu-id="ad956-118">Para mostrar esta información, abra el [cuadro de diálogo Opciones, proyectos y soluciones, compilar y ejecutar](/visualstudio/ide/reference/options-dialog-box-projects-and-solutions-build-and-run)y, a continuación, establezca el nivel de detalle de la salida de la **compilación del proyecto de MSBuild** en **normal** o en un nivel más alto de detalle.</span><span class="sxs-lookup"><span data-stu-id="ad956-118">To display this information, open the [Options Dialog Box,  Projects and Solutions, Build and Run](/visualstudio/ide/reference/options-dialog-box-projects-and-solutions-build-and-run), and then set the **MSBuild project build output verbosity** to **Normal** or a higher level of verbosity.</span></span>

## <a name="see-also"></a><span data-ttu-id="ad956-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="ad956-119">See also</span></span>

- [<span data-ttu-id="ad956-120">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ad956-120">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="ad956-121">Compilación condicional</span><span class="sxs-lookup"><span data-stu-id="ad956-121">Conditional Compilation</span></span>](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
