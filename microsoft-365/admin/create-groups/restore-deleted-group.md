---
title: 还原已删除Microsoft 365组
ms.reviewer: arvaradh
f1.keywords: CSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: b7c66b59-657a-4e1a-8aa0-8163b1f4eb54
description: 已删除的组将保留 30 天，您仍可以还原该组。 30 天后，该组及其内容将永久删除。
ms.openlocfilehash: 926cfa18972a7ca72009258b02b565bd28a183be
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60165696"
---
# <a name="restore-a-deleted-microsoft-365-group"></a>还原已删除Microsoft 365组

如果已删除某个组，默认情况下该组将保留 30 天。 此 30 天期限被视为"软删除"，因为您仍可以还原组。 30 天后，该组及其关联内容将永久删除且无法还原。

还原组时，还可还原以下内容：
  
- Azure Active Directory (组) Microsoft 365、属性和成员创建 AD。
    
- 组的电子邮件地址。
    
- Exchange Online共享收件箱和日历。
    
- SharePoint联机团队网站和文件。
    
- OneNote 笔记本
    
- Planner
    
- Teams

- Yammer组和组内容 (如果Microsoft 365组是Yammer) 

- Power BI[经典工作区](/power-bi/collaborate-share/service-create-workspaces)

> [!NOTE]
> 本文介绍仅还原Microsoft 365组。 所有其他组在删除后无法还原。

## <a name="restore-a-group"></a>还原组

# <a name="outlook"></a>[Outlook](#tab/outlook)

如果你是组的所有者，Microsoft 365以下步骤，可以在Outlook 网页版中自己还原组：

1. 在"[已删除的组"页上](https://outlook.office.com/people/group/deleted)**，选择"** 组"节点下的"管理组"选项，然后选择"**已删除"。**

2. 单击要 **还原** 的组旁边的"还原"选项卡。

如果已删除的组未在此处显示，请与管理员联系。

# <a name="admin-center"></a>[管理中心](#tab/admin-center)

如果您是全局管理员或组管理员，可以在以下网站中还原已删除Microsoft 365 管理中心：

1. 转到[管理中心](https://admin.microsoft.com)。
2. 展开 **"组**"，然后单击"**已删除组"。**
3. 选择要还原的组，然后单击"还原 **组"。**

> [!NOTE]
> 在某些情况下，可能需要 24 小时才能还原组及其所有数据。 

---

## <a name="got-questions-about-microsoft-365-groups"></a>对组Microsoft 365问题？

请访问[Microsoft 技术Community](https://techcommunity.microsoft.com/t5/Office-365-Groups/ct-p/Office365Groups)发布问题并参与有关 Microsoft 365 组的对话。 
  
## <a name="related-content"></a>相关内容

[Manage Microsoft 365 Groups with PowerShell](../../enterprise/manage-microsoft-365-groups-with-powershell.md) (article) \
[使用 Remove-UnifiedGroup cmdlet 删除](/powershell/module/exchange/remove-unifiedgroup) (文章) \
[管理与组连接的团队网站设置](https://support.microsoft.com/office/8376034d-d0c7-446e-9178-6ab51c58df42) (文章) \
[删除本文Outlook (](https://support.microsoft.com/office/ca7f5a9e-ae4f-4cbe-a4bc-89c469d1726f)中的) 
