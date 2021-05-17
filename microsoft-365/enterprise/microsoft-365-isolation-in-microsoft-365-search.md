---
title: Microsoft 365 搜索中的租户隔离
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
f1.keywords:
- NOCSH
description: 本文介绍租户隔离在搜索中分隔租户数据Microsoft 365说明。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 3416afdeceaa7000b516ec89b4a2a1e59d8708d0
ms.sourcegitcommit: c029834c8a914b4e072de847fc4c3a3dde7790c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/02/2020
ms.locfileid: "47332396"
---
# <a name="tenant-isolation-in-microsoft-365-search"></a><span data-ttu-id="3453a-103">Microsoft 365 搜索中的租户隔离</span><span class="sxs-lookup"><span data-stu-id="3453a-103">Tenant Isolation in Microsoft 365 Search</span></span>

<span data-ttu-id="3453a-104">SharePoint联机搜索使用租户分离模型，该模型可平衡共享数据结构的效率，并防范租户之间的信息泄露。</span><span class="sxs-lookup"><span data-stu-id="3453a-104">SharePoint Online search uses a tenant separation model that balances the efficiency of shared data structures with protection against information leaking between tenants.</span></span> <span data-ttu-id="3453a-105">通过此模型，我们可以阻止搜索功能：</span><span class="sxs-lookup"><span data-stu-id="3453a-105">With this model, we prevent the Search features from:</span></span>

- <span data-ttu-id="3453a-106">返回包含来自其他租户的文档的查询结果</span><span class="sxs-lookup"><span data-stu-id="3453a-106">Returning query results that contain documents from other tenants</span></span>
- <span data-ttu-id="3453a-107">在查询结果中公开足够信息，技能熟练用户可以推断出有关其他租户的信息</span><span class="sxs-lookup"><span data-stu-id="3453a-107">Exposing sufficient information in query results that a skilled user could infer information about other tenants</span></span>
- <span data-ttu-id="3453a-108">显示来自另一个租户的架构或设置</span><span class="sxs-lookup"><span data-stu-id="3453a-108">Showing schema or settings from another tenant</span></span>
- <span data-ttu-id="3453a-109">在租户或存储之间混合分析处理信息会导致错误的租户</span><span class="sxs-lookup"><span data-stu-id="3453a-109">Mixing analytics processing information between tenants or store results in the wrong tenant</span></span>
- <span data-ttu-id="3453a-110">使用来自另一个租户的词典条目</span><span class="sxs-lookup"><span data-stu-id="3453a-110">Using dictionary entries from another tenant</span></span>

<span data-ttu-id="3453a-111">对于每种类型的租户数据，我们在代码中使用一个或多个保护层来防止意外泄露信息。</span><span class="sxs-lookup"><span data-stu-id="3453a-111">For each type of tenant data, we use one or more layers of protection in the code to prevent accidental leaking of information.</span></span> <span data-ttu-id="3453a-112">最重要的数据具有最多保护层，以确保单个缺陷不导致实际或感知的信息泄露。</span><span class="sxs-lookup"><span data-stu-id="3453a-112">The most critical data has the most layers of protection to make sure that a single defect doesn't result in actual or perceived information leakage.</span></span>

## <a name="tenant-separation-for-the-search-index"></a><span data-ttu-id="3453a-113">搜索索引的租户分离</span><span class="sxs-lookup"><span data-stu-id="3453a-113">Tenant Separation for the Search Index</span></span>

<span data-ttu-id="3453a-114">搜索索引存储在磁盘上托管索引组件的服务器中，并且租户共享索引文件。</span><span class="sxs-lookup"><span data-stu-id="3453a-114">The search index is stored on disk in the servers hosting the index components and the tenants share the index files.</span></span> <span data-ttu-id="3453a-115">租户的索引文档仅对租户的查询可见。</span><span class="sxs-lookup"><span data-stu-id="3453a-115">A tenant's indexed documents are visible only for queries for that tenant.</span></span> <span data-ttu-id="3453a-116">三种独立的机制可防止信息泄露：</span><span class="sxs-lookup"><span data-stu-id="3453a-116">Three independent mechanisms prevent information leakage:</span></span>

- <span data-ttu-id="3453a-117">租户 ID 筛选</span><span class="sxs-lookup"><span data-stu-id="3453a-117">Tenant ID filtering</span></span>
- <span data-ttu-id="3453a-118">租户 ID 术语前缀</span><span class="sxs-lookup"><span data-stu-id="3453a-118">Tenant ID term prefixing</span></span>
- <span data-ttu-id="3453a-119">ACL 检查</span><span class="sxs-lookup"><span data-stu-id="3453a-119">ACL checks</span></span>

<span data-ttu-id="3453a-120">所有三种机制都将无法通过搜索将文档返回到错误的租户。</span><span class="sxs-lookup"><span data-stu-id="3453a-120">All three mechanisms would have to fail for Search to return documents to the wrong tenant.</span></span>

## <a name="tenant-id-filtering-and-tenant-id-term-prefixing"></a><span data-ttu-id="3453a-121">租户 ID 筛选和租户 ID 术语前缀</span><span class="sxs-lookup"><span data-stu-id="3453a-121">Tenant ID Filtering and Tenant ID Term Prefixing</span></span>

<span data-ttu-id="3453a-122">使用租户 ID 在全文检索中编制索引的词的搜索前缀。</span><span class="sxs-lookup"><span data-stu-id="3453a-122">Search prefixes every term that is indexed in the full-text index with the tenant ID.</span></span> <span data-ttu-id="3453a-123">例如，当 ID 为 *"123"* 的租户对术语 *"foo"* 编制索引时，全文本索引中的条目为 *"123foo"。*</span><span class="sxs-lookup"><span data-stu-id="3453a-123">For example, when the term "*foo*" is indexed for a tenant with an ID of "*123*", the entry in the full-text index is "*123foo.*"</span></span>

<span data-ttu-id="3453a-124">每个查询都经过转换，以使用称为租户 ID 筛选的过程包含租户 ID。</span><span class="sxs-lookup"><span data-stu-id="3453a-124">Every query is converted to include the tenant ID using a process called tenant ID filtering.</span></span> <span data-ttu-id="3453a-125">例如，查询 *"foo"* 将转换为"<*guid>。\*\*foo* AND *tenantID*：<*guid*>"，其中<*guid*>表示执行查询的租户。</span><span class="sxs-lookup"><span data-stu-id="3453a-125">For example, the query "*foo*" is converted to "<*guid*>.*foo* AND *tenantID*:<*guid*>", where <*guid*> represents the tenant performing the query.</span></span> <span data-ttu-id="3453a-126">此查询转换发生在每个索引节点中，并且查询和内容处理均不能影响它。</span><span class="sxs-lookup"><span data-stu-id="3453a-126">This query conversion occurs within each index node and neither query nor content processing can influence it.</span></span> <span data-ttu-id="3453a-127">由于租户 ID 将添加到每个查询中，因此无法通过查看一个租户中的最佳匹配排名来推断其他租户中术语的频率。</span><span class="sxs-lookup"><span data-stu-id="3453a-127">Because the tenant ID is added to every query, the frequency of a term in other tenants can't be inferred by looking at best match ranking in one tenant.</span></span>

<span data-ttu-id="3453a-128">租户 ID 术语前缀仅在全文索引中发生。</span><span class="sxs-lookup"><span data-stu-id="3453a-128">Tenant ID term prefixing occurs only in the full-text index.</span></span> <span data-ttu-id="3453a-129">字段搜索（如"*title：foo*"）转到一个综合搜索索引，其中字词不以租户 ID 作为前缀。</span><span class="sxs-lookup"><span data-stu-id="3453a-129">Fielded searches, such as "*title:foo*", go to a synthetic search index where terms aren't prefixed by tenant ID.</span></span> <span data-ttu-id="3453a-130">相反，域搜索的前缀为字段名称。</span><span class="sxs-lookup"><span data-stu-id="3453a-130">Instead, fielded searches are prefixed with the field name.</span></span> <span data-ttu-id="3453a-131">例如，查询 *"title：foo"* 将转换为"*fields.title：foo AND fields.tenantID*：<*guid*>"。</span><span class="sxs-lookup"><span data-stu-id="3453a-131">For example, the query "*title:foo*" is converted to "*fields.title:foo AND fields.tenantID*:<*guid*>."</span></span> <span data-ttu-id="3453a-132">由于术语的频率对综合搜索索引中的命中排名没有影响，因此无需使用术语前缀来分隔租户。</span><span class="sxs-lookup"><span data-stu-id="3453a-132">Because the frequency of a term doesn't influence ranking of hits in the synthetic search index, there's no need for tenant separation by term prefixing.</span></span> <span data-ttu-id="3453a-133">对于 *"title：foo"* 等字段搜索，租户内容分离取决于查询转换对租户 ID 的筛选。</span><span class="sxs-lookup"><span data-stu-id="3453a-133">For a fielded search like "*title:foo*", tenant content separation depends on tenant ID filtering by query conversion.</span></span>

## <a name="document-access-control-list-checks"></a><span data-ttu-id="3453a-134">文档访问控制列表检查</span><span class="sxs-lookup"><span data-stu-id="3453a-134">Document Access Control List Checks</span></span>

<span data-ttu-id="3453a-135">搜索控制通过保存在搜索索引中的 ACL 访问文档。</span><span class="sxs-lookup"><span data-stu-id="3453a-135">Search controls access to documents through ACLs that are saved in the search index.</span></span> <span data-ttu-id="3453a-136">每个项目都使用一组特殊 ACL 字段中的术语进行索引。</span><span class="sxs-lookup"><span data-stu-id="3453a-136">Every item is indexed with a set of terms in a special ACL field.</span></span> <span data-ttu-id="3453a-137">ACL 字段包含每个组或用户可以查看文档的一个术语。</span><span class="sxs-lookup"><span data-stu-id="3453a-137">The ACL field contains one term per group or user that can view the document.</span></span> <span data-ttu-id="3453a-138">每个查询都使用 ACE 术语 (访问控制) 列表进行扩充，其中一个列表针对经过身份验证的用户所属的每个组。</span><span class="sxs-lookup"><span data-stu-id="3453a-138">Every query is augmented with a list of access control entry (ACE) terms, one for each group to which the authenticated user belongs.</span></span>

<span data-ttu-id="3453a-139">例如，类似"<*guid">。\*\*foo AND tenantID*：<*guid*>" 变为："<*guid>。\*\*foo AND tenantID*：<*guid* >  *AND* (*docACL：* < *ace1* >  *OR docACL*：<*ace2* >  *OR docACL*：<*ace3* >  *...*) "</span><span class="sxs-lookup"><span data-stu-id="3453a-139">For example, a query like "<*guid*>.*foo AND tenantID*:<*guid*>" becomes: "<*guid*>.*foo AND tenantID*:<*guid*> *AND* (*docACL:*<*ace1*> *OR docACL*:<*ace2*> *OR docACL*:<*ace3*> *...*)"</span></span>

<span data-ttu-id="3453a-140">由于用户和组标识符以及 AES 都是唯一的，因此这可为仅对部分用户可见的文档提供租户之间的额外安全级别。</span><span class="sxs-lookup"><span data-stu-id="3453a-140">Because user and group identifiers and hence ACEs are unique, this provides an extra level of security between tenants for documents that are only visible to some users.</span></span> <span data-ttu-id="3453a-141">授予租户中常规用户访问权限的特殊"除外部用户以外的每个人"ACE 也一样。</span><span class="sxs-lookup"><span data-stu-id="3453a-141">The same is the case for the special "Everyone except external users" ACE that grants access to regular users in the tenant.</span></span> <span data-ttu-id="3453a-142">但由于"每个人"的 AES 对于所有租户都相同，因此公共文档的租户分离取决于租户 ID 筛选。</span><span class="sxs-lookup"><span data-stu-id="3453a-142">But since ACEs for "Everyone" are the same for all tenants, tenant separation for public documents depends on tenant ID filtering.</span></span> <span data-ttu-id="3453a-143">还支持拒绝 AES。</span><span class="sxs-lookup"><span data-stu-id="3453a-143">Deny ACEs are also supported.</span></span> <span data-ttu-id="3453a-144">查询扩充添加一个子句，当与拒绝 ACE 匹配时，该子句从结果中删除文档。</span><span class="sxs-lookup"><span data-stu-id="3453a-144">The query augmentation adds a clause that removes a document from the result when there is a match with a deny ACE.</span></span>

<span data-ttu-id="3453a-145">在Exchange Online搜索中，索引按单个用户邮箱的邮箱 ID 而不是租户 ID (订阅 ID) 如 SharePoint Online 中的SharePoint分区。</span><span class="sxs-lookup"><span data-stu-id="3453a-145">In Exchange Online search, the index is partitioned on mailbox ID for individual user's mailboxes instead of tenant ID (subscription ID) as in SharePoint Online.</span></span> <span data-ttu-id="3453a-146">分区机制与 SharePoint 相同，但没有 ACL 筛选。</span><span class="sxs-lookup"><span data-stu-id="3453a-146">The partitioning mechanism is the same as SharePoint Online, but there is no ACL filtering.</span></span>
