---
title: 在 Microsoft SharePoint Syntex 中创建内容中心
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
localization_priority: Priority
description: 了解如何创建内容中心。
ms.openlocfilehash: 34ba45cd62214743e5a6784893e0f24e9815fdfb
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905820"
---
# <a name="create-a-content-center-in-microsoft-sharepoint-syntex"></a><span data-ttu-id="d5da2-103">在 Microsoft SharePoint Syntex 中创建内容中心</span><span class="sxs-lookup"><span data-stu-id="d5da2-103">Create a content center in Microsoft SharePoint Syntex</span></span>


</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CPSF]

</br>

<span data-ttu-id="d5da2-104">要创建和管理文档理解模型，首先需要内容中心。</span><span class="sxs-lookup"><span data-stu-id="d5da2-104">To create and manage document understanding models, you first need a content center.</span></span> <span data-ttu-id="d5da2-105">内容中心是模型创建界面，它还包含已应用文档库发布模型的相关信息。</span><span class="sxs-lookup"><span data-stu-id="d5da2-105">The content center is the model creation interface and also contains information about which document libraries published models have been applied to.</span></span></br>

   ![选择文档库](../media/content-understanding/content-center-page.png)</br>

<span data-ttu-id="d5da2-107">[设置](set-up-content-understanding.md)期间创建默认内容中心。</span><span class="sxs-lookup"><span data-stu-id="d5da2-107">You create a default content center during [setup](set-up-content-understanding.md).</span></span> <span data-ttu-id="d5da2-108">但 SharePoint 管理员也可根据需要选择创建其他中心。</span><span class="sxs-lookup"><span data-stu-id="d5da2-108">But a SharePoint admin can also choose to create additional centers as needed.</span></span> <span data-ttu-id="d5da2-109">虽然单个内容中心对于你想汇总所有模型活动的环境可能不错，但你可能希望组织中多个部门有其他中心，这可能对其模型有不同需求和权限要求。</span><span class="sxs-lookup"><span data-stu-id="d5da2-109">While a single content center may be fine for environments for which you want a roll-up of all model activity, you may want to have additional centers for multiple departments within your organization, which may have different needs and permission requirements for their models.</span></span>

> [!NOTE]
> <span data-ttu-id="d5da2-110">在 [Microsoft 365 多地理环境](../enterprise/microsoft-365-multi-geo.md)中，如果中心位置中具有一个默认内容中心，则只能提供该位置内的模型活动汇总。</span><span class="sxs-lookup"><span data-stu-id="d5da2-110">In a [Microsoft 365 Multi-Geo environment](../enterprise/microsoft-365-multi-geo.md), if you have a single default content center in your central location, you can only provide a roll-up of model activity from within that location.</span></span> <span data-ttu-id="d5da2-111">当前无法在多地理环境中跨服务器场边界汇总模型活动。</span><span class="sxs-lookup"><span data-stu-id="d5da2-111">You currently cannot get a roll-up of model activity across farm-boundaries in Multi-Geo environment.</span></span> 


## <a name="create-a-content-center"></a><span data-ttu-id="d5da2-112">创建内容中心</span><span class="sxs-lookup"><span data-stu-id="d5da2-112">Create a content center</span></span>

<span data-ttu-id="d5da2-113">SharePoint 管理员可以创建内容中心网站，就像通过管理中心网站预配面板 [创建任何其他 SharePoint 网站](/sharepoint/create-site-collection) 一样。</span><span class="sxs-lookup"><span data-stu-id="d5da2-113">A SharePoint admin can create a content center site like they would [create any other SharePoint site](/sharepoint/create-site-collection) through the admin center site provisioning panel.</span></span>

<span data-ttu-id="d5da2-114">创建新的内容中心：</span><span class="sxs-lookup"><span data-stu-id="d5da2-114">To create a new content center:</span></span>

1. <span data-ttu-id="d5da2-115">在 Microsoft 365 管理中心，转到 SharePoint 管理中心。</span><span class="sxs-lookup"><span data-stu-id="d5da2-115">On the Microsoft 365 admin center, go to the SharePoint admin center.</span></span>

2. <span data-ttu-id="d5da2-116">在 SharePoint 管理中心的“**网站**”下，选择“**活动网站**”。</span><span class="sxs-lookup"><span data-stu-id="d5da2-116">On the SharePoint admin center, under **Sites**, select **Active Sites**.</span></span>

3. <span data-ttu-id="d5da2-117">在“**活动网站**”页面上，单击“**创建**”，然后选择“**其他选项**”。</span><span class="sxs-lookup"><span data-stu-id="d5da2-117">On the **Active Sites** page, click **Create**, and then select **Other options**.</span></span>

4. <span data-ttu-id="d5da2-118">在“**选择模板**”菜单上，选择“**内容中心**”。</span><span class="sxs-lookup"><span data-stu-id="d5da2-118">On the **Choose a template** menu, select **Content Center**.</span></span>

5. <span data-ttu-id="d5da2-119">对于新网站，提供 **网站名称**、**主管理员** 和 **语言**。</span><span class="sxs-lookup"><span data-stu-id="d5da2-119">For the new site, provide a **Site Name**, **Primary administrator**, and a **Language**.</span></span></br>

   > [!NOTE] 
   > <span data-ttu-id="d5da2-120">可选择一个内容中心网站呈现任意可用语言，但请注意，当前模型仅可为英语文件创建。</span><span class="sxs-lookup"><span data-stu-id="d5da2-120">You can select a content center site to render in any of the available languages, but note that currently models can only be created for English files.</span></span> <span data-ttu-id="d5da2-121">另请注意，与其他网站模板一样，网站创建后，默认网站语言不可编辑。</span><span class="sxs-lookup"><span data-stu-id="d5da2-121">Also note that like other site templates, the default site language isn't editable after the site is created.</span></span></br>

6. <span data-ttu-id="d5da2-122">选择“**已完成**”。</span><span class="sxs-lookup"><span data-stu-id="d5da2-122">Select **Finished**.</span></span>
 
<span data-ttu-id="d5da2-123">创建内容中心网站后，将看到它在 SharePoint 管理中心的“**活动网站**”页面上列出。</span><span class="sxs-lookup"><span data-stu-id="d5da2-123">After you create a content center site, you will see it listed on the **Active sites** page in the SharePoint admin center.</span></span> 

### <a name="give-access-to-additional-users"></a><span data-ttu-id="d5da2-124">授予其他用户访问权限</span><span class="sxs-lookup"><span data-stu-id="d5da2-124">Give access to additional users</span></span>
 
<span data-ttu-id="d5da2-125">创建网站后，可通过标准的 [SharePoint 网站权限模型](/sharepoint/modern-experience-sharing-permissions)授予其他用户网站访问权限。</span><span class="sxs-lookup"><span data-stu-id="d5da2-125">After you create the site, you can give additional users access to the site through the standard [SharePoint site permissions model](/sharepoint/modern-experience-sharing-permissions).</span></span>

## <a name="see-also"></a><span data-ttu-id="d5da2-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d5da2-126">See Also</span></span>
[<span data-ttu-id="d5da2-127">创建分类器</span><span class="sxs-lookup"><span data-stu-id="d5da2-127">Create a classifier</span></span>](create-a-classifier.md)

[<span data-ttu-id="d5da2-128">创建提取程序</span><span class="sxs-lookup"><span data-stu-id="d5da2-128">Create an extractor</span></span>](create-an-extractor.md)

[<span data-ttu-id="d5da2-129">创建内容中心</span><span class="sxs-lookup"><span data-stu-id="d5da2-129">Create a content center</span></span>](create-a-content-center.md)

[<span data-ttu-id="d5da2-130">文档理解概述</span><span class="sxs-lookup"><span data-stu-id="d5da2-130">Document understanding overview</span></span>](document-understanding-overview.md)

[<span data-ttu-id="d5da2-131">创建表单处理模型</span><span class="sxs-lookup"><span data-stu-id="d5da2-131">Create a form processing model</span></span>](create-a-form-processing-model.md)

[<span data-ttu-id="d5da2-132">应用模型</span><span class="sxs-lookup"><span data-stu-id="d5da2-132">Apply a model</span></span>](apply-a-model.md)