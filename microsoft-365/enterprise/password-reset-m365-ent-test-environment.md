---
title: Microsoft 365 测试环境的密码重置
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/13/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom:
- TLGS
- Ent_TLGs
ms.assetid: ''
description: 摘要：配置和测试适用于 Microsoft 365 测试环境的密码重置。
ms.openlocfilehash: 5d98dcc50f16bc08da787a928beeeacf825201c9
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487420"
---
# <a name="password-reset-for-your-microsoft-365-test-environment"></a><span data-ttu-id="cc508-103">Microsoft 365 测试环境的密码重置</span><span class="sxs-lookup"><span data-stu-id="cc508-103">Password reset for your Microsoft 365 test environment</span></span>

<span data-ttu-id="cc508-104">*此测试实验室指南仅可用于企业测试环境的 Microsoft 365。*</span><span class="sxs-lookup"><span data-stu-id="cc508-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="cc508-105">借助 Azure Active Directory (Azure AD) 自助服务密码重置 (SSPR)，用户可重置或解锁其密码或帐户。</span><span class="sxs-lookup"><span data-stu-id="cc508-105">Azure Active Directory (Azure AD) self-service password reset (SSPR) allows users to reset or unlock their passwords or accounts.</span></span>

<span data-ttu-id="cc508-106">本文介绍如何在 Microsoft 365 测试环境中配置和测试密码重置。</span><span class="sxs-lookup"><span data-stu-id="cc508-106">This article describes how to configure and test password resets in your Microsoft 365 test environment.</span></span>

<span data-ttu-id="cc508-107">设置 SSPR 包括三个阶段：</span><span class="sxs-lookup"><span data-stu-id="cc508-107">Setting up SSPR involves three phases:</span></span>
- [<span data-ttu-id="cc508-108">阶段 1：为 Microsoft 365 测试环境配置密码哈希同步</span><span class="sxs-lookup"><span data-stu-id="cc508-108">Phase 1: Configure password hash synchronization for your Microsoft 365 test environment</span></span>](#phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment)
- [<span data-ttu-id="cc508-109">阶段 2：启用密码写回</span><span class="sxs-lookup"><span data-stu-id="cc508-109">Phase 2: Enable password writeback</span></span>](#phase-2-enable-password-writeback)
- [<span data-ttu-id="cc508-110">第 3 阶段：配置和测试密码重置</span><span class="sxs-lookup"><span data-stu-id="cc508-110">Phase 3: Configure and test password reset</span></span>](#phase-3-configure-and-test-password-reset)
    
![Microsoft 云测试实验室指南](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="cc508-112">若要了解到 Microsoft 365 for 企业测试实验室指南堆栈中的所有文章的可视化地图，请转到 [microsoft 365 for Enterprise Test Lab Guide stack](../downloads/Microsoft365EnterpriseTLGStack.pdf)。</span><span class="sxs-lookup"><span data-stu-id="cc508-112">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>

## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a><span data-ttu-id="cc508-113">阶段 1：为 Microsoft 365 测试环境配置密码哈希同步</span><span class="sxs-lookup"><span data-stu-id="cc508-113">Phase 1: Configure password hash synchronization for your Microsoft 365 test environment</span></span>

<span data-ttu-id="cc508-114">首先，按照 " [密码哈希同步](password-hash-sync-m365-ent-test-environment.md)" 中的说明操作。</span><span class="sxs-lookup"><span data-stu-id="cc508-114">First, follow the instructions in [password hash synchronization](password-hash-sync-m365-ent-test-environment.md).</span></span> 

<span data-ttu-id="cc508-115">生成的配置如下所示：</span><span class="sxs-lookup"><span data-stu-id="cc508-115">Your resulting configuration looks like this:</span></span>
  
![使用密码哈希同步测试环境的模拟企业配置](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
<span data-ttu-id="cc508-117">此配置包括：</span><span class="sxs-lookup"><span data-stu-id="cc508-117">This configuration consists of:</span></span>
  
- <span data-ttu-id="cc508-118">Microsoft 365 E5 试用版或付费版订阅。</span><span class="sxs-lookup"><span data-stu-id="cc508-118">A Microsoft 365 E5 trial or paid subscription.</span></span>
- <span data-ttu-id="cc508-119">连接到 internet 的简化的组织 intranet，由 Azure 虚拟网络的子网上的 DC1、APP1 和 CLIENT1 虚拟机组成。</span><span class="sxs-lookup"><span data-stu-id="cc508-119">A simplified organization intranet connected to the internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span>
- <span data-ttu-id="cc508-120">在 APP1 上运行的 Azure AD Connect，用于将 TESTLAB Active Directory 域服务 (AD DS) 域同步到 Microsoft 365 订阅的 Azure AD 租户。</span><span class="sxs-lookup"><span data-stu-id="cc508-120">Azure AD Connect runs on APP1 to synchronize the TESTLAB Active Directory Domain Services (AD DS) domain to the Azure AD tenant of your Microsoft 365 subscription.</span></span>

## <a name="phase-2-enable-password-writeback"></a><span data-ttu-id="cc508-121">阶段 2：启用密码写回</span><span class="sxs-lookup"><span data-stu-id="cc508-121">Phase 2: Enable password writeback</span></span>

<span data-ttu-id="cc508-122">接下来，按照[“密码写回”测试实验室指南的阶段 2](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain) 中的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="cc508-122">Follow the instructions in [Phase 2 of the password writeback Test Lab Guide](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain).</span></span>

<span data-ttu-id="cc508-123">必须启用密码写回才能使用密码重置。</span><span class="sxs-lookup"><span data-stu-id="cc508-123">You must have password writeback enabled to use password reset.</span></span>
  
## <a name="phase-3-configure-and-test-password-reset"></a><span data-ttu-id="cc508-124">第 3 阶段：配置和测试密码重置</span><span class="sxs-lookup"><span data-stu-id="cc508-124">Phase 3: Configure and test password reset</span></span>

<span data-ttu-id="cc508-125">在此阶段中，通过组成员身份在 Azure AD 租户中配置密码重置，然后验证它是否正常工作。</span><span class="sxs-lookup"><span data-stu-id="cc508-125">In this phase, configure password reset in the Azure AD tenant through group membership, and then verify that it works.</span></span>

<span data-ttu-id="cc508-126">首先，为特定 Azure AD 组中的帐户启用密码重置。</span><span class="sxs-lookup"><span data-stu-id="cc508-126">First, enable password reset for the accounts in a specific Azure AD group.</span></span>

1. <span data-ttu-id="cc508-127">在浏览器的专用实例中，打开 [https://portal.azure.com](https://portal.azure.com)，然后使用全局管理员帐户的凭据登录。</span><span class="sxs-lookup"><span data-stu-id="cc508-127">From a private instance of your browser, open [https://portal.azure.com](https://portal.azure.com), and then sign in with the credentials of your global administrator account.</span></span>
2. <span data-ttu-id="cc508-128">在 azure 门户中，选择 " **azure Active Directory**  >  **组**  >  **新组**"。</span><span class="sxs-lookup"><span data-stu-id="cc508-128">In the Azure portal, select **Azure Active Directory** > **Groups** > **New group**.</span></span>
3. <span data-ttu-id="cc508-129">将“**组类型**”设置为“**安全**”，将“**组名称**”设置为“**PWReset**”，将“**成员身份类型**”设置为“**已分配**”。</span><span class="sxs-lookup"><span data-stu-id="cc508-129">Set the **Group type** to **Security**, **Group name** to **PWReset**, and the **Membership type** to **Assigned**.</span></span>
4. <span data-ttu-id="cc508-130">选择 " **成员**"，查找并选择 " **用户 3**"，选择 " **选择**"，然后选择 " **创建**"。</span><span class="sxs-lookup"><span data-stu-id="cc508-130">Select **Members**, find and select **User 3**, select **Select**, and then select **Create**.</span></span>
5. <span data-ttu-id="cc508-131">关闭“**组**”窗格。</span><span class="sxs-lookup"><span data-stu-id="cc508-131">Close the **Groups** pane.</span></span>
6. <span data-ttu-id="cc508-132">在 "Azure Active Directory" 窗格中，选择左侧导航栏中的 " **密码重置** "。</span><span class="sxs-lookup"><span data-stu-id="cc508-132">In the Azure Active Directory pane, select **Password reset** in the left navigation.</span></span>
7. <span data-ttu-id="cc508-133">在“**密码重置属性**”窗格的“**已启用自助式密码重置**”选项下，选中“**已选择**”。</span><span class="sxs-lookup"><span data-stu-id="cc508-133">In the **Password reset-Properties** pane, under the option **Self Service Password Reset Enabled**, choose **Selected**.</span></span>
8. <span data-ttu-id="cc508-134">选择 "**选择组**"，选择 " **PWReset** " 组，然后选择 "**选择**  >  **保存**"。</span><span class="sxs-lookup"><span data-stu-id="cc508-134">Select **Select group**, select the **PWReset** group, and then select **Select** > **Save**.</span></span>
9. <span data-ttu-id="cc508-135">关闭专用浏览器实例。</span><span class="sxs-lookup"><span data-stu-id="cc508-135">Close the private browser instance.</span></span>

<span data-ttu-id="cc508-136">接下来，为用户3帐户测试密码重置。</span><span class="sxs-lookup"><span data-stu-id="cc508-136">Next, test password reset for the User 3 account.</span></span>

1. <span data-ttu-id="cc508-137">打开新的专用浏览器实例并浏览到 [https://aka.ms/ssprsetup](https://aka.ms/ssprsetup)。</span><span class="sxs-lookup"><span data-stu-id="cc508-137">Open a new private browser instance and browse to [https://aka.ms/ssprsetup](https://aka.ms/ssprsetup).</span></span>
1. <span data-ttu-id="cc508-138">使用用户 3 帐户凭据登录。</span><span class="sxs-lookup"><span data-stu-id="cc508-138">Sign in with the User 3 account credentials.</span></span>
1. <span data-ttu-id="cc508-139">在 " **需要详细信息**" 中，选择 " **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="cc508-139">In **More information required**, select **Next**.</span></span> 
1. <span data-ttu-id="cc508-140">在“不丢失对帐户的访问权限”\*\*\*\* 中，将身份验证电话设置为你的移动电话号码，并将身份验证电子邮件地址设置为你的工作或个人电子邮件帐户。</span><span class="sxs-lookup"><span data-stu-id="cc508-140">In **Don't lose access to your account**, set the authentication phone to your mobile phone number and the authentication email to your work or personal email account.</span></span>
1. <span data-ttu-id="cc508-141">经过验证后，选择 " **外观**"，然后关闭浏览器的专用实例。</span><span class="sxs-lookup"><span data-stu-id="cc508-141">After both are verified, select **Looks good**, and then close the private instance of the browser.</span></span>
1. <span data-ttu-id="cc508-142">在新的专用浏览器实例中，转到 [https://aka.ms/sspr](https://aka.ms/sspr) 。</span><span class="sxs-lookup"><span data-stu-id="cc508-142">In a new private browser instance, go to [https://aka.ms/sspr](https://aka.ms/sspr).</span></span>
1. <span data-ttu-id="cc508-143">输入用户3帐户名称，输入 CAPTCHA 中的字符，然后选择 " **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="cc508-143">Enter the User 3 account name, enter the characters from the CAPTCHA, and then select **Next**.</span></span>
1. <span data-ttu-id="cc508-144">对于 **验证步骤 1**，请选择 **"电子邮件-我的备用电子邮件**"，然后选择 " **电子邮件**"。</span><span class="sxs-lookup"><span data-stu-id="cc508-144">For **verification step 1**, select **Email my alternate email**, and then select **Email**.</span></span> <span data-ttu-id="cc508-145">当您收到电子邮件时，请输入验证代码，然后选择 " **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="cc508-145">When you receive the email, enter the verification code, and then select **Next**.</span></span>
1. <span data-ttu-id="cc508-146">在 " **返回到帐户**" 中，为用户3帐户输入一个新密码，然后选择 " **完成**"。</span><span class="sxs-lookup"><span data-stu-id="cc508-146">In **Get back into your account**, enter a new password for the User 3 account, and then select **Finish**.</span></span> <span data-ttu-id="cc508-147">记下已更改的用户 3 帐户密码并将其存储在安全的位置。</span><span class="sxs-lookup"><span data-stu-id="cc508-147">Note the changed password of the User 3 account and store it in a safe location.</span></span>
1. <span data-ttu-id="cc508-148">在同一浏览器的独立选项卡中，转到 [https://portal.office.com](https://portal.office.com)，然后使用用户 3 帐户名及其新密码登录。</span><span class="sxs-lookup"><span data-stu-id="cc508-148">In a separate tab of the same browser, go to [https://portal.office.com](https://portal.office.com), and then sign in with the User 3 account name and its new password.</span></span> <span data-ttu-id="cc508-149">应该会看到“Microsoft Office 主页”页面。\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="cc508-149">You should see the **Microsoft Office Home** page.</span></span>

## <a name="next-step"></a><span data-ttu-id="cc508-150">后续步骤</span><span class="sxs-lookup"><span data-stu-id="cc508-150">Next step</span></span>

<span data-ttu-id="cc508-151">在测试环境中探索其他[标识](m365-enterprise-test-lab-guides.md#identity)特性和功能。</span><span class="sxs-lookup"><span data-stu-id="cc508-151">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="cc508-152">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cc508-152">See also</span></span>

[<span data-ttu-id="cc508-153">Microsoft 365 企业版测试实验室指南</span><span class="sxs-lookup"><span data-stu-id="cc508-153">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="cc508-154">Microsoft 365 企业版概述</span><span class="sxs-lookup"><span data-stu-id="cc508-154">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="cc508-155">适用于企业的 Microsoft 365 文档</span><span class="sxs-lookup"><span data-stu-id="cc508-155">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
