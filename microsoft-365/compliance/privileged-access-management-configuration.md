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
ms.localizationpriority: medium
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
- admindeeplinkMAC
ms.assetid: ''
description: 使用本文了解有关在 Office 365 中启用和配置特权访问管理Office 365。
ms.openlocfilehash: fd7216b09b17f7f900a9aee98059918a1796fe19
ms.sourcegitcommit: 7fd1bcbd8246501029837e3ea92adea64c3406e1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/01/2022
ms.locfileid: "62295346"
---
# <a name="get-started-with-privileged-access-management"></a>特权访问管理入门

本主题指导你完成在组织中启用和配置特权访问管理。 可以使用 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 管理中心 或 Exchange</a> PowerShell 管理和使用特权访问。

## <a name="before-you-begin"></a>开始之前

在开始使用特权访问管理之前，应该先确认你的Microsoft 365[订阅](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans)和任何加载项。 若要访问和使用特权访问管理，组织必须具有以下订阅或加载项之一：

- Microsoft 365 E5 订阅（付费或试用版本）
- Microsoft 365 E3 (或 Office 365 E3 订阅 + Enterprise 移动性和安全性 E3 订阅) + Microsoft 365 E5 合规 加载项
- 任何Microsoft 365、Office 365、Exchange、SharePoint 或 OneDrive for Business 订阅 + Microsoft 365 E5 Insider Risk Management 加载项
- Microsoft 365 A5 订阅（付费或试用版本）
- Microsoft 365 A3 (或 Office 365 A3 订阅 + Enterprise 移动性和安全性 A3 订阅) + Microsoft A5 合规性加载项
- 任何 Microsoft 365、Office 365、Exchange、SharePoint 或 OneDrive for Education 订阅 + Microsoft 365 A5 Insider Risk Management 加载项
- Office 365 企业版 E5 订阅（付费或试用版本）
- Office 365 企业版 E3 订阅 + Office 365 高级合规版加载项（新订阅已不再可用，请参阅注释）

必须为提交和响应特权访问管理请求的用户分配上述许可证之一。

> [!IMPORTANT]
> Office 365 高级合规版已不再作为独立订阅销售。 当前订阅到期后，客户应过渡到以上订阅之一，其中包含了相同的或其它合规性功能。

如果你没有现有的 Office 365 企业版 E5 计划，并且想要尝试特权访问管理，可以将 [Microsoft 365](/office365/admin/try-or-buy-microsoft-365) 添加到现有 Office 365 订阅或注册 Microsoft 365 企业版 E5 的试用版。[](https://www.microsoft.com/microsoft-365/enterprise)

## <a name="enable-and-configure-privileged-access-management"></a>启用和配置特权访问管理

请按照以下步骤在组织中设置和使用特权访问：

- [步骤 1：创建审批者组](privileged-access-management-configuration.md#step1)

    在开始使用特权访问之前，决定需要审批机构授予权限以完成提升和特权任务的人员。 审批者组的任何用户都有权批准访问请求。 此组通过在此邮箱中创建启用邮件的安全Office 365。

- [步骤 2：启用特权访问](privileged-access-management-configuration.md#step2)

    特权访问必须在 Office 365 中通过默认审批者组显式启用，包括想要排除在特权访问管理控制之外的系统账户集。

- [步骤 3：创建访问策略](privileged-access-management-configuration.md#step3)

    创建访问策略让你可以定义限定在个人任务范围的具体审批要求。 审批类型选项有 **自动** 或 **手动**。

- [步骤 4：提交/批准特权访问请求](privileged-access-management-configuration.md#step4)

    启用后，特权访问需要对所有定义了相关审批策略的任务进行审批。 对于包含在批准策略中的任务，用户必须请求并被授予访问许可来获取执行任务必要的权限。

在获得批准后，发出请求的用户可以执行目标任务，特权访问会授权并代表用户执行该任务。 批准有效期为请求时长（默认为 4 小时），在此期间，请求者可以多次执行目标任务。 所有这些执行操作会被记录，供安全和合规性审计所用。

> [!NOTE]
> 如果要使用 Exchange Management PowerShell 启用和配置特权访问，请按照 连接 中的步骤使用多重身份验证连接到 [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell#connect-to-exchange-online-powershell-using-mfa)，并使用 Office 365 凭据连接到 Exchange Online PowerShell。 在连接到 PowerShell 时，无需为组织启用多重身份验证Exchange Online特权访问。 通过多重身份验证连接将创建一个身份验证令牌，该令牌由特权访问用于对请求进行签名。

<a name="step1"> </a>

## <a name="step-1-create-an-approvers-group"></a>步骤 1：创建审批者组

1. 使用[Microsoft 365 管理中心管理员](https://admin.microsoft.com)帐户的凭据登录登录帐户。

2. 在管理中心中，转到" <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">**组**</a> > **""将组"作为"组"**。

3. 选择 **"启用邮件的安全组**"，然后填写新组的"名称"、组电子邮件地址和"说明"字段。

4. 保存组。 该组可能需要几分钟时间才能完全配置好并出现在 Microsoft 365 管理中心。

5. 选择新审批者组，然后选择" **编辑** "将用户添加到组。

6. 保存组。

<a name="step2"> </a>

## <a name="step-2-enable-privileged-access"></a>步骤 2：启用特权访问

### <a name="in-the-microsoft-365-admin-center"></a>在Microsoft 365 管理中心

1. 使用组织中[Microsoft 365 管理](https://admin.microsoft.com)帐户的凭据登录到管理中心。

2. In the admin center， go to **设置** > **Org 设置** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2072756" target="_blank">**Security &**</a> **PrivacyPrivileged** >  access.

3. 启用 **"需要批准特权任务"** 控件。

4. 将步骤 1 中创建的审批者组分配为 **"默认审批者"组**。

5. **保存** 并 **关闭**。

### <a name="in-exchange-management-powershell"></a>在 Exchange Management PowerShell 中

若要启用特权访问并分配审批者组，在 PowerShell 中运行Exchange Online命令：

```PowerShell
Enable-ElevatedAccessControl -AdminGroup '<default approver group>' -SystemAccounts @('<systemAccountUPN1>','<systemAccountUPN2>')
```

示例：

```PowerShell
Enable-ElevatedAccessControl -AdminGroup 'pamapprovers@fabrikam.onmicrosoft.com' -SystemAccounts @('sys1@fabrikamorg.onmicrosoft.com', 'sys2@fabrikamorg.onmicrosoft.com')
```

> [!NOTE]
> 系统帐户功能可用于确保组织内的某些自动化可以在不依赖特权访问的情况下工作，但建议此类排除项异常，并且应定期批准和审核允许的排除项。

<a name="step3"> </a>

## <a name="step-3-create-an-access-policy"></a>步骤 3：创建访问策略

你可以为组织创建和配置最多 30 个特权访问策略。

### <a name="in-the-microsoft-365-admin-center"></a>在Microsoft 365 管理中心

1. 使用组织中[Microsoft 365 管理](https://admin.microsoft.com)帐户的凭据登录到管理中心。

2. In the Admin Center， go to **设置** > **Org 设置** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2072756" target="_blank">**Security &**</a> **PrivacyPrivileged** >  access.

3. 选择 **"管理访问策略和请求"**。

4. 选择 **"配置策略** "，然后选择 **"添加策略"**。

5. 从下拉字段中，为组织选择适当的值：

    **策略类型**: 任务、角色或角色组

    **策略范围**: Exchange

    **策略名称**: 从可用策略中选择

    **审批类型**: 手动或自动

    **审批组**: 选择在步骤 1 中创建的审批者组

6. 选择 **"创建** "，然后选择" **关闭"**。 可能需要几分钟时间才能完全配置和启用策略。

### <a name="in-exchange-management-powershell"></a>在 Exchange Management PowerShell 中

若要创建和定义审批策略，在 PowerShell 中Exchange Online命令：

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

特权访问的请求在请求提交后的 24 小时内有效。 如果未批准或已拒绝，则请求将过期且不允许访问。

#### <a name="in-the-microsoft-365-admin-center"></a>在Microsoft 365 管理中心

1. 使用凭据[Microsoft 365 管理](https://admin.microsoft.com)登录中心。

2. In the Admin Center， go to **设置** > **Org 设置** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2072756" target="_blank">**Security &**</a> **PrivacyPrivileged** >  access.

3. 选择 **"管理访问策略和请求"**。

4. 选择 **"新建请求"**。 从下拉字段中，为组织选择适当的值：

    **请求类型**: 任务、角色或角色组

    **请求范围**: Exchange

    **请求**: 从可用策略中选择

    **持续时间 (小时)**: 请求访问的小时数。 可以请求的小时数没有限制。

    **注释**：与访问请求相关的注释的文本字段

5. 选择 **"保存"** ，然后选择" **关闭"**。 您的请求将通过电子邮件发送到审批者组。

#### <a name="in-exchange-management-powershell"></a>在 Exchange Management PowerShell 中

在 PowerShell Exchange Online运行以下命令，以创建审批请求并提交到审批者组：

```PowerShell
New-ElevatedAccessRequest -Task 'Exchange\<exchange management cmdlet name>' -Reason '<appropriate reason>' -DurationHours <duration in hours>
```

示例：

```PowerShell
New-ElevatedAccessRequest -Task 'Exchange\New-MoveRequest' -Reason 'Attempting to fix the user mailbox error' -DurationHours 4
```

### <a name="view-status-of-elevation-requests"></a>查看提升请求的状态

创建审批请求后，可以在管理中心或 Exchange管理 PowerShell 中查看提升请求状态（使用与请求 ID 关联的）。

#### <a name="in-the-microsoft-365-admin-center"></a>在 Microsoft 365 管理中心

1. Sign into the [Microsoft 365 管理中心](https://admin.microsoft.com) with your credentials.

2. In the admin center， go to **设置** > **Org 设置** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2072756" target="_blank">**Security &**</a> **PrivacyPrivileged** >  access.

3. 选择 **"管理访问策略和请求"**。

4. 选择 **"** 视图"按"挂起、已批准 **、已拒绝**"或"客户 **密码箱状态"筛选提交的请求**。

#### <a name="in-exchange-management-powershell"></a>在 Exchange Management PowerShell 中

在 PowerShell Exchange Online运行以下命令以查看特定请求 ID 的审批请求状态：

```PowerShell
Get-ElevatedAccessRequest -Identity <request ID> | select RequestStatus
```

示例：

```PowerShell
Get-ElevatedAccessRequest -Identity 28560ed0-419d-4cc3-8f5b-603911cbd450 | select RequestStatus
```

### <a name="approving-an-elevation-authorization-request"></a>批准提升授权请求

创建审批请求后，相关审批者组的成员将收到电子邮件通知，并可以批准与请求 ID 关联的请求。 请求者通过电子邮件收到请求批准或拒绝的通知。

#### <a name="in-the-microsoft-365-admin-center"></a>在 Microsoft 365 管理中心

1. Sign into the [Microsoft 365 管理中心](https://admin.microsoft.com) with your credentials.

2. In the admin center， go to **设置** > **Org 设置** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2072756" target="_blank">**Security &**</a> **PrivacyPrivileged** >  access.

3. 选择 **"管理访问策略和请求"**。

4. 选择列出的请求以查看详细信息，然后对请求采取措施。

5. 选择 **"** 批准"以批准请求，或选择" **拒绝** "以拒绝请求。 通过选择"撤销"，可以撤消以前批准的 **请求的访问权限**。

#### <a name="in-exchange-management-powershell"></a>在 Exchange Management PowerShell 中

若要批准提升授权请求，在 PowerShell 中Exchange Online命令：

```PowerShell
Approve-ElevatedAccessRequest -RequestId <request id> -Comment '<approval comment>'
```

示例：

```PowerShell
Approve-ElevatedAccessRequest -RequestId a4bc1bdf-00a1-42b4-be65-b6c63d6be279 -Comment '<approval comment>'
```

若要拒绝提升授权请求，请运行 PowerShell 中的以下Exchange Online命令：

```PowerShell
Deny-ElevatedAccessRequest -RequestId <request id> -Comment '<denial comment>'
```

示例：

```PowerShell
Deny-ElevatedAccessRequest -RequestId a4bc1bdf-00a1-42b4-be65-b6c63d6be279 -Comment '<denial comment>'
```

## <a name="delete-a-privileged-access-policy-in-office-365"></a>在策略中删除特权访问Office 365

如果组织中不再需要它，可以删除特权访问策略。

### <a name="in-the-microsoft-365-admin-center"></a>在 Microsoft 365 管理中心

1. 使用[Microsoft 365 管理中心管理员](https://admin.microsoft.com)帐户的凭据登录登录帐户。

2. In the admin center， go to **设置** > **Org 设置** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2072756" target="_blank">**Security &**</a> **PrivacyPrivileged** >  access.

3. 选择 **"管理访问策略和请求"**。

4. 选择 **"配置策略"**。

5. 选择要删除的策略，然后选择"删除 **策略"**。

6. 选择“**关闭**”。

### <a name="in-exchange-management-powershell"></a>在 Exchange Management PowerShell 中

若要删除特权访问策略，请运行 Powershell 中的以下Exchange Online命令：

```PowerShell
Remove-ElevatedAccessApprovalPolicy -Identity <identity GUID of the policy you want to delete>
```

## <a name="disable-privileged-access-in-office-365"></a>在管理中禁用特权Office 365

如果需要，你可以为组织禁用特权访问管理。 禁用特权访问不会删除任何关联的审批策略或审批者组。

### <a name="in-the-microsoft-365-admin-center"></a>在 Microsoft 365 管理中心

1. 使用[Microsoft 365 管理中心管理员](https://admin.microsoft.com)帐户的凭据登录登录帐户。

2. In the Admin Center， go to **设置** > **Org 设置** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2072756" target="_blank">**Security &**</a> **PrivacyPrivileged** >  access.

3. 启用 **"需要批准特权访问控制** "。

### <a name="in-exchange-management-powershell"></a>在 Exchange Management PowerShell 中

若要禁用特权访问，在 Powershell 中Exchange Online命令：

```PowerShell
Disable-ElevatedAccessControl
```
