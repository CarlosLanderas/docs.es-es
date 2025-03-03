---
title: Introducción a Containers y Docker
description: Consulte una introducción de alto nivel a las principales ventajas del uso de Docker.
ms.date: 02/15/2019
ms.openlocfilehash: 9ac08a64cd2465b4b88a266c1ec0925f37680bf9
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2019
ms.locfileid: "73738175"
---
# <a name="introduction-to-containers-and-docker"></a>Introducción a Containers y Docker

*La creación de contenedores es un enfoque de desarrollo de software en el que una aplicación o un servicio, sus dependencias y su configuración (extraídos como archivos de manifiesto de implementación) se empaquetan como una imagen de contenedor. Puede probar la aplicación en contenedor como una unidad e implementarla como una instancia de imagen de contenedor en el sistema operativo host.*

Del mismo modo que los contenedores de mercancías permiten su transporte por barco, tren o camión independientemente de la carga de su interior, los contenedores de software actúan como una unidad estándar de implementación de software que puede contener diferentes dependencias y código. De esta manera, la inclusión del software en contenedor permite a los desarrolladores y los profesionales de TI implementarlo en entornos con pocas modificaciones o ninguna en absoluto.

Los contenedores también aíslan las aplicaciones entre sí en un sistema operativo compartido. Las aplicaciones en contenedor se ejecutan sobre un host de contenedor que a su vez se ejecuta en el sistema operativo (Linux o Windows). Por lo tanto, los contenedores tienen una superficie mucho menor que las imágenes de máquina virtual (VM).

Cada contenedor puede ejecutar una aplicación web o un servicio al completo, como se muestra en la figura 1-1. En este ejemplo, el host de Docker es un host de contenedor, y App 1, App 2, Svc 1 y Svc 2 son aplicaciones o servicios en contenedor.

![Diagrama en el que se muestran cuatro contenedores que se ejecutan en una máquina virtual o un servidor.](./media/index/multiple-containers-single-host.png)

**Figura 1-1**. Varios contenedores ejecutándose en un host de contenedor.

Otra ventaja derivada de la inclusión en contenedores es la escalabilidad. La creación de contenedores para tareas a corto plazo permite escalar horizontalmente con gran rapidez. Desde el punto de vista de la aplicación, la creación de instancias de una imagen (la creación de un contenedor) es similar a la creación de instancias de un proceso como un servicio o una aplicación web. Pero con fines de confiabilidad, cuando ejecute varias instancias de la misma imagen en varios servidores host, seguramente le interesará que cada contenedor (instancia de imagen) se ejecute en un servidor host o máquina virtual diferente en dominios de error distintos.

En resumen, los contenedores ofrecen las ventajas del aislamiento, la portabilidad, la agilidad, la escalabilidad y el control a lo largo de todo el flujo de trabajo del ciclo de vida de la aplicación. La ventaja más importante es el aislamiento del entorno que se proporciona entre el desarrollo y las operaciones.

>[!div class="step-by-step"]
>[Siguiente](what-is-docker.md)
