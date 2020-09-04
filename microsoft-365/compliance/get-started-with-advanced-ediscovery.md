---
title: Microsoft 365 中的高级电子数据展示入门
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: 本文介绍如何开始在 Microsoft 365 中使用高级电子数据展示。 完成几个快速的步骤之后，高级电子数据展示工具即可供使用。 第一步是创建一个事例，然后开始使用高级电子数据展示功能和功能。
ms.openlocfilehash: cc593009337a9b78285fbcf98ad78dbf1899bce1
ms.sourcegitcommit: 9ce9001aa41172152458da27c1c52825355f426d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/03/2020
ms.locfileid: "47357502"
---
# <a name="get-started-with-advanced-ediscovery"></a><span data-ttu-id="3cf85-105">高级电子数据展示入门</span><span class="sxs-lookup"><span data-stu-id="3cf85-105">Get started with Advanced eDiscovery</span></span>

<span data-ttu-id="3cf85-106">Microsoft 365 中的高级电子数据展示提供了一种端到端工作流，用于保留、收集、查看、分析和导出对组织的内部和外部调查做出响应的数据。</span><span class="sxs-lookup"><span data-stu-id="3cf85-106">Advanced eDiscovery in Microsoft 365 provides an end-to-end workflow to preserve, collect, review, analyze, and export data that's responsive to your organization's internal and external investigations.</span></span> <span data-ttu-id="3cf85-107">无需部署高级电子数据展示，但必须有一些先决条件任务，IT 管理员和电子数据展示管理器必须完成这些任务，然后组织才能开始创建并使用高级电子数据展示事例来管理调查。</span><span class="sxs-lookup"><span data-stu-id="3cf85-107">Nothing is needed to deploy Advanced eDiscovery, but there are some prerequisite tasks that an IT admin and eDiscovery manager have to complete before your organization can start to create and use Advanced eDiscovery cases to manage your investigations.</span></span>

<span data-ttu-id="3cf85-108">本文讨论了设置高级电子数据展示所需的步骤。</span><span class="sxs-lookup"><span data-stu-id="3cf85-108">This article discusses the steps necessary to set up Advanced eDiscovery.</span></span> <span data-ttu-id="3cf85-109">这包括确保访问高级电子数据展示所需的正确许可，并将保管人添加到案例，以及将权限分配给法律和调查团队以便他们能够访问和管理案例。</span><span class="sxs-lookup"><span data-stu-id="3cf85-109">This includes ensuring the proper licensing required to access Advanced eDiscovery and add custodians to cases, as well as assigning permissions to your legal and investigation team so they can access and manage cases.</span></span> <span data-ttu-id="3cf85-110">此外，本文还提供了使用案例来管理法律调查的高级电子数据展示工作流的高级别概述。</span><span class="sxs-lookup"><span data-stu-id="3cf85-110">This article also provides a high-level overview of using cases to manage the Advanced eDiscovery workflow for a legal investigation.</span></span>

## <a name="step-1-verify-and-assign-appropriate-licenses"></a><span data-ttu-id="3cf85-111">步骤1：验证并分配适当的许可证</span><span class="sxs-lookup"><span data-stu-id="3cf85-111">Step 1: Verify and assign appropriate licenses</span></span>

<span data-ttu-id="3cf85-112">高级电子数据展示的许可要求相应的组织订阅和每用户许可。</span><span class="sxs-lookup"><span data-stu-id="3cf85-112">Licensing for Advanced eDiscovery requires the appropriate organization subscription and per-user licensing.</span></span>

- <span data-ttu-id="3cf85-113">**组织订阅：** 若要访问 Microsoft 365 合规性中心或安全 & 合规性中心中的高级电子数据展示，您的组织必须具备以下各项之一：</span><span class="sxs-lookup"><span data-stu-id="3cf85-113">**Organization subscription:** To access Advanced eDiscovery in the Microsoft 365 compliance center or the Security & Compliance Center, your organization must have one of the following:</span></span>

  - <span data-ttu-id="3cf85-114">Microsoft 365 E5 或 Office 365 E5 订阅</span><span class="sxs-lookup"><span data-stu-id="3cf85-114">Microsoft 365 E5 or Office 365 E5 subscription</span></span>
  
  - <span data-ttu-id="3cf85-115">具有 E5 合规性附加设备的 Microsoft 365 E3 订阅</span><span class="sxs-lookup"><span data-stu-id="3cf85-115">Microsoft 365 E3 subscription with E5 Compliance add-on</span></span>

  - <span data-ttu-id="3cf85-116">使用 E5 电子数据展示和审核附加版的 Microsoft 365 E3 订阅</span><span class="sxs-lookup"><span data-stu-id="3cf85-116">Microsoft 365 E3 subscription with E5 eDiscovery and Audit add-on</span></span>

  <span data-ttu-id="3cf85-117">如果你没有现有的 Microsoft 365 E5 计划，并且想要尝试高级电子数据展示，则可以 [将 microsoft 365 添加](https://docs.microsoft.com/office365/admin/try-or-buy-microsoft-365) 到现有订阅或注册 Microsoft 365 E5 的 [试用版](https://www.microsoft.com/microsoft-365/enterprise) 。</span><span class="sxs-lookup"><span data-stu-id="3cf85-117">If you don't have an existing Microsoft 365 E5 plan and want to try Advanced eDiscovery, you can [add Microsoft 365](https://docs.microsoft.com/office365/admin/try-or-buy-microsoft-365) to your existing subscription or [sign up for a trial](https://www.microsoft.com/microsoft-365/enterprise) of Microsoft 365 E5.</span></span>

- <span data-ttu-id="3cf85-118">**每用户许可：** 若要在提前电子数据展示事例中将用户添加为保管人，则必须为该用户分配以下许可证之一，具体取决于您的组织订阅：</span><span class="sxs-lookup"><span data-stu-id="3cf85-118">**Per-user licensing:** To add a user as a custodian in an Advance eDiscovery case, that user must be assigned one of the following licenses, depending on your organization subscription:</span></span>

  - <span data-ttu-id="3cf85-119">Microsoft 365：必须为用户分配 Microsoft 365 E5 许可证、E5 合规性附加许可证或 E5 电子数据展示和审核附加许可证。</span><span class="sxs-lookup"><span data-stu-id="3cf85-119">Microsoft 365: Users must be assigned a Microsoft 365 E5 license, an E5 Compliance add-on license, or an E5 eDiscovery and Audit add-on license.</span></span>

  - <span data-ttu-id="3cf85-120">Office 365：必须为用户分配 Office 365 E5 许可证。</span><span class="sxs-lookup"><span data-stu-id="3cf85-120">Office 365: Users must be assigned an Office 365 E5 license.</span></span>

   <span data-ttu-id="3cf85-121">有关如何分配许可证的信息，请参阅向 [用户分配许可证](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)。</span><span class="sxs-lookup"><span data-stu-id="3cf85-121">For information about how to assign licenses, see [Assign licenses to users](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users).</span></span>

> [!NOTE]
> <span data-ttu-id="3cf85-122">用户只需将 E5 许可证 (或相应的附加许可证) 添加为高级电子数据展示事例的 "保管人"。</span><span class="sxs-lookup"><span data-stu-id="3cf85-122">Users only need an E5 license (or the appropriate add-on license) to be added as custodians to an Advanced eDiscovery case.</span></span> <span data-ttu-id="3cf85-123">使用高级电子数据展示来管理案例和审阅事例数据的 IT 管理员、电子数据展示管理者、律师、paralegals 或调查人员不需要 E5 或附加许可证。</span><span class="sxs-lookup"><span data-stu-id="3cf85-123">IT admins, eDiscovery managers, lawyers, paralegals, or investigators who use Advanced eDiscovery to manage cases and review case data don't need an E5 or add-on license.</span></span>

## <a name="step-2-assign-ediscovery-permissions"></a><span data-ttu-id="3cf85-124">步骤2：分配电子数据展示权限</span><span class="sxs-lookup"><span data-stu-id="3cf85-124">Step 2: Assign eDiscovery permissions</span></span>

<span data-ttu-id="3cf85-125">若要访问高级电子数据展示或添加为高级电子数据展示事例的成员，则必须为用户分配适当的权限。</span><span class="sxs-lookup"><span data-stu-id="3cf85-125">To access Advanced eDiscovery or added as a member of an Advanced eDiscovery case, a user must be assigned the appropriate permissions.</span></span> <span data-ttu-id="3cf85-126">具体来说，用户必须作为安全 & 合规中心中的电子数据展示管理器角色组的成员进行添加。</span><span class="sxs-lookup"><span data-stu-id="3cf85-126">Specifically, a user must be added as a member of the eDiscovery Manager role group in the Security & Compliance Center.</span></span> <span data-ttu-id="3cf85-127">此角色组的成员可以创建和管理高级电子数据展示事例。</span><span class="sxs-lookup"><span data-stu-id="3cf85-127">Members of this role group can create and manage Advanced eDiscovery cases.</span></span> <span data-ttu-id="3cf85-128">他们可以添加和删除成员，将保管人和内容位置置于保留状态，管理法律封存通知，创建和编辑与案例关联的搜索，将搜索结果添加到审阅集，分析审阅集中的数据，以及从高级电子数据展示事例中导出和下载。</span><span class="sxs-lookup"><span data-stu-id="3cf85-128">They can add and remove members, place custodians and content locations on hold, manage legal hold notifications, create and edit searches associated in a case, add search results to a review set, analyze data in a review set, and export and download from an Advanced eDiscovery case.</span></span>

<span data-ttu-id="3cf85-129">完成以下步骤以将用户添加到电子数据展示管理器角色组：</span><span class="sxs-lookup"><span data-stu-id="3cf85-129">Complete the following steps to add users to the eDiscovery Manager role group:</span></span>

1. <span data-ttu-id="3cf85-130">转到 [https://protection.office.com/permissions](https://protection.office.com/permissions) 并使用 Microsoft 365 组织中的管理员帐户的凭据登录。</span><span class="sxs-lookup"><span data-stu-id="3cf85-130">Go to [https://protection.office.com/permissions](https://protection.office.com/permissions) and sign in using the credentials for an admin account in your Microsoft 365 organization.</span></span>

2. <span data-ttu-id="3cf85-131">在 " **权限** " 页上，选择 " **电子数据展示管理器** " 角色组。</span><span class="sxs-lookup"><span data-stu-id="3cf85-131">On the **Permissions** page, select the **eDiscovery Manager** role group.</span></span>

3. <span data-ttu-id="3cf85-132">在 "电子数据展示管理器" 弹出页面上，单击**电子数据展示管理器**部分旁边的 "**编辑**"。</span><span class="sxs-lookup"><span data-stu-id="3cf85-132">On the eDiscovery Manager flyout page, click **Edit** next to the **eDiscovery Manager** section.</span></span>

4. <span data-ttu-id="3cf85-133">在编辑角色组向导中的 " **选择电子数据展示管理器** " 页上，单击 " **选择发现管理器**"。</span><span class="sxs-lookup"><span data-stu-id="3cf85-133">On the **Choose eDiscovery Manager** page in the edit role group wizard, click **Choose Discovery Manager**.</span></span>

5. <span data-ttu-id="3cf85-134">单击 " **添加** "，然后选中要添加到角色组的所有用户的复选框。</span><span class="sxs-lookup"><span data-stu-id="3cf85-134">Click **Add** then select the checkbox for all users you want to add to the role group.</span></span>

6. <span data-ttu-id="3cf85-135">单击 " **添加** " 以添加选定的用户，然后单击 " **完成**"。</span><span class="sxs-lookup"><span data-stu-id="3cf85-135">Click **Add** to add the selected users, and then click **Done**.</span></span>

7. <span data-ttu-id="3cf85-136">单击 " **保存** " 将用户添加到角色组，然后单击 " **关闭** " 完成步骤。</span><span class="sxs-lookup"><span data-stu-id="3cf85-136">Click **Save** to add the users to the role group, and then click **Close** to complete the step.</span></span>

### <a name="more-information-about-the-ediscovery-manager-role-group"></a><span data-ttu-id="3cf85-137">有关电子数据展示管理器角色组的详细信息</span><span class="sxs-lookup"><span data-stu-id="3cf85-137">More information about the eDiscovery Manager role group</span></span>

<span data-ttu-id="3cf85-138">"电子数据展示管理器" 角色组中有两个子组。</span><span class="sxs-lookup"><span data-stu-id="3cf85-138">There are two subgroups in the eDiscovery Manager role group.</span></span> <span data-ttu-id="3cf85-139">这些子组之间的差异基于作用域。</span><span class="sxs-lookup"><span data-stu-id="3cf85-139">The difference between these subgroups is based on scope.</span></span>

- <span data-ttu-id="3cf85-140">**电子数据展示管理器：** 可以查看和管理他们创建的或为其成员的高级电子数据展示事例。</span><span class="sxs-lookup"><span data-stu-id="3cf85-140">**eDiscovery Manager:** Can view and manage the Advanced eDiscovery cases they create or are a member of.</span></span> <span data-ttu-id="3cf85-141">如果另一个电子数据展示管理器创建了一个事例，但未将另一个电子数据展示管理器添加为这种情况的成员，则第二个电子数据展示管理器将无法在合规性中心的高级电子数据展示页面上查看或打开该事例。</span><span class="sxs-lookup"><span data-stu-id="3cf85-141">If another eDiscovery Manager creates a case but doesn't add a second eDiscovery Manager as a member of that case, the second eDiscovery Manager won't be able to view or open the case on the Advanced eDiscovery page in the compliance center.</span></span> <span data-ttu-id="3cf85-142">通常，可以将组织中的大多数用户添加到电子数据展示管理器子组。</span><span class="sxs-lookup"><span data-stu-id="3cf85-142">In general, most people in your organization can be added to the eDiscovery Manager subgroup.</span></span>

- <span data-ttu-id="3cf85-143">**电子数据展示管理员：** 可以执行电子数据展示管理器可以执行的所有案例管理任务。</span><span class="sxs-lookup"><span data-stu-id="3cf85-143">**eDiscovery Administrator:** Can perform all case management tasks that an eDiscovery Manager can do.</span></span> <span data-ttu-id="3cf85-144">此外，电子数据展示管理员可以：</span><span class="sxs-lookup"><span data-stu-id="3cf85-144">Additionally, an eDiscovery Administrator can:</span></span>

  - <span data-ttu-id="3cf85-145">查看高级电子数据展示页面上列出的所有事例。</span><span class="sxs-lookup"><span data-stu-id="3cf85-145">View all cases that are listed on the Advanced eDiscovery page.</span></span>
  
  - <span data-ttu-id="3cf85-146">在组织中管理任何事例，然后在将自己添加为案例成员。</span><span class="sxs-lookup"><span data-stu-id="3cf85-146">Manage any case in the organization after they add themselves as a member of the case.</span></span>

  - <span data-ttu-id="3cf85-147">组织中的任何事例的访问和导出事例数据。</span><span class="sxs-lookup"><span data-stu-id="3cf85-147">Access and export case data for any case in the organization.</span></span>

  <span data-ttu-id="3cf85-148">由于访问范围很广，组织应仅有几个作为电子数据展示管理员子组成员的管理员。</span><span class="sxs-lookup"><span data-stu-id="3cf85-148">Because of the broad scope of access, an organization should have only a few admins who are members of the eDiscovery Administrators subgroup.</span></span>

<span data-ttu-id="3cf85-149">有关电子数据展示权限的详细信息以及分配给电子数据展示管理器角色组的每个角色的说明，请参阅 [分配电子数据展示权限](assign-ediscovery-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="3cf85-149">For more information about eDiscovery permissions and a description of each role that's assigned to the eDiscovery Manager role group, see [Assign eDiscovery permissions](assign-ediscovery-permissions.md).</span></span>

## <a name="step-3-configure-global-settings-for-advanced-ediscovery"></a><span data-ttu-id="3cf85-150">步骤3：为高级电子数据展示配置全局设置</span><span class="sxs-lookup"><span data-stu-id="3cf85-150">Step 3: Configure global settings for Advanced eDiscovery</span></span>

<span data-ttu-id="3cf85-151">在贵组织中的人员开始创建和用例之前，要完成的最后一步是配置适用于组织中的所有案例的全局设置。</span><span class="sxs-lookup"><span data-stu-id="3cf85-151">The last step to complete before people in your organization start to create and use cases is to configure global settings that apply to all cases in your organization.</span></span> <span data-ttu-id="3cf85-152">目前，唯一的全局设置是 *律师-客户端特权检测* (更多全局设置将在将来的) 中可用。</span><span class="sxs-lookup"><span data-stu-id="3cf85-152">At this time, the only global setting is *attorney-client privilege detection* (more global settings will be available in the future).</span></span> <span data-ttu-id="3cf85-153">此设置使律师-客户端权限模型能够在您分析评审集内的数据时运行。</span><span class="sxs-lookup"><span data-stu-id="3cf85-153">This setting enables the attorney-client privilege model to run when you analyze data in a review set.</span></span> <span data-ttu-id="3cf85-154">模型使用机器学习确定文档包含性质合法的内容的可能性。</span><span class="sxs-lookup"><span data-stu-id="3cf85-154">The model uses machine learning to determine the likelihood that a document contains content that is legal in nature.</span></span> <span data-ttu-id="3cf85-155">它还会将文档的参与者与您在设置模型) 时提交的律师列表 (进行比较，以确定文档是否至少有一个作为律师的参与者。</span><span class="sxs-lookup"><span data-stu-id="3cf85-155">It also compares the participants of documents with an attorney list (that you submit when setting up the model) to determine if a document has at least one participant who is an attorney.</span></span>

<span data-ttu-id="3cf85-156">有关设置和使用律师-客户端权限检测模型的详细信息，请参阅 [在高级电子数据展示中设置律师-客户端权限检测](attorney-privilege-detection.md)。</span><span class="sxs-lookup"><span data-stu-id="3cf85-156">For more information about setting up and using the attorney-client privilege detection model, see [Set up attorney-client privilege detection in Advanced eDiscovery](attorney-privilege-detection.md).</span></span>

> [!NOTE]
> <span data-ttu-id="3cf85-157">这是一种可随时执行的可选步骤。</span><span class="sxs-lookup"><span data-stu-id="3cf85-157">This is an optional step that you can perform anytime.</span></span> <span data-ttu-id="3cf85-158">不实现律师-客户端特权检测模型不会阻止您创建和使用高级电子数据展示事例。</span><span class="sxs-lookup"><span data-stu-id="3cf85-158">Not implementing the attorney-client privilege detection model doesn't prevent you from creating and using Advanced eDiscovery cases.</span></span>

## <a name="step-4-create-an-advanced-ediscovery-case"></a><span data-ttu-id="3cf85-159">步骤4：创建高级电子数据展示事例</span><span class="sxs-lookup"><span data-stu-id="3cf85-159">Step 4: Create an Advanced eDiscovery case</span></span>

<span data-ttu-id="3cf85-160">下一步是创建一个事例，并开始使用高级电子数据展示。</span><span class="sxs-lookup"><span data-stu-id="3cf85-160">The next step is to create a case and start using Advanced eDiscovery.</span></span> <span data-ttu-id="3cf85-161">完成以下步骤以创建事例并添加成员。</span><span class="sxs-lookup"><span data-stu-id="3cf85-161">Complete the following steps to create a case and add members.</span></span> <span data-ttu-id="3cf85-162">创建案例的用户将自动添加为成员。</span><span class="sxs-lookup"><span data-stu-id="3cf85-162">The user who creates the case is automatically added as a member.</span></span>

1. <span data-ttu-id="3cf85-163">转到 [https://compliance.microsoft.com](https://compliance.microsoft.com) 并使用已为其分配了相应电子数据展示权限的用户帐户的凭据登录。</span><span class="sxs-lookup"><span data-stu-id="3cf85-163">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and sign in using the credentials for user account that has been assigned the appropriate eDiscovery permissions.</span></span> <span data-ttu-id="3cf85-164">组织管理角色组的成员也可以创建高级电子数据展示事例。</span><span class="sxs-lookup"><span data-stu-id="3cf85-164">Members of the Organization Management role group can also create Advanced eDiscovery cases.</span></span>

2. <span data-ttu-id="3cf85-165">在 Microsoft 365 合规性中心的左侧导航窗格中，单击 " **全部显示**"，然后单击 " **电子数据展示 > 高级**"。</span><span class="sxs-lookup"><span data-stu-id="3cf85-165">In the left navigation pane of the Microsoft 365 compliance center, click **Show all**, and then click **eDiscovery > Advanced**.</span></span>

3. <span data-ttu-id="3cf85-166">在 " **高级电子数据展示** " 页上，单击 " **事例** " 选项卡，然后单击 " **创建事例**"。</span><span class="sxs-lookup"><span data-stu-id="3cf85-166">On the **Advanced eDiscovery** page, click the **Cases** tab, and then click **Create a case**.</span></span>

4. <span data-ttu-id="3cf85-167">在 **新的电子数据展示事例** 弹出页面上，为事例提供名称 (必需的) ，然后键入一个可选的事例编号和说明。</span><span class="sxs-lookup"><span data-stu-id="3cf85-167">On the **New eDiscovery case** flyout page, give the case a name (required), and then type an optional case number and description.</span></span> <span data-ttu-id="3cf85-168">案例名称在您的组织中必须是唯一的。</span><span class="sxs-lookup"><span data-stu-id="3cf85-168">The case name must be unique in your organization.</span></span>

5. <span data-ttu-id="3cf85-169">单击 " **保存** " 以创建事例。</span><span class="sxs-lookup"><span data-stu-id="3cf85-169">Click **Save** to create the case.</span></span>

   <span data-ttu-id="3cf85-170">将创建新事例，并显示新事例中的 " **设置** " 选项卡。</span><span class="sxs-lookup"><span data-stu-id="3cf85-170">The new case is created and the **Settings** tab in the new case is displayed.</span></span> 

6. <span data-ttu-id="3cf85-171">在 "**设置**" 选项卡上的 "**访问 & 权限**" 磁贴中，单击 "**选择**"，然后单击 "**更新**"。</span><span class="sxs-lookup"><span data-stu-id="3cf85-171">In the **Access & permissions** tile on the **Settings** tab, click **Select**, and then click **Update**.</span></span>

7. <span data-ttu-id="3cf85-172">单击“更新”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="3cf85-172">Click **Update**.</span></span>

8. <span data-ttu-id="3cf85-173">在 " **管理此案例** " 弹出页面上的 " **管理成员**" 下，单击 " **添加** " 向事例添加成员。</span><span class="sxs-lookup"><span data-stu-id="3cf85-173">On the **Manage this case** flyout page, under **Manage members**, click **Add** to add members to the case.</span></span>

9. <span data-ttu-id="3cf85-174">在 "人员" 列表中，选中要向事例添加的人员姓名旁边的复选框。</span><span class="sxs-lookup"><span data-stu-id="3cf85-174">In the list of people, select the check box next to the names of the people that you want to add to the case.</span></span> <span data-ttu-id="3cf85-175">如上文所述，请确保您添加到此案例的人员已分配了相应的电子数据展示权限。</span><span class="sxs-lookup"><span data-stu-id="3cf85-175">As previously explained, be sure that the people you add to the case have been assigned the appropriate eDiscovery permissions.</span></span>

10. <span data-ttu-id="3cf85-176">选择要添加为事例成员的人员后，单击 " **添加**"。</span><span class="sxs-lookup"><span data-stu-id="3cf85-176">After you've selected the people to add as members of the case, click **Add**.</span></span>

11. <span data-ttu-id="3cf85-177">在 " **管理此事例** " 弹出页面中，单击 " **保存** " 以保存新的事例成员列表。</span><span class="sxs-lookup"><span data-stu-id="3cf85-177">In the **Manage this case** flyout page, click **Save** to save the new list of case members.</span></span>

12. <span data-ttu-id="3cf85-178">单击 " **主页** " 选项卡转到 "案例" 主页。</span><span class="sxs-lookup"><span data-stu-id="3cf85-178">Click the **Home** tab to go to the case home page.</span></span>

## <a name="explore-the-advanced-ediscovery-workflow"></a><span data-ttu-id="3cf85-179">探索高级电子数据展示工作流</span><span class="sxs-lookup"><span data-stu-id="3cf85-179">Explore the Advanced eDiscovery workflow</span></span>

<span data-ttu-id="3cf85-180">为了让你开始使用高级电子数据展示，下面是一个与 [常见电子数据展示做法](overview-ediscovery-20.md#alignment-with-edrm)相适应的简单工作流。</span><span class="sxs-lookup"><span data-stu-id="3cf85-180">To get you started using Advanced eDiscovery, here's a simple workflow that aligns with [common eDiscovery practices](overview-ediscovery-20.md#alignment-with-edrm).</span></span> <span data-ttu-id="3cf85-181">在上述每个步骤中，我们还将重点介绍你可以探索的一些扩展高级电子数据展示功能。</span><span class="sxs-lookup"><span data-stu-id="3cf85-181">In each of these steps, we'll also highlight some extended Advanced eDiscovery functionality that you can explore.</span></span>

![高级电子数据展示工作流](../media/AeDWorkflow.png)

1. <span data-ttu-id="3cf85-183">向**[事例添加保管人](add-custodians-to-case.md)**。</span><span class="sxs-lookup"><span data-stu-id="3cf85-183">**[Add custodians to a case](add-custodians-to-case.md)**.</span></span> <span data-ttu-id="3cf85-184">创建事例的第一步是添加保管人。</span><span class="sxs-lookup"><span data-stu-id="3cf85-184">The first step after creating a case is to add custodians.</span></span> <span data-ttu-id="3cf85-185">*管理员*是具有对文档或电子文件的管理控制的人员，可能与案例相关。</span><span class="sxs-lookup"><span data-stu-id="3cf85-185">A *custodian* is a person having administrative control of a document or electronic file that may be relevant to the case.</span></span> <span data-ttu-id="3cf85-186">以下是 (发生的一些操作，也可以在向事例添加保管人时执行) 操作：</span><span class="sxs-lookup"><span data-stu-id="3cf85-186">Here are some things that happen (or that you can do) when you add custodians to a case:</span></span>

   - <span data-ttu-id="3cf85-187">如果保管人的 Exchange 邮箱、OneDrive 帐户以及保管人所属的任何 Microsoft 团队或 Yammer 组中的数据，都可以在案例中 "标记" 为 "custodial" 数据。</span><span class="sxs-lookup"><span data-stu-id="3cf85-187">Data in the custodian's Exchange mailbox, OneDrive account, and any Microsoft Teams or Yammer groups that the custodian is a member of can be "marked" as custodial data in the case.</span></span>
  
   - <span data-ttu-id="3cf85-188">由名为 " *高级索引*) " 的进程对保管人数据进行重新编制索引 (。</span><span class="sxs-lookup"><span data-stu-id="3cf85-188">Custodian data is re-indexed (by a process called *Advanced indexing*).</span></span> <span data-ttu-id="3cf85-189">这有助于在下一步中优化搜索。</span><span class="sxs-lookup"><span data-stu-id="3cf85-189">This helps optimize searching for it in the next step.</span></span>
  
   - <span data-ttu-id="3cf85-190">您可以对保管人数据设置保留。</span><span class="sxs-lookup"><span data-stu-id="3cf85-190">You can place a hold on custodian data.</span></span> <span data-ttu-id="3cf85-191">这将保留在调查过程中可能与事例相关的数据。</span><span class="sxs-lookup"><span data-stu-id="3cf85-191">This preserves data that may be relevant to the case during the investigation.</span></span>
  
   - <span data-ttu-id="3cf85-192">可以将其他数据源与保管人 (相关联。例如，可以将 SharePoint 网站或 Microsoft 365 组与保管人) 相关联，以便可以对这些数据进行重新编制索引、置于保留和搜索，就像在保管人的邮箱或 OneDrive 帐户中的数据一样。</span><span class="sxs-lookup"><span data-stu-id="3cf85-192">You can associate other data sources with a custodian (for example, you can associate a SharePoint site or Microsoft 365 Group with a custodian) so this data can be re-indexed, placed on hold, and searched, just like the data in the custodian's mailbox or OneDrive account.</span></span>

   - <span data-ttu-id="3cf85-193">您可以使用高级电子数据展示中的 [通信工作流](managing-custodian-communications.md) 向保管人发送合法保留通知。</span><span class="sxs-lookup"><span data-stu-id="3cf85-193">You can use the [communications workflow](managing-custodian-communications.md) in Advanced eDiscovery to send a legal hold notification to custodians.</span></span>

2. <span data-ttu-id="3cf85-194">**[在 custodial 数据源中搜索与事例相关的数据](collecting-data-for-ediscovery.md)**。</span><span class="sxs-lookup"><span data-stu-id="3cf85-194">**[Search custodial data sources for data relevant to the case](collecting-data-for-ediscovery.md)**.</span></span> <span data-ttu-id="3cf85-195">向事例添加保管人后，使用内置搜索工具在保管人数据位置中搜索可能与事例相关的数据。</span><span class="sxs-lookup"><span data-stu-id="3cf85-195">After you add custodians to a case, use the built-in search tool to search the custodian data locations for data that may be relevant to the case.</span></span> <span data-ttu-id="3cf85-196">使用关键字、属性和条件 [构建搜索查询](building-search-queries.md) ，以使用最可能与案例相关的数据返回搜索结果。</span><span class="sxs-lookup"><span data-stu-id="3cf85-196">You use keywords, properties, and conditions to [build search queries](building-search-queries.md) that return search results with the data that's most likely relevant to the case.</span></span> <span data-ttu-id="3cf85-197">还可以执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="3cf85-197">You can also:</span></span>

   - <span data-ttu-id="3cf85-198">查看可帮助您优化搜索查询以缩小结果范围的 [搜索统计信息](search-statistics.md) 。</span><span class="sxs-lookup"><span data-stu-id="3cf85-198">View [search statistics](search-statistics.md) that may help you refine a search query to narrow the results.</span></span>

   - <span data-ttu-id="3cf85-199">预览搜索结果以快速验证是否找到了相关数据。</span><span class="sxs-lookup"><span data-stu-id="3cf85-199">Preview the search results to quickly verify whether the relevant data is being found.</span></span>

   - <span data-ttu-id="3cf85-200">修订查询并重新运行搜索。</span><span class="sxs-lookup"><span data-stu-id="3cf85-200">Revise a query and re-run the search.</span></span>

3. <span data-ttu-id="3cf85-201">**[将数据添加到审阅集](add-data-to-review-set.md)**。</span><span class="sxs-lookup"><span data-stu-id="3cf85-201">**[Add data to a review set](add-data-to-review-set.md)**.</span></span> <span data-ttu-id="3cf85-202">配置并验证搜索是否返回所需数据之后，下一步是将搜索结果添加到审阅集。</span><span class="sxs-lookup"><span data-stu-id="3cf85-202">Once you've configured and verified that a search returns the desired data, the next step is to add the search results to a review set.</span></span> <span data-ttu-id="3cf85-203">将数据添加到审阅集时，会将项目从其原始位置复制到安全的 Azure 存储位置。</span><span class="sxs-lookup"><span data-stu-id="3cf85-203">When you add data to a review set, items are copied from their original location to a secure Azure Storage location.</span></span> <span data-ttu-id="3cf85-204">再次对数据重新编制索引，以便在审阅和分析评审集中的项时对其进行全面和快速的搜索优化。</span><span class="sxs-lookup"><span data-stu-id="3cf85-204">The data is re-indexed again to optimize it for thorough and fast searches when reviewing and analyzing items in the review set.</span></span> <span data-ttu-id="3cf85-205">此外，还可以 [将非 Office 365 数据添加到审阅集中](load-non-office-365-data-into-a-review-set.md)。</span><span class="sxs-lookup"><span data-stu-id="3cf85-205">Additionally, you can also [add non-Office 365 data into a review set](load-non-office-365-data-into-a-review-set.md).</span></span>

   <span data-ttu-id="3cf85-206">此外，还有一种特殊的审阅集，可向其添加数据，称为 *对话审阅集*。</span><span class="sxs-lookup"><span data-stu-id="3cf85-206">There's also a special kind of review set that you can add data to, called a *conversation review set*.</span></span> <span data-ttu-id="3cf85-207">这些类型的审查集提供了会话重建功能，用于重构、查看和导出像 Microsoft 团队中的对话对话。</span><span class="sxs-lookup"><span data-stu-id="3cf85-207">These types of reviews sets provide conversation reconstruction capabilities to reconstruct, review, and export threaded conversations like those in Microsoft Teams.</span></span> <span data-ttu-id="3cf85-208">有关详细信息，请参阅 [在高级电子数据展示中查看对话](conversation-review-sets.md)。</span><span class="sxs-lookup"><span data-stu-id="3cf85-208">For more information, see [Review conversations in Advanced eDiscovery](conversation-review-sets.md).</span></span>

4. <span data-ttu-id="3cf85-209">**查看和分析评审集中的数据**。</span><span class="sxs-lookup"><span data-stu-id="3cf85-209">**Review and analyze data in a review set**.</span></span> <span data-ttu-id="3cf85-210">现在，数据处于审阅集中，您可以使用各种工具和功能来查看和分析事例数据，目的是将数据集的目标减少为与您调查的案例最相关的内容。</span><span class="sxs-lookup"><span data-stu-id="3cf85-210">Now that data is in a review set, you can use a wide-variety of tools and capabilities to view and analyze the case data with the goal of reducing the data set to what is most relevant to the case you're investigation.</span></span> <span data-ttu-id="3cf85-211">下面列出了可在此过程中使用的一些工具和功能。</span><span class="sxs-lookup"><span data-stu-id="3cf85-211">Here's a list of some tools and capabilities that you can use during this process.</span></span>

   - <span data-ttu-id="3cf85-212">[查看文档](view-documents-in-review-set.md)。</span><span class="sxs-lookup"><span data-stu-id="3cf85-212">[View documents](view-documents-in-review-set.md).</span></span> <span data-ttu-id="3cf85-213">这包括查看评审集中每个文档的元数据，以及在文档的本机版本或文本版本中查看该文档。</span><span class="sxs-lookup"><span data-stu-id="3cf85-213">This includes viewing the metadata for each document in a review set, and viewing the document in its native version or text version.</span></span>

   - <span data-ttu-id="3cf85-214">[创建查询和筛选器](review-set-search.md)。</span><span class="sxs-lookup"><span data-stu-id="3cf85-214">[Create queries and filters](review-set-search.md).</span></span> <span data-ttu-id="3cf85-215">您可以使用各种搜索条件来创建搜索查询 (包括搜索所有 [文件元数据属性](document-metadata-fields-in-advanced-ediscovery.md) 的能力) 进一步优化和挑选对事例最相关的事例数据。</span><span class="sxs-lookup"><span data-stu-id="3cf85-215">You create search queries using a variety of search criteria (including the ability to search all [file metadata properties](document-metadata-fields-in-advanced-ediscovery.md)) to further refine and cull the case data to what is most relevant to the case.</span></span> <span data-ttu-id="3cf85-216">您还可以使用审阅设置筛选器将其他条件快速应用于搜索查询的结果，以进一步优化这些结果。</span><span class="sxs-lookup"><span data-stu-id="3cf85-216">You can also use review set filters to quickly apply additional conditions to the results of a search query to further refine those results.</span></span> 

   - <span data-ttu-id="3cf85-217">[创建和使用标记](tagging-documents.md)。</span><span class="sxs-lookup"><span data-stu-id="3cf85-217">[Create and use tags](tagging-documents.md).</span></span> <span data-ttu-id="3cf85-218">您可以对审阅集内的文档应用标记，以确定哪些响应速度 (或对事例不响应) 然后在创建搜索查询以包含或排除带标签的文档时使用这些标记。</span><span class="sxs-lookup"><span data-stu-id="3cf85-218">You can apply tags to documents in a review set to identify which are responsive (or non-responsive to the case) and then use those tags when creating search queries to include or exclude the tagged documents.</span></span> <span data-ttu-id="3cf85-219">您还可以进行标记以确定要导出的文档。</span><span class="sxs-lookup"><span data-stu-id="3cf85-219">You can also tagging to determine which documents to export.</span></span>

   - <span data-ttu-id="3cf85-220">对[文档添加批注和密文](view-documents-in-review-set.md#annotate-view)。</span><span class="sxs-lookup"><span data-stu-id="3cf85-220">[Annotate and redact documents](view-documents-in-review-set.md#annotate-view).</span></span> <span data-ttu-id="3cf85-221">您可以在审阅中使用批注工具对文档中的内容进行批注和在文档中对内容进行密文标记作为工作产品。</span><span class="sxs-lookup"><span data-stu-id="3cf85-221">You can use the annotation tool in a review to annotate documents and redact content in documents as work product.</span></span> <span data-ttu-id="3cf85-222">在审阅过程中，我们会生成 PDF 版本的批注或编辑文档，以降低导出 unredacted 本机版本的文档的风险。</span><span class="sxs-lookup"><span data-stu-id="3cf85-222">We generate a PDF version of an annotated or redacted document during review to reduce the risk of exporting the unredacted native version of the document.</span></span>

   - <span data-ttu-id="3cf85-223">[分析事例数据](analyzing-data-in-review-set.md)。</span><span class="sxs-lookup"><span data-stu-id="3cf85-223">[Analyze case data](analyzing-data-in-review-set.md).</span></span> <span data-ttu-id="3cf85-224">高级电子数据展示中的分析功能非常强大。</span><span class="sxs-lookup"><span data-stu-id="3cf85-224">The analytics functionality in Advanced eDiscovery is powerful.</span></span> <span data-ttu-id="3cf85-225">在对评审设置中的数据运行分析之后，我们会执行分析，如接近重复检测、电子邮件线程和主题，可帮助减少必须查看的文档量。</span><span class="sxs-lookup"><span data-stu-id="3cf85-225">After you run analytics on the data in review set, we perform analysis such as near duplicate detection, email threading, and themes that can help reduce the volume of documents that you have to review.</span></span> <span data-ttu-id="3cf85-226">我们还会生成汇总运行分析结果的分析报告。</span><span class="sxs-lookup"><span data-stu-id="3cf85-226">We also generate an Analytics reports that summarize the result of running analytics.</span></span> <span data-ttu-id="3cf85-227">如前所述，运行分析还运行 [律师-客户端特权检测模型](attorney-privilege-detection.md#use-the-attorney-client-privilege-detection-model)。</span><span class="sxs-lookup"><span data-stu-id="3cf85-227">As previously explained, running analytics also runs [the attorney-client privilege detection model](attorney-privilege-detection.md#use-the-attorney-client-privilege-detection-model).</span></span>

5. <span data-ttu-id="3cf85-228">**导出和下载事例数据**。</span><span class="sxs-lookup"><span data-stu-id="3cf85-228">**Export and download case data**.</span></span> <span data-ttu-id="3cf85-229">收集、查看和分析事例数据的最后一步是将其导出到高级电子数据展示中，以供外部审阅或调查团队之外的人员进行审阅。</span><span class="sxs-lookup"><span data-stu-id="3cf85-229">A final step after collecting, reviewing, and analyzing case data is to export it out of Advanced eDiscovery for external review or for review by people outside of the investigation team.</span></span> <span data-ttu-id="3cf85-230">导出数据的过程分为两个步骤。</span><span class="sxs-lookup"><span data-stu-id="3cf85-230">Exporting data is a two-step process.</span></span> <span data-ttu-id="3cf85-231">第一步是将数据 [导出](export-documents-from-review-set.md) 到审阅集，并将其复制到其他 Azure 存储位置 (由 Microsoft 提供，或者由组织) 的管理。</span><span class="sxs-lookup"><span data-stu-id="3cf85-231">The first step is to [export](export-documents-from-review-set.md) data out of the review set and copy it to a different Azure Storage location (one provided by Microsoft or one managed by your organization).</span></span> <span data-ttu-id="3cf85-232">然后，使用 Azure 存储资源管理器将数据 [下载](download-export-jobs.md) 到本地计算机。</span><span class="sxs-lookup"><span data-stu-id="3cf85-232">Then you use Azure Storage Explorer to [download](download-export-jobs.md) the data to a local computer.</span></span> <span data-ttu-id="3cf85-233">除了导出的数据文件之外，导出包的包含还包含导出报告、摘要报告和错误报告。</span><span class="sxs-lookup"><span data-stu-id="3cf85-233">In addition to the exported data files, the contains of the export package also contains an export report, a summary report, and an error report.</span></span>
