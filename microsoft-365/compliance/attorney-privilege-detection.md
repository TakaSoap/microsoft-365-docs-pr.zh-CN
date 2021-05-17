---
title: 在服务中设置律师-客户Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: 在审查案例内容时，使用律师-客户特权检测模型使用基于机器学习的特权Advanced eDiscovery检测。
ms.openlocfilehash: 73a0efeece7bc331045e9bbe1a1da56f9fd24700
ms.sourcegitcommit: 9ce9001aa41172152458da27c1c52825355f426d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/03/2020
ms.locfileid: "47358038"
---
# <a name="set-up-attorney-client-privilege-detection-in-advanced-ediscovery"></a><span data-ttu-id="ec943-103">在服务中设置律师-客户Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="ec943-103">Set up attorney-client privilege detection in Advanced eDiscovery</span></span>

<span data-ttu-id="ec943-104">任何电子数据展示过程的审阅阶段的主要且成本高昂的方面是查看文档的特权内容。</span><span class="sxs-lookup"><span data-stu-id="ec943-104">A major and costly aspect of the review phase of any eDiscovery process is reviewing documents for privileged content.</span></span> <span data-ttu-id="ec943-105">Advanced eDiscovery提供基于机器学习的特权内容的检测，提高此过程的效率。</span><span class="sxs-lookup"><span data-stu-id="ec943-105">Advanced eDiscovery provides machine learning-based detection of privileged content to make this process more efficient.</span></span> <span data-ttu-id="ec943-106">此功能称为 *律师-客户特权检测*。</span><span class="sxs-lookup"><span data-stu-id="ec943-106">This feature is called *attorney-client privilege detection*.</span></span>

## <a name="how-does-it-work"></a><span data-ttu-id="ec943-107">它的工作原理</span><span class="sxs-lookup"><span data-stu-id="ec943-107">How does it work?</span></span>

<span data-ttu-id="ec943-108">启用律师-客户特权检测后，当您分析审阅集内的数据时，律师-客户特权检测模型将处理审阅集内的所有[](analyzing-data-in-review-set.md)文档。</span><span class="sxs-lookup"><span data-stu-id="ec943-108">When attorney-client privilege detection is enabled, all documents in a review set will be processed by the attorney-client privilege detection model when you [analyze the data](analyzing-data-in-review-set.md) in the review set.</span></span> <span data-ttu-id="ec943-109">模型查找两项内容：</span><span class="sxs-lookup"><span data-stu-id="ec943-109">The model looks for two things:</span></span>

- <span data-ttu-id="ec943-110">特权内容 – 模型使用机器学习来确定文档包含本质上合法内容的可能性。</span><span class="sxs-lookup"><span data-stu-id="ec943-110">Privileged content – The model uses machine learning to determine the likelihood that the document contains content that is legal in nature.</span></span>

- <span data-ttu-id="ec943-111">参与者 – 作为设置律师-客户特权检测的一部分，您必须为组织提交律师列表。</span><span class="sxs-lookup"><span data-stu-id="ec943-111">Participants – As part of setting up attorney-client privilege detection, you have to submit a list of attorneys for your organization.</span></span> <span data-ttu-id="ec943-112">模型随后将文档参与者与代理列表进行比较，以确定文档是否具有至少一个代理参与者。</span><span class="sxs-lookup"><span data-stu-id="ec943-112">The model then compares the participants of the document with the attorney list to determine if a document has at least one attorney participant.</span></span>

<span data-ttu-id="ec943-113">模型将生成每个文档的以下三个属性：</span><span class="sxs-lookup"><span data-stu-id="ec943-113">The model produces the following three properties for every document:</span></span>

- <span data-ttu-id="ec943-114">**AttorneyClientPrivilegeScore：** 文档在本质上是合法的可能性;分数的值介于 **0** 和 **1 之间**。</span><span class="sxs-lookup"><span data-stu-id="ec943-114">**AttorneyClientPrivilegeScore:** The likelihood the document is legal in nature; the values for the score are between **0** and **1**.</span></span>

- <span data-ttu-id="ec943-115">**HasAttorney：** 如果律师列表中列出了其中一个文档参与者，则此属性设置为 **true;** 否则值为 **false**。</span><span class="sxs-lookup"><span data-stu-id="ec943-115">**HasAttorney:** This property is set to **true** if one of the document participants is listed in the attorney list; otherwise the value is **false**.</span></span> <span data-ttu-id="ec943-116">如果你的组织未上传代理列表，则此值设置为 **false**。</span><span class="sxs-lookup"><span data-stu-id="ec943-116">The value is also set to **false** if your organization didn't upload an attorney list.</span></span>

- <span data-ttu-id="ec943-117">**IsPrivilege：** 如果 **"AttorneyClientPrivilegeScore"** 的值超过阈值或文档具有律师参与者，则此属性设置为 **true;** 否则，值设置为 **false**。</span><span class="sxs-lookup"><span data-stu-id="ec943-117">**IsPrivilege:** This property is set to **true** if the value for **AttorneyClientPrivilegeScore** is above the threshold *or* if the document has an attorney participant; otherwise the value is set to **false**.</span></span>

<span data-ttu-id="ec943-118">这些属性 (及其对应的值) 添加到审阅集内文档的文件元数据中，如以下屏幕截图所示：</span><span class="sxs-lookup"><span data-stu-id="ec943-118">These properties (and their corresponding values) are added to the file metadata of the documents in a review set, as shown in the following screenshot:</span></span>

![文件元数据中显示的律师-客户特权属性](../media/AeDAttorneyClientPrivilegeMetadata.png)

<span data-ttu-id="ec943-120">这三个属性也可在审阅集内搜索。</span><span class="sxs-lookup"><span data-stu-id="ec943-120">These three properties are also searchable within a review set.</span></span> <span data-ttu-id="ec943-121">有关详细信息，请参阅查询 [审阅集内的数据](review-set-search.md)。</span><span class="sxs-lookup"><span data-stu-id="ec943-121">For more information, see [Query the data in a review set](review-set-search.md).</span></span>

## <a name="set-up-the-attorney-client-privilege-detection-model"></a><span data-ttu-id="ec943-122">设置律师-客户特权检测模型</span><span class="sxs-lookup"><span data-stu-id="ec943-122">Set up the attorney-client privilege detection model</span></span>

<span data-ttu-id="ec943-123">若要启用律师-客户特权检测模型，你的组织必须将其打开，然后上载律师列表。</span><span class="sxs-lookup"><span data-stu-id="ec943-123">To enable the attorney-client privilege detection model, your organization has to turn it on and then upload an attorney list.</span></span>

### <a name="step-1-turn-on-attorney-client-privilege-detection"></a><span data-ttu-id="ec943-124">步骤 1：启用律师-客户特权检测</span><span class="sxs-lookup"><span data-stu-id="ec943-124">Step 1: Turn on attorney-client privilege detection</span></span>

<span data-ttu-id="ec943-125">作为您组织中电子数据展示管理员 (电子数据展示管理员角色组) 中的电子数据展示管理员子组的成员必须在 Advanced eDiscovery 事例中提供模型。</span><span class="sxs-lookup"><span data-stu-id="ec943-125">A person who is an eDiscovery Administrator in your organization (a member of the eDiscovery Administrator subgroup in the eDiscovery Manager role group) must make the model available in your Advanced eDiscovery cases.</span></span>

1. <span data-ttu-id="ec943-126">在安全&合规中心，转到"**电子数据展示> Advanced eDiscovery"。**</span><span class="sxs-lookup"><span data-stu-id="ec943-126">In the Security & Compliance Center, go to **eDiscovery > Advanced eDiscovery**.</span></span>

2. <span data-ttu-id="ec943-127">在Advanced eDiscovery **主页** 上的"设置"磁贴中，单击"配置 **全局分析设置"。**</span><span class="sxs-lookup"><span data-stu-id="ec943-127">On the **Advanced eDiscovery** home page, in the **Settings** tile, click **Configure global analytics settings**.</span></span>

   ![选择"配置实验性功能"](../media/AeDExperimentalFeatures.png)

3. <span data-ttu-id="ec943-129">在"**分析设置"** 选项卡上，选择"**管理律师-客户特权设置"。**</span><span class="sxs-lookup"><span data-stu-id="ec943-129">On the **Analytics settings** tab, select **Manage attorney-client privilege setting**.</span></span>

4. <span data-ttu-id="ec943-130">在 **律师-客户特权** 弹出页面上，使用开关打开该功能，然后选择 **保存**。</span><span class="sxs-lookup"><span data-stu-id="ec943-130">On the **Attorney-client privilege** flyout page, use the toggle to turn on the feature and then select **Save**.</span></span>

### <a name="step-2-upload-a-list-of-attorneys-optional"></a><span data-ttu-id="ec943-131">步骤 2：Upload可选律师 (列表) </span><span class="sxs-lookup"><span data-stu-id="ec943-131">Step 2: Upload a list of attorneys (optional)</span></span>

<span data-ttu-id="ec943-132">若要充分利用律师-客户特权检测模型，并使用前面所述的"律师或潜在特权"检测的结果，我们建议您为在组织工作的律师和律师上载电子邮件地址列表。</span><span class="sxs-lookup"><span data-stu-id="ec943-132">To take full advantage of the attorney-client privilege detection model and use the results of the **Has Attorney** or **Potentially Privileged** detection that was previously described, we recommend that you upload a list of email addresses for the lawyers and legal personnel who work for your organization.</span></span> 

<span data-ttu-id="ec943-133">要上载律师-客户特权检测模型使用律师列表，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="ec943-133">To upload an attorney list for use by the attorney-client privilege detection model:</span></span>

1. <span data-ttu-id="ec943-134">创建 .csv 文件（不带标题行），在单独的行上为每个合适的人员添加电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="ec943-134">Create a .csv file (without a header row) and add the email address for each appropriate person on a separate line.</span></span> <span data-ttu-id="ec943-135">将此文件保存到本地计算机。</span><span class="sxs-lookup"><span data-stu-id="ec943-135">Save this file to your local computer.</span></span>

2. <span data-ttu-id="ec943-136">在Advanced eDiscovery **主页** 上的"设置 **磁贴中**，选择"配置实验性功能"，然后选择"管理 **律师-客户特权设置"。**</span><span class="sxs-lookup"><span data-stu-id="ec943-136">On the **Advanced eDiscovery** home page, in the **Settings** tile, select **Configure experimental features**, and then select **Manage attorney-client privilege setting**.</span></span>

   <span data-ttu-id="ec943-137">将显示 **"律师-客户特权** "页，并且" **律师-客户特权检测** "切换处于打开状态。</span><span class="sxs-lookup"><span data-stu-id="ec943-137">The **Attorney-client privilege** page is displayed, and the **Attorney-client privilege detection** toggle is turned on.</span></span>

   ![律师-客户特权飞出页](../media/AeDUploadAttorneyList.png)

3. <span data-ttu-id="ec943-139">选择 **"** 浏览"，然后查找并选择.csv 1 中创建的配置文件。</span><span class="sxs-lookup"><span data-stu-id="ec943-139">Select **Browse** and then find and select the .csv file that you created in step 1.</span></span>

4. <span data-ttu-id="ec943-140">选择 **"保存** "上载律师列表。</span><span class="sxs-lookup"><span data-stu-id="ec943-140">Select **Save** to upload the attorney list.</span></span>

## <a name="use-the-attorney-client-privilege-detection-model"></a><span data-ttu-id="ec943-141">使用律师-客户特权检测模型</span><span class="sxs-lookup"><span data-stu-id="ec943-141">Use the attorney-client privilege detection model</span></span>

<span data-ttu-id="ec943-142">按照本节中的步骤对审阅集内的文档使用律师-客户特权检测。</span><span class="sxs-lookup"><span data-stu-id="ec943-142">Follow the steps in this section to use attorney-client privilege detection for documents in a review set.</span></span>

### <a name="step-1-create-a-smart-tag-group-with-attorney-client-privilege-detection-model"></a><span data-ttu-id="ec943-143">步骤 1：使用律师-客户特权检测模型创建智能标记组</span><span class="sxs-lookup"><span data-stu-id="ec943-143">Step 1: Create a smart tag group with attorney-client privilege detection model</span></span>

<span data-ttu-id="ec943-144">在审核过程中查看律师-客户特权检测结果的主要方法之一是使用智能标记组。</span><span class="sxs-lookup"><span data-stu-id="ec943-144">One of the primary ways to see the results of attorney-client privilege detection in your review process is by using a smart tag group.</span></span> <span data-ttu-id="ec943-145">智能标记组指示律师-客户特权检测的结果，并在智能标记组中的标记旁边在线显示结果。</span><span class="sxs-lookup"><span data-stu-id="ec943-145">A smart tag group indicates the results of the attorney-client privilege detection and shows the results in-line next to the tags in a smart tag group.</span></span> <span data-ttu-id="ec943-146">这样，您可以在文档审阅过程中快速识别潜在的特权文档。</span><span class="sxs-lookup"><span data-stu-id="ec943-146">This lets you quickly identify potentially privileged documents during document review.</span></span> <span data-ttu-id="ec943-147">此外，您还可以使用智能标记组的标记来标记具有特权或非特权的文档。</span><span class="sxs-lookup"><span data-stu-id="ec943-147">Additionally, you can also use the tags in the smart tag group to tag documents as privileged or non-privileged.</span></span> <span data-ttu-id="ec943-148">有关智能标记详细信息，请参阅在智能标记[Advanced eDiscovery。](smart-tags.md)</span><span class="sxs-lookup"><span data-stu-id="ec943-148">For more information about smart tags, see [Set up smart tags in Advanced eDiscovery](smart-tags.md).</span></span>

1. <span data-ttu-id="ec943-149">在包含步骤 1 中分析的文档的审阅集内，选择"管理 **审阅** 集"，然后选择"**管理标记"。**</span><span class="sxs-lookup"><span data-stu-id="ec943-149">In the review set that contains the documents that you analyzed in Step 1, select **Manage review set** and then select **Manage tags**.</span></span>
 
2. <span data-ttu-id="ec943-150">在 **"标记**"下，选择"添加组"旁边的下拉 **组件**，然后选择"**添加智能标记组"。**</span><span class="sxs-lookup"><span data-stu-id="ec943-150">Under **Tags**, select the pull-down next to **Add group** and then select **Add smart tag group**.</span></span>

   ![选择"添加智能标记组"](../media/AeDCreateSmartTag.png)

3. <span data-ttu-id="ec943-152">在"**为智能标记选择模型"页上**，选择"**律师\*\*\*\*-客户特权"旁边的"选择"。**</span><span class="sxs-lookup"><span data-stu-id="ec943-152">On the **Choose a model for your smart tag** page, choose **Select** next to **Attorney-client privilege**.</span></span>

   <span data-ttu-id="ec943-153">将显示名为 **"律师-客户特权"的** 标记组。</span><span class="sxs-lookup"><span data-stu-id="ec943-153">A tag group named **Attorney-client privilege** is displayed.</span></span> <span data-ttu-id="ec943-154">它包含名为 **Positive** 和 **Negative** 的两个子标记，它们对应于模型生成的可能结果。</span><span class="sxs-lookup"><span data-stu-id="ec943-154">It contains two child tags named **Positive** and **Negative**, which correspond to the possible results produced by the model.</span></span>

   ![律师-客户特权智能标记组](../media/AeDAttorneyClientSmartTagGroup.png)

3. <span data-ttu-id="ec943-156">根据审阅情况重命名标记组和标记。</span><span class="sxs-lookup"><span data-stu-id="ec943-156">Rename the tag group and tags as appropriate for your review.</span></span> <span data-ttu-id="ec943-157">例如，可以将"正"**重命名** 为 **"特权**"，将 **"负**"重命名为"**非特权"。**</span><span class="sxs-lookup"><span data-stu-id="ec943-157">For example, you can rename **Positive** to **Privileged** and **Negative** to **Not privileged**.</span></span>

### <a name="step-2-analyze-a-review-set"></a><span data-ttu-id="ec943-158">步骤 2：分析审阅集</span><span class="sxs-lookup"><span data-stu-id="ec943-158">Step 2: Analyze a review set</span></span>

<span data-ttu-id="ec943-159">在分析审阅集内的文档时，律师-客户特权检测模型也将运行，并且将 (如何工作 [？](#how-does-it-work) 中所述的相应属性添加到审阅集内的所有文档。</span><span class="sxs-lookup"><span data-stu-id="ec943-159">When you analyze the documents in a review set, the attorney-client privilege detection model will also run and the corresponding properties (described in [How does it work?](#how-does-it-work) will be added to every document in the review set.</span></span> <span data-ttu-id="ec943-160">有关分析审阅集内的数据详细信息，请参阅在审阅集内分析[Advanced eDiscovery。](analyzing-data-in-review-set.md)</span><span class="sxs-lookup"><span data-stu-id="ec943-160">For more information about analyzing data in review set, see [Analyze data in a review set in Advanced eDiscovery](analyzing-data-in-review-set.md).</span></span>

### <a name="step-3-use-the-smart-tag-group-for-review-of-privileged-content"></a><span data-ttu-id="ec943-161">步骤 3：使用智能标记组查看特权内容</span><span class="sxs-lookup"><span data-stu-id="ec943-161">Step 3: Use the smart tag group for review of privileged content</span></span>

<span data-ttu-id="ec943-162">分析审阅集并设置智能标记后，下一步是查看文档。</span><span class="sxs-lookup"><span data-stu-id="ec943-162">After analyzing the review set and setting up smart tags, the next step is to review the documents.</span></span> <span data-ttu-id="ec943-163">如果模型已确定文档可能具有特权，则标记面板中的相应智能标记将指示律师-客户特权检测生成的以下结果：</span><span class="sxs-lookup"><span data-stu-id="ec943-163">If the model has determined the document is potentially privileged, the corresponding smart tag in the **Tagging panel** will indicate the following results produced by the attorney-client privilege detection:</span></span>

- <span data-ttu-id="ec943-164">如果文档的内容在本质上可能是合法内容，则标签"法律内容"显示在相应的智能标记 (在这种情况下，该智能标记是默认的 **"正**") 。</span><span class="sxs-lookup"><span data-stu-id="ec943-164">If the document has content that may be legal in nature, the label **Legal content** is displayed next to the corresponding smart tag (which in this case is the default **Positive** tag).</span></span>

- <span data-ttu-id="ec943-165">如果文档中有一个在组织律师列表中找到的参与者，则标签"律师"显示在相应的智能标记旁边 (该智能标记在此例中也是默认的 **"** 正") 。</span><span class="sxs-lookup"><span data-stu-id="ec943-165">If the document has a participant who is found in your organization's attorney list, the label **Attorney** is displayed next to the corresponding smart tag (which in this case is also the default **Positive** tag).</span></span>

- <span data-ttu-id="ec943-166">如果文档的内容在本质上可能是合法的，并且律师列表中有参与者，则同时显示法律内容和律师标签。  </span><span class="sxs-lookup"><span data-stu-id="ec943-166">If the document has content that may be legal in nature *and* has a participant found in the attorney list, both the **Legal content**  and **Attorney** labels are displayed.</span></span> 

<span data-ttu-id="ec943-167">如果模型确定文档不包含本质上是合法的内容或不包含律师列表中的参与者，则标记面板中不会显示任何标签。</span><span class="sxs-lookup"><span data-stu-id="ec943-167">If the model determines that a document doesn't contain content that is legal in nature or doesn't contain a participant from the attorney list, then neither label is displayed in the tagging panel.</span></span>

<span data-ttu-id="ec943-168">例如，以下屏幕截图显示了两个文档。</span><span class="sxs-lookup"><span data-stu-id="ec943-168">For example, the following screenshots show two documents.</span></span> <span data-ttu-id="ec943-169">第一个包含本质上是合法的内容，并且有一个参与者在律师列表中找到。</span><span class="sxs-lookup"><span data-stu-id="ec943-169">The first one contains content that is legal in nature and has a participant found in the list of attorneys.</span></span> <span data-ttu-id="ec943-170">第二个不包含任何标签，因此不显示任何标签。</span><span class="sxs-lookup"><span data-stu-id="ec943-170">The second contains neither and therefore doesn't display any labels.</span></span>

![包含律师和法律内容标签的文档](../media/AeDTaggingPanelLegalContentAttorney.png)

![不带任何标签的文档](../media/AeDTaggingPanelNegative.png)

<span data-ttu-id="ec943-173">在查看文档以查看文档是否包含特权内容后，可以使用相应的标记标记该文档。</span><span class="sxs-lookup"><span data-stu-id="ec943-173">After you review a document to see if it contains privileged content, you can tag the document with the appropriate tag.</span></span>
