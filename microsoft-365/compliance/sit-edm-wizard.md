---
title: 使用精确数据匹配架构和敏感信息类型向导
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
ms.date: ''
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 学习如何使用精确数据匹配和敏感信息类型向导。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 5fdf289c403d8c09342a1eac1434c4219bb7b13c
ms.sourcegitcommit: 3e971b31435d17ceeaa9871c01e88e25ead560fb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/09/2021
ms.locfileid: "52861655"
---
# <a name="use-the-exact-data-match-schema-and-sensitive-information-type-wizard"></a><span data-ttu-id="45162-103">使用精确数据匹配架构和敏感信息类型向导</span><span class="sxs-lookup"><span data-stu-id="45162-103">Use the Exact Data Match Schema and Sensitive Information Type Wizard</span></span>

<span data-ttu-id="45162-104">[使用基于精确数据匹配 (EDM) 分类创建自定义敏感信息类型](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md) 包含多个步骤。</span><span class="sxs-lookup"><span data-stu-id="45162-104">[Creating a custom sensitive information type with Exact Data Match (EDM) based classification](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)  involves many steps.</span></span>  <span data-ttu-id="45162-105">可以使用此向导创建架构和敏感信息类型， (SIT) 模式 (规则包) 文件来帮助简化此过程。</span><span class="sxs-lookup"><span data-stu-id="45162-105">You can use this wizard to create your schema and sensitive information type (SIT) pattern (rule package) files to help simplify the process.</span></span>

> [!NOTE]
> <span data-ttu-id="45162-106">精确数据匹配架构和敏感信息类型向导仅用于 World Wide 和 GCC。</span><span class="sxs-lookup"><span data-stu-id="45162-106">The Exact Data Match Schema and Sensitive Information Type Wizard is only available for the World Wide and GCC clouds only.</span></span>

<span data-ttu-id="45162-107">可以使用此向导而无需：</span><span class="sxs-lookup"><span data-stu-id="45162-107">This wizard can be used instead of the:</span></span>

- [<span data-ttu-id="45162-108">定义敏感信息数据库的架构</span><span class="sxs-lookup"><span data-stu-id="45162-108">Define the schema for your database of sensitive information</span></span>](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#define-the-schema-for-your-database-of-sensitive-information)
- [<span data-ttu-id="45162-109">设置模式（规则包）</span><span class="sxs-lookup"><span data-stu-id="45162-109">Set up a pattern (rule package)</span></span>](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#set-up-a-rule-package)

<span data-ttu-id="45162-110">[第 1 部分：设置基于 EDM 的分类](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#part-1-set-up-edm-based-classification) 中的步骤。</span><span class="sxs-lookup"><span data-stu-id="45162-110">steps in [Part 1: Set up EDM-based classification](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#part-1-set-up-edm-based-classification).</span></span>

## <a name="pre-requisites"></a><span data-ttu-id="45162-111">先决条件</span><span class="sxs-lookup"><span data-stu-id="45162-111">Pre-requisites</span></span>

1. <span data-ttu-id="45162-112">通过 EDM [工作流程概览](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#the-work-flow-at-a-glance) 熟悉使用 EDM 创建自定义敏感信息类型的步骤。</span><span class="sxs-lookup"><span data-stu-id="45162-112">Familiarize yourself with the steps to create a custom sensitive information type with EDM [work flow at a glance](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#the-work-flow-at-a-glance).</span></span>

2. <span data-ttu-id="45162-113">执行 [以 .csv 格式保存敏感数据](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#save-sensitive-data-in-csv-format) 一节中的步骤。</span><span class="sxs-lookup"><span data-stu-id="45162-113">Perform the steps in the [Save sensitive data in .csv format](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#save-sensitive-data-in-csv-format) section.</span></span>

## <a name="use-the-exact-data-match-schema-and-sensitive-information-type-pattern-wizard"></a><span data-ttu-id="45162-114">使用精确数据匹配架构和敏感信息类型模式向导</span><span class="sxs-lookup"><span data-stu-id="45162-114">Use the exact data match schema and sensitive information type pattern wizard</span></span>

1. <span data-ttu-id="45162-115">在 Microsoft 365 合规中心为租户转到 **数据分类** > **精确数据匹配**。</span><span class="sxs-lookup"><span data-stu-id="45162-115">In the Microsoft 365 Compliance center for your tenant go to **Data classification** > **Exact data matches**.</span></span>

2. <span data-ttu-id="45162-116">选择 **创建 EDM 架构** 打开架构向导配置弹出菜单t。</span><span class="sxs-lookup"><span data-stu-id="45162-116">Choose **Create EDM schema** to open the schema wizard configuration flyout.</span></span>

![EDM 架构创建向导配置弹出菜单](../media/edm-schema-wizard-1.png)

3. <span data-ttu-id="45162-118">填入相应的 **名称** 和 **说明**。</span><span class="sxs-lookup"><span data-stu-id="45162-118">Fill in an appropriate **Name** and **Description**.</span></span>

4. <span data-ttu-id="45162-119">如果需要 **此行为，** 请选择"忽略所有架构字段的分隔符和标点符号"。</span><span class="sxs-lookup"><span data-stu-id="45162-119">Choose **Ignore delimiters and punctuation for all schema fields** if you want that behavior.</span></span> <span data-ttu-id="45162-120">若要了解有关将 EDM 配置为忽略大小写或分隔符的信息，请参阅使用基于 [EDM](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)的精确数据匹配 (自定义) 类型。</span><span class="sxs-lookup"><span data-stu-id="45162-120">To learn more about configuring EDM to ignore case or delimiters, see [Creating a custom sensitive information type with Exact Data Match (EDM) based classification](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md).</span></span>

5. <span data-ttu-id="45162-121">在 **架构字段 #1** 中填入所需值，并按需要添加新字段。</span><span class="sxs-lookup"><span data-stu-id="45162-121">Fill in your desired values for your **Schema field #1** and add more fields as needed.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="45162-122">必须指定至少 1 个，但不超过 5 个架构字段为可搜索字段。</span><span class="sxs-lookup"><span data-stu-id="45162-122">At least one, but no more than five of your schema fields must be designated as searchable.</span></span>

6. <span data-ttu-id="45162-123">选择保存。</span><span class="sxs-lookup"><span data-stu-id="45162-123">Choose save.</span></span> <span data-ttu-id="45162-124">您的架构现已加入列表。</span><span class="sxs-lookup"><span data-stu-id="45162-124">Your schema will now be listed.</span></span>

7. <span data-ttu-id="45162-125">选择 **EDM 敏感信息类型** 和 **创建 EDM 敏感信息类型** 以打开敏感信息类型配置向导。</span><span class="sxs-lookup"><span data-stu-id="45162-125">Choose **EDM sensitive info types** and **Create EDM sensitive info type** to open the sensitive info type configuration wizard.</span></span>

8. <span data-ttu-id="45162-126">选择 **选择已有的 EDM 架构**，然后从列表中选择按照步骤 2-6 所创建的架构。</span><span class="sxs-lookup"><span data-stu-id="45162-126">Choose **Choose an existing EDM schema** and choose the schema you created in steps 2-6 from the list.</span></span>

9. <span data-ttu-id="45162-127">选择 **下一步**，然后选择 **创建模式**。</span><span class="sxs-lookup"><span data-stu-id="45162-127">Choose **Next** and choose **Create pattern**.</span></span>

10. <span data-ttu-id="45162-128">选择 **可信度** 和 **主元素**。</span><span class="sxs-lookup"><span data-stu-id="45162-128">Choose the **Confidence level** and **Primary element**.</span></span>  <span data-ttu-id="45162-129">若要了解有关配置模式的详细信息，请参阅 [在合规中心中创建自定义敏感信息类型](create-a-custom-sensitive-information-type.md)</span><span class="sxs-lookup"><span data-stu-id="45162-129">To learn more about configuring a pattern, see [Create a custom sensitive information type in the Compliance Center](create-a-custom-sensitive-information-type.md)</span></span>

11.  <span data-ttu-id="45162-130">选择 **主元素敏感信息类型** 以建立关联。</span><span class="sxs-lookup"><span data-stu-id="45162-130">Choose the **Primary element's sensitive info type** to associate it with.</span></span> <span data-ttu-id="45162-131">若要了解可用敏感信息类型的详细信息，请参阅[敏感信息类型实体定义](sensitive-information-type-entity-definitions.md)。</span><span class="sxs-lookup"><span data-stu-id="45162-131">See [Sensitive Information Type Entity Definitions](sensitive-information-type-entity-definitions.md) to learn more about the available sensitive information types.</span></span>

12. <span data-ttu-id="45162-132">选择 **完成**。</span><span class="sxs-lookup"><span data-stu-id="45162-132">Choose **Done**.</span></span>

13. <span data-ttu-id="45162-133">选择所需的 **可信度和字符邻近度**。</span><span class="sxs-lookup"><span data-stu-id="45162-133">Choose your desired **Confidence level and character proximity**.</span></span>  <span data-ttu-id="45162-134">此操作将设定整个 EDM 敏感信息类型的默认值。</span><span class="sxs-lookup"><span data-stu-id="45162-134">This will be the default value for the whole EDM sensitive info type</span></span>

13. <span data-ttu-id="45162-135">如果要 **为** EDM 敏感信息类型创建其他模式，请选择"创建模式"。</span><span class="sxs-lookup"><span data-stu-id="45162-135">Choose **Create pattern** if you want to create additional patterns for your EDM sensitive info type.</span></span>

14. <span data-ttu-id="45162-136">选择 **下一步** 并填写 **名称** 和 **面向管理员的说明**。</span><span class="sxs-lookup"><span data-stu-id="45162-136">Choose **Next** and fill in a **Name** and **Description for admins**.</span></span>

15. <span data-ttu-id="45162-137">查看并选择 **提交**。</span><span class="sxs-lookup"><span data-stu-id="45162-137">Review and choose **Submit**.</span></span>

<span data-ttu-id="45162-138">通过选择编辑和删除控制面，可以删除或编辑敏感信息类型模式。</span><span class="sxs-lookup"><span data-stu-id="45162-138">You can delete or edit the sensitive information type pattern by selecting it which surfaces the edit and delete controls.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="45162-139">若要删除已经关联某一 EDM 敏感信息类型的架构，必须先删除此 EDM 敏感信息类型，然后才能删除架构。</span><span class="sxs-lookup"><span data-stu-id="45162-139">If you want to remove a schema, and it is already associated with an EDM sensitive info type, you must first delete the EDM sensitive info type, then you can delete the schema.</span></span>

## <a name="post-creation-steps"></a><span data-ttu-id="45162-140">创建后的步骤</span><span class="sxs-lookup"><span data-stu-id="45162-140">Post creation steps</span></span>

<span data-ttu-id="45162-141">使用此向导创建 EDM 架构和模式（规则包）文件后，还必须执行 [第二部分：哈希和上传敏感数据](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#part-2-hash-and-upload-the-sensitive-data) 中的步骤，才能使用此 EDM 自定义敏感信息类型。</span><span class="sxs-lookup"><span data-stu-id="45162-141">After you have used this wizard to create your EDM schema and pattern (rule package) files, you still have to perform the steps in [Part 2: Hash and upload the sensitive data](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#part-2-hash-and-upload-the-sensitive-data) before you can use the EDM custom sensitive information type.</span></span>

<span data-ttu-id="45162-142">确认敏感信息表已正确上载后，可以测试其是否正常工作。</span><span class="sxs-lookup"><span data-stu-id="45162-142">After verifying that your sensitive information table has correctly been uploaded, you can test that it's working properly.</span></span>

1. <span data-ttu-id="45162-143">打开 **合规中心**  >  **数据分类**  >  **敏感信息类型**。</span><span class="sxs-lookup"><span data-stu-id="45162-143">Open **Compliance center** > **Data classification** > **Sensitive Information Types**.</span></span>
2. <span data-ttu-id="45162-144">从列表中选择 EDM SIT，然后在飞 **出窗格中** 选择"测试"。</span><span class="sxs-lookup"><span data-stu-id="45162-144">Select your EDM SIT from the list and then select **Test** in the flyout pane.</span></span> 
3. <span data-ttu-id="45162-145">Upload包含要检测的数据的项，例如创建一个包含敏感信息表中的部分数据的项。</span><span class="sxs-lookup"><span data-stu-id="45162-145">Upload an item that contains data you want to detect, for example create an item that contains some of the data in your sensitive information table.</span></span> <span data-ttu-id="45162-146">如果在架构中使用了可配置的匹配功能来定义忽略的分隔符，请确保该项包含带和不带这些分隔符的示例。</span><span class="sxs-lookup"><span data-stu-id="45162-146">If you used the configurable match feature in your schema to define ignored delimiters, make sure the item includes examples with and without those delimiters.</span></span>
4. <span data-ttu-id="45162-147">上传并扫描文件后，检查 EDM SIT 的匹配项。</span><span class="sxs-lookup"><span data-stu-id="45162-147">After the file has been uploaded and scanned, check for matches to your EDM SIT.</span></span>
5. <span data-ttu-id="45162-148">如果 **SIT** 中的 Test 函数检测到匹配项，请检查它未进行修整或提取不正确。</span><span class="sxs-lookup"><span data-stu-id="45162-148">If the **Test** function in the SIT detects a match, check that it is not trimming it or extracting it incorrectly.</span></span> <span data-ttu-id="45162-149">例如，通过仅提取它应检测的完整字符串的子字符串，或仅选取多词字符串中的第一个单词，或在提取中添加额外的符号或字符。</span><span class="sxs-lookup"><span data-stu-id="45162-149">For example by extracting only a substring of the full string it is supposed to detect, or picking up only the first word in a multi-word string, or including extra symbols or characters in the extraction.</span></span> <span data-ttu-id="45162-150">有关 [正则表达式语言参考，](/dotnet/standard/base-types/regular-expression-language-quick-reference) 请参阅正则表达式语言 - 快速参考。</span><span class="sxs-lookup"><span data-stu-id="45162-150">See [Regular Expression Language - Quick Reference](/dotnet/standard/base-types/regular-expression-language-quick-reference) for the regular expression language reference.</span></span> 

### <a name="troubleshooting"></a><span data-ttu-id="45162-151">疑难解答</span><span class="sxs-lookup"><span data-stu-id="45162-151">Troubleshooting</span></span>

<span data-ttu-id="45162-152">如果找不到任何匹配项，请尝试执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="45162-152">If you don't find any matches, try the following:</span></span>
- <span data-ttu-id="45162-153">使用使用 [EDM](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)工具上传敏感数据的指南中介绍的命令确认你的敏感数据已正确上载。</span><span class="sxs-lookup"><span data-stu-id="45162-153">Confirm that your sensitive data was uploaded correctly using the commands explained in [the guidance for uploading your sensitive data using the EDM tool](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md).</span></span>
- <span data-ttu-id="45162-154">检查在项中输入的示例是否存在于敏感信息表中，以及忽略的分隔符是否正确。</span><span class="sxs-lookup"><span data-stu-id="45162-154">Check that the examples you entered in the item are present in your sensitive information table and that the ignored delimiters are correct.</span></span>
- <span data-ttu-id="45162-155">**测试** 在每个模式中配置主元素时所使用的 SIT。</span><span class="sxs-lookup"><span data-stu-id="45162-155">**Test** the SIT you used when you configured the primary element in each of your patterns.</span></span> <span data-ttu-id="45162-156">这将确认 SIT 能够匹配项中的示例。</span><span class="sxs-lookup"><span data-stu-id="45162-156">This will confirm that the SIT is able to match the examples in the item.</span></span> 
  -  <span data-ttu-id="45162-157">如果为 EDM 类型中的主元素选择的 SIT 在项中找不到匹配项或找到的匹配项数低于预期，请检查它是否支持存在于内容中的分隔符和分隔符。</span><span class="sxs-lookup"><span data-stu-id="45162-157">If the SIT you selected for a primary element in the EDM type doesn't find a match in the item or finds fewer matches than you expected, check that it supports separators and delimiters that exist in the content.</span></span> <span data-ttu-id="45162-158">请务必在架构中包括定义的忽略分隔符。</span><span class="sxs-lookup"><span data-stu-id="45162-158">Be sure to include the ignored delimiters defined in your schema.</span></span> 
  -  <span data-ttu-id="45162-159">如果 **Test** 函数完全检测不到任何内容，请检查所选的 SIT 是否包含其他关键字或其他验证的要求。</span><span class="sxs-lookup"><span data-stu-id="45162-159">If the **Test** function does not detect any content at all, check if the SIT you selected includes requirements for additional keywords or other validations.</span></span> <span data-ttu-id="45162-160">有关内置 SIT，请参阅敏感信息类型 [实体](sensitive-information-type-entity-definitions.md) 定义，以验证匹配每种类型的最低要求。</span><span class="sxs-lookup"><span data-stu-id="45162-160">For the built-in SITs, see [Sensitive information types entity definitions](sensitive-information-type-entity-definitions.md) to verify what the minimum requirements are for matching each type.</span></span>
