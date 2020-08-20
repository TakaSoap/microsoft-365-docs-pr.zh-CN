---
title: 执行内部管理员操作
f1.keywords:
- CSH
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
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: b9707ec8-2247-4e25-9bad-f11ddbc686e4
description: 了解如何在 Microsoft 365 中验证你的电子邮件和域所有权以接过非托管租户
ms.openlocfilehash: 9c1d98616b10737553060bcbad62df9b3b4c0c9a
ms.sourcegitcommit: 167c05cc6a776f62f0a0c2de5f3ffeb68c4a27ac
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/19/2020
ms.locfileid: "46814464"
---
# <a name="perform-an-internal-admin-takeover"></a><span data-ttu-id="b6484-103">执行内部管理员操作</span><span class="sxs-lookup"><span data-stu-id="b6484-103">Perform an internal admin takeover</span></span>

 <span data-ttu-id="b6484-104">如果找不到要查找的内容，请**[查看域常见问题解答](../setup/domains-faq.md)**。</span><span class="sxs-lookup"><span data-stu-id="b6484-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 

<span data-ttu-id="b6484-105">如果你是管理员，并且想要使用自助服务用户注册创建的非托管租户，可以用内部管理员转到此方法。</span><span class="sxs-lookup"><span data-stu-id="b6484-105">If you are an admin and want to take over an unmanaged tenant created by a self-service user signup, you can do this with an internal admin takeover.</span></span>

> [!NOTE]
> <span data-ttu-id="b6484-106">自助注册使用 Azure AD 的用户会将用户添加到非托管或"影子"Azure AD 目录，并创建非托管租户。</span><span class="sxs-lookup"><span data-stu-id="b6484-106">A self-service sign up for any cloud service that uses Azure AD will add the user to an unmanaged or "shadow" Azure AD directory and create an unmanaged tenant.</span></span> <span data-ttu-id="b6484-107">非托管租户是没有全局管理员的目录。</span><span class="sxs-lookup"><span data-stu-id="b6484-107">An unmanaged tenant is a directory without a global administrator.</span></span> <span data-ttu-id="b6484-108">若要确定租户是否由托管或非托管，请参阅["确定租户类型"。](https://docs.microsoft.com/power-platform/admin/powerapps-gdpr-dsr-guide-systemlogs#determining-tenant-type)</span><span class="sxs-lookup"><span data-stu-id="b6484-108">To determine whether a tenant is managed or unmanaged, please see [Determining Tenant Type](https://docs.microsoft.com/power-platform/admin/powerapps-gdpr-dsr-guide-systemlogs#determining-tenant-type).</span></span> 
  
## <a name="step-1-verify-your-email-address"></a><span data-ttu-id="b6484-109">步骤 1：验证您的电子邮件地址</span><span class="sxs-lookup"><span data-stu-id="b6484-109">Step 1: Verify your email address</span></span>

> [!NOTE]
> <span data-ttu-id="b6484-110">如果你的租户启用了自助服务，则用户可以自行订阅免费服务，例如 Power BI。</span><span class="sxs-lookup"><span data-stu-id="b6484-110">If self-service is enabled in your tenant, users can subscribe to free services, such as Power BI, on their own.</span></span> <span data-ttu-id="b6484-111">这些步骤假定自助式用户订阅已创建你想要作为管理员认为的非托管租户。第一步是在非托管租户中创建用户上下文，使用 Power BI 来说明管理员接入路径。</span><span class="sxs-lookup"><span data-stu-id="b6484-111">These steps assume that a self-service user subscription has created the unmanaged tenant you want to take over as admin. In the first step you create a user context in the unmanaged tenant, using Power BI to illustrate the admin takeover path.</span></span>

1. <span data-ttu-id="b6484-112">要注册 Power BI，请转到[Power BI](https://powerbi.com)网站，然后选择"**开始**使用  >  Power BI 专业版 (CTrial (Ca power BI Pro"框) 。**Start free trial**</span><span class="sxs-lookup"><span data-stu-id="b6484-112">To sign up for Power BI, go to the [Power BI site](https://powerbi.com) and select **Start Free** > **Start free trial** (in Share with Power BI Pro box).</span></span> 

2. <span data-ttu-id="b6484-113">使用组织域名的用户帐户进行注册， (如 `powerbiadmin@contoso.com`) 。</span><span class="sxs-lookup"><span data-stu-id="b6484-113">Sign up with a user account that uses the domain name of your organization (like `powerbiadmin@contoso.com`).</span></span> <span data-ttu-id="b6484-114">如果你的帐户已在使用中，请使用当前密码登录。</span><span class="sxs-lookup"><span data-stu-id="b6484-114">If your account is already in use, sign in using your current password.</span></span>

3. <span data-ttu-id="b6484-115">检查您的电子邮件 **中是否有验证码，** 输入代码以验证您的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="b6484-115">Check your email for the **verification code** and enter the code to validate your email address.</span></span>
    
## <a name="step-2-create-a-new-account"></a><span data-ttu-id="b6484-116">步骤 2：创建新帐户</span><span class="sxs-lookup"><span data-stu-id="b6484-116">Step 2: Create a new account</span></span>

1. <span data-ttu-id="b6484-117">输入验证代码时，你将转到可创建新帐户的页面。</span><span class="sxs-lookup"><span data-stu-id="b6484-117">When you enter the verification code, you'll be brought to a page where you can create a new account.</span></span> 
    
2. <span data-ttu-id="b6484-118">使用您想要使用的帐户填写用户名和密码字段，然后选择"开始 **"。**</span><span class="sxs-lookup"><span data-stu-id="b6484-118">Fill in the user name and password fields with the account that you want to use, then select **Start**.</span></span> 
    
## <a name="step-3-verify-domain-ownership-and-become-the-admin"></a><span data-ttu-id="b6484-119">步骤 3：验证域所有权并成为管理员</span><span class="sxs-lookup"><span data-stu-id="b6484-119">Step 3: Verify domain ownership and become the admin</span></span>

1. <span data-ttu-id="b6484-120">此 **时将会打开"** 成为管理员"向导。</span><span class="sxs-lookup"><span data-stu-id="b6484-120">The **Become the admin** wizard will open.</span></span> <span data-ttu-id="b6484-121">如果没有启动该向导，请查找管理 **磁贴** 并选择它。</span><span class="sxs-lookup"><span data-stu-id="b6484-121">If the wizard doesn't start, look for the **Admin** tile and select it.</span></span> 

2. <span data-ttu-id="b6484-122">选择 **"是"，我想是管理员**。</span><span class="sxs-lookup"><span data-stu-id="b6484-122">Select **Yes, I want to be the admin**.</span></span>

3. <span data-ttu-id="b6484-123">向域注册机构添加 TXT 记录以验证你是否拥有要完全覆盖过的域。</span><span class="sxs-lookup"><span data-stu-id="b6484-123">Verify that you own the domain you want to take over by adding a TXT record to your domain registrar.</span></span> <span data-ttu-id="b6484-124">该向导将提供要添加的 TXT 记录、提供注册机构网站的链接及分步说明链接。</span><span class="sxs-lookup"><span data-stu-id="b6484-124">The wizard will give you the TXT record to add, as well as provide a link to your registrar's website, and a link to step-by-step instructions.</span></span>
    
4. <span data-ttu-id="b6484-125">将 TXT 记录添加到注册机构网站后，返回向导并选择 **"确定"，我添加了记录**。</span><span class="sxs-lookup"><span data-stu-id="b6484-125">Once you've added the TXT record to your registrar site, return to the wizard and select **Okay, I've added the record**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="b6484-126">处理卷影租户不会影响任何现有信息或服务。</span><span class="sxs-lookup"><span data-stu-id="b6484-126">Taking over the shadow tenant will not impact any existing information or services.</span></span> <span data-ttu-id="b6484-127">但是，如果域中的任何用户注册了需要许可证的服务，作为取对管理员角色的一部分，系统会要求你为他们购买许可证。</span><span class="sxs-lookup"><span data-stu-id="b6484-127">However, if any users in the domain have signed up for services that require a license, you'll be asked to buy licenses for them as part of taking over the admin role.</span></span> <span data-ttu-id="b6484-128">管理员设置过程完成后，你可以购买或删除许可证。</span><span class="sxs-lookup"><span data-stu-id="b6484-128">You can buy or remove licenses once the admin setup process is finished.</span></span>
  
## <a name="related-articles"></a><span data-ttu-id="b6484-129">相关文章</span><span class="sxs-lookup"><span data-stu-id="b6484-129">Related articles</span></span>

<span data-ttu-id="b6484-130">YouTube： [为 Power BI 和 Microsoft 365 执行 IT 管理员角色角色的 3 个步骤](https://www.youtube.com/watch?v=xt5EsrQBZZk)</span><span class="sxs-lookup"><span data-stu-id="b6484-130">YouTube: [3 steps to do an IT Admin Takeover for Power BI and Microsoft 365](https://www.youtube.com/watch?v=xt5EsrQBZZk)</span></span>

[<span data-ttu-id="b6484-131">Azure AD 中的管理员角色</span><span class="sxs-lookup"><span data-stu-id="b6484-131">Admin takeover in Azure AD</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/domains-admin-takeover)

[<span data-ttu-id="b6484-132">在组织中使用自助式注册</span><span class="sxs-lookup"><span data-stu-id="b6484-132">Using self-service sign up in your organization</span></span>](self-service-sign-up.md)
  
[<span data-ttu-id="b6484-133">了解 Power BI 服务管理员角色</span><span class="sxs-lookup"><span data-stu-id="b6484-133">Understanding the Power BI service administrator role</span></span>](https://docs.microsoft.com/power-bi/service-admin-role)

