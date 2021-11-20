---
title: 第 3 步。 规划Microsoft 365 Defender服务目录的集成
description: 将安全Microsoft 365 Defender集成到服务的安全操作目录中的基础知识。
keywords: 事件， 警报， 调查， 关联， 攻击， 设备， 用户， 标识， 标识， 邮箱， 电子邮件， 365， microsoft， m365， 事件响应， 网络攻击， secops， 安全操作， soc
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
- m365solution-m365dsecops
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 7053616ebee7a0c8a63394e2db98704910d1ff10
ms.sourcegitcommit: 07405a81513d1c63071a128b9d5070d3a3bfe1cd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/19/2021
ms.locfileid: "61121443"
---
# <a name="step-3-plan-for-microsoft-365-defender-integration-with-your-soc-catalog-of-services"></a>步骤 3. 规划Microsoft 365 Defender服务目录的集成

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**适用于：**
- Microsoft 365 Defender

已建立的安全 (SOC) 应具有一个服务目录，其中可能包括：

- 入侵&恶意软件分析
- 属性&反向工程
- 威胁智能
- 分析
- 搜寻调查
- 取证
- 事件响应 
- 计算机安全事件响应 (与 SOC)  (隔离的 CSIRT)  
- 合规性测试
- 内部威胁&欺诈监视
- 安全事件&事件监视 
- 漏洞扫描
- XDR (扩展) /Security 业务流程、自动化和响应 (SOAR) 
- 网络钓鱼
- 数据丢失防护
- 品牌监视

由于Microsoft 365 Defender技术跨多个功能，因此 SOC 团队需要确定哪些角色和职责最适合管理组织的各个组件Microsoft 365 Defender与服务功能保持一致。

这些Microsoft 365 Defender包括：

- **Microsoft Defender for Identity** (以前称为 Azure 高级威胁防护（也称为 Azure ATP) ）是一种基于云的安全解决方案，它使用 Active Directory 域服务 (AD DS) 信号来识别、检测和调查针对组织的高级威胁、泄露的身份和恶意预览体验成员操作。

- **Microsoft Defender for Endpoint** 是一款全面的云终结点安全解决方案，适用于设备，包括基于风险的 漏洞管理 和评估、攻击面减少、基于行为和云的下一代保护、终结点检测和响应 (EDR) 、自动调查和修正、托管搜寻服务、丰富的 API 和统一安全管理。

 - **Microsoft Defender for Office 365** 是一种基于云的电子邮件筛选服务，它通过提供强大的零日保护来帮助组织抵御未知恶意软件和病毒，并包括实时保护组织免受有害的链接危害的功能。 它还提供了全面的调查和搜寻、响应和修正、认知和培训以及安全状态功能。

- **Microsoft Defender for Cloud Apps** 是 CASB (云访问安全代理) 支持各种部署模式，包括日志收集、API 连接器和反向代理。 它提供了丰富的可见性、对数据传输的控制以及复杂的分析，以识别和防御所有 Microsoft 和第三方云服务中的网络威胁。

由于Microsoft 365 Defender和技术跨多个功能，因此 SOC 团队需要确定哪些角色和职责最适合管理 Microsoft 365 Defender 的每个组件，并与服务功能保持一致。

若要集成这些Microsoft 365 Defender，您需要优化 SOC 服务。 有关用户功能Microsoft 365 Defender，请参阅以下文章：

- [什么是 Microsoft Defender for Endpoint?](/defender-endpoint/microsoft-defender-endpoint)
- [什么是 Microsoft Defender for Identity?](/defender-for-identity/what-is)
- [什么是 Defender for Office 365？](/office-365-security/defender-for-office-365)
- [什么是 Microsoft Defender 云应用？](/cloud-app-security/what-is-cloud-app-security)

## <a name="next-step"></a>后续步骤

[步骤 4.定义Microsoft 365 Defender角色、职责和监管](integrate-microsoft-365-defender-secops-roles.md)
