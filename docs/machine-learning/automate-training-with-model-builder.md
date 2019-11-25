---
title: ¿Qué es el Generador de modelos y cómo funciona?
description: Cómo usar el Generador de modelos de ML.NET para entrenar un modelo de Machine Learning de forma automática
author: natke
ms.date: 08/07/2019
ms.custom: overview
ms.openlocfilehash: 77fe56dba3532617ad9fb0c89bfaac7c8e031ce7
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/12/2019
ms.locfileid: "73971524"
---
# <a name="what-is-model-builder-and-how-does-it-work"></a><span data-ttu-id="516ab-103">¿Qué es el Generador de modelos y cómo funciona?</span><span class="sxs-lookup"><span data-stu-id="516ab-103">What is Model Builder and how does it work?</span></span>

<span data-ttu-id="516ab-104">El Generador de modelos de ML.NET es una extensión gráfica intuitiva de Visual Studio para compilar, entrenar e implementar modelos de Machine Learning personalizados.</span><span class="sxs-lookup"><span data-stu-id="516ab-104">ML.NET Model Builder is an intuitive graphical Visual Studio extension to build, train, and deploy custom machine learning models.</span></span>

<span data-ttu-id="516ab-105">El Generador de modelos usa aprendizaje automático automatizado (AutoML) para explorar distintos algoritmos y configuraciones de aprendizaje automático a fin de ayudar a encontrar el más adecuado a cada escenario.</span><span class="sxs-lookup"><span data-stu-id="516ab-105">Model Builder uses automated machine learning (AutoML) to explore different machine learning algorithms and settings to help you find the one that best suits your scenario.</span></span>

<span data-ttu-id="516ab-106">Para usar el Generador de modelos no se necesita experiencia previa con el aprendizaje automático.</span><span class="sxs-lookup"><span data-stu-id="516ab-106">You don't need machine learning expertise to use Model Builder.</span></span> <span data-ttu-id="516ab-107">Lo único que se necesita son algunos datos y un problema para resolver.</span><span class="sxs-lookup"><span data-stu-id="516ab-107">All you need is some data, and a problem to solve.</span></span> <span data-ttu-id="516ab-108">El Generador de modelos genera el código para agregar el modelo a la aplicación de .NET.</span><span class="sxs-lookup"><span data-stu-id="516ab-108">Model Builder generates the code to add the model to your .NET application.</span></span>

![Animación de la interfaz de usuario de la extensión Generador de modelos de Visual Studio](media/ml-dotnet-model-builder.gif)

> [!NOTE]
> <span data-ttu-id="516ab-110">De momento, el Generador de modelos se encuentra en versión preliminar.</span><span class="sxs-lookup"><span data-stu-id="516ab-110">Model Builder is currently in Preview.</span></span>

## <a name="scenarios"></a><span data-ttu-id="516ab-111">Escenarios</span><span class="sxs-lookup"><span data-stu-id="516ab-111">Scenarios</span></span>

<span data-ttu-id="516ab-112">Se pueden incorporar muchos escenarios diferentes al Generador de modelos a fin de generar un modelo de Machine Learning para la aplicación.</span><span class="sxs-lookup"><span data-stu-id="516ab-112">You can bring many different scenarios to Model Builder, to generate a machine learning model for your application.</span></span>

<span data-ttu-id="516ab-113">Un escenario es una descripción del tipo de predicción que se quiere realizar usando los datos.</span><span class="sxs-lookup"><span data-stu-id="516ab-113">A scenario is a description of the type of prediction you want to make using your data.</span></span> <span data-ttu-id="516ab-114">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="516ab-114">For example:</span></span>

- <span data-ttu-id="516ab-115">predecir el volumen futuro de ventas de productos en función de los datos de ventas históricos</span><span class="sxs-lookup"><span data-stu-id="516ab-115">predict future product sales volume based on historical sales data</span></span>
- <span data-ttu-id="516ab-116">clasificar opiniones como positivas o negativas en función de las revisiones de los clientes</span><span class="sxs-lookup"><span data-stu-id="516ab-116">classify sentiments as positive or negative based on customer reviews</span></span>
- <span data-ttu-id="516ab-117">detectar si una transacción bancaria es fraudulenta</span><span class="sxs-lookup"><span data-stu-id="516ab-117">detect whether a banking transaction is fraudulent</span></span>
- <span data-ttu-id="516ab-118">dirigir problemas de comentarios de clientes al equipo correcto de la empresa</span><span class="sxs-lookup"><span data-stu-id="516ab-118">route customer feedback issues to the correct team in your company</span></span>

## <a name="choose-a-model-type"></a><span data-ttu-id="516ab-119">Elegir un tipo de modelo</span><span class="sxs-lookup"><span data-stu-id="516ab-119">Choose a model type</span></span>

<span data-ttu-id="516ab-120">En el generador de modelos, debe seleccionar un tipo de modelo de Machine Learning.</span><span class="sxs-lookup"><span data-stu-id="516ab-120">In Model Builder, you need to select a machine learning model type.</span></span> <span data-ttu-id="516ab-121">El tipo de modelo depende del tipo de predicción que esté intentando realizar.</span><span class="sxs-lookup"><span data-stu-id="516ab-121">The type of model depends on what sort of prediction you are trying to make.</span></span>

<span data-ttu-id="516ab-122">En los escenarios que predicen un número, el tipo de modelo de Machine Learning se denomina `regression`.</span><span class="sxs-lookup"><span data-stu-id="516ab-122">For scenarios that predict a number, the machine learning model type is called `regression`.</span></span>

<span data-ttu-id="516ab-123">En los escenarios que predicen una categoría, el tipo de modelo es `classification`.</span><span class="sxs-lookup"><span data-stu-id="516ab-123">For scenarios that predict a category, the model type is `classification`.</span></span> <span data-ttu-id="516ab-124">Hay dos tipos de clasificaciones:</span><span class="sxs-lookup"><span data-stu-id="516ab-124">There are two types of classification:</span></span>

- <span data-ttu-id="516ab-125">la que cuenta con solo dos categorías: `binary classification`.</span><span class="sxs-lookup"><span data-stu-id="516ab-125">where there are only 2 categories: `binary classification`.</span></span>
- <span data-ttu-id="516ab-126">la que cuenta con tres categorías o más: `multiclass classification`.</span><span class="sxs-lookup"><span data-stu-id="516ab-126">where there are three or more categories: `multiclass classification`.</span></span>

### <a name="which-model-type-is-right-for-me"></a><span data-ttu-id="516ab-127">¿Qué tipo de modelo es el adecuado para mí?</span><span class="sxs-lookup"><span data-stu-id="516ab-127">Which model type is right for me?</span></span>

#### <a name="predict-a-category-when-there-are-only-two-categories"></a><span data-ttu-id="516ab-128">Predecir una categoría (que cuente solo con dos categorías)</span><span class="sxs-lookup"><span data-stu-id="516ab-128">Predict a category (when there are only two categories)</span></span>

<span data-ttu-id="516ab-129">La clasificación binaria se usa para clasificar los datos en dos categorías (sí o no; correcto o incorrecto; verdadero o falso; positivo o negativo).</span><span class="sxs-lookup"><span data-stu-id="516ab-129">Binary classification is used to categorize data into two categories (yes/no; pass/fail; true/false; positive/negative).</span></span>

![Diagrama en el que se muestran ejemplos de clasificación binaria, como detección de fraudes, mitigación de riesgos y filtrado de aplicaciones](media/binary-classification-examples.png)

<span data-ttu-id="516ab-131">El análisis de opiniones se puede usar para predecir una opinión positiva o negativa de los comentarios del cliente.</span><span class="sxs-lookup"><span data-stu-id="516ab-131">Sentiment analysis can be used to predict positive or negative sentiment of customer feedback.</span></span> <span data-ttu-id="516ab-132">Es un ejemplo de un tipo de clasificación binaria.</span><span class="sxs-lookup"><span data-stu-id="516ab-132">It is an example of a binary classification model type.</span></span>

<span data-ttu-id="516ab-133">Si el escenario requiere clasificación en dos categorías, puede usar esta plantilla con un conjunto de datos propio.</span><span class="sxs-lookup"><span data-stu-id="516ab-133">If your scenario requires classification into two categories, you can use this template with your own dataset.</span></span>

#### <a name="predict-a-category-when-there-are-three-or-more-categories"></a><span data-ttu-id="516ab-134">Predecir una categoría (que cuente con tres categorías o más)</span><span class="sxs-lookup"><span data-stu-id="516ab-134">Predict a category (when there are three or more categories)</span></span>

<span data-ttu-id="516ab-135">La clasificación multiclase puede usarse para clasificar los datos en tres o más clases.</span><span class="sxs-lookup"><span data-stu-id="516ab-135">Multiclass classification can be used to categorize data into three or more classes.</span></span>

![Ejemplos de clasificación multiclase que incluyen la clasificación de documentos y productos, el enrutamiento de incidencias de soporte técnico y la priorización de problemas de clientes](media/multiclass-classification-examples.png)

<span data-ttu-id="516ab-137">La clasificación de problemas se puede usar para clasificar problemas de comentarios de clientes (por ejemplo, en GitHub) mediante el título y la descripción del problema.</span><span class="sxs-lookup"><span data-stu-id="516ab-137">Issue classification can be used to categorize customer feedback (for example, on GitHub) issues using the issue title and description.</span></span> <span data-ttu-id="516ab-138">Es un ejemplo del tipo de modelo de clasificación multiclase.</span><span class="sxs-lookup"><span data-stu-id="516ab-138">It is an example of the multi-class classification model type.</span></span>

<span data-ttu-id="516ab-139">Puede usar la plantilla de clasificación de problemas para el escenario si quiere clasificar los datos en tres o más categorías.</span><span class="sxs-lookup"><span data-stu-id="516ab-139">You can use the issue classification template for your scenario if you want to categorize data into three or more categories.</span></span>

#### <a name="predict-a-number"></a><span data-ttu-id="516ab-140">Predecir un número</span><span class="sxs-lookup"><span data-stu-id="516ab-140">Predict a number</span></span>

<span data-ttu-id="516ab-141">La regresión se usa para predecir números.</span><span class="sxs-lookup"><span data-stu-id="516ab-141">Regression is used to predict numbers.</span></span>

![Diagrama en el que se muestran ejemplos de regresión, como la predicción de precios, la previsión de ventas y el mantenimiento predictivo](media/regression-examples.png)

<span data-ttu-id="516ab-143">La predicción de precios puede usarse para predecir los precios de viviendas según la ubicación, el tamaño y otras características del inmueble.</span><span class="sxs-lookup"><span data-stu-id="516ab-143">Price prediction can be used to predict house prices using location, size, and other characteristics of the house.</span></span> <span data-ttu-id="516ab-144">Es un ejemplo de un tipo de modelo de regresión.</span><span class="sxs-lookup"><span data-stu-id="516ab-144">It is an example of a regression model type.</span></span>

<span data-ttu-id="516ab-145">Puede usar la plantilla de predicción de precios para el escenario si quiere predecir un valor numérico con un conjunto de datos propio.</span><span class="sxs-lookup"><span data-stu-id="516ab-145">You can use the price prediction template for your scenario if you want to predict a numerical value with your own dataset.</span></span>

#### <a name="custom-scenario-choose-your-model-type"></a><span data-ttu-id="516ab-146">Escenario personalizado (elija el tipo de modelo)</span><span class="sxs-lookup"><span data-stu-id="516ab-146">Custom scenario (choose your model type)</span></span>

<span data-ttu-id="516ab-147">El escenario personalizado permite elegir manualmente un tipo de modelo.</span><span class="sxs-lookup"><span data-stu-id="516ab-147">The custom scenario allows you to manually choose your model type.</span></span>

## <a name="data"></a><span data-ttu-id="516ab-148">Datos</span><span class="sxs-lookup"><span data-stu-id="516ab-148">Data</span></span>

<span data-ttu-id="516ab-149">Una vez que ha elegido el tipo de modelo, el generador de modelos pide que se proporcione un conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="516ab-149">Once you have chosen your model type, Model Builder asks you to provide a dataset.</span></span> <span data-ttu-id="516ab-150">Los datos se usan para entrenar, evaluar y elegir el mejor modelo para el escenario.</span><span class="sxs-lookup"><span data-stu-id="516ab-150">The data is used to train, evaluate, and choose the best model for your scenario.</span></span>

![Diagrama en el que se muestran los pasos del generador de modelos](media/model-builder-steps.png)

### <a name="choose-the-output-to-predict-label"></a><span data-ttu-id="516ab-152">Selección del resultado que se va a predecir (etiqueta)</span><span class="sxs-lookup"><span data-stu-id="516ab-152">Choose the output to predict (label)</span></span>

<span data-ttu-id="516ab-153">Un conjunto de datos es una tabla de filas de ejemplos de entrenamiento y columnas de atributos.</span><span class="sxs-lookup"><span data-stu-id="516ab-153">A dataset is a table of rows of training examples, and columns of attributes.</span></span> <span data-ttu-id="516ab-154">Cada fila tiene:</span><span class="sxs-lookup"><span data-stu-id="516ab-154">Each row has:</span></span>

- <span data-ttu-id="516ab-155">una **etiqueta** (el atributo que se quiere predecir)</span><span class="sxs-lookup"><span data-stu-id="516ab-155">a **label** (the attribute that you want to predict)</span></span>
- <span data-ttu-id="516ab-156">**características** (atributos que se usan como entradas para predecir la etiqueta).</span><span class="sxs-lookup"><span data-stu-id="516ab-156">**features** (attributes that are used as inputs to predict the label).</span></span>

<span data-ttu-id="516ab-157">En el escenario de predicción del precio de las viviendas, las características podrían ser:</span><span class="sxs-lookup"><span data-stu-id="516ab-157">For the house-price prediction scenario, the features could be:</span></span>

- <span data-ttu-id="516ab-158">los metros cuadrados de la vivienda</span><span class="sxs-lookup"><span data-stu-id="516ab-158">the square footage of the house</span></span>
- <span data-ttu-id="516ab-159">el número de dormitorios y baños</span><span class="sxs-lookup"><span data-stu-id="516ab-159">the number of bedrooms and bathrooms</span></span>
- <span data-ttu-id="516ab-160">el código postal</span><span class="sxs-lookup"><span data-stu-id="516ab-160">the zip code</span></span>

<span data-ttu-id="516ab-161">La etiqueta es el precio histórico de la vivienda para esa fila de valores de metros cuadrados, baños y dormitorios y el código postal.</span><span class="sxs-lookup"><span data-stu-id="516ab-161">The label is the historical house price for that row of square footage, bedroom, and bathroom values and zip code.</span></span>

![Tabla donde se muestran las filas y columnas de datos de precios de viviendas con características que constan de etiquetas de tamaño, habitaciones, código postal y precio](media/model-builder-data.png)

### <a name="example-datasets"></a><span data-ttu-id="516ab-163">Conjuntos de datos de ejemplo</span><span class="sxs-lookup"><span data-stu-id="516ab-163">Example datasets</span></span>

<span data-ttu-id="516ab-164">Si aún no tiene datos propios, pruebe uno de estos conjuntos de datos:</span><span class="sxs-lookup"><span data-stu-id="516ab-164">If you don't have your own data yet, try out one of these datasets:</span></span>

|<span data-ttu-id="516ab-165">Escenario</span><span class="sxs-lookup"><span data-stu-id="516ab-165">Scenario</span></span>|<span data-ttu-id="516ab-166">Tipo de modelo</span><span class="sxs-lookup"><span data-stu-id="516ab-166">Model Type</span></span>|<span data-ttu-id="516ab-167">Datos</span><span class="sxs-lookup"><span data-stu-id="516ab-167">Data</span></span>|<span data-ttu-id="516ab-168">Etiqueta</span><span class="sxs-lookup"><span data-stu-id="516ab-168">Label</span></span>|<span data-ttu-id="516ab-169">Características</span><span class="sxs-lookup"><span data-stu-id="516ab-169">Features</span></span>|
|-|-|-|-|-|
|<span data-ttu-id="516ab-170">Predicción de precios</span><span class="sxs-lookup"><span data-stu-id="516ab-170">Price prediction</span></span>|<span data-ttu-id="516ab-171">regresión</span><span class="sxs-lookup"><span data-stu-id="516ab-171">regression</span></span>|[<span data-ttu-id="516ab-172">datos de carreras de taxi</span><span class="sxs-lookup"><span data-stu-id="516ab-172">taxi fare data</span></span>](https://github.com/dotnet/machinelearning-samples/blob/master/datasets/taxi-fare-train.csv)|<span data-ttu-id="516ab-173">Carrera</span><span class="sxs-lookup"><span data-stu-id="516ab-173">Fare</span></span>|<span data-ttu-id="516ab-174">Tiempo de viaje, distancia</span><span class="sxs-lookup"><span data-stu-id="516ab-174">Trip time, distance</span></span>|
|<span data-ttu-id="516ab-175">Detección de anomalías</span><span class="sxs-lookup"><span data-stu-id="516ab-175">Anomaly detection</span></span>|<span data-ttu-id="516ab-176">clasificación binaria</span><span class="sxs-lookup"><span data-stu-id="516ab-176">binary classification</span></span>|[<span data-ttu-id="516ab-177">datos de ventas de productos</span><span class="sxs-lookup"><span data-stu-id="516ab-177">product sales data</span></span>](https://github.com/dotnet/machinelearning-samples/blob/master/samples/csharp/getting-started/AnomalyDetection_Sales/SpikeDetection/Data/product-sales.csv)|<span data-ttu-id="516ab-178">Ventas de productos</span><span class="sxs-lookup"><span data-stu-id="516ab-178">Product Sales</span></span>|<span data-ttu-id="516ab-179">Mes</span><span class="sxs-lookup"><span data-stu-id="516ab-179">Month</span></span>|
|<span data-ttu-id="516ab-180">análisis de opiniones</span><span class="sxs-lookup"><span data-stu-id="516ab-180">Sentiment analysis</span></span>|<span data-ttu-id="516ab-181">clasificación binaria</span><span class="sxs-lookup"><span data-stu-id="516ab-181">binary classification</span></span>|[<span data-ttu-id="516ab-182">datos de comentarios de sitio web</span><span class="sxs-lookup"><span data-stu-id="516ab-182">website comment data</span></span>](https://raw.githubusercontent.com/dotnet/machinelearning/master/test/data/wikipedia-detox-250-line-data.tsv)|<span data-ttu-id="516ab-183">Etiqueta (0 si la opinión es negativa, 1 si es positiva)</span><span class="sxs-lookup"><span data-stu-id="516ab-183">Label (0 when negative sentiment, 1 when positive)</span></span>|<span data-ttu-id="516ab-184">Comentario, año</span><span class="sxs-lookup"><span data-stu-id="516ab-184">Comment, Year</span></span>|
|<span data-ttu-id="516ab-185">Detección de fraudes</span><span class="sxs-lookup"><span data-stu-id="516ab-185">Fraud detection</span></span>|<span data-ttu-id="516ab-186">clasificación binaria</span><span class="sxs-lookup"><span data-stu-id="516ab-186">binary classification</span></span>|[<span data-ttu-id="516ab-187">datos de tarjetas de crédito</span><span class="sxs-lookup"><span data-stu-id="516ab-187">credit card data</span></span>](https://github.com/dotnet/machinelearning-samples/blob/master/samples/csharp/getting-started/BinaryClassification_CreditCardFraudDetection/CreditCardFraudDetection.Trainer/assets/input/creditcardfraud-dataset.zip)|<span data-ttu-id="516ab-188">Clase (1 si es fraudulenta, en caso contrario, 0)</span><span class="sxs-lookup"><span data-stu-id="516ab-188">Class (1 when fraudulent, 0 otherwise)</span></span>|<span data-ttu-id="516ab-189">Cantidad, V1-V28 (características anónimas)</span><span class="sxs-lookup"><span data-stu-id="516ab-189">Amount, V1-V28 (anonymized features)</span></span>|
|<span data-ttu-id="516ab-190">Clasificación de textos</span><span class="sxs-lookup"><span data-stu-id="516ab-190">Text classification</span></span>|<span data-ttu-id="516ab-191">clasificación multiclase</span><span class="sxs-lookup"><span data-stu-id="516ab-191">multiclass classification</span></span>|[<span data-ttu-id="516ab-192">datos de problemas de GitHub</span><span class="sxs-lookup"><span data-stu-id="516ab-192">GitHub issue data</span></span>](https://github.com/dotnet/machinelearning-samples/blob/master/samples/csharp/end-to-end-apps/MulticlassClassification-GitHubLabeler/GitHubLabeler/Data/corefx-issues-train.tsv)|<span data-ttu-id="516ab-193">Área</span><span class="sxs-lookup"><span data-stu-id="516ab-193">Area</span></span>|<span data-ttu-id="516ab-194">Título, descripción</span><span class="sxs-lookup"><span data-stu-id="516ab-194">Title, Description</span></span>|

## <a name="train"></a><span data-ttu-id="516ab-195">Train</span><span class="sxs-lookup"><span data-stu-id="516ab-195">Train</span></span>

<span data-ttu-id="516ab-196">Una vez que se seleccionan el escenario, los datos y la etiqueta, el Generador de modelos entrena el modelo.</span><span class="sxs-lookup"><span data-stu-id="516ab-196">Once you select your scenario, data, and label, Model Builder trains the model.</span></span>

### <a name="what-is-training"></a><span data-ttu-id="516ab-197">¿Qué es el entrenamiento?</span><span class="sxs-lookup"><span data-stu-id="516ab-197">What is training?</span></span>

<span data-ttu-id="516ab-198">El entrenamiento es un proceso automático mediante el cual el Generador de modelos enseña al modelo a responder a preguntas del escenario.</span><span class="sxs-lookup"><span data-stu-id="516ab-198">Training is an automatic process by which Model Builder teaches your model how to answer questions for your scenario.</span></span> <span data-ttu-id="516ab-199">Una vez entrenado, el modelo puede realizar predicciones con datos de entrada que no ha visto antes.</span><span class="sxs-lookup"><span data-stu-id="516ab-199">Once trained, your model can make predictions with input data that it has not seen before.</span></span> <span data-ttu-id="516ab-200">Por ejemplo, si está prediciendo los precios de la vivienda y se pone en el mercado un nuevo inmueble, puede predecir su precio de venta.</span><span class="sxs-lookup"><span data-stu-id="516ab-200">For example, if you are predicting house prices and a new house comes on the market, you can predict its sale price.</span></span>

<span data-ttu-id="516ab-201">Dado que el Generador de modelos usa aprendizaje automático automatizado (AutoML), no requiere ninguna entrada ni ajuste por parte del usuario durante el entrenamiento.</span><span class="sxs-lookup"><span data-stu-id="516ab-201">Because Model Builder uses automated machine learning (AutoML), it does not require any input or tuning from you during training.</span></span>

## <a name="evaluate"></a><span data-ttu-id="516ab-202">Evaluate</span><span class="sxs-lookup"><span data-stu-id="516ab-202">Evaluate</span></span>

<span data-ttu-id="516ab-203">La evaluación es el proceso de usar el modelo entrenado para realizar predicciones con nuevos datos de prueba y luego medir la calidad de las predicciones.</span><span class="sxs-lookup"><span data-stu-id="516ab-203">Evaluation is the process of using the trained model to make predictions with new test data, and then measuring how good the predictions are.</span></span>

<span data-ttu-id="516ab-204">El Generador de modelos divide los datos de entrenamiento en un conjunto de entrenamiento y un conjunto de prueba.</span><span class="sxs-lookup"><span data-stu-id="516ab-204">Model Builder splits the training data into a training set and a test set.</span></span> <span data-ttu-id="516ab-205">Los datos de entrenamiento (80 %) se usan para entrenar el modelo y los datos de prueba (20 %) se incluyen para evaluar el modelo.</span><span class="sxs-lookup"><span data-stu-id="516ab-205">The training data (80%) is used to train your model and the test data (20%) is held back to evaluate your model.</span></span> <span data-ttu-id="516ab-206">El generador de modelos usa métricas para medir el grado de calidad del modelo.</span><span class="sxs-lookup"><span data-stu-id="516ab-206">Model Builder uses metrics to measure how good the model is.</span></span> <span data-ttu-id="516ab-207">Las métricas específicas que se usan dependen del tipo de modelo.</span><span class="sxs-lookup"><span data-stu-id="516ab-207">The specific metrics used are dependent on the type of model.</span></span> <span data-ttu-id="516ab-208">Para obtener más información, vea [Métricas de evaluación de modelos](resources/metrics.md).</span><span class="sxs-lookup"><span data-stu-id="516ab-208">For more information, see [model evaluation metrics](resources/metrics.md).</span></span>

## <a name="improve"></a><span data-ttu-id="516ab-209">Mejora</span><span class="sxs-lookup"><span data-stu-id="516ab-209">Improve</span></span>

<span data-ttu-id="516ab-210">Si la puntuación de rendimiento del modelo no es tan buena como se quiere que sea, se puede:</span><span class="sxs-lookup"><span data-stu-id="516ab-210">If your model performance score is not as good as you want it to be, you can:</span></span>

- <span data-ttu-id="516ab-211">Entrenar durante más tiempo.</span><span class="sxs-lookup"><span data-stu-id="516ab-211">Train for a longer period of time.</span></span> <span data-ttu-id="516ab-212">Con más tiempo, el motor de aprendizaje automático automatizado prueba más algoritmos y configuraciones.</span><span class="sxs-lookup"><span data-stu-id="516ab-212">With more time, the automated machine learning engine to try more algorithms and settings.</span></span>

- <span data-ttu-id="516ab-213">Agregar más datos.</span><span class="sxs-lookup"><span data-stu-id="516ab-213">Add more data.</span></span> <span data-ttu-id="516ab-214">A veces la cantidad de datos no es suficiente para entrenar un modelo de Machine Learning de alta calidad.</span><span class="sxs-lookup"><span data-stu-id="516ab-214">Sometimes the amount of data is not sufficient to train a high-quality machine learning model.</span></span>

- <span data-ttu-id="516ab-215">Equilibrar los datos.</span><span class="sxs-lookup"><span data-stu-id="516ab-215">Balance your data.</span></span> <span data-ttu-id="516ab-216">En las tareas de clasificación, asegúrese de que el conjunto de entrenamiento esté equilibrado entre las categorías.</span><span class="sxs-lookup"><span data-stu-id="516ab-216">For classification tasks, make sure that the training set is balanced across the categories.</span></span> <span data-ttu-id="516ab-217">Por ejemplo, si tiene cuatro clases de 100 ejemplos de entrenamiento y las dos primeras (etiqueta1 y etiqueta2) se usan para 90 registros, pero las otras dos (etiqueta3 y etiqueta4) solo se usan en los 10 registros restantes, la falta de datos equilibrados puede hacer que el modelo se esfuerce por predecir correctamente etiqueta3 o etiqueta4.</span><span class="sxs-lookup"><span data-stu-id="516ab-217">For example, if you have four classes for 100 training examples, and the two first classes (tag1 and tag2) are used for 90 records, but the other two (tag3 and tag4) are only used on the remaining 10 records, the lack of balanced data may cause your model to struggle to correctly predict tag3 or tag4.</span></span>

## <a name="code"></a><span data-ttu-id="516ab-218">Código</span><span class="sxs-lookup"><span data-stu-id="516ab-218">Code</span></span>

<span data-ttu-id="516ab-219">Después de la fase de evaluación, el Generador de modelos genera un archivo de modelo y el código que se puede usar para agregar el modelo a la aplicación.</span><span class="sxs-lookup"><span data-stu-id="516ab-219">After the evaluation phase, Model Builder outputs a model file, and code that you can use to add the model to your application.</span></span> <span data-ttu-id="516ab-220">Los modelos de ML.NET se guardan como un archivo zip.</span><span class="sxs-lookup"><span data-stu-id="516ab-220">ML.NET models are saved as a zip file.</span></span> <span data-ttu-id="516ab-221">El código para cargar y usar el modelo se agrega como un nuevo proyecto a la solución.</span><span class="sxs-lookup"><span data-stu-id="516ab-221">The code to load and use your model is added as a new project in your solution.</span></span> <span data-ttu-id="516ab-222">El Generador de modelos también agrega una aplicación de consola de ejemplo que se puede ejecutar para ver el modelo en acción.</span><span class="sxs-lookup"><span data-stu-id="516ab-222">Model Builder also adds a sample console app that you can run to see your model in action.</span></span>

<span data-ttu-id="516ab-223">Además, el Generador de modelos produce el código que ha generado el modelo, para que pueda entender los pasos llevados a cabo para generar el modelo.</span><span class="sxs-lookup"><span data-stu-id="516ab-223">In addition, Model Builder outputs the code that generated the model, so that you can understand the steps used to generate the model.</span></span> <span data-ttu-id="516ab-224">También puede usar el código de entrenamiento del modelo para volver a entrenar el modelo con nuevos datos.</span><span class="sxs-lookup"><span data-stu-id="516ab-224">You can also use the model training code to retrain your model with new data.</span></span>

## <a name="whats-next"></a><span data-ttu-id="516ab-225">Pasos adicionales</span><span class="sxs-lookup"><span data-stu-id="516ab-225">What's next?</span></span>

<span data-ttu-id="516ab-226">[Instalar](how-to-guides/install-model-builder.md) la extensión de Visual Studio del generador de modelos</span><span class="sxs-lookup"><span data-stu-id="516ab-226">[Install](how-to-guides/install-model-builder.md) the Model Builder Visual Studio extension</span></span>

<span data-ttu-id="516ab-227">Pruebe la [predicción de precios o cualquier escenario de regresión](tutorials/predict-prices-with-model-builder.md)</span><span class="sxs-lookup"><span data-stu-id="516ab-227">Try [price prediction or any regression scenario](tutorials/predict-prices-with-model-builder.md)</span></span>
