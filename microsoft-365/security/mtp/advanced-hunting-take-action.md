---
title: 在 Microsoft 365 Defender 中对高级搜寻查询结果采取措施
description: 在高级搜寻查询结果中快速解决威胁和受影响的资产
keywords: 高级搜寻， 威胁搜寻， 网络威胁搜寻， Microsoft 威胁防护， microsoft 365， mtp， m365， 搜索， 查询， 遥测， 采取行动
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 9e8ad544cfe17d0d8e5c895e208b42ec56555565
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932174"
---
# <a name="take-action-on-advanced-hunting-query-results"></a>对高级搜寻查询结果采取措施

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**适用于：**
- Microsoft 365 Defender

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

可以使用强大而全面的操作选项快速包含威胁或解决在高级搜寻[](advanced-hunting-overview.md)中发现的威胁或遭到入侵的资产。 通过这些选项，您可以：

- 在设备上执行各种操作
- 隔离文件

## <a name="required-permissions"></a>所需权限
若要能够通过高级搜寻来采取措施，你需要具有在设备上提交修正操作的权限的 Microsoft Defender for Endpoint [角色](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles#permission-options)。 如果无法采取措施，请与全局管理员联系，获取以下权限：

*威胁和>管理的活动修正操作 - 修正处理*

## <a name="take-various-actions-on-devices"></a>在设备上执行各种操作
可以在查询结果中的列标识的 `DeviceId` 设备上执行以下操作：

- 隔离受影响的设备以包含感染或阻止攻击以其他方式移动
- 收集调查包以获取更多取证信息
- 运行防病毒扫描以使用最新的安全智能更新查找和删除威胁
- 启动自动调查，以检查和修正设备上以及可能受影响的其他设备上的威胁
- 将应用执行限制为仅 Microsoft 签名的可执行文件，阻止通过恶意软件或其他不受信任的可执行文件进行后续威胁活动

若要了解有关这些响应操作如何通过 Microsoft Defender for Endpoint 执行，请阅读 [有关设备上响应操作的信息](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts)。
   
## <a name="quarantine-files"></a>隔离文件
您可以对 *文件部署隔离* 操作，以便遇到文件时自动隔离这些文件。 选择此操作时，可以选择以下列以标识查询结果中要隔离的文件：

- `SHA1` — 在最高级搜寻表中，这是受录制操作影响的文件的 SHA-1。 例如，如果复制了文件，则这是复制的文件。
- `InitiatingProcessSHA1` — 在大部分高级搜寻表中，这是负责启动所记录操作的文件。 例如，如果启动子进程，这将是父进程。 
- `SHA256` — 这是由列标识的文件的 SHA-256 `SHA1` 等效项。
- `InitiatingProcessSHA256` — 这是由列标识的文件的 SHA-256 `InitiatingProcessSHA1` 等效项。

若要详细了解如何执行隔离操作以及如何还原文件，请阅读[有关文件的响应操作。](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-file-alerts)

>[!NOTE]
>若要查找并隔离文件，查询结果还应包括值 `DeviceId` 作为设备标识符。  

## <a name="take-action"></a>采取措施
若要执行上述任何操作，请在查询结果中选择一条或多条记录，然后选择 **"采取操作"。** 向导将指导你完成选择并提交首选操作的过程。

![包含用于检查记录的面板的选定记录的图像](../../media/mtp-ah/ah-take-actions.png)

## <a name="review-actions-taken"></a>查看已采取的操作
每个操作分别记录在操作中心的"操作[](mtp-action-center.md)中心历史记录  >  " (security.microsoft.com/action-center/history) 。 [](https://security.microsoft.com/action-center/history) 转到操作中心以检查每个操作的状态。
 
## <a name="related-topics"></a>相关主题
- [高级搜寻概述](advanced-hunting-overview.md)
- [了解查询语言](advanced-hunting-query-language.md)
- [处理查询结果](advanced-hunting-query-results.md)
- [了解架构](advanced-hunting-schema-tables.md)
- [操作中心概述](mtp-action-center.md)
