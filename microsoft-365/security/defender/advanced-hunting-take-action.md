---
title: 对搜索中的高级搜寻查询结果Microsoft 365 Defender
description: 在高级搜寻查询结果中快速解决威胁和受影响的资产
keywords: 高级搜寻， 威胁搜寻， 网络威胁搜寻， Microsoft 365 Defender， microsoft 365， m365， 搜索， 查询， 遥测， 采取行动
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 30e3d3ffbe2bf95def8c2c62906b82abb1356213
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60159098"
---
# <a name="take-action-on-advanced-hunting-query-results"></a>对高级搜寻查询结果采取措施

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**适用于：**
- Microsoft 365 Defender
- Microsoft Defender for Endpoint

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

使用强大而全面的操作选项，可以快速包含威胁或解决在高级[](advanced-hunting-overview.md)搜寻中发现的威胁资产。 通过这些选项，您可以：

- 在设备上执行各种操作
- 隔离文件

## <a name="required-permissions"></a>所需权限
若要能够通过高级搜寻采取行动，你需要具有在设备上提交修正操作的权限的 Microsoft Defender for Endpoint [角色](/windows/security/threat-protection/microsoft-defender-atp/user-roles#permission-options)。 如果无法采取措施，请与全局管理员联系，获取以下权限：

*威胁和>的活动漏洞管理 - 修正处理*

## <a name="take-various-actions-on-devices"></a>在设备上执行各种操作
可以在查询结果中的列标识的 `DeviceId` 设备上执行以下操作：

- 隔离受影响的设备以包含感染或阻止攻击以稍后移动
- 收集调查包以获取更多取证信息
- 运行防病毒扫描以使用最新的安全智能更新查找和删除威胁
- 启动自动调查，以检查和修正设备上以及可能受影响的其他设备上的威胁
- 将应用执行限制为仅 Microsoft 签名的可执行文件，阻止通过恶意软件或其他不受信任的可执行文件进行后续威胁活动

若要了解有关如何通过 Microsoft Defender for Endpoint 执行这些响应操作的信息， [请阅读有关设备的响应操作](/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts)。
   
## <a name="quarantine-files"></a>隔离文件
您可以对 *文件部署* 隔离操作，以便遇到文件时自动隔离它们。 选择此操作时，可以选择以下各列以标识查询结果中要隔离的文件：

- `SHA1` — 在大多数高级搜寻表中，这是受录制操作影响的文件的 SHA-1。 例如，如果复制了文件，则这是复制的文件。
- `InitiatingProcessSHA1` — 在大部分高级搜寻表中，这是负责启动录制的操作的文件。 例如，如果启动子进程，这将是父进程。 
- `SHA256` — 这是由列标识的文件的 SHA-256 `SHA1` 等效项。
- `InitiatingProcessSHA256` — 这是由列标识的文件的 SHA-256 `InitiatingProcessSHA1` 等效项。

若要详细了解如何执行隔离操作以及如何还原文件，请阅读 [有关文件的响应操作](/windows/security/threat-protection/microsoft-defender-atp/respond-file-alerts)。

>[!NOTE]
>若要查找并隔离文件，查询结果还应包含作为 `DeviceId` 设备标识符的值。  

## <a name="take-action"></a>采取行动
若要执行任何描述的操作，请在查询结果中选择一个或多个记录，然后选择"**采取操作"。** 向导将指导你完成选择并提交首选操作的过程。

![包含用于检查记录的面板的选定记录的图像。](../../media/mtp-ah/ah-take-actions.png)

## <a name="review-actions-taken"></a>查看已采取的操作
每个操作分别记录在操作中心的"操作[](m365d-action-center.md)中心历史记录" (security.microsoft.com/action-center/history) 。   >   [](https://security.microsoft.com/action-center/history) 转到操作中心以检查每个操作的状态。
 
>[!NOTE]
>本文中的某些表在 Microsoft Defender for Endpoint 中可能不可用。 [打开Microsoft 365 Defender](m365d-enable.md)更多数据源来搜寻威胁。 你可以按照从 Microsoft Defender for Endpoint 迁移高级搜寻查询中的步骤将高级搜寻工作流从 Microsoft Defender for Endpoint 移动到[Microsoft 365 Defender。](advanced-hunting-migrate-from-mde.md)

## <a name="related-topics"></a>相关主题
- [高级搜寻概述](advanced-hunting-overview.md)
- [了解查询语言](advanced-hunting-query-language.md)
- [处理查询结果](advanced-hunting-query-results.md)
- [了解架构](advanced-hunting-schema-tables.md)
- [操作中心概述](m365d-action-center.md)
