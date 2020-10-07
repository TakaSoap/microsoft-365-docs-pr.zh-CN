---
title: 允许成员作为组发送或代表组发送
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
description: 了解如何允许成员以 Microsoft 365 组的形式发送电子邮件，或代表 Microsoft 365 组发送电子邮件。
ms.openlocfilehash: 9ccaeff49914dd5b510beb80f40a3a3b790ce831
ms.sourcegitcommit: 9841058fcc95f7c2fed6af92bc3c3686944829b6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/07/2020
ms.locfileid: "48377589"
---
# <a name="allow-members-to-send-as-or-send-on-behalf-of-a-group"></a>允许成员作为组发送或代表组发送

已被授予 " **代理发送** " 或 **"代表发送"** 权限的 Microsoft 365 组的成员可以作为组或代表组发送电子邮件。 本文介绍管理员如何设置这些权限。
  
例如，如果 Megan Bowen 是 Microsoft 365 的 **培训** 组的一部分，并且对该组具有 " **代理发送** " 权限，则如果她将电子邮件作为组发送，则它看起来就像是电子邮件发送的 " **培训** 组"。 
  
" **代表发送** " 权限允许用户代表 Microsoft 365 组发送电子邮件。 例如，如果 Alex Wilber 是 **市场营销** Microsoft 365 组的一部分，并且拥有 " **代表发送** " 权限并将电子邮件作为组发送，则电子邮件看起来好像是由 **Alex Wilber 代表行销**发送的。

> [!IMPORTANT]
> 您可以为给定用户配置 " **代理发送** " 或 **"代表发送** "，但不能同时配置两者。 如果同时配置两者，则默认为 " **代理发送**"。

> [!TIP]
> 请参阅 [通过或代表 Microsoft 365 组发送电子邮件](https://support.microsoft.com/office/0f4964af-aec6-484b-a65c-0434df8cdb6b) ，了解如何使用 Outlook 和 Web 上的 outlook 从组发送电子邮件。
    
## <a name="allow-members-to-send-email-as-a-group"></a>允许成员以组的形式发送电子邮件

本节介绍如何允许用户在 exchange Online 中 (EAC) 在 [exchange 管理中心](https://go.microsoft.com/fwlink/p/?linkid=2059104) 中以组的形式发送电子邮件。
  
1. 在 <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange 管理中心</a>中，转到 " **收件人** \> **组**"。
    
2. 在**Edit** ![ ](../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) 要允许用户发送的组中选择 "编辑编辑组" 图标。   
    
3. 选择 " **组委派**"。
    
4. 在 " **代理发送** " 部分中，选择 **+** 用于添加要作为组发送的用户的符号。 
    
    !["代理发送" 对话框的屏幕截图](../media/1df167f6-1eff-4f98-9ecd-4230fab46557.png)
  
5. 键入从列表中搜索或选取用户。 选择 **"确定"** ，然后单击 " **保存**"。
    
    ![从列表中搜索或选取用户的类型](../media/522919cf-664c-4a25-8076-c51c8c9fbe43.png)
  
## <a name="allow-members-to-send-email-on-behalf-of-a-group"></a>允许成员代表组发送电子邮件

本节介绍如何允许用户代表 exchange Online 中的组在 Exchange 管理中心内发送电子邮件 (EAC) 。
  
1. 在 <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange 管理中心</a>中，转到 " **收件人** \> **组**"。
    
2. 在**Edit** ![ ](../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) 要允许用户发送的组中选择 "编辑编辑组" 图标。 
    
3. 选择 " **组委派**"。
    
4. 在 "代表发送" 部分中，选择 **+** 用于添加要作为组发送的用户的符号。 
    
    !["代表发送" 对话框的屏幕截图](../media/2bae0579-8907-4d6b-8920-ddd6555897b4.png)
  
5. 键入从列表中搜索或选取用户。 选择 **"确定"** ，然后单击 " **保存**"。
    
    ![从列表中搜索或选取用户的类型](../media/522919cf-664c-4a25-8076-c51c8c9fbe43.png)

## <a name="related-articles"></a>相关文章

[了解有关 Microsoft 365 组的详细信息](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2)

[外接 Add-recipientpermission](https://go.microsoft.com/fwlink/p/?LinkId=723960)

[Remove-unifiedgroup](https://go.microsoft.com/fwlink/p/?LinkId=616189)
