---
title: Office 365 组命名策略
ms.reviewer: arvaradh
f1.keywords:
- NOCSH
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
description: 了解如何创建 Office 365 组的命名策略。
ms.openlocfilehash: 50ea076e22680a444cb9acf04466a7e7d052bb7a
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/24/2020
ms.locfileid: "42238082"
---
# <a name="office-365-groups-naming-policy"></a><span data-ttu-id="ba323-103">Office 365 组命名策略</span><span class="sxs-lookup"><span data-stu-id="ba323-103">Office 365 Groups naming policy</span></span>

<span data-ttu-id="ba323-104">您可以使用组命名策略为组织中的用户创建的组强制实施一致的命名策略。</span><span class="sxs-lookup"><span data-stu-id="ba323-104">You use a group naming policy to enforce a consistent naming strategy for groups created by users in your organization.</span></span> <span data-ttu-id="ba323-105">命名策略可帮助您和您的用户标识组、成员身份、地理区域或创建组的用户的功能。</span><span class="sxs-lookup"><span data-stu-id="ba323-105">A naming policy can help you and your users identify the function of the group, membership, geographic region, or who created the group.</span></span> <span data-ttu-id="ba323-106">命名策略还有助于对通讯簿中的组进行分类。</span><span class="sxs-lookup"><span data-stu-id="ba323-106">The naming policy can also help categorize groups in the address book.</span></span> <span data-ttu-id="ba323-107">您可以使用该策略阻止在组名称和别名中使用特定字词。</span><span class="sxs-lookup"><span data-stu-id="ba323-107">You can use the policy to block specific words from being used in group names and aliases.</span></span>

<span data-ttu-id="ba323-108">命名策略适用于跨所有组工作负荷（如 Outlook、Microsoft 团队、SharePoint、Planner、Yammer 等）创建的组。</span><span class="sxs-lookup"><span data-stu-id="ba323-108">The naming policy is applied to groups that are created across all groups workloads (like Outlook, Microsoft Teams, SharePoint, Planner, Yammer, etc).</span></span> <span data-ttu-id="ba323-109">它将应用于组名称和组别名。</span><span class="sxs-lookup"><span data-stu-id="ba323-109">It gets applied to both the group name and group alias.</span></span> <span data-ttu-id="ba323-110">当用户创建组时，或者在编辑现有组的组名称或别名时，将应用此方法。</span><span class="sxs-lookup"><span data-stu-id="ba323-110">It gets applied when a user creates a group and when group name or alias is edited for an existing group.</span></span>

> [!TIP]
> <span data-ttu-id="ba323-111">Office 365 组命名策略仅适用于 Office 365 组。</span><span class="sxs-lookup"><span data-stu-id="ba323-111">An Office 365 group naming policy only applies to Office 365 Groups.</span></span> <span data-ttu-id="ba323-112">它不适用于 Exchange Online 中创建的通讯组。</span><span class="sxs-lookup"><span data-stu-id="ba323-112">It doesn't apply to distribution groups created in Exchange Online.</span></span> <span data-ttu-id="ba323-113">若要创建通讯组的命名策略，请参阅[创建通讯组命名策略](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-distribution-groups/create-group-naming-policy)。</span><span class="sxs-lookup"><span data-stu-id="ba323-113">To create a naming policy for distribution groups, see [Create a distribution group naming policy](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-distribution-groups/create-group-naming-policy).</span></span>

<span data-ttu-id="ba323-114">组命名策略包含以下功能：</span><span class="sxs-lookup"><span data-stu-id="ba323-114">The group naming policy consists of the following features:</span></span>

- <span data-ttu-id="ba323-115">**前缀后缀命名策略**：可以使用前缀或后缀定义组的命名约定（例如： "GRP\_US\_My Group\_工程"）。</span><span class="sxs-lookup"><span data-stu-id="ba323-115">**Prefix-Suffix naming policy**: You can use prefixes or suffixes to define the naming convention of groups (for example: "GRP\_US\_My Group\_Engineering").</span></span> <span data-ttu-id="ba323-116">前缀/后缀可以是固定字符串或像 [部门] 这样的用户属性，将根据创建组的用户进行替换。</span><span class="sxs-lookup"><span data-stu-id="ba323-116">The prefixes/suffixes can either be fixed strings or user attributes like [Department] that will get substituted based on the user who is creating the group.</span></span>

- <span data-ttu-id="ba323-117">**自定义阻止的单词**：您可以将特定于其组织的一组阻止词上传到用户创建的组中被阻止。</span><span class="sxs-lookup"><span data-stu-id="ba323-117">**Custom Blocked Words**: You can upload a set of blocked words specific to their organization that would be blocked in groups created by users.</span></span> <span data-ttu-id="ba323-118">（例如： "CEO，工资表，HR"）。</span><span class="sxs-lookup"><span data-stu-id="ba323-118">(For example: "CEO, Payroll, HR").</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="ba323-119">许可要求</span><span class="sxs-lookup"><span data-stu-id="ba323-119">Licensing requirements</span></span>

<span data-ttu-id="ba323-120">使用适用于 Office 365 组的 Azure AD 命名策略时，需要为每个具有一个或多个 Office 365 组成员的唯一用户（包括来宾）分配 Azure Active Directory Premium P1 许可证或 Azure AD Basic EDU 许可证。</span><span class="sxs-lookup"><span data-stu-id="ba323-120">Using Azure AD naming policy for Office 365 groups requires that you possess but not necessarily assign an Azure Active Directory Premium P1 license or Azure AD Basic EDU license for each unique user (including guests) that is a member of one or more Office 365 groups.</span></span>
<span data-ttu-id="ba323-121">这对于创建组命名策略的管理员来说也是必需的。</span><span class="sxs-lookup"><span data-stu-id="ba323-121">This is also required for the administrator that creates the Groups naming policy.</span></span>

## <a name="prefix-suffix-naming-policy"></a><span data-ttu-id="ba323-122">前缀-后缀命名策略</span><span class="sxs-lookup"><span data-stu-id="ba323-122">Prefix-Suffix naming policy</span></span>

<span data-ttu-id="ba323-123">前缀和后缀可以是固定字符串，也可以是用户属性。</span><span class="sxs-lookup"><span data-stu-id="ba323-123">Prefixes and suffixes can either be fixed strings or user attributes.</span></span>

### <a name="fixed-strings"></a><span data-ttu-id="ba323-124">固定字符串</span><span class="sxs-lookup"><span data-stu-id="ba323-124">Fixed strings</span></span>

<span data-ttu-id="ba323-125">您可以使用简短字符串来帮助您区分 GAL 和组工作负荷的左侧导航组中的组。</span><span class="sxs-lookup"><span data-stu-id="ba323-125">You can use short strings that can help you differentiate groups in the GAL and Left nav of the group workloads.</span></span> <span data-ttu-id="ba323-126">某些常用前缀后缀是关键字，如 "Grp\_Name"、"\#name"、"\_name"</span><span class="sxs-lookup"><span data-stu-id="ba323-126">Some of the common prefixes suffixes are Keywords like 'Grp\_Name' , '\#Name', '\_Name'</span></span>

### <a name="attributes"></a><span data-ttu-id="ba323-127">属性</span><span class="sxs-lookup"><span data-stu-id="ba323-127">Attributes</span></span>

<span data-ttu-id="ba323-128">您可以使用可帮助标识创建组（如 [部门]）的用户以及从 [国家/地区] 创建组的位置的属性。</span><span class="sxs-lookup"><span data-stu-id="ba323-128">You can use attributes that can help identify who created the group like [Department] and where it was created from like [Country].</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="ba323-129">**示例**</span><span class="sxs-lookup"><span data-stu-id="ba323-129">**Examples**</span></span>|<span data-ttu-id="ba323-130">Policy = "GRP [个名] [部门]"</span><span class="sxs-lookup"><span data-stu-id="ba323-130">Policy = "GRP [GroupName] [Department]"</span></span>|
||<span data-ttu-id="ba323-131">用户所在的部门 = 工程</span><span class="sxs-lookup"><span data-stu-id="ba323-131">User's department = Engineering</span></span>|
||<span data-ttu-id="ba323-132">创建的组名称 = "GRP My Group 工程"</span><span class="sxs-lookup"><span data-stu-id="ba323-132">Created group name = "GRP My Group Engineering"</span></span>|

<span data-ttu-id="ba323-133">受支持的 Azure Active Directory （Azure AD）属性为 [部门]、[Company]、[Office]、[StateOrProvince]、[CountryOrRegion]、[标题]</span><span class="sxs-lookup"><span data-stu-id="ba323-133">Supported Azure Active Directory (Azure AD) attributes are [Department], [Company], [Office], [StateOrProvince], [CountryOrRegion], [Title]</span></span>

- <span data-ttu-id="ba323-134">不受支持的用户属性被视为固定字符串。</span><span class="sxs-lookup"><span data-stu-id="ba323-134">Unsupported user attributes are considered as fixed strings.</span></span> <span data-ttu-id="ba323-135">例如，</span><span class="sxs-lookup"><span data-stu-id="ba323-135">E.g.</span></span> <span data-ttu-id="ba323-136">"[邮政编码]"</span><span class="sxs-lookup"><span data-stu-id="ba323-136">"[postalCode]"</span></span>

- <span data-ttu-id="ba323-137">不支持扩展属性和自定义属性。</span><span class="sxs-lookup"><span data-stu-id="ba323-137">Extension attributes and custom attributes aren't supported.</span></span>

<span data-ttu-id="ba323-138">建议使用已为组织中的所有用户填充的值的属性，而不要使用具有较长值的属性。</span><span class="sxs-lookup"><span data-stu-id="ba323-138">It's recommended that you use attributes that have values filled in for all users in your organization and don't use attributes that have longer values.</span></span>

### <a name="things-to-look-out-for"></a><span data-ttu-id="ba323-139">要查看的内容</span><span class="sxs-lookup"><span data-stu-id="ba323-139">Things to look out for</span></span>

- <span data-ttu-id="ba323-140">在创建策略的过程中，总前缀和后缀字符串长度限制为53个字符。</span><span class="sxs-lookup"><span data-stu-id="ba323-140">During policy creation, the total prefixes and suffixes string length is restricted to 53 characters.</span></span>

- <span data-ttu-id="ba323-141">前缀和后缀可以包含组名和组别名中支持的特殊字符。</span><span class="sxs-lookup"><span data-stu-id="ba323-141">Prefixes and suffixes can contain special characters supported in group name and group alias.</span></span> <span data-ttu-id="ba323-142">当前缀和后缀包含在组别名中不允许的特殊字符时，它们将被删除并应用于组别名。</span><span class="sxs-lookup"><span data-stu-id="ba323-142">When the prefixes and suffixes contain special characters that are not allowed in the group alias, they are removed and applied to the group alias.</span></span> <span data-ttu-id="ba323-143">因此，在这种情况下，应用于组名称的前缀和后缀将不同于应用于组别名的前缀和后缀。</span><span class="sxs-lookup"><span data-stu-id="ba323-143">So in this case, the prefixes and suffixes applied to group name would be different from the ones applied to the group alias.</span></span>

- <span data-ttu-id="ba323-144">如果使用的是 Yammer Office 365 连接的组，请避免在命名策略中使用以下字符： @ \#、 \[、 \] \<、、和\>。</span><span class="sxs-lookup"><span data-stu-id="ba323-144">If you are using Yammer Office 365 connected groups, avoid using the following characters in your naming policy: @, \#, \[, \], \<, and \>.</span></span> <span data-ttu-id="ba323-145">如果这些字符位于命名策略中，则常规 Yammer 用户将无法创建组。</span><span class="sxs-lookup"><span data-stu-id="ba323-145">If these characters are in the naming policy, regular Yammer users will not be able to create groups.</span></span>

## <a name="custom-blocked-words"></a><span data-ttu-id="ba323-146">自定义阻止的单词</span><span class="sxs-lookup"><span data-stu-id="ba323-146">Custom blocked words</span></span>

<span data-ttu-id="ba323-147">您可以输入将在组名称和别名中阻止的阻止单词的逗号分隔列表。</span><span class="sxs-lookup"><span data-stu-id="ba323-147">You can enter a comma separated list of blocked words that will be blocked in group names and aliases.</span></span>

<span data-ttu-id="ba323-148">阻止的词检查是对用户输入的组名称完成的。</span><span class="sxs-lookup"><span data-stu-id="ba323-148">The blocked words check is done on the user entered group name.</span></span> <span data-ttu-id="ba323-149">因此，如果用户输入 "darnit"，而\_"prefix" 是命名策略，则\_"prefix darnit" 将失败。</span><span class="sxs-lookup"><span data-stu-id="ba323-149">So if user enters 'darnit' and 'Prefix\_' is the naming policy, 'Prefix\_darnit' will fail.</span></span>

<span data-ttu-id="ba323-150">不执行任何子字符串搜索;具体来说，用户输入名称和自定义阻止词之间的完全匹配是触发故障所必需的。</span><span class="sxs-lookup"><span data-stu-id="ba323-150">No sub-string searches are carried out; specifically, an exact match between the user entered name and the custom blocked words is required to trigger a failure.</span></span> <span data-ttu-id="ba323-151">不执行子字符串搜索，以便用户可以像 "类" 那样使用一些常见词语，即使 "ass" 是一个被阻止的词也是如此。</span><span class="sxs-lookup"><span data-stu-id="ba323-151">Sub-string search isn't done so that users can use some of the common words like 'Class' even if 'ass' is a blocked word.</span></span>

<span data-ttu-id="ba323-152">**要查看的内容**：</span><span class="sxs-lookup"><span data-stu-id="ba323-152">**Things to look out for**:</span></span>

- <span data-ttu-id="ba323-153">被阻止的单词不区分大小写。</span><span class="sxs-lookup"><span data-stu-id="ba323-153">The blocked words are case-insensitive.</span></span>

- <span data-ttu-id="ba323-154">当用户输入被阻止的单词时，组客户端将显示一条错误消息，其中包含被阻止的单词。</span><span class="sxs-lookup"><span data-stu-id="ba323-154">When a user enters a blocked word, the group client will show an error message with the blocked word.</span></span>

- <span data-ttu-id="ba323-155">使用的阻止词中没有字符限制。</span><span class="sxs-lookup"><span data-stu-id="ba323-155">There are no character restrictions in the blocked words used.</span></span>

- <span data-ttu-id="ba323-156">有5000个字的上限可被设置为阻止的单词。</span><span class="sxs-lookup"><span data-stu-id="ba323-156">There is an upper limit of 5000 words that can be set as blocked words.</span></span>

## <a name="admin-override"></a><span data-ttu-id="ba323-157">管理员替代</span><span class="sxs-lookup"><span data-stu-id="ba323-157">Admin override</span></span>

<span data-ttu-id="ba323-158">在所有组的工作负荷和终结点上，在这些策略中免除了选择性管理员，以便他们可以使用这些阻止的词以及所需的命名约定创建组。</span><span class="sxs-lookup"><span data-stu-id="ba323-158">Selective administrators are exempted from these policies, across all group workloads and endpoints, so that they can create groups with these blocked words and with their desired naming conventions.</span></span> <span data-ttu-id="ba323-159">下面列出了从组命名策略中免除的管理员角色。</span><span class="sxs-lookup"><span data-stu-id="ba323-159">The following are the list of administrator roles exempted from the group naming policy.</span></span>

- <span data-ttu-id="ba323-160">全局管理员</span><span class="sxs-lookup"><span data-stu-id="ba323-160">Global admin</span></span>

- <span data-ttu-id="ba323-161">合作伙伴第1层支持</span><span class="sxs-lookup"><span data-stu-id="ba323-161">Partner Tier 1 Support</span></span>

- <span data-ttu-id="ba323-162">合作伙伴第2层支持</span><span class="sxs-lookup"><span data-stu-id="ba323-162">Partner Tier 2 Support</span></span>

- <span data-ttu-id="ba323-163">用户帐户管理员</span><span class="sxs-lookup"><span data-stu-id="ba323-163">User account admin</span></span>

- <span data-ttu-id="ba323-164">目录编写者</span><span class="sxs-lookup"><span data-stu-id="ba323-164">Directory writers</span></span>

## <a name="how-to-set-up-the-naming-policy"></a><span data-ttu-id="ba323-165">如何设置命名策略</span><span class="sxs-lookup"><span data-stu-id="ba323-165">How to set up the naming policy</span></span>

<span data-ttu-id="ba323-166">若要设置命名策略，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="ba323-166">To set up a naming policy:</span></span>

1. <span data-ttu-id="ba323-167">在 " [Azure Active Directory](https://aad.portal.azure.com)" 中的 "**管理**" 下，单击 "**组**"。</span><span class="sxs-lookup"><span data-stu-id="ba323-167">In [Azure Active Directory](https://aad.portal.azure.com), under **Manage**, click **Groups**.</span></span>
2. <span data-ttu-id="ba323-168">在 "**设置**" 下，单击 "**命名策略**"。</span><span class="sxs-lookup"><span data-stu-id="ba323-168">Under **Settings**, click **Naming policy**.</span></span>
3. <span data-ttu-id="ba323-169">选择 "**组命名策略**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="ba323-169">Choose the **Group naming policy** tab.</span></span>
4. <span data-ttu-id="ba323-170">在 "**当前策略**" 下，选择是否需要前缀或后缀，或者同时选择这两者，并选中相应的复选框。</span><span class="sxs-lookup"><span data-stu-id="ba323-170">Under **Current policy**, choose if you want to require a prefix or suffix or both, and select the appropriate check boxes.</span></span>
5. <span data-ttu-id="ba323-171">在每个行的**属性**和**字符串**中进行选择，然后指定属性或字符串。</span><span class="sxs-lookup"><span data-stu-id="ba323-171">Choose between **Attribute** and **String** for each line and then specify the attribute or string.</span></span>
6. <span data-ttu-id="ba323-172">添加所需的前缀和后缀后，单击 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="ba323-172">When you have added the prefixes and suffixes that you need, click **Save**.</span></span>

![Azure Active Directory 中的组命名策略设置的屏幕截图](../media/groups-naming-policy-azure.png)

## <a name="naming-policy-experiences-across-office-365-apps"></a><span data-ttu-id="ba323-174">跨 Office 365 应用程序命名策略体验</span><span class="sxs-lookup"><span data-stu-id="ba323-174">Naming policy experiences across Office 365 apps</span></span>

<span data-ttu-id="ba323-175">Office 365 应用程序已更新，以在用户键入组名称和别名时显示命名策略组名称（带有前缀和后缀）的预览。</span><span class="sxs-lookup"><span data-stu-id="ba323-175">The Office 365 apps have been updated to show a preview of the naming policy group name (with prefixes and suffixes) when the user types in the group name and alias.</span></span> <span data-ttu-id="ba323-176">当用户输入阻止的单词时，他们将看到一条错误消息，以便可以删除被阻止的单词。</span><span class="sxs-lookup"><span data-stu-id="ba323-176">When the user enters blocked words, they'll see an error message so they can remove the blocked words.</span></span>

## <a name="outlook-on-the-web"></a><span data-ttu-id="ba323-177">Outlook 网页版</span><span class="sxs-lookup"><span data-stu-id="ba323-177">Outlook on the web</span></span>

<span data-ttu-id="ba323-178">Web 上的 Outlook （以前称为 Outlook Web App 或 OWA）在用户键入组名称或组别名时显示命名策略修饰的名称。</span><span class="sxs-lookup"><span data-stu-id="ba323-178">Outlook on the web (formerly known as Outlook Web App or OWA) shows the naming policy decorated name when the user types a group name or group alias.</span></span> <span data-ttu-id="ba323-179">当用户输入一个自定义阻止的 word 时，将在 UI 中显示一条错误消息以及阻止的 word，以便用户可以将其删除。</span><span class="sxs-lookup"><span data-stu-id="ba323-179">When an user enters a custom blocked word, an error message is shown in the UI along with the blocked word so that the user can remove it.</span></span> <span data-ttu-id="ba323-180">Web 体验快照中的 Outlook 如下所示。</span><span class="sxs-lookup"><span data-stu-id="ba323-180">Outlook on the web experience snapshots are shown below.</span></span>

![Office 365 组中的组命名策略的并排视图](../media/1a21657a-c542-4d9e-ac7d-887ac542a9d9.png)

## <a name="outlook-desktop"></a><span data-ttu-id="ba323-182">Outlook 桌面</span><span class="sxs-lookup"><span data-stu-id="ba323-182">Outlook Desktop</span></span>

<span data-ttu-id="ba323-183">在 Outlook 桌面版中创建的组符合命名策略。</span><span class="sxs-lookup"><span data-stu-id="ba323-183">Groups created in Outlook desktop are compliant with naming policy.</span></span> <span data-ttu-id="ba323-184">Outlook 桌面应用程序尚未显示命名策略的预览，并且在用户输入组名称时不会返回自定义阻止的 word 错误。</span><span class="sxs-lookup"><span data-stu-id="ba323-184">Outlook desktop app doesn't yet show the preview of the naming policy and doesn't return the custom blocked word errors, when the user enters the group name.</span></span> <span data-ttu-id="ba323-185">但是，如果在组名称或别名中存在自定义阻止的单词，则会在选择 "创建"/"编辑" 时自动应用命名策略，并且用户将会看到错误。</span><span class="sxs-lookup"><span data-stu-id="ba323-185">However, naming policy will be automatically applied on selecting create/edit and users will be presented with errors if there are custom blocked words in the group name or alias.</span></span>

## <a name="microsoft-teams"></a><span data-ttu-id="ba323-186">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ba323-186">Microsoft Teams</span></span>

<span data-ttu-id="ba323-187">Microsoft 团队显示当用户键入团队名称时的命名策略修饰名。</span><span class="sxs-lookup"><span data-stu-id="ba323-187">Microsoft Teams shows the naming policy decorated name when the user types a team name.</span></span> <span data-ttu-id="ba323-188">当用户输入一个已阻止的自定义单词时，将显示一条错误消息和被阻止的 word，以便用户可以将其删除。</span><span class="sxs-lookup"><span data-stu-id="ba323-188">When a user enters a custom blocked word, an error message is shown along with the blocked word so that the user can remove it.</span></span>

![Microsoft 团队中的组命名策略阻止的示例](../media/7c904546-5853-4642-949a-a55dbb004eca.png)

## <a name="sharepoint"></a><span data-ttu-id="ba323-190">SharePoint</span><span class="sxs-lookup"><span data-stu-id="ba323-190">SharePoint</span></span>

<span data-ttu-id="ba323-191">当用户键入站点名称或组电子邮件地址时，SharePoint 将显示命名策略名称。</span><span class="sxs-lookup"><span data-stu-id="ba323-191">SharePoint shows the naming policy name when the user types a site name or group email address.</span></span> <span data-ttu-id="ba323-192">当用户输入一个已阻止的自定义单词时，将显示一条错误消息以及被阻止的单词，以便用户可以将其删除。</span><span class="sxs-lookup"><span data-stu-id="ba323-192">When an user enters a custom blocked word, an error message is shown, along with the blocked word so that the user can remove it.</span></span>

![组命名策略-SharePoint 网站阻止名称](../media/cf0d6158-fd32-4a93-ac24-2e037102c42c.png)

## <a name="microsoft-stream"></a><span data-ttu-id="ba323-194">Microsoft Stream</span><span class="sxs-lookup"><span data-stu-id="ba323-194">Microsoft Stream</span></span>

<span data-ttu-id="ba323-195">Microsoft Stream 显示用户键入组名称或组电子邮件别名时的命名策略修饰名。</span><span class="sxs-lookup"><span data-stu-id="ba323-195">Microsoft Stream shows the naming policy decorated name when the user types a group name or group email alias.</span></span> <span data-ttu-id="ba323-196">当用户输入一个已阻止的自定义单词时，将显示一条错误消息，其中包含被阻止的 word，以便用户可以将其删除。</span><span class="sxs-lookup"><span data-stu-id="ba323-196">When an user enters a custom blocked word, an error message is shown with the blocked word so the user can remove it.</span></span>

![Microsoft Stream 的组命名策略阻止示例](../media/9748f52a-3814-41a6-9ac1-4e8cd4c91011.png)

## <a name="outlook-ios-and-android-app"></a><span data-ttu-id="ba323-198">Outlook iOS 和 Android 应用</span><span class="sxs-lookup"><span data-stu-id="ba323-198">Outlook iOS and Android App</span></span>

<span data-ttu-id="ba323-199">在 Outlook 应用程序中创建的组符合命名策略。</span><span class="sxs-lookup"><span data-stu-id="ba323-199">Groups created in Outlook apps are compliant with naming policy.</span></span> <span data-ttu-id="ba323-200">Outlook mobile 在输入组名称时显示 "命名策略预览"。</span><span class="sxs-lookup"><span data-stu-id="ba323-200">Outlook mobile shows the naming policy preview when entering the Group name.</span></span> <span data-ttu-id="ba323-201">当用户输入一个已阻止的自定义单词时，将在创建组时显示一条错误消息，以便用户可以删除被阻止的单词。</span><span class="sxs-lookup"><span data-stu-id="ba323-201">When a user enters a custom blocked word, an error message is shown on creating the group, so the user can remove the blocked word.</span></span>

## <a name="planner"></a><span data-ttu-id="ba323-202">Planner</span><span class="sxs-lookup"><span data-stu-id="ba323-202">Planner</span></span>

<span data-ttu-id="ba323-203">Planner 与命名策略兼容。</span><span class="sxs-lookup"><span data-stu-id="ba323-203">Planner is compliant with naming policy.</span></span> <span data-ttu-id="ba323-204">Planner 显示在输入计划名称时的命名策略预览。</span><span class="sxs-lookup"><span data-stu-id="ba323-204">Planner shows the naming policy preview when entering the Plan name.</span></span> <span data-ttu-id="ba323-205">当用户输入一个已阻止的自定义单词时，将在创建计划时显示一条错误消息，以便用户可以删除被阻止的单词。</span><span class="sxs-lookup"><span data-stu-id="ba323-205">When a user enters a custom blocked word, an error message is shown on creating the plan, so the user can remove the blocked word.</span></span>

![组命名策略-创建新的计划阻止的示例](../media/ea692b44-3a56-4e6d-bcb8-8444fe5bbc4f.png)

## <a name="dynamics-365-for-customer-engagement"></a><span data-ttu-id="ba323-207">用于客户接洽的 Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="ba323-207">Dynamics 365 for Customer Engagement</span></span>

<span data-ttu-id="ba323-208">用于客户接洽的 Dynamics 365 符合命名策略。</span><span class="sxs-lookup"><span data-stu-id="ba323-208">Dynamics 365 for Customer Engagement is compliant with naming policy.</span></span> <span data-ttu-id="ba323-209">Dynamics 365 显示用户键入组名称或组电子邮件别名时的命名策略修饰名。</span><span class="sxs-lookup"><span data-stu-id="ba323-209">Dynamics 365 shows the naming policy decorated name when the user types a group name or group email alias.</span></span> <span data-ttu-id="ba323-210">当用户输入一个已阻止的自定义单词时，将显示一条错误消息，其中包含被阻止的 word，以便用户可以将其删除。</span><span class="sxs-lookup"><span data-stu-id="ba323-210">When the user enters a custom blocked word, an error message is shown with the blocked word so the user can remove it.</span></span>

![Dynamics 365](../media/8190331c-6779-42bd-a6b3-f7007428c8ae.png)

## <a name="school-data-sync-sds"></a><span data-ttu-id="ba323-212">学校数据同步（SDS）</span><span class="sxs-lookup"><span data-stu-id="ba323-212">School Data Sync (SDS)</span></span>

<span data-ttu-id="ba323-213">通过 SDS 创建的组符合命名策略，但不会自动应用命名策略。</span><span class="sxs-lookup"><span data-stu-id="ba323-213">Groups created through SDS comply with naming policy, but the naming policy isn't applied automatically.</span></span> <span data-ttu-id="ba323-214">SDS 管理员必须将前缀和后缀追加到需要为其创建组的类名，然后上传到 SDS。</span><span class="sxs-lookup"><span data-stu-id="ba323-214">SDS administrators have to append the prefixes and suffixes to class names for which groups need to be created and then upload to SDS.</span></span> <span data-ttu-id="ba323-215">否则，组创建/编辑会失败。</span><span class="sxs-lookup"><span data-stu-id="ba323-215">Groups creation/edit would fail otherwise.</span></span>

## <a name="outlook-customer-manager-ocm"></a><span data-ttu-id="ba323-216">Outlook 客户管理器（OCM）</span><span class="sxs-lookup"><span data-stu-id="ba323-216">Outlook Customer Manager (OCM)</span></span>

<span data-ttu-id="ba323-217">Outlook 客户管理器符合命名策略。</span><span class="sxs-lookup"><span data-stu-id="ba323-217">Outlook Customer Manager is compliant with naming policy.</span></span> <span data-ttu-id="ba323-218">命名策略将自动应用于在 Outlook 客户管理器中创建的组。</span><span class="sxs-lookup"><span data-stu-id="ba323-218">The naming policy gets automatically applied to the group created in Outlook Customer Manager.</span></span> <span data-ttu-id="ba323-219">如果 "所有销售团队" 中的任何单词被定义为一个自定义的阻止单词，OCM 中的组创建将被阻止。</span><span class="sxs-lookup"><span data-stu-id="ba323-219">If any of the words within "All Sales Team" is defined as a custom blocked word, the group creation in OCM will be blocked.</span></span> <span data-ttu-id="ba323-220">用户将无法创建 OCM 组，并将阻止使用 OCM 应用。 "</span><span class="sxs-lookup"><span data-stu-id="ba323-220">The user will not be able to create the OCM group and will be blocked from using the OCM app."</span></span>

## <a name="classroom-app"></a><span data-ttu-id="ba323-221">教室应用</span><span class="sxs-lookup"><span data-stu-id="ba323-221">Classroom App</span></span>

<span data-ttu-id="ba323-222">在课堂应用中创建的组符合命名策略，但不会自动应用命名策略，并且在输入教室组名称时不向用户显示命名策略预览。</span><span class="sxs-lookup"><span data-stu-id="ba323-222">Groups created in classroom app comply with naming policy, but the naming policy isn't applied automatically, and the naming policy preview isn't shown to the users while entering a classroom group name.</span></span> <span data-ttu-id="ba323-223">因此，用户必须输入具有前缀和后缀的修饰教室组名称。</span><span class="sxs-lookup"><span data-stu-id="ba323-223">So users would have to enter the decorated classroom group name with prefixes and suffixes.</span></span> <span data-ttu-id="ba323-224">否则，课堂组创建或编辑将失败，并出现错误。</span><span class="sxs-lookup"><span data-stu-id="ba323-224">Otherwise the classroom group create or edit will fail with errors.</span></span>

## <a name="power-bi"></a><span data-ttu-id="ba323-225">Power BI</span><span class="sxs-lookup"><span data-stu-id="ba323-225">Power BI</span></span>

<span data-ttu-id="ba323-226">Power BI 工作区中创建的组符合命名策略，但不会自动应用命名策略。</span><span class="sxs-lookup"><span data-stu-id="ba323-226">Groups created in Power BI workspaces comply with the naming policy, but the naming policy isn't applied automatically.</span></span> <span data-ttu-id="ba323-227">而且，用户在输入 Power BI 工作区名称时不会向用户显示命名策略预览。</span><span class="sxs-lookup"><span data-stu-id="ba323-227">And, the naming policy preview isn't shown to users when they enter a Power BI workspace name.</span></span>

<span data-ttu-id="ba323-228">建议的名称（应用了命名策略）显示在创建或编辑工作区的错误详细信息中。</span><span class="sxs-lookup"><span data-stu-id="ba323-228">The recommended name - with the naming policy applied - is shown in the error details on create or edit workspaces.</span></span> <span data-ttu-id="ba323-229">这意味着用户必须输入带前缀和后缀的修饰的工作区名称。</span><span class="sxs-lookup"><span data-stu-id="ba323-229">This means users have to enter the decorated workspace name with prefixes and suffixes.</span></span> <span data-ttu-id="ba323-230">否则，工作区创建或编辑将失败，并出现错误。</span><span class="sxs-lookup"><span data-stu-id="ba323-230">Otherwise the workspace create or edit will fail with errors.</span></span>

## <a name="yammer"></a><span data-ttu-id="ba323-231">Yammer</span><span class="sxs-lookup"><span data-stu-id="ba323-231">Yammer</span></span>

<span data-ttu-id="ba323-232">当用户使用其 Azure Active Directory 帐户登录到 Yammer 时创建组或编辑组名称时，组名称将符合命名策略。</span><span class="sxs-lookup"><span data-stu-id="ba323-232">When a user signed in to Yammer with their Azure Active Directory account creates a group or edits a group name, the group name will comply with naming policy.</span></span> <span data-ttu-id="ba323-233">这同时适用于 Office 365 连接的组和所有其他 Yammer 组。</span><span class="sxs-lookup"><span data-stu-id="ba323-233">This applies both to Office 365 connected groups and all other Yammer groups.</span></span>

<span data-ttu-id="ba323-234">如果在命名策略就绪之前创建了 Office 365 连接组，则组名称将不会自动遵循命名策略。</span><span class="sxs-lookup"><span data-stu-id="ba323-234">If an Office 365 connected group was created before the naming policy is in place, the group name will not automatically follow the naming policies.</span></span> <span data-ttu-id="ba323-235">当用户编辑组名称时，系统将提示他们添加前缀和后缀。</span><span class="sxs-lookup"><span data-stu-id="ba323-235">When a user edits the group name, they will be prompted to add the prefix and suffix.</span></span>

<span data-ttu-id="ba323-236">如果命名策略包含不能位于 Yammer 组名称中的字符，则只有管理员能够在 Yammer 中创建连接的组。</span><span class="sxs-lookup"><span data-stu-id="ba323-236">If the naming policy includes characters that can't be in Yammer group names, only admins will be able to create a connected group in Yammer.</span></span>

## <a name="staffhub"></a><span data-ttu-id="ba323-237">StaffHub</span><span class="sxs-lookup"><span data-stu-id="ba323-237">StaffHub</span></span>

<span data-ttu-id="ba323-238">StaffHub 团队不遵循命名策略，但基础 Office 365 组也不遵循。</span><span class="sxs-lookup"><span data-stu-id="ba323-238">StaffHub teams do not follow the naming policy, but the underlying Office 365 group does.</span></span> <span data-ttu-id="ba323-239">StaffHub 团队名称不会应用前缀和后缀，也不会检查是否存在自定义阻止的单词。</span><span class="sxs-lookup"><span data-stu-id="ba323-239">StaffHub team name does not apply the prefixes and suffixes and does not check for custom blocked words.</span></span> <span data-ttu-id="ba323-240">但 StaffHub 确实应用了前缀和后缀并删除了基础 Office 365 组中阻止的单词。</span><span class="sxs-lookup"><span data-stu-id="ba323-240">But StaffHub does apply the prefixes and suffixes and removes blocked words from the underlying Office 365 group.</span></span>

## <a name="exchange-powershell"></a><span data-ttu-id="ba323-241">Exchange PowerShell</span><span class="sxs-lookup"><span data-stu-id="ba323-241">Exchange PowerShell</span></span>

<span data-ttu-id="ba323-242">Exchange PowerShell cmdlet 符合命名策略。</span><span class="sxs-lookup"><span data-stu-id="ba323-242">Exchange PowerShell cmdlets are compliant with naming policy.</span></span> <span data-ttu-id="ba323-243">如果在组名称和组别名中未使用命名约定，则用户将使用建议的前缀和后缀以及自定义被阻止的单词获取相应的错误消息。</span><span class="sxs-lookup"><span data-stu-id="ba323-243">Users will get appropriate error messages with suggested prefixes and suffixes and for custom blocked words if naming convention isn't used in the group names and group alias.</span></span>

## <a name="azure-active-directory-powershell-cmdlets"></a><span data-ttu-id="ba323-244">Azure Active Directory PowerShell cmdlet</span><span class="sxs-lookup"><span data-stu-id="ba323-244">Azure Active Directory PowerShell cmdlets</span></span>

<span data-ttu-id="ba323-245">Azure Active Directory PowerShell cmdlet 符合命名策略。</span><span class="sxs-lookup"><span data-stu-id="ba323-245">Azure Active Directory PowerShell cmdlets are compliant with naming policy.</span></span> <span data-ttu-id="ba323-246">如果在组名称和组别名中未使用命名约定，则用户将使用建议的前缀和后缀以及自定义被阻止的单词获取相应的错误消息。</span><span class="sxs-lookup"><span data-stu-id="ba323-246">Users will get appropriate error messages with suggested prefixes and suffixes and for custom blocked words if naming convention isn't used in the group names and group alias.</span></span>

## <a name="exchange-admin-center"></a><span data-ttu-id="ba323-247">Exchange 管理中心</span><span class="sxs-lookup"><span data-stu-id="ba323-247">Exchange admin center</span></span>

<span data-ttu-id="ba323-248">Exchange 管理中心（EAC）符合命名策略。</span><span class="sxs-lookup"><span data-stu-id="ba323-248">The Exchange admin center (EAC) is compliant with naming policy.</span></span> <span data-ttu-id="ba323-249">在 "创建" 或 "编辑" 操作时，如果组名称和组别名中未使用命名约定，则用户将获得相应的错误消息，其中包含建议的前缀和后缀以及自定义被阻止的词。</span><span class="sxs-lookup"><span data-stu-id="ba323-249">On create or edit actions, users will get appropriate error messages with suggested prefixes and suffixes and for custom blocked words if naming convention isn't used in the group names and group alias.</span></span>

## <a name="microsoft-365-admin-center"></a><span data-ttu-id="ba323-250">Microsoft 365 管理中心</span><span class="sxs-lookup"><span data-stu-id="ba323-250">Microsoft 365 admin center</span></span>

<span data-ttu-id="ba323-251">Microsoft 365 admin center 符合命名策略。</span><span class="sxs-lookup"><span data-stu-id="ba323-251">The Microsoft 365 admin center is compliant with naming policy.</span></span> <span data-ttu-id="ba323-252">在 "创建" 或 "编辑" 操作中，将自动应用命名策略。</span><span class="sxs-lookup"><span data-stu-id="ba323-252">On create or edit actions, naming policy will automatically get applied.</span></span> <span data-ttu-id="ba323-253">用户在输入被阻止的自定义单词时，会收到适当的错误。</span><span class="sxs-lookup"><span data-stu-id="ba323-253">Users will get appropriate errors when they enter custom blocked words.</span></span> <span data-ttu-id="ba323-254">Microsoft 365 管理中心尚未显示命名策略的预览，并且在用户输入组名称时不会返回已阻止的自定义 word 错误。</span><span class="sxs-lookup"><span data-stu-id="ba323-254">The Microsoft 365 admin center doesn't yet show the preview of the naming policy and doesn't return the custom blocked word errors, when the user enters the group name.</span></span>

## <a name="azure-active-directory-portal"></a><span data-ttu-id="ba323-255">Azure Active Directory 门户</span><span class="sxs-lookup"><span data-stu-id="ba323-255">Azure Active Directory portal</span></span>

<span data-ttu-id="ba323-256">Azure Active Directory 门户符合命名策略。</span><span class="sxs-lookup"><span data-stu-id="ba323-256">The Azure Active Directory portal is compliant with naming policy.</span></span> <span data-ttu-id="ba323-257">Azure Active Directory 门户显示在输入组名称时的命名策略预览。</span><span class="sxs-lookup"><span data-stu-id="ba323-257">Azure Active Directory portal shows the naming policy preview when entering the Group name.</span></span> <span data-ttu-id="ba323-258">当用户输入一个已阻止的自定义单词时，将在创建组时显示一条错误消息，以便用户可以删除被阻止的单词。</span><span class="sxs-lookup"><span data-stu-id="ba323-258">When a user enters a custom blocked word, an error message is shown on creating the group, so the user can remove the blocked word.</span></span>

## <a name="more-articles-on-naming-policy"></a><span data-ttu-id="ba323-259">有关命名策略的更多文章</span><span class="sxs-lookup"><span data-stu-id="ba323-259">More articles on naming policy</span></span>

[<span data-ttu-id="ba323-260">为 Azure Active Directory 中的 Office 365 组强制实施命名策略</span><span class="sxs-lookup"><span data-stu-id="ba323-260">Enforce a naming policy for Office 365 groups in Azure Active Directory</span></span>](https://go.microsoft.com/fwlink/?linkid=868340)

[<span data-ttu-id="ba323-261">用于配置组设置的 Azure Active Directory cmdlet</span><span class="sxs-lookup"><span data-stu-id="ba323-261">Azure Active Directory cmdlets for configuring group settings</span></span>](https://go.microsoft.com/fwlink/?linkid=868341)
