---
title: 将域添加到 Microsoft 365
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
- Adm_O365_Setup
- Adm_O365
- Adm_TOC
ms.custom:
- TopSMBIssues
- SaRA
- MSStore_Link
- okr_smb
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 6383f56d-3d09-4dcb-9b41-b5f5a5efd611
description: 使用设置向导，通过添加 DNS Microsoft 365 DNS Microsoft 365管理中心将域添加到管理中心。
ms.openlocfilehash: 96849e90a420dc31dbde8c55d5a1108f73f85978
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2021
ms.locfileid: "52535826"
---
# <a name="add-a-domain-to-microsoft-365"></a><span data-ttu-id="89b4a-103">将域添加到 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="89b4a-103">Add a domain to Microsoft 365</span></span>

 <span data-ttu-id="89b4a-104">如果找不到要查找的内容，请 **[查看域常见问题解答](domains-faq.yml)**。</span><span class="sxs-lookup"><span data-stu-id="89b4a-104">**[Check the Domains FAQ](domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
 <span data-ttu-id="89b4a-105">*若要添加、修改或删除域，\*\*你必须*\* 是企业 **或** 企业计划的 [全局管理员](https://products.office.com/business/office)。这些更改会影响整个 *租户，自定义* 管理员或常规用户将无法进行这些更改。\*</span><span class="sxs-lookup"><span data-stu-id="89b4a-105">*To Add, modify or remove domains you **must** be a **Global Administrator** of a [business or enterprise plan](https://products.office.com/business/office). These changes affect the whole tenant, *Customized administrators* or *regular users* won't be able to make these changes.*</span></span>  

 ## <a name="add-a-domain"></a><span data-ttu-id="89b4a-106">添加域</span><span class="sxs-lookup"><span data-stu-id="89b4a-106">Add a domain</span></span>

<span data-ttu-id="89b4a-107">按照以下步骤添加、设置或继续设置域。</span><span class="sxs-lookup"><span data-stu-id="89b4a-107">Follow these steps to add, set up, or continue setting up a domain.</span></span> 

::: moniker range="o365-worldwide"

1. <span data-ttu-id="89b4a-108">转到位于 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> 的管理中心。</span><span class="sxs-lookup"><span data-stu-id="89b4a-108">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

::: moniker-end
::: moniker range="o365-germany"

1. <span data-ttu-id="89b4a-109">转到位于 <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a> 的管理中心。</span><span class="sxs-lookup"><span data-stu-id="89b4a-109">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a>.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="89b4a-110">转到位于 <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a> 的管理中心。</span><span class="sxs-lookup"><span data-stu-id="89b4a-110">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a>.</span></span>

::: moniker-end
    
2. <span data-ttu-id="89b4a-111">转到 **"设置**  >  **域"** 页面。</span><span class="sxs-lookup"><span data-stu-id="89b4a-111">Go to the **Settings** > **Domains** page.</span></span> 

3. <span data-ttu-id="89b4a-112">选择 “**添加域**”。</span><span class="sxs-lookup"><span data-stu-id="89b4a-112">Select **Add domain**.</span></span>
    
4. <span data-ttu-id="89b4a-113">输入要添加的域的名称，然后选择"下一步 **"。**</span><span class="sxs-lookup"><span data-stu-id="89b4a-113">Enter the name of the domain you want to add, then select **Next**.</span></span>
    
5. <span data-ttu-id="89b4a-114">选择您希望如何验证您是否拥有该域。</span><span class="sxs-lookup"><span data-stu-id="89b4a-114">Choose how you want to verify that you own the domain.</span></span>
    
    1. <span data-ttu-id="89b4a-115">如果你的域注册机构[](#domain-connect-registrars-integrating-with-microsoft-365)使用域连接，Microsoft 会[](../get-help-with-domains/domain-connect.md)通过登录你的注册机构并确认连接到你的注册机构来自动Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="89b4a-115">If your domain registrar uses [Domain Connect](#domain-connect-registrars-integrating-with-microsoft-365), Microsoft [will set up your records automatically](../get-help-with-domains/domain-connect.md) by having you sign in to your registrar and confirm the connection to Microsoft 365.</span></span> <span data-ttu-id="89b4a-116">你将返回到管理中心，然后 Microsoft 将自动验证你的域。</span><span class="sxs-lookup"><span data-stu-id="89b4a-116">You'll be returned to the admin center and Microsoft will then automatically verify your domain.</span></span>
    2. <span data-ttu-id="89b4a-117">可使用 TXT 记录验证域。</span><span class="sxs-lookup"><span data-stu-id="89b4a-117">You can use a TXT record to verify your domain.</span></span> <span data-ttu-id="89b4a-118">选择此选项并选择" **下一** 步"以查看有关如何将此 DNS 记录添加到注册机构网站的说明。</span><span class="sxs-lookup"><span data-stu-id="89b4a-118">Select this and select **Next** to see instructions for how to add this DNS record to your registrar's website.</span></span> <span data-ttu-id="89b4a-119">添加记录后，最多可能需要 30 分钟进行验证。</span><span class="sxs-lookup"><span data-stu-id="89b4a-119">This can take up to 30 minutes to verify after you've added the record.</span></span> 
    3. <span data-ttu-id="89b4a-120">你可以将文本文件添加到你的域的网站。</span><span class="sxs-lookup"><span data-stu-id="89b4a-120">You can add a text file to your domain's website.</span></span> <span data-ttu-id="89b4a-121">从安装向导.txt下载文件，然后将该文件上载到网站的顶级文件夹。</span><span class="sxs-lookup"><span data-stu-id="89b4a-121">Select and download the .txt file from the setup wizard, then upload the file to your website's top level folder.</span></span> <span data-ttu-id="89b4a-122">文件的路径应类似于 `http://mydomain.com/ms39978200.txt` ：。</span><span class="sxs-lookup"><span data-stu-id="89b4a-122">The path to the file should look similar to: `http://mydomain.com/ms39978200.txt`.</span></span> <span data-ttu-id="89b4a-123">我们将通过在网站上查找文件来确认你拥有该域。</span><span class="sxs-lookup"><span data-stu-id="89b4a-123">We'll confirm you own the domain by finding the file on your website.</span></span>
    
6. <span data-ttu-id="89b4a-124">选择希望 Microsoft 使用域所需的 DNS 更改。</span><span class="sxs-lookup"><span data-stu-id="89b4a-124">Choose how you want to make the DNS changes required for Microsoft to use your domain.</span></span>
    
    1. <span data-ttu-id="89b4a-125">如果你 **的** 注册机构支持域 [连接，](#domain-connect-registrars-integrating-with-microsoft-365)请选择"为我添加 DNS 记录"，Microsoft [](../get-help-with-domains/domain-connect.md)会通过登录注册机构并确认与注册机构的连接来自动Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="89b4a-125">Choose **Add the DNS records for me** if your registrar supports [Domain Connect](#domain-connect-registrars-integrating-with-microsoft-365), and Microsoft [will set up your records automatically](../get-help-with-domains/domain-connect.md) by having you sign in to your registrar and confirm the connection to Microsoft 365.</span></span>
    2. <span data-ttu-id="89b4a-126">Choose **I'll add the DNS records自己** if you want to attach only specific Microsoft 365 services to your domain or if you want to skip this for now and do this later.</span><span class="sxs-lookup"><span data-stu-id="89b4a-126">Choose **I'll add the DNS records myself** if you want to attach only specific Microsoft 365 services to your domain or if you want to skip this for now and do this later.</span></span> <span data-ttu-id="89b4a-127">**如果确切了解执行内容，请选择此选项。**</span><span class="sxs-lookup"><span data-stu-id="89b4a-127">**Choose this option if you know exactly what you're doing.**</span></span>

7. <span data-ttu-id="89b4a-128">如果选择自己添加 *DNS* 记录，请选择"下一步"，你将看到一个包含要添加到注册机构网站以设置域的所有记录的页面。</span><span class="sxs-lookup"><span data-stu-id="89b4a-128">If you chose to *add DNS records yourself*  , select **Next** and you'll see a page with all the records that you need to add to your registrars website to set up your domain.</span></span> 

    <span data-ttu-id="89b4a-129">如果门户无法识别你的注册机构，你可以[按照以下常规说明操作。](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)</span><span class="sxs-lookup"><span data-stu-id="89b4a-129">If the portal doesn't recognize your registrar, you can [follow these general instructions.](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)</span></span>
    
    <span data-ttu-id="89b4a-130">查看[主机特定说明](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md)列表，以找到你的主机并按照步骤添加所需的全部记录。</span><span class="sxs-lookup"><span data-stu-id="89b4a-130">Check our list of [host-specific instructions](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md) to find your host and follow the steps to add all the records you need.</span></span> 
    
    <span data-ttu-id="89b4a-131">如果不知道你的域的 DNS 托管提供商或域注册机构，请参阅[查找域注册机构或 DNS 托管提供商](../get-help-with-domains/find-your-domain-registrar.md)。</span><span class="sxs-lookup"><span data-stu-id="89b4a-131">If you don't know the DNS hosting provider or domain registrar for your domain, see [Find your domain registrar or DNS hosting provider](../get-help-with-domains/find-your-domain-registrar.md).</span></span>
    
    <span data-ttu-id="89b4a-132">如果要等待以后，请取消选择所有服务并单击"继续"，或在上一个域连接步骤中选择"更多选项"并选择"立即跳过 **此"。**</span><span class="sxs-lookup"><span data-stu-id="89b4a-132">If you want to wait for later, either unselect all the services and click **Continue**, or in the previous domain connection step choose **More Options** and select **Skip this for now**.</span></span>
    
8. <span data-ttu-id="89b4a-133">选择 **完成** - 你已完成！</span><span class="sxs-lookup"><span data-stu-id="89b4a-133">Select **Finish** - you're done!</span></span>

## <a name="add-or-edit-custom-dns-records"></a><span data-ttu-id="89b4a-134">添加或编辑自定义 DNS 记录</span><span class="sxs-lookup"><span data-stu-id="89b4a-134">Add or edit custom DNS records</span></span>

<span data-ttu-id="89b4a-135">按照以下步骤为网站或第三方服务添加自定义记录。</span><span class="sxs-lookup"><span data-stu-id="89b4a-135">Follow the steps below to add a custom record for a website or 3rd party service.</span></span>

1. <span data-ttu-id="89b4a-136">在 登录 Microsoft 管理中心 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> 。</span><span class="sxs-lookup"><span data-stu-id="89b4a-136">Sign in to the Microsoft admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="89b4a-137">转到 **"设置**   >  **域"** 页面。</span><span class="sxs-lookup"><span data-stu-id="89b4a-137">Go to the **Settings**  > **Domains** page.</span></span>

3. <span data-ttu-id="89b4a-138">在" **域**"页面上选择域。</span><span class="sxs-lookup"><span data-stu-id="89b4a-138">On the **Domains** page, select a domain.</span></span> 
    
4. <span data-ttu-id="89b4a-139">在 **"DNS 设置"** 下，选择 **"自定义记录";** 然后选择"**新建自定义记录"。**</span><span class="sxs-lookup"><span data-stu-id="89b4a-139">Under **DNS settings**, select **Custom Records**; then select **New custom record**.</span></span>

5. <span data-ttu-id="89b4a-140">选择要添加的 DNS 记录类型，然后键入新记录的信息。</span><span class="sxs-lookup"><span data-stu-id="89b4a-140">Select the type of DNS record you want to add and type the information for the new record.</span></span>
    
6. <span data-ttu-id="89b4a-141">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="89b4a-141">Select **Save**.</span></span>

## <a name="registrars-with-domain-connect"></a><span data-ttu-id="89b4a-142">具有域注册机构的连接</span><span class="sxs-lookup"><span data-stu-id="89b4a-142">Registrars with Domain Connect</span></span>

<span data-ttu-id="89b4a-143">[通过连接](https://www.domainconnect.org/)域注册机构，你可以将域添加到Microsoft 365只需几分钟即可完成一个三步过程。</span><span class="sxs-lookup"><span data-stu-id="89b4a-143">[Domain Connect](https://www.domainconnect.org/) enabled registrars let you add your domain to Microsoft 365 in a three-step process that takes minutes.</span></span> 
  
<span data-ttu-id="89b4a-144">在向导中，我们将仅确认您拥有该域，然后自动设置您的域记录，因此电子邮件会发送到 Microsoft 365 和其他 Microsoft 365 服务（如 Teams）处理您的域。</span><span class="sxs-lookup"><span data-stu-id="89b4a-144">In the wizard, we'll just confirm that you own the domain, and then automatically set up your domain's records, so email comes to Microsoft 365 and other Microsoft 365 services, like Teams, work with your domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="89b4a-145">在开始此设置向导前，请确保你已禁用浏览器中的任何弹出窗口阻止程序。</span><span class="sxs-lookup"><span data-stu-id="89b4a-145">Make sure you disable any popup blockers in your browser before you start the setup wizard.</span></span>
  
### <a name="domain-connect-registrars-integrating-with-microsoft-365"></a><span data-ttu-id="89b4a-146">域连接注册机构与 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="89b4a-146">Domain Connect registrars integrating with Microsoft 365</span></span>

- [<span data-ttu-id="89b4a-147">1 &amp; 1 IONOS</span><span class="sxs-lookup"><span data-stu-id="89b4a-147">1&amp;1 IONOS</span></span>](https://www.1and1.com/)
- [<span data-ttu-id="89b4a-148">EuroDNS</span><span class="sxs-lookup"><span data-stu-id="89b4a-148">EuroDNS</span></span>](https://www.eurodns.com/)
- [<span data-ttu-id="89b4a-149">Cloudflare</span><span class="sxs-lookup"><span data-stu-id="89b4a-149">Cloudflare</span></span>](https://www.cloudflare.com/)
- [<span data-ttu-id="89b4a-150">GoDaddy</span><span class="sxs-lookup"><span data-stu-id="89b4a-150">GoDaddy</span></span>](https://www.godaddy.com/)
- [<span data-ttu-id="89b4a-151">WordPress.com</span><span class="sxs-lookup"><span data-stu-id="89b4a-151">WordPress.com</span></span>](https://wordpress.com/)
- [<span data-ttu-id="89b4a-152">Plesk</span><span class="sxs-lookup"><span data-stu-id="89b4a-152">Plesk</span></span>](https://www.plesk.com/)
- [<span data-ttu-id="89b4a-153">MediaTemple</span><span class="sxs-lookup"><span data-stu-id="89b4a-153">MediaTemple</span></span>](https://mediatemple.net/)
- <span data-ttu-id="89b4a-154">SecureServer 或 WildWestDomains (使用 SecureServer DNS 托管客户端的 GoDaddy) </span><span class="sxs-lookup"><span data-stu-id="89b4a-154">SecureServer or WildWestDomains (GoDaddy resellers using SecureServer DNS hosting)</span></span>
    - <span data-ttu-id="89b4a-155">示例：</span><span class="sxs-lookup"><span data-stu-id="89b4a-155">Examples:</span></span>
        - [<span data-ttu-id="89b4a-156">DomainsPricedRight</span><span class="sxs-lookup"><span data-stu-id="89b4a-156">DomainsPricedRight</span></span>](https://www.domainspricedright.com/products/domain-registration)
        - [<span data-ttu-id="89b4a-157">DomainRightNow</span><span class="sxs-lookup"><span data-stu-id="89b4a-157">DomainRightNow</span></span>](https://www.domainrightnow.com/)

### <a name="what-happens-to-my-email-and-website"></a><span data-ttu-id="89b4a-158">我的电子邮件和网站会发生什么情况？</span><span class="sxs-lookup"><span data-stu-id="89b4a-158">What happens to my email and website?</span></span>

<span data-ttu-id="89b4a-159">完成设置后，你的域的 MX 记录将更新为指向Microsoft 365并且你的域的所有电子邮件都将开始Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="89b4a-159">After you finish setup, the MX record for your domain is updated to point to Microsoft 365 and all email for your domain will start coming to Microsoft 365.</span></span> <span data-ttu-id="89b4a-160">确保你已添加用户，并Microsoft 365域中收到电子邮件的每个人设置邮箱！</span><span class="sxs-lookup"><span data-stu-id="89b4a-160">Make sure you've added users and set up mailboxes in Microsoft 365 for everyone who gets email on your domain!</span></span>
  
<span data-ttu-id="89b4a-161">如果你有一个用于你的企业的网站，它将在其所在的位置保持工作。</span><span class="sxs-lookup"><span data-stu-id="89b4a-161">If you have a website that you use with your business, it will keep working where it is.</span></span> <span data-ttu-id="89b4a-162">域连接设置步骤不会影响您的网站。</span><span class="sxs-lookup"><span data-stu-id="89b4a-162">The Domain Connect setup steps don't affect your website.</span></span>

## <a name="related-content"></a><span data-ttu-id="89b4a-163">相关内容</span><span class="sxs-lookup"><span data-stu-id="89b4a-163">Related content</span></span>

<span data-ttu-id="89b4a-164">[域常见问题](domains-faq.yml) (文章) </span><span class="sxs-lookup"><span data-stu-id="89b4a-164">[Domains FAQ](domains-faq.yml) (article)</span></span>

[<span data-ttu-id="89b4a-165">什么是域？</span><span class="sxs-lookup"><span data-stu-id="89b4a-165">What is a domain?</span></span>](../get-help-with-domains/what-is-a-domain.md) <span data-ttu-id="89b4a-166"> (文章) </span><span class="sxs-lookup"><span data-stu-id="89b4a-166">(article)</span></span>

<span data-ttu-id="89b4a-167">[购买域名Microsoft 365 (](../get-help-with-domains/buy-a-domain-name.md)文章) </span><span class="sxs-lookup"><span data-stu-id="89b4a-167">[Buy a domain name in Microsoft 365](../get-help-with-domains/buy-a-domain-name.md) (article)</span></span>

<span data-ttu-id="89b4a-168">[设置域设置](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md) (文章) </span><span class="sxs-lookup"><span data-stu-id="89b4a-168">[Set up your domain](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md) (article)</span></span>