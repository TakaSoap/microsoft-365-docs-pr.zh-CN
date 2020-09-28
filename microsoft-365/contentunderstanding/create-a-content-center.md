---
title: 在 Microsoft SharePoint Syntex 中创建内容中心
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 8/1/2020
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: 了解如何创建内容中心。
ms.openlocfilehash: 62977bc5a34b041e9e958ff46e0dbc010d6bd822
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/28/2020
ms.locfileid: "48295428"
---
# <a name="create-a-content-center-in-microsoft-sharepoint-syntex"></a><span data-ttu-id="b518b-103">在 Microsoft SharePoint Syntex 中创建内容中心</span><span class="sxs-lookup"><span data-stu-id="b518b-103">Create a content center in Microsoft SharePoint Syntex</span></span>

<span data-ttu-id="b518b-104">本文中的内容适用于 Project Cortex 私人预览。</span><span class="sxs-lookup"><span data-stu-id="b518b-104">The content in this article is for the Project Cortex Private Preview.</span></span> <span data-ttu-id="b518b-105">了解[有关 Project Cortex 的详细信息](https://aka.ms/projectcortex)。</span><span class="sxs-lookup"><span data-stu-id="b518b-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span></br>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CPSF]

</br>

<span data-ttu-id="b518b-106">若要创建和管理文档理解模型，首先需要一个内容中心。</span><span class="sxs-lookup"><span data-stu-id="b518b-106">To create and manage document understanding models, you first need a content center.</span></span> <span data-ttu-id="b518b-107">内容中心是模型创建界面，还包含有关已应用了已发布模型的文档库的信息。</span><span class="sxs-lookup"><span data-stu-id="b518b-107">The content center is the model creation interface and also contains information about which document libraries published models have been applied to.</span></span></br>

   ![选择文档库](../media/content-understanding/content-center-page.png)</br>

<span data-ttu-id="b518b-109">在 [安装](set-up-content-understanding.md)过程中创建初始内容中心。</span><span class="sxs-lookup"><span data-stu-id="b518b-109">You create an initial content center during [setup](set-up-content-understanding.md).</span></span> <span data-ttu-id="b518b-110">但 SharePoint 管理员也可以根据需要选择创建其他中心。</span><span class="sxs-lookup"><span data-stu-id="b518b-110">But a SharePoint admin can also choose to create additional centers as needed.</span></span> <span data-ttu-id="b518b-111">虽然单个内容中心对于您希望汇总所有模型活动的环境可能很好，但您可能希望为组织中的多个部门添加其他中心，这可能对其模型有不同的需求和要求。</span><span class="sxs-lookup"><span data-stu-id="b518b-111">While a single content center may be fine for environments for which you want a roll-up of all model activity, you may want to have additional centers for multiple departments within your organization, which may have different needs and requirements for their models.</span></span>

> [!NOTE]
> <span data-ttu-id="b518b-112">SharePoint 管理员可以创建内容中心网站，如他们将使用网站模板 [创建任何其他 SharePoint 网站](https://docs.microsoft.com/sharepoint/create-site-collection) 。</span><span class="sxs-lookup"><span data-stu-id="b518b-112">A SharePoint admin can create a content center site like they would [create any other SharePoint site](https://docs.microsoft.com/sharepoint/create-site-collection) by using a site template.</span></span>

<span data-ttu-id="b518b-113">若要创建新的内容中心，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="b518b-113">To create a new content center:</span></span>

1. <span data-ttu-id="b518b-114">在 Microsoft 365 管理中心，转到 "SharePoint 管理中心"。</span><span class="sxs-lookup"><span data-stu-id="b518b-114">From the Microsoft 365 admin center, go to the SharePoint admin center.</span></span>
2. <span data-ttu-id="b518b-115">在 SharePoint 管理中心中的 " **网站**" 下，选择 " **活动网站**"。</span><span class="sxs-lookup"><span data-stu-id="b518b-115">In the SharePoint admin center, under **Sites**, select **Active Sites**.</span></span>
3. <span data-ttu-id="b518b-116">在 " **活动网站** " 页上，单击 " **创建**"，然后选择 " **其他选项**"。</span><span class="sxs-lookup"><span data-stu-id="b518b-116">On the **Active Sites** page, click **Create**, and then select **Other options**.</span></span>
4. <span data-ttu-id="b518b-117">在 " **选择模板** " 菜单上，选择 " **内容中心**"。</span><span class="sxs-lookup"><span data-stu-id="b518b-117">On the **Choose a template** menu, select **Content Center**.</span></span>
5. <span data-ttu-id="b518b-118">对于新网站，提供 **网站名称**、 **主管理员**和一种 **语言**。</span><span class="sxs-lookup"><span data-stu-id="b518b-118">For the new site, provide a **Site Name**, **Primary administrator**, and a **Language**.</span></span></br>

> [!NOTE] 
> <span data-ttu-id="b518b-119">可以选择使用任意可用的语言呈现内容中心网站。</span><span class="sxs-lookup"><span data-stu-id="b518b-119">You can optionally select a content center site to render in any of the available languages.</span></span> <span data-ttu-id="b518b-120">仅可为英语文件创建当前模型。</span><span class="sxs-lookup"><span data-stu-id="b518b-120">Only current models can be created for English files.</span></span></br>

6. <span data-ttu-id="b518b-121">选择 " **完成**"。</span><span class="sxs-lookup"><span data-stu-id="b518b-121">Select **Finished**.</span></span>

### <a name="give-access-to-additional-users"></a><span data-ttu-id="b518b-122">授予对其他用户的访问权限</span><span class="sxs-lookup"><span data-stu-id="b518b-122">Give access to additional users</span></span>
 
<span data-ttu-id="b518b-123">创建网站后，可以通过标准 [SharePoint 网站权限模型](https://docs.microsoft.com/sharepoint/modern-experience-sharing-permissions)向其他用户授予对网站的访问权限。</span><span class="sxs-lookup"><span data-stu-id="b518b-123">After you create the site, you can give additional users access to the site through the standard [SharePoint site permissions model](https://docs.microsoft.com/sharepoint/modern-experience-sharing-permissions).</span></span>

## <a name="see-also"></a><span data-ttu-id="b518b-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b518b-124">See Also</span></span>
[<span data-ttu-id="b518b-125">创建类元</span><span class="sxs-lookup"><span data-stu-id="b518b-125">Create a classifier</span></span>](create-a-classifier.md)</br>
[<span data-ttu-id="b518b-126">创建提取程序</span><span class="sxs-lookup"><span data-stu-id="b518b-126">Create an extractor</span></span>](create-an-extractor.md)</br>
<span data-ttu-id="b518b-127">[创建内容中心](create-a-content-center.md) 
[文档理解概述](document-understanding-overview.md)</span><span class="sxs-lookup"><span data-stu-id="b518b-127">[Create a content center](create-a-content-center.md)
[Document understanding overview](document-understanding-overview.md)</span></span></br>
[<span data-ttu-id="b518b-128">创建表单处理模型</span><span class="sxs-lookup"><span data-stu-id="b518b-128">Create a form processing model</span></span>](create-a-form-processing-model.md)</br>
[<span data-ttu-id="b518b-129">应用模型</span><span class="sxs-lookup"><span data-stu-id="b518b-129">Apply a model</span></span>](apply-a-model.md)    
