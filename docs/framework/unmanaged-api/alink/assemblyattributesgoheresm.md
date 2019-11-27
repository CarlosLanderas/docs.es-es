---
title: Clase AssemblyAttributesGoHereSM (System. Runtime. CompilerServices)
ms.date: 03/30/2017
api_name:
- System.Runtime.CompilerServices.AssemblyAttributesGoHereSM
api_location:
- mscorlib.dll
api_type:
- Assembly
f1_keywords:
- AssemblyAttributesGoHereSM
helpviewer_keywords:
- AssemblyAttributesGoHereSM type
- Alink API, AssemblyAttributesGoHereSM type
ms.assetid: 4cf9bf39-1527-49e0-a0e9-55e7a018bf66
topic_type:
- apiref
ms.openlocfilehash: 379ba20ebf675bec71e6e5f5bcfc0dc2fbd1f92c
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446598"
---
# <a name="assemblyattributesgoheresm-class"></a><span data-ttu-id="b73e5-102">Clase AssemblyAttributesGoHereSM</span><span class="sxs-lookup"><span data-stu-id="b73e5-102">AssemblyAttributesGoHereSM Class</span></span>

<span data-ttu-id="b73e5-103">ALink lo utiliza como marcador de posición para almacenar información acerca de los atributos personalizados.</span><span class="sxs-lookup"><span data-stu-id="b73e5-103">Used by ALink as a placeholder to store information about custom attributes.</span></span>

## <a name="syntax"></a><span data-ttu-id="b73e5-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b73e5-104">Syntax</span></span>

```csharp
internal sealed class AssemblyAttributesGoHereSM
```

## <a name="remarks"></a><span data-ttu-id="b73e5-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b73e5-105">Remarks</span></span>

<span data-ttu-id="b73e5-106">Las referencias a este tipo se pueden incrustar en archivos .netmodules cuyos orígenes contengan atributos personalizados de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="b73e5-106">References to this type might be embedded inside netmodules whose sources contain assembly custom attributes.</span></span> <span data-ttu-id="b73e5-107">Cuando se genera un manifiesto de ensamblado de uno o más .netmodules que contienen referencias a estos tipos, ALink utiliza la información adjunta a estas referencias para emitir atributos personalizados reales.</span><span class="sxs-lookup"><span data-stu-id="b73e5-107">When building an assembly manifest from one or more netmodules that contain references to these types, ALink uses information attached to these references to emit real custom attributes.</span></span> <span data-ttu-id="b73e5-108">Como tal, nunca se crea una instancia de este tipo y las referencias a él se utilizan únicamente como parte del proceso de compilación, no sirven para ningún propósito en el ensamblado final.</span><span class="sxs-lookup"><span data-stu-id="b73e5-108">As such, this type is never instantiated, and references to it are used only as part of the build process and serve no purpose in the final assembly.</span></span>

<span data-ttu-id="b73e5-109">Las referencias a este tipo indican atributos personalizados que están relacionados con la seguridad y que tienen diversos usos.</span><span class="sxs-lookup"><span data-stu-id="b73e5-109">References to this type indicate custom attributes that are security related and multiple-use.</span></span>

<span data-ttu-id="b73e5-110">Estos tipos se marcan como "Internal" dentro del .NET Framework y se encuentran en el espacio de nombres <xref:System.Runtime.CompilerServices>.</span><span class="sxs-lookup"><span data-stu-id="b73e5-110">These types are marked "internal" within the .NET Framework and are located in the <xref:System.Runtime.CompilerServices> namespace.</span></span>

## <a name="requirements"></a><span data-ttu-id="b73e5-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b73e5-111">Requirements</span></span>

<span data-ttu-id="b73e5-112">mscorlib.dll</span><span class="sxs-lookup"><span data-stu-id="b73e5-112">mscorlib.dll</span></span>

## <a name="see-also"></a><span data-ttu-id="b73e5-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="b73e5-113">See also</span></span>

- [<span data-ttu-id="b73e5-114">AssemblyAttributesGoHere</span><span class="sxs-lookup"><span data-stu-id="b73e5-114">AssemblyAttributesGoHere</span></span>](assemblyattributesgohere.md)
- [<span data-ttu-id="b73e5-115">AssemblyAttributesGoHereM</span><span class="sxs-lookup"><span data-stu-id="b73e5-115">AssemblyAttributesGoHereM</span></span>](assemblyattributesgoherem.md)
- [<span data-ttu-id="b73e5-116">AssemblyAttributesGoHereS</span><span class="sxs-lookup"><span data-stu-id="b73e5-116">AssemblyAttributesGoHereS</span></span>](assemblyattributesgoheres.md)
