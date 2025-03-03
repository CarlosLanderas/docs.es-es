---
title: ICorDebugFunction3::GetActiveReJitRequestILCode (Método)
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorDebugFunction3.GetActiveReJitRequestILCode
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 88584574-ade5-45b2-9778-489ed5c4dd7f
topic_type:
- apiref
ms.openlocfilehash: 0e706861237ed08700ef0abcc424b6f1de5f462c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134639"
---
# <a name="icordebugfunction3getactiverejitrequestilcode-method"></a>ICorDebugFunction3::GetActiveReJitRequestILCode (Método)
[Compatible con .NET Framework 4.5.2 y versiones posteriores]  
  
 Obtiene un puntero de interfaz a un [ICorDebugILCode](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-interface.md) que contiene el Il de una solicitud ReJIT activa.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp
HRESULT GetActiveReJitRequestILCode(  
   ICorDebugILCode **ppReJitedILCode  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `ppReJitedILCode`  
 Puntero al IL desde una solicitud ReJIT activa.  
  
## <a name="remarks"></a>Comentarios  
 Si el método que representa este objeto `ICorDebugFunction3` tiene una solicitud ReJIT activa, `ppReJitedILCode` devuelve un puntero a su IL. Si no hay ninguna solicitud activa, que es un caso común, `ppReJitedILCode` es **null**.  
  
 Una solicitud ReJIT se activa justo después de que la ejecución vuelva de la llamada al método [ICorProfilerCallback4:: getrejitparameters (](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-getrejitparameters-method.md) . Puede que JIT aún no la haya compilado y que los subprocesos se estén ejecutando en la versión original del código. Una solicitud ReJIT pasa a estar inactiva durante la llamada del generador de perfiles al método [ICorProfilerInfo4:: requestrevert (](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-requestrevert-method.md) . Incluso después de revertir el IL, un subproceso puede seguir ejecutándose en el código JIT nuevamente compilado (ReJIT).  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorDebugFunction3 (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction3-interface.md)
- [Interfaces de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [ReJIT: Guía de procedimientos](https://blogs.msdn.microsoft.com/davbr/2011/10/12/rejit-a-how-to-guide/)
