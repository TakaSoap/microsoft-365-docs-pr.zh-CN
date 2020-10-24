---
title: 还原已删除的 Microsoft 365 组
ms.reviewer: arvaradh
f1.keywords: CSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: b7c66b59-657a-4e1a-8aa0-8163b1f4eb54
description: 了解如何还原已删除的 Microsoft 365 组。
ms.openlocfilehash: 091697be54b1127a5cb336179733d51519947e14
ms.sourcegitcommit: 3cdb670f10519f7af4015731e7910954ba9f70dc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/24/2020
ms.locfileid: "48753239"
---
# <a name="restore-a-deleted-microsoft-365-group"></a>还原已删除的 Microsoft 365 组

如果已删除某个组，默认情况下它将保留30天。 这30天的期限被视为 "软删除"，因为您仍可以还原组。 30天后，该组及其关联的内容将被永久删除且无法还原。

还原组时，还可还原以下内容：
  
- Azure Active Directory (AD) Microsoft 365 组对象、属性和成员。
    
- 组的电子邮件地址。
    
- Exchange Online 共享的收件箱和日历。
    
- SharePoint Online 团队网站和文件。
    
- OneNote 笔记本
    
- Planner
    
- Teams

- Yammer group and group content (如果 Microsoft 365 组是从 Yammer 创建的) 

> [!NOTE]
> 本文介绍仅还原 Microsoft 365 组。 删除后，所有其他组都不能还原。

## <a name="restore-a-group"></a>还原组

# <a name="outlook"></a>[Outlook](#tab/outlook)

如果你是 Microsoft 365 组的所有者，则可以通过执行以下步骤，在 web 上的 Outlook 中自行还原组：

1. 在 "[已删除的组" 页](https://outlook.office.com/people/group/deleted)上，选择 "**组**" 节点下的 "**管理组**" 选项，然后选择 "**已删除**"。

2. 单击要还原的组旁边的 " **还原** " 选项卡。

如果此处未显示已删除的组，请与管理员联系。

# <a name="admin-center"></a>[管理中心](#tab/admin-center)

如果您是全局管理员或组管理员，则可以在 Microsoft 365 管理中心中还原已删除的组：

1. 转到[管理中心](https://admin.microsoft.com)。
2. 展开 " **组**"，然后单击 " **已删除组**"。
3. 选择要还原的组，然后单击 " **还原组**"。

> [!NOTE]
> 在某些情况下，可能需要长达24小时才能还原组及其所有数据。 

---

## <a name="got-questions-about-microsoft-365-groups"></a>遇到有关 Microsoft 365 组的问题？

访问 [Microsoft 技术社区](https://techcommunity.microsoft.com/t5/Office-365-Groups/ct-p/Office365Groups) 以发布问题，并参与有关 Microsoft 365 组的对话。 
  
## <a name="related-articles"></a>相关文章

[使用 PowerShell 管理 Microsoft 365 组](https://docs.microsoft.com/microsoft-365/enterprise/manage-microsoft-365-groups-with-powershell)
  
[使用 Remove-UnifiedGroup cmdlet 删除组](https://technet.microsoft.com/library/mt238270%28v=exchg.160%29.aspx)
  
[管理连接了组的团队网站设置](https://support.microsoft.com/office/8376034d-d0c7-446e-9178-6ab51c58df42)
  
[在 Outlook 中删除组](https://support.microsoft.com/office/ca7f5a9e-ae4f-4cbe-a4bc-89c469d1726f)
