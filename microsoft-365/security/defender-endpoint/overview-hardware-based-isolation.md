---
title: 'Windows 10 (基于硬件的) '
ms.reviewer: ''
description: 了解 Windows 10 中基于硬件的隔离如何有助于防御恶意软件。
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.author: macapara
ms.date: 09/07/2018
ms.technology: mde
ms.openlocfilehash: 82841ccdb2a6ad09f43d0bf8d12cb54fe44d6dfe
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/24/2021
ms.locfileid: "51186901"
---
# <a name="hardware-based-isolation-in-windows-10"></a>Windows 10 中基于硬件的隔离

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要体验 Microsoft Defender for Endpoint？ [注册免费试用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


基于硬件的隔离可帮助保护 Windows 10 中的系统完整性，并且与 Microsoft Defender for Endpoint 集成。 

| 功能 | 说明 |
|------------|-------------|
| [Windows Defender 应用程序防护](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-application-guard/md-app-guard-overview.md) | 应用程序防护可保护你的设备免受高级攻击，同时保持你的工作效率。 使用基于硬件的独特隔离方法，目标是将不受信任的网站和 PDF 文档隔离在通过本机 Windows 虚拟机监控程序与操作系统分离的轻型容器内。 如果不受信任的站点或 PDF 文档是恶意的，它仍包含在应用程序防护的安全容器中，使桌面电脑受到保护，并且攻击者不会访问企业数据。 |
| [Windows Defender System Guard](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-system-guard/system-guard-how-hardware-based-root-of-trust-helps-protect-windows.md) | System Guard 在系统启动时和运行后保护和维护系统的完整性，并且使用证明验证系统完整性。  |

