---
title: 部署和启用 Microsoft Defender 防病毒软件
description: 部署Microsoft Defender 防病毒以使用Microsoft Intune、Microsoft Endpoint Configuration Manager、组策略、PowerShell cmdlet 或 WMI 保护终结点。
keywords: 部署、启用、Microsoft Defender 防病毒
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
ms.topic: conceptual
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.collection: m365-security-compliance
ms.openlocfilehash: fe84fa4df958ea42304531defc4810edf332b3a3
ms.sourcegitcommit: 4f56b4b034267b28c7dd165e78ecfb4b5390087d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/12/2022
ms.locfileid: "64790517"
---
# <a name="deploy-and-enable-microsoft-defender-antivirus"></a>部署和启用 Microsoft Defender 防病毒软件

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**适用于：**

- [Microsoft Defender for Endpoint 计划 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- Microsoft Defender 防病毒

**平台**
- Windows

根据所使用的管理工具，可能需要专门启用或配置Microsoft Defender 防病毒保护。 

有关如何使用 [Microsoft Intune、Microsoft Endpoint Configuration Manager、组策略、](deploy-manage-report-microsoft-defender-antivirus.md#ref2)Active Directory 启用保护的说明，请参阅有关Microsoft Defender 防病毒的部署、管理和报告表，Microsoft Azure、PowerShell cmdlet 和 Windows 管理指令 (WMI) 。

某些方案需要有关如何成功部署或配置Microsoft Defender 防病毒保护的更多指导，例如虚拟桌面基础结构 (VDI) 环境。

本部分的其余文章提供端到端建议和最佳做法，用于[在 VDI 或远程桌面服务 (RDS) 环境中) 的虚拟机 (VM 上设置Microsoft Defender 防病毒](deployment-vdi-microsoft-defender-antivirus.md)。

## <a name="related-articles"></a>相关文章

- [Windows 10 中的 Microsoft Defender 防病毒](microsoft-defender-antivirus-in-windows-10.md)
- [部署、管理更新并报告Microsoft Defender 防病毒](deploy-manage-report-microsoft-defender-antivirus.md)
- [虚拟桌面基础结构 （VDI） 环境中 Microsoft Defender 防病毒软件的部署指南](deployment-vdi-microsoft-defender-antivirus.md)

> [!TIP]
> 如果要查找其他平台的防病毒相关信息，请参阅：
> - [在 macOS 上设置Microsoft Defender for Endpoint首选项](mac-preferences.md)
> - [Mac 上的 Microsoft Defender for Endpoint](microsoft-defender-endpoint-mac.md)
> - [适用于Intune的Microsoft Defender 防病毒的 macOS 防病毒策略设置](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [在 Linux 上设置Microsoft Defender for Endpoint首选项](linux-preferences.md)
> - [Microsoft Defender for Endpoint on Linux](microsoft-defender-endpoint-linux.md)
> - [在 Android 功能上配置 Defender for Endpoint](android-configure.md)
> - [在 iOS 功能上配置Microsoft Defender for Endpoint](ios-configure-features.md)