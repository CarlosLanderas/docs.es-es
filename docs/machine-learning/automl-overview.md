---
title: Aprendizaje automático automatizado con ML.NET
description: Introducción a la selección y el entrenamiento de modelos automáticos
author: natke
ms.date: 05/01/2019
ms.topic: overview
ms.custom: mvc
ms.author: nakersha
ms.openlocfilehash: 263004e67bf88af4182788e8c74cb410460e9201
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/12/2019
ms.locfileid: "73971405"
---
# <a name="automated-machine-learning-with-mlnet"></a>Aprendizaje automático automatizado con ML.NET

El aprendizaje automático automatizado es una característica de ML.NET que realiza automáticamente el entrenamiento y la selección de modelos. Especifique la tarea de aprendizaje automático y proporcione un conjunto de datos, y ML automatizado elegirá el modelo con las mejores métricas. Se genera:

- un archivo de modelo que se puede cargar en la aplicación de predicción
- código de aplicación para realizar predicciones
- el código fuente que se usa para la selección de características y el entrenamiento del modelo (para comprender el modelo)

> [!NOTE]
> Esta característica se encuentra actualmente en versión preliminar, por lo que el material está sujeto a cambios.

El ML automatizado se limita actualmente a las [tareas](resources/tasks.md) de aprendizaje automático de clasificación binaria, clasificación multiclase y regresión. Las demás tareas de aprendizaje automático se admitirán en versiones futuras.

Existen tres maneras de usar ML automatizado:

1. Con una interfaz gráfica de usuario, mediante el [compilador de modelos de ML.NET](automate-training-with-model-builder.md)
1. En la línea de comandos, con la [CLI de ML.NET](automate-training-with-cli.md)
1. A través de una aplicación, con la [API automatizada de ML](how-to-guides/how-to-use-the-automl-api.md)
