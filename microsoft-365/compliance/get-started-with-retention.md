---
title: 开始使用保留策略和保留标签
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: 已准备好实现保留策略和保留标签来管理组织的数据，但不确定从哪里入手？ 请阅读一些实用指南来入门。
ms.openlocfilehash: b390e4594d97e96eadac9541429a838abe006a3f
ms.sourcegitcommit: d988faa292c2661ffea43c7161aef92b2b4b99bc
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/04/2020
ms.locfileid: "46560759"
---
# <a name="get-started-with-retention-policies-and-retention-labels"></a>开始使用保留策略和保留标签

>*[Microsoft 365 安全性与合规性许可指南](https://aka.ms/ComplianceSD)。*

已准备好通过保留需要保留的内容和删除不需要的内容来开始管理组织的数据？ 请遵循下面的简要指南来入门：

1. **了解保留在 Microsoft 365 中的工作原理**，然后确定是需要使用保留策略还是保留标签，亦或是两者的组合：[了解保留](retention.md)

2. **确定组织策略或行业法规所要求的保留设置和操作**。
    
    在此评估过程中，请确定是否将使用[记录管理](records-management.md)。

3. 根据已确定的保留设置和操作，**创建保留策略和保留标签**。
    
    对于保留标签，你可能会发现使用[文件计划](file-plan-manager.md)在电子表格中定义和优化保留标签很有用。 然后，导入相应电子表格来创建标签。
    
3. **发布并应用保留标签**。 保留策略是为“一次设置、后顾无忧”配置而设计的，而保留标签是可重用的构建基块，可用于多个策略中，并可纳入用户工作流中。 请参阅[常见应用场景](#common-scenarios-for-retention-policies-and-retention-labels)列表，此列表有助于确定如何使用保留标签。 

## <a name="subscription-and-licensing-requirements-for-retention-policies-and-retention-labels"></a>保留策略和保留标签的订阅和许可要求

许多不同的订阅都支持保留策略和保留标签，用户的许可要求取决于你使用的功能。

若要查看许可用户以便受益于 Microsoft 365 合规性功能的选项，请参阅 [Microsoft 365 安全性与合规性许可指南](https://aka.ms/ComplianceSD)。 对于保留，请参阅[信息管理](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-governance)部分和相关 PDF 或 Excel 下载内容，以了解功能级别许可要求。

## <a name="permissions-required-to-create-and-manage-retention-policies-and-retention-labels"></a>创建和管理保留策略和保留标签所需的权限

负责创建和管理保留策略和保留标签的合规性团队成员必须有权访问 [Microsoft 365 合规中心](https://compliance.microsoft.com/)。 默认情况下，租户管理员（全局管理员）有权访问此位置，并可向合规专员和其他人提供访问权限，而不为其提供租户管理员的所有权限。若要授予实现此有限管理的权限，建议将用户添加到**合规性管理员**管理角色组。 有关说明，请参阅[向用户授予对安全与合规中心的访问权限](https://docs.microsoft.com/microsoft-365/security/office-365-security/grant-access-to-the-security-and-compliance-center)。

只有在创建和应用保留策略时才需要这些权限。 配置保留策略的人员不需要访问该内容。

## <a name="common-scenarios-for-retention-policies-and-retention-labels"></a>保留策略和保留标签的常见应用场景

请使用下表来帮助你将业务需求映射到保留策略和保留标签支持的保留应用场景。

|我想...|文档|
|----------------|---------------|
|高效地为组织或按 Microsoft 365 服务设置保留和删除操作： <br />- Exchange  <br />- SharePoint  <br />- OneDrive  <br />- Microsoft 365 组 <br />- Skype for Business  <br />- Microsoft Teams  |[创建和配置保留策略](create-retention-policies.md)|
|让管理员和用户手动为文档和电子邮件应用一组保留和删除操作： <br />- SharePoint <br />- OneDrive <br />- Outlook 和 Outlook 网页版|[创建保留标签并在应用中应用它们](create-apply-retention-labels.md)|
|让网站管理员为 SharePoint 库、文件夹或文档集中的所有内容设置默认保留标签|[创建保留标签并在应用中应用它们](create-apply-retention-labels.md)|
|让用户使用 Outlook 规则向电子邮件自动应用保留标签|[创建保留标签并在应用中应用它们](create-apply-retention-labels.md)|
|向文档和电子邮件自动应用一组保留和删除操作 |[自动向内容应用保留标签](apply-retention-labels-automatically.md)|
|从事件发生时开始计算保留期，比如：  <br />- 员工离开组织 <br />- 合同到期 <br />- 产品生存期结束| [从事件发生时开始计算保留期](event-driven-retention.md)|
|管理 SharePoint 中不同文档类型的生命周期| [使用保留标签管理 SharePoint 中存储的文档的生命周期](auto-apply-retention-labels-scenario.md)|
|将一个记录管理解决方案同时用于文档和电子邮件 |[Microsoft 365 中的记录管理](records-management.md) |
|遵守 SEC 规则 17a-4|[使用 Exchange Online 和安全与合规中心来遵守 SEC 规则 17a-4](use-exchange-online-to-comply-with-sec-rule-17a-4.md) |
|确保内容在内容保留期结束时被删除之前，有人进行评审和批准|[处置评审](disposition.md#disposition-reviews) |
|对在保留期结束时删除的内容有处置证明|[处置记录](disposition.md#disposition-of-records) |

## <a name="end-user-documentation-for-retention-labels"></a>保留标签的最终用户文档

与保留策略不同，保留标签在 Microsoft 365 应用中有 UI。 请务必在将保留标签部署到生产网络前，为最终用户和技术支持人员提供指导。

最有效的最终用户文档将是你针对所选保留标签名称和配置提供的定制指南和说明。 不过，可以使用以下信息作为基本说明：

- [手动应用保留标签](create-apply-retention-labels.md#manually-apply-retention-labels)
