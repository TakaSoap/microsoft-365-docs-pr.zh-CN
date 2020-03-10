---
title: 开始使用敏感度标签
f1.keywords:
- CSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: 3/05/2020
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
description: 已准备好实现敏感度标签以帮助保护组织的数据，但不确定从哪里开始？ 请阅读一些可帮助你使用标签的实用指导。
ms.openlocfilehash: 3e9dd5c02b3502eab2d3abfe5d65b5baebe18cda
ms.sourcegitcommit: cc3b64a91e16ccdaa9c338b9a9056dbe3963ba9e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/09/2020
ms.locfileid: "42569178"
---
# <a name="get-started-with-sensitivity-labels"></a><span data-ttu-id="aa063-104">开始使用敏感度标签</span><span class="sxs-lookup"><span data-stu-id="aa063-104">Get started with sensitivity labels</span></span>

<span data-ttu-id="aa063-105">如需了解什么是敏感度标签以及该标签如何帮助你保护组织数据，请参阅[了解敏感度标签](sensitivity-labels.md)。</span><span class="sxs-lookup"><span data-stu-id="aa063-105">For information about what sensitivity labels are and how they can help you protect your organization's data, see [Learn about sensitivity labels](sensitivity-labels.md).</span></span>

<span data-ttu-id="aa063-106">如果你有 [Azure 信息保护](https://docs.microsoft.com/azure/information-protection/what-is-information-protection)，请确定是否需要将标签迁移到统一标签平台，以及要使用哪一个标签客户端：</span><span class="sxs-lookup"><span data-stu-id="aa063-106">If you have [Azure Information Protection](https://docs.microsoft.com/azure/information-protection/what-is-information-protection), determine whether you need to migrate labels to the unified labeling platform, and which labeling client to use:</span></span>
- [<span data-ttu-id="aa063-107">如何确定我的租户是否在统一标签平台上？</span><span class="sxs-lookup"><span data-stu-id="aa063-107">How can I determine if my tenant is on the unified labeling platform?</span></span>](https://docs.microsoft.com/azure/information-protection/faqs#how-can-i-determine-if-my-tenant-is-on-the-unified-labeling-platform)
- [<span data-ttu-id="aa063-108">选择要用于 Windows 计算机的标签客户端</span><span class="sxs-lookup"><span data-stu-id="aa063-108">Choose which labeling client to use for Windows computers</span></span>](https://docs.microsoft.com/azure/information-protection/rms-client/use-client#choose-which-labeling-client-to-use-for-windows-computers)

<span data-ttu-id="aa063-109">如果已准备好使用敏感度标签来开始保护组织的数据：</span><span class="sxs-lookup"><span data-stu-id="aa063-109">When you're ready to start protecting your organization's data by using sensitivity labels:</span></span>

1. <span data-ttu-id="aa063-110">**创建应用程序。**</span><span class="sxs-lookup"><span data-stu-id="aa063-110">**Create the labels.**</span></span> <span data-ttu-id="aa063-111">根据组织的分类法为不同敏感度级别的内容创建和命名敏感度标签。</span><span class="sxs-lookup"><span data-stu-id="aa063-111">Create and name your sensitivity labels according to your organization's classification taxonomy for different sensitivity levels of content.</span></span> <span data-ttu-id="aa063-112">使用对用户有意义的常用名称或术语。</span><span class="sxs-lookup"><span data-stu-id="aa063-112">Use common names or terms that make sense to your users.</span></span> <span data-ttu-id="aa063-113">如果尚未建立分类，请考虑以“个人”、“公共”、“常规”、“机密”和“高度机密”等标签名称开头。</span><span class="sxs-lookup"><span data-stu-id="aa063-113">If you don't already have an established taxonomy, consider starting with label names such as Personal, Public, General, Confidential, and Highly Confidential.</span></span> <span data-ttu-id="aa063-114">可以使用子标签按类别对类似标签进行分组。</span><span class="sxs-lookup"><span data-stu-id="aa063-114">You can then use sublabels to group similar labels by category.</span></span> <span data-ttu-id="aa063-115">创建标签时，可使用工具提示文本帮助用户选择相应的标签。</span><span class="sxs-lookup"><span data-stu-id="aa063-115">When you create a label, use the  tooltip text to help users select the appropriate label.</span></span>
    
    <span data-ttu-id="aa063-116">有关定义分类法的更多深入指南，请从“[服务信任门户](https://aka.ms/DataClassificationWhitepaper)”下载白皮书“数据分类和敏感度标签分类”。</span><span class="sxs-lookup"><span data-stu-id="aa063-116">For more extensive guidance for defining a classificaton taxonomy, download the white paper, "Data Classification & Sensitivity Label Taxonomy" from the [Service Trust Portal](https://aka.ms/DataClassificationWhitepaper).</span></span>

2. <span data-ttu-id="aa063-117">**定义每个标签的用途。**</span><span class="sxs-lookup"><span data-stu-id="aa063-117">**Define what each label can do.**</span></span> <span data-ttu-id="aa063-118">配置要与每个标签关联的保护设置。</span><span class="sxs-lookup"><span data-stu-id="aa063-118">Configure the protection settings you want associated with each label.</span></span> <span data-ttu-id="aa063-119">例如，你可能希望较低灵敏度的内容（例如“常规”标签）仅应用页眉或页脚，而较高灵敏度的内容（例如“机密”标签）应该应用水印、加密和端点保护。</span><span class="sxs-lookup"><span data-stu-id="aa063-119">For example, you might want lower sensitivity content (such as a “General” label) to have just a header or footer applied, while higher sensitivity content (such as a “Confidential” label) should have a watermark, encryption, and endpoint protection applied.</span></span>

3. <span data-ttu-id="aa063-120">**发布标签。**</span><span class="sxs-lookup"><span data-stu-id="aa063-120">**Publish the labels.**</span></span> <span data-ttu-id="aa063-121">配置灵敏度标签后，使用标签策略发布它们。</span><span class="sxs-lookup"><span data-stu-id="aa063-121">After your sensitivity labels are configured, publish them by using a label policy.</span></span> <span data-ttu-id="aa063-122">确定应该应用标签的用户和组以及要使用的策略设置。</span><span class="sxs-lookup"><span data-stu-id="aa063-122">Decide which users and groups should have the labels and what policy settings to use.</span></span> <span data-ttu-id="aa063-123">单个标签可重用，可将其定义一次，然后可将其包含在分配给不同用户的多个标签策略中。</span><span class="sxs-lookup"><span data-stu-id="aa063-123">A single label is reusable — you define it once, and then you can include it in several label policies assigned to different users.</span></span> <span data-ttu-id="aa063-124">例如，可以通过将标签策略分配给少数用户来试用灵敏度标签。</span><span class="sxs-lookup"><span data-stu-id="aa063-124">So for example, you could pilot your sensitivity labels by assigning a label policy to just a few users.</span></span> <span data-ttu-id="aa063-125">然后，当你准备在整个组织中推广标签时，可以为标签创建新的标签策略，这次指定所有用户。</span><span class="sxs-lookup"><span data-stu-id="aa063-125">Then when you're ready to roll out the labels across your organization, you can create a new label policy for your labels and this time, specify all users.</span></span>

<span data-ttu-id="aa063-126">部署和应用敏感度标签的基本流程如下：</span><span class="sxs-lookup"><span data-stu-id="aa063-126">The basic flow for deploying and applying sensitivity labels:</span></span>

![敏感度标签工作流关系图](../media/Sensitivity-label-flow.png)

## <a name="permissions-required-to-create-and-manage-sensitivity-labels"></a><span data-ttu-id="aa063-128">创建和管理敏感度标签所需的权限</span><span class="sxs-lookup"><span data-stu-id="aa063-128">Permissions required to create and manage sensitivity labels</span></span>

<span data-ttu-id="aa063-129">将要创建敏感度标签的合规团队成员需要 Microsoft 365 合规中心、Microsoft 365 安全中心或 Office 365 安全与合规中心的访问权限。</span><span class="sxs-lookup"><span data-stu-id="aa063-129">Members of your compliance team who will create sensitivity labels need permissions to the Microsoft 365 compliance center, Microsoft 365 security center, or Office 365 Security & Compliance Center.</span></span> 

<span data-ttu-id="aa063-130">默认情况下，你的租户的全局管理员有权访问这些管理中心，可向合规专员和其他人提供访问权限，而不为其提供租户管理员的所有权限。要获得这一委派的受限管理员访问权限，请转到其中一个管理中心的**权限**页面，然后将成员添加到**合规性数据管理员**、**合规性管理员**或**安全管理员**角色组。</span><span class="sxs-lookup"><span data-stu-id="aa063-130">By default, global administrators for your tenant have access to these admin centers and can give compliance officers and other people access, without giving them all of the permissions of a tenant admin. For this delegated limited admin access, go to the **Permissions** page of one of these admin centers, and then add members to the **Compliance Data Administrator**, **Compliance Administrator** or **Security Administrator** role group.</span></span>

<span data-ttu-id="aa063-131">如果不使用角色，可以创建新的角色组，然后将“**敏感度标签管理员**”或“**组织配置**”角色添加到此组。</span><span class="sxs-lookup"><span data-stu-id="aa063-131">Alternatively to using roles, you can create a new role group and add either **Sensitivity Label Administrator** or **Organization Configuration** roles to this group.</span></span> <span data-ttu-id="aa063-132">有关说明，请参阅[向用户授予对 Office 365 安全与合规中心的访问权限](https://docs.microsoft.com/microsoft-365/security/office-365-security/grant-access-to-the-security-and-compliance-center)。</span><span class="sxs-lookup"><span data-stu-id="aa063-132">For instructions, see [Give users access to the Office 365 Security & Compliance Center](https://docs.microsoft.com/microsoft-365/security/office-365-security/grant-access-to-the-security-and-compliance-center).</span></span>

<span data-ttu-id="aa063-133">只有在创建和配置灵敏度标签及其标签策略时才需要这些权限。</span><span class="sxs-lookup"><span data-stu-id="aa063-133">These permissions are required only to create and configure sensitivity labels and their label policies.</span></span> <span data-ttu-id="aa063-134">在应用或服务中应用标这些签时不需要这些权限。</span><span class="sxs-lookup"><span data-stu-id="aa063-134">They are not required to apply the labels in apps or services.</span></span>

## <a name="common-scenarios-for-sensitivity-labels"></a><span data-ttu-id="aa063-135">敏感度标签的常见场景</span><span class="sxs-lookup"><span data-stu-id="aa063-135">Common scenarios for sensitivity labels</span></span>

<span data-ttu-id="aa063-136">使用以下文档支持敏感度标签部署：</span><span class="sxs-lookup"><span data-stu-id="aa063-136">Use the following documentation to support your sensitivity labeling deployment:</span></span>

|<span data-ttu-id="aa063-137">我想...</span><span class="sxs-lookup"><span data-stu-id="aa063-137">I want to ...</span></span>|<span data-ttu-id="aa063-138">文档</span><span class="sxs-lookup"><span data-stu-id="aa063-138">Documentation</span></span>|
|----------------|---------------|
|<span data-ttu-id="aa063-139">创建并发布有助于保护组织数据的敏感度标签</span><span class="sxs-lookup"><span data-stu-id="aa063-139">Create and publish sensitivity labels that will help protect my organization's data</span></span>|[<span data-ttu-id="aa063-140">创建和配置敏感度标签及其策略</span><span class="sxs-lookup"><span data-stu-id="aa063-140">Create and configure sensitivity labels and their policies</span></span>](create-sensitivity-labels.md)|
|<span data-ttu-id="aa063-141">使用敏感度标签加密文档和电子邮件，并限制谁可以访问该内容以及可以如何使用它</span><span class="sxs-lookup"><span data-stu-id="aa063-141">Encrypt documents and emails with sensitivity labels and restrict who can access that content and how it can be used</span></span> |[<span data-ttu-id="aa063-142">通过敏感度标签应用加密，从而限制对内容的访问</span><span class="sxs-lookup"><span data-stu-id="aa063-142">Restrict access to content by using sensitivity labels to apply encryption</span></span>](encryption-sensitivity-labels.md)|
|<span data-ttu-id="aa063-143">为标记为加密的文档启用 SharePoint（和 OneDrive）中的协作功能</span><span class="sxs-lookup"><span data-stu-id="aa063-143">Enable collaboration capabilities in SharePoint (and OneDrive) for documents that are labeled with encryption</span></span> | [<span data-ttu-id="aa063-144">启用 SharePoint 和 OneDrive（公共预览版）中 Office 文件的敏感度标签</span><span class="sxs-lookup"><span data-stu-id="aa063-144">Enable sensitivity labels for Office files in SharePoint and OneDrive (public preview)</span></span>](sensitivity-labels-sharepoint-onedrive-files.md)
|<span data-ttu-id="aa063-145">管理 Office 应用的敏感度标签，以便在创建内容时对其进行标记</span><span class="sxs-lookup"><span data-stu-id="aa063-145">Manage sensitivity labels for Office apps so that content is labeled as it's created</span></span> |[<span data-ttu-id="aa063-146">在 Office 应用中使用敏感度标签</span><span class="sxs-lookup"><span data-stu-id="aa063-146">Use sensitivity labels in Office apps</span></span>](sensitivity-labels-office-apps.md)|
|<span data-ttu-id="aa063-147">创建内容时，自动对用户应用敏感度标签或建议标签</span><span class="sxs-lookup"><span data-stu-id="aa063-147">Automatically apply sensitivity labels or recommend labels to users when content is created</span></span> | [<span data-ttu-id="aa063-148">将敏感度标签自动应用于内容</span><span class="sxs-lookup"><span data-stu-id="aa063-148">Apply a sensitivity label to content automatically</span></span>](apply-sensitivity-label-automatically.md)|
|<span data-ttu-id="aa063-149">使用敏感度标签来保护 Teams和 SharePoint 中的内容</span><span class="sxs-lookup"><span data-stu-id="aa063-149">Use sensitivity labels to protect content in Teams and  SharePoint</span></span> |[<span data-ttu-id="aa063-150">将敏感度标签与 Microsoft Teams、Office 365 组和 SharePoint 网站（公共预览版）配合使用</span><span class="sxs-lookup"><span data-stu-id="aa063-150">Use sensitivity labels with Microsoft Teams, Office 365 groups, and SharePoint sites (public preview)</span></span>](sensitivity-labels-teams-groups-sites.md)|
|<span data-ttu-id="aa063-151">发现、标记和保护本地数据存储中存储的文件</span><span class="sxs-lookup"><span data-stu-id="aa063-151">Discover, label, and protect files stored in data stores that are on premises</span></span> |[<span data-ttu-id="aa063-152">部署 Azure 信息保护扫描程序以自动分类和保护文件</span><span class="sxs-lookup"><span data-stu-id="aa063-152">Deploying the Azure Information Protection scanner to automatically classify and protect files</span></span>](https://docs.microsoft.com/azure/information-protection/deploy-aip-scanner)|
|<span data-ttu-id="aa063-153">发现、标记和保护云端数据存储中存储的文件</span><span class="sxs-lookup"><span data-stu-id="aa063-153">Discover, label, and protect files stored in data stores that are in the cloud</span></span>|[<span data-ttu-id="aa063-154">发现、分类、标记和保护存储在云中的管控和敏感数据</span><span class="sxs-lookup"><span data-stu-id="aa063-154">Discover, classify, label, and protect regulated and sensitive data stored in the cloud</span></span>](https://docs.microsoft.com/cloud-app-security/best-practices#discover-classify-label-and-protect-regulated-and-sensitive-data-stored-in-the-cloud)|
|<span data-ttu-id="aa063-155">直观地显示敏感度标签的使用情况，以报告部署状态和精细调整标签配置</span><span class="sxs-lookup"><span data-stu-id="aa063-155">Visualize how sensitivity labels are being used to report deployment status and fine-tune label configuration</span></span>|[<span data-ttu-id="aa063-156">使用标签分析查看标签使用情况</span><span class="sxs-lookup"><span data-stu-id="aa063-156">View label usage with label analytics</span></span>](label-analytics.md)|


## <a name="end-user-documentation-for-sensitivity-labels"></a><span data-ttu-id="aa063-157">敏感度标签的最终用户文档</span><span class="sxs-lookup"><span data-stu-id="aa063-157">End-user documentation for sensitivity labels</span></span>

<span data-ttu-id="aa063-158">最有效的最终用户文档将用作你为所选标签名称和配置提供的定制指南和说明。</span><span class="sxs-lookup"><span data-stu-id="aa063-158">The most effective end-user documentation will be customized guidance and instructions you provide for the label names and configurations you choose.</span></span> <span data-ttu-id="aa063-159">但你可通过以下资源查看基本说明：</span><span class="sxs-lookup"><span data-stu-id="aa063-159">However, you can use the following resources for basic instructions:</span></span>   

- [<span data-ttu-id="aa063-160">将敏感度标签应用到 Office 中的文件和电子邮件</span><span class="sxs-lookup"><span data-stu-id="aa063-160">Apply sensitivity labels to your files and email in Office</span></span>](https://support.office.com/article/apply-sensitivity-labels-to-your-files-and-email-in-office-2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)
    - [<span data-ttu-id="aa063-161">Office 中敏感度标签的已知问题</span><span class="sxs-lookup"><span data-stu-id="aa063-161">Known issues with sensitivity labels in Office</span></span>](https://support.office.com/en-us/article/known-issues-with-sensitivity-labels-in-office-b169d687-2bbd-4e21-a440-7da1b2743edc)

- [<span data-ttu-id="aa063-162">向 Office 中的文件和电子邮件自动应用或建议敏感度标签</span><span class="sxs-lookup"><span data-stu-id="aa063-162">Automatically apply or recommend sensitivity labels to your files and emails in Office</span></span>](https://support.office.com/article/automatically-apply-or-recommend-sensitivity-labels-to-your-files-and-emails-in-office-622e0d9c-f38c-470a-bcdb-9e90b24d71a1)
    - [<span data-ttu-id="aa063-163">有关自动应用或建议敏感度标签的已知问题</span><span class="sxs-lookup"><span data-stu-id="aa063-163">Known issues with automatically applying or recommending sensitivity labels</span></span>](https://support.office.com/article/known-issues-with-automatically-applying-or-recommending-sensitivity-labels-451698ae-311b-4d28-83aa-a839a66f6efc)

- [<span data-ttu-id="aa063-164">Azure 信息保护统一标记用户指南</span><span class="sxs-lookup"><span data-stu-id="aa063-164">Azure Information Protection unified labeling user guide</span></span>](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-user-guide)


