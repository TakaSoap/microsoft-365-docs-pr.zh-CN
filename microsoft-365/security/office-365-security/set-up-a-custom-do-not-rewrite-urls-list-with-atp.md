---
title: 使用 ATP 安全链接设置自定义"请勿重写 URL"列表
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: how-to
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
description: 了解如何为用户设置自定义阻止的 URL 以及不重写 Office 365 ATP 安全链接策略中的用户组 URL 列表。
ms.openlocfilehash: 9ec9c92e038aee33c716405916df009e3f4c60c5
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "46825229"
---
# <a name="set-up-a-custom-do-not-rewrite-urls-list-using-atp-safe-links"></a><span data-ttu-id="1d89c-103">使用 ATP 安全链接设置自定义"请勿重写 URL"列表</span><span class="sxs-lookup"><span data-stu-id="1d89c-103">Set up a custom do-not-rewrite URLs list using ATP Safe Links</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1d89c-104">本文适用于拥有 [Office 365 高级威胁防护](office-365-atp.md)的企业客户。</span><span class="sxs-lookup"><span data-stu-id="1d89c-104">This article is intended for business customers who have [Office 365 Advanced Threat Protection](office-365-atp.md).</span></span> <span data-ttu-id="1d89c-105">如果您是家庭用户，而您正在查找有关 Outlook 中安全链接的信息，请参阅"高级 [应用程序Outlook.com信息](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)"。</span><span class="sxs-lookup"><span data-stu-id="1d89c-105">If you are a home user looking for information about Safe Links in Outlook, see [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="1d89c-106">借 [用 Office 365 高级威胁防](office-365-atp.md) 护 (ATP) ，你的组织可能会具有 [自定义的阻止 URL，](set-up-a-custom-blocked-urls-list-atp.md)这样，当用户单击电子邮件中的 Web 地址 (URL) 或某些 Office 文档时，他们无法转到这些 URL。</span><span class="sxs-lookup"><span data-stu-id="1d89c-106">With [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP), your organization can have a [custom blocked URLs](set-up-a-custom-blocked-urls-list-atp.md), such that when people click on web addresses (URLs) in email messages or certain Office documents, they are prevented from going to those URLs.</span></span> <span data-ttu-id="1d89c-107">贵组织还可以为组织中特定组包含自定义"不重写"列表。</span><span class="sxs-lookup"><span data-stu-id="1d89c-107">Your organization can also have custom "do not rewrite" lists for specific groups in your organization.</span></span> <span data-ttu-id="1d89c-108">"不重写"列表让一些人们都可以访问通过其他方式在 Office 365 中的 ATP 安全链接[阻止的 URL。](atp-safe-links.md)</span><span class="sxs-lookup"><span data-stu-id="1d89c-108">A "do not rewrite" list enables some people to visit URLs that are otherwise blocked by [ATP Safe Links in Office 365](atp-safe-links.md).</span></span>

<span data-ttu-id="1d89c-109">本文介绍如何指定从 ATP 安全链接扫描中排除的 URL 列表以及需要注意的一些重要注意事项。</span><span class="sxs-lookup"><span data-stu-id="1d89c-109">This article describes how to specify a list of URLs that are excluded from ATP Safe Links scanning, and a few important points to keep in mind.</span></span>

> [!NOTE]
> <span data-ttu-id="1d89c-110">如果组织使用安全链接策略，则"请勿重写"列表是第三方网络钓鱼测试的唯一受支持方法。</span><span class="sxs-lookup"><span data-stu-id="1d89c-110">If your organization use Safe Links policies, the "do not rewrite" list is the only supported method for third party phishing tests.</span></span>

## <a name="set-up-a-do-not-rewrite-list"></a><span data-ttu-id="1d89c-111">设置"不重写"列表</span><span class="sxs-lookup"><span data-stu-id="1d89c-111">Set up a "do not rewrite" list</span></span>

<span data-ttu-id="1d89c-112">ATP 安全链接保护使用多个列表，其中包括你组织的阻止的 URL 列表和"不重写"列表用于异常。</span><span class="sxs-lookup"><span data-stu-id="1d89c-112">ATP Safe Links protection uses several lists, including your organization's blocked URLs list and the "do not rewrite" lists for exceptions.</span></span> <span data-ttu-id="1d89c-113">如果你具有必要权限，可以设置自定义"不要重写"列表。</span><span class="sxs-lookup"><span data-stu-id="1d89c-113">If you have the necessary permissions, you can set up your custom "do not rewrite" lists.</span></span> <span data-ttu-id="1d89c-114">当您添加或编辑应用于您组织中特定收件人的安全链接策略时，将执行此操作。</span><span class="sxs-lookup"><span data-stu-id="1d89c-114">You do this when you add or edit Safe Links policies that apply to specific recipients in your organization.</span></span>

<span data-ttu-id="1d89c-115">若要编辑 (定义) ATP 策略，必须分配有适当的角色。</span><span class="sxs-lookup"><span data-stu-id="1d89c-115">To edit (or define) ATP policies, you must be assigned an appropriate role.</span></span> <span data-ttu-id="1d89c-116">下表包含了一些示例。</span><span class="sxs-lookup"><span data-stu-id="1d89c-116">The following table includes some examples.</span></span> <span data-ttu-id="1d89c-117">若要了解详细信息，请参阅 [安全与合规中心&权限](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="1d89c-117">To learn more, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

|<span data-ttu-id="1d89c-118">Role</span><span class="sxs-lookup"><span data-stu-id="1d89c-118">Role</span></span>|<span data-ttu-id="1d89c-119">分配位置/分配方法</span><span class="sxs-lookup"><span data-stu-id="1d89c-119">Where/how assigned</span></span>|
|---|---|
|<span data-ttu-id="1d89c-120">全局管理员</span><span class="sxs-lookup"><span data-stu-id="1d89c-120">global administrator</span></span>|<span data-ttu-id="1d89c-121">注册以购买 Microsoft 365 的人员是默认管理员。</span><span class="sxs-lookup"><span data-stu-id="1d89c-121">The person who signs up to buy Microsoft 365 is a global admin by default.</span></span> <span data-ttu-id="1d89c-122"> (了解 [详细信息，请参阅 Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) 管理员角色) </span><span class="sxs-lookup"><span data-stu-id="1d89c-122">(See [About Microsoft 365 admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) to learn more.)</span></span>|
|<span data-ttu-id="1d89c-123">安全管理员</span><span class="sxs-lookup"><span data-stu-id="1d89c-123">Security Administrator</span></span>|<span data-ttu-id="1d89c-124">Azure Active Directory 管理中心 [https://aad.portal.azure.com](https://aad.portal.azure.com) () </span><span class="sxs-lookup"><span data-stu-id="1d89c-124">Azure Active Directory admin center ([https://aad.portal.azure.com](https://aad.portal.azure.com))</span></span>|
|<span data-ttu-id="1d89c-125">Exchange Online 组织管理</span><span class="sxs-lookup"><span data-stu-id="1d89c-125">Exchange Online Organization Management</span></span>|<span data-ttu-id="1d89c-126">Exchange 管理中心 [https://outlook.office365.com/ecp](https://outlook.office365.com/ecp) () </span><span class="sxs-lookup"><span data-stu-id="1d89c-126">Exchange admin center ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp))</span></span> <br><span data-ttu-id="1d89c-127">或</span><span class="sxs-lookup"><span data-stu-id="1d89c-127">or</span></span> <br>  <span data-ttu-id="1d89c-128">PowerShell cmdlet (请参阅 [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)) </span><span class="sxs-lookup"><span data-stu-id="1d89c-128">PowerShell cmdlets (See [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell))</span></span>|
|

> [!TIP]
> <span data-ttu-id="1d89c-129">若要了解有关角色和权限的详细信息，请参阅 [安全与合规中心&权限](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="1d89c-129">To learn more about roles and permissions, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

### <a name="to-view-or-edit-a-custom-do-not-rewrite-urls-list"></a><span data-ttu-id="1d89c-130">查看或编辑自定义"不重写"URL 列表的方法</span><span class="sxs-lookup"><span data-stu-id="1d89c-130">To view or edit a custom "do not rewrite" URLs list</span></span>

1. <span data-ttu-id="1d89c-131">转到 [https://protection.office.com](https://protection.office.com) 工作或学校帐户并进行登录。</span><span class="sxs-lookup"><span data-stu-id="1d89c-131">Go to [https://protection.office.com](https://protection.office.com) and sign in with your work or school account.</span></span>

2. <span data-ttu-id="1d89c-132">在左侧导航中的"威 **胁管理** \> **策略安全** \> **链接"下**。</span><span class="sxs-lookup"><span data-stu-id="1d89c-132">In the left navigation, under **Threat management** \> **Policy** \> **Safe Links**.</span></span>

3. <span data-ttu-id="1d89c-133">在" **适用于特定收件人的策略"** 部分中， (**新建** "按钮将与 **+** () ) 类似 () ) ，以创建新策略。</span><span class="sxs-lookup"><span data-stu-id="1d89c-133">In the **Policies that apply to specific recipients** section, choose **New** (the New button resembles a plus sign ( **+**)) to create a new policy.</span></span> <span data-ttu-id="1d89c-134"> (选，可以编辑现有的 policy.) </span><span class="sxs-lookup"><span data-stu-id="1d89c-134">(Alternatively, you can edit an existing policy.)</span></span><br/><span data-ttu-id="1d89c-135">![选择"新建"为特定电子邮件收件人添加安全链接策略](../../media/01073f42-3cec-4ddb-8c10-4d33ec434676.png)</span><span class="sxs-lookup"><span data-stu-id="1d89c-135">![Choose New to add a Safe Links policy for specific email recipients](../../media/01073f42-3cec-4ddb-8c10-4d33ec434676.png)</span></span>

4. <span data-ttu-id="1d89c-136">为策略指定名称和说明。</span><span class="sxs-lookup"><span data-stu-id="1d89c-136">Specify a name and description for your policy.</span></span>

5. <span data-ttu-id="1d89c-137">当用户 **单击** 链接时，将重写 ON URL 并对它检查已知恶意链接列表。</span><span class="sxs-lookup"><span data-stu-id="1d89c-137">Turn **ON** URLs will be rewritten and checked against a list of known malicious links when user clicks on the link.</span></span>

6. <span data-ttu-id="1d89c-138">在" **不重写以下 URL"** 部分，选择 **"输入有效的 URL"框，** 输入 URL，然后选择加号 (+) 。</span><span class="sxs-lookup"><span data-stu-id="1d89c-138">In the **Do not rewrite the following URLs** section, select the **Enter a valid URL** box, enter a URL, and then choose the plus sign (+).</span></span>

7. <span data-ttu-id="1d89c-139">在" **适用于"** 部分中， **选择"收件人为以下**组的成员"，然后选择要在 (的组) 你要包括在策略中的组。</span><span class="sxs-lookup"><span data-stu-id="1d89c-139">In the **Applied To** section, choose **The recipient is a member of**, and then choose the group(s) you want to include in your policy.</span></span> <span data-ttu-id="1d89c-140">选择 **'添加**'，然后选择'**确定'。**</span><span class="sxs-lookup"><span data-stu-id="1d89c-140">Choose **Add**, and then choose **OK**.</span></span>

8. <span data-ttu-id="1d89c-141">添加完 URL 后，在屏幕右下角选择"保存 **"。**</span><span class="sxs-lookup"><span data-stu-id="1d89c-141">When you are finished adding URLs, in the lower right corner of the screen, choose **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="1d89c-142">务必查看组织的阻止 URL 的自定义列表。</span><span class="sxs-lookup"><span data-stu-id="1d89c-142">Make sure to review your organization's custom list of blocked URLs.</span></span> <span data-ttu-id="1d89c-143">请参阅 [使用 ATP 安全链接设置自定义已阻止 URL 列表](set-up-a-custom-blocked-urls-list-atp.md)。</span><span class="sxs-lookup"><span data-stu-id="1d89c-143">See [Set up a custom blocked URLs list using ATP Safe Links](set-up-a-custom-blocked-urls-list-atp.md).</span></span>

## <a name="important-points-to-keep-in-mind"></a><span data-ttu-id="1d89c-144">需要记住的重要要点</span><span class="sxs-lookup"><span data-stu-id="1d89c-144">Important points to keep in mind</span></span>

- <span data-ttu-id="1d89c-145">"不要重写"列表中指定的任何 URL 都将从用于指定收件人的 ATP 安全链接扫描中排除。</span><span class="sxs-lookup"><span data-stu-id="1d89c-145">Any URLs that you specify in the "do not rewrite" list are excluded from ATP Safe Links scanning for the recipients that you specify.</span></span>

- <span data-ttu-id="1d89c-146">请考虑将常用内部 URL 添加到"不重写"列表中以改善用户体验。</span><span class="sxs-lookup"><span data-stu-id="1d89c-146">Consider adding commonly used internal URLs to the "do not rewrite" list to improve the user experience.</span></span> <span data-ttu-id="1d89c-147">例如，如果拥有本地服务，如 Skype for Business 或 Sharepoint，则可将其 URL 添加到列表中以将其排除在扫描中。</span><span class="sxs-lookup"><span data-stu-id="1d89c-147">For example, if you have on-premises services, such as Skype for Business or Sharepoint, you can add their URLs to the list to exclude them from scanning.</span></span>

- <span data-ttu-id="1d89c-148">如果您的"不重写"列表中已有 URL 的列表，请确保查看该列表，并根据需要添加通配符。</span><span class="sxs-lookup"><span data-stu-id="1d89c-148">If you already have a list of URLs in your "do not rewrite" list, make sure to review that list and add wildcards as appropriate.</span></span> <span data-ttu-id="1d89c-149">例如，如果现有列表具有类似条目，并且你想要在策略中包含子 `https://contoso.com/a` 路径 `https://contoso.com/a/b` ，请向条目添加通配符，使其看起来像 `https://contoso.com/a/*` 。</span><span class="sxs-lookup"><span data-stu-id="1d89c-149">For example, if your existing list has an entry like `https://contoso.com/a` and you want to include subpaths like `https://contoso.com/a/b` in your policy, add a wildcard to your entry so it looks like `https://contoso.com/a/*`.</span></span>

- <span data-ttu-id="1d89c-150">如果为 ATP 安全链接策略指定"不重写"列表，可以包括最多三个通配 \* () 。</span><span class="sxs-lookup"><span data-stu-id="1d89c-150">When you specify a "do not rewrite" list for an ATP Safe Links policy, you can include up to three wildcards (\*).</span></span> <span data-ttu-id="1d89c-151">通配符明确包含前缀或子域。</span><span class="sxs-lookup"><span data-stu-id="1d89c-151">Wildcards explicitly include prefixes or subdomains.</span></span> <span data-ttu-id="1d89c-152">例如，条目 `contoso.com` 与其他选项不同 `*.contoso.com/*` ， `*.contoso.com/*` 因为允许用户访问指定域中的子域和路径。</span><span class="sxs-lookup"><span data-stu-id="1d89c-152">For example, the entry `contoso.com` is not the same as `*.contoso.com/*`, because `*.contoso.com/*` allows people to visit subdomains and paths in the specified domain.</span></span>

<span data-ttu-id="1d89c-153">下表列出了您可以输入内容的示例，以及这些条目产生了什么影响。</span><span class="sxs-lookup"><span data-stu-id="1d89c-153">The following table lists examples of what you can enter and what effect those entries have.</span></span>

****

|<span data-ttu-id="1d89c-154">示例条目</span><span class="sxs-lookup"><span data-stu-id="1d89c-154">Example Entry</span></span>|<span data-ttu-id="1d89c-155">功能</span><span class="sxs-lookup"><span data-stu-id="1d89c-155">What It Does</span></span>|
|---|---|
|`contoso.com`|<span data-ttu-id="1d89c-156">允许收件人访问类似子域 `https://contoso.com` 或路径的站点。</span><span class="sxs-lookup"><span data-stu-id="1d89c-156">Allows recipients to visit a site like `https://contoso.com` but not subdomains or paths.</span></span>|
|`*.contoso.com/*`|<span data-ttu-id="1d89c-157">允许收件人访问域、子域和路径，例如 `https://www.contoso.com` `https://www.contoso.com` `https://maps.contoso.com` ，，，或 `https://www.contoso.com/a` 。</span><span class="sxs-lookup"><span data-stu-id="1d89c-157">Allows recipients to visit a domain, subdomains, and paths, such as `https://www.contoso.com`, `https://www.contoso.com`, `https://maps.contoso.com`, or `https://www.contoso.com/a`.</span></span> <br/><br/> <span data-ttu-id="1d89c-158">此条目本身就更加优 `*contoso.com*` ，因为它不包含潜在的恶意站点（如或 `https://www.falsecontoso.com``https://www.false.contoso.completelyfalse.com`</span><span class="sxs-lookup"><span data-stu-id="1d89c-158">This entry is inherently better than `*contoso.com*`, because it doesn't include potentially fraudulent sites, like `https://www.falsecontoso.com` or `https://www.false.contoso.completelyfalse.com`</span></span>|
|`https://contoso.com/a`|<span data-ttu-id="1d89c-159">允许特定收件人访问类似网站（如 `https://contoso.com/a` ），但不允许子路径访问 `https://contoso.com/a/b`</span><span class="sxs-lookup"><span data-stu-id="1d89c-159">Allows specific recipients to visit a site like `https://contoso.com/a`, but not subpaths like `https://contoso.com/a/b`</span></span>|
|`https://contoso.com/a/*`|<span data-ttu-id="1d89c-160">允许特定收件人访问类似网站和 `https://contoso.com/a` 子路径 `https://contoso.com/a/b`</span><span class="sxs-lookup"><span data-stu-id="1d89c-160">Allows specific recipients to visit a site like `https://contoso.com/a` and subpaths like `https://contoso.com/a/b`</span></span>|
|
