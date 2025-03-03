---
title: ICorDebug::SetUnmanagedHandler (Método)
ms.date: 03/30/2017
api_name:
- ICorDebug.SetUnmanagedHandler
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebug::SetUnmanagerHandler
helpviewer_keywords:
- SetUnmanagedHandler method [.NET Framework debugging]
- ICorDebug::SetUnmanagedHandler method [.NET Framework debugging]
ms.assetid: 6b546be4-f86d-4536-8cfc-1d08e5066eb6
topic_type:
- apiref
ms.openlocfilehash: 36d314211d95dff6648753f5d550a2cfd402a918
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134046"
---
# <a name="icordebugsetunmanagedhandler-method"></a>ICorDebug::SetUnmanagedHandler (Método)
Especifica el objeto de controlador de eventos para los eventos no administrados.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT SetUnmanagedHandler (  
    [in] ICorDebugUnmanagedCallback  *pCallback  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `pCallback`  
 de Un puntero a un objeto [ICorDebugUnmanagedCallback (](../../../../docs/framework/unmanaged-api/debugging/icordebugunmanagedcallback-interface.md) que representa el controlador de eventos para los eventos no administrados.  
  
## <a name="remarks"></a>Comentarios  
 El objeto de controlador de eventos para eventos no administrados debe establecerse después de una llamada a [ICorDebug:: Initialize](../../../../docs/framework/unmanaged-api/debugging/icordebug-initialize-method.md) y antes de cualquier llamada a [ICorDebug:: CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebug-createprocess-method.md) o [ICorDebug::D ebugactiveprocess](../../../../docs/framework/unmanaged-api/debugging/icordebug-debugactiveprocess-method.md). Sin embargo, para los fines heredados, no es necesario establecer el objeto de controlador de eventos para los eventos no administrados hasta que se genere el primer evento de depuración nativo. En concreto, si `ICorDebug::CreateProcess` ha establecido la marca CREATE_SUSPENDED, los eventos de depuración nativos no se pueden enviar hasta que se reanude el subproceso principal.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorDebug (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
