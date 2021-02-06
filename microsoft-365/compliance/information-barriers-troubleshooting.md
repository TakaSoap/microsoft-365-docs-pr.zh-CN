---
title: 信息屏障疑难解答
description: 使用本文作为信息屏障疑难解答指南。
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
ms.openlocfilehash: 3810dd977ef0d25642ba86a2b62a036c9a4ace06
ms.sourcegitcommit: eac5d9f759f290d3c51cafaf335a1a1c43ded927
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2021
ms.locfileid: "50126559"
---
# <a name="troubleshooting-information-barriers"></a>信息屏障疑难解答

[信息屏障](information-barriers.md) 可帮助组织保持遵守法律要求和行业法规。 例如，在信息障碍下，可以限制特定用户组之间的通信，以避免发生冲突或其他问题。  (若要详细了解如何设置信息屏障，请参阅"定义信息屏障[策略") ](information-barriers-policies.md)

如果信息屏障存在后，用户遇到意外问题，您可以采取一些步骤来解决这些问题。 使用本文作为指南。

> [!IMPORTANT]
> 若要执行本文中所述的任务，必须分配有适当的角色，例如以下角色之一：<br/>- Microsoft 365 企业版全局管理员<br/>- 全局管理员<br/>- 合规性管理员<br/>- IBM 合规性管理 (这是一个新角色！) <p>若要了解有关信息屏障的先决条件详细信息，请参阅 ([策略的先决条件 ](information-barriers-policies.md#prerequisites)) 。<p>确保连接到[安全与合规& PowerShell。](/powershell/exchange/connect-to-scc-powershell)

## <a name="issue-users-are-unexpectedly-blocked-from-communicating-with-others-in-microsoft-teams"></a>问题：意外阻止用户与 Microsoft Teams 中的其他人通信 

在这种情况下，人们报告与 Microsoft Teams 中的其他人通信时出现意外问题。 示例如下：

- 用户在 Microsoft Teams 中搜索另一个用户，但无法找到。
- 用户可以在 Microsoft Teams 中查找但无法选择其他用户。
- 用户可以看到另一个用户，但无法在 Microsoft Teams 中向该其他用户发送邮件。

### <a name="what-to-do"></a>需执行的操作

确定用户是否受信息屏障策略的影响。 根据策略的配置方式，信息屏障可能会按预期工作。 或者，您可能必须优化组织的策略。

1. 将 **Get-InformationBarrierRecipientStatus** cmdlet 与 Identity 参数一同使用。 

    |**语法**|**示例**|
    |:---------|:----------|
    | `Get-InformationBarrierRecipientStatus -Identity` <p> 可以使用唯一标识每个收件人的任何标识值，例如名称、别名、可分辨名称 (DN) 、规范 DN、电子邮件地址或 GUID。 |`Get-InformationBarrierRecipientStatus -Identity meganb` <p> 本示例中，我们将别名 (*mbnb*) Identity 参数。 此 cmdlet 将返回指示用户是否受信息屏障策略影响的信息。  (查找 *ExoPolicyId： \<GUID> .)  |

    **如果用户未包含在信息屏障策略中，请联系支持人员**。 否则，继续执行下一步。

2. 了解信息屏障策略中包含的分段。 为此，请使用带 Identity 参数的 `Get-InformationBarrierPolicy` cmdlet。 

    |**语法**|**示例**|
    |:---------|:----------|
    | `Get-InformationBarrierPolicy` <p> 使用在上一步 (ExoPolicyId) 策略 GUID 作为标识值。 | `Get-InformationBarrierPolicy -Identity b42c3d0f-49e9-4506-a0a5-bf2853b5df6f` <p> 本示例中，我们将获取有关具有 ExoPolicyId *b42c3d0f-49e9-4506-a0a5-bf2853b5df6f* 的信息屏障策略的详细信息。 |

    运行 cmdlet 后，在结果中查找 **AssignedSegment、SegmentsAllowed** 和 **SegmentsBlocked** 值。 

    例如，运行 `Get-InformationBarrierPolicy` cmdlet 后，我们在结果列表中看到以下内容：

    ```powershell
    AssignedSegment : Sales
    SegmentsAllowed : {}
    SegmentsBlocked : {Research}
    ```

    在这种情况下，我们看到信息屏障策略会影响销售和研究部门中的人员。 在这种情况下，销售部门人员无法与 Research 中的人员通信。

    如果看起来正确，则信息屏障将正常工作。 如果没有，继续执行下一步。

3. 确保正确定义了线段。 为此，请使用 `Get-OrganizationSegment` cmdlet，并查看结果列表。

    |**语法**|**示例**|
    |:---------|:----------|
    | `Get-OrganizationSegment`<p> 使用此 cmdlet 和 Identity 参数。 | `Get-OrganizationSegment -Identity c96e0837-c232-4a8a-841e-ef45787d8fcd` <p> 此示例中，我们将获取具有 GUID *c96e0837-c232-4a8a-841e-ef45787d8fcd* 的段的信息。 |

    查看该段的详细信息。 如有必要， [编辑线段](information-barriers-edit-segments-policies.md#edit-a-segment)，然后重新 `Start-InformationBarrierPoliciesApplication` 使用该 cmdlet。

    **如果信息屏障策略仍有问题，请联系支持人员**。

## <a name="issue-communications-are-allowed-between-users-who-should-be-blocked-in-microsoft-teams"></a>问题：允许在 Microsoft Teams 中阻止的用户之间的通信

在这种情况下，虽然定义了、激活和应用了信息屏障，但应阻止彼此通信的人以某种方式能够在 Microsoft Teams 中相互聊天和通话。

### <a name="what-to-do"></a>需执行的操作

验证信息屏障策略中是否包含有关用户。 

1. 将 **Get-InformationBarrierRecipientStatus** cmdlet 与 Identity 参数一同使用。

    |**语法** _|_ *示例**|
    |:----------|:----------|
    | `Get-InformationBarrierRecipientStatus -Identity <value> -Identity2 <value>` <p> 可以使用任何能够唯一标识每个用户的值，例如名称、别名、可分辨名称、规范域名、电子邮件地址或 GUID。 |`Get-InformationBarrierRecipientStatus -Identity meganb -Identity2 alexw` <p> 本示例中，我们引用了 Office 365 中的两个用户帐户 *：Meganb* for *Megan* 和 *alexw* for *Alex。* |

    > [!TIP]
    > 您还可以对单个用户使用此 cmdlet： `Get-InformationBarrierRecipientStatus -Identity <value>`

2. 查看结果。 **Get-InformationBarrierRecipientStatus** cmdlet 返回有关用户的信息，例如属性值和应用的任何信息屏障策略。

    查看结果，然后执行下一步，如下表所述：

    |**结果**|**下一步要做什么**|
    |:----------|:------------------|
    | 未为所选用户列出任何 ()  | 执行下列操作之一：<br/>- 在 Azure Active Directory 中编辑用户的用户配置文件，将用户分配到现有段。  (Office [365 PowerShell](/microsoft-365/enterprise/configure-user-account-properties-with-microsoft-365-powershell).) <br/>- 使用信息屏障 [的受支持属性定义线段](information-barriers-attributes.md)。 然后，[定义新策略或](information-barriers-policies.md#part-2-define-information-barrier-policies)[编辑现有策略](information-barriers-edit-segments-policies.md#edit-a-policy)以包含该段。 |
    | 列出分段，但没有为这些分段分配信息屏障策略 | 执行下列操作之一：<br/>- [为所针对的每个分段](information-barriers-policies.md#part-2-define-information-barrier-policies) 定义新的信息屏障策略 <br/>- [编辑现有信息屏障策略](information-barriers-edit-segments-policies.md#edit-a-policy) 以将其分配到正确的段 |
    | 列出了分段，并且每个分段都包含在信息屏障策略中 | - 运行 `Get-InformationBarrierPolicy` cmdlet 以验证信息屏障策略是否处于活动状态<br/>- 运行 `Get-InformationBarrierPoliciesApplicationStatus` cmdlet 以确认已应用策略<br/>- 运行 `Start-InformationBarrierPoliciesApplication` cmdlet 以应用所有活动信息屏障策略 |

## <a name="issue-i-need-to-remove-a-single-user-from-an-information-barrier-policy"></a>问题：我需要从信息屏障策略中删除单个用户

在这种情况下，信息屏障策略生效，意外地阻止一个或多个用户与 Microsoft Teams 中的其他人通信。 你可以从信息屏障策略中删除一个或多个单个用户，而不是完全删除信息屏障策略。

### <a name="what-to-do"></a>需执行的操作

信息屏障策略分配给用户细分。 使用用户帐户配置文件中的 [某些属性定义分段](information-barriers-attributes.md)。 如果必须从单个用户中删除策略，请考虑在 Azure Active Directory 中编辑该用户的配置文件，使该用户不再包含在受信息屏障影响的段中。

1. 将 **Get-InformationBarrierRecipientStatus** cmdlet 与 Identity 参数一同使用。 此 cmdlet 返回有关用户的信息，例如属性值和应用的任何信息屏障策略。

    |**语法**|**示例**|
    |:---------|:----------|
    | `Get-InformationBarrierRecipientStatus -Identity <value> -Identity2 <value>` <p> 可以使用任何能够唯一标识每个用户的值，例如名称、别名、可分辨名称、规范域名、电子邮件地址或 GUID。 | `Get-InformationBarrierRecipientStatus -Identity meganb -Identity2 alexw` <p> 本示例中，我们引用了 Office 365 中的两个用户帐户 *：Meganb* for *Megan* 和 *alexw* for *Alex。*          |
    | `Get-InformationBarrierRecipientStatus -Identity <value>` <p> 可以使用任何能够唯一标识用户的值，例如名称、别名、可分辨名称、规范域名、电子邮件地址或 GUID。|`Get-InformationBarrierRecipientStatus -Identity jeanp`<p> 本示例中，我们引用了 Office 365 中的单个 *帐户：用户。* |

2. 查看结果以查看是否分配了信息屏障策略，以及用户 (所属的) 属于 (类别) 类别。

3. 若要从受信息屏障影响的区段中删除用户，请更新 [Azure Active Directory](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)中的用户配置文件信息。

4. 等待大约 30 分钟，FwdSync 发生。 或者，运行 `Start-InformationBarrierPoliciesApplication` cmdlet 以应用所有活动信息屏障策略。

## <a name="issue-the-information-barrier-application-process-is-taking-too-long"></a>问题：信息屏障应用程序过程过长

运行 **Start-InformationBarrierPoliciesApplication** cmdlet 后，此过程需要很长时间才能完成。

### <a name="what-to-do"></a>需执行的操作

请记住，在运行策略应用程序 cmdlet 时，会针对组织 (用户) 用户应用或删除信息屏障策略。 如果有很多用户，需要一段时间处理。  (一般来说，处理 5，000 个用户帐户大约需要一个小时) 

1. 使用 **Get-InformationBarrierPoliciesApplicationStatus** cmdlet 验证最新策略应用程序的状态。

    |**查看最新的策略应用程序**|**查看所有策略应用程序的状态**|
    |:---------------------------------------------|:---------------------------------------------|
    | `Get-InformationBarrierPoliciesApplicationStatus` | `Get-InformationBarrierPoliciesApplicationStatus -All $true` |

    这将显示有关策略应用程序已完成、失败还是正在进行的信息。

2. 根据上一步的结果，执行以下步骤之一：
  
    |"状态"|**后续步骤**|
    |:---------|:------------|
    | **未启动** | 如果自 **Start-InformationBarrierPoliciesApplication** cmdlet 运行以来已超过 45 分钟，请查看 审核日志 以查看策略定义中是否有错误，或应用程序未启动的其他原因。 |
    | **失败** | 如果应用程序失败，请查看审核日志。 此外，查看你的分段和策略。 是否向多个用户分配了多个用户段？ 是否向任何分段分配了多个策略？ 如有必要， [编辑分段](information-barriers-edit-segments-policies.md#edit-a-segment) 和/ [或编辑策略](information-barriers-edit-segments-policies.md#edit-a-policy)，然后再次运行 **Start-InformationBarrierPoliciesApplication** cmdlet。 |
    | **正在进行** | 如果应用程序仍在处理中，请留出更多时间来完成它。 如果已经过几天，请收集审核日志，然后联系支持人员。 |

## <a name="issue-information-barrier-policies-are-not-being-applied-at-all"></a>问题：完全未应用信息屏障策略

在这种情况下，已定义分段、定义信息屏障策略，并尝试应用这些策略。 但是，运行 `Get-InformationBarrierPoliciesApplicationStatus` cmdlet 时，可以看到策略应用程序已失败。

### <a name="what-to-do"></a>需执行的操作

确保您的组织没有 [Exchange 通讯簿](/exchange/address-books/address-book-policies/address-book-policies) 策略。 此类策略将阻止应用信息屏障策略。

1. 连接到 [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。

2. 运行 [Get-AddressBookPolicy](/powershell/module/exchange/get-addressbookpolicy) cmdlet 并查看结果。

    |**结果**|**后续步骤**|
    |:----------|:------------|
    | 列出 Exchange 通讯簿策略 | [删除通讯簿策略](/exchange/address-books/address-book-policies/remove-an-address-book-policy) |
    | 不存在通讯簿策略 |查看审核日志，了解策略应用程序失败的原因 |

3. [查看用户帐户、分段、策略或策略应用程序的状态](information-barriers-policies.md#view-status-of-user-accounts-segments-policies-or-policy-application)。

## <a name="issue-information-barrier-policy-not-applied-to-all-designated-users"></a>问题：信息屏障策略未应用于所有指定用户

定义分段、定义信息屏障策略并尝试应用这些策略后，您可能会发现该策略正在应用于某些收件人，但不适用于其他收件人。
运行 `Get-InformationBarrierPoliciesApplicationStatus` cmdlet 时，在输出中搜索如下所示的文本。

> 标识： `<application guid>`
>
> 收件人总数：81527
>
> 失败的收件人：2
>
> 失败类别：无
>
> 状态：完成

### <a name="what-to-do"></a>需执行的操作

1. 在搜索审核日志 `<application guid>` 搜索。 您可以复制此 PowerShell 代码并针对变量进行修改。

```powershell
$DetailedLogs = Search-UnifiedAuditLog -EndDate <yyyy-mm-ddThh:mm:ss>  -StartDate <yyyy-mm-ddThh:mm:ss> -RecordType InformationBarrierPolicyApplication -ResultSize 1000 |?{$_.AuditData.Contains(<application guid>)} 
```

2. 检查输出结果中审核日志和字段 `"UserId"` `"ErrorDetails"` 的值。 这将为您提供失败的原因。 您可以复制此 PowerShell 代码并针对变量进行修改。

```powershell
   $DetailedLogs[1] |fl
```

例如：

> "UserId"：User1
>
>"ErrorDetails"："Status： IBMPolicyConflict. 错误：IBM 段"segment id1"和 IBM segment"segment id2"存在冲突，无法分配给收件人。

3. 通常，你会发现用户已包含在多个段中。 可以通过更新中的值 `-UserGroupFilter` 来解决此问题 `OrganizationSegments` 。

4. 使用这些步骤重新应用信息屏障策略 [信息屏障策略](information-barriers-policies.md#part-3-apply-information-barrier-policies)。

## <a name="resources"></a>资源

- [在 Microsoft Teams 中定义信息屏障策略](information-barriers-policies.md)
- [信息屏障](information-barriers.md)
