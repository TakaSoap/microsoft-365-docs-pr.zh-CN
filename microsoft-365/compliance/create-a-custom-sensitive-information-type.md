---
title: 自定义敏感信息类型入门
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.date: 04/17/2019
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 了解如何在安全与合规中心的图形用户界面中为 DLP 创建、修改、删除和测试自定义敏感信息类型。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 94f0f6b68e9f952e0d52ce7cb71ccf03913584f4
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929348"
---
# <a name="get-started-with-custom-sensitive-information-types"></a><span data-ttu-id="79ac9-103">自定义敏感信息类型入门</span><span class="sxs-lookup"><span data-stu-id="79ac9-103">Get started with custom sensitive information types</span></span>

<span data-ttu-id="79ac9-104">如果预先配置的敏感信息类型不满足你的需要，可以创建自己的自定义敏感信息类型，你可以完全定义这些类型，也可以复制其中一个预先配置的类型并进行修改。</span><span class="sxs-lookup"><span data-stu-id="79ac9-104">If the pre-configured sensitive information types don't meet your needs, you can create your own custom sensitive information types that you fully define or you can copy one of the pre-configured ones and modify it.</span></span>

<span data-ttu-id="79ac9-105">使用此方法创建的自定义敏感信息类型将添加到名为 `Microsoft.SCCManaged.CustomRulePack` 的规则包中。</span><span class="sxs-lookup"><span data-stu-id="79ac9-105">The custom sensitive information types that you create by using this method are added to the rule package named `Microsoft.SCCManaged.CustomRulePack`.</span></span>

<span data-ttu-id="79ac9-106">有两种方法可以创建新的敏感信息类型：</span><span class="sxs-lookup"><span data-stu-id="79ac9-106">There are two ways to create a new sensitive information type:</span></span>

- [<span data-ttu-id="79ac9-107">从头开始完全定义所有元素</span><span class="sxs-lookup"><span data-stu-id="79ac9-107">from scratch where you fully define all elements</span></span>](#create-a-custom-sensitive-information-type)
- [<span data-ttu-id="79ac9-108">复制和修改现有的敏感信息类型</span><span class="sxs-lookup"><span data-stu-id="79ac9-108">copy and modify an existing sensitive information type</span></span>](#copy-and-modify-a-sensitive-information-type)


## <a name="before-you-begin"></a><span data-ttu-id="79ac9-109">开始之前</span><span class="sxs-lookup"><span data-stu-id="79ac9-109">Before you begin</span></span>

- <span data-ttu-id="79ac9-110">应该熟悉敏感信息类型及其组成。</span><span class="sxs-lookup"><span data-stu-id="79ac9-110">You should be familiar with sensitive information types and what they are composed of.</span></span> <span data-ttu-id="79ac9-111">请参阅，[了解敏感信息类型](sensitive-information-type-learn-about.md)。</span><span class="sxs-lookup"><span data-stu-id="79ac9-111">See, [Learn about sensitive information types](sensitive-information-type-learn-about.md).</span></span> <span data-ttu-id="79ac9-112">了解以下角色至关重要：</span><span class="sxs-lookup"><span data-stu-id="79ac9-112">It is critical to understand the roles of:</span></span>
    - <span data-ttu-id="79ac9-113">[正则表达式](https://www.boost.org/doc/libs/1_68_0/libs/regex/doc/html/) - Microsoft 365 敏感信息类型使用 Boost.RegEx 5.1.3 引擎</span><span class="sxs-lookup"><span data-stu-id="79ac9-113">[regular expressions](https://www.boost.org/doc/libs/1_68_0/libs/regex/doc/html/) - Microsoft 365 sensitive information types uses the Boost.RegEx 5.1.3 engine</span></span>
    - <span data-ttu-id="79ac9-114">关键字列表 - 可以在定义敏感信息类型或从现有关键字列表中选择时创建自己的关键字列表</span><span class="sxs-lookup"><span data-stu-id="79ac9-114">keyword lists - you can create your own as you define your sensitive information type or choose from existing keyword lists</span></span>
    - [<span data-ttu-id="79ac9-115">关键字字典</span><span class="sxs-lookup"><span data-stu-id="79ac9-115">keyword dictionary</span></span>](create-a-keyword-dictionary.md)
    - [<span data-ttu-id="79ac9-116">函数</span><span class="sxs-lookup"><span data-stu-id="79ac9-116">functions</span></span>](what-the-dlp-functions-look-for.md)
    - [<span data-ttu-id="79ac9-117">可信度</span><span class="sxs-lookup"><span data-stu-id="79ac9-117">confidence levels</span></span>](sensitive-information-type-learn-about.md#more-on-confidence-levels)
 
- <span data-ttu-id="79ac9-118">必须拥有全局管理员或合规性管理员权限，以便可以通过 UI 创建、测试和部署自定义的敏感信息类型。</span><span class="sxs-lookup"><span data-stu-id="79ac9-118">You must have Global admin or Compliance admin permissions to create, test, and deploy a custom sensitive information type through the UI.</span></span> <span data-ttu-id="79ac9-119">请参阅 Office 365 中的[关于管理员角色](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles?view=o365-worldwide)。</span><span class="sxs-lookup"><span data-stu-id="79ac9-119">See [About admin roles](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles?view=o365-worldwide) in Office 365.</span></span>

- <span data-ttu-id="79ac9-120">组织必须具有包含数据丢失防护 (DLP) 的订阅（如 Office 365 企业版）。</span><span class="sxs-lookup"><span data-stu-id="79ac9-120">Your organization must have a subscription, such as Office 365 Enterprise, that includes Data Loss Prevention (DLP).</span></span> <span data-ttu-id="79ac9-121">请参阅[邮件策略和合规性服务说明](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/messaging-policy-and-compliance-servicedesc)。</span><span class="sxs-lookup"><span data-stu-id="79ac9-121">See [Messaging Policy and Compliance ServiceDescription](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/messaging-policy-and-compliance-servicedesc).</span></span> 


> [!IMPORTANT]
> <span data-ttu-id="79ac9-122">在创建自定义分类或正则表达式模式时，不可从 Microsoft 客户服务和支持获取帮助。</span><span class="sxs-lookup"><span data-stu-id="79ac9-122">Microsoft Customer Service & Support can't assist with creating custom classifications or regular expression patterns.</span></span> <span data-ttu-id="79ac9-123">支持工程师可对功能提供有限的支持，例如提供用于测试目的的示例正则表达式，或者帮助排查未如期触发的现有正则表达式模式的问题，但无法保证所有自定义内容匹配开发都将满足你的要求或义务。</span><span class="sxs-lookup"><span data-stu-id="79ac9-123">Support engineers can provide limited support for the feature, such as, providing sample regular expression patterns for testing purposes, or assisting with troubleshooting an existing regular expression pattern that's not triggering as expected, but can't provide assurances that any custom content-matching development will fulfill your requirements or obligations.</span></span>

## <a name="create-a-custom-sensitive-information-type"></a><span data-ttu-id="79ac9-124">创建自定义敏感信息类型</span><span class="sxs-lookup"><span data-stu-id="79ac9-124">Create a custom sensitive information type</span></span>

<span data-ttu-id="79ac9-125">使用以下步骤可以创建完全定义的新敏感信息类型。</span><span class="sxs-lookup"><span data-stu-id="79ac9-125">Use this procedure to create a new sensitive information type that you fully define.</span></span> 

1. <span data-ttu-id="79ac9-126">在“合规中心”中，转到“**数据分类**”\>“**敏感信息类型**”，然后选择“**创建信息类型**”。</span><span class="sxs-lookup"><span data-stu-id="79ac9-126">In the Compliance Center, go to **Data classification** \> **Sensitive info types** and choose **Create info type**.</span></span>
2. <span data-ttu-id="79ac9-127">填写“**名称**”和“**说明**” 的值，然后选择“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="79ac9-127">Fill in values for **Name** and **Description** and choose **Next**.</span></span>
3. <span data-ttu-id="79ac9-128">选择“**创建模式**”。</span><span class="sxs-lookup"><span data-stu-id="79ac9-128">Choose **Create pattern**.</span></span> <span data-ttu-id="79ac9-129">在定义新的敏感信息类型时，可以创建多个模式，每个模式具有不同的元素和置信度。</span><span class="sxs-lookup"><span data-stu-id="79ac9-129">You can create multiple patterns, each with different elements and confidence levels, as you define your new sensitive information type.</span></span>
4. <span data-ttu-id="79ac9-130">选择模式的默认可信度。</span><span class="sxs-lookup"><span data-stu-id="79ac9-130">Choose the default confidence level for the pattern.</span></span> <span data-ttu-id="79ac9-131">这些值是“**低可信度**”、“**中可信度**”和“**高可信度**”。</span><span class="sxs-lookup"><span data-stu-id="79ac9-131">The values are **Low confidence**, **Medium confidence**, and **High confidence**.</span></span>
5. <span data-ttu-id="79ac9-132">选择并定义 **主要元素**。</span><span class="sxs-lookup"><span data-stu-id="79ac9-132">Choose and define **Primary element**.</span></span> <span data-ttu-id="79ac9-133">主要元素可以是带有可选验证程序的 **正则表达式**、**关键字列表**、**关键字字典** 或预先配置的 **函数** 之一。</span><span class="sxs-lookup"><span data-stu-id="79ac9-133">The primary element can be a **Regular expression** with an optional validator, a **Keyword list**, a **Keyword dictionary**, or one of the pre-configured **Functions**.</span></span> <span data-ttu-id="79ac9-134">有关 DLP 函数的详细信息，请参阅 [DLP 函数查找的内容](what-the-dlp-functions-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="79ac9-134">For more information on DLP functions, see [What the DLP functions look for](what-the-dlp-functions-look-for.md).</span></span>
6. <span data-ttu-id="79ac9-135">填写 **字符领近度** 的值。</span><span class="sxs-lookup"><span data-stu-id="79ac9-135">Fill in a value for **Character proximity**.</span></span>
7. <span data-ttu-id="79ac9-136">（可选）添加支持元素（如有）。</span><span class="sxs-lookup"><span data-stu-id="79ac9-136">(Optional) Add supporting elements if you have any.</span></span> <span data-ttu-id="79ac9-137">支持元素可以是带有可选验证程序的正则表达式、关键字列表、关键字字典或预定义的函数之一。</span><span class="sxs-lookup"><span data-stu-id="79ac9-137">Supporting elements can be a regular expression with an optional validator, a keyword list, a keyword dictionary or one of the pre-defined functions.</span></span> 
8.  <span data-ttu-id="79ac9-138">（可选）从可用检查列表中添加其他检查</span><span class="sxs-lookup"><span data-stu-id="79ac9-138">(Optional) Add additional checks from the list of available checks</span></span>
9. <span data-ttu-id="79ac9-139">选择“**创建**”。</span><span class="sxs-lookup"><span data-stu-id="79ac9-139">Choose **Create**.</span></span>
10. <span data-ttu-id="79ac9-140">选择“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="79ac9-140">Choose **Next**.</span></span>
11. <span data-ttu-id="79ac9-141">为此敏感信息类型选择 **建议的可信度**。</span><span class="sxs-lookup"><span data-stu-id="79ac9-141">Choose the **recommended confidence level** for this sensitive information type.</span></span>
12. <span data-ttu-id="79ac9-142">检查设置并选择“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="79ac9-142">Check your setting and choose **Submit**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="79ac9-143">Microsoft 365 使用搜索爬网程序来确定 SharePoint Online 和 OneDrive for Business 网站中的敏感信息并对其分类。</span><span class="sxs-lookup"><span data-stu-id="79ac9-143">Microsoft 365 uses the search crawler to identify and classify sensitive information in SharePoint Online and OneDrive for Business sites.</span></span> <span data-ttu-id="79ac9-144">要确定现有内容中新的自定义敏感信息类型，必须对该内容重新爬网。</span><span class="sxs-lookup"><span data-stu-id="79ac9-144">To identify your new custom sensitive information type in existing content, the content must be re-crawled.</span></span> <span data-ttu-id="79ac9-145">根据计划对内容进行爬网，但你可手动重新爬网内容来查找网站集、列表或库。</span><span class="sxs-lookup"><span data-stu-id="79ac9-145">Content is crawled based on a schedule, but you can manually re-crawl content for a site collection, list, or library.</span></span> <span data-ttu-id="79ac9-146">有关详细信息，请参阅[Manually request crawling and re-indexing of a site, a library or a list](https://docs.microsoft.com/sharepoint/crawl-site-content)（手动请求对网站、库或列表进行爬网和重新编制索引）。</span><span class="sxs-lookup"><span data-stu-id="79ac9-146">For more information, see [Manually request crawling and re-indexing of a site, a library or a list](https://docs.microsoft.com/sharepoint/crawl-site-content).</span></span>

13. <span data-ttu-id="79ac9-147">在“**数据分类**”页面上，将看到列出的所有敏感信息类型。</span><span class="sxs-lookup"><span data-stu-id="79ac9-147">On the **Data classification** page, you'll see all the sensitive information types listed.</span></span> <span data-ttu-id="79ac9-148">选择“**刷新**”，然后浏览或使用搜索工具查找刚刚创建的敏感信息类型。</span><span class="sxs-lookup"><span data-stu-id="79ac9-148">Choose **Refresh** and then browse for or use the search tool to find the sensitive information type you just created.</span></span>

## <a name="test-a-sensitive-information-type"></a><span data-ttu-id="79ac9-149">测试敏感信息类型</span><span class="sxs-lookup"><span data-stu-id="79ac9-149">Test a sensitive information type</span></span>

<span data-ttu-id="79ac9-150">可以测试列表中的任何敏感信息类型。</span><span class="sxs-lookup"><span data-stu-id="79ac9-150">You can test any sensitive information type in the list.</span></span> <span data-ttu-id="79ac9-151">我们建议在策略中使用之前，测试创建的每种敏感信息类型。</span><span class="sxs-lookup"><span data-stu-id="79ac9-151">We suggest that you test every sensitive information type that you create before using it in a policy.</span></span>

1. <span data-ttu-id="79ac9-152">准备两个文件，比如 Word 文档。</span><span class="sxs-lookup"><span data-stu-id="79ac9-152">Prepare two files, like a Word document.</span></span> <span data-ttu-id="79ac9-153">一个包含与敏感信息类型中指定的元素匹配的内容，另一个不匹配。</span><span class="sxs-lookup"><span data-stu-id="79ac9-153">One with content that matches the elements you specified in your sensitive information type and one that doesn't match.</span></span>
2. <span data-ttu-id="79ac9-154">在“合规中心”中，转到“**数据分类**”\>“**敏感信息类型**”，然后从列表中选择敏感信息类型，以打开“详细信息”窗格并选择“**测试**”。</span><span class="sxs-lookup"><span data-stu-id="79ac9-154">In the Compliance Center, go to **Data classification** \> **Sensitive info types** and choose the sensitive information type from the list to open the details pane and choose **Test**.</span></span>
3. <span data-ttu-id="79ac9-155">上传文件并选择“**测试**”。</span><span class="sxs-lookup"><span data-stu-id="79ac9-155">Upload a file and choose **Test**.</span></span>
4. <span data-ttu-id="79ac9-156">在“**匹配结果**”页面上，查看结果并选择“**完成**”。</span><span class="sxs-lookup"><span data-stu-id="79ac9-156">On the **Matches results** page, review the results and choose **Finish**.</span></span>

## <a name="modify-custom-sensitive-information-types-in-the-compliance-center"></a><span data-ttu-id="79ac9-157">在合规中心内修改自定义敏感信息类型</span><span class="sxs-lookup"><span data-stu-id="79ac9-157">Modify custom sensitive information types in the Compliance Center</span></span>

1. <span data-ttu-id="79ac9-158">在“合规中心”中，转到“**数据分类**”\>“**敏感信息类型**”，然后从要修改的列表中选择敏感信息类型，然后选择“**编辑**”。</span><span class="sxs-lookup"><span data-stu-id="79ac9-158">In the Compliance Center, go to **Data classification** \> **Sensitive info types** and choose the sensitive information type from the list that you want to modify choose **Edit**.</span></span>
2. <span data-ttu-id="79ac9-159">可以添加其他模式，其中包括唯一的主元素和支持元素、可信度、字符领近度和其他检查，或者编辑/删除现有的模式。</span><span class="sxs-lookup"><span data-stu-id="79ac9-159">You can add other patterns, with unique primary and supporting elements, confidence levels, character proximity, and additional checks or edit/remove the existing ones.</span></span> <span data-ttu-id="79ac9-160">有关详细信息，请参阅[创建自定义敏感信息类型](#create-a-custom-sensitive-information-type)。</span><span class="sxs-lookup"><span data-stu-id="79ac9-160">For more information, see [Create a custom sensitive information type](#create-a-custom-sensitive-information-type).</span></span>

## <a name="remove-custom-sensitive-information-types-in-the-compliance-center"></a><span data-ttu-id="79ac9-161">移除合规中心中的自定义敏感信息类型</span><span class="sxs-lookup"><span data-stu-id="79ac9-161">Remove custom sensitive information types in the Compliance Center</span></span> 

> [!NOTE]
> <span data-ttu-id="79ac9-162">只能删除自定义敏感信息类型；不能删除内置敏感信息类型。</span><span class="sxs-lookup"><span data-stu-id="79ac9-162">You can only remove custom sensitive information types; you can't remove built-in sensitive information types.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="79ac9-163">删除自定义敏感信息类型前，请先验证没有 DLP 策略或 Exchange 邮件流规则（亦称为“传输规则”）仍在引用此敏感信息类型。</span><span class="sxs-lookup"><span data-stu-id="79ac9-163">Before your remove a custom sensitive information type, verify that no DLP policies or Exchange mail flow rules (also known as transport rules) still reference the sensitive information type.</span></span>

1. <span data-ttu-id="79ac9-164">在“合规中心”中，转到“**数据分类**”\>“**敏感信息类型**”，然后从列表中选择要删除的敏感信息类型。</span><span class="sxs-lookup"><span data-stu-id="79ac9-164">In the Compliance Center, go to **Data classification** \> **Sensitive info types** and choose the sensitive information type from the list that you want to remove.</span></span>
2. <span data-ttu-id="79ac9-165">在打开的浮出控件中，选择“**删除**”。</span><span class="sxs-lookup"><span data-stu-id="79ac9-165">In the fly-out that opens, choose **Delete**.</span></span>

## <a name="copy-and-modify-a-sensitive-information-type"></a><span data-ttu-id="79ac9-166">复制和修改敏感信息类型</span><span class="sxs-lookup"><span data-stu-id="79ac9-166">Copy and modify a sensitive information type</span></span>

<span data-ttu-id="79ac9-167">使用以下步骤可以创建基于现有敏感信息类型的新敏感信息类型。</span><span class="sxs-lookup"><span data-stu-id="79ac9-167">Use this procedure to create a new sensitive information type that is based on an existing sensitive information type.</span></span> 

1. <span data-ttu-id="79ac9-168">在“合规中心”中，转到“**数据分类**”\>“**敏感信息类型**”，然后选择要复制的敏感信息类型。</span><span class="sxs-lookup"><span data-stu-id="79ac9-168">In the Compliance Center, go to **Data classification** \> **Sensitive info types** and choose the sensitive information type that you want to copy.</span></span>
2. <span data-ttu-id="79ac9-169">在浮出控件中，选择“**复制**”。</span><span class="sxs-lookup"><span data-stu-id="79ac9-169">In the flyout, choose **Copy**.</span></span>
3. <span data-ttu-id="79ac9-170">在敏感信息类型列表中选择“**刷新**”，然后浏览或搜索刚刚创建的副本。</span><span class="sxs-lookup"><span data-stu-id="79ac9-170">Choose **Refresh** in the list of sensitive information types and either browse or search for the copy you just made.</span></span> <span data-ttu-id="79ac9-171">部分字串搜索有用，所以可以只搜索 `copy`，搜索将返回名称中包含 `copy` 文字的所有敏感信息类型。</span><span class="sxs-lookup"><span data-stu-id="79ac9-171">Partial sting searches work, so you could just search for `copy` and search would return all the sensitive information types with the word `copy` in the name.</span></span> 
4. <span data-ttu-id="79ac9-172">填写“**名称**”和“**说明**” 的值，然后选择“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="79ac9-172">Fill in values for **Name** and **Description** and choose **Next**.</span></span>
5. <span data-ttu-id="79ac9-173">选择敏感信息类型“副本”，然后选择“**编辑**”。</span><span class="sxs-lookup"><span data-stu-id="79ac9-173">Choose your sensitive information type copy and choose **Edit**.</span></span> 
6. <span data-ttu-id="79ac9-174">为新的敏感信息类型提供新“**名称**”和“**描述**”。</span><span class="sxs-lookup"><span data-stu-id="79ac9-174">Give your new sensitive information type a new **Name** and **Description**.</span></span>
7. <span data-ttu-id="79ac9-175">您可以选择编辑或删除现有模式，以及添加新模式。</span><span class="sxs-lookup"><span data-stu-id="79ac9-175">You can choose to edit or remove the existing patterns and add new ones.</span></span> <span data-ttu-id="79ac9-176">选择新模式的默认可信度。</span><span class="sxs-lookup"><span data-stu-id="79ac9-176">Choose the default confidence level for the new pattern.</span></span> <span data-ttu-id="79ac9-177">这些值是“**低可信度**”、“**中可信度**”和“**高可信度**”。</span><span class="sxs-lookup"><span data-stu-id="79ac9-177">The values are **Low confidence**, **Medium confidence**, and **High confidence**.</span></span>
8. <span data-ttu-id="79ac9-178">选择并定义 **主要元素**。</span><span class="sxs-lookup"><span data-stu-id="79ac9-178">Choose and define **Primary element**.</span></span> <span data-ttu-id="79ac9-179">主要元素可以是 **正则表达式**、**关键字列表**、**关键字字典** 或预先配置的 **函数** 之一。</span><span class="sxs-lookup"><span data-stu-id="79ac9-179">The primary element can be a **Regular expression**, a **Keyword list**, a **Keyword dictionary**, or one of the pre-configured **Functions**.</span></span> <span data-ttu-id="79ac9-180">请参阅，[DLP 函数查找的内容](what-the-dlp-functions-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="79ac9-180">See, [What the DLP functions look for](what-the-dlp-functions-look-for.md).</span></span>
9. <span data-ttu-id="79ac9-181">填写 **字符领近度** 的值。</span><span class="sxs-lookup"><span data-stu-id="79ac9-181">Fill in a value for **Character proximity**.</span></span>
10. <span data-ttu-id="79ac9-182">（可选）如果有 **支持元素** 或任何 **其他检查**，请添加它们。</span><span class="sxs-lookup"><span data-stu-id="79ac9-182">(Optional) If you have **Supporting elements** or any **Additional checks** add them.</span></span> <span data-ttu-id="79ac9-183">如果需要，可以将你的 **支持元素** 分组。</span><span class="sxs-lookup"><span data-stu-id="79ac9-183">If needed you can group your **Supporting elements**.</span></span>
11. <span data-ttu-id="79ac9-184">选择“**创建**”。</span><span class="sxs-lookup"><span data-stu-id="79ac9-184">Choose **Create**.</span></span>
12. <span data-ttu-id="79ac9-185">选择“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="79ac9-185">Choose **Next**.</span></span>
13. <span data-ttu-id="79ac9-186">为此敏感信息类型选择 **建议的可信度**。</span><span class="sxs-lookup"><span data-stu-id="79ac9-186">Choose the **recommended confidence level** for this sensitive information type.</span></span>
14. <span data-ttu-id="79ac9-187">检查设置并选择“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="79ac9-187">Check your setting and choose **Submit**.</span></span>

<span data-ttu-id="79ac9-188">此外，还可以使用 PowerShell 和精确的数据匹配功能创建自定义敏感信息类型。</span><span class="sxs-lookup"><span data-stu-id="79ac9-188">You can also create custom sensitive information types by using PowerShell and Exact Data Match capabilities.</span></span> <span data-ttu-id="79ac9-189">若要了解有关这些方法的详细信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="79ac9-189">To learn more about those methods, see:</span></span>
- [<span data-ttu-id="79ac9-190">使用安全与合规中心 PowerShell 创建自定义敏感信息类型</span><span class="sxs-lookup"><span data-stu-id="79ac9-190">Create a custom sensitive information type in Security & Compliance Center PowerShell</span></span>](create-a-custom-sensitive-information-type-in-scc-powershell.md)
- [<span data-ttu-id="79ac9-191">使用精确数据匹配 (EDM) 为 DLP 创建自定义敏感信息类型</span><span class="sxs-lookup"><span data-stu-id="79ac9-191">Create a custom sensitive information type for DLP with Exact Data Match (EDM)</span></span>](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)
 
> [!NOTE]
> <span data-ttu-id="79ac9-192">Microsoft 365 信息保护可为以下语言提供双字节字符集语言支持（预览）：</span><span class="sxs-lookup"><span data-stu-id="79ac9-192">Microsoft 365 Information Protection supports, in preview, double byte character set languages for:</span></span>
> - <span data-ttu-id="79ac9-193">简体中文</span><span class="sxs-lookup"><span data-stu-id="79ac9-193">Chinese (simplified)</span></span>
> - <span data-ttu-id="79ac9-194">繁体中文</span><span class="sxs-lookup"><span data-stu-id="79ac9-194">Chinese (traditional)</span></span>
> - <span data-ttu-id="79ac9-195">韩语</span><span class="sxs-lookup"><span data-stu-id="79ac9-195">Korean</span></span>
> - <span data-ttu-id="79ac9-196">日语</span><span class="sxs-lookup"><span data-stu-id="79ac9-196">Japanese</span></span>
>
><span data-ttu-id="79ac9-197">此支持适用于敏感信息类型。</span><span class="sxs-lookup"><span data-stu-id="79ac9-197">This support is available for sensitive information types.</span></span> <span data-ttu-id="79ac9-198">有关详细信息，请参阅[双字节字符集的信息保护支持发行说明（预览版）](mip-dbcs-relnotes.md)。</span><span class="sxs-lookup"><span data-stu-id="79ac9-198">See, [Information protection support for double byte character sets release notes (preview)](mip-dbcs-relnotes.md) for more information.</span></span>