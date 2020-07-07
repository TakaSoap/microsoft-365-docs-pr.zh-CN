---
title: 符合 GDPR 的 Windows 通知数据处理者服务
description: 介绍了 Windows 数据处理者服务如何避免个人数据泄露，以及 Microsoft 如何在出现数据泄露时响应和通知用户。
keywords: Windows 数据处理者服务, Microsoft 365, Microsoft 365 文档, GDPR
localization_priority: Priority
ROBOTS: NOINDEX, NOFOLLOW
ms.prod: Microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: daniha
author: DaniHalfin
manager: dansimp
audience: itpro
ms.collection:
- GDPR
- M365-security-compliance
ms.openlocfilehash: bfadeae0f4f0b01197f58f0610d1040da3080922
ms.sourcegitcommit: 3ddcf08e8deec087df1fe524147313f1cb12a26d
ms.contentlocale: zh-CN
ms.lasthandoff: 07/02/2020
ms.locfileid: "45023594"
---
# <a name="data-processor-service-for-windows-breach-notification-under-the-gdpr"></a>符合 GDPR 的 Windows 泄露通知数据处理者服务

>[!NOTE]
>本主题面向 Windows 预览程序的数据处理者服务的参与者，并且需要接受特定的使用条款。 若要了解有关计划的详细信息并同意使用条款，请参阅 [https://aka.ms/dpswpublicpreview](https://aka.ms/dpswpublicpreview)。

Microsoft 的 Windows 数据处理者服务严格履行《一般数据保护条例》(GDPR) 规定的义务。 Microsoft 的 Windows 数据处理者服务采取大量安全措施来防止数据泄露， 其中包括主动预测、防御和减少恶意访问的专业威胁管理团队。内部安全措施，例如端口扫描、外围漏洞扫描和入侵检测、检测并阻止恶意访问，以及自动化安全流程、全面的信息安全和隐私策略，以及针对所有人员的安全和隐私培训。 

安全从[安全开发生命周期](https://www.microsoft.com/sdl/)开始就内置于 Microsoft 的 Windows 数据处理者服务中，这是一个融合了“通过设计保护隐私”和“默认保护隐私”方法的强制性开发过程。 Microsoft 的安全策略指导原则是"假定泄露"，这是深层防护策略的扩展。 通过不断挑战 Windows 数据处理者服务的安全功能，Microsoft 能够了解新兴威胁。 有关 Windows 数据处理者安全的详细信息，请查看这些[资源](https://www.microsoft.com/TrustCenter/Security/windows10-security)。Windows 的数据处理者服务根据安全事件响应流程来响应潜在数据泄露。 Windows 数据处理者服务通过五个阶段的流程实施安全事件响应：检测、评估、诊断、稳定和关闭。 随着调查的进行，安全事件响应小组可能会在诊断阶段和稳定阶段之间轮换。 安全事件响应流程概述如下： 

|**Stage**|**说明**|
| ------- | ------------- |
| ***1 — 检测*** | 潜在事件的第一个指征。 |
| ***2 — 评估*** | An on-call incident response team member assesses the impact and severity of the event. Based on evidence, the assessment may or may not result in further escalation to the security response team. |
| ***3 — 诊断*** | 安全响应专家开展技术或鉴证调查，确定遏制、缓解和解决方法策略。 如果安全团队认为非法或未经授权的个人可能接触到了客户数据，将开始并行执行客户事件通知流程。 |
| ***4 — 稳定和恢复*** | The incident response team creates a recovery plan to mitigate the issue. Crisis containment steps such as quarantining impacted systems may occur immediately and in parallel with diagnosis. Longer term mitigations may be planned which occur after the immediate risk has passed. |
| ***5 — 关闭和事后分析*** | 事件响应团队创建事后分析，其中会列出事件详情，目的是修改策略、过程和流程，以防事件再次发生。 |

Microsoft 的 Windows 数据处理者服务使用的检测流程旨在发现威胁 Windows 数据处理者服务机密性、完整性和可用性的事件。 多个事件可能会触发调查： 

 - 通过内部监控和警报框架自动发出系统警报。 这些警报采用反恶意软件和入侵检测等基于签名的警报的形式提供，或者通过专为分析发生异常时的预期活动和警报而设计的算法来提供。
 - 来自 Microsoft Azure 和 Azure 政府版上运行的 Microsoft 服务的第一方报告。
 - 通过 [secure@microsoft.com] (mailto:secure@microsoft.com) 将安全漏洞报告给 [Microsoft 安全响应中心 (MSRC)](https://technet.microsoft.com/security/dn440717)。 MSRC 与全球的合作伙伴和安全研究机构合作，帮助预防安全事件和提高 Microsoft 产品安全性。
 - 通过客户支持门户或 Microsoft Azure 和 Azure 政府版管理门户提供的客户报告，其中描述了归因于 Azure 基础结构的可疑活动（与客户的责任范围内发生的活动相对）。
 - 安全[红队和蓝队](https://azure.microsoft.com/blog/red-teaming-using-cutting-edge-threat-simulation-to-harden-the-microsoft-enterprise-cloud/)活动。 此策略使用训练有素的红队攻击性 Microsoft 安全专家来发现和攻击 Azure 服务中的潜在弱点。 安全响应蓝队必须检测并防御红队的活动。 红队和蓝队操作都用于验证 Azure 安全响应工作是否有效地管理安全事件。 安全红队和蓝队根据参与规则开展活动，以有助于确保对客户数据的保护。
 - 由 Azure 服务操作人员进行升级。 Microsoft 员工经过培训，可识别和上报潜在安全问题。

 ## <a name="data-processor-service-for-windows-data-breach-response"></a>Windows 数据处理者服务数据泄露响应 

 Microsoft 通过确定事件的功能影响、可恢复性和信息影响，为调查分配相应的优先级和严重性级别。 随着调查的进行，优先级和严重性都可能会基于新发现和结论而发生改变。 即将发生或已确认的客户数据风险安全事件被视为高严重性，需要全天候解决。 Microsoft 的 Windows 数据处理者服务将事件的信息影响归类为以下泄露类别： 

| **类别**             | **定义**                                                                                                                   |
| ------------------------ | -------------------------------------------------------------------------------------------------------------------------------- |
| ***无***               | 没有泄露、更改、删除或以其他方式破坏任何信息。 |
| ***隐私泄露***     | 纳税人、员工、受益人等的敏感个人数据被访问或泄露。 |
| ***专有信息泄露*** | 受保护的关键基础机构信息 (PCII) 等未分类专有信息被访问或泄露。 |
| ***完整性损失***     | 敏感信息或专有信息被更改或删除。 |

安全响应团队与 Microsoft 的 Windows 数据处理者服务安全工程师和 SME 一起，基于从证据得出的事实性数据对事件进行分类。 安全事件可分类为： 

 - **误报**：符合检测条件的事件被发现属于正常业务惯例，可能需要进行筛选。 服务团队将确定误报的根本原因，并将根据需要通过系统化方式利用检测源并对其进行微调，以解决这些问题。 
 - **安全事件**：非法访问存储在 Microsoft 设备或 Microsoft 设施上的任何客户数据或支持数据，或者未经授权访问此类设备或设施从而导致客户数据或支持数据丢失、泄露或改动的事件。 
 - **客户可报告的安全事件 (CRSI)**：非法或未经授权访问或使用 Microsoft 的系统、设备或设施，从而导致客户数据泄露、修改或丢失。 
 - **隐私泄露**：涉及个人数据的安全事件的子类型。 处理过程与安全事件没有区别。 

 For a CRSI to be declared, Microsoft must determine that unauthorized access to customer data has or has very likely occurred and/or that there is a legal or contractual commitment that notification must occur. It is desired, but not required, that specific customer impact, resource access, and repair steps be known. An incident is generally declared a CRSI after the conclusion of the Diagnose stage of a security incident; however, the declaration may happen at any point that all pertinent information is available. The security incident manager must establish evidence beyond reasonable doubt that a reportable event has occurred to begin execution of the Customer Incident Notification Process. 

Throughout the investigation, the security response team works closely with global legal advisors to help ensure that forensics are performed in accordance with legal obligations and commitments to customers. There are also significant restrictions on system and customer data viewing and handling in various operating environments. Sensitive or confidential data, as well as Customer Data, are not transferred out of the production environment without explicit written approval from the Incident Manager recorded in the corresponding incident ticket. 

Microsoft verifies that customer and business risk is successfully contained, and that corrective measures are implemented. If necessary, emergency mitigation steps to resolve immediate security risks associated with the event are taken. 

Microsoft 还会完成数据泄露的内部事后分析。 作为此练习的一部分，会评估响应和操作过程的充分性，并识别和实施安全事件响应 SOP 或相关流程所必需的任何更新。 数据泄露的内部事后分析是高度机密的记录，不会提供给客户。 但是，会汇总事后分析并将其包括在其他客户事件通知中。 作为 Windows 数据处理者服务例行审核周期的一部分，会将这些报告提供给外部审计员进行审阅。 

## <a name="customer-notice"></a>客户通知

Microsoft 的 Windows 数据处理者服务会根据需要将数据泄露通知给客户和监管机构。 Microsoft 在Windows 数据处理者服务的操作中依赖于大量的内部分隔。 数据流日志也很可靠。 此设计的一个优点是，大多数事件可以仅限于特定客户。 目的是在数据遭到泄漏时向受影响的客户提供准确、可操作和及时的通知。 

声明 CRSI 后，将尽快进行通知流程，同时仍然考虑快速移动的安全风险。 通常，在进行事件调查时，会就开始起草通知。 我们会在声明泄露之时起的 72 小时内送达客户通知，但以下情况除外： 

 - Microsoft believes the act of performing a notification will increase the risk to other customers. For example, the act of notifying may tip off an adversary causing an inability to remediate. 
 - 经 Microsoft 的法律部门公司外部和法律事务部 (CELA) 和行政事件经理审查的其他异常或极端情况。 

 Microsoft 的 Windows 数据处理者服务向客户提供详细信息，使他们能够执行内部调查，并协助其履行最终用户承诺，而不是过度地延迟通知流程。 

个人数据泄露通知将通过 Microsoft 选择的任何途径送达客户，包括通过电子邮件。 数据泄露通知会送达 Azure 安全中心提供的安全联系人列表，该列表可根据[实施指导原则](https://docs.microsoft.com/azure/security-center/security-center-provide-security-contact-details)进行配置。 如果 Azure 安全中心未提供联系人信息，通知发送给 Azure 订阅中的一个或多个管理员。 为确保通知成功送达，客户有责任确保每个适用订阅和在线服务门户上管理员联系信息的正确性。

Windows 数据处理者服务团队还可能选择通知其他 Microsoft 人员，例如客户服务 (CSS) 和客户的客户经理 (AM) 或技术客户经理 (TAM)。 这些人员通常与客户关系密切，因此可加速补救过程 

若要详细了解 Microsoft 如何检测和响应个人数据泄露，请参阅服务信任门户中的 [GDPR 数据泄露通知](https://servicetrust.microsoft.com/ViewPage/GDPRBreach)。