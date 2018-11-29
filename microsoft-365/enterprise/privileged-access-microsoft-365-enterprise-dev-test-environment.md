---
title: 用于 Microsoft 365 企业版测试环境的 Privileged Access Management
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: 09/21/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
ms.custom: Ent_TLGs
description: 使用此测试实验室指南启用特权的访问管理 Microsoft 365 企业版测试环境。
ms.openlocfilehash: 5f1a416a12171504af110ec62b9a7882143263e6
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2018
ms.locfileid: "26865407"
---
# <a name="privileged-access-management-for-your-microsoft-365-enterprise-test-environment"></a>用于 Microsoft 365 企业版测试环境的 Privileged Access Management

本文中的说明，您配置访问权限的管理，以提高 Microsoft 365 企业版测试环境中的安全性。

![Microsoft 云测试实验室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> 单击[此处](https://aka.ms/m365etlgstack)可查看 Microsoft 365 企业版测试实验室指南集合中所有文章的直观图。
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>第 1 阶段： 构建 Microsoft 365 企业版测试环境

如果您只想要配置的最低硬件要求与轻型方式访问权限的管理，按照[轻型基本配置](lightweight-base-configuration-microsoft-365-enterprise.md)中的说明。
  
如果您想要配置模拟企业中的访问权限的管理，请按照[传递身份验证](pass-through-auth-m365-ent-test-environment.md)中的说明。
  
> [!NOTE]
> 测试访问权限的管理不需要模拟的企业测试环境，其中包括连接到 Internet 模拟的 intranet 和 Windows Server AD 林目录同步。此处提供了作为一个选项，以便可以测试特权访问管理和代表典型组织的环境中试验它。 

## <a name="phase-2-configure-privileged-access-management"></a>第 2 阶段： 配置访问权限的管理

在此阶段中，可以配置审批者组和 Microsoft 365 企业版测试环境中启用访问权限的管理。有关其他详细信息和概述特权访问管理，请参阅[Office 365 中的访问权限的管理](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview)。

请按照下列步骤设置和使用 Office 365 组织中的访问权限：

- [步骤 1： 创建审批者组](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration#step-1---create-an-approvers-group)

    在开始使用最小特权 access 之前，决定谁将具有审批授权的传入请求访问提升特权的任务。审批者的组的一部分的任何用户都将能够批准访问请求。这被启用的 Office 365 中创建启用邮件的安全组。创建新的安全组测试环境中名为"特权访问审批者"，并添加"User 3" 以前在早期测试实验室指南步骤中创建。

- [步骤 2： 启用访问权限](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration#step-2---enable-privileged-access)

    需要显式打开 Office 365 中使用的默认审批者组和包括要排除的访问权限的管理访问控制从系统帐户的一组访问权限。请务必启用您在开始本指南的第 3 阶段之前的 Office 365 组织中的授权访问权限。

## <a name="phase-3-verify-that-approval-is-required-for-elevated-and-privileged-tasks"></a>第 3 阶段： 验证进行审批的提升特权的任务
在此阶段中，您将验证使用特权的访问策略和用户需要审批执行定义的提升和特权任务。

### <a name="test-ability-to-execute-a-task-not-defined-in-a-privileged-access-policy"></a>测试能够执行未授权访问权限策略中定义的任务

首先，使用配置为您的测试环境中的全局管理员的用户的凭据连接到 Exchange Management PowerShell 并尝试创建新的日记规则。[New-journalrule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-journalrule?view=exchange-ps)任务当前不在您的组织的访问权限的策略中定义。

1. 在本地计算机上打开并登录到 Exchange Online 远程 PowerShell 模块， **Microsoft Corporation** > **Microsoft Exchange Online 远程 PowerShell 模块**使用全局管理员帐户的测试环境。

2. 在 Exchange Management Powershell 中，创建您的组织的新日记规则：

```
New-JournalRule -Name "JournalRule1" -Recipient joe@contoso.onmicrosoft.com -JournalEmailAddress barbara@adatum.com -Scope Global -Enabled $true
```
4. 在 Exchange Management PowerShell 创建的视图的新的日记规则已成功。

### <a name="create-a-new-privileged-access-policy-for-the-new-journalrule-task"></a>创建新的访问权限的策略 New-journalrule 任务

> [!NOTE]
> 如果您没有已完成步骤 1 和 2，自本指南的第 2 阶段，为确保遵循的步骤创建名为"最小特权访问审批者"审批者组以及启用测试环境中的授权访问权限。

1. 测试环境的全局管理员帐户登录到[Microsoft 365 Admin Center](https://portal.office.com)使用凭据。

2. 在管理中心，转到**设置** > **安全性和隐私** > **访问权限**。

3. 选择**管理访问策略和请求**。

4. 选择**配置策略**，然后选择**添加策略**。

5. 从下拉列表的字段中，选择或输入以下值：
    
    **策略类型**： 任务

    **策略作用域**： Exchange

    **策略名称**： 新日记规则

    **审批类型**： 手动

    **审核组**： 特权访问审批者

6. 选择**创建**，然后**关闭**。可能需要几分钟，要完全配置并启用的策略。请务必允许将策略应用之前在下一步中测试审批要求完全启用的时间。

### <a name="test-approval-requirement-for-the-new-journalrule-task-defined-in-a-privileged-access-policy"></a>测试 New-journalrule 任务的访问权限的策略中定义的审批要求

1. 在本地计算机上打开并登录到 Exchange Online 远程 PowerShell 模块， **Microsoft Corporation** > **Microsoft Exchange Online 远程 PowerShell 模块**使用使用全局管理员帐户为测试环境。

2. 在 Exchange Management Powershell 中，创建您的组织的新日记规则：

```
New-JournalRule -Name "JournalRule2" -Recipient user1@<your subscription domain> -JournalEmailAddress user1@<your subscription domain> -Scope Global -Enabled $true
```
3. 在 Exchange Management PowerShell 中查看"Insuffient 权限"错误：

```
Insufficient permissions. Please raise an elevated access request for this task.
    + CategoryInfo          : NotSpecified: (:) [], LocalizedException
    + FullyQualifiedErrorId : [Server=CY1PR00MB0220,RequestId=7b8c7470-ddd0-4528-a01e-5e20ecc9bd54,TimeStamp=9/19/2018
    7:38:34 PM] [FailureCategory=Cmdlet-LocalizedException] 882BD051
    + PSComputerName        : outlook.office365.com
```

### <a name="request-access-to-create-a-new-journal-rule-using-the-new-journalrule-task"></a>请求创建一个新的日记规则使用 New-journalrule 任务的访问

1. 登录到[Microsoft 365 Admin Center](https://portal.office.com)的测试环境中使用的全局管理员帐户。

2. 在管理中心，转到**设置** > **安全性和隐私** > **访问权限**。

3. 选择**管理访问策略和请求**。

4. 选择**新的请求**。从下拉列表字段中，选择您的组织的相应值：

    **请求类型**： 任务

    **请求作用域**： Exchange

    **请求**： 新日记规则

    **持续时间 （小时）**: 2

    **注释**： 请求权限以创建新的日记规则

5. 选择**保存**和**关闭**。您的请求将发送到通过电子邮件的审批者的组。

### <a name="approve-privileged-access-request-for-the-creation-of-a-new-journal-rule"></a>批准创建新的日记规则的访问权限的请求

1. 登录到[Microsoft 365 Admin Center](https://portal.office.com)用户 3 的测试环境 （在测试环境中的"特权访问审批者"安全组的成员） 中使用的凭据。

2. 在管理中心，转到**设置** > **安全性和隐私** > **访问权限**。

3. 选择**管理访问策略和请求**。

4. 选择待处理的请求并选择**批准**向要创建新的日记规则的全局管理员帐户授予访问权限。确认已授予审批通知电子邮件将发送到的全局管理员帐户 （发出请求的用户）。  

### <a name="test-creating-a-new-journal-rule-with-privileged-access-approved-for-the-new-journalrule-task"></a>测试与批准 New-journalrule 任务的访问权限创建一个新的日记规则

1. 在本地计算机上打开并登录到 Exchange Online 远程 PowerShell 模块， **Microsoft Corporation** > **Microsoft Exchange Online 远程 PowerShell 模块**使用全局管理员帐户的测试环境。

2. 在 Exchange Management Powershell 中，创建您的组织的新日记规则：

```
New-JournalRule -Name "JournalRule2" -Recipient user1@<your subscription domain> -JournalEmailAddress user1@<your subscription domain> -Scope Global -Enabled $true
```
3. 在 Exchange Management PowerShell 创建的视图的新的日记规则已成功。

## <a name="next-step"></a>后续步骤

浏览您的测试环境中其他[信息保护](m365-enterprise-test-lab-guides.md#information-protection)特性和功能。

## <a name="see-also"></a>另请参阅

[Microsoft 365 企业版测试实验室指南](m365-enterprise-test-lab-guides.md)

[部署 Microsoft 365 企业版](deploy-microsoft-365-enterprise.md)

[Microsoft 365 企业版文档](https://docs.microsoft.com/microsoft-365-enterprise/)