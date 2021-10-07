---
title: 在 Microsoft Defender 防病毒软件中还原隔离的文件
description: 你可以还原被用户隔离的文件和Microsoft Defender 防病毒。
keywords: ''
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/23/2021
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.collection: M365-security-compliance
ms.openlocfilehash: 0eed4f8b615ce759cd81385546158232d51c6158
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60168202"
---
# <a name="restore-quarantined-files-in-microsoft-defender-antivirus"></a>在 Microsoft Defender 防病毒软件中还原隔离的文件

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**适用于：**

- [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)

如果Microsoft Defender 防病毒配置为检测和修正设备上的威胁，Microsoft Defender 防病毒隔离可疑文件。 如果确定隔离文件不是威胁，可以还原它。

1. 打开 **Windows 安全中心**。
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
- [在 Microsoft Defender 防病毒 服务器上配置Windows排除项](configure-server-exclusions-microsoft-defender-antivirus.md)