---
title: ICorDebugAppDomain3 (Interfaz)
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain3
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain3
helpviewer_keywords:
- ICorDebugAppDomain3 interface [.NET Framework debugging]
ms.assetid: 875ef5be-c1e7-4d95-97e9-d3a667aeaba0
topic_type:
- apiref
ms.openlocfilehash: 0b238a953fa5cd57c8b7af9a0643bfc36ee1032e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73088860"
---
# <a name="icordebugappdomain3-interface"></a>ICorDebugAppDomain3 (Interfaz)
Proporciona métodos para recuperar información sobre las representaciones administradas de Windows Runtime tipos cargados actualmente en un dominio de aplicación. Esta interfaz es una extensión de las interfaces ICorDebugAppDomain e ICorDebugAppDomain2.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[ICorDebugAppDomain3:: Getcachedwinrttypes (](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-getcachedwinrttypes-method.md)|Obtiene un enumerador para todos los tipos de Windows Runtime almacenados en caché.|  
|[ICorDebugAppDomain3:: Getcachedwinrttypesforiids (](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-getcachedwinrttypesforiids-method.md)|Obtiene un enumerador para los tipos de Windows Runtime almacenados en memoria caché en un dominio de aplicación en función de sus identificadores de interfaz.|  
  
## <a name="remarks"></a>Comentarios  
 Esta interfaz está pensada para que la use un depurador junto con una llamada de evaluación de función para `M:System.Runtime.InteropServices.Marshal.GetInspectableIIDs(System.Object)`. Cuando el método recupera los identificadores de interfaz admitidos por un objeto de servidor Windows Runtime, el depurador puede usar los métodos definidos en esta interfaz para asignarlos a tipos administrados que corresponden a esas interfaces.  
  
 Para recuperar una instancia de esta interfaz, ejecute `QueryInterface` en una instancia de la interfaz ICorDebugAppDomain o ICorDebugAppDomain2.  
  
> [!NOTE]
> Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Windows Runtime  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaces de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
