---
title: 准备 Microsoft Defender for Endpoint 部署
description: 为部署 Microsoft Defender for Endpoint 准备利益干系人审批、日程表、环境注意事项和采用顺序
keywords: 部署， 准备， 利益干系人， 时间线， 环境， 终结点， 服务器， 管理， 采用
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-endpointprotect
- m365solution-scenario
ms.topic: article
ms.technology: mde
ms.openlocfilehash: f171bd8ce62e8e3d3b35c8dbab6740ad62b172fd
ms.sourcegitcommit: 986ea76ecaceb5fe6b9616e553003e3c5b0df2e7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/25/2022
ms.locfileid: "62214185"
---
# <a name="prepare-microsoft-defender-for-endpoint-deployment"></a>准备 Microsoft Defender for Endpoint 部署

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 希望体验 Microsoft Defender for Endpoint？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)。

部署适用于终结点的 Defender 的过程分三个阶段：

|![部署阶段 - 准备。](images/phase-diagrams/prepare.png)<br>阶段 1：准备|[![部署阶段 - 设置](images/phase-diagrams/setup.png)](production-deployment.md)<br>[阶段 2：设置](production-deployment.md)|[![部署阶段 - 载入](images/phase-diagrams/onboard.png)](onboarding.md)<br>[阶段 3：开始使用](onboarding.md)|
|---|---|---|
|*你在这里！*|||

您当前处于准备阶段。

准备是任何成功部署的关键。 本文将指导你在准备部署适用于终结点的 Defender 时需要考虑的要点。

## <a name="stakeholders-and-approval"></a>利益干系人与审批

以下部分用于确定项目所涉及的所有利益干系人，并需要批准、审阅或随时了解情况。

根据组织需要，将利益干系人添加到下表。

- SO = 批准项目
- R = 查看此项目并提供输入
- I = 已通知此项目

<br>

****

|名称|Role|操作|
|---|---|---|
|输入名称和电子邮件|**首席信息安全 (CISO)** 一名执行代表，他作为新技术部署 *的组织内部发起人。*|SO|
|输入名称和电子邮件|**网络防御操作中心 (CDOC)** CDOC 团队的代表，负责定义此更改如何与客户安全运营团队中的流程 *保持一致。*|SO|
|输入名称和电子邮件|**安全** 架构师 来自安全团队的代表，负责定义此更改如何与组织中 *的核心安全体系结构保持一致。*|R|
|输入名称和电子邮件|**工作区** 架构师 来自 IT 团队的代表，负责定义此变更如何与组织中的核心 *工作场所体系结构保持一致。*|R|
|输入名称和电子邮件|**安全***分析师 来自 CDOC* 团队的代表，可以从安全操作角度提供有关此更改的检测功能、用户体验和整体实用性的输入。|I|
||||

## <a name="environment"></a>环境

本节用于确保利益干系人深入理解您的环境，这有助于确定技术或流程所需的潜在依赖关系和/或更改。

<br>

****

|什么|说明|
|---|---|
|终结点计数|按操作系统表示的终结点总数。|
|服务器计数|按操作系统版本表示的服务器总数。|
|管理引擎|管理引擎名称和版本 (例如，System Center Configuration Manager Current Branch 1803) 。|
|CDOC 分发|高级 CDOC 结构 (，例如，第 1 层外包到 Contoso，第 2 层和 3 层内部分布于欧洲和亚洲) 。|
|SIEM 安全 (事件) |使用的 SIEM 技术。|
|||

## <a name="role-based-access-control"></a>基于角色的访问控制

Microsoft 建议使用最小特权的概念。 Defender for Endpoint 利用内置角色Azure Active Directory。 Microsoft [建议查看可用的不同角色](/azure/active-directory/roles/permissions-reference) ，并选择适当的角色来解决你对此应用程序的每个角色的需求。 一些角色可能需要在部署完成后临时应用和删除。

<br>

****

|Personas|角色|Azure AD需要 (角色角色) |分配到|
|---|---|---|---|
|安全管理员||||
|安全分析师||||
|终结点管理员||||
|基础结构管理员||||
|业务所有者/利益干系人||||
|

Microsoft[建议使用Privileged Identity Management](/azure/active-directory/active-directory-privileged-identity-management-configure)管理角色，为具有目录权限的用户提供额外的审核、控制和访问评审。

Defender for Endpoint 支持两种权限管理方法：

- **基本权限管理**：将权限设置为完全访问或只读。 具有全局管理员或安全管理员角色的用户Azure Active Directory完全访问权限。 安全读取者角色具有只读访问权限，不授予查看计算机/设备清单的访问权限。

- 基于角色的访问控制 **(RBAC) ：** 通过定义角色、将 Azure AD 用户组分配给角色并授予用户组对设备组的访问权限来设置粒度权限。 有关详细信息。 请参阅 [使用基于角色的访问控制管理门户访问](rbac.md)。

Microsoft 建议利用 RBAC 来确保只有具有业务理由的用户才能访问 Defender for Endpoint。

你可以在此处找到有关权限准则的详细信息：[创建角色并将角色分配给Azure Active Directory组](/microsoft-365/security/defender-endpoint/user-roles#create-roles-and-assign-the-role-to-an-azure-active-directory-group)。

以下示例表用于标识环境中的网络防御操作中心结构，该结构将帮助您确定环境所需的 RBAC 结构。

<br>

****

|层|说明|所需的权限|
|---|---|---|
|第 1 层|**本地安全运营团队/IT 团队** <p> 此团队通常会会审并调查其地理位置中包含的警报，并上报至第 2 层（如果需要进行主动修正）。||
|第 2 层|**区域安全运营团队** <p> 此团队可以看到其区域的所有设备并执行修正操作。|查看数据|
|第 3 层|**全球安全运营团队** <p> 此团队由安全专家组成，有权查看并执行门户的所有操作。|查看数据 <p> 警报调查 活动修正操作 <p> 警报调查 活动修正操作 <p> 管理门户系统设置 <p> 管理安全设置|
||||

## <a name="adoption-order"></a>采用顺序

在许多情况下，组织将拥有现有的终结点安全产品。 每个组织至少应该是防病毒解决方案。 但在某些情况下，组织可能还已经EDR解决方案。

过去，由于与应用程序层和基础结构依赖项的紧密关联，替换任何安全解决方案会非常耗时且难以实现。 但是，由于 Defender for Endpoint 内置于操作系统中，因此替换第三方解决方案现在很容易实现。

选择要使用的 Defender for Endpoint 组件并删除不适用的组件。 下表指示 Microsoft 建议如何启用终结点安全套件的顺序。

<br>

****

|组件|说明|采用顺序排名|
|---|---|---|
|终结点检测&响应 (EDR) |Defender for Endpoint endpoint detection and response capabilities provide advanced attack detections that are near real-time and actionable. 安全分析员可以有效地确定警报的优先级，了解整个泄露范围，并采取响应措施来修正威胁。 <p> [了解详细信息。](/windows/security/threat-protection/windows-defender-atp/overview-endpoint-detection-response)|1|
|TVM &威胁 (漏洞管理) |威胁&漏洞管理是 Microsoft Defender for Endpoint 的一个组件，可为安全管理员和安全运营团队提供独特的价值，包括： <ul><li>与终结点漏洞相关的实时终结点检测和响应（EDR）见解</li><li>事件调查期间有价值的设备漏洞上下文</li><li>内置的修正过程通过 Microsoft Intune 和 Microsoft System Center Configuration Manager</li></ul> <p> [了解详细信息](https://techcommunity.microsoft.com/t5/Windows-Defender-ATP/Introducing-a-risk-based-approach-to-threat-and-vulnerability/ba-p/377845)。|2|
|NGP (下一代) |Microsoft Defender 防病毒内置反恶意软件解决方案，可为台式机、便携计算机和服务器提供下一代保护。 Microsoft Defender 防病毒包括以下功能： <ul><li>云提供的保护功能，用于近乎即时地检测和阻止新出现的威胁。 在机器学习和 Intelligent Security Graph 功能的基础上，Microsoft Defender 防病毒的下一代技术包括云提供的保护功能。</li><li>始终使用高级文件和进程行为监视以及其他启发式扫描 (也称为"实时保护") 。</li><li>基于机器学习、人工和自动化大数据分析，以及深入的威胁抵御研究的专用保护更新。</li></ul> <p> [了解详细信息](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10)。|3|
|攻击面减少 (ASR) |Microsoft Defender for Endpoint 中的攻击面减少功能可帮助保护组织的设备和应用程序免受新的和新出现的威胁。 <br> [了解详细信息。](/windows/security/threat-protection/windows-defender-atp/overview-attack-surface-reduction)|4|
|AIR &自动 (修正) |Microsoft Defender for Endpoint 使用自动调查显著减少需要单独调查的警报数量。 自动调查功能利用各种检查算法和分析人员 (例如) 手册）来检查警报并立即采取修正措施来解决违规问题。 这将极大地减少警报量，使安全操作专家能够专注于更复杂的威胁和其他高价值计划。 <p> [了解详细信息。](/windows/security/threat-protection/windows-defender-atp/automated-investigations-windows-defender-advanced-threat-protection)|不适用|
|Microsoft 威胁专家 (MTE) |Microsoft 威胁专家是一项托管搜寻服务，可为安全操作中心 (SOC) 提供专家级别的监视和分析，以帮助他们确保不会错过独特环境中的关键威胁。 <p> [了解详细信息。](/windows/security/threat-protection/windows-defender-atp/microsoft-threat-experts)|不适用|

## <a name="next-step"></a>后续步骤

![阶段 2：设置。](images/setup.png) <br> [阶段 2：设置](production-deployment.md)

设置 Microsoft Defender for Endpoint 部署。
