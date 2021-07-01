---
title: 在开发/测试环境中配置具有安全隔离的团队
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 08/14/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- remotework
ms.custom: ''
description: 配置安全性和基础结构，使你的员工能够随时随地远程工作。
ms.openlocfilehash: c58f0849937d7a807c9969e1651c51b3a9470ba5
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/30/2021
ms.locfileid: "53228599"
---
# <a name="configure-a-team-with-security-isolation-in-a-devtest-environment"></a><span data-ttu-id="56d2c-103">在开发/测试环境中配置具有安全隔离的团队</span><span class="sxs-lookup"><span data-stu-id="56d2c-103">Configure a team with security isolation in a dev/test environment</span></span>

<span data-ttu-id="56d2c-104">本文提供了在开发/测试环境中创建[具有安全隔离的团队](secure-teams-security-isolation.md)的分步式说明。</span><span class="sxs-lookup"><span data-stu-id="56d2c-104">This article provides step-by-step instructions to create a [team with security isolation](secure-teams-security-isolation.md) in a dev/test environment.</span></span>

![公司战略隔离团队的配置](../media/team-security-isolation-dev-test/team-security-isolation-dev-test-config.png)

<span data-ttu-id="56d2c-106">在生产中部署此类团队前，可使用此开发/测试环境试验和微调设置以满足你的特定需求。</span><span class="sxs-lookup"><span data-stu-id="56d2c-106">Use this dev/test environment to experiment and fine-tune settings for your specific needs before deploying this type of team in production.</span></span>

## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="56d2c-107">阶段 1：构建 Microsoft 365 企业版测试环境。</span><span class="sxs-lookup"><span data-stu-id="56d2c-107">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="56d2c-108">如果只需要测试达到最低要求的轻型敏感和高度敏感团队，请按照[轻型基本配置](../enterprise/lightweight-base-configuration-microsoft-365-enterprise.md)中的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="56d2c-108">If you just want to test sensitive and highly sensitive teams in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](../enterprise/lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>

<span data-ttu-id="56d2c-109">如果想要在模拟企业中测试敏感和高度敏感的团队，请按照[密码哈希同步](../enterprise/password-hash-sync-m365-ent-test-environment.md)中的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="56d2c-109">If you want to test sensitive and highly sensitive teams in a simulated enterprise, follow the instructions in [Password hash synchronization](../enterprise/password-hash-sync-m365-ent-test-environment.md).</span></span>

> [!NOTE]
> <span data-ttu-id="56d2c-110">测试具有安全隔离的团队不需要模拟的企业测试环境，该环境中包括连接到 Internet 的模拟内部网和  Active Directory Domain Services (AD DS) 资源林的目录同步。</span><span class="sxs-lookup"><span data-stu-id="56d2c-110">Testing a team with security isolation does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="56d2c-111">它在此处作为一个选项提供，以便你可以测试具有安全隔离的团队，并在代表典型组织的环境中对其进行试验。</span><span class="sxs-lookup"><span data-stu-id="56d2c-111">It is provided here as an option so that you can test a team with security isolation and experiment with it in an environment that represents a typical organization.</span></span>

## <a name="phase-2-create-and-configure-your-azure-active-directory-azure-ad-group-and-users"></a><span data-ttu-id="56d2c-112">第 2 阶段：创建和配置你的 Azure Active Directory (Azure AD)  组和用户。</span><span class="sxs-lookup"><span data-stu-id="56d2c-112">Phase 2: Create and configure your Azure Active Directory (Azure AD) group and users</span></span>

<span data-ttu-id="56d2c-113">此阶段为虚构组织创建和配置 Azure AD 组和用户。</span><span class="sxs-lookup"><span data-stu-id="56d2c-113">In this phase, you create and configure an Azure AD group and users for your fictional organization.</span></span>

<span data-ttu-id="56d2c-114">首先，使用 Azure 门户创建一个安全组。</span><span class="sxs-lookup"><span data-stu-id="56d2c-114">First, create a security group with the Azure portal.</span></span>

1. <span data-ttu-id="56d2c-115">在浏览器中创建单独的选项卡，然后转到 Azure 门户，网址为 [https://portal.azure.com](https://portal.azure.com)。</span><span class="sxs-lookup"><span data-stu-id="56d2c-115">Create a separate tab in your browser, and then go to the Azure portal at [https://portal.azure.com](https://portal.azure.com).</span></span> <span data-ttu-id="56d2c-116">如有需要，请使用 Microsoft 365 E5 试用或已付款订阅的全局管理员帐户凭据登录。</span><span class="sxs-lookup"><span data-stu-id="56d2c-116">If needed, sign in with the credentials of the global administrator account for your Microsoft 365 E5 trial or paid subscription.</span></span>

2. <span data-ttu-id="56d2c-117">在 Azure 门户中，单击“**Azure Active Directory”>“组**”。</span><span class="sxs-lookup"><span data-stu-id="56d2c-117">In the Azure portal, click **Azure Active Directory > Groups**.</span></span>

3. <span data-ttu-id="56d2c-118">在“**组 - 所有组**”边栏选项卡上，单击“**+ 新建组**”。</span><span class="sxs-lookup"><span data-stu-id="56d2c-118">On the **Groups - All groups** blade, click **+ New group**.</span></span>

4. <span data-ttu-id="56d2c-119">在“**组**”边栏选项卡上：</span><span class="sxs-lookup"><span data-stu-id="56d2c-119">On the **Group** blade:</span></span>

  - <span data-ttu-id="56d2c-120">在“组类型”中选择“安全性”。</span><span class="sxs-lookup"><span data-stu-id="56d2c-120">Select **Security** in **Group type**.</span></span>

  - <span data-ttu-id="56d2c-121">在“**名称**”中键入 **高层管理人员**。</span><span class="sxs-lookup"><span data-stu-id="56d2c-121">Type **C-Suite** in **Name**.</span></span>

  - <span data-ttu-id="56d2c-122">在“**成员身份**”类型中，选择“**已分配**”。</span><span class="sxs-lookup"><span data-stu-id="56d2c-122">Select **Assigned** in **Membership type**.</span></span>

5. <span data-ttu-id="56d2c-123">单击“**创建**”，然后关闭“**组**”边栏选项卡。</span><span class="sxs-lookup"><span data-stu-id="56d2c-123">Click **Create**, and then close the **Group** blade.</span></span>

<span data-ttu-id="56d2c-124">接下来，配置自动许可，使新的“**高层管理人员**”组的成员可以自动分配 Microsoft 365 E5 许可。</span><span class="sxs-lookup"><span data-stu-id="56d2c-124">Next, configure automatic licensing so that members of the new **C-Suite** group are automatically assigned a Microsoft 365 E5 license.</span></span>

1. <span data-ttu-id="56d2c-125">在 Azure 门户中，单击“Azure Active Directory”>“许可证”>“所有产品”。</span><span class="sxs-lookup"><span data-stu-id="56d2c-125">In the Azure portal, click **Azure Active Directory > Licenses > All products**.</span></span>

2. <span data-ttu-id="56d2c-126">在列表中，选择“Microsoft 365 企业版 E5”，然后单击“分配”。</span><span class="sxs-lookup"><span data-stu-id="56d2c-126">In the list, select **Microsoft 365 Enterprise E5**, and then click **Assign**.</span></span>

3. <span data-ttu-id="56d2c-127">在“**分配许可证**”边栏选项卡中，单击“**用户和组**”。</span><span class="sxs-lookup"><span data-stu-id="56d2c-127">In the **Assign license** blade, click **Users and groups**.</span></span>

4. <span data-ttu-id="56d2c-128">在组列表中，选择“**高层管理人员**”组。</span><span class="sxs-lookup"><span data-stu-id="56d2c-128">In the list of groups, select the **C-Suite** group.</span></span>

5. <span data-ttu-id="56d2c-129">单击“**选择**”，然后单击“**分配**”。</span><span class="sxs-lookup"><span data-stu-id="56d2c-129">Click **Select**, and then click **Assign**.</span></span>

6. <span data-ttu-id="56d2c-130">关闭浏览器中的 Azure 门户选项卡。</span><span class="sxs-lookup"><span data-stu-id="56d2c-130">Close the Azure portal tab in your browser.</span></span>

<span data-ttu-id="56d2c-131">接下来，[连接到 Azure Active Directory PowerShell for Graph 模块](../enterprise/connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)。</span><span class="sxs-lookup"><span data-stu-id="56d2c-131">Next, [connect with the Azure Active Directory PowerShell for Graph module](../enterprise/connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>

<span data-ttu-id="56d2c-132">填写组织名称、位置和公用密码并从 PowerShell 命令提示符或集成脚本环境 (ISE) 中运行以下命令，创建新的用户帐户并将其添加到相应的高层管理人员组：</span><span class="sxs-lookup"><span data-stu-id="56d2c-132">Fill in your organization name, your location, and a common password, and then run these commands from the PowerShell command prompt or Integrated Script Environment (ISE) to create new user accounts and add them to the C-Suite group:</span></span>

```powershell
$orgName="<organization name, such as contoso-test for the contoso-test.onmicrosoft.com trial subscription domain name>"
$location="<the ISO ALPHA2 country code, such as US for the United States>"
$commonPassword="<common password for all the new accounts>"

$PasswordProfile=New-Object -TypeName Microsoft.Open.AzureAD.Model.PasswordProfile
$PasswordProfile.Password=$commonPassword

$groupName="C-Suite"
$userNames=@("CEO","CFO","CIO")
$groupID=(Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
ForEach ($element in $userNames){
New-AzureADUser -DisplayName $element -PasswordProfile $PasswordProfile -UserPrincipalName ($element + "@" + $orgName + ".onmicrosoft.com") -AccountEnabled $true -MailNickName $element -UsageLocation $location
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $element }).ObjectID -ObjectId $groupID
}
```

> [!NOTE]
> <span data-ttu-id="56d2c-p103">此处使用公用密码旨在自动配置开发/测试环境，简化配置过程。 但不建议生产订阅这样做。</span><span class="sxs-lookup"><span data-stu-id="56d2c-p103">The use of a common password here is for automation and ease of configuration for a dev/test environment. Obviously, this is highly discouraged for production subscriptions.</span></span>

<span data-ttu-id="56d2c-135">请按照以下步骤验证基于组的许可是否正常工作。</span><span class="sxs-lookup"><span data-stu-id="56d2c-135">Use these steps to verify that group-based licensing is working correctly.</span></span>

1. <span data-ttu-id="56d2c-136">登录到 [Microsoft 365 管理中心](https://admin.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="56d2c-136">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com).</span></span>

2. <span data-ttu-id="56d2c-137">在浏览器的新“**Microsoft 365 管理中心**”标签页中，单击“**用户**”。</span><span class="sxs-lookup"><span data-stu-id="56d2c-137">From the new **Microsoft 365 admin center** tab of your browser, click **Users**.</span></span>

3. <span data-ttu-id="56d2c-138">在用户列表中，单击“CEO”。</span><span class="sxs-lookup"><span data-stu-id="56d2c-138">In the list of users, click **CEO**.</span></span>

4. <span data-ttu-id="56d2c-139">在列出“**CEO**”用户帐户属性的窗格中，验证是否已向其分配“**Microsoft 365 企业版 E5**”许可证（位于“**产品许可证**”中）。</span><span class="sxs-lookup"><span data-stu-id="56d2c-139">In the pane that lists the properties of the **CEO** user account, verify that it has been assigned the **Microsoft 365 Enterprise E5** license in **Product licenses**.</span></span>

## <a name="phase-3-create-your-team"></a><span data-ttu-id="56d2c-140">阶段 3：创建团队</span><span class="sxs-lookup"><span data-stu-id="56d2c-140">Phase 3: Create your team</span></span>

<span data-ttu-id="56d2c-141">在此阶段中，可为高级领导团队的成员创建和配置具有安全隔离的团队，以便协作处理公司战略。</span><span class="sxs-lookup"><span data-stu-id="56d2c-141">In this phase, you create and configure a team with security isolation for members of the senior leadership team to collaborate on company strategy.</span></span>

<span data-ttu-id="56d2c-142">首先，在继续执行[本文](../compliance/sensitivity-labels-teams-groups-sites.md)中的步骤之前，先启用敏感度标签来保护 Microsoft Teams、Office 365 组和 SharePoint 网站中的内容。</span><span class="sxs-lookup"><span data-stu-id="56d2c-142">First, enable sensitivity labels to protect content in Microsoft Teams, Office 365 groups, and SharePoint sites before you proceed with the steps in [this article](../compliance/sensitivity-labels-teams-groups-sites.md).</span></span>

<span data-ttu-id="56d2c-143">接下来，创建团队：</span><span class="sxs-lookup"><span data-stu-id="56d2c-143">Next, create the team:</span></span>

1. <span data-ttu-id="56d2c-144">在 Teams 中，单击应用程序左侧的“**团队**”，然后在团队列表底部单击“**加入或创建团队**”。</span><span class="sxs-lookup"><span data-stu-id="56d2c-144">In Teams, click **Teams** on the left side of the app, then click **Join or create a team** at the bottom of the teams list.</span></span>
2. <span data-ttu-id="56d2c-145">点击“**创建团队**”（第一张卡片，左上角）。</span><span class="sxs-lookup"><span data-stu-id="56d2c-145">Click **Create team** (first card, top left corner).</span></span>
3. <span data-ttu-id="56d2c-146">选择“**从头开始构建团队**”。</span><span class="sxs-lookup"><span data-stu-id="56d2c-146">Choose **Build a team from scratch**.</span></span>
4. <span data-ttu-id="56d2c-147">在“**敏感度**”列表中，保留默认值。</span><span class="sxs-lookup"><span data-stu-id="56d2c-147">In the **Sensitivity** list, keep the default.</span></span>
5. <span data-ttu-id="56d2c-148">在“**隐私**”下，单击“**专用**”。</span><span class="sxs-lookup"><span data-stu-id="56d2c-148">Under **Privacy**, click **Private**.</span></span>
6. <span data-ttu-id="56d2c-149">键入 **公司战略**，然后单击“**创建**” > “**关闭**”。</span><span class="sxs-lookup"><span data-stu-id="56d2c-149">Type **Company Strategy**, and then click **Create** > **Close**.</span></span>

<span data-ttu-id="56d2c-150">接下来，限制公司战略组的所有者建立私人渠道。</span><span class="sxs-lookup"><span data-stu-id="56d2c-150">Next, restrict the creation of private channels to owners of the Company Strategy group.</span></span>

1. <span data-ttu-id="56d2c-151">在团队中，单击“**更多选项**”，然后单击“**管理团队**”。</span><span class="sxs-lookup"><span data-stu-id="56d2c-151">In the team, click **More options**, and then click **Manage team**.</span></span>
2. <span data-ttu-id="56d2c-152">在“**设置**”选项卡上，展开“**成员权限**”。</span><span class="sxs-lookup"><span data-stu-id="56d2c-152">On the **Settings** tab, expand **Member permissions**.</span></span>
3. <span data-ttu-id="56d2c-153">清除“**允许成员创建专用频道**”复选框。</span><span class="sxs-lookup"><span data-stu-id="56d2c-153">Clear the **Allow members to create private channels** check box.</span></span>

<span data-ttu-id="56d2c-154">下一步，你需要用以下设置配置灵敏度标签：</span><span class="sxs-lookup"><span data-stu-id="56d2c-154">Next, you need to configure a sensitivity label with the following settings:</span></span>

- <span data-ttu-id="56d2c-155">名称为“公司战略”</span><span class="sxs-lookup"><span data-stu-id="56d2c-155">The name is Company Strategy</span></span>
- <span data-ttu-id="56d2c-156">启用加密</span><span class="sxs-lookup"><span data-stu-id="56d2c-156">Encryption is enabled</span></span>
- <span data-ttu-id="56d2c-157">公司战略组具有共同创作权限</span><span class="sxs-lookup"><span data-stu-id="56d2c-157">The Company Strategy group has Co-Author permissions</span></span>

<span data-ttu-id="56d2c-158">请按以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="56d2c-158">Follow these steps:</span></span>

1. <span data-ttu-id="56d2c-159">打开 [Microsoft 365 合规中心](https://compliance.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="56d2c-159">Open the [Microsoft 365 compliance center](https://compliance.microsoft.com).</span></span>
2. <span data-ttu-id="56d2c-160">在“**解决方案**”下，单击“**信息保护**”。</span><span class="sxs-lookup"><span data-stu-id="56d2c-160">Under **Solutions**, click **Information protection**.</span></span>
3. <span data-ttu-id="56d2c-161">单击“**创建标签**”。</span><span class="sxs-lookup"><span data-stu-id="56d2c-161">Click **Create a label**.</span></span>
4. <span data-ttu-id="56d2c-162">为标签名称键入 **公司战略**。</span><span class="sxs-lookup"><span data-stu-id="56d2c-162">Type **Company Strategy** for the label name.</span></span>
5. <span data-ttu-id="56d2c-163">键入 **高级领导公司战略文档** 作为工具提示，然后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="56d2c-163">Type **Senior leadership company strategy documents** as the tool tip, and then click **Next**.</span></span>
6. <span data-ttu-id="56d2c-164">在“**加密**”页面上的“**加密**”下拉列表中，选择“**应用**”。</span><span class="sxs-lookup"><span data-stu-id="56d2c-164">On the **Encryption** page, in the **Encryption** dropdown, choose **Apply**.</span></span>
7. <span data-ttu-id="56d2c-165">添加团队权限：</span><span class="sxs-lookup"><span data-stu-id="56d2c-165">To add the team permissions:</span></span><br>
  <span data-ttu-id="56d2c-166">a.</span><span class="sxs-lookup"><span data-stu-id="56d2c-166">a.</span></span> <span data-ttu-id="56d2c-167">单击“**分配权限**”。</span><span class="sxs-lookup"><span data-stu-id="56d2c-167">Click **Assign permissions**.</span></span><br>
  <span data-ttu-id="56d2c-168">b.</span><span class="sxs-lookup"><span data-stu-id="56d2c-168">b.</span></span> <span data-ttu-id="56d2c-169">单击“**添加用户或组**”，选择“**公司战略**”，然后单击“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="56d2c-169">Click **Add users or groups**, select **Company Strategy**, and then click **Add**.</span></span><br>
  <span data-ttu-id="56d2c-170">c.</span><span class="sxs-lookup"><span data-stu-id="56d2c-170">c.</span></span> <span data-ttu-id="56d2c-171">单击“**选择权限**”。</span><span class="sxs-lookup"><span data-stu-id="56d2c-171">Click **Choose permissions**.</span></span><br>
  <span data-ttu-id="56d2c-172">d.</span><span class="sxs-lookup"><span data-stu-id="56d2c-172">d.</span></span> <span data-ttu-id="56d2c-173">从下拉列表中选择“**共同创作**”，然后单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="56d2c-173">Choose **Co-Author** from the dropdown list, and then click **Save**.</span></span><br>
8. <span data-ttu-id="56d2c-174">单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="56d2c-174">Click **Next**.</span></span>
9. <span data-ttu-id="56d2c-175">在“**内容标记**”页面上，单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="56d2c-175">On the **Content marking** page, click **Next**.</span></span>
10. <span data-ttu-id="56d2c-176">在“**网站和组设置**”页面上，将“**网站和组设置**”设置为“**开**”。</span><span class="sxs-lookup"><span data-stu-id="56d2c-176">On the **Site and group settings** page, set **Site and group settings** to **On**.</span></span>
11. <span data-ttu-id="56d2c-177">在“**连接了 Office 365 组的团队网站的隐私**”下拉菜单中，选择“**专用 - 仅成员可访问站点**”。</span><span class="sxs-lookup"><span data-stu-id="56d2c-177">In the **Privacy of Office 365 group-connected team sites** dropdown, choose **Private - only members can access the site**.</span></span>
12. <span data-ttu-id="56d2c-178">在“**非托管的设备**”下，选择“**阻止访问**”。</span><span class="sxs-lookup"><span data-stu-id="56d2c-178">Under **Unmanaged devices**, choose **Block access**.</span></span>
13. <span data-ttu-id="56d2c-179">单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="56d2c-179">Click **Next**.</span></span>
14. <span data-ttu-id="56d2c-180">在“**Office 应用程序自动标记**”页面上，单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="56d2c-180">On the **Auto-labeling for Office apps** page, click **Next**.</span></span>
15. <span data-ttu-id="56d2c-181">单击“**提交**”，然后单击“**完成**”。</span><span class="sxs-lookup"><span data-stu-id="56d2c-181">Click **Submit**, and then click **Done**.</span></span>

<span data-ttu-id="56d2c-182">接下来，按照以下步骤发布新标签：</span><span class="sxs-lookup"><span data-stu-id="56d2c-182">Next, publish the new label with these steps:</span></span>

1. <span data-ttu-id="56d2c-183">在 Microsoft 365 合规中心的“**信息保护**”页面上，选择“**标签策略**”选项卡。</span><span class="sxs-lookup"><span data-stu-id="56d2c-183">In the Microsoft 365 compliance center, on the **Information protection** page, choose the **Label policies** tab.</span></span>
2. <span data-ttu-id="56d2c-184">单击“**发布标签**”。</span><span class="sxs-lookup"><span data-stu-id="56d2c-184">Click **Publish labels**.</span></span>
3. <span data-ttu-id="56d2c-185">在“**选择要发布的敏感度标签**”页面上，单击“**选择要发布的敏感度标签**”。</span><span class="sxs-lookup"><span data-stu-id="56d2c-185">On the **Choose sensitivity labels to publish** page, click **Choose sensitivity labels to publish**.</span></span>
4. <span data-ttu-id="56d2c-186">选择“**公司战略**”，然后单击“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="56d2c-186">Select **Company Strategy**, and then click **Add**.</span></span>
5. <span data-ttu-id="56d2c-187">单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="56d2c-187">Click **Next**.</span></span>
6. <span data-ttu-id="56d2c-188">在“**发布到用户和组**”页面上，单击“**选择用户和组**”。</span><span class="sxs-lookup"><span data-stu-id="56d2c-188">On the **Publish to users and groups** page, click **Choose users and groups**.</span></span>
7. <span data-ttu-id="56d2c-189">单击“**添加**”，然后选择“**公司策略**”。</span><span class="sxs-lookup"><span data-stu-id="56d2c-189">Click **Add**, and then select **Company Strategy**.</span></span>
8. <span data-ttu-id="56d2c-190">单击“**添加**”，然后单击“**完成**”。</span><span class="sxs-lookup"><span data-stu-id="56d2c-190">Click **Add**, and then click **Done**.</span></span>
9. <span data-ttu-id="56d2c-191">单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="56d2c-191">Click **Next**.</span></span>
10. <span data-ttu-id="56d2c-192">在“策略设置”页面上，选中“**用户必须提供理由才可删除标签或设置更低分类标签**”复选框，然后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="56d2c-192">On the Policy settings page, select the **Users must provide justification to remove a label or lower classification label** check box, and then click **Next**.</span></span>
11. <span data-ttu-id="56d2c-193">为策略名称键入 **公司战略**，然后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="56d2c-193">Type **Company Strategy** for the policy name, and then click **Next**.</span></span>
12. <span data-ttu-id="56d2c-194">单击“**提交**”，然后单击“**完成**”。</span><span class="sxs-lookup"><span data-stu-id="56d2c-194">Click **Submit** and then click **Done**.</span></span>

<span data-ttu-id="56d2c-195">注意，“**公司战略**”标签在发布后可能需要一些时间才可用。</span><span class="sxs-lookup"><span data-stu-id="56d2c-195">It may take some time for the **Company Strategy** label to become available after it's been published.</span></span>

<span data-ttu-id="56d2c-196">接下来，将新标签应用到“**公司战略**”团队并更新默认共享链接类型，以减少将文件和文件夹意外共享给比预期更多受众的风险。</span><span class="sxs-lookup"><span data-stu-id="56d2c-196">Next, apply your new label to the **Company Strategy** team and update the default sharing link type to reduce the risk of accidentally sharing files and folders to a wider audience than intended.</span></span>

1. <span data-ttu-id="56d2c-197">打开 [SharePoint 管理中心](https://admin.microsoft.com/sharepoint)。</span><span class="sxs-lookup"><span data-stu-id="56d2c-197">Open the [SharePoint admin center](https://admin.microsoft.com/sharepoint).</span></span>
2. <span data-ttu-id="56d2c-198">在“**站点**”下，单击“**活动站点**”。</span><span class="sxs-lookup"><span data-stu-id="56d2c-198">Under **Sites**, click **Active sites**.</span></span>
3. <span data-ttu-id="56d2c-199">单击“**公司战略**”站点。</span><span class="sxs-lookup"><span data-stu-id="56d2c-199">Click the **Company Strategy** site.</span></span>
4. <span data-ttu-id="56d2c-200">在“**策略**”选项卡的“**敏感度**”下，单击“**编辑**”。</span><span class="sxs-lookup"><span data-stu-id="56d2c-200">On the **Policies** tab, under **Sensitivity**, click **Edit**.</span></span>
5. <span data-ttu-id="56d2c-201">选择“**公司战略**”标签，然后单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="56d2c-201">Select the **Company Strategy** label, and then click **Save**.</span></span>
6. <span data-ttu-id="56d2c-202">在“**策略**”选项卡的“**外部共享**”下，单击“**编辑**”。</span><span class="sxs-lookup"><span data-stu-id="56d2c-202">On the **Policies** tab, under **External sharing**, click **Edit**.</span></span>
5. <span data-ttu-id="56d2c-203">选择“**仅限组织中的人员**”。</span><span class="sxs-lookup"><span data-stu-id="56d2c-203">Choose **Only people in your organization**.</span></span>
6. <span data-ttu-id="56d2c-204">在“**默认共享链接类型**”下，清除“**与组织级别设置相同**”复选框，然后选择“**现有访问权限者**”。</span><span class="sxs-lookup"><span data-stu-id="56d2c-204">Under **Default sharing** link type, clear the **Same as organization-level setting** check box, and select **People with existing access**.</span></span>
7. <span data-ttu-id="56d2c-205">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="56d2c-205">Click **Save**.</span></span>

<span data-ttu-id="56d2c-206">接下来，为“**公司战略**”团队配置“仅所有者”站点共享。</span><span class="sxs-lookup"><span data-stu-id="56d2c-206">Next, configure owners-only site sharing for the **Company Strategy** team.</span></span>

1. <span data-ttu-id="56d2c-207">在 Teams 中，导航至“**公司战略**”团队的“**常规**”选项卡。</span><span class="sxs-lookup"><span data-stu-id="56d2c-207">In Teams, navigate to the **General** tab of the **Company Strategy** team.</span></span>
2. <span data-ttu-id="56d2c-208">在团队的工具栏中，单击“文件”。</span><span class="sxs-lookup"><span data-stu-id="56d2c-208">In the tool bar for the team, click **Files**.</span></span>
3. <span data-ttu-id="56d2c-209">单击省略号，然后单击“在 SharePoint 中打开”。</span><span class="sxs-lookup"><span data-stu-id="56d2c-209">Click the ellipsis, and then click **Open in SharePoint**.</span></span>
4. <span data-ttu-id="56d2c-210">在基础 SharePoint 网站的工具栏中，依次单击设置图标和“网站权限”。</span><span class="sxs-lookup"><span data-stu-id="56d2c-210">In the tool bar of the underlying SharePoint site, click the settings icon, and then click **Site permissions**.</span></span>
5. <span data-ttu-id="56d2c-211">在“网站权限”窗格的“**网站共享**”下方，单击“**更改成员共享方式**”。</span><span class="sxs-lookup"><span data-stu-id="56d2c-211">In the Site permissions pane, under **Site Sharing**, click **Change how members can share**.</span></span>
6. <span data-ttu-id="56d2c-212">在“**共享权限**”下方，选择“**仅网站所有者可以共享文件、文件夹和网站**”，然后单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="56d2c-212">Under **Sharing permissions**, choose **Only site owners can share files, folders, and the site**, and then click **Save**.</span></span>
7. <span data-ttu-id="56d2c-213">关闭“**权限**”和“**设置**”窗格。</span><span class="sxs-lookup"><span data-stu-id="56d2c-213">Close the **Permissions** and **Settings** panes.</span></span>

<span data-ttu-id="56d2c-214">如果以公司战略组成员身份登录，将在 Word、Excel 和 PowerPoint 的“主页”工具栏中的“**敏感度**”选项中看到“**公司战略**”。</span><span class="sxs-lookup"><span data-stu-id="56d2c-214">If you sign in as a member of the Company Strategy group, you will see **Company Strategy** in the **Sensitivity** option in the Home toolbar of Word, Excel, and PowerPoint.</span></span> <span data-ttu-id="56d2c-215">从“**敏感度**”选项中选择“**公司战略**”标签，将标签分配给文件。</span><span class="sxs-lookup"><span data-stu-id="56d2c-215">Select the **Company Strategy** label from the **Sensitivity** option to assign the label to a file.</span></span>

<span data-ttu-id="56d2c-216">下面是公司战略团队的配置结果。</span><span class="sxs-lookup"><span data-stu-id="56d2c-216">Here is the resulting configuration for the Company Strategy team.</span></span>

![公司战略隔离团队的配置](../media/team-security-isolation-dev-test/team-security-isolation-dev-test-config.png)

## <a name="next-step"></a><span data-ttu-id="56d2c-218">后续步骤</span><span class="sxs-lookup"><span data-stu-id="56d2c-218">Next step</span></span>

<span data-ttu-id="56d2c-219">当你准备好进行生产部署时，请参考 [配置说明](secure-teams-security-isolation.md)。</span><span class="sxs-lookup"><span data-stu-id="56d2c-219">When you're ready for production deployment, see these [configuration instructions](secure-teams-security-isolation.md).</span></span>
