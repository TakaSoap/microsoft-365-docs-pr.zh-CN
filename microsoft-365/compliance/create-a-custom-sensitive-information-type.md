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
ms.date: ''
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 了解如何在安全与合规中心内为 DLP 创建、修改、删除和测试&类型。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: e067bc502267e918bd355d9bf8a1982795255846
ms.sourcegitcommit: a4c93a4c7d7db08fe3b032b58d5c7dbbb9476e90
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/02/2021
ms.locfileid: "53256719"
---
# <a name="get-started-with-custom-sensitive-information-types"></a><span data-ttu-id="65680-103">自定义敏感信息类型入门</span><span class="sxs-lookup"><span data-stu-id="65680-103">Get started with custom sensitive information types</span></span>

<span data-ttu-id="65680-104">如果预先配置的敏感信息类型不满足你的需要，可以创建自己的自定义敏感信息类型，你可以完全定义这些类型，也可以复制其中一个预先配置的类型并进行修改。</span><span class="sxs-lookup"><span data-stu-id="65680-104">If the pre-configured sensitive information types don't meet your needs, you can create your own custom sensitive information types that you fully define or you can copy one of the pre-configured ones and modify it.</span></span>

<span data-ttu-id="65680-105">使用此方法创建的自定义敏感信息类型将添加到名为 `Microsoft.SCCManaged.CustomRulePack` 的规则包中。</span><span class="sxs-lookup"><span data-stu-id="65680-105">The custom sensitive information types that you create by using this method are added to the rule package named `Microsoft.SCCManaged.CustomRulePack`.</span></span>

<span data-ttu-id="65680-106">有两种方法可以创建新的敏感信息类型：</span><span class="sxs-lookup"><span data-stu-id="65680-106">There are two ways to create a new sensitive information type:</span></span>

- [<span data-ttu-id="65680-107">从头开始完全定义所有元素</span><span class="sxs-lookup"><span data-stu-id="65680-107">from scratch where you fully define all elements</span></span>](#create-a-custom-sensitive-information-type)
- [<span data-ttu-id="65680-108">复制和修改现有的敏感信息类型</span><span class="sxs-lookup"><span data-stu-id="65680-108">copy and modify an existing sensitive information type</span></span>](#copy-and-modify-a-sensitive-information-type)


## <a name="before-you-begin"></a><span data-ttu-id="65680-109">开始之前</span><span class="sxs-lookup"><span data-stu-id="65680-109">Before you begin</span></span>

- <span data-ttu-id="65680-110">应该熟悉敏感信息类型及其组成。</span><span class="sxs-lookup"><span data-stu-id="65680-110">You should be familiar with sensitive information types and what they are composed of.</span></span> <span data-ttu-id="65680-111">请参阅，[了解敏感信息类型](sensitive-information-type-learn-about.md)。</span><span class="sxs-lookup"><span data-stu-id="65680-111">See, [Learn about sensitive information types](sensitive-information-type-learn-about.md).</span></span> <span data-ttu-id="65680-112">了解以下角色至关重要：</span><span class="sxs-lookup"><span data-stu-id="65680-112">It is critical to understand the roles of:</span></span>
    - <span data-ttu-id="65680-113">[正则表达式](https://www.boost.org/doc/libs/1_68_0/libs/regex/doc/html/) - Microsoft 365 敏感信息类型使用 Boost.RegEx 5.1.3 引擎</span><span class="sxs-lookup"><span data-stu-id="65680-113">[regular expressions](https://www.boost.org/doc/libs/1_68_0/libs/regex/doc/html/) - Microsoft 365 sensitive information types uses the Boost.RegEx 5.1.3 engine</span></span>
    - <span data-ttu-id="65680-114">关键字列表 - 可以在定义敏感信息类型或从现有关键字列表中选择时创建自己的关键字列表</span><span class="sxs-lookup"><span data-stu-id="65680-114">keyword lists - you can create your own as you define your sensitive information type or choose from existing keyword lists</span></span>
    - [<span data-ttu-id="65680-115">关键字字典</span><span class="sxs-lookup"><span data-stu-id="65680-115">keyword dictionary</span></span>](create-a-keyword-dictionary.md)
    - [<span data-ttu-id="65680-116">函数</span><span class="sxs-lookup"><span data-stu-id="65680-116">functions</span></span>](what-the-dlp-functions-look-for.md)
    - [<span data-ttu-id="65680-117">可信度</span><span class="sxs-lookup"><span data-stu-id="65680-117">confidence levels</span></span>](sensitive-information-type-learn-about.md#more-on-confidence-levels)
 
- <span data-ttu-id="65680-118">必须拥有全局管理员或合规性管理员权限，以便可以通过 UI 创建、测试和部署自定义的敏感信息类型。</span><span class="sxs-lookup"><span data-stu-id="65680-118">You must have Global admin or Compliance admin permissions to create, test, and deploy a custom sensitive information type through the UI.</span></span> <span data-ttu-id="65680-119">请参阅 Office 365 中的[关于管理员角色](/office365/admin/add-users/about-admin-roles)。</span><span class="sxs-lookup"><span data-stu-id="65680-119">See [About admin roles](/office365/admin/add-users/about-admin-roles) in Office 365.</span></span>

- <span data-ttu-id="65680-120">组织必须具有包含数据丢失防护 (DLP) 的订阅（如 Office 365 企业版）。</span><span class="sxs-lookup"><span data-stu-id="65680-120">Your organization must have a subscription, such as Office 365 Enterprise, that includes Data Loss Prevention (DLP).</span></span> <span data-ttu-id="65680-121">请参阅[邮件策略和合规性服务说明](/office365/servicedescriptions/exchange-online-protection-service-description/messaging-policy-and-compliance-servicedesc)。</span><span class="sxs-lookup"><span data-stu-id="65680-121">See [Messaging Policy and Compliance ServiceDescription](/office365/servicedescriptions/exchange-online-protection-service-description/messaging-policy-and-compliance-servicedesc).</span></span> 


> [!IMPORTANT]
> <span data-ttu-id="65680-122">在创建自定义分类或正则表达式模式时，不可从 Microsoft 客户服务和支持获取帮助。</span><span class="sxs-lookup"><span data-stu-id="65680-122">Microsoft Customer Service & Support can't assist with creating custom classifications or regular expression patterns.</span></span> <span data-ttu-id="65680-123">支持工程师可对功能提供有限的支持，例如提供用于测试目的的示例正则表达式，或者帮助排查未如期触发的现有正则表达式模式的问题，但无法保证所有自定义内容匹配开发都将满足你的要求或义务。</span><span class="sxs-lookup"><span data-stu-id="65680-123">Support engineers can provide limited support for the feature, such as, providing sample regular expression patterns for testing purposes, or assisting with troubleshooting an existing regular expression pattern that's not triggering as expected, but can't provide assurances that any custom content-matching development will fulfill your requirements or obligations.</span></span>

## <a name="create-a-custom-sensitive-information-type"></a><span data-ttu-id="65680-124">创建自定义敏感信息类型</span><span class="sxs-lookup"><span data-stu-id="65680-124">Create a custom sensitive information type</span></span>

<span data-ttu-id="65680-125">使用以下步骤可以创建完全定义的新敏感信息类型。</span><span class="sxs-lookup"><span data-stu-id="65680-125">Use this procedure to create a new sensitive information type that you fully define.</span></span> 

1. <span data-ttu-id="65680-126">在“合规中心”中，转到“**数据分类**”\>“**敏感信息类型**”，然后选择“**创建信息类型**”。</span><span class="sxs-lookup"><span data-stu-id="65680-126">In the Compliance Center, go to **Data classification** \> **Sensitive info types** and choose **Create info type**.</span></span>
2. <span data-ttu-id="65680-127">填写“**名称**”和“**说明**” 的值，然后选择“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="65680-127">Fill in values for **Name** and **Description** and choose **Next**.</span></span>
3. <span data-ttu-id="65680-128">选择“**创建模式**”。</span><span class="sxs-lookup"><span data-stu-id="65680-128">Choose **Create pattern**.</span></span> <span data-ttu-id="65680-129">在定义新的敏感信息类型时，可以创建多个模式，每个模式具有不同的元素和置信度。</span><span class="sxs-lookup"><span data-stu-id="65680-129">You can create multiple patterns, each with different elements and confidence levels, as you define your new sensitive information type.</span></span>
4. <span data-ttu-id="65680-130">选择模式的默认可信度。</span><span class="sxs-lookup"><span data-stu-id="65680-130">Choose the default confidence level for the pattern.</span></span> <span data-ttu-id="65680-131">这些值是“**低可信度**”、“**中可信度**”和“**高可信度**”。</span><span class="sxs-lookup"><span data-stu-id="65680-131">The values are **Low confidence**, **Medium confidence**, and **High confidence**.</span></span>
5. <span data-ttu-id="65680-132">选择并定义 **主要元素**。</span><span class="sxs-lookup"><span data-stu-id="65680-132">Choose and define **Primary element**.</span></span> <span data-ttu-id="65680-133">主要元素可以是带有可选验证程序的 **正则表达式**、**关键字列表**、**关键字字典** 或预先配置的 **函数** 之一。</span><span class="sxs-lookup"><span data-stu-id="65680-133">The primary element can be a **Regular expression** with an optional validator, a **Keyword list**, a **Keyword dictionary**, or one of the pre-configured **Functions**.</span></span> <span data-ttu-id="65680-134">有关 DLP 函数的详细信息，请参阅 [DLP 函数查找的内容](what-the-dlp-functions-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="65680-134">For more information on DLP functions, see [What the DLP functions look for](what-the-dlp-functions-look-for.md).</span></span> <span data-ttu-id="65680-135">有关日期和校验和验证程序的信息，请参阅有关 [正则表达式验证程序详细信息](#more-information-on-regular-expression-validators)。</span><span class="sxs-lookup"><span data-stu-id="65680-135">For more information on the date and the checksum validators, see [More information on regular expression validators](#more-information-on-regular-expression-validators).</span></span>
6. <span data-ttu-id="65680-136">填写 **字符领近度** 的值。</span><span class="sxs-lookup"><span data-stu-id="65680-136">Fill in a value for **Character proximity**.</span></span>
7. <span data-ttu-id="65680-137">（可选）添加支持元素（如有）。</span><span class="sxs-lookup"><span data-stu-id="65680-137">(Optional) Add supporting elements if you have any.</span></span> <span data-ttu-id="65680-138">支持元素可以是带有可选验证程序的正则表达式、关键字列表、关键字字典或预定义的函数之一。</span><span class="sxs-lookup"><span data-stu-id="65680-138">Supporting elements can be a regular expression with an optional validator, a keyword list, a keyword dictionary or one of the pre-defined functions.</span></span> <span data-ttu-id="65680-139">支持元素可以有自己的 **字符邻近** 度配置。</span><span class="sxs-lookup"><span data-stu-id="65680-139">Supporting elements can have their own **Character proximity** configuration.</span></span> 
8. <span data-ttu-id="65680-140">（可选）从可用检查列表中添加任何 [**其他检查**](#more-information-on-additional-checks)。</span><span class="sxs-lookup"><span data-stu-id="65680-140">(Optional) Add any [**additional checks**](#more-information-on-additional-checks) from the list of available checks.</span></span>
9. <span data-ttu-id="65680-141">选择“**创建**”。</span><span class="sxs-lookup"><span data-stu-id="65680-141">Choose **Create**.</span></span>
10. <span data-ttu-id="65680-142">选择“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="65680-142">Choose **Next**.</span></span>
11. <span data-ttu-id="65680-143">为此敏感信息类型选择 **建议的可信度**。</span><span class="sxs-lookup"><span data-stu-id="65680-143">Choose the **recommended confidence level** for this sensitive information type.</span></span>
12. <span data-ttu-id="65680-144">检查设置并选择“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="65680-144">Check your setting and choose **Submit**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="65680-145">Microsoft 365 使用搜索爬网程序来确定 SharePoint Online 和 OneDrive for Business 网站中的敏感信息并对其分类。</span><span class="sxs-lookup"><span data-stu-id="65680-145">Microsoft 365 uses the search crawler to identify and classify sensitive information in SharePoint Online and OneDrive for Business sites.</span></span> <span data-ttu-id="65680-146">要确定现有内容中新的自定义敏感信息类型，必须对该内容重新爬网。</span><span class="sxs-lookup"><span data-stu-id="65680-146">To identify your new custom sensitive information type in existing content, the content must be re-crawled.</span></span> <span data-ttu-id="65680-147">根据计划对内容进行爬网，但你可手动重新爬网内容来查找网站集、列表或库。</span><span class="sxs-lookup"><span data-stu-id="65680-147">Content is crawled based on a schedule, but you can manually re-crawl content for a site collection, list, or library.</span></span> <span data-ttu-id="65680-148">有关详细信息，请参阅[Manually request crawling and re-indexing of a site, a library or a list](/sharepoint/crawl-site-content)（手动请求对网站、库或列表进行爬网和重新编制索引）。</span><span class="sxs-lookup"><span data-stu-id="65680-148">For more information, see [Manually request crawling and re-indexing of a site, a library or a list](/sharepoint/crawl-site-content).</span></span>

13. <span data-ttu-id="65680-149">在“**数据分类**”页面上，将看到列出的所有敏感信息类型。</span><span class="sxs-lookup"><span data-stu-id="65680-149">On the **Data classification** page, you'll see all the sensitive information types listed.</span></span> <span data-ttu-id="65680-150">选择“**刷新**”，然后浏览或使用搜索工具查找你创建的敏感信息类型。</span><span class="sxs-lookup"><span data-stu-id="65680-150">Choose **Refresh** and then browse for or use the search tool to find the sensitive information type you created.</span></span>

## <a name="test-a-sensitive-information-type"></a><span data-ttu-id="65680-151">测试敏感信息类型</span><span class="sxs-lookup"><span data-stu-id="65680-151">Test a sensitive information type</span></span>

<span data-ttu-id="65680-152">可以测试列表中的任何敏感信息类型。</span><span class="sxs-lookup"><span data-stu-id="65680-152">You can test any sensitive information type in the list.</span></span> <span data-ttu-id="65680-153">我们建议在策略中使用之前，测试创建的每种敏感信息类型。</span><span class="sxs-lookup"><span data-stu-id="65680-153">We suggest that you test every sensitive information type that you create before using it in a policy.</span></span>

1. <span data-ttu-id="65680-154">准备两个文件，比如 Word 文档。</span><span class="sxs-lookup"><span data-stu-id="65680-154">Prepare two files, like a Word document.</span></span> <span data-ttu-id="65680-155">一个包含与敏感信息类型中指定的元素匹配的内容，另一个不匹配。</span><span class="sxs-lookup"><span data-stu-id="65680-155">One with content that matches the elements you specified in your sensitive information type and one that doesn't match.</span></span>
2. <span data-ttu-id="65680-156">在“合规中心”中，转到“**数据分类**”\>“**敏感信息类型**”，然后从列表中选择敏感信息类型，以打开“详细信息”窗格并选择“**测试**”。</span><span class="sxs-lookup"><span data-stu-id="65680-156">In the Compliance Center, go to **Data classification** \> **Sensitive info types** and choose the sensitive information type from the list to open the details pane and choose **Test**.</span></span>
3. <span data-ttu-id="65680-157">上传文件并选择“**测试**”。</span><span class="sxs-lookup"><span data-stu-id="65680-157">Upload a file and choose **Test**.</span></span>
4. <span data-ttu-id="65680-158">在“**匹配结果**”页面上，查看结果并选择“**完成**”。</span><span class="sxs-lookup"><span data-stu-id="65680-158">On the **Matches results** page, review the results and choose **Finish**.</span></span>

## <a name="modify-custom-sensitive-information-types-in-the-compliance-center"></a><span data-ttu-id="65680-159">在合规中心内修改自定义敏感信息类型</span><span class="sxs-lookup"><span data-stu-id="65680-159">Modify custom sensitive information types in the Compliance Center</span></span>

1. <span data-ttu-id="65680-160">在“合规中心”中，转到“**数据分类**”\>“**敏感信息类型**”，然后从要修改的列表中选择敏感信息类型，然后选择“**编辑**”。</span><span class="sxs-lookup"><span data-stu-id="65680-160">In the Compliance Center, go to **Data classification** \> **Sensitive info types** and choose the sensitive information type from the list that you want to modify choose **Edit**.</span></span>
2. <span data-ttu-id="65680-161">可以添加其他模式，其中包括唯一的主元素和支持元素、可信度、字符邻近度和 [**其他检查**](#more-information-on-additional-checks)，或者编辑/删除现有的模式。</span><span class="sxs-lookup"><span data-stu-id="65680-161">You can add other patterns, with unique primary and supporting elements, confidence levels, character proximity, and [**additional checks**](#more-information-on-additional-checks) or edit/remove the existing ones.</span></span>

## <a name="remove-custom-sensitive-information-types-in-the-compliance-center"></a><span data-ttu-id="65680-162">移除合规中心中的自定义敏感信息类型</span><span class="sxs-lookup"><span data-stu-id="65680-162">Remove custom sensitive information types in the Compliance Center</span></span> 

> [!NOTE]
> <span data-ttu-id="65680-163">只能删除自定义敏感信息类型；不能删除内置敏感信息类型。</span><span class="sxs-lookup"><span data-stu-id="65680-163">You can only remove custom sensitive information types; you can't remove built-in sensitive information types.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="65680-164">删除自定义敏感信息类型前，请先验证没有 DLP 策略或 Exchange 邮件流规则（亦称为“传输规则”）仍在引用此敏感信息类型。</span><span class="sxs-lookup"><span data-stu-id="65680-164">Before your remove a custom sensitive information type, verify that no DLP policies or Exchange mail flow rules (also known as transport rules) still reference the sensitive information type.</span></span>

1. <span data-ttu-id="65680-165">在“合规中心”中，转到“**数据分类**”\>“**敏感信息类型**”，然后从列表中选择要删除的敏感信息类型。</span><span class="sxs-lookup"><span data-stu-id="65680-165">In the Compliance Center, go to **Data classification** \> **Sensitive info types** and choose the sensitive information type from the list that you want to remove.</span></span>
2. <span data-ttu-id="65680-166">在打开的浮出控件中，选择“**删除**”。</span><span class="sxs-lookup"><span data-stu-id="65680-166">In the fly-out that opens, choose **Delete**.</span></span>

## <a name="copy-and-modify-a-sensitive-information-type"></a><span data-ttu-id="65680-167">复制和修改敏感信息类型</span><span class="sxs-lookup"><span data-stu-id="65680-167">Copy and modify a sensitive information type</span></span>

<span data-ttu-id="65680-168">使用以下步骤可以创建基于现有敏感信息类型的新敏感信息类型。</span><span class="sxs-lookup"><span data-stu-id="65680-168">Use this procedure to create a new sensitive information type that is based on an existing sensitive information type.</span></span> 

1. <span data-ttu-id="65680-169">在“合规中心”中，转到“**数据分类**”\>“**敏感信息类型**”，然后选择要复制的敏感信息类型。</span><span class="sxs-lookup"><span data-stu-id="65680-169">In the Compliance Center, go to **Data classification** \> **Sensitive info types** and choose the sensitive information type that you want to copy.</span></span>
2. <span data-ttu-id="65680-170">在浮出控件中，选择“**复制**”。</span><span class="sxs-lookup"><span data-stu-id="65680-170">In the flyout, choose **Copy**.</span></span>
3. <span data-ttu-id="65680-171">在敏感信息类型列表中选择“**刷新**”，然后浏览或搜索刚刚创建的副本。</span><span class="sxs-lookup"><span data-stu-id="65680-171">Choose **Refresh** in the list of sensitive information types and either browse or search for the copy you just made.</span></span> <span data-ttu-id="65680-172">部分字串搜索有用，所以可以只搜索 `copy`，搜索将返回名称中包含 `copy` 文字的所有敏感信息类型。</span><span class="sxs-lookup"><span data-stu-id="65680-172">Partial sting searches work, so you could just search for `copy` and search would return all the sensitive information types with the word `copy` in the name.</span></span> 
4. <span data-ttu-id="65680-173">填写“**名称**”和“**说明**” 的值，然后选择“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="65680-173">Fill in values for **Name** and **Description** and choose **Next**.</span></span>
5. <span data-ttu-id="65680-174">选择敏感信息类型“副本”，然后选择“**编辑**”。</span><span class="sxs-lookup"><span data-stu-id="65680-174">Choose your sensitive information type copy and choose **Edit**.</span></span> 
6. <span data-ttu-id="65680-175">为新的敏感信息类型提供新“**名称**”和“**描述**”。</span><span class="sxs-lookup"><span data-stu-id="65680-175">Give your new sensitive information type a new **Name** and **Description**.</span></span>
7. <span data-ttu-id="65680-176">您可以选择编辑或删除现有模式，以及添加新模式。</span><span class="sxs-lookup"><span data-stu-id="65680-176">You can choose to edit or remove the existing patterns and add new ones.</span></span> <span data-ttu-id="65680-177">选择新模式的默认可信度。</span><span class="sxs-lookup"><span data-stu-id="65680-177">Choose the default confidence level for the new pattern.</span></span> <span data-ttu-id="65680-178">这些值是“**低可信度**”、“**中可信度**”和“**高可信度**”。</span><span class="sxs-lookup"><span data-stu-id="65680-178">The values are **Low confidence**, **Medium confidence**, and **High confidence**.</span></span>
8. <span data-ttu-id="65680-179">选择并定义 **主要元素**。</span><span class="sxs-lookup"><span data-stu-id="65680-179">Choose and define **Primary element**.</span></span> <span data-ttu-id="65680-180">主要元素可以是 **正则表达式**、**关键字列表**、**关键字字典** 或预先配置的 **函数** 之一。</span><span class="sxs-lookup"><span data-stu-id="65680-180">The primary element can be a **Regular expression**, a **Keyword list**, a **Keyword dictionary**, or one of the pre-configured **Functions**.</span></span> <span data-ttu-id="65680-181">请参阅，[DLP 函数查找的内容](what-the-dlp-functions-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="65680-181">See, [What the DLP functions look for](what-the-dlp-functions-look-for.md).</span></span>
9. <span data-ttu-id="65680-182">填写 **字符领近度** 的值。</span><span class="sxs-lookup"><span data-stu-id="65680-182">Fill in a value for **Character proximity**.</span></span>
10. <span data-ttu-id="65680-183">（可选）如果有 **支持元素** 或任何 [**其他检查**](#more-information-on-additional-checks)，请添加它们。</span><span class="sxs-lookup"><span data-stu-id="65680-183">(Optional) If you have **Supporting elements** or any [**Additional checks**](#more-information-on-additional-checks) add them.</span></span> <span data-ttu-id="65680-184">如果需要，可以将你的 **支持元素** 分组。</span><span class="sxs-lookup"><span data-stu-id="65680-184">If needed you can group your **Supporting elements**.</span></span>
11. <span data-ttu-id="65680-185">选择“**创建**”。</span><span class="sxs-lookup"><span data-stu-id="65680-185">Choose **Create**.</span></span>
12. <span data-ttu-id="65680-186">选择“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="65680-186">Choose **Next**.</span></span>
13. <span data-ttu-id="65680-187">为此敏感信息类型选择 **建议的可信度**。</span><span class="sxs-lookup"><span data-stu-id="65680-187">Choose the **recommended confidence level** for this sensitive information type.</span></span>
14. <span data-ttu-id="65680-188">检查设置并选择“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="65680-188">Check your setting and choose **Submit**.</span></span>

<span data-ttu-id="65680-189">此外，还可以使用 PowerShell 和精确的数据匹配功能创建自定义敏感信息类型。</span><span class="sxs-lookup"><span data-stu-id="65680-189">You can also create custom sensitive information types by using PowerShell and Exact Data Match capabilities.</span></span> <span data-ttu-id="65680-190">若要了解有关这些方法的详细信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="65680-190">To learn more about those methods, see:</span></span>
- [<span data-ttu-id="65680-191">使用安全与合规中心 PowerShell 创建自定义敏感信息类型</span><span class="sxs-lookup"><span data-stu-id="65680-191">Create a custom sensitive information type in Security & Compliance Center PowerShell</span></span>](create-a-custom-sensitive-information-type-in-scc-powershell.md)
- [<span data-ttu-id="65680-192">使用精确数据匹配 (EDM) 为 DLP 创建自定义敏感信息类型</span><span class="sxs-lookup"><span data-stu-id="65680-192">Create a custom sensitive information type for DLP with Exact Data Match (EDM)</span></span>](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)

## <a name="more-information-on-regular-expression-validators"></a><span data-ttu-id="65680-193">有关正则表达式验证程序详细信息</span><span class="sxs-lookup"><span data-stu-id="65680-193">More information on regular expression validators</span></span>

### <a name="checksum-validator"></a><span data-ttu-id="65680-194">校验和验证程序</span><span class="sxs-lookup"><span data-stu-id="65680-194">Checksum validator</span></span>

<span data-ttu-id="65680-195">如果需要对正则表达式中的数字运行校验和，可以使用 *校验和验证程序*。</span><span class="sxs-lookup"><span data-stu-id="65680-195">If you need to run a checksum on a digit in a regular expression, you can use the *checksum validator*.</span></span> <span data-ttu-id="65680-196">例如，假设你需要为八位数的许可证号码创建 SIT，其中最后一个数字是校验和数字，使用 mod 9 计算进行验证。</span><span class="sxs-lookup"><span data-stu-id="65680-196">For example, say you need to create a SIT for an eight digit license number where the last digit is a checksum digit that is validated using a mod 9 calculation.</span></span> <span data-ttu-id="65680-197">你已设置校验和算法，如下所示：</span><span class="sxs-lookup"><span data-stu-id="65680-197">You've set up the checksum algorithm like this:</span></span>
 
<span data-ttu-id="65680-198">Sum = digit 1 \* Weight 1 + digit 2 \* weight 2 + digit 3 \* weight 3 + digit 4 \* weight 4 + digit 5 \* weight 5 + digit 6 \* weight 6 + digit 7 \* weight 7 + digit 8 \* weight 8 Mod value = Sum % 9 If Mod value == digit 8 Account number is valid If Mod value ！= digit 8 Account number is invalid</span><span class="sxs-lookup"><span data-stu-id="65680-198">Sum = digit 1 \* Weight 1 + digit 2 \* weight 2 + digit 3 \* weight 3 + digit 4 \* weight 4 + digit 5 \* weight 5 + digit 6 \* weight 6 + digit 7 \* weight 7 + digit 8 \* weight 8 Mod value = Sum % 9 If Mod value == digit 8 Account number is valid If Mod value != digit 8 Account number is invalid</span></span>

1. <span data-ttu-id="65680-199">定义具有此正则表达式的主元素：</span><span class="sxs-lookup"><span data-stu-id="65680-199">Define the primary element with this regular expression:</span></span>

`\d{8}`

2. <span data-ttu-id="65680-200">然后添加校验和验证程序。</span><span class="sxs-lookup"><span data-stu-id="65680-200">Then add the checksum validator.</span></span>
3. <span data-ttu-id="65680-201">添加用逗号分隔的权重值、检查数字的位置和 Mod 值。</span><span class="sxs-lookup"><span data-stu-id="65680-201">Add the weight values separated by commas, the position of the check digit and the Mod value.</span></span> <span data-ttu-id="65680-202">有关 Modulo 操作详细信息，请参阅 [Modulo 操作](https://en.wikipedia.org/wiki/Modulo_operation)。</span><span class="sxs-lookup"><span data-stu-id="65680-202">For more information on the Modulo operation, see [Modulo operation](https://en.wikipedia.org/wiki/Modulo_operation).</span></span>

> [!NOTE]
> <span data-ttu-id="65680-203">如果校验位不是校验和计算的一部分，则使用 0 作为校验位的权重。</span><span class="sxs-lookup"><span data-stu-id="65680-203">If the check digit is not part of the checksum calculation then use 0 as the weight for the check digit.</span></span> <span data-ttu-id="65680-204">例如，如果检查数字不用于计算检查数字，则上述情况下权重 8 将等于 0。</span><span class="sxs-lookup"><span data-stu-id="65680-204">For example, in the above case weight 8 will be equal to 0 if the check digit is not to be used for calculating the check digit.</span></span>  <span data-ttu-id="65680-205">Modulo_operation) 。</span><span class="sxs-lookup"><span data-stu-id="65680-205">Modulo_operation).</span></span>

![已配置的校验和验证器的屏幕截图](../media/checksum-validator.png)

### <a name="date-validator"></a><span data-ttu-id="65680-207">日期验证程序</span><span class="sxs-lookup"><span data-stu-id="65680-207">Date validator</span></span>

<span data-ttu-id="65680-208">如果嵌入在正则表达式中的日期值是正在创建的新模式的一部分，可以使用日期验证程序测试它是否满足您的条件。</span><span class="sxs-lookup"><span data-stu-id="65680-208">If a date value that is embedded in regular expression is part of a new pattern you are creating, you can use the *date validator* to test that it meets your criteria.</span></span> <span data-ttu-id="65680-209">例如，假设你要为九位数的员工标识号创建 SIT。</span><span class="sxs-lookup"><span data-stu-id="65680-209">For example, say you want to create a SIT for a nine digit employee identification number.</span></span> <span data-ttu-id="65680-210">前六个数字是 DDMMYY 格式的雇用日期，后三个数字是随机生成的数字。</span><span class="sxs-lookup"><span data-stu-id="65680-210">The first six digits are the date of hire in DDMMYY format and the last three are randomly generated numbers.</span></span> <span data-ttu-id="65680-211">验证前六个数字的格式是否正确。</span><span class="sxs-lookup"><span data-stu-id="65680-211">To validate that the first six digits are in the correct format.</span></span> 

1. <span data-ttu-id="65680-212">定义具有此正则表达式的主元素：</span><span class="sxs-lookup"><span data-stu-id="65680-212">Define the primary element with this regular expression:</span></span>

`\d{9}`

2. <span data-ttu-id="65680-213">然后添加日期验证程序。</span><span class="sxs-lookup"><span data-stu-id="65680-213">Then add the date validator.</span></span>
3. <span data-ttu-id="65680-214">选择日期格式和开始偏移。</span><span class="sxs-lookup"><span data-stu-id="65680-214">Select the date format and the start offset.</span></span> <span data-ttu-id="65680-215">由于日期字符串是前六个数字，因此偏移量是 `0` 。</span><span class="sxs-lookup"><span data-stu-id="65680-215">Since the date string is the first six digits, the offset is `0`.</span></span>

![已配置日期验证器的屏幕截图](../media/date-validator.png)

### <a name="functional-processors-as-validators"></a><span data-ttu-id="65680-217">作为验证程序的功能处理器</span><span class="sxs-lookup"><span data-stu-id="65680-217">Functional processors as validators</span></span>

<span data-ttu-id="65680-218">你可以对一些最常用的 SIT 使用函数处理器作为验证程序。</span><span class="sxs-lookup"><span data-stu-id="65680-218">You can use function processors for some of the most commonly used SITs as validators.</span></span> <span data-ttu-id="65680-219">这允许你定义自己的正则表达式，同时确保它们通过 SIT 所需的其他检查。</span><span class="sxs-lookup"><span data-stu-id="65680-219">This allows you to define your own regular expression while ensuring they pass the additional checks required by the SIT.</span></span> <span data-ttu-id="65680-220">例如，Func_India_Aadhar将确保您定义的自定义正则表达式传递了为"印度 Aadhar"卡所需的验证逻辑。</span><span class="sxs-lookup"><span data-stu-id="65680-220">For example, Func_India_Aadhar will ensure that the custom regular expression defined by you passes the validation logic required for Indian Aadhar card.</span></span> <span data-ttu-id="65680-221">有关可以用作验证符的 DLP 函数详细信息，请参阅 [DLP 函数查找什么](what-the-dlp-functions-look-for.md#what-the-dlp-functions-look-for)。</span><span class="sxs-lookup"><span data-stu-id="65680-221">For more information on DLP functions that can be used as validators, see [What the DLP functions look for](what-the-dlp-functions-look-for.md#what-the-dlp-functions-look-for).</span></span> 

### <a name="luhn-check-validator"></a><span data-ttu-id="65680-222">Luhn 检查验证程序</span><span class="sxs-lookup"><span data-stu-id="65680-222">Luhn check validator</span></span>

<span data-ttu-id="65680-223">如果您具有包含应传递 Luhn 算法的正则表达式的自定义敏感信息类型，您可以使用 [Luhn 检查验证程序](https://en.wikipedia.org/wiki/Luhn_algorithm)。</span><span class="sxs-lookup"><span data-stu-id="65680-223">You can use the Luhn check validator if you have a custom Sensitive information type that includes a regular expression which should pass the [Luhn algorithm](https://en.wikipedia.org/wiki/Luhn_algorithm).</span></span>

## <a name="more-information-on-additional-checks"></a><span data-ttu-id="65680-224">关于其他检查的详细信息</span><span class="sxs-lookup"><span data-stu-id="65680-224">More information on additional checks</span></span>

<span data-ttu-id="65680-225">以下是可用的其他检查的定义和一些示例。</span><span class="sxs-lookup"><span data-stu-id="65680-225">Here are the definitions and some examples for the available additional checks.</span></span>

<span data-ttu-id="65680-226">**排除特定匹配**：在为正在编辑的模式检测匹配时，此检查允许定义关键词以进行排除。</span><span class="sxs-lookup"><span data-stu-id="65680-226">**Exclude specific matches**: This check lets you define keywords to exclude when detecting matches for the pattern you are editing.</span></span> <span data-ttu-id="65680-227">例如，你可能排除测试信用卡号（如 4111111111111111），以便其不会作为有效号码进行匹配。</span><span class="sxs-lookup"><span data-stu-id="65680-227">For example, you might exclude test credit card numbers like '4111111111111111' so that they're not matched as a valid number.</span></span>

<span data-ttu-id="65680-228">**以或不以字符开头**：此检查允许定义字符，匹配项必须或禁止以其开头。</span><span class="sxs-lookup"><span data-stu-id="65680-228">**Starts or doesn't start with characters**: This check lets you define the characters that the matched items must or must not start with.</span></span> <span data-ttu-id="65680-229">例如，如果希望模式仅检测以 41、42 或 43 开头的信用卡号码，请选择“**开头为**”，然后向列表中添加 41、42 和 43，并以逗号分隔。</span><span class="sxs-lookup"><span data-stu-id="65680-229">For example, if you want the pattern to detect only credit card numbers that start with 41, 42, or 43, select **Starts with** and add 41, 42, and 43 to the list, separated by commas.</span></span> 

<span data-ttu-id="65680-230">**以或不以字符结尾**：此检查允许定义字符，匹配项必须或禁止以其结尾。</span><span class="sxs-lookup"><span data-stu-id="65680-230">**Ends or doesn't end with characters**: This check lets you define the characters that the matched items must or must not end with.</span></span> <span data-ttu-id="65680-231">例如，如果员工 ID 号不能以 0 或 1 结尾，请选择“**结尾不可为**”，然后向列表添加 0 和 1，并用逗号分隔。</span><span class="sxs-lookup"><span data-stu-id="65680-231">For example, if your Employee ID number cannot end with 0 or 1, select **Doesn't end with** and add 0 and 1 to the list, separated by commas.</span></span>

<span data-ttu-id="65680-232">**排除重复字符**：此检查允许忽略所有数字都相同的匹配项。</span><span class="sxs-lookup"><span data-stu-id="65680-232">**Exclude duplicate characters**: This check lets you ignore matches in which all the digits are the same.</span></span> <span data-ttu-id="65680-233">例如，如果六位数员工 ID 号码不能都是相同数字，可以选择“**排除重复字符**”，以从员工 ID 的有效匹配列表中排除 111111、222222、333333、444444、555555、666666、777777、888888、999999 和 000000。</span><span class="sxs-lookup"><span data-stu-id="65680-233">For example, if the six digit employee ID number cannot have all the digits be the same, you can select **Exclude duplicate characters** to exclude 111111, 222222, 333333, 444444, 555555, 666666, 777777, 888888, 999999, and 000000 from the list of valid matches for the employee ID.</span></span>

<span data-ttu-id="65680-234">**包括或排除前缀**：此检查可定义在匹配实体之前必须或不得立即找到的关键字。</span><span class="sxs-lookup"><span data-stu-id="65680-234">**Include or exclude prefixes**: This check lets you define the keywords that must or must not be found immediately before the matching entity.</span></span> <span data-ttu-id="65680-235">如果实体前面带有此处包含的前缀，则这些实体将匹配或不匹配，具体取决于你的选择。</span><span class="sxs-lookup"><span data-stu-id="65680-235">Depending on your selection, entities will be matched or not matched if they're preceded by the prefixes you include here.</span></span> <span data-ttu-id="65680-236">例如，如果 **排除** 前缀 **GUID：**，则将不会把前缀为 **GUID：** 的任何实体视为匹配项。</span><span class="sxs-lookup"><span data-stu-id="65680-236">For example, if you **Exclude** the prefix **GUID:**, any entity that's preceded by **GUID:** won't be considered a match.</span></span>

<span data-ttu-id="65680-237">**包括或排除后缀** 此检查可定义在匹配实体之后必须或不得立即找到的关键字。</span><span class="sxs-lookup"><span data-stu-id="65680-237">**Include or exclude suffixes** This check lets you define the keywords that must or must not be found immediately after the matching entity.</span></span> <span data-ttu-id="65680-238">如果实体后面是此处包含的后缀，则实体将匹配或不匹配，具体取决于你的选择。</span><span class="sxs-lookup"><span data-stu-id="65680-238">Depending on your selection, entities will be matched or not matched if they're followed by the suffixes you include here.</span></span> <span data-ttu-id="65680-239">例如，如果 **排除** 后缀 **：GUID**，则后附 **：GUID** 的任何文本将不匹配。</span><span class="sxs-lookup"><span data-stu-id="65680-239">For example, if you **Exclude** the suffix **:GUID**, any text that's followed by **:GUID** won't be matched.</span></span>


> [!NOTE]
> <span data-ttu-id="65680-240">Microsoft 365信息保护支持双字节字符集语言，</span><span class="sxs-lookup"><span data-stu-id="65680-240">Microsoft 365 Information Protection supports double byte character set languages for:</span></span>
> - <span data-ttu-id="65680-241">简体中文</span><span class="sxs-lookup"><span data-stu-id="65680-241">Chinese (simplified)</span></span>
> - <span data-ttu-id="65680-242">繁体中文</span><span class="sxs-lookup"><span data-stu-id="65680-242">Chinese (traditional)</span></span>
> - <span data-ttu-id="65680-243">韩语</span><span class="sxs-lookup"><span data-stu-id="65680-243">Korean</span></span>
> - <span data-ttu-id="65680-244">日语</span><span class="sxs-lookup"><span data-stu-id="65680-244">Japanese</span></span>
>
><span data-ttu-id="65680-245">此支持适用于敏感信息类型。</span><span class="sxs-lookup"><span data-stu-id="65680-245">This support is available for sensitive information types.</span></span> <span data-ttu-id="65680-246">有关详细信息，请参阅[双字节字符集的信息保护支持发行说明（预览版）](mip-dbcs-relnotes.md)。</span><span class="sxs-lookup"><span data-stu-id="65680-246">See, [Information protection support for double byte character sets release notes (preview)](mip-dbcs-relnotes.md) for more information.</span></span>

> [!TIP]
> <span data-ttu-id="65680-247">若要检测包含中文/日语字符和单个字节字符的模式，或检测包含中文/日语和英语的模式，请定义关键字或正则表达式的两个变体。</span><span class="sxs-lookup"><span data-stu-id="65680-247">To detect patterns containing Chinese/Japanese characters and single byte characters or to detect patterns containing Chinese/Japanese and English, define two variants of the keyword or regex.</span></span> <span data-ttu-id="65680-248">例如，若要检测关键字（如"添加的关键字"，请使用关键字的两个变体;一个在日语和英语文本之间带空格，另一个在日语和英语文本之间没有空格。</span><span class="sxs-lookup"><span data-stu-id="65680-248">For example, to detect a keyword like "机密的document", use two variants of the keyword; one with a space between the Japanese and English text and another without a space between the Japanese and English text.</span></span> <span data-ttu-id="65680-249">因此，要添加到 SIT 中的关键字应为"添加的 document"和"添加的 document"。</span><span class="sxs-lookup"><span data-stu-id="65680-249">So, the keywords to be added in the SIT should be "机密的 document" and "机密的document".</span></span> <span data-ttu-id="65680-250">同样，若要检测短语"オリピック2020"，应该使用两个变量;"オリオリピック 2020"和"オリピック2020"。</span><span class="sxs-lookup"><span data-stu-id="65680-250">Similarly, to detect a phrase "東京オリンピック2020", two variants should be used; "東京オリンピック 2020" and "東京オリンピック2020".</span></span>
> <span data-ttu-id="65680-251">在使用双字节连字符或双字节周期创建正则表达式时，请确保转义这两个字符，就像在正则表达式中转义连字符或周期一样。</span><span class="sxs-lookup"><span data-stu-id="65680-251">While creating a regex using a double byte hyphen or a double byte period, make sure to escape both the characters like one would escape a hyphen or period in a regex.</span></span> <span data-ttu-id="65680-252">下面是示例正则表达式，仅供参考：</span><span class="sxs-lookup"><span data-stu-id="65680-252">Here is a sample regex for reference:</span></span>
    - <span data-ttu-id="65680-253"> (？<！\d)  ([4][0-9] {3} [ \- ？\-\t\]*[0-9]{4}</span><span class="sxs-lookup"><span data-stu-id="65680-253">(?<!\d)([４][０-９]{3}[\-?\－\t]\*[０-９]{4}</span></span>
> <span data-ttu-id="65680-254">我们建议在关键字列表中使用字符串匹配而不是单词匹配。</span><span class="sxs-lookup"><span data-stu-id="65680-254">We recommend using a string match instead of a word match in a keyword list.</span></span>
