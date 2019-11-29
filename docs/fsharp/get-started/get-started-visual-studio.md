---
title: Introducción a F# en Visual Studio
description: Obtenga información sobre cómo F# usar con Visual Studio.
ms.date: 07/03/2018
ms.openlocfilehash: 80b4fc5b7631eace719832fe32003cad578ead27
ms.sourcegitcommit: 93762e1a0dae1b5f64d82eebb7b705a6d566d839
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/27/2019
ms.locfileid: "74552827"
---
# <a name="get-started-with-f-in-visual-studio"></a><span data-ttu-id="74907-103">Introducción a F# en Visual Studio</span><span class="sxs-lookup"><span data-stu-id="74907-103">Get started with F# in Visual Studio</span></span>

<span data-ttu-id="74907-104">F#y las herramientas F# visuales se admiten en el IDE de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="74907-104">F# and the Visual F# tooling are supported in the Visual Studio IDE.</span></span>

<span data-ttu-id="74907-105">Para empezar, asegúrese de que tiene [Visual Studio instalado con F# ](install-fsharp.md#install-f-with-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="74907-105">To begin, ensure that you have [Visual Studio installed with F#](install-fsharp.md#install-f-with-visual-studio).</span></span>

## <a name="creating-a-console-application"></a><span data-ttu-id="74907-106">Creación de una aplicación de consola</span><span class="sxs-lookup"><span data-stu-id="74907-106">Creating a console application</span></span>

<span data-ttu-id="74907-107">Uno de los proyectos más básicos de Visual Studio es la aplicación de consola.</span><span class="sxs-lookup"><span data-stu-id="74907-107">One of the most basic projects in Visual Studio is the Console Application.</span></span>  <span data-ttu-id="74907-108">A continuación le mostramos cómo hacerlo.</span><span class="sxs-lookup"><span data-stu-id="74907-108">Here's how to do it.</span></span>  <span data-ttu-id="74907-109">Una vez que Visual Studio está abierto:</span><span class="sxs-lookup"><span data-stu-id="74907-109">Once Visual Studio is open:</span></span>

1. <span data-ttu-id="74907-110">En el menú **archivo** , elija **nuevo**y, a continuación, elija **proyecto**.</span><span class="sxs-lookup"><span data-stu-id="74907-110">On the **File** menu, point to **New**, and then choose **Project**.</span></span>

2. <span data-ttu-id="74907-111">En el cuadro de diálogo nuevo proyecto, en **plantillas**, debería **Ver F#visual** .</span><span class="sxs-lookup"><span data-stu-id="74907-111">In the New Project dialog, under **Templates**, you should see **Visual F#**.</span></span>  <span data-ttu-id="74907-112">Elija esta opción para mostrar F# las plantillas.</span><span class="sxs-lookup"><span data-stu-id="74907-112">Choose this to show the F# templates.</span></span>

3. <span data-ttu-id="74907-113">Seleccione **aplicación de consola de .net Core** o **aplicación de consola**.</span><span class="sxs-lookup"><span data-stu-id="74907-113">Select either **.NET Core Console app** or **Console app**.</span></span>

4. <span data-ttu-id="74907-114">Elija el botón **Aceptar** para crear el F# proyecto.</span><span class="sxs-lookup"><span data-stu-id="74907-114">Choose the **Okay** button to create the F# project!</span></span>  <span data-ttu-id="74907-115">Ahora debería ver un F# proyecto en el explorador de soluciones.</span><span class="sxs-lookup"><span data-stu-id="74907-115">You should now see an F# project in the Solution Explorer.</span></span>

## <a name="writing-your-code"></a><span data-ttu-id="74907-116">Escritura del código</span><span class="sxs-lookup"><span data-stu-id="74907-116">Writing your code</span></span>

<span data-ttu-id="74907-117">Vamos a empezar por escribir código primero.</span><span class="sxs-lookup"><span data-stu-id="74907-117">Let's get started by writing some code first.</span></span>  <span data-ttu-id="74907-118">Asegúrese de que el archivo de `Program.fs` está abierto y, a continuación, reemplace el contenido por lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="74907-118">Make sure that the `Program.fs` file is open, and then replace its contents with the following:</span></span>

[!code-fsharp[HelloSquare](~/samples/snippets/fsharp/getting-started/hello-square.fs)]

<span data-ttu-id="74907-119">En el ejemplo de código anterior, se ha definido una función `square` que toma una entrada denominada `x` y la multiplica por sí misma.</span><span class="sxs-lookup"><span data-stu-id="74907-119">In the previous code sample, a function `square` has been defined which takes an input named `x` and multiplies it by itself.</span></span>  <span data-ttu-id="74907-120">Dado F# que utiliza la [inferencia de tipos](../language-reference/type-inference.md), no es necesario especificar el tipo de `x`.</span><span class="sxs-lookup"><span data-stu-id="74907-120">Because F# uses [Type Inference](../language-reference/type-inference.md), the type of `x` doesn't need to be specified.</span></span>  <span data-ttu-id="74907-121">El F# compilador entiende los tipos en los que la multiplicación es válida y asignará un tipo a `x` basándose en cómo se llama a `square`.</span><span class="sxs-lookup"><span data-stu-id="74907-121">The F# compiler understands the types where multiplication is valid, and will assign a type to `x` based on how `square` is called.</span></span>  <span data-ttu-id="74907-122">Si mantiene el mouse sobre `square`, debería ver lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="74907-122">If you hover over `square`, you should see the following:</span></span>

```fsharp
val square: x:int -> int
```

<span data-ttu-id="74907-123">Esto es lo que se conoce como la firma de tipo de la función.</span><span class="sxs-lookup"><span data-stu-id="74907-123">This is what is known as the function's type signature.</span></span>  <span data-ttu-id="74907-124">Se puede leer de la siguiente manera: "Square es una función que toma un entero denominado x y genera un entero".</span><span class="sxs-lookup"><span data-stu-id="74907-124">It can be read like this: "Square is a function which takes an integer named x and produces an integer".</span></span>  <span data-ttu-id="74907-125">Tenga en cuenta que el compilador dio `square` el tipo de `int` por ahora: esto se debe a que la multiplicación no es genérica en *todos los* tipos, sino que es genérica en un conjunto cerrado de tipos.</span><span class="sxs-lookup"><span data-stu-id="74907-125">Note that the compiler gave `square` the `int` type for now - this is because multiplication is not generic across *all* types, but rather is generic across a closed set of types.</span></span>  <span data-ttu-id="74907-126">El F# compilador eligió `int` en este punto, pero ajustará la firma del tipo si llama a `square` con un tipo de entrada diferente, como un `float`.</span><span class="sxs-lookup"><span data-stu-id="74907-126">The F# compiler picked `int` at this point, but it will adjust the type signature if you call `square` with a different input type, such as a `float`.</span></span>

<span data-ttu-id="74907-127">Otra función, `main`, se define, que está decorada con el atributo `EntryPoint` para indicar F# al compilador que la ejecución del programa debe comenzar allí.</span><span class="sxs-lookup"><span data-stu-id="74907-127">Another function, `main`, is defined, which is decorated with the `EntryPoint` attribute to tell the F# compiler that program execution should start there.</span></span>  <span data-ttu-id="74907-128">Sigue la misma Convención que otros [lenguajes de programación de estilo C](https://en.wikipedia.org/wiki/Entry_point#C_and_C.2B.2B), donde se pueden pasar argumentos de línea de comandos a esta función y se devuelve un código entero (normalmente `0`).</span><span class="sxs-lookup"><span data-stu-id="74907-128">It follows the same convention as other [C-style programming languages](https://en.wikipedia.org/wiki/Entry_point#C_and_C.2B.2B), where command-line arguments can be passed to this function, and an integer code is returned (typically `0`).</span></span>

<span data-ttu-id="74907-129">En esta función se llama a la función `square` con un argumento de `12`.</span><span class="sxs-lookup"><span data-stu-id="74907-129">It is in this function that we call the `square` function with an argument of `12`.</span></span>  <span data-ttu-id="74907-130">A F# continuación, el compilador asigna el tipo de `square` que se va a `int -> int` (es decir, una función que toma un `int` y genera un `int`).</span><span class="sxs-lookup"><span data-stu-id="74907-130">The F# compiler then assigns the type of `square` to be `int -> int` (that is, a function which takes an `int` and produces an `int`).</span></span>  <span data-ttu-id="74907-131">La llamada a `printfn` es una función de impresión con formato que usa una cadena de formato, similar a los lenguajes de programación de estilo C, los parámetros que se corresponden con los especificados en la cadena de formato y, a continuación, imprime el resultado y una nueva línea.</span><span class="sxs-lookup"><span data-stu-id="74907-131">The call to `printfn` is a formatted printing function which uses a format string, similar to C-style programming languages, parameters which correspond to those specified in the format string, and then prints the result and a new line.</span></span>

## <a name="running-your-code"></a><span data-ttu-id="74907-132">Ejecución del código</span><span class="sxs-lookup"><span data-stu-id="74907-132">Running your code</span></span>

<span data-ttu-id="74907-133">Puede ejecutar el código y ver los resultados presionando **Ctrl**+**F5**.</span><span class="sxs-lookup"><span data-stu-id="74907-133">You can run the code and see results by pressing **Ctrl**+**F5**.</span></span>  <span data-ttu-id="74907-134">Esto ejecuta el programa sin depuración y permite ver los resultados.</span><span class="sxs-lookup"><span data-stu-id="74907-134">This runs the program without debugging and allows you to see the results.</span></span>  <span data-ttu-id="74907-135">Como alternativa, puede elegir el elemento de menú **depurar** de nivel superior en Visual Studio y elegir **iniciar sin depurar**.</span><span class="sxs-lookup"><span data-stu-id="74907-135">Alternatively, you can choose the **Debug** top-level menu item in Visual Studio and choose **Start Without Debugging**.</span></span>

<span data-ttu-id="74907-136">Ahora debería ver lo siguiente en la ventana de la consola que Visual Studio ha extraído:</span><span class="sxs-lookup"><span data-stu-id="74907-136">You should now see the following printed to the console window that Visual Studio popped up:</span></span>

```console
12 squared is 144!
```

<span data-ttu-id="74907-137">¡Enhorabuena!</span><span class="sxs-lookup"><span data-stu-id="74907-137">Congratulations!</span></span>  <span data-ttu-id="74907-138">Ha creado su primer F# proyecto en Visual Studio, ha escrito una F# función que ha impreso los resultados de la llamada a esa función y ejecutado el proyecto para ver algunos resultados.</span><span class="sxs-lookup"><span data-stu-id="74907-138">You've created your first F# project in Visual Studio, written an F# function printed the results of calling that function, and run the project to see some results.</span></span>

## <a name="next-steps"></a><span data-ttu-id="74907-139">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="74907-139">Next steps</span></span>

<span data-ttu-id="74907-140">Si no lo ha hecho ya, consulte el [paseo F# ](../tour.md)por, que cubre algunas de las características principales del F# lenguaje.</span><span class="sxs-lookup"><span data-stu-id="74907-140">If you haven't already, check out the [Tour of F#](../tour.md), which covers some of the core features of the F# language.</span></span>  <span data-ttu-id="74907-141">Le proporcionará una visión general de algunas de las funcionalidades de F#y proporcionará ejemplos de código que puede copiar en Visual Studio y ejecutar.</span><span class="sxs-lookup"><span data-stu-id="74907-141">It will give you an overview of some of the capabilities of F#, and provide ample code samples that you can copy into Visual Studio and run.</span></span>  <span data-ttu-id="74907-142">También puede obtener más información sobre la F# documentación en la [ F# Página principal de docs](../index.yml).</span><span class="sxs-lookup"><span data-stu-id="74907-142">You can also learn more about the F# documentation in the [F# docs homepage](../index.yml).</span></span>

## <a name="see-also"></a><span data-ttu-id="74907-143">Vea también</span><span class="sxs-lookup"><span data-stu-id="74907-143">See also</span></span>

- [<span data-ttu-id="74907-144">Paseo por F</span><span class="sxs-lookup"><span data-stu-id="74907-144">Tour of F#</span></span>](../tour.md)
- [<span data-ttu-id="74907-145">F#Referencia del lenguaje</span><span class="sxs-lookup"><span data-stu-id="74907-145">F# language reference</span></span>](../language-reference/index.md)
- [<span data-ttu-id="74907-146">Inferencia de tipos</span><span class="sxs-lookup"><span data-stu-id="74907-146">Type inference</span></span>](../language-reference/type-inference.md)
- [<span data-ttu-id="74907-147">Referencia de símbolos y operadores</span><span class="sxs-lookup"><span data-stu-id="74907-147">Symbol and operator reference</span></span>](../language-reference/symbol-and-operator-reference/index.md)
