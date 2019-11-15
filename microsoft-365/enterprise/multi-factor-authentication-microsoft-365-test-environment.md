---
title: Microsoft 365 企业版测试环境的多重身份验证
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/21/2018
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom:
- TLG
- Ent_TLGs
description: 使用发送到 Microsoft 365 企业版测试环境中的智能手机的短信配置多重身份验证。
ms.openlocfilehash: 6c004f1ac093a997c263162ab8c945366f6361bd
ms.sourcegitcommit: 2c2248b03f7753d64490f2f7e56ec644a235b65a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/15/2019
ms.locfileid: "38639902"
---
# <a name="multi-factor-authentication-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="974b4-103">Microsoft 365 企业版测试环境的多重身份验证</span><span class="sxs-lookup"><span data-stu-id="974b4-103">Multi-factor authentication for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="974b4-104">若要使用其他级别的安全来登录到 Office 365 或使用组织的 Azure AD 租户的任何服务或应用程序，您可以启用 Azure 多重身份验证，它需要的用户名和密码不只需要用户名和密码才能验证上级.</span><span class="sxs-lookup"><span data-stu-id="974b4-104">For an additional level of security for signing in to Office 365 or any service or application that uses the Azure AD tenant for your organization, you can enable Azure multi-factor authentication, which requires more than just a username and password to verify an account.</span></span> <span data-ttu-id="974b4-105">使用多重身份验证时，用户需要确认电话呼叫、在短信中键入验证代码，或者在正确输入密码后在智能手机上指定应用密码。</span><span class="sxs-lookup"><span data-stu-id="974b4-105">With multi-factor authentication, users are required to acknowledge a phone call, type a verification code sent in a text message, or specify an app password on their smart phones after correctly entering their passwords.</span></span> <span data-ttu-id="974b4-106">仅在满足第二个身份验证因素时才能登录。</span><span class="sxs-lookup"><span data-stu-id="974b4-106">They can sign in only after this second authentication factor has been satisfied.</span></span> 
  
<span data-ttu-id="974b4-107">本文介绍如何为特定帐户启用和测试基于短信的身份验证。</span><span class="sxs-lookup"><span data-stu-id="974b4-107">This article describes how to enable and test text message-based authentication for a specific account.</span></span>
  
<span data-ttu-id="974b4-108">为 Microsoft 365 企业版测试环境中的帐户设置多重身份验证有两个阶段：</span><span class="sxs-lookup"><span data-stu-id="974b4-108">There are two phases to setting up multi-factor authentication for an account in your Microsoft 365 Enterprise test environment:</span></span>
  
1. <span data-ttu-id="974b4-109">创建 Microsoft 365 企业版测试环境。</span><span class="sxs-lookup"><span data-stu-id="974b4-109">Create the Microsoft 365 Enterprise test environment.</span></span>
    
2. <span data-ttu-id="974b4-110">为 User 2 帐户启用并测试多重身份验证。</span><span class="sxs-lookup"><span data-stu-id="974b4-110">Enable and test multi-factor authentication for the User 2 account.</span></span>

![Microsoft 云测试实验室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="974b4-112">单击[此处](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf)，即可获得 Microsoft 365 企业版测试实验室指南堆栈中所有文章的直观目录图。</span><span class="sxs-lookup"><span data-stu-id="974b4-112">Click [here](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="974b4-113">阶段 1：构建 Microsoft 365 企业版测试环境。</span><span class="sxs-lookup"><span data-stu-id="974b4-113">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="974b4-114">如果只想使用最低要求以轻型方式测试多重身份验证，请按照[轻型基本配置](lightweight-base-configuration-microsoft-365-enterprise.md)中的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="974b4-114">If you just want to test multi-factor authentication in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="974b4-115">如果要在模拟的企业中测试多重身份验证，请按照[传递身份验证](pass-through-auth-m365-ent-test-environment.md)中的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="974b4-115">If you want to test multi-factor authentication in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="974b4-116">测试多重身份验证不需要模拟企业测试环境，其中包括连接到 Internet 的模拟 intranet 和 Active Directory 域服务（AD DS）林的目录同步。</span><span class="sxs-lookup"><span data-stu-id="974b4-116">Testing multi-factor authentication does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for a Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="974b4-117">它在此处作为一个选项提供，以便你可以测试多重身份验证，并在代表典型组织的环境中对其进行试验。</span><span class="sxs-lookup"><span data-stu-id="974b4-117">It is provided here as an option so that you can test multi-factor authentication and experiment with it in an environment that represents a typical organization.</span></span> 
  
## <a name="phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account"></a><span data-ttu-id="974b4-118">阶段 2：启用和测试 User 2 帐户的多重身份验证</span><span class="sxs-lookup"><span data-stu-id="974b4-118">Phase 2: Enable and test multi-factor authentication for the User 2 account</span></span>

<span data-ttu-id="974b4-119">通过以下步骤为 User 2 帐户启用多重身份验证：</span><span class="sxs-lookup"><span data-stu-id="974b4-119">Enable multi-factor authentication for the User 2 account with these steps:</span></span>
  
1. <span data-ttu-id="974b4-120">打开浏览器的单独私有实例，转到 Microsoft 365 管理中心（[https://portal.microsoft.com](https://portal.microsoft.com)），然后使用全局管理员帐户登录。</span><span class="sxs-lookup"><span data-stu-id="974b4-120">Open a separate, private instance of your browser, go to the Microsoft 365 admin center ([https://portal.microsoft.com](https://portal.microsoft.com)), and then sign in with your global administrator account.</span></span>
    
2. <span data-ttu-id="974b4-121">在左侧导航栏中，单击“用户”>“活动用户”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="974b4-121">In the left navigation, click **Users > Active users**.</span></span>
    
3. <span data-ttu-id="974b4-122">在 "活动用户" 窗格中，单击 "**更多 > 多重身份验证设置**"。</span><span class="sxs-lookup"><span data-stu-id="974b4-122">In the Active users pane, click **More > Multi-factor authentication setup**.</span></span>
    
4. <span data-ttu-id="974b4-123">在列表中，选择 "**用户 2** " 帐户。</span><span class="sxs-lookup"><span data-stu-id="974b4-123">In the list, select the **User 2** account.</span></span>
    
5. <span data-ttu-id="974b4-124">在“User 2”\*\*\*\* 部分的“快速步骤”\*\*\*\* 下，单击“启用”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="974b4-124">In the **User 2** section, under **Quick steps**, click **Enable**.</span></span>
    
6. <span data-ttu-id="974b4-125">在“关于启用多重身份验证”\*\*\*\* 对话框中，单击“启用多重身份验证”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="974b4-125">In the **About enabling multi-factor auth** dialog box, click **Enable multi-factor auth**.</span></span>
    
7. <span data-ttu-id="974b4-126">在 "**更新成功**" 对话框中，单击 "**关闭**"。</span><span class="sxs-lookup"><span data-stu-id="974b4-126">In the **Updates successful** dialog box, click **Close**.</span></span>
    
8. <span data-ttu-id="974b4-127">在 " **Microsoft 365 管理中心**" 选项卡上，单击右上角的 "用户帐户" 图标，然后单击 **"注销"。**</span><span class="sxs-lookup"><span data-stu-id="974b4-127">On the **Microsoft 365 admin center** tab, click the user account icon in the upper right, and then click **Sign out**.</span></span>
    
9. <span data-ttu-id="974b4-128">关闭浏览器实例。</span><span class="sxs-lookup"><span data-stu-id="974b4-128">Close your browser instance.</span></span>
   
<span data-ttu-id="974b4-129">完成 User 2 帐户的配置，通过以下步骤，使用短信对其进行验证和测试：</span><span class="sxs-lookup"><span data-stu-id="974b4-129">Complete the configuration for the User 2 account to use a text message for validation and test it with these steps:</span></span>
  
1. <span data-ttu-id="974b4-130">打开浏览器的新的私有实例。</span><span class="sxs-lookup"><span data-stu-id="974b4-130">Open a new, private instance of your browser.</span></span>
    
2. <span data-ttu-id="974b4-131">转到 Office 365 门户（[https://portal.office.com](https://portal.office.com)），并使用用户2帐户名称和密码登录。</span><span class="sxs-lookup"><span data-stu-id="974b4-131">Go to the Office 365 portal ([https://portal.office.com](https://portal.office.com)) and sign in with the User 2 account name and password.</span></span>
    
3. <span data-ttu-id="974b4-132">登录后，系统会提示您设置帐户以获取详细信息。</span><span class="sxs-lookup"><span data-stu-id="974b4-132">After signing in, you are prompted to set up the account for more information.</span></span> <span data-ttu-id="974b4-133">单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="974b4-133">Click **Next**.</span></span>
    
4. <span data-ttu-id="974b4-134">在“其他安全性验证”\*\*\*\* 页上： </span><span class="sxs-lookup"><span data-stu-id="974b4-134">On the **Additional security verification** page:</span></span>
    
   - <span data-ttu-id="974b4-135">选择你所在的国家或地区。</span><span class="sxs-lookup"><span data-stu-id="974b4-135">Select your country or region.</span></span>
    
   - <span data-ttu-id="974b4-136">键入接收短信的智能手机的电话号码。</span><span class="sxs-lookup"><span data-stu-id="974b4-136">Type phone number of the smart phone that will receive text messages.</span></span>
    
   - <span data-ttu-id="974b4-137">在**方法**中，单击 "**通过短信向我发送代码**"。</span><span class="sxs-lookup"><span data-stu-id="974b4-137">In **Method**, click **Send me a code by text message**.</span></span>
    
5. <span data-ttu-id="974b4-138">单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="974b4-138">Click **Next**.</span></span>
    
6. <span data-ttu-id="974b4-139">输入智能手机收到的短信中的验证码，然后单击“验证”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="974b4-139">Enter the verification code from the text message received on your smart phone, and then click **Verify**.</span></span>
    
7. <span data-ttu-id="974b4-140">在“第 3 步: 保留现有应用程序”\*\*\*\* 页上，将显示的 User 2 帐户的应用密码记录在安全位置，然后单击“完成”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="974b4-140">On the **Step 3: Keep your existing applications** page, record the displayed app password for the User 2 account in a secure location, and then click **Done**.</span></span>
    
8. <span data-ttu-id="974b4-p104">如果这是你第一次使用 User 2 帐户登录，那么系统将提示你更改密码。键入原始密码和新密码两次，然后单击“更新密码并登录”\*\*\*\*。将新密码记录在安全位置。</span><span class="sxs-lookup"><span data-stu-id="974b4-p104">If this is the first time you signed in with the User 2 account, you are prompted to change the password. Type the original password and a new password twice, and then click **Update password and sign in**. Record the new password in a secure location.</span></span>
    
    <span data-ttu-id="974b4-144">您应在浏览器的 " **Microsoft Office 主页**" 选项卡上看到 "用户 2" 的 Office 门户。</span><span class="sxs-lookup"><span data-stu-id="974b4-144">You should see the Office portal for User 2 on the **Microsoft Office Home** tab of your browser.</span></span>


<span data-ttu-id="974b4-145">若要了解如何在生产环境中部署多重身份验证的信息和链接，请参阅 Identity 阶段中的[设置多重身份验证](identity-secure-user-sign-ins.md#identity-mfa)步骤。</span><span class="sxs-lookup"><span data-stu-id="974b4-145">See the [Set up multi-factor authentication](identity-secure-user-sign-ins.md#identity-mfa) step in the Identity phase for information and links to deploy multi-factor authentication in production.</span></span>
    
## <a name="next-step"></a><span data-ttu-id="974b4-146">后续步骤</span><span class="sxs-lookup"><span data-stu-id="974b4-146">Next step</span></span>

<span data-ttu-id="974b4-147">在测试环境中探索其他[标识](m365-enterprise-test-lab-guides.md#identity)特性和功能。</span><span class="sxs-lookup"><span data-stu-id="974b4-147">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="974b4-148">另请参阅</span><span class="sxs-lookup"><span data-stu-id="974b4-148">See also</span></span>

[<span data-ttu-id="974b4-149">阶段 2：标识</span><span class="sxs-lookup"><span data-stu-id="974b4-149">Phase 2: Identity</span></span>](identity-infrastructure.md)

[<span data-ttu-id="974b4-150">Microsoft 365 企业版测试实验室指南</span><span class="sxs-lookup"><span data-stu-id="974b4-150">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="974b4-151">Microsoft 365 企业版部署</span><span class="sxs-lookup"><span data-stu-id="974b4-151">Microsoft 365 Enterprise deployment</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="974b4-152">Microsoft 365 企业版文档</span><span class="sxs-lookup"><span data-stu-id="974b4-152">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
