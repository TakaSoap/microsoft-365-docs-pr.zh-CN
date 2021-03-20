---
title: 在 Freenom for Microsoft 创建 DNS 记录
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
ms.assetid: d8ff45a2-19e3-413d-aa64-a9982bd6633c
description: 了解如何在 Freenom for Microsoft 中验证域并设置电子邮件、Skype for Business Online 和其他服务的 DNS 记录。
ms.openlocfilehash: 8332d63acf34a7f999b549467494b7819cebf092
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50910350"
---
# <a name="create-dns-records-at-freenom-for-microsoft"></a>在 Freenom for Microsoft 创建 DNS 记录

[如果找不到 ](../setup/domains-faq.yml) 要查找的内容，请查看域常见问题解答。 
  
> [!CAUTION]
> Freenom 网站不支持 SRV 记录，这意味着多个 Skype for Business Online 和 Outlook Web App 功能将不起作用。 无论使用哪种 Microsoft 计划，都存在重大服务限制，您可能需要切换到其他 DNS 托管提供商。 
  
If despite the service limitations， you choose to manage your own Microsoft DNS records at Freenom， follow the steps in this article to verify your domain and set up DNS records for email and other services.
  
  
> [!NOTE]
> DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。 
  
## <a name="add-a-txt-record-for-verification"></a>添加 TXT 记录进行验证
<a name="bkmk_txt"> </a>

在将域用于 Microsoft 之前，必须确保你拥有该域。如果你能够在域注册机构处登录到你的帐户并创建 DNS 记录，便可向 Microsoft 证明你是域所有者。
  
> [!NOTE]
> 此记录仅用于验证您是否拥有自己的域；它不会影响其他任何内容。 如果需要，您可以以后将其删除。 
  
1. To get started， go to your domains page in Freenom by using [this link](https://my.freenom.com/). You'll be prompted to log in.
    
    ![Freenom 登录](../../media/90a32855-bfdd-4dfe-881c-b9a36b2f0582.png)
  
2. 选择 **"服务**"，然后选择"**我的域"。**
    
    ![Freenom 选择"服务和我的域"](../../media/1917ced2-e254-4aec-9096-46d339b84d9a.png)
  
3. 对于要编辑的域，请选择"**管理域"。**
    
    ![Freenom 选择"管理域"](../../media/67737b71-8b1b-42a6-abaf-62d776d3eb87.png)
  
4. 选择 **"管理 Freenom DNS"。**
    
    ![Freenom 管理 Freenom DNS](../../media/9854a511-27e3-4658-8903-34b3d425096d.png)
  
5. 在 **"添加记录"** 下的"**类型"** 列中，从菜单中选择 **"TXT"。** 
    
    ![Freenom 添加记录类型 TXT](../../media/7f0e85e7-844f-4962-815e-5d80d9e6efa0.png)
  
6. 在新记录的框中，键入或复制并粘贴下表中的值。 
    
    |**名称**|**类型**|**TTL**|**Target**|
    |:-----|:-----|:-----|:-----|
    |（保留为空白）  <br/> |TXT  <br/> |3600 (秒)   <br/> |MS=msXXXXXXXX  <br/> **注意：** 这是一个示例。 在这里使用表中的特定“**目标地址或指向的地址**”值。           [如何查找此项？](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![用于验证的 Freenom TXT 值](../../media/650098df-b3aa-47e5-9763-7fde24e34c3f.png)
  
7. 选择 **"保存更改"。**
    
    ![Freenom TXT 记录 保存更改](../../media/b1a63f9a-4578-491a-9554-c40f73b37e09.png)
  
8. 请在继续之前等待数分钟，以便您刚刚创建的记录可以通过 Internet 完成更新。
    
在在域注册机构网站添加了记录后，你将返回到 Microsoft 并请求记录。
  
Microsof 找到正确的 TXT 记录表明域已通过验证。
  
1. 在 Microsoft 管理中心，转到“**设置**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">域</a>”页面。

    
2. 在“**域**”页面上，选择要验证的域。 
    
    
  
3. 在“**设置**”页面上，选择“**开始设置**”。
    
    
  
4. 在“**验证域**”页面上，选择“**验证**”。
    
    
  
> [!NOTE]
>  DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>添加一条 MX 记录，确保发往你的域的电子邮件将会发送到 Microsoft
<a name="bkmk_mx"> </a>

1. To get started， go to your domains page in Freenom by using [this link](https://my.freenom.com/). You'll be prompted to log in.
    
    ![Freenom 登录](../../media/90a32855-bfdd-4dfe-881c-b9a36b2f0582.png)
  
2. 选择 **"服务**"，然后选择"**我的域"。**
    
    ![Freenom 选择"服务和我的域"](../../media/1917ced2-e254-4aec-9096-46d339b84d9a.png)
  
3. 对于要编辑的域，请选择"**管理域"。**
    
    ![Freenom 选择"管理域"](../../media/67737b71-8b1b-42a6-abaf-62d776d3eb87.png)
  
4. 将域的名称"服务"设置为默认 Freenom 名称服务器。 选择 **"管理工具"，** 然后选择"**名称服务器"。**
    
    ![Freenom Nameservers 设置](../../media/a6ae877a-c248-42b9-bae9-210a80cd01e7.png)
  
5. 确保选中 **"使用默认名称服务器**"，然后选择"**更改名称服务器"。**
    
    ![Freenom Change Nameservers](../../media/0ef90d84-c0a0-4ef9-9e4c-43ef0aac3a2e.png)
  
6. 选择 **"管理 Freenom DNS"。**
    
    ![Freenom 选择"管理 Freenom DNS"](../../media/f55a8053-2411-45da-a357-776c6699f721.png)
  
7. 在 **"添加记录"** 下的"**类型"** 列中，从 **菜单中选择"MX"。** 
    
    ![Freenom 添加记录类型 MX](../../media/c728c6ee-786c-4f6a-8ad5-1d9914a5bfcf.png)
  
8. 在新记录的框中，键入或复制并粘贴下表中第一行的值。 
    
    |**名称**|**类型**|**TTL**|**Target**|**Priority**|
    |:-----|:-----|:-----|:-----|:-----|
    |（保留为空白）  <br/> |MX (Mail Exchanger)   <br/> |3600 (秒)   <br/> |\<domain-key\>.mail.protection.outlook.com  <br/> **注意：** 从  *\<domain-key\>*  Microsoft 帐户获取你的信息。   如何查找此内容？[](../get-help-with-domains/information-for-dns-records.md)          |10    <br/> 有关优先级的详细信息，请参阅[什么是 MX 优先级？](../setup/domains-faq.yml) <br/> |
   
   ![Freenom MX 记录](../../media/8896c4a9-b3dd-45ed-9916-f7da2715ba8c.png)
  
9. 选择 **"保存更改"。**
    
    ![Freenom MX 记录 保存更改](../../media/7aa0a464-d136-417f-be40-48d3f728eeb7.png)
  
10. 如果存在任何其他 MX 记录，请全部删除。 对于每个记录，选择"删除 **"。** 当出现消息 **"是否确实要删除此条目？"** 时，选择"确定 **"。**
    
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a>添加 Microsoft 所需的 CNAME 记录
<a name="bkmk_cname"> </a>

1. To get started， go to your domains page in Freenom by using [this link](https://my.freenom.com/). You'll be prompted to log in.
    
    ![Freenom 登录](../../media/90a32855-bfdd-4dfe-881c-b9a36b2f0582.png)
  
2. 选择 **"服务**"，然后选择"**我的域"。**
    
    ![Freenom 选择"服务和我的域"](../../media/1917ced2-e254-4aec-9096-46d339b84d9a.png)
  
3. 对于要编辑的域，请选择"**管理域"。**
    
    ![Freenom 选择"管理域"](../../media/67737b71-8b1b-42a6-abaf-62d776d3eb87.png)
  
4. 选择 **"管理 Freenom DNS"。**
    
    ![Freenom 选择"管理 Freenom DNS"](../../media/5e7bc3a7-0d5e-431b-bb27-da3b0f316d01.png)
  
5. 在 **"添加记录"** 下的"**类型**"列中，从 **菜单中选择"CNAME"。** 
    
    ![Freenom 添加记录类型 CNAME](../../media/9b204755-ca2a-46d2-bce2-030d82fd1f9e.png)
  
6. 创建第一条 CNAME 记录。 在新记录的框中，键入或复制并粘贴下表中第一行的值。 
    
    |**名称**|**记录类型**|**TTL**|**Target**|
    |:-----|:-----|:-----|:-----|
    |自动发现  <br/> |CNAME  <br/> |3600 (秒)   <br/> |autodiscover.outlook.com  <br/> |
    |sip  <br/> |CNAME  <br/> |3600 (秒)   <br/> |sipdir.online.lync.com  <br/> |
    |lyncdiscover  <br/> |CNAME  <br/> |3600 (秒)   <br/> |webdir.online.lync.com  <br/> |
    |enterpriseregistration  <br/> |CNAME  <br/> |3600 (秒)   <br/> |enterpriseregistration.windows.net  <br/> |
    |enterpriseenrollment  <br/> |CNAME  <br/> |3600 (秒)   <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> |
   
    ![Freenom CNAME 值](../../media/752fc682-e3f2-4b9c-9253-bf1ba2d414e9.png)
  
7. 选择 **"保存更改"。**
    
    ![Freenom CNAME 保存更改](../../media/68103fd2-0f5f-4aac-a875-25157c6bbdd2.png)
  
8. 重复上述步骤以创建其他五条 CNAME 记录。 
    
    对于每个记录，键入或复制上表中下一行的值并将其粘贴到该记录的框中。
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>为 SPF 添加 TXT 记录以帮助防止垃圾邮件
<a name="bkmk_spf"> </a>

> [!IMPORTANT]
> 一个域所拥有的 SPF 的 TXT 记录不能超过一个。 如果域具有多个 SPF 记录，你将收到电子邮件错误，其中随附发送和垃圾邮件分类问题。 如果你的域已有 SPF 记录，请不要为 Microsoft 创建新记录。 相反，将所需的 Microsoft 值添加到当前记录，以便你有一个  *包含这*  两组值的 SPF 记录。 

1. To get started， go to your domains page in Freenom by using [this link](https://my.freenom.com/). You'll be prompted to log in.
    
    ![Freenom 登录](../../media/90a32855-bfdd-4dfe-881c-b9a36b2f0582.png)
  
2. 选择 **"服务**"，然后选择"**我的域"。**
    
    ![Freenom 选择"服务和我的域"](../../media/1917ced2-e254-4aec-9096-46d339b84d9a.png)
  
3. 对于要编辑的域，请选择"**管理域"。**
    
    ![Freenom 选择"管理域"](../../media/67737b71-8b1b-42a6-abaf-62d776d3eb87.png)
  
4. 选择 **"管理 Freenom DNS"。**
    
    ![Freenom 选择"管理 Freenom DNS"](../../media/94809955-0315-409c-a15d-703a2fe4c4ed.png)
  
5. 在 **"添加记录"** 下的"**类型"** 列中，从菜单中选择 **"TXT"。** 
    
    ![Freenom 添加记录类型 TXT](../../media/d8854285-c4ae-416c-a072-72a11ba1cd9a.png)
  
6. In the boxes for the new record, type or copy and paste the following values. 
    
    |**名称**|**记录类型**|**TTL**|**Target**|
    |:-----|:-----|:-----|:-----|
    |（保留为空白）  <br/> |TXT  <br/> |3600 (秒)   <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/>**注意：** 建议复制粘贴此条目，以保证正确保留所有空格。           |
   
    ![SPF 的 Freenom TXT 值](../../media/1b3b1199-9104-4ca1-acdb-786d139c21ac.png)
  
7. 选择 **"保存更改"。**
    
    ![SPF 保存更改的 Freenom TXT 记录](../../media/e2fc52b1-0dcb-4595-9a4c-fca5e2ef9f97.png)
