---
title: IMetaDataImport::ResetEnum (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataImport.ResetEnum
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::ResetEnum
helpviewer_keywords:
- ResetEnum method [.NET Framework metadata]
- IMetaDataImport::ResetEnum method [.NET Framework metadata]
ms.assetid: dda867b5-1050-49ba-b01c-fcc83b7a5617
topic_type:
- apiref
ms.openlocfilehash: 3f965ab215ff861c6df61de82dcbbea6b389c8da
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74426781"
---
# <a name="imetadataimportresetenum-method"></a><span data-ttu-id="eefb0-102">IMetaDataImport::ResetEnum (Método)</span><span class="sxs-lookup"><span data-stu-id="eefb0-102">IMetaDataImport::ResetEnum Method</span></span>
<span data-ttu-id="eefb0-103">Restablece el enumerador especificado a la posición especificada.</span><span class="sxs-lookup"><span data-stu-id="eefb0-103">Resets the specified enumerator to the specified position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eefb0-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="eefb0-104">Syntax</span></span>  
  
```cpp  
HRESULT ResetEnum (  
   [in] HCORENUM    hEnum,   
   [in] ULONG       ulPos  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="eefb0-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="eefb0-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="eefb0-106">de Enumerador que se va a restablecer.</span><span class="sxs-lookup"><span data-stu-id="eefb0-106">[in] The enumerator to reset.</span></span>  
  
 `ulPos`  
 <span data-ttu-id="eefb0-107">de Nueva posición en la que se va a colocar el enumerador.</span><span class="sxs-lookup"><span data-stu-id="eefb0-107">[in] The new position at which to place the enumerator.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eefb0-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="eefb0-108">Requirements</span></span>  
 <span data-ttu-id="eefb0-109">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="eefb0-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eefb0-110">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="eefb0-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="eefb0-111">**Biblioteca:** Se incluye como recurso en MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="eefb0-111">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="eefb0-112">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eefb0-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eefb0-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="eefb0-113">See also</span></span>

- [<span data-ttu-id="eefb0-114">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="eefb0-114">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="eefb0-115">IMetaDataImport2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="eefb0-115">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
