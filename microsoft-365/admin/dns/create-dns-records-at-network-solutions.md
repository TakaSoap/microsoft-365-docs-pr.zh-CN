---
title: 在网络解决方案中连接 DNS 记录以Microsoft 365
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
ms.assetid: 1dc55f9f-5309-450f-acc3-b2b4119c8be3
description: 了解如何在适用于 Microsoft 的网络解决方案中验证域并设置电子邮件、Skype for Business Online 和其他服务的 DNS 记录。
ms.openlocfilehash: 87026bfbbae7398c774bf083e0df8d2c228c7560
ms.sourcegitcommit: ac0ae5c2888e2b323e36bad041a4abef196c9c96
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/12/2022
ms.locfileid: "64780276"
---
# <a name="connect-your-dns-records-at-network-solutions-to-microsoft-365"></a>在网络解决方案中连接 DNS 记录以Microsoft 365

 如果找不到要查找的内容，请 **[查看域常见问题解答](../setup/domains-faq.yml)**。

如果网络解决方案是 DNS 托管提供商，请按照本文中的步骤验证域，并为电子邮件、Skype for Business联机等设置 DNS 记录。

在网络解决方案中添加这些记录后，域将设置为使用Microsoft 服务。

> [!NOTE]
> DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。

## <a name="add-a-txt-record-for-verification"></a>添加 TXT 记录进行验证

在将域用于 Microsoft 之前，必须确保你拥有该域。如果你能够在域注册机构处登录到你的帐户并创建 DNS 记录，便可向 Microsoft 证明你是域所有者。

> [!NOTE]
> 此记录仅用于验证您是否拥有自己的域；它不会影响其他任何内容。 如果需要，您可以以后将其删除。

1. 若要开始，请使用[此链接](https://www.networksolutions.com/manage-it)转到 Network Solutions 上你的域页面。系统将会提示您登录。

1. 在登陆页上，选择 **“域名**”。

1. 选中要修改的域旁边的复选框。

1. 在 **“操作”** 下，选择三个点，然后从下拉列表中选择 **“管理** ”。

   :::image type="content" source="../../media/dns-networksolutions/networksolutions-domains-1.png" alt-text="从下拉列表中选择“管理”。":::

1. 向下滚动以选择 **“高级工具”**，然后在 **“高级 DNS 记录**”旁边选择 **“管理**”。

   :::image type="content" source="../../media/dns-networksolutions/networksolutions-domains-2.png" alt-text="在“高级 DNS 记录”旁边，选择“管理”。":::

   可能需要选择 **“继续** ”才能访问“管理高级 DNS 记录”页。

1. 在“管理高级 DNS 记录”页上，选择 **“+添加记录**”。

   :::image type="content" source="../../media/dns-networksolutions/networksolutions-domains-add-record.png" alt-text="选择“+添加记录”。":::

1. 在 **“类型**”下，从下拉列表中选择 **TXT** 。

1. In the boxes for the new record, type or copy and paste the values in the following table.

   |引用|TXT Value|TTL|
   |---|---|---|
   |@  <br/> (The system will change this value to **@ (None)** when you save the record.)|MS=ms *XXXXXXXX*  <br/> **注意：** 这是一个示例。 在这里使用表中的特定“**目标地址或指向的地址**”值。  [如何查找此项？](../get-help-with-domains/information-for-dns-records.md)|3600|

1. 选择 **“添加**”。

   :::image type="content" source="../../media/dns-networksolutions/networksolutions-domains-add.png" alt-text="选择“添加”。":::

   > [!NOTE]
   > 选择右上角的 **经典视图** 以查看创建的 TXT 记录。

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

1. 若要开始，请使用[此链接](https://www.networksolutions.com/manage-it)转到 Network Solutions 上你的域页面。系统将会提示您登录。

1. 在登陆页上，选择 **“域名**”。

1. 选中要修改的域旁边的复选框。

1. 在 **“操作”** 下，选择三个点，然后在下拉列表中选择 **“管理** ”。

   :::image type="content" source="../../media/dns-networksolutions/networksolutions-domains-1.png" alt-text="从下拉列表中选择“管理”。":::

1. 向下滚动以选择 **“高级工具”**，然后在 **“高级 DNS 记录**”旁边选择 **“管理**”。

   :::image type="content" source="../../media/dns-networksolutions/networksolutions-domains-2.png" alt-text="在“高级 DNS 记录”旁边，选择“管理”。":::

   可能需要选择 **“继续** ”才能访问“管理高级 DNS 记录”页。

1. 在“管理高级 DNS 记录”页上，选择 **“+添加记录**”。

   :::image type="content" source="../../media/dns-networksolutions/networksolutions-domains-add-record.png" alt-text="选择“+添加记录”。":::

1. 在 **“类型**”下，从下拉列表中选择 **MX** 。

1. 在新记录的框中，键入或复制并粘贴下表中的值。

   |引用|邮件服务器|优先级|TTL|
   |---|---|---|---|
   |@|*\<domain-key\>*.mail.protection.outlook.com  <br/> **此值不能以句点 (.) 结尾** <br/> **注意：** 从 Microsoft 帐户获取你 *\<domain-key\>* 。 如何查找此内容？[](../get-help-with-domains/information-for-dns-records.md)|0  <br/> 有关优先级的详细信息，请参阅[什么是 MX 优先级？](../setup/domains-faq.yml)|1 Hour|

1. 选择 **“添加**”。

   :::image type="content" source="../../media/dns-networksolutions/networksolutions-domains-MX-add.png" alt-text="选择“添加”。":::

   > [!NOTE]
   > 选择右上角的 **经典视图** 以查看创建的 TXT 记录。

1. 如果有任何其他 MX 记录，请通过选择编辑工具删除所有记录，然后 **删除** 每个记录。

   :::image type="content" source="../../media/dns-networksolutions/networksolutions-domains-edit.png" alt-text="选择“编辑”工具。":::

## <a name="add-the-cname-record-required-for-microsoft"></a>添加 Microsoft 所需的 CNAME 记录

1. 若要开始，请使用[此链接](https://www.networksolutions.com/manage-it)转到 Network Solutions 上你的域页面。系统将会提示您登录。

1. 在登陆页上，选择 **“域名**”。

1. 选中要修改的域旁边的复选框。

1. 在 **“操作”** 下，选择三个点，然后在下拉列表中选择 **“管理** ”。

   :::image type="content" source="../../media/dns-networksolutions/networksolutions-domains-1.png" alt-text="从下拉列表中选择“管理”。":::

1. 选择 **“高级工具”**，然后在 **“高级 DNS 记录**”旁边选择 **“管理**”。

   :::image type="content" source="../../media/dns-networksolutions/networksolutions-domains-2.png" alt-text="在“高级 DNS 记录”旁边，选择“管理”。":::

   可能需要选择 **“继续** ”才能访问“管理高级 DNS 记录”页。

1. 在“管理高级 DNS 记录”页上，选择 **“+添加记录**”。

   :::image type="content" source="../../media/dns-networksolutions/networksolutions-domains-add-record.png" alt-text="选择“+添加记录”。":::

1. 在 **“类型**”下，从下拉列表中选择 **CNAME** 。

   :::image type="content" source="../../media/dns-networksolutions/networksolutions-domains-cname.png" alt-text="从下拉列表中选择 CNAME 类型。":::

1. 在 CNAME 记录的框中，键入或复制并粘贴下表中的值。

   |引用|主机名|别名|TTL|
   |---|---|---|---|
   |其他主机|自动发现|autodiscover.outlook.com **此值不能以句点 (.) 结尾** <br/> 1 Hour|

   :::image type="content" source="../../media/dns-networksolutions/networksolutions-domains-cname-values.png" alt-text="键入或复制表中的 CNAME 值并将其粘贴到窗口中。":::

1. 选择 **“添加**”。

   > [!NOTE]
   > 选择右上角的 **经典视图** 以查看创建的记录。

## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>为 SPF 添加 TXT 记录以帮助防止垃圾邮件

> [!IMPORTANT]
> 一个域所拥有的 SPF 的 TXT 记录不能超过一个。 如果域具有多个 SPF 记录，你将收到电子邮件错误，其中随附发送和垃圾邮件分类问题。 如果你的域已有 SPF 记录，请不要为 Microsoft 创建新记录。 而是将所需的 Microsoft 值添加到当前记录，以便具有包含这两组值的  *单*  个 SPF 记录。

1. 若要开始，请使用[此链接](https://www.networksolutions.com/manage-it)转到 Network Solutions 上你的域页面。系统将会提示您登录。

1. 在登陆页上，选择 **“域名**”。

1. 选中要修改的域旁边的复选框。

1. 在 **“操作”** 下，选择三个点，然后在下拉列表中选择 **“管理** ”。

   :::image type="content" source="../../media/dns-networksolutions/networksolutions-domains-1.png" alt-text="从下拉列表中选择“管理”。":::

1. 选择 **“高级工具”**，然后在 **“高级 DNS 记录**”旁边选择 **“管理**”。

   :::image type="content" source="../../media/dns-networksolutions/networksolutions-domains-2.png" alt-text="在“高级 DNS 记录”旁边，选择“管理”。":::

   可能需要选择 **“继续** ”才能访问“管理高级 DNS 记录”页。

1. 在“管理高级 DNS 记录”页上，选择 **“+添加记录**”。

   :::image type="content" source="../../media/dns-networksolutions/networksolutions-domains-add-record.png" alt-text="选择“+添加记录”。":::

1. 在 **“类型**”下，从下拉列表中选择 **TXT** 。

   :::image type="content" source="../../media/dns-networksolutions/networksolutions-domains-TXT.png" alt-text="从“类型”下拉列表中选择 TXT。":::

1. In the boxes for the new record, type or copy and paste the following values.

   |引用|TXT Value|TTL
   |---|---|---|
   |@  <br/> (The system will change this value to **@ (None)** when you save the record.)|v=spf1 include:spf.protection.outlook.com -all  <br/> **注意：** 建议复制粘贴此条目，以保证正确保留所有空格。|1 Hour|

1. 选择 **“添加**”。

   :::image type="content" source="../../media/dns-networksolutions/networksolutions-domains-add.png" alt-text="选择“添加”。":::

   > [!NOTE]
   > 选择右上角的 **经典视图** 以查看创建的记录。

## <a name="advanced-option-skype-for-business"></a>高级选项：Skype for Business

仅当组织对联机通信服务（例如聊天、电话会议和视频呼叫）使用Skype for Business时，除了Microsoft Teams，才选择此选项。 Skype需要 4 条记录：2 条用于用户到用户通信的 SRV 记录，以及 2 条用于登录和将用户连接到服务的 CNAME 记录。

### <a name="add-the-two-required-srv-records"></a>添加两个必需的 SRV 记录

1. 若要开始，请使用[此链接](https://www.networksolutions.com/manage-it)转到 Network Solutions 上你的域页面。系统将会提示您登录。

1. 在登陆页上，选择 **“域名**”。

1. 选中要修改的域旁边的复选框。

1. 在 **“操作”** 下，选择三个点，然后在下拉列表中选择 **“管理** ”。

   :::image type="content" source="../../media/dns-networksolutions/networksolutions-domains-1.png" alt-text="从下拉列表中选择“管理”。":::

1. 选择 **“高级工具”**，然后在 **“高级 DNS 记录**”旁边选择 **“管理**”。

   :::image type="content" source="../../media/dns-networksolutions/networksolutions-domains-2.png" alt-text="在“高级 DNS 记录”旁边，选择“管理”。":::

   可能需要选择 **“继续** ”才能访问“管理高级 DNS 记录”页。

1. 在“管理高级 DNS 记录”页上，选择 **“+添加记录**”。

   :::image type="content" source="../../media/dns-networksolutions/networksolutions-domains-add-record.png" alt-text="选择“+添加记录”。":::

1. 在 **“类型**”下，从下拉列表中选择 **SRV** 。

   :::image type="content" source="../../media/dns-networksolutions/networksolutions-domains-srv.png" alt-text="从“类型”下拉列表中选择 SRV。":::

1. 在两个新记录的框中，键入或复制并粘贴下表中的值。

    (从下拉列表中选择 **服务** 和 **协议** 值。) 

   |类型|服务|协议|粗细|端口|Target|优先级|TTL|
   |---|---|---|---|---|---|---|---|
   |SRV|_sip|TLS|100|443|sipdir.online.lync.com  <br/> **此值不能以句点 (.) 结尾**|1|1 Hour|
   |SRV|_sipfederationtls|TCP|100|5061|sipfed.online.lync.com  <br/> **此值不能以句点 (.) 结尾**|1|1 Hour|

1. 选择 **“添加**”。

   :::image type="content" source="../../media/dns-networksolutions/networksolutions-domains-srv-add.png" alt-text="选择“添加”。":::

   > [!NOTE]
   > 选择右上角的 **经典视图** 以查看创建的记录。

1. 通过从表的第二行复制值来添加其他 SRV 记录。

> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果在添加 DNS 记录后遇到邮件流问题或其他问题，请参阅[查找在添加域或 DNS 记录后遇到的问题并进行修复](../get-help-with-domains/find-and-fix-issues.md)。

### <a name="add-the-two-required-cname-records-for-skype-for-business"></a>为Skype for Business添加两条所需的 CNAME 记录

1. 若要开始，请使用[此链接](https://www.networksolutions.com/manage-it)转到 Network Solutions 上你的域页面。系统将会提示您登录。

1. 在登陆页上，选择 **“域名**”。

1. 选中要修改的域旁边的复选框。

1. 在 **“操作”** 下，选择三个点，然后在下拉列表中选择 **“管理** ”。

   :::image type="content" source="../../media/dns-networksolutions/networksolutions-domains-1.png" alt-text="从下拉列表中选择“管理”。":::

1. 选择 **“高级工具”**，然后在 **“高级 DNS 记录**”旁边选择 **“管理**”。

   :::image type="content" source="../../media/dns-networksolutions/networksolutions-domains-2.png" alt-text="在“高级 DNS 记录”旁边，选择“管理”。":::

   可能需要选择 **“继续** ”才能访问“管理高级 DNS 记录”页。

1. 在“管理高级 DNS 记录”页上，选择 **“+ 添加记录**”。

   :::image type="content" source="../../media/dns-networksolutions/networksolutions-domains-add-record.png" alt-text="选择“+添加记录”。":::

1. 在 **“类型**”下，从下拉列表中选择 **CNAME** 。

   :::image type="content" source="../../media/dns-networksolutions/networksolutions-domains-cname.png" alt-text="从下拉列表中选择 CNAME 类型。":::

1. 在 CNAME 记录的框中，键入或复制并粘贴下表中的值。

   |类型|引用|主机名|别名|TTL|
   |---|---|---|---|---|
   |CNAME|其他主机|sip|sipdir.online.lync.com  <br/> **此值不能以句点 (.) 结尾**|1 小时|
   |CNAME|其他主机|lyncdiscover|webdir.online.lync.com  <br/> **此值不能以句点 (.) 结尾**|1 Hour|

   :::image type="content" source="../../media/dns-networksolutions/networksolutions-domains-cname-values.png" alt-text="键入或复制表中的 CNAME 值并将其粘贴到窗口中。":::

1. 选择 **“添加**”。

   > [!NOTE]
   > 选择右上角的 **经典视图** 以查看创建的记录。

1. 通过从表的第二行复制值来添加其他 CNAME 记录。

> [!NOTE]
> DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。

## <a name="advanced-option-intune-and-mobile-device-management-for-microsoft-365"></a>高级选项：适用于Microsoft 365的Intune和移动设备管理

此服务可帮助保护和远程管理连接到域的移动设备。 移动设备管理需要 2 条 CNAME 记录，以便用户可以将设备注册到服务。

### <a name="add-the-two-required-cname-records-for-mobile-device-management"></a>添加移动设备管理所需的两条 CNAME 记录

1. 若要开始，请使用[此链接](https://www.networksolutions.com/manage-it)转到 Network Solutions 上你的域页面。系统将会提示您登录。

1. 在登陆页上，选择 **“域名**”。

1. 选中要修改的域旁边的复选框。

1. 在 **“操作”** 下，选择三个点，然后在下拉列表中选择 **“管理** ”。

   :::image type="content" source="../../media/dns-networksolutions/networksolutions-domains-1.png" alt-text="从下拉列表中选择“管理”。":::

1. 选择 **“高级工具”**，然后在 **“高级 DNS 记录**”旁边选择 **“管理**”。

   :::image type="content" source="../../media/dns-networksolutions/networksolutions-domains-2.png" alt-text="在“高级 DNS 记录”旁边，选择“管理”。":::

   可能需要选择 **“继续** ”才能访问“管理高级 DNS 记录”页。

1. 在“管理高级 DNS 记录”页上，选择 **“+添加记录**”。

   :::image type="content" source="../../media/dns-networksolutions/networksolutions-domains-add-record.png" alt-text="选择“+添加记录”。":::

1. 在 **“类型**”下，从下拉列表中选择 **CNAME** 。

   :::image type="content" source="../../media/dns-networksolutions/networksolutions-domains-cname.png" alt-text="从下拉列表中选择 CNAME 类型。":::

1. 在 CNAME 记录的框中，键入或复制并粘贴下表中的值。

   |类型|引用|主机名|别名|TTL|
   |---|---|---|---|---|
   |CNAME|其他主机|enterpriseregistration|enterpriseregistration.windows.net  <br/> **此值不能以句点 (.) 结尾**|1 小时|
   |CNAME|其他主机|enterpriseenrollment|enterpriseenrollment-s.manage.microsoft.com  <br/> **此值不能以句点 (.) 结尾**|1 Hour|

   :::image type="content" source="../../media/dns-networksolutions/networksolutions-domains-cname-values.png" alt-text="键入或复制表中的 CNAME 值并将其粘贴到窗口中。":::

1. 选择 **“添加**”。

   > [!NOTE]
   > 选择右上角的 **经典视图** 以查看创建的记录。

1. 通过从表的第二行复制值来添加其他 CNAME 记录。

> [!NOTE]
> DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。

