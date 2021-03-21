---
title: Microsoft 365 中的核心电子数据展示事例入门
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: 本文介绍如何开始使用 Microsoft 365 中的核心电子数据展示。 分配电子数据展示权限并创建案例后，可以添加成员、创建电子数据展示保留，然后搜索和导出与调查相关的数据。
ms.openlocfilehash: 4a814b2e0019f86e4a4fc0e26d19df4411402749
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919758"
---
# <a name="get-started-with-core-ediscovery"></a><span data-ttu-id="b36ba-104">核心电子数据展示入门</span><span class="sxs-lookup"><span data-stu-id="b36ba-104">Get started with Core eDiscovery</span></span>

<span data-ttu-id="b36ba-105">Microsoft 365 中的核心电子数据展示提供了一个基本电子数据展示工具，组织可以使用该工具搜索和导出 Microsoft 365 和 Office 365 中的内容。</span><span class="sxs-lookup"><span data-stu-id="b36ba-105">Core eDiscovery in Microsoft 365 provides a basic eDiscovery tool that organizations can use to search and export content in Microsoft 365 and Office 365.</span></span> <span data-ttu-id="b36ba-106">您还可以使用核心电子数据展示将电子数据展示保留置于内容位置（如 Exchange 邮箱、SharePoint 网站、OneDrive 帐户和 Microsoft Teams）上。</span><span class="sxs-lookup"><span data-stu-id="b36ba-106">You can also use Core eDiscovery to place an eDiscovery hold on content locations, such as Exchange mailboxes, SharePoint sites, OneDrive accounts, and Microsoft Teams.</span></span> <span data-ttu-id="b36ba-107">部署核心电子数据展示不需要任何内容，但在您的组织开始使用核心电子数据展示搜索、导出和保留内容之前，IT 管理员和电子数据展示管理员必须完成一些先决条件任务。</span><span class="sxs-lookup"><span data-stu-id="b36ba-107">Nothing is needed to deploy Core eDiscovery, but there are some prerequisite tasks that an IT admin and eDiscovery manager have to complete before your organization can start using Core eDiscovery to search, export, and preserve content.</span></span>

<span data-ttu-id="b36ba-108">本文讨论设置核心电子数据展示所需的步骤。</span><span class="sxs-lookup"><span data-stu-id="b36ba-108">This article discusses the steps necessary to set up Core eDiscovery.</span></span> <span data-ttu-id="b36ba-109">这包括确保访问核心电子数据展示所需的适当许可，并将电子数据展示保留放在内容位置，以及向 IT、法律和调查团队分配权限，以便他们可以访问和管理事例。</span><span class="sxs-lookup"><span data-stu-id="b36ba-109">This includes ensuring the proper licensing required to access Core eDiscovery and place an eDiscovery hold on content locations, as well as assigning permissions to your IT, legal, and investigation team so they can access and manage cases.</span></span> <span data-ttu-id="b36ba-110">本文还简要概述了使用事例搜索和导出内容的情况。</span><span class="sxs-lookup"><span data-stu-id="b36ba-110">This article also provides a high-level overview of using cases to search for and export content.</span></span>

## <a name="step-1-verify-and-assign-appropriate-licenses"></a><span data-ttu-id="b36ba-111">步骤 1：验证并分配适当的许可证</span><span class="sxs-lookup"><span data-stu-id="b36ba-111">Step 1: Verify and assign appropriate licenses</span></span>

<span data-ttu-id="b36ba-112">核心电子数据展示的许可需要相应的组织订阅和每用户许可。</span><span class="sxs-lookup"><span data-stu-id="b36ba-112">Licensing for Core eDiscovery requires the appropriate organization subscription and per-user licensing.</span></span>

- <span data-ttu-id="b36ba-113">**组织订阅：** 若要访问 Microsoft 365 合规中心或 Office 365 安全 & 合规中心中的核心电子数据展示并使用保留和导出功能，你的组织必须具有 Microsoft 365 E3 或 Office 365 E3 订阅或更高版本。</span><span class="sxs-lookup"><span data-stu-id="b36ba-113">**Organization subscription:** To access Core eDiscovery in the Microsoft 365 compliance center or the Office 365 Security & Compliance Center and use the hold and export features, your organization must have a Microsoft 365 E3 or Office 365 E3 subscription or higher.</span></span>

- <span data-ttu-id="b36ba-114">**每用户许可：** 若要将电子数据展示保留置于邮箱和网站上，必须为用户分配以下许可证之一，具体取决于您的组织订阅：</span><span class="sxs-lookup"><span data-stu-id="b36ba-114">**Per-user licensing:** To place an eDiscovery hold on mailboxes and sites, a user must be assigned one of the following licenses, depending on your organization subscription:</span></span>

  - <span data-ttu-id="b36ba-115">Microsoft 365 E3 或 Office 365 E3 许可证或更高版本</span><span class="sxs-lookup"><span data-stu-id="b36ba-115">A Microsoft 365 E3 or Office 365 E3 license or higher</span></span>

   <span data-ttu-id="b36ba-116">或</span><span class="sxs-lookup"><span data-stu-id="b36ba-116">OR</span></span>

  - <span data-ttu-id="b36ba-117">具有 Exchange Online 计划 2 的 Office 365 E1 许可证Exchange Online Archiving附加许可证</span><span class="sxs-lookup"><span data-stu-id="b36ba-117">Office 365 E1 license with an Exchange Online Plan 2 or Exchange Online Archiving add-on license</span></span>

  <span data-ttu-id="b36ba-118">AND</span><span class="sxs-lookup"><span data-stu-id="b36ba-118">AND</span></span>

  - <span data-ttu-id="b36ba-119">具有 SharePoint Online 计划 2 或 OneDrive for Business 计划 2 附加许可证的 Office 365 E1 许可证</span><span class="sxs-lookup"><span data-stu-id="b36ba-119">Office 365 E1 license with an SharePoint Online Plan 2 or OneDrive for Business Plan 2 add-on license</span></span>
  
  <span data-ttu-id="b36ba-120">若要了解如何分配许可证，请参阅 [向用户分配许可证](../admin/manage/assign-licenses-to-users.md)。</span><span class="sxs-lookup"><span data-stu-id="b36ba-120">For information about how to assign licenses, see [Assign licenses to users](../admin/manage/assign-licenses-to-users.md).</span></span>

<span data-ttu-id="b36ba-121">有关许可的信息：</span><span class="sxs-lookup"><span data-stu-id="b36ba-121">For information about licensing:</span></span>

- <span data-ttu-id="b36ba-122">下载并查看 [Microsoft 365](/office365/servicedescriptions/downloads/microsoft-365-compliance-licensing-comparison.xlsx)合规性许可比较中的"发现&响应"解决方案。</span><span class="sxs-lookup"><span data-stu-id="b36ba-122">Download and see the "Discover & Respond" solution in the [Microsoft 365 Compliance Licensing Comparison](/office365/servicedescriptions/downloads/microsoft-365-compliance-licensing-comparison.xlsx).</span></span>

- <span data-ttu-id="b36ba-123">请参阅 [安全&中心服务说明](/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center)。</span><span class="sxs-lookup"><span data-stu-id="b36ba-123">See the [Security & Compliance Center service description](/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center).</span></span>

## <a name="step-2-assign-ediscovery-permissions"></a><span data-ttu-id="b36ba-124">步骤 2：分配电子数据展示权限</span><span class="sxs-lookup"><span data-stu-id="b36ba-124">Step 2: Assign eDiscovery permissions</span></span>

<span data-ttu-id="b36ba-125">若要访问核心电子数据展示或添加为核心电子数据展示案例的成员，必须为用户分配适当的权限。</span><span class="sxs-lookup"><span data-stu-id="b36ba-125">To access Core eDiscovery or be added as a member of a Core eDiscovery case, a user must be assigned the appropriate permissions.</span></span> <span data-ttu-id="b36ba-126">具体而言，必须将用户添加为 Office 365 安全与合规中心内电子数据展示&组的成员。</span><span class="sxs-lookup"><span data-stu-id="b36ba-126">Specifically, a user must be added as a member of the eDiscovery Manager role group in the Office 365 Security & Compliance Center.</span></span> <span data-ttu-id="b36ba-127">此角色组的成员可以创建和管理核心电子数据展示事例。</span><span class="sxs-lookup"><span data-stu-id="b36ba-127">Members of this role group can create and manage Core eDiscovery cases.</span></span> <span data-ttu-id="b36ba-128">他们可以添加和删除成员、将电子数据展示保留放在用户上、创建和编辑搜索以及从核心电子数据展示案例导出内容。</span><span class="sxs-lookup"><span data-stu-id="b36ba-128">They can add and remove members, place an eDiscovery hold on users, create and edit searches, and export content from a Core eDiscovery case.</span></span>

<span data-ttu-id="b36ba-129">完成以下步骤以将用户添加到电子数据展示管理员角色组：</span><span class="sxs-lookup"><span data-stu-id="b36ba-129">Complete the following steps to add users to the eDiscovery Manager role group:</span></span>

1. <span data-ttu-id="b36ba-130">转到 [https://protection.office.com/permissions](https://protection.office.com/permissions) ，然后使用 Microsoft 365 或 Office 365 组织中管理员帐户的凭据登录。</span><span class="sxs-lookup"><span data-stu-id="b36ba-130">Go to [https://protection.office.com/permissions](https://protection.office.com/permissions) and sign in using the credentials for an admin account in your Microsoft 365 or Office 365 organization.</span></span>

2. <span data-ttu-id="b36ba-131">在" **权限"** 页上，选择 **电子数据展示管理员角色** 组。</span><span class="sxs-lookup"><span data-stu-id="b36ba-131">On the **Permissions** page, select the **eDiscovery Manager** role group.</span></span>

3. <span data-ttu-id="b36ba-132">在"电子数据展示管理器"飞出页面上，单击 **"电子** 数据展示管理器"部分 **旁边的"编辑** "。</span><span class="sxs-lookup"><span data-stu-id="b36ba-132">On the eDiscovery Manager flyout page, click **Edit** next to the **eDiscovery Manager** section.</span></span>

4. <span data-ttu-id="b36ba-133">在编辑角色组向导中的"选择 **电子数据** 展示管理器"页上，单击"**选择发现管理器"。**</span><span class="sxs-lookup"><span data-stu-id="b36ba-133">On the **Choose eDiscovery Manager** page in the edit role group wizard, click **Choose Discovery Manager**.</span></span>

5. <span data-ttu-id="b36ba-134">单击 **"** 添加"，然后选中要添加到角色组的所有用户的复选框。</span><span class="sxs-lookup"><span data-stu-id="b36ba-134">Click **Add** then select the checkbox for all users you want to add to the role group.</span></span>

6. <span data-ttu-id="b36ba-135">单击 **"** 添加"添加所选用户，然后单击"完成 **"。**</span><span class="sxs-lookup"><span data-stu-id="b36ba-135">Click **Add** to add the selected users, and then click **Done**.</span></span>

7. <span data-ttu-id="b36ba-136">单击 **"** 保存"将用户添加到角色组，然后单击 **"关闭"** 以完成此步骤。</span><span class="sxs-lookup"><span data-stu-id="b36ba-136">Click **Save** to add the users to the role group, and then click **Close** to complete the step.</span></span>

### <a name="more-information-about-the-ediscovery-manager-role-group"></a><span data-ttu-id="b36ba-137">有关电子数据展示管理员角色组详细信息</span><span class="sxs-lookup"><span data-stu-id="b36ba-137">More information about the eDiscovery Manager role group</span></span>

<span data-ttu-id="b36ba-138">电子数据展示管理员角色组中有两个子组。</span><span class="sxs-lookup"><span data-stu-id="b36ba-138">There are two subgroups in the eDiscovery Manager role group.</span></span> <span data-ttu-id="b36ba-139">这些子组之间的差异基于作用域。</span><span class="sxs-lookup"><span data-stu-id="b36ba-139">The difference between these subgroups is based on scope.</span></span>

- <span data-ttu-id="b36ba-140">**电子数据展示管理器：** 可查看和管理他们创建或作为成员的核心电子数据展示事例。</span><span class="sxs-lookup"><span data-stu-id="b36ba-140">**eDiscovery Manager:** Can view and manage the Core eDiscovery cases they create or are a member of.</span></span> <span data-ttu-id="b36ba-141">如果另一个电子数据展示管理员创建了一个案例，但没有将第二个电子数据展示管理员添加为该案例的成员，则第二个电子数据展示管理员将无法在合规中心的"核心电子数据展示"页上查看或打开该案例。</span><span class="sxs-lookup"><span data-stu-id="b36ba-141">If another eDiscovery Manager creates a case but doesn't add a second eDiscovery Manager as a member of that case, the second eDiscovery Manager won't be able to view or open the case on the Core eDiscovery page in the compliance center.</span></span> <span data-ttu-id="b36ba-142">通常，可以将您组织中的大多数人员添加到电子数据展示管理员子组。</span><span class="sxs-lookup"><span data-stu-id="b36ba-142">In general, most people in your organization can be added to the eDiscovery Manager subgroup.</span></span>

- <span data-ttu-id="b36ba-143">**电子数据展示管理员：** 可以执行电子数据展示管理员可执行的所有案例管理任务。</span><span class="sxs-lookup"><span data-stu-id="b36ba-143">**eDiscovery Administrator:** Can perform all case management tasks that an eDiscovery Manager can do.</span></span> <span data-ttu-id="b36ba-144">此外，电子数据展示管理员可以：</span><span class="sxs-lookup"><span data-stu-id="b36ba-144">Additionally, an eDiscovery Administrator can:</span></span>

  - <span data-ttu-id="b36ba-145">查看核心电子数据展示页面上列出的所有事例。</span><span class="sxs-lookup"><span data-stu-id="b36ba-145">View all cases that are listed on the Core eDiscovery page.</span></span>
  
  - <span data-ttu-id="b36ba-146">在将自己添加为案件组的成员后，管理组织的任何案例。</span><span class="sxs-lookup"><span data-stu-id="b36ba-146">Manage any case in the organization after they add themselves as a member of the case.</span></span>

  - <span data-ttu-id="b36ba-147">访问和导出组织中任意案例的案例数据。</span><span class="sxs-lookup"><span data-stu-id="b36ba-147">Access and export case data for any case in the organization.</span></span>

  <span data-ttu-id="b36ba-148">由于访问范围广泛，因此组织应只有少数几个作为电子数据展示管理员子组成员的管理员。</span><span class="sxs-lookup"><span data-stu-id="b36ba-148">Because of the broad scope of access, an organization should have only a few admins who are members of the eDiscovery Administrators subgroup.</span></span>

<span data-ttu-id="b36ba-149">有关电子数据展示权限以及分配给电子数据展示管理员角色组的每个角色的说明，请参阅分配 [电子数据展示权限](assign-ediscovery-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="b36ba-149">For more information about eDiscovery permissions and a description of each role that's assigned to the eDiscovery Manager role group, see [Assign eDiscovery permissions](assign-ediscovery-permissions.md).</span></span>

## <a name="step-3-create-a-core-ediscovery-case"></a><span data-ttu-id="b36ba-150">步骤 3：创建核心电子数据展示案例</span><span class="sxs-lookup"><span data-stu-id="b36ba-150">Step 3: Create a Core eDiscovery case</span></span>

<span data-ttu-id="b36ba-151">下一步是创建案例并开始使用核心电子数据展示。</span><span class="sxs-lookup"><span data-stu-id="b36ba-151">The next step is to create a case and start using Core eDiscovery.</span></span> <span data-ttu-id="b36ba-152">完成以下步骤以创建案例并添加成员。</span><span class="sxs-lookup"><span data-stu-id="b36ba-152">Complete the following steps to create a case and add members.</span></span> <span data-ttu-id="b36ba-153">创建案例的用户将自动添加为成员。</span><span class="sxs-lookup"><span data-stu-id="b36ba-153">The user who creates the case is automatically added as a member.</span></span>

1. <span data-ttu-id="b36ba-154">转到 ，然后使用已分配有相应电子数据展示权限的用户帐户 [https://compliance.microsoft.com](https://compliance.microsoft.com) 的凭据登录。</span><span class="sxs-lookup"><span data-stu-id="b36ba-154">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and sign in using the credentials for a user account that has been assigned the appropriate eDiscovery permissions.</span></span> <span data-ttu-id="b36ba-155">组织管理角色组的成员还可以创建核心电子数据展示事例。</span><span class="sxs-lookup"><span data-stu-id="b36ba-155">Members of the Organization Management role group can also create Core eDiscovery cases.</span></span>

2. <span data-ttu-id="b36ba-156">在 Microsoft 365 合规中心的左侧导航窗格中，单击"全部显示"，然后单击"电子数据展示>**核心"。**</span><span class="sxs-lookup"><span data-stu-id="b36ba-156">In the left navigation pane of the Microsoft 365 compliance center, click **Show all**, and then click **eDiscovery > Core**.</span></span>

3. <span data-ttu-id="b36ba-157">在"**核心电子数据展示"** 页上，单击"**创建案例"。**</span><span class="sxs-lookup"><span data-stu-id="b36ba-157">On the **Core eDiscovery** page, click **Create a case**.</span></span>

4. <span data-ttu-id="b36ba-158">在" **新建案例** "飞出页面上，为案例指定 (所需的) ，然后键入可选的案例编号和说明。</span><span class="sxs-lookup"><span data-stu-id="b36ba-158">On the **New case** flyout page, give the case a name (required), and then type an optional case number and description.</span></span> <span data-ttu-id="b36ba-159">案例名称在组织中必须是唯一的。</span><span class="sxs-lookup"><span data-stu-id="b36ba-159">The case name must be unique in your organization.</span></span>

5. <span data-ttu-id="b36ba-160">单击 **"保存** "创建案例。</span><span class="sxs-lookup"><span data-stu-id="b36ba-160">Click **Save** to create the case.</span></span>

   <span data-ttu-id="b36ba-161">新案例创建并显示在核心电子数据展示页面上。</span><span class="sxs-lookup"><span data-stu-id="b36ba-161">The new case is created and displayed on the Core eDiscovery page.</span></span> <span data-ttu-id="b36ba-162">您可能必须单击"刷新 **"** 以显示新案例。</span><span class="sxs-lookup"><span data-stu-id="b36ba-162">You may have to click **Refresh** to display the new case.</span></span> 

## <a name="step-4-optional-add-members-to-a-core-ediscovery-case"></a><span data-ttu-id="b36ba-163">步骤 4 (可选) ：向核心电子数据展示案例添加成员</span><span class="sxs-lookup"><span data-stu-id="b36ba-163">Step 4 (optional): Add members to a Core eDiscovery case</span></span>

<span data-ttu-id="b36ba-164">如果在步骤 3 中创建了一个案例，并且你是将使用该案例的唯一人员，则不必执行此步骤。</span><span class="sxs-lookup"><span data-stu-id="b36ba-164">If you create a case in Step 3 and you're the only person who will use the case, then you don't have to perform this step.</span></span> <span data-ttu-id="b36ba-165">你可以开始使用此案例创建电子数据展示保留、搜索内容或导出搜索结果。</span><span class="sxs-lookup"><span data-stu-id="b36ba-165">You can start using the case to create eDiscovery holds, search for content, or export search results.</span></span> <span data-ttu-id="b36ba-166">如果要向其他用户授予对案例 (或角色) 执行此步骤。</span><span class="sxs-lookup"><span data-stu-id="b36ba-166">Perform this step if you want to give other users (or roles group) access to the case.</span></span>

1. <span data-ttu-id="b36ba-167">在Microsoft 365 合规中心的"核心电子数据展示"页面上，单击要添加成员的情况的名称。</span><span class="sxs-lookup"><span data-stu-id="b36ba-167">On the **Core eDiscovery** page in the Microsoft 365 compliance center, click the name of the case that you want to add members to.</span></span>

2. <span data-ttu-id="b36ba-168">在" **管理此案例** "飞出页面上的"管理成员 **"下**，单击 **"添加** "将成员添加到案例。</span><span class="sxs-lookup"><span data-stu-id="b36ba-168">On the **Manage this case** flyout page, under **Manage members**, click **Add** to add members to the case.</span></span> 

    <span data-ttu-id="b36ba-169">还可以选择将角色组添加为案例的成员。</span><span class="sxs-lookup"><span data-stu-id="b36ba-169">You can also choose to add role group as members of a case.</span></span> <span data-ttu-id="b36ba-170">在"**管理角色组"下，** 单击"**添加"。**</span><span class="sxs-lookup"><span data-stu-id="b36ba-170">Under **Manage role groups**, click **Add**.</span></span> <span data-ttu-id="b36ba-171">只能将您作为成员的角色组分配给案例。</span><span class="sxs-lookup"><span data-stu-id="b36ba-171">You can only assign the role groups that you are a member of to a case.</span></span> <span data-ttu-id="b36ba-172">这是因为角色组控制谁可以将成员分配给电子数据展示案例。</span><span class="sxs-lookup"><span data-stu-id="b36ba-172">That's because role groups control who can assign members to an eDiscovery case.</span></span>

3. <span data-ttu-id="b36ba-173">在可添加为案例成员的人或角色组列表中，单击要添加的 (或角色组) 旁边的复选框。</span><span class="sxs-lookup"><span data-stu-id="b36ba-173">In the list of people or role groups that can be added as members of the case, click the check box next to the names of the people (or role groups) that you want to add.</span></span> <span data-ttu-id="b36ba-174">如果您有一个可添加为成员的大型人员列表，请使用"搜索"框搜索列表中的特定人员。</span><span class="sxs-lookup"><span data-stu-id="b36ba-174">If you have a large list of people who can added as members, use the **Search** box to search for a specific person in the list.</span></span>
  
4. <span data-ttu-id="b36ba-175">选择要添加为案例成员的人或角色组后，单击"添加 **"。**</span><span class="sxs-lookup"><span data-stu-id="b36ba-175">After you select the people or role groups to add as members of the case, click **Add**.</span></span>

5. <span data-ttu-id="b36ba-176">单击 **"** 保存"以保存新案例成员列表。</span><span class="sxs-lookup"><span data-stu-id="b36ba-176">Click **Save** to save the new list of case members.</span></span>

## <a name="explore-the-core-ediscovery-workflow"></a><span data-ttu-id="b36ba-177">探索核心电子数据展示工作流</span><span class="sxs-lookup"><span data-stu-id="b36ba-177">Explore the Core eDiscovery workflow</span></span>

<span data-ttu-id="b36ba-178">为了让你开始使用核心电子数据展示，下面是一个简单的工作流，该工作流为感兴趣的用户创建电子数据展示保留，搜索与调查相关的内容，然后导出该数据以进一步查看。</span><span class="sxs-lookup"><span data-stu-id="b36ba-178">To get you started using core eDiscovery, here's a simple workflow of creating eDiscovery holds for people of interest, searching for content that relevant to your investigation, and then exporting that data for further review.</span></span> <span data-ttu-id="b36ba-179">在每个步骤中，我们还将重点介绍一些你可以浏览的扩展核心电子数据展示功能。</span><span class="sxs-lookup"><span data-stu-id="b36ba-179">In each of these steps, we'll also highlight some extended Core eDiscovery functionality that you can explore.</span></span>

![核心电子数据展示工作流](../media/CoreEdiscoveryWorkflow.png)

1. <span data-ttu-id="b36ba-181">**[创建电子数据展示保留](create-ediscovery-holds.md)**。</span><span class="sxs-lookup"><span data-stu-id="b36ba-181">**[Create an eDiscovery hold](create-ediscovery-holds.md)**.</span></span> <span data-ttu-id="b36ba-182">创建案例后的第一步是 (调查感兴趣的人员的内容位置) 电子数据展示保留设置。</span><span class="sxs-lookup"><span data-stu-id="b36ba-182">The first step after creating a case is placing a hold (also called an *eDiscovery hold*) on the content locations of the people of interest in your investigation.</span></span> <span data-ttu-id="b36ba-183">内容位置包括 Exchange 邮箱、SharePoint 网站、OneDrive 帐户，以及与 Microsoft Teams 和 Office 365 组关联的邮箱和网站。</span><span class="sxs-lookup"><span data-stu-id="b36ba-183">Content locations include Exchange mailboxes, SharePoint sites, OneDrive accounts, as well as the mailboxes and sites associated with Microsoft Teams and Office 365 Groups.</span></span> <span data-ttu-id="b36ba-184">虽然此步骤是可选的，但创建电子数据展示保留会保留调查期间可能与案例相关的内容。</span><span class="sxs-lookup"><span data-stu-id="b36ba-184">While this step is optional, creating an eDiscovery hold preserves content that may be relevant to the case during the investigation.</span></span> <span data-ttu-id="b36ba-185">创建电子数据展示保留时，可以保留特定内容位置中的内容，也可以创建基于查询的保留以仅保留与保留查询匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="b36ba-185">When you create an eDiscovery hold you can preserve all content in specific content locations or you can create a query-based hold to preserve only the content that matches a hold query.</span></span> <span data-ttu-id="b36ba-186">除了保留内容之外，创建电子数据展示保留的另一个很好的理由就是快速搜索保留的内容位置 (而不必在下一步创建和运行搜索时选择每个位置来搜索) 。</span><span class="sxs-lookup"><span data-stu-id="b36ba-186">In addition to preserving content, another good reason to create eDiscovery holds is to quickly search the content locations on hold (instead of having to select each location to search) when you create and run searches in the next step.</span></span> <span data-ttu-id="b36ba-187">完成调查后，可以解除所创建的任何保留。</span><span class="sxs-lookup"><span data-stu-id="b36ba-187">After you complete your investigation, you can release any hold that you created.</span></span>

2. <span data-ttu-id="b36ba-188">**[搜索内容](search-for-content-in-core-ediscovery.md)**。</span><span class="sxs-lookup"><span data-stu-id="b36ba-188">**[Search for content](search-for-content-in-core-ediscovery.md)**.</span></span> <span data-ttu-id="b36ba-189">创建电子数据展示保留后，使用内置搜索工具搜索保留的内容位置。</span><span class="sxs-lookup"><span data-stu-id="b36ba-189">After you create eDiscovery holds, use the built-in search tool to search the content locations on hold.</span></span> <span data-ttu-id="b36ba-190">您还可以搜索其他内容位置，查找可能与案例相关的数据。</span><span class="sxs-lookup"><span data-stu-id="b36ba-190">You can also search other content locations for data that may be relevant to the case.</span></span> <span data-ttu-id="b36ba-191">您可以创建和运行与案例关联的不同搜索。</span><span class="sxs-lookup"><span data-stu-id="b36ba-191">You can create and run different searches that are associated with the case.</span></span> <span data-ttu-id="b36ba-192">您可以使用关键字、属性和条件来构建搜索查询[](keyword-queries-and-search-conditions.md)，这些查询使用与案例最相关的数据返回搜索结果。</span><span class="sxs-lookup"><span data-stu-id="b36ba-192">You use keywords, properties, and conditions to [build search queries](keyword-queries-and-search-conditions.md) that return search results with the data that's most likely relevant to the case.</span></span> <span data-ttu-id="b36ba-193">还可以执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="b36ba-193">You can also:</span></span>

   - <span data-ttu-id="b36ba-194">查看可帮助您优化搜索查询以缩小结果范围的搜索统计信息。</span><span class="sxs-lookup"><span data-stu-id="b36ba-194">View search statistics that may help you refine a search query to narrow the results.</span></span>

   - <span data-ttu-id="b36ba-195">预览搜索结果以快速验证是否已找到相关数据。</span><span class="sxs-lookup"><span data-stu-id="b36ba-195">Preview the search results to quickly verify whether the relevant data is being found.</span></span>

   - <span data-ttu-id="b36ba-196">修改查询并重新运行搜索。</span><span class="sxs-lookup"><span data-stu-id="b36ba-196">Revise a query and rerun the search.</span></span>

3. <span data-ttu-id="b36ba-197">**[导出和下载搜索结果](export-content-in-core-ediscovery.md)**。</span><span class="sxs-lookup"><span data-stu-id="b36ba-197">**[Export and download search results](export-content-in-core-ediscovery.md)**.</span></span> <span data-ttu-id="b36ba-198">搜索并查找与调查相关的数据后，可以将该数据从 Office 365 导出，供调查团队外部人员查看。</span><span class="sxs-lookup"><span data-stu-id="b36ba-198">After you search for and find data that's relevant to your investigation, you can export it out of Office 365 for review by people outside of the investigation team.</span></span> <span data-ttu-id="b36ba-199">导出数据的过程包含两个步骤。</span><span class="sxs-lookup"><span data-stu-id="b36ba-199">Exporting data is a two-step process.</span></span> <span data-ttu-id="b36ba-200">第一步是在 Office 365 中导出搜索的结果（如果为 ）。</span><span class="sxs-lookup"><span data-stu-id="b36ba-200">The first step is to export the results of a search in the case out of Office 365.</span></span> <span data-ttu-id="b36ba-201">这是通过将搜索结果复制到 Microsoft 提供的 Azure 存储位置完成的。</span><span class="sxs-lookup"><span data-stu-id="b36ba-201">This is accomplished by copying the results of a search to a Microsoft-provided Azure Storage location.</span></span> <span data-ttu-id="b36ba-202">下一步是使用电子数据展示导出工具将内容下载到本地计算机。</span><span class="sxs-lookup"><span data-stu-id="b36ba-202">The next step is to use the eDiscovery Export tool to download the content to a local computer.</span></span> <span data-ttu-id="b36ba-203">除了导出的数据文件之外，导出包的 包含还包含导出报告、摘要报表和错误报告。</span><span class="sxs-lookup"><span data-stu-id="b36ba-203">In addition to the exported data files, the contains of the export package also contains an export report, a summary report, and an error report.</span></span>