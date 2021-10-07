---
title: 文档指纹
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: ITPro
ms.topic: article
search.appverid: MET150
ms.service: exchange-online
ms.collection: M365-security-compliance
ms.localizationpriority: medium
description: 组织中的信息工作人员每天会处理大量的敏感信息。 "文档指纹"可识别贵组织中使用的标准表单，以便于您保护此信息。 本主题介绍文档指纹背后的概念，以及如何使用 PowerShell 创建文档指纹。
ms.openlocfilehash: 6661fd52bfe94ab23a38eaa42eca45a3e609c565
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60155042"
---
# <a name="document-fingerprinting"></a>文档指纹

组织中的信息工作人员每天会处理大量的敏感信息。 在安全与合规中心内，文档指纹通过标识整个组织使用的标准表单来更轻松地 &amp; 保护此信息。 本主题介绍文档指纹背后的概念，以及如何使用 PowerShell 创建文档指纹。
  
## <a name="basic-scenario-for-document-fingerprinting"></a>文档指纹的基本方案

文档指纹是一项数据丢失防护 (DLP) 功能，可将标准表单转换为敏感信息类型，可在 DLP 策略的规则中使用该类型。 例如，您可以基于空白父模板来创建文档指纹，然后创建 DLP 策略，用于检测和阻止所有包含敏感内容的传出父模板。 （可选）您可以设置策略提示[](use-notifications-and-policy-tips.md)以通知发件人他们可能正在发送敏感信息，并且发件人应验证收件人是否有资格接收专利。 此过程与组织中使用的任何基于文本的表单一起使用。 您可以上载的其他表单示例包括：
  
- 政府表单
- 符合《健康保险可携性与责任法案》 (HIPAA) 的表单  
- 人力资源部的员工信息表单
- 组织专门创建的自定义表单

理想情况下，贵组织已经创建使用特定表单传输敏感信息的业务实践。 上载要转换为文档指纹的空表单并设置相应的策略后，DLP 会检测出站邮件中与此指纹匹配的任何文档。

## <a name="how-document-fingerprinting-works"></a>文档指纹的工作原理

您可能已经猜到，文档并非真的有指纹，只是"指纹"这个词可以表明其功能。 人的指纹各不相同，同理，文档的单词模式也各不相同。 上载文件时，DLP 标识文档中的唯一单词模式，基于该模式创建文档指纹，并使用该文档指纹检测包含相同模式的出站文档。 这也是为什么上载表单或模板可以创建最有效的文档指纹的原因。 填写表单的每个人使用相同的单词集，然后在文档中添加自己的词句。 只要出站文档不受密码保护且包含原始表单的所有文本，DLP 就可以确定文档是否与文档指纹匹配。

> [!IMPORTANT]
> 目前，DLP 可以将文档指纹用作仅联机Exchange检测方法。

下列示例说明了当您基于父模板创建文档指纹时发生了什么，但您可以使用任何表单作为基础来创建文档指纹。
  
### <a name="example-of-a-patent-document-matching-a-document-fingerprint-of-a-patent-template"></a>与父模板的文档指纹匹配的父文档示例

![文档指纹关系图。](../media/Document-Fingerprinting-diagram.png)
  
专利模板包含空白字段"专利标题"、"专利"和"说明"以及其中每个字段的说明，即单词模式。 上载原始专利模板时，该模板为受支持的文件类型之一，以纯文本格式显示。 DLP 将此单词模式转换为文档指纹，文档指纹是一个小的 Unicode XML 文件，其中包含表示原始文本的唯一哈希值，指纹在 Active Directory 中另存为数据分类。  (作为一种安全措施，原始文档本身不会存储在服务中;仅存储哈希值，并且无法从哈希值重新构造原始文档。) 然后，专利指纹将成为您可以与 DLP 策略关联的敏感信息类型。 将指纹与 DLP 策略关联后，DLP 会检测包含与专利指纹匹配的文档的任何出站电子邮件，并根据组织策略处理这些电子邮件。 

例如，您可能希望设置一个 DLP 策略，阻止普通员工发送包含专利的传出邮件。 DLP 将使用专利指纹来检测专利并阻止这些电子邮件。 或者，您可能希望让法律部门能够向其他组织发送专利，因为它具有执行此操作的业务需求。 您可以通过在 DLP 策略中为特定部门创建例外来允许特定部门发送敏感信息，也可以允许它们使用业务理由覆盖策略提示。
  
### <a name="supported-file-types"></a>支持的文件类型

文档指纹支持邮件流规则中支持的相同文件类型 (传输规则) 。 有关受支持的文件类型的列表，请参阅支持的邮件 [流规则内容检查的文件类型](/exchange/security-and-compliance/mail-flow-rules/inspect-message-attachments#supported-file-types-for-mail-flow-rule-content-inspection)。 关于文件类型的一个快速说明：邮件流规则或文档指纹均支持 .dotx 文件类型，这可能会令人困惑，因为这是 Word 中的模板文件。 当您在本主题或其他文档指纹主题中看到"template"一词时，它是指您构建为标准模板的文档，而非模板文件类型。
  
#### <a name="limitations-of-document-fingerprinting"></a>文档指纹的限制

在下列情况下，文档指纹不会检测敏感信息：
  
- 密码保护的文件
- 仅包含图片的文件
- 不包含用于创建文档指纹的原始表单中所有文本的文档
- 大于 10 MB 的文件

## <a name="use-powershell-to-create-a-classification-rule-package-based-on-document-fingerprinting"></a>使用 PowerShell 创建基于文档指纹的分类规则包

请注意，当前只能使用安全与合规中心中的 PowerShell 创建文档 &amp; 指纹。 若要连接，请参阅[连接安全&中心 PowerShell。](/powershell/exchange/connect-to-scc-powershell)

DLP 使用分类规则包检测敏感内容。 若要创建基于文档指纹的分类规则包，请使用 **New-DlpFingerprint** 和 **New-DlpSensitiveInformationType** cmdlet。 由于 **New-DlpFingerprint** 的结果不存储在数据分类规则外部，因此始终在同一 PowerShell 会话中运行 **New-DlpFingerprint** 和 **New-DlpSensitiveInformationType** 或 **Set-DlpSensitiveInformationType。** 以下示例基于文件 C:\My Documents\Contoso Employee Template.docx 创建新的文档指纹。 将新指纹存储为变量，以便可以在同一 PowerShell 会话中将新指纹与 **New-DlpSensitiveInformationType** cmdlet 一同使用。
  
```powershell
$Employee_Template = Get-Content "C:\My Documents\Contoso Employee Template.docx" -Encoding byte -ReadCount 0
$Employee_Fingerprint = New-DlpFingerprint -FileData $Employee_Template -Description "Contoso Employee Template"
```

现在，我们可以一起创建名为"Contoso Employee Confidential"的新数据分类规则，该规则使用文件 C:\My Documents\Contoso Customer Information Form.docx 的文档指纹。
  
```powershell
$Customer_Form = Get-Content "C:\My Documents\Contoso Customer Information Form.docx" -Encoding byte -ReadCount 0
$Customer_Fingerprint = New-DlpFingerprint -FileData $Customer_Form -Description "Contoso Customer Information Form"
New-DlpSensitiveInformationType -Name "Contoso Customer Confidential" -Fingerprints $Customer_Fingerprint -Description "Message contains Contoso customer information." 
```

现在，您可以使用 **Get-DlpSensitiveInformationType** cmdlet 查找所有 DLP 数据分类规则包，并且本示例中，"Contoso Customer Confidential"是数据分类规则包列表的一部分。 
  
最后，将"Contoso Customer Confidential"数据分类规则包添加到安全与合规中心中的 DLP &amp; 策略。 本示例向名为"ConfidentialPolicy"的现有 DLP 策略添加规则。

```powershell
New-DlpComplianceRule -Name "ContosoConfidentialRule" -Policy "ConfidentialPolicy" -ContentContainsSensitiveInformation @{Name="Contoso Customer Confidential"} -BlockAccess $True
```

您还可以使用邮件流规则中的数据分类规则包Exchange Online，如以下示例所示。 若要运行此命令，首先需要连接[Exchange Online PowerShell。](/powershell/exchange/connect-to-exchange-online-powershell) 另请注意，规则包需要一些时间从安全与合规中心同步到Exchange &amp; 中心。
  
```powershell
New-TransportRule -Name "Notify :External Recipient Contoso confidential" -NotifySender NotifyOnly -Mode Enforce -SentToScope NotInOrganization -MessageContainsDataClassification @{Name=" Contoso Customer Confidential"}
```

DLP 现在检测到与 Contoso Customer 和文档指纹Form.docx匹配的文档。
  
有关语法和参数的信息，请参阅：

- [New-DlpFingerprint](/powershell/module/exchange/New-DlpFingerprint)
- [New-DlpSensitiveInformationType](/powershell/module/exchange/New-DlpSensitiveInformationType)
- [Remove-DlpSensitiveInformationType](/powershell/module/exchange/Remove-DlpSensitiveInformationType)
- [Set-DlpSensitiveInformationType](/powershell/module/exchange/Set-DlpSensitiveInformationType)
- [Get-DlpSensitiveInformationType](/powershell/module/exchange/Get-DlpSensitiveInformationType)
