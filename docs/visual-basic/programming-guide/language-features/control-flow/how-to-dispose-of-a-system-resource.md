---
title: 'Cómo: Deshacerse de un recurso del sistema'
ms.date: 07/20/2015
helpviewer_keywords:
- Using statement [Visual Basic], disposing of system resources
- Visual Basic code, control flow
- system resources, disposing of
- resources [Visual Basic], disposing of system
- system resources
- Using statement [Visual Basic], Using...End Using
- Using block
ms.assetid: 8be2b239-8090-419b-8e7e-bcaa75b0ecc8
ms.openlocfilehash: c493051050442597196ba484fb9ce8e99249dbb7
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74353942"
---
# <a name="how-to-dispose-of-a-system-resource-visual-basic"></a><span data-ttu-id="46129-102">Cómo: Deshacerse de un recurso del sistema (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="46129-102">How to: Dispose of a System Resource (Visual Basic)</span></span>
<span data-ttu-id="46129-103">Puede usar un bloque `Using` para garantizar que el sistema desecha un recurso cuando el código sale del bloque.</span><span class="sxs-lookup"><span data-stu-id="46129-103">You can use a `Using` block to guarantee that the system disposes of a resource when your code exits the block.</span></span> <span data-ttu-id="46129-104">Esto resulta útil si está utilizando un recurso del sistema que consume una gran cantidad de memoria, o que otros componentes también desean usar.</span><span class="sxs-lookup"><span data-stu-id="46129-104">This is useful if you are using a system resource that consumes a large amount of memory, or that other components also want to use.</span></span>  
  
### <a name="to-dispose-of-a-database-connection-when-your-code-is-finished-with-it"></a><span data-ttu-id="46129-105">Para eliminar una conexión de base de datos cuando el código finaliza con ella</span><span class="sxs-lookup"><span data-stu-id="46129-105">To dispose of a database connection when your code is finished with it</span></span>  
  
1. <span data-ttu-id="46129-106">Asegúrese de incluir la [instrucción Imports (espacio de nombres y tipo .net)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) adecuada para la conexión de base de datos al principio del archivo de código fuente (en este caso, <xref:System.Data.SqlClient>).</span><span class="sxs-lookup"><span data-stu-id="46129-106">Make sure you include the appropriate [Imports Statement (.NET Namespace and Type)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) for the database connection at the beginning of your source file (in this case, <xref:System.Data.SqlClient>).</span></span>  
  
2. <span data-ttu-id="46129-107">Cree un bloque `Using` con las instrucciones `Using` y `End Using`.</span><span class="sxs-lookup"><span data-stu-id="46129-107">Create a `Using` block with the `Using` and `End Using` statements.</span></span> <span data-ttu-id="46129-108">Dentro del bloque, coloque el código que se ocupa de la conexión de base de datos.</span><span class="sxs-lookup"><span data-stu-id="46129-108">Inside the block, put the code that deals with the database connection.</span></span>  
  
3. <span data-ttu-id="46129-109">Declare la conexión y cree una instancia de ella como parte de la instrucción `Using`.</span><span class="sxs-lookup"><span data-stu-id="46129-109">Declare the connection and create an instance of it as part of the `Using` statement.</span></span>  
  
    ```vb  
    ' Insert the following line at the beginning of your source file.  
    Imports System.Data.SqlClient  
    Public Sub AccessSql(ByVal s As String)  
        Using sqc As New System.Data.SqlClient.SqlConnection(s)  
            MsgBox("Connected with string """ & sqc.ConnectionString & """")  
        End Using  
    End Sub  
    ```  
  
     <span data-ttu-id="46129-110">El sistema desecha el recurso independientemente de cómo salga del bloque, incluido el caso de una excepción no controlada.</span><span class="sxs-lookup"><span data-stu-id="46129-110">The system disposes of the resource no matter how you exit the block, including the case of an unhandled exception.</span></span>  
  
     <span data-ttu-id="46129-111">Tenga en cuenta que no puede tener acceso a `sqc` desde fuera del bloque de `Using`, porque su ámbito está limitado al bloque.</span><span class="sxs-lookup"><span data-stu-id="46129-111">Note that you cannot access `sqc` from outside the `Using` block, because its scope is limited to the block.</span></span>  
  
     <span data-ttu-id="46129-112">Puede usar esta misma técnica en un recurso del sistema, como un identificador de archivo o un contenedor COM.</span><span class="sxs-lookup"><span data-stu-id="46129-112">You can use this same technique on a system resource such as a file handle or a COM wrapper.</span></span> <span data-ttu-id="46129-113">Use un bloque de `Using` cuando desee asegurarse de dejar el recurso disponible para otros componentes después de salir del bloque de `Using`.</span><span class="sxs-lookup"><span data-stu-id="46129-113">You use a `Using` block when you want to be sure to leave the resource available for other components after you have exited the `Using` block.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46129-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="46129-114">See also</span></span>

- <xref:System.Data.SqlClient.SqlConnection>
- [<span data-ttu-id="46129-115">Flujo de control</span><span class="sxs-lookup"><span data-stu-id="46129-115">Control Flow</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)
- [<span data-ttu-id="46129-116">Estructuras de decisión</span><span class="sxs-lookup"><span data-stu-id="46129-116">Decision Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)
- [<span data-ttu-id="46129-117">Estructuras de bucle</span><span class="sxs-lookup"><span data-stu-id="46129-117">Loop Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
- [<span data-ttu-id="46129-118">Estructuras de control adicionales</span><span class="sxs-lookup"><span data-stu-id="46129-118">Other Control Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/other-control-structures.md)
- [<span data-ttu-id="46129-119">Estructuras de control anidadas</span><span class="sxs-lookup"><span data-stu-id="46129-119">Nested Control Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)
- [<span data-ttu-id="46129-120">Using (instrucción)</span><span class="sxs-lookup"><span data-stu-id="46129-120">Using Statement</span></span>](../../../../visual-basic/language-reference/statements/using-statement.md)
