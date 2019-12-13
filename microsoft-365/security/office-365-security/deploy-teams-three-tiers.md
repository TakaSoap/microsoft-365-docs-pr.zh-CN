---
title: 部署适用于三层文件保护的团队
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 10/31/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom:
- Ent_Solutions
ms.assetid: 1e8e3cfd-b878-4088-b941-9940363a5fae
description: 通过 Microsoft Teams 创建和配置团队，以实现对文件的多级别信息保护。
ms.openlocfilehash: 3b90a1b084f7cd7e56d1d6448d74a7d2c2469a4d
ms.sourcegitcommit: 5710ce729c55d95b8b452d99ffb7ea92b5cb254a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2019
ms.locfileid: "39971820"
---
# <a name="deploy-teams-for-three-tiers-of-protection-for-files"></a><span data-ttu-id="4f618-103">部署适用于三层文件保护的团队</span><span class="sxs-lookup"><span data-stu-id="4f618-103">Deploy teams for three tiers of protection for files</span></span>

<span data-ttu-id="4f618-104">使用本文中的步骤设计和部署基线、敏感和高度机密团队。</span><span class="sxs-lookup"><span data-stu-id="4f618-104">Use the steps in this article to design and deploy baseline, sensitive, and highly confidential teams.</span></span> <span data-ttu-id="4f618-105">有关这三层保护的详细信息，请参阅[保护 Microsoft Teams 中的文件](secure-files-in-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="4f618-105">For more information about these three tiers of protection, see [Secure files in Microsoft Teams](secure-files-in-teams.md).</span></span>

## <a name="baseline-teams"></a><span data-ttu-id="4f618-106">基准团队</span><span class="sxs-lookup"><span data-stu-id="4f618-106">Baseline teams</span></span>

<span data-ttu-id="4f618-107">基线保护同时包括公共和专用团队。</span><span class="sxs-lookup"><span data-stu-id="4f618-107">Baseline protection includes both public and private teams.</span></span> <span data-ttu-id="4f618-108">组织中的任何人均可发现和访问公共团队。</span><span class="sxs-lookup"><span data-stu-id="4f618-108">Public teams can be discovered and accessed by anybody in the organization.</span></span> <span data-ttu-id="4f618-109">只有与团队关联的 Office 365 组的成员才可以发现并访问专用网站。</span><span class="sxs-lookup"><span data-stu-id="4f618-109">Private sites can only be discovered and accessed by members of the Office 365 group associated with the team.</span></span> <span data-ttu-id="4f618-110">两种类型的团队均允许成员与他人共享网站。</span><span class="sxs-lookup"><span data-stu-id="4f618-110">Both of these types of teams allow members to share the site with others.</span></span>

### <a name="public"></a><span data-ttu-id="4f618-111">公开</span><span class="sxs-lookup"><span data-stu-id="4f618-111">Public</span></span>

<span data-ttu-id="4f618-112">按照[本文](https://support.office.com/article/174adf5f-846b-4780-b765-de1a0a737e2b)中的说明操作，创建具有公共访问权限和权限的基准团队。</span><span class="sxs-lookup"><span data-stu-id="4f618-112">Follow the instructions in [this article](https://support.office.com/article/174adf5f-846b-4780-b765-de1a0a737e2b) to create a baseline team with public access and permissions.</span></span>

<span data-ttu-id="4f618-113">下面是生成的配置。</span><span class="sxs-lookup"><span data-stu-id="4f618-113">Here is your resulting configuration.</span></span>

![面向公共团队的基准级别保护。](../media/baseline-public-team.png)

### <a name="private"></a><span data-ttu-id="4f618-115">Private</span><span class="sxs-lookup"><span data-stu-id="4f618-115">Private</span></span>

<span data-ttu-id="4f618-116">按照[本文](https://support.office.com/article/174adf5f-846b-4780-b765-de1a0a737e2b)中的说明操作，创建具有私人访问权限和权限的基准团队。</span><span class="sxs-lookup"><span data-stu-id="4f618-116">Follow the instructions in [this article](https://support.office.com/article/174adf5f-846b-4780-b765-de1a0a737e2b) to create a baseline team with private access and permissions.</span></span>

<span data-ttu-id="4f618-117">下面是生成的配置。</span><span class="sxs-lookup"><span data-stu-id="4f618-117">Here is your resulting configuration.</span></span>

![面向私人团队的基准级别保护。](../media/baseline-private-team.png)

## <a name="sensitive-teams"></a><span data-ttu-id="4f618-119">敏感团队</span><span class="sxs-lookup"><span data-stu-id="4f618-119">Sensitive teams</span></span>

<span data-ttu-id="4f618-120">对于敏感团队，首先应[创建私人团队](https://support.office.com/article/174adf5f-846b-4780-b765-de1a0a737e2b)。</span><span class="sxs-lookup"><span data-stu-id="4f618-120">For a sensitive team, you start by [creating a private team](https://support.office.com/article/174adf5f-846b-4780-b765-de1a0a737e2b).</span></span>

<span data-ttu-id="4f618-121">接下来，配置底层 SharePoint 网站以防止团队成员共享。</span><span class="sxs-lookup"><span data-stu-id="4f618-121">Next, you configure the underlying SharePoint site to prevent sharing by team members.</span></span>

1. <span data-ttu-id="4f618-122">在团队的工具栏中，单击“文件”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4f618-122">In the tool bar for the team, click **Files**.</span></span>

2. <span data-ttu-id="4f618-123">单击省略号，然后单击“在 SharePoint 中打开”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4f618-123">Click the ellipsis, and then click **Open in SharePoint**.</span></span>

3. <span data-ttu-id="4f618-124">在基础 SharePoint 网站的工具栏中，依次单击设置图标和“网站权限”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4f618-124">In the tool bar of the underlying SharePoint site, click the settings icon, and then click **Site permissions**.</span></span>

4. <span data-ttu-id="4f618-125">在“**网站权限**”窗格的“**共享设置**”下方，单击“**更改共享设置**”。</span><span class="sxs-lookup"><span data-stu-id="4f618-125">In the **Site permissions** pane, under **Sharing Settings**, click **Change sharing settings**.</span></span>

5. <span data-ttu-id="4f618-126">在“共享权限”下方，选择“仅网站所有者可以共享文件、文件夹和网站”，然后单击“保存”\*\*\*\*\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4f618-126">Under **Sharing permissions**, choose **Only site owners can share files, folders, and the site**, and then click **Save**.</span></span>

<span data-ttu-id="4f618-127">下面是生成的配置。</span><span class="sxs-lookup"><span data-stu-id="4f618-127">Here is your resulting configuration.</span></span>

![团队的敏感保护。](../media/sensitive-team.png)

## <a name="highly-confidential-teams"></a><span data-ttu-id="4f618-129">高度机密团队</span><span class="sxs-lookup"><span data-stu-id="4f618-129">Highly confidential teams</span></span>

<span data-ttu-id="4f618-130">对于高度机密团队，首先应[创建私人团队](https://support.office.com/article/174adf5f-846b-4780-b765-de1a0a737e2b)。</span><span class="sxs-lookup"><span data-stu-id="4f618-130">With a highly confidential team, you start by [creating a private team](https://support.office.com/article/174adf5f-846b-4780-b765-de1a0a737e2b).</span></span>

<span data-ttu-id="4f618-131">接下来，配置底层 SharePoint 网站以防止团队成员共享，并防止团队的非成员请求访问权限。</span><span class="sxs-lookup"><span data-stu-id="4f618-131">Next, you configure the underlying SharePoint site to prevent sharing by team members and the requesting of access by non-members of the team.</span></span>

1. <span data-ttu-id="4f618-132">在团队的工具栏中，单击“文件”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4f618-132">In the tool bar for the team, click **Files**.</span></span>

2. <span data-ttu-id="4f618-133">单击省略号，然后单击“在 SharePoint 中打开”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4f618-133">Click the ellipsis, and then click **Open in SharePoint**.</span></span>

3. <span data-ttu-id="4f618-134">在基础 SharePoint 网站的工具栏中，依次单击设置图标和“网站权限”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4f618-134">In the tool bar of the underlying SharePoint site, click the settings icon, and then click **Site permissions**.</span></span>

4. <span data-ttu-id="4f618-135">在“**网站权限**”窗格的“**共享设置**”下方，单击“**更改共享设置**”。</span><span class="sxs-lookup"><span data-stu-id="4f618-135">In the **Site permissions** pane, under **Sharing Settings**, click **Change sharing settings**.</span></span>

5. <span data-ttu-id="4f618-136">在“**共享权限**”下方，选择“**仅网站所有者可以共享文件、文件夹和网站**”。</span><span class="sxs-lookup"><span data-stu-id="4f618-136">Under **Sharing permissions**, choose **Only site owners can share files, folders, and the site**.</span></span>

6. <span data-ttu-id="4f618-137">关闭“**允许访问请求**”，然后单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="4f618-137">Turn off **Allow access requests**, and then click **Save**.</span></span>

<span data-ttu-id="4f618-138">下面是生成的配置。</span><span class="sxs-lookup"><span data-stu-id="4f618-138">Here is your resulting configuration.</span></span>

![团队的高度机密保护。](../media/highly-confidential-team.png)

## <a name="next-step"></a><span data-ttu-id="4f618-140">后续步骤</span><span class="sxs-lookup"><span data-stu-id="4f618-140">Next step</span></span>

[<span data-ttu-id="4f618-141">使用保留标签和 DLP 保护团队中的文件</span><span class="sxs-lookup"><span data-stu-id="4f618-141">Protect files in teams with retention labels and DLP</span></span>](deploy-teams-retention-DLP.md)

## <a name="see-also"></a><span data-ttu-id="4f618-142">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4f618-142">See also</span></span>

[<span data-ttu-id="4f618-143">保护 Microsoft Teams 中的文件</span><span class="sxs-lookup"><span data-stu-id="4f618-143">Secure files in Microsoft Teams</span></span>](secure-files-in-teams.md)

[<span data-ttu-id="4f618-144">云应用和混合解决方案</span><span class="sxs-lookup"><span data-stu-id="4f618-144">Cloud adoption and hybrid solutions</span></span>](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)
