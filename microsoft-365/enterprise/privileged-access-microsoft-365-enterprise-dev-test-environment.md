---
title: 用于 Microsoft 365 企业版测试环境的 Privileged Access Management
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
description: 使用此测试实验室指南可启用 Microsoft 365 企业版测试环境的特权访问管理。
ms.openlocfilehash: 1a81c62124177a328209f175262ac13455ca0899
ms.sourcegitcommit: 40ec697e27b6c9a78f2b679c6f5a8875dacde943
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/23/2020
ms.locfileid: "44352518"
---
# <a name="privileged-access-management-for-your-microsoft-365-enterprise-test-environment"></a>用于 Microsoft 365 企业版测试环境的 Privileged Access Management

*此测试实验室指南可用于 Microsoft 365 企业版和 Office 365 企业版测试环境。*

使用本文中的说明，可以配置特权访问管理以提高 Microsoft 365 企业版测试环境中的安全性。

![Microsoft 云测试实验室指南](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

>[!TIP]
>单击[此处](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf)可查看 Microsoft 365 企业版测试实验室指南集合中所有文章的直观图。
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>阶段 1：构建 Microsoft 365 企业版测试环境。

如果只想使用最低要求以轻型方式配置特权访问管理，请按照[轻型基本配置](lightweight-base-configuration-microsoft-365-enterprise.md)中的说明进行操作。
  
如果要在模拟的企业中配置特权访问管理，请按照[传递身份验证](pass-through-auth-m365-ent-test-environment.md)中的说明进行操作。
  
>[!NOTE]
>测试特权访问管理不需要模拟企业测试环境，其中包括连接到 Internet 的模拟 intranet 和 AD DS 林的目录同步。 此处提供它作为选项，以便您可以测试特权访问管理并在代表典型组织的环境中进行试验。 

## <a name="phase-2-configure-privileged-access-management"></a>阶段2：配置特权访问管理

在此阶段中，您将为 Microsoft 365 企业版测试环境配置 "审批者" 组并启用 "特权访问管理"。 有关其他详细信息和权限访问管理的概述，请参阅[Office 365 中的 "特权访问管理](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview)"。

按照以下步骤设置和使用组织中的特权访问：

- [步骤1：创建审批者的组](https://docs.microsoft.com/microsoft-365/compliance/privileged-access-management-configuration#step-1-create-an-approvers-group)

    在开始使用权限访问之前，请确定谁将拥有对已提升和特权任务的传入请求的审批权限。 作为审批者组的一部分的任何用户都将能够批准访问请求。 这是通过在 Office 365 中创建启用邮件的安全组来启用的。 在测试环境中创建一个名为 "特权访问审批者" 的新安全组，并添加先前在之前的测试实验室指南步骤中创建的 "用户 3"。

- [步骤2：启用特权访问](https://docs.microsoft.com/microsoft-365/compliance/privileged-access-management-configuration#step-2-enable-privileged-access)

    需要在 Office 365 中显式打开具有默认审批者组的特权访问权限，并包含要从特权访问管理访问控制中排除的一组系统帐户。 在开始本指南的第3阶段之前，请务必在你的组织中启用访问权限。

## <a name="phase-3-verify-that-approval-is-required-for-elevated-and-privileged-tasks"></a>第3阶段：验证提升权限和特权任务是否都需要审批

在此阶段中，您将验证特权访问策略是否正常工作，以及用户是否需要批准以执行定义的提升和特权任务。

### <a name="test-ability-to-execute-a-task-not-defined-in-a-privileged-access-policy"></a>测试执行未在特权访问策略中定义的任务的能力

首先，使用在测试环境中配置为全局管理员的用户的凭据连接到 Exchange 管理 PowerShell，并尝试创建新的日记规则。 尚未在组织的特权访问策略中定义[新的-new-journalrule](https://docs.microsoft.com/powershell/module/exchange/new-journalrule?view=exchange-ps)任务。

1. 在本地计算机上， **Microsoft Corporation**  >  使用您的测试环境的全局管理员帐户在 microsoft Corporation**microsoft Exchange online 远程 powershell 模块**中打开并登录到 Exchange online 远程 powershell 模块。

2. 在 Exchange 管理 PowerShell 中，为您的组织创建新的日记规则：

```ExchangeManagementPowerShell
New-JournalRule -Name "JournalRule1" -Recipient joe@contoso.onmicrosoft.com -JournalEmailAddress barbara@adatum.com -Scope Global -Enabled $true
```

4. 查看在 Exchange 管理 PowerShell 中已成功创建新日记规则。

### <a name="create-a-new-privileged-access-policy-for-the-new-journalrule-task"></a>为新的-New-journalrule 任务创建新的特权访问策略

>[!NOTE]
>如果您尚未从本指南的第2阶段完成步骤1和步骤2，请确保按照步骤创建名为 "权限访问审批者" 的审批者组，并在您的测试环境中启用特权访问。

1. 使用凭据登录到[Microsoft 365 管理中心](https://admin.microsoft.com)您的测试环境的全局管理员帐户。

2. 在管理中心中，转到 "**设置**  >  **安全 & 隐私**"  >  **特权访问权限**。

3. 选择 "**管理访问策略和请求**"。

4. 选择 "**配置策略**"，然后选择 "**添加策略**"。

5. 从下拉字段中，选择或输入以下值：

    **策略类型**：任务

    **策略作用域**： Exchange

    **策略名称**：新日记规则

    **审批类型**：手动

    **审批组**：特权访问审批者

6. 选择 "**创建**"，然后单击 "**关闭**"。 为策略完全配置和启用可能需要几分钟时间。 在测试下一步中的审批要求之前，请务必为策略完全启用时间。

### <a name="test-approval-requirement-for-the-new-journalrule-task-defined-in-a-privileged-access-policy"></a>在特权访问策略中定义的 New-journalrule 任务的测试批准要求

1. 在您的本地计算机上，使用您的测试环境的全局管理员帐户在**microsoft Corporation**  >  **microsoft Exchange online 远程 powershell 模块**中打开并登录到 Exchange online 远程 powershell 模块。

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

### <a name="request-access-to-create-a-new-journal-rule-using-the-new-journalrule-task"></a>请求访问权限以使用 New-journalrule 任务创建新的日记规则

1. 使用您的测试环境的全局管理员帐户登录[Microsoft 365 管理中心](https://admin.microsoft.com)。

2. 在管理中心中，转到 "**设置**  >  **安全 & 隐私**"  >  **特权访问权限**。

3. 选择 "**管理访问策略和请求**"。

4. 选择 "**新建请求**"。 从下拉字段中，为您的组织选择适当的值：

    **请求类型**：任务

    **请求范围**： Exchange

    **请求**：新日记规则

    **持续时间（小时）**：2

    **注释**：请求创建新日记规则的权限

5. 依次选择 "**保存**" 和 "**关闭**"。 您的请求将通过电子邮件发送给审批者的组。

### <a name="approve-privileged-access-request-for-the-creation-of-a-new-journal-rule"></a>批准创建新日记规则的特权访问请求

1. 使用测试环境中用户3的凭据登录到[Microsoft 365 管理中心](https://admin.microsoft.com)（测试环境中的 "特权访问审批者" 安全组的成员）。

2. 在管理中心中，转到 "**设置**  >  **安全 & 隐私**"  >  **特权访问权限**。

3. 选择 "**管理访问策略和请求**"。

4. 选择 "挂起的请求"，然后选择 "**批准**" 以授予对全局管理员帐户的访问权限，以创建新的日记规则。 将向全局管理员帐户（发出请求的用户）发送确认已授予审批的通知电子邮件。  

### <a name="test-creating-a-new-journal-rule-with-privileged-access-approved-for-the-new-journalrule-task"></a>测试创建新的日记规则，该规则具有针对 New-journalrule 任务审批的特权访问权限

1. 在本地计算机上， **Microsoft Corporation**  >  使用您的测试环境的全局管理员帐户在 microsoft Corporation**microsoft Exchange online 远程 powershell 模块**中打开并登录到 Exchange online 远程 powershell 模块。

2. 在 Exchange 管理 PowerShell 中，为您的组织创建新的日记规则：

```ExchangeManagementPowerShell
New-JournalRule -Name "JournalRule2" -Recipient user1@<your subscription domain> -JournalEmailAddress user1@<your subscription domain> -Scope Global -Enabled $true
```

3. 查看在 Exchange 管理 PowerShell 中已成功创建新日记规则。

## <a name="next-step"></a>后续步骤

在您的测试环境中浏览其他[信息保护](m365-enterprise-test-lab-guides.md#information-protection)特性和功能。

## <a name="see-also"></a>另请参阅

[Microsoft 365 企业版测试实验室指南](m365-enterprise-test-lab-guides.md)

[部署 Microsoft 365 企业版](deploy-microsoft-365-enterprise.md)

[Microsoft 365 企业版文档](https://docs.microsoft.com/microsoft-365-enterprise/)
