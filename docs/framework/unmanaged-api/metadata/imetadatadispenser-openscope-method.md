---
title: IMetaDataDispenser::OpenScope (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataDispenser.OpenScope
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataDispenser::OpenScope
helpviewer_keywords:
- IMetaDataDispenser::OpenScope method [.NET Framework metadata]
- OpenScope method, IMetaDataDispenser interface [.NET Framework metadata]
ms.assetid: 65063ad5-e0d9-4c01-8f8b-9a5950109fa6
topic_type:
- apiref
ms.openlocfilehash: 5ce1af82631531f8f7105fbf92ba78db3cca437b
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74442328"
---
# <a name="imetadatadispenseropenscope-method"></a><span data-ttu-id="fe5df-102">IMetaDataDispenser::OpenScope (Método)</span><span class="sxs-lookup"><span data-stu-id="fe5df-102">IMetaDataDispenser::OpenScope Method</span></span>
<span data-ttu-id="fe5df-103">Abre un archivo en disco existente y asigna sus metadatos a la memoria.</span><span class="sxs-lookup"><span data-stu-id="fe5df-103">Opens an existing, on-disk file and maps its metadata into memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fe5df-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fe5df-104">Syntax</span></span>  
  
```cpp  
HRESULT OpenScope (  
    [in]  LPCWSTR     szScope,   
    [in]  DWORD       dwOpenFlags,   
    [in]  REFIID      riid,   
    [out] IUnknown    **ppIUnk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fe5df-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="fe5df-105">Parameters</span></span>  
 `szScope`  
 <span data-ttu-id="fe5df-106">de Nombre del archivo que se va a abrir.</span><span class="sxs-lookup"><span data-stu-id="fe5df-106">[in] The name of the file to be opened.</span></span> <span data-ttu-id="fe5df-107">El archivo debe contener metadatos de Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="fe5df-107">The file must contain common language runtime (CLR) metadata.</span></span>  
  
 `dwOpenFlags`  
 <span data-ttu-id="fe5df-108">de Un valor de la enumeración [CorOpenFlags (](../../../../docs/framework/unmanaged-api/metadata/coropenflags-enumeration.md) para especificar el modo (lectura, escritura, etc.) para abrirlo.</span><span class="sxs-lookup"><span data-stu-id="fe5df-108">[in] A value of the [CorOpenFlags](../../../../docs/framework/unmanaged-api/metadata/coropenflags-enumeration.md) enumeration to specify the mode (read, write, and so on) for opening.</span></span>  
  
 `riid`  
 <span data-ttu-id="fe5df-109">de IID de la interfaz de metadatos deseada que se va a devolver; el autor de la llamada usará la interfaz para importar (leer) o emitir (escribir) metadatos.</span><span class="sxs-lookup"><span data-stu-id="fe5df-109">[in] The IID of the desired metadata interface to be returned; the caller will use the interface to import (read) or emit (write) metadata.</span></span>  
  
 <span data-ttu-id="fe5df-110">El valor de `riid` debe especificar una de las interfaces "Import" o "Emit".</span><span class="sxs-lookup"><span data-stu-id="fe5df-110">The value of `riid` must specify one of the "import" or "emit" interfaces.</span></span> <span data-ttu-id="fe5df-111">Los valores válidos son IID_IMetaDataEmit, IID_IMetaDataImport, IID_IMetaDataAssemblyEmit, IID_IMetaDataAssemblyImport, IID_IMetaDataEmit2 o IID_IMetaDataImport2.</span><span class="sxs-lookup"><span data-stu-id="fe5df-111">Valid values are IID_IMetaDataEmit, IID_IMetaDataImport, IID_IMetaDataAssemblyEmit, IID_IMetaDataAssemblyImport, IID_IMetaDataEmit2, or IID_IMetaDataImport2.</span></span>  
  
 `ppIUnk`  
 <span data-ttu-id="fe5df-112">enuncia Puntero a la interfaz devuelta.</span><span class="sxs-lookup"><span data-stu-id="fe5df-112">[out] The pointer to the returned interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fe5df-113">Comentarios</span><span class="sxs-lookup"><span data-stu-id="fe5df-113">Remarks</span></span>  
 <span data-ttu-id="fe5df-114">La copia en memoria de los metadatos se puede consultar utilizando métodos de una de las interfaces de "importación" o se pueden agregar al uso de métodos de una de las interfaces de "emisión".</span><span class="sxs-lookup"><span data-stu-id="fe5df-114">The in-memory copy of the metadata can be queried using methods from one of the "import" interfaces, or added to using methods from the one of the "emit" interfaces.</span></span>  
  
 <span data-ttu-id="fe5df-115">Si el archivo de destino no contiene metadatos de CLR, se producirá un error en el método `OpenScope`.</span><span class="sxs-lookup"><span data-stu-id="fe5df-115">If the target file does not contain CLR metadata, the `OpenScope` method will fail.</span></span>  
  
 <span data-ttu-id="fe5df-116">En el .NET Framework versión 1,0 y la versión 1,1, si se abre un ámbito con `dwOpenFlags` establecido en unread, es válido para el uso compartido.</span><span class="sxs-lookup"><span data-stu-id="fe5df-116">In the .NET Framework version 1.0 and version 1.1, if a scope is opened with `dwOpenFlags` set to ofRead, it is eligible for sharing.</span></span> <span data-ttu-id="fe5df-117">Es decir, si las llamadas subsiguientes a `OpenScope` pasan el nombre de un archivo que se abrió anteriormente, se reutiliza el ámbito existente y no se crea un nuevo conjunto de estructuras de datos.</span><span class="sxs-lookup"><span data-stu-id="fe5df-117">That is, if subsequent calls to `OpenScope` pass in the name of a file that was previously opened, the existing scope is reused and a new set of data structures is not created.</span></span> <span data-ttu-id="fe5df-118">Sin embargo, pueden surgir problemas debido a este uso compartido.</span><span class="sxs-lookup"><span data-stu-id="fe5df-118">However, problems can arise due to this sharing.</span></span>  
  
 <span data-ttu-id="fe5df-119">En la versión .NET Framework 2,0, los ámbitos abiertos con `dwOpenFlags` establecido en unread ya no se comparten.</span><span class="sxs-lookup"><span data-stu-id="fe5df-119">In the .NET Framework version 2.0, scopes opened with `dwOpenFlags` set to ofRead are no longer shared.</span></span> <span data-ttu-id="fe5df-120">Use el valor ofReadOnly para permitir que se comparta el ámbito.</span><span class="sxs-lookup"><span data-stu-id="fe5df-120">Use the ofReadOnly value to allow the scope to be shared.</span></span> <span data-ttu-id="fe5df-121">Cuando se comparte un ámbito, se producirá un error en las consultas que usan interfaces de metadatos de "lectura/escritura".</span><span class="sxs-lookup"><span data-stu-id="fe5df-121">When a scope is shared, queries that use "read/write" metadata interfaces will fail.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fe5df-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fe5df-122">Requirements</span></span>  
 <span data-ttu-id="fe5df-123">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fe5df-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fe5df-124">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="fe5df-124">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="fe5df-125">**Biblioteca:** Se utiliza como recurso en MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="fe5df-125">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="fe5df-126">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fe5df-126">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe5df-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="fe5df-127">See also</span></span>

- [<span data-ttu-id="fe5df-128">IMetaDataDispenser (interfaz)</span><span class="sxs-lookup"><span data-stu-id="fe5df-128">IMetaDataDispenser Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
- [<span data-ttu-id="fe5df-129">IMetaDataDispenserEx (interfaz)</span><span class="sxs-lookup"><span data-stu-id="fe5df-129">IMetaDataDispenserEx Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)
- [<span data-ttu-id="fe5df-130">IMetaDataAssemblyEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="fe5df-130">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
- [<span data-ttu-id="fe5df-131">IMetaDataAssemblyImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="fe5df-131">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
- [<span data-ttu-id="fe5df-132">IMetaDataEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="fe5df-132">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="fe5df-133">IMetaDataEmit2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="fe5df-133">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
- [<span data-ttu-id="fe5df-134">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="fe5df-134">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="fe5df-135">IMetaDataImport2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="fe5df-135">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
