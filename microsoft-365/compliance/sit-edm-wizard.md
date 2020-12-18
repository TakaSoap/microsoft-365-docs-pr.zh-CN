---
title: 使用精确数据匹配架构和敏感信息类型向导
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.date: ''
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 学习如何使用精确数据匹配和敏感信息类型向导。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 2081de887e09794350222dac3527bb3ff932837a
ms.sourcegitcommit: 884ac262443c50362d0c3ded961d36d6b15d8b73
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/16/2020
ms.locfileid: "49699141"
---
# <a name="use-the-exact-data-match-schema-and-sensitive-information-type-wizard"></a><span data-ttu-id="42ca8-103">使用精确数据匹配架构和敏感信息类型向导</span><span class="sxs-lookup"><span data-stu-id="42ca8-103">Use the Exact Data Match Schema and Sensitive Information Type Wizard</span></span>

<span data-ttu-id="42ca8-104">[使用基于精确数据匹配 (EDM) 分类创建自定义敏感信息类型](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md) 包含多个步骤。</span><span class="sxs-lookup"><span data-stu-id="42ca8-104">[Creating a custom sensitive information type with Exact Data Match (EDM) based classification](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)  involves many steps.</span></span>  <span data-ttu-id="42ca8-105">可以使用此向导创建您的架构和敏感信息类型（规则包）文件，以帮助简化过程。</span><span class="sxs-lookup"><span data-stu-id="42ca8-105">You can use this wizard to create your schema and sensitive information type pattern (rule package) files to help simplify the process.</span></span>

> [!NOTE]
> <span data-ttu-id="42ca8-106">精确数据匹配架构和敏感信息类型向导仅用于 World Wide 和 GCC。</span><span class="sxs-lookup"><span data-stu-id="42ca8-106">The Exact Data Match Schema and Sensitive Information Type Wizard is only available for the World Wide and GCC clouds only.</span></span>

<span data-ttu-id="42ca8-107">可以使用此向导而无需：</span><span class="sxs-lookup"><span data-stu-id="42ca8-107">This wizard can be used instead of the:</span></span>

- [<span data-ttu-id="42ca8-108">定义敏感信息数据库的架构</span><span class="sxs-lookup"><span data-stu-id="42ca8-108">Define the schema for your database of sensitive information</span></span>](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#define-the-schema-for-your-database-of-sensitive-information)
- [<span data-ttu-id="42ca8-109">设置模式（规则包）</span><span class="sxs-lookup"><span data-stu-id="42ca8-109">Set up a pattern (rule package)</span></span>](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#set-up-a-rule-package)

<span data-ttu-id="42ca8-110">[第 1 部分：设置基于 EDM 的分类](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#part-1-set-up-edm-based-classification) 中的步骤。</span><span class="sxs-lookup"><span data-stu-id="42ca8-110">steps in [Part 1: Set up EDM-based classification](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#part-1-set-up-edm-based-classification).</span></span>

## <a name="pre-requisites"></a><span data-ttu-id="42ca8-111">先决条件</span><span class="sxs-lookup"><span data-stu-id="42ca8-111">Pre-requisites</span></span>

1. <span data-ttu-id="42ca8-112">通过 EDM [工作流程概览](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#the-work-flow-at-a-glance) 熟悉使用 EDM 创建自定义敏感信息类型的步骤。</span><span class="sxs-lookup"><span data-stu-id="42ca8-112">Familiarize yourself with the steps to create a custom sensitive information type with EDM [work flow at a glance](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#the-work-flow-at-a-glance).</span></span>

2. <span data-ttu-id="42ca8-113">执行 [以 .csv 格式保存敏感数据](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#save-sensitive-data-in-csv-format) 一节中的步骤。</span><span class="sxs-lookup"><span data-stu-id="42ca8-113">Perform the steps in the [Save sensitive data in .csv format](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#save-sensitive-data-in-csv-format) section.</span></span>

## <a name="use-the-exact-data-match-schema-and-sensitive-information-type-pattern-wizard"></a><span data-ttu-id="42ca8-114">使用精确数据匹配架构和敏感信息类型模式向导</span><span class="sxs-lookup"><span data-stu-id="42ca8-114">Use the exact data match schema and sensitive information type pattern wizard</span></span>

1. <span data-ttu-id="42ca8-115">在 Microsoft 365 合规中心为租户转到 **数据分类** > **精确数据匹配**。</span><span class="sxs-lookup"><span data-stu-id="42ca8-115">In the Microsoft 365 Compliance center for your tenant go to **Data classification** > **Exact data matches**.</span></span>

2. <span data-ttu-id="42ca8-116">选择 **创建 EDM 架构** 打开架构向导配置弹出菜单t。</span><span class="sxs-lookup"><span data-stu-id="42ca8-116">Choose **Create EDM schema** to open the schema wizard configuration flyout.</span></span>

![EDM 架构创建向导配置弹出菜单](../media/edm-schema-wizard-1.png)

3. <span data-ttu-id="42ca8-118">填入相应的 **名称** 和 **说明**。</span><span class="sxs-lookup"><span data-stu-id="42ca8-118">Fill in an appropriate **Name** and **Description**.</span></span>

4. <span data-ttu-id="42ca8-119">如果愿意，选择 **为所有架构字段忽略分隔符和标点符号**。</span><span class="sxs-lookup"><span data-stu-id="42ca8-119">Choose **Ignore delimiters and punctuations for all schema fields** if you want that behavior.</span></span> <span data-ttu-id="42ca8-120">若要了解配置 EDM 忽略分隔符方面的详细信息，请参阅 [使用基于精确数据匹配 (EDM) 分类创建自定义敏感信息类型](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)。</span><span class="sxs-lookup"><span data-stu-id="42ca8-120">To learn more about configuring EDM to ignore case or delimitere, see [Creating a custom sensitive information type with Exact Data Match (EDM) based classification](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md).</span></span>

5. <span data-ttu-id="42ca8-121">在 **架构字段 #1** 中填入所需值，并按需要添加新字段。</span><span class="sxs-lookup"><span data-stu-id="42ca8-121">Fill in your desired values for your **Schema field #1** and add more fields as needed.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="42ca8-122">必须指定至少 1 个，但不超过 5 个架构字段为可搜索字段。</span><span class="sxs-lookup"><span data-stu-id="42ca8-122">At least one, but no more than five of your schema fields must be designated as searchable.</span></span>

6. <span data-ttu-id="42ca8-123">选择保存。</span><span class="sxs-lookup"><span data-stu-id="42ca8-123">Choose save.</span></span> <span data-ttu-id="42ca8-124">您的架构现已加入列表。</span><span class="sxs-lookup"><span data-stu-id="42ca8-124">Your schema will now be listed.</span></span>

7. <span data-ttu-id="42ca8-125">选择 **EDM 敏感信息类型** 和 **创建 EDM 敏感信息类型** 以打开敏感信息类型配置向导。</span><span class="sxs-lookup"><span data-stu-id="42ca8-125">Choose **EDM sensitive info types** and **Create EDM sensitive info type** to open the sensitive info type configuration wizard.</span></span>

8. <span data-ttu-id="42ca8-126">选择 **选择已有的 EDM 架构**，然后从列表中选择按照步骤 2-6 所创建的架构。</span><span class="sxs-lookup"><span data-stu-id="42ca8-126">Choose **Choose an existing EDM schema** and choose the schema you created in steps 2-6 from the list.</span></span>

9. <span data-ttu-id="42ca8-127">选择 **下一步**，然后选择 **创建模式**。</span><span class="sxs-lookup"><span data-stu-id="42ca8-127">Choose **Next** and choose **Create pattern**.</span></span>

10. <span data-ttu-id="42ca8-128">选择 **可信度** 和 **主元素**。</span><span class="sxs-lookup"><span data-stu-id="42ca8-128">Choose the **Confidence level** and **Primary element**.</span></span>  <span data-ttu-id="42ca8-129">若要了解有关配置模式的详细信息，请参阅 [在合规中心中创建自定义敏感信息类型](create-a-custom-sensitive-information-type.md)</span><span class="sxs-lookup"><span data-stu-id="42ca8-129">To learn more about configuring a pattern, see [Create a custom sensitive information type in the Compliance Center](create-a-custom-sensitive-information-type.md)</span></span>

11.  <span data-ttu-id="42ca8-130">选择 **主元素敏感信息类型** 以建立关联。</span><span class="sxs-lookup"><span data-stu-id="42ca8-130">Choose the **Primary element's sensitive info type** to associate it with.</span></span> <span data-ttu-id="42ca8-131">若要了解可用敏感信息类型的详细信息，请参阅[敏感信息类型实体定义](sensitive-information-type-entity-definitions.md)。</span><span class="sxs-lookup"><span data-stu-id="42ca8-131">See [Sensitive Information Type Entity Definitions](sensitive-information-type-entity-definitions.md) to learn more about the available sensitive information types.</span></span>

12. <span data-ttu-id="42ca8-132">选择 **完成**。</span><span class="sxs-lookup"><span data-stu-id="42ca8-132">Choose **Done**.</span></span>

13. <span data-ttu-id="42ca8-133">选择所需的 **可信度和字符邻近度**。</span><span class="sxs-lookup"><span data-stu-id="42ca8-133">Choose your desired **Confidence level and character proximity**.</span></span>  <span data-ttu-id="42ca8-134">此操作将设定整个 EDM 敏感信息类型的默认值。</span><span class="sxs-lookup"><span data-stu-id="42ca8-134">This will be the default value for the whole EDM sensitive info type</span></span>

13. <span data-ttu-id="42ca8-135">若要为 EDM 敏感信息类型创建其他模式，请选择 **创建模式**。</span><span class="sxs-lookup"><span data-stu-id="42ca8-135">Choose **Create pattern** if you want to creaet additional patterns for your EDM sensitive info type.</span></span>

14. <span data-ttu-id="42ca8-136">选择 **下一步** 并填写 **名称** 和 **面向管理员的说明**。</span><span class="sxs-lookup"><span data-stu-id="42ca8-136">Choose **Next** and fill in a **Name** and **Description for admins**.</span></span>

15. <span data-ttu-id="42ca8-137">查看并选择 **提交**。</span><span class="sxs-lookup"><span data-stu-id="42ca8-137">Review and choose **Submit**.</span></span>

<span data-ttu-id="42ca8-138">通过选择编辑和删除控制面，可以删除或编辑敏感信息类型模式。</span><span class="sxs-lookup"><span data-stu-id="42ca8-138">You can delete or edit the sensitive information type pattern by selecting it which surfaces the edit and delete controls.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="42ca8-139">若要删除已经关联某一 EDM 敏感信息类型的架构，必须先删除此 EDM 敏感信息类型，然后才能删除架构。</span><span class="sxs-lookup"><span data-stu-id="42ca8-139">If you want to remove a schema, and it is already associated with an EDM sensitive info type, you must first delete the EDM sensitive info type, then you can delete the schema.</span></span>

## <a name="post-steps"></a><span data-ttu-id="42ca8-140">后续步骤</span><span class="sxs-lookup"><span data-stu-id="42ca8-140">Post steps</span></span>

<span data-ttu-id="42ca8-141">使用此向导创建 EDM 架构和模式（规则包）文件后，还必须执行 [第二部分：哈希和上传敏感数据](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#part-2-hash-and-upload-the-sensitive-data) 中的步骤，才能使用此 EDM 自定义敏感信息类型。</span><span class="sxs-lookup"><span data-stu-id="42ca8-141">After you have used this wizard to create your EDM schema and pattern (rule package) files, you still have to perform the steps in [Part 2: Hash and upload the sensitive data](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#part-2-hash-and-upload-the-sensitive-data) before you can use the EDM custom sensitive information type.</span></span>