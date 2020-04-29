---
title: 在 Bluehost 处为 Microsoft 创建 DNS 记录
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
ms.assetid: 657934ff-d9d2-4563-9ccf-ef4832a03a99
description: 了解如何验证您的域，并在 Bluehost for Microsoft 中为电子邮件、Skype for Business Online 和其他服务设置 DNS 记录。
ms.openlocfilehash: 1608aebdf984e22e45d7a2469acb0a8002fca2a1
ms.sourcegitcommit: 2399ee6f9bc955cf8f2a76c01fc84c19eb37ff42
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2020
ms.locfileid: "43919547"
---
# <a name="create-dns-records-at-bluehost-for-microsoft"></a>在 Bluehost 处为 Microsoft 创建 DNS 记录

 如果找不到要查找的内容，请**[查看域常见问题解答](../setup/domains-faq.md)**。 
  
如果 Bluehost 是您的 DNS 托管提供商，请按照本文中的步骤验证您的域并为电子邮件、Skype for Business Online 等设置 DNS 记录。
  
在 Bluehost 中添加这些记录后，您的域将设置为与 Microsoft 服务一起使用。
  
若要了解如何与 Microsoft 结合使用网站的 Web 宿主和 DNS，请参阅[配合使用公共网站与 Microsoft](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9)。
  
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果在添加 DNS 记录后遇到邮件流问题或其他问题，请参阅[查找在添加域或 DNS 记录后遇到的问题并进行修复](../get-help-with-domains/find-and-fix-issues.md)。 
  
## <a name="add-a-txt-record-for-verification"></a>添加 TXT 记录进行验证
<a name="BKMK_verify"> </a>

在将域用于 Microsoft 之前，必须确保你拥有该域。如果你能够在域注册机构处登录到你的帐户并创建 DNS 记录，便可向 Microsoft 证明你是域所有者。
  
> [!NOTE]
> 此记录仅用于验证您是否拥有自己的域；它不会影响其他任何内容。 如果需要，您可以以后将其删除。 
  
1. 要开始，请使用[此链接](https://my.bluehost.com/cgi/dm)转到您在 Bluehost 上的域页面。 系统将会提示您先登录。
    
2. 在" **域**"页面上的" **域**"区域中，找到你要更改的域所在的行，然后选中该域对应的复选框。 
    
    （您可能需要向下滚动。）
    
3. 在 " ***domain_name*** " 区域的 " **DNS 区域编辑器**" 行中，选择 "**管理 DNS 记录**"。
    
4. On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (Choose the **Type** value from the drop-down list.) 
    
    |||||
    |:-----|:-----|:-----|:-----|
    |**Host Record** <br/> |**TTL** <br/> |**类型** <br/> |**TXT Value** <br/> |
    |@  <br/> |14400  <br/> |TXT  <br/> |MS=ms *XXXXXXXX*  <br/> **注意：** 这是一个示例。 在这里使用表中的特定“**目标地址或指向的地址**”值。 [如何查找此项？](../get-help-with-domains/information-for-dns-records.md)          |
   
5. 选择 "**添加记录**"。
    
6. 请在继续之前等待数分钟，以便您刚刚创建的记录可以通过 Internet 完成更新。
    
现在您已在域注册机构的网站上添加了记录，您将返回到 Microsoft 并请求搜索该记录。
  
Microsof 找到正确的 TXT 记录表明域已通过验证。
  
1. 在 Microsoft 管理中心，转到“**设置**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">域</a>”页面。

    
2. 在“**域**”页面上，选择要验证的域。 
    
3. 在“**设置**”页面上，选择“**开始设置**”。
    
4. 在“**验证域**”页面上，选择“**验证**”。
    
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果在添加 DNS 记录后遇到邮件流问题或其他问题，请参阅[查找在添加域或 DNS 记录后遇到的问题并进行修复](../get-help-with-domains/find-and-fix-issues.md)。 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>添加一条 MX 记录，确保发往你的域的电子邮件将会发送到 Microsoft
<a name="BKMK_add_MX"> </a>

1. 要开始，请使用[此链接](https://my.bluehost.com/cgi/dm)转到您在 Bluehost 上的域页面。 系统将会提示您先登录。
    
2. 在" **域**"页面上的" **域**"区域中，找到你要更改的域所在的行，然后选中该域对应的复选框。 
    
    （您可能需要向下滚动。）
    
3. 在 " ***domain_name*** " 区域的 " **DNS 区域编辑器**" 行中，选择 "**管理 DNS 记录**"。
    
4. On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (Choose the **Type** value from the drop-down list.) 
    
    |**Host Record**|**TTL**|**类型**|**指向**|**优先级**|
    |:-----|:-----|:-----|:-----|:-----|
    |@  <br/> |14400  <br/> |MX  <br/> | *\<域密钥\>*  .mail.protection.outlook.com  <br/>**注意：** 从 Microsoft 帐户获取\<*域密钥*\>。 如何查找此内容？[](../get-help-with-domains/information-for-dns-records.md)          |0  <br/> 有关优先级的详细信息，请参阅[什么是 MX 优先级？](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx) <br/> |
   
   ![从下拉列表中选择 "类型"](../../media/70791420-d83c-4a5d-a46c-5cc3bc67f565.png)
  
5. 选择 "**添加记录**"。
    
    ![选择 "添加记录"](../../media/c7ef9733-1665-4dbf-accc-caadf1574abc.png)
  
6. 如果**mx （邮件交换器）** 部分中有任何其他 MX 记录，请将其删除。 
    
    对于其中一个 MX 记录，请选择 "**删除"。**
    
    ![选择每个其他 MX 记录的 "删除"](../../media/6be17f54-3f33-47af-a9db-4689141530c2.png)
  
7. 在确认对话框中，选择 **"确定"**。
    
    ![选择 "确定"](../../media/a50df7a3-2906-4cc0-87d4-1231ab234230.png)
  
8. 使用相同的过程删除已列出的任何其他 MX 记录。
    
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a>添加 Microsoft 所需的六条 CNAME 记录
<a name="BKMK_add_CNAME"> </a>

1. 要开始，请使用[此链接](https://my.bluehost.com/cgi/dm)转到您在 Bluehost 上的域页面。 系统将会提示您先登录。
    
2. 在" **域**"页面上的" **域**"区域中，找到你要更改的域所在的行，然后选中该域对应的复选框。 
    
    （您可能需要向下滚动。）
    
3. 在 " ***domain_name*** " 区域的 " **DNS 区域编辑器**" 行中，选择 "**管理 DNS 记录**"。
    
4. 在 " **A （主机）** 记录" 部分中，找到**自动发现**记录所在的行，然后为该行选择 "**删除**"。 
    
    > [!IMPORTANT]
    > 在添加 Microsoft 所需的**自动发现**记录*之前*，必须删除现有的**自动发现**记录。 Bluehost 不允许同时维护两个**自动发现**记录。 
  
    ![选择 "删除"](../../media/416a447e-3710-4ae7-8bf1-459381af4f6e.png)
  
5. 选择“**确定**”。
    
    ![选择 "确定"](../../media/0c8f409d-c39f-4ed2-9c95-9af3e61c2411.png)
  
6. 创建 6 条 CNAME 记录中的第一条记录。
    
    在 " **DNS 区域编辑器**" 页上的 "**添加 DNS 记录**" 区域中，在新记录的框中，键入或复制并粘贴下表中第一行的值。 
    
    (Choose the **Type** value from the drop-down list.) 
    
    |**Host Record**|**TTL**|**类型**|**指向**|
    |:-----|:-----|:-----|:-----|
    |自动发现  <br/> |14400  <br/> |CNAME  <br/> |autodiscover.outlook.com  <br/> |
    |sip  <br/> |14400  <br/> |CNAME  <br/> |sipdir.online.lync.com  <br/> |
    |lyncdiscover  <br/> |14400  <br/> |CNAME  <br/> |webdir.online.lync.com  <br/> |
    |enterpriseregistration  <br/> |14400  <br/> |CNAME  <br/> |enterpriseregistration.windows.net  <br/> |
    |enterpriseenrollment  <br/> |14400  <br/> |CNAME  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> |
   
    ![创建第一个 CNAME 记录](../../media/4f12e9b1-9dec-4bc2-aa15-8bffa71fe131.png)
  
7. 选择 "**添加记录**"。
    
    ![选择 "添加记录"](../../media/c2782250-a9a6-4aee-bb15-f57cb0008587.png)
  
8. 逐一添加其他 5 条 CNAME 记录。
    
    仍在 "**添加 DNS 记录**" 部分，使用表中下一行的值创建记录，然后再次选择 "**添加记录**" 以完成该记录。 
    
    重复该过程，直到创建完全部 6 条 CNAME 记录。
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>为 SPF 添加 TXT 记录以帮助防止垃圾邮件
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> 一个域所拥有的 SPF 的 TXT 记录不能超过一个。 如果域具有多个 SPF 记录，你将收到电子邮件错误，其中随附发送和垃圾邮件分类问题。 如果你的域已有 SPF 记录，请不要为 Microsoft 创建新记录。 改为将所需的 Microsoft 值添加到当前记录，以便您具有包含两组值的*单个*SPF 记录。 需要示例吗？ 请查看 [Microsoft 的外部域名系统记录](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0)。 若要验证您的 SPF 记录，您可以使用其中一种[SPF 验证工具](../setup/domains-faq.md)。 
  
1. 要开始，请使用[此链接](https://my.bluehost.com/cgi/dm)转到您在 Bluehost 上的域页面。 系统将会提示您先登录。
    
2. 在" **域**"页面上的" **域**"区域中，找到你要更改的域所在的行，然后选中该域对应的复选框。 
    
    （您可能需要向下滚动。）
    
3. 在 " ***domain_name*** " 区域的 " **DNS 区域编辑器**" 行中，选择 "**管理 DNS 记录**"。
    
4. On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (Choose the **Type** value from the drop-down list.) 
        
    |**Host Record**|**TTL**|**类型**|**TXT Value**|
    |:-----|:-----|:-----|:-----|
    |@  <br/> |14400  <br/> |TXT  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/>**注意：** 我们建议您复制并粘贴此条目，以保证正确保留所有空格。           |
   
    ![复制 TXT 值](../../media/b2dabd7a-ee3d-4209-aa1e-0233eb8cf3b9.png)
  
5. 选择 "**添加记录**"。
    
    ![选择 "添加记录"](../../media/c050e9a2-2274-4640-8f0f-6752d382df5d.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>添加 Microsoft 所需的两条 SRV 记录
<a name="BKMK_add_SRV"> </a>

1. 要开始，请使用[此链接](https://my.bluehost.com/cgi/dm)转到您在 Bluehost 上的域页面。 系统将会提示您先登录。
    
2. 在" **域**"页面上的" **域**"区域中，找到你要更改的域所在的行，然后选中该域对应的复选框。 
    
    （您可能需要向下滚动。）
    
3. 在 " ***domain_name*** " 区域的 " **DNS 区域编辑器**" 行中，选择 "**管理 DNS 记录**"。
    
4. 创建两条 SRV 记录中的第一条记录。
    
    在 " **DNS 区域编辑器**" 页上的 "**添加 DNS 记录**" 区域中，在新记录的框中，键入或复制并粘贴下表中第一行的值。 
    
    (Choose the **Type** value from the drop-down list.) 
    
    |**服务**|**协议**|**主机**|**TTL**|**类型**|**优先级**|**权重**|**端口**|**指向**|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |_sip  <br/> |_tls  <br/> |@  <br/> |14400  <br/> |SRV  <br/> |100  <br/> |1  <br/> |443  <br/> |sipdir.online.lync.com  <br/> |
    |_sipfederationtls  <br/> |_tcp  <br/> |@  <br/> |14400  <br/> |SRV  <br/> |100  <br/> |1  <br/> |5061  <br/> |sipfed.online.lync.com  <br/> |
   
    ![复制新记录的值](../../media/e2911bca-c00b-4b8a-837f-f1d438c474c4.png)
  
5. 选择 "**添加记录**"。
    
    ![选择 "添加记录"](../../media/0fd6a587-03fd-4bce-8321-b14e6ad21f5c.png)
  
6. 添加另一条 SRV 记录。
    
    仍在 "**添加 DNS 记录**" 部分，使用表中其他行的值创建记录，然后再次选择 "**添加记录**" 以完成该记录。 
    
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果在添加 DNS 记录后遇到邮件流问题或其他问题，请参阅[查找在添加域或 DNS 记录后遇到的问题并进行修复](../get-help-with-domains/find-and-fix-issues.md)。 
  

