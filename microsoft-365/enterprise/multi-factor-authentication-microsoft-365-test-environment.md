---
title: Microsoft 365 企业版的多因素身份验证测试环境
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/21/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
ms.custom:
- TLG
- Ent_TLGs
description: 配置多重身份验证使用发送到 Microsoft 365 企业版测试环境中智能电话的短信。
ms.openlocfilehash: aae493e79a197635b2e14fa7f238a3189ed695ae
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2018
ms.locfileid: "26865401"
---
# <a name="multi-factor-authentication-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="18077-103">Microsoft 365 企业版的多因素身份验证测试环境</span><span class="sxs-lookup"><span data-stu-id="18077-103">Multi-factor authentication for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="18077-p101">登录到 Office 365 或任何服务或为您的组织使用 Azure AD 租户的应用程序的安全性的其他级别，可以启用 Azure 多因素身份验证，这要求远不止用户名和密码验证帐户。使用多因素身份验证，用户所需确认电话呼叫，键入验证代码发送文本消息，或在其智能手机上正确输入自己的密码之后指定应用程序密码。在此第二个身份验证因素已得到满足之后，才可以登录状态。</span><span class="sxs-lookup"><span data-stu-id="18077-p101">For an additional level of security for signing in to Office 365 or any service or application that uses the Azure AD tenant for your organization, you can enable Azure multi-factor authentication, which requires more than just a username and password to verify an account. With multi-factor authentication, users are required to acknowledge a phone call, type a verification code sent in a text message, or specify an app password on their smart phones after correctly entering their passwords. They can sign in only after this second authentication factor has been satisfied.</span></span> 
  
<span data-ttu-id="18077-107">本文介绍如何启用和测试文本为特定帐户的基于消息的身份验证。</span><span class="sxs-lookup"><span data-stu-id="18077-107">This article describes how to enable and test text message-based authentication for a specific account.</span></span>
  
<span data-ttu-id="18077-108">有两个阶段设置多因素身份验证 Microsoft 365 企业版测试环境中的帐户：</span><span class="sxs-lookup"><span data-stu-id="18077-108">There are two phases to setting up multi-factor authentication for an account in your Microsoft 365 Enterprise test environment:</span></span>
  
1. <span data-ttu-id="18077-109">创建 Microsoft 365 企业版测试环境。</span><span class="sxs-lookup"><span data-stu-id="18077-109">Create the Microsoft 365 Enterprise test environment.</span></span>
    
2. <span data-ttu-id="18077-110">为 User 2 帐户启用并测试多重身份验证。</span><span class="sxs-lookup"><span data-stu-id="18077-110">Enable and test multi-factor authentication for the User 2 account.</span></span>

![Microsoft 云测试实验室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="18077-112">单击[此处](https://aka.ms/m365etlgstack)可查看 Microsoft 365 企业版测试实验室指南集合中所有文章的直观图。</span><span class="sxs-lookup"><span data-stu-id="18077-112">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="18077-113">第 1 阶段： 构建 Microsoft 365 企业版测试环境</span><span class="sxs-lookup"><span data-stu-id="18077-113">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="18077-114">如果您只想要测试的最低硬件要求与轻型方式中的多因素身份验证，请按照[轻型基本配置](lightweight-base-configuration-microsoft-365-enterprise.md)中的说明。</span><span class="sxs-lookup"><span data-stu-id="18077-114">If you just want to test multi-factor authentication in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="18077-115">如果您想要测试模拟企业中的多因素身份验证，请按照[传递身份验证](pass-through-auth-m365-ent-test-environment.md)中的说明。</span><span class="sxs-lookup"><span data-stu-id="18077-115">If you want to test multi-factor authentication in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="18077-p102">测试多因素身份验证不需要模拟的企业测试环境，其中包括连接到 Internet 模拟的 intranet 和 Windows Server AD 林目录同步。它提供此处作为一个选项，以便可以测试多因素身份验证并代表典型组织的环境中试验它。</span><span class="sxs-lookup"><span data-stu-id="18077-p102">Testing multi-factor authentication does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for a Windows Server AD forest. It is provided here as an option so that you can test multi-factor authentication and experiment with it in an environment that represents a typical organization.</span></span> 
  
## <a name="phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account"></a><span data-ttu-id="18077-118">阶段 2：启用和测试 User 2 帐户的多重身份验证</span><span class="sxs-lookup"><span data-stu-id="18077-118">Phase 2: Enable and test multi-factor authentication for the User 2 account</span></span>

<span data-ttu-id="18077-119">通过以下步骤为 User 2 帐户启用多重身份验证：</span><span class="sxs-lookup"><span data-stu-id="18077-119">Enable multi-factor authentication for the User 2 account with these steps:</span></span>
  
1. <span data-ttu-id="18077-120">打开单独的专用的浏览器实例，请转到 Office 365 门户 ([https://portal.office.com](https://portal.office.com))，然后使用您的全局管理员帐户登录。</span><span class="sxs-lookup"><span data-stu-id="18077-120">Open a separate, private instance of your browser, go to the Office 365 portal ([https://portal.office.com](https://portal.office.com)), and then sign in with your global administrator account.</span></span>
    
2. <span data-ttu-id="18077-121">在主门户页上，单击“管理员”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="18077-121">From the main portal page, click **Admin**.</span></span>
    
3. <span data-ttu-id="18077-122">在左侧导航栏中，依次单击“用户”和“活动用户”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="18077-122">In the left navigation, click **Users > Active users**.</span></span>
    
4. <span data-ttu-id="18077-123">在活动用户窗格中，单击**更多 > 多因素身份验证设置**。</span><span class="sxs-lookup"><span data-stu-id="18077-123">In the Active users pane, click **More > Multi-factor authentication setup**.</span></span>
    
5. <span data-ttu-id="18077-124">在列表中，选择的**用户 2**帐户。</span><span class="sxs-lookup"><span data-stu-id="18077-124">In the list, select the **User 2** account.</span></span>
    
6. <span data-ttu-id="18077-125">在**用户 2**部分中，单击**快速步骤**下的**启用**。</span><span class="sxs-lookup"><span data-stu-id="18077-125">In the **User 2** section, under **Quick steps**, click **Enable**.</span></span>
    
7. <span data-ttu-id="18077-126">在**有关启用多重身份验证**对话框中，单击**启用多重身份验证**。</span><span class="sxs-lookup"><span data-stu-id="18077-126">In the **About enabling multi-factor auth** dialog box, click **Enable multi-factor auth**.</span></span>
    
8. <span data-ttu-id="18077-127">在**更新成功**对话框中，单击**关闭**。</span><span class="sxs-lookup"><span data-stu-id="18077-127">In the **Updates successful** dialog box, click **Close**.</span></span>
    
9. <span data-ttu-id="18077-128">在**Microsoft Office Home**选项卡上，单击右上方中的用户帐户图标，然后单击**注销**。</span><span class="sxs-lookup"><span data-stu-id="18077-128">On the **Microsoft Office Home** tab, click the user account icon in the upper right, and then click **Sign out**.</span></span>
    
10. <span data-ttu-id="18077-129">关闭浏览器实例。</span><span class="sxs-lookup"><span data-stu-id="18077-129">Close your browser instance.</span></span>
   
<span data-ttu-id="18077-130">完成 User 2 帐户的配置，通过以下步骤，使用短信对其进行验证和测试：</span><span class="sxs-lookup"><span data-stu-id="18077-130">Complete the configuration for the User 2 account to use a text message for validation and test it with these steps:</span></span>
  
1. <span data-ttu-id="18077-131">打开浏览器的专用的新实例。</span><span class="sxs-lookup"><span data-stu-id="18077-131">Open a new, private instance of your browser.</span></span>
    
2. <span data-ttu-id="18077-132">转到 Office 365 门户 ([https://portal.office.com](https://portal.office.com)) 和使用用户 2 帐户的登录 (user2 @\<组织名称 >。 onmicrosoft.com) 和密码。</span><span class="sxs-lookup"><span data-stu-id="18077-132">Go to the Office 365 portal ([https://portal.office.com](https://portal.office.com)) and sign in with the User 2 account (user2@\<organization name>.onmicrosoft.com) and password.</span></span>
    
3. <span data-ttu-id="18077-p103">在登录后被提示设置的详细信息的帐户。单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="18077-p103">After signing in, you are prompted to set up the account for more information. Click **Next**.</span></span>
    
4. <span data-ttu-id="18077-135">在**其他安全验证**页上：</span><span class="sxs-lookup"><span data-stu-id="18077-135">On the **Additional security verification** page:</span></span>
    
   - <span data-ttu-id="18077-136">选择你所在的国家或地区。</span><span class="sxs-lookup"><span data-stu-id="18077-136">Select your country or region.</span></span>
    
   - <span data-ttu-id="18077-137">键入接收短信的智能手机的电话号码。</span><span class="sxs-lookup"><span data-stu-id="18077-137">Type phone number of the smart phone that will receive text messages.</span></span>
    
   - <span data-ttu-id="18077-138">在**方法**中，单击**给我发送的短信代码**。</span><span class="sxs-lookup"><span data-stu-id="18077-138">In **Method**, click **Send me a code by text message**.</span></span>
    
5. <span data-ttu-id="18077-139">单击“下一步”。</span><span class="sxs-lookup"><span data-stu-id="18077-139">Click **Next**.</span></span>
    
6. <span data-ttu-id="18077-140">输入介于智能手机上收到的文本消息验证代码，然后单击**验证**。</span><span class="sxs-lookup"><span data-stu-id="18077-140">Enter the verification code from the text message received on your smart phone, and then click **Verify**.</span></span>
    
7. <span data-ttu-id="18077-141">在**步骤 3： 保留现有的应用程序**页上，在安全的位置，记录用户 2 帐户的显示应用程序密码，然后单击**完成**。</span><span class="sxs-lookup"><span data-stu-id="18077-141">On the **Step 3: Keep your existing applications** page, record the displayed app password for the User 2 account in a secure location, and then click **Done**.</span></span>
    
8. <span data-ttu-id="18077-p104">如果这是首次您使用登录用户 2 帐户后，在系统提示您要更改的密码。两次，键入原始密码和新密码，然后单击**更新密码和登录**。记录在安全位置的新密码。</span><span class="sxs-lookup"><span data-stu-id="18077-p104">If this is the first time you signed in with the User 2 account, you are prompted to change the password. Type the original password and a new password twice, and then click **Update password and sign in**. Record the new password in a secure location.</span></span>
    
    <span data-ttu-id="18077-145">您应在浏览器的**Microsoft Office Home**选项卡上看到用户 2 的 Office 365 门户。</span><span class="sxs-lookup"><span data-stu-id="18077-145">You should see the Office 365 portal for User 2 on the **Microsoft Office Home** tab of your browser.</span></span>


<span data-ttu-id="18077-146">在标识阶段的信息和链接以部署生产环境中的多因素身份验证，请参阅[设置多因素身份验证](identity-multi-factor-authentication.md)步骤。</span><span class="sxs-lookup"><span data-stu-id="18077-146">See the [Set up multi-factor authentication](identity-multi-factor-authentication.md) step in the Identity phase for information and links to deploy multi-factor authentication in production.</span></span>
    
## <a name="next-step"></a><span data-ttu-id="18077-147">后续步骤</span><span class="sxs-lookup"><span data-stu-id="18077-147">Next step</span></span>

<span data-ttu-id="18077-148">在测试环境中探索其他[标识](m365-enterprise-test-lab-guides.md#identity)特性和功能。</span><span class="sxs-lookup"><span data-stu-id="18077-148">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="18077-149">另请参阅</span><span class="sxs-lookup"><span data-stu-id="18077-149">See also</span></span>

[<span data-ttu-id="18077-150">阶段 2：标识</span><span class="sxs-lookup"><span data-stu-id="18077-150">Phase 2: Identity</span></span>](identity-infrastructure.md)

[<span data-ttu-id="18077-151">Microsoft 365 企业版测试实验室指南</span><span class="sxs-lookup"><span data-stu-id="18077-151">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="18077-152">Microsoft 365 企业版部署</span><span class="sxs-lookup"><span data-stu-id="18077-152">Microsoft 365 Enterprise deployment</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="18077-153">Microsoft 365 企业版文档</span><span class="sxs-lookup"><span data-stu-id="18077-153">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
