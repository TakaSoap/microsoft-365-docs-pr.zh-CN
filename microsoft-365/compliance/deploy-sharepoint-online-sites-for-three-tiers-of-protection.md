---
title: 部署具有三层保护的 SharePoint Online 网站
f1.keywords:
- NOCSH
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
ms.assetid: 1e8e3cfd-b878-4088-b941-9940363a5fae
description: 摘要：为各种级别的信息保护创建和配置 SharePoint Online 团队网站。
ms.openlocfilehash: 1827c4a19cfd31a236dfbd58e454c610cae14477
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42075506"
---
# <a name="deploy-sharepoint-online-sites-for-three-tiers-of-protection"></a><span data-ttu-id="e3da8-103">部署具有三层保护的 SharePoint Online 网站</span><span class="sxs-lookup"><span data-stu-id="e3da8-103">Deploy SharePoint Online sites for three tiers of protection</span></span>

<span data-ttu-id="e3da8-p101">使用本文中的步骤设计和部署基线、敏感和高度机密的 SharePoint Online 团队网站。 有关三层保护的详细信息，请参阅[保护 SharePoint Online 网站和文件](../security/office-365-security/secure-sharepoint-online-sites-and-files.md)。</span><span class="sxs-lookup"><span data-stu-id="e3da8-p101">Use the steps in this article to design and deploy baseline, sensitive, and highly confidential SharePoint Online team sites. For more information about these three tiers of protection, see [Secure SharePoint Online sites and files](../security/office-365-security/secure-sharepoint-online-sites-and-files.md).</span></span>
  
## <a name="baseline-sharepoint-online-team-sites"></a><span data-ttu-id="e3da8-106">基线 SharePoint Online 团队网站</span><span class="sxs-lookup"><span data-stu-id="e3da8-106">Baseline SharePoint Online team sites</span></span>

<span data-ttu-id="e3da8-p102">基线保护同时包括公共和专用团队网站。 组织中的任何人均可发现并访问公共团队网站。 只有与团队网站关联的 Office 365 组的成员才可以发现并访问专用网站。 两种类型的团队网站均允许成员与他人共享网站。</span><span class="sxs-lookup"><span data-stu-id="e3da8-p102">Baseline protection includes both public and private team sites. Public team sites can be discovered and accessed by anybody in the organization. Private sites can only be discovered and accessed by members of the Office 365 group associated with the team site. Both of these types of team sites allow members to share the site with others.</span></span>
  
### <a name="public"></a><span data-ttu-id="e3da8-111">公开</span><span class="sxs-lookup"><span data-stu-id="e3da8-111">Public</span></span>

<span data-ttu-id="e3da8-112">要创建具有公共访问和权限的基线 SharePoint Online 团队网站，请按照[这些说明](https://support.office.com/article/create-a-team-site-in-sharepoint-ef10c1e7-15f3-42a3-98aa-b5972711777d)操作。</span><span class="sxs-lookup"><span data-stu-id="e3da8-112">To create a baseline SharePoint Online team site with public access and permissions, follow [these instructions](https://support.office.com/article/create-a-team-site-in-sharepoint-ef10c1e7-15f3-42a3-98aa-b5972711777d).</span></span>

<span data-ttu-id="e3da8-113">下面是生成的配置。</span><span class="sxs-lookup"><span data-stu-id="e3da8-113">Here is your resulting configuration.</span></span>
  
![适用于公共 SharePoint Online 团队网站的基线级保护。](../media/bcd46b8d-3f89-4398-80ce-4da17ee85e03.png)
  
### <a name="private"></a><span data-ttu-id="e3da8-115">私人</span><span class="sxs-lookup"><span data-stu-id="e3da8-115">Private</span></span>

<span data-ttu-id="e3da8-116">要创建具有专用访问和权限的基线 SharePoint Online 团队网站，请按照[这些说明](https://support.office.com/article/create-a-team-site-in-sharepoint-ef10c1e7-15f3-42a3-98aa-b5972711777d)操作。</span><span class="sxs-lookup"><span data-stu-id="e3da8-116">To create a baseline SharePoint Online team site with private access and permissions, follow [these instructions](https://support.office.com/article/create-a-team-site-in-sharepoint-ef10c1e7-15f3-42a3-98aa-b5972711777d).</span></span>
  
<span data-ttu-id="e3da8-117">下面是生成的配置。</span><span class="sxs-lookup"><span data-stu-id="e3da8-117">Here is your resulting configuration.</span></span>
  
![适用于专用 SharePoint Online 团队网站的基线级保护。](../media/91769026-37e3-4383-ac3c-dbf7aca98e41.png)
  
## <a name="sensitive-sharepoint-online-team-sites"></a><span data-ttu-id="e3da8-119">敏感 SharePoint Online 团队网站</span><span class="sxs-lookup"><span data-stu-id="e3da8-119">Sensitive SharePoint Online team sites</span></span>

<span data-ttu-id="e3da8-120">敏感的 SharePoint Online 团队网站首先是一个专用团队网站。</span><span class="sxs-lookup"><span data-stu-id="e3da8-120">A sensitive SharePoint Online team site starts as a private team site.</span></span>
  
<span data-ttu-id="e3da8-121">首先，按照[这些说明](https://support.office.com/article/create-a-team-site-in-sharepoint-ef10c1e7-15f3-42a3-98aa-b5972711777d)创建专用 SharePoint Online 团队网站。</span><span class="sxs-lookup"><span data-stu-id="e3da8-121">First, create the private SharePoint Online team site with [these instructions](https://support.office.com/article/create-a-team-site-in-sharepoint-ef10c1e7-15f3-42a3-98aa-b5972711777d).</span></span>

<span data-ttu-id="e3da8-122">接下来，在新的 SharePoint Online 团队网站中，按照以下步骤操作配置其他权限。</span><span class="sxs-lookup"><span data-stu-id="e3da8-122">Next, from the new SharePoint Online team site, configure additional permission settings with these steps.</span></span>

1.  <span data-ttu-id="e3da8-123">在 SharePoint 团队网站的工具栏中，依次单击设置图标和“**网站权限**”。</span><span class="sxs-lookup"><span data-stu-id="e3da8-123">In the tool bar of the SharePoint team site, click the settings icon, and then click **Site permissions**.</span></span>
2.  <span data-ttu-id="e3da8-124">在“**网站权限**”窗格的“**共享设置**”下方，单击“**更改共享设置**”。</span><span class="sxs-lookup"><span data-stu-id="e3da8-124">In the **Site permissions** pane, under **Sharing Settings**, click **Change sharing settings**.</span></span>
3.  <span data-ttu-id="e3da8-125">在“共享权限”下方，选择“仅网站所有者可以共享文件、文件夹和网站”，然后单击“保存”\*\*\*\*\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="e3da8-125">Under **Sharing permissions**, choose **Only site owners can share files, folders, and the site**, and then click **Save**.</span></span>

<span data-ttu-id="e3da8-126">下面是这些权限设置的结果：</span><span class="sxs-lookup"><span data-stu-id="e3da8-126">The results of these permission settings are:</span></span>

- <span data-ttu-id="e3da8-127">已禁用成员间的相互共享功能。</span><span class="sxs-lookup"><span data-stu-id="e3da8-127">The ability for members to share with other members is disabled.</span></span>
- <span data-ttu-id="e3da8-128">启用非成员请求访问的功能。</span><span class="sxs-lookup"><span data-stu-id="e3da8-128">The ability for non-members to request access is enabled.</span></span>

<span data-ttu-id="e3da8-129">下面是生成的配置。</span><span class="sxs-lookup"><span data-stu-id="e3da8-129">Here is your resulting configuration.</span></span>
  
![适用于独立 SharePoint Online 团队网站的敏感级保护。](../media/7a6ab9c6-560a-4674-ac39-8175644dbe6f.png)
  
<span data-ttu-id="e3da8-131">通过其中一个访问组的组成员身份，网站成员现可对网站资源进行安全协作。</span><span class="sxs-lookup"><span data-stu-id="e3da8-131">The members of the site, through group membership in one of the access groups, can now securely collaborate on the resources of the site.</span></span>
  
## <a name="highly-confidential-sharepoint-online-team-sites"></a><span data-ttu-id="e3da8-132">高度机密的 SharePoint Online 团队网站</span><span class="sxs-lookup"><span data-stu-id="e3da8-132">Highly confidential SharePoint Online team sites</span></span>

<span data-ttu-id="e3da8-133">高度机密的 SharePoint Online 团队网站是一个具有额外权限设置的专用团队网站。</span><span class="sxs-lookup"><span data-stu-id="e3da8-133">A highly confidential SharePoint Online team site is a private team site with additional permissions settings.</span></span>

<span data-ttu-id="e3da8-134">首先，按照[这些说明](https://support.office.com/article/create-a-team-site-in-sharepoint-ef10c1e7-15f3-42a3-98aa-b5972711777d)创建专用 SharePoint Online 团队网站。</span><span class="sxs-lookup"><span data-stu-id="e3da8-134">First, create the private SharePoint Online team site with [these instructions](https://support.office.com/article/create-a-team-site-in-sharepoint-ef10c1e7-15f3-42a3-98aa-b5972711777d).</span></span>

<span data-ttu-id="e3da8-135">接下来，在新的 SharePoint Online 团队网站中，按照以下步骤操作配置其他权限。</span><span class="sxs-lookup"><span data-stu-id="e3da8-135">Next, from the new SharePoint Online team site, configure additional permission settings with these steps.</span></span>

1.  <span data-ttu-id="e3da8-136">在 SharePoint 团队网站的工具栏中，依次单击设置图标和“**网站权限**”。</span><span class="sxs-lookup"><span data-stu-id="e3da8-136">In the tool bar of the SharePoint team site, click the settings icon, and then click **Site permissions**.</span></span>
2.  <span data-ttu-id="e3da8-137">在“**网站权限**”窗格的“**共享设置**”下方，单击“**更改共享设置**”。</span><span class="sxs-lookup"><span data-stu-id="e3da8-137">In the **Site permissions** pane, under **Sharing Settings**, click **Change sharing settings**.</span></span>
3.  <span data-ttu-id="e3da8-138">在“**共享权限**”下方，选择“**仅网站所有者可以共享文件、文件夹和网站**”。</span><span class="sxs-lookup"><span data-stu-id="e3da8-138">Under **Sharing permissions**, choose **Only site owners can share files, folders, and the site**.</span></span>
4. <span data-ttu-id="e3da8-139">关闭“**允许访问请求**”，然后单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="e3da8-139">Turn off **Allow access requests**, and then click **Save**.</span></span>

<span data-ttu-id="e3da8-140">下面是这些权限设置的结果：</span><span class="sxs-lookup"><span data-stu-id="e3da8-140">The results of these permission settings are:</span></span>

- <span data-ttu-id="e3da8-141">已禁用成员间的相互共享功能。</span><span class="sxs-lookup"><span data-stu-id="e3da8-141">The ability for members to share with other members is disabled.</span></span>
- <span data-ttu-id="e3da8-142">禁用非成员请求访问的功能。</span><span class="sxs-lookup"><span data-stu-id="e3da8-142">The ability for non-members to request access is disabled.</span></span>

<span data-ttu-id="e3da8-143">下面是生成的配置。</span><span class="sxs-lookup"><span data-stu-id="e3da8-143">Here is your resulting configuration.</span></span>
  
![适用于独立 SharePoint Online 团队网站的高度机密级保护。](../media/196359ab-d7ed-4fcf-97b4-61820a74aca4.png)
  
<span data-ttu-id="e3da8-145">通过其中一个访问组的组成员身份，网站成员现可对网站资源进行安全协作。</span><span class="sxs-lookup"><span data-stu-id="e3da8-145">The members of the site, through group membership in one of the access groups, can now securely collaborate on the resources of the site.</span></span>
  
## <a name="next-step"></a><span data-ttu-id="e3da8-146">后续步骤</span><span class="sxs-lookup"><span data-stu-id="e3da8-146">Next step</span></span>

[<span data-ttu-id="e3da8-147">使用 Office 365 标签和 DLP 保护 SharePoint Online 文件</span><span class="sxs-lookup"><span data-stu-id="e3da8-147">Protect SharePoint Online files with Office 365 labels and DLP</span></span>](protect-sharepoint-online-files-with-office-365-labels-and-dlp.md)

## <a name="see-also"></a><span data-ttu-id="e3da8-148">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e3da8-148">See also</span></span>

[<span data-ttu-id="e3da8-149">Microsoft 针对政治宣传活动、非营利组织和其他敏捷性组织的安全指南</span><span class="sxs-lookup"><span data-stu-id="e3da8-149">Microsoft Security Guidance for Political Campaigns, Nonprofits, and Other Agile Organizations</span></span>](../security/office-365-security/microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md)
  
[<span data-ttu-id="e3da8-150">云应用和混合解决方案</span><span class="sxs-lookup"><span data-stu-id="e3da8-150">Cloud adoption and hybrid solutions</span></span>](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)
