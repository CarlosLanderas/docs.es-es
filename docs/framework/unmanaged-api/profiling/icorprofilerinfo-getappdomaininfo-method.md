---
title: ICorProfilerInfo::GetAppDomainInfo (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetAppDomainInfo
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetAppDomainInfo
helpviewer_keywords:
- ICorProfilerInfo::GetAppDomainInfo method [.NET Framework profiling]
- GetAppDomainInfo method [.NET Framework profiling]
ms.assetid: a6bf5a04-e03e-44f0-917a-96f6a6d3cc96
topic_type:
- apiref
ms.openlocfilehash: 8c13ce443037d706f9eba49760ba76f47c5a6538
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448171"
---
# <a name="icorprofilerinfogetappdomaininfo-method"></a>ICorProfilerInfo::GetAppDomainInfo (Método)
Acepta un identificador de dominio de una aplicación. Devuelve un nombre de dominio de una aplicación y el identificador del proceso que lo contiene.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetAppDomainInfo(  
    [in]  AppDomainID appDomainId,  
    [in]  ULONG       cchName,  
    [out] ULONG       *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]  
          WCHAR       szName[] ,  
    [out] ProcessID   *pProcessId);  
```  
  
## <a name="parameters"></a>Parámetros  
 `appDomainId`  
 [in] Identificador de dominio de la aplicación.  
  
 `cchName`  
 [in] Longitud, en caracteres, del búfer de retorno `szName`.  
  
 `pcchName`  
 [out] Puntero a la longitud total de caracteres del nombre de dominio de la aplicación.  
  
 `szName`  
 [out] Búfer de caracteres anchos proporcionado por el llamador. Con la devolución del método, `szName` contendrá el nombre total o parcial del dominio de aplicación.  
  
 `pProcessId`  
 [out] Puntero al identificador del proceso que contiene el dominio de la aplicación.  
  
## <a name="remarks"></a>Comentarios  
 Tras la devolución de este método, debe comprobar que el búfer `szName` era lo suficientemente grande como para contener el nombre completo del dominio de la aplicación. Para ello, compare el valor al que `pcchName` apunta con el valor del parámetro `cchName`. Si `pcchName` apunta un valor mayor que `cchName`, asigne un búfer `szName` mayor, actualice `cchName` con el nuevo tamaño de mayores dimensiones y vuelva a llamar a `GetAppDomainInfo`.  
  
 También tiene la opción de llamar primero a `GetAppDomainInfo` con un búfer `szName` de longitud de cero para obtener el tamaño de búfer correcto. Después, puede establecer el tamaño del búfer en el valor devuelto en `pcchName` y volver a llamar a `GetAppDomainInfo`.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorProfilerInfo (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [Interfaces para generación de perfiles](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [Generación de perfiles](../../../../docs/framework/unmanaged-api/profiling/index.md)
