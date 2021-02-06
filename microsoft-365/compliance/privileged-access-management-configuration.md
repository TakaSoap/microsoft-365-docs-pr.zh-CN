---
title: 特权访问管理入门
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- m365-security-compliance
- m365solution-insiderrisk
- m365initiative-compliance
ms.custom:
- Ent_Solutions
- seo-marvel-apr2020
ms.assetid: ''
description: 使用本文详细了解如何启用和配置 Office 365 中的特权访问管理。
ms.openlocfilehash: 0b8d79c3012ecd321d7b00c1566aa557077d55f1
ms.sourcegitcommit: eac5d9f759f290d3c51cafaf335a1a1c43ded927
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2021
ms.locfileid: "50126529"
---
# <a name="get-started-with-privileged-access-management"></a>特权访问管理入门

本主题指导你完成在组织中启用和配置特权访问管理。 可以使用 Microsoft 365 管理中心或 Exchange 管理 PowerShell 管理和使用特权访问。

## <a name="before-you-begin"></a>准备工作

在开始使用特权访问管理之前，应确认 [Microsoft 365](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans) 订阅和任何加载项。 若要访问和使用特权访问管理，您的组织必须具有以下订阅或加载项之一：

- Microsoft 365 E5 订阅（付费或试用版本）
- Microsoft 365 E3 订阅 (Office 365 E3 订阅 + 企业移动性和安全性 E3 订阅) + Microsoft 365 E5 合规性加载项
- 任何 Microsoft 365、Office 365、Exchange、SharePoint 或 OneDrive for Business 订阅 + Microsoft 365 E5 Insider Risk Management 加载项  
- Microsoft 365 A5 订阅（付费或试用版本）
- Microsoft 365 A3 订阅 (Office 365 A3 订阅 + 企业移动性和安全性 A3) + Microsoft A5 合规性加载项
- 任何 Microsoft 365、Office 365、Exchange、SharePoint 或 OneDrive for Education 订阅 + Microsoft 365 A5 Insider Risk Management 加载项
- Office 365 企业版 E5 订阅（付费或试用版本）
- Office 365 企业版 E3 订阅 + Office 365 高级合规版加载项（新订阅已不再可用，请参阅注释）

必须为提交和响应特权访问管理请求的用户分配上述许可证之一。

>[!IMPORTANT]
>Office 365 高级合规版已不再作为独立订阅销售。 当前订阅到期后，客户应过渡到以上订阅之一，其中包含了相同的或其它合规性功能。

如果你没有现有的 Office 365 企业版 E5 计划，并且想要尝试特权访问管理，可以将[Microsoft 365](/office365/admin/try-or-buy-microsoft-365)添加到现有 Office 365[](https://www.microsoft.com/microsoft-365/enterprise)订阅或注册 Microsoft 365 企业版 E5 试用版。

## <a name="enable-and-configure-privileged-access-management"></a>启用和配置特权访问管理

按照以下步骤在组织中设置和使用特权访问：

- [步骤 1：创建审批者组](privileged-access-management-configuration.md#step1)

    开始使用特权访问之前，请确定哪些人需要审批权限才能对提升和特权任务的访问权限的传入请求。 属于审批者组的任何用户都能够批准访问请求。 通过创建 Office 365 中启用邮件的安全组来启用此组。

- [步骤 2：启用特权访问](privileged-access-management-configuration.md#step2)

    必须在具有默认审批者组的 Office 365 中显式启用特权访问，包括一组您希望从特权访问管理访问控制中排除的系统帐户。

- [步骤 3：创建访问策略](privileged-access-management-configuration.md#step3)

    通过创建审批策略，您可以定义范围为单个任务的特定审批要求。 审批类型选项为 **"自动"或**"**手动"。**

- [步骤 4：提交/批准特权访问请求](privileged-access-management-configuration.md#step4)

    启用后，特权访问需要批准已定义关联审批策略的任何任务。 对于审批策略中包含的任务，用户必须请求并被授予访问权限审批，才能拥有执行该任务所需的权限。

批准授予后，请求用户可以执行预期任务，特权访问将代表用户授权和执行该任务。 审批对请求的持续时间保持有效 (默认持续时间为 4) ，在此期间请求者可以多次执行预期任务。 将记录所有此类执行，并可用于安全性和合规性审核。 

>[!NOTE]
>如果要使用 Exchange 管理 PowerShell 启用和配置特权访问，请按照使用多重身份验证连接到 [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell#connect-to-exchange-online-powershell-using-mfa) 中的步骤，使用 Office 365 凭据连接到 Exchange Online PowerShell。 在连接到 Exchange Online PowerShell 时，无需为组织启用多重身份验证，只需按照步骤启用特权访问。 通过多重身份验证进行连接将创建一个 OAuth 令牌，该令牌由特权访问用于对请求进行签名。

<a name="step1"> </a>

## <a name="step-1-create-an-approvers-group"></a>步骤 1：创建审批者组

1. 使用组织中管理员帐户的凭据登录 [Microsoft 365](https://admin.microsoft.com) 管理中心。

2. 在管理中心，转到"组  >  **添加组"。**

3. 选择 **启用邮件的安全组**，然后完成新组的名称、组电子邮件地址 **和说明** 字段。

4. 保存组。 可能需要几分钟时间才能完全配置组，并出现在 Microsoft 365 管理中心中。

5. 选择新的审批者组，然后选择 **"** 编辑"将用户添加到组中。

6. 保存组。

<a name="step2"> </a>

## <a name="step-2-enable-privileged-access"></a>步骤 2：启用特权访问

### <a name="in-the-microsoft-365-admin-center"></a>在 Microsoft 365 管理中心

1. 使用组织中管理员帐户的凭据登录 [Microsoft 365](https://admin.microsoft.com) 管理中心。

2. 在管理中心中，**转到"设置**  >  **组织** 设置  >  **安全设置&权限**  >  **"。**

3. 启用 **特权任务控件的"需要审批"。**

4. 将你在步骤 1 中创建的审批者组分配为 **默认审批者组**。

5. **保存** 并 **关闭**。

### <a name="in-exchange-management-powershell"></a>在 Exchange 管理 PowerShell 中

若要启用特权访问并分配审批者组，请运行 Exchange Online PowerShell 中的以下命令：

```PowerShell
Enable-ElevatedAccessControl -AdminGroup '<default approver group>' -SystemAccounts @('<systemAccountUPN1>','<systemAccountUPN2>')
```

示例：

```PowerShell
Enable-ElevatedAccessControl -AdminGroup 'pamapprovers@fabrikam.onmicrosoft.com' -SystemAccounts @('sys1@fabrikamorg.onmicrosoft.com', 'sys2@fabrikamorg.onmicrosoft.com')
```

>[!NOTE]
>系统帐户功能可用于确保组织内部的某些自动化能够正常工作，而无需依赖特权访问，但建议此类排除项是例外的，应定期批准和审核允许的排除项。

<a name="step3"> </a>

## <a name="step-3-create-an-access-policy"></a>步骤 3：创建访问策略

你可以为组织创建和配置最多 30 个特权访问策略。

### <a name="in-the-microsoft-365-admin-center"></a>在 Microsoft 365 管理中心

1. 使用组织中管理员帐户的凭据登录 [Microsoft 365](https://admin.microsoft.com) 管理中心。

2. 在管理中心中，**转到"设置**  >  **组织** 设置  >  **安全设置&权限**  >  **"。**

3. 选择 **"管理访问策略和请求"。**

4. 选择 **"配置策略**"，然后选择 **"添加策略"。**

5. 从下拉列表中，为组织选择适当的值：
    
    **策略类型**：任务、角色或角色组

    **策略作用域**：Exchange

    **策略名称**：从可用策略中选择

    **审批类型**：手动或自动

    **审批组**：选择在步骤 1 中创建的审批者组

6. 选择 **"创建** "，然后 **关闭**。 可能需要几分钟时间才能完全配置和启用策略。

### <a name="in-exchange-management-powershell"></a>在 Exchange 管理 PowerShell 中

若要创建和定义审批策略，请运行 Exchange Online PowerShell 中的以下命令：

```PowerShell
New-ElevatedAccessApprovalPolicy -Task 'Exchange\<exchange management cmdlet name>' -ApprovalType <Manual, Auto> -ApproverGroup '<default/custom approver group>'
```

示例：

```PowerShell
New-ElevatedAccessApprovalPolicy -Task 'Exchange\New-MoveRequest' -ApprovalType Manual -ApproverGroup 'mbmanagers@fabrikamorg.onmicrosoft.com'
```

<a name="step4"> </a>

## <a name="step-4-submitapprove-privileged-access-requests"></a>步骤 4：提交/批准特权访问请求

### <a name="requesting-elevation-authorization-to-execute-privileged-tasks"></a>请求提升授权以执行特权任务

特权访问请求的有效期为提交请求后的最多 24 小时。 如果未批准或拒绝，请求将过期，访问将被拒绝。

#### <a name="in-the-microsoft-365-admin-center"></a>在 Microsoft 365 管理中心

1. 使用凭据登录 [Microsoft 365](https://admin.microsoft.com) 管理中心。

2. 在管理中心中，**转到"设置**  >  **组织** 设置  >  **安全设置&权限**  >  **"。**

3. 选择 **"管理访问策略和请求"。**

4. 选择 **"新建请求"。** 从下拉列表中，为组织选择适当的值：

    **请求类型**：任务、角色或角色组

    **请求范围**： Exchange

    **请求：** 从可用策略中选择

    **持续时间 (小时数) ：** 请求的访问小时数。 可以请求的小时数没有限制。

    **注释**：与访问请求相关的注释的文本字段

5. 选择 **"保存** "，然后 **关闭**。 您的请求将通过电子邮件发送到审批者组。

#### <a name="in-exchange-management-powershell"></a>在 Exchange 管理 PowerShell 中

在 Exchange Online PowerShell 中运行以下命令，创建审批请求并提交到审批者组：

```PowerShell
New-ElevatedAccessRequest -Task 'Exchange\<exchange management cmdlet name>' -Reason '<appropriate reason>' -DurationHours <duration in hours>
```

示例：

```PowerShell
New-ElevatedAccessRequest -Task 'Exchange\New-MoveRequest' -Reason 'Attempting to fix the user mailbox error' -DurationHours 4
```

### <a name="view-status-of-elevation-requests"></a>查看提升请求的状态

创建审批请求后，可以使用与请求 ID 关联的权限提升请求状态在管理中心或 Exchange 管理 PowerShell 中查看。

#### <a name="in-the-microsoft-365-admin-center"></a>在 Microsoft 365 管理中心

1. 使用凭据登录 [Microsoft 365](https://admin.microsoft.com) 管理中心。

2. 在管理中心，转到"**设置**  >  **组织** 设置  >  **安全设置&权限**  >  **"。**

3. 选择 **"管理访问策略和请求"。**

4. Select **View** to filter submitted requests by **Pending，** **Approved，** **Denied，** or **Customer Lockbox** status.

#### <a name="in-exchange-management-powershell"></a>在 Exchange 管理 PowerShell 中

在 Exchange Online PowerShell 中运行以下命令以查看特定请求 ID 的审批请求状态：

```PowerShell
Get-ElevatedAccessRequest -Identity <request ID> | select RequestStatus
```

示例：

```PowerShell
Get-ElevatedAccessRequest -Identity 28560ed0-419d-4cc3-8f5b-603911cbd450 | select RequestStatus
```

### <a name="approving-an-elevation-authorization-request"></a>批准提升授权请求

创建审批请求后，相关审批者组的成员将收到电子邮件通知，并可以批准与请求 ID 关联的请求。 通过电子邮件向请求者通知请求审批或拒绝。

#### <a name="in-the-microsoft-365-admin-center"></a>在 Microsoft 365 管理中心

1. 使用凭据登录 [Microsoft 365](https://admin.microsoft.com) 管理中心。

2. 在管理中心，转到"**设置**  >  **组织** 设置  >  **安全设置&权限**  >  **"。**

3. 选择 **"管理访问策略和请求"。**

4. 选择列出的请求以查看详细信息，并针对请求采取措施。

5. 选择 **"** 批准"以批准请求， **或选择** "拒绝拒绝"请求。 以前批准的请求可以通过选择"撤销"来 **撤销访问权限**。

#### <a name="in-exchange-management-powershell"></a>在 Exchange 管理 PowerShell 中

若要批准提升授权请求，请运行 Exchange Online PowerShell 中的以下命令：

```PowerShell
Approve-ElevatedAccessRequest -RequestId <request id> -Comment '<approval comment>'
```

示例：

```PowerShell
Approve-ElevatedAccessRequest -RequestId a4bc1bdf-00a1-42b4-be65-b6c63d6be279 -Comment '<approval comment>'
```

若要拒绝提升授权请求，请运行 Exchange Online PowerShell 中的以下命令：

```PowerShell
Deny-ElevatedAccessRequest -RequestId <request id> -Comment '<denial comment>'
```

示例：

```PowerShell
Deny-ElevatedAccessRequest -RequestId a4bc1bdf-00a1-42b4-be65-b6c63d6be279 -Comment '<denial comment>'
```

## <a name="delete-a-privileged-access-policy-in-office-365"></a>删除 Office 365 中的特权访问策略

如果组织中不再需要它，可以删除特权访问策略。

### <a name="in-the-microsoft-365-admin-center"></a>在 Microsoft 365 管理中心

1. 使用组织中管理员帐户的凭据登录 [Microsoft 365](https://admin.microsoft.com) 管理中心。

2. 在管理中心，转到"**设置**  >  **组织** 设置  >  **安全设置&权限**  >  **"。**

3. 选择 **"管理访问策略和请求"。**

4. 选择 **"配置策略"。**

5. 选择要删除的策略，然后选择"删除 **策略"。**

6. 选择“**关闭**”。

### <a name="in-exchange-management-powershell"></a>在 Exchange 管理 PowerShell 中

若要删除特权访问策略，请运行 Exchange Online Powershell 中的以下命令：

```PowerShell
Remove-ElevatedAccessApprovalPolicy -Identity <identity GUID of the policy you want to delete>
```

## <a name="disable-privileged-access-in-office-365"></a>在 Office 365 中禁用特权访问

如果需要，您可以为组织禁用特权访问管理。 禁用特权访问不会删除任何关联的审批策略或审批者组。

### <a name="in-the-microsoft-365-admin-center"></a>在 Microsoft 365 管理中心

1. 使用组织中管理员帐户的凭据登录 [Microsoft 365](https://admin.microsoft.com) 管理中心。

2. 在管理中心中，**转到"设置**  >  **组织** 设置  >  **安全设置&权限**  >  **"。**

3. 启用 **特权访问控制的"需要审批** "。

### <a name="in-exchange-management-powershell"></a>在 Exchange 管理 PowerShell 中

若要禁用特权访问，请运行 Exchange Online Powershell 中的以下命令：

```PowerShell
Disable-ElevatedAccessControl
```
