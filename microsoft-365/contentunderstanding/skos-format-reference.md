---
title: SharePoint 分类的 SKOS 格式参考
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
description: SharePoint 分类的 SKOS 格式参考
ms.openlocfilehash: eb228394b06b6e6027937ab105df7c0079875226
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/28/2020
ms.locfileid: "48295796"
---
# <a name="skos-format-reference-for-sharepoint-taxonomy"></a>SharePoint 分类的 SKOS 格式参考

本文包括用于表示 [SharePoint 分类](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) 和基于 [SKOS](https://www.w3.org/TR/skos-primer/)的 RDF 词汇。 若要对此 RDF 语法进行序列化，请使用 RDF [龟标](https://www.w3.org/TR/turtle/)。

下表显示了[SharePoint 分类](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy)词汇的[SKOS](https://www.w3.org/TR/skos-primer/)等效项。 SharePoint 不支持没有 SharePoint 分类等效项的 [SKOS](https://www.w3.org/TR/skos-primer/) 值。

|SharePoint 分类|SKOS 等效项|
|:-----------------|:--------------|
|sharepoint-分类：术语|skos：概念|
|sharepoint-分类： TermSet|skos:ConceptScheme|
|sharepoint-分类： inTermSet|skos:inScheme|
|sharepoint-分类： hasTopLevelTerm|skos:hasTopConcept|
|sharepoint-分类： topLevelTermOf|skos:topConceptOf|
|sharepoint-分类： defaultLabel|skos:prefLabel|
|sharepoint-分类： termSetName|skos:prefLabel|
|sharepoint-分类： propertyName|skos:prefLabel|
|sharepoint-分类： otherLabel|skos:altLabel|
|sharepoint-分类：说明|skos：定义|
|sharepoint-分类：父|skos：更广泛|
|sharepoint-分类：子级|skos：变窄|

下表显示了从 [OWL](https://www.w3.org/TR/owl2-primer/)派生的 SharePoint 分类词汇的实体。

|SharePoint 分类词汇|派生自 OWL|
|:-----------------------------|:----------------------|
|sharepoint-分类： isAvailableForTagging|owl:datatypeproperty|
|sharepoint-分类： SharedCustomPropertyForTerm|owl： Property|
|sharepoint-分类： LocalCustomPropertyForTerm|owl： Property|
|sharepoint-分类： CustomPropertyForTermSet|owl： Property|

## <a name="sharepoint-taxonomy-vocabulary"></a>SharePoint 分类词汇

分类是正式的分类系统。 分类对描述内容的词、标签和术语进行分组，然后将组排列到一个层次结构中。

**sharepoint-分类：术语**

表示托管元数据层次结构中的 Term 或关键字。

[术语](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)是 SharePoint [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore)的原子单元。 每个[术语](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)都属于一个属于[术语组](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.group)的[TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) 。 

定义 [术语](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) 的语法如下所示：

```SKOS
ex:TermA    a    sharepoint-taxonomy:Term;
    sharepoint-taxonomy:inTermSet    ex:TermSetA;
    sharepoint-taxonomy:topLevelTermOf    ex:TermSetA;
    sharepoint-taxonomy:child    ex:TermA1;
    sharepoint-taxonomy:isAvailableForTagging    “true”^^xsd:Boolean;
    sharePoint-taxonomy:defaultLabel    “Term A”@en-us.
```

[术语](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)compulsorily 存在于[TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)中。 DefaultLabel 是显示在可视表示形式中的 [术语](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) 的名称。 用于定义 [术语](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) 的必填字段包括：

- sharepoint-分类： defaultLabel
- sharepoint-分类： inTermSet

[术语](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)可以：

- 与另一个 [术语](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) 按层次结构相关，这两个 [术语](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) 都属于同一个 [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)。
- 具有多个子 [术语](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)，但只能有一个父 [术语](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)。
- 未定义父 [术语](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) ，如果它是 [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)的 topLevelTermOf。
- 具有一个 defaultLabel，每个 [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) 的工作语言。
- 如果它既不包含父 [术语](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)，也不是 topLevelTermOf [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)，则不存在。 
- 在相同的层次结构级别中只有一个唯一的 defaultLabel。

**sharepoint-分类： TermSet**

按场中注册的名称显示的标识提供程序的名称。

顾名思义，TermSet 是一组 [术语](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)。 [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore)中的某个[术语](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)必须属于[TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)。 任何 [术语](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) 都不能独立存在。 

定义 [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) 的语法为：

```SKOS
ex:TermSetA    a    sharepoint-taxonomy:TermSet;
    sharepoint-taxonomy:termSetName    “TermSet A";
    sharepoint-taxonomy:isAvailableForTagging    “true”^^xsd:Boolean;
    sharepoint-taxonomy:hasTopLevelTerm    Ex:Term A.
```

[TermSets](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) 在 [TermGroups](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.group)中逻辑分组在一起。 用于定义 [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) 的必填字段为：

- sharepoint-分类： termSetName

在 [术语组](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.group)中提供的 termSetName 不是唯一的情况下，SharPoint 会在名称的末尾追加一个数字，以保持 termSetName (s) 的唯一性。

**sharepoint-分类： hasTopLevelTerm**

SharePoint 使用此属性在[TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)中映射最顶部的[术语](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)，这是[TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)中[术语](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)层次结构的入口点。 这是对 sharepoint 分类的反向关系： topLevelTermOf。 

定义此项的语法为：

```SKOS
ex:TermSetA    sharepoint-taxonomy:hasTopLevelTerm    ex:TermA.
```

>[!NOTE]
> 您不能定义父[术语](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)的顶级[术语](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)。

**sharepoint-分类： topLevelTermOf**

Sharepoint-分类： topLevelTermOf 是 sharepoint 分类的反向： hasTopLevelTerm

定义此项的语法为：

```SKOS
ex:TermA    sharepoint-taxonomy:topLevelTermOf    ex:TermSetA.
```

**sharepoint-分类： inTermSet**

使用此 [项将术语](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) 映射到 [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)。 一个 [词](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) 只能存在于一个 [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)中。 [定义术语](https://github.com/MicrosoftDocs/microsoft-365-docs-pr/blob/3a3cd54dd076b18bdff1d43b3e342897f8704c23/microsoft-365/contentunderstanding/skos-format-reference.md#term)时，SharePoint 需要此属性。

## <a name="required-labels"></a>必需标签

您的组织可能希望在开始使用托管元数据之前进行周密的规划。 您必须执行的规划量取决于您的分类的形式。 它还取决于您希望对元数据施加多少控制。 在层次结构的每个级别，需要为术语或 TermSet 配置所需的 lables。

一个术语可以具有一个或多个默认语言的标签，而非默认语言中的零个或多个标签。 如果术语具有某种语言的标签，则其中一个标签必须为默认标签。

**sharepoint-分类： defaultLabel**

对术语为必需参数的[术语](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)使用此默认词法[标签。](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) 用于以可视方式表示 [术语](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)。

定义 defaultLabel 的语法为：

```SKOS
ex:TermA    sharepoint-taxonomy:defaultLabel    “Term A”@en-us.
```

DefaultLabel 包含两个部分–字符串和语言标记。 该语言必须是 [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) 工作的语言之一。 对于同一[TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)中的所有[术语](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)，defaultLabel 必须是唯一的层次结构级别。

**sharepoint-分类： termSetName**

获取并设置当前 TermSet 对象的名称。

这是 [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)的词法标签，采用 [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) 的工作语言。 这是 [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)的必需参数。 用于以可视方式表示 [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)。

定义 termSetName 的语法为：

```SKOS
ex:TermA    sharepoint-taxonomy:TermSetName    “Term Set A”@en-us.
```

**sharepoint-分类： propertyName**

获取并设置当前 TermSet 对象的属性名称。

这是 sharepoint 分类的词法标签： SharedCustomPropertyForTerm、sharepoint 分类： LocalCustomPropertyForTerm 和 sharepoint 分类： CustomPropertyForTermSet in [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) 工作语言。

Sharepoint 分类： propertyName 将被视为 CustomProperty 的键。

定义 propetyName 的语法为：

```SKOS
ex:SharedCustomProperty1    sharepoint-taxonomy:propertyName    “Shared Custom Property Key 1”@en-us.
```

## <a name="optional-labels"></a>可选标签

您还可以将可选标签添加到分类中。

**sharepoint-分类： otherLabel**

这是 [术语](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)的替代词法标签。 

定义 otherLabel 的语法为：

```SKOS
ex:TermA    sharepoint-taxonomy:otherLabel    “Term A”@en-us.
```

## <a name="semantic-relationships"></a>语义关系

分类具有层次结构，有时也是一个简单的 "相关术语" 关联关系，但有些是 "语义关系" 或自定义创建的关系。 

**sharepoint-分类：父**

这将一个 [术语](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) 分层与另一个 [术语](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)相关联。 [术语](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)可以是[TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)的首要[术语](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)，但如果它不必须具有父[术语](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)。 

定义父级的语法为：

```SKOS
ex:TermA1    sharepoint-taxonomy:parent    ex:TermA.
```

这意味着 TermA1 具有父 TermA。 同时，还意味着 TermA1 是 TermA 的子项。 父子关系是一个 inversible 关系。

**sharepoint-分类：子级**

对象包含一个或多个子 TermSet 实例，可以通过 TermSets 属性访问这些实例。 此类还提供用于创建新的子 TermSet 对象的方法。 在组中指定编辑子术语和 TermSet 实例的权限。 

这将一个 [术语](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) 分层与另一个 [术语](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)相关联。

用于定义子级的语法为：

```SKOS
ex:TermA    sharepoint-taxonomy:child    ex:TermA1.
```

这意味着 TermA 具有子 TermA1。 同时，还意味着 TermA 是 TermA1 父-子关系的父级是一个 inversible 关系。

## <a name="documentation-notes"></a>文档说明

本节讨论了在 Microsoft. 分类命名空间中详细介绍的分类。

**sharepoint-分类：说明**

这是对任何 [SharePoint 分类](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) 词汇实体的详细说明。 

添加说明的语法为：

```SKOS
ex:TermA    sharepoint-taxonomy:description    “Term A is the top level term of TermSetA”@en-us.
```

## <a name="custom-properties"></a>自定义属性

从只读字典中获取当前 Term 对象的自定义属性对象的集合。

自定义属性是可为 [术语](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) 或 [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)定义的键值对，以进一步说明 [术语](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) 或 [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)的说明。 SharePoint 指定具有 propertyName 的帮助的自定义属性的键。

**sharepoint-分类： CustomPropertyForTermSet**

定义此项的语法为：

```SKOS
ex:CustomProp1    rdf:type    sharepoint-taxonomy:CustomPropertyForTermSet;
    sharepoint-taxonomy:propertyName “Colour”.

ex:TermSetA    ex:CustomProp1    “Red”@en-us.
```

**sharepoint-分类： SharedCustomPropertyForTerm**

如果某一 [术语](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) 的自定义属性需要与 [术语](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)一起使用，则在其他地方重复使用该 [术语](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) 时，需要在 SharedCustomPropertyForTerm 下定义它。

定义此项的语法为：

``` SKOS
ex:CustomProp2    rdf:type sharepoint-taxonomy:SharedCustomPropertyForTerm;
    sharepoint-taxonomy:propertyName “Length”.

ex:TermA    ex:CustomProp2    “5 cm”@en-us.
```
**sharepoint-分类： LocalCustomPropertyForTerm**

如果不需要将 [术语](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) 的自定义属性与 [术语](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)一起携带，则在其他地方重复使用该 [术语](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) 时，需要在 LocalCustomPropertyForTerm 下定义它。

定义此项的语法为：

```SKOS
ex:CustomProp3    rdf:type sharepoint-taxonomy:LocalCustomPropertyForTerm;
    sharepoint-taxonomy:propertyName “width”.

ex:TermA    ex:CustomProp3    “5 cm”@en-us.
```

## <a name="data-properties"></a>数据属性

在层次结构的每个级别上，可以为术语或 TermSet 配置特定的数据属性。

**sharepoint-分类： isAvailableForTagging**

使用此项可指定某个 [术语](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) 或 [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) 在 SharePoint 列表和库中是否可用。  

的语法如下：

```SKOS
ex:TermA    sharepoint-taxonomy:isAvailableForTagging     "true"^^xsd:Boolean;
```

## <a name="domain-and-range"></a>域和区域

下表介绍了 SharePoint 分类词汇的域和范围。

|谓词/谓词|含义|域|Range|
|:--------------|:------|:-----|:----|
inTermSet|在术语集中|Term|术语集|
inTermGroup|在术语组中|TermSet|TermGroup|
topLevelTermOf|是顶级术语|Term|TermSet|
hasTopLevelTerm|具有顶级术语|术语集|Term|
termSetName|术语集具有名称|Term|纯文本|
defaultLabel|条件具有默认标签|Term|纯文本|
otherLabel|字词有其他标签|Term|纯文本|
propertyName|具有属性标签|SharedCustomPropertyForTerm, LocalCustomPropertyForTerm, CustomPropertyForTermSet |Boolean、String、Integer、Decimal、Double|
|description|包含描述|全部|纯文本|
|父级|具有父级|Term|Term|
|该子|具有子|Term|Term|
|isAvailableForTagging|是否可用于标记|术语、术语集|Boolean|
|SharedCustomPropertyForTerm|具有共享的自定义属性|Term|Boolean、string、Integer、Decimal、Double|
|LocalCustomPropertyForTerm|具有本地自定义属性|Term|Boolean、String、Integer、Decimal、Double|
|CustomPropertyForTermSet|具有自定义属性|TermSet|Boolean、String、Integer、Decimal、Double|

[SKOS](https://www.w3.org/TR/skos-primer/) [SharePoint 分类](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) 不允许的有效方案：

- 分层冗余- [SKOS](https://www.w3.org/TR/skos-primer/) 概念可以同时附加到多个更广泛的概念，但 sharepoint 分类：术语只能有一个 sharepoint 分类：父，因此，也不允许使用循环依赖项。
- SharePoint 分类中不允许使用孤立术语。 每个 sharepoint 分类：术语应具有 sharepoint 分类： parent 或应为 sharepoint 分类： topLevelTermOf a TermSet。
- SharePoint 分类不支持关联关系。
- SharePoint 分类只允许2种类型的层次结构关系– sharepoint 分类：父项和 sharepoint 分类：子级。 
- 与 [SKOS](https://www.w3.org/TR/skos-primer/) 不同，SharePoint 分类词汇表中的层次结构关系仅可在同一 TermSet 中使用术语建立。

## <a name="see-also"></a>另请参阅

[使用基于 SKOS 的格式导入术语集](import-term-set-skos.md)

