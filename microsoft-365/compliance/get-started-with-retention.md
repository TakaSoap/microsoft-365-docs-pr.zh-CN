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
ms.localizationpriority: high
ms.collection:
- M365-security-compliance
- SPO_Content
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: 已准备好实现保留策略和保留标签来管理组织的数据，但不确定从哪里入手？请阅读一些实用指南来入门。
ms.openlocfilehash: 5d1566cc5840b93a4d3a994004ea0e1d52e01bb6
ms.sourcegitcommit: dc26169e485c3a31e1af9a5f495be9db75c49760
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2021
ms.locfileid: "60757354"
---
# <a name="get-started-with-retention-policies-and-retention-labels"></a>开始使用保留策略和保留标签

>*[Microsoft 365 安全性与合规性许可指南](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)。*

已准备好通过保留需要保留的内容和删除不需要的内容来开始管理组织的数据？使用以下指南来入门：

1. **了解保留在 Microsoft 365 中的工作原理**，然后确定是需要使用保留策略还是保留标签，亦或是两者的组合：[了解保留](retention.md)

2. **确定组织策略或行业法规所要求的保留设置和操作**。
    
    在此评估过程中，请确定是否将使用[记录管理](records-management.md)。

3. 根据已确定的保留设置和操作，**创建保留策略和保留标签**。
    
    对于保留标签，你可能会发现使用[文件计划](file-plan-manager.md)在电子表格中定义和优化保留标签很有用。然后，导入相应电子表格来创建标签。
    
3. **发布并应用保留标签**。 保留策略是为“一次设置、后顾无忧”配置而设计的，而保留标签是可重用的构建基块，可用于多个策略中，并可纳入用户工作流中。 请参阅[常见应用场景](#common-scenarios-for-retention-policies-and-retention-labels)列表，此列表有助于确定如何使用保留标签。 

## <a name="subscription-and-licensing-requirements-for-retention-policies-and-retention-labels"></a>保留策略和保留标签的订阅和许可要求

许多不同的订阅都支持保留策略和保留标签，用户的许可要求取决于你使用的功能。

若要查看许可用户以便受益于 Microsoft 365 合规性功能的选项，请参阅 [Microsoft 365 安全性与合规性许可指南](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)。 对于保留，请参阅[信息治理](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-governance)部分和相关 PDF 下载内容，以了解功能级别许可要求。

## <a name="permissions-required-to-create-and-manage-retention-policies-and-retention-labels"></a>创建和管理保留策略和保留标签所需的权限

负责创建和管理保留策略和保留标签的合规性团队成员必须有权访问 <a href="https://go.microsoft.com/fwlink/p/?linkid=2077149" target="_blank">Microsoft 365 合规中心</a>。 默认情况下，租户管理员（全局管理员）有权访问此位置，并可向合规专员和其他人提供访问权限，而不为其提供租户管理员的所有权限。若要授予实现此有限管理的权限，建议将用户添加到 **合规性管理员** 管理角色组。

除了使用该默认角色，还可创建一个新的角色组，并将 **保留管理** 角色添加到该组。对于只读角色，请使用 **只查看保留管理**。 

有关将用户添加到默认角色或创建自己的角色组的说明，请参阅 [Microsoft 365 合规中心中的权限](microsoft-365-compliance-center-permissions.md)。

只有在创建、配置和应用保留策略和保留标签时才需要这些权限。 配置这些策略及标签的人员不需要访问该内容。

## <a name="common-scenarios-for-retention-policies-and-retention-labels"></a>保留策略和保留标签的常见应用场景

请使用下表来帮助你将业务需求映射到保留策略和保留标签支持的保留应用场景。

|我想...|文档|
|----------------|---------------|
|高效地按 Microsoft 365 服务设置保留和删除操作： <br />- Exchange  <br />- SharePoint  <br />- OneDrive  <br />- Microsoft 365 组 <br />- Skype for Business  <br />- Microsoft Teams <br />- Yammer 网络 |[创建和配置保留策略](create-retention-policies.md)|
|让管理员和用户手动为文档和电子邮件应用保留和删除操作： <br />- SharePoint <br />- OneDrive <br />- Outlook 和 Outlook 网页版|[创建保留标签并在应用中应用它们](create-apply-retention-labels.md)|
|让网站管理员为 SharePoint 库、文件夹或文档集中的所有内容设置默认保留和删除操作|[创建保留标签并在应用中应用它们](create-apply-retention-labels.md)|
|让用户使用 Outlook 规则向电子邮件自动应用保留和删除操作|[创建保留标签并在应用中应用它们](create-apply-retention-labels.md)|
|让管理员向文档理解模型应用保留和删除操作，以便将这些操作自动应用于 SharePoint 库中已标识的文档|[创建保留标签并在应用中应用它们](create-apply-retention-labels.md)|
|向文档和电子邮件自动应用保留和删除操作 |[自动向内容应用保留标签](apply-retention-labels-automatically.md)|
|从事件发生时开始计算保留期，比如：  <br />- 员工离开组织 <br />- 合同到期 <br />- 产品生存期结束| [从事件发生时开始计算保留期](event-driven-retention.md)|
|限制对策略的更改，以帮助满足管理法规要求或防止恶意管理员| [使用保留锁定来限制对保留策略和保留标签策略的更改](retention-preservation-lock.md)
|确保内容在内容保留期结束时被删除之前，有人进行评审和批准|[处置评审](disposition.md#disposition-reviews) |
| 监视将保留和删除设置应用于项目的方式和位置 | [监视保留标签](retention.md#monitoring-retention-labels) |
|将一个记录管理解决方案同时用于文档和电子邮件 |[了解记录管理](records-management.md) |

如果将保留标签用于记录管理，则对于将内容标记为记录的保留标签，还有其他一些特有的方案。请参阅[记录管理常见方案](get-started-with-records-management.md#common-scenarios-for-records-management)。

## <a name="end-user-documentation-for-retention"></a>保留的最终用户文档

大多数保留策略在后台运行，且无需用户交互，因此用户需要的文档很少。 删除邮件后，Teams 的保留策略会通知用户，并包含指向 Teams 中有关保留策略 [保留策略](https://support.microsoft.com/office/teams-messages-about-retention-policies-c151fa2f-1558-4cf9-8e51-854e925b483b)。

由于保留标签在 Microsoft 365 应用中具有 UI 状态，因此在将标签部署到生产网络之前，请确保为最终用户和技术支持人员提供指导。 要帮助用户在 SharePoint 和 OneDrive 中应用保留标签，请参阅[将保留标签应用于 SharePoint 或 OneDrive 中的文件](https://support.microsoft.com/office/apply-retention-labels-to-files-in-sharepoint-or-onedrive-11a6835b-ec9f-40db-8aca-6f5ef18132df)。

不过，最有效的最终用户文档将是你针对所选保留标签名称和配置提供的定制指南和说明。 请参阅以下页面，并下载可用于帮助培训用户的内容：[有关保留标签的最终用户培训](https://microsoft.github.io/ComplianceCxE/enduser/retention/)。