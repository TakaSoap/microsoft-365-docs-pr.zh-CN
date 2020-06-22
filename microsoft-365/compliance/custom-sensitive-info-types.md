---
title: DLP 自定义敏感信息类型
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.date: 04/23/2019
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 获取有关数据丢失防护 (DLP) 的自定义敏感信息类型的概述，如主要模式、字符接近度和可信度级别。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 6934edba6eef03bc9d4bfc5c1c69f127a7d3a0e5
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/19/2020
ms.locfileid: "44817961"
---
# <a name="custom-sensitive-information-types"></a><span data-ttu-id="7206b-103">自定义敏感信息类型</span><span class="sxs-lookup"><span data-stu-id="7206b-103">Custom sensitive information types</span></span>

<span data-ttu-id="7206b-104">Microsoft 365 包括许多你可直接在组织中使用的内置敏感信息类型，包括用于[数据丢失保护](data-loss-prevention-policies.md) (DLP) 或 [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security)。</span><span class="sxs-lookup"><span data-stu-id="7206b-104">Microsoft 365 includes many built-in sensitive information types that are ready for you to use in your organization, such as for [data loss prevention](data-loss-prevention-policies.md) (DLP), or with [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security).</span></span> <span data-ttu-id="7206b-105">内置敏感信息类型可以根据正则表达式 (regex) 或函数定义的模式，帮助标识和保护信用卡号、银行账号、护照号等。</span><span class="sxs-lookup"><span data-stu-id="7206b-105">Built-in sensitive information types can help identify and protect credit card numbers, bank account numbers, passport numbers, and more, based on patterns that are defined by a regular expression (regex) or a function.</span></span> <span data-ttu-id="7206b-106">若要了解详细信息，请参阅[敏感信息类型查找的内容](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="7206b-106">To learn more, see [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>

<span data-ttu-id="7206b-107">但是，如果需要标识和保护使用组织特定格式的不同敏感信息类型，如员工 ID 或项目号，那该怎么办？</span><span class="sxs-lookup"><span data-stu-id="7206b-107">But what if you need to identify and protect a different type of sensitive information, such as for employee IDs or project numbers, using a format that's specific to your organization?</span></span> <span data-ttu-id="7206b-108">为此，你可以创建自定义敏感信息类型。</span><span class="sxs-lookup"><span data-stu-id="7206b-108">To do this, you can create a custom sensitive information type.</span></span>

<span data-ttu-id="7206b-109">自定义敏感信息类型的基本组成部分是：</span><span class="sxs-lookup"><span data-stu-id="7206b-109">The fundamental parts of a custom sensitive information type are:</span></span>

- <span data-ttu-id="7206b-110">**主要模式**：员工 ID 号、项目编号等。这通常是由正则表达式 (RegEx) 标识，但也可以是关键字列表。</span><span class="sxs-lookup"><span data-stu-id="7206b-110">**Primary pattern**: employee ID numbers, project numbers, etc. This is typically identified by a regular expression (RegEx), but it can also be a list of keywords.</span></span>

- <span data-ttu-id="7206b-111">**Additional evidence**: Suppose you're looking for a nine-digit employee ID number.</span><span class="sxs-lookup"><span data-stu-id="7206b-111">**Additional evidence**: Suppose you're looking for a nine-digit employee ID number.</span></span> <span data-ttu-id="7206b-112">Not all nine-digit numbers are employee ID numbers, so you can look for additional text: keywords like "employee", "badge", "ID", or other text patterns based on additional regular expressions.</span><span class="sxs-lookup"><span data-stu-id="7206b-112">Not all nine-digit numbers are employee ID numbers, so you can look for additional text: keywords like "employee", "badge", "ID", or other text patterns based on additional regular expressions.</span></span> <span data-ttu-id="7206b-113">This supporting evidence (also known as _supporting_ or _corroborative_ evidence) increases the likelihood that nine-digit number found in content is really an employee ID number.</span><span class="sxs-lookup"><span data-stu-id="7206b-113">This supporting evidence (also known as _supporting_ or _corroborative_ evidence) increases the likelihood that nine-digit number found in content is really an employee ID number.</span></span>

- <span data-ttu-id="7206b-114">**Character proximity**: It makes sense that the closer the primary pattern and the supporting evidence are to each other, the more likely the detected content is going to be what you're looking for.</span><span class="sxs-lookup"><span data-stu-id="7206b-114">**Character proximity**: It makes sense that the closer the primary pattern and the supporting evidence are to each other, the more likely the detected content is going to be what you're looking for.</span></span> <span data-ttu-id="7206b-115">You can specify the character distance between the primary pattern and the supporting evidence (also known as the _proximity window_) as shown in the following diagram:</span><span class="sxs-lookup"><span data-stu-id="7206b-115">You can specify the character distance between the primary pattern and the supporting evidence (also known as the _proximity window_) as shown in the following diagram:</span></span>

    ![确证性证据和临近度窗口的关系图](../media/dc68e38e-dfa1-45b8-b204-89c8ba121f96.png)

- <span data-ttu-id="7206b-117">**Confidence level**: The more supporting evidence you have, the higher the likelihood that a match contains the sensitive information you're looking for.</span><span class="sxs-lookup"><span data-stu-id="7206b-117">**Confidence level**: The more supporting evidence you have, the higher the likelihood that a match contains the sensitive information you're looking for.</span></span> <span data-ttu-id="7206b-118">You can assign higher levels of confidence for matches that are detected by using more evidence.</span><span class="sxs-lookup"><span data-stu-id="7206b-118">You can assign higher levels of confidence for matches that are detected by using more evidence.</span></span>

  <span data-ttu-id="7206b-119">When satisfied, a pattern returns a count and confidence level, which you can use in the conditions in your DLP policies.</span><span class="sxs-lookup"><span data-stu-id="7206b-119">When satisfied, a pattern returns a count and confidence level, which you can use in the conditions in your DLP policies.</span></span> <span data-ttu-id="7206b-120">When you add a condition for detecting a sensitive information type to a DLP policy, you can edit the count and confidence level as shown in the following diagram:</span><span class="sxs-lookup"><span data-stu-id="7206b-120">When you add a condition for detecting a sensitive information type to a DLP policy, you can edit the count and confidence level as shown in the following diagram:</span></span>

    ![“实例计数”和“匹配准确度”选项](../media/11d0b51e-7c3f-4cc6-96d8-b29bcdae1aeb.png)

## <a name="creating-custom-sensitive-information-types"></a><span data-ttu-id="7206b-122">创建自定义敏感信息类型</span><span class="sxs-lookup"><span data-stu-id="7206b-122">Creating custom sensitive information types</span></span>

<span data-ttu-id="7206b-123">若要在安全与合规中心内创建自定义敏感信息类型，可使用以下几种方法：</span><span class="sxs-lookup"><span data-stu-id="7206b-123">To create custom sensitive information types in the Security & Compliance Center, you can choose from several options:</span></span>

- <span data-ttu-id="7206b-124">**使用 EDM**（新方法！）可以使用基于精确数据匹配 (EDM) 的分类创建自定义敏感信息类型。</span><span class="sxs-lookup"><span data-stu-id="7206b-124">**Use EDM** (NEW!) You can set up custom sensitive information types using Exact Data Match (EDM)-based classification.</span></span> <span data-ttu-id="7206b-125">通过此方法，你可以使用可定期刷新的安全数据库创建动态敏感信息类型。</span><span class="sxs-lookup"><span data-stu-id="7206b-125">This method enables you to create a dynamic sensitive information type using a secure database that you can refresh periodically.</span></span> <span data-ttu-id="7206b-126">请参阅[使用基于精确数据匹配的分类创建自定义敏感信息类型](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)。</span><span class="sxs-lookup"><span data-stu-id="7206b-126">See [Create a custom sensitive information type with Exact Data Match based classification](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md).</span></span>

- <span data-ttu-id="7206b-127">**使用 PowerShell** 可以使用 PowerShell 创建自定义敏感信息类型。</span><span class="sxs-lookup"><span data-stu-id="7206b-127">**Use PowerShell** You can set up custom sensitive information types using PowerShell.</span></span> <span data-ttu-id="7206b-128">尽管此方法比使用 UI 更复杂，但你可以拥有更多的配置选项。</span><span class="sxs-lookup"><span data-stu-id="7206b-128">Although this method is more complex than using the UI, you have more configuration options.</span></span> <span data-ttu-id="7206b-129">请参阅[使用安全与合规中心 PowerShell 创建自定义敏感信息类型](create-a-custom-sensitive-information-type-in-scc-powershell.md)。</span><span class="sxs-lookup"><span data-stu-id="7206b-129">See [Create a custom sensitive information type in Security & Compliance Center PowerShell](create-a-custom-sensitive-information-type-in-scc-powershell.md).</span></span>

- <span data-ttu-id="7206b-130">**使用 UI** 可以使用安全与合规中心 UI 创建自定义敏感信息类型。</span><span class="sxs-lookup"><span data-stu-id="7206b-130">**Use the UI** You can set up a custom sensitive information type using the Security & Compliance Center UI.</span></span> <span data-ttu-id="7206b-131">通过此方法，你可以使用正则表达式、关键字和关键字字典。</span><span class="sxs-lookup"><span data-stu-id="7206b-131">With this method, you can use regular expressions, keywords, and keyword dictionaries.</span></span> <span data-ttu-id="7206b-132">若要了解详细信息，请参阅[创建自定义敏感信息类型](create-a-custom-sensitive-information-type.md)。</span><span class="sxs-lookup"><span data-stu-id="7206b-132">To learn more, see [Create a custom sensitive information type](create-a-custom-sensitive-information-type.md).</span></span>



