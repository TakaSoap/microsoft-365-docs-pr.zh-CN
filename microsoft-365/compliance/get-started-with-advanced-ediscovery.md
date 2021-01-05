---
title: Microsoft 365 中的高级电子数据展示入门
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-aed
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: 本文介绍了如何在 Microsoft 365 中开始使用高级电子数据展示。 完成几个快速步骤后，即可使用高级电子数据展示工具。 第一步是创建一个案例，然后开始使用高级电子数据展示特性和功能。
ms.openlocfilehash: 45443620f294489c3afb4392376c9fe999fa098b
ms.sourcegitcommit: 98b889e674ad1d5fa37d4b6c5fc3eda60a1d67f3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/05/2021
ms.locfileid: "49751089"
---
# <a name="get-started-with-advanced-ediscovery"></a><span data-ttu-id="60794-105">高级电子数据展示入门</span><span class="sxs-lookup"><span data-stu-id="60794-105">Get started with Advanced eDiscovery</span></span>

<span data-ttu-id="60794-106">Microsoft 365 中的高级电子数据展示提供了[](overview-ediscovery-20.md#advanced-ediscovery-architecture)端到端工作流，用于保留、收集、审阅、分析和导出对组织内部和外部调查做出响应的数据。</span><span class="sxs-lookup"><span data-stu-id="60794-106">Advanced eDiscovery in Microsoft 365 provides an [end-to-end workflow](overview-ediscovery-20.md#advanced-ediscovery-architecture) to preserve, collect, review, analyze, and export data that's responsive to your organization's internal and external investigations.</span></span> <span data-ttu-id="60794-107">部署高级电子数据展示不需要任何内容，但 IT 管理员和电子数据展示管理员必须完成一些先决条件任务，然后组织才能开始创建和使用高级电子数据展示事例来管理调查。</span><span class="sxs-lookup"><span data-stu-id="60794-107">Nothing is needed to deploy Advanced eDiscovery, but there are some prerequisite tasks that an IT admin and eDiscovery manager have to complete before your organization can start to create and use Advanced eDiscovery cases to manage your investigations.</span></span>

<span data-ttu-id="60794-108">本文讨论设置高级电子数据展示所需的步骤。</span><span class="sxs-lookup"><span data-stu-id="60794-108">This article discusses the steps necessary to set up Advanced eDiscovery.</span></span> <span data-ttu-id="60794-109">这包括确保访问高级电子数据展示和将保管人添加到事例所需的适当许可，以及向法律和调查团队分配权限，以便他们可以访问和管理事例。</span><span class="sxs-lookup"><span data-stu-id="60794-109">This includes ensuring the proper licensing required to access Advanced eDiscovery and add custodians to cases, as well as assigning permissions to your legal and investigation team so they can access and manage cases.</span></span> <span data-ttu-id="60794-110">本文还提供了有关使用事例管理高级电子数据展示工作流进行法律调查的高级概述。</span><span class="sxs-lookup"><span data-stu-id="60794-110">This article also provides a high-level overview of using cases to manage the Advanced eDiscovery workflow for a legal investigation.</span></span>

## <a name="step-1-verify-and-assign-appropriate-licenses"></a><span data-ttu-id="60794-111">步骤 1：验证并分配适当的许可证</span><span class="sxs-lookup"><span data-stu-id="60794-111">Step 1: Verify and assign appropriate licenses</span></span>

<span data-ttu-id="60794-112">高级电子数据展示的许可需要相应的组织订阅和每用户许可。</span><span class="sxs-lookup"><span data-stu-id="60794-112">Licensing for Advanced eDiscovery requires the appropriate organization subscription and per-user licensing.</span></span>

- <span data-ttu-id="60794-113">**组织订阅：** 若要在 Microsoft 365 合规中心或安全与合规中心&高级电子数据展示，你的组织必须具有以下功能之一：</span><span class="sxs-lookup"><span data-stu-id="60794-113">**Organization subscription:** To access Advanced eDiscovery in the Microsoft 365 compliance center or the Security & Compliance Center, your organization must have one of the following:</span></span>

  - <span data-ttu-id="60794-114">Microsoft 365 E5 或 Office 365 E5 订阅</span><span class="sxs-lookup"><span data-stu-id="60794-114">Microsoft 365 E5 or Office 365 E5 subscription</span></span>
  
  - <span data-ttu-id="60794-115">具有 E5 合规性附加设备的 Microsoft 365 E3 订阅</span><span class="sxs-lookup"><span data-stu-id="60794-115">Microsoft 365 E3 subscription with E5 Compliance add-on</span></span>

  - <span data-ttu-id="60794-116">具有 E5 电子数据展示和审核加载项的 Microsoft 365 E3 订阅</span><span class="sxs-lookup"><span data-stu-id="60794-116">Microsoft 365 E3 subscription with E5 eDiscovery and Audit add-on</span></span>

  <span data-ttu-id="60794-117">如果你没有现有的 Microsoft 365 E5 计划，并且想要试用高级电子数据展示，可以将[Microsoft 365](https://docs.microsoft.com/office365/admin/try-or-buy-microsoft-365)添加到现有订阅或注册 Microsoft [](https://www.microsoft.com/microsoft-365/enterprise) 365 E5 试用版。</span><span class="sxs-lookup"><span data-stu-id="60794-117">If you don't have an existing Microsoft 365 E5 plan and want to try Advanced eDiscovery, you can [add Microsoft 365](https://docs.microsoft.com/office365/admin/try-or-buy-microsoft-365) to your existing subscription or [sign up for a trial](https://www.microsoft.com/microsoft-365/enterprise) of Microsoft 365 E5.</span></span>

- <span data-ttu-id="60794-118">**每用户许可：** 若要在高级电子数据展示案例中将用户添加为保管人，必须为该用户分配以下许可证之一，具体取决于你的组织订阅：</span><span class="sxs-lookup"><span data-stu-id="60794-118">**Per-user licensing:** To add a user as a custodian in an Advance eDiscovery case, that user must be assigned one of the following licenses, depending on your organization subscription:</span></span>

  - <span data-ttu-id="60794-119">Microsoft 365：必须为用户分配 Microsoft 365 E5 许可证、E5 合规性加载项许可证或 E5 电子数据展示和审核加载项许可证。</span><span class="sxs-lookup"><span data-stu-id="60794-119">Microsoft 365: Users must be assigned a Microsoft 365 E5 license, an E5 Compliance add-on license, or an E5 eDiscovery and Audit add-on license.</span></span>

  - <span data-ttu-id="60794-120">Office 365：必须为用户分配 Office 365 E5 许可证。</span><span class="sxs-lookup"><span data-stu-id="60794-120">Office 365: Users must be assigned an Office 365 E5 license.</span></span>

   <span data-ttu-id="60794-121">若要了解如何分配许可证，请参阅"[向用户分配许可证"。](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)</span><span class="sxs-lookup"><span data-stu-id="60794-121">For information about how to assign licenses, see [Assign licenses to users](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users).</span></span>

> [!NOTE]
> <span data-ttu-id="60794-122">用户只需要 E5 许可证 (或相应的附加许可证) 才能作为保管人添加到高级电子数据展示案例。</span><span class="sxs-lookup"><span data-stu-id="60794-122">Users only need an E5 license (or the appropriate add-on license) to be added as custodians to an Advanced eDiscovery case.</span></span> <span data-ttu-id="60794-123">使用高级电子数据展示管理事例和审阅事例数据的 IT 管理员、电子数据展示管理员、律师、律师律师或律师无需 E5 或附加许可证。</span><span class="sxs-lookup"><span data-stu-id="60794-123">IT admins, eDiscovery managers, lawyers, paralegals, or investigators who use Advanced eDiscovery to manage cases and review case data don't need an E5 or add-on license.</span></span>

## <a name="step-2-assign-ediscovery-permissions"></a><span data-ttu-id="60794-124">步骤 2：分配电子数据展示权限</span><span class="sxs-lookup"><span data-stu-id="60794-124">Step 2: Assign eDiscovery permissions</span></span>

<span data-ttu-id="60794-125">若要访问高级电子数据展示或添加为高级电子数据展示案例的成员，必须为用户分配适当的权限。</span><span class="sxs-lookup"><span data-stu-id="60794-125">To access Advanced eDiscovery or added as a member of an Advanced eDiscovery case, a user must be assigned the appropriate permissions.</span></span> <span data-ttu-id="60794-126">具体而言，必须将用户添加为安全与合规中心内电子数据展示&组的成员。</span><span class="sxs-lookup"><span data-stu-id="60794-126">Specifically, a user must be added as a member of the eDiscovery Manager role group in the Security & Compliance Center.</span></span> <span data-ttu-id="60794-127">此角色组的成员可以创建和管理高级电子数据展示事例。</span><span class="sxs-lookup"><span data-stu-id="60794-127">Members of this role group can create and manage Advanced eDiscovery cases.</span></span> <span data-ttu-id="60794-128">他们可以添加和删除成员、将保管人和内容位置保留、管理法定保留通知、创建和编辑与案例关联的搜索、将搜索结果添加到审阅集、分析审阅集内的数据以及从高级电子数据展示案例导出和下载。</span><span class="sxs-lookup"><span data-stu-id="60794-128">They can add and remove members, place custodians and content locations on hold, manage legal hold notifications, create and edit searches associated in a case, add search results to a review set, analyze data in a review set, and export and download from an Advanced eDiscovery case.</span></span>

<span data-ttu-id="60794-129">完成以下步骤以将用户添加到电子数据展示管理员角色组：</span><span class="sxs-lookup"><span data-stu-id="60794-129">Complete the following steps to add users to the eDiscovery Manager role group:</span></span>

1. <span data-ttu-id="60794-130">转到 Microsoft 365 组织中管理员帐户的凭据 [https://protection.office.com/permissions](https://protection.office.com/permissions) 并登录。</span><span class="sxs-lookup"><span data-stu-id="60794-130">Go to [https://protection.office.com/permissions](https://protection.office.com/permissions) and sign in using the credentials for an admin account in your Microsoft 365 organization.</span></span>

2. <span data-ttu-id="60794-131">在 **"权限"** 页上，选择 **电子数据展示管理员角色** 组。</span><span class="sxs-lookup"><span data-stu-id="60794-131">On the **Permissions** page, select the **eDiscovery Manager** role group.</span></span>

3. <span data-ttu-id="60794-132">在电子数据展示管理器飞出页上 **，单击电子** 数据展示管理器 **部分旁边的"编辑** "。</span><span class="sxs-lookup"><span data-stu-id="60794-132">On the eDiscovery Manager flyout page, click **Edit** next to the **eDiscovery Manager** section.</span></span>

4. <span data-ttu-id="60794-133">在编辑角色组向导中的"选择 **电子数据** 展示管理器"页上，单击"**选择电子数据展示管理器"。**</span><span class="sxs-lookup"><span data-stu-id="60794-133">On the **Choose eDiscovery Manager** page in the edit role group wizard, click **Choose eDiscovery Manager**.</span></span>

5. <span data-ttu-id="60794-134">单击 **"** 添加"，然后选中要添加到角色组的所有用户的复选框。</span><span class="sxs-lookup"><span data-stu-id="60794-134">Click **Add** then select the checkbox for all users you want to add to the role group.</span></span>

6. <span data-ttu-id="60794-135">单击 **"** 添加"添加所选用户，然后单击"**完成"。**</span><span class="sxs-lookup"><span data-stu-id="60794-135">Click **Add** to add the selected users, and then click **Done**.</span></span>

7. <span data-ttu-id="60794-136">单击 **"** 保存"将用户添加到角色组，然后单击" **关闭"以** 完成此步骤。</span><span class="sxs-lookup"><span data-stu-id="60794-136">Click **Save** to add the users to the role group, and then click **Close** to complete the step.</span></span>

### <a name="more-information-about-the-ediscovery-manager-role-group"></a><span data-ttu-id="60794-137">有关电子数据展示管理员角色组详细信息</span><span class="sxs-lookup"><span data-stu-id="60794-137">More information about the eDiscovery Manager role group</span></span>

<span data-ttu-id="60794-138">电子数据展示管理员角色组中有两个子组。</span><span class="sxs-lookup"><span data-stu-id="60794-138">There are two subgroups in the eDiscovery Manager role group.</span></span> <span data-ttu-id="60794-139">这些子组之间的差异基于作用域。</span><span class="sxs-lookup"><span data-stu-id="60794-139">The difference between these subgroups is based on scope.</span></span>

- <span data-ttu-id="60794-140">**电子数据展示管理器：** 可查看和管理他们创建或作为成员的高级电子数据展示事例。</span><span class="sxs-lookup"><span data-stu-id="60794-140">**eDiscovery Manager:** Can view and manage the Advanced eDiscovery cases they create or are a member of.</span></span> <span data-ttu-id="60794-141">如果另一个电子数据展示管理器创建了一个案例，但没有将第二个电子数据展示管理员添加为该案例的成员，则第二个电子数据展示管理器将无法在合规中心的"高级电子数据展示"页上查看或打开该案例。</span><span class="sxs-lookup"><span data-stu-id="60794-141">If another eDiscovery Manager creates a case but doesn't add a second eDiscovery Manager as a member of that case, the second eDiscovery Manager won't be able to view or open the case on the Advanced eDiscovery page in the compliance center.</span></span> <span data-ttu-id="60794-142">通常，可以将组织中大多数人员添加到电子数据展示管理器子组。</span><span class="sxs-lookup"><span data-stu-id="60794-142">In general, most people in your organization can be added to the eDiscovery Manager subgroup.</span></span>

- <span data-ttu-id="60794-143">**电子数据展示管理员：** 可以执行电子数据展示管理员可以执行的所有案例管理任务。</span><span class="sxs-lookup"><span data-stu-id="60794-143">**eDiscovery Administrator:** Can perform all case management tasks that an eDiscovery Manager can do.</span></span> <span data-ttu-id="60794-144">此外，电子数据展示管理员可以：</span><span class="sxs-lookup"><span data-stu-id="60794-144">Additionally, an eDiscovery Administrator can:</span></span>

  - <span data-ttu-id="60794-145">查看"高级电子数据展示"页上列出的所有事例。</span><span class="sxs-lookup"><span data-stu-id="60794-145">View all cases that are listed on the Advanced eDiscovery page.</span></span>
  
  - <span data-ttu-id="60794-146">在将自己添加为案件组的成员后，管理组织的任何案例。</span><span class="sxs-lookup"><span data-stu-id="60794-146">Manage any case in the organization after they add themselves as a member of the case.</span></span>

  - <span data-ttu-id="60794-147">访问和导出组织中任何案例的大小写数据。</span><span class="sxs-lookup"><span data-stu-id="60794-147">Access and export case data for any case in the organization.</span></span>

  <span data-ttu-id="60794-148">由于访问权限广泛，组织应只有少数几个作为电子数据展示管理员子组成员的管理员。</span><span class="sxs-lookup"><span data-stu-id="60794-148">Because of the broad scope of access, an organization should have only a few admins who are members of the eDiscovery Administrators subgroup.</span></span>

<span data-ttu-id="60794-149">有关电子数据展示权限以及分配给电子数据展示管理员角色组的每个角色的说明，请参阅"分配[电子数据展示权限"。](assign-ediscovery-permissions.md)</span><span class="sxs-lookup"><span data-stu-id="60794-149">For more information about eDiscovery permissions and a description of each role that's assigned to the eDiscovery Manager role group, see [Assign eDiscovery permissions](assign-ediscovery-permissions.md).</span></span>

## <a name="step-3-configure-global-settings-for-advanced-ediscovery"></a><span data-ttu-id="60794-150">步骤 3：配置高级电子数据展示的全局设置</span><span class="sxs-lookup"><span data-stu-id="60794-150">Step 3: Configure global settings for Advanced eDiscovery</span></span>

<span data-ttu-id="60794-151">在组织中人员开始创建和使用案例之前，要完成的最后一步是配置适用于组织中所有案例的全局设置。</span><span class="sxs-lookup"><span data-stu-id="60794-151">The last step to complete before people in your organization start to create and use cases is to configure global settings that apply to all cases in your organization.</span></span> <span data-ttu-id="60794-152">目前，唯一的全局设置是 *律师-客户特权* 检测 (将来将有更多的全局设置) 。</span><span class="sxs-lookup"><span data-stu-id="60794-152">At this time, the only global setting is *attorney-client privilege detection* (more global settings will be available in the future).</span></span> <span data-ttu-id="60794-153">此设置使你能够在分析审阅集内的数据时运行律师-客户特权模型。</span><span class="sxs-lookup"><span data-stu-id="60794-153">This setting enables the attorney-client privilege model to run when you analyze data in a review set.</span></span> <span data-ttu-id="60794-154">模型使用机器学习来确定文档包含本质上合法内容的可能性。</span><span class="sxs-lookup"><span data-stu-id="60794-154">The model uses machine learning to determine the likelihood that a document contains content that is legal in nature.</span></span> <span data-ttu-id="60794-155">它还将文档参与者与你在设置模型 (时提交的律师列表) 以确定文档是否至少有一个参与者是律师。</span><span class="sxs-lookup"><span data-stu-id="60794-155">It also compares the participants of documents with an attorney list (that you submit when setting up the model) to determine if a document has at least one participant who is an attorney.</span></span>

<span data-ttu-id="60794-156">有关设置和使用律师-客户特权检测模型的信息，请参阅高级电子数据展示中的"设置律师[-客户特权检测"。](attorney-privilege-detection.md)</span><span class="sxs-lookup"><span data-stu-id="60794-156">For more information about setting up and using the attorney-client privilege detection model, see [Set up attorney-client privilege detection in Advanced eDiscovery](attorney-privilege-detection.md).</span></span>

> [!NOTE]
> <span data-ttu-id="60794-157">这是一个可选步骤，可以随时执行。</span><span class="sxs-lookup"><span data-stu-id="60794-157">This is an optional step that you can perform anytime.</span></span> <span data-ttu-id="60794-158">不实现律师-客户特权检测模型不会阻止你创建和使用高级电子数据展示事例。</span><span class="sxs-lookup"><span data-stu-id="60794-158">Not implementing the attorney-client privilege detection model doesn't prevent you from creating and using Advanced eDiscovery cases.</span></span>

## <a name="step-4-create-an-advanced-ediscovery-case"></a><span data-ttu-id="60794-159">步骤 4：创建高级电子数据展示案例</span><span class="sxs-lookup"><span data-stu-id="60794-159">Step 4: Create an Advanced eDiscovery case</span></span>

<span data-ttu-id="60794-160">下一步是创建案例并开始使用高级电子数据展示。</span><span class="sxs-lookup"><span data-stu-id="60794-160">The next step is to create a case and start using Advanced eDiscovery.</span></span> <span data-ttu-id="60794-161">完成以下步骤以创建案例并添加成员。</span><span class="sxs-lookup"><span data-stu-id="60794-161">Complete the following steps to create a case and add members.</span></span> <span data-ttu-id="60794-162">创建案例的用户将自动添加为成员。</span><span class="sxs-lookup"><span data-stu-id="60794-162">The user who creates the case is automatically added as a member.</span></span>

1. <span data-ttu-id="60794-163">转到已分配有相应电子数据展示权限的用户帐户 [https://compliance.microsoft.com](https://compliance.microsoft.com) 并登录。</span><span class="sxs-lookup"><span data-stu-id="60794-163">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and sign in with a user account that has been assigned the appropriate eDiscovery permissions.</span></span> <span data-ttu-id="60794-164">组织管理角色组的成员还可以创建高级电子数据展示事例。</span><span class="sxs-lookup"><span data-stu-id="60794-164">Members of the Organization Management role group can also create Advanced eDiscovery cases.</span></span>

2. <span data-ttu-id="60794-165">在 Microsoft 365 合规中心的左侧导航窗格中，单击"全部显示"，然后单击"电子数据展示>**高级"**。</span><span class="sxs-lookup"><span data-stu-id="60794-165">In the left navigation pane of the Microsoft 365 compliance center, click **Show all**, and then click **eDiscovery > Advanced**.</span></span>

3. <span data-ttu-id="60794-166">在 **"高级电子数据展示"** 页上，单击"事例 **"选项卡，** 然后单击"**创建事例"。**</span><span class="sxs-lookup"><span data-stu-id="60794-166">On the **Advanced eDiscovery** page, click the **Cases** tab, and then click **Create a case**.</span></span>

4. <span data-ttu-id="60794-167">在 **"新建电子数据** 展示案例"飞出页上，为案例指定 (一) ，然后键入可选的案例编号和说明。</span><span class="sxs-lookup"><span data-stu-id="60794-167">On the **New eDiscovery case** flyout page, give the case a name (required), and then type an optional case number and description.</span></span> <span data-ttu-id="60794-168">在组织中，案例名称必须是唯一的。</span><span class="sxs-lookup"><span data-stu-id="60794-168">The case name must be unique in your organization.</span></span>

5. <span data-ttu-id="60794-169">单击 **"** 保存"创建案例。</span><span class="sxs-lookup"><span data-stu-id="60794-169">Click **Save** to create the case.</span></span>

   <span data-ttu-id="60794-170">将新建案例，并显示新案例的"设置"选项卡。</span><span class="sxs-lookup"><span data-stu-id="60794-170">The new case is created and the **Settings** tab in the new case is displayed.</span></span>

6. <span data-ttu-id="60794-171">在 **"&"** 选项卡上的"访问权限"磁贴中，**单击"** 选择"，然后单击"更新 **"。**</span><span class="sxs-lookup"><span data-stu-id="60794-171">In the **Access & permissions** tile on the **Settings** tab, click **Select**, and then click **Update**.</span></span>

7. <span data-ttu-id="60794-172">单击“更新”。</span><span class="sxs-lookup"><span data-stu-id="60794-172">Click **Update**.</span></span>

8. <span data-ttu-id="60794-173">在" **管理此案例"** 飞出页上的" **管理** 成员"下 **，单击"** 添加"以向案例添加成员。</span><span class="sxs-lookup"><span data-stu-id="60794-173">On the **Manage this case** flyout page, under **Manage members**, click **Add** to add members to the case.</span></span>

9. <span data-ttu-id="60794-174">在人员列表中，选中要添加到案例的用户名旁边的复选框。</span><span class="sxs-lookup"><span data-stu-id="60794-174">In the list of people, select the check box next to the names of the people that you want to add to the case.</span></span> <span data-ttu-id="60794-175">如前所述，请确保你添加到案例的人已分配有适当的电子数据展示权限。</span><span class="sxs-lookup"><span data-stu-id="60794-175">As previously explained, be sure that the people you add to the case have been assigned the appropriate eDiscovery permissions.</span></span>

10. <span data-ttu-id="60794-176">选择要添加为案例成员的人后，单击"**添加"。**</span><span class="sxs-lookup"><span data-stu-id="60794-176">After you've selected the people to add as members of the case, click **Add**.</span></span>

11. <span data-ttu-id="60794-177">在 **"管理此案例"** 飞出页中 **，单击"** 保存"以保存新案例成员列表。</span><span class="sxs-lookup"><span data-stu-id="60794-177">In the **Manage this case** flyout page, click **Save** to save the new list of case members.</span></span>

12. <span data-ttu-id="60794-178">单击 **"主页** "选项卡转到案例主页。</span><span class="sxs-lookup"><span data-stu-id="60794-178">Click the **Home** tab to go to the case home page.</span></span>

## <a name="explore-the-advanced-ediscovery-workflow"></a><span data-ttu-id="60794-179">探索高级电子数据展示工作流</span><span class="sxs-lookup"><span data-stu-id="60794-179">Explore the Advanced eDiscovery workflow</span></span>

<span data-ttu-id="60794-180">若要开始使用高级电子数据展示，下面是一个符合常见电子数据展示做法 [的简单工作流](overview-ediscovery-20.md#alignment-with-edrm)。</span><span class="sxs-lookup"><span data-stu-id="60794-180">To get you started using Advanced eDiscovery, here's a simple workflow that aligns with [common eDiscovery practices](overview-ediscovery-20.md#alignment-with-edrm).</span></span> <span data-ttu-id="60794-181">在每个步骤中，我们还将重点介绍您可以浏览的一些扩展的高级电子数据展示功能。</span><span class="sxs-lookup"><span data-stu-id="60794-181">In each of these steps, we'll also highlight some extended Advanced eDiscovery functionality that you can explore.</span></span>

![高级电子数据展示工作流](../media/AeDWorkflow.png)

1. <span data-ttu-id="60794-183">**[将保管人添加到案例](add-custodians-to-case.md)**。</span><span class="sxs-lookup"><span data-stu-id="60794-183">**[Add custodians to a case](add-custodians-to-case.md)**.</span></span> <span data-ttu-id="60794-184">创建案例后的第一步是添加保管人。</span><span class="sxs-lookup"><span data-stu-id="60794-184">The first step after creating a case is to add custodians.</span></span> <span data-ttu-id="60794-185">*保管人* 是拥有与案例相关的文档或电子文件的管理控制的人。</span><span class="sxs-lookup"><span data-stu-id="60794-185">A *custodian* is a person having administrative control of a document or electronic file that may be relevant to the case.</span></span> <span data-ttu-id="60794-186">以下是在向案例 (保管人时) 可以执行某些操作：</span><span class="sxs-lookup"><span data-stu-id="60794-186">Here are some things that happen (or that you can do) when you add custodians to a case:</span></span>

   - <span data-ttu-id="60794-187">保管人 Exchange 邮箱、OneDrive 帐户以及保管人是其中成员的任何 Microsoft Teams 或 Yammer 组的数据都可以"标记为"诉讼数据"。</span><span class="sxs-lookup"><span data-stu-id="60794-187">Data in the custodian's Exchange mailbox, OneDrive account, and any Microsoft Teams or Yammer groups that the custodian is a member of can be "marked" as custodial data in the case.</span></span>
  
   - <span data-ttu-id="60794-188">保管人数据通过称为高级 (过程 *重新编制* 索引) 。</span><span class="sxs-lookup"><span data-stu-id="60794-188">Custodian data is reindexed (by a process called *Advanced indexing*).</span></span> <span data-ttu-id="60794-189">这有助于在下一步中优化搜索。</span><span class="sxs-lookup"><span data-stu-id="60794-189">This helps optimize searching for it in the next step.</span></span>
  
   - <span data-ttu-id="60794-190">你可以对保管人数据进行保留。</span><span class="sxs-lookup"><span data-stu-id="60794-190">You can place a hold on custodian data.</span></span> <span data-ttu-id="60794-191">这将保留调查期间可能与案件相关的数据。</span><span class="sxs-lookup"><span data-stu-id="60794-191">This preserves data that may be relevant to the case during the investigation.</span></span>
  
   - <span data-ttu-id="60794-192">可以将其他数据源与保管人 (关联，例如，可以将 SharePoint 站点或 Microsoft 365 组与保管人) 关联，以便可以重新索引、将其置于保留和搜索状态，就像保管人邮箱或 OneDrive 帐户中的数据一样。</span><span class="sxs-lookup"><span data-stu-id="60794-192">You can associate other data sources with a custodian (for example, you can associate a SharePoint site or Microsoft 365 Group with a custodian) so this data can be reindexed, placed on hold, and searched, just like the data in the custodian's mailbox or OneDrive account.</span></span>

   - <span data-ttu-id="60794-193">您可以使用高级电子 [数据](managing-custodian-communications.md) 展示中的通信工作流向保管人发送法定保留通知。</span><span class="sxs-lookup"><span data-stu-id="60794-193">You can use the [communications workflow](managing-custodian-communications.md) in Advanced eDiscovery to send a legal hold notification to custodians.</span></span>

2. <span data-ttu-id="60794-194">**[搜索与案例相关的数据的来源](collecting-data-for-ediscovery.md)**。</span><span class="sxs-lookup"><span data-stu-id="60794-194">**[Search custodial data sources for data relevant to the case](collecting-data-for-ediscovery.md)**.</span></span> <span data-ttu-id="60794-195">将保管人添加到案例后，使用内置搜索工具在保管人数据位置搜索可能与案例相关的数据。</span><span class="sxs-lookup"><span data-stu-id="60794-195">After you add custodians to a case, use the built-in search tool to search the custodian data locations for data that may be relevant to the case.</span></span> <span data-ttu-id="60794-196">您可以使用关键字、属性和条件来构建搜索查询[](building-search-queries.md)，以使用与案例最相关的数据返回搜索结果。</span><span class="sxs-lookup"><span data-stu-id="60794-196">You use keywords, properties, and conditions to [build search queries](building-search-queries.md) that return search results with the data that's most likely relevant to the case.</span></span> <span data-ttu-id="60794-197">还可以执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="60794-197">You can also:</span></span>

   - <span data-ttu-id="60794-198">查看 [可帮助您](search-statistics-in-advanced-ediscovery.md) 优化搜索查询以缩小结果范围的搜索统计信息。</span><span class="sxs-lookup"><span data-stu-id="60794-198">View [search statistics](search-statistics-in-advanced-ediscovery.md) that may help you refine a search query to narrow the results.</span></span>

   - <span data-ttu-id="60794-199">预览搜索结果以快速验证是否已找到相关数据。</span><span class="sxs-lookup"><span data-stu-id="60794-199">Preview the search results to quickly verify whether the relevant data is being found.</span></span>

   - <span data-ttu-id="60794-200">修改查询并重新运行搜索。</span><span class="sxs-lookup"><span data-stu-id="60794-200">Revise a query and rerun the search.</span></span>

3. <span data-ttu-id="60794-201">**[将数据添加到审阅集](add-data-to-review-set.md)**。</span><span class="sxs-lookup"><span data-stu-id="60794-201">**[Add data to a review set](add-data-to-review-set.md)**.</span></span> <span data-ttu-id="60794-202">配置并验证搜索返回所需数据后，下一步是将搜索结果添加到审阅集。</span><span class="sxs-lookup"><span data-stu-id="60794-202">Once you've configured and verified that a search returns the desired data, the next step is to add the search results to a review set.</span></span> <span data-ttu-id="60794-203">向审阅集添加数据时，项目会从原始位置复制到安全的 Azure 存储位置。</span><span class="sxs-lookup"><span data-stu-id="60794-203">When you add data to a review set, items are copied from their original location to a secure Azure Storage location.</span></span> <span data-ttu-id="60794-204">重新对数据进行索引索引，以在审阅和分析审阅集内的项目时优化数据，以便进行全面而快速搜索。</span><span class="sxs-lookup"><span data-stu-id="60794-204">The data is reindexed again to optimize it for thorough and fast searches when reviewing and analyzing items in the review set.</span></span> <span data-ttu-id="60794-205">此外，您还可以 [将非 Office 365 数据添加到审阅集](load-non-office-365-data-into-a-review-set.md)。</span><span class="sxs-lookup"><span data-stu-id="60794-205">Additionally, you can also [add non-Office 365 data into a review set](load-non-office-365-data-into-a-review-set.md).</span></span>

   <span data-ttu-id="60794-206">还有一种特殊类型的审阅集，你可以向其中添加数据，称为 *对话审阅集*。</span><span class="sxs-lookup"><span data-stu-id="60794-206">There's also a special kind of review set that you can add data to, called a *conversation review set*.</span></span> <span data-ttu-id="60794-207">这些类型的审阅集提供对话重建功能，以重建、审阅和导出线程对话，如 Microsoft Teams 中的会话。</span><span class="sxs-lookup"><span data-stu-id="60794-207">These types of review sets provide conversation reconstruction capabilities to reconstruct, review, and export threaded conversations like those in Microsoft Teams.</span></span> <span data-ttu-id="60794-208">有关详细信息，请参阅高级电子数据[展示中的"审阅对话"。](conversation-review-sets.md)</span><span class="sxs-lookup"><span data-stu-id="60794-208">For more information, see [Review conversations in Advanced eDiscovery](conversation-review-sets.md).</span></span>

4. <span data-ttu-id="60794-209">**审阅和分析审阅集内的数据**。</span><span class="sxs-lookup"><span data-stu-id="60794-209">**Review and analyze data in a review set**.</span></span> <span data-ttu-id="60794-210">现在数据已位于审阅集内，您可以使用各种工具和功能来查看和分析案例数据，目的是将数据集减少为与正在调查的案例中最相关的数据。</span><span class="sxs-lookup"><span data-stu-id="60794-210">Now that data is in a review set, you can use a wide-variety of tools and capabilities to view and analyze the case data with the goal of reducing the data set to what is most relevant to the case you're investigating.</span></span> <span data-ttu-id="60794-211">以下是您可以在此过程期间使用的一些工具和功能的列表。</span><span class="sxs-lookup"><span data-stu-id="60794-211">Here's a list of some tools and capabilities that you can use during this process.</span></span>

   - <span data-ttu-id="60794-212">[查看文档](view-documents-in-review-set.md)。</span><span class="sxs-lookup"><span data-stu-id="60794-212">[View documents](view-documents-in-review-set.md).</span></span> <span data-ttu-id="60794-213">这包括查看审阅集内每个文档的元数据，以及查看文档本机版本或文本版本。</span><span class="sxs-lookup"><span data-stu-id="60794-213">This includes viewing the metadata for each document in a review set, and viewing the document in its native version or text version.</span></span>

   - <span data-ttu-id="60794-214">[创建查询和筛选器](review-set-search.md)。</span><span class="sxs-lookup"><span data-stu-id="60794-214">[Create queries and filters](review-set-search.md).</span></span> <span data-ttu-id="60794-215">您可以使用各种搜索条件创建搜索查询 (包括搜索所有文件元数据属性 [) ](document-metadata-fields-in-advanced-ediscovery.md) 以进一步优化和剔除与案例最相关的案例数据。</span><span class="sxs-lookup"><span data-stu-id="60794-215">You create search queries using a variety of search criteria (including the ability to search all [file metadata properties](document-metadata-fields-in-advanced-ediscovery.md)) to further refine and cull the case data to what is most relevant to the case.</span></span> <span data-ttu-id="60794-216">您还可以使用审阅集筛选器快速将其他条件应用于搜索查询的结果，以进一步优化这些结果。</span><span class="sxs-lookup"><span data-stu-id="60794-216">You can also use review set filters to quickly apply additional conditions to the results of a search query to further refine those results.</span></span>

   - <span data-ttu-id="60794-217">[创建和使用标记](tagging-documents.md)。</span><span class="sxs-lookup"><span data-stu-id="60794-217">[Create and use tags](tagging-documents.md).</span></span> <span data-ttu-id="60794-218">您可以将标记应用于审阅集内的文档，以确定哪些文档是响应式 (还是对案例) 无响应，然后在创建搜索查询时使用这些标记来包含或排除标记的文档。</span><span class="sxs-lookup"><span data-stu-id="60794-218">You can apply tags to documents in a review set to identify which are responsive (or non-responsive to the case) and then use those tags when creating search queries to include or exclude the tagged documents.</span></span> <span data-ttu-id="60794-219">您还可以标记以确定要导出的文档。</span><span class="sxs-lookup"><span data-stu-id="60794-219">You can also tagging to determine which documents to export.</span></span>

   - <span data-ttu-id="60794-220">[批注和修订文档](view-documents-in-review-set.md#annotate-view)。</span><span class="sxs-lookup"><span data-stu-id="60794-220">[Annotate and redact documents](view-documents-in-review-set.md#annotate-view).</span></span> <span data-ttu-id="60794-221">可以在审阅中使用批注工具为文档添加批注，将文档中的内容修订为工作产品。</span><span class="sxs-lookup"><span data-stu-id="60794-221">You can use the annotation tool in a review to annotate documents and redact content in documents as work product.</span></span> <span data-ttu-id="60794-222">我们在审阅期间生成批注或修订文档的 PDF 版本，以减少导出未修订的本机版本文档的风险。</span><span class="sxs-lookup"><span data-stu-id="60794-222">We generate a PDF version of an annotated or redacted document during the review to reduce the risk of exporting the un-redacted native version of the document.</span></span>

   - <span data-ttu-id="60794-223">[分析案例数据](analyzing-data-in-review-set.md)。</span><span class="sxs-lookup"><span data-stu-id="60794-223">[Analyze case data](analyzing-data-in-review-set.md).</span></span> <span data-ttu-id="60794-224">高级电子数据展示中的分析功能很强大。</span><span class="sxs-lookup"><span data-stu-id="60794-224">The analytics functionality in Advanced eDiscovery is powerful.</span></span> <span data-ttu-id="60794-225">高级电子数据展示提供了许多工具来分析文档，以进一步减少审阅集内要审阅的文档数量。</span><span class="sxs-lookup"><span data-stu-id="60794-225">Advanced eDiscovery provides a number of tools to analyze the documents to further reduce the volume of documents to be reviewed in a review set.</span></span> <span data-ttu-id="60794-226">我们还生成分析报告，汇总了运行分析的结果。</span><span class="sxs-lookup"><span data-stu-id="60794-226">We also generate analytics reports that summarize the result of running analytics.</span></span> <span data-ttu-id="60794-227">如前所述，运行分析还会运行 [律师-客户特权检测模型](attorney-privilege-detection.md#use-the-attorney-client-privilege-detection-model)。</span><span class="sxs-lookup"><span data-stu-id="60794-227">As previously explained, running analytics also runs [the attorney-client privilege detection model](attorney-privilege-detection.md#use-the-attorney-client-privilege-detection-model).</span></span>

5. <span data-ttu-id="60794-228">**导出和下载案例数据**。</span><span class="sxs-lookup"><span data-stu-id="60794-228">**Export and download case data**.</span></span> <span data-ttu-id="60794-229">收集、审阅和分析案例数据后的最后一步是从高级电子数据展示中导出数据，以用于外部审阅或供调查团队外部人员查看。</span><span class="sxs-lookup"><span data-stu-id="60794-229">A final step after collecting, reviewing, and analyzing case data is to export it out of Advanced eDiscovery for external review or for review by people outside of the investigation team.</span></span> <span data-ttu-id="60794-230">导出数据的过程分两步完成。</span><span class="sxs-lookup"><span data-stu-id="60794-230">Exporting data is a two-step process.</span></span> <span data-ttu-id="60794-231">第一步是将数据从[](export-documents-from-review-set.md)审阅集中导出，并复制到其他 Azure 存储位置 (Microsoft 提供一个 Azure 存储位置，或由组织托管的 Azure 存储) 。</span><span class="sxs-lookup"><span data-stu-id="60794-231">The first step is to [export](export-documents-from-review-set.md) data out of the review set and copy it to a different Azure Storage location (one provided by Microsoft or one managed by your organization).</span></span> <span data-ttu-id="60794-232">然后，使用 Azure 存储资源管理器 [将数据](download-export-jobs.md) 下载到本地计算机。</span><span class="sxs-lookup"><span data-stu-id="60794-232">Then you use Azure Storage Explorer to [download](download-export-jobs.md) the data to a local computer.</span></span> <span data-ttu-id="60794-233">除了导出的数据文件之外，导出包的包含内容还包含导出报告、摘要报表和错误报告。</span><span class="sxs-lookup"><span data-stu-id="60794-233">In addition to the exported data files, the contains of the export package also contains an export report, a summary report, and an error report.</span></span>
