---
title: SharePoint 分类的 SKOS 格式参考
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection: enabler-strategic
ms.localizationpriority: high
description: SharePoint 分类的 SKOS 格式参考
ms.openlocfilehash: 95183b64d76a70f69d08cd5a3c9dcf76f4e83bce
ms.sourcegitcommit: dc26169e485c3a31e1af9a5f495be9db75c49760
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2021
ms.locfileid: "60747652"
---
# <a name="skos-format-reference-for-sharepoint-taxonomy"></a>SharePoint 分类的 SKOS 格式参考

本文包含用于表示 [SharePoint 分类](/dotnet/api/microsoft.sharepoint.taxonomy)，并且基于 [SKOS](https://www.w3.org/TR/skos-primer/) 的 RDF 词汇表。 若要将此 RDF 语法序列化，请使用 RDF [TURTLE](https://www.w3.org/TR/turtle/)。

下表显示了 [SharePoint 分类](/dotnet/api/microsoft.sharepoint.taxonomy) 词汇表的 [SKOS](https://www.w3.org/TR/skos-primer/) 等效项。 SharePoint 不支持没有 SharePoint 分类等效项的 [SKOS](https://www.w3.org/TR/skos-primer/) 值。

|SharePoint 分类|SKOS 等效项|
|:-----------------|:--------------|
|sharepoint-taxonomy:Term|skos:Concept|
|sharepoint-taxonomy:TermSet|skos:ConceptScheme|
|sharepoint-taxonomy:inTermSet|skos:inScheme|
|sharepoint-taxonomy:hasTopLevelTerm|skos:hasTopConcept|
|sharepoint-taxonomy:topLevelTermOf|skos:topConceptOf|
|sharepoint-taxonomy:defaultLabel|skos:prefLabel|
|sharepoint-taxonomy:termSetName|skos:prefLabel|
|sharepoint-taxonomy:propertyName|skos:prefLabel|
|sharepoint-taxonomy:otherLabel|skos:altLabel|
|sharepoint-taxonomy:description|skos:definition|
|sharepoint-taxonomy:parent|skos:broader|
|sharepoint-taxonomy:child|skos:narrower|

下表显示从 [OWL](https://www.w3.org/TR/owl2-primer/) 派生的 SharePoint 分类词汇表的实体。

|SharePoint 分类词汇表|派生自 OWL|
|:-----------------------------|:----------------------|
|sharepoint-taxonomy:isAvailableForTagging|owl:datatypeproperty|
|sharepoint-taxonomy:SharedCustomPropertyForTerm|owl:ObjectProperty|
|sharepoint-taxonomy:LocalCustomPropertyForTerm|owl:ObjectProperty|
|sharepoint-taxonomy:CustomPropertyForTermSet|owl:ObjectProperty|

## <a name="sharepoint-taxonomy-vocabulary"></a>SharePoint 分类词汇表

分类是正式分类系统。分类将描述某些内容的字词、标签和术语分组，然后将组排列到层次结构中。

**sharepoint-taxonomy:Term**

表示托管元数据层次结构中的Term或“关键字”。

[Term](/dotnet/api/microsoft.sharepoint.taxonomy.term)是 SharePoint [TermStore](/dotnet/api/microsoft.sharepoint.taxonomy.termstore) 的原子单元。 每个[Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) 都隶属于归属 [TermGroup](/dotnet/api/microsoft.sharepoint.taxonomy.group) 的 [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset)。

定义 [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) 的语法如下所示：

```SKOS
ex:TermA    a    sharepoint-taxonomy:Term;
    sharepoint-taxonomy:inTermSet    ex:TermSetA;
    sharepoint-taxonomy:topLevelTermOf    ex:TermSetA;
    sharepoint-taxonomy:child    ex:TermA1;
    sharepoint-taxonomy:isAvailableForTagging    “true”^^xsd:Boolean;
    sharePoint-taxonomy:defaultLabel    “Term A”@en-us.
```

[Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) 强制性地存在于 [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset) 内。 DefaultLabel 是 [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) 显示在直观呈现方式中的名称。。 定义 [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) 所需的字段包括：

- sharepoint-taxonomy:defaultLabel
- sharepoint-taxonomy:inTermSet

[Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) 可以：

- 可与另一个 [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) 进行分层，前提是两个 [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) 都属于同一 [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset)。
- 具有多个子级 [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term)，但仅一个父级 [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term)。
- 如果是某个 [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset) 的 topLevelTermOf 术语的话，则可以不必由父级 [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) 定义。
- 在每个 [TermStore](/dotnet/api/microsoft.sharepoint.taxonomy.termstore) 工作语言中拥有一个 defaultLabel。
- 不存在（如果它既不包含父级 [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term)，也不是某个 [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset) 的 topLevelTermOf 术语的话）。
- 在相同的分层级别中只拥有一个唯一的 defaultLabel。

**sharepoint-taxonomy:TermSet**

表示称为 “TermSet” 的分层或平面对象集。

顾名思义，TermSet 是 [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) 的集合。 [TermStore](/dotnet/api/microsoft.sharepoint.taxonomy.termstore) 中的 [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) 必须属于 [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset)。 没有 [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) 可以独立存在。

定义 [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset) 的语法如下：

```SKOS
ex:TermSetA    a    sharepoint-taxonomy:TermSet;
    sharepoint-taxonomy:termSetName    “TermSet A";
    sharepoint-taxonomy:isAvailableForTagging    “true”^^xsd:Boolean;
    sharepoint-taxonomy:hasTopLevelTerm    Ex:Term A.
```

[TermSets](/dotnet/api/microsoft.sharepoint.taxonomy.termset) 是按逻辑在 [TermGroups](/dotnet/api/microsoft.sharepoint.taxonomy.group) 中分组的。。 用于定义 [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset) 的必填字段为：

- sharepoint-taxonomy:termSetName

如果提供的 termSetName 在 [TermGroup](/dotnet/api/microsoft.sharepoint.taxonomy.group) 中不是唯一，则 SharePoint 会在名称结尾处附加一个数字，以保持 termSetName 的唯一性。

**sharepoint-taxonomy:hasTopLevelTerm**

SharePoint 使用此属性在 [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset) 中映射最顶端的 [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term)，这是 [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.term) 中 [Term](/dotnet/api/microsoft.sharepoint.taxonomy.termset) 的层次结构入口点。这是 sharepoint-taxonomy:topLevelTermOf 的反向关系。

用于定义这种情况的语法如下所示：

```SKOS
ex:TermSetA    sharepoint-taxonomy:hasTopLevelTerm    ex:TermA.
```

> [!NOTE]
> 你无法定义父级 [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) 的顶级 [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term)。

**sharepoint-taxonomy:topLevelTermOf**

Sharepoint-taxonomy:topLevelTermOf 是 sharepoint-taxonomy:hasTopLevelTerm 的翻面

用于定义这种情况的语法如下所示：

```SKOS
ex:TermA    sharepoint-taxonomy:topLevelTermOf    ex:TermSetA.
```

**sharepoint-taxonomy:inTermSet**

使用此操作将 [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) 映射到 [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset)。 [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) 只能存在于单个 [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset)中。 [定义术语](https://github.com/MicrosoftDocs/microsoft-365-docs-pr/blob/3a3cd54dd076b18bdff1d43b3e342897f8704c23/microsoft-365/contentunderstanding/skos-format-reference.md#term)时，SharePoint 需要此属性。

## <a name="required-labels"></a>需要的标签

组织可能希望在开始使用托管元数据之前执行周密的规划。 必须执行的计划量取决于分类的正式程度。 它还取决于你希望对元数据施加多少控制。 在层次结构的每个级别，需配置 Term 或 TermSet 所需的标签。

一个 Term 可以具有默认语言中的一个或多个标签，以及非默认语言的零个或多个标签。 如果术语在某种语言中拥有标签，则其中一个标签必须是默认标签。

**sharepoint-taxonomy:defaultLabel**

将此默认词法标签用于 [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term)，这是 [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) 所需的参数。用于直观地表示 [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term)。

定义 defaultLabel 的语法如下：

```SKOS
ex:TermA    sharepoint-taxonomy:defaultLabel    “Term A”@en-us.
```

DefaultLabel 包含两个部分，即字符串和语言标记。 该语言必须是 [TermStore](/dotnet/api/microsoft.sharepoint.taxonomy.termstore) 中的其中一个工作语言。 在相同的分层级别中，defaultLabel 对于同一 [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset) 中的所有 [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) 来说必须是唯一的。

**sharepoint-taxonomy:termSetName**

获取和设置当前 TermSet 对象的名称。

这是 [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset) 在 [TermStore](/dotnet/api/microsoft.sharepoint.taxonomy.termstore) 工作语言的词法标签。 这是 [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset) 所需的参数。 用于以可视方式表示 [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset)。

定义 termSetName 的语法如下：

```SKOS
ex:TermA    sharepoint-taxonomy:TermSetName    “Term Set A”@en-us.
```

**sharepoint-taxonomy:propertyName**

获取和设置当前 TermSet 对象的属性名称。

这是 sharepoint-taxonomy:SharedCustomPropertyForTerm, sharepoint-taxonomy:LocalCustomPropertyForTerm and sharepoint-taxonomy:CustomPropertyForTermSet 在 [TermStore](/dotnet/api/microsoft.sharepoint.taxonomy.termstore) 工作语言的词法标签。

sharepoint-taxonomy:propertyName 被当成是 CustomProperty 的密钥来对待。

定义 propetyName 的语法如下：

```SKOS
ex:SharedCustomProperty1    sharepoint-taxonomy:propertyName    “Shared Custom Property Key 1”@en-us.
```

## <a name="optional-labels"></a>可选标签

还可以向分类添加可选标签。

**sharepoint-taxonomy:otherLabel**

这是 [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) 的备用词法标签。

定义 otherLabel 的语法如下：

```SKOS
ex:TermA    sharepoint-taxonomy:otherLabel    “Term A”@en-us.
```

## <a name="semantic-relationships"></a>语义关系

分类具有层次结构关系，有时只是简单的“相关术语”关联关系，但是有些分类是“语义关系”或自定义创建的关系。

**sharepoint-taxonomy:parent**

这将 [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) 与另一个 [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) 分层地相关联。[Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) 可以是 [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset) 的顶级 [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term)，但是如果不是的话，则必须拥有父级 [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term)。

定义父级的语法如下：

```SKOS
ex:TermA1    sharepoint-taxonomy:parent    ex:TermA.
```

这意味着 TermA 是父级，而 TermA 是孩子。

**sharepoint-taxonomy:child**

对象中包含一个或多个子级 TermSet 实例，可通过 TermSets 属性访问这些实例。 此类还提供创建新子级 TermSet 对象的方法。 组中指定了用于编辑子 Term 和 TermSet 实例的权限。

这将 [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) 与另一个 [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) 分层地相关联。

定义子级的语法如下：

```SKOS
ex:TermA    sharepoint-taxonomy:child    ex:TermA1.
```

这意味着 TermA 是父级，而 TermA 是子级。

## <a name="documentation-notes"></a>文档注释

本节讨论了 Microsoft.SharePoint.Taxonomy 命名空间中详细说明的分类。

**sharepoint-taxonomy:description**

下面是对任何 [SharePoint 分类](/dotnet/api/microsoft.sharepoint.taxonomy) 词汇表实体的详细说明。

用于添加说明的语法为：

```SKOS
ex:TermA    sharepoint-taxonomy:description    “Term A is the top level term of TermSetA”@en-us.
```

## <a name="custom-properties"></a>自定义属性

从只读字典中获取当前 Term 对象的自定义属性对象的集合。

“自定义属性”是可以为 [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) 或 [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset) 定义的密钥值配对，进一步完善 [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) 或 [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset) 的说明。 SharePoint 借助 propertyName 来指定自定义属性的密钥。

**sharepoint-taxonomy:CustomPropertyForTermSet**

用于定义这种情况的语法如下所示：

```SKOS
ex:CustomProp1    rdf:type    sharepoint-taxonomy:CustomPropertyForTermSet;
    sharepoint-taxonomy:propertyName “Colour”.

ex:TermSetA    ex:CustomProp1    “Red”@en-us.
```

**sharepoint-taxonomy:SharedCustomPropertyForTerm**

如果需要将 [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) 的自定义属性与 [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) 一起执行的话，当你在其他位置重复使用 [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) 时，则需要在 SharedCustomPropertyForTerm 下进行定义。

用于定义这种情况的语法如下所示：

```SKOS
ex:CustomProp2    rdf:type sharepoint-taxonomy:SharedCustomPropertyForTerm;
    sharepoint-taxonomy:propertyName “Length”.

ex:TermA    ex:CustomProp2    “5 cm”@en-us.
```
**sharepoint-taxonomy:LocalCustomPropertyForTerm**

如果 [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) 的自定义属性无需随 [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) 一起执行的话，当你在在其他位置重复使用 [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) 时，则需要在 LocalCustomPropertyForTerm 下进行定义。

用于定义这种情况的语法如下所示：

```SKOS
ex:CustomProp3    rdf:type sharepoint-taxonomy:LocalCustomPropertyForTerm;
    sharepoint-taxonomy:propertyName “width”.

ex:TermA    ex:CustomProp3    “5 cm”@en-us.
```

## <a name="data-properties"></a>数据属性

在层次结构的每个级别，可以配置特定的 Term 或 TermSet 的数据属性。

**sharepoint-taxonomy:isAvailableForTagging**

如果 [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) 或 [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset) 在 SharePoint 列表和库中可用的话，用这个来指定其。

此项的语法是：

```SKOS
ex:TermA    sharepoint-taxonomy:isAvailableForTagging     "true"^^xsd:Boolean;
```

## <a name="domain-and-range"></a>域和范围

下表介绍了 SharePoint 分类词汇表的域和范围。

|谓词/谓词|含义|域|Range|
|:--------------|:------|:-----|:----|
inTermSet|在术语集里|Term|Term Set|
inTermGroup|在术语组内|TermSet|TermGroup|
topLevelTermOf|是顶级术语|Term|TermSet|
hasTopLevelTerm|具有顶级术语|Term Set|Term|
termSetName|术语集具有名称|Term|纯字面意义|
defaultLabel|术语具有默认标签|Term|纯字面意义|
otherLabel|术语具有其他标签|Term|纯字面意义|
PropertyName|具有属性标签|SharedCustomPropertyForTerm, LocalCustomPropertyForTerm, CustomPropertyForTermSet |布尔，字符串，整数，小数，双|
|description|具有说明|全部|纯字面意义|
|parent|具有父级|Term|Term|
|Child|具有子级|Term|Term|
|isAvailableForTagging|可用于标记|术语、术语集|布尔值|
|SharedCustomPropertyForTerm|拥有共享的自定义属性|Term|布尔值、字符串、整数、小数、双|
|LocalCustomPropertyForTerm|具有本地自定义属性|Term|布尔值、字符串、整数、小数、双|
|CustomPropertyForTermSet|具有自定义属性|TermSet|布尔值、字符串、整数、小数、双|

[SharePoint 分类](/dotnet/api/microsoft.sharepoint.taxonomy) 不允许的 [SKOS](https://www.w3.org/TR/skos-primer/) 有效方案：

- 分层冗余 - [SKOS](https://www.w3.org/TR/skos-primer/) 概念可同时附加到多个更广泛的概念，但 sharepoint-taxonomy：Term 只能有一个 sharepoint-taxonomy:parent，因此循环依赖术语是不被允许的。
- SharePoint 分类中不允许使用孤立术语。每个 sharepoint-taxonomy：术语应具有 sharepoint-taxonomy：parent 或它应该是 sharepoint-taxonomy：topLevelTermOf a TermSet。
- SharePoint 分类不支持关联关系。
- SharePoint 分类仅允许 2 种类型的分层关系 – sharepoint-taxonomy:parent 和 sharepoint-Taxonomy:child.
- 不同于 [SKOS](https://www.w3.org/TR/skos-primer/)，SharePoint 分类词汇表中的分层关系只能使用同一 TermSet 中的 Term 建立。

## <a name="see-also"></a>另请参阅

[使用基于 SKOS 的格式导入术语集](import-term-set-skos.md)