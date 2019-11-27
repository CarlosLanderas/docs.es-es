---
title: IMetaDataTables::GetStringHeapSize (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetStringHeapSize
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetStringHeapSize
helpviewer_keywords:
- IMetaDataTables::GetStringHeapSize method [.NET Framework metadata]
- GetStringHeapSize method [.NET Framework metadata]
ms.assetid: ed8f6335-81f5-4c09-81a9-2a909fc530c9
topic_type:
- apiref
ms.openlocfilehash: 43599a7e39ca4cc9d27dab43a948dc2f04e5010a
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74426676"
---
# <a name="imetadatatablesgetstringheapsize-method"></a><span data-ttu-id="cd373-102">IMetaDataTables::GetStringHeapSize (Método)</span><span class="sxs-lookup"><span data-stu-id="cd373-102">IMetaDataTables::GetStringHeapSize Method</span></span>
<span data-ttu-id="cd373-103">Obtiene el tamaño, en bytes, del montón de cadenas.</span><span class="sxs-lookup"><span data-stu-id="cd373-103">Gets the size, in bytes, of the string heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cd373-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cd373-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStringHeapSize (  
    [out] ULONG   *pcbStrings  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cd373-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="cd373-105">Parameters</span></span>  
 `pcbStrings`  
 <span data-ttu-id="cd373-106">enuncia Puntero al tamaño, en bytes, del montón de cadenas.</span><span class="sxs-lookup"><span data-stu-id="cd373-106">[out] A pointer to the size, in bytes, of the string heap.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cd373-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="cd373-107">Requirements</span></span>  
 <span data-ttu-id="cd373-108">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cd373-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cd373-109">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="cd373-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="cd373-110">**Biblioteca:** Se utiliza como recurso en MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="cd373-110">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="cd373-111">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cd373-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd373-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="cd373-112">See also</span></span>

- [<span data-ttu-id="cd373-113">IMetaDataTables (interfaz)</span><span class="sxs-lookup"><span data-stu-id="cd373-113">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="cd373-114">IMetaDataTables2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="cd373-114">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
