---
title: 开始使用敏感度标签
f1.keywords:
- CSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: 你是否已准备好实现敏感度标签以帮助保护组织的数据，但不确定从哪里开始？ 阅读一些可帮助你使用标签的实用指导。
ms.openlocfilehash: efb0d8401cca8fd0e8c2450a5d35788015f37dad
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42073171"
---
# <a name="get-started-with-sensitivity-labels"></a><span data-ttu-id="cda0e-104">开始使用敏感度标签</span><span class="sxs-lookup"><span data-stu-id="cda0e-104">Get started with sensitivity labels</span></span>

<span data-ttu-id="cda0e-105">如需了解什么是敏感度标签以及该标签如何帮助你保护组织数据，请参阅[了解敏感度标签](sensitivity-labels.md)。</span><span class="sxs-lookup"><span data-stu-id="cda0e-105">For information about what sensitivity labels are and how they can help you protect your organization's data, see [Learn about sensitivity labels](sensitivity-labels.md).</span></span>

<span data-ttu-id="cda0e-106">如果你有 [Azure 信息保护](https://docs.microsoft.com/azure/information-protection/what-is-information-protection)，请确定是否需要将标签迁移到统一标签平台，以及要使用哪一个标签客户端：</span><span class="sxs-lookup"><span data-stu-id="cda0e-106">If you have [Azure Information Protection](https://docs.microsoft.com/azure/information-protection/what-is-information-protection), determine whether you need to migrate labels to the unified labeling platform, and which labeling client to use:</span></span>
- [<span data-ttu-id="cda0e-107">如何确定我的租户是否在统一标签平台上？</span><span class="sxs-lookup"><span data-stu-id="cda0e-107">How can I determine if my tenant is on the unified labeling platform?</span></span>](https://docs.microsoft.com/azure/information-protection/faqs#how-can-i-determine-if-my-tenant-is-on-the-unified-labeling-platform)
- [<span data-ttu-id="cda0e-108">选择要用于 Windows 计算机的标签客户端</span><span class="sxs-lookup"><span data-stu-id="cda0e-108">Choose which labeling client to use for Windows computers</span></span>](https://docs.microsoft.com/azure/information-protection/rms-client/use-client#choose-which-labeling-client-to-use-for-windows-computers)

<span data-ttu-id="cda0e-109">如果已准备好使用敏感度标签来开始保护组织的数据：</span><span class="sxs-lookup"><span data-stu-id="cda0e-109">When you're ready to start protecting your organization's data by using sensitivity labels:</span></span>

1. <span data-ttu-id="cda0e-110">**创建应用程序。**</span><span class="sxs-lookup"><span data-stu-id="cda0e-110">**Create the labels.**</span></span> <span data-ttu-id="cda0e-111">根据组织的分类法为不同敏感度级别的内容创建和命名敏感度标签。</span><span class="sxs-lookup"><span data-stu-id="cda0e-111">Create and name your sensitivity labels according to your organization's classification taxonomy for different sensitivity levels of content.</span></span> <span data-ttu-id="cda0e-112">使用对用户有意义的常用名称或术语。</span><span class="sxs-lookup"><span data-stu-id="cda0e-112">Use common names or terms that make sense to your users.</span></span> <span data-ttu-id="cda0e-113">如果尚未建立分类，请考虑以“个人”、“公共”、“常规”、“机密”和“高度机密”等标签名称开头。</span><span class="sxs-lookup"><span data-stu-id="cda0e-113">If you don't already have an established taxonomy, consider starting with label names such as Personal, Public, General, Confidential, and Highly Confidential.</span></span> <span data-ttu-id="cda0e-114">可以使用子标签按类别对类似标签进行分组。</span><span class="sxs-lookup"><span data-stu-id="cda0e-114">You can then use sublabels to group similar labels by category.</span></span> <span data-ttu-id="cda0e-115">创建标签时，可使用工具提示文本帮助用户选择相应的标签。</span><span class="sxs-lookup"><span data-stu-id="cda0e-115">When you create a label, use the  tooltip text to help users select the appropriate label.</span></span>

2. <span data-ttu-id="cda0e-116">**定义每个标签的用途。**</span><span class="sxs-lookup"><span data-stu-id="cda0e-116">**Define what each label can do.**</span></span> <span data-ttu-id="cda0e-117">配置要与每个标签关联的保护设置。</span><span class="sxs-lookup"><span data-stu-id="cda0e-117">Configure the protection settings you want associated with each label.</span></span> <span data-ttu-id="cda0e-118">例如，你可能希望较低灵敏度的内容（例如“常规”标签）仅应用页眉或页脚，而较高灵敏度的内容（例如“机密”标签）应该应用水印、加密和端点保护。</span><span class="sxs-lookup"><span data-stu-id="cda0e-118">For example, you might want lower sensitivity content (such as a “General” label) to have just a header or footer applied, while higher sensitivity content (such as a “Confidential” label) should have a watermark, encryption, and endpoint protection applied.</span></span>

3. <span data-ttu-id="cda0e-119">**发布标签。**</span><span class="sxs-lookup"><span data-stu-id="cda0e-119">**Publish the labels.**</span></span> <span data-ttu-id="cda0e-120">配置灵敏度标签后，使用标签策略发布它们。</span><span class="sxs-lookup"><span data-stu-id="cda0e-120">After your sensitivity labels are configured, publish them by using a label policy.</span></span> <span data-ttu-id="cda0e-121">确定应该应用标签的用户和组以及要使用的策略设置。</span><span class="sxs-lookup"><span data-stu-id="cda0e-121">Decide which users and groups should have the labels and what policy settings to use.</span></span> <span data-ttu-id="cda0e-122">单个标签可重用，可将其定义一次，然后可将其包含在分配给不同用户的多个标签策略中。</span><span class="sxs-lookup"><span data-stu-id="cda0e-122">A single label is reusable — you define it once, and then you can include it in several label policies assigned to different users.</span></span> <span data-ttu-id="cda0e-123">例如，可以通过将标签策略分配给少数用户来试用灵敏度标签。</span><span class="sxs-lookup"><span data-stu-id="cda0e-123">So for example, you could pilot your sensitivity labels by assigning a label policy to just a few users.</span></span> <span data-ttu-id="cda0e-124">然后，当你准备在整个组织中推广标签时，可以为标签创建新的标签策略，这次指定所有用户。</span><span class="sxs-lookup"><span data-stu-id="cda0e-124">Then when you're ready to roll out the labels across your organization, you can create a new label policy for your labels and this time, specify all users.</span></span>

<span data-ttu-id="cda0e-125">管理员，用户以及 Office 应用和服务使敏感度标签起作用的基本流程：</span><span class="sxs-lookup"><span data-stu-id="cda0e-125">The basic flow for what the admin, user, and Office apps and services do to make sensitivity labels work:</span></span>

![敏感度标签工作流关系图](../media/Sensitivity-label-flow.png)

## <a name="common-scenarios-for-sensitivity-labels"></a><span data-ttu-id="cda0e-127">敏感度标签的常见场景</span><span class="sxs-lookup"><span data-stu-id="cda0e-127">Common scenarios for sensitivity labels</span></span>

<span data-ttu-id="cda0e-128">使用以下文档支持敏感度标签部署：</span><span class="sxs-lookup"><span data-stu-id="cda0e-128">Use the following documentation to support your sensitivity labeling deployment:</span></span>

|<span data-ttu-id="cda0e-129">我想...</span><span class="sxs-lookup"><span data-stu-id="cda0e-129">I want to ...</span></span>|<span data-ttu-id="cda0e-130">文档</span><span class="sxs-lookup"><span data-stu-id="cda0e-130">Documentation</span></span>|
|----------------|---------------|
|<span data-ttu-id="cda0e-131">创建并发布有助于保护组织数据的敏感度标签</span><span class="sxs-lookup"><span data-stu-id="cda0e-131">Create and publish sensitivity labels that will help protect my organization's data</span></span>|[<span data-ttu-id="cda0e-132">创建和配置敏感度标签及其策略</span><span class="sxs-lookup"><span data-stu-id="cda0e-132">Create and configure sensitivity labels and their policies</span></span>](create-sensitivity-labels.md)|
|<span data-ttu-id="cda0e-133">使用敏感度标签加密文档和电子邮件，并限制可访问它的人员及其使用该内容的方式</span><span class="sxs-lookup"><span data-stu-id="cda0e-133">Encrypt documents and emails with sensitivity labels and restrict who can access it and how they can use that content</span></span> |[<span data-ttu-id="cda0e-134">通过敏感度标签应用加密，从而限制对内容的访问</span><span class="sxs-lookup"><span data-stu-id="cda0e-134">Restrict access to content by using sensitivity labels to apply encryption</span></span>](encryption-sensitivity-labels.md)|
|<span data-ttu-id="cda0e-135">为标记为加密的文档启用 SharePoint（和 OneDrive）中的协作功能</span><span class="sxs-lookup"><span data-stu-id="cda0e-135">Enable collaboration capabilities in SharePoint (and OneDrive) for documents that are labeled with encryption</span></span> | [<span data-ttu-id="cda0e-136">启用 SharePoint 和 OneDrive（公共预览版）中 Office 文件的敏感度标签</span><span class="sxs-lookup"><span data-stu-id="cda0e-136">Enable sensitivity labels for Office files in SharePoint and OneDrive (public preview)</span></span>](sensitivity-labels-sharepoint-onedrive-files.md)
|<span data-ttu-id="cda0e-137">管理 Office 应用的敏感度标签，以便在创建内容时对其进行标记</span><span class="sxs-lookup"><span data-stu-id="cda0e-137">Manage sensitivity labels for Office apps so that content is labeled as it's created</span></span> |[<span data-ttu-id="cda0e-138">在 Office 应用中使用敏感度标签</span><span class="sxs-lookup"><span data-stu-id="cda0e-138">Use sensitivity labels in Office apps</span></span>](sensitivity-labels-office-apps.md)|
|<span data-ttu-id="cda0e-139">创建内容时，自动对用户应用敏感度标签或建议标签</span><span class="sxs-lookup"><span data-stu-id="cda0e-139">Automatically apply sensitivity labels or recommend labels to users when content is created</span></span> | [<span data-ttu-id="cda0e-140">将敏感度标签自动应用于内容</span><span class="sxs-lookup"><span data-stu-id="cda0e-140">Apply a sensitivity label to content automatically</span></span>](apply-sensitivity-label-automatically.md)|
|<span data-ttu-id="cda0e-141">使用敏感度标签来保护 Teams和 SharePoint 中的内容</span><span class="sxs-lookup"><span data-stu-id="cda0e-141">Use sensitivity labels to protect content in Teams and  SharePoint</span></span> |[<span data-ttu-id="cda0e-142">将敏感度标签与 Microsoft Teams、Office 365 组和 SharePoint 网站（公共预览版）配合使用</span><span class="sxs-lookup"><span data-stu-id="cda0e-142">Use sensitivity labels with Microsoft Teams, Office 365 groups, and SharePoint sites (public preview)</span></span>](sensitivity-labels-teams-groups-sites.md)|
|<span data-ttu-id="cda0e-143">发现、标记和保护存储在本地数据存储中的文件</span><span class="sxs-lookup"><span data-stu-id="cda0e-143">Discover, label, and protect files stored in on-premises data stores</span></span> |[<span data-ttu-id="cda0e-144">部署 Azure 信息保护扫描程序以自动分类和保护文件</span><span class="sxs-lookup"><span data-stu-id="cda0e-144">Deploying the Azure Information Protection scanner to automatically classify and protect files</span></span>](https://docs.microsoft.com/azure/information-protection/deploy-aip-scanner)|
|<span data-ttu-id="cda0e-145">发现、标记和保护存储在云数据存储中的文件</span><span class="sxs-lookup"><span data-stu-id="cda0e-145">Discover, label, and protect files stored in cloud data stores</span></span> |[<span data-ttu-id="cda0e-146">发现、分类、标记和保护存储在云中的管控和敏感数据</span><span class="sxs-lookup"><span data-stu-id="cda0e-146">Discover, classify, label, and protect regulated and sensitive data stored in the cloud</span></span>](https://docs.microsoft.com/cloud-app-security/best-practices#discover-classify-label-and-protect-regulated-and-sensitive-data-stored-in-the-cloud)|
|<span data-ttu-id="cda0e-147">直观地显示敏感度标签的使用情况，以报告部署状态和精细调整标签配置</span><span class="sxs-lookup"><span data-stu-id="cda0e-147">Visualize how sensitivity labels are being used to report deployment status and fine-tune label configuration</span></span>|[<span data-ttu-id="cda0e-148">使用标签分析查看标签使用情况</span><span class="sxs-lookup"><span data-stu-id="cda0e-148">View label usage with label analytics</span></span>](label-analytics.md)|


## <a name="end-user-documentation-for-sensitivity-labels"></a><span data-ttu-id="cda0e-149">敏感度标签的最终用户文档</span><span class="sxs-lookup"><span data-stu-id="cda0e-149">End-user documentation for sensitivity labels</span></span>

- [<span data-ttu-id="cda0e-150">将敏感度标签应用到 Office 中的文件和电子邮件</span><span class="sxs-lookup"><span data-stu-id="cda0e-150">Apply sensitivity labels to your files and email in Office</span></span>](https://support.office.com/article/apply-sensitivity-labels-to-your-files-and-email-in-office-2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)

- [<span data-ttu-id="cda0e-151">Office 中敏感度标签的已知问题</span><span class="sxs-lookup"><span data-stu-id="cda0e-151">Known issues with sensitivity labels in Office</span></span>](https://support.office.com/en-us/article/known-issues-with-sensitivity-labels-in-office-b169d687-2bbd-4e21-a440-7da1b2743edc)

- [<span data-ttu-id="cda0e-152">向 Office 中的文件和电子邮件自动应用或建议敏感度标签</span><span class="sxs-lookup"><span data-stu-id="cda0e-152">Automatically apply or recommend sensitivity labels to your files and emails in Office</span></span>](https://support.office.com/article/automatically-apply-or-recommend-sensitivity-labels-to-your-files-and-emails-in-office-622e0d9c-f38c-470a-bcdb-9e90b24d71a1)

- [<span data-ttu-id="cda0e-153">有关自动应用或建议敏感度标签的已知问题</span><span class="sxs-lookup"><span data-stu-id="cda0e-153">Known issues with automatically applying or recommending sensitivity labels</span></span>](https://support.office.com/article/known-issues-with-automatically-applying-or-recommending-sensitivity-labels-451698ae-311b-4d28-83aa-a839a66f6efc)


