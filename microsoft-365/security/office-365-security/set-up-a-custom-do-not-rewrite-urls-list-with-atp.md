---
title: 使用 ATP 安全链接设置自定义不重写 Url 列表
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: article
ms.date: ''
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 35dbfd99-da5a-422b-9b0e-c6caf3b645fa
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 了解如何为 Office 365 ATP 安全链接策略中的用户组设置用户的自定义已阻止 Url 和不重写的 Url 列表。
ms.openlocfilehash: 7909e91b96f8bdbc38ffdceafe11fa47f5ebe897
ms.sourcegitcommit: fa8e488936a36e4b56e1252cb4061b5bd6c0eafc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/13/2020
ms.locfileid: "46656965"
---
# <a name="set-up-a-custom-do-not-rewrite-urls-list-using-atp-safe-links"></a><span data-ttu-id="2de16-103">使用 ATP 安全链接设置自定义不重写 Url 列表</span><span class="sxs-lookup"><span data-stu-id="2de16-103">Set up a custom do-not-rewrite URLs list using ATP Safe Links</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2de16-104">本文适用于拥有 [Office 365 高级威胁防护](office-365-atp.md)的企业客户。</span><span class="sxs-lookup"><span data-stu-id="2de16-104">This article is intended for business customers who have [Office 365 Advanced Threat Protection](office-365-atp.md).</span></span> <span data-ttu-id="2de16-105">如果您是在 Outlook 中查找有关安全链接的信息的家庭用户，请参阅[Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)。</span><span class="sxs-lookup"><span data-stu-id="2de16-105">If you are a home user looking for information about Safe Links in Outlook, see [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="2de16-106">使用[Office 365 高级威胁防护](office-365-atp.md) (ATP) ，您的组织可以有一个[自定义的被阻止的 url](set-up-a-custom-blocked-urls-list-atp.md)，这样，当用户单击电子邮件中的 Web 地址 () url 或某些 Office 文档时，将阻止这些 Url 转到这些 url。</span><span class="sxs-lookup"><span data-stu-id="2de16-106">With [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP), your organization can have a [custom blocked URLs](set-up-a-custom-blocked-urls-list-atp.md), such that when people click on web addresses (URLs) in email messages or certain Office documents, they are prevented from going to those URLs.</span></span> <span data-ttu-id="2de16-107">您的组织还可以为组织中的特定组提供自定义的 "不重写" 列表。</span><span class="sxs-lookup"><span data-stu-id="2de16-107">Your organization can also have custom "do not rewrite" lists for specific groups in your organization.</span></span> <span data-ttu-id="2de16-108">"不重写" 列表使某些用户能够访问由[Office 365 中的 ATP 安全链接](atp-safe-links.md)阻止的 url。</span><span class="sxs-lookup"><span data-stu-id="2de16-108">A "do not rewrite" list enables some people to visit URLs that are otherwise blocked by [ATP Safe Links in Office 365](atp-safe-links.md).</span></span>

<span data-ttu-id="2de16-109">本文介绍如何指定从 ATP 安全链接扫描中排除的 Url 的列表，以及需要牢记的几个重要事项。</span><span class="sxs-lookup"><span data-stu-id="2de16-109">This article describes how to specify a list of URLs that are excluded from ATP Safe Links scanning, and a few important points to keep in mind.</span></span>

## <a name="set-up-a-do-not-rewrite-list"></a><span data-ttu-id="2de16-110">设置 "不重写" 列表</span><span class="sxs-lookup"><span data-stu-id="2de16-110">Set up a "do not rewrite" list</span></span>

<span data-ttu-id="2de16-111">ATP 安全链接保护使用多个列表，包括组织的阻止 Url 列表和 "不重写" 列表中的例外。</span><span class="sxs-lookup"><span data-stu-id="2de16-111">ATP Safe Links protection uses several lists, including your organization's blocked URLs list and the "do not rewrite" lists for exceptions.</span></span> <span data-ttu-id="2de16-112">如果您具有必要的权限，则可以设置自定义的 "不重写" 列表。</span><span class="sxs-lookup"><span data-stu-id="2de16-112">If you have the necessary permissions, you can set up your custom "do not rewrite" lists.</span></span> <span data-ttu-id="2de16-113">在添加或编辑适用于组织中特定收件人的安全链接策略时，可以执行此操作。</span><span class="sxs-lookup"><span data-stu-id="2de16-113">You do this when you add or edit Safe Links policies that apply to specific recipients in your organization.</span></span>

<span data-ttu-id="2de16-114">若要编辑 (或定义) ATP 策略，必须为您分配适当的角色。</span><span class="sxs-lookup"><span data-stu-id="2de16-114">To edit (or define) ATP policies, you must be assigned an appropriate role.</span></span> <span data-ttu-id="2de16-115">下表包括一些示例。</span><span class="sxs-lookup"><span data-stu-id="2de16-115">The following table includes some examples.</span></span> <span data-ttu-id="2de16-116">若要了解详细信息，请参阅[安全性 & 合规性中心中的权限](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="2de16-116">To learn more, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

|<span data-ttu-id="2de16-117">Role</span><span class="sxs-lookup"><span data-stu-id="2de16-117">Role</span></span>|<span data-ttu-id="2de16-118">分配的位置/方式</span><span class="sxs-lookup"><span data-stu-id="2de16-118">Where/how assigned</span></span>|
|---|---|
|<span data-ttu-id="2de16-119">全局管理员</span><span class="sxs-lookup"><span data-stu-id="2de16-119">global administrator</span></span>|<span data-ttu-id="2de16-120">默认情况下，注册购买 Microsoft 365 的人是全局管理员。</span><span class="sxs-lookup"><span data-stu-id="2de16-120">The person who signs up to buy Microsoft 365 is a global admin by default.</span></span> <span data-ttu-id="2de16-121"> (参阅[关于 Microsoft 365 管理员角色](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)，了解详细信息。 ) </span><span class="sxs-lookup"><span data-stu-id="2de16-121">(See [About Microsoft 365 admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) to learn more.)</span></span>|
|<span data-ttu-id="2de16-122">安全管理员</span><span class="sxs-lookup"><span data-stu-id="2de16-122">Security Administrator</span></span>|<span data-ttu-id="2de16-123">Azure Active Directory 管理员中心 ([https://aad.portal.azure.com](https://aad.portal.azure.com)) </span><span class="sxs-lookup"><span data-stu-id="2de16-123">Azure Active Directory admin center ([https://aad.portal.azure.com](https://aad.portal.azure.com))</span></span>|
|<span data-ttu-id="2de16-124">Exchange Online 组织管理</span><span class="sxs-lookup"><span data-stu-id="2de16-124">Exchange Online Organization Management</span></span>|<span data-ttu-id="2de16-125">Exchange 管理中心 ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) </span><span class="sxs-lookup"><span data-stu-id="2de16-125">Exchange admin center ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp))</span></span> <br><span data-ttu-id="2de16-126">或</span><span class="sxs-lookup"><span data-stu-id="2de16-126">or</span></span> <br>  <span data-ttu-id="2de16-127">PowerShell cmdlet (参阅[Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)) </span><span class="sxs-lookup"><span data-stu-id="2de16-127">PowerShell cmdlets (See [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell))</span></span>|
|

> [!TIP]
> <span data-ttu-id="2de16-128">若要了解有关角色和权限的详细信息，请参阅[Security & 合规性中心中的权限](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="2de16-128">To learn more about roles and permissions, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

### <a name="to-view-or-edit-a-custom-do-not-rewrite-urls-list"></a><span data-ttu-id="2de16-129">查看或编辑自定义 "不重写" Url 列表</span><span class="sxs-lookup"><span data-stu-id="2de16-129">To view or edit a custom "do not rewrite" URLs list</span></span>

1. <span data-ttu-id="2de16-130">转到 [https://protection.office.com](https://protection.office.com) 并使用你的工作或学校帐户登录。</span><span class="sxs-lookup"><span data-stu-id="2de16-130">Go to [https://protection.office.com](https://protection.office.com) and sign in with your work or school account.</span></span>

2. <span data-ttu-id="2de16-131">在左侧导航中的 "**威胁管理** \> **策略** \> **安全链接**" 下。</span><span class="sxs-lookup"><span data-stu-id="2de16-131">In the left navigation, under **Threat management** \> **Policy** \> **Safe Links**.</span></span>

3. <span data-ttu-id="2de16-132">在 "**适用于特定收件人的策略**" 部分中，选择 "**新建**" (新按钮类似于加号 ( **+**) # A3 以创建新策略。</span><span class="sxs-lookup"><span data-stu-id="2de16-132">In the **Policies that apply to specific recipients** section, choose **New** (the New button resembles a plus sign ( **+**)) to create a new policy.</span></span> <span data-ttu-id="2de16-133"> (此外，还可以编辑现有策略。 ) </span><span class="sxs-lookup"><span data-stu-id="2de16-133">(Alternatively, you can edit an existing policy.)</span></span><br/><span data-ttu-id="2de16-134">![选择 "新建" 为特定的电子邮件收件人添加安全链接策略](../../media/01073f42-3cec-4ddb-8c10-4d33ec434676.png)</span><span class="sxs-lookup"><span data-stu-id="2de16-134">![Choose New to add a Safe Links policy for specific email recipients](../../media/01073f42-3cec-4ddb-8c10-4d33ec434676.png)</span></span>

4. <span data-ttu-id="2de16-135">为策略指定名称和说明。</span><span class="sxs-lookup"><span data-stu-id="2de16-135">Specify a name and description for your policy.</span></span>

5. <span data-ttu-id="2de16-136">当用户单击链接时，将会重写并**检查 url 的**已知恶意链接列表。</span><span class="sxs-lookup"><span data-stu-id="2de16-136">Turn **ON** URLs will be rewritten and checked against a list of known malicious links when user clicks on the link.</span></span>

6. <span data-ttu-id="2de16-137">在 "**不重写以下 url"** 部分，选择 "**输入一个有效的 url** " 框，输入一个 url，然后选择加号 (+) 。</span><span class="sxs-lookup"><span data-stu-id="2de16-137">In the **Do not rewrite the following URLs** section, select the **Enter a valid URL** box, enter a URL, and then choose the plus sign (+).</span></span>

7. <span data-ttu-id="2de16-138">在 "**应用**于" 部分中，选择 **"收件人是其成员**"，然后选择要在策略中包括的组 (s) 。</span><span class="sxs-lookup"><span data-stu-id="2de16-138">In the **Applied To** section, choose **The recipient is a member of**, and then choose the group(s) you want to include in your policy.</span></span> <span data-ttu-id="2de16-139">选择 "**添加**"，然后选择 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="2de16-139">Choose **Add**, and then choose **OK**.</span></span>

8. <span data-ttu-id="2de16-140">添加完 Url 后，在屏幕的右下角，选择 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="2de16-140">When you are finished adding URLs, in the lower right corner of the screen, choose **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="2de16-141">请务必查看您的组织的已阻止 Url 的自定义列表。</span><span class="sxs-lookup"><span data-stu-id="2de16-141">Make sure to review your organization's custom list of blocked URLs.</span></span> <span data-ttu-id="2de16-142">请参阅[使用 ATP 安全链接设置自定义阻止的 url 列表](set-up-a-custom-blocked-urls-list-atp.md)。</span><span class="sxs-lookup"><span data-stu-id="2de16-142">See [Set up a custom blocked URLs list using ATP Safe Links](set-up-a-custom-blocked-urls-list-atp.md).</span></span>

## <a name="important-points-to-keep-in-mind"></a><span data-ttu-id="2de16-143">需要牢记的要点</span><span class="sxs-lookup"><span data-stu-id="2de16-143">Important points to keep in mind</span></span>

- <span data-ttu-id="2de16-144">您在 "不重写" 列表中指定的任何 Url 将从 ATP 安全链接扫描中排除，用于您指定的收件人。</span><span class="sxs-lookup"><span data-stu-id="2de16-144">Any URLs that you specify in the "do not rewrite" list are excluded from ATP Safe Links scanning for the recipients that you specify.</span></span>

- <span data-ttu-id="2de16-145">请考虑将常用的内部 Url 添加到 "不重写" 列表中，以改善用户体验。</span><span class="sxs-lookup"><span data-stu-id="2de16-145">Consider adding commonly used internal URLs to the "do not rewrite" list to improve the user experience.</span></span> <span data-ttu-id="2de16-146">例如，如果您有本地服务（如 Skype for Business 或 Sharepoint），则可以将其 Url 添加到列表中，以将其排除在扫描之外。</span><span class="sxs-lookup"><span data-stu-id="2de16-146">For example, if you have on-premises services, such as Skype for Business or Sharepoint, you can add their URLs to the list to exclude them from scanning.</span></span>

- <span data-ttu-id="2de16-147">如果您在 "不重写" 列表中已经有 Url 列表，请务必查看该列表并根据需要添加通配符。</span><span class="sxs-lookup"><span data-stu-id="2de16-147">If you already have a list of URLs in your "do not rewrite" list, make sure to review that list and add wildcards as appropriate.</span></span> <span data-ttu-id="2de16-148">例如，如果您的现有列表中有类似的条目， `https://contoso.com/a` 并且您希望 `https://contoso.com/a/b` 在策略中包含类似的子路径，请将通配符添加到您的条目，使其看起来像这样 `https://contoso.com/a/*` 。</span><span class="sxs-lookup"><span data-stu-id="2de16-148">For example, if your existing list has an entry like `https://contoso.com/a` and you want to include subpaths like `https://contoso.com/a/b` in your policy, add a wildcard to your entry so it looks like `https://contoso.com/a/*`.</span></span>

- <span data-ttu-id="2de16-149">当您为 ATP 安全链接策略指定 "不重写" 列表时，最长可包含三个通配符 (\*) 。</span><span class="sxs-lookup"><span data-stu-id="2de16-149">When you specify a "do not rewrite" list for an ATP Safe Links policy, you can include up to three wildcards (\*).</span></span> <span data-ttu-id="2de16-150">通配符显式包含前缀或子域。</span><span class="sxs-lookup"><span data-stu-id="2de16-150">Wildcards explicitly include prefixes or subdomains.</span></span> <span data-ttu-id="2de16-151">例如，输入项与 `contoso.com` 不同 `*.contoso.com/*` ，因为 `*.contoso.com/*` 允许用户访问指定域中的子域和路径。</span><span class="sxs-lookup"><span data-stu-id="2de16-151">For example, the entry `contoso.com` is not the same as `*.contoso.com/*`, because `*.contoso.com/*` allows people to visit subdomains and paths in the specified domain.</span></span>

<span data-ttu-id="2de16-152">下表列出了可以输入的内容的示例以及这些项有何影响。</span><span class="sxs-lookup"><span data-stu-id="2de16-152">The following table lists examples of what you can enter and what effect those entries have.</span></span>

****

|<span data-ttu-id="2de16-153">示例条目</span><span class="sxs-lookup"><span data-stu-id="2de16-153">Example Entry</span></span>|<span data-ttu-id="2de16-154">功能</span><span class="sxs-lookup"><span data-stu-id="2de16-154">What It Does</span></span>|
|---|---|
|`contoso.com`|<span data-ttu-id="2de16-155">允许收件人访问的网站（如 `https://contoso.com` 不是子域或路径）。</span><span class="sxs-lookup"><span data-stu-id="2de16-155">Allows recipients to visit a site like `https://contoso.com` but not subdomains or paths.</span></span>|
|`*.contoso.com/*`|<span data-ttu-id="2de16-156">允许收件人访问域、子域和路径，例如 `https://www.contoso.com` 、、 `https://www.contoso.com` `https://maps.contoso.com` 或 `https://www.contoso.com/a` 。</span><span class="sxs-lookup"><span data-stu-id="2de16-156">Allows recipients to visit a domain, subdomains, and paths, such as `https://www.contoso.com`, `https://www.contoso.com`, `https://maps.contoso.com`, or `https://www.contoso.com/a`.</span></span> <br/><br/> <span data-ttu-id="2de16-157">此条目的本质上优于 `*contoso.com*` ，因为它不包含潜在的欺诈网站，如 `https://www.falsecontoso.com` 或`https://www.false.contoso.completelyfalse.com`</span><span class="sxs-lookup"><span data-stu-id="2de16-157">This entry is inherently better than `*contoso.com*`, because it doesn't include potentially fraudulent sites, like `https://www.falsecontoso.com` or `https://www.false.contoso.completelyfalse.com`</span></span>|
|`https://contoso.com/a`|<span data-ttu-id="2de16-158">允许特定收件人访问类似的网站 `https://contoso.com/a` ，但不允许像这样的子路径`https://contoso.com/a/b`</span><span class="sxs-lookup"><span data-stu-id="2de16-158">Allows specific recipients to visit a site like `https://contoso.com/a`, but not subpaths like `https://contoso.com/a/b`</span></span>|
|`https://contoso.com/a/*`|<span data-ttu-id="2de16-159">允许特定收件人访问像这样的子 `https://contoso.com/a` 网站之类的子网站`https://contoso.com/a/b`</span><span class="sxs-lookup"><span data-stu-id="2de16-159">Allows specific recipients to visit a site like `https://contoso.com/a` and subpaths like `https://contoso.com/a/b`</span></span>|
|
