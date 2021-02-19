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
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 了解如何在合规中心中创建并导入策略的自定义敏感信息类型。
ms.openlocfilehash: e3735458f3259478a7df36bb3c6ddbc4a5fed719
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/18/2021
ms.locfileid: "50288499"
---
# <a name="create-a-custom-sensitive-information-type-using-powershell"></a><span data-ttu-id="d8321-103">使用 PowerShell 创建自定义敏感信息类型</span><span class="sxs-lookup"><span data-stu-id="d8321-103">Create a custom sensitive information type using PowerShell</span></span>

<span data-ttu-id="d8321-104">本主题介绍如何使用 PowerShell 创建定义自己的自定义 [敏感信息类型](sensitive-information-type-entity-definitions.md)的 XML *规则包* 文件。</span><span class="sxs-lookup"><span data-stu-id="d8321-104">This topic shows you how to use PowerShell to create an XML *rule package* file that defines your own custom [sensitive information types](sensitive-information-type-entity-definitions.md).</span></span> <span data-ttu-id="d8321-105">需要了解如何创建正则表达式。</span><span class="sxs-lookup"><span data-stu-id="d8321-105">You need to know how to create a regular expression.</span></span> <span data-ttu-id="d8321-106">为提供示例，本主题创建识别员工 ID 的自定义敏感信息类型。</span><span class="sxs-lookup"><span data-stu-id="d8321-106">As an example, this topic creates a custom sensitive information type that identifies an employee ID.</span></span> <span data-ttu-id="d8321-107">可以此示例 XML 为起点，创建自己的 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="d8321-107">You can use this example XML as a starting point for your own XML file.</span></span> <span data-ttu-id="d8321-108">如果不熟悉敏感信息类型，请参阅[了解敏感信息类型](sensitive-information-type-learn-about.md)。</span><span class="sxs-lookup"><span data-stu-id="d8321-108">If you are new to sensitive information types, see [Learn about sensitive information types](sensitive-information-type-learn-about.md).</span></span>

<span data-ttu-id="d8321-109">创建正常可用的 XML 文件后，可使用 Microsoft 365 PowerShell 将其上传到 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="d8321-109">After you've created a well-formed XML file, you can upload it to Microsoft 365 by using Microsoft 365 PowerShell.</span></span> <span data-ttu-id="d8321-110">然后便可在策略中使用自定义敏感信息类型，测试其是否能按需检测敏感信息。</span><span class="sxs-lookup"><span data-stu-id="d8321-110">Then you're ready to use your custom sensitive information type in your policies and test that it's detecting the sensitive information as you intended.</span></span>

> [!NOTE]
> <span data-ttu-id="d8321-111">如果不需要 PowerShell 提供的细化控制，可以在合规中心中创建自定义敏感信息类型。</span><span class="sxs-lookup"><span data-stu-id="d8321-111">If you don't need the fine grained control that PowerShell provides, you can create custom sensitive information types in the Compliance center.</span></span> <span data-ttu-id="d8321-112">有关详细信息，请参阅[创建自定义敏感信息类型](create-a-custom-sensitive-information-type.md)。</span><span class="sxs-lookup"><span data-stu-id="d8321-112">For more information, see [Create a custom sensitive information type](create-a-custom-sensitive-information-type.md).</span></span>

## <a name="important-disclaimer"></a><span data-ttu-id="d8321-113">重要免责声明</span><span class="sxs-lookup"><span data-stu-id="d8321-113">Important disclaimer</span></span>

<span data-ttu-id="d8321-p104">由于客户环境和内容匹配要求的多样性，Microsoft 支持部门无法帮助提供自定义内容匹配定义（例如，定义自定义分类或正则表达式（也称为“RegEx”）模式）。对于自定义内容匹配的开发、测试和调试，Microsoft 365 客户将需要依赖于内部 IT 资源，或使用 Microsoft 咨询服务 (MCS) 等外部咨询资源。支持工程师可提供针对该功能的有限支持，但无法保证任何自定义内容匹配开发都能满足客户的要求或义务。作为可提供的支持类型的示例，可以提供示例正则表达式模式以供测试使用。或者，支持人员可以帮助对现有 RegEx 模式（单个特定内容示例未按预期触发）进行故障排除。</span><span class="sxs-lookup"><span data-stu-id="d8321-p104">Due to the variances in customer environments and content match requirements, Microsoft Support cannot assist in providing custom content-matching definitions; e.g., defining custom classifications or regular expression (also known as RegEx) patterns. For custom content-matching development, testing, and debugging, Microsoft 365 customers will need to rely upon internal IT resources, or use an external consulting resource such as Microsoft Consulting Services (MCS). Support engineers can provide limited support for the feature, but cannot provide assurances that any custom content-matching development will fulfill the customer's requirements or obligations.  As an example of the type of support that can be provided, sample regular expression patterns may be provided for testing purposes. Or, support can assist with troubleshooting an existing RegEx pattern which is not triggering as expected with a single specific content example.</span></span>

<span data-ttu-id="d8321-119">请参阅本主题中的[要注意的潜在验证问题](#potential-validation-issues-to-be-aware-of)。</span><span class="sxs-lookup"><span data-stu-id="d8321-119">See [Potential validation issues to be aware of](#potential-validation-issues-to-be-aware-of) in this topic.</span></span>

<span data-ttu-id="d8321-120">有关用于处理文本的 Boost.RegEx（以前称为 RegEx++）引擎的详细信息，请参阅 [Boost.Regex 5.1.3](https://www.boost.org/doc/libs/1_68_0/libs/regex/doc/html/)。</span><span class="sxs-lookup"><span data-stu-id="d8321-120">For more information about the Boost.RegEx (formerly known as RegEx++) engine that's used for processing the text, see [Boost.Regex 5.1.3](https://www.boost.org/doc/libs/1_68_0/libs/regex/doc/html/).</span></span>

## <a name="sample-xml-of-a-rule-package"></a><span data-ttu-id="d8321-121">规则包 XML 示例</span><span class="sxs-lookup"><span data-stu-id="d8321-121">Sample XML of a rule package</span></span>

<span data-ttu-id="d8321-p105">下面就是本主题将创建的规则包 XML 示例。下面各部分介绍了元素和特性。</span><span class="sxs-lookup"><span data-stu-id="d8321-p105">Here's the sample XML of the rule package that we'll create in this topic. Elements and attributes are explained in the sections below.</span></span>
  
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
    <Entity id="E1CC861E-3FE9-4A58-82DF-4BD259EAB378" patternsProximity="300" recommendedConfidence="70">
        <Pattern confidenceLevel="60">
            <IdMatch idRef="Regex_employee_id"/>
        </Pattern>
        <Pattern confidenceLevel="70">
            <IdMatch idRef="Regex_employee_id"/>
            <Match idRef="Func_us_date"/>
        </Pattern>
        <Pattern confidenceLevel="80">
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

## <a name="what-are-your-key-requirements-rule-entity-pattern-elements"></a><span data-ttu-id="d8321-p106">关键要求是什么？[Rule、Entity、Pattern 元素]</span><span class="sxs-lookup"><span data-stu-id="d8321-p106">What are your key requirements? [Rule, Entity, Pattern elements]</span></span>

<span data-ttu-id="d8321-126">开始前，有必要了解规则 XML 架构的基本结构，以及如何使用这种结构来定义用于标识适当内容的自定义敏感信息类型。</span><span class="sxs-lookup"><span data-stu-id="d8321-126">Before you get started, it's helpful to understand the basic structure of the XML schema for a rule, and how you can use this structure to define your custom sensitive information type so that it will identify the right content.</span></span>
  
<span data-ttu-id="d8321-127">一个规则定义一个或多个实体（敏感信息类型），且每个实体定义一个或多个模式。</span><span class="sxs-lookup"><span data-stu-id="d8321-127">A rule defines one or more entities (sensitive information types), and each entity defines one or more patterns.</span></span> <span data-ttu-id="d8321-128">模式是原则在评估电子邮件和文档等内容时查找的对象。</span><span class="sxs-lookup"><span data-stu-id="d8321-128">A pattern is what a policy looks for when it evaluates content such as email and documents.</span></span>

<span data-ttu-id="d8321-129">在本主题中，XML 标记使用规则来表示定义实体的模式，该实体也称为敏感信息类型。</span><span class="sxs-lookup"><span data-stu-id="d8321-129">In this topic, the XML markup uses rule to mean the patterns that define an entity, also known as a sensitive information type.</span></span> <span data-ttu-id="d8321-130">所以在本主题中，出现规则时，请将其视为实体或敏感信息类型，而非条件和操作。</span><span class="sxs-lookup"><span data-stu-id="d8321-130">So in this topic, when you see rule, think entity or sensitive information type, not conditions and actions.</span></span>
  
### <a name="simplest-scenario-entity-with-one-pattern"></a><span data-ttu-id="d8321-131">最简单方案：包含一个模式的实体</span><span class="sxs-lookup"><span data-stu-id="d8321-131">Simplest scenario: entity with one pattern</span></span>

<span data-ttu-id="d8321-132">下面是最简单的方案。</span><span class="sxs-lookup"><span data-stu-id="d8321-132">Here's the simplest scenario.</span></span> <span data-ttu-id="d8321-133">希望策略识别包含组织员工 ID 的内容，该 ID 由九位数字组成。</span><span class="sxs-lookup"><span data-stu-id="d8321-133">You want your policy to identify content that contains your organization's employee ID, which is formatted as a nine-digit number.</span></span> <span data-ttu-id="d8321-134">此时，模式是指规则中包含的可识别九位数字的正则表达式。</span><span class="sxs-lookup"><span data-stu-id="d8321-134">So the pattern refers to a regular expression contained in the rule that identifies nine-digit numbers.</span></span> <span data-ttu-id="d8321-135">包含九位数字的任何内容都满足该模式。</span><span class="sxs-lookup"><span data-stu-id="d8321-135">Any content containing a nine-digit number satisfies the pattern.</span></span>
  
![包含一个模式的实体的关系图](../media/4cc82dcf-068f-43ff-99b2-bac3892e9819.png)
  
<span data-ttu-id="d8321-137">虽然简单，但此模式可能会标识许多误报内容，因为包含任何九位数的匹配内容不一定是员工 ID。</span><span class="sxs-lookup"><span data-stu-id="d8321-137">However, while simple, this pattern may identify many false positives by matching content that contains any nine-digit number that is not necessarily an employee ID.</span></span>
  
### <a name="more-common-scenario-entity-with-multiple-patterns"></a><span data-ttu-id="d8321-138">更常见方案：包含多个模式的实体</span><span class="sxs-lookup"><span data-stu-id="d8321-138">More common scenario: entity with multiple patterns</span></span>

<span data-ttu-id="d8321-139">因此，更常见的做法是使用多个模式定义实体。这样，除了实体（如九位数）外，这些模式还可标识证据（如关键字或日期）。</span><span class="sxs-lookup"><span data-stu-id="d8321-139">For this reason, it's more common to define an entity by using more than one pattern, where the patterns identify supporting evidence (such as a keyword or date) in addition to the entity (such as a nine-digit number).</span></span>
  
<span data-ttu-id="d8321-140">例如，若要更有胜算地标识包含员工 ID 的内容，除了九位数外，还可以定义另一种模式来标识聘用日期，并再定义一种模式来标识聘用日期和关键字（如“员工 ID”）。</span><span class="sxs-lookup"><span data-stu-id="d8321-140">For example, to increase the likelihood of identifying content that contains an employee ID, you can define another pattern that also identifies a hire date, and define yet another pattern that identifies both a hire date and a keyword (such as "employee ID"), in addition to the nine-digit number.</span></span>
  
![包含多个模式的实体的关系图](../media/c8dc2c9d-00c6-4ebc-889a-53b41a90024a.png)
  
<span data-ttu-id="d8321-142">对于此结构，请务必注意以下几点：</span><span class="sxs-lookup"><span data-stu-id="d8321-142">Note a couple of important aspects of this structure:</span></span>
  
- <span data-ttu-id="d8321-143">需要更多证据的模式具有更高的可信度级别。</span><span class="sxs-lookup"><span data-stu-id="d8321-143">Patterns that require more evidence have a higher confidence level.</span></span> <span data-ttu-id="d8321-144">这一点十分有用，因为稍后在策略中使用此敏感信息类型时，可仅通过较高可信度级别的匹配来使用限制性更高的操作（如阻止内容）；通过较低可信度级别的匹配来使用限制性较低的操作（如发送通知）。</span><span class="sxs-lookup"><span data-stu-id="d8321-144">This is useful because when you later use this sensitive information type in a policy, you can use more restrictive actions (such as block content) with only the higher-confidence matches, and you can use less restrictive actions (such as send notification) with the lower-confidence matches.</span></span>

- <span data-ttu-id="d8321-p111">支持元素 IdMatch 和 Match 引用的正则表达式和关键字实际上是 Rule 元素（而不是 Pattern 元素）的子级。这些支持元素是由 Pattern 引用，但包含在 Rule 中。也就是说，单个定义的支持元素（如正则表达式或关键字列表）可被多个实体和模式引用。</span><span class="sxs-lookup"><span data-stu-id="d8321-p111">The supporting IdMatch and Match elements reference regexes and keywords that are actually children of the Rule element, not the Pattern. These supporting elements are referenced by the Pattern but included in the Rule. This means that a single definition of a supporting element, like a regular expression or a keyword list, can be referenced by multiple entities and patterns.</span></span>

## <a name="what-entity-do-you-need-to-identify-entity-element-id-attribute"></a><span data-ttu-id="d8321-p112">需要标识什么实体？[Entity 元素，id 特性]</span><span class="sxs-lookup"><span data-stu-id="d8321-p112">What entity do you need to identify? [Entity element, id attribute]</span></span>

<span data-ttu-id="d8321-p113">实体是包含明确定义的模式的敏感信息类型，如信用卡号。每个实体都有一个唯一 GUID 作为自己的 ID。</span><span class="sxs-lookup"><span data-stu-id="d8321-p113">An entity is a sensitive information type, such as a credit card number, that has a well-defined pattern. Each entity has a unique GUID as its ID.</span></span>
  
### <a name="name-the-entity-and-generate-its-guid"></a><span data-ttu-id="d8321-152">命名实体并生成 GUID</span><span class="sxs-lookup"><span data-stu-id="d8321-152">Name the entity and generate its GUID</span></span>

1. <span data-ttu-id="d8321-153">在选择的 XML 编辑器中，添加规则和实体元素。</span><span class="sxs-lookup"><span data-stu-id="d8321-153">In your XML editor of choice, add the Rules and Entity elements.</span></span>
2. <span data-ttu-id="d8321-154">添加一个包含自定义实体名称的注释 - 在本示例中为员工 ID。</span><span class="sxs-lookup"><span data-stu-id="d8321-154">Add a comment that contains the name of your custom entity — in this example, Employee ID.</span></span> <span data-ttu-id="d8321-155">稍后将实体名称添加到本地化的字符串部分，创建策略时，会在 UI 中显示该名称。</span><span class="sxs-lookup"><span data-stu-id="d8321-155">Later, you'll add the entity name to the localized strings section, and that name is what appears in the UI when you create a policy.</span></span>
3. <span data-ttu-id="d8321-156">生成实体的 GUID。</span><span class="sxs-lookup"><span data-stu-id="d8321-156">Generate a GUID for your entity.</span></span> <span data-ttu-id="d8321-157">有几种方法可生成 GUID，可在 PowerShell 中通过键入 **[guid]::NewGuid()** 轻松生成。</span><span class="sxs-lookup"><span data-stu-id="d8321-157">There are several ways to generate GUIDs, but you can do it easily in PowerShell by typing **[guid]::NewGuid()**.</span></span> <span data-ttu-id="d8321-158">稍后还要将实体 GUID 添加到本地化的字符串部分。</span><span class="sxs-lookup"><span data-stu-id="d8321-158">Later, you'll also add the entity GUID to the localized strings section.</span></span>
  
![显示 Rule 和 Entity 元素的 XML 标记](../media/c46c0209-0947-44e0-ac3a-8fd5209a81aa.png)
  
## <a name="what-pattern-do-you-want-to-match-pattern-element-idmatch-element-regex-element"></a><span data-ttu-id="d8321-p116">要匹配什么模式？[Pattern 元素、IdMatch 元素、Regex 元素]</span><span class="sxs-lookup"><span data-stu-id="d8321-p116">What pattern do you want to match? [Pattern element, IdMatch element, Regex element]</span></span>

<span data-ttu-id="d8321-p117">模式包含敏感信息类型要查找的内容列表。其中可能包括正则表达式、关键字和内置函数（用于执行任务，如运行正则表达式以查找日期或地址）。敏感信息类型可包含多个具有唯一可信度的模式。</span><span class="sxs-lookup"><span data-stu-id="d8321-p117">The pattern contains the list of what the sensitive information type is looking for. This can include regexes, keywords, and built-in functions (which perform tasks like running regexes to find dates or addresses). Sensitive information types can have multiple patterns with unique confidences.</span></span>
  
<span data-ttu-id="d8321-p118">以下所有模式的共同点是，全都引用同一个正则表达式，以查找两边是空格 (\s) ... (\s) 的九位数 (\d{9})。此正则表达式由 IdMatch 元素引用，同时也是所有查找“员工 ID”实体的模式的通用要求。IdMatch 是模式尝试匹配的标识符，如员工 ID、信用卡号或身份证号。每个 Pattern 元素只能有一个 IdMatch 元素。</span><span class="sxs-lookup"><span data-stu-id="d8321-p118">What all of the below patterns have in common is that they all reference the same regular expression, which looks for a nine-digit number (\d{9}) surrounded by white space (\s) … (\s). This regular expression is referenced by the IdMatch element and is the common requirement for all patterns that look for the Employee ID entity. IdMatch is the identifier that the pattern is to trying to match, such as Employee ID or credit card number or social security number. A Pattern element must have exactly one IdMatch element.</span></span>
  
![显示引用一个 Regex 元素的多个 Pattern 元素的 XML 标记](../media/8f3f497b-3b8b-4bad-9c6a-d9abf0520854.png)
  
<span data-ttu-id="d8321-171">在满足条件的情况下，模式返回一个计数和可信度级别，可用于策略中的条件。</span><span class="sxs-lookup"><span data-stu-id="d8321-171">When satisfied, a pattern returns a count and confidence level, which you can use in the conditions in your policy.</span></span> <span data-ttu-id="d8321-172">将检测敏感信息类型的条件添加到策略时，可编辑计数和可信度级别，如以下所示。</span><span class="sxs-lookup"><span data-stu-id="d8321-172">When you add a condition for detecting a sensitive information type to a policy, you can edit the count and confidence level as shown here.</span></span> <span data-ttu-id="d8321-173">本主题稍后会介绍可信度级别（也称为匹配准确度）。</span><span class="sxs-lookup"><span data-stu-id="d8321-173">Confidence level (also called match accuracy) is explained later in this topic.</span></span>
  
![“实例计数”和“匹配准确度”选项](../media/11d0b51e-7c3f-4cc6-96d8-b29bcdae1aeb.png)
  
<span data-ttu-id="d8321-p120">创建正则表达式时，请注意一些潜在问题。例如，如果编写并上传的正则表达式标识过多内容，这可能会影响性能。若要详细了解这些潜在问题，请参阅后面的[要注意的潜在验证问题](#potential-validation-issues-to-be-aware-of)部分。</span><span class="sxs-lookup"><span data-stu-id="d8321-p120">When you create your regular expression, keep in mind that there are potential issues to be aware of. For example, if you write and upload a regex that identifies too much content, this can impact performance. To learn more about these potential issues, see the later section [Potential validation issues to be aware of](#potential-validation-issues-to-be-aware-of).</span></span>
  
## <a name="do-you-want-to-require-additional-evidence-match-element-mincount-attribute"></a><span data-ttu-id="d8321-p121">是否需要其他证据？[Match 元素、minCount 特性]</span><span class="sxs-lookup"><span data-stu-id="d8321-p121">Do you want to require additional evidence? [Match element, minCount attribute]</span></span>

<span data-ttu-id="d8321-180">除了 IdMatch 外，模式还可以使用 Match 元素来要求发现其他证据，如关键字、正则表达式、日期或地址。</span><span class="sxs-lookup"><span data-stu-id="d8321-180">In addition to the IdMatch, a pattern can use the Match element to require additional supporting evidence, such as a keyword, regex, date, or address.</span></span>
  
<span data-ttu-id="d8321-p122">一个 Pattern 可包含多个 Match 元素；可以直接将 Match 元素添加到 Pattern 元素中，也可以使用 Any 元素合并 Match 元素。Match 元素通过隐式 AND 运算符进行联接；必须符合所有 Match 元素，才算与模式匹配。可使用 Any 元素引入 AND 或 OR 运算符（有关详细信息，请参阅后面的部分）。</span><span class="sxs-lookup"><span data-stu-id="d8321-p122">A Pattern can include multiple Match elements; they can be included directly in the Pattern element or combined by using the Any element. Match elements are joined by an implicit AND operator; all Match elements must be satisfied for the pattern to be matched. You can use the Any element to introduce AND or OR operators (more on that in a later section).</span></span>
  
<span data-ttu-id="d8321-p123">可选的 minCount 特性可用于指定，必须为每个 Match 元素找到多少个匹配实例。例如，可指定至少必须找到关键字列表中的两个关键字时，才算符合模式。</span><span class="sxs-lookup"><span data-stu-id="d8321-p123">You can use the optional minCount attribute to specify how many instances of a match need to be found for each of the Match elements. For example, you can specify that a pattern is satisfied only when at least two keywords from a keyword list are found.</span></span>
  
![显示包含 minCount 特性的 Match 元素的 XML 标记](../media/607f6b5e-2c7d-43a5-a131-a649f122e15a.png)
  
### <a name="keywords-keyword-group-and-term-elements-matchstyle-and-casesensitive-attributes"></a><span data-ttu-id="d8321-187">关键字 [Keyword、Group 和 Term 元素，matchStyle 和 caseSensitive 特性]</span><span class="sxs-lookup"><span data-stu-id="d8321-187">Keywords [Keyword, Group, and Term elements, matchStyle and caseSensitive attributes]</span></span>

<span data-ttu-id="d8321-p124">在识别员工 ID 等敏感信息时，通常希望要求将关键字作为补强证据。例如，除匹配九位数字外，还可能希望查找“卡”、“徽章”或“ID”等字眼。为此，可使用 Keyword 元素。Keyword 元素具有一个 ID 属性，可由多个模式或实体中的多个 Match 元素引用。</span><span class="sxs-lookup"><span data-stu-id="d8321-p124">When you identify sensitive information, like an employee ID, you often want to require keywords as corroborative evidence. For example, in addition to matching a nine-digit number, you may want to look for words like "card", "badge", or "ID". To do this, you use the Keyword element. The Keyword element has an ID attribute that can be referenced by multiple Match elements in multiple patterns or entities.</span></span>
  
<span data-ttu-id="d8321-p125">关键字以 Term 元素列表的形式包含在 Group 元素中。Group 元素包含有以下两个可取值的 matchStyle 特性：</span><span class="sxs-lookup"><span data-stu-id="d8321-p125">Keywords are included as a list of Term elements in a Group element. The Group element has a matchStyle attribute with two possible values:</span></span>
  
- <span data-ttu-id="d8321-p126">**matchStyle="word"**：标识两边是空格或其他分隔符的整个字词的字词匹配。应始终使用 word，除非需要匹配部分字词或亚洲语言字词。</span><span class="sxs-lookup"><span data-stu-id="d8321-p126">**matchStyle="word"** Word match identifies whole words surrounded by white space or other delimiters. You should always use word unless you need to match parts of words or match words in Asian languages.</span></span> 
    
- <span data-ttu-id="d8321-p127">**matchStyle="string"**：标识无论两边是什么的字符串的字符串匹配。例如，“id”匹配“bid”和“idea”。仅在需要匹配亚洲语言字词或关键字可能是其他字符串的一部分时，才使用 string。</span><span class="sxs-lookup"><span data-stu-id="d8321-p127">**matchStyle="string"** String match identifies strings no matter what they're surrounded by. For example, "id" will match "bid" and "idea". Use string only when you need to match Asian words or if your keyword may be included as part of other strings.</span></span> 
    
<span data-ttu-id="d8321-199">最后，可使用 Term 元素的 caseSensitive 特性，以指定内容必须与关键字完全匹配，包括字母大小写。</span><span class="sxs-lookup"><span data-stu-id="d8321-199">Finally, you can use the caseSensitive attribute of the Term element to specify that the content must match the keyword exactly, including lower- and upper-case letters.</span></span>
  
![显示引用关键字的 Match 元素的 XML 标记](../media/e729ba27-dec6-46f4-9242-584c6c12fd85.png)
  
### <a name="regular-expressions-regex-element"></a><span data-ttu-id="d8321-201">正则表达式 [Regex 元素]</span><span class="sxs-lookup"><span data-stu-id="d8321-201">Regular expressions [Regex element]</span></span>

<span data-ttu-id="d8321-p128">在此示例中，员工 ID 实体已使用 IdMatch 元素引用模式（由空格包围的九位数字）的正则表达式。此外，模式还可使用 Match 元素再引用一个 Regex 元素，以识别补强证据，例如格式为美国邮政编码格式的五位或九位数字。</span><span class="sxs-lookup"><span data-stu-id="d8321-p128">In this example, the employee ID entity already uses the IdMatch element to reference a regex for the pattern — a nine-digit number surrounded by whitespace. In addition, a pattern can use a Match element to reference an additional Regex element to identify corroborative evidence, such as a five- or nine-digit number in the format of a US zip code.</span></span>
  
### <a name="additional-patterns-such-as-dates-or-addresses-built-in-functions"></a><span data-ttu-id="d8321-204">日期或地址等其他模式 [内置函数]</span><span class="sxs-lookup"><span data-stu-id="d8321-204">Additional patterns such as dates or addresses [built-in functions]</span></span>

<span data-ttu-id="d8321-205">除内置的敏感信息类型外，敏感信息类型还可使用内置函数，可识别美国日期、欧洲日期、到期日或美国地址等补强证据。</span><span class="sxs-lookup"><span data-stu-id="d8321-205">In addition to the built-in sensitive information types, sensitive information types can also use built-in functions that can identify corroborative evidence such as a US date, EU date, expiration date, or US address.</span></span> <span data-ttu-id="d8321-206">Microsoft 365 不支持上传自己的自定义函数，但创建自定义敏感信息类型时，实体可引用内置函数。</span><span class="sxs-lookup"><span data-stu-id="d8321-206">Microsoft 365 does not support uploading your own custom functions, but when you create a custom sensitive information type, your entity can reference the built-in functions.</span></span>
  
<span data-ttu-id="d8321-207">例如，由于员工 ID 徽章中有聘用日期，因此这个自定义实体可使用内置函数 `Func_us_date` 标识采用美国通用格式的日期。</span><span class="sxs-lookup"><span data-stu-id="d8321-207">For example, an employee ID badge has a hire date on it, so this custom entity can use the built-in function  `Func_us_date` to identify a date in the format commonly used in the US.</span></span> 
  
<span data-ttu-id="d8321-208">有关详细信息，请参阅 [DLP 函数查找什么](what-the-dlp-functions-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="d8321-208">For more information, see [What the DLP functions look for](what-the-dlp-functions-look-for.md).</span></span>
  
![显示引用内置函数的 Match 元素的 XML 标记](../media/dac6eae3-9c52-4537-b984-f9f127cc9c33.png)
  
## <a name="different-combinations-of-evidence-any-element-minmatches-and-maxmatches-attributes"></a><span data-ttu-id="d8321-210">不同证据组合 [Any 元素、minMatches 和 maxMatches 特性]</span><span class="sxs-lookup"><span data-stu-id="d8321-210">Different combinations of evidence [Any element, minMatches and maxMatches attributes]</span></span>

<span data-ttu-id="d8321-p130">在 Pattern 元素中，所有 IdMatch 和 Match 元素均通过隐式 AND 运算符进行联接。也就是说，必须符合所有 IdMatch 和 Match 元素，才算符合模式。不过，可使用 Any 元素对 Match 元素进行分组，从而创建更灵活的匹配逻辑。例如，可使用 Any 元素匹配所有或确切的一部分 Match 子元素，或不匹配任何 Match 子元素。</span><span class="sxs-lookup"><span data-stu-id="d8321-p130">In a Pattern element, all IdMatch and Match elements are joined by an implicit AND operator — all of the matches must be satisfied before the pattern can be satisfied. However, you can create more flexible matching logic by using the Any element to group Match elements. For example, you can use the Any element to match all, none, or an exact subset of its children Match elements.</span></span>
  
<span data-ttu-id="d8321-p131">Any 元素有可选的 minMatches 和 maxMatches 特性，可用于定义必须符合多少个 Match 子元素才算与模式匹配。请注意，这些特性定义的是必须符合的 Match 元素数量，而不是为与模式匹配而找到的证据实例数。若要定义为特定匹配找到的最小实例数（如列表中的两个关键字），请使用 Match 元素的 minCount 特性（见上文）。</span><span class="sxs-lookup"><span data-stu-id="d8321-p131">The Any element has optional minMatches and maxMatches attributes that you can use to define how many of the children Match elements must be satisfied before the pattern is matched. Note that these attributes define the number of Match elements that must be satisfied, not the number of instances of evidence found for the matches. To define a minimum number of instances for a specific match, such as two keywords from a list, use the minCount attribute for a Match element (see above).</span></span>
  
### <a name="match-at-least-one-child-match-element"></a><span data-ttu-id="d8321-217">至少匹配一个 Match 子元素</span><span class="sxs-lookup"><span data-stu-id="d8321-217">Match at least one child Match element</span></span>

<span data-ttu-id="d8321-p132">若要规定至少必须符合多少个 Match 元素，可使用 minMatches 特性。实际上，这些 Match 元素是通过隐式 OR 运算符进行联接。如果从任一列表中找到美国格式日期或关键字，就符合以下 Any 元素。</span><span class="sxs-lookup"><span data-stu-id="d8321-p132">If you want to require that only a minimum number of Match elements must be met, you can use the minMatches attribute. In effect, these Match elements are joined by an implicit OR operator. This Any element is satisfied if a US-formatted date or a keyword from either list is found.</span></span>

```xml
<Any minMatches="1" >
     <Match idRef="Func_us_date" />
     <Match idRef="Keyword_employee" />
     <Match idRef="Keyword_badge" />
</Any>
```
    
### <a name="match-an-exact-subset-of-any-children-match-elements"></a><span data-ttu-id="d8321-221">匹配确切的一部分 Match 子元素</span><span class="sxs-lookup"><span data-stu-id="d8321-221">Match an exact subset of any children Match elements</span></span>

<span data-ttu-id="d8321-p133">若要规定必须符合确切数量的 Match 元素，可以将 minMatches 和 maxMatches 设置为相同值。仅当找到确切的一个日期或关键字时，才符合以下 Any 元素。如果找到多个，则与模式不匹配。</span><span class="sxs-lookup"><span data-stu-id="d8321-p133">If you want to require that an exact number of Match elements must be met, you can set minMatches and maxMatches to the same value. This Any element is satisfied only if exactly one date or keyword is found — any more than that, and the pattern won't be matched.</span></span>

```xml
<Any minMatches="1" maxMatches="1" >
     <Match idRef="Func_us_date" />
     <Match idRef="Keyword_employee" />
     <Match idRef="Keyword_badge" />
</Any>
```
  
### <a name="match-none-of-children-match-elements"></a><span data-ttu-id="d8321-224">与任何 Match 子元素都不匹配</span><span class="sxs-lookup"><span data-stu-id="d8321-224">Match none of children Match elements</span></span>

<span data-ttu-id="d8321-p134">若要规定只要缺少某证据才算符合模式，可以将 minMatches 和 maxMatches 同时设置为 0。如果关键字列表或其他证据可能发出误报，这样做就很有用。</span><span class="sxs-lookup"><span data-stu-id="d8321-p134">If you want to require the absence of specific evidence for a pattern to be satisfied, you can set both minMatches and maxMatches to 0. This can be useful if you have a keyword list or other evidence that are likely to indicate a false positive.</span></span>
  
<span data-ttu-id="d8321-p135">例如，“员工 ID”实体查找关键字“卡”，因为这可能会指代“ID 卡”。不过，如果“卡”仅出现在短语“信用卡”中，此内容中的“卡”就不太可能表示“ID 卡”。因此，可以将“信用卡”作为关键字，添加到匹配模式时要排除的术语列表。</span><span class="sxs-lookup"><span data-stu-id="d8321-p135">For example, the employee ID entity looks for the keyword "card" because it might refer to an "ID card". However, if card appears only in the phrase "credit card", "card" in this content is unlikely to mean "ID card". So you can add "credit card" as a keyword to a list of terms that you want to exclude from satisfying the pattern.</span></span>
  
```xml
<Any minMatches="0" maxMatches="0" >
    <Match idRef="Keyword_false_positives_local" />
    <Match idRef="Keyword_false_positives_intl" />
</Any>
```

### <a name="match-a-number-of-unique-terms"></a><span data-ttu-id="d8321-230">匹配多个唯一术语</span><span class="sxs-lookup"><span data-stu-id="d8321-230">Match a number of unique terms</span></span>

<span data-ttu-id="d8321-231">如果要匹配多个唯一术语，请使用 *uniqueResults* 参数，将其设置为 *true*，如下例所示：</span><span class="sxs-lookup"><span data-stu-id="d8321-231">If you want to match a number of unique terms, use the *uniqueResults* parameter, set to *true*, as shown in the following example:</span></span>

```xml
<Pattern confidenceLevel="75">
    <IdMatch idRef="Salary_Revision_terms" />
    <Match idRef=" Salary_Revision_ID " minCount="3" uniqueResults="true" />
</Pattern>
```

<span data-ttu-id="d8321-232">在此示例中，使用至少三个唯一匹配为薪资修订定义模式。</span><span class="sxs-lookup"><span data-stu-id="d8321-232">In this example, a pattern is defined for salary revision using at least three unique matches.</span></span> 
  
## <a name="how-close-to-the-entity-must-the-other-evidence-be-patternsproximity-attribute"></a><span data-ttu-id="d8321-p136">另一证据必须与实体有多接近？[patternsProximity 特性]</span><span class="sxs-lookup"><span data-stu-id="d8321-p136">How close to the entity must the other evidence be? [patternsProximity attribute]</span></span>

<span data-ttu-id="d8321-p137">敏感信息类型要查找表示员工 ID 的模式，此模式还查找确证性证据，如“ID”等关键字。很明显，此证据越接近，模式就越有可能是实际员工 ID。可使用 Entity 元素的必需特性 patternsProximity，确定模式中的另一证据必须与实体有多接近。</span><span class="sxs-lookup"><span data-stu-id="d8321-p137">Your sensitive information type is looking for a pattern that represents an employee ID, and as part of that pattern it's also looking for corroborative evidence like a keyword such as "ID". It makes sense that the closer together this evidence is, the more likely the pattern is to be an actual employee ID. You can determine how close other evidence in the pattern must be to the entity by using the required patternsProximity attribute of the Entity element.</span></span>
  
![显示 patternsProximity 特性的 XML 标记](../media/e97eb7dc-b897-4e11-9325-91c742d9839b.png)
  
<span data-ttu-id="d8321-p138">对于实体中的每种模式，patternsProximity 特性值都定义针对相应模式指定的其他所有 Match 与 IdMatch 位置的距离（以 Unicode 字符数为单位）。接近度窗口以 IdMatch 位置为关键主体，向 IdMatch 左右延伸。</span><span class="sxs-lookup"><span data-stu-id="d8321-p138">For each pattern in the entity, the patternsProximity attribute value defines the distance (in Unicode characters) from the IdMatch location for all other Matches specified for that Pattern. The proximity window is anchored by the IdMatch location, with the window extending to the left and right of the IdMatch.</span></span>
  
![接近度窗口关系图](../media/b593dfd1-5eef-4d79-8726-a28923f7c31e.png)
  
<span data-ttu-id="d8321-p139">下面的示例展示了接近度窗口如何影响模式匹配，其中“员工 ID”自定义实体的 IdMatch 元素要求至少必须有一个关键字或日期确证性匹配。仅 ID1 匹配，因为对于 ID2 和 ID3，在接近度窗口中找不到任何确证性证据或只找到部分确证性证据。</span><span class="sxs-lookup"><span data-stu-id="d8321-p139">The example below illustrates how the proximity window affects the pattern matching where IdMatch element for the employee ID custom entity requires at least one corroborating match of keyword or date. Only ID1 matches because for ID2 and ID3, either no or only partial corroborating evidence is found within the proximity window.</span></span>
  
![确证性证据和接近度窗口的关系图](../media/dc68e38e-dfa1-45b8-b204-89c8ba121f96.png)
  
<span data-ttu-id="d8321-p140">请注意，对于电子邮件，邮件正文和每个附件均被视为独立项。也就是说，接近度窗口不会超越各项末端。对于每一项（附件或正文），idMatch 和确证性证据都必须驻留在相应项中。</span><span class="sxs-lookup"><span data-stu-id="d8321-p140">Note that for email, the message body and each attachment are treated as separate items. This means that the proximity window does not extend beyond the end of each of these items. For each item (attachment or body), both the idMatch and corroborative evidence needs to reside in that item.</span></span>
  
## <a name="what-are-the-right-confidence-levels-for-different-patterns-confidencelevel-attribute-recommendedconfidence-attribute"></a><span data-ttu-id="d8321-p141">什么是各个模式的合适可信度？[confidenceLevel 特性、recommendedConfidence 特性]</span><span class="sxs-lookup"><span data-stu-id="d8321-p141">What are the right confidence levels for different patterns? [confidenceLevel attribute, recommendedConfidence attribute]</span></span>

<span data-ttu-id="d8321-p142">模式需要的证据越多，模式匹配时所标识的实际实体（如员工 ID）的可信度就越高。例如，与只要求匹配九位数 ID 的模式相比，要求匹配九位数 ID、聘用日期和关键字（极为接近）的模式的可信度更高。</span><span class="sxs-lookup"><span data-stu-id="d8321-p142">The more evidence that a pattern requires, the more confidence you have that an actual entity (such as employee ID) has been identified when the pattern is matched. For example, you have more confidence in a pattern that requires a nine-digit ID number, hire date, and keyword in close proximity, than you do in a pattern that requires only a nine-digit ID number.</span></span>
  
<span data-ttu-id="d8321-252">Pattern 元素具有必需的 confidenceLevel 属性。</span><span class="sxs-lookup"><span data-stu-id="d8321-252">The Pattern element has a required confidenceLevel attribute.</span></span> <span data-ttu-id="d8321-253">可将 confidenceLevel（1 到 100 间的整数）的值视为实体中每个模式的唯一 ID - 实体中的模式必须具有不同的可信度级别。</span><span class="sxs-lookup"><span data-stu-id="d8321-253">You can think of the value of confidenceLevel (an integer between 1 and 100) as a unique ID for each pattern in an entity — the patterns in an entity must have different confidence levels that you assign.</span></span> <span data-ttu-id="d8321-254">整数的具体值无关紧要 - 只需选取对符合性团队有意义的数字即可。</span><span class="sxs-lookup"><span data-stu-id="d8321-254">The precise value of the integer doesn't matter — simply pick numbers that make sense to your compliance team.</span></span> <span data-ttu-id="d8321-255">上传自定义敏感信息类型并创建策略后，可在创建的规则的条件中引用这些可信度级别。</span><span class="sxs-lookup"><span data-stu-id="d8321-255">After you upload your custom sensitive information type and then create a policy, you can reference these confidence levels in the conditions of the rules that you create.</span></span>
  
![显示包含不同 confidenceLevel 特性值的 Pattern 元素的 XML 标记](../media/301e0ba1-2deb-4add-977b-f6e9e18fba8b.png)
  
<span data-ttu-id="d8321-257">除每个模式的 confidenceLevel 外，Entity 还有一个 recommendedConfidence 属性。</span><span class="sxs-lookup"><span data-stu-id="d8321-257">In addition to confidenceLevel for each Pattern, the Entity has a recommendedConfidence attribute.</span></span> <span data-ttu-id="d8321-258">可将推荐的可信度属性视为规则的默认可信度级别。</span><span class="sxs-lookup"><span data-stu-id="d8321-258">The recommended confidence attribute can be thought of as the default confidence level for the rule.</span></span> <span data-ttu-id="d8321-259">在策略中创建规则时，如果不指定规则要使用的可信度级别，则该规则将基于推荐的实体可信度级别进行匹配。</span><span class="sxs-lookup"><span data-stu-id="d8321-259">When you create a rule in a policy, if you don't specify a confidence level for the rule to use, that rule will match based on the recommended confidence level for the entity.</span></span> <span data-ttu-id="d8321-260">请注意，规则包中的每个实体 ID 都必须使用 recommendedConfidence 属性，如果该属性缺失，将无法保存使用敏感信息类型的策略。</span><span class="sxs-lookup"><span data-stu-id="d8321-260">Please note that the recommendedConfidence attribute is mandatory for each Entity ID in the Rule Package, if missing you won't be able to save policies that use the Sensitive Information Type.</span></span> 
  
## <a name="do-you-want-to-support-other-languages-in-the-ui-of-the-compliance-center-localizedstrings-element"></a><span data-ttu-id="d8321-261">是否要在合规中心的 UI 中支持其他语言？</span><span class="sxs-lookup"><span data-stu-id="d8321-261">Do you want to support other languages in the UI of the Compliance center?</span></span> <span data-ttu-id="d8321-262">[LocalizedStrings 元素]</span><span class="sxs-lookup"><span data-stu-id="d8321-262">[LocalizedStrings element]</span></span>

<span data-ttu-id="d8321-263">如果符合性团队使用 Microsoft 365 合规中心在不同区域设置和不同语言环境中创建策略，则可提供本地化版本的自定义敏感信息类型的名称和描述。</span><span class="sxs-lookup"><span data-stu-id="d8321-263">If your compliance team uses the Microsoft 365 Compliance center to create polices policies in different locales and in different languages, you can provide localized versions of the name and description of your custom sensitive information type.</span></span> <span data-ttu-id="d8321-264">若符合性团队使用支持语言的 Microsoft 365，则 UI 中会出现本地化的名称。</span><span class="sxs-lookup"><span data-stu-id="d8321-264">When your compliance team uses Microsoft 365 in a language that you support, they'll see the localized name in the UI.</span></span>
  
![“实例计数”和“匹配准确度”选项](../media/11d0b51e-7c3f-4cc6-96d8-b29bcdae1aeb.png)
  
<span data-ttu-id="d8321-p147">Rule 元素必须包含 LocalizedStrings 元素，因为其中包含引用自定义实体 GUID 的 Resource 元素。相应地，每个 Resource 元素都包含一个或多个 Name 和 Description 元素，这些元素使用 langcode 特性来提供特定语言的本地化字符串。</span><span class="sxs-lookup"><span data-stu-id="d8321-p147">The Rules element must contain a LocalizedStrings element, which contains a Resource element that references the GUID of your custom entity. In turn, each Resource element contains one or more Name and Description elements that each use the langcode attribute to provide a localized string for a specific language.</span></span>
  
![显示 LocalizedStrings 元素内容的 XML 标记](../media/a96fc34a-b93d-498f-8b92-285b16a7bbe6.png)
  
<span data-ttu-id="d8321-269">请注意，本地化字符串只能用于决定自定义敏感信息类型在合规中心的 UI 中的显示方式。</span><span class="sxs-lookup"><span data-stu-id="d8321-269">Note that you use localized strings only for how your custom sensitive information type appears in the UI of the Compliance center.</span></span> <span data-ttu-id="d8321-270">不能使用本地化字符串来提供不同版本的本地化关键字列表或正则表达式。</span><span class="sxs-lookup"><span data-stu-id="d8321-270">You can't use localized strings to provide different localized versions of a keyword list or regular expression.</span></span>
  
## <a name="other-rule-package-markup-rulepack-guid"></a><span data-ttu-id="d8321-271">其他规则包标记 [RulePack GUID]</span><span class="sxs-lookup"><span data-stu-id="d8321-271">Other rule package markup [RulePack GUID]</span></span>

<span data-ttu-id="d8321-p149">最后，每个 RulePackage 的开头都有一些需要填写的常规信息。可以下面的标记为模板，将“...”占位符替换为你自己的信息。</span><span class="sxs-lookup"><span data-stu-id="d8321-p149">Finally, the beginning of each RulePackage contains some general information that you need to fill in. You can use the following markup as a template and replace the ". . ." placeholders with your own info.</span></span>
  
<span data-ttu-id="d8321-p150">最重要的是，必须为 RulePack 生成 GUID。在上文中，已为实体生成了 GUID；这是 RulePack 的第二个 GUID。虽然生成 GUID 的方法有很多，但可通过在 PowerShell 中键入 [guid]::NewGuid() 轻松完成。</span><span class="sxs-lookup"><span data-stu-id="d8321-p150">Most importantly, you'll need to generate a GUID for the RulePack. Above, you generated a GUID for the entity; this is a second GUID for the RulePack. There are several ways to generate GUIDs, but you can do it easily in PowerShell by typing [guid]::NewGuid().</span></span>
  
<span data-ttu-id="d8321-p151">Version 元素也很重要。当你首次上传规则包时，Microsoft 365 会记录版本号。稍后，如果更新规则包并上传新版本，请务必更新版本号，否则 Microsoft 365 便不会部署规则包。</span><span class="sxs-lookup"><span data-stu-id="d8321-p151">The Version element is also important. When you upload your rule package for the first time, Microsoft 365 notes the version number. Later, if you update the rule package and upload a new version, make sure to update the version number or Microsoft 365 won't deploy the rule package.</span></span>
  
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

<span data-ttu-id="d8321-283">完成后，RulePack 元素应如下所示。</span><span class="sxs-lookup"><span data-stu-id="d8321-283">When complete, your RulePack element should look like this.</span></span>
  
![显示 RulePack 元素的 XML 标记](../media/fd0f31a7-c3ee-43cd-a71b-6a3813b21155.png)
  
## <a name="changes-for-exchange-online"></a><span data-ttu-id="d8321-285">针对 Exchange Online 的变化</span><span class="sxs-lookup"><span data-stu-id="d8321-285">Changes for Exchange Online</span></span>

<span data-ttu-id="d8321-286">以前，你可能已使用过 Exchange Online PowerShell 为 DLP 导入自定义敏感信息类型。</span><span class="sxs-lookup"><span data-stu-id="d8321-286">Previously, you might have used Exchange Online PowerShell to import your custom sensitive information types for DLP.</span></span> <span data-ttu-id="d8321-287">现在，可以自定义可用于 Exchange 管理中心中和合规中心的敏感信息类型。</span><span class="sxs-lookup"><span data-stu-id="d8321-287">Now your custom sensitive information types can be used in both the Exchange admin center and the Compliance center.</span></span> <span data-ttu-id="d8321-288">此次改进后，应使用合规中心 PowerShell 导入自定义敏感信息类型，不再可从 Exchange PowerShell 导入它们。</span><span class="sxs-lookup"><span data-stu-id="d8321-288">As part of this improvement, you should use Compliance center PowerShell to import your custom sensitive information types — you can't import them from the Exchange PowerShell anymore.</span></span> <span data-ttu-id="d8321-289">自定义敏感信息类型将像往常一样正常工作，但是，在合规中心进行的更改可能需要至多一小时才会出现在 Exchange 管理中心。</span><span class="sxs-lookup"><span data-stu-id="d8321-289">Your custom sensitive information types will continue to work just like before; however, it may take up to one hour for changes made to custom sensitive information types in the Compliance center to appear in the Exchange admin center.</span></span>
  
<span data-ttu-id="d8321-290">请注意，在合规中心中，可以使用 **[New-DlpSensitiveInformationTypeRulePackage](https://docs.microsoft.com/powershell/module/exchange/new-dlpsensitiveinformationtyperulepackage)** cmdlet 上载规则包。</span><span class="sxs-lookup"><span data-stu-id="d8321-290">Note that in the Compliance center, you use the **[New-DlpSensitiveInformationTypeRulePackage](https://docs.microsoft.com/powershell/module/exchange/new-dlpsensitiveinformationtyperulepackage)** cmdlet to upload a rule package.</span></span> <span data-ttu-id="d8321-291">（以前，在 Exchange 管理中心中，使用的是 **ClassificationRuleCollection**\`cmdlet。）</span><span class="sxs-lookup"><span data-stu-id="d8321-291">(Previously, in the Exchange admin center, you used the  **ClassificationRuleCollection**\` cmdlet.)</span></span> 
  
## <a name="upload-your-rule-package"></a><span data-ttu-id="d8321-292">上传规则包</span><span class="sxs-lookup"><span data-stu-id="d8321-292">Upload your rule package</span></span>



<span data-ttu-id="d8321-293">若要上传规则包，请按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="d8321-293">To upload your rule package, do the following steps:</span></span>
  
1. <span data-ttu-id="d8321-294">将文件另存为采用 Unicode 编码的 .xml 文件。</span><span class="sxs-lookup"><span data-stu-id="d8321-294">Save it as an .xml file with Unicode encoding.</span></span>
    
2. [<span data-ttu-id="d8321-295">连接到合规中心 PowerShell</span><span class="sxs-lookup"><span data-stu-id="d8321-295">Connect to Compliance center PowerShell</span></span>](https://go.microsoft.com/fwlink/p/?LinkID=799771)
    
3. <span data-ttu-id="d8321-296">使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="d8321-296">Use the following syntax:</span></span>

   ```powershell
   New-DlpSensitiveInformationTypeRulePackage -FileData (Get-Content -Path "PathToUnicodeXMLFile" -Encoding Byte -ReadCount 0)
   ```

   <span data-ttu-id="d8321-297">本示例从 C:\My Documents 上传名为 MyNewRulePack.xml 的 Unicode XML 文件。</span><span class="sxs-lookup"><span data-stu-id="d8321-297">This example uploads the Unicode XML file named MyNewRulePack.xml from C:\My Documents.</span></span>

   ```powershell
   New-DlpSensitiveInformationTypeRulePackage -FileData (Get-Content -Path "C:\My Documents\MyNewRulePack.xml" -Encoding Byte -ReadCount 0)
   ```

   <span data-ttu-id="d8321-298">有关语法和参数的详细信息，请参阅 [New-DlpSensitiveInformationTypeRulePackage](https://docs.microsoft.com/powershell/module/exchange/new-dlpsensitiveinformationtyperulepackage)。</span><span class="sxs-lookup"><span data-stu-id="d8321-298">For detailed syntax and parameter information, see [New-DlpSensitiveInformationTypeRulePackage](https://docs.microsoft.com/powershell/module/exchange/new-dlpsensitiveinformationtyperulepackage).</span></span>

   > [!NOTE]
   > <span data-ttu-id="d8321-299">支持的规则包数量最多为10个，但每个包可以包含多个敏感信息类型的定义。</span><span class="sxs-lookup"><span data-stu-id="d8321-299">The maximum number of rule packages supported is 10, but each package can contain the definition of multiple sensitive information types.</span></span>

4. <span data-ttu-id="d8321-300">若要验证是否已成功新建敏感信息类型，请按以下任一步骤操作：</span><span class="sxs-lookup"><span data-stu-id="d8321-300">To verify that you've successfully created a new sensitive information type, do any of the following steps:</span></span>

   - <span data-ttu-id="d8321-301">运行 [Get-DlpSensitiveInformationTypeRulePackage](https://docs.microsoft.com/powershell/module/exchange/get-dlpsensitiveinformationtyperulepackage) cmdlet，验证新规则包是否已列出：</span><span class="sxs-lookup"><span data-stu-id="d8321-301">Run the [Get-DlpSensitiveInformationTypeRulePackage](https://docs.microsoft.com/powershell/module/exchange/get-dlpsensitiveinformationtyperulepackage) cmdlet to verify the new rule package is listed:</span></span>

     ```powershell
     Get-DlpSensitiveInformationTypeRulePackage
     ``` 

   - <span data-ttu-id="d8321-302">Run the [Get-DlpSensitiveInformationType](https://docs.microsoft.com/powershell/module/exchange/get-dlpsensitiveinformationtype)，验证敏感信息类型是否已列出：</span><span class="sxs-lookup"><span data-stu-id="d8321-302">Run the [Get-DlpSensitiveInformationType](https://docs.microsoft.com/powershell/module/exchange/get-dlpsensitiveinformationtype) cmdlet to verify the sensitive information type is listed:</span></span>

     ```powershell
     Get-DlpSensitiveInformationType
     ``` 

     <span data-ttu-id="d8321-303">对于自定义敏感信息类型，Publisher 属性值将不是 Microsoft Corporation。</span><span class="sxs-lookup"><span data-stu-id="d8321-303">For custom sensitive information types, the Publisher property value will be something other than Microsoft Corporation.</span></span>

   - <span data-ttu-id="d8321-304">将 \<Name\> 替换为敏感信息类型的 Name 值（例如，员工 ID），然后运行 [Get-DlpSensitiveInformationType](https://docs.microsoft.com/powershell/module/exchange/get-dlpsensitiveinformationtype) cmdlet：</span><span class="sxs-lookup"><span data-stu-id="d8321-304">Replace \<Name\> with the Name value of the sensitive information type (example: Employee ID) and run the [Get-DlpSensitiveInformationType](https://docs.microsoft.com/powershell/module/exchange/get-dlpsensitiveinformationtype) cmdlet:</span></span>

     ```powershell
     Get-DlpSensitiveInformationType -Identity "<Name>"
     ```
    
## <a name="potential-validation-issues-to-be-aware-of"></a><span data-ttu-id="d8321-305">要注意的潜在验证问题</span><span class="sxs-lookup"><span data-stu-id="d8321-305">Potential validation issues to be aware of</span></span>

<span data-ttu-id="d8321-p154">当你上传规则包 XML 文件时，系统会验证 XML，并检查是否有已知的错误模式和明显的性能问题。验证检查正则表达式时，需要检查其中是否有下面的一些已知问题：</span><span class="sxs-lookup"><span data-stu-id="d8321-p154">When you upload your rule package XML file, the system validates the XML and checks for known bad patterns and obvious performance issues. Here are some known issues that the validation checks for — a regular expression:</span></span>
  
- <span data-ttu-id="d8321-308">不得以匹配所有项的交替符“|”开头或结尾，因为这被视为空匹配。</span><span class="sxs-lookup"><span data-stu-id="d8321-308">Cannot begin or end with alternator "|", which matches everything because it's considered an empty match.</span></span>
    
  <span data-ttu-id="d8321-309">例如，“|a”或“b|”无法通过验证。</span><span class="sxs-lookup"><span data-stu-id="d8321-309">For example, "|a" or "b|" will not pass validation.</span></span>
    
- <span data-ttu-id="d8321-310">不得以“{0,m}”模式开头或结尾，它不具备功能性，只会削弱性能。</span><span class="sxs-lookup"><span data-stu-id="d8321-310">Cannot begin or end with a ".{0,m}" pattern, which has no functional purpose and only impairs performance.</span></span>
    
  <span data-ttu-id="d8321-311">例如，“.{0,50}ASDF”或“ASDF.{0,50}”无法通过验证。</span><span class="sxs-lookup"><span data-stu-id="d8321-311">For example, ".{0,50}ASDF" or "ASDF.{0,50}" will not pass validation.</span></span>
    
- <span data-ttu-id="d8321-312">组中既不得有“.{0,m}”或“.{1,m}”，也不得有“.\*”或“.+”。</span><span class="sxs-lookup"><span data-stu-id="d8321-312">Cannot have ".{0,m}" or ".{1,m}" in groups, and cannot have ".\*" or ".+" in groups.</span></span>
    
  <span data-ttu-id="d8321-313">例如，“(.{0,50000})”无法通过验证。</span><span class="sxs-lookup"><span data-stu-id="d8321-313">For example, "(.{0,50000})" will not pass validation.</span></span>
    
- <span data-ttu-id="d8321-314">组中不得有任何字符包含“{0,m}”或“{1,m}”重复符。</span><span class="sxs-lookup"><span data-stu-id="d8321-314">Cannot have any character with "{0,m}" or "{1,m}" repeaters in groups.</span></span>
    
  <span data-ttu-id="d8321-315">例如，“(a\*)”无法通过验证。</span><span class="sxs-lookup"><span data-stu-id="d8321-315">For example, "(a\*)" will not pass validation.</span></span>
    
- <span data-ttu-id="d8321-316">不得以“.{1,m}”开头或结尾；请改用“.”</span><span class="sxs-lookup"><span data-stu-id="d8321-316">Cannot begin or end with ".{1,m}"; instead, use just "."</span></span>
    
  <span data-ttu-id="d8321-317">例如，“.{1,m}asdf”无法通过验证；请改用“.asdf”。</span><span class="sxs-lookup"><span data-stu-id="d8321-317">For example, ".{1,m}asdf" will not pass validation; instead, use just ".asdf".</span></span>
    
- <span data-ttu-id="d8321-318">组中不得有无限重复符（如“\*”或“+”）。</span><span class="sxs-lookup"><span data-stu-id="d8321-318">Cannot have an unbounded repeater (such as "\*" or "+") on a group.</span></span>
    
  <span data-ttu-id="d8321-319">例如，“(xx)\*”和“(xx)+”无法通过验证。</span><span class="sxs-lookup"><span data-stu-id="d8321-319">For example, "(xx)\*" and "(xx)+" will not pass validation.</span></span>
  
- <span data-ttu-id="d8321-320">关键字最多可包含 50 个字符。</span><span class="sxs-lookup"><span data-stu-id="d8321-320">Keywords have a maximum of 50 characters in Length.</span></span>  <span data-ttu-id="d8321-321">如果组中的关键字超过此字符数，建议将术语组创建为[关键字字典](https://docs.microsoft.com/microsoft-365/compliance/create-a-keyword-dictionary)，并在 XML 结构中引用关键字字典的 GUID 作为文件中的 Match 或 idMatch 实体的一部分。</span><span class="sxs-lookup"><span data-stu-id="d8321-321">If you have a keyword within a Group exceeding this, a suggested solution is to create the Group of terms as a [Keyword Dictionary](https://docs.microsoft.com/microsoft-365/compliance/create-a-keyword-dictionary) and reference the GUID of the Keyword Dictionary within the XML structure as part of the Entity for Match or idMatch in the file.</span></span>

- <span data-ttu-id="d8321-322">每个自定义敏感信息类型最多可以包含 2048 个关键字。</span><span class="sxs-lookup"><span data-stu-id="d8321-322">Each Custom Sensitive Information Type can have a maximum of 2048 keywords total.</span></span>

- <span data-ttu-id="d8321-323">单个租户中关键字词典的最大大小为压缩的 100 KB。</span><span class="sxs-lookup"><span data-stu-id="d8321-323">The maximum size of Keyword Dictionaries in a single tenant is 100 kilobytes compressed.</span></span> <span data-ttu-id="d8321-324">创建自定义敏感信息类型时，请尽情地根据需要多次引用同一词典。</span><span class="sxs-lookup"><span data-stu-id="d8321-324">Reference the same dictionary as many times as necessary when creating custom sensitive information types.</span></span> <span data-ttu-id="d8321-325">请先在敏感信息类型中创建自定义关键字列表，然后如果关键字列表中有超过 2048 个关键字或某个关键字长度超过 50 个字符时，请使用关键字词典。</span><span class="sxs-lookup"><span data-stu-id="d8321-325">Start with creating custom keyword lists in the sensitive information type and use keyword dictionaries if you have more than 2048 keywords in a keyword list or a keyword is larger than 50 characters in length.</span></span>

- <span data-ttu-id="d8321-326">确保每个 Entity 元素都包含一个 recommendedConfidence 属性。</span><span class="sxs-lookup"><span data-stu-id="d8321-326">Ensure each Entity element contains a recommendedConfidence attribute.</span></span>

- <span data-ttu-id="d8321-327">使用 PowerShell Cmdlet 时，最多可返回约 1 MB 的反序列化数据。</span><span class="sxs-lookup"><span data-stu-id="d8321-327">When using the PowerShell Cmdlet there is a maximum return size of the Deserialized Data of approximately 1 megabyte.</span></span>   <span data-ttu-id="d8321-328">这会影响规则包 XML 文件的大小。</span><span class="sxs-lookup"><span data-stu-id="d8321-328">This will affect the size of your rule pack XML file.</span></span> <span data-ttu-id="d8321-329">将所上传文件的建议上限设置为 770 KB，以确保结果一致，处理时不会出错。</span><span class="sxs-lookup"><span data-stu-id="d8321-329">Keep the uploaded file limited to a 770 kilobyte maximum as a suggested limit for consistent results without error when processing.</span></span>

- <span data-ttu-id="d8321-330">XML 结构不需要格式设置字符，例如空格、制表符或回车符/行源条目。</span><span class="sxs-lookup"><span data-stu-id="d8321-330">The XML structure does not require formatting characters such as spaces, tabs, or carriage return/linefeed entries.</span></span>  <span data-ttu-id="d8321-331">在针对上传空间进行优化时，请注意这一点。</span><span class="sxs-lookup"><span data-stu-id="d8321-331">Take note of this when optimizing for space on uploads.</span></span> <span data-ttu-id="d8321-332">诸如 Microsoft Visual Code 等工具提供连接线功能来压缩 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="d8321-332">Tools such as Microsoft Visual Code provide join line features to compact the XML file.</span></span>
    
<span data-ttu-id="d8321-333">如果自定义敏感信息类型存在可能会影响性能的问题，便无法上传，且可能会导致以下错误消息之一出现：</span><span class="sxs-lookup"><span data-stu-id="d8321-333">If a custom sensitive information type contains an issue that may affect performance, it won't be uploaded and you may see one of these error messages:</span></span>
  
- <span data-ttu-id="d8321-334">**泛型限定符匹配的内容量超过预期(例如，“+”、“\*”)**</span><span class="sxs-lookup"><span data-stu-id="d8321-334">**Generic quantifiers which match more content than expected (e.g., '+', '\*')**</span></span>
    
- <span data-ttu-id="d8321-335">**环视断言**</span><span class="sxs-lookup"><span data-stu-id="d8321-335">**Lookaround assertions**</span></span>
    
- <span data-ttu-id="d8321-336">**与常规限定符一同使用的分组复杂**</span><span class="sxs-lookup"><span data-stu-id="d8321-336">**Complex grouping in conjunction with general quantifiers**</span></span>
    
## <a name="recrawl-your-content-to-identify-the-sensitive-information"></a><span data-ttu-id="d8321-337">对内容重新爬网以标识敏感信息</span><span class="sxs-lookup"><span data-stu-id="d8321-337">Recrawl your content to identify the sensitive information</span></span>

<span data-ttu-id="d8321-338">Microsoft 365 使用搜索爬取器识别网站内容中的敏感信息并进行分类。</span><span class="sxs-lookup"><span data-stu-id="d8321-338">Microsoft 365 uses the search crawler to identify and classify sensitive information in site content.</span></span> <span data-ttu-id="d8321-339">SharePoint Online 和 OneDrive for Business 网站中的内容更新时会自动重新爬取内容。</span><span class="sxs-lookup"><span data-stu-id="d8321-339">Content in SharePoint Online and OneDrive for Business sites is recrawled automatically whenever it's updated.</span></span> <span data-ttu-id="d8321-340">但若要确定所有现有内容中的新自定义类型的敏感信息，必须重新爬取该内容。</span><span class="sxs-lookup"><span data-stu-id="d8321-340">But to identify your new custom type of sensitive information in all existing content, that content must be recrawled.</span></span>
  
<span data-ttu-id="d8321-341">在 Microsoft 365 中，无法手动请求对整个租户进行重新爬网，但可以对网站集、列表或库这样做。请参阅[手动请求对网站、库或列表进行爬网和重新编制索引](https://docs.microsoft.com/sharepoint/crawl-site-content)。</span><span class="sxs-lookup"><span data-stu-id="d8321-341">In Microsoft 365, you can't manually request a recrawl of an entire tenant, but you can do this for a site collection, list, or library — see [Manually request crawling and re-indexing of a site, a library or a list](https://docs.microsoft.com/sharepoint/crawl-site-content).</span></span>
  
## <a name="remove-a-custom-sensitive-information-type"></a><span data-ttu-id="d8321-342">删除自定义敏感信息类型</span><span class="sxs-lookup"><span data-stu-id="d8321-342">Remove a custom sensitive information type</span></span>

> [!NOTE]
> <span data-ttu-id="d8321-343">删除自定义敏感信息类型前，请先验证没有 DLP 策略或 Exchange 邮件流规则（亦称为“传输规则”）仍在引用此敏感信息类型。</span><span class="sxs-lookup"><span data-stu-id="d8321-343">Before your remove a custom sensitive information type, verify that no DLP policies or Exchange mail flow rules (also known as transport rules) still reference the sensitive information type.</span></span>

<span data-ttu-id="d8321-344">在合规中心 PowerShell 中，有两种方法可以删除自定义敏感信息类型：</span><span class="sxs-lookup"><span data-stu-id="d8321-344">In Compliance center PowerShell, there are two methods to remove custom sensitive information types:</span></span>

- <span data-ttu-id="d8321-p160">删除各个自定义敏感信息类型：使用[修改自定义敏感信息类型](#modify-a-custom-sensitive-information-type)中介绍的方法。导出包含自定义敏感信息类型的自定义规则包，从 XML 文件中删除敏感信息类型，然后将更新的 XML 文件导回现有的自定义规则包。</span><span class="sxs-lookup"><span data-stu-id="d8321-p160">**Remove individual custom sensitive information types**: Use the method documented in [Modify a custom sensitive information type](#modify-a-custom-sensitive-information-type). You export the custom rule package that contains the custom sensitive information type, remove the sensitive information type from the XML file, and import the updated XML file back into the existing custom rule package.</span></span>

- <span data-ttu-id="d8321-347">删除自定义规则包及其包含的所有自定义敏感信息类型：本部分介绍了此方法。</span><span class="sxs-lookup"><span data-stu-id="d8321-347">**Remove a custom rule package and all custom sensitive information types that it contains**: This method is documented in this section.</span></span>

1. [<span data-ttu-id="d8321-348">连接到合规中心 PowerShell</span><span class="sxs-lookup"><span data-stu-id="d8321-348">Connect to Compliance center PowerShell</span></span>](https://go.microsoft.com/fwlink/p/?LinkID=799771)

2. <span data-ttu-id="d8321-349">若要删除自定义规则包，请使用 [Remove-DlpSensitiveInformationTypeRulePackage](https://docs.microsoft.com/powershell/module/exchange/remove-dlpsensitiveinformationtyperulepackage) cmdlet：</span><span class="sxs-lookup"><span data-stu-id="d8321-349">To remove a custom rule package, use the [Remove-DlpSensitiveInformationTypeRulePackage](https://docs.microsoft.com/powershell/module/exchange/remove-dlpsensitiveinformationtyperulepackage) cmdlet:</span></span>

   ```powershell
   Remove-DlpSensitiveInformationTypeRulePackage -Identity "RulePackageIdentity"
   ```

   <span data-ttu-id="d8321-350">可使用 Name 值（适用于任何语言）或 `RulePack id` (GUID) 值来标识规则包。</span><span class="sxs-lookup"><span data-stu-id="d8321-350">You can use the Name value (for any language) or the `RulePack id` (GUID) value to identify the rule package.</span></span>

   <span data-ttu-id="d8321-351">本示例删除名为“Employee ID Custom Rule Pack”的规则包。</span><span class="sxs-lookup"><span data-stu-id="d8321-351">This example removes the rule package named "Employee ID Custom Rule Pack".</span></span>

   ```powershell
   Remove-DlpSensitiveInformationTypeRulePackage -Identity "Employee ID Custom Rule Pack"
   ```

   <span data-ttu-id="d8321-352">有关语法和参数的详细信息，请参阅 [Remove-DlpSensitiveInformationTypeRulePackage](https://docs.microsoft.com/powershell/module/exchange/remove-dlpsensitiveinformationtyperulepackage)。</span><span class="sxs-lookup"><span data-stu-id="d8321-352">For detailed syntax and parameter information, see [Remove-DlpSensitiveInformationTypeRulePackage](https://docs.microsoft.com/powershell/module/exchange/remove-dlpsensitiveinformationtyperulepackage).</span></span>

3. <span data-ttu-id="d8321-353">若要验证是否已成功删除自定义敏感信息类型，请执行以下任意步骤：</span><span class="sxs-lookup"><span data-stu-id="d8321-353">To verify that you've successfully removed a custom sensitive information type, do any of the following steps:</span></span>

   - <span data-ttu-id="d8321-354">运行 [Get-DlpSensitiveInformationTypeRulePackage](https://docs.microsoft.com/powershell/module/exchange/get-dlpsensitiveinformationtyperulepackage) cmdlet，验证规则包不再列出：</span><span class="sxs-lookup"><span data-stu-id="d8321-354">Run the [Get-DlpSensitiveInformationTypeRulePackage](https://docs.microsoft.com/powershell/module/exchange/get-dlpsensitiveinformationtyperulepackage) cmdlet and verify the rule package is no longer listed:</span></span>

     ```powershell
     Get-DlpSensitiveInformationTypeRulePackage
     ```

   - <span data-ttu-id="d8321-355">运行 [Get-DlpSensitiveInformationType](https://docs.microsoft.com/powershell/module/exchange/get-dlpsensitiveinformationtype) cmdlet，验证已删除的规则包中的敏感信息类型不再列出：</span><span class="sxs-lookup"><span data-stu-id="d8321-355">Run the [Get-DlpSensitiveInformationType](https://docs.microsoft.com/powershell/module/exchange/get-dlpsensitiveinformationtype) cmdlet to verify the sensitive information types in the removed rule package are no longer listed:</span></span>

     ```powershell
     Get-DlpSensitiveInformationType
     ```

     <span data-ttu-id="d8321-356">对于自定义敏感信息类型，Publisher 属性值将不是 Microsoft Corporation。</span><span class="sxs-lookup"><span data-stu-id="d8321-356">For custom sensitive information types, the Publisher property value will be something other than Microsoft Corporation.</span></span>

   - <span data-ttu-id="d8321-357">将 \<Name\> 替换为敏感信息类型的 Name 值（例如，员工 ID），然后运行 [Get-DlpSensitiveInformationType](https://docs.microsoft.com/powershell/module/exchange/get-dlpsensitiveinformationtype) cmdlet ，验证敏感信息类型是否不再列出：</span><span class="sxs-lookup"><span data-stu-id="d8321-357">Replace \<Name\> with the Name value of the sensitive information type (for example, Employee ID) and run the [Get-DlpSensitiveInformationType](https://docs.microsoft.com/powershell/module/exchange/get-dlpsensitiveinformationtype) cmdlet to verify the sensitive information type is no longer listed:</span></span>

     ```powershell
     Get-DlpSensitiveInformationType -Identity "<Name>"
     ```

## <a name="modify-a-custom-sensitive-information-type"></a><span data-ttu-id="d8321-358">修改自定义敏感信息类型</span><span class="sxs-lookup"><span data-stu-id="d8321-358">Modify a custom sensitive information type</span></span>

<span data-ttu-id="d8321-359">在合规中心 PowerShell 中，若要修改自定义敏感信息类型，需要执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="d8321-359">In Compliance center PowerShell, modifying a custom sensitive information type requires you to:</span></span>

1. <span data-ttu-id="d8321-360">将包含自定义敏感信息类型的现有规则包导出到 XML 文件（或者，如果已有 XML 文件，则使用它）。</span><span class="sxs-lookup"><span data-stu-id="d8321-360">Export the existing rule package that contains the custom sensitive information type to an XML file (or use the existing XML file if you have it).</span></span>

2. <span data-ttu-id="d8321-361">修改导出的 XML 文件中的自定义敏感信息类型。</span><span class="sxs-lookup"><span data-stu-id="d8321-361">Modify the custom sensitive information type in the exported XML file.</span></span>

3. <span data-ttu-id="d8321-362">将更新的 XML 文件导回现有规则包。</span><span class="sxs-lookup"><span data-stu-id="d8321-362">Import the updated XML file back into the existing rule package.</span></span>

<span data-ttu-id="d8321-363">若要连接到合规中心 PowerShell，请参阅[连接到合规中心 PowerShell](https://go.microsoft.com/fwlink/p/?LinkID=799771)。</span><span class="sxs-lookup"><span data-stu-id="d8321-363">To connect to Compliance Center PowerShell, see [Connect to Compliance Center PowerShell](https://go.microsoft.com/fwlink/p/?LinkID=799771).</span></span>

### <a name="step-1-export-the-existing-rule-package-to-an-xml-file"></a><span data-ttu-id="d8321-364">步骤 1：将现有的规则包导出到 XML 文件</span><span class="sxs-lookup"><span data-stu-id="d8321-364">Step 1: Export the existing rule package to an XML file</span></span>

> [!NOTE]
> <span data-ttu-id="d8321-365">如果有 XML 文件的副本 （例如，只需创建并导入它），可跳到下一步来修改 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="d8321-365">If you have a copy of the XML file (for example, you just created and imported it), you can skip to the next step to modify the XML file.</span></span>

1. <span data-ttu-id="d8321-366">如果你还不确定，请运行 [Get-DlpSensitiveInformationTypeRulePackage](https://docs.microsoft.com/powershell/module/exchange/get-dlpsensitiveinformationtype) cmdlet，查找自定义规则包的名称：</span><span class="sxs-lookup"><span data-stu-id="d8321-366">If you don't already know it, run the [Get-DlpSensitiveInformationTypeRulePackage](https://docs.microsoft.com/powershell/module/exchange/get-dlpsensitiveinformationtype) cmdlet to find the name of the custom rule package:</span></span>

   ```powershell
   Get-DlpSensitiveInformationTypeRulePackage
   ```

   > [!NOTE]
   > <span data-ttu-id="d8321-367">包含内置敏感信息类型的内置规则包被称为 Microsoft 规则包。</span><span class="sxs-lookup"><span data-stu-id="d8321-367">The built-in rule package that contains the built-in sensitive information types is named Microsoft Rule Package.</span></span> <span data-ttu-id="d8321-368">包含你在“合规中心” UI中创建的自定义敏感信息类型的规则包称为 Microsoft.SCCManaged.CustomRulePack。</span><span class="sxs-lookup"><span data-stu-id="d8321-368">The rule package that contains the custom sensitive information types that you created in the Compliance center UI is named Microsoft.SCCManaged.CustomRulePack.</span></span>

2. <span data-ttu-id="d8321-369">使用 [Get-DlpSensitiveInformationTypeRulePackage](https://docs.microsoft.com/powershell/module/exchange/get-dlpsensitiveinformationtyperulepackage) cmdlet，将自定义规则包存储到变量：</span><span class="sxs-lookup"><span data-stu-id="d8321-369">Use the [Get-DlpSensitiveInformationTypeRulePackage](https://docs.microsoft.com/powershell/module/exchange/get-dlpsensitiveinformationtyperulepackage) cmdlet to store the custom rule package to a variable:</span></span>

   ```powershell
   $rulepak = Get-DlpSensitiveInformationTypeRulePackage -Identity "RulePackageName"
   ```

   <span data-ttu-id="d8321-370">例如，如果规则包的名称是“Employee ID Custom Rule Pack”，请运行以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="d8321-370">For example, if the name of the rule package is "Employee ID Custom Rule Pack", run the following cmdlet:</span></span>

   ```powershell
   $rulepak = Get-DlpSensitiveInformationTypeRulePackage -Identity "Employee ID Custom Rule Pack"
   ```

3. <span data-ttu-id="d8321-371">使用 [Set-Content](https://docs.microsoft.com/powershell/module/microsoft.powershell.management/set-content?view=powershell-6) cmdlet 将自定义规则包导出到 XML 文件：</span><span class="sxs-lookup"><span data-stu-id="d8321-371">Use the [Set-Content](https://docs.microsoft.com/powershell/module/microsoft.powershell.management/set-content?view=powershell-6) cmdlet to export the custom rule package to an XML file:</span></span>

   ```powershell
   Set-Content -Path "XMLFileAndPath" -Encoding Byte -Value $rulepak.SerializedClassificationRuleCollection
   ```

   <span data-ttu-id="d8321-372">本示例将规则包导出到 C:\My Documents 文件夹中名为 ExportedRulePackage.xml 的文件。</span><span class="sxs-lookup"><span data-stu-id="d8321-372">This example export the rule package to the file named ExportedRulePackage.xml in the C:\My Documents folder.</span></span>

   ```powershell
   Set-Content -Path "C:\My Documents\ExportedRulePackage.xml" -Encoding Byte -Value $rulepak.SerializedClassificationRuleCollection
   ```

#### <a name="step-2-modify-the-sensitive-information-type-in-the-exported-xml-file"></a><span data-ttu-id="d8321-373">步骤 2：修改导出的 XML 文件中的敏感信息类型</span><span class="sxs-lookup"><span data-stu-id="d8321-373">Step 2: Modify the sensitive information type in the exported XML file</span></span>

<span data-ttu-id="d8321-374">本文前面介绍了 XML 文件中的敏感信息类型和文件中的其他元素。</span><span class="sxs-lookup"><span data-stu-id="d8321-374">Sensitive information types in the XML file and other elements in the file are described earlier in this topic.</span></span>

#### <a name="step-3-import-the-updated-xml-file-back-into-the-existing-rule-package"></a><span data-ttu-id="d8321-375">步骤 3：将更新的 XML 文件导回现有规则包。</span><span class="sxs-lookup"><span data-stu-id="d8321-375">Step 3: Import the updated XML file back into the existing rule package</span></span>

<span data-ttu-id="d8321-376">若要将更新的 XML 导回现有规则包，请使用 [Set-DlpSensitiveInformationTypeRulePackage](https://docs.microsoft.com/powershell/module/exchange/set-dlpsensitiveinformationtyperulepackage) cmdlet：</span><span class="sxs-lookup"><span data-stu-id="d8321-376">To import the updated XML back into the existing rule package, use the [Set-DlpSensitiveInformationTypeRulePackage](https://docs.microsoft.com/powershell/module/exchange/set-dlpsensitiveinformationtyperulepackage) cmdlet:</span></span>

```powershell
Set-DlpSensitiveInformationTypeRulePackage -FileData ([Byte[]]$(Get-Content -Path "C:\My Documents\External Sensitive Info Type Rule Collection.xml" -Encoding Byte -ReadCount 0))
```

<span data-ttu-id="d8321-377">有关语法和参数的详细信息，请参阅 [Set-DlpSensitiveInformationTypeRulePackage](https://docs.microsoft.com/powershell/module/exchange/set-dlpsensitiveinformationtyperulepackage)。</span><span class="sxs-lookup"><span data-stu-id="d8321-377">For detailed syntax and parameter information, see [Set-DlpSensitiveInformationTypeRulePackage](https://docs.microsoft.com/powershell/module/exchange/set-dlpsensitiveinformationtyperulepackage).</span></span>

## <a name="reference-rule-package-xml-schema-definition"></a><span data-ttu-id="d8321-378">参考：规则包 XML 架构定义</span><span class="sxs-lookup"><span data-stu-id="d8321-378">Reference: Rule package XML schema definition</span></span>

<span data-ttu-id="d8321-379">可复制此标记，并将它另存为 XSD 文件，以用来验证规则包 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="d8321-379">You can copy this markup, save it as an XSD file, and use it to validate your rule package XML file.</span></span>
  
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

## <a name="more-information"></a><span data-ttu-id="d8321-380">更多信息</span><span class="sxs-lookup"><span data-stu-id="d8321-380">More information</span></span>

- [<span data-ttu-id="d8321-381">数据丢失防护策略概述</span><span class="sxs-lookup"><span data-stu-id="d8321-381">Overview of data loss prevention policies</span></span>](data-loss-prevention-policies.md)

- [<span data-ttu-id="d8321-382">敏感信息类型属性定义</span><span class="sxs-lookup"><span data-stu-id="d8321-382">Sensitive information type entity definitions</span></span>](sensitive-information-type-entity-definitions.md)

- [<span data-ttu-id="d8321-383">DLP 函数查找什么</span><span class="sxs-lookup"><span data-stu-id="d8321-383">What the DLP functions look for</span></span>](what-the-dlp-functions-look-for.md)
