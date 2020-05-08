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
description: 已准备好实现敏感度标签以帮助保护组织的数据，但不确定从哪里开始？ 请阅读一些可帮助你使用标签的实用指导。
ms.openlocfilehash: f024995f63af19efa410cdb02a1f8c8d110902eb
ms.sourcegitcommit: 7ff75a0f45371b247d975fc61cfa286f5b6f42f6
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2020
ms.locfileid: "44140988"
---
# <a name="get-started-with-sensitivity-labels"></a><span data-ttu-id="98d40-104">开始使用敏感度标签</span><span class="sxs-lookup"><span data-stu-id="98d40-104">Get started with sensitivity labels</span></span>

><span data-ttu-id="98d40-105">*[Microsoft 365 安全性与合规性许可指南](https://aka.ms/ComplianceSD)。*</span><span class="sxs-lookup"><span data-stu-id="98d40-105">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="98d40-106">如需了解什么是敏感度标签以及该标签如何帮助你保护组织数据，请参阅[了解敏感度标签](sensitivity-labels.md)。</span><span class="sxs-lookup"><span data-stu-id="98d40-106">For information about what sensitivity labels are and how they can help you protect your organization's data, see [Learn about sensitivity labels](sensitivity-labels.md).</span></span>

<span data-ttu-id="98d40-107">如果你有 [Azure 信息保护](https://docs.microsoft.com/azure/information-protection/what-is-information-protection)，请确定是否需要将标签迁移到统一标签平台，以及要使用哪一个标签客户端：</span><span class="sxs-lookup"><span data-stu-id="98d40-107">If you have [Azure Information Protection](https://docs.microsoft.com/azure/information-protection/what-is-information-protection), determine whether you need to migrate labels to the unified labeling platform, and which labeling client to use:</span></span>
- [<span data-ttu-id="98d40-108">如何确定我的租户是否在统一标签平台上？</span><span class="sxs-lookup"><span data-stu-id="98d40-108">How can I determine if my tenant is on the unified labeling platform?</span></span>](https://docs.microsoft.com/azure/information-protection/faqs#how-can-i-determine-if-my-tenant-is-on-the-unified-labeling-platform)
- [<span data-ttu-id="98d40-109">选择要用于 Windows 计算机的标签客户端</span><span class="sxs-lookup"><span data-stu-id="98d40-109">Choose which labeling client to use for Windows computers</span></span>](https://docs.microsoft.com/azure/information-protection/rms-client/use-client#choose-which-labeling-client-to-use-for-windows-computers)

<span data-ttu-id="98d40-110">如果已准备好使用敏感度标签来开始保护组织的数据：</span><span class="sxs-lookup"><span data-stu-id="98d40-110">When you're ready to start protecting your organization's data by using sensitivity labels:</span></span>

1. <span data-ttu-id="98d40-111">**创建应用程序。**</span><span class="sxs-lookup"><span data-stu-id="98d40-111">**Create the labels.**</span></span> <span data-ttu-id="98d40-112">根据组织的分类法为不同敏感度级别的内容创建和命名敏感度标签。</span><span class="sxs-lookup"><span data-stu-id="98d40-112">Create and name your sensitivity labels according to your organization's classification taxonomy for different sensitivity levels of content.</span></span> <span data-ttu-id="98d40-113">使用对用户有意义的常用名称或术语。</span><span class="sxs-lookup"><span data-stu-id="98d40-113">Use common names or terms that make sense to your users.</span></span> <span data-ttu-id="98d40-114">如果尚未建立分类，请考虑以“个人”、“公共”、“常规”、“机密”和“高度机密”等标签名称开头。</span><span class="sxs-lookup"><span data-stu-id="98d40-114">If you don't already have an established taxonomy, consider starting with label names such as Personal, Public, General, Confidential, and Highly Confidential.</span></span> <span data-ttu-id="98d40-115">可以使用子标签按类别对类似标签进行分组。</span><span class="sxs-lookup"><span data-stu-id="98d40-115">You can then use sublabels to group similar labels by category.</span></span> <span data-ttu-id="98d40-116">创建标签时，可使用工具提示文本帮助用户选择相应的标签。</span><span class="sxs-lookup"><span data-stu-id="98d40-116">When you create a label, use the  tooltip text to help users select the appropriate label.</span></span>
    
    <span data-ttu-id="98d40-117">有关定义分类法的更多深入指南，请从“[服务信任门户](https://aka.ms/DataClassificationWhitepaper)”下载白皮书“数据分类和敏感度标签分类”。</span><span class="sxs-lookup"><span data-stu-id="98d40-117">For more extensive guidance for defining a classificaton taxonomy, download the white paper, "Data Classification & Sensitivity Label Taxonomy" from the [Service Trust Portal](https://aka.ms/DataClassificationWhitepaper).</span></span>

2. <span data-ttu-id="98d40-118">**定义每个标签的用途。**</span><span class="sxs-lookup"><span data-stu-id="98d40-118">**Define what each label can do.**</span></span> <span data-ttu-id="98d40-119">配置要与每个标签关联的保护设置。</span><span class="sxs-lookup"><span data-stu-id="98d40-119">Configure the protection settings you want associated with each label.</span></span> <span data-ttu-id="98d40-120">例如，你可能希望较低灵敏度的内容（例如“常规”标签）仅应用页眉或页脚，而较高灵敏度的内容（例如“机密”标签）应该应用水印、加密和端点保护。</span><span class="sxs-lookup"><span data-stu-id="98d40-120">For example, you might want lower sensitivity content (such as a "General" label) to have just a header or footer applied, while higher sensitivity content (such as a "Confidential" label) should have a watermark, encryption, and endpoint protection applied.</span></span>

3. <span data-ttu-id="98d40-121">**发布标签。**</span><span class="sxs-lookup"><span data-stu-id="98d40-121">**Publish the labels.**</span></span> <span data-ttu-id="98d40-122">配置灵敏度标签后，使用标签策略发布它们。</span><span class="sxs-lookup"><span data-stu-id="98d40-122">After your sensitivity labels are configured, publish them by using a label policy.</span></span> <span data-ttu-id="98d40-123">确定应该应用标签的用户和组以及要使用的策略设置。</span><span class="sxs-lookup"><span data-stu-id="98d40-123">Decide which users and groups should have the labels and what policy settings to use.</span></span> <span data-ttu-id="98d40-124">单个标签可重用，可将其定义一次，然后可将其包含在分配给不同用户的多个标签策略中。</span><span class="sxs-lookup"><span data-stu-id="98d40-124">A single label is reusable — you define it once, and then you can include it in several label policies assigned to different users.</span></span> <span data-ttu-id="98d40-125">例如，可以通过将标签策略分配给少数用户来试用灵敏度标签。</span><span class="sxs-lookup"><span data-stu-id="98d40-125">So for example, you could pilot your sensitivity labels by assigning a label policy to just a few users.</span></span> <span data-ttu-id="98d40-126">然后，当你准备在整个组织中推广标签时，可以为标签创建新的标签策略，这次指定所有用户。</span><span class="sxs-lookup"><span data-stu-id="98d40-126">Then when you're ready to roll out the labels across your organization, you can create a new label policy for your labels and this time, specify all users.</span></span>

<span data-ttu-id="98d40-127">部署和应用敏感度标签的基本流程如下：</span><span class="sxs-lookup"><span data-stu-id="98d40-127">The basic flow for deploying and applying sensitivity labels:</span></span>

![敏感度标签工作流关系图](../media/Sensitivity-label-flow.png)

## <a name="subscription-and-licensing-requirements-for-sensitivity-labels"></a><span data-ttu-id="98d40-129">灵敏度标签的订阅和许可要求</span><span class="sxs-lookup"><span data-stu-id="98d40-129">Subscription and licensing requirements for sensitivity labels</span></span>

<span data-ttu-id="98d40-130">许多不同的订阅都支持灵敏度标签，并且用户的许可要求取决于你使用的功能。</span><span class="sxs-lookup"><span data-stu-id="98d40-130">A number of different subscriptions support sensitivity labels and the licensing requirements for users depend on the features you use.</span></span>

<span data-ttu-id="98d40-131">自 2020 年 4 月 1 日起，若要查看许可用户从 Microsoft 365 合规性功能中受益的选项，请参阅 [Microsoft 365 安全性与合规性许可指南](https://aka.ms/ComplianceSD)。</span><span class="sxs-lookup"><span data-stu-id="98d40-131">To see the options for licensing your users to benefit from Microsoft 365 compliance features as of April 1, 2020, see the [Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).</span></span> <span data-ttu-id="98d40-132">有关敏感度标签，请参阅[信息保护](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection)部分和相关 PDF 或 Excel 下载内容。</span><span class="sxs-lookup"><span data-stu-id="98d40-132">For sensitivity labels, see the [Information Protection](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection) section and related PDF or Excel download.</span></span>

## <a name="permissions-required-to-create-and-manage-sensitivity-labels"></a><span data-ttu-id="98d40-133">创建和管理敏感度标签所需的权限</span><span class="sxs-lookup"><span data-stu-id="98d40-133">Permissions required to create and manage sensitivity labels</span></span>

<span data-ttu-id="98d40-134">将要创建敏感度标签的合规团队成员需要 Microsoft 365 合规中心、Microsoft 365 安全中心或安全与合规中心的访问权限。</span><span class="sxs-lookup"><span data-stu-id="98d40-134">Members of your compliance team who will create sensitivity labels need permissions to the Microsoft 365 compliance center, Microsoft 365 security center, or the Security & Compliance Center.</span></span> 

<span data-ttu-id="98d40-135">默认情况下，你的租户的全局管理员有权访问这些管理中心，可向合规专员和其他人提供访问权限，而不为其提供租户管理员的所有权限。要获得这一委派的受限管理员访问权限，请转到其中一个管理中心的**权限**页面，然后将成员添加到**合规性数据管理员**、**合规性管理员**或**安全管理员**角色组。</span><span class="sxs-lookup"><span data-stu-id="98d40-135">By default, global administrators for your tenant have access to these admin centers and can give compliance officers and other people access, without giving them all of the permissions of a tenant admin. For this delegated limited admin access, go to the **Permissions** page of one of these admin centers, and then add members to the **Compliance Data Administrator**, **Compliance Administrator** or **Security Administrator** role group.</span></span>

<span data-ttu-id="98d40-136">如果不使用角色，可以创建新的角色组，然后将“**敏感度标签管理员**”或“**组织配置**”角色添加到此组。</span><span class="sxs-lookup"><span data-stu-id="98d40-136">Alternatively to using roles, you can create a new role group and add either **Sensitivity Label Administrator** or **Organization Configuration** roles to this group.</span></span> <span data-ttu-id="98d40-137">对于只读角色，请使用**敏感度标签阅读器**。</span><span class="sxs-lookup"><span data-stu-id="98d40-137">For a read-only role, use **Sensitivity Label Reader**.</span></span> <span data-ttu-id="98d40-138">有关说明，请参阅[向用户授予对 Office 365 安全与合规中心的访问权限](https://docs.microsoft.com/microsoft-365/security/office-365-security/grant-access-to-the-security-and-compliance-center)。</span><span class="sxs-lookup"><span data-stu-id="98d40-138">For instructions, see [Give users access to the Office 365 Security & Compliance Center](https://docs.microsoft.com/microsoft-365/security/office-365-security/grant-access-to-the-security-and-compliance-center).</span></span>

<span data-ttu-id="98d40-139">只有在创建和配置灵敏度标签及其标签策略时才需要这些权限。</span><span class="sxs-lookup"><span data-stu-id="98d40-139">These permissions are required only to create and configure sensitivity labels and their label policies.</span></span> <span data-ttu-id="98d40-140">在应用或服务中应用标这些签时不需要这些权限。</span><span class="sxs-lookup"><span data-stu-id="98d40-140">They are not required to apply the labels in apps or services.</span></span>

> [!NOTE]
> <span data-ttu-id="98d40-141">**敏感度标签阅读器**是一个新角色，最初仅支持 PowerShell 标签 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="98d40-141">**Sensitivity Label Reader** is a new role that initially supported just the PowerShell labeling cmdlets.</span></span> <span data-ttu-id="98d40-142">现在，将向租户推出管理员标签中心支持。</span><span class="sxs-lookup"><span data-stu-id="98d40-142">Support for the admin labeling centers is now rolling out to tenants.</span></span>

## <a name="common-scenarios-for-sensitivity-labels"></a><span data-ttu-id="98d40-143">敏感度标签的常见场景</span><span class="sxs-lookup"><span data-stu-id="98d40-143">Common scenarios for sensitivity labels</span></span>

<span data-ttu-id="98d40-144">使用以下文档支持敏感度标签部署：</span><span class="sxs-lookup"><span data-stu-id="98d40-144">Use the following documentation to support your sensitivity labeling deployment:</span></span>

|<span data-ttu-id="98d40-145">我想...</span><span class="sxs-lookup"><span data-stu-id="98d40-145">I want to ...</span></span>|<span data-ttu-id="98d40-146">文档</span><span class="sxs-lookup"><span data-stu-id="98d40-146">Documentation</span></span>|
|----------------|---------------|
|<span data-ttu-id="98d40-147">创建并发布有助于保护组织数据的敏感度标签</span><span class="sxs-lookup"><span data-stu-id="98d40-147">Create and publish sensitivity labels that will help protect my organization's data</span></span>|[<span data-ttu-id="98d40-148">创建和配置敏感度标签及其策略</span><span class="sxs-lookup"><span data-stu-id="98d40-148">Create and configure sensitivity labels and their policies</span></span>](create-sensitivity-labels.md)|
|<span data-ttu-id="98d40-149">使用敏感度标签加密文档和电子邮件，并限制谁可以访问该内容以及可以如何使用它</span><span class="sxs-lookup"><span data-stu-id="98d40-149">Encrypt documents and emails with sensitivity labels and restrict who can access that content and how it can be used</span></span> |[<span data-ttu-id="98d40-150">通过敏感度标签应用加密，从而限制对内容的访问</span><span class="sxs-lookup"><span data-stu-id="98d40-150">Restrict access to content by using sensitivity labels to apply encryption</span></span>](encryption-sensitivity-labels.md)|
|<span data-ttu-id="98d40-151">为标记为加密的文档启用 SharePoint（和 OneDrive）中的协作功能</span><span class="sxs-lookup"><span data-stu-id="98d40-151">Enable collaboration capabilities in SharePoint (and OneDrive) for documents that are labeled with encryption</span></span> | [<span data-ttu-id="98d40-152">启用 SharePoint 和 OneDrive 中 Office 文件的敏感度标签</span><span class="sxs-lookup"><span data-stu-id="98d40-152">Enable sensitivity labels for Office files in SharePoint and OneDrive</span></span>](sensitivity-labels-sharepoint-onedrive-files.md)
|<span data-ttu-id="98d40-153">管理 Office 应用的敏感度标签，以便在创建内容时对其进行标记</span><span class="sxs-lookup"><span data-stu-id="98d40-153">Manage sensitivity labels for Office apps so that content is labeled as it's created</span></span> |[<span data-ttu-id="98d40-154">在 Office 应用中使用敏感度标签</span><span class="sxs-lookup"><span data-stu-id="98d40-154">Use sensitivity labels in Office apps</span></span>](sensitivity-labels-office-apps.md)|
|<span data-ttu-id="98d40-155">自动将敏感度标签应用于文档和电子邮件</span><span class="sxs-lookup"><span data-stu-id="98d40-155">Automatically apply sensitivity labels to documents and emails</span></span> | [<span data-ttu-id="98d40-156">将敏感度标签自动应用于内容</span><span class="sxs-lookup"><span data-stu-id="98d40-156">Apply a sensitivity label to content automatically</span></span>](apply-sensitivity-label-automatically.md)|
|<span data-ttu-id="98d40-157">使用敏感度标签来保护 Teams和 SharePoint 中的内容</span><span class="sxs-lookup"><span data-stu-id="98d40-157">Use sensitivity labels to protect content in Teams and  SharePoint</span></span> |[<span data-ttu-id="98d40-158">将敏感度标签与 Microsoft Teams、Microsoft 365 组和 SharePoint 网站（公共预览版）配合使用</span><span class="sxs-lookup"><span data-stu-id="98d40-158">Use sensitivity labels with Microsoft Teams, Microsoft 365 groups, and SharePoint sites (public preview)</span></span>](sensitivity-labels-teams-groups-sites.md)|
|<span data-ttu-id="98d40-159">发现、标记和保护本地数据存储中存储的文件</span><span class="sxs-lookup"><span data-stu-id="98d40-159">Discover, label, and protect files stored in data stores that are on premises</span></span> |[<span data-ttu-id="98d40-160">部署 Azure 信息保护扫描程序以自动分类和保护文件</span><span class="sxs-lookup"><span data-stu-id="98d40-160">Deploying the Azure Information Protection scanner to automatically classify and protect files</span></span>](https://docs.microsoft.com/azure/information-protection/deploy-aip-scanner)|
|<span data-ttu-id="98d40-161">发现、标记和保护云端数据存储中存储的文件</span><span class="sxs-lookup"><span data-stu-id="98d40-161">Discover, label, and protect files stored in data stores that are in the cloud</span></span>|[<span data-ttu-id="98d40-162">发现、分类、标记和保护存储在云中的管控和敏感数据</span><span class="sxs-lookup"><span data-stu-id="98d40-162">Discover, classify, label, and protect regulated and sensitive data stored in the cloud</span></span>](https://docs.microsoft.com/cloud-app-security/best-practices#discover-classify-label-and-protect-regulated-and-sensitive-data-stored-in-the-cloud)|
|<span data-ttu-id="98d40-163">在 Power BI 中应用和查看敏感性标签，并保护下载的报表</span><span class="sxs-lookup"><span data-stu-id="98d40-163">Apply and view sensitivity labels in Power BI, and protect reports that are downloaded</span></span>|[<span data-ttu-id="98d40-164">Power BI （预览版）中的数据保护</span><span class="sxs-lookup"><span data-stu-id="98d40-164">Data protection in Power BI (preview)</span></span>](https://docs.microsoft.com/power-bi/admin/service-security-data-protection-overview)|
|<span data-ttu-id="98d40-165">直观地显示敏感度标签的使用情况，以报告部署状态和精细调整标签配置</span><span class="sxs-lookup"><span data-stu-id="98d40-165">Visualize how sensitivity labels are being used to report deployment status and fine-tune label configuration</span></span>|[<span data-ttu-id="98d40-166">使用标签分析查看标签使用情况</span><span class="sxs-lookup"><span data-stu-id="98d40-166">View label usage with label analytics</span></span>](label-analytics.md)|


## <a name="end-user-documentation-for-sensitivity-labels"></a><span data-ttu-id="98d40-167">敏感度标签的最终用户文档</span><span class="sxs-lookup"><span data-stu-id="98d40-167">End-user documentation for sensitivity labels</span></span>

<span data-ttu-id="98d40-168">最有效的最终用户文档将用作你为所选标签名称和配置提供的定制指南和说明。</span><span class="sxs-lookup"><span data-stu-id="98d40-168">The most effective end-user documentation will be customized guidance and instructions you provide for the label names and configurations you choose.</span></span> <span data-ttu-id="98d40-169">但你可通过以下资源查看基本说明：</span><span class="sxs-lookup"><span data-stu-id="98d40-169">However, you can use the following resources for basic instructions:</span></span>   

- [<span data-ttu-id="98d40-170">将敏感度标签应用到 Office 中的文件和电子邮件</span><span class="sxs-lookup"><span data-stu-id="98d40-170">Apply sensitivity labels to your files and email in Office</span></span>](https://support.office.com/article/apply-sensitivity-labels-to-your-files-and-email-in-office-2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)
    - [<span data-ttu-id="98d40-171">Office 中敏感度标签的已知问题</span><span class="sxs-lookup"><span data-stu-id="98d40-171">Known issues with sensitivity labels in Office</span></span>](https://support.office.com/zh-CN/article/known-issues-with-sensitivity-labels-in-office-b169d687-2bbd-4e21-a440-7da1b2743edc)

- [<span data-ttu-id="98d40-172">向 Office 中的文件和电子邮件自动应用或建议敏感度标签</span><span class="sxs-lookup"><span data-stu-id="98d40-172">Automatically apply or recommend sensitivity labels to your files and emails in Office</span></span>](https://support.office.com/article/automatically-apply-or-recommend-sensitivity-labels-to-your-files-and-emails-in-office-622e0d9c-f38c-470a-bcdb-9e90b24d71a1)
    - [<span data-ttu-id="98d40-173">有关自动应用或建议敏感度标签的已知问题</span><span class="sxs-lookup"><span data-stu-id="98d40-173">Known issues with automatically applying or recommending sensitivity labels</span></span>](https://support.office.com/article/known-issues-with-automatically-applying-or-recommending-sensitivity-labels-451698ae-311b-4d28-83aa-a839a66f6efc)

- [<span data-ttu-id="98d40-174">Azure 信息保护统一标记用户指南</span><span class="sxs-lookup"><span data-stu-id="98d40-174">Azure Information Protection unified labeling user guide</span></span>](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-user-guide)


