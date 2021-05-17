---
title: 针对企业测试环境Microsoft 365全局管理员帐户
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
description: 使用这些步骤来保护企业测试环境中 Microsoft 365全局管理员帐户。
ms.openlocfilehash: 3eab538b59e460857e2fa195aaacf51051f94d6b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50918878"
---
# <a name="protect-global-administrator-accounts-in-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="70236-103">针对企业测试环境Microsoft 365全局管理员帐户</span><span class="sxs-lookup"><span data-stu-id="70236-103">Protect global administrator accounts in your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="70236-104">*本测试实验室指南只能用于Microsoft 365测试环境。*</span><span class="sxs-lookup"><span data-stu-id="70236-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="70236-105">您可以通过确保管理员帐户尽可能安全来防止对组织的数字攻击。</span><span class="sxs-lookup"><span data-stu-id="70236-105">You can prevent digital attacks on your organization by ensuring that your administrator accounts are as secure as possible.</span></span> 

<span data-ttu-id="70236-106">本文介绍如何使用 Azure AD Azure Active Directory (条件) 保护全局管理员帐户。</span><span class="sxs-lookup"><span data-stu-id="70236-106">This article describes how to use Azure Active Directory (Azure AD) conditional access policies to protect global administrator accounts.</span></span>

<span data-ttu-id="70236-107">在企业测试环境中Microsoft 365全局管理员帐户包括两个阶段：</span><span class="sxs-lookup"><span data-stu-id="70236-107">Protecting global administrator accounts in your Microsoft 365 for enterprise test environment involves two phases:</span></span>
- [<span data-ttu-id="70236-108">第 1 阶段：构建Microsoft 365测试环境</span><span class="sxs-lookup"><span data-stu-id="70236-108">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [<span data-ttu-id="70236-109">阶段 2：配置条件访问策略</span><span class="sxs-lookup"><span data-stu-id="70236-109">Phase 2: Configure conditional access policies</span></span>](#phase-2-configure-conditional-access-policies)

![Microsoft 云测试实验室指南](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="70236-111">有关企业测试实验室指南堆栈中Microsoft 365文章的直观映射，请转到 Microsoft 365[企业测试实验室指南堆栈](../downloads/Microsoft365EnterpriseTLGStack.pdf)。</span><span class="sxs-lookup"><span data-stu-id="70236-111">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>

## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="70236-112">第 1 阶段：构建Microsoft 365测试环境</span><span class="sxs-lookup"><span data-stu-id="70236-112">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="70236-113">如果要使用最低要求的轻型方式测试全局管理员帐户保护，请按照轻型基本配置 [中的说明进行操作](lightweight-base-configuration-microsoft-365-enterprise.md)。</span><span class="sxs-lookup"><span data-stu-id="70236-113">If you want to test global administrator account protection in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="70236-114">如果要在模拟的企业中测试全局管理员帐户保护，请按照传递 [身份验证 中的说明操作](pass-through-auth-m365-ent-test-environment.md)。</span><span class="sxs-lookup"><span data-stu-id="70236-114">If you want to test global administrator account protection in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="70236-115">测试全局管理员帐户保护不需要模拟的企业测试环境，该环境中包括连接到 Internet 的模拟 Intranet 和 Active Directory 域服务 (AD DS) 。</span><span class="sxs-lookup"><span data-stu-id="70236-115">Testing global administrator account protection does not require the simulated enterprise test environment, which includes a simulated intranet connected to the internet and directory synchronization for an Active Directory Domain Services (AD DS).</span></span> <span data-ttu-id="70236-116">它在此处作为一个选项提供，以便你可以测试全局管理员帐户保护，在代表典型组织的环境中试验它。</span><span class="sxs-lookup"><span data-stu-id="70236-116">It is provided here as an option so that you can test global administrator account protection and experiment with it in an environment that represents a typical organization.</span></span> 
  
## <a name="phase-2-configure-conditional-access-policies"></a><span data-ttu-id="70236-117">阶段 2：配置条件访问策略</span><span class="sxs-lookup"><span data-stu-id="70236-117">Phase 2: Configure conditional access policies</span></span>

<span data-ttu-id="70236-118">首先，创建一个新的用户帐户作为专用全局管理员。</span><span class="sxs-lookup"><span data-stu-id="70236-118">First, create a new user account as a dedicated global administrator.</span></span>

1. <span data-ttu-id="70236-119">在单独的选项卡上，打开Microsoft 365[管理中心。](https://admin.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="70236-119">On a separate tab, open the [Microsoft 365 admin center](https://admin.microsoft.com/).</span></span>
2. <span data-ttu-id="70236-120">选择 **"用户**  >  **""** 活动用户"，然后选择"**添加用户"。**</span><span class="sxs-lookup"><span data-stu-id="70236-120">Select **Users** > **Active users**, and then select **Add a user**.</span></span>
3. <span data-ttu-id="70236-121">在"**添加用户"** 窗格中，在"名字"、"显示名称"和"用户名"框中输入 **DedicatedAdmin。** </span><span class="sxs-lookup"><span data-stu-id="70236-121">In the **Add user** pane, enter **DedicatedAdmin** in the **First name**, **Display name**, and **Username** boxes.</span></span>
4. <span data-ttu-id="70236-122">选择 **"密码\*\*\*\*"，选择"允许我创建密码**"，然后输入强密码。</span><span class="sxs-lookup"><span data-stu-id="70236-122">Select **Password**, select **Let me create the password**, and then enter a strong password.</span></span> <span data-ttu-id="70236-123">在安全位置记录此新帐户的密码。</span><span class="sxs-lookup"><span data-stu-id="70236-123">Record the password for this new account in a secure location.</span></span>
5. <span data-ttu-id="70236-124">选择“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="70236-124">Select **Next**.</span></span>
6. <span data-ttu-id="70236-125">在"**分配产品许可证**"窗格中，选择 **"Microsoft 365 E5"，** 然后选择"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="70236-125">In the **Assign product licenses** pane, select **Microsoft 365 E5**, and then select **Next**.</span></span>
7. <span data-ttu-id="70236-126">在"**可选设置"窗格中**，选择"**角色**  >  **""管理中心""访问**  >  **全局管理员""下一**  >  **步"。**</span><span class="sxs-lookup"><span data-stu-id="70236-126">In the **Optional settings** pane, select **Roles** > **Admin center access** > **Global admin** > **Next**.</span></span>
8. <span data-ttu-id="70236-127">在"**你已完成"窗格中**，选择"**完成添加"，** 然后选择"关闭 **"。**</span><span class="sxs-lookup"><span data-stu-id="70236-127">On the **You're almost done** pane, select **Finish adding**, and then select **Close**.</span></span>

<span data-ttu-id="70236-128">接下来，创建一个名为 GlobalAdmins 的新组，并添加 DedicatedAdmin 帐户。</span><span class="sxs-lookup"><span data-stu-id="70236-128">Next, create a new group named GlobalAdmins and add the DedicatedAdmin account to it.</span></span>

1. <span data-ttu-id="70236-129">在 **"Microsoft 365中心"** 选项卡上，选择左侧导航中的"组"，然后选择"组 **"。**</span><span class="sxs-lookup"><span data-stu-id="70236-129">On the **Microsoft 365 admin center** tab, select **Groups** in the left navigation, and then select **Groups**.</span></span>
2. <span data-ttu-id="70236-130">选择 **"添加组"。**</span><span class="sxs-lookup"><span data-stu-id="70236-130">Select **Add a group**.</span></span>
3. <span data-ttu-id="70236-131">在"**选择组类型"窗格中**，选择"**安全性"，** 然后选择"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="70236-131">In the **Choose a group type** pane, select **Security**, and then select **Next**.</span></span>
4. <span data-ttu-id="70236-132">在"**设置基础知识"窗格中**，选择"**创建组**"，然后选择"关闭 **"。**</span><span class="sxs-lookup"><span data-stu-id="70236-132">In the **Set up the basics** pane, select **Create group**, and then select **Close**.</span></span>
5. <span data-ttu-id="70236-133">在"**查看并完成添加组"窗格中**，输入 **GlobalAdmins，** 然后选择"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="70236-133">In the **Review and finish adding group** pane, enter **GlobalAdmins**, and then select **Next**.</span></span>
7. <span data-ttu-id="70236-134">在组列表中，选择 **GlobalAdmins** 组。</span><span class="sxs-lookup"><span data-stu-id="70236-134">In the list of groups, select the **GlobalAdmins** group.</span></span>
8. <span data-ttu-id="70236-135">在"**全局管理"窗格中**，选择"成员 **"，** 然后选择"**查看所有和管理成员"。**</span><span class="sxs-lookup"><span data-stu-id="70236-135">In the **GlobalAdmins** pane, select **Members**, and then select **View all and manage members**.</span></span>
9. <span data-ttu-id="70236-136">在 **GlobalAdmins** 窗格中，选择"**添加** 成员"，选择 **DedicatedAdmin** 帐户和全局管理员帐户，然后选择 **"保存**  >  **关闭关闭**  >  **"。**</span><span class="sxs-lookup"><span data-stu-id="70236-136">In the **GlobalAdmins** pane, select **Add members**, select the **DedicatedAdmin** account and your global admin account, and then select **Save** > **Close** > **Close**.</span></span>

<span data-ttu-id="70236-137">接下来，创建条件访问策略，要求对全局管理员帐户进行多重身份验证，如果登录风险为中或高，则拒绝身份验证。</span><span class="sxs-lookup"><span data-stu-id="70236-137">Next, create conditional access policies to require multi-factor authentication for global administrator accounts and to deny authentication if the sign-in risk is medium or high.</span></span>

<span data-ttu-id="70236-138">此第一个策略要求所有全局管理员帐户都使用 MFA。</span><span class="sxs-lookup"><span data-stu-id="70236-138">This first policy requires that all global administrator accounts use MFA.</span></span>

1. <span data-ttu-id="70236-139">在浏览器的新选项卡中，转到 [https://portal.azure.com](https://portal.azure.com) 。</span><span class="sxs-lookup"><span data-stu-id="70236-139">In a new tab of your browser, go to [https://portal.azure.com](https://portal.azure.com).</span></span>
2. <span data-ttu-id="70236-140">单击 **Azure Active Directory**  >  **安全**  >  **条件访问"。**</span><span class="sxs-lookup"><span data-stu-id="70236-140">Click **Azure Active Directory** > **Security** > **Conditional Access**.</span></span>
3. <span data-ttu-id="70236-141">在"**条件访问 – 策略"** 窗格中，选择"**基线策略： 要求管理员使用 MFA (预览) "。**</span><span class="sxs-lookup"><span data-stu-id="70236-141">In the **Conditional access – Policies** pane, select **Baseline policy: Require MFA for admins (preview)**.</span></span>
4. <span data-ttu-id="70236-142">在"**基线策略"** 窗格中，选择"立即 **使用策略>保存"。**</span><span class="sxs-lookup"><span data-stu-id="70236-142">In the **Baseline policy** pane, select **Use policy immediately > Save**.</span></span>

<span data-ttu-id="70236-143">当登录风险为中或高时，第二个策略将阻止访问全局管理员帐户身份验证。</span><span class="sxs-lookup"><span data-stu-id="70236-143">This second policy blocks access to global administrator account authentication when the sign-in risk is medium or high.</span></span>

1. <span data-ttu-id="70236-144">在"**条件访问 – 策略"** 窗格中，选择"**新建策略"。**</span><span class="sxs-lookup"><span data-stu-id="70236-144">In the **Conditional access – Policies** pane, select **New policy**.</span></span>
2. <span data-ttu-id="70236-145">在"**新建"** 窗格中，在"**名称"中输入"全局\*\*\*\*管理员"。**</span><span class="sxs-lookup"><span data-stu-id="70236-145">In the **New** pane, enter **Global administrators** in **Name**.</span></span>
3. <span data-ttu-id="70236-146">在"**分配"** 部分，选择"**用户和组"。**</span><span class="sxs-lookup"><span data-stu-id="70236-146">In the **Assignments** section, select **Users and groups**.</span></span>
4. <span data-ttu-id="70236-147">在"**用户和** 组"**窗格** 的"包含"选项卡上，选择 **"选择用户和组**  >  **用户和组**  >  **"选择**。</span><span class="sxs-lookup"><span data-stu-id="70236-147">On the **Include** tab of the **Users and groups** pane, select **Select users and groups** > **Users and groups** > **Select**.</span></span>
5. <span data-ttu-id="70236-148">在"**选择**"窗格中，选择 **"GlobalAdmins"** 组，然后选择"**选择完成**  >  **"。**</span><span class="sxs-lookup"><span data-stu-id="70236-148">In the **Select** pane, select the **GlobalAdmins** group, and then select **Select** > **Done**.</span></span>
6. <span data-ttu-id="70236-149">在"**分配"** 部分，选择"条件 **"。**</span><span class="sxs-lookup"><span data-stu-id="70236-149">In the **Assignments** section, select **Conditions**.</span></span>
7. <span data-ttu-id="70236-150">在"**条件"** 窗格中，选择"**登录风险**"，为"配置"选择"是"，选择"高"和"中等"，然后选择"**选择** 并 **完成"。** </span><span class="sxs-lookup"><span data-stu-id="70236-150">In the **Conditions** pane, select **Sign-in risk**, select **Yes** for **Configure**, select **High** and **Medium**, and then select **Select** and **Done**.</span></span>
8. <span data-ttu-id="70236-151">在"**新建"窗格** 的"访问控制"**部分**，选择"授予 **"。**</span><span class="sxs-lookup"><span data-stu-id="70236-151">In the **Access controls** section of the **New** pane, select **Grant**.</span></span>
9. <span data-ttu-id="70236-152">在"**授予"窗格中**，选择 **"阻止访问**"，然后选择"选择 **"。**</span><span class="sxs-lookup"><span data-stu-id="70236-152">In the **Grant** pane, select **Block access**, and then select **Select**.</span></span>
10. <span data-ttu-id="70236-153">在"**新建"** 窗格中，为"启用策略"选择 **"打开\*\*\*\*"，** 然后选择"创建 **"。**</span><span class="sxs-lookup"><span data-stu-id="70236-153">In the **New** pane, select **On** for **Enable policy**, and then select **Create**.</span></span>
11. <span data-ttu-id="70236-154">关闭 **Azure 门户，Microsoft 365\*\*\*\*管理中心** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="70236-154">Close the **Azure portal** and **Microsoft 365 admin center** tabs.</span></span>

<span data-ttu-id="70236-155">若要测试第一个策略，请注销，然后使用 DedicatedAdmin 帐户登录。</span><span class="sxs-lookup"><span data-stu-id="70236-155">To test the first policy, sign out and sign in with the DedicatedAdmin account.</span></span> <span data-ttu-id="70236-156">系统将提示你配置 MFA。</span><span class="sxs-lookup"><span data-stu-id="70236-156">You should be prompted to configure MFA.</span></span> <span data-ttu-id="70236-157">这演示了正在应用第一个策略。</span><span class="sxs-lookup"><span data-stu-id="70236-157">This demonstrates that the first policy is being applied.</span></span>

## <a name="next-step"></a><span data-ttu-id="70236-158">后续步骤</span><span class="sxs-lookup"><span data-stu-id="70236-158">Next step</span></span>

<span data-ttu-id="70236-159">在测试环境中探索其他[标识](m365-enterprise-test-lab-guides.md#identity)特性和功能。</span><span class="sxs-lookup"><span data-stu-id="70236-159">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="70236-160">另请参阅</span><span class="sxs-lookup"><span data-stu-id="70236-160">See also</span></span>

[<span data-ttu-id="70236-161">标识路线图</span><span class="sxs-lookup"><span data-stu-id="70236-161">Identity roadmap</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="70236-162">Microsoft 365 企业版测试实验室指南</span><span class="sxs-lookup"><span data-stu-id="70236-162">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="70236-163">Microsoft 365 企业版概述</span><span class="sxs-lookup"><span data-stu-id="70236-163">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="70236-164">适用于企业的 Microsoft 365 文档</span><span class="sxs-lookup"><span data-stu-id="70236-164">Microsoft 365 for enterprise documentation</span></span>](/microsoft-365-enterprise/)