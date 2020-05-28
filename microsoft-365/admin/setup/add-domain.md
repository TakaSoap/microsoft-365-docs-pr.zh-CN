---
title: 将域添加到 Office 365
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
description: 通过在 DNS 主机上添加 DNS 记录，将您的域添加到 Microsoft 365 管理中心中的 Office 365。 安装向导将引导您完成该过程。
ms.openlocfilehash: b5ad21174c0a2ebb3466072ef43fb1ba284d3b59
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2020
ms.locfileid: "44398986"
---
# <a name="add-a-domain-to-microsoft-365"></a><span data-ttu-id="10ae2-104">将域添加到 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="10ae2-104">Add a domain to Microsoft 365</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="10ae2-105">管理中心正在发生改变。</span><span class="sxs-lookup"><span data-stu-id="10ae2-105">The admin center is changing.</span></span> <span data-ttu-id="10ae2-106">如果你的体验与此处提供的详细信息不匹配，请参阅[有关新版 Microsoft 365 管理中心](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet)。</span><span class="sxs-lookup"><span data-stu-id="10ae2-106">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

 <span data-ttu-id="10ae2-107">如果找不到要查找的内容，请**[查看域常见问题解答](domains-faq.md)**。</span><span class="sxs-lookup"><span data-stu-id="10ae2-107">**[Check the Domains FAQ](domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
 <span data-ttu-id="10ae2-108">*若要添加、修改或删除域，您**必须**是[企业或企业计划](https://products.office.com/business/office)的**全局管理员**。这些更改会影响整个租户、*自定义管理员*或*常规用户*无法进行这些更改。*</span><span class="sxs-lookup"><span data-stu-id="10ae2-108">*To Add, modify or remove domains you **must** be a **Global Administrator** of a [business or enterprise plan](https://products.office.com/business/office). These changes affect the whole tenant, *Customized administrators* or *regular users* won't be able to make these changes.*</span></span>  

 <span data-ttu-id="10ae2-109">按照以下步骤添加、设置或继续设置域。</span><span class="sxs-lookup"><span data-stu-id="10ae2-109">Follow these steps to add, set up, or continue setting up a domain.</span></span> 

::: moniker range="o365-worldwide"
  
::: moniker-end

::: moniker range="o365-germany"

> [!VIDEO https://www.microsoft.com/videoplayer/embed/dda6df6d-37b0-41ff-905b-089448355a31?autoplay=false]
  
::: moniker-end

::: moniker range="o365-worldwide"

1. <span data-ttu-id="10ae2-110">转到位于 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> 的管理中心。</span><span class="sxs-lookup"><span data-stu-id="10ae2-110">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

::: moniker-end
::: moniker range="o365-germany"

1. <span data-ttu-id="10ae2-111">转到位于 <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a> 的管理中心。</span><span class="sxs-lookup"><span data-stu-id="10ae2-111">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a>.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="10ae2-112">转到位于 <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a> 的管理中心。</span><span class="sxs-lookup"><span data-stu-id="10ae2-112">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a>.</span></span>

::: moniker-end
    
2. <span data-ttu-id="10ae2-113">转到 "**设置**  >  **域**" 页面。</span><span class="sxs-lookup"><span data-stu-id="10ae2-113">Go to the **Settings** > **Domains** page.</span></span> 

3. <span data-ttu-id="10ae2-114">选择 "**添加域**"。</span><span class="sxs-lookup"><span data-stu-id="10ae2-114">Select **Add domain**.</span></span>
    
4. <span data-ttu-id="10ae2-115">输入要添加的域的名称，然后选择 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="10ae2-115">Enter the name of the domain you want to add, then select **Next**.</span></span>
    
5. <span data-ttu-id="10ae2-116">选择要验证您是否拥有域的方式。</span><span class="sxs-lookup"><span data-stu-id="10ae2-116">Choose how you want to verify that you own the domain.</span></span>
    
    1. <span data-ttu-id="10ae2-117">如果你的域是在 GoDaddy 或 1 &amp; 1 注册的**Sign in**，请选择 "  >  **下一步**"，Microsoft[将自动设置你的记录](../get-help-with-domains/domain-connect.md)。</span><span class="sxs-lookup"><span data-stu-id="10ae2-117">If your domain is registered at GoDaddy or 1&amp;1, select **Sign in** > **Next** and Microsoft [will set up your records automatically](../get-help-with-domains/domain-connect.md).</span></span>
    
    2. <span data-ttu-id="10ae2-118">可向域注册联系人发送包含验证码的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="10ae2-118">You can have an email sent to the registered contact for the domain with a verification code.</span></span> <span data-ttu-id="10ae2-119">如果无法识别记录的电子邮件或对其具有访问权限，则可以使用第三个选项。</span><span class="sxs-lookup"><span data-stu-id="10ae2-119">If you don't recognize or have access to the email on record, you can use the third option.</span></span>
    
    3. <span data-ttu-id="10ae2-120">可使用 TXT 记录验证域。</span><span class="sxs-lookup"><span data-stu-id="10ae2-120">You can use a TXT record to verify your domain.</span></span> <span data-ttu-id="10ae2-121">选择此操作并选择 "**下一步**"，查看有关如何将此 DNS 记录添加到你的注册机构网站的说明。</span><span class="sxs-lookup"><span data-stu-id="10ae2-121">Select this and select **Next** to see instructions for how to add this DNS record to your registrar's website.</span></span> <span data-ttu-id="10ae2-122">在添加记录后，可能需要长达30分钟的时间来进行验证。</span><span class="sxs-lookup"><span data-stu-id="10ae2-122">This can take up to 30 minutes to verify after you've added the record.</span></span> 
    
6. <span data-ttu-id="10ae2-123">选择您希望如何对 Office 使用您的域所做的 DNS 更改。</span><span class="sxs-lookup"><span data-stu-id="10ae2-123">Choose how you want to make the DNS changes required for Office to use your domain.</span></span>
    
    1. <span data-ttu-id="10ae2-124">如果您希望 Office 自动配置您的 DNS，请选择 **"为我添加 dns 记录"** 。</span><span class="sxs-lookup"><span data-stu-id="10ae2-124">Choose **Add the DNS records for me** if you want Office to configure your DNS automatically.</span></span> 
    
  
    2. <span data-ttu-id="10ae2-125">如果你想要仅将特定的 Office 365 服务附加到你的域，或者你现在想要跳过此操作，请选择 **"我要在自己添加 DNS 记录"** 。</span><span class="sxs-lookup"><span data-stu-id="10ae2-125">Choose **I'll add the DNS records myself** if you want to attach only specific Office 365 services to your domain or if you want to skip this for now and do this later.</span></span> <span data-ttu-id="10ae2-126">**如果确切了解执行内容，请选择此选项。**</span><span class="sxs-lookup"><span data-stu-id="10ae2-126">**Choose this option if you know exactly what you're doing.**</span></span>
    
7. <span data-ttu-id="10ae2-127">如果你选择*自己添加 DNS 记录*，请选择 "**下一步**"，你将看到一个页面，其中包含你需要将其添加到注册机构网站以设置你的域的所有记录。</span><span class="sxs-lookup"><span data-stu-id="10ae2-127">If you chose to  *add DNS records yourself*  , select **Next** and you'll see a page with all the records that you need to add to your registrars website to set up your domain.</span></span> 
    
  
  
    <span data-ttu-id="10ae2-128">如果门户无法识别你的注册机构，你可以[按照以下常规说明操作。](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)</span><span class="sxs-lookup"><span data-stu-id="10ae2-128">If the portal doesn't recognize your registrar, you can [follow these general instructions.](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)</span></span>
    
    <span data-ttu-id="10ae2-129">查看[主机特定说明](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions)列表，以找到你的主机并按照步骤添加所需的全部记录。</span><span class="sxs-lookup"><span data-stu-id="10ae2-129">Check our list of [host-specific instructions](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions) to find your host and follow the steps to add all the records you need.</span></span> 
    
    <span data-ttu-id="10ae2-130">如果不知道你的域的 DNS 托管提供商或域注册机构，请参阅[查找域注册机构或 DNS 托管提供商](../get-help-with-domains/find-your-domain-registrar.md)。</span><span class="sxs-lookup"><span data-stu-id="10ae2-130">If you don't know the DNS hosting provider or domain registrar for your domain, see [Find your domain registrar or DNS hosting provider](../get-help-with-domains/find-your-domain-registrar.md).</span></span>
    
    <span data-ttu-id="10ae2-131">如果要稍后等待，请滚动到底部，然后选择 "**跳过此步骤**"。</span><span class="sxs-lookup"><span data-stu-id="10ae2-131">If you want to wait for later, scroll to the bottom and select **Skip this step**.</span></span>
    
8. <span data-ttu-id="10ae2-132">选择 "**完成**"-完成！</span><span class="sxs-lookup"><span data-stu-id="10ae2-132">Select **Finish** - you're done!</span></span> 

## <a name="add-or-edit-custom-dns-records"></a><span data-ttu-id="10ae2-133">添加或编辑自定义 DNS 记录</span><span class="sxs-lookup"><span data-stu-id="10ae2-133">Add or edit custom DNS records</span></span>

<span data-ttu-id="10ae2-134">按照以下步骤为网站或第三方服务添加自定义记录。</span><span class="sxs-lookup"><span data-stu-id="10ae2-134">Follow the steps below to add a custom record for a website or 3rd party service.</span></span>

1. <span data-ttu-id="10ae2-135">在上登录到 Microsoft 管理中心 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> 。</span><span class="sxs-lookup"><span data-stu-id="10ae2-135">Sign in to the Microsoft admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="10ae2-136">转到 "**设置**   >  **域**" 页面。</span><span class="sxs-lookup"><span data-stu-id="10ae2-136">Go to the **Settings**  > **Domains** page.</span></span>

3. <span data-ttu-id="10ae2-137">在" **域**"页面上选择域。</span><span class="sxs-lookup"><span data-stu-id="10ae2-137">On the **Domains** page, select a domain.</span></span> 
    
4. <span data-ttu-id="10ae2-138">在 " **DNS 设置**" 下，选择 "**自定义记录**";然后选择 "**新建自定义记录**"。</span><span class="sxs-lookup"><span data-stu-id="10ae2-138">Under **DNS settings**, select **Custom Records**; then select **New custom record**.</span></span>

5. <span data-ttu-id="10ae2-139">选择要添加的 DNS 记录的类型，然后键入新记录的信息。</span><span class="sxs-lookup"><span data-stu-id="10ae2-139">Select the type of DNS record you want to add and type the information for the new record.</span></span>
    
6. <span data-ttu-id="10ae2-140">选择“保存”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="10ae2-140">Select **Save**.</span></span>

## <a name="registrars-with-domain-connect"></a><span data-ttu-id="10ae2-141">具有域连接的注册机构</span><span class="sxs-lookup"><span data-stu-id="10ae2-141">Registrars with Domain Connect</span></span>

<span data-ttu-id="10ae2-142">启用[域连接](https://www.domainconnect.org/)的注册机构允许您将您的域添加到 Microsoft 365，这是一个需要几分钟时间的三步骤过程。</span><span class="sxs-lookup"><span data-stu-id="10ae2-142">[Domain Connect](https://www.domainconnect.org/) enabled registrars let you add your domain to Microsoft 365 in a three-step process that takes minutes.</span></span> 
  
<span data-ttu-id="10ae2-143">在向导中，我们将只是确认你拥有域，然后自动设置你的域的记录，因此电子邮件将发送到 Microsoft 365 和其他 Microsoft 365 服务（如团队）使用你的域。</span><span class="sxs-lookup"><span data-stu-id="10ae2-143">In the wizard, we'll just confirm that you own the domain, and then automatically set up your domain's records, so email comes to Microsoft 365 and other Microsoft 365 services, like Teams, work with your domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="10ae2-144">在开始此设置向导前，请确保你已禁用浏览器中的任何弹出窗口阻止程序。</span><span class="sxs-lookup"><span data-stu-id="10ae2-144">Make sure you disable any popup blockers in your browser before you start the setup wizard.</span></span>
  
### <a name="domain-connect-registrars-integrating-with-microsoft-365"></a><span data-ttu-id="10ae2-145">与 Microsoft 365 集成的域连接注册机构</span><span class="sxs-lookup"><span data-stu-id="10ae2-145">Domain Connect registrars integrating with Microsoft 365</span></span>

- [<span data-ttu-id="10ae2-146">1 &amp; 1 IONOS</span><span class="sxs-lookup"><span data-stu-id="10ae2-146">1&amp;1 IONOS</span></span>](https://www.1and1.com/)
- [<span data-ttu-id="10ae2-147">123Reg</span><span class="sxs-lookup"><span data-stu-id="10ae2-147">123Reg</span></span>](https://www.123-reg.co.uk/)
- [<span data-ttu-id="10ae2-148">GoDaddy</span><span class="sxs-lookup"><span data-stu-id="10ae2-148">GoDaddy</span></span>](https://www.godaddy.com/)
- [<span data-ttu-id="10ae2-149">WordPress</span><span class="sxs-lookup"><span data-stu-id="10ae2-149">WordPress</span></span>](https://wordpress.com/)
- [<span data-ttu-id="10ae2-150">Plesk</span><span class="sxs-lookup"><span data-stu-id="10ae2-150">Plesk</span></span>](https://www.plesk.com/)
- [<span data-ttu-id="10ae2-151">MediaTemple</span><span class="sxs-lookup"><span data-stu-id="10ae2-151">MediaTemple</span></span>](https://mediatemple.net/)
- <span data-ttu-id="10ae2-152">SecureServer 或 WildWestDomains （使用 SecureServer DNS 托管的 GoDaddy 经销商）</span><span class="sxs-lookup"><span data-stu-id="10ae2-152">SecureServer or WildWestDomains (GoDaddy resellers using SecureServer DNS hosting)</span></span>
    - [<span data-ttu-id="10ae2-153">MadDog 域</span><span class="sxs-lookup"><span data-stu-id="10ae2-153">MadDog Domains</span></span>](https://www.maddogdomains.com/)
    - [<span data-ttu-id="10ae2-154">CheapNames</span><span class="sxs-lookup"><span data-stu-id="10ae2-154">CheapNames</span></span>](https://www.cheapnames.com)

### <a name="what-happens-to-my-email-and-website"></a><span data-ttu-id="10ae2-155">我的电子邮件和网站会发生什么情况？</span><span class="sxs-lookup"><span data-stu-id="10ae2-155">What happens to my email and website?</span></span>

<span data-ttu-id="10ae2-156">完成设置后，你的域的 MX 记录将更新为指向 Microsoft 365，并且你的域的所有电子邮件都将开始进入 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="10ae2-156">After you finish setup, the MX record for your domain is updated to point to Microsoft 365 and all email for your domain will start coming to Microsoft 365.</span></span> <span data-ttu-id="10ae2-157">请确保你已在 Office 365 中添加用户并为每个在你的域中收到电子邮件的人设置邮箱！</span><span class="sxs-lookup"><span data-stu-id="10ae2-157">Make sure you've added users and set up mailboxes in Office 365 for everyone who gets email on your domain!</span></span>
  
<span data-ttu-id="10ae2-158">如果你有一个用于你的企业的网站，它将在其所在的位置保持工作。</span><span class="sxs-lookup"><span data-stu-id="10ae2-158">If you have a website that you use with your business, it will keep working where it is.</span></span> <span data-ttu-id="10ae2-159">域连接设置步骤不会影响您的网站。</span><span class="sxs-lookup"><span data-stu-id="10ae2-159">The Domain Connect setup steps don't affect your website.</span></span>

## <a name="related-articles"></a><span data-ttu-id="10ae2-160">相关文章</span><span class="sxs-lookup"><span data-stu-id="10ae2-160">Related articles</span></span>

[<span data-ttu-id="10ae2-161">关于域的常见问题</span><span class="sxs-lookup"><span data-stu-id="10ae2-161">Domains FAQ</span></span>](domains-faq.md)

[<span data-ttu-id="10ae2-162">什么是域？</span><span class="sxs-lookup"><span data-stu-id="10ae2-162">What is a domain?</span></span>](../get-help-with-domains/what-is-a-domain.md)

[<span data-ttu-id="10ae2-163">在 Office 365 中购买域名</span><span class="sxs-lookup"><span data-stu-id="10ae2-163">Buy a domain name in Office 365</span></span>](../get-help-with-domains/buy-a-domain-name.md)

[<span data-ttu-id="10ae2-164">设置域（主机特定的操作说明）</span><span class="sxs-lookup"><span data-stu-id="10ae2-164">Set up your domain (host-specific instructions)</span></span>](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md)

[<span data-ttu-id="10ae2-165">获取有关域的帮助</span><span class="sxs-lookup"><span data-stu-id="10ae2-165">Get help with domains</span></span>](../get-help-with-domains/get-help-with-domains.md)
