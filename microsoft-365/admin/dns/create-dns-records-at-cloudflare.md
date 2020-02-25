---
title: 在 Cloudflare 上为 Office 365 创建 DNS 记录
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
- Adm_O365_Setup
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 84acd4fc-6eec-4d00-8bed-568f036ae2af
description: 了解如何在 Cloudflare for Office 365 中验证您的域并为电子邮件、Skype for Business Online 和其他服务设置 DNS 记录。
ms.openlocfilehash: efd7a4a41a0cc27c2a50da732d648c87c79c6ff7
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/24/2020
ms.locfileid: "42240381"
---
# <a name="create-dns-records-at-cloudflare-for-office-365"></a>在 Cloudflare 上为 Office 365 创建 DNS 记录

 如果找不到要查找的内容，请**[查看域常见问题解答](../setup/domains-faq.md)**。 
  
如果 Cloudflare 是您的 DNS 托管提供商，请按照本文中的步骤验证您的域并为电子邮件、Skype for Business Online 等设置 DNS 记录。
  
在 Cloudflare 中添加这些记录后，您的域将设置为与 Office 365 服务配合使用。
  
若要了解如何与 Office 365 结合使用网站的 Web 宿主和 DNS，请参阅[配合使用公共网站与 Office 365](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx)。
  
> [!NOTE]
>  DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。 
  
## <a name="change-your-domains-nameserver-ns-records"></a>更改域的名称服务器 (NS) 记录
<a name="BKMK_Nameservers"> </a>

> [!IMPORTANT]
> 必须在购买和注册域的域注册机构中执行此过程。 
  
注册 Cloudflare 时，使用 Cloudflare**安装**过程添加了一个域。 
  
您添加的域是从单独的域注册机构购买的;Cloudflare 不提供域注册服务。 若要在 Office 365 中验证和创建域的 DNS 记录，首先需要在域注册机构中更改名称服务器，以便它们使用 Cloudflare 的名称服务器。
  
若要在域注册机构的网站上更改域的名称服务器，请执行以下步骤。
  
1. 在域注册机构的网站上查找您可以在其中编辑您的域的名称服务器的区域。
    
2. 通过使用下表中的值创建两个名称服务器记录，或编辑现有的名称服务器记录以使其与这些值匹配。
    
    |||
    |:-----|:-----|
    |首选名称服务器  <br/> |使用由 Cloudflare 提供的名称服务器值。  <br/> |
    |次要名称服务器  <br/> |使用由 Cloudflare 提供的名称服务器值。  <br/> |
   
    > [!TIP]
    > You should use at least two name server records. 如果列出了任何其他名称服务器，则应将其删除。 
  
3. 保存所做的更改。
    
> [!NOTE]
> 你的名称服务器记录更新可能需要多达数小时才能在 Internet 的 DNS 系统中更新。然后，你的 Office 365 电子邮件和其他服务将全部设置为使用你的域。 
  
## <a name="add-a-txt-record-for-verification"></a>添加 TXT 记录进行验证
<a name="BKMK_verify"> </a>

在将域用于 Office 365 之前，必须确保你拥有该域。如果你能够在域注册机构处登录到你的帐户并创建 DNS 记录，便可向 Office 365 证明你是所有者。
  
> [!NOTE]
> 此记录仅用于验证您是否拥有自己的域；它不会影响其他任何内容。 如果需要，您可以以后将其删除。 
  
1. 若要开始，请使用[此链接](https://www.cloudflare.com/a/login)转到 Cloudflare 上的 "域" 页面。 You'll be prompted to log in first.
  
2. 在**主页**上，选择要更新的域。 
  
3. 在域的 "**概述**" 页上，选择 " **DNS**"。

  
4. 在 " **DNS 管理**" 页上，单击 "**添加记录**"，然后选择下表中的值。 
    
    |**类型**|**名称**|**自动 TTL**|**内容**|
    |:-----|:-----|:-----|:----|
    |TXT  <br/> |@  <br/> |30 分钟  <br/> |MS=ms *XXXXXXXX*  <br/> **注意：** 这是一个示例。 在这里使用来自 Office 365 中的表的特定" **目标或指向的地址**"值。           [如何查找此内容？](../get-help-with-domains/information-for-dns-records.md)    |
  
    
5. 选择“**保存**”。
  
  
9. 请在继续之前等待数分钟，以便您刚刚创建的记录可以通过 Internet 完成更新。
    
Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.
  
When Office 365 finds the correct TXT record, your domain is verified.
  
1. 在管理中心中，转到 "**设置** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">域</a>" 页。

    
2. 在 "**域**" 页上，选择要验证的域。 
    
    
  
3. 在 "**设置**" 页上，选择 "**启动安装程序**"。
    
    
  
4. 在 "**验证域**" 页上，选择 "**验证**"。
    
    
  
> [!NOTE]
>  DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a>添加一条 MX 记录，确保发往您的域的电子邮件发送到 Office 365
<a name="BKMK_add_MX"> </a>

1. 若要开始，请使用[此链接](https://www.cloudflare.com/a/login)转到 Cloudflare 上的 "域" 页面。 You'll be prompted to log in first.
  
2. 在**主页**上，选择要更新的域。 
  
3. 在域的 "**概述**" 页上，选择 " **DNS**"。

  
4. 在 " **DNS 管理**" 页上，单击 "**添加记录**"，然后选择下表中的值。 
    
    |**类型**|**名称**|**邮件服务器**|**优先级**|**TTL**|
    |:-----|:-----|:-----|:-----|:-----|
    |MX  <br/> |@  <br/> |*\<域密钥\>*  .mail.protection.outlook.com  <br/> **注意：** 从 Office 365 帐户中获取你* \<的域密钥\> * 。   如何查找此内容？[](../get-help-with-domains/information-for-dns-records.md) |1  <br/> 有关优先级的详细信息，请参阅[什么是 MX 优先级？](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx) <br/>|30 分钟  <br/> |
   

  
5. 选择“**保存**”。
  
9. 如果 " **Mx 记录**" 一节中列出了任何其他 MX 记录，请通过选择 "**删除（X）** " 图标将其删除。 
  
10. 在确认对话框中，选择 "**删除**" 以确认更改。 

  
## <a name="add-the-six-cname-records-that-are-required-for-office-365"></a>添加 Office 365 所需的6条 CNAME 记录
<a name="BKMK_add_CNAME"> </a>

1. 若要开始，请使用[此链接](https://www.cloudflare.com/a/login)转到 Cloudflare 上的 "域" 页面。 You'll be prompted to log in first.
    
  
2. 在**主页**上，选择要更新的域。 
  
3. 在域的 "**概述**" 页上，选择 " **DNS**"。

  
4. 添加五个 CNAME 记录中的第一个。
    
    在 " **DNS 管理**" 页上，单击 "**添加记录**"，然后选择下表中的值。
    
    
    |**类型**|**名称**|**Target**|**TTL**|
    |:-----|:-----|:-----|:-----|
    |CNAME  <br/> |autodiscover  <br/> |autodiscover.outlook.com  <br/> |30 分钟  <br/> |
    |CNAME  <br/> |sip  <br/> |sipdir.online.lync.com  <br/> |30 分钟  <br/> |
    |CNAME  <br/> |lyncdiscover  <br/> |webdir.online.lync.com  <br/> |30 分钟  <br/> |
    |CNAME  <br/> |enterpriseregistration  <br/> |enterpriseregistration.windows.net  <br/> |30 分钟  <br/> |
    |CNAME  <br/> |enterpriseenrollment  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> |30 分钟  <br/> |
    |CNAME  <br/> |msoid  <br/> |clientconfig.microsoftonline-p.net  <br/> |30 分钟  <br/> |
    
  
5. 选择 " **DNS 流量**" 图标（橙色云）以绕过 Cloudflare 服务器。
  
6. 选择“**保存**”。
  
7. 逐一添加其他 5 条 CNAME 记录。

    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>为 SPF 添加 TXT 记录以帮助防止垃圾邮件
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> You cannot have more than one TXT record for SPF for a domain. If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues. If you already have an SPF record for your domain, don't create a new one for Office 365. 改为将所需的 Office 365 值添加到当前记录，以便您具有包含两组值的*单个*SPF 记录。 
  
1. 若要开始，请使用[此链接](https://www.cloudflare.com/a/login)转到 Cloudflare 上的 "域" 页面。 You'll be prompted to log in first.
    
  
2. 在**主页**上，选择要更新的域。 
  
3. 在域的 "**概述**" 页上，选择 " **DNS**"。

  
4. 在 " **DNS 管理**" 页上，单击 "**添加记录**"，然后选择下表中的值。  
    
    |**类型**|**名称**|**TTL**|**内容**|
    |:-----|:-----|:-----|:-----|
    |TXT  <br/> |@  <br/> |30 分钟  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **注意：** 我们建议您复制并粘贴此条目，以确保所有的间距保持正确。   |

 
5. 选择“**保存**”。
    

  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a>添加 Office 365 所需的两条 SRV 记录
<a name="BKMK_add_SRV"> </a>

> [!IMPORTANT]
> 请记住，Cloudflare 有责任使此功能可用。 如果您看到以下步骤与当前 Cloudflare GUI （图形用户界面）之间的差异，请利用[Cloudflare 社区](https://community.cloudflare.com/)。 

1. 若要开始，请使用[此链接](https://www.cloudflare.com/a/login)转到 Cloudflare 上的 "域" 页面。 You'll be prompted to log in first.
      
2. 在**主页**上，选择要更新的域。 
  
3. 在域的 "**概述**" 页上，选择 " **DNS**"。
  
4. 添加两条 SRV 记录中的第一条记录。

    在 " **DNS 管理**" 页上，单击 "**添加记录**"，然后选择下表中第一行的值。
        
    |**类型**|**服务**|**协议**|**名称**|**TTL**|**优先级**|**权重**|**端口**|**目标**|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |SRV|_sip |TLS |使用*domain_name*;例如，contoso.com  |30 分钟 | 100|1 |443 |sipfed.online.lync.com  |
    |SRV|_sipfederationtls | TCP|使用*domain_name*;例如，contoso.com   |30 分钟 |100 |1 |5061 | sipfed.online.lync.com |

  
5. 选择“**保存**”。

  
6. 通过从表的第二行中选择值来添加其他 SRV 记录。 

    
> [!NOTE]
>  DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。 
  
