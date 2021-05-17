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
localization_priority: Normal
ms.assetid: 34674847-a6b7-4a7e-9eaa-b64f22bc150d
description: 了解独立部署中的任务所需的Exchange Online Protection
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 212a109c792522270b7e5000747bec950b7f4fe2
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/25/2021
ms.locfileid: "51203927"
---
# <a name="permissions-in-standalone-eop"></a>独立 EOP 中的权限

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用对象**
-  [Exchange Online Protection独立](exchange-online-protection-overview.md)

独立Exchange Online Protection (EOP) 邮箱Exchange Online基于角色的访问控制 (RBAC) 权限模型轻松地向管理员授予权限。 可以使用独立 EOP 中的权限功能快速启动并运行新组织。

若要向用户授予权限，请参阅在 EOP 中管理 [管理员角色组](manage-admin-role-group-permissions-in-eop.md)。

有关跨用户的权限Microsoft 365，请参阅关于[管理员角色](../../admin/add-users/about-admin-roles.md)。

## <a name="role-based-permissions"></a>基于角色的权限

授予用户的管理员权限基于管理角色。 管理角色定义可用于一组给定任务的 cmdlet。 由于 Exchange 管理中心 (EAC) 和独立 EOP PowerShell 都使用 cmdlet，因此授予对 cmdlet 的访问权限会授予用户在 EAC 或独立 EOP PowerShell 中执行相关任务的权限。 例如，Mail Recipients 角色定义修改邮件用户所需的 cmdlet。

在独立 EOP 中，管理角色是唯一可用的管理角色 (没有最终用户角色或角色分配策略) 。

## <a name="role-groups"></a>角色组

为了便于向用户分配角色，独立 EOP 使用角色组。 管理角色将分配给角色组，角色组的成员将获取与角色关联的权限。 换句话说，管理角色不会直接分配给用户;它们将被分配给角色组。 此模型允许您一次向多个角色组成员分配多个角色。 角色组的成员可以是邮件用户、启用邮件的安全组、Microsoft 365管理中心的用户和其他角色组。

下图显示了用户、角色组和角色之间的关系。

![角色、角色组和成员关系](../../media/ITPro_Security_RBAC_EXO_SimplifiedRoleGroupRelationship.png)

下表介绍了独立 EOP 中的可用角色组。

****

|角色组|说明|分配的默认角色|
|---|---|---|
|ComplianceManagement|在组织中配置和管理合规性设置，包括 DLP (DLP) DLP 功能时。 <p> Azure AD [中合规性管理员](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#compliance-administrator) 角色的成员会自动获得此角色组的权限。|审核日志 <p> 合规性管理 <p> 信息权限管理 <p> 保留管理 <p> 仅供查看审核日志 <p> 仅查看配置 <p> 仅查看收件人|
|ContentExplorerContentViewer|未使用。|数据分类内容查看器|
|ContentExplorerListViewer|未使用。|数据分类列表查看器|
|HelpDesk|查看和管理邮件用户。|重置密码 <p> 用户选项 <p> 仅查看收件人|
|HygieneManagement|管理反 (、反恶意软件等保护) 。|传输清洁 <p> 仅查看配置 <p> 仅查看收件人|
|MailFlowAdministrator|查看和管理接受域和连接器|远程域和接受域 <p> 仅查看收件人|
|OrganizationManagement|管理员访问整个组织以及执行几乎任何任务的能力。 <p> Azure AD [中的全局管理员](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-administrator--company-administrator) 角色的成员会自动获取此角色组的权限。 <p> **重要** 提示：由于 OrganizationManagement 角色组是一个强大的角色，因此只有执行组织级别管理任务的用户才能成为此角色组的成员。|AntiMalware <p> AntiSpam <p> 审核日志 <p> 合规性管理员 <p> 动态通讯组 <p> 信息权限管理 <p> 邮件收件人创建 <p> 邮件收件人 <p> 邮件跟踪 <p> 迁移 <p> 组织客户端访问 <p> 组织配置 <p> 组织传输设置 <p> 隔离 <p> 收件人策略 <p> 远程域和接受域 <p> 重置密码 <p> 保留管理 <p> 角色管理 <p> 安全管理员 <p> 安全组创建和成员身份 <p> 安全读取者 <p> 敏感度标签管理员 <p> 监督 <p> 传输清洁 <p> 传输规则 <p> 用户选项 <p> View-Only AntiMalware <p> View-Only AntiSpam <p> 仅供查看审核日志 <p> 仅查看配置 <p> View-Only隔离 <p> 仅查看收件人 <p> View-Only威胁智能|
|QuarantineAdministrator|管理所有收件人的隔离邮件。|隔离|
|RecipientManagement|在组织中创建、管理和删除收件人对象。|动态通讯组 <p> 邮件收件人创建 <p> 邮件收件人 <p> 邮件跟踪 <p> 迁移 <p> 收件人策略 <p> 重置密码|
|RecordsManagement|配置遵从性功能，如保留策略标记、邮件分类和邮件流规则 (也称为传输) 。|邮件跟踪 <p> 保留管理 <p> 传输规则|
|SecurityAdministrator|配置组织中保护的各个方面 (反垃圾邮件、反恶意软件、反欺骗、隔离等) 。 <p> Azure AD [中安全管理员](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) 角色的成员会自动获取此角色组的权限。|AntiMalware <p> AntiSpam <p> 审核日志 <p> 隔离 <p> 安全管理员 <p> 敏感度标签管理员 <p> View-Only AntiMalware <p> View-Only AntiSpam <p> 仅供查看审核日志 <p> View-Only隔离 <p> View-Only威胁智能|
|SecurityReader|对组织中保护的各个方面的仅查看 (反垃圾邮件、反恶意软件、反欺骗、隔离等) 。 <p> Azure AD [中安全读者](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-reader) 角色的成员会自动获取此角色组的权限。|安全读取者 <p> View-Only AntiMalware <p> View-Only AntiSpam <p> View-Only隔离 <p> View-Only威胁智能|
|TenantAdmins|此角色组的成员身份跨服务进行同步并集中管理。 默认情况下，不会为此角色组分配任何角色。 但是，它将是组织管理角色组的成员，并且将继承这些权限。|无|
|ViewOnlyOrganizationManagement|查看收件人、保护和配置对象及其在组织中的属性。|合规性管理员 <p> 安全管理员 <p> 安全读取者 <p> 敏感度标签管理员 <p> 仅查看配置 <p> 仅查看收件人|
|

如果你在只有几个管理员的小组织中工作，可能需要仅将这些用户添加到组织管理角色组，并且可能永远不需要使用其他角色组。 如果你在大型组织中工作，则你可能有执行特定任务（如收件人配置）的管理员。 在这种情况下，可以将一个管理员添加到收件人管理角色组，将另一个管理员添加到组织管理角色组。 然后，这些管理员可以管理其特定区域，但他们没有权限管理他们不负责的区域。

如果 Exchange Online 中的内置角色组与管理员的工作职能不匹配，可以创建角色组并向其中添加角色。 有关详细信息，请参阅管理 [独立 EOP 中的角色组](manage-admin-role-group-permissions-in-eop.md)。

## <a name="roles"></a>角色

下表介绍了独立 EOP 中可用的内置角色。

****

|Role**|说明|默认角色组分配|
|---|---|---|
|AntiMalware|查看和修改反恶意软件功能的配置和报告。|OrganizationManagement <p> SecurityAdministrator|
|AntiSpam|查看和修改反垃圾邮件功能的配置和报告。|OrganizationManagement <p> SecurityAdministrator|
|审核日志|搜索管理员审核日志并查看结果。|ComplianceManagement <p> OrganizationManagement <p> SecurityAdministrator|
|合规性管理员<sup>\*</sup>||ComplianceManagement <p> OrganizationManagement <p> ViewOnlyOrganizationManagement|
|数据分类内容查看器<sup>\*</sup>||ContentExplorerContentViewer|
|数据分类列表查看器<sup>\*</sup>||
|动态通讯组|创建和管理所有通讯组、启用邮件的安全组和成员。|OrganizationManagement <p> RecipientManagement|
|信息权限管理<sup>\*</sup>||ComplianceManagement <p> OrganizationManagement|
|邮件收件人创建|创建和删除邮件用户。|OrganizationManagement <p> RecipientManagement|
|邮件收件人|修改现有邮件用户。|OrganizationManagement <p> RecipientManagement|
|邮件跟踪<sup>\*</sup>||OrganizationManagement <p> RecipientManagement <p> 记录管理|
|迁移<sup>\*</sup>||OrganizationManagement <p> RecipientManagement|
|MyBaseOptions|允许用户查看其自己的隔离邮件。 <p> 此角色将自动分配给用户，并且不能手动分配。|无|
|组织客户端访问<sup>\*</sup>||OrganizationManagement|
|组织配置|查看报告。|OrganizationManagement|
|组织传输设置<sup>\*</sup>||OrganizationManagement|
|隔离|管理所有收件人的所有类型的隔离邮件。|OrganizationManagement <p> QuarantineAdministrator <p> SecurityAdministrator|
|收件人策略<sup>\*</sup>||OrganizationManagement <p> RecipientManagement|
|远程域和接受域|管理远程域、接受域和连接器。|MailFlowAdministrator <p> OrganizationManagement|
|重置密码<sup>\*</sup>||HelpDesk <p> OrganizationManagement <p> RecipientManagement|
|保留管理<sup>\*</sup>||ComplianceManagement <p> OrganizationManagement <p> RecordsManagement|
|角色管理|创建和管理角色组。|OrganizationManagement|
|安全管理员|管理所有安全和保护功能的配置和报告。|OrganizationManagement <p> SecurityAdministrator <p> ViewOnlyOrganizationManagement|
|安全组创建和成员身份|创建和管理启用邮件的安全组。|OrganizationManagement|
|安全读取者|查看安全和保护功能的配置和报告。|组织管理 <p> SecurityReader <p> ViewOnlyOrganizationManagement|
|敏感度标签管理员<sup>\*</sup>||OrganizationManagement <p> SecurityAdministrator <p> ViewOnlyOrganizationManagement|
|监督<sup>\*</sup>||OrganizationManagement|
|传输清洁|管理反恶意软件、反垃圾邮件功能和反欺骗功能。|HygieneManagement <p> OrganizationManagement|
|传输规则|创建和管理邮件流规则 (传输规则) 。|OrganizationManagement <p> RecordsManagement|
|用户选项|修改现有邮件用户。|HelpDesk <p> OrganizationManagement|
|View-Only AntiMalware|查看反恶意软件功能的配置和报告。|OrganizationManagement <p> SecurityAdministrator <p> SecurityReader|
|View-Only AntiSpam|查看反垃圾邮件功能的配置和报告。|OrganizationManagement <p> SecurityAdministrator <p> SecurityReader|
|仅供查看审核日志|搜索管理员审核日志并查看结果。|ComplianceManagement <p> OrganizationManagement <p> SecurityAdministrator|
|仅查看配置|查看组织的所有组织和非 (邮件) 设置。|ComplianceManagement <p> HygieneManagement <p> OrganizationManagement <p> ViewOnlyOrganizationManagement|
|View-Only隔离|查看所有收件人的所有隔离邮件。|OrganizationManagement <p> SecurityAdministrator <p> SecurityReader|
|仅查看收件人|查看收件人属性并运行邮件跟踪。|ComplianceManagement <p> HelpDesk <p> HygieneManagement <p> MailFlowAdministrator <p>  OrganizationManagement <p> ViewOnlyOrganizationManagement|
|View-Only威胁智能<sup>\*</sup>||OrganizationManagement <p> SecurityAdministrator <p> SecurityReader|
|

<sup>\*</sup> 尽管此角色可用，但它基本上在独立 EOP 中没有任何用处。

## <a name="microsoft-365-permissions-in-standalone-eop"></a>Microsoft 365 EOP 中的权限

在 Microsoft 365 管理中心创建用户时，可以选择是否向用户分配各种管理角色，例如全局管理员、服务管理员、密码管理员等。 某些（而不是全部）Microsoft 365角色在 EOP 中授予用户管理权限。

> [!NOTE]
> 用于创建独立 EOP 组织的帐户将自动分配给全局管理员角色。

下表列出了这些Microsoft 365角色及其对应的独立 EOP 角色组。 有关这些角色详细信息，请参阅关于 [管理员角色](../../admin/add-users/about-admin-roles.md)。

****

|Microsoft 365角色|EOP 角色组|
|---|---|
|Exchange 管理员|OrganizationManagement|
|全局管理员|OrganizationManagement <p> **注意**：全局管理员角色和 OrganizationManagement 角色组使用特殊的公司管理员角色组关联在一起。 公司管理员角色组在内部管理，不能直接修改。|
|密码管理员|HelpDesk|
|全局读取者|ViewOnlyOrganizationManagement|
|安全管理员|SecurityAdministrator|
|安全读者|SecurityReader|
|

其他Microsoft 365角色没有对应的 EOP 角色组，也不会在 EOP 中授予管理权限。 有关向用户分配Microsoft 365角色的信息，请参阅分配[管理员角色](../../admin/add-users/assign-admin-roles.md)。

可以在 EOP 中向用户授予管理权限，而无需将用户添加到Microsoft 365角色。 为此，将用户添加为 EOP 角色组的成员。 用户将在 EOP 中获取权限，但他们不会获得其他任务Microsoft 365权限。

### <a name="how-do-you-know-this-worked"></a>如何知道操作成功？

若要验证是否成功复制了角色组，请执行以下步骤之一：

- 在 EAC 中，转到"**权限**""管理员角色"，验证角色组是否 (\> 列出) 。 选择角色组，并验证"详细信息"窗格中的设置或单击 **"编辑编辑** ![ "图标 ](../../media/ITPro-EAC-EditIcon.png) 以验证设置。

- 在 Exchange Online PowerShell 中，将 替换为角色组的名称，并运行以下命令来验证角色组是否存在 (或不存在) 验证 \<Role Group Name\> 设置：

  ```PowerShell
  Get-RoleGroup -Identity "<Role Group Name>" | Format-List
  ```