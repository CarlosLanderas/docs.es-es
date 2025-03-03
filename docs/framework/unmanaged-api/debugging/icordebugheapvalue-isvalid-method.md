---
title: ICorDebugHeapValue::IsValid (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugHeapValue.IsValid
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHeapValue::IsValid
helpviewer_keywords:
- IsValid method [.NET Framework debugging]
- ICorDebugHeapValue::IsValid method [.NET Framework debugging]
ms.assetid: 68e20e62-203d-46d8-bb91-8d3c61cfacc3
topic_type:
- apiref
ms.openlocfilehash: 7edf0065fa7eb39dada167a682f2b634a438f1f3
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138395"
---
# <a name="icordebugheapvalueisvalid-method"></a>ICorDebugHeapValue::IsValid (Método)
Obtiene un valor que indica si el objeto representado por este ICorDebugHeapValue es válido.  
  
 Este método está en desuso en la versión .NET Framework 2,0.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT IsValid (  
    [out] BOOL    *pbValid  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `pbValid`  
 enuncia Un puntero a un valor booleano que indica si este valor en el montón es válido.  
  
## <a name="remarks"></a>Comentarios  
 El valor no es válido si lo ha reclamado el recolector de elementos no utilizados.  
  
 Este método está en desuso. En el .NET Framework 2,0, todos los valores son válidos hasta que se llama a [ICorDebugController:: Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) , momento en el que se invalidan los valores.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
