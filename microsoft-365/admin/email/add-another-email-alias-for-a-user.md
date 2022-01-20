---
title: 添加用户的其他电子邮件别名
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 0b0bd900-68b1-4bf5-808b-5d240a7739f4
description: '了解如何将多个电子邮件地址（称为电子邮件别名）与企业Microsoft 365相关联。 '
ms.openlocfilehash: 16296c9ba748ec76fef52be3ae13bba9ff8552b1
ms.sourcegitcommit: cde34d38bdfb6335b980f1c48c6b218da6a64bf8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/20/2022
ms.locfileid: "62155964"
---
# <a name="add-another-email-alias-for-a-user"></a>为用户添加另一个电子邮件别名
  
本文适用于Microsoft 365订阅的管理员。 不适用于家庭用户。
  
用户邮箱中Microsoft 365电子邮件地址通常是用户创建帐户时分配的电子邮件地址。 当用户向其他人发送电子邮件时，其主要电子邮件地址通常在电子邮件应用的" *发件人*  "字段中显示。 他们还可以将多个电子邮件地址与其企业Microsoft 365关联。 其他地址称为别名。 
  
例如，假设 Jenna 的电子邮件地址 jenna@contosoco.com，但是她还想在 jen@contosoco.com 接收电子邮件，因为一些人用该姓名引用她。 你可以为她创建别名，以便两个电子邮件地址都转到 Jenna 的收件箱。
  
最多可为一个用户创建 400 个别名。无需其他费用或许可证。
  
> [!Tip]
> 如果希望多个用户管理发送到单个电子邮件地址（如 info@NodPublishers.com 或 sales@NodPublishers.com）的电子邮件，请创建共享邮箱。 若要了解更多信息，请参阅 [创建共享邮箱](create-a-shared-mailbox.md)。
  
## <a name="add-email-aliases-to-a-user"></a>向用户添加电子邮件别名

您必须具有全局管理员权限才能向用户添加电子邮件别名。

1. 在管理中心，转到“**用户**\><a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">活动用户</a>”页面。

2. 在" **活动用户"** 页上，选择"管理> **和电子邮件"的用户**。 如果用户未分配许可证，则看不到此选项。 
    
3. 选择 **+ 添加别名** ，然后输入用户的新别名。   
    
    > [!Important] 
    > 如果收到错误消息"找不到与参数名称 **"EmailAddresses"** 匹配的参数，则意味着完成租户或自定义域设置（如果最近添加了一个）需要更长时间。 设置过程最多需要 4 个小时才能完成。 稍等片刻，待设置过程完成后重试。 如果问题仍然存在，请致电支持人员，他们会为你执行完全同步。
    
  
    > [!IMPORTANT]
    > 如果从 GoDaddy 或另一合作伙伴购买订阅，则必须转到 GoDaddy/合作伙伴管理控制台，才能将新别名设置为主要。 


   > [!IMPORTANT]
   >  如果收到错误消息，则 **此用户已与本地 Active Directory 同步。某些详细信息只能** 通过本地 Active Directory 进行编辑，这意味着 Active Directory 对同步用户的属性具有权威性，您需要修改本地 Active Directory 中的属性。
  
    > [!TIP]
    > 电子邮件别名必须以下拉列表中的域结尾。 若要向列表中添加其他域名，请参阅将[域添加到Microsoft 365。](../setup/add-domain.md) 
  
     
5. 完成后，选择"保存 **更改"。**
    
6. 请等待 24 小时，以在整个过程中填充Microsoft 365。
    
    用户现在将具有主地址和别名。 例如，发送到 Eliza Hoffman 的主地址、Eliza@NodPublishers.com 和别名 Sales@NodPublishers.com 的所有邮件都将发送到 Eliza 的收件箱。
    
  
7. **当用户回复时，"发送者"地址将取决于她Outlook客户端。Outlook 网页版将使用收到电子邮件的别名 (我们将此称为 ping- 一) 。Outlook桌面将使用她的主要电子邮件别名。** 例如，假设有一封邮件发送到 Sales@NodPublishers.com，并到达吉萨的收件箱。 当 Eliza 使用桌面Outlook回复邮件时，她的主要电子邮件地址将显示为 Eliza@NodPublishers.com，而不是 Sales@NodPublishers.com。
    
## <a name="did-you-get-a-parameter-cannot-be-found-that-matches-parameter-name-emailaddresses"></a>您是否收到"找不到与参数名称 EmailAddresses 匹配的参数"？

如果收到错误消息" 找不到与参数名称 **EmailAddresses** 匹配的参数"，则意味着完成租户或自定义域设置（如果最近添加了一个）需要更长时间。 设置过程最多需要 4 个小时才能完成。 稍等片刻，待设置过程完成后重试。 如果问题仍然存在，请致电支持人员，他们会为你执行完全同步。
  
## <a name="did-you-purchase-your-subscription-from-godaddy-or-another-partner"></a>是否从 GoDaddy 或另一合作伙伴处购买订阅？


如果从 GoDaddy 或另一合作伙伴购买订阅，则必须转到 GoDaddy/合作伙伴管理控制台，才能将新别名设置为主要。

## <a name="sending-email-from-the-proxy-address-easily"></a>轻松地从代理地址发送电子邮件

2021 年 7 月推出一项新功能，允许用户在使用别名时轻松Outlook 网页版。 当功能推出到租户管理员使用 cmdlet 的租赁时，租户内的用户将有权访问复选框列表，其中每个条目对应其 Outlook 设置中的别名。 `Set-OrganizationConfig -SendFromAliasEnabled $true` 选择别名将使其出现在"撰写"窗体的"自"下拉列表中。
  
## <a name="related-content"></a>相关内容

[本文介绍的不同地址 (](https://support.microsoft.com/office/ccba89cb-141c-4a36-8c56-6d16a8556d2e) 发送电子邮件) 

[Change a user name and email address (](../add-users/change-a-user-name-and-email-address.md) article) 

[在 Microsoft 365 中配置电子邮件转发](configure-email-forwarding.md)（文章）
