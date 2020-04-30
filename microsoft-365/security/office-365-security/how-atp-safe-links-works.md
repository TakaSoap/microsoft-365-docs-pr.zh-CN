---
title: ATP 安全链接的工作原理
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: Admin
ms.date: ''
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: "\"安全链接\" 功能可提供对 Office 文档中的超链接和电子邮件中的超链接的单击时间验证。 阅读本文，了解 ATP 安全链接的工作原理。"
ms.openlocfilehash: 7887c3c2920f472d4baa7ff899c3e3b4f704385d
ms.sourcegitcommit: 60c1932dcca249355ef7134df0ceb0e57757dc81
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/29/2020
ms.locfileid: "43943707"
---
# <a name="how-atp-safe-links-works"></a><span data-ttu-id="9cf37-104">ATP 安全链接的工作原理</span><span class="sxs-lookup"><span data-stu-id="9cf37-104">How ATP Safe Links works</span></span>
> [!IMPORTANT] 
> <span data-ttu-id="9cf37-105">为了使 Office 365 ATP 安全链接正常运行，所有服务都必须为同一版本。</span><span class="sxs-lookup"><span data-stu-id="9cf37-105">For Office 365 ATP Safe Links to operate correctly, all of the services need to be at the same version.</span></span>
         
## <a name="how-atp-safe-links-works-with-urls-in-email"></a><span data-ttu-id="9cf37-106">ATP 安全链接如何处理电子邮件中的 Url</span><span class="sxs-lookup"><span data-stu-id="9cf37-106">How ATP Safe Links works with URLs in email</span></span>

<span data-ttu-id="9cf37-107">从较高的层次来看， [ATP 安全链接](atp-safe-links.md)保护对电子邮件中的 url 的工作方式（托管在 Office 365 中，而不是在本地中）：</span><span class="sxs-lookup"><span data-stu-id="9cf37-107">At a high level, here's how [ATP Safe Links](atp-safe-links.md) protection works for URLs in email (hosted in Office 365, not on-premises):</span></span>
  
1. <span data-ttu-id="9cf37-108">用户接收包含 Url 的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="9cf37-108">People receive email messages, some of which contain URLs.</span></span>
    
2. <span data-ttu-id="9cf37-109">所有电子邮件都通过 Exchange Online 保护，其中应用了 internet 协议（IP）和信封筛选器、基于签名的恶意软件保护、反垃圾邮件和反恶意软件筛选器。</span><span class="sxs-lookup"><span data-stu-id="9cf37-109">All email goes through Exchange Online Protection, where internet protocol (IP) and envelope filters, signature-based malware protection, anti-spam and anti-malware filters are applied.</span></span> 
    
3. <span data-ttu-id="9cf37-110">电子邮件到达用户的收件箱。</span><span class="sxs-lookup"><span data-stu-id="9cf37-110">Email arrives in people's inboxes.</span></span>
    
4. <span data-ttu-id="9cf37-111">用户登录到 Office 365，并转到其电子邮件收件箱。</span><span class="sxs-lookup"><span data-stu-id="9cf37-111">A user signs in to Office 365, and goes to their email inbox.</span></span>
    
5. <span data-ttu-id="9cf37-112">用户打开一封电子邮件，然后单击电子邮件中的 URL。</span><span class="sxs-lookup"><span data-stu-id="9cf37-112">The user opens an email message, and clicks on a URL in the email message.</span></span>
    
6. <span data-ttu-id="9cf37-113">ATP 安全链接功能将在打开网站之前立即检查 URL。</span><span class="sxs-lookup"><span data-stu-id="9cf37-113">The ATP Safe Links feature immediately checks the URL before opening the website.</span></span> <span data-ttu-id="9cf37-114">该 URL 被标识为 "阻止"、"恶意" 或 "安全"。</span><span class="sxs-lookup"><span data-stu-id="9cf37-114">The URL is identified as blocked, malicious, or safe.</span></span>
        
   - <span data-ttu-id="9cf37-115">如果 URL 指向的网站包含在组织的[自定义阻止 url 列表](set-up-a-custom-blocked-urls-list-wtih-atp.md)中，则会打开一个[警告页面](atp-safe-links-warning-pages.md)。</span><span class="sxs-lookup"><span data-stu-id="9cf37-115">If the URL is to a website that is included in the organization's [custom blocked URLs list](set-up-a-custom-blocked-urls-list-wtih-atp.md), a [warning page](atp-safe-links-warning-pages.md) opens.</span></span> 
    
   - <span data-ttu-id="9cf37-116">如果 URL 指向已确定为恶意的网站，将打开 "[警告" 页](atp-safe-links-warning-pages.md)。</span><span class="sxs-lookup"><span data-stu-id="9cf37-116">If the URL is to a website that has been determined to be malicious, a [warning page](atp-safe-links-warning-pages.md) opens.</span></span> 
    
   - <span data-ttu-id="9cf37-117">如果 URL 转到一个可下载的文件，并且您的组织的[ATP 安全链接策略](set-up-atp-safe-links-policies.md)已配置为扫描此类内容，则会检查下载的文件。</span><span class="sxs-lookup"><span data-stu-id="9cf37-117">If the URL goes to a downloadable file and your organization's [ATP Safe Links policies](set-up-atp-safe-links-policies.md) are configured to scan such content, the downloadable file is checked.</span></span> 
    
   - <span data-ttu-id="9cf37-118">如果确定该 URL 是安全的，则会打开该网站。</span><span class="sxs-lookup"><span data-stu-id="9cf37-118">If the URL is determined to be safe, the website opens.</span></span>
    
## <a name="how-atp-safe-links-works-with-urls-in-office-documents"></a><span data-ttu-id="9cf37-119">ATP 安全链接如何处理 Office 文档中的 Url</span><span class="sxs-lookup"><span data-stu-id="9cf37-119">How ATP Safe Links works with URLs in Office documents</span></span> 

<span data-ttu-id="9cf37-120">从较高的层次来看， [ATP 安全链接](atp-safe-links.md)保护在 Microsoft 365 应用程序中适用于企业或商业高级应用程序的 Url （Windows、Mac 上的当前版本的 Word、Excel 和 PowerPoint），或在浏览器中、在 windows 上的 Visio、在浏览器中使用 OneNote 的 Office 应用程序）：</span><span class="sxs-lookup"><span data-stu-id="9cf37-120">At a high level, here's how [ATP Safe Links](atp-safe-links.md) protection works for URLs in Microsoft 365 Apps for enterprise or Business Premium applications (current versions of Word, Excel, and PowerPoint on Windows, Mac, or in a browser, Office apps on iOS or Android devices, Visio on Windows, OneNote in a browser):</span></span>
  
1. <span data-ttu-id="9cf37-121">用户已在其计算机、智能手机或平板电脑上安装了适用于企业或商业高级的 Microsoft 365 应用程序。</span><span class="sxs-lookup"><span data-stu-id="9cf37-121">People have installed Microsoft 365 Apps for enterprise or Business Premium on their computer, smartphone, or tablet.</span></span> <span data-ttu-id="9cf37-122">（或者，他们在浏览器中使用 Office。）</span><span class="sxs-lookup"><span data-stu-id="9cf37-122">(Or, they are using Office in their browser.)</span></span>
    
2. <span data-ttu-id="9cf37-123">用户打开 Word、Excel、PowerPoint、OneNote （在浏览器中）或 Visio （在桌面上），并使用其工作或学校帐户登录到 Office 365 企业版。</span><span class="sxs-lookup"><span data-stu-id="9cf37-123">A user opens a Word, Excel, PowerPoint, OneNote (in the browser), or Visio (on desktop), and signs in to Office 365 Enterprise using their work or school account.</span></span> <span data-ttu-id="9cf37-124">文档包含 Url。</span><span class="sxs-lookup"><span data-stu-id="9cf37-124">The document contains URLs.</span></span>
    
3. <span data-ttu-id="9cf37-125">当用户单击文档中的某个 URL 时，ATP 安全链接服务将检查该链接。</span><span class="sxs-lookup"><span data-stu-id="9cf37-125">When the user clicks on a URL in the document, the link is checked by the ATP Safe Links service.</span></span>
    
   - <span data-ttu-id="9cf37-126">如果 URL 指向的网站包含在组织的[自定义阻止 url 列表](set-up-a-custom-blocked-urls-list-wtih-atp.md)中，则会向用户提供一个[警告页面](atp-safe-links-warning-pages.md)。</span><span class="sxs-lookup"><span data-stu-id="9cf37-126">If the URL is to a website that is included in the organization's [custom blocked URLs list](set-up-a-custom-blocked-urls-list-wtih-atp.md), the user is taken to a [warning page](atp-safe-links-warning-pages.md).</span></span>
    
   - <span data-ttu-id="9cf37-127">如果 URL 指向已确定为恶意的网站，则会向用户提供[警告页面](atp-safe-links-warning-pages.md)。</span><span class="sxs-lookup"><span data-stu-id="9cf37-127">If the URL is to a website that has been determined to be malicious, the user is taken to a [warning page](atp-safe-links-warning-pages.md).</span></span>
    
   - <span data-ttu-id="9cf37-128">如果 URL 转到可下载的文件，并且已将[ATP 安全链接策略](set-up-atp-safe-links-policies.md)配置为扫描此类下载，则会检查可下载的文件。</span><span class="sxs-lookup"><span data-stu-id="9cf37-128">If the URL goes to a downloadable file and the [ATP Safe Links policies](set-up-atp-safe-links-policies.md) are configured to scan such downloads, the downloadable file is checked.</span></span> 
    
   - <span data-ttu-id="9cf37-129">如果该 URL 被认为是安全的，则会将用户转到该网站。</span><span class="sxs-lookup"><span data-stu-id="9cf37-129">If the URL is considered safe, the user is taken to the website.</span></span>
      
   - <span data-ttu-id="9cf37-130">如果 URL 检查失败，安全链接的保护将不会触发。</span><span class="sxs-lookup"><span data-stu-id="9cf37-130">If the URL check fails, Safe Links' protection will not trigger.</span></span> <span data-ttu-id="9cf37-131">在桌面客户端上，将在继续进入网站之前警告用户。</span><span class="sxs-lookup"><span data-stu-id="9cf37-131">On the desktop clients, the user will be warned before proceeding through to the site.</span></span>
      
> [!NOTE]
> <span data-ttu-id="9cf37-132">在每个会话开始时可能需要几秒钟的时间来验证用户是否已启用 Office 的 ATP 安全链接。</span><span class="sxs-lookup"><span data-stu-id="9cf37-132">It may take several seconds at the beginning of each session to verify that the user has ATP Safe Links for Office enabled.</span></span> 
      
