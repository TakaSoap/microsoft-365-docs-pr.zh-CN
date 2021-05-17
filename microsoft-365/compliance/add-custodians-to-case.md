---
title: 将保管人添加到Advanced eDiscovery案例
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
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: 了解如何在工作流中使用内置保管人Advanced eDiscovery协调工作流，并识别相关数据源。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 9468fb889e9115b3652d1dba8a6c6632bb367fe3
ms.sourcegitcommit: 36d12e02f6fda199ae7f2fb72fe52d7e2b5b4efd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/31/2020
ms.locfileid: "49740339"
---
# <a name="add-custodians-to-an-advanced-ediscovery-case"></a><span data-ttu-id="d30b9-103">将保管人添加到Advanced eDiscovery案例</span><span class="sxs-lookup"><span data-stu-id="d30b9-103">Add custodians to an Advanced eDiscovery case</span></span>

<span data-ttu-id="d30b9-104">使用 Advanced eDiscovery 中的内置保管人管理工具协调您的工作流，以管理保管人并识别与案例相关的监管数据源。</span><span class="sxs-lookup"><span data-stu-id="d30b9-104">Use the built-in custodian management tool in Advanced eDiscovery to coordinate your workflows around managing custodians and identifying relevant, custodial data sources associated with a case.</span></span> <span data-ttu-id="d30b9-105">添加保管人时，系统可自动识别并保留其邮箱Exchange帐户OneDrive for Business保留。</span><span class="sxs-lookup"><span data-stu-id="d30b9-105">When you add a custodian, the system can automatically identify and place a hold on their Exchange mailbox and OneDrive for Business account.</span></span> <span data-ttu-id="d30b9-106">在调查的发现过程中，您还可以确定保管人访问 (参与的其他数据源，如Teams) 邮箱、网站或网站。</span><span class="sxs-lookup"><span data-stu-id="d30b9-106">During the discovery process of your investigation, you might also identify other data sources (such as mailboxes, sites, or Teams) that a custodian accessed or contributed to.</span></span> <span data-ttu-id="d30b9-107">在这种情况下，可以使用保管人管理工具将那些数据源关联为特定保管人。</span><span class="sxs-lookup"><span data-stu-id="d30b9-107">In this situation, you can use the custodian management tool to associate those data sources will a specific custodian.</span></span> <span data-ttu-id="d30b9-108">将保管人添加到案例并将其他数据源与它们关联后，您可以快速保留数据并搜索监管数据。</span><span class="sxs-lookup"><span data-stu-id="d30b9-108">After you add custodians to a case and associate other data source with them, you can quickly preserve data and search the custodial data.</span></span>

<span data-ttu-id="d30b9-109">您可以在以下四个步骤中添加和管理Advanced eDiscovery保管人：</span><span class="sxs-lookup"><span data-stu-id="d30b9-109">You can add and manage custodians in Advanced eDiscovery cases in four steps:</span></span>

1. <span data-ttu-id="d30b9-110">确定保管人。</span><span class="sxs-lookup"><span data-stu-id="d30b9-110">Identify the custodians.</span></span>

2. <span data-ttu-id="d30b9-111">选择保管人数据位置。</span><span class="sxs-lookup"><span data-stu-id="d30b9-111">Choose custodian data locations.</span></span>

3. <span data-ttu-id="d30b9-112">配置保留设置。</span><span class="sxs-lookup"><span data-stu-id="d30b9-112">Configure hold settings.</span></span>

4. <span data-ttu-id="d30b9-113">查看保管人并完成此过程。</span><span class="sxs-lookup"><span data-stu-id="d30b9-113">Review the custodians and complete the process.</span></span>

   <span data-ttu-id="d30b9-114">[!["源"选项卡Advanced eDiscovery大小写 ](../media/AeD-Sources-Tab.png)](../media/AeD-Sources-Tab.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="d30b9-114">[ ![Sources tab in Advanced eDiscovery case](../media/AeD-Sources-Tab.png) ](../media/AeD-Sources-Tab.png#lightbox)</span></span>

## <a name="make-sure-you-have-the-necessary-permissions"></a><span data-ttu-id="d30b9-115">确保您具有必要的权限</span><span class="sxs-lookup"><span data-stu-id="d30b9-115">Make sure you have the necessary permissions</span></span>

<span data-ttu-id="d30b9-116">若要向案例添加保管人，您必须是电子数据展示管理员角色组的成员。</span><span class="sxs-lookup"><span data-stu-id="d30b9-116">To add custodians to a case, you must be a member of the eDiscovery Manager role group.</span></span> <span data-ttu-id="d30b9-117">这为您提供了向案例添加保管人并保留现有数据源的必要权限。</span><span class="sxs-lookup"><span data-stu-id="d30b9-117">This provides you with the necessary permissions to add custodians to a case and place a hold on the custodial data sources.</span></span> <span data-ttu-id="d30b9-118">有关详细信息，请参阅[分配电子数据展示权限](get-started-with-advanced-ediscovery.md#step-2-assign-ediscovery-permissions)。</span><span class="sxs-lookup"><span data-stu-id="d30b9-118">For more information, see [Assign eDiscovery permissions](get-started-with-advanced-ediscovery.md#step-2-assign-ediscovery-permissions).</span></span>

## <a name="step-1-identify-custodians"></a><span data-ttu-id="d30b9-119">步骤 1：标识保管人</span><span class="sxs-lookup"><span data-stu-id="d30b9-119">Step 1: Identify custodians</span></span>

1. <span data-ttu-id="d30b9-120">转到 [https://compliance.microsoft.com](https://compliance.microsoft.com) ，然后使用已分配有相应电子数据展示权限的用户帐户登录。</span><span class="sxs-lookup"><span data-stu-id="d30b9-120">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and sign in with a user account that has been assigned the appropriate eDiscovery permissions.</span></span>

2. <span data-ttu-id="d30b9-121">在 Microsoft 365 合规中心的左侧导航窗格中，单击 **显示所有**，然后单击" **电子数据展示>高级**。</span><span class="sxs-lookup"><span data-stu-id="d30b9-121">In the left navigation pane of the Microsoft 365 compliance center, click **Show all**, and then click **eDiscovery > Advanced**.</span></span>

3. <span data-ttu-id="d30b9-122">在 **"Advanced eDiscovery"** 页上，单击"事例"选项卡，然后选择要添加保管人的案例。</span><span class="sxs-lookup"><span data-stu-id="d30b9-122">On the **Advanced eDiscovery** page, click the **Cases** tab, and then select the case that you want to add custodians to.</span></span>

4. <span data-ttu-id="d30b9-123">单击"**数据源"** 选项卡，然后单击"**添加数据源**  >  **""添加新保管人"。**</span><span class="sxs-lookup"><span data-stu-id="d30b9-123">Click the **Data sources** tab and then click **Add data source** > **Add new custodians**.</span></span>

5. <span data-ttu-id="d30b9-124">通过键入人员姓名或别名的第一部分，将组织中一个或多个用户作为保管人添加到案例。</span><span class="sxs-lookup"><span data-stu-id="d30b9-124">Add one or more users in your organization as custodians to the case by typing the first part of a person's name or alias.</span></span> <span data-ttu-id="d30b9-125">找到正确的人员后，选择其姓名以将其添加到列表中。</span><span class="sxs-lookup"><span data-stu-id="d30b9-125">After you find the correct person, select their name to add them to the list.</span></span>

## <a name="step-2-choose-custodian-data-locations"></a><span data-ttu-id="d30b9-126">步骤 2：选择保管人数据位置</span><span class="sxs-lookup"><span data-stu-id="d30b9-126">Step 2: Choose custodian data locations</span></span>

<span data-ttu-id="d30b9-127">选择保管人后，系统会自动尝试标识并验证这些用户及其数据源。</span><span class="sxs-lookup"><span data-stu-id="d30b9-127">After you select custodians, the system automatically attempts to identify and verify these users and their data sources.</span></span> <span data-ttu-id="d30b9-128">将保管人添加到列表中后，该工具将自动包含每个保管人的主OneDrive帐户。</span><span class="sxs-lookup"><span data-stu-id="d30b9-128">After adding custodians to the list, the tool automatically includes the primary mailbox and OneDrive account for each custodian.</span></span> <span data-ttu-id="d30b9-129">在向案例添加保管人时，可以选择不包括这些数据源。</span><span class="sxs-lookup"><span data-stu-id="d30b9-129">You can choose not to include these data sources when adding custodians to the case.</span></span>

<span data-ttu-id="d30b9-130">除了保管人邮箱和 OneDrive 帐户，您还可以将其他数据位置关联到保管人，例如 SharePoint 站点或保管人是其中一个成员的 Microsoft Team。</span><span class="sxs-lookup"><span data-stu-id="d30b9-130">In addition to a custodian's mailbox and OneDrive account, you can also associate other data locations to a custodian, such as SharePoint site or a Microsoft Team the custodian is a member of.</span></span> <span data-ttu-id="d30b9-131">这允许您保留、收集、分析和查看与案例保管人关联的其他数据源中的内容。</span><span class="sxs-lookup"><span data-stu-id="d30b9-131">This allows you to preserve, collect, analyze, and review content in other data sources associated with the custodians of the case.</span></span>

<span data-ttu-id="d30b9-132">若要取消选择保管人的主邮箱OneDrive帐户，</span><span class="sxs-lookup"><span data-stu-id="d30b9-132">To deselect the primary mailbox and OneDrive account for a custodian:</span></span>

1. <span data-ttu-id="d30b9-133">展开保管人以查看已自动与每个保管人关联的主数据位置。</span><span class="sxs-lookup"><span data-stu-id="d30b9-133">Expand the custodian to view the primary data locations that have been automatically associated to each custodian.</span></span>

2. <span data-ttu-id="d30b9-134">选择 **"\*\*\*\*邮箱或** OneDrive"旁边的"清除"，将保管人邮箱或OneDrive帐户作为此保管人的数据位置相关联。</span><span class="sxs-lookup"><span data-stu-id="d30b9-134">Select **Clear** next to **Mailbox** or **OneDrive** to remove a custodian's mailbox or OneDrive account from being associated as a data location for this custodian.</span></span>

   ![配置要与保管人关联的位置](../media/ConfigureCustodianLocations.png)

<span data-ttu-id="d30b9-136">若要将其他邮箱、站点、Teams或Yammer组关联到特定保管人：</span><span class="sxs-lookup"><span data-stu-id="d30b9-136">To associate other mailboxes, sites, Teams, or Yammer groups to a specific custodian:</span></span>

1. <span data-ttu-id="d30b9-137">展开保管人以显示以下服务以将数据位置与保管人关联。</span><span class="sxs-lookup"><span data-stu-id="d30b9-137">Expand a custodian to display the following services to associate data locations with the custodian.</span></span> <span data-ttu-id="d30b9-138">单击 **服务** 旁边的"编辑"以添加数据位置。</span><span class="sxs-lookup"><span data-stu-id="d30b9-138">Click **Edit** next to a service to add a data location.</span></span>

   - <span data-ttu-id="d30b9-139">**Exchange：** 用于将其他邮箱与保管人关联。</span><span class="sxs-lookup"><span data-stu-id="d30b9-139">**Exchange**: Use to associate other mailboxes to the custodian.</span></span> <span data-ttu-id="d30b9-140">在搜索框中键入用户邮箱或 (组的名称或别名) 至少包含三个字符。</span><span class="sxs-lookup"><span data-stu-id="d30b9-140">Type into the search box the name or alias (a minimum of three characters) of user mailboxes or distribution groups.</span></span> <span data-ttu-id="d30b9-141">选择要分配给保管人的邮箱，然后单击"添加 **"。**</span><span class="sxs-lookup"><span data-stu-id="d30b9-141">Select the mailboxes to assign to the custodian and then click **Add**.</span></span>

   - <span data-ttu-id="d30b9-142">**SharePoint：** 用于将SharePoint网站与保管人关联。</span><span class="sxs-lookup"><span data-stu-id="d30b9-142">**SharePoint**: Use to associate SharePoint sites to the custodian.</span></span> <span data-ttu-id="d30b9-143">在列表中选择网站，或在搜索框中键入 URL 来搜索网站。</span><span class="sxs-lookup"><span data-stu-id="d30b9-143">Select a site in the list or search for a site by typing a URL in the search box.</span></span> <span data-ttu-id="d30b9-144">选择要分配给保管人的网站，然后单击"添加 **"。**</span><span class="sxs-lookup"><span data-stu-id="d30b9-144">Select the sites to assign to the custodian and then click **Add**.</span></span>

   - <span data-ttu-id="d30b9-145">**Teams：** 用于分配Microsoft Teams保管人当前是其中成员的成员。</span><span class="sxs-lookup"><span data-stu-id="d30b9-145">**Teams**: Use to assign the Microsoft Teams the custodian is currently a member of.</span></span> <span data-ttu-id="d30b9-146">选择要分配给保管人的团队，然后单击"添加 **"。**</span><span class="sxs-lookup"><span data-stu-id="d30b9-146">Select the teams to assign to the custodian and then click **Add**.</span></span> <span data-ttu-id="d30b9-147">添加团队后，系统会自动标识并找到SharePoint关联的网站和组邮箱，并将其分配给保管人。</span><span class="sxs-lookup"><span data-stu-id="d30b9-147">After you add a team, the system automatically identifies and locates the SharePoint site and group mailbox associated to that team and assigns them to the custodian.</span></span>

   - <span data-ttu-id="d30b9-148">**Yammer：** 用于分配Yammer保管人当前是其中一个成员的组。</span><span class="sxs-lookup"><span data-stu-id="d30b9-148">**Yammer**:  Use to assign the Yammer groups the custodian is currently a member of.</span></span> <span data-ttu-id="d30b9-149">选择要分配给保管人的组，然后单击"添加 **"。**</span><span class="sxs-lookup"><span data-stu-id="d30b9-149">Select the groups to assign to the custodian and then click **Add**.</span></span> <span data-ttu-id="d30b9-150">添加团队后，系统会自动标识并找到SharePoint组关联的网站和组邮箱，并将其分配给保管人。</span><span class="sxs-lookup"><span data-stu-id="d30b9-150">After you add a team, the system automatically identifies and locates the SharePoint site and group mailbox associated to that group and assigns them to the custodian.</span></span>

   > [!NOTE]
   > <span data-ttu-id="d30b9-151">可以使用 Exchange和 SharePoint 位置选取器将 (不是保管人成员的其他团队或 Yammer 组) 保管人。</span><span class="sxs-lookup"><span data-stu-id="d30b9-151">You can use the **Exchange** and **SharePoint** location pickers to associate other teams or Yammer groups (that a custodian is not a member of) to a custodian.</span></span> <span data-ttu-id="d30b9-152">为此，您必须添加与每个团队或组关联的邮箱和Yammer网站。</span><span class="sxs-lookup"><span data-stu-id="d30b9-152">To do this, you have to add both the mailbox and site associated with each team or Yammer group.</span></span>

2. <span data-ttu-id="d30b9-153">通过展开表中的每个保管人，可以查看分配给每个保管Teams的邮箱、站点、Yammer组总数。</span><span class="sxs-lookup"><span data-stu-id="d30b9-153">You can view the total number of mailboxes, sites, Teams, and Yammer groups assigned to each custodian by expanding each custodian in the table.</span></span> <span data-ttu-id="d30b9-154">在最终确定每个保管人分配的数据位置后，这些关联将在托管工作流中的收集、处理和审阅阶段Advanced eDiscovery使用。</span><span class="sxs-lookup"><span data-stu-id="d30b9-154">When you've finalized the assigned data locations for each custodian, these associations will be maintained and used during the collection, processing, and review stages in the Advanced eDiscovery workflow.</span></span>

3. <span data-ttu-id="d30b9-155">添加保管人并配置其数据位置后，单击"下一步"转到"**保留设置"** 页。</span><span class="sxs-lookup"><span data-stu-id="d30b9-155">After adding custodians and configuring their data locations, click **Next** to go to the **Hold settings** page.</span></span>  

## <a name="step-3-configure-hold-settings"></a><span data-ttu-id="d30b9-156">步骤 3：配置保留设置</span><span class="sxs-lookup"><span data-stu-id="d30b9-156">Step 3: Configure hold settings</span></span>

 <span data-ttu-id="d30b9-157">完成保管人及其数据位置后，可以将部分或所有保管人保留。</span><span class="sxs-lookup"><span data-stu-id="d30b9-157">After you've finalized the custodians and their data locations, you can place some or all of the custodians on hold.</span></span> <span data-ttu-id="d30b9-158">当您将保管人保留时，与保管人关联的所有内容位置中的内容将一直保留，直到您删除保留或将保管人从保留中解除。</span><span class="sxs-lookup"><span data-stu-id="d30b9-158">When you place a custodian on hold, all content in all content locations that are associated with the custodian is preserved until you remove the hold or release the custodian from the hold.</span></span> <span data-ttu-id="d30b9-159">在某些情况下，你可能希望向事例添加保管人，而不将其置于保留状态。</span><span class="sxs-lookup"><span data-stu-id="d30b9-159">In some cases, you may want to add custodians to a case without placing them on hold.</span></span>

<span data-ttu-id="d30b9-160">将保管人和数据源放在保留状态：</span><span class="sxs-lookup"><span data-stu-id="d30b9-160">To place the custodians and data sources on hold:</span></span>

1. <span data-ttu-id="d30b9-161">在 **"保留设置** "页上，可以通过选中"保留"列下的复选框将保留应用于 **各个保管** 人。</span><span class="sxs-lookup"><span data-stu-id="d30b9-161">On the **Hold settings** page, you can apply a hold to individual custodians by selecting the checkbox under the **Hold** column.</span></span>

   <span data-ttu-id="d30b9-162">或者，可以通过选中列顶部的"保留"复选框来保留所有保管人。</span><span class="sxs-lookup"><span data-stu-id="d30b9-162">Alternatively, you can place all custodians on hold by selecting the **Hold** checkbox at the top of the column.</span></span>

2. <span data-ttu-id="d30b9-163">验证保管人保留选择，然后单击下一 **步**。</span><span class="sxs-lookup"><span data-stu-id="d30b9-163">Verify the custodian hold selections and then click **Next**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="d30b9-164">如果您没有将保管人保留，则保管人及其关联的数据源将添加到案例，但与该案例关联的保留不会保留这些数据源中的内容。</span><span class="sxs-lookup"><span data-stu-id="d30b9-164">If you don't place a hold on a custodian, the custodian and their associated data sources will be added to the case but the content in those data sources won't preserved by the hold that associated with the case.</span></span>

## <a name="step-4-review-the-custodians-and-complete-the-process"></a><span data-ttu-id="d30b9-165">步骤 4：检查保管人并完成此过程</span><span class="sxs-lookup"><span data-stu-id="d30b9-165">Step 4: Review the custodians and complete the process</span></span>

<span data-ttu-id="d30b9-166">在将保管人实际添加到案例之前，你可以查看保管人列表、分配给保管人的数据位置以及保留设置。</span><span class="sxs-lookup"><span data-stu-id="d30b9-166">Before you actually add the custodians to the case, you can review the list of custodians, the data locations assigned to them, and the hold settings.</span></span>

1. <span data-ttu-id="d30b9-167">验证并查看与表中每个保管人关联的所有数据源计数和保留设置。</span><span class="sxs-lookup"><span data-stu-id="d30b9-167">Verify and review all the data sources count and the hold setting associated with each custodian in the table.</span></span> <span data-ttu-id="d30b9-168">如有必要，请返回到"识别 **保管人** "或" **保留设置"** 页以做出任何更改。</span><span class="sxs-lookup"><span data-stu-id="d30b9-168">If necessary, go back to the **Identify custodian** or **Hold settings** pages to make any changes.</span></span>

2. <span data-ttu-id="d30b9-169">单击 **"** 提交"将保管人及其数据位置添加到案例，并应用所有托管保留设置。</span><span class="sxs-lookup"><span data-stu-id="d30b9-169">Click **Submit** to add custodians and their data locations to the case and apply all custodial hold settings.</span></span>

   <span data-ttu-id="d30b9-170">新保管人将添加到案例，并显示在" **数据源"** 选项卡上。</span><span class="sxs-lookup"><span data-stu-id="d30b9-170">The new custodians are added to the case and displayed on the **Data sources** tab.</span></span>

   <span data-ttu-id="d30b9-171">[!["数据源"选项卡上列出的保管人 ](../media/DataSourcesTab.png)](../media/DataSourcesTab.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="d30b9-171">[ ![Custodians listed on the Data sources tab](../media/DataSourcesTab.png) ](../media/DataSourcesTab.png#lightbox)</span></span>
