---
title: 'Tarea 2: Hospedaje del Diseñador de flujo de trabajo'
ms.date: 03/30/2017
ms.assetid: 0a29b138-270d-4846-b78e-2b875e34e501
ms.openlocfilehash: 8e4c17ed182cec7748b9a1f11f76ff90aa60c39e
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/03/2019
ms.locfileid: "74715790"
---
# <a name="task-2-host-the-workflow-designer"></a><span data-ttu-id="b9b8c-102">Tarea 2: Hospedaje del Diseñador de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="b9b8c-102">Task 2: Host the Workflow Designer</span></span>

<span data-ttu-id="b9b8c-103">En este tema se describe el procedimiento para hospedar una instancia de Windows Diseñador de flujo de trabajo en una aplicación de Windows Presentation Foundation (WPF).</span><span class="sxs-lookup"><span data-stu-id="b9b8c-103">This topic describes the procedure for hosting an instance of the Windows Workflow Designer in a Windows Presentation Foundation (WPF) application.</span></span>

<span data-ttu-id="b9b8c-104">El procedimiento configura el control de **cuadrícula** que contiene el diseñador, crea mediante programación una instancia de la <xref:System.Activities.Presentation.WorkflowDesigner> que contiene una actividad <xref:System.Activities.Statements.Sequence> predeterminada, registra los metadatos del diseñador para proporcionar compatibilidad con el diseñador para todas las actividades integradas y hospeda la diseñador de flujo de trabajo en la aplicación WPF.</span><span class="sxs-lookup"><span data-stu-id="b9b8c-104">The procedure configures the **Grid** control that contains the designer, programmatically creates an instance of the <xref:System.Activities.Presentation.WorkflowDesigner> that contains a default <xref:System.Activities.Statements.Sequence> activity, registers the designer metadata to provide designer support for all built-in activities, and hosts the Workflow Designer in the WPF application.</span></span>

## <a name="to-host-the-workflow-designer"></a><span data-ttu-id="b9b8c-105">Para hospedar el diseñador de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="b9b8c-105">To host the workflow designer</span></span>

1. <span data-ttu-id="b9b8c-106">Abra el proyecto HostingApplication que creó en la [tarea 1: crear una nueva aplicación de Windows Presentation Foundation](task-1-create-a-new-wpf-app.md).</span><span class="sxs-lookup"><span data-stu-id="b9b8c-106">Open the HostingApplication project you created in [Task 1: Create a New Windows Presentation Foundation Application](task-1-create-a-new-wpf-app.md).</span></span>

2. <span data-ttu-id="b9b8c-107">Ajuste el tamaño de la ventana para que sea más fácil usar el Diseñador de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="b9b8c-107">Adjust the size of the window to make it easier to use the Workflow Designer.</span></span> <span data-ttu-id="b9b8c-108">Para ello, seleccione **MainWindow** en el diseñador, presione F4 para mostrar la ventana **propiedades** y, en la sección de **diseño** , establezca el **ancho** en un valor de 600 y el **alto** en un valor de 350.</span><span class="sxs-lookup"><span data-stu-id="b9b8c-108">To do this, select **MainWindow** in the designer, press F4 to display the **Properties** window, and, in the **Layout** section there, set the **Width** to a value of 600 and the **Height** to a value of 350.</span></span>

3. <span data-ttu-id="b9b8c-109">Para establecer el nombre de la cuadrícula, seleccione el panel de **cuadrícula** en el diseñador (haga clic en el cuadro dentro de **MainWindow**) y establezca la propiedad **nombre** en la parte superior de la ventana **propiedades** en "Grid1".</span><span class="sxs-lookup"><span data-stu-id="b9b8c-109">Set the grid name by selecting the **Grid** panel in the designer (click the box inside the **MainWindow**) and setting the **Name** property at the top of the **Properties** window to "grid1".</span></span>

4. <span data-ttu-id="b9b8c-110">En la ventana **propiedades** , haga clic en los puntos suspensivos ( **...** ) junto a la propiedad `ColumnDefinitions` para abrir el cuadro de diálogo Editor de la **colección** .</span><span class="sxs-lookup"><span data-stu-id="b9b8c-110">In the **Properties** window, click the ellipsis (**…**) next to the `ColumnDefinitions` property to open the **Collection Editor** dialog box.</span></span>

5. <span data-ttu-id="b9b8c-111">En el cuadro de diálogo **Editor de colecciones** , haga clic en el botón **Agregar** tres veces para insertar tres columnas en el diseño.</span><span class="sxs-lookup"><span data-stu-id="b9b8c-111">In the **Collection Editor** dialog box, click the **Add** button three times to insert three columns into the layout.</span></span> <span data-ttu-id="b9b8c-112">La primera columna contendrá el **cuadro de herramientas**, la segunda columna hospedará el diseñador de flujo de trabajo y la tercera columna se utilizará para el inspector de propiedad.</span><span class="sxs-lookup"><span data-stu-id="b9b8c-112">The first column will contain the **Toolbox**, the second column will host the Workflow Designer, and the third column will be used for the property inspector.</span></span>

6. <span data-ttu-id="b9b8c-113">Establezca la propiedad `Width` de la columna central en el valor "4 \*".</span><span class="sxs-lookup"><span data-stu-id="b9b8c-113">Set the `Width` property of the middle column to the value "4\*".</span></span>

7. <span data-ttu-id="b9b8c-114">Haga clic en **Aceptar** para guardar los cambios.</span><span class="sxs-lookup"><span data-stu-id="b9b8c-114">Click **OK** to save the changes.</span></span> <span data-ttu-id="b9b8c-115">El siguiente código XAML se agrega al archivo *MainWindow. Xaml* :</span><span class="sxs-lookup"><span data-stu-id="b9b8c-115">The following XAML is added to your *MainWindow.xaml* file:</span></span>

    ```xaml
    <Grid Name="grid1">
        <Grid.ColumnDefinitions>
            <ColumnDefinition />
            <ColumnDefinition Width="4*" />
            <ColumnDefinition />
        </Grid.ColumnDefinitions>
    </Grid>
    ```

8. <span data-ttu-id="b9b8c-116">En **Explorador de soluciones**, haga clic con el botón secundario en *MainWindow. Xaml* y seleccione **Ver código**.</span><span class="sxs-lookup"><span data-stu-id="b9b8c-116">In **Solution Explorer**, right-click *MainWindow.xaml* and select **View Code**.</span></span> <span data-ttu-id="b9b8c-117">Modifique el código siguiendo estos pasos:</span><span class="sxs-lookup"><span data-stu-id="b9b8c-117">Modify the code by following these steps:</span></span>

    1. <span data-ttu-id="b9b8c-118">Agregue los siguientes espacios de nombres:</span><span class="sxs-lookup"><span data-stu-id="b9b8c-118">Add the following namespaces:</span></span>

        ```csharp
        using System.Activities;
        using System.Activities.Core.Presentation;
        using System.Activities.Presentation;
        using System.Activities.Presentation.Metadata;
        using System.Activities.Presentation.Toolbox;
        using System.Activities.Statements;
        using System.ComponentModel;
        ```

    2. <span data-ttu-id="b9b8c-119">Para declarar un campo de miembro privado para que contenga una instancia de la <xref:System.Activities.Presentation.WorkflowDesigner>, agregue el código siguiente a la clase `MainWindow`:</span><span class="sxs-lookup"><span data-stu-id="b9b8c-119">To declare a private member field to hold an instance of the <xref:System.Activities.Presentation.WorkflowDesigner>, add the following code to the `MainWindow` class:</span></span>

        ```csharp
        public partial class MainWindow : Window
        {
            private WorkflowDesigner wd;

            public MainWindow()
            {
                InitializeComponent();
            }
        }
        ```

    3. <span data-ttu-id="b9b8c-120">Agregue el método `AddDesigner` siguiente a la clase `MainWindow`.</span><span class="sxs-lookup"><span data-stu-id="b9b8c-120">Add the following `AddDesigner` method to the `MainWindow` class.</span></span> <span data-ttu-id="b9b8c-121">La implementación crea una instancia de la <xref:System.Activities.Presentation.WorkflowDesigner>, le agrega una actividad <xref:System.Activities.Statements.Sequence> y la coloca en la columna central de la **cuadrícula**de Grid1.</span><span class="sxs-lookup"><span data-stu-id="b9b8c-121">The implementation creates an instance of the <xref:System.Activities.Presentation.WorkflowDesigner>, adds a <xref:System.Activities.Statements.Sequence> activity to it, and places it in middle column of the grid1 **Grid**.</span></span>

        ```csharp
        private void AddDesigner()
        {
            // Create an instance of WorkflowDesigner class.
            this.wd = new WorkflowDesigner();

            // Place the designer canvas in the middle column of the grid.
            Grid.SetColumn(this.wd.View, 1);

            // Load a new Sequence as default.
            this.wd.Load(new Sequence());

            // Add the designer canvas to the grid.
            grid1.Children.Add(this.wd.View);
        }
        ```

    4. <span data-ttu-id="b9b8c-122">Registre los metadatos del diseñador para agregar la compatibilidad con el diseñador para todas las actividades integradas.</span><span class="sxs-lookup"><span data-stu-id="b9b8c-122">Register the designer metadata to add designer support for all the  built-in activities.</span></span> <span data-ttu-id="b9b8c-123">Esto le permite colocar las actividades del cuadro de herramientas en la actividad <xref:System.Activities.Statements.Sequence> original del Diseñador de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="b9b8c-123">This enables you to drop activities from the toolbox onto the original <xref:System.Activities.Statements.Sequence> activity in the Workflow Designer.</span></span> <span data-ttu-id="b9b8c-124">Para ello, agregue el método `RegisterMetadata` a la clase `MainWindow`:</span><span class="sxs-lookup"><span data-stu-id="b9b8c-124">To do this, add the `RegisterMetadata` method to the `MainWindow` class:</span></span>

        ```csharp
        private void RegisterMetadata()
        {
            var dm = new DesignerMetadata();
            dm.Register();
        }
        ```

        <span data-ttu-id="b9b8c-125">Para obtener más información sobre el registro de diseñadores de actividad, vea [Cómo: crear un diseñador de actividad personalizado](how-to-create-a-custom-activity-designer.md).</span><span class="sxs-lookup"><span data-stu-id="b9b8c-125">For more information about registering activity designers, see [How to: Create a Custom Activity Designer](how-to-create-a-custom-activity-designer.md).</span></span>

    5. <span data-ttu-id="b9b8c-126">En el constructor de clases `MainWindow`, agregue llamadas a los métodos declarados previamente para registrar los metadatos a fin de ser compatibles con el diseñador y crear <xref:System.Activities.Presentation.WorkflowDesigner>.</span><span class="sxs-lookup"><span data-stu-id="b9b8c-126">In the `MainWindow` class constructor, add calls to the methods declared previously to register the metadata for designer support and to create the <xref:System.Activities.Presentation.WorkflowDesigner>.</span></span>

        ```csharp
        public MainWindow()
        {
            InitializeComponent();

            // Register the metadata.
            RegisterMetadata();

            // Add the WFF Designer.
            AddDesigner();
        }
        ```

        > [!NOTE]
        > <span data-ttu-id="b9b8c-127">El método `RegisterMetadata` registra los metadatos del diseñador de actividades integradas incluida la actividad <xref:System.Activities.Statements.Sequence>.</span><span class="sxs-lookup"><span data-stu-id="b9b8c-127">The `RegisterMetadata` method registers the designer metadata of built-in activities including the <xref:System.Activities.Statements.Sequence> activity.</span></span> <span data-ttu-id="b9b8c-128">Puesto que el método `AddDesigner` usa la actividad <xref:System.Activities.Statements.Sequence>, es necesario llamar primero al método `RegisterMetadata`.</span><span class="sxs-lookup"><span data-stu-id="b9b8c-128">Because the `AddDesigner` method uses the <xref:System.Activities.Statements.Sequence> activity, the `RegisterMetadata` method must be called first.</span></span>

9. <span data-ttu-id="b9b8c-129">Presione <kbd>F5</kbd> para compilar y ejecutar la solución.</span><span class="sxs-lookup"><span data-stu-id="b9b8c-129">Press <kbd>F5</kbd> to build and run the solution.</span></span>

10. <span data-ttu-id="b9b8c-130">Vea [tarea 3: creación de los paneles cuadro de herramientas y PropertyGrid](task-3-create-the-toolbox-and-propertygrid-panes.md) para obtener información sobre cómo agregar compatibilidad con el **cuadro de herramientas** y **PropertyGrid** al diseñador de flujo de trabajo hospedado en otro host.</span><span class="sxs-lookup"><span data-stu-id="b9b8c-130">See [Task 3: Create the Toolbox and PropertyGrid Panes](task-3-create-the-toolbox-and-propertygrid-panes.md) to learn how to add **Toolbox** and **PropertyGrid** support to your rehosted workflow designer.</span></span>

## <a name="see-also"></a><span data-ttu-id="b9b8c-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="b9b8c-131">See also</span></span>

- [<span data-ttu-id="b9b8c-132">Rehospedaje del Diseñador de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="b9b8c-132">Rehosting the Workflow Designer</span></span>](rehosting-the-workflow-designer.md)
- [<span data-ttu-id="b9b8c-133">Tarea 1: Crear una aplicación de Windows Presentation Foundation</span><span class="sxs-lookup"><span data-stu-id="b9b8c-133">Task 1: Create a New Windows Presentation Foundation Application</span></span>](task-1-create-a-new-wpf-app.md)
- [<span data-ttu-id="b9b8c-134">Tarea 3: Crear los paneles de Cuadro de herramientas y PropertyGrid</span><span class="sxs-lookup"><span data-stu-id="b9b8c-134">Task 3: Create the Toolbox and PropertyGrid Panes</span></span>](task-3-create-the-toolbox-and-propertygrid-panes.md)
