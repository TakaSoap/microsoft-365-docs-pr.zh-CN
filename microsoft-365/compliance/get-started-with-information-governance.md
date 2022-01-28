---
title: 开始使用 Microsoft 365 中的信息治理
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
ms.custom: admindeeplinkCOMPLIANCE
search.appverid:
- MOE150
- MET150
description: 已准备好开始治理组织数据，但不确定从哪里开始? 阅读一些说明性指南以开始使用。
ms.openlocfilehash: 5b30dc870389c06bd006a056127439f1ec18ac65
ms.sourcegitcommit: 400ef9ac34247978e3de7ecc0b376c4abb6c99d8
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/27/2022
ms.locfileid: "62242124"
---
# <a name="get-started-with-information-governance"></a>开始使用信息治理

>*[Microsoft 365 安全性与合规性许可指南](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)。*

已准备好通过保留需要保留的内容和删除不需要的内容来开始管理组织的数据？使用以下指南来入门：

1. **了解 Microsoft 365 中保留和删除的工作原理**，然后确定需要保留策略的工作负载以及是否需要为异常创建保留标签: [了解保留](retention.md)
    
    > [!NOTE]
    > 如果需要对高价值项目进行生命周期管理以满足业务、法律或法规上的记录保持要求: 将保留标签与 [记录管理](records-management.md) (而非信息治理)结合使用。

2. **为已确定的工作负载创建保留策略**，指定组织策略或行业法规要求的保留设置和操作: [创建保留策略](create-retention-policies.md)
    
    如果需要，[为异常创建并应用保留标签](create-retention-labels-information-governance.md)。

3. **启用邮箱存档**，从而为用户提供额外的邮箱存储空间: [在合规中心内启用存档邮箱](enable-archive-mailboxes.md)
    
    如果需要支持存档邮箱:
    
    - [为需要 100 GB 存储以上的邮箱启用自动扩展存档](enable-autoexpanding-archiving.md)。
    
    - 如果需要自定义电子邮件从用户的主邮箱自动移动到其存档邮箱的方式，或者需要为特定文件夹(而非整个邮箱)指定保留和删除设置，请将 [保留标记与邮件传递记录管理(MRM)的保留策略结合使用](set-up-an-archive-and-deletion-policy-for-mailboxes.md)。

4. 在员工离开组织后，**了解并管理保留邮箱内容的非活动邮箱**: [了解非活动邮箱](inactive-mailboxes-in-office-365.md)

5. 如果有 PST 文件包含想要治理的数据: 使用网络上传或驱动器传送以 **将 PST 文件导入联机邮箱**: [了解如何导入组织的 PST 文件](importing-pst-files-to-office-365.md)

独立于这些步骤，**使用连接器以导入并存档第三方数据**，其中包含来自社交媒体平台、即时消息平台以及文档协作平台的数据。 当将此数据导入联机邮箱时，其不仅支持 Microsoft 365 合规中心的信息治理，还支持通信合规性、内部风险管理和电子数据展示等其他合规性解决方案。 有关详细信息，请参阅 [了解第三方数据的连接器](archiving-third-party-data.md)。

## <a name="subscription-and-licensing-requirements"></a>订阅和许可要求

许多不同的订阅都支持信息治理功能。

若要查看许可用户以便受益于 Microsoft 365 合规性功能的选项，请参阅 [Microsoft 365 安全性与合规性许可指南](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)。 有关此页上列出的功能，请参阅 [信息治理](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-governance) 节以及功能级别许可要求的相关 [PDF 下载](https://go.microsoft.com/fwlink/?linkid=2139145)。

## <a name="permissions"></a>权限

有关用于管理 Microsoft 365 保留的角色和角色组的信息，请参阅以下节。

对于管理邮箱(存档、非活动邮箱和导入)的权限，这些操作通常需要邮件收件人角色等 Exchange 权限。 默认情况下，此角色分配给“收件人管理”和“组织管理”角色组。 有关每个管理任务的准确权限要求，请参阅管理员说明随附的文档。

### <a name="permissions-for-retention-policies-and-retention-labels"></a>保留策略和保留标签的权限

负责创建和管理保留策略和保留标签的合规性团队成员必须有权访问 <a href="https://go.microsoft.com/fwlink/p/?linkid=2077149" target="_blank">Microsoft 365 合规中心</a>。 默认情况下，租户管理员（全局管理员）有权访问此位置，并可向合规专员和其他人提供访问权限，而不为其提供租户管理员的所有权限。若要授予实现此有限管理的权限，建议将用户添加到 **合规性管理员** 管理角色组。

除了使用该默认角色，还可创建一个新的角色组，并将 **保留管理** 角色添加到该组。对于只读角色，请使用 **只查看保留管理**。 

有关将用户添加到默认角色或创建自己的角色组的说明，请参阅 [Microsoft 365 合规中心中的权限](microsoft-365-compliance-center-permissions.md)。

只有在创建、配置和应用保留策略和保留标签时才需要这些权限。 配置这些策略及标签的人员不需要访问该内容。

## <a name="common-scenarios"></a>常见方案

使用下表以帮助你将业务要求映射到信息治理的最常见场景中。

|我想...|文档|
|----------------|---------------|
|高效保留或删除 Microsoft 365 服务的数据: <br />- Exchange  <br />- SharePoint  <br />- OneDrive  <br />- Microsoft 365 组 <br />- Teams <br />- Yammer <br />- Skype for Business |[创建和配置保留策略](create-retention-policies.md)|
|为用户提供额外的邮箱存储 |[在合规性中心中启用存档邮箱](enable-archive-mailboxes.md)|
|在员工离开组织后，保留邮箱数据 |[创建和管理非活动邮箱](create-and-manage-inactive-mailboxes.md)|
|从 PST 文件上传邮箱数据 |[使用网络上传导入 PST 文件](use-network-upload-to-import-pst-files.md)|


如果有需要对单个项目进行生命周期管理的场景，请参阅 [记录管理的常见场景](get-started-with-records-management.md#common-scenarios)。 

## <a name="end-user-documentation"></a>最终用户文档

有关支持 Microsoft 365 保留的最终用户文档的信息，请参阅以下节。

支持邮箱管理(存档、非活动邮箱和导入)的信息治理功能通常无需最终用户文档。

### <a name="end-user-documentation-for-retention-and-deletion"></a>用于保留和删除的最终用户文档

大多数保留策略在后台运行，且无需用户交互，因此用户需要的文档很少。 删除邮件后，Teams 的保留策略会通知用户，并包含指向 Teams 中有关保留策略 [保留策略](https://support.microsoft.com/office/teams-messages-about-retention-policies-c151fa2f-1558-4cf9-8e51-854e925b483b)。

但是，如果使用保留标签补充保留策略，则这些标签在Microsoft 365 应用中确实存在 UI。 在将这些标签部署到生产网络之前，请确保为最终用户和支持人员提供信息和说明。 要帮助用户在 SharePoint 和 OneDrive 中应用保留标签，请参阅[将保留标签应用于 SharePoint 或 OneDrive 中的文件](https://support.microsoft.com/office/apply-retention-labels-to-files-in-sharepoint-or-onedrive-11a6835b-ec9f-40db-8aca-6f5ef18132df)。

最有效的最终用户文档将始终是你为所选的保留标签名称和配置提供的自定义指南和说明。 请参阅以下页面，并下载可用于帮助培训用户的内容：[有关保留标签的最终用户培训](https://microsoft.github.io/ComplianceCxE/enduser/retention/)。

