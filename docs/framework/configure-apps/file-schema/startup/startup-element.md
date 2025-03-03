---
title: Elemento <startup>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/startup
- http://schemas.microsoft.com/.NetConfiguration/v2.0#startup
helpviewer_keywords:
- container tags, <startup> element
- <startup> element
- startup element
ms.assetid: 536acfd8-f827-452f-838a-e14fa3b87621
ms.openlocfilehash: 634d9c5248c33619abec50d441d95c111febdcbf
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2019
ms.locfileid: "71699414"
---
# <a name="startup-element"></a>\<elemento > de inicio

Especifica Common Language Runtime información de inicio.

[ **\<configuration>** ](../configuration-element.md)  
&nbsp;&nbsp; **\<startup >**  

## <a name="syntax"></a>Sintaxis

```xml
<startup useLegacyV2RuntimeActivationPolicy="true|false" > 
</startup>
```

## <a name="attributes-and-elements"></a>Atributos y elementos

 En las secciones siguientes se describen atributos, elementos secundarios y elementos primarios.

### <a name="attributes"></a>Atributos

|Atributo|Descripción|
|---------------|-----------------|
|`useLegacyV2RuntimeActivationPolicy`|Atributo opcional.<br /><br /> Especifica si se debe habilitar la Directiva de activación en tiempo de ejecución de .NET Framework 2,0 o usar la Directiva de activación de .NET Framework 4.|

## <a name="uselegacyv2runtimeactivationpolicy-attribute"></a>useLegacyV2RuntimeActivationPolicy (atributo)

|Valor|Descripción|
|-----------|-----------------|
|`true`|Habilite la Directiva de activación en tiempo de ejecución de .NET Framework 2,0 para el tiempo de ejecución elegido, que consiste en enlazar las técnicas de activación en tiempo de ejecución heredadas (como la [función CorBindToRuntimeEx](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md)) al tiempo de ejecución elegido desde el archivo de configuración en lugar de limitarlos a la versión 2,0 de CLR. Por lo tanto, si se elige CLR versión 4 o posterior del archivo de configuración, los ensamblados de modo mixto creados con versiones anteriores del .NET Framework se cargan con la versión de CLR elegida. Si se establece este valor, se evita que la versión 1,1 o la versión 2,0 de CLR se carguen en el mismo proceso, deshabilitando eficazmente la característica en paralelo en proceso.|
|`false`|Use la Directiva de activación predeterminada para el .NET Framework 4 y versiones posteriores, que consiste en permitir técnicas de activación en tiempo de ejecución heredadas para cargar la versión 1,1 o 2,0 de CLR en el proceso. Al establecer este valor, se evita que los ensamblados de modo mixto se carguen en el .NET Framework 4 o posterior, a menos que se hayan compilado con .NET Framework 4 o posterior. Este es el valor predeterminado.|

### <a name="child-elements"></a>Elementos secundarios

|Elemento|Descripción|
|-------------|-----------------|
|[\<requiredRuntime>](requiredruntime-element.md)|Especifica que la aplicación solo admite la versión 1.0 de Common Language Runtime. Las aplicaciones compiladas con la versión 1,1 o posterior del tiempo de ejecución deben usar el elemento **\<supportedRuntime >** .|
|[\<supportedRuntime>](supportedruntime-element.md)|Especifica qué versiones de Common Language Runtime admite la aplicación.|

### <a name="parent-elements"></a>Elementos primarios

|Elemento|Descripción|
|-------------|-----------------|
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|

## <a name="remarks"></a>Comentarios

 Todas las aplicaciones compiladas con la versión 1,1 o posterior del tiempo de ejecución deben usar el elemento **\<supportedRuntime >** . Las aplicaciones compiladas para admitir solo la versión 1,0 del Runtime deben usar el elemento **\<requiredRuntime >** .

 El código de inicio de una aplicación hospedada en Microsoft Internet Explorer omite el elemento **\<> de inicio** y sus elementos secundarios.

## <a name="the-uselegacyv2runtimeactivationpolicy-attribute"></a>El atributo useLegacyV2RuntimeActivationPolicy

 Este atributo es útil si la aplicación usa rutas de activación heredadas, como la [función CorBindToRuntimeEx](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md), y desea que esas rutas de acceso activen la versión 4 de CLR en lugar de una versión anterior, o si la aplicación se compila con el .NET Framework 4 pero tiene una dependencia en un ensamblado de modo mixto creado con una versión anterior del .NET Framework. En esos escenarios, establezca el atributo en `true`.

> [!NOTE]
> Al establecer el atributo en `true` se impide que se cargue la versión 1,1 o la versión 2,0 de CLR en el mismo proceso, lo que permite deshabilitar la característica en paralelo en proceso (vea la [ejecución en paralelo para la interoperabilidad com](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/8t8td04t(v=vs.100))).

## <a name="example"></a>Ejemplo

 En el ejemplo siguiente se muestra cómo especificar la versión en tiempo de ejecución en un archivo de configuración.

```xml
<!-- When used with version 1.0 of the .NET Framework runtime -->
<configuration>
   <startup>
      <requiredRuntime version="v1.0.3705" safemode="true"/>
   </startup>
</configuration>
<!-- When used with version 1.1 (or later) of the runtime -->
<configuration>
   <startup>
      <supportedRuntime version="v1.1.4322"/>
      <supportedRuntime version="v1.0.3705"/>
   </startup>
</configuration>
```

## <a name="see-also"></a>Vea también

- [Esquema de la configuración de inicio](index.md)
- [Esquema de los archivos de configuración](../index.md)
- [Cómo: configurar una aplicación para admitir .NET Framework 4 o versiones posteriores](../../../migration-guide/how-to-configure-an-app-to-support-net-framework-4-or-4-5.md)
- [Ejecución en paralelo para la interoperabilidad COM](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/8t8td04t(v=vs.100))
- [Ejecución en paralelo en proceso](../../../deployment/in-process-side-by-side-execution.md)
