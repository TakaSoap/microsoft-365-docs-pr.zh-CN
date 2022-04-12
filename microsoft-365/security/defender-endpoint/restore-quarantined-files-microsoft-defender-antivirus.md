---
title: 在 Microsoft Defender 防病毒软件中还原隔离的文件
description: 可以还原Microsoft Defender 防病毒隔离的文件和文件夹。
keywords: ''
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 10/19/2021
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.collection: M365-security-compliance
ms.openlocfilehash: 14b6f6812e88a49220230e0e422d5c95f90fe187
ms.sourcegitcommit: 4f56b4b034267b28c7dd165e78ecfb4b5390087d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/12/2022
ms.locfileid: "64790583"
---
# <a name="restore-quarantined-files-in-microsoft-defender-antivirus"></a>在 Microsoft Defender 防病毒软件中还原隔离的文件

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**适用于：**
- [Microsoft Defender for Endpoint 计划 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- Microsoft Defender 防病毒

**平台**
- Windows

如果Microsoft Defender 防病毒配置为检测和修正设备上的威胁，Microsoft Defender 防病毒隔离可疑文件。 如果确定隔离的文件不是威胁，则可以还原它。

1. 打开 **Windows 安全中心**。
2. 选择 **病毒&威胁防护** ，然后单击 **“保护历史记录**”。
3. 在所有最近项目列表中，筛选 **隔离项**。
4. 选择要保留的项，并执行还原等操作。

> [!TIP]
> 还可使用命令提示符从隔离区还原文件。 请参阅 [从隔离区还原文件](/windows/security/threat-protection/microsoft-defender-atp/respond-file-alerts#restore-file-from-quarantine)。 

> [!TIP]
> 如果要查找其他平台的防病毒相关信息，请参阅：
> - [在 macOS 上设置Microsoft Defender for Endpoint首选项](mac-preferences.md)
> - [Mac 上的 Microsoft Defender for Endpoint](microsoft-defender-endpoint-mac.md)
> - [适用于Intune的Microsoft Defender 防病毒的 macOS 防病毒策略设置](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [在 Linux 上设置Microsoft Defender for Endpoint首选项](linux-preferences.md)
> - [Microsoft Defender for Endpoint on Linux](microsoft-defender-endpoint-linux.md)
> - [在 Android 功能上配置 Defender for Endpoint](android-configure.md)
> - [在 iOS 功能上配置Microsoft Defender for Endpoint](ios-configure-features.md)

## <a name="related-articles"></a>相关文章

- [配置扫描修正](configure-remediation-microsoft-defender-antivirus.md)
- [查看扫描结果](review-scan-results-microsoft-defender-antivirus.md)
- [基于文件名、扩展名和文件夹位置配置和验证排除项](configure-extension-file-exclusions-microsoft-defender-antivirus.md)
- [配置和验证进程打开的文件的排除项](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md)
- [在Windows服务器上配置Microsoft Defender 防病毒排除项](configure-server-exclusions-microsoft-defender-antivirus.md)