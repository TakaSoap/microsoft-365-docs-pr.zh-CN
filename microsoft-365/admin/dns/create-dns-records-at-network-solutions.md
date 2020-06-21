---
title: 在 Microsoft 的网络解决方案中创建 DNS 记录
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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 1dc55f9f-5309-450f-acc3-b2b4119c8be3
description: 了解如何在 Microsoft 的网络解决方案中验证您的域并为电子邮件、Skype for Business Online 和其他服务设置 DNS 记录。
ms.openlocfilehash: 25e85bf30527b49ada711af9ba5c418409acd24c
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/17/2020
ms.locfileid: "44780333"
---
# <a name="create-dns-records-at-network-solutions-for-microsoft"></a>在 Microsoft 的网络解决方案中创建 DNS 记录

 如果找不到要查找的内容，请**[查看域常见问题解答](../setup/domains-faq.md)**。 
  
如果网络解决方案是您的 DNS 托管提供商，请按照本文中的步骤验证您的域并为电子邮件、Skype for Business Online 等设置 DNS 记录。
  
下面是要添加的主要记录。 请按下列步骤操作或[观看视频](https://support.microsoft.com/office/c49698c2-6991-47fb-b5ac-18e49a505099)。 
  
- [添加 TXT 记录进行验证](#add-a-txt-record-for-verification)
    
- [添加一条 MX 记录，确保发往你的域的电子邮件将会发送到 Microsoft](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft)
    
- [添加 Microsoft 所需的 CNAME 记录](#add-the-cname-records-that-are-required-for-microsoft)
    
- [为 SPF 添加 TXT 记录以帮助防止垃圾邮件](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [添加 Microsoft 所需的两条 SRV 记录](#add-the-two-srv-records-that-are-required-for-microsoft)
    
在网络解决方案中添加这些记录后，您的域将设置为与 Microsoft 服务配合使用。
  

  
> [!NOTE]
>  Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-a-txt-record-for-verification"></a>添加 TXT 记录进行验证
<a name="BKMK_verify"> </a>

Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.
  
> [!NOTE]
> This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like. 
  
请按下列步骤操作或[观看视频（从 0:47 开始）](https://support.microsoft.com/office/c49698c2-6991-47fb-b5ac-18e49a505099)。
  
1. To get started, go to your domains page at Network Solutions by using [this link](https://www.networksolutions.com/manage-it). You'll be prompted to log in.
    
    > [!IMPORTANT]
    > 在选择 "**登录**" 按钮之前，先在 "**登录到：** " 下拉列表中选择 **"管理我的域名**"。 
  
    ![选择'管理我的域名'并登录到 Network Solutions](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. 选择要修改的域名称旁边的复选框。
    
    ![选择域的复选框](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. 选择 "**编辑 DNS**"。
    
    ![选择 "编辑 DNS"](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. 选择 "**管理高级 DNS 记录**"。
    
    (You may have to scroll down.)
    
    ![选择 "管理高级 DNS 记录"](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. 向下滚动到 "**文本（TXT 记录）** " 部分，然后选择 "**编辑 TXT 记录**"。
    
    ![选择 "编辑 TXT 记录"](../../media/240a01d6-750a-4da6-8554-641b571e4b71.png)
  
6. 在新记录的框中，键入或复制并粘贴下表中的值。
    
    |**主机**|**TTL**|**文本**|
    |:-----|:-----|:-----|
    |@  <br/> (The system will change this value to **@ (None)** when you save the record.)  <br/> |3600  <br/> |MS=ms *XXXXXXXX*  <br/> **注意：** 这是一个示例。 在这里使用表中的特定“**目标地址或指向的地址**”值。  [如何查找此项？](../get-help-with-domains/information-for-dns-records.md)   |
       
    ![在新记录的框中键入或粘贴值](../../media/8a76daab-b6ff-4c82-ba68-192b24fbb934.png)
  
7. 选择 "**继续**"。
    
    ![选择 "继续"](../../media/89e7fb38-b4d9-4949-a1bb-d0dd10b361e0.png)
  
8. 选择 "**保存更改**"。
    
    ![选择 "保存更改"](../../media/bd4d7cd0-c8a3-497a-b080-cfd5a5c60dc5.png)
  
9. 请在继续之前等待数分钟，以便您刚刚创建的记录可以通过 Internet 完成更新。
    
在在域注册机构网站添加了记录后，你将返回到 Microsoft 并请求记录。
  
Microsof 找到正确的 TXT 记录表明域已通过验证。

1. 在管理中心，转到“**设置**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">域</a>”页面。
    
2. 在“**域**”页面上，选择要验证的域。 
    
    
  
3. 在“**设置**”页面上，选择“**开始设置**”。
    
    
  
4. 在“**验证域**”页面上，选择“**验证**”。
    
    
  
> [!NOTE]
>  Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>添加一条 MX 记录，确保发往你的域的电子邮件将会发送到 Microsoft
<a name="BKMK_add_MX"> </a>

请执行以下步骤或[观看视频（从3:51 开始）](https://support.microsoft.com/office/c49698c2-6991-47fb-b5ac-18e49a505099)。
  
1. 若要开始，请使用[此链接](https://www.networksolutions.com/manage-it)转到 Network Solutions 上你的域页面。 系统将会提示您登录。
    
    > [!IMPORTANT]
    > 在选择 "**登录**" 按钮之前，先在 "**登录到：** " 下拉列表中选择 **"管理我的域名**"。 
  
    ![选择'管理我的域名'并登录到 Network Solutions](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. 选择要修改的域名称旁边的复选框。
    
    ![选择域的复选框](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. 选择 "**编辑 DNS**"。
    
    ![选择 "编辑 DNS"](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. 选择 "**管理高级 DNS 记录**"。
    
    (You may have to scroll down.)
    
    ![选择 "管理高级 DNS 记录"](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. 向下滚动到 "**邮件服务器（MX 记录）** " 部分，然后选择 "**编辑 MX 记录**"。
    
    ![选择 "编辑 MX 记录"](../../media/74b4e412-9073-4d2d-8710-fe340b223798.png)
  
6. 在新记录的框中，键入或复制并粘贴下表中的值。
    
    |**Priority**|**TTL**|**邮件服务器**|
    |:-----|:-----|:-----|
    |10    <br/> 有关优先级的详细信息，请参阅[什么是 MX 优先级？](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) <br/> |3600  <br/> | *\<domain-key\>*. mail.protection.outlook.com。  <br/> **This value MUST end with a period (.)** <br/> **注意：***\<domain-key\>* 从你的 Microsoft 帐户获取你的。 [如何查找此项？](../get-help-with-domains/information-for-dns-records.md)          |
       
    ![在新记录的框中键入或粘贴值](../../media/0bb96872-cc6e-4dfa-a649-fb7efbbf0012.png)
  
7. 选择 "**继续**"。
    
    ![选择 "继续"](../../media/963f758b-e79d-4452-8340-7eba8a3972c9.png)
  
8. 选择 "**保存更改**"。
    
    ![选择 "保存更改"](../../media/7c2f784a-6dee-4364-866c-ad7202ef1fc2.png)
  
9. 如果有任何其他 MX 记录，请通过选择每条记录的 "**删除**" 来删除所有这些记录。 
    
    ![选中其他 MX 记录的 "删除" 复选框](../../media/709d6133-9f5d-490a-a91e-95e21ca94695.png)
  
10. 选择所有选项后，选择 "**继续**"。
    
    ![选择 "继续"](../../media/4710f988-0bbc-4ba7-bf31-ca2392b2900e.png)
  
11. 选择 "**保存更改**"。
    
    ![选择 "保存更改"](../../media/24432ec6-666b-4612-9488-37c06437959b.png)
  
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a>添加 Microsoft 所需的 CNAME 记录
<a name="BKMK_add_CNAME"> </a>

请执行以下步骤或[观看视频（从4:43 开始）](https://support.microsoft.com/office/c49698c2-6991-47fb-b5ac-18e49a505099)。
  
1. 若要开始，请使用[此链接](https://www.networksolutions.com/manage-it)转到 Network Solutions 上你的域页面。 系统将会提示您登录。
    
    > [!IMPORTANT]
    > 在选择 "**登录**" 按钮之前，先在 "**登录到：** " 下拉列表中选择 **"管理我的域名**"。 
  
    ![选择'管理我的域名'并登录到 Network Solutions](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. 选择要修改的域名称旁边的复选框。
    
    ![选择域的复选框](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. 选择 "**编辑 DNS**"。
    
    ![选择 "编辑 DNS"](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. 选择 "**管理高级 DNS 记录**"。
    
    (You may have to scroll down.)
    
    ![选择 "管理高级 DNS 记录"](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. 向下滚动到 "**主机别名（CNAME 记录）** " 部分，然后选择 "**编辑 CNAME 记录**"。
    
    ![选择 "在主机别名下编辑 CNAME 记录"](../../media/2d0a4666-8d40-48f4-886c-64a5157baaf5.png)
  
6. 在四个新记录的框中，键入或复制并粘贴下表中的值。
    
    |**Alias**|**TTL**|**引用主机名**|**其他主机（选择 "**其他主机**" 选项按钮）**|
    |:-----|:-----|:-----|:-----|
    |自动发现  <br/> |3600  <br/> |（无设置）  <br/> |autodiscover.outlook.com。  <br/> **This value MUST end with a period (.)** <br/> |
    |sip  <br/> |3600  <br/> |（无设置）  <br/> |sipdir.online.lync.com。  <br/> **此值必须以句点 (.) 结尾。** <br/> |
    |lyncdiscover  <br/> |3600  <br/> |（无设置）  <br/> |webdir.online.lync.com。  <br/> **This value MUST end with a period (.)** <br/> |
    |enterpriseregistration  <br/> |3600  <br/> |（无设置）  <br/> |EnterpriseRegistration.windows.net  <br/> **此值必须以句点 (.) 结尾。** <br/> |
    |enterpriseenrollment  <br/> |3600  <br/> |（无设置）  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> **This value MUST end with a period (.)** <br/> |
    
    ![为新记录键入或粘贴值](../../media/5ce0b30c-b46c-4778-aa5a-fb5e2f0961c1.png)
  
7. 添加完所需的所有 CNAME 记录后，选择 "**继续**"。
    
    ![选择 "继续"](../../media/4978bd8b-f6a6-458d-9522-ad612b301c4a.png)
  
8. 选择 "**保存更改**"。
    
    ![选择 "保存更改"](../../media/f005c38a-0d8d-4c61-bec6-15e60c89aa5a.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>为 SPF 添加 TXT 记录以帮助防止垃圾邮件
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> 一个域所拥有的 SPF 的 TXT 记录不能超过一个。 如果域具有多个 SPF 记录，你将收到电子邮件错误，其中随附发送和垃圾邮件分类问题。 如果你的域已有 SPF 记录，请不要为 Microsoft 创建新记录。 改为将所需的 Microsoft 值添加到当前记录，以便您具有包含两组值的*单个*SPF 记录。 
  
请执行以下步骤或[观看视频（从5:35 开始）](https://support.microsoft.com/office/c49698c2-6991-47fb-b5ac-18e49a505099)。
  
1. 若要开始，请使用[此链接](https://www.networksolutions.com/manage-it)转到 Network Solutions 上你的域页面。 系统将会提示您登录。
    
    > [!IMPORTANT]
    > 在选择 "**登录**" 按钮之前，先在 "**登录到：** " 下拉列表中选择 **"管理我的域名**"。 
  
    ![选择'管理我的域名'并登录到 Network Solutions](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. 选择要修改的域名称旁边的复选框。
    
    ![选择域的复选框](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. 选择 "**编辑 DNS**"。
    
    ![选择 "编辑 DNS"](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. 选择 "**管理高级 DNS 记录**"。
    
    (You may have to scroll down.)
    
    ![选择 "管理高级 DNS 记录"](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. 向下滚动到 "**文本（TXT 记录）** " 部分，然后选择 "**编辑 TXT 记录**"。
    
    ![选择 "文本" 下的 "编辑 TXT 记录"](../../media/a69a2631-6da2-4e81-99ab-9a9ab9b30b07.png)
  
6. In the boxes for the new record, type or copy and paste the following values.
    
    |**主机**|**TTL**|**文本**|
    |:-----|:-----|:-----|
    |@  <br/> (The system will change this value to **@ (None)** when you save the record.)  <br/> |3600  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **注意：** 我们建议您复制并粘贴此条目，以保证正确保留所有空格。 |
       
    ![为新记录键入或粘贴值](../../media/11564eca-e2ee-4f17-af2b-a00eb7c157db.png)
  
7. 选择 "**继续**"。
    
    ![选择 "继续"](../../media/482a8dae-0c79-47c4-8bd8-87965683de24.png)
  
8. 选择 "**保存更改**"。
    
    ![选择 "保存更改"](../../media/600b8c6d-184f-4213-a50e-8f119ebf3ff0.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>添加 Microsoft 所需的两条 SRV 记录
<a name="BKMK_add_SRV"> </a>

请执行以下步骤或[观看视频（从6:18 开始）](https://support.microsoft.com/office/c49698c2-6991-47fb-b5ac-18e49a505099)。
  
1. 若要开始，请使用[此链接](https://www.networksolutions.com/manage-it)转到 Network Solutions 上你的域页面。 系统将会提示您登录。
    
    > [!IMPORTANT]
    > 在选择 "**登录**" 按钮之前，先在 "**登录到：** " 下拉列表中选择 **"管理我的域名**"。 
  
    ![选择'管理我的域名'并登录到 Network Solutions](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. 选择要修改的域名称旁边的复选框。
    
    ![选择域的复选框](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. 选择 "**编辑 DNS**"。
    
    ![选择 "编辑 DNS"](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. 选择 "**管理高级 DNS 记录**"。
    
    (You may have to scroll down.)
    
    ![选择 "管理高级 DNS 记录"](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. 向下滚动到 "**服务（SRV 记录）** " 部分，然后选择 "**编辑 SRV 记录**"。
    
    ![选择 "服务" 下的 "编辑 SRV 记录"](../../media/9a9248ea-5de5-4e16-9364-f7600fa371f5.png)
  
6. 在两个新记录的框中，键入或复制并粘贴下表中的值。
    
    （从下拉列表中选择 "**服务**" 和 "**协议**" 值。） 
    
    |**服务**|**协议**|**TTL**|**优先级**|**权重**|**端口**|**目标**|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |_sip  <br/> |_tls  <br/> |3600  <br/> |100  <br/> |1   <br/> |443  <br/> |sipdir.online.lync.com。  <br/> **This value MUST end with a period (.)** <br/> |
    |_sipfederationtls  <br/> |_tcp  <br/> |3600  <br/> |100  <br/> |1   <br/> |5061  <br/> |sipfed.online.lync.com。  <br/> **此值必须以句点 (.) 结尾。** <br/> |
       
    ![为新记录键入或粘贴值](../../media/86968d1c-8e43-4e61-aeaa-37fc7d7ef7a7.png)
  
7. 选择 "**继续**"。
    
    ![选择 "继续"](../../media/bfe2c778-5d2b-4bb6-a79d-c3ff9caf9e1e.png)
  
8. 选择 "**保存更改**"。
    
    ![选择 "保存更改"](../../media/6d323126-0ebe-45ab-8567-c234711d84c7.png)
  
> [!NOTE]
>  Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md). 
  
