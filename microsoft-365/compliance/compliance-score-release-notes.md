---
title: Microsoft 合规性分数发行说明
f1.keywords:
- NOCSH
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
ms.openlocfilehash: a46a495e14187ed76926438bc3e28bd70d4f025e
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "41595759"
---
# <a name="microsoft-compliance-score-preview-release-notes"></a><span data-ttu-id="5a7b3-103">Microsoft 合规性分数（预览）发行说明</span><span class="sxs-lookup"><span data-stu-id="5a7b3-103">Microsoft Compliance Score (Preview) release notes</span></span>

<span data-ttu-id="5a7b3-104">Microsoft 合规性分数的公开预览为你提供了对即将推出的功能和更新的早期访问权限。</span><span class="sxs-lookup"><span data-stu-id="5a7b3-104">The public preview of Microsoft Compliance Score provides you with early access to upcoming functionality and updates.</span></span> <span data-ttu-id="5a7b3-105">请经常查看此页面，了解新增功能。</span><span class="sxs-lookup"><span data-stu-id="5a7b3-105">Check this page frequently to learn what's new.</span></span>

<span data-ttu-id="5a7b3-106">合规性分数是[Microsoft 365 合规性中心](microsoft-365-compliance-center.md)中的一项新功能，可计算基于风险的分数，从而衡量完成建议的操作以帮助降低合规性风险的进度。</span><span class="sxs-lookup"><span data-stu-id="5a7b3-106">Compliance Score is a new feature in the [Microsoft 365 compliance center](microsoft-365-compliance-center.md) that calculates a risk-based score, measuring your progress towards completing recommended actions that help reduce compliance risks.</span></span>

## <a name="whats-new"></a><span data-ttu-id="5a7b3-107">最近更新</span><span class="sxs-lookup"><span data-stu-id="5a7b3-107">What's new</span></span>

### <a name="new-templates-for-assessments"></a><span data-ttu-id="5a7b3-108">新的评估模板</span><span class="sxs-lookup"><span data-stu-id="5a7b3-108">New templates for assessments</span></span>

<span data-ttu-id="5a7b3-109">将新的预先配置的模板发布到生产中，以便在符合性分数（预览）变得可用时发布这些模板。</span><span class="sxs-lookup"><span data-stu-id="5a7b3-109">New pre-configured templates for assessments are released into production for Compliance Score (Preview) as they become available.</span></span> <span data-ttu-id="5a7b3-110">[在此处查看模板的完整列表](compliance-score.md#templates)。</span><span class="sxs-lookup"><span data-stu-id="5a7b3-110">Check the [full list of templates here](compliance-score.md#templates).</span></span> <span data-ttu-id="5a7b3-111">最近添加的模板包括：</span><span class="sxs-lookup"><span data-stu-id="5a7b3-111">Recently-added templates include:</span></span>

- <span data-ttu-id="5a7b3-112">巴西常规数据保护法律（LGPD）</span><span class="sxs-lookup"><span data-stu-id="5a7b3-112">Brazil General Data Protection Law (LGPD)</span></span>
- <span data-ttu-id="5a7b3-113">IRAP/澳大利亚政府版 ISM （预览）</span><span class="sxs-lookup"><span data-stu-id="5a7b3-113">IRAP / Australian Government ISM (Preview)</span></span>
- <span data-ttu-id="5a7b3-114">ISO 27701:2019</span><span class="sxs-lookup"><span data-stu-id="5a7b3-114">ISO 27701:2019</span></span>
- <span data-ttu-id="5a7b3-115">SOC 1</span><span class="sxs-lookup"><span data-stu-id="5a7b3-115">SOC 1</span></span>
- <span data-ttu-id="5a7b3-116">SOC 2</span><span class="sxs-lookup"><span data-stu-id="5a7b3-116">SOC 2</span></span>

### <a name="compliance-score-relationship-to-compliance-manager"></a><span data-ttu-id="5a7b3-117">与合规性管理器的合规性分数关系</span><span class="sxs-lookup"><span data-stu-id="5a7b3-117">Compliance Score relationship to Compliance Manager</span></span>

<span data-ttu-id="5a7b3-118">现在，在合规性管理器中处理的许多合规性函数都可以在合规性分数中完成。</span><span class="sxs-lookup"><span data-stu-id="5a7b3-118">Many of the compliance functions handled in Compliance Manager can now be done in Compliance Score.</span></span> <span data-ttu-id="5a7b3-119">但是，某些功能仍仅驻留在合规性管理器中，并且在公共预览版期间，合规性管理器中的一些以前的功能会发生更改。</span><span class="sxs-lookup"><span data-stu-id="5a7b3-119">However some functionality still resides only in Compliance Manager, and some previous functionality in Compliance Manager is altered during the public preview period.</span></span> 

<span data-ttu-id="5a7b3-120">在公共预览版过程中使用合规性分数和合规性管理器时，请牢记以下几点：</span><span class="sxs-lookup"><span data-stu-id="5a7b3-120">Keep these points in mind as you work with Compliance Score and Compliance Manager during public preview:</span></span>

- <span data-ttu-id="5a7b3-121">**管理评估**：用户可以按合规性分数查看评估及其状态详细信息。</span><span class="sxs-lookup"><span data-stu-id="5a7b3-121">**Managing assessments**: users can view assessments and their status details in Compliance Score.</span></span> <span data-ttu-id="5a7b3-122">但是，用户只能在合规性管理器中执行评估管理任务（[查看说明](working-with-compliance-manager.md#assessments)），并且任务限制为以下各项：</span><span class="sxs-lookup"><span data-stu-id="5a7b3-122">However users can only perform assessment management tasks in Compliance Manager ([view instructions](working-with-compliance-manager.md#assessments)), and tasks are limited to the following:</span></span>
    - <span data-ttu-id="5a7b3-123">上载新的评估，但不修改现有评估。</span><span class="sxs-lookup"><span data-stu-id="5a7b3-123">Upload new assessments, but not modify existing assessments.</span></span> <span data-ttu-id="5a7b3-124">如果需要修改现有评估，将需要上传新模板。</span><span class="sxs-lookup"><span data-stu-id="5a7b3-124">If you need to modify an existing assessment, you will need to upload a new template.</span></span>
    - <span data-ttu-id="5a7b3-125">导出评估</span><span class="sxs-lookup"><span data-stu-id="5a7b3-125">Export assessments</span></span>
    - <span data-ttu-id="5a7b3-126">存档评估</span><span class="sxs-lookup"><span data-stu-id="5a7b3-126">Archive assessments</span></span>
    - <span data-ttu-id="5a7b3-127">查看存档的评估</span><span class="sxs-lookup"><span data-stu-id="5a7b3-127">View archived assessments</span></span>
 - <span data-ttu-id="5a7b3-128">**创建用于评估的模板**：</span><span class="sxs-lookup"><span data-stu-id="5a7b3-128">**Creating templates for assessments**:</span></span> 
   - <span data-ttu-id="5a7b3-129">用户必须转到合规性管理器以创建新模板并导出现有模板。</span><span class="sxs-lookup"><span data-stu-id="5a7b3-129">Users must go to Compliance Manager to create new templates and export existing templates.</span></span> 
   - <span data-ttu-id="5a7b3-130">现有模板不能自定义。</span><span class="sxs-lookup"><span data-stu-id="5a7b3-130">Existing templates cannot be customized.</span></span> <span data-ttu-id="5a7b3-131">阅读有关[管理合规性管理器中的模板](working-with-compliance-manager.md#templates)的说明。</span><span class="sxs-lookup"><span data-stu-id="5a7b3-131">Read instructions for [managing templates in Compliance Manager](working-with-compliance-manager.md#templates).</span></span>
   - <span data-ttu-id="5a7b3-132">创建模板时，您必须包括**产品**和**证书**的维度，以确保您的模板在合规性分数中显示。</span><span class="sxs-lookup"><span data-stu-id="5a7b3-132">When creating a template, you must include Dimensions for both **Product** and **Certification** to ensure your template displays in Compliance Score.</span></span>
 - <span data-ttu-id="5a7b3-133">**设置权限**：合规性分数以前未授予合规性管理器中的权限的用户必须在 Microsoft 365 合规性中心中设置其权限（[了解详细信息](compliance-score-setup.md#set-user-permissions-and-assign-roles)）。</span><span class="sxs-lookup"><span data-stu-id="5a7b3-133">**Setting permissions**: Compliance Score users who were not previously granted permissions in Compliance Manager must have their permissions set in the Microsoft 365 compliance center ([learn more](compliance-score-setup.md#set-user-permissions-and-assign-roles)).</span></span> <span data-ttu-id="5a7b3-134">以前在合规性管理器中设置了其角色的用户可以在遵守合规性分数时使用相同级别的访问权限。</span><span class="sxs-lookup"><span data-stu-id="5a7b3-134">Users whose roles were previously set in Compliance Manager can use that same level of access when working in Compliance Score.</span></span>
- <span data-ttu-id="5a7b3-135">**数据传输**：具有驻留在合规性管理器中的数据的组织将看到符合性分数的数据，反之亦然。</span><span class="sxs-lookup"><span data-stu-id="5a7b3-135">**Transfer of data**: organizations with data residing in Compliance Manger will see that data in Compliance Score, and vice-versa.</span></span>
- <span data-ttu-id="5a7b3-136">**根据合规性分数登录合规性管理器**：如果用户已登录合规性分数并选择链接以转到合规性管理器，则用户将不必再次登录。</span><span class="sxs-lookup"><span data-stu-id="5a7b3-136">**Signing in to Compliance Manager from Compliance Score**: if a user is signed in to Compliance Score and selects a link to go to Compliance Manager, the user will not have to sign in again.</span></span> <span data-ttu-id="5a7b3-137">单击该链接后，将在浏览器中打开一个新的选项卡，其中带有一个对话框。</span><span class="sxs-lookup"><span data-stu-id="5a7b3-137">After clicking the link, a new tab opens in your browser featuring a dialogue box.</span></span> <span data-ttu-id="5a7b3-138">在标题为 "已成为 Microsoft 云服务客户" 的顶部部分？</span><span class="sxs-lookup"><span data-stu-id="5a7b3-138">In the top section with the header, “Already a Microsoft cloud services customer?</span></span> <span data-ttu-id="5a7b3-139">登录您的帐户，选择 "**登录**" 按钮以自动登录合规性管理器。</span><span class="sxs-lookup"><span data-stu-id="5a7b3-139">Sign in to your account,” select the **Sign In** button to automatically sign in to Compliance Manager.</span></span>

## <a name="known-issues-in-compliance-score-preview"></a><span data-ttu-id="5a7b3-140">合规性分数中的已知问题（预览）</span><span class="sxs-lookup"><span data-stu-id="5a7b3-140">Known issues in Compliance Score (Preview)</span></span>

<span data-ttu-id="5a7b3-141">以下各节介绍了在即将发布的合规性分数中要解决的已知问题。</span><span class="sxs-lookup"><span data-stu-id="5a7b3-141">The following sections cover known issues to be resolved in upcoming releases of Compliance Score.</span></span>

### <a name="launch-now-links-in-certain-improvement-actions"></a><span data-ttu-id="5a7b3-142">在某些改进操作中立即启动链接</span><span class="sxs-lookup"><span data-stu-id="5a7b3-142">Launch Now links in certain improvement actions</span></span>

<span data-ttu-id="5a7b3-143">在某些改进操作中，选择显示在实现指令下方的 "**立即启动**" 链接会产生错误。</span><span class="sxs-lookup"><span data-stu-id="5a7b3-143">In certain improvement actions, selecting the **Launch Now** link that appears underneath the implementation instructions gives an error.</span></span> <span data-ttu-id="5a7b3-144">若要访问正确的目标（即 SharePoint 管理中心），请按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="5a7b3-144">To access the proper destination, which is the SharePoint admin center, follow these steps:</span></span>

1. <span data-ttu-id="5a7b3-145">转到[Microsoft 365 管理中心](https://admin.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="5a7b3-145">Go to the [Microsoft 365 Admin Center](https://admin.microsoft.com).</span></span>
2. <span data-ttu-id="5a7b3-146">在左侧导航菜单上，选择 "**全部显示**"。</span><span class="sxs-lookup"><span data-stu-id="5a7b3-146">On the left navigation menu, select **Show all**.</span></span>
3. <span data-ttu-id="5a7b3-147">在 "**管理中心" 下，** 选择 " **SharePoint**"。</span><span class="sxs-lookup"><span data-stu-id="5a7b3-147">Under **Admin centers,** select **SharePoint**.</span></span>

<span data-ttu-id="5a7b3-148">以下是受影响的改进操作，它们都驻留在 "**保护信息**" 类别中：</span><span class="sxs-lookup"><span data-stu-id="5a7b3-148">Below are the affected improvement actions, which all reside in the **Protect information** category:</span></span>
  - <span data-ttu-id="5a7b3-149">将加密应用于 SharePoint 库</span><span class="sxs-lookup"><span data-stu-id="5a7b3-149">Apply encryption to SharePoint Library</span></span>
  - <span data-ttu-id="5a7b3-150">对 SharePoint Online 中的数据进行分类</span><span class="sxs-lookup"><span data-stu-id="5a7b3-150">Classify Data in SharePoint Online</span></span>
  - <span data-ttu-id="5a7b3-151">配置外部共享链接以使其过期</span><span class="sxs-lookup"><span data-stu-id="5a7b3-151">Configure External Sharing Links to Expire</span></span>
  - <span data-ttu-id="5a7b3-152">为文档库启用版本控制</span><span class="sxs-lookup"><span data-stu-id="5a7b3-152">Enable Versioning for Document Libraries</span></span>

### <a name="long-load-times-for-non-admin-users"></a><span data-ttu-id="5a7b3-153">非管理员用户的长时间加载时间</span><span class="sxs-lookup"><span data-stu-id="5a7b3-153">Long load times for non-admin users</span></span>
<span data-ttu-id="5a7b3-154">合规性分数在尝试登录时，保留非管理员角色角色的用户可能会遇到较长的加载时间。</span><span class="sxs-lookup"><span data-stu-id="5a7b3-154">Compliance Score users who hold roles other than an admin role may experience long load times when trying to a sign in.</span></span> <span data-ttu-id="5a7b3-155">刷新浏览器将解决此问题。</span><span class="sxs-lookup"><span data-stu-id="5a7b3-155">Refreshing your browser will resolve this issue.</span></span> <span data-ttu-id="5a7b3-156">（了解有关[合规性分数角色](compliance-score-setup.md#set-user-permissions-and-assign-roles)的详细信息。）</span><span class="sxs-lookup"><span data-stu-id="5a7b3-156">(Learn more about [Compliance Score roles](compliance-score-setup.md#set-user-permissions-and-assign-roles).)</span></span>

### <a name="supported-browsers"></a><span data-ttu-id="5a7b3-157">支持的浏览器</span><span class="sxs-lookup"><span data-stu-id="5a7b3-157">Supported browsers</span></span>

- <span data-ttu-id="5a7b3-158">Microsoft Edge、Chrome 和 Safari 的最新版本均受支持。</span><span class="sxs-lookup"><span data-stu-id="5a7b3-158">The latest versions of Microsoft Edge, Chrome, and Safari are supported.</span></span>
- <span data-ttu-id="5a7b3-159">在刷新浏览器之前，可能会出现更新后的数据未出现的情况。</span><span class="sxs-lookup"><span data-stu-id="5a7b3-159">There may be instances where updated data does not appear until your browser is refreshed.</span></span>
- <span data-ttu-id="5a7b3-160">Microsoft Edge 的预览版本不受支持，但没有已知问题。</span><span class="sxs-lookup"><span data-stu-id="5a7b3-160">The preview version of Microsoft Edge is not supported but has no known issues.</span></span>
- <span data-ttu-id="5a7b3-161">不支持 Internet Explorer。</span><span class="sxs-lookup"><span data-stu-id="5a7b3-161">Internet Explorer is not supported.</span></span>
 
### <a name="language-support"></a><span data-ttu-id="5a7b3-162">语言支持</span><span class="sxs-lookup"><span data-stu-id="5a7b3-162">Language support</span></span>

- <span data-ttu-id="5a7b3-163">合规性分数仅适用于美国英语版。</span><span class="sxs-lookup"><span data-stu-id="5a7b3-163">Compliance Score is only available in U.S. English.</span></span>