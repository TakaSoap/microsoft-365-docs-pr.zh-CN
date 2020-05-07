---
title: 在 web.com 处为 Microsoft 创建 DNS 记录
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: article
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
description: 了解如何验证您的域，并在 web.com for Microsoft 中为电子邮件、Skype for Business Online 和其他服务设置 DNS 记录。
ms.openlocfilehash: a7567688ad9935b30c0749cb7aeffdbe128506ef
ms.sourcegitcommit: 5476c2578400894640ae74bfe8e93c3319f685bd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/06/2020
ms.locfileid: "44048875"
---
# <a name="create-dns-records-at-webcom-for-microsoft"></a>在 web.com 处为 Microsoft 创建 DNS 记录

 如果找不到要查找的内容，请**[查看域常见问题解答](../setup/domains-faq.md)**。 
  
如果 web.com 是您的 DNS 托管提供商，请按照本文中的步骤验证您的域并为电子邮件、Skype for Business Online 等设置 DNS 记录。
  
在 web.com 中添加这些记录后，您的域将设置为与 Microsoft 服务一起使用。

  
> [!NOTE]
>  DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。 
  
## <a name="change-your-domains-nameserver-ns-records"></a>更改域的名称服务器 (NS) 记录
<a name="BKMK_Nameservers"> </a>

> [!IMPORTANT]
> 必须在购买和注册域的域注册机构中执行此过程。 
  
注册 web.com 时，使用 web.com**安装**过程添加了一个域。 
  
若要在 Microsoft 中验证和创建域的 DNS 记录，首先需要更改域注册机构中的名称服务器，以便它们使用 .com 的名称服务器。
  
若要在域注册机构的网站上更改域的名称服务器，请执行以下步骤。
  
1. 在域注册机构的网站上查找您可以在其中编辑您的域的名称服务器的区域。
    
2. 通过使用下表中的值创建两个名称服务器记录，或编辑现有的名称服务器记录以使其与这些值匹配。
    
    |||
    |:-----|:-----|
    |首选名称服务器  <br/> |使用由 web.com 提供的名称服务器值。  <br/> |
    |次要名称服务器  <br/> |使用由 web.com 提供的名称服务器值。  <br/> |
   
    > [!TIP]
    > You should use at least two name server records. 如果列出了任何其他名称服务器，则应将其删除。 
  
3. 保存所做的更改。
    
> [!NOTE]
> Your nameserver record updates may take up to several hours to update across the Internet's DNS system. 然后，你的 Microsoft 电子邮件和其他服务将全部设置为与你的域一起使用。 
  
## <a name="add-a-txt-record-for-verification"></a>添加 TXT 记录进行验证
<a name="BKMK_verify"> </a>

在将域用于 Microsoft 之前，必须确保你拥有该域。如果你能够在域注册机构处登录到你的帐户并创建 DNS 记录，便可向 Microsoft 证明你是域所有者。
  
> [!NOTE]
> 此记录仅用于验证您是否拥有自己的域；它不会影响其他任何内容。 如果需要，您可以以后将其删除。 
  
1. 若要开始，请使用[此链接](https://checkout.web.com/manage-it/index.jsp)转到 web.com 上的 "域" 页面。 先登录。
  
2. 在 "**帐户管理器**" 页上，选择 **"我的域名**"。 
  
3. 在 "* * 管理 * 我的域 * * *" 下，选择 "**编辑高级 DNS 记录**"。

  
4. 在 "**域名**" 页上的 "**文本（TXT 记录）**" 下，单击 "**编辑 TXT 记录**"，然后选择下表中的值。 
    
    |**主机**|**TTL**|**文本**|
    |:-----|:-----|:----|
    |@  <br/> |3600  <br/> |MS=ms *XXXXXXXX*  <br/> **注意：** 这是一个示例。 在这里使用表中的特定“**目标地址或指向的地址**”值。           [如何查找此项？](../get-help-with-domains/information-for-dns-records.md)    |
  
    
5. 选择 "**继续**"。
  
  
6. 请等待几分钟，然后再验证新的 TXT 记录，以便您刚刚创建的记录可以通过 Internet 进行更新。
    
在在域注册机构网站添加了记录后，你将返回到 Microsoft 并请求记录。
  
Microsof 找到正确的 TXT 记录表明域已通过验证。
  
1. 在管理中心，转到“**设置**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">域</a>”页面。

    
2. 在“**域**”页面上，选择要验证的域。 
    
    
  
3. 在“**设置**”页面上，选择“**开始设置**”。
    
    
  
4. 在“**验证域**”页面上，选择“**验证**”。
    
    
  
> [!NOTE]
>  DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>添加一条 MX 记录，确保发往你的域的电子邮件将会发送到 Microsoft
<a name="BKMK_add_MX"> </a>

1. 若要开始，请使用[此链接](https://checkout.web.com/manage-it/index.jsp)转到 web.com 上的 "域" 页面。 先登录。
  
2. 在 "**帐户管理器**" 页上，选择 **"我的域名**"。 
  
3. 在 "* * 管理 * 我的域 * * *" 下，选择 "**编辑高级 DNS 记录**"。

4. 在 "**邮件服务器（MX 记录）**" 下，单击 "**编辑 MX 记录**"，然后选择下表中的值。 
    
    |**优先级**|**TTL**|**邮件服务器**|
    |:-----|:-----|:-----|
    |1  <br/> 有关优先级的详细信息，请参阅[什么是 MX 优先级？](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) <br/> |3600  <br/> |*\<域密钥\>*  .mail.protection.outlook.com  <br/> **注意：** 从你的 Microsoft 帐户中获取你* \<的域密钥\> * 。   [如何查找此项？](../get-help-with-domains/information-for-dns-records.md) |
   

5. 选择“保存”****。
  
6. 如果 " **Mx 记录**" 部分中列出了任何其他 MX 记录，请选中 "**删除**" 下的记录旁边的复选框，然后选择 "**保存**"。 
  
7. 在确认屏幕上，选择 "**保存更改**"。 

  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a>添加 Microsoft 所需的六条 CNAME 记录
<a name="BKMK_add_CNAME"> </a>

1. 若要开始，请使用[此链接](https://checkout.web.com/manage-it/index.jsp)转到 web.com 上的 "域" 页面。 系统将会提示您先登录。
     
2. 在 "**帐户管理器**" 页上，选择 **"我的域名**"。 
  
3. 在 "* * 管理 * 我的域 * * *" 下，选择 "**编辑高级 DNS 记录**"。

4. 添加第一条 CNAME 记录（共 6 条）。
    
    在 "**主机别名（CNAME 记录）**" 下，单击 "**编辑 CNAME 记录**"，然后选择下表中的值。
    
    
    |**Alias**|**TTL**|**引用主机名**|**其他主机**|
    |:-----|:-----|:-----|:-----|
    |自动发现  <br/> |3600  <br/> |@ （无）  <br/> |autodiscover.outlook.com  <br/> |
    |sip  <br/> |3600  <br/> |@ （无）  <br/> |sipdir.online.lync.com  <br/> |
    |lyncdiscover  <br/> |3600  <br/> |@ （无）  <br/> | webdir.online.lync.com  <br/> |
    |enterpriseregistration  <br/> |3600  <br/> |@ （无）  <br/> |enterpriseregistration.windows.net  <br/> |
    |enterpriseenrollment  <br/> |3600  <br/> |@ （无）  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> |
    |msoid  <br/> |3600  <br/> |@ （无）  <br/> |clientconfig.microsoftonline-p.net  <br/> |
    
  
5. 选择 "**继续**"。
  
6. 逐一添加其他 5 条 CNAME 记录。

    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>为 SPF 添加 TXT 记录以帮助防止垃圾邮件
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> 一个域所拥有的 SPF 的 TXT 记录不能超过一个。 如果域具有多个 SPF 记录，你将收到电子邮件错误，其中随附发送和垃圾邮件分类问题。 如果你的域已有 SPF 记录，请不要为 Microsoft 创建新记录。 改为将所需的 Microsoft 值添加到当前记录，以便您具有包含两组值的*单个*SPF 记录。 
  
1. 若要开始，请使用[此链接](https://checkout.web.com/manage-it/index.jsp)转到 web.com 上的 "域" 页面。 先登录。
    
  
2. 在 "**帐户管理器**" 页上，选择 **"我的域名**"。 
  
3. 在 "* * 管理 * 我的域 * * *" 下，选择 "**编辑高级 DNS 记录**"。

  
4. 在 "**域名**" 页上的 "**文本（TXT 记录）**" 下，单击 "**编辑 TXT 记录**"，然后选择下表中的值。   
    
    |**主机**|**TTL**|**文本**|
    |:-----|:-----|:-----|
    |@  <br/> |3600  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **注意：** 我们建议您复制并粘贴此条目，以保证正确保留所有空格。   |

 
5. 选择 "**继续**"。

6. 选择“**保存更改**”。
    

  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>添加 Microsoft 所需的两条 SRV 记录
<a name="BKMK_add_SRV"> </a>

> [!IMPORTANT]
> 请记住，web.com 有责任使此功能可用。 如果您看到以下步骤与当前 web.com GUI （图形用户界面）之间的差异，请利用[Web.com 社区](https://community.web.com.com/)。 

1. 若要开始，请使用[此链接](https://checkout.web.com/manage-it/index.jsp)转到 web.com 上的 "域" 页面。 先登录。
      
2. 在 "**帐户管理器**" 页上，选择 **"我的域名**"。 
  
3. 在 "* * 管理 * 我的域 * * *" 下，选择 "**编辑高级 DNS 记录**"。
  
4. 添加两条 SRV 记录中的第一条记录。

    在 "**服务（SRV 记录）**" 下，单击 "**编辑 SRV 记录**"，然后选择下表中的值。 
        
    |**服务**|**协议**|**TTL**|**优先级**|**权重**|**端口**|**目标**|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |_sip |_tls |3600 | 100|1 |443 |sipfed.online.lync.com  |
    |_sipfederationtls |_tcp |3600 |100 |1 |5061 | sipfed.online.lync.com |

  
5. 通过从表的第二行中选择值来添加其他 SRV 记录。 
  
6. 选择 "**继续**"。

7. 选择“**保存更改**”。

    
> [!NOTE]
>  DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。 
  
