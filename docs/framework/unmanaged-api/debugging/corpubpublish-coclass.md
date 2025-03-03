---
title: CorpubPublish (coclase)
ms.date: 03/30/2017
api_name:
- CorpubPublish Coclass
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorpubPublish
helpviewer_keywords:
- CorpubPublish coclass [.NET Framework debugging]
ms.assetid: 191015da-f54a-4bac-a28a-1de7ab3c3428
topic_type:
- apiref
ms.openlocfilehash: 89af99fab1f1265701e0dbfe74a46000cb3bfaa6
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132152"
---
# <a name="corpubpublish-coclass"></a>CorpubPublish (coclase)
Proporciona interfaces para publicar información acerca de procesos y dominios de aplicación.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
coclass CorpubPublish {  
    [default] interface ICorPublish;  
    interface           ICorPublishProcess;  
    interface           ICorPublishAppDomain;  
    interface           ICorPublishProcessEnum;  
    interface           ICorPublishAppDomainEnum;  
};  
```  
  
## <a name="interfaces"></a>Interfaces  
  
|Interfaz|Descripción|  
|---------------|-----------------|  
|[ICorPublish (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icorpublish-interface.md)|Proporciona métodos para publicar información sobre los procesos y los dominios de aplicación en esos procesos.|  
|[ICorPublishAppDomain (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md)|Representa y proporciona información sobre un dominio de aplicación en un proceso.|  
|[ICorPublishAppDomainEnum (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-interface.md)|Proporciona métodos que atraviesan una colección de dominios de aplicación que existen actualmente dentro de un proceso.|  
|[ICorPublishProcess (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md)|Representa un proceso que se está ejecutando en un equipo.|  
|[ICorPublishProcessEnum (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-interface.md)|Proporciona métodos que atraviesan una colección de procesos que se ejecutan en un equipo.|  
  
## <a name="remarks"></a>Comentarios  
 Un escenario de publicación típico implica a un desarrollador que desea depurar el código administrado que se ejecuta en un equipo dentro de un dominio de aplicación. Es posible que el entorno de hospedaje ejecute más de un dominio de aplicación dentro de un proceso. El desarrollador desea usar una interfaz gráfica de usuario u otros medios para enumerar todos los procesos que se ejecutan en el equipo y elegir un proceso específico. La lista debe incluir todos los dominios de aplicación dentro de los procesos que ejecutan código administrado. A continuación, el desarrollador puede identificar el dominio de aplicación específico y asociar un depurador a ese dominio.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorPub. idl  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Depuración](../../../../docs/framework/unmanaged-api/debugging/index.md)
