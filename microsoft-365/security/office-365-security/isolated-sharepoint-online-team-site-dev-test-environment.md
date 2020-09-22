---
title: 独立的 SharePoint Online 团队网站开发/测试环境
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/15/2017
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: Ent_O365
ms.custom:
- TLG
- Ent_TLGs
ms.assetid: d1795031-beef-49ea-a6fc-5da5450d320d
description: 摘要：在 Microsoft 365 开发/测试环境中配置与组织的其余部分隔离的 SharePoint Online 团队网站。
ms.openlocfilehash: e21dccb9ef535bb997d6e62b70e5576bf531041c
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/22/2020
ms.locfileid: "48199657"
---
# <a name="isolated-sharepoint-online-team-site-devtest-environment"></a><span data-ttu-id="0f203-103">独立的 SharePoint Online 团队网站开发/测试环境</span><span class="sxs-lookup"><span data-stu-id="0f203-103">Isolated SharePoint Online team site dev/test environment</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


 <span data-ttu-id="0f203-104">**摘要：** 在 Microsoft 365 开发/测试环境中配置与组织的其余部分隔离的 SharePoint Online 团队网站。</span><span class="sxs-lookup"><span data-stu-id="0f203-104">**Summary:** Configure a SharePoint Online team site that is isolated from the rest of the organization in your Microsoft 365 dev/test environment.</span></span>

<span data-ttu-id="0f203-105">Microsoft 365 中的 SharePoint Online 团队网站是使用通用文档库、OneNote 笔记本和其他服务进行协作的位置。</span><span class="sxs-lookup"><span data-stu-id="0f203-105">SharePoint Online team sites in Microsoft 365 are locations for collaboration using a common document library, a OneNote notebook, and other services.</span></span> <span data-ttu-id="0f203-106">在大多数情况下，需要跨部门或组织实现广泛访问和协作。</span><span class="sxs-lookup"><span data-stu-id="0f203-106">In many cases, you want wide access and collaboration across departments or organizations.</span></span> <span data-ttu-id="0f203-107">但是，在某些情况下，您希望在一小部分人员之间严格控制协作的访问权限和权限。</span><span class="sxs-lookup"><span data-stu-id="0f203-107">However, in some cases, you want to tightly control the access and permissions for collaboration among a small group of people.</span></span>

<span data-ttu-id="0f203-108">对 SharePoint Online 团队网站的访问权限以及用户可以执行的操作由 SharePoint 组和权限级别控制。</span><span class="sxs-lookup"><span data-stu-id="0f203-108">Access to SharePoint Online team sites and what users can do is controlled by SharePoint groups and permission levels.</span></span> <span data-ttu-id="0f203-109">默认情况下，SharePoint Online 网站有三种访问级别：</span><span class="sxs-lookup"><span data-stu-id="0f203-109">By default, SharePoint Online sites have three levels of access:</span></span>

- <span data-ttu-id="0f203-110">**成员**：可以在网站上查看、创建和修改资源。</span><span class="sxs-lookup"><span data-stu-id="0f203-110">**Members**, who can view, create, and modify resources on the site.</span></span>

- <span data-ttu-id="0f203-111">**所有者**：可完全控制网站，包括能够更改权限。</span><span class="sxs-lookup"><span data-stu-id="0f203-111">**Owners**, who have complete control of the site, including the ability to change permissions.</span></span>

- <span data-ttu-id="0f203-112">**访问者**：只能在网站上查看资源。</span><span class="sxs-lookup"><span data-stu-id="0f203-112">**Visitors**, who only can view resources on the site.</span></span>

<span data-ttu-id="0f203-113">本文将指导您完成对名为 ProjectX 的机密研究项目的独立 SharePoint Online 团队网站的配置。</span><span class="sxs-lookup"><span data-stu-id="0f203-113">This article steps you through the configuration of an isolated SharePoint Online team site for a secret research project named ProjectX.</span></span> <span data-ttu-id="0f203-114">访问要求为：</span><span class="sxs-lookup"><span data-stu-id="0f203-114">The access requirements are:</span></span>

- <span data-ttu-id="0f203-115">只有此项目的成员才能访问网站及其内容（文档、OneNote 笔记本、网页），编辑和查看 SharePoint 权限级别是通过组成员身份进行控制。</span><span class="sxs-lookup"><span data-stu-id="0f203-115">Only members of the project can access the site and its contents (documents, OneNote Notebook, Pages), with edit and view SharePoint permission levels controlled through group membership.</span></span>

- <span data-ttu-id="0f203-116">只有网站创建者和网站管理员组成员才能管理网站，包括可以修改网站级权限。</span><span class="sxs-lookup"><span data-stu-id="0f203-116">Only the site creator and members of an Admins group for the site can perform site administration, which includes modifying site-level permissions.</span></span>

<span data-ttu-id="0f203-117">在 Microsoft 365 开发/测试环境中设置独立的 SharePoint Online 团队网站有三个阶段：</span><span class="sxs-lookup"><span data-stu-id="0f203-117">There are three phases to setting up an isolated SharePoint Online team site in your Microsoft 365 dev/test environment:</span></span>

1. <span data-ttu-id="0f203-118">创建 Microsoft 365 开发/测试环境。</span><span class="sxs-lookup"><span data-stu-id="0f203-118">Create the Microsoft 365 dev/test environment.</span></span>

2. <span data-ttu-id="0f203-119">创建 ProjectX 用户和组。</span><span class="sxs-lookup"><span data-stu-id="0f203-119">Create the users and groups for ProjectX.</span></span>

3. <span data-ttu-id="0f203-120">创建一个新的 ProjectX SharePoint Online 团队网站并将其隔离。</span><span class="sxs-lookup"><span data-stu-id="0f203-120">Create a new ProjectX SharePoint Online team site and isolate it.</span></span>

> [!TIP]
> <span data-ttu-id="0f203-121">单击[此处](https://aka.ms/catlgstack)可直观映射到 One Microsoft 云测试实验室指南堆栈中的所有文章。</span><span class="sxs-lookup"><span data-stu-id="0f203-121">Click [here](https://aka.ms/catlgstack) for a visual map to all the articles in the One Microsoft Cloud Test Lab Guide stack.</span></span>

## <a name="phase-1-build-out-your-lightweight-or-simulated-enterprise-microsoft-365-devtest-environment"></a><span data-ttu-id="0f203-122">第1阶段：构建轻型或模拟的企业 Microsoft 365 开发/测试环境</span><span class="sxs-lookup"><span data-stu-id="0f203-122">Phase 1: Build out your lightweight or simulated enterprise Microsoft 365 dev/test environment</span></span>

<span data-ttu-id="0f203-123">如果只想使用最低要求以轻量方式创建独立的 SharePoint Online 团队网站，请按照 [轻型基本配置](https://docs.microsoft.com/microsoft-365/enterprise/lightweight-base-configuration-microsoft-365-enterprise)的第2阶段和第3阶段中的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="0f203-123">If you just want to create an isolated SharePoint Online team site in a lightweight way with the minimum requirements, follow the instructions in phases 2 and 3 of [The lightweight base configuration](https://docs.microsoft.com/microsoft-365/enterprise/lightweight-base-configuration-microsoft-365-enterprise).</span></span>

<span data-ttu-id="0f203-124">如果要在模拟的企业配置中创建独立的 SharePoint Online 团队网站，请按照 [针对 Microsoft 365 测试环境的密码哈希同步](https://docs.microsoft.com/microsoft-365/enterprise/password-hash-sync-m365-ent-test-environment)中的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="0f203-124">If you want to create an isolated SharePoint Online team site in a simulated enterprise configuration, follow the instructions in [Password hash synchronization for your Microsoft 365 test environment](https://docs.microsoft.com/microsoft-365/enterprise/password-hash-sync-m365-ent-test-environment).</span></span>

> [!NOTE]
> <span data-ttu-id="0f203-125">创建独立的 SharePoint Online 网站不需要模拟企业开发/测试环境，其中包括连接到 Internet 的模拟 intranet 和 Active Directory 域服务 (AD DS) 林的目录同步。</span><span class="sxs-lookup"><span data-stu-id="0f203-125">Creating an isolated SharePoint Online site does not require the simulated enterprise dev/test environment, which includes a simulated intranet connected to the Internet and directory synchronization for a Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="0f203-126">可以根据需要选择此选项，以便能够测试独立 SharePoint Online 网站，并在代表典型组织的环境中对其进行试验。</span><span class="sxs-lookup"><span data-stu-id="0f203-126">It is provided here as an option so that you can test an isolated SharePoint Online site and experiment with it in an environment that represents a typical organization.</span></span>

## <a name="phase-2-create-user-accounts-and-access-groups"></a><span data-ttu-id="0f203-127">第2阶段：创建用户帐户和访问组</span><span class="sxs-lookup"><span data-stu-id="0f203-127">Phase 2: Create user accounts and access groups</span></span>

<span data-ttu-id="0f203-128">使用 [连接到 Office 365 PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-microsoft-365-powershell) 中的说明，通过全局管理员帐户连接到你的试用订阅：</span><span class="sxs-lookup"><span data-stu-id="0f203-128">Use the instructions in [Connect to Office 365 PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-microsoft-365-powershell) to connect to your trial subscription with your global administrator account from:</span></span>

- <span data-ttu-id="0f203-129">您的计算机 (的轻型 Microsoft 365 开发/测试环境) 。</span><span class="sxs-lookup"><span data-stu-id="0f203-129">Your computer (for the lightweight Microsoft 365 dev/test environment).</span></span>

- <span data-ttu-id="0f203-130">模拟企业 Microsoft 365 开发/测试环境的 CLIENT1 虚拟机 () 。</span><span class="sxs-lookup"><span data-stu-id="0f203-130">The CLIENT1 virtual machine (for the simulated enterprise Microsoft 365 dev/test environment).</span></span>

<span data-ttu-id="0f203-131">若要为 ProjectX SharePoint Online 团队网站创建新的访问组，请从 Windows PowerShell 提示符的 Windows Azure Active Directory 模块运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="0f203-131">To create the new access groups for the ProjectX SharePoint Online team site, run these commands from the Windows Azure Active Directory Module for Windows PowerShell prompt:</span></span>

```powershell
$groupName="ProjectX-Members"
$groupDesc="People allowed to collaborate for ProjectX."
New-MsolGroup -DisplayName $groupName -Description $groupDesc
$groupName="ProjectX-Admins"
$groupDesc="People allowed to administer SharePoint for ProjectX."
New-MsolGroup -DisplayName $groupName -Description $groupDesc
$groupName="ProjectX-Viewers"
$groupDesc="People allowed to view the SharePoint resources for ProjectX."
New-MsolGroup -DisplayName $groupName -Description $groupDesc
```

<span data-ttu-id="0f203-132">填写组织名称（示例：contosotoycompany），你所在位置的两位字符的国家/地区代码，然后从用于 Windows PowerShell 的 Windows Azure Active Directory 模块提示符中运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="0f203-132">Fill in your organization name (example: contosotoycompany), the two-character country code for your location, and then run the following commands from the Windows Azure Active Directory Module for Windows PowerShell prompt:</span></span>

```powershell
$orgName="<organization name>"
$loc="<two-character country code, such as US>"
$licAssignment= $orgName + ":ENTERPRISEPREMIUM"
$userName= "designer@" + $orgName + ".onmicrosoft.com"
New-MsolUser -DisplayName "Lead Designer" -FirstName Lead -LastName Designer -UserPrincipalName $userName -UsageLocation $loc -LicenseAssignment $licAssignment -ForceChangePassword $false
```

<span data-ttu-id="0f203-133">在安全的位置上，记下显示的 **New-MsolUser** 命令中为 Lead Designer 帐户生成的密码。</span><span class="sxs-lookup"><span data-stu-id="0f203-133">From the display of the **New-MsolUser** command, note the generated password for the Lead Designer account and record it in a safe location.</span></span>

<span data-ttu-id="0f203-134">从用于 Windows PowerShell 的 Windows Azure Active Directory 模块提示符中运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="0f203-134">Run the following commands from the Windows Azure Active Directory Module for Windows PowerShell prompt:</span></span>

```powershell
$userName= "researcher@" + $orgName + ".onmicrosoft.com"
New-MsolUser -DisplayName "Lead Researcher" -FirstName Lead -LastName Researcher -UserPrincipalName $userName -UsageLocation $loc -LicenseAssignment $licAssignment -ForceChangePassword $false
```

<span data-ttu-id="0f203-135">在安全的位置上，记下显示的 **New-MsolUser** 命令中为 Lead Researcher 帐户生成的密码。</span><span class="sxs-lookup"><span data-stu-id="0f203-135">From the display of the **New-MsolUser** command, note the generated password for the Lead Researcher account and record it in a safe location.</span></span>

<span data-ttu-id="0f203-136">从用于 Windows PowerShell 的 Windows Azure Active Directory 模块提示符中运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="0f203-136">Run the following commands from the Windows Azure Active Directory Module for Windows PowerShell prompt:</span></span>

```powershell
$userName= "devvp@" + $orgName + ".onmicrosoft.com"
New-MsolUser -DisplayName "Development VP" -FirstName Development -LastName VP -UserPrincipalName $userName -UsageLocation $loc -LicenseAssignment $licAssignment -ForceChangePassword $false
```

<span data-ttu-id="0f203-137">在安全的位置上，记下显示的 **New-MsolUser** 命令中为 Development VP 帐户生成的密码。</span><span class="sxs-lookup"><span data-stu-id="0f203-137">From the display of the **New-MsolUser** command, note the generated password for the Development VP account and record it in a safe location.</span></span>

<span data-ttu-id="0f203-138">接下来，若要将新帐户添加到新的访问组，请从 Windows PowerShell 提示符的 Windows Azure Active Directory 模块中运行这些 PowerShell 命令：</span><span class="sxs-lookup"><span data-stu-id="0f203-138">Next, to add the new accounts to the new access groups, run these PowerShell commands from the Windows Azure Active Directory Module for Windows PowerShell prompt:</span></span>

```powershell
$grpName="ProjectX-Members"
$userUPN="designer@" + $orgName + ".onmicrosoft.com"
Add-MsolGroupMember -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $grpName }).ObjectID -GroupMemberObjectId (Get-MsolUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -GroupMemberType "User"
$userUPN="researcher@" + $orgName + ".onmicrosoft.com"
Add-MsolGroupMember -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $grpName }).ObjectID -GroupMemberObjectId (Get-MsolUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -GroupMemberType "User"
$grpName="ProjectX-Admins"
Add-MsolGroupMember -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $grpName }).ObjectID -GroupMemberObjectId (Get-MsolUser | Where { $_.UserPrincipalName -eq $userCredential.UserName }).ObjectID -GroupMemberType "User"
$grpName="ProjectX-Viewers"
$userUPN="devvp@" + $orgName + ".onmicrosoft.com"
Add-MsolGroupMember -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $grpName }).ObjectID -GroupMemberObjectId (Get-MsolUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -GroupMemberType "User"
```

<span data-ttu-id="0f203-139">引起</span><span class="sxs-lookup"><span data-stu-id="0f203-139">Results:</span></span>

- <span data-ttu-id="0f203-140">ProjectX 访问组包含潜在客户设计人员和潜在客户研究工具用户帐户</span><span class="sxs-lookup"><span data-stu-id="0f203-140">The ProjectX-Members access group contains the Lead Designer and Lead Researcher user accounts</span></span>

- <span data-ttu-id="0f203-141">ProjectX 访问组包含试用订阅的全局管理员帐户</span><span class="sxs-lookup"><span data-stu-id="0f203-141">The ProjectX-Admins access group contains the global administrator account for your trial subscription</span></span>

- <span data-ttu-id="0f203-142">ProjectX 访问组包含开发副总裁用户帐户</span><span class="sxs-lookup"><span data-stu-id="0f203-142">The ProjectX-Viewers access group contains the Development VP user account</span></span>

<span data-ttu-id="0f203-143">图1显示了访问组及其成员资格。</span><span class="sxs-lookup"><span data-stu-id="0f203-143">Figure 1 shows the access groups and their membership.</span></span>

<span data-ttu-id="0f203-144">**图1**</span><span class="sxs-lookup"><span data-stu-id="0f203-144">**Figure 1**</span></span>

![适用于独立 SharePoint Online 组网站的 Microsoft 365 组及其成员资格](../../media/5b7373b9-2a80-4880-afe5-63ffb17237e6.png)

## <a name="phase-3-create-a-new-projectx-sharepoint-online-team-site-and-isolate-it"></a><span data-ttu-id="0f203-146">第3阶段：创建新的 ProjectX SharePoint Online 团队网站并将其隔离</span><span class="sxs-lookup"><span data-stu-id="0f203-146">Phase 3: Create a new ProjectX SharePoint Online team site and isolate it</span></span>

<span data-ttu-id="0f203-147">若要为 ProjectX 创建 SharePoint Online 团队网站，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="0f203-147">To create a SharePoint Online team site for ProjectX, do the following:</span></span>

1. <span data-ttu-id="0f203-148">使用本地计算机上的浏览器 (轻量配置) 或在 CLIENT1 (模拟企业配置) 上，使用全局管理员帐户登录 Microsoft 365 管理中心 ([https://admin.microsoft.com](https://admin.microsoft.com)) 。</span><span class="sxs-lookup"><span data-stu-id="0f203-148">Using a browser on either your local computer (lightweight configuration) or on CLIENT1 (simulated enterprise configuration), sign in to the Microsoft 365 admin center ([https://admin.microsoft.com](https://admin.microsoft.com)) using your global administrator account.</span></span>

2. <span data-ttu-id="0f203-149">在磁贴列表中，单击“SharePoint”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0f203-149">In the list of tiles, click **SharePoint**.</span></span>

3. <span data-ttu-id="0f203-150">在浏览器上的新“SharePoint”选项卡中，单击“+ 创建网站”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0f203-150">On the new SharePoint tab in your browser, click **+ Create site**.</span></span>

4. <span data-ttu-id="0f203-151">在“团队网站名称”\*\*\*\* 中，键入“ProjectX”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0f203-151">In **Team site name**, type **ProjectX**.</span></span> <span data-ttu-id="0f203-152">在 " **隐私设置**" 中，选择 " **仅专用成员可以访问此网站**"。</span><span class="sxs-lookup"><span data-stu-id="0f203-152">In **Privacy settings**, select **Private - only members can access this site**.</span></span>

5. <span data-ttu-id="0f203-153">在“团队网站描述”\*\*\*\* 中，键入“ProjectX 的 SharePoint 网站”\*\*\*\*，然后单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0f203-153">In **Team site description**, type **SharePoint site for ProjectX**, and then click **Next**.</span></span>

6. <span data-ttu-id="0f203-154">在“想添加什么人员?”\*\*\*\* 窗格中，单击“完成”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0f203-154">On the **Who do you want to add**? pane, click **Finish**.</span></span>

7. <span data-ttu-id="0f203-155">在浏览器上的新“ProjectX-主页”\*\*\*\* 选项卡上，依次单击工具栏中的设置图标和“网站权限”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0f203-155">On the new **ProjectX-Home** tab in your browser, in the tool bar, click the settings icon, and then click **Site permissions**.</span></span>

8. <span data-ttu-id="0f203-156">在“网站权限”\*\*\*\* 窗格中，单击“高级权限设置”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0f203-156">In the **Site permissions** pane, click **Advanced permissions settings**.</span></span>

9. <span data-ttu-id="0f203-157">在浏览器上的新“权限：\*\*\*\* Project X”选项卡中，单击“访问请求设置”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0f203-157">In the new **Permissions: Project X** tab in your browser, click **Access Request Settings**.</span></span>

10. <span data-ttu-id="0f203-158">在“访问请求设置”\*\*\*\* 对话框中，取消选中“允许成员共享网站以及个别文件和文件夹”\*\*\*\* 和“允许访问请求”\*\*\*\*（以便取消选中全部三个复选框），然后单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0f203-158">In the **Access Requests Settings** dialog box, clear **Allow members to share the site and individual files and folders** and **Allow access requests** (so that all three check boxes are cleared), and then click **OK**.</span></span>

11. <span data-ttu-id="0f203-159">单击列表中的“ProjectX 成员”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0f203-159">Click **ProjectX Members** in the list.</span></span>

12. <span data-ttu-id="0f203-160">在“**人员和组**”页面上，单击“**新建**”。</span><span class="sxs-lookup"><span data-stu-id="0f203-160">On the **People and Groups** page, click **New**.</span></span>

13. <span data-ttu-id="0f203-161">在“共享”\*\*\*\* 对话框中，键入并选择“ProjectX-Members”\*\*\*\*，然后单击“共享”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0f203-161">In the **Share** dialog box, type **ProjectX-Members**, select it, and then click **Share**.</span></span>

14. <span data-ttu-id="0f203-162">单击浏览器上的后退按钮。</span><span class="sxs-lookup"><span data-stu-id="0f203-162">Click the back button on your browser.</span></span>

15. <span data-ttu-id="0f203-163">单击列表中的“ProjectX 所有者”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0f203-163">Click **ProjectX Owners** in the list.</span></span>

16. <span data-ttu-id="0f203-164">在“**人员和组**”页面上，单击“**新建**”。</span><span class="sxs-lookup"><span data-stu-id="0f203-164">On the **People and Groups** page, click **New**.</span></span>

17. <span data-ttu-id="0f203-165">在“共享”\*\*\*\* 对话框中，键入并选择“ProjectX-Admins”\*\*\*\*，然后单击“共享”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0f203-165">In the **Share** dialog box, type **ProjectX-Admins**, select it, and then click **Share**.</span></span>

18. <span data-ttu-id="0f203-166">单击浏览器上的后退按钮。</span><span class="sxs-lookup"><span data-stu-id="0f203-166">Click the back button on your browser.</span></span>

19. <span data-ttu-id="0f203-167">单击列表中的“ProjectX 访问者”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0f203-167">Click **ProjectX Visitors** in the list.</span></span>

20. <span data-ttu-id="0f203-168">在“人员和组”\*\*\*\* 页面上，单击“新建”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0f203-168">On the **People and Groups** page, click **New**.</span></span>

21. <span data-ttu-id="0f203-169">在“共享”\*\*\*\* 对话框中，键入并选择“ProjectX-Viewers”\*\*\*\*，然后单击“共享”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0f203-169">In the **Share** dialog box, type **ProjectX-Viewers**, select it, and then click **Share**.</span></span>

22. <span data-ttu-id="0f203-170">关闭浏览器上的“人员和组”\*\*\*\* 选项卡，单击浏览器上的“ProjectX-主页”\*\*\*\* 选项卡，然后关闭“网站权限”\*\*\*\* 窗格。</span><span class="sxs-lookup"><span data-stu-id="0f203-170">Close the **People and Groups** tab in your browser, click the **ProjectX-Home** tab in your browser, and then close the **Site permissions** pane.</span></span>

<span data-ttu-id="0f203-171">下面介绍了权限配置结果：</span><span class="sxs-lookup"><span data-stu-id="0f203-171">Here are the results of configuring permissions:</span></span>

- <span data-ttu-id="0f203-172">ProjectX Members SharePoint 组仅包含 ProjectX 成员访问组 (，其中仅包含领导设计人员和负责人研究人员用户帐户) 以及仅包含全局管理员用户帐户) 的 ProjectX 组 (。</span><span class="sxs-lookup"><span data-stu-id="0f203-172">The ProjectX Members SharePoint group contains only the ProjectX-Members access group (which contains only the Lead Designer and Lead Researcher user accounts) and the ProjectX group (which contains only the global administrator user account).</span></span>

- <span data-ttu-id="0f203-173">ProjectX 所有者 SharePoint 组仅包含 ProjectX 访问组 (仅包含全局管理员用户帐户的) 。</span><span class="sxs-lookup"><span data-stu-id="0f203-173">The ProjectX Owners SharePoint group contains only the ProjectX-Admins access group (which contains only the global administrator user account).</span></span>

- <span data-ttu-id="0f203-174">"ProjectX 访问者" SharePoint 组仅包含 "ProjectX" 访问组 (，其中仅包含 "开发副总裁" 用户帐户) 。</span><span class="sxs-lookup"><span data-stu-id="0f203-174">The ProjectX Visitors SharePoint group contains only the ProjectX-Viewers access group (which contains only the Development VP user account).</span></span>

- <span data-ttu-id="0f203-175">成员无法修改网站级权限（只有 ProjectX-Admins 组成员才能修改）。</span><span class="sxs-lookup"><span data-stu-id="0f203-175">Members cannot modify site-level permissions (this can only be done by members of the ProjectX-Admins group).</span></span>

- <span data-ttu-id="0f203-176">其他用户帐户无法访问网站及其资源，也无法请求访问网站。</span><span class="sxs-lookup"><span data-stu-id="0f203-176">Other user accounts cannot access the site or its resources or request access to the site.</span></span>

<span data-ttu-id="0f203-177">图 2 展示了 SharePoint 组及其成员身份。</span><span class="sxs-lookup"><span data-stu-id="0f203-177">Figure 2 shows the SharePoint groups and their membership.</span></span>

<span data-ttu-id="0f203-178">**图2**</span><span class="sxs-lookup"><span data-stu-id="0f203-178">**Figure 2**</span></span>

![SharePoint Online 组及其针对独立 SharePoint Online 组网站的成员身份](../../media/595abff4-64f9-49de-a37a-c70c6856936b.png)

<span data-ttu-id="0f203-180">现在，让我们来演示如何使用主导 Designer 用户帐户进行访问：</span><span class="sxs-lookup"><span data-stu-id="0f203-180">Now let's demonstrate access using the Lead Designer user account:</span></span>

1. <span data-ttu-id="0f203-181">关闭浏览器中的“ProjectX-主页”\*\*\*\* 选项卡，然后单击浏览器中的“Microsoft Office 主页”\*\*\*\* 选项卡。</span><span class="sxs-lookup"><span data-stu-id="0f203-181">Close the **ProjectX-Home** tab in your browser, and then click the **Microsoft Office Home** tab in your browser.</span></span>

2. <span data-ttu-id="0f203-182">依次单击全局管理员名称和“注销”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0f203-182">Click the name of your global administrator, and then click **Sign out**.</span></span>

3. <span data-ttu-id="0f203-183">[https://admin.microsoft.com](https://admin.microsoft.com)使用主导 Designer 帐户名称及其密码登录到 Microsoft 365 管理中心 () 。</span><span class="sxs-lookup"><span data-stu-id="0f203-183">Sign in to the Microsoft 365 admin center ([https://admin.microsoft.com](https://admin.microsoft.com)) using the Lead Designer account name and its password.</span></span>

4. <span data-ttu-id="0f203-184">在磁贴列表中，单击“SharePoint”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0f203-184">In the list of tiles, click **SharePoint**.</span></span>

5. <span data-ttu-id="0f203-185">在浏览器的 "新建 **SharePoint** " 选项卡上，在 "搜索" 框中键入 **ProjectX** ，激活搜索，然后单击 " **ProjectX** 团队网站"。</span><span class="sxs-lookup"><span data-stu-id="0f203-185">On the new **SharePoint** tab in your browser, type **ProjectX** in the search box, activate the search, and then click the **ProjectX** team site.</span></span> <span data-ttu-id="0f203-186">您应该会在浏览器中看到一个用于 ProjectX 团队网站的新选项卡。</span><span class="sxs-lookup"><span data-stu-id="0f203-186">You should see a new tab in your browser for the ProjectX team site.</span></span>

6. <span data-ttu-id="0f203-p107">单击设置图标。请注意，没有“网站权限”\*\*\*\* 选项。这没有问题，因为只有 ProjectX-Admins 组成员才能修改网站级权限</span><span class="sxs-lookup"><span data-stu-id="0f203-p107">Click the settings icon. Notice that there is no option for **Site Permissions**. This is correct because only the members of the ProjectX-Admins group can modify permissions on the site</span></span>

7. <span data-ttu-id="0f203-190">打开选择的记事本或文本编辑器。</span><span class="sxs-lookup"><span data-stu-id="0f203-190">Open Notepad or a text editor of your choice.</span></span>

8. <span data-ttu-id="0f203-191">复制 ProjectX 团队网站的 URL，并将其粘贴到记事本或文本编辑器中的新行上。</span><span class="sxs-lookup"><span data-stu-id="0f203-191">Copy the URL of the ProjectX team site and paste it on a new line in Notepad or your text editor.</span></span>

9. <span data-ttu-id="0f203-192">在浏览器上的新“ProjectX-主页”\*\*\*\* 选项卡中，单击“文档”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0f203-192">On the new **ProjectX-Home** tab in your browser, click **Documents**.</span></span>

10. <span data-ttu-id="0f203-193">将 ProjectX 文档文件夹的 URL 复制并粘贴到记事本或文本编辑器中的新行上。</span><span class="sxs-lookup"><span data-stu-id="0f203-193">Copy the URL of the ProjectX documents folder and paste it on a new line in Notepad or your text editor.</span></span>

11. <span data-ttu-id="0f203-194">在浏览器上的新“ProjectX-文档”\*\*\*\* 选项卡中，依次单击“新建”>“Word 文档”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0f203-194">On the new **ProjectX-Documents** tab in your browser, click **New > Word document**.</span></span>

12. <span data-ttu-id="0f203-195">在页面上键入一些文本，等待状态显示为 " **已保存**"，单击浏览器上的 "后退" 按钮，然后刷新页面。</span><span class="sxs-lookup"><span data-stu-id="0f203-195">Type some text on the page, wait for the status to indicate **Saved**, click the back button on your browser, and then refresh the page.</span></span> <span data-ttu-id="0f203-196">应该会看到“文档”\*\*\*\* 文件夹中有新的“Document.docx”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0f203-196">You should see a new **Document.docx** in the **Documents** folder.</span></span>

13. <span data-ttu-id="0f203-197">依次单击“Document.docx”\*\*\*\* 文档对应的省略号和“获取链接”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0f203-197">Click the ellipsis for the **Document.docx** document, and then click **Get a link**.</span></span>

14. <span data-ttu-id="0f203-198">复制 **共享 "Document.docx"** 对话框中的 URL，并将其粘贴到记事本或文本编辑器中的新行上，然后关闭 **共享 "Document.docx"** 对话框。</span><span class="sxs-lookup"><span data-stu-id="0f203-198">Copy the URL in the **Share 'Document.docx'** dialog box and paste it on a new line in Notepad or your text editor, and then close the **Share 'Document.docx'** dialog box.</span></span>

15. <span data-ttu-id="0f203-199">关闭浏览器中的“ProjectX-文档”\*\*\*\* 和“SharePoint”\*\*\*\* 选项卡，然后单击“Microsoft Office 主页”\*\*\*\* 选项卡。</span><span class="sxs-lookup"><span data-stu-id="0f203-199">Close the **ProjectX-Documents** and **SharePoint** tabs in your browser, and then click the **Microsoft Office Home** tab.</span></span>

16. <span data-ttu-id="0f203-200">依次单击“Lead Designer”\*\*\*\* 名称和“注销”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0f203-200">Click the **Lead Designer** name, and then click **Sign out**.</span></span>

<span data-ttu-id="0f203-201">现在，让我们来演示如何使用开发 VP 用户帐户进行访问：</span><span class="sxs-lookup"><span data-stu-id="0f203-201">Now let's demonstrate access using the Development VP user account:</span></span>

1. <span data-ttu-id="0f203-202">[https://admin.microsoft.com](https://admin.microsoft.com)使用开发副总裁帐户名称及其密码登录到 Microsoft 365 管理中心 () 。</span><span class="sxs-lookup"><span data-stu-id="0f203-202">Sign in to the Microsoft 365 admin center ([https://admin.microsoft.com](https://admin.microsoft.com)) using the Development VP account name and its password.</span></span>

2. <span data-ttu-id="0f203-203">在磁贴列表中，单击“SharePoint”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0f203-203">In the list of tiles, click **SharePoint**.</span></span>

3. <span data-ttu-id="0f203-204">在浏览器的 "新建 **SharePoint** " 选项卡上，在 "搜索" 框中键入 **ProjectX** ，激活搜索，然后单击 " **ProjectX** 团队网站"。</span><span class="sxs-lookup"><span data-stu-id="0f203-204">On the new **SharePoint** tab in your browser, type **ProjectX** in the search box, activate the search, and then click the **ProjectX** team site.</span></span> <span data-ttu-id="0f203-205">您应该会在浏览器中看到一个用于 ProjectX 团队网站的新选项卡。</span><span class="sxs-lookup"><span data-stu-id="0f203-205">You should see a new tab in your browser for the ProjectX team site.</span></span>

4. <span data-ttu-id="0f203-206">依次单击“文档”\*\*\*\* 和“Document.docx”\*\*\*\* 文件。</span><span class="sxs-lookup"><span data-stu-id="0f203-206">Click **Documents**, and then click the **Document.docx** file.</span></span>

5. <span data-ttu-id="0f203-p110">在浏览器上的“Document.docx”\*\*\*\* 选项卡中，尝试修改文本。应该会看到一条内容为“此文档为只读”\*\*\*\* 的消息。这属于正常情况，因为 Development VP 用户帐户仅拥有对网站的查看权限。</span><span class="sxs-lookup"><span data-stu-id="0f203-p110">In the **Document.docx** tab in your browser, try to modify the text. You should see a message stating **This document is read-only.** This is expected because the Development VP user account only has view permissions for the site.</span></span>

6. <span data-ttu-id="0f203-210">关闭浏览器中的“Document.docx”\*\*\*\*、“ProjectX-文档”\*\*\*\* 和“SharePoint”\*\*\*\* 选项卡。</span><span class="sxs-lookup"><span data-stu-id="0f203-210">Close the **Document.docx**, **ProjectX-Documents**, and **SharePoint** tabs in your browser.</span></span>

7. <span data-ttu-id="0f203-211">依次单击“Microsoft Office 主页”\*\*\*\* 选项卡、“Development VP”\*\*\*\* 名称和“注销”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0f203-211">Click the **Microsoft Office Home** tab, click the **Development VP** name, and then click **Sign out**.</span></span>

<span data-ttu-id="0f203-212">现在，让我们使用没有权限的用户帐户演示访问权限：</span><span class="sxs-lookup"><span data-stu-id="0f203-212">Now let's demonstrate access with a user account that has no permissions:</span></span>

1. <span data-ttu-id="0f203-213">[https://admin.microsoft.com](https://admin.microsoft.com)使用用户3帐户名称及其密码登录到 Microsoft 365 管理中心 () 。</span><span class="sxs-lookup"><span data-stu-id="0f203-213">Sign in to the Microsoft 365 admin center ([https://admin.microsoft.com](https://admin.microsoft.com)) using the User 3 account name and its password.</span></span>

2. <span data-ttu-id="0f203-214">在磁贴列表中，单击“SharePoint”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0f203-214">In the list of tiles, click **SharePoint**.</span></span>

3. <span data-ttu-id="0f203-p111">	在浏览器上的新“SharePoint”\*\*\*\* 选项卡中，在搜索框中键入“ProjectX”\*\*\*\*，然后开始搜索。应该会看到一条内容为“这里没有与你的搜索相匹配的内容”\*\*\*\* 的消息。</span><span class="sxs-lookup"><span data-stu-id="0f203-p111">On the new **SharePoint** tab in your browser, type **ProjectX** in the search box and then activate the search. You should see the message **Nothing here matches your search.**</span></span>

4. <span data-ttu-id="0f203-p112">将 ProjectX 网站的 URL 从记事本或文本编辑器的打开实例复制到浏览器的地址栏中，然后按“Enter”\*\*\*\*。应该会看到“拒绝访问”\*\*\*\* 网页。</span><span class="sxs-lookup"><span data-stu-id="0f203-p112">From the open instance of Notepad or your text editor, copy the URL for the ProjectX site into the address bar of your browser and press **Enter**. You should see an **Access Denied** page.</span></span>

5. <span data-ttu-id="0f203-p113">将 ProjectX 文档文件夹的 URL 从记事本或文本编辑器复制到浏览器的地址栏中，然后按“Enter”\*\*\*\*。应该会看到“拒绝访问”\*\*\*\* 网页。</span><span class="sxs-lookup"><span data-stu-id="0f203-p113">From Notepad or your text editor, copy the URL for the ProjectX Documents folder into the address bar of your browser and press **Enter**. You should see an **Access Denied** page.</span></span>

6. <span data-ttu-id="0f203-p114">将 Documents.docx 文件的 URL 从记事本或文本编辑器复制到浏览器的地址栏中，然后按“Enter”\*\*\*\*。应该会看到“拒绝访问”\*\*\*\* 网页。</span><span class="sxs-lookup"><span data-stu-id="0f203-p114">From Notepad or your text editor, copy the URL for the Documents.docx file into the address bar of your browser and press **Enter**. You should see an **Access Denied** page.</span></span>

7. <span data-ttu-id="0f203-223">关闭浏览器中的“SharePoint”\*\*\*\* 选项卡，然后依次单击“Microsoft Office 主页”\*\*\*\* 选项卡、“用户 3”\*\*\*\* 名称和“注销”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0f203-223">Close the **SharePoint** tab in your browser, click the **Microsoft Office Home** tab, click the **User 3** name, and then click **Sign out**.</span></span>

<span data-ttu-id="0f203-224">你的独立 SharePoint Online 网站现已准备好进行额外的实验。</span><span class="sxs-lookup"><span data-stu-id="0f203-224">Your isolated SharePoint Online site is now ready for your additional experimentation.</span></span>

## <a name="next-step"></a><span data-ttu-id="0f203-225">后续步骤</span><span class="sxs-lookup"><span data-stu-id="0f203-225">Next Step</span></span>

<span data-ttu-id="0f203-226">当准备好在生产中部署单独的 SharePoint Online 团队网站后，请参阅[设计单独的 SharePoint Online 团队网站](design-an-isolated-sharepoint-online-team-site.md)中的分步设计注意事项。</span><span class="sxs-lookup"><span data-stu-id="0f203-226">When you are ready to deploy an isolated SharePoint Online team site in production, see the step-by-step design considerations in [Design an isolated SharePoint Online team site](design-an-isolated-sharepoint-online-team-site.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="0f203-227">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0f203-227">See Also</span></span>

[<span data-ttu-id="0f203-228">独立 SharePoint Online 团队网站</span><span class="sxs-lookup"><span data-stu-id="0f203-228">Isolated SharePoint Online team sites</span></span>](isolated-sharepoint-online-team-sites.md)

[<span data-ttu-id="0f203-229">云采用测试实验室指南 (TLG)</span><span class="sxs-lookup"><span data-stu-id="0f203-229">Cloud adoption Test Lab Guides (TLGs)</span></span>](https://docs.microsoft.com/microsoft-365/enterprise/cloud-adoption-test-lab-guides-tlgs)

[<span data-ttu-id="0f203-230">模拟企业基础配置</span><span class="sxs-lookup"><span data-stu-id="0f203-230">The simulated enterprise base configuration</span></span>](https://docs.microsoft.com/microsoft-365/enterprise/simulated-ent-base-configuration-microsoft-365-enterprise)

[<span data-ttu-id="0f203-231">轻型基本配置</span><span class="sxs-lookup"><span data-stu-id="0f203-231">The lightweight base configuration</span></span>](https://docs.microsoft.com/microsoft-365/enterprise/lightweight-base-configuration-microsoft-365-enterprise)

[<span data-ttu-id="0f203-232">云应用和混合解决方案</span><span class="sxs-lookup"><span data-stu-id="0f203-232">Cloud adoption and hybrid solutions</span></span>](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)
