---
title: 更改名称服务器以使用任意域名注册机构设置 Office 365
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
- Adm_TOC
- Adm_O365_Setup
search.appverid:
- BCS160
- MET150
- MOE150
- GEU150
- GEA150
ms.assetid: a8b487a9-2a45-4581-9dc4-5d28a47010a2
description: 了解如何在 Office 365 中添加和设置域，以便您的服务（如电子邮件和 Skype for Business Online）使用您自己的域名。
ms.custom: okr_smb
ms.openlocfilehash: 3030fc33a6d528fd6cb4e97c27cdbb7c251e9a97
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/24/2020
ms.locfileid: "42251158"
---
# <a name="change-nameservers-to-set-up-office-365-with-any-domain-registrar"></a>更改名称服务器以使用任意域名注册机构设置 Office 365

 如果找不到要查找的内容，请**[查看域常见问题解答](../setup/domains-faq.md)**。 
  
先检查 "[设置域（特定于主机的说明）](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md) "，然后查看是否有关于注册器的说明。 
  
请按照以下说明在 Office 365 中添加和设置你的域，以便你的服务（如电子邮件和 Skype for Business Online）将使用你自己的域名。 为此，你需要验证你的域，然后将你的域的名称服务器更改为 Office 365，以便为你设置正确的 DNS 记录。 如果以下语句描述了您的情况，请按照以下步骤操作：
  
- 您拥有自己的域，并且想要将其设置为使用 Office 365。
    
- 希望 Office 365 代为管理 DNS 记录。（如果愿意，可[管理自己的 DNS 记录](../setup/add-domain.md)。）
    
## <a name="add-a-txt-or-mx-record-for-verification"></a>添加 TXT 记录或 MX 记录进行验证
<a name="BKMK_verify"> </a>

> [!NOTE]
> 您必须仅创建这些记录中的其中一项。TXT 是首选记录类型，但某些 DNS 托管提供商不支持它，在这种情况下，您可以创建 MX 记录。 
  
在将域用于 Office 365 之前，必须确保你拥有该域。如果你能够在域注册机构处登录到你的帐户并创建 DNS 记录，便可向 Office 365 证明你是所有者。
  
> [!NOTE]
> 此记录仅用于验证您是否拥有自己的域；它不会影响其他任何内容。 如果需要，您可以以后将其删除。 
  
### <a name="find-the-area-on-your-dns-hosting-providers-website-where-you-can-create-a-new-record"></a>在您的 DNS 托管提供商网站上查找可以在其中创建新记录的区域

1. 登录到您的 DNS 托管提供商的网站。
    
2. 选择你的域。
    
3. 查找您可以在其中编辑您的域的 DNS 记录的页面。
    
### <a name="create-the-record"></a>创建记录

根据是要创建 TXT 记录还是 MX 记录，请执行下列操作之一：
  
**如果要创建 TXT 记录，请使用这些值：**
    
|||||
|:-----|:-----|:-----|:-----|
|**记录类型** <br/> |**别名** 或 **主机名称** <br/> |**值** <br/> |**TTL** <br/> |
|TXT  <br/> |执行下列操作之一：键入 **@** ，将该字段留空或键入你的域名。  <br/> > [!NOTE]> 此字段对不同的 DNS 主机有不同的要求。           
|MS=ms *XXXXXXXX*  <br/> > [!NOTE]> 这是一个示例。 在这里使用来自 Office 365 中的表的特定" **目标或指向的地址**"值。          [如何查找此内容？](../get-help-with-domains/information-for-dns-records.md)          |将此值设置为 **1 小时** 或等效的分钟数 ( **60** )、秒数 ( **3600** )，等等。  <br/> |
   
**如果您创建 MX 记录，请使用这些值：**
    
||||||
|:-----|:-----|:-----|:-----|:-----|
|**记录类型**|**别名** 或 **主机名称**|**值**|**优先级**|**TTL**|
|MX|键入" **@** "或你的域名。 |MS=ms *XXXXXXXX* > [!NOTE]> 这是一个示例。 在这里使用来自 Office 365 中的表的特定" **目标或指向的地址**"值。          [如何查找此内容？](../get-help-with-domains/information-for-dns-records.md)          |为了**避免**与用于邮件流的 MX 记录发生冲突，请使用比任何现有 MX 记录的优先级更低的优先级。 有关优先级的详细信息，请参阅[什么是 MX 优先级？](../setup/domains-faq.md#what-is-mx-priority) |将此值设置为 **1 小时** 或等效的分钟数 ( **60** )、秒数 ( **3600** )，等等。 |
   
### <a name="save-the-record"></a>保存记录

Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.
  
When Office 365 finds the correct TXT record, your domain is verified.
  

1. 在管理中心中，转到 "**设置** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">域</a>" 页。
    
2. 在 "**域**" 页上，选择要验证的域。 
    
  
3. 在 "**设置**" 页上，选择 "**启动安装程序**"。
 
    
  
4. 在 "**验证域**" 页上，选择 "**验证**"。
    
    
  
> [!NOTE]
>  DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。 
  
## <a name="change-your-domains-nameserver-ns-records"></a>更改域的名称服务器 (NS) 记录
<a name="BKMK_nameservers"> </a>

当您进入到 Office 365 中的域设置向导的最后一步时，便只剩下一项任务未完成。要使用 Office 365 服务（如电子邮件）设置您的域，请在域注册机构中将您的域的名称服务器 (NS) 记录更改为指向 Office 365 主要名称服务器和次要名称服务器。然后，由于 Office 365 托管您的 DNS，将自动为您设置服务所需的 DNS 记录。 通过按照您的域注册机构在其网站的帮助内容中所提供步骤进行操作，您可以自己更新名称服务器记录。如果不熟悉 DNS，请联系域注册机构的支持人员。

::: moniker range="o365-worldwide"
  
若要在域注册机构的网站上更改您的域的名称服务器，请执行以下步骤：
  
1. 在域注册机构的网站上查找您可以在其中编辑您的域的名称服务器的区域。
    
2. 创建两个名称服务器记录，或编辑现有名称服务器记录匹配以下值：
    
|||
|:-----|:-----|
|首选名称服务器  <br/> |ns1.bdm.microsoftonline.com  <br/> |
|次要名称服务器  <br/> |ns2.bdm.microsoftonline.com  <br/> |
   
   > [!TIP]
   > 应至少使用两个 nameserver 记录。 如果列出了任何其他名称服务器，则可以将其删除，也可以将其更改为**ns3.bdm.microsoftonline.com**和**ns4.bdm.microsoftonline.com**。 
  
3. 保存所做的更改。
    
> [!CAUTION]
> 将您的域的 NS 记录更改为指向 Office 365 名称服务器时，当前与您的域相关联的所有服务都会受影响。如果您跳过了向导中的任何步骤，或是将域用于博客、购物车或其他服务，则需要执行一些附加步骤。否则此更改可能会导致服务停机时间，例如导致电子邮件访问丢失或您的当前网站不可访问。 

::: moniker-end

::: moniker range="o365-21vianet"
  
1. 在域注册机构的网站上查找您可以在其中编辑您的域的名称服务器的区域。
    
2. 创建两个名称服务器记录，或编辑现有名称服务器记录匹配以下值：
    
|||
|:-----|:-----|
|首选名称服务器  <br/> |ns1.dns.partner.microsoftonline.cn  <br/> |
|次要名称服务器  <br/> |ns2.dns.partner.microsoftonline.cn  <br/> |
   
   > [!TIP]
   > 应至少使用两个 nameserver 记录。 如果列出了任何其他名称服务器，则可以将其删除，也可以将其更改为**ns3.dns.partner.microsoftonline.cn**和**ns4.dns.partner.microsoftonline.cn**。 
  
3. 保存所做的更改。
    
> [!CAUTION]
> 当您将您的域的 NS 记录更改为指向由世纪互联运营的 Office 365 时名称服务器，当前与您的域相关联的所有服务都将受到影响。 如果您跳过了向导中的任何步骤，或是将域用于博客、购物车或其他服务，则需要执行一些附加步骤。 否则此更改可能会导致服务停机时间，例如导致电子邮件访问丢失或您的当前网站不可访问。 

::: moniker-end
  
例如，以下是电子邮件和网站托管可能需要的一些附加步骤：
  
- 将使用您的域的所有电子邮件地址移动到 Office 365，然后再更改您的 NS 记录。
    
- 希望添加当前用于网站地址的域，如 www.fourthcoffee.com？ 你可以在以下步骤中添加域，以在网站托管的位置保持网站托管，以便用户在将域的 NS 记录更改为指向 Office 365 后仍可访问网站。

1. 在管理中心中，转到 "**设置** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">域</a>" 页。

3. 在" 域"页面上选择域。

4. 在 " **DNS 设置**" 下，选择 "**自定义记录**"，然后选择 "**新建自定义记录**"。

5. 选择要添加的 DNS 记录的类型，然后键入新记录的信息。

6. 选择“**保存**”。
    
> [!NOTE]
> 你的名称服务器记录更新可能需要多达数小时才能在 Internet 的 DNS 系统中更新。然后，你的 Office 365 电子邮件和其他服务将全部设置为使用你的域。 
  

