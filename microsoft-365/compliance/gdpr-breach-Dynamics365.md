---
title: Dynamics 365 与 GDPR 泄露通知
description: 介绍了 Dynamics 365 如何避免个人数据泄露，以及 Microsoft 如何在出现数据泄露时响应和通知用户。
keywords: Dynamics 365, Microsoft 365, Microsoft 365 教育版, Microsoft 365 文档, GDPR
localization_priority: Priority
ms.prod: Microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection:
- GDPR
- M365-security-compliance
titleSuffix: Microsoft GDPR
ms.openlocfilehash: ff0a6c7a0a6d8e82110daa7d7e294ce16aa8e2db
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "41594462"
---
# <a name="dynamics-365-and-breach-notification-under-the-gdpr"></a>Dynamics 365 与 GDPR 泄露通知

Dynamics 365 认真遵守《一般数据保护条例》(GDPR) 规定的义务并采取全面的安全措施来防止数据泄露。 Microsoft 努力持续为 Dynamics 365 客户提供高度安全的企业级服务。 本节中的信息概述了 Microsoft Dynamics 365 如何防范安全事件/数据泄露，以及我们响应并通知我们的客户时所遵循的流程。

## <a name="microsoft-dynamics-365-built-in-security-features"></a>Microsoft Dynamics 365 内置安全功能

Microsoft Dynamics 365 利用云服务基础结构和内置安全功能，使用安全措施和机制来保护数据。此外，Dynamics 365 还提供了高效的数据访问以及在以下方面与数据完整性及隐私性的协作：[安全标识、数据保护、基于角色的安全性和威胁管理](https://www.microsoft.com/trustcenter/security/dynamics365-security)。

## <a name="incident-response-training"></a>事件响应培训

使用 Microsoft Dynamics 365 的每个员工都要接受适合其角色的有关安全事件和响应过程的培训。每个 Microsoft Dynamics 365 员工在入职时都会接受培训，此后每年还会接受年度进修培训。该培训旨在让员工对 Microsoft 的方法有基本的了解，以便在培训完成时，所有员工都了解：

- 安全事件的定义；
- 所有员工报告安全事件的责任；
- 如何向 Dynamics 365 安全事件响应团队上报潜在安全事件；
- Dynamics 365 安全事件响应团队如何响应安全事件；
- 有关隐私尤其是客户隐私的特别问题；
- 查找有关安全性和隐私性的其他信息的位置，以及上报联系人。

## <a name="how-does-microsoft-dynamics-365-define-security-incidentpotential-breaches"></a>Microsoft Dynamics 365 如何定义安全事件/潜在泄露

安全事件/数据泄露是指非法访问存储在 Microsoft 设备或 Microsoft 设施中的客户数据或未经授权访问此类设备或设施从而可能导致客户数据丢失、泄露或改动等事件。Microsoft 在安全事件/数据泄露响应方面的目标是保护客户数据和 Dynamics 365 服务。Microsoft 管理安全事件的方法符合[国家标准和技术](https://www.nist.gov/) (NIST) 特殊出版物 (SP) [800-61](https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-61r2.pdf)。

Microsoft 不会监控或响应属于客户责任范围的安全事件。仅限客户的漏洞不会作为 Dynamics 365 安全事件进行处理，将需要客户租户来管理响应工作。如果指定了适当的服务联系人，客户事件响应部门也可能会与 Microsoft Dynamics 365 客户支持部门进行协作。

## <a name="detection-of-potential-breaches"></a>检测潜在泄露

Dynamics 365 根据安全事件响应流程响应潜在数据泄露，该流程属于 Microsoft Dynamics 365 事件管理计划的一部分。Dynamics 365 安全事件响应使用五阶段流程来实现：检测、评估、诊断、稳定和关闭。随着调查的进展，安全事故响应团队可能在诊断和稳定阶段之间切换。安全事件响应流程概述如下：

|**阶段**|**说明**|
|:-----|:-----|
| ***1 - 检测*** | 潜在事件的第一个指征。 |
| ***2 - 评估*** | 时刻待命的事件响应团队成员评估事件的影响和严重性。根据证据，评估可能会也可能不会导致进一步向安全响应团队上报。 |
| ***3 - 诊断*** | 安全响应专家开展技术或鉴证调查，确定遏制、缓解和解决方法策略。 如果安全团队认为非法或未经授权的个人可能接触到了客户数据，将开始并行执行客户事件通知流程。|
| ***4 - 稳定和恢复*** | 事件响应团队创建恢复计划以缓解问题。将立即执行危机遏制步骤。例如隔离受影响的系统，同时进行诊断。在即时风险过去之后，还会规划更长期的缓解措施。 |
| ***5 - 关闭和事后分析*** | 事件响应团队创建事后分析，其中会列出事件详情，目的是修改策略、过程和流程，以防事件再次发生。 |

[《Dynamics 安全事件管理》](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=266d445f-ea95-42de-9124-4b2118a639ee&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers)白皮书进一步详细介绍了 Microsoft 如何在 Dynamics 365 内调查、管理和响应安全事件。

Microsoft Dynamics 365 使用的检测流程旨在发现威胁 Dynamics 365 服务机密性、完整性和可用性的事件。多个事件可能会触发调查：

- 自动化系统通过内部监控和警报框架发出警报。这些警报采用反恶意软件和入侵检测等基于签名的警报的形式提供，或者通过专为分析发生异常时的预期活动和警报而设计的算法来提供。
- 来自部署在公有云中的 Microsoft Dynamics 365 服务和部署在主权云中的 Microsoft Dynamics 365 服务的第一方报告。
- 通过 <secure@microsoft.com> 将安全漏洞报告给 [Microsoft 安全响应中心 (MSRC)](https://technet.microsoft.com/security/dn440717)。MSRC 与全球的合作伙伴和安全研究机构合作，帮助预防安全事件和提高 Microsoft 产品安全性。
- 描述归因于 Microsoft Dynamics 365 服务的可疑活动（与客户责任范围内发生的活动相对）的客户报告。
- 安全[红队和蓝队](https://azure.microsoft.com/blog/red-teaming-using-cutting-edge-threat-simulation-to-harden-the-microsoft-enterprise-cloud/)活动。 此策略使用训练有素的红队攻击性安全专家来发现和攻击 Microsoft Dynamics 365 服务中的潜在弱点。 安全响应蓝队必须检测并防御红队的活动。 红队和蓝队操作都用于验证 Microsoft Dynamics 365 安全响应工作是否有效地管理安全事件。 安全红队和蓝队根据责任要求开展活动，以有助于确保对客户数据的保护。
- Microsoft Dynamics 365 服务运营商的上报。 Microsoft 员工经过培训，可识别和上报潜在安全问题。

## <a name="microsoft-dynamics-365-data-breach-response"></a>Microsoft Dynamics 365 数据泄露响应

Microsoft 将通过确定功能影响、可恢复性和事件的信息影响来调查相应的优先级和严重性级别。随着调查的进行，优先级和严重性可能会基于新发现和结论而发生更改。涉及客户数据所面临的即将发生或已确认的风险的安全事件视为具有高严重性，全天候进行解决。Microsoft Dynamics 365 将隐私泄露定义为“联机服务最终用户或 Microsoft 员工的个人数据”的泄露。

安全响应团队与 Microsoft Dynamics 365 安全工程师和主题专家 (SME) 一起，基于从证据得出的事实性数据对事件进行分类。安全事件可分类为：

- **误报：** 符合检测条件的事件被发现属于正常业务惯例，可能需要进行筛选。 服务团队将确定误报的根本原因，并将根据需要通过系统化方式利用检测源并对其进行微调，以解决这些问题。
- **安全事件：** 非法访问存储在 Microsoft 设备或 Microsoft 设施上的任何客户数据或支持数据，或者未经授权访问此类设备或设施从而导致客户数据或支持数据丢失、泄露或改动的事件。
- **客户可报告的安全/隐私事件 (CRSPI)：** 非法或未经授权访问或使用 Microsoft 的系统、设备或设施从而导致客户数据泄露、修改或丢失。
- **隐私事件：** 涉及个人数据的安全事件的子类型。 处理过程与安全事件没有区别。

对于要声明的 CRSPI，Microsoft 必须确定已经或很可能已经发生对客户数据的未经授权访问，和/或存在必须发出通知的法律或合同承诺。 需要知道特定的客户影响、资源访问和修复步骤，但这不是必需的。 事件通常在安全事件的诊断阶段结束后声明为 CRSPI。 但是，声明可能会在所有相关信息可用的任何时候发生。 安全事件经理必须无可置疑地证明发生了可报告事件，以开始执行客户事件通知流程。

在整个调查过程中，安全响应团队与全球法律顾问密切合作，帮助确保取证是根据法律义务和对客户的承诺来执行的。对于各种操作环境中系统和客户数据的查看和处理，还存在重大限制。敏感或机密数据以及客户数据不会转移出生产环境，除非有事件经理的明确书面批准，且记录在对应的事件票证中。

Microsoft 验证是否成功遏制了客户和业务风险并实施了纠正措施。如有必要，会采取紧急缓解步骤来解决与事件直接关联的安全风险。

Microsoft 还会完成数据泄露的内部事后分析。 作为此练习的一部分，会评估响应和操作过程的充分性，并识别和实施 Microsoft 内部安全策略或相关流程所必需的任何更新。 数据泄露的内部事后分析是高度机密的记录，不会提供给客户。 但是，会汇总事后分析并将其包括在其他客户事件通知中。 作为 Dynamics 365 例行审核周期的一部分，会将这些报告提供给外部审计机构进行审阅。

## <a name="customer-notification"></a>客户通知

Microsoft Dynamics 365 会根据需要将数据泄露通知客户和监管机构。Microsoft 在 Dynamics 365 服务的操作中依赖于大量的内部分隔。数据流日志也很可靠。此设计的一个优点是，大多数事件可以仅限于特定客户。目的是在数据遭到泄漏时向受影响的客户提供准确、可操作和及时的通知。

声明 CRSPI 后的通知过程将尽快进行，同时仍然考虑快速移动的安全风险。 通常，在进行事件调查时，会就发生起草通知的过程。 我们会在声明泄露时立即送达客户通知，但以下情况*除外*：

- Microsoft 认为通知操作将增加其他客户面临的风险。例如，发送通知可能向对手预警，导致无法进行补救。
- 经 Microsoft 的法律部门和行政事件经理审查的其他异常或极端情况。

Microsoft Dynamics 365 向客户提供详细信息，使他们能够执行内部调查，并协助其履行最终用户承诺，而不是过度地延迟通知流程。

个人数据泄露通知将通过 Microsoft 选择的任何途径送达客户，包括通过电子邮件。数据泄露通知会送达 Office 安全中心提供的客户联系人/管理员列表（仅受影响的租户），该列表可由客户/租户管理员配置。为确保通知成功送达，客户有责任确保每个适用订阅和在线服务门户上管理员联系信息的正确性。

Microsoft Dynamics 365 团队还可能选择通知其他 Microsoft 人员，例如客户服务 (CSS) 和客户的客户经理 (AM) 或技术客户经理 (TAM)。 这些人员通常与客户关系密切，因此可加速补救过程。

## <a name="learn-more"></a>了解更多

- [Microsoft 信任中心](https://www.microsoft.com/TrustCenter/Privacy/gdpr/default.aspx)