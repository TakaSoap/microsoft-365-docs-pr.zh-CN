---
title: 适用于企业测试环境的 Microsoft 365 的特权访问管理
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
description: 使用此测试实验室指南可为 Microsoft 365 企业版测试环境启用特权访问管理。
ms.openlocfilehash: 24ca7a6408a4290c54dd2bcd7c3f6061eb8f6c05
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487584"
---
# <a name="privileged-access-management-for-your-microsoft-365-for-enterprise-test-environment"></a>适用于企业测试环境的 Microsoft 365 的特权访问管理

*此测试实验室指南可用于适用于企业和 Office 365 企业测试环境的 Microsoft 365。*

本文介绍如何配置特权访问管理以提高 Microsoft 365 企业版测试环境中的安全性。

配置 priviledged 访问管理涉及三个阶段：
- [第1阶段：构建您的 Microsoft 365 企业版测试环境](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [阶段2：配置特权访问管理](#phase-2-configure-privileged-access-management)
- [第3阶段：验证提升权限和特权任务是否都需要审批](#phase-3-verify-that-approval-is-required-for-elevated-and-privileged-tasks)

![Microsoft 云测试实验室指南](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> 若要了解到 Microsoft 365 for 企业测试实验室指南堆栈中的所有文章的可视化地图，请转到 [microsoft 365 for Enterprise Test Lab Guide stack](../downloads/Microsoft365EnterpriseTLGStack.pdf)。
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>第1阶段：构建您的 Microsoft 365 企业版测试环境

如果要使用最低要求以轻型方式配置特权访问管理，请按照 [轻型基本配置](lightweight-base-configuration-microsoft-365-enterprise.md)中的说明进行操作。
  
如果要在模拟的企业中配置特权访问管理，请按照 [传递身份验证](pass-through-auth-m365-ent-test-environment.md)中的说明进行操作。
  
>[!NOTE]
>测试特权访问管理不需要模拟企业测试环境，其中包括连接到 internet 的模拟 intranet 和 Active Directory 域服务林的目录同步。 它作为选项提供，以便您可以测试特权访问管理，并在代表典型组织的环境中进行试验。

## <a name="phase-2-configure-privileged-access-management"></a>阶段2：配置特权访问管理

在这一阶段，为 Microsoft 365 配置 "审批者" 组并启用适用于企业测试环境的 "特权访问管理"。 有关其他详细信息和权限访问管理的概述，请参阅 [特权访问管理](../compliance/privileged-access-management-overview.md)。

若要设置和使用组织中的特权访问，请执行以下步骤。

#### <a name="step-1-create-an-approvers-group"></a>[步骤1：创建审批者的组](../compliance/privileged-access-management-configuration.md#step-1-create-an-approvers-group)

在开始使用特权访问之前，请确定谁将拥有对已提升和特权任务的传入请求的审批权限。 作为审批者组一部分的所有用户都可以批准访问请求。 若要使用特权访问，必须在 Microsoft 365 中创建启用邮件的安全组。 在您的测试环境中，将新安全组命名为 "特权访问审批者"，并添加先前在之前的测试实验室指南中的步骤中创建的 "用户 3"。

#### <a name="step-2-enable-privileged-access"></a>[步骤2：启用特权访问](../compliance/privileged-access-management-configuration.md#step-2-enable-privileged-access)

需要在 Microsoft 365 中显式打开具有默认审批者组的特权访问权限，并且必须包含要从特权访问管理访问控制中排除的一组系统帐户。 在开始本指南的第3阶段之前，请务必在你的组织中启用访问权限。

## <a name="phase-3-verify-that-approval-is-required-for-elevated-and-privileged-tasks"></a>第3阶段：验证提升权限和特权任务是否都需要审批

在此阶段中，验证特权访问策略是否正常运行，以及用户是否需要批准以执行定义的提升和特权任务。

### <a name="test-the-ability-to-execute-a-task-not-defined-in-a-privileged-access-policy"></a>测试执行未在特权访问策略中定义的任务的能力

首先，使用在测试环境中配置为全局管理员的用户的凭据连接到 Exchange 管理 PowerShell，并尝试创建新的日记规则。 尚未在组织的特权访问策略中定义 [新的-new-journalrule](https://docs.microsoft.com/powershell/module/exchange/new-journalrule) 任务。

1. 在您的本地计算机上， **Microsoft Corporation**  >  使用您的测试环境的全局管理员帐户在 microsoft Corporation**microsoft Exchange online 远程 powershell 模块**中打开并登录到 Exchange online 远程 powershell 模块。

1. 在 Exchange 管理 PowerShell 中，为您的组织创建新的日记规则：

   ```ExchangeManagementPowerShell
   New-JournalRule -Name "JournalRule1" -Recipient joe@contoso.onmicrosoft.com -JournalEmailAddress barbara@adatum.com -Scope Global -Enabled $true
   ```

1. 查看在 Exchange 管理 PowerShell 中已成功创建新日记规则。

### <a name="create-a-new-privileged-access-policy-for-the-new-journalrule-task"></a>为 New-JournalRule 任务创建新的特权访问策略

>[!NOTE]
>如果您尚未从本指南的第2阶段完成步骤1和步骤2，请务必按照创建名为 "权限访问审批者" 的审批者组中的步骤，在测试环境中启用权限访问。

1. 使用凭据登录到 [Microsoft 365 管理中心](https://admin.microsoft.com) 您的测试环境的全局管理员帐户。

2. 在管理中心中，转到 "**设置**  >  **安全 & 隐私**"  >  **特权访问权限**。

3. 选择 " **管理访问策略和请求**"。

4. 选择 " **配置策略**"，然后选择 " **添加策略**"。

5. 从下拉字段中，选择或输入以下值：

    **策略类型**：任务

    **策略作用域**： Exchange

    **策略名称**：新日记规则

    **审批类型**：手动

    **审批组**：特权访问审批者

6. 选择 " **创建**"，然后选择 " **关闭**"。 为策略完全配置和启用可能需要几分钟时间。 在测试下一步中的审批要求之前，请务必为策略完全启用时间。

### <a name="test-approval-requirement-for-the-new-journalrule-task-defined-in-a-privileged-access-policy"></a>在特权访问策略中定义的 New-JournalRule 任务的测试批准要求

1. 在您的本地计算机上，在**microsoft Corporation**  >  **microsoft Exchange online powershell 模块**中打开并登录到 exchange online 远程 powershell 模块，使用您的测试环境的全局管理员帐户。

2. 在 Exchange 管理 PowerShell 中，为您的组织创建新的日记规则：

   ```ExchangeManagementPowerShell
   New-JournalRule -Name "JournalRule2" -Recipient user1@<your subscription domain> -JournalEmailAddress user1@<your subscription domain> -Scope Global -Enabled $true
   ```

3. 在 Exchange 管理 PowerShell 中查看 "权限不足" 错误：

   ```ExchangeManagementPowerShell
   Insufficient permissions. Please raise an elevated access request for this task.
       + CategoryInfo          : NotSpecified: (:) [], LocalizedException
       + FullyQualifiedErrorId : [Server=CY1PR00MB0220,RequestId=7b8c7470-ddd0-4528-a01e-5e20ecc9bd54,TimeStamp=9/19/2018
       7:38:34 PM] [FailureCategory=Cmdlet-LocalizedException] 882BD051
       + PSComputerName        : outlook.office365.com
   ```

### <a name="request-access-to-create-a-new-journal-rule-using-the-new-journalrule-task"></a>请求访问权限以使用 New-JournalRule 任务创建新的日记规则

1. 使用您的测试环境的全局管理员帐户登录到 [Microsoft 365 管理中心](https://admin.microsoft.com) 。

2. 在管理中心中，转到 "**设置**  >  **安全 & 隐私**"  >  **特权访问权限**。

3. 选择 " **管理访问策略和请求**"。

4. 选择 " **新建请求**"。 从下拉字段中，为您的组织选择适当的值：

    **请求类型**：任务

    **请求范围**： Exchange

    **请求**：新日记规则

    **持续时间 (小时) **：2

    **注释**：请求创建新日记规则的权限

5. 选择 " **保存**"，然后选择 " **关闭**"。 您的请求将通过电子邮件发送给审批者的组。

### <a name="approve-privileged-access-request-for-the-creation-of-a-new-journal-rule"></a>批准创建新日记规则的特权访问请求

1. 使用测试环境中用户3的凭据登录到 [Microsoft 365 管理中心](https://admin.microsoft.com) ， (测试环境中 "特权访问审批者" 安全组的成员) 。

2. 在管理中心中，转到 "**设置**  >  **安全 & 隐私**"  >  **特权访问权限**。

3. 选择 " **管理访问策略和请求**"。

4. 选择 "挂起的请求"，然后选择 " **批准** " 以授予对全局管理员帐户的访问权限，以创建新的日记规则。  (请求用户) 的全局管理员帐户将收到已授予审批的电子邮件确认。

### <a name="test-creating-a-new-journal-rule-with-privileged-access-approved-for-the-new-journalrule-task"></a>测试创建新的日记规则，并为 New-JournalRule 任务批准权限访问

1. 在您的本地计算机上， **Microsoft Corporation**  >  使用您的测试环境的全局管理员帐户在 microsoft Corporation**microsoft Exchange online 远程 powershell 模块**中打开并登录到 Exchange online 远程 powershell 模块。

1. 在 Exchange 管理 PowerShell 中，为您的组织创建新的日记规则：

   ```ExchangeManagementPowerShell
   New-JournalRule -Name "JournalRule2" -Recipient user1@<your subscription domain> -JournalEmailAddress user1@<your subscription domain> -Scope Global -Enabled $true
   ```

1. 查看在 Exchange 管理 PowerShell 中已成功创建新日记规则。

## <a name="next-step"></a>后续步骤

在您的测试环境中浏览其他 [信息保护](m365-enterprise-test-lab-guides.md#information-protection) 特性和功能。

## <a name="see-also"></a>另请参阅

[Microsoft 365 企业版测试实验室指南](m365-enterprise-test-lab-guides.md)

[Microsoft 365 企业版概述](microsoft-365-overview.md)

[适用于企业的 Microsoft 365 文档](https://docs.microsoft.com/microsoft-365-enterprise/)
