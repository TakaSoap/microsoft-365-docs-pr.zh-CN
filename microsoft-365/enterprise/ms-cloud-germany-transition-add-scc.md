---
title: 从德国 Microsoft 云迁移期间电子数据展示体验的信息
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/01/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Ent_TLGs
description: 摘要：从德国 Microsoft 云迁移电子数据展示迁移步骤。
ms.openlocfilehash: afea899e06a732ff0ab13bf416410aa94bc3c191
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60168442"
---
# <a name="information-about-the-ediscovery-experience-during-the-migration-from-microsoft-cloud-deutschland"></a>从德国 Microsoft 云迁移期间电子数据展示体验的信息
以下各节提供有关从德国 Microsoft 云 (德国 microsoft 云迁移到新的德国数据中心) Office 365 服务时电子数据展示体验的其他信息。

## <a name="ediscovery-administration-until-phase-4"></a>第 4 阶段前电子数据展示管理
在第 4 阶段之前，安全与合规中心将完全可用。 所有内容仍保留在德国 Microsoft 云中，并且由德国 Microsoft 云安全与合规中心 https://protection.office.de/) (。

## <a name="ediscovery-experience-between-phase-4-until-the-the-end-of-phase-9"></a>阶段 4 到阶段 9 结束之间的电子数据展示体验
从阶段 4 开始到阶段 9 完成，电子数据展示搜索将失败或返回已迁移的 SharePoint Online、OneDrive for Business 和 Exchange Online 位置的 0 个结果。

> [!NOTE]
> 在迁移过程中，客户可以在安全与合规中心（包括内容搜索）&案例、保留、 [搜索](/microsoft-365/compliance/manage-legal-investigations)和 [导出](/microsoft-365/compliance/search-for-content)。 但是，针对 SharePoint Online、OneDrive for Business 和 Exchange Online 位置的搜索将返回 0 个结果或产生错误。

如果搜索在迁移过程中返回零结果或错误，请对 SharePoint Online 执行以下操作：

- 按照从 SharePoint 或 OneDrive for Business OneDrive 下载文件和文件夹中的说明，直接从 SharePoint Online 或 SharePoint[下载网站](https://support.office.com/article/download-files-and-folders-from-onedrive-or-sharepoint-5c7397b7-19c7-4893-84fe-d02e8fa5df05)。 此方法需要SharePoint联机管理员权限或只读权限。
- 如果超出限制，如从 OneDrive 或[SharePoint](https://support.office.com/article/download-files-and-folders-from-onedrive-or-sharepoint-5c7397b7-19c7-4893-84fe-d02e8fa5df05)下载文件和文件夹中介绍，客户可以按照 Sync SharePoint 中的指导使用 OneDrive for Business 同步客户端，并使用计算机下载[Teams 文件](https://support.office.com/article/sync-sharepoint-files-with-the-new-onedrive-sync-app-6de9ede8-5b6e-4503-80b2-6190f3354a88)。

- 有关详细信息，请参阅[In-Place eDiscovery in Exchange Server](/Exchange/policy-and-compliance/ediscovery/ediscovery)。


## <a name="ediscovery-administration-after-phase-9"></a>第 9 阶段之后电子数据展示管理

**适用于：** 使用电子数据展示的所有客户

在第 9 阶段，将完成移动到新的德国数据中心区域的最后步骤。 在此阶段，将迁移其余的所有服务组件。
在第 9 阶段之后，不再支持使用德国 Microsoft 云 (protection.office.de) 合规中心。 请改为使用新的[安全中心](https://security.microsoft.com/)[或合规中心](https://compliance.microsoft.com/)。 所有数据已迁移到新的管理门户。

| 步骤 ()  | 说明 | 影响 |
|:-------|:-------|:-------|
|  所有 SharePoint Online、OneDrive for Business 和 Exchange Online 位置已随安全与合规中心 (SCC) 。 | 所有电子数据展示活动都应从全球租户运行。 搜索现在将 100% 成功。 任何失败或错误应遵循正常支持渠道。 | 无 |
||||

### <a name="ediscovery-retention-policy"></a>电子数据展示保留策略
**适用于：**  作为迁移前步骤的一部分应用保留策略的所有客户

| 步骤 ()  | 说明 | 影响 |
|:-------|:-------|:-------|
| 删除在迁移前步骤期间创建的组织范围内的保留策略 | 客户可以删除在客户迁移前工作期间创建的组织范围的保留策略。 | 无 |
||||
