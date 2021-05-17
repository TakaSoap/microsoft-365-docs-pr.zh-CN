---
title: Microsoft 365企业测试环境的多重身份验证
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
description: 使用发送到适用于企业测试环境的 Microsoft 365智能手机配置多重身份验证。
ms.openlocfilehash: aeb8940a9499909b8c568d1230f9aa45aee07b3d
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50923752"
---
# <a name="multi-factor-authentication-for-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="c53fb-103">适用于企业测试环境Microsoft 365多重身份验证</span><span class="sxs-lookup"><span data-stu-id="c53fb-103">Multi-factor authentication for your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="c53fb-104">*本测试实验室指南可用于企业Microsoft 365和Office 365 企业版环境。*</span><span class="sxs-lookup"><span data-stu-id="c53fb-104">*This Test Lab Guide can be used for both Microsoft 365 for enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="c53fb-105">若要为登录 Microsoft 365 或任何将 Azure AD 租户用于订阅的服务或应用程序提供一个额外的安全级别，可以启用 Azure AD 多重身份验证，该身份验证不仅需要用户名和密码来验证帐户。</span><span class="sxs-lookup"><span data-stu-id="c53fb-105">For an additional level of security for signing in to Microsoft 365 or any service or application that uses the Azure AD tenant for your subscription, you can enable Azure AD multi-factor authentication, which requires more than just a username and password to verify an account.</span></span>

<span data-ttu-id="c53fb-106">使用多重身份验证，用户必须确认电话呼叫、键入短信中发送的验证码，或在正确输入密码后验证智能手机上的应用是否进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="c53fb-106">With multi-factor authentication, users are required to acknowledge a phone call, type a verification code sent in a text message, or verify the authentication with an app on their smart phones after correctly entering their passwords.</span></span> <span data-ttu-id="c53fb-107">只有在满足第二个身份验证因素后，他们才能登录。</span><span class="sxs-lookup"><span data-stu-id="c53fb-107">They can sign in only after this second authentication factor is satisfied.</span></span>
  
<span data-ttu-id="c53fb-108">本文介绍如何为特定用户帐户启用和测试基于短信的身份验证。</span><span class="sxs-lookup"><span data-stu-id="c53fb-108">This article describes how to enable and test text message-based authentication for a specific user account.</span></span>
  
<span data-ttu-id="c53fb-109">在企业测试环境中为 Microsoft 365设置多重身份验证包括两个阶段和第三个可选阶段：</span><span class="sxs-lookup"><span data-stu-id="c53fb-109">Setting up multi-factor authentication for an account in your Microsoft 365 for enterprise test environment involves two phases and a third optional phase:</span></span>
- [<span data-ttu-id="c53fb-110">第 1 阶段：构建Microsoft 365测试环境</span><span class="sxs-lookup"><span data-stu-id="c53fb-110">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [<span data-ttu-id="c53fb-111">阶段 2：启用和测试 User 2 帐户的多重身份验证</span><span class="sxs-lookup"><span data-stu-id="c53fb-111">Phase 2: Enable and test multi-factor authentication for the User 2 account</span></span>](#phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account)
- [<span data-ttu-id="c53fb-112">阶段 3：使用条件访问策略启用和测试多重身份验证</span><span class="sxs-lookup"><span data-stu-id="c53fb-112">Phase 3: Enable and test multi-factor authentication with a conditional access policy</span></span>](#phase-3-enable-and-test-multi-factor-authentication-with-a-conditional-access-policy)

![Microsoft 云测试实验室指南](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="c53fb-114">有关企业测试实验室指南堆栈中Microsoft 365文章的直观映射，请转到 Microsoft 365[企业测试实验室指南堆栈](../downloads/Microsoft365EnterpriseTLGStack.pdf)。</span><span class="sxs-lookup"><span data-stu-id="c53fb-114">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="c53fb-115">第 1 阶段：构建Microsoft 365测试环境</span><span class="sxs-lookup"><span data-stu-id="c53fb-115">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="c53fb-116">如果你只想以最低要求的轻型方式测试多重身份验证，请按照轻型基本配置 [中的说明进行操作](lightweight-base-configuration-microsoft-365-enterprise.md)。</span><span class="sxs-lookup"><span data-stu-id="c53fb-116">If you just want to test multi-factor authentication in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="c53fb-117">如果要在模拟的企业中测试多重身份验证，请按照传递身份验证 [中的说明操作](pass-through-auth-m365-ent-test-environment.md)。</span><span class="sxs-lookup"><span data-stu-id="c53fb-117">If you want to test multi-factor authentication in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="c53fb-118">测试多重身份验证不需要模拟的企业测试环境，该环境包括连接到 Internet 的模拟 Intranet 和 Active Directory 域服务 (AD DS) 同步。</span><span class="sxs-lookup"><span data-stu-id="c53fb-118">Testing multi-factor authentication does not require the simulated enterprise test environment, which includes a simulated intranet connected to the internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="c53fb-119">它在此处作为一个选项提供，以便你可以测试多重身份验证，并在代表典型组织的环境中对其进行试验。</span><span class="sxs-lookup"><span data-stu-id="c53fb-119">It is provided here as an option so that you can test multi-factor authentication and experiment with it in an environment that represents a typical organization.</span></span>
  
## <a name="phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account"></a><span data-ttu-id="c53fb-120">阶段 2：启用和测试 User 2 帐户的多重身份验证</span><span class="sxs-lookup"><span data-stu-id="c53fb-120">Phase 2: Enable and test multi-factor authentication for the User 2 account</span></span>

<span data-ttu-id="c53fb-121">通过以下步骤为 User 2 帐户启用多重身份验证：</span><span class="sxs-lookup"><span data-stu-id="c53fb-121">Enable multi-factor authentication for the User 2 account with these steps:</span></span>
  
1. <span data-ttu-id="c53fb-122">打开浏览器的单独专用实例，转到 Microsoft 365 管理中心 () ，然后使用全局管理员 [https://portal.microsoft.com](https://portal.microsoft.com) 帐户登录。</span><span class="sxs-lookup"><span data-stu-id="c53fb-122">Open a separate, private instance of your browser, go to the Microsoft 365 admin center ([https://portal.microsoft.com](https://portal.microsoft.com)), and then sign in with your global administrator account.</span></span>
    
2. <span data-ttu-id="c53fb-123">在左侧导航栏中，选择"**用户**  >  **""活动用户"。**</span><span class="sxs-lookup"><span data-stu-id="c53fb-123">In the left navigation, select **Users** > **Active users**.</span></span>
    
3. <span data-ttu-id="c53fb-124">在"活动用户"窗格中，选择 **"多重身份验证"。**</span><span class="sxs-lookup"><span data-stu-id="c53fb-124">In the Active users pane, select **Multi-factor authentication**.</span></span>
    
4. <span data-ttu-id="c53fb-125">在列表中，选择 **"用户 2"** 帐户。</span><span class="sxs-lookup"><span data-stu-id="c53fb-125">In the list, select the **User 2** account.</span></span>
    
5. <span data-ttu-id="c53fb-126">在"**用户 2"** 部分中的"**快速步骤"下**，选择"**启用"。**</span><span class="sxs-lookup"><span data-stu-id="c53fb-126">In the **User 2** section, under **Quick steps**, select **Enable**.</span></span>
    
6. <span data-ttu-id="c53fb-127">在 **"关于启用多重** 身份验证"对话框中，选择"**启用多重身份验证"。**</span><span class="sxs-lookup"><span data-stu-id="c53fb-127">In the **About enabling multi-factor auth** dialog box, select **Enable multi-factor auth**.</span></span>
    
7. <span data-ttu-id="c53fb-128">在"**更新成功"** 对话框中，选择"关闭 **"。**</span><span class="sxs-lookup"><span data-stu-id="c53fb-128">In the **Updates successful** dialog box, select **Close**.</span></span>
    
8. <span data-ttu-id="c53fb-129">在 **"Microsoft 365** 中心"选项卡上，选择右上角的用户帐户图标，然后选择"**注销"。**</span><span class="sxs-lookup"><span data-stu-id="c53fb-129">On the **Microsoft 365 admin center** tab, select the user account icon in the upper right, and then select **Sign out**.</span></span>
    
9. <span data-ttu-id="c53fb-130">关闭浏览器实例。</span><span class="sxs-lookup"><span data-stu-id="c53fb-130">Close your browser instance.</span></span>
   
<span data-ttu-id="c53fb-131">完成 User 2 帐户的配置，通过以下步骤，使用短信对其进行验证和测试：</span><span class="sxs-lookup"><span data-stu-id="c53fb-131">Complete the configuration for the User 2 account to use a text message for validation and test it with these steps:</span></span>
  
1. <span data-ttu-id="c53fb-132">打开浏览器的新专用实例。</span><span class="sxs-lookup"><span data-stu-id="c53fb-132">Open a new, private instance of your browser.</span></span>
    
2. <span data-ttu-id="c53fb-133">转到管理[Microsoft 365](https://admin.microsoft.com)中心，然后使用 User 2 帐户名称和密码登录。</span><span class="sxs-lookup"><span data-stu-id="c53fb-133">Go to the [Microsoft 365 admin center](https://admin.microsoft.com) and sign in with the User 2 account name and password.</span></span>
    
3. <span data-ttu-id="c53fb-134">登录后，系统将提示你设置帐户，了解详细信息。</span><span class="sxs-lookup"><span data-stu-id="c53fb-134">After signing in, you are prompted to set up the account for more information.</span></span> <span data-ttu-id="c53fb-135">选择“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="c53fb-135">Select **Next**.</span></span>
    
4. <span data-ttu-id="c53fb-136">在“其他安全性验证”页上： </span><span class="sxs-lookup"><span data-stu-id="c53fb-136">On the **Additional security verification** page:</span></span>
    
   - <span data-ttu-id="c53fb-137">选择你所在的国家或地区。</span><span class="sxs-lookup"><span data-stu-id="c53fb-137">Select your country or region.</span></span>
    
   - <span data-ttu-id="c53fb-138">输入将接收短信的智能手机的电话号码。</span><span class="sxs-lookup"><span data-stu-id="c53fb-138">Enter the phone number of the smart phone that will receive text messages.</span></span>
    
   - <span data-ttu-id="c53fb-139">在 **"方法**"中 **，选择"通过短信向我发送代码"。**</span><span class="sxs-lookup"><span data-stu-id="c53fb-139">In **Method**, select **Send me a code by text message**.</span></span>
    
5. <span data-ttu-id="c53fb-140">选择“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="c53fb-140">Select **Next**.</span></span>
    
6. <span data-ttu-id="c53fb-141">输入智能手机上收到的短信中的验证码，然后选择"验证 **"。**</span><span class="sxs-lookup"><span data-stu-id="c53fb-141">Enter the verification code from the text message received on your smart phone, and then select **Verify**.</span></span>
    
7. <span data-ttu-id="c53fb-142">在"**步骤 3： 保留现有应用程序"页上**，选择"完成 **"。**</span><span class="sxs-lookup"><span data-stu-id="c53fb-142">On the **Step 3: Keep your existing applications** page, select **Done**.</span></span>
    
8. <span data-ttu-id="c53fb-143">如果这是你第一次使用 User 2 帐户登录，那么系统将提示你更改密码。</span><span class="sxs-lookup"><span data-stu-id="c53fb-143">If this is the first time you signed in with the User 2 account, you are prompted to change the password.</span></span> <span data-ttu-id="c53fb-144">输入原始密码和新密码两次，然后选择更新 **密码并登录**。</span><span class="sxs-lookup"><span data-stu-id="c53fb-144">Enter the original password and a new password twice, and then select **Update password and sign in**.</span></span> <span data-ttu-id="c53fb-145">将新密码记录在安全位置。</span><span class="sxs-lookup"><span data-stu-id="c53fb-145">Record the new password in a secure location.</span></span>
    
    <span data-ttu-id="c53fb-146">你应该在浏览器Office主页"选项卡上看到用户 2 Microsoft Office门户。</span><span class="sxs-lookup"><span data-stu-id="c53fb-146">You should see the Office portal for User 2 on the **Microsoft Office Home** tab of your browser.</span></span>

## <a name="phase-3-enable-and-test-multi-factor-authentication-with-a-conditional-access-policy"></a><span data-ttu-id="c53fb-147">阶段 3：使用条件访问策略启用和测试多重身份验证</span><span class="sxs-lookup"><span data-stu-id="c53fb-147">Phase 3: Enable and test multi-factor authentication with a conditional access policy</span></span>

<span data-ttu-id="c53fb-148">*此阶段只能用于企业Microsoft 365测试环境。*</span><span class="sxs-lookup"><span data-stu-id="c53fb-148">*This phase can only be used for a Microsoft 365 for enterprise test environment.*</span></span>

<span data-ttu-id="c53fb-149">在此阶段，使用组和条件访问策略为用户 3 帐户启用多重身份验证。</span><span class="sxs-lookup"><span data-stu-id="c53fb-149">In this phase, you enable multi-factor authentication for the User 3 account using a group and a conditional access policy.</span></span>

<span data-ttu-id="c53fb-150">接下来，创建一个名为 MFAUsers 的新组，并添加 User 3 帐户。</span><span class="sxs-lookup"><span data-stu-id="c53fb-150">Next, create a new group named MFAUsers and add the User 3 account to it.</span></span>

1. <span data-ttu-id="c53fb-151">在 **"Microsoft 365中心"** 选项卡上，选择左侧导航中的"组"，然后选择"组 **"。**</span><span class="sxs-lookup"><span data-stu-id="c53fb-151">On the **Microsoft 365 admin center** tab, select **Groups** in the left navigation, and then select **Groups**.</span></span>
2. <span data-ttu-id="c53fb-152">选择 **"添加组"。**</span><span class="sxs-lookup"><span data-stu-id="c53fb-152">Select **Add a group**.</span></span>
3. <span data-ttu-id="c53fb-153">在"**选择组类型"窗格中**，选择"**安全性"，** 然后选择"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="c53fb-153">In the **Choose a group type** pane, select **Security**, and then select **Next**.</span></span>
4. <span data-ttu-id="c53fb-154">在"**设置基础知识"窗格中**，选择"**创建组**"，然后选择"关闭 **"。**</span><span class="sxs-lookup"><span data-stu-id="c53fb-154">In the **Set up the basics** pane, select **Create group**, and then select **Close**.</span></span>
5. <span data-ttu-id="c53fb-155">在"**查看并完成添加组"窗格中**，输入 **"MFAUsers"，** 然后选择"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="c53fb-155">In the **Review and finish adding group** pane, enter **MFAUsers**, and then select **Next**.</span></span>
6. <span data-ttu-id="c53fb-156">在组列表中，选择 **MFAUsers** 组。</span><span class="sxs-lookup"><span data-stu-id="c53fb-156">In the list of groups, select the **MFAUsers** group.</span></span>
7. <span data-ttu-id="c53fb-157">在 **"MFAUsers"** 窗格中，选择"**成员"，** 然后选择"**查看所有和管理成员"。**</span><span class="sxs-lookup"><span data-stu-id="c53fb-157">In the **MFAUsers** pane, select **Members**, and then select **View all and manage members**.</span></span>
8. <span data-ttu-id="c53fb-158">在 **"MFAUsers"** 窗格中，选择"**添加** 成员"，选择 **"用户 3"** 帐户，然后选择"**保存**  >  **关闭**  >  **关闭"。**</span><span class="sxs-lookup"><span data-stu-id="c53fb-158">In the **MFAUsers** pane, select **Add members**, select the **User 3** account, and then select **Save** > **Close** > **Close**.</span></span>

<span data-ttu-id="c53fb-159">接下来，创建条件访问策略，要求 MFAUsers 组的成员进行多重身份验证。</span><span class="sxs-lookup"><span data-stu-id="c53fb-159">Next, create a conditional access policy to require multifactor authentication for members of the MFAUsers group.</span></span>

1. <span data-ttu-id="c53fb-160">在浏览器的新选项卡中，转到 [https://portal.azure.com](https://portal.azure.com) 。</span><span class="sxs-lookup"><span data-stu-id="c53fb-160">In a new tab of your browser, go to [https://portal.azure.com](https://portal.azure.com).</span></span>
2. <span data-ttu-id="c53fb-161">选择 **Azure Active Directory**  >  **安全**  >  **条件访问"。**</span><span class="sxs-lookup"><span data-stu-id="c53fb-161">Select **Azure Active Directory** > **Security** > **Conditional Access**.</span></span>
3. <span data-ttu-id="c53fb-162">在"**条件访问 – 策略"** 窗格中，选择"**新建策略"。**</span><span class="sxs-lookup"><span data-stu-id="c53fb-162">In the **Conditional access – Policies** pane, select **New policy**.</span></span>
4. <span data-ttu-id="c53fb-163">在"**新建**"窗格中，在"名称"**框中输入用户帐户的 MFA。** </span><span class="sxs-lookup"><span data-stu-id="c53fb-163">In the **New** pane, enter **MFA for user accounts** in the **Name** box.</span></span>
5. <span data-ttu-id="c53fb-164">在"**分配"** 部分，选择"**用户和组"。**</span><span class="sxs-lookup"><span data-stu-id="c53fb-164">In the **Assignments** section, select **Users and groups**.</span></span>
6. <span data-ttu-id="c53fb-165">在"**用户和** 组"**窗格** 的"包含"选项卡上，选择 **"选择用户和组**  >  **用户和组**  >  **"选择**。</span><span class="sxs-lookup"><span data-stu-id="c53fb-165">On the **Include** tab of the **Users and groups** pane, select **Select users and groups** > **Users and groups** > **Select**.</span></span>
7. <span data-ttu-id="c53fb-166">在"**选择**"窗格中，选择 **"MFAUsers"** 组，然后选择"**选择完成**  >  **"。**</span><span class="sxs-lookup"><span data-stu-id="c53fb-166">In the **Select** pane, select the **MFAUsers** group, and then select **Select** > **Done**.</span></span>
8. <span data-ttu-id="c53fb-167">在"**新建"窗格** 的"访问控制"**部分**，选择"授予 **"。**</span><span class="sxs-lookup"><span data-stu-id="c53fb-167">In the **Access controls** section of the **New** pane, select **Grant**.</span></span>
9. <span data-ttu-id="c53fb-168">在"**授予"** 窗格中，选择 **"需要多重身份验证"，** 然后选择"选择 **"。**</span><span class="sxs-lookup"><span data-stu-id="c53fb-168">In the **Grant** pane, select **Require multi-factor authentication**, and then select **Select**.</span></span>
10. <span data-ttu-id="c53fb-169">在"**新建"** 窗格中，为"启用策略"选择 **"打开\*\*\*\*"，** 然后选择"创建 **"。**</span><span class="sxs-lookup"><span data-stu-id="c53fb-169">In the **New** pane, select **On** for **Enable policy**, and then select **Create**.</span></span>
11. <span data-ttu-id="c53fb-170">关闭 **Azure 门户，Microsoft 365\*\*\*\*管理中心** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="c53fb-170">Close the **Azure portal** and **Microsoft 365 admin center** tabs.</span></span>

<span data-ttu-id="c53fb-171">若要测试此策略，请注销，然后使用 User 3 帐户登录。</span><span class="sxs-lookup"><span data-stu-id="c53fb-171">To test this policy, sign out and sign in with the User 3 account.</span></span> <span data-ttu-id="c53fb-172">系统将提示你配置 MFA。</span><span class="sxs-lookup"><span data-stu-id="c53fb-172">You should be prompted to configure MFA.</span></span> <span data-ttu-id="c53fb-173">这演示了正在应用 MFAUsers 策略。</span><span class="sxs-lookup"><span data-stu-id="c53fb-173">This demonstrates that the MFAUsers policy is being applied.</span></span>

## <a name="next-step"></a><span data-ttu-id="c53fb-174">后续步骤</span><span class="sxs-lookup"><span data-stu-id="c53fb-174">Next step</span></span>

<span data-ttu-id="c53fb-175">在测试环境中探索其他[标识](m365-enterprise-test-lab-guides.md#identity)特性和功能。</span><span class="sxs-lookup"><span data-stu-id="c53fb-175">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="c53fb-176">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c53fb-176">See also</span></span>

[<span data-ttu-id="c53fb-177">标识路线图</span><span class="sxs-lookup"><span data-stu-id="c53fb-177">Identity roadmap</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="c53fb-178">Microsoft 365 企业版测试实验室指南</span><span class="sxs-lookup"><span data-stu-id="c53fb-178">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="c53fb-179">Microsoft 365 企业版概述</span><span class="sxs-lookup"><span data-stu-id="c53fb-179">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="c53fb-180">适用于企业的 Microsoft 365 文档</span><span class="sxs-lookup"><span data-stu-id="c53fb-180">Microsoft 365 for enterprise documentation</span></span>](/microsoft-365-enterprise/)