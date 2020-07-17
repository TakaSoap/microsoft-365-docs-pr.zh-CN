---
title: Microsoft 365 企业版测试环境多重身份验证
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/12/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom:
- TLG
- Ent_TLGs
- seo-marvel-apr2020
description: 使用发送到 Microsoft 365 企业版测试环境中的智能手机的短信配置多重身份验证。
ms.openlocfilehash: e26fb7470e01397266f5f424ee45941a79a2940c
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/19/2020
ms.locfileid: "44819372"
---
# <a name="multi-factor-authentication-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="4a160-103">Microsoft 365 企业版测试环境的多重身份验证</span><span class="sxs-lookup"><span data-stu-id="4a160-103">Multi-factor authentication for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="4a160-104">*本测试实验室指南可用于 Microsoft 365 企业版和 Office 365 企业版测试环境。*</span><span class="sxs-lookup"><span data-stu-id="4a160-104">*This Test Lab Guide can be used for both Microsoft 365 Enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="4a160-105">若要使用其他级别的安全来登录 Microsoft 365 或使用 Azure AD 租户订阅订阅的任何服务或应用程序，您可以启用 Azure 多重身份验证，它需要的用户和密码不只需要用户名和密码即可验证帐户。</span><span class="sxs-lookup"><span data-stu-id="4a160-105">For an additional level of security for signing in to Microsoft 365 or any service or application that uses the Azure AD tenant for your subscription, you can enable Azure multi-factor authentication, which requires more than just a username and password to verify an account.</span></span> 

<span data-ttu-id="4a160-106">使用多重身份验证，用户需要确认电话呼叫，在短信中键入验证代码，或在正确输入密码后验证智能手机上的应用程序的身份验证。</span><span class="sxs-lookup"><span data-stu-id="4a160-106">With multi-factor authentication, users are required to acknowledge a phone call, type a verification code sent in a text message, or verify the authentication with an app on their smart phones after correctly entering their passwords.</span></span> <span data-ttu-id="4a160-107">仅在满足第二个身份验证因素时才能登录。</span><span class="sxs-lookup"><span data-stu-id="4a160-107">They can sign in only after this second authentication factor has been satisfied.</span></span> 
  
<span data-ttu-id="4a160-108">本文介绍如何为特定用户帐户启用和测试基于短信的身份验证。</span><span class="sxs-lookup"><span data-stu-id="4a160-108">This article describes how to enable and test text message-based authentication for a specific user account.</span></span>
  
<span data-ttu-id="4a160-109">为 Microsoft 365 企业版测试环境中的帐户设置多重身份验证有两个阶段：</span><span class="sxs-lookup"><span data-stu-id="4a160-109">There are two phases to setting up multi-factor authentication for an account in your Microsoft 365 Enterprise test environment:</span></span>
  
1. <span data-ttu-id="4a160-110">创建 Microsoft 365 企业版测试环境。</span><span class="sxs-lookup"><span data-stu-id="4a160-110">Create the Microsoft 365 Enterprise test environment.</span></span>
    
2. <span data-ttu-id="4a160-111">为 User 2 帐户启用并测试多重身份验证。</span><span class="sxs-lookup"><span data-stu-id="4a160-111">Enable and test multi-factor authentication for the User 2 account.</span></span>

3. <span data-ttu-id="4a160-112">使用条件访问策略启用和测试多重身份验证（可选）。</span><span class="sxs-lookup"><span data-stu-id="4a160-112">Enable and test multi-factor authentication with a conditional access policy (optional).</span></span>

![Microsoft 云测试实验室指南](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="4a160-114">转到 "[测试实验室指南" 堆栈](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf)，获取 Microsoft 365 企业版测试实验室指南堆栈中的所有文章的可视化地图。</span><span class="sxs-lookup"><span data-stu-id="4a160-114">Go to [Test Lab Guide Stack](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="4a160-115">阶段 1：构建 Microsoft 365 企业版测试环境。</span><span class="sxs-lookup"><span data-stu-id="4a160-115">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="4a160-116">如果只想使用最低要求以轻型方式测试多重身份验证，请按照[轻型基本配置](lightweight-base-configuration-microsoft-365-enterprise.md)中的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="4a160-116">If you just want to test multi-factor authentication in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="4a160-117">如果要在模拟的企业中测试多重身份验证，请按照[传递身份验证](pass-through-auth-m365-ent-test-environment.md)中的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="4a160-117">If you want to test multi-factor authentication in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="4a160-118">测试多重身份验证不需要模拟企业测试环境，其中包括连接到 Internet 的模拟 intranet 和 Active Directory 域服务（AD DS）林的目录同步。</span><span class="sxs-lookup"><span data-stu-id="4a160-118">Testing multi-factor authentication does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="4a160-119">它在此处作为一个选项提供，以便你可以测试多重身份验证，并在代表典型组织的环境中对其进行试验。</span><span class="sxs-lookup"><span data-stu-id="4a160-119">It is provided here as an option so that you can test multi-factor authentication and experiment with it in an environment that represents a typical organization.</span></span> 
  
## <a name="phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account"></a><span data-ttu-id="4a160-120">阶段 2：启用和测试 User 2 帐户的多重身份验证</span><span class="sxs-lookup"><span data-stu-id="4a160-120">Phase 2: Enable and test multi-factor authentication for the User 2 account</span></span>

<span data-ttu-id="4a160-121">通过以下步骤为 User 2 帐户启用多重身份验证：</span><span class="sxs-lookup"><span data-stu-id="4a160-121">Enable multi-factor authentication for the User 2 account with these steps:</span></span>
  
1. <span data-ttu-id="4a160-122">打开浏览器的单独私有实例，转到 Microsoft 365 管理中心（ [https://portal.microsoft.com](https://portal.microsoft.com) ），然后使用全局管理员帐户登录。</span><span class="sxs-lookup"><span data-stu-id="4a160-122">Open a separate, private instance of your browser, go to the Microsoft 365 admin center ([https://portal.microsoft.com](https://portal.microsoft.com)), and then sign in with your global administrator account.</span></span>
    
2. <span data-ttu-id="4a160-123">在左侧导航窗格中，单击“**用户 > 活动用户**”。</span><span class="sxs-lookup"><span data-stu-id="4a160-123">In the left navigation, click **Users > Active users**.</span></span>
    
3. <span data-ttu-id="4a160-124">在 "活动用户" 窗格中，单击 "**多因素身份验证**"。</span><span class="sxs-lookup"><span data-stu-id="4a160-124">In the Active users pane, click **Multi-factor authentication**.</span></span>
    
4. <span data-ttu-id="4a160-125">在列表中，选择 "**用户 2** " 帐户。</span><span class="sxs-lookup"><span data-stu-id="4a160-125">In the list, select the **User 2** account.</span></span>
    
5. <span data-ttu-id="4a160-126">在“User 2”\*\*\*\* 部分的“快速步骤”\*\*\*\* 下，单击“启用”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4a160-126">In the **User 2** section, under **Quick steps**, click **Enable**.</span></span>
    
6. <span data-ttu-id="4a160-127">在“关于启用多重身份验证”\*\*\*\* 对话框中，单击“启用多重身份验证”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4a160-127">In the **About enabling multi-factor auth** dialog box, click **Enable multi-factor auth**.</span></span>
    
7. <span data-ttu-id="4a160-128">在 "**更新成功**" 对话框中，单击 "**关闭**"。</span><span class="sxs-lookup"><span data-stu-id="4a160-128">In the **Updates successful** dialog box, click **Close**.</span></span>
    
8. <span data-ttu-id="4a160-129">在 " **Microsoft 365 管理中心**" 选项卡上，单击右上角的 "用户帐户" 图标，然后单击 **"注销"。**</span><span class="sxs-lookup"><span data-stu-id="4a160-129">On the **Microsoft 365 admin center** tab, click the user account icon in the upper right, and then click **Sign out**.</span></span>
    
9. <span data-ttu-id="4a160-130">关闭浏览器实例。</span><span class="sxs-lookup"><span data-stu-id="4a160-130">Close your browser instance.</span></span>
   
<span data-ttu-id="4a160-131">完成 User 2 帐户的配置，通过以下步骤，使用短信对其进行验证和测试：</span><span class="sxs-lookup"><span data-stu-id="4a160-131">Complete the configuration for the User 2 account to use a text message for validation and test it with these steps:</span></span>
  
1. <span data-ttu-id="4a160-132">打开浏览器的新的私有实例。</span><span class="sxs-lookup"><span data-stu-id="4a160-132">Open a new, private instance of your browser.</span></span>
    
2. <span data-ttu-id="4a160-133">转到 Office 365 门户（ [https://portal.office.com](https://portal.office.com) ），并使用用户2帐户名称和密码登录。</span><span class="sxs-lookup"><span data-stu-id="4a160-133">Go to the Office 365 portal ([https://portal.office.com](https://portal.office.com)) and sign in with the User 2 account name and password.</span></span>
    
3. <span data-ttu-id="4a160-134">登录后，系统会提示您设置帐户以获取详细信息。</span><span class="sxs-lookup"><span data-stu-id="4a160-134">After signing in, you are prompted to set up the account for more information.</span></span> <span data-ttu-id="4a160-135">单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="4a160-135">Click **Next**.</span></span>
    
4. <span data-ttu-id="4a160-136">在“其他安全性验证”\*\*\*\* 页上： </span><span class="sxs-lookup"><span data-stu-id="4a160-136">On the **Additional security verification** page:</span></span>
    
   - <span data-ttu-id="4a160-137">选择你所在的国家或地区。</span><span class="sxs-lookup"><span data-stu-id="4a160-137">Select your country or region.</span></span>
    
   - <span data-ttu-id="4a160-138">键入接收短信的智能手机的电话号码。</span><span class="sxs-lookup"><span data-stu-id="4a160-138">Type phone number of the smart phone that will receive text messages.</span></span>
    
   - <span data-ttu-id="4a160-139">在**方法**中，单击 "**通过短信向我发送代码**"。</span><span class="sxs-lookup"><span data-stu-id="4a160-139">In **Method**, click **Send me a code by text message**.</span></span>
    
5. <span data-ttu-id="4a160-140">单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="4a160-140">Click **Next**.</span></span>
    
6. <span data-ttu-id="4a160-141">输入智能手机收到的短信中的验证码，然后单击“验证”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4a160-141">Enter the verification code from the text message received on your smart phone, and then click **Verify**.</span></span>
    
7. <span data-ttu-id="4a160-142">在 "**步骤3：保留现有应用程序**" 页上，单击 "**完成**"。</span><span class="sxs-lookup"><span data-stu-id="4a160-142">On the **Step 3: Keep your existing applications** page, click **Done**.</span></span>
    
8. <span data-ttu-id="4a160-p104">如果这是你第一次使用 User 2 帐户登录，那么系统将提示你更改密码。键入原始密码和新密码两次，然后单击“更新密码并登录”\*\*\*\*。将新密码记录在安全位置。</span><span class="sxs-lookup"><span data-stu-id="4a160-p104">If this is the first time you signed in with the User 2 account, you are prompted to change the password. Type the original password and a new password twice, and then click **Update password and sign in**. Record the new password in a secure location.</span></span>
    
    <span data-ttu-id="4a160-146">您应在浏览器的 " **Microsoft Office 主页**" 选项卡上看到 "用户 2" 的 Office 门户。</span><span class="sxs-lookup"><span data-stu-id="4a160-146">You should see the Office portal for User 2 on the **Microsoft Office Home** tab of your browser.</span></span>

## <a name="phase-3-enable-and-test-multi-factor-authentication-with-a-conditional-access-policy"></a><span data-ttu-id="4a160-147">第3阶段：使用条件访问策略启用和测试多重身份验证</span><span class="sxs-lookup"><span data-stu-id="4a160-147">Phase 3: Enable and test multi-factor authentication with a conditional access policy</span></span>

<span data-ttu-id="4a160-148">*此阶段仅可用于 Microsoft 365 企业版测试环境。*</span><span class="sxs-lookup"><span data-stu-id="4a160-148">*This phase can only be used for a Microsoft 365 Enterprise test environment.*</span></span>

<span data-ttu-id="4a160-149">在此阶段中，将使用组和条件访问策略为用户3帐户启用多重身份验证。</span><span class="sxs-lookup"><span data-stu-id="4a160-149">In this phase you enable multi-factor authentication for the User 3 account using a group and a conditional access policy.</span></span>

<span data-ttu-id="4a160-150">接下来，创建一个名为 "MFAUsers" 的新组，并向其添加用户3帐户。</span><span class="sxs-lookup"><span data-stu-id="4a160-150">Next, create a new group named MFAUsers and add the User 3 account to it.</span></span>

1. <span data-ttu-id="4a160-151">在 " **Microsoft 365 管理中心**" 选项卡上，单击左侧导航栏中的 "**组**"，然后单击 "**组**"。</span><span class="sxs-lookup"><span data-stu-id="4a160-151">On the **Microsoft 365 admin center** tab, click **Groups** in the left navigation, and then click **Groups**.</span></span>
2. <span data-ttu-id="4a160-152">单击 "**添加组**"。</span><span class="sxs-lookup"><span data-stu-id="4a160-152">Click **Add a group**.</span></span>
3. <span data-ttu-id="4a160-153">在 "**选择组类型**" 窗格中，选择 "**安全性**"，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="4a160-153">In the **Choose a group type** pane, select **Security**, and then click **Next**.</span></span>
4. <span data-ttu-id="4a160-154">在 "**设置基础知识"** 窗格中，单击 "**创建组**"，然后单击 "**关闭**"。</span><span class="sxs-lookup"><span data-stu-id="4a160-154">In the **Set up the basics** pane, click **Create group**, and then click **Close**.</span></span>
5. <span data-ttu-id="4a160-155">在 "**查看并完成添加组**窗格" 中，键入**MFAUsers**，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="4a160-155">In the **Review and finish adding group** pane, type **MFAUsers**, and then click **Next**.</span></span>
6. <span data-ttu-id="4a160-156">在组列表中，单击 " **MFAUsers** " 组。</span><span class="sxs-lookup"><span data-stu-id="4a160-156">In the list of groups, click the **MFAUsers** group.</span></span>
7. <span data-ttu-id="4a160-157">在 " **MFAUsers** " 窗格中，单击 "**成员**"，然后单击 "**查看所有和管理成员**"。</span><span class="sxs-lookup"><span data-stu-id="4a160-157">In the **MFAUsers** pane, click **Members**, and then click **View all and manage members**.</span></span>
8. <span data-ttu-id="4a160-158">在 " **MFAUsers** " 窗格中，单击 "**添加成员**"，选择**用户 3**帐户，然后单击 "**保存" > 关闭 > "关闭**"。</span><span class="sxs-lookup"><span data-stu-id="4a160-158">In the **MFAUsers** pane, click **Add members**, select the **User 3** account, and then click **Save > Close > Close**.</span></span>

<span data-ttu-id="4a160-159">接下来，创建一个条件访问策略，以要求对 MFAUsers 组成员进行多重身份验证。</span><span class="sxs-lookup"><span data-stu-id="4a160-159">Next, create a conditional access policy to require multifactor authentication for members of the MFAUsers group.</span></span>

1. <span data-ttu-id="4a160-160">在浏览器的新选项卡中，转到 [https://portal.azure.com](https://portal.azure.com) 。</span><span class="sxs-lookup"><span data-stu-id="4a160-160">In a new tab of your browser, go to [https://portal.azure.com](https://portal.azure.com).</span></span>
2. <span data-ttu-id="4a160-161">单击 " **Azure Active Directory > Security > 条件访问**。</span><span class="sxs-lookup"><span data-stu-id="4a160-161">Click **Azure Active Directory > Security > Conditional Access**.</span></span>
3. <span data-ttu-id="4a160-162">在 "**条件访问–策略**" 窗格中，单击 "**新建策略**"。</span><span class="sxs-lookup"><span data-stu-id="4a160-162">In the **Conditional access – Policies** pane, click **New policy**.</span></span>
4. <span data-ttu-id="4a160-163">在 "**新建**" 窗格中，为 "**名称**" 中**的用户帐户键入 MFA** 。</span><span class="sxs-lookup"><span data-stu-id="4a160-163">In the **New** pane, type **MFA for user accounts** in **Name**.</span></span>
5. <span data-ttu-id="4a160-164">在 "**工作分配**" 部分，单击 "**用户和组**"。</span><span class="sxs-lookup"><span data-stu-id="4a160-164">In the **Assignments** section, click **Users and groups**.</span></span>
6. <span data-ttu-id="4a160-165">在 "**用户和组**" 窗格的 "**包含**" 选项卡上，单击 "选择用户和组" **> 用户和组**"。 >" 选择 "。</span><span class="sxs-lookup"><span data-stu-id="4a160-165">On the **Include** tab of the **Users and groups** pane, click **Select users and groups > Users and groups > Select**.</span></span>
7. <span data-ttu-id="4a160-166">在**选择**窗格中，单击 " **MFAUsers** " 组，然后单击 "**选择 > 完成**"。</span><span class="sxs-lookup"><span data-stu-id="4a160-166">In the **Select** pane, click the **MFAUsers** group, and then click **Select > Done**.</span></span>
8. <span data-ttu-id="4a160-167">在**新**窗格的 "**访问控制**" 部分，单击 "**授予**"。</span><span class="sxs-lookup"><span data-stu-id="4a160-167">In the **Access controls** section of the **New** pane, click **Grant**.</span></span>
9. <span data-ttu-id="4a160-168">在 "**授予**" 窗格中，单击 "**要求多重身份验证**"，然后单击 "**选择**"。</span><span class="sxs-lookup"><span data-stu-id="4a160-168">In the **Grant** pane, click **Require multi-factor authentication**, and then click **Select**.</span></span>
10. <span data-ttu-id="4a160-169">在 "**新建**" 窗格中，单击 **"** **启用策略**"，然后单击 "**创建**"。</span><span class="sxs-lookup"><span data-stu-id="4a160-169">In the **New** pane, click **On** for **Enable policy**, and then click **Create**.</span></span>
11. <span data-ttu-id="4a160-170">关闭 " **Azure 门户**" 和 " **Microsoft 365 管理中心**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="4a160-170">Close the **Azure portal** and **Microsoft 365 admin center** tabs.</span></span>

<span data-ttu-id="4a160-171">若要测试此策略，请注销并使用用户3帐户登录。</span><span class="sxs-lookup"><span data-stu-id="4a160-171">To test this policy, sign out and sign in with the User 3 account.</span></span> <span data-ttu-id="4a160-172">系统会提示您配置 MFA。</span><span class="sxs-lookup"><span data-stu-id="4a160-172">You should be prompted to configure MFA.</span></span> <span data-ttu-id="4a160-173">这说明正在应用 MFAUsers 策略。</span><span class="sxs-lookup"><span data-stu-id="4a160-173">This demonstrates that the MFAUsers policy is being applied.</span></span>

<span data-ttu-id="4a160-174">若要了解如何在生产环境中部署多重身份验证的信息和链接，请参阅 Identity 阶段中的[设置多重身份验证](identity-secure-user-sign-ins.md#identity-mfa)步骤。</span><span class="sxs-lookup"><span data-stu-id="4a160-174">See the [Set up multi-factor authentication](identity-secure-user-sign-ins.md#identity-mfa) step in the Identity phase for information and links to deploy multi-factor authentication in production.</span></span>
    
## <a name="next-step"></a><span data-ttu-id="4a160-175">后续步骤</span><span class="sxs-lookup"><span data-stu-id="4a160-175">Next step</span></span>

<span data-ttu-id="4a160-176">在测试环境中探索其他[标识](m365-enterprise-test-lab-guides.md#identity)特性和功能。</span><span class="sxs-lookup"><span data-stu-id="4a160-176">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="4a160-177">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4a160-177">See also</span></span>

[<span data-ttu-id="4a160-178">阶段 2：标识</span><span class="sxs-lookup"><span data-stu-id="4a160-178">Phase 2: Identity</span></span>](identity-infrastructure.md)

[<span data-ttu-id="4a160-179">Microsoft 365 企业版测试实验室指南</span><span class="sxs-lookup"><span data-stu-id="4a160-179">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="4a160-180">Microsoft 365 企业版部署</span><span class="sxs-lookup"><span data-stu-id="4a160-180">Microsoft 365 Enterprise deployment</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="4a160-181">Microsoft 365 企业版文档</span><span class="sxs-lookup"><span data-stu-id="4a160-181">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
