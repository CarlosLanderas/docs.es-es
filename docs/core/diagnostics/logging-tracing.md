---
title: 'Registro y seguimiento: .NET Core'
description: Introducción al registro y seguimiento de .NET Core.
author: sdmaclea
ms.author: stmaclea
ms.date: 08/05/2019
ms.openlocfilehash: 46e64a7f60b88c26ceef9ac817be885bfa180c8e
ms.sourcegitcommit: 33c8d6f7342a4bb2c577842b7f075b0e20a2fa40
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/12/2019
ms.locfileid: "72303657"
---
# <a name="net-core-logging-and-tracing"></a>Registro y seguimiento de .NET Core

El registro y el seguimiento son en realidad dos nombres para la misma técnica. Esta sencilla técnica se ha usado desde el inicio de la era de la informática. Simplemente implica instrumentar una aplicación para escribir la salida que se va a consumir más adelante.

## <a name="reasons-to-use-logging-and-tracing"></a>Motivos para usar el registro y seguimiento

Esta técnica sencilla es sorprendentemente eficaz. Se puede usar en situaciones en las que se produzca un error en un depurador:

- Las incidencias que se producen durante largos períodos de tiempo pueden ser difíciles de depurar con un depurador tradicional. Los registros permiten una revisión detallada de evaluación que abarca períodos largos de tiempo. En cambio, los depuradores están restringidos a análisis en tiempo real.
- Las aplicaciones multiproceso y las aplicaciones distribuidas a menudo son difíciles de depurar.  Adjuntar un depurador tiende a modificar los comportamientos. Los registros detallados se pueden analizar, según sea necesario, para comprender sistemas complejos.
- Las incidencias en las aplicaciones distribuidas pueden surgir de una interacción compleja entre muchos componentes y puede que no sea razonable conectar un depurador en todas las partes del sistema.
- Muchos servicios no deben estar detenidos. Al adjuntar un depurador a menudo se producen errores de tiempo de expiración.
- Las incidencias no siempre están previstas. El registro y seguimiento están diseñados para una baja sobrecarga, de modo que los programas siempre pueden grabarse en caso de que se produzca una incidencia.

## <a name="net-core-apis"></a>API de .NET Core

### <a name="print-style-apis"></a>API de estilo de impresión

Cada una de las clases <xref:System.Console?displayProperty=nameWithType>, <xref:System.Diagnostics.Trace?displayProperty=nameWithType> y <xref:System.Diagnostics.Debug?displayProperty=nameWithType> proporcionan API de estilo de impresión parecidas para el registro.

La elección de la API de estilo de impresión que se va a usar depende de usted. Las principales diferencias son:

- <xref:System.Console?displayProperty=nameWithType>
  - Siempre está habilitada y siempre escribe en la consola.
  - Resulta útil para la información que es posible que el cliente necesite ver en la versión.
  - Dado que es el enfoque más sencillo, a menudo se usa para la depuración temporal ad hoc. Este código de depuración a veces no se registra nunca en el control de código fuente.
- <xref:System.Diagnostics.Trace?displayProperty=nameWithType>
  - Solo se habilita cuando se define `TRACE`.
  - Escribe en el elemento <xref:System.Diagnostics.Trace.Listeners> adjuntado, de forma predeterminada, <xref:System.Diagnostics.DefaultTraceListener>.
  - Use esta API cuando cree registros que se vayan a habilitar en la mayoría de compilaciones.
- <xref:System.Diagnostics.Debug?displayProperty=nameWithType>
  - Solo se habilita cuando se define `DEBUG`.
  - Escribe en un depurador adjuntado.
  - En `*nix`, escribe en stderr si se establece `COMPlus_DebugWriteToStdErr`.
  - Use esta API cuando cree registros que se vayan a habilitar solo en las compilaciones de depuración.

### <a name="logging-events"></a>Eventos de registro

Las siguientes API están más orientadas a eventos. En lugar de registrar cadenas sencillas, registran objetos de evento.

- <xref:System.Diagnostics.Tracing.EventSource?displayProperty=nameWithType>
  - EventSource es la API de seguimiento de .NET Core de raíz principal.
  - Disponible en todas las versiones .NET Standard.
  - Solo permite el seguimiento de objetos serializables.
  - Escribe en los [clientes de escucha de evento](xref:System.Diagnostics.Tracing.EventListener) adjuntados.
  - .NET Core proporciona clientes de escucha para:
    - EventPipe de .NET Core en todas las plataformas
    - [Seguimiento de eventos para Windows (ETW)](/windows/win32/etw/event-tracing-portal)
    - [Marco de seguimiento de LTTng para Linux](https://lttng.org/)

- <xref:System.Diagnostics.DiagnosticSource?displayProperty=nameWithType>
  - Se incluye en .NET Core y como un [paquete NuGet](https://www.nuget.org/packages/System.Diagnostics.DiagnosticSource) para .NET Framework.
  - Permite el seguimiento en curso de objetos no serializables.
  - Incluye un puente para permitir que los campos seleccionados de objetos registrados se escriban en un elemento <xref:System.Diagnostics.Tracing.EventSource>.

- <xref:System.Diagnostics.Activity?displayProperty=nameWithType>
  - Proporciona una manera definitiva de identificar los mensajes de registro resultantes de una actividad o transacción específica. Este objeto se puede utilizar para correlacionar los registros entre distintos servicios.

- <xref:System.Diagnostics.EventLog?displayProperty=nameWithType>
  - Solo Windows.
  - Escribe mensajes en el registro de eventos de Windows.
  - Los administradores del sistema esperan que aparezcan mensajes de error grave de aplicación en el registro de eventos de Windows.

## <a name="ilogger-and-logging-frameworks"></a>Plataformas de registro y de ILogger

Es posible que las API de bajo nivel no sean la opción adecuada para sus necesidades de registro. Puede que quiera considerar la posibilidad de usar una plataforma de registro.

La interfaz de <xref:Microsoft.Extensions.Logging.ILogger> se ha utilizado para crear una interfaz de registro común en la que se pueden insertar los registradores mediante la inserción de dependencias.

Por ejemplo, para que pueda elegir la mejor opción para la aplicación, `ASP.NET` ofrece compatibilidad con una selección de marcos integrados y de terceros:

- [Proveedores de registro integrados de ASP.NET](/aspnet/core/fundamentals/logging/#built-in-logging-providers)
- [Proveedores de registro de terceros de ASP.NET](/aspnet/core/fundamentals/logging/#third-party-logging-providers)

## <a name="logging-related-references"></a>Referencias relacionadas de registro

- [Cómo: Compilación condicional con Trace y Debug](../../framework/debug-trace-profile/how-to-compile-conditionally-with-trace-and-debug.md)

- [Cómo: agregar instrucciones de seguimiento al código de aplicación](../../framework/debug-trace-profile/how-to-add-trace-statements-to-application-code.md)

- [El registro de ASP.NET](/aspnet/core/fundamentals/logging) proporciona información general sobre las técnicas de registro que admite.

- [La interpolación de cadenas de C#](../../csharp/language-reference/tokens/interpolated.md) puede simplificar la escritura de código de registro.

- La propiedad <xref:System.Exception.Message?displayProperty=nameWithType> es útil para las excepciones de registro.

- La clase <xref:System.Diagnostics.StackTrace?displayProperty=nameWithType> puede ser útil para proporcionar información de pila en los registros.

## <a name="performance-considerations"></a>Consideraciones sobre el rendimiento

El formato de cadena puede tomar un tiempo de procesamiento de la CPU considerable.

En las aplicaciones críticas de rendimiento, se recomienda lo siguiente:

- Evitar muchos registros cuando no haya nadie escuchando. Evitar la construcción de mensajes de registro costosos comprobando en primer lugar si el registro está habilitado.
- Registrar únicamente lo que sea útil.
- Aplazar el formato sofisticado a la fase de análisis.
