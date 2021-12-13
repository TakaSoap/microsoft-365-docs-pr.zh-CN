---
title: 在"管理"中设置Microsoft 365
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
- m365solution-audit
- m365initiative-compliance
- m365solution-scenario
ms.custom: admindeeplinkEXCHANGE
search.appverid:
- MOE150
- MET150
description: 本文介绍如何设置基本审核，以便您可以开始搜索组织中用户和管理员执行的审核活动。
ms.openlocfilehash: e4ae5901c9a4f400e2a01659395d27947ad433c2
ms.sourcegitcommit: b1066b2a798568afdea9c09401d52fa38fe93546
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/13/2021
ms.locfileid: "61423607"
---
# <a name="set-up-basic-audit-in-microsoft-365"></a>在"管理"中设置Microsoft 365

通过"Microsoft 365基本审核"，可以搜索用户和管理员在不同 Microsoft 365 服务中执行的活动的审核记录。 由于默认情况下为大多数 Microsoft 365 和 Office 365 组织启用了基本审核，因此只有一些操作需要执行，您和您的组织中的其他人才能搜索审核日志。

本文讨论设置基本审核所需的以下步骤。

![设置基本审核的步骤。](../media/BasicAuditingWorkflow.png)

这些步骤包括确保生成和保留审核记录所需的正确组织订阅和用户许可，以及向安全操作、IT、合规性和法律团队的团队成员分配权限，以便搜索审核日志。

有关详细信息，请参阅 Basic [Audit in Microsoft 365](auditing-solutions-overview.md#basic-audit)。

## <a name="step-1-verify-organization-subscription-and-user-licensing"></a>步骤 1：验证组织订阅和用户许可

基本审核许可需要适当的组织订阅，该订阅提供对 审核日志 搜索工具和每用户许可的访问权限，这是记录并保留审核记录所需的。

当用户或管理员执行审核活动时，将生成审核记录并将其存储在组织的审核日志中。 在基本审核中，审核记录在审核记录中保留审核日志搜索 90 天。

有关基本审核的订阅和许可要求的列表，请参阅审核[Microsoft 365。](auditing-solutions-overview.md#licensing-requirements)

## <a name="step-2-assign-permissions-to-search-the-audit-log"></a>步骤 2：分配搜索搜索审核日志

必须为管理员和调查团队的成员分配View-Only审核日志或审核日志"角色Exchange Online搜索审核日志。 默认情况下，在 <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange 管理中心</a>中的“**权限**”页面上将这些角色分配给“合规性管理”和“组织管理”角色组。 Office 365 和 Microsoft 365 中的全局管理员将自动添加为 Exchange Online 的组织管理角色组成员。 若要让用户能够使用最低权限级别搜索审核日志，可以在 Exchange Online 中创建自定义角色组，添加“仅供查看审核日志”或“审核日志”角色，然后将用户添加为新角色组的成员。 有关详细信息，请参阅[在 Exchange Online 中管理角色组](/Exchange/permissions-exo/role-groups)。

以下屏幕截图显示了分配给管理中心中"组织管理"角色组的两个Exchange角色。

![审核分配给角色组中角色Exchange Online。](../media/EACAuditRoles.png)

## <a name="step-3-search-the-audit-log"></a>步骤 3：搜索审核日志

现在，你已准备好在搜索审核日志搜索Microsoft 365 合规中心。

1. 转到 <https://compliance.microsoft.com> ，然后使用已分配有相应审核权限的帐户登录。

2. 在页面的左侧导航窗格中 **Microsoft 365 合规中心"全部显示**"，然后单击"审核 **"。**

3. 在" **审核** "页上，使用"搜索"选项卡上的以下条件 **配置搜索** 。 

   ![用于搜索审核日志设置。](../media/AuditLogSearchToolMCCCallouts.png)

   1. **日期和时间范围**。 选择日期和时间范围，以显示在这段时间内发生的事件。 日期和时间以本地时间显示。 默认情况下选择最近七天。
  
   2. **活动**。 选择要搜索的活动。 使用搜索框搜索要添加到列表中的活动。 有关审核的活动的部分列表，请参阅 [审核的活动](search-the-audit-log-in-security-and-compliance.md#audited-activities)。 保留此框为空可返回所有审核的活动的条目。
  
   3. **用户**。  单击此框并开始键入要显示其搜索结果的用户的名称。 在此审核日志中选择的用户执行的选定活动的条目将显示在结果列表中。 将此框留空以返回组织中所有用户（和服务帐户）的条目。
  
   4. **文件、文件夹或网站**。 键入部分或所有文件或文件夹名称，以搜索与包含指定关键字的文件夹文件相关的活动。 你还可以指定文件或文件夹的 URL。 如果使用文件或文件夹的 URL，请确保键入完整 URL 路径，或者键入 URL 的一部分时，请勿包含任何特殊字符或空格。 将此框留空以返回组织中所有文件和文件夹的条目。

4. 单击 **"** 搜索"运行搜索。

将显示一个新页面，审核日志搜索正在运行的时间。 搜索完成后，审核记录将显示在页面上。 单击记录以显示具有详细属性的飞出页。

有关更详细的说明，请参阅在审核日志 [搜索策略](search-the-audit-log-in-security-and-compliance.md)。
