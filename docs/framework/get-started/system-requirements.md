---
title: Requisitos de sistema de .NET Framework
description: Averigüe cuáles son los requisitos de hardware, sistema operativo y software para instalar .NET Framework 4.5 y versiones posteriores.
ms.custom: updateeachrelease
ms.date: 04/18/2019
helpviewer_keywords:
- software requirements
- .NET Framework, system requirements
- system requirements
- operating systems supported
- hardware requirements
ms.assetid: 298275e2-da1d-4618-9f74-6a3567832350
ms.openlocfilehash: f2c22f13f74698b8cbd1474b331d65dcedfa4889
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73114563"
---
# <a name="net-framework-system-requirements"></a>Requisitos de sistema de .NET Framework

En las tablas de este tema se indican los requisitos de hardware, sistema operativo y software de las siguientes versiones de .NET Framework:

- .NET Framework 4.5 y sus versiones secundarias (4.5.1 y 4.5.2).
- .NET Framework 4.6 y sus versiones secundarias (4.6.1 y 4.6.2).
- .NET Framework 4.7 y sus versiones secundarias (4.7.1 y 4.7.2).
- .NET Framework 4.8

Para información sobre las versiones de .NET Framework anteriores a .NET Framework 4.5, vea [Versiones y dependencias de .NET Framework](../migration-guide/versions-and-dependencies.md).

Los entornos de desarrollo que permiten desarrollar aplicaciones para .NET Framework tienen otros requisitos diferentes.

[!INCLUDE[net-framework-4-versions](../../../includes/net-framework-4x-versions.md)]

Para obtener información y vínculos de descarga, vea [Instalar .NET Framework para desarrolladores](../install/guide-for-developers.md).

Para obtener información sobre el ciclo de vida de soporte técnico de las versiones de .NET Framework, vea [Microsoft Support Lifecycle](https://support.microsoft.com/lifecycle/search?sort=PN&alpha=Microsoft%20.NET%20Framework&Filter=FilterNO).

## <a name="hardware-requirements"></a>Requisitos de hardware

|                          |        |
| ------------------------ | ------ |
| **Procesador**            | 1 GHz  |
| **RAM**                  | 512 MB |
| **Espacio en disco (mínimo)** |        |
| 32 bits                   | 4.5 GB |
| 64 bits                   | 4.5 GB |

## <a name="installation-requirements"></a>Requisitos de instalación

Necesita tener privilegios de administrador para poder instalar .NET Framework. Si no tiene derechos de administrador en el equipo en el que quiere instalar .NET Framework, póngase en contacto con el administrador de red.

## <a name="supported-client-operating-systems"></a>Sistemas operativos de cliente admitidos

| Sistema operativo | Ediciones compatibles | Preinstalado con el sistema operativo | Instalable por separado |
| ---------------- | ------------------ | ------------------------ | ---------------------- |
| Actualización del 10 de mayo de 2019 de Windows 2019 | 32 bits y 64 bits | .NET Framework 4.8 | -- |
| Actualización de octubre de 2018 de Windows 10 | 32 bits y 64 bits | .NET Framework 4.7.2 | .NET Framework 4.8 |
| Actualización de abril de 2018 de Windows 10 | 32 bits y 64 bits | .NET Framework 4.7.2 |.NET Framework 4.8|
| Windows 10 Fall Creators Update | 32 bits y 64 bits | .NET Framework 4.7.1 | .NET Framework 4.7.2<br/><br/>.NET Framework 4.8 |
| Windows 10 Creators Update | 32 bits y 64 bits | .NET Framework 4.7 | .NET Framework 4.7.1<br/><br/>.NET Framework 4.7.2<br/><br/>.NET Framework 4.8 |
| Actualización de aniversario de Windows 10 | 32 bits y 64 bits | .NET Framework 4.6.2 |.NET Framework 4.7<br/><br/>.NET Framework 4.7.1<br/><br/>.NET Framework 4.7.2<br/><br/>.NET Framework 4.8  |
| Actualización de noviembre de Windows 10 | 32 bits y 64 bits | .NET Framework 4.6.1 | .NET Framework 4.6.2 |
| Windows 10 | 32 bits y 64 bits | .NET Framework 4.6 | .NET Framework 4.6.1 <br/><br/> .NET Framework 4.6.2 |
| [!INCLUDE[win81](../../../includes/win81-md.md)] | 32 bits, 64 bits y ARM | .NET Framework 4.5.1 | .NET Framework 4.5.2<br /><br /> .NET Framework 4.6<br /><br /> .NET Framework 4.6.1<br /><br /> .NET Framework 4.6.2<br /><br />.NET Framework 4.7<br/><br/>.NET Framework 4.7.1<br/><br/>.NET Framework 4.7.2<br/><br/>.NET Framework 4.8 |
| [!INCLUDE[win8](../../../includes/win8-md.md)] | 32 bits, 64 bits y ARM | .NET Framework 4.5 | .NET Framework 4.5.1<br /><br />.NET Framework 4.5.2<br /><br /> .NET Framework 4.6<br /><br /> .NET Framework 4.6.1 |
| Windows 7 SP1|32 bits y 64 bits | -- | .NET Framework 4<br /><br /> .NET Framework 4.5<br /><br /> .NET Framework 4.5.1<br /><br /> .NET Framework 4.5.2<br /><br /> .NET Framework 4.6<br /><br /> .NET Framework 4.6.1<br /><br /> .NET Framework 4.6.2<br /><br />.NET Framework 4.7<br/><br/>.NET Framework 4.7.1<br/><br/>.NET Framework 4.7.2<br/><br/>.NET Framework 4.8 |
| Windows Vista SP2|32 bits y 64 bits | -- | .NET Framework 4<br /><br /> .NET Framework 4.5<br /><br /> .NET Framework 4.5.1<br /><br /> .NET Framework 4.5.2<br /><br /> .NET Framework 4.6 |
| Windows XP |32 bits y 64 bits | -- | .NET Framework 4 |

 **Notas:**

- Para sistemas de Windows 7, tenga en cuenta que .NET Framework requiere Windows 7 SP1. Si usa Windows 7 y aún no ha instalado Service Pack 1, debe hacerlo antes de instalar .NET Framework.

- .NET Framework 4.5 se admite en el Entorno de preinstalación de Windows (Windows PE). No todas las características se admiten en Windows PE.

- .NET Framework 4 también es compatible con la plataforma IA64.

- Para todas las plataformas, se recomienda actualizar al último Service Pack de Windows e instalar las actualizaciones críticas disponibles del [sitio web de Windows Update](https://go.microsoft.com/fwlink/?LinkId=168461) para garantizar la máxima compatibilidad y seguridad.

- En sistemas operativos de 64 bits, .NET Framework admite WOW64 (procesamiento de 32 bits en un equipo de 64 bits) y el procesamiento nativo de 64 bits.

## <a name="supported-server-operating-systems"></a>Sistemas operativos de servidor admitidos

| Sistema operativo | Ediciones compatibles | Preinstalado con el sistema operativo | Instalable por separado |
| ---------------- | ------------------ | ------------------------ | ---------------------- |
| Windows Server 2019 | 64 bits | .NET Framework 4.7.2 | .NET Framework 4.8 |
| Windows Server, versión 1809 | 64 bits | .NET Framework 4.7.2 | .NET Framework 4.8 |
| Windows Server, versión 1803 | 64 bits | .NET Framework 4.7.2 | .NET Framework 4.8 |
| Windows Server, versión 1709 | 64 bits | .NET Framework 4.7.1 | .NET Framework 4.7.2|
| Windows Server 2016 | 64 bits | .NET Framework 4.6.2 | .NET Framework 4.7<br/><br/> .NET Framework 4.7.1<br/><br/>.NET Framework 4.7.2<br/><br/>.NET Framework 4.8 |
| Windows Server 2012 R2 | 64 bits | .NET Framework 4.5.1 | .NET Framework 4.5.2<br /><br /> .NET Framework 4.6<br /><br /> .NET Framework 4.6.1<br /><br /> .NET Framework 4.6.2<br /><br />.NET Framework 4.7<br/><br/> .NET Framework 4.7.1<br/><br/>.NET Framework 4.7.2<br/><br/>.NET Framework 4.8 |
| Windows Server 2012 (edición de 64 bits) | 64 bits| .NET Framework 4.5 | .NET Framework 4.5.1<br /><br /> .NET Framework 4.5.2<br /><br /> .NET Framework 4.6<br /><br /> .NET Framework 4.6.1<br /><br /> .NET Framework 4.6.2<br /><br />.NET Framework 4.7<br/><br/>.NET Framework 4.7.1<br/><br/>.NET Framework 4.7.2<br/><br/>.NET Framework 4.8 |
| Windows Server 2008 R2 SP1|64 bits | -- | .NET Framework 4<br /><br /> .NET Framework 4.5<br /><br /> .NET Framework 4.5.1<br /><br /> .NET Framework 4.5.2<br /><br /> .NET Framework 4.6<br /><br /> .NET Framework 4.6.1<br /><br /> .NET Framework 4.6.2<br /><br />.NET Framework 4.7<br/><br/>.NET Framework 4.7.1<br/><br/>.NET Framework 4.7.2<br/><br/>.NET Framework 4.8 |
| Windows Server 2008 SP2|32 bits y 64 bits | -- | .NET Framework 4<br /><br /> .NET Framework 4.5<br /><br /> .NET Framework 4.5.1<br /><br /> .NET Framework 4.5.2<br /><br /> .NET Framework 4.6 |

 **Notas:**

- [!INCLUDE[winserver8](../../../includes/winserver8-md.md)] incluye .NET Framework 4.5, por lo que no tendrá que instalarlo por separado. De forma similar, [!INCLUDE[winblue_server_2](../../../includes/winblue-server-2-md.md)] incluye .NET Framework 4.5.1.

- .NET Framework. tiene compatibilidad limitada con el rol Server Core con Windows Server 2008 R2 SP1 o versiones posteriores. Vea [Server Core .NET Functionality](https://docs.microsoft.com/previous-versions//dd745015(v=vs.85)) (Funcionalidad de .NET en Server Core) para obtener una lista de las API no compatibles.

- .NET Framework no se admite en Windows Server 2008 R2 for Itanium-Based Systems.

- En Windows Server 2008 SP2, .NET Framework no se admite en el rol Server Core.

- Para todas las plataformas, se recomienda instalar el último Service Pack de Windows y las actualizaciones críticas disponibles del [sitio web de Windows Update](https://go.microsoft.com/fwlink/?LinkId=168461) para garantizar la máxima compatibilidad y seguridad. La instalación del último Service Pack de Windows puede ser necesaria en algunos sistemas operativos.

- En sistemas operativos de 64 bits, .NET Framework admite WOW64 (procesamiento de 32 bits en un equipo de 64 bits) y el procesamiento nativo de 64 bits.

## <a name="see-also"></a>Vea también

- [Guía de instalación](../install/index.md)
- [Introducción](index.md)
- [Solución de problemas en instalaciones y desinstalaciones bloqueadas de .NET Framework](../install/troubleshoot-blocked-installations-and-uninstallations.md)
