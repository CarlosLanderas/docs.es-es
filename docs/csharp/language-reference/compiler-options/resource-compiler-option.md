---
title: -resource (Opciones del compilador de C#)
ms.date: 07/20/2015
f1_keywords:
- /resource
helpviewer_keywords:
- -resource compiler option [C#]
- /resource compiler option [C#]
- -res compiler option [C#]
- /res compiler option [C#]
- res compiler option [C#]
- resource compiler option [C#]
ms.assetid: 5212666e-98ab-47e4-a497-b5545ab15c7f
ms.openlocfilehash: e14bf59f5922a918b627af22c052c8efd9081e84
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/19/2019
ms.locfileid: "69602528"
---
# <a name="-resource-c-compiler-options"></a>-resource (Opciones del compilador de C#)
Inserta el recurso especificado en el archivo de salida.  
  
## <a name="syntax"></a>Sintaxis  
  
```console  
-resource:filename[,identifier[,accessibility-modifier]]  
```  
  
## <a name="arguments"></a>Argumentos  
 `filename`  
 El archivo de recursos de .NET Framework que quiere insertar en el archivo de salida.  
  
 `identifier` (opcional)  
 El nombre lógico del recurso; nombre que se usa para cargar el recurso. El valor predeterminado es el nombre del archivo.  
  
 `accessibility-modifier` (opcional)  
 La accesibilidad del recurso: pública o privada. El valor predeterminado es que sea pública.  
  
## <a name="remarks"></a>Comentarios  
 Use [-linkresource](./linkresource-compiler-option.md) para vincular un recurso a un ensamblado y no agregar el archivo de recursos al archivo de salida.  
  
 De manera predeterminada, los recursos son públicos en el ensamblado cuando se crean mediante el compilador de C#. Para que sean privados, especifique el modificador de accesibilidad `private`. No se permite ninguna otra accesibilidad distinta de `public` o `private`.  
  
 Si `filename` es un archivo de recursos de .NET Framework creado, por ejemplo, con [Resgen.exe](../../../framework/tools/resgen-exe-resource-file-generator.md) o en el entorno de desarrollo, se puede obtener acceso a él con miembros del espacio de nombres <xref:System.Resources>. Para más información, consulte <xref:System.Resources.ResourceManager?displayProperty=nameWithType>. Para todos los demás recursos, use los métodos `GetManifestResource` de la clase <xref:System.Reflection.Assembly> para tener acceso al recurso en tiempo de ejecución.  
  
 **-res** es la forma abreviada de **-resource**.  
  
 El orden de los recursos en el archivo de salida se determina a partir del orden especificado en la línea de comandos.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Para establecer esta opción del compilador en el entorno de desarrollo de Visual Studio  
  
1. Agregue un archivo de recursos al proyecto.  
  
2. Seleccione el archivo que quiere insertar en el **Explorador de soluciones**.  
  
3. Seleccione **Acción de compilación** para el archivo en la ventana **Propiedades**.  
  
4. Establezca **Acción de compilación** en **Recurso incrustado**.  
  
 Para obtener información sobre cómo establecer esta opción del compilador mediante programación, vea <xref:VSLangProj80.FileProperties2.BuildAction%2A>.  
  
## <a name="example"></a>Ejemplo  
 Compile `in.cs` y adjunte el archivo de recursos `rf.resource`:  
  
```console  
csc -resource:rf.resource in.cs  
```  
  
## <a name="see-also"></a>Vea también

- [Opciones del compilador de C#](./index.md)
- [Administrar propiedades de soluciones y proyectos](/visualstudio/ide/managing-project-and-solution-properties)
