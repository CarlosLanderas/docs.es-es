---
title: Convertir horas entre zonas horarias
ms.date: 04/10/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- times [.NET Framework], converting
- time zones [.NET Framework], conversions
- UTC times, converting
- converting times
- local time conversions
ms.assetid: a51e1a3b-c983-4320-b31a-1f9fa3cf824a
ms.openlocfilehash: d0b38523f054598ba6fb1f05a0183bc4ccff2120
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132560"
---
# <a name="converting-times-between-time-zones"></a>Convertir horas entre zonas horarias

Para cualquier aplicación que trabaje con fechas y horas se está volviendo cada vez más importante controlar las diferencias entre zonas horarias. Una aplicación ya no puede suponer que todas las horas se pueden expresar en la hora local, que es el tiempo disponible en la estructura de <xref:System.DateTime>. Por ejemplo, una página web que muestre la hora actual en la zona oriental de los Estados Unidos no tendrá credibilidad para un cliente de Asia oriental. En este tema se explica cómo convertir las horas de una zona horaria a otra, así como cómo convertir valores <xref:System.DateTimeOffset> que tienen un reconocimiento limitado de la zona horaria.

## <a name="converting-to-coordinated-universal-time"></a>Conversión a la hora universal coordinada

La hora universal coordinada (UTC) es un estándar de hora atómica de alta precisión. Las zonas horarias del mundo se expresan como diferencias positivas o negativas con respecto a la hora UTC. Por lo tanto, UTC proporciona un tipo de hora libre o neutra de zona horaria. Se recomienda el uso de la hora UTC cuando importa la portabilidad de la fecha y la hora entre equipos. (Para obtener información detallada y otras prácticas recomendadas que usan fechas y horas, vea [procedimientos recomendados de codificación usando DateTime en el .NET Framework](https://docs.microsoft.com/previous-versions/dotnet/articles/ms973825(v=msdn.10))). La conversión de zonas horarias individuales a UTC facilita las comparaciones de hora.

> [!NOTE]
> También puede serializar una estructura de <xref:System.DateTimeOffset> para representar de forma inequívoca un único punto en el tiempo. Dado que <xref:System.DateTimeOffset> objetos almacenan un valor de fecha y hora junto con su diferencia horaria con respecto a la hora UTC, siempre representan un punto concreto en el tiempo en relación con la hora UTC.

La forma más fácil de convertir una hora a UTC es llamar al método de <xref:System.TimeZoneInfo.ConvertTimeToUtc%28System.DateTime%29?displayProperty=nameWithType> `static` (`Shared` en Visual Basic). La conversión exacta realizada por el método depende del valor de la propiedad <xref:System.DateTime.Kind%2A> del parámetro `dateTime`, como se muestra en la tabla siguiente.

| `DateTime.Kind`            | Conversión                                                                     |
| -------------------------- | ------------------------------------------------------------------------------ |
| `DateTimeKind.Local`       | Convierte la hora local a UTC.                                                    |
| `DateTimeKind.Unspecified` | Supone que el parámetro `dateTime` es la hora local y la convierte a UTC. |
| `DateTimeKind.Utc`         | Devuelve el parámetro `dateTime` sin modificar.                                    |

El código siguiente convierte la hora local actual a UTC y muestra el resultado en la consola.

[!code-csharp[System.TimeZone2.Concepts#6](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#6)]
[!code-vb[System.TimeZone2.Concepts#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#6)]

Si el valor de fecha y hora no representa la hora local o UTC, el método de <xref:System.DateTime.ToUniversalTime%2A> probablemente devolverá un resultado erróneo. Sin embargo, puede utilizar el método <xref:System.TimeZoneInfo.ConvertTimeToUtc%2A?displayProperty=nameWithType> para convertir la fecha y hora de una zona horaria especificada. (Para obtener más información sobre cómo recuperar un objeto <xref:System.TimeZoneInfo> que representa la zona horaria de destino, consulte [Buscar las zonas horarias definidas en un sistema local](../../../docs/standard/datetime/finding-the-time-zones-on-local-system.md)). En el código siguiente se usa el método <xref:System.TimeZoneInfo.ConvertTimeToUtc%2A?displayProperty=nameWithType> para convertir la hora estándar del este a UTC.

[!code-csharp[System.TimeZone2.Concepts#7](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#7)]
[!code-vb[System.TimeZone2.Concepts#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#7)]

Tenga en cuenta que este método produce una <xref:System.ArgumentException> si la propiedad <xref:System.DateTime.Kind%2A> del objeto <xref:System.DateTime> y la zona horaria no coinciden. Se produce un error de coincidencia si se <xref:System.DateTimeKind.Local?displayProperty=nameWithType> la propiedad <xref:System.DateTime.Kind%2A> pero el objeto <xref:System.TimeZoneInfo> no representa la zona horaria local o si la propiedad <xref:System.DateTime.Kind%2A> se <xref:System.DateTimeKind.Utc?displayProperty=nameWithType> pero el objeto <xref:System.TimeZoneInfo> no es igual a <xref:System.TimeZoneInfo.Utc?displayProperty=nameWithType>.

Todos estos métodos toman <xref:System.DateTime> valores como parámetros y devuelven un valor de <xref:System.DateTime>. Para los valores de <xref:System.DateTimeOffset>, la estructura <xref:System.DateTimeOffset> tiene un método de instancia <xref:System.DateTimeOffset.ToUniversalTime%2A> que convierte la fecha y hora de la instancia actual a UTC. En el ejemplo siguiente se llama al método <xref:System.DateTimeOffset.ToUniversalTime%2A> para convertir una hora local y varias otras horas a la hora universal coordinada (UTC).

[!code-csharp[System.DateTimeOffset.Methods#16](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Methods/cs/Methods.cs#16)]
[!code-vb[System.DateTimeOffset.Methods#16](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Methods/vb/Methods.vb#16)]

## <a name="converting-utc-to-a-designated-time-zone"></a>Conversión de una hora UTC a una zona horaria designada

Para convertir la hora UTC a la hora local, consulte la sección "convertir la hora UTC a la hora local" que aparece a continuación. Para convertir la hora UTC a la hora de cualquier zona horaria que designe, llame al método <xref:System.TimeZoneInfo.ConvertTimeFromUtc%2A>. El método toma dos parámetros:

- La hora UTC que se va a convertir. Debe ser un valor <xref:System.DateTime> cuya propiedad <xref:System.DateTime.Kind%2A> esté establecida en `Unspecified` o `Utc`.

- La zona horaria a la que se va a convertir la hora UTC.

El código siguiente convierte la hora UTC a la hora estándar central.

[!code-csharp[System.TimeZone2.Concepts#8](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#8)]
[!code-vb[System.TimeZone2.Concepts#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#8)]

## <a name="converting-utc-to-local-time"></a>Conversión de una hora UTC a la hora local

Para convertir la hora UTC a la hora local, llame al método <xref:System.DateTime.ToLocalTime%2A> del objeto <xref:System.DateTime> cuya hora desee convertir. El comportamiento exacto del método depende del valor de la propiedad <xref:System.DateTime.Kind%2A> del objeto, como se muestra en la tabla siguiente.

| `DateTime.Kind`            | Conversión                                                                               |
| -------------------------- | ---------------------------------------------------------------------------------------- |
| `DateTimeKind.Local`       | Devuelve el valor de <xref:System.DateTime> sin modificar.                                      |
| `DateTimeKind.Unspecified` | Supone que el valor <xref:System.DateTime> es UTC y convierte la hora UTC a la hora local. |
| `DateTimeKind.Utc`         | Convierte el valor de <xref:System.DateTime> en la hora local.                                 |

> [!NOTE]
> El método <xref:System.TimeZone.ToLocalTime%2A?displayProperty=nameWithType> se comporta igual que el método `DateTime.ToLocalTime`. Toma un único parámetro, que es el valor de fecha y hora que se va a convertir.

También puede convertir la hora de cualquier zona horaria designada a hora local mediante el método de <xref:System.TimeZoneInfo.ConvertTime%2A?displayProperty=nameWithType> `static` (`Shared` en Visual Basic). Esta técnica se describe en la sección siguiente.

## <a name="converting-between-any-two-time-zones"></a>Conversión entre dos zonas horarias cualquiera

Puede realizar la conversión entre dos zonas horarias mediante cualquiera de los dos métodos `static` (`Shared` en Visual Basic) siguientes de la clase <xref:System.TimeZoneInfo>:

- <xref:System.TimeZoneInfo.ConvertTime%2A>

  Los parámetros de este método son el valor de fecha y hora que se va a convertir, un objeto `TimeZoneInfo` que representa la zona horaria del valor de fecha y hora, y un objeto `TimeZoneInfo` que representa la zona horaria a la que se va a convertir el valor de fecha y hora.

- <xref:System.TimeZoneInfo.ConvertTimeBySystemTimeZoneId%2A>

  Los parámetros de este método son el valor de fecha y hora que se va a convertir, el identificador de la zona horaria del valor de fecha y hora, y el identificador de la zona horaria en la que se va a convertir el valor de fecha y hora.

Ambos métodos requieren que la propiedad <xref:System.DateTime.Kind%2A> del valor de fecha y hora que se va a convertir y el objeto <xref:System.TimeZoneInfo> o el identificador de zona horaria que representa su zona horaria se correspondan entre sí. De lo contrario, se produce una excepción <xref:System.ArgumentException>. Por ejemplo, si la propiedad `Kind` del valor de fecha y hora es `DateTimeKind.Local`, se produce una excepción si el objeto de `TimeZoneInfo` que se pasa como parámetro al método no es igual a `TimeZoneInfo.Local`. También se produce una excepción si el identificador pasado como un parámetro al método no es igual a `TimeZoneInfo.Local.Id`.

En el ejemplo siguiente se usa el método <xref:System.TimeZoneInfo.ConvertTime%2A> para convertir de la hora estándar de Hawai a la hora local.

[!code-csharp[System.TimeZone2.Concepts#9](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#9)]
[!code-vb[System.TimeZone2.Concepts#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#9)]

## <a name="converting-datetimeoffset-values"></a>Conversión de valores DateTimeOffset

Los valores de fecha y hora representados por objetos <xref:System.DateTimeOffset> no reconocen totalmente la zona horaria porque el objeto se desasocia de su zona horaria en el momento en que se crea la instancia. Pero en muchos casos una aplicación simplemente necesita convertir una fecha y hora basada en dos diferencias horarias diferentes con respecto a la hora UTC en lugar de en la hora en zonas horarias determinadas. Para realizar esta conversión, puede llamar al método <xref:System.DateTimeOffset.ToOffset%2A> de la instancia actual. El parámetro único del método es el desplazamiento del nuevo valor de fecha y hora que el método va a devolver.

Por ejemplo, si la fecha y hora de una solicitud de usuario de una página web se conoce y se serializa como una cadena con el formato MM/dd/aaaa hh: mm:ss zzzz, el siguiente método `ReturnTimeOnServer` convierte este valor de fecha y hora en la fecha y hora del servidor web.

[!code-csharp[System.DateTimeOffset.Conceptual.OffsetConversions#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.OffsetConversions/cs/TimeConversions.cs#1)]
[!code-vb[System.DateTimeOffset.Conceptual.OffsetConversions#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.OffsetConversions/vb/TimeConversions.vb#1)] 

Si se pasa al método la cadena "9/1/2007 5:32:07 -05:00", que representa la fecha y hora de una zona horaria cinco horas anterior a UTC, devuelve 9/1/2007 3:32:07 AM-07:00 para un servidor ubicado en la zona horaria estándar del Pacífico de EE. UU.

La clase <xref:System.TimeZoneInfo> también incluye una sobrecarga del método <xref:System.TimeZoneInfo.ConvertTime%28System.DateTimeOffset%2CSystem.TimeZoneInfo%29?displayProperty=nameWithType> que realiza conversiones de zona horaria con valores <xref:System.DateTimeOffset.ToOffset(System.TimeSpan)>. Los parámetros del método son un valor <xref:System.DateTimeOffset> y una referencia a la zona horaria a la que se va a convertir la hora. La llamada al método devuelve un valor <xref:System.DateTimeOffset>. Por ejemplo, el método `ReturnTimeOnServer` del ejemplo anterior podría volver a escribirse como sigue para llamar al método <xref:System.TimeZoneInfo.ConvertTime%28System.DateTimeOffset%2CSystem.TimeZoneInfo%29>.

[!code-csharp[System.DateTimeOffset.Conceptual.OffsetConversions#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.OffsetConversions/cs/timeconversions2.cs#2)]
[!code-vb[System.DateTimeOffset.Conceptual.OffsetConversions#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.OffsetConversions/vb/TimeConversions2.vb#2)]

## <a name="see-also"></a>Vea también

- <xref:System.TimeZoneInfo>
- [Fechas, horas y zonas horarias](../../../docs/standard/datetime/index.md)
- [Búsqueda de las zonas horarias definidas en un sistema local](../../../docs/standard/datetime/finding-the-time-zones-on-local-system.md)
