---
title: EOP 中的功能权限
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 34674847-a6b7-4a7e-9eaa-b64f22bc150d
description: 了解独立 Exchange Online Protection 中的任务所需的权限
ms.openlocfilehash: 2f653fbae49087b8fc1ebc3a97586512965df970
ms.sourcegitcommit: 6a1a8aa024fd685d04da97bfcbc8eadacc488534
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/12/2020
ms.locfileid: "46652893"
---
# <a name="permissions-in-standalone-eop"></a>独立 EOP 中的权限

独立 Exchange Online Protection (EOP) 如果没有 Exchange Online 邮箱，则使用基于角色的访问控制 (RBAC) 权限模型来轻松地向管理员授予权限。 您可以使用独立 EOP 中的权限功能，快速设置并运行新组织。

若要向用户授予权限，请参阅[在 EOP 中管理管理员角色组](manage-admin-role-group-permissions-in-eop.md)。

有关跨 Microsoft 365 的权限的详细信息，请参阅[关于管理员角色](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)。

## <a name="role-based-permissions"></a>基于角色的权限

授予用户的管理员权限基于管理角色。 管理角色定义了可用于一组给定任务的 cmdlet。 由于 Exchange 管理中心 (EAC) 和独立 EOP PowerShell 都使用 cmdlet，因此授予对 cmdlet 的访问权限将使用户能够在 EAC 或独立 EOP PowerShell 中执行相关任务。 例如，"邮件收件人" 角色定义修改邮件用户所需的 cmdlet。

在独立 EOP 中，只有在没有最终用户角色或角色分配策略) 的情况下，管理角色才是唯一可用的管理角色类型 (。

## <a name="role-groups"></a>角色组

为了便于向用户分配角色，独立 EOP 使用角色组。 将管理角色分配给角色组，角色组成员将获得与角色相关联的权限。 换言之，管理角色不会直接分配给用户;它们已分配给角色组。 此模型允许一次将许多角色分配给许多角色组成员。 角色组成员可以是邮件用户、已启用邮件的安全组、Microsoft 365 管理中心的用户以及其他角色组。

下图显示了用户、角色组和角色之间的关系。

![角色、角色组和成员关系](../../media/ITPro_Security_RBAC_EXO_SimplifiedRoleGroupRelationship.png)

下表介绍了独立 EOP 中可用的角色组。

****

|角色组|说明|分配的默认角色|
|---|---|---|
|ComplianceManagement|配置和管理组织中的合规性设置，包括数据丢失防护 (DLP) （如果你的订阅具有 DLP 功能）。 <br/><br/> Azure AD 中[合规性管理员](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#compliance-administrator)角色的成员将自动获取此角色组的权限。|审核日志 <br/><br/> 合规性管理 <br/><br/> 信息权限管理 <br/><br/> 保留管理 <br/><br/> 仅查看审核日志 <br/><br/> 仅查看配置 <br/><br/> 仅查看收件人|
|ContentExplorerContentViewer|未使用。|数据分类内容查看器|
|ContentExplorerListViewer|未使用。|数据分类列表查看器|
|技术|查看和管理邮件用户。|重置密码 <br/><br/> 用户选项 <br/><br/> 仅查看收件人|
|HygieneManagement|管理 (反垃圾邮件、反恶意软件等 ) 的保护功能。|传输卫生 <br/><br/> 仅查看配置 <br/><br/> 仅查看收件人|
|MailFlowAdministrator|查看和管理接受的域和连接器|远程和接受域 <br/><br/> 仅查看收件人|
|OrganizationManagement|对整个组织的管理员访问权限以及执行几乎所有任务的能力。 <br/><br/> Azure AD 中[全局管理员](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-administrator--company-administrator)角色的成员会自动获取此角色组的权限。 <br/><br/> **重要说明**：由于 OrganizationManagement 角色组是一个功能强大的角色，因此只有执行组织级别管理任务的用户才应该是此角色组的成员。|恶意 <br/><br/> 反垃圾邮件 <br/><br/> 审核日志 <br/><br/> 合规性管理员 <br/><br/> 动态通讯组 <br/><br/> 信息权限管理 <br/><br/> 邮件收件人创建 <br/><br/> 邮件收件人 <br/><br/> 邮件跟踪 <br/><br/> 迁移 <br/><br/> 组织客户端访问 <br/><br/> 组织配置 <br/><br/> 组织传输设置 <br/><br/> 隔离 <br/><br/> 收件人策略 <br/><br/> 远程和接受域 <br/><br/> 重置密码 <br/><br/> 保留管理 <br/><br/> 角色管理 <br/><br/> 安全管理员 <br/><br/> 安全组创建和成员身份 <br/><br/> 安全读取者 <br/><br/> 敏感度标签管理员 <br/><br/> 监督 <br/><br/> 传输卫生 <br/><br/> 传输规则 <br/><br/> 用户选项 <br/><br/> 仅查看反恶意软件 <br/><br/> 仅查看反垃圾邮件 <br/><br/> 仅查看审核日志 <br/><br/> 仅查看配置 <br/><br/> 仅查看隔离 <br/><br/> 仅查看收件人 <br/><br/> 仅查看威胁智能|
|QuarantineAdministrator|管理所有收件人的已隔离邮件。|隔离|
|RecipientManagement|创建、管理和删除组织中的收件人对象。|动态通讯组 <br/><br/> 邮件收件人创建 <br/><br/> 邮件收件人 <br/><br/> 邮件跟踪 <br/><br/> 迁移 <br/><br/> 收件人策略 <br/><br/> 重置密码|
|Ecm.recordsmanagement|配置合规性功能，如保留策略标记、邮件分类和邮件流规则 (也称为传输规则) 。|邮件跟踪 <br/><br/> 保留管理 <br/><br/> 传输规则|
|SecurityAdministrator|在组织中配置保护的所有方面 (反垃圾邮件、反恶意软件、反欺骗、隔离、等等 ) 。 <br/><br/> Azure AD 中的[安全管理员](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator)角色的成员将自动获取此角色组的权限。|恶意 <br/><br/> 反垃圾邮件 <br/><br/> 审核日志 <br/><br/> 隔离 <br/><br/> 安全管理员 <br/><br/> 敏感度标签管理员 <br/><br/> 仅查看反恶意软件 <br/><br/> 仅查看反垃圾邮件 <br/><br/> 仅查看审核日志 <br/><br/> 仅查看隔离 <br/><br/> 仅查看威胁智能|
|SecurityReader|仅查看对组织中的所有保护的各个方面的访问 (反垃圾邮件、反恶意软件、反欺骗、隔离等 ) 。 <br/><br/> Azure AD 中的[安全读者](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-reader)角色的成员将自动获取此角色组的权限。|安全读取者 <br/><br/> 仅查看反恶意软件 <br/><br/> 仅查看反垃圾邮件 <br/><br/> 仅查看隔离 <br/><br/> 仅查看威胁智能|
|TenantAdmins|此角色组中的成员身份将跨服务同步并集中管理。 默认情况下，不会向此角色组分配任何角色。 但是，它将是 "组织管理" 角色组的成员，并将继承这些权限。|无|
|ViewOnlyOrganizationManagement|查看组织中的收件人、保护和配置对象及其属性。|合规性管理员 <br/><br/> 安全管理员 <br/><br/> 安全读取者 <br/><br/> 敏感度标签管理员 <br/><br/> 仅查看配置 <br/><br/> 仅查看收件人|
|

如果您在只有几个管理员的小型组织中工作，则可能需要仅将这些用户添加到组织管理角色组中，并且您可能永远不需要使用其他角色组。 如果您在更大的组织中工作，可能会有管理员执行特定任务，如收件人配置。 在这些情况下，您可以将一个管理员添加到 "收件人管理" 角色组，并将另一个管理员添加到 "组织管理" 角色组。 然后，这些管理员可以管理自己的特定区域，但他们不会拥有管理其不负责的区域的权限。

如果 Exchange Online 中的内置角色组与管理员的工作职能不匹配，可以创建角色组并向其中添加角色。 有关详细信息，请参阅[在独立 EOP 中管理角色组](manage-admin-role-group-permissions-in-eop.md)。

## <a name="roles"></a>角色

在独立 EOP 中可用的内置角色如下表所述。

****

|Role * *|说明|默认角色组分配|
|---|---|---|
|恶意|查看和修改反恶意软件功能的配置和报告。|OrganizationManagement <br/><br/> SecurityAdministrator|
|反垃圾邮件|查看和修改反垃圾邮件功能的配置和报告。|OrganizationManagement <br/><br/> SecurityAdministrator|
|审核日志|搜索管理员审核日志并查看结果。|ComplianceManagement <br/><br/> OrganizationManagement <br/><br/> SecurityAdministrator|
|合规性管理员<sup>\*</sup>||ComplianceManagement <br/><br/> OrganizationManagement <br/><br/> ViewOnlyOrganizationManagement|
|数据分类内容查看器<sup>\*</sup>||ContentExplorerContentViewer|
|数据分类列表查看器<sup>\*</sup>||
|动态通讯组|创建和管理所有通讯组、启用邮件的安全组和成员。|OrganizationManagement <br/><br/> RecipientManagement|
|信息权限管理<sup>\*</sup>||ComplianceManagement <br/><br/> OrganizationManagement|
|邮件收件人创建|创建和删除邮件用户。|OrganizationManagement <br/><br/> RecipientManagement|
|邮件收件人|修改现有的邮件用户。|OrganizationManagement <br/><br/> RecipientManagement|
|邮件跟踪<sup>\*</sup>||OrganizationManagement <br/><br/> RecipientManagement <br/><br/> 记录管理|
|迁移<sup>\*</sup>||OrganizationManagement <br/><br/> RecipientManagement|
|MyBaseOptions|允许用户查看其自己的隔离邮件。 <br/><br/> 此角色将自动分配给用户，无法手动分配。|无|
|组织客户端访问<sup>\*</sup>||OrganizationManagement|
|组织配置|查看报告。|OrganizationManagement|
|组织传输设置<sup>\*</sup>||OrganizationManagement|
|隔离|管理所有收件人的所有隔离邮件类型。|OrganizationManagement <br/><br/> QuarantineAdministrator <br/><br/> SecurityAdministrator|
|收件人策略<sup>\*</sup>||OrganizationManagement <br/><br/> RecipientManagement|
|远程和接受域|管理远程域、接受域和连接器。|MailFlowAdministrator <br/><br/> OrganizationManagement|
|重置密码<sup>\*</sup>||技术 <br/><br/> OrganizationManagement <br/><br/> RecipientManagement|
|保留管理<sup>\*</sup>||ComplianceManagement <br/><br/> OrganizationManagement <br/><br/> Ecm.recordsmanagement|
|角色管理|创建和管理角色组。|OrganizationManagement|
|安全管理员|管理所有安全和保护功能的配置和报告。|OrganizationManagement <br/><br/> SecurityAdministrator <br/><br/> ViewOnlyOrganizationManagement|
|安全组创建和成员身份|创建和管理启用邮件的安全组。|OrganizationManagement|
|安全读取者|查看安全和保护功能的配置和报告。|组织管理 <br/><br/> SecurityReader <br/><br/> ViewOnlyOrganizationManagement|
|敏感度标签管理员<sup>\*</sup>||OrganizationManagement <br/><br/> SecurityAdministrator <br/><br/> ViewOnlyOrganizationManagement|
|监控<sup>\*</sup>||OrganizationManagement|
|传输卫生|管理反恶意软件、反垃圾邮件功能和反欺骗功能。|HygieneManagement <br/><br/> OrganizationManagement|
|传输规则|创建和管理邮件流规则 (也称为传输规则) 。|OrganizationManagement <br/><br/> Ecm.recordsmanagement|
|用户选项|修改现有的邮件用户。|技术 <br/><br/> OrganizationManagement|
|仅查看反恶意软件|查看有关反恶意软件功能的配置和报告。|OrganizationManagement <br/><br/> SecurityAdministrator <br/><br/> SecurityReader|
|仅查看反垃圾邮件|查看反垃圾邮件功能的配置和报告。|OrganizationManagement <br/><br/> SecurityAdministrator <br/><br/> SecurityReader|
|仅查看审核日志|搜索管理员审核日志并查看结果。|ComplianceManagement <br/><br/> OrganizationManagement <br/><br/> SecurityAdministrator|
|仅查看配置|查看组织中的所有组织和邮件流 (非收件人) 设置。|ComplianceManagement <br/><br/> HygieneManagement <br/><br/> OrganizationManagement <br/><br/> ViewOnlyOrganizationManagement|
|仅查看隔离|查看所有收件人的所有已隔离邮件。|OrganizationManagement <br/><br/> SecurityAdministrator <br/><br/> SecurityReader|
|仅查看收件人|查看收件人属性并运行邮件跟踪。|ComplianceManagement <br/><br/> 技术 <br/><br/> HygieneManagement <br/><br/> MailFlowAdministrator <br/><br/>  OrganizationManagement <br/><br/> ViewOnlyOrganizationManagement|
|仅查看威胁智能<sup>\*</sup>||OrganizationManagement <br/><br/> SecurityAdministrator <br/><br/> SecurityReader|
|

<sup>\*</sup>虽然此角色可用，但在独立 EOP 中基本上没什么用处。

## <a name="microsoft-365-permissions-in-standalone-eop"></a>独立 EOP 中的 Microsoft 365 权限

在 Microsoft 365 管理中心创建用户时，可以选择是否向用户分配各种管理角色，如全局管理员、服务管理员、密码管理员等。 某些（而非全部） Microsoft 365 角色授予用户在 EOP 中的管理权限。

> [!NOTE]
> 用于创建独立 EOP 组织的帐户将自动分配给全局管理员角色。

下表列出了 Microsoft 365 角色以及它们对应的独立 EOP 角色组。 有关这些角色的详细信息，请参阅[关于管理员角色](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)。

****

|Microsoft 365 角色|EOP 角色组|
|---|---|
|Exchange 管理员|OrganizationManagement|
|全局管理员|OrganizationManagement <br/><br/> **注意**：全局管理员角色和 OrganizationManagement 角色组使用特殊的公司管理员角色组关联在一起。 公司管理员角色组是内部管理的，不能直接修改。|
|密码管理员|技术|
|全局读取者|ViewOnlyOrganizationManagement|
|安全管理员|SecurityAdministrator|
|安全读者|SecurityReader|
|

其他 Microsoft 365 角色没有相应的 EOP 角色组，也不会在 EOP 中授予管理权限。 有关将 Microsoft 365 角色分配给用户的详细信息，请参阅[分配管理员角色](https://docs.microsoft.com/microsoft-365/admin/add-users/assign-admin-roles)。

可以在 EOP 中向用户授予管理权限，而无需将其添加到 Microsoft 365 角色。 为此，请将用户添加为 EOP 角色组的成员。 用户将在 EOP 中获取权限，但他们不会在其他 Microsoft 365 工作负荷中获取权限。

### <a name="how-do-you-know-this-worked"></a>如何知道操作成功？

若要验证是否已成功复制角色组，请执行以下步骤之一：

- 在 EAC 中，转到 "**权限** \> " "**管理员角色**"，并验证角色组是否 (列出，或者是否未列出) 。 选择角色组，并验证详细信息窗格中的设置，或单击 "**编辑** ![ 编辑图标 ](../../media/ITPro-EAC-EditIcon.png) " 以验证设置。

- 在 Exchange Online PowerShell 中，将替换 \<Role Group Name\> 为角色组的名称，然后运行以下命令来验证角色组是否存在 (或不存在) 并验证设置：

    ```PowerShell
    Get-RoleGroup -Identity "<Role Group Name>" | Format-List
    ```
