---
title: 更改名称服务器以设置Microsoft 365注册机构的域名
f1.keywords:
- CSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
ms.custom:
- okr_smb
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
- GEU150
- GEA150
ms.assetid: a8b487a9-2a45-4581-9dc4-5d28a47010a2
description: 了解如何在 Microsoft 365 中添加和设置域，以便电子邮件和 Skype for Business Online 等服务使用你自己的域名。
ms.openlocfilehash: 2d591429d74e03eec883b524b8fa36d082cfab93
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/08/2022
ms.locfileid: "63316963"
---
# <a name="change-nameservers-to-set-up-microsoft-365-with-any-domain-registrar"></a>更改名称服务器以设置Microsoft 365注册机构的域名

 如果找不到要查找的内容，请 **[查看域常见问题解答](../setup/domains-faq.yml)**。

请按照以下说明在 Microsoft 365中添加和设置你的域，以便电子邮件和 Teams 等服务将使用你自己的域名。 为此，您需要验证您的域，然后将您的域的名称服务器更改为 Microsoft 365以便您可以设置正确的 DNS 记录。 如果以下语句描述了您的情况，请按照以下步骤操作：

- 你有你自己的域，并且想要设置它以使用Microsoft 365。

- 您希望Microsoft 365管理 DNS 记录。  (如果愿意，可以 [管理自己的 DNS](../setup/add-domain.md) 记录。) 

## <a name="add-a-txt-or-mx-record-for-verification"></a>添加 TXT 记录或 MX 记录进行验证

> [!NOTE]
> 您必须仅创建这些记录中的其中一项。TXT 是首选记录类型，但某些 DNS 托管提供商不支持它，在这种情况下，您可以创建 MX 记录。

在将域用于 Microsoft 365 之前，必须确保你拥有该域。如果你能够在域注册机构处登录到你的帐户并创建 DNS 记录，便可向 Microsoft 365 证明你是域所有者。

> [!NOTE]
> 此记录仅用于验证您是否拥有自己的域；它不会影响其他任何内容。 如果需要，您可以以后将其删除。

### <a name="find-the-area-on-your-dns-hosting-providers-website-where-you-can-create-a-new-record"></a>在 DNS 托管提供商网站上查找可在其中创建新记录的区域

1. 登录到您的 DNS 托管提供商的网站。

2. 选择您的域。

3. 查找您可以在其中编辑您的域的 DNS 记录的页面。

### <a name="create-the-record"></a>创建记录

根据是要创建 TXT 记录还是 MX 记录，请执行下列操作之一：

**如果要创建 TXT 记录，请使用这些值：**

<br>

****

|记录类型|别名或主机名|值|TTL|
|---|---|---|---|
|TXT|执行下列操作之一：键入 **@** ，将该字段留空或键入你的域名。  <p> **注意**：不同的 DNS 主机对此字段有不同的要求。|MS=ms *XXXXXXXX* <p> **注意：** 这是一个示例。 在这里使用来自 Microsoft 365 中的表的具体“**目标地址或指向的地址**”值。 [如何查找此项？](../get-help-with-domains/information-for-dns-records.md)|将此值设置为 **1 小时** 或等效的分钟数 ( **60** )、秒数 ( **3600** )，等等。|
|||||

**如果您创建 MX 记录，请使用这些值：**

<br>

****

|记录类型|别名或主机名|值|优先级|TTL|
|---|---|---|---|---|
|MX|键入" **@** "或你的域名。 |MS=ms *XXXXXXXX* **注意：** 这是一个示例。 在这里使用来自 Microsoft 365 中的表的具体“**目标地址或指向的地址**”值。 [如何查找此项？](../get-help-with-domains/information-for-dns-records.md)|对于“**优先级**”，为避免与用于邮件流的 MX 记录发生冲突，请使用比任何现有 MX 记录的优先级要低的优先级。 有关优先级的详细信息，请参阅[什么是 MX 优先级？](../setup/domains-faq.yml)|将此值设置为 **1 小时** 或等效的分钟数 ( **60** )、秒数 ( **3600** )，等等。|
||||||

### <a name="save-the-record"></a>保存记录

在域注册机构网站添加了记录后，你将返回到 Microsoft 365 并请求 Microsoft 365 查找记录。

Microsoft 365 找到正确的 TXT 记录表明域已通过验证。

1. 在管理中心，转到“**设置**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">域</a>”页面。

2. 在“**域**”页面上，选择要验证的域。

3. 在“**设置**”页面上，选择“**开始设置**”。

4. 在“**验证域**”页面上，选择“**验证**”。

> [!NOTE]
> DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。

## <a name="change-your-domains-nameserver-ns-records"></a>更改域的名称服务器 (NS) 记录

当您在 Microsoft 365 中到达域设置向导的最后一步时，您还有一项任务。 若要使用 Microsoft 365 服务（如电子邮件）设置域，您可以在域注册机构中更改域的名称服务器 (或 NS) 记录，以指向 Microsoft 365 主名称服务器和辅助名称服务器。 然后，由于Microsoft 365 DNS，系统会自动为服务设置所需的 DNS 记录。 通过按照您的域注册机构在其网站的帮助内容中所提供步骤进行操作，您可以自己更新名称服务器记录。 如果不熟悉 DNS，请联系域注册机构的支持人员。

::: moniker range="o365-worldwide"

若要在域注册机构的网站上更改您的域的名称服务器，请执行以下步骤：

1. 在域注册机构网站上查找区域，您可以在其中更改域的名称服务器或使用自定义名称服务器的区域。

2. 创建名称机记录，或编辑现有名称机记录以匹配以下值：

    - 第一个名称 ns1.bdm.microsoftonline.com
    - 第二个名称器：ns2.bdm.microsoftonline.com
    - 第三个名称 ns3.bdm.microsoftonline.com
    - 第四个名称 ns4.bdm.microsoftonline.com

   > [!TIP]
   > 最好添加所有四条记录，但如果注册机构仅支持两条，请添加 **ns1.bdm.microsoftonline.com 和** **ns2.bdm.microsoftonline.com**。

3. 保存所做的更改。

> [!CAUTION]
> 当您将域的 NS 记录更改为指向Microsoft 365服务器时，当前与域关联的所有服务都受到影响。 如果您跳过了向导中的任何步骤，或是将域用于博客、购物车或其他服务，则需要执行一些附加步骤。 否则此更改可能会导致服务停机时间，例如导致电子邮件访问丢失或您的当前网站不可访问。

::: moniker-end

::: moniker range="o365-21vianet"

1. 在域注册机构的网站上查找您可以在其中编辑您的域的名称服务器的区域。

2. 创建两个名称服务器记录，或编辑现有名称服务器记录匹配以下值：

   - 第一个名称 ns1.dns.partner.microsoftonline.cn
   - 第二个名称 ns2.dns.partner.microsoftonline.cn

   > [!TIP]
   > 应至少使用两个名称机记录。 如果列出了任何其他名称服务器，您可以删除它们，或将其更改为 **ns3.dns.partner.microsoftonline.cn ns4.dns.partner.microsoftonline.cn。** 

3. 保存所做的更改。

> [!CAUTION]
> 将域的 NS 记录更改为指向由世纪Office 365服务器运营的域时，当前与域关联的所有服务都受到影响。 如果您跳过了向导中的任何步骤，或是将域用于博客、购物车或其他服务，则需要执行一些附加步骤。 否则此更改可能会导致服务停机时间，例如导致电子邮件访问丢失或您的当前网站不可访问。

::: moniker-end

例如，以下是电子邮件和网站托管可能需要的一些附加步骤：

- 在更改 NS 记录之前，Microsoft 365域的所有电子邮件地址进行移动。

- 想要添加当前与网站地址一同使用的域，如 `https://www.fourthcoffee.com`？ 在添加域以保持其网站现在托管位置的托管位置时，您可以采取以下步骤，以便当您将域的 NS 记录更改为指向 Microsoft 365 后，用户仍可访问网站。

1. 在管理中心，转到“**设置**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">域</a>”页面。

2. 在" **域**"页面上选择域。

3. 在"域详细信息"页上，选择 **"DNS 记录"** 选项卡。

4. 选择 **"添加记录"**。

5. 在"**添加自定义 DNS** 记录"窗格中，从"类型"下拉列表中选择" (**地址) "**。

6. 在" **主机名"或"别名"** 框中，键入 **@**。

7. 在 **"IP 地址** "框中，键入其当前托管的网站的静态 IP 地址。 例如，172.16.140.1。

   > [!IMPORTANT]
   > 这必须是网站的 _静态_ IP 地址，而不是 _动态_ IP 地址。 若要确保您可以获取公共网站的静态 IP 地址，请与承载您的网站的网站核实。

8. 如果要更改记录的 TTL 设置，请从 **TTL** 下拉列表中选择一个新的时间长度。 否则，继续执行步骤 9。

9. 选择" **保存** "。

此外，您可以创建 CNAME 记录以帮助客户找到您的网站。

1. 选择 **"添加记录"**。
2. 在"**添加自定义 DNS 记录"** 窗格中，从"类型"下拉列表中选择"**CNAME (别名) "**。
3. 在" **主机名"或"别名"** 框中，键入 **www**。
4. 在" **指向地址"** 框中，键入网站的 (FQDN) 完全限定的域名。 例如， **contoso.5om**。
5. 如果要更改记录的 TTL 设置，请从 **TTL** 下拉列表中选择一个新的时间长度。 否则，继续执行步骤 6。
6. 选择“**保存**”。

将名称服务器记录更新为指向 Microsoft 后，域设置即完成。 电子邮件被路由到 Microsoft，并且发送到你的网站地址的流量将继续转到你的当前网站主机。'

> [!NOTE]
> Your nameserver record updates may take up to several hours to update across the Internet's DNS system. 然后，你的 Microsoft 电子邮件和其他服务都将设置为使用你的域。

## <a name="related-content"></a>相关内容

[添加 DNS 记录以连接域](create-dns-records-at-any-dns-hosting-provider.md) (文章) \
[查找并修复添加域或 DNS 记录之后出现的问题](find-and-fix-issues.md)（文章）\
[管理域](/admin)（链接页）
