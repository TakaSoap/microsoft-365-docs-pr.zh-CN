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
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
- okr_smb
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 0b0bd900-68b1-4bf5-808b-5d240a7739f4
description: '了解如何将多个电子邮件地址（称为电子邮件别名）与 Microsoft 365 商业版帐户关联。 '
ms.openlocfilehash: afb576a0499577b910fe3ed14eff75ae0a52b394
ms.sourcegitcommit: 0d709e9ab0d8d56c5fc11a921298f82e40e122c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/05/2021
ms.locfileid: "50114029"
---
# <a name="add-another-email-alias-for-a-user"></a>为用户添加另一个电子邮件别名

::: moniker range="o365-21vianet"

> [!NOTE]
> 管理中心正在发生改变。 如果你的体验与此处提供的详细信息不匹配，请参阅[有关新版 Microsoft 365 管理中心](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true)。

::: moniker-end
  
本文适用于具有商业版订阅的 Microsoft 365 管理员。 不适用于家庭用户。
  
Microsoft 365 中的主电子邮件地址通常是用户创建帐户时分配的电子邮件地址。 当用户向其他人发送电子邮件时，其主要电子邮件地址通常在电子邮件应用的" *发件人*  "字段中显示。 他们还可以具有多个与其 Microsoft 365 商业版帐户关联的电子邮件地址。 其他地址称为别名。 
  
例如，假设 Jenna 的电子邮件地址为 jenna@contosoco.com，但是她还想在 jen@contosoco.com 接收电子邮件，因为一些用户通过该姓名引用她。 你可以为她创建别名，以便两个电子邮件地址都转到 Jenna 的收件箱。
<br><br>  
  
最多可为一个用户创建 400 个别名。 无需其他费用或许可证。
  
> [!Tip]
> 如果希望多个用户管理发送到单个电子邮件地址（如 info@NodPublishers.com 或 sales@NodPublishers.com）的电子邮件，请创建共享邮箱。 若要了解更多信息，请参阅["创建共享邮箱"。](create-a-shared-mailbox.md)
  
## <a name="add-email-aliases-to-a-user"></a>向用户添加电子邮件别名
<a name="AddEmailPreview"> </a>

为此， [你必须具有](../add-users/about-admin-roles.md) 管理员权限。 

  
::: moniker range="o365-worldwide"

1. 在管理中心，转到“**用户**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">活动用户</a>”页面。

2. 在 **"活动用户"** 页上，> **管理电子邮件别名的用户**。 如果用户没有为其分配许可证，则看不到此选项。 
    
3. 选择 **" + 添加别名** "，然后输入用户的新别名。   
    
    > [!Important] 
    > 如果收到错误消息"找不到与参数名称 **"EmailAddresses"** 匹配的参数，则意味着完成租户设置或自定义域（如果最近添加一个）需要更长时间。 设置过程最多需要 4 个小时才能完成。 稍等片刻，待设置过程完成后重试。 如果问题仍然存在，请致电支持人员，他们会为你执行完全同步。
    
  
    > [!IMPORTANT]
    > 如果从 GoDaddy 或另一合作伙伴购买订阅，则必须转到 GoDaddy/合作伙伴管理控制台，才能将新别名设置为主要。 
  
    > [!TIP]
    > 电子邮件别名必须以下拉列表中的域结尾。 若要向列表中添加其他域名，请参阅"[将域添加到 Microsoft 365"。](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain) 
  
     
5. 完成后，选择"保存 **更改"。**
    
6. 等待 24 小时，以在整个 Microsoft 365 中填充新别名。
    
    用户现在将具有主地址和别名。 例如，发送到 Eliza Hoffman 的主地址、Eliza@NodPublishers.com和别名 Sales@NodPublishers.com的所有邮件都将发送到 Eliza 的收件箱。
    
  
7. **当用户回复时，" *发送*  "地址将是她的主要电子邮件别名。** 例如，假设有一封邮件发送到Sales@NodPublishers.com，并且它到达了吉萨的收件箱。 陶湘回复邮件时，其主电子邮件地址将显示为发件人，而不是 Sales@NodPublishers.com。 
    
::: moniker-end

::: moniker range="o365-germany"
    
1. 在管理中心，转到“**用户**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">活动用户</a>”页面。 
    
    
2. 在" **活动用户**"页面上，选择要编辑的用户名。

3. 在用户名 **/电子邮件别名旁边，** 选择"编辑 **"。**

    > [!Important] 
    > 如果收到错误消息"找不到与参数名称 **"EmailAddresses"** 匹配的参数，则意味着完成租户设置或自定义域（如果最近添加一个）需要更长时间。 设置过程最多需要 4 个小时才能完成。 稍等片刻，待设置过程完成后重试。 如果问题仍然存在，请致电支持人员，他们会为你执行完全同步。

4. 在"别名 **"下的文本框** 中，键入新电子邮件别名的第一部分。 如果已将自己的域添加到 Microsoft 365，则可使用下拉列表为新电子邮件别名选择域。 然后，选择“**添加**”。

    > [!IMPORTANT]
    > 如果从 GoDaddy 或另一合作伙伴购买订阅，则必须转到 GoDaddy/合作伙伴管理控制台，才能将新别名设置为主要。 
  
    > [!TIP]
    > 电子邮件别名必须以下拉列表中的域结尾。 若要向列表中添加其他域名，请参阅"[将域添加到 Microsoft 365"。](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain) 

5. 完成后，选择“**保存**”。

6. 等待 24 小时，以在整个 Microsoft 365 中填充新别名。 
    
    用户现在将具有主地址和别名。 例如，发送到 Eliza Hoffman 的主地址、Eliza@NodPublishers.com和别名 Sales@NodPublishers.com的所有邮件都将发送到 Eliza 的收件箱。
    
  
7. **当用户回复时，" *发送*  "地址将是她的主要电子邮件别名。** 例如，假设有一封邮件发送到Sales@NodPublishers.com，并且它到达了吉萨的收件箱。 陶湘回复邮件时，其主电子邮件地址将显示为发件人，而不是 Sales@NodPublishers.com。 

::: moniker-end

::: moniker range="o365-21vianet"

1. 在管理中心，转到“**用户**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">活动用户</a>”页面。 

    
2. 在" **活动用户**"页面上，选择要编辑的用户名。

3. 在用户名 **/电子邮件别名旁边，** 选择"编辑 **"。**

    > [!Important] 
    > 如果收到错误消息"找不到与参数名称 **"EmailAddresses"** 匹配的参数，则意味着完成租户设置或自定义域（如果最近添加一个）需要更长时间。 设置过程最多需要 4 个小时才能完成。 稍等片刻，待设置过程完成后重试。 如果问题仍然存在，请致电支持人员，他们会为你执行完全同步。

4. 在"别名 **"下的文本框** 中，键入新电子邮件别名的第一部分。 如果已将自己的域添加到 Microsoft 365，则可使用下拉列表为新电子邮件别名选择域。 然后，选择“**添加**”。

    > [!IMPORTANT]
    > 如果从 GoDaddy 或另一合作伙伴购买订阅，则必须转到 GoDaddy/合作伙伴管理控制台，才能将新别名设置为主要。 
  
    > [!TIP]
    > 电子邮件别名必须以下拉列表中的域结尾。 若要向列表中添加其他域名，请参阅"[将域添加到 Microsoft 365"。](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain) 

5. 完成后，选择“**保存**”。

6. 等待 24 小时，以在整个 Microsoft 365 中填充新别名。 
    
    用户现在将具有主地址和别名。 例如，发送到 Eliza Hoffman 的主地址、Eliza@NodPublishers.com和别名 Sales@NodPublishers.com的所有邮件都将发送到 Eliza 的收件箱。
    
  
7. **当用户回复时，" *发送*  "地址将是她的主要电子邮件别名。** 例如，假设有一封邮件发送到Sales@NodPublishers.com，并且它到达了吉萨的收件箱。 陶湘回复邮件时，其主电子邮件地址将显示为发件人，而不是 Sales@NodPublishers.com。 

::: moniker-end


## <a name="did-you-get-a-parameter-cannot-be-found-that-matches-parameter-name-emailaddresses"></a>是否收到"找不到与参数名称 EmailAddresses 匹配的参数"？


如果收到错误消息"找不到与参数名称 **EmailAddresses** 匹配的参数"，则意味着完成租户设置或自定义域（如果最近添加了一个）需要更长时间。 设置过程最多需要 4 个小时才能完成。 稍等片刻，待设置过程完成后重试。 如果问题仍然存在，请致电支持人员，他们会为你执行完全同步。
  
## <a name="did-you-purchase-your-subscription-from-godaddy-or-another-partner"></a>是否从 GoDaddy 或另一合作伙伴处购买订阅？


如果从 GoDaddy 或另一合作伙伴购买订阅，则必须转到 GoDaddy/合作伙伴管理控制台，才能将新别名设置为主要。
  
## <a name="related-articles"></a>相关文章

[从不同的地址发送电子邮件](https://support.microsoft.com/office/ccba89cb-141c-4a36-8c56-6d16a8556d2e)

[更改用户名和电子邮件地址](../add-users/change-a-user-name-and-email-address.md)
  

