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
- business_assist
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 0b0bd900-68b1-4bf5-808b-5d240a7739f4
description: '了解如何将多个电子邮件地址（称为电子邮件别名）与业务帐户Microsoft 365相关联。 '
ms.openlocfilehash: 19303cb2c60455713595dbe23a23bae7e57efb71
ms.sourcegitcommit: ac0ae5c2888e2b323e36bad041a4abef196c9c96
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/12/2022
ms.locfileid: "64780206"
---
# <a name="add-another-email-alias-for-a-user"></a>为用户添加另一个电子邮件别名
  
本文适用于具有业务订阅的Microsoft 365管理员。 不适用于家庭用户。
  
Microsoft 365中的主要电子邮件地址通常是用户在创建帐户时分配的电子邮件地址。 当用户向其他人发送电子邮件时，其主要电子邮件地址通常在电子邮件应用的" *发件人*  "字段中显示。 他们还可以有多个与业务帐户Microsoft 365相关联的电子邮件地址。 其他地址称为别名。 
  
例如，假设 Jenna 有电子邮件地址 jenna@contosoco.com，但她也想在 jen@contosoco.com 收到电子邮件，因为有些人用这个名字来称呼她。 你可以为她创建别名，以便两个电子邮件地址都转到 Jenna 的收件箱。
  
最多可为一个用户创建 400 个别名。无需其他费用或许可证。
  
> [!Tip]
> 如果希望多人管理发送到单个电子邮件地址（例如 info@NodPublishers.com 或 sales@NodPublishers.com）的电子邮件，请创建一个共享邮箱。 若要了解详细信息，请参阅 [“创建共享邮箱](create-a-shared-mailbox.md)”。

> [!TIP]
> 如果需要有关本主题中步骤的帮助，请考虑 [与 Microsoft 小型企业专家合作](https://go.microsoft.com/fwlink/?linkid=2186871)。 借助业务助手，你和你的员工在发展业务时，可以针对从加入到日常使用的各个方面随时访问小型企业专家。
  
## <a name="add-email-aliases-to-a-user"></a>向用户添加电子邮件别名

必须具有全局管理员权限才能向用户添加电子邮件别名。

1. 在管理中心，转到“**用户**\><a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">活动用户</a>”页面。

2. 在 **“活动用户** ”页上，选择> **管理用户名和电子邮件的用户**。 如果该人员没有向其分配许可证，则不会看到此选项。 
    
3. 选择 **+添加别名** ，并为用户输入新别名。   
    
    > [!Important] 
    > 如果收到错误消息“**找不到与参数名称'EmailAddresses'匹配的参数”**，则表示完成租户设置需要更长的时间，或者最近添加了自定义域。 设置过程最多需要 4 个小时才能完成。 稍等片刻，待设置过程完成后重试。 如果问题仍然存在，请致电支持人员，他们会为你执行完全同步。
    
  
    > [!IMPORTANT]
    > 如果从 GoDaddy 或另一合作伙伴购买订阅，则必须转到 GoDaddy/合作伙伴管理控制台，才能将新别名设置为主要。 


   > [!IMPORTANT]
   >  如果收到错误消息 **，此用户将与本地 Active Directory 同步。某些详细信息只能通过本地 Active Directory 进行编辑**，这意味着 Active Directory 对于同步用户的属性具有权威性，需要修改本地 Active Directory中的属性。
  
    > [!TIP]
    > 电子邮件别名必须以下拉列表中的域结尾。 若要将另一个域名添加到列表中，请[参阅“将域添加到Microsoft 365](../setup/add-domain.md)。 
  
     
5. 完成后，选择 **“保存更改**”。
    
6. 等待 24 小时，让新别名填充整个Microsoft 365。
    
    用户现在将具有主地址和别名。 例如，发送到伊丽莎·霍夫曼的主要地址（Eliza@NodPublishers.com）的所有邮件以及她的别名（Sales@NodPublishers.com）都将转到伊丽莎的收件箱。
    
  
7. **当用户答复时，*From* 地址将取决于她的Outlook客户端。Outlook 网页版将使用收到电子邮件的别名 (我们将此称为乒乓球原则) 。Outlook桌面将使用她的主要电子邮件别名。** 例如，假设向 Sales@NodPublishers.com 发送了一条消息，并将其发送到 Eliza 的收件箱中。 当 Eliza 使用桌面Outlook回复邮件时，她的主要电子邮件地址将显示为 Eliza@NodPublishers.com，而不是 Sales@NodPublishers.com。
    
## <a name="did-you-get-a-parameter-cannot-be-found-that-matches-parameter-name-emailaddresses"></a>是否收到“找不到与参数名称 EmailAddresses 匹配的参数”？

如果收到错误消息“**找不到与参数名称 EmailAddresses 匹配的参数**”，则表示完成租户设置需要更长的时间，或者最近添加了自定义域。 设置过程最多需要 4 个小时才能完成。 稍等片刻，待设置过程完成后重试。 如果问题仍然存在，请致电支持人员，他们会为你执行完全同步。
  
## <a name="did-you-purchase-your-subscription-from-godaddy-or-another-partner"></a>是否从 GoDaddy 或另一合作伙伴处购买订阅？


如果从 GoDaddy 或另一合作伙伴购买订阅，则必须转到 GoDaddy/合作伙伴管理控制台，才能将新别名设置为主要。

## <a name="sending-email-from-the-proxy-address-easily"></a>轻松从代理地址发送电子邮件

2021 年 7 月将推出一项新功能，允许用户在使用Outlook 网页版时轻松地从别名发送。 当该功能推出到租户管理员使用 `Set-OrganizationConfig -SendFromAliasEnabled $true` cmdlet 的租户时，租户中的用户将有权访问复选框列表，其中每个条目对应于其Outlook设置中的别名。 选择别名会使其显示在 Compose 窗体的“从”下拉列表中。
  
## <a name="related-content"></a>相关内容

[从其他地址发送电子邮件](https://support.microsoft.com/office/ccba89cb-141c-4a36-8c56-6d16a8556d2e) (文章) 

[更改用户名和电子邮件地址](../add-users/change-a-user-name-and-email-address.md) (文章) 

[在 Microsoft 365 中配置电子邮件转发](configure-email-forwarding.md)（文章）
