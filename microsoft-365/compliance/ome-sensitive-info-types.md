---
title: 使用Office 365消息加密创建敏感信息类型策略
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 8/28/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: ''
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- Strat_O365_Enterprise
description: 了解如何使用Office 365消息加密为组织创建敏感信息类型策略。
ms.custom:
- seo-marvel-apr2020
- admindeeplinkEXCHANGE
ms.openlocfilehash: a12c3c559fdd9dcc7bd142e5ee7d58d777211bc7
ms.sourcegitcommit: 9ba00298cfa9ae293e4a57650965fdb3e8ffe07b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/11/2022
ms.locfileid: "64759404"
---
# <a name="create-a-sensitive-information-type-policy-for-your-organization-using-message-encryption"></a>使用消息加密为组织创建敏感信息类型策略

可以使用Exchange邮件流规则或数据丢失防护 (DLP) 创建包含Office 365消息加密的敏感信息类型策略。 若要创建Exchange邮件流规则，可以使用<a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange管理中心 (EAC) </a>或 PowerShell。

## <a name="to-create-the-policy-by-using-mail-flow-rules-in-the-eac"></a>在 EAC 中使用邮件流规则创建策略

登录到 <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange管理中心</a>并转到 **Mail** **flowRules** > 。 在“规则”页上，创建一个应用Office 365消息加密的规则。 可以根据条件创建规则，例如消息或附件中存在某些关键字或敏感信息类型。

### <a name="to-create-the-policy-by-using-mail-flow-rules-in-powershell"></a>在 PowerShell 中使用邮件流规则创建策略

使用组织中具有全局管理员权限的工作或学校帐户，启动Windows PowerShell会话并连接到Exchange Online。 有关说明，请参阅[连接 PowerShell Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell)。 使用Set-IRMConfiguration和New-TransportRule cmdlet 创建策略。

## <a name="example-mail-flow-rule-created-with-powershell"></a>使用 PowerShell 创建的邮件流规则示例

在 PowerShell 中运行以下命令，创建一个Exchange邮件流规则，如果电子邮件或其附件包含以下敏感信息类型，则使用仅加密选项自动加密组织外部发送的电子邮件：

- ABA 路由编号
- 信用卡号
- 缉毒局 (DEA) 号码
- 美国/英国 passport number
- 美国银行帐号
- 美国单独的纳税人标识号 (ITIN)
- 美国社会保险号 (SSN)

```powershell
Set-IRMConfiguration -DecryptAttachmentForEncryptOnly $true
New-TransportRule -Name "Encrypt outbound sensitive emails (out of box rule)" -SentToScope  NotInOrganization  -ApplyRightsProtectionTemplate "Encrypt" -MessageContainsDataClassifications @(@{Name="ABA Routing Number"; minCount="1"},@{Name="Credit Card Number"; minCount="1"},@{Name="Drug Enforcement Agency (DEA) Number"; minCount="1"},@{Name="U.S. / U.K. Passport Number"; minCount="1"},@{Name="U.S. Bank Account Number"; minCount="1"},@{Name="U.S. Individual Taxpayer Identification Number (ITIN)"; minCount="1"},@{Name="U.S. Social Security Number (SSN)"; minCount="1"}) -SenderNotificationType "NotifyOnly"
```

有关详细信息，请参阅 [Set-IRMConfiguration](/powershell/module/exchange/set-irmconfiguration) 和 [New-TransportRule](/powershell/module/exchange/new-transportrule)。

## <a name="how-recipients-access-attachments"></a>收件人如何访问附件

Microsoft 加密邮件后，收件人访问并打开加密电子邮件时，对附件的访问不受限制。

## <a name="to-prepare-for-this-change"></a>为此更改做好准备

你可能想要更新任何适用的最终用户文档和培训材料，为组织中的人员准备此更改。 根据需要与用户共享这些Office 365消息加密资源：

- [在电脑Outlook中发送、查看和答复加密邮件](https://support.microsoft.com/en-us/office/send-view-and-reply-to-encrypted-messages-in-outlook-for-pc-eaa43495-9bbb-4fca-922a-df90dee51980)
- [Microsoft 365概要视频：Office消息加密](https://youtu.be/CQR0cG_iEUc)

## <a name="view-these-changes-in-the-audit-log"></a>在审核日志中查看这些更改

Microsoft 365审核此活动，并使其可供管理员使用。 操作为“New-TransportRule”，下面是安全&合规中心审核日志搜索示例审核条目的代码片段：

```text
*{"CreationTime":"2018-11-28T23:35:01","Id":"a1b2c3d4-daa0-4c4f-a019-03a1234a1b0c","Operation":"New-TransportRule","OrganizationId":"123456-221d-12345 ","RecordType":1,"ResultStatus":"True","UserKey":"Microsoft Operator","UserType":3,"Version":1,"Workload":"Exchange","ClientIP":"123.456.147.68:17584","ObjectId":"","UserId":"Microsoft Operator","ExternalAccess":true,"OrganizationName":"contoso.onmicrosoft.com","OriginatingServer":"CY4PR13MBXXXX (15.20.1382.008)","Parameters": {"Name":"Organization","Value":"123456-221d-12346"{"Name":"ApplyRightsProtectionTemplate","Value":"Encrypt"},{"Name":"Name","Value":"Encrypt outbound sensitive emails (out of box rule)"},{"Name":"MessageContainsDataClassifications"...etc.*
```

## <a name="to-disable-or-customize-the-sensitive-information-types-policy"></a>禁用或自定义敏感信息类型策略

创建Exchange邮件流规则后，可以通过转到 <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange管理中心</a>中的 **Mail** **flowRules** >  并禁用规则“*加密出站敏感电子邮件 (开箱即用规则)*”来 [禁用或编辑](/exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules#enable-or-disable-a-mail-flow-rule)该规则。