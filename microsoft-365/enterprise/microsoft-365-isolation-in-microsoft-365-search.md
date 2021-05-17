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
# <a name="tenant-isolation-in-microsoft-365-search"></a>Microsoft 365 搜索中的租户隔离

SharePoint联机搜索使用租户分离模型，该模型可平衡共享数据结构的效率，并防范租户之间的信息泄露。 通过此模型，我们可以阻止搜索功能：

- 返回包含来自其他租户的文档的查询结果
- 在查询结果中公开足够信息，技能熟练用户可以推断出有关其他租户的信息
- 显示来自另一个租户的架构或设置
- 在租户或存储之间混合分析处理信息会导致错误的租户
- 使用来自另一个租户的词典条目

对于每种类型的租户数据，我们在代码中使用一个或多个保护层来防止意外泄露信息。 最重要的数据具有最多保护层，以确保单个缺陷不导致实际或感知的信息泄露。

## <a name="tenant-separation-for-the-search-index"></a>搜索索引的租户分离

搜索索引存储在磁盘上托管索引组件的服务器中，并且租户共享索引文件。 租户的索引文档仅对租户的查询可见。 三种独立的机制可防止信息泄露：

- 租户 ID 筛选
- 租户 ID 术语前缀
- ACL 检查

所有三种机制都将无法通过搜索将文档返回到错误的租户。

## <a name="tenant-id-filtering-and-tenant-id-term-prefixing"></a>租户 ID 筛选和租户 ID 术语前缀

使用租户 ID 在全文检索中编制索引的词的搜索前缀。 例如，当 ID 为 *"123"* 的租户对术语 *"foo"* 编制索引时，全文本索引中的条目为 *"123foo"。*

每个查询都经过转换，以使用称为租户 ID 筛选的过程包含租户 ID。 例如，查询 *"foo"* 将转换为"<*guid>。**foo* AND *tenantID*：<*guid*>"，其中<*guid*>表示执行查询的租户。 此查询转换发生在每个索引节点中，并且查询和内容处理均不能影响它。 由于租户 ID 将添加到每个查询中，因此无法通过查看一个租户中的最佳匹配排名来推断其他租户中术语的频率。

租户 ID 术语前缀仅在全文索引中发生。 字段搜索（如"*title：foo*"）转到一个综合搜索索引，其中字词不以租户 ID 作为前缀。 相反，域搜索的前缀为字段名称。 例如，查询 *"title：foo"* 将转换为"*fields.title：foo AND fields.tenantID*：<*guid*>"。 由于术语的频率对综合搜索索引中的命中排名没有影响，因此无需使用术语前缀来分隔租户。 对于 *"title：foo"* 等字段搜索，租户内容分离取决于查询转换对租户 ID 的筛选。

## <a name="document-access-control-list-checks"></a>文档访问控制列表检查

搜索控制通过保存在搜索索引中的 ACL 访问文档。 每个项目都使用一组特殊 ACL 字段中的术语进行索引。 ACL 字段包含每个组或用户可以查看文档的一个术语。 每个查询都使用 ACE 术语 (访问控制) 列表进行扩充，其中一个列表针对经过身份验证的用户所属的每个组。

例如，类似"<*guid">。**foo AND tenantID*：<*guid*>" 变为："<*guid>。**foo AND tenantID*：<*guid* >  *AND* (*docACL：* < *ace1* >  *OR docACL*：<*ace2* >  *OR docACL*：<*ace3* >  *...*) "

由于用户和组标识符以及 AES 都是唯一的，因此这可为仅对部分用户可见的文档提供租户之间的额外安全级别。 授予租户中常规用户访问权限的特殊"除外部用户以外的每个人"ACE 也一样。 但由于"每个人"的 AES 对于所有租户都相同，因此公共文档的租户分离取决于租户 ID 筛选。 还支持拒绝 AES。 查询扩充添加一个子句，当与拒绝 ACE 匹配时，该子句从结果中删除文档。

在Exchange Online搜索中，索引按单个用户邮箱的邮箱 ID 而不是租户 ID (订阅 ID) 如 SharePoint Online 中的SharePoint分区。 分区机制与 SharePoint 相同，但没有 ACL 筛选。
