---
title: 在 Microsoft 365 企业版测试环境中保护全局管理员帐户
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/21/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom:
- TLG
- Ent_TLGs
description: 使用这些步骤来保护 Microsoft 365 企业版测试环境中的全局管理员帐户。
ms.openlocfilehash: 5447177c6581b69d48272ceef7718552ea84dc9d
ms.sourcegitcommit: fb3815ee186b2b3ec790ee32a9d7b1628d623b0b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "39202223"
---
# <a name="protect-global-administrator-accounts-in-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="2c1a0-103">在 Microsoft 365 企业版测试环境中保护全局管理员帐户</span><span class="sxs-lookup"><span data-stu-id="2c1a0-103">Protect global administrator accounts in your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="2c1a0-104">*此测试实验室指南仅可用于 Microsoft 365 企业版测试环境。*</span><span class="sxs-lookup"><span data-stu-id="2c1a0-104">*This Test Lab Guide can only be used for Microsoft 365 Enterprise test environments.*</span></span>

<span data-ttu-id="2c1a0-105">您可以通过确保您的管理员帐户尽可能安全，来阻止组织的数字攻击。</span><span class="sxs-lookup"><span data-stu-id="2c1a0-105">You can prevent digital attacks on your organization by ensuring that your administrator accounts are as secure as possible.</span></span> <span data-ttu-id="2c1a0-106">本文介绍如何使用 Azure Active Directory （Azure AD）条件访问策略来保护全局管理员帐户。</span><span class="sxs-lookup"><span data-stu-id="2c1a0-106">This article describes how to use Azure Active Directory (Azure AD) conditional access policies to protect global administrator accounts.</span></span>

<span data-ttu-id="2c1a0-107">在 Microsoft 365 企业版测试环境中保护全局管理员帐户有两个阶段：</span><span class="sxs-lookup"><span data-stu-id="2c1a0-107">There are two phases to protecting global administrator accounts in your Microsoft 365 Enterprise test environment:</span></span>

1.  <span data-ttu-id="2c1a0-108">创建 Microsoft 365 企业版测试环境。</span><span class="sxs-lookup"><span data-stu-id="2c1a0-108">Create the Microsoft 365 Enterprise test environment.</span></span>
2.  <span data-ttu-id="2c1a0-109">保护您的专用全局管理员帐户。</span><span class="sxs-lookup"><span data-stu-id="2c1a0-109">Protect your dedicated global administrator account.</span></span>

![Microsoft 云测试实验室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="2c1a0-111">单击[此处](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf)，即可获得 Microsoft 365 企业版测试实验室指南堆栈中所有文章的直观目录图。</span><span class="sxs-lookup"><span data-stu-id="2c1a0-111">Click [here](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>

## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="2c1a0-112">阶段 1：构建 Microsoft 365 企业版测试环境。</span><span class="sxs-lookup"><span data-stu-id="2c1a0-112">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="2c1a0-113">如果只想使用最低要求以轻型方式测试全局管理员帐户保护，请按照[轻型基本配置](lightweight-base-configuration-microsoft-365-enterprise.md)中的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="2c1a0-113">If you just want to test global administrator account protection in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="2c1a0-114">如果要在模拟的企业中测试全局管理员帐户保护，请按照[传递身份验证](pass-through-auth-m365-ent-test-environment.md)中的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="2c1a0-114">If you want to test global administrator account protection in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>

  
> [!NOTE]
> <span data-ttu-id="2c1a0-115">测试全局管理员帐户保护不需要模拟企业测试环境，其中包括连接到 Internet 的模拟 intranet 和 Active Directory 域服务（AD DS）的目录同步。</span><span class="sxs-lookup"><span data-stu-id="2c1a0-115">Testing global administrator account protection does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS).</span></span> <span data-ttu-id="2c1a0-116">此处提供它作为选项，以便您可以测试全局管理员帐户保护并在代表典型组织的环境中进行实验。</span><span class="sxs-lookup"><span data-stu-id="2c1a0-116">It is provided here as an option so that you can test global administrator account protection and experiment with it in an environment that represents a typical organization.</span></span> 
  
## <a name="phase-2-configure-conditional-access-policies"></a><span data-ttu-id="2c1a0-117">阶段2：配置条件访问策略</span><span class="sxs-lookup"><span data-stu-id="2c1a0-117">Phase 2: Configure conditional access policies</span></span>

<span data-ttu-id="2c1a0-118">首先，创建一个新的用户帐户作为专用全局管理员。</span><span class="sxs-lookup"><span data-stu-id="2c1a0-118">First, create a new user account as a dedicated global administrator.</span></span>

1. <span data-ttu-id="2c1a0-119">在单独的选项卡上，打开[Microsoft 365 管理中心](https://admin.microsoft.com/)。</span><span class="sxs-lookup"><span data-stu-id="2c1a0-119">On a separate tab, open the [Microsoft 365 admin center](https://admin.microsoft.com/).</span></span>
2. <span data-ttu-id="2c1a0-120">在 "**活动用户**" 下，单击 "**添加用户**"。</span><span class="sxs-lookup"><span data-stu-id="2c1a0-120">Under **Active users**, click **Add a user**.</span></span>
3. <span data-ttu-id="2c1a0-121">在 "**新建用户**" 页上，在 **"名字"**、"**显示名称**" 和 "**用户名**" 中键入**DedicatedAdmin** 。</span><span class="sxs-lookup"><span data-stu-id="2c1a0-121">On the **New user** page, type **DedicatedAdmin** in **First name**, **Display name**, and **Username**.</span></span>
4. <span data-ttu-id="2c1a0-122">单击 "**密码**"，单击 "**让我创建密码**"，然后键入一个强密码。</span><span class="sxs-lookup"><span data-stu-id="2c1a0-122">Click **Password**, click **Let me create the password**, and then type a strong password.</span></span> <span data-ttu-id="2c1a0-123">将此新帐户的密码记录在安全位置。</span><span class="sxs-lookup"><span data-stu-id="2c1a0-123">Record the password for this new account in a secure location.</span></span>
5. <span data-ttu-id="2c1a0-124">清除**使此用户在首次登录时更改其密码**。</span><span class="sxs-lookup"><span data-stu-id="2c1a0-124">Clear **Make this user change their password when they first sign in**.</span></span>
6. <span data-ttu-id="2c1a0-125">单击 "**角色**"，然后单击 "**全局管理员**"。</span><span class="sxs-lookup"><span data-stu-id="2c1a0-125">Click **Roles**, and then click **Global administrator**.</span></span>
7. <span data-ttu-id="2c1a0-126">单击 "**产品许可证**"，然后在上打开**Microsoft 365 E5**许可证。</span><span class="sxs-lookup"><span data-stu-id="2c1a0-126">Click **Product licenses**, and then turn the **Microsoft 365 E5** license on.</span></span>
8. <span data-ttu-id="2c1a0-127">单击“添加”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2c1a0-127">Click **Add**.</span></span>
9. <span data-ttu-id="2c1a0-128">在 "**添加了用户" 页面**上，清除 "**在电子邮件中发送密码**"，然后单击 "**关闭**"。</span><span class="sxs-lookup"><span data-stu-id="2c1a0-128">On the **User was added page**, clear **Send password in email**, and then click **Close**.</span></span>

<span data-ttu-id="2c1a0-129">接下来，创建一个名为 "GlobalAdmins" 的新组，并向其添加 DedicatedAdmin 帐户。</span><span class="sxs-lookup"><span data-stu-id="2c1a0-129">Next, create a new group named GlobalAdmins and add the DedicatedAdmin account to it.</span></span>

1. <span data-ttu-id="2c1a0-130">在 " **Microsoft 365 管理中心**" 选项卡上，单击左侧导航栏中的 "组" 图标，然后单击 "**组**"。</span><span class="sxs-lookup"><span data-stu-id="2c1a0-130">On the **Microsoft 365 admin center** tab, click the groups icon in the left navigation, and then click **Groups**.</span></span>
2. <span data-ttu-id="2c1a0-131">单击 "**添加组**"。</span><span class="sxs-lookup"><span data-stu-id="2c1a0-131">Click **Add a group**.</span></span>
3. <span data-ttu-id="2c1a0-132">在 "**新建组**" 页上，键入**GlobalAdmins**。</span><span class="sxs-lookup"><span data-stu-id="2c1a0-132">On the **New Group** page, type **GlobalAdmins**.</span></span>
4. <span data-ttu-id="2c1a0-133">单击 "**选择所有者**"，单击全局管理员帐户，然后单击 "**添加" > "关闭**"。</span><span class="sxs-lookup"><span data-stu-id="2c1a0-133">Click **Select owner** click your global administrator account, and then click **Add > Close**.</span></span>
5. <span data-ttu-id="2c1a0-134">在组列表中，单击 " **GlobalAdmins** " 组。</span><span class="sxs-lookup"><span data-stu-id="2c1a0-134">In the list of groups, click the **GlobalAdmins** group.</span></span>
6. <span data-ttu-id="2c1a0-135">在 " **GlobalAdmins** " 页上，单击 "**成员编辑**"，然后单击 "**添加成员**"。</span><span class="sxs-lookup"><span data-stu-id="2c1a0-135">On the **GlobalAdmins** page, click **Edit for Member**, and then click **Add members**.</span></span>
7. <span data-ttu-id="2c1a0-136">在列表中，单击 " **DedicatedAdmin** " 帐户，然后单击 "**保存 > 关闭" > 关闭 > 管理中心**"。</span><span class="sxs-lookup"><span data-stu-id="2c1a0-136">In the list, click the **DedicatedAdmin** account, and then click **Save > Close > Close > Admin center**.</span></span>

<span data-ttu-id="2c1a0-137">接下来，创建条件访问策略以要求对全局管理员帐户进行多因素身份验证，并在登录风险为 "中" 或 "高" 时拒绝身份验证。</span><span class="sxs-lookup"><span data-stu-id="2c1a0-137">Next, create conditional access policies to require multifactor authentication for global administrator accounts and to deny authentication if the sign-in risk is medium or high.</span></span>

<span data-ttu-id="2c1a0-138">第一个策略要求所有全局管理员帐户使用 MFA。</span><span class="sxs-lookup"><span data-stu-id="2c1a0-138">This first policy requires that all global administrator accounts use MFA.</span></span>

1. <span data-ttu-id="2c1a0-139">在浏览器的新选项卡中，转[https://portal.azure.com](https://portal.azure.com)到。</span><span class="sxs-lookup"><span data-stu-id="2c1a0-139">In a new tab of your browser, go to [https://portal.azure.com](https://portal.azure.com).</span></span>
2. <span data-ttu-id="2c1a0-140">单击 " **Azure Active Directory > 条件访问**"。</span><span class="sxs-lookup"><span data-stu-id="2c1a0-140">Click **Azure Active Directory > Conditional access**.</span></span>
3. <span data-ttu-id="2c1a0-141">在 "**条件访问–策略**" 边栏选项卡上，单击 "**基准策略：要求对管理员进行 MFA （预览）**"。</span><span class="sxs-lookup"><span data-stu-id="2c1a0-141">On the **Conditional access – Policies** blade, click **Baseline policy: Require MFA for admins (preview)**.</span></span>
4. <span data-ttu-id="2c1a0-142">在**基准策略上 ...**</span><span class="sxs-lookup"><span data-stu-id="2c1a0-142">On the **Baseline policies…**</span></span> <span data-ttu-id="2c1a0-143">边栏，请**立即单击 "使用策略" > 保存**。</span><span class="sxs-lookup"><span data-stu-id="2c1a0-143">blade, click **Use policy immediately > Save**.</span></span>

<span data-ttu-id="2c1a0-144">当登录风险为 "中" 或 "高" 时，第二个策略将阻止对全局管理员帐户进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="2c1a0-144">This second policy blocks access to global administrator account authentication when the sign-in risk is medium or high.</span></span>

1. <span data-ttu-id="2c1a0-145">在 "**条件访问–策略**" 边栏选项卡上，单击 "**新建策略**"。</span><span class="sxs-lookup"><span data-stu-id="2c1a0-145">On the **Conditional access – Policies** blade, click **New policy**.</span></span>
2. <span data-ttu-id="2c1a0-146">在**新**的边栏中，在 "**名称**" 中键入**全局管理员**。</span><span class="sxs-lookup"><span data-stu-id="2c1a0-146">On the **New** blade, type **Global administrators** in **Name**.</span></span>
3. <span data-ttu-id="2c1a0-147">在 "**工作分配**" 部分，单击 "**用户和组**"。</span><span class="sxs-lookup"><span data-stu-id="2c1a0-147">In the **Assignments** section, click **Users and groups**.</span></span>
4. <span data-ttu-id="2c1a0-148">在 "**用户和组**" 边栏的 "**包含**" 选项卡上，单击 "**选择用户和组" > 用户和组 "。 > 选择**。</span><span class="sxs-lookup"><span data-stu-id="2c1a0-148">On the **Include** tab of the **Users and groups** blade, click **Select users and groups > Users and groups > Select**.</span></span>
5. <span data-ttu-id="2c1a0-149">在 "**选择**" 边栏选项卡上，单击 " **GlobalAdmins" > 选择 "> 完成**"。</span><span class="sxs-lookup"><span data-stu-id="2c1a0-149">On the **Select** blade, click the **GlobalAdmins > Select > Done**.</span></span>
6. <span data-ttu-id="2c1a0-150">在 "**工作分配**" 部分，单击 "**条件**"。</span><span class="sxs-lookup"><span data-stu-id="2c1a0-150">In the **Assignments** section, click **Conditions**.</span></span>
7. <span data-ttu-id="2c1a0-151">在 "**条件**" 边栏选项卡上，单击 "**登录风险**"，依次单击 **"是" "** **配置**"、"**高**" 和 "**中**"，然后单击 "**选择**并**完成**"。</span><span class="sxs-lookup"><span data-stu-id="2c1a0-151">On the **Conditions** blade, click **Sign-in risk**, click **Yes** for **Configure**, click **High** and **Medium**, and then click **Select** and **Done**.</span></span>
8. <span data-ttu-id="2c1a0-152">在**新**边栏的 "**访问控制**" 部分，单击 "**授予**"。</span><span class="sxs-lookup"><span data-stu-id="2c1a0-152">In the **Access controls** section of the **New** blade, click **Grant**.</span></span>
9. <span data-ttu-id="2c1a0-153">在 "**授予**" 边栏选项卡上，单击 "**阻止访问**"，然后单击 "**选择**"。</span><span class="sxs-lookup"><span data-stu-id="2c1a0-153">On the **Grant** blade, click **Block access**, and then click **Select**.</span></span>
10. <span data-ttu-id="2c1a0-154">在**新**的边栏上， \*\*\*\* 单击 "**启用策略**"，然后单击 "**创建**"。</span><span class="sxs-lookup"><span data-stu-id="2c1a0-154">On the **New** blade, click **On** for **Enable policy**, and then click **Create**.</span></span>
11. <span data-ttu-id="2c1a0-155">关闭 " **Azure 门户**" 和 " **Microsoft 365 管理中心**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="2c1a0-155">Close the **Azure portal** and **Microsoft 365 admin center** tabs.</span></span>

<span data-ttu-id="2c1a0-156">若要测试第一个策略，请注销并使用 DedicatedAdmin 帐户登录。</span><span class="sxs-lookup"><span data-stu-id="2c1a0-156">To test the first policy, sign out and sign in with the DedicatedAdmin account.</span></span> <span data-ttu-id="2c1a0-157">系统会提示您在用户帐户上配置 MFA。</span><span class="sxs-lookup"><span data-stu-id="2c1a0-157">You should be prompted to configure MFA on the user account.</span></span> <span data-ttu-id="2c1a0-158">这说明正在应用第一个策略。</span><span class="sxs-lookup"><span data-stu-id="2c1a0-158">This demonstrates that the first policy is being applied.</span></span>

<span data-ttu-id="2c1a0-159">请参阅 Identity 阶段中的[保护全局管理员帐户](identity-create-protect-global-admins.md#identity-global-admin)步骤，以保护您的全局管理员帐户在生产中的信息和链接。</span><span class="sxs-lookup"><span data-stu-id="2c1a0-159">See the [Protect global administrator accounts](identity-create-protect-global-admins.md#identity-global-admin) step in the Identity phase for information and links to protect your global administrator accounts in production.</span></span>

## <a name="next-step"></a><span data-ttu-id="2c1a0-160">后续步骤</span><span class="sxs-lookup"><span data-stu-id="2c1a0-160">Next step</span></span>

<span data-ttu-id="2c1a0-161">在测试环境中探索其他[标识](m365-enterprise-test-lab-guides.md#identity)特性和功能。</span><span class="sxs-lookup"><span data-stu-id="2c1a0-161">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="2c1a0-162">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2c1a0-162">See also</span></span>

[<span data-ttu-id="2c1a0-163">阶段 2：标识</span><span class="sxs-lookup"><span data-stu-id="2c1a0-163">Phase 2: Identity</span></span>](identity-infrastructure.md)

[<span data-ttu-id="2c1a0-164">Microsoft 365 企业版测试实验室指南</span><span class="sxs-lookup"><span data-stu-id="2c1a0-164">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="2c1a0-165">Microsoft 365 企业版部署</span><span class="sxs-lookup"><span data-stu-id="2c1a0-165">Microsoft 365 Enterprise deployment</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="2c1a0-166">Microsoft 365 企业版文档</span><span class="sxs-lookup"><span data-stu-id="2c1a0-166">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
