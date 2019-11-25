---
title: WCF Data Services 4.5
ms.date: 03/30/2017
helpviewer_keywords:
- Astoria
- WCF Data Services, getting started
ms.assetid: 73d2bec3-7c92-4110-b905-11bb0462357a
ms.openlocfilehash: 1ce152b84f17a35982a75f54b5418623ba39210f
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/12/2019
ms.locfileid: "73975230"
---
# <a name="wcf-data-services-45"></a><span data-ttu-id="bf574-102">WCF Data Services 4.5</span><span class="sxs-lookup"><span data-stu-id="bf574-102">WCF Data Services 4.5</span></span>

<span data-ttu-id="bf574-103">WCF Data Services (anteriormente conocido como "ADO.NET Data Services") es un componente de la .NET Framework que le permite crear servicios que usan Open Data Protocol (OData) para exponer y consumir datos en Internet o en una intranet mediante la semántica de [transferencia de estado representacional (REST)](https://go.microsoft.com/fwlink/?LinkId=113919).</span><span class="sxs-lookup"><span data-stu-id="bf574-103">WCF Data Services (formerly known as "ADO.NET Data Services") is a component of the .NET Framework that enables you to create services that use the Open Data Protocol (OData) to expose and consume data over the Web or intranet by using the semantics of [representational state transfer (REST)](https://go.microsoft.com/fwlink/?LinkId=113919).</span></span> <span data-ttu-id="bf574-104">OData expone los datos como recursos direccionables a través de identificadores uniformes de recursos (URI).</span><span class="sxs-lookup"><span data-stu-id="bf574-104">OData exposes data as resources that are addressable by URIs.</span></span> <span data-ttu-id="bf574-105">Para tener acceso a los datos y cambiarlos se utilizan los verbos HTTP estándar GET, PUT, POST y DELETE.</span><span class="sxs-lookup"><span data-stu-id="bf574-105">Data is accessed and changed by using standard HTTP verbs of GET, PUT, POST, and DELETE.</span></span> <span data-ttu-id="bf574-106">OData usa las convenciones de entidad-relación del [Entity Data Model](../adonet/entity-data-model.md) para exponer los recursos como conjuntos de entidades que se relacionan mediante asociaciones.</span><span class="sxs-lookup"><span data-stu-id="bf574-106">OData uses the entity-relationship conventions of the [Entity Data Model](../adonet/entity-data-model.md) to expose resources as sets of entities that are related by associations.</span></span>

<span data-ttu-id="bf574-107">WCF Data Services usa el protocolo OData para direccionar y actualizar los recursos.</span><span class="sxs-lookup"><span data-stu-id="bf574-107">WCF Data Services uses the OData protocol for addressing and updating resources.</span></span> <span data-ttu-id="bf574-108">De esta manera, puede tener acceso a estos servicios desde cualquier cliente que admita OData.</span><span class="sxs-lookup"><span data-stu-id="bf574-108">In this way, you can access these services from any client that supports OData.</span></span> <span data-ttu-id="bf574-109">OData le permite solicitar y escribir datos en los recursos mediante formatos de transferencia conocidos: Atom, un conjunto de estándares para intercambiar y actualizar datos como XML, y notación de objetos JavaScript (JSON), un formato de intercambio de datos basado en texto que se usa mucho en AJAX programas.</span><span class="sxs-lookup"><span data-stu-id="bf574-109">OData enables you to request and write data to resources by using well-known transfer formats: Atom, a set of standards for exchanging and updating data as XML, and JavaScript Object Notation (JSON), a text-based data exchange format used extensively in AJAX applications.</span></span>

<span data-ttu-id="bf574-110">WCF Data Services pueden exponer datos procedentes de varios orígenes como fuentes de OData.</span><span class="sxs-lookup"><span data-stu-id="bf574-110">WCF Data Services can expose data that originates from various sources as OData feeds.</span></span> <span data-ttu-id="bf574-111">Las herramientas de Visual Studio facilitan la creación de un servicio basado en OData mediante un modelo de datos de ADO.NET Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="bf574-111">Visual Studio tools make it easier for you to create an OData-based service by using an ADO.NET Entity Framework data model.</span></span> <span data-ttu-id="bf574-112">También puede crear fuentes de OData basadas en clases de Common Language Runtime (CLR) e incluso datos enlazados en tiempo de ejecución o sin tipo.</span><span class="sxs-lookup"><span data-stu-id="bf574-112">You can also create OData feeds based on common language runtime (CLR) classes and even late-bound or un-typed data.</span></span>

<span data-ttu-id="bf574-113">WCF Data Services también incluye un conjunto de bibliotecas de cliente, uno para las aplicaciones cliente de .NET Framework general y otro específicamente para las aplicaciones basadas en Silverlight.</span><span class="sxs-lookup"><span data-stu-id="bf574-113">WCF Data Services also includes a set of client libraries, one for general .NET Framework client applications and another specifically for Silverlight-based applications.</span></span> <span data-ttu-id="bf574-114">Estas bibliotecas de cliente proporcionan un modelo de programación basado en objetos cuando se tiene acceso a una fuente de OData desde entornos como el .NET Framework y Silverlight.</span><span class="sxs-lookup"><span data-stu-id="bf574-114">These client libraries provide an object-based programming model when you access an OData feed from environments such as the .NET Framework and Silverlight.</span></span>

## <a name="where-should-i-start"></a><span data-ttu-id="bf574-115">¿Por dónde empiezo?</span><span class="sxs-lookup"><span data-stu-id="bf574-115">Where Should I Start?</span></span>

<span data-ttu-id="bf574-116">En función de sus intereses, considere la posibilidad de empezar a trabajar con WCF Data Services en uno de los siguientes temas.</span><span class="sxs-lookup"><span data-stu-id="bf574-116">Depending on your interests, consider getting started with WCF Data Services in one of the following topics.</span></span>

<span data-ttu-id="bf574-117">Quiero comenzar de inmediato…</span><span class="sxs-lookup"><span data-stu-id="bf574-117">I want to jump right in...</span></span>

- [<span data-ttu-id="bf574-118">Inicio rápido</span><span class="sxs-lookup"><span data-stu-id="bf574-118">Quickstart</span></span>](quickstart-wcf-data-services.md)

- [<span data-ttu-id="bf574-119">Introducción</span><span class="sxs-lookup"><span data-stu-id="bf574-119">Getting Started</span></span>](getting-started-with-wcf-data-services.md)

- [<span data-ttu-id="bf574-120">Inicio rápido de Silverlight</span><span class="sxs-lookup"><span data-stu-id="bf574-120">Silverlight Quickstart</span></span>](https://go.microsoft.com/fwlink/?LinkID=192782)

- [<span data-ttu-id="bf574-121">Inicio rápido de Silverlight para desarrollo de Windows Phone</span><span class="sxs-lookup"><span data-stu-id="bf574-121">Silverlight Quickstart for Windows Phone Development</span></span>](https://go.microsoft.com/fwlink/?LinkID=214535)

<span data-ttu-id="bf574-122">Simplemente mostrarme parte del código...</span><span class="sxs-lookup"><span data-stu-id="bf574-122">Just show me some code...</span></span>

- [<span data-ttu-id="bf574-123">Inicio rápido</span><span class="sxs-lookup"><span data-stu-id="bf574-123">Quickstart</span></span>](quickstart-wcf-data-services.md)

- [<span data-ttu-id="bf574-124">Cómo: ejecutar consultas de servicios de datos</span><span class="sxs-lookup"><span data-stu-id="bf574-124">How to: Execute Data Service Queries</span></span>](how-to-execute-data-service-queries-wcf-data-services.md)

- [<span data-ttu-id="bf574-125">Cómo: enlazar datos a elementos de Windows Presentation Foundation</span><span class="sxs-lookup"><span data-stu-id="bf574-125">How to: Bind Data to Windows Presentation Foundation Elements</span></span>](bind-data-to-wpf-elements-wcf-data-services.md)

<span data-ttu-id="bf574-126">Deseo obtener más información acerca de OData...</span><span class="sxs-lookup"><span data-stu-id="bf574-126">I want to know more about OData...</span></span>

- [<span data-ttu-id="bf574-127">Notas del producto: introducción a OData</span><span class="sxs-lookup"><span data-stu-id="bf574-127">Whitepaper: Introducing OData</span></span>](https://go.microsoft.com/fwlink/?LinkId=220867)

- [<span data-ttu-id="bf574-128">Sitio web de Open Data Protocol</span><span class="sxs-lookup"><span data-stu-id="bf574-128">Open Data Protocol Web site</span></span>](https://go.microsoft.com/fwlink/?LinkID=184554)

- [<span data-ttu-id="bf574-129">OData: SDK</span><span class="sxs-lookup"><span data-stu-id="bf574-129">OData: SDK</span></span>](https://go.microsoft.com/fwlink/?LinkID=185248)

- [<span data-ttu-id="bf574-130">OData: preguntas más frecuentes</span><span class="sxs-lookup"><span data-stu-id="bf574-130">OData: Frequently Asked Questions</span></span>](https://go.microsoft.com/fwlink/?LinkId=185867)

<span data-ttu-id="bf574-131">Quiero ver algunos vídeos...</span><span class="sxs-lookup"><span data-stu-id="bf574-131">I want to watch some videos...</span></span>

- [<span data-ttu-id="bf574-132">Guía para principiantes de Servicios de datos de WCF</span><span class="sxs-lookup"><span data-stu-id="bf574-132">Beginner's Guide to WCF Data Services</span></span>](https://go.microsoft.com/fwlink/?LinkId=220864)

- [<span data-ttu-id="bf574-133">Vídeos para desarrolladores de Servicios de datos de WCF</span><span class="sxs-lookup"><span data-stu-id="bf574-133">WCF Data Services Developer Videos</span></span>](https://go.microsoft.com/fwlink/?LinkId=220861)

- [<span data-ttu-id="bf574-134">OData: sitio web para desarrolladores</span><span class="sxs-lookup"><span data-stu-id="bf574-134">OData: Developers Web site</span></span>](https://go.microsoft.com/fwlink/?LinkId=185866)

<span data-ttu-id="bf574-135">Deseo ver ejemplos de un extremo a otro...</span><span class="sxs-lookup"><span data-stu-id="bf574-135">I want to see end-to-end samples...</span></span>

- [<span data-ttu-id="bf574-136">Ejemplos de documentación de Servicios de datos de WCF en la galería de ejemplos de MSDN</span><span class="sxs-lookup"><span data-stu-id="bf574-136">WCF Data Services Documentation Samples on MSDN Samples Gallery</span></span>](https://go.microsoft.com/fwlink/?LinkID=220865)

- [<span data-ttu-id="bf574-137">Otros ejemplos de Servicios de datos de WCF en la galería de ejemplos de MSDN</span><span class="sxs-lookup"><span data-stu-id="bf574-137">Other WCF Data Services Samples on MSDN Samples Gallery</span></span>](https://go.microsoft.com/fwlink/?LinkId=220866)

- [<span data-ttu-id="bf574-138">OData: SDK</span><span class="sxs-lookup"><span data-stu-id="bf574-138">OData: SDK</span></span>](https://go.microsoft.com/fwlink/?LinkID=185248)

<span data-ttu-id="bf574-139">¿Cómo se integra con Visual Studio?</span><span class="sxs-lookup"><span data-stu-id="bf574-139">How does it integrate with Visual Studio?</span></span>

- [<span data-ttu-id="bf574-140">Generar la biblioteca cliente del servicio de datos</span><span class="sxs-lookup"><span data-stu-id="bf574-140">Generating the Data Service Client Library</span></span>](generating-the-data-service-client-library-wcf-data-services.md)

- [<span data-ttu-id="bf574-141">Creación del servicio de datos</span><span class="sxs-lookup"><span data-stu-id="bf574-141">Creating the Data Service</span></span>](creating-the-data-service.md)

- [<span data-ttu-id="bf574-142">Proveedor de Entity Framework</span><span class="sxs-lookup"><span data-stu-id="bf574-142">Entity Framework Provider</span></span>](entity-framework-provider-wcf-data-services.md)

<span data-ttu-id="bf574-143">¿Qué me permite hacer?</span><span class="sxs-lookup"><span data-stu-id="bf574-143">What can I do with it?</span></span>

- [<span data-ttu-id="bf574-144">Información general</span><span class="sxs-lookup"><span data-stu-id="bf574-144">Overview</span></span>](wcf-data-services-overview.md)

- [<span data-ttu-id="bf574-145">Notas del producto: introducción a OData</span><span class="sxs-lookup"><span data-stu-id="bf574-145">Whitepaper: Introducing OData</span></span>](https://go.microsoft.com/fwlink/?LinkId=220867)

- [<span data-ttu-id="bf574-146">Escenarios de aplicación</span><span class="sxs-lookup"><span data-stu-id="bf574-146">Application Scenarios</span></span>](application-scenarios-wcf-data-services.md)

<span data-ttu-id="bf574-147">Deseo usar Silverlight...</span><span class="sxs-lookup"><span data-stu-id="bf574-147">I want to use Silverlight...</span></span>

- [<span data-ttu-id="bf574-148">Inicio rápido de Silverlight</span><span class="sxs-lookup"><span data-stu-id="bf574-148">Silverlight Quickstart</span></span>](https://go.microsoft.com/fwlink/?LinkID=192782)

- [<span data-ttu-id="bf574-149">Servicios de datos de WCF (Silverlight)</span><span class="sxs-lookup"><span data-stu-id="bf574-149">WCF Data Services (Silverlight)</span></span>](https://go.microsoft.com/fwlink/?LinkID=143149)

- [<span data-ttu-id="bf574-150">Introducción a Silverlight</span><span class="sxs-lookup"><span data-stu-id="bf574-150">Getting Started with Silverlight</span></span>](https://go.microsoft.com/fwlink/?LinkId=148366)

<span data-ttu-id="bf574-151">Deseo usar LINQ...</span><span class="sxs-lookup"><span data-stu-id="bf574-151">I want to use LINQ...</span></span>

- [<span data-ttu-id="bf574-152">Consultar el servicio de datos</span><span class="sxs-lookup"><span data-stu-id="bf574-152">Querying the Data Service</span></span>](querying-the-data-service-wcf-data-services.md)

- [<span data-ttu-id="bf574-153">Consideraciones sobre LINQ</span><span class="sxs-lookup"><span data-stu-id="bf574-153">LINQ Considerations</span></span>](linq-considerations-wcf-data-services.md)

- [<span data-ttu-id="bf574-154">Cómo: ejecutar consultas de servicios de datos</span><span class="sxs-lookup"><span data-stu-id="bf574-154">How to: Execute Data Service Queries</span></span>](how-to-execute-data-service-queries-wcf-data-services.md)

<span data-ttu-id="bf574-155">Todavía necesito más información...</span><span class="sxs-lookup"><span data-stu-id="bf574-155">I still need some more information...</span></span>

- [<span data-ttu-id="bf574-156">Blog del equipo de Servicios de datos de WCF</span><span class="sxs-lookup"><span data-stu-id="bf574-156">WCF Data Services Team Blog</span></span>](https://go.microsoft.com/fwlink/?LinkID=150511)

- [<span data-ttu-id="bf574-157">Recursos</span><span class="sxs-lookup"><span data-stu-id="bf574-157">Resources</span></span>](wcf-data-services-resources.md)

- [<span data-ttu-id="bf574-158">Centro para desarrolladores de Servicios de datos de WCF</span><span class="sxs-lookup"><span data-stu-id="bf574-158">WCF Data Services Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=220868)

- [<span data-ttu-id="bf574-159">Sitio web de Open Data Protocol</span><span class="sxs-lookup"><span data-stu-id="bf574-159">Open Data Protocol Web site</span></span>](https://go.microsoft.com/fwlink/?LinkID=184554)

## <a name="in-this-section"></a><span data-ttu-id="bf574-160">En esta sección</span><span class="sxs-lookup"><span data-stu-id="bf574-160">In This Section</span></span>

[<span data-ttu-id="bf574-161">Información general</span><span class="sxs-lookup"><span data-stu-id="bf574-161">Overview</span></span>](wcf-data-services-overview.md)

<span data-ttu-id="bf574-162">Proporciona información general sobre las características y la funcionalidad disponibles en WCF Data Services.</span><span class="sxs-lookup"><span data-stu-id="bf574-162">Provides an overview of the features and functionality available in WCF Data Services.</span></span>

<span data-ttu-id="bf574-163">[Novedades de WCF Data Services 5,0](https://docs.microsoft.com/previous-versions/dotnet/wcf-data-services/ee373845(v=vs.103))</span><span class="sxs-lookup"><span data-stu-id="bf574-163">[What's New in WCF Data Services 5.0](https://docs.microsoft.com/previous-versions/dotnet/wcf-data-services/ee373845(v=vs.103))</span></span>

<span data-ttu-id="bf574-164">Describe la nueva funcionalidad de WCF Data Services y la compatibilidad con las nuevas características de OData.</span><span class="sxs-lookup"><span data-stu-id="bf574-164">Describes new functionality in WCF Data Services and support for new OData features.</span></span>

[<span data-ttu-id="bf574-165">Introducción</span><span class="sxs-lookup"><span data-stu-id="bf574-165">Getting Started</span></span>](getting-started-with-wcf-data-services.md)

<span data-ttu-id="bf574-166">Describe cómo exponer y consumir fuentes de OData mediante WCF Data Services.</span><span class="sxs-lookup"><span data-stu-id="bf574-166">Describes how to expose and consume OData feeds by using WCF Data Services.</span></span>

[<span data-ttu-id="bf574-167">Definir Servicios de datos de WCF</span><span class="sxs-lookup"><span data-stu-id="bf574-167">Defining WCF Data Services</span></span>](defining-wcf-data-services.md)

<span data-ttu-id="bf574-168">Describe cómo crear y configurar un servicio de datos que exponga fuentes de OData.</span><span class="sxs-lookup"><span data-stu-id="bf574-168">Describes how to create and configure a data service that exposes OData feeds.</span></span>

[<span data-ttu-id="bf574-169">Biblioteca cliente de Servicios de datos de WCF</span><span class="sxs-lookup"><span data-stu-id="bf574-169">WCF Data Services Client Library</span></span>](wcf-data-services-client-library.md)

<span data-ttu-id="bf574-170">Describe cómo usar las bibliotecas de cliente para consumir fuentes de OData desde una aplicación cliente de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="bf574-170">Describes how to use client libraries to consume OData feeds from a .NET Framework client application.</span></span>

## <a name="see-also"></a><span data-ttu-id="bf574-171">Vea también</span><span class="sxs-lookup"><span data-stu-id="bf574-171">See also</span></span>

- [<span data-ttu-id="bf574-172">Transferencia de estado representacional (REST)</span><span class="sxs-lookup"><span data-stu-id="bf574-172">Representational State Transfer (REST)</span></span>](https://go.microsoft.com/fwlink/?LinkId=113919)
