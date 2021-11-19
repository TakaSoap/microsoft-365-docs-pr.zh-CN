---
title: 查看 Microsoft Defender for Cloud Apps 的体系结构要求和结构
description: Microsoft Defender for Cloud Apps 技术图表介绍了 Microsoft 365 Defender 中的体系结构，这将帮助你构建试点环境。
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: bcarter
author: brendacarter
ms.date: 07/09/2021
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 065dd43af376c16ee9e5daa332a08bc25b0d6b11
ms.sourcegitcommit: 1ef176c79a0e6dbb51834fe30807409d4e94847c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/19/2021
ms.locfileid: "61110315"
---
# <a name="review-architecture-requirements-and-key-concepts-for-microsoft-defender-for-cloud-apps"></a>查看 Microsoft Defender for Cloud Apps 的体系结构要求和关键概念


**适用于：**

- Microsoft 365 Defender

本文是设置 Microsoft Defender for Cloud Apps 评估环境过程中的步骤[1/3](eval-defender-mcas-overview.md) Microsoft 365 Defender。 有关此过程详细信息，请参阅 [概述文章](eval-defender-identity-overview.md)。

在启用适用于云应用的 Microsoft Defender 之前，请确保你了解体系结构并满足要求。 

## <a name="understand-the-architecture"></a>了解体系结构

Microsoft Defender for Cloud Apps 是 CASB (云) 。 CASB 充当网关守卫，在企业用户和用户使用的云资源之间实时代理访问，无论用户位于何处，无论他们使用何种设备。 Microsoft Defender for Cloud Apps 在本机与 Microsoft 安全性功能集成，包括Microsoft 365 Defender。

如果没有适用于云应用的 Defender，组织使用的云应用将不受管理且不受保护，如上所示。

![Microsoft Defender for Cloud Apps 的体系结构。](../../media/defender/m365-defender-mcas-architecture-a.png)

在此图中：
- 组织使用云应用不受监控且不受保护。 
- 此使用超出在托管组织中实现的保护范围。 

#### <a name="discovering-cloud-apps"></a>发现云应用

管理云应用使用的第一步是发现组织使用哪些云应用。 下图说明了云发现如何与 Defender for Cloud Apps 一起工作。

![Microsoft Defender for Cloud Apps 的体系结构 - 云发现。](../../media/defender/m365-defender-mcas-architecture-b.png)

在此图中，有两种方法可用于监视网络流量和发现组织使用的云应用。
- 答： 云应用发现与 Microsoft Defender for Endpoint 本地集成。 Defender for Endpoint 报告从 IT 托管的云应用和服务Windows 10和Windows 11访问。 
- B. 为了覆盖连接到网络的所有设备，将 Defender for Cloud Apps 日志收集器安装在防火墙和其他代理上，以从终结点收集数据。 此数据将发送到 Defender for Cloud Apps 进行分析。

#### <a name="managing-cloud-apps"></a>管理云应用

在发现云应用并分析组织如何使用这些应用的行为后，你可以开始管理你选择的云应用。 

![Microsoft Defender for Cloud Apps 的体系结构 - 管理云应用。](../../media/defender/m365-defender-mcas-architecture-c.png)

在此图中：
- 某些应用已批准使用。 这是开始管理应用的一种简单方法。
- 通过将应用与应用连接器连接，你可以实现更高的可见性和控制。 应用连接器使用应用提供程序的 API。


#### <a name="applying-session-controls-to-cloud-apps"></a>将会话控件应用到云应用

Microsoft Defender for Cloud Apps 充当反向代理，提供对批准的云应用的代理访问。 这允许 Defender for Cloud Apps 应用你配置的会话控件。 

![Microsoft Defender for Cloud Apps 的体系结构 - 代理访问会话控制。](../../media/defender/m365-defender-mcas-architecture-d.png)

在此图中：
- 通过 Defender for Cloud Apps 路由组织中用户和设备对批准的云应用的访问权限。
- 此代理访问允许应用会话控件。
- 未批准或明确未批准的云应用不受影响。

会话控件允许你将参数应用于组织如何使用云应用。 例如，如果组织使用的是 Salesforce，可以配置仅允许托管设备访问 Salesforce 中组织数据的会话策略。 一个更简单的示例可能是将策略配置为监视来自非托管设备的流量，以便可以在应用更严格的策略之前分析此流量的风险。

#### <a name="integrating-with-azure-ad-with-conditional-access-app-control"></a>与条件Azure AD应用程序控件集成

你可能已经将 SaaS 应用添加到 Azure AD 租户以强制执行多重身份验证和其他条件访问策略。 Microsoft Defender for Cloud Apps 本机与 Azure AD。 只需在云应用中配置策略Azure AD在 Defender for Cloud Apps 中使用条件访问应用控制。 这将通过 Defender for Cloud Apps 作为代理路由这些托管 SaaS 应用的网络流量，从而允许云应用的 Defender 监视此流量并应用会话控件。 

![Microsoft Defender for Cloud Apps 的体系结构 - SaaS 应用。](../../media/defender/m365-defender-mcas-architecture-e.png)

在此图中：
- SaaS 应用与 Azure AD 集成。 这允许Azure AD条件访问策略，包括多重身份验证。
- 策略将添加到 Azure Active Directory，以将 SaaS 应用的流量直接引导到适用于云应用的 Defender。 策略指定要应用此策略的 SaaS 应用。 因此，Azure AD强制执行适用于这些 SaaS 应用的任何条件访问策略后，Azure AD 会通过 Defender for Cloud Apps (代理) 会话流量。
- 云应用的 Defender 监视此流量，并应用管理员配置的任何会话控制策略。 

你可能已使用 Defender for Cloud Apps 发现和批准的云应用，这些应用尚未添加到Azure AD。 通过将这些云应用添加到你的租户和条件访问规则的范围，Azure AD条件访问应用控制。

#### <a name="protecting-your-organization-from-hackers"></a>保护组织免受黑客攻击

Defender for Cloud Apps 本身提供强大的保护。 但是，当与云应用的其他功能Microsoft 365 Defender，Defender for Cloud Apps 会向共享信号提供数据，这共同有助于阻止攻击。

从概述到本试点评估和试点指南，值得Microsoft 365 Defender此图示。 

![如何Microsoft 365 Defender威胁链。](../../media/defender/m365-defender-eval-threat-chain.png)

专注于此图的右侧，Microsoft Defender for Cloud Apps 注意到异常行为，如无法旅行、凭据访问和异常下载、文件共享或邮件转发活动，并报告给安全团队。 因此，Defender for Cloud Apps 有助于防止黑客横向移动和敏感数据的窃取。 Microsoft 356 Defender for Cloud 将来自所有组件的信号关联在一起，以提供完整的攻击情景。

## <a name="understand-key-concepts"></a>了解关键概念

下表确定了在评估、配置和部署 Microsoft Defender for Cloud Apps 时必须了解的重要概念。


|概念  |说明 |更多信息  |
|---------|---------|---------|
| 云应用仪表板的 Defender | 概述了有关组织的最重要的信息，并提供了深入调查的链接。        | [使用仪表板 ](/cloud-app-security/daily-activities-to-protect-your-cloud-environment)       |
| 条件访问应用控制    | 与 Identity Provider 和 IdP (的反向代理) ，Azure AD条件访问策略，并选择性地强制执行会话控制。        |  [使用 Microsoft Defender for Cloud Apps 条件访问应用控制保护应用](/cloud-app-security/proxy-intro-aad)       |
|  云应用程序目录   | 通过云应用目录，你可以全面了解超过 16，000 个云应用的 Microsoft 目录，这些应用根据 80 多个风险因素进行排名和评分。    |  [使用应用风险评分](/cloud-app-security/risk-score)       |
| 云发现仪表板    | 云发现可分析流量日志，旨在进一步深入了解云应用在组织中是如何使用的，并给出警报和风险级别。     |  [使用发现的应用   ](/cloud-app-security/discovered-apps)    |
|连接的应用 |Defender for Cloud Apps 使用云到云集成、API 连接器以及利用条件应用访问控制实时访问和会话控件为连接应用提供端到端保护。 |[保护已连接的应用](/cloud-app-security/protect-connected-apps) |
| | | |

## <a name="review-architecture-requirements"></a>查看体系结构要求

### <a name="discovering-cloud-apps"></a>发现云应用

若要发现环境中使用的云应用，你可以执行以下一项或两项操作：

- 与 Microsoft Defender for Endpoint 集成，快速启动并运行云发现。 通过此本机集成，你可以立即开始在网络内和Windows 11 Windows 10设备上收集云流量数据。
- 若要发现连接到网络的所有设备访问的所有云应用，请在你的防火墙和其他代理上部署 Defender for Cloud Apps 日志收集器。 这将从终结点收集数据，并将其发送到 Defender for Cloud Apps 进行分析。 云应用的 Defender 在本机与一些第三方代理集成，实现更多功能。

这些选项包含在步骤 [2 中。启用评估环境](eval-defender-mcas-enable-eval.md)。 

### <a name="applying-azure-ad-conditional-access-policies-to-cloud-apps"></a>将Azure AD访问策略应用于云应用

条件访问应用控制 (条件访问策略应用于云应用) 需要与 Azure AD。 这不是开始使用 Defender for Cloud Apps 的要求。 我们鼓励你在试点阶段（步骤 [3）中试用此步骤。试用 Microsoft Defender for Cloud Apps](eval-defender-mcas-pilot.md)。

## <a name="siem-integration"></a>SIEM 集成

你可以将 Microsoft Defender for Cloud Apps 与通用 SIEM 服务器或 Microsoft Sentinel 集成，以集中监视已连接应用中的警报和活动。 

此外，Microsoft Sentinel 包括 Microsoft Defender for Cloud Apps 连接器，以便与 Microsoft Sentinel 进行更深入的集成。 这样，你不仅能够了解云应用，还可以获得复杂的分析，以识别和防御网络威胁，并控制数据传输方式。

- [通用 SIEM 集成](/cloud-app-security/siem)
- [将警报和云发现日志从 Defender for Cloud Apps 流式传输至 Microsoft Sentinel](/azure/sentinel/connect-cloud-app-security)

### <a name="next-steps"></a>后续步骤

步骤 2/3： [为 Microsoft Defender for Cloud Apps 启用评估环境](eval-defender-mcas-enable-eval.md)

返回到评估 Microsoft [Defender for Cloud Apps 的概述](eval-defender-mcas-overview.md)

返回到评估和试点[计划概述Microsoft 365 Defender](eval-overview.md)
