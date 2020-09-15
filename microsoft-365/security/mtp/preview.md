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
ms.openlocfilehash: 502dc87b45c42f0ae95ea9da898c4d4589b19671
ms.sourcegitcommit: 9a275a13af3e063e80ce1bd3cd8142a095db92d2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/14/2020
ms.locfileid: "47649945"
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

1. 在导航窗格中，选择 " **设置**"。

2. 选择 " **Microsoft 威胁防护**"。


3. 选择 "**预览功能**  >  **" "打开预览功能"**。 

3. 选择“**保存**”。

当您看到 " **打开预览功能** " 复选框处于选中状态时，您将知道已经打开了预览功能。 

## <a name="preview-features"></a>预览功能
目前，预览中提供了以下功能和增强功能：

- **[Microsoft 威胁防护 api](api-overview.md)** -Lop-exo 级 Microsoft 威胁防护 api 使您能够自动化基于共享事件和高级搜寻表的工作流。 
- **[高级搜索中的 IdentityDirectoryEvents 表](advanced-hunting-identitydirectoryevents-table.md)** -查找涉及到内部部署域控制器的事件，该事件运行 Active DIRECTORY (AD) 。 此表涵盖了与标识相关的事件的范围以及域控制器上的系统事件。
- **[AssignedIPAddresses ( # A1 函数](advanced-hunting-assignedipaddresses-function.md)** —在高级搜寻中使用此函数可快速获取从指定时间点分配给设备或最近的 ip 地址的最新 ip 地址。
- **[在高级搜索中执行操作](advanced-hunting-take-action.md)** -快速包含威胁或在 [高级](advanced-hunting-overview.md)搜索中找到的已泄露资产的地址。
- **[在门户架构参考中](advanced-hunting-schema-tables.md#get-schema-information-in-the-security-center)** ，直接在安全中心中获取有关高级搜寻架构表的信息。 除了表和列说明之外，此方便的参考还提供了有关受支持的事件类型 (`ActionType` 值) 和示例查询的信息。

