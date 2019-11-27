---
title: Emitir métodos y ensamblados dinámicos
ms.date: 08/30/2017
helpviewer_keywords:
- reflection emit
- dynamic assemblies
- metadata, emit interfaces
- reflection emit, overview
- assemblies [.NET Framework], emitting dynamic assemblies
ms.openlocfilehash: 578851bed188921324e3c25e533b3466068dee3d
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446785"
---
# <a name="emitting-dynamic-methods-and-assemblies"></a><span data-ttu-id="175e4-102">Emitir métodos y ensamblados dinámicos</span><span class="sxs-lookup"><span data-stu-id="175e4-102">Emitting Dynamic Methods and Assemblies</span></span>

<span data-ttu-id="175e4-103">En esta sección se describe un conjunto de tipos administrados del espacio de nombres <xref:System.Reflection.Emit> que permite a un compilador o una herramienta emitir metadatos y el Lenguaje Intermedio de Microsoft (MSIL) en tiempo de ejecución y, opcionalmente, generar un archivo portable ejecutable (PE) en el disco.</span><span class="sxs-lookup"><span data-stu-id="175e4-103">This section describes a set of managed types in the <xref:System.Reflection.Emit> namespace that allow a compiler or tool to emit metadata and Microsoft intermediate language (MSIL) at run time and optionally generate a portable executable (PE) file on disk.</span></span> <span data-ttu-id="175e4-104">Los motores de scripts y los compiladores son los principales usuarios de este espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="175e4-104">Script engines and compilers are the primary users of this namespace.</span></span> <span data-ttu-id="175e4-105">En esta sección, la funcionalidad proporcionada por el espacio de nombres <xref:System.Reflection.Emit> se conoce como emisión de la reflexión.</span><span class="sxs-lookup"><span data-stu-id="175e4-105">In this section, the functionality provided by the <xref:System.Reflection.Emit> namespace is referred to as reflection emit.</span></span>  
  
<span data-ttu-id="175e4-106">La emisión de la reflexión permite lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="175e4-106">Reflection emit provides the following capabilities:</span></span>  
  
- <span data-ttu-id="175e4-107">Definir métodos globales ligeros en tiempo de ejecución, usando la clase <xref:System.Reflection.Emit.DynamicMethod>, y ejecutarlos usando delegados.</span><span class="sxs-lookup"><span data-stu-id="175e4-107">Define lightweight global methods at run time, using the <xref:System.Reflection.Emit.DynamicMethod> class, and execute them using delegates.</span></span>  
  
- <span data-ttu-id="175e4-108">Definir ensamblados en tiempo de ejecución y, después, ejecutarlos o guardarlos en el disco.</span><span class="sxs-lookup"><span data-stu-id="175e4-108">Define assemblies at run time and then run them and/or save them to disk.</span></span>  
  
- <span data-ttu-id="175e4-109">Definir ensamblados en tiempo de ejecución, ejecutarlos y, después, descargarlos y permitir la recolección de elementos no utilizados para reclamar sus recursos.</span><span class="sxs-lookup"><span data-stu-id="175e4-109">Define assemblies at run time, run them, and then unload them and allow garbage collection to reclaim their resources.</span></span>  
  
- <span data-ttu-id="175e4-110">Definir módulos en nuevos ensamblados en tiempo de ejecución y, después, ejecutarlos o guardarlos en el disco.</span><span class="sxs-lookup"><span data-stu-id="175e4-110">Define modules in new assemblies at run time and then run and/or save them to disk.</span></span>  
  
- <span data-ttu-id="175e4-111">Definir tipos en módulos en tiempo de ejecución, crear instancias de estos tipos y llamar a sus métodos.</span><span class="sxs-lookup"><span data-stu-id="175e4-111">Define types in modules at run time, create instances of these types, and invoke their methods.</span></span>  
  
- <span data-ttu-id="175e4-112">Definir información simbólica para módulos definidos que puedan usar herramientas como depuradores y generadores de perfiles de código.</span><span class="sxs-lookup"><span data-stu-id="175e4-112">Define symbolic information for defined modules that can be used by tools such as debuggers and code profilers.</span></span>  
  
<span data-ttu-id="175e4-113">Además de los tipos administrados del espacio de nombres <xref:System.Reflection.Emit>, hay interfaces de metadatos no administradas que se describen en la documentación de referencia [Interfaces de metadatos](../unmanaged-api/metadata/metadata-interfaces.md).</span><span class="sxs-lookup"><span data-stu-id="175e4-113">In addition to the managed types in the <xref:System.Reflection.Emit> namespace, there are unmanaged metadata interfaces which are described in the [Metadata Interfaces](../unmanaged-api/metadata/metadata-interfaces.md) reference documentation.</span></span> <span data-ttu-id="175e4-114">La emisión de reflexión administrada proporciona una comprobación más estricta de los errores semánticos y un mayor nivel de abstracción de los metadatos que las interfaces de metadatos no administradas.</span><span class="sxs-lookup"><span data-stu-id="175e4-114">Managed reflection emit provides stronger semantic error checking and a higher level of abstraction of the metadata than the unmanaged metadata interfaces.</span></span>  
  
<span data-ttu-id="175e4-115">Otro recurso útil para trabajar con metadatos y MSIL es la documentación de Common Language Infrastructure (CLI), especialmente la sección II sobre la definición y la semántica de los metadatos y la partición III sobre el conjunto de instrucciones de CIL.</span><span class="sxs-lookup"><span data-stu-id="175e4-115">Another useful resource for working with metadata and MSIL is the Common Language Infrastructure (CLI) documentation, especially "Partition II: Metadata Definition and Semantics" and "Partition III: CIL Instruction Set".</span></span> <span data-ttu-id="175e4-116">La documentación está disponible en línea en el [sitio web de ECMA](https://www.ecma-international.org/publications/standards/Ecma-335.htm).</span><span class="sxs-lookup"><span data-stu-id="175e4-116">The documentation is available online at the [Ecma Web site](https://www.ecma-international.org/publications/standards/Ecma-335.htm).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="175e4-117">Esta sección</span><span class="sxs-lookup"><span data-stu-id="175e4-117">In This Section</span></span>
  
[<span data-ttu-id="175e4-118">Problemas de seguridad de la emisión de la reflexión</span><span class="sxs-lookup"><span data-stu-id="175e4-118">Security issues in reflection emit</span></span>](security-issues-in-reflection-emit.md)  
<span data-ttu-id="175e4-119">Describe los problemas de seguridad relacionados con la creación de ensamblados dinámicos mediante emisión de la reflexión.</span><span class="sxs-lookup"><span data-stu-id="175e4-119">Describes security issues related to creating dynamic assemblies using reflection emit.</span></span>  

<span data-ttu-id="175e4-120">[Cómo: Definir y ejecutar métodos dinámicos](how-to-define-and-execute-dynamic-methods.md) </span><span class="sxs-lookup"><span data-stu-id="175e4-120">[How to: Define and execute dynamic methods](how-to-define-and-execute-dynamic-methods.md) </span></span>  
<span data-ttu-id="175e4-121">Muestra cómo ejecutar un método dinámico simple y un método dinámico enlazado a una instancia de una clase.</span><span class="sxs-lookup"><span data-stu-id="175e4-121">Shows how to execute a simple dynamic method and a dynamic method bound to an instance of a class.</span></span>

<span data-ttu-id="175e4-122">[Cómo: Definir un tipo genérico con emisión de reflexión](how-to-define-a-generic-type-with-reflection-emit.md) </span><span class="sxs-lookup"><span data-stu-id="175e4-122">[How to: Define a generic type with reflection emit](how-to-define-a-generic-type-with-reflection-emit.md) </span></span>  
<span data-ttu-id="175e4-123">Muestra cómo crear un tipo genérico simple con dos parámetros de tipo, cómo aplicar restricciones de clase, interfaz y especiales a los parámetros de tipo y cómo crear miembros que usen los parámetros de tipo de la clase como tipos de parámetro y tipos de valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="175e4-123">Shows how to create a simple generic type with two type parameters, how to apply class, interface, and special constraints to the type parameters, and how to create members that use the type parameters of the class as parameter types and return types.</span></span>

<span data-ttu-id="175e4-124">[Cómo: Definir un método genérico con emisión de reflexión](how-to-define-a-generic-method-with-reflection-emit.md) </span><span class="sxs-lookup"><span data-stu-id="175e4-124">[How to: Define a generic method with reflection emit](how-to-define-a-generic-method-with-reflection-emit.md) </span></span>  
<span data-ttu-id="175e4-125">Muestra cómo crear, emitir e invocar un método genérico simple.</span><span class="sxs-lookup"><span data-stu-id="175e4-125">Shows how to create, emit, and invoke a simple generic method.</span></span>

<span data-ttu-id="175e4-126">[Ensamblados recopilables para la generación dinámica de tipos](collectible-assemblies.md) </span><span class="sxs-lookup"><span data-stu-id="175e4-126">[Collectible assemblies for dynamic type generation](collectible-assemblies.md) </span></span>  
<span data-ttu-id="175e4-127">Presenta los ensamblados recopilables, que son ensamblados dinámicos que se pueden descargar sin descargar el dominio de aplicación en el que se crearon.</span><span class="sxs-lookup"><span data-stu-id="175e4-127">Introduces collectible assemblies, which are dynamic assemblies that can be unloaded without unloading the application domain in which they were created.</span></span>
  
## <a name="reference"></a><span data-ttu-id="175e4-128">Referencia</span><span class="sxs-lookup"><span data-stu-id="175e4-128">Reference</span></span>  

<xref:System.Reflection.Emit.OpCodes>  
<span data-ttu-id="175e4-129">Cataloga los códigos de instrucción de MSIL que puede usar para compilar cuerpos de método.</span><span class="sxs-lookup"><span data-stu-id="175e4-129">Catalogs the MSIL instruction codes you can use to build method bodies.</span></span>  
  
<xref:System.Reflection.Emit>  
<span data-ttu-id="175e4-130">Contiene clases administradas usadas para emitir ensamblados, tipos y métodos dinámicos.</span><span class="sxs-lookup"><span data-stu-id="175e4-130">Contains managed classes used to emit dynamic methods, assemblies, and types.</span></span>  
  
<xref:System.Type>  
<span data-ttu-id="175e4-131">Describe la clase <xref:System.Type>, que representa los tipos en reflexión administrada y emisión de la reflexión, y que es clave para el uso de estas tecnologías.</span><span class="sxs-lookup"><span data-stu-id="175e4-131">Describes the <xref:System.Type> class, which represents types in managed reflection and reflection emit, and which is key to the use of these technologies.</span></span>  
  
<xref:System.Reflection>  
<span data-ttu-id="175e4-132">Contiene clases administradas usadas para explorar metadatos y código administrado.</span><span class="sxs-lookup"><span data-stu-id="175e4-132">Contains managed classes used to explore metadata and managed code.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="175e4-133">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="175e4-133">Related Sections</span></span>  

[<span data-ttu-id="175e4-134">Reflexión</span><span class="sxs-lookup"><span data-stu-id="175e4-134">Reflection</span></span>](reflection.md)  
<span data-ttu-id="175e4-135">Explica cómo explorar metadatos y código administrado.</span><span class="sxs-lookup"><span data-stu-id="175e4-135">Explains how to explore metadata and managed code.</span></span>  
  
[<span data-ttu-id="175e4-136">Ensamblados de .NET</span><span class="sxs-lookup"><span data-stu-id="175e4-136">Assemblies in .NET</span></span>](../../standard/assembly/index.md)  
<span data-ttu-id="175e4-137">Proporciona información general sobre los ensamblados de las implementaciones de. NET.</span><span class="sxs-lookup"><span data-stu-id="175e4-137">Provides an overview of assemblies in .NET implementations.</span></span>
