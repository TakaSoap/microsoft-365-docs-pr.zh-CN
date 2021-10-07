---
title: 搜索内容
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
ms.localizationpriority: medium
description: 使用 Microsoft 365 合规中心 中的内容搜索电子数据展示工具可快速查找 Exchange 邮箱中的电子邮件、SharePoint 网站和 OneDrive 位置中的文档以及 Skype for Business 中的即时消息对话。
ms.openlocfilehash: 6a49dffccb701958912fb0185eec4a8312f22429
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60202999"
---
# <a name="search-for-content-using-the-content-search-tool"></a>使用内容搜索工具搜索内容

使用 Microsoft 365 合规中心 中的内容搜索工具可快速查找 Exchange 邮箱中的电子邮件、SharePoint 网站和 OneDrive 位置中的文档以及 Skype for Business 中的即时消息对话。 可以使用内容搜索工具在协作工具（如组和组）中搜索电子邮件、文档和Microsoft Teams Microsoft 365对话。
  
## <a name="search-for-content"></a>搜索内容

第一步是开始使用内容搜索工具选择要搜索的内容位置，并配置关键字查询以搜索特定项目。 或者，您可以将查询留空并返回目标位置的所有项目。
  
- [创建和运行](content-search.md) 内容搜索

- [内容搜索](content-search-reference.md) 的功能参考

- [生成搜索查询并使用条件](keyword-queries-and-search-conditions.md) 来缩小搜索范围

- [配置搜索权限筛选](permissions-filtering-for-content-search.md) ，以便电子数据展示管理员只能搜索组织中邮箱或网站的子集

- [运行 ID 列表搜索](csv-file-for-an-id-list-content-search.md) 以搜索特定电子邮件

- [在基于云的邮箱中搜索](search-cloud-based-mailboxes-for-on-premises-users.md)本地Microsoft 365

- [查看搜索结果](view-keyword-statistics-for-content-search.md) 的关键字统计信息，然后在必要时优化查询

- [搜索组织已导入](use-content-search-to-search-third-party-data-that-was-imported.md)到数据的第三方Microsoft 365

- [重试内容搜索](retry-failed-content-search.md) 以解决内容位置错误

- [保留"Bcc"](/exchange/policy-and-compliance/holds/preserve-bcc-recipients-and-group-members) 收件人，以便可以搜索他们

## <a name="perform-actions-on-content-you-find"></a>对找到的内容执行操作

运行搜索并在必要时进行优化后，下一步是对搜索返回的结果执行一些操作。 可以将结果导出并下载到本地计算机，或在组织受到电子邮件攻击的情况下，可以从用户邮箱中删除搜索结果。
  
- [导出内容搜索的结果，](export-search-results.md) 并下载到本地计算机

- [搜索并删除电子邮件，](search-for-and-delete-messages-in-your-organization.md)例如包含病毒、危险附件或网络钓鱼邮件的邮件

- [导出有关](export-a-content-search-report.md) 内容搜索结果的报告，而不导出实际结果

## <a name="learn-more-about-content-search"></a>详细了解内容搜索

内容搜索易于使用，但它也是一个强大的工具。 在后台，会进行很多操作。 你越了解它并了解它的行为及其限制，你越成功地使用它以满足组织的搜索和调查需求。 了解以下信息：
  
- [网站和](partially-indexed-items-in-content-search.md)网站中的部分Exchange索引SharePoint以及如何在导出和下载搜索结果时包含或排除这些项

- [调查部分索引](investigating-partially-indexed-items-in-ediscovery.md) 项并确定组织对这些项目的曝光

- [内容搜索工具](limits-for-content-search.md)的限制，例如一次可以运行的最大搜索数和可以包含在单个搜索中的最大内容位置数

- [估计和实际搜索结果](differences-between-estimated-and-actual-ediscovery-search-results.md) 以及当您导出和下载搜索结果时它们之间可能存在差异的原因

- [导出作为搜索结果](de-duplication-in-ediscovery-search-results.md) 的电子邮件时可以启用的搜索结果中的重复数据删除

## <a name="use-scripts-for-advanced-scenarios"></a>将脚本用于高级方案

有时，您必须执行更高级、更复杂且重复的内容搜索任务。 在这些情况下，使用安全与合规中心 PowerShell 中的命令&快捷。 为了帮助简化这一过程，我们已创建多个安全与合规& PowerShell 脚本，以帮助你完成与内容搜索相关的复杂任务。

- [当您确信对](use-content-search-for-targeted-collections.md) 案例做出响应 (位于该文件夹中时，搜索特定邮箱和网站文件夹) 称为 *目标集合的邮箱和网站文件夹

- [搜索邮箱OneDrive](search-the-mailbox-and-onedrive-for-business-for-a-list-of-users.md)搜索用户列表

- [创建、报告并删除多个搜索](create-report-on-and-delete-multiple-content-searches.md) ，以快速高效地标识和剔除搜索数据

- [克隆内容搜索](clone-a-content-search.md) 并快速比较在同一内容位置运行的不同关键字搜索查询的结果;或使用脚本节省时间，而无需在创建新搜索时重新输入大量内容位置