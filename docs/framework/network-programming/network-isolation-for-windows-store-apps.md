---
title: Aislamiento de red para aplicaciones de la Tienda Windows
ms.date: 03/30/2017
ms.assetid: b064497c-d956-46b8-838d-7a0223c7e200
ms.openlocfilehash: 34b8865781079f45a68d3dd1aab7fbd66c703d50
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74447423"
---
# <a name="network-isolation-for-windows-store-apps"></a>Aislamiento de red para aplicaciones de la Tienda Windows
Es posible usar las clases de los espacios de nombres <xref:System.Net>, <xref:System.Net.Http> y <xref:System.Net.Http.Headers> para desarrollar aplicaciones de la Tienda Windows o aplicaciones de escritorio. Cuando se usan en una aplicación de la Tienda Windows, las clases de estos espacios de nombres se ven afectadas por el aislamiento de red, que forma parte del modelo de seguridad para las aplicaciones usado por [!INCLUDE[win8](../../../includes/win8-md.md)]. Las funcionalidades de red correspondientes deben estar habilitadas en el manifiesto de la aplicación de la Tienda Windows para que el sistema permita el acceso a la red.  
  
## <a name="checklist-for-network-isolation"></a>Lista de comprobación para el aislamiento de red  
 Use esta lista de comprobación para asegurarse de que el aislamiento de red está configurado para la aplicación de la Tienda Windows.  
  
1. Determine la dirección de las solicitudes de acceso a la red que necesita la aplicación. Puede tratarse de solicitudes salientes iniciadas por el cliente, solicitudes entrantes no solicitadas o una combinación de ambos tipos de solicitudes de red.  
  
2. Determine el tipo de recursos de red con los que se comunicará la aplicación. Una aplicación podría tener que comunicarse con recursos de confianza en una red doméstica o de trabajo. Una aplicación podría tener que comunicarse con recursos de Internet. Una aplicación podría necesitar tener acceso a ambos tipos de recursos de red.  
  
3. Configure las funcionalidades mínimas necesarias de aislamiento de red en el manifiesto de la aplicación.  
  
4. Implemente y ejecute la aplicación para probarla mediante las herramientas de aislamiento de red proporcionadas para la solución de problemas.  
  
 Para obtener más información sobre cómo configurar las funcionalidades de red y las herramientas de aislamiento que se usan para la solución de problemas de aislamiento de red, vea [Cómo configurar las funcionalidades de aislamiento de red](https://docs.microsoft.com/previous-versions/windows/apps/hh770532(v=win.10)) en la documentación para desarrolladores de la Tienda Windows 8.x.
  
## <a name="see-also"></a>Vea también

- [Conectar con un servicio web](https://docs.microsoft.com/previous-versions/windows/apps/hh761504(v=win.10))
- [Directrices y lista de comprobación para el aislamiento de red](https://docs.microsoft.com/previous-versions/windows/apps/hh770532(v=win.10))
- [Inicio rápido: conectarse mediante HttpClient](https://docs.microsoft.com/previous-versions/windows/apps/hh781239(v=win.10))
- [Cómo usar controladores HttpClient](https://docs.microsoft.com/previous-versions/windows/apps/hh781241(v=win.10))
- [Cómo proteger conexiones HttpClient](https://docs.microsoft.com/previous-versions/windows/apps/hh781240(v=win.10))
- [Ejemplo de HttpClient](https://code.msdn.microsoft.com/windowsapps/HttpClient-sample-55700664)
