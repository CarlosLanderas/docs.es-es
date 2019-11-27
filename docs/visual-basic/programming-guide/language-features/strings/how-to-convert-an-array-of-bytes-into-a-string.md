---
title: 'Cómo: convertir una matriz de bytes en una cadena'
ms.date: 07/20/2015
helpviewer_keywords:
- string conversion [Visual Basic], arrays
- byte arrays [Visual Basic], converting to strings
- examples [Visual Basic], strings
- arrays [Visual Basic], converting to strings
ms.assetid: d0dc8317-9ab3-4324-99f7-3f5788c0e72a
ms.openlocfilehash: 8c1d9d1d2e89390873bc1c3dbb9623f047433a9a
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351986"
---
# <a name="how-to-convert-an-array-of-bytes-into-a-string-in-visual-basic"></a><span data-ttu-id="ba765-102">Cómo: Convertir una matriz de bytes en una cadena en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ba765-102">How to: Convert an Array of Bytes into a String in Visual Basic</span></span>
<span data-ttu-id="ba765-103">En este tema se muestra cómo convertir los bytes de una matriz de bytes en una cadena.</span><span class="sxs-lookup"><span data-stu-id="ba765-103">This topic shows how to convert the bytes from a byte array into a string.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ba765-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ba765-104">Example</span></span>  
 <span data-ttu-id="ba765-105">En este ejemplo se usa el método <xref:System.Text.Encoding.GetString%2A> de la clase de codificación <xref:System.Text.Encoding.Unicode%2A?displayProperty=nameWithType> para convertir todos los bytes de una matriz de bytes en una cadena.</span><span class="sxs-lookup"><span data-stu-id="ba765-105">This example uses the <xref:System.Text.Encoding.GetString%2A> method of the <xref:System.Text.Encoding.Unicode%2A?displayProperty=nameWithType> encoding class to convert all the bytes from a byte array into a string.</span></span>  
  
 [!code-vb[VbVbalrStrings#72](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#72)]  
  
 <span data-ttu-id="ba765-106">Puede elegir entre varias opciones de codificación para convertir una matriz de bytes en una cadena:</span><span class="sxs-lookup"><span data-stu-id="ba765-106">You can choose from several encoding options to convert a byte array into a string:</span></span>  
  
- <span data-ttu-id="ba765-107"><xref:System.Text.Encoding.ASCII%2A?displayProperty=nameWithType>: obtiene una codificación para el juego de caracteres ASCII (7 bits).</span><span class="sxs-lookup"><span data-stu-id="ba765-107"><xref:System.Text.Encoding.ASCII%2A?displayProperty=nameWithType>: Gets an encoding for the ASCII (7-bit) character set.</span></span>  
  
- <span data-ttu-id="ba765-108"><xref:System.Text.Encoding.BigEndianUnicode%2A?displayProperty=nameWithType>: obtiene una codificación para el formato UTF-16 utilizando el orden de bytes big-endian.</span><span class="sxs-lookup"><span data-stu-id="ba765-108"><xref:System.Text.Encoding.BigEndianUnicode%2A?displayProperty=nameWithType>: Gets an encoding for the UTF-16 format using the big-endian byte order.</span></span>  
  
- <span data-ttu-id="ba765-109"><xref:System.Text.Encoding.Default%2A?displayProperty=nameWithType>: obtiene una codificación para la página de códigos ANSI actual del sistema.</span><span class="sxs-lookup"><span data-stu-id="ba765-109"><xref:System.Text.Encoding.Default%2A?displayProperty=nameWithType>: Gets an encoding for the system's current ANSI code page.</span></span>  
  
- <span data-ttu-id="ba765-110"><xref:System.Text.Encoding.Unicode%2A?displayProperty=nameWithType>: obtiene una codificación para el formato UTF-16 utilizando el orden de bytes Little-Endian.</span><span class="sxs-lookup"><span data-stu-id="ba765-110"><xref:System.Text.Encoding.Unicode%2A?displayProperty=nameWithType>: Gets an encoding for the UTF-16 format using the little-endian byte order.</span></span>  
  
- <span data-ttu-id="ba765-111"><xref:System.Text.Encoding.UTF32%2A?displayProperty=nameWithType>: obtiene una codificación para el formato UTF-32 utilizando el orden de bytes Little-Endian.</span><span class="sxs-lookup"><span data-stu-id="ba765-111"><xref:System.Text.Encoding.UTF32%2A?displayProperty=nameWithType>: Gets an encoding for the UTF-32 format using the little-endian byte order.</span></span>  
  
- <span data-ttu-id="ba765-112"><xref:System.Text.Encoding.UTF7%2A?displayProperty=nameWithType>: obtiene una codificación para el formato UTF-7.</span><span class="sxs-lookup"><span data-stu-id="ba765-112"><xref:System.Text.Encoding.UTF7%2A?displayProperty=nameWithType>: Gets an encoding for the UTF-7 format.</span></span>  
  
- <span data-ttu-id="ba765-113"><xref:System.Text.Encoding.UTF8%2A?displayProperty=nameWithType>: obtiene una codificación para el formato UTF-8.</span><span class="sxs-lookup"><span data-stu-id="ba765-113"><xref:System.Text.Encoding.UTF8%2A?displayProperty=nameWithType>: Gets an encoding for the UTF-8 format.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba765-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="ba765-114">See also</span></span>

- <xref:System.Text.Encoding?displayProperty=nameWithType>
- <xref:System.Text.Encoding.GetString%2A>
- [<span data-ttu-id="ba765-115">Cómo: convertir cadenas en una matriz de bytes en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ba765-115">How to: Convert Strings into an Array of Bytes in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/strings/how-to-convert-strings-into-an-array-of-bytes.md)
