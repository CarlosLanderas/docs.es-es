---
title: Get WorkflowInstanceId
ms.date: 03/30/2017
ms.assetid: bd7eea3b-1c28-4b84-9a67-003bc553aa81
ms.openlocfilehash: 37dc0cac9c6ac69b9e430677a9c8cf3f47b200eb
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/03/2019
ms.locfileid: "74716019"
---
# <a name="get-workflowinstanceid"></a>Get WorkflowInstanceId
En este ejemplo se muestra cómo utilizar la actividad personalizada `GetWorkflowInstanceId` para devolver el identificador de la instancia de flujo de trabajo.  
  
## <a name="demonstrates"></a>Demostraciones  
 Desarrollo de actividades personalizadas, cómo tener acceso a la instancia de flujo de trabajo.  
  
## <a name="discussion"></a>Discusión  
 La obtención del Id. de instancia de un flujo de trabajo en ejecución requiere código de escritura. Si desea escribir un flujo de trabajo totalmente declarativo, necesita una actividad que pueda devolver el identificador de la instancia de flujo de trabajo para que se pueda hacer referencia a la actividad en el flujo de trabajo a fin de proporcionar un flujo de trabajo totalmente declarativo que cree la experiencia. Muchos escenarios requieren tener acceso al Id. de instancia: algunos ejemplos son para registrar o auditar propósitos o para realizar una correlación en la aplicación proporcionando el Id. de instancia a un cliente para su asociación futura (por ejemplo, utilizando esta actividad dentro de una actividad SendReply).  
  
 `GetWorkflowInstanceId` se implementa como un objeto <xref:System.Activities.CodeActivity%601> porque debe devolver un valor de tipo <xref:System.Guid> y debe tener acceso a <xref:System.Activities.CodeActivityContext> para obtener el Id. de instancia del flujo de trabajo. Su implementación es bastante básica.  
  
```csharp  
public sealed class GetWorkflowInstanceId : CodeActivity<Guid>  
{  
    protected override Guid Execute(CodeActivityContext context)  
    {  
        return context.WorkflowInstanceId;  
    }  
}
```  
  
> [!IMPORTANT]
> Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los ejemplos de Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)]. Este ejemplo se encuentra en el siguiente directorio.  
>   
> `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\GetWorkflowInstanceId`
