---
title: 在 Google Domains 为 Office 365 创建 DNS 记录
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
ms.assetid: 0db29490-2612-48bc-9b77-1862e7a41a8c
description: 了解如何在适用于 Office 365 的 Google 域上验证您的域并为电子邮件、Lync 和其他服务设置 DNS 记录。
ms.openlocfilehash: c59a3d63797f20b0d3a42647eb68d7699ed63450
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/24/2020
ms.locfileid: "42240825"
---
# <a name="create-dns-records-at-google-domains-for-office-365"></a>在 Google Domains 为 Office 365 创建 DNS 记录

 **如果找不到要查找的内容，请[查看域常见问题解答](../setup/domains-faq.md)** 。 
  
如果 DNS 托管提供商是 Google Domains，请按照本文中的步骤验证域并为电子邮件、Lync 等设置 DNS 记录。
  
在 Google Domains 添加这些记录后，域将设置为使用 Office 365 服务。
  
若要了解如何与 Office 365 结合使用网站的 Web 宿主和 DNS，请参阅[配合使用公共网站与 Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9)。
  
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅[在 Office 365 中添加域或 DNS 记录后，查找并修复问题](../get-help-with-domains/find-and-fix-issues.md)。 
  
## <a name="add-a-txt-record-for-verification"></a>添加 TXT 记录进行验证
<a name="BKMK_verify"> </a>

在将域用于 Office 365 之前，必须确保你拥有该域。如果你能够在域注册机构处登录到你的帐户并创建 DNS 记录，便可向 Office 365 证明你是所有者。
  
> [!NOTE]
> 此记录仅用于验证您是否拥有自己的域；它不会影响其他任何内容。 如果需要，您可以以后将其删除。 
  
1. 要开始，请使用[此链接](https://domains.google.com/registrar)转到你在 Google Domains 上的域页面。 系统将会提示您登录。 为此，请执行以下操作：
    
1. 选择 **"登录"**。
    
2. 输入登录凭据，然后再次选择 **"登录**"。
    
2. 在 "**我的域**" 页面上，找到要用于 Office 365 的域，然后选择它旁边的 "**管理**" 链接。 在左侧导航栏中，选择 " **DNS**"。
    
3. 在 "* * 自定义资源记录 * *" 部分中新记录的框内，键入或复制并粘贴下表中的值。 
    
    (You may have to scroll down.)
    
    (Choose the **Type** value from the drop-down list.) 
    
    |||||
    |:-----|:-----|:-----|:-----|
    |**名称** <br/> |**Type** <br/> |**TTL** <br/> |**数据** <br/> |
    |@  <br/> |TXT  <br/> |1H  <br/> |MS=ms *XXXXXXXX*  <br/> **注意：** 这是一个示例。 在这里使用来自 Office 365 中的表的特定" **目标或指向的地址**"值。 [如何查找此内容？](../get-help-with-domains/information-for-dns-records.md)          |
   
4. 选择“**添加**”。
    
5. 请在继续之前等待数分钟，以便您刚刚创建的记录可以通过 Internet 完成更新。
    
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

1. 要开始，请使用[此链接](https://domains.google.com/registrar)转到你在 Google Domains 上的域页面。 系统将会提示您登录。 为此，请执行以下操作：
    
2. 选择 **"登录"**。
    
3. 输入登录凭据，然后再次选择 **"登录**"。
4. 在 "**域**" 页上的 "**域**" 部分，为要编辑的域选择 "**配置 DNS** "。
    
    > [!IMPORTANT]
    > 如果有 G 套件电子邮件帐户，必须先删除与该帐户关联的 MX 记录。G 套件的 MX 记录将导致无法添加任何其他 MX 记录，包括 Office 365 所需的 MX 记录。请注意，删除 G 套件记录不会删除 G 套件帐户。若要删除 G 套件 MX 记录，请使用以下步骤。 
  
5. 在 "**综合记录**" 部分的 " **G 套件**" 区域中，选择 "**删除**"。
    
    (You may have to scroll down.)
    
    ![在 "综合记录" 部分中选择 "删除"](../media/bd276b5d-5667-4bb1-a233-2dc5194e7ace.png)
  
6. 选择 "**删除**"。
    
    ![选择 "删除"](../media/4413a45a-5b82-4ec6-82c6-0091f5be9696.png)
  
7. In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (You may have to scroll down.)
    
    (Choose the **Type** value from the drop-down list.) 
    
    |**名称**|**Type**|**TTL**|**数据**|
    |:-----|:-----|:-----|:-----|
    |@  <br/> |MX  <br/> |1H  <br/> |0  *\<域密钥\>*  .mail.protection.outlook.com。  <br/> **此值必须以句点 (.) 结尾。** <br/> **0** 是 MX 优先级值。将其添加到 MX 值的开头，使用一个空格将其与其余部分隔开。  <br/> **注意：** 从 Office \<365 帐户中获取你的*域密钥*\> 。  如何查找此内容？[](../get-help-with-domains/information-for-dns-records.md)          有关优先级的详细信息，请参阅[什么是 MX 优先级？](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx) <br/> |
   
    ![在 "自定义资源记录" 部分键入或粘贴值](../media/b660ca9e-984d-449f-ae59-a65fe4e2c6bd.png)
  
5. 选择“**添加**”。
    
    ![选择"添加"](../media/32f8f23c-0b80-48da-b08e-4e04052971af.png)
  
6. 如果有任何其他自定义 MX 记录，请将其删除。
    
1. 在 "MX 记录" 行中选择 "**编辑**"。 
    
    ![在 MX 记录行中选择 "编辑"](../media/acc53ae9-3b8a-421d-8d11-d4a4108b2353.png)
  
2. 对于每个其他自定义 MX 记录，请选择 "**数据**" 框中的条目，然后按键盘上的**Delete**键以删除该记录。 
    
    继续操作，直到删除所有其他 MX 记录的" **数据**"条目。 
    
    ![Delete entries in the Data box](../media/28192089-7b38-4d2e-9d52-9b83422c27d5.png)
  
7. 删除了每个其他 MX 记录的**数据**输入后，请选择 "**保存**" 以保存所做的更改。 
    
    ![选择 "保存"](../media/bf496d01-ccbe-4800-95f4-7b2283f2e5f6.png)
  
## <a name="add-the-five-cname-records-that-are-required-for-office-365"></a>添加 Office 365 所需的五个 CNAME 记录

1. 若要开始，请转到 [Google 域页面] （https://domains.google.com/registrar)并登录。
    
2. 在 "**域**" 页上的 "**域**" 部分，为要编辑的域选择 "**配置 DNS** "。 
    
3. 添加第一条 CNAME 记录。
    
    在" **自定义资源记录**"部分中新记录的框内，键入或复制粘贴下表第一行中的值。 
    
    (You may have to scroll down.)
    
    (Choose the **Type** value from the drop-down list.) 
    
    |**名称**|**Type**|**TTL**|**数据**|
    |:-----|:-----|:-----|:-----|
    |autodiscover  <br/> |CNAME  <br/> |1H  <br/> |autodiscover.outlook.com。  <br/> **This value MUST end with a period (.)** <br/> |
    |sip  <br/> |CNAME  <br/> |1H  <br/> |sipdir.online.lync.com。  <br/> **This value MUST end with a period (.)** <br/> |
    |lyncdiscover  <br/> |CNAME  <br/> |1H  <br/> |webdir.online.lync.com。  <br/> **This value MUST end with a period (.)** <br/> |
    |enterpriseregistration  <br/> |CNAME  <br/> |1H  <br/> |enterpriseregistration.windows.net。  <br/> **This value MUST end with a period (.)** <br/> |
    |enterpriseenrollment  <br/> |CNAME  <br/> |1H  <br/> |enterpriseenrollment-s.manage.microsoft.com。  <br/> **This value MUST end with a period (.)** <br/> |
   
    ![在 "自定义资源记录" 部分键入或粘贴值](../media/cff9832a-6d57-421f-a183-55320974ed87.png)
  
4. 选择“**添加**”。
    
    ![选择"添加"](../media/4a78080a-e0b2-4582-9696-3fe4fea41e91.png)
  
5. 添加其他 4 条 CNAME 记录。
    
    在 "**自定义资源记录**" 部分，使用表中下一行的值创建记录，然后再次选择 "**添加**" 以完成该记录。 
    
    重复此过程，直到您已创建所有必需的 CNAME 记录。
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>为 SPF 添加 TXT 记录以帮助防止垃圾邮件

> [!IMPORTANT]
> You cannot have more than one TXT record for SPF for a domain. If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues. If you already have an SPF record for your domain, don't create a new one for Office 365. Instead, add the required Office 365 values to the current record so that you have a single SPF record that includes both sets of values. Need examples? 查看[Office 365 的这些外部域名系统记录](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0#bkmk_spfrecords)。 To validate your SPF record, you can use one of these [SPF validation tools](../setup/domains-faq.md). 
  
1. 要开始，请使用[此链接](https://domains.google.com/registrar)转到你在 Google Domains 上的域页面。 系统将会提示您登录。 为此，请执行以下操作：
    
1. 选择 **"登录"**。
    
2. 输入登录凭据，然后再次选择 **"登录**"。
    
3. 在 "**域**" 页上的 "**域**" 部分，为要编辑的域选择 "**配置 DNS** "。 
    
4. 在 "**自定义资源记录**" 部分的 "TXT 记录" 行中，选择 "**编辑**"。 
    
    > [!IMPORTANT]
    > Google Domains 会将 TXT 记录存储为可能含有多条记录的集。存在至少一条其他 TXT 记录（例如用于验证域的 TXT 记录）时，必须向该记录集添加新的 TXT 记录。如果尝试将其他 TXT 记录作为单独条目进行输入，将始终出现" **记录重复**"错误信息。 
  
    ![在 TXT 记录行中选择 "编辑"](../media/eae14850-8d0c-4f29-8587-df8b36129d5f.png)
  
5. 选择 " **（+）** " 控件。 
    
    ![选择加号控件](../media/628604cc-d2b2-42a5-bb5b-13c327b85d9f.png)
  
6. 在新记录的框中，键入或复制粘贴下表中的值。
    
    （可能需要向下滚动。）
    
    |**数据**|
    |:-----|
    |v=spf1 include:spf.protection.outlook.com -all  <br/> 

    > [!NOTE]
    > We recommend copying and pasting this entry, so that all of the spacing stays correct.           
   
   ![在 "自定义资源记录" 部分键入或粘贴值](../media/4645cc4f-9fcc-4626-9674-072ed6fa34c2.png)
  
7. 选择“**保存**”。
    
    ![选择 "保存"](../media/20c4c926-f062-4048-9265-bf752be54e0c.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a>添加 Office 365 所需的两条 SRV 记录
<a name="BKMK_add_SRV"> </a>

1. 要开始，请使用[此链接](https://domains.google.com/registrar)转到你在 Google Domains 上的域页面。 系统将会提示您登录。 为此，请执行以下操作：
    
2. 选择 **"登录"**。
    
3. 输入登录凭据，然后再次选择 **"登录**"。
    
4. 在 "**域**" 页上的 "**域**" 部分，为要编辑的域选择 "**配置 DNS** "。 
    
5. 添加第一条 SRV 记录。
    
    In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (You may have to scroll down.)
    
    (Choose the **Type** value from the drop-down list.) 
    
    |**名称**|**Type**|**TTL**|**Data**|
    |:-----|:-----|:-----|:-----|
    |_sip _tls|SRV|1H|100 1 443 sipdir.online.lync.com。 **此值必须以句点（.）结尾****注意：** 我们建议您复制并粘贴此条目，以确保所有的间距保持正确。           |
    |_sipfederationtls _tcp|SRV|1H|100 1 5061 sipfed.online.lync.com。 **This value MUST end with a period (.)**

    We recommend copying and pasting this entry, so that all of the spacing stays correct.       
   
    ![在 "自定义资源记录" 部分键入或粘贴值](../media/429d06a9-c0af-4961-b7d2-7a8dea6db37e.png)
  
6. 选择“**添加**”。
    
    ![选择"添加"](../media/89df6efd-e641-4441-baa2-d9a890424569.png)
  
7. 添加另一条 SRV 记录。
    
    在 "**自定义资源记录**" 部分，使用表中第二行的值创建记录，然后再次选择 "**添加**" 以完成该记录。 
    
    > [!NOTE]
    > Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅[在 Office 365 中添加域或 DNS 记录后，查找并修复问题](../get-help-with-domains/find-and-fix-issues.md)。 
  
