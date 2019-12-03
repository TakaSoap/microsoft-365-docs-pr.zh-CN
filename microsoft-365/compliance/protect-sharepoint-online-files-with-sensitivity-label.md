---
title: 使用敏感度标签保护 SharePoint Online 文件
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/27/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- SPO_Content
ms.custom:
- Ent_Solutions
ms.assetid: 5b9c8e41-25d2-436d-89bb-9aecb9ec2b80
description: 摘要：应用 Azure 信息保护来保护高度机密的 SharePoint Online 团队网站中的文件。
ms.openlocfilehash: b5251d393249e9023f6f437cb3df6c074ebdf436
ms.sourcegitcommit: bf30a2314376f0b7d577741b97df017969737d11
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/27/2019
ms.locfileid: "39637710"
---
# <a name="protect-sharepoint-online-files-with-a-sensitivity-label"></a><span data-ttu-id="56567-103">使用敏感度标签保护 SharePoint Online 文件</span><span class="sxs-lookup"><span data-stu-id="56567-103">Protect SharePoint Online files with sensitivity labels</span></span>

<span data-ttu-id="56567-104">使用本文中的步骤配置 Office 365 敏感度标签，从而为文件提供加密和各种权限。</span><span class="sxs-lookup"><span data-stu-id="56567-104">Use the steps in this article to configure an Office 365 sensitivity label to provide encryption and permissions for files.</span></span> <span data-ttu-id="56567-105">你可以将这些文件添加到配置为高度机密保护的 SharePoint 库中。</span><span class="sxs-lookup"><span data-stu-id="56567-105">These files can be added to a SharePoint library configured for highly confidential protection.</span></span> <span data-ttu-id="56567-106">或者，也可以直接从网站打开文件，并应用相应标签。</span><span class="sxs-lookup"><span data-stu-id="56567-106">Or, you can open a file directly from the site and apply the label.</span></span> <span data-ttu-id="56567-107">加密和权限保护会一直跟随文件，即使从网站上下载下来也是如此。</span><span class="sxs-lookup"><span data-stu-id="56567-107">The encryption and permissions protection travels with a file even when it is downloaded from the site.</span></span> 

<span data-ttu-id="56567-p102">为 SharePoint 网站及其中文件配置高度机密保护的大型解决方案采用这些步骤。有关详细信息，请参阅[保护 SharePoint Online 网站和文件](https://docs.microsoft.com/microsoft-365/compliance/deploy-sharepoint-online-sites-for-three-tiers-of-protection)。</span><span class="sxs-lookup"><span data-stu-id="56567-p102">These steps are part of a larger solution for configuring highly confidential protection for SharePoint sites and the files within these sites. For more information, see [Secure SharePoint Online sites and files](https://docs.microsoft.com/microsoft-365/compliance/deploy-sharepoint-online-sites-for-three-tiers-of-protection).</span></span> 

<span data-ttu-id="56567-110">对于有些客户而言，不建议对 SharePoint Online 中的文件使用敏感度标签，但对于部分文件需要这种保护级别的客户，这提供了一种选择。</span><span class="sxs-lookup"><span data-stu-id="56567-110">Using Azure Information Protection for files in SharePoint Online is not recommended for all customers, but is an option for customers who need this level of protection for a subset of files.</span></span>

<span data-ttu-id="56567-111">关于此解决方案，请务必注意以下几点：</span><span class="sxs-lookup"><span data-stu-id="56567-111">Some important notes about this solution:</span></span>
- <span data-ttu-id="56567-112">将加密应用于 Office 365 中存储的文件时，该服务无法处理这些文件的内容。</span><span class="sxs-lookup"><span data-stu-id="56567-112">When Azure Information Protection encryption is applied to files stored in Office 365, the service cannot process the contents of these files.</span></span> <span data-ttu-id="56567-113">共同创作、电子数据展示、搜索、Delve 和其他协作功能将无法正常使用。</span><span class="sxs-lookup"><span data-stu-id="56567-113">Co-authoring, eDiscovery, search, Delve, and other collaborative features do not work.</span></span> <span data-ttu-id="56567-114">数据丢失防护 (DLP) 策略只适用于元数据（包括 Office 365 标签），但并不适用于这些文件的内容（如文件内的信用卡号）。</span><span class="sxs-lookup"><span data-stu-id="56567-114">Data Loss Prevention (DLP) policies can only work with the metadata (including Office 365 labels) but not the contents of these files (such as credit card numbers within files).</span></span>

- <span data-ttu-id="56567-115">此解决方案要求用户选择应用相应保护的标签。</span><span class="sxs-lookup"><span data-stu-id="56567-115">This solution requires a user to select a label that applies the protection.</span></span> <span data-ttu-id="56567-116">如果需要自动加密以及支持 SharePoint 索引和检查文件的功能，请考虑在 SharePoint Online 中使用信息权限管理 (IRM)。</span><span class="sxs-lookup"><span data-stu-id="56567-116">If you require automatic encryption and the ability for SharePoint to index and inspect the files, consider using Information Rights Management (IRM) in SharePoint Online.</span></span> <span data-ttu-id="56567-117">为 IRM 配置 SharePoint 库时，文件会在下载以供进行编辑时自动进行加密。</span><span class="sxs-lookup"><span data-stu-id="56567-117">When you configure a SharePoint library for IRM, files are automatically encrypted when they are downloaded for editing.</span></span>  <span data-ttu-id="56567-118">SharePoint IRM 包含可能会影响你的决策的限制。</span><span class="sxs-lookup"><span data-stu-id="56567-118">SharePoint IRM includes limitations that might influence your decision.</span></span> <span data-ttu-id="56567-119">有关详细信息，请参阅[在 SharePoint 管理中心设置信息权限管理 (IRM)](https://support.office.com/article/Set-up-Information-Rights-Management-IRM-in-SharePoint-admin-center-239CE6EB-4E81-42DB-BF86-A01362FED65C)。</span><span class="sxs-lookup"><span data-stu-id="56567-119">[Set up Information Rights Management (IRM) in SharePoint admin center](https://support.office.com/article/Set-up-Information-Rights-Management-IRM-in-SharePoint-admin-center-239CE6EB-4E81-42DB-BF86-A01362FED65C)</span></span>

## <a name="admin-setup"></a><span data-ttu-id="56567-120">管理员设置</span><span class="sxs-lookup"><span data-stu-id="56567-120">Admin setup</span></span>

<span data-ttu-id="56567-121">若要以这种方式为特定 SharePoint Online 团队网站中的文件实现更高的安全级别，必须配置一个自定义的敏感度标签，以用作其自身标签，或作为高度管控数据的常规标签的子标签。</span><span class="sxs-lookup"><span data-stu-id="56567-121">To accomplish this additional level of security for files stored in the underlying SharePoint site of a team, you must configure a customized sensitivity label that is either its own label or a sublabel of the general label for highly regulated data.</span></span> <span data-ttu-id="56567-122">只有 SharePoint Online 团队网站的 Office 365 组的成员才能在其标签列表中看到自定义标签或子标签。</span><span class="sxs-lookup"><span data-stu-id="56567-122">Only members of the Office 365 group for the SharePoint Online team site will see the customized label or sublabel in their list of labels.</span></span>

- <span data-ttu-id="56567-123">如果需要将少量标签应用于全局和各个私人团队，请使用敏感度标签。</span><span class="sxs-lookup"><span data-stu-id="56567-123">Use a sensitivity label when you need a small number of labels for both global use and individual private teams.</span></span>

- <span data-ttu-id="56567-124">如果你拥有大量标签，或者希望在高度管控标签下整理高度机密团队的标签，请使用敏感度子标签。</span><span class="sxs-lookup"><span data-stu-id="56567-124">Use a sensitivity sublabel when you have a large number of labels or want to organize labels for highly confidential teams under the highly regulated label.</span></span>

<span data-ttu-id="56567-125">按照[这些说明](encryption-sensitivity-labels.md)，使用以下设置配置单独的标签或子标签：</span><span class="sxs-lookup"><span data-stu-id="56567-125">Use [these instructions](encryption-sensitivity-labels.md) to configure a separate label or a sublabel with the following settings:</span></span>

- <span data-ttu-id="56567-126">标签或子标签名称包含团队网站的名称</span><span class="sxs-lookup"><span data-stu-id="56567-126">The name of the label or sublabel contains the name of the team</span></span>
- <span data-ttu-id="56567-127">已启用加密</span><span class="sxs-lookup"><span data-stu-id="56567-127">Encryption is enabled</span></span>
- <span data-ttu-id="56567-128">团队网站的 Office 365 组有共同创作权限</span><span class="sxs-lookup"><span data-stu-id="56567-128">The Office 365 group for the team has Co-Author permissions</span></span>

<span data-ttu-id="56567-129">创建后，为用户发布新的标签或子标签，用户可在将文件上传到团队之前或文件存储在团队中之后，将其应用到文件。</span><span class="sxs-lookup"><span data-stu-id="56567-129">After creating, publish the new label or sublabel for your users, who can then apply them to files either locally before uploading them to the team or later once the file is stored in the team.</span></span>
 
<span data-ttu-id="56567-130">使用后，在 Microsoft Word、Excel 和 PowerPoint 中，可从“**开始**”功能区中的“**敏感度**”选项中选择敏感度标签。</span><span class="sxs-lookup"><span data-stu-id="56567-130">Once your uses can select the sensitivity label from the **Sensitivity** option from the **Home** ribbon in Microsoft Word, Excel, and PowerPoint.</span></span>
  
> [!NOTE]
> <span data-ttu-id="56567-131">如果你有多个高度敏感的 SharePoint Online 团队网站，则应创建多个敏感度标签。</span><span class="sxs-lookup"><span data-stu-id="56567-131">If you have multiple highly sensitive SharePoint Online team sites, you should create multiple sensitivity labels.</span></span> 
  
## <a name="adding-permissions-for-external-users"></a><span data-ttu-id="56567-132">为外部用户添加权限</span><span class="sxs-lookup"><span data-stu-id="56567-132">Adding permissions for external users</span></span>
<span data-ttu-id="56567-133">可通过两种方式授予使用敏感度标签进行保护的文件的外部用户访问权限。</span><span class="sxs-lookup"><span data-stu-id="56567-133">There are two ways you can grant external users access to files protected with a sensitivity label.</span></span> <span data-ttu-id="56567-134">在这两种情况下，外部用户均须具有 Azure AD 帐户。</span><span class="sxs-lookup"><span data-stu-id="56567-134">In both these cases, external users must have an Azure AD account.</span></span> <span data-ttu-id="56567-135">如果外部用户不是使用 Azure AD 的组织的成员，他们可以通过使用此注册页面以个人身份获得 Azure AD 帐户：[https://aka.ms/aip-signup](https://aka.ms/aip-signup)。</span><span class="sxs-lookup"><span data-stu-id="56567-135">If external users aren't members of an organization that uses Azure AD, they can obtain an Azure AD account as an individual by using this sign-up page: [https://aka.ms/aip-signup](https://aka.ms/aip-signup).</span></span>

 - <span data-ttu-id="56567-136">将外部用户添加到团队网站的 Office 365 组中。</span><span class="sxs-lookup"><span data-stu-id="56567-136">Add external users to the Office 365 group for the team site.</span></span> <span data-ttu-id="56567-137">首先需要将帐户添加为目录中的 B2B 用户。</span><span class="sxs-lookup"><span data-stu-id="56567-137">You'll need to first add the account as a B2B user in your directory.</span></span> <span data-ttu-id="56567-138">[通过 Azure Rights Management 缓存组成员身份](https://docs.microsoft.com/azure/information-protection/plan-design/prepare#group-membership-caching-by-azure-information-protection)可能需要数小时。</span><span class="sxs-lookup"><span data-stu-id="56567-138">It can take a couple of hours for [group membership caching by Azure Rights Management](https://docs.microsoft.com/azure/information-protection/plan-design/prepare#group-membership-caching-by-azure-information-protection).</span></span>  
 - <span data-ttu-id="56567-139">将外部用户帐户直接添加到标签配置。</span><span class="sxs-lookup"><span data-stu-id="56567-139">Add external user accounts directly to the label configuration.</span></span> <span data-ttu-id="56567-140">可以添加组织（例如 Fabrikam.com）中的所有用户、一个 Office 365 组（例如组织内的财务组）或单个用户。</span><span class="sxs-lookup"><span data-stu-id="56567-140">You can add all users from an organization (e.g. Fabrikam.com), an Azure AD group (such as a finance group within an organization), or an individual user.</span></span> <span data-ttu-id="56567-141">例如，可以将外部监管人员团队添加到敏感度标签权限。</span><span class="sxs-lookup"><span data-stu-id="56567-141">For example, you can add an external team of regulators to the protection for a label.</span></span>

## <a name="see-also"></a><span data-ttu-id="56567-142">另请参阅</span><span class="sxs-lookup"><span data-stu-id="56567-142">See Also</span></span>

[<span data-ttu-id="56567-143">保护 SharePoint Online 网站和文件</span><span class="sxs-lookup"><span data-stu-id="56567-143">Secure SharePoint Online sites and files</span></span>](https://docs.microsoft.com/microsoft-365/compliance/deploy-sharepoint-online-sites-for-three-tiers-of-protection)
  
[<span data-ttu-id="56567-144">Microsoft 针对政治宣传活动、非营利组织和其他敏捷性组织的安全指南</span><span class="sxs-lookup"><span data-stu-id="56567-144">Microsoft Security Guidance for Political Campaigns, Nonprofits, and Other Agile Organizations</span></span>](/security/office-365-security/microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md)
  
[<span data-ttu-id="56567-145">云应用和混合解决方案</span><span class="sxs-lookup"><span data-stu-id="56567-145">Cloud adoption and hybrid solutions</span></span>](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)
