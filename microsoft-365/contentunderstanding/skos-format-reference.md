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
# <a name="skos-format-reference-for-sharepoint-taxonomy"></a><span data-ttu-id="a790f-103">SharePoint 分类的 SKOS 格式参考</span><span class="sxs-lookup"><span data-stu-id="a790f-103">SKOS format reference for SharePoint taxonomy</span></span>

<span data-ttu-id="a790f-104">本文包括用于表示 [SharePoint 分类](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) 和基于 [SKOS](https://www.w3.org/TR/skos-primer/)的 RDF 词汇。</span><span class="sxs-lookup"><span data-stu-id="a790f-104">This article includes RDF vocabulary used to represent [SharePoint taxonomy](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) and is based on [SKOS](https://www.w3.org/TR/skos-primer/).</span></span> <span data-ttu-id="a790f-105">若要对此 RDF 语法进行序列化，请使用 RDF [龟标](https://www.w3.org/TR/turtle/)。</span><span class="sxs-lookup"><span data-stu-id="a790f-105">For serialization of this RDF syntax, use RDF [TURTLE](https://www.w3.org/TR/turtle/).</span></span>

<span data-ttu-id="a790f-106">下表显示了[SharePoint 分类](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy)词汇的[SKOS](https://www.w3.org/TR/skos-primer/)等效项。</span><span class="sxs-lookup"><span data-stu-id="a790f-106">The following table shows the [SKOS](https://www.w3.org/TR/skos-primer/) equivalents for the [SharePoint taxonomy](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) vocabulary.</span></span> <span data-ttu-id="a790f-107">SharePoint 不支持没有 SharePoint 分类等效项的 [SKOS](https://www.w3.org/TR/skos-primer/) 值。</span><span class="sxs-lookup"><span data-stu-id="a790f-107">SharePoint does not support [SKOS](https://www.w3.org/TR/skos-primer/) values that have no SharePoint taxonomy equivalent.</span></span>

|<span data-ttu-id="a790f-108">SharePoint 分类</span><span class="sxs-lookup"><span data-stu-id="a790f-108">SharePoint taxonomy</span></span>|<span data-ttu-id="a790f-109">SKOS 等效项</span><span class="sxs-lookup"><span data-stu-id="a790f-109">SKOS equivalent</span></span>|
|:-----------------|:--------------|
|<span data-ttu-id="a790f-110">sharepoint-分类：术语</span><span class="sxs-lookup"><span data-stu-id="a790f-110">sharepoint-taxonomy:Term</span></span>|<span data-ttu-id="a790f-111">skos：概念</span><span class="sxs-lookup"><span data-stu-id="a790f-111">skos:Concept</span></span>|
|<span data-ttu-id="a790f-112">sharepoint-分类： TermSet</span><span class="sxs-lookup"><span data-stu-id="a790f-112">sharepoint-taxonomy:TermSet</span></span>|<span data-ttu-id="a790f-113">skos:ConceptScheme</span><span class="sxs-lookup"><span data-stu-id="a790f-113">skos:ConceptScheme</span></span>|
|<span data-ttu-id="a790f-114">sharepoint-分类： inTermSet</span><span class="sxs-lookup"><span data-stu-id="a790f-114">sharepoint-taxonomy:inTermSet</span></span>|<span data-ttu-id="a790f-115">skos:inScheme</span><span class="sxs-lookup"><span data-stu-id="a790f-115">skos:inScheme</span></span>|
|<span data-ttu-id="a790f-116">sharepoint-分类： hasTopLevelTerm</span><span class="sxs-lookup"><span data-stu-id="a790f-116">sharepoint-taxonomy:hasTopLevelTerm</span></span>|<span data-ttu-id="a790f-117">skos:hasTopConcept</span><span class="sxs-lookup"><span data-stu-id="a790f-117">skos:hasTopConcept</span></span>|
|<span data-ttu-id="a790f-118">sharepoint-分类： topLevelTermOf</span><span class="sxs-lookup"><span data-stu-id="a790f-118">sharepoint-taxonomy:topLevelTermOf</span></span>|<span data-ttu-id="a790f-119">skos:topConceptOf</span><span class="sxs-lookup"><span data-stu-id="a790f-119">skos:topConceptOf</span></span>|
|<span data-ttu-id="a790f-120">sharepoint-分类： defaultLabel</span><span class="sxs-lookup"><span data-stu-id="a790f-120">sharepoint-taxonomy:defaultLabel</span></span>|<span data-ttu-id="a790f-121">skos:prefLabel</span><span class="sxs-lookup"><span data-stu-id="a790f-121">skos:prefLabel</span></span>|
|<span data-ttu-id="a790f-122">sharepoint-分类： termSetName</span><span class="sxs-lookup"><span data-stu-id="a790f-122">sharepoint-taxonomy:termSetName</span></span>|<span data-ttu-id="a790f-123">skos:prefLabel</span><span class="sxs-lookup"><span data-stu-id="a790f-123">skos:prefLabel</span></span>|
|<span data-ttu-id="a790f-124">sharepoint-分类： propertyName</span><span class="sxs-lookup"><span data-stu-id="a790f-124">sharepoint-taxonomy:propertyName</span></span>|<span data-ttu-id="a790f-125">skos:prefLabel</span><span class="sxs-lookup"><span data-stu-id="a790f-125">skos:prefLabel</span></span>|
|<span data-ttu-id="a790f-126">sharepoint-分类： otherLabel</span><span class="sxs-lookup"><span data-stu-id="a790f-126">sharepoint-taxonomy:otherLabel</span></span>|<span data-ttu-id="a790f-127">skos:altLabel</span><span class="sxs-lookup"><span data-stu-id="a790f-127">skos:altLabel</span></span>|
|<span data-ttu-id="a790f-128">sharepoint-分类：说明</span><span class="sxs-lookup"><span data-stu-id="a790f-128">sharepoint-taxonomy:description</span></span>|<span data-ttu-id="a790f-129">skos：定义</span><span class="sxs-lookup"><span data-stu-id="a790f-129">skos:definition</span></span>|
|<span data-ttu-id="a790f-130">sharepoint-分类：父</span><span class="sxs-lookup"><span data-stu-id="a790f-130">sharepoint-taxonomy:parent</span></span>|<span data-ttu-id="a790f-131">skos：更广泛</span><span class="sxs-lookup"><span data-stu-id="a790f-131">skos:broader</span></span>|
|<span data-ttu-id="a790f-132">sharepoint-分类：子级</span><span class="sxs-lookup"><span data-stu-id="a790f-132">sharepoint-taxonomy:child</span></span>|<span data-ttu-id="a790f-133">skos：变窄</span><span class="sxs-lookup"><span data-stu-id="a790f-133">skos:narrower</span></span>|

<span data-ttu-id="a790f-134">下表显示了从 [OWL](https://www.w3.org/TR/owl2-primer/)派生的 SharePoint 分类词汇的实体。</span><span class="sxs-lookup"><span data-stu-id="a790f-134">The following table displays the entities of the SharePoint taxonomy vocabulary derived from [OWL](https://www.w3.org/TR/owl2-primer/).</span></span>

|<span data-ttu-id="a790f-135">SharePoint 分类词汇</span><span class="sxs-lookup"><span data-stu-id="a790f-135">SharePoint taxonomy vocabulary</span></span>|<span data-ttu-id="a790f-136">派生自 OWL</span><span class="sxs-lookup"><span data-stu-id="a790f-136">Derived from OWL</span></span>|
|:-----------------------------|:----------------------|
|<span data-ttu-id="a790f-137">sharepoint-分类： isAvailableForTagging</span><span class="sxs-lookup"><span data-stu-id="a790f-137">sharepoint-taxonomy:isAvailableForTagging</span></span>|<span data-ttu-id="a790f-138">owl:datatypeproperty</span><span class="sxs-lookup"><span data-stu-id="a790f-138">owl:datatypeproperty</span></span>|
|<span data-ttu-id="a790f-139">sharepoint-分类： SharedCustomPropertyForTerm</span><span class="sxs-lookup"><span data-stu-id="a790f-139">sharepoint-taxonomy:SharedCustomPropertyForTerm</span></span>|<span data-ttu-id="a790f-140">owl： Property</span><span class="sxs-lookup"><span data-stu-id="a790f-140">owl:ObjectProperty</span></span>|
|<span data-ttu-id="a790f-141">sharepoint-分类： LocalCustomPropertyForTerm</span><span class="sxs-lookup"><span data-stu-id="a790f-141">sharepoint-taxonomy:LocalCustomPropertyForTerm</span></span>|<span data-ttu-id="a790f-142">owl： Property</span><span class="sxs-lookup"><span data-stu-id="a790f-142">owl:ObjectProperty</span></span>|
|<span data-ttu-id="a790f-143">sharepoint-分类： CustomPropertyForTermSet</span><span class="sxs-lookup"><span data-stu-id="a790f-143">sharepoint-taxonomy:CustomPropertyForTermSet</span></span>|<span data-ttu-id="a790f-144">owl： Property</span><span class="sxs-lookup"><span data-stu-id="a790f-144">owl:ObjectProperty</span></span>|

## <a name="sharepoint-taxonomy-vocabulary"></a><span data-ttu-id="a790f-145">SharePoint 分类词汇</span><span class="sxs-lookup"><span data-stu-id="a790f-145">SharePoint taxonomy vocabulary</span></span>

<span data-ttu-id="a790f-146">分类是正式的分类系统。</span><span class="sxs-lookup"><span data-stu-id="a790f-146">A taxonomy is a formal classification system.</span></span> <span data-ttu-id="a790f-147">分类对描述内容的词、标签和术语进行分组，然后将组排列到一个层次结构中。</span><span class="sxs-lookup"><span data-stu-id="a790f-147">A taxonomy groups the words, labels, and terms that describe something, and then arranges the groups into a hierarchy.</span></span>

<span data-ttu-id="a790f-148">**sharepoint-分类：术语**</span><span class="sxs-lookup"><span data-stu-id="a790f-148">**sharepoint-taxonomy:Term**</span></span>

<span data-ttu-id="a790f-149">表示托管元数据层次结构中的 Term 或关键字。</span><span class="sxs-lookup"><span data-stu-id="a790f-149">Represents a Term or a Keyword in a managed metadata hierarchy.</span></span>

<span data-ttu-id="a790f-150">[术语](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)是 SharePoint [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore)的原子单元。</span><span class="sxs-lookup"><span data-stu-id="a790f-150">A [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) is the atomic unit of a SharePoint [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore).</span></span> <span data-ttu-id="a790f-151">每个[术语](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)都属于一个属于[术语组](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.group)的[TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) 。</span><span class="sxs-lookup"><span data-stu-id="a790f-151">Each [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) belongs to a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) that belongs to a [TermGroup](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.group).</span></span> 

<span data-ttu-id="a790f-152">定义 [术语](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) 的语法如下所示：</span><span class="sxs-lookup"><span data-stu-id="a790f-152">The syntax to define a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) is as follows:</span></span>

```SKOS
ex:TermA    a    sharepoint-taxonomy:Term;
    sharepoint-taxonomy:inTermSet    ex:TermSetA;
    sharepoint-taxonomy:topLevelTermOf    ex:TermSetA;
    sharepoint-taxonomy:child    ex:TermA1;
    sharepoint-taxonomy:isAvailableForTagging    “true”^^xsd:Boolean;
    sharePoint-taxonomy:defaultLabel    “Term A”@en-us.
```

<span data-ttu-id="a790f-153">[术语](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)compulsorily 存在于[TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)中。</span><span class="sxs-lookup"><span data-stu-id="a790f-153">A [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) compulsorily exists within a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> <span data-ttu-id="a790f-154">DefaultLabel 是显示在可视表示形式中的 [术语](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) 的名称。</span><span class="sxs-lookup"><span data-stu-id="a790f-154">DefaultLabel is the name of the [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) as it appears in the visual representation.</span></span> <span data-ttu-id="a790f-155">用于定义 [术语](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) 的必填字段包括：</span><span class="sxs-lookup"><span data-stu-id="a790f-155">The required fields for defining a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) include:</span></span>

- <span data-ttu-id="a790f-156">sharepoint-分类： defaultLabel</span><span class="sxs-lookup"><span data-stu-id="a790f-156">sharepoint-taxonomy:defaultLabel</span></span>
- <span data-ttu-id="a790f-157">sharepoint-分类： inTermSet</span><span class="sxs-lookup"><span data-stu-id="a790f-157">sharepoint-taxonomy:inTermSet</span></span>

<span data-ttu-id="a790f-158">[术语](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)可以：</span><span class="sxs-lookup"><span data-stu-id="a790f-158">A [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) can:</span></span>

- <span data-ttu-id="a790f-159">与另一个 [术语](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) 按层次结构相关，这两个 [术语](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) 都属于同一个 [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)。</span><span class="sxs-lookup"><span data-stu-id="a790f-159">Be hierarchically related to another [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) that is provided both the [Terms](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) belong to the same [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span>
- <span data-ttu-id="a790f-160">具有多个子 [术语](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)，但只能有一个父 [术语](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)。</span><span class="sxs-lookup"><span data-stu-id="a790f-160">Have multiple child [Terms](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term), but only a single parent [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span>
- <span data-ttu-id="a790f-161">未定义父 [术语](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) ，如果它是 [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)的 topLevelTermOf。</span><span class="sxs-lookup"><span data-stu-id="a790f-161">Not have a parent [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) defined, if it is a topLevelTermOf a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span>
- <span data-ttu-id="a790f-162">具有一个 defaultLabel，每个 [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) 的工作语言。</span><span class="sxs-lookup"><span data-stu-id="a790f-162">Have one defaultLabel, per [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) working language.</span></span>
- <span data-ttu-id="a790f-163">如果它既不包含父 [术语](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)，也不是 topLevelTermOf [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)，则不存在。</span><span class="sxs-lookup"><span data-stu-id="a790f-163">Not exist if it neither contains a parent [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term), nor is the topLevelTermOf a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> 
- <span data-ttu-id="a790f-164">在相同的层次结构级别中只有一个唯一的 defaultLabel。</span><span class="sxs-lookup"><span data-stu-id="a790f-164">Have only a unique defaultLabel in the same hierarchical level.</span></span>

<span data-ttu-id="a790f-165">**sharepoint-分类： TermSet**</span><span class="sxs-lookup"><span data-stu-id="a790f-165">**sharepoint-taxonomy:TermSet**</span></span>

<span data-ttu-id="a790f-166">按场中注册的名称显示的标识提供程序的名称。</span><span class="sxs-lookup"><span data-stu-id="a790f-166">Represents a hierarchical or flat set of Term objects known as a "TermSet".</span></span>

<span data-ttu-id="a790f-167">顾名思义，TermSet 是一组 [术语](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)。</span><span class="sxs-lookup"><span data-stu-id="a790f-167">As the name suggests, TermSet is a set of [Terms](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span> <span data-ttu-id="a790f-168">[TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore)中的某个[术语](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)必须属于[TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)。</span><span class="sxs-lookup"><span data-stu-id="a790f-168">A [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) in a [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) must belong to a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> <span data-ttu-id="a790f-169">任何 [术语](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) 都不能独立存在。</span><span class="sxs-lookup"><span data-stu-id="a790f-169">No [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) can exist independently.</span></span> 

<span data-ttu-id="a790f-170">定义 [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) 的语法为：</span><span class="sxs-lookup"><span data-stu-id="a790f-170">The syntax to define a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) is:</span></span>

```SKOS
ex:TermSetA    a    sharepoint-taxonomy:TermSet;
    sharepoint-taxonomy:termSetName    “TermSet A";
    sharepoint-taxonomy:isAvailableForTagging    “true”^^xsd:Boolean;
    sharepoint-taxonomy:hasTopLevelTerm    Ex:Term A.
```

<span data-ttu-id="a790f-171">[TermSets](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) 在 [TermGroups](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.group)中逻辑分组在一起。</span><span class="sxs-lookup"><span data-stu-id="a790f-171">[TermSets](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) are logically grouped together in [TermGroups](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.group).</span></span> <span data-ttu-id="a790f-172">用于定义 [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) 的必填字段为：</span><span class="sxs-lookup"><span data-stu-id="a790f-172">The required field for defining a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) is:</span></span>

- <span data-ttu-id="a790f-173">sharepoint-分类： termSetName</span><span class="sxs-lookup"><span data-stu-id="a790f-173">sharepoint-taxonomy:termSetName</span></span>

<span data-ttu-id="a790f-174">在 [术语组](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.group)中提供的 termSetName 不是唯一的情况下，SharPoint 会在名称的末尾追加一个数字，以保持 termSetName (s) 的唯一性。</span><span class="sxs-lookup"><span data-stu-id="a790f-174">In the case of the termSetName provided is not unique within the [TermGroup](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.group), SharPoint appends a number at the end of the name to maintain the uniqueness of termSetName(s).</span></span>

<span data-ttu-id="a790f-175">**sharepoint-分类： hasTopLevelTerm**</span><span class="sxs-lookup"><span data-stu-id="a790f-175">**sharepoint-taxonomy:hasTopLevelTerm**</span></span>

<span data-ttu-id="a790f-176">SharePoint 使用此属性在[TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)中映射最顶部的[术语](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)，这是[TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)中[术语](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)层次结构的入口点。</span><span class="sxs-lookup"><span data-stu-id="a790f-176">SharePoint uses this property to map the top most [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) in the [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), which is the entry point to the hierarchy of [Terms](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) in a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> <span data-ttu-id="a790f-177">这是对 sharepoint 分类的反向关系： topLevelTermOf。</span><span class="sxs-lookup"><span data-stu-id="a790f-177">This is an inverse relation to sharepoint-taxonomy:topLevelTermOf.</span></span> 

<span data-ttu-id="a790f-178">定义此项的语法为：</span><span class="sxs-lookup"><span data-stu-id="a790f-178">The syntax to define this is:</span></span>

```SKOS
ex:TermSetA    sharepoint-taxonomy:hasTopLevelTerm    ex:TermA.
```

>[!NOTE]
> <span data-ttu-id="a790f-179">您不能定义父[术语](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)的顶级[术语](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)。</span><span class="sxs-lookup"><span data-stu-id="a790f-179">You cannot define the top level [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) of a parent [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span>

<span data-ttu-id="a790f-180">**sharepoint-分类： topLevelTermOf**</span><span class="sxs-lookup"><span data-stu-id="a790f-180">**sharepoint-taxonomy:topLevelTermOf**</span></span>

<span data-ttu-id="a790f-181">Sharepoint-分类： topLevelTermOf 是 sharepoint 分类的反向： hasTopLevelTerm</span><span class="sxs-lookup"><span data-stu-id="a790f-181">Sharepoint-taxonomy:topLevelTermOf is the inverse of sharepoint-taxonomy:hasTopLevelTerm</span></span>

<span data-ttu-id="a790f-182">定义此项的语法为：</span><span class="sxs-lookup"><span data-stu-id="a790f-182">The syntax to define this is:</span></span>

```SKOS
ex:TermA    sharepoint-taxonomy:topLevelTermOf    ex:TermSetA.
```

<span data-ttu-id="a790f-183">**sharepoint-分类： inTermSet**</span><span class="sxs-lookup"><span data-stu-id="a790f-183">**sharepoint-taxonomy:inTermSet**</span></span>

<span data-ttu-id="a790f-184">使用此 [项将术语](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) 映射到 [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)。</span><span class="sxs-lookup"><span data-stu-id="a790f-184">Use this to map a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) to a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> <span data-ttu-id="a790f-185">一个 [词](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) 只能存在于一个 [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)中。</span><span class="sxs-lookup"><span data-stu-id="a790f-185">A [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) can only exist in a single [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> <span data-ttu-id="a790f-186">[定义术语](https://github.com/MicrosoftDocs/microsoft-365-docs-pr/blob/3a3cd54dd076b18bdff1d43b3e342897f8704c23/microsoft-365/contentunderstanding/skos-format-reference.md#term)时，SharePoint 需要此属性。</span><span class="sxs-lookup"><span data-stu-id="a790f-186">SharePoint requires this property when [defining a term](https://github.com/MicrosoftDocs/microsoft-365-docs-pr/blob/3a3cd54dd076b18bdff1d43b3e342897f8704c23/microsoft-365/contentunderstanding/skos-format-reference.md#term).</span></span>

## <a name="required-labels"></a><span data-ttu-id="a790f-187">必需标签</span><span class="sxs-lookup"><span data-stu-id="a790f-187">Required labels</span></span>

<span data-ttu-id="a790f-188">您的组织可能希望在开始使用托管元数据之前进行周密的规划。</span><span class="sxs-lookup"><span data-stu-id="a790f-188">Your organization may want to do careful planning before you start to use managed metadata.</span></span> <span data-ttu-id="a790f-189">您必须执行的规划量取决于您的分类的形式。</span><span class="sxs-lookup"><span data-stu-id="a790f-189">The amount of planning that you must do depends on how formal your taxonomy is.</span></span> <span data-ttu-id="a790f-190">它还取决于您希望对元数据施加多少控制。</span><span class="sxs-lookup"><span data-stu-id="a790f-190">It also depends on how much control that you want to impose on metadata.</span></span> <span data-ttu-id="a790f-191">在层次结构的每个级别，需要为术语或 TermSet 配置所需的 lables。</span><span class="sxs-lookup"><span data-stu-id="a790f-191">At each level of the hierarchy, you need to configure required lables for a Term or TermSet.</span></span>

<span data-ttu-id="a790f-192">一个术语可以具有一个或多个默认语言的标签，而非默认语言中的零个或多个标签。</span><span class="sxs-lookup"><span data-stu-id="a790f-192">A Term can have one or more labels in the default language, and zero or more labels in the non-default language.</span></span> <span data-ttu-id="a790f-193">如果术语具有某种语言的标签，则其中一个标签必须为默认标签。</span><span class="sxs-lookup"><span data-stu-id="a790f-193">If the term has labels in a language, one of the labels must be the default label.</span></span>

<span data-ttu-id="a790f-194">**sharepoint-分类： defaultLabel**</span><span class="sxs-lookup"><span data-stu-id="a790f-194">**sharepoint-taxonomy:defaultLabel**</span></span>

<span data-ttu-id="a790f-195">对术语为必需参数的[术语](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)使用此默认词法[标签。](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)</span><span class="sxs-lookup"><span data-stu-id="a790f-195">Use this default lexical label for a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) that is a required parameter for a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span> <span data-ttu-id="a790f-196">用于以可视方式表示 [术语](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)。</span><span class="sxs-lookup"><span data-stu-id="a790f-196">Use to visually representing the [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span>

<span data-ttu-id="a790f-197">定义 defaultLabel 的语法为：</span><span class="sxs-lookup"><span data-stu-id="a790f-197">The syntax to define a defaultLabel is:</span></span>

```SKOS
ex:TermA    sharepoint-taxonomy:defaultLabel    “Term A”@en-us.
```

<span data-ttu-id="a790f-198">DefaultLabel 包含两个部分–字符串和语言标记。</span><span class="sxs-lookup"><span data-stu-id="a790f-198">The defaultLabel contains two parts to it – the string and the language tag.</span></span> <span data-ttu-id="a790f-199">该语言必须是 [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) 工作的语言之一。</span><span class="sxs-lookup"><span data-stu-id="a790f-199">The language must be one of the [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) working languages.</span></span> <span data-ttu-id="a790f-200">对于同一[TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)中的所有[术语](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)，defaultLabel 必须是唯一的层次结构级别。</span><span class="sxs-lookup"><span data-stu-id="a790f-200">The defaultLabel must be unique for all [Terms](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) in the same [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), at the same hierarchical level.</span></span>

<span data-ttu-id="a790f-201">**sharepoint-分类： termSetName**</span><span class="sxs-lookup"><span data-stu-id="a790f-201">**sharepoint-taxonomy:termSetName**</span></span>

<span data-ttu-id="a790f-202">获取并设置当前 TermSet 对象的名称。</span><span class="sxs-lookup"><span data-stu-id="a790f-202">Gets and sets the name for the current TermSet object.</span></span>

<span data-ttu-id="a790f-203">这是 [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)的词法标签，采用 [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) 的工作语言。</span><span class="sxs-lookup"><span data-stu-id="a790f-203">This the lexical label for a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), in a [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) working language.</span></span> <span data-ttu-id="a790f-204">这是 [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)的必需参数。</span><span class="sxs-lookup"><span data-stu-id="a790f-204">This is a required parameter for a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> <span data-ttu-id="a790f-205">用于以可视方式表示 [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)。</span><span class="sxs-lookup"><span data-stu-id="a790f-205">Use to visually representing a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span>

<span data-ttu-id="a790f-206">定义 termSetName 的语法为：</span><span class="sxs-lookup"><span data-stu-id="a790f-206">The syntax to define a termSetName is:</span></span>

```SKOS
ex:TermA    sharepoint-taxonomy:TermSetName    “Term Set A”@en-us.
```

<span data-ttu-id="a790f-207">**sharepoint-分类： propertyName**</span><span class="sxs-lookup"><span data-stu-id="a790f-207">**sharepoint-taxonomy:propertyName**</span></span>

<span data-ttu-id="a790f-208">获取并设置当前 TermSet 对象的属性名称。</span><span class="sxs-lookup"><span data-stu-id="a790f-208">Gets and sets the property name for the current TermSet object.</span></span>

<span data-ttu-id="a790f-209">这是 sharepoint 分类的词法标签： SharedCustomPropertyForTerm、sharepoint 分类： LocalCustomPropertyForTerm 和 sharepoint 分类： CustomPropertyForTermSet in [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) 工作语言。</span><span class="sxs-lookup"><span data-stu-id="a790f-209">This is the lexical label for a sharepoint-taxonomy:SharedCustomPropertyForTerm, sharepoint-taxonomy:LocalCustomPropertyForTerm and sharepoint-taxonomy:CustomPropertyForTermSet in a [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) working language.</span></span>

<span data-ttu-id="a790f-210">Sharepoint 分类： propertyName 将被视为 CustomProperty 的键。</span><span class="sxs-lookup"><span data-stu-id="a790f-210">The sharepoint-taxonomy:propertyName is treated as the key of the CustomProperty.</span></span>

<span data-ttu-id="a790f-211">定义 propetyName 的语法为：</span><span class="sxs-lookup"><span data-stu-id="a790f-211">The syntax to define a propetyName is:</span></span>

```SKOS
ex:SharedCustomProperty1    sharepoint-taxonomy:propertyName    “Shared Custom Property Key 1”@en-us.
```

## <a name="optional-labels"></a><span data-ttu-id="a790f-212">可选标签</span><span class="sxs-lookup"><span data-stu-id="a790f-212">Optional labels</span></span>

<span data-ttu-id="a790f-213">您还可以将可选标签添加到分类中。</span><span class="sxs-lookup"><span data-stu-id="a790f-213">You can also add optional labels to your taxonomy.</span></span>

<span data-ttu-id="a790f-214">**sharepoint-分类： otherLabel**</span><span class="sxs-lookup"><span data-stu-id="a790f-214">**sharepoint-taxonomy:otherLabel**</span></span>

<span data-ttu-id="a790f-215">这是 [术语](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)的替代词法标签。</span><span class="sxs-lookup"><span data-stu-id="a790f-215">This is the alternate lexical label for a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span> 

<span data-ttu-id="a790f-216">定义 otherLabel 的语法为：</span><span class="sxs-lookup"><span data-stu-id="a790f-216">The syntax to define an otherLabel is:</span></span>

```SKOS
ex:TermA    sharepoint-taxonomy:otherLabel    “Term A”@en-us.
```

## <a name="semantic-relationships"></a><span data-ttu-id="a790f-217">语义关系</span><span class="sxs-lookup"><span data-stu-id="a790f-217">Semantic relationships</span></span>

<span data-ttu-id="a790f-218">分类具有层次结构，有时也是一个简单的 "相关术语" 关联关系，但有些是 "语义关系" 或自定义创建的关系。</span><span class="sxs-lookup"><span data-stu-id="a790f-218">Taxonomies have hierarchical and sometimes a simple “related term” associative relationship, but some have "semantic relationships" or custom-created relationships.</span></span> 

<span data-ttu-id="a790f-219">**sharepoint-分类：父**</span><span class="sxs-lookup"><span data-stu-id="a790f-219">**sharepoint-taxonomy:parent**</span></span>

<span data-ttu-id="a790f-220">这将一个 [术语](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) 分层与另一个 [术语](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)相关联。</span><span class="sxs-lookup"><span data-stu-id="a790f-220">This hierarchically relates a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) to another [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span> <span data-ttu-id="a790f-221">[术语](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)可以是[TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)的首要[术语](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)，但如果它不必须具有父[术语](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)。</span><span class="sxs-lookup"><span data-stu-id="a790f-221">A [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) could be a top level [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) of a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), but in case it doesn’t it must have a parent [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span> 

<span data-ttu-id="a790f-222">定义父级的语法为：</span><span class="sxs-lookup"><span data-stu-id="a790f-222">The syntax to define a parent is:</span></span>

```SKOS
ex:TermA1    sharepoint-taxonomy:parent    ex:TermA.
```

<span data-ttu-id="a790f-223">这意味着 TermA1 具有父 TermA。</span><span class="sxs-lookup"><span data-stu-id="a790f-223">This means that TermA1 has parent TermA.</span></span> <span data-ttu-id="a790f-224">同时，还意味着 TermA1 是 TermA 的子项。</span><span class="sxs-lookup"><span data-stu-id="a790f-224">Inversely it also means that TermA1 is the child of TermA.</span></span> <span data-ttu-id="a790f-225">父子关系是一个 inversible 关系。</span><span class="sxs-lookup"><span data-stu-id="a790f-225">Parent-child relationship is an inversible relationship.</span></span>

<span data-ttu-id="a790f-226">**sharepoint-分类：子级**</span><span class="sxs-lookup"><span data-stu-id="a790f-226">**sharepoint-taxonomy:child**</span></span>

<span data-ttu-id="a790f-227">对象包含一个或多个子 TermSet 实例，可以通过 TermSets 属性访问这些实例。</span><span class="sxs-lookup"><span data-stu-id="a790f-227">The object contains one or more child TermSet instances, and these can be accessed through the TermSets property.</span></span> <span data-ttu-id="a790f-228">此类还提供用于创建新的子 TermSet 对象的方法。</span><span class="sxs-lookup"><span data-stu-id="a790f-228">This class also provides methods for creating new child TermSet objects.</span></span> <span data-ttu-id="a790f-229">在组中指定编辑子术语和 TermSet 实例的权限。</span><span class="sxs-lookup"><span data-stu-id="a790f-229">Permissions for editing child Term and TermSet instances is specified on the group.</span></span> 

<span data-ttu-id="a790f-230">这将一个 [术语](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) 分层与另一个 [术语](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)相关联。</span><span class="sxs-lookup"><span data-stu-id="a790f-230">This hierarchically relates a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) to another [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span>

<span data-ttu-id="a790f-231">用于定义子级的语法为：</span><span class="sxs-lookup"><span data-stu-id="a790f-231">The syntax to define a child is:</span></span>

```SKOS
ex:TermA    sharepoint-taxonomy:child    ex:TermA1.
```

<span data-ttu-id="a790f-232">这意味着 TermA 具有子 TermA1。</span><span class="sxs-lookup"><span data-stu-id="a790f-232">This means that TermA has child TermA1.</span></span> <span data-ttu-id="a790f-233">同时，还意味着 TermA 是 TermA1 父-子关系的父级是一个 inversible 关系。</span><span class="sxs-lookup"><span data-stu-id="a790f-233">Inversely it also means that TermA is the parent of TermA1 parent-child relationship is an inversible relationship.</span></span>

## <a name="documentation-notes"></a><span data-ttu-id="a790f-234">文档说明</span><span class="sxs-lookup"><span data-stu-id="a790f-234">Documentation notes</span></span>

<span data-ttu-id="a790f-235">本节讨论了在 Microsoft. 分类命名空间中详细介绍的分类。</span><span class="sxs-lookup"><span data-stu-id="a790f-235">This section discusses the taxonomy detailed in the Microsoft.SharePoint.Taxonomy Namespace.</span></span>

<span data-ttu-id="a790f-236">**sharepoint-分类：说明**</span><span class="sxs-lookup"><span data-stu-id="a790f-236">**sharepoint-taxonomy:description**</span></span>

<span data-ttu-id="a790f-237">这是对任何 [SharePoint 分类](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) 词汇实体的详细说明。</span><span class="sxs-lookup"><span data-stu-id="a790f-237">This is a detailed explanation of any [SharePoint taxonomy](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) vocabulary entity.</span></span> 

<span data-ttu-id="a790f-238">添加说明的语法为：</span><span class="sxs-lookup"><span data-stu-id="a790f-238">The syntax to add a description is:</span></span>

```SKOS
ex:TermA    sharepoint-taxonomy:description    “Term A is the top level term of TermSetA”@en-us.
```

## <a name="custom-properties"></a><span data-ttu-id="a790f-239">自定义属性</span><span class="sxs-lookup"><span data-stu-id="a790f-239">Custom properties</span></span>

<span data-ttu-id="a790f-240">从只读字典中获取当前 Term 对象的自定义属性对象的集合。</span><span class="sxs-lookup"><span data-stu-id="a790f-240">Gets the collection of custom property objects for the current Term object from the read-only dictionary.</span></span>

<span data-ttu-id="a790f-241">自定义属性是可为 [术语](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) 或 [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)定义的键值对，以进一步说明 [术语](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) 或 [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)的说明。</span><span class="sxs-lookup"><span data-stu-id="a790f-241">Custom Properties are key-values pairs that can be defined for a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) or a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), to further the description of the [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) or a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> <span data-ttu-id="a790f-242">SharePoint 指定具有 propertyName 的帮助的自定义属性的键。</span><span class="sxs-lookup"><span data-stu-id="a790f-242">SharePoint specifies the key of the custom property with the help of propertyName.</span></span>

<span data-ttu-id="a790f-243">**sharepoint-分类： CustomPropertyForTermSet**</span><span class="sxs-lookup"><span data-stu-id="a790f-243">**sharepoint-taxonomy:CustomPropertyForTermSet**</span></span>

<span data-ttu-id="a790f-244">定义此项的语法为：</span><span class="sxs-lookup"><span data-stu-id="a790f-244">The syntax to define this is:</span></span>

```SKOS
ex:CustomProp1    rdf:type    sharepoint-taxonomy:CustomPropertyForTermSet;
    sharepoint-taxonomy:propertyName “Colour”.

ex:TermSetA    ex:CustomProp1    “Red”@en-us.
```

<span data-ttu-id="a790f-245">**sharepoint-分类： SharedCustomPropertyForTerm**</span><span class="sxs-lookup"><span data-stu-id="a790f-245">**sharepoint-taxonomy:SharedCustomPropertyForTerm**</span></span>

<span data-ttu-id="a790f-246">如果某一 [术语](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) 的自定义属性需要与 [术语](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)一起使用，则在其他地方重复使用该 [术语](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) 时，需要在 SharedCustomPropertyForTerm 下定义它。</span><span class="sxs-lookup"><span data-stu-id="a790f-246">If the custom property for a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) needs to be carried along with the [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term), when you reuse the [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) somewhere else, then you need to be define it under SharedCustomPropertyForTerm.</span></span>

<span data-ttu-id="a790f-247">定义此项的语法为：</span><span class="sxs-lookup"><span data-stu-id="a790f-247">The syntax to define this is:</span></span>

``` SKOS
ex:CustomProp2    rdf:type sharepoint-taxonomy:SharedCustomPropertyForTerm;
    sharepoint-taxonomy:propertyName “Length”.

ex:TermA    ex:CustomProp2    “5 cm”@en-us.
```
<span data-ttu-id="a790f-248">**sharepoint-分类： LocalCustomPropertyForTerm**</span><span class="sxs-lookup"><span data-stu-id="a790f-248">**sharepoint-taxonomy:LocalCustomPropertyForTerm**</span></span>

<span data-ttu-id="a790f-249">如果不需要将 [术语](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) 的自定义属性与 [术语](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)一起携带，则在其他地方重复使用该 [术语](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) 时，需要在 LocalCustomPropertyForTerm 下定义它。</span><span class="sxs-lookup"><span data-stu-id="a790f-249">If the custom property for a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) does not need to be carried along with the [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term), when you reuse the [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) somewhere else, then you need to define it under LocalCustomPropertyForTerm.</span></span>

<span data-ttu-id="a790f-250">定义此项的语法为：</span><span class="sxs-lookup"><span data-stu-id="a790f-250">The syntax to define this is:</span></span>

```SKOS
ex:CustomProp3    rdf:type sharepoint-taxonomy:LocalCustomPropertyForTerm;
    sharepoint-taxonomy:propertyName “width”.

ex:TermA    ex:CustomProp3    “5 cm”@en-us.
```

## <a name="data-properties"></a><span data-ttu-id="a790f-251">数据属性</span><span class="sxs-lookup"><span data-stu-id="a790f-251">Data properties</span></span>

<span data-ttu-id="a790f-252">在层次结构的每个级别上，可以为术语或 TermSet 配置特定的数据属性。</span><span class="sxs-lookup"><span data-stu-id="a790f-252">At each level of the hierarchy, you can configure specific data properties for a Term or TermSet.</span></span>

<span data-ttu-id="a790f-253">**sharepoint-分类： isAvailableForTagging**</span><span class="sxs-lookup"><span data-stu-id="a790f-253">**sharepoint-taxonomy:isAvailableForTagging**</span></span>

<span data-ttu-id="a790f-254">使用此项可指定某个 [术语](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) 或 [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) 在 SharePoint 列表和库中是否可用。</span><span class="sxs-lookup"><span data-stu-id="a790f-254">Use this to specify if a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) or a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) available in SharePoint Lists and Libraries.</span></span>  

<span data-ttu-id="a790f-255">的语法如下：</span><span class="sxs-lookup"><span data-stu-id="a790f-255">The syntax for this is:</span></span>

```SKOS
ex:TermA    sharepoint-taxonomy:isAvailableForTagging     "true"^^xsd:Boolean;
```

## <a name="domain-and-range"></a><span data-ttu-id="a790f-256">域和区域</span><span class="sxs-lookup"><span data-stu-id="a790f-256">Domain and range</span></span>

<span data-ttu-id="a790f-257">下表介绍了 SharePoint 分类词汇的域和范围。</span><span class="sxs-lookup"><span data-stu-id="a790f-257">The table below describes the domain and range of SharePoint taxonomy vocabulary.</span></span>

|<span data-ttu-id="a790f-258">谓词/谓词</span><span class="sxs-lookup"><span data-stu-id="a790f-258">Predicates/verb</span></span>|<span data-ttu-id="a790f-259">含义</span><span class="sxs-lookup"><span data-stu-id="a790f-259">Meaning</span></span>|<span data-ttu-id="a790f-260">域</span><span class="sxs-lookup"><span data-stu-id="a790f-260">Domain</span></span>|<span data-ttu-id="a790f-261">Range</span><span class="sxs-lookup"><span data-stu-id="a790f-261">Range</span></span>|
|:--------------|:------|:-----|:----|
<span data-ttu-id="a790f-262">inTermSet</span><span class="sxs-lookup"><span data-stu-id="a790f-262">inTermSet</span></span>|<span data-ttu-id="a790f-263">在术语集中</span><span class="sxs-lookup"><span data-stu-id="a790f-263">In term set</span></span>|<span data-ttu-id="a790f-264">Term</span><span class="sxs-lookup"><span data-stu-id="a790f-264">Term</span></span>|<span data-ttu-id="a790f-265">术语集</span><span class="sxs-lookup"><span data-stu-id="a790f-265">Term Set</span></span>|
<span data-ttu-id="a790f-266">inTermGroup</span><span class="sxs-lookup"><span data-stu-id="a790f-266">inTermGroup</span></span>|<span data-ttu-id="a790f-267">在术语组中</span><span class="sxs-lookup"><span data-stu-id="a790f-267">In term group</span></span>|<span data-ttu-id="a790f-268">TermSet</span><span class="sxs-lookup"><span data-stu-id="a790f-268">TermSet</span></span>|<span data-ttu-id="a790f-269">TermGroup</span><span class="sxs-lookup"><span data-stu-id="a790f-269">TermGroup</span></span>|
<span data-ttu-id="a790f-270">topLevelTermOf</span><span class="sxs-lookup"><span data-stu-id="a790f-270">topLevelTermOf</span></span>|<span data-ttu-id="a790f-271">是顶级术语</span><span class="sxs-lookup"><span data-stu-id="a790f-271">Is Top Level Term Of</span></span>|<span data-ttu-id="a790f-272">Term</span><span class="sxs-lookup"><span data-stu-id="a790f-272">Term</span></span>|<span data-ttu-id="a790f-273">TermSet</span><span class="sxs-lookup"><span data-stu-id="a790f-273">TermSet</span></span>|
<span data-ttu-id="a790f-274">hasTopLevelTerm</span><span class="sxs-lookup"><span data-stu-id="a790f-274">hasTopLevelTerm</span></span>|<span data-ttu-id="a790f-275">具有顶级术语</span><span class="sxs-lookup"><span data-stu-id="a790f-275">Has top level term</span></span>|<span data-ttu-id="a790f-276">术语集</span><span class="sxs-lookup"><span data-stu-id="a790f-276">Term Set</span></span>|<span data-ttu-id="a790f-277">Term</span><span class="sxs-lookup"><span data-stu-id="a790f-277">Term</span></span>|
<span data-ttu-id="a790f-278">termSetName</span><span class="sxs-lookup"><span data-stu-id="a790f-278">termSetName</span></span>|<span data-ttu-id="a790f-279">术语集具有名称</span><span class="sxs-lookup"><span data-stu-id="a790f-279">Term set has Name</span></span>|<span data-ttu-id="a790f-280">Term</span><span class="sxs-lookup"><span data-stu-id="a790f-280">Term</span></span>|<span data-ttu-id="a790f-281">纯文本</span><span class="sxs-lookup"><span data-stu-id="a790f-281">Plain literal</span></span>|
<span data-ttu-id="a790f-282">defaultLabel</span><span class="sxs-lookup"><span data-stu-id="a790f-282">defaultLabel</span></span>|<span data-ttu-id="a790f-283">条件具有默认标签</span><span class="sxs-lookup"><span data-stu-id="a790f-283">Term has default label</span></span>|<span data-ttu-id="a790f-284">Term</span><span class="sxs-lookup"><span data-stu-id="a790f-284">Term</span></span>|<span data-ttu-id="a790f-285">纯文本</span><span class="sxs-lookup"><span data-stu-id="a790f-285">Plain literal</span></span>|
<span data-ttu-id="a790f-286">otherLabel</span><span class="sxs-lookup"><span data-stu-id="a790f-286">otherLabel</span></span>|<span data-ttu-id="a790f-287">字词有其他标签</span><span class="sxs-lookup"><span data-stu-id="a790f-287">Term has other label</span></span>|<span data-ttu-id="a790f-288">Term</span><span class="sxs-lookup"><span data-stu-id="a790f-288">Term</span></span>|<span data-ttu-id="a790f-289">纯文本</span><span class="sxs-lookup"><span data-stu-id="a790f-289">Plain literal</span></span>|
<span data-ttu-id="a790f-290">propertyName</span><span class="sxs-lookup"><span data-stu-id="a790f-290">propertyName</span></span>|<span data-ttu-id="a790f-291">具有属性标签</span><span class="sxs-lookup"><span data-stu-id="a790f-291">Has Property Label</span></span>|<span data-ttu-id="a790f-292">SharedCustomPropertyForTerm, LocalCustomPropertyForTerm, CustomPropertyForTermSet</span><span class="sxs-lookup"><span data-stu-id="a790f-292">SharedCustomPropertyForTerm, LocalCustomPropertyForTerm, CustomPropertyForTermSet</span></span> |<span data-ttu-id="a790f-293">Boolean、String、Integer、Decimal、Double</span><span class="sxs-lookup"><span data-stu-id="a790f-293">Boolean, String, Integer, Decimal, Double</span></span>|
|<span data-ttu-id="a790f-294">description</span><span class="sxs-lookup"><span data-stu-id="a790f-294">description</span></span>|<span data-ttu-id="a790f-295">包含描述</span><span class="sxs-lookup"><span data-stu-id="a790f-295">Has Description</span></span>|<span data-ttu-id="a790f-296">全部</span><span class="sxs-lookup"><span data-stu-id="a790f-296">All</span></span>|<span data-ttu-id="a790f-297">纯文本</span><span class="sxs-lookup"><span data-stu-id="a790f-297">Plain literal</span></span>|
|<span data-ttu-id="a790f-298">父级</span><span class="sxs-lookup"><span data-stu-id="a790f-298">parent</span></span>|<span data-ttu-id="a790f-299">具有父级</span><span class="sxs-lookup"><span data-stu-id="a790f-299">Has parent</span></span>|<span data-ttu-id="a790f-300">Term</span><span class="sxs-lookup"><span data-stu-id="a790f-300">Term</span></span>|<span data-ttu-id="a790f-301">Term</span><span class="sxs-lookup"><span data-stu-id="a790f-301">Term</span></span>|
|<span data-ttu-id="a790f-302">该子</span><span class="sxs-lookup"><span data-stu-id="a790f-302">child</span></span>|<span data-ttu-id="a790f-303">具有子</span><span class="sxs-lookup"><span data-stu-id="a790f-303">Has Child</span></span>|<span data-ttu-id="a790f-304">Term</span><span class="sxs-lookup"><span data-stu-id="a790f-304">Term</span></span>|<span data-ttu-id="a790f-305">Term</span><span class="sxs-lookup"><span data-stu-id="a790f-305">Term</span></span>|
|<span data-ttu-id="a790f-306">isAvailableForTagging</span><span class="sxs-lookup"><span data-stu-id="a790f-306">isAvailableForTagging</span></span>|<span data-ttu-id="a790f-307">是否可用于标记</span><span class="sxs-lookup"><span data-stu-id="a790f-307">Is available for tagging</span></span>|<span data-ttu-id="a790f-308">术语、术语集</span><span class="sxs-lookup"><span data-stu-id="a790f-308">Term, Term Set</span></span>|<span data-ttu-id="a790f-309">Boolean</span><span class="sxs-lookup"><span data-stu-id="a790f-309">Boolean</span></span>|
|<span data-ttu-id="a790f-310">SharedCustomPropertyForTerm</span><span class="sxs-lookup"><span data-stu-id="a790f-310">SharedCustomPropertyForTerm</span></span>|<span data-ttu-id="a790f-311">具有共享的自定义属性</span><span class="sxs-lookup"><span data-stu-id="a790f-311">Has shared custom property</span></span>|<span data-ttu-id="a790f-312">Term</span><span class="sxs-lookup"><span data-stu-id="a790f-312">Term</span></span>|<span data-ttu-id="a790f-313">Boolean、string、Integer、Decimal、Double</span><span class="sxs-lookup"><span data-stu-id="a790f-313">Boolean, string, Integer, Decimal, Double</span></span>|
|<span data-ttu-id="a790f-314">LocalCustomPropertyForTerm</span><span class="sxs-lookup"><span data-stu-id="a790f-314">LocalCustomPropertyForTerm</span></span>|<span data-ttu-id="a790f-315">具有本地自定义属性</span><span class="sxs-lookup"><span data-stu-id="a790f-315">Has local custom property</span></span>|<span data-ttu-id="a790f-316">Term</span><span class="sxs-lookup"><span data-stu-id="a790f-316">Term</span></span>|<span data-ttu-id="a790f-317">Boolean、String、Integer、Decimal、Double</span><span class="sxs-lookup"><span data-stu-id="a790f-317">Boolean, String, Integer, Decimal, Double</span></span>|
|<span data-ttu-id="a790f-318">CustomPropertyForTermSet</span><span class="sxs-lookup"><span data-stu-id="a790f-318">CustomPropertyForTermSet</span></span>|<span data-ttu-id="a790f-319">具有自定义属性</span><span class="sxs-lookup"><span data-stu-id="a790f-319">Has Custom Property</span></span>|<span data-ttu-id="a790f-320">TermSet</span><span class="sxs-lookup"><span data-stu-id="a790f-320">TermSet</span></span>|<span data-ttu-id="a790f-321">Boolean、String、Integer、Decimal、Double</span><span class="sxs-lookup"><span data-stu-id="a790f-321">Boolean, String, Integer, Decimal, Double</span></span>|

<span data-ttu-id="a790f-322">[SKOS](https://www.w3.org/TR/skos-primer/) [SharePoint 分类](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) 不允许的有效方案：</span><span class="sxs-lookup"><span data-stu-id="a790f-322">[SKOS](https://www.w3.org/TR/skos-primer/) valid scenarios that [SharePoint taxonomy](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) does not allow:</span></span>

- <span data-ttu-id="a790f-323">分层冗余- [SKOS](https://www.w3.org/TR/skos-primer/) 概念可以同时附加到多个更广泛的概念，但 sharepoint 分类：术语只能有一个 sharepoint 分类：父，因此，也不允许使用循环依赖项。</span><span class="sxs-lookup"><span data-stu-id="a790f-323">Hierarchical redundancy - A [SKOS](https://www.w3.org/TR/skos-primer/) concept can be attached to several broader concepts at the same time, but a sharepoint-taxonomy:Term can have only one sharepoint-taxonomy:parent, hence cyclic dependency, of Terms is also not allowed.</span></span>
- <span data-ttu-id="a790f-324">SharePoint 分类中不允许使用孤立术语。</span><span class="sxs-lookup"><span data-stu-id="a790f-324">Orphaned terms are not allowed in SharePoint taxonomy.</span></span> <span data-ttu-id="a790f-325">每个 sharepoint 分类：术语应具有 sharepoint 分类： parent 或应为 sharepoint 分类： topLevelTermOf a TermSet。</span><span class="sxs-lookup"><span data-stu-id="a790f-325">Every sharepoint-taxonomy:Term should either have a sharepoint-taxonomy:parent or it should be the sharepoint-taxonomy:topLevelTermOf a TermSet.</span></span>
- <span data-ttu-id="a790f-326">SharePoint 分类不支持关联关系。</span><span class="sxs-lookup"><span data-stu-id="a790f-326">SharePoint taxonomy does not support associative relations.</span></span>
- <span data-ttu-id="a790f-327">SharePoint 分类只允许2种类型的层次结构关系– sharepoint 分类：父项和 sharepoint 分类：子级。</span><span class="sxs-lookup"><span data-stu-id="a790f-327">SharePoint taxonomy only allows 2 types of Hierarchical relations – sharepoint-taxonomy:parent and sharepoint-Taxonomy:child.</span></span> 
- <span data-ttu-id="a790f-328">与 [SKOS](https://www.w3.org/TR/skos-primer/) 不同，SharePoint 分类词汇表中的层次结构关系仅可在同一 TermSet 中使用术语建立。</span><span class="sxs-lookup"><span data-stu-id="a790f-328">Unlike [SKOS](https://www.w3.org/TR/skos-primer/) the hierarchical relationship in SharePoint taxonomy vocabulary, can only be established with Terms within the same TermSet.</span></span>

## <a name="see-also"></a><span data-ttu-id="a790f-329">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a790f-329">See also</span></span>

[<span data-ttu-id="a790f-330">使用基于 SKOS 的格式导入术语集</span><span class="sxs-lookup"><span data-stu-id="a790f-330">Import a term set using a SKOS-based format</span></span>](import-term-set-skos.md)

