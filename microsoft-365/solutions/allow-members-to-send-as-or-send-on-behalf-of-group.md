---
title: 允许成员以组发送或代表组发送
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- m365solution-collabgovernance
search.appverid:
- MET150
ms.assetid: 0ad41414-0cc6-4b97-90fb-06bec7bcf590
description: 了解如何允许成员以 Microsoft 365 组发送电子邮件或代表 Microsoft 365 组发送电子邮件。
ms.openlocfilehash: 6dff559eceec1b719f31d577d7fff8f604636a47
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/12/2020
ms.locfileid: "49663579"
---
# <a name="allow-members-to-send-as-or-send-on-behalf-of-a-group"></a>允许成员以组发送或代表组发送

已被授予"代理发送"或"代表发送"权限的 Microsoft  365 组的成员可以作为组或代表组发送电子邮件。  本文介绍了全局管理员或 Exchange 管理员如何设置这些权限。
  
例如，如果 Megan Bowen **是培训** Microsoft 365 组的一部分，并且对该组具有"发送为"权限，那么如果她以组发送电子邮件，则看起来就像培训组发送了该电子邮件一样。 
  
" **代表发送"** 权限允许用户代表 Microsoft 365 组发送电子邮件。 例如，如果 Alex Wilber 是 **Marketing** Microsoft 365 组的一部分，并且具有"代表发送"权限并作为组发送电子邮件，则电子邮件看起来好像是由 **Alex Wilber** 代表 Marketing 发送的。

> [!IMPORTANT]
> 您可以为给定 **用户****配置"** 代理发送"或"代表发送"，但不能同时配置这两者。 如果同时配置这两者，它将默认 **为"发送为"。**

> [!TIP]
> 请参阅 ["从 Microsoft 365](https://support.microsoft.com/office/0f4964af-aec6-484b-a65c-0434df8cdb6b) 组或代表 Microsoft 365 组发送电子邮件"，了解如何使用 Outlook 和 Outlook 网页版从组发送电子邮件。
    
## <a name="allow-members-to-send-email-as-a-group"></a>允许成员作为组发送电子邮件

本节介绍如何允许用户在 Exchange Online 的 [EAC](https://go.microsoft.com/fwlink/p/?linkid=2059104) (Exchange 管理中心) 组发送电子邮件。
  
1. 在 <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange 管理中心</a>，转到 **"收件人** \> **组"。**
    
2. 选择要允许用户发送的组上的"编辑编辑组" ![ ](../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) 图标。   
    
3. 选择 **组委派**。
    
4. 在 **"发送为** "部分，选择符号以添加要作为组 **+** 发送的用户。 
    
    !["发送为"对话框的屏幕截图](../media/1df167f6-1eff-4f98-9ecd-4230fab46557.png)
  
5. 键入以搜索或从列表中选择用户。 选择 **"确定** "并 **保存**。
    
    ![键入以搜索或从列表中选择用户](../media/522919cf-664c-4a25-8076-c51c8c9fbe43.png)
  
## <a name="allow-members-to-send-email-on-behalf-of-a-group"></a>允许成员代表组发送电子邮件

本节介绍如何允许用户代表 Exchange 管理中心中的组发送电子邮件， (EAC) Exchange Online。
  
1. 在 <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange 管理中心</a>，转到 **"收件人** \> **组"。**
    
2. 选择要允许用户发送的组上的"编辑编辑组" ![ ](../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) 图标。 
    
3. 选择 **组委派**。
    
4. 在"代表发送"部分，选择符号以添加要作为组 **+** 发送的用户。 
    
    !["代表发送"对话框的屏幕截图](../media/2bae0579-8907-4d6b-8920-ddd6555897b4.png)
  
5. 键入以搜索或从列表中选择用户。 选择 **"确定** "并 **保存**。
    
    ![键入以搜索或从列表中选择用户](../media/522919cf-664c-4a25-8076-c51c8c9fbe43.png)

## <a name="related-articles"></a>相关文章

[协作治理规划分步规划](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[创建协作治理计划](collaboration-governance-first.md)

[详细了解 Microsoft 365 组](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2)

[Add-RecipientPermission](https://go.microsoft.com/fwlink/p/?LinkId=723960)

[Set-UnifiedGroup](https://go.microsoft.com/fwlink/p/?LinkId=616189)
