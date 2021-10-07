---
title: DNS 基础
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: high
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- okr_smb
- AdminTemplateSet
- admindeeplinkMAC
search.appverid:
- MET150
- MOE150
- GEA150
- BSA160
ms.assetid: 854b6b2b-0255-4089-8019-b765cff70377
ROBOTS: NOINDEX
description: 域名系统将计算机主机名映射到 IP 地址，了解 DNS 和域注册机构基本信息可帮助管理域。
ms.openlocfilehash: 3195e6ba1e8483a5444eb0f8046add1e3e7725f3
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60164772"
---
# <a name="dns-basics"></a>DNS 基础

 如果找不到要查找的内容，请 **[查看域常见问题解答](../setup/domains-faq.yml)**。 
  
::: moniker range="o365-worldwide"

域名（如 contoso.com）可通过全球范围的域注册机构和数据库托管。 域名系统（DNS ）在可人工读取的计算机主机名与网络设备所用的 IP 地址之间进行映射。 理解 DNS 和域注册机构的基础知识，有助于管理域。

## <a name="watch-domains--dns-an-overview"></a>观看：域和 DNS：概述
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/c005f2a4-90ad-46fe-b1ab-90f41f2a9d53?autoplay=false]
  
::: moniker-end

::: moniker range="o365-germany"

域名（如 contoso.com）可通过全球范围的域注册机构和数据库托管。 域名系统（DNS ）在可人工读取的计算机主机名与网络设备所用的 IP 地址之间进行映射。 理解 DNS 和域注册机构的基础知识，有助于管理域。

## <a name="watch-domains--dns-an-overview"></a>观看：域和 DNS：概述
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/c005f2a4-90ad-46fe-b1ab-90f41f2a9d53?autoplay=false]
  
::: moniker-end

::: moniker range="o365-21vianet"

域名（如 contoso.com）可通过全球范围的域注册机构和数据库托管。 域名系统（DNS ）在可人工读取的计算机主机名与网络设备所用的 IP 地址之间进行映射。 理解 DNS 和域注册机构的基础知识，有助于管理员管理域。
  
::: moniker-end

## <a name="what-are-domain-names"></a>什么是域名？

域名用于 URL 和电子邮件地址，这些域名具有不同级别。 例如，mail.contoso.com 是一个具有以下三种级别的域名：
  
- **.com** 是顶级域名 
    
- **contoso** 是第二级域名 
    
- **mail** 是第三级域名 
    
为什么使用第三级域名？ 可能希望针对市场营销或博客使用不同的域名。 例如 blog.contoso.com。 通常添加二级域（如 contoso.com）以与 Microsoft 一起使用，但也可以根据需要使用第三级域。
  
在 [Microsoft 365 和 Office 365 平台服务说明](/office365/servicedescriptions/office-365-platform-service-description/domains)中了解有关对于每种类型的服务你可以使用域执行的操作的更多信息。
  
## <a name="understand-dns-record-types"></a>了解 DNS 记录类型

域 DNS 主机上存储的 DNS 记录用于定向域的通信。 下表介绍了常用的 DNS 记录以及如何使用。
  
|**NS（名称服务器）记录**|**标识属于域的“权威名称服务器”的名称服务器。 当你更改域的名称服务器时，你将更改管理 DNS 记录的位置以及 DNS 系统查找邮件服务器等相关信息的位置。 Microsoft 有其自己的名称服务器，或者你也可以一直使用你的域已设置好的名称服务器。**|
|:-----|:-----|
|记录（地址记录）  <br/> |让一个域名和一个 IP 地址产生关联。  <br/> |
|CNAME（别名或规范名称）记录  <br/> |将一个域重定向到 DNS 系统中的另一个域。当名称服务器查找一个域，且找到一个 CNAME 记录时，它会用 CNAME 替换第一个域名，然后查找新的名称。  <br/> |
|MX（邮件交换器）记录  <br/> |指向应发送您的电子邮件的位置。它还具有一个优先级字段，以便您可以按优先顺序向不同服务器发送邮件。  <br/> |
|SPF（发送方策略框架）记录  <br/> |有助于防止电子邮件欺诈和网络钓鱼的 TXT 记录。  <br/> |
|SRV（服务）记录  <br/> |由 Skype for Business Online 和 Exchange Online 用来协调 Microsoft 服务间的信息流。 例如在 Outlook Web App 中查看联机状态、使用 Skype for Business Online、Skype 或其他即使消息工具与其他公司的人员交流，SRV 记录必不可少。  <br/> |
|TTL（生存时间）  <br/> |服务器查找更新版本之前名称服务器保留 DNS 记录的时间量。  <br/> |
   
## <a name="how-does-dns-work"></a>DNS 如何工作？

使用云服务（如 Microsoft 365）设置域包括更改或添加域的 [DNS 记录](dns-basics.md)。 由于 DNS、域名系统和域名在 Internet 中的工作方式，需要这些更改才能知道从何处发送或查找内容，例如电子邮件和网站。 
  
Internet 已设置为使用 DNS 或域名系统（允许我们使用熟悉的名称，如 contoso.com），可在标有难以记住的数字（称为 Internet 协议 (IP) 地址）的范围下查找实际的特定 Internet 位置。 IP 地址类似于 70.42.241.42，因此，您可以更轻松地使用域名来识别电子邮件主机和网站等位置。
  
简而言之：DNS 记录告诉 Internet 在何处发送电子邮件（如 joe@contoso.com）或查找使用域名的网站（如 www.contoso.com）。 存储合适的信息至正确的域 DNS 记录中时，DNS 系统正确路由，例如电子邮件能够到达 Microsoft 365，而不是其它地方。
  
域的 DNS 记录可以通过其他方式发挥作用。 例如，Exchange 检查允许 Outlook 自动设置与合适 Exchange Server 的连接的 DNS 记录。
  
### <a name="dns-records-help-the-internet-send-email-to-the-right-place"></a>DNS 记录帮助 Internet 将电子邮件发送到正确的位置

如上所述，DNS 实际会路由 Internet 上的流量，将友好域名映射到难于记住的 IP 地址。  一个 DNS 记录（称为 MX 记录）专门用于向合适的主机发送电子邮件。 
  
DNS 记录就是域信息的数据库。 记录及其数值保存在区域文件中，文件中含有各域记录及其数值的列表。 域注册机构和其他 DNS 托管公司在网站上提供用户界面，因此可在域区域文件中编辑记录。 在那里可更新域的 MX 记录，发送电子邮件至 Microsoft 365。
  
 *当将你的电子邮件更改为 Microsoft 365 时，在下一步中更新的域的 MX 记录，那么发送到该域的所有电子邮件都将开始传送到 Microsoft 365。*  如果其他用户的电子邮件使用你的域，必须为每个这些用户设置 Microsoft 365 邮箱。 
  
听起来很复杂？ 可能是，我们将引导你完成 Microsoft 域设置中的每个步骤。
  
### <a name="dns-tells-the-internet-where-to-look-for-websites-too"></a>DNS 告知 Internet 在哪里查找网站

输入网站地址（例如 www.contoso.com）时，Internet 首先会检查其中一个 DNS 服务器，查找用于（本例中）contoso.com 的名称服务器（NS）记录。 NS 记录告诉 Internet 应在哪里查找含有所有此域的其他 DNS 记录的区域文件。 存在大量相互连接的 DNS 服务器。 服务器协同工作，跟踪所有已注册域名，域名必须唯一，而且是域区域文件所在的位置。
  
::: moniker range="o365-worldwide"

假设 contoso.com 的 NS 记录为 “godaddy.com”。 现在 Internet 知道，GoDaddy.com 是查找区域文件的位置，区域文件列出了用于 contoso.com 的所有其他 DNS 记录。 这些 DNS 记录包含 MS 记录，显示发送 contoso.com 电子邮件和其他记录的位置。 如果 MX 拥有一个数值 "send email to Microsoft 365"，表示所有发送至 contoso.com 电子邮件地址（如 joe@contoso.com）的所有电子邮件将被发送到那里。 随后只要此位置有一个名为“joe”的收件箱，电子邮件就会被递送。

::: moniker-end

::: moniker range="o365-germany"

假设 contoso.com 的 NS 记录为 “godaddy.com”。 现在 Internet 知道，GoDaddy.com 是查找区域文件的位置，区域文件列出了用于 contoso.com 的所有其他 DNS 记录。 这些 DNS 记录包含 MS 记录，显示发送 contoso.com 电子邮件和其他记录的位置。 如果 MX 拥有一个数值 "send email to Microsoft 365"，表示所有发送至 contoso.com 电子邮件地址（如 joe@contoso.com）的所有电子邮件将被发送到那里。 随后只要此位置有一个名为“joe”的收件箱，电子邮件就会被递送。

::: moniker-end

::: moniker range="o365-21vianet"

假设 contoso.com 的 NS 记录为 “hichina.com”。 现在 Internet 知道，hichina.com 是查找区域文件的位置，区域文件列出了用于 contoso.com 的所有其他 DNS 记录。 这些 DNS 记录包含 MS 记录，显示发送 contoso.com 电子邮件和其他记录的位置。 如果 MX 拥有一个数值 "send email to Microsoft 365"，表示所有发送至 contoso.com 电子邮件地址（如 joe@contoso.com）的所有电子邮件将被发送到那里。 随后只要此位置有一个名为“joe”的收件箱，电子邮件就会被递送。

::: moniker-end

如果在域设置步骤中设置域，必须输入以使用 Microsoft 365 工作的实际值为你列出。 若要手动执行设置，可将值复制并粘贴到 DNS 主机上的正确 DNS 记录（MX 记录、CNAME 记录等）中，这可能是域注册机构，但不强制。
  
::: moniker range="o365-worldwide"

为什么域区域文件可能是在域注册机构之外的其他位置？ 嗯，你可能会在域注册机构（如 GoDaddy）中注册域名，但 DNS 记录可能被托管在其他位置，如独立 DNS 托管公司或 web 托管公司。 域 NS 记录存储的信息，能够使 DNS 服务器知道在哪里查找。

::: moniker-end

::: moniker range="o365-germany"

为什么域区域文件可能是在域注册机构之外的其他位置？ 嗯，你可能会在域注册机构（如 GoDaddy）中注册域名，但 DNS 记录可能被托管在其他位置，如独立 DNS 托管公司或 web 托管公司。 域 NS 记录存储的信息，能够使 DNS 服务器知道在哪里查找。

::: moniker-end

::: moniker range="o365-21vianet"

为什么域区域文件可能是在域注册机构之外的其他位置？ 嗯，你可能会在域注册机构（如 HiChina）中注册域名，但 DNS 记录可能被托管在其他位置，如独立 DNS 托管公司或 web 托管公司。 域 NS 记录存储的信息，能够使 DNS 服务器知道在哪里查找。

::: moniker-end

::: moniker range="o365-worldwide"
## <a name="why-add-a-domain-in-microsoft-365"></a>为什么要在 Microsoft 365 中添加域？


添加自定义域（如 fourthcoffee.com）至 Microsoft 365，让你能够使用更短、更熟悉的电子邮件和 userID 及服务。 注册 Microsoft 365 帐户时，将会[提供一个域供使用](../setup/domains-faq.yml)，但它包含 "onmicrosoft.com"。 如果计划将 Microsoft 365 用于电子邮件，许多人更愿意添加组织或商业域。 
  
> [!NOTE]
> 如果只希望下载和使用 Microsoft 应用（如 Outlook 或 Word），则不需要添加域：[在 PC 或 Mac 上安装 Office](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658) 即可。 
  
您可以在 Microsoft 365 中为您的电子邮件、公共网站和即时消息地址使用您的域名。
  
- **电子邮件：** 域名可以让你自定义电子邮件，因此可以使用比附带账户的 [初始 onmicrosoft.com 电子邮件](../setup/domains-faq.yml)更短、更易记的地址。 因此替代 joe@contoso.onmicrosoft.com，电子邮件地址（也是用于登录到 Microsoft 365 的工作帐户）可能是 joe@contoso.com。 
    
- **网站：** 如果你有包含 SharePoint Online 公共网站的 Microsoft 365 订阅（不能再购买），你的公共网站附带有如下初始地址：contoso-public.sharepoint.com。 如果你为你的企业设置网站，则可以使用自定义域名将网站地址重命名为类似于 www.contoso.com 的地址。 
    
- **即时消息**：也可以自定义 Skype for Business Online 地址以使用你的域名，以便你组织中的人员可以在 Skype for Business Online 上使用更容易记住的较短地址（如 joe@contoso.com）相互联系。 
    
::: moniker-end

::: moniker range="o365-germany"
## <a name="why-add-a-domain-in-microsoft-365"></a>为什么要在 Microsoft 365 中添加域？


添加自定义域（如 fourthcoffee.com）至 Microsoft 365，让你能够使用更短、更熟悉的电子邮件和 userID 及服务。 注册 Microsoft 365 帐户时，将会[提供一个域供使用](../setup/domains-faq.yml)，但它包含 "onmicrosoft.com"。 如果计划将 Microsoft 365 用于电子邮件，许多人更愿意添加组织或商业域。 
  
> [!NOTE]
> 如果只希望下载和使用 Microsoft 365 应用（如 Outlook 或 Word），则不需要添加域：[在 PC 或 Mac 上安装 Office](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658) 即可。 
  
您可以在 Microsoft 365 中为您的电子邮件、公共网站和即时消息地址使用您的域名。
  
- **电子邮件：** 域名可以让你自定义电子邮件，因此可以使用比附带账户的 [初始 onmicrosoft.com 电子邮件](../setup/domains-faq.yml)更短、更易记的地址。 因此替代 joe@contoso.onmicrosoft.com，电子邮件地址（也是用于登录到 Microsoft 365 的工作帐户）可能是 joe@contoso.com。 
    
- **网站：** 如果你有包含 SharePoint Online 公共网站的订阅（不能再购买），你的公共网站附带有如下初始地址：contoso-public.sharepoint.com。 如果你为你的企业设置网站，则可以使用自定义域名将网站地址重命名为类似于 www.contoso.com 的地址。 
    
- **即时消息**：也可以自定义 Skype for Business Online 地址以使用你的域名，以便你组织中的人员可以在 Skype for Business Online 上使用更容易记住的较短地址（如 joe@contoso.com）相互联系。 
    
::: moniker-end

## <a name="the-dns-records-required-for-microsoft-365"></a>Microsoft 365 所需的 DNS 记录

Microsoft 365 需要几个 DNS 记录才能使用你的域。除了设置你的域的 MX 记录来将电子邮件发送到 Microsoft 365，还有一些记录可以帮助你完成以下任务：确保 Outlook 可以自动连接到正确的 Exchange 服务器，设置即时消息，帮助防止垃圾电子邮件等。
  
可[查找值列表](information-for-dns-records.md)来设置域。 它们包含在 <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Microsoft 365 管理中心</a> 中。 
  
或者，如果正在计划部署，可能需要查看 Microsoft 365 所需的所有 DNS 记录的列表、其功能以及示例值。请查看[Microsoft 365 的外部域名系统记录](../../enterprise/external-domain-name-system-records.md)。
  
## <a name="next-steps"></a>后续步骤

请查看以下内容之一： 
  
- 不确定域的注册位置？ [获取查找域名注册机构的帮助。](find-your-domain-registrar.md)
- 了解[为什么您必须完成向导步骤操作](../setup/add-domain.md)，然后才能将您的域与 Microsoft 365 配合使用。

## <a name="related-content"></a>相关内容

[域常见问题解答](../setup/domains-faq.yml)（文章）\
[查找并修复添加域或 DNS 记录之后出现的问题](find-and-fix-issues.md)（文章）\
[管理域](/admin)（链接页）