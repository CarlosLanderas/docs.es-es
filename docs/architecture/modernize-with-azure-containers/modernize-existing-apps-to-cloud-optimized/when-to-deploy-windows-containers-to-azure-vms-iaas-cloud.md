---
title: Cuándo se deben implementar contenedores de Windows en máquinas virtuales de Azure (nube IaaS)
description: Modernización de las aplicaciones .NET existentes con Azure Clour y contenedores Windows | Cuándo se deben implementar contenedores Windows en máquinas virtuales de Azure (nube IaaS)
ms.date: 04/28/2018
ms.openlocfilehash: e9a2903662306b607977a7751018e24161ab80ab
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/08/2019
ms.locfileid: "69577908"
---
# <a name="when-to-deploy-windows-containers-to-azure-vms-iaas-cloud"></a>Cuándo se deben implementar contenedores de Windows en máquinas virtuales de Azure (nube IaaS)

Si su organización usa máquinas virtuales de Azure, aunque también esté usando contenedores Windows, seguirá tratando con IaaS. Esto significa que, cuando necesite realizar una implementación en varias máquinas virtuales en una infraestructura con equilibrio de carga, tendrá que tratar con las operaciones de infraestructura, las revisiones del sistema operativo de las máquinas virtuales y la complejidad de la infraestructura para aplicaciones altamente escalables. Los principales escenarios para el uso de contenedores Windows en una máquina virtual de Azure son:

- **Entornos de desarrollo y pruebas**: una máquina virtual en la nube es perfecta para actividades de desarrollo y pruebas en la nube. Puede crear o detener el entorno rápidamente en función de sus necesidades.

- **Necesidades de escalabilidad pequeñas y medianas**: en escenarios en los que podría necesitar un par de máquinas virtuales para el entorno de producción, administrar un número pequeño de máquinas virtuales puede resultar asequible hasta que pueda pasar a entornos PaaS más avanzados, como los orquestadores.

- **Entorno de producción con herramientas de implementación existentes**: podría pasar de un entorno local en el que ha realizado inversiones en herramientas a realizar implementaciones complejas en máquinas virtuales o en servidores sin sistema operativo (como Puppet o herramientas similares). Para pasar a la nube con unos cambios mínimos en los procedimientos de implementación del entorno de producción, puede seguir usando esas herramientas para realizar las implementaciones en máquinas virtuales de Azure. Sin embargo, querrá usar contenedores Windows como unidad de implementación para mejorar la experiencia de implementación.

>[!div class="step-by-step"]
>[Anterior](when-to-deploy-windows-containers-in-your-on-premises-iaas-vm-infrastructure.md)
>[Siguiente](when-to-deploy-windows-containers-to-azure-container-instances-ACI.md)
