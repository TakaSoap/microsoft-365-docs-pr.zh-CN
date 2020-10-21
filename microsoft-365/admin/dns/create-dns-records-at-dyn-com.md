---
title: 在 Dyn.com 处为 Microsoft 创建 DNS 记录
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
ms.assetid: 34e57a00-2a7d-469c-beec-089423f18369
description: 了解如何验证您的域，并在 Dyn.com for Microsoft 中为电子邮件、Skype for Business Online 和其他服务设置 DNS 记录。
ms.openlocfilehash: 91dbd3fbde8417764a01eb285b267f3981b2f139
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/21/2020
ms.locfileid: "48646135"
---
# <a name="create-dns-records-at-dyncom-for-microsoft"></a>在 Dyn.com 处为 Microsoft 创建 DNS 记录

 **如果找不到要查找的内容，请[查看域常见问题解答](../setup/domains-faq.md)** 。 
  
如果 DNS 托管提供者是 Dyn.com，请按本文中的步骤验证域并为电子邮件、Skype for Business Online 等设置 DNS 记录。
 

  
> [!NOTE]
>  DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。 
  
## <a name="add-a-txt-record-for-verification"></a>添加 TXT 记录进行验证
<a name="BKMK_verify"> </a>

1. 若要开始，请使用[此链接](https://account.dyn.com/dns/)转到你在 Dyn.com 上的域页面。系统会提示你先进行登录。
    
    ![Dyn-BP-Configure-1-1](../../media/77597d44-9b04-43b1-8e23-d4fad238def2.png)
  
2. 在 " **区域级别服务** " 页上，为要编辑的域选择 " **Dyn Standard DNS 服务** "。 
    
3. 在您的域的 " **DNS** " 页面上，选择 " **首选项**"。
    
4. 选择 " **启用专家界面**"。
    
5. In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (Choose the **Type** value from the drop-down list.) 
    
    |**主机**|**TTL**|**类型**|**数据**|
    |:-----|:-----|:-----|:-----|
    |(Leave this field empty.)  <br/> |600  <br/> |TXT  <br/> |MS=ms *XXXXXXXX*  <br/> **注意：** 这是一个示例。 在这里使用表中的特定“**目标地址或指向的地址**”值。           [如何查找此项？](../get-help-with-domains/information-for-dns-records.md)          |
       
   ![Dyn-验证-1-1](../../media/b3730b15-a313-4b4c-b91e-646eebb649e8.png)
  
6. 选择 " **创建记录**"。
    
    ![Dyn-BP-Verify-1-2](../../media/8b63b4ee-dbd7-44a7-b1e6-c6892b02f13e.png)
  
7. 请在继续之前等待数分钟，以便您刚刚创建的记录可以通过 Internet 完成更新。
    
在在域注册机构网站添加了记录后，你将返回到 Microsoft 并请求记录。
  
Microsof 找到正确的 TXT 记录表明域已通过验证。
  
1. 在 Microsoft 管理中心，转到“**设置**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">域</a>”页面。

    
2. 在“**域**”页面上，选择要验证的域。 
    
    
  
3. 在“**设置**”页面上，选择“**开始设置**”。
    
    
  
4. 在“**验证域**”页面上，选择“**验证**”。
    
    
  
> [!NOTE]
>  DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>添加一条 MX 记录，确保发往你的域的电子邮件将会发送到 Microsoft
<a name="BKMK_add_MX"> </a>

1. 若要开始，请使用[此链接](https://account.dyn.com/dns/)转到你在 Dyn.com 上的域页面。系统会提示你先进行登录。
    
    ![Dyn-BP-Configure-1-1](../../media/77597d44-9b04-43b1-8e23-d4fad238def2.png)
  
2. 在 " **区域级别服务** " 页上，为要编辑的域选择 " **Dyn Standard DNS 服务** "。 
    
3. 在您的域的 "DNS" 页面上，选择 " **首选项**"。
    
4. 选择 " **启用专家界面**"。
    
5. In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (Choose the **Type** value from the drop-down list.) 
    
    |**主机**|**TTL**|**类型**|**数据**|
    |:-----|:-----|:-----|:-----|
    |(Leave this field empty.)  <br/> |600  <br/> |MX  <br/> |10  *\<domain-key\>*  . mail.protection.outlook.com。  <br/> **此值必须以句点 (.) 结尾。** <br/> **10** 是 MX 优先级值。将其添加到 MX 值的开头，使用一个空格将其与其余部分隔开。  <br/> **注意：***\<domain-key\>* 从你的 Microsoft 帐户获取你的。           [如何查找此项？](../get-help-with-domains/information-for-dns-records.md)      <br>    有关优先级的详细信息，请参阅[什么是 MX 优先级？](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) <br/> |
   
    ![Dyn-配置-2-1](../../media/62ac77b7-c84d-426d-9ec4-a28d6479ad04.png)
  
6. 选择 " **创建记录**"。
    
    ![Dyn-BP-Configure-2-2](../../media/e84e2cca-75e3-4584-8a98-f2f89cb71bd3.png)
  
7. 如果存在任何其他 MX 记录，通过选中" **删除**"列中这些记录的复选框将其删除。 
    
    ![Dyn-BP-Configure-2-3](../../media/f24f02cc-c0b7-42cf-a2ff-4d0fc203e4de.png)
  
8. 选择 " **应用更改**"。
    
    ![Dyn-BP-Configure-2-4](../../media/0cc23c2b-b6f2-4f58-af20-4c6506de7b43.png)
  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a>添加 Microsoft 所需的六条 CNAME 记录
<a name="BKMK_add_CNAME"> </a>

1. 若要开始，请使用[此链接](https://account.dyn.com/dns/)转到你在 Dyn.com 上的域页面。系统会提示你先进行登录。
    
    ![Dyn-BP-Configure-1-1](../../media/77597d44-9b04-43b1-8e23-d4fad238def2.png)
  
2. 在 " **区域级别服务** " 页上，为要编辑的域选择 " **Dyn Standard DNS 服务** "。 
    
3. 在您的域的 " **DNS** " 页面上，选择 " **首选项**"。
    
4. 选择 " **启用专家界面**"。
    
5. 添加第一条 CNAME 记录（共 6 条）。
    
    在" **添加 DNS 记录**"部分中新记录的框内，键入或复制并粘贴下表中第一行的值。 
    
    （从下拉列表中选择" **类型**"值。） 
    
    |**主机**|**TTL**|**类型**|**数据**|
    |:-----|:-----|:-----|:-----|
    |自动发现  <br/> |600  <br/> |CNAME  <br/> |autodiscover.outlook.com.  <br/> **此值必须以句点 (.) 结尾。** <br/> |
    |sip  <br/> |600  <br/> |CNAME  <br/> |sipdir.online.lync.com.  <br/> **此值必须以句点 (.) 结尾。** <br/> |
    |lyncdiscover  <br/> |600  <br/> |CNAME  <br/> |webdir.online.lync.com.  <br/> **此值必须以句点 (.) 结尾。** <br/> |
    |enterpriseregistration  <br/> |600  <br/> |CNAME  <br/> |enterpriseregistration.windows.net.  <br/> **此值必须以句点 (.) 结尾。** <br/> |
    |enterpriseenrollment  <br/> |600  <br/> |CNAME  <br/> |enterpriseenrollment-s.manage.microsoft.com.  <br/> **此值必须以句点 (.) 结尾。** <br/> |
   
    ![Dyn-配置-3-1](../../media/1fd80695-d3d7-4298-9ebe-97a69f46f1b2.png)
  
6. 选择 " **创建记录**"。
    
    ![Dyn-BP-Configure-3-2](../../media/89551495-3fa5-44ab-96b2-855f70be0880.png)
  
7. 添加其他五条 CNAME 记录。
    
    在 " **添加 DNS 记录** " 部分，使用表中下一行的值创建记录，然后再次选择 " **创建记录** " 以完成该记录。 
    
    重复该过程，直到创建完全部 6 条 CNAME 记录。
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>为 SPF 添加 TXT 记录以帮助防止垃圾邮件
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> 一个域所拥有的 SPF 的 TXT 记录不能超过一个。 如果域具有多个 SPF 记录，你将收到电子邮件错误，其中随附发送和垃圾邮件分类问题。 如果你的域已有 SPF 记录，请不要为 Microsoft 创建新记录。 改为将所需的 Microsoft 值添加到当前记录，以便您具有包含两组值的  *单个*  SPF 记录。
  
1. 若要开始，请使用[此链接](https://account.dyn.com/dns/)转到你在 Dyn.com 上的域页面。系统会提示你先进行登录。
    
    ![Dyn-BP-Configure-1-1](../../media/77597d44-9b04-43b1-8e23-d4fad238def2.png)
  
2. 在 " **区域级别服务** " 页上，为要编辑的域选择 " **Dyn Standard DNS 服务** "。 
    
3. 在您的域的 " **DNS** " 页面上，选择 " **首选项**"。
    
4. 选择 " **启用专家界面**"。
    
5. In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (Choose the **Type** value from the drop-down list.) 
    
    |**主机**|**TTL**|**类型**|**数据**|
    |:-----|:-----|:-----|:-----|
    |(Leave this field empty.)  <br/> |600  <br/> |TXT  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **注意：** 建议复制粘贴此条目，以保证正确保留所有空格。           |
   
    ![Dyn-配置-4-1](../../media/f8511349-3ea2-40c3-9853-98e1a58a91b5.png)
  
6. 选择 " **创建记录**"。
    
    ![Dyn-BP-Configure-4-2](../../media/bbe04835-d3c0-4146-8123-9781bb9eca51.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>添加 Microsoft 所需的两条 SRV 记录
<a name="BKMK_add_SRV"> </a>

1. 若要开始，请使用[此链接](https://account.dyn.com/dns/)转到你在 Dyn.com 上的域页面。 系统将提示您先登录 
    
    ![Dyn-BP-Configure-1-1](../../media/77597d44-9b04-43b1-8e23-d4fad238def2.png)
  
2. 在 " **区域级别服务** " 页上，为要编辑的域选择 " **Dyn Standard DNS 服务** "。 
    
3. 在您的域的 " **DNS** " 页面上，选择 " **首选项**"。
    
4. 选择 " **启用专家界面**"。
    
5. 添加两条 SRV 记录中的第一条。
    
    在" **添加 DNS 记录**"部分中新记录的框内，键入或复制并粘贴下表中第一行的值。 
    
    （从下拉列表中选择" **类型**"值。） 
    
    |**主机**|**TTL**|**类型**|**数据**|
    |:-----|:-----|:-----|:-----|
    |_sip._tls|600|SRV|100 1 443 sipdir.online.lync.com. **此值必须以句点 (.) 结尾。**<br>**注意：** 建议复制粘贴此条目，以保证正确保留所有空格。           |
    |_sipfederationtls._tcp|600|SRV|100 1 5061 sipfed.online.lync.com. **此值必须以句点 (.) 结尾。**<br> **注意：** 建议复制粘贴此条目，以保证正确保留所有空格。           |
   
    ![Dyn-配置-5-1](../../media/a6873411-f4ce-4327-9145-02d435930976.png)
  
6. 选择 " **创建记录**"。
    
    ![Dyn-BP-Configure-5-2](../../media/e6f33452-e527-473b-a645-b31ed70b0d43.png)
  
7. 添加另一条 SRV 记录。
    
    在 " **添加 DNS 记录** " 部分，使用表中第二行的值创建记录，然后再次选择 " **创建记录** " 以完成该记录。 
    
> [!NOTE]
>  DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。 
  
