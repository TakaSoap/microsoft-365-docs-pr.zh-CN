---
title: 更改名称服务器以使用任意域注册机构设置 Microsoft 365
f1.keywords:
- CSH
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
- Adm_TOC
- Adm_O365_Setup
ms.custom:
- okr_smb
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEU150
- GEA150
ms.assetid: a8b487a9-2a45-4581-9dc4-5d28a47010a2
description: 了解如何在 Microsoft 365 中添加和设置域，以便电子邮件和 Skype for Business Online 等服务使用你自己的域名。
ms.openlocfilehash: 492bc5d2a5f3fd9810f045e7effda1ea20fa15ed
ms.sourcegitcommit: 849b365bd3eaa9f3c3a9ef9f5973ef81af9156fa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/16/2020
ms.locfileid: "49688245"
---
# <a name="change-nameservers-to-set-up-microsoft-365-with-any-domain-registrar"></a>更改名称服务器以使用任意域注册机构设置 Microsoft 365

 如果找不到要查找的内容，请 **[查看域常见问题解答](../setup/domains-faq.yml)**。 
  
检查 ["设置域 (主机 ](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md) 特定的说明) 首先查看我们是否提供了注册机构的说明。 
  
按照以下说明在 Microsoft 365 中添加和设置域，以便电子邮件和 Teams 等服务使用你自己的域名。 为此，将验证域，然后将域的名称服务器更改为 Microsoft 365，以便可以设置正确的 DNS 记录。 如果以下语句描述了您的情况，请按照以下步骤操作：
  
- 你有你自己的域，并且想要设置它以使用 Microsoft 365。
    
- 您希望 Microsoft 365 管理 DNS 记录。  (，可以管理 [自己的 DNS](../setup/add-domain.md)记录 .) 
    
## <a name="add-a-txt-or-mx-record-for-verification"></a>添加 TXT 记录或 MX 记录进行验证
<a name="BKMK_verify"> </a>

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
    
|||||
|:-----|:-----|:-----|:-----|
|**记录类型** <br/> |**别名** 或 **主机名称** <br/> |**值** <br/> |**TTL** <br/> |
|TXT  <br/> |执行下列操作之一：键入 **@** ，将该字段留空或键入你的域名。  <br/> > [!NOTE]> 此字段对不同的 DNS 主机有不同的要求。           
|MS=ms *XXXXXXXX*  <br/> > [!NOTE]> 这是一个示例。 在这里使用来自 Microsoft 365 中的表的具体“**目标地址或指向的地址**”值。           [如何查找此项？](../get-help-with-domains/information-for-dns-records.md)          |将此值设置为 **1 小时** 或等效的分钟数 ( **60** )、秒数 ( **3600** )，等等。  <br/> |
   
**如果您创建 MX 记录，请使用这些值：**
    
||||||
|:-----|:-----|:-----|:-----|:-----|
|**记录类型**|**别名** 或 **主机名称**|**值**|**优先级**|**TTL**|
|MX|键入" **@** "或你的域名。 |MS=ms *XXXXXXXX* > [!NOTE]> 这是一个示例。 在这里使用来自 Microsoft 365 中的表的具体“**目标地址或指向的地址**”值。           [如何查找此项？](../get-help-with-domains/information-for-dns-records.md)          |对于“**优先级**”，为避免与用于邮件流的 MX 记录发生冲突，请使用比任何现有 MX 记录的优先级要低的优先级。 有关优先级的详细信息，请参阅[什么是 MX 优先级？](../setup/domains-faq.yml) |将此值设置为 **1 小时** 或等效的分钟数 ( **60** )、秒数 ( **3600** )，等等。 |
   
### <a name="save-the-record"></a>保存记录

在域注册机构网站添加了记录后，你将返回到 Microsoft 365 并请求 Microsoft 365 查找记录。
  
Microsoft 365 找到正确的 TXT 记录表明域已通过验证。
  

1. 在管理中心，转到“**设置**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">域</a>”页面。
    
2. 在“**域**”页面上，选择要验证的域。 
    
  
3. 在“**设置**”页面上，选择“**开始设置**”。
 
    
  
4. 在“**验证域**”页面上，选择“**验证**”。
    
    
  
> [!NOTE]
>  DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。 
  
## <a name="change-your-domains-nameserver-ns-records"></a>更改域的名称服务器 (NS) 记录
<a name="BKMK_nameservers"> </a>

在 Microsoft 365 中执行域设置向导的最后一步时，还有一项任务。 若要使用 Microsoft 365 服务（如电子邮件）设置域，请更改域注册机构中的域名称服务器 (或 NS) 记录，以指向 Microsoft 365 主名称服务器和辅助名称服务器。 然后，由于 Microsoft 365 托管 DNS，因此会自动为服务设置所需的 DNS 记录。 通过按照您的域注册机构在其网站的帮助内容中所提供步骤进行操作，您可以自己更新名称服务器记录。 如果不熟悉 DNS，请联系域注册机构的支持人员。

::: moniker range="o365-worldwide"
  
若要在域注册机构的网站上更改您的域的名称服务器，请执行以下步骤：
  
1. 在域注册机构网站上查找区域，您可以在其中更改域的名称服务器，或可在其中使用自定义名称服务器的区域。
    
2. 创建名称机记录，或编辑现有名称机记录以匹配以下值：
    
|||
|:-----|:-----|
|首选名称服务器  <br/> |ns1.bdm.microsoftonline.com  <br/> |
|次要名称服务器  <br/> |ns2.bdm.microsoftonline.com  <br/> |
|第三个名称服务器  <br/> |ns3.bdm.microsoftonline.com  <br/> |
|第四个名称服务器  <br/> |ns4.bdm.microsoftonline.com  <br/> |
   
   > [!TIP]
   > 最好添加所有四条记录，但如果你的注册机构仅支持两个，ns1.bdm.microsoftonline.com ns2.bdm.microsoftonline.com。  
  
3. 保存所做的更改。
    
> [!CAUTION]
> 当您将域的 NS 记录更改为指向 Microsoft 365 名称服务器时，当前与域关联的所有服务都受到影响。 如果您跳过了向导中的任何步骤，或是将域用于博客、购物车或其他服务，则需要执行一些附加步骤。 否则此更改可能会导致服务停机时间，例如导致电子邮件访问丢失或您的当前网站不可访问。 

::: moniker-end

::: moniker range="o365-21vianet"
  
1. 在域注册机构的网站上查找您可以在其中编辑您的域的名称服务器的区域。
    
2. 创建两个名称服务器记录，或编辑现有名称服务器记录匹配以下值：
    
|||
|:-----|:-----|
|首选名称服务器  <br/> |ns1.dns.partner.microsoftonline.cn  <br/> |
|次要名称服务器  <br/> |ns2.dns.partner.microsoftonline.cn  <br/> |
   
   > [!TIP]
   > 您至少应该使用两个名称机记录。 如果列出了任何其他名称服务器，您可以删除它们，或者将其更改为ns3.dns.partner.microsoftonline.cn ns4.dns.partner.microsoftonline.cn。  
  
3. 保存所做的更改。
    
> [!CAUTION]
> 当您将域的 NS 记录更改为指向由世纪银行运营的 Office 365 时，当前与域关联的所有服务都受到影响。 如果您跳过了向导中的任何步骤，或是将域用于博客、购物车或其他服务，则需要执行一些附加步骤。 否则此更改可能会导致服务停机时间，例如导致电子邮件访问丢失或您的当前网站不可访问。 

::: moniker-end
  
例如，以下是电子邮件和网站托管可能需要的一些附加步骤：
  
- 在更改 NS 记录之前，将使用您的域的所有电子邮件地址移动到 Microsoft 365。
    
- 希望添加当前用于网站地址的域，如 www.fourthcoffee.com？ 在添加域以保持其网站托管位置（现在托管网站）时，您可以执行以下步骤，以便用户仍可在将域的 NS 记录更改为指向 Microsoft 365 后访问网站。

1. 在管理中心，转到“**设置**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">域</a>”页面。

2. 在"**域**"页上，选择域，然后选择 **"DNS 记录"。**

3. 在 **"管理 DNS"** 下 **，选择"自定义记录**"，然后选择 **"新建自定义记录"。**

4. 选择要添加的 DNS 记录的类型，然后键入新记录的信息。

5. 选择“**保存**”。
    
> [!NOTE]
> Your nameserver record updates may take up to several hours to update across the Internet's DNS system. 然后，你的 Microsoft 电子邮件和其他服务都将设置为使用你的域。 
  
