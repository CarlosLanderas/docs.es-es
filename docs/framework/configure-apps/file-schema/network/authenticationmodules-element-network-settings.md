---
title: Elemento <authenticationModules> (configuración de red)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#authenticationModules
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/authenticationModules
helpviewer_keywords:
- authenticationModules element
- <authenticationModules> element
ms.assetid: 10fcfaad-82ef-4692-871a-0aec9dfbe75e
ms.openlocfilehash: bacaaf92464a355804a9ea8307f6e6f1caac1f05
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/14/2019
ms.locfileid: "74087609"
---
# <a name="authenticationmodules-element-network-settings"></a><span data-ttu-id="53ff0-102">Elemento \<authenticationModules > (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="53ff0-102">\<authenticationModules> Element (Network Settings)</span></span>
<span data-ttu-id="53ff0-103">Especifica los módulos que se usan para autenticar las solicitudes de red.</span><span class="sxs-lookup"><span data-stu-id="53ff0-103">Specifies modules used to authenticate network requests.</span></span>  

<span data-ttu-id="53ff0-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="53ff0-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="53ff0-105">&nbsp;&nbsp;[ **\<System. net >** ](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="53ff0-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>\
<span data-ttu-id="53ff0-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<authenticationModules >**</span><span class="sxs-lookup"><span data-stu-id="53ff0-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<authenticationModules>**</span></span>

## <a name="syntax"></a><span data-ttu-id="53ff0-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="53ff0-107">Syntax</span></span>  
  
```xml  
<authenticationModules>   
</authenticationModules>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="53ff0-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="53ff0-108">Attributes and Elements</span></span>  
 <span data-ttu-id="53ff0-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="53ff0-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="53ff0-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="53ff0-110">Attributes</span></span>  
 <span data-ttu-id="53ff0-111">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="53ff0-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="53ff0-112">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="53ff0-112">Child Elements</span></span>  
  
|<span data-ttu-id="53ff0-113">**Element**</span><span class="sxs-lookup"><span data-stu-id="53ff0-113">**Element**</span></span>|<span data-ttu-id="53ff0-114">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="53ff0-114">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="53ff0-115">add</span><span class="sxs-lookup"><span data-stu-id="53ff0-115">add</span></span>](add-element-for-authenticationmodules-network-settings.md)|<span data-ttu-id="53ff0-116">Agrega un módulo de autenticación a la aplicación.</span><span class="sxs-lookup"><span data-stu-id="53ff0-116">Adds an authentication module to the application.</span></span>|  
|[<span data-ttu-id="53ff0-117">clear</span><span class="sxs-lookup"><span data-stu-id="53ff0-117">clear</span></span>](clear-element-for-authenticationmodules-network-settings.md)|<span data-ttu-id="53ff0-118">Borra todos los módulos de autenticación de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="53ff0-118">Clears all authentication modules from the application.</span></span>|  
|[<span data-ttu-id="53ff0-119">remove</span><span class="sxs-lookup"><span data-stu-id="53ff0-119">remove</span></span>](remove-element-for-authenticationmodules-network-settings.md)|<span data-ttu-id="53ff0-120">Quita un módulo de autenticación de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="53ff0-120">Removes an authentication module from the application.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="53ff0-121">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="53ff0-121">Parent Elements</span></span>  
  
|<span data-ttu-id="53ff0-122">**Element**</span><span class="sxs-lookup"><span data-stu-id="53ff0-122">**Element**</span></span>|<span data-ttu-id="53ff0-123">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="53ff0-123">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="53ff0-124">system.net</span><span class="sxs-lookup"><span data-stu-id="53ff0-124">system.net</span></span>](system-net-element-network-settings.md)|<span data-ttu-id="53ff0-125">Contiene valores que especifican cómo se conecta .NET Framework a la red.</span><span class="sxs-lookup"><span data-stu-id="53ff0-125">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="53ff0-126">Comentarios</span><span class="sxs-lookup"><span data-stu-id="53ff0-126">Remarks</span></span>  
 <span data-ttu-id="53ff0-127">El elemento `authenticationModule` especifica los módulos de autenticación que llevan a cabo el proceso de autenticación con un servidor.</span><span class="sxs-lookup"><span data-stu-id="53ff0-127">The `authenticationModule` element specifies the authentication modules that conduct the authentication process with a server.</span></span> <span data-ttu-id="53ff0-128">Un módulo de autenticación debe implementar la interfaz <xref:System.Net.IAuthenticationModule>.</span><span class="sxs-lookup"><span data-stu-id="53ff0-128">An authentication module must implement the <xref:System.Net.IAuthenticationModule> interface.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="53ff0-129">Archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="53ff0-129">Configuration Files</span></span>  
 <span data-ttu-id="53ff0-130">Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="53ff0-130">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="53ff0-131">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="53ff0-131">Example</span></span>  
 <span data-ttu-id="53ff0-132">En el ejemplo siguiente se habilita un módulo de autenticación.</span><span class="sxs-lookup"><span data-stu-id="53ff0-132">The following example enables an authentication module.</span></span> <span data-ttu-id="53ff0-133">Debe reemplazar los valores de version y PublicKeyToken por los valores correctos para el módulo especificado.</span><span class="sxs-lookup"><span data-stu-id="53ff0-133">You should replace the values for Version and PublicKeyToken with the correct values for the specified module.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <authenticationModules>  
      <add type="System.Net.DigestClient, System, Version=2.0.3600.0,  
                 Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
    </authenticationModules>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="53ff0-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="53ff0-134">See also</span></span>

- <xref:System.Net.IAuthenticationModule>
- <xref:System.Net.AuthenticationManager>
- [<span data-ttu-id="53ff0-135">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="53ff0-135">Network Settings Schema</span></span>](index.md)
