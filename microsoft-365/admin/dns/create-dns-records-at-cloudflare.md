---
title: 在 Cloudflare 为 Microsoft 创建 DNS 记录
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
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
description: 了解如何在 Cloudflare for Microsoft 中验证域并设置电子邮件、Skype for Business Online 和其他服务的 DNS 记录。
ms.openlocfilehash: 0a80cf059a3a69dcb8aa48251875410f35684286
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50910374"
---
# <a name="create-dns-records-at-cloudflare-for-microsoft"></a>在 Cloudflare 为 Microsoft 创建 DNS 记录

 如果找不到要查找的内容，请 **[查看域常见问题解答](../setup/domains-faq.yml)**。 
  
如果 Cloudflare 是你的 DNS 托管提供商，请按照本文中的步骤验证域并设置电子邮件、Skype for Business Online 等的 DNS 记录。
  
在 Cloudflare 添加这些记录后，你的域将设置为使用 Microsoft 365 服务。
  
  
> [!NOTE]
>  DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。 
  
## <a name="change-your-domains-nameserver-ns-records"></a>更改域的名称服务器 (NS) 记录
<a name="BKMK_Nameservers"> </a>

> [!IMPORTANT]
> 必须在购买和注册域的域注册机构中执行此过程。 
  
注册 Cloudflare 时，你使用 Cloudflare 安装过程添加了域。 
  
你添加的域是从 Cloudflare 或单独的域注册机构购买的。 若要在 Microsoft 365 中验证和创建域的 DNS 记录，首先需要更改域注册机构中的名称服务器，以便它们使用 Cloudflare 的名称服务器。
  
若要在域注册机构的网站上更改域的名称服务器，请执行以下步骤。
  
1. 在域注册机构的网站上查找您可以在其中编辑您的域的名称服务器的区域。
    
2. 使用下表中的值创建两个名称机记录，或编辑现有名称机记录，以便它们与这些值匹配。
    
    |||
    |:-----|:-----|
    |首选名称服务器  <br/> |使用 Cloudflare 提供的名称器值。  <br/> |
    |次要名称服务器  <br/> |使用 Cloudflare 提供的名称器值。  <br/> |
   
    > [!TIP]
    > You should use at least two name server records. 如果列出了任何其他名称服务器，您应该将其删除。 
  
3. 保存所做的更改。
    
> [!NOTE]
> Your nameserver record updates may take up to several hours to update across the Internet's DNS system. 然后，你的 Microsoft 电子邮件和其他服务都将设置为使用你的域。 
  
## <a name="add-a-txt-record-for-verification"></a>添加 TXT 记录进行验证
<a name="BKMK_verify"> </a>

在将域用于 Microsoft 之前，必须确保你拥有该域。如果你能够在域注册机构处登录到你的帐户并创建 DNS 记录，便可向 Microsoft 证明你是域所有者。
  
> [!NOTE]
> 此记录仅用于验证您是否拥有自己的域；它不会影响其他任何内容。 如果需要，您可以以后将其删除。 
  
1. To get started， go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login). 系统将会提示您先登录。
  
2. 在 **主页** 上，选择要更新的域。 
  
3. 在域 **的"** 概述"页面上，选择 **"DNS"。**

  
4. 在 **"DNS 管理"** 页上，单击" **添加** 记录"，然后从下表中选择值。 
    
    | 类型 | 名称 | 自动 TTL | 内容 |
    |:-----|:-----|:-----|:----|
    |TXT  <br/> |@  <br/> |30 分钟  <br/> |MS=ms *XXXXXXXX*  <br/> **注意：** 这是一个示例。 在这里使用表中的特定“**目标地址或指向的地址**”值。           [如何查找此项？](../get-help-with-domains/information-for-dns-records.md)    |
  
    
5. 选择“**保存**”。
  
  
9. 请在继续之前等待数分钟，以便您刚刚创建的记录可以通过 Internet 完成更新。
    
现在，你已在你的域注册机构网站添加了记录，你将返回到 Microsoft 并搜索该记录。
  
Microsof 找到正确的 TXT 记录表明域已通过验证。
  
1. 在 Microsoft 管理中心，转到“**设置**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">域</a>”页面。

    
2. 在“**域**”页面上，选择要验证的域。 
    
    
  
3. 在“**设置**”页面上，选择“**开始设置**”。
    
    
  
4. 在“**验证域**”页面上，选择“**验证**”。
    
    
  
> [!NOTE]
>  DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>添加一条 MX 记录，确保发往你的域的电子邮件将会发送到 Microsoft
<a name="BKMK_add_MX"> </a>

1. To get started， go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login). 系统将会提示您先登录。
  
2. 在 **主页** 上，选择要更新的域。 
  
3. 在域 **的"** 概述"页面上，选择 **"DNS"。**

  
4. 在 **"DNS 管理"** 页上，单击" **添加** 记录"，然后从下表中选择值。 
    
    | 类型 | 名称 | 邮件服务器 | 优先级 | TTL |
    |:-----|:-----|:-----|:-----|:-----|
    |MX  <br/> |@  <br/> |*\<domain-key\>*  .mail.protection.outlook.com  <br/> **注意：** 从  *\<domain-key\>*  Microsoft 365 帐户获取你的。   如何查找此内容？[](../get-help-with-domains/information-for-dns-records.md) |1  <br/> 有关优先级的详细信息，请参阅[什么是 MX 优先级？](../setup/domains-faq.yml) <br/>|30 分钟  <br/> |
   

  
5. 选择“**保存**”。
  
9. 如果 **"MX** 记录"部分列出了任何其他 MX 记录，则通过选择"删除 X 记录" (**删除)** 删除它们。 
  
10. 在确认对话框中，选择 **"删除** "以确认所做的更改。 

  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a>添加 Microsoft 所需的六条 CNAME 记录
<a name="BKMK_add_CNAME"> </a>

1. To get started， go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login). 系统将会提示您先登录。
    
  
2. 在 **主页** 上，选择要更新的域。 
  
3. 在域 **的"** 概述"页面上，选择 **"DNS"。**

  
4. 添加五条 CNAME 记录中的第一条。
    
    在 **"DNS 管理"** 页上，单击" **添加** 记录"，然后从下表中选择值。
    
    
    | 类型 | 名称 | Target | TTL |
    |:-----|:-----|:-----|:-----|
    |CNAME  <br/> |自动发现  <br/> |autodiscover.outlook.com  <br/> |30 分钟  <br/> |
    |CNAME  <br/> |sip  <br/> |sipdir.online.lync.com  <br/> |30 分钟  <br/> |
    |CNAME  <br/> |lyncdiscover  <br/> |webdir.online.lync.com  <br/> |30 分钟  <br/> |
    |CNAME  <br/> |enterpriseregistration  <br/> |enterpriseregistration.windows.net  <br/> |30 分钟  <br/> |
    |CNAME  <br/> |enterpriseenrollment  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> |30 分钟  <br/> |
    |CNAME  <br/> |msoid  <br/> |clientconfig.microsoftonline-p.net  <br/> |30 分钟  <br/> |
    
  
5. 选择 **"DNS 流量** "图标 (橙色云更改为灰色) 以绕过 Cloudflare 服务器。
  
6. 选择“**保存**”。
  
7. 逐一添加其他 5 条 CNAME 记录。

    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>为 SPF 添加 TXT 记录以帮助防止垃圾邮件
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> 一个域所拥有的 SPF 的 TXT 记录不能超过一个。 如果域具有多个 SPF 记录，你将收到电子邮件错误，其中随附发送和垃圾邮件分类问题。 如果你的域已有 SPF 记录，请不要为 Microsoft 365 创建新记录。 可以将所需的 Microsoft 365 值添加到当前记录，这样就拥有包含两组值的 *单个* SPF 记录。 
  
1. To get started， go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login). 系统将会提示您先登录。
    
  
2. 在 **主页** 上，选择要更新的域。 
  
3. 在域 **的"** 概述"页面上，选择 **"DNS"。**

  
4. 在 **"DNS 管理"** 页上，单击" **添加** 记录"，然后从下表中选择值。  
    
    | 类型 | 名称 | TTL | 内容 |
    |:-----|:-----|:-----|:-----|
    |TXT  <br/> |@  <br/> |30 分钟  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **注意：** 建议复制粘贴此条目，以保证正确保留所有空格。   |

 
5. 选择“**保存**”。
    

  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>添加 Microsoft 所需的两条 SRV 记录
<a name="BKMK_add_SRV"> </a>

> [!IMPORTANT]
> 请记住，Cloudflare 负责提供此功能。 如果你看到以下步骤与图形用户界面中当前 Cloudflare GUI (差异) ，请利用 [Cloudflare 社区](https://community.cloudflare.com/)。 

1. To get started， go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login). 系统将会提示您先登录。
      
2. 在 **主页** 上，选择要更新的域。 
  
3. 在域 **的"** 概述"页面上，选择 **"DNS"。**
  
4. 添加两条 SRV 记录中的第一条记录。

    在 **"DNS 管理"** 页上 **，单击"** 添加记录"，然后从下表的第一行中选择值。
        
    | 类型 | 服务 | 协议 | 名称 | TTL | Priority | 粗细 | 端口 | Target |
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |SRV|_sip |TLS |使用你的 *domain_name;* 例如，contoso.com  |30 分钟 | 100|1 |443 |sipfed.online.lync.com  |
    |SRV|_sipfederationtls | TCP|使用你的 *domain_name;* 例如，contoso.com   |30 分钟 |100 |1 |5061 | sipfed.online.lync.com |

  
5. 选择“**保存**”。

  
6. 通过从表的第二行选择值添加其他 SRV 记录。 

    
> [!NOTE]
>  DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。 
