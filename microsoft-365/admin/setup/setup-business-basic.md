---
title: 设置 Microsoft 365 商业基础版
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
- TRN_SMB
ms.custom:
- TRN_M365B
- OKR_SMB_Videos
- AdminSurgePortfolio
search.appverid:
- MET150
- MOE150
- BEA160
description: 了解如何设置 Microsoft 365 商业基础版订阅。
ms.openlocfilehash: 51a83d4cc230fa4bdb78bba71c9c7193a36fd391
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2021
ms.locfileid: "52535718"
---
# <a name="set-up-microsoft-365-business-basic"></a><span data-ttu-id="e93ef-103">设置 Microsoft 365 商业基础版</span><span class="sxs-lookup"><span data-stu-id="e93ef-103">Set up Microsoft 365 Business Basic</span></span>

 <span data-ttu-id="e93ef-104">观看有关设置 Microsoft 365 商业基础版的简短视频。</span><span class="sxs-lookup"><span data-stu-id="e93ef-104">Watch a short video about setting up Microsoft 365 Business Basic.</span></span><br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4vk3W]

<span data-ttu-id="e93ef-105">如果你觉得这段视频有用，请查看[适用于小型企业和 Microsoft 365 新手的完整培训系列](../../business-video/index.yml)。</span><span class="sxs-lookup"><span data-stu-id="e93ef-105">If you found this video helpful, check out the [complete training series for small businesses and those new to Microsoft 365](../../business-video/index.yml).</span></span>

## <a name="add-your-domain-to-personalize-sign-in"></a><span data-ttu-id="e93ef-106">添加你的域以个性化设置登录名</span><span class="sxs-lookup"><span data-stu-id="e93ef-106">Add your domain to personalize sign-in</span></span>

<span data-ttu-id="e93ef-107">购买 Microsoft 365 商业基础版时，你可以选择使用自己拥有的域，也可以在注册期间购买一个域。</span><span class="sxs-lookup"><span data-stu-id="e93ef-107">When you purchase Microsoft 365 Business Basic, you have the option of using a domain you own, or buying one during the sign-up.</span></span>

- <span data-ttu-id="e93ef-108">如果你在注册时购买了新域，则域已全部设置好，你可以继续[添加用户并分配许可证](#add-users-and-assign-licenses)。</span><span class="sxs-lookup"><span data-stu-id="e93ef-108">If you purchased a new domain when you signed up, your domain is all set up and you can move to [Add users and assign licenses](#add-users-and-assign-licenses).</span></span>

 ::: moniker range="o365-worldwide"

1. <span data-ttu-id="e93ef-109">转到位于 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> 的管理中心。</span><span class="sxs-lookup"><span data-stu-id="e93ef-109">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="e93ef-110">转到位于 <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de</a> 的管理中心。</span><span class="sxs-lookup"><span data-stu-id="e93ef-110">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de</a>.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="e93ef-111">转到位于 <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a> 的管理中心。</span><span class="sxs-lookup"><span data-stu-id="e93ef-111">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a>.</span></span>

::: moniker-end 

2. <span data-ttu-id="e93ef-112">选择“**转到设置**”以启动向导。</span><span class="sxs-lookup"><span data-stu-id="e93ef-112">Choose **Go to setup** to start the wizard.</span></span>
    
3. <span data-ttu-id="e93ef-113">在“**添加域**”步骤中，输入要使用的域名（如 contoso.com）。</span><span class="sxs-lookup"><span data-stu-id="e93ef-113">In the **Add domain** step, enter the domain name you want to use (like contoso.com).</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="e93ef-114">如果你在注册期间购买了域，则此处不会看到“**添加域**”步骤。</span><span class="sxs-lookup"><span data-stu-id="e93ef-114">If you purchased a domain during the sign-up, you will not see **Add a domain** step here.</span></span> <span data-ttu-id="e93ef-115">转到“[添加用户](#add-users-and-assign-licenses)”。</span><span class="sxs-lookup"><span data-stu-id="e93ef-115">Go to [Add users](#add-users-and-assign-licenses) instead.</span></span>

    
4. <span data-ttu-id="e93ef-116">按照向导[在任何 DNS 托管提供商处为 Office 365 创建 DNS 记录](/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider)中的步骤验证你是否拥有该域。</span><span class="sxs-lookup"><span data-stu-id="e93ef-116">Follow the steps in the wizard to [Create DNS records at any DNS hosting provider for Office 365](/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) that verifies you own the domain.</span></span> <span data-ttu-id="e93ef-117">如果你知道域主机，另请参阅[主机特定说明](/office365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions)。</span><span class="sxs-lookup"><span data-stu-id="e93ef-117">If you know your domain host, see also the [host specific instructions](/office365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions).</span></span>

    <span data-ttu-id="e93ef-118">如果你的托管服务提供商是 GoDaddy 或启用了 [domain connect](/office365/admin/get-help-with-domains/domain-connect) 的其他主机，则此过程很简单，系统会自动要求你登录并让 Microsoft 代表你进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="e93ef-118">If your hosting provider is GoDaddy or another host enabled with [domain connect](/office365/admin/get-help-with-domains/domain-connect), the process is easy and you'll be automatically asked to sign in and let Microsoft authenticate on your behalf.</span></span>

    ![在 GoDaddy“确认访问”页面上，选择“授权”。](../../media/godaddyauth.png)

## <a name="add-users-and-assign-licenses"></a><span data-ttu-id="e93ef-120">添加用户并分配许可证</span><span class="sxs-lookup"><span data-stu-id="e93ef-120">Add users and assign licenses</span></span>

<span data-ttu-id="e93ef-121">你可以在向导中添加用户，但你也可以[以后在管理中心添加用户](../add-users/add-users.md)。</span><span class="sxs-lookup"><span data-stu-id="e93ef-121">You can add users in the wizard, but you can also [add users later](../add-users/add-users.md) in the admin center.</span></span> <span data-ttu-id="e93ef-122">此外，如果你具有本地域控制器，则可以使用 [Azure AD Connect](/azure/active-directory/hybrid/how-to-connect-install-express) 添加用户。</span><span class="sxs-lookup"><span data-stu-id="e93ef-122">Additionally, if you have a local domain controller, you can add users with [Azure AD Connect](/azure/active-directory/hybrid/how-to-connect-install-express).</span></span>

## <a name="add-users-in-the-wizard"></a><span data-ttu-id="e93ef-123">在向导中添加用户</span><span class="sxs-lookup"><span data-stu-id="e93ef-123">Add users in the wizard</span></span>

<span data-ttu-id="e93ef-124">你在向导中添加的所有用户都将自动分配一个 Microsoft 365 商业基础版许可证。</span><span class="sxs-lookup"><span data-stu-id="e93ef-124">Any users you add in the wizard get automatically assigned a Microsoft 365 Business Basic license.</span></span>

1. <span data-ttu-id="e93ef-p104">如果你的 Microsoft 365 商业基础版订阅中存在现有用户（例如，如果使用了 Azure AD Connect），将显示现在为其分配许可证的选项。继续操作，并为这些用户添加许可证。</span><span class="sxs-lookup"><span data-stu-id="e93ef-p104">If your Microsoft 365 Business Basic subscription has existing users (for example, if you used Azure AD Connect), you get an option to assign licenses to them now. Go ahead and add licenses to them as well.</span></span>

2. <span data-ttu-id="e93ef-127">在你添加用户后，还将显示与添加的新用户共享凭据的选项。</span><span class="sxs-lookup"><span data-stu-id="e93ef-127">After you've added the users, you'll also get an option to share credentials with the new users you added.</span></span> <span data-ttu-id="e93ef-128">可以选择打印、通过电子邮件发送或下载凭据。</span><span class="sxs-lookup"><span data-stu-id="e93ef-128">You can choose to print them out, email them, or download them.</span></span>

## <a name="connect-your-domain"></a><span data-ttu-id="e93ef-129">连接你的域</span><span class="sxs-lookup"><span data-stu-id="e93ef-129">Connect your domain</span></span>

> [!NOTE]
> <span data-ttu-id="e93ef-130">如果你选择使用 .onmicrosoft 域或使用 Azure AD Connect 设置用户，将不会看到此步骤。</span><span class="sxs-lookup"><span data-stu-id="e93ef-130">If you chose to use the .onmicrosoft domain, or used Azure AD Connect to set up users, you will not see this step.</span></span>
  
<span data-ttu-id="e93ef-131">必须更新 DNS 主机或域注册机构的一些记录才能设置服务。</span><span class="sxs-lookup"><span data-stu-id="e93ef-131">To set up services, you have to update some records at your DNS host or domain registrar.</span></span>
  
1. <span data-ttu-id="e93ef-132">安装向导通常将检测你的注册机构，并提供更新注册机构网站上 NS 记录分步说明的链接。</span><span class="sxs-lookup"><span data-stu-id="e93ef-132">The setup wizard typically detects your registrar and gives you a link to step-by-step instructions for updating your NS records at the registrar website.</span></span> <span data-ttu-id="e93ef-133">如果没有，请[将名称服务器更改为使用任意域名注册机构设置 Office 365](../get-help-with-domains/change-nameservers-at-any-domain-registrar.md)。</span><span class="sxs-lookup"><span data-stu-id="e93ef-133">If it doesn't, [Change nameservers to set up Office 365 with any domain registrar](../get-help-with-domains/change-nameservers-at-any-domain-registrar.md).</span></span> 

    - <span data-ttu-id="e93ef-134">如果你有现有的 DNS 记录（例如现有网站），但你的 DNS 主机已启用 [domain connect](/office365/admin/get-help-with-domains/domain-connect)，请选择“**为我添加记录**”。</span><span class="sxs-lookup"><span data-stu-id="e93ef-134">If you have existing DNS records, for example an existing web site, but your DNS host is enabled for [domain connect](/office365/admin/get-help-with-domains/domain-connect), choose **Add records for me**.</span></span> <span data-ttu-id="e93ef-135">在“**选择联机服务**”页面上，接受所有默认设置，选择“**下一步**”，然后在DNS 主机页面上选择“**授权**”。</span><span class="sxs-lookup"><span data-stu-id="e93ef-135">On the **Choose your online services** page, accept all the defaults, and choose **Next**, and choose **Authorize** on your DNS host's page.</span></span>
    - <span data-ttu-id="e93ef-136">如果你具有用于其他 DNS 主机的现有 DNS 记录（未启用 domain connect），则需要管理自己的 DNS 记录以确保现有服务保持连接状态。</span><span class="sxs-lookup"><span data-stu-id="e93ef-136">If you have existing DNS records with other DNS hosts (not enabled for domain connect), you'll want to manage your own DNS records to make sure the existing services stay connected.</span></span> <span data-ttu-id="e93ef-137">有关详细信息，请参阅[域基础知识](/office365/admin/get-help-with-domains/dns-basics)。</span><span class="sxs-lookup"><span data-stu-id="e93ef-137">See [domain basics](/office365/admin/get-help-with-domains/dns-basics) for more info.</span></span>

2. <span data-ttu-id="e93ef-138">请按照向导中的步骤进行操作，然后将为你设置电子邮件和其他服务。</span><span class="sxs-lookup"><span data-stu-id="e93ef-138">Follow the steps in the wizard and email and other services will be set up for you.</span></span>

    <span data-ttu-id="e93ef-139">注册过程完成后，你将转到管理中心，可在其中添加用户并分配许可证。</span><span class="sxs-lookup"><span data-stu-id="e93ef-139">When the signup process is complete, you'll be directed to the admin center, where you can add users, and assign licenses.</span></span> <span data-ttu-id="e93ef-140">完成初始设置后，可使用管理中心中的“**设置**”页面，继续设置和配置订阅附带的服务。</span><span class="sxs-lookup"><span data-stu-id="e93ef-140">After you complete the initial setup, you can use the **Setup** page in the admin center to continue setting up and configuring the services that come with your subscriptions.</span></span>

    <span data-ttu-id="e93ef-141">有关设置向导和管理中心“**设置**”页面的详细信息，请参阅 [设置向导和设置页面之间的区别](o365-setup-wizard-and-setup-page.md)。</span><span class="sxs-lookup"><span data-stu-id="e93ef-141">For more information about the setup wizard and the admin center **Setup** page, see [Difference between the setup wizard and the Setup page](o365-setup-wizard-and-setup-page.md).</span></span>