---
title: 将域添加到 Office 365
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
- Adm_O365_Setup
- Adm_O365
- Adm_TOC
ms.custom:
- TopSMBIssues
- SaRA
- MSStore_Link
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 6383f56d-3d09-4dcb-9b41-b5f5a5efd611
description: 通过在 DNS 主机上添加 DNS 记录，将您的域添加到 Microsoft 365 管理中心中的 Office 365。 安装向导将引导您完成该过程。
ms.openlocfilehash: 4170fd74ae734a6fda9e535c17086997b1db6f6b
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/24/2020
ms.locfileid: "42240269"
---
# <a name="add-a-domain-to-office-365"></a><span data-ttu-id="e754b-104">将域添加到 Office 365</span><span class="sxs-lookup"><span data-stu-id="e754b-104">Add a domain to Office 365</span></span>

 <span data-ttu-id="e754b-105">如果找不到要查找的内容，请**[查看域常见问题解答](domains-faq.md)**。</span><span class="sxs-lookup"><span data-stu-id="e754b-105">**[Check the Domains FAQ](domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
 <span data-ttu-id="e754b-106">*若要添加、修改或删除域，您**必须**是[企业或企业计划](https://products.office.com/business/office)的**全局管理员**。这些更改会影响整个租户、*自定义管理员*或*常规用户*无法进行这些更改。*</span><span class="sxs-lookup"><span data-stu-id="e754b-106">*To Add, modify or remove domains you **must** be a **Global Administrator** of a [business or enterprise plan](https://products.office.com/business/office). These changes affect the whole tenant, *Customized administrators* or *regular users* won't be able to make these changes.*</span></span>  

 <span data-ttu-id="e754b-107">按照以下步骤添加、设置或继续设置域。</span><span class="sxs-lookup"><span data-stu-id="e754b-107">Follow these steps to add, set up, or continue setting up a domain.</span></span> 

::: moniker range="o365-worldwide"
  
::: moniker-end

::: moniker range="o365-germany"

> [!VIDEO https://www.microsoft.com/videoplayer/embed/dda6df6d-37b0-41ff-905b-089448355a31?autoplay=false]
  
::: moniker-end

::: moniker range="o365-worldwide"

1. <span data-ttu-id="e754b-108">转到位于 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> 的管理中心。</span><span class="sxs-lookup"><span data-stu-id="e754b-108">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

::: moniker-end
::: moniker range="o365-germany"

1. <span data-ttu-id="e754b-109">转到位于 <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a> 的管理中心。</span><span class="sxs-lookup"><span data-stu-id="e754b-109">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a>.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="e754b-110">转到位于 <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a> 的管理中心。</span><span class="sxs-lookup"><span data-stu-id="e754b-110">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a>.</span></span>

::: moniker-end
    
2. <span data-ttu-id="e754b-111">转到 "**设置** > **域**" 页面。</span><span class="sxs-lookup"><span data-stu-id="e754b-111">Go to the **Settings** > **Domains** page.</span></span> 

3. <span data-ttu-id="e754b-112">选择 "**添加域**"。</span><span class="sxs-lookup"><span data-stu-id="e754b-112">Select **Add domain**.</span></span>
    
4. <span data-ttu-id="e754b-113">输入要添加的域的名称，然后选择 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="e754b-113">Enter the name of the domain you want to add, then select **Next**.</span></span>
    
5. <span data-ttu-id="e754b-114">选择要验证您是否拥有域的方式。</span><span class="sxs-lookup"><span data-stu-id="e754b-114">Choose how you want to verify that you own the domain.</span></span>
    
    1. <span data-ttu-id="e754b-115">如果您的域是在 GoDaddy 或 1&amp;1 注册的，请选择 "**登录** > "。在 "**下一步**"，Office 365[将自动设置您的记录](../get-help-with-domains/domain-connect.md)。</span><span class="sxs-lookup"><span data-stu-id="e754b-115">If your domain is registered at GoDaddy or 1&amp;1, select **Sign in** > **Next** and Office 365 [will set up your records automatically](../get-help-with-domains/domain-connect.md).</span></span>
    
    2. <span data-ttu-id="e754b-116">可向域注册联系人发送包含验证码的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="e754b-116">You can have an email sent to the registered contact for the domain with a verification code.</span></span> <span data-ttu-id="e754b-117">如果无法识别记录的电子邮件或对其具有访问权限，则可以使用第三个选项。</span><span class="sxs-lookup"><span data-stu-id="e754b-117">If you don't recognize or have access to the email on record, you can use the third option.</span></span>
    
    3. <span data-ttu-id="e754b-118">可使用 TXT 记录验证域。</span><span class="sxs-lookup"><span data-stu-id="e754b-118">You can use a TXT record to verify your domain.</span></span> <span data-ttu-id="e754b-119">选择此操作并选择 "**下一步**"，查看有关如何将此 DNS 记录添加到你的注册机构网站的说明。</span><span class="sxs-lookup"><span data-stu-id="e754b-119">Select this and select **Next** to see instructions for how to add this DNS record to your registrar's website.</span></span> <span data-ttu-id="e754b-120">在添加记录后，可能需要长达30分钟的时间来进行验证。</span><span class="sxs-lookup"><span data-stu-id="e754b-120">This can take up to 30 minutes to verify after you've added the record.</span></span> 
    
6. <span data-ttu-id="e754b-121">选择您希望如何对 Office 使用您的域所做的 DNS 更改。</span><span class="sxs-lookup"><span data-stu-id="e754b-121">Choose how you want to make the DNS changes required for Office to use your domain.</span></span>
    
    1. <span data-ttu-id="e754b-122">如果您希望 Office 自动配置您的 DNS，请选择 **"为我添加 dns 记录"** 。</span><span class="sxs-lookup"><span data-stu-id="e754b-122">Choose **Add the DNS records for me** if you want Office to configure your DNS automatically.</span></span> 
    
  
    2. <span data-ttu-id="e754b-123">如果你想要仅将特定的 Office 365 服务附加到你的域，或者你现在想要跳过此操作，请选择 **"我要在自己添加 DNS 记录"** 。</span><span class="sxs-lookup"><span data-stu-id="e754b-123">Choose **I'll add the DNS records myself** if you want to attach only specific Office 365 services to your domain or if you want to skip this for now and do this later.</span></span> <span data-ttu-id="e754b-124">**如果确切了解执行内容，请选择此选项。**</span><span class="sxs-lookup"><span data-stu-id="e754b-124">**Choose this option if you know exactly what you're doing.**</span></span>
    
7. <span data-ttu-id="e754b-125">如果你选择*自己添加 DNS 记录*，请选择 "**下一步**"，你将看到一个页面，其中包含你需要将其添加到注册机构网站以设置你的域的所有记录。</span><span class="sxs-lookup"><span data-stu-id="e754b-125">If you chose to  *add DNS records yourself*  , select **Next** and you'll see a page with all the records that you need to add to your registrars website to set up your domain.</span></span> 
    
  
  
    <span data-ttu-id="e754b-126">如果门户无法识别你的注册机构，你可以[按照以下常规说明操作。](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)</span><span class="sxs-lookup"><span data-stu-id="e754b-126">If the portal doesn't recognize your registrar, you can [follow these general instructions.](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)</span></span>
    
    <span data-ttu-id="e754b-127">查看[主机特定说明](https://support.office.com/article/ae950c9e-e8d9-4108-b0cb-449156998580)列表，以找到你的主机并按照步骤添加所需的全部记录。</span><span class="sxs-lookup"><span data-stu-id="e754b-127">Check our list of [host-specific instructions](https://support.office.com/article/ae950c9e-e8d9-4108-b0cb-449156998580) to find your host and follow the steps to add all the records you need.</span></span> 
    
    <span data-ttu-id="e754b-128">如果不知道你的域的 DNS 托管提供商或域注册机构，请参阅[查找域注册机构或 DNS 托管提供商](../get-help-with-domains/find-your-domain-registrar.md)。</span><span class="sxs-lookup"><span data-stu-id="e754b-128">If you don't know the DNS hosting provider or domain registrar for your domain, see [Find your domain registrar or DNS hosting provider](../get-help-with-domains/find-your-domain-registrar.md).</span></span>
    
    <span data-ttu-id="e754b-129">如果要稍后等待，请滚动到底部，然后选择 "**跳过此步骤**"。</span><span class="sxs-lookup"><span data-stu-id="e754b-129">If you want to wait for later, scroll to the bottom and select **Skip this step**.</span></span>
    
8. <span data-ttu-id="e754b-130">选择 "**完成**"-完成！</span><span class="sxs-lookup"><span data-stu-id="e754b-130">Select **Finish** - you're done!</span></span> 

## <a name="related-articles"></a><span data-ttu-id="e754b-131">相关文章</span><span class="sxs-lookup"><span data-stu-id="e754b-131">Related articles</span></span>

[<span data-ttu-id="e754b-132">关于域的常见问题</span><span class="sxs-lookup"><span data-stu-id="e754b-132">Domains FAQ</span></span>](domains-faq.md)

[<span data-ttu-id="e754b-133">什么是域？</span><span class="sxs-lookup"><span data-stu-id="e754b-133">What is a domain?</span></span>](../get-help-with-domains/what-is-a-domain.md)

[<span data-ttu-id="e754b-134">在 Office 365 中购买域名</span><span class="sxs-lookup"><span data-stu-id="e754b-134">Buy a domain name in Office 365</span></span>](../get-help-with-domains/buy-a-domain-name.md)

[<span data-ttu-id="e754b-135">设置域（主机特定的操作说明）</span><span class="sxs-lookup"><span data-stu-id="e754b-135">Set up your domain (host-specific instructions)</span></span>](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md)

[<span data-ttu-id="e754b-136">获取 Office 365 域的帮助</span><span class="sxs-lookup"><span data-stu-id="e754b-136">Get help with Office 365 domains</span></span>](../get-help-with-domains/get-help-with-domains.md)
