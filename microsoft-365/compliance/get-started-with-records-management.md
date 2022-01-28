---
title: Microsoft 365 中的记录管理入门
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
ms.custom: admindeeplinkCOMPLIANCE
search.appverid:
- MOE150
- MET150
description: 需要用于管理高价值内容的 Microsoft 365 记录管理解决方案以满足法律、业务或法规方面的义务，但不确定从哪里入手？请阅读一些实用指南来入门。
ms.openlocfilehash: ba23aed20cbef05272bc33306df5fc1eebc6cb3f
ms.sourcegitcommit: 400ef9ac34247978e3de7ecc0b376c4abb6c99d8
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/27/2022
ms.locfileid: "62241175"
---
# <a name="get-started-with-records-management"></a>记录管理入门

>*[Microsoft 365 安全性与合规性许可指南](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)。*

准备好开始使用 Microsoft 365 中的记录管理解决方案来管理组织的高价值内容以满足法律、业务或法规方面的义务了吗？使用以下指南来入门：

1. **了解 Microsoft 365 中保留和删除的工作原理**，并确定是否需要使用保留策略来补充在项目级别管理文档和电子邮件的保留标签：[了解保留策略和保留标签](retention.md)
    
    如有必要，[创建保留策略](create-retention-policies.md)，以便跨 Microsoft 365 工作负荷对数据进行基线治理。
    
2. **了解记录管理解决方案** 以及在声明文档和电子邮件时如何使用保留标签来允许或阻止操作：[了解记录管理](records-management.md)

3. 通过导入现有计划（如果有）或创建新的保留标签 **为保留和删除设置和操作创建文件计划，以及设置何时应将项目标记为记录**：[使用文件计划创建和管理保留标签](file-plan-manager.md)

4. **发布并应用保留标签**。保留标签是可重用的构建基块，可用于多个策略中，并可纳入用户工作流中：

    - [创建保留标签并在应用中应用它们](create-apply-retention-labels.md)
    - [自动向内容应用保留标签](apply-retention-labels-automatically.md)

在这些步骤之外，**使用连接器以导入并存档第三方数据**，其中包含来自社交媒体平台、即时消息平台以及文档协作平台的数据。 当将此数据导入联机邮箱时，其不仅支持 Microsoft 365 合规中心的记录管理，还支持通信合规性、内部风险管理和电子数据展示等其他合规性解决方案。 有关详细信息，请参阅[了解第三方数据的连接器](archiving-third-party-data.md)。

## <a name="subscription-and-licensing-requirements"></a>订阅和许可要求

许多不同的订阅都支持记录管理，并且用户的许可要求取决于你使用的功能。

若要查看许可用户以便受益于 Microsoft 365 合规性功能的选项，请参阅 [Microsoft 365 安全性与合规性许可指南](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)。 对于记录管理，请参阅[记录管理](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#records-management)部分和相关 PDF 下载内容，以了解功能级别许可要求。

## <a name="permissions"></a>权限

负责记录管理的合规性团队成员必须有权访问 <a href="https://go.microsoft.com/fwlink/p/?linkid=2077149" target="_blank">Microsoft 365 合规中心</a>。默认情况下，租户管理员（全局管理员）有权访问此位置，并可向合规专员和其他人提供访问权限，而不为其提供租户管理员的所有权限。为了授予该有限管理权限，建议将用户添加至授予所有与记录管理相关的功能的权限的 **记录管理** 管理员角色组，其中包括 [处置审查和验证](disposition.md)。

对于只读角色，可以创建新的角色组，并将 **只读记录管理** 角色添加到该组中。

有关将用户添加到默认角色或创建自己的角色组的说明，请参阅 [Microsoft 365 合规中心中的权限](microsoft-365-compliance-center-permissions.md)。

只有在创建、配置和应用用于声明记录和管理处置的保留标签时才需要这些权限。 配置这些标签的人员不需要访问该内容。

## <a name="common-scenarios"></a>常见方案

请使用下表将业务需求与记录管理支持的方案对应起来。

> [!TIP]
> 需要遵守特定的行业法规？ 有关特定法规的指南，请查看[信息管理和记录管理的法规要求](retention-regulatory-requirements.md)。

|我想...|文档|
|----------------|---------------|
|声明记录 |[使用保留标签声明记录](declare-records.md)|
|更新记录 |[使用记录版本控制来更新存储在 SharePoint 或 OneDrive 中的记录](record-versioning.md)|
|让管理员和用户手动为文档和电子邮件应用保留和删除操作： <br />- SharePoint <br />- OneDrive <br />- Outlook 和 Outlook 网页版|[创建保留标签并在应用中应用它们](create-apply-retention-labels.md)|
|让网站管理员为 SharePoint 库、文件夹或文档集中的所有内容设置默认保留和删除操作|[创建保留标签并在应用中应用它们](create-apply-retention-labels.md)|
|让用户使用 Outlook 规则向电子邮件自动应用保留和删除操作|[创建保留标签并在应用中应用它们](create-apply-retention-labels.md)|
|让管理员向文档理解模型应用保留和删除操作，以便将这些操作自动应用于 SharePoint 库中已标识的文档|[创建保留标签并在应用中应用它们](create-apply-retention-labels.md)|
|向文档和电子邮件自动应用保留和删除操作 |[自动向内容应用保留标签](apply-retention-labels-automatically.md)|
|从事件发生时开始计算保留期，比如：  <br />- 员工离开组织 <br />- 合同到期 <br />- 产品生存期结束| [从事件发生时开始计算保留期](event-driven-retention.md)|
|限制对策略的更改，以帮助满足管理法规要求或防止恶意管理员| [使用保留锁定来限制对保留策略和保留标签策略的更改](retention-preservation-lock.md)
|管理 SharePoint 中不同文档类型的生命周期| [使用保留标签管理 SharePoint 中存储的文档的生命周期](auto-apply-retention-labels-scenario.md)|
|确保内容在内容保留期结束时被删除之前，有人进行评审和批准|[处置评审](disposition.md#disposition-reviews) |
|对在保留期结束时永久删除的内容有处置证明|[处置记录](disposition.md#disposition-of-records) |
| 监视将保留和删除设置应用于项目的方式和位置 | [监视保留标签](retention.md#monitoring-retention-labels) |

## <a name="end-user-documentation"></a>最终用户文档

如果使用保留策略进行基线数据管理，它们通常在后台不显眼地工作，而无需用户交互。 因此，他们几乎不需要用户的文档。 删除邮件后，Teams 的保留策略会通知用户，并包含指向 Teams 中有关保留策略 [保留策略](https://support.microsoft.com/office/teams-messages-about-retention-policies-c151fa2f-1558-4cf9-8e51-854e925b483b)。

相比之下，保留标签在 Microsoft 365 应用中具有 UI 状态，因此在将标签部署到生产网络之前，请确保为最终用户和技术支持人员提供指导。 要帮助用户在 SharePoint 和 OneDrive 中应用保留标签，以及有关解锁记录以进行编辑的信息，请参阅[将保留标签应用于 SharePoint 或 OneDrive 中的文件](https://support.microsoft.com/office/apply-retention-labels-to-files-in-sharepoint-or-onedrive-11a6835b-ec9f-40db-8aca-6f5ef18132df)。

不过，最有效的最终用户文档将是你针对所选保留标签名称和配置提供的定制指南和说明。 请参阅以下页面，并下载可用于帮助培训用户的内容：[有关保留标签的最终用户培训](https://microsoft.github.io/ComplianceCxE/enduser/retention/)。
