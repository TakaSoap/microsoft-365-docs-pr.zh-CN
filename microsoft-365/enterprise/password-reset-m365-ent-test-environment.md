---
title: Microsoft 365 测试环境的密码重置
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/19/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom:
- TLGS
- Ent_TLGs
ms.assetid: ''
description: 摘要：配置和测试适用于 Microsoft 365 测试环境的密码重置。
ms.openlocfilehash: f5fc8d68493464d6b4a6ffdcda64ed9a0d8c7cdd
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32289456"
---
# <a name="password-reset-for-your-microsoft-365-test-environment"></a><span data-ttu-id="f9eea-103">Microsoft 365 测试环境的密码重置</span><span class="sxs-lookup"><span data-stu-id="f9eea-103">Password reset for your Microsoft 365 test environment</span></span>

<span data-ttu-id="f9eea-104">使用 Azure AD 自助服务密码重置 (SSPR)，用户可以重置或解锁其密码或帐户。</span><span class="sxs-lookup"><span data-stu-id="f9eea-104">Azure AD self-service password reset (SSPR) allows users to reset or unlock their passwords or accounts.</span></span> 

<span data-ttu-id="f9eea-105">本文介绍如何分两个阶段在 Microsoft 365 测试环境中配置和测试密码重置：</span><span class="sxs-lookup"><span data-stu-id="f9eea-105">This article describes how you can configure and test password resets in your Microsoft 365 test environment in two phases:</span></span>

1.  <span data-ttu-id="f9eea-106">创建 Microsoft 365 企业版测试环境。</span><span class="sxs-lookup"><span data-stu-id="f9eea-106">Create the Microsoft 365 simulated enterprise test environment.</span></span>
2.  <span data-ttu-id="f9eea-107">为用户 2 帐户配置和测试密码重置。</span><span class="sxs-lookup"><span data-stu-id="f9eea-107">Configure and test password reset for the User 2 account.</span></span>
    
![Microsoft 云测试实验室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="f9eea-109">单击[此处](https://aka.ms/m365etlgstack)可查看 Microsoft 365 企业版测试实验室指南集合中所有文章的直观图。</span><span class="sxs-lookup"><span data-stu-id="f9eea-109">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>

## <a name="phase-1-configure-password-hash-synchronization-and-password-writebback-for-your-microsoft-365-test-environment"></a><span data-ttu-id="f9eea-110">阶段 1：为 Microsoft 365 测试环境配置密码哈希同步和密码写回</span><span class="sxs-lookup"><span data-stu-id="f9eea-110">Phase 1: Configure password hash synchronization and password reset for your Microsoft 365 test environment</span></span>

<span data-ttu-id="f9eea-p101">首先，按照[密码哈希同步](password-hash-sync-m365-ent-test-environment.md)中的说明操作。下面是生成的配置。</span><span class="sxs-lookup"><span data-stu-id="f9eea-p101">First, follow the instructions in [password hash synchronization](password-hash-sync-m365-ent-test-environment.md). Here is your resulting configuration.</span></span>
  
![使用密码哈希同步测试环境的模拟企业配置](media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
<span data-ttu-id="f9eea-114">此配置包括：</span><span class="sxs-lookup"><span data-stu-id="f9eea-114">This configuration consists of:</span></span> 
  
- <span data-ttu-id="f9eea-115">Office 365 E5 和 EMS E5 试用订阅或付费订阅。</span><span class="sxs-lookup"><span data-stu-id="f9eea-115">Office 365 E5 and EMS E5 trial or paid subscriptions.</span></span>
- <span data-ttu-id="f9eea-116">连接到 Internet 的简化的组织 Intranet，包含 Azure 虚拟网络子网中的 DC1、APP1 和 CLIENT1 虚拟机。</span><span class="sxs-lookup"><span data-stu-id="f9eea-116">A simplified organization intranet connected to the Internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span> 
- <span data-ttu-id="f9eea-117">在 APP1 上运行的 Azure AD Connect，用于将 TESTLAB AD DS 域同步到 Office 365 和 EMS E5 订阅的 Azure AD 租户。</span><span class="sxs-lookup"><span data-stu-id="f9eea-117">Azure AD Connect runs on APP1 to synchronize the TESTLAB AD DS domain to the Azure AD tenant of your Office 365 and EMS E5 subscriptions.</span></span>

<span data-ttu-id="f9eea-118">接下来，按照[密码写回阶段 2](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain) 测试实验室指南中的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="f9eea-118">Next, follow the instructions in [Phase 2 of the password reset](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain) Test Lab Guide.</span></span>

<span data-ttu-id="f9eea-119">必须启用密码写回才能使用密码重置。</span><span class="sxs-lookup"><span data-stu-id="f9eea-119">You must have password reset enabled to use password writeback.</span></span>
  
## <a name="phase-2-configure-and-test-password-reset"></a><span data-ttu-id="f9eea-120">第 2 阶段：配置和测试密码重置</span><span class="sxs-lookup"><span data-stu-id="f9eea-120">Phase 2: Configure and test password reset</span></span>

<span data-ttu-id="f9eea-121">在这一阶段，通过组成员身份在 Azure AD 租户中配置密码重置，然后验证它是否能够正常工作。</span><span class="sxs-lookup"><span data-stu-id="f9eea-121">In this phase, you configure password reset in the Azure AD tenant through group membership, and then verify that it works.</span></span>

<span data-ttu-id="f9eea-122">首先，为特定 Azure AD 组中的帐户启用密码重置。</span><span class="sxs-lookup"><span data-stu-id="f9eea-122">First, enable password reset for the accounts in a specific Azure AD group.</span></span>

1. <span data-ttu-id="f9eea-123">在浏览器的专用实例中，打开 [https://portal.azure.com](https://portal.azure.com)，然后使用全局管理员帐户的凭据登录。</span><span class="sxs-lookup"><span data-stu-id="f9eea-123">From a private instance of your browser, open [https://portal.azure.com](https://portal.azure.com), and then sign in with the credentials of your global administrator account.</span></span>
2. <span data-ttu-id="f9eea-124">在 Azure 门户中，单击“Azure Active Directory”>“组”>“新组”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f9eea-124">In the Azure portal, click **Azure Active Directory > Groups > New group**.</span></span>
3. <span data-ttu-id="f9eea-p102">将“组类型”\*\*\*\* 设置为“安全”\*\*\*\*，将“组名称”\*\*\*\* 设置为“PWReset”\*\*\*\*，将“成员身份类型”\*\*\*\* 设置为“分配”\*\*\*\*。单击“创建”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f9eea-p102">Set the **Group type** to **Security**, **Group name** to **PWReset**, and the **Membership type** to **Assigned**. Click **Create**.</span></span>
5. <span data-ttu-id="f9eea-127">单击列表中的“PWReset”\*\*\*\* 组，然后单击“成员”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f9eea-127">Click the **PWReset** group in the list, and then click **Members**.</span></span>
6. <span data-ttu-id="f9eea-p103">依次单击“添加成员”\*\*\*\*、“用户 2”\*\*\*\*，再单击“选择”\*\*\*\*。关闭“PWReset”\*\*\*\* 和“组”\*\*\*\* 页。</span><span class="sxs-lookup"><span data-stu-id="f9eea-p103">Click **Add members**, click **User 2**, and then click **Select**. Close the **PWReset** and **Group** pages.</span></span>
7. <span data-ttu-id="f9eea-130">在 Azure Active Directory 页上，单击“密码重置”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f9eea-130">On the Azure Active Directory page, click **Password reset**.</span></span>
8. <span data-ttu-id="f9eea-131">在“属性”\*\*\*\* 页的“自助服务密码重置已启用”\*\*\*\* 选项下，选择“已选择”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f9eea-131">From the **Properties** page, under the option **Self Service Password Reset Enabled**, choose **Selected**.</span></span>
9. <span data-ttu-id="f9eea-132">从“选择组”\*\*\*\* 中选择“PWReset”\*\*\*\*，然后单击“保存”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f9eea-132">From **Select group**, select **PWReset**, and then click **Save**.</span></span>
10. <span data-ttu-id="f9eea-133">关闭专用浏览器实例。</span><span class="sxs-lookup"><span data-stu-id="f9eea-133">Close the private browser instance.</span></span>

<span data-ttu-id="f9eea-134">接下来，为用户 2 帐户测试密码重置。</span><span class="sxs-lookup"><span data-stu-id="f9eea-134">Next, you test password reset for the User 2 account.</span></span>

1. <span data-ttu-id="f9eea-135">打开新的专用浏览器实例并浏览到 [https://aka.ms/ssprsetup](https://aka.ms/ssprsetup)。</span><span class="sxs-lookup"><span data-stu-id="f9eea-135">Open a new private browser instance and browse to [https://aka.ms/ssprsetup](https://aka.ms/ssprsetup).</span></span>
2. <span data-ttu-id="f9eea-136">使用用户 2 帐户凭据登录。</span><span class="sxs-lookup"><span data-stu-id="f9eea-136">Sign in with the User 2 account credentials.</span></span>
3. <span data-ttu-id="f9eea-137">在“不丢失对帐户的访问权限”\*\*\*\* 中，将身份验证电话设置为你的手机号码，并将身份验证电子邮件设置为你的工作或个人电子邮件帐户。</span><span class="sxs-lookup"><span data-stu-id="f9eea-137">In **Don’t lose access to your account**, set the authentication phone to your mobile phone number and the authentication email to your work or personal email account.</span></span>
4. <span data-ttu-id="f9eea-138">对这两项进行验证后，单击“良好”\*\*\*\*，然后关闭浏览器的专用实例。</span><span class="sxs-lookup"><span data-stu-id="f9eea-138">After both are verified, click **Looks good** and close the private instance of the browser.</span></span>
5. <span data-ttu-id="f9eea-139">打开新的专用浏览器实例并转到 [https://aka.ms/sspr](https://aka.ms/sspr)</span><span class="sxs-lookup"><span data-stu-id="f9eea-139">Open a new private browser instance and go to [https://aka.ms/sspr](https://aka.ms/sspr).</span></span>
6. <span data-ttu-id="f9eea-140">使用用户 2 帐户凭据登录，键入 CAPTCHA 中的字符，然后单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f9eea-140">Sign in with the User 2 account credentials, type the characters from the CAPTCHA, and then click **Next**.</span></span>
8. <span data-ttu-id="f9eea-p104">对于“验证步骤 1”\*\*\*\*，单击“以电子邮件形式发送备用电子邮件”\*\*\*\*，然后单击“电子邮件”\*\*\*\*。在收到电子邮件时，键入验证码，然后单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f9eea-p104">For **verification step 1**, click **Email my alternate email**, and then click **Email**. When you receive the email, type the verification code, and then click **Next**.</span></span>
9. <span data-ttu-id="f9eea-p105">在“返回到帐户”\*\*\*\* 中，键入用户 2 帐户的新密码，然后单击“完成”\*\*\*\*。记录用户 2 帐户更改后的密码，然后将其存储在一个安全的位置。</span><span class="sxs-lookup"><span data-stu-id="f9eea-p105">In **Get back into your account**, type a new password for the User 2 account, and then click **Finish**. Note the changed password of the User 2 account and store it in a safe location.</span></span>
10. <span data-ttu-id="f9eea-p106">在同一浏览器的独立选项卡中，转到 [https://office.com](https://office.com)，然后使用用户 2 帐户名及其新密码登录。应看到 Office 主\*\*\*\* 页面。</span><span class="sxs-lookup"><span data-stu-id="f9eea-p106">In a separate tab of the same browser, go to [https://office.com](https://office.com), and then sign in with the User 2 account name and its new password. You should see the **Office Home** page.</span></span>

<span data-ttu-id="f9eea-147">有关在生产中配置密码重置的信息和相关链接，请参阅“标识”阶段中的[简化密码重置](identity-password-reset.md#identity-pw-reset)步骤。</span><span class="sxs-lookup"><span data-stu-id="f9eea-147">See the [Simplify password resets](identity-password-reset.md#identity-pw-reset) step in the Identity phase for information and links to configure password resets in production.</span></span>

## <a name="next-step"></a><span data-ttu-id="f9eea-148">后续步骤</span><span class="sxs-lookup"><span data-stu-id="f9eea-148">Next step</span></span>

<span data-ttu-id="f9eea-149">在测试环境中探索其他[标识](m365-enterprise-test-lab-guides.md#identity)特性和功能。</span><span class="sxs-lookup"><span data-stu-id="f9eea-149">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="f9eea-150">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f9eea-150">See also</span></span>

[<span data-ttu-id="f9eea-151">Microsoft 365 企业版测试实验室指南</span><span class="sxs-lookup"><span data-stu-id="f9eea-151">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="f9eea-152">部署 Microsoft 365 企业版</span><span class="sxs-lookup"><span data-stu-id="f9eea-152">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="f9eea-153">Microsoft 365 企业版文档</span><span class="sxs-lookup"><span data-stu-id="f9eea-153">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
