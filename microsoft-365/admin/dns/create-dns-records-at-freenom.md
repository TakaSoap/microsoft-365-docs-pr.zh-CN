---
title: 在 Freenom 处为 Microsoft 创建 DNS 记录
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
ms.assetid: d8ff45a2-19e3-413d-aa64-a9982bd6633c
description: 了解如何验证您的域，并在 Freenom for Microsoft 中为电子邮件、Skype for Business Online 和其他服务设置 DNS 记录。
ms.openlocfilehash: 39963b5c0f5f3f82fe193160e8aa8ab03894cedd
ms.sourcegitcommit: 5476c2578400894640ae74bfe8e93c3319f685bd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/06/2020
ms.locfileid: "44049031"
---
# <a name="create-dns-records-at-freenom-for-microsoft"></a>在 Freenom 处为 Microsoft 创建 DNS 记录

如果找不到您要查找的内容，[请检查域 FAQ](../setup/domains-faq.md) 。 
  
> [!CAUTION]
> Freenom 网站不支持 SRV 记录，这意味着多个 Skype for Business Online 和 Outlook Web App 功能将不起作用。 无论使用哪种 Microsoft 计划，都有显著的服务限制，您可能想要切换到其他 DNS 承载提供程序。 
  
如果考虑到服务限制，您可以选择在 Freenom 管理自己的 Microsoft DNS 记录，请按照本文中的步骤验证您的域并为电子邮件和其他服务设置 DNS 记录。
  
  
> [!NOTE]
> DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。 
  
## <a name="add-a-txt-record-for-verification"></a>添加 TXT 记录进行验证
<a name="bkmk_txt"> </a>

在将域用于 Microsoft 之前，必须确保你拥有该域。如果你能够在域注册机构处登录到你的帐户并创建 DNS 记录，便可向 Microsoft 证明你是域所有者。
  
> [!NOTE]
> 此记录仅用于验证您是否拥有自己的域；它不会影响其他任何内容。 如果需要，您可以以后将其删除。 
  
1. 若要开始，请使用[此链接](https://my.freenom.com/)转到 Freenom 中的 "域" 页面。 You'll be prompted to log in.
    
    ![Freenom 登录名](../../media/90a32855-bfdd-4dfe-881c-b9a36b2f0582.png)
  
2. 选择 "**服务**"，然后选择 **"我的域**"。
    
    ![Freenom 选择服务和我的域](../../media/1917ced2-e254-4aec-9096-46d339b84d9a.png)
  
3. 对于要编辑的域，选择 "**管理域**"。
    
    ![Freenom 选择管理域](../../media/67737b71-8b1b-42a6-abaf-62d776d3eb87.png)
  
4. 选择 "**管理 FREENOM DNS**"。
    
    ![Freenom 管理 Freenom DNS](../../media/9854a511-27e3-4658-8903-34b3d425096d.png)
  
5. 在 "**添加记录**" 下的 "**类型**" 列中，从菜单中选择 " **TXT** "。 
    
    ![Freenom 添加记录类型 TXT](../../media/7f0e85e7-844f-4962-815e-5d80d9e6efa0.png)
  
6. 在新记录的框中，键入或复制并粘贴下表中的值。 
    
    |**名称**|**Type**|**TTL**|**目标**|
    |:-----|:-----|:-----|:-----|
    |（保留为空白）  <br/> |TXT  <br/> |3600（秒）  <br/> |MS = msXXXXXXXX  <br/> **注意：** 这是一个示例。 在这里使用表中的特定“**目标地址或指向的地址**”值。           [如何查找此项？](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![用于验证的 Freenom TXT 值](../../media/650098df-b3aa-47e5-9763-7fde24e34c3f.png)
  
7. 选择 "**保存更改**"。
    
    ![Freenom TXT 记录保存更改](../../media/b1a63f9a-4578-491a-9554-c40f73b37e09.png)
  
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

1. 若要开始，请使用[此链接](https://my.freenom.com/)转到 Freenom 中的 "域" 页面。 You'll be prompted to log in.
    
    ![Freenom 登录名](../../media/90a32855-bfdd-4dfe-881c-b9a36b2f0582.png)
  
2. 选择 "**服务**"，然后选择 **"我的域**"。
    
    ![Freenom 选择服务和我的域](../../media/1917ced2-e254-4aec-9096-46d339b84d9a.png)
  
3. 对于要编辑的域，选择 "**管理域**"。
    
    ![Freenom 选择管理域](../../media/67737b71-8b1b-42a6-abaf-62d776d3eb87.png)
  
4. 将您的域的名称设置为默认的 Freenom 名称服务器。 选择 "**管理工具**"，然后选择 "**名称服务器**"。
    
    ![Freenom 名称服务器设置](../../media/a6ae877a-c248-42b9-bae9-210a80cd01e7.png)
  
5. 请确保已选择 "**使用默认名称服务器**"，然后选择 "**更改名称服务器**"。
    
    ![Freenom 更改名称服务器](../../media/0ef90d84-c0a0-4ef9-9e4c-43ef0aac3a2e.png)
  
6. 选择 "**管理 FREENOM DNS**"。
    
    ![Freenom select Manage Freenom DNS](../../media/f55a8053-2411-45da-a357-776c6699f721.png)
  
7. 在 "**添加记录**" 下的 "**类型**" 列中，从菜单中选择 " **MX** "。 
    
    ![Freenom 添加记录类型 MX](../../media/c728c6ee-786c-4f6a-8ad5-1d9914a5bfcf.png)
  
8. 在新记录的框中，键入或复制并粘贴下表中第一行的值。 
    
    |**名称**|**Type**|**TTL**|**目标**|**优先级**|
    |:-----|:-----|:-----|:-----|:-----|
    |（保留为空白）  <br/> |MX （邮件交换器）  <br/> |3600（秒）  <br/> |\<域密钥\>. mail.protection.outlook.com  <br/> **注意：** 从你的 Microsoft 帐户中获取你* \<的域密钥\> * 。   如何查找此内容？[](../get-help-with-domains/information-for-dns-records.md)          |10    <br/> 有关优先级的详细信息，请参阅[什么是 MX 优先级？](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) <br/> |
   
   ![Freenom MX 记录](../../media/8896c4a9-b3dd-45ed-9916-f7da2715ba8c.png)
  
9. 选择 "**保存更改**"。
    
    ![Freenom MX 记录保存更改](../../media/7aa0a464-d136-417f-be40-48d3f728eeb7.png)
  
10. 如果有任何其他 MX 记录，请将它们全部删除。 对于每个记录，选择 "**删除**"。 当**您确实要删除此条目时？** 出现时，选择 **"确定"**。
    
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a>添加 Microsoft 所需的 CNAME 记录
<a name="bkmk_cname"> </a>

1. 若要开始，请使用[此链接](https://my.freenom.com/)转到 Freenom 中的 "域" 页面。 You'll be prompted to log in.
    
    ![Freenom 登录名](../../media/90a32855-bfdd-4dfe-881c-b9a36b2f0582.png)
  
2. 选择 "**服务**"，然后选择 **"我的域**"。
    
    ![Freenom 选择服务和我的域](../../media/1917ced2-e254-4aec-9096-46d339b84d9a.png)
  
3. 对于要编辑的域，选择 "**管理域**"。
    
    ![Freenom 选择管理域](../../media/67737b71-8b1b-42a6-abaf-62d776d3eb87.png)
  
4. 选择 "**管理 FREENOM DNS**"。
    
    ![Freenom select Manage Freenom DNS](../../media/5e7bc3a7-0d5e-431b-bb27-da3b0f316d01.png)
  
5. 在 "**添加记录**" 下的 "**类型**" 列中，从菜单中选择 " **CNAME** "。 
    
    ![Freenom 添加记录类型 CNAME](../../media/9b204755-ca2a-46d2-bce2-030d82fd1f9e.png)
  
6. 创建第一个 CNAME 记录。 在新记录的框中，键入或复制并粘贴下表中第一行的值。 
    
    |**名称**|**记录类型**|**TTL**|**目标**|
    |:-----|:-----|:-----|:-----|
    |autodiscover  <br/> |CNAME  <br/> |3600（秒）  <br/> |autodiscover.outlook.com  <br/> |
    |sip  <br/> |CNAME  <br/> |3600（秒）  <br/> |sipdir.online.lync.com  <br/> |
    |lyncdiscover  <br/> |CNAME  <br/> |3600（秒）  <br/> |webdir.online.lync.com  <br/> |
    |enterpriseregistration  <br/> |CNAME  <br/> |3600（秒）  <br/> |enterpriseregistration.windows.net  <br/> |
    |enterpriseenrollment  <br/> |CNAME  <br/> |3600（秒）  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> |
   
    ![Freenom CNAME 值](../../media/752fc682-e3f2-4b9c-9253-bf1ba2d414e9.png)
  
7. 选择 "**保存更改**"。
    
    ![Freenom CNAME 保存更改](../../media/68103fd2-0f5f-4aac-a875-25157c6bbdd2.png)
  
8. 重复前面的步骤以创建其他五个 CNAME 记录。 
    
    对于每个记录，键入或复制并将上表中下一行的值粘贴到该记录的框中。
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>为 SPF 添加 TXT 记录以帮助防止垃圾邮件
<a name="bkmk_spf"> </a>

> [!IMPORTANT]
> 一个域所拥有的 SPF 的 TXT 记录不能超过一个。 如果域具有多个 SPF 记录，你将收到电子邮件错误，其中随附发送和垃圾邮件分类问题。 如果你的域已有 SPF 记录，请不要为 Microsoft 创建新记录。 改为将所需的 Microsoft 值添加到当前记录，以便您具有包含两组值的*单个*SPF 记录。 

1. 若要开始，请使用[此链接](https://my.freenom.com/)转到 Freenom 中的 "域" 页面。 You'll be prompted to log in.
    
    ![Freenom 登录名](../../media/90a32855-bfdd-4dfe-881c-b9a36b2f0582.png)
  
2. 选择 "**服务**"，然后选择 **"我的域**"。
    
    ![Freenom 选择服务和我的域](../../media/1917ced2-e254-4aec-9096-46d339b84d9a.png)
  
3. 对于要编辑的域，选择 "**管理域**"。
    
    ![Freenom 选择管理域](../../media/67737b71-8b1b-42a6-abaf-62d776d3eb87.png)
  
4. 选择 "**管理 FREENOM DNS**"。
    
    ![Freenom select Manage Freenom DNS](../../media/94809955-0315-409c-a15d-703a2fe4c4ed.png)
  
5. 在 "**添加记录**" 下的 "**类型**" 列中，从菜单中选择 " **TXT** "。 
    
    ![Freenom 添加记录类型 TXT](../../media/d8854285-c4ae-416c-a072-72a11ba1cd9a.png)
  
6. In the boxes for the new record, type or copy and paste the following values. 
    
    |**名称**|**记录类型**|**TTL**|**目标**|
    |:-----|:-----|:-----|:-----|
    |（保留为空白）  <br/> |TXT  <br/> |3600（秒）  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/>**注意：** 我们建议您复制并粘贴此条目，以保证正确保留所有空格。           |
   
    ![SPF 的 Freenom TXT 值](../../media/1b3b1199-9104-4ca1-acdb-786d139c21ac.png)
  
7. 选择 "**保存更改**"。
    
    ![SPF 保存更改的 Freenom TXT 记录](../../media/e2fc52b1-0dcb-4595-9a4c-fca5e2ef9f97.png)
  

