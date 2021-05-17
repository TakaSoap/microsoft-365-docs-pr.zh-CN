---
title: 信息屏障疑难解答
description: 使用本文作为解决信息障碍的指南。
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
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: de415ba7b68df786ead038bb72465c445a86ba5a
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50928002"
---
# <a name="troubleshooting-information-barriers"></a>信息屏障疑难解答

[信息屏障](information-barriers.md) 可帮助组织保持遵守法律要求和行业法规。 例如，由于存在信息障碍，您可以限制特定用户组之间的通信，以避免发生冲突或其他问题。  (若要详细了解如何设置信息屏障，请参阅定义信息 [屏障的策略](information-barriers-policies.md)。) 

如果信息屏障就位后用户遇到意外问题，可以采取一些步骤来解决这些问题。 使用本文作为指南。

> [!IMPORTANT]
> 若要执行本文中所述的任务，您必须分配有适当的角色，例如以下角色之一：<br/>- Microsoft 365 企业版全局管理员<br/>- 全局管理员<br/>- 合规性管理员<br/>- IBM 合规性管理 (这是一个新角色！) <p>若要了解有关信息屏障的先决条件详细信息，请参阅S [prerequisites (for information barrier policies) ](information-barriers-policies.md#prerequisites)。<p>确保连接到[安全与&中心 PowerShell。](/powershell/exchange/connect-to-scc-powershell)

## <a name="issue-users-are-unexpectedly-blocked-from-communicating-with-others-in-microsoft-teams"></a>问题：意外阻止用户与用户中的其他人Microsoft Teams 

在这种情况下，人们报告与企业中的其他人通信时出现意外Microsoft Teams。 示例如下：

- 用户在搜索中搜索另一个用户，但Microsoft Teams。
- 用户可以在搜索中查找另一个用户，但不能Microsoft Teams。
- 用户可以看到另一个用户，但不能在邮件中向该其他用户Microsoft Teams。

### <a name="what-to-do"></a>需执行的操作

确定用户是否受信息屏障策略的影响。 根据策略的配置方式，信息屏障可能会按预期方式工作。 或者，您可能必须优化组织的策略。

1. 将 **Get-InformationBarrierRecipientStatus** cmdlet 与 Identity 参数一同使用。 

    |**语法**|**示例**|
    |:---------|:----------|
    | `Get-InformationBarrierRecipientStatus -Identity` <p> 可以使用唯一标识每个收件人的任何标识值，如名称、别名、可分辨名称 (DN) 、规范 DN、电子邮件地址或 GUID。 |`Get-InformationBarrierRecipientStatus -Identity meganb` <p> 本示例中，我们将别名 (*meganb*) Identity 参数。 此 cmdlet 将返回指示用户是否受信息屏障策略影响的信息。  (查找 *ExoPolicyId：.) \<GUID> |

    **如果用户未包含在信息屏障策略中，请联系支持人员**。 否则，继续执行下一步。

2. 了解信息屏障策略中包括哪些分段。 为此，请使用 `Get-InformationBarrierPolicy` 带 Identity 参数的 cmdlet。 

    |**语法**|**示例**|
    |:---------|:----------|
    | `Get-InformationBarrierPolicy` <p> 使用在上一步骤 (收到) ExoPolicyId 策略 GUID 等详细信息作为标识值。 | `Get-InformationBarrierPolicy -Identity b42c3d0f-49e9-4506-a0a5-bf2853b5df6f` <p> 此示例中，我们将获取有关 ExoPolicyId *为 b42c3d0f-49e9-4506-a0a5-bf2853b5df6f* 的信息屏障策略的详细信息。 |

    运行 cmdlet 后，在结果中查找 **AssignedSegment、SegmentsAllowed** 和 **SegmentsBlocked** 值。 

    例如，运行 `Get-InformationBarrierPolicy` cmdlet 后，我们在结果列表中看到以下内容：

    ```powershell
    AssignedSegment : Sales
    SegmentsAllowed : {}
    SegmentsBlocked : {Research}
    ```

    在这种情况下，我们看到信息屏障策略会影响销售和研究部门中的人员。 在这种情况下，销售人员无法与 Research 中的人员通信。

    如果这看起来正确，则信息屏障将正常工作。 如果没有，继续执行下一步。

3. 确保正确定义了你的线段。 为此，请使用 `Get-OrganizationSegment` cmdlet 并查看结果列表。

    |**语法**|**示例**|
    |:---------|:----------|
    | `Get-OrganizationSegment`<p> 此 cmdlet 与 Identity 参数一同使用。 | `Get-OrganizationSegment -Identity c96e0837-c232-4a8a-841e-ef45787d8fcd` <p> 此示例中，我们将获取具有 GUID *c96e0837-c232-4a8a-841e-ef45787d8fcd* 的段的信息。 |

    查看该段的详细信息。 如有必要， [编辑段](information-barriers-edit-segments-policies.md#edit-a-segment)，然后重新使用该 `Start-InformationBarrierPoliciesApplication` cmdlet。

    **如果信息屏障策略仍有问题，请联系支持** 人员。

## <a name="issue-communications-are-allowed-between-users-who-should-be-blocked-in-microsoft-teams"></a>问题：允许在网站中阻止的用户之间Microsoft Teams

在这种情况下，虽然定义了、激活和应用了信息屏障，但应阻止相互通信的人以某种方式能够与对方聊天，并Microsoft Teams。

### <a name="what-to-do"></a>需执行的操作

验证问题用户是否包含在信息屏障策略中。 

1. 将 **Get-InformationBarrierRecipientStatus** cmdlet 与 Identity 参数一同使用。

    |**语法** _|_ *示例**|
    |:----------|:----------|
    | `Get-InformationBarrierRecipientStatus -Identity <value> -Identity2 <value>` <p> 可以使用任何能够唯一标识每个用户的值，例如名称、别名、可分辨名称、规范域名、电子邮件地址或 GUID。 |`Get-InformationBarrierRecipientStatus -Identity meganb -Identity2 alexw` <p> 本示例中，我们引用了 Office 365 中的两个用户帐户 *：meganb* 表示 *Megan，alexw* 表示 *Alex。*  |

    > [!TIP]
    > 还可以对单个用户使用此 cmdlet： `Get-InformationBarrierRecipientStatus -Identity <value>`

2. 查看结果。 **Get-InformationBarrierRecipientStatus** cmdlet 返回有关用户的信息，例如属性值和应用的任何信息屏障策略。

    查看结果，然后执行下一步，如下表所述：

    |**结果**|**下一步要做什么**|
    |:----------|:------------------|
    | 未针对所选用户列表列出任何 ()  | 执行下列操作之一：<br/>- 通过编辑用户的用户配置文件，将用户分配给现有Azure Active Directory。  (请参阅 Configure [user account properties with Office 365 PowerShell](../enterprise/configure-user-account-properties-with-microsoft-365-powershell.md).) <br/>- 使用信息屏障 [的受支持属性定义一个段](information-barriers-attributes.md)。 然后，[定义新策略或](information-barriers-policies.md#part-2-define-information-barrier-policies)[编辑现有策略](information-barriers-edit-segments-policies.md#edit-a-policy)以包含该区段。 |
    | 列出了分段，但没有向这些分段分配信息屏障策略 | 执行下列操作之一：<br/>- [为问题的每个段](information-barriers-policies.md#part-2-define-information-barrier-policies) 定义新的信息屏障策略 <br/>- [编辑现有信息屏障策略](information-barriers-edit-segments-policies.md#edit-a-policy) 以将其分配到正确的段 |
    | 列出了各个分段，并且每个分段都包含在信息屏障策略中 | - 运行 `Get-InformationBarrierPolicy` cmdlet 以验证信息屏障策略是否处于活动状态<br/>- 运行 `Get-InformationBarrierPoliciesApplicationStatus` cmdlet 以确认策略已应用<br/>- 运行 `Start-InformationBarrierPoliciesApplication` cmdlet 以应用所有活动信息屏障策略 |

## <a name="issue-i-need-to-remove-a-single-user-from-an-information-barrier-policy"></a>问题：我需要从信息屏障策略中删除单个用户

在这种情况下，信息屏障策略生效，一个或多个用户意外被阻止与网站中的其他用户Microsoft Teams。 你可以从信息屏障策略中删除一个或多个单个用户，而不是完全删除信息屏障策略。

### <a name="what-to-do"></a>需执行的操作

信息屏障策略分配给用户细分。 使用用户帐户配置文件 中的 [某些属性定义分段](information-barriers-attributes.md)。 如果必须从单个用户中删除策略，请考虑在 Azure Active Directory中编辑该用户的配置文件，使该用户不再包含在受信息屏障影响的段中。

1. 将 **Get-InformationBarrierRecipientStatus** cmdlet 与 Identity 参数一同使用。 此 cmdlet 返回有关用户的信息，例如属性值和应用的任何信息屏障策略。

    |**语法**|**示例**|
    |:---------|:----------|
    | `Get-InformationBarrierRecipientStatus -Identity <value> -Identity2 <value>` <p> 可以使用任何能够唯一标识每个用户的值，例如名称、别名、可分辨名称、规范域名、电子邮件地址或 GUID。 | `Get-InformationBarrierRecipientStatus -Identity meganb -Identity2 alexw` <p> 本示例中，我们引用了 Office 365 中的两个用户帐户 *：meganb* 表示 *Megan，alexw* 表示 *Alex。*           |
    | `Get-InformationBarrierRecipientStatus -Identity <value>` <p> 可以使用任何能够唯一标识该用户的值，如名称、别名、可分辨名称、规范域名、电子邮件地址或 GUID。|`Get-InformationBarrierRecipientStatus -Identity jeanp`<p> 此示例引用了 Office 365 中的单个 *帐户*。 |

2. 查看结果，查看是否分配了信息屏障策略，以及用户所属的 (所属的)  (类别) 类别。

3. 若要从受信息障碍影响的区段中删除用户，请更新用户[Azure Active Directory。](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)

4. 等待大约 30 分钟，FwdSync 发生。 或者，运行 `Start-InformationBarrierPoliciesApplication` cmdlet 以应用所有活动信息屏障策略。

## <a name="issue-the-information-barrier-application-process-is-taking-too-long"></a>问题：信息屏障应用程序过程所花时间过长

运行 **Start-InformationBarrierPoliciesApplication** cmdlet 后，此过程需要很长时间才能完成。

### <a name="what-to-do"></a>需执行的操作

请记住，在运行策略应用程序 cmdlet 时，将针对组织 (用户) 用户应用或删除信息屏障策略。 如果你有很多用户，需要一段时间处理。  (作为一般原则，大约需要一个小时处理 5，000 个用户帐户。) 

1. 使用 **Get-InformationBarrierPoliciesApplicationStatus** cmdlet 验证最新策略应用程序的状态。

    |**查看最新的策略应用程序**|**查看所有策略应用程序的状态**|
    |:---------------------------------------------|:---------------------------------------------|
    | `Get-InformationBarrierPoliciesApplicationStatus` | `Get-InformationBarrierPoliciesApplicationStatus -All $true` |

    这将显示有关策略应用程序已完成、失败还是正在进行的信息。

2. 根据上一步的结果，执行下列步骤之一：
  
    |**状态**|**后续步骤**|
    |:---------|:------------|
    | **未启动** | 如果自 **Start-InformationBarrierPoliciesApplication** cmdlet 运行以来已超过 45 分钟，请查看 审核日志 以查看策略定义中是否有错误，或应用程序未启动的其他原因。 |
    | **失败** | 如果应用程序失败，请查看审核日志。 此外，查看你的分段和策略。 是否向多个用户分配了多个段？ 是否向任何分段分配了多个策略？ 如有必要， [编辑分段](information-barriers-edit-segments-policies.md#edit-a-segment) 和/ [或编辑策略](information-barriers-edit-segments-policies.md#edit-a-policy)，然后再次运行 **Start-InformationBarrierPoliciesApplication** cmdlet。 |
    | **正在进行** | 如果应用程序仍在处理中，请留出更多时间来完成。 如果已经过几天，请收集审核日志，然后联系支持人员。 |

## <a name="issue-information-barrier-policies-are-not-being-applied-at-all"></a>问题：完全未应用信息屏障策略

在这种情况下，你已定义分段、定义的信息屏障策略，并且已尝试应用这些策略。 但是，当您运行该 `Get-InformationBarrierPoliciesApplicationStatus` cmdlet 时，可以看到策略应用程序已失败。

### <a name="what-to-do"></a>需执行的操作

确保您的组织没有Exchange[通讯簿](/exchange/address-books/address-book-policies/address-book-policies)策略。 此类策略将阻止应用信息屏障策略。

1. 连接到 [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。

2. 运行 [Get-AddressBookPolicy](/powershell/module/exchange/get-addressbookpolicy) cmdlet 并查看结果。

    |**结果**|**后续步骤**|
    |:----------|:------------|
    | Exchange通讯簿策略 | [删除通讯簿策略](/exchange/address-books/address-book-policies/remove-an-address-book-policy) |
    | 不存在通讯簿策略 |查看审核日志，了解策略应用程序失败的原因 |

3. [查看用户帐户、分段、策略或策略应用程序的状态](information-barriers-policies.md#view-status-of-user-accounts-segments-policies-or-policy-application)。

## <a name="issue-information-barrier-policy-not-applied-to-all-designated-users"></a>问题：未将信息屏障策略应用于所有指定用户

定义分段、定义的信息屏障策略并尝试应用这些策略后，您可能会发现该策略将应用于某些收件人，而不是应用于其他收件人。
运行 `Get-InformationBarrierPoliciesApplicationStatus` cmdlet 时，在输出中搜索如下所示的文本。

> 标识： `<application guid>`
>
> 收件人总数：81527
>
> 失败的收件人：2
>
> 故障类别：无
>
> 状态：完成

### <a name="what-to-do"></a>需执行的操作

1. 在 "审核日志 中搜索 `<application guid>` 。 您可以复制此 PowerShell 代码并针对变量进行修改。

```powershell
$DetailedLogs = Search-UnifiedAuditLog -EndDate <yyyy-mm-ddThh:mm:ss>  -StartDate <yyyy-mm-ddThh:mm:ss> -RecordType InformationBarrierPolicyApplication -ResultSize 1000 |?{$_.AuditData.Contains(<application guid>)} 
```

2. 检查字段的详细信息输出审核日志 和 `"UserId"` 字段 `"ErrorDetails"` 的值。 这将给出失败的原因。 您可以复制此 PowerShell 代码并针对变量进行修改。

```powershell
   $DetailedLogs[1] |fl
```

例如：

> "UserId"： User1
>
>"ErrorDetails"："Status： IBMPolicyConflict. 错误：IBM 段"segment id1"和"SEGMENT id2"存在冲突，无法分配给收件人。

3. 通常，你会发现用户已包含在多个段中。 可以通过更新 中的值 `-UserGroupFilter` 来解决此问题 `OrganizationSegments` 。

4. 使用这些过程重新应用信息屏障策略 [信息屏障策略](information-barriers-policies.md#part-3-apply-information-barrier-policies)。

## <a name="resources"></a>资源

- [定义信息屏障策略Microsoft Teams](information-barriers-policies.md)
- [信息屏障](information-barriers.md)