---
title: COR_PRF_FUNCTION_ARGUMENT_RANGE (Estructura)
ms.date: 03/30/2017
api_name:
- COR_PRF_FUNCTION_ARGUMENT_RANGE
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_FUNCTION_ARGUMENT_RANGE
helpviewer_keywords:
- COR_PRF_FUNCTION_ARGUMENT_RANGE structure [.NET Framework profiling'
ms.assetid: 9f469eac-ac66-419b-8668-fe705bc1a51f
topic_type:
- apiref
ms.openlocfilehash: 223ad57f0b317bf75778d4e5355ec129185f5a29
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449487"
---
# <a name="cor_prf_function_argument_range-structure"></a><span data-ttu-id="36635-102">COR_PRF_FUNCTION_ARGUMENT_RANGE (Estructura)</span><span class="sxs-lookup"><span data-stu-id="36635-102">COR_PRF_FUNCTION_ARGUMENT_RANGE Structure</span></span>
<span data-ttu-id="36635-103">Representa un bloque de argumentos de función almacenados en la memoria de forma contigua, ordenados de izquierda a derecha.</span><span class="sxs-lookup"><span data-stu-id="36635-103">Represents a block of function arguments stored contiguously in left-to-right order in memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="36635-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="36635-104">Syntax</span></span>  
  
```cpp  
typedef struct _COR_PRF_FUNCTION_ARGUMENT_RANGE {  
    UINT_PTR startAddress;  
    ULONG length;  
} COR_PRF_FUNCTION_ARGUMENT_RANGE;  
```  
  
## <a name="members"></a><span data-ttu-id="36635-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="36635-105">Members</span></span>  
  
|<span data-ttu-id="36635-106">Miembros</span><span class="sxs-lookup"><span data-stu-id="36635-106">Members</span></span>|<span data-ttu-id="36635-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="36635-107">Description</span></span>|  
|-------------|-----------------|  
|`startAddress`|<span data-ttu-id="36635-108">Dirección inicial del bloque.</span><span class="sxs-lookup"><span data-stu-id="36635-108">The starting address of the block.</span></span>|  
|`length`|<span data-ttu-id="36635-109">Longitud del bloque contiguo.</span><span class="sxs-lookup"><span data-stu-id="36635-109">The length of the contiguous block.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="36635-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="36635-110">Requirements</span></span>  
 <span data-ttu-id="36635-111">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="36635-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="36635-112">**Encabezado:** Corprof. idl</span><span class="sxs-lookup"><span data-stu-id="36635-112">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="36635-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="36635-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="36635-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="36635-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36635-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="36635-115">See also</span></span>

- [<span data-ttu-id="36635-116">Estructuras para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="36635-116">Profiling Structures</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-structures.md)
