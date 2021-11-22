---
title: 步骤 7. 使用信息保护功能实现数据丢失防护（DLP）
ms.author: bcarter
author: brendacarter
f1.keywords:
- NOCSH
manager: dougeby
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.localizationpriority: high
ms.collection:
- M365-security-compliance
ms.custom: ''
keywords: ''
description: ''
ms.openlocfilehash: 76c7f613ba6a859f843550e18baa78637858be46
ms.sourcegitcommit: 2ea2105d40b60a87fc9aa30f392a73a3a9db6d99
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/20/2021
ms.locfileid: "61129068"
---
# <a name="step-7-implement-data-loss-prevention-dlp-with-information-protection-capabilities"></a>步骤 7. 使用信息保护功能实现数据丢失防护（DLP）

如果组织已投入时间了解数据、开发数据敏感度架构和应用架构，则可以使用数据丢失防护（DLP） 策略将此架构的元素扩展到终结点。 

DLP 策略由信息保护和管理团队创建。 每个 DLP 策略定义要查找的数据集中的元素，例如敏感信息类型或标签，以及如何保护此数据。 

例如，DLP 策略可以查找个人数据，如护照号码。 DLP 策略将包括触发策略采取行动的条件，例如当护照号码与组织外部的人员共享时。 也可以配置策略采取的操作。 选项范围包括仅向管理员报告操作、警告用户，甚至阻止共享数据。

DLP 策略还指定要将策略应用到的位置，例如 Exchange 电子邮件和 SharePoint 网站。 管理员可用的位置之一是设备。 如果选择了设备，则可以指定要将策略应用到的用户和用户组。 还可以指定要从策略中排除的用户和用户组。

如果信息保护和管理团队已准备好将 DLP 策略扩展到终结点，则需要与它们协调以载入设备、测试和优化策略、培训用户并监视结果。 

使用以下步骤与信息保护团队协作。


|步骤  |说明  |
|---------|---------|
|1     |  [了解 Microsoft 365 终结点数据丢失防护](../compliance/endpoint-dlp-learn-about.md)。        |
|2     | 将设备加入 Microsoft 365 合规性解决方案。 有关以下说明，请参阅[终结点数据丢失防护入门](../compliance/endpoint-dlp-getting-started.md)：<br>- 加入 Windows 10 和 Windows 11<br>- 加入 MacOS       |
|3     |   与信息保护和治理团队协作，定义、测试、优化策略。 这包括监视结果。 请查看以下资源：<br>- [使用终结点数据丢失防护](../compliance/endpoint-dlp-using.md)<br>- [查看数据丢失防护报告](../compliance/view-the-dlp-reports.md)      |
|     |         |
