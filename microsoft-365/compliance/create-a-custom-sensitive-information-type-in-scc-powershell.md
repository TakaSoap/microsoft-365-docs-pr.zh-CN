---
title: 使用 PowerShell 创建自定义敏感信息类型
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 了解如何在合规中心中创建并导入策略的自定义敏感信息类型。
ms.openlocfilehash: 89c215ca52b255a6e3aed72ff032cdd2475c0d87
ms.sourcegitcommit: bb493f12701f6d6ee7d5e64b541adb87470bc7bc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/18/2022
ms.locfileid: "62903857"
---
# <a name="create-a-custom-sensitive-information-type-using-powershell"></a>使用 PowerShell 创建自定义敏感信息类型

本文演示如何创建定义自定义敏感信息 *类型的 XML 规则*[包文件](sensitive-information-type-entity-definitions.md)。 本文介绍标识员工 ID 的自定义敏感信息类型。 您可以使用本文中的示例 XML 作为您自己的 XML 文件的起点。

有关敏感信息类型详细信息，请参阅 [了解敏感信息类型](sensitive-information-type-learn-about.md)。

创建格式良好的 XML 文件后，可以使用 PowerShell 将其Microsoft 365文件。 然后，即可在策略中使用您的自定义敏感信息类型。 您可以测试其检测敏感信息的有效性（如预期）。

> [!NOTE]
> 如果不需要 PowerShell 提供的精细控件，可以在自定义控件中创建自定义Microsoft 365 合规中心。 有关详细信息，请参阅[创建自定义敏感信息类型](create-a-custom-sensitive-information-type.md)。

## <a name="important-disclaimer"></a>重要免责声明

Microsoft 支持无法帮助您创建内容匹配定义。

对于自定义内容匹配开发、测试和调试，您需要使用自己的内部 IT 资源或使用咨询服务，如 Microsoft 咨询服务 (MCS) 。 Microsoft 支持工程师可提供对此功能的有限支持，但他们无法保证自定义内容匹配建议将完全满足您的需求。

MCS 可以提供用于测试的正则表达式。 他们还可以协助排查使用单个特定内容示例未如预期工作的现有 RegEx 模式。

请参阅 [本文中要注意的潜在](#potential-validation-issues-to-be-aware-of) 验证问题。

有关用于处理文本的 Boost.RegEx（以前称为 RegEx++）引擎的详细信息，请参阅 [Boost.Regex 5.1.3](https://www.boost.org/doc/libs/1_68_0/libs/regex/doc/html/)。

> [!NOTE]
> 如果使用与号字符 (&) 作为自定义敏感信息类型中关键字的一部分，则需要添加一个附加字词，该字符周围有空格。 例如 _，不使用_ `L&P``L & P` 。

## <a name="sample-xml-of-a-rule-package"></a>规则包 XML 示例

下面是我们将在本文创建的规则包的示例 XML。 以下各节介绍了元素和属性。

```xml
<?xml version="1.0" encoding="UTF-16"?>
<RulePackage xmlns="http://schemas.microsoft.com/office/2011/mce">
<RulePack id="DAD86A92-AB18-43BB-AB35-96F7C594ADAA">
  <Version build="0" major="1" minor="0" revision="0"/>
  <Publisher id="619DD8C3-7B80-4998-A312-4DF0402BAC04"/>
  <Details defaultLangCode="en-us">
    <LocalizedDetails langcode="en-us">
      <PublisherName>Contoso</PublisherName>
      <Name>Employee ID Custom Rule Pack</Name>
      <Description>
      This rule package contains the custom Employee ID entity.
      </Description>
    </LocalizedDetails>
  </Details>
</RulePack>
<Rules>
<!-- Employee ID -->
  <Entity id="E1CC861E-3FE9-4A58-82DF-4BD259EAB378" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="65">
      <IdMatch idRef="Regex_employee_id"/>
    </Pattern>
    <Pattern confidenceLevel="75">
      <IdMatch idRef="Regex_employee_id"/>
      <Match idRef="Func_us_date"/>
    </Pattern>
    <Pattern confidenceLevel="85">
      <IdMatch idRef="Regex_employee_id"/>
      <Match idRef="Func_us_date"/>
      <Any minMatches="1">
        <Match idRef="Keyword_badge" minCount="2"/>
        <Match idRef="Keyword_employee"/>
      </Any>
      <Any minMatches="0" maxMatches="0">
        <Match idRef="Keyword_false_positives_local"/>
        <Match idRef="Keyword_false_positives_intl"/>
      </Any>
    </Pattern>
  </Entity>
  <Regex id="Regex_employee_id">(\s)(\d{9})(\s)</Regex>
  <Keyword id="Keyword_employee">
    <Group matchStyle="word">
      <Term>Identification</Term>
      <Term>Contoso Employee</Term>
    </Group>
  </Keyword>
  <Keyword id="Keyword_badge">
    <Group matchStyle="string">
      <Term>card</Term>
      <Term>badge</Term>
      <Term caseSensitive="true">ID</Term>
    </Group>
  </Keyword>
  <Keyword id="Keyword_false_positives_local">
    <Group matchStyle="word">
      <Term>credit card</Term>
      <Term>national ID</Term>
    </Group>
  </Keyword>
  <Keyword id="Keyword_false_positives_intl">
    <Group matchStyle="word">
      <Term>identity card</Term>
      <Term>national ID</Term>
      <Term>EU debit card</Term>
    </Group>
  </Keyword>
  <LocalizedStrings>
    <Resource idRef="E1CC861E-3FE9-4A58-82DF-4BD259EAB378">
      <Name default="true" langcode="en-us">Employee ID</Name>
      <Description default="true" langcode="en-us">
      A custom classification for detecting Employee IDs.
      </Description>
      <Description default="false" langcode="de-de">
      Description for German locale.
      </Description>
    </Resource>
  </LocalizedStrings>
</Rules>
</RulePackage>
```

## <a name="what-are-your-key-requirements-rule-entity-pattern-elements"></a>关键要求是什么？[Rule、Entity、Pattern 元素]

了解规则 XML 架构的基本结构非常重要。 您了解结构将有助于您的自定义敏感信息类型识别正确的内容。

规则定义一个或多个实体 (也称为敏感信息类型) 。 每个实体定义一个或多个模式。 模式是策略在评估内容类型（例如，电子邮件 (文档）时) 。

在 XML 标记中，"规则"表示定义敏感信息类型的模式。 请勿将本文中对规则的引用与其他 Microsoft 功能中常见的"条件"或"操作"关联。

### <a name="simplest-scenario-entity-with-one-pattern"></a>最简单方案：包含一个模式的实体

下面是一个简单的方案：您希望策略标识包含组织中使用的九位数员工标识的内容。 模式是指标识九位数的规则中的正则表达式。 包含九位数的任何内容都满足模式。

![具有一种模式的实体关系图。](../media/4cc82dcf-068f-43ff-99b2-bac3892e9819.png)

但是，此 **模式可能标识** 任何九位数，包括较长号码或其他类型的非员工标识的九位数。 此类不需要的匹配称为 *误报*。

### <a name="more-common-scenario-entity-with-multiple-patterns"></a>更常见方案：包含多个模式的实体

由于误报的可能性，通常使用多个模式来定义实体。 多个模式为目标实体提供支持性证据。 例如，其他关键字、日期或其他文本可帮助标识原始实体 (例如，使用九位数的员工) 。

例如，若要提高识别包含员工 ID 的内容的可能性，可以定义要查找的其他模式：

- 标识雇用日期的模式。
- 标识雇用日期和"员工 ID"关键字的模式。

![具有多个模式的实体关系图。](../media/c8dc2c9d-00c6-4ebc-889a-53b41a90024a.png)

对于多个模式匹配，需要考虑一些要点：

- 需要更多证据的模式具有更高的可信度级别。 根据可信度，可以执行以下操作：
  - 使用更严格的操作 (，例如) 高可信度匹配的内容。
  - 使用限制性较低的 (，例如) 较低的匹配发送通知。

- 支持和元素`IdMatch``Match`引用 RegExes 和关键字，它们实际上是 `Rule` 元素的子元素，而不是 `Pattern`。 这些支持元素由 引用， `Pattern`但包含在 中 `Rule`。 此行为意味着支持元素（如正则表达式或关键字列表）的单个定义可以通过多个实体和模式引用。

## <a name="what-entity-do-you-need-to-identify-entity-element-id-attribute"></a>需要标识哪些实体？ [Entity 元素，ID 属性]

实体是包含明确定义的模式的敏感信息类型，如信用卡号。每个实体都有一个唯一 GUID 作为自己的 ID。

### <a name="name-the-entity-and-generate-its-guid"></a>命名实体并生成 GUID

1. 在选择的 XML 编辑器中，添加 和 `Rules` `Entity` 元素。
2. 添加包含自定义实体名称的注释，如"员工 ID"。 稍后，将实体名称添加到本地化字符串部分，该名称在您创建策略时将显示在管理中心。
3. 为实体生成唯一的 GUID。 例如，在Windows PowerShell中，可以运行命令 `[guid]::NewGuid()`。 稍后，您还将 GUID 添加到实体的本地化字符串部分。

![显示 Rules 和 Entity 元素的 XML 标记。](../media/c46c0209-0947-44e0-ac3a-8fd5209a81aa.png)

## <a name="what-pattern-do-you-want-to-match-pattern-element-idmatch-element-regex-element"></a>要匹配什么模式？[Pattern 元素、IdMatch 元素、Regex 元素]

模式包含敏感信息类型所查找内容的列表。 该模式可以包括 RegExes、关键字和内置函数。 函数执行类似运行 RegExes 以查找日期或地址的任务。 敏感信息类型可能具有多个模式，每个模式均具有唯一的可信度。

在下图中，所有模式引用相同的正则表达式。 此 RegEx 查找用空格包围的九 `(\d{9})` 位数 `(\s) ... (\s)`。 此正则表达式由 元素 `IdMatch` 引用，是查找 Employee ID 实体的所有模式的共同要求。 `IdMatch` 是模式尝试匹配的标识符。 元素 `Pattern` 必须只有一个元素 `IdMatch` 。

![显示引用单个 Regex 元素的多个 Pattern 元素的 XML 标记。](../media/8f3f497b-3b8b-4bad-9c6a-d9abf0520854.png)

满足的模式匹配将返回计数和可信度，可以在策略中的条件中使用它。 向策略添加用于检测敏感信息类型的条件时，可以编辑计数和可信度，如下图所示。 可信度 (也称为匹配准确度) 本文稍后将介绍。

![实例计数和匹配准确度选项。](../media/sit-confidence-level.png)

正则表达式功能强大，因此您需要了解一些问题。 例如，标识过多内容的 RegEx 会影响性能。 若要详细了解这些问题，请参阅本文稍后介绍的潜在[](#potential-validation-issues-to-be-aware-of)验证问题部分。

## <a name="do-you-want-to-require-additional-evidence-match-element-mincount-attribute"></a>是否需要其他证据？[Match 元素、minCount 特性]

除了 ， `IdMatch`模式可以使用 `Match` 元素来要求其他支持性证据，如关键字、RegEx、日期或地址。

可能 `Pattern` 包含多个 `Match` 元素：

- 直接在 `Pattern` 元素中。
- 使用 元素组合 `Any` 。

`Match` 元素由隐式 AND 运算符联接。 换句话说，若要匹配 `Match` 模式，必须满足所有元素。

可以使用 元素引入 `Any` AND 或 OR 运算符。 元素 `Any` 在本文的稍后部分进行介绍。

可以使用可选属性 `minCount` 指定需要为每个元素找到的匹配项实例 `Match` 数。 例如，您可以指定仅在至少找到关键字列表中的两个关键字时满足模式。

![显示具有 minOccurs 属性的 Match 元素的 XML 标记。](../media/607f6b5e-2c7d-43a5-a131-a649f122e15a.png)

### <a name="keywords-keyword-group-and-term-elements-matchstyle-and-casesensitive-attributes"></a>关键字 [Keyword、Group 和 Term 元素，matchStyle 和 caseSensitive 特性]

如前面所述，识别敏感信息通常需要其他关键字作为确证性证据。 例如，除了匹配九位数外，您还可以使用 Keyword 元素查找"card"、"badge"或"ID"等单词。 元素 `Keyword` 具有一 `ID` 个属性，可通过多个模式 `Match` 或实体中的多个元素引用该属性。

关键字作为元素中的 `Term` 元素列表 `Group` 包含在内。 元素 `Group` 具有具有两 `matchStyle` 个可能值的属性：

- **matchStyle="word"**：字词匹配标识空格或其他分隔符包围的整个单词。 除非需要匹配 **部分单词** 或亚洲语言的单词，否则应始终使用单词。

- **matchStyle="string"**：无论字符串被什么包围，字符串匹配都标识字符串。 例如，"ID"将匹配"bid"和"idea"。 仅在 `string` 需要匹配亚洲语言字词或关键字可能包含在其他字符串中时使用。

最后，可以使用 元素 `caseSensitive` 的 属性 `Term` 指定内容必须与关键字完全匹配，包括小写字母和大写字母。

![显示引用关键字的 Match 元素的 XML 标记。](../media/e729ba27-dec6-46f4-9242-584c6c12fd85.png)

### <a name="regular-expressions-regex-element"></a>正则表达式 [Regex 元素]

本示例中，employee `ID` 实体已 `IdMatch` 使用 元素引用模式的正则表达式：一个用空格包围的九位数。 此外，模式`Match``Regex`可以使用 元素引用其他元素来标识确证性证据，如采用美国邮政编码格式的五位数或九位数。

### <a name="additional-patterns-such-as-dates-or-addresses-built-in-functions"></a>日期或地址等其他模式 [内置函数]

敏感信息类型还可使用内置函数来识别确定证据。 例如，美国日期、欧盟日期、到期日期或美国地址。 Microsoft 365不支持上载自己的自定义函数。 但是，当您创建自定义敏感信息类型时，实体可以引用内置函数。

例如，员工 ID `Func_us_date` 徽章具有雇用日期，因此此自定义实体可以使用内置函数来标识美国常用的格式的日期。

有关详细信息，请参阅 [敏感信息类型函数](sit-functions.md)。

![显示引用内置函数的 Match 元素的 XML 标记。](../media/dac6eae3-9c52-4537-b984-f9f127cc9c33.png)

## <a name="different-combinations-of-evidence-any-element-minmatches-and-maxmatches-attributes"></a>不同证据组合 [Any 元素、minMatches 和 maxMatches 特性]

在 元素 `Pattern` 中，所有 `IdMatch` 和 `Match` 元素都由隐式 AND 运算符联接。 换句话说，必须先满足所有匹配项，然后才能满足模式。

通过使用 元素对元素进行分组，可以创建更灵活 `Any` 的匹配 `Match` 逻辑。 例如，可以使用 元素 `Any` 来匹配其子元素的所有、无或确切的子集 `Match` 。

元素 `Any` 具有可选的 `minMatches` 和 `maxMatches` 属性 `Match` ，可用于定义在匹配模式之前必须满足多少子元素。 这些属性定义 *元素数*`Match`，而不是为匹配找到的证据实例数。 若要为特定匹配`minCount``Match`定义最少数量的实例（如列表中的两个关键字），请使用元素的 (属性，) 。

### <a name="match-at-least-one-child-match-element"></a>至少匹配一个 Match 子元素

若要只需要最少数量的元素 `Match` ，可以使用 `minMatches` 属性。 实际上，这些 `Match` 元素由隐式 OR 运算符联接。 如果 `Any` 找到美国格式的日期或任一列表中的关键字，则满足此元素。

```xml
<Any minMatches="1" >
     <Match idRef="Func_us_date" />
     <Match idRef="Keyword_employee" />
     <Match idRef="Keyword_badge" />
</Any>
```

### <a name="match-an-exact-subset-of-any-children-match-elements"></a>匹配确切的一部分 Match 子元素

若要要求确切的元素数 `Match` ，请设置 和 `minMatches` `maxMatches` 为相同值。 只有在 `Any` 找到一个日期或关键字时，才满足此元素。 如果还有匹配项，则模式不匹配。

```xml
<Any minMatches="1" maxMatches="1" >
     <Match idRef="Func_us_date" />
     <Match idRef="Keyword_employee" />
     <Match idRef="Keyword_badge" />
</Any>
```

### <a name="match-none-of-children-match-elements"></a>与任何 Match 子元素都不匹配

若要规定只要缺少某证据才算符合模式，可以将 minMatches 和 maxMatches 同时设置为 0。如果关键字列表或其他证据可能发出误报，这样做就很有用。

例如，“员工 ID”实体查找关键字“卡”，因为这可能会指代“ID 卡”。不过，如果“卡”仅出现在短语“信用卡”中，此内容中的“卡”就不太可能表示“ID 卡”。因此，可以将“信用卡”作为关键字，添加到匹配模式时要排除的术语列表。

```xml
<Any minMatches="0" maxMatches="0" >
    <Match idRef="Keyword_false_positives_local" />
    <Match idRef="Keyword_false_positives_intl" />
</Any>
```

### <a name="match-a-number-of-unique-terms"></a>匹配多个唯一术语

如果要匹配多个唯一术语，请使用 *uniqueResults* 参数，将其设置为 *true*，如下例所示：

```xml
<Pattern confidenceLevel="75">
    <IdMatch idRef="Salary_Revision_terms" />
    <Match idRef=" Salary_Revision_ID " minCount="3" uniqueResults="true" />
</Pattern>
```

在此示例中，使用至少三个唯一匹配为薪资修订定义模式。

## <a name="how-close-to-the-entity-must-the-other-evidence-be-patternsproximity-attribute"></a>另一证据必须与实体有多接近？[patternsProximity 特性]

敏感信息类型要查找表示员工 ID 的模式，此模式还查找确证性证据，如“ID”等关键字。很明显，此证据越接近，模式就越有可能是实际员工 ID。可使用 Entity 元素的必需特性 patternsProximity，确定模式中的另一证据必须与实体有多接近。

![显示 patternsProximity 属性的 XML 标记。](../media/e97eb7dc-b897-4e11-9325-91c742d9839b.png)

对于实体中的每种模式，patternsProximity 特性值都定义针对相应模式指定的其他所有 Match 与 IdMatch 位置的距离（以 Unicode 字符数为单位）。接近度窗口以 IdMatch 位置为关键主体，向 IdMatch 左右延伸。

![邻近感应窗口的图示。](../media/b593dfd1-5eef-4d79-8726-a28923f7c31e.png)

下面的示例展示了接近度窗口如何影响模式匹配，其中“员工 ID”自定义实体的 IdMatch 元素要求至少必须有一个关键字或日期确证性匹配。仅 ID1 匹配，因为对于 ID2 和 ID3，在接近度窗口中找不到任何确证性证据或只找到部分确证性证据。

![确定证据和邻近感应窗口的关系图。](../media/dc68e38e-dfa1-45b8-b204-89c8ba121f96.png)

请注意，对于电子邮件，邮件正文和每个附件被视为单独的项目。 这意味着邻近感应窗口不会扩展到上述每个项的末尾之外。 对于附件 (正文) ，idMatch 和确定证据都需要驻留在该项中。

## <a name="what-are-the-right-confidence-levels-for-different-patterns-confidencelevel-attribute-recommendedconfidence-attribute"></a>什么是各个模式的合适可信度？[confidenceLevel 特性、recommendedConfidence 特性]

模式需要的证据越多，模式匹配时所标识的实际实体（如员工 ID）的可信度就越高。例如，与只要求匹配九位数 ID 的模式相比，要求匹配九位数 ID、聘用日期和关键字（极为接近）的模式的可信度更高。

Pattern 元素有必需的 confidenceLevel 属性。可将 confidenceLevel 值（介于 1 和 100 之间的整数）视为实体中每个模式的唯一 ID - 实体中的模式必须具有你分配的不同的可信度。整数值是否精确并不重要 - 只需选取对合规性团队有意义的数字即可。上传自定义敏感信息类型和创建策略后，可以在所创建规则的条件中引用这些可信度。

![显示具有不同 confidenceLevel 属性值的 Pattern 元素的 XML 标记。](../media/sit-xml-markedup-2.png)

除每个模式的 confidenceLevel 外，Entity 还有一个 recommendedConfidence 属性。 可将推荐的可信度属性视为规则的默认可信度级别。 在策略中创建规则时，如果不指定规则要使用的可信度级别，则该规则将基于推荐的实体可信度级别进行匹配。 请注意，规则包中的每个实体 ID 都必须使用 recommendedConfidence 属性，如果该属性缺失，将无法保存使用敏感信息类型的策略。

## <a name="do-you-want-to-support-other-languages-in-the-ui-of-the-compliance-center-localizedstrings-element"></a>是否要在合规中心的 UI 中支持其他语言？[LocalizedStrings 元素]

如果合规性团队使用 Microsoft 365 合规性中心创建不同区域设置和不同语言的策略，你可以提供自定义敏感信息类型的名称和说明的本地化版本。 若符合性团队使用支持语言的 Microsoft 365，则 UI 中会出现本地化的名称。

![实例计数和匹配准确度配置。](../media/11d0b51e-7c3f-4cc6-96d8-b29bcdae1aeb.png)

Rule 元素必须包含 LocalizedStrings 元素，因为其中包含引用自定义实体 GUID 的 Resource 元素。相应地，每个 Resource 元素都包含一个或多个 Name 和 Description 元素，这些元素使用 langcode 特性来提供特定语言的本地化字符串。

![显示 LocalizedStrings 元素内容的 XML 标记。](../media/a96fc34a-b93d-498f-8b92-285b16a7bbe6.png)

请注意，本地化字符串只能用于指定自定义敏感信息类型在合规中心 UI 中的显示方式。不能使用本地化字符串来提供不同本地化版本的关键字列表或正则表达式。

## <a name="other-rule-package-markup-rulepack-guid"></a>其他规则包标记 [RulePack GUID]

最后，每个 RulePackage 的开头都有一些需要填写的常规信息。可以下面的标记为模板，将“...”占位符替换为你自己的信息。

最重要的是，必须为 RulePack 生成 GUID。在上文中，已为实体生成了 GUID；这是 RulePack 的第二个 GUID。虽然生成 GUID 的方法有很多，但可通过在 PowerShell 中键入 [guid]::NewGuid() 轻松完成。

Version 元素也很重要。当你首次上传规则包时，Microsoft 365 会记录版本号。稍后，如果更新规则包并上传新版本，请务必更新版本号，否则 Microsoft 365 便不会部署规则包。

```xml
<?xml version="1.0" encoding="utf-16"?>
<RulePackage xmlns="http://schemas.microsoft.com/office/2011/mce">
  <RulePack id=". . .">
    <Version major="1" minor="0" build="0" revision="0" />
    <Publisher id=". . ." />
    <Details defaultLangCode=". . .">
      <LocalizedDetails langcode=" . . . ">
         <PublisherName>. . .</PublisherName>
         <Name>. . .</Name>
         <Description>. . .</Description>
      </LocalizedDetails>
    </Details>
  </RulePack>

 <Rules>
  . . .
 </Rules>
</RulePackage>
```

完成后，RulePack 元素应如下所示。

![显示 RulePack 元素的 XML 标记。](../media/fd0f31a7-c3ee-43cd-a71b-6a3813b21155.png)

## <a name="validators"></a>验证程序

Microsoft 365公开常用 SIT 的函数处理器作为验证程序。 以下是它们的列表。

### <a name="list-of-currently-available-validators"></a>当前可用的验证程序列表

- `Func_credit_card`
- `Func_ssn`
- `Func_unformatted_ssn`
- `Func_randomized_formatted_ssn`
- `Func_randomized_unformatted_ssn`
- `Func_aba_routing`
- `Func_south_africa_identification_number`
- `Func_brazil_cpf`
- `Func_iban`
- `Func_brazil_cnpj`
- `Func_swedish_national_identifier`
- `Func_india_aadhaar`
- `Func_uk_nhs_number`
- `Func_Turkish_National_Id`
- `Func_australian_tax_file_number`
- `Func_usa_uk_passport`
- `Func_canadian_sin`
- `Func_formatted_itin`
- `Func_unformatted_itin`
- `Func_dea_number_v2`
- `Func_dea_number`
- `Func_japanese_my_number_personal`
- `Func_japanese_my_number_corporate`

这让你能够定义自己的 RegEx 并验证它们。 若要使用验证程序，请定义你自己的 RegEx，并使用 `Validator` 属性添加你选择的函数处理器。 定义后，可以在 SIT 中使用此 RegEx。

在下面的示例中，正则表达式 - Regex_credit_card_AdditionalDelimiters定义为信用卡，然后使用信用卡的校验和函数将 Func_credit_card 用作验证程序进行验证。

```xml
<Regex id="Regex_credit_card_AdditionalDelimiters" validators="Func_credit_card"> (?:^|[\s,;\:\(\)\[\]"'])([0-9]{4}[ -_][0-9]{4}[ -_][0-9]{4}[ -_][0-9]{4})(?:$|[\s,;\:\(\)\[\]"'])</Regex>
<Entity id="675634eb7-edc8-4019-85dd-5a5c1f2bb085" patternsProximity="300" recommendedConfidence="85">
<Pattern confidenceLevel="85">
<IdMatch idRef="Regex_credit_card_AdditionalDelimiters" />
<Any minMatches="1">
<Match idRef="Keyword_cc_verification" />
<Match idRef="Keyword_cc_name" />
<Match idRef="Func_expiration_date" />
</Any>
</Pattern>
</Entity>
```

Microsoft 365两个泛型验证程序

### <a name="checksum-validator"></a>校验和验证程序

本示例定义员工 ID 的校验和验证程序，以验证 EmployeeID 的 RegEx。

```xml
<Validators id="EmployeeIDChecksumValidator">
<Validator type="Checksum">
<Param name="Weights">2, 2, 2, 2, 2, 1</Param>
<Param name="Mod">28</Param>
<Param name="CheckDigit">2</Param> <!-- Check 2nd digit -->
<Param name="AllowAlphabets">1</Param> <!— 0 if no Alphabets -->
</Validator>
</Validators>
<Regex id="Regex_EmployeeID" validators="ChecksumValidator">(\d{5}[A-Z])</Regex>
<Entity id="675634eb7-edc8-4019-85dd-5a5c1f2bb085" patternsProximity="300" recommendedConfidence="85">
<Pattern confidenceLevel="85">
<IdMatch idRef="Regex_EmployeeID"/>
</Pattern>
</Entity>
```

### <a name="date-validator"></a>日期验证程序

本示例中，为为日期的 RegEx 部分定义日期验证程序。

```xml
<Validators id="date_validator_1"> <Validator type="DateSimple"> <Param name="Pattern">DDMMYYYY</Param> <!—supported patterns DDMMYYYY, MMDDYYYY, YYYYDDMM, YYYYMMDD, DDMMYYYY, DDMMYY, MMDDYY, YYDDMM, YYMMDD --> </Validator> </Validators>
<Regex id="date_regex_1" validators="date_validator_1">\d{8}</Regex>
```

## <a name="changes-for-exchange-online"></a>针对 Exchange Online 的变化

以前，你可能已使用过 Exchange Online PowerShell 为 DLP 导入自定义敏感信息类型。 现在，自定义敏感信息类型可用于管理Exchange<a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">和</a>合规中心。 此次改进后，应使用合规中心 PowerShell 导入自定义敏感信息类型，不再可从 Exchange PowerShell 导入它们。 自定义敏感信息类型将像往常一样正常工作，但是，在合规中心进行的更改可能需要至多一小时才会出现在 Exchange 管理中心。

请注意，在合规中心中，可以使用 **[New-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/new-dlpsensitiveinformationtyperulepackage)** cmdlet 上载规则包。 （以前，在 Exchange 管理中心中，使用的是 **ClassificationRuleCollection**`cmdlet。）

## <a name="upload-your-rule-package"></a>上传规则包

若要上传规则包，请按照以下步骤操作：

1. 将文件另存为采用 Unicode 编码的 .xml 文件。

2. [连接到合规中心 PowerShell](/powershell/exchange/exchange-online-powershell)

3. 使用以下语法：

   ```powershell
   New-DlpSensitiveInformationTypeRulePackage -FileData ([System.IO.File]::ReadAllBytes('PathToUnicodeXMLFile'))
   ```

   本示例从 C:\My Documents 上传名为 MyNewRulePack.xml 的 Unicode XML 文件。

   ```powershell
   New-DlpSensitiveInformationTypeRulePackage -FileData ([System.IO.File]::ReadAllBytes('C:\My Documents\MyNewRulePack.xml'))
   ```

   有关语法和参数的详细信息，请参阅 [New-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/new-dlpsensitiveinformationtyperulepackage)。

   > [!NOTE]
   > 支持的规则包数量最多为10个，但每个包可以包含多个敏感信息类型的定义。

4. 若要验证是否已成功新建敏感信息类型，请按以下任一步骤操作：

   - 运行 [Get-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/get-dlpsensitiveinformationtyperulepackage) cmdlet，验证新规则包是否已列出：

     ```powershell
     Get-DlpSensitiveInformationTypeRulePackage
     ```

   - Run the [Get-DlpSensitiveInformationType](/powershell/module/exchange/get-dlpsensitiveinformationtype)，验证敏感信息类型是否已列出：

     ```powershell
     Get-DlpSensitiveInformationType
     ```

     对于自定义敏感信息类型，Publisher 属性值将不是 Microsoft Corporation。

   - 将 \<Name\> 替换为敏感信息类型的 Name 值（例如，员工 ID），然后运行 [Get-DlpSensitiveInformationType](/powershell/module/exchange/get-dlpsensitiveinformationtype) cmdlet：

     ```powershell
     Get-DlpSensitiveInformationType -Identity "<Name>"
     ```

## <a name="potential-validation-issues-to-be-aware-of"></a>要注意的潜在验证问题

当你上传规则包 XML 文件时，系统会验证 XML，并检查是否有已知的错误模式和明显的性能问题。验证检查正则表达式时，需要检查其中是否有下面的一些已知问题：

- 正则表达式中的查找断言应仅具有固定长度。 可变长度断言将导致错误。

  例如， `"(?<=^|\s|_)"` 无法通过验证。 第一个 `^` () 为零长度 `\s` ，而后两种模式 () `_` 一个长度。 编写此正则表达式的替代方法是 `"(?:^|(?<=\s|_))"`。

- 不得以交替符开头或结尾， `|`它匹配所有内容，因为它被视为空匹配。

  例如， `|a` 或 `b|` 无法通过验证。

- 不能以模式开头或 `.{0,m}` 结尾，该模式没有功能用途，只会损害性能。

  例如， `.{0,50}ASDF` 或 `ASDF.{0,50}` 无法通过验证。

- 不能具有 `.{0,m}` 或 `.{1,m}` 组，也不能具有 或 `.\*` `.+` 组。

  例如， `(.{0,50000})` 无法通过验证。

- 组中不能有任何字符或`{0,m}``{1,m}`重复符。

  例如， `(a\*)` 无法通过验证。

- 不能以 开头或结尾 `.{1,m}`;请改为使用 `.`。

  例如， `.{1,m}asdf` 无法通过验证。 请改为使用 `.asdf`。

- 组中不能有无限 (重复 `*` `+`) 或无限制。

  例如， `(xx)\*` 和 `(xx)+` 无法通过验证。

- 关键字最多可包含 50 个字符。  如果组中的关键字超过此字符数，建议将术语组创建为[关键字字典](./create-a-keyword-dictionary.md)，并在 XML 结构中引用关键字字典的 GUID 作为文件中的 Match 或 idMatch 实体的一部分。

- 每个自定义敏感信息类型最多可以包含 2048 个关键字。

- 为了符合 AD 架构限制，单个租户中关键字词典的最大大小为 480 KB。 创建自定义敏感信息类型时，请尽情地根据需要多次引用同一词典。 请先在敏感信息类型中创建自定义关键字列表，然后如果关键字列表中有超过 2048 个关键字或某个关键字长度超过 50 个字符时，请使用关键字词典。

- 租户中最多允许 50 种基于关键字字典的敏感信息类型。

- 确保每个 Entity 元素都包含一个 recommendedConfidence 属性。

- 使用 PowerShell Cmdlet 时，反反初始化数据的最大返回大小约为 1 MB。   这会影响规则包 XML 文件的大小。 将所上传文件的建议上限设置为 770 KB，以确保结果一致，处理时不会出错。

- XML 结构不需要格式字符，如空格、制表符或回车/换行条目。  在针对上传空间进行优化时，请注意这一点。 诸如 Microsoft Visual Code 等工具提供连接线功能来压缩 XML 文件。

如果自定义敏感信息类型存在可能会影响性能的问题，便无法上传，且可能会导致以下错误消息之一出现：

- `Generic quantifiers which match more content than expected (e.g., '+', '*')`

- `Lookaround assertions`

- `Complex grouping in conjunction with general quantifiers`

## <a name="recrawl-your-content-to-identify-the-sensitive-information"></a>对内容重新爬网以标识敏感信息

Microsoft 365 使用搜索爬网程序对网站内容中的敏感信息进行标识和分类。SharePoint Online 和 OneDrive for Business 网站中的内容会在更新后自动重新爬网。但若要标识所有现有内容中新的自定义类型敏感信息，必须对相应内容重新爬网。

在Microsoft 365中，无法手动请求对整个组织进行重新进行，但可以手动请求对网站集、列表或库进行重新CRAWL。 有关详细信息，请参阅手动请求对网站、库或列表进行爬网和 [重新索引](/sharepoint/crawl-site-content)。

## <a name="reference-rule-package-xml-schema-definition"></a>参考：规则包 XML 架构定义

可复制此标记，并将它另存为 XSD 文件，以用来验证规则包 XML 文件。

```xml
<?xml version="1.0" encoding="utf-8"?>
<xs:schema xmlns:mce="http://schemas.microsoft.com/office/2011/mce"
           targetNamespace="http://schemas.microsoft.com/office/2011/mce"
           xmlns:xs="https://www.w3.org/2001/XMLSchema"
           elementFormDefault="qualified"
           attributeFormDefault="unqualified"
           id="RulePackageSchema">
  <!-- Use include if this schema has the same target namespace as the schema being referenced, otherwise use import -->
  <xs:element name="RulePackage" type="mce:RulePackageType"/>
  <xs:simpleType name="LangType">
    <xs:union memberTypes="xs:language">
      <xs:simpleType>
        <xs:restriction base="xs:string">
          <xs:enumeration value=""/>
        </xs:restriction>
      </xs:simpleType>
    </xs:union>
  </xs:simpleType>
  <xs:simpleType name="GuidType" final="#all">
    <xs:restriction base="xs:token">
      <xs:pattern value="[0-9a-fA-F]{8}\-([0-9a-fA-F]{4}\-){3}[0-9a-fA-F]{12}"/>
    </xs:restriction>
  </xs:simpleType>
  <xs:complexType name="RulePackageType">
    <xs:sequence>
      <xs:element name="RulePack" type="mce:RulePackType"/>
      <xs:element name="Rules" type="mce:RulesType">
        <xs:key name="UniqueRuleId">
          <xs:selector xpath="mce:Entity|mce:Affinity|mce:Version/mce:Entity|mce:Version/mce:Affinity"/>
          <xs:field xpath="@id"/>
        </xs:key>
        <xs:key name="UniqueProcessorId">
          <xs:selector xpath="mce:Regex|mce:Keyword|mce:Fingerprint"></xs:selector>
          <xs:field xpath="@id"/>
        </xs:key>
        <xs:key name="UniqueResourceIdRef">
          <xs:selector xpath="mce:LocalizedStrings/mce:Resource"/>
          <xs:field xpath="@idRef"/>
        </xs:key>
        <xs:keyref name="ReferencedRuleMustExist" refer="mce:UniqueRuleId">
          <xs:selector xpath="mce:LocalizedStrings/mce:Resource"/>
          <xs:field xpath="@idRef"/>
        </xs:keyref>
        <xs:keyref name="RuleMustHaveResource" refer="mce:UniqueResourceIdRef">
          <xs:selector xpath="mce:Entity|mce:Affinity|mce:Version/mce:Entity|mce:Version/mce:Affinity"/>
          <xs:field xpath="@id"/>
        </xs:keyref>
      </xs:element>
    </xs:sequence>
  </xs:complexType>
  <xs:complexType name="RulePackType">
    <xs:sequence>
      <xs:element name="Version" type="mce:VersionType"/>
      <xs:element name="Publisher" type="mce:PublisherType"/>
      <xs:element name="Details" type="mce:DetailsType">
        <xs:key name="UniqueLangCodeInLocalizedDetails">
          <xs:selector xpath="mce:LocalizedDetails"/>
          <xs:field xpath="@langcode"/>
        </xs:key>
        <xs:keyref name="DefaultLangCodeMustExist" refer="mce:UniqueLangCodeInLocalizedDetails">
          <xs:selector xpath="."/>
          <xs:field xpath="@defaultLangCode"/>
        </xs:keyref>
      </xs:element>
      <xs:element name="Encryption" type="mce:EncryptionType" minOccurs="0" maxOccurs="1"/>
    </xs:sequence>
    <xs:attribute name="id" type="mce:GuidType" use="required"/>
  </xs:complexType>
  <xs:complexType name="VersionType">
    <xs:attribute name="major" type="xs:unsignedShort" use="required"/>
    <xs:attribute name="minor" type="xs:unsignedShort" use="required"/>
    <xs:attribute name="build" type="xs:unsignedShort" use="required"/>
    <xs:attribute name="revision" type="xs:unsignedShort" use="required"/>
  </xs:complexType>
  <xs:complexType name="PublisherType">
    <xs:attribute name="id" type="mce:GuidType" use="required"/>
  </xs:complexType>
  <xs:complexType name="LocalizedDetailsType">
    <xs:sequence>
      <xs:element name="PublisherName" type="mce:NameType"/>
      <xs:element name="Name" type="mce:RulePackNameType"/>
      <xs:element name="Description" type="mce:OptionalNameType"/>
    </xs:sequence>
    <xs:attribute name="langcode" type="mce:LangType" use="required"/>
  </xs:complexType>
  <xs:complexType name="DetailsType">
    <xs:sequence>
      <xs:element name="LocalizedDetails" type="mce:LocalizedDetailsType" maxOccurs="unbounded"/>
    </xs:sequence>
    <xs:attribute name="defaultLangCode" type="mce:LangType" use="required"/>
  </xs:complexType>
  <xs:complexType name="EncryptionType">
    <xs:sequence>
      <xs:element name="Key" type="xs:normalizedString"/>
      <xs:element name="IV" type="xs:normalizedString"/>
    </xs:sequence>
  </xs:complexType>
  <xs:simpleType name="RulePackNameType">
    <xs:restriction base="xs:token">
      <xs:minLength value="1"/>
      <xs:maxLength value="64"/>
    </xs:restriction>
  </xs:simpleType>
  <xs:simpleType name="NameType">
    <xs:restriction base="xs:normalizedString">
      <xs:minLength value="1"/>
      <xs:maxLength value="256"/>
    </xs:restriction>
  </xs:simpleType>
  <xs:simpleType name="OptionalNameType">
    <xs:restriction base="xs:normalizedString">
      <xs:minLength value="0"/>
      <xs:maxLength value="256"/>
    </xs:restriction>
  </xs:simpleType>
  <xs:simpleType name="RestrictedTermType">
    <xs:restriction base="xs:string">
      <xs:minLength value="1"/>
      <xs:maxLength value="100"/>
    </xs:restriction>
  </xs:simpleType>
  <xs:complexType name="RulesType">
    <xs:sequence>
      <xs:choice maxOccurs="unbounded">
        <xs:element name="Entity" type="mce:EntityType"/>
        <xs:element name="Affinity" type="mce:AffinityType"/>
        <xs:element name="Version" type="mce:VersionedRuleType"/>
      </xs:choice>
      <xs:choice minOccurs="0" maxOccurs="unbounded">
        <xs:element name="Regex" type="mce:RegexType"/>
        <xs:element name="Keyword" type="mce:KeywordType"/>
        <xs:element name="Fingerprint" type="mce:FingerprintType"/>
        <xs:element name="ExtendedKeyword" type="mce:ExtendedKeywordType"/>
      </xs:choice>
      <xs:element name="LocalizedStrings" type="mce:LocalizedStringsType"/>
    </xs:sequence>
  </xs:complexType>
  <xs:complexType name="EntityType">
    <xs:sequence>
      <xs:element name="Pattern" type="mce:PatternType" maxOccurs="unbounded"/>
      <xs:element name="Version" type="mce:VersionedPatternType" minOccurs="0" maxOccurs="unbounded" />
    </xs:sequence>
    <xs:attribute name="id" type="mce:GuidType" use="required"/>
    <xs:attribute name="patternsProximity" type="mce:ProximityType" use="required"/>
    <xs:attribute name="recommendedConfidence" type="mce:ProbabilityType"/>
    <xs:attribute name="workload" type="mce:WorkloadType"/>
  </xs:complexType>
  <xs:complexType name="PatternType">
    <xs:sequence>
      <xs:element name="IdMatch" type="mce:IdMatchType"/>
      <xs:choice minOccurs="0" maxOccurs="unbounded">
        <xs:element name="Match" type="mce:MatchType"/>
        <xs:element name="Any" type="mce:AnyType"/>
      </xs:choice>
    </xs:sequence>
    <xs:attribute name="confidenceLevel" type="mce:ProbabilityType" use="required"/>
  </xs:complexType>
  <xs:complexType name="AffinityType">
    <xs:sequence>
      <xs:element name="Evidence" type="mce:EvidenceType" maxOccurs="unbounded"/>
      <xs:element name="Version" type="mce:VersionedEvidenceType" minOccurs="0" maxOccurs="unbounded" />
    </xs:sequence>
    <xs:attribute name="id" type="mce:GuidType" use="required"/>
    <xs:attribute name="evidencesProximity" type="mce:ProximityType" use="required"/>
    <xs:attribute name="thresholdConfidenceLevel" type="mce:ProbabilityType" use="required"/>
    <xs:attribute name="workload" type="mce:WorkloadType"/>
  </xs:complexType>
  <xs:complexType name="EvidenceType">
    <xs:sequence>
      <xs:choice maxOccurs="unbounded">
        <xs:element name="Match" type="mce:MatchType"/>
        <xs:element name="Any" type="mce:AnyType"/>
      </xs:choice>
    </xs:sequence>
    <xs:attribute name="confidenceLevel" type="mce:ProbabilityType" use="required"/>
  </xs:complexType>
  <xs:complexType name="IdMatchType">
    <xs:attribute name="idRef" type="xs:string" use="required"/>
  </xs:complexType>
  <xs:complexType name="MatchType">
    <xs:attribute name="idRef" type="xs:string" use="required"/>
    <xs:attribute name="minCount" type="xs:positiveInteger" use="optional"/>
    <xs:attribute name="uniqueResults" type="xs:boolean" use="optional"/>
  </xs:complexType>
  <xs:complexType name="AnyType">
    <xs:sequence>
      <xs:choice maxOccurs="unbounded">
        <xs:element name="Match" type="mce:MatchType"/>
        <xs:element name="Any" type="mce:AnyType"/>
      </xs:choice>
    </xs:sequence>
    <xs:attribute name="minMatches" type="xs:nonNegativeInteger" default="1"/>
    <xs:attribute name="maxMatches" type="xs:nonNegativeInteger" use="optional"/>
  </xs:complexType>
  <xs:simpleType name="ProximityType">
    <xs:union>
      <xs:simpleType>
        <xs:restriction base='xs:string'>
          <xs:enumeration value="unlimited"/>
        </xs:restriction>
      </xs:simpleType>
      <xs:simpleType>
        <xs:restriction base="xs:positiveInteger">
          <xs:minInclusive value="1"/>
        </xs:restriction>
      </xs:simpleType>
    </xs:union>
  </xs:simpleType>
  <xs:simpleType name="ProbabilityType">
    <xs:restriction base="xs:integer">
      <xs:minInclusive value="1"/>
      <xs:maxInclusive value="100"/>
    </xs:restriction>
  </xs:simpleType>
  <xs:simpleType name="WorkloadType">
    <xs:restriction base="xs:string">
      <xs:enumeration value="Exchange"/>
      <xs:enumeration value="Outlook"/>
    </xs:restriction>
  </xs:simpleType>
  <xs:simpleType name="EngineVersionType">
    <xs:restriction base="xs:token">
      <xs:pattern value="^\d{2}\.01?\.\d{3,4}\.\d{1,3}$"/>
    </xs:restriction>
  </xs:simpleType>
  <xs:complexType name="VersionedRuleType">
    <xs:choice maxOccurs="unbounded">
      <xs:element name="Entity" type="mce:EntityType"/>
      <xs:element name="Affinity" type="mce:AffinityType"/>
    </xs:choice>
    <xs:attribute name="minEngineVersion" type="mce:EngineVersionType" use="required" />
  </xs:complexType>
  <xs:complexType name="VersionedPatternType">
    <xs:sequence>
      <xs:element name="Pattern" type="mce:PatternType" maxOccurs="unbounded"/>
    </xs:sequence>
    <xs:attribute name="minEngineVersion" type="mce:EngineVersionType" use="required" />
  </xs:complexType>
  <xs:complexType name="VersionedEvidenceType">
    <xs:sequence>
      <xs:element name="Evidence" type="mce:EvidenceType" maxOccurs="unbounded"/>
    </xs:sequence>
    <xs:attribute name="minEngineVersion" type="mce:EngineVersionType" use="required" />
  </xs:complexType>
  <xs:simpleType name="FingerprintValueType">
    <xs:restriction base="xs:string">
      <xs:minLength value="2732"/>
      <xs:maxLength value="2732"/>
    </xs:restriction>
  </xs:simpleType>
  <xs:complexType name="FingerprintType">
    <xs:simpleContent>
      <xs:extension base="mce:FingerprintValueType">
        <xs:attribute name="id" type="xs:token" use="required"/>
        <xs:attribute name="threshold" type="mce:ProbabilityType" use="required"/>
        <xs:attribute name="shingleCount" type="xs:positiveInteger" use="required"/>
        <xs:attribute name="description" type="xs:string" use="optional"/>
      </xs:extension>
    </xs:simpleContent>
  </xs:complexType>
  <xs:complexType name="RegexType">
    <xs:simpleContent>
      <xs:extension base="xs:string">
        <xs:attribute name="id" type="xs:token" use="required"/>
      </xs:extension>
    </xs:simpleContent>
  </xs:complexType>
  <xs:complexType name="KeywordType">
    <xs:sequence>
      <xs:element name="Group" type="mce:GroupType" maxOccurs="unbounded"/>
    </xs:sequence>
    <xs:attribute name="id" type="xs:token" use="required"/>
  </xs:complexType>
  <xs:complexType name="GroupType">
    <xs:sequence>
      <xs:choice>
        <xs:element name="Term" type="mce:TermType" maxOccurs="unbounded"/>
      </xs:choice>
    </xs:sequence>
    <xs:attribute name="matchStyle" default="word">
      <xs:simpleType>
        <xs:restriction base="xs:NMTOKEN">
          <xs:enumeration value="word"/>
          <xs:enumeration value="string"/>
        </xs:restriction>
      </xs:simpleType>
    </xs:attribute>
  </xs:complexType>
  <xs:complexType name="TermType">
    <xs:simpleContent>
      <xs:extension base="mce:RestrictedTermType">
        <xs:attribute name="caseSensitive" type="xs:boolean" default="false"/>
      </xs:extension>
    </xs:simpleContent>
  </xs:complexType>
  <xs:complexType name="ExtendedKeywordType">
    <xs:simpleContent>
      <xs:extension base="xs:string">
        <xs:attribute name="id" type="xs:token" use="required"/>
      </xs:extension>
    </xs:simpleContent>
  </xs:complexType>
  <xs:complexType name="LocalizedStringsType">
    <xs:sequence>
      <xs:element name="Resource" type="mce:ResourceType" maxOccurs="unbounded">
      <xs:key name="UniqueLangCodeUsedInNamePerResource">
        <xs:selector xpath="mce:Name"/>
        <xs:field xpath="@langcode"/>
      </xs:key>
      <xs:key name="UniqueLangCodeUsedInDescriptionPerResource">
        <xs:selector xpath="mce:Description"/>
        <xs:field xpath="@langcode"/>
      </xs:key>
    </xs:element>
    </xs:sequence>
  </xs:complexType>
  <xs:complexType name="ResourceType">
    <xs:sequence>
      <xs:element name="Name" type="mce:ResourceNameType" maxOccurs="unbounded"/>
      <xs:element name="Description" type="mce:DescriptionType" minOccurs="0" maxOccurs="unbounded"/>
    </xs:sequence>
    <xs:attribute name="idRef" type="mce:GuidType" use="required"/>
  </xs:complexType>
  <xs:complexType name="ResourceNameType">
    <xs:simpleContent>
      <xs:extension base="xs:string">
        <xs:attribute name="default" type="xs:boolean" default="false"/>
        <xs:attribute name="langcode" type="mce:LangType" use="required"/>
      </xs:extension>
    </xs:simpleContent>
  </xs:complexType>
  <xs:complexType name="DescriptionType">
    <xs:simpleContent>
      <xs:extension base="xs:string">
        <xs:attribute name="default" type="xs:boolean" default="false"/>
        <xs:attribute name="langcode" type="mce:LangType" use="required"/>
      </xs:extension>
    </xs:simpleContent>
  </xs:complexType>
</xs:schema>
```

## <a name="more-information"></a>更多信息

- [了解数据丢失防护](dlp-learn-about-dlp.md)
- [敏感信息类型属性定义](sensitive-information-type-entity-definitions.md)
- [敏感信息类型函数](sit-functions.md)
