---
title: Interfaces de metadatos
ms.date: 03/30/2017
helpviewer_keywords:
- unmanaged interfaces [.NET Framework], metadata
- metadata interfaces [.NET Framework]
- interfaces (.NET Framework metadata]
ms.assetid: f5cdac93-a28c-48ef-8a19-5773376e9e7c
ms.openlocfilehash: 4672cb813cec4a127f7888a2273eb26c3f34c3d9
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74431587"
---
# <a name="metadata-interfaces"></a><span data-ttu-id="46e0d-102">Interfaces de metadatos</span><span class="sxs-lookup"><span data-stu-id="46e0d-102">Metadata Interfaces</span></span>
<span data-ttu-id="46e0d-103">En esta sección se describen las interfaces no administradas que proporcionan acceso a los metadatos expuestos por los tipos, métodos o campos .NET Framework, entre otros.</span><span class="sxs-lookup"><span data-stu-id="46e0d-103">This section describes the unmanaged interfaces that provide access to the metadata exposed by the .NET Framework types, methods, fields, and so on.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="46e0d-104">Esta sección</span><span class="sxs-lookup"><span data-stu-id="46e0d-104">In This Section</span></span>  
 [<span data-ttu-id="46e0d-105">ICeeGen (interfaz)</span><span class="sxs-lookup"><span data-stu-id="46e0d-105">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)  
 <span data-ttu-id="46e0d-106">Proporciona métodos para la compilación de código dinámico.</span><span class="sxs-lookup"><span data-stu-id="46e0d-106">Provides methods for dynamic code compilation.</span></span>  
  
 [<span data-ttu-id="46e0d-107">IHostFilter (interfaz)</span><span class="sxs-lookup"><span data-stu-id="46e0d-107">IHostFilter Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/ihostfilter-interface.md)  
 <span data-ttu-id="46e0d-108">Proporciona un método para que el host en tiempo de ejecución marque los tokens de metadatos para su procesamiento.</span><span class="sxs-lookup"><span data-stu-id="46e0d-108">Provides a method for the run-time host to mark metadata tokens for processing.</span></span>  
  
 [<span data-ttu-id="46e0d-109">IMapToken (interfaz)</span><span class="sxs-lookup"><span data-stu-id="46e0d-109">IMapToken Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imaptoken-interface.md)  
 <span data-ttu-id="46e0d-110">Proporciona funciones de asignación entre las firmas de metadatos importadas y emitidas.</span><span class="sxs-lookup"><span data-stu-id="46e0d-110">Provides mapping capabilities between imported and emitted metadata signatures.</span></span>  
  
 [<span data-ttu-id="46e0d-111">IMetaDataAssemblyEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="46e0d-111">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)  
 <span data-ttu-id="46e0d-112">Proporciona métodos que admiten el modelo autodescriptivo usado por Common Language Runtime (CLR) para resolver y consumir recursos.</span><span class="sxs-lookup"><span data-stu-id="46e0d-112">Provides methods that support the self-description model used by the common language runtime (CLR) to resolve and consume resources.</span></span>  
  
 [<span data-ttu-id="46e0d-113">IMetaDataAssemblyImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="46e0d-113">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)  
 <span data-ttu-id="46e0d-114">Proporciona métodos para acceder al contenido de un manifiesto del ensamblado y examinarlo.</span><span class="sxs-lookup"><span data-stu-id="46e0d-114">Provides methods to access and examine the contents of an assembly manifest.</span></span>  
  
 [<span data-ttu-id="46e0d-115">IMetaDataConverter (interfaz)</span><span class="sxs-lookup"><span data-stu-id="46e0d-115">IMetaDataConverter Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataconverter-interface.md)  
 <span data-ttu-id="46e0d-116">Proporciona métodos para asignar las bibliotecas de tipos a sus firmas de metadatos y para convertirlas de uno a otro.</span><span class="sxs-lookup"><span data-stu-id="46e0d-116">Provides methods to map type libraries to their metadata signatures, and to convert from one to the other.</span></span>  
  
 [<span data-ttu-id="46e0d-117">IMetaDataDispenser (interfaz)</span><span class="sxs-lookup"><span data-stu-id="46e0d-117">IMetaDataDispenser Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)  
 <span data-ttu-id="46e0d-118">`IMetaDataDispenser` está obsoleto.</span><span class="sxs-lookup"><span data-stu-id="46e0d-118">`IMetaDataDispenser` is obsolete.</span></span> <span data-ttu-id="46e0d-119">Utilice `IMetaDataDispenserEx` en su lugar.</span><span class="sxs-lookup"><span data-stu-id="46e0d-119">Use `IMetaDataDispenserEx` instead.</span></span>  
  
 [<span data-ttu-id="46e0d-120">IMetaDataDispenserEx (interfaz)</span><span class="sxs-lookup"><span data-stu-id="46e0d-120">IMetaDataDispenserEx Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)  
 <span data-ttu-id="46e0d-121">Proporciona métodos que asignan áreas de memoria para crear o modificar los metadatos.</span><span class="sxs-lookup"><span data-stu-id="46e0d-121">Provides methods that map areas of memory for creating or modifying metadata.</span></span>  
  
 [<span data-ttu-id="46e0d-122">IMetaDataEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="46e0d-122">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 <span data-ttu-id="46e0d-123">Proporciona métodos para crear, modificar y almacenar metadatos acerca del ensamblado del ámbito definido actualmente.</span><span class="sxs-lookup"><span data-stu-id="46e0d-123">Provides methods to create, modify and store metadata about the assembly in the currently defined scope.</span></span>  
  
 [<span data-ttu-id="46e0d-124">IMetaDataEmit2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="46e0d-124">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)  
 <span data-ttu-id="46e0d-125">Proporciona métodos para definir y modificar las firmas de metadatos de los métodos y constructores con parámetros del tipo <xref:System.Type?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="46e0d-125">Provides methods for defining and modifying the metadata signatures of methods and constructors with parameters of type <xref:System.Type?displayProperty=nameWithType>.</span></span>  
  
 [<span data-ttu-id="46e0d-126">IMetaDataError (interfaz)</span><span class="sxs-lookup"><span data-stu-id="46e0d-126">IMetaDataError Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataerror-interface.md)  
 <span data-ttu-id="46e0d-127">Proporciona un mecanismo de devolución de llamada para notificar errores durante la resolución de la firma de metadatos de un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="46e0d-127">Provides a callback mechanism for reporting errors during the resolution of the metadata signature for an assembly.</span></span>  
  
 [<span data-ttu-id="46e0d-128">IMetaDataFilter (interfaz)</span><span class="sxs-lookup"><span data-stu-id="46e0d-128">IMetaDataFilter Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatafilter-interface.md)  
 <span data-ttu-id="46e0d-129">Proporciona métodos para marcar y filtrar los tokens de metadatos para evitar repetir acciones que ya se han realizado.</span><span class="sxs-lookup"><span data-stu-id="46e0d-129">Provides methods for marking and filtering metadata tokens to avoid repeating actions that have already been taken.</span></span>  
  
 [<span data-ttu-id="46e0d-130">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="46e0d-130">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 <span data-ttu-id="46e0d-131">Proporciona métodos para importar y manipular tipos de otros ensamblados.</span><span class="sxs-lookup"><span data-stu-id="46e0d-131">Provides methods for importing and manipulating types from other assemblies.</span></span>  
  
 [<span data-ttu-id="46e0d-132">IMetaDataImport2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="46e0d-132">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)  
 <span data-ttu-id="46e0d-133">Extiende `IMetaDataImport` para proporcionar la capacidad de trabajar con tipos genéricos.</span><span class="sxs-lookup"><span data-stu-id="46e0d-133">Extends `IMetaDataImport` to provide the capability of working with generic types.</span></span>  
  
 [<span data-ttu-id="46e0d-134">IMetaDataInfo (interfaz)</span><span class="sxs-lookup"><span data-stu-id="46e0d-134">IMetaDataInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatainfo-interface.md)  
 <span data-ttu-id="46e0d-135">Proporciona un método que obtiene información sobre la asignación de metadatos desde un archivo en disco a la memoria.</span><span class="sxs-lookup"><span data-stu-id="46e0d-135">Provides a method that gets information about the mapping of metadata from an on-disk file into memory.</span></span>  
  
 [<span data-ttu-id="46e0d-136">IMetaDataTables (interfaz)</span><span class="sxs-lookup"><span data-stu-id="46e0d-136">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)  
 <span data-ttu-id="46e0d-137">Proporciona métodos para el almacenamiento y la recuperación de información de metadatos en tablas.</span><span class="sxs-lookup"><span data-stu-id="46e0d-137">Provides methods for the storage and retrieval of metadata information in tables.</span></span>  
  
 [<span data-ttu-id="46e0d-138">IMetaDataTables2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="46e0d-138">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)  
 <span data-ttu-id="46e0d-139">Extiende `IMetaDataTables` para incluir métodos para trabajar con secuencias de metadatos.</span><span class="sxs-lookup"><span data-stu-id="46e0d-139">Extends `IMetaDataTables` to include methods for working with metadata streams.</span></span>  
  
 [<span data-ttu-id="46e0d-140">IMetaDataValidate (interfaz)</span><span class="sxs-lookup"><span data-stu-id="46e0d-140">IMetaDataValidate Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatavalidate-interface.md)  
 <span data-ttu-id="46e0d-141">Proporciona métodos para la validación de firmas de metadatos.</span><span class="sxs-lookup"><span data-stu-id="46e0d-141">Provides methods to use for validation of metadata signatures.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="46e0d-142">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="46e0d-142">Related Sections</span></span>  
 [<span data-ttu-id="46e0d-143">Funciones estáticas globales para metadatos</span><span class="sxs-lookup"><span data-stu-id="46e0d-143">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)  
  
 [<span data-ttu-id="46e0d-144">Enumeraciones para metadatos</span><span class="sxs-lookup"><span data-stu-id="46e0d-144">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)  
  
 [<span data-ttu-id="46e0d-145">Estructuras de metadatos</span><span class="sxs-lookup"><span data-stu-id="46e0d-145">Metadata Structures</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-structures.md)  
  
 [<span data-ttu-id="46e0d-146">Uniones de metadatos</span><span class="sxs-lookup"><span data-stu-id="46e0d-146">Metadata Unions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-unions.md)
