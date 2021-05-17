---
title: 在Advanced eDiscovery中Microsoft 365
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
- m365solution-scenario
search.appverid:
- MOE150
- MET150
description: 本文介绍如何设置Advanced eDiscovery，以便你可以开始创建和管理事例。 它还介绍了所需的 Microsoft 订阅和许可。 完成几个快速步骤后，Advanced eDiscovery即可使用。
ms.openlocfilehash: 6c6aed482da8f203154d94313ec04519d6a330ea
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919739"
---
# <a name="set-up-microsoft-365-advanced-ediscovery"></a><span data-ttu-id="509fd-105">设置Microsoft 365 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="509fd-105">Set up Microsoft 365 Advanced eDiscovery</span></span>

<span data-ttu-id="509fd-106">Advanced eDiscovery中Microsoft 365提供了端到端工作流，以保留、收集、审阅、分析和导出对组织内部和外部调查做出响应的数据。</span><span class="sxs-lookup"><span data-stu-id="509fd-106">Advanced eDiscovery in Microsoft 365 provides an end-to-end workflow to preserve, collect, review, analyze, and export data that's responsive to your organization's internal and external investigations.</span></span> <span data-ttu-id="509fd-107">部署 Advanced eDiscovery 不需要任何内容，但 IT 管理员和电子数据展示管理员必须完成一些先决条件任务，然后组织才能开始创建和使用 Advanced eDiscovery 事例来管理调查。</span><span class="sxs-lookup"><span data-stu-id="509fd-107">Nothing is needed to deploy Advanced eDiscovery, but there are some prerequisite tasks that an IT admin and eDiscovery manager have to complete before your organization can start to create and use Advanced eDiscovery cases to manage your investigations.</span></span>

<span data-ttu-id="509fd-108">本文讨论设置项目所需的Advanced eDiscovery。</span><span class="sxs-lookup"><span data-stu-id="509fd-108">This article discusses the following steps necessary to set up Advanced eDiscovery.</span></span>

![设置项目Advanced eDiscovery](../media/set-up-advanced-ediscovery.png)

<span data-ttu-id="509fd-110">这包括确保访问事例所需的适当许可Advanced eDiscovery并将保管人添加到事例，并将权限分配给法律和调查团队，以便他们可以访问和管理事例。</span><span class="sxs-lookup"><span data-stu-id="509fd-110">This includes ensuring the proper licensing required to access Advanced eDiscovery and add custodians to cases, and assigning permissions to your legal and investigation team so they can access and manage cases.</span></span>

## <a name="step-1-verify-and-assign-appropriate-licenses"></a><span data-ttu-id="509fd-111">步骤 1：验证并分配适当的许可证</span><span class="sxs-lookup"><span data-stu-id="509fd-111">Step 1: Verify and assign appropriate licenses</span></span>

<span data-ttu-id="509fd-112">用户Advanced eDiscovery需要相应的组织订阅和每用户许可。</span><span class="sxs-lookup"><span data-stu-id="509fd-112">Licensing for Advanced eDiscovery requires the appropriate organization subscription and per-user licensing.</span></span> <span data-ttu-id="509fd-113">有关许可要求列表，Advanced eDiscovery订阅[和许可](overview-ediscovery-20.md#subscriptions-and-licensing)。</span><span class="sxs-lookup"><span data-stu-id="509fd-113">For a list of licensing requirements for Advanced eDiscovery, see [Subscriptions and licensing](overview-ediscovery-20.md#subscriptions-and-licensing).</span></span>

## <a name="step-2-assign-ediscovery-permissions"></a><span data-ttu-id="509fd-114">步骤 2：分配电子数据展示权限</span><span class="sxs-lookup"><span data-stu-id="509fd-114">Step 2: Assign eDiscovery permissions</span></span>

<span data-ttu-id="509fd-115">若要Advanced eDiscovery或添加为 Advanced eDiscovery的成员，必须为用户分配适当的权限。</span><span class="sxs-lookup"><span data-stu-id="509fd-115">To access Advanced eDiscovery or added as a member of an Advanced eDiscovery case, a user must be assigned the appropriate permissions.</span></span> <span data-ttu-id="509fd-116">具体而言，必须将用户添加为安全与合规中心内电子数据展示&组的成员。</span><span class="sxs-lookup"><span data-stu-id="509fd-116">Specifically, a user must be added as a member of the eDiscovery Manager role group in the Security & Compliance Center.</span></span> <span data-ttu-id="509fd-117">此角色组的成员可以创建和管理Advanced eDiscovery案例。</span><span class="sxs-lookup"><span data-stu-id="509fd-117">Members of this role group can create and manage Advanced eDiscovery cases.</span></span> <span data-ttu-id="509fd-118">他们可以添加和删除成员、将保管人和内容位置保留、管理合法保留通知、创建和编辑与案例关联的搜索、将搜索结果添加到审阅集、分析审阅集内的数据以及从 Advanced eDiscovery 案例导出和下载。</span><span class="sxs-lookup"><span data-stu-id="509fd-118">They can add and remove members, place custodians and content locations on hold, manage legal hold notifications, create and edit searches associated in a case, add search results to a review set, analyze data in a review set, and export and download from an Advanced eDiscovery case.</span></span>

<span data-ttu-id="509fd-119">完成以下步骤以将用户添加到电子数据展示管理员角色组：</span><span class="sxs-lookup"><span data-stu-id="509fd-119">Complete the following steps to add users to the eDiscovery Manager role group:</span></span>

1. <span data-ttu-id="509fd-120">转到 <https://protection.office.com/permissions> ，然后使用组织中管理员帐户的凭据Microsoft 365登录。</span><span class="sxs-lookup"><span data-stu-id="509fd-120">Go to <https://protection.office.com/permissions> and sign in using the credentials for an admin account in your Microsoft 365 organization.</span></span>

2. <span data-ttu-id="509fd-121">在" **权限"** 页上，选择 **电子数据展示管理员角色** 组。</span><span class="sxs-lookup"><span data-stu-id="509fd-121">On the **Permissions** page, select the **eDiscovery Manager** role group.</span></span>

3. <span data-ttu-id="509fd-122">在"电子数据展示管理器"飞出页面上，单击 **"电子** 数据展示管理器"部分 **旁边的"编辑** "。</span><span class="sxs-lookup"><span data-stu-id="509fd-122">On the eDiscovery Manager flyout page, click **Edit** next to the **eDiscovery Manager** section.</span></span>

4. <span data-ttu-id="509fd-123">在编辑角色组向导中的"选择 **电子数据** 展示管理器"页上，单击"**选择电子数据展示管理器"。**</span><span class="sxs-lookup"><span data-stu-id="509fd-123">On the **Choose eDiscovery Manager** page in the edit role group wizard, click **Choose eDiscovery Manager**.</span></span>

5. <span data-ttu-id="509fd-124">单击 **"** 添加"，然后选中要添加到角色组的所有用户的复选框。</span><span class="sxs-lookup"><span data-stu-id="509fd-124">Click **Add** then select the checkbox for all users you want to add to the role group.</span></span>

6. <span data-ttu-id="509fd-125">单击 **"** 添加"添加所选用户，然后单击"完成 **"。**</span><span class="sxs-lookup"><span data-stu-id="509fd-125">Click **Add** to add the selected users, and then click **Done**.</span></span>

7. <span data-ttu-id="509fd-126">单击 **"** 保存"将用户添加到角色组，然后单击 **"关闭"** 以完成此步骤。</span><span class="sxs-lookup"><span data-stu-id="509fd-126">Click **Save** to add the users to the role group, and then click **Close** to complete the step.</span></span>

### <a name="more-information-about-the-ediscovery-manager-role-group"></a><span data-ttu-id="509fd-127">有关电子数据展示管理员角色组详细信息</span><span class="sxs-lookup"><span data-stu-id="509fd-127">More information about the eDiscovery Manager role group</span></span>

<span data-ttu-id="509fd-128">电子数据展示管理员角色组中有两个子组。</span><span class="sxs-lookup"><span data-stu-id="509fd-128">There are two subgroups in the eDiscovery Manager role group.</span></span> <span data-ttu-id="509fd-129">这些子组之间的差异基于作用域。</span><span class="sxs-lookup"><span data-stu-id="509fd-129">The difference between these subgroups is based on scope.</span></span>

- <span data-ttu-id="509fd-130">**电子数据展示管理器**：可以查看和管理Advanced eDiscovery或是这些事例的成员。</span><span class="sxs-lookup"><span data-stu-id="509fd-130">**eDiscovery Manager**: Can view and manage the Advanced eDiscovery cases they create or are a member of.</span></span> <span data-ttu-id="509fd-131">如果另一个电子数据展示管理员创建了一个案例，但没有将第二个电子数据展示管理员添加为该案例的成员，则第二个电子数据展示管理员将无法在合规中心的 Advanced eDiscovery 页面上查看或打开该案例。</span><span class="sxs-lookup"><span data-stu-id="509fd-131">If another eDiscovery Manager creates a case but doesn't add a second eDiscovery Manager as a member of that case, the second eDiscovery Manager won't be able to view or open the case on the Advanced eDiscovery page in the compliance center.</span></span> <span data-ttu-id="509fd-132">通常，可以将您组织中的大多数人员添加到电子数据展示管理员子组。</span><span class="sxs-lookup"><span data-stu-id="509fd-132">In general, most people in your organization can be added to the eDiscovery Manager subgroup.</span></span>

- <span data-ttu-id="509fd-133">**电子数据展示管理员**：可以执行电子数据展示管理员可以执行的所有案例管理任务。</span><span class="sxs-lookup"><span data-stu-id="509fd-133">**eDiscovery Administrator**: Can perform all case management tasks that an eDiscovery Manager can do.</span></span> <span data-ttu-id="509fd-134">此外，电子数据展示管理员可以：</span><span class="sxs-lookup"><span data-stu-id="509fd-134">Additionally, an eDiscovery Administrator can:</span></span>

  - <span data-ttu-id="509fd-135">查看"高级电子数据展示"页面上列出的所有事例。</span><span class="sxs-lookup"><span data-stu-id="509fd-135">View all cases that are listed on the Advanced eDiscovery page.</span></span>
  
  - <span data-ttu-id="509fd-136">在将自己添加为案例的成员之后管理组织内的任何案例。</span><span class="sxs-lookup"><span data-stu-id="509fd-136">Manage any case in the organization after they add themselves as a member of the case.</span></span>

  - <span data-ttu-id="509fd-137">访问和导出组织中任意案例的大小写数据。</span><span class="sxs-lookup"><span data-stu-id="509fd-137">Access and export case data for any case in the organization.</span></span>

  <span data-ttu-id="509fd-138">由于访问权限的范围很广，组织应仅应该只有部分管理员是电子数据展示管理员子组的成员。</span><span class="sxs-lookup"><span data-stu-id="509fd-138">Because of the broad scope of access, an organization should have only a few admins who are members of the eDiscovery Administrators subgroup.</span></span>

<span data-ttu-id="509fd-139">有关电子数据展示权限以及分配给电子数据展示管理员角色组的每个角色的说明，请参阅分配 [电子数据展示权限](assign-ediscovery-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="509fd-139">For more information about eDiscovery permissions and a description of each role that's assigned to the eDiscovery Manager role group, see [Assign eDiscovery permissions](assign-ediscovery-permissions.md).</span></span>

## <a name="step-3-configure-global-settings-for-advanced-ediscovery"></a><span data-ttu-id="509fd-140">步骤 3：配置全局设置Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="509fd-140">Step 3: Configure global settings for Advanced eDiscovery</span></span>

<span data-ttu-id="509fd-141">在组织中人员开始创建和使用案例之前，要完成的最后一步是配置适用于组织中所有案例的全局设置。</span><span class="sxs-lookup"><span data-stu-id="509fd-141">The last step to complete before people in your organization start to create and use cases is to configure global settings that apply to all cases in your organization.</span></span> <span data-ttu-id="509fd-142">目前，唯一的全局设置是律师 *-客户特权* 检测 (将来将有更多的全局设置) 。</span><span class="sxs-lookup"><span data-stu-id="509fd-142">At this time, the only global setting is *attorney-client privilege detection* (more global settings will be available in the future).</span></span> <span data-ttu-id="509fd-143">此设置允许律师-客户特权模型在您分析审阅集内的数据时运行。</span><span class="sxs-lookup"><span data-stu-id="509fd-143">This setting enables the attorney-client privilege model to run when you analyze data in a review set.</span></span> <span data-ttu-id="509fd-144">模型使用机器学习来确定文档是否包含本质上是合法的内容。</span><span class="sxs-lookup"><span data-stu-id="509fd-144">The model uses machine learning to determine the likelihood that a document contains content that is legal in nature.</span></span> <span data-ttu-id="509fd-145">它还将文档参与者与律师列表 (设置模型) 时提交的列表进行比较，以确定文档是否至少有一个参与者是律师。</span><span class="sxs-lookup"><span data-stu-id="509fd-145">It also compares the participants of documents with an attorney list (that you submit when setting up the model) to determine if a document has at least one participant who is an attorney.</span></span>

<span data-ttu-id="509fd-146">有关设置和使用律师-客户特权检测模型的信息，请参阅在 Advanced eDiscovery 中设置律师[-客户特权Advanced eDiscovery。](attorney-privilege-detection.md)</span><span class="sxs-lookup"><span data-stu-id="509fd-146">For more information about setting up and using the attorney-client privilege detection model, see [Set up attorney-client privilege detection in Advanced eDiscovery](attorney-privilege-detection.md).</span></span>

> [!NOTE]
> <span data-ttu-id="509fd-147">这是一个可选步骤，可以随时执行。</span><span class="sxs-lookup"><span data-stu-id="509fd-147">This is an optional step that you can perform anytime.</span></span> <span data-ttu-id="509fd-148">不实现律师-客户特权检测模型不会阻止你创建和使用Advanced eDiscovery案例。</span><span class="sxs-lookup"><span data-stu-id="509fd-148">Not implementing the attorney-client privilege detection model doesn't prevent you from creating and using Advanced eDiscovery cases.</span></span>

## <a name="next-steps"></a><span data-ttu-id="509fd-149">后续步骤</span><span class="sxs-lookup"><span data-stu-id="509fd-149">Next steps</span></span>

<span data-ttu-id="509fd-150">设置Advanced eDiscovery后，就可以[创建案例了](create-and-manage-advanced-ediscoveryv2-case.md)。</span><span class="sxs-lookup"><span data-stu-id="509fd-150">After you set up Advanced eDiscovery, you're ready to [create a case](create-and-manage-advanced-ediscoveryv2-case.md).</span></span>