---
title: 查看你的应用
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: m365-security-compliance
localization_priority: Priority
search.appverid:
- MOE150
- MET150
description: 查看你的应用。
ms.openlocfilehash: 48a1a2140a3b59091796ca013a12eeefb8a284b9
ms.sourcegitcommit: 41c7f7bd5c808ee5ceca0f6efe13d4e67da0262b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/14/2021
ms.locfileid: "53420029"
---
# <a name="view-your-apps"></a><span data-ttu-id="660e7-103">查看你的应用</span><span class="sxs-lookup"><span data-stu-id="660e7-103">View your apps</span></span>

><span data-ttu-id="660e7-104">*[Microsoft 365 安全性与合规性许可指南](https://aka.ms/ComplianceSD)。*</span><span class="sxs-lookup"><span data-stu-id="660e7-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="660e7-105">Microsoft 应用治理让你可以快速深入了解租户中的 Microsoft 365 应用。</span><span class="sxs-lookup"><span data-stu-id="660e7-105">Microsoft app governance allows you to quickly gain deep insights into the Microsoft 365 apps in your tenant.</span></span> <span data-ttu-id="660e7-106">例如，你可以看到：</span><span class="sxs-lookup"><span data-stu-id="660e7-106">For example, you can see:</span></span>

- <span data-ttu-id="660e7-107">租户中使用 Microsoft Graph API，并且已启用 OAuth 的应用列表，以及相关的应用元数据和使用情况数据。</span><span class="sxs-lookup"><span data-stu-id="660e7-107">A list of OAuth-enabled apps in the tenant that use the Microsoft Graph API, together with relevant app metadata and usage data.</span></span>
- <span data-ttu-id="660e7-108">通过在列表中选择一个应用，可以看到包含更深入的见解和信息的应用详细信息。</span><span class="sxs-lookup"><span data-stu-id="660e7-108">App details with deeper insights and information by selecting an app in the list.</span></span>

## <a name="getting-a-list-of-all-the-apps-in-your-tenant"></a><span data-ttu-id="660e7-109">获取租户中所有应用的列表</span><span class="sxs-lookup"><span data-stu-id="660e7-109">Getting a list of all the apps in your tenant</span></span>

<span data-ttu-id="660e7-110">有关租户中应用的摘要，请转到 **“Microsoft 365 合规中心”>“应用保护和治理”>“应用”**。</span><span class="sxs-lookup"><span data-stu-id="660e7-110">For a summary of apps in your tenant, go to **Microsoft 365 Compliance Center > App protection & governance > Apps**.</span></span>

![Microsoft 365 合规中心内的 MAPG 应用摘要页面](..\media\manage-app-protection-governance\mapg-cc-apps.png)

>[!Note]
> <span data-ttu-id="660e7-112">若要查看应用治理数据，你的登录帐户必须具有[这些角色](app-governance-get-started.md#administrator-roles)中的一个。</span><span class="sxs-lookup"><span data-stu-id="660e7-112">Your sign-in account must have one of [these roles](app-governance-get-started.md#administrator-roles) to view any app governance data.</span></span>
>

<span data-ttu-id="660e7-113">你将看到应用列表和以下信息：</span><span class="sxs-lookup"><span data-stu-id="660e7-113">You will see a list of apps and this information:</span></span>

- <span data-ttu-id="660e7-114">应用名称</span><span class="sxs-lookup"><span data-stu-id="660e7-114">App Name</span></span>
- <span data-ttu-id="660e7-115">发布者</span><span class="sxs-lookup"><span data-stu-id="660e7-115">Publisher</span></span>
- <span data-ttu-id="660e7-116">应用认证</span><span class="sxs-lookup"><span data-stu-id="660e7-116">App certification</span></span>

  <span data-ttu-id="660e7-117">指示应用是否与 Microsoft 技术兼容、是否符合云应用安全最佳实践以及是否受 Microsoft 支持。</span><span class="sxs-lookup"><span data-stu-id="660e7-117">Indicates whether the app is compatible with Microsoft technologies, compliant with cloud app security best practices, and supported by Microsoft.</span></span>

- <span data-ttu-id="660e7-118">上次修改日期</span><span class="sxs-lookup"><span data-stu-id="660e7-118">Last modified</span></span>

  <span data-ttu-id="660e7-119">如果在客户端中安装应用治理的日期比上次修改应用的日期更近，则显示安装日期。</span><span class="sxs-lookup"><span data-stu-id="660e7-119">Shows the date app governance was installed in client if that date is more recent than the date the app was last modified.</span></span>

- <span data-ttu-id="660e7-120">安装日期</span><span class="sxs-lookup"><span data-stu-id="660e7-120">Date installed</span></span>
- <span data-ttu-id="660e7-121">权限级别</span><span class="sxs-lookup"><span data-stu-id="660e7-121">Privilege level</span></span>
- <span data-ttu-id="660e7-122">用户数</span><span class="sxs-lookup"><span data-stu-id="660e7-122">Number of users</span></span>
- <span data-ttu-id="660e7-123">数据访问</span><span class="sxs-lookup"><span data-stu-id="660e7-123">Data access</span></span>

  <span data-ttu-id="660e7-124">过去一天租户中此应用的数据上传和下载总和以及前一天的更改。</span><span class="sxs-lookup"><span data-stu-id="660e7-124">The sum of the app’s data upload and download in the tenant over the last day, along with the change over the prior day.</span></span>

<span data-ttu-id="660e7-125">默认情况下，应用治理按 **应用名称** 对应用列表进行排序。</span><span class="sxs-lookup"><span data-stu-id="660e7-125">App governance sorts the app list by **App name** by default.</span></span> <span data-ttu-id="660e7-126">要按其他应用属性对列表排序，请选择对应的属性名称。</span><span class="sxs-lookup"><span data-stu-id="660e7-126">To sort the list by another app attribute, select the attribute name.</span></span>

<span data-ttu-id="660e7-127">你还可以选择“**搜索**”以按名称搜索应用。</span><span class="sxs-lookup"><span data-stu-id="660e7-127">You can also select **Search** to search for an app by name.</span></span>

## <a name="getting-detailed-information-on-an-app"></a><span data-ttu-id="660e7-128">获取有关应用的详细信息</span><span class="sxs-lookup"><span data-stu-id="660e7-128">Getting detailed information on an app</span></span>

<span data-ttu-id="660e7-129">有关租户中特定应用的详细信息，请转到 \**“Microsoft 365 合规中心”>“应用治理”>“应用页面”>“*应用名称”\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="660e7-129">For detailed information on a specific app in your tenant, go to \*\*Microsoft 365 Compliance Center > App governance > Apps page > \*app name\*\*\*.</span></span>

![Microsoft 365 合规中心内的应用治理应用详细信息窗格](..\media\manage-app-protection-governance\mapg-cc-apps-app.png)

<span data-ttu-id="660e7-131">应用详细信息窗格提供有关这些选项卡的附加信息：</span><span class="sxs-lookup"><span data-stu-id="660e7-131">The app details pane provides additional information on these tabs:</span></span>

| <span data-ttu-id="660e7-132">选项卡名称</span><span class="sxs-lookup"><span data-stu-id="660e7-132">Tab name</span></span> | <span data-ttu-id="660e7-133">说明</span><span class="sxs-lookup"><span data-stu-id="660e7-133">Description</span></span> |
|:-------|:-----|
| <span data-ttu-id="660e7-134">详细信息</span><span class="sxs-lookup"><span data-stu-id="660e7-134">Details</span></span> | <span data-ttu-id="660e7-135">查看应用的其他数据，例如首次同意的日期和应用 ID。</span><span class="sxs-lookup"><span data-stu-id="660e7-135">See additional data on the app such as the date first consented and the App ID.</span></span> <span data-ttu-id="660e7-136">要查看在 Azure AD 中注册的应用的属性，请选择“**在 Azure AD 中查看应用**”。</span><span class="sxs-lookup"><span data-stu-id="660e7-136">To see the properties of the app as registered in Azure AD, select **View app in Azure AD**.</span></span> |
| <span data-ttu-id="660e7-137">使用情况</span><span class="sxs-lookup"><span data-stu-id="660e7-137">Usage</span></span> | <span data-ttu-id="660e7-138">查看租户中的应用访问的数据、绘制数据使用情况图，并显示排名靠前的 \<x> 用户和拥有[优先帐户](/microsoft-365/admin/setup/priority-accounts)的用户的使用情况。</span><span class="sxs-lookup"><span data-stu-id="660e7-138">See the data accessed by the app in the tenant, plot the data usage, and show usage by the top \<x> users and users with [priority accounts](/microsoft-365/admin/setup/priority-accounts).</span></span> |
| <span data-ttu-id="660e7-139">用户</span><span class="sxs-lookup"><span data-stu-id="660e7-139">Users</span></span> | <span data-ttu-id="660e7-140">查看正在使用该应用的用户列表、他们是否是优先帐户，以及下载和上传的数据量。</span><span class="sxs-lookup"><span data-stu-id="660e7-140">See a list of users who are using the app, whether they are a priority account, and the amount of data downloaded and uploaded.</span></span> |
| <span data-ttu-id="660e7-141">权限</span><span class="sxs-lookup"><span data-stu-id="660e7-141">Permissions</span></span> | <span data-ttu-id="660e7-142">查看应用授予和使用的权限的摘要以及特定权限的列表。</span><span class="sxs-lookup"><span data-stu-id="660e7-142">See a summary of the permissions granted to and used by the app and the list of specific permissions.</span></span> <span data-ttu-id="660e7-143">有关详细信息，请参阅 [Microsoft Graph 权限参考](/graph/permissions-reference)。</span><span class="sxs-lookup"><span data-stu-id="660e7-143">See the [Microsoft Graph permissions reference](/graph/permissions-reference) for more information.</span></span> |
|||

<span data-ttu-id="660e7-144">对于已启用的应用，还有一个“**禁用应用**”控件和一个“**启用应用**”控件，前者用于禁用所选应用，后者用于启用已禁用应用。</span><span class="sxs-lookup"><span data-stu-id="660e7-144">For an enabled app, there is also a **Disable app** control to disable the use of the selected app and an **Enable app** control to enable the use of the disabled app.</span></span> <span data-ttu-id="660e7-145">这些操作需要以下[管理员角色](app-governance-get-started.md#administrator-roles)才能执行：</span><span class="sxs-lookup"><span data-stu-id="660e7-145">These actions require these [administrator roles](app-governance-get-started.md#administrator-roles):</span></span>

- <span data-ttu-id="660e7-146">合规管理员</span><span class="sxs-lookup"><span data-stu-id="660e7-146">Compliance Administrator</span></span>
- <span data-ttu-id="660e7-147">全局管理员</span><span class="sxs-lookup"><span data-stu-id="660e7-147">Global Administrator</span></span>
- <span data-ttu-id="660e7-148">安全管理员</span><span class="sxs-lookup"><span data-stu-id="660e7-148">Security Administrator</span></span>
- <span data-ttu-id="660e7-149">安全操作员</span><span class="sxs-lookup"><span data-stu-id="660e7-149">Security Operator</span></span>

## <a name="next-step"></a><span data-ttu-id="660e7-150">后续步骤</span><span class="sxs-lookup"><span data-stu-id="660e7-150">Next step</span></span>

<span data-ttu-id="660e7-151">[确定你的整体应用合规状况](app-governance-visibility-insights-compliance-posture.md)。</span><span class="sxs-lookup"><span data-stu-id="660e7-151">[Determine your overall app compliance posture](app-governance-visibility-insights-compliance-posture.md).</span></span>
