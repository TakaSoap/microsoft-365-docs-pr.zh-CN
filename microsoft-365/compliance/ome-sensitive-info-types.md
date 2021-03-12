---
title: 使用 Office 365 邮件加密创建敏感信息类型策略
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 8/28/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- Strat_O365_Enterprise
description: 了解如何使用 Office 365 邮件加密为组织创建敏感信息类型策略。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 22aec87b149c58b2537f6921fb7c37552ef72f98
ms.sourcegitcommit: 06d9e056eabfbac8fafe66cc32907b33d4ae8253
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2021
ms.locfileid: "50741375"
---
# <a name="create-a-sensitive-information-type-policy-for-your-organization-using-message-encryption"></a>使用邮件加密为组织创建敏感信息类型策略

您可以使用 Exchange 邮件流规则或数据丢失防护 (DLP) Office 365 邮件加密创建敏感信息类型策略。 若要创建 Exchange 邮件流规则，可以使用 Exchange 管理中心或 (EAC) PowerShell。

## <a name="to-create-the-policy-by-using-mail-flow-rules-in-the-eac"></a>使用 EAC 中的邮件流规则创建策略

登录到 Exchange 管理中心 (EAC) ，**然后转到"** 邮件流""规则  >  **"。** 在"规则"页上，创建应用 Office 365 邮件加密的规则。 您可以基于某些条件（如邮件或附件中是否存在某些关键字或敏感信息类型）创建规则。

### <a name="to-create-the-policy-by-using-mail-flow-rules-in-powershell"></a>使用 PowerShell 中的邮件流规则创建策略

使用在组织中具有全局管理员权限的工作或学校帐户，启动Windows PowerShell会话并连接到 Exchange Online。 有关说明，请参阅[连接 PowerShell Exchange Online](https://aka.ms/exopowershell)。 使用 Set-IRMConfiguration 和 New-TransportRule cmdlet 创建策略。

## <a name="example-mail-flow-rule-created-with-powershell"></a>使用 PowerShell 创建的邮件流规则示例

在 PowerShell 中运行以下命令，创建 Exchange 邮件流规则，如果电子邮件或附件包含以下敏感信息类型，则使用仅加密选项自动加密发送到组织外部的电子邮件：

- ABA 路由号码
- 信用卡号
- 管制局 (DEA) 号码
- 美国/英国 passport number
- 美国银行帐号
- 美国单独的纳税人标识号 (ITIN)
- 美国社会保险号 (SSN)

```powershell
Set-IRMConfiguration -DecryptAttachmentForEncryptOnly $true
New-TransportRule -Name "Encrypt outbound sensitive emails (out of box rule)" -SentToScope  NotInOrganization  -ApplyRightsProtectionTemplate "Encrypt" -MessageContainsDataClassifications @(@{Name="ABA Routing Number"; minCount="1"},@{Name="Credit Card Number"; minCount="1"},@{Name="Drug Enforcement Agency (DEA) Number"; minCount="1"},@{Name="U.S. / U.K. Passport Number"; minCount="1"},@{Name="U.S. Bank Account Number"; minCount="1"},@{Name="U.S. Individual Taxpayer Identification Number (ITIN)"; minCount="1"},@{Name="U.S. Social Security Number (SSN)"; minCount="1"}) -SenderNotificationType "NotifyOnly"
```

有关详细信息，请参阅[Set-IRMConfiguration](https://docs.microsoft.com/powershell/module/exchange/set-irmconfiguration)和[New-TransportRule。](https://docs.microsoft.com/powershell/module/exchange/new-transportrule)

## <a name="how-recipients-access-attachments"></a>收件人如何访问附件

Microsoft 加密邮件后，收件人在访问和打开其加密电子邮件时可以不受限制地访问附件。

## <a name="to-prepare-for-this-change"></a>准备进行此更改

您可能需要更新任何适用的最终用户文档和培训材料，以让组织人员为此更改做好准备。 根据情况与用户共享这些 Office 365 邮件加密资源：

- [在 Outlook for PC 中发送、查看和回复加密邮件](https://support.microsoft.com/en-us/office/send-view-and-reply-to-encrypted-messages-in-outlook-for-pc-eaa43495-9bbb-4fca-922a-df90dee51980)
- [Microsoft 365 Essentials 视频：Office 邮件加密](https://youtu.be/CQR0cG_iEUc)

## <a name="view-these-changes-in-the-audit-log"></a>在"管理"中查看审核日志

Microsoft 365 审核此活动，并提供给管理员使用。 操作为"New-TransportRule"，下面是安全与合规中心审核日志搜索&代码段：

```text
*{"CreationTime":"2018-11-28T23:35:01","Id":"a1b2c3d4-daa0-4c4f-a019-03a1234a1b0c","Operation":"New-TransportRule","OrganizationId":"123456-221d-12345 ","RecordType":1,"ResultStatus":"True","UserKey":"Microsoft Operator","UserType":3,"Version":1,"Workload":"Exchange","ClientIP":"123.456.147.68:17584","ObjectId":"","UserId":"Microsoft Operator","ExternalAccess":true,"OrganizationName":"contoso.onmicrosoft.com","OriginatingServer":"CY4PR13MBXXXX (15.20.1382.008)","Parameters": {"Name":"Organization","Value":"123456-221d-12346"{"Name":"ApplyRightsProtectionTemplate","Value":"Encrypt"},{"Name":"Name","Value":"Encrypt outbound sensitive emails (out of box rule)"},{"Name":"MessageContainsDataClassifications"…etc.*
```

## <a name="to-disable-or-customize-the-sensitive-information-types-policy"></a>禁用或自定义敏感信息类型策略

创建 Exchange 邮件流规则后，可以通过在 Exchange [](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules#enable-or-disable-a-mail-flow-rule)管理中心 (EAC ) 中访问"邮件流规则"来禁用或编辑该规则) 并禁用规则"加密出站敏感电子邮件 (开箱即用规则  >  *) "。*
