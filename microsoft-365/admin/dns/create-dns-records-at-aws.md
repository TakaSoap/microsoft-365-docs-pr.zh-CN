---
title: 在 Amazon Web Services (AWS) 连接 DNS 记录以Microsoft 365
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
ms.assetid: 7a2efd75-0771-4897-ba7b-082fe5bfa9da
description: 了解如何在 Amazon Web Services (适用于 Microsoft 的 AWS) 中验证域并设置电子邮件、Skype for Business Online 和其他服务的 DNS 记录。
ms.openlocfilehash: d194e425485a45d2c3dc949fc85e74bc957932fb
ms.sourcegitcommit: ac0ae5c2888e2b323e36bad041a4abef196c9c96
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/12/2022
ms.locfileid: "64780646"
---
# <a name="connect-your-dns-records-at-amazon-web-services-aws-to-microsoft-365"></a>在 Amazon Web Services (AWS) 连接 DNS 记录以Microsoft 365

 如果找不到要查找的内容，请 **[查看域常见问题解答](../setup/domains-faq.yml)**。

如果 AWS 是 DNS 托管提供商，请按照本文中的步骤验证域，并为电子邮件、Skype Online for Business 等设置 DNS 记录。

在 AWS 中添加这些记录后，域将设置为使用Microsoft 服务。

> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果在添加 DNS 记录后遇到邮件流问题或其他问题，请参阅[查找在添加域或 DNS 记录后遇到的问题并进行修复](../get-help-with-domains/find-and-fix-issues.md)。

## <a name="add-a-txt-record-for-verification"></a>添加 TXT 记录进行验证

在将域用于 Microsoft 之前，必须确保你拥有该域。如果你能够在域注册机构处登录到你的帐户并创建 DNS 记录，便可向 Microsoft 证明你是域所有者。

> [!NOTE]
> 此记录仅用于验证您是否拥有自己的域；它不会影响其他任何内容。 如果需要，您可以以后将其删除。

1. 要开始，请使用[此链接](https://console.aws.amazon.com/route53/home)转到你在 AWS 上的域页面。 系统将会提示您先登录。

1. 在登陆页 **上的“域**”下，选择 **“已注册的域**”。

1. 在 **“域名”** 下，选择要在Microsoft 365中设置的域。

    **注意**：如果尚未为域创建托管区域，请选择 **“创建托管区域** ”并完成步骤，然后再转到下一步。

   :::image type="content" source="../../media/dns-aws/aws-domains-1.png" alt-text="选择要验证的域的名称。":::

1. 选择 **“管理 DNS**”。

   :::image type="content" source="../../media/dns-aws/aws-domains-2.png" alt-text="从下拉列表中选择“管理 DNS”。":::

1. 在 **“域名**”下，选择要验证的域的托管区域版本的域名。

   :::image type="content" source="../../media/dns-aws/aws-domains-3.png" alt-text="选择要验证的域的名称。":::

1. 选择 **“创建记录**”。

   :::image type="content" source="../../media/dns-aws/aws-domains-create-record.png" alt-text="选择“创建记录”。":::

1. 在新记录的框中，键入或复制并粘贴下表中的值。

     (从下拉列表中选择 **类型** 和 **路由策略** 值。) 

    > [!TIP]
    > The quotation marks required by the onscreen instructions are supplied automatically. You don't need to type them manually.

    |记录名称|记录类型|值|TTL (Seconds)|路由策略|
    |:-----|:-----|:-----|:-----|:-----|
    |(Leave this field empty.)|TXT - 用于验证电子邮件发件人|MS=*msXXXXXXXX* <br/> **注意：** 这是一个示例。 在这里使用来自 Microsoft 365 中的表的具体“**目标地址或指向的地址**”值。 [如何查找此项？](../get-help-with-domains/information-for-dns-records.md)|300|简单|

1. 选择 **“创建记录**”。

   :::image type="content" source="../../media/dns-aws/aws-domains-txt-create-records.png" alt-text="选择“创建记录”。":::

   请在继续之前等待数分钟，以便您刚刚创建的记录可以通过 Internet 完成更新。

现在，你已在域注册机构的站点上添加了该记录，你将返回到 Microsoft 并请求搜索记录。 当 Microsof 找到正确的 TXT 记录时，表明域已通过验证。

若要验证Microsoft 365中的记录，

1. 在管理中心，转到 **设置** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">**域**</a>。

1. 在“域”页上，选择要验证的域，然后选择 **“开始设置**”。

    :::image type="content" source="../../media/dns-IONOS/IONOS-DomainConnects-2.png" alt-text="选择“开始”设置。":::

1. 选择 **继续**。

1. 在“**验证域**”页面上，选择“**验证**”。

> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果在添加 DNS 记录后遇到邮件流问题或其他问题，请参阅[查找在添加域或 DNS 记录后遇到的问题并进行修复](../get-help-with-domains/find-and-fix-issues.md)。

## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft-365"></a>添加 MX 记录，以便将域的电子邮件发送到Microsoft 365

1. 要开始，请使用[此链接](https://console.aws.amazon.com/route53/home)转到你在 AWS 上的域页面。 系统将会提示您先登录。

1. 在登陆页 **上的“域**”下，选择 **“已注册的域**”。

1. 在 **“域名”** 下，选择要在Microsoft 365中设置的域。

    **注意**：如果尚未为域创建托管区域，请选择 **“创建托管区域** ”并完成步骤，然后再转到下一步。

   :::image type="content" source="../../media/dns-aws/aws-domains-1.png" alt-text="选择域的名称。":::

1. 选择 **“管理 DNS**”。

   :::image type="content" source="../../media/dns-aws/aws-domains-2.png" alt-text="从下拉列表中选择“管理 DNS”。":::

1. 在 **“域名**”下，选择要验证的域的托管区域版本的域名。

   :::image type="content" source="../../media/dns-aws/aws-domains-3.png" alt-text="选择域的名称。":::

1. 选择 **“创建记录**”。

   :::image type="content" source="../../media/dns-aws/aws-domains-create-record.png" alt-text="选择“创建记录”。":::

1. 在新记录的框中，键入或复制并粘贴下表中的值。

     (从下拉列表中选择 **类型** 和 **路由策略** 值。) 

    > [!TIP]
    > The quotation marks required by the onscreen instructions are supplied automatically. You don't need to type them manually.

    |记录名称|记录类型|值|TTL (Seconds)|路由策略|
    |:-----|:-----|:-----|:-----|:-----|
    |(Leave this field empty.)|MX - 指定邮件服务器|0 *\<domain-key\>*.mail.protection.outlook.com。 <br/> 0 是 MX 优先级值。 将其添加到 MX 值的开头，使用一个空格将其与其余部分隔开。  <br/> **此值必须以句点 (.) 结尾。** <br/> **注意：** 从Microsoft 365帐户获取你\<*domain-key*\>。 [如何查找此项？](../get-help-with-domains/information-for-dns-records.md)|300|简单路由|

1. 选择 **“创建记录**”。

   :::image type="content" source="../../media/dns-aws/aws-domains-mx-create-records.png" alt-text="选择“创建记录”。":::

1. 如果有任何其他 MX 记录，请通过选择记录，然后选择 **“删除”** 来删除它们。

## <a name="add-the-cname-record-required-for-microsoft-365"></a>添加Microsoft 365所需的 CNAME 记录

1. 要开始，请使用[此链接](https://console.aws.amazon.com/route53/home)转到你在 AWS 上的域页面。 系统将会提示您先登录。

1. 在登陆页 **上的“域**”下，选择 **“已注册的域**”。

1. 在 **“域名”** 下，选择要在Microsoft 365中设置的域。

    **注意**：如果尚未为域创建托管区域，请选择 **“创建托管区域** ”并完成步骤，然后再转到下一步。

   :::image type="content" source="../../media/dns-aws/aws-domains-1.png" alt-text="选择域的名称。":::

1. 选择 **“管理 DNS**”。

   :::image type="content" source="../../media/dns-aws/aws-domains-2.png" alt-text="从下拉列表中选择“管理 DNS”。":::

1. 在 **“域名**”下，选择要验证的域的托管区域版本的域名。

   :::image type="content" source="../../media/dns-aws/aws-domains-3.png" alt-text="选择域的名称。":::

1. 选择 **“创建记录**”。

   :::image type="content" source="../../media/dns-aws/aws-domains-create-record.png" alt-text="选择“创建记录”。":::

1. 在新记录的框中，键入或复制并粘贴下表中的值。

     (从下拉列表中选择 **类型** 和 **路由策略** 值。) 

    |记录名称|记录类型|值|TTL|路由策略|
    |:-----|:-----|:-----|:-----|:-----|
    |自动发现|CNAME - 将流量路由到另一个域名|autodiscover.outlook.com. <br/> **此值必须以句点 (.) 结尾。**|300|简单|

1. 选择 **“创建记录**”。

   :::image type="content" source="../../media/dns-aws/aws-domains-cname-create-records.png" alt-text="选择“创建记录”。":::

## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>为 SPF 添加 TXT 记录以帮助防止垃圾邮件

> [!IMPORTANT]
> 一个域所拥有的 SPF 的 TXT 记录不能超过一个。 如果域具有多个 SPF 记录，你将收到电子邮件错误，其中随附发送和垃圾邮件分类问题。 如果你的域已有 SPF 记录，请不要为 Microsoft 创建新记录。 而是将所需的 Microsoft 值添加到当前记录，以便具有包含这两组值的 *单* 个 SPF 记录。 需要示例吗？ 请查看 [Microsoft 的外部域名系统记录](../../enterprise/external-domain-name-system-records.md)。 若要验证 SPF 记录，可以使用以下 [SPF 验证工具](../setup/domains-faq.yml)之一。

1. 要开始，请使用[此链接](https://console.aws.amazon.com/route53/home)转到你在 AWS 上的域页面。 系统将会提示您先登录。

1. 在登陆页 **上的“域**”下，选择 **“已注册的域**”。

1. 在 **“域名”** 下，选择要在Microsoft 365中设置的域。

    **注意**：如果尚未为域创建托管区域，请选择 **“创建托管区域** ”并完成步骤，然后再转到下一步。

   :::image type="content" source="../../media/dns-aws/aws-domains-1.png" alt-text="选择域的名称。":::

1. 选择 **“管理 DNS**”。

   :::image type="content" source="../../media/dns-aws/aws-domains-2.png" alt-text="从下拉列表中选择“管理 DNS”。":::

1. 在 **“域名**”下，选择要验证的域的托管区域版本的域名。

   :::image type="content" source="../../media/dns-aws/aws-domains-3.png" alt-text="选择域的名称。":::

1. 选择 **“创建记录**”。

   :::image type="content" source="../../media/dns-aws/aws-domains-create-record.png" alt-text="选择“创建记录”。":::

1. 在新记录的框中，键入或复制并粘贴下表中的值。

     (从下拉列表中选择 **Type** 值。) 

    |记录类型|值|
    |:-----|:-----|
    |TXT - 用于验证电子邮件发件人和特定于应用程序的值|v=spf1 include:outlook.com -all <br/> （系统会自动提供屏幕说明所需的引号。无需手动键入。）  <br/> **注意：** 建议复制粘贴此条目，以保证正确保留所有空格。|

1. 选择 **“创建记录**”。

   :::image type="content" source="../../media/dns-aws/aws-domains-txt-create-records.png" alt-text="选择“创建记录”。":::

## <a name="advanced-option-skype-for-business"></a>高级选项：Skype for Business

仅当组织对联机通信服务（例如聊天、电话会议和视频呼叫）使用Skype for Business时，除了Microsoft Teams，才选择此选项。 Skype需要 4 条记录：2 条用于用户到用户通信的 SRV 记录，以及 2 条用于登录和将用户连接到服务的 CNAME 记录。

### <a name="add-the-two-required-srv-records"></a>添加两个必需的 SRV 记录

1. 要开始，请使用[此链接](https://console.aws.amazon.com/route53/home)转到你在 AWS 上的域页面。 系统将会提示您先登录。

1. 在登陆页 **上的“域**”下，选择 **“已注册的域**”。

1. 在 **“域名”** 下，选择要在Microsoft 365中设置的域。

    **注意**：如果尚未为域创建托管区域，请选择 **“创建托管区域** ”并完成步骤，然后再转到下一步。

   :::image type="content" source="../../media/dns-aws/aws-domains-1.png" alt-text="选择域的名称。":::

1. 选择 **“管理 DNS**”。

   :::image type="content" source="../../media/dns-aws/aws-domains-2.png" alt-text="从下拉列表中选择“管理 DNS”。":::

1. 在 **“域名**”下，选择要验证的域的托管区域版本的域名。

   :::image type="content" source="../../media/dns-aws/aws-domains-3.png" alt-text="选择域的名称。":::

1. 选择 **“创建记录**”。

   :::image type="content" source="../../media/dns-aws/aws-domains-create-record.png" alt-text="选择“创建记录”。":::

1. 在新记录的框中，键入或复制并粘贴下表中的值。

    (Choose the **Type** and **Routing Policy** values from the drop-down lists.)

    |记录名称|记录类型|值|TTL (Seconds)|路由策略|
    |:-----|:-----|:-----|:-----|:-----|
    |_sip._tls|SRV - ID 服务器的特定于应用程序的值|100 1 443 sipdir.online.lync.com. **此值必须以句点 (.) 结尾**> <br/> **注意：** 建议复制粘贴此条目，以保证正确保留所有空格。|300|简单|
    |_sipfederationtls._tcp|SRV - ID 服务器的特定于应用程序的值|100 1 5061 sipfed.online.lync.com. **此值必须以句点 (.) 结尾。** <br/> **注意：** 建议复制粘贴此条目，以保证正确保留所有空格。|300|简单|

1. 若要添加其他 SRV 记录，请选择 **“添加另** 一条记录”，使用表中下一行中的值创建记录，然后再次选择 **“创建记录**”。

   :::image type="content" source="../../media/dns-aws/aws-domians-srv-create-records.png" alt-text="选择“创建记录”。":::

> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果在添加 DNS 记录后遇到邮件流问题或其他问题，请参阅[查找在添加域或 DNS 记录后遇到的问题并进行修复](../get-help-with-domains/find-and-fix-issues.md)。

### <a name="add-the-two-required-cname-records-for-skype-for-business"></a>为Skype for Business添加两条所需的 CNAME 记录

1. 要开始，请使用[此链接](https://console.aws.amazon.com/route53/home)转到你在 AWS 上的域页面。 系统将会提示您先登录。

1. 在登陆页 **上的“域**”下，选择 **“已注册的域**”。

1. 在 **“域名”** 下，选择要在Microsoft 365中设置的域。

    **注意**：如果尚未为域创建托管区域，请选择 **“创建托管区域** ”并完成步骤，然后再转到下一步。

   :::image type="content" source="../../media/dns-aws/aws-domains-1.png" alt-text="选择域的名称。":::

1. 选择 **“管理 DNS**”。

   :::image type="content" source="../../media/dns-aws/aws-domains-2.png" alt-text="从下拉列表中选择“管理 DNS”。":::

1. 在 **“域名**”下，选择要验证的域的托管区域版本的域名。

   :::image type="content" source="../../media/dns-aws/aws-domains-3.png" alt-text="选择域的名称。":::

1. 选择 **“创建记录**”。

   :::image type="content" source="../../media/dns-aws/aws-domains-create-record.png" alt-text="选择“创建记录”。":::

1. 在新记录的框中，键入或复制并粘贴下表中的值。

     (从下拉列表中选择 **类型** 和 **路由策略** 值。) 

    |记录名称|记录类型|值|TTL|路由策略|
    |:-----|:-----|:-----|:-----|:-----|
    |sip|CNAME - 规范名称|sipdir.online.lync.com. <br/> **此值必须以句点 (.) 结尾。**|300|简单|
    |lyncdiscover|CNAME - 规范名称|webdir.online.lync.com. <br/> **此值必须以句点 (.) 结尾。**|300|简单|

1. 若要添加其他 CNAME 记录，请选择 **“添加另一条记录**”，使用表中下一行中的值创建记录。

1. 选择 **“创建记录**”。

   :::image type="content" source="../../media/dns-aws/aws-domains-cname-create-records.png" alt-text="选择“创建记录”。":::

> [!NOTE]
> DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。

## <a name="advanced-option-intune-and-mobile-device-management-for-microsoft-365"></a>高级选项：适用于Microsoft 365的Intune和移动设备管理

此服务可帮助保护和远程管理连接到域的移动设备。 移动设备管理需要两条 CNAME 记录，以便用户可以将设备注册到服务。

### <a name="add-the-two-required-cname-records-for-mobile-device-management"></a>添加移动设备管理所需的两条 CNAME 记录

1. 要开始，请使用[此链接](https://console.aws.amazon.com/route53/home)转到你在 AWS 上的域页面。 系统将会提示您先登录。

1. 在登陆页 **上的“域**”下，选择 **“已注册的域**”。

1. 在 **“域名”** 下，选择要在Microsoft 365中设置的域。

    **注意**：如果尚未为域创建托管区域，请选择 **“创建托管区域** ”并完成步骤，然后再转到下一步。

   :::image type="content" source="../../media/dns-aws/aws-domains-1.png" alt-text="选择域的名称。":::

1. 选择 **“管理 DNS**”。

   :::image type="content" source="../../media/dns-aws/aws-domains-2.png" alt-text="从下拉列表中选择“管理 DNS”。":::

1. 在 **“域名**”下，选择要验证的域的托管区域版本的域名。

   :::image type="content" source="../../media/dns-aws/aws-domains-3.png" alt-text="选择域的名称。":::

1. 选择 **“创建记录**”。

   :::image type="content" source="../../media/dns-aws/aws-domains-create-record.png" alt-text="选择“创建记录”。":::

1. 在新记录的框中，键入或复制并粘贴下表中的值。

     (从下拉列表中选择 **类型** 和 **路由策略** 值。) 

    |记录名称|记录类型|值|TTL|路由策略|
    |:-----|:-----|:-----|:-----|:-----|
    |enterpriseregistration|CNAME - 规范名称|enterpriseregistration.windows.net. <br/> **此值必须以句点 (.) 结尾。**|300|简单|
    |EnterpriseEnrollment|CNAME - 规范名称|enterpriseenrollment-s.manage.microsoft.com. <br/> **此值必须以句点 (.) 结尾。**|300|简单|

1. 若要添加其他 CNAME 记录，请选择 **“添加另一条记录**”，使用表中下一行中的值创建记录。

1. 选择 **“创建记录**”。

   :::image type="content" source="../../media/dns-aws/aws-domains-cname-create-records.png" alt-text="选择“创建记录”。":::

> [!NOTE]
> DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。
