---
title: ICorProfilerCallback::RuntimeResumeFinished (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RuntimeResumeFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RuntimeResumeFinished
helpviewer_keywords:
- RuntimeResumeFinished method [.NET Framework profiling]
- ICorProfilerCallback::RuntimeResumeFinished method [.NET Framework profiling]
ms.assetid: 76de0494-dc49-426b-887d-bee98806a982
topic_type:
- apiref
ms.openlocfilehash: 81c26214762fba1cac43e42adc1ee9909759972f
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74430309"
---
# <a name="icorprofilercallbackruntimeresumefinished-method"></a><span data-ttu-id="c93b2-102">ICorProfilerCallback::RuntimeResumeFinished (Método)</span><span class="sxs-lookup"><span data-stu-id="c93b2-102">ICorProfilerCallback::RuntimeResumeFinished Method</span></span>
<span data-ttu-id="c93b2-103">Notifica al generador de perfiles que el tiempo de ejecución ha reanudado todos los subprocesos en tiempo de ejecución y ha vuelto a la operación normal.</span><span class="sxs-lookup"><span data-stu-id="c93b2-103">Notifies the profiler that the runtime has resumed all runtime threads and has returned to normal operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c93b2-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c93b2-104">Syntax</span></span>  
  
```cpp  
HRESULT RuntimeResumeFinished();  
```  
  
## <a name="remarks"></a><span data-ttu-id="c93b2-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c93b2-105">Remarks</span></span>  
 <span data-ttu-id="c93b2-106">No se garantiza que la devolución de llamada de `RuntimeResumeFinished` se produzca en el mismo subproceso que la devolución de llamada [ICorProfilerCallback:: runtimesuspendstarted (](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendstarted-method.md) .</span><span class="sxs-lookup"><span data-stu-id="c93b2-106">The `RuntimeResumeFinished` callback is not guaranteed to occur on the same thread as the [ICorProfilerCallback::RuntimeSuspendStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendstarted-method.md) callback.</span></span> <span data-ttu-id="c93b2-107">Sin embargo, se garantiza que se produzca en el mismo subproceso que la devolución de llamada [ICorProfilerCallback:: RuntimeResumeStarted (](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimeresumestarted-method.md) .</span><span class="sxs-lookup"><span data-stu-id="c93b2-107">However, it is guaranteed to occur on the same thread as the [ICorProfilerCallback::RuntimeResumeStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimeresumestarted-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c93b2-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c93b2-108">Requirements</span></span>  
 <span data-ttu-id="c93b2-109">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c93b2-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c93b2-110">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c93b2-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c93b2-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c93b2-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c93b2-112">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c93b2-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c93b2-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="c93b2-113">See also</span></span>

- [<span data-ttu-id="c93b2-114">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="c93b2-114">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
