---
title: 自定义敏感信息类型筛选器参考
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 本文提供可以编码为自定义敏感信息类型的筛选器列表。
ms.openlocfilehash: 6dfa562d581f14c0b1ac41c4ce803e2367a94636
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2021
ms.locfileid: "53322499"
---
# <a name="custom-sensitive-information-type-filters-reference"></a><span data-ttu-id="04296-103">自定义敏感信息类型筛选器参考</span><span class="sxs-lookup"><span data-stu-id="04296-103">Custom sensitive information type filters reference</span></span>

<span data-ttu-id="04296-104">在 Microsoft 中，可以在使用 SIT 策略创建自定义敏感信息类型时定义 (或其他) 。</span><span class="sxs-lookup"><span data-stu-id="04296-104">In Microsoft you can define filters or additional checks while creating a custom sensitive information types (SIT).</span></span>

## <a name="list-of-supported-filters-and-use-cases"></a><span data-ttu-id="04296-105">支持的筛选器和用例列表</span><span class="sxs-lookup"><span data-stu-id="04296-105">List of supported filters and use cases</span></span>

### <a name="alldigitssame-exclude"></a><span data-ttu-id="04296-106">AllDigitsSame 排除</span><span class="sxs-lookup"><span data-stu-id="04296-106">AllDigitsSame Exclude</span></span>

<span data-ttu-id="04296-107">说明：允许您排除所有数字为重复数字的匹配项，如 1111111111 或 111-111-111</span><span class="sxs-lookup"><span data-stu-id="04296-107">Description: Allows you to exclude matches which have all digits as duplicate digits, like 111111111 or 111-111-111</span></span>

<span data-ttu-id="04296-108">定义筛选器</span><span class="sxs-lookup"><span data-stu-id="04296-108">Defining filters</span></span>
```xml
<Filters id="ssn_filters">
    <Filter type="AllDigitsSameFilter"></Filter>
</Filters>
```

<span data-ttu-id="04296-109">在实体级别的规则包中使用它</span><span class="sxs-lookup"><span data-stu-id="04296-109">Using it in rule package at the entity level</span></span>
```xml
<Entity id="50842eb7-edc8-4019-85dd-5a5c1f2bb085" patternsProximity="300" recommendedConfidence="85"  filters="ssn_filters">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_ssn" />
      </Pattern>
</Entity>
```

<span data-ttu-id="04296-110">在模式级别的规则包中使用它</span><span class="sxs-lookup"><span data-stu-id="04296-110">Using it in rule package at the pattern level</span></span>
```xml
<Entity id="50842eb7-edc8-4019-85dd-5a5c1f2bb085" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85"  filters="ssn_filters">
        <IdMatch idRef="Func_ssn" />
      </Pattern>
</Entity>
```

### <a name="textmatchfilter-startswith"></a><span data-ttu-id="04296-111">TextMatchFilter StartsWith</span><span class="sxs-lookup"><span data-stu-id="04296-111">TextMatchFilter StartsWith</span></span> 

<span data-ttu-id="04296-112">说明：允许您定义实体的起始字符。</span><span class="sxs-lookup"><span data-stu-id="04296-112">Description: Allows you to define the starting characters for the entity.</span></span> <span data-ttu-id="04296-113">它具有两种变体，即 include 和 exclude。</span><span class="sxs-lookup"><span data-stu-id="04296-113">It has two variants, include and exclude.</span></span>

<span data-ttu-id="04296-114">例如，在列表中排除以 0500、91、091、010 开始的数字，如下所示：</span><span class="sxs-lookup"><span data-stu-id="04296-114">For example to exclude the numbers starting with 0500, 91, 091, 010 in a list like this:</span></span>

- <span data-ttu-id="04296-115">0500-4500-027</span><span class="sxs-lookup"><span data-stu-id="04296-115">0500-4500-027</span></span>
- <span data-ttu-id="04296-116">91564721450</span><span class="sxs-lookup"><span data-stu-id="04296-116">91564721450</span></span>
- <span data-ttu-id="04296-117">91-8523697410</span><span class="sxs-lookup"><span data-stu-id="04296-117">91-8523697410</span></span>
- <span data-ttu-id="04296-118">700-8956-7844</span><span class="sxs-lookup"><span data-stu-id="04296-118">700-8956-7844</span></span>
- <span data-ttu-id="04296-119">1000-3265-9874</span><span class="sxs-lookup"><span data-stu-id="04296-119">1000-3265-9874</span></span>
- <span data-ttu-id="04296-120">0100-7892-3012</span><span class="sxs-lookup"><span data-stu-id="04296-120">0100-7892-3012</span></span>

<span data-ttu-id="04296-121">可以使用此 xml</span><span class="sxs-lookup"><span data-stu-id="04296-121">you can use this xml</span></span>

```xml
<Filters id="phone_number_filters_exc">
    <Filter type="TextMatchFilter" direction="StartsWith" logic="Exclude" textProcessorId="Keyword_false_positives_sw">
</Filter>
</Filters>

  <Keyword id="Keyword_false_positives_sw">
    <Group matchStyle="string">
      <Term>0500</Term>
      <Term>91</Term>
      <Term>091</Term>
      <Term>0100</Term>
    </Group>
  </Keyword>
```
<span data-ttu-id="04296-122">例如，在列表中包含以 0500、91、091、0100 开始的数字，如下所示：</span><span class="sxs-lookup"><span data-stu-id="04296-122">For example, to include the numbers starting with 0500, 91, 091, 0100 in a list like this:</span></span> 

- <span data-ttu-id="04296-123">0500-4500-027</span><span class="sxs-lookup"><span data-stu-id="04296-123">0500-4500-027</span></span>
- <span data-ttu-id="04296-124">91564721450</span><span class="sxs-lookup"><span data-stu-id="04296-124">91564721450</span></span>
- <span data-ttu-id="04296-125">91-8523697410</span><span class="sxs-lookup"><span data-stu-id="04296-125">91-8523697410</span></span>
- <span data-ttu-id="04296-126">700-8956-7844</span><span class="sxs-lookup"><span data-stu-id="04296-126">700-8956-7844</span></span>
- <span data-ttu-id="04296-127">1000-3265-9874</span><span class="sxs-lookup"><span data-stu-id="04296-127">1000-3265-9874</span></span>
- <span data-ttu-id="04296-128">0100-7892-3012</span><span class="sxs-lookup"><span data-stu-id="04296-128">0100-7892-3012</span></span>

<span data-ttu-id="04296-129">可以使用此 xml</span><span class="sxs-lookup"><span data-stu-id="04296-129">you can use this xml</span></span>

```xml
<Filters id="phone_filters_inc">
    <Filter type="TextMatchFilter" direction="StartsWith" logic="Include" textProcessorId="Keyword_false_positives_sw">
</Filter>
```

### <a name="textmatchfilter-endswith"></a><span data-ttu-id="04296-130">TextMatchFilter EndsWith</span><span class="sxs-lookup"><span data-stu-id="04296-130">TextMatchFilter EndsWith</span></span> 

<span data-ttu-id="04296-131">说明：允许您定义实体的结束字符。</span><span class="sxs-lookup"><span data-stu-id="04296-131">Description: Allows you to define the ending characters for the entity.</span></span> 

<span data-ttu-id="04296-132">例如，要排除列表中以 0500，91，091， 0100 结尾的数字，如下所示：</span><span class="sxs-lookup"><span data-stu-id="04296-132">For example, to exclude the numbers ending with 0500,91,091, 0100 in a list like this:</span></span>

- <span data-ttu-id="04296-133">1234567891</span><span class="sxs-lookup"><span data-stu-id="04296-133">1234567891</span></span>
- <span data-ttu-id="04296-134">1234-5678-0091</span><span class="sxs-lookup"><span data-stu-id="04296-134">1234-5678-0091</span></span>
- <span data-ttu-id="04296-135">1234.4567.7091</span><span class="sxs-lookup"><span data-stu-id="04296-135">1234.4567.7091</span></span>
- <span data-ttu-id="04296-136">1234-8091-4564</span><span class="sxs-lookup"><span data-stu-id="04296-136">1234-8091-4564</span></span>

<span data-ttu-id="04296-137">可以使用此 xml</span><span class="sxs-lookup"><span data-stu-id="04296-137">you can use this xml</span></span>

```xml
<Filters id="phone_number_filters_exc">
    <Filter type="TextMatchFilter" direction="EndsWith" logic="Exclude" textProcessorId="Keyword_false_positives_sw">
</Filter>

  <Keyword id="Keyword_false_positives_sw">
    <Group matchStyle="string">
      <Term>0500</Term>
      <Term>91</Term>
      <Term>091</Term>
      <Term>0100</Term>
    </Group>
  </Keyword>
```

<span data-ttu-id="04296-138">例如，将以 0500、91、091、0100 结尾的数字包括在如下所示的列表中：</span><span class="sxs-lookup"><span data-stu-id="04296-138">For example, to include the numbers ending with 0500, 91, 091, 0100, in a list like this:</span></span>

- <span data-ttu-id="04296-139">1234567891</span><span class="sxs-lookup"><span data-stu-id="04296-139">1234567891</span></span>
- <span data-ttu-id="04296-140">1234-5678-0091</span><span class="sxs-lookup"><span data-stu-id="04296-140">1234-5678-0091</span></span>
- <span data-ttu-id="04296-141">1234.4567.7091</span><span class="sxs-lookup"><span data-stu-id="04296-141">1234.4567.7091</span></span>
- <span data-ttu-id="04296-142">1234-8091-4564</span><span class="sxs-lookup"><span data-stu-id="04296-142">1234-8091-4564</span></span>

<span data-ttu-id="04296-143">可以使用此 xml</span><span class="sxs-lookup"><span data-stu-id="04296-143">you can use this xml</span></span>

```xml
<Filters id="phone_filters_inc">
    <Filter type="TextMatchFilter" direction=" EndsWith" logic="Include" textProcessorId="Keyword_false_positives_sw">
</Filter>
```

### <a name="textmatchfilter-full"></a><span data-ttu-id="04296-144">TextMatchFilter Full</span><span class="sxs-lookup"><span data-stu-id="04296-144">TextMatchFilter Full</span></span>

<span data-ttu-id="04296-145">说明：允许您禁止某些匹配，以防止它们触发规则。</span><span class="sxs-lookup"><span data-stu-id="04296-145">Description: Allows you to prohibit certain matches to prevent them from triggering the rule.</span></span> <span data-ttu-id="04296-146">例如，从有效信用卡匹配列表中排除 411111111111111。</span><span class="sxs-lookup"><span data-stu-id="04296-146">For example, exclude 4111111111111111 from the list of valid credit card matches.</span></span>

<span data-ttu-id="04296-147">例如，要排除列表中类似 4111111111111111111 和 32418910311131111 的信用卡号，如下所示：</span><span class="sxs-lookup"><span data-stu-id="04296-147">For example, to exclude credit card numbers like 4111111111111111 and 3241891031113111 in a list like this:</span></span>

- <span data-ttu-id="04296-148">4485 3647 3952 7352</span><span class="sxs-lookup"><span data-stu-id="04296-148">4485 3647 3952 7352</span></span>
- <span data-ttu-id="04296-149">4111111111111111</span><span class="sxs-lookup"><span data-stu-id="04296-149">4111111111111111</span></span>
- <span data-ttu-id="04296-150">3241891031113111</span><span class="sxs-lookup"><span data-stu-id="04296-150">3241891031113111</span></span>

<span data-ttu-id="04296-151">可以使用此 xml</span><span class="sxs-lookup"><span data-stu-id="04296-151">you can use this xml</span></span>

```xml
<Filters id="cc_number_filters_exc">
    <Filter type="TextMatchFilter" direction="Full" logic="Exclude" textProcessorId="Keyword_false_positives_full">
</Filter>

  <Keyword id="Keyword_false_positives_full">
    <Group matchStyle="string">
      <Term>4111111111111111</Term>
      <Term>3241891031113111</Term>
    </Group>
  </Keyword>
```

<span data-ttu-id="04296-152">例如，若要在列表中包括信用卡号（如 411111111111111111111 和 32418910311131111111，如下所示）：</span><span class="sxs-lookup"><span data-stu-id="04296-152">For example, to include credit card numbers like 4111111111111111 and 3241891031113111 in a list like this:</span></span>

- <span data-ttu-id="04296-153">4485 3647 3952 7352</span><span class="sxs-lookup"><span data-stu-id="04296-153">4485 3647 3952 7352</span></span>
- <span data-ttu-id="04296-154">4111111111111111</span><span class="sxs-lookup"><span data-stu-id="04296-154">4111111111111111</span></span>
- <span data-ttu-id="04296-155">3241891031113111</span><span class="sxs-lookup"><span data-stu-id="04296-155">3241891031113111</span></span>

<span data-ttu-id="04296-156">可以使用此 xml</span><span class="sxs-lookup"><span data-stu-id="04296-156">you can use this xml</span></span>

```xml
<Filters id="cc_filters_inc">
    <Filter type="TextMatchFilter" direction="Full" logic="Include" textProcessorId="Keyword_false_positives_full">
</Filter>
```

### <a name="textmatchfilter-prefix"></a><span data-ttu-id="04296-157">TextMatchFilter 前缀</span><span class="sxs-lookup"><span data-stu-id="04296-157">TextMatchFilter Prefix</span></span>

<span data-ttu-id="04296-158">说明：允许你定义应始终包含或排除的前面字符。</span><span class="sxs-lookup"><span data-stu-id="04296-158">Description: Allows you to define the preceding characters that should be always included or excluded.</span></span> <span data-ttu-id="04296-159">例如，如果信用卡号前面有"订单 ID："，则从有效匹配项中删除匹配项。</span><span class="sxs-lookup"><span data-stu-id="04296-159">For example, if Credit card number is preceded by ‘Order ID:’ then remove the match from the valid matches.</span></span>

<span data-ttu-id="04296-160">例如，要排除包含电话号码的电话号码电话，在类似以下的列表中，在电话号码前的字符串下呼叫我：</span><span class="sxs-lookup"><span data-stu-id="04296-160">For example, to exclude occurrences of phone numbers which have **Phone number** and **call me at** strings before the phone number, in a list like this:</span></span>

- <span data-ttu-id="04296-161">电话号码 091-8974-653278</span><span class="sxs-lookup"><span data-stu-id="04296-161">phone number 091-8974-653278</span></span>
- <span data-ttu-id="04296-162">电话 45-124576532-123</span><span class="sxs-lookup"><span data-stu-id="04296-162">Phone 45-124576532-123</span></span>
- <span data-ttu-id="04296-163">45-124576532-123</span><span class="sxs-lookup"><span data-stu-id="04296-163">45-124576532-123</span></span>

<span data-ttu-id="04296-164">可以使用此 xml</span><span class="sxs-lookup"><span data-stu-id="04296-164">you can use this xml</span></span>

```xml
<Filters id="cc_number_filters_exc">
    <Filter type="TextMatchFilter" direction="Prefix" logic="Exclude" textProcessorId="Keyword_false_positives_prefix">
</Filter>
  <Keyword id="Keyword_false_positives_prefix">
    <Group matchStyle="string">
      <Term>phone number</Term>
      <Term>call me at</Term>
    </Group>
  </Keyword>
```

<span data-ttu-id="04296-165">例如，若要在信用卡号前包含信用卡和卡 **#** 字符串，在如下所示的列表中包含：</span><span class="sxs-lookup"><span data-stu-id="04296-165">For example, to include occurrences that have **credit card** and **card #** strings before the credit card number, in a list like this:</span></span>

- <span data-ttu-id="04296-166">信用卡 45-124576532-123</span><span class="sxs-lookup"><span data-stu-id="04296-166">Credit card 45-124576532-123</span></span> 
- <span data-ttu-id="04296-167">45-124576532-123 (可以是电话号码) </span><span class="sxs-lookup"><span data-stu-id="04296-167">45-124576532-123  (which could be phone number)</span></span>

<span data-ttu-id="04296-168">可以使用此 xml</span><span class="sxs-lookup"><span data-stu-id="04296-168">you can use this xml</span></span>

```xml
<Filters id="cc_filters_inc">
    <Filter type="TextMatchFilter" direction="Full" logic="Include" textProcessorId="Keyword_true_positives_prefix">
</Filter>

  <Keyword id="Keyword_true_positives_prefix">
    <Group matchStyle="string">
      <Term>credit card</Term>
      <Term>card #</Term>
    </Group>
  </Keyword
```

### <a name="textmatchfilter-suffix"></a><span data-ttu-id="04296-169">TextMatchFilter 后缀</span><span class="sxs-lookup"><span data-stu-id="04296-169">TextMatchFilter Suffix</span></span>

<span data-ttu-id="04296-170">说明：允许你定义应始终包含或排除的以下字符。</span><span class="sxs-lookup"><span data-stu-id="04296-170">Description: Allows you to define the following characters that should be always included or excluded.</span></span> <span data-ttu-id="04296-171">例如，如果信用卡号后跟"/xuid"，则从有效匹配项中删除匹配项。</span><span class="sxs-lookup"><span data-stu-id="04296-171">For example, if Credit card number is followed by ‘/xuid’ then remove the match from the valid matches.</span></span>

<span data-ttu-id="04296-172">例如，如果列表中还有 5 个包含四个数字的实例作为后缀，则排除顶部，如下所示：</span><span class="sxs-lookup"><span data-stu-id="04296-172">For example, top exclude occurrences if there are 5 more instances of four digits as suffix in a list like this:</span></span>

- <span data-ttu-id="04296-173">1234-5678-9321 4500 9870 6321 48925566</span><span class="sxs-lookup"><span data-stu-id="04296-173">1234-5678-9321 4500 9870 6321 48925566</span></span>
- <span data-ttu-id="04296-174">1234-5678-9321</span><span class="sxs-lookup"><span data-stu-id="04296-174">1234-5678-9321</span></span>

<span data-ttu-id="04296-175">可以使用此 xml</span><span class="sxs-lookup"><span data-stu-id="04296-175">you can use this xml</span></span>

```xml
<Filters id="cc_number_filters_exc">
    <Filter type="TextMatchFilter" direction="Prefix" logic="Exclude" textProcessorId="Regex_false_positives_suffix">
</Filter>

  <Regexid="Regex_false_positives_suffix">(\d{4}){5,}</Regex>
```
<span data-ttu-id="04296-176">例如，若要排除后跟 **/xuidsuffix** 的事件，如此列表中的一个：</span><span class="sxs-lookup"><span data-stu-id="04296-176">For example, to exclude occurrences if they are followed by **/xuidsuffix**, like one in this list:</span></span>

- <span data-ttu-id="04296-177">1234-5678-9321 /xuid</span><span class="sxs-lookup"><span data-stu-id="04296-177">1234-5678-9321 /xuid</span></span>
- <span data-ttu-id="04296-178">1234-5678-9321</span><span class="sxs-lookup"><span data-stu-id="04296-178">1234-5678-9321</span></span>

<span data-ttu-id="04296-179">可以使用此 xml</span><span class="sxs-lookup"><span data-stu-id="04296-179">you can use this xml</span></span>

<span data-ttu-id="04296-180">''xml <Filters id="cc_number_filters_exc"></span><span class="sxs-lookup"><span data-stu-id="04296-180">\`\`xml <Filters id="cc_number_filters_exc"></span></span>
    <Filter type="TextMatchFilter" direction="Prefix" logic="Exclude" textProcessorId="Keyword_false_positives_suffix">
</Filter>

  <span data-ttu-id="04296-181"><Keyword id="Keyword_false_positives_suffix"> <Group matchStyle="string">
      </span><span class="sxs-lookup"><span data-stu-id="04296-181"><Keyword id="Keyword_false_positives_suffix"> <Group matchStyle="string">
      </span></span><Term><span data-ttu-id="04296-182">/xuid</span><span class="sxs-lookup"><span data-stu-id="04296-182">/xuid</span></span></Term>
    <span data-ttu-id="04296-183"></Group> </Keyword></span><span class="sxs-lookup"><span data-stu-id="04296-183"></Group> </Keyword></span></span>
```

For example, to include an occurrence only if it is followed by **cvv** or **expires**, like two in this list:

- 45-124576532-123 
- 45-124576532-123  cvv 966
- 45-124576532-123  expires 03/23

you can use this xml

```xml
<Filters id="cc_filters_inc">
    <Filter type="TextMatchFilter" direction="Full" logic="Include" textProcessorId="Keyword_true_positives_suffix">
</Filter>

  <Keyword id="Keyword_true_positives_suffix">
    <Group matchStyle="string">
      <Term>cvv</Term>
      <Term>expires</Term>
    </Group>
  </Keyword>
```

## <a name="using-filters-in-rule-packages"></a><span data-ttu-id="04296-184">使用规则包中的筛选器</span><span class="sxs-lookup"><span data-stu-id="04296-184">Using filters in rule packages</span></span>

<span data-ttu-id="04296-185">可以在整个 SIT 或模式中定义筛选器。</span><span class="sxs-lookup"><span data-stu-id="04296-185">Filters can be defined on the entire SIT or on a pattern.</span></span> <span data-ttu-id="04296-186">下面是一些代码段示例。</span><span class="sxs-lookup"><span data-stu-id="04296-186">Here are some code snippets examples.</span></span> 

### <a name="at-sensitive-information-type-level"></a><span data-ttu-id="04296-187">在敏感信息类型级别</span><span class="sxs-lookup"><span data-stu-id="04296-187">At sensitive information type level</span></span>

<span data-ttu-id="04296-188">Entity 中的筛选器 - 将涵盖所有子模式</span><span class="sxs-lookup"><span data-stu-id="04296-188">Filters at Entity - will cover all child patterns</span></span>

<span data-ttu-id="04296-189">筛选器将应用于该实体/敏感类型中任何模式分类的所有实例</span><span class="sxs-lookup"><span data-stu-id="04296-189">The filters will be applied on **all** the instances classified by any of the patterns in that entity / sensitive type</span></span>

```xml
<Entity id="6443b88f-2808-482a-8e1a-3ae5026645e1" patternsProximity="300" recommendedConfidence="85" filters="CompositeFiltersAtEntityLevel">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Regex_denmark_id" />
      </Pattern>
</Entity>
```

### <a name="at-the-individual-pattern-of-the-sensitive-information-type-level"></a><span data-ttu-id="04296-190">在敏感信息类型级别的单个模式</span><span class="sxs-lookup"><span data-stu-id="04296-190">At the individual pattern of the sensitive information type level</span></span>

<span data-ttu-id="04296-191">仅在模式级别进行筛选。</span><span class="sxs-lookup"><span data-stu-id="04296-191">Filters only at the pattern level.</span></span>

<span data-ttu-id="04296-192">筛选器将应用于与模式匹配的实例。</span><span class="sxs-lookup"><span data-stu-id="04296-192">The filter will be applied on the instances matched by the pattern.</span></span>

```xml
<Entity id="50842eb7-edc8-4019-85dd-5a5c1f2bb085" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85"  filters="CompositeFiltersAtPattern">
        <IdMatch idRef="Keyword_cc_verification" />
      </Pattern>
</Entity>
```


### <a name="at-sensitive-information-type-level-and-an-additional-filter-on-some-of-the-patterns-of-that-entity"></a><span data-ttu-id="04296-193">在敏感信息类型级别，以及该实体的一些模式的其他筛选器</span><span class="sxs-lookup"><span data-stu-id="04296-193">At sensitive information type level and an additional filter on some of the patterns of that entity</span></span>

<span data-ttu-id="04296-194">实体 + 模式的筛选器</span><span class="sxs-lookup"><span data-stu-id="04296-194">Filters at Entity + pattern</span></span>

<span data-ttu-id="04296-195">筛选器将 **应用于该实体** /敏感类型中任何模式分类的所有实例。</span><span class="sxs-lookup"><span data-stu-id="04296-195">The filters will be applied on **all** the instances classified by any of the patterns in that entity / sensitive type.</span></span> <span data-ttu-id="04296-196">模式级别筛选器将筛选该模式匹配的实例。</span><span class="sxs-lookup"><span data-stu-id="04296-196">The pattern level filter will filter the instances matched by that pattern.</span></span>

```xml
<Entity id="6443b88f-2808-482a-8e1a-3ae5026645e1" patternsProximity="300" recommendedConfidence="85" filters="CompositeFiltersAtEntityLevel">
      <Pattern confidenceLevel="85" filters="CompositeFiltersAtPattern">
        <IdMatch idRef="Regex_denmark_id" />
      </Pattern>
</Entity>
``` 

 

## <a name="more-information"></a><span data-ttu-id="04296-197">更多信息</span><span class="sxs-lookup"><span data-stu-id="04296-197">More information</span></span>

- [<span data-ttu-id="04296-198">了解数据丢失防护</span><span class="sxs-lookup"><span data-stu-id="04296-198">Learn about data loss prevention</span></span>](dlp-learn-about-dlp.md)

- [<span data-ttu-id="04296-199">敏感信息类型属性定义</span><span class="sxs-lookup"><span data-stu-id="04296-199">Sensitive information type entity definitions</span></span>](sensitive-information-type-entity-definitions.md)

- [<span data-ttu-id="04296-200">DLP 函数查找什么</span><span class="sxs-lookup"><span data-stu-id="04296-200">What the DLP functions look for</span></span>](what-the-dlp-functions-look-for.md)
