---
title: 在 Cloudflare 连接 DNS 记录以Microsoft 365
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
ms.assetid: 84acd4fc-6eec-4d00-8bed-568f036ae2af
description: 了解如何在适用于 Microsoft 的 Cloudflare 中验证域并设置电子邮件、Skype for Business Online 和其他服务的 DNS 记录。
ms.openlocfilehash: 164a681cccac3385d2ca963ac58706c8e743bc1e
ms.sourcegitcommit: ac0ae5c2888e2b323e36bad041a4abef196c9c96
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/12/2022
ms.locfileid: "64780360"
---
# <a name="connect-your-dns-records-at-cloudflare-to-microsoft-365"></a>在 Cloudflare 连接 DNS 记录以Microsoft 365

 如果找不到要查找的内容，请 **[查看域常见问题解答](../setup/domains-faq.yml)**。

如果 Cloudflare 是 DNS 托管提供商，请按照本文中的步骤验证域，并为电子邮件、Skype for Business Online 等设置 DNS 记录。

## <a name="before-you-begin"></a>准备工作

有两个选项可用于设置域的 DNS 记录：

- [**使用域连接**](#use-domain-connect-to-verify-and-set-up-your-domain)如果尚未使用其他电子邮件服务提供商设置域，请使用域连接步骤自动验证和设置要与Microsoft 365配合使用的新域。

    或

- [**使用手动步骤**](#create-dns-records-with-manual-setup) 使用以下手动步骤验证域，并选择何时以及向域注册机构添加哪些记录。 这样就可以在方便的时候设置新的 MX (邮件) 记录。

## <a name="use-domain-connect-to-verify-and-set-up-your-domain"></a>使用域连接验证和设置域

请按照以下步骤使用Microsoft 365自动验证和设置 Cloudflare 域：

1. 在Microsoft 365 管理中心中，选择 **设置** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">**域**</a>，然后选择要设置的域。

1. 选择三个点 (多个操作) \> 选择 **“开始”设置**。

    :::image type="content" source="../../media/dns-IONOS/IONOS-DomainConnects-2.png" alt-text="选择“开始”设置。":::

1. 在“如何连接域”上？页面，选择 **“继续**”。

1. 在“添加 DNS 记录”页上，选择 **“添加 DNS 记录**”。

1. 在 Cloudflare 登录页上，登录到帐户，然后选择 **“授权**”。

    这会完成Microsoft 365的域设置。

## <a name="create-dns-records-with-manual-setup"></a>使用手动设置创建 DNS 记录

在 Cloudflare 中添加这些记录后，域将设置为使用Microsoft 365服务。

> [!NOTE]
> DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。

### <a name="change-your-domains-nameserver-ns-records"></a>更改域的名称服务器 (NS) 记录

> [!IMPORTANT]
> 必须在购买和注册域的域注册机构中执行此过程。

注册 Cloudflare 时，将使用 Cloudflare 安装过程添加域。

添加的域是从 Cloudflare 或单独的域注册机构购买的。 若要在Microsoft 365中验证和创建域的 DNS 记录，首先需要更改域注册机构中的名称服务器，以便它们使用 Cloudflare 名称服务器。

若要在域注册机构的网站上更改域的名称服务器，请执行以下步骤。

1. 在域注册机构的网站上查找您可以在其中编辑您的域的名称服务器的区域。

2. 使用下表中的值创建两个名称服务器记录，或编辑现有名称服务器记录，使其与这些值匹配。

    |类型|值|
    |---|---|
    |首选名称服务器|使用 Cloudflare 提供的 nameserver 值。|
    |次要名称服务器|使用 Cloudflare 提供的 nameserver 值。|

    > [!TIP]
    > You should use at least two name server records. 如果列出了任何其他名称服务器，则应删除它们。

3. 保存所做的更改。

> [!NOTE]
> Your nameserver record updates may take up to several hours to update across the Internet's DNS system. 然后，你的 Microsoft 电子邮件和其他服务将全部设置为使用你的域。

### <a name="add-a-txt-record-for-verification"></a>添加 TXT 记录进行验证

在将域用于 Microsoft 之前，必须确保你拥有该域。如果你能够在域注册机构处登录到你的帐户并创建 DNS 记录，便可向 Microsoft 证明你是域所有者。

> [!NOTE]
> 此记录仅用于验证您是否拥有自己的域；它不会影响其他任何内容。 如果需要，您可以以后将其删除。

1. 若要开始，请使用 [此链接](https://www.cloudflare.com/a/login)转到 Cloudflare 的域页面。 系统将会提示您先登录。

1. 在主页上，选择要更新的域。

    :::image type="content" source="../../media/dns-cloudflare/cloudflare-domains-1.png" alt-text="选择要更新的域。":::

1. 在域的“概述”页上，选择 **“DNS**”。

    :::image type="content" source="../../media/dns-cloudflare/cloudflare-domains-2.png" alt-text="选择 DNS。":::

1. 在 DNS 管理页上，选择 **“+添加记录**”。

   :::image type="content" source="../../media/dns-cloudflare/cloudflare-domains-add-record.png" alt-text="选择“添加记录”。":::

1. 从下拉列表中选择 TXT 类型，然后键入或复制并粘贴此表中的值。

    |类型|名称|TTL|内容|
    |---|---|---|:----|
    |TXT|@|30 分钟|MS=*msXXXXXXXX* <br/> **注意：** 这是一个示例。 在这里使用表中的特定“**目标地址或指向的地址**”值。 [如何查找此项？](../get-help-with-domains/information-for-dns-records.md)|

1. 选择“**保存**”。

   :::image type="content" source="../../media/dns-cloudflare/cloudflare-domains-TXT-save.png" alt-text="选择“添加记录”。":::

   请在继续之前等待数分钟，以便您刚刚创建的记录可以通过 Internet 完成更新。

现在，你已在域注册机构的站点上添加了记录，你将返回到 Microsoft 并搜索记录。 当 Microsof 找到正确的 TXT 记录时，表明域已通过验证。

若要验证Microsoft 365中的记录，

1. 在管理中心，转到 **设置** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">**域**</a>。

1. 在“域”页上，选择要验证的域，然后选择 **“开始设置**”。

    :::image type="content" source="../../media/dns-IONOS/IONOS-DomainConnects-2.png" alt-text="选择“开始”设置。":::

1. 选择 **继续**。

1. 在“**验证域**”页面上，选择“**验证**”。

> [!NOTE]
> DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。

### <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>添加一条 MX 记录，确保发往你的域的电子邮件将会发送到 Microsoft

1. 若要开始，请使用 [此链接](https://www.cloudflare.com/a/login)转到 Cloudflare 的域页面。 系统将会提示您先登录。

1. 在主页上，选择要更新的域。

   :::image type="content" source="../../media/dns-cloudflare/cloudflare-domains-1.png" alt-text="选择要更新的域。":::

1. 在域的“概述”页上，选择 **“DNS**”。

   :::image type="content" source="../../media/dns-cloudflare/cloudflare-domains-2.png" alt-text="选择 DNS。":::

1. 在 DNS 管理页上，选择 **“+添加记录**”。

   :::image type="content" source="../../media/dns-cloudflare/cloudflare-domains-add-record.png" alt-text="选择“添加记录”。":::

1. 从下拉列表中选择 MX 类型，然后键入或复制并粘贴此表中的值。

   |类型|名称|邮件服务器|TTL|优先级|
   |---|---|---|---|---|
   |MX|@|*\<domain-key\>*.mail.protection.outlook.com <br/> **注意：** 从Microsoft 365帐户获取你 *\<domain-key\>*。 [如何查找此项？](../get-help-with-domains/information-for-dns-records.md)|30 分钟|1 <br/> 有关优先级的详细信息，请参阅[什么是 MX 优先级？](../setup/domains-faq.yml) <br/>|

1. 选择“**保存**”。

   :::image type="content" source="../../media/dns-cloudflare/cloudflare-domains-mx-save.png" alt-text="选择“添加记录”。":::

1. 如果 **MX 记录** 部分中列出了任何其他 MX 记录，请选择 **“编辑**”将其删除，然后选择 **“删除**”。

   :::image type="content" source="../../media/dns-cloudflare/cloudflare-domains-mx-delete.png" alt-text="选择“删除”。":::

1. 在确认对话框中，选择 **“删除** ”以确认所做的更改。

### <a name="add-the-cname-record-required-for-microsoft"></a>添加 Microsoft 所需的 CNAME 记录

1. 若要开始，请使用 [此链接](https://www.cloudflare.com/a/login)转到 Cloudflare 的域页面。 系统将会提示您先登录。

1. 在主页上，选择要更新的域。

   :::image type="content" source="../../media/dns-cloudflare/cloudflare-domains-1.png" alt-text="选择要更新的域。":::

1. 在域的“概述”页上，选择 **“DNS**”。

   :::image type="content" source="../../media/dns-cloudflare/cloudflare-domains-2.png" alt-text="选择 DNS。":::

1. 在 **DNS 管理** 页上，选择 **“+添加记录”**

   :::image type="content" source="../../media/dns-cloudflare/cloudflare-domains-add-record.png" alt-text="选择“添加记录”。":::

1. 从下拉列表中选择 CNAME 类型，然后键入或复制并粘贴此表中的值。

    |类型|名称|Target|TTL|
    |---|---|---|---|
    |CNAME|自动发现|autodiscover.outlook.com|自动|

1. 选择“**保存**”。

   :::image type="content" source="../../media/dns-cloudflare/cloudflare-domains-cname-save.png" alt-text="选择“保存”。":::

### <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>为 SPF 添加 TXT 记录以帮助防止垃圾邮件

> [!IMPORTANT]
> 一个域所拥有的 SPF 的 TXT 记录不能超过一个。 如果域具有多个 SPF 记录，你将收到电子邮件错误，其中随附发送和垃圾邮件分类问题。 如果你的域已有 SPF 记录，请不要为 Microsoft 365 创建新记录。 相反，请将所需的Microsoft 365值添加到当前记录，以便具有包含这两组值的 *单* 个 SPF 记录。

1. 若要开始，请使用 [此链接](https://www.cloudflare.com/a/login)转到 Cloudflare 的域页面。 系统将会提示您先登录。

1. 在主页上，选择要更新的域。

    :::image type="content" source="../../media/dns-cloudflare/cloudflare-domains-1.png" alt-text="选择要更新的域。":::

1. 在域的“概述”页上，选择 **“DNS**”。

    :::image type="content" source="../../media/dns-cloudflare/cloudflare-domains-2.png" alt-text="选择 DNS。":::

1. 在 DNS 管理页上，选择 **“+添加记录**”。

   :::image type="content" source="../../media/dns-cloudflare/cloudflare-domains-add-record.png" alt-text="选择“添加记录”。":::

1. 从下拉列表中选择 TXT 类型，然后键入或复制并粘贴此表中的值。

    |类型|名称|TTL|内容|
    |---|---|---|---|
    |TXT|@|30 分钟|v=spf1 include:spf.protection.outlook.com -all <br/> **注意：** 建议复制粘贴此条目，以保证正确保留所有空格。|

1. 选择“**保存**”。

   :::image type="content" source="../../media/dns-cloudflare/cloudflare-domains-TXT-save.png" alt-text="选择“保存”。":::

## <a name="advanced-option-skype-for-business"></a>高级选项：Skype for Business

仅当组织对联机通信服务（例如聊天、电话会议和视频呼叫）使用Skype for Business时，除了Microsoft Teams，才选择此选项。 Skype需要 4 条记录：2 条用于用户到用户通信的 SRV 记录，以及 2 条用于登录和将用户连接到服务的 CNAME 记录。

### <a name="add-the-two-required-srv-records"></a>添加两个必需的 SRV 记录

> [!IMPORTANT]
> 请记住，Cloudflare 负责使此功能可用。 如果看到以下步骤与当前 Cloudflare GUI (图形用户界面) 之间的差异，请利用 [Cloudflare Community](https://community.cloudflare.com/)。

1. 若要开始，请使用 [此链接](https://www.cloudflare.com/a/login)转到 Cloudflare 的域页面。 系统将会提示您先登录。

1. 在主页上，选择要更新的域。

    :::image type="content" source="../../media/dns-cloudflare/cloudflare-domains-1.png" alt-text="选择要更新的域。":::

1. 在域的“概述”页上，选择 **“DNS**”。

    :::image type="content" source="../../media/dns-cloudflare/cloudflare-domains-2.png" alt-text="选择 DNS。":::

1. 在 DNS 管理页上，选择 **“+添加记录”**

   :::image type="content" source="../../media/dns-cloudflare/cloudflare-domains-add-record.png" alt-text="选择“添加记录”。":::

1. 从下拉列表中选择 SRV 类型，然后键入或复制并粘贴此表中的值。

    |类型|名称|服务|协议|TTL|优先级|粗细|端口|Target|
    |---|---|---|---|---|---|---|---|---|
    |SRV|使用 *domain_name*;例如，contoso.com|_sip|TLS|30 分钟|100|1|443|sipfed.online.lync.com|
    |SRV|_sipfederationtls|TCP|使用 *domain_name*;例如，contoso.com|30 分钟|100|1|5061|sipfed.online.lync.com|

1. 选择“**保存**”。

   :::image type="content" source="../../media/dns-cloudflare/cloudflare-domains-srv-save.png" alt-text="选择“保存”。":::

1. 通过从表的第二行复制值来添加其他 SRV 记录。

> [!NOTE]
> DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。

### <a name="add-the-two-required-cname-records-for-skype-for-business"></a>为Skype for Business添加两条所需的 CNAME 记录

1. 若要开始，请使用 [此链接](https://www.cloudflare.com/a/login)转到 Cloudflare 的域页面。 系统将会提示您先登录。

1. 在主页上，选择要更新的域。

    :::image type="content" source="../../media/dns-cloudflare/cloudflare-domains-1.png" alt-text="选择要更新的域。":::

1. 在域的“概述”页上，选择 **“DNS**”。

    :::image type="content" source="../../media/dns-cloudflare/cloudflare-domains-2.png" alt-text="选择 DNS。":::

1. 在 DNS 管理页上，选择 **“+添加记录”**

   :::image type="content" source="../../media/dns-cloudflare/cloudflare-domains-add-record.png" alt-text="选择“添加记录”。":::

1. 从下拉列表中选择 CNAME 类型，然后键入或复制并粘贴此表中的值。

    |类型|名称|Target|TTL|
    |---|---|---|---|
    |CNAME|sip|sipdir.online.lync.com. <br/> **此值必须以句点 (.) 结尾。**|1 小时|
    |CNAME|lyncdiscover|webdir.online.lync.com. <br/> **此值必须以句点 (.) 结尾。**|1 Hour|

1. 选择 **“保存**”。

   :::image type="content" source="../../media/dns-cloudflare/cloudflare-domains-cname-save.png" alt-text="选择“保存”。":::

1. 通过从表的第二行复制值来添加其他 CNAME 记录。

> [!NOTE]
> DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。

## <a name="advanced-option-intune-and-mobile-device-management-for-microsoft-365"></a>高级选项：适用于Microsoft 365的Intune和移动设备管理

此服务可帮助保护和远程管理连接到域的移动设备。 移动设备管理需要 2 条 CNAME 记录，以便用户可以将设备注册到服务。

### <a name="add-the-two-required-cname-records-for-mobile-device-management"></a>添加移动设备管理所需的两条 CNAME 记录

1. 若要开始，请使用 [此链接](https://www.cloudflare.com/a/login)转到 Cloudflare 的域页面。 系统将会提示您先登录。

1. 在主页上，选择要更新的域。

    :::image type="content" source="../../media/dns-cloudflare/cloudflare-domains-1.png" alt-text="选择要更新的域。":::

1. 在域的“概述”页上，选择 **“DNS**”。

    :::image type="content" source="../../media/dns-cloudflare/cloudflare-domains-2.png" alt-text="选择 DNS。":::

1. 在 DNS 管理页上，选择 **“+添加记录”**

   :::image type="content" source="../../media/dns-cloudflare/cloudflare-domains-add-record.png" alt-text="选择“添加记录”。":::

1. 从下拉列表中选择 CNAME 类型，然后键入或复制并粘贴此表中的值。

    |类型|名称|Target|TTL|
    |---|---|---|---|
    |CNAME|enterpriseregistration|enterpriseregistration.windows.net. <br/> **此值必须以句点 (.) 结尾。**|1 小时|
    |CNAME|enterpriseenrollment|enterpriseenrollment-s.manage.microsoft.com. <br/> **此值必须以句点 (.) 结尾。**|1 Hour|

1. 选择“**保存**”。

   :::image type="content" source="../../media/dns-cloudflare/cloudflare-domains-cname-save.png" alt-text="选择“保存”。":::

1. 通过从表的第二行复制值来添加其他 CNAME 记录。

> [!NOTE]
> DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。
