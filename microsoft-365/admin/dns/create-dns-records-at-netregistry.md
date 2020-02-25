---
title: 在 Netregistry 上为 Office 365 创建 DNS 记录
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
- BEA160
ms.assetid: 48e09394-2287-4b3c-9853-21eadf61277e
description: 了解如何在 Netregistry for Office 365 中验证您的域并为电子邮件、Skype for Business Online 和其他服务设置 DNS 记录。
ms.openlocfilehash: de4e16fa20f950edef8d30b4c6d02214e3753b9c
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/24/2020
ms.locfileid: "42251038"
---
# <a name="create-dns-records-at-netregistry-for-office-365"></a>在 Netregistry 上为 Office 365 创建 DNS 记录

如果找不到要查找的内容，请[查看域常见问题解答](../setup/domains-faq.md)。 
  
如果 Netregistry 是您的 DNS 托管提供商，请按照本文中的步骤验证您的域并为电子邮件、Skype for Business Online 等设置 DNS 记录。
  
下面是要添加的主要记录：
  
- [添加 TXT 记录进行验证](#add-a-txt-record-for-verification)
    
- [添加一条 MX 记录，确保发往您的域的电子邮件发送到 Office 365](#add-an-mx-record-so-email-for-your-domain-will-come-to-office-365)

- [添加 Office 365 所需的 CNAME 记录](#add-the-cname-records-that-are-required-for-office-365)
    
- [为 SPF 添加 TXT 记录以帮助防止垃圾邮件](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [添加 Office 365 所需的两条 SRV 记录](#add-the-two-srv-records-that-are-required-for-office-365)
    
在 Netregistry 中添加这些记录后，您的域将设置为与 Office 365 服务配合使用。
  
若要了解如何与 Office 365 结合使用网站的 Web 宿主和 DNS，请参阅[配合使用公共网站与 Office 365](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx)。
  
> [!NOTE]
> DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。 
  
## <a name="add-a-txt-record-for-verification"></a>添加 TXT 记录进行验证
<a name="bkmk_txt"> </a>

在将域用于 Office 365 之前，必须确保你拥有该域。如果你能够在域注册机构处登录到你的帐户并创建 DNS 记录，便可向 Office 365 证明你是所有者。
  
> [!NOTE]
> 此记录仅用于验证您是否拥有自己的域；它不会影响其他任何内容。 如果需要，您可以以后将其删除。 
  
1. 若要开始，请使用[此链接](https://theconsole.netregistry.com.au/)转到 Netregistry 中的 "域" 页面。 You'll be prompted to log in.
    
    ![Netregistry_login](../media/ed3c785f-01c3-49e7-affd-c04637c0ffe9.png)
  
2. 在要管理的域旁边，选择 "**管理**"。
    
    ![Netregistry_Manage](../media/64ad542a-5ec4-4148-96f8-d6e163449352.png)
  
3. 选择 "**区域管理器**"。
    
    ![Netregistry_selectZoneManager](../media/e18c32f9-c1e7-4aa2-9aa6-8dc9c5ea44af.png)
  
4. 在 "**添加区域记录**" 下，从列表中选择 " **TXT 记录**"，然后选择 "**创建新记录**"。
    
    ![Netregistry_TXT_select](../media/eb1761e6-9deb-4631-8deb-bc5d09926722.png)
  
    > [!NOTE]
    > 必须在 TXT 框中的条目前后使用引号。 
  
    在 "**新建 TXT 记录**" 表单中，键入或复制并粘贴下表中的值。 
    
    |**名称**|**TTL （秒）**|**TXT （指向 "地址" 或 "值"）**|
    |:-----|:-----|:-----|
    |（保留为空白）  <br/> |3600（秒）  <br/> |"MS = msXXXXXXXX"  <br/> **注意：** 这是一个示例。 在这里使用来自 Office 365 中的表的特定" **目标或指向的地址**"值。 [如何查找此内容？](../get-help-with-domains/information-for-dns-records.md)  |
       
    ![Netregistry_verificationTXTvalues](../media/cfe8b05a-fa8b-4dba-9554-7a3466e6c012.png)
  
6. 选择 "**添加记录**"。
    
Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.
  
When Office 365 finds the correct TXT record, your domain is verified.
  
1. 在管理中心中，转到 "**设置** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">域</a>" 页。
    
2. 在 "**域**" 页上，选择要验证的域。 
    
    
  
3. 在 "**设置**" 页上，选择 "**启动安装程序**"。
    
    
  
4. 在 "**验证域**" 页上，选择 "**验证**"。
    
    
  
> [!NOTE]
>  DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a>添加一条 MX 记录，确保发往您的域的电子邮件发送到 Office 365
<a name="bkmk_mx"> </a>

1. 若要开始，请使用[此链接](https://theconsole.netregistry.com.au/)转到 Netregistry 中的 "域" 页面。 You'll be prompted to log in.
    
    ![Netregistry_login](../media/80277b0e-547e-4635-aa6a-5d8ebe3fba85.png)
  
2. 在要管理的域旁边，选择 "**管理**"。
    
    ![Netregistry_Manage](../media/96e2c6e4-21fd-4405-a4fe-b1188400b985.png)
  
3. 选择 "**区域管理器**"。
    
    ![Netregistry_selectZoneManager](../media/914021f6-dff3-4640-84d6-b83cf8f61cf1.png)
  
4. 在 "**当前区域记录**" 下，选择列表中每条 MX 记录旁边的 "**删除**"，删除默认的 MX 记录。 
    
    ![Netregistry_MX_remove](../media/494670a9-8b8d-46e5-8136-05e82212a115.png)
  
5. 在 "**添加区域记录**" 下，从列表中选择 " **MX 记录**"，然后选择 "**创建新记录**"。
    
    ![Netregistry_MX_select](../media/29b60eb9-6c40-490f-9669-e65b65962f37.png)
  
6. 在 "**新建 MX 记录**" 表单中，键入或复制并粘贴下表中的值。 
    
    |**名称**|**TTL （秒）**|**Exchange （指向 "地址" 或 "值"）**|**主机是否处于完全限定状态？**|**首选项（优先级）**|
    |:-----|:-----|:-----|:-----|:-----|
    |（保留为空白）  <br/> |3600（秒）  <br/> | *\<域密钥\>*  .mail.protection.outlook.com  <br/> **注意：** 从 Office 365 帐户中获取你* \<的域密钥\> * 。  [如何查找此内容？](../get-help-with-domains/information-for-dns-records.md)      |（选中 "" 复选框）  <br/> |10   <br/> For more information about priority, see What is MX priority?  <br/> |
       
    ![Netregistry_MX_values](../media/518b3da6-4055-4e2d-b5ce-44a0fee25419.png)
  
7. 选择 "**添加记录**"。
    
    ![Netregistry_MX_values_AddRecord](../media/8194cb38-afa0-48ac-831c-fd34b6ad652e.png)
  
## <a name="add-the-cname-records-that-are-required-for-office-365"></a>添加 Office 365 所需的 CNAME 记录
<a name="bkmk_cname"> </a>

1. 若要开始，请使用[此链接](https://theconsole.netregistry.com.au/)转到 Netregistry 中的 "域" 页面。 You'll be prompted to log in.
    
    ![Netregistry_login](../media/cbf83dce-86d2-4008-9400-56def4b6fcd7.png)
  
2. 在要管理的域旁边，选择 "**管理**"。
    
    ![Netregistry_Manage](../media/7bee4b0f-2c1d-43ca-b1bb-9b889ca0c5e4.png)
  
3. 选择 "**区域管理器**"。
    
    ![Netregistry_selectZoneManager](../media/58384add-0a9d-472b-a5d0-51ec8155fd41.png)
  
4. 在 "**添加区域记录**" 下，从列表中选择 " **CNAME 记录**"，然后选择 "**创建新记录**"。
    
    ![Netregistry_CNAME_CreateNewRecord](../media/7b4f133f-45da-48da-93c0-62f57c786165.png)
  
5. In the boxes for the new record, type or copy and paste the values from the following table.
    
    |**名称**|**Type**|**TTL**|**主机（指向或地址值）**|
    |:-----|:-----|:-----|:-----|
    |autodiscover  <br/> |CNAME  <br/> |3600（秒）  <br/> |autodiscover.outlook.com  <br/> |
    |sip  <br/> |CNAME  <br/> |3600（秒）  <br/> |sipdir.online.lync.com  <br/> |
    |lyncdiscover  <br/> |CNAME  <br/> |3600（秒）  <br/> |webdir.online.lync.com  <br/> |
    |enterpriseregistration  <br/> |CNAME  <br/> |3600（秒）  <br/> |enterpriseregistration.windows.net  <br/> |
    |enterpriseenrollment  <br/> |CNAME  <br/> |3600（秒）  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> |
       
    ![Netregistry_CNAME_values](../media/93c479f0-3ce2-491a-9113-6dde1cd7131b.png)
      
6. 选择 "**添加记录**"。
    
    ![Netregistry_CNAME_values_AddRecord](../media/046c8c64-ea71-4530-9fc6-69f0c70993b6.png)
  
7. 重复前面的步骤以创建其他五个 CNAME 记录。
    
    对于每个记录，键入或复制并将上表中下一行的值粘贴到该记录的框中。
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>为 SPF 添加 TXT 记录以帮助防止垃圾邮件
<a name="bkmk_spf"> </a>

> [!IMPORTANT]
> You cannot have more than one TXT record for SPF for a domain. If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues. If you already have an SPF record for your domain, don't create a new one for Office 365. 改为将所需的 Office 365 值添加到当前记录，以便您具有包含两组值的*单个*SPF 记录。
  
1. 若要开始，请使用[此链接](https://theconsole.netregistry.com.au/)转到 Netregistry 中的 "域" 页面。 You'll be prompted to log in.
    
    ![Netregistry_login](../media/a841f11f-1c0f-4926-acea-a2b8bb083984.png)
  
2. 在要管理的域旁边，选择 "**管理**"。
    
    ![Netregistry_Manage](../media/4245bbbb-4e2d-49e7-a89c-679949aa3d18.png)
  
3. 选择 "**区域管理器**"。
    
    ![Netregistry_selectZoneManager](../media/372e5918-b6dc-4268-8f9a-0aa71d65deef.png)
  
4. 在 "**添加区域记录**" 下，从列表中选择 " **TXT 记录**"，然后选择 "**创建新记录**"。
    
    ![Netregistry_TXT_select](../media/a2930d03-853a-4f1e-9205-d00f25bed35f.png)
  
5. In the boxes for the new record, type or copy and paste the values from the following table. 
    
    > [!NOTE]
    > 必须在 TXT 框中的条目前后使用引号。 
  
    |**名称**|**Type**|**TTL**|**TXT 数据（目标）**|
    |:-----|:-----|:-----|:-----|
    |（保留为空白）  <br/> |TXT  <br/> |3600（秒）  <br/> |"v = spf1 包括 include spf.protection.outlook.com-all"  <br/> **注意：** 我们建议您复制并粘贴此条目，以确保所有的间距保持正确。           |
   
    ![Netregistry_SPF TXTvalues](../media/a369345a-d774-48bc-8160-b628ab8247f9.png)
  
6. 选择 "**添加记录**"。
    
    ![Netregistry_SPF TXTvalues_AddRecord](../media/063bfbaf-940a-489f-970f-29c026b4b312.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a>添加 Office 365 所需的两条 SRV 记录
<a name="bkmk_srv"> </a>

1. 若要开始，请使用[此链接](https://theconsole.netregistry.com.au/)转到 Netregistry 中的 "域" 页面。 You'll be prompted to log in.
    
    ![Netregistry_login](../media/accf6584-e5f4-4d68-a641-0f8847f8370f.png)
  
2. 在要管理的域旁边，选择 "**管理**"。
    
    ![Netregistry_Manage](../media/e0ddc79e-0123-4e24-8380-9645bdb41aac.png)
  
3. 选择 "**区域管理器**"。
    
    ![Netregistry_selectZoneManager](../media/f122888b-3cc5-40ec-adac-0ede04799d9a.png)
  
4. 在 "**添加区域记录**" 下，从列表中选择 " **SRV 记录**"，然后选择 "**创建新记录**"。
    
    ![Netregistry_SRV_select](../media/e5dab850-acd1-48b8-8b4a-e3b9777cf508.png)
  
5. In the boxes for the new record, type or copy and paste the values from the following table.
    
    > [!NOTE]
    > "名称" 字段是服务（例如，_sip）和协议（例如，_tls）的组合。 
  
    |**类型**|**名称**|**TTL （秒）**|**优先级**|**权重**|**端口**|**目标**|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |SRV （服务）  <br/> |_sip _tls  <br/> |3600（秒）  <br/> |100  <br/> |1  <br/> |443  <br/> |sipdir.online.lync.com  <br/> |
    |SRV （服务）  <br/> |_sipfederationtls _tcp  <br/> |3600（秒）  <br/> |100  <br/> |1  <br/> |5061  <br/> |sipfed.online.lync.com  <br/> |
       
    ![Netregistry_SRV_values](../media/49292846-1598-4b8c-9940-db6e10675753.png)
  
6. 选择 "**添加记录**"。
    
    ![Netregistry_SRV_values_AddRecord](../media/abc82061-939f-4757-87e4-0e8f9e43ebcb.png)
  
7. 重复前面的步骤以创建其他 SRV 记录。
    
    将上表中第二行的值键入或复制并粘贴到第二条记录的框中。
    
> [!NOTE]
> DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。 
  

