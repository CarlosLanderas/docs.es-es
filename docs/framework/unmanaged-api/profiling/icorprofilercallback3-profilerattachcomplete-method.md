---
title: ICorProfilerCallback3::ProfilerAttachComplete (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback3.ProfilerAttachComplete Method
api_location:
- Mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback3::ProfilerAttachComplete
helpviewer_keywords:
- ProfilerAttachComplete method [.NET Framework profiling]
- ICorProfilerCallback3::ProfilerAttachComplete method [.NET Framework profiling]
ms.assetid: 257d6076-06e0-4d93-bb33-651fbb2b92d7
topic_type:
- apiref
ms.openlocfilehash: 4c5b8f18424ba54d9e8e14ba0a518a89e0d54796
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74439468"
---
# <a name="icorprofilercallback3profilerattachcomplete-method"></a><span data-ttu-id="ef6b5-102">ICorProfilerCallback3::ProfilerAttachComplete (Método)</span><span class="sxs-lookup"><span data-stu-id="ef6b5-102">ICorProfilerCallback3::ProfilerAttachComplete Method</span></span>
<span data-ttu-id="ef6b5-103">Lo llama el Common Language Runtime (CLR) para indicar que el generador de perfiles ahora puede llamar a los métodos de puesta al día de [ICorProfilerInfo3:: EnumJITedFunctions (](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-enumjitedfunctions-method.md) y [Icorprofilerinfo3:: EnumModules (](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-enummodules-method.md) .</span><span class="sxs-lookup"><span data-stu-id="ef6b5-103">Called by the common language runtime (CLR) to indicate that the profiler can now call the [ICorProfilerInfo3::EnumJITedFunctions](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-enumjitedfunctions-method.md) and [ICorProfilerInfo3::EnumModules](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-enummodules-method.md) catch-up methods.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ef6b5-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ef6b5-104">Syntax</span></span>  
  
```cpp  
HRESULT ProfilerAttachComplete ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="ef6b5-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ef6b5-105">Remarks</span></span>  
 <span data-ttu-id="ef6b5-106">La devolución de llamada de `ProfilerAttachComplete` se emite después de llamar al método [ICorProfilerCallback3:: InitializeForAttach](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback3-initializeforattach-method.md) .</span><span class="sxs-lookup"><span data-stu-id="ef6b5-106">The `ProfilerAttachComplete` callback is issued after the [ICorProfilerCallback3::InitializeForAttach](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback3-initializeforattach-method.md) method is called.</span></span> <span data-ttu-id="ef6b5-107">Indica que:</span><span class="sxs-lookup"><span data-stu-id="ef6b5-107">It indicates the following:</span></span>  
  
- <span data-ttu-id="ef6b5-108">Las devoluciones de llamada que solicitó el generador de perfiles en `InitializeForAttach` se han activado.</span><span class="sxs-lookup"><span data-stu-id="ef6b5-108">The callbacks that were requested by the profiler in `InitializeForAttach` have been activated.</span></span>  
  
- <span data-ttu-id="ef6b5-109">El generador de perfiles ya puede poner al día los identificadores asociados sin preocuparse sobre las notificaciones que faltan.</span><span class="sxs-lookup"><span data-stu-id="ef6b5-109">The profiler can now perform catch-up on the associated IDs without being concerned about missing notifications.</span></span>  
  
 <span data-ttu-id="ef6b5-110">CLR pasa por alto el valor devuelto por esta devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="ef6b5-110">The CLR ignores the return value from this callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ef6b5-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ef6b5-111">Requirements</span></span>  
 <span data-ttu-id="ef6b5-112">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ef6b5-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ef6b5-113">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ef6b5-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ef6b5-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ef6b5-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ef6b5-115">**Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ef6b5-115">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef6b5-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="ef6b5-116">See also</span></span>

- [<span data-ttu-id="ef6b5-117">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ef6b5-117">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="ef6b5-118">ICorProfilerInfo3 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ef6b5-118">ICorProfilerInfo3 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)
- [<span data-ttu-id="ef6b5-119">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="ef6b5-119">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="ef6b5-120">Generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="ef6b5-120">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
