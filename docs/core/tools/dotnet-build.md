---
title: Comando dotnet build
description: El comando dotnet build compila un proyecto y todas sus dependencias.
ms.date: 10/14/2019
ms.openlocfilehash: b85ef06aa445e4708487deed9ec6bfeffeab3657
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2019
ms.locfileid: "73454217"
---
# <a name="dotnet-build"></a>dotnet build

**Este artículo se aplica a: ✓** SDK de .NET Core 1.x y versiones posteriores

<!-- todo: uncomment when all CLI commands are reviewed
[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]
-->

## <a name="name"></a>Name

`dotnet build`: compila un proyecto y todas sus dependencias.

## <a name="synopsis"></a>Sinopsis

```dotnetcli
dotnet build [<PROJECT>|<SOLUTION>] [-c|--configuration] [-f|--framework] [--force]
    [--interactive] [--no-dependencies] [--no-incremental] [--no-restore] [--nologo] 
    [-o|--output] [-r|--runtime] [-v|--verbosity] [--version-suffix]

dotnet build [-h|--help]
```

## <a name="description"></a>DESCRIPCIÓN

El comando `dotnet build` crea el proyecto y sus dependencias en un conjunto de archivos binarios. Los archivos binarios incluyen el código del proyecto en archivos de lenguaje intermedio (IL) con una extensión *.dll*.  Según el tipo de proyecto y la configuración, se pueden incluir otros archivos, como los siguientes:

- Un archivo ejecutable que se pueda usar para ejecutar la aplicación, si el tipo de proyecto es un archivo ejecutable que tiene como destino .NET Core 3.0 o versiones posteriores.
- Archivos de símbolos usados para la depuración con una extensión *.pdb*.
- Un archivo *.deps.json*, que muestra las dependencias de la aplicación o la biblioteca.
- Un archivo *.runtimeconfig.json*, que especifica el runtime compartido y su versión de una aplicación.
- Otras bibliotecas de las que depende el proyecto (a través de referencias de proyecto o referencias de paquetes NuGet).

En el caso de los proyectos ejecutables que tienen como destino versiones anteriores a .NET Core 3.0, las dependencias de biblioteca de NuGet normalmente no se copian en la carpeta de salida.  Se resuelven desde la carpeta de paquetes globales NuGet en tiempo de ejecución. Teniendo eso en cuenta, el producto de `dotnet build` no está listo para transferirse a otra máquina para ejecutarse. Para crear una versión de la aplicación que se pueda implementar, se debe publicar (por ejemplo, con el comando [dotnet publish](dotnet-publish.md)). Para obtener más información, consulte el tema [Implementación de aplicaciones .NET Core](../deploying/index.md).

En el caso de los proyectos ejecutables que tienen como destino .NET Core 3.0 y versiones posteriores, las dependencias de biblioteca se copian en la carpeta de salida. Esto significa que, si no hay ninguna otra lógica específica de la publicación (como los proyectos web), se debería poder implementar la salida de la compilación.

La compilación requiere el archivo *project.assets.json*, que muestra las dependencias de la aplicación. El archivo se crea cuando se ejecuta [`dotnet restore`](dotnet-restore.md). Sin el archivo de recursos en su lugar, las herramientas no pueden resolver los ensamblados de referencia, lo que se traduce en errores. Con el SDK de .NET Core 1.x, era necesario ejecutar de forma explícita `dotnet restore` antes de ejecutar `dotnet build`. A partir del SDK de .NET Core 2.0, `dotnet restore` se ejecuta implícitamente al ejecutar `dotnet build`. Si quiere deshabilitar la restauración implícita cuando se ejecuta el comando de compilación, puede usar la opción `--no-restore`.

[!INCLUDE[dotnet restore note + options](~/includes/dotnet-restore-note-options.md)]

Si el proyecto es ejecutable o no viene determinado por la propiedad `<OutputType>` en el archivo del proyecto. En el ejemplo siguiente se muestra un proyecto en el que se genera código ejecutable:

```xml
<PropertyGroup>
  <OutputType>Exe</OutputType>
</PropertyGroup>
```

Para generar una biblioteca, omita la propiedad `<OutputType>` o cambie su valor a `Library`. La DLL de IL para una biblioteca no contiene puntos de entrada y no se puede ejecutar.

### <a name="msbuild"></a>MSBuild

`dotnet build` usa MSBuild para compilar el proyecto, por lo que admite las compilaciones en paralelo e incrementales. Para obtener más información, consulte [Compilaciones incrementales](/visualstudio/msbuild/incremental-builds).

Además de sus opciones, el comando `dotnet build` acepta opciones de MSBuild, como `-p` para establecer propiedades o `-l` para definir un registrador. Para obtener más información sobre estas opciones, vea la [Referencia de la línea de comandos de MSBuild](/visualstudio/msbuild/msbuild-command-line-reference). O también puede usar el comando [dotnet msbuild](dotnet-msbuild.md).

Ejecutar `dotnet build` es equivalente a ejecutar `dotnet msbuild -restore`; sin embargo, el nivel de detalle predeterminado de la salida es distinto.

## <a name="arguments"></a>Argumentos

`PROJECT | SOLUTION`

El archivo de proyecto o solución para compilar. Si no se especifica un archivo de proyecto o solución, MSBuild busca en el directorio de trabajo actual un archivo que tiene una extensión de archivo que termina por *proj* o *sln* y usa ese archivo.

## <a name="options"></a>Opciones

- **`-c|--configuration {Debug|Release}`**

  Define la configuración de compilación. El valor predeterminado para la mayoría de los proyectos es `Debug`, pero puede invalidar los valores de configuración de compilación en el proyecto.

- **`-f|--framework <FRAMEWORK>`**

  Compila para un [marco de trabajo](../../standard/frameworks.md) específico. El marco se debe definir en el [archivo de proyecto](csproj.md).

- **`--force`**

  Fuerza la resolución de todas las dependencias, incluso si la última restauración se realizó correctamente. Especificar esta marca es lo mismo que eliminar el archivo *project.assets.json*. Disponible a partir del SDK de .NET Core 2.0.

- **`-h|--help`**

  Imprime una corta ayuda para el comando.

- **`--interactive`**

  Permite que el comando se detenga y espere una entrada o una acción del usuario. Por ejemplo, para completar la autenticación. Disponible desde el SDK de .NET Core 3.0.

- **`--no-dependencies`**

  Omite las referencias de proyecto a proyecto (P2P) y solo compila el proyecto raíz especificado.

- **`--no-incremental`**

  Marca la compilación como no segura para la compilación incremental. Esta marca desactiva la compilación incremental y fuerza una recompilación limpia del gráfico de dependencias del proyecto.

- **`--no-restore`**

  No ejecuta una restauración implícita durante la compilación. Disponible a partir del SDK de .NET Core 2.0.

- **`--nologo`**

  No se muestra la pancarta de inicio ni el mensaje de copyright. Disponible desde el SDK de .NET Core 3.0.

- **`-o|--output <OUTPUT_DIRECTORY>`**

  Directorio donde se colocan los archivos binarios compilados. Si no se especifica la ruta de acceso predeterminada es `./bin/<configuration>/<framework>/`.  En el caso de los proyectos con varias plataformas de destino (a través de la propiedad `TargetFrameworks`), también debe definir `--framework` al especificar esta opción.

- **`-r|--runtime <RUNTIME_IDENTIFIER>`**

  Especifica el tiempo de ejecución de destino. Para obtener una lista de identificadores de tiempo de ejecución (RID), consulte el [catálogo de RID](../rid-catalog.md).

- **`-v|--verbosity <LEVEL>`**

  Establece el nivel de detalle de MSBuild. Los valores permitidos son `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` y `diag[nostic]`. De manera predeterminada, es `minimal`.

- **`--version-suffix <VERSION_SUFFIX>`**

  Establece el valor de la propiedad `$(VersionSuffix)` que se va a usar al compilar el proyecto. Solo funciona si no se establece la propiedad `$(Version)`. A continuación, `$(Version)` se establece en `$(VersionPrefix)` combinada con `$(VersionSuffix)`, separadas por un guion.

## <a name="examples"></a>Ejemplos

- Creación de un proyecto y sus dependencias:

  ```dotnetcli
  dotnet build
  ```

- Creación de un proyecto y sus dependencias mediante la configuración de lanzamiento:

  ```dotnetcli
  dotnet build --configuration Release
  ```

- Compilación de un proyecto y sus dependencias para un tiempo de ejecución concreto (en este ejemplo, Ubuntu 18.04):

  ```dotnetcli
  dotnet build --runtime ubuntu.18.04-x64
  ```

- Compile el proyecto y use origen del paquete NuGet especificado durante la operación de restauración (SDK de .NET Core 2.0 y versiones posteriores):

  ```dotnetcli
  dotnet build --source c:\packages\mypackages
  ```

- Compile el proyecto y establezca la versión 1.2.3.4 como un parámetro de compilación mediante la `-p`opción [ de MSBuild](#msbuild):

  ```dotnetcli
  dotnet build -p:Version=1.2.3.4
  ```
