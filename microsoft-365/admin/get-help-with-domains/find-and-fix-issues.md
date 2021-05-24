---
title: 查找并修复添加域或 DNS 记录之后出现的问题
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
- Adm_TOC
- Adm_O365_Setup
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 40398b0b-bdd0-4afd-ab5e-b5ae6b7990bf
description: 了解如何通过确保正确设置 DNS 记录来跟踪在设置自定义域时遇到的任何问题。
ms.openlocfilehash: 70beb877251c333766a0963316287796eb81d595
ms.sourcegitcommit: 686f192e1a650ec805fe8e908b46ca51771ed41f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/24/2021
ms.locfileid: "52623961"
---
# <a name="find-and-fix-issues-after-adding-your-domain-or-dns-records"></a><span data-ttu-id="f4b80-103">查找并修复添加域或 DNS 记录之后出现的问题</span><span class="sxs-lookup"><span data-stu-id="f4b80-103">Find and fix issues after adding your domain or DNS records</span></span>

 <span data-ttu-id="f4b80-104">如果找不到要查找的内容，请 **[查看域常见问题解答](../setup/domains-faq.yml)**。</span><span class="sxs-lookup"><span data-stu-id="f4b80-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="f4b80-105">设置域以使用Microsoft 365可能非常困难。</span><span class="sxs-lookup"><span data-stu-id="f4b80-105">Getting your domain set up to work with Microsoft 365 can be challenging.</span></span> <span data-ttu-id="f4b80-106">DNS 系统要求严格，很难使用，并且，你的域的 DNS 设置会影响重要的业务活动，如电子邮件！</span><span class="sxs-lookup"><span data-stu-id="f4b80-106">The DNS system is nitpicky to work with, and the DNS setup for your domain affects important business activities, like email!</span></span>

> [!NOTE]
> <span data-ttu-id="f4b80-107">可以通过检查域的状态来检查域的问题。</span><span class="sxs-lookup"><span data-stu-id="f4b80-107">You can check for problems with your domain by checking its status.</span></span> <span data-ttu-id="f4b80-108">转到"**设置**  >  **域**"，在"状态"列中 **查看** 通知。</span><span class="sxs-lookup"><span data-stu-id="f4b80-108">Go to **Setup** > **Domains** and view the notifications in the **Status** column.</span></span> <span data-ttu-id="f4b80-109">如果看到问题，请选择三个点 (执行) ，然后选择"检查运行状况 **"。**</span><span class="sxs-lookup"><span data-stu-id="f4b80-109">If you see an issue, select the three dots (more actions), and then choose **Check health**.</span></span> <span data-ttu-id="f4b80-110">打开的窗格将描述您的域发生的任何问题。</span><span class="sxs-lookup"><span data-stu-id="f4b80-110">The pane that opens will describe any issues occurring with your domain.</span></span>
  
## <a name="whats-going-on"></a><span data-ttu-id="f4b80-111">What's going on?</span><span class="sxs-lookup"><span data-stu-id="f4b80-111">What's going on?</span></span>

- [<span data-ttu-id="f4b80-112">无法验证你的域？</span><span class="sxs-lookup"><span data-stu-id="f4b80-112">Can't verify your domain?</span></span>](#cant-verify-your-domain)
    
- [<span data-ttu-id="f4b80-113">Outlook运行不工作？</span><span class="sxs-lookup"><span data-stu-id="f4b80-113">Outlook isn't working?</span></span>](#outlook-isnt-working)
    
- [<span data-ttu-id="f4b80-114">每个人的电子邮件已切换到Microsoft 365，而您只想切换您的电子邮件？</span><span class="sxs-lookup"><span data-stu-id="f4b80-114">Everyone's email got switched to Microsoft 365 and you only wanted YOUR email to switch?</span></span>](#everyones-email-got-switched-to-microsoft-365-and-you-only-wanted-your-email-to-switch)

- [<span data-ttu-id="f4b80-115">无法确认非营利组织或学校帐户状态？</span><span class="sxs-lookup"><span data-stu-id="f4b80-115">Can't confirm non-profit or school account status?</span></span>](#cant-confirm-non-profit-or-school-account-status)

- [<span data-ttu-id="f4b80-116">服务无法与域一起运行？</span><span class="sxs-lookup"><span data-stu-id="f4b80-116">Services not working with your domain?</span></span>](#services-not-working-with-your-domain)
    
- [<span data-ttu-id="f4b80-117">访问网站不工作？</span><span class="sxs-lookup"><span data-stu-id="f4b80-117">Accessing your website isn't working?</span></span>](#accessing-your-website-isnt-working)

## <a name="cant-verify-your-domain"></a><span data-ttu-id="f4b80-118">无法验证你的域？</span><span class="sxs-lookup"><span data-stu-id="f4b80-118">Can't verify your domain?</span></span>
<span data-ttu-id="f4b80-119"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="f4b80-119"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="f4b80-120">域验证未按计划方式执行，有几个常见原因：</span><span class="sxs-lookup"><span data-stu-id="f4b80-120">There are a couple of common reasons that domain verification doesn't work as it should:</span></span>
  
1. <span data-ttu-id="f4b80-p103">**验证记录值不完全正确。** 请在 DNS 主机处仔细检查你已复制确切值并将其粘贴到 TXT 验证记录中。一个常见的问题是未包含记录的 "MS=" 部分。我们也需要的！</span><span class="sxs-lookup"><span data-stu-id="f4b80-p103">**The verification record value isn't quite correct.** Doublecheck that you've copied and pasted the exact value into the TXT verification record at your DNS host. One common issue is not including the "MS=" part of the record. We need that too!</span></span> 
    
2. <span data-ttu-id="f4b80-125">**尚未保存记录。**</span><span class="sxs-lookup"><span data-stu-id="f4b80-125">**The record hasn't been saved.**</span></span> <span data-ttu-id="f4b80-126">在一些 DNS 主机上，你需要采取额外步骤来保存区域文件（存储 DNS记录的地方），以便它将通过 Internet 更新。</span><span class="sxs-lookup"><span data-stu-id="f4b80-126">At some DNS hosts, you have to take an extra step to save the zone file (where the DNS record is stored) so that it will update across the Internet.</span></span> <span data-ttu-id="f4b80-127">确保已保存更改，Microsoft 365并验证记录。</span><span class="sxs-lookup"><span data-stu-id="f4b80-127">Make sure you've saved your changes so Microsoft 365 can see and verify the record.</span></span> 
    
3. <span data-ttu-id="f4b80-128">**记录尚未通过 Internet 更新。**</span><span class="sxs-lookup"><span data-stu-id="f4b80-128">**The record hasn't updated across the Internet.**</span></span> <span data-ttu-id="f4b80-129">通常只需几分钟，我们就能看到新记录，但有时可能需要几个小时。</span><span class="sxs-lookup"><span data-stu-id="f4b80-129">It typically only takes a few minutes for us to be able to see the new record, but occasionally it can take as long as a few hours.</span></span> 
    
## <a name="outlook-isnt-working"></a><span data-ttu-id="f4b80-130">Outlook 无法正常工作？</span><span class="sxs-lookup"><span data-stu-id="f4b80-130">Outlook isn't working?</span></span>
<span data-ttu-id="f4b80-131"><a name="BKMK_OutlookBroken"> </a></span><span class="sxs-lookup"><span data-stu-id="f4b80-131"><a name="BKMK_OutlookBroken"> </a></span></span>

<span data-ttu-id="f4b80-132">如果你已为域正确设置了你的 MX 记录和其他 DNS 记录，但邮件不起作用，让我们帮助你 [解决 Outlook 问题](/exchange/troubleshoot/outlook-connectivity/outlook-connection-issues)。</span><span class="sxs-lookup"><span data-stu-id="f4b80-132">If you've set up your MX record and other DNS records correctly for your domain, but mail doesn't work, let us help you [fix your Outlook problems](/exchange/troubleshoot/outlook-connectivity/outlook-connection-issues).</span></span>
  
## <a name="everyones-email-got-switched-to-microsoft-365-and-you-only-wanted-your-email-to-switch"></a><span data-ttu-id="f4b80-133">每个人的电子邮件已切换到Microsoft 365，而您只想切换您的电子邮件？</span><span class="sxs-lookup"><span data-stu-id="f4b80-133">Everyone's email got switched to Microsoft 365 and you only wanted YOUR email to switch?</span></span>
<span data-ttu-id="f4b80-134"><a name="BKMK_EmailSwitched"> </a></span><span class="sxs-lookup"><span data-stu-id="f4b80-134"><a name="BKMK_EmailSwitched"> </a></span></span>

<span data-ttu-id="f4b80-135">将域添加到 Microsoft 365 时，你的域的 MX 记录通常由你或 Microsoft 365) 更新 (以指向 Microsoft 365，并且发送到该域的所有电子邮件都将开始Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="f4b80-135">When you add your domain to Microsoft 365, typically your domain's MX record is updated (by you or Microsoft 365) to point to Microsoft 365, and ALL email sent to that domain will start coming to Microsoft 365.</span></span> <span data-ttu-id="f4b80-136">在更改 MX 记录之前，请确保Microsoft 365域中拥有电子邮件的所有人创建邮箱。</span><span class="sxs-lookup"><span data-stu-id="f4b80-136">Make sure you've created mailboxes in Microsoft 365 for everyone who has email on your domain BEFORE you change the MX record.</span></span>
  
<span data-ttu-id="f4b80-137">如果您不想将域中的每个人的电子邮件移动到其他域中，Microsoft 365？</span><span class="sxs-lookup"><span data-stu-id="f4b80-137">What if you don't want to move email for everyone on your domain to Microsoft 365?</span></span> <span data-ttu-id="f4b80-138">你可以采取一些[步骤来Microsoft 365一些电子邮件地址进行试点](../setup/domains-faq.yml)。</span><span class="sxs-lookup"><span data-stu-id="f4b80-138">You can take steps to [pilot Microsoft 365 with just a few email addresses instead](../setup/domains-faq.yml).</span></span>
  
## <a name="cant-confirm-non-profit-or-school-account-status"></a><span data-ttu-id="f4b80-139">无法确认非营利组织或学校帐户状态？</span><span class="sxs-lookup"><span data-stu-id="f4b80-139">Can't confirm non-profit or school account status?</span></span>
<span data-ttu-id="f4b80-140"><a name="BKMK_validateAcct"> </a></span><span class="sxs-lookup"><span data-stu-id="f4b80-140"><a name="BKMK_validateAcct"> </a></span></span>

<span data-ttu-id="f4b80-141">当你只需验证组织的域而不需要设置任何服务时，有两种情况。</span><span class="sxs-lookup"><span data-stu-id="f4b80-141">There are a couple of scenarios when you just need to verify your organization's domain and not set up any services.</span></span> <span data-ttu-id="f4b80-142">例如，为了证明Microsoft 365组织有资格使用学校订阅。</span><span class="sxs-lookup"><span data-stu-id="f4b80-142">For example, to prove to Microsoft 365 that your organization qualifies for a school subscription.</span></span>
  
<span data-ttu-id="f4b80-143">请查看验证你的Microsoft 365域以证明所有权、非营利组织或教育状态或激活[Yammer](../setup/domains-faq.yml)以确保你已完成所有必需的步骤中的指南。</span><span class="sxs-lookup"><span data-stu-id="f4b80-143">Check out the guidance in [Verify your Microsoft 365 domain to prove ownership, nonprofit or education status, or to activate Yammer](../setup/domains-faq.yml) to make sure you've completed all the required steps.</span></span> <span data-ttu-id="f4b80-144">每种情况都有一些不同。</span><span class="sxs-lookup"><span data-stu-id="f4b80-144">It's a little different for each situation.</span></span> 
  
## <a name="services-not-working-with-your-domain"></a><span data-ttu-id="f4b80-145">这些服务对你的域不起作用？</span><span class="sxs-lookup"><span data-stu-id="f4b80-145">Services not working with your domain?</span></span>
<span data-ttu-id="f4b80-146"><a name="BKMK_Test"> </a></span><span class="sxs-lookup"><span data-stu-id="f4b80-146"><a name="BKMK_Test"> </a></span></span>

<span data-ttu-id="f4b80-147">我们可帮助你跟踪域的 DNS 设置问题。</span><span class="sxs-lookup"><span data-stu-id="f4b80-147">We can help you track down issues with your domain's DNS setup.</span></span> <span data-ttu-id="f4b80-148">Microsoft 365中的域疑难解答将显示任何需要修复的记录，以及记录需要设置为什么。</span><span class="sxs-lookup"><span data-stu-id="f4b80-148">The domains troubleshooter in Microsoft 365 will show you any records that need fixing, and exactly what the records need to be set to.</span></span> 

> [!TIP]
> <span data-ttu-id="f4b80-149">已正确设置你的 DNS，但桌面版 Outlook 的邮件仍然无法工作？</span><span class="sxs-lookup"><span data-stu-id="f4b80-149">Got your DNS set up correctly, but mail doesn't work in Outlook on your desktop?</span></span> <span data-ttu-id="f4b80-150">查看使用[邮件流时](/exchange/mail-flow-best-practices/mail-flow-best-practices)可以Microsoft 365，以确保业务设置正确。</span><span class="sxs-lookup"><span data-stu-id="f4b80-150">Check out the [different mail flow scenarios you can have with Microsoft 365](/exchange/mail-flow-best-practices/mail-flow-best-practices) to make sure you've got things set up correctly for your business.</span></span> <span data-ttu-id="f4b80-151">或发送电子邮件到下面的地址以获取更多疑难解答帮助：[修复 Outlook 问题](/exchange/troubleshoot/outlook-connectivity/outlook-connection-issues)。</span><span class="sxs-lookup"><span data-stu-id="f4b80-151">Or get more troubleshooting help with email here: [Fix Outlook problems](/exchange/troubleshoot/outlook-connectivity/outlook-connection-issues).</span></span> 
  
## <a name="accessing-your-website-isnt-working"></a><span data-ttu-id="f4b80-152">无法正常访问你的网站？</span><span class="sxs-lookup"><span data-stu-id="f4b80-152">Accessing your website isn't working?</span></span>
<span data-ttu-id="f4b80-153"><a name="BKMK_Website"> </a></span><span class="sxs-lookup"><span data-stu-id="f4b80-153"><a name="BKMK_Website"> </a></span></span>

<span data-ttu-id="f4b80-154">如果您已修复任何 DNS 问题，但仍遇到问题，请尝试执行下列操作之一。</span><span class="sxs-lookup"><span data-stu-id="f4b80-154">If you've fixed any DNS issues and you're still having trouble, try one of the following.</span></span>
  
- <span data-ttu-id="f4b80-155">用户无法在 www.mydomain.com 上访问您的网站：[跟踪网站问题](../setup/add-domain.md)</span><span class="sxs-lookup"><span data-stu-id="f4b80-155">People can't get to your website at www.mydomain.com: [Track down website issues](../setup/add-domain.md)</span></span>
    
- <span data-ttu-id="f4b80-156">无法将 A 记录或 CNAME 记录更新为指向您的网站：更新自定义[DNS 记录](../setup/add-domain.md)Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="f4b80-156">You can't update your A record or CNAME record to point to your website: [Update custom DNS records in Microsoft 365](../setup/add-domain.md)</span></span>

## <a name="related-content"></a><span data-ttu-id="f4b80-157">相关内容</span><span class="sxs-lookup"><span data-stu-id="f4b80-157">Related content</span></span>

<span data-ttu-id="f4b80-158">[疑难解答：审核已验证域更改的数据](/azure/active-directory/reports-monitoring/troubleshoot-audit-data-verified-domain) (文章) </span><span class="sxs-lookup"><span data-stu-id="f4b80-158">[Troubleshoot: Audit data on verified domain change](/azure/active-directory/reports-monitoring/troubleshoot-audit-data-verified-domain) (article)</span></span>\
<span data-ttu-id="f4b80-159">[域常见问题](../setup/domains-faq.yml) （文章）</span><span class="sxs-lookup"><span data-stu-id="f4b80-159">[Domains FAQ](../setup/domains-faq.yml) (article)</span></span>

