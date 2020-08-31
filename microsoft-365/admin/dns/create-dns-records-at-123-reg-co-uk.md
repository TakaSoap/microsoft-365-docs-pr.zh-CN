---
title: 在123-reg.co.uk 处为 Microsoft 创建 DNS 记录
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
ms.assetid: 1f2d08c9-2a88-4d2f-ae1f-e39f9e358b17
description: 了解如何验证您的域，并在 123-reg.co.uk for Microsoft 中为电子邮件、Skype for Business Online 和其他服务设置 DNS 记录。
ms.openlocfilehash: 51542e1f00153a87ca06ec540d391de6ca621bab
ms.sourcegitcommit: 555d756c69ac9031d1fb928f2e1f9750beede066
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/29/2020
ms.locfileid: "47307027"
---
# <a name="create-dns-records-at-123-regcouk-for-microsoft"></a>在123-reg.co.uk 处为 Microsoft 创建 DNS 记录

 **如果找不到要查找的内容，请[查看域常见问题解答](../setup/domains-faq.md)** 。 
  
如果 DNS 托管提供者是 123-reg.co.uk，请按本文中的步骤验证域并为电子邮件、Skype for Business Online 等设置 DNS 记录。
  
在123-reg.co.uk 中添加这些记录后，您的域将设置为与 Microsoft 服务一起使用。
  
  
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果在添加 DNS 记录后遇到邮件流问题或其他问题，请参阅[查找在添加域或 DNS 记录后遇到的问题并进行修复](../get-help-with-domains/find-and-fix-issues.md)。 
  
## <a name="add-a-txt-record-for-verification"></a>添加 TXT 记录进行验证
<a name="BKMK_verify"> </a>

在将域用于 Microsoft 之前，必须确保你拥有该域。如果你能够在域注册机构处登录到你的帐户并创建 DNS 记录，便可向 Microsoft 证明你是域所有者。
  
> [!NOTE]
> 此记录仅用于验证您是否拥有自己的域；它不会影响其他任何内容。 如果需要，您可以以后将其删除。 
  
1. 要开始，请使用[此链接](https://www.123-reg.co.uk/secure/cpanel/domain/overview)转到您在 123-reg.co.uk 上的域页面。 系统将会提示您先登录。
    
2. On the **Domain name overview** page, select the name of the domain that you want to edit. 
    
3. Choose **DNS** from the **Select action** drop-down list. 
    
4. 在 " **管理 DNS** " 页面上，选择 " **高级 DNS** " 选项卡。 
    
5. In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (Choose the **Type** value from the drop-down list.) 
    
    ||||
    |:-----|:-----|:-----|
    |**主机名** <br/> |**类型** <br/> |**Destination TXT/SPF** <br/> |
    |@  <br/> |TXT/SPF  <br/> |MS=ms *XXXXXXXX*  <br/> **注意：** 这是一个示例。 在这里使用表中的特定“**目标地址或指向的地址**”值。 [如何查找此项？](../get-help-with-domains/information-for-dns-records.md)          |
   
6. 选择“**添加**”。
    
7. 请在继续之前等待数分钟，以便您刚刚创建的记录可以通过 Internet 完成更新。
    
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

1. 要开始，请使用[此链接](https://www.123-reg.co.uk/secure/cpanel/domain/overview)转到您在 123-reg.co.uk 上的域页面。 系统将会提示您先登录。
    
2. On the **Domain name overview** page, select the name of the domain that you want to edit. 
    
3. Choose **DNS** from the **Select action** drop-down list. 
    
4. 在 " **管理 DNS** " 页面上，选择 " **高级 DNS** " 选项卡。 
    
5. In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (Choose the **Type** value from the drop-down list.) 
    
    |**主机名**|**类型**|**优先级**|**目标 MX**|
    |:-----|:-----|:-----|:-----|
    |@  <br/> |MX  <br/> |1   <br/> 有关优先级的详细信息，请参阅[什么是 MX 优先级？](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) <br/> | *\<domain-key\>*  . mail.protection.outlook.com。  <br/> **此值必须以句点 (.) 结尾。** <br/> **注意：** 从 Microsoft 帐户获取 \<domain-key\>。 [如何查找此项？](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![复制并粘贴表中的值](../../media/65366165-85a6-4a39-b9a7-6c5f47fbe790.png)
  
6. 选择“**添加**”。
    
    ![选择“添加”](../../media/a8ae6c0c-4365-4137-af8a-6e003996e3d0.png)
  
7. 如果有任何其他 MX 记录，通过选择每条记录的" **删除(回收站)**"图标将其删除。 
    
    ![选择 "删除 (垃圾桶" 图标) ](../../media/3be635e6-b591-49af-8430-a158272834b4.png)
  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a>添加 Microsoft 所需的六条 CNAME 记录
<a name="BKMK_add_CNAME"> </a>

1. 要开始，请使用[此链接](https://www.123-reg.co.uk/secure/cpanel/domain/overview)转到您在 123-reg.co.uk 上的域页面。 系统将会提示您先登录。
    
2. On the **Domain name overview** page, select the name of the domain that you want to edit. 
    
3. Choose **DNS** from the **Select action** drop-down list. 
    
4. 在 " **管理 DNS** " 页面上，选择 " **高级 DNS** " 选项卡。 
    
5. 添加第一条 CNAME 记录（共 6 条）。
    
    In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (Choose the **Type** value from the drop-down list.) 
    
    |**主机名**|**类型**|**目标 CNAME**|
    |:-----|:-----|:-----|
    |自动发现  <br/> |CNAME  <br/> |autodiscover.outlook.com.  <br/> **此值必须以句点 (.) 结尾。** <br/> |
    |sip  <br/> |CNAME  <br/> |sipdir.online.lync.com.  <br/> **此值必须以句点 (.) 结尾。** <br/> |
    |lyncdiscover  <br/> |CNAME  <br/> |webdir.online.lync.com.  <br/> **此值必须以句点 (.) 结尾。** <br/> |
    |enterpriseregistration  <br/> |CNAME  <br/> |enterpriseregistration.windows.net.  <br/> **此值必须以句点 (.) 结尾。** <br/> |
    |enterpriseenrollment  <br/> |CNAME  <br/> |enterpriseenrollment-s.manage.microsoft.com.  <br/> **此值必须以句点 (.) 结尾。** <br/> |
   
    ![复制并粘贴表中的值](../../media/24bf388c-5f7f-4fc0-b4ec-4b17226b6246.png)
  
6. 选择“**添加**”。
    
    ![选择“添加”](../../media/825a9854-559d-4a22-90ac-5e7a0a54269a.png)
  
7. 添加其他 5 条 CNAME 记录。
    
    在 " **高级 DNS** " 部分，使用表中下一行的值创建记录，然后再次选择 " **添加** " 以完成该记录。 
    
    重复该过程，直到创建完全部 6 条 CNAME 记录。
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>为 SPF 添加 TXT 记录以帮助防止垃圾邮件
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> 一个域所拥有的 SPF 的 TXT 记录不能超过一个。 如果域具有多个 SPF 记录，你将收到电子邮件错误，其中随附发送和垃圾邮件分类问题。 如果你已有域的 SPF 记录，请勿为 Microsfot 创建新的。 改为将所需的 Microsoft 值添加到当前记录，以便您具有包含两组值的  *单个*  SPF 记录。 需要示例吗？ 请查看 [Microsoft 的外部域名系统记录](https://docs.microsoft.com/microsoft-365/enterprise/external-domain-name-system-records#external-dns-records-required-for-spf)。 若要验证 SPF 记录，可使用以下任一 [SPF 验证工具](../setup/domains-faq.md)。 
  
1. 要开始，请使用[此链接](https://www.123-reg.co.uk/secure/cpanel/domain/overview)转到您在 123-reg.co.uk 上的域页面。 系统将会提示您先登录。
    
2. On the **Domain name overview** page, select the name of the domain that you want to edit. 
    
3. Choose **DNS** from the **Select action** drop-down list. 
    
4. 在 " **管理 DNS** " 页面上，选择 " **高级 DNS** " 选项卡。 
    
5. In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (Choose the **Type** value from the drop-down list.) 
    
    |**主机名**|**类型**|**Destination TXT/SPF**|
    |:-----|:-----|:-----|
    |@  <br/> |TXT/SPF  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **注意：** 建议复制粘贴此条目，以保证正确保留所有空格。           |
   
    ![123Reg-配置-4-1](../../media/4697701c-eba0-4b03-8d75-4f7fc3bef94a.png)
  
6. 选择“**添加**”。
    
    ![选择“添加”](../../media/7906dd91-fd23-44c3-bb37-ef185655c6eb.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>添加 Microsoft 所需的两条 SRV 记录
<a name="BKMK_add_SRV"> </a>

1. 要开始，请使用[此链接](https://www.123-reg.co.uk/secure/cpanel/domain/overview)转到您在 123-reg.co.uk 上的域页面。 系统将会提示您先登录。
    
2. On the **Domain name overview** page, select the name of the domain that you want to edit. 
    
3. Choose **DNS** from the **Select action** drop-down list. 
    
4. 在 " **管理 DNS** " 页面上，选择 " **高级 DNS** " 选项卡。 
    
5. 添加两条 SRV 记录中的第一个：
    
    In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (Choose the **Type** value from the drop-down list.) 
    
    ||||||
    |:-----|:-----|:-----|:-----|:-----|
    |主机名|类型|优先级|TTL|目标 SRV|
    |_sip._tls|SRV|100|3600|1 443 sipdir.online.lync.com。 **此值必须以句点 (.) 结尾。**<br> **注意：** 建议复制粘贴此条目，以保证正确保留所有空格。           |
    |_sipfederationtls._tcp|SRV|100|3600|1 5061 sipfed.online.lync.com。 **此值必须以句点 (.) 结尾。** <br> **注意：** 建议复制粘贴此条目，以保证正确保留所有空格。           |
   
    ![复制并粘贴表中的值](../../media/c1786b86-52ef-4dca-8b99-b479554fa531.png)
  
6. 选择“**添加**”。
    
    ![选择“添加”](../../media/5fd9d3a2-a8bb-466b-829f-b3a6e54b5104.png)
  
7. 添加其他 SRV 记录：
    
    在 " **高级 DNS** " 部分，使用表中第二行的值创建记录，然后再次选择 " **添加** " 以完成该记录。 
    
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果在添加 DNS 记录后遇到邮件流问题或其他问题，请参阅[查找在添加域或 DNS 记录后遇到的问题并进行修复](../get-help-with-domains/find-and-fix-issues.md)。 
  
