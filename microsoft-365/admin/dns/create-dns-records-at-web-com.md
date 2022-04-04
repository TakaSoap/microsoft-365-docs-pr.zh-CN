---
title: 连接 DNS 记录，web.com Microsoft 365
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
description: 了解如何验证域，并设置电子邮件、Skype for Business Online 和其他服务的 DNS 记录，web.com Microsoft。
ms.openlocfilehash: 612c22b518402fccaf9ced76b2506aa15c0e89f6
ms.sourcegitcommit: a4729532278de62f80f2160825d446f6ecd36995
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/31/2022
ms.locfileid: "64568403"
---
# <a name="connect-your-dns-records-at-webcom-to-microsoft-365"></a>连接 DNS 记录，web.com Microsoft 365

 如果找不到要查找的内容，请 **[查看域常见问题解答](../setup/domains-faq.yml)**。

如果 web.com DNS 托管提供商，请按照本文中的步骤验证域，并设置电子邮件、Skype for Business Online 等的 DNS 记录。

在添加这些记录 web.com，域将设置为使用Microsoft 服务。

> [!NOTE]
> DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。

## <a name="change-your-domains-nameserver-ns-records"></a>更改域的名称服务器 (NS) 记录

> [!IMPORTANT]
> 必须在购买和注册域的域注册机构中执行此过程。

注册域 web.com，即使用"设置"过程 web.com **域** 。

若要在 Microsoft 中验证和创建域的 DNS 记录，首先需要更改域注册机构中的名称服务器，以便它们使用 web.com 服务器。

若要在域注册机构的网站上更改域的名称服务器，请执行以下步骤。

1. 在域注册机构的网站上查找您可以在其中编辑您的域的名称服务器的区域。

2. 使用下表中的值创建两个名称机记录，或编辑现有名称机记录，以便它们与这些值匹配。

    |类型|值|
    |---|---|
    |首选名称服务器|使用由 web.com 提供的名称 web.com。|
    |次要名称服务器|使用由 web.com 提供的名称 web.com。|

    > [!TIP]
    > You should use at least two name server records. 如果列出了任何其他名称服务器，您应该将其删除。

3. 保存所做的更改。

> [!NOTE]
> Your nameserver record updates may take up to several hours to update across the Internet's DNS system. 然后，你的 Microsoft 电子邮件和其他服务都将设置为使用你的域。

## <a name="add-a-txt-record-for-verification"></a>添加 TXT 记录进行验证

在将域用于 Microsoft 之前，必须确保你拥有该域。如果你能够在域注册机构处登录到你的帐户并创建 DNS 记录，便可向 Microsoft 证明你是域所有者。

> [!NOTE]
> 此记录仅用于验证您是否拥有自己的域；它不会影响其他任何内容。 如果需要，您可以以后将其删除。

1. To get started， go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp). 首先登录。

1. 在登录页面上，选择 **"域名"**。

1. 在 **"操作**"下，选择三个点，然后在下拉列表中选择"管理"。

    :::image type="content" source="../../media/dns-webcom/webcom-domains-1.png" alt-text="从下拉列表中选择&quot;管理&quot;。":::

1. 向下滚动以选择" **高级工具"，** 在"高级 DNS 记录" **旁边**，选择" **管理"**。

    您可能必须选择" **继续"** 才能访问"管理高级 DNS 记录"页。

    :::image type="content" source="../../media/dns-webcom/webcom-domains-2.png" alt-text="在&quot;高级 DNS 记录&quot;旁边，选择&quot;管理&quot;。":::

1. 在"管理高级 DNS 记录"页上，选择" **+ 添加记录"**。

    :::image type="content" source="../../media/dns-webcom/webcom-domains-add-record.png" alt-text="选择&quot; + 添加记录&quot;。":::

1. 在 **"类型**"下，从下拉列表中选择 **"TXT** "。

    :::image type="content" source="../../media/dns-webcom/webcom-domains-TXT.png" alt-text="从&quot;类型&quot;下拉列表中选择&quot;TXT&quot;。":::

1. 选择或复制并粘贴下表中的值。

    |Refers|TXT 值|TTL|
    |---|---|:----|
    |@|MS=*msXXXXXXXX* <br/> **注意：** 这是一个示例。 在这里使用表中的特定“**目标地址或指向的地址**”值。 [如何查找此项？](../get-help-with-domains/information-for-dns-records.md)|1 小时|

1. 选择 **"添加"**。

    请等待几分钟，然后验证新的 TXT 记录，以便刚刚创建的记录可以通过 Internet 更新。

在在域注册机构网站添加了记录后，你将返回到 Microsoft 并请求记录。 Microsof 找到正确的 TXT 记录表明域已通过验证。

若要验证记录是否Microsoft 365：

1. 在管理中心，转到 **"设置** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">**域"**</a>。

1. 在"域"页面上，选择要验证的域，然后选择"开始 **设置"**。

    :::image type="content" source="../../media/dns-IONOS/IONOS-DomainConnects-2.png" alt-text="选择&quot;开始设置&quot;。":::

1. 选择 **继续**。

1. 在“**验证域**”页面上，选择“**验证**”。

> [!NOTE]
> DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。

## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>添加一条 MX 记录，确保发往你的域的电子邮件将会发送到 Microsoft

1. To get started， go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp). 首先登录。

1. 在登录页面上，选择 **"域名"**。

1. 在 **"操作**"下，选择三个点，然后在下拉列表中选择"管理"。

    :::image type="content" source="../../media/dns-webcom/webcom-domains-1.png" alt-text="从下拉列表中选择&quot;管理&quot;。":::

1. 向下滚动以选择" **高级工具"，** 在"高级 DNS 记录" **旁边**，选择" **管理"**。

    您可能必须选择" **继续"** 才能访问"管理高级 DNS 记录"页。

    :::image type="content" source="../../media/dns-webcom/webcom-domains-2.png" alt-text="在&quot;高级 DNS 记录&quot;旁边，选择&quot;管理&quot;。":::

1. 在"管理高级 DNS 记录"页上，选择" **+ 添加记录"**。

    :::image type="content" source="../../media/dns-webcom/webcom-domains-add-record.png" alt-text="选择&quot; + 添加记录&quot;。":::

1. 在 **"类型**"下，从下拉列表中选择 **"MX** "。

1. 选择或复制并粘贴下表中的值。

    |引用|邮件服务器|优先级|TTL|
    |---|---|---|---|
    |@|*\<domain-key\>*.mail.protection.outlook.com <br/> **注意：***\<domain-key\>* 从 Microsoft 管理中心获取你。 [如何查找此项？](../get-help-with-domains/information-for-dns-records.md)|有关优先级的详细信息，请参阅[什么是 MX 优先级？](../setup/domains-faq.yml) <br/> 1|1 Hour|

1. 选择 **"添加"**。

    :::image type="content" source="../../media/dns-webcom/webcom-domains-mx-add.png" alt-text="选择&quot;添加&quot;。":::

1. 如果存在任何其他 MX 记录，请通过选择编辑工具删除所有记录，然后 **删除每条记录** 。

    :::image type="content" source="../../media/dns-webcom/webcom-domains-edit.png" alt-text="选择&quot;编辑&quot;。":::

## <a name="add-the-cname-record-required-for-microsoft"></a>添加 Microsoft 所需的 CNAME 记录

1. To get started， go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp). 首先登录。

1. 在登录页面上，选择 **"域名"**。

1. 在 **"操作**"下，选择三个点，然后在下拉列表中选择"管理"。

    :::image type="content" source="../../media/dns-webcom/webcom-domains-1.png" alt-text="从下拉列表中选择&quot;管理&quot;。":::

1. 向下滚动以选择" **高级工具"，** 在"高级 DNS 记录" **旁边**，选择" **管理"**。

    您可能必须选择" **继续"** 才能访问"管理高级 DNS 记录"页。

    :::image type="content" source="../../media/dns-webcom/webcom-domains-2.png" alt-text="在&quot;高级 DNS 记录&quot;旁边，选择&quot;管理&quot;。":::

1. 在"管理高级 DNS 记录"页上，选择" **+ 添加记录"**。

    :::image type="content" source="../../media/dns-webcom/webcom-domains-add-record.png" alt-text="选择&quot; + 添加记录&quot;。":::

1. 在 **"类型**"下，从下拉列表中选择 **"CNAME** "。

    :::image type="content" source="../../media/dns-webcom/webcom-domains-cname.png" alt-text="从&quot;类型&quot;下拉列表中选择&quot;CNAME&quot;。":::

1. 选择或复制并粘贴下表中的值。

    |引用|主机名|别名|TTL|
    |---|---|---|---|
    |其他主机|自动发现|autodiscover.outlook.com|1 Hour|

    :::image type="content" source="../../media/dns-webcom/webcom-domains-cname-values.png" alt-text="键入或复制 CNAME 值并将其粘贴到窗口中。":::

1. 选择 **"添加"**。

## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>为 SPF 添加 TXT 记录以帮助防止垃圾邮件

> [!IMPORTANT]
> 一个域所拥有的 SPF 的 TXT 记录不能超过一个。 如果域具有多个 SPF 记录，你将收到电子邮件错误，其中随附发送和垃圾邮件分类问题。 如果你的域已有 SPF 记录，请不要为 Microsoft 创建新记录。 相反，将所需的 Microsoft 值添加到当前记录，以便你有一 *个包含这* 两组值的 SPF 记录。

1. To get started， go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp). 首先登录。

1. 在登录页面上，选择 **"域名"**。

1. 在 **"操作**"下，选择三个点，然后在下拉列表中选择"管理"。

    :::image type="content" source="../../media/dns-webcom/webcom-domains-1.png" alt-text="从下拉列表中选择&quot;管理&quot;。":::

1. 向下滚动以选择" **高级工具"，** 在"高级 DNS 记录" **旁边**，选择" **管理"**。

    您可能必须选择" **继续"** 才能访问"管理高级 DNS 记录"页。

    :::image type="content" source="../../media/dns-webcom/webcom-domains-2.png" alt-text="在&quot;高级 DNS 记录&quot;旁边，选择&quot;管理&quot;。":::

1. 在"管理高级 DNS 记录"页上，选择" **+ 添加记录"**。

    :::image type="content" source="../../media/dns-webcom/webcom-domains-add-record.png" alt-text="选择&quot; + 添加记录&quot;。":::

1. 在 **"类型**"下，从下拉列表中选择 **"TXT** "。

    :::image type="content" source="../../media/dns-webcom/webcom-domains-TXT.png" alt-text="从&quot;类型&quot;下拉列表中选择&quot;TXT&quot;。":::

1. 选择或复制并粘贴下表中的值。

    |引用|TXT 值|TTL|
    |---|---|---|
    |@|v=spf1 include:spf.protection.outlook.com -all <br/> **注意：** 建议复制粘贴此条目，以保证正确保留所有空格。|1 Hour|

1. 选择 **"添加"**。

## <a name="advanced-option-skype-for-business"></a>高级选项：Skype for Business

只有组织对联机通信服务（Skype for Business、电话会议和视频呼叫）使用 Microsoft Teams。 Skype 4 条记录：2 条 SRV 记录用于用户到用户的通信，2 条 CNAME 记录用于登录和将用户连接到服务。

### <a name="add-the-two-required-srv-records"></a>添加两条必需的 SRV 记录

1. To get started， go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp). 首先登录。

1. 在登录页面上，选择 **"域名"**。

1. 在 **"操作**"下，选择三个点，然后在下拉列表中选择"管理"。

    :::image type="content" source="../../media/dns-webcom/webcom-domains-1.png" alt-text="从下拉列表中选择&quot;管理&quot;。":::

1. 向下滚动以选择" **高级工具"，** 在"高级 DNS 记录" **旁边**，选择" **管理"**。

    您可能必须选择" **继续"** 才能访问"管理高级 DNS 记录"页。

    :::image type="content" source="../../media/dns-webcom/webcom-domains-2.png" alt-text="在&quot;高级 DNS 记录&quot;旁边，选择&quot;管理&quot;。":::

1. 在"管理高级 DNS 记录"页上，选择" **+ 添加记录"**。

    :::image type="content" source="../../media/dns-webcom/webcom-domains-add-record.png" alt-text="选择&quot; + 添加记录&quot;。":::

1. 在 **"类型**"下，从下拉列表中选择 **SRV** 。

    :::image type="content" source="../../media/dns-webcom/webcom-domains-srv.png" alt-text="从类型下拉列表中选择 SRV。":::

1. 选择或复制并粘贴下表中的值。

    |类型|服务|协议|粗细|端口|Target|优先级|TTL|
    |---|---|---|---|---|---|---|---|
    |SRV|_sip|TLS|100|443|sipdir.online.lync.com <br/> **此值不能以 (.)**|1|1 Hour|
    |SRV|_sipfederationtls|TCP|100|5061|sipfed.online.lync.com <br/> **此值不能以 (.)**|1|1 Hour|

    :::image type="content" source="../../media/dns-webcom/webcom-domains-srv-add.png" alt-text="键入或复制表中的值并将其粘贴到 SRV 记录窗口中。":::

1. 选择 **"添加"**。

1. 通过复制表中第二行的值添加其他 SRV 记录。

> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果在添加 DNS 记录后遇到邮件流问题或其他问题，请参阅[查找在添加域或 DNS 记录后遇到的问题并进行修复](../get-help-with-domains/find-and-fix-issues.md)。

### <a name="add-the-two-required-cname-records"></a>添加两个必需的 CNAME 记录

1. To get started， go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp). 首先登录。

1. 在登录页面上，选择 **"域名"**。

1. 在 **"操作**"下，选择三个点，然后在下拉列表中选择"管理"。

    :::image type="content" source="../../media/dns-webcom/webcom-domains-1.png" alt-text="从下拉列表中选择&quot;管理&quot;。":::

1. 向下滚动以选择" **高级工具"，** 在"高级 DNS 记录" **旁边**，选择" **管理"**。

    :::image type="content" source="../../media/dns-webcom/webcom-domains-2.png" alt-text="在&quot;高级 DNS 记录&quot;旁边，选择&quot;管理&quot;。":::

    您可能必须选择" **继续"** 才能访问"管理高级 DNS 记录"页。

1. 在"管理高级 DNS 记录"页上，选择" **+ 添加记录"**。

    :::image type="content" source="../../media/dns-webcom/webcom-domains-add-record.png" alt-text="选择&quot; + 添加记录&quot;。":::

1. 在 **"类型**"下，从下拉列表中选择 **"CNAME** "。

    :::image type="content" source="../../media/dns-webcom/webcom-domains-cname.png" alt-text="从&quot;类型&quot;下拉列表中选择&quot;CNAME&quot;。":::

1. 选择或复制并粘贴下表中的值。

    |类型|引用|主机名|别名|TTL|
    |---|---|---|---|---|
    |CNAME|其他主机|sip|sipdir.online.lync.com <br/> **此值不能以 (.)**|1 小时|
    |CNAME|其他主机|lyncdiscover|webdir.online.lync.com <br/> **此值不能以 (.)**|1 Hour|

    :::image type="content" source="../../media/dns-webcom/webcom-domains-cname-values.png" alt-text="键入或复制 CNAME 值并将其粘贴到窗口中。":::

1. 选择 **"添加"**。

1. 通过复制表中第二行的值添加其他 CNAME 记录。

> [!NOTE]
> DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。

## <a name="advanced-option-intune-and-mobile-device-management-for-microsoft-365"></a>高级选项：Intune和移动设备管理Microsoft 365

此服务可帮助你保护并远程管理连接到域的移动设备。 移动设备管理需要 2 条 CNAME 记录，以便用户可以将设备注册到服务。

### <a name="add-the-two-required-cname-records-for-mobile-device-management"></a>为 Mobile 应用程序添加两个必需的 CNAME 记录设备管理

1. To get started， go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp). 首先登录。

1. 在登录页面上，选择 **"域名"**。

1. 在 **"操作**"下，选择三个点，然后在下拉列表中选择"管理"。

    :::image type="content" source="../../media/dns-webcom/webcom-domains-1.png" alt-text="从下拉列表中选择&quot;管理&quot;。":::

1. 向下滚动以选择" **高级工具"，** 在"高级 DNS 记录" **旁边**，选择" **管理"**。

    您可能必须选择" **继续"** 才能访问"管理高级 DNS 记录"页。

    :::image type="content" source="../../media/dns-webcom/webcom-domains-2.png" alt-text="在&quot;高级 DNS 记录&quot;旁边，选择&quot;管理&quot;。":::

1. 在"管理高级 DNS 记录"页上，选择" **+ 添加记录"**。

    :::image type="content" source="../../media/dns-webcom/webcom-domains-add-record.png" alt-text="选择&quot; + 添加记录&quot;。":::

1. 在 **"类型**"下，从下拉列表中选择 **"CNAME** "。

    :::image type="content" source="../../media/dns-webcom/webcom-domains-cname.png" alt-text="从&quot;类型&quot;下拉列表中选择&quot;CNAME&quot;。":::

1. 选择或复制并粘贴下表中的值。

    |类型|引用|主机名|别名|TTL|
    |---|---|---|---|---|
    |CNAME|其他主机|enterpriseregistration|enterpriseregistration.windows.net <br/> **此值不能以 (.)**|1 小时|
    |CNAME|其他主机|enterpriseenrollment|enterpriseenrollment-s.manage.microsoft.com <br/> **此值不能以 (.)**|1 Hour|

    :::image type="content" source="../../media/dns-webcom/webcom-domains-cname-values.png" alt-text="键入或复制并粘贴表中的 CNAME 值到窗口中。":::

1. 选择 **"添加"**。

1. 通过复制表中第二行的值添加其他 CNAME 记录。

> [!NOTE]
> DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。
