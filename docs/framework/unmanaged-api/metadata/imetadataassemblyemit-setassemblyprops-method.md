---
title: IMetaDataAssemblyEmit::SetAssemblyProps (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit.SetAssemblyProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::SetAssemblyProps
helpviewer_keywords:
- SetAssemblyProps method [.NET Framework metadata]
- IMetaDataAssemblyEmit::SetAssemblyProps method [.NET Framework metadata]
ms.assetid: 91b633d7-9e75-43c3-a8d2-2144984e5f9e
topic_type:
- apiref
ms.openlocfilehash: f79320d5b7d2ad4ad44a79fae063ce6718490a70
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74431951"
---
# <a name="imetadataassemblyemitsetassemblyprops-method"></a><span data-ttu-id="6b193-102">IMetaDataAssemblyEmit::SetAssemblyProps (Método)</span><span class="sxs-lookup"><span data-stu-id="6b193-102">IMetaDataAssemblyEmit::SetAssemblyProps Method</span></span>
<span data-ttu-id="6b193-103">Modifica la estructura de metadatos `Assembly` especificada.</span><span class="sxs-lookup"><span data-stu-id="6b193-103">Modifies the specified `Assembly` metadata structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6b193-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6b193-104">Syntax</span></span>  
  
```cpp  
HRESULT SetAssemblyProps (  
    [in] mdAssembly               pma,  
    [in] const void               *pbPublicKey,  
    [in] ULONG                    cbPublicKey,  
    [in] ULONG                    ulHashAlgId,  
    [in] LPCWSTR                  szName,  
    [in] const ASSEMBLYMETADATA   *pMetaData,  
    [in] DWORD                    dwAssemblyFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6b193-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="6b193-105">Parameters</span></span>  
 `pma`  
 <span data-ttu-id="6b193-106">[in] The metadata token that specifies the `Assembly` metadata structure to be modified.</span><span class="sxs-lookup"><span data-stu-id="6b193-106">[in] The metadata token that specifies the `Assembly` metadata structure to be modified.</span></span>  
  
 `pbPublicKey`  
 <span data-ttu-id="6b193-107">[in] A pointer to the public key of the publisher of the assembly.</span><span class="sxs-lookup"><span data-stu-id="6b193-107">[in] A pointer to the public key of the publisher of the assembly.</span></span>  
  
 `cbPublicKey`  
 <span data-ttu-id="6b193-108">[in] The size in bytes of `pbPublicKey`.</span><span class="sxs-lookup"><span data-stu-id="6b193-108">[in] The size in bytes of `pbPublicKey`.</span></span>  
  
 `ulHashAlgId`  
 <span data-ttu-id="6b193-109">[in] The identifier for the hash algorithm used to hash the assembly files.</span><span class="sxs-lookup"><span data-stu-id="6b193-109">[in] The identifier for the hash algorithm used to hash the assembly files.</span></span>  
  
 `szName`  
 <span data-ttu-id="6b193-110">[in] The human-readable text name of the assembly.</span><span class="sxs-lookup"><span data-stu-id="6b193-110">[in] The human-readable text name of the assembly.</span></span>  
  
 `pMetaData`  
 <span data-ttu-id="6b193-111">[in] A pointer to the ASSEMBLYMETADATA that contains version, platform, and locale information for the assembly.</span><span class="sxs-lookup"><span data-stu-id="6b193-111">[in] A pointer to the ASSEMBLYMETADATA that contains version, platform, and locale information for the assembly.</span></span>  
  
 `dwAssemblyFlags`  
 <span data-ttu-id="6b193-112">[in] A bitwise combination of [AssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/assemblyflags-enumeration.md) values that specify various attributes of the assembly.</span><span class="sxs-lookup"><span data-stu-id="6b193-112">[in] A bitwise combination of [AssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/assemblyflags-enumeration.md) values that specify various attributes of the assembly.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6b193-113">Comentarios</span><span class="sxs-lookup"><span data-stu-id="6b193-113">Remarks</span></span>  
 <span data-ttu-id="6b193-114">To create an `Assembly` metadata structure, use the [IMetaDataAssemblyEmit::DefineAssembly](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassembly-method.md) method.</span><span class="sxs-lookup"><span data-stu-id="6b193-114">To create an `Assembly` metadata structure, use the [IMetaDataAssemblyEmit::DefineAssembly](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassembly-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6b193-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6b193-115">Requirements</span></span>  
 <span data-ttu-id="6b193-116">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6b193-116">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6b193-117">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="6b193-117">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="6b193-118">**Library:** Used as a resource in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="6b193-118">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="6b193-119">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6b193-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b193-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="6b193-120">See also</span></span>

- [<span data-ttu-id="6b193-121">IMetaDataAssemblyEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="6b193-121">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
