---
title: 组命名策略
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MST160
- MET150
- MOE150
ms.assetid: 6ceca4d3-cad1-4532-9f0f-d469dfbbb552
description: 了解如何为 Microsoft 365 组创建命名策略。
ms.openlocfilehash: 2d8b016e0830f0d20ea6fb6227dd7789878bfc94
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/21/2020
ms.locfileid: "43630439"
---
# <a name="groups-naming-policy"></a><span data-ttu-id="29d7c-103">组命名策略</span><span class="sxs-lookup"><span data-stu-id="29d7c-103">Groups naming policy</span></span>

<span data-ttu-id="29d7c-104">您可以使用组命名策略为组织中的用户创建的组强制实施一致的命名策略。</span><span class="sxs-lookup"><span data-stu-id="29d7c-104">You use a group naming policy to enforce a consistent naming strategy for groups created by users in your organization.</span></span> <span data-ttu-id="29d7c-105">命名策略可帮助您和您的用户标识组、成员身份、地理区域或创建组的用户的功能。</span><span class="sxs-lookup"><span data-stu-id="29d7c-105">A naming policy can help you and your users identify the function of the group, membership, geographic region, or who created the group.</span></span> <span data-ttu-id="29d7c-106">命名策略还有助于对通讯簿中的组进行分类。</span><span class="sxs-lookup"><span data-stu-id="29d7c-106">The naming policy can also help categorize groups in the address book.</span></span> <span data-ttu-id="29d7c-107">您可以使用该策略阻止在组名称和别名中使用特定字词。</span><span class="sxs-lookup"><span data-stu-id="29d7c-107">You can use the policy to block specific words from being used in group names and aliases.</span></span>

<span data-ttu-id="29d7c-108">命名策略适用于跨所有组工作负载（如 Outlook、Microsoft 团队、SharePoint、Planner、Yammer 等）创建的组。</span><span class="sxs-lookup"><span data-stu-id="29d7c-108">The naming policy is applied to groups that are created across all groups workloads (like Outlook, Microsoft Teams, SharePoint, Planner, Yammer, etc.).</span></span> <span data-ttu-id="29d7c-109">它将应用于组名称和组别名。</span><span class="sxs-lookup"><span data-stu-id="29d7c-109">It gets applied to both the group name and group alias.</span></span> <span data-ttu-id="29d7c-110">当用户创建组时，或者在编辑现有组的组名称或别名时，将应用此方法。</span><span class="sxs-lookup"><span data-stu-id="29d7c-110">It gets applied when a user creates a group and when group name or alias is edited for an existing group.</span></span>

> [!TIP]
> <span data-ttu-id="29d7c-111">Microsoft 365 组命名策略仅适用于 Microsoft 365 组。</span><span class="sxs-lookup"><span data-stu-id="29d7c-111">A Microsoft 365 group naming policy only applies to Microsoft 365 groups.</span></span> <span data-ttu-id="29d7c-112">它不适用于 Exchange Online 中创建的通讯组。</span><span class="sxs-lookup"><span data-stu-id="29d7c-112">It doesn't apply to distribution groups created in Exchange Online.</span></span> <span data-ttu-id="29d7c-113">若要创建通讯组的命名策略，请参阅[创建通讯组命名策略](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-distribution-groups/create-group-naming-policy)。</span><span class="sxs-lookup"><span data-stu-id="29d7c-113">To create a naming policy for distribution groups, see [Create a distribution group naming policy](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-distribution-groups/create-group-naming-policy).</span></span>

<span data-ttu-id="29d7c-114">组命名策略包含以下功能：</span><span class="sxs-lookup"><span data-stu-id="29d7c-114">The group naming policy consists of the following features:</span></span>

- <span data-ttu-id="29d7c-115">**前缀后缀命名策略**：您可以使用前缀或后缀定义组的命名约定（例如： "US\_My Group\_工程"）。</span><span class="sxs-lookup"><span data-stu-id="29d7c-115">**Prefix-Suffix naming policy**: You can use prefixes or suffixes to define the naming convention of groups (for example: "US\_My Group\_Engineering").</span></span> <span data-ttu-id="29d7c-116">前缀/后缀可以是固定字符串或像 [部门] 这样的用户属性，将根据创建组的用户进行替换。</span><span class="sxs-lookup"><span data-stu-id="29d7c-116">The prefixes/suffixes can either be fixed strings or user attributes like [Department] that will get substituted based on the user who is creating the group.</span></span>

- <span data-ttu-id="29d7c-117">**自定义阻止的词**：您可以将特定于您的组织的一组阻止的词上载到用户创建的组中被阻止。</span><span class="sxs-lookup"><span data-stu-id="29d7c-117">**Custom Blocked Words**: You can upload a set of blocked words specific to your organization that would be blocked in groups created by users.</span></span> <span data-ttu-id="29d7c-118">（例如： "CEO，工资表，HR"）。</span><span class="sxs-lookup"><span data-stu-id="29d7c-118">(For example: "CEO, Payroll, HR").</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="29d7c-119">许可要求</span><span class="sxs-lookup"><span data-stu-id="29d7c-119">Licensing requirements</span></span>

<span data-ttu-id="29d7c-120">使用适用于 Microsoft 365 组的 Azure AD 命名策略时，需要拥有（但不一定）为属于一个或多个 Microsoft 365 组成员的每个唯一用户（包括来宾）分配 Azure Active Directory Premium P1 许可证或 Azure AD Basic EDU 许可证。</span><span class="sxs-lookup"><span data-stu-id="29d7c-120">Using Azure AD naming policy for Microsoft 365 groups requires that you possess but not necessarily assign an Azure Active Directory Premium P1 license or Azure AD Basic EDU license for each unique user (including guests) that is a member of one or more Microsoft 365 groups.</span></span>

<span data-ttu-id="29d7c-121">这对于创建组命名策略的管理员来说也是必需的。</span><span class="sxs-lookup"><span data-stu-id="29d7c-121">This is also required for the administrator that creates the Groups naming policy.</span></span>

## <a name="prefix-suffix-naming-policy"></a><span data-ttu-id="29d7c-122">前缀-后缀命名策略</span><span class="sxs-lookup"><span data-stu-id="29d7c-122">Prefix-Suffix naming policy</span></span>

<span data-ttu-id="29d7c-123">前缀和后缀可以是固定字符串，也可以是用户属性。</span><span class="sxs-lookup"><span data-stu-id="29d7c-123">Prefixes and suffixes can either be fixed strings or user attributes.</span></span>

### <a name="fixed-strings"></a><span data-ttu-id="29d7c-124">固定字符串</span><span class="sxs-lookup"><span data-stu-id="29d7c-124">Fixed strings</span></span>

<span data-ttu-id="29d7c-125">您可以使用简短字符串来帮助您区分 GAL 中的组和组工作负荷的左侧导航。</span><span class="sxs-lookup"><span data-stu-id="29d7c-125">You can use short strings that can help you differentiate groups in the GAL and left navigation of the group workloads.</span></span> <span data-ttu-id="29d7c-126">某些常用前缀后缀是关键字，如 "Grp\_Name"、"\#name"、"\_name"</span><span class="sxs-lookup"><span data-stu-id="29d7c-126">Some of the common prefixes suffixes are keywords like 'Grp\_Name' , '\#Name', '\_Name'</span></span>

### <a name="attributes"></a><span data-ttu-id="29d7c-127">属性</span><span class="sxs-lookup"><span data-stu-id="29d7c-127">Attributes</span></span>

<span data-ttu-id="29d7c-128">您可以使用可帮助标识创建组（如 [部门]）的用户以及从 [国家/地区] 创建组的位置的属性。</span><span class="sxs-lookup"><span data-stu-id="29d7c-128">You can use attributes that can help identify who created the group like [Department] and where it was created from like [Country].</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="29d7c-129">**示例**</span><span class="sxs-lookup"><span data-stu-id="29d7c-129">**Examples**</span></span>|<span data-ttu-id="29d7c-130">Policy = "GRP [个名] [部门]"</span><span class="sxs-lookup"><span data-stu-id="29d7c-130">Policy = "GRP [GroupName] [Department]"</span></span>|
||<span data-ttu-id="29d7c-131">用户所在的部门 = 工程</span><span class="sxs-lookup"><span data-stu-id="29d7c-131">User's department = Engineering</span></span>|
||<span data-ttu-id="29d7c-132">创建的组名称 = "GRP My Group 工程"</span><span class="sxs-lookup"><span data-stu-id="29d7c-132">Created group name = "GRP My Group Engineering"</span></span>|

<span data-ttu-id="29d7c-133">受支持的 Azure Active Directory （Azure AD）属性为 [部门]、[Company]、[Office]、[StateOrProvince]、[CountryOrRegion] 和 [Title]。</span><span class="sxs-lookup"><span data-stu-id="29d7c-133">Supported Azure Active Directory (Azure AD) attributes are [Department], [Company], [Office], [StateOrProvince], [CountryOrRegion], and [Title].</span></span>

- <span data-ttu-id="29d7c-134">不受支持的用户属性被视为固定字符串。</span><span class="sxs-lookup"><span data-stu-id="29d7c-134">Unsupported user attributes are considered as fixed strings.</span></span> <span data-ttu-id="29d7c-135">例如，</span><span class="sxs-lookup"><span data-stu-id="29d7c-135">E.g.</span></span> <span data-ttu-id="29d7c-136">"[邮政编码]"</span><span class="sxs-lookup"><span data-stu-id="29d7c-136">"[postalCode]"</span></span>

- <span data-ttu-id="29d7c-137">不支持扩展属性和自定义属性。</span><span class="sxs-lookup"><span data-stu-id="29d7c-137">Extension attributes and custom attributes aren't supported.</span></span>

<span data-ttu-id="29d7c-138">建议使用已为组织中的所有用户填充的值的属性，而不要使用具有较长值的属性。</span><span class="sxs-lookup"><span data-stu-id="29d7c-138">It's recommended that you use attributes that have values filled in for all users in your organization and don't use attributes that have longer values.</span></span>

### <a name="things-to-look-out-for"></a><span data-ttu-id="29d7c-139">要查看的内容</span><span class="sxs-lookup"><span data-stu-id="29d7c-139">Things to look out for</span></span>

- <span data-ttu-id="29d7c-140">在创建策略的过程中，总前缀和后缀字符串长度限制为53个字符。</span><span class="sxs-lookup"><span data-stu-id="29d7c-140">During policy creation, the total prefixes and suffixes string length is restricted to 53 characters.</span></span>

- <span data-ttu-id="29d7c-141">前缀和后缀可以包含组名和组别名中支持的特殊字符。</span><span class="sxs-lookup"><span data-stu-id="29d7c-141">Prefixes and suffixes can contain special characters supported in group name and group alias.</span></span> <span data-ttu-id="29d7c-142">当前缀和后缀包含在组别名中不允许的特殊字符时，它们仅应用于组名称。</span><span class="sxs-lookup"><span data-stu-id="29d7c-142">When the prefixes and suffixes contain special characters that are not allowed in the group alias, they are only applied to the group name.</span></span> <span data-ttu-id="29d7c-143">因此，在这种情况下，应用于组名称的前缀和后缀将不同于应用于组别名的前缀和后缀。</span><span class="sxs-lookup"><span data-stu-id="29d7c-143">So in this case, the prefixes and suffixes applied to group name would be different from the ones applied to the group alias.</span></span>

- <span data-ttu-id="29d7c-144">如果\#使用 Yammer Microsoft 365 连接的组，请避免在命名策略中使用以下字符： @、、 \[ \] \<、、和。 \></span><span class="sxs-lookup"><span data-stu-id="29d7c-144">If you are using Yammer Microsoft 365 connected groups, avoid using the following characters in your naming policy: @, \#, \[, \], \<, and \>.</span></span> <span data-ttu-id="29d7c-145">如果这些字符位于命名策略中，则常规 Yammer 用户将无法创建组。</span><span class="sxs-lookup"><span data-stu-id="29d7c-145">If these characters are in the naming policy, regular Yammer users will not be able to create groups.</span></span>

## <a name="custom-blocked-words"></a><span data-ttu-id="29d7c-146">自定义阻止的单词</span><span class="sxs-lookup"><span data-stu-id="29d7c-146">Custom blocked words</span></span>

<span data-ttu-id="29d7c-147">您可以输入将在组名称和别名中阻止的阻止单词的逗号分隔列表。</span><span class="sxs-lookup"><span data-stu-id="29d7c-147">You can enter a comma separated list of blocked words that will be blocked in group names and aliases.</span></span>

<span data-ttu-id="29d7c-148">不执行任何子字符串搜索;具体来说，用户输入名称和自定义阻止词之间的完全匹配是触发故障所必需的。</span><span class="sxs-lookup"><span data-stu-id="29d7c-148">No sub-string searches are carried out; specifically, an exact match between the user entered name and the custom blocked words is required to trigger a failure.</span></span> <span data-ttu-id="29d7c-149">不执行子字符串搜索，以便用户可以像 "类" 那样使用一些常见词语，即使 "ass" 是一个被阻止的词也是如此。</span><span class="sxs-lookup"><span data-stu-id="29d7c-149">Sub-string search isn't done so that users can use some of the common words like 'Class' even if 'ass' is a blocked word.</span></span>

<span data-ttu-id="29d7c-150">**要查看的内容**：</span><span class="sxs-lookup"><span data-stu-id="29d7c-150">**Things to look out for**:</span></span>

- <span data-ttu-id="29d7c-151">被阻止的单词不区分大小写。</span><span class="sxs-lookup"><span data-stu-id="29d7c-151">The blocked words are case-insensitive.</span></span>

- <span data-ttu-id="29d7c-152">当用户输入被阻止的单词时，组客户端将显示一条错误消息，其中包含被阻止的单词。</span><span class="sxs-lookup"><span data-stu-id="29d7c-152">When a user enters a blocked word, the group client will show an error message with the blocked word.</span></span>

- <span data-ttu-id="29d7c-153">使用的阻止词中没有字符限制。</span><span class="sxs-lookup"><span data-stu-id="29d7c-153">There are no character restrictions in the blocked words used.</span></span>

- <span data-ttu-id="29d7c-154">有5000个字的限制可被设置为阻止的词。</span><span class="sxs-lookup"><span data-stu-id="29d7c-154">There is a limit of 5000 words that can be set as blocked words.</span></span>

## <a name="admin-override"></a><span data-ttu-id="29d7c-155">管理员替代</span><span class="sxs-lookup"><span data-stu-id="29d7c-155">Admin override</span></span>

<span data-ttu-id="29d7c-156">在所有组的工作负荷和终结点上，在这些策略中免除了选择性管理员，以便他们可以使用这些阻止的词以及所需的命名约定创建组。</span><span class="sxs-lookup"><span data-stu-id="29d7c-156">Selective administrators are exempted from these policies, across all group workloads and endpoints, so that they can create groups with these blocked words and with their desired naming conventions.</span></span> <span data-ttu-id="29d7c-157">下面列出了从组命名策略中免除的管理员角色。</span><span class="sxs-lookup"><span data-stu-id="29d7c-157">The following are the list of administrator roles exempted from the group naming policy.</span></span>

- <span data-ttu-id="29d7c-158">全局管理员</span><span class="sxs-lookup"><span data-stu-id="29d7c-158">Global admin</span></span>

- <span data-ttu-id="29d7c-159">合作伙伴第1层支持</span><span class="sxs-lookup"><span data-stu-id="29d7c-159">Partner Tier 1 Support</span></span>

- <span data-ttu-id="29d7c-160">合作伙伴第2层支持</span><span class="sxs-lookup"><span data-stu-id="29d7c-160">Partner Tier 2 Support</span></span>

- <span data-ttu-id="29d7c-161">用户帐户管理员</span><span class="sxs-lookup"><span data-stu-id="29d7c-161">User account admin</span></span>

- <span data-ttu-id="29d7c-162">目录编写者</span><span class="sxs-lookup"><span data-stu-id="29d7c-162">Directory writers</span></span>

## <a name="how-to-set-up-the-naming-policy"></a><span data-ttu-id="29d7c-163">如何设置命名策略</span><span class="sxs-lookup"><span data-stu-id="29d7c-163">How to set up the naming policy</span></span>

<span data-ttu-id="29d7c-164">若要设置命名策略，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="29d7c-164">To set up a naming policy:</span></span>

1. <span data-ttu-id="29d7c-165">在 " [Azure Active Directory](https://aad.portal.azure.com)" 中的 "**管理**" 下，单击 "**组**"。</span><span class="sxs-lookup"><span data-stu-id="29d7c-165">In [Azure Active Directory](https://aad.portal.azure.com), under **Manage**, click **Groups**.</span></span>
2. <span data-ttu-id="29d7c-166">在 "**设置**" 下，单击 "**命名策略**"。</span><span class="sxs-lookup"><span data-stu-id="29d7c-166">Under **Settings**, click **Naming policy**.</span></span>
3. <span data-ttu-id="29d7c-167">选择 "**组命名策略**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="29d7c-167">Choose the **Group naming policy** tab.</span></span>
4. <span data-ttu-id="29d7c-168">在 "**当前策略**" 下，选择是否需要前缀或后缀，或者同时选择这两者，并选中相应的复选框。</span><span class="sxs-lookup"><span data-stu-id="29d7c-168">Under **Current policy**, choose if you want to require a prefix or suffix or both, and select the appropriate check boxes.</span></span>
5. <span data-ttu-id="29d7c-169">在每个行的**属性**和**字符串**中进行选择，然后指定属性或字符串。</span><span class="sxs-lookup"><span data-stu-id="29d7c-169">Choose between **Attribute** and **String** for each line and then specify the attribute or string.</span></span>
6. <span data-ttu-id="29d7c-170">添加所需的前缀和后缀后，单击 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="29d7c-170">When you have added the prefixes and suffixes that you need, click **Save**.</span></span>

![Azure Active Directory 中的组命名策略设置的屏幕截图](../../media/groups-naming-policy-azure.png)

> [!NOTE]
> <span data-ttu-id="29d7c-172">StaffHub 团队不遵循命名策略，但基础 Microsoft 365 组也不遵循命名策略。</span><span class="sxs-lookup"><span data-stu-id="29d7c-172">StaffHub teams do not follow the naming policy, but the underlying Microsoft 365 group does.</span></span> <span data-ttu-id="29d7c-173">StaffHub 团队名称不会应用前缀和后缀，也不会检查是否存在自定义阻止的单词。</span><span class="sxs-lookup"><span data-stu-id="29d7c-173">StaffHub team name does not apply the prefixes and suffixes and does not check for custom blocked words.</span></span> <span data-ttu-id="29d7c-174">但 StaffHub 确实应用了前缀和后缀并删除了基础 Microsoft 365 组中阻止的单词。</span><span class="sxs-lookup"><span data-stu-id="29d7c-174">But StaffHub does apply the prefixes and suffixes and removes blocked words from the underlying Microsoft 365 group.</span></span>

## <a name="more-articles-on-naming-policy"></a><span data-ttu-id="29d7c-175">有关命名策略的更多文章</span><span class="sxs-lookup"><span data-stu-id="29d7c-175">More articles on naming policy</span></span>

[<span data-ttu-id="29d7c-176">在 Azure Active Directory 中强制实施 Microsoft 365 组的命名策略</span><span class="sxs-lookup"><span data-stu-id="29d7c-176">Enforce a naming policy for Microsoft 365 groups in Azure Active Directory</span></span>](https://go.microsoft.com/fwlink/?linkid=868340)

[<span data-ttu-id="29d7c-177">用于配置组设置的 Azure Active Directory cmdlet</span><span class="sxs-lookup"><span data-stu-id="29d7c-177">Azure Active Directory cmdlets for configuring group settings</span></span>](https://go.microsoft.com/fwlink/?linkid=868341)
