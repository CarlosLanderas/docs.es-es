---
title: 'Cómo: Definir una operación de servicio (Data Services de WCF)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Service Operations [WCF Data Services]
- WCF Data Services, service operations
ms.assetid: dfcd3cb1-2f07-4d0b-b16a-6b056c4f45fa
ms.openlocfilehash: e9d15698c1e020f5b4179efb3e8492f3754ff02f
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2019
ms.locfileid: "74569127"
---
# <a name="how-to-define-a-service-operation-wcf-data-services"></a><span data-ttu-id="c1ac0-102">Cómo: Definir una operación de servicio (Data Services de WCF)</span><span class="sxs-lookup"><span data-stu-id="c1ac0-102">How to: Define a Service Operation (WCF Data Services)</span></span>

<span data-ttu-id="c1ac0-103">WCF Data Services exponer métodos que se definen en el servidor como operaciones de servicio.</span><span class="sxs-lookup"><span data-stu-id="c1ac0-103">WCF Data Services expose methods that are defined on the server as service operations.</span></span> <span data-ttu-id="c1ac0-104">Las operaciones de servicio permiten que un servicio de datos proporcione acceso a través de un URI a un método que se define en el servidor.</span><span class="sxs-lookup"><span data-stu-id="c1ac0-104">Service operations allow a data service to provide access through a URI to a method that is defined on the server.</span></span> <span data-ttu-id="c1ac0-105">Para definir una operación de servicio, aplique el atributo [`WebGet]` o `[WebInvoke]` al método.</span><span class="sxs-lookup"><span data-stu-id="c1ac0-105">To define a service operation, apply the [`WebGet]` or `[WebInvoke]` attribute to the method.</span></span> <span data-ttu-id="c1ac0-106">Para admitir los operadores de consulta, la operación de servicio debe devolver una instancia de <xref:System.Linq.IQueryable%601>.</span><span class="sxs-lookup"><span data-stu-id="c1ac0-106">To support query operators, the service operation must return an <xref:System.Linq.IQueryable%601> instance.</span></span> <span data-ttu-id="c1ac0-107">Las operaciones del servicio pueden tener acceso al origen de datos subyacente por medio de la propiedad <xref:System.Data.Services.DataService%601.CurrentDataSource%2A> en <xref:System.Data.Services.DataService%601>.</span><span class="sxs-lookup"><span data-stu-id="c1ac0-107">Service operations may access the underlying data source through the <xref:System.Data.Services.DataService%601.CurrentDataSource%2A> property on the <xref:System.Data.Services.DataService%601>.</span></span> <span data-ttu-id="c1ac0-108">Para obtener más información, consulte [operaciones de servicio](service-operations-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="c1ac0-108">For more information, see [Service Operations](service-operations-wcf-data-services.md).</span></span>

<span data-ttu-id="c1ac0-109">En el ejemplo de este tema se define una operación del servicio denominada `GetOrdersByCity` que devuelve una instancia de <xref:System.Linq.IQueryable%601> filtrada de los objetos `Orders` y `Order_Details` relacionados.</span><span class="sxs-lookup"><span data-stu-id="c1ac0-109">The example in this topic defines a service operation named `GetOrdersByCity` that returns a filtered <xref:System.Linq.IQueryable%601> instance of `Orders` and related `Order_Details` objects.</span></span> <span data-ttu-id="c1ac0-110">En el ejemplo se obtiene acceso a la instancia de <xref:System.Data.Objects.ObjectContext> que es el origen de datos del servicio de datos de ejemplo Northwind.</span><span class="sxs-lookup"><span data-stu-id="c1ac0-110">The example accesses the <xref:System.Data.Objects.ObjectContext> instance that is the data source for the Northwind sample data service.</span></span> <span data-ttu-id="c1ac0-111">Este servicio se crea cuando se completa la guía de [Inicio rápido de WCF Data Services](quickstart-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="c1ac0-111">This service is created when you complete the [WCF Data Services quickstart](quickstart-wcf-data-services.md).</span></span>

### <a name="to-define-a-service-operation-in-the-northwind-data-service"></a><span data-ttu-id="c1ac0-112">Para definir una operación del servicio en el servicio de datos Northwind</span><span class="sxs-lookup"><span data-stu-id="c1ac0-112">To define a service operation in the Northwind data service</span></span>

1. <span data-ttu-id="c1ac0-113">En el proyecto del servicio de datos Northwind, abra el archivo Northwind.svc.</span><span class="sxs-lookup"><span data-stu-id="c1ac0-113">In the Northwind data service project, open the Northwind.svc file.</span></span>

2. <span data-ttu-id="c1ac0-114">En la clase `Northwind`, defina un método de operación de servicio denominado `GetOrdersByCity` como sigue:</span><span class="sxs-lookup"><span data-stu-id="c1ac0-114">In the `Northwind` class, define a service operation method named `GetOrdersByCity` as follows:</span></span>

     [!code-csharp[Astoria Northwind Service#ServiceOperationDef](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_service/cs/northwind2.svc.cs#serviceoperationdef)]
     [!code-vb[Astoria Northwind Service#ServiceOperationDef](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_service/vb/northwind2.svc.vb#serviceoperationdef)]

3. <span data-ttu-id="c1ac0-115">En el método `InitializeService` de la clase `Northwind`, agregue el siguiente código para permitir el acceso a la operación del servicio:</span><span class="sxs-lookup"><span data-stu-id="c1ac0-115">In the `InitializeService` method of the `Northwind` class, add the following code to enable access to the service operation:</span></span>

     [!code-csharp[Astoria Northwind Service#ServiceOperationConfig](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_service/cs/northwind2.svc.cs#serviceoperationconfig)]
     [!code-vb[Astoria Northwind Service#ServiceOperationConfig](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_service/vb/northwind2.svc.vb#serviceoperationconfig)]

### <a name="to-query-the-getordersbycity-service-operation"></a><span data-ttu-id="c1ac0-116">Para consultar la operación del servicio GetOrdersByCity</span><span class="sxs-lookup"><span data-stu-id="c1ac0-116">To query the GetOrdersByCity service operation</span></span>

- <span data-ttu-id="c1ac0-117">En un explorador web, escriba uno de los siguientes URI para invocar la operación del servicio que se define en el siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="c1ac0-117">In a Web browser, enter one of the following URIs to invoke the service operation that is defined in the following example:</span></span>

  - `http://localhost:12345/Northwind.svc/GetOrdersByCity?city='London'`

  - `http://localhost:12345/Northwind.svc/GetOrdersByCity?city='London'&$top=2`

  - `http://localhost:12345/Northwind.svc/GetOrdersByCity?city='London'&$expand=Order_Details&$orderby=RequiredDate desc`

## <a name="example"></a><span data-ttu-id="c1ac0-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c1ac0-118">Example</span></span>

<span data-ttu-id="c1ac0-119">En el ejemplo siguiente se implementa una operación del servicio denominada `GetOrderByCity` en el servicio de datos Northwind.</span><span class="sxs-lookup"><span data-stu-id="c1ac0-119">The following example implements a service operation named `GetOrderByCity` on the Northwind data service.</span></span> <span data-ttu-id="c1ac0-120">Esta operación utiliza ADO.NET Entity Framework para devolver un conjunto de objetos `Orders` y `Order_Details` relacionados como una instancia de <xref:System.Linq.IQueryable%601> basada en el nombre de ciudad suministrado.</span><span class="sxs-lookup"><span data-stu-id="c1ac0-120">This operation uses the ADO.NET Entity Framework to return a set of `Orders` and related `Order_Details` objects as an <xref:System.Linq.IQueryable%601> instance based on the provided city name.</span></span>

> [!NOTE]
> <span data-ttu-id="c1ac0-121">Los operadores de consulta se admiten en este extremo de la operación del servicio porque el método devuelve una instancia de <xref:System.Linq.IQueryable%601>.</span><span class="sxs-lookup"><span data-stu-id="c1ac0-121">Query operators are supported on this service operation endpoint because the method returns an <xref:System.Linq.IQueryable%601> instance.</span></span>

[!code-csharp[Astoria Northwind Service#ServiceOperation](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_service/cs/northwind2.svc.cs#serviceoperation)]
[!code-vb[Astoria Northwind Service#ServiceOperation](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_service/vb/northwind2.svc.vb#serviceoperation)]

## <a name="see-also"></a><span data-ttu-id="c1ac0-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="c1ac0-122">See also</span></span>

- [<span data-ttu-id="c1ac0-123">Definir Servicios de datos de WCF</span><span class="sxs-lookup"><span data-stu-id="c1ac0-123">Defining WCF Data Services</span></span>](defining-wcf-data-services.md)
