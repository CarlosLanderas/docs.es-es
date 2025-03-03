---
title: Tecnologías de .NET Framework no disponibles en .NET Core
description: Más información sobre las tecnologías de .NET Framework no disponibles en .NET Core
author: cartermp
ms.date: 04/30/2019
ms.openlocfilehash: 47f93268c44682afeba87cde17fe9c39811b37bf
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2019
ms.locfileid: "73739716"
---
# <a name="net-framework-technologies-unavailable-on-net-core"></a>Tecnologías de .NET Framework no disponibles en .NET Core

Varias tecnologías disponibles para las bibliotecas de .NET Framework no están disponibles para su uso con .NET Core, por ejemplo, dominios de aplicaciones, comunicación remota, seguridad de acceso del código (CAS), transparencia de seguridad y System.EnterpriseServices. Si las bibliotecas se basan en una o varias de estas tecnologías, considere los enfoques alternativos que se describen a continuación. Para obtener más información sobre la compatibilidad de API, consulte el artículo [Cambios importantes en .NET Core](../compatibility/breaking-changes.md).

El hecho de que una API o tecnología no estén implementadas actualmente no implica que sea incompatible deliberadamente. Primero debe buscar en los repositorios de GitHub para .NET Core para ver si un problema determinado que tiene se debe al diseño, pero si no se encuentra este indicador, registre un problema en el [repositorio de problemas dotnet/corefx](https://github.com/dotnet/corefx/issues) en GitHub para solicitar tecnologías y API específicas. [Las solicitudes de portabilidad de los problemas](https://github.com/dotnet/corefx/labels/port-to-core) se marcan con la etiqueta `port-to-core`.

## <a name="appdomains"></a>Dominios de aplicaciones

Los dominios de aplicación aíslan las aplicaciones entre sí. Los dominios de aplicación requieren la compatibilidad con el runtime y suelen ser muy caros. No se admite la creación de dominios de aplicación adicionales. No se pretende agregar esta compatibilidad en el futuro. En el caso del aislamiento del código, se recomiendan procesos independientes o usar contenedores como alternativa. Para la carga dinámica de ensamblados, se recomienda la nueva clase <xref:System.Runtime.Loader.AssemblyLoadContext>.

Para facilitar la migración de código de .NET Framework, .NET Core expone algunas de las superficies de la API <xref:System.AppDomain>. Algunas de las API funcionan con normalidad (por ejemplo, <xref:System.AppDomain.UnhandledException?displayProperty=nameWithType>), algunos miembros no hacen nada (por ejemplo, <xref:System.AppDomain.SetCachePath%2A>) y algunos de ellos generan <xref:System.PlatformNotSupportedException> (por ejemplo, <xref:System.AppDomain.CreateDomain%2A>). Compruebe los tipos que usa en la [fuente de referencias de `System.AppDomain`](https://github.com/dotnet/corefx/blob/master/src/Common/src/CoreLib/System/AppDomain.cs) en el [repositorio dotnet/corefx de GitHub](https://github.com/dotnet/corefx), y asegúrese de que selecciona la rama correspondiente a la versión implementada.

## <a name="remoting"></a>Comunicación remota

La comunicación remota de .NET se identificó como una arquitectura problemática. Se usa para la comunicación entre dominios de aplicaciones, una funcionalidad que ya no es compatible. Además, la comunicación remota requiere la compatibilidad con el runtime, cuyo mantenimiento resulta caro. Por estos motivos, la comunicación remota de .NET no es compatible con .NET Core y no se prevé agregar esta compatibilidad en el futuro.

Para la comunicación entre procesos, considere la posibilidad de usar mecanismos de comunicación entre procesos (IPC) como alternativa a la comunicación remota, como las clases <xref:System.IO.Pipes> o <xref:System.IO.MemoryMappedFiles.MemoryMappedFile>.

En los equipos, utilice una solución basada en red como una alternativa. Si es posible, use un protocolo de texto sin formato con poca sobrecarga, como HTTP. El [servidor web Kestrel](https://docs.microsoft.com/aspnet/core/fundamentals/servers/kestrel), el servidor web que usa ASP.NET Core, se puede usar como opción aquí. También considere el uso de <xref:System.Net.Sockets> para escenarios de conexión entre equipos basada en red. Para obtener más opciones, vea [.NET Open Source Developer Projects: Messaging](https://github.com/Microsoft/dotnet/blob/master/dotnet-developer-projects.md#messaging) (Proyectos de desarrolladores de código abierto de .NET: mensajería).

## <a name="code-access-security-cas"></a>Seguridad de acceso del código (CAS)

El espacio aislado, que se basa en el runtime o en el marco para restringir qué recursos usa o ejecuta una aplicación administrada, [no es compatible con .NET Framework](../../framework/misc/code-access-security.md) y, por tanto, tampoco se admite en .NET Core. Hay demasiados casos en .NET Framework y en el runtime en los que se produce una elevación de privilegios para continuar tratando la seguridad de acceso al código (CAS) como un límite de seguridad. Además, la seguridad de acceso del código dificulta más la implementación y suele tener implicaciones en el rendimiento de corrección para las aplicaciones que no pretenden usar esta funcionalidad.

Use los límites de seguridad que proporciona el sistema operativo, como la virtualización, los contenedores o las cuentas de usuario para ejecutar procesos con el menor conjunto de privilegios.

## <a name="security-transparency"></a>Transparencia de seguridad

De forma similar a lo que ocurre con la seguridad de acceso al código, la transparencia de seguridad separa el código de espacios aislados del código crítico de seguridad de manera declarativa, pero [ya no se admite como un límite de seguridad](../../framework/misc/security-transparent-code.md). Silverlight usa mucho esta característica. 

Use los límites de seguridad que proporciona el sistema operativo, como visualización, contenedores o cuentas de usuario para ejecutar procesos con el menor conjunto de privilegios.

## <a name="systementerpriseservices"></a>System.EnterpriseServices

System.EnterpriseServices (COM+) no es compatible con .NET Core.

>[!div class="step-by-step"]
>[Siguiente](third-party-deps.md)
