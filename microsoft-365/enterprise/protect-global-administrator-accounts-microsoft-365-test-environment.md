---
title: 在 Microsoft 365 企业版测试环境中保护全局管理员帐户
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/16/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom:
- TLG
- Ent_TLGs
description: 使用这些步骤来保护 Microsoft 365 企业版测试环境中的全局管理员帐户。
ms.openlocfilehash: cded424188447f96e5614f31d3e207bb541d438e
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32290855"
---
# <a name="protect-global-administrator-accounts-in-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="8cf2a-103">在 Microsoft 365 企业版测试环境中保护全局管理员帐户</span><span class="sxs-lookup"><span data-stu-id="8cf2a-103">Protect global administrator accounts in your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="8cf2a-104">您可以通过确保您的管理员帐户尽可能安全, 来阻止组织的数字攻击。</span><span class="sxs-lookup"><span data-stu-id="8cf2a-104">You can prevent digital attacks on your organization by ensuring that your administrator accounts are as secure as possible.</span></span> <span data-ttu-id="8cf2a-105">本文介绍如何使用 Office 365 云应用安全和 Azure AD 条件访问策略来保护全局管理员帐户。</span><span class="sxs-lookup"><span data-stu-id="8cf2a-105">This article describes how to use Office 365 Cloud App Security and Azure AD conditional access policies to protect global administrator accounts.</span></span>

<span data-ttu-id="8cf2a-106">在 Microsoft 365 企业版测试环境中保护全局管理员帐户有两个阶段:</span><span class="sxs-lookup"><span data-stu-id="8cf2a-106">There are two phases to protecting global administrator accounts in your Microsoft 365 Enterprise test environment:</span></span>

1.  <span data-ttu-id="8cf2a-107">创建 Microsoft 365 企业版测试环境。</span><span class="sxs-lookup"><span data-stu-id="8cf2a-107">Create the Microsoft 365 Enterprise test environment.</span></span>
2.  <span data-ttu-id="8cf2a-108">保护您的专用全局管理员帐户。</span><span class="sxs-lookup"><span data-stu-id="8cf2a-108">Protect your dedicated global administrator account.</span></span>

![Microsoft 云测试实验室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="8cf2a-110">单击[此处](https://aka.ms/m365etlgstack)可查看 Microsoft 365 企业版测试实验室指南集合中所有文章的直观图。</span><span class="sxs-lookup"><span data-stu-id="8cf2a-110">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>

> [!NOTE]
> <span data-ttu-id="8cf2a-111">Microsoft 365 企业版测试环境使用 Office 365 的 E5 版本和企业版管理 + 安全性 (EMS)。</span><span class="sxs-lookup"><span data-stu-id="8cf2a-111">The Microsoft 365 Enterprise test environment uses E5 versions of Office 365 and Enterprise Management + Security (EMS).</span></span> <span data-ttu-id="8cf2a-112">office 365 云应用安全功能仅在 E5 版本 Office 365 中可用。</span><span class="sxs-lookup"><span data-stu-id="8cf2a-112">The Office 365 Cloud App Security feature is only available in the E5 version Office 365.</span></span> 

## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="8cf2a-113">第1阶段: 构建 Microsoft 365 企业版测试环境</span><span class="sxs-lookup"><span data-stu-id="8cf2a-113">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="8cf2a-114">如果只想使用最低要求以轻型方式测试全局管理员帐户保护, 请按照[轻型基本配置](lightweight-base-configuration-microsoft-365-enterprise.md)中的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="8cf2a-114">If you just want to test global administrator account protection in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="8cf2a-115">如果要在模拟的企业中测试全局管理员帐户保护, 请按照[传递身份验证](pass-through-auth-m365-ent-test-environment.md)中的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="8cf2a-115">If you want to test global administrator account protection in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>

  
> [!NOTE]
> <span data-ttu-id="8cf2a-116">测试全局管理员帐户保护不需要模拟企业测试环境, 其中包括连接到 Internet 的模拟 intranet 和 Active directory 域服务 (AD DS) 的目录同步。</span><span class="sxs-lookup"><span data-stu-id="8cf2a-116">Testing global administrator account protection does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS).</span></span> <span data-ttu-id="8cf2a-117">此处提供它作为选项, 以便您可以测试全局管理员帐户保护并在代表典型组织的环境中进行实验。</span><span class="sxs-lookup"><span data-stu-id="8cf2a-117">It is provided here as an option so that you can test global administrator account protection and experiment with it in an environment that represents a typical organization.</span></span> 
  
## <a name="phase-2-configure-cloud-app-security-and-conditional-access-policies"></a><span data-ttu-id="8cf2a-118">第2阶段: 配置云应用安全和条件访问策略</span><span class="sxs-lookup"><span data-stu-id="8cf2a-118">Phase 2: Configure Cloud App Security and conditional access policies</span></span>

<span data-ttu-id="8cf2a-119">首先, 创建 Office 365 云应用安全策略以监视全局管理员帐户活动并将警报发送到全局管理员帐户的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="8cf2a-119">First, create an Office 365 Cloud App Security policy to monitor global administrator account activity and send alerts to the email address of your global administrator account.</span></span> 

1. <span data-ttu-id="8cf2a-120">使用全局管理员帐户登录到[Office 365 Security & 合规性门户](https://protection.office.com/)。</span><span class="sxs-lookup"><span data-stu-id="8cf2a-120">Sign in to the [Office 365 Security & Compliance portal](https://protection.office.com/) using your global administrator account.</span></span>
2. <span data-ttu-id="8cf2a-121">在左侧导航窗格中, 单击 "**通知 > 管理高级警报**"。</span><span class="sxs-lookup"><span data-stu-id="8cf2a-121">In the left navigation pane, click **Alerts > Manage advanced alerts**.</span></span>
3. <span data-ttu-id="8cf2a-122">在 "**管理高级通知**" 页面上, 单击 "**启用 office 365 云应用安全性**", 然后单击 "**转到 office 365 云应用安全性**"。</span><span class="sxs-lookup"><span data-stu-id="8cf2a-122">On the **Manage advanced alerts** page, click **Turn on Office 365 Cloud App Security**, and then click **Go to Office 365 Cloud App Security**.</span></span>
4. <span data-ttu-id="8cf2a-123">在 "新建**仪表板**" 选项卡上, 单击 "**控制 > 策略**"。</span><span class="sxs-lookup"><span data-stu-id="8cf2a-123">On the new **Dashboard** tab, click **Control > Policies**.</span></span>
5. <span data-ttu-id="8cf2a-124">在 "**策略**" 页上, 单击 "**创建策略**", 然后单击 "**活动策略**"。</span><span class="sxs-lookup"><span data-stu-id="8cf2a-124">On the **Policy** page, click **Create policy**, and then click **Activity policy**.</span></span>
6. <span data-ttu-id="8cf2a-125">在 "**策略名称**" 中, 键入 "**管理活动**"。</span><span class="sxs-lookup"><span data-stu-id="8cf2a-125">In **Policy name**, type **Administrative activity**.</span></span>
7. <span data-ttu-id="8cf2a-126">在“**策略严重性**”中，单击“**高**”。</span><span class="sxs-lookup"><span data-stu-id="8cf2a-126">In **Policy severity**, click **High**.</span></span>
8. <span data-ttu-id="8cf2a-127">在 "**类别**" 中, 单击 "**特权帐户**"。</span><span class="sxs-lookup"><span data-stu-id="8cf2a-127">In **Category**, click **Privileged accounts**.</span></span>
9. <span data-ttu-id="8cf2a-128">在 **"为策略创建筛选器**" 中, 在**匹配以下所有**项的活动中, 单击 "**管理活动**"。</span><span class="sxs-lookup"><span data-stu-id="8cf2a-128">In **Create filters for the policy**, in **Activities matching all of the following**, click **Administrative activity**.</span></span>
10. <span data-ttu-id="8cf2a-p104">在“**警报**”中，单击“**作为电子邮件发送警报**”。在“**收件人**”中，键入你的全局管理员帐户的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="8cf2a-p104">In **Alerts**, click **Send alert as email**. In **To**, type the email address of your global administrator account.</span></span>
11. <span data-ttu-id="8cf2a-131">在页面底部，单击“**创建**”。</span><span class="sxs-lookup"><span data-stu-id="8cf2a-131">At the bottom of the page, click **Create**.</span></span>
12. <span data-ttu-id="8cf2a-132">关闭 "**仪表板**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="8cf2a-132">Close the **Dashboard** tab.</span></span>
    
<span data-ttu-id="8cf2a-133">接下来, 创建一个新的用户帐户作为专用全局管理员。</span><span class="sxs-lookup"><span data-stu-id="8cf2a-133">Next, create a new user account as a dedicated global administrator.</span></span>

1. <span data-ttu-id="8cf2a-134">在单独的选项卡上, 打开[Microsoft 365 管理中心](https://admin.microsoft.com/)。</span><span class="sxs-lookup"><span data-stu-id="8cf2a-134">On a separate tab, open the [Microsoft 365 admin center](https://admin.microsoft.com/).</span></span>
2. <span data-ttu-id="8cf2a-135">在 "**活动用户**" 下, 单击 "**添加用户**"。</span><span class="sxs-lookup"><span data-stu-id="8cf2a-135">Under **Active users**, click **Add a user**.</span></span>
3. <span data-ttu-id="8cf2a-136">在 "**新建用户**" 页上, 在\*\*\*\*"名字"、"**显示名称**" 和 "**用户名**" 中键入**DedicatedAdmin** 。</span><span class="sxs-lookup"><span data-stu-id="8cf2a-136">On the **New user** page, type **DedicatedAdmin** in **First name**, **Display name**, and **Username**.</span></span>
4. <span data-ttu-id="8cf2a-137">单击 "**密码**", 单击 "**让我创建密码**", 然后键入一个强密码。</span><span class="sxs-lookup"><span data-stu-id="8cf2a-137">Click **Password**, click **Let me create the password**, and then type a strong password.</span></span> <span data-ttu-id="8cf2a-138">将此新帐户的密码记录在安全位置。</span><span class="sxs-lookup"><span data-stu-id="8cf2a-138">Record the password for this new account in a secure location.</span></span>
5. <span data-ttu-id="8cf2a-139">清除**使此用户在首次登录时更改其密码**。</span><span class="sxs-lookup"><span data-stu-id="8cf2a-139">Clear **Make this user change their password when they first sign in**.</span></span>
6. <span data-ttu-id="8cf2a-140">单击 "**角色**", 然后单击 "**全局管理员**"。</span><span class="sxs-lookup"><span data-stu-id="8cf2a-140">Click **Roles**, and then click **Global administrator**.</span></span>
7. <span data-ttu-id="8cf2a-141">单击 "**产品许可证**", 然后在上打开**企业移动性 + 安全 E5**和**Office 365 企业版 e5 许可证**。</span><span class="sxs-lookup"><span data-stu-id="8cf2a-141">Click **Product licenses**, and then turn the **Enterprise Mobility + Security E5** and **Office 365 Enterprise E5 licenses** on.</span></span>
8. <span data-ttu-id="8cf2a-142">单击“添加”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="8cf2a-142">Click **Add**.</span></span>
9. <span data-ttu-id="8cf2a-143">在 "**添加了用户" 页面**上, 清除 "**在电子邮件中发送密码**", 然后单击 "**关闭**"。</span><span class="sxs-lookup"><span data-stu-id="8cf2a-143">On the **User was added page**, clear **Send password in email**, and then click **Close**.</span></span>

<span data-ttu-id="8cf2a-144">接下来, 创建一个名为 "GlobalAdmins" 的新组, 并向其添加 DedicatedAdmin 帐户。</span><span class="sxs-lookup"><span data-stu-id="8cf2a-144">Next, create a new group named GlobalAdmins and add the DedicatedAdmin account to it.</span></span>

1. <span data-ttu-id="8cf2a-145">在 " **Microsoft 365 管理中心**" 选项卡上, 单击左侧导航栏中的 "组" 图标, 然后单击 "**组**"。</span><span class="sxs-lookup"><span data-stu-id="8cf2a-145">On the **Microsoft 365 admin center** tab, click the groups icon in the left navigation, and then click **Groups**.</span></span>
2. <span data-ttu-id="8cf2a-146">单击 "**添加组**"。</span><span class="sxs-lookup"><span data-stu-id="8cf2a-146">Click **Add a group**.</span></span>
3. <span data-ttu-id="8cf2a-147">在 "**新建组**" 页上, 键入**GlobalAdmins**。</span><span class="sxs-lookup"><span data-stu-id="8cf2a-147">On the **New Group** page, type **GlobalAdmins**.</span></span>
4. <span data-ttu-id="8cf2a-148">单击 "**选择所有者**", 单击全局管理员帐户, 然后单击 "**添加 > 关闭**"。</span><span class="sxs-lookup"><span data-stu-id="8cf2a-148">Click **Select owner** click your global administrator account, and then click **Add > Close**.</span></span>
5. <span data-ttu-id="8cf2a-149">在组列表中, 单击 " **GlobalAdmins** " 组。</span><span class="sxs-lookup"><span data-stu-id="8cf2a-149">In the list of groups, click the **GlobalAdmins** group.</span></span>
6. <span data-ttu-id="8cf2a-150">在 " **GlobalAdmins** " 页上, 单击 "**成员编辑**", 然后单击 "**添加成员**"。</span><span class="sxs-lookup"><span data-stu-id="8cf2a-150">On the **GlobalAdmins** page, click **Edit for Member**, and then click **Add members**.</span></span>
7. <span data-ttu-id="8cf2a-151">在列表中, 单击**DedicatedAdmin**帐户, 然后单击 "**保存 >" 关闭 > "关闭 > 管理中心**"。</span><span class="sxs-lookup"><span data-stu-id="8cf2a-151">In the list, click the **DedicatedAdmin** account, and then click **Save > Close > Close > Admin center**.</span></span>

<span data-ttu-id="8cf2a-152">接下来, 创建条件访问策略以要求对全局管理员帐户进行多因素身份验证, 并在登录风险为 "中" 或 "高" 时拒绝身份验证。</span><span class="sxs-lookup"><span data-stu-id="8cf2a-152">Next, create conditional access policies to require multifactor authentication for global administrator accounts and to deny authentication if the sign-in risk is medium or high.</span></span>

<span data-ttu-id="8cf2a-153">第一个策略要求所有全局管理员帐户使用 MFA。</span><span class="sxs-lookup"><span data-stu-id="8cf2a-153">This first policy requires that all global administrator accounts use MFA.</span></span>

1. <span data-ttu-id="8cf2a-154">在浏览器的新选项卡中, 转[https://portal.azure.com](https://portal.azure.com)到。</span><span class="sxs-lookup"><span data-stu-id="8cf2a-154">In a new tab of your browser, go to [https://portal.azure.com](https://portal.azure.com).</span></span>
2. <span data-ttu-id="8cf2a-155">单击 " **Azure Active Directory > 条件访问**"。</span><span class="sxs-lookup"><span data-stu-id="8cf2a-155">Click **Azure Active Directory > Conditional access**.</span></span>
3. <span data-ttu-id="8cf2a-156">在 "**条件访问–策略**" 边栏选项卡上, 单击 "**基准策略: 要求对管理员进行 MFA (预览)**"。</span><span class="sxs-lookup"><span data-stu-id="8cf2a-156">On the **Conditional access – Policies** blade, click **Baseline policy: Require MFA for admins (preview)**.</span></span>
4. <span data-ttu-id="8cf2a-157">在**基准策略上 ...**</span><span class="sxs-lookup"><span data-stu-id="8cf2a-157">On the **Baseline policies…**</span></span> <span data-ttu-id="8cf2a-158">边栏, 请单击 "**立即使用策略" > "保存**"。</span><span class="sxs-lookup"><span data-stu-id="8cf2a-158">blade, click **Use policy immediately > Save**.</span></span>

<span data-ttu-id="8cf2a-159">当登录风险为 "中" 或 "高" 时, 第二个策略将阻止对全局管理员帐户进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="8cf2a-159">This second policy blocks access to global administrator account authentication when the sign-in risk is medium or high.</span></span>

1. <span data-ttu-id="8cf2a-160">在 "**条件访问–策略**" 边栏选项卡上, 单击 "**新建策略**"。</span><span class="sxs-lookup"><span data-stu-id="8cf2a-160">On the **Conditional access – Policies** blade, click **New policy**.</span></span>
2. <span data-ttu-id="8cf2a-161">在**新**的边栏中, 在 "**名称**" 中键入**全局管理员**。</span><span class="sxs-lookup"><span data-stu-id="8cf2a-161">On the **New** blade, type **Global administrators** in **Name**.</span></span>
3. <span data-ttu-id="8cf2a-162">在 "**工作分配**" 部分, 单击 "**用户和组**"。</span><span class="sxs-lookup"><span data-stu-id="8cf2a-162">In the **Assignments** section, click **Users and groups**.</span></span>
4. <span data-ttu-id="8cf2a-163">在 " \*\*\*\* **用户和组**" 边栏选项卡上的 "用户和组" 选项卡上, 单击 "**选择用户和组" > users and groups > Select**</span><span class="sxs-lookup"><span data-stu-id="8cf2a-163">On the **Include** tab of the **Users and groups** blade, click **Select users and groups > Users and groups > Select**.</span></span>
5. <span data-ttu-id="8cf2a-164">在 "**选择**" 边栏选项卡上, 单击 " **GlobalAdmins" > 选择 "> 完成**"。</span><span class="sxs-lookup"><span data-stu-id="8cf2a-164">On the **Select** blade, click the **GlobalAdmins > Select > Done**.</span></span>
6. <span data-ttu-id="8cf2a-165">在 "**工作分配**" 部分, 单击 "**条件**"。</span><span class="sxs-lookup"><span data-stu-id="8cf2a-165">In the **Assignments** section, click **Conditions**.</span></span>
7. <span data-ttu-id="8cf2a-166">在 "**条件**" 边栏选项卡上, 单击 "**登录风险**", 依次单击 **"是" "** **配置**"、"**高**" 和 "**中**", 然后单击 "**选择**并**完成**"。</span><span class="sxs-lookup"><span data-stu-id="8cf2a-166">On the **Conditions** blade, click **Sign-in risk**, click **Yes** for **Configure**, click **High** and **Medium**, and then click **Select** and **Done**.</span></span>
8. <span data-ttu-id="8cf2a-167">在**新**边栏的 "**访问控制**" 部分, 单击 "**授予**"。</span><span class="sxs-lookup"><span data-stu-id="8cf2a-167">In the **Access controls** section of the **New** blade, click **Grant**.</span></span>
9. <span data-ttu-id="8cf2a-168">在 "**授予**" 边栏选项卡上, 单击 "**阻止访问**", 然后单击 "**选择**"。</span><span class="sxs-lookup"><span data-stu-id="8cf2a-168">On the **Grant** blade, click **Block access**, and then click **Select**.</span></span>
10. <span data-ttu-id="8cf2a-169">在**新**的边栏上, \*\*\*\* 单击 "**启用策略**", 然后单击 "**创建**"。</span><span class="sxs-lookup"><span data-stu-id="8cf2a-169">On the **New** blade, click **On** for **Enable policy**, and then click **Create**.</span></span>
11. <span data-ttu-id="8cf2a-170">关闭 " **Azure 门户**" 和 " **Microsoft 365 管理中心**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="8cf2a-170">Close the **Azure portal** and **Microsoft 365 admin center** tabs.</span></span>

<span data-ttu-id="8cf2a-171">若要测试第一个策略, 请注销并使用 DedicatedAdmin 帐户登录。</span><span class="sxs-lookup"><span data-stu-id="8cf2a-171">To test the first policy, sign out and sign in with the DedicatedAdmin account.</span></span> <span data-ttu-id="8cf2a-172">系统会提示您在用户帐户上配置 MFA。</span><span class="sxs-lookup"><span data-stu-id="8cf2a-172">You should be prompted to configure MFA on the user account.</span></span> <span data-ttu-id="8cf2a-173">这说明正在应用第一个策略。</span><span class="sxs-lookup"><span data-stu-id="8cf2a-173">This demonstrates that the first policy is being applied.</span></span>

<span data-ttu-id="8cf2a-174">请参阅 Identity 阶段中的[保护全局管理员帐户](identity-designate-protect-admin-accounts.md#identity-global-admin)步骤, 以保护您的全局管理员帐户在生产中的信息和链接。</span><span class="sxs-lookup"><span data-stu-id="8cf2a-174">See the [Protect global administrator accounts](identity-designate-protect-admin-accounts.md#identity-global-admin) step in the Identity phase for information and links to protect your global administrator accounts in production.</span></span>

## <a name="next-step"></a><span data-ttu-id="8cf2a-175">后续步骤</span><span class="sxs-lookup"><span data-stu-id="8cf2a-175">Next step</span></span>

<span data-ttu-id="8cf2a-176">在测试环境中探索其他[标识](m365-enterprise-test-lab-guides.md#identity)特性和功能。</span><span class="sxs-lookup"><span data-stu-id="8cf2a-176">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="8cf2a-177">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8cf2a-177">See also</span></span>

[<span data-ttu-id="8cf2a-178">阶段 2：身份</span><span class="sxs-lookup"><span data-stu-id="8cf2a-178">Phase 2: Identity</span></span>](identity-infrastructure.md)

[<span data-ttu-id="8cf2a-179">Microsoft 365 企业版测试实验室指南</span><span class="sxs-lookup"><span data-stu-id="8cf2a-179">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="8cf2a-180">Microsoft 365 企业版部署</span><span class="sxs-lookup"><span data-stu-id="8cf2a-180">Microsoft 365 Enterprise deployment</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="8cf2a-181">Microsoft 365 企业版文档</span><span class="sxs-lookup"><span data-stu-id="8cf2a-181">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
