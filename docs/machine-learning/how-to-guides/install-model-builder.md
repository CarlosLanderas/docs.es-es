---
title: Cómo instalar el Generador de modelos
description: Obtenga información sobre cómo instalar la herramienta Generador de modelos de ML.NET.
author: luisquintanilla
ms.author: luquinta
ms.date: 11/21/2019
ms.custom: mvc, how-to
ms.openlocfilehash: b87f712ad7a8b2229c1d42db4bad1fe511475ac7
ms.sourcegitcommit: 93762e1a0dae1b5f64d82eebb7b705a6d566d839
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/27/2019
ms.locfileid: "74552941"
---
# <a name="how-to-install-mlnet-model-builder"></a>Cómo instalar el Generador de modelos de ML.NET

Obtenga información sobre cómo instalar el Generador de modelos de ML.NET para agregar aprendizaje automático a las aplicaciones. NET.

> [!NOTE]
> De momento, el Generador de modelos se encuentra en versión preliminar.

## <a name="prerequisites"></a>Requisitos previos

- Visual Studio 2017, versión 15.9.12 o una posterior/Visual Studio 2019
- SDK de .NET Core 2.1 o versiones posteriores.

> [!NOTE]
> El SDK de .NET Core 3.0 no se admite actualmente.

## <a name="limitations"></a>Limitaciones

- La extensión Generador de modelos de ML.NET solo funciona actualmente en Visual Studio para Windows.
- El límite del conjunto de datos de entrenamiento es de 1 GB
- SQL Server tiene un límite de 100 000 filas para el entrenamiento
- No admite Microsoft SQL Server Data Tools para Visual Studio 2017

## <a name="install"></a>Instalar

El Generador de modelos de ML.NET se puede instalar desde Visual Studio Marketplace o desde el propio Visual Studio.

### <a name="visual-studio-marketplace"></a>Visual Studio Marketplace

1. Descargar desde [Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=MLNET.07)
1. Siga las indicaciones para instalar en la versión correspondiente de Visual Studio.

### <a name="visual-studio-2017"></a>Visual Studio 2017

1. En la barra de menús, elija **Herramientas** > **Extensiones y actualizaciones**.

    ![Cuadro de diálogo Abrir administrador de extensiones de VS2017](./media/install-model-builder/vs2017-open-extensions-manager.png)

1. Dentro del símbolo del sistema de *Extensiones y actualizaciones*, seleccione el nodo *En línea*.
1. En la barra de búsqueda, busque *Generador de modelos de ML.NET* y en los resultados, seleccione Generador de modelos de ML.NET (versión preliminar).

    ![Cuadro de diálogo de búsqueda e instalación de la extensión del Generador de modelos en el Administrador de extensiones de VS2017](./media/install-model-builder/vs2017-install-model-builder.png)

1. Siga las indicaciones para completar la instalación.

### <a name="visual-studio-2019"></a>Visual Studio 2019

1. En la barra de menús, elija **Extensiones** > **Administrar extensiones**.

    ![Cuadro de diálogo Abrir administrador de extensiones de VS2019](./media/install-model-builder/vs2019-open-extensions-manager.png)

1. Dentro del símbolo del sistema de *Extensiones y actualizaciones*, seleccione el nodo *En línea*.
1. Busque *Generador de modelos de ML.NET* en la barra de búsqueda y seleccione Generador de modelos de ML.NET (versión preliminar).

    ![Cuadro de diálogo de búsqueda e instalación de la extensión del Generador de modelos en el Administrador de extensiones de VS2019](./media/install-model-builder/vs2019-install-model-builder.png)

1. Siga las indicaciones para completar la instalación.

## <a name="uninstall"></a>Desinstalar

### <a name="visual-studio-2017"></a>Visual Studio 2017

1. En la barra de menús, elija **Herramientas** > **Extensiones y actualizaciones**.

    ![Abrir cuadro de diálogo de administración de extensiones de VS2017](./media/install-model-builder/vs2017-open-extensions-manager.png)

1. Dentro del símbolo del sistema de *Extensiones y actualizaciones*, expanda el nodo *Instaladas* y seleccione *Herramientas*.
1. Seleccione Generador de modelos de ML.NET (versión preliminar) en la lista de herramientas y, a continuación, seleccione *Desinstalar*.

    ![Cuadro de diálogo de búsqueda e instalación de la extensión del Generador de modelos en el Administrador de extensiones de VS2017](./media/install-model-builder/vs2017-uninstall-model-builder.png)

1. Siga las indicaciones para completar la desinstalación.

### <a name="visual-studio-2019"></a>Visual Studio 2019

1. En la barra de menús, elija **Extensiones** > **Administrar extensiones**.

    ![Abrir cuadro de diálogo de administración de extensiones de VS2019](./media/install-model-builder/vs2019-open-extensions-manager.png)

1. Dentro del símbolo del sistema de *Extensiones y actualizaciones*, expanda el nodo *Instaladas* y seleccione *Herramientas*.
1. Seleccione Generador de modelos de ML.NET (versión preliminar) en la lista de herramientas y, a continuación, seleccione *Desinstalar*.

    ![Cuadro de diálogo de búsqueda e instalación de la extensión del Generador de modelos en el Administrador de extensiones de VS2019](./media/install-model-builder/vs2019-uninstall-model-builder.png)

1. Siga las indicaciones para completar la desinstalación.

## <a name="upgrade"></a>Actualización:

El proceso de actualización es similar al proceso de instalación. Descargue la versión más reciente desde Visual Studio Marketplace o use el Administrador de extensiones de Visual Studio.
