---
title: Seguimiento circular
ms.date: 03/30/2017
ms.assetid: 5ff139f9-8806-47bc-8f33-47fe6c436b92
ms.openlocfilehash: b0778a25c75ae48c2215625f40b08a1e3815ba81
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/03/2019
ms.locfileid: "74716004"
---
# <a name="circular-tracing"></a>Seguimiento circular

Este ejemplo muestra la implementación de un agente de escucha de seguimiento del búfer circular. Un escenario común para los servicios de producción es tener servicios que están disponibles para largos periodos de tiempo y para tener habilitado el registro de seguimiento en un nivel bajo. Estos servicios utilizan mucho espacio en disco. Al solucionar problemas de un servicio, serán relevantes los datos más recientes que haya en el registro de seguimiento para resolver un problema. Este ejemplo muestra una implementación de un agente de escucha de seguimiento del búfer circular en el que solo los seguimientos más recientes se guardan en el disco hasta llegar a una cantidad de datos configurable. Este ejemplo se basa en el [Introducción](../../../../docs/framework/wcf/samples/getting-started-sample.md) e incluye un agente de escucha de seguimiento personalizado.

> [!NOTE]
> El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.

En este ejemplo se da por supuesto que está familiarizado con el ejemplo de [registro de mensajes](../../../../docs/framework/wcf/samples/tracing-and-message-logging.md) y de seguimiento y que ha leído la documentación proporcionada para el ejemplo de [registro de mensajes y seguimiento](../../../../docs/framework/wcf/samples/tracing-and-message-logging.md) .

## <a name="circular-buffer-trace-listener"></a>Agente de escucha de seguimiento de búfer circular

El concepto que se encuentra detrás de la implementación del Agente de escucha de seguimiento del búfer circular es tener dos archivos que pueden almacenar hasta la mitad de los datos de registro de seguimiento deseados. El agente de escucha crea un archivo y escribe en ese archivo hasta que llega al límite de la mitad del tamaño de datos, momento en el cual cambia a un segundo archivo. Cuando el agente de escucha alcanza el límite para el segundo archivo, sobrescribe el primer archivo con nuevos seguimientos.

Este agente de escucha se deriva del `XmlWriteTraceListener` y permite ver los registros con la herramienta de [visor de seguimiento de servicio (SvcTraceViewer. exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md). Al intentar ver los registros, los dos archivos de registro se pueden recombinar con facilidad abriendo al mismo tiempo ambos archivos de registro en la herramienta Visor de seguimiento de servicio. La herramienta Visor de seguimiento de servicio trata automáticamente de ordenar los seguimientos de manera que aparezcan en el orden correcto.

## <a name="configuration"></a>Configuración de

Se puede configurar un servicio para usar el Agente de escucha de seguimiento del búfer circular agregando el código siguiente para unos elementos de agente de escucha y origen. El tamaño máximo de archivo se especifica estableciendo el atributo `maxFileSizeKB` en la configuración del agente de escucha de seguimiento circular. Esto último se muestra en el código siguiente.

```xml
<system.diagnostics>
  <sources>
    <source name="System.ServiceModel" switchValue="Information,ActivityTracing" propagateActivity="true">
      <listeners>
        <add name="CircularTraceListener" />
      </listeners>
    </source>
  </sources>
  <sharedListeners>
    <add name="CircularTraceListener" type="Microsoft. Samples.ServiceModel.CircularTraceListener,CircularTraceListener"
         initializeData="c:\logs\CircularTracing-service.svclog" maxFileSizeKB="100" />
  </sharedListeners>
  <trace autoflush="true" />
</system.diagnostics>
```

#### <a name="to-set-up-build-and-run-the-sample"></a>Configurar, compilar y ejecutar el ejemplo

1. Asegúrese de que ha realizado el [procedimiento de instalación única para los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).

2. Para compilar el código C# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).

3. Para ejecutar el ejemplo en una configuración de equipos única o cruzada, siga las instrucciones de [ejecución de los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).

> [!IMPORTANT]
> Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los ejemplos de Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)]. Este ejemplo se encuentra en el siguiente directorio.
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\CircularTracing`

## <a name="see-also"></a>Vea también

- [Ejemplos de supervisión de AppFabric](https://go.microsoft.com/fwlink/?LinkId=193959)
