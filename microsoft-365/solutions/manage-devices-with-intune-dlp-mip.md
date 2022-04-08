---
title: 步骤 7. 使用信息保护功能实现数据丢失防护 (DLP)
ms.author: bcarter
author: brendacarter
f1.keywords:
- Endpoint dlp
- data loss prevention
- dlp policies
manager: dougeby
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.localizationpriority: high
ms.collection:
- endpoint dlp
- data loss prevention
- dlp policies
- M365-security-compliance
- m365solution-managedevices
- m365solution-scenario
ms.custom: ''
keywords: ''
description: 通过与信息保护和管理团队合作，为组织创建 DLP 策略，实现终结点 DLP。
ms.openlocfilehash: ab0be14f0a20f35044489e7f3ad0ba3f60180bcd
ms.sourcegitcommit: 5c9137f98e688ab23c144e75687399e390bb2601
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/07/2022
ms.locfileid: "64705180"
---
# <a name="step-7-implement-data-loss-prevention-dlp-with-information-protection-capabilities"></a>步骤 7. 使用信息保护功能实现数据丢失防护 (DLP)


如果组织使用 Microsoft 365 信息保护，并且已投入时间来了解数据、开发数据敏感度架构和应用架构，则你可能已准备好使用数据丢失防护 (DLP) 策略将此架构的元素扩展到终结点。 

Microsoft Endpoint 数据丢失防护（终结点 DLP）当前适用于：
- Windows 10、Windows 11
- macOS

DLP 策略由信息保护和管理团队创建。每个 DLP 策略定义要查找的数据集中的元素，例如敏感信息类型或标签，以及如何保护此数据。 

例如，DLP 策略可以查找个人数据，如护照号码。 DLP 策略将包括触发策略采取行动的条件，例如当护照号码与组织外部的人员共享时。 也可以配置策略采取的操作。 选项范围包括仅向管理员报告操作、警告用户，甚至阻止共享数据。

DLP 策略还指定要将策略应用到的位置，例如 Exchange 电子邮件和 SharePoint 网站。 管理员可用的位置之一是设备。 如果选择了设备，则可以指定要将策略应用到的用户和用户组。 还可以指定要从策略中排除的用户和用户组。

如果信息保护和治理团队已准备好将 DLP 策略扩展到终结点，则需要与它们协调以为终结点 DLP 启用设备、测试和优化 DLP 策略、培训用户并监视结果。 

![设备管理员的终结点 DLP 步骤](../media/devices/endpoint-dlp-steps.png#lightbox)


使用以下步骤与信息保护团队协作。


|步骤  |说明  |
|---------|---------|
|1     |  [了解 Microsoft 365 终结点数据丢失防护](../compliance/endpoint-dlp-learn-about.md)。        |
|2     | 载入终结点 DLP 的设备。 如果已将设备载入到 Microsoft Defender for Endpoint，则设备已加入 Microsoft 365 合规性，包括终结点 DLP。 如果设备未载入到 Defender for Endpoint，请参阅 [开始使用终结点数据丢失防护](../compliance/endpoint-dlp-getting-started.md) 以获取说明。 更多有关载入工作原理的信息，请参阅 [注册设备与载入设备](manage-devices-with-intune-overview.md#enrolling-devices-vs-onboarding-devices)|
|3     |   与信息保护和治理团队协作，定义、测试、优化策略。 这包括监视结果。 请查看以下资源：<br>- [使用终结点数据丢失防护](../compliance/endpoint-dlp-using.md)<br>- [查看数据丢失防护报告](../compliance/view-the-dlp-reports.md)      |
