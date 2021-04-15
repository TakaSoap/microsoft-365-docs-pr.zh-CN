---
title: 在 Microsoft Defender AV 中还原隔离的文件
description: 你可以还原 Microsoft Defender AV 隔离的文件和文件夹。
keywords: ''
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 05/20/2020
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 3de9ddfc0cab12d2eea717c5d6b01e5b70b21213
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/14/2021
ms.locfileid: "51765787"
---
# <a name="restore-quarantined-files-in-microsoft-defender-av"></a>在 Microsoft Defender AV 中还原隔离的文件

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**适用于：**

- [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)

如果 Microsoft Defender 防病毒配置为检测和修正设备上的威胁，Microsoft Defender 防病毒将隔离可疑文件。 如果确定隔离文件不是威胁，可以还原它。

1. 打开 **Windows 安全。**
2. 选择 **病毒&威胁防护，** 然后单击保护 **历史记录**。
3. 在所有最近项的列表中，筛选"**隔离项目"。**
4. 选择要保留的项，然后执行还原等操作。

> [!TIP]
> 还可使用命令提示符从隔离区还原文件。 请参阅 [从隔离区还原文件](/windows/security/threat-protection/microsoft-defender-atp/respond-file-alerts#restore-file-from-quarantine)。 

## <a name="related-articles"></a>相关文章

- [配置扫描修正](configure-remediation-microsoft-defender-antivirus.md)
- [查看扫描结果](review-scan-results-microsoft-defender-antivirus.md)
- [根据文件名、扩展名和文件夹位置配置并验证排除项](configure-extension-file-exclusions-microsoft-defender-antivirus.md)
- [配置并验证进程打开的文件的排除项](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md)
- [在 Windows Server 上配置 Microsoft Defender 防病毒排除项](configure-server-exclusions-microsoft-defender-antivirus.md)