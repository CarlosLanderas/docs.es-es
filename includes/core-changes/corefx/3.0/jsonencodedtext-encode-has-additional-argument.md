---
ms.openlocfilehash: 375a6f57a867c2a11fe95753c1085d6d708db2bd
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2019
ms.locfileid: "74568106"
---
### <a name="jsonencodedtextencode-methods-have-an-additional-javascriptencoder-argument"></a><span data-ttu-id="8d44a-101">Los métodos JsonEncodedText.Encode tienen un argumento JavaScriptEncoder adicional</span><span class="sxs-lookup"><span data-stu-id="8d44a-101">JsonEncodedText.Encode methods have an additional JavaScriptEncoder argument</span></span>

<span data-ttu-id="8d44a-102">A partir de la versión preliminar 8 de .NET Core 3.0, los métodos <xref:System.Text.Json.JsonEncodedText.Encode%2A?displayProperty=nameWithType> contienen un argumento <xref:System.Text.Encodings.Web.JavaScriptEncoder> opcional.</span><span class="sxs-lookup"><span data-stu-id="8d44a-102">Starting with .NET Core 3.0 Preview 8, the <xref:System.Text.Json.JsonEncodedText.Encode%2A?displayProperty=nameWithType> methods contain an optional <xref:System.Text.Encodings.Web.JavaScriptEncoder> argument.</span></span>

#### <a name="change-description"></a><span data-ttu-id="8d44a-103">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="8d44a-103">Change description</span></span>

<span data-ttu-id="8d44a-104">.NET Core 3.0 incluye un nuevo tipo, xref:System.Text.Json.JsonEncodedText.Encode%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="8d44a-104">.NET Core 3.0 includes a new type, xref:System.Text.Json.JsonEncodedText.Encode%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="8d44a-105">A partir de la versión preliminar 8 de .NET Core 3.0, la firma de todas las sobrecargas de método <xref:System.Text.Json.JsonEncodedText.Encode%2A?displayProperty=nameWithType> ha cambiado para incluir un parámetro <xref:System.Text.Encodings.Web.JavaScriptEncoder> opcional.</span><span class="sxs-lookup"><span data-stu-id="8d44a-105">Starting with .NET Core 3.0 Preview 8, the signature of all <xref:System.Text.Json.JsonEncodedText.Encode%2A?displayProperty=nameWithType> method overloads has changed to include an optional <xref:System.Text.Encodings.Web.JavaScriptEncoder> parameter.</span></span> <span data-ttu-id="8d44a-106">Este cambio se realizó para permitir un codificador diferente o personalizado.</span><span class="sxs-lookup"><span data-stu-id="8d44a-106">This change was made to allow for a different or custom encoder.</span></span>

<span data-ttu-id="8d44a-107">La firma de los métodos `Encode` en la versión preliminar 7 de .NET Core 3.0 es la siguiente:</span><span class="sxs-lookup"><span data-stu-id="8d44a-107">The signature of the `Encode` methods in .NET Core 3.0 Preview 7 is:</span></span>

```csharp
namespace System.Text.Json
{
    public readonly struct JsonEncodedText
    {
        public static JsonEncodedText Encode(ReadOnlySpan<byte> utf8Value);
        public static JsonEncodedText Encode(ReadOnlySpan<char> value);
        public static JsonEncodedText Encode(string value);
    }
}
```

<span data-ttu-id="8d44a-108">La firma de los mismos métodos `Encode` en la versión preliminar 8 de .NET Core 3.0 y versiones posteriores es:</span><span class="sxs-lookup"><span data-stu-id="8d44a-108">The signature of the same `Encode` methods in .NET Core 3.0 Preview 8 and later versions is:</span></span>

```csharp
namespace System.Text.Json
{
    public readonly struct JsonEncodedText
    {
        public static JsonEncodedText Encode(ReadOnlySpan<byte> utf8Value, JavaScriptEncoder encoder = null);
        public static JsonEncodedText Encode(ReadOnlySpan<char> value, JavaScriptEncoder encoder = null);
        public static JsonEncodedText Encode(string value, JavaScriptEncoder encoder = null);
    }
}
```

#### <a name="version-introduced"></a><span data-ttu-id="8d44a-109">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="8d44a-109">Version introduced</span></span>

<span data-ttu-id="8d44a-110">.NET Core 3.0 (versión preliminar 8)</span><span class="sxs-lookup"><span data-stu-id="8d44a-110">.NET Core 3.0 Preview 8</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="8d44a-111">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="8d44a-111">Recommended action</span></span>

<span data-ttu-id="8d44a-112">Se trata solo de un cambio importante de archivo binario; si se vuelve a compilar con la versión preliminar 8 de .NET Core 3.0 o una versión posterior, se solucionarán los problemas en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="8d44a-112">This is a binary breaking change only; a recompile against .NET Core 3.0 Preview 8 or a later version will fix any runtime issues.</span></span>

#### <a name="category"></a><span data-ttu-id="8d44a-113">Categoría</span><span class="sxs-lookup"><span data-stu-id="8d44a-113">Category</span></span>

<span data-ttu-id="8d44a-114">CoreFX</span><span class="sxs-lookup"><span data-stu-id="8d44a-114">CoreFx</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="8d44a-115">API afectadas</span><span class="sxs-lookup"><span data-stu-id="8d44a-115">Affected APIs</span></span>

<xref:System.Text.Json.JsonEncodedText.Encode(System.ReadOnlySpan%7BSystem.Byte%7D,System.Text.Encodings.Web.JavaScriptEncoder)?displayProperty=nameWithType>
<xref:System.Text.Json.JsonEncodedText.Encode(System.ReadOnlySpan%7BSystem.Char%7D,System.Text.Encodings.Web.JavaScriptEncoder)?displayProperty=nameWithType>
<xref:System.Text.Json.JsonEncodedText.Encode(System.String,System.Text.Encodings.Web.JavaScriptEncoder)?displayProperty=nameWithType>

<!--

### Affected APIs

- `M:System.Text.Json.JsonEncodedText.Encode(System.ReadOnlySpan{System.Byte},System.Text.Encodings.Web.JavaScriptEncoder)`
- `M:System.Text.Json.JsonEncodedText.Encode(System.ReadOnlySpan{System.Char},System.Text.Encodings.Web.JavaScriptEncoder)`
- `M:System.Text.Json.JsonEncodedText.Encode(System.String,System.Text.Encodings.Web.JavaScriptEncoder)`

-->
