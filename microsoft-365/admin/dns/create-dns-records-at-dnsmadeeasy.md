---
title: 在 DNSMadeEasy 上为 Office 365 创建 DNS 记录
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
ms.assetid: e158b079-b054-4b7e-8e01-e55169ce18d7
description: 了解如何在 DNSMadeEasy for Office 365 中验证您的域并为电子邮件、Skype for Business Online 和其他服务设置 DNS 记录。
ms.openlocfilehash: 7b94b8d4b3a02a0f436ba2af314eece8b7606ec2
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/24/2020
ms.locfileid: "42240721"
---
# <a name="create-dns-records-at-dnsmadeeasy-for-office-365"></a>在 DNSMadeEasy 上为 Office 365 创建 DNS 记录

 如果找不到要查找的内容，请**[查看域常见问题解答](../setup/domains-faq.md)**。 
  
如果 DNSMadeEasy 是您的 DNS 托管提供商，请按照本文中的步骤验证您的域并为电子邮件、Skype for Business Online 等设置 DNS 记录。
  
在 DNSMadeEasy 中添加这些记录后，您的域将设置为与 Office 365 服务配合使用。
  
若要了解如何与 Office 365 结合使用网站的 Web 宿主和 DNS，请参阅[配合使用公共网站与 Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9)。
  
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅[在 Office 365 中添加域或 DNS 记录后，查找并修复问题](../get-help-with-domains/find-and-fix-issues.md)。 
  
## <a name="add-a-txt-record-for-verification"></a>添加 TXT 记录进行验证
<a name="BKMK_verify"> </a>

在将域用于 Office 365 之前，必须确保你拥有该域。如果你能够在域注册机构处登录到你的帐户并创建 DNS 记录，便可向 Office 365 证明你是所有者。
  
> [!NOTE]
> 此记录仅用于验证您是否拥有自己的域；它不会影响其他任何内容。 如果需要，您可以以后将其删除。 
  
> [!IMPORTANT]
> 对于 DNSMadeEasy 帐户，添加的域是从单独的域注册机构购买的。 DNSMadeEasy 不提供域注册服务。 您在 DNSMadeEasy 登录并创建 DNS 记录的能力是足够的所有权证明。 
  
1. 要开始，请使用[此链接](https://cp.dnsmadeeasy.com/)转到您在 DNSMadeEasy 上的域页面。 系统将会提示您首先登录。
    
2. 在 "**管理控制台**" 页上的 "**最近更新的域**" 区域中，选择要更新的域。 
    
3. 在 "**托管 DNS** " 页面上的 " **TXT 记录**" 区域中， **+** 选择 "（"）控件（**添加新**控件）。
    
    (You may have to scroll down.)
    
4. In the **Add TXT Records** area, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    ||||
    |:-----|:-----|:-----|
    |**Name** <br/> |**值** <br/> |**TTL** <br/> |
    |（将此字段留空。）  <br/> |MS=ms *XXXXXXXX*  <br/> **注意：** 这是一个示例。 在这里使用来自 Office 365 中的表的特定" **目标或指向的地址**"值。 [如何查找此内容？](../get-help-with-domains/information-for-dns-records.md)          |1800  <br/> |
   
5. 选择 "**提交**"。
    
6. 请在继续之前等待数分钟，以便您刚刚创建的记录可以通过 Internet 完成更新。
    
Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.
  
When Office 365 finds the correct TXT record, your domain is verified.
  
1. 在管理中心中，转到 "**设置** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">域</a>" 页。

    
2. 在 "**域**" 页上，选择要验证的域。 
    
3. 在 "**设置**" 页上，选择 "**启动安装程序**"。
    
4. 在 "**验证域**" 页上，选择 "**验证**"。
    
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅[在 Office 365 中添加域或 DNS 记录后，查找并修复问题](../get-help-with-domains/find-and-fix-issues.md)。 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a>添加一条 MX 记录，确保发往您的域的电子邮件发送到 Office 365
<a name="BKMK_add_MX"> </a>

1. 要开始，请使用[此链接](https://cp.dnsmadeeasy.com/)转到您在 DNSMadeEasy 上的域页面。 系统将会提示您首先登录。
    
2. 在 "**管理控制台**" 页上的 "**最近更新的域**" 区域中，选择要更新的域。 
    
    在 "**管理控制台**" 页上的 "**最近更新的域**" 区域中，选择要更新的域。 
    
    ![DNSMadeEasy-配置-1-2](../media/8d8f403e-d7cd-429e-913b-dacb1f4644a2.png)
  
3. 在 "**托管 DNS** " 页面上的 " **MX 记录**" 区域中，选择 " **（+）** " 控件（**添加新**控件）。
    
    (You may have to scroll down.)
    
    ![DNSMadeEasy-配置-2-1](../media/404c73bf-1db4-4d68-82d8-68303f418ed4.png)
  
4. 在 "**添加 MX 记录**" 区域中新记录的框内，键入或复制并粘贴下表中的值。 
    
    (You may have to scroll down.)
    
    |**名称**|**服务器**|**MX 级别**|**TTL**|
    |:-----|:-----|:-----|:-----|
    |（将此字段留空。）  <br/> | *\<域密钥\>*  .mail.protection.outlook.com  <br/> **This value MUST end with a period (.)** <br/> **注意：** 从 Office \<365 帐户中获取你的*域密钥*\> 。 如何查找此内容？[](../get-help-with-domains/information-for-dns-records.md)          |10   <br/> 有关优先级的详细信息，请参阅[什么是 MX 优先级？](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx) <br/> |1800  <br/> |
   
    ![DNSMadeEasy-配置-2-2](../media/69b53af9-1eec-435c-8434-1b6058c1ec82.png)
  
5. 选择 "**提交**"。
    
    ![DNSMadeEasy-配置-2-3](../media/381054a6-bb85-4ebb-b576-42cbba78ed1b.png)
  
6. 如果 " **Mx 记录**" 一节中列出了任何其他 MX 记录，请通过选择每条记录将其删除。 
    
    ![DNSMadeEasy-配置-2-4-1](../media/58a07769-0b30-4111-b555-bfc3b82a7d4c.png)
  
7. 选择所有记录后，选择 "**删除所选**"。
    
    ![DNSMadeEasy-配置-2-4-2](../media/e9064c07-1ce7-4387-b47a-90d4193da374.png)
  
8. 在 "**删除 MX 记录**" 对话框中，选择 "**删除**" 以确认更改。 
    
    ![DNSMadeEasy-配置-2-5](../media/03c405e5-868f-468f-b6d2-046d27b201fb.png)
  
## <a name="add-the-five-cname-records-that-are-required-for-office-365"></a>添加 Office 365 所需的五个 CNAME 记录
<a name="BKMK_add_CNAME"> </a>

1. 要开始，请使用[此链接](https://cp.dnsmadeeasy.com/)转到您在 DNSMadeEasy 上的域页面。 系统将会提示您首先登录。
    
2. 在 "**管理控制台**" 页上的 "**最近更新的域**" 区域中，选择要更新的域。 
    
3. 在 "**托管 DNS** " 页面上的 " **CNAME 记录**" 区域中，选择 " **（+）** " 控件（**添加新**控件）。
    
    (You may have to scroll down.)
    
    ![DNSMadeEasy-配置-3-1](../media/a5feb238-690d-4b64-a625-91a82b3f4068.png)
  
4. 添加五个 CNAME 记录中的第一个。
    
    在 "**添加 CNAME 记录**" 区域中新记录的框内，键入或复制并粘贴下表中第一行的值。 
    
    |**名称**|**别名**|**TTL**|
    |:-----|:-----|:-----|
    |autodiscover  <br/> |autodiscover.outlook.com。  <br/> **This value MUST end with a period (.)** <br/> |1800  <br/> |
    |sip  <br/> |sipdir.online.lync.com。  <br/> **This value MUST end with a period (.)** <br/> |1800  <br/> |
    |lyncdiscover  <br/> |webdir.online.lync.com。  <br/> **This value MUST end with a period (.)** <br/> |1800  <br/> |
    |enterpriseregistration  <br/> |enterpriseregistration.windows.net。  <br/> **This value MUST end with a period (.)** <br/> |1800  <br/> |
    |enterpriseenrollment  <br/> |enterpriseenrollment-s.manage.microsoft.com。  <br/> **此值必须以句点 (.) 结尾。** <br/> |1800  <br/> |
   
    ![DNSMadeEasy-配置-3-2](../media/de6dddcd-bf0a-4993-ab4c-a6d10167bf34.png)
  
5. 选择 "**提交**"。
    
    ![DNSMadeEasy-配置-3-3](../media/e44ef73e-99cb-41ce-a3f2-549cb2f29eef.png)
  
6. 添加其他四条 CNAME 记录中的每一个。
    
    在 " **CNAME 记录**" 部分中，选择 " **（** **添加新**控件）"，使用表中下一行的值创建记录，然后再次选择 "**提交**" 以完成该记录。 
    
    重复此过程，直到创建完所有五个 CNAME 记录。
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>为 SPF 添加 TXT 记录以帮助防止垃圾邮件
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> You cannot have more than one TXT record for SPF for a domain. If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues. If you already have an SPF record for your domain, don't create a new one for Office 365. 改为将所需的 Office 365 值添加到当前记录，以便您具有包含两组值的*单个*SPF 记录。 Need examples? 查看[Office 365 的这些外部域名系统记录](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0)。 若要验证您的 SPF 记录，您可以使用其中一种[SPF 验证工具](../setup/domains-faq.md)。 
  
1. 要开始，请使用[此链接](https://cp.dnsmadeeasy.com/)转到您在 DNSMadeEasy 上的域页面。 系统将会提示您首先登录。
    
2. 在 "**管理控制台**" 页上的 "**最近更新的域**" 区域中，选择要更新的域。 
    
3. 在 "**托管 DNS** " 页面上的 " **TXT 记录**" 区域中，选择 " **（+）** " 控件（**添加新**控件）。
    
    (You may have to scroll down.)
    
    ![DNSMadeEasy-配置-4-1](../media/657b87a5-dcb4-4ae7-8f27-bd857f0f4189.png)
  
4. In the **Add TXT Records** area, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    |**名称**|**值**|**TTL**|
    |:-----|:-----|:-----|
    |（将此字段留空。）  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **注意：** 我们建议您复制并粘贴此条目，以确保所有的间距保持正确。           |1800  <br/> |
   
    ![DNSMadeEasy-配置-4-2](../media/b317bcb9-18c6-4609-a8f4-963823032669.png)
  
5. 选择 "**提交**"。
    
    ![DNSMadeEasy-配置-4-3](../media/8a1c53c3-1222-4127-a190-70f6f5059433.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a>添加 Office 365 所需的两条 SRV 记录
<a name="BKMK_add_SRV"> </a>

1. 要开始，请使用[此链接](https://cp.dnsmadeeasy.com/)转到您在 DNSMadeEasy 上的域页面。 系统将会提示您首先登录。
    
2. 在 "**管理控制台**" 页上的 "**最近更新的域**" 区域中，选择要更新的域。 
    
3. 在 "**托管 DNS** " 页面上的 " **SRV 记录**" 区域中，选择 " **（+）** " 控件（**添加新**控件）。
    
    （您可能需要向下滚动）
    
    ![DNSMadeEasy-配置-5-1](../media/5c9e8f50-adbd-4f23-8ce3-2844b2896f3f.png)
  
4. 添加两条 SRV 记录中的第一条记录。
    
    在 "**添加 SRV 记录**" 区域中新记录的框内，键入或复制并粘贴下表中第一行的值。 
    
    |**名称**|**优先级**|**权重**|**端口**|**主机**|**TTL**|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |_sip _tls  <br/> |100  <br/> |1  <br/> |443  <br/> |sipdir.online.lync.com。  <br/> **This value MUST end with a period (.)** <br/> |1800  <br/> |
    |_sipfederationtls _tcp  <br/> |100  <br/> |1  <br/> |5061  <br/> |sipfed.online.lync.com。  <br/> **此值必须以句点 (.) 结尾。** <br/> |1800  <br/> |
   
    ![DNSMadeEasy-配置-5-2](../media/e1155f94-575f-441a-9a61-d948391d42ca.png)
  
5. 选择 "**提交**"。
    
    ![DNSMadeEasy-配置-5-3](../media/7eae54e1-08bd-4902-afdf-fd5cc251ab59.png)
  
6. 添加另一条 SRV 记录。
    
    在 " **SRV 记录**" 部分中，选择 " **（** **添加新**控件）"，使用表中下一行的值创建记录，然后再次选择 "**提交**" 以完成该记录。 
    
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅[在 Office 365 中添加域或 DNS 记录后，查找并修复问题](../get-help-with-domains/find-and-fix-issues.md)。 
  

