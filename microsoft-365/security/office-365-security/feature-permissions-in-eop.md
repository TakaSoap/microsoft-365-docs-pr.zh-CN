---
title: EOP 中的功能权限
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 34674847-a6b7-4a7e-9eaa-b64f22bc150d
description: 了解独立 Exchange Online Protection 中的任务所需的权限
ms.openlocfilehash: f9c0f0549ba5a0a65fa3bbe3af1afbfddc6e735c
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826621"
---
# <a name="permissions-in-standalone-eop"></a>独立 EOP 中的权限

没有 Exchange Online 邮箱的 (Exchange Online Protection (EOP) 使用基于角色的访问控制 (RBAC) 权限模型轻松向管理员授予权限。 你可以使用独立 EOP 中的权限功能来快速设置并运行新组织。

若要向用户授予权限，请参阅["在 EOP 中管理管理员角色组"。](manage-admin-role-group-permissions-in-eop.md)

有关 Microsoft 365 中的权限的详细信息，请参阅 [关于管理员角色](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)。

## <a name="role-based-permissions"></a>基于角色的权限

授予用户的管理员权限基于管理角色。 管理角色定义可用于一组给定任务的 cmdlet。 由于 Exchange 管理中心 (EAC) 和独立 EOP PowerShell 都使用 cmdlet，因此授予对 cmdlet 的访问权限将给用户提供在 EAC 或独立 EOP PowerShell 中执行相关任务的权限。 例如，Mail Recipients 角色定义修改邮件用户所需的 cmdlet。

在独立 EOP 中，管理角色是可用的唯一管理角色 (没有最终用户角色或策略角色分配策略) 。

## <a name="role-groups"></a>角色组

为了更易于为用户分配角色，独立 EOP 使用角色组。 管理角色分配给角色组，角色组成员将获取与角色关联的权限。 换句话说，管理角色不会直接分配给用户;它们将分配给角色组。 此模型允许您同时将许多角色分配给许多角色组成员。 角色组成员可以是邮件用户、启用邮件的安全组、Microsoft 365 管理中心中的用户以及其他角色组。

下图显示了用户、角色组和角色之间的关系。

![角色、角色组和成员关系](../../media/ITPro_Security_RBAC_EXO_SimplifiedRoleGroupRelationship.png)

下表介绍了独立 EOP 中的可用角色组。

****

|角色组|说明|分配的默认角色|
|---|---|---|
|ComplianceManagement|在组织中配置和管理合规性设置，包括数据丢失 (DLP) （如果你的订阅具有 DLP 功能）。 <br/><br/> Azure AD [中合规性](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#compliance-administrator) 管理员角色的成员会自动获得此角色组的权限。|审核日志 <br/><br/> 合规性管理 <br/><br/> 信息权限管理 <br/><br/> 保留管理 <br/><br/> 仅查看审核日志 <br/><br/> 仅查看配置 <br/><br/> 仅查看收件人|
|ContentExplorerContentViewer|未使用。|数据分类内容查看器|
|ContentExplorerListViewer|未使用。|数据分类列表查看器|
|HelpDesk|查看和管理邮件用户。|重置密码 <br/><br/> 用户选项 <br/><br/> 仅查看收件人|
|HygieneManagement|管理保护功能 (反垃圾邮件、反恶意软件等) 。|传输安全机制 <br/><br/> 仅查看配置 <br/><br/> 仅查看收件人|
|MailFlowAdministrator|查看和管理接受域与连接器|远程域和接受域 <br/><br/> 仅查看收件人|
|OrganizationManagement|对整个组织的管理员访问权限以及几乎能够执行任何任务。 <br/><br/> Azure AD [中全局](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-administrator--company-administrator) 管理员角色的成员会自动获取此角色组的权限。 <br/><br/> **重要**说明：由于 OrganizationManagement 角色组是一个强大的角色，因此只有执行组织级别管理任务的用户才能是此角色组的成员。|反恶意软件 <br/><br/> AntiSpam <br/><br/> 审核日志 <br/><br/> 合规性管理员 <br/><br/> 动态通讯组 <br/><br/> 信息权限管理 <br/><br/> 邮件收件人创建 <br/><br/> 邮件收件人 <br/><br/> 邮件跟踪 <br/><br/> 迁移 <br/><br/> 组织客户端访问 <br/><br/> 组织配置 <br/><br/> 组织传输设置 <br/><br/> 隔离 <br/><br/> 收件人策略 <br/><br/> 远程域和接受域 <br/><br/> 重置密码 <br/><br/> 保留管理 <br/><br/> 角色管理 <br/><br/> 安全管理员 <br/><br/> 安全组创建和成员身份 <br/><br/> 安全读取者 <br/><br/> 敏感度标签管理员 <br/><br/> 监督 <br/><br/> 传输安全机制 <br/><br/> 传输规则 <br/><br/> 用户选项 <br/><br/> 仅查看反恶意软件 <br/><br/> 仅查看反垃圾邮件 <br/><br/> 仅查看审核日志 <br/><br/> 仅查看配置 <br/><br/> 仅限查看隔离区 <br/><br/> 仅查看收件人 <br/><br/> 仅查看威胁智能|
|QuarantineAdministrator|管理所有收件人的隔离邮件。|隔离|
|RecipientManagement|创建、管理和删除组织中的所有收件人对象。|动态通讯组 <br/><br/> 邮件收件人创建 <br/><br/> 邮件收件人 <br/><br/> 邮件跟踪 <br/><br/> 迁移 <br/><br/> 收件人策略 <br/><br/> 重置密码|
|RecordsManagement|配置遵从性功能，例如保留策略标记、邮件分类，以及邮件流规则 (也称为传输规则) 。|邮件跟踪 <br/><br/> 保留管理 <br/><br/> 传输规则|
|SecurityAdministrator|配置组织中的所有保护方面 (反垃圾邮件、反恶意软件、反欺 ) 骗、隔离等。 <br/><br/> Azure AD [中安全](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) 管理员角色的成员会自动获取此角色组的权限。|反恶意软件 <br/><br/> AntiSpam <br/><br/> 审核日志 <br/><br/> 隔离 <br/><br/> 安全管理员 <br/><br/> 敏感度标签管理员 <br/><br/> 仅查看反恶意软件 <br/><br/> 仅查看反垃圾邮件 <br/><br/> 仅查看审核日志 <br/><br/> 仅限查看隔离区 <br/><br/> 仅查看威胁智能|
|SecurityReader|仅查看组织中保护的以下方面 (反垃圾邮件、反恶意软件、反欺骗、隔离等) 。 <br/><br/> Azure AD [中安全读](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-reader) 者角色的成员会自动获取此角色组的权限。|安全读取者 <br/><br/> 仅查看反恶意软件 <br/><br/> 仅查看反垃圾邮件 <br/><br/> 仅限查看隔离区 <br/><br/> 仅查看威胁智能|
|TenantAdmins|此角色组的成员资格跨服务同步并且集中进行管理。 默认情况下，不向此角色组分配任何角色。 但是，它将是组织管理角色组的成员，并将继承这些权限。|无|
|ViewOnlyOrganizationManagement|查看组织中的收件人、保护和配置对象及其属性。|合规性管理员 <br/><br/> 安全管理员 <br/><br/> 安全读取者 <br/><br/> 敏感度标签管理员 <br/><br/> 仅查看配置 <br/><br/> 仅查看收件人|
|

如果您在只有少数几个管理员的小型组织工作，可能只需要将这些用户添加到 组织管理 角色组，并且可能永远不需要使用其他角色组。 如果您在较大型的组织工作，可能会由执行特定任务（如收件人配置）的管理员。 在这些情况下，可能要将一个管理员添加到 收件人管理 角色组，并将另一个管理员添加到 组织管理 角色组。 然后这些管理员可以管理特定的区域，但他们没有权限管理他们不负责的区域。

如果 Exchange Online 中的内置角色组与管理员的工作职能不匹配，可以创建角色组并向其中添加角色。 有关详细信息，请参阅["在独立 EOP 中管理角色组"。](manage-admin-role-group-permissions-in-eop.md)

## <a name="roles"></a>角色

下表介绍了独立 EOP 中可用的内置角色。

****

|Role**|说明|默认角色组分配|
|---|---|---|
|反恶意软件|查看和修改反恶意软件功能的配置和报告。|OrganizationManagement <br/><br/> SecurityAdministrator|
|AntiSpam|查看和修改反垃圾邮件功能的配置和报告。|OrganizationManagement <br/><br/> SecurityAdministrator|
|审核日志|搜索管理员审核日志查看结果。|ComplianceManagement <br/><br/> OrganizationManagement <br/><br/> SecurityAdministrator|
|合规性管理员<sup>\*</sup>||ComplianceManagement <br/><br/> OrganizationManagement <br/><br/> ViewOnlyOrganizationManagement|
|数据分类内容查看器<sup>\*</sup>||ContentExplorerContentViewer|
|数据分类列表查看器<sup>\*</sup>||
|动态通讯组|创建和管理所有通讯组、启用邮件的安全组和成员。|OrganizationManagement <br/><br/> RecipientManagement|
|信息权限管理<sup>\*</sup>||ComplianceManagement <br/><br/> OrganizationManagement|
|邮件收件人创建|创建和删除邮件用户。|OrganizationManagement <br/><br/> RecipientManagement|
|邮件收件人|修改现有的邮件用户。|OrganizationManagement <br/><br/> RecipientManagement|
|邮件跟踪<sup>\*</sup>||OrganizationManagement <br/><br/> RecipientManagement <br/><br/> 记录管理|
|迁移<sup>\*</sup>||OrganizationManagement <br/><br/> RecipientManagement|
|MyBaseOptions|允许用户查看其自己的隔离邮件。 <br/><br/> 此角色会自动分配给用户，且无法手动分配。|无|
|组织客户端访问<sup>\*</sup>||OrganizationManagement|
|组织配置|查看报告。|OrganizationManagement|
|组织传输设置<sup>\*</sup>||OrganizationManagement|
|隔离|管理所有收件人的所有类型的隔离邮件。|OrganizationManagement <br/><br/> QuarantineAdministrator <br/><br/> SecurityAdministrator|
|收件人策略<sup>\*</sup>||OrganizationManagement <br/><br/> RecipientManagement|
|远程域和接受域|管理远程域、接受域和连接器。|MailFlowAdministrator <br/><br/> OrganizationManagement|
|重置密码<sup>\*</sup>||HelpDesk <br/><br/> OrganizationManagement <br/><br/> RecipientManagement|
|保留管理<sup>\*</sup>||ComplianceManagement <br/><br/> OrganizationManagement <br/><br/> RecordsManagement|
|角色管理|创建和管理角色组。|OrganizationManagement|
|安全管理员|管理所有安全和保护功能的配置和报告。|OrganizationManagement <br/><br/> SecurityAdministrator <br/><br/> ViewOnlyOrganizationManagement|
|安全组创建和成员身份|创建和管理启用邮件的安全组。|OrganizationManagement|
|安全读取者|查看安全和保护功能的配置和报告。|组织管理 <br/><br/> SecurityReader <br/><br/> ViewOnlyOrganizationManagement|
|敏感度标签管理员<sup>\*</sup>||OrganizationManagement <br/><br/> SecurityAdministrator <br/><br/> ViewOnlyOrganizationManagement|
|监督<sup>\*</sup>||OrganizationManagement|
|传输安全机制|管理反恶意软件、反垃圾邮件功能和反欺骗功能。|HygieneManagement <br/><br/> OrganizationManagement|
|传输规则|创建和管理邮件流规则 (也称为传输规则) 。|OrganizationManagement <br/><br/> RecordsManagement|
|用户选项|修改现有的邮件用户。|HelpDesk <br/><br/> OrganizationManagement|
|仅查看反恶意软件|查看反恶意软件功能的配置和报告。|OrganizationManagement <br/><br/> SecurityAdministrator <br/><br/> SecurityReader|
|仅查看反垃圾邮件|查看反垃圾邮件功能的配置和报告。|OrganizationManagement <br/><br/> SecurityAdministrator <br/><br/> SecurityReader|
|仅查看审核日志|搜索管理员审核日志查看结果。|ComplianceManagement <br/><br/> OrganizationManagement <br/><br/> SecurityAdministrator|
|仅查看配置|查看组织和邮件流过程 (组织中非收件人) 设置。|ComplianceManagement <br/><br/> HygieneManagement <br/><br/> OrganizationManagement <br/><br/> ViewOnlyOrganizationManagement|
|仅限查看隔离区|查看所有收件人的所有隔离邮件。|OrganizationManagement <br/><br/> SecurityAdministrator <br/><br/> SecurityReader|
|仅查看收件人|查看收件人属性并运行邮件跟踪。|ComplianceManagement <br/><br/> HelpDesk <br/><br/> HygieneManagement <br/><br/> MailFlowAdministrator <br/><br/>  OrganizationManagement <br/><br/> ViewOnlyOrganizationManagement|
|仅查看威胁智能<sup>\*</sup>||OrganizationManagement <br/><br/> SecurityAdministrator <br/><br/> SecurityReader|
|

<sup>\*</sup> 尽管此角色可用，但它基本上对独立 EOP 没有任何帮助。

## <a name="microsoft-365-permissions-in-standalone-eop"></a>独立 EOP 中的 Microsoft 365 权限

在 Microsoft 365 管理中心创建了一个用户后，可选择是否为用户分配各种管理角色，例如全局管理员、服务管理员、密码管理员等。 Microsoft 365 角色授予 EOP 中用户管理员一些（不是所有）权限。

> [!NOTE]
> 用于创建独立 EOP 组织的帐户会自动分配给全局管理员角色。

下表列出了它们对应的 Microsoft 365 角色和独立 EOP 角色组。 有关这些角色的详细信息，请参阅关于 [管理员角色](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)。

****

|Microsoft 365 角色|EOP 角色组|
|---|---|
|Exchange 管理员|OrganizationManagement|
|全局管理员|OrganizationManagement <br/><br/> **注意**：全局管理员角色和 OrganizationManagement 角色组使用特殊的公司管理角色组联系在一起。 公司管理员角色组是在内部管理的，不能直接修改。|
|密码管理员|HelpDesk|
|全局读取者|ViewOnlyOrganizationManagement|
|安全管理员|SecurityAdministrator|
|安全读者|SecurityReader|
|

其他 Microsoft 365 角色没有相应的 EOP 角色组，也不会在 EOP 中授予管理权限。 有关为用户分配 Microsoft 365 角色的详细信息，请参阅"分配[管理员角色"。](https://docs.microsoft.com/microsoft-365/admin/add-users/assign-admin-roles)

用户无需添加到 Microsoft 365 角色中，即可在 EOP 中被授予权限。 通过添加用户作为 EOP 角色组的成员可做到这一点。 用户将在 EOP 中获得权限，但他们无法在其他 Microsoft 365 工作负载中获得权限。

### <a name="how-do-you-know-this-worked"></a>如何判断是否生效？

若要验证是否已成功复制了角色组，请执行以下步骤之一：

- 在 EAC 中，转到" **权限** \> **管理员角色**"，然后验证角色组是否未 (或未列出) 。 选择角色组，然后验证"详细信息"窗格中的设置，或单击"**Edit**编辑 ![ "图标 ](../../media/ITPro-EAC-EditIcon.png) 验证设置。

- 在 Exchange Online PowerShell 中 \<Role Group Name\> ，将角色组名称替换为角色组名称，并运行以下命令，验证角色组是否存在 (或不存在) 并验证设置：

    ```PowerShell
    Get-RoleGroup -Identity "<Role Group Name>" | Format-List
    ```
