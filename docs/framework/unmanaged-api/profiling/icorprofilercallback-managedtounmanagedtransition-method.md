---
title: ICorProfilerCallback::ManagedToUnmanagedTransition (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ManagedToUnmanagedTransition
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ManagedToUnmanagedTransition
helpviewer_keywords:
- ManagedToUnmanagedTransition method [.NET Framework profiling]
- ICorProfilerCallback::ManagedToUnmanagedTransition method [.NET Framework profiling]
ms.assetid: ef3cd619-912d-40c5-a449-03ba02a39ee7
topic_type:
- apiref
ms.openlocfilehash: f4f5871bdd7adf11fcc811fd40c62e3027b8e607
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74426175"
---
# <a name="icorprofilercallbackmanagedtounmanagedtransition-method"></a>ICorProfilerCallback::ManagedToUnmanagedTransition (Método)
Notifica al generador de perfiles que se ha producido una transición de código administrado a código no administrado.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT ManagedToUnmanagedTransition(  
    [in] FunctionID functionId,  
    [in] COR_PRF_TRANSITION_REASON reason);  
```  
  
## <a name="parameters"></a>Parámetros  
 `functionId`  
 de IDENTIFICADOR de la función a la que se está llamando.  
  
 `reason`  
 de Un valor de la enumeración [COR_PRF_TRANSITION_REASON](../../../../docs/framework/unmanaged-api/profiling/cor-prf-transition-reason-enumeration.md) que indica si la transición se produjo debido a una llamada a código no administrado desde código administrado, o debido a una devolución de una función administrada a la que llama un no administrado.  
  
## <a name="remarks"></a>Comentarios  
 Si el valor de `reason` es COR_PRF_TRANSITION_CALL, el identificador de función es el de la función no administrada, que nunca se habrá compilado con el compilador Just-in-Time. Las funciones no administradas tienen información básica asociada, como un nombre y algunos metadatos. Si se llamó a la función no administrada mediante invocación de plataforma implícita (PInvoke), el tiempo de ejecución no puede determinar el destino de la llamada y el valor de `functionId` será null. Para obtener más información sobre PInvoke implícito, [vea C++ usar Interop (implicit PInvoke)](/cpp/dotnet/using-cpp-interop-implicit-pinvoke).  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorProfilerCallback (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [UnmanagedToManagedTransition (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-unmanagedtomanagedtransition-method.md)
- [Usar un elemento PInvoke explícito en C++ (Atributo DllImport)](/cpp/dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute)
