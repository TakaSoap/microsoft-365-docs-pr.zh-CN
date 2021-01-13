---
title: 在 Microsoft 365 中设置高级电子数据展示
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
description: 本文介绍如何设置高级电子数据展示，以便你可以开始创建和管理事例。 它还介绍了所需的 Microsoft 订阅和许可。 完成几个快速步骤后，即可使用高级电子数据展示工具。
ms.openlocfilehash: aef5cd2e465306b4401cda66d4ba30c97b9fc8cd
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/13/2021
ms.locfileid: "49841173"
---
# <a name="set-up-microsoft-365-advanced-ediscovery"></a><span data-ttu-id="6380c-105">设置 Microsoft 365 高级电子数据展示</span><span class="sxs-lookup"><span data-stu-id="6380c-105">Set up Microsoft 365 Advanced eDiscovery</span></span>

<span data-ttu-id="6380c-106">Microsoft 365 中的高级电子数据展示提供了[](overview-ediscovery-20.md#advanced-ediscovery-workflow)端到端工作流，用于保留、收集、审阅、分析和导出对组织内部和外部调查做出响应的数据。</span><span class="sxs-lookup"><span data-stu-id="6380c-106">Advanced eDiscovery in Microsoft 365 provides an [end-to-end workflow](overview-ediscovery-20.md#advanced-ediscovery-workflow) to preserve, collect, review, analyze, and export data that's responsive to your organization's internal and external investigations.</span></span> <span data-ttu-id="6380c-107">部署高级电子数据展示不需要任何内容，但 IT 管理员和电子数据展示管理员必须完成一些先决条件任务，然后组织才能开始创建和使用高级电子数据展示事例来管理调查。</span><span class="sxs-lookup"><span data-stu-id="6380c-107">Nothing is needed to deploy Advanced eDiscovery, but there are some prerequisite tasks that an IT admin and eDiscovery manager have to complete before your organization can start to create and use Advanced eDiscovery cases to manage your investigations.</span></span>

<span data-ttu-id="6380c-108">本文讨论设置高级电子数据展示所需的步骤。</span><span class="sxs-lookup"><span data-stu-id="6380c-108">This article discusses the steps necessary to set up Advanced eDiscovery.</span></span> <span data-ttu-id="6380c-109">这包括确保访问高级电子数据展示和将保管人添加到事例所需的适当许可，以及向法律和调查团队分配权限，以便他们可以访问和管理事例。</span><span class="sxs-lookup"><span data-stu-id="6380c-109">This includes ensuring the proper licensing required to access Advanced eDiscovery and add custodians to cases, and assigning permissions to your legal and investigation team so they can access and manage cases.</span></span>

## <a name="step-1-verify-and-assign-appropriate-licenses"></a><span data-ttu-id="6380c-110">步骤 1：验证并分配适当的许可证</span><span class="sxs-lookup"><span data-stu-id="6380c-110">Step 1: Verify and assign appropriate licenses</span></span>

<span data-ttu-id="6380c-111">高级电子数据展示的许可需要相应的组织订阅和每用户许可。</span><span class="sxs-lookup"><span data-stu-id="6380c-111">Licensing for Advanced eDiscovery requires the appropriate organization subscription and per-user licensing.</span></span>

- <span data-ttu-id="6380c-112">**组织订阅：** 若要访问 Microsoft 365 合规中心或安全与合规中心&高级电子数据展示，你的组织必须具有以下其中一项：</span><span class="sxs-lookup"><span data-stu-id="6380c-112">**Organization subscription:** To access Advanced eDiscovery in the Microsoft 365 compliance center or the Security & Compliance Center, your organization must have one of the following:</span></span>

  - <span data-ttu-id="6380c-113">Microsoft 365 E5 或 Office 365 E5 订阅</span><span class="sxs-lookup"><span data-stu-id="6380c-113">Microsoft 365 E5 or Office 365 E5 subscription</span></span>
  
  - <span data-ttu-id="6380c-114">具有 E5 合规性附加设备的 Microsoft 365 E3 订阅</span><span class="sxs-lookup"><span data-stu-id="6380c-114">Microsoft 365 E3 subscription with E5 Compliance add-on</span></span>

  - <span data-ttu-id="6380c-115">带 E5 电子数据展示和审核加载项的 Microsoft 365 E3 订阅</span><span class="sxs-lookup"><span data-stu-id="6380c-115">Microsoft 365 E3 subscription with E5 eDiscovery and Audit add-on</span></span>

  <span data-ttu-id="6380c-116">如果你没有现有的 Microsoft 365 E5 计划，并且想要试用高级电子数据展示，可以将[Microsoft 365](https://docs.microsoft.com/office365/admin/try-or-buy-microsoft-365)添加到现有订阅或注册 Microsoft [](https://www.microsoft.com/microsoft-365/enterprise) 365 E5 试用版。</span><span class="sxs-lookup"><span data-stu-id="6380c-116">If you don't have an existing Microsoft 365 E5 plan and want to try Advanced eDiscovery, you can [add Microsoft 365](https://docs.microsoft.com/office365/admin/try-or-buy-microsoft-365) to your existing subscription or [sign up for a trial](https://www.microsoft.com/microsoft-365/enterprise) of Microsoft 365 E5.</span></span>

- <span data-ttu-id="6380c-117">**每用户许可：** 若要在高级电子数据展示案例中将用户添加为保管人，必须为该用户分配以下许可证之一，具体取决于你的组织订阅：</span><span class="sxs-lookup"><span data-stu-id="6380c-117">**Per-user licensing:** To add a user as a custodian in an Advance eDiscovery case, that user must be assigned one of the following licenses, depending on your organization subscription:</span></span>

  - <span data-ttu-id="6380c-118">Microsoft 365：必须为用户分配 Microsoft 365 E5 许可证、E5 合规性附加许可证或 E5 电子数据展示和审核加载项许可证。</span><span class="sxs-lookup"><span data-stu-id="6380c-118">Microsoft 365: Users must be assigned a Microsoft 365 E5 license, an E5 Compliance add-on license, or an E5 eDiscovery and Audit add-on license.</span></span>

  - <span data-ttu-id="6380c-119">Office 365：必须为用户分配 Office 365 E5 许可证。</span><span class="sxs-lookup"><span data-stu-id="6380c-119">Office 365: Users must be assigned an Office 365 E5 license.</span></span>

   <span data-ttu-id="6380c-120">若要了解如何分配许可证，请参阅"[向用户分配许可证"。](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)</span><span class="sxs-lookup"><span data-stu-id="6380c-120">For information about how to assign licenses, see [Assign licenses to users](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users).</span></span>

> [!NOTE]
> <span data-ttu-id="6380c-121">用户只需要 E5 许可证 (或相应的附加许可证) 才能作为保管人添加到高级电子数据展示案例。</span><span class="sxs-lookup"><span data-stu-id="6380c-121">Users only need an E5 license (or the appropriate add-on license) to be added as custodians to an Advanced eDiscovery case.</span></span> <span data-ttu-id="6380c-122">使用高级电子数据展示管理事例和审阅事例数据的 IT 管理员、电子数据展示管理员、律师、律师律师或律师无需 E5 或附加许可证。</span><span class="sxs-lookup"><span data-stu-id="6380c-122">IT admins, eDiscovery managers, lawyers, paralegals, or investigators who use Advanced eDiscovery to manage cases and review case data don't need an E5 or add-on license.</span></span>

## <a name="step-2-assign-ediscovery-permissions"></a><span data-ttu-id="6380c-123">步骤 2：分配电子数据展示权限</span><span class="sxs-lookup"><span data-stu-id="6380c-123">Step 2: Assign eDiscovery permissions</span></span>

<span data-ttu-id="6380c-124">若要访问高级电子数据展示或添加为高级电子数据展示案例的成员，必须为用户分配适当的权限。</span><span class="sxs-lookup"><span data-stu-id="6380c-124">To access Advanced eDiscovery or added as a member of an Advanced eDiscovery case, a user must be assigned the appropriate permissions.</span></span> <span data-ttu-id="6380c-125">具体而言，必须将用户添加为安全与合规中心内电子数据展示&组的成员。</span><span class="sxs-lookup"><span data-stu-id="6380c-125">Specifically, a user must be added as a member of the eDiscovery Manager role group in the Security & Compliance Center.</span></span> <span data-ttu-id="6380c-126">此角色组的成员可以创建和管理高级电子数据展示事例。</span><span class="sxs-lookup"><span data-stu-id="6380c-126">Members of this role group can create and manage Advanced eDiscovery cases.</span></span> <span data-ttu-id="6380c-127">他们可以添加和删除成员、将保管人和内容位置保留、管理法定保留通知、创建和编辑与案例关联的搜索、将搜索结果添加到审阅集、分析审阅集内的数据以及从高级电子数据展示案例导出和下载。</span><span class="sxs-lookup"><span data-stu-id="6380c-127">They can add and remove members, place custodians and content locations on hold, manage legal hold notifications, create and edit searches associated in a case, add search results to a review set, analyze data in a review set, and export and download from an Advanced eDiscovery case.</span></span>

<span data-ttu-id="6380c-128">完成以下步骤以将用户添加到电子数据展示管理员角色组：</span><span class="sxs-lookup"><span data-stu-id="6380c-128">Complete the following steps to add users to the eDiscovery Manager role group:</span></span>

1. <span data-ttu-id="6380c-129">转到 Microsoft 365 组织中管理员帐户的凭据 [https://protection.office.com/permissions](https://protection.office.com/permissions) 并登录。</span><span class="sxs-lookup"><span data-stu-id="6380c-129">Go to [https://protection.office.com/permissions](https://protection.office.com/permissions) and sign in using the credentials for an admin account in your Microsoft 365 organization.</span></span>

2. <span data-ttu-id="6380c-130">在 **"权限"** 页上，选择 **电子数据展示管理员角色** 组。</span><span class="sxs-lookup"><span data-stu-id="6380c-130">On the **Permissions** page, select the **eDiscovery Manager** role group.</span></span>

3. <span data-ttu-id="6380c-131">在电子数据展示管理器飞出页上 **，单击电子** 数据展示管理器 **部分旁边的"编辑** "。</span><span class="sxs-lookup"><span data-stu-id="6380c-131">On the eDiscovery Manager flyout page, click **Edit** next to the **eDiscovery Manager** section.</span></span>

4. <span data-ttu-id="6380c-132">在编辑角色组向导中的"选择 **电子数据** 展示管理器"页上，单击"**选择电子数据展示管理器"。**</span><span class="sxs-lookup"><span data-stu-id="6380c-132">On the **Choose eDiscovery Manager** page in the edit role group wizard, click **Choose eDiscovery Manager**.</span></span>

5. <span data-ttu-id="6380c-133">单击 **"** 添加"，然后选中要添加到角色组的所有用户的复选框。</span><span class="sxs-lookup"><span data-stu-id="6380c-133">Click **Add** then select the checkbox for all users you want to add to the role group.</span></span>

6. <span data-ttu-id="6380c-134">单击 **"** 添加"添加所选用户，然后单击"**完成"。**</span><span class="sxs-lookup"><span data-stu-id="6380c-134">Click **Add** to add the selected users, and then click **Done**.</span></span>

7. <span data-ttu-id="6380c-135">单击 **"** 保存"将用户添加到角色组，然后单击" **关闭"以** 完成此步骤。</span><span class="sxs-lookup"><span data-stu-id="6380c-135">Click **Save** to add the users to the role group, and then click **Close** to complete the step.</span></span>

### <a name="more-information-about-the-ediscovery-manager-role-group"></a><span data-ttu-id="6380c-136">有关电子数据展示管理员角色组详细信息</span><span class="sxs-lookup"><span data-stu-id="6380c-136">More information about the eDiscovery Manager role group</span></span>

<span data-ttu-id="6380c-137">电子数据展示管理员角色组中有两个子组。</span><span class="sxs-lookup"><span data-stu-id="6380c-137">There are two subgroups in the eDiscovery Manager role group.</span></span> <span data-ttu-id="6380c-138">这些子组之间的差异基于作用域。</span><span class="sxs-lookup"><span data-stu-id="6380c-138">The difference between these subgroups is based on scope.</span></span>

- <span data-ttu-id="6380c-139">**电子数据展示管理器：** 可查看和管理他们创建或作为成员的高级电子数据展示事例。</span><span class="sxs-lookup"><span data-stu-id="6380c-139">**eDiscovery Manager:** Can view and manage the Advanced eDiscovery cases they create or are a member of.</span></span> <span data-ttu-id="6380c-140">如果另一个电子数据展示管理器创建了一个案例，但没有将第二个电子数据展示管理员添加为该案例的成员，则第二个电子数据展示管理器将无法在合规中心的高级电子数据展示页面上查看或打开该案例。</span><span class="sxs-lookup"><span data-stu-id="6380c-140">If another eDiscovery Manager creates a case but doesn't add a second eDiscovery Manager as a member of that case, the second eDiscovery Manager won't be able to view or open the case on the Advanced eDiscovery page in the compliance center.</span></span> <span data-ttu-id="6380c-141">通常，可以将组织中大多数人员添加到电子数据展示管理器子组。</span><span class="sxs-lookup"><span data-stu-id="6380c-141">In general, most people in your organization can be added to the eDiscovery Manager subgroup.</span></span>

- <span data-ttu-id="6380c-142">**电子数据展示管理员：** 可以执行电子数据展示管理员可以执行的所有案例管理任务。</span><span class="sxs-lookup"><span data-stu-id="6380c-142">**eDiscovery Administrator:** Can perform all case management tasks that an eDiscovery Manager can do.</span></span> <span data-ttu-id="6380c-143">此外，电子数据展示管理员可以：</span><span class="sxs-lookup"><span data-stu-id="6380c-143">Additionally, an eDiscovery Administrator can:</span></span>

  - <span data-ttu-id="6380c-144">查看"高级电子数据展示"页上列出的所有事例。</span><span class="sxs-lookup"><span data-stu-id="6380c-144">View all cases that are listed on the Advanced eDiscovery page.</span></span>
  
  - <span data-ttu-id="6380c-145">在将自己添加为案件组的成员后，管理组织的任何案例。</span><span class="sxs-lookup"><span data-stu-id="6380c-145">Manage any case in the organization after they add themselves as a member of the case.</span></span>

  - <span data-ttu-id="6380c-146">访问和导出组织中任何案例的大小写数据。</span><span class="sxs-lookup"><span data-stu-id="6380c-146">Access and export case data for any case in the organization.</span></span>

  <span data-ttu-id="6380c-147">由于访问权限广泛，组织应只有少数几个作为电子数据展示管理员子组成员的管理员。</span><span class="sxs-lookup"><span data-stu-id="6380c-147">Because of the broad scope of access, an organization should have only a few admins who are members of the eDiscovery Administrators subgroup.</span></span>

<span data-ttu-id="6380c-148">有关电子数据展示权限以及分配给电子数据展示管理员角色组的每个角色的说明，请参阅"分配[电子数据展示权限"。](assign-ediscovery-permissions.md)</span><span class="sxs-lookup"><span data-stu-id="6380c-148">For more information about eDiscovery permissions and a description of each role that's assigned to the eDiscovery Manager role group, see [Assign eDiscovery permissions](assign-ediscovery-permissions.md).</span></span>

## <a name="step-3-configure-global-settings-for-advanced-ediscovery"></a><span data-ttu-id="6380c-149">步骤 3：配置高级电子数据展示的全局设置</span><span class="sxs-lookup"><span data-stu-id="6380c-149">Step 3: Configure global settings for Advanced eDiscovery</span></span>

<span data-ttu-id="6380c-150">在组织中人员开始创建和使用案例之前，要完成的最后一步是配置适用于组织中所有案例的全局设置。</span><span class="sxs-lookup"><span data-stu-id="6380c-150">The last step to complete before people in your organization start to create and use cases is to configure global settings that apply to all cases in your organization.</span></span> <span data-ttu-id="6380c-151">目前，唯一的全局设置是 *律师-客户特权* 检测 (将来将有更多的全局设置) 。</span><span class="sxs-lookup"><span data-stu-id="6380c-151">At this time, the only global setting is *attorney-client privilege detection* (more global settings will be available in the future).</span></span> <span data-ttu-id="6380c-152">此设置使你能够在分析审阅集内的数据时运行律师-客户特权模型。</span><span class="sxs-lookup"><span data-stu-id="6380c-152">This setting enables the attorney-client privilege model to run when you analyze data in a review set.</span></span> <span data-ttu-id="6380c-153">模型使用机器学习来确定文档包含本质上合法内容的可能性。</span><span class="sxs-lookup"><span data-stu-id="6380c-153">The model uses machine learning to determine the likelihood that a document contains content that is legal in nature.</span></span> <span data-ttu-id="6380c-154">它还将文档参与者与你在设置模型 (时提交的律师列表) 以确定文档是否至少有一个参与者是律师。</span><span class="sxs-lookup"><span data-stu-id="6380c-154">It also compares the participants of documents with an attorney list (that you submit when setting up the model) to determine if a document has at least one participant who is an attorney.</span></span>

<span data-ttu-id="6380c-155">有关设置和使用律师-客户特权检测模型的信息，请参阅"在高级电子数据展示中设置律师[-客户特权检测"。](attorney-privilege-detection.md)</span><span class="sxs-lookup"><span data-stu-id="6380c-155">For more information about setting up and using the attorney-client privilege detection model, see [Set up attorney-client privilege detection in Advanced eDiscovery](attorney-privilege-detection.md).</span></span>

> [!NOTE]
> <span data-ttu-id="6380c-156">这是一个可选步骤，可以随时执行。</span><span class="sxs-lookup"><span data-stu-id="6380c-156">This is an optional step that you can perform anytime.</span></span> <span data-ttu-id="6380c-157">不实现律师-客户特权检测模型不会阻止你创建和使用高级电子数据展示事例。</span><span class="sxs-lookup"><span data-stu-id="6380c-157">Not implementing the attorney-client privilege detection model doesn't prevent you from creating and using Advanced eDiscovery cases.</span></span>

## <a name="next-steps"></a><span data-ttu-id="6380c-158">后续步骤</span><span class="sxs-lookup"><span data-stu-id="6380c-158">Next steps</span></span>

<span data-ttu-id="6380c-159">设置高级电子数据展示后，即可 [创建案例](create-and-manage-advanced-ediscoveryv2-case.md)。</span><span class="sxs-lookup"><span data-stu-id="6380c-159">After you set up Advanced eDiscovery, you're ready to [create a case](create-and-manage-advanced-ediscoveryv2-case.md).</span></span>
