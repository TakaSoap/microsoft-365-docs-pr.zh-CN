---
title: 保护信息
f1.keywords:
- NOCSH
ms.author: bcarter
author: brendacarter
manager: laurawi
ms.date: 4/26/2019
audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: a6ef28a4-2447-4b43-aae2-f5af6d53c68e
description: 此登录页提供有关保护 Microsoft 365 和 Office 365 中的信息的链接和信息。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: bf230c8ca679b36046048b0b349326778a489369
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/05/2020
ms.locfileid: "44031476"
---
# <a name="protect-information"></a>保护信息

Microsoft 365 和 Office 365 包含可应用于特定类型的数据以保护信息的功能。


|**功能**|**详细信息**|
|:-----|:-----|
|[敏感度标签](sensitivity-labels.md) <br/> |使用灵敏度标签，你可以对敏感内容进行分类和帮助保护。 保护选项包括标签、水印和加密。 敏感度标签使用 Azure 信息保护。 如果您使用的是 Azure 信息保护标签，我们建议您在完成迁移后，避免在其他管理中心中心创建新标签。 请参阅[Azure 信息保护迁移](https://docs.microsoft.com/azure/information-protection/configure-policy-migrate-labels)。 <br/> [保留标签](retention-policies.md)不同于敏感度标签。 保留标签可帮助您根据定义的策略保留或删除内容。 这些帮助组织应遵守行业法规和内部策略。|
|[数据丢失防护](data-loss-prevention-policies.md)（DLP）  <br/> |使用 DLP 策略，您可以在 Office 365 中识别、监视和自动保护敏感信息。 数据丢失防护策略可以使用敏感度标签和敏感信息类型来标识敏感信息。 <br/> |
|[敏感信息类型](what-the-sensitive-information-types-look-for.md) <br/> |Microsoft 365 包括许多可供您在 DLP 策略中使用的敏感信息类型，以及具有敏感度和保留标签的自动分类。 敏感信息类型也可以与[Azure 信息保护扫描程序](https://docs.microsoft.com/azure/information-protection/deploy-aip-scanner)结合使用，以在本地对文件进行分类和保护。 敏感信息类型定义了自动化过程如何识别特定的信息类型，如运行状况服务号码和信用卡号。   <br/> |
|[Office 365 邮件加密](ome.md)（OME）  <br/> |使用 Office 365 邮件加密，组织可以在组织内部和外部的人员之间发送和接收加密的电子邮件。 Office 365 邮件加密适用于 Outlook.com、Yahoo！、Gmail 和其他电子邮件服务。 电子邮件加密有助于确保只有预期的收件人可以查看邮件内容。 <br/> |
|[Azure 信息保护](https://docs.microsoft.com/azure/information-protection/)<br/> |Azure 信息保护（有时称为 "AIP"）可帮助组织对文档和电子邮件进行分类、添加标签以及保护文档和电子邮件。 管理员可以通过定义规则和条件来自动应用标签。 用户可以手动将标签应用于文件和邮件。 您还可以向用户提供有关何时应用标签的建议。<br/> 如果使用的是敏感度标签或 Office 邮件加密，则您已经在使用分类和保护功能。 如果尚未将 Azure 信息保护标签迁移到 Office 365，请继续在 Azure 信息保护中管理这些标签。  <br/>您可以在本地运行[Azure 信息保护扫描程序](https://docs.microsoft.com/azure/information-protection/deploy-aip-scanner)，以对 Windows Server、网络共享和 SharePoint server 网站和库上的文件进行分类和保护。 这可能是确定要迁移到 Office 365 的数据的第一步。
|使用客户托管加密密钥的 Azure 信息保护 <br/> |有些组织有业务需求或合规性要求来保留对加密密钥的控制。 这并不常见。 Azure 信息保护允许组织将你自己的密钥（BYOK）带到服务。 有关详细信息，请参阅[为 Azure 信息保护引入你自己的密钥（BYOK）](https://docs.microsoft.com/azure/information-protection/byok-price-restrictions)。 另一个更复杂的选项是为有要求在本地保留加密密钥的客户提供的，称为 "保留自己的密钥（HYOK）"。  有关详细信息，请参阅[保留您自己的密钥（HYOK）以获取 Azure 信息保护](https://docs.microsoft.com/azure/information-protection/configure-adrms-restrictions)。 <br/> |
    

