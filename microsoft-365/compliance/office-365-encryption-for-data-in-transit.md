---
title: 加密传输中的数据
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
ms.collection:
- Strat_O365_Enterprise
- M365-security-compliance
- Strat_O365_Enterprise
description: 在本文中，我们将简单说明 Microsoft 如何在传输过程中加密 Microsoft 365 客户数据。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 7ee869308549398a9df00ed42975b4aeedb666a4
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/05/2020
ms.locfileid: "44033600"
---
# <a name="encryption-for-data-in-transit"></a><span data-ttu-id="ad1d4-103">加密传输中的数据</span><span class="sxs-lookup"><span data-stu-id="ad1d4-103">Encryption for data in transit</span></span>

<span data-ttu-id="ad1d4-104">除了保护静态客户数据之外，Microsoft 还使用加密技术来保护传输中的客户数据。</span><span class="sxs-lookup"><span data-stu-id="ad1d4-104">In addition to protecting customer data at rest, Microsoft uses encryption technologies to protect customer data in transit.</span></span> 

<span data-ttu-id="ad1d4-105">数据在传输中：</span><span class="sxs-lookup"><span data-stu-id="ad1d4-105">Data is in transit:</span></span>

- <span data-ttu-id="ad1d4-106">当客户端计算机与 Microsoft 服务器通信时;</span><span class="sxs-lookup"><span data-stu-id="ad1d4-106">when a client machine communicates with a Microsoft server;</span></span>
- <span data-ttu-id="ad1d4-107">当 Microsoft 服务器与另一台 Microsoft 服务器通信时;并</span><span class="sxs-lookup"><span data-stu-id="ad1d4-107">when a Microsoft server communicates with another Microsoft server; and</span></span>
- <span data-ttu-id="ad1d4-108">当 Microsoft 服务器与非 Microsoft 服务器通信时（例如，Exchange Online 将电子邮件传递到第三方电子邮件服务器）。</span><span class="sxs-lookup"><span data-stu-id="ad1d4-108">when a Microsoft server communicates with a non-Microsoft server (e.g., Exchange Online delivering email to a third-party email server).</span></span>

<span data-ttu-id="ad1d4-109">Microsoft 服务器之间的数据中心之间的通信通过 TLS 或 IPsec 进行，所有面向客户的服务器都使用 TLS 与客户端计算机协商安全会话（例如，Exchange Online 使用带256位密码强度的 TLS 1.2 （FIPS 140-2 级别2验证）。</span><span class="sxs-lookup"><span data-stu-id="ad1d4-109">Inter-data center communications between Microsoft servers takes place over TLS or IPsec, and all customer-facing servers negotiate a secure session using TLS with client machines (e.g., Exchange Online uses TLS 1.2 with 256-bit cipher strength is used (FIPS 140-2 Level 2-validated).</span></span> <span data-ttu-id="ad1d4-110">（有关 Office 365 支持的 TLS 密码套件列表的[加密的技术参考详细信息](technical-reference-details-about-encryption.md)，请参阅。）这适用于客户端（如 Outlook、Skype for Business、Microsoft 团队和 web 上的 Outlook）使用的协议（例如，HTTP、POP3 等）。</span><span class="sxs-lookup"><span data-stu-id="ad1d4-110">(See [Technical reference details about encryption](technical-reference-details-about-encryption.md) for a list of TLS cipher suites supported by Office 365.) This applies to the protocols that are used by clients such as Outlook, Skype for Business, Microsoft Teams, and Outlook on the web (e.g., HTTP, POP3, etc.).</span></span>

<span data-ttu-id="ad1d4-111">公共证书由 Microsoft IT SSL 使用 SSLAdmin （一个内部 Microsoft 工具）颁发，以保护传输信息的机密性。</span><span class="sxs-lookup"><span data-stu-id="ad1d4-111">The public certificates are issued by Microsoft IT SSL using SSLAdmin, an internal Microsoft tool to protect confidentiality of transmitted information.</span></span> <span data-ttu-id="ad1d4-112">Microsoft 颁发的所有证书的长度都至少为2048位，并且 Webtrust 合规性要求 SSLAdmin 确保仅将证书颁发给 Microsoft 拥有的公用 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="ad1d4-112">All certificates issued by Microsoft IT have a minimum of 2048 bits in length, and Webtrust compliance requires SSLAdmin to make sure that certificates are issued only to public IP addresses owned by Microsoft.</span></span> <span data-ttu-id="ad1d4-113">任何无法满足此条件的 IP 地址都将通过异常过程进行路由。</span><span class="sxs-lookup"><span data-stu-id="ad1d4-113">Any IP addresses that fail to meet this criterion are routed through an exception process.</span></span>

<span data-ttu-id="ad1d4-114">所有实现详细信息（如使用的 TLS 版本、是否已启用向前保密（FS））都可公开使用密码套件等的顺序。</span><span class="sxs-lookup"><span data-stu-id="ad1d4-114">All implementation details such as the version of TLS being used, whether Forward Secrecy (FS) is enabled, the order of cipher suites, etc., are available publicly.</span></span> <span data-ttu-id="ad1d4-115">查看这些详细信息的一种方法是使用第三方网站，如[QUALYS SSL 实验室](https://www.ssllabs.com)。</span><span class="sxs-lookup"><span data-stu-id="ad1d4-115">One way to see these details is to use a third-party website, such as [Qualys SSL Labs](https://www.ssllabs.com).</span></span> <span data-ttu-id="ad1d4-116">以下是来自 Qualys 的自动测试页面的链接，这些页面显示以下服务的信息：</span><span class="sxs-lookup"><span data-stu-id="ad1d4-116">Below are the links to automated test pages from Qualys that display information for the following services:</span></span>

- [<span data-ttu-id="ad1d4-117">Office 365 门户</span><span class="sxs-lookup"><span data-stu-id="ad1d4-117">Office 365 Portal</span></span>](https://www.ssllabs.com/ssltest/analyze.html?d=portal.office.com&hideResults=on)
- [<span data-ttu-id="ad1d4-118">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="ad1d4-118">Exchange Online</span></span>](https://www.ssllabs.com/ssltest/analyze.html?d=outlook.office365.com&hideResults=on)
- [<span data-ttu-id="ad1d4-119">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="ad1d4-119">SharePoint Online</span></span>](https://www.ssllabs.com/ssltest/analyze.html?d=microsoft-my.sharepoint.com&hideResults=on)
- [<span data-ttu-id="ad1d4-120">Skype for Business （SIP）</span><span class="sxs-lookup"><span data-stu-id="ad1d4-120">Skype for Business (SIP)</span></span>](https://www.ssllabs.com/ssltest/analyze.html?d=sipdir.online.lync.com)
- [<span data-ttu-id="ad1d4-121">Skype for Business （Web）</span><span class="sxs-lookup"><span data-stu-id="ad1d4-121">Skype for Business (Web)</span></span>](https://www.ssllabs.com/ssltest/analyze.html?d=webdir.online.lync.com&hideResults=on)
- [<span data-ttu-id="ad1d4-122">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="ad1d4-122">Exchange Online Protection</span></span>](https://ssl-tools.net/mailservers/microsoft-com.mail.protection.outlook.com)
- [<span data-ttu-id="ad1d4-123">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ad1d4-123">Microsoft Teams</span></span>](https://www.ssllabs.com/ssltest/analyze.html?d=teams.microsoft.com&latest)

<span data-ttu-id="ad1d4-124">对于 Exchange Online Protection，Url 会因租户名称而异;但是，所有客户都可以使用**microsoft-com.mail.protection.outlook.com**测试 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="ad1d4-124">For Exchange Online Protection, URLs vary by tenant names; however, all customers can test Microsoft 365 using **microsoft-com.mail.protection.outlook.com**.</span></span>
