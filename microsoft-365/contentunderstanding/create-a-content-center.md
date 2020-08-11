---
title: '创建内容中心 (预览) '
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 8/1/2020
audience: admin
ms.topic: article
ms.service: ''
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: 了解如何创建内容中心。
ms.openlocfilehash: 5332ffa195519aebd5ae8dd2c26d7d62fd9b3267
ms.sourcegitcommit: a3a5dc541b0c971608cc86ef480509c25a13ca60
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/10/2020
ms.locfileid: "46612746"
---
# <a name="create-a-content-center-preview"></a><span data-ttu-id="eb93a-103">创建内容中心 (预览) </span><span class="sxs-lookup"><span data-stu-id="eb93a-103">Create a content center (Preview)</span></span>

> [!Note] 
> <span data-ttu-id="eb93a-104">本文中的内容适用于 Project Cortex 私人预览。</span><span class="sxs-lookup"><span data-stu-id="eb93a-104">The content in this article is for Project Cortex Private Preview.</span></span> <span data-ttu-id="eb93a-105">了解[有关 Project Cortex 的详细信息](https://aka.ms/projectcortex)。</span><span class="sxs-lookup"><span data-stu-id="eb93a-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span></br>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CPSF]

</br>

<span data-ttu-id="eb93a-106">若要创建和管理文档理解模型，首先需要一个内容中心。</span><span class="sxs-lookup"><span data-stu-id="eb93a-106">To create and manage document understanding models, you first need a content center.</span></span> <span data-ttu-id="eb93a-107">内容中心是模型创建界面，还包含有关已应用了已发布模型的文档库的信息。</span><span class="sxs-lookup"><span data-stu-id="eb93a-107">The content center is the model creation interface and also contains information about which document libraries published models have been applied.</span></span></br>

   ![选择文档库](../media/content-understanding/content-center-page.png)</br>

<span data-ttu-id="eb93a-109">初始内容中心是在[安装](set-up-content-understanding.md)过程中创建的，但 SharePoint 管理员可以根据需要选择创建其他内容中心。</span><span class="sxs-lookup"><span data-stu-id="eb93a-109">An initial content center is created during [setup](set-up-content-understanding.md), but a SharePoint admin can choose to create additional ones as needed.</span></span> <span data-ttu-id="eb93a-110">虽然单个内容中心对于要查看所有模型活动的汇总的环境可能很好，但如果您的组织中有多个部门可能对其模型有不同的需求和要求，则您可能需要其他客户端。</span><span class="sxs-lookup"><span data-stu-id="eb93a-110">While a single content center may be fine for environments in which you want to see a roll-up of all model activity, you may want to have additional ones if your have multiple departments within your organization that may have different needs and requirements for their models.</span></span>

<span data-ttu-id="eb93a-111">SharePoint 管理员可以创建内容中心网站，如他们通过网站模板[创建任何其他 SharePoint 网站](https://docs.microsoft.com/sharepoint/create-site-collection)。</span><span class="sxs-lookup"><span data-stu-id="eb93a-111">A SharePoint admin can create a content center site like they would [create any other SharePoint site](https://docs.microsoft.com/sharepoint/create-site-collection) - through a site template.</span></span>

<span data-ttu-id="eb93a-112">若要创建新的内容中心，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="eb93a-112">To create a new content center:</span></span>

1. <span data-ttu-id="eb93a-113">在 Microsoft 365 管理中心，转到 "SharePoint 管理中心"。</span><span class="sxs-lookup"><span data-stu-id="eb93a-113">On the Microsoft 365 admin center, go to the SharePoint admin center.</span></span>
2. <span data-ttu-id="eb93a-114">在 SharePoint 管理中心的 "**网站**" 下，选择 "**活动网站**"。</span><span class="sxs-lookup"><span data-stu-id="eb93a-114">On the SharePoint admin center, under **Sites**, select **Active Sites**.</span></span>
3. <span data-ttu-id="eb93a-115">在 "**活动网站**" 页上，单击 "**创建**"，然后选择 "**其他选项**"。</span><span class="sxs-lookup"><span data-stu-id="eb93a-115">On the **Active Sites** page, click **Create**, and then select **Other options**.</span></span>
4. <span data-ttu-id="eb93a-116">在 "**选择模板**" 菜单上，选择 "**内容中心**"。</span><span class="sxs-lookup"><span data-stu-id="eb93a-116">On the **Choose a template** menu, select **Content Center**.</span></span>
5. <span data-ttu-id="eb93a-117">对于新网站，提供**网站名称**、**主管理员**和一种**语言**。</span><span class="sxs-lookup"><span data-stu-id="eb93a-117">For the new site, provide a **Site Name**, **Primary administrator**, and a **Language**.</span></span></br>

> [!Note] 
> <span data-ttu-id="eb93a-118">您可以选择以任何可用语言呈现的内容中心网站，但请注意，当前的模型只能为英语文件创建。</span><span class="sxs-lookup"><span data-stu-id="eb93a-118">You can select a content center site to render in any of the available languages, but note that currently models can only be created for English files.</span></span></br>

6. <span data-ttu-id="eb93a-119">单击“完成”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="eb93a-119">Click **Finished**.</span></span>

### <a name="give-access-to-additional-users"></a><span data-ttu-id="eb93a-120">授予对其他用户的访问权限</span><span class="sxs-lookup"><span data-stu-id="eb93a-120">Give access to additional users</span></span>
 
<span data-ttu-id="eb93a-121">创建网站后，可以通过标准[SharePoint 网站权限模型](https://docs.microsoft.com/sharepoint/modern-experience-sharing-permissions)向其他用户授予对网站的访问权限。</span><span class="sxs-lookup"><span data-stu-id="eb93a-121">After the site is created, you can give additional users access to the site through the standard [SharePoint site permissions model](https://docs.microsoft.com/sharepoint/modern-experience-sharing-permissions).</span></span>





## <a name="see-also"></a><span data-ttu-id="eb93a-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="eb93a-122">See Also</span></span>
[<span data-ttu-id="eb93a-123">创建类元</span><span class="sxs-lookup"><span data-stu-id="eb93a-123">Create a classifier</span></span>](create-a-classifier.md)</br>
[<span data-ttu-id="eb93a-124">创建提取程序</span><span class="sxs-lookup"><span data-stu-id="eb93a-124">Create an extractor</span></span>](create-an-extractor.md)</br>
<span data-ttu-id="eb93a-125">[创建内容中心](create-a-content-center.md) 
[文档理解概述](document-understanding-overview.md)</span><span class="sxs-lookup"><span data-stu-id="eb93a-125">[Create a content center](create-a-content-center.md)
[Document understanding overview](document-understanding-overview.md)</span></span></br>
[<span data-ttu-id="eb93a-126">创建表单处理模型</span><span class="sxs-lookup"><span data-stu-id="eb93a-126">Create a form processing model</span></span>](create-a-form-processing-model.md)</br>
[<span data-ttu-id="eb93a-127">应用模型</span><span class="sxs-lookup"><span data-stu-id="eb93a-127">Apply a model</span></span>](apply-a-model.md)    




