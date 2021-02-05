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
description: 在 DNS 主机上添加 DNS 记录，将域添加到 Microsoft 365 管理中心中的 Microsoft 365。 安装向导将指导你完成此过程。
ms.openlocfilehash: 5a3c86fb2b2f93e9da844c15a55555c5d0d7b5c1
ms.sourcegitcommit: 0d709e9ab0d8d56c5fc11a921298f82e40e122c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/05/2021
ms.locfileid: "50114251"
---
# <a name="add-a-domain-to-microsoft-365"></a><span data-ttu-id="98a19-104">将域添加到 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="98a19-104">Add a domain to Microsoft 365</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="98a19-105">管理中心正在发生改变。</span><span class="sxs-lookup"><span data-stu-id="98a19-105">The admin center is changing.</span></span> <span data-ttu-id="98a19-106">如果你的体验与此处提供的详细信息不匹配，请参阅[有关新版 Microsoft 365 管理中心](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true)。</span><span class="sxs-lookup"><span data-stu-id="98a19-106">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).</span></span>

::: moniker-end

 <span data-ttu-id="98a19-107">如果找不到要查找的内容，请 **[查看域常见问题解答](domains-faq.yml)**。</span><span class="sxs-lookup"><span data-stu-id="98a19-107">**[Check the Domains FAQ](domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
 <span data-ttu-id="98a19-108">*若要添加、修改或删除域，\*\*你必须*\* 是企业 **或** 企业计划的 [全局管理员](https://products.office.com/business/office)。这些更改会影响整个租户，自定义管理员或常规用户将无法进行这些更改。\*</span><span class="sxs-lookup"><span data-stu-id="98a19-108">*To Add, modify or remove domains you **must** be a **Global Administrator** of a [business or enterprise plan](https://products.office.com/business/office). These changes affect the whole tenant, *Customized administrators* or *regular users* won't be able to make these changes.*</span></span>  

 <span data-ttu-id="98a19-109">按照以下步骤添加、设置或继续设置域。</span><span class="sxs-lookup"><span data-stu-id="98a19-109">Follow these steps to add, set up, or continue setting up a domain.</span></span> 

::: moniker range="o365-worldwide"
  
::: moniker-end

::: moniker range="o365-germany"

> [!VIDEO https://www.microsoft.com/videoplayer/embed/dda6df6d-37b0-41ff-905b-089448355a31?autoplay=false]
  
::: moniker-end

::: moniker range="o365-worldwide"

1. <span data-ttu-id="98a19-110">转到位于 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> 的管理中心。</span><span class="sxs-lookup"><span data-stu-id="98a19-110">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

::: moniker-end
::: moniker range="o365-germany"

1. <span data-ttu-id="98a19-111">转到位于 <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a> 的管理中心。</span><span class="sxs-lookup"><span data-stu-id="98a19-111">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a>.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="98a19-112">转到位于 <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a> 的管理中心。</span><span class="sxs-lookup"><span data-stu-id="98a19-112">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a>.</span></span>

::: moniker-end
    
2. <span data-ttu-id="98a19-113">转到"**设置**  >  **域"** 页。</span><span class="sxs-lookup"><span data-stu-id="98a19-113">Go to the **Settings** > **Domains** page.</span></span> 

3. <span data-ttu-id="98a19-114">选择 **"添加域"。**</span><span class="sxs-lookup"><span data-stu-id="98a19-114">Select **Add domain**.</span></span>
    
4. <span data-ttu-id="98a19-115">输入要添加的域的名称，然后选择"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="98a19-115">Enter the name of the domain you want to add, then select **Next**.</span></span>
    
5. <span data-ttu-id="98a19-116">选择您希望如何验证您是否拥有该域。</span><span class="sxs-lookup"><span data-stu-id="98a19-116">Choose how you want to verify that you own the domain.</span></span>
    
    1. <span data-ttu-id="98a19-117">如果你的域注册机构使用[域连接](#domain-connect-registrars-integrating-with-microsoft-365)[，Microsoft](../get-help-with-domains/domain-connect.md)会通过登录注册机构并确认与 Microsoft 365 的连接来自动设置记录。</span><span class="sxs-lookup"><span data-stu-id="98a19-117">If your domain registrar uses [Domain Connect](#domain-connect-registrars-integrating-with-microsoft-365), Microsoft [will set up your records automatically](../get-help-with-domains/domain-connect.md) by having you sign in to your registrar and confirm the connection to Microsoft 365.</span></span> <span data-ttu-id="98a19-118">你将返回到管理中心，然后 Microsoft 将自动验证你的域。</span><span class="sxs-lookup"><span data-stu-id="98a19-118">You'll be returned to the admin center and Microsoft will then automatically verify your domain.</span></span>
    2. <span data-ttu-id="98a19-119">可使用 TXT 记录验证域。</span><span class="sxs-lookup"><span data-stu-id="98a19-119">You can use a TXT record to verify your domain.</span></span> <span data-ttu-id="98a19-120">选择此选项，然后选择 **"** 下一步"，查看有关如何将此 DNS 记录添加到注册机构网站的说明。</span><span class="sxs-lookup"><span data-stu-id="98a19-120">Select this and select **Next** to see instructions for how to add this DNS record to your registrar's website.</span></span> <span data-ttu-id="98a19-121">添加记录后，最多可能需要 30 分钟才能进行验证。</span><span class="sxs-lookup"><span data-stu-id="98a19-121">This can take up to 30 minutes to verify after you've added the record.</span></span> 
    3. <span data-ttu-id="98a19-122">可以将文本文件添加到域的网站。</span><span class="sxs-lookup"><span data-stu-id="98a19-122">You can add a text file to your domain's website.</span></span> <span data-ttu-id="98a19-123">从安装向导中选择并下载 .txt 文件，然后将该文件上载到网站的顶级文件夹。</span><span class="sxs-lookup"><span data-stu-id="98a19-123">Select and download the .txt file from the setup wizard, then upload the file to your website's top level folder.</span></span> <span data-ttu-id="98a19-124">文件的路径应 `http://mydomain.com/ms39978200.txt` 类似于：</span><span class="sxs-lookup"><span data-stu-id="98a19-124">The path to the file should look similar to: `http://mydomain.com/ms39978200.txt`.</span></span> <span data-ttu-id="98a19-125">我们将通过在网站上查找文件来确认你拥有该域。</span><span class="sxs-lookup"><span data-stu-id="98a19-125">We'll confirm you own the domain by finding the file on your website.</span></span>
    
6. <span data-ttu-id="98a19-126">选择要对 Microsoft 使用域所需的 DNS 更改。</span><span class="sxs-lookup"><span data-stu-id="98a19-126">Choose how you want to make the DNS changes required for Microsoft to use your domain.</span></span>
    
    1. <span data-ttu-id="98a19-127">如果你 **的** 注册机构支持 [域](#domain-connect-registrars-integrating-with-microsoft-365)连接，请选择"为我添加 DNS 记录 ["，Microsoft](../get-help-with-domains/domain-connect.md) 会通过登录注册机构并确认与 Microsoft 365 的连接来自动设置记录。</span><span class="sxs-lookup"><span data-stu-id="98a19-127">Choose **Add the DNS records for me** if your registrar supports [Domain Connect](#domain-connect-registrars-integrating-with-microsoft-365), and Microsoft [will set up your records automatically](../get-help-with-domains/domain-connect.md) by having you sign in to your registrar and confirm the connection to Microsoft 365.</span></span>
    2. <span data-ttu-id="98a19-128">如果你 **只想将** 特定的 Microsoft 365 服务附加到你的域，或者如果你希望暂时跳过此步骤，并且稍后要这样做，请选择"我将自己添加 DNS 记录"。</span><span class="sxs-lookup"><span data-stu-id="98a19-128">Choose **I'll add the DNS records myself** if you want to attach only specific Microsoft 365 services to your domain or if you want to skip this for now and do this later.</span></span> <span data-ttu-id="98a19-129">**如果确切了解执行内容，请选择此选项。**</span><span class="sxs-lookup"><span data-stu-id="98a19-129">**Choose this option if you know exactly what you're doing.**</span></span>

7. <span data-ttu-id="98a19-130">如果选择自己添加 *DNS* 记录，请选择"下一步"，你将看到一个页面，包含要添加到注册机构网站以设置域的所有记录。</span><span class="sxs-lookup"><span data-stu-id="98a19-130">If you chose to *add DNS records yourself*  , select **Next** and you'll see a page with all the records that you need to add to your registrars website to set up your domain.</span></span> 

    <span data-ttu-id="98a19-131">如果门户无法识别你的注册机构，你可以[按照以下常规说明操作。](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)</span><span class="sxs-lookup"><span data-stu-id="98a19-131">If the portal doesn't recognize your registrar, you can [follow these general instructions.](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)</span></span>
    
    <span data-ttu-id="98a19-132">查看[主机特定说明](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions)列表，以找到你的主机并按照步骤添加所需的全部记录。</span><span class="sxs-lookup"><span data-stu-id="98a19-132">Check our list of [host-specific instructions](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions) to find your host and follow the steps to add all the records you need.</span></span> 
    
    <span data-ttu-id="98a19-133">如果不知道你的域的 DNS 托管提供商或域注册机构，请参阅[查找域注册机构或 DNS 托管提供商](../get-help-with-domains/find-your-domain-registrar.md)。</span><span class="sxs-lookup"><span data-stu-id="98a19-133">If you don't know the DNS hosting provider or domain registrar for your domain, see [Find your domain registrar or DNS hosting provider](../get-help-with-domains/find-your-domain-registrar.md).</span></span>
    
    <span data-ttu-id="98a19-134">如果要等待稍后，请取消选择所有服务并单击"继续"，或在上一个域连接步骤中选择"更多选项"，然后选择"立即跳过 **此"。**</span><span class="sxs-lookup"><span data-stu-id="98a19-134">If you want to wait for later, either unselect all the services and click **Continue**, or in the previous domain connection step choose **More Options** and select **Skip this for now**.</span></span>
    
8. <span data-ttu-id="98a19-135">选择 **"** 完成 " - 已完成！</span><span class="sxs-lookup"><span data-stu-id="98a19-135">Select **Finish** - you're done!</span></span>

## <a name="add-or-edit-custom-dns-records"></a><span data-ttu-id="98a19-136">添加或编辑自定义 DNS 记录</span><span class="sxs-lookup"><span data-stu-id="98a19-136">Add or edit custom DNS records</span></span>

<span data-ttu-id="98a19-137">按照以下步骤为网站或第三方服务添加自定义记录。</span><span class="sxs-lookup"><span data-stu-id="98a19-137">Follow the steps below to add a custom record for a website or 3rd party service.</span></span>

1. <span data-ttu-id="98a19-138">登录 Microsoft 管理中心 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> 。</span><span class="sxs-lookup"><span data-stu-id="98a19-138">Sign in to the Microsoft admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="98a19-139">转到"**设置**   >  **域"** 页。</span><span class="sxs-lookup"><span data-stu-id="98a19-139">Go to the **Settings**  > **Domains** page.</span></span>

3. <span data-ttu-id="98a19-140">在" **域**"页面上选择域。</span><span class="sxs-lookup"><span data-stu-id="98a19-140">On the **Domains** page, select a domain.</span></span> 
    
4. <span data-ttu-id="98a19-141">在 **DNS 设置下**，选择 **"自定义记录";** 然后选择 **"新建自定义记录"。**</span><span class="sxs-lookup"><span data-stu-id="98a19-141">Under **DNS settings**, select **Custom Records**; then select **New custom record**.</span></span>

5. <span data-ttu-id="98a19-142">选择要添加的 DNS 记录的类型，然后键入新记录的信息。</span><span class="sxs-lookup"><span data-stu-id="98a19-142">Select the type of DNS record you want to add and type the information for the new record.</span></span>
    
6. <span data-ttu-id="98a19-143">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="98a19-143">Select **Save**.</span></span>

## <a name="registrars-with-domain-connect"></a><span data-ttu-id="98a19-144">使用域连接的注册器</span><span class="sxs-lookup"><span data-stu-id="98a19-144">Registrars with Domain Connect</span></span>

<span data-ttu-id="98a19-145">[通过启用域](https://www.domainconnect.org/) 连接的注册机构，你可以将域添加到 Microsoft 365，此过程分三步完成，此过程需要几分钟时间。</span><span class="sxs-lookup"><span data-stu-id="98a19-145">[Domain Connect](https://www.domainconnect.org/) enabled registrars let you add your domain to Microsoft 365 in a three-step process that takes minutes.</span></span> 
  
<span data-ttu-id="98a19-146">在向导中，我们将仅确认你拥有该域，然后自动设置域记录，因此电子邮件发送到 Microsoft 365 和其他 Microsoft 365 服务（如 Teams）处理你的域。</span><span class="sxs-lookup"><span data-stu-id="98a19-146">In the wizard, we'll just confirm that you own the domain, and then automatically set up your domain's records, so email comes to Microsoft 365 and other Microsoft 365 services, like Teams, work with your domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="98a19-147">在开始此设置向导前，请确保你已禁用浏览器中的任何弹出窗口阻止程序。</span><span class="sxs-lookup"><span data-stu-id="98a19-147">Make sure you disable any popup blockers in your browser before you start the setup wizard.</span></span>
  
### <a name="domain-connect-registrars-integrating-with-microsoft-365"></a><span data-ttu-id="98a19-148">与 Microsoft 365 集成域连接注册机构</span><span class="sxs-lookup"><span data-stu-id="98a19-148">Domain Connect registrars integrating with Microsoft 365</span></span>

- [<span data-ttu-id="98a19-149">1 &amp; 1 IONOS</span><span class="sxs-lookup"><span data-stu-id="98a19-149">1&amp;1 IONOS</span></span>](https://www.1and1.com/)
- [<span data-ttu-id="98a19-150">EuroDNS</span><span class="sxs-lookup"><span data-stu-id="98a19-150">EuroDNS</span></span>](https://www.eurodns.com/)
- [<span data-ttu-id="98a19-151">Cloudflare</span><span class="sxs-lookup"><span data-stu-id="98a19-151">Cloudflare</span></span>](https://www.cloudflare.com/)
- [<span data-ttu-id="98a19-152">GoDaddy</span><span class="sxs-lookup"><span data-stu-id="98a19-152">GoDaddy</span></span>](https://www.godaddy.com/)
- [<span data-ttu-id="98a19-153">WordPress.com</span><span class="sxs-lookup"><span data-stu-id="98a19-153">WordPress.com</span></span>](https://wordpress.com/)
- [<span data-ttu-id="98a19-154">Plesk</span><span class="sxs-lookup"><span data-stu-id="98a19-154">Plesk</span></span>](https://www.plesk.com/)
- [<span data-ttu-id="98a19-155">MediaTemple</span><span class="sxs-lookup"><span data-stu-id="98a19-155">MediaTemple</span></span>](https://mediatemple.net/)
- <span data-ttu-id="98a19-156">SecureServer 或 WildWestDomains (使用 SecureServer DNS 托管服务访问 GoDaddy) </span><span class="sxs-lookup"><span data-stu-id="98a19-156">SecureServer or WildWestDomains (GoDaddy resellers using SecureServer DNS hosting)</span></span>
    - <span data-ttu-id="98a19-157">示例：</span><span class="sxs-lookup"><span data-stu-id="98a19-157">Examples:</span></span>
        - [<span data-ttu-id="98a19-158">DomainsPricedRight</span><span class="sxs-lookup"><span data-stu-id="98a19-158">DomainsPricedRight</span></span>](https://www.domainspricedright.com/products/domain-registration)
        - [<span data-ttu-id="98a19-159">DomainRightNow</span><span class="sxs-lookup"><span data-stu-id="98a19-159">DomainRightNow</span></span>](https://www.domainrightnow.com/)

### <a name="what-happens-to-my-email-and-website"></a><span data-ttu-id="98a19-160">我的电子邮件和网站会发生什么情况？</span><span class="sxs-lookup"><span data-stu-id="98a19-160">What happens to my email and website?</span></span>

<span data-ttu-id="98a19-161">完成设置后，你的域的 MX 记录将更新为指向 Microsoft 365，并且你的域的所有电子邮件都将开始发送到 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="98a19-161">After you finish setup, the MX record for your domain is updated to point to Microsoft 365 and all email for your domain will start coming to Microsoft 365.</span></span> <span data-ttu-id="98a19-162">确保在 Microsoft 365 中为在你的域中收到电子邮件的每个人添加了用户并设置了邮箱！</span><span class="sxs-lookup"><span data-stu-id="98a19-162">Make sure you've added users and set up mailboxes in Microsoft 365 for everyone who gets email on your domain!</span></span>
  
<span data-ttu-id="98a19-163">如果你有一个用于你的企业的网站，它将在其所在的位置保持工作。</span><span class="sxs-lookup"><span data-stu-id="98a19-163">If you have a website that you use with your business, it will keep working where it is.</span></span> <span data-ttu-id="98a19-164">域连接设置步骤不会影响您的网站。</span><span class="sxs-lookup"><span data-stu-id="98a19-164">The Domain Connect setup steps don't affect your website.</span></span>

## <a name="related-articles"></a><span data-ttu-id="98a19-165">相关文章</span><span class="sxs-lookup"><span data-stu-id="98a19-165">Related articles</span></span>

[<span data-ttu-id="98a19-166">关于域的常见问题</span><span class="sxs-lookup"><span data-stu-id="98a19-166">Domains FAQ</span></span>](domains-faq.yml)

[<span data-ttu-id="98a19-167">什么是域？</span><span class="sxs-lookup"><span data-stu-id="98a19-167">What is a domain?</span></span>](../get-help-with-domains/what-is-a-domain.md)

[<span data-ttu-id="98a19-168">在 Microsoft 365 中购买域名</span><span class="sxs-lookup"><span data-stu-id="98a19-168">Buy a domain name in Microsoft 365</span></span>](../get-help-with-domains/buy-a-domain-name.md)

[<span data-ttu-id="98a19-169">设置域（主机特定的操作说明）</span><span class="sxs-lookup"><span data-stu-id="98a19-169">Set up your domain (host-specific instructions)</span></span>](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md)
