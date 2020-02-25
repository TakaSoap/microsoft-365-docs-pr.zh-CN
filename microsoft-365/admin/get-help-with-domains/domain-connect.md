---
title: 使用域连接
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
- Adm_TOC
- Adm_O365_Setup
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: ec6f4bd8-5996-4505-ba68-afaf8a141fb9
description: 了解如何使用启用域连接的注册机构并将你的域添加到 Microsoft 365。
ms.openlocfilehash: e014504116e5d19c8413549c802fd110dddfb8df
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/24/2020
ms.locfileid: "42251155"
---
# <a name="using-domain-connect"></a><span data-ttu-id="73a68-103">使用域连接</span><span class="sxs-lookup"><span data-stu-id="73a68-103">Using Domain Connect</span></span>

 <span data-ttu-id="73a68-104">如果找不到要查找的内容，请**[查看域常见问题解答](../setup/domains-faq.md)**。</span><span class="sxs-lookup"><span data-stu-id="73a68-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span>
  
<span data-ttu-id="73a68-105">启用[域连接](https://www.domainconnect.org/)的注册机构允许您将您的域添加到 Microsoft 365，这是一个需要几分钟时间的三步骤过程。</span><span class="sxs-lookup"><span data-stu-id="73a68-105">[Domain Connect ](https://www.domainconnect.org/) enabled registrars let you add your domain to Microsoft 365 in a three-step process that takes minutes.</span></span> 
  
<span data-ttu-id="73a68-106">在向导中，我们将只是确认你拥有域，然后自动设置你的域的记录，因此电子邮件将发送到 Microsoft 365 和其他 Microsoft 365 服务（如团队）使用你的域。</span><span class="sxs-lookup"><span data-stu-id="73a68-106">In the wizard, we'll just confirm that you own the domain, and then automatically set up your domain's records, so email comes to Microsoft 365 and other Microsoft 365 services, like Teams, work with your domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="73a68-107">在开始此设置向导前，请确保你已禁用浏览器中的任何弹出窗口阻止程序。</span><span class="sxs-lookup"><span data-stu-id="73a68-107">Make sure you disable any popup blockers in your browser before you start the setup wizard.</span></span>
  
## <a name="domain-connect-registrars-integrating-with-microsoft-365"></a><span data-ttu-id="73a68-108">与 Microsoft 365 集成的域连接注册机构</span><span class="sxs-lookup"><span data-stu-id="73a68-108">Domain Connect registrars integrating with Microsoft 365</span></span>

- [<span data-ttu-id="73a68-109">1&amp;1 IONOS</span><span class="sxs-lookup"><span data-stu-id="73a68-109">1&amp;1 IONOS</span></span>](https://www.1and1.com/)
- [<span data-ttu-id="73a68-110">123Reg</span><span class="sxs-lookup"><span data-stu-id="73a68-110">123Reg</span></span>](https://www.123-reg.co.uk/)
- [<span data-ttu-id="73a68-111">GoDaddy</span><span class="sxs-lookup"><span data-stu-id="73a68-111">GoDaddy</span></span>](https://www.godaddy.com/)
- [<span data-ttu-id="73a68-112">WordPress</span><span class="sxs-lookup"><span data-stu-id="73a68-112">WordPress</span></span>](https://wordpress.com/)
- [<span data-ttu-id="73a68-113">Plesk</span><span class="sxs-lookup"><span data-stu-id="73a68-113">Plesk</span></span>](https://www.plesk.com/)
- [<span data-ttu-id="73a68-114">MediaTemple</span><span class="sxs-lookup"><span data-stu-id="73a68-114">MediaTemple</span></span>](https://mediatemple.net/)
- <span data-ttu-id="73a68-115">SecureServer 或 WildWestDomains （使用 SecureServer DNS 托管的 GoDaddy 经销商）</span><span class="sxs-lookup"><span data-stu-id="73a68-115">SecureServer or WildWestDomains (GoDaddy resellers using SecureServer DNS hosting)</span></span>
    - [<span data-ttu-id="73a68-116">MadDog 域</span><span class="sxs-lookup"><span data-stu-id="73a68-116">MadDog Domains</span></span>](https://www.maddogdomains.com/)
    - [<span data-ttu-id="73a68-117">CheapNames</span><span class="sxs-lookup"><span data-stu-id="73a68-117">CheapNames</span></span>](https://www.cheapnames.com)

## <a name="what-happens-to-my-email-and-website"></a><span data-ttu-id="73a68-118">我的电子邮件和网站会发生什么情况？</span><span class="sxs-lookup"><span data-stu-id="73a68-118">What happens to my email and website?</span></span>

<span data-ttu-id="73a68-119">完成设置后，你的域的 MX 记录将更新为指向 Microsoft 365，并且你的域的所有电子邮件都将开始进入 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="73a68-119">After you finish setup, the MX record for your domain is updated to point to Microsoft 365 and all email for your domain will start coming to Microsoft 365.</span></span> <span data-ttu-id="73a68-120">请确保你已在 Office 365 中添加用户并为每个在你的域中收到电子邮件的人设置邮箱！</span><span class="sxs-lookup"><span data-stu-id="73a68-120">Make sure you've added users and set up mailboxes in Office 365 for everyone who gets email on your domain!</span></span>
  
<span data-ttu-id="73a68-121">如果你有一个用于你的企业的网站，它将在其所在的位置保持工作。</span><span class="sxs-lookup"><span data-stu-id="73a68-121">If you have a website that you use with your business, it will keep working where it is.</span></span> <span data-ttu-id="73a68-122">域连接设置步骤不会影响您的网站。</span><span class="sxs-lookup"><span data-stu-id="73a68-122">The Domain Connect setup steps don't affect your website.</span></span>