---
title: Introducción
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: db8a557a-fef8-4f4f-bb91-8cff7250ee25
ms.openlocfilehash: bd82b7e83149aaa53cf1b240cb79f8747bccba47
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70793913"
---
# <a name="getting-started"></a>Introducción
Mediante el [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]uso de, puede usar [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] la tecnología de para tener acceso a las bases de datos SQL de la misma forma que tendría acceso a una colección en memoria.  
  
 Por ejemplo, en el código siguiente, se crea el objeto `nw` para representar la base de datos `Northwind`, el destino es la tabla `Customers`, las filas se filtran para `Customers` de `London` y se selecciona para la recuperación una cadena de `CompanyName`.  
  
 Cuando se ejecuta el bucle, se recupera la colección de valores `CompanyName`.  
  
 [!code-csharp[DLinqGettingStarted#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqGettingStarted/cs/Program.cs#1)]
 [!code-vb[DLinqGettingStarted#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqGettingStarted/vb/Module1.vb#1)]  
  
## <a name="next-steps"></a>Pasos siguientes  
 Para ver algunos ejemplos adicionales, como la inserción y la actualización, consulte [lo que puede hacer con LINQ to SQL](what-you-can-do-with-linq-to-sql.md).  
  
 Luego, intente realizar algunos tutoriales para obtener experiencia práctica en el uso de [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]. Vea [aprendizaje de los tutoriales](learning-by-walkthroughs.md).  
  
 Por último, aprenda a empezar a trabajar en su [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] propio proyecto mediante la lectura de [los pasos típicos para usar LINQ to SQL](typical-steps-for-using-linq-to-sql.md).  
  
## <a name="see-also"></a>Vea también

- [LINQ to SQL](index.md)
- [Introducción a LINQ (C#)](../../../../../csharp/programming-guide/concepts/linq/index.md)
- [Introducción a LINQ (Visual Basic)](../../../../../visual-basic/programming-guide/concepts/linq/introduction-to-linq.md)
- [Modelo de objetos de LINQ to SQL](the-linq-to-sql-object-model.md)
