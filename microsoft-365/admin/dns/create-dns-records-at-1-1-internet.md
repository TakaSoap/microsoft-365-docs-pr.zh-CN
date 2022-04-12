---
title: 将 IONOS 中的 DNS 记录连接 1&1 到 Microsoft 365
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
ms.assetid: 5762c3ca-1de2-4999-bfe5-4c5e25a8957e
description: 了解如何验证域，并在 Microsoft 的 1&1 IONOS 中设置电子邮件、Skype for Business Online 和其他服务的 DNS 记录。
ms.openlocfilehash: 8afdfed0998a262b1df4c95a63e9086e4f71e5b6
ms.sourcegitcommit: ac0ae5c2888e2b323e36bad041a4abef196c9c96
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/12/2022
ms.locfileid: "64780668"
---
# <a name="connect-your-dns-records-at-ionos-by-11-to-microsoft-365"></a>将 IONOS 中的 DNS 记录连接 1&1 到 Microsoft 365

 如果找不到要查找的内容，请 **[查看域常见问题解答](../setup/domains-faq.yml)**。

如果 IONOS by 1&1 是 DNS 托管提供商，请按照本文中的步骤验证域，并为电子邮件、Skype for Business Online 等设置 DNS 记录。

## <a name="before-you-begin"></a>准备工作

有两个选项可用于设置域的 DNS 记录：

- [**使用域连接**](#use-domain-connect-to-verify-and-set-up-your-domain)如果尚未使用其他电子邮件服务提供商设置域，请使用域连接步骤自动验证和设置要与Microsoft 365配合使用的新域。

    或

- [**使用手动步骤**](#create-dns-records-with-manual-setup) 使用以下手动步骤验证域，并选择何时以及向域注册机构添加哪些记录。 这样就可以在方便的时候设置新的 MX (邮件) 记录。

## <a name="use-domain-connect-to-verify-and-set-up-your-domain"></a>使用域连接验证和设置域

请按照以下步骤使用Microsoft 365自动验证和设置 IONOS 1&1 域：

1. 在Microsoft 365 管理中心中，选择 **设置** > <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">**域**</a>，然后选择要设置的域。

    :::image type="content" source="../../media/dns-IONOS/IONOS-DomainConnects-1.png" alt-text="在Microsoft 365中选择域。":::

1. 选择三个点 (更多操作) >选择 **“开始”设置**。

    :::image type="content" source="../../media/dns-IONOS/IONOS-DomainConnects-2.png" alt-text="选择“开始”设置。":::

1. 在“如何连接域”上？页面，选择 **“继续**”。

1. 在“添加 DNS 记录”页上，选择 **“添加 DNS 记录**”。

1. 在 IONOS by 1&1 登录页上，登录到帐户，然后选择 **“连接**”和“**允许**”。

    :::image type="content" source="../../media/dns-IONOS/IONOS-DomainConnects-3.png" alt-text="选择连接，然后允许。":::

    这会完成Microsoft 365的域设置。

## <a name="create-dns-records-with-manual-setup"></a>使用手动设置创建 DNS 记录

在 IONOS 中按 1&1 添加这些记录后，域将设置为使用Microsoft 服务。

> [!CAUTION]
> 请注意，IONOS by 1&1 不允许域同时具有 MX 记录和顶级自动发现 CNAME 记录。 这将限制为 Microsoft 配置 Exchange Online 的方式。 有一种解决方法，但我们建议 **仅** 在已有在 IONOS 上创建子域的经验时才使用它，&1。
> 如果尽管存在此[服务限制](../setup/domains-faq.yml)，你还是选择在 IONOS 上按 1&1 管理自己的 Microsoft DNS 记录，请按照本文中的步骤验证域，并为电子邮件、Skype for Business Online 等设置 DNS 记录。

> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果在添加 DNS 记录后遇到邮件流问题或其他问题，请参阅[查找在添加域或 DNS 记录后遇到的问题并进行修复](../get-help-with-domains/find-and-fix-issues.md)。

### <a name="add-a-txt-record-for-verification"></a>添加 TXT 记录进行验证

在将域用于 Microsoft 之前，必须确保你拥有该域。如果你能够在域注册机构处登录到你的帐户并创建 DNS 记录，便可向 Microsoft 证明你是域所有者。

> [!NOTE]
> 此记录仅用于验证您是否拥有自己的域；它不会影响其他任何内容。 如果需要，您可以以后将其删除。

1. 若要开始，请使用 [此链接](https://my.1and1.com/)转到 IONOS 1&1 的域页。 You'll be prompted to log in.

1. 选择 **菜单**，然后选择 **“域”和“SSL**”。

   :::image type="content" source="../../media/dns-IONOS/IONOS-domains-1.png" alt-text="选择域和 SSL。":::

1. 在要更新的域的 **“操作** ”下，选择齿轮控件，然后选择 **DNS**。

   :::image type="content" source="../../media/dns-IONOS/IONOS-domains-2.png" alt-text="从下拉列表中选择 DNS。":::

1. 选择 **“添加记录**”。

    :::image type="content" source="../../media/dns-IONOS/IONOS-domains-3.png" alt-text="选择“添加记录”。":::

1. 选择 **“TXT”** 部分。

    :::image type="content" source="../../media/dns-IONOS/IONOS-domains-4.png" alt-text="选择“TXT”部分。":::

1. 在“添加 DNS 记录”页上，在新记录的框中键入或复制并粘贴下表中的值。

    |主机名|值|TTL|
    |---|---|---|
    | (将此字段留空) |MS=ms *XXXXXXXX*  <br/> 注意：这是一个示例。 在这里使用表中的特定“**目标地址或指向的地址**”值。 [如何查找此项？](../get-help-with-domains/information-for-dns-records.md)|1 小时|

1. 选择“**保存**”。

    :::image type="content" source="../../media/dns-IONOS/IONOS-domains-5.png" alt-text="选择“保存”。":::

    请在继续之前等待数分钟，以便您刚刚创建的记录可以通过 Internet 完成更新。

在域注册机构网站添加了记录后，你将返回到 Microsoft 365 并请求 Microsoft 365 查找记录。 当 Microsof 找到正确的 TXT 记录时，表明域已通过验证。

若要验证Microsoft 365中的记录，

1. 在管理中心，转到 **设置** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">**域**</a>。

1. 在“域”页上，选择要验证的域，然后选择 **“开始设置**”。

    :::image type="content" source="../../media/dns-IONOS/IONOS-DomainConnects-2.png" alt-text="选择“开始”设置。":::

1. 选择 **继续**。

1. 在“**验证域**”页面上，选择“**验证**”。

> [!NOTE]
> DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。

### <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>添加一条 MX 记录，确保发往你的域的电子邮件将会发送到 Microsoft

> [!NOTE]
> 如果已注册 1und1.de，请 [在此处登录](https://go.microsoft.com/fwlink/?linkid=859152)。

1. 若要开始，请使用 [此链接](https://my.1and1.com/)转到 IONOS 1&1 的域页。 You'll be prompted to log in.

1. 选择 **菜单**，然后选择 **“域”和“SSL**”。

   :::image type="content" source="../../media/dns-IONOS/IONOS-domains-1.png" alt-text="选择域和 SSL。":::

1. 在要更新的域的 **“操作** ”下，选择齿轮控件，然后选择 **DNS**。

   :::image type="content" source="../../media/dns-IONOS/IONOS-domains-2.png" alt-text="从下拉列表中选择 DNS。":::

1. 选择 **“添加记录**”。

    :::image type="content" source="../../media/dns-IONOS/IONOS-domains-3.png" alt-text="选择“添加记录”。":::

1. 选择 **“MX”** 部分。

    :::image type="content" source="../../media/dns-IONOS/IONOS-domains-MX.png" alt-text="选择“MX”部分。":::

1. 在“添加 DNS 记录”页上，在新记录的框中键入或复制并粘贴下表中的值。

    |主机名|Points to |优先级|TTL|
    |---|---|---|---|
    |@|*\<domain-key\>*.mail.protection.outlook.com  <br/>  注意：从 Microsoft 帐户获取你的 \<domain-key\> 帐户。 如何查找此内容？[](../get-help-with-domains/information-for-dns-records.md)|10   <br/> 有关优先级的详细信息，请参阅[什么是 MX 优先级？](../setup/domains-faq.yml)|1 小时|

1. 选择“**保存**”。

    :::image type="content" source="../../media/dns-IONOS/IONOS-domains-MX-Save.png" alt-text="选择“保存”。":::

1. 如果已列出任何 MX 记录，请在 **“添加记录**”页上选择 **“删除记录**”垃圾桶，将其删除。

    :::image type="content" source="../../media/dns-IONOS/IONOS-domains-Delete.png" alt-text="选择“删除记录”。":::

### <a name="add-the-cname-record-required-for-microsoft"></a>添加 Microsoft 所需的 CNAME 记录

> [!NOTE]
> 如果已注册 1und1.de，请 [在此处登录](https://go.microsoft.com/fwlink/?linkid=859152)。

1. 若要开始，请使用 [此链接](https://my.1and1.com/)转到 IONOS 1&1 的域页。 You'll be prompted to log in.

1. 选择 **菜单**，然后选择 **“域”和“SSL**”。

   :::image type="content" source="../../media/dns-IONOS/IONOS-domains-1.png" alt-text="选择域和 SSL。":::

1. 在要更新的域的 **“操作** ”下，选择齿轮控件，然后选择 **DNS**。

   :::image type="content" source="../../media/dns-IONOS/IONOS-domains-2.png" alt-text="从下拉列表中选择 DNS。":::

   现在，你将创建两个子域并为每个子域设置别 **名** 值。

    (这是必需的，因为 1&IONOS 仅支持一个顶级 CNAME 记录，但 Microsoft 需要多个 CNAME 记录。) 

   首先，将创建自动发现子域。

1. 选择 **子域**。

   :::image type="content" source="../../media/dns-IONOS/IONOS-domains-Subdomains.png" alt-text="选择子域。":::

1. 选择 **“添加子域**”。

   :::image type="content" source="../../media/dns-IONOS/IONOS-domains-add-subdomains.png" alt-text="选择“添加子域”。":::

1. 在新 **子域的“添加子域** ”框中，键入或复制并粘贴下表中的 **“添加子域** ”值。  (你将在后面的步骤中添加 **别名** 值。) 

    |添加子域|别名|
    |---|---|
    |自动发现|autodiscover.outlook.com|

1. 在刚创建的 **自动发现** 子域的 **“操作**”下，选择齿轮控件，然后从下拉列表中选择 **DNS**。

1. 选择 **“添加记录**”，然后选择 **“CNAME”** 部分。

1. 在“**别名:**”框中，只键入或复制并粘贴下表中的“**别名**”值。

    |添加子域|别名|
    |---|---|
    |自动发现|autodiscover.outlook.com|

1. 选择“**保存**”。

## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>为 SPF 添加 TXT 记录以帮助防止垃圾邮件

> [!IMPORTANT]
> 一个域所拥有的 SPF 的 TXT 记录不能超过一个。 如果域具有多个 SPF 记录，你将收到电子邮件错误，其中随附发送和垃圾邮件分类问题。 如果你的域已有 SPF 记录，请不要为 Microsoft 创建新记录。 而是将所需的 Microsoft 值添加到当前记录，以便具有包含这两组值的  *单*  个 SPF 记录。 需要示例吗？ 请查看 [Microsoft 的外部域名系统记录](../../enterprise/external-domain-name-system-records.md)。 若要验证 SPF 记录，可以使用以下 [SPF 验证工具](../setup/domains-faq.yml)之一。

> [!NOTE]
> 如果已注册 1und1.de，请 [在此处登录](https://go.microsoft.com/fwlink/?linkid=859152)。

1. 若要开始，请使用 [此链接](https://my.1and1.com/)转到 IONOS 1&1 的域页。 You'll be prompted to log in.

1. 选择 **菜单**，然后选择 **“域”和“SSL**”。

   :::image type="content" source="../../media/dns-IONOS/IONOS-domains-1.png" alt-text="选择域和 SSL。":::

1. 在要更新的域的 **“操作** ”下，选择齿轮控件，然后选择 **DNS**。

   :::image type="content" source="../../media/dns-IONOS/IONOS-domains-2.png" alt-text="从下拉列表中选择 DNS。":::

1. 选择 **“添加记录**”。

    :::image type="content" source="../../media/dns-IONOS/IONOS-domains-3.png" alt-text="选择“添加记录”。":::

1. 选择 **“SPF (TXT)** ”部分。

    :::image type="content" source="../../media/dns-IONOS/IONOS-domains-SPFTXT.png" alt-text="选择“SPF (TXT) ”部分。":::

1. 在新记录的框中，键入或复制并粘贴下表中的值。

    |类型|主机名|值|TTL|
    |---|---|---|---|
    |SPF (TXT)|（将此字段留空。）|v=spf1 include:spf.protection.outlook.com -all  <br/> **注意：** 我们建议您复制并粘贴此条目，以保证正确保留所有空格。|1 小时|

1. 选择“**保存**”。

   :::image type="content" source="../../media/dns-IONOS/IONOS-domains-SPFTXT-Save.png" alt-text="选择“保存”。":::

## <a name="advanced-option-skype-for-business"></a>高级选项：Skype for Business

仅当组织对联机通信服务（例如聊天、电话会议和视频呼叫）使用Skype for Business时，除了Microsoft Teams，才选择此选项。 Skype需要 4 条记录：2 条用于用户到用户通信的 SRV 记录，以及 2 条用于登录和将用户连接到服务的 CNAME 记录。

### <a name="add-two-additional-cname-records"></a>添加两个额外的 CNAME 记录

1. 若要开始，请使用 [此链接](https://my.1and1.com/)转到 IONOS 1&1 的域页。 You'll be prompted to log in.

1. 选择 **菜单**，然后选择 **“域”和“SSL**”。

   :::image type="content" source="../../media/dns-IONOS/IONOS-domains-1.png" alt-text="选择域和 SSL。":::

1. 在要更新的域的 **“操作** ”下，选择齿轮控件，然后选择 **DNS**。

   :::image type="content" source="../../media/dns-IONOS/IONOS-domains-2.png" alt-text="从下拉列表中选择 DNS。":::

   现在，你将创建两个子域并为每个子域设置别 **名** 值。

    (这是必需的，因为 1&IONOS 仅支持一个顶级 CNAME 记录，但 Microsoft 需要多个 CNAME 记录。) 

   首先，创建 lyncdiscover 子域。

1. 选择 **子域**。

   :::image type="content" source="../../media/dns-IONOS/IONOS-domains-Subdomains.png" alt-text="选择子域。":::

1. 选择 **“添加子域**”。

   :::image type="content" source="../../media/dns-IONOS/IONOS-domains-add-subdomains.png" alt-text="选择“添加子域”。":::

1. 在新 **子域的“添加子域** ”框中，键入或复制并粘贴下表中的 **“添加子域** ”值。  (你将在后面的步骤中添加 **别名** 值。) 

    |添加子域|别名|
    |---|---|
    |lyncdiscover   |webdir.online.lync.com  |

1. 在刚创建的 **lyncdiscover** 子域的 **“操作**”下，选择齿轮控件，然后从下拉列表中选择 **DNS**。

1. 选择 **“添加记录**”，然后选择 **“CNAME”** 部分。

1. 在“**别名:**”框中，只键入或复制并粘贴下表中的“**别名**”值。

    |创建子域|别名|
    |---|---|
    |lyncdiscover|webdir.online.lync.com|

1.  (SIP) 创建另一个 **子域：选择“添加子域**”。

1. 在新 **子域的“添加子域** ”框中，键入或复制并粘贴下表中的 **“添加子域** ”值。  (你将在后面的步骤中添加 **别名** 值。) 

    |添加子域|别名|
    |---|---|
    |sip|sipdir.online.lync.com|

1. 在刚刚创建的子域的 **“操作** ”下，选择齿轮控件，然后从下拉列表中选择 **DNS** 。

1. 选择 **“添加记录**”。

    :::image type="content" source="../../media/dns-IONOS/IONOS-domains-3.png" alt-text="选择“添加记录”。":::

1. 选择 **“CNAME”** 部分。

1. 在 **别名中：** 框中，键入或复制并粘贴下表中的 **别名** 值。

    |创建子域|别名|
    |---|---|
    |sip|sipdir.online.lync.com|

1. 选中“**我知道**”声明的复选框，然后选择“**保存**”。

## <a name="add-the-two-srv-records-required-for-microsoft"></a>添加 Microsoft 所需的两条 SRV 记录

> [!NOTE]
> 如果已注册 1und1.de，请 [在此处登录](https://go.microsoft.com/fwlink/?linkid=859152)。

1. 若要开始，请使用 [此链接](https://my.1and1.com/)转到 IONOS 1&1 的域页。 You'll be prompted to log in.

1. 选择 **菜单**，然后选择 **“域”和“SSL**”。

   :::image type="content" source="../../media/dns-IONOS/IONOS-domains-1.png" alt-text="选择域和 SSL。":::

1. 在要更新的域的 **“操作** ”下，选择齿轮控件，然后选择 **DNS**。

   :::image type="content" source="../../media/dns-IONOS/IONOS-domains-2.png" alt-text="从下拉列表中选择 DNS。":::

1. 选择 **“添加记录**”。

    :::image type="content" source="../../media/dns-IONOS/IONOS-domains-3.png" alt-text="选择“添加记录”。":::

1. 选择 **“SRV”** 部分。

    :::image type="content" source="../../media/dns-IONOS/IONOS-domains-SRV.png" alt-text="选择“SRV”部分。":::

1. 在新记录的框中，键入或复制并粘贴下表中的值。

    |类型|服务|协议|主机名|Points to |优先级|粗细|端口|TTL|
    |---|---|---|---|---|---|---|---|---|
    |SRV|_sip|tls|(Leave this field empty.)|sipdir.online.lync.com|100|1|443|1 小时|
    |SRV|_sipfederationtls|tcp|(Leave this field empty.)|sipfed.online.lync.com|100|1|5061|1 小时|

1. 选择“**保存**”。

    :::image type="content" source="../../media/dns-IONOS/IONOS-domains-SRV-Save.png" alt-text="选择“保存”。":::

1. 添加另一条 SRV 记录。

> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果在添加 DNS 记录后遇到邮件流问题或其他问题，请参阅[查找在添加域或 DNS 记录后遇到的问题并进行修复](../get-help-with-domains/find-and-fix-issues.md)。

## <a name="advanced-option-intune-and-mobile-device-management-for-microsoft-365"></a>高级选项：适用于Microsoft 365的Intune和移动设备管理

此服务可帮助保护和远程管理连接到域的移动设备。 移动设备管理需要 2 条 CNAME 记录，以便用户可以将设备注册到服务。

### <a name="add-the-two-required-cname-records"></a>添加两个必需的 CNAME 记录

> [!IMPORTANT]
> 遵循用于其他 CNAME 记录的子域过程，并提供下表中的值。

1. 若要开始，请使用 [此链接](https://my.1and1.com/)转到 IONOS 1&1 的域页。 You'll be prompted to log in.

1. 选择 **菜单**，然后选择 **“域”和“SSL**”。

   :::image type="content" source="../../media/dns-IONOS/IONOS-domains-1.png" alt-text="选择域和 SSL。":::

1. 在要更新的域的 **“操作** ”下，选择齿轮控件，然后选择 **DNS**。

   :::image type="content" source="../../media/dns-IONOS/IONOS-domains-2.png" alt-text="从下拉列表中选择 DNS。":::

   现在，你将创建两个子域并为每个子域设置别 **名** 值。

    (这是必需的，因为 1&IONOS 仅支持一个顶级 CNAME 记录，但 Microsoft 需要多个 CNAME 记录。) 

   首先，创建 lyncdiscover 子域。

1. 选择 **子域**。

   :::image type="content" source="../../media/dns-IONOS/IONOS-domains-Subdomains.png" alt-text="选择子域。":::

1. 选择 **“添加子域**”。

   :::image type="content" source="../../media/dns-IONOS/IONOS-domains-add-subdomains.png" alt-text="选择“添加子域”。":::

1. 在新 **子域的“添加子域** ”框中，键入或复制并粘贴下表中的 **“添加子域** ”值。  (你将在后面的步骤中添加 **别名** 值。) 

    |添加子域|别名|
    |---|---|
    |enterpriseregistration|enterpriseregistration.windows.net|

1. 在刚刚创建 **的企业注册** 子域的 **“操作**”下，选择齿轮控件，然后从下拉列表中选择 **DNS**。

1. 选择 **“添加记录**”，然后选择 **“CNAME”** 部分。

1. 在“**别名:**”框中，只键入或复制并粘贴下表中的“**别名**”值。

    |添加子域|别名|
    |---|---|
    |enterpriseregistration|enterpriseregistration.windows.net|

1. 创建另一个子域：选择 **“添加子域**”。

1. 在新 **子域的“添加子域** ”框中，键入或复制并粘贴下表中的 **“添加子域** ”值。  (你将在后面的步骤中添加 **别名** 值。) 

    |添加子域|别名|
    |---|---|
    |enterpriseenrollment|enterpriseenrollment-s.manage.microsoft.com|

1. 在刚创建 **的企业注册** 子域的 **“操作**”下，选择齿轮控件，然后从下拉列表中选择 **DNS**。

1. 选择 **“添加记录**”。

    :::image type="content" source="../../media/dns-IONOS/IONOS-domains-3.png" alt-text="选择“添加记录”。":::

1. 选择 **“CNAME”** 部分。

1. 在 **别名中：** 框中，键入或复制并粘贴下表中的 **别名** 值。

    |创建子域|别名|
    |---|---|
    |enterpriseenrollment|enterpriseenrollment-s.manage.microsoft.com|

1. 选中“**我知道**”声明的复选框，然后选择“**保存**”。
