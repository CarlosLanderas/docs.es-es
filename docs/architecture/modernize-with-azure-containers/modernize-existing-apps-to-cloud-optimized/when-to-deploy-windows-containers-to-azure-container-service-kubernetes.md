---
title: Cuándo se deben implementar contenedores Windows en Azure Container Service (es decir, Kubernetes)
description: Modernización de las aplicaciones .NET existentes con Azure Clour y contenedores Windows | Cuándo se deben implementar contenedores Windows en Azure Container Service (es decir, Kubernetes)
ms.date: 04/30/2018
ms.openlocfilehash: 903082deba635dd0dfc22d0186fbc589f8d05b92
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/08/2019
ms.locfileid: "69577948"
---
# <a name="when-to-deploy-windows-containers-to-azure-container-service-that-is-kubernetes"></a>Cuándo se deben implementar contenedores Windows en Azure Container Service (es decir, Kubernetes)

Azure Container Service optimiza la configuración de las conocidas herramientas y tecnologías de código abierto específicamente para Azure. Se trata de una solución abierta que ofrece portabilidad tanto para los contenedores como para la configuración de la aplicación. Seleccione el tamaño, el número de hosts y las herramientas de orquestador. Azure Container Service controla la infraestructura.

Si ya está trabajando con orquestadores de código abierto, como Kubernetes, Docker Swarm o DC/OS, no es necesario cambiar los procedimientos de administración existentes para trasladar las cargas de trabajo de los contenedores a la nube. Use las herramientas de administración de aplicaciones con las que ya está familiarizado y conéctelas a través de los puntos de conexión de API estándar para el orquestador de su elección.

Todos estos orquestadores son entornos maduros si usa contenedores Linux de Docker, pero podrían estar solo en versión preliminar para los contenedores Windows.

Por ejemplo, en Kubernetes, la compatibilidad con contenedores es nativa (ciudadano de primera clase), por lo que el uso de contenedores Windows en Kubernetes también es eficaz (en versión preliminar en ACS desde principios de 2018).

Nota importante: La versión evolucionada y "más PaaS" de ACS (Azure Container Service) para Kubernetes es AKS (Azure Kubernetes Service). Sin embargo, en el 2T de 2018 no se admiten aún los contenedores Windows, que pronto se admitirán.

>[!div class="step-by-step"]
>[Anterior](when-to-deploy-windows-containers-to-azure-container-instances-ACI.md)
>[Siguiente](choosing-azure-compute-options-for-container-based-applications.md)
