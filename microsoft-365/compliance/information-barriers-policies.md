---
title: 信息屏障入门
description: 了解如何开始使用信息屏障。
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
ms.localizationpriority: ''
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: fb6de09c0c020631f42d8f2f09cb236affb94417
ms.sourcegitcommit: 1c5f9d17a8b095cd88b23f4874539adc3ae021de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2022
ms.locfileid: "64713528"
---
# <a name="get-started-with-information-barriers"></a>信息屏障入门

借助信息屏障，可以定义旨在防止某些用户段相互通信或允许特定段仅与某些其他段通信的策略。 信息屏障策略可以帮助组织保持符合相关行业标准和法规，并避免潜在的利益冲突。 有关详细信息，请参阅 [了解信息障碍](information-barriers.md)。

本文介绍如何配置信息屏障策略。 涉及多个步骤，因此请确保在开始配置信息屏障策略之前查看整个过程。

> [!TIP]
> 本文包含一个 [示例方案](#example-scenario-contosos-departments-segments-and-policies) ，可帮助你规划和定义信息屏障策略。

## <a name="concepts"></a>概念

为信息屏障定义策略时，你将使用用户帐户属性、段、"阻止"和/或"allow"策略以及策略应用程序。

- 用户帐户属性 在 Azure Active Directory（或 Exchange Online）中定义。 这些属性可能包括部门、职务、位置、团队名称和其他职务资料详细信息。
- 段是使用所选用户 **帐户属性** 在Microsoft 365 合规中心中定义的用户集。 （请参阅 [支持的属性列表](information-barriers-attributes.md)。）
- 信息屏障策略决定了通信限制或限制。 定义信息屏障策略时，可以从以下两种策略中选择：
  - *阻止* 策略阻止一个区段与另一个区段通信。
  - *允许* 策略允许一个区段仅与特定其他区段通信。
- 策略应用 之前应先定义所有信息屏障策略。全部定义之后，则已准备好在组织中应用这些策略。

## <a name="configuration-at-a-glance"></a>一目了然地配置

| **步骤** | **所涉及的内容** |
|:------|:----------------|
| **步骤 1**： [确保满足先决条件](#step-1-make-sure-prerequisites-are-met) | - 验证是否具有 [所需的许可证和权限](information-barriers.md#required-licenses-and-permissions)<br/>- 验证目录是否包含区段用户的数据<br/>- 为[Microsoft Teams启用按名称搜索](/microsoftteams/teams-scoped-directory-search)<br/>- 确保审核日志记录已打开<br/>- 确保没有 Exchange 通讯簿策略<br/>- 使用 PowerShell (示例提供) <br/>- 为Microsoft Teams (步骤提供管理员同意)  |
| **步骤 2**： [将组织中的用户分段](#step-2-segment-users-in-your-organization) | - 确定需要的策略<br/>- 列出要定义的区段<br/>- 确定要使用的属性<br/>- 确定区段的策略筛选器 |
| **步骤 3**： [定义信息屏障策略](#step-3-define-information-barrier-policies) | - 定义策略 (尚未应用) <br/>- 从两种类型中进行选择（阻止或允许） |
| **步骤 4**： [应用信息屏障策略](#step-4-apply-information-barrier-policies) | - 将策略设置为活动状态<br/>- 运行策略应用程序<br/>- 查看策略状态 |
| **步骤 5**：[针对SharePoint和OneDrive (可选) 的信息屏障进行配置](#step-5-configuration-for-information-barriers-on-sharepoint-and-onedrive) | - 为SharePoint和OneDrive配置信息屏障 |
| **步骤 6**： [信息屏障模式 (可选)](#step-6-information-barriers-modes) | - 更新信息屏障模式（如果适用） |

## <a name="step-1-make-sure-prerequisites-are-met"></a>步骤 1：确保满足先决条件

除了 [所需的许可证和权限](information-barriers.md#required-licenses-and-permissions)外，在配置信息屏障之前，请确保满足以下要求：

- **目录数据**：确保组织的结构反映在目录数据中。 若要执行此操作，请确保在Azure Active Directory (或Exchange Online) 中正确填充用户帐户属性，例如组成员身份、部门名称等。 若要了解详细信息，请参阅以下资源：
  - [信息屏障策略的属性](information-barriers-attributes.md)
  - [使用Azure Active Directory添加或更新用户的个人资料信息](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)
  - [使用 Office 365 PowerShell 配置用户帐户的属性](../enterprise/configure-user-account-properties-with-microsoft-365-powershell.md)

- **作用域目录搜索**：在定义组织的第一个信息屏障策略之前，必须在 [Microsoft Teams中启用作用域目录搜索](/MicrosoftTeams/teams-scoped-directory-search)。 在启用范围目录搜索后，请等待至少 24 小时，然后再设置或定义信息屏障策略。

- **Exchange Online许可证**：只有在为目标用户分配了Exchange Online许可证时，信息屏障策略才有效。

- **验证是否已启用审核日志记录**：若要查找策略应用程序的状态，必须启用审核日志记录。 默认情况下，为 Microsoft 365 组织启用审核。 一些组织可能出于特定原因禁用了审核。 如果组织禁用了审核，则可能是因为其他管理员已将其禁用。 我们建议确认在完成此步骤时可以重新启用审核。 有关详细信息，请参阅[启用或禁用审核日志搜索](turn-audit-log-search-on-or-off.md)。

- **无通讯簿策略**：在定义和应用信息屏障策略之前，请确保没有Exchange通讯簿策略。 信息屏障基于通讯簿策略，但两种类型的策略不兼容。 如果有此类策略，请务必先 [删除通讯簿策略](/exchange/address-books/address-book-policies/remove-an-address-book-policy) 。 启用信息屏障策略并启用分层通讯簿后，**_所有未包含_** 在信息屏障段中的用户都会在联机Exchange中看到 [分层通讯簿](/exchange/address-books/hierarchical-address-books/hierarchical-address-books)。

- **使用 PowerShell 进行管理**：目前，信息屏障策略是在安全&合规中心 PowerShell 中定义和管理的。 虽然本文提供了几个示例，但需要熟悉 PowerShell cmdlet 和参数。 还需要 Azure Active Directory PowerShell 模块。
  - [连接到安全与合规中心 PowerShell](/powershell/exchange/connect-to-scc-powershell)
  - [安装 Azure Active Directory PowerShell for Graph](/powershell/azure/active-directory/install-adv2)

- **管理员同意Microsoft Teams中的信息障碍**：IB 策略到位后，他们可以从组中删除非 IB 合规性用户 (，即基于组) 的Teams通道。 此配置有助于确保组织仍符合策略和法规。 使用以下过程可使信息屏障策略在Microsoft Teams中按预期工作。

   1. 先决条件：[安装 Azure Active Directory PowerShell for Graph](/powershell/azure/active-directory/install-adv2)。

   1. 运行以下 PowerShell cmdlet：

      ```powershell
      Connect-AzureAD -Tenant "<yourtenantdomain.com>"  //for example: Connect-AzureAD -Tenant "Contoso.onmicrosoft.com"
      $appId="bcf62038-e005-436d-b970-2a472f8c1982" 
      $sp=Get-AzureADServicePrincipal -Filter "appid eq '$($appid)'"
      if ($sp -eq $null) { New-AzureADServicePrincipal -AppId $appId }
      Start-Process  "https://login.microsoftonline.com/common/adminconsent?client_id=$appId"
      ```

   1. 系统提示时，使用工作或学校帐户登录Office 365。

   1. 在" **权限请求** "对话框中，查看信息，然后选择 **"接受**"。 应用请求的权限如下所示。

      > [!div class="mx-imgBorder"]
      > ![图像。](https://user-images.githubusercontent.com/8932063/107690955-b1772300-6c5f-11eb-9527-4235de860b27.png)

满足所有先决条件后，继续执行下一步。

> [!TIP]
> 为了帮助你准备计划，本文中包含一个示例方案。 [请参阅 Contoso 的部门、部门和策略](#example-scenario-contosos-departments-segments-and-policies)。

## <a name="step-2-segment-users-in-your-organization"></a>步骤 2：将组织中的用户分段

在此步骤中，确定需要哪些信息屏障策略，列出要定义的段，然后定义段。

### <a name="determine-what-policies-are-needed"></a>确定需要哪些策略

考虑到法律和行业法规，组织中谁需要信息屏障策略？ 创建列表。 是否有任何组应阻止与另一个组通信？ 是否应允许任何组仅与一个或两个其他组通信？ 将所需的策略视为属于两个组之一：

- "阻止"策略阻止一个组与另一个组通信。
- "允许"策略允许组仅与某些其他特定组通信。

当有组和策略的初始列表时，请继续确定所需的段。

### <a name="identify-segments"></a>标识段

除了初始策略列表外，还为组织创建细分列表。 将包含在信息屏障策略中的用户应属于一个段。 以用户身份仔细规划段，只能在一个段中。 每个段只能应用一个信息屏障策略。

> [!IMPORTANT]
> 用户只能在一个段中。

确定要用于定义段的组织目录数据中的哪些属性。 可以使用 *Department*、 *MemberOf* 或任何受支持的属性。 请确保为用户选择的属性中有值。 [有关信息屏障，请参阅支持的属性列表](information-barriers-attributes.md)。

> [!IMPORTANT]
> **在继续下一部分之前，请确保目录数据具有可用于定义段的属性的值**。 如果目录数据没有要使用的属性的值，则必须先更新用户帐户以包含该信息，然后再继续使用信息屏障。 若要获取相关帮助，请参阅以下资源：<br/>- [使用 Office 365 PowerShell 配置用户帐户属性](../enterprise/configure-user-account-properties-with-microsoft-365-powershell.md)<br/>- [使用Azure Active Directory添加或更新用户的个人资料信息](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)

### <a name="define-segments-using-powershell"></a>使用 PowerShell 定义段

定义段不会影响用户;它只是设置要定义然后应用的信息屏障策略的阶段。

1. 将 **New-OrganizationSegment** cmdlet 与与要使用的 [属性](information-barriers-attributes.md)相对应的 **UserGroupFilter** 参数配合使用。

    | 语法 | 示例 |
    |:---------|:----------|
    | `New-OrganizationSegment -Name "segmentname" -UserGroupFilter "attribute -eq 'attributevalue'"` |`New-OrganizationSegment -Name "HR" -UserGroupFilter "Department -eq 'HR'"` <p>在此示例中，使用 HR 定义名为 *HR* 的段，*这是**部门* 属性中的值。 cmdlet 的 **-eq** 部分引用"equals"。  (或者，可以使用 **-ne** 来表示"不等于"。 请参阅 [在段定义中使用"equals"和"not equals"。](#using-equals-and-not-equals-in-segment-definitions))  |

    运行每个 cmdlet 后，应会看到有关新段的详细信息列表。 详细信息包括段的类型、创建或上次修改该段的人员等。 

2. 对要定义的每个区段重复此过程。

    > [!IMPORTANT]
    > **确保段不重叠**。 每个受信息屏障影响的用户应属于一个 (，只有一个) 段。 任何用户都不应属于两个或多个段。  (请参阅示 [例：本文中 Contoso 定义的段](#contosos-defined-segments) 。) 

定义段后，继续 [定义信息屏障策略](#step-3-define-information-barrier-policies)。

### <a name="using-equals-and-not-equals-in-segment-definitions"></a>在段定义中使用"equals"和"not equals"

在下面的示例中，我们将定义一个段，以便"部门等于 HR"。 

| 示例 | 注意 |
|:----------|:-------|
|`New-OrganizationSegment -Name "HR" -UserGroupFilter "Department -eq 'HR'"` | 请注意，在此示例中，段定义包含表示为 **-eq** 的"equals"参数。 |

还可以使用表示为 **-ne** 的"不等于"参数定义段，如下表所示：

| 语法 | 示例 |
|:---------|:----------|
| `New-OrganizationSegment -Name "NotSales" -UserGroupFilter "Department -ne 'Sales'"` | 在此示例中，我们定义了一个名为 *NotSales* 的细分，其中包含所有不在 *Sales* 中的人员。 cmdlet 的 **-ne** 部分引用"不等于"。 |

除了使用"equals"或"not equals"定义段外，还可以使用"等于"和"不等于"参数定义段。 还可以使用逻辑 *AND* 和 *OR* 运算符定义复杂的组筛选器。

| 语法 | 示例 |
|:---------|:----------|
| `New-OrganizationSegment -Name "LocalFTE" -UserGroupFilter "Location -eq 'Local'" -and "Position -ne 'Temporary'"` | 在此示例中，我们定义了一个名为 *LocalFTE* 的段，其中包含位于本地且其位置未列为 *"临时*"的人员。 |
| `New-OrganizationSegment -Name "Segment1" -UserGroupFilter "MemberOf -eq 'group1@contoso.com'' -and MemberOf -ne 'group3@contoso.com'"`| 在此示例中，我们定义了一个名为 *Segment1* 的段，该段包括 group1@contoso.com 成员而不是 group3@contoso.com 成员的人员。 |
| `New-OrganizationSegment -Name "Segment2" -UserGroupFilter "MemberOf -eq 'group2@contoso.com' -or MemberOf -ne 'group3@contoso.com'"` | 在此示例中，我们定义了一个名为 *Segment2* 的段，该段包括 group2@contoso.com 成员而不是 group3@contoso.com 成员的人员。 |
| `New-OrganizationSegment -Name "Segment1and2" -UserGroupFilter "(MemberOf -eq 'group1@contoso.com' -or MemberOf -eq 'group2@contoso.com') -and MemberOf -ne 'group3@contoso.com'"`| 在此示例中，我们定义了一个名为 *Segment1and2* 的段，其中包含 group1@contoso.com 和 group2@contoso.com 的人员，而不是 group3@contoso.com 的成员。 |

> [!TIP]
> 如果可能，请使用包含"-eq"或"-ne"的段定义。 请尽量不要定义复杂的段定义。

## <a name="step-3-define-information-barrier-policies"></a>步骤 3：定义信息屏障策略

确定是需要阻止某些段之间的通信，还是将通信限制为特定段。 理想情况下，你将使用最少数量的策略来确保组织符合法律和行业要求。

使用用户段列表和要定义的信息屏障策略，选择方案，然后按照步骤操作。

- [方案 1：阻止段之间的通信](#scenario-1-block-communications-between-segments)
- [方案 2：允许一个区段仅与另一个区段通信](#scenario-2-allow-a-segment-to-communicate-only-with-one-other-segment)

> [!IMPORTANT]
> **请确保在定义策略时，不会将多个策略分配给某个段**。 例如，如果为名为 *Sales* 的细分市场定义一个策略，请不要为 *Sales* 定义其他策略。<p> 此外，在定义信息屏障策略时，请确保将这些策略设置为非活动状态，直到准备好应用它们。 定义 (或编辑) 策略不会影响用户，直到这些策略设置为活动状态，然后应用。

 (请参阅本文中的 [示例：Contoso 的信息屏障策略](#contosos-information-barrier-policies) 。) 

### <a name="scenario-1-block-communications-between-segments"></a>方案 1：阻止区段之间的通信

如果要阻止段彼此通信，请定义两个策略：一个用于每个方向。 每个策略仅阻止一个方向的通信。

例如，假设要阻止 A 段和 B 段之间的通信。在这种情况下，你定义了一个策略来阻止段 A 与段 B 通信，然后定义第二个策略以防止段 B 与段 A 通信。

1. 若要定义第一个阻止策略，请将 **New-InformationBarrierPolicy** cmdlet 与 **SegmentsBlocked 参数配合** 使用。

    | 语法 | 示例 |
    |:--------|:----------|
    | `New-InformationBarrierPolicy -Name "policyname" -AssignedSegment "segment1name" -SegmentsBlocked "segment2name"` | `New-InformationBarrierPolicy -Name "Sales-Research" -AssignedSegment "Sales" -SegmentsBlocked "Research" -State Inactive` <p> 在此示例中，我们 *为名为* Sales 的细分市场定义了名为 *Sales-Research* 的策略。 当处于活动状态并应用时，此策略会阻止 *Sales* 中的人员与名为" *Research*"的细分市场中的人员进行通信。 |

2. 若要定义第二个阻塞段，请再次将 **New-InformationBarrierPolicy** cmdlet 与 **SegmentsBlocked 参数配合** 使用，这次将段反转。

    | 示例 | 注意 |
    |:----------|:-------|
    |`New-InformationBarrierPolicy -Name "Research-Sales" -AssignedSegment "Research" -SegmentsBlocked "Sales" -State Inactive` | 在此示例中，我们定义了一个名为 *"Research-Sales"的* 策略，以防止 *研究* 与 *Sales* 通信。 |

3. 继续执行以下操作之一：

   -  (如果需要，) [定义一个策略，以允许段仅与其他段通信](#scenario-2-allow-a-segment-to-communicate-only-with-one-other-segment) 
   -  (在定义所有策略) [应用信息屏障策略](#step-4-apply-information-barrier-policies)后

### <a name="scenario-2-allow-a-segment-to-communicate-only-with-one-other-segment"></a>方案 2：允许一个区段仅与另一个区段通信

1. 若要允许一个段仅与另一个段通信，请将 **New-InformationBarrierPolicy** cmdlet 与 **SegmentsAllowed** 参数配合使用。

    | 语法 | 示例 |
    |:----------|:----------|
    | `New-InformationBarrierPolicy -Name "policyname" -AssignedSegment "segment1name" -SegmentsAllowed "segment2name","segment1name"` | `New-InformationBarrierPolicy -Name "Manufacturing-HR" -AssignedSegment "Manufacturing" -SegmentsAllowed "HR","Manufacturing" -State Inactive` <p> 在此示例中，我们为名为"*制造*"的细分市场定义了一个名为"*制造-HR*"的策略。 当活动和应用时，此策略允许 *制造* 中的人员仅与名为 *HR* 的细分市场中的人员通信。  (在这种情况下， *制造* 无法与不属于 *HR*.) 的用户通信 |

    **如果需要，可以使用此 cmdlet 指定多个段，如以下示例所示。**

    | 语法 | 示例 |
    |:---------|:----------|
    | `New-InformationBarrierPolicy -Name "policyname" -AssignedSegment "segment1name" -SegmentsAllowed "segment2name", "segment3name","segment1name"` | `New-InformationBarrierPolicy -Name "Research-HRManufacturing" -AssignedSegment "Research" -SegmentsAllowed "HR","Manufacturing","Research" -State Inactive` <p> 在此示例中，我们定义了一个策略，该策略允许 *Research* 细分市场仅与 *HR* 和 *制造* 进行通信。 |

    针对要定义的每个策略重复此步骤，以允许特定段仅与某些其他特定段通信。

2. 继续执行以下操作之一：

   -  (如果需要，) [定义一个策略来阻止段之间的通信](#scenario-1-block-communications-between-segments) 
   -  (在定义所有策略) [应用信息屏障策略](#step-4-apply-information-barrier-policies)后

## <a name="step-4-apply-information-barrier-policies"></a>步骤 4：应用信息屏障策略

在将信息屏障策略设置为活动状态，然后应用策略之前，这些策略才有效。

1. 使用 **Get-InformationBarrierPolicy** cmdlet 查看已定义的策略列表。 记下每个策略的 GUID)  (状态和标识。

    语法： `Get-InformationBarrierPolicy`

2. 若要将策略设置为活动状态，请将 **Set-InformationBarrierPolicy** cmdlet 与 **Identity** 参数一起使用，并将 **State** 参数设置为 **"活动**"。 

    | 语法 | 示例 |
    |:---------|:----------|
    | `Set-InformationBarrierPolicy -Identity GUID -State Active` | `Set-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c93772471 -State Active` <p> 在此示例中，我们将 GUID *43c37853-ea10-4b90-a23d-ab8c93772471* 设置为活动状态的信息屏障策略。 |

    针对每个策略重复此步骤。

3. 完成将信息屏障策略设置为活动状态后，请在安全&合规中心中使用 **Start-InformationBarrierPoliciesApplication** cmdlet。

    语法： `Start-InformationBarrierPoliciesApplication`

    运行 `Start-InformationBarrierPoliciesApplication` 后，需要等待 30 分钟，系统才能开始应用策略。 系统按用户应用策略。 系统每小时处理大约 5，000 个用户帐户。

### <a name="view-status-of-user-accounts-segments-policies-or-policy-application"></a>查看用户帐户、段、策略或策略应用程序的状态

使用 PowerShell，可以查看用户帐户、段、策略和策略应用程序的状态，如下表所列。

| 查看此信息 | 执行此操作 |
|:---------------|:----------|
| 用户帐户 | 将 **Get-InformationBarrierRecipientStatus** cmdlet 与 Identity 参数配合使用。 <p> 语法： `Get-InformationBarrierRecipientStatus -Identity <value> -Identity2 <value>` <p> 可以使用任何唯一标识每个用户的值，例如名称、别名、可分辨名称、规范域名、电子邮件地址或 GUID。 <p> 例如：`Get-InformationBarrierRecipientStatus -Identity meganb -Identity2 alexw` <p> 在此示例中，我们引用了Office 365中的两个用户帐户：*Megan* 的 *meganb* 和 *Alexw* for *Alexw*。 <p>  (还可以对单个用户使用此 cmdlet： `Get-InformationBarrierRecipientStatus -Identity <value>`)  <p> 此 cmdlet 返回有关用户的信息，例如属性值和应用的任何信息屏障策略。|
| 段 | 使用 **Get-OrganizationSegment** cmdlet。<p> 语法： `Get-OrganizationSegment` <p> 此 cmdlet 将显示为组织定义的所有段的列表。 |
| 信息屏障策略 | 使用 **Get-InformationBarrierPolicy** cmdlet。 <p> 语法： `Get-InformationBarrierPolicy` <p> 此 cmdlet 将显示已定义的信息屏障策略及其状态列表。 |
| 最新的信息屏障策略应用程序 | 使用 **Get-InformationBarrierPoliciesApplicationStatus** cmdlet。 <p> 语法： `Get-InformationBarrierPoliciesApplicationStatus`<p> 此 cmdlet 将显示有关策略应用程序是否已完成、失败还是正在进行的信息。 |
| 所有信息屏障策略应用程序|使用 `Get-InformationBarrierPoliciesApplicationStatus -All`<p> 此 cmdlet 将显示有关策略应用程序是否已完成、失败还是正在进行的信息。|

<!-- IN the " The most recent information barrier policy application, add link to troubleshooting topic -->

### <a name="what-if-i-need-to-remove-or-change-policies"></a>如果需要删除或更改策略，该怎么办？

资源可用于帮助你管理信息屏障策略。

- 如果信息屏障出现问题，请参阅 [信息屏障疑难解答](/office365/troubleshoot/information-barriers/information-barriers-troubleshooting)。
- 若要阻止应用策略，请 [参阅"停止策略应用程序](information-barriers-edit-segments-policies.md#stop-a-policy-application)"。
- 若要删除信息屏障策略，请参阅 ["删除策略](information-barriers-edit-segments-policies.md#remove-a-policy)"。
- 若要对段或策略进行更改，请参阅 ["编辑 (或删除) 信息屏障策略](information-barriers-edit-segments-policies.md)。

## <a name="step-5-configuration-for-information-barriers-on-sharepoint-and-onedrive"></a>步骤 5：针对SharePoint和OneDrive的信息屏障进行配置

如果要为SharePoint和OneDrive配置信息屏障，则需要在这些服务上启用信息屏障。 如果要为Microsoft Teams配置信息屏障，则还需要在这些服务上启用信息屏障。 创建Microsoft Teams团队时，会自动创建SharePoint站点，并与文件体验的Microsoft Teams相关联。 默认情况下，此 SharePoint 网站和文件不适用信息屏障策略。

若要在SharePoint和OneDrive中启用信息屏障，请按照SharePoint文章中的["使用信息屏障](/sharepoint/information-barriers)"中的指导和步骤操作。

## <a name="step-6-information-barriers-modes"></a>步骤 6：信息屏障模式

模式可帮助加强基于资源 IB 模式的Microsoft 365资源的访问、共享和成员身份。 Microsoft 365 组、Microsoft Teams、OneDrive 和SharePoint站点上支持模式，并在新的或现有的 IB 配置中自动启用。

Microsoft 365资源支持以下 IB 模式：

| **Mode** | **说明** | **示例** |
|:-----|:------------|:--------|
| “**打开**” | 没有任何与Microsoft 365资源关联的 IB 策略或段。 任何人都可以被邀请成为资源的成员。 | 为组织野餐活动创建的团队网站。 |
| **所有者审查 (预览)** | Microsoft 365资源的 IB 策略由资源所有者的 IB 策略确定。 资源所有者可以根据其 IB 策略邀请任何用户访问资源。 当你的公司希望允许由所有者审查的不兼容段用户之间进行协作时，此模式非常有用。 只有资源所有者可以根据其 IB 策略添加新成员。 | HR 的 VP 希望与销售和研究的 VP 协作。 使用 IB 模式 *"所有者审查*"设置的新SharePoint网站，用于将销售和研究部门用户同时添加到同一网站。 所有者有责任确保将适当的成员添加到资源中。 |
| **隐式** | Microsoft 365资源的 IB 策略或段继承自资源成员 IB 策略。 所有者可以添加成员，只要它们与资源的现有成员兼容。 这是Microsoft Teams的默认 IB 模式。 | Sales 细分用户创建一个Microsoft Teams团队，以便与组织中的其他兼容细分市场进行协作。 |
| **Explicit** | Microsoft 365资源的 IB 策略是根据与资源关联的段。 资源所有者或SharePoint管理员能够管理资源上的段。  | 仅为销售部门成员创建的网站，通过将 Sales 细分与网站关联来进行协作。   |

有关信息屏障模式以及如何跨服务配置它们的详细信息，请参阅以下文章：

- [格式屏障模式和 Microsoft Teams](/microsoftteams/information-barriers-in-teams)
- [格式屏障模式和 OneDrive](/onedrive/information-barriers)
- [格式屏障模式和 SharePoint](/sharepoint/information-barriers)

## <a name="example-scenario-contosos-departments-segments-and-policies"></a>示例方案：Contoso 的部门、细分和策略

若要了解组织如何定义细分和策略，请考虑以下示例方案。

### <a name="contosos-departments-and-plan"></a>Contoso 的部门与计划

Contoso 有五个部门：人力资源、销售、市场营销、研究和制造。 为了保持遵守行业法规，某些部门的人员不应与其他部门沟通，如下表所示：

| 用户群 | 可以沟通 | 不可以沟通 |
|:----------|:--------------|:-----------------|
| 人力资源 | 所有人 | （无限制） |
| 销售 | HR、Marketing、Manufacturing | 信息检索 |
| 市场营销 | 所有人 | （无限制） |
| 研究 | HR、Marketing、Manufacturing | 销售 |
| 制造 | HR、Marketing | 除 HR 或 Marketing 以外的任何人 |

对于此结构，Contoso 的计划包括三个信息屏障策略：

1. 旨在防止 Sales 与 Research (通信的策略，以及防止 Research 与 Sales) 通信的另一项策略。

2. 一项策略，旨在允许制造仅与 HR 和 Marketing 通信。

对于此方案，无需为 HR 或 Marketing 定义策略。

### <a name="contosos-defined-segments"></a>Contoso 定义的用户群

Contoso 将使用 Azure Active Directory 中的 Department 属性来定义段，如下所示：

| Department | 段定义 |
|:-------------|:---------------------|
| 人力资源 | `New-OrganizationSegment -Name "HR" -UserGroupFilter "Department -eq 'HR'"` |
| 销售 | `New-OrganizationSegment -Name "Sales" -UserGroupFilter "Department -eq 'Sales'"` |
| 市场营销 | `New-OrganizationSegment -Name "Marketing" -UserGroupFilter "Department -eq 'Marketing'"` |
| 研究 | `New-OrganizationSegment -Name "Research" -UserGroupFilter "Department -eq 'Research'"` |
| 制造 | `New-OrganizationSegment -Name "Manufacturing" -UserGroupFilter "Department -eq 'Manufacturing'"` |

定义用户群后，Contoso 将继续定义策略。

### <a name="contosos-information-barrier-policies"></a>Contoso 的信息屏障策略

如下表所述，Contoso 定义了三个策略：

| 策略 | 策略定义 |
|:---------|:--------------------|
| **策略1：防止销售与研究部门沟通** | `New-InformationBarrierPolicy -Name "Sales-Research" -AssignedSegment "Sales" -SegmentsBlocked "Research" -State Inactive` <p> 此示例中，信息屏障策略称为 *销售-研究*。 此策略处于活动状态并已应用时，它将帮助防止销售部门中的用户与研究部门中的用户沟通。 此策略是单向策略;它不会阻止研究与 Sales 通信。 因此，需要策略 2。 |
| **策略 2：阻止研究与销售部门沟通** | `New-InformationBarrierPolicy -Name "Research-Sales" -AssignedSegment "Research" -SegmentsBlocked "Sales" -State Inactive` <p> 在此例中，信息屏障策略称为 *研究-销售*。 此策略处于活动状态并已应用时，它将帮助防止研究部门中的用户与销售部门中的用户沟通。 |
| **策略 3：允许制造仅与人力资源和市场营销通信** | `New-InformationBarrierPolicy -Name "Manufacturing-HRMarketing" -AssignedSegment "Manufacturing" -SegmentsAllowed "HR","Marketing","Manufacturing" -State Inactive` <p> 在这种情况下，信息屏障策略称为 *制造-人力资源市场营销*。 此策略处于活动状态和已应用后，制造仅能与人力资源和市场营销部门沟通。 不限制人力资源和营销与其他细分市场进行通信。 |

在定义段和策略后，Contoso 通过运行 **Start-InformationBarrierPoliciesApplication** cmdlet 应用策略。

cmdlet 完成后，Contoso 符合法律和行业要求。

## <a name="resources"></a>资源

- [获取信息屏障概述](information-barriers.md)
- [详细了解Microsoft Teams中的信息障碍](/MicrosoftTeams/information-barriers-in-teams)
- [详细了解联机SharePoint信息障碍](/sharepoint/information-barriers)
- [详细了解OneDrive中的信息障碍](/onedrive/information-barriers)
