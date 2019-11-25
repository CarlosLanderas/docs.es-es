---
title: Generar clases de tipos de datos a partir de XML
ms.date: 03/30/2017
ms.assetid: e4e5e4e8-527f-44d1-92fa-8904a08784ea
ms.openlocfilehash: 977b12b5c61c196a4f033361d37785e4ed0af73a
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/12/2019
ms.locfileid: "73975848"
---
# <a name="generating-data-type-classes-from-xml"></a><span data-ttu-id="a1961-102">Generar clases de tipos de datos a partir de XML</span><span class="sxs-lookup"><span data-stu-id="a1961-102">Generating Data Type Classes from XML</span></span>
<span data-ttu-id="a1961-103">.NET Framework 4,5 incluye una nueva característica para generar clases de tipos de datos a partir de XML.</span><span class="sxs-lookup"><span data-stu-id="a1961-103">.NET Framework 4.5 includes a new feature to generate data type classes from XML.</span></span> <span data-ttu-id="a1961-104">En este tema se describe cómo generar automáticamente tipos de datos para la fuente RSS del blog de .NET.</span><span class="sxs-lookup"><span data-stu-id="a1961-104">This topic describes how to automatically generate data types for the .NET Blog RSS feed.</span></span>  
  
### <a name="obtaining-the-xml-from-the-net-blog-rss-feed"></a><span data-ttu-id="a1961-105">Obtener el XML de la fuente RSS del blog de .NET</span><span class="sxs-lookup"><span data-stu-id="a1961-105">Obtaining the XML from the .NET Blog RSS feed</span></span>  
  
1. <span data-ttu-id="a1961-106">En Internet Explorer, vaya a la [fuente RSS del blog de .net](https://devblogs.microsoft.com/dotnet/feed/).</span><span class="sxs-lookup"><span data-stu-id="a1961-106">In Internet Explorer, navigate to the [.NET Blog RSS feed](https://devblogs.microsoft.com/dotnet/feed/).</span></span>  
  
2. <span data-ttu-id="a1961-107">Haga clic con el botón secundario en la página y seleccione **Ver código fuente**.</span><span class="sxs-lookup"><span data-stu-id="a1961-107">Right-click the page and select **View Source**.</span></span>  
  
3. <span data-ttu-id="a1961-108">Copie el texto de la fuente presionando **Ctrl +** a para seleccionar todo el texto y **Ctrl + C** para copiar.</span><span class="sxs-lookup"><span data-stu-id="a1961-108">Copy the text of the feed by pressing **Ctrl+A** to select all text, and **Ctrl+C** to copy.</span></span>  
  
### <a name="creating-the-data-types"></a><span data-ttu-id="a1961-109">Crear los tipos de datos</span><span class="sxs-lookup"><span data-stu-id="a1961-109">Creating the data types</span></span>  
  
1. <span data-ttu-id="a1961-110">Abra un archivo de código donde se vaya a usar el proxy.</span><span class="sxs-lookup"><span data-stu-id="a1961-110">Open a code file where the proxy is to be used.</span></span> <span data-ttu-id="a1961-111">Este archivo debe formar parte de un proyecto .NET Framework 4,5.</span><span class="sxs-lookup"><span data-stu-id="a1961-111">This file should be part of a .NET Framework 4.5 project.</span></span>  
  
2. <span data-ttu-id="a1961-112">Coloque el cursor en una ubicación en el archivo fuera de las clases existentes.</span><span class="sxs-lookup"><span data-stu-id="a1961-112">Place the cursor in a location in the file outside any existing classes.</span></span>  
  
3. <span data-ttu-id="a1961-113">Seleccione **Editar**, **Pegar especial**y **pegar XML como clases**.</span><span class="sxs-lookup"><span data-stu-id="a1961-113">Select **Edit**, **Paste Special**, **Paste XML as Classes**.</span></span>  
  
4. <span data-ttu-id="a1961-114">Las clases denominadas `link`, `rss`, `rssChannel`, `rssChannelImage`, `rssChannelItem` y `rssChannelItemGuid` se crean con los miembros necesarios para tener acceso a los elementos de la fuente RSS.</span><span class="sxs-lookup"><span data-stu-id="a1961-114">Classes called `link`, `rss`, `rssChannel`, `rssChannelImage`, `rssChannelItem` and `rssChannelItemGuid` are created with the necessary members for accessing the elements in the RSS feed.</span></span>  
  
### <a name="using-the-generated-classes"></a><span data-ttu-id="a1961-115">Usar las clases generadas</span><span class="sxs-lookup"><span data-stu-id="a1961-115">Using the generated classes</span></span>  
  
1. <span data-ttu-id="a1961-116">Una vez que se generan las clases, se pueden usar en código como cualquier otra clase.</span><span class="sxs-lookup"><span data-stu-id="a1961-116">Once the classes are generated, they can be used in code like any other classes.</span></span> <span data-ttu-id="a1961-117">En el siguiente ejemplo de código se devuelve una nueva instancia de la clase `rssChannelImage`.</span><span class="sxs-lookup"><span data-stu-id="a1961-117">The following code example returns a new instance of the `rssChannelImage` class.</span></span>  
  
    ```csharp
    var channelImage = new rssChannelImage()   
    {   
        title = "MyImage",   
        link = "http://www.contoso.com/images/channelImage.jpg",   
        url = "http://www.contoso.com/entries/myEntry.html"   
    };  
    ```
