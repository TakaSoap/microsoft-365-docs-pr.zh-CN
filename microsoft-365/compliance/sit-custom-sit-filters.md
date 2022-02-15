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
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 本文提供可以编码为自定义敏感信息类型的筛选器列表。
ms.openlocfilehash: e5f3fb99ec4454410c3719dc3d76356e02f03573
ms.sourcegitcommit: 19e16b16f144159b55bb4c544403e3642b69e335
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2022
ms.locfileid: "62818224"
---
# <a name="custom-sensitive-information-type-filters-reference"></a>自定义敏感信息类型筛选器参考

在 Microsoft 中，可以在使用 SIT 策略创建自定义敏感信息类型时定义 (或其他) 。

## <a name="list-of-supported-filters-and-use-cases"></a>支持的筛选器和用例列表

### <a name="alldigitssame-exclude"></a>AllDigitsSame 排除

说明：允许您排除所有数字都为重复数字的匹配项，如 111111111 或 111-111-111

定义筛选器
```xml
<Filters id="ssn_filters">
    <Filter type="AllDigitsSameFilter"></Filter>
</Filters>
```

在实体级别的规则包中使用它
```xml
<Entity id="50842eb7-edc8-4019-85dd-5a5c1f2bb085" patternsProximity="300" recommendedConfidence="85"  filters="ssn_filters">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_ssn" />
      </Pattern>
</Entity>
```

在模式级别的规则包中使用它
```xml
<Entity id="50842eb7-edc8-4019-85dd-5a5c1f2bb085" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85"  filters="ssn_filters">
        <IdMatch idRef="Func_ssn" />
      </Pattern>
</Entity>
```

### <a name="textmatchfilter-startswith"></a>TextMatchFilter StartsWith 

说明：允许您定义实体的起始字符。 它具有两种变体，即 include 和 exclude。

例如，在列表中排除以 0500、91、091、010 开始的数字，如下所示：

- 0500-4500-027
- 91564721450
- 91-8523697410
- 700-8956-7844
- 1000-3265-9874
- 0100-7892-3012

可以使用以下 xml

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
例如，在列表中包含以 0500、91、091、0100 开始的数字，如下所示： 

- 0500-4500-027
- 91564721450
- 91-8523697410
- 700-8956-7844
- 1000-3265-9874
- 0100-7892-3012

可以使用以下 xml

```xml
<Filters id="phone_filters_inc">
    <Filter type="TextMatchFilter" direction="StartsWith" logic="Include" textProcessorId="Keyword_false_positives_sw">
</Filter>
```

### <a name="textmatchfilter-endswith"></a>TextMatchFilter EndsWith 

说明：允许您定义实体的结束字符。 

例如，要排除列表中以 0500，91，091， 0100 结尾的数字，如下所示：

- 1234567891
- 1234-5678-0091
- 1234.4567.7091
- 1234-8091-4564

可以使用以下 xml

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

例如，在类似如下的列表中包含以 0500、91、091、0100 结尾的数字：

- 1234567891
- 1234-5678-0091
- 1234.4567.7091
- 1234-8091-4564

可以使用以下 xml

```xml
<Filters id="phone_filters_inc">
    <Filter type="TextMatchFilter" direction=" EndsWith" logic="Include" textProcessorId="Keyword_false_positives_sw">
</Filter>
```

### <a name="textmatchfilter-full"></a>TextMatchFilter Full

说明：允许您禁止某些匹配以防止它们触发规则。 例如，将4111111111111111信用卡匹配列表中排除。

例如，要排除信用卡号（如 4111111111111111）3241891031113111列表，如下所示：

- 4485 3647 3952 7352
- 4111111111111111
- 3241891031113111

可以使用以下 xml

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

例如，若要将信用卡号（如 4111111111111111 和 3241891031113111）包括在如下所示的列表中：

- 4485 3647 3952 7352
- 4111111111111111
- 3241891031113111

可以使用以下 xml

```xml
<Filters id="cc_filters_inc">
    <Filter type="TextMatchFilter" direction="Full" logic="Include" textProcessorId="Keyword_false_positives_full">
</Filter>
```

### <a name="textmatchfilter-prefix"></a>TextMatchFilter 前缀

说明：允许你定义应始终包含或排除的前面字符。 例如，如果信用卡号前面有"订单 ID："，则从有效匹配项中删除匹配项。

例如，要排除包含电话号码电话电话号码，并按电话号码前的字符串呼叫我，在如下所示的列表中：

- 电话号码 091-8974-653278
- 电话 45-124576532-123
- 45-124576532-123

可以使用以下 xml

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

例如，若要在信用卡号前包含信用卡和卡 **#** 字符串，在如下所示的列表中包含：

- 信用卡 45-124576532-123 
- 45-124576532-123 (可以是电话号码) 

可以使用以下 xml

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

### <a name="textmatchfilter-suffix"></a>TextMatchFilter 后缀

说明：允许你定义应始终包含或排除的以下字符。 例如，如果信用卡号后跟"/xuid"，则从有效匹配项中删除匹配项。

例如，如果列表中还有五个包含四个数字的实例作为后缀，则顶部排除，如下所示：

- 1234-5678-9321 4500 9870 6321 48925566
- 1234-5678-9321

可以使用以下 xml

```xml
<Filters id="cc_number_filters_exc">
    <Filter type="TextMatchFilter" direction="Prefix" logic="Exclude" textProcessorId="Regex_false_positives_suffix">
</Filter>

  <Regexid="Regex_false_positives_suffix">(\d{4}){5,}</Regex>
```
例如，若要排除后跟 **/xuidsuffix** 的事件，如此列表中的一个：

- 1234-5678-9321 /xuid
- 1234-5678-9321

可以使用此 xml

```xml
<Filters id="cc_number_filters_exc">
    <Filter type="TextMatchFilter" direction="Prefix" logic="Exclude" textProcessorId="Keyword_false_positives_suffix">
</Filter>

  <Keyword id="Keyword_false_positives_suffix">
    <Group matchStyle="string">
      <Term>/xuid</Term>
    </Group>
  </Keyword>
```

例如，仅在后跟 **cvv** 或过期时包含事件，如此列表中的两个：

- 45-124576532-123 
- 45-124576532-123 cvv 966
- 45-124576532-123 过期时间 03/23

可以使用此 xml

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

## <a name="using-filters-in-rule-packages"></a>使用规则包中的筛选器

可以在整个 SIT 或模式中定义筛选器。 下面是一些代码段示例。 

### <a name="at-sensitive-information-type-level"></a>在敏感信息类型级别

Entity 中的筛选器 - 将涵盖所有子模式

筛选器将应用于该实体/敏感类型中任何模式分类的所有实例

```xml
<Entity id="6443b88f-2808-482a-8e1a-3ae5026645e1" patternsProximity="300" recommendedConfidence="85" filters="CompositeFiltersAtEntityLevel">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Regex_denmark_id" />
      </Pattern>
</Entity>
```

### <a name="at-the-individual-pattern-of-the-sensitive-information-type-level"></a>在敏感信息类型级别的单个模式

仅在模式级别进行筛选。

筛选器将应用于与模式匹配的实例。

```xml
<Entity id="50842eb7-edc8-4019-85dd-5a5c1f2bb085" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85"  filters="CompositeFiltersAtPattern">
        <IdMatch idRef="Keyword_cc_verification" />
      </Pattern>
</Entity>
```


### <a name="at-sensitive-information-type-level-and-an-additional-filter-on-some-of-the-patterns-of-that-entity"></a>在敏感信息类型级别，以及该实体的一些模式的其他筛选器

实体 + 模式的筛选器

筛选器将 **应用于该实体** /敏感类型中任何模式分类的所有实例。 模式级别筛选器将筛选该模式匹配的实例。

```xml
<Entity id="6443b88f-2808-482a-8e1a-3ae5026645e1" patternsProximity="300" recommendedConfidence="85" filters="CompositeFiltersAtEntityLevel">
      <Pattern confidenceLevel="85" filters="CompositeFiltersAtPattern">
        <IdMatch idRef="Regex_denmark_id" />
      </Pattern>
</Entity>
``` 

 

## <a name="more-information"></a>更多信息

- [了解数据丢失防护](dlp-learn-about-dlp.md)

- [敏感信息类型属性定义](sensitive-information-type-entity-definitions.md)

- [DLP 函数查找什么](what-the-dlp-functions-look-for.md)
