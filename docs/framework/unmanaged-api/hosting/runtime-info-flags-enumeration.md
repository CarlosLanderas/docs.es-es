---
title: RUNTIME_INFO_FLAGS (Enumeración)
ms.date: 03/30/2017
api_name:
- RUNTIME_INFO_FLAGS
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- RUNTIME_INFO_FLAGS
helpviewer_keywords:
- RUNTIME_INFO_FLAGS enumeration [.NET Framework hosting]
ms.assetid: adba37be-f775-4cdb-8919-5746ce694f33
topic_type:
- apiref
ms.openlocfilehash: 80643187045e7e96b9c18169c5e71287713d711f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73106235"
---
# <a name="runtime_info_flags-enumeration"></a>RUNTIME_INFO_FLAGS (Enumeración)
Contiene valores que indican qué información sobre el Common Language Runtime (CLR) se debe devolver.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
typedef enum {  
  
    RUNTIME_INFO_UPGRADE_VERSION             = 0x01,  
    RUNTIME_INFO_REQUEST_IA64                = 0x02,  
    RUNTIME_INFO_REQUEST_AMD64               = 0x04,  
    RUNTIME_INFO_REQUEST_X86                 = 0x08,  
    RUNTIME_INFO_DONT_RETURN_DIRECTORY       = 0x10,  
    RUNTIME_INFO_DONT_RETURN_VERSION         = 0x20,  
    RUNTIME_INFO_DONT_SHOW_ERROR_DIALOG      = 0x40,  
    RUNTIME_INFO_IGNORE_ERROR_MODE           = 0x1000  
  
} RUNTIME_INFO_FLAGS;  
```  
  
## <a name="members"></a>Miembros  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`RUNTIME_INFO_DONT_RETURN_DIRECTORY`|Indica que no se debe incluir la información de directorio.|  
|`RUNTIME_INFO_DONT_RETURN_VERSION`|Indica que no se debe incluir la información de versión.|  
|`RUNTIME_INFO_DONT_SHOW_ERROR_DIALOG`|Indica que no se debe mostrar un cuadro de diálogo de error en caso de error.|  
|`RUNTIME_INFO_IGNORE_ERROR_MODE`|Indica que se deben invalidar los efectos de llamar a la función [SetErrorMode](https://go.microsoft.com/fwlink/p/?LinkId=255242) con la marca SEM_FAILCRITICALERRORS. Es decir, se debe mostrar un cuadro de diálogo de instalación cuando se produzca un error, en lugar de suprimirse.|  
|`RUNTIME_INFO_REQUEST_AMD64`|Indica una solicitud de información sobre una versión compatible con AMD-64 del motor en tiempo de ejecución.|  
|`RUNTIME_INFO_REQUEST_IA64`|Indica una solicitud de información sobre una versión compatible con IA-64 del Runtime.|  
|`RUNTIME_INFO_REQUEST_X86`|Indica una solicitud de información sobre una versión compatible con x86 del Runtime.|  
|`RUNTIME_INFO_UPGRADE_VERSION`|Indica que se debe incluir la información de actualización de la versión.|  
  
## <a name="remarks"></a>Comentarios  
 Las marcas de arquitectura de plataforma siguientes solo se pueden especificar de una en una y no se pueden combinar:  
  
- RUNTIME_INFO_REQUEST_IA64  
  
- RUNTIME_INFO_REQUEST_AMD64  
  
- RUNTIME_INFO_REQUEST_X86  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** MSCorEE. dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Enumeraciones para hosts](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
