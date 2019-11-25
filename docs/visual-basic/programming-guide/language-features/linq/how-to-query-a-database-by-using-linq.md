---
title: 'How to: Query a Database by Using LINQ'
ms.date: 07/20/2015
helpviewer_keywords:
- query samples [LINQ]
- database querying [LINQ]
- queries [LINQ in Visual Basic], database querying
- querying databases [LINQ]
- queries [LINQ in Visual Basic], how-to topics
- query samples [Visual Basic]
ms.assetid: bcf5e9c3-a236-4399-9a7f-3991eca7cf56
ms.openlocfilehash: f4b2510bad2b23d7a0e179383b34c4e425e6564e
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344962"
---
# <a name="how-to-query-a-database-by-using-linq-visual-basic"></a><span data-ttu-id="331a3-102">Cómo: Consultar una base de datos usando LINQ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="331a3-102">How to: Query a Database by Using LINQ (Visual Basic)</span></span>
<span data-ttu-id="331a3-103">Language-Integrated Query (LINQ) makes it easy to access database information and execute queries.</span><span class="sxs-lookup"><span data-stu-id="331a3-103">Language-Integrated Query (LINQ) makes it easy to access database information and execute queries.</span></span>  
  
 <span data-ttu-id="331a3-104">The following example shows how to create a new application that performs queries against a SQL Server database.</span><span class="sxs-lookup"><span data-stu-id="331a3-104">The following example shows how to create a new application that performs queries against a SQL Server database.</span></span>  
  
 <span data-ttu-id="331a3-105">The examples in this topic use the Northwind sample database.</span><span class="sxs-lookup"><span data-stu-id="331a3-105">The examples in this topic use the Northwind sample database.</span></span> <span data-ttu-id="331a3-106">If you do not have this database on your development computer, you can download it from the Microsoft Download Center.</span><span class="sxs-lookup"><span data-stu-id="331a3-106">If you do not have this database on your development computer, you can download it from the Microsoft Download Center.</span></span> <span data-ttu-id="331a3-107">For instructions, see [Downloading Sample Databases](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).</span><span class="sxs-lookup"><span data-stu-id="331a3-107">For instructions, see [Downloading Sample Databases](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="to-create-a-connection-to-a-database"></a><span data-ttu-id="331a3-108">To create a connection to a database</span><span class="sxs-lookup"><span data-stu-id="331a3-108">To create a connection to a database</span></span>  
  
1. <span data-ttu-id="331a3-109">In Visual Studio, open **Server Explorer**/**Database Explorer** by clicking **Server Explorer**/**Database Explorer** on the **View** menu.</span><span class="sxs-lookup"><span data-stu-id="331a3-109">In Visual Studio, open **Server Explorer**/**Database Explorer** by clicking **Server Explorer**/**Database Explorer** on the **View** menu.</span></span>  
  
2. <span data-ttu-id="331a3-110">Right-click **Data Connections** in **Server Explorer**/**Database Explorer** and then click **Add Connection**.</span><span class="sxs-lookup"><span data-stu-id="331a3-110">Right-click **Data Connections** in **Server Explorer**/**Database Explorer** and then click **Add Connection**.</span></span>  
  
3. <span data-ttu-id="331a3-111">Specify a valid connection to the Northwind sample database.</span><span class="sxs-lookup"><span data-stu-id="331a3-111">Specify a valid connection to the Northwind sample database.</span></span>  
  
## <a name="to-add-a-project-that-contains-a-linq-to-sql-file"></a><span data-ttu-id="331a3-112">To add a project that contains a LINQ to SQL file</span><span class="sxs-lookup"><span data-stu-id="331a3-112">To add a project that contains a LINQ to SQL file</span></span>  
  
1. <span data-ttu-id="331a3-113">En el menú **Archivo** de Visual Studio, apunte a **Nuevo** y haga clic en **Proyecto**.</span><span class="sxs-lookup"><span data-stu-id="331a3-113">In Visual Studio, on the **File** menu, point to **New** and then click **Project**.</span></span> <span data-ttu-id="331a3-114">Select Visual Basic **Windows Forms Application** as the project type.</span><span class="sxs-lookup"><span data-stu-id="331a3-114">Select Visual Basic **Windows Forms Application** as the project type.</span></span>  
  
2. <span data-ttu-id="331a3-115">En el menú **Proyecto** , haga clic en **Agregar nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="331a3-115">On the **Project** menu, click **Add New Item**.</span></span> <span data-ttu-id="331a3-116">Select the **LINQ to SQL Classes** item template.</span><span class="sxs-lookup"><span data-stu-id="331a3-116">Select the **LINQ to SQL Classes** item template.</span></span>  
  
3. <span data-ttu-id="331a3-117">Asigne al archivo el nombre `northwind.dbml`.</span><span class="sxs-lookup"><span data-stu-id="331a3-117">Name the file `northwind.dbml`.</span></span> <span data-ttu-id="331a3-118">Haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="331a3-118">Click **Add**.</span></span> <span data-ttu-id="331a3-119">The Object Relational Designer (O/R Designer) is opened for the northwind.dbml file.</span><span class="sxs-lookup"><span data-stu-id="331a3-119">The Object Relational Designer (O/R Designer) is opened for the northwind.dbml file.</span></span>  
  
## <a name="to-add-tables-to-query-to-the-or-designer"></a><span data-ttu-id="331a3-120">To add tables to query to the O/R Designer</span><span class="sxs-lookup"><span data-stu-id="331a3-120">To add tables to query to the O/R Designer</span></span>  
  
1. <span data-ttu-id="331a3-121">In **Server Explorer**/**Database Explorer**, expand the connection to the Northwind database.</span><span class="sxs-lookup"><span data-stu-id="331a3-121">In **Server Explorer**/**Database Explorer**, expand the connection to the Northwind database.</span></span> <span data-ttu-id="331a3-122">Expand the **Tables** folder.</span><span class="sxs-lookup"><span data-stu-id="331a3-122">Expand the **Tables** folder.</span></span>  
  
     <span data-ttu-id="331a3-123">If you have closed the O/R Designer, you can reopen it by double-clicking the northwind.dbml file that you added earlier.</span><span class="sxs-lookup"><span data-stu-id="331a3-123">If you have closed the O/R Designer, you can reopen it by double-clicking the northwind.dbml file that you added earlier.</span></span>  
  
2. <span data-ttu-id="331a3-124">Click the Customers table and drag it to the left pane of the designer.</span><span class="sxs-lookup"><span data-stu-id="331a3-124">Click the Customers table and drag it to the left pane of the designer.</span></span> <span data-ttu-id="331a3-125">Click the Orders table and drag it to the left pane of the designer.</span><span class="sxs-lookup"><span data-stu-id="331a3-125">Click the Orders table and drag it to the left pane of the designer.</span></span>  
  
     <span data-ttu-id="331a3-126">The designer creates new `Customer` and `Order` objects for your project.</span><span class="sxs-lookup"><span data-stu-id="331a3-126">The designer creates new `Customer` and `Order` objects for your project.</span></span> <span data-ttu-id="331a3-127">Notice that the designer automatically detects relationships between the tables and creates child properties for related objects.</span><span class="sxs-lookup"><span data-stu-id="331a3-127">Notice that the designer automatically detects relationships between the tables and creates child properties for related objects.</span></span> <span data-ttu-id="331a3-128">For example, IntelliSense will show that the `Customer` object has an `Orders` property for all orders related to that customer.</span><span class="sxs-lookup"><span data-stu-id="331a3-128">For example, IntelliSense will show that the `Customer` object has an `Orders` property for all orders related to that customer.</span></span>  
  
3. <span data-ttu-id="331a3-129">Save your changes and close the designer.</span><span class="sxs-lookup"><span data-stu-id="331a3-129">Save your changes and close the designer.</span></span>  
  
4. <span data-ttu-id="331a3-130">Guarde el proyecto.</span><span class="sxs-lookup"><span data-stu-id="331a3-130">Save your project.</span></span>  
  
## <a name="to-add-code-to-query-the-database-and-display-the-results"></a><span data-ttu-id="331a3-131">To add code to query the database and display the results</span><span class="sxs-lookup"><span data-stu-id="331a3-131">To add code to query the database and display the results</span></span>  
  
1. <span data-ttu-id="331a3-132">From the **Toolbox**, drag a <xref:System.Windows.Forms.DataGridView> control onto the default Windows Form for your project, Form1.</span><span class="sxs-lookup"><span data-stu-id="331a3-132">From the **Toolbox**, drag a <xref:System.Windows.Forms.DataGridView> control onto the default Windows Form for your project, Form1.</span></span>  
  
2. <span data-ttu-id="331a3-133">Double-click Form1 to add code to the `Load` event of the form.</span><span class="sxs-lookup"><span data-stu-id="331a3-133">Double-click Form1 to add code to the `Load` event of the form.</span></span>  
  
3. <span data-ttu-id="331a3-134">When you added tables to the O/R Designer, the designer added a <xref:System.Data.Linq.DataContext> object for your project.</span><span class="sxs-lookup"><span data-stu-id="331a3-134">When you added tables to the O/R Designer, the designer added a <xref:System.Data.Linq.DataContext> object for your project.</span></span> <span data-ttu-id="331a3-135">This object contains the code that you must have to access those tables, in addition to individual objects and collections for each table.</span><span class="sxs-lookup"><span data-stu-id="331a3-135">This object contains the code that you must have to access those tables, in addition to individual objects and collections for each table.</span></span> <span data-ttu-id="331a3-136">The <xref:System.Data.Linq.DataContext> object for your project is named based on the name of your .dbml file.</span><span class="sxs-lookup"><span data-stu-id="331a3-136">The <xref:System.Data.Linq.DataContext> object for your project is named based on the name of your .dbml file.</span></span> <span data-ttu-id="331a3-137">For this project, the <xref:System.Data.Linq.DataContext> object is named `northwindDataContext`.</span><span class="sxs-lookup"><span data-stu-id="331a3-137">For this project, the <xref:System.Data.Linq.DataContext> object is named `northwindDataContext`.</span></span>  
  
     <span data-ttu-id="331a3-138">You can create an instance of the <xref:System.Data.Linq.DataContext> in your code and query the tables specified by the O/R Designer.</span><span class="sxs-lookup"><span data-stu-id="331a3-138">You can create an instance of the <xref:System.Data.Linq.DataContext> in your code and query the tables specified by the O/R Designer.</span></span>  
  
     <span data-ttu-id="331a3-139">Add the following code to the `Load` event to query the tables that are exposed as properties of your data context.</span><span class="sxs-lookup"><span data-stu-id="331a3-139">Add the following code to the `Load` event to query the tables that are exposed as properties of your data context.</span></span>  
  
     [!code-vb[VbLINQToSQLHowTos#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQtoSQLHowTos/VB/Form2.vb#3)]  
  
4. <span data-ttu-id="331a3-140">Press F5 to run your project and view the results.</span><span class="sxs-lookup"><span data-stu-id="331a3-140">Press F5 to run your project and view the results.</span></span>  
  
5. <span data-ttu-id="331a3-141">Following are some additional queries that you can try:</span><span class="sxs-lookup"><span data-stu-id="331a3-141">Following are some additional queries that you can try:</span></span>  
  
     [!code-vb[VbLINQToSQLHowTos#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQtoSQLHowTos/VB/Form2.vb#4)]  
    [!code-vb[VbLINQToSQLHowTos#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQtoSQLHowTos/VB/Form2.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="331a3-142">Vea también</span><span class="sxs-lookup"><span data-stu-id="331a3-142">See also</span></span>

- [<span data-ttu-id="331a3-143">LINQ</span><span class="sxs-lookup"><span data-stu-id="331a3-143">LINQ</span></span>](../../../../visual-basic/programming-guide/language-features/linq/index.md)
- [<span data-ttu-id="331a3-144">Consultas</span><span class="sxs-lookup"><span data-stu-id="331a3-144">Queries</span></span>](../../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="331a3-145">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="331a3-145">LINQ to SQL</span></span>](../../../../framework/data/adonet/sql/linq/index.md)
- [<span data-ttu-id="331a3-146">Métodos DataContext (Object Relational Designer)</span><span class="sxs-lookup"><span data-stu-id="331a3-146">DataContext Methods (O/R Designer)</span></span>](/visualstudio/data-tools/datacontext-methods-o-r-designer)
