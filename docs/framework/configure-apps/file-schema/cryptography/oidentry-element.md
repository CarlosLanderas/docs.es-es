---
title: <oidEntry> (Elemento)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib/cryptographySettings/oidMap/oidEntry
- http://schemas.microsoft.com/.NetConfiguration/v2.0#oidEntry
helpviewer_keywords:
- <oidEntry> element
- oidEntry element
ms.assetid: 22fb88b0-bf27-489c-9ca0-e65950ac136c
ms.openlocfilehash: 4564cf59e3b6cfbdcd9dca06cd0f966d524834de
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/14/2019
ms.locfileid: "74088548"
---
# <a name="oidentry-element"></a><span data-ttu-id="fd9b8-102">\<elemento > oidEntry</span><span class="sxs-lookup"><span data-stu-id="fd9b8-102">\<oidEntry> Element</span></span>
<span data-ttu-id="fd9b8-103">Asigna un identificador de objeto (OID) ASN.1 a un nombre descriptivo.</span><span class="sxs-lookup"><span data-stu-id="fd9b8-103">Maps an ASN.1 object identifier (OID) to a friendly name.</span></span>  

<span data-ttu-id="fd9b8-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="fd9b8-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="fd9b8-105">&nbsp;&nbsp;[ **\<mscorlib >** ](mscorlib-element-for-cryptography-settings.md)</span><span class="sxs-lookup"><span data-stu-id="fd9b8-105">&nbsp;&nbsp;[**\<mscorlib>**](mscorlib-element-for-cryptography-settings.md)</span></span>\
<span data-ttu-id="fd9b8-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<cryptographySettings >** ](cryptographysettings-element.md)</span><span class="sxs-lookup"><span data-stu-id="fd9b8-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptographySettings>**](cryptographysettings-element.md)</span></span>\
<span data-ttu-id="fd9b8-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<oidMap**](oidmap-element.md) ></span><span class="sxs-lookup"><span data-stu-id="fd9b8-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<oidMap>**](oidmap-element.md)</span></span>\
<span data-ttu-id="fd9b8-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<oidEntry >**</span><span class="sxs-lookup"><span data-stu-id="fd9b8-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<oidEntry>**</span></span>

## <a name="syntax"></a><span data-ttu-id="fd9b8-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fd9b8-109">Syntax</span></span>  
  
```xml  
<oidEntry OID="object identifier number" name="friendly name" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fd9b8-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="fd9b8-110">Attributes and Elements</span></span>  
 <span data-ttu-id="fd9b8-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="fd9b8-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fd9b8-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="fd9b8-112">Attributes</span></span>  
  
|<span data-ttu-id="fd9b8-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="fd9b8-113">Attribute</span></span>|<span data-ttu-id="fd9b8-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="fd9b8-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="fd9b8-115">**OID**</span><span class="sxs-lookup"><span data-stu-id="fd9b8-115">**OID**</span></span>|<span data-ttu-id="fd9b8-116">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="fd9b8-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="fd9b8-117">Especifica el OID ASN. 1 correspondiente al algoritmo implementado por la clase.</span><span class="sxs-lookup"><span data-stu-id="fd9b8-117">Specifies the ASN.1 OID corresponding to the algorithm implemented by your class.</span></span>|  
|<span data-ttu-id="fd9b8-118">**name**</span><span class="sxs-lookup"><span data-stu-id="fd9b8-118">**name**</span></span>|<span data-ttu-id="fd9b8-119">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="fd9b8-119">Required attribute.</span></span><br /><br /> <span data-ttu-id="fd9b8-120">Especifica el valor para el atributo de **nombre** en la etiqueta [\<elemento nameEntry >](nameentry-element.md) .</span><span class="sxs-lookup"><span data-stu-id="fd9b8-120">Specifies the value for the **name** attribute in the [\<nameEntry>](nameentry-element.md) tag.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="fd9b8-121">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="fd9b8-121">Child Elements</span></span>  
 <span data-ttu-id="fd9b8-122">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="fd9b8-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="fd9b8-123">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="fd9b8-123">Parent Elements</span></span>  
  
|<span data-ttu-id="fd9b8-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="fd9b8-124">Element</span></span>|<span data-ttu-id="fd9b8-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="fd9b8-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="fd9b8-126">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="fd9b8-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`cryptographySettings`|<span data-ttu-id="fd9b8-127">Contiene la configuración de criptografía.</span><span class="sxs-lookup"><span data-stu-id="fd9b8-127">Contains cryptography settings.</span></span>|  
|`mscorlib`|<span data-ttu-id="fd9b8-128">Contiene el elemento `cryptographySettings`.</span><span class="sxs-lookup"><span data-stu-id="fd9b8-128">Contains the `cryptographySettings` element.</span></span>|  
|`oidMap`|<span data-ttu-id="fd9b8-129">Contiene las asignaciones de identificador de objetos (OID) ASN. 1 a las clases.</span><span class="sxs-lookup"><span data-stu-id="fd9b8-129">Contains ASN.1 object identifier (OID) mappings to classes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fd9b8-130">Comentarios</span><span class="sxs-lookup"><span data-stu-id="fd9b8-130">Remarks</span></span>  
 <span data-ttu-id="fd9b8-131">Los identificadores de objeto ASN. 1 identifican los algoritmos en algunos formatos criptográficos.</span><span class="sxs-lookup"><span data-stu-id="fd9b8-131">ASN.1 object identifiers identify algorithms in some cryptographic formats.</span></span> <span data-ttu-id="fd9b8-132">Asigne identificadores de objeto a nombres descriptivos para los algoritmos que desee identificar.</span><span class="sxs-lookup"><span data-stu-id="fd9b8-132">Map object identifiers to friendly names for the algorithms you want to identify.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fd9b8-133">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="fd9b8-133">Example</span></span>  
 <span data-ttu-id="fd9b8-134">En el ejemplo siguiente se muestra cómo usar el elemento **\<oidEntry >** para asignar un identificador de objeto para el algoritmo hash RIPEMD-160 a una implementación de ese algoritmo hash.</span><span class="sxs-lookup"><span data-stu-id="fd9b8-134">The following example shows how to use the **\<oidEntry>** element to map an object identifier for the RIPEMD-160 hash algorithm to an implementation of that hash algorithm.</span></span>  
  
```xml  
<configuration>  
   <mscorlib>  
      <cryptographySettings>  
         <cryptoNameMapping>  
            <cryptoClasses>  
               <cryptoClass   MyCrypto="MyCryptoClass, MyAssembly  
                  Culture=neutral, PublicKeyToken=a5d015c7d5a0b012,  
                  Version=1.0.0.0"/>  
            </cryptoClasses>  
            <nameEntry name="RIPEMD-160" class="MyCrypto"/>  
         </cryptoNameMapping>  
         <oidMap>  
            <oidEntry OID="1.3.36.3.2.1"   name="MyCryptoClass"/>  
         </oidMap>  
      </cryptographySettings>  
   </mscorlib>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="fd9b8-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="fd9b8-135">See also</span></span>

- [<span data-ttu-id="fd9b8-136">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="fd9b8-136">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="fd9b8-137">Esquema de la configuración de criptografía</span><span class="sxs-lookup"><span data-stu-id="fd9b8-137">Cryptography Settings Schema</span></span>](index.md)
- [<span data-ttu-id="fd9b8-138">Servicios criptográficos</span><span class="sxs-lookup"><span data-stu-id="fd9b8-138">Cryptographic Services</span></span>](../../../../standard/security/cryptographic-services.md)
- [<span data-ttu-id="fd9b8-139">Configurar clases de criptografía</span><span class="sxs-lookup"><span data-stu-id="fd9b8-139">Configuring Cryptography Classes</span></span>](../../configure-cryptography-classes.md)
- [<span data-ttu-id="fd9b8-140">Asignar identificadores de objeto a algoritmos de criptografía</span><span class="sxs-lookup"><span data-stu-id="fd9b8-140">Mapping Object Identifiers to Cryptography Algorithms</span></span>](../../map-object-identifiers-to-cryptography-algorithms.md)
