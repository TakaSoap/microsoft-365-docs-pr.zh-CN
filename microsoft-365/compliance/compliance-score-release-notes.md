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
ms.openlocfilehash: 6678ec03d2cd87a97244acaa55a15483d78dd632
ms.sourcegitcommit: 3ddcf08e8deec087df1fe524147313f1cb12a26d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/02/2020
ms.locfileid: "45022189"
---
# <a name="microsoft-compliance-score-preview-release-notes"></a><span data-ttu-id="18e9a-103">Microsoft 合规性分数（预览）发行说明</span><span class="sxs-lookup"><span data-stu-id="18e9a-103">Microsoft Compliance Score (preview) release notes</span></span>

<span data-ttu-id="18e9a-104">**本文内容：** 此页面显示[Microsoft 合规性分数](compliance-score.md)的公共预览中的**新增**功能，这为你提供了对新功能的早期访问权限。</span><span class="sxs-lookup"><span data-stu-id="18e9a-104">**In this article:** This page shows **what's new** in the public preview of [Microsoft Compliance Score](compliance-score.md), which provides you with early access to new functionality.</span></span>

## <a name="assessment-creation-and-management-functionality"></a><span data-ttu-id="18e9a-105">评估创建和管理功能</span><span class="sxs-lookup"><span data-stu-id="18e9a-105">Assessment creation and management functionality</span></span>

<span data-ttu-id="18e9a-106">2020年6月发布的版本为用户添加了用于在合规性分数中直接创建、删除和管理评估的功能。</span><span class="sxs-lookup"><span data-stu-id="18e9a-106">The June 2020 release adds functionality for users to create, delete, and manage their assessments directly in Compliance Score.</span></span> <span data-ttu-id="18e9a-107">以前，所有评估管理都驻留在合规性管理器中。</span><span class="sxs-lookup"><span data-stu-id="18e9a-107">Previously, all assessment management resided in Compliance Manager.</span></span> <span data-ttu-id="18e9a-108">当您在合规性分数中创建或修改评估时，更新将在合规性管理器中呈现。</span><span class="sxs-lookup"><span data-stu-id="18e9a-108">When you create or modify an assessment in Compliance Score, the updates will surface in Compliance Manager.</span></span> <span data-ttu-id="18e9a-109">同样，在合规性管理器中执行的任何评估工作都会在合规性分数中显示出来。</span><span class="sxs-lookup"><span data-stu-id="18e9a-109">Likewise, any assessment work performed in Compliance Manager will surface in Compliance Score.</span></span> <span data-ttu-id="18e9a-110">了解如何[在合规性分数中管理评估](compliance-score-assessments.md)。</span><span class="sxs-lookup"><span data-stu-id="18e9a-110">Learn how to [manage assessments in Compliance Score](compliance-score-assessments.md).</span></span> <span data-ttu-id="18e9a-111">请注意，模板创建和修改仍在合规性管理器中进行管理。</span><span class="sxs-lookup"><span data-stu-id="18e9a-111">Note that template creation and modification is still managed in Compliance Manager.</span></span>

## <a name="new-templates-for-assessments"></a><span data-ttu-id="18e9a-112">新的评估模板</span><span class="sxs-lookup"><span data-stu-id="18e9a-112">New templates for assessments</span></span>

<span data-ttu-id="18e9a-113">新的准备好使用模板进行评估的功能将在合规性分数中发布，在它们变得可用时发布。</span><span class="sxs-lookup"><span data-stu-id="18e9a-113">New ready to use templates for assessments are released in Compliance Score as they become available.</span></span> <span data-ttu-id="18e9a-114">[在此处查看模板的完整列表](compliance-score-templates.md)。</span><span class="sxs-lookup"><span data-stu-id="18e9a-114">Check the [full list of templates here](compliance-score-templates.md).</span></span> <span data-ttu-id="18e9a-115">最近添加的：</span><span class="sxs-lookup"><span data-stu-id="18e9a-115">Recently added:</span></span>

- <span data-ttu-id="18e9a-116">迪拜信息安全解决方案（DGISR）</span><span class="sxs-lookup"><span data-stu-id="18e9a-116">Dubai Information Security Resolution (DGISR)</span></span>

## <a name="compliance-score-relationship-to-compliance-manager"></a><span data-ttu-id="18e9a-117">与合规性管理器的合规性分数关系</span><span class="sxs-lookup"><span data-stu-id="18e9a-117">Compliance Score relationship to Compliance Manager</span></span>

<span data-ttu-id="18e9a-118">现在，在合规性管理器中处理的许多函数都可以在合规性分数中完成。</span><span class="sxs-lookup"><span data-stu-id="18e9a-118">Many of the functions handled in Compliance Manager can now be done in Compliance Score.</span></span> <span data-ttu-id="18e9a-119">但是，一些功能仍在合规性管理器中。</span><span class="sxs-lookup"><span data-stu-id="18e9a-119">However some functions still live in Compliance Manager.</span></span> <span data-ttu-id="18e9a-120">在公共预览版过程中使用合规性分数和合规性管理器时，请牢记以下几点：</span><span class="sxs-lookup"><span data-stu-id="18e9a-120">Keep these points in mind as you work with Compliance Score and Compliance Manager during public preview:</span></span>

 - <span data-ttu-id="18e9a-121">**创建用于评估的模板**：</span><span class="sxs-lookup"><span data-stu-id="18e9a-121">**Creating templates for assessments**:</span></span> 
   - <span data-ttu-id="18e9a-122">用户必须转到合规性管理器以[创建新模板并修改现有模板](working-with-compliance-manager.md#templates)。</span><span class="sxs-lookup"><span data-stu-id="18e9a-122">Users must go to Compliance Manager to [create new templates and modify existing templates](working-with-compliance-manager.md#templates).</span></span>
   - <span data-ttu-id="18e9a-123">新模板必须包括**产品**和**证书**的尺寸。</span><span class="sxs-lookup"><span data-stu-id="18e9a-123">New templates must include Dimensions for both **Product** and **Certification**.</span></span>
 - <span data-ttu-id="18e9a-124">**设置权限**：合规性分数尚未在合规性管理器中拥有权限的用户需要在 Microsoft 365 合规性中心中设置其权限（[了解详细信息](compliance-score-setup.md#set-user-permissions-and-assign-roles)）。</span><span class="sxs-lookup"><span data-stu-id="18e9a-124">**Setting permissions**: Compliance Score users who didn't already have permissions in Compliance Manager need their permissions set in the Microsoft 365 compliance center ([learn more](compliance-score-setup.md#set-user-permissions-and-assign-roles)).</span></span>
- <span data-ttu-id="18e9a-125">**数据传输**：具有合规性管理器中的数据的组织将看到符合性分数中的数据，而与此不同的方法也是如此。</span><span class="sxs-lookup"><span data-stu-id="18e9a-125">**Transfer of data**: organizations with data in Compliance Manager will see that data in Compliance Score, and the same is true the other way around.</span></span>
- <span data-ttu-id="18e9a-126">**根据合规性分数登录合规性管理器**：如果用户已登录合规性分数并选择链接以转到合规性管理器，则用户不必再次登录。</span><span class="sxs-lookup"><span data-stu-id="18e9a-126">**Signing in to Compliance Manager from Compliance Score**: if a user is signed in to Compliance Score and selects a link to go to Compliance Manager, the user won't have to sign in again.</span></span> <span data-ttu-id="18e9a-127">单击该链接后，将在浏览器中打开一个新的选项卡，其中带有一个对话框。</span><span class="sxs-lookup"><span data-stu-id="18e9a-127">After clicking the link, a new tab opens in your browser featuring a dialogue box.</span></span> <span data-ttu-id="18e9a-128">在标题为 "已成为 Microsoft 云服务客户" 的顶部部分？</span><span class="sxs-lookup"><span data-stu-id="18e9a-128">In the top section with the header, "Already a Microsoft cloud services customer?</span></span> <span data-ttu-id="18e9a-129">登录您的帐户，选择 "**登录**" 按钮以自动登录合规性管理器。</span><span class="sxs-lookup"><span data-stu-id="18e9a-129">Sign in to your account," select the **Sign In** button to automatically sign in to Compliance Manager.</span></span>

## <a name="known-issues-in-compliance-score-preview"></a><span data-ttu-id="18e9a-130">合规性分数中的已知问题（预览）</span><span class="sxs-lookup"><span data-stu-id="18e9a-130">Known issues in Compliance Score (Preview)</span></span>

<span data-ttu-id="18e9a-131">以下各节介绍了在即将发布的合规性分数中要解决的已知问题。</span><span class="sxs-lookup"><span data-stu-id="18e9a-131">The following sections cover known issues to be resolved in upcoming releases of Compliance Score.</span></span>

### <a name="long-load-times-for-non-admin-users"></a><span data-ttu-id="18e9a-132">非管理员用户的长时间加载时间</span><span class="sxs-lookup"><span data-stu-id="18e9a-132">Long load times for non-admin users</span></span>
<span data-ttu-id="18e9a-133">合规性分数在尝试登录时，保留非管理员角色角色的用户可能会遇到较长的加载时间。</span><span class="sxs-lookup"><span data-stu-id="18e9a-133">Compliance Score users who hold roles other than an admin role may experience long load times when trying to a sign in.</span></span> <span data-ttu-id="18e9a-134">刷新浏览器将解决此问题。</span><span class="sxs-lookup"><span data-stu-id="18e9a-134">Refreshing your browser will resolve this issue.</span></span> <span data-ttu-id="18e9a-135">了解有关[合规性分数角色](compliance-score-setup.md#set-user-permissions-and-assign-roles)的详细信息。</span><span class="sxs-lookup"><span data-stu-id="18e9a-135">Learn more about [Compliance Score roles](compliance-score-setup.md#set-user-permissions-and-assign-roles).</span></span>

### <a name="supported-browsers"></a><span data-ttu-id="18e9a-136">支持的浏览器</span><span class="sxs-lookup"><span data-stu-id="18e9a-136">Supported browsers</span></span>

- <span data-ttu-id="18e9a-137">Microsoft Edge、Chrome 和 Safari 的最新版本均受支持。</span><span class="sxs-lookup"><span data-stu-id="18e9a-137">The latest versions of Microsoft Edge, Chrome, and Safari are supported.</span></span>
- <span data-ttu-id="18e9a-138">在刷新浏览器之前，有时不会显示更新后的数据。</span><span class="sxs-lookup"><span data-stu-id="18e9a-138">Updated data sometimes doesn't appear until your browser is refreshed.</span></span>
- <span data-ttu-id="18e9a-139">不支持 Internet Explorer。</span><span class="sxs-lookup"><span data-stu-id="18e9a-139">Internet Explorer is not supported.</span></span>
