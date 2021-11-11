---
title: 步骤 5. 开发和测试用例
description: 将应用程序集成到安全操作时，Microsoft 365 Defender和测试用例的基础知识。
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
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 6003488c0244a33a9fa632d081922ebf85dc85c9
ms.sourcegitcommit: 8410a49995a084e4cc9b3f7286c8d506b7a85d79
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/11/2021
ms.locfileid: "60914388"
---
# <a name="step-5-develop-and-test-use-cases"></a>步骤 5. 开发和测试用例

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**适用于：**
- Microsoft 365 Defender

在安全操作中心 (SOC) 中部署 Microsoft 365 Defender 的建议方法将取决于 SOC 团队当前的一组工具、流程和技能集。 维护跨平台的网络清洁可能充满挑战，因为来自数十个（如果不是数百个）安全源的大量数据。 

安全工具相互关联。 在安全技术中启用一项功能或更改流程可能会破坏另一项功能。 因此，Microsoft 建议 SOC 团队正式化一种用于定义用例和确定用例优先级的方法。 用例有助于为各个团队中的 SOC 操作定义要求和测试流程。 它创建用于捕获指标的方法，以确定正确的角色和任务组合是否与具有正确技能集的合适团队保持一致。 

## <a name="develop-and-formalize-use-case-process"></a>制定并正式化用例流程

SOC 应定义用于开发用例的高级别标准和流程，这由 SOC 监督团队控制。 SOC 监督团队应该与业务、IT、法律、HR 和其他组合作，确定 SOC 用例的优先级，这些用例最终将进入 SOC 团队的 Runbook 和 Playbook。 用例的优先级基于目标，如合规性或隐私。

与用例开发相关的 SOC 监督活动包括： 

- Requirements
- 人员配备或培训需求
- 软件许可证
- 供应商合同
- 管理计划
- 维护用例注册表
- 维护/更新模板

为了加快 Runbook 和 Playbook 的创建过程，请创建用例决策树。 此图显示了一个示例。

:::image type="content" source="../../media/integrate-microsoft-365-defender-secops/use-case-decision-process.png" alt-text="用例决策流程。" lightbox="../../media/integrate-microsoft-365-defender-secops/use-case-decision-process.png":::

定义和批准高级用例标准后，下一步是创建和测试实际用例。 以下各节使用防钓鱼、威胁和漏洞扫描方案作为示例。

## <a name="use-case-example-1-new-phishing-variant"></a>用例示例 1：新的网络钓鱼变体

创建用例的第一步是使用情节提要板概述工作流。 下面是威胁智能团队的新网络钓鱼攻击通知高级情节板示例。
 
:::image type="content" source="../../media/integrate-microsoft-365-defender-secops/example-use-case-workflow-storyboard-phishing.png" alt-text="防钓鱼活动用例工作流示例。" lightbox="../../media/integrate-microsoft-365-defender-secops/example-use-case-workflow-storyboard-phishing.png":::

### <a name="invoke-the-use-case-workflow-for-example-1"></a>调用用例工作流，例如 1

在文章板获得批准后，下一步是调用用例工作流。 下面是防钓鱼活动的示例过程。 
 
:::image type="content" source="../../media/integrate-microsoft-365-defender-secops/example-detailed-use-case-workflow-phishing.png" alt-text="反网络钓鱼活动的详细用例工作流示例。" lightbox="../../media/integrate-microsoft-365-defender-secops/example-detailed-use-case-workflow-phishing.png":::

## <a name="use-case-example-2-threat-and-vulnerability-scanning"></a>用例示例 2：威胁和漏洞扫描

可以使用用例的另一种情况是威胁和漏洞扫描。 在此例中，SOC 要求通过包括资产扫描的已批准流程针对资产修正威胁和漏洞。 

下面是一个有关资产危险和漏洞管理示例。
 
:::image type="content" source="../../media/integrate-microsoft-365-defender-secops/example-use-case-workflow-storyboard-tvm.png" alt-text="示例用例工作流危险和漏洞管理。" lightbox="../../media/integrate-microsoft-365-defender-secops/example-use-case-workflow-storyboard-tvm.png":::

### <a name="invoke-the-use-case-workflow-for-example-2"></a>调用用例工作流（例如 2）

下面是威胁和漏洞扫描的示例过程。
 
:::image type="content" source="../../media/integrate-microsoft-365-defender-secops/example-detailed-use-case-workflow-tvm.png" alt-text="用于工作流的详细用例工作流危险和漏洞管理。" lightbox="../../media/integrate-microsoft-365-defender-secops/example-detailed-use-case-workflow-tvm.png":::
 
### <a name="analyze-the-use-case-output-and-lessons-learned"></a>分析用例输出和学到的经验

批准和测试用例后，应确定安全团队之间的差异，以及所涉及的人员、流程和Microsoft 365 Defender技术。 Microsoft 365 Defender技术，以确定它们是否能够达到预期的结果。 可以通过清单或矩阵跟踪这些记录。 

例如，在防钓鱼方案中，SOC 团队可能在此表中进行了发现。


| SOC 团队 | 要求 | 满足要求的人 | 满足要求的过程 | 相关技术 | 已识别的间隙 | 用例更改日志 | 豁免 (Y/N)  |
|:-------|:-----|:-------|:-------|:-------|:-----|:-------|:-------|
| 威胁智能和分析团队 | 数据源正确馈送威胁情报引擎。 | 威胁智能分析员/工程师 | 已建立数据源要求，来自已批准来源的威胁情报触发器 | Microsoft Defender for Identity，Microsoft Defender for Endpoint | 威胁智能团队没有使用自动化脚本将 Microsoft 365 Defender API 与威胁情报引擎链接 | 将Microsoft 365 Defender作为数据源添加到威胁引擎 <BR> <BR> 更新用例运行书籍 | 网络 |
| 监视团队 | 数据源正确馈送监控仪表板 | 第 1、2 层 SOC 分析员–监视&警报 | 报告安全与&安全分数的工作流 | [安全与合规&中的警报](/microsoft-365/security/office-365-security/alerts)  <br><br> 安全分数监视  | SOC 分析师没有报告成功的新网络钓鱼变体检测以提高安全分数的机制 <br><br> [安全与合规&中的报告](/microsoft-365/security/office-365-security/reports-and-insights-in-security-and-compliance)| 向报告工作流添加跟踪安全分数改进的流程 | 网络 | 
| 工程和 SecOps 团队 | 更改控件更新在 SOC 团队 Runbook 中执行 | 第 2 层 SOC 工程师 | SOC 团队 Runbook 的变更控制通知过程 | 批准的安全设备更改 | 需要批准Microsoft 365 Defender SOC 安全技术的连接的更改 | 将Microsoft Cloud App Security、Defender for Identity、Defender for Endpoint、安全&中心添加到 SOC Runbook | Y |
|||||||||

此外，SOC 团队还可以针对上面概述的危险和漏洞管理表中列出的发现：

| SOC 团队 | 要求 | 满足要求的人 | 满足要求的过程 | 相关技术 | 已识别的间隙 | 用例更改日志 | 豁免 (Y/N)  |
|:-------|:-----|:-------|:-------|:-------|:-----|:-------|:-------|
| SOC 监督 | 已连接到已批准网络的所有资产都进行标识和分类 | SOC 监督、BU 所有者、应用程序所有者、IT 资产所有者等。 | 集中式资产管理系统，用于根据风险发现和列出资产类别和属性。 | ServiceNow 或其他资产。 <br><br>[Microsoft 365设备清单](/security/defender-endpoint/device-discovery) | 仅发现 70% 的资产。 Microsoft 365 Defender修正跟踪仅对已知资产有效 | 成熟资产生命周期管理服务，确保Microsoft 365 Defender 100% 覆盖 | 网络 |
| 工程& SecOps Teams | 根据策略修复资产中的高影响和关键漏洞 | SecOps 工程师和 SOC 分析师：漏洞&合规性，安全工程 | 用于对高风险和关键漏洞进行分类的已定义过程 | [威胁和漏洞管理仪表板](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt) | Defender for Endpoint 已识别高影响、高警报设备，无修正计划或 Microsoft 建议活动的实现 | 添加工作流，以在需要修正活动时根据策略在 30 天内通知资产所有者;实施票证系统以通知资产所有者修正步骤。 | 网络 |
| 监视Teams | 通过公司 Intranet 门户报告威胁和漏洞状态 | 第 2 层 SOC 分析师 | 报告中自动生成的报告Microsoft 365 Defender资产修正进度 | [安全与合规&中的警报](/microsoft-365/security/office-365-security/alerts) <br><br> 安全分数监视 | 未就资产的威胁和漏洞状态向资产所有者传达任何视图或仪表板报告。 | 创建自动化脚本以填充组织的高风险和关键资产漏洞修正状态。 | 网络 |
|||||||||

在这些示例用例中，测试揭示 SOC 团队要求中的一些缺陷，这些要求已建立为每个团队职责的基准。 用例清单可以尽可能全面，以确保 SOC 团队已做好与新的或现有 SOC Microsoft 365 Defender集成的准备。 由于这将是一个迭代过程，用例开发过程和用例输出内容自然有助于更新和成熟 SOC 的 Runbook，并总结经验。

## <a name="update-production-runbooks-and-playbooks"></a>更新生产 Runbook 和 Playbook

针对所有差距修复了用例测试后，可以将所总结的经验和收集的指标合并到 SOC 团队的生产运行手册 (操作流程) 中 (事件响应和上报过程) 。 

可以通过多种方式组织 SOC 团队 Runbook 和 Playbook 的维护。 每个 SOC 团队可能各自负责，或者可能有一个集中版本供所有团队在中央存储库中共享。 适用于各个组织的 Runbook 和 Playbook 管理基于规模、技能集、角色和职责划分。 更新 Runbook 后，应该遵循操作手册更新过程。 

## <a name="use-a-standard-framework-for-escalation"></a>使用标准框架进行升级

Playbook 是 SOC 团队在真实事件发生时需要遵循的步骤，以成功集成和测试用例为基础。 因此，SOC 必须采用形式化的方法处理事件响应，例如 [NIST](https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-61r2.pdf) 事件响应标准，该标准已成为事件响应的领先行业标准之一。

NIST 四步事件响应流程包括四个阶段：

1.  准备
2.  检测和分析
3.  包含、消除和恢复
4.  事件后活动

### <a name="example-tracking-preparation-phase-activity"></a>示例：跟踪准备阶段活动

升级操作手册的核心基础之一是确保每个 SOC 团队在事件或事件之前、期间和之后应执行哪些操作没有任何歧义。 因此，最佳做法是列出分步说明。 

例如，准备阶段可能包括任务的 if/then 或 XoR 矩阵。 对于新的网络钓鱼变体示例用例，此类矩阵可能如下所示：

| 为什么保证升级？ | 后续步骤 |
|:-------|:-----|
| SOC 监控中警报的级别 **为关键** 触发> **500/小时** | 转到 Playbook A， Section 2， Activity 5 (with a link to the playbook section)  |
| eCommerce 报告的潜在 DDoS 攻击 | 调用 Playbook B-Section C， Activity 19 (with a link to the playbook section)  |
| 管理层将可疑电子邮件报告为网络钓鱼尝试 | Go to Playbook 5， Section 2， Activity 5 (with a link to the playbook section)  |
|||

执行准备阶段后，组织应调用 NIST 概述的剩余阶段：

- 检测和分析
- 包含、消除和恢复
- 事件后活动 

## <a name="next-step"></a>后续步骤

[步骤 6.确定 SOC 维护任务](integrate-microsoft-365-defender-secops-tasks.md)

