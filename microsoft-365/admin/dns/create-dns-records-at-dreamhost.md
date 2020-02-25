---
title: 在 Dreamhost 上为 Office 365 创建 DNS 记录
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
ms.assetid: 9c0812e0-908b-4b41-a64b-77f0dbd3db7a
description: 了解如何在 Dreamhost for Office 365 中验证您的域并为电子邮件、Skype for Business Online 和其他服务设置 DNS 记录。
ms.openlocfilehash: f3f52e97fefece72dd96d9370e75e24fc4cebedf
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/24/2020
ms.locfileid: "42240752"
---
# <a name="create-dns-records-at-dreamhost-for-office-365"></a>在 Dreamhost 上为 Office 365 创建 DNS 记录

 如果找不到要查找的内容，请**[查看域常见问题解答](../setup/domains-faq.md)**。 
  
如果 DreamHost 是您的 DNS 托管提供商，请按照本文中的步骤验证您的域并为电子邮件、Lync 等设置 DNS 记录。
 
在 DreamHost 中添加这些记录后，您的域将设置为与 Office 365 服务配合使用。
  
若要了解如何与 Office 365 结合使用网站的 Web 宿主和 DNS，请参阅[配合使用公共网站与 Office 365](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx)。
  
> [!NOTE]
> DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。 
  
## <a name="add-a-txt-record-for-verification"></a>添加 TXT 记录进行验证
<a name="BKMK_verify"> </a>

在将域用于 Office 365 之前，必须确保你拥有该域。如果你能够在域注册机构处登录到你的帐户并创建 DNS 记录，便可向 Office 365 证明你是所有者。
  
> [!NOTE]
> 此记录仅用于验证您是否拥有自己的域；它不会影响其他任何内容。 如果需要，您可以以后将其删除。 
  
1. 若要开始，请使用[此链接](https://panel.dreamhost.com/)转到 DreamHost 上的 "域" 页面。 系统将提示您登录。
    
    ![Dreamhost-配置-1-1](../media/1919b810-b6ba-4e29-a774-de1e7c67d078.png)
  
2. 在**仪表板**页面上，选择 "**域**"，然后**管理域**。
    
    ![Dreamhost-配置-1-2](../media/ab05c16a-79f6-491f-ad07-9a2e6674671d.png)
  
3. 在 "**管理域**" 页上的 "**域**" 部分，为要编辑的域选择 " **DNS** "。 
    
    ![Dreamhost-配置-1-3](../media/1a8723a0-54bc-40ff-bc30-5fc3e8cd219b.png)
  
4. In the **Add a custom DNS record** section, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (You may have to scroll down.)
    
    (Choose the **Type** value from the drop-down list.) 
    
    |**名称**|**Type**|**值**|**Comment**|
    |:-----|:-----|:-----|:-----|
    |(Leave this field empty.)  <br/> |TXT  <br/> |MS=ms *XXXXXXXX*  <br/> **注意：** 这是一个示例。 在这里使用来自 Office 365 中的表的特定" **目标或指向的地址**"值。           [如何查找此内容？](../get-help-with-domains/information-for-dns-records.md)          |（此字段是可选的。）  <br/> |
   
   ![Dreamhost-验证-1-1](../media/ed4a7d43-eeeb-4ec8-849c-37f81315dc69.png)
  
5. 立即选择 "**添加记录"！**
    
    ![Dreamhost-验证-1-2](../media/5b89c89b-3a8e-4624-895a-86f3cc4638f6.png)
  
6. 请在继续之前等待数分钟，以便您刚刚创建的记录可以通过 Internet 完成更新。
    
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

按照下面的步骤操作。
  
1. 若要开始，请使用[此链接](https://panel.dreamhost.com/)转到 DreamHost 上的 "域" 页面。 系统将提示您登录。
    
    ![Dreamhost-配置-1-1](../media/1919b810-b6ba-4e29-a774-de1e7c67d078.png)
  
2. 在**仪表板**页面上，依次选择 "**邮件**" 和 "**自定义 MX**"。
    
    ![Dreamhost-配置-2-1](../media/58478679-4018-49cc-9d83-371dc5fa4a22.png)
  
3. 在 "**管理邮件传递**" 部分的 "**操作**" 列中，为要编辑的域选择 "**编辑**"。 
    
    ![Dreamhost-配置-2-2](../media/6eed0be2-6477-4f49-9f90-39e190499a53.png)
  
4. 在 "**自定义 MX 记录**" 部分中，在新记录的框中，键入或复制并粘贴下表中的以下值。 
    
    (You may have to scroll down.)
    
    （如果存在任何其他现有 MX 记录，则将这些记录标记为 "删除"。）
    
    |**MX 记录（必需）**|
    |:-----|
    |0  *\<域密钥\>*  .mail.protection.outlook.com。  <br/> **此值必须以句点 (.) 结尾。** <br/> 0 是 MX 优先级值。 将其添加到 MX 值的开头，使用一个空格将其与其余部分隔开。  <br/> **注意：** 从 Office 365 帐户中获取你* \<的域密钥\> * 。           [如何查找此内容？](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Dreamhost-配置-2-3](../media/90da1816-e186-4016-ab22-7962f8b86add.png)
  
5. 选择 "**立即将此域改为使用自定义 MX 记录！** "
    
    ![Dreamhost-配置-2-4](../media/3221c767-83d3-4f30-9d08-dc998772d2a3.png)
  
6. 如果存在任何其他现有 MX 记录，请通过选择相应的条目，然后按键盘上的**delete**键来删除每个记录。 
    
    ![Dreamhost-配置-2-5](../media/1827733c-3609-4b0f-bba1-531ab090da91.png)
  
7. 如果已删除任何记录，请选择 "**立即更新自定义 MX 记录！** "
    
    ![Dreamhost-配置-2-6](../media/177462be-0686-47b7-a389-025dfc8d6526.png)

  
## <a name="add-the-six-cname-records-that-are-required-for-office-365"></a>添加 Office 365 所需的 6 条 CNAME 记录
<a name="BKMK_add_CNAME"> </a>

按照下面的步骤操作。
  
1. 若要开始，请使用[此链接](https://panel.dreamhost.com/)转到 DreamHost 上的 "域" 页面。 系统将提示您登录。
    
    ![Dreamhost-配置-1-1](../media/1919b810-b6ba-4e29-a774-de1e7c67d078.png)
  
2. 在**仪表板**页面上，选择 "**域**"，然后**管理域**。
    
    ![Dreamhost-配置-1-2](../media/ab05c16a-79f6-491f-ad07-9a2e6674671d.png)
  
3. 在 "**管理域**" 页上的 "**域**" 部分，为要编辑的域选择 " **DNS** "。 
    
    ![Dreamhost-配置-1-3](../media/1a8723a0-54bc-40ff-bc30-5fc3e8cd219b.png)
  
4. 在 "**添加自定义 DNS 记录**" 部分中，在新记录的框中，键入或复制并粘贴下表中第一行的值。 
    
    (You may have to scroll down.)
    
    (Choose the **Type** value from the drop-down list.) 
    
    |**名称**|**Type**|**值**|**Comment**|
    |:-----|:-----|:-----|:-----|
    |autodiscover  <br/> |CNAME  <br/> |autodiscover.outlook.com。  <br/> **This value MUST end with a period (.)** <br/> |（此字段是可选的。）  <br/> |
    |sip  <br/> |CNAME  <br/> |sipdir.online.lync.com。  <br/> **This value MUST end with a period (.)** <br/> |（此字段是可选的。）  <br/> |
    |lyncdiscover  <br/> |CNAME  <br/> |webdir.online.lync.com。  <br/> **This value MUST end with a period (.)** <br/> |（此字段是可选的。）  <br/> |
    |enterpriseregistration  <br/> |CNAME  <br/> |enterpriseregistration.windows.net。  <br/> **This value MUST end with a period (.)** <br/> |（此字段是可选的。）  <br/> |
    |enterpriseenrollment  <br/> |CNAME  <br/> |enterpriseenrollment-s.manage.microsoft.com。  <br/> **This value MUST end with a period (.)** <br/> |（此字段是可选的。）  <br/> |
   
    ![Dreamhost-配置-3-1](../media/0c4cc587-ea24-47f2-8dc6-a35735b250e6.png)
  
5. 立即选择 "**添加记录"！**
    
    ![Dreamhost-配置-3-2](../media/b5d4f939-de6d-4d1f-a20a-4eb5fe715281.png)
  
6. 使用前面的两个步骤和表中的其他五行中的值，添加其他五个 CNAME 记录中的每个。

  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>为 SPF 添加 TXT 记录以帮助防止垃圾邮件
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> You cannot have more than one TXT record for SPF for a domain. If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues. If you already have an SPF record for your domain, don't create a new one for Office 365. 改为将所需的 Office 365 值添加到当前记录，以便您具有包含两组值的*单个*SPF 记录。
  
按照下面的步骤操作。
  
1. 若要开始，请使用[此链接](https://panel.dreamhost.com/)转到 DreamHost 上的 "域" 页面。 系统将提示您登录。
    
    ![Dreamhost-配置-1-1](../media/1919b810-b6ba-4e29-a774-de1e7c67d078.png)
  
2. 在**仪表板**页面上，选择 "**域**"，然后**管理域**。
    
    ![Dreamhost-配置-1-2](../media/ab05c16a-79f6-491f-ad07-9a2e6674671d.png)
  
3. 在 "**管理域**" 页上的 "**域**" 部分，为要编辑的域选择 " **DNS** "。 
    
    ![Dreamhost-配置-1-3](../media/1a8723a0-54bc-40ff-bc30-5fc3e8cd219b.png)
  
4. 在 "**添加自定义 DNS 记录**" 部分中，在新记录的框中，键入或复制并粘贴下表中第一行的值。 
    
    (You may have to scroll down.)
    
    (Choose the **Type** value from the drop-down list.) 
    
    |**名称**|**Type**|**值**|**Comment**|
    |:-----|:-----|:-----|:-----|
    |(Leave this field empty.)  <br/> |TXT  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **注意：** 我们建议您复制并粘贴此条目，以确保所有的间距保持正确。           |（此字段是可选的。）  <br/> |
   
   ![Dreamhost-配置-4-1](../media/cbc4bbca-bdbc-4dc9-b1b7-b55491eb1e53.png)
  
5. 立即选择 "**添加记录"！**
    
    ![Dreamhost-配置-4-2](../media/2bd7cae8-1fbc-4407-8dfa-06ce37c586c0.png)
  
6. 使用前面的两个步骤和表中第二行的值，添加另一条 SRV 记录。
    
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a>添加 Office 365 所需的两条 SRV 记录
<a name="BKMK_add_SRV"> </a>

按照下面的步骤操作。
  
1. 若要开始，请使用[此链接](https://panel.dreamhost.com/)转到 DreamHost 上的 "域" 页面。 系统将提示您登录。
    
    ![Dreamhost-配置-1-1](../media/1919b810-b6ba-4e29-a774-de1e7c67d078.png)
  
2. 在**仪表板**页面上，选择 "**域**"，然后**管理域**。
    
    ![Dreamhost-配置-1-2](../media/ab05c16a-79f6-491f-ad07-9a2e6674671d.png)
  
3. 在 "**管理域**" 页上的 "**域**" 部分，为要编辑的域选择 " **DNS** "。 
    
    ![Dreamhost-配置-1-3](../media/1a8723a0-54bc-40ff-bc30-5fc3e8cd219b.png)
  
4. 在 "**添加自定义 DNS 记录**" 部分中，在新记录的框中，键入或复制并粘贴下表中第一行的值。 
    
    (You may have to scroll down.)
    
    (Choose the **Type** value from the drop-down list.) 
    
    |**名称**|**Type**|**值**|**Comment**|
    |:-----|:-----|:-----|:-----|
    |_sip _tls  <br/> |SRV  <br/> |100 1 443  <br/> sipdir.online.lync.com。  <br/> **This value MUST end with a period (.)** <br/> |（此字段是可选的。）  <br/> |
    |_sipfederationtls _tcp  <br/> |SRV  <br/> |100 1 5061  <br/> sipfed.online.lync.com。  <br/> **此值必须以句点 (.) 结尾。** <br/> |（此字段是可选的。）  <br/> |
   
    ![Dreamhost-配置-5-1](../media/934eb79f-3617-4b72-802c-c42c7d165283.png)
  
5. 选择 "**立即添加记录"！**。
    
    ![Dreamhost-配置-5-2](../media/015bc73c-8f88-49ce-87f9-e5a6ea3e10a8.png)
  
6. 使用前面的两个步骤和表中第二行的值，添加另一条 SRV 记录。
    
> [!NOTE]
>  DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。 

  
