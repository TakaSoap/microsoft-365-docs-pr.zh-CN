---
title: 在 Microsoft 悬停时创建 DNS 记录
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
ms.assetid: 46ab4b10-6857-44b1-b08d-d1b5f45a69c6
description: 了解如何验证你的域并为 Microsoft 的悬停时设置电子邮件、Skype for Business Online 和其他服务的 DNS 记录。
ms.openlocfilehash: 4779b8f6fadcd4b134d3954d2c6c133da40c19e6
ms.sourcegitcommit: 5476c2578400894640ae74bfe8e93c3319f685bd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/06/2020
ms.locfileid: "44048983"
---
# <a name="create-dns-records-at-hover-for-microsoft"></a>在 Microsoft 悬停时创建 DNS 记录

 如果找不到要查找的内容，请**[查看域常见问题解答](../setup/domains-faq.md)**。 
  
如果悬停是您的 DNS 托管提供商，请按照本文中的步骤验证您的域并为电子邮件、Skype for Business Online 等设置 DNS 记录。
     
在悬停时添加这些记录后，您的域将设置为与 Microsoft 服务配合使用。
  

  
> [!NOTE]
>  DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。 
  
## <a name="add-a-txt-record-for-verification"></a>添加 TXT 记录进行验证
<a name="BKMK_verify"> </a>

在将域用于 Microsoft 之前，必须确保你拥有该域。如果你能够在域注册机构处登录到你的帐户并创建 DNS 记录，便可向 Microsoft 证明你是域所有者。
  
> [!NOTE]
> 此记录仅用于验证您是否拥有自己的域；它不会影响其他任何内容。 如果需要，您可以以后将其删除。 
  
请按下列步骤操作或[观看视频](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US)。
  
1. 若要开始，请使用[此链接](https://www.hover.com/domains)转到 Hover 上您的域页面。系统将会提示您首先登录。
    
    ![登录](../../media/f608cfaa-4962-46a1-a469-89010494e4be.png)
  
2. 在 "**管理您的域**" 下，选择要编辑的域的名称。
    
    ![选择域](../../media/ae7c1c46-7ad5-467a-b41c-077c90018989.png)
  
3. 选择 " **DNS** " 选项卡。 
    
    ![选择 "DNS" 选项卡](../../media/bd727fb4-0b06-426d-9387-42a160aead42.png)
  
4. 选择 "**添加新**"。
    
    ![选择 "添加新](../../media/66d6b2c9-741e-40e0-a096-6e7e204d655d.png)
  
5. In the boxes for the new record, select **TXT** for the **Record Type**, and then type or copy and paste the values from the following table.
    
    ||||
    |:-----|:-----|:-----|
    |主机名  <br/> |记录类型  <br/> |值  <br/> |
    |@  <br/> |TXT  <br/> |MS=ms *XXXXXXXX*  <br/> **注意：** 这是一个示例。 在这里使用表中的特定“**目标地址或指向的地址**”值。           [如何查找此项？](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![键入或复制并粘贴 DNS 值](../../media/3b0d19f9-4138-47a7-aab2-137ad120ded6.png)
  
6. 选择“保存”****。
    
    ![选择 "保存"](../../media/07dcf68e-34be-47dc-999e-0216de68cc9c.png)
  
7. 请在继续之前等待数分钟，以便您刚刚创建的记录可以通过 Internet 完成更新。
    
在域注册机构网站添加了记录后，你将返回到 Microsoft 365 并请求 Microsoft 365 查找记录。
  
Microsof 找到正确的 TXT 记录表明域已通过验证。
  
1. 在 Microsoft 管理中心，转到“**设置**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">域</a>”页面。
    
2. 在“**域**”页面上，选择要验证的域。 
    
    
  
3. 在“**设置**”页面上，选择“**开始设置**”。
    
    
  
4. 在“**验证域**”页面上，选择“**验证**”。
    
    
  
> [!NOTE]
>  DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>添加一条 MX 记录，确保发往你的域的电子邮件将会发送到 Microsoft
<a name="BKMK_add_MX"> </a>

请按下列步骤操作或[观看视频](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US)。
  
1. 若要开始，请使用[此链接](https://www.hover.com/domains)转到 Hover 上您的域页面。系统将会提示您首先登录。
    
    ![登录](../../media/f608cfaa-4962-46a1-a469-89010494e4be.png)
  
2. 在 "**管理您的域**" 下，选择要编辑的域的名称。
    
    ![选择域](../../media/ae7c1c46-7ad5-467a-b41c-077c90018989.png)
  
3. 选择 " **DNS** " 选项卡。 
    
    ![选择 "DNS" 选项卡](../../media/bd727fb4-0b06-426d-9387-42a160aead42.png)
  
4. 选择 "**添加新**"。
    
    ![选择 "添加新](../../media/66d6b2c9-741e-40e0-a096-6e7e204d655d.png)
  
5. 在新记录的框中，选择**记录类型**的 " **MX** "，然后键入或复制并粘贴下表中的值。
    
    |**主机名**|**记录类型**|**优先级**|**主机名**|
    |:-----|:-----|:-----|:-----|
    |@  <br/> |MX  <br/> |0  <br/> 有关优先级的详细信息，请参阅[什么是 MX 优先级？](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) <br/> | *\<域密钥\>*  .mail.protection.outlook.com  <br/> **注意：** 从你的 Microsoft 帐户中获取你* \<的域密钥\> * 。           [如何查找此项？](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![键入或复制并粘贴 DNS 值](../../media/2c8915fa-04a8-4d2a-a8ae-a79de0c8ef99.png)
  
6. 选择“保存”****。
    
    ![选择 "保存"](../../media/266c30a4-6703-48fb-a919-b510ed966193.png)
  
7. 如果有任何其他 MX 记录，请使用以下两步过程删除每个：
    
    首先，鼠标移要删除的记录，选择 "**删除**"。
    
    ![鼠标悬停并选择 "删除"](../../media/2ddf4902-8cd2-4969-a418-2cb592741e86.png)
  
    其次，选择 **"是"** 以确认每次删除。 
    
    ![选择 "是" 以确认删除](../../media/48756bd5-0205-4c4d-9803-9246795dbf4a.png)
  
    重复此过程，直到删除了之前在此过程中添加的 MX 记录之外的所有 MX 记录。
    
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a>添加 Microsoft 所需的 CNAME 记录
<a name="BKMK_add_CNAME"> </a>

请按下列步骤操作或[观看视频](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US)。
  
1. 若要开始，请使用[此链接](https://www.hover.com/domains)转到 Hover 上您的域页面。系统将会提示您首先登录。
    
    ![登录](../../media/f608cfaa-4962-46a1-a469-89010494e4be.png)
  
2. 在 "**管理您的域**" 下，选择要编辑的域的名称。
    
    ![选择域](../../media/ae7c1c46-7ad5-467a-b41c-077c90018989.png)
  
3. 选择 " **DNS** " 选项卡。 
    
    ![选择 "DNS" 选项卡](../../media/bd727fb4-0b06-426d-9387-42a160aead42.png)
  
4. 添加第一条 CNAME 记录（共 6 条）。
    
    选择 "**添加新**"。
    
    ![选择 "添加新](../../media/66d6b2c9-741e-40e0-a096-6e7e204d655d.png)
  
5. 在新记录的空框中，为**记录类型**选择 " **CNAME** "，然后键入或复制并粘贴下表中第一行的值。
    
    |**主机名**|**记录类型**|**目标主机**|
    |:-----|:-----|:-----|
    |autodiscover  <br/> |CNAME  <br/> |autodiscover.outlook.com  <br/> |
    |sip  <br/> |CNAME  <br/> |sipdir.online.lync.com  <br/> |
    |lyncdiscover  <br/> |CNAME  <br/> |webdir.online.lync.com  <br/> |
    |enterpriseregistration  <br/> |CNAME  <br/> |enterpriseregistration.windows.net  <br/> |
    |enterpriseenrollment  <br/> |CNAME  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> |
   
    ![键入或复制并粘贴 DNS 值](../../media/6ae607f8-d26e-47f0-a0f2-3487d37e8c7f.png)
  
6. 选择“保存”****。
    
    ![选择 "保存"](../../media/69aa3546-32de-4c17-a2e2-8c0cd133efaa.png)
  
7. 使用前面的三个步骤和表中其他五行中的值，添加其他五个 CNAME 记录中的每个。
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>为 SPF 添加 TXT 记录以帮助防止垃圾邮件
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> 一个域所拥有的 SPF 的 TXT 记录不能超过一个。 如果域具有多个 SPF 记录，你将收到电子邮件错误，其中随附发送和垃圾邮件分类问题。 如果你的域已有 SPF 记录，请不要为 Microsoft 创建新记录。 改为将所需的 Microsoft 值添加到当前记录，以便您具有包含两组值的*单个*SPF 记录。 
  
请按下列步骤操作或[观看视频](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US)。
  
1. 若要开始，请使用[此链接](https://www.hover.com/domains)转到 Hover 上您的域页面。系统将会提示您首先登录。
    
    ![登录](../../media/f608cfaa-4962-46a1-a469-89010494e4be.png)
  
2. 在 "**管理您的域**" 下，选择要编辑的域的名称。
    
    ![选择域](../../media/ae7c1c46-7ad5-467a-b41c-077c90018989.png)
  
3. 选择 " **DNS** " 选项卡。 
    
    ![选择 "DNS" 选项卡](../../media/bd727fb4-0b06-426d-9387-42a160aead42.png)
  
4. 选择 "**添加新**"。
    
    ![选择 "添加新](../../media/66d6b2c9-741e-40e0-a096-6e7e204d655d.png)
  
5. In the boxes for the new record, select **TXT** for the **Record Type**, and then type or copy and paste the values from the following table.
    
    |**主机名**|**记录类型**|**值**|
    |:-----|:-----|:-----|
    |@  <br/> |TXT  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/>**注意：** 我们建议您复制并粘贴此条目，以保证正确保留所有空格。           |
   
    ![键入或复制并粘贴 DNS 值](../../media/ed36b9e0-aaa9-45fb-804d-7d4e82ba0c7f.png)
  
6. 选择“保存”****。
    
    ![选择 "保存"](../../media/13a395b9-e0e8-4393-b568-5f99b2da39da.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>添加 Microsoft 所需的两条 SRV 记录
<a name="BKMK_add_SRV"> </a>

请按下列步骤操作或[观看视频](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US)。
  
1. 若要开始，请使用[此链接](https://www.hover.com/domains)转到 Hover 上您的域页面。系统将会提示您首先登录。
    
    ![登录](../../media/f608cfaa-4962-46a1-a469-89010494e4be.png)
  
2. 在 "**管理您的域**" 下，选择要编辑的域的名称。
    
    ![选择域](../../media/ae7c1c46-7ad5-467a-b41c-077c90018989.png)
  
3. 选择 " **DNS** " 选项卡。 
    
    ![选择 "DNS" 选项卡](../../media/bd727fb4-0b06-426d-9387-42a160aead42.png)
  
4. 添加两条 SRV 记录中的第一条记录。
    
    选择 "**添加新**"。
    
    ![选择 "添加新](../../media/66d6b2c9-741e-40e0-a096-6e7e204d655d.png)
  
5. 在新记录的空框中，为**记录类型**选择 " **SRV** "，然后键入或复制并粘贴下表中第一行的值。
    
    |**主机名**|**记录类型**|**优先级**|**权重**|**端口**|**目标**|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |_sip _tls  <br/> |SRV  <br/> |100  <br/> |1  <br/> |443  <br/> |sipdir.online.lync.com  <br/> |
    |_sipfederationtls _tcp  <br/> |SRV  <br/> |100  <br/> |1  <br/> |5061  <br/> |sipfed.online.lync.com  <br/> |
   
    ![键入或复制并粘贴 DNS 值](../../media/67562cd6-c598-4c37-af53-626f153c0197.png)
  
6. 选择“保存”****。
    
    ![选择 "保存"](../../media/0d7ec216-9277-4709-b637-e94c8662730f.png)
  
7. 使用前面的三个步骤和表中第二行的值，添加另一条 SRV 记录。
    
> [!NOTE]
> DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。 
  
