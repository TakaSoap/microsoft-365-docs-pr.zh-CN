---
title: 在 Hostgator 处为 Microsoft 创建 DNS 记录
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
ms.assetid: 5f0c840e-4140-4571-88ed-cf235ff142d6
description: 了解如何验证您的域，并在 Hostgator for Microsoft 中为电子邮件、Skype for Business Online 和其他服务设置 DNS 记录。
ms.openlocfilehash: fb510bcdcdefb141535e9a1099e18b63adffd2ab
ms.sourcegitcommit: 5476c2578400894640ae74bfe8e93c3319f685bd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/06/2020
ms.locfileid: "44048995"
---
# <a name="create-dns-records-at-hostgator-for-microsoft"></a>在 Hostgator 处为 Microsoft 创建 DNS 记录

 如果找不到要查找的内容，请**[查看域常见问题解答](../setup/domains-faq.md)**。 
  
如果 Hostgator 是您的 DNS 托管提供商，请按照本文中的步骤验证您的域并为电子邮件、Skype for Business Online 等设置 DNS 记录。
  
> [!IMPORTANT]
> 您必须先执行第一个 procedurebelow，将[您的域指向您的托管帐户](#point-your-domain-to-your-hosting-account)，然后再使用本文中的任何其他过程添加 DNS 记录。 

在 Hostgator 中进行所有这些更改后，您的域将设置为使用 Microsoft 服务。
  

  
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果在添加 DNS 记录后遇到邮件流问题或其他问题，请参阅[查找在添加域或 DNS 记录后遇到的问题并进行修复](../get-help-with-domains/find-and-fix-issues.md)。 
  
## <a name="point-your-domain-to-your-hosting-account"></a>将你的域指向你的托管帐户
<a name="BKMK_PointDomain"> </a>

> [!IMPORTANT]
> 在执行本文中的任何其他过程之前，必须执行此过程。 
  
请按以下步骤将域与托管帐户关联。
  
1. 若要开始，请使用[此链接](https://portal.hostgator.com/)转到 Hostgator 上的 "域管理" 页面。 You'll be prompted to log in.
    
2. 选择左侧的 "**域**"。
  
3. 在 "**管理域**" 页上，选择要更新的域。 
  
4. 在左侧的弹出菜单中，选择 "**名称服务器**"。
  
5. 在您的域的 "**名称服务器**" 页上，在 "**自动将此域指向我的托管帐户**" 下拉列表中，选择与您的域关联的主机帐户。 
  
6. 选择 "**保存名称服务器**"。
    
  
## <a name="add-a-txt-record-for-verification"></a>添加 TXT 记录进行验证
<a name="BKMK_verify"> </a>

> [!IMPORTANT]
> 执行此过程之前，必须首先执行本文第一部分[将域指向托管帐户](#point-your-domain-to-your-hosting-account)中的过程。 
  
在将域用于 Microsoft 之前，必须确保你拥有该域。如果你能够在域注册机构处登录到你的帐户并创建 DNS 记录，便可向 Microsoft 证明你是域所有者。
  
> [!NOTE]
> 此记录仅用于验证您是否拥有自己的域；它不会影响其他任何内容。 如果需要，您可以以后将其删除。 
  
1. 若要开始，请转到您在 Hostgator 上的 cPanel 页面。 系统将会提示您先登录。
    
    (Each hosted account at Hostgator is assigned a unique cPanel address. 您的 cPanel 地址应如下所示https://YourSiteAddress:secure-port-number：。 从 Hostgator 接收的注册电子邮件将指定该地址，并且在**托管**页上也可以使用 cPanel 链接。
    
    > [!IMPORTANT]
    > To have a cPanel associated with your domain, you need a hosting account with Hostgator. 若要开始使用 Microsoft，你可以从 Hostgator 或委派中购买托管帐户，[以指向 Microsoft](change-nameservers-at-hostgator.md)。 
  
2. 在 "**控制面板**" 页上的 "**域**" 区域中，选择 "**高级区域编辑器**"。
    
3. 在 "**高级区域编辑器**" 页上的 "**添加记录**" 区域中，在新记录的框中，键入或复制并粘贴下表中的值。 
    
    （从下拉列表中选择" **类型**"值。） 
    
    |||||
    |:-----|:-----|:-----|:-----|
    |**名称** <br/> |**TTL** <br/> |**类型** <br/> |**TXT 数据** <br/> |
    |使用您的*domain_name*。 （例如，fourthcoffee.com.)。  <br/> **此值必须以句点 (.) 结尾。** <br/> |1  <br/> |TXT  <br/> |MS=ms *XXXXXXXX*  <br/> **注意：** 这是一个示例。 在这里使用表中的特定“**目标地址或指向的地址**”值。 [如何查找此项？](../get-help-with-domains/information-for-dns-records.md)          |
   
4. 选择 "**添加记录**"。
    
5. 请在继续之前等待数分钟，以便您刚刚创建的记录可以通过 Internet 完成更新。
    
在在域注册机构网站添加了记录后，你将返回到 Microsoft 并请求记录。
  
Microsof 找到正确的 TXT 记录表明域已通过验证。
  
1. 在管理中心，转到“**设置**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">域</a>”页面。
    
2. 在“**域**”页面上，选择要验证的域。 
    
3. 在“**设置**”页面上，选择“**开始设置**”。
    
4. 在“**验证域**”页面上，选择“**验证**”。
    
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果在添加 DNS 记录后遇到邮件流问题或其他问题，请参阅[查找在添加域或 DNS 记录后遇到的问题并进行修复](../get-help-with-domains/find-and-fix-issues.md)。 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>添加一条 MX 记录，确保发往你的域的电子邮件将会发送到 Microsoft
<a name="BKMK_add_MX"> </a>

> [!IMPORTANT]
> 执行此过程之前，必须首先执行本文第一部分[将域指向托管帐户](#point-your-domain-to-your-hosting-account)中的过程。 
  
1. To get started, go to your cPanel page at Hostgator. You'll be prompted to log in first.
    
    (Each hosted account at Hostgator is assigned a unique cPanel address. 您的 cPanel 地址应如下所示https://YourSiteAddress:secure-port-number：。 从 Hostgator 接收的注册电子邮件将指定该地址，并且在**托管**页上也可以使用 cPanel 链接。
    
    > [!IMPORTANT]
    > To have a cPanel associated with your domain, you need a hosting account with Hostgator. 若要开始使用 Microsoft，你可以从 Hostgator 或委派中购买托管帐户，[以指向 Microsoft](change-nameservers-at-hostgator.md)。 
  
2. 在 "**控制面板**" 页上的 "**电子邮件**" 区域中，选择 " **MX 条目**"。
    
 
3. 在 "**电子邮件路由**" 区域中，选择 "**远程邮件交换器**"。

4. 选择 "**更改**"。
  
5. 在 "**添加新记录**" 区域中新记录的框内，键入或复制并粘贴下表中的值。 
    
    |**优先级**|**目标**|
    |:-----|:-----|
    |0  <br/> 有关优先级的详细信息，请参阅[什么是 MX 优先级？](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) <br/> | *\<域密钥\>*  .mail.protection.outlook.com  <br/> **注意：** 从你\<的 Microsoft 帐户中获取你的*域密钥*\> 。    [如何查找此项？](../get-help-with-domains/information-for-dns-records.md)          |
  
6. 选择 "**添加新记录**"。
   
 
7. 如果 " **Mx 记录**" 一节中有任何其他 MX 记录，请将其删除。 

    
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a>添加 Microsoft 所需的六条 CNAME 记录
<a name="BKMK_add_CNAME"> </a>

> [!IMPORTANT]
> 执行此过程之前，必须首先执行本文第一部分[将域指向托管帐户](#point-your-domain-to-your-hosting-account)中的过程。 
  
1. To get started, go to your cPanel page at Hostgator. You'll be prompted to log in first.
    
    (Each hosted account at Hostgator is assigned a unique cPanel address. 您的 cPanel 地址应如下所示https://YourSiteAddress:secure-port-number：。 从 Hostgator 接收的注册电子邮件将指定该地址，并且在**托管**页上也可以使用 cPanel 链接。
    
    > [!IMPORTANT]
    > To have a cPanel associated with your domain, you need a hosting account with Hostgator. 若要开始使用 Microsoft，你可以从 Hostgator 或委派中购买托管帐户，[以指向 Microsoft](change-nameservers-at-hostgator.md)。 
  
2. 在 "**控制面板**" 页上的 "**域**" 区域中，选择 "**高级区域编辑器**"。
    
3. 添加第一条 CNAME 记录（共 6 条）。
    
    在 "**高级区域编辑器**" 页上的 "**添加记录**" 区域中，在新记录的框中，键入或复制并粘贴下表中第一行的值。 
    
    （从下拉列表中选择" **类型**"值。） 
    
    |**名称**|**TTL**|**类型**|**CNAME**|
    |:-----|:-----|:-----|:-----|
    |autodiscover. *domain_name*。 （例如，autodiscover.fourthcoffee.com。）  <br/> **This value MUST end with a period (.)** <br/> |3600  <br/> |CNAME  <br/> |autodiscover.outlook.com  <br/> |
    |sip. *domain_name*。 （例如，sip.fourthcoffee.com。）  <br/> **This value MUST end with a period (.)** <br/> |3600  <br/> |CNAME  <br/> |sipdir.online.lync.com  <br/> |
    |lyncdiscover. *domain_name*。 （例如，lyncdiscover.fourthcoffee.com。）  <br/> **This value MUST end with a period (.)** <br/> |3600  <br/> |CNAME  <br/> |webdir.online.lync.com  <br/> |
    |enterpriseregistration. *domain_name*。 （例如，enterpriseregistration.fourthcoffee.com。）  <br/> **This value MUST end with a period (.)** <br/> |3600  <br/> |CNAME  <br/> |EnterpriseRegistration.windows.net  <br/> |
    |enterpriseenrollment. *domain_name*。 （例如，enterpriseregistration.fourthcoffee.com。）  <br/> **This value MUST end with a period (.)** <br/> |3600  <br/> |CNAME  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> |

  
4. 选择 "**添加记录**"。

5. 逐一添加其他 5 条 CNAME 记录。
    
    在 "**添加记录**" 部分，使用表中下一行的值创建记录，然后再次选择 "**添加记录**" 以完成该记录。 
    
    重复该过程，直到创建完全部 6 条 CNAME 记录。
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>为 SPF 添加 TXT 记录以帮助防止垃圾邮件
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> 一个域所拥有的 SPF 的 TXT 记录不能超过一个。 如果域具有多个 SPF 记录，你将收到电子邮件错误，其中随附发送和垃圾邮件分类问题。 如果你的域已有 SPF 记录，请不要为 Microsoft 创建新记录。 可以将所需的 Microsoft 值添加到当前记录，这样就拥有包含两组值的单个 SPF 记录。 需要示例吗？ 请查看 [Microsoft 的外部域名系统记录](https://docs.microsoft.com/office365/enterprise/external-domain-name-system-records#bkmk_spfrecords)。 若要验证 SPF 记录，可使用以下任一 [SPF 验证工具](../setup/domains-faq.md)。 
  
> [!IMPORTANT]
> 执行此过程之前，必须首先执行本文第一部分[将域指向托管帐户](#point-your-domain-to-your-hosting-account)中的过程。 
  
1. To get started, go to your cPanel page at Hostgator. You'll be prompted to log in first.
    
    (Each hosted account at Hostgator is assigned a unique cPanel address. 您的 cPanel 地址应如下所示https://YourSiteAddress:secure-port-number：。 从 Hostgator 接收的注册电子邮件将指定该地址，并且在**托管**页上也可以使用 cPanel 链接。
    
    > [!IMPORTANT]
    > To have a cPanel associated with your domain, you need a hosting account with Hostgator. 若要开始使用 Microsoft，你可以从 Hostgator 或委派中购买托管帐户，[以指向 Microsoft](change-nameservers-at-hostgator.md)。 
  
2. 在 "**控制面板**" 页上的 "**域**" 区域中，选择 "**高级区域编辑器**"。
    
3. On the **Advanced DNS Zone Editor** page, in the **Add a Record** area, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    （从下拉列表中选择" **类型**"值。） 
    
    |**名称**|**TTL**|**类型**|**TXT 数据**|
    |:-----|:-----|:-----|:-----|
    |使用您的*domain_name*。 （例如，fourthcoffee.com.)。  <br/> **此值必须以句点 (.) 结尾。** <br/> |3600  <br/> |TXT  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **注意：** 我们建议您复制并粘贴此条目，以保证正确保留所有空格。           |
  
4. 选择 "**添加记录**"。
    
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>添加 Microsoft 所需的两条 SRV 记录
<a name="BKMK_add_SRV"> </a>

> [!IMPORTANT]
> 执行此过程之前，必须首先执行本文第一部分[将域指向托管帐户](#point-your-domain-to-your-hosting-account)中的过程。 
  
1. To get started, go to your cPanel page at Hostgator. You'll be prompted to log in first.
    
    (Each hosted account at Hostgator is assigned a unique cPanel address. 您的 cPanel 地址应如下所示https://YourSiteAddress:secure-port-number：。 从 Hostgator 接收的注册电子邮件将指定该地址，并且在**托管**页上也可以使用 cPanel 链接。
    
    > [!IMPORTANT]
    > To have a cPanel associated with your domain, you need a hosting account with Hostgator. 若要开始使用 Microsoft，你可以从 Hostgator 或委派中购买托管帐户，[以指向 Microsoft](change-nameservers-at-hostgator.md)。 
  
2. 在 "**控制面板**" 页上的 "**域**" 区域中，选择 "**高级区域编辑器**"。

    
3. 添加两条 SRV 记录中的第一条记录。
    
    在 "**高级 DNS 区域编辑器**" 页上的 "**添加记录**" 区域中，在新记录的框中，键入或复制并粘贴下表中第一行的值。 
    
    （从下拉列表中选择" **类型**"值。） 
    
    |**名称**|**TTL**|**类型**|**优先级**|**权重**|**端口**|**目标**|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |_sip _tls。 *domain_name*。 （例如 _sip，_tls fourthcoffee）  <br/> **此值必须以句点 (.) 结尾。** <br/> |3600  <br/> |SRV  <br/> |100  <br/> |1  <br/> |443  <br/> |sipdir.online.lync.com  <br/> |
    |_sipfederationtls _tcp。 *domain_name*。 （例如 _sipfederationtls，_tcp fourthcoffee）  <br/> **此值必须以句点 (.) 结尾。** <br/> |3600  <br/> |SRV  <br/> |100  <br/> |1  <br/> |5061  <br/> |sipfed.online.lync.com  <br/> |
   

4. 选择 "**添加记录**"。

  
5. 添加另一条 SRV 记录。
    
    在 "**添加记录**" 部分，使用表中下一行的值创建记录，然后再次选择 "**添加记录**" 以完成该记录。 
    
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果在添加 DNS 记录后遇到邮件流问题或其他问题，请参阅[查找在添加域或 DNS 记录后遇到的问题并进行修复](../get-help-with-domains/find-and-fix-issues.md)。 
