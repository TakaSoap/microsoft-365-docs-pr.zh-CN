---
title: 在适用于 Office 365 的古怪域中创建 DNS 记录
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
ms.assetid: 6386d63e-b78f-4736-90e7-b99a2c116a9f
description: 了解如何验证您的域并为 Office 365 的电子邮件、Skype for Business Online 和古怪域中的其他服务设置 DNS 记录。
ms.openlocfilehash: 157c33a52403efbefe673bf11465de525ffb4f33
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/02/2020
ms.locfileid: "42351153"
---
# <a name="create-dns-records-at-crazy-domains-for-office-365"></a>在适用于 Office 365 的古怪域中创建 DNS 记录

 如果找不到要查找的内容，请**[查看域常见问题解答](../setup/domains-faq.md)**。 
  
如果古怪域是 DNS 托管提供商，请按照本文中的步骤验证您的域，并为电子邮件、Skype for Business Online 等设置 DNS 记录。
  
在古怪域中添加这些记录后，您的域将设置为与 Office 365 服务配合使用。
  
若要了解如何与 Office 365 结合使用网站的 Web 宿主和 DNS，请参阅[配合使用公共网站与 Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9)。
  
> [!NOTE]
> DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。 
  
## <a name="add-a-txt-record-for-verification"></a>添加 TXT 记录进行验证
<a name="BKMK_verify"> </a>

在将域用于 Office 365 之前，必须确保你拥有该域。如果你能够在域注册机构处登录到你的帐户并创建 DNS 记录，便可向 Office 365 证明你是所有者。
  
> [!NOTE]
> 此记录仅用于验证您是否拥有自己的域；它不会影响其他任何内容。 如果需要，您可以以后将其删除。 
  
1. 要开始，请使用[此链接](https://manage.crazydomains.com/members/domains/)转到你在 Crazy Domains 上的域页面。系统将会提示你首先登录。
    
    ![CrazyDomains-配置-1-1](../../media/40c5117c-acad-4fe5-bf0d-d3c362b08a16.png)
  
2. 在 "**我的帐户**" 部分，选择 "**域**"。
    
    ![CrazyDomains-配置-1-2](../../media/778576c3-560e-4ffb-b3b4-bd92fc6a6bd4.png)
  
3. 在 "**域名**" 页上的 "**域**" 部分，选择要更新的域的名称。 
    
    ![CrazyDomains-配置-1-3](../../media/4dd7bb74-c8ed-4b4a-b4c1-d9538fc6bd9a.png)
  
4. 在 " **DNS 设置**" 部分中，选择下拉列表图标。 
    
    ![CrazyDomains-配置-1-4-1](../../media/c7573fbf-467d-49c1-abb6-8c7b9b4af83d.png)
  
5. 选择 "**添加记录**"。
    
    ![CrazyDomains-配置-1-4-2](../../media/7bef31f5-f180-4b61-a462-9326789e770f.png)
  
6. 从" **添加记录**"下拉列表中选择" **TXT 记录**"。 
    
    ![CrazyDomains-验证-1-1](../../media/f0ffdefb-d7a5-47df-bb5e-bf8a3bcc9b01.png)
  
7. 选择“**添加**”。
    
    ![CrazyDomains-验证-1-2](../../media/b0cd623a-67f7-4bae-a5b5-507f5a106123.png)
  
8. 在新记录的框中，键入或复制粘贴下表中的值。
    
    |**子域**|**文本记录**|
    |:-----|:-----|
    |（将此字段留空。）  <br/> |MS=ms *XXXXXXXX*  <br/> **注意：** 此为示例。 在这里使用来自 Office 365 中的表的具体**目标地址或指向的地址**值。           [如何查找此项？](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![CrazyDomains-验证-1-3](../../media/3867de97-6a98-4475-9bda-470bac75d483.png)
  
9. 选择“更新”****。
    
    ![CrazyDomains-验证-1-4](../../media/0e416df6-b7a2-4dd7-971c-f1cc31df30da.png)
  
10. 请在继续之前等待数分钟，以便您刚刚创建的记录可以通过 Internet 完成更新。
    
现在你已在域注册机构网站添加了记录，然后将返回到 Office 365 并请求 Office 365 查找记录。
  
Office 365 找到正确的 TXT 记录时，表明你的域已通过验证。
  
1. 在管理中心，转到“**设置**”\> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">域</a>页面。

    
2. 在“**域**”页面上，选择要验证的域。 
    
    
  
3. 在“**设置**”页面上，选择“**开始设置**”。
    
    
  
4. 在“**验证域**”页面上，选择“**验证**”。
    
    
  
> [!NOTE]
>  DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a>添加一条 MX 记录，确保发往你的域的电子邮件发送到 Office 365
<a name="BKMK_add_MX"> </a>

1. 要开始，请使用[此链接](https://manage.crazydomains.com/members/domains/)转到你在 Crazy Domains 上的域页面。系统将会提示你首先登录。
    
    ![CrazyDomains-配置-1-1](../../media/40c5117c-acad-4fe5-bf0d-d3c362b08a16.png)
  
2. 在 "**我的帐户**" 部分，选择 "**域**"。
    
    ![CrazyDomains-配置-1-2](../../media/778576c3-560e-4ffb-b3b4-bd92fc6a6bd4.png)
  
3. 在 "**域名**" 页上的 "**域**" 部分，选择要更新的域的名称。 
    
    ![CrazyDomains-配置-1-3](../../media/4dd7bb74-c8ed-4b4a-b4c1-d9538fc6bd9a.png)
  
4. 在 " **DNS 设置**" 部分中，选择下拉列表图标。 
    
    ![CrazyDomains-配置-1-4-1](../../media/c7573fbf-467d-49c1-abb6-8c7b9b4af83d.png)
  
5. 选择 "**添加记录**"。
    
    ![CrazyDomains-配置-1-4-2](../../media/7bef31f5-f180-4b61-a462-9326789e770f.png)
  
6. 从 "**添加记录：** " 下拉列表中选择 " **MX 记录**"。 
    
    ![CrazyDomains-配置-2-1](../../media/63f7ab77-e686-4e7b-a3a2-1ac28a02d5f3.png)
  
7. 选择“**添加**”。
    
    ![CrazyDomains-配置-2-2](../../media/a60680a1-2513-498c-b42f-8ffa575ee48e.png)
  
8. 在新记录的框中，键入或复制并粘贴下表中的值。
    
    （从下拉列表中选择 "**优先级**" 值。） 
    
    |**区域邮件**|**优先级**|**分配给服务器**|
    |:-----|:-----|:-----|
    |(Leave this field empty.)  <br/> |1  <br/> 有关优先级的详细信息，请参阅[什么是 MX 优先级？](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx) <br/> | *\<域密钥\>*  .mail.protection.outlook.com  <br/> **注意：** 从 Office 365 帐户中获取你* \<的域密钥\> * 。           [如何查找此项？](../get-help-with-domains/information-for-dns-records.md)          |
       
   ![CrazyDomains-配置-2-3](../../media/e27df6a6-19a6-4e58-9716-a74be1c3f8da.png)
  
9. 选择“更新”****。
    
    ![CrazyDomains-配置-2-4](../../media/ba25cdef-a436-48bf-b0e9-5dffd03234a4.png)
  
10. 如果 " **Mx 记录**" 部分中列出了任何其他 MX 记录，请为其中一个记录选择 "**修改**"。 
    
    ![CrazyDomains-配置-2-5](../../media/9acdda39-33ec-4b24-ad83-91c26f9c599b.png)
  
11. 选择 "**删除**"。
    
    ![CrazyDomains-配置-2-6](../../media/50b0e263-6f21-41b3-8fa0-7dd55dbe6c2e.png)
  
12. 选择 "**更新**" 以确认删除。 
    
    ![CrazyDomains-配置-2-7](../../media/db751bfe-31c2-4632-a491-6893eda38a51.png)
  
13. 使用相同的过程删除列表中的任何其他 MX 记录，只有在此过程之前添加的任何 MX 记录保持不变。
    
## <a name="add-the-six-cname-records-that-are-required-for-office-365"></a>添加 Office 365 所需的 6 条 CNAME 记录
<a name="BKMK_add_CNAME"> </a>

1. 要开始，请使用[此链接](https://manage.crazydomains.com/members/domains/)转到你在 Crazy Domains 上的域页面。系统将会提示你首先登录。
    
    ![CrazyDomains-配置-1-1](../../media/40c5117c-acad-4fe5-bf0d-d3c362b08a16.png)
  
2. 在 "**我的帐户**" 部分，选择 "**域**"。
    
    ![CrazyDomains-配置-1-2](../../media/778576c3-560e-4ffb-b3b4-bd92fc6a6bd4.png)
  
3. 在 "**域名**" 页上的 "**域**" 部分，选择要更新的域的名称。 
    
    ![CrazyDomains-配置-1-3](../../media/4dd7bb74-c8ed-4b4a-b4c1-d9538fc6bd9a.png)
  
4. 在 " **DNS 设置**" 部分中，选择下拉列表图标。 
    
    ![CrazyDomains-配置-1-4-1](../../media/c7573fbf-467d-49c1-abb6-8c7b9b4af83d.png)
  
5. 选择 "**添加记录**"。
    
    ![CrazyDomains-配置-1-4-2](../../media/7bef31f5-f180-4b61-a462-9326789e770f.png)
  
6. 从 "**添加记录：** " 下拉列表中选择 " **CNAME 记录**"。 
    
    ![CrazyDomains-配置-3-1](../../media/2f02538b-fc79-46d2-a2b7-1022eaf0fb08.png)
  
7. 选择“**添加**”。
    
    ![CrazyDomains-配置-3-2](../../media/4c5929cf-1c21-4af9-899b-e36091f0f14d.png)
  
8. 添加第一条 CNAME 记录（共 6 条）。
    
    在新记录的框中，键入或复制并粘贴下表中第一行的值。
    
    |**子域**|**的别名**|
    |:-----|:-----|
    |自动发现  <br/> |autodiscover.outlook.com  <br/> |
    |sip  <br/> |sipdir.online.lync.com  <br/> |
    |lyncdiscover  <br/> |webdir.online.lync.com  <br/> |
    |enterpriseregistration  <br/> |enterpriseregistration.windows.net  <br/> |
    |enterpriseenrollment  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> |
   
    ![CrazyDomains-配置-3-3](../../media/81a7b837-3f4d-4565-89a9-380e4d318acf.png)
  
9. 选择 "**添加 CNAME 记录**"。
    
    ![CrazyDomains-配置-3-4](../../media/9bcba729-7085-4ebc-8183-ecde82f5c364.png)
  
10. 添加第二条 CNAME 记录。
    
    在新记录的框中，使用表中下一行的值，然后再次选择 "**添加 CNAME 记录**"。
    
    重复该过程，直到创建完全部 6 条 CNAME 记录。
    
11. 选择 "**更新**" 以保存所做的更改。 
    
    ![CrazyDomains-配置-3-5](../../media/dbe578f6-359c-428c-b296-ca624cecfc3c.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>为 SPF 添加 TXT 记录以帮助防止垃圾邮件
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> 一个域所拥有的 SPF 的 TXT 记录不能超过一个。 如果域具有多个 SPF 记录，你将收到电子邮件错误，其中随附发送和垃圾邮件分类问题。 If you already have an SPF record for your domain, don't create a new one for Office 365. 可以将所需的 Office 365 添加到当前记录，这样就拥有包含两组值的*单个*SPF 记录。 
  
1. 要开始，请使用[此链接](https://manage.crazydomains.com/members/domains/)转到你在 Crazy Domains 上的域页面。系统将会提示你首先登录。
    
    ![CrazyDomains-配置-1-1](../../media/40c5117c-acad-4fe5-bf0d-d3c362b08a16.png)
  
2. 在 "**我的帐户**" 部分，选择 "**域**"。
    
    ![CrazyDomains-配置-1-2](../../media/778576c3-560e-4ffb-b3b4-bd92fc6a6bd4.png)
  
3. 在 "**域名**" 页上的 "**域**" 部分，选择要更新的域的名称。 
    
    ![CrazyDomains-配置-1-3](../../media/4dd7bb74-c8ed-4b4a-b4c1-d9538fc6bd9a.png)
  
4. 在 " **DNS 设置**" 部分中，选择下拉列表图标。 
    
    ![CrazyDomains-配置-1-4-1](../../media/c7573fbf-467d-49c1-abb6-8c7b9b4af83d.png)
  
5. 选择 "**添加记录**"。
    
    ![CrazyDomains-配置-1-4-2](../../media/7bef31f5-f180-4b61-a462-9326789e770f.png)
  
6. 从 "**添加记录：** " 下拉列表中选择 " **TXT 记录**"。 
    
    ![CrazyDomains-配置-4-1](../../media/7f2461e2-0468-49bd-9eb0-981e9b2f72d6.png)
  
7. 选择“**添加**”。
    
    ![CrazyDomains-配置-4-2](../../media/64ef9e1f-676d-46e2-9253-a83d9bcd1c4e.png)
  
8. 在新记录的框中，键入或粘贴下表中的值。
    
    |**子域**|**文本记录**|
    |:-----|:-----|
    |（将此字段留空。）  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **注意：** 建议复制粘贴此条目，以保证正确保留所有空格。           |
   
    ![CrazyDomains-配置-4-3](../../media/e7fd524a-c94b-4cdd-b264-67abb532a71b.png)
  
9. 选择“更新”****。
    
    ![CrazyDomains-配置-4-4](../../media/d4f378ee-0f14-46ae-ba32-1596660ecf91.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a>添加 Office 365 所需的两条 SRV 记录
<a name="BKMK_add_SRV"> </a>

1. 要开始，请使用[此链接](https://manage.crazydomains.com/members/domains/)转到你在 Crazy Domains 上的域页面。系统将会提示你首先登录。
    
    ![CrazyDomains-配置-1-1](../../media/40c5117c-acad-4fe5-bf0d-d3c362b08a16.png)
  
2. 在 "**我的帐户**" 部分，选择 "**域**"。
    
    ![CrazyDomains-配置-1-2](../../media/778576c3-560e-4ffb-b3b4-bd92fc6a6bd4.png)
  
3. 在 "**域名**" 页上的 "**域**" 部分，选择要更新的域的名称。 
    
    ![CrazyDomains-配置-1-3](../../media/4dd7bb74-c8ed-4b4a-b4c1-d9538fc6bd9a.png)
  
4. 在 " **DNS 设置**" 部分中，选择下拉列表图标。 
    
    ![CrazyDomains-配置-1-4-1](../../media/c7573fbf-467d-49c1-abb6-8c7b9b4af83d.png)
  
5. 选择 "**添加记录**"。
    
    ![CrazyDomains-配置-1-4-2](../../media/7bef31f5-f180-4b61-a462-9326789e770f.png)
  
6. 从 "**添加记录：** " 下拉列表中选择 " **SRV 记录**"。 
    
    ![CrazyDomains-配置-5-1](../../media/156acebc-7f6d-4b5e-8493-6bc62ca0ee27.png)
  
7. 选择“**添加**”。
    
    ![CrazyDomains-配置-5-2](../../media/6a711df7-4215-49b2-b58f-1cf1a242b383.png)
  
8. 添加两条 SRV 记录中的第一条记录。
    
    在新记录的框中，键入或复制并粘贴下表中第一行的值。
    
    |**记录类型**|**子域**|**优先级**|**权重**|**端口**|**目标**|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |SRV 记录  <br/> |_sip _tls  <br/> |100  <br/> |1  <br/> |443  <br/> |sipdir.online.lync.com  <br/> |
    |SRV 记录  <br/> |_sipfederationtls _tcp  <br/> |100  <br/> |1  <br/> |5061  <br/> |sipfed.online.lync.com  <br/> |
   
    ![CrazyDomains-配置-5-3](../../media/cc0ea6eb-7358-434e-bd1a-2737725c6d41.png)
  
9. 选择 "**添加 SRV 记录**"。
    
    ![CrazyDomains-配置-5-4](../../media/de4ec312-6833-469a-b23a-f376140a35ca.png)
  
10. 添加另一条 SRV 记录。
    
    在新记录的框中，使用表中第二行的值。
    
11. 选择 "**更新**" 以保存所做的更改。 
    
    ![CrazyDomains-配置-5-5](../../media/f0bb1dd6-3772-4293-bf74-710f635e0658.png)
  
> [!NOTE]
> DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。 
  
