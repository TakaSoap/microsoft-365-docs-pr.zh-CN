---
title: 管理信息屏障策略
description: 了解如何编辑或删除信息屏障策略。
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: None
f1.keywords:
- NOCSH
ms.openlocfilehash: dff13dd6c4011ec73a1976bce0af69b607e391b0
ms.sourcegitcommit: 7e7effd8ef4ffe75cdee7bb8517fec8608e4c230
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/18/2021
ms.locfileid: "59444051"
---
# <a name="manage-information-barrier-policies"></a>管理信息屏障策略

定义信息[屏障策略后](information-barriers-policies.md)，可能需要更改这些策略或用户区段，作为故障排除或定期维护的一部分。 [](/office365/troubleshoot/information-barriers/information-barriers-troubleshooting)

## <a name="what-do-you-want-to-do"></a>要执行什么操作？

|**操作**|**说明**|
|:---------|:--------------|
| [编辑用户帐户属性](#edit-user-account-attributes) | 在可用于定义Azure Active Directory填充属性。<br/>当用户未包含在自己本该在的区段时，请编辑用户帐户属性，以更改用户所在的区段，或使用不同的属性定义区段。 |
| [编辑区段](#edit-a-segment) | 希望更改区段定义方式时编辑区段。 <br/>例如，您可能最初使用 *Department* 定义了分段，但现在想要使用另一个属性，例如 *MemberOf*。 |
| [编辑策略](#edit-a-policy) | 想要更改策略的工作方式时，编辑信息屏障策略。<br/>例如，你可能决定只允许在某些分段之间发生通信，而不是阻止两个段之间的通信。 |
| [将策略设置为非活动状态](#set-a-policy-to-inactive-status) |在想要更改策略时，或者不希望策略生效时，将策略设置为非活动状态。 |
| [删除策略](#remove-a-policy) | 如果不再需要特定策略，请删除信息屏障策略。 |
| [停止策略应用程序](#stop-a-policy-application) | 若要停止应用信息屏障策略的过程，请执行该操作。<br/> 停止策略应用程序不是即时的，它不会撤消已应用于用户的策略。 |
| [定义信息屏障策略](information-barriers-policies.md) | 如果尚未制定此类策略，并且必须限制或限制特定用户组之间的通信，请定义信息屏障策略。 |
| [信息屏障疑难解答](/office365/troubleshoot/information-barriers/information-barriers-troubleshooting) | 当您遇到信息障碍的意外问题时，请参阅本文。 |

> [!IMPORTANT]
> 若要执行本文中所述的任务，您必须分配有适当的角色，例如以下角色之一：<br/>- Microsoft 365 企业版全局管理员<br/>- 全局管理员<br/>- 合规性管理员<br/>- IBM 合规性管理 (这是一个新角色！) <br><br>若要了解有关信息屏障的先决条件详细信息，请参阅S [prerequisites (for information barrier policies) ](information-barriers-policies.md#prerequisites)。<br><br> 确保连接到[安全与合规& PowerShell。](/powershell/exchange/connect-to-scc-powershell)

## <a name="edit-user-account-attributes"></a>编辑用户帐户属性

使用此过程可编辑用于划分用户的属性。 例如，如果您使用的是 Department 属性，并且一个或多个用户帐户当前没有为"部门"列出任何值，则必须编辑这些用户帐户以包含部门信息。 用户帐户属性用于定义分段，以便可以分配信息屏障策略。

1. 若要查看特定用户帐户的详细信息（如属性值和分配段 () ），请使用带 Identity 参数的 **Get-InformationBarrierRecipientStatus** cmdlet。

    |**语法**|**示例**|
    |:---------|:----------|
    | `Get-InformationBarrierRecipientStatus -Identity <value> -Identity2 <value>` <p> 可以使用任何能够唯一标识每个用户的值，如名称、别名、可分辨名称、规范域名、电子邮件地址或 GUID。 <p>  (也可以对单个用户使用此 cmdlet：) `Get-InformationBarrierRecipientStatus -Identity <value>` |`Get-InformationBarrierRecipientStatus -Identity meganb -Identity2 alexw` <p> 本示例中，我们引用了 Office 365 中的两个用户帐户 *：meganb* 表示 *Megan，alexw* 表示 *Alex。*  |

2. 确定要编辑用户帐户配置文件的属性 () 。 有关详细信息，请参阅 [信息屏障策略的属性](information-barriers-attributes.md)。 

3. 编辑一个或多个用户帐户，以包含在上一步中所选的属性的值。 若要执行此操作，请使用以下过程之一：

    - 若要编辑单个帐户，请参阅使用帐户添加或更新[Azure Active Directory。](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)

    - 若要编辑多个帐户 (或使用 PowerShell 编辑单个帐户) ，请参阅 Configure user account [properties with Office 365 PowerShell](../enterprise/configure-user-account-properties-with-microsoft-365-powershell.md)。

## <a name="edit-a-segment"></a>编辑区段

使用此过程可编辑用户区段的定义。 例如，您可以更改线段的名称，或者更改用于确定该线段中包括哪些人使用的筛选器。

1. 若要查看所有现有分段，请使用 **Get-OrganizationSegment** cmdlet。

    语法： `Get-OrganizationSegment`

    你将看到每个分段的列表和详细信息，如线段类型、其 UserGroupFilter 值、创建或上次修改者、GUID 等。

    > [!TIP]
    > 打印或保存分段列表，供以后参考。 例如，如果要编辑线段，需要知道其名称或标识值 (Identity 参数参数) 。

2. 若要编辑段，请使用带 **Identity** 参数和相关详细信息的 **Set-OrganizationSegment** cmdlet。

    |**语法**|**示例**|
    |:---------|:----------|
    | `Set-OrganizationSegment -Identity GUID -UserGroupFilter "attribute -eq 'attributevalue'"` |`Set-OrganizationSegment -Identity c96e0837-c232-4a8a-841e-ef45787d8fcd -UserGroupFilter "Department -eq 'HRDept'"` <p> 此示例中，对于 GUID *为 c96e0837-c232-4a8a-841e-ef45787d8fcd* 的段，我们将部门名称更新为"HRDept"。 |

为组织完成编辑分段后，可以[定义或](information-barriers-policies.md#part-2-define-information-barrier-policies)[编辑](#edit-a-policy)信息屏障策略。

## <a name="edit-a-policy"></a>编辑策略

1. 若要查看当前信息屏障策略的列表，请使用 **Get-InformationBarrierPolicy** cmdlet。

    语法： `Get-InformationBarrierPolicy`

    在结果列表中，确定要更改的策略。 请注意策略的 GUID 和名称。

2. 将 **Set-InformationBarrierPolicy** cmdlet 与 **Identity** 参数一同使用，并指定要所做的更改。

    示例：假设定义了一个策略来阻止 *Research* 部门与 *销售和市场营销部门**通信。* 策略是使用此 cmdlet 定义的： `New-InformationBarrierPolicy -Name "Research-SalesMarketing" -AssignedSegment "Research" -SegmentsBlocked "Sales","Marketing"`

    假设我们想要更改它，以便 *"* 研究"部门中的人员只能与 *人力资源部门中的* 人员通信。 若要进行此更改，我们使用此 cmdlet： `Set-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c93772471 -SegmentsAllowed "HR"`

    本示例将"SegmentsBlocked"更改为"SegmentsAllowed"，并指定 *HR* 段。

3. 编辑完策略后，请确保应用更改。  (应用 [信息屏障策略](information-barriers-policies.md#part-3-apply-information-barrier-policies).) 

## <a name="set-a-policy-to-inactive-status"></a>将策略设置为非活动状态

1. 若要查看当前信息屏障策略的列表，请使用 **Get-InformationBarrierPolicy** cmdlet。

    语法： `Get-InformationBarrierPolicy`

    在结果列表中，确定要更改或删除 (策略) 。 请注意策略的 GUID 和名称。

2. 若要将策略的状态设置为非活动状态，请使用带 Identity 参数的 **Set-InformationBarrierPolicy** cmdlet，将 State 参数设置为 Inactive。

    |**语法**|**示例**|
    |:---------|:----------|
    | `Set-InformationBarrierPolicy -Identity GUID -State Inactive` | `Set-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c9377247 -State Inactive` <p> 本示例将 GUID *为 43c37853-ea10-4b90-a23d-ab8c9377247* 的信息屏障策略设置为非活动状态。 |

3. 若要应用更改，请使用 **Start-InformationBarrierPoliciesApplication** cmdlet。

    语法： `Start-InformationBarrierPoliciesApplication`

    将按用户对组织应用更改。 如果组织规模较大，可能需要 24 (或) 才能完成此过程。  (作为一般原则，大约需要一个小时处理 5，000 个用户帐户。) 

此时，一个或多个信息屏障策略设置为非活动状态。 在这里，你可以执行以下操作之一：

- 一直 (设置为非活动状态的策略对用户没有) 
- [编辑策略](#edit-a-policy) 
- [删除策略](#remove-a-policy)

## <a name="remove-a-policy"></a>删除策略

1. 若要查看当前信息屏障策略的列表，请使用 **Get-InformationBarrierPolicy** cmdlet。

    语法： `Get-InformationBarrierPolicy`

    在结果列表中，标识要删除的策略。 请注意策略的 GUID 和名称。 确保策略设置为非活动状态。

2. 将 **Remove-InformationBarrierPolicy** cmdlet 与 Identity 参数一同使用。

    |**语法**|**示例**|
    |:---------|:----------|
    | `Remove-InformationBarrierPolicy -Identity GUID` | `Remove-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c93772471` <p> 本示例将删除 GUID *为 43c37853-ea10-4b90-a23d-ab8c93772471 的策略*。 |

    当系统提示时，确认更改。

3. 对要删除的每个策略重复步骤 1-2。

4. 删除完策略后，应用更改。 若要执行该操作，请使用 **Start-InformationBarrierPoliciesApplication** cmdlet。

    语法： `Start-InformationBarrierPoliciesApplication`

    将按用户对组织应用更改。 如果组织规模较大，可能需要 24 (或) 才能完成此过程。

## <a name="stop-a-policy-application"></a>停止策略应用程序

开始应用信息屏障策略后，如果要阻止应用这些策略，请使用以下过程。 此过程需要大约 30-35 分钟才能开始。

1. 若要查看最新信息屏障策略应用程序的状态，请使用 **Get-InformationBarrierPoliciesApplicationStatus** cmdlet。

    语法： `Get-InformationBarrierPoliciesApplicationStatus`

    请注意应用程序的 GUID。

2. 将 **Stop-InformationBarrierPoliciesApplication** cmdlet 与 Identity 参数一同使用。

    |**语法**|**示例**|
    |:---------|:----------|
    | `Stop-InformationBarrierPoliciesApplication -Identity GUID` | `Stop-InformationBarrierPoliciesApplication -Identity 46237888-12ca-42e3-a541-3fcb7b5231d1` <p> 本示例中，我们将阻止应用信息屏障策略。 |

## <a name="resources"></a>资源

- [获取信息屏障概述](information-barriers.md)
- [定义信息屏障策略](information-barriers-policies.md)
- [详细了解信息障碍Microsoft Teams](/MicrosoftTeams/information-barriers-in-teams)
- [详细了解 SharePoint Online 中的信息障碍](/sharepoint/information-barriers)
- [详细了解信息障碍OneDrive](/onedrive/information-barriers)
- [信息屏障策略的属性](information-barriers-attributes.md)
- [信息屏障疑难解答](/office365/troubleshoot/information-barriers/information-barriers-troubleshooting)