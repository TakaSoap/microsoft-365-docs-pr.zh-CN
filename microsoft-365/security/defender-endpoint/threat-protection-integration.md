---
title: 将 Microsoft Defender for Endpoint 与其他 Microsoft 解决方案集成
description: 了解 Microsoft Defender for Endpoint 如何与其他 Microsoft 解决方案集成，包括 Microsoft Defender for Identity 和 Microsoft Defender for Cloud。
author: mjcaparas
ms.author: macapara
ms.prod: m365-security
keywords: microsoft 365 defender， 条件访问， office， Microsoft Defender for Endpoint， microsoft defender for identity， microsoft defender for office， Azure Defender， Microsoft 云应用安全， azure sentinel
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 8da23203a7ab2f8faf86603f6a68700b65cc83e5
ms.sourcegitcommit: 1ef176c79a0e6dbb51834fe30807409d4e94847c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/19/2021
ms.locfileid: "61111551"
---
# <a name="microsoft-defender-for-endpoint-and-other-microsoft-solutions"></a>Microsoft Defender for Endpoint 和其他 Microsoft 解决方案

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 希望体验 Microsoft Defender for Endpoint？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)。

## <a name="integrate-with-other-microsoft-solutions"></a>与其他 Microsoft 解决方案集成

Microsoft Defender for Endpoint 直接与各种 Microsoft 解决方案集成。

### <a name="microsoft-defender-for-cloud"></a>Microsoft Defender for Cloud

Microsoft Defender for Endpoint 提供了全面的服务器保护解决方案，包括终结点检测和响应 (EDR) 服务器上Windows功能。

### <a name="microsoft-sentinel"></a>Microsoft Sentinel

Microsoft Defender for Endpoint 连接器允许你将来自 Microsoft Defender for Endpoint 的警报流式传输至 Microsoft Sentinel。 这将使您能够更全面分析整个组织的安全事件，并生成有效且即时响应的手册。

### <a name="azure-information-protection"></a>Azure 信息保护

我们最近弃用 Azure 信息保护集成，因为我们的 Endpoint DLP 功能包含针对存储在终结点设备上敏感数据的改进的发现和保护解决方案，以便提高解决方案的可见性和集成。 这是在下面的博客中 [宣布的](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/protecting-sensitive-information-on-devices/ba-p/2143555)。 我们建议客户开始使用 Endpoint DLP。

### <a name="conditional-access"></a>条件访问

Microsoft Defender for Endpoint 的动态设备风险评分已集成到条件访问评估中，确保只有安全设备有权访问资源。

### <a name="microsoft-defender-for-cloud-apps"></a>Microsoft Defender for Cloud Apps

Microsoft Defender for Cloud Apps 利用 Microsoft Defender for Endpoint 信号，直接查看云应用程序使用情况，包括从所有 Microsoft Defender for Endpoint 受监视设备使用不受支持的云服务 (卷影 IT) 。

### <a name="microsoft-defender-for-identity"></a>Microsoft Defender for Identity

可疑活动是用户上下文中运行的进程。 Microsoft Defender for Endpoint 和 Microsoft Defender for Identity 之间的集成提供了跨活动和标识进行网络安全调查的灵活性。

### <a name="microsoft-defender-for-office"></a>Microsoft Defender for Office

[Defender for Office 365](/office365/securitycompliance/office-365-atp)通过 保险箱 链接、保险箱 附件、高级防钓鱼和欺骗智能功能帮助保护你的组织免受电子邮件或文件中恶意软件的攻击。 Microsoft Defender for Office 365 和 Microsoft Defender for Endpoint 之间的集成使安全分析师能够前往上游调查攻击的入口点。 通过威胁情报共享，可以包含和阻止攻击。

> [!NOTE]
> Defender for Office 365最近 30 天内的事件显示数据。 对于警报，defender for Office 365基于第一个活动时间显示数据。 此后，数据将不再在 Defender for Office 365。

### <a name="skype-for-business"></a>Skype for Business

通过Skype for Business集成，分析人员可以通过门户中的简单按钮与可能受到威胁的用户或设备所有者进行通信。

## <a name="microsoft-365-defender"></a>Microsoft 365 Defender

借助 Microsoft 365 Defender、Microsoft Defender for Endpoint 和各种 Microsoft 安全解决方案，形成统一的攻破前和入侵后企业防御套件，可跨终结点、标识、电子邮件和应用程序进行本机集成，以检测、阻止、调查和自动响应复杂的攻击。

[详细了解Microsoft 365 Defender](/microsoft-365/security/defender/microsoft-365-defender)

## <a name="related-topics"></a>相关主题

- [配置集成和其他高级功能](advanced-features.md)
- [Microsoft 365 Defender概述](/microsoft-365/security/defender/microsoft-threat-protection)
- [打开 Microsoft 365 Defender](/microsoft-365/security/defender/mtp-enable)
- [使用条件访问保护用户、数据和设备](conditional-access.md)
