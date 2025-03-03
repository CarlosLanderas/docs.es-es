---
title: ICorProfilerCallback8::D método ynamicMethodJITCompilationStarted
ms.date: 04/10/2018
api_name:
- ICorProfilerCallback8.DynamicMethodJITCompilationStarted
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
ms.openlocfilehash: 1eaf29e1c93f352facde4af2ee57910783d82e5d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136461"
---
# <a name="icorprofilercallback8dynamicmethodjitcompilationstarted-method"></a>ICorProfilerCallback8::D método ynamicMethodJITCompilationStarted
[Se admite en el .NET Framework 4,7 y versiones posteriores]  
  
Notifica al generador de perfiles cada vez que se inicia la compilación JIT de un método dinámico.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT DynamicMethodJITCompilationStarted(  
     [in]  FunctionID  functionId,   
     [in]  BOOL        fIsSafeToBlock,   
     [in]  LPCBYTE     pILHeader,   
     [in]  LONG        cbILHeader   
);  
```  
  
## <a name="parameters"></a>Parámetros  
[in] `functionId`  
Identificador de la función en memoria para la que se inicia la compilación JIT.   

[in] `fIsSafeToBlock`   
`true` para indicar que el bloqueo puede hacer que el tiempo de ejecución espere a que el subproceso que realiza la llamada devuelva de esta devolución de llamada; `false` para indicar que el bloqueo no afectará al funcionamiento del tiempo de ejecución.  

[in] `pILHeader`    
Puntero al primer byte del encabezado IL del método.   

[in] `cbILHeader`    
Número de bytes del encabezado IL. 

## <a name="remarks"></a>Comentarios  

Esta devolución de llamada se desencadena cada vez que se compila un método dinámico. Esto incluye varios códigos auxiliares de IL y métodos LCG. Su objetivo es proporcionar a los escritores de Profiler información suficiente para identificar el método compilado para los usuarios.

> [!NOTE]
> `functionId` valores no se pueden usar para resolver sus tokens de metadatos, porque los métodos dinámicos no tienen metadatos.

El puntero `pILHeader` solo es válido durante la devolución de llamada.

## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  
  
## <a name="see-also"></a>Vea también

- [DynamicMethodJITCompilationFinished (método)](icorprofilercallback8-dynamicmethodjitcompilationfinished-method.md)
- [ICorProfilerCallback8 (interfaz)](icorprofilercallback8-interface.md)
