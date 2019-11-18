---
title: Microsoft 合规性分数发行说明
ms.author: chvukosw
author: chvukosw
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Microsoft 合规性分数的发行说明和已知问题（预览版）（M365 合规性中心中的一项功能，可帮助简化和自动化风险评估）。
ms.openlocfilehash: 192519e323f9d23420f82a603979b50f4581ac4f
ms.sourcegitcommit: e2ed110c4c3a8434f9fcc9d610069bc77bc39220
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/12/2019
ms.locfileid: "38685233"
---
# <a name="microsoft-compliance-score-release-notes-preview"></a><span data-ttu-id="5aa89-103">Microsoft 合规性分数发行说明（预览）</span><span class="sxs-lookup"><span data-stu-id="5aa89-103">Microsoft Compliance Score release notes (Preview)</span></span>

<span data-ttu-id="5aa89-104">Microsoft 合规性分数的公开预览为你提供了对即将推出的功能和更新的早期访问权限。</span><span class="sxs-lookup"><span data-stu-id="5aa89-104">The public preview of Microsoft Compliance Score provides you with early access to upcoming functionality and updates.</span></span>

<span data-ttu-id="5aa89-105">合规性分数是[Microsoft 365 合规性中心](microsoft-365-compliance-center.md)中的一项新功能，可计算基于风险的分数，从而衡量完成建议的操作以帮助降低合规性风险的进度。</span><span class="sxs-lookup"><span data-stu-id="5aa89-105">Compliance Score is a new feature in the [Microsoft 365 compliance center](microsoft-365-compliance-center.md) that calculates a risk-based score, measuring your progress towards completing recommended actions that help reduce compliance risks.</span></span>

## <a name="compliance-score-and-compliance-manager-relationship"></a><span data-ttu-id="5aa89-106">合规性分数和合规性管理器关系</span><span class="sxs-lookup"><span data-stu-id="5aa89-106">Compliance Score and Compliance Manager relationship</span></span>

<span data-ttu-id="5aa89-107">现在，在合规性管理器中处理的许多合规性函数都可以在合规性分数中完成。</span><span class="sxs-lookup"><span data-stu-id="5aa89-107">Many of the compliance functions handled in Compliance Manager can now be done in Compliance Score.</span></span> <span data-ttu-id="5aa89-108">但是，某些功能仍仅驻留在合规性管理器中，并且在公共预览版期间，合规性管理器中的一些以前的功能会发生更改。</span><span class="sxs-lookup"><span data-stu-id="5aa89-108">However some functionality still resides only in Compliance Manager, and some previous functionality in Compliance Manager is altered during the public preview period.</span></span> 

<span data-ttu-id="5aa89-109">在公共预览版过程中使用合规性分数和合规性管理器时，请牢记以下几点：</span><span class="sxs-lookup"><span data-stu-id="5aa89-109">Keep these points in mind as you work with Compliance Score and Compliance Manager during public preview:</span></span>

- <span data-ttu-id="5aa89-110">**管理评估**：用户可以按合规性分数查看评估及其状态详细信息。</span><span class="sxs-lookup"><span data-stu-id="5aa89-110">**Managing assessments**: users can view assessments and their status details in Compliance Score.</span></span> <span data-ttu-id="5aa89-111">但是，用户只能在合规性管理器（[查看说明](working-with-compliance-manager.md#assessments)）和任务中执行评估管理任务，并将其限制为以下各项：</span><span class="sxs-lookup"><span data-stu-id="5aa89-111">However users can only perform assessment management tasks in Compliance Manager ([view instructions](working-with-compliance-manager.md#assessments)), and tasks and are limited to the following:</span></span>
    - <span data-ttu-id="5aa89-112">上载新的评估，但不修改现有评估。</span><span class="sxs-lookup"><span data-stu-id="5aa89-112">Upload new assessments, but not modify existing assessments.</span></span> <span data-ttu-id="5aa89-113">如果需要修改现有评估，将需要上传新模板。</span><span class="sxs-lookup"><span data-stu-id="5aa89-113">If you need to modify an existing assessment, you will need to upload a new template.</span></span>
    - <span data-ttu-id="5aa89-114">导出评估</span><span class="sxs-lookup"><span data-stu-id="5aa89-114">Export assessments</span></span>
    - <span data-ttu-id="5aa89-115">存档评估</span><span class="sxs-lookup"><span data-stu-id="5aa89-115">Archive assessments</span></span>
    - <span data-ttu-id="5aa89-116">查看存档的评估</span><span class="sxs-lookup"><span data-stu-id="5aa89-116">View archived assessments</span></span>
 - <span data-ttu-id="5aa89-117">**创建用于评估的模板**：</span><span class="sxs-lookup"><span data-stu-id="5aa89-117">**Creating templates for assessments**:</span></span> 
   - <span data-ttu-id="5aa89-118">用户必须转到合规性管理器以创建新模板并导出现有模板。</span><span class="sxs-lookup"><span data-stu-id="5aa89-118">Users must go to Compliance Manager to create new templates and export existing templates.</span></span> 
   - <span data-ttu-id="5aa89-119">现有模板不能自定义。</span><span class="sxs-lookup"><span data-stu-id="5aa89-119">Existing templates cannot be customized.</span></span> <span data-ttu-id="5aa89-120">阅读有关[管理合规性管理器中的模板](working-with-compliance-manager.md#templates)的说明。</span><span class="sxs-lookup"><span data-stu-id="5aa89-120">Read instructions for [managing templates in Compliance Manager](working-with-compliance-manager.md#templates).</span></span>
   - <span data-ttu-id="5aa89-121">创建模板时，您必须包括**产品**和**证书**的维度，以确保您的模板在合规性分数中显示。</span><span class="sxs-lookup"><span data-stu-id="5aa89-121">When creating a template, you must include Dimensions for both **Product** and **Certification** to ensure your template displays in Compliance Score.</span></span>
 - <span data-ttu-id="5aa89-122">**设置权限**：合规性分数以前未授予合规性管理器中的权限的用户必须在 Microsoft 365 合规性中心中设置其权限。</span><span class="sxs-lookup"><span data-stu-id="5aa89-122">**Setting permissions**: Compliance Score users who were not previously granted permissions in Compliance Manager must have their permissions set in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="5aa89-123">以前在合规性管理器中设置了其角色的用户可以在遵守合规性分数时使用相同级别的访问权限。</span><span class="sxs-lookup"><span data-stu-id="5aa89-123">Users whose roles were previously set in Compliance Manager can use that same level of access when working in Compliance Score.</span></span>
- <span data-ttu-id="5aa89-124">**数据传输**：具有驻留在合规性管理器中的数据的组织将看到符合性分数的数据，反之亦然。</span><span class="sxs-lookup"><span data-stu-id="5aa89-124">**Transfer of data**: organizations with data residing in Compliance Manger will see that data in Compliance Score, and vice-versa.</span></span>
- <span data-ttu-id="5aa89-125">**根据合规性分数登录合规性管理器**：如果用户已登录合规性分数并选择链接以转到合规性管理器，则用户将不必再次登录。</span><span class="sxs-lookup"><span data-stu-id="5aa89-125">**Signing in to Compliance Manager from Compliance Score**: if a user is signed in to Compliance Score and selects a link to go to Compliance Manager, the user will not have to sign in again.</span></span> <span data-ttu-id="5aa89-126">单击该链接后，将在浏览器中打开一个新的选项卡，其中带有一个对话框。</span><span class="sxs-lookup"><span data-stu-id="5aa89-126">After clicking the link, a new tab opens in your browser featuring a dialogue box.</span></span> <span data-ttu-id="5aa89-127">在标题为 "已成为 Microsoft 云服务客户" 的顶部部分？</span><span class="sxs-lookup"><span data-stu-id="5aa89-127">In the top section with the header, “Already a Microsoft cloud services customer?</span></span> <span data-ttu-id="5aa89-128">登录您的帐户，选择 "**登录**" 按钮以自动登录合规性管理器。</span><span class="sxs-lookup"><span data-stu-id="5aa89-128">Sign in to your account,” select the **Sign In** button to automatically sign in to Compliance Manager.</span></span>

## <a name="known-issues-in-compliance-score-preview"></a><span data-ttu-id="5aa89-129">合规性分数中的已知问题（预览）</span><span class="sxs-lookup"><span data-stu-id="5aa89-129">Known issues in Compliance Score (Preview)</span></span>

<span data-ttu-id="5aa89-130">以下各节介绍了在即将发布的合规性分数中要解决的已知问题。</span><span class="sxs-lookup"><span data-stu-id="5aa89-130">The following sections cover known issues to be resolved in upcoming releases of Compliance Score.</span></span>

### <a name="launch-now-links-in-certain-improvement-actions"></a><span data-ttu-id="5aa89-131">在某些改进操作中立即启动链接</span><span class="sxs-lookup"><span data-stu-id="5aa89-131">Launch Now links in certain improvement actions</span></span>

<span data-ttu-id="5aa89-132">在某些改进操作中，选择显示在实现指令下方的 "**立即启动**" 链接会产生错误。</span><span class="sxs-lookup"><span data-stu-id="5aa89-132">In certain improvement actions, selecting the **Launch Now** link that appears underneath the implementation instructions gives an error.</span></span> <span data-ttu-id="5aa89-133">若要访问正确的目标（即 SharePoint 管理中心），请按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="5aa89-133">To access the proper destination, which is the the SharePoint admin center, follow these steps:</span></span>

1. <span data-ttu-id="5aa89-134">转到[Microsoft 365 管理中心](https://admin.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="5aa89-134">Go to the [Microsoft 365 Admin Center](https://admin.microsoft.com).</span></span>
2. <span data-ttu-id="5aa89-135">在左侧导航菜单上，选择 "**全部显示**"。</span><span class="sxs-lookup"><span data-stu-id="5aa89-135">On the left navigation menu, select **Show all**.</span></span>
3. <span data-ttu-id="5aa89-136">在 "**管理中心" 下，** 选择 " **SharePoint**"。</span><span class="sxs-lookup"><span data-stu-id="5aa89-136">Under **Admin centers,** select **SharePoint**.</span></span>

<span data-ttu-id="5aa89-137">以下是受影响的改进操作，它们都驻留在 "**保护信息**" 类别中：</span><span class="sxs-lookup"><span data-stu-id="5aa89-137">Below are the affected improvement actions, which all reside in the **Protect information** category:</span></span>
  - <span data-ttu-id="5aa89-138">将加密应用于 SharePoint 库</span><span class="sxs-lookup"><span data-stu-id="5aa89-138">Apply encryption to SharePoint Library</span></span>
  - <span data-ttu-id="5aa89-139">对 SharePoint Online 中的数据进行分类</span><span class="sxs-lookup"><span data-stu-id="5aa89-139">Classify Data in SharePoint Online</span></span>
  - <span data-ttu-id="5aa89-140">配置外部共享链接以使其过期</span><span class="sxs-lookup"><span data-stu-id="5aa89-140">Configure External Sharing Links to Expire</span></span>
  - <span data-ttu-id="5aa89-141">为文档库启用版本控制</span><span class="sxs-lookup"><span data-stu-id="5aa89-141">Enable Versioning for Document Libraries</span></span>

### <a name="long-load-times-for-non-admin-users"></a><span data-ttu-id="5aa89-142">非管理员用户的长时间加载时间</span><span class="sxs-lookup"><span data-stu-id="5aa89-142">Long load times for non-admin users</span></span>
<span data-ttu-id="5aa89-143">合规性分数在尝试登录时，保留非管理员角色角色的用户可能会遇到较长的加载时间。</span><span class="sxs-lookup"><span data-stu-id="5aa89-143">Compliance Score users who hold roles other than an admin role may experience long load times when trying to a sign in.</span></span> <span data-ttu-id="5aa89-144">刷新浏览器将解决此问题。</span><span class="sxs-lookup"><span data-stu-id="5aa89-144">Refreshing your browser will resolve this issue.</span></span> <span data-ttu-id="5aa89-145">（了解有关[合规性分数角色](compliance-score-setup.md#set-user-permissions-and-assign-roles)的详细信息。）</span><span class="sxs-lookup"><span data-stu-id="5aa89-145">(Learn more about [Compliance Score roles](compliance-score-setup.md#set-user-permissions-and-assign-roles).)</span></span>

### <a name="supported-browsers"></a><span data-ttu-id="5aa89-146">支持的浏览器</span><span class="sxs-lookup"><span data-stu-id="5aa89-146">Supported browsers</span></span>

- <span data-ttu-id="5aa89-147">Microsoft Edge、Chrome 和 Safari 的最新版本均受支持。</span><span class="sxs-lookup"><span data-stu-id="5aa89-147">The latest versions of Microsoft Edge, Chrome, and Safari are supported.</span></span>
- <span data-ttu-id="5aa89-148">在刷新浏览器之前，可能会出现更新后的数据未出现的情况。</span><span class="sxs-lookup"><span data-stu-id="5aa89-148">There may be instances where updated data does not appear until your browser is refreshed.</span></span>
- <span data-ttu-id="5aa89-149">Microsoft Edge 的预览版本不受支持，但没有已知问题。</span><span class="sxs-lookup"><span data-stu-id="5aa89-149">The preview version of Microsoft Edge is not supported but has no known issues.</span></span>
- <span data-ttu-id="5aa89-150">不支持 Internet Explorer。</span><span class="sxs-lookup"><span data-stu-id="5aa89-150">Internet Explorer is not supported.</span></span>
 
### <a name="language-support"></a><span data-ttu-id="5aa89-151">语言支持</span><span class="sxs-lookup"><span data-stu-id="5aa89-151">Language support</span></span>

- <span data-ttu-id="5aa89-152">合规性分数仅适用于美国英语版。</span><span class="sxs-lookup"><span data-stu-id="5aa89-152">Compliance Score is only available in U.S. English.</span></span>