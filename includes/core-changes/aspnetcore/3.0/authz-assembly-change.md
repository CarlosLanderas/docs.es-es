---
ms.openlocfilehash: b91cdc7a0d2e4258662155a840500ce21ab35760
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/14/2019
ms.locfileid: "74101472"
---
### <a name="authorization-addauthorization-overload-moved-to-different-assembly"></a>Autorización: la sobrecarga de AddAuthorization se ha cambiado a otro ensamblado

Se ha cambiado a `AddAuthorizationCore` el nombre de los métodos `AddAuthorization` principales que antes se encontraban en `Microsoft.AspNetCore.Authorization`. Los métodos `AddAuthorization` antiguos todavía existen, pero ahora se encuentran en el ensamblado `Microsoft.AspNetCore.Authorization.Policy`. Las aplicaciones en las que se usen ambos métodos no se verán afectadas. Tenga en cuenta que `Microsoft.AspNetCore.Authorization.Policy` ahora se incluye en el marco compartido en lugar de en un paquete independiente, tal como se describe en [Marco compartido: se han quitado los ensamblados de Microsoft.AspNetCore.App](#shared-framework-assemblies-removed-from-microsoftaspnetcoreapp).

#### <a name="version-introduced"></a>Versión introducida

3.0

#### <a name="old-behavior"></a>Comportamiento anterior
Los métodos `AddAuthorization` existían en `Microsoft.AspNetCore.Authorization`.

#### <a name="new-behavior"></a>Comportamiento nuevo

Los métodos `AddAuthorization` existen en `Microsoft.AspNetCore.Authorization.Policy`. `AddAuthorizationCore` es el nuevo nombre de los métodos antiguos.

#### <a name="reason-for-change"></a>Motivo del cambio

`AddAuthorization` es un nombre de método más indicado para agregar todos los servicios comunes necesarios para la autorización.

#### <a name="recommended-action"></a>Acción recomendada

Agregue una referencia a `Microsoft.AspNetCore.Authorization.Policy` o, en su lugar, use `AddAuthorizationCore`.

#### <a name="category"></a>Category

ASP.NET Core

#### <a name="affected-apis"></a>API afectadas

<xref:Microsoft.Extensions.DependencyInjection.AuthorizationServiceCollectionExtensions.AddAuthorization(Microsoft.Extensions.DependencyInjection.IServiceCollection,System.Action{Microsoft.AspNetCore.Authorization.AuthorizationOptions})?displayProperty=fullName>

<!--

#### Affected APIs

`M:Microsoft.Extensions.DependencyInjection.AuthorizationServiceCollectionExtensions.AddAuthorization(Microsoft.Extensions.DependencyInjection.IServiceCollection,System.Action{Microsoft.AspNetCore.Authorization.AuthorizationOptions})`

-->
