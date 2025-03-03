---
title: ICorProfilerInfo::GetModuleMetaData (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetModuleMetaData
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetModuleMetaData
helpviewer_keywords:
- GetModuleMetaData method [.NET Framework profiling]
- ICorProfilerInfo::GetModuleMetaData method [.NET Framework profiling]
ms.assetid: 7a439d92-348a-44dd-b60f-cad7cba56379
topic_type:
- apiref
ms.openlocfilehash: c7bf8e3ebedb17a4536b604909434c3e004fc828
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74439833"
---
# <a name="icorprofilerinfogetmodulemetadata-method"></a>ICorProfilerInfo::GetModuleMetaData (Método)
Obtiene una instancia de la interfaz de metadatos que se asigna al módulo especificado.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetModuleMetaData(  
    [in]  ModuleID moduleId,  
    [in]  DWORD    dwOpenFlags,  
    [in]  REFIID   riid,  
    [out] IUnknown **ppOut);  
```  
  
## <a name="parameters"></a>Parámetros  
 `moduleId`  
 de IDENTIFICADOR del módulo al que se asignará la instancia de interfaz.  
  
 `dwOpenFlags`  
 de Un valor de la enumeración [CorOpenFlags (](../../../../docs/framework/unmanaged-api/metadata/coropenflags-enumeration.md) que especifica el modo para abrir los archivos de manifiesto. Solo los bits `ofRead`, `ofWrite` y `ofNoTransform` son válidos.  
  
 `riid`  
 de IDENTIFICADOR de referencia (GUID) de la interfaz de metadatos cuya instancia se va a recuperar. Vea [interfaces de metadatos](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md) para obtener una lista de las interfaces.  
  
 `ppOut`  
 enuncia Puntero a la dirección de la instancia de la interfaz de metadatos.  
  
## <a name="remarks"></a>Comentarios  
 Puede solicitar que los metadatos se abran en modo de lectura/escritura, pero esto hará que la ejecución del programa sea más lenta, ya que los cambios realizados en los metadatos no se pueden optimizar tal como estaban del compilador.  
  
 Algunos módulos (como los módulos de recursos) no tienen metadatos. En estos casos, `GetModuleMetaData` devolverá un valor HRESULT de S_FALSE y un valor null en *`ppOut`.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorProfilerInfo (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
