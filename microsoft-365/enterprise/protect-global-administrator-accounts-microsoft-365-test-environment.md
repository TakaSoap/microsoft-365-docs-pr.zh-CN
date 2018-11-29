---
title: 保护 Microsoft 365 企业版测试环境中的全局管理员帐户
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
description: 使用以下步骤来保护 Microsoft 365 企业版测试环境中的全局管理员帐户。
ms.openlocfilehash: 233e2178b060df4950c340e034d5f51216fac8fb
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2018
ms.locfileid: "26865422"
---
# <a name="protect-global-administrator-accounts-in-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="138ec-103">保护 Microsoft 365 企业版测试环境中的全局管理员帐户</span><span class="sxs-lookup"><span data-stu-id="138ec-103">Protect global administrator accounts in your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="138ec-p101">您可以确保您的管理员帐户尽可能安全以阻止对您的组织的数字攻击。本文介绍如何使用 Office 365 云应用程序安全性和 Azure AD 条件访问策略来保护全局管理员帐户。</span><span class="sxs-lookup"><span data-stu-id="138ec-p101">You can prevent digital attacks on your organization by ensuring that your administrator accounts are as secure as possible. This article describes how to use Office 365 Cloud App Security and Azure AD conditional access policies to protect global administrator accounts.</span></span>

<span data-ttu-id="138ec-106">有两个阶段保护 Microsoft 365 企业版测试环境中的全局管理员帐户：</span><span class="sxs-lookup"><span data-stu-id="138ec-106">There are two phases to protecting global administrator accounts in your Microsoft 365 Enterprise test environment:</span></span>

1.  <span data-ttu-id="138ec-107">创建 Microsoft 365 企业版测试环境。</span><span class="sxs-lookup"><span data-stu-id="138ec-107">Create the Microsoft 365 Enterprise test environment.</span></span>
2.  <span data-ttu-id="138ec-108">保护您的专用的全局管理员帐户。</span><span class="sxs-lookup"><span data-stu-id="138ec-108">Protect your dedicated global administrator account.</span></span>

![Microsoft 云测试实验室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="138ec-110">单击[此处](https://aka.ms/m365etlgstack)可查看 Microsoft 365 企业版测试实验室指南集合中所有文章的直观图。</span><span class="sxs-lookup"><span data-stu-id="138ec-110">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  

## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="138ec-111">第 1 阶段： 构建 Microsoft 365 企业版测试环境</span><span class="sxs-lookup"><span data-stu-id="138ec-111">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="138ec-112">如果您只想要测试的最低硬件要求与轻型方式的全局管理员帐户保护，按照[轻型基本配置](lightweight-base-configuration-microsoft-365-enterprise.md)中的说明。</span><span class="sxs-lookup"><span data-stu-id="138ec-112">If you just want to test global administrator account protection in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="138ec-113">如果您想要测试模拟企业中的全局管理员帐户保护，请按照[传递身份验证](pass-through-auth-m365-ent-test-environment.md)中的说明。</span><span class="sxs-lookup"><span data-stu-id="138ec-113">If you want to test global administrator account protection in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="138ec-p102">测试全局管理员帐户保护不需要模拟的企业测试环境，其中包括模拟的 intranet 连接到 Internet 和 Windows Server AD 林目录同步。它提供此处作为一个选项，以便可以测试全局管理员帐户保护并与之试验环境值，该值代表典型组织中。</span><span class="sxs-lookup"><span data-stu-id="138ec-p102">Testing global administrator account protection does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for a Windows Server AD forest. It is provided here as an option so that you can test global administrator account protection and experiment with it in an environment that represents a typical organization.</span></span> 
  
## <a name="phase-2-configure-cloud-app-security-and-conditional-access-policies"></a><span data-ttu-id="138ec-116">第 2 阶段： 配置云应用程序安全性和条件的访问策略</span><span class="sxs-lookup"><span data-stu-id="138ec-116">Phase 2: Configure Cloud App Security and conditional access policies</span></span>

<span data-ttu-id="138ec-117">首先，创建 Office 365 云应用程序安全性策略监视全局管理员帐户活动并将通知发送给您的全局管理员帐户的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="138ec-117">First, create an Office 365 Cloud App Security policy to monitor global administrator account activity and send alerts to the email address of your global administrator account.</span></span> 

1. <span data-ttu-id="138ec-118">登录到 Office 365 门户[http://portal.office.com](http://portal.office.com)使用全局管理员帐户。</span><span class="sxs-lookup"><span data-stu-id="138ec-118">Sign in to the Office 365 portal at [http://portal.office.com](http://portal.office.com) using your global administrator account.</span></span>
2. <span data-ttu-id="138ec-p103">单击**管理员**图块。在**Office Admin center**选项卡上单击**管理中心 > 安全和合规性**。</span><span class="sxs-lookup"><span data-stu-id="138ec-p103">Click the **Admin** tile. On the **Office Admin center** tab, click **Admin centers > Security & Compliance**.</span></span>
3. <span data-ttu-id="138ec-121">在左侧的导航窗格中，单击**通知 > 管理高级通知**。</span><span class="sxs-lookup"><span data-stu-id="138ec-121">In the left navigation pane, click **Alerts > Manage advanced alerts**.</span></span>
4. <span data-ttu-id="138ec-122">在**高级通知的管理**页上，单击**打开 Office 365 云应用程序安全性**，然后单击**转到 Office 365 云应用程序安全性**。</span><span class="sxs-lookup"><span data-stu-id="138ec-122">On the **Manage advanced alerts** page, click **Turn on Office 365 Cloud App Security**, and then click **Go to Office 365 Cloud App Security**.</span></span>
5. <span data-ttu-id="138ec-123">在新的**仪表板**选项卡，单击**控件 > 策略**。</span><span class="sxs-lookup"><span data-stu-id="138ec-123">On the new **Dashboard** tab, click **Control > Policies**.</span></span>
6. <span data-ttu-id="138ec-124">在**策略**页上，单击**创建策略**，，然后单击**活动策略**。</span><span class="sxs-lookup"><span data-stu-id="138ec-124">On the **Policy** page, click **Create policy**, and then click **Activity policy**.</span></span>
7. <span data-ttu-id="138ec-125">在**策略名称**框中，键入**管理活动**。</span><span class="sxs-lookup"><span data-stu-id="138ec-125">In **Policy name**, type **Administrative activity**.</span></span>
8. <span data-ttu-id="138ec-126">在“**策略严重性**”中，单击“**高**”。</span><span class="sxs-lookup"><span data-stu-id="138ec-126">In **Policy severity**, click **High**.</span></span>
9. <span data-ttu-id="138ec-127">在**类别**中，单击**特权的帐户**。</span><span class="sxs-lookup"><span data-stu-id="138ec-127">In **Category**, click **Privileged accounts**.</span></span>
10. <span data-ttu-id="138ec-128">在**创建筛选器策略**，在**以下所有条件匹配的活动**中，单击**管理活动**。</span><span class="sxs-lookup"><span data-stu-id="138ec-128">In **Create filters for the policy**, in **Activities matching all of the following**, click **Administrative activity**.</span></span>
11. <span data-ttu-id="138ec-p104">在“**警报**”中，单击“**作为电子邮件发送警报**”。在“**收件人**”中，键入你的全局管理员帐户的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="138ec-p104">In **Alerts**, click **Send alert as email**. In **To**, type the email address of your global administrator account.</span></span>
12. <span data-ttu-id="138ec-131">在页面底部，单击“**创建**”。</span><span class="sxs-lookup"><span data-stu-id="138ec-131">At the bottom of the page, click **Create**.</span></span>
13. <span data-ttu-id="138ec-132">关闭**仪表板**选项卡。</span><span class="sxs-lookup"><span data-stu-id="138ec-132">Close the **Dashboard** tab.</span></span>
    
<span data-ttu-id="138ec-133">接下来，创建新的用户帐户作为专用的全局管理员。</span><span class="sxs-lookup"><span data-stu-id="138ec-133">Next, create a new user account as a dedicated global administrator.</span></span>

1. <span data-ttu-id="138ec-134">在**Office Admin center**选项卡上，在**活动用户**下单击**添加用户**。</span><span class="sxs-lookup"><span data-stu-id="138ec-134">On the **Office Admin center** tab, under **Active users**, click **Add a user**.</span></span>
2. <span data-ttu-id="138ec-135">在**新建用户**页上，在**名字**、**显示名称**和**用户名**中键入**DedicatedAdmin** 。</span><span class="sxs-lookup"><span data-stu-id="138ec-135">On the **New user** page, type **DedicatedAdmin** in **First name**, **Display name**, and **Username**.</span></span>
3. <span data-ttu-id="138ec-p105">单击**密码**，单击**让我创建密码**，，，然后键入强密码。在安全位置记录此新帐户的密码。</span><span class="sxs-lookup"><span data-stu-id="138ec-p105">Click **Password**, click **Let me create the password**, and then type a strong password. Record the password for this new account in a secure location.</span></span>
4. <span data-ttu-id="138ec-138">清除**进行此更改其密码它们首次登录时的用户**。</span><span class="sxs-lookup"><span data-stu-id="138ec-138">Clear **Make this user change their password when they first sign in**.</span></span>
5. <span data-ttu-id="138ec-139">单击**角色**，然后单击**全局管理员**。</span><span class="sxs-lookup"><span data-stu-id="138ec-139">Click **Roles**, and then click **Global administrator**.</span></span>
6. <span data-ttu-id="138ec-140">单击**产品许可证**，，然后打开的**企业移动 + 安全 E5**和**Office 365 企业 E5 许可证**。</span><span class="sxs-lookup"><span data-stu-id="138ec-140">Click **Product licenses**, and then turn the **Enterprise Mobility + Security E5** and **Office 365 Enterprise E5 licenses** on.</span></span>
7. <span data-ttu-id="138ec-141">单击" **添加**"。</span><span class="sxs-lookup"><span data-stu-id="138ec-141">Click **Add**.</span></span>
8. <span data-ttu-id="138ec-142">在**用户已添加页上**，清除**发送电子邮件中的密码**，，然后单击**关闭**。</span><span class="sxs-lookup"><span data-stu-id="138ec-142">On the **User was added page**, clear **Send password in email**, and then click **Close**.</span></span>

<span data-ttu-id="138ec-143">接下来，创建一个名为 GlobalAdmins 的新组并向其添加 DedicatedAdmin 帐户。</span><span class="sxs-lookup"><span data-stu-id="138ec-143">Next, create a new group named GlobalAdmins and add the DedicatedAdmin account to it.</span></span>

1. <span data-ttu-id="138ec-144">在**Office Admin center**选项卡中，单击左侧导航窗格中，在组图标，然后单击**组**。</span><span class="sxs-lookup"><span data-stu-id="138ec-144">On the **Office Admin center** tab, click the groups icon in the left navigation, and then click **Groups**.</span></span>
2. <span data-ttu-id="138ec-145">单击**添加组**。</span><span class="sxs-lookup"><span data-stu-id="138ec-145">Click **Add a group**.</span></span>
3. <span data-ttu-id="138ec-146">在**新建组**页中，键入**GlobalAdmins**。</span><span class="sxs-lookup"><span data-stu-id="138ec-146">On the **New Group** page, type **GlobalAdmins**.</span></span>
4. <span data-ttu-id="138ec-147">单击您的全局管理员帐户的**选择所有者**单击，然后单击**添加 > 关闭**。</span><span class="sxs-lookup"><span data-stu-id="138ec-147">Click **Select owner** click your global administrator account, and then click **Add > Close**.</span></span>
5. <span data-ttu-id="138ec-148">在组列表中，单击**GlobalAdmins**组。</span><span class="sxs-lookup"><span data-stu-id="138ec-148">In the list of groups, click the **GlobalAdmins** group.</span></span>
6. <span data-ttu-id="138ec-149">在**GlobalAdmins**页上，单击**编辑的成员**，然后单击**添加成员**。</span><span class="sxs-lookup"><span data-stu-id="138ec-149">On the **GlobalAdmins** page, click **Edit for Member**, and then click **Add members**.</span></span>
7. <span data-ttu-id="138ec-150">在列表中，单击**DedicatedAdmin**帐户，然后单击**保存 > 关闭 > 关闭 > Admin center**。</span><span class="sxs-lookup"><span data-stu-id="138ec-150">In the list, click the **DedicatedAdmin** account, and then click **Save > Close > Close > Admin center**.</span></span>

<span data-ttu-id="138ec-151">接下来，创建条件访问策略需要多因素身份验证的全局管理员帐户和拒绝身份验证登录风险时中型或更高。</span><span class="sxs-lookup"><span data-stu-id="138ec-151">Next, create conditional access policies to require multifactor authentication for global administrator accounts and to deny authentication if the sign-in risk is medium or high.</span></span>

<span data-ttu-id="138ec-152">此第一个策略要求所有全局管理员帐户使用 MFA。</span><span class="sxs-lookup"><span data-stu-id="138ec-152">This first policy requires that all global administrator accounts use MFA.</span></span>

1. <span data-ttu-id="138ec-153">在浏览器的新建选项卡上，转到[https://portal.azure.com](https://portal.azure.com)。</span><span class="sxs-lookup"><span data-stu-id="138ec-153">In a new tab of your browser, go to [https://portal.azure.com](https://portal.azure.com).</span></span>
2. <span data-ttu-id="138ec-154">单击**Azure Active Directory > 条件访问**。</span><span class="sxs-lookup"><span data-stu-id="138ec-154">Click **Azure Active Directory > Conditional access**.</span></span>
3. <span data-ttu-id="138ec-155">在**条件访问 – 策略**刀片中，单击**基准策略： 对于管理员 （预览） 需要 MFA**。</span><span class="sxs-lookup"><span data-stu-id="138ec-155">On the **Conditional access – Policies** blade, click **Baseline policy: Require MFA for admins (preview)**.</span></span>
4. <span data-ttu-id="138ec-p106">在**比较基准策略...** 刀片中，单击**立即使用策略 > 保存**。</span><span class="sxs-lookup"><span data-stu-id="138ec-p106">On the **Baseline policies…** blade, click **Use policy immediately > Save**.</span></span>

<span data-ttu-id="138ec-158">此第二个策略阻止对访问登录助手风险时中型或更高的全局管理员帐户身份验证。</span><span class="sxs-lookup"><span data-stu-id="138ec-158">This second policy blocks access to global administrator account authentication when the sign-in risk is medium or high.</span></span>

1. <span data-ttu-id="138ec-159">在**条件访问 – 策略**刀片中，单击**新建策略**。</span><span class="sxs-lookup"><span data-stu-id="138ec-159">On the **Conditional access – Policies** blade, click **New policy**.</span></span>
2. <span data-ttu-id="138ec-160">在**新建**刀片，在**名称**中键入**全局管理员**。</span><span class="sxs-lookup"><span data-stu-id="138ec-160">On the **New** blade, type **Global administrators** in **Name**.</span></span>
3. <span data-ttu-id="138ec-161">在**分配**部分中，单击**用户和组**。</span><span class="sxs-lookup"><span data-stu-id="138ec-161">In the **Assignments** section, click **Users and groups**.</span></span>
4. <span data-ttu-id="138ec-162">在**用户和组**刀片**包含**选项卡上，单击**选择用户和组 > 用户和组 > 选择**。</span><span class="sxs-lookup"><span data-stu-id="138ec-162">On the **Include** tab of the **Users and groups** blade, click **Select users and groups > Users and groups > Select**.</span></span>
5. <span data-ttu-id="138ec-163">在**选择**刀片中，单击**GlobalAdmins > 选择 > 完成**。</span><span class="sxs-lookup"><span data-stu-id="138ec-163">On the **Select** blade, click the **GlobalAdmins > Select > Done**.</span></span>
6. <span data-ttu-id="138ec-164">在**分配**部分中，单击**条件**。</span><span class="sxs-lookup"><span data-stu-id="138ec-164">In the **Assignments** section, click **Conditions**.</span></span>
7. <span data-ttu-id="138ec-165">**条件**刀片上, 单击**登录风险**，单击**是\*\*\*\*配置**，单击**高**和**Medium**，然后单击**选择**并**完成**。</span><span class="sxs-lookup"><span data-stu-id="138ec-165">On the **Conditions** blade, click **Sign-in risk**, click **Yes** for **Configure**, click **High** and **Medium**, and then click **Select** and **Done**.</span></span>
8. <span data-ttu-id="138ec-166">在**新建**刀片**访问控制**部分中，单击**授予**。</span><span class="sxs-lookup"><span data-stu-id="138ec-166">In the **Access controls** section of the **New** blade, click **Grant**.</span></span>
9. <span data-ttu-id="138ec-167">**授予**刀片上, 单击**阻止访问**，然后单击**选择**。</span><span class="sxs-lookup"><span data-stu-id="138ec-167">On the **Grant** blade, click **Block access**, and then click **Select**.</span></span>
10. <span data-ttu-id="138ec-168">**新建**刀片上**的**启用策略**，单击**，然后单击**创建**。</span><span class="sxs-lookup"><span data-stu-id="138ec-168">On the **New** blade, click **On** for **Enable policy**, and then click **Create**.</span></span>
11. <span data-ttu-id="138ec-169">关闭**Azure 门户**和**Office 管理中心**选项卡。</span><span class="sxs-lookup"><span data-stu-id="138ec-169">Close the **Azure portal** and **Office Admin center** tabs.</span></span>

<span data-ttu-id="138ec-p107">若要测试的第一个策略，请先注销，然后使用 DedicatedAdmin 帐户登录。您应提示用户帐户配置 MFA。此示例演示应用的第一个策略。</span><span class="sxs-lookup"><span data-stu-id="138ec-p107">To test the first policy, sign out and sign in with the DedicatedAdmin account. You should be prompted to configure MFA on the user account. This demonstrates that the first policy is being applied.</span></span>

<span data-ttu-id="138ec-173">有关信息和链接以保护您的全局管理员帐户在生产中的标识阶段，请参阅[Protect 全局管理员帐户](identity-designate-protect-admin-accounts.md)步骤。</span><span class="sxs-lookup"><span data-stu-id="138ec-173">See the [Protect global administrator accounts](identity-designate-protect-admin-accounts.md) step in the Identity phase for information and links to protect your global administrator accounts in production.</span></span>

## <a name="next-step"></a><span data-ttu-id="138ec-174">后续步骤</span><span class="sxs-lookup"><span data-stu-id="138ec-174">Next step</span></span>

<span data-ttu-id="138ec-175">在测试环境中探索其他[标识](m365-enterprise-test-lab-guides.md#identity)特性和功能。</span><span class="sxs-lookup"><span data-stu-id="138ec-175">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="138ec-176">另请参阅</span><span class="sxs-lookup"><span data-stu-id="138ec-176">See also</span></span>

[<span data-ttu-id="138ec-177">阶段 2：标识</span><span class="sxs-lookup"><span data-stu-id="138ec-177">Phase 2: Identity</span></span>](identity-infrastructure.md)

[<span data-ttu-id="138ec-178">Microsoft 365 企业版测试实验室指南</span><span class="sxs-lookup"><span data-stu-id="138ec-178">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="138ec-179">Microsoft 365 企业版部署</span><span class="sxs-lookup"><span data-stu-id="138ec-179">Microsoft 365 Enterprise deployment</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="138ec-180">Microsoft 365 企业版文档</span><span class="sxs-lookup"><span data-stu-id="138ec-180">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
