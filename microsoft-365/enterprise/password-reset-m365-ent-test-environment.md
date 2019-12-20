---
title: Microsoft 365 测试环境的密码重置
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/13/2019
audience: ITPro
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
ms.openlocfilehash: 930c5b4a4ddcc4866a586ff444380ff6dcd66238
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/19/2019
ms.locfileid: "40801407"
---
# <a name="password-reset-for-your-microsoft-365-test-environment"></a><span data-ttu-id="51db2-103">Microsoft 365 测试环境的密码重置</span><span class="sxs-lookup"><span data-stu-id="51db2-103">Password reset for your Microsoft 365 test environment</span></span>

<span data-ttu-id="51db2-104">*此测试实验室指南仅可用于 Microsoft 365 企业版测试环境。*</span><span class="sxs-lookup"><span data-stu-id="51db2-104">*This Test Lab Guide can only be used for Microsoft 365 Enterprise test environments.*</span></span>

<span data-ttu-id="51db2-105">借助 Azure Active Directory (Azure AD) 自助服务密码重置 (SSPR)，用户可重置或解锁其密码或帐户。</span><span class="sxs-lookup"><span data-stu-id="51db2-105">Azure Active Directory (Azure AD) self-service password reset (SSPR) allows users to reset or unlock their passwords or accounts.</span></span> 

<span data-ttu-id="51db2-106">本文介绍如何分三个阶段在 Microsoft 365 测试环境中配置和测试密码重置：</span><span class="sxs-lookup"><span data-stu-id="51db2-106">This article describes how you can configure and test password resets in your Microsoft 365 test environment in three phases:</span></span>

1.  <span data-ttu-id="51db2-107">创建 Microsoft 365 企业版测试环境。</span><span class="sxs-lookup"><span data-stu-id="51db2-107">Create the Microsoft 365 Enterprise test environment.</span></span>
2.  <span data-ttu-id="51db2-108">启用密码写回。</span><span class="sxs-lookup"><span data-stu-id="51db2-108">Enable password writeback.</span></span>
3.  <span data-ttu-id="51db2-109">为用户 3 帐户配置和测试密码重置。</span><span class="sxs-lookup"><span data-stu-id="51db2-109">Configure and test password reset for the User 2 account.</span></span>
    
![Microsoft 云测试实验室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="51db2-111">单击[此处](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf)可查看 Microsoft 365 企业版测试实验室指南集合中所有文章的直观图。</span><span class="sxs-lookup"><span data-stu-id="51db2-111">Click [here](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>

## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a><span data-ttu-id="51db2-112">阶段 1：为 Microsoft 365 测试环境配置密码哈希同步</span><span class="sxs-lookup"><span data-stu-id="51db2-112">Phase 1: Configure password hash synchronization for your Microsoft 365 test environment</span></span>

<span data-ttu-id="51db2-p101">首先，按照[密码哈希同步](password-hash-sync-m365-ent-test-environment.md)中的说明操作。下面是生成的配置。</span><span class="sxs-lookup"><span data-stu-id="51db2-p101">First, follow the instructions in [password hash synchronization](password-hash-sync-m365-ent-test-environment.md). Here is your resulting configuration.</span></span>
  
![使用密码哈希同步测试环境的模拟企业配置](media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
<span data-ttu-id="51db2-116">此配置包括：</span><span class="sxs-lookup"><span data-stu-id="51db2-116">This configuration consists of:</span></span> 
  
- <span data-ttu-id="51db2-117">Microsoft 365 E5 或 Office 365 E5 试用版或付费版订阅。</span><span class="sxs-lookup"><span data-stu-id="51db2-117">Microsoft 365 E5 or Office 365 E5 trial or paid subscriptions.</span></span>
- <span data-ttu-id="51db2-118">连接到 Internet 的简化的组织 Intranet，包含 Azure 虚拟网络子网中的 DC1、APP1 和 CLIENT1 虚拟机。</span><span class="sxs-lookup"><span data-stu-id="51db2-118">A simplified organization intranet connected to the Internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span> 
- <span data-ttu-id="51db2-119">在 APP1 上运行的 Azure AD Connect，用于将 TESTLAB Active Directory 域服务 (AD DS) 同步到 Microsoft 365 或 Office 365 订阅的 Azure AD 租户。</span><span class="sxs-lookup"><span data-stu-id="51db2-119">Azure AD Connect runs on APP1 to synchronize the TESTLAB Active Directory Domain Services (AD DS) domain to the Azure AD tenant of your Microsoft 365 or Office 365 subscription.</span></span>

## <a name="phase-2-enable-password-writeback"></a><span data-ttu-id="51db2-120">阶段 2：启用密码写回</span><span class="sxs-lookup"><span data-stu-id="51db2-120">Phase 2: Enable password writeback</span></span>

<span data-ttu-id="51db2-121">接下来，按照[“密码写回”测试实验室指南的阶段 2](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain) 中的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="51db2-121">Follow the instructions in [Phase 2 of the password writeback Test Lab Guide](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain).</span></span>

<span data-ttu-id="51db2-122">必须启用密码写回才能使用密码重置。</span><span class="sxs-lookup"><span data-stu-id="51db2-122">You must have password writeback enabled to use password reset.</span></span>
  
## <a name="phase-3-configure-and-test-password-reset"></a><span data-ttu-id="51db2-123">第 3 阶段：配置和测试密码重置</span><span class="sxs-lookup"><span data-stu-id="51db2-123">Phase 3: Configure and test password reset</span></span>

<span data-ttu-id="51db2-124">在这一阶段，通过组成员身份在 Azure AD 租户中配置密码重置，然后验证它是否能够正常工作。</span><span class="sxs-lookup"><span data-stu-id="51db2-124">In this phase, you configure password reset in the Azure AD tenant through group membership, and then verify that it works.</span></span>

<span data-ttu-id="51db2-125">首先，为特定 Azure AD 组中的帐户启用密码重置。</span><span class="sxs-lookup"><span data-stu-id="51db2-125">First, enable password reset for the accounts in a specific Azure AD group.</span></span>

1. <span data-ttu-id="51db2-126">在浏览器的专用实例中，打开 [https://portal.azure.com](https://portal.azure.com)，然后使用全局管理员帐户的凭据登录。</span><span class="sxs-lookup"><span data-stu-id="51db2-126">From a private instance of your browser, open [https://portal.azure.com](https://portal.azure.com), and then sign in with the credentials of your global administrator account.</span></span>
2. <span data-ttu-id="51db2-127">在 Azure 门户中，单击“Azure Active Directory”>“组”>“新组”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="51db2-127">In the Azure portal, click **Azure Active Directory > Groups > New group**.</span></span>
3. <span data-ttu-id="51db2-128">将“**组类型**”设置为“**安全**”，将“**组名称**”设置为“**PWReset**”，将“**成员身份类型**”设置为“**已分配**”。</span><span class="sxs-lookup"><span data-stu-id="51db2-128">Set the **Group type** to **Security**, **Group name** to **PWReset**, and the **Membership type** to **Assigned**. Click Create.</span></span> 
4. <span data-ttu-id="51db2-129">单击“**成员**”，查找并选择**用户 3**，然后单击“**选择**”，再单击“**创建**”。</span><span class="sxs-lookup"><span data-stu-id="51db2-129">Click **Members**, find and select **User 3**, and then click **Select**, and then click **Create**.</span></span>
5. <span data-ttu-id="51db2-130">关闭“**组**”窗格。</span><span class="sxs-lookup"><span data-stu-id="51db2-130">Close the **Groups** pane.</span></span>
6. <span data-ttu-id="51db2-131">在 Azure Active Directory 窗格中，单击左侧导航兰中的“**密码重置**”。</span><span class="sxs-lookup"><span data-stu-id="51db2-131">In the Azure Active Directory pane, click **Password reset** in the left navigation.</span></span>
7. <span data-ttu-id="51db2-132">在“**密码重置属性**”窗格的“**已启用自助式密码重置**”选项下，选中“**已选择**”。</span><span class="sxs-lookup"><span data-stu-id="51db2-132">From the **Properties** page, under the option **Self Service Password Reset Enabled**, choose **Selected**.</span></span>
8. <span data-ttu-id="51db2-133">单击“**选择组**”，选择“**PWReset**组，然后单击**选择”>“保存”**。</span><span class="sxs-lookup"><span data-stu-id="51db2-133">Click **Select group**, select the **PWReset** group, and then click **Select > Save**.</span></span>
9. <span data-ttu-id="51db2-134">关闭专用浏览器实例。</span><span class="sxs-lookup"><span data-stu-id="51db2-134">Close the private browser instance.</span></span>

<span data-ttu-id="51db2-135">接下来，为用户 3 帐户测试密码重置。</span><span class="sxs-lookup"><span data-stu-id="51db2-135">Next, you test password reset for the User 2 account.</span></span>

1. <span data-ttu-id="51db2-136">打开新的专用浏览器实例并浏览到 [https://aka.ms/ssprsetup](https://aka.ms/ssprsetup)。</span><span class="sxs-lookup"><span data-stu-id="51db2-136">Open a new private browser instance and browse to [https://aka.ms/ssprsetup](https://aka.ms/ssprsetup).</span></span>
2. <span data-ttu-id="51db2-137">使用用户 3 帐户凭据登录。</span><span class="sxs-lookup"><span data-stu-id="51db2-137">Sign in with the User 2 account credentials.</span></span>
3. <span data-ttu-id="51db2-138">在“**需要详细信息**”中，单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="51db2-138">In **More information required**, click **Next**.</span></span> 
5. <span data-ttu-id="51db2-139">在“不丢失对帐户的访问权限”\*\*\*\* 中，将身份验证电话设置为你的手机号码，并将身份验证电子邮件设置为你的工作或个人电子邮件帐户。</span><span class="sxs-lookup"><span data-stu-id="51db2-139">In **Don’t lose access to your account**, set the authentication phone to your mobile phone number and the authentication email to your work or personal email account.</span></span>
7. <span data-ttu-id="51db2-140">对这两项进行验证后，单击“良好”\*\*\*\*，然后关闭浏览器的专用实例。</span><span class="sxs-lookup"><span data-stu-id="51db2-140">After both are verified, click **Looks good** and close the private instance of the browser.</span></span>
8. <span data-ttu-id="51db2-141">打开新的专用浏览器实例并转到 [https://aka.ms/sspr](https://aka.ms/sspr)</span><span class="sxs-lookup"><span data-stu-id="51db2-141">Open a new private browser instance and go to [https://aka.ms/sspr](https://aka.ms/sspr).</span></span>
9. <span data-ttu-id="51db2-142">键入用户 3 帐户的名称，键入来自 CAPTCHA 的字符，然后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="51db2-142">Sign in with the User 2 account credentials, type the characters from the CAPTCHA, and then click **Next**.</span></span>
10. <span data-ttu-id="51db2-p102">对于“验证步骤 1”\*\*\*\*，单击“以电子邮件形式发送备用电子邮件”\*\*\*\*，然后单击“电子邮件”\*\*\*\*。在收到电子邮件时，键入验证码，然后单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="51db2-p102">For **verification step 1**, click **Email my alternate email**, and then click **Email**. When you receive the email, type the verification code, and then click **Next**.</span></span>
11. <span data-ttu-id="51db2-145">在“**返回帐户**”中，键入用户 3 帐户的新密码，然后单击“**完成**”。</span><span class="sxs-lookup"><span data-stu-id="51db2-145">In **Get back into your account**, type a new password for the User 2 account, and then click **Finish**. Note the changed password of the User 2 account and store it in a safe location.</span></span> <span data-ttu-id="51db2-146">记下已更改的用户 3 帐户密码并将其存储在安全的位置。</span><span class="sxs-lookup"><span data-stu-id="51db2-146">Note the changed password of the User 3 account and store it in a safe location.</span></span>
12. <span data-ttu-id="51db2-147">在同一浏览器的独立选项卡中，转到 [https://portal.office.com](https://portal.office.com)，然后使用用户 3 帐户名及其新密码登录。</span><span class="sxs-lookup"><span data-stu-id="51db2-147">In a separate tab of the same browser, go to [https://portal.office.com](https://portal.office.com), and then sign in with the User 2 account name and its new password.</span></span> <span data-ttu-id="51db2-148">应该会看到“Microsoft Office 主页”页面。\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="51db2-148">You should see the **Microsoft Office Home** page.</span></span>

<span data-ttu-id="51db2-149">有关在生产中配置密码重置的信息和相关链接，请参阅“标识”阶段中的[简化密码重置](identity-secure-your-passwords.md#identity-pw-reset)步骤。</span><span class="sxs-lookup"><span data-stu-id="51db2-149">See the [Simplify password resets](identity-secure-your-passwords.md#identity-pw-reset) step in the Identity phase for information and links to configure password resets in production.</span></span>

## <a name="next-step"></a><span data-ttu-id="51db2-150">后续步骤</span><span class="sxs-lookup"><span data-stu-id="51db2-150">Next step</span></span>

<span data-ttu-id="51db2-151">在测试环境中探索其他[标识](m365-enterprise-test-lab-guides.md#identity)特性和功能。</span><span class="sxs-lookup"><span data-stu-id="51db2-151">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="51db2-152">另请参阅</span><span class="sxs-lookup"><span data-stu-id="51db2-152">See also</span></span>

[<span data-ttu-id="51db2-153">Microsoft 365 企业版测试实验室指南</span><span class="sxs-lookup"><span data-stu-id="51db2-153">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="51db2-154">部署 Microsoft 365 企业版</span><span class="sxs-lookup"><span data-stu-id="51db2-154">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="51db2-155">Microsoft 365 企业版文档</span><span class="sxs-lookup"><span data-stu-id="51db2-155">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
