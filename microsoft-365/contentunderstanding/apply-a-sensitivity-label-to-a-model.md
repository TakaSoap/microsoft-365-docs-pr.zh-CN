---
title: 在 Microsoft SharePoint Syntex 中向模型应用保留标签
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: ssquires
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
localization_priority: Priority
description: 了解如何将敏感度标签应用于 SharePoint Syntex 中的模型。
ms.openlocfilehash: 799ab3fa0fcdc9af9d227428056d2cd7abeaf539
ms.sourcegitcommit: a05f61a291eb4595fa9313757a3815b7f217681d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2021
ms.locfileid: "52706688"
---
# <a name="apply-a-sensitivity-label-to-a-model-in-microsoft-sharepoint-syntex"></a><span data-ttu-id="5cb1e-103">在 Microsoft SharePoint Syntex 中向模型应用保留标签</span><span class="sxs-lookup"><span data-stu-id="5cb1e-103">Apply a sensitivity label to a model in Microsoft SharePoint Syntex</span></span>

<span data-ttu-id="5cb1e-104">可以轻松将 [敏感度标签](../compliance/sensitivity-labels.md) 应用于 Microsoft SharePoint Syntex 中的文档理解模型。</span><span class="sxs-lookup"><span data-stu-id="5cb1e-104">You can easily apply a [sensitivity label](../compliance/sensitivity-labels.md) to document understanding models in Microsoft SharePoint Syntex.</span></span> <span data-ttu-id="5cb1e-105">此功能尚不可用于表单处理模型。</span><span class="sxs-lookup"><span data-stu-id="5cb1e-105">This feature isn't available yet for form processing models.</span></span>

<span data-ttu-id="5cb1e-106">通过敏感度标签，可以将加密、共享和条件访问策略应用于模型所识别的文档。</span><span class="sxs-lookup"><span data-stu-id="5cb1e-106">Sensitivity labels let you apply encryption, sharing, and conditional access policies to the documents that your models identify.</span></span> <span data-ttu-id="5cb1e-107">例如，你希望模型不仅识别任何包含上传到文档库的银行账号或信用卡号码的财务文档，而且将 *加密* 敏感度标签应用于这些文档，以限制可以访问其内容的人员和其使用方式。</span><span class="sxs-lookup"><span data-stu-id="5cb1e-107">For example, you want your model to not only identify any financial documents that contain bank account numbers or credit card numbers that are uploaded to your document library, but also to apply an *Encryption* sensitivity label to them to restrict who can access that content and how it can be used.</span></span>

<span data-ttu-id="5cb1e-108">可以通过模型主页上的模型设置将预先存在的敏感度标签应用于模型。</span><span class="sxs-lookup"><span data-stu-id="5cb1e-108">You can apply a pre-existing sensitivity label to your model through your model settings on your model's home page.</span></span> <span data-ttu-id="5cb1e-109">标签必须已经发布，可以在模型设置中进行选择。</span><span class="sxs-lookup"><span data-stu-id="5cb1e-109">The label must already be published to be available for selection from model settings.</span></span>

> [!Important]
> <span data-ttu-id="5cb1e-110">对于可应用于内容理解模型的保留标签，需要 [在 Microsoft 365 合规中心中创建和发布](../business-video/create-sensitivity-labels.md)。</span><span class="sxs-lookup"><span data-stu-id="5cb1e-110">For sensitivity labels to be available to apply to your document understanding models, they need to be [created and published in the Microsoft 365 Compliance Center](../business-video/create-sensitivity-labels.md).</span></span>

## <a name="add-a-sensitivity-label-to-a-document-understanding-model"></a><span data-ttu-id="5cb1e-111">将敏感度标签添加到文档理解模型</span><span class="sxs-lookup"><span data-stu-id="5cb1e-111">Add a sensitivity label to a document understanding model</span></span>

1. <span data-ttu-id="5cb1e-112">从模型主页中，选择“**模型设置**”。</span><span class="sxs-lookup"><span data-stu-id="5cb1e-112">From the model home page, select **Model settings**.</span></span>

   ![带有突出显示模型设置选项的模型页面屏幕截图。](../media/content-understanding/sensitivity-model-settings.png)

2. <span data-ttu-id="5cb1e-114">在“**模型设置**”窗格中的“**合规性**”部分中，选择“**敏感度标签**”菜单，以查看可应用于模型的敏感度标签列表。</span><span class="sxs-lookup"><span data-stu-id="5cb1e-114">On **Model settings** pane, in the **Compliance** section, select the **Sensitivity label** menu to see a list of sensitivity labels that are available for you to apply to the model.</span></span>

   ![显示敏感度标签菜单的模型设置窗格屏幕截图。](../media/content-understanding/sensitivity-model-settings-pane.png) 

3. <span data-ttu-id="5cb1e-116">选择要应用于模型的敏感度标签，然后选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="5cb1e-116">Select the sensitivity label you want to apply to the model, and then select **Save**.</span></span>

<span data-ttu-id="5cb1e-117">将敏感度标签应用于模型后，可以将其应用于：</span><span class="sxs-lookup"><span data-stu-id="5cb1e-117">After you apply the sensitivity label to your model, you can apply it to a:</span></span>

- <span data-ttu-id="5cb1e-118">新文档库</span><span class="sxs-lookup"><span data-stu-id="5cb1e-118">New document library</span></span>
- <span data-ttu-id="5cb1e-119">已应用模型的文档库</span><span class="sxs-lookup"><span data-stu-id="5cb1e-119">Document library to which the model is already applied</span></span>
 
### <a name="apply-the-sensitivity-label-to-a-document-library-to-which-the-model-is-already-applied"></a><span data-ttu-id="5cb1e-120">将敏感度标签应用于已应用该标签模型的文档库</span><span class="sxs-lookup"><span data-stu-id="5cb1e-120">Apply the sensitivity label to a document library to which the model is already applied</span></span>

<span data-ttu-id="5cb1e-121">如果已将文档理解模型应用于文档库，则可执行以下操作来同步敏感度标签更新以将其应用于文档库：</span><span class="sxs-lookup"><span data-stu-id="5cb1e-121">If your document understanding model has already been applied to a document library, you can do the following to sync your sensitivity label update to apply it to the document library:</span></span>

1. <span data-ttu-id="5cb1e-122">在模型主页的“**带模型的库**”部分中，选择要应用敏感度标签更新的文档库。</span><span class="sxs-lookup"><span data-stu-id="5cb1e-122">On the model home page, in the **Libraries with this model** section, select the document library to which you want to apply the sensitivity label update.</span></span>

2. <span data-ttu-id="5cb1e-123">选择“**同步**”。</span><span class="sxs-lookup"><span data-stu-id="5cb1e-123">Select **Sync**.</span></span>

   ![带有此模型部分，且同步突出显示的库的屏幕截图。](../media/content-understanding/sensitivity-libraries-sync.png)

<span data-ttu-id="5cb1e-125">应用更新并将其同步到模型后，可通过执行以下步骤来确认此更新已应用：</span><span class="sxs-lookup"><span data-stu-id="5cb1e-125">After you apply the update and sync it to your model, you can confirm that it has been applied by doing the following steps:</span></span>

1. <span data-ttu-id="5cb1e-126">在内容中心的“**带模型的库**”部分中，单击应用了已更新模型的库。</span><span class="sxs-lookup"><span data-stu-id="5cb1e-126">In the content center, in the **Libraries with this model** section, select the library to which your updated model was applied.</span></span> 

2. <span data-ttu-id="5cb1e-127">在文档库视图中，选择“信息”图标以查看模型属性。</span><span class="sxs-lookup"><span data-stu-id="5cb1e-127">In your document library view, select the information icon to check the model properties.</span></span>

3. <span data-ttu-id="5cb1e-128">在 **活动模型** 列表中，选择已更新模型。</span><span class="sxs-lookup"><span data-stu-id="5cb1e-128">In the **Active models** list, select your updated model.</span></span>

4. <span data-ttu-id="5cb1e-129">在“**敏感度标签**”部分中，将看到已应用的敏感度标签的名称。</span><span class="sxs-lookup"><span data-stu-id="5cb1e-129">In the **Sensitivity label** section, you'll see the name of the applied sensitivity label.</span></span>

<span data-ttu-id="5cb1e-130">在文档库中模型视图页面上，将显示新的“**敏感度标签**”列。</span><span class="sxs-lookup"><span data-stu-id="5cb1e-130">On your model's view page in your document library, a new **Sensitivity label** column will display.</span></span> <span data-ttu-id="5cb1e-131">当模型对其标识为属于其内容类型的文件进行分类并将文件在库视图中列出时，**敏感度标签** 列也将显示通过模型对其应用的敏感度标签名称。</span><span class="sxs-lookup"><span data-stu-id="5cb1e-131">As your model classifies files it identifies as belonging to its content type and lists them in the library view, the **Sensitivity label** column will also display the name of the sensitivity label that has been applied to it through the model.</span></span>

<span data-ttu-id="5cb1e-132">例如，模型识别的所有财务文档也将具有应用于它们的 *加密* 敏感度标签，防止未授权人员对其进行访问。</span><span class="sxs-lookup"><span data-stu-id="5cb1e-132">For example, all financial documents that your model identifies also will have the *Encryption* sensitivity label applied to them, preventing them from being accessed by unauthorized people.</span></span> <span data-ttu-id="5cb1e-133">如果未授权人员尝试从文档库中访问文件，将显示一条错误消息，提示由于应用了敏感度标签，不允许访问文件。</span><span class="sxs-lookup"><span data-stu-id="5cb1e-133">If an attempt is made to access the file from the document library by an unauthorized person, an error will display saying it isn't allowed because of the applied sensitivity label.</span></span>

<!---
## Add a sensitivity label to a form processing model

> [!Important]
> For sensitivity labels to be available to apply to your form processing model, they need to be [created and published in the Microsoft 365 Compliance Center](../business-video/create-sensitivity-labels.md).

You can either apply a sensitivity label to a form processing model when you are creating a model, or apply it to an existing model.

### Add a sensitivity label when you create a form processing model

1. When you [create a new form processing model](create-a-form-processing-model.md), select **Advanced settings**.

2. In **Advanced settings**, in the **Sensitivity label** section, select the menu and then select the sensitivity label you want to apply to the model.

3.  After you've completed your remaining model settings, select **Create** to build your model.

### Add a sensitivity label to an existing form processing model

You can add a sensitivity label to an existing form processing model in different ways:

- Through the **Automate** menu in the document library
- Through the **Active model** settings in the document library 

#### Add a sensitivity label to an existing form processing model through the Automate menu

You can add a sensitivity label to an existing form processing model that you own through the **Automate** menu in the document library in which the model is applied.

1. In your document library to which the form processing model is applied, select the **Automate** menu, select **AI Builder**, and then select **View form processing model details**.

2. On the **Model details** pane, in the **Sensitivity label** section, select the sensitivity label you want to apply. Then select **Save**.

#### Add a sensitivity label to an existing form processing model in the active model settings

You can add a sensitivity label to an existing form processing model that you own through the **Active model** settings in the document library in which the model is applied.

1. In the SharePoint document library in which the model is applied, select the **View active models** icon, and then select **View active models**.

2. In **Active models**, select the form processing model to which you want to apply the sensitivity label.

3. On the **Model details** pane, in the **Sensitivity label** section, select the sensitivity label you want to apply. Then select **Save**.

   > [!NOTE]
   > You must be the model owner for the **Model settings** pane to be editable. 
--->

## <a name="see-also"></a><span data-ttu-id="5cb1e-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5cb1e-134">See also</span></span>

[<span data-ttu-id="5cb1e-135">应用保留标签</span><span class="sxs-lookup"><span data-stu-id="5cb1e-135">Apply a retention label</span></span>](apply-a-retention-label-to-a-model.md)

[<span data-ttu-id="5cb1e-136">创建分类器</span><span class="sxs-lookup"><span data-stu-id="5cb1e-136">Create a classifier</span></span>](create-a-classifier.md)

[<span data-ttu-id="5cb1e-137">创建提取程序</span><span class="sxs-lookup"><span data-stu-id="5cb1e-137">Create an extractor</span></span>](create-an-extractor.md)

[<span data-ttu-id="5cb1e-138">文档理解概述</span><span class="sxs-lookup"><span data-stu-id="5cb1e-138">Document Understanding overview</span></span>](document-understanding-overview.md)