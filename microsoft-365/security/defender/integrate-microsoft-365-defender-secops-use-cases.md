---
title: 步骤 5. 开发和测试用例
description: 将Microsoft 365 Defender集成到安全操作中时开发和测试用例的基础知识。
keywords: 事件， 警报， 调查， 关联， 攻击， 设备， 用户， 标识， 标识， 邮箱， 电子邮件， 365， microsoft， m365， 事件响应， 网络攻击， secops， 安全操作， soc
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-m365dsecops
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: ae77d89a568f79e3369f9ded4cfb0a96aa0255d0
ms.sourcegitcommit: ac0ae5c2888e2b323e36bad041a4abef196c9c96
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/12/2022
ms.locfileid: "64782536"
---
# <a name="step-5-develop-and-test-use-cases"></a>步骤 5. 开发和测试用例

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**适用于：**
- Microsoft 365 Defender

建议在安全运营中心 (SOC) 中部署Microsoft 365 Defender的方法取决于 SOC 团队当前的一组工具、流程和技能集。 跨平台维护网络卫生可能很困难，因为大量数据来自数十个（如果不是数百个）安全源。

安全工具相互关联。 在安全技术中打开一项功能或更改进程可能会反过来破坏另一项功能。 因此，Microsoft 建议 SOC 团队正式设置用于定义和确定用例优先级的方法。 用例有助于定义不同团队中 SOC 操作的要求和测试过程。 它创建一个用于捕获指标的方法，以确定正确的角色和任务组合是否与具有正确技能集的正确团队保持一致。

## <a name="develop-and-formalize-use-case-process"></a>开发和正式化用例过程

SOC 应为开发用例定义一个高级标准和流程，该用例将由 SOC 监督团队进行监管。 SOC 监督团队应与你的业务、IT、法律、人力资源和其他组合作，确定 SOC 的用例优先级，这些用例最终将进入 SOC 团队的 Runbook 和 playbook。 用例的优先级基于目标，例如合规性或隐私。

与用例开发相关的 SOC 监督活动包括：

- 要求
- 人员配备或培训需求
- 软件许可证
- 供应商合同
- 管理计划
- 维护用例注册表
- 维护/更新模板

若要简化 Runbook 和 playbook 创建过程，请创建一个用例决策树。 此图显示了一个示例。

:::image type="content" source="../../media/integrate-microsoft-365-defender-secops/use-case-decision-process.png" alt-text="用例决策过程" lightbox="../../media/integrate-microsoft-365-defender-secops/use-case-decision-process.png":::

定义并批准高级用例标准后，下一步是创建和测试实际用例。 以下部分使用防钓鱼、威胁和漏洞扫描方案作为示例。

## <a name="use-case-example-1-new-phishing-variant"></a>用例示例 1：新的网络钓鱼变体

创建用例的第一步是使用故事板概述工作流。 下面是一个高级故事板示例，用于向威胁情报团队发出新的网络钓鱼攻击通知。

:::image type="content" source="../../media/integrate-microsoft-365-defender-secops/example-use-case-workflow-storyboard-phishing.png" alt-text="反钓鱼活动的用例工作流" lightbox="../../media/integrate-microsoft-365-defender-secops/example-use-case-workflow-storyboard-phishing.png":::

### <a name="invoke-the-use-case-workflow-for-example-1"></a>调用用例 1 的用例工作流

故事板获得批准后，下一步是调用用例工作流。 下面是反网络钓鱼活动的示例过程。

:::image type="content" source="../../media/integrate-microsoft-365-defender-secops/example-detailed-use-case-workflow-phishing.png" alt-text="反钓鱼活动的详细用例工作流" lightbox="../../media/integrate-microsoft-365-defender-secops/example-detailed-use-case-workflow-phishing.png":::

## <a name="use-case-example-2-threat-and-vulnerability-scanning"></a>用例示例 2：威胁和漏洞扫描

另一种可以使用用例的情况是威胁和漏洞扫描。 在此示例中，SOC 要求通过批准的流程（包括资产扫描）来修正资产的威胁和漏洞。

下面是资产危险和漏洞管理的示例高级情节提要。

:::image type="content" source="../../media/integrate-microsoft-365-defender-secops/example-use-case-workflow-storyboard-tvm.png" alt-text="用于危险和漏洞管理的用例工作流" lightbox="../../media/integrate-microsoft-365-defender-secops/example-use-case-workflow-storyboard-tvm.png":::

### <a name="invoke-the-use-case-workflow-for-example-2"></a>调用用例 2 的用例工作流

下面是威胁和漏洞扫描的示例过程。

:::image type="content" source="../../media/integrate-microsoft-365-defender-secops/example-detailed-use-case-workflow-tvm.png" alt-text="危险和漏洞管理的详细用例工作流" lightbox="../../media/integrate-microsoft-365-defender-secops/example-detailed-use-case-workflow-tvm.png":::

### <a name="analyze-the-use-case-output-and-lessons-learned"></a>分析用例输出和经验教训

批准和测试用例后，应识别安全团队之间的差距，以及人员、流程和涉及的Microsoft 365 Defender技术。 应分析Microsoft 365 Defender技术，以确定它们是否能够实现所需的结果。 可以通过清单或矩阵跟踪这些内容。

例如，在反网络钓鱼方案示例中，SOC 团队本可以在此表中进行发现。

|SOC 团队|要求|满足要求的人员|满足要求的流程|相关技术|标识的差距|用例更改日志|免除 (Y/N) |
|---|---|---|---|---|---|---|---|
|威胁情报和分析团队|数据源正在正确馈送威胁情报引擎。|威胁情报分析师/工程师|数据馈送要求已建立，来自已批准源的威胁情报触发器|Microsoft Defender for Identity、Microsoft Defender for Endpoint|威胁情报团队没有使用自动化脚本将Microsoft 365 Defender API 与威胁情报引擎链接|将Microsoft 365 Defender作为数据源添加到威胁引擎 <BR> <BR> 更新用例运行簿|N|
|监视团队|数据源正确馈送监视仪表板|第 1，2 层 SOC 分析师 – 监视&警报|报告安全&合规中心安全分数的工作流|[安全&合规中心中的警报](/microsoft-365/security/office-365-security/alerts)  <br><br> 安全分数监视|SOC 分析师无法报告成功进行新的网络钓鱼变体检测以提高安全分数的机制 <br><br> [安全&合规中心中的报告](/microsoft-365/security/office-365-security/reports-and-insights-in-security-and-compliance)|向报告工作流添加跟踪安全分数改进的过程|N|
|工程和 SecOps 团队|更改控制更新是在 SOC 团队 Runbook 中进行的|第 2 层 SOC 工程师|更改 SOC 团队 Runbook 的控制通知过程|已批准的安全设备更改|更改与 SOC 安全技术Microsoft 365 Defender连接需要审批|将 Microsoft Defender for Cloud Apps、Defender for Identity、Defender for Endpoint、安全&合规中心添加到 SOC Runbook|Y|

此外，SOC 团队本可以就上述危险和漏洞管理方案做出下表所述的发现：

|SOC 团队|要求|满足要求的人员|满足要求的流程|相关技术|标识的差距|用例更改日志|免除 (Y/N) |
|---|---|---|---|---|---|---|---|
|SOC 监督|已确定并分类连接到已批准网络的所有资产|SOC 监督、BU 所有者、应用程序所有者、IT 资产所有者等。|集中式资产管理系统，用于发现和列出基于风险的资产类别和属性。|ServiceNow 或其他资产。 <br><br>[Microsoft 365设备清单](/security/defender-endpoint/device-discovery)|只有70%的资产被发现。 Microsoft 365 Defender修正跟踪仅对已知资产有效|成熟的资产生命周期管理服务，确保Microsoft 365 Defender覆盖率达到 100%|N|
|工程& SecOps Teams|根据策略修正资产的高影响和严重漏洞|SecOps 工程师、SOC 分析师：漏洞&合规性、安全工程|用于分类高风险和严重漏洞的定义过程|[威胁和漏洞管理仪表板](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)|Defender for Endpoint 已识别出影响大、警报性高的设备，没有修正计划或实施 Microsoft 建议的活动|添加工作流，以便在每个策略的 30 天内需要修正活动时通知资产所有者;实现票证系统，以通知资产所有者修正步骤。|N|
|监视Teams|威胁和漏洞状态通过公司 Intranet 门户报告|第 2 层 SOC 分析师|从Microsoft 365 Defender自动生成的报表，显示资产的修正进度|[安全&合规中心中的警报](/microsoft-365/security/office-365-security/alerts) <br><br> 安全分数监视|没有向资产所有者传达有关资产威胁和漏洞状态的视图或仪表板报告。|创建自动化脚本，以填充组织的高风险和关键资产漏洞修正状态。|N|

在这些示例用例中，测试显示 SOC 团队的要求存在一些差距，这些差距是作为每个团队职责的基线建立的。 用例清单可以根据需要进行全面的检查，以确保 SOC 团队已准备好Microsoft 365 Defender与新的或现有的 SOC 要求集成。 由于这将是一个迭代过程，因此用例开发过程和用例输出内容自然有助于更新和成熟 SOC 的 Runbook，并吸取经验教训。

## <a name="update-production-runbooks-and-playbooks"></a>更新生产 Runbook 和 playbook

针对所有差距修正用例测试后，可以将所学到的教训和所收集的指标合并到 SOC 团队的生产 Runbook 中， (操作流程) 和 playbook (事件响应和升级过程) 。

可通过多种方式组织 SOC 团队 Runbook 和 playbook 的维护。 每个 SOC 团队可能自行负责，或者可能有一个集中式版本供所有团队在中央存储库中共享。 各个组织的 Runbook 和 playbook 管理基于规模、技能集、角色和职责隔离。 更新 Runbook 后，playbook 更新过程应遵循。

## <a name="use-a-standard-framework-for-escalation"></a>使用标准框架进行升级

Playbook 是 SOC 团队在发生真实事件时需要遵循的步骤，具体取决于对用例的成功集成和测试。 因此，SOC 必须遵循正式的事件响应方法，例如 [NIST 事件响应标准](https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-61r2.pdf) ，该标准已成为事件响应的领先行业标准之一。

NIST 四步事件响应过程包括四个阶段：

1. 准备
2. 检测和分析
3. 包含、消除和恢复
4. 事件后活动

### <a name="example-tracking-preparation-phase-activity"></a>示例：跟踪准备阶段活动

升级 playbook 的核心基础之一是确保每个 SOC 团队在事件或事件之前、期间和之后应该做什么都没有什么歧义。 因此，最好逐步列出说明。

例如，准备阶段可能包含任务的 if/then 或 XoR 矩阵。 对于新的网络钓鱼变体示例用例，此类矩阵可能如下所示：

|为什么需要升级？|后续步骤|
|---|---|
|SOC 监视中的警报被评定为 **严重** 触发> **500/小时**|转到 Playbook A，第 2 节，活动 5 (，其中包含指向 playbook 部分的链接) |
|电子商务报告潜在的 DDoS 攻击|调用 Playbook B 节 C、活动 19 (，其中包含指向 playbook 部分的链接) |
|高管报告一封可疑电子邮件是鱼叉式网络钓鱼企图|转到 Playbook 5、第 2 节、活动 5 (，其中包含指向 playbook 部分的链接) |

执行准备阶段后，组织应调用 NIST 概述的剩余阶段：

- 检测和分析
- 包含、消除和恢复
- 事件后活动

## <a name="next-step"></a>后续步骤

[步骤 6.标识 SOC 维护任务](integrate-microsoft-365-defender-secops-tasks.md)
