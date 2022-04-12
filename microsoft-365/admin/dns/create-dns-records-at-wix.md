---
title: 连接 Wix 中的 DNS 记录以Microsoft 365
f1.keywords:
- CSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ROBOTS: NOINDEX, NOFOLLOW
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
- Adm_O365_Setup
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 7173c635-58b3-400f-95e0-97abe915565e
description: 了解如何在 Wix for Microsoft 中验证域并设置电子邮件、Skype for Business Online 和其他服务的 DNS 记录。
ms.openlocfilehash: 58d7819e006183a35272811ed791d3236f9fc742
ms.sourcegitcommit: ac0ae5c2888e2b323e36bad041a4abef196c9c96
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/12/2022
ms.locfileid: "64780282"
---
# <a name="connect-your-dns-records-at-wix-to-microsoft-365"></a>连接 Wix 中的 DNS 记录以Microsoft 365

如果找不到要查找的内容，请 **[查看域常见问题解答](../setup/domains-faq.yml)**。

如果 Wix 是 DNS 托管提供商，请按照本文中的步骤验证域，并为电子邮件、Skype for Business Online 等设置 DNS 记录。

在 Wix 中添加这些记录后，域将设置为使用Microsoft 服务。

> [!NOTE]
> DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。

## <a name="add-a-txt-record-for-verification"></a>添加 TXT 记录进行验证

在 Microsoft 中使用你的域之前，我们必须确保你拥有它。 你在域注册机构登录到帐户并创建 DNS 记录的能力向 Microsoft 证明你拥有该域。

> [!NOTE]
> 此记录仅用于验证您的域属于您所有，并不影响任何其他操作。 如果需要，可以稍后将其删除。

> [!NOTE]
> WIX 不支持子域的 DNS 条目。

1. 若要开始，请使用 [此链接](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account)转到 Wix 上的域页面。 系统将会提示您先登录。

2. 选择 **“域** \> **...**”，然后从下拉列表中选择 **“管理 DNS 记录** ”。

   :::image type="content" source="../../media/dns-wix/wix-domains-1.png" alt-text="从下拉列表中选择“管理 DNS 记录”。":::

3. 在 DNS 编辑器的 **TXT (文本)** 行中选择 **+添加记录**。

   :::image type="content" source="../../media/dns-wix/wix-domains-TXT-add-record.png" alt-text="选择“添加记录”。":::

4. In the boxes for the new record, type or copy and paste the values from the following table.

   |主机名|TXT Value|TTL|
   |---|---|---|
   |自动填充 (留空) |MS=*msXXXXXXXX* <br/> **注意：** 这是一个示例。 在这里使用表中的特定“**目标地址或指向的地址**”值。 [如何查找此项？](../get-help-with-domains/information-for-dns-records.md)|1 小时|

5. **SelectSave**。

   :::image type="content" source="../../media/dns-wix/wix-domains-txt-save.png" alt-text="选择“保存”。":::

   请在继续之前等待数分钟，以便您刚刚创建的记录可以通过 Internet 完成更新。


在在域注册机构网站添加了记录后，你将返回到 Microsoft 并请求记录。 Microsof 找到正确的 TXT 记录表明域已通过验证。

若要验证Microsoft 365中的记录，

1. 在管理中心，转到 **设置** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">**域**</a>。

1. 在“域”页上，选择要验证的域，然后选择 **“开始设置**”。

    :::image type="content" source="../../media/dns-IONOS/IONOS-DomainConnects-2.png" alt-text="选择“开始”设置。":::

1. 选择 **继续**。

1. 在“**验证域**”页面上，选择“**验证**”。

> [!NOTE]
> DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。

## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>添加一条 MX 记录，确保发往你的域的电子邮件将会发送到 Microsoft

1. 若要开始，请使用 [此链接](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account)转到 Wix 上的域页面。 系统将会提示您先登录。

1. 选择 **“域** \> **...**”，然后从下拉列表中选择 **“管理 DNS 记录** ”。

   :::image type="content" source="../../media/dns-wix/wix-domains-1.png" alt-text="从下拉列表中选择“管理 DNS 记录”。":::

1. 在 **MX (邮件交换)** 下，选择 **“编辑 MX 记录**”。

   :::image type="content" source="../../media/dns-wix/wix-domains-edit-mx-records.png" alt-text="选择“编辑 MX 记录”。":::

1. 从下拉列表中选择 **“其他** ”，然后选择 **“+ 添加记录**”。

   :::image type="content" source="../../media/dns-wix/wix-domains-other.png" alt-text="从下拉列表中选择“其他”。":::

1. 在新记录的框中，键入或复制并粘贴下表中的值：

   |主机名|Points to |优先级|TTL|
   |---|---|---|---|
   |自动填充|*\<domain-key\>*.mail.protection.outlook.com <br/> **注意：** 从 Microsoft 帐户获取你 *\<domain-key\>* 。  如何查找此内容？[](../get-help-with-domains/information-for-dns-records.md)|0 <br/> 有关优先级的详细信息，请参阅[什么是 MX 优先级？](../setup/domains-faq.yml)|1 Hour|

1. 如果列出了任何其他 MX 记录，请删除其中的每个记录。

  :::image type="content" source="../../media/dns-wix/wix-domains-mx-delete.png" alt-text="选择“删除”。":::

1. 选择“**保存**”。

## <a name="add-the-cname-record-required-for-microsoft"></a>添加 Microsoft 所需的 CNAME 记录

1. 若要开始，请使用 [此链接](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account)转到 Wix 上的域页面。 系统将会提示您先登录。

2. 选择 **“域** \> **...**”，然后从下拉列表中选择 **“管理 DNS 记录** ”。

   :::image type="content" source="../../media/dns-wix/wix-domains-1.png" alt-text="从下拉列表中选择“管理 DNS 记录”。":::

3. 在 **CNAME 记录的 DNS 编辑器) 行的 CNAME (别名** 中选择 **+ 添加记录**。

   :::image type="content" source="../../media/dns-wix/wix-domains-cname-add-record.png" alt-text="选择+添加记录。":::

4. 在新记录的框中，键入或复制并粘贴下表中的值：

   |主机名|值|TTL|
   |---|---|---|
   |自动发现|autodiscover.outlook.com|1 Hour|

5. 选择“**保存**”。

   :::image type="content" source="../../media/dns-wix/wix-domains-cname-save.png" alt-text="选择“保存”。":::

   请在继续之前等待数分钟，以便您刚刚创建的记录可以通过 Internet 完成更新。

## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>为 SPF 添加 TXT 记录以帮助防止垃圾邮件

> [!IMPORTANT]
> 一个域所拥有的 SPF 的 TXT 记录不能超过一个。 如果域具有多个 SPF 记录，你将收到电子邮件错误，其中随附发送和垃圾邮件分类问题。 如果你的域已有 SPF 记录，请不要为 Microsoft 创建新记录。 而是将所需的 Microsoft 值添加到当前记录，以便具有包含这两组值的 *单* 个 SPF 记录。

1. 若要开始，请使用 [此链接](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account)转到 Wix 上的域页面。 系统将会提示您先登录。

2. 选择 **“域** \> **...**”，然后从下拉列表中选择 **“管理 DNS 记录** ”。

   :::image type="content" source="../../media/dns-wix/wix-domains-1.png" alt-text="从下拉列表中选择“管理 DNS 记录”。":::

3. 在 DNS 编辑器的 **TXT (文本)** 行中选择 **+添加记录**。

   :::image type="content" source="../../media/dns-wix/wix-domains-TXT-add-record.png" alt-text="选择+添加记录。":::

   **注意**：Wix 在 DNS 编辑器中提供 SPF 行。 忽略该行，并使用 **TXT (文本)** 行输入下面的 SPF 值。

4. 在新记录的框中，键入或复制并粘贴下表中的值：

   |主机名|值|TTL|
   |---|---|---|
   |[保留此空白]|v=spf1 include:spf.protection.outlook.com -all <br/> **注意：** 建议复制粘贴此条目，以保证正确保留所有空格。|1 Hour|

5. 选择“**保存**”。

   :::image type="content" source="../../media/dns-wix/wix-domains-txt-save.png" alt-text="选择“保存”。":::

   请在继续之前等待数分钟，以便您刚刚创建的记录可以通过 Internet 完成更新。

## <a name="advanced-option-skype-for-business"></a>高级选项：Skype for Business

仅当组织对联机通信服务（例如聊天、电话会议和视频呼叫）使用Skype for Business时，除了Microsoft Teams，才选择此选项。 Skype需要四条记录：两条用于用户到用户通信的 SRV 记录，以及两条用于登录和将用户连接到服务的 CNAME 记录。

### <a name="add-the-two-required-srv-records"></a>添加两个必需的 SRV 记录

1. 若要开始，请使用 [此链接](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account)转到 Wix 上的域页面。 系统将会提示您先登录。

1. 选择 **“域** \> **...**”，然后从下拉列表中选择 **“管理 DNS 记录** ”。

   :::image type="content" source="../../media/dns-wix/wix-domains-1.png" alt-text="从下拉列表中选择“管理 DNS 记录”。":::

1. 在 DNS 编辑器的 **SRV** 行中选择 **+添加记录**。

   :::image type="content" source="../../media/dns-wix/wix-domains-srv-add-record.png" alt-text="选择+添加记录。":::

1. 在新记录的框中，键入或复制并粘贴表中第一行中的值：

   |服务|协议|主机名|粗细|端口|Target|优先级|TTL|
   |---|---|---|---|---|---|---|---|
   |sip|tls|自动填充|1|443|sipdir.online.lync.com|100|1 Hour|
   |sipfed|tcp|自动填充|1|5061|sipfed.online.lync.com|100|1 Hour|

1. 选择“**保存**”。

   :::image type="content" source="../../media/dns-wix/wix-domains-srv-save.png" alt-text="选择“保存”。":::

1. 通过从表的第二行复制值来添加其他 SRV 记录。

> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果在添加 DNS 记录后遇到邮件流问题或其他问题，请参阅[查找在添加域或 DNS 记录后遇到的问题并进行修复](../get-help-with-domains/find-and-fix-issues.md)。

### <a name="add-the-two-required-cname-records-for-skype-for-business"></a>为Skype for Business添加两条所需的 CNAME 记录

1. 选择 **“ +** 在 **DNS 编辑器的 CNAME (别名)** 行中添加其他值，然后输入下表中第一行中的值。

   |类型|主机|值|TTL|
   |---|---|---|---|
   |CNAME|sip|sipdir.online.lync.com. <br/> **此值必须以句点 (.) 结尾。**|1 小时|
   |CNAME|lyncdiscover|webdir.online.lync.com. <br/> **此值必须以句点 (.) 结尾。**|1 Hour|

1. 选择“**保存**”。

   :::image type="content" source="../../media/dns-wix/wix-domains-cname-save.png" alt-text="选择“保存”。":::

1. 通过从表的第二行复制值来添加其他 CNAME 记录。

> [!NOTE]
> DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。

## <a name="advanced-option-intune-and-mobile-device-management-for-microsoft-365"></a>高级选项：适用于Microsoft 365的Intune和移动设备管理

此服务可帮助保护和远程管理连接到域的移动设备。 移动设备管理需要两条 CNAME 记录，以便用户可以将设备注册到服务。

### <a name="add-the-two-required-cname-records-for-mobile-device-management"></a>添加移动设备管理所需的两条 CNAME 记录

1. 若要开始，请使用 [此链接](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account)转到 Wix 上的域页面。 系统将会提示您先登录。

1. 选择 **“域** \> **...**”，然后从下拉列表中选择 **“管理 DNS 记录** ”。

   :::image type="content" source="../../media/dns-wix/wix-domains-1.png" alt-text="从下拉列表中选择“管理 DNS 记录”。":::

1. 在 **CNAME 记录的 DNS 编辑器) 行的 CNAME (别名** 中选择 **+ 添加记录**。

   :::image type="content" source="../../media/dns-wix/wix-domains-cname-add-record.png" alt-text="选择+添加记录。":::

1. 输入下表中第一行中的值。

    |类型|主机|值|TTL|
    |---|---|---|---|
    |CNAME|enterpriseregistration|enterpriseregistration.windows.net. <br/> **此值必须以句点 (.) 结尾。**|1 小时|
    |CNAME|enterpriseenrollment|enterpriseenrollment.manage.microsoft.com。 <br/> **此值必须以句点 (.) 结尾。**|1 Hour|

1. 选择“**保存**”。

   :::image type="content" source="../../media/dns-wix/wix-domains-cname-save.png" alt-text="选择“保存”。":::

1. 通过从表的第二行复制值来添加其他 CNAME 记录。

> [!NOTE]
> DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。
