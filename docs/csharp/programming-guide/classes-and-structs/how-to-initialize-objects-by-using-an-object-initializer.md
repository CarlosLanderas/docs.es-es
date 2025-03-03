---
title: Procedimiento para inicializar objetos usando un inicializador de objeto - Guía de programación de C#
ms.custom: seodec18
ms.date: 12/20/2018
helpviewer_keywords:
- object initializers [C#], how to use
- objects [C#], initializing
ms.assetid: 4b75ebb2-2e29-43de-929c-d736a8f27ce6
ms.openlocfilehash: be555688a645c7689e76b5b4499c44255c18dbc8
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/12/2019
ms.locfileid: "73970878"
---
# <a name="how-to-initialize-objects-by-using-an-object-initializer-c-programming-guide"></a>Procedimiento para inicializar objetos usando un inicializador de objeto (Guía de programación de C#)

Puede usar inicializadores de objeto para inicializar objetos de tipo de una forma declarativa sin tener que invocar explícitamente un constructor para el tipo.  
  
En los siguientes ejemplos se muestra cómo usar los inicializadores de objeto con objetos con nombre. El compilador procesa los inicializadores de objeto primero obteniendo acceso al constructor de instancia predeterminado y después procesando las inicializaciones de miembro. Por lo tanto, si el constructor sin parámetros se declara como `private` en la clase, se producirá un error en los inicializadores de objeto que requieren acceso público.
  
Debe usar un inicializador de objeto si va a definir un tipo anónimo. Para obtener más información, vea [Procedimiento para devolver subconjuntos de propiedades de elementos en una consulta](how-to-return-subsets-of-element-properties-in-a-query.md).  
  
## <a name="example"></a>Ejemplo  

En el siguiente ejemplo se muestra cómo inicializar un nuevo tipo `StudentName` usando inicializadores de objeto. Este ejemplo establece propiedades en el tipo `StudentName`:
  
[!code-csharp[InitializerObjectExample](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/object-collection-initializers/HowToObjectInitializers.cs#HowToObjectInitializers)]  

Los inicializadores de objeto pueden usarse para establecer indizadores en un objeto. En el ejemplo siguiente se define una clase `BaseballTeam` que usa un indizador para obtener y establecer jugadores en posiciones diferentes. El inicializador puede asignar jugadores en función de la abreviatura de la posición o del número usado para las puntuaciones de béisbol de cada posición:

[!code-csharp[InitializerIndexerExample](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/object-collection-initializers/HowToIndexInitializer.cs#HowToIndexInitializer)]  

## <a name="see-also"></a>Vea también

- [Guía de programación de C#](../index.md)
- [Inicializadores de objeto y colección](object-and-collection-initializers.md)
