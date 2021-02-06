---
title: Microsoft 365 企业版测试环境的特权访问管理
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- M365-security-compliance
ms.custom: Ent_TLGs
description: 使用此测试实验室指南启用 Microsoft 365 企业版测试环境的特权访问管理。
ms.openlocfilehash: e9684ebd2aa147049dadfbda9408257ff801aff0
ms.sourcegitcommit: eac5d9f759f290d3c51cafaf335a1a1c43ded927
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2021
ms.locfileid: "50126413"
---
# <a name="privileged-access-management-for-your-microsoft-365-for-enterprise-test-environment"></a>Microsoft 365 企业版测试环境的特权访问管理

*本测试实验室指南可用于 Microsoft 365 企业版和 Office 365 企业版测试环境。*

本文介绍如何配置特权访问管理以提高 Microsoft 365 企业版测试环境的安全性。

配置伪造访问管理包括三个阶段：
- [第 1 阶段：构建 Microsoft 365 企业版测试环境](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [阶段 2：配置特权访问管理](#phase-2-configure-privileged-access-management)
- [阶段 3：验证提升和特权任务需要审批](#phase-3-verify-that-approval-is-required-for-elevated-and-privileged-tasks)

![Microsoft 云测试实验室指南](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> 有关 Microsoft 365 企业版测试实验室指南堆栈中所有文章的直观地图，请转到 [Microsoft 365 企业版测试实验室指南堆栈](../downloads/Microsoft365EnterpriseTLGStack.pdf)。
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>第 1 阶段：构建 Microsoft 365 企业版测试环境

如果要使用最低要求的轻型方式配置特权访问管理，请按照轻型基本 [配置中的说明操作](lightweight-base-configuration-microsoft-365-enterprise.md)。
  
如果要在模拟的企业中配置特权访问管理，请按照传递身份验证 [中的说明操作](pass-through-auth-m365-ent-test-environment.md)。
  
>[!NOTE]
>测试特权访问管理不需要模拟的企业测试环境，其中包括连接到 Internet 的模拟 Intranet 和 Active Directory 域服务林的目录同步。 它在此处作为一个选项提供，以便你可以测试特权访问管理，并尝试在代表典型组织的环境中进行此管理。

## <a name="phase-2-configure-privileged-access-management"></a>阶段 2：配置特权访问管理

在此阶段，配置审批者组，并启用 Microsoft 365 企业版测试环境的特权访问管理。 有关其他详细信息和特权访问管理的概述，请参阅 [Privileged 访问管理](../compliance/privileged-access-management-overview.md)。

若要在组织中设置和使用特权访问，请执行以下步骤。

#### <a name="step-1-create-an-approvers-group"></a>[步骤 1：创建审批者组](../compliance/privileged-access-management-configuration.md#step-1-create-an-approvers-group)

开始使用特权访问之前，请确定谁将拥有对访问提升和特权任务的传入请求的审批权限。 属于审批者组的所有用户都可以批准访问请求。 若要使用特权访问，必须在 Microsoft 365 中创建启用邮件的安全组。 在测试环境中，将新安全组命名为"Privileged Access Approvers"，并添加之前测试实验室指南步骤中创建的"User 3"。

#### <a name="step-2-enable-privileged-access"></a>[步骤 2：启用特权访问](../compliance/privileged-access-management-configuration.md#step-2-enable-privileged-access)

特权访问需要在具有默认审批者组的 Microsoft 365 中显式启用，并且它必须包含一组您希望从特权访问管理访问控制中排除的系统帐户。 在启动本指南的第 3 阶段之前，请确保在组织中启用特权访问。

## <a name="phase-3-verify-that-approval-is-required-for-elevated-and-privileged-tasks"></a>阶段 3：验证提升和特权任务需要审批

在此阶段，验证特权访问策略是否正常工作，以及用户是否需要批准，以执行已定义的提升和特权任务。

### <a name="test-the-ability-to-execute-a-task-not-defined-in-a-privileged-access-policy"></a>测试执行特权访问策略中未定义的任务的能力

首先，使用在测试环境中配置为全局管理员的用户的凭据连接到 Exchange 管理 PowerShell，并尝试创建新的日记规则。 [New-JournalRule](/powershell/module/exchange/new-journalrule)任务当前未在组织的特权访问策略中定义。

1. 在本地计算机上，使用测试环境的全局管理员帐户打开并登录到 **Microsoft Corporation** Microsoft Exchange Online 远程 PowerShell 模块的 Exchange Online 远程  >  **PowerShell** 模块。

1. 在 Exchange 管理 PowerShell 中，为组织创建新的日记规则：

   ```ExchangeManagementPowerShell
   New-JournalRule -Name "JournalRule1" -Recipient joe@contoso.onmicrosoft.com -JournalEmailAddress barbara@adatum.com -Scope Global -Enabled $true
   ```

1. 查看新日记规则已成功在 Exchange 管理 PowerShell 中创建。

### <a name="create-a-new-privileged-access-policy-for-the-new-journalrule-task"></a>为任务创建新的特权访问New-JournalRule策略

>[!NOTE]
>如果尚未完成本指南第 2 阶段中的步骤 1 和步骤 2，请确保按照步骤创建名为"Privilege Access Approvers"的审批者组，以在测试环境中启用特权访问。

1. 使用适用于测试环境的全局管理员帐户的凭据登录 [Microsoft 365](https://admin.microsoft.com) 管理中心。

2. 在管理中心中，**转到"设置**  >  **安全设置&**  >  **特权访问"。**

3. 选择 **"管理访问策略和请求"。**

4. 选择 **"配置策略**"，然后选择"**添加策略"。**

5. 从下拉列表字段中，选择或输入以下值：

    **策略类型**：任务

    **策略作用域**：Exchange

    **策略名称**：新建日记规则

    **审批类型**：手动

    **审批组**：特权访问审批者

6. 选择 **"** 创建"，然后选择"**关闭"。** 可能需要几分钟时间才能完全配置和启用策略。 在测试下一步中的审批要求之前，请确保留出时间使策略完全启用。

### <a name="test-approval-requirement-for-the-new-journalrule-task-defined-in-a-privileged-access-policy"></a>特权访问策略中定义的New-JournalRule任务的测试审批要求

1. 在本地计算机上，使用测试环境的全局管理员帐户打开并登录到 **Microsoft Corporation** Microsoft Exchange Online 远程 PowerShell 模块的 Exchange Online 远程  >  **PowerShell** 模块。

2. 在 Exchange 管理 PowerShell 中，为组织创建新的日记规则：

   ```ExchangeManagementPowerShell
   New-JournalRule -Name "JournalRule2" -Recipient user1@<your subscription domain> -JournalEmailAddress user1@<your subscription domain> -Scope Global -Enabled $true
   ```

3. 在 Exchange 管理 PowerShell 中查看"权限不足"错误：

   ```ExchangeManagementPowerShell
   Insufficient permissions. Please raise an elevated access request for this task.
       + CategoryInfo          : NotSpecified: (:) [], LocalizedException
       + FullyQualifiedErrorId : [Server=CY1PR00MB0220,RequestId=7b8c7470-ddd0-4528-a01e-5e20ecc9bd54,TimeStamp=9/19/2018
       7:38:34 PM] [FailureCategory=Cmdlet-LocalizedException] 882BD051
       + PSComputerName        : outlook.office365.com
   ```

### <a name="request-access-to-create-a-new-journal-rule-using-the-new-journalrule-task"></a>请求访问权限以使用"日记"任务New-JournalRule日记规则

1. 使用测试环境的全局管理员帐户登录到 [Microsoft 365](https://admin.microsoft.com) 管理中心。

2. 在管理中心中，**转到"设置**  >  **安全设置&**  >  **特权访问"。**

3. 选择 **"管理访问策略和请求"。**

4. 选择 **"新建请求"。** 从下拉列表中，为组织选择适当的值：

    **请求类型**： 任务

    **请求范围**： Exchange

    **请求：** 新建日记规则

    **持续时间 (小时) ：** 2

    **注释**：请求创建新日记规则的权限

5. 选择 **"** 保存"，然后选择"**关闭"。** 您的请求将通过电子邮件发送到审批者组。

### <a name="approve-privileged-access-request-for-the-creation-of-a-new-journal-rule"></a>批准新建日记规则的特权访问请求

1. 使用测试环境中用户 3 的凭据登录 [Microsoft 365](https://admin.microsoft.com) 管理中心 (测试环境中"Privileged Access Approvers"安全组的成员) 。

2. 在管理中心中，**转到"设置**  >  **安全设置&**  >  **特权访问"。**

3. 选择 **"管理访问策略和请求"。**

4. 选择挂起的请求，然后选择"批准"以授予对全局管理员帐户的访问权限以创建新的日记规则。 请求用户 (全局管理员帐户) 将收到一封电子邮件确认，确认已授予批准。

### <a name="test-creating-a-new-journal-rule-with-privileged-access-approved-for-the-new-journalrule-task"></a>测试创建一个新的日记规则，该规则具有批准用于该任务New-JournalRule权限

1. 在本地计算机上，使用测试环境的全局管理员帐户打开并登录到 **Microsoft Corporation** Microsoft Exchange Online 远程 PowerShell 模块的 Exchange Online 远程  >  **PowerShell** 模块。

1. 在 Exchange 管理 PowerShell 中，为组织创建新的日记规则：

   ```ExchangeManagementPowerShell
   New-JournalRule -Name "JournalRule2" -Recipient user1@<your subscription domain> -JournalEmailAddress user1@<your subscription domain> -Scope Global -Enabled $true
   ```

1. 查看新日记规则已成功在 Exchange 管理 PowerShell 中创建。

## <a name="next-step"></a>后续步骤

探索 [测试环境中](m365-enterprise-test-lab-guides.md#information-protection) 的其他信息保护特性和功能。

## <a name="see-also"></a>另请参阅

[Microsoft 365 企业版测试实验室指南](m365-enterprise-test-lab-guides.md)

[Microsoft 365 企业版概述](microsoft-365-overview.md)

[适用于企业的 Microsoft 365 文档](/microsoft-365-enterprise/)
