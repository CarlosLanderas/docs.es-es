---
title: MDA de invalidOverlappedToPinvoke
ms.date: 03/30/2017
helpviewer_keywords:
- overlapped pointers
- managed debugging assistants (MDAs), overlapped pointers
- invalid overlapped pointer to platform invoke
- InvalidOverlappedToPinvoke MDA
- MDAs (managed debugging assistants), overlapped pointers
- pointers, overlapped
ms.assetid: 28876047-58bd-4fed-9452-c7da346d67c0
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7e9c7e1038591e5e8ea6f62b37ff4d02b2b6a9c5
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/17/2019
ms.locfileid: "71052557"
---
# <a name="invalidoverlappedtopinvoke-mda"></a>MDA de invalidOverlappedToPinvoke
El asistente para la depuración administrada (MDA) `invalidOverlappedToPinvoke` se activa cuando un puntero superpuesto que no se ha creado en el montón de recolección de elementos no utilizados se pasa a funciones de Win32 específicas.  
  
> [!NOTE]
> De forma predeterminada, este MDA solo se activa si se define la llamada de invocación de plataforma en el código y el depurador informa del estado de JustMyCode de cada método. Un depurador que no entienda JustMyCode (como MDbg.exe sin extensiones) no activará este MDA, Este MDA se puede habilitar en este tipo de depuradores utilizando un archivo de configuración y estableciendo explícitamente `justMyCode="false"` en el archivo .mda.config (`(<invalidOverlappedToPinvoke enable="true" justMyCode="false"/>`).  
  
## <a name="symptoms"></a>Síntomas  
 Bloqueos o daños inexplicables del montón.  
  
## <a name="cause"></a>Causa  
 Se pasa un puntero superpuesto que no se ha creado en el montón de recolección de elementos no utilizados a funciones de sistema operativo concretas.  
  
 En la tabla siguiente se muestran las funciones de las que realiza el seguimiento este MDA.  
  
|Module|Función|  
|------------|--------------|  
|HttpApi.dll|`HttpReceiveHttpRequest`|  
|IpHlpApi.dll|`NotifyAddrChange`|  
|kernel32.dll|`ReadFile`|  
|kernel32.dll|`ReadFileEx`|  
|kernel32.dll|`WriteFile`|  
|kernel32.dll|`WriteFileEx`|  
|kernel32.dll|`ReadDirectoryChangesW`|  
|kernel32.dll|`PostQueuedCompletionStatus`|  
|MSWSock.dll|`ConnectEx`|  
|WS2_32.dll|`WSASend`|  
|WS2_32.dll|`WSASendTo`|  
|WS2_32.dll|`WSARecv`|  
|WS2_32.dll|`WSARecvFrom`|  
|MQRT.dll|`MQReceiveMessage`|  
  
 La probabilidad de daños en el montón es alta para esta condición porque se podría descargar el <xref:System.AppDomain> que hace la llamada. Si se descarga el <xref:System.AppDomain>, el código de la aplicación liberará la memoria del puntero superpuesto, provocando daños cuando termine la operación, o producirá la pérdida de memoria, lo que más adelante causará dificultades.  
  
## <a name="resolution"></a>Resolución  
 Use un objeto <xref:System.Threading.Overlapped>, llamando al método <xref:System.Threading.Overlapped.Pack%2A> para obtener una estructura <xref:System.Threading.NativeOverlapped> que se puede pasar a la función. Si se descarga el <xref:System.AppDomain>, CLR espera hasta que la operación asincrónica finalice antes de liberar el puntero.  
  
## <a name="effect-on-the-runtime"></a>Efecto en el Runtime  
 Este MDA no tiene ningún efecto en el CLR.  
  
## <a name="output"></a>Resultados  
 A continuación se muestra un ejemplo de resultado de este MDA.  
  
 `An overlapped pointer (0x00ea3430) that was not allocated on the GC heap was passed via Pinvoke to the Win32 function 'WriteFile' in module 'KERNEL32.DLL'. If the AppDomain is shut down, this can cause heap corruption when the async I/O completes. The best solution is to pass a NativeOverlapped structure retrieved from a call to System.Threading.Overlapped.Pack(). If the AppDomain exits, the CLR will keep this structure alive and pinned until the I/O completes.`  
  
## <a name="configuration"></a>Configuración  
  
```xml  
<mdaConfig>  
  <assistants>  
    <invalidOverlappedToPinvoke/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a>Vea también

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [Diagnosing Errors with Managed Debugging Assistants (Diagnóstico de errores con asistentes para la depuración administrada)](diagnosing-errors-with-managed-debugging-assistants.md)
- [Serialización de interoperabilidad](../interop/interop-marshaling.md)
