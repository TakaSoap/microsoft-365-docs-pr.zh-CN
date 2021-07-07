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
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 了解如何在合规中心中创建并导入策略的自定义敏感信息类型。
ms.openlocfilehash: ab89104804fd1af781ca30ed8893bed60cd29e47
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2021
ms.locfileid: "53322253"
---
# <a name="create-a-custom-sensitive-information-type-using-powershell"></a><span data-ttu-id="57ed8-103">使用 PowerShell 创建自定义敏感信息类型</span><span class="sxs-lookup"><span data-stu-id="57ed8-103">Create a custom sensitive information type using PowerShell</span></span>

<span data-ttu-id="57ed8-104">本主题介绍如何使用 PowerShell 创建定义自己的自定义 [敏感信息类型](sensitive-information-type-entity-definitions.md)的 XML *规则包* 文件。</span><span class="sxs-lookup"><span data-stu-id="57ed8-104">This topic shows you how to use PowerShell to create an XML *rule package* file that defines your own custom [sensitive information types](sensitive-information-type-entity-definitions.md).</span></span> <span data-ttu-id="57ed8-105">需要了解如何创建正则表达式。</span><span class="sxs-lookup"><span data-stu-id="57ed8-105">You need to know how to create a regular expression.</span></span> <span data-ttu-id="57ed8-106">为提供示例，本主题创建识别员工 ID 的自定义敏感信息类型。</span><span class="sxs-lookup"><span data-stu-id="57ed8-106">As an example, this topic creates a custom sensitive information type that identifies an employee ID.</span></span> <span data-ttu-id="57ed8-107">可以此示例 XML 为起点，创建自己的 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="57ed8-107">You can use this example XML as a starting point for your own XML file.</span></span> <span data-ttu-id="57ed8-108">如果不熟悉敏感信息类型，请参阅[了解敏感信息类型](sensitive-information-type-learn-about.md)。</span><span class="sxs-lookup"><span data-stu-id="57ed8-108">If you are new to sensitive information types, see [Learn about sensitive information types](sensitive-information-type-learn-about.md).</span></span>

<span data-ttu-id="57ed8-p102">创建格式标准的 XML 文件后，可使用 Microsoft 365 PowerShell 将其上传到 Microsoft 365。然后，就可以在策略中使用自定义敏感信息类型，并测试其是否按预期检测敏感信息。</span><span class="sxs-lookup"><span data-stu-id="57ed8-p102">After you've created a well-formed XML file, you can upload it to Microsoft 365 by using Microsoft 365 PowerShell. Then you're ready to use your custom sensitive information type in your policies and test that it's detecting the sensitive information as you intended.</span></span>

> [!NOTE]
> <span data-ttu-id="57ed8-111">如果不需要 PowerShell 提供的细化控制，可以在合规中心中创建自定义敏感信息类型。</span><span class="sxs-lookup"><span data-stu-id="57ed8-111">If you don't need the fine grained control that PowerShell provides, you can create custom sensitive information types in the Compliance center.</span></span> <span data-ttu-id="57ed8-112">有关详细信息，请参阅[创建自定义敏感信息类型](create-a-custom-sensitive-information-type.md)。</span><span class="sxs-lookup"><span data-stu-id="57ed8-112">For more information, see [Create a custom sensitive information type](create-a-custom-sensitive-information-type.md).</span></span>

## <a name="important-disclaimer"></a><span data-ttu-id="57ed8-113">重要免责声明</span><span class="sxs-lookup"><span data-stu-id="57ed8-113">Important disclaimer</span></span>

<span data-ttu-id="57ed8-p104">由于客户环境和内容匹配要求的多样性，Microsoft 支持部门无法帮助提供自定义内容匹配定义（例如，定义自定义分类或正则表达式（也称为“RegEx”）模式）。对于自定义内容匹配的开发、测试和调试，Microsoft 365 客户将需要依赖于内部 IT 资源，或使用 Microsoft 咨询服务 (MCS) 等外部咨询资源。支持工程师可提供针对该功能的有限支持，但无法保证任何自定义内容匹配开发都能满足客户的要求或义务。作为可提供的支持类型的示例，可以提供示例正则表达式模式以供测试使用。或者，支持人员可以帮助对现有 RegEx 模式（单个特定内容示例未按预期触发）进行故障排除。</span><span class="sxs-lookup"><span data-stu-id="57ed8-p104">Due to the variances in customer environments and content match requirements, Microsoft Support cannot assist in providing custom content-matching definitions; e.g., defining custom classifications or regular expression (also known as RegEx) patterns. For custom content-matching development, testing, and debugging, Microsoft 365 customers will need to rely upon internal IT resources, or use an external consulting resource such as Microsoft Consulting Services (MCS). Support engineers can provide limited support for the feature, but cannot provide assurances that any custom content-matching development will fulfill the customer's requirements or obligations.  As an example of the type of support that can be provided, sample regular expression patterns may be provided for testing purposes. Or, support can assist with troubleshooting an existing RegEx pattern which is not triggering as expected with a single specific content example.</span></span>

<span data-ttu-id="57ed8-119">请参阅本主题中的[要注意的潜在验证问题](#potential-validation-issues-to-be-aware-of)。</span><span class="sxs-lookup"><span data-stu-id="57ed8-119">See [Potential validation issues to be aware of](#potential-validation-issues-to-be-aware-of) in this topic.</span></span>

<span data-ttu-id="57ed8-120">有关用于处理文本的 Boost.RegEx（以前称为 RegEx++）引擎的详细信息，请参阅 [Boost.Regex 5.1.3](https://www.boost.org/doc/libs/1_68_0/libs/regex/doc/html/)。</span><span class="sxs-lookup"><span data-stu-id="57ed8-120">For more information about the Boost.RegEx (formerly known as RegEx++) engine that's used for processing the text, see [Boost.Regex 5.1.3](https://www.boost.org/doc/libs/1_68_0/libs/regex/doc/html/).</span></span>

> [!NOTE]
> <span data-ttu-id="57ed8-121">如果使用与号字符 (&) 自定义敏感信息类型中关键字的一部分，请注意存在一个已知问题。</span><span class="sxs-lookup"><span data-stu-id="57ed8-121">If you use an ampersand character (&) as part of a keyword in your custom sensitive information type, please note that there is a known issue.</span></span> <span data-ttu-id="57ed8-122">您应该在字符周围添加一个附加的术语，使其具有空格，以确保正确标识该字符，例如 L & P _而不是_ L&P。</span><span class="sxs-lookup"><span data-stu-id="57ed8-122">You should add an additional term with spaces around the character to make sure that the character is properly identified, for example, L & P _not_ L&P.</span></span>

## <a name="sample-xml-of-a-rule-package"></a><span data-ttu-id="57ed8-123">规则包 XML 示例</span><span class="sxs-lookup"><span data-stu-id="57ed8-123">Sample XML of a rule package</span></span>

<span data-ttu-id="57ed8-p106">下面就是本主题将创建的规则包 XML 示例。下面各部分介绍了元素和特性。</span><span class="sxs-lookup"><span data-stu-id="57ed8-p106">Here's the sample XML of the rule package that we'll create in this topic. Elements and attributes are explained in the sections below.</span></span>
  
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

## <a name="what-are-your-key-requirements-rule-entity-pattern-elements"></a><span data-ttu-id="57ed8-p107">关键要求是什么？[Rule、Entity、Pattern 元素]</span><span class="sxs-lookup"><span data-stu-id="57ed8-p107">What are your key requirements? [Rule, Entity, Pattern elements]</span></span>

<span data-ttu-id="57ed8-128">开始前，有必要了解规则 XML 架构的基本结构，以及如何使用这种结构来定义用于标识适当内容的自定义敏感信息类型。</span><span class="sxs-lookup"><span data-stu-id="57ed8-128">Before you get started, it's helpful to understand the basic structure of the XML schema for a rule, and how you can use this structure to define your custom sensitive information type so that it will identify the right content.</span></span>
  
<span data-ttu-id="57ed8-p108">一个规则定义一个或多个实体（即敏感信息类型），每个实体定义一个或多个模式。模式是策略在评估电子邮件和文档等内容时查找的内容。</span><span class="sxs-lookup"><span data-stu-id="57ed8-p108">A rule defines one or more entities (sensitive information types), and each entity defines one or more patterns. A pattern is what a policy looks for when it evaluates content such as email and documents.</span></span>

<span data-ttu-id="57ed8-p109">在本主题中，XML 标记使用规则来表示定义实体（也称为敏感信息类型）的模式。所以在本主题中，当你看到规则时，请考虑实体或敏感信息类型，而非条件和操作。</span><span class="sxs-lookup"><span data-stu-id="57ed8-p109">In this topic, the XML markup uses rule to mean the patterns that define an entity, also known as a sensitive information type. So in this topic, when you see rule, think entity or sensitive information type, not conditions and actions.</span></span>
  
### <a name="simplest-scenario-entity-with-one-pattern"></a><span data-ttu-id="57ed8-133">最简单方案：包含一个模式的实体</span><span class="sxs-lookup"><span data-stu-id="57ed8-133">Simplest scenario: entity with one pattern</span></span>

<span data-ttu-id="57ed8-p110">以下是一个最简单方案：假设你希望策略标识的内容包含采用九位数格式的组织员工 ID。因此，模式是指标识九位数的规则中包含的正则表达式。任何包含九位数的内容都符合模式。</span><span class="sxs-lookup"><span data-stu-id="57ed8-p110">Here's the simplest scenario. You want your policy to identify content that contains your organization's employee ID, which is formatted as a nine-digit number. So the pattern refers to a regular expression contained in the rule that identifies nine-digit numbers. Any content containing a nine-digit number satisfies the pattern.</span></span>
  
![包含一个模式的实体的关系图](../media/4cc82dcf-068f-43ff-99b2-bac3892e9819.png)
  
<span data-ttu-id="57ed8-139">虽然简单，但此模式可能会标识许多误报内容，因为包含任何九位数的匹配内容不一定是员工 ID。</span><span class="sxs-lookup"><span data-stu-id="57ed8-139">However, while simple, this pattern may identify many false positives by matching content that contains any nine-digit number that is not necessarily an employee ID.</span></span>
  
### <a name="more-common-scenario-entity-with-multiple-patterns"></a><span data-ttu-id="57ed8-140">更常见方案：包含多个模式的实体</span><span class="sxs-lookup"><span data-stu-id="57ed8-140">More common scenario: entity with multiple patterns</span></span>

<span data-ttu-id="57ed8-141">因此，更常见的做法是使用多个模式定义实体。这样，除了实体（如九位数）外，这些模式还可标识证据（如关键字或日期）。</span><span class="sxs-lookup"><span data-stu-id="57ed8-141">For this reason, it's more common to define an entity by using more than one pattern, where the patterns identify supporting evidence (such as a keyword or date) in addition to the entity (such as a nine-digit number).</span></span>
  
<span data-ttu-id="57ed8-142">例如，若要更有胜算地标识包含员工 ID 的内容，除了九位数外，还可以定义另一种模式来标识聘用日期，并再定义一种模式来标识聘用日期和关键字（如“员工 ID”）。</span><span class="sxs-lookup"><span data-stu-id="57ed8-142">For example, to increase the likelihood of identifying content that contains an employee ID, you can define another pattern that also identifies a hire date, and define yet another pattern that identifies both a hire date and a keyword (such as "employee ID"), in addition to the nine-digit number.</span></span>
  
![包含多个模式的实体的关系图](../media/c8dc2c9d-00c6-4ebc-889a-53b41a90024a.png)
  
<span data-ttu-id="57ed8-144">对于此结构，请务必注意以下几点：</span><span class="sxs-lookup"><span data-stu-id="57ed8-144">Note a couple of important aspects of this structure:</span></span>
  
- <span data-ttu-id="57ed8-p111">需要更多证据的模式具有更高的可信度。这一点非常有用，因为稍后在策略中使用此敏感信息类型时，可以仅对较高可信度匹配内容执行限制较高的操作（如屏蔽内容），并对较低可信度匹配内容执行限制较低的操作（如发送通知）。</span><span class="sxs-lookup"><span data-stu-id="57ed8-p111">Patterns that require more evidence have a higher confidence level. This is useful because when you later use this sensitive information type in a policy, you can use more restrictive actions (such as block content) with only the higher-confidence matches, and you can use less restrictive actions (such as send notification) with the lower-confidence matches.</span></span>

- <span data-ttu-id="57ed8-p112">支持元素 IdMatch 和 Match 引用的正则表达式和关键字实际上是 Rule 元素（而不是 Pattern 元素）的子级。这些支持元素是由 Pattern 引用，但包含在 Rule 中。也就是说，单个定义的支持元素（如正则表达式或关键字列表）可被多个实体和模式引用。</span><span class="sxs-lookup"><span data-stu-id="57ed8-p112">The supporting IdMatch and Match elements reference regexes and keywords that are actually children of the Rule element, not the Pattern. These supporting elements are referenced by the Pattern but included in the Rule. This means that a single definition of a supporting element, like a regular expression or a keyword list, can be referenced by multiple entities and patterns.</span></span>

## <a name="what-entity-do-you-need-to-identify-entity-element-id-attribute"></a><span data-ttu-id="57ed8-p113">需要标识什么实体？[Entity 元素，id 特性]</span><span class="sxs-lookup"><span data-stu-id="57ed8-p113">What entity do you need to identify? [Entity element, id attribute]</span></span>

<span data-ttu-id="57ed8-p114">实体是包含明确定义的模式的敏感信息类型，如信用卡号。每个实体都有一个唯一 GUID 作为自己的 ID。</span><span class="sxs-lookup"><span data-stu-id="57ed8-p114">An entity is a sensitive information type, such as a credit card number, that has a well-defined pattern. Each entity has a unique GUID as its ID.</span></span>
  
### <a name="name-the-entity-and-generate-its-guid"></a><span data-ttu-id="57ed8-154">命名实体并生成 GUID</span><span class="sxs-lookup"><span data-stu-id="57ed8-154">Name the entity and generate its GUID</span></span>

1. <span data-ttu-id="57ed8-155">在选择的 XML 编辑器中，添加规则和实体元素。</span><span class="sxs-lookup"><span data-stu-id="57ed8-155">In your XML editor of choice, add the Rules and Entity elements.</span></span>
2. <span data-ttu-id="57ed8-p115">添加包含自定义实体名称（在本示例中，为“员工 ID”）的注释。稍后，将把实体名称添加到本地化字符串部分，此名称就是在创建 DLP 策略时在 UI 中看到的名称。</span><span class="sxs-lookup"><span data-stu-id="57ed8-p115">Add a comment that contains the name of your custom entity — in this example, Employee ID. Later, you'll add the entity name to the localized strings section, and that name is what appears in the UI when you create a policy.</span></span>
3. <span data-ttu-id="57ed8-158">生成实体的 GUID。</span><span class="sxs-lookup"><span data-stu-id="57ed8-158">Generate a GUID for your entity.</span></span> <span data-ttu-id="57ed8-159">有几种方法可生成 GUID，可在 PowerShell 中通过键入 **[guid]::NewGuid()** 轻松生成。</span><span class="sxs-lookup"><span data-stu-id="57ed8-159">There are several ways to generate GUIDs, but you can do it easily in PowerShell by typing **[guid]::NewGuid()**.</span></span> <span data-ttu-id="57ed8-160">稍后还要将实体 GUID 添加到本地化的字符串部分。</span><span class="sxs-lookup"><span data-stu-id="57ed8-160">Later, you'll also add the entity GUID to the localized strings section.</span></span>
  
![显示 Rule 和 Entity 元素的 XML 标记](../media/c46c0209-0947-44e0-ac3a-8fd5209a81aa.png)
  
## <a name="what-pattern-do-you-want-to-match-pattern-element-idmatch-element-regex-element"></a><span data-ttu-id="57ed8-p117">要匹配什么模式？[Pattern 元素、IdMatch 元素、Regex 元素]</span><span class="sxs-lookup"><span data-stu-id="57ed8-p117">What pattern do you want to match? [Pattern element, IdMatch element, Regex element]</span></span>

<span data-ttu-id="57ed8-p118">模式包含敏感信息类型要查找的内容列表。其中可能包括正则表达式、关键字和内置函数（用于执行任务，如运行正则表达式以查找日期或地址）。敏感信息类型可包含多个具有唯一可信度的模式。</span><span class="sxs-lookup"><span data-stu-id="57ed8-p118">The pattern contains the list of what the sensitive information type is looking for. This can include regexes, keywords, and built-in functions (which perform tasks like running regexes to find dates or addresses). Sensitive information types can have multiple patterns with unique confidences.</span></span>
  
<span data-ttu-id="57ed8-p119">以下所有模式的共同点是，全都引用同一个正则表达式，以查找两边是空格 (\s) ... (\s) 的九位数 (\d{9})。此正则表达式由 IdMatch 元素引用，同时也是所有查找“员工 ID”实体的模式的通用要求。IdMatch 是模式尝试匹配的标识符，如员工 ID、信用卡号或身份证号。每个 Pattern 元素只能有一个 IdMatch 元素。</span><span class="sxs-lookup"><span data-stu-id="57ed8-p119">What all of the below patterns have in common is that they all reference the same regular expression, which looks for a nine-digit number (\d{9}) surrounded by white space (\s) … (\s). This regular expression is referenced by the IdMatch element and is the common requirement for all patterns that look for the Employee ID entity. IdMatch is the identifier that the pattern is to trying to match, such as Employee ID or credit card number or social security number. A Pattern element must have exactly one IdMatch element.</span></span>
  
![显示引用一个 Regex 元素的多个 Pattern 元素的 XML 标记](../media/8f3f497b-3b8b-4bad-9c6a-d9abf0520854.png)
  
<span data-ttu-id="57ed8-p120">若符合，模式返回可用于策略内条件中的计数和可信度。向策略添加用于检测敏感信息类型的条件时，可以编辑计数和可信度（如下所示）。本主题稍后将解释可信度（亦称为匹配准确度）。</span><span class="sxs-lookup"><span data-stu-id="57ed8-p120">When satisfied, a pattern returns a count and confidence level, which you can use in the conditions in your policy. When you add a condition for detecting a sensitive information type to a policy, you can edit the count and confidence level as shown here. Confidence level (also called match accuracy) is explained later in this topic.</span></span>
  
![“实例计数”和“匹配准确度”选项](../media/sit-confidence-level.png)
  
<span data-ttu-id="57ed8-p121">创建正则表达式时，请注意一些潜在问题。例如，如果编写并上传的正则表达式标识过多内容，这可能会影响性能。若要详细了解这些潜在问题，请参阅后面的[要注意的潜在验证问题](#potential-validation-issues-to-be-aware-of)部分。</span><span class="sxs-lookup"><span data-stu-id="57ed8-p121">When you create your regular expression, keep in mind that there are potential issues to be aware of. For example, if you write and upload a regex that identifies too much content, this can impact performance. To learn more about these potential issues, see the later section [Potential validation issues to be aware of](#potential-validation-issues-to-be-aware-of).</span></span>
  
## <a name="do-you-want-to-require-additional-evidence-match-element-mincount-attribute"></a><span data-ttu-id="57ed8-p122">是否需要其他证据？[Match 元素、minCount 特性]</span><span class="sxs-lookup"><span data-stu-id="57ed8-p122">Do you want to require additional evidence? [Match element, minCount attribute]</span></span>

<span data-ttu-id="57ed8-182">除了 IdMatch 外，模式还可以使用 Match 元素来要求发现其他证据，如关键字、正则表达式、日期或地址。</span><span class="sxs-lookup"><span data-stu-id="57ed8-182">In addition to the IdMatch, a pattern can use the Match element to require additional supporting evidence, such as a keyword, regex, date, or address.</span></span>
  
<span data-ttu-id="57ed8-p123">一个 Pattern 可包含多个 Match 元素；可以直接将 Match 元素添加到 Pattern 元素中，也可以使用 Any 元素合并 Match 元素。Match 元素通过隐式 AND 运算符进行联接；必须符合所有 Match 元素，才算与模式匹配。可使用 Any 元素引入 AND 或 OR 运算符（有关详细信息，请参阅后面的部分）。</span><span class="sxs-lookup"><span data-stu-id="57ed8-p123">A Pattern can include multiple Match elements; they can be included directly in the Pattern element or combined by using the Any element. Match elements are joined by an implicit AND operator; all Match elements must be satisfied for the pattern to be matched. You can use the Any element to introduce AND or OR operators (more on that in a later section).</span></span>
  
<span data-ttu-id="57ed8-p124">可选的 minCount 特性可用于指定，必须为每个 Match 元素找到多少个匹配实例。例如，可指定至少必须找到关键字列表中的两个关键字时，才算符合模式。</span><span class="sxs-lookup"><span data-stu-id="57ed8-p124">You can use the optional minCount attribute to specify how many instances of a match need to be found for each of the Match elements. For example, you can specify that a pattern is satisfied only when at least two keywords from a keyword list are found.</span></span>
  
![显示包含 minCount 特性的 Match 元素的 XML 标记](../media/607f6b5e-2c7d-43a5-a131-a649f122e15a.png)
  
### <a name="keywords-keyword-group-and-term-elements-matchstyle-and-casesensitive-attributes"></a><span data-ttu-id="57ed8-189">关键字 [Keyword、Group 和 Term 元素，matchStyle 和 caseSensitive 特性]</span><span class="sxs-lookup"><span data-stu-id="57ed8-189">Keywords [Keyword, Group, and Term elements, matchStyle and caseSensitive attributes]</span></span>

<span data-ttu-id="57ed8-p125">在识别员工 ID 等敏感信息时，通常希望要求将关键字作为补强证据。例如，除匹配九位数字外，还可能希望查找“卡”、“徽章”或“ID”等字眼。为此，可使用 Keyword 元素。Keyword 元素具有一个 ID 属性，可由多个模式或实体中的多个 Match 元素引用。</span><span class="sxs-lookup"><span data-stu-id="57ed8-p125">When you identify sensitive information, like an employee ID, you often want to require keywords as corroborative evidence. For example, in addition to matching a nine-digit number, you may want to look for words like "card", "badge", or "ID". To do this, you use the Keyword element. The Keyword element has an ID attribute that can be referenced by multiple Match elements in multiple patterns or entities.</span></span>
  
<span data-ttu-id="57ed8-p126">关键字以 Term 元素列表的形式包含在 Group 元素中。Group 元素包含有以下两个可取值的 matchStyle 特性：</span><span class="sxs-lookup"><span data-stu-id="57ed8-p126">Keywords are included as a list of Term elements in a Group element. The Group element has a matchStyle attribute with two possible values:</span></span>
  
- <span data-ttu-id="57ed8-p127">**matchStyle="word"**：标识两边是空格或其他分隔符的整个字词的字词匹配。应始终使用 word，除非需要匹配部分字词或亚洲语言字词。</span><span class="sxs-lookup"><span data-stu-id="57ed8-p127">**matchStyle="word"** Word match identifies whole words surrounded by white space or other delimiters. You should always use word unless you need to match parts of words or match words in Asian languages.</span></span> 
    
- <span data-ttu-id="57ed8-p128">**matchStyle="string"**：标识无论两边是什么的字符串的字符串匹配。例如，“id”匹配“bid”和“idea”。仅在需要匹配亚洲语言字词或关键字可能是其他字符串的一部分时，才使用 string。</span><span class="sxs-lookup"><span data-stu-id="57ed8-p128">**matchStyle="string"** String match identifies strings no matter what they're surrounded by. For example, "id" will match "bid" and "idea". Use string only when you need to match Asian words or if your keyword may be included as part of other strings.</span></span> 
    
<span data-ttu-id="57ed8-201">最后，可使用 Term 元素的 caseSensitive 特性，以指定内容必须与关键字完全匹配，包括字母大小写。</span><span class="sxs-lookup"><span data-stu-id="57ed8-201">Finally, you can use the caseSensitive attribute of the Term element to specify that the content must match the keyword exactly, including lower- and upper-case letters.</span></span>
  
![显示引用关键字的 Match 元素的 XML 标记](../media/e729ba27-dec6-46f4-9242-584c6c12fd85.png)
  
### <a name="regular-expressions-regex-element"></a><span data-ttu-id="57ed8-203">正则表达式 [Regex 元素]</span><span class="sxs-lookup"><span data-stu-id="57ed8-203">Regular expressions [Regex element]</span></span>

<span data-ttu-id="57ed8-p129">在此示例中，员工 ID 实体已使用 IdMatch 元素引用模式（由空格包围的九位数字）的正则表达式。此外，模式还可使用 Match 元素再引用一个 Regex 元素，以识别补强证据，例如格式为美国邮政编码格式的五位或九位数字。</span><span class="sxs-lookup"><span data-stu-id="57ed8-p129">In this example, the employee ID entity already uses the IdMatch element to reference a regex for the pattern — a nine-digit number surrounded by whitespace. In addition, a pattern can use a Match element to reference an additional Regex element to identify corroborative evidence, such as a five- or nine-digit number in the format of a US zip code.</span></span>
  
### <a name="additional-patterns-such-as-dates-or-addresses-built-in-functions"></a><span data-ttu-id="57ed8-206">日期或地址等其他模式 [内置函数]</span><span class="sxs-lookup"><span data-stu-id="57ed8-206">Additional patterns such as dates or addresses [built-in functions]</span></span>

<span data-ttu-id="57ed8-p130">除了内置敏感信息类型外，敏感信息类型也可以使用能够识别确证性证据（如美国日期、欧洲日期、到期日期或美国地址）的内置函数。虽然 Microsoft 365 不支持上传你自己的自定义函数，但在创建自定义敏感信息类型时，实体可引用该内置函数。</span><span class="sxs-lookup"><span data-stu-id="57ed8-p130">In addition to the built-in sensitive information types, sensitive information types can also use built-in functions that can identify corroborative evidence such as a US date, EU date, expiration date, or US address. Microsoft 365 does not support uploading your own custom functions, but when you create a custom sensitive information type, your entity can reference the built-in functions.</span></span>
  
<span data-ttu-id="57ed8-209">例如，由于员工 ID 徽章中有聘用日期，因此这个自定义实体可使用内置函数 `Func_us_date` 标识采用美国通用格式的日期。</span><span class="sxs-lookup"><span data-stu-id="57ed8-209">For example, an employee ID badge has a hire date on it, so this custom entity can use the built-in function  `Func_us_date` to identify a date in the format commonly used in the US.</span></span> 
  
<span data-ttu-id="57ed8-210">有关详细信息，请参阅 [DLP 函数查找什么](what-the-dlp-functions-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="57ed8-210">For more information, see [What the DLP functions look for](what-the-dlp-functions-look-for.md).</span></span>
  
![显示引用内置函数的 Match 元素的 XML 标记](../media/dac6eae3-9c52-4537-b984-f9f127cc9c33.png)
  
## <a name="different-combinations-of-evidence-any-element-minmatches-and-maxmatches-attributes"></a><span data-ttu-id="57ed8-212">不同证据组合 [Any 元素、minMatches 和 maxMatches 特性]</span><span class="sxs-lookup"><span data-stu-id="57ed8-212">Different combinations of evidence [Any element, minMatches and maxMatches attributes]</span></span>

<span data-ttu-id="57ed8-p131">在 Pattern 元素中，所有 IdMatch 和 Match 元素均通过隐式 AND 运算符进行联接。也就是说，必须符合所有 IdMatch 和 Match 元素，才算符合模式。不过，可使用 Any 元素对 Match 元素进行分组，从而创建更灵活的匹配逻辑。例如，可使用 Any 元素匹配所有或确切的一部分 Match 子元素，或不匹配任何 Match 子元素。</span><span class="sxs-lookup"><span data-stu-id="57ed8-p131">In a Pattern element, all IdMatch and Match elements are joined by an implicit AND operator — all of the matches must be satisfied before the pattern can be satisfied. However, you can create more flexible matching logic by using the Any element to group Match elements. For example, you can use the Any element to match all, none, or an exact subset of its children Match elements.</span></span>
  
<span data-ttu-id="57ed8-p132">Any 元素有可选的 minMatches 和 maxMatches 特性，可用于定义必须符合多少个 Match 子元素才算与模式匹配。请注意，这些特性定义的是必须符合的 Match 元素数量，而不是为与模式匹配而找到的证据实例数。若要定义为特定匹配找到的最小实例数（如列表中的两个关键字），请使用 Match 元素的 minCount 特性（见上文）。</span><span class="sxs-lookup"><span data-stu-id="57ed8-p132">The Any element has optional minMatches and maxMatches attributes that you can use to define how many of the children Match elements must be satisfied before the pattern is matched. Note that these attributes define the number of Match elements that must be satisfied, not the number of instances of evidence found for the matches. To define a minimum number of instances for a specific match, such as two keywords from a list, use the minCount attribute for a Match element (see above).</span></span>
  
### <a name="match-at-least-one-child-match-element"></a><span data-ttu-id="57ed8-219">至少匹配一个 Match 子元素</span><span class="sxs-lookup"><span data-stu-id="57ed8-219">Match at least one child Match element</span></span>

<span data-ttu-id="57ed8-p133">若要规定至少必须符合多少个 Match 元素，可使用 minMatches 特性。实际上，这些 Match 元素是通过隐式 OR 运算符进行联接。如果从任一列表中找到美国格式日期或关键字，就符合以下 Any 元素。</span><span class="sxs-lookup"><span data-stu-id="57ed8-p133">If you want to require that only a minimum number of Match elements must be met, you can use the minMatches attribute. In effect, these Match elements are joined by an implicit OR operator. This Any element is satisfied if a US-formatted date or a keyword from either list is found.</span></span>

```xml
<Any minMatches="1" >
     <Match idRef="Func_us_date" />
     <Match idRef="Keyword_employee" />
     <Match idRef="Keyword_badge" />
</Any>
```
    
### <a name="match-an-exact-subset-of-any-children-match-elements"></a><span data-ttu-id="57ed8-223">匹配确切的一部分 Match 子元素</span><span class="sxs-lookup"><span data-stu-id="57ed8-223">Match an exact subset of any children Match elements</span></span>

<span data-ttu-id="57ed8-p134">若要规定必须符合确切数量的 Match 元素，可以将 minMatches 和 maxMatches 设置为相同值。仅当找到确切的一个日期或关键字时，才符合以下 Any 元素。如果找到多个，则与模式不匹配。</span><span class="sxs-lookup"><span data-stu-id="57ed8-p134">If you want to require that an exact number of Match elements must be met, you can set minMatches and maxMatches to the same value. This Any element is satisfied only if exactly one date or keyword is found — any more than that, and the pattern won't be matched.</span></span>

```xml
<Any minMatches="1" maxMatches="1" >
     <Match idRef="Func_us_date" />
     <Match idRef="Keyword_employee" />
     <Match idRef="Keyword_badge" />
</Any>
```
  
### <a name="match-none-of-children-match-elements"></a><span data-ttu-id="57ed8-226">与任何 Match 子元素都不匹配</span><span class="sxs-lookup"><span data-stu-id="57ed8-226">Match none of children Match elements</span></span>

<span data-ttu-id="57ed8-p135">若要规定只要缺少某证据才算符合模式，可以将 minMatches 和 maxMatches 同时设置为 0。如果关键字列表或其他证据可能发出误报，这样做就很有用。</span><span class="sxs-lookup"><span data-stu-id="57ed8-p135">If you want to require the absence of specific evidence for a pattern to be satisfied, you can set both minMatches and maxMatches to 0. This can be useful if you have a keyword list or other evidence that are likely to indicate a false positive.</span></span>
  
<span data-ttu-id="57ed8-p136">例如，“员工 ID”实体查找关键字“卡”，因为这可能会指代“ID 卡”。不过，如果“卡”仅出现在短语“信用卡”中，此内容中的“卡”就不太可能表示“ID 卡”。因此，可以将“信用卡”作为关键字，添加到匹配模式时要排除的术语列表。</span><span class="sxs-lookup"><span data-stu-id="57ed8-p136">For example, the employee ID entity looks for the keyword "card" because it might refer to an "ID card". However, if card appears only in the phrase "credit card", "card" in this content is unlikely to mean "ID card". So you can add "credit card" as a keyword to a list of terms that you want to exclude from satisfying the pattern.</span></span>
  
```xml
<Any minMatches="0" maxMatches="0" >
    <Match idRef="Keyword_false_positives_local" />
    <Match idRef="Keyword_false_positives_intl" />
</Any>
```

### <a name="match-a-number-of-unique-terms"></a><span data-ttu-id="57ed8-232">匹配多个唯一术语</span><span class="sxs-lookup"><span data-stu-id="57ed8-232">Match a number of unique terms</span></span>

<span data-ttu-id="57ed8-233">如果要匹配多个唯一术语，请使用 *uniqueResults* 参数，将其设置为 *true*，如下例所示：</span><span class="sxs-lookup"><span data-stu-id="57ed8-233">If you want to match a number of unique terms, use the *uniqueResults* parameter, set to *true*, as shown in the following example:</span></span>

```xml
<Pattern confidenceLevel="75">
    <IdMatch idRef="Salary_Revision_terms" />
    <Match idRef=" Salary_Revision_ID " minCount="3" uniqueResults="true" />
</Pattern>
```

<span data-ttu-id="57ed8-234">在此示例中，使用至少三个唯一匹配为薪资修订定义模式。</span><span class="sxs-lookup"><span data-stu-id="57ed8-234">In this example, a pattern is defined for salary revision using at least three unique matches.</span></span> 
  
## <a name="how-close-to-the-entity-must-the-other-evidence-be-patternsproximity-attribute"></a><span data-ttu-id="57ed8-p137">另一证据必须与实体有多接近？[patternsProximity 特性]</span><span class="sxs-lookup"><span data-stu-id="57ed8-p137">How close to the entity must the other evidence be? [patternsProximity attribute]</span></span>

<span data-ttu-id="57ed8-p138">敏感信息类型要查找表示员工 ID 的模式，此模式还查找确证性证据，如“ID”等关键字。很明显，此证据越接近，模式就越有可能是实际员工 ID。可使用 Entity 元素的必需特性 patternsProximity，确定模式中的另一证据必须与实体有多接近。</span><span class="sxs-lookup"><span data-stu-id="57ed8-p138">Your sensitive information type is looking for a pattern that represents an employee ID, and as part of that pattern it's also looking for corroborative evidence like a keyword such as "ID". It makes sense that the closer together this evidence is, the more likely the pattern is to be an actual employee ID. You can determine how close other evidence in the pattern must be to the entity by using the required patternsProximity attribute of the Entity element.</span></span>
  
![显示 patternsProximity 特性的 XML 标记](../media/e97eb7dc-b897-4e11-9325-91c742d9839b.png)
  
<span data-ttu-id="57ed8-p139">对于实体中的每种模式，patternsProximity 特性值都定义针对相应模式指定的其他所有 Match 与 IdMatch 位置的距离（以 Unicode 字符数为单位）。接近度窗口以 IdMatch 位置为关键主体，向 IdMatch 左右延伸。</span><span class="sxs-lookup"><span data-stu-id="57ed8-p139">For each pattern in the entity, the patternsProximity attribute value defines the distance (in Unicode characters) from the IdMatch location for all other Matches specified for that Pattern. The proximity window is anchored by the IdMatch location, with the window extending to the left and right of the IdMatch.</span></span>
  
![接近度窗口关系图](../media/b593dfd1-5eef-4d79-8726-a28923f7c31e.png)
  
<span data-ttu-id="57ed8-p140">下面的示例展示了接近度窗口如何影响模式匹配，其中“员工 ID”自定义实体的 IdMatch 元素要求至少必须有一个关键字或日期确证性匹配。仅 ID1 匹配，因为对于 ID2 和 ID3，在接近度窗口中找不到任何确证性证据或只找到部分确证性证据。</span><span class="sxs-lookup"><span data-stu-id="57ed8-p140">The example below illustrates how the proximity window affects the pattern matching where IdMatch element for the employee ID custom entity requires at least one corroborating match of keyword or date. Only ID1 matches because for ID2 and ID3, either no or only partial corroborating evidence is found within the proximity window.</span></span>
  
![确证性证据和接近度窗口的关系图](../media/dc68e38e-dfa1-45b8-b204-89c8ba121f96.png)
  
<span data-ttu-id="57ed8-p141">请注意，对于电子邮件，邮件正文和每个附件均被视为独立项。也就是说，接近度窗口不会超越各项末端。对于每一项（附件或正文），idMatch 和确证性证据都必须驻留在相应项中。</span><span class="sxs-lookup"><span data-stu-id="57ed8-p141">Note that for email, the message body and each attachment are treated as separate items. This means that the proximity window does not extend beyond the end of each of these items. For each item (attachment or body), both the idMatch and corroborative evidence needs to reside in that item.</span></span>
  
## <a name="what-are-the-right-confidence-levels-for-different-patterns-confidencelevel-attribute-recommendedconfidence-attribute"></a><span data-ttu-id="57ed8-p142">什么是各个模式的合适可信度？[confidenceLevel 特性、recommendedConfidence 特性]</span><span class="sxs-lookup"><span data-stu-id="57ed8-p142">What are the right confidence levels for different patterns? [confidenceLevel attribute, recommendedConfidence attribute]</span></span>

<span data-ttu-id="57ed8-p143">模式需要的证据越多，模式匹配时所标识的实际实体（如员工 ID）的可信度就越高。例如，与只要求匹配九位数 ID 的模式相比，要求匹配九位数 ID、聘用日期和关键字（极为接近）的模式的可信度更高。</span><span class="sxs-lookup"><span data-stu-id="57ed8-p143">The more evidence that a pattern requires, the more confidence you have that an actual entity (such as employee ID) has been identified when the pattern is matched. For example, you have more confidence in a pattern that requires a nine-digit ID number, hire date, and keyword in close proximity, than you do in a pattern that requires only a nine-digit ID number.</span></span>
  
<span data-ttu-id="57ed8-p144">Pattern 元素有必需的 confidenceLevel 属性。可将 confidenceLevel 值（介于 1 和 100 之间的整数）视为实体中每个模式的唯一 ID - 实体中的模式必须具有你分配的不同的可信度。整数值是否精确并不重要 - 只需选取对合规性团队有意义的数字即可。上传自定义敏感信息类型和创建策略后，可以在所创建规则的条件中引用这些可信度。</span><span class="sxs-lookup"><span data-stu-id="57ed8-p144">The Pattern element has a required confidenceLevel attribute. You can think of the value of confidenceLevel (an integer between 1 and 100) as a unique ID for each pattern in an entity — the patterns in an entity must have different confidence levels that you assign. The precise value of the integer doesn't matter — simply pick numbers that make sense to your compliance team. After you upload your custom sensitive information type and then create a policy, you can reference these confidence levels in the conditions of the rules that you create.</span></span>
  
![显示包含不同 confidenceLevel 特性值的 Pattern 元素的 XML 标记](../media/sit-xml-markedup-2.png)
  
<span data-ttu-id="57ed8-259">除每个模式的 confidenceLevel 外，Entity 还有一个 recommendedConfidence 属性。</span><span class="sxs-lookup"><span data-stu-id="57ed8-259">In addition to confidenceLevel for each Pattern, the Entity has a recommendedConfidence attribute.</span></span> <span data-ttu-id="57ed8-260">可将推荐的可信度属性视为规则的默认可信度级别。</span><span class="sxs-lookup"><span data-stu-id="57ed8-260">The recommended confidence attribute can be thought of as the default confidence level for the rule.</span></span> <span data-ttu-id="57ed8-261">在策略中创建规则时，如果不指定规则要使用的可信度级别，则该规则将基于推荐的实体可信度级别进行匹配。</span><span class="sxs-lookup"><span data-stu-id="57ed8-261">When you create a rule in a policy, if you don't specify a confidence level for the rule to use, that rule will match based on the recommended confidence level for the entity.</span></span> <span data-ttu-id="57ed8-262">请注意，规则包中的每个实体 ID 都必须使用 recommendedConfidence 属性，如果该属性缺失，将无法保存使用敏感信息类型的策略。</span><span class="sxs-lookup"><span data-stu-id="57ed8-262">Please note that the recommendedConfidence attribute is mandatory for each Entity ID in the Rule Package, if missing you won't be able to save policies that use the Sensitive Information Type.</span></span> 
  
## <a name="do-you-want-to-support-other-languages-in-the-ui-of-the-compliance-center-localizedstrings-element"></a><span data-ttu-id="57ed8-p146">是否要在合规中心的 UI 中支持其他语言？[LocalizedStrings 元素]</span><span class="sxs-lookup"><span data-stu-id="57ed8-p146">Do you want to support other languages in the UI of the Compliance center? [LocalizedStrings element]</span></span>

<span data-ttu-id="57ed8-p147">如果合规性团队使用 Microsoft 365 合规中心创建不同区域设置和不同语言的策略，你可以提供自定义敏感信息类型的名称和说明的本地化版本。这样，如果合规性团队在使用 Microsoft 365 时采用你所支持的语言，就会在 UI 中看到本地化名称。</span><span class="sxs-lookup"><span data-stu-id="57ed8-p147">If your compliance team uses the Microsoft 365 Compliance center to create polices policies in different locales and in different languages, you can provide localized versions of the name and description of your custom sensitive information type. When your compliance team uses Microsoft 365 in a language that you support, they'll see the localized name in the UI.</span></span>
  
![“实例计数”和“匹配准确度”选项](../media/11d0b51e-7c3f-4cc6-96d8-b29bcdae1aeb.png)
  
<span data-ttu-id="57ed8-p148">Rule 元素必须包含 LocalizedStrings 元素，因为其中包含引用自定义实体 GUID 的 Resource 元素。相应地，每个 Resource 元素都包含一个或多个 Name 和 Description 元素，这些元素使用 langcode 特性来提供特定语言的本地化字符串。</span><span class="sxs-lookup"><span data-stu-id="57ed8-p148">The Rules element must contain a LocalizedStrings element, which contains a Resource element that references the GUID of your custom entity. In turn, each Resource element contains one or more Name and Description elements that each use the langcode attribute to provide a localized string for a specific language.</span></span>
  
![显示 LocalizedStrings 元素内容的 XML 标记](../media/a96fc34a-b93d-498f-8b92-285b16a7bbe6.png)
  
<span data-ttu-id="57ed8-p149">请注意，本地化字符串只能用于指定自定义敏感信息类型在合规中心 UI 中的显示方式。不能使用本地化字符串来提供不同本地化版本的关键字列表或正则表达式。</span><span class="sxs-lookup"><span data-stu-id="57ed8-p149">Note that you use localized strings only for how your custom sensitive information type appears in the UI of the Compliance center. You can't use localized strings to provide different localized versions of a keyword list or regular expression.</span></span>
  
## <a name="other-rule-package-markup-rulepack-guid"></a><span data-ttu-id="57ed8-273">其他规则包标记 [RulePack GUID]</span><span class="sxs-lookup"><span data-stu-id="57ed8-273">Other rule package markup [RulePack GUID]</span></span>

<span data-ttu-id="57ed8-p150">最后，每个 RulePackage 的开头都有一些需要填写的常规信息。可以下面的标记为模板，将“...”占位符替换为你自己的信息。</span><span class="sxs-lookup"><span data-stu-id="57ed8-p150">Finally, the beginning of each RulePackage contains some general information that you need to fill in. You can use the following markup as a template and replace the ". . ." placeholders with your own info.</span></span>
  
<span data-ttu-id="57ed8-p151">最重要的是，必须为 RulePack 生成 GUID。在上文中，已为实体生成了 GUID；这是 RulePack 的第二个 GUID。虽然生成 GUID 的方法有很多，但可通过在 PowerShell 中键入 [guid]::NewGuid() 轻松完成。</span><span class="sxs-lookup"><span data-stu-id="57ed8-p151">Most importantly, you'll need to generate a GUID for the RulePack. Above, you generated a GUID for the entity; this is a second GUID for the RulePack. There are several ways to generate GUIDs, but you can do it easily in PowerShell by typing [guid]::NewGuid().</span></span>
  
<span data-ttu-id="57ed8-p152">Version 元素也很重要。当你首次上传规则包时，Microsoft 365 会记录版本号。稍后，如果更新规则包并上传新版本，请务必更新版本号，否则 Microsoft 365 便不会部署规则包。</span><span class="sxs-lookup"><span data-stu-id="57ed8-p152">The Version element is also important. When you upload your rule package for the first time, Microsoft 365 notes the version number. Later, if you update the rule package and upload a new version, make sure to update the version number or Microsoft 365 won't deploy the rule package.</span></span>
  
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

<span data-ttu-id="57ed8-285">完成后，RulePack 元素应如下所示。</span><span class="sxs-lookup"><span data-stu-id="57ed8-285">When complete, your RulePack element should look like this.</span></span>
  
![显示 RulePack 元素的 XML 标记](../media/fd0f31a7-c3ee-43cd-a71b-6a3813b21155.png)

## <a name="validators"></a><span data-ttu-id="57ed8-287">验证程序</span><span class="sxs-lookup"><span data-stu-id="57ed8-287">Validators</span></span>

<span data-ttu-id="57ed8-288">Microsoft 365公开常用 SIT 的函数处理器作为验证程序。</span><span class="sxs-lookup"><span data-stu-id="57ed8-288">Microsoft 365 exposes function processors for commonly used SITs as validators.</span></span> <span data-ttu-id="57ed8-289">以下是它们的列表。</span><span class="sxs-lookup"><span data-stu-id="57ed8-289">Here's a list of them.</span></span> 

### <a name="list-of-validators-currently-available"></a><span data-ttu-id="57ed8-290">当前可用的验证程序列表</span><span class="sxs-lookup"><span data-stu-id="57ed8-290">List of validators currently available</span></span>

- <span data-ttu-id="57ed8-291">Func_credit_card</span><span class="sxs-lookup"><span data-stu-id="57ed8-291">Func_credit_card</span></span>
- <span data-ttu-id="57ed8-292">Func_ssn</span><span class="sxs-lookup"><span data-stu-id="57ed8-292">Func_ssn</span></span>
- <span data-ttu-id="57ed8-293">Func_unformatted_ssn</span><span class="sxs-lookup"><span data-stu-id="57ed8-293">Func_unformatted_ssn</span></span>
- <span data-ttu-id="57ed8-294">Func_randomized_formatted_ssn</span><span class="sxs-lookup"><span data-stu-id="57ed8-294">Func_randomized_formatted_ssn</span></span>
- <span data-ttu-id="57ed8-295">Func_randomized_unformatted_ssn</span><span class="sxs-lookup"><span data-stu-id="57ed8-295">Func_randomized_unformatted_ssn</span></span>
- <span data-ttu-id="57ed8-296">Func_aba_routing</span><span class="sxs-lookup"><span data-stu-id="57ed8-296">Func_aba_routing</span></span>
- <span data-ttu-id="57ed8-297">Func_south_africa_identification_number</span><span class="sxs-lookup"><span data-stu-id="57ed8-297">Func_south_africa_identification_number</span></span>
- <span data-ttu-id="57ed8-298">Func_brazil_cpf</span><span class="sxs-lookup"><span data-stu-id="57ed8-298">Func_brazil_cpf</span></span>
- <span data-ttu-id="57ed8-299">Func_iban</span><span class="sxs-lookup"><span data-stu-id="57ed8-299">Func_iban</span></span>
- <span data-ttu-id="57ed8-300">Func_brazil_cnpj</span><span class="sxs-lookup"><span data-stu-id="57ed8-300">Func_brazil_cnpj</span></span>
- <span data-ttu-id="57ed8-301">Func_swedish_national_identifier</span><span class="sxs-lookup"><span data-stu-id="57ed8-301">Func_swedish_national_identifier</span></span>
- <span data-ttu-id="57ed8-302">Func_india_aadhaar</span><span class="sxs-lookup"><span data-stu-id="57ed8-302">Func_india_aadhaar</span></span>
- <span data-ttu-id="57ed8-303">Func_uk_nhs_number</span><span class="sxs-lookup"><span data-stu-id="57ed8-303">Func_uk_nhs_number</span></span>
- <span data-ttu-id="57ed8-304">Func_Turkish_National_Id</span><span class="sxs-lookup"><span data-stu-id="57ed8-304">Func_Turkish_National_Id</span></span>
- <span data-ttu-id="57ed8-305">Func_australian_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="57ed8-305">Func_australian_tax_file_number</span></span>
- <span data-ttu-id="57ed8-306">Func_usa_uk_passport</span><span class="sxs-lookup"><span data-stu-id="57ed8-306">Func_usa_uk_passport</span></span>
- <span data-ttu-id="57ed8-307">Func_canadian_sin</span><span class="sxs-lookup"><span data-stu-id="57ed8-307">Func_canadian_sin</span></span>
- <span data-ttu-id="57ed8-308">Func_formatted_itin</span><span class="sxs-lookup"><span data-stu-id="57ed8-308">Func_formatted_itin</span></span>
- <span data-ttu-id="57ed8-309">Func_unformatted_itin</span><span class="sxs-lookup"><span data-stu-id="57ed8-309">Func_unformatted_itin</span></span>
- <span data-ttu-id="57ed8-310">Func_dea_number_v2</span><span class="sxs-lookup"><span data-stu-id="57ed8-310">Func_dea_number_v2</span></span>
- <span data-ttu-id="57ed8-311">Func_dea_number</span><span class="sxs-lookup"><span data-stu-id="57ed8-311">Func_dea_number</span></span>
- <span data-ttu-id="57ed8-312">Func_japanese_my_number_personal</span><span class="sxs-lookup"><span data-stu-id="57ed8-312">Func_japanese_my_number_personal</span></span>
- <span data-ttu-id="57ed8-313">Func_japanese_my_number_corporate</span><span class="sxs-lookup"><span data-stu-id="57ed8-313">Func_japanese_my_number_corporate</span></span>

<span data-ttu-id="57ed8-314">这让你能够定义自己的正则表达式并验证它们。</span><span class="sxs-lookup"><span data-stu-id="57ed8-314">This gives you the ability to define your own regex and validate them.</span></span> <span data-ttu-id="57ed8-315">若要使用验证程序，请定义你自己的正则表达式，定义正则表达式时，请使用 validator 属性添加您所选择的函数处理器。</span><span class="sxs-lookup"><span data-stu-id="57ed8-315">To use validators, define your own regex and while defining the regex use the validator property to add the function processor of your choice.</span></span> <span data-ttu-id="57ed8-316">定义后，可以在 SIT 中使用此正则表达式。</span><span class="sxs-lookup"><span data-stu-id="57ed8-316">Once defined, you can use this regex in an SIT.</span></span> 

<span data-ttu-id="57ed8-317">在下面的示例中，正则表达式 - Regex_credit_card_AdditionalDelimiters定义为信用卡，然后使用信用卡的校验和函数将 Func_credit_card 用作验证程序进行验证。</span><span class="sxs-lookup"><span data-stu-id="57ed8-317">In the example below, a regular expression - Regex_credit_card_AdditionalDelimiters is defined for Credit card which is then validated using the checksum function for credit card by using Func_credit_card as a validator.</span></span>

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

<span data-ttu-id="57ed8-318">Microsoft 365两个通用验证程序</span><span class="sxs-lookup"><span data-stu-id="57ed8-318">Microsoft 365 provides two generic validators</span></span>

### <a name="checksum-validator"></a><span data-ttu-id="57ed8-319">校验和验证程序</span><span class="sxs-lookup"><span data-stu-id="57ed8-319">Checksum validator</span></span>

<span data-ttu-id="57ed8-320">本示例定义员工 ID 的校验和验证程序，以验证 EmployeeID 的正则表达式。</span><span class="sxs-lookup"><span data-stu-id="57ed8-320">In this example, a checksum validator for employee ID is defined to validate the regex for EmployeeID.</span></span>

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

### <a name="date-validator"></a><span data-ttu-id="57ed8-321">日期验证程序</span><span class="sxs-lookup"><span data-stu-id="57ed8-321">Date Validator</span></span>

<span data-ttu-id="57ed8-322">本示例为日期的正则表达式部分定义日期验证程序。</span><span class="sxs-lookup"><span data-stu-id="57ed8-322">In this example, a date validator is defined for a regex part of which is date.</span></span>

```xml
<Validators id="date_validator_1"> <Validator type="DateSimple"> <Param name="Pattern">DDMMYYYY</Param> <!—supported patterns DDMMYYYY, MMDDYYYY, YYYYDDMM, YYYYMMDD, DDMMYYYY, DDMMYY, MMDDYY, YYDDMM, YYMMDD --> </Validator> </Validators>
<Regex id="date_regex_1" validators="date_validator_1">\d{8}</Regex>
```
  
## <a name="changes-for-exchange-online"></a><span data-ttu-id="57ed8-323">针对 Exchange Online 的变化</span><span class="sxs-lookup"><span data-stu-id="57ed8-323">Changes for Exchange Online</span></span>

<span data-ttu-id="57ed8-p155">之前，你可能使用 Exchange Online PowerShell 来导入 DLP 的自定义敏感信息类型。而现在，自定义敏感信息类型可同时在 Exchange 管理中心和安全与合规中心使用。作为该项改进的一部分，你应使用合规中心 PowerShell 来导入自定义敏感信息类型 - 不可再从 Exchange PowerShell 中导入它们。自定义敏感信息类型将继续像之前一样发挥作用，但是，在合规中心内对自定义敏感信息类型所做更改可能最多 1 个小时后才会在 Exchange 管理中心内显示。</span><span class="sxs-lookup"><span data-stu-id="57ed8-p155">Previously, you might have used Exchange Online PowerShell to import your custom sensitive information types for DLP. Now your custom sensitive information types can be used in both the Exchange admin center and the Compliance center. As part of this improvement, you should use Compliance center PowerShell to import your custom sensitive information types — you can't import them from the Exchange PowerShell anymore. Your custom sensitive information types will continue to work just like before; however, it may take up to one hour for changes made to custom sensitive information types in the Compliance center to appear in the Exchange admin center.</span></span>
  
<span data-ttu-id="57ed8-328">请注意，在合规中心中，可以使用 **[New-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/new-dlpsensitiveinformationtyperulepackage)** cmdlet 上载规则包。</span><span class="sxs-lookup"><span data-stu-id="57ed8-328">Note that in the Compliance center, you use the **[New-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/new-dlpsensitiveinformationtyperulepackage)** cmdlet to upload a rule package.</span></span> <span data-ttu-id="57ed8-329">（以前，在 Exchange 管理中心中，使用的是 **ClassificationRuleCollection**\`cmdlet。）</span><span class="sxs-lookup"><span data-stu-id="57ed8-329">(Previously, in the Exchange admin center, you used the  **ClassificationRuleCollection**\` cmdlet.)</span></span> 
  
## <a name="upload-your-rule-package"></a><span data-ttu-id="57ed8-330">上传规则包</span><span class="sxs-lookup"><span data-stu-id="57ed8-330">Upload your rule package</span></span>

<span data-ttu-id="57ed8-331">若要上传规则包，请按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="57ed8-331">To upload your rule package, do the following steps:</span></span>
  
1. <span data-ttu-id="57ed8-332">将文件另存为采用 Unicode 编码的 .xml 文件。</span><span class="sxs-lookup"><span data-stu-id="57ed8-332">Save it as an .xml file with Unicode encoding.</span></span>
    
2. [<span data-ttu-id="57ed8-333">连接到合规中心 PowerShell</span><span class="sxs-lookup"><span data-stu-id="57ed8-333">Connect to Compliance center PowerShell</span></span>](/powershell/exchange/exchange-online-powershell)
    
3. <span data-ttu-id="57ed8-334">使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="57ed8-334">Use the following syntax:</span></span>

   ```powershell
   New-DlpSensitiveInformationTypeRulePackage -FileData (Get-Content -Path "PathToUnicodeXMLFile" -Encoding Byte -ReadCount 0)
   ```

   <span data-ttu-id="57ed8-335">本示例从 C:\My Documents 上传名为 MyNewRulePack.xml 的 Unicode XML 文件。</span><span class="sxs-lookup"><span data-stu-id="57ed8-335">This example uploads the Unicode XML file named MyNewRulePack.xml from C:\My Documents.</span></span>

   ```powershell
   New-DlpSensitiveInformationTypeRulePackage -FileData (Get-Content -Path "C:\My Documents\MyNewRulePack.xml" -Encoding Byte -ReadCount 0)
   ```

   <span data-ttu-id="57ed8-336">有关语法和参数的详细信息，请参阅 [New-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/new-dlpsensitiveinformationtyperulepackage)。</span><span class="sxs-lookup"><span data-stu-id="57ed8-336">For detailed syntax and parameter information, see [New-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/new-dlpsensitiveinformationtyperulepackage).</span></span>

   > [!NOTE]
   > <span data-ttu-id="57ed8-337">支持的规则包数量最多为10个，但每个包可以包含多个敏感信息类型的定义。</span><span class="sxs-lookup"><span data-stu-id="57ed8-337">The maximum number of rule packages supported is 10, but each package can contain the definition of multiple sensitive information types.</span></span>

4. <span data-ttu-id="57ed8-338">若要验证是否已成功新建敏感信息类型，请按以下任一步骤操作：</span><span class="sxs-lookup"><span data-stu-id="57ed8-338">To verify that you've successfully created a new sensitive information type, do any of the following steps:</span></span>

   - <span data-ttu-id="57ed8-339">运行 [Get-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/get-dlpsensitiveinformationtyperulepackage) cmdlet，验证新规则包是否已列出：</span><span class="sxs-lookup"><span data-stu-id="57ed8-339">Run the [Get-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/get-dlpsensitiveinformationtyperulepackage) cmdlet to verify the new rule package is listed:</span></span>

     ```powershell
     Get-DlpSensitiveInformationTypeRulePackage
     ``` 

   - <span data-ttu-id="57ed8-340">Run the [Get-DlpSensitiveInformationType](/powershell/module/exchange/get-dlpsensitiveinformationtype)，验证敏感信息类型是否已列出：</span><span class="sxs-lookup"><span data-stu-id="57ed8-340">Run the [Get-DlpSensitiveInformationType](/powershell/module/exchange/get-dlpsensitiveinformationtype) cmdlet to verify the sensitive information type is listed:</span></span>

     ```powershell
     Get-DlpSensitiveInformationType
     ``` 

     <span data-ttu-id="57ed8-341">对于自定义敏感信息类型，Publisher 属性值将不是 Microsoft Corporation。</span><span class="sxs-lookup"><span data-stu-id="57ed8-341">For custom sensitive information types, the Publisher property value will be something other than Microsoft Corporation.</span></span>

   - <span data-ttu-id="57ed8-342">将 \<Name\> 替换为敏感信息类型的 Name 值（例如，员工 ID），然后运行 [Get-DlpSensitiveInformationType](/powershell/module/exchange/get-dlpsensitiveinformationtype) cmdlet：</span><span class="sxs-lookup"><span data-stu-id="57ed8-342">Replace \<Name\> with the Name value of the sensitive information type (example: Employee ID) and run the [Get-DlpSensitiveInformationType](/powershell/module/exchange/get-dlpsensitiveinformationtype) cmdlet:</span></span>

     ```powershell
     Get-DlpSensitiveInformationType -Identity "<Name>"
     ```
    
## <a name="potential-validation-issues-to-be-aware-of"></a><span data-ttu-id="57ed8-343">要注意的潜在验证问题</span><span class="sxs-lookup"><span data-stu-id="57ed8-343">Potential validation issues to be aware of</span></span>

<span data-ttu-id="57ed8-p157">当你上传规则包 XML 文件时，系统会验证 XML，并检查是否有已知的错误模式和明显的性能问题。验证检查正则表达式时，需要检查其中是否有下面的一些已知问题：</span><span class="sxs-lookup"><span data-stu-id="57ed8-p157">When you upload your rule package XML file, the system validates the XML and checks for known bad patterns and obvious performance issues. Here are some known issues that the validation checks for — a regular expression:</span></span>
  
- <span data-ttu-id="57ed8-346">不得以匹配所有项的交替符“|”开头或结尾，因为这被视为空匹配。</span><span class="sxs-lookup"><span data-stu-id="57ed8-346">Cannot begin or end with alternator "|", which matches everything because it's considered an empty match.</span></span>
    
  <span data-ttu-id="57ed8-347">例如，“|a”或“b|”无法通过验证。</span><span class="sxs-lookup"><span data-stu-id="57ed8-347">For example, "|a" or "b|" will not pass validation.</span></span>
    
- <span data-ttu-id="57ed8-348">不得以“{0,m}”模式开头或结尾，它不具备功能性，只会削弱性能。</span><span class="sxs-lookup"><span data-stu-id="57ed8-348">Cannot begin or end with a ".{0,m}" pattern, which has no functional purpose and only impairs performance.</span></span>
    
  <span data-ttu-id="57ed8-349">例如，“.{0,50}ASDF”或“ASDF.{0,50}”无法通过验证。</span><span class="sxs-lookup"><span data-stu-id="57ed8-349">For example, ".{0,50}ASDF" or "ASDF.{0,50}" will not pass validation.</span></span>
    
- <span data-ttu-id="57ed8-350">组中既不得有“.{0,m}”或“.{1,m}”，也不得有“.\*”或“.+”。</span><span class="sxs-lookup"><span data-stu-id="57ed8-350">Cannot have ".{0,m}" or ".{1,m}" in groups, and cannot have ".\*" or ".+" in groups.</span></span>
    
  <span data-ttu-id="57ed8-351">例如，“(.{0,50000})”无法通过验证。</span><span class="sxs-lookup"><span data-stu-id="57ed8-351">For example, "(.{0,50000})" will not pass validation.</span></span>
    
- <span data-ttu-id="57ed8-352">组中不得有任何字符包含“{0,m}”或“{1,m}”重复符。</span><span class="sxs-lookup"><span data-stu-id="57ed8-352">Cannot have any character with "{0,m}" or "{1,m}" repeaters in groups.</span></span>
    
  <span data-ttu-id="57ed8-353">例如，“(a\*)”无法通过验证。</span><span class="sxs-lookup"><span data-stu-id="57ed8-353">For example, "(a\*)" will not pass validation.</span></span>
    
- <span data-ttu-id="57ed8-354">不得以“.{1,m}”开头或结尾；请改用“.”</span><span class="sxs-lookup"><span data-stu-id="57ed8-354">Cannot begin or end with ".{1,m}"; instead, use just "."</span></span>
    
  <span data-ttu-id="57ed8-355">例如，“.{1,m}asdf”无法通过验证；请改用“.asdf”。</span><span class="sxs-lookup"><span data-stu-id="57ed8-355">For example, ".{1,m}asdf" will not pass validation; instead, use just ".asdf".</span></span>
    
- <span data-ttu-id="57ed8-356">组中不得有无限重复符（如“\*”或“+”）。</span><span class="sxs-lookup"><span data-stu-id="57ed8-356">Cannot have an unbounded repeater (such as "\*" or "+") on a group.</span></span>
    
  <span data-ttu-id="57ed8-357">例如，“(xx)\*”和“(xx)+”无法通过验证。</span><span class="sxs-lookup"><span data-stu-id="57ed8-357">For example, "(xx)\*" and "(xx)+" will not pass validation.</span></span>
  
- <span data-ttu-id="57ed8-358">关键字最多可包含 50 个字符。</span><span class="sxs-lookup"><span data-stu-id="57ed8-358">Keywords have a maximum of 50 characters in Length.</span></span>  <span data-ttu-id="57ed8-359">如果组中的关键字超过此字符数，建议将术语组创建为[关键字字典](./create-a-keyword-dictionary.md)，并在 XML 结构中引用关键字字典的 GUID 作为文件中的 Match 或 idMatch 实体的一部分。</span><span class="sxs-lookup"><span data-stu-id="57ed8-359">If you have a keyword within a Group exceeding this, a suggested solution is to create the Group of terms as a [Keyword Dictionary](./create-a-keyword-dictionary.md) and reference the GUID of the Keyword Dictionary within the XML structure as part of the Entity for Match or idMatch in the file.</span></span>

- <span data-ttu-id="57ed8-360">每个自定义敏感信息类型最多可以包含 2048 个关键字。</span><span class="sxs-lookup"><span data-stu-id="57ed8-360">Each Custom Sensitive Information Type can have a maximum of 2048 keywords total.</span></span>

- <span data-ttu-id="57ed8-361">单个租户中关键字字典的最大大小为压缩的 1 MB。</span><span class="sxs-lookup"><span data-stu-id="57ed8-361">The maximum size of Keyword Dictionaries in a single tenant is 1 MB compressed.</span></span> <span data-ttu-id="57ed8-362">创建自定义敏感信息类型时，请尽情地根据需要多次引用同一词典。</span><span class="sxs-lookup"><span data-stu-id="57ed8-362">Reference the same dictionary as many times as necessary when creating custom sensitive information types.</span></span> <span data-ttu-id="57ed8-363">请先在敏感信息类型中创建自定义关键字列表，然后如果关键字列表中有超过 2048 个关键字或某个关键字长度超过 50 个字符时，请使用关键字词典。</span><span class="sxs-lookup"><span data-stu-id="57ed8-363">Start with creating custom keyword lists in the sensitive information type and use keyword dictionaries if you have more than 2048 keywords in a keyword list or a keyword is larger than 50 characters in length.</span></span>

- <span data-ttu-id="57ed8-364">租户中最多允许 50 种基于关键字字典的敏感信息类型。</span><span class="sxs-lookup"><span data-stu-id="57ed8-364">A maximum of 50 keyword dictionary based sensitive information types are allowed in a tenant.</span></span>

- <span data-ttu-id="57ed8-365">确保每个 Entity 元素都包含一个 recommendedConfidence 属性。</span><span class="sxs-lookup"><span data-stu-id="57ed8-365">Ensure each Entity element contains a recommendedConfidence attribute.</span></span>

- <span data-ttu-id="57ed8-366">使用 PowerShell Cmdlet 时，最多可返回约 1 MB 的反序列化数据。</span><span class="sxs-lookup"><span data-stu-id="57ed8-366">When using the PowerShell Cmdlet there is a maximum return size of the Deserialized Data of approximately 1 megabyte.</span></span>   <span data-ttu-id="57ed8-367">这会影响规则包 XML 文件的大小。</span><span class="sxs-lookup"><span data-stu-id="57ed8-367">This will affect the size of your rule pack XML file.</span></span> <span data-ttu-id="57ed8-368">将所上传文件的建议上限设置为 770 KB，以确保结果一致，处理时不会出错。</span><span class="sxs-lookup"><span data-stu-id="57ed8-368">Keep the uploaded file limited to a 770 kilobyte maximum as a suggested limit for consistent results without error when processing.</span></span>

- <span data-ttu-id="57ed8-369">XML 结构不需要格式设置字符，例如空格、制表符或回车符/行源条目。</span><span class="sxs-lookup"><span data-stu-id="57ed8-369">The XML structure does not require formatting characters such as spaces, tabs, or carriage return/linefeed entries.</span></span>  <span data-ttu-id="57ed8-370">在针对上传空间进行优化时，请注意这一点。</span><span class="sxs-lookup"><span data-stu-id="57ed8-370">Take note of this when optimizing for space on uploads.</span></span> <span data-ttu-id="57ed8-371">诸如 Microsoft Visual Code 等工具提供连接线功能来压缩 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="57ed8-371">Tools such as Microsoft Visual Code provide join line features to compact the XML file.</span></span>
    
<span data-ttu-id="57ed8-372">如果自定义敏感信息类型存在可能会影响性能的问题，便无法上传，且可能会导致以下错误消息之一出现：</span><span class="sxs-lookup"><span data-stu-id="57ed8-372">If a custom sensitive information type contains an issue that may affect performance, it won't be uploaded and you may see one of these error messages:</span></span>
  
- <span data-ttu-id="57ed8-373">**泛型限定符匹配的内容量超过预期(例如，“+”、“\*”)**</span><span class="sxs-lookup"><span data-stu-id="57ed8-373">**Generic quantifiers which match more content than expected (e.g., '+', '\*')**</span></span>
    
- <span data-ttu-id="57ed8-374">**环视断言**</span><span class="sxs-lookup"><span data-stu-id="57ed8-374">**Lookaround assertions**</span></span>
    
- <span data-ttu-id="57ed8-375">**与常规限定符一同使用的分组复杂**</span><span class="sxs-lookup"><span data-stu-id="57ed8-375">**Complex grouping in conjunction with general quantifiers**</span></span>
    
## <a name="recrawl-your-content-to-identify-the-sensitive-information"></a><span data-ttu-id="57ed8-376">对内容重新爬网以标识敏感信息</span><span class="sxs-lookup"><span data-stu-id="57ed8-376">Recrawl your content to identify the sensitive information</span></span>

<span data-ttu-id="57ed8-p162">Microsoft 365 使用搜索爬网程序对网站内容中的敏感信息进行标识和分类。SharePoint Online 和 OneDrive for Business 网站中的内容会在更新后自动重新爬网。但若要标识所有现有内容中新的自定义类型敏感信息，必须对相应内容重新爬网。</span><span class="sxs-lookup"><span data-stu-id="57ed8-p162">Microsoft 365 uses the search crawler to identify and classify sensitive information in site content. Content in SharePoint Online and OneDrive for Business sites is recrawled automatically whenever it's updated. But to identify your new custom type of sensitive information in all existing content, that content must be recrawled.</span></span>
  
<span data-ttu-id="57ed8-380">在 Microsoft 365 中，无法手动请求对整个租户进行重新爬网，但可以对网站集、列表或库这样做。请参阅[手动请求对网站、库或列表进行爬网和重新编制索引](/sharepoint/crawl-site-content)。</span><span class="sxs-lookup"><span data-stu-id="57ed8-380">In Microsoft 365, you can't manually request a recrawl of an entire tenant, but you can do this for a site collection, list, or library — see [Manually request crawling and re-indexing of a site, a library or a list](/sharepoint/crawl-site-content).</span></span>
  
## <a name="reference-rule-package-xml-schema-definition"></a><span data-ttu-id="57ed8-381">参考：规则包 XML 架构定义</span><span class="sxs-lookup"><span data-stu-id="57ed8-381">Reference: Rule package XML schema definition</span></span>

<span data-ttu-id="57ed8-382">可复制此标记，并将它另存为 XSD 文件，以用来验证规则包 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="57ed8-382">You can copy this markup, save it as an XSD file, and use it to validate your rule package XML file.</span></span>
  
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

## <a name="more-information"></a><span data-ttu-id="57ed8-383">更多信息</span><span class="sxs-lookup"><span data-stu-id="57ed8-383">More information</span></span>

- [<span data-ttu-id="57ed8-384">了解数据丢失防护</span><span class="sxs-lookup"><span data-stu-id="57ed8-384">Learn about data loss prevention</span></span>](dlp-learn-about-dlp.md)

- [<span data-ttu-id="57ed8-385">敏感信息类型属性定义</span><span class="sxs-lookup"><span data-stu-id="57ed8-385">Sensitive information type entity definitions</span></span>](sensitive-information-type-entity-definitions.md)

- [<span data-ttu-id="57ed8-386">DLP 函数查找什么</span><span class="sxs-lookup"><span data-stu-id="57ed8-386">What the DLP functions look for</span></span>](what-the-dlp-functions-look-for.md)
