---
title: 连接 DNS 记录，123-reg.co.uk Microsoft 365
f1.keywords:
- CSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
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
ms.assetid: 1f2d08c9-2a88-4d2f-ae1f-e39f9e358b17
description: 了解如何验证域，并设置 Microsoft Skype for Business Online 和其他服务的 DNS 123-reg.co.uk 记录。
ms.openlocfilehash: 64fdb9df70598aed5113620ea11caf8f70b5926a
ms.sourcegitcommit: bf3965b46487f6f8cf900dd9a3af8b213a405989
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2021
ms.locfileid: "60648703"
---
# <a name="connect-your-dns-records-at-123-regcouk-to-microsoft-365"></a>连接 DNS 记录，123-reg.co.uk Microsoft 365

 **如果找不到要查找的内容，请 [查看域常见问题解答](../setup/domains-faq.yml)** 。 
  
如果 DNS 托管提供者是 123-reg.co.uk，请按本文中的步骤验证域并为电子邮件、Skype for Business Online 等设置 DNS 记录。
  
在添加这些记录 123-reg.co.uk，您的域将设置为使用Microsoft 服务。 
  
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果在添加 DNS 记录后遇到邮件流问题或其他问题，请参阅[查找在添加域或 DNS 记录后遇到的问题并进行修复](../get-help-with-domains/find-and-fix-issues.md)。 
  
## <a name="add-a-txt-record-for-verification"></a>添加 TXT 记录进行验证

在将域用于 Microsoft 之前，必须确保你拥有该域。如果你能够在域注册机构处登录到你的帐户并创建 DNS 记录，便可向 Microsoft 证明你是域所有者。
  
> [!NOTE]
> 此记录仅用于验证您是否拥有自己的域；它不会影响其他任何内容。 如果需要，您可以以后将其删除。 
  
1. 要开始，请使用[此链接](https://www.123-reg.co.uk/secure/cpanel/domain/overview)转到您在 123-reg.co.uk 上的域页面。 系统将会提示您先登录。

2. 选择 **"** 域"，在"域名概述"页上，选择要验证的域的名称或转到"控制面板"。

   :::image type="content" source="../../media/dns-123reg/123reg-domains-1.png" alt-text="选择要验证的域。":::

3. 在"管理域"页面上的"高级 **域设置"下**，选择"**管理 DNS"。**
  
   :::image type="content" source="../../media/dns-123reg/123reg-domains-2.png" alt-text="从下拉列表中选择&quot;管理 DNS&quot;。":::
  
4. 在"管理 DNS"页上，选择" **高级 DNS"** 选项卡。 
  
   :::image type="content" source="../../media/dns-123reg/123reg-domains-3.png" alt-text="选择&quot;高级 DNS&quot;选项卡。":::
  
5. In the **Type** box for the new record choose **TXT/SPF** from the drop-down list， and then type or copy and paste the other values from the following table. 

    ||||
    |:-----|:-----|:-----|
    |**主机名** <br/> |**类型** <br/> |**Destination TXT/SPF** <br/> |
    |@  <br/> |TXT/SPF  <br/> |MS=ms *XXXXXXXX*  <br/> **注意：** 这是一个示例。 在这里使用表中的特定“**目标地址或指向的地址**”值。 [如何查找此项？](../get-help-with-domains/information-for-dns-records.md)          |
  
   :::image type="content" source="../../media/dns-123reg/123reg-domains-TypeTXTSPF.png" alt-text="从下拉列表中选择 TXT/SPF 类型，并填写值。":::

6. 选择“**添加**”。

   :::image type="content" source="../../media/dns-123reg/123reg-domains-TXTSPF-Add.png" alt-text="选择&quot;添加&quot;。":::

   请在继续之前等待数分钟，以便您刚刚创建的记录可以通过 Internet 完成更新。

现在，你已在你的域注册机构网站添加了记录，你将返回到 Microsoft 并请求搜索该记录。 当 Microsof 找到正确的 TXT 记录时，表明域已通过验证。
  
若要验证记录是否Microsoft 365：
  
1. 在管理中心中，转到 **"设置** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">**域"。**</a>

1. On the Domains page， select the domain that you're verifying， and select **Start setup**. 

    :::image type="content" source="../../media/dns-IONOS/IONOS-DomainConnects-2.png" alt-text="选择&quot;开始设置&quot;。":::

1. 选择 **继续**。
  
1. 在“**验证域**”页面上，选择“**验证**”。

> [!NOTE]
> DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>添加一条 MX 记录，确保发往你的域的电子邮件将会发送到 Microsoft

1. 要开始，请使用[此链接](https://www.123-reg.co.uk/secure/cpanel/domain/overview)转到您在 123-reg.co.uk 上的域页面。 系统将会提示您先登录。

2. On the Domain name overview page, select the name of the domain that you want to edit. 

   :::image type="content" source="../../media/dns-123reg/123reg-domains-1.png" alt-text="选择要编辑的域的名称。":::

3. 在"管理域"页面上的"高级 **域设置"下**，选择"**管理 DNS"。**
  
   :::image type="content" source="../../media/dns-123reg/123reg-domains-2.png" alt-text="从下拉列表中选择&quot;管理 DNS&quot;。":::
  
4. 在"管理 DNS"页上，选择" **高级 DNS"** 选项卡。 
  
   :::image type="content" source="../../media/dns-123reg/123reg-domains-3.png" alt-text="选择&quot;高级 DNS&quot;选项卡。":::

5. In the **Type** box for the new record choose **MX** from the drop-down list， and then type or copy and paste the other values from the following table.

    |**主机名**|**类型**|**优先级**|**目标 MX**|
    |:-----|:-----|:-----|:-----|
    |@  <br/> |MX  <br/> |1  <br/> 有关优先级的详细信息，请参阅[什么是 MX 优先级？](../setup/domains-faq.yml) <br/> | *\<domain-key\>*  .mail.protection.outlook.com。  <br/> **此值必须以句点 (.) 结尾。** <br/> **注意：** 从 Microsoft 帐户获取 \<domain-key\>。 [如何查找此项？](../get-help-with-domains/information-for-dns-records.md)          |

   :::image type="content" source="../../media/dns-123reg/123reg-domains-MX.png" alt-text="从下拉列表中选择 MX 类型，然后填写值。":::

6. 选择“**添加**”。

   :::image type="content" source="../../media/dns-123reg/123reg-domains-MX-Add.png" alt-text="选择&quot;添加&quot;。":::

7. 如果存在任何其他 MX 记录，请通过选择"删除" (**删除** 每个记录) 该记录的图标。

   :::image type="content" source="../../media/dns-123reg/123reg-domains-MX-delete.png" alt-text="选择删除 (回收站) 。":::
  
## <a name="add-the-cname-record-required-for-microsoft"></a>添加 Microsoft 所需的 CNAME 记录

1. 要开始，请使用[此链接](https://www.123-reg.co.uk/secure/cpanel/domain/overview)转到您在 123-reg.co.uk 上的域页面。 系统将会提示您先登录。

2. On the Domain name overview page, select the name of the domain that you want to edit. 

   :::image type="content" source="../../media/dns-123reg/123reg-domains-1.png" alt-text="选择要编辑的域的名称。":::

3. 在"管理域"页面上的"高级 **域设置"下**，选择"**管理 DNS"。**
  
   :::image type="content" source="../../media/dns-123reg/123reg-domains-2.png" alt-text="从下拉列表中选择&quot;管理 DNS&quot;。":::
  
4. 在"管理 DNS"页上，选择" **高级 DNS"** 选项卡。 
  
   :::image type="content" source="../../media/dns-123reg/123reg-domains-3.png" alt-text="选择&quot;高级 DNS&quot;选项卡。":::

5. 添加 CNAME 记录。

    In the **Type** box for the new record choose **CNAME** from the drop-down list， and then type or copy and paste the other values from the following table.

    |**主机名**|**类型**|**目标 CNAME**|
    |:-----|:-----|:-----|
    |自动发现  <br/> |CNAME  <br/> |autodiscover.outlook.com.  <br/> **此值必须以句点 (.) 结尾。** <br/> |

   :::image type="content" source="../../media/dns-123reg/123reg-domains-CNAME.png" alt-text="从下拉列表中选择 CNAME 类型，然后填写值。":::

6. 选择“**添加**”。

   :::image type="content" source="../../media/dns-123reg/123reg-domains-CNAME-Add.png" alt-text="选择&quot;添加&quot;。":::

## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>为 SPF 添加 TXT 记录以帮助防止垃圾邮件

> [!IMPORTANT]
> 一个域所拥有的 SPF 的 TXT 记录不能超过一个。 如果域具有多个 SPF 记录，你将收到电子邮件错误，其中随附发送和垃圾邮件分类问题。 如果你的域已有 SPF 记录，请不要为 Microsfot 创建新的 SPF 记录。 相反，将所需的 Microsoft 值添加到当前记录，以便你有一个  *包含这*  两组值的 SPF 记录。 需要示例吗？ 请查看 [Microsoft 的外部域名系统记录](../../enterprise/external-domain-name-system-records.md)。 若要验证 SPF 记录，可使用以下任一 [SPF 验证工具](../setup/domains-faq.yml)。 
  
1. 要开始，请使用[此链接](https://www.123-reg.co.uk/secure/cpanel/domain/overview)转到您在 123-reg.co.uk 上的域页面。 系统将会提示您先登录。

2. On the Domain name overview page, select the name of the domain that you want to edit. 

   :::image type="content" source="../../media/dns-123reg/123reg-domains-1.png" alt-text="选择要编辑的域的名称。":::

3. 在"管理域"页面上的"高级 **域设置"下**，选择"**管理 DNS"。**
  
   :::image type="content" source="../../media/dns-123reg/123reg-domains-2.png" alt-text="从下拉列表中选择&quot;管理 DNS&quot;。":::
  
4. 在"管理 DNS"页上，选择" **高级 DNS"** 选项卡。 
  
   :::image type="content" source="../../media/dns-123reg/123reg-domains-3.png" alt-text="选择&quot;高级 DNS&quot;选项卡。":::

5. In the **Type** box for the new record choose **TXT/SPF** from the drop-down list， and then type or copy and paste the other values from the following table.

    |**主机名**|**类型**|**Destination TXT/SPF**|
    |:-----|:-----|:-----|
    |@  <br/> |TXT/SPF  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **注意：** 建议复制粘贴此条目，以保证正确保留所有空格。           |

   :::image type="content" source="../../media/dns-123reg/123reg-domains-TypeTXTSPF.png" alt-text="从下拉列表中选择 TXT/SPF 类型，并填写值。":::
  
6. 选择“**添加**”。

## <a name="advanced-option-skype-for-business"></a>高级选项：Skype for Business

只有组织将 Skype for Business 用于聊天、电话会议和视频呼叫等联机通信服务时，以及使用 Microsoft Teams。 Skype 4 条记录：2 条 SRV 记录用于用户到用户的通信，2 条 CNAME 记录用于登录和将用户连接到服务。

### <a name="add-the-two-required-srv-records"></a>添加两条必需的 SRV 记录

1. 要开始，请使用[此链接](https://www.123-reg.co.uk/secure/cpanel/domain/overview)转到您在 123-reg.co.uk 上的域页面。 系统将会提示您先登录。

2. On the Domain name overview page, select the name of the domain that you want to edit. 

   :::image type="content" source="../../media/dns-123reg/123reg-domains-1.png" alt-text="选择要编辑的域的名称。":::

3. 在"管理域"页面上的"高级 **域设置"下**，选择"**管理 DNS"。**
  
   :::image type="content" source="../../media/dns-123reg/123reg-domains-2.png" alt-text="从下拉列表中选择&quot;管理 DNS&quot;。":::
  
4. 在"管理 DNS"页上，选择" **高级 DNS"** 选项卡。 
  
   :::image type="content" source="../../media/dns-123reg/123reg-domains-3.png" alt-text="选择&quot;高级 DNS&quot;选项卡。":::

5. 添加两条 SRV 记录中的第一个：

   In the **Type** box for the new record choose **SRV** from the drop-down list， and then type or copy and paste the other values from the following table.

    ||||||
    |:-----|:-----|:-----|:-----|:-----|
    |**主机名**|**类型**|**优先级**|**TTL**|**目标 SRV**|
    |_sip._tls|SRV|100|3600|1 443 sipdir.online.lync.com。 **此值必须以句点 (.) 结尾。**<br> **注意：** 建议复制粘贴此条目，以保证正确保留所有空格。           |
    |_sipfederationtls._tcp|SRV|100|3600|1 5061 sipfed.online.lync.com。 **此值必须以句点 (.) 结尾。** <br> **注意：** 建议复制粘贴此条目，以保证正确保留所有空格。           |
  
   :::image type="content" source="../../media/dns-123reg/123reg-domains-TypeTXTSPF.png" alt-text="从下拉列表中选择 TXT/SPF 类型，并填写值。":::

6. 选择“**添加**”。
  
   :::image type="content" source="../../media/dns-123reg/123reg-domains-TXTSPF-Add.png" alt-text="选择&quot;添加&quot;。":::

7. 添加另一条 SRV 记录。

> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果在添加 DNS 记录后遇到邮件流问题或其他问题，请参阅[查找在添加域或 DNS 记录后遇到的问题并进行修复](../get-help-with-domains/find-and-fix-issues.md)。 

### <a name="add-the-two-required-cname-records"></a>添加两个必需的 CNAME 记录 

1. 要开始，请使用[此链接](https://www.123-reg.co.uk/secure/cpanel/domain/overview)转到您在 123-reg.co.uk 上的域页面。 系统将会提示您先登录。

1. On the Domain name overview page, select the name of the domain that you want to edit. 

   :::image type="content" source="../../media/dns-123reg/123reg-domains-1.png" alt-text="选择要编辑的域的名称。":::

1. 在"管理域"页面上的"高级 **域设置"下**，选择"**管理 DNS"。**
  
   :::image type="content" source="../../media/dns-123reg/123reg-domains-2.png" alt-text="从下拉列表中选择&quot;管理 DNS&quot;。":::
  
1. 在"管理 DNS"页上，选择" **高级 DNS"** 选项卡。 
  
   :::image type="content" source="../../media/dns-123reg/123reg-domains-3.png" alt-text="选择&quot;高级 DNS&quot;选项卡。":::

1. 添加第一条 CNAME 记录。

    In the **Type** box for the new record choose **CNAME** from the drop-down list， and then type or copy and paste the other values from the following table.

    | **主机名** |**类型**|**目标 CNAME**|
    |:-----|:-----|:-----|
    |sip  <br/>|CNAME  <br/> |sipdir.online.lync.com.  <br/> **此值必须以句点 (.) 结尾。** <br/> |
    |lyncdiscover  <br/>|CNAME  <br/> |webdir.online.lync.com.  <br/> **此值必须以句点 (.) 结尾。** <br/> |

   :::image type="content" source="../../media/dns-123reg/123reg-domains-CNAME.png" alt-text="从下拉列表中选择 CNAME 类型，然后填写值。":::

1. 选择“**添加**”。

   :::image type="content" source="../../media/dns-123reg/123reg-domains-CNAME-Add.png" alt-text="选择&quot;添加&quot;。":::
  
1. 添加其他 CNAME 记录。

> [!NOTE]
> DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。 
  
## <a name="advanced-option-intune-and-mobile-device-management-for-microsoft-365"></a>高级选项：Intune 和移动设备管理 for Microsoft 365

此服务可帮助你保护并远程管理连接到域的移动设备。 移动设备管理需要两条 CNAME 记录，以便用户可以将设备注册到服务。

### <a name="add-the-two-required-cname-records"></a>添加两个必需的 CNAME 记录

1. 要开始，请使用[此链接](https://www.123-reg.co.uk/secure/cpanel/domain/overview)转到您在 123-reg.co.uk 上的域页面。 系统将会提示您先登录。

1. On the Domain name overview page, select the name of the domain that you want to edit. 

   :::image type="content" source="../../media/dns-123reg/123reg-domains-1.png" alt-text="选择要编辑的域的名称。":::

1. 在"管理域"页面上的"高级 **域设置"下**，选择"**管理 DNS"。**
  
   :::image type="content" source="../../media/dns-123reg/123reg-domains-2.png" alt-text="从下拉列表中选择&quot;管理 DNS&quot;。":::
  
1. 在"管理 DNS"页上，选择" **高级 DNS"** 选项卡。 
  
   :::image type="content" source="../../media/dns-123reg/123reg-domains-3.png" alt-text="选择&quot;高级 DNS&quot;选项卡。":::

1. 添加第一条 CNAME 记录。

    In the **Type** box for the new record choose **CNAME** from the drop-down list， and then type or copy and paste the other values from the following table.

   | **主机名**|**类型**|**目标 CNAME**|
   |:-----|:-----|:-----|
   | enterpriseregistration <br/> | CNAME  <br/> |enterpriseregistration.windows.net.  <br/> **此值必须以句点 (.) 结尾。** <br/> |
   |enterpriseenrollment  <br/> | CNAME  <br/> |enterpriseenrollment.manage.microsoft.com。  <br/> **此值必须以句点 (.) 结尾。** <br/> |
  
   :::image type="content" source="../../media/dns-123reg/123reg-domains-CNAME.png" alt-text="从下拉列表中选择 CNAME 类型，然后填写值。":::

1. 选择“**添加**”。

   :::image type="content" source="../../media/dns-123reg/123reg-domains-CNAME-Add.png" alt-text="选择&quot;添加&quot;。":::

1. 添加其他 CNAME 记录。

> [!NOTE]
> DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。