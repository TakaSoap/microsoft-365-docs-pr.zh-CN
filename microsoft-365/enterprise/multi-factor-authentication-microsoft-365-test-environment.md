---
title: 适用于企业测试环境的 Microsoft 365 多因素身份验证
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
ms.openlocfilehash: f41fe7ad933f85c4b44a1e90529a998651412191
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487136"
---
# <a name="multi-factor-authentication-for-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="f6df9-103">适用于 Microsoft 365 企业版测试环境的多重身份验证</span><span class="sxs-lookup"><span data-stu-id="f6df9-103">Multi-factor authentication for your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="f6df9-104">*此测试实验室指南可用于适用于企业和 Office 365 企业测试环境的 Microsoft 365。*</span><span class="sxs-lookup"><span data-stu-id="f6df9-104">*This Test Lab Guide can be used for both Microsoft 365 for enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="f6df9-105">若要使用其他级别的安全来登录 Microsoft 365 或使用 Azure AD 租户订阅订阅的任何服务或应用程序，您可以启用 Azure 多重身份验证，它需要的用户和密码不只需要用户名和密码即可验证帐户。</span><span class="sxs-lookup"><span data-stu-id="f6df9-105">For an additional level of security for signing in to Microsoft 365 or any service or application that uses the Azure AD tenant for your subscription, you can enable Azure multi-factor authentication, which requires more than just a username and password to verify an account.</span></span>

<span data-ttu-id="f6df9-106">使用多重身份验证，用户需要确认电话呼叫，在短信中键入验证代码，或在正确输入密码后验证智能手机上的应用程序的身份验证。</span><span class="sxs-lookup"><span data-stu-id="f6df9-106">With multi-factor authentication, users are required to acknowledge a phone call, type a verification code sent in a text message, or verify the authentication with an app on their smart phones after correctly entering their passwords.</span></span> <span data-ttu-id="f6df9-107">只有在满足第二个身份验证因素之后，他们才能登录。</span><span class="sxs-lookup"><span data-stu-id="f6df9-107">They can sign in only after this second authentication factor is satisfied.</span></span>
  
<span data-ttu-id="f6df9-108">本文介绍如何为特定用户帐户启用和测试基于短信的身份验证。</span><span class="sxs-lookup"><span data-stu-id="f6df9-108">This article describes how to enable and test text message-based authentication for a specific user account.</span></span>
  
<span data-ttu-id="f6df9-109">为 Microsoft 365 for 企业版测试环境中的帐户设置多重身份验证包括两个阶段和第三个可选阶段：</span><span class="sxs-lookup"><span data-stu-id="f6df9-109">Setting up multi-factor authentication for an account in your Microsoft 365 for enterprise test environment involves two phases and a third optional phase:</span></span>
- [<span data-ttu-id="f6df9-110">第1阶段：构建您的 Microsoft 365 企业版测试环境</span><span class="sxs-lookup"><span data-stu-id="f6df9-110">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [<span data-ttu-id="f6df9-111">阶段 2：启用和测试 User 2 帐户的多重身份验证</span><span class="sxs-lookup"><span data-stu-id="f6df9-111">Phase 2: Enable and test multi-factor authentication for the User 2 account</span></span>](#phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account)
- [<span data-ttu-id="f6df9-112">第3阶段：使用条件访问策略启用和测试多重身份验证</span><span class="sxs-lookup"><span data-stu-id="f6df9-112">Phase 3: Enable and test multi-factor authentication with a conditional access policy</span></span>](#phase-3-enable-and-test-multi-factor-authentication-with-a-conditional-access-policy)

![Microsoft 云测试实验室指南](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="f6df9-114">若要了解到 Microsoft 365 for 企业测试实验室指南堆栈中的所有文章的可视化地图，请转到 [microsoft 365 for Enterprise Test Lab Guide stack](../downloads/Microsoft365EnterpriseTLGStack.pdf)。</span><span class="sxs-lookup"><span data-stu-id="f6df9-114">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="f6df9-115">第1阶段：构建您的 Microsoft 365 企业版测试环境</span><span class="sxs-lookup"><span data-stu-id="f6df9-115">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="f6df9-116">如果只想使用最低要求以轻型方式测试多重身份验证，请按照 [轻型基本配置](lightweight-base-configuration-microsoft-365-enterprise.md)中的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="f6df9-116">If you just want to test multi-factor authentication in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="f6df9-117">如果要在模拟的企业中测试多重身份验证，请按照 [传递身份验证](pass-through-auth-m365-ent-test-environment.md)中的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="f6df9-117">If you want to test multi-factor authentication in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="f6df9-118">测试多重身份验证不需要模拟企业测试环境，其中包括连接到 internet 的模拟 intranet 和 Active Directory 域服务 (AD DS) 林的目录同步。</span><span class="sxs-lookup"><span data-stu-id="f6df9-118">Testing multi-factor authentication does not require the simulated enterprise test environment, which includes a simulated intranet connected to the internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="f6df9-119">它在此处作为一个选项提供，以便你可以测试多重身份验证，并在代表典型组织的环境中对其进行试验。</span><span class="sxs-lookup"><span data-stu-id="f6df9-119">It is provided here as an option so that you can test multi-factor authentication and experiment with it in an environment that represents a typical organization.</span></span>
  
## <a name="phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account"></a><span data-ttu-id="f6df9-120">阶段 2：启用和测试 User 2 帐户的多重身份验证</span><span class="sxs-lookup"><span data-stu-id="f6df9-120">Phase 2: Enable and test multi-factor authentication for the User 2 account</span></span>

<span data-ttu-id="f6df9-121">通过以下步骤为 User 2 帐户启用多重身份验证：</span><span class="sxs-lookup"><span data-stu-id="f6df9-121">Enable multi-factor authentication for the User 2 account with these steps:</span></span>
  
1. <span data-ttu-id="f6df9-122">打开浏览器的单独私有实例，转到 Microsoft 365 管理中心 ([https://portal.microsoft.com](https://portal.microsoft.com)) ，然后使用全局管理员帐户登录。</span><span class="sxs-lookup"><span data-stu-id="f6df9-122">Open a separate, private instance of your browser, go to the Microsoft 365 admin center ([https://portal.microsoft.com](https://portal.microsoft.com)), and then sign in with your global administrator account.</span></span>
    
2. <span data-ttu-id="f6df9-123">在左侧导航栏中，选择 "**用户**  >  **活动用户**"。</span><span class="sxs-lookup"><span data-stu-id="f6df9-123">In the left navigation, select **Users** > **Active users**.</span></span>
    
3. <span data-ttu-id="f6df9-124">在 "活动用户" 窗格中，选择 " **多因素身份验证**"。</span><span class="sxs-lookup"><span data-stu-id="f6df9-124">In the Active users pane, select **Multi-factor authentication**.</span></span>
    
4. <span data-ttu-id="f6df9-125">在列表中，选择 " **用户 2** " 帐户。</span><span class="sxs-lookup"><span data-stu-id="f6df9-125">In the list, select the **User 2** account.</span></span>
    
5. <span data-ttu-id="f6df9-126">在 " **用户 2** " 部分的 " **快速步骤**" 下，选择 " **启用**"。</span><span class="sxs-lookup"><span data-stu-id="f6df9-126">In the **User 2** section, under **Quick steps**, select **Enable**.</span></span>
    
6. <span data-ttu-id="f6df9-127">在 " **关于启用多重身份验证** " 对话框中，选择 " **启用多重身份验证**"。</span><span class="sxs-lookup"><span data-stu-id="f6df9-127">In the **About enabling multi-factor auth** dialog box, select **Enable multi-factor auth**.</span></span>
    
7. <span data-ttu-id="f6df9-128">在 " **更新成功** " 对话框中，选择 " **关闭**"。</span><span class="sxs-lookup"><span data-stu-id="f6df9-128">In the **Updates successful** dialog box, select **Close**.</span></span>
    
8. <span data-ttu-id="f6df9-129">在 " **Microsoft 365 管理中心**" 选项卡上，选择右上角的 "用户帐户" 图标，然后选择 **"注销"。**</span><span class="sxs-lookup"><span data-stu-id="f6df9-129">On the **Microsoft 365 admin center** tab, select the user account icon in the upper right, and then select **Sign out**.</span></span>
    
9. <span data-ttu-id="f6df9-130">关闭浏览器实例。</span><span class="sxs-lookup"><span data-stu-id="f6df9-130">Close your browser instance.</span></span>
   
<span data-ttu-id="f6df9-131">完成 User 2 帐户的配置，通过以下步骤，使用短信对其进行验证和测试：</span><span class="sxs-lookup"><span data-stu-id="f6df9-131">Complete the configuration for the User 2 account to use a text message for validation and test it with these steps:</span></span>
  
1. <span data-ttu-id="f6df9-132">打开浏览器的新的私有实例。</span><span class="sxs-lookup"><span data-stu-id="f6df9-132">Open a new, private instance of your browser.</span></span>
    
2. <span data-ttu-id="f6df9-133">请转到 [Microsoft 365 管理中心](https://admin.microsoft.com) 并使用用户2帐户名称和密码登录。</span><span class="sxs-lookup"><span data-stu-id="f6df9-133">Go to the [Microsoft 365 admin center](https://admin.microsoft.com) and sign in with the User 2 account name and password.</span></span>
    
3. <span data-ttu-id="f6df9-134">登录后，系统会提示您设置帐户以获取详细信息。</span><span class="sxs-lookup"><span data-stu-id="f6df9-134">After signing in, you are prompted to set up the account for more information.</span></span> <span data-ttu-id="f6df9-135">选择“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="f6df9-135">Select **Next**.</span></span>
    
4. <span data-ttu-id="f6df9-136">在“其他安全性验证”\*\*\*\* 页上： </span><span class="sxs-lookup"><span data-stu-id="f6df9-136">On the **Additional security verification** page:</span></span>
    
   - <span data-ttu-id="f6df9-137">选择你所在的国家或地区。</span><span class="sxs-lookup"><span data-stu-id="f6df9-137">Select your country or region.</span></span>
    
   - <span data-ttu-id="f6df9-138">输入将接收短信的智能手机的电话号码。</span><span class="sxs-lookup"><span data-stu-id="f6df9-138">Enter the phone number of the smart phone that will receive text messages.</span></span>
    
   - <span data-ttu-id="f6df9-139">在 " **方法**" 中，选择 " **通过短信向我发送代码**"。</span><span class="sxs-lookup"><span data-stu-id="f6df9-139">In **Method**, select **Send me a code by text message**.</span></span>
    
5. <span data-ttu-id="f6df9-140">选择“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="f6df9-140">Select **Next**.</span></span>
    
6. <span data-ttu-id="f6df9-141">输入智能手机上收到的短信中的验证码，然后选择 " **验证**"。</span><span class="sxs-lookup"><span data-stu-id="f6df9-141">Enter the verification code from the text message received on your smart phone, and then select **Verify**.</span></span>
    
7. <span data-ttu-id="f6df9-142">在 " **步骤3：保留现有应用程序** " 页上，选择 " **完成**"。</span><span class="sxs-lookup"><span data-stu-id="f6df9-142">On the **Step 3: Keep your existing applications** page, select **Done**.</span></span>
    
8. <span data-ttu-id="f6df9-143">如果这是你第一次使用 User 2 帐户登录，那么系统将提示你更改密码。</span><span class="sxs-lookup"><span data-stu-id="f6df9-143">If this is the first time you signed in with the User 2 account, you are prompted to change the password.</span></span> <span data-ttu-id="f6df9-144">输入原始密码和新密码两次，然后选择 " **更新密码" 和 "登录"**。</span><span class="sxs-lookup"><span data-stu-id="f6df9-144">Enter the original password and a new password twice, and then select **Update password and sign in**.</span></span> <span data-ttu-id="f6df9-145">将新密码记录在安全位置。</span><span class="sxs-lookup"><span data-stu-id="f6df9-145">Record the new password in a secure location.</span></span>
    
    <span data-ttu-id="f6df9-146">您应在浏览器的 " **Microsoft Office 主页** " 选项卡上看到 "用户 2" 的 Office 门户。</span><span class="sxs-lookup"><span data-stu-id="f6df9-146">You should see the Office portal for User 2 on the **Microsoft Office Home** tab of your browser.</span></span>

## <a name="phase-3-enable-and-test-multi-factor-authentication-with-a-conditional-access-policy"></a><span data-ttu-id="f6df9-147">第3阶段：使用条件访问策略启用和测试多重身份验证</span><span class="sxs-lookup"><span data-stu-id="f6df9-147">Phase 3: Enable and test multi-factor authentication with a conditional access policy</span></span>

<span data-ttu-id="f6df9-148">*此阶段仅可用于适用于企业测试环境的 Microsoft 365。*</span><span class="sxs-lookup"><span data-stu-id="f6df9-148">*This phase can only be used for a Microsoft 365 for enterprise test environment.*</span></span>

<span data-ttu-id="f6df9-149">在此阶段中，将使用组和条件访问策略为用户3帐户启用多重身份验证。</span><span class="sxs-lookup"><span data-stu-id="f6df9-149">In this phase, you enable multi-factor authentication for the User 3 account using a group and a conditional access policy.</span></span>

<span data-ttu-id="f6df9-150">接下来，创建一个名为 "MFAUsers" 的新组，并向其添加用户3帐户。</span><span class="sxs-lookup"><span data-stu-id="f6df9-150">Next, create a new group named MFAUsers and add the User 3 account to it.</span></span>

1. <span data-ttu-id="f6df9-151">在 " **Microsoft 365 管理中心** " 选项卡上，选择左侧导航栏中的 " **组** "，然后选择 " **组**"。</span><span class="sxs-lookup"><span data-stu-id="f6df9-151">On the **Microsoft 365 admin center** tab, select **Groups** in the left navigation, and then select **Groups**.</span></span>
2. <span data-ttu-id="f6df9-152">选择 " **添加组**"。</span><span class="sxs-lookup"><span data-stu-id="f6df9-152">Select **Add a group**.</span></span>
3. <span data-ttu-id="f6df9-153">在 " **选择组类型** " 窗格中，选择 " **安全性**"，然后选择 " **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="f6df9-153">In the **Choose a group type** pane, select **Security**, and then select **Next**.</span></span>
4. <span data-ttu-id="f6df9-154">在 " **设置基础知识"** 窗格中，选择 " **创建组**"，然后选择 " **关闭**"。</span><span class="sxs-lookup"><span data-stu-id="f6df9-154">In the **Set up the basics** pane, select **Create group**, and then select **Close**.</span></span>
5. <span data-ttu-id="f6df9-155">在 " **查看并完成添加组** " 窗格中，输入 **MFAUsers**，然后选择 " **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="f6df9-155">In the **Review and finish adding group** pane, enter **MFAUsers**, and then select **Next**.</span></span>
6. <span data-ttu-id="f6df9-156">在组列表中，选择 " **MFAUsers** " 组。</span><span class="sxs-lookup"><span data-stu-id="f6df9-156">In the list of groups, select the **MFAUsers** group.</span></span>
7. <span data-ttu-id="f6df9-157">在 " **MFAUsers** " 窗格中，选择 " **成员**"，然后选择 " **查看所有和管理成员**"。</span><span class="sxs-lookup"><span data-stu-id="f6df9-157">In the **MFAUsers** pane, select **Members**, and then select **View all and manage members**.</span></span>
8. <span data-ttu-id="f6df9-158">在 " **MFAUsers** " 窗格中，选择 "**添加成员**"，选择 "**用户 3**帐户"，然后选择 "**保存**  >  **关闭**  >  **关闭**"。</span><span class="sxs-lookup"><span data-stu-id="f6df9-158">In the **MFAUsers** pane, select **Add members**, select the **User 3** account, and then select **Save** > **Close** > **Close**.</span></span>

<span data-ttu-id="f6df9-159">接下来，创建一个条件访问策略，以要求对 MFAUsers 组成员进行多重身份验证。</span><span class="sxs-lookup"><span data-stu-id="f6df9-159">Next, create a conditional access policy to require multifactor authentication for members of the MFAUsers group.</span></span>

1. <span data-ttu-id="f6df9-160">在浏览器的新选项卡中，转到 [https://portal.azure.com](https://portal.azure.com) 。</span><span class="sxs-lookup"><span data-stu-id="f6df9-160">In a new tab of your browser, go to [https://portal.azure.com](https://portal.azure.com).</span></span>
2. <span data-ttu-id="f6df9-161">选择 " **Azure Active Directory**  >  **安全**  >  **条件访问**"。</span><span class="sxs-lookup"><span data-stu-id="f6df9-161">Select **Azure Active Directory** > **Security** > **Conditional Access**.</span></span>
3. <span data-ttu-id="f6df9-162">在 " **条件访问–策略** " 窗格中，选择 " **新建策略**"。</span><span class="sxs-lookup"><span data-stu-id="f6df9-162">In the **Conditional access – Policies** pane, select **New policy**.</span></span>
4. <span data-ttu-id="f6df9-163">在 "**新建**" 窗格中，在 "**名称**" 框中输入**用户帐户**的 "MFA"。</span><span class="sxs-lookup"><span data-stu-id="f6df9-163">In the **New** pane, enter **MFA for user accounts** in the **Name** box.</span></span>
5. <span data-ttu-id="f6df9-164">在 " **工作分配** " 部分，选择 " **用户和组**"。</span><span class="sxs-lookup"><span data-stu-id="f6df9-164">In the **Assignments** section, select **Users and groups**.</span></span>
6. <span data-ttu-id="f6df9-165">在 "**用户和组**" 窗格的 "**包含**" 选项卡上，选择 "**选择用户和组**  >  **用户和组**  >  **选择**"。</span><span class="sxs-lookup"><span data-stu-id="f6df9-165">On the **Include** tab of the **Users and groups** pane, select **Select users and groups** > **Users and groups** > **Select**.</span></span>
7. <span data-ttu-id="f6df9-166">在**选择**窗格中，选择 " **MFAUsers** " 组，然后选择 "**选择**"  >  **完成**"。</span><span class="sxs-lookup"><span data-stu-id="f6df9-166">In the **Select** pane, select the **MFAUsers** group, and then select **Select** > **Done**.</span></span>
8. <span data-ttu-id="f6df9-167">在**新**窗格的 "**访问控制**" 部分，选择 "**授予**"。</span><span class="sxs-lookup"><span data-stu-id="f6df9-167">In the **Access controls** section of the **New** pane, select **Grant**.</span></span>
9. <span data-ttu-id="f6df9-168">在 " **授予** " 窗格中，选择 " **需要多重身份验证**"，然后选择 " **选择**"。</span><span class="sxs-lookup"><span data-stu-id="f6df9-168">In the **Grant** pane, select **Require multi-factor authentication**, and then select **Select**.</span></span>
10. <span data-ttu-id="f6df9-169">在 "**新建**" 窗格中，选择 "**启用策略**"，然后选择 "**创建** **"** 。</span><span class="sxs-lookup"><span data-stu-id="f6df9-169">In the **New** pane, select **On** for **Enable policy**, and then select **Create**.</span></span>
11. <span data-ttu-id="f6df9-170">关闭 " **Azure 门户** " 和 " **Microsoft 365 管理中心** " 选项卡。</span><span class="sxs-lookup"><span data-stu-id="f6df9-170">Close the **Azure portal** and **Microsoft 365 admin center** tabs.</span></span>

<span data-ttu-id="f6df9-171">若要测试此策略，请注销并使用用户3帐户登录。</span><span class="sxs-lookup"><span data-stu-id="f6df9-171">To test this policy, sign out and sign in with the User 3 account.</span></span> <span data-ttu-id="f6df9-172">系统会提示您配置 MFA。</span><span class="sxs-lookup"><span data-stu-id="f6df9-172">You should be prompted to configure MFA.</span></span> <span data-ttu-id="f6df9-173">这说明正在应用 MFAUsers 策略。</span><span class="sxs-lookup"><span data-stu-id="f6df9-173">This demonstrates that the MFAUsers policy is being applied.</span></span>

## <a name="next-step"></a><span data-ttu-id="f6df9-174">后续步骤</span><span class="sxs-lookup"><span data-stu-id="f6df9-174">Next step</span></span>

<span data-ttu-id="f6df9-175">在测试环境中探索其他[标识](m365-enterprise-test-lab-guides.md#identity)特性和功能。</span><span class="sxs-lookup"><span data-stu-id="f6df9-175">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="f6df9-176">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f6df9-176">See also</span></span>

[<span data-ttu-id="f6df9-177">标识路线图</span><span class="sxs-lookup"><span data-stu-id="f6df9-177">Identity roadmap</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="f6df9-178">Microsoft 365 企业版测试实验室指南</span><span class="sxs-lookup"><span data-stu-id="f6df9-178">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="f6df9-179">Microsoft 365 企业版概述</span><span class="sxs-lookup"><span data-stu-id="f6df9-179">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="f6df9-180">适用于企业的 Microsoft 365 文档</span><span class="sxs-lookup"><span data-stu-id="f6df9-180">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
