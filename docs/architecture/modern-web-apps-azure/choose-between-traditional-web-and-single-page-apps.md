---
title: Elección entre aplicaciones web tradicionales y aplicaciones de página única
description: Obtenga información sobre cómo elegir entre aplicaciones web tradicionales y aplicaciones de página única (SPA) al crear aplicaciones web.
author: ardalis
ms.author: wiwagn
ms.date: 01/30/2019
ms.openlocfilehash: 9ede64249705aba3f22a9663b8a258e41f030aca
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2019
ms.locfileid: "73739458"
---
# <a name="choose-between-traditional-web-apps-and-single-page-apps-spas"></a>Elección entre aplicaciones web tradicionales y aplicaciones de página única (SPA)

> "Ley de Atwood: cualquier aplicación que se pueda escribir en JavaScript, se acabará escribiendo en JavaScript".  
> _\- Jeff Atwood_

En la actualidad hay dos enfoques generales para crear aplicaciones web: aplicaciones web tradicionales que ejecutan la mayor parte de la lógica de aplicación en el servidor y las aplicaciones de página única (SPA) que ejecutan la mayor parte de la lógica de la interfaz de usuario en un explorador web, y se comunican con el servidor web principalmente mediante las API web. También es posible un enfoque híbrido; el más sencillo es hospedar una o más subaplicaciones enriquecidas de tipo SPA dentro de una aplicación web tradicional más grande.

Las aplicaciones web tradicionales se deberían usar cuando:

- Los requisitos del lado cliente de la aplicación son sencillos o incluso de solo lectura.

- La aplicación necesita funcionar en exploradores que no admiten JavaScript.

- El equipo no está familiarizado con las técnicas de desarrollo de JavaScript o TypeScript.

Una SPA se debería usar cuando:

- La aplicación tenga que exponer una interfaz de usuario enriquecida con muchas características.

- El equipo está familiarizado con el desarrollo de JavaScript o TypeScript.

- La aplicación ya tiene que exponer una API para otros clientes (internos o públicos).

Además, los marcos de SPA requieren mayores conocimientos de arquitectura y seguridad. Experimentan una renovación mayor que las aplicaciones web tradicionales debido a las actualizaciones frecuentes y los marcos de trabajo nuevos. La configuración de procesos de compilación e implementación automatizados y el uso de opciones de implementación como contenedores son más difíciles con las SPA que con las aplicaciones web tradicionales.

Las mejoras en la experiencia del usuario que posibilita el modelo de SPA deben ponderarse con estas consideraciones.

## <a name="blazor"></a>Blazor

ASP.NET Core 3.0 presenta un nuevo modelo para crear interfaces de usuario detalladas, interactivas y que admiten composición, denominadas Blazor. El lado servidor Blazor permite a los desarrolladores crear interfaces de usuario con Razor en el servidor y, además, entregar el código al navegador y ejecutarlo en el lado cliente mediante [WebAssembly](https://webassembly.org/). ASP.NET Core 3.0 aún está en desarrollo, pero en la actualización 3.0 de este libro electrónico se incluirá más información sobre dicha tecnología. Para más información sobre Blazor, consulte el artículo de [introducción a Blazor](https://blazor.net/docs/get-started.html).

## <a name="when-to-choose-traditional-web-apps"></a>Casos en los que elegir aplicaciones web tradicionales

A continuación se explican de manera más detallada las razones indicadas anteriormente para elegir aplicaciones web tradicionales.

**La aplicación tiene requisitos simples del lado cliente, posiblemente de solo lectura**

La mayoría de los usuarios usan muchas aplicaciones web principalmente en un modo de solo lectura. Las aplicaciones de solo lectura (o principalmente de solo lectura) tienden a ser mucho más sencillas que las que mantienen y manipulan una gran cantidad de estado. Por ejemplo, es posible que un motor de búsqueda conste de un único punto de entrada con un cuadro de texto y una segunda página para mostrar los resultados de la búsqueda. Los usuarios anónimos pueden realizar solicitudes con facilidad y la necesidad de lógica del lado cliente es escasa. Del mismo modo, una aplicación de acceso público de un blog o sistema de administración de contenido suele estar compuesta principalmente de contenido con poco comportamiento del lado cliente. Estas aplicaciones se compilan fácilmente como aplicaciones web tradicionales basadas en servidor que ejecutan la lógica en el servidor web y representan HTML que se mostrará en el explorador. El hecho de que cada página del sitio tenga su propia dirección URL que se pueda guardar como marcador e indexar por los motores de búsqueda (de forma predeterminada, sin tener que agregar esto como una característica independiente de la aplicación) también es una ventaja clara en este tipo de escenarios.

**La aplicación necesita funcionar en exploradores que no admiten JavaScript**

Las aplicaciones web que tienen que funcionar en exploradores con compatibilidad limitada con JavaScript o sin ella se deben escribir mediante flujos de trabajo de aplicaciones web tradicionales (o al menos que se puedan revertir a este comportamiento). Las SPA requieren JavaScript del lado cliente para poder funcionar; si no está disponible, las SPA no son una buena elección.

**El equipo no está familiarizado con las técnicas de desarrollo de JavaScript o TypeScript**

Si el equipo no está familiarizado con JavaScript o TypeScript, pero sí con el desarrollo de aplicaciones web del lado servidor, probablemente podrán ofrecer una aplicación web tradicional más rápidamente que una SPA. A menos que aprender a programar SPA sea un objetivo o que se necesite la experiencia del usuario que ofrece una SPA, las aplicaciones web tradicionales son una opción más productiva para los equipos que ya están familiarizados con su creación.

## <a name="when-to-choose-spas"></a>Casos en los que elegir SPA

A continuación, se ofrece una explicación más detallada de cuándo se debe elegir un estilo de desarrollo de aplicaciones de página única para la aplicación web.

**La aplicación tiene que exponer una interfaz de usuario enriquecida con muchas características**

Las SPA pueden admitir funciones enriquecidas del lado cliente que no requieran volver a cargar la página cuando los usuarios realicen acciones o naveguen entre las áreas de la aplicación. Las SPA se pueden cargar más rápidamente, recuperar datos en segundo plano y las acciones individuales de los usuarios tienen más capacidad de respuesta ya que las recargas de página completas son poco frecuentes. Las SPA pueden admitir actualizaciones incrementales y guardar formularios o documentos completados parcialmente sin que el usuario tenga que hacer clic en un botón para enviar un formulario. Las SPA pueden admitir comportamientos enriquecidos del lado cliente, como arrastrar y colocar, mucho más fácilmente que las aplicaciones tradicionales. Las SPA se pueden diseñar para ejecutarse en un modo sin conexión y realizar actualizaciones en un modelo del lado cliente que se sincronizan finalmente al servidor una vez que se restablece la conexión. Debe elegir una aplicación de estilo SPA si los requisitos de la aplicación incluyen funcionalidad enriquecida que va más allá de la que ofrecen los formularios HTML típicos.

Tenga en cuenta que, habitualmente, las SPA tienen que implementar características integradas en las aplicaciones web tradicionales, como mostrar una dirección URL significativa en la barra de direcciones que refleje la operación actual (y que permita a los usuarios guardarla como marcador o vínculo profundo para volver a ella). Las SPA también deben permitir a los usuarios hacer clic en los botones Atrás y Adelante del explorador con resultados que no les sorprendan.

**El equipo está familiarizado con el desarrollo de JavaScript o TypeScript**

Para escribir SPA es necesario estar familiarizado con JavaScript o TypeScript y técnicas de programación y bibliotecas del lado cliente. El equipo debería ser competente en la escritura de JavaScript moderno con un marco de SPA como Angular.

> ### <a name="references--spa-frameworks"></a>Referencias: marcos de SPA
>
> - **Angular**  
>   <https://angular.io>
> - **Comparison of JavaScript Frameworks** (Comparación de marcos de JavaScript)  
>   <https://jsreport.io/the-ultimate-guide-to-javascript-frameworks/>

**La aplicación ya tiene que exponer una API para otros clientes (internos o públicos)**

Si ya admite una API web para su uso por otros clientes, crear una implementación de SPA que aproveche estas API puede requerir menos trabajo que reproducir la lógica en el lado de servidor. Las SPA realizan un amplio uso de las API web para consultar y actualizar datos cuando los usuarios interactúan con la aplicación.

## <a name="decision-table--traditional-web-or-spa"></a>Tabla de decisiones: aplicaciones web tradicionales o SPA

En la tabla de decisiones siguiente se resumen algunos de los factores básicos que tener en cuenta al elegir entre una aplicación web tradicional y una SPA.

| **Factor**                                           | **Aplicación web tradicional** | **Aplicación de una sola página** |
| ---------------------------------------------------- | ----------------------- | --------------------------- |
| Familiaridad del equipo necesaria con JavaScript o TypeScript | **Mínima**             | **Obligatoria**                |
| Compatibilidad con exploradores sin scripting                   | **Compatible**           | **No compatible**           |
| Comportamiento mínimo del lado cliente de la aplicación             | **Adecuado**         | **Excesivo**                |
| Requisitos de la interfaz de usuario enriquecidos y complejos            | **Limitados**             | **Adecuados**             |

>[!div class="step-by-step"]
>[Anterior](modern-web-applications-characteristics.md)
>[Siguiente](architectural-principles.md)
