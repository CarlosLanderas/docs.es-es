---
title: ICorProfilerCallback::Shutdown (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.Shutdown
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::Shutdown
helpviewer_keywords:
- ICorProfilerCallback::Shutdown method [.NET Framework profiling]
- Shutdown method [.NET Framework profiling]
ms.assetid: 1ea194f0-a331-4855-a2ce-37393b8e5f84
topic_type:
- apiref
ms.openlocfilehash: 63e41df8af85d94df068526ef69708687b341e78
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446947"
---
# <a name="icorprofilercallbackshutdown-method"></a><span data-ttu-id="3e5dd-102">ICorProfilerCallback::Shutdown (Método)</span><span class="sxs-lookup"><span data-stu-id="3e5dd-102">ICorProfilerCallback::Shutdown Method</span></span>
<span data-ttu-id="3e5dd-103">Notifies the profiler that the application is shutting down.</span><span class="sxs-lookup"><span data-stu-id="3e5dd-103">Notifies the profiler that the application is shutting down.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3e5dd-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3e5dd-104">Syntax</span></span>  
  
```cpp  
HRESULT Shutdown();  
```  
  
## <a name="remarks"></a><span data-ttu-id="3e5dd-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="3e5dd-105">Remarks</span></span>  
 <span data-ttu-id="3e5dd-106">The profiler code cannot safely call methods of the [ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md) interface after the `Shutdown` method is called.</span><span class="sxs-lookup"><span data-stu-id="3e5dd-106">The profiler code cannot safely call methods of the [ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md) interface after the `Shutdown` method is called.</span></span> <span data-ttu-id="3e5dd-107">Any calls to `ICorProfilerInfo` methods result in undefined behavior after the `Shutdown` method returns.</span><span class="sxs-lookup"><span data-stu-id="3e5dd-107">Any calls to `ICorProfilerInfo` methods result in undefined behavior after the `Shutdown` method returns.</span></span> <span data-ttu-id="3e5dd-108">Certain immutable events may still occur after shutdown; the profiler should take care to return immediately when this occurs.</span><span class="sxs-lookup"><span data-stu-id="3e5dd-108">Certain immutable events may still occur after shutdown; the profiler should take care to return immediately when this occurs.</span></span>  
  
 <span data-ttu-id="3e5dd-109">The `Shutdown` method will be called only if the managed application that is being profiled started as managed code (that is, the initial frame on the process stack is managed).</span><span class="sxs-lookup"><span data-stu-id="3e5dd-109">The `Shutdown` method will be called only if the managed application that is being profiled started as managed code (that is, the initial frame on the process stack is managed).</span></span> <span data-ttu-id="3e5dd-110">If the application started as unmanaged code but later jumped into managed code, thereby creating an instance of the common language runtime (CLR), then `Shutdown` will not be called.</span><span class="sxs-lookup"><span data-stu-id="3e5dd-110">If the application started as unmanaged code but later jumped into managed code, thereby creating an instance of the common language runtime (CLR), then `Shutdown` will not be called.</span></span> <span data-ttu-id="3e5dd-111">For these cases, the profiler should include in its library a `DllMain` routine that uses the DLL_PROCESS_DETACH value to free any resources and perform clean-up processing of its data, such as flushing traces to disk and so on.</span><span class="sxs-lookup"><span data-stu-id="3e5dd-111">For these cases, the profiler should include in its library a `DllMain` routine that uses the DLL_PROCESS_DETACH value to free any resources and perform clean-up processing of its data, such as flushing traces to disk and so on.</span></span>  
  
 <span data-ttu-id="3e5dd-112">In general, the profiler must cope with unexpected shutdowns.</span><span class="sxs-lookup"><span data-stu-id="3e5dd-112">In general, the profiler must cope with unexpected shutdowns.</span></span> <span data-ttu-id="3e5dd-113">For example, a process might be halted by Win32's `TerminateProcess` method (declared in Winbase.h).</span><span class="sxs-lookup"><span data-stu-id="3e5dd-113">For example, a process might be halted by Win32's `TerminateProcess` method (declared in Winbase.h).</span></span> <span data-ttu-id="3e5dd-114">In other cases, the CLR will halt certain managed threads (background threads) without delivering orderly destruction messages for them.</span><span class="sxs-lookup"><span data-stu-id="3e5dd-114">In other cases, the CLR will halt certain managed threads (background threads) without delivering orderly destruction messages for them.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3e5dd-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3e5dd-115">Requirements</span></span>  
 <span data-ttu-id="3e5dd-116">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3e5dd-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3e5dd-117">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="3e5dd-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="3e5dd-118">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3e5dd-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3e5dd-119">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3e5dd-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e5dd-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="3e5dd-120">See also</span></span>

- [<span data-ttu-id="3e5dd-121">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="3e5dd-121">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="3e5dd-122">Initialize (método)</span><span class="sxs-lookup"><span data-stu-id="3e5dd-122">Initialize Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md)
