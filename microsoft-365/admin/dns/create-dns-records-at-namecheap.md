---
title: 在 Namecheap 处为 Microsoft 创建 DNS 记录
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
ms.assetid: 54ae2002-b38e-43a1-82fa-3e49d78fda56
description: 了解如何验证您的域，并在 Namecheap for Microsoft 中为电子邮件、Skype for Business Online 和其他服务设置 DNS 记录。
ms.openlocfilehash: 2aae667428aba5ea22ab210c47aa9c994a9acf14
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2020
ms.locfileid: "44400384"
---
# <a name="create-dns-records-at-namecheap-for-microsoft"></a>在 Namecheap 处为 Microsoft 创建 DNS 记录

 如果找不到要查找的内容，请**[查看域常见问题解答](../setup/domains-faq.md)**。 
  
如果 Namecheap 是您的 DNS 托管提供商，请按照本文中的步骤验证您的域并为电子邮件、Skype for Business Online 等设置 DNS 记录。
  
在 Namecheap 中添加这些记录后，您的域将设置为与 Microsoft 服务一起使用。
  
> [!NOTE]
> DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。 
  
## <a name="add-a-txt-record-for-verification"></a>添加 TXT 记录进行验证
<a name="BKMK_verify"> </a>

在将域用于 Microsoft 之前，必须确保你拥有该域。如果你能够在域注册机构处登录到你的帐户并创建 DNS 记录，便可向 Microsoft 证明你是域所有者。
  
> [!NOTE]
> 此记录仅用于验证您是否拥有自己的域；它不会影响其他任何内容。 如果需要，您可以以后将其删除。 
  
按照下面的步骤操作。
  
1. 若要开始，请使用[此链接](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f)转到 Namecheap 上的 "域" 页面。 系统将提示您登录并继续。
    
    ![Namecheap-配置-1-1](../../media/1827f9fc-4dc9-4f9d-a392-7817c47b00b3.png)
  
2. 在 "**登录**" 页面上的 "**帐户**" 下，从下拉列表中选择 "**域列表**"。 
    
    ![Namecheap-配置-1-2](../../media/3f457d64-4589-422c-ae34-fc24b0e819eb.png)
  
3. 在 "**域列表**" 页上，找到要编辑的域的名称，然后选择 "**管理**"。
    
    ![Namecheap-配置-1-3](../../media/fb2020d8-707c-4148-835e-304ac6244d66.png)
  
4. 选择 "**高级 DNS**"。
    
    ![Namecheap-配置-1-4](../../media/05a4f0b9-1d27-448e-9954-2b23304c5f65.png)
  
5. 在 "**主机记录**" 部分，选择 "**添加新记录**"。
    
    ![Namecheap-配置-1-5](../../media/8849abfe-deb6-4f6a-b56d-e69be9a28b0f.png)
  
6. 在 "**类型**" 下拉中，选择 " **TXT 记录**"。
    
    > [!NOTE]
    > 当您选择 "**添加新记录**" 时，"类型" 下拉**类型**将自动显示。 
  
    ![Namecheap-验证-1-1](../../media/a5b40973-19b5-4c32-8e1b-1521aa971836.png)
  
7. 在新记录的框中，键入或复制并粘贴下表中的值。
    
    （从下拉列表中选择 " **TTL** " 值。） 
    
    |**类型**|**主机**|**值**|**TTL**|
    |:-----|:-----|:-----|:-----|
    |TXT  <br/> |@  <br/> |MS=ms *XXXXXXXX*  <br/>**注意：** 这是一个示例。 在这里使用表中的特定“**目标地址或指向的地址**”值。  [如何查找此项？](../get-help-with-domains/information-for-dns-records.md)          |30分钟  <br/> |
       
    ![Namecheap-验证-1-2](../../media/fe75c0fd-f85c-4bef-8068-edaf9779b7f1.png)
  
8. 选择 "**保存更改**" （复选标记）控件。 
    
    ![Namecheap-验证-1-3](../../media/b48d2c67-66b5-4aa4-8e59-0c764f236fac.png)
  
9. 请在继续之前等待数分钟，以便您刚刚创建的记录可以通过 Internet 完成更新。
    
在在域注册机构网站添加了记录后，你将返回到 Microsoft 并请求记录。
  
Microsof 找到正确的 TXT 记录表明域已通过验证。
  
1. 在管理中心，转到“**设置**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">域</a>”页面。
    
2. 在“**域**”页面上，选择要验证的域。 
    
    
  
3. 在“**设置**”页面上，选择“**开始设置**”。
    
    
  
4. 在“**验证域**”页面上，选择“**验证**”。
    
    
  
> [!NOTE]
> DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。 

  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>添加一条 MX 记录，确保发往你的域的电子邮件将会发送到 Microsoft
<a name="BKMK_add_MX"> </a>

按照下面的步骤操作。
  
1. 若要开始，请使用[此链接](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f)转到 Namecheap 上的 "域" 页面。 系统将提示您登录并继续。
    
    ![Namecheap-配置-1-1](../../media/1827f9fc-4dc9-4f9d-a392-7817c47b00b3.png)
  
2. 在 "**登录**" 页面上的 "**帐户**" 下，从下拉列表中选择 "**域列表**"。 
    
    ![Namecheap-配置-1-2](../../media/3f457d64-4589-422c-ae34-fc24b0e819eb.png)
  
3. 在 "**域列表**" 页上，找到要编辑的域的名称，然后选择 "**管理**"。
    
    ![Namecheap-配置-1-3](../../media/fb2020d8-707c-4148-835e-304ac6244d66.png)
  
4. 选择 "**高级 DNS**"。
    
    ![Namecheap-配置-1-4](../../media/05a4f0b9-1d27-448e-9954-2b23304c5f65.png)
  
5. 在 "**邮件设置**" 部分，从 "**电子邮件转发**" 下拉列表中选择 "**自定义 MX** "。 
    
    (You may have to scroll down.)
    
    ![Namecheap-配置-2-1](../../media/40199e2c-42cf-4c3f-9936-3cbe5d4e81a4.png)
  
6. 选择 "**添加新记录**"。
    
    ![Namecheap-配置-2-2-1](../../media/8d169b81-ba48-4d51-84ea-a08fa1616457.png)
  
7. 在新记录的框中，键入或复制并粘贴下表中的值。
    
    （"**优先级**" 框是 "**值**" 框右侧的未命名框。 从下拉列表中选择 " **TTL** " 值。 
    
    |**类型**|**主机**|**值**|**优先级**|**TTL**|
    |:-----|:-----|:-----|:-----|:-----|
    |MX 记录  <br/> |@  <br/> |\<*domain-key*\>. mail.protection.outlook.com。  <br/> **This value MUST end with a period (.)** <br/> **注意：***\<domain-key\>* 从你的 Microsoft 帐户获取你的。  如何查找此内容？[](../get-help-with-domains/information-for-dns-records.md)          |0  <br/> 有关优先级的详细信息，请参阅[什么是 MX 优先级？](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) <br/> |30分钟  <br/> |
       
    ![Namecheap-配置-2-2-2](../../media/f3b76d62-5022-48c1-901b-8615a8571309.png)
  
8. 选择 "**保存更改**" （复选标记）控件。 
    
    ![Namecheap-配置-2-3](../../media/ef4e3112-36d2-47c8-a478-136a565dd71d.png)
  
9. 如果有任何其他 MX 记录，请使用以下两步过程删除每个：
    
    首先，选择要删除的记录的 "**删除" 图标**（垃圾桶）。 
    
    ![Namecheap-配置-2-4](../../media/7a7a751f-29c2-495f-8f55-98ca37ce555a.png)
  
    其次，选择 **"是"** 以确认删除。 
    
    ![Namecheap-配置-2-5](../../media/85ebc0c7-8787-43ee-9e7b-647375b3345c.png)
  
    删除在此过程前面添加的 MX 记录之外的所有 MX 记录。

  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a>添加 Microsoft 所需的六条 CNAME 记录
<a name="BKMK_add_CNAME"> </a>

按照下面的步骤操作。
  
1. 若要开始，请使用[此链接](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f)转到 Namecheap 上的 "域" 页面。 系统将提示您登录并继续。
    
    ![Namecheap-配置-1-1](../../media/1827f9fc-4dc9-4f9d-a392-7817c47b00b3.png)
  
2. 在 "**登录**" 页面上的 "**帐户**" 下，从下拉列表中选择 "**域列表**"。 
    
    ![Namecheap-配置-1-2](../../media/3f457d64-4589-422c-ae34-fc24b0e819eb.png)
  
3. 在 "**域列表**" 页上，找到要编辑的域的名称，然后选择 "**管理**"。
    
    ![Namecheap-配置-1-3](../../media/fb2020d8-707c-4148-835e-304ac6244d66.png)
  
4. 选择 "**高级 DNS**"。
    
    ![Namecheap-配置-1-4](../../media/05a4f0b9-1d27-448e-9954-2b23304c5f65.png)
  
5. 在 "**主机记录**" 部分，选择 "**添加新记录**"。
    
    ![Namecheap-配置-1-5](../../media/8849abfe-deb6-4f6a-b56d-e69be9a28b0f.png)
  
6. 在 "**类型**" 下拉菜单中，选择 " **CNAME 记录**"。
    
    > [!NOTE]
    > 当您选择 "**添加新记录**" 时，"类型" 下拉**类型**将自动显示。 
  
    ![Namecheap-配置-3-1](../../media/0898f3b2-06ab-4364-a86a-a603a25b39f4.png)
  
7. 在新记录的空框中，为**记录类型**选择 " **CNAME** "，然后键入或复制并粘贴下表中第一行的值。
    
    |**类型**|**主机**|**值**|**TTL**|
    |:-----|:-----|:-----|:-----|
    |CNAME  <br/> |autodiscover  <br/> |autodiscover.outlook.com。  <br/> **此值必须以句点 (.) 结尾。** <br/> |3600  <br/> |
    |CNAME  <br/> |sip  <br/> |sipdir.online.lync.com。  <br/> **此值必须以句点 (.) 结尾。** <br/> |3600  <br/> |
    |CNAME  <br/> |lyncdiscover  <br/> |webdir.online.lync.com。  <br/> **此值必须以句点 (.) 结尾。** <br/> |3600  <br/> |
    |CNAME  <br/> |enterpriseregistration  <br/> |enterpriseregistration.windows.net。  <br/> **此值必须以句点 (.) 结尾。** <br/> |3600  <br/> |
    |CNAME  <br/> |enterpriseenrollment  <br/> |enterpriseenrollment-s.manage.microsoft.com。  <br/> **此值必须以句点 (.) 结尾。** <br/> |3600  <br/> |
       
    ![Namecheap-配置-3-2](../../media/f79c5679-34eb-4544-8517-caa2e8a4111a.png)
  
8. 选择 "**保存更改**" （复选标记）控件。 
    
    ![Namecheap-配置-3-3](../../media/91a5cce4-ca41-41ec-b976-aafe681a4d68.png)
  
9. 使用前面的四个步骤和表中其他五行中的值，添加其他五个 CNAME 记录中的每个。

  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>为 SPF 添加 TXT 记录以帮助防止垃圾邮件
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> 一个域所拥有的 SPF 的 TXT 记录不能超过一个。 如果域具有多个 SPF 记录，你将收到电子邮件错误，其中随附发送和垃圾邮件分类问题。 如果你的域已有 SPF 记录，请不要为 Microsoft 创建新记录。 改为将所需的 Microsoft 值添加到当前记录，以便您具有包含两组值的*单个*SPF 记录。 

按照下面的步骤操作。
  
1. 若要开始，请使用[此链接](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f)转到 Namecheap 上的 "域" 页面。 系统将提示您登录并继续。
    
2. 在 "**登录**" 页面上的 "**帐户**" 下，从下拉列表中选择 "**域列表**"。 
    
    ![Namecheap-配置-1-2](../../media/3f457d64-4589-422c-ae34-fc24b0e819eb.png)
  
3. 在 "**域列表**" 页上，找到要编辑的域的名称，然后选择 "**管理**"。
    
    ![Namecheap-配置-1-3](../../media/fb2020d8-707c-4148-835e-304ac6244d66.png)
  
4. 选择 "**高级 DNS**"。
    
    ![Namecheap-配置-1-4](../../media/05a4f0b9-1d27-448e-9954-2b23304c5f65.png)
  
5. 在 "**主机记录**" 部分，选择 "**添加新记录**"。
    
    ![Namecheap-配置-1-5](../../media/8849abfe-deb6-4f6a-b56d-e69be9a28b0f.png)
  
6. 在 "**类型**" 下拉中，选择 " **TXT 记录**"。
    
    > [!NOTE]
    > 当您选择 "**添加新记录**" 时，"类型" 下拉**类型**将自动显示。 
  
    ![Namecheap-配置-4-1](../../media/c5d1fddb-28b5-48ec-91c9-3e5d3955ac80.png)
  
7. 在新记录的框中，键入或复制并粘贴下表中的以下值。
    
    （从下拉列表中选择 " **TTL** " 值。） 
    
    |**类型**|**主机**|**值**|**TTL**|
    |:-----|:-----|:-----|:-----|
    |TXT  <br/> |@  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **注意：** 我们建议您复制并粘贴此条目，以保证正确保留所有空格。           |30分钟  <br/> |
       
    ![Namecheap-配置-4-2](../../media/ea0829f1-990b-424b-b26e-9859468318dd.png)
  
8. 选择 "**保存更改**" （复选标记）控件。 
    
    ![Namecheap-配置-4-3](../../media/f2846c36-ace3-43d8-be5d-a65e2c267619.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>添加 Microsoft 所需的两条 SRV 记录
<a name="BKMK_add_SRV"> </a>

1. 若要开始，请使用[此链接](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f)转到 Namecheap 上的 "域" 页面。 You'll be prompted to sign in.
    
    ![Namecheap-配置-1-1](../../media/1827f9fc-4dc9-4f9d-a392-7817c47b00b3.png)
  
2. 在 "**登录**" 页面上的 "**帐户**" 下，从下拉列表中选择 "**域列表**"。 
    
    ![Namecheap-配置-1-2](../../media/3f457d64-4589-422c-ae34-fc24b0e819eb.png)
  
3. 在 "**域列表**" 页上，找到要编辑的域的名称，然后选择 "**管理**"。
    
    ![Namecheap-配置-1-3](../../media/fb2020d8-707c-4148-835e-304ac6244d66.png)
  
4. 选择 "**高级 DNS**"。
    
    ![Namecheap-配置-1-4](../../media/05a4f0b9-1d27-448e-9954-2b23304c5f65.png)
  
5. 在 "**主机记录**" 部分，选择 "**添加新记录**"。
    
    ![Namecheap-配置-1-5](../../media/8849abfe-deb6-4f6a-b56d-e69be9a28b0f.png)
  
6. 在 "**类型**" 下拉菜单中，选择 " **SRV 记录**"。
    
    > [!NOTE]
    > 当您选择 "**添加新记录**" 时，"类型" 下拉**类型**将自动显示。 
  
    ![Namecheap-配置-5-1](../../media/fd55cd7c-2243-4de1-8d39-2c3f7ea3ae51.png)
  
7. 在新记录的空框中，键入或复制并粘贴下表中第一行的值。
    
    |**服务**|**协议**|**优先级**|**权重**|**端口**|**目标**|**TTL**|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |_sip  <br/> |_tls  <br/> |100  <br/> |1   <br/> |443  <br/> |sipdir.online.lync.com。  <br/> **This value MUST end with a period (.)** <br/> |30分钟  <br/> |
    |_sipfederationtls  <br/> |_tcp  <br/> |100  <br/> |1   <br/> |5061  <br/> |sipfed.online.lync.com。  <br/> **此值必须以句点 (.) 结尾。** <br/> |30分钟  <br/> |
       
    ![Namecheap-配置-5-2](../../media/ff9566ea-0096-4b7f-873c-027080a23b56.png)
  
8. 选择 "**保存更改**" （复选标记）控件。 
    
    ![Namecheap-配置-5-3](../../media/48a8dee4-c66d-449d-8759-9e9784c82b13.png)
  
9. 使用前面的四个步骤和表中第二行的值，添加另一条 SRV 记录。
    
> [!NOTE]
> DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。 
  

  
