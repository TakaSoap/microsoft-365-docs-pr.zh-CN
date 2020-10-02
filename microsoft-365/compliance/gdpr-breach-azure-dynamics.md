---
title: GDPR 下的 Azure 和 Dynamics 365 泄露通知
description: 介绍了 Azure 和 Dynamics 365 如何避免个人数据泄露，以及 Microsoft 如何在出现数据泄露时响应和通知用户。
keywords: Azure、Microsoft 365、Dynamics 365、Microsoft 365 文档、GDPR
localization_priority: Priority
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: c262e496313ec5f59e9e369d8622f4698a9a585a
ms.sourcegitcommit: 888b9355ef7b933c55ca6c18639c12426ff3fbde
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/29/2020
ms.locfileid: "48305196"
---
# <a name="azure-and-dynamics-365-breach-notification-under-the-gdpr"></a>GDPR 下的 Azure 和 Dynamics 365 泄露通知

Microsoft Azure 认真遵守《一般数据保护条例》(GDPR) 规定的义务。Microsoft Azure 采取全面的安全措施来防止数据泄露。这些措施包括物理和逻辑安全控制以及自动化安全流程、全面的信息安全和隐私策略，以及针对所有人员的安全和隐私培训。

安全从[安全开发生命周期](https://www.microsoft.com/sdl/)开始就内置于 Microsoft Azure 中，这是一个融合了“通过设计保护隐私”和“默认保护隐私”方法的强制性开发过程。Microsoft 的安全策略指导原则是"假定泄露"，这是深层防护策略的扩展。通过不断挑战 Azure 的安全功能，Microsoft 能够了解新兴威胁。有关 Azure 安全的详细信息，请查看这些[资源](https://www.microsoft.com/trustcenter/security/azure-security)。

Microsoft 拥有全球性的全天候事件响应服务，努力减轻针对 Microsoft Azure 的攻击所造成的影响。Microsoft 通过了多项安全性和合规性审核 (例如 [ISO/IEC 27018](offering-iso-27018.md)) 的检验，在其数据中心使用严格的操作和流程来防止未经授权的访问，包括全天候视频监控、经过培训的安全人员、智能卡和生物识别控制。

## <a name="detection-of-potential-breaches"></a>检测潜在泄露

由于现代云计算的特性，客户云环境中发生的所有数据泄露并非都涉及 Microsoft Azure 服务。 Microsoft 采用了 Azure 服务的共享责任模型来定义安全和操作责任。 共享责任在讨论云服务的安全性时非常重要，因为云服务提供商和客户都对云安全性有部分负责。

Microsoft 不会监控或响应属于客户责任范围的安全事件。仅限客户的漏洞不会作为 Azure 安全事件进行处理，将需要客户租户来管理响应工作。如果指定了适当的服务联系人，客户事件响应部门也可能会与 Microsoft Azure [客户支持](https://azure.microsoft.com/support/options/)部门进行协作。Microsoft Azure 还提供各种服务（例如 [Azure 安全中心](https://azure.microsoft.com/services/security-center/)），客户可以用来开发和管理安全事件响应。

Azure 根据安全事件响应流程响应潜在数据泄露，该流程属于 Microsoft Azure 事件管理计划的一部分。Azure 安全事件响应使用五阶段流程来实现：检测、评估、诊断、稳定和关闭。随着调查的进展，安全事故响应团队可能在诊断和稳定阶段之间切换。安全事件响应流程概述如下：

|**Stage**|**说明**|
| ------- | ------------- |
| ***1 — 检测*** | 潜在事件的第一个指征。 |
| ***2 — 评估*** | 时刻待命的事件响应团队成员评估事件的影响和严重性。根据证据，评估可能会也可能不会导致进一步向安全响应团队上报。 |
| ***3 — 诊断*** | 安全响应专家开展技术或鉴证调查，确定遏制、缓解和解决方法策略。 如果安全团队认为非法或未经授权的个人可能接触到了客户数据，将开始并行执行客户事件通知流程。 |
| ***4 — 稳定和恢复*** | 事件响应团队创建恢复计划以缓解问题。将立即执行危机遏制步骤。例如隔离受影响的系统，同时进行诊断。在即时风险过去之后，还会规划更长期的缓解措施。 |
| ***5 — 关闭和事后分析*** | 事件响应团队创建事后分析，其中会列出事件详情，目的是修改策略、过程和流程，以防事件再次发生。 |

[《云中的 Microsoft Azure 安全响应》](https://gallery.technet.microsoft.com/Azure-Security-Response-in-dd18c678)白皮书进一步详细介绍了 Microsoft 如何在 Azure 内调查、管理和响应安全事件。

Microsoft Azure 使用的检测流程旨在发现威胁 Azure 服务机密性、完整性和可用性的事件。多个事件可能会触发调查：

- 通过内部监控和警报框架自动发出系统警报。 这些警报采用反恶意软件和入侵检测等基于签名的警报的形式提供，或者通过专为分析发生异常时的预期活动和警报而设计的算法来提供。
- 来自 Microsoft Azure 和 Azure 政府版上运行的 Microsoft 服务的第一方报告。
- 通过[secure@microsoft.com](mailto:secure@microsoft.com)将安全漏洞报告给 [Microsoft 安全响应中心 (MSRC)](https://technet.microsoft.com/security/dn440717)。 MSRC 与全球的合作伙伴和安全研究机构合作，帮助预防安全事件和提高 Microsoft 产品安全性。
- 通过[客户支持门户](https://www.windowsazure.com/support/contact/)或 Microsoft Azure 和 Azure 政府版管理门户提供的客户报告，其中描述了归因于 Azure 基础结构的可疑活动（与客户的责任范围内发生的活动相对）。
- 安全[红队和蓝队](https://azure.microsoft.com/blog/red-teaming-using-cutting-edge-threat-simulation-to-harden-the-microsoft-enterprise-cloud/)活动。 此策略使用训练有素的红队攻击性 Microsoft 安全专家来发现和攻击 Azure 服务中的潜在弱点。 安全响应蓝队必须检测并防御红队的活动。 红队和蓝队操作都用于验证 Azure 安全响应工作是否有效地管理安全事件。 安全红队和蓝队根据参与规则开展活动，以有助于确保对客户数据的保护。
- 由 Azure 服务操作人员进行升级。 Microsoft 员工经过培训，可识别和上报潜在安全问题。

## <a name="azures-data-breach-response"></a>Azure 的数据泄露响应

Microsoft 通过确定事件的功能影响、可恢复性和信息影响，为调查分配相应的优先级和严重性级别。 随着调查的进行，优先级和严重性都可能会基于新发现和结论而发生改变。 即将发生或已确认的客户数据风险安全事件被视为高严重性，需要全天候解决。 

Microsoft Azure 将事件的信息影响归类为以下泄露类别：

| **类别**             | **定义**                                                                                                                   |
| ------------------------ | -------------------------------------------------------------------------------------------------------------------------------- |
| ***无***               | 没有泄露、更改、删除或以其他方式破坏任何信息。                                                      |
| ***隐私泄露***     | 纳税人、员工、受益人等的敏感个人数据被访问或泄露。                                |
| ***专有信息泄露*** | 受保护的关键基础机构信息 (PCII) 等未分类专有信息被访问或泄露。 |
| ***完整性损失***     | 敏感信息或专有信息被更改或删除。                                                                     |

安全响应团队与 Microsoft Azure 安全工程师和 SME 一起，基于从证据得出的事实性数据对事件进行分类。安全事件可分类为：

- **误报**：符合检测条件的事件被发现属于正常业务惯例，可能需要进行筛选。 服务团队将确定误报的根本原因，并将根据需要通过系统化方式使用检测源并对其进行微调，以解决这些问题。
- **安全事件**：非法访问存储在 Microsoft 设备或 Microsoft 设施上的任何客户数据或支持数据，或者未经授权访问此类设备或设施从而导致客户数据或支持数据丢失、泄露或改动的事件。
- **客户可报告的安全/隐私事件 (CRSPI)**：非法或未经授权访问或使用 Microsoft 的系统、设备或设施从而导致客户数据泄露、修改或丢失。
- **隐私泄露**：涉及个人数据的安全事件的子类型。 处理过程与安全事件没有区别。

对于要声明的 CRSPI，Microsoft 必须确定已经或可能已经发生对客户数据的未经授权访问，和/或存在必须发出通知的法律或合同承诺。 需要知道特定的客户影响、资源访问和修复步骤，但这不是必需的。 事件通常在安全事件的诊断阶段结束后声明为 CRSPI。 但是，声明可能会在所有相关信息可用的任何时候发生。 安全事件经理必须无可置疑地证明发生了可报告事件，以开始执行客户事件通知流程。

在整个调查过程中，安全响应团队与全球法律顾问密切合作，帮助确保取证是根据法律义务和对客户的承诺来执行的。对于各种操作环境中系统和客户数据的查看和处理，还存在重大限制。敏感或机密数据以及客户数据不会转移出生产环境，除非有事件经理的明确书面批准，且记录在对应的事件票证中。

Microsoft 验证是否成功遏制了客户和业务风险并实施了纠正措施。如有必要，会采取紧急缓解步骤来解决与事件直接关联的安全风险。

Microsoft 还会完成数据泄露的内部事后分析。 作为此练习的一部分，会评估响应和操作过程的充分性，并识别和实施安全事件响应 SOP 或相关流程所必需的任何更新。 数据泄露的内部事后分析是高度机密的记录，不会提供给客户。 但是，会汇总事后分析并将其包括在其他客户事件通知中。 作为 Azure 例行审核周期的一部分，会将这些报告提供给外部审计机构进行审阅。

## <a name="customer-notification"></a>客户通知

Microsoft Azure 会根据需要将数据泄露通知客户和监管机构。Microsoft 在 Azure 服务的操作中依赖于大量的内部分隔。数据流日志也很可靠。此设计的一个优点是，大多数事件可以仅限于特定客户。目的是在数据遭到泄漏时向受影响的客户提供准确、可操作和及时的通知。

声明 CRSPI 后，通知过程将尽快进行，同时仍然考虑快速移动的安全风险。 通常，在进行事件调查时，会就发生起草通知的过程。 我们会在声明泄露之时起的 72 小时内送达客户通知，但以下情况*除外*：

- Microsoft 认为通知操作会增加其他客户面临的风险。 例如，发送通知可能向对手预警，导致无法进行补救。
- 经 Microsoft 的法律部门公司外部和法律事务部 (CELA) 和行政事件经理审查的其他异常或极端情况。
- 72 小时时间线可能会留下一些可用的事件详细信息。 调查过程中，这些将提供给客户和管理机构。

Microsoft Azure 向客户提供详细信息，使他们能够执行内部调查，并协助其履行最终用户承诺，而不是过度地延迟通知流程。

个人数据泄露通知将通过 Microsoft 选择的任何途径送达客户，包括通过电子邮件。 数据泄露通知会送达 Azure 安全中心提供的安全联系人列表，该列表可根据[实施指导原则](https://docs.microsoft.com/azure/security-center/security-center-provide-security-contact-details)进行配置。 如果 Azure 安全中心未提供联系人信息，通知发送给 Azure 订阅中的一个或多个管理员。 为确保通知成功送达，客户有责任确保每个适用订阅和在线服务门户上管理员联系信息的正确性。

Microsoft Azure 或 Azure 政府版团队还可能选择通知其他 Microsoft 人员，例如客户服务 (CSS) 和客户的客户经理 (AM) 或技术客户经理 (TAM)。 这些人员通常与客户关系密切，因此可加速补救过程

## <a name="microsoft-dynamics-365-built-in-security-features"></a>Microsoft Dynamics 365 内置安全功能

Microsoft Dynamics 365 利用云服务基础结构和内置安全功能，使用安全措施和机制来保护数据。此外，Dynamics 365 还提供了高效的数据访问以及在以下方面与数据完整性及隐私性的协作：[安全标识、数据保护、基于角色的安全性和威胁管理](https://www.microsoft.com/trustcenter/security/dynamics365-security)。

Microsoft Dynamics 365 服务遵循 Microsoft Azure 针对防御数据泄露流程采取的相同技术和组织措施。 所以，“Microsoft Azure 数据泄露”通知文档中记录的任何信息也与 Microsoft Dynamics 365 服务类似。

## <a name="learn-more"></a>了解更多

[Microsoft 信任中心](https://www.microsoft.com/trust-center/privacy/gdpr-overview)
