---
title: 定义信息屏障策略
description: 了解如何为信息屏障定义策略Microsoft Teams。
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
localization_priority: None
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 8b29c2f5256c991e327e8962f02a96a294a6bec6
ms.sourcegitcommit: a0185d6b0dd091db6e1e1bfae2f68ab0e3cf05e5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/13/2021
ms.locfileid: "58246557"
---
# <a name="define-information-barrier-policies"></a>定义信息屏障策略

通过信息屏障，你可以定义旨在阻止某些用户区段相互通信的策略，或允许特定细分仅与某些其他分段进行通信。 信息屏障策略可帮助组织保持对相关行业标准和法规的合规性，并避免潜在的兴趣冲突。 若要了解详细信息，请参阅 [信息屏障](information-barriers.md)。

本文介绍如何规划、定义、实现和管理信息屏障策略。 涉及几个步骤，并且工作流程分为几个部分。 在开始定义策略或编辑信息[](#prerequisites)屏障策略之前， (先决条件) 整个过程。

> [!TIP]
> 本文包含一 [个示例方案](#example-contosos-departments-segments-and-policies) ，可帮助你计划和定义信息屏障策略。

## <a name="concepts-of-information-barrier-policies"></a>信息屏障策略的概念

定义信息屏障策略时，你将使用用户帐户属性、分段、"阻止"和/或"允许"策略以及策略应用程序。

- 用户帐户属性 在 Azure Active Directory（或 Exchange Online）中定义。 这些属性可能包括部门、职务、位置、团队名称和其他职务资料详细信息。 
- 分段是使用所选用户帐户属性在安全与&中心 **定义的用户组**。 （请参阅 [支持的属性列表](information-barriers-attributes.md)。）
- 信息屏障策略决定了通信限制或限制。 定义信息屏障策略时，可以从以下两种策略中选择：
  - "阻止"策略阻止一个段与另一个段通信。
  - "允许"策略允许一个段仅与某些其他段通信。
- 策略应用 之前应先定义所有信息屏障策略。全部定义之后，则已准备好在组织中应用这些策略。

## <a name="the-work-flow-at-a-glance"></a>工作流程概览

| 阶段 | 所涉及的内容 |
|:--------|:------------------|
| [确保满足先决条件](#prerequisites) | - 验证您是否具有 [所需的许可证和权限](information-barriers.md#required-licenses-and-permissions)<br/>- 验证目录是否包含用于分段用户的数据<br/>- 为用户启用作用域内目录Microsoft Teams<br/>- 确保审核日志记录已打开<br/>- 确保没有Exchange通讯簿策略<br/>- 使用 PowerShell (提供了示例) <br/>- 提供管理员同意Microsoft Teams (步骤包含在)  |
| [第 1 部分：划分组织中用户](#part-1-segment-users) | - 确定需要哪些策略<br/>- 创建要定义的线段列表<br/>- 确定要使用哪些属性<br/>- 根据策略筛选器定义分段 |
| [第 2 部分：定义信息屏障策略](#part-2-define-information-barrier-policies) | - 定义策略 (尚不适用) <br/>- 从两种类型的 (选择或允许)  |
| [第 3 部分：应用信息屏障策略](#part-3-apply-information-barrier-policies) | - 将策略设置为活动状态<br/>- 运行策略应用程序<br/>- 查看策略状态 |
|  (根据需要) [编辑段或策略](information-barriers-edit-segments-policies.md) | - 编辑线段<br/>- 编辑或删除策略<br/>- 重新运行策略应用程序<br/>- 查看策略状态 |
|  (根据需要) [疑难解答](information-barriers-troubleshooting.md)| - 在未如预期运行时采取措施|

## <a name="prerequisites"></a>先决条件

除了所需的 [许可证和权限](information-barriers.md#required-licenses-and-permissions)之外，请确保满足以下要求：

- 目录数据 - 确保组织的结构反映在目录数据中。 若要采取此操作，请确保用户帐户属性（如组成员身份、部门名称等）正确填充在 Azure Active Directory (或 Exchange Online) 。 若要了解详细信息，请参阅以下资源：
  - [信息屏障策略的属性](information-barriers-attributes.md)
  - [使用自定义设置添加或更新Azure Active Directory](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)
  - [使用 Office 365 PowerShell 配置用户帐户的属性](../enterprise/configure-user-account-properties-with-microsoft-365-powershell.md)

- 作用域目录搜索 - 在定义组织的第一个信息屏障策略之前，必须在 Microsoft Teams 中启用作用域[目录搜索](/MicrosoftTeams/teams-scoped-directory-search)。 在启用作用域目录搜索后至少等待 24 小时，然后再设置或定义信息屏障策略。

- EXO 许可证 - 仅在目标用户分配了 EXO 许可证时，IBM 策略才正常工作。

- 审核日志记录 - 为了查找策略应用程序的状态，必须启用审核日志记录。 建议在开始定义分段或策略之前启用审核。 若要了解更多信息，请参阅 [打开审核日志或关闭搜索](turn-audit-log-search-on-or-off.md)。

- 无通讯簿策略 - 定义和应用信息屏障策略之前，请确保Exchange通讯簿策略。 信息屏障基于通讯簿策略，但两种类型的策略不兼容。 如果您具有此类策略，请确保首先 [删除通讯簿](/exchange/address-books/address-book-policies/remove-an-address-book-policy) 策略。 启用信息屏障策略并启用分层通讯簿后，未包含在信息屏障段中的所有用户都将在 Exchange 通讯簿。 [](/exchange/address-books/hierarchical-address-books/hierarchical-address-books)

- PowerShell - 目前，使用 PowerShell cmdlet 在 Office 365 安全&中心定义和管理信息屏障策略。 尽管本文提供了几个示例，但您需要熟悉 PowerShell cmdlet 和参数。 您还需要该Azure PowerShell模块。
  - [连接到安全与合规中心 PowerShell](/powershell/exchange/connect-to-scc-powershell)
  - [安装Azure PowerShell模块](/powershell/azure/install-az-ps)

- 管理员同意 Microsoft Teams 中的信息屏障 - 如果符合您的 IBM 策略，他们可以从组 (（即基于组) 的 Teams 频道）中删除非 TEAMS 合规性用户。 此配置有助于确保组织符合策略和法规。 使用以下过程使信息屏障策略能够按照预期在Microsoft Teams。

   1. 先决条件：从 Install Azure PowerShell[安装Azure PowerShell。](/powershell/azure/install-az-ps)

   1. 运行以下 PowerShell cmdlet：

      ```powershell
      Connect-AzAccount -Tenant "<yourtenantdomain.com>"  //for example: Connect-AzAccount -Tenant "Contoso.onmicrosoft.com"
      $appId="bcf62038-e005-436d-b970-2a472f8c1982" 
      $sp=Get-AzureADServicePrincipal -Filter "appid eq '$($appid)'"
      if ($sp -eq $null) { New-AzureADServicePrincipal -ApplicationId $appId }
      Start-Process  "https://login.microsoftonline.com/common/adminconsent?client_id=$appId"
      ```

   1. 系统提示时，使用工作或学校帐户登录Office 365。

   1. 在"**请求的权限"** 对话框中，查看信息，然后选择"接受 **"。** 应用程序请求的权限如下所示。

      > [!div class="mx-imgBorder"]
      > ![图像](https://user-images.githubusercontent.com/8932063/107690955-b1772300-6c5f-11eb-9527-4235de860b27.png)

满足所有先决条件后，继续下一节。

> [!TIP]
> 为了帮助你准备计划，本文中包括了一个示例方案。 [请参阅 Contoso 的部门、部门和策略](#example-contosos-departments-segments-and-policies)。

## <a name="part-1-segment-users"></a>第 1 部分：划分用户

在此阶段中，确定需要哪些信息屏障策略，创建要定义的分段列表，然后定义你的分段。

### <a name="determine-what-policies-are-needed"></a>确定需要哪些策略

考虑法律和行业法规，贵组织中哪些组需要信息屏障策略？ 创建列表。 应阻止任何组与另一个组通信？ 是否允许任何组仅与一个或两个其他组通信？ 将所需的策略视为属于以下两个组之一：

- "阻止"策略阻止一个组与另一个组通信。
- "允许"策略允许组仅与某些其他特定组通信。

当你拥有组和策略的初始列表时，请继续确定你需要的分段。

### <a name="identify-segments"></a>标识线段

除了初始策略列表之外，请为组织创建一个分段列表。 将包含在信息屏障策略中的用户应属于某个类别。 请仔细规划你的分段，因为用户只能在一个分段中。 每个分段只能应用一个信息屏障策略。

> [!IMPORTANT]
> 用户只能有一个区段。

确定要用于定义分段的组织目录数据中的哪些属性。 可以使用 *Department、MemberOf* 或任何受支持的属性。  请确保你在为用户选择的 属性中具有值。 [有关信息屏障，请参阅受支持的属性列表](information-barriers-attributes.md)。

> [!IMPORTANT]
> **在继续下一节之前**，请确保目录数据具有可用于定义分段的属性值。 如果您的目录数据没有您想要使用的属性的值，则必须先更新用户帐户以包含该信息，然后才能继续信息屏障。 若要获取有关此内容的帮助，请参阅以下资源：<br/>- [使用 PowerShell 配置Office 365属性](../enterprise/configure-user-account-properties-with-microsoft-365-powershell.md)<br/>- [使用自定义设置添加或更新Azure Active Directory](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)

### <a name="define-segments-using-powershell"></a>使用 PowerShell 定义分段

定义分段不会影响用户;它只是设置要定义并应用的信息屏障策略的阶段。

1. 将 **New-OrganizationSegment** cmdlet 与对应于您想要使用的属性的 **UserGroupFilter** 参数一同使用。 [](information-barriers-attributes.md)

    | 语法 | 示例 |
    |:---------|:----------|
    | `New-OrganizationSegment -Name "segmentname" -UserGroupFilter "attribute -eq 'attributevalue'"` |`New-OrganizationSegment -Name "HR" -UserGroupFilter "Department -eq 'HR'"` <p>在此例中，名为 *HR* 的段使用 *HR* 进行定义，这是 Department 属性 *中的* 值。 cmdlet 的 **-eq** 部分引用"equals"。  (，可以使用 **-ne** 表示"不等于"。 请参阅 [使用段定义 .) ](#using-equals-and-not-equals-in-segment-definitions)中的"等于"和"不)  |

    运行每个 cmdlet 后，应看到有关新段的详细信息列表。 详细信息包括类别类型、创建者或上次修改者等。 

2. 对要定义的每个段重复此过程。

    > [!IMPORTANT]
    > **请确保你的线段不重叠**。 将受信息障碍影响的每个用户应属于一个组 (一个) 类别。 用户不应属于两个或多个类别。  ([请参阅本文中的示例：Contoso](#contosos-defined-segments) 的定义) 

定义分段后，继续定义 [信息屏障策略](#part-2-define-information-barrier-policies)。

### <a name="using-equals-and-not-equals-in-segment-definitions"></a>在线段定义中使用"equals"和"not equals"

在下面的示例中，我们定义一个"Department equals HR"的段。 

| 示例 | 注释 |
|:----------|:-------|
|`New-OrganizationSegment -Name "HR" -UserGroupFilter "Department -eq 'HR'"` | 请注意，此示例中的线段定义包含一个表示为 **-eq** 的"equals"参数。 |

您还可以使用"不等于"参数定义线段，该参数表示为 **-ne，** 如下表所示：

| 语法 | 示例 |
|:---------|:----------|
| `New-OrganizationSegment -Name "NotSales" -UserGroupFilter "Department -ne 'Sales'"` | 本示例中，我们定义了一个称为 *NotSales* 的段，其中包括不在销售部门 *中的每个人*。 cmdlet 的 **-ne** 部分引用"不等于"。 |

除了使用"equals"或"not equals"定义线段之外，您还可以使用"equals"和"not equals"参数定义线段。 您还可以使用逻辑 *AND* 和 OR 运算符定义复杂的 *组* 筛选器。

| 语法 | 示例 |
|:---------|:----------|
| `New-OrganizationSegment -Name "LocalFTE" -UserGroupFilter "Location -eq 'Local'" -and "Position -ne 'Temporary'"` | 本示例中，我们定义了一个称为 *LocalFTE* 的段，其中包括位于本地且其位置未列为"临时 *"的人*。 |
| `New-OrganizationSegment -Name "Segment1" -UserGroupFilter "MemberOf -eq 'group1@contoso.com'' -and MemberOf -ne 'group3@contoso.com'"`| 本示例中，我们定义了一个称为 *Segment1* 的段，其中包括作为 group1@contoso.com 成员而不是 group3@contoso.com。 |
| `New-OrganizationSegment -Name "Segment2" -UserGroupFilter "MemberOf -eq 'group2@contoso.com' -or MemberOf -ne 'group3@contoso.com'"` | 本示例中，我们定义了一个称为 *Segment2* 的段，其中包括作为用户 group2@contoso.com 而不是 group3@contoso.com。 |
| `New-OrganizationSegment -Name "Segment1and2" -UserGroupFilter "(MemberOf -eq 'group1@contoso.com' -or MemberOf -eq 'group2@contoso.com') -and MemberOf -ne 'group3@contoso.com'"`| 本示例中，我们定义了一个称为 *Segment1and2* 的段，其中包含 group1@contoso.com 和 group2@contoso.com 的成员，而不是 group3@contoso.com。 |

> [!TIP]
> 如果可能，请使用包含"-eq"或"-ne"的线段定义。 尽量不要定义复杂的线段定义。

## <a name="part-2-define-information-barrier-policies"></a>第 2 部分：定义信息屏障策略

确定是需要阻止某些分段之间的通信，还是限制与某些段的通信。 理想情况下，你将使用最少数量的策略，以确保你的组织符合法律和行业要求。

使用要定义的用户区段列表和信息屏障策略，选择一个方案，然后按照步骤操作。

- [方案 1：阻止区段之间的通信](#scenario-1-block-communications-between-segments)
- [方案 2：允许一个区段仅与另一个区段通信](#scenario-2-allow-a-segment-to-communicate-only-with-one-other-segment)

> [!IMPORTANT]
> **请确保在定义策略时，不要** 向一个段分配多个策略。 例如，如果为名为 Sales 的段定义一个策略，则不要为 Sales 定义其他 *策略*。<p> 此外，在定义信息屏障策略时，请确保将这些策略设置为非活动状态，直到准备好应用它们。 定义 (编辑) 策略不会影响用户，除非这些策略设置为活动状态，然后应用。

 ([请参阅本文中的示例：Contoso](#contosos-information-barrier-policies) 的信息屏障) 

### <a name="scenario-1-block-communications-between-segments"></a>方案 1：阻止区段之间的通信

当你想要阻止分段相互通信时，你可以定义两个策略：每个方向一个策略。 每个策略仅阻止一个方向的通信。

例如，假设您要阻止段 A 和段 B 之间的通信。在这种情况下，定义一个策略来阻止段 A 与段 B 通信，然后定义第二个策略以防止段 B 与段 A 通信。

1. 若要定义第一个阻止策略，请使用 **New-InformationBarrierPolicy** cmdlet 和 **SegmentsBlocked** 参数。

    | 语法 | 示例 |
    |:--------|:----------|
    | `New-InformationBarrierPolicy -Name "policyname" -AssignedSegment "segment1name" -SegmentsBlocked "segment2name"` | `New-InformationBarrierPolicy -Name "Sales-Research" -AssignedSegment "Sales" -SegmentsBlocked "Research" -State Inactive` <p> 在此示例中，我们为名为 Sales 的段定义了名为 *Sales-Research* *的策略*。 当处于活动状态和应用时，此策略会阻止 *销售* 部门中的人员与名为 Research 的部门中的 *人员通信*。 |

2. 若要定义第二个阻止线段，请再次使用带 **SegmentsBlocked** 参数的 **New-InformationBarrierPolicy** cmdlet，这次反向使用分段。

    | 示例 | 注释 |
    |:----------|:-------|
    |`New-InformationBarrierPolicy -Name "Research-Sales" -AssignedSegment "Research" -SegmentsBlocked "Sales" -State Inactive` | 本示例中，我们定义了一个称为 *"Research-Sales"* 的策略，以阻止 *Research* 与 *Sales 通信*。 |

3. 继续执行下列操作之一：

   -  (如果需要) [定义一个策略以](#scenario-2-allow-a-segment-to-communicate-only-with-one-other-segment)允许一个段仅与其他一个段通信 
   -  (定义所有策略后) [应用信息屏障策略](#part-3-apply-information-barrier-policies)

### <a name="scenario-2-allow-a-segment-to-communicate-only-with-one-other-segment"></a>方案 2：允许一个区段仅与另一个区段通信

1. 若要允许一个段仅与其他一个段通信，请使用 **New-InformationBarrierPolicy** cmdlet 和 **SegmentsAllowed** 参数。

    | 语法 | 示例 |
    |:----------|:----------|
    | `New-InformationBarrierPolicy -Name "policyname" -AssignedSegment "segment1name" -SegmentsAllowed "segment2name","segment1name"` | `New-InformationBarrierPolicy -Name "Manufacturing-HR" -AssignedSegment "Manufacturing" -SegmentsAllowed "HR","Manufacturing" -State Inactive` <p> 在此例中，我们为名为"制造"的线段定义了一个称为 *"制造-HR"**的策略*。 当激活和应用时，此策略允许制造中的人员仅与名为 HR 的部门中的人员 *通信*。  (在这种情况下，*制造* 无法与 HR *.)* |

    **如果需要，可以使用此 cmdlet 指定多个线段，如以下示例所示。**

    | 语法 | 示例 |
    |:---------|:----------|
    | `New-InformationBarrierPolicy -Name "policyname" -AssignedSegment "segment1name" -SegmentsAllowed "segment2name", "segment3name","segment1name"` | `New-InformationBarrierPolicy -Name "Research-HRManufacturing" -AssignedSegment "Research" -SegmentsAllowed "HR","Manufacturing","Research" -State Inactive` <p> 在此例中，我们定义了一个策略，允许 *研究* 部门仅与 *人力资源* 和制造 *部门进行通信*。 |

    对要定义的每个策略重复此步骤，以允许特定分段仅与其他特定分段进行通信。

2. 继续执行下列操作之一：

   -  (如果需要) [定义阻止分段之间通信的策略](#scenario-1-block-communications-between-segments) 
   -  (定义所有策略后) [应用信息屏障策略](#part-3-apply-information-barrier-policies)

## <a name="part-3-apply-information-barrier-policies"></a>第 3 部分：应用信息屏障策略

在将信息屏障策略设置为活动状态，然后应用这些策略之前，这些策略才会生效。

1. 使用 **Get-InformationBarrierPolicy** cmdlet 查看已定义的策略列表。 记下每个策略 (GUID) 和标识。

    语法： `Get-InformationBarrierPolicy`

2. 若要将策略设置为活动状态，请使用带 **Identity** 参数的 **Set-InformationBarrierPolicy** cmdlet，将 **State** 参数设置为 **Active**。 

    | 语法 | 示例 |
    |:---------|:----------|
    | `Set-InformationBarrierPolicy -Identity GUID -State Active` | `Set-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c93772471 -State Active` <p> 在此例中，我们将 GUID *为 43c37853-ea10-4b90-a23d-ab8c93772471* 的信息屏障策略设置为活动状态。 |

    根据需要对每个策略重复此步骤。

3. 完成将信息屏障策略设置为活动状态后，请使用安全与合规中心中的 **Start-InformationBarrierPoliciesApplication** cmdlet & Cmdlet。

    语法： `Start-InformationBarrierPoliciesApplication`

    运行 后 `Start-InformationBarrierPoliciesApplication` ，允许系统 30 分钟开始应用策略。 系统按用户应用策略。 系统每小时处理大约 5，000 个用户帐户。

## <a name="view-status-of-user-accounts-segments-policies-or-policy-application"></a>查看用户帐户、分段、策略或策略应用程序的状态

通过 PowerShell，您可以查看用户帐户、分段、策略和策略应用程序的状态，如下表所列。

| 查看此信息 | 采取此操作 |
|:---------------|:----------|
| 用户帐户 | 将 **Get-InformationBarrierRecipientStatus** cmdlet 与 Identity 参数一同使用。 <p> 语法： `Get-InformationBarrierRecipientStatus -Identity <value> -Identity2 <value>` <p> 可以使用任何能够唯一标识每个用户的值，如名称、别名、可分辨名称、规范域名、电子邮件地址或 GUID。 <p> 示例：`Get-InformationBarrierRecipientStatus -Identity meganb -Identity2 alexw` <p> 本示例中，我们引用了 Office 365 中的两个用户帐户 *：meganb* 表示 *Megan，alexw* 表示 *Alex。*  <p>  (也可以对单个用户使用此 cmdlet：) `Get-InformationBarrierRecipientStatus -Identity <value>` <p> 此 cmdlet 返回有关用户的信息，例如属性值和应用的任何信息屏障策略。|
| 分段 | 使用 **Get-OrganizationSegment** cmdlet。<p> 语法： `Get-OrganizationSegment` <p> 此 cmdlet 将显示为组织定义的所有分段的列表。 |
| 信息屏障策略 | 使用 **Get-InformationBarrierPolicy** cmdlet。 <p> 语法： `Get-InformationBarrierPolicy` <p> 此 cmdlet 将显示已定义的信息屏障策略及其状态的列表。 |
| 最新信息屏障策略应用程序 | 使用 **Get-InformationBarrierPoliciesApplicationStatus** cmdlet。 <p> 语法： `Get-InformationBarrierPoliciesApplicationStatus`<p> 此 cmdlet 将显示有关策略应用程序已完成、失败还是正在进行的信息。 |
| 所有信息屏障策略应用程序|使用 `Get-InformationBarrierPoliciesApplicationStatus -All`<p> 此 cmdlet 将显示有关策略应用程序已完成、失败还是正在进行的信息。|

<!-- IN the " The most recent information barrier policy application, add link to troubleshooting topic -->

## <a name="what-if-i-need-to-remove-or-change-policies"></a>如果需要删除或更改策略，如何？

资源可帮助您管理信息屏障策略。

- 如果信息屏障出现问题，请参阅 [解决信息障碍](information-barriers-troubleshooting.md)问题。
- 若要阻止应用策略，请参阅停止 [策略应用程序](information-barriers-edit-segments-policies.md#stop-a-policy-application)。
- 若要删除信息屏障策略，请参阅删除 [策略](information-barriers-edit-segments-policies.md#remove-a-policy)。
- 若要更改分段或策略，请参阅编辑 ([或删除) 信息屏障策略](information-barriers-edit-segments-policies.md)。

## <a name="example-contosos-departments-segments-and-policies"></a>示例：Contoso 的部门、部门和策略

若要了解组织会如何定义用户群和策略，请考虑以下示例。

### <a name="contosos-departments-and-plan"></a>Contoso 的部门与计划

Contoso 有五个部门：人力资源、销售、市场营销、研究和制造。 为了符合行业法规，某些部门中的人员不应与其他部门进行通信，如下表所示：

| 用户群 | 可以沟通 | 不可以沟通 |
|:----------|:--------------|:-----------------|
| 人力资源 | 所有人 | （无限制） |
| 销售 | 人力资源、市场营销、制造 | 研究 |
| 市场营销 | 所有人 | （无限制） |
| 研究 | 人力资源、市场营销、制造 | 销售 |
| 制造 | HR、Marketing | 除 HR 或 Marketing 外的任何人员 |

对于此结构，Contoso 的计划包括三个信息屏障策略：

1. 一个策略，用于阻止销售部门与研究 (，另一个策略阻止研究与销售) 。

2. 旨在允许制造部门仅与 HR 和市场营销部门进行通信的策略。

对于此方案，不需要为 HR 或 Marketing 定义策略。

### <a name="contosos-defined-segments"></a>Contoso 定义的用户群

Contoso 将使用 Azure Active Directory 中的 Department 属性定义分段，如下所示：

| 部门 | 线段定义 |
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
| **策略1：防止销售与研究部门沟通** | `New-InformationBarrierPolicy -Name "Sales-Research" -AssignedSegment "Sales" -SegmentsBlocked "Research" -State Inactive` <p> 此示例中，信息屏障策略称为 *销售-研究*。 此策略处于活动状态并已应用时，它将帮助防止销售部门中的用户与研究部门中的用户沟通。 此策略是单向策略;它不会阻止 Research 与销售部门通信。 因此，需要策略 2。 |
| **策略 2：阻止研究与销售部门沟通** | `New-InformationBarrierPolicy -Name "Research-Sales" -AssignedSegment "Research" -SegmentsBlocked "Sales" -State Inactive` <p> 在此例中，信息屏障策略称为 *研究-销售*。 此策略处于活动状态并已应用时，它将帮助防止研究部门中的用户与销售部门中的用户沟通。 |
| **策略 3：仅允许制造与 HR 和市场营销部门进行通信** | `New-InformationBarrierPolicy -Name "Manufacturing-HRMarketing" -AssignedSegment "Manufacturing" -SegmentsAllowed "HR","Marketing","Manufacturing" -State Inactive` <p> 在这种情况下，信息屏障策略称为 *制造-人力资源市场营销*。 此策略处于活动状态和已应用后，制造仅能与人力资源和市场营销部门沟通。 人力资源和市场营销部不限制与其他部门进行通信。 |

定义分段和策略后，Contoso 通过运行 **Start-InformationBarrierPoliciesApplication** cmdlet 来应用策略。

cmdlet 完成后，Contoso 符合法律和行业要求。

## <a name="resources"></a>资源

- [获取信息屏障概述](information-barriers.md)
- [详细了解信息障碍Microsoft Teams](/MicrosoftTeams/information-barriers-in-teams)
- [详细了解 SharePoint Online 中的信息障碍](/sharepoint/information-barriers)
- [详细了解信息障碍OneDrive](/onedrive/information-barriers)
