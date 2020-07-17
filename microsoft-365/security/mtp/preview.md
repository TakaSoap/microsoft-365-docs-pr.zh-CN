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
ms.openlocfilehash: 45bc42e825c55ca228b13e8d308f9a1384301d07
ms.sourcegitcommit: 11218af1d792af297b4280ca5975d139d2bbe350
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/06/2020
ms.locfileid: "45048263"
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

- **["门户架构参考"](advanced-hunting-schema-tables.md#get-schema-information-in-the-security-center)** —有关安全中心中直接使用的架构表的信息。 除了表和列说明之外，此参考还提供有关受支持的事件类型（ `ActionType` 值）和示例查询的信息。  

- **[标识和应用程序表](advanced-hunting-schema-tables.md)**—使用高级搜寻架构中的[IdentityLogonEvents](advanced-hunting-identitylogonevents-table.md)、 [IdentityQueryEvents](advanced-hunting-identityqueryevents-table.md)和[AppFileEvents](advanced-hunting-appfileevents-table.md)表深入了解身份验证事件、Active Directory 查询和与应用程序相关的活动。

- **[进入寻找](advanced-hunting-go-hunt.md)**--快速透视，从调查事件到使用基于查询的[高级](advanced-hunting-overview.md)搜索功能检查特定事件、用户、设备或其他实体类型。

- **[FileProfile （）函数](advanced-hunting-fileprofile-function.md)**—在你的[高级搜寻](advanced-hunting-overview.md)查询中使用，以合并全面的文件信息。
