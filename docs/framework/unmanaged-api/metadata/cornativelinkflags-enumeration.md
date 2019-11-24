---
title: CorNativeLinkFlags (Enumeración)
ms.date: 03/30/2017
api_name:
- CorNativeLinkFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorNativeLinkFlags
helpviewer_keywords:
- CorNativeLinkFlags enumeration [.NET Framework metadata]
ms.assetid: 8027df7c-cfad-4724-bda0-7538d9519070
topic_type:
- apiref
ms.openlocfilehash: 1362efbf518310240ce665badc93810d1c0b9b89
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74450187"
---
# <a name="cornativelinkflags-enumeration"></a><span data-ttu-id="de1c7-102">CorNativeLinkFlags (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="de1c7-102">CorNativeLinkFlags Enumeration</span></span>
<span data-ttu-id="de1c7-103">Proporciona valores de marca que el vinculador usa al vincular código nativo.</span><span class="sxs-lookup"><span data-stu-id="de1c7-103">Provides flag values used by the linker when linking native code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="de1c7-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="de1c7-104">Syntax</span></span>  
  
```cpp  
typedef enum  
{  
    nlfNone         = 0x00,  
    nlfLastError    = 0x01,  
    nlfNoMangle     = 0x02,  
    nlfMaxValue     = 0x03  
} CorNativeLinkFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="de1c7-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="de1c7-105">Members</span></span>  
  
|<span data-ttu-id="de1c7-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="de1c7-106">Member</span></span>|<span data-ttu-id="de1c7-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="de1c7-107">Description</span></span>|  
|------------|-----------------|  
|`nlfNone`|<span data-ttu-id="de1c7-108">Indicates no flags.</span><span class="sxs-lookup"><span data-stu-id="de1c7-108">Indicates no flags.</span></span>|  
|`nlfLastError`|<span data-ttu-id="de1c7-109">Indicates a `setLastError` keyword.</span><span class="sxs-lookup"><span data-stu-id="de1c7-109">Indicates a `setLastError` keyword.</span></span>|  
|`nlfNoMangle`|<span data-ttu-id="de1c7-110">Indicates a `nomangle` keyword.</span><span class="sxs-lookup"><span data-stu-id="de1c7-110">Indicates a `nomangle` keyword.</span></span>|  
|`nlfMaxValue`|<span data-ttu-id="de1c7-111">No se utiliza.</span><span class="sxs-lookup"><span data-stu-id="de1c7-111">Not used.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="de1c7-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="de1c7-112">Requirements</span></span>  
 <span data-ttu-id="de1c7-113">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="de1c7-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="de1c7-114">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="de1c7-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="de1c7-115">**Library:** Included as a resource in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="de1c7-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="de1c7-116">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="de1c7-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de1c7-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="de1c7-117">See also</span></span>

- [<span data-ttu-id="de1c7-118">Enumeraciones para metadatos</span><span class="sxs-lookup"><span data-stu-id="de1c7-118">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
