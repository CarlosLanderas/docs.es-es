---
ms.openlocfilehash: f103c96588bae167216d09a82973a4a7abfb5cc3
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2019
ms.locfileid: "72394080"
---
### <a name="data-protection-dataprotectionazurestorage-uses-new-azure-storage-apis"></a>Protección de datos: DataProtection.AzureStorage usa API nuevas de Azure Storage

<xref:Microsoft.AspNetCore.DataProtection.AzureStorage?displayProperty=fullName> depende de las [bibliotecas de Azure Storage](https://github.com/Azure/azure-storage-net). Estas bibliotecas han cambiado el nombre de los ensamblados, paquetes y espacios de nombres. A partir de ASP.NET Core 3.0, `Microsoft.AspNetCore.DataProtection.AzureStorage` utiliza las nuevas API y paquetes con prefijo `Microsoft.Azure.Storage.`.

Si tiene preguntas sobre las API de Azure Storage, utilice <https://github.com/Azure/azure-storage-net>. Para obtener información sobre esta incidencia, consulte [aspnet/AspNetCore#8472](https://github.com/aspnet/AspNetCore/issues/8472).

#### <a name="version-introduced"></a>Versión introducida

3.0

#### <a name="old-behavior"></a>Comportamiento anterior

El paquete hacía referencia al paquete NuGet `WindowsAzure.Storage`.

#### <a name="new-behavior"></a>Comportamiento nuevo

El paquete hace referencia al paquete NuGet `Microsoft.Azure.Storage.Blob`.

#### <a name="reason-for-change"></a>Motivo del cambio

Este cambio permite a `Microsoft.AspNetCore.DataProtection.AzureStorage` migrar a los paquetes de Azure Storage recomendados.

#### <a name="recommended-action"></a>Acción recomendada

Si todavía necesita usar las API de Azure Storage anteriores con ASP.NET Core 3.0, agregue una dependencia directa al paquete [WindowsAzure.Storage](https://www.nuget.org/packages/WindowsAzure.Storage/). Este paquete se puede instalar junto con las nuevas API de `Microsoft.Azure.Storage`.

En muchos casos, la actualización solo implica cambiar las instrucciones `using` para usar los espacios de nombres nuevos:

```diff
- using Microsoft.WindowsAzure.Storage;
- using Microsoft.WindowsAzure.Storage.Blob;
+ using Microsoft.Azure.Storage;
+ using Microsoft.Azure.Storage.Blob;
```

#### <a name="category"></a>Categoría

ASP.NET Core

#### <a name="affected-apis"></a>API afectadas

None

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
