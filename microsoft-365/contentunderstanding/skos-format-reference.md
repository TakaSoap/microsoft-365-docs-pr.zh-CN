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
localization_priority: Priority
description: SharePoint 分类的 SKOS 格式参考
ms.openlocfilehash: 4c08073f453ef0b6a224829b7d4cb4034b74ed14
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/30/2021
ms.locfileid: "53228731"
---
# <a name="skos-format-reference-for-sharepoint-taxonomy"></a><span data-ttu-id="8e9c3-103">SharePoint 分类的 SKOS 格式参考</span><span class="sxs-lookup"><span data-stu-id="8e9c3-103">SKOS format reference for SharePoint taxonomy</span></span>

<span data-ttu-id="8e9c3-104">本文包含用于表示 [SharePoint 分类](/dotnet/api/microsoft.sharepoint.taxonomy)，并且基于 [SKOS](https://www.w3.org/TR/skos-primer/) 的 RDF 词汇表。</span><span class="sxs-lookup"><span data-stu-id="8e9c3-104">This article includes RDF vocabulary used to represent [SharePoint taxonomy](/dotnet/api/microsoft.sharepoint.taxonomy) and is based on [SKOS](https://www.w3.org/TR/skos-primer/).</span></span> <span data-ttu-id="8e9c3-105">若要将此 RDF 语法序列化，请使用 RDF [TURTLE](https://www.w3.org/TR/turtle/)。</span><span class="sxs-lookup"><span data-stu-id="8e9c3-105">For serialization of this RDF syntax, use RDF [TURTLE](https://www.w3.org/TR/turtle/).</span></span>

<span data-ttu-id="8e9c3-106">下表显示了 [SharePoint 分类](/dotnet/api/microsoft.sharepoint.taxonomy) 词汇表的 [SKOS](https://www.w3.org/TR/skos-primer/) 等效项。</span><span class="sxs-lookup"><span data-stu-id="8e9c3-106">The following table shows the [SKOS](https://www.w3.org/TR/skos-primer/) equivalents for the [SharePoint taxonomy](/dotnet/api/microsoft.sharepoint.taxonomy) vocabulary.</span></span> <span data-ttu-id="8e9c3-107">SharePoint 不支持没有 SharePoint 分类等效项的 [SKOS](https://www.w3.org/TR/skos-primer/) 值。</span><span class="sxs-lookup"><span data-stu-id="8e9c3-107">SharePoint does not support [SKOS](https://www.w3.org/TR/skos-primer/) values that have no SharePoint taxonomy equivalent.</span></span>

|<span data-ttu-id="8e9c3-108">SharePoint 分类</span><span class="sxs-lookup"><span data-stu-id="8e9c3-108">SharePoint taxonomy</span></span>|<span data-ttu-id="8e9c3-109">SKOS 等效项</span><span class="sxs-lookup"><span data-stu-id="8e9c3-109">SKOS equivalent</span></span>|
|:-----------------|:--------------|
|<span data-ttu-id="8e9c3-110">sharepoint-taxonomy:Term</span><span class="sxs-lookup"><span data-stu-id="8e9c3-110">sharepoint-taxonomy:Term</span></span>|<span data-ttu-id="8e9c3-111">skos:Concept</span><span class="sxs-lookup"><span data-stu-id="8e9c3-111">skos:Concept</span></span>|
|<span data-ttu-id="8e9c3-112">sharepoint-taxonomy:TermSet</span><span class="sxs-lookup"><span data-stu-id="8e9c3-112">sharepoint-taxonomy:TermSet</span></span>|<span data-ttu-id="8e9c3-113">skos:ConceptScheme</span><span class="sxs-lookup"><span data-stu-id="8e9c3-113">skos:ConceptScheme</span></span>|
|<span data-ttu-id="8e9c3-114">sharepoint-taxonomy:inTermSet</span><span class="sxs-lookup"><span data-stu-id="8e9c3-114">sharepoint-taxonomy:inTermSet</span></span>|<span data-ttu-id="8e9c3-115">skos:inScheme</span><span class="sxs-lookup"><span data-stu-id="8e9c3-115">skos:inScheme</span></span>|
|<span data-ttu-id="8e9c3-116">sharepoint-taxonomy:hasTopLevelTerm</span><span class="sxs-lookup"><span data-stu-id="8e9c3-116">sharepoint-taxonomy:hasTopLevelTerm</span></span>|<span data-ttu-id="8e9c3-117">skos:hasTopConcept</span><span class="sxs-lookup"><span data-stu-id="8e9c3-117">skos:hasTopConcept</span></span>|
|<span data-ttu-id="8e9c3-118">sharepoint-taxonomy:topLevelTermOf</span><span class="sxs-lookup"><span data-stu-id="8e9c3-118">sharepoint-taxonomy:topLevelTermOf</span></span>|<span data-ttu-id="8e9c3-119">skos:topConceptOf</span><span class="sxs-lookup"><span data-stu-id="8e9c3-119">skos:topConceptOf</span></span>|
|<span data-ttu-id="8e9c3-120">sharepoint-taxonomy:defaultLabel</span><span class="sxs-lookup"><span data-stu-id="8e9c3-120">sharepoint-taxonomy:defaultLabel</span></span>|<span data-ttu-id="8e9c3-121">skos:prefLabel</span><span class="sxs-lookup"><span data-stu-id="8e9c3-121">skos:prefLabel</span></span>|
|<span data-ttu-id="8e9c3-122">sharepoint-taxonomy:termSetName</span><span class="sxs-lookup"><span data-stu-id="8e9c3-122">sharepoint-taxonomy:termSetName</span></span>|<span data-ttu-id="8e9c3-123">skos:prefLabel</span><span class="sxs-lookup"><span data-stu-id="8e9c3-123">skos:prefLabel</span></span>|
|<span data-ttu-id="8e9c3-124">sharepoint-taxonomy:propertyName</span><span class="sxs-lookup"><span data-stu-id="8e9c3-124">sharepoint-taxonomy:propertyName</span></span>|<span data-ttu-id="8e9c3-125">skos:prefLabel</span><span class="sxs-lookup"><span data-stu-id="8e9c3-125">skos:prefLabel</span></span>|
|<span data-ttu-id="8e9c3-126">sharepoint-taxonomy:otherLabel</span><span class="sxs-lookup"><span data-stu-id="8e9c3-126">sharepoint-taxonomy:otherLabel</span></span>|<span data-ttu-id="8e9c3-127">skos:altLabel</span><span class="sxs-lookup"><span data-stu-id="8e9c3-127">skos:altLabel</span></span>|
|<span data-ttu-id="8e9c3-128">sharepoint-taxonomy:description</span><span class="sxs-lookup"><span data-stu-id="8e9c3-128">sharepoint-taxonomy:description</span></span>|<span data-ttu-id="8e9c3-129">skos:definition</span><span class="sxs-lookup"><span data-stu-id="8e9c3-129">skos:definition</span></span>|
|<span data-ttu-id="8e9c3-130">sharepoint-taxonomy:parent</span><span class="sxs-lookup"><span data-stu-id="8e9c3-130">sharepoint-taxonomy:parent</span></span>|<span data-ttu-id="8e9c3-131">skos:broader</span><span class="sxs-lookup"><span data-stu-id="8e9c3-131">skos:broader</span></span>|
|<span data-ttu-id="8e9c3-132">sharepoint-taxonomy:child</span><span class="sxs-lookup"><span data-stu-id="8e9c3-132">sharepoint-taxonomy:child</span></span>|<span data-ttu-id="8e9c3-133">skos:narrower</span><span class="sxs-lookup"><span data-stu-id="8e9c3-133">skos:narrower</span></span>|

<span data-ttu-id="8e9c3-134">下表显示从 [OWL](https://www.w3.org/TR/owl2-primer/) 派生的 SharePoint 分类词汇表的实体。</span><span class="sxs-lookup"><span data-stu-id="8e9c3-134">The following table displays the entities of the SharePoint taxonomy vocabulary derived from [OWL](https://www.w3.org/TR/owl2-primer/).</span></span>

|<span data-ttu-id="8e9c3-135">SharePoint 分类词汇表</span><span class="sxs-lookup"><span data-stu-id="8e9c3-135">SharePoint taxonomy vocabulary</span></span>|<span data-ttu-id="8e9c3-136">派生自 OWL</span><span class="sxs-lookup"><span data-stu-id="8e9c3-136">Derived from OWL</span></span>|
|:-----------------------------|:----------------------|
|<span data-ttu-id="8e9c3-137">sharepoint-taxonomy:isAvailableForTagging</span><span class="sxs-lookup"><span data-stu-id="8e9c3-137">sharepoint-taxonomy:isAvailableForTagging</span></span>|<span data-ttu-id="8e9c3-138">owl:datatypeproperty</span><span class="sxs-lookup"><span data-stu-id="8e9c3-138">owl:datatypeproperty</span></span>|
|<span data-ttu-id="8e9c3-139">sharepoint-taxonomy:SharedCustomPropertyForTerm</span><span class="sxs-lookup"><span data-stu-id="8e9c3-139">sharepoint-taxonomy:SharedCustomPropertyForTerm</span></span>|<span data-ttu-id="8e9c3-140">owl:ObjectProperty</span><span class="sxs-lookup"><span data-stu-id="8e9c3-140">owl:ObjectProperty</span></span>|
|<span data-ttu-id="8e9c3-141">sharepoint-taxonomy:LocalCustomPropertyForTerm</span><span class="sxs-lookup"><span data-stu-id="8e9c3-141">sharepoint-taxonomy:LocalCustomPropertyForTerm</span></span>|<span data-ttu-id="8e9c3-142">owl:ObjectProperty</span><span class="sxs-lookup"><span data-stu-id="8e9c3-142">owl:ObjectProperty</span></span>|
|<span data-ttu-id="8e9c3-143">sharepoint-taxonomy:CustomPropertyForTermSet</span><span class="sxs-lookup"><span data-stu-id="8e9c3-143">sharepoint-taxonomy:CustomPropertyForTermSet</span></span>|<span data-ttu-id="8e9c3-144">owl:ObjectProperty</span><span class="sxs-lookup"><span data-stu-id="8e9c3-144">owl:ObjectProperty</span></span>|

## <a name="sharepoint-taxonomy-vocabulary"></a><span data-ttu-id="8e9c3-145">SharePoint 分类词汇表</span><span class="sxs-lookup"><span data-stu-id="8e9c3-145">SharePoint taxonomy vocabulary</span></span>

<span data-ttu-id="8e9c3-p103">分类是正式分类系统。分类将描述某些内容的字词、标签和术语分组，然后将组排列到层次结构中。</span><span class="sxs-lookup"><span data-stu-id="8e9c3-p103">A taxonomy is a formal classification system. A taxonomy groups the words, labels, and terms that describe something, and then arranges the groups into a hierarchy.</span></span>

<span data-ttu-id="8e9c3-148">**sharepoint-taxonomy:Term**</span><span class="sxs-lookup"><span data-stu-id="8e9c3-148">**sharepoint-taxonomy:Term**</span></span>

<span data-ttu-id="8e9c3-149">表示托管元数据层次结构中的Term或“关键字”。</span><span class="sxs-lookup"><span data-stu-id="8e9c3-149">Represents a Term or a Keyword in a managed metadata hierarchy.</span></span>

<span data-ttu-id="8e9c3-150">[Term](/dotnet/api/microsoft.sharepoint.taxonomy.term)是 SharePoint [TermStore](/dotnet/api/microsoft.sharepoint.taxonomy.termstore) 的原子单元。</span><span class="sxs-lookup"><span data-stu-id="8e9c3-150">A [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) is the atomic unit of a SharePoint [TermStore](/dotnet/api/microsoft.sharepoint.taxonomy.termstore).</span></span> <span data-ttu-id="8e9c3-151">每个[Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) 都隶属于归属 [TermGroup](/dotnet/api/microsoft.sharepoint.taxonomy.group) 的 [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset)。</span><span class="sxs-lookup"><span data-stu-id="8e9c3-151">Each [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) belongs to a [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset) that belongs to a [TermGroup](/dotnet/api/microsoft.sharepoint.taxonomy.group).</span></span>

<span data-ttu-id="8e9c3-152">定义 [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) 的语法如下所示：</span><span class="sxs-lookup"><span data-stu-id="8e9c3-152">The syntax to define a [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) is as follows:</span></span>

```SKOS
ex:TermA    a    sharepoint-taxonomy:Term;
    sharepoint-taxonomy:inTermSet    ex:TermSetA;
    sharepoint-taxonomy:topLevelTermOf    ex:TermSetA;
    sharepoint-taxonomy:child    ex:TermA1;
    sharepoint-taxonomy:isAvailableForTagging    “true”^^xsd:Boolean;
    sharePoint-taxonomy:defaultLabel    “Term A”@en-us.
```

<span data-ttu-id="8e9c3-153">[Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) 强制性地存在于 [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset) 内。</span><span class="sxs-lookup"><span data-stu-id="8e9c3-153">A [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) compulsorily exists within a [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> <span data-ttu-id="8e9c3-154">DefaultLabel 是 [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) 显示在直观呈现方式中的名称。。</span><span class="sxs-lookup"><span data-stu-id="8e9c3-154">DefaultLabel is the name of the [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) as it appears in the visual representation.</span></span> <span data-ttu-id="8e9c3-155">定义 [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) 所需的字段包括：</span><span class="sxs-lookup"><span data-stu-id="8e9c3-155">The required fields for defining a [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) include:</span></span>

- <span data-ttu-id="8e9c3-156">sharepoint-taxonomy:defaultLabel</span><span class="sxs-lookup"><span data-stu-id="8e9c3-156">sharepoint-taxonomy:defaultLabel</span></span>
- <span data-ttu-id="8e9c3-157">sharepoint-taxonomy:inTermSet</span><span class="sxs-lookup"><span data-stu-id="8e9c3-157">sharepoint-taxonomy:inTermSet</span></span>

<span data-ttu-id="8e9c3-158">[Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) 可以：</span><span class="sxs-lookup"><span data-stu-id="8e9c3-158">A [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) can:</span></span>

- <span data-ttu-id="8e9c3-159">可与另一个 [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) 进行分层，前提是两个 [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) 都属于同一 [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset)。</span><span class="sxs-lookup"><span data-stu-id="8e9c3-159">Be hierarchically related to another [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) that is provided both the [Terms](/dotnet/api/microsoft.sharepoint.taxonomy.term) belong to the same [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span>
- <span data-ttu-id="8e9c3-160">具有多个子级 [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term)，但仅一个父级 [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term)。</span><span class="sxs-lookup"><span data-stu-id="8e9c3-160">Have multiple child [Terms](/dotnet/api/microsoft.sharepoint.taxonomy.term), but only a single parent [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span>
- <span data-ttu-id="8e9c3-161">如果是某个 [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset) 的 topLevelTermOf 术语的话，则可以不必由父级 [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) 定义。</span><span class="sxs-lookup"><span data-stu-id="8e9c3-161">Not have a parent [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) defined, if it is a topLevelTermOf a [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span>
- <span data-ttu-id="8e9c3-162">在每个 [TermStore](/dotnet/api/microsoft.sharepoint.taxonomy.termstore) 工作语言中拥有一个 defaultLabel。</span><span class="sxs-lookup"><span data-stu-id="8e9c3-162">Have one defaultLabel, per [TermStore](/dotnet/api/microsoft.sharepoint.taxonomy.termstore) working language.</span></span>
- <span data-ttu-id="8e9c3-163">不存在（如果它既不包含父级 [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term)，也不是某个 [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset) 的 topLevelTermOf 术语的话）。</span><span class="sxs-lookup"><span data-stu-id="8e9c3-163">Not exist if it neither contains a parent [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term), nor is the topLevelTermOf a [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span>
- <span data-ttu-id="8e9c3-164">在相同的分层级别中只拥有一个唯一的 defaultLabel。</span><span class="sxs-lookup"><span data-stu-id="8e9c3-164">Have only a unique defaultLabel in the same hierarchical level.</span></span>

<span data-ttu-id="8e9c3-165">**sharepoint-taxonomy:TermSet**</span><span class="sxs-lookup"><span data-stu-id="8e9c3-165">**sharepoint-taxonomy:TermSet**</span></span>

<span data-ttu-id="8e9c3-166">表示称为 “TermSet” 的分层或平面对象集。</span><span class="sxs-lookup"><span data-stu-id="8e9c3-166">Represents a hierarchical or flat set of Term objects known as a "TermSet".</span></span>

<span data-ttu-id="8e9c3-167">顾名思义，TermSet 是 [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) 的集合。</span><span class="sxs-lookup"><span data-stu-id="8e9c3-167">As the name suggests, TermSet is a set of [Terms](/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span> <span data-ttu-id="8e9c3-168">[TermStore](/dotnet/api/microsoft.sharepoint.taxonomy.termstore) 中的 [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) 必须属于 [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset)。</span><span class="sxs-lookup"><span data-stu-id="8e9c3-168">A [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) in a [TermStore](/dotnet/api/microsoft.sharepoint.taxonomy.termstore) must belong to a [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> <span data-ttu-id="8e9c3-169">没有 [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) 可以独立存在。</span><span class="sxs-lookup"><span data-stu-id="8e9c3-169">No [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) can exist independently.</span></span>

<span data-ttu-id="8e9c3-170">定义 [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset) 的语法如下：</span><span class="sxs-lookup"><span data-stu-id="8e9c3-170">The syntax to define a [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset) is:</span></span>

```SKOS
ex:TermSetA    a    sharepoint-taxonomy:TermSet;
    sharepoint-taxonomy:termSetName    “TermSet A";
    sharepoint-taxonomy:isAvailableForTagging    “true”^^xsd:Boolean;
    sharepoint-taxonomy:hasTopLevelTerm    Ex:Term A.
```

<span data-ttu-id="8e9c3-171">[TermSets](/dotnet/api/microsoft.sharepoint.taxonomy.termset) 是按逻辑在 [TermGroups](/dotnet/api/microsoft.sharepoint.taxonomy.group) 中分组的。。</span><span class="sxs-lookup"><span data-stu-id="8e9c3-171">[TermSets](/dotnet/api/microsoft.sharepoint.taxonomy.termset) are logically grouped together in [TermGroups](/dotnet/api/microsoft.sharepoint.taxonomy.group).</span></span> <span data-ttu-id="8e9c3-172">用于定义 [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset) 的必填字段为：</span><span class="sxs-lookup"><span data-stu-id="8e9c3-172">The required field for defining a [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset) is:</span></span>

- <span data-ttu-id="8e9c3-173">sharepoint-taxonomy:termSetName</span><span class="sxs-lookup"><span data-stu-id="8e9c3-173">sharepoint-taxonomy:termSetName</span></span>

<span data-ttu-id="8e9c3-174">如果提供的 termSetName 在 [TermGroup](/dotnet/api/microsoft.sharepoint.taxonomy.group) 中不是唯一，则 SharePoint 会在名称结尾处附加一个数字，以保持 termSetName 的唯一性。</span><span class="sxs-lookup"><span data-stu-id="8e9c3-174">In the case of the termSetName provided is not unique within the [TermGroup](/dotnet/api/microsoft.sharepoint.taxonomy.group), SharePoint appends a number at the end of the name to maintain the uniqueness of termSetName(s).</span></span>

<span data-ttu-id="8e9c3-175">**sharepoint-taxonomy:hasTopLevelTerm**</span><span class="sxs-lookup"><span data-stu-id="8e9c3-175">**sharepoint-taxonomy:hasTopLevelTerm**</span></span>

<span data-ttu-id="8e9c3-176">SharePoint 使用此属性在 [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset) 中映射最顶端的 [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term)，这是 [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.term) 中 [Term](/dotnet/api/microsoft.sharepoint.taxonomy.termset) 的层次结构入口点。</span><span class="sxs-lookup"><span data-stu-id="8e9c3-176">SharePoint uses this property to map the top most [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) in the [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset), which is the entry point to the hierarchy of [Terms](/dotnet/api/microsoft.sharepoint.taxonomy.term) in a [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> <span data-ttu-id="8e9c3-177">这是 sharepoint-taxonomy:topLevelTermOf 的反向关系。</span><span class="sxs-lookup"><span data-stu-id="8e9c3-177">This is an inverse relation to sharepoint-taxonomy:topLevelTermOf.</span></span>

<span data-ttu-id="8e9c3-178">用于定义这种情况的语法如下所示：</span><span class="sxs-lookup"><span data-stu-id="8e9c3-178">The syntax to define this is:</span></span>

```SKOS
ex:TermSetA    sharepoint-taxonomy:hasTopLevelTerm    ex:TermA.
```

> [!NOTE]
> <span data-ttu-id="8e9c3-179">你无法定义父级 [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) 的顶级 [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term)。</span><span class="sxs-lookup"><span data-stu-id="8e9c3-179">You cannot define the top level [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) of a parent [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span>

<span data-ttu-id="8e9c3-180">**sharepoint-taxonomy:topLevelTermOf**</span><span class="sxs-lookup"><span data-stu-id="8e9c3-180">**sharepoint-taxonomy:topLevelTermOf**</span></span>

<span data-ttu-id="8e9c3-181">Sharepoint-taxonomy:topLevelTermOf 是 sharepoint-taxonomy:hasTopLevelTerm 的翻面</span><span class="sxs-lookup"><span data-stu-id="8e9c3-181">Sharepoint-taxonomy:topLevelTermOf is the inverse of sharepoint-taxonomy:hasTopLevelTerm</span></span>

<span data-ttu-id="8e9c3-182">用于定义这种情况的语法如下所示：</span><span class="sxs-lookup"><span data-stu-id="8e9c3-182">The syntax to define this is:</span></span>

```SKOS
ex:TermA    sharepoint-taxonomy:topLevelTermOf    ex:TermSetA.
```

<span data-ttu-id="8e9c3-183">**sharepoint-taxonomy:inTermSet**</span><span class="sxs-lookup"><span data-stu-id="8e9c3-183">**sharepoint-taxonomy:inTermSet**</span></span>

<span data-ttu-id="8e9c3-184">使用此操作将 [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) 映射到 [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset)。</span><span class="sxs-lookup"><span data-stu-id="8e9c3-184">Use this to map a [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) to a [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> <span data-ttu-id="8e9c3-185">[Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) 只能存在于单个 [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset)中。</span><span class="sxs-lookup"><span data-stu-id="8e9c3-185">A [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) can only exist in a single [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> <span data-ttu-id="8e9c3-186">[定义术语](https://github.com/MicrosoftDocs/microsoft-365-docs-pr/blob/3a3cd54dd076b18bdff1d43b3e342897f8704c23/microsoft-365/contentunderstanding/skos-format-reference.md#term)时，SharePoint 需要此属性。</span><span class="sxs-lookup"><span data-stu-id="8e9c3-186">SharePoint requires this property when [defining a term](https://github.com/MicrosoftDocs/microsoft-365-docs-pr/blob/3a3cd54dd076b18bdff1d43b3e342897f8704c23/microsoft-365/contentunderstanding/skos-format-reference.md#term).</span></span>

## <a name="required-labels"></a><span data-ttu-id="8e9c3-187">需要的标签</span><span class="sxs-lookup"><span data-stu-id="8e9c3-187">Required labels</span></span>

<span data-ttu-id="8e9c3-188">组织可能希望在开始使用托管元数据之前执行周密的规划。</span><span class="sxs-lookup"><span data-stu-id="8e9c3-188">Your organization may want to do careful planning before you start to use managed metadata.</span></span> <span data-ttu-id="8e9c3-189">必须执行的计划量取决于分类的正式程度。</span><span class="sxs-lookup"><span data-stu-id="8e9c3-189">The amount of planning that you must do depends on how formal your taxonomy is.</span></span> <span data-ttu-id="8e9c3-190">它还取决于你希望对元数据施加多少控制。</span><span class="sxs-lookup"><span data-stu-id="8e9c3-190">It also depends on how much control that you want to impose on metadata.</span></span> <span data-ttu-id="8e9c3-191">在层次结构的每个级别，需配置 Term 或 TermSet 所需的标签。</span><span class="sxs-lookup"><span data-stu-id="8e9c3-191">At each level of the hierarchy, you need to configure required labels for a Term or TermSet.</span></span>

<span data-ttu-id="8e9c3-192">一个 Term 可以具有默认语言中的一个或多个标签，以及非默认语言的零个或多个标签。</span><span class="sxs-lookup"><span data-stu-id="8e9c3-192">A Term can have one or more labels in the default language, and zero or more labels in the non-default language.</span></span> <span data-ttu-id="8e9c3-193">如果术语在某种语言中拥有标签，则其中一个标签必须是默认标签。</span><span class="sxs-lookup"><span data-stu-id="8e9c3-193">If the term has labels in a language, one of the labels must be the default label.</span></span>

<span data-ttu-id="8e9c3-194">**sharepoint-taxonomy:defaultLabel**</span><span class="sxs-lookup"><span data-stu-id="8e9c3-194">**sharepoint-taxonomy:defaultLabel**</span></span>

<span data-ttu-id="8e9c3-195">将此默认词法标签用于 [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term)，这是 [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) 所需的参数。</span><span class="sxs-lookup"><span data-stu-id="8e9c3-195">Use this default lexical label for a [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) that is a required parameter for a [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span> <span data-ttu-id="8e9c3-196">用于以直观方式表示 [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term)。</span><span class="sxs-lookup"><span data-stu-id="8e9c3-196">Use to visually representing the [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span>

<span data-ttu-id="8e9c3-197">定义 defaultLabel 的语法如下：</span><span class="sxs-lookup"><span data-stu-id="8e9c3-197">The syntax to define a defaultLabel is:</span></span>

```SKOS
ex:TermA    sharepoint-taxonomy:defaultLabel    “Term A”@en-us.
```

<span data-ttu-id="8e9c3-198">DefaultLabel 包含两个部分，即字符串和语言标记。</span><span class="sxs-lookup"><span data-stu-id="8e9c3-198">The defaultLabel contains two parts to it – the string and the language tag.</span></span> <span data-ttu-id="8e9c3-199">该语言必须是 [TermStore](/dotnet/api/microsoft.sharepoint.taxonomy.termstore) 中的其中一个工作语言。</span><span class="sxs-lookup"><span data-stu-id="8e9c3-199">The language must be one of the [TermStore](/dotnet/api/microsoft.sharepoint.taxonomy.termstore) working languages.</span></span> <span data-ttu-id="8e9c3-200">在相同的分层级别中，defaultLabel 对于同一 [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset) 中的所有 [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) 来说必须是唯一的。</span><span class="sxs-lookup"><span data-stu-id="8e9c3-200">The defaultLabel must be unique for all [Terms](/dotnet/api/microsoft.sharepoint.taxonomy.term) in the same [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset), at the same hierarchical level.</span></span>

<span data-ttu-id="8e9c3-201">**sharepoint-taxonomy:termSetName**</span><span class="sxs-lookup"><span data-stu-id="8e9c3-201">**sharepoint-taxonomy:termSetName**</span></span>

<span data-ttu-id="8e9c3-202">获取和设置当前 TermSet 对象的名称。</span><span class="sxs-lookup"><span data-stu-id="8e9c3-202">Gets and sets the name for the current TermSet object.</span></span>

<span data-ttu-id="8e9c3-203">这是 [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset) 在 [TermStore](/dotnet/api/microsoft.sharepoint.taxonomy.termstore) 工作语言的词法标签。</span><span class="sxs-lookup"><span data-stu-id="8e9c3-203">This the lexical label for a [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset), in a [TermStore](/dotnet/api/microsoft.sharepoint.taxonomy.termstore) working language.</span></span> <span data-ttu-id="8e9c3-204">这是 [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset) 所需的参数。</span><span class="sxs-lookup"><span data-stu-id="8e9c3-204">This is a required parameter for a [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> <span data-ttu-id="8e9c3-205">用于以可视方式表示 [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset)。</span><span class="sxs-lookup"><span data-stu-id="8e9c3-205">Use to visually representing a [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span>

<span data-ttu-id="8e9c3-206">定义 termSetName 的语法如下：</span><span class="sxs-lookup"><span data-stu-id="8e9c3-206">The syntax to define a termSetName is:</span></span>

```SKOS
ex:TermA    sharepoint-taxonomy:TermSetName    “Term Set A”@en-us.
```

<span data-ttu-id="8e9c3-207">**sharepoint-taxonomy:propertyName**</span><span class="sxs-lookup"><span data-stu-id="8e9c3-207">**sharepoint-taxonomy:propertyName**</span></span>

<span data-ttu-id="8e9c3-208">获取和设置当前 TermSet 对象的属性名称。</span><span class="sxs-lookup"><span data-stu-id="8e9c3-208">Gets and sets the property name for the current TermSet object.</span></span>

<span data-ttu-id="8e9c3-209">这是 sharepoint-taxonomy:SharedCustomPropertyForTerm, sharepoint-taxonomy:LocalCustomPropertyForTerm and sharepoint-taxonomy:CustomPropertyForTermSet 在 [TermStore](/dotnet/api/microsoft.sharepoint.taxonomy.termstore) 工作语言的词法标签。</span><span class="sxs-lookup"><span data-stu-id="8e9c3-209">This is the lexical label for a sharepoint-taxonomy:SharedCustomPropertyForTerm, sharepoint-taxonomy:LocalCustomPropertyForTerm and sharepoint-taxonomy:CustomPropertyForTermSet in a [TermStore](/dotnet/api/microsoft.sharepoint.taxonomy.termstore) working language.</span></span>

<span data-ttu-id="8e9c3-210">sharepoint-taxonomy:propertyName 被当成是 CustomProperty 的密钥来对待。</span><span class="sxs-lookup"><span data-stu-id="8e9c3-210">The sharepoint-taxonomy:propertyName is treated as the key of the CustomProperty.</span></span>

<span data-ttu-id="8e9c3-211">定义 propetyName 的语法如下：</span><span class="sxs-lookup"><span data-stu-id="8e9c3-211">The syntax to define a propetyName is:</span></span>

```SKOS
ex:SharedCustomProperty1    sharepoint-taxonomy:propertyName    “Shared Custom Property Key 1”@en-us.
```

## <a name="optional-labels"></a><span data-ttu-id="8e9c3-212">可选标签</span><span class="sxs-lookup"><span data-stu-id="8e9c3-212">Optional labels</span></span>

<span data-ttu-id="8e9c3-213">还可以向分类添加可选标签。</span><span class="sxs-lookup"><span data-stu-id="8e9c3-213">You can also add optional labels to your taxonomy.</span></span>

<span data-ttu-id="8e9c3-214">**sharepoint-taxonomy:otherLabel**</span><span class="sxs-lookup"><span data-stu-id="8e9c3-214">**sharepoint-taxonomy:otherLabel**</span></span>

<span data-ttu-id="8e9c3-215">这是 [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) 的备用词法标签。</span><span class="sxs-lookup"><span data-stu-id="8e9c3-215">This is the alternate lexical label for a [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span>

<span data-ttu-id="8e9c3-216">定义 otherLabel 的语法如下：</span><span class="sxs-lookup"><span data-stu-id="8e9c3-216">The syntax to define an otherLabel is:</span></span>

```SKOS
ex:TermA    sharepoint-taxonomy:otherLabel    “Term A”@en-us.
```

## <a name="semantic-relationships"></a><span data-ttu-id="8e9c3-217">语义关系</span><span class="sxs-lookup"><span data-stu-id="8e9c3-217">Semantic relationships</span></span>

<span data-ttu-id="8e9c3-218">分类具有层次结构关系，有时只是简单的“相关术语”关联关系，但是有些分类是“语义关系”或自定义创建的关系。</span><span class="sxs-lookup"><span data-stu-id="8e9c3-218">Taxonomies have hierarchical and sometimes a simple “related term” associative relationship, but some have "semantic relationships" or custom-created relationships.</span></span>

<span data-ttu-id="8e9c3-219">**sharepoint-taxonomy:parent**</span><span class="sxs-lookup"><span data-stu-id="8e9c3-219">**sharepoint-taxonomy:parent**</span></span>

<span data-ttu-id="8e9c3-220">这将 [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) 与另一个 [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) 分层地相关联。</span><span class="sxs-lookup"><span data-stu-id="8e9c3-220">This hierarchically relates a [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) to another [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span> <span data-ttu-id="8e9c3-221">[Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) 可以是 [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset) 的顶级 [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term)，但是如果不是的话，则必须拥有父级 [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term)。</span><span class="sxs-lookup"><span data-stu-id="8e9c3-221">A [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) could be a top level [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) of a [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset), but in case it doesn’t it must have a parent [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span>

<span data-ttu-id="8e9c3-222">定义父级的语法如下：</span><span class="sxs-lookup"><span data-stu-id="8e9c3-222">The syntax to define a parent is:</span></span>

```SKOS
ex:TermA1    sharepoint-taxonomy:parent    ex:TermA.
```

<span data-ttu-id="8e9c3-223">这意味着 TermA 是父级，而 TermA 是孩子。</span><span class="sxs-lookup"><span data-stu-id="8e9c3-223">This means that TermA is the parent and  TermA is the child.</span></span>

<span data-ttu-id="8e9c3-224">**sharepoint-taxonomy:child**</span><span class="sxs-lookup"><span data-stu-id="8e9c3-224">**sharepoint-taxonomy:child**</span></span>

<span data-ttu-id="8e9c3-225">对象中包含一个或多个子级 TermSet 实例，可通过 TermSets 属性访问这些实例。</span><span class="sxs-lookup"><span data-stu-id="8e9c3-225">The object contains one or more child TermSet instances, and these can be accessed through the TermSets property.</span></span> <span data-ttu-id="8e9c3-226">此类还提供创建新子级 TermSet 对象的方法。</span><span class="sxs-lookup"><span data-stu-id="8e9c3-226">This class also provides methods for creating new child TermSet objects.</span></span> <span data-ttu-id="8e9c3-227">组中指定了用于编辑子 Term 和 TermSet 实例的权限。</span><span class="sxs-lookup"><span data-stu-id="8e9c3-227">Permissions for editing child Term and TermSet instances is specified on the group.</span></span>

<span data-ttu-id="8e9c3-228">这将 [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) 与另一个 [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) 分层地相关联。</span><span class="sxs-lookup"><span data-stu-id="8e9c3-228">This hierarchically relates a [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) to another [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span>

<span data-ttu-id="8e9c3-229">定义子级的语法如下：</span><span class="sxs-lookup"><span data-stu-id="8e9c3-229">The syntax to define a child is:</span></span>

```SKOS
ex:TermA    sharepoint-taxonomy:child    ex:TermA1.
```

<span data-ttu-id="8e9c3-230">这意味着 TermA 是父级，而 TermA 是子级。</span><span class="sxs-lookup"><span data-stu-id="8e9c3-230">This means that TermA is the parent and  TermA is the child.</span></span>

## <a name="documentation-notes"></a><span data-ttu-id="8e9c3-231">文档注释</span><span class="sxs-lookup"><span data-stu-id="8e9c3-231">Documentation notes</span></span>

<span data-ttu-id="8e9c3-232">本节讨论了 Microsoft.SharePoint.Taxonomy 命名空间中详细说明的分类。</span><span class="sxs-lookup"><span data-stu-id="8e9c3-232">This section discusses the taxonomy detailed in the Microsoft.SharePoint.Taxonomy Namespace.</span></span>

<span data-ttu-id="8e9c3-233">**sharepoint-taxonomy:description**</span><span class="sxs-lookup"><span data-stu-id="8e9c3-233">**sharepoint-taxonomy:description**</span></span>

<span data-ttu-id="8e9c3-234">下面是对任何 [SharePoint 分类](/dotnet/api/microsoft.sharepoint.taxonomy) 词汇表实体的详细说明。</span><span class="sxs-lookup"><span data-stu-id="8e9c3-234">This is a detailed explanation of any [SharePoint taxonomy](/dotnet/api/microsoft.sharepoint.taxonomy) vocabulary entity.</span></span>

<span data-ttu-id="8e9c3-235">用于添加说明的语法为：</span><span class="sxs-lookup"><span data-stu-id="8e9c3-235">The syntax to add a description is:</span></span>

```SKOS
ex:TermA    sharepoint-taxonomy:description    “Term A is the top level term of TermSetA”@en-us.
```

## <a name="custom-properties"></a><span data-ttu-id="8e9c3-236">自定义属性</span><span class="sxs-lookup"><span data-stu-id="8e9c3-236">Custom properties</span></span>

<span data-ttu-id="8e9c3-237">从只读字典中获取当前 Term 对象的自定义属性对象的集合。</span><span class="sxs-lookup"><span data-stu-id="8e9c3-237">Gets the collection of custom property objects for the current Term object from the read-only dictionary.</span></span>

<span data-ttu-id="8e9c3-238">“自定义属性”是可以为 [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) 或 [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset) 定义的密钥值配对，进一步完善 [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) 或 [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset) 的说明。</span><span class="sxs-lookup"><span data-stu-id="8e9c3-238">Custom Properties are key-values pairs that can be defined for a [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) or a [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset), to further the description of the [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) or a [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> <span data-ttu-id="8e9c3-239">SharePoint 借助 propertyName 来指定自定义属性的密钥。</span><span class="sxs-lookup"><span data-stu-id="8e9c3-239">SharePoint specifies the key of the custom property with the help of propertyName.</span></span>

<span data-ttu-id="8e9c3-240">**sharepoint-taxonomy:CustomPropertyForTermSet**</span><span class="sxs-lookup"><span data-stu-id="8e9c3-240">**sharepoint-taxonomy:CustomPropertyForTermSet**</span></span>

<span data-ttu-id="8e9c3-241">用于定义这种情况的语法如下所示：</span><span class="sxs-lookup"><span data-stu-id="8e9c3-241">The syntax to define this is:</span></span>

```SKOS
ex:CustomProp1    rdf:type    sharepoint-taxonomy:CustomPropertyForTermSet;
    sharepoint-taxonomy:propertyName “Colour”.

ex:TermSetA    ex:CustomProp1    “Red”@en-us.
```

<span data-ttu-id="8e9c3-242">**sharepoint-taxonomy:SharedCustomPropertyForTerm**</span><span class="sxs-lookup"><span data-stu-id="8e9c3-242">**sharepoint-taxonomy:SharedCustomPropertyForTerm**</span></span>

<span data-ttu-id="8e9c3-243">如果需要将 [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) 的自定义属性与 [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) 一起执行的话，当你在其他位置重复使用 [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) 时，则需要在 SharedCustomPropertyForTerm 下进行定义。</span><span class="sxs-lookup"><span data-stu-id="8e9c3-243">If the custom property for a [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) needs to be carried along with the [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term), when you reuse the [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) somewhere else, then you need to be define it under SharedCustomPropertyForTerm.</span></span>

<span data-ttu-id="8e9c3-244">用于定义这种情况的语法如下所示：</span><span class="sxs-lookup"><span data-stu-id="8e9c3-244">The syntax to define this is:</span></span>

``` SKOS
ex:CustomProp2    rdf:type sharepoint-taxonomy:SharedCustomPropertyForTerm;
    sharepoint-taxonomy:propertyName “Length”.

ex:TermA    ex:CustomProp2    “5 cm”@en-us.
```
<span data-ttu-id="8e9c3-245">**sharepoint-taxonomy:LocalCustomPropertyForTerm**</span><span class="sxs-lookup"><span data-stu-id="8e9c3-245">**sharepoint-taxonomy:LocalCustomPropertyForTerm**</span></span>

<span data-ttu-id="8e9c3-246">如果 [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) 的自定义属性无需随 [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) 一起执行的话，当你在在其他位置重复使用 [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) 时，则需要在 LocalCustomPropertyForTerm 下进行定义。</span><span class="sxs-lookup"><span data-stu-id="8e9c3-246">If the custom property for a [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) does not need to be carried along with the [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term), when you reuse the [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) somewhere else, then you need to define it under LocalCustomPropertyForTerm.</span></span>

<span data-ttu-id="8e9c3-247">用于定义这种情况的语法如下所示：</span><span class="sxs-lookup"><span data-stu-id="8e9c3-247">The syntax to define this is:</span></span>

```SKOS
ex:CustomProp3    rdf:type sharepoint-taxonomy:LocalCustomPropertyForTerm;
    sharepoint-taxonomy:propertyName “width”.

ex:TermA    ex:CustomProp3    “5 cm”@en-us.
```

## <a name="data-properties"></a><span data-ttu-id="8e9c3-248">数据属性</span><span class="sxs-lookup"><span data-stu-id="8e9c3-248">Data properties</span></span>

<span data-ttu-id="8e9c3-249">在层次结构的每个级别，可以配置特定的 Term 或 TermSet 的数据属性。</span><span class="sxs-lookup"><span data-stu-id="8e9c3-249">At each level of the hierarchy, you can configure specific data properties for a Term or TermSet.</span></span>

<span data-ttu-id="8e9c3-250">**sharepoint-taxonomy:isAvailableForTagging**</span><span class="sxs-lookup"><span data-stu-id="8e9c3-250">**sharepoint-taxonomy:isAvailableForTagging**</span></span>

<span data-ttu-id="8e9c3-251">如果 [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) 或 [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset) 在 SharePoint 列表和库中可用的话，用这个来指定其。</span><span class="sxs-lookup"><span data-stu-id="8e9c3-251">Use this to specify if a [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) or a [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset) available in SharePoint Lists and Libraries.</span></span>

<span data-ttu-id="8e9c3-252">此项的语法是：</span><span class="sxs-lookup"><span data-stu-id="8e9c3-252">The syntax for this is:</span></span>

```SKOS
ex:TermA    sharepoint-taxonomy:isAvailableForTagging     "true"^^xsd:Boolean;
```

## <a name="domain-and-range"></a><span data-ttu-id="8e9c3-253">域和范围</span><span class="sxs-lookup"><span data-stu-id="8e9c3-253">Domain and range</span></span>

<span data-ttu-id="8e9c3-254">下表介绍了 SharePoint 分类词汇表的域和范围。</span><span class="sxs-lookup"><span data-stu-id="8e9c3-254">The table below describes the domain and range of SharePoint taxonomy vocabulary.</span></span>

|<span data-ttu-id="8e9c3-255">谓词/谓词</span><span class="sxs-lookup"><span data-stu-id="8e9c3-255">Predicates/verb</span></span>|<span data-ttu-id="8e9c3-256">含义</span><span class="sxs-lookup"><span data-stu-id="8e9c3-256">Meaning</span></span>|<span data-ttu-id="8e9c3-257">域</span><span class="sxs-lookup"><span data-stu-id="8e9c3-257">Domain</span></span>|<span data-ttu-id="8e9c3-258">Range</span><span class="sxs-lookup"><span data-stu-id="8e9c3-258">Range</span></span>|
|:--------------|:------|:-----|:----|
<span data-ttu-id="8e9c3-259">inTermSet</span><span class="sxs-lookup"><span data-stu-id="8e9c3-259">inTermSet</span></span>|<span data-ttu-id="8e9c3-260">在术语集里</span><span class="sxs-lookup"><span data-stu-id="8e9c3-260">In term set</span></span>|<span data-ttu-id="8e9c3-261">Term</span><span class="sxs-lookup"><span data-stu-id="8e9c3-261">Term</span></span>|<span data-ttu-id="8e9c3-262">Term Set</span><span class="sxs-lookup"><span data-stu-id="8e9c3-262">Term Set</span></span>|
<span data-ttu-id="8e9c3-263">inTermGroup</span><span class="sxs-lookup"><span data-stu-id="8e9c3-263">inTermGroup</span></span>|<span data-ttu-id="8e9c3-264">在术语组内</span><span class="sxs-lookup"><span data-stu-id="8e9c3-264">In term group</span></span>|<span data-ttu-id="8e9c3-265">TermSet</span><span class="sxs-lookup"><span data-stu-id="8e9c3-265">TermSet</span></span>|<span data-ttu-id="8e9c3-266">TermGroup</span><span class="sxs-lookup"><span data-stu-id="8e9c3-266">TermGroup</span></span>|
<span data-ttu-id="8e9c3-267">topLevelTermOf</span><span class="sxs-lookup"><span data-stu-id="8e9c3-267">topLevelTermOf</span></span>|<span data-ttu-id="8e9c3-268">是顶级术语</span><span class="sxs-lookup"><span data-stu-id="8e9c3-268">Is Top Level Term Of</span></span>|<span data-ttu-id="8e9c3-269">Term</span><span class="sxs-lookup"><span data-stu-id="8e9c3-269">Term</span></span>|<span data-ttu-id="8e9c3-270">TermSet</span><span class="sxs-lookup"><span data-stu-id="8e9c3-270">TermSet</span></span>|
<span data-ttu-id="8e9c3-271">hasTopLevelTerm</span><span class="sxs-lookup"><span data-stu-id="8e9c3-271">hasTopLevelTerm</span></span>|<span data-ttu-id="8e9c3-272">具有顶级术语</span><span class="sxs-lookup"><span data-stu-id="8e9c3-272">Has top level term</span></span>|<span data-ttu-id="8e9c3-273">Term Set</span><span class="sxs-lookup"><span data-stu-id="8e9c3-273">Term Set</span></span>|<span data-ttu-id="8e9c3-274">Term</span><span class="sxs-lookup"><span data-stu-id="8e9c3-274">Term</span></span>|
<span data-ttu-id="8e9c3-275">termSetName</span><span class="sxs-lookup"><span data-stu-id="8e9c3-275">termSetName</span></span>|<span data-ttu-id="8e9c3-276">术语集具有名称</span><span class="sxs-lookup"><span data-stu-id="8e9c3-276">Term set has Name</span></span>|<span data-ttu-id="8e9c3-277">Term</span><span class="sxs-lookup"><span data-stu-id="8e9c3-277">Term</span></span>|<span data-ttu-id="8e9c3-278">纯字面意义</span><span class="sxs-lookup"><span data-stu-id="8e9c3-278">Plain literal</span></span>|
<span data-ttu-id="8e9c3-279">defaultLabel</span><span class="sxs-lookup"><span data-stu-id="8e9c3-279">defaultLabel</span></span>|<span data-ttu-id="8e9c3-280">术语具有默认标签</span><span class="sxs-lookup"><span data-stu-id="8e9c3-280">Term has default label</span></span>|<span data-ttu-id="8e9c3-281">Term</span><span class="sxs-lookup"><span data-stu-id="8e9c3-281">Term</span></span>|<span data-ttu-id="8e9c3-282">纯字面意义</span><span class="sxs-lookup"><span data-stu-id="8e9c3-282">Plain literal</span></span>|
<span data-ttu-id="8e9c3-283">otherLabel</span><span class="sxs-lookup"><span data-stu-id="8e9c3-283">otherLabel</span></span>|<span data-ttu-id="8e9c3-284">术语具有其他标签</span><span class="sxs-lookup"><span data-stu-id="8e9c3-284">Term has other label</span></span>|<span data-ttu-id="8e9c3-285">Term</span><span class="sxs-lookup"><span data-stu-id="8e9c3-285">Term</span></span>|<span data-ttu-id="8e9c3-286">纯字面意义</span><span class="sxs-lookup"><span data-stu-id="8e9c3-286">Plain literal</span></span>|
<span data-ttu-id="8e9c3-287">PropertyName</span><span class="sxs-lookup"><span data-stu-id="8e9c3-287">propertyName</span></span>|<span data-ttu-id="8e9c3-288">具有属性标签</span><span class="sxs-lookup"><span data-stu-id="8e9c3-288">Has Property Label</span></span>|<span data-ttu-id="8e9c3-289">SharedCustomPropertyForTerm, LocalCustomPropertyForTerm, CustomPropertyForTermSet</span><span class="sxs-lookup"><span data-stu-id="8e9c3-289">SharedCustomPropertyForTerm, LocalCustomPropertyForTerm, CustomPropertyForTermSet</span></span> |<span data-ttu-id="8e9c3-290">布尔，字符串，整数，小数，双</span><span class="sxs-lookup"><span data-stu-id="8e9c3-290">Boolean, String, Integer, Decimal, Double</span></span>|
|<span data-ttu-id="8e9c3-291">description</span><span class="sxs-lookup"><span data-stu-id="8e9c3-291">description</span></span>|<span data-ttu-id="8e9c3-292">具有说明</span><span class="sxs-lookup"><span data-stu-id="8e9c3-292">Has Description</span></span>|<span data-ttu-id="8e9c3-293">全部</span><span class="sxs-lookup"><span data-stu-id="8e9c3-293">All</span></span>|<span data-ttu-id="8e9c3-294">纯字面意义</span><span class="sxs-lookup"><span data-stu-id="8e9c3-294">Plain literal</span></span>|
|<span data-ttu-id="8e9c3-295">parent</span><span class="sxs-lookup"><span data-stu-id="8e9c3-295">parent</span></span>|<span data-ttu-id="8e9c3-296">具有父级</span><span class="sxs-lookup"><span data-stu-id="8e9c3-296">Has parent</span></span>|<span data-ttu-id="8e9c3-297">Term</span><span class="sxs-lookup"><span data-stu-id="8e9c3-297">Term</span></span>|<span data-ttu-id="8e9c3-298">Term</span><span class="sxs-lookup"><span data-stu-id="8e9c3-298">Term</span></span>|
|<span data-ttu-id="8e9c3-299">Child</span><span class="sxs-lookup"><span data-stu-id="8e9c3-299">child</span></span>|<span data-ttu-id="8e9c3-300">具有子级</span><span class="sxs-lookup"><span data-stu-id="8e9c3-300">Has Child</span></span>|<span data-ttu-id="8e9c3-301">Term</span><span class="sxs-lookup"><span data-stu-id="8e9c3-301">Term</span></span>|<span data-ttu-id="8e9c3-302">Term</span><span class="sxs-lookup"><span data-stu-id="8e9c3-302">Term</span></span>|
|<span data-ttu-id="8e9c3-303">isAvailableForTagging</span><span class="sxs-lookup"><span data-stu-id="8e9c3-303">isAvailableForTagging</span></span>|<span data-ttu-id="8e9c3-304">可用于标记</span><span class="sxs-lookup"><span data-stu-id="8e9c3-304">Is available for tagging</span></span>|<span data-ttu-id="8e9c3-305">术语、术语集</span><span class="sxs-lookup"><span data-stu-id="8e9c3-305">Term, Term Set</span></span>|<span data-ttu-id="8e9c3-306">布尔值</span><span class="sxs-lookup"><span data-stu-id="8e9c3-306">Boolean</span></span>|
|<span data-ttu-id="8e9c3-307">SharedCustomPropertyForTerm</span><span class="sxs-lookup"><span data-stu-id="8e9c3-307">SharedCustomPropertyForTerm</span></span>|<span data-ttu-id="8e9c3-308">拥有共享的自定义属性</span><span class="sxs-lookup"><span data-stu-id="8e9c3-308">Has shared custom property</span></span>|<span data-ttu-id="8e9c3-309">Term</span><span class="sxs-lookup"><span data-stu-id="8e9c3-309">Term</span></span>|<span data-ttu-id="8e9c3-310">布尔值、字符串、整数、小数、双</span><span class="sxs-lookup"><span data-stu-id="8e9c3-310">Boolean, string, Integer, Decimal, Double</span></span>|
|<span data-ttu-id="8e9c3-311">LocalCustomPropertyForTerm</span><span class="sxs-lookup"><span data-stu-id="8e9c3-311">LocalCustomPropertyForTerm</span></span>|<span data-ttu-id="8e9c3-312">具有本地自定义属性</span><span class="sxs-lookup"><span data-stu-id="8e9c3-312">Has local custom property</span></span>|<span data-ttu-id="8e9c3-313">Term</span><span class="sxs-lookup"><span data-stu-id="8e9c3-313">Term</span></span>|<span data-ttu-id="8e9c3-314">布尔值、字符串、整数、小数、双</span><span class="sxs-lookup"><span data-stu-id="8e9c3-314">Boolean, String, Integer, Decimal, Double</span></span>|
|<span data-ttu-id="8e9c3-315">CustomPropertyForTermSet</span><span class="sxs-lookup"><span data-stu-id="8e9c3-315">CustomPropertyForTermSet</span></span>|<span data-ttu-id="8e9c3-316">具有自定义属性</span><span class="sxs-lookup"><span data-stu-id="8e9c3-316">Has Custom Property</span></span>|<span data-ttu-id="8e9c3-317">TermSet</span><span class="sxs-lookup"><span data-stu-id="8e9c3-317">TermSet</span></span>|<span data-ttu-id="8e9c3-318">布尔值、字符串、整数、小数、双</span><span class="sxs-lookup"><span data-stu-id="8e9c3-318">Boolean, String, Integer, Decimal, Double</span></span>|

<span data-ttu-id="8e9c3-319">[SharePoint 分类](/dotnet/api/microsoft.sharepoint.taxonomy) 不允许的 [SKOS](https://www.w3.org/TR/skos-primer/) 有效方案：</span><span class="sxs-lookup"><span data-stu-id="8e9c3-319">[SKOS](https://www.w3.org/TR/skos-primer/) valid scenarios that [SharePoint taxonomy](/dotnet/api/microsoft.sharepoint.taxonomy) does not allow:</span></span>

- <span data-ttu-id="8e9c3-320">分层冗余 - [SKOS](https://www.w3.org/TR/skos-primer/) 概念可同时附加到多个更广泛的概念，但 sharepoint-taxonomy：Term 只能有一个 sharepoint-taxonomy:parent，因此循环依赖术语是不被允许的。</span><span class="sxs-lookup"><span data-stu-id="8e9c3-320">Hierarchical redundancy - A [SKOS](https://www.w3.org/TR/skos-primer/) concept can be attached to several broader concepts at the same time, but a sharepoint-taxonomy:Term can have only one sharepoint-taxonomy:parent, hence cyclic dependency, of Terms is also not allowed.</span></span>
- <span data-ttu-id="8e9c3-p118">SharePoint 分类中不允许使用孤立术语。每个 sharepoint-taxonomy：术语应具有 sharepoint-taxonomy：parent 或它应该是 sharepoint-taxonomy：topLevelTermOf a TermSet。</span><span class="sxs-lookup"><span data-stu-id="8e9c3-p118">Orphaned terms are not allowed in SharePoint taxonomy. Every sharepoint-taxonomy:Term should either have a sharepoint-taxonomy:parent or it should be the sharepoint-taxonomy:topLevelTermOf a TermSet.</span></span>
- <span data-ttu-id="8e9c3-323">SharePoint 分类不支持关联关系。</span><span class="sxs-lookup"><span data-stu-id="8e9c3-323">SharePoint taxonomy does not support associative relations.</span></span>
- <span data-ttu-id="8e9c3-324">SharePoint 分类仅允许 2 种类型的分层关系 – sharepoint-taxonomy:parent 和 sharepoint-Taxonomy:child.</span><span class="sxs-lookup"><span data-stu-id="8e9c3-324">SharePoint taxonomy only allows 2 types of Hierarchical relations – sharepoint-taxonomy:parent and sharepoint-Taxonomy:child.</span></span>
- <span data-ttu-id="8e9c3-325">不同于 [SKOS](https://www.w3.org/TR/skos-primer/)，SharePoint 分类词汇表中的分层关系只能使用同一 TermSet 中的 Term 建立。</span><span class="sxs-lookup"><span data-stu-id="8e9c3-325">Unlike [SKOS](https://www.w3.org/TR/skos-primer/) the hierarchical relationship in SharePoint taxonomy vocabulary, can only be established with Terms within the same TermSet.</span></span>

## <a name="see-also"></a><span data-ttu-id="8e9c3-326">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8e9c3-326">See also</span></span>

[<span data-ttu-id="8e9c3-327">使用基于 SKOS 的格式导入术语集</span><span class="sxs-lookup"><span data-stu-id="8e9c3-327">Import a term set using a SKOS-based format</span></span>](import-term-set-skos.md)