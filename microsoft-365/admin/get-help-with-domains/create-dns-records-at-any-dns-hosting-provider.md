---
title: 在任意 DNS 托管提供商处创建 DNS 记录
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 7b7b075d-79f9-4e37-8a9e-fb60c1d95166
description: 了解如何验证域和在任何 DNS 托管提供商处为 Microsoft 365 创建 DNS 记录。
ms.custom: okr_smb
ms.openlocfilehash: 2cf28cdd3cc2f85e448d512e72f5b022177e8f1e
ms.sourcegitcommit: 83f980927728bc080f97a3e6dc70dc305f3df841
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/06/2020
ms.locfileid: "44053714"
---
# <a name="create-dns-records-at-any-dns-hosting-provider"></a>在任意 DNS 托管提供商处创建 DNS 记录

 如果找不到要查找的内容，请**[查看域常见问题解答](../setup/domains-faq.md)**。 
  
查看[主机特定说明](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions)列表，以找到你的主机并按照步骤添加所需的全部记录。 
  
如果不知道你的域的 DNS 托管提供商或域注册机构，请参阅[查找域注册机构或 DNS 托管提供商](../get-help-with-domains/find-your-domain-registrar.md)。
  
若要自行设置记录，需要添加这些记录。 注意，验证记录和 MX 记录是域所特有的。 若要进行设置，需要为域获取和使用特定的“令牌”值。 下面的步骤介绍如何执行此操作。
  
> [!IMPORTANT]
> 为创建各种类型的 DNS 记录，将信息要输入或粘贴到的框或*字段*，根据 DNS 记录有所差异。 DNS 主机可能在网站上提供“帮助”，有助于你映射这里显示的说明至网站的准确字段。 检查以了解在“[为 Microsoft 365 创建 DNS 记录](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider)”中是否存在 DNS 主机分步说明。 > 部分 DNS 主机无法让你创建在 Microsoft 365 中[引起服务限制](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)的所有需要的记录类型。 例如，如果域主机不支持 SRV、TXT 或 CNAME 记录，建议[转移域](../get-help-with-domains/buy-a-domain-name.md)至不支持所有必须记录的 DNS 主机。 为实现使用 Microsoft 365 设置的快速自动化过程，建议将域转移到 GoDaddy。 
  
> [!NOTE]
> DNS 更改通常只需要几分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅“[查找并修复更改域名或 DNS 记录后出现的问题](../get-help-with-domains/find-and-fix-issues.md)”。 
  
## <a name="add-a-txt-or-mx-record-for-verification"></a>添加 TXT 记录或 MX 记录进行验证
<a name="BKMK_verify"> </a>

> [!NOTE]
> 您必须仅创建这些记录中的其中一项。TXT 是首选记录类型，但某些 DNS 托管提供商不支持它，在这种情况下，您可以创建 MX 记录。 
  
在将域用于 Microsoft 365 之前，必须确保你拥有该域。如果你能够在域注册机构处登录到你的帐户并创建 DNS 记录，便可向 Microsoft 365 证明你是域所有者。
  
> [!NOTE]
> 此记录仅用于验证您是否拥有自己的域；它不会影响其他任何内容。 如果需要，您可以以后将其删除。 
  
 **查找你的 DNS 托管提供商网站上可以在其中创建新记录的区域。**
  
1. 登录到您的 DNS 托管提供商的网站。
    
2. 选择您的域。
    
3. 查找您可以在其中编辑您的域的 DNS 记录的页面。
    
 **创建记录。**
  
1. 根据是要创建 TXT 记录还是 MX 记录，请执行下列操作之一：
    
   - **如果要创建 TXT 记录，请使用这些值：**
    
      |||||
      |:-----|:-----|:-----|:-----|
      |**记录类型**|**别名**或**主机名称**|**值**|**TTL**|
      |TXT|执行下列操作之一：键入 **@** ，将该字段留空或键入你的域名。  <br/> **注意：** 此字段对不同的 DNS 主机有不同的要求。 |MS=ms *XXXXXXXX*  <br/> **注意：** 这是一个示例。 在这里使用来自 Microsoft 365 中的表的具体“**目标地址或指向的地址**”值。  <br/>        [如何查找此项？](../get-help-with-domains/information-for-dns-records.md)     <br/>     |将此值设置为 **1 小时** 或等效的分钟数 ( **60** )、秒数 ( **3600** )，等等。  |
   
   - **如果您创建 MX 记录，请使用这些值：**
    
      ||||||
      |:-----|:-----|:-----|:-----|:-----|
      |**记录类型**|**别名**或**主机名称**|**值**|**优先级**|**TTL**|
      |MX|键入" **@** "或你的域名。 |MS=ms *XXXXXXXX* <br/> **注意：** 此为示例。 在这里使用来自 Office 365 中的表的具体**目标地址或指向的地址**值。    <br/>       [如何查找此项？](../get-help-with-domains/information-for-dns-records.md)     <br/>     |对于“**优先级**”，为避免与用于邮件流的 MX 记录发生冲突，请使用比任何现有 MX 记录的优先级要低的优先级。 <br/> 有关优先级的详细信息，请参阅[什么是 MX 优先级？](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) <br/> |将此值设置为 **1 小时** 或等效的分钟数 ( **60** )、秒数 ( **3600** )，等等。 |
   
2. 保存记录。
    
在域注册机构网站添加了记录后，你将返回到 Microsoft 365 并请求 Microsoft 365 查找记录。
  
Microsoft 365 找到正确的 TXT 记录表明域已通过验证。
  
1. 在管理中心，转到“**设置**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">域</a>”页面。
    
2. 在“**域**”页面上，选择要验证的域。 
  
3. 在“**设置**”页面上，选择“**开始设置**”。
       
4. 在“**验证域**”页面上，选择“**验证**”。   
  
> [!NOTE]
>  DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。 
  
## <a name="add-mx-record-to-route-email"></a>添加 MX 记录以路由电子邮件
<a name="BKMK_add_MX"> </a>

添加一条 MX 记录，确保发往你的域的电子邮件将会发送到 Microsoft 365。  *更新你的域的 MX 记录时，使用你的域的任何人的所有新电子邮件都将发往 Microsoft 365*。 你已拥有的任何电子邮件将保留在你当前的电子邮件主机，除非你决定[将电子邮件和联系人迁移到 Microsoft 365。](../setup/migrate-email-and-contacts-admin.md)

 **Task**
  
查找您可以在其中为您的域创建记录的页面。
  
1. 登录到您的 DNS 主机的网站。
    
2. 选择您的域。
    
3. 查找您可以在其中编辑您的域的 DNS 记录的页面。
    
::: moniker range="o365-worldwide"

  您添加的 MX 记录包括以下类似值（" **指向地址**"值）：\<MX token\>.mail.protection.outlook.com，其中，\<MX 令牌\> 是类似于 MSxxxxxxx 的值。 

::: moniker-end

::: moniker range="o365-germany"

  您添加的 MX 记录包括以下类似值（“**指向地址**”值）：\<MX 令牌\>.mail.protection.outlook.de，其中，\<MX 令牌\> 是类似于 MSxxxxxxx 的值。 

::: moniker-end

4. 在您的 DNS 主机的网站上，添加一条新的 MX 记录。
    
    现在，你将从 Microsoft 365 [获得 MX 记录的信息](../get-help-with-domains/information-for-dns-records.md)。 
    
5. 对于 MX 记录（上面的步骤中），复制**指向地址**值。 
    
    如下一步中所述，您将在 DNS 主机网站上创建的记录中使用此值。
    
6. 在您的 DNS 主机的网站上的新 MX 记录中，确保字段精确地设置为以下值：
    
   - **记录类型**：**MX**
    
   - **优先级**：将 MX 记录的优先级设置为可用的最高值，通常为 **0**。
    
      有关优先级的详细信息，请参阅[什么是 MX 优先级？](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)
    
   - **主机名**：**@**
    
   - **指向地址**：粘贴你刚刚从 Microsoft 365 复制的“**指向地址**”值。 
    
   - **TTL**：将此值设置为 **1 小时**或等效的分钟数 (**60**)、秒数 (**3600**)等。 
    
7. 保存记录。
    
删除其他所有 MX 记录。
  
如果此域中存在将电子邮件发送到除 Microsoft 365 以外的其他地址的任何 MX 记录，将其全部删除。
  
## <a name="add-three-cname-records"></a>添加 3 条 CNAME 记录
<a name="BKMK_add_MX"> </a>

::: moniker range="o365-worldwide"

请按照下列步骤添加 Microsoft 365 所需的三条 CNAME 记录。 如果 Microsoft 365 中列出了其他 CNAME 记录，则按照此处所示的相同常规步骤进行添加。
  
在 DNS 主机的网站中，您将创建三条新的 CNAME 记录，通常一次一条。
  
1. 在新记录的框中，键入或复制并粘贴以下值。 添加前三条新记录后，请选择创建另一条 CNAME 记录。
    
      |||||
      |:-----|:-----|:-----|:-----|
      |**记录类型** <br/> |**主机** <br/> |**指向** <br/> |**TTL** <br/> |
      |CNAME（别名）  <br/> |autodiscover  <br/> |autodiscover.outlook.com  <br/> |1 小时  <br/> |
      |CNAME（别名）  <br/> |lyncdiscover  <br/> |webdir.online.lync.com  <br/> |1 小时  <br/> |
      |CNAME（别名）  <br/> |sip  <br/> |sipdir.online.lync.com  <br/> |1 小时  <br/> |
   
   > [!NOTE]
   > 对于“**TTL**”：将此值设置为 **1 小时**或等效的分钟数 (**60**)、秒数 (**3600**)等。 > 这些记录不适用于 Exchange、Lync、或 Skype for Business 混合部署。 
  
2. 完成后，保存记录。
    
::: moniker-end
::: moniker range="o365-germany"

请按照下列步骤添加 Microsoft 365 所需的三条 CNAME 记录。 如果 Microsoft 365 中列出了其他 CNAME 记录，则按照此处所示的相同常规步骤进行添加。
  
在 DNS 主机的网站中，您将创建三条新的 CNAME 记录，通常一次一条。
  
1. 在新记录的框中，键入或复制并粘贴以下值。 添加前三条新记录后，请选择创建另一条 CNAME 记录。
    
    |||||
    |:-----|:-----|:-----|:-----|
    |**记录类型** <br/> |**主机** <br/> |**指向** <br/> |**TTL** <br/> |
    |CNAME（别名）  <br/> |autodiscover  <br/> |autodiscover-outlook.office.de  <br/> |1 小时  <br/> |
    |CNAME（别名）  <br/> |lyncdiscover  <br/> |webdir.online.skype.de  <br/> |1 小时  <br/> |
    |CNAME（别名）  <br/> |sip  <br/> |sipdir.online.lync.de  <br/> |1 小时  <br/> |
   
     > [!NOTE]
     > 对于“**TTL**”：将此值设置为 **1 小时**或等效的分钟数 (**60**)、秒数 (**3600**)等。 > 这些记录不适用于 Exchange、Lync、或 Skype for Business 混合部署。 
  
2. 完成后，保存记录。
    
::: moniker-end

::: moniker range="o365-21vianet"

请按照下列步骤添加 Microsoft 365 所需的三条 CNAME 记录。 如果 Microsoft 365 中列出了其他 CNAME 记录，则按照此处所示的相同常规步骤进行添加。
  
在 DNS 主机的网站中，您将创建三条新的 CNAME 记录，通常一次一条。
  
1. 在新记录的框中，键入或复制并粘贴以下值。 添加前三条新记录后，请选择创建另一条 CNAME 记录。
    
    |||||
    |:-----|:-----|:-----|:-----|
    |**记录类型** <br/> |**主机** <br/> |**指向** <br/> |**TTL** <br/> |
    |CNAME（别名）  <br/> |自动发现  <br/> |autodiscover.partner.outlook.cn  <br/> |1 小时  <br/> |
    |CNAME（别名）  <br/> |lyncdiscover  <br/> |webdir.online.partner.lync.cn  <br/> |1 小时  <br/> |
    |CNAME（别名）  <br/> |sip  <br/> |sipdir.online.partner.lync.cn  <br/> |1 小时  <br/> |
   
     > [!NOTE]
     > 对于“**TTL**”：将此值设置为 **1 小时**或等效的分钟数 (**60**)、秒数 (**3600**)等。 > 这些记录不适用于 Exchange、Lync、或 Skype for Business 混合部署。 
  
2. 完成后，保存记录。
    
::: moniker-end

## <a name="add-two-cname-records-for-mobile-device-management-mdm-for-microsoft-365"></a>为适用于 Microsoft 365 的移动设备管理 (MDM) 添加两个 CNAME 记录
<a name="BKMK_add_MX"> </a>

::: moniker range="o365-worldwide"

> [!IMPORTANT]
> 如果你有 Microsoft 365 的移动设备管理 (MDM)，则必须创建另外两个 CNAME 记录。 创建流程与你用于其他四个 CNAME 记录的流程一样，但需提供下表中的值。 > （如果您没有 MDM，则可以跳过此步骤。） 
  
   |||||
   |:-----|:-----|:-----|:-----|
   |**记录类型** <br/> |**主机** <br/> |**指向** <br/> |**TTL** <br/> |
   |CNAME（别名）  <br/> |EnterpriseRegistration  <br/> |EnterpriseRegistration.windows.net  <br/> |1 小时  <br/> |
   |CNAME（别名）  <br/> |EnterpriseEnrollment  <br/> |EnterpriseEnrollment.manage.microsoft.com  <br/> |1 小时  <br/> |
   
::: moniker-end

::: moniker range="o365-germany"

> [!IMPORTANT]
> 如果你有 Microsoft 365 的移动设备管理 (MDM)，则必须创建另外两个 CNAME 记录。 创建流程与你用于其他四个 CNAME 记录的流程一样，但需提供下表中的值。 > （如果您没有 MDM，则可以跳过此步骤。） 
  
   |||||
   |:-----|:-----|:-----|:-----|
   |**记录类型** <br/> |**主机** <br/> |**指向** <br/> |**TTL** <br/> |
   |CNAME（别名）  <br/> |enterpriseregistration  <br/> |enterpriseregistration.microsoftonline.de  <br/> |1 小时  <br/> |
   |CNAME（别名）  <br/> |enterpriseenrollment  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> |1 小时  <br/> |
   
::: moniker-end

## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>为 SPF 添加 TXT 记录以帮助防止垃圾邮件
<a name="BKMK_add_MX"> </a>

::: moniker range="o365-worldwide"

> [!IMPORTANT]
> 一个域所拥有的 SPF 的 TXT 记录不能超过一个。 如果域具有多个 SPF 记录，你将收到电子邮件错误，其中随附发送和垃圾邮件分类问题。 如果你的域已有 SPF 记录，请不要为 Microsoft 365 创建新记录。 可以将所需的 Microsoft 365 值添加到当前记录，这样就拥有包含两组值的*单个* SPF 记录。
  
在 DNS 主机的网站上，编辑现有的 SPF 记录或为 SPF 创建新的 TXT 记录。
  
> [!IMPORTANT]
> SPF 专为防止欺骗而设计，但是 SPF 无法防御某些骗术。 为防止这些欺骗，在你设置 SPF 后，也应该为 Microsoft 365 配置 DKIM 和 DMARC。 若要开始配置，请参阅[使用 DKIM 验证从 Microsoft 365 中的域发送的出站电子邮件](https://technet.microsoft.com/library/mt695945%28v=exchg.150%29.aspx)。 然后，请参阅[使用 DMARC 验证 Microsoft 365 中的电子邮件](https://technet.microsoft.com/library/mt734386%28v=exchg.150%29.aspx)。 
  
1. 在新记录的框中，键入或复制并粘贴以下适用于你的情况的值集。
    
    |||||
    |:-----|:-----|:-----|:-----|
    |**记录类型** <br/> |**Host** <br/> |**TXT 值** <br/> |**TTL** <br/> |
    |TXT（文本）  <br/> |@  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **注意：** 我们建议您复制并粘贴此条目，以保证正确保留所有空格。           |1 小时  <br/> |
   
    对于“**TTL**”：将此值设置为 **1 小时**或等效的分钟数 (**60**)、秒数 (**3600**)等。 
    
2. 完成后，保存记录。
    
3. 若要验证 SPF 记录，请使用以下任一 [SPF 验证工具](https://docs.microsoft.com/office365/admin/setup/domains-faq#how-can-i-validate-spf-records-for-my-domain)。

::: moniker-end

::: moniker range="o365-germany"

> [!IMPORTANT]
> 一个域所拥有的 SPF 的 TXT 记录不能超过一个。 如果域具有多个 SPF 记录，你将收到电子邮件错误，其中随附发送和垃圾邮件分类问题。 如果你的域已有 SPF 记录，请不要为 Microsoft 365 创建新记录。 可以将所需的 Microsoft 365 值添加到当前记录，这样就拥有包含两组值的*单个* SPF 记录。 
  
在 DNS 主机的网站上，编辑现有的 SPF 记录或为 SPF 创建新的 TXT 记录。
  
> [!IMPORTANT]
> SPF 专为防止欺骗而设计，但是 SPF 无法防御某些骗术。 为防止这些欺骗，在你设置 SPF 后，也应该为 Microsoft 365 配置 DKIM 和 DMARC。 若要开始配置，请参阅[使用 DKIM 验证从 Microsoft 365 中的域发送的出站电子邮件](https://technet.microsoft.com/library/mt695945%28v=exchg.150%29.aspx)。 然后，请参阅[使用 DMARC 验证 Microsoft 365 中的电子邮件](https://technet.microsoft.com/library/mt734386%28v=exchg.150%29.aspx)。 
  
1. 在新记录的框中，键入或复制并粘贴以下适用于你的情况的值集。
    
    |||||
    |:-----|:-----|:-----|:-----|
    |**记录类型**|**Host**|**TXT 值**|**TTL**|
    |TXT（文本）|@|v=spf1 include:spf.protection.outlook.de -all <br/>  我们建议您复制并粘贴此条目，以保证正确保留所有空格。           |1 小时|
   
    对于“**TTL**”：将此值设置为 **1 小时**或等效的分钟数 (**60**)、秒数 (**3600**)等。 
    
2. 完成后，保存记录。
    
3. 若要验证 SPF 记录，请使用以下任一 [SPF 验证工具](https://docs.microsoft.com/office365/admin/setup/domains-faq#how-can-i-validate-spf-records-for-my-domain)。
    
::: moniker-end

::: moniker range="o365-21vianet"

> [!IMPORTANT]
> 一个域所拥有的 SPF 的 TXT 记录不能超过一个。 如果域具有多个 SPF 记录，你将收到电子邮件错误，其中随附发送和垃圾邮件分类问题。 如果你的域已有 SPF 记录，请不要为 Microsoft 365 创建新记录。 可以将所需的 Microsoft 365 值添加到当前记录，这样就拥有包含两组值的*单个* SPF 记录。 
  
在 DNS 主机的网站上，编辑现有的 SPF 记录或为 SPF 创建新的 TXT 记录。
  
> [!IMPORTANT]
> SPF 专为防止欺骗而设计，但是 SPF 无法防御某些骗术。 为防止这些欺骗，在你设置 SPF 后，也应该为 Microsoft 365 配置 DKIM 和 DMARC。 若要开始配置，请参阅[使用 DKIM 验证从 Microsoft 365 中的域发送的出站电子邮件](https://technet.microsoft.com/library/mt695945%28v=exchg.150%29.aspx)。 然后，请参阅[使用 DMARC 验证 Microsoft 365 中的电子邮件](https://technet.microsoft.com/library/mt734386%28v=exchg.150%29.aspx)。 
  
1. 在新记录的框中，键入或复制并粘贴以下适用于你的情况的值集。
    
    |||||
    |:-----|:-----|:-----|:-----|
    |**记录类型**|**Host**|**TXT 值**|**TTL**|
    |TXT（文本）|@|v=spf1 include:spf.protection.partner.outlook.cn -all> [!NOTE]> 我们建议您复制并粘贴此条目，以保证正确保留所有空格。           |1 小时|
   
    对于“**TTL**”：将此值设置为 **1 小时**或等效的分钟数 (**60**)、秒数 (**3600**)等。 
    
2. 完成后，保存记录。
    
3. 若要验证 SPF 记录，请使用以下任一 [SPF 验证工具](https://docs.microsoft.com/office365/admin/setup/domains-faq#how-can-i-validate-spf-records-for-my-domain)。
    
::: moniker-end

## <a name="add-two-srv-records"></a>添加两条 SRV 记录
<a name="BKMK_add_MX"> </a>

::: moniker range="o365-worldwide"

在 DNS 主机的网站中，您将创建两条新的 SRV 记录，通常一次一条。 即在网站中添加第一条 SRV 记录后，请选择创建另一条 SRV 记录。
  
1. 在新记录的框中，键入或复制并粘贴以下值。 **（如果 DNS 主机中的所有这些都不是单独字段，请参阅以下有关创建 SRV 记录的说明。）**
    
    ||||||||||
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |**记录类型** <br/> |**名称** <br/> |**目标** <br/> |**协议** <br/> |**服务** <br/> |**优先级** <br/> |**权重** <br/> |**端口** <br/> |**TTL** <br/> |
    |SRV（服务）  <br/> |@  <br/> （或，如果不允许使用 @ 则留空）  <br/> |sipdir.online.lync.com  <br/> |_tls  <br/> |_sip  <br/> |100  <br/> |{1}  <br/> |4:43  <br/> |1 小时  <br/> |
    |SRV（服务）  <br/> |@  <br/> （或，如果不允许使用 @ 则留空）  <br/> |sipfed.online.lync.com  <br/> |_tcp  <br/> |_sipfederationtls  <br/> |100  <br/> |{1}  <br/> |5061  <br/> |1 小时  <br/> |
   
    > [!NOTE]
    >  对于**名称**：如果你的 DNS 主机不允许将此设置为 **@**，请将其保留为空。 当 DNS 主机的“服务”和“协议”值有单独字段时，*只能*使用此方法。 否则，查看下面的服务和协议说明。 
    > 
    >  对于**服务**和**协议**：如果 DNS 主机未提供这些用于 SRV 记录的字段，必须将“**服务**”和“**协议**”值指定为记录的“**名称**”值。 （注意：根据 DNS 主机，“**名称**”字段可能被称为其他名称，如： “**主机**”、“**主机名**”或“**子域**”。）若要设置组合值，可创建一个字符串，数值使用圆点分隔。  例如，“**名称**”：_sip._tls 
    > 
    >  对于“**优先级**”、“**权重**”和“ **端口**”：如果 DNS 主机未提供用于 SRV 记录的这些字段，必须将其指定为记录的“**目标**”值。 （注意：根据 DNS 主机，“**目标**”字段可能被称为其他名称，如： “**内容**”、“**IP 地址**”或“**目标主机**”。）若要设置组合值，可创建一个字符串，数值使用空格分隔并以圆点为结尾。 值必须采用此顺序包含：优先级、权重、端口、目标。 例如：“**目标**”：100 1 443 sipdir.online.lync.com。 
    > 
    >  **优先级**、**权重**和**端口**变体：有些 DNS 主机分别提供部分但非全部所需的字段。 对于这些 DNS 主机网站，指定不单独显示为组合字符串，以确定记录的“**目标**”值。 （注意：根据 DNS 主机，“**目标**”字段可能被称为其他名称，如： “**内容**”、“**IP 地址**”或“**目标主机**”。）若要设置组合值，可针对未单独显示的字段创建一个字符串，数值使用空格分隔并以圆点为结尾。 值必须“*按顺序*”包含，但保留单独字段可用的值：优先级、权重、端口、目标。 例如，当“优先级”具有单独的字段时，请仅连接“权重”、“端口”和“目标”值：**目标**：1 443 sipdir.online.lync.com 
    > 
    > 对于“**TTL**”：将此值设置为 **1 小时**或等效的分钟数 (**60**)、秒数 (**3600**)等。 
  
2. 完成后，保存记录。
    
    > [!NOTE]
    >  DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。 
  
::: moniker-end


::: moniker range="o365-germany"

在 DNS 主机的网站中，您将创建两条新的 SRV 记录，通常一次一条。 即在网站中添加第一条 SRV 记录后，请选择创建另一条 SRV 记录。
  
1. 在新记录的框中，键入或复制并粘贴以下值。 **（如果 DNS 主机中的所有这些都不是单独字段，请参阅以下有关创建 SRV 记录的说明。）**
    
    ||||||||||
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |**记录类型** <br/> |**名称** <br/> |**目标** <br/> |**协议** <br/> |**服务** <br/> |**优先级** <br/> |**权重** <br/> |**端口** <br/> |**TTL** <br/> |
    |SRV（服务）  <br/> |@  <br/> （或，如果不允许使用 @ 则留空）  <br/> |sipdir.online.lync.de  <br/> |_tls  <br/> |_sip  <br/> |100  <br/> |{1}  <br/> |4:43  <br/> |1 小时  <br/> |
    |SRV（服务）  <br/> |@  <br/> （或，如果不允许使用 @ 则留空）  <br/> |sipfed.online.lync.de  <br/> |_tcp  <br/> |_sipfederationtls  <br/> |100  <br/> |{1}  <br/> |5061  <br/> |1 小时  <br/> |
   
    > [!NOTE]
    >  对于**名称**：如果你的 DNS 主机不允许将此设置为 **@**，请将其保留为空。 当 DNS 主机的“服务”和“协议”值有单独字段时，*只能*使用此方法。 否则，查看下面的服务和协议说明。 
    > 
    >  对于**服务**和**协议**：如果 DNS 主机未提供这些用于 SRV 记录的字段，必须将“**服务**”和“**协议**”值指定为记录的“**名称**”值。 （注意：根据 DNS 主机，“**名称**”字段可能被称为其他名称，如： “**主机**”、“**主机名**”或“**子域**”。）若要设置组合值，可创建一个字符串，数值使用圆点分隔。 >  例如：“**名称**”：_sip._tls 
    > 
    >  对于“**优先级**”、“**权重**”和“ **端口**”：如果 DNS 主机未提供用于 SRV 记录的这些字段，必须将其指定为记录的“**目标**”值。 （注意：根据 DNS 主机，“**目标**”字段可能被称为其他名称，如： “**内容**”、“**IP 地址**”或“**目标主机**”。）若要设置组合值，可创建一个字符串，数值使用空格分隔并以圆点为结尾。 值必须采用此顺序包含：优先级、权重、端口、目标。 >  例如：“**目标**”：100 1 443 sipdir.online.lync.de。 
    > 
    >  **优先级**、**权重**和**端口**变体：有些 DNS 主机分别提供部分但非全部所需的字段。 对于这些 DNS 主机网站，指定不单独显示为组合字符串，以确定记录的“**目标**”值。 （注意：根据 DNS 主机，“**目标**”字段可能被称为其他名称，如： “**内容**”、“**IP 地址**”或“**目标主机**”。）若要设置组合值，可针对未单独显示的字段创建一个字符串，数值使用空格分隔并以圆点为结尾。 值必须“*按顺序*”包含，但保留单独字段可用的值：优先级、权重、端口、目标。 >  例如，当“优先级”具有单独的字段时，请仅连接“权重”、“端口”和“目标”值：**目标**：1 443 sipdir.online.lync.de 
    > 
    >  对于“**TTL**”：将此值设置为 **1 小时**或等效的分钟数 (**60**)、秒数 (**3600**)等。 
  
2. 完成后，保存记录。
    
    > [!NOTE]
    >  DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。 
  
::: moniker-end


::: moniker range="o365-21vianet"

在 DNS 主机的网站中，您将创建两条新的 SRV 记录，通常一次一条。 即在网站中添加第一条 SRV 记录后，请选择创建另一条 SRV 记录。
  
1. 在新记录的框中，键入或复制并粘贴以下值。 **（如果 DNS 主机中的所有这些都不是单独字段，请参阅以下有关创建 SRV 记录的说明。）**
    
    ||||||||||
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |**记录类型** <br/> |**名称** <br/> |**目标** <br/> |**协议** <br/> |**服务** <br/> |**优先级** <br/> |**权重** <br/> |**端口** <br/> |**TTL** <br/> |
    |SRV（服务）  <br/> |@  <br/> （或，如果不允许使用 @ 则留空）  <br/> |sipdir.online.partner.lync.cn  <br/> |_tls  <br/> |_sip  <br/> |100  <br/> |{1}  <br/> |4:43  <br/> |1 小时  <br/> |
    |SRV（服务）  <br/> |@  <br/> （或，如果不允许使用 @ 则留空）  <br/> |sipfed.online.partner.lync.cn  <br/> |_tcp  <br/> |_sipfederationtls  <br/> |100  <br/> |{1}  <br/> |5061  <br/> |1 小时  <br/> |
   
    > [!NOTE]
    >  对于**名称**：如果你的 DNS 主机不允许将此设置为 **@**，请将其保留为空。 当 DNS 主机的“服务”和“协议”值有单独字段时，*只能*使用此方法。 否则，查看下面的服务和协议说明。 
    > 
    >  对于**服务**和**协议**：如果 DNS 主机未提供这些用于 SRV 记录的字段，必须将“**服务**”和“**协议**”值指定为记录的“**名称**”值。 （注意：根据 DNS 主机，“**名称**”字段可能被称为其他名称，如： “**主机**”、“**主机名**”或“**子域**”。）若要设置组合值，可创建一个字符串，数值使用圆点分隔。 >  例如：“**名称**”：_sip._tls 
    > 
    >  对于“**优先级**”、“**权重**”和“ **端口**”：如果 DNS 主机未提供用于 SRV 记录的这些字段，必须将其指定为记录的“**目标**”值。 （注意：根据 DNS 主机，“**目标**”字段可能被称为其他名称，如： “**内容**”、“**IP 地址**”或“**目标主机**”。）若要设置组合值，可创建一个字符串，数值使用空格分隔并以圆点为结尾。 值必须采用此顺序包含：优先级、权重、端口、目标。 >  例如：“**目标**”：100 1 443 sipdir.online.partner.lync.cn。 
    > 
    >  **优先级**、**权重**和**端口**变体：有些 DNS 主机分别提供部分但非全部所需的字段。 对于这些 DNS 主机网站，指定不单独显示为组合字符串，以确定记录的“**目标**”值。 （注意：根据 DNS 主机，“**目标**”字段可能被称为其他名称，如： “**内容**”、“**IP 地址**”或“**目标主机**”。）若要设置组合值，可针对未单独显示的字段创建一个字符串，数值使用空格分隔并以圆点为结尾。 值必须“*按顺序*”包含，但保留单独字段可用的值：优先级、权重、端口、目标。 >  例如，当“优先级”具有单独的字段时，请仅连接“权重”、“端口”和“目标”值：**目标**：1 443 sipdir.online.partner.lync.cn 
    > 
    >  对于“**TTL**”：将此值设置为 **1 小时**或等效的分钟数 (**60**)、秒数 (**3600**)等。 
  
2. 完成后，保存记录。
    
    > [!NOTE]
    >  DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。 
  
::: moniker-end

## <a name="more-about-updating-dns-records"></a>了解有关更新 DNS 记录的详细信息
<a name="BKMK_MoreAbout"> </a>

 **如果知道如何更新域 DNS 主机上的 DNS 主机**，使用 Microsoft 365 DNS 值编辑域的 DNS 主机，例如设置 MX 记录或 SPF 记录。 [执行以下步骤](../get-help-with-domains/information-for-dns-records.md)查找要使用的特定值，或在逐步执行时在域设置向导中查看。
  
 **如果需要一些帮助来了解如何添加所需 DNS 记录的信息**，参阅[设置域（特定于主机的说明）](https://docs.microsoft.com/office365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions?view=o365-worldwide)，请首先[收集创建 Microsoft 365 DNS 记录所需的信息](../get-help-with-domains/information-for-dns-records.md)。 然后使用本主题中的常规步骤设置你的域的 DNS 记录，以便可以将域用于 Microsoft 365 服务，如电子邮件。
  
 **如果没有要使用自定义域的网站**，可以让 Microsoft 365 设置和管理你的域的 DNS 记录，而不是自己执行所有设置。 了解 Microsoft 365 中[用于为自定义域设置和管理 DNS 记录的两个选项](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)。 
  

