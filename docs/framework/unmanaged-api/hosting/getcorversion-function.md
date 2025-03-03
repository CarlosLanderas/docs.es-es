---
title: GetCORVersion (Función)
ms.date: 03/30/2017
api_name:
- GetCORVersion
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- GetCORVersion
helpviewer_keywords:
- GetCORVersion function [.NET Framework hosting]
ms.assetid: 2f09cd37-bf3a-4cc5-87b0-adc42a7eed31
topic_type:
- apiref
ms.openlocfilehash: 1283abaf6b08af1d842d8fe4469f7f6c15e38ec5
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136418"
---
# <a name="getcorversion-function"></a>GetCORVersion (Función)
Devuelve el número de versión del Common Language Runtime (CLR) que se ejecuta en el proceso actual.  
  
 Esta función está en desuso en el .NET Framework 4.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetCORVersion (  
    [in] LPWSTR  pbuffer,  
    [in]  DWORD   cchBuffer,   
    [out] DWORD*  dwlength  
);   
```  
  
## <a name="parameters"></a>Parámetros  
 `pbuffer`  
 Un puntero a un búfer en el que CLR devuelve una cadena que especifica la versión del Runtime que está cargada actualmente en el proceso. La cadena devuelta tiene el mismo formato que las cadenas que se pasan a [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md), por ejemplo, "v 1.0.1216". Si el tiempo de ejecución aún no se ha cargado en el proceso, la función devuelve la información de directorio adecuada para la versión más reciente del motor en tiempo de ejecución instalada en el equipo.  
  
 `cchBuffer`  
 Número de caracteres (`WCHAR`s) que se pueden mantener en `pbuffer`.  
  
 `dwLength`  
 Puntero al número de caracteres devueltos realmente en `pbuffer`. Si `pbuffer` es un puntero nulo, el tiempo de ejecución devuelve E_POINTER. Si el número de caracteres es mayor que la longitud de `pbuffer`, el tiempo de ejecución devuelve ERROR_INSUFFICIENT_BUFFER.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** MSCorEE. dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Funciones de hospedaje de CLR en desuso](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
