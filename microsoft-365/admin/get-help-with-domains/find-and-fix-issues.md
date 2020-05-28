---
title: 查找并修复添加域或 DNS 记录之后出现的问题
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
- Adm_TOC
- Adm_O365_Setup
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 40398b0b-bdd0-4afd-ab5e-b5ae6b7990bf
description: 了解在设置自定义域时，通过确保正确设置了 DNS 记录来跟踪你遇到的任何问题。
ms.openlocfilehash: e3c66e10a673d840cfddad81a057739b6dfac721
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2020
ms.locfileid: "44399940"
---
# <a name="find-and-fix-issues-after-adding-your-domain-or-dns-records"></a><span data-ttu-id="2f39d-103">查找并修复添加域或 DNS 记录之后出现的问题</span><span class="sxs-lookup"><span data-stu-id="2f39d-103">Find and fix issues after adding your domain or DNS records</span></span>

 <span data-ttu-id="2f39d-104">如果找不到要查找的内容，请**[查看域常见问题解答](../setup/domains-faq.md)**。</span><span class="sxs-lookup"><span data-stu-id="2f39d-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="2f39d-105">将您的域设置为与 Microsoft 365 配合使用可能会非常困难。</span><span class="sxs-lookup"><span data-stu-id="2f39d-105">Getting your domain set up to work with Microsoft 365 can be challenging.</span></span> <span data-ttu-id="2f39d-106">DNS 系统要求严格，很难使用，并且，你的域的 DNS 设置会影响重要的业务活动，如电子邮件！</span><span class="sxs-lookup"><span data-stu-id="2f39d-106">The DNS system is nitpicky to work with, and the DNS setup for your domain affects important business activities, like email!</span></span>

> [!NOTE]
> <span data-ttu-id="2f39d-107">您可以通过检查域的状态检查是否存在问题。</span><span class="sxs-lookup"><span data-stu-id="2f39d-107">You can check for problems with your domain by checking its status.</span></span> <span data-ttu-id="2f39d-108">转到 "**设置**  >  **域**" 并查看 "**状态**" 列中的通知。</span><span class="sxs-lookup"><span data-stu-id="2f39d-108">Go to **Setup** > **Domains** and view the notifications in the **Status** column.</span></span> <span data-ttu-id="2f39d-109">如果出现问题，请选择 "更多操作（三个点）"，然后选择 "**检查运行状况**"。</span><span class="sxs-lookup"><span data-stu-id="2f39d-109">If you see an issue, select More actions (three dots), and then choose **Check health**.</span></span> <span data-ttu-id="2f39d-110">打开的窗格将描述您的域中出现的任何问题。</span><span class="sxs-lookup"><span data-stu-id="2f39d-110">The pane that opens will describe any issues occurring with your domain.</span></span>
  
## <a name="whats-going-on"></a><span data-ttu-id="2f39d-111">What's going on?</span><span class="sxs-lookup"><span data-stu-id="2f39d-111">What's going on?</span></span>

- [<span data-ttu-id="2f39d-112">无法验证你的域？</span><span class="sxs-lookup"><span data-stu-id="2f39d-112">Can't verify your domain?</span></span>](#cant-verify-your-domain)
    
- [<span data-ttu-id="2f39d-113">Outlook 不工作？</span><span class="sxs-lookup"><span data-stu-id="2f39d-113">Outlook isn't working?</span></span>](#outlook-isnt-working)
    
- [<span data-ttu-id="2f39d-114">每个人的电子邮件已切换到 Microsoft 365，并且您仅希望您的电子邮件切换？</span><span class="sxs-lookup"><span data-stu-id="2f39d-114">Everyone's email got switched to Microsoft 365 and you only wanted YOUR email to switch?</span></span>](#everyones-email-got-switched-to-microsoft-365-and-you-only-wanted-your-email-to-switch)

- [<span data-ttu-id="2f39d-115">无法确认非盈利或学校帐户状态？</span><span class="sxs-lookup"><span data-stu-id="2f39d-115">Can't confirm non-profit or school account status?</span></span>](#cant-confirm-non-profit-or-school-account-status)

- [<span data-ttu-id="2f39d-116">服务不能与您的域一起使用？</span><span class="sxs-lookup"><span data-stu-id="2f39d-116">Services not working with your domain?</span></span>](#services-not-working-with-your-domain)
    
- [<span data-ttu-id="2f39d-117">访问你的网站不起作用？</span><span class="sxs-lookup"><span data-stu-id="2f39d-117">Accessing your website isn't working?</span></span>](#accessing-your-website-isnt-working)

## <a name="cant-verify-your-domain"></a><span data-ttu-id="2f39d-118">无法验证你的域？</span><span class="sxs-lookup"><span data-stu-id="2f39d-118">Can't verify your domain?</span></span>
<span data-ttu-id="2f39d-119"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="2f39d-119"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="2f39d-120">域验证未按计划方式执行，有几个常见原因：</span><span class="sxs-lookup"><span data-stu-id="2f39d-120">There are a couple of common reasons that domain verification doesn't work as it should:</span></span>
  
1. <span data-ttu-id="2f39d-p103">**验证记录值不完全正确。** 请在 DNS 主机处仔细检查你已复制确切值并将其粘贴到 TXT 验证记录中。一个常见的问题是未包含记录的 "MS=" 部分。我们也需要的！</span><span class="sxs-lookup"><span data-stu-id="2f39d-p103">**The verification record value isn't quite correct.** Doublecheck that you've copied and pasted the exact value into the TXT verification record at your DNS host. One common issue is not including the "MS=" part of the record. We need that too!</span></span> 
    
2. <span data-ttu-id="2f39d-125">**尚未保存记录。**</span><span class="sxs-lookup"><span data-stu-id="2f39d-125">**The record hasn't been saved.**</span></span> <span data-ttu-id="2f39d-126">在一些 DNS 主机上，你需要采取额外步骤来保存区域文件（存储 DNS记录的地方），以便它将通过 Internet 更新。</span><span class="sxs-lookup"><span data-stu-id="2f39d-126">At some DNS hosts, you have to take an extra step to save the zone file (where the DNS record is stored) so that it will update across the Internet.</span></span> <span data-ttu-id="2f39d-127">请确保您已保存所做的更改，以便 Microsoft 365 能够查看和验证记录。</span><span class="sxs-lookup"><span data-stu-id="2f39d-127">Make sure you've saved your changes so Microsoft 365 can see and verify the record.</span></span> 
    
3. <span data-ttu-id="2f39d-128">**该记录未在 Internet 上更新。**</span><span class="sxs-lookup"><span data-stu-id="2f39d-128">**The record hasn't updated across the Internet.**</span></span> <span data-ttu-id="2f39d-129">通常只需几分钟，我们才能看到新记录，但偶尔可能需要几个小时的时间。</span><span class="sxs-lookup"><span data-stu-id="2f39d-129">It typically only takes a few minutes for us to be able to see the new record, but occasionally it can take as long as a few hours.</span></span> 
    
## <a name="outlook-isnt-working"></a><span data-ttu-id="2f39d-130">Outlook 无法正常工作？</span><span class="sxs-lookup"><span data-stu-id="2f39d-130">Outlook isn't working?</span></span>
<span data-ttu-id="2f39d-131"><a name="BKMK_OutlookBroken"> </a></span><span class="sxs-lookup"><span data-stu-id="2f39d-131"><a name="BKMK_OutlookBroken"> </a></span></span>

<span data-ttu-id="2f39d-132">如果你已为域正确设置了你的 MX 记录和其他 DNS 记录，但邮件不起作用，让我们帮助你 [解决 Outlook 问题](https://docs.microsoft.com/exchange/troubleshoot/outlook-connectivity/outlook-connection-issues)。</span><span class="sxs-lookup"><span data-stu-id="2f39d-132">If you've set up your MX record and other DNS records correctly for your domain, but mail doesn't work, let us help you [fix your Outlook problems](https://docs.microsoft.com/exchange/troubleshoot/outlook-connectivity/outlook-connection-issues).</span></span>
  
## <a name="everyones-email-got-switched-to-microsoft-365-and-you-only-wanted-your-email-to-switch"></a><span data-ttu-id="2f39d-133">每个人的电子邮件已切换到 Microsoft 365，并且您仅希望您的电子邮件切换？</span><span class="sxs-lookup"><span data-stu-id="2f39d-133">Everyone's email got switched to Microsoft 365 and you only wanted YOUR email to switch?</span></span>
<span data-ttu-id="2f39d-134"><a name="BKMK_EmailSwitched"> </a></span><span class="sxs-lookup"><span data-stu-id="2f39d-134"><a name="BKMK_EmailSwitched"> </a></span></span>

<span data-ttu-id="2f39d-135">将域添加到 Microsoft 365 时，通常您的域的 MX 记录将更新（您或 Microsoft 365）以指向 Microsoft 365，发送到该域的所有电子邮件都将开始进入 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="2f39d-135">When you add your domain to Microsoft 365, typically your domain's MX record is updated (by you or Microsoft 365) to point to Microsoft 365, and ALL email sent to that domain will start coming to Microsoft 365.</span></span> <span data-ttu-id="2f39d-136">请确保您已在 Microsoft 365 中为每个在您的域中有电子邮件的用户创建了邮箱，然后再更改 MX 记录。</span><span class="sxs-lookup"><span data-stu-id="2f39d-136">Make sure you've created mailboxes in Microsoft 365 for everyone who has email on your domain BEFORE you change the MX record.</span></span>
  
<span data-ttu-id="2f39d-137">如果您不想将域中每个人的电子邮件移至 Microsoft 365，该怎么办？</span><span class="sxs-lookup"><span data-stu-id="2f39d-137">What if you don't want to move email for everyone on your domain to Microsoft 365?</span></span> <span data-ttu-id="2f39d-138">您可以采取步骤[仅使用几个电子邮件地址来试用 Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)。</span><span class="sxs-lookup"><span data-stu-id="2f39d-138">You can take steps to [pilot Microsoft 365 with just a few email addresses instead](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq).</span></span>
  
## <a name="cant-confirm-non-profit-or-school-account-status"></a><span data-ttu-id="2f39d-139">无法确认非盈利或学校帐户状态？</span><span class="sxs-lookup"><span data-stu-id="2f39d-139">Can't confirm non-profit or school account status?</span></span>
<span data-ttu-id="2f39d-140"><a name="BKMK_validateAcct"> </a></span><span class="sxs-lookup"><span data-stu-id="2f39d-140"><a name="BKMK_validateAcct"> </a></span></span>

<span data-ttu-id="2f39d-141">在以下几种情况下，只需验证组织的域，而不会设置任何服务。</span><span class="sxs-lookup"><span data-stu-id="2f39d-141">There are a couple of scenarios when you just need to verify your organization's domain and not set up any services.</span></span> <span data-ttu-id="2f39d-142">例如，若要证明你的组织符合学校订阅的 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="2f39d-142">For example, to prove to Microsoft 365 that your organization qualifies for a school subscription.</span></span>
  
<span data-ttu-id="2f39d-143">请查看[验证 Microsoft 365 域中的指南，以证明所有权、非盈利或教育状态，或激活 Yammer](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)以确保您已完成所有必需的步骤。</span><span class="sxs-lookup"><span data-stu-id="2f39d-143">Check out the guidance in [Verify your Microsoft 365 domain to prove ownership, nonprofit or education status, or to activate Yammer](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) to make sure you've completed all the required steps.</span></span> <span data-ttu-id="2f39d-144">这在每种情况下稍有不同。</span><span class="sxs-lookup"><span data-stu-id="2f39d-144">It's a little different for each situation.</span></span> 
  
## <a name="services-not-working-with-your-domain"></a><span data-ttu-id="2f39d-145">这些服务对你的域不起作用？</span><span class="sxs-lookup"><span data-stu-id="2f39d-145">Services not working with your domain?</span></span>
<span data-ttu-id="2f39d-146"><a name="BKMK_Test"> </a></span><span class="sxs-lookup"><span data-stu-id="2f39d-146"><a name="BKMK_Test"> </a></span></span>

<span data-ttu-id="2f39d-147">我们可帮助你跟踪域的 DNS 设置问题。</span><span class="sxs-lookup"><span data-stu-id="2f39d-147">We can help you track down issues with your domain's DNS setup.</span></span> <span data-ttu-id="2f39d-148">Microsoft 365 中的 "域" 疑难解答程序将向您显示需要修复的任何记录，以及记录需要设置到的确切内容。</span><span class="sxs-lookup"><span data-stu-id="2f39d-148">The domains troubleshooter in Microsoft 365 will show you any records that need fixing, and exactly what the records need to be set to.</span></span> 

> [!TIP]
> <span data-ttu-id="2f39d-149">已正确设置你的 DNS，但桌面版 Outlook 的邮件仍然无法工作？</span><span class="sxs-lookup"><span data-stu-id="2f39d-149">Got your DNS set up correctly, but mail doesn't work in Outlook on your desktop?</span></span> <span data-ttu-id="2f39d-150">请查看[您可以使用 Microsoft 365 的不同邮件流方案](https://www.microsoft.com/?ref=go)，以确保您已为您的企业正确设置了项目。</span><span class="sxs-lookup"><span data-stu-id="2f39d-150">Check out the [different mail flow scenarios you can have with Microsoft 365](https://www.microsoft.com/?ref=go) to make sure you've got things set up correctly for your business.</span></span> <span data-ttu-id="2f39d-151">或发送电子邮件到下面的地址以获取更多疑难解答帮助：[修复 Outlook 问题](https://docs.microsoft.com/exchange/troubleshoot/outlook-connectivity/outlook-connection-issues)。</span><span class="sxs-lookup"><span data-stu-id="2f39d-151">Or get more troubleshooting help with email here: [Fix Outlook problems](https://docs.microsoft.com/exchange/troubleshoot/outlook-connectivity/outlook-connection-issues).</span></span> 
  
## <a name="accessing-your-website-isnt-working"></a><span data-ttu-id="2f39d-152">无法正常访问你的网站？</span><span class="sxs-lookup"><span data-stu-id="2f39d-152">Accessing your website isn't working?</span></span>
<span data-ttu-id="2f39d-153"><a name="BKMK_Website"> </a></span><span class="sxs-lookup"><span data-stu-id="2f39d-153"><a name="BKMK_Website"> </a></span></span>

<span data-ttu-id="2f39d-154">如果您已修复任何 DNS 问题，但仍遇到问题，请尝试执行下列操作之一。</span><span class="sxs-lookup"><span data-stu-id="2f39d-154">If you've fixed any DNS issues and you're still having trouble, try one of the following.</span></span>
  
- <span data-ttu-id="2f39d-155">用户无法在 www.mydomain.com 上访问您的网站：[跟踪网站问题](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain)</span><span class="sxs-lookup"><span data-stu-id="2f39d-155">People can't get to your website at www.mydomain.com: [Track down website issues](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain)</span></span>
    
- <span data-ttu-id="2f39d-156">您不能更新 A 记录或 CNAME 记录以指向您的网站：[在 Microsoft 365 中更新自定义 DNS 记录](../dns/add-or-edit-custom-dns-records.md)</span><span class="sxs-lookup"><span data-stu-id="2f39d-156">You can't update your A record or CNAME record to point to your website: [Update custom DNS records in Microsoft 365](../dns/add-or-edit-custom-dns-records.md)</span></span>
    
