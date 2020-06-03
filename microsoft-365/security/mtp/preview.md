---
title: Microsoft 威胁防护中的预览功能
description: 了解 Microsoft 365 安全中的新功能
keywords: 预览版、new、m365 security、security、365、功能
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: b0703aa14bee3d14d1c3ff4fe46ea9d72de73ce2
ms.sourcegitcommit: eee4f651bd51d5aedd64e42d02bfed8ccb9be4cd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/02/2020
ms.locfileid: "44515863"
---
# <a name="microsoft-threat-protection-preview-features"></a>Microsoft 威胁防护预览功能

**适用于：**
- Microsoft 威胁防护


Microsoft 威胁防护服务不断更新，以提供新的功能增强功能和功能。

了解 Microsoft 威胁防护预览版本中的新功能，并通过启用预览体验在首次尝试即将推出的功能。

有关新增功能的详细信息，请参阅 [Microsoft 威胁防护中的新增功能](whats-new.md)。

## <a name="turn-on-preview-features"></a>打开预览功能
你将有权访问即将推出的功能，您可以在中提供反馈，以帮助改进功能，使其在功能普遍可用之前获得全面体验。

打开预览体验设置，使其在第一次尝试即将推出的功能中。

1. 在导航窗格中，选择 "**设置**"。

2. 选择 " **Microsoft 威胁防护**"。


3. 选择 "**预览功能**  >  **" "打开预览功能"**。 

3. 选择“**保存**”。

当您看到 "**打开预览功能**" 复选框处于选中状态时，您将知道已经打开了预览功能。 

## <a name="preview-features"></a>预览功能
目前，预览中提供了以下功能和增强功能：

- **[标识和应用程序表](advanced-hunting-schema-tables.md)**—使用高级搜寻架构中的[IdentityLogonEvents](advanced-hunting-identitylogonevents-table.md)、 [IdentityQueryEvents](advanced-hunting-identityqueryevents-table.md)和[AppFileEvents](advanced-hunting-appfileevents-table.md)表深入了解身份验证事件、Active Directory 查询和与应用程序相关的活动。

- **[EmailPostDeliveryEvents 表](advanced-hunting-emailpostdeliveryevents-table.md)**—使用此表可创建[高级搜寻](advanced-hunting-overview.md)查询，以检查在将电子邮件传递到收件人邮箱后对电子邮件所执行的操作。

- **[FileProfile （）函数](advanced-hunting-fileprofile-function.md)**—在你的[高级搜寻](advanced-hunting-overview.md)查询中使用，以合并全面的文件信息。
