---
title: Habilitar dinámicamente la traza analítica
ms.date: 03/30/2017
ms.assetid: 58b63cfc-307a-427d-b69d-9917ff9f44ac
ms.openlocfilehash: bea64ac9a9312d17b7f47e72a46d876552e20a12
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798100"
---
# <a name="dynamically-enabling-analytic-tracing"></a>Habilitar dinámicamente la traza analítica
Con las herramientas que se distribuyen con el sistema operativo Windows, puede habilitar o deshabilitar la traza de forma dinámica mediante el Seguimiento de eventos para Windows (ETW). En todos [!INCLUDE[netfx_current_long](../../../../../includes/netfx-current-long-md.md)] los servicios de Windows Communication Foundation (WCF), el seguimiento analítico se puede habilitar y deshabilitar de forma dinámica sin modificar el archivo Web. config de la aplicación ni reiniciar el servicio. Esto permite que la aplicación que emite los eventos de traza siga sin más.  
  
 Las opciones de seguimiento de WCF se pueden configurar de forma similar. Por ejemplo, puede cambiar el nivel de gravedad de **Error** a **Información** sin interrumpir a la aplicación. Esto se puede hacer mediante las siguientes herramientas:  
  
- **Logman** . Una herramienta de línea de comandos para configurar, controlar y consultar los datos de la traza. Para obtener más información, vea [Logman Create Trace](https://go.microsoft.com/fwlink/?LinkId=165426) y [Logman Update Trace](https://go.microsoft.com/fwlink/?LinkId=165427).  
  
- **EventViewer** . Herramienta de administración gráfica de Windows para ver los resultados de la traza. Para obtener más información, vea [servicios WCF y seguimiento de eventos para Windows](../../samples/wcf-services-and-event-tracing-for-windows.md) y [visor de eventos](https://go.microsoft.com/fwlink/?LinkId=165428).  
  
- **Perfmon** . Herramienta de administración gráfica de Windows que usa los contadores para supervisar los contadores de traza y los efectos de la traza durante el rendimiento. Para obtener más información, vea [crear un conjunto de recopiladores de datos manualmente](https://go.microsoft.com/fwlink/?LinkId=165429).  
  
### <a name="keywords"></a>Palabras clave  
 Al utilizar la clase <xref:System.ServiceModel.Activation.Configuration.ServiceModelActivationSectionGroup.Diagnostics%2A> , los mensajes de traza de .NET Framework se suelen filtrar según el nivel de gravedad (por ejemplo, Error, Advertencia e Información). ETW admite el concepto de nivel de gravedad, pero introduce un mecanismo de filtro nuevo y flexible mediante palabras clave. Las palabras clave son valores textuales arbitrarios que permiten a los eventos de traza proporcionar contexto adicional sobre lo que ese evento significa.  
  
 En el caso del seguimiento analítico de WCF, cada evento de seguimiento tiene dos tipos de palabras clave. Primero, cada evento tiene una o más palabras clave de escenario. Estas palabras clave indican los escenarios que este evento debería admitir. Hay tres palabras clave de escenario, cada una diseñada para un propósito concreto, tal y como se muestra en la siguiente tabla. El filtrado con palabras clave puede cambiarse dinámicamente sin alterar el servicio WCF. Eso significa que puede cambiar de forma dinámica el escenario de traza actual y la cantidad de información de traza recopilada. Por ejemplo, puede cambiar `HealthMonitoring` a `Troubleshooting` y aumentar la granularidad de los eventos de traza.  
  
|Palabra clave|DESCRIPCIÓN|  
|-------------|-----------------|  
|`HealthMonitoring`|Traza muy ligera y mínima que permite supervisar la actividad del servicio.|  
|`EndToEndMonitoring`|Eventos usados para admitir la traza de flujo de mensajes.|  
|`Troubleshooting`|Eventos más granulares alrededor de los puntos de extensibilidad de WCF.|  
  
 El segundo grupo de palabras clave define qué componente de la .NET Framework emitió el evento.  
  
|Palabra clave|DESCRIPCIÓN|  
|-------------|-----------------|  
|`UserEvents`|Eventos emitidos por el código de usuario y no por el .NET Framework.|  
|`ServiceModel`|Eventos emitidos por el tiempo de ejecución de WCF.|  
|`ServiceHost`|Eventos emitidos por el host de servicio.|  
|`WCFMessageLogging`|Eventos de registro de mensajes de WCF.|  
  
## <a name="see-also"></a>Vea también

- [Servicios WCF y Seguimiento de eventos para Windows](../../samples/wcf-services-and-event-tracing-for-windows.md)
