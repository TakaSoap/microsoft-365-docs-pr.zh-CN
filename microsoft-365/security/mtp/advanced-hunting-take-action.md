---
title: 对 Microsoft 365 Defender 中的高级搜寻查询结果执行操作
description: 快速解决高级搜寻查询结果中的威胁和受影响资产
keywords: 高级搜索、威胁搜寻、网络威胁搜寻、microsoft 威胁防护、microsoft 365、mtp、m365、搜索、查询、遥测、执行操作
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: 506af82ec08ad6cd8dbeece5c1c2741e09e4817a
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2020
ms.locfileid: "48842460"
---
# <a name="take-action-on-advanced-hunting-query-results"></a>对高级搜寻查询结果执行操作

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**适用于：**
- Microsoft 365 Defender

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

您可以使用强大而全面的操作选项快速包含您在 [高级](advanced-hunting-overview.md) 搜索中找到的威胁或地址已泄露资产。 使用这些选项，您可以执行以下操作：

- 对设备执行各种操作
- 隔离文件

## <a name="required-permissions"></a>所需权限
若要能够通过高级搜索执行操作，您需要在 Microsoft Defender for Endpoint 中具有一个角色，在 [设备上具有提交修正操作的权限](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles#permission-options)。 如果无法执行此操作，请联系全局管理员了解获取以下权限：

*> 威胁和漏洞管理的活动修正操作-修正处理*

## <a name="take-various-actions-on-devices"></a>对设备执行各种操作
您可以对由查询结果中的列标识的设备执行以下操作 `DeviceId` ：

- 隔离受影响的设备以包含感染或阻止攻击横向移动
- 收集调查包以获取更多的取证信息
- 运行防病毒扫描，以使用最新的安全智能更新查找并删除威胁
- 启动自动调查以检查和修正设备上可能受影响的其他设备上的威胁
- 仅将应用程序执行限制为 Microsoft 签名的可执行文件，从而通过恶意软件或其他不受信任的可执行文件阻止后续威胁活动

若要了解有关如何通过 Microsoft Defender for Endpoint 执行这些响应操作的详细信息，请 [阅读有关设备的响应操作的信息](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts)。
   
## <a name="quarantine-files"></a>隔离文件
您可以对文件部署 *隔离* 操作，以便在遇到时自动隔离这些文件。 选择此操作时，可以在下列各列之间进行选择，以确定要隔离的查询结果中的哪些文件：

- `SHA1` —在大多数高级搜寻表中，这是受录制操作影响的文件的 SHA-1。 例如，如果复制了文件，则该文件是复制的文件。
- `InitiatingProcessSHA1` —在大多数高级搜寻表中，这是负责启动录制的操作的文件。 例如，如果已启动子进程，则为父进程。 
- `SHA256` —这是与列所标识文件的 SHA-256 等效项 `SHA1` 。
- `InitiatingProcessSHA256` —这是与列所标识文件的 SHA-256 等效项 `InitiatingProcessSHA1` 。

若要了解有关如何执行隔离操作和还原文件的详细信息，请 [阅读有关文件的响应操作的信息](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-file-alerts)。

>[!NOTE]
>若要查找文件并将其隔离，查询结果还应将 `DeviceId` 值作为设备标识符包括在内。  

## <a name="take-action"></a>执行操作
若要执行任何所述的操作，请在查询结果中选择一个或多个记录，然后选择 " **采取操作** "。 向导将指导您完成选择和提交首选操作的过程。

![包含用于检查记录的面板的选定记录的图像](../../media/mtp-ah/ah-take-actions.png)

## <a name="review-actions-taken"></a>查看所执行的操作
每个操作都将在操作 [中心](mtp-action-center.md)中单独记录在 " **操作中心**  >  **历史记录** ( [security.microsoft.com/action-center/history](https://security.microsoft.com/action-center/history) ") "下。 转到操作中心以检查每个操作的状态。
 
## <a name="related-topics"></a>相关主题
- [高级搜寻概述](advanced-hunting-overview.md)
- [了解查询语言](advanced-hunting-query-language.md)
- [处理查询结果](advanced-hunting-query-results.md)
- [了解架构](advanced-hunting-schema-tables.md)
- [操作中心概述](mtp-action-center.md)
