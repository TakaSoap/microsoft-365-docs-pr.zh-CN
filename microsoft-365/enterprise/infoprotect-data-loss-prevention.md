---
title: 步骤 5：配置 Office 365 数据丢失防护
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/19/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: 了解并部署 Microsoft 365 中的 Office 365 数据丢失防护。
ms.openlocfilehash: 43ebfb39202e407fe6dc7bb4c8e0fe8f906f7a6d
ms.sourcegitcommit: 8bcd76e5c8749a5670fbc3356957a089454c03d1
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/02/2019
ms.locfileid: "37370159"
---
# <a name="step-5-configure-office-365-data-loss-prevention"></a>步骤 5：配置 Office 365 数据丢失防护

*此步骤可选，它适用于 Microsoft 365 企业版的 E3 和 E5 版本*

![第 6 阶段：信息保护](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

通过 Office 365 安全与合规中心的数据丢失防护 (DLP) 策略，可在 Microsoft 365 内识别、监视和自动保护敏感数据。 DLP 策略可助你实现以下操作：

- 跨 Exchange Online、SharePoint Online、OneDrive for Business 和 Microsoft Teams 等多个位置标识敏感信息。
- 阻止访问某文档或阻止包含该文档的电子邮件，从而防止额外共享敏感信息。
- 监视和保护 Excel、PowerPoint 和 Word 桌面版中的敏感信息。
- 帮助用户了解如何通过电子邮件通知和策略提示在不中断工作流的同时保证合规。 
- 查看 DLP 报告，了解符合组织的 DLP 策略的内容。

DLP 策略指定以下内容：

- **何处：** Exchange Online、SharePoint Online 和 OneDrive for Business 网站等位置，还包括 Microsoft Teams 聊天和频道。
- **何时：** 内容必须在特定策略规则中匹配的条件。
- **如何：** 该匹配策略规则中针对匹配条件自动执行的操作。

换言之：

- 对于此位置（何处）中的文档，如果内容与规则的条件相匹配（何时），则自动执行规则中指定的操作（如何）。

为确定你需要的 DLP 策略集，必须分析需要防止数据丢失的文档及其包含的数据类型。 例如，如果你是美国的一家财务组织，则会创建一个 DLP 策略来阻止在组织外部共享包含社会安全号码的文档或阻止通过电子邮件将此类文档发送到组织外部。

接下来，你使用测试位置来配置和测试策略，以确保 DLP 行为正确无误并最大程度减少误报。

最后，你让员工知晓新策略及其预期行为，同时扩大位置范围，将它推广到整个组织。

有关详细信息，请参阅[开始使用 DLP 策略建议](https://docs.microsoft.com/office365/securitycompliance/get-started-with-dlp-policy-recommendations)。

作为临时检查点，请查看对应于此步骤的[退出条件](infoprotect-exit-criteria.md#crit-infoprotect-step5)。

## <a name="next-step"></a>后续步骤

|||
|:-------|:-----|
|![第 6 步](./media/stepnumbers/Step6.png)|[配置电子邮件加密](infoprotect-email-encryption.md)|


