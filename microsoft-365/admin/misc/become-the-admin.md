---
title: 执行内部管理员接管
f1.keywords:
- CSH
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
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: b9707ec8-2247-4e25-9bad-f11ddbc686e4
description: 了解如何验证电子邮件和域所有权以接管 Microsoft 365 中的非托管租户
ms.openlocfilehash: 28359908576260218459d13b8c1c1b662b9a2c8f
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "49658059"
---
# <a name="perform-an-internal-admin-takeover"></a><span data-ttu-id="1ab43-103">执行内部管理员接管</span><span class="sxs-lookup"><span data-stu-id="1ab43-103">Perform an internal admin takeover</span></span>

 <span data-ttu-id="1ab43-104">如果找不到要查找的内容，请 **[查看域常见问题解答](../setup/domains-faq.yml)**。</span><span class="sxs-lookup"><span data-stu-id="1ab43-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 

<span data-ttu-id="1ab43-105">如果你是管理员，并且想要接管由自助服务用户注册创建的非托管租户，可以通过内部管理员接管来完成此操作。</span><span class="sxs-lookup"><span data-stu-id="1ab43-105">If you are an admin and want to take over an unmanaged tenant created by a self-service user signup, you can do this with an internal admin takeover.</span></span>

> [!NOTE]
> <span data-ttu-id="1ab43-106">对于使用 Azure AD 的任何云服务，自助注册将用户添加到非托管或"影子"Azure AD 目录，并创建非托管租户。</span><span class="sxs-lookup"><span data-stu-id="1ab43-106">A self-service sign up for any cloud service that uses Azure AD will add the user to an unmanaged or "shadow" Azure AD directory and create an unmanaged tenant.</span></span> <span data-ttu-id="1ab43-107">非托管租户是一个没有全局管理员的目录。</span><span class="sxs-lookup"><span data-stu-id="1ab43-107">An unmanaged tenant is a directory without a global administrator.</span></span> <span data-ttu-id="1ab43-108">若要确定租户是托管租户还是非托管租户，请参阅"确定[租户类型"。](https://docs.microsoft.com/power-platform/admin/powerapps-gdpr-dsr-guide-systemlogs#determining-tenant-type)</span><span class="sxs-lookup"><span data-stu-id="1ab43-108">To determine whether a tenant is managed or unmanaged, please see [Determining Tenant Type](https://docs.microsoft.com/power-platform/admin/powerapps-gdpr-dsr-guide-systemlogs#determining-tenant-type).</span></span> 
  
## <a name="step-1-verify-your-email-address"></a><span data-ttu-id="1ab43-109">步骤 1：验证电子邮件地址</span><span class="sxs-lookup"><span data-stu-id="1ab43-109">Step 1: Verify your email address</span></span>

> [!NOTE]
> <span data-ttu-id="1ab43-110">如果在租户中启用了自助服务，用户可以自行订阅免费服务，如 Power BI。</span><span class="sxs-lookup"><span data-stu-id="1ab43-110">If self-service is enabled in your tenant, users can subscribe to free services, such as Power BI, on their own.</span></span> <span data-ttu-id="1ab43-111">这些步骤假定自助服务用户订阅已创建你想要以管理员角色接管的非托管租户。第一步是在非托管租户中创建用户上下文，使用 Power BI 说明管理员接管路径。</span><span class="sxs-lookup"><span data-stu-id="1ab43-111">These steps assume that a self-service user subscription has created the unmanaged tenant you want to take over as admin. In the first step you create a user context in the unmanaged tenant, using Power BI to illustrate the admin takeover path.</span></span>

1. <span data-ttu-id="1ab43-112">若要注册 Power BI，请转到 Power BI 站点并选择"与[Power BI](https://powerbi.com)专业版共享 (免费启动免费试用版  >  ) 。</span><span class="sxs-lookup"><span data-stu-id="1ab43-112">To sign up for Power BI, go to the [Power BI site](https://powerbi.com) and select **Start Free** > **Start free trial** (in Share with Power BI Pro box).</span></span> 

2. <span data-ttu-id="1ab43-113">使用使用组织域名的用户帐户进行注册， (如 `powerbiadmin@contoso.com`) 。</span><span class="sxs-lookup"><span data-stu-id="1ab43-113">Sign up with a user account that uses the domain name of your organization (like `powerbiadmin@contoso.com`).</span></span> <span data-ttu-id="1ab43-114">如果你的帐户已在使用中，请使用当前密码登录。</span><span class="sxs-lookup"><span data-stu-id="1ab43-114">If your account is already in use, sign in using your current password.</span></span>

3. <span data-ttu-id="1ab43-115">检查电子邮件的 **验证代码，** 并输入代码以验证您的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="1ab43-115">Check your email for the **verification code** and enter the code to validate your email address.</span></span>
    
## <a name="step-2-create-a-new-account"></a><span data-ttu-id="1ab43-116">步骤 2：创建新帐户</span><span class="sxs-lookup"><span data-stu-id="1ab43-116">Step 2: Create a new account</span></span>

1. <span data-ttu-id="1ab43-117">输入验证码后，你将进入一个页面，可在其中创建新帐户。</span><span class="sxs-lookup"><span data-stu-id="1ab43-117">When you enter the verification code, you'll be brought to a page where you can create a new account.</span></span> 
    
2. <span data-ttu-id="1ab43-118">使用想要使用的帐户填写用户名和密码字段，然后选择"开始 **"。**</span><span class="sxs-lookup"><span data-stu-id="1ab43-118">Fill in the user name and password fields with the account that you want to use, then select **Start**.</span></span> 
    
## <a name="step-3-verify-domain-ownership-and-become-the-admin"></a><span data-ttu-id="1ab43-119">步骤 3：验证域所有权并成为管理员</span><span class="sxs-lookup"><span data-stu-id="1ab43-119">Step 3: Verify domain ownership and become the admin</span></span>

1. <span data-ttu-id="1ab43-120">" **成为管理员"** 向导将打开。</span><span class="sxs-lookup"><span data-stu-id="1ab43-120">The **Become the admin** wizard will open.</span></span> <span data-ttu-id="1ab43-121">如果向导未启动，请查找"管理 **"** 磁贴并选择它。</span><span class="sxs-lookup"><span data-stu-id="1ab43-121">If the wizard doesn't start, look for the **Admin** tile and select it.</span></span> 

2. <span data-ttu-id="1ab43-122">选择 **"是"，我希望成为管理员**。</span><span class="sxs-lookup"><span data-stu-id="1ab43-122">Select **Yes, I want to be the admin**.</span></span>

3. <span data-ttu-id="1ab43-123">通过将 TXT 记录添加到域注册机构，验证您是否拥有要接管的域。</span><span class="sxs-lookup"><span data-stu-id="1ab43-123">Verify that you own the domain you want to take over by adding a TXT record to your domain registrar.</span></span> <span data-ttu-id="1ab43-124">该向导将提供要添加的 TXT 记录，并提供注册机构网站的链接和分步说明链接。</span><span class="sxs-lookup"><span data-stu-id="1ab43-124">The wizard will give you the TXT record to add, as well as provide a link to your registrar's website, and a link to step-by-step instructions.</span></span>
    
4. <span data-ttu-id="1ab43-125">将 TXT 记录添加到注册机构网站后，返回到向导并选择"好的，**我已添加该记录"。**</span><span class="sxs-lookup"><span data-stu-id="1ab43-125">Once you've added the TXT record to your registrar site, return to the wizard and select **Okay, I've added the record**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="1ab43-126">接管卷影租户不会影响任何现有信息或服务。</span><span class="sxs-lookup"><span data-stu-id="1ab43-126">Taking over the shadow tenant will not impact any existing information or services.</span></span> <span data-ttu-id="1ab43-127">但是，如果域中的任何用户已注册需要许可证的服务，则作为接管管理员角色的一部分，将要求您购买许可证。</span><span class="sxs-lookup"><span data-stu-id="1ab43-127">However, if any users in the domain have signed up for services that require a license, you'll be asked to buy licenses for them as part of taking over the admin role.</span></span> <span data-ttu-id="1ab43-128">在管理员设置过程完成后，你可以购买或删除许可证。</span><span class="sxs-lookup"><span data-stu-id="1ab43-128">You can buy or remove licenses once the admin setup process is finished.</span></span>
  
## <a name="related-articles"></a><span data-ttu-id="1ab43-129">相关文章</span><span class="sxs-lookup"><span data-stu-id="1ab43-129">Related articles</span></span>

<span data-ttu-id="1ab43-130">[YouTube：执行 Power BI 和 Microsoft 365 IT 管理员接管的 3 个步骤](https://www.youtube.com/watch?v=xt5EsrQBZZk)</span><span class="sxs-lookup"><span data-stu-id="1ab43-130">YouTube: [3 steps to do an IT Admin Takeover for Power BI and Microsoft 365](https://www.youtube.com/watch?v=xt5EsrQBZZk)</span></span>

[<span data-ttu-id="1ab43-131">Azure AD 中的管理员接管</span><span class="sxs-lookup"><span data-stu-id="1ab43-131">Admin takeover in Azure AD</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/domains-admin-takeover)

[<span data-ttu-id="1ab43-132">在组织中使用自助式注册</span><span class="sxs-lookup"><span data-stu-id="1ab43-132">Using self-service sign up in your organization</span></span>](self-service-sign-up.md)
  
[<span data-ttu-id="1ab43-133">了解 Power BI 服务管理员角色</span><span class="sxs-lookup"><span data-stu-id="1ab43-133">Understanding the Power BI service administrator role</span></span>](https://docs.microsoft.com/power-bi/service-admin-role)

