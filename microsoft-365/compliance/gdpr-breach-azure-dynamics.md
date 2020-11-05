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
ms.openlocfilehash: 0cdd3a2d8e158800cef534a1488df0f25e3d232f
ms.sourcegitcommit: d7975c391e03eeb96e29c1d02e77d2a1433ea67c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/05/2020
ms.locfileid: "48920255"
---
# <a name="azure-and-dynamics-365-breach-notification-under-the-gdpr"></a>GDPR 下的 Azure 和 Dynamics 365 泄露通知

Microsoft Azure 认真遵守《一般数据保护条例》(GDPR) 规定的义务。Microsoft Azure 采取全面的安全措施来防止数据泄露。这些措施包括物理和逻辑安全控制以及自动化安全流程、全面的信息安全和隐私策略，以及针对所有人员的安全和隐私培训。

安全从[安全开发生命周期](https://www.microsoft.com/sdl/)开始就内置于 Microsoft Azure 中，这是一个融合了“通过设计保护隐私”和“默认保护隐私”方法的强制性开发过程。Microsoft 的安全策略指导原则是"假定泄露"，这是深层防护策略的扩展。通过不断挑战 Azure 的安全功能，Microsoft 能够了解新兴威胁。有关 Azure 安全的详细信息，请查看这些[资源](https://www.microsoft.com/trustcenter/security/azure-security)。

Microsoft 拥有全球性的全天候事件响应服务，努力减轻针对 Microsoft Azure 的攻击所造成的影响。Microsoft 通过了多项安全性和合规性审核 (例如 [ISO/IEC 27018](offering-iso-27018.md)) 的检验，在其数据中心使用严格的操作和流程来防止未经授权的访问，包括全天候视频监控、经过培训的安全人员、智能卡和生物识别控制。

## <a name="detection-of-potential-breaches"></a>检测潜在泄露

Due to the nature of modern cloud computing, not all data breaches occurring in a customer cloud environment involve Microsoft Azure services. Microsoft employs a shared responsibility model for Azure services to define security and operational accountabilities. Shared responsibility is important when discussing security of a cloud service, because both the cloud services provider and the customer are accountable for portions of cloud security.

Microsoft does not monitor for or respond to security incidents within the customer's realm of responsibility. A customer-only security compromise would not be processed as an Azure security incident and would require the customer tenant to manage the response effort. Customer incident response may involve collaboration with Microsoft Azure [customer support](https://azure.microsoft.com/support/options/), given appropriate service contracts. Microsoft Azure also offers various services (e.g., [Azure Defender](https://azure.microsoft.com/services/security-center/)) that customers can utilize for developing and managing security incident response.

Azure 根据安全事件响应流程响应潜在数据泄露，该流程属于 Microsoft Azure 事件管理计划的一部分。Azure 安全事件响应使用五阶段流程来实现：检测、评估、诊断、稳定和关闭。随着调查的进展，安全事故响应团队可能在诊断和稳定阶段之间切换。安全事件响应流程概述如下：

|**Stage**|**说明**|
| ------- | ------------- |
| **_1 — 检测_* _ | 潜在事件的第一个指征。 |
| _*_2 — 评估_*_ | 时刻待命的事件响应团队成员评估事件的影响和严重性。根据证据，评估可能会也可能不会导致进一步向安全响应团队上报。 |
| _*_3 — 诊断_*_ | Security response experts conduct the technical or forensic investigation, identify containment, mitigation, and workaround strategies. If the security team believes that customer data may have become exposed to an unlawful or unauthorized individual, execution of the Customer Incident Notification process begins in parallel. |
| _*_4 — 稳定和恢复_*_ | 事件响应团队创建恢复计划以缓解问题。将立即执行危机遏制步骤。例如隔离受影响的系统，同时进行诊断。在即时风险过去之后，还会规划更长期的缓解措施。 |
| _*_5 — 关闭和事后分析_*_ | 事件响应团队创建事后分析，其中会列出事件详情，目的是修改策略、过程和流程，以防事件再次发生。 |

[《云中的 Microsoft Azure 安全响应》](https://gallery.technet.microsoft.com/Azure-Security-Response-in-dd18c678)白皮书进一步详细介绍了 Microsoft 如何在 Azure 内调查、管理和响应安全事件。

Microsoft Azure 使用的检测流程旨在发现威胁 Azure 服务机密性、完整性和可用性的事件。多个事件可能会触发调查：

- Automated system alerts via internal monitoring and alerting frameworks. These alerts could come in the way of signature-based alarms such as anti-malware, intrusion detection or via algorithms designed to profile expected activity and alert upon anomalies.
- 来自 Microsoft Azure 和 Azure 政府版上运行的 Microsoft 服务的第一方报告。
- Security vulnerabilities are reported to the [Microsoft Security Response Center (MSRC)](https://technet.microsoft.com/security/dn440717) via [secure@microsoft.com](mailto:secure@microsoft.com). MSRC works with partners and security researchers around the world to help prevent security incidents and to advance Microsoft product security.
- 通过[客户支持门户](https://www.windowsazure.com/support/contact/)或 Microsoft Azure 和 Azure 政府版管理门户提供的客户报告，其中描述了归因于 Azure 基础结构的可疑活动（与客户的责任范围内发生的活动相对）。
- Security [Red Team and Blue Team](https://azure.microsoft.com/blog/red-teaming-using-cutting-edge-threat-simulation-to-harden-the-microsoft-enterprise-cloud/) activity. This strategy uses a highly skilled Red Team of offensive Microsoft security experts to uncover and attack potential weaknesses in Azure. The security response Blue Team must detect and defend against the Red Team's activity. Both Red and Blue Team actions are used to verify that Azure security response efforts are effectively managing security incidents. Security Red Team and Blue Team activities are operated under rules of engagement to help ensure the protection of customer data.
- Azure 服务操作员的上报。Microsoft 员工经过培训，可识别和上报潜在安全问题。

## <a name="azures-data-breach-response"></a>Azure 的数据泄露响应

Microsoft assigns the investigation appropriate priority and severity levels by determining the functional impact, recoverability, and information impact of the incident. Both the priority and severity may change over the course of the investigation, based on new findings and conclusions. Security events involving imminent or confirmed risk to customer data are treated as high severity and worked around the clock to resolution. 

Microsoft Azure 将事件的信息影响归类为以下泄露类别：

| _ *类别**             | **定义**                                                                                                                   |
| ------------------------ | -------------------------------------------------------------------------------------------------------------------------------- |
| **_无_* _               | 没有泄露、更改、删除或以其他方式破坏任何信息。                                                      |
| _*_隐私泄露_*_     | 纳税人、员工、受益人等的敏感个人数据被访问或泄露。                                |
| _*_专有信息泄露_*_ | 受保护的关键基础机构信息 (PCII) 等未分类专有信息被访问或泄露。 |
| _*_完整性损失_*_     | 敏感信息或专有信息被更改或删除。                                                                     |

安全响应团队与 Microsoft Azure 安全工程师和 SME 一起，基于从证据得出的事实性数据对事件进行分类。安全事件可分类为：

- _*False Positive**: An event that meets detection criteria but is found to be part of a normal business practice and may need to be filtered. The service team identifies the root cause for false positives and will address them in a systematic way using detection sources and fine-tuning them as needed.
- **安全事件** ：非法访问存储在 Microsoft 设备或 Microsoft 设施上的任何客户数据或支持数据，或者未经授权访问此类设备或设施从而导致客户数据或支持数据丢失、泄露或改动的事件。
- **客户可报告的安全/隐私事件 (CRSPI)** ：非法或未经授权访问或使用 Microsoft 的系统、设备或设施从而导致客户数据泄露、修改或丢失。
- **Privacy Breach** : A subtype of Security Incident involving personal data. Handling procedures are no different than a security incident.

For a CRSPI to be declared, Microsoft must determine that unauthorized access to customer data has or has likely occurred and/or that there is a legal or contractual commitment that notification must occur. It is desired, but not required, that specific customer impact, resource access, and repair steps be known. An incident is generally declared a CRSPI after the conclusion of the Diagnose stage of a security incident. However, the declaration may happen at any point that all pertinent information is available. The security incident manager must establish evidence beyond reasonable doubt that a reportable event has occurred to begin execution of the Customer Incident Notification Process.

在整个调查过程中，安全响应团队与全球法律顾问密切合作，帮助确保取证是根据法律义务和对客户的承诺来执行的。对于各种操作环境中系统和客户数据的查看和处理，还存在重大限制。敏感或机密数据以及客户数据不会转移出生产环境，除非有事件经理的明确书面批准，且记录在对应的事件票证中。

Microsoft 验证是否成功遏制了客户和业务风险并实施了纠正措施。如有必要，会采取紧急缓解步骤来解决与事件直接关联的安全风险。

Microsoft also completes an internal post-mortem for data breaches. As a part of this exercise, sufficiency of response and operating procedures are evaluated, and any updates that may be necessary to the Security Incident Response SOP or related processes are identified and implemented. Internal postmortems for data breaches are highly confidential records not available to customers. Postmortems may, however, be summarized and included in other customer event notifications. These reports are provided to external auditors for review as part of Azure's routine audit cycle.

## <a name="customer-notification"></a>客户通知

Microsoft Azure 会根据需要将数据泄露通知客户和监管机构。Microsoft 在 Azure 服务的操作中依赖于大量的内部分隔。数据流日志也很可靠。此设计的一个优点是，大多数事件可以仅限于特定客户。目的是在数据遭到泄漏时向受影响的客户提供准确、可操作和及时的通知。

After the declaration of a CRSPI, the notification process takes place as expeditiously as possible while still considering the security risks of moving quickly. Generally, the process of drafting notifications occurs as the incident investigation is ongoing. Customer notices are delivered in no more than 72 hours from the time we declared a breach *except* in the following circumstances:

- Microsoft believes that the act of performing a notification increases the risk to other customers. For example, the act of notifying may tip off an adversary causing an inability to remediate.
- 经 Microsoft 的法律部门公司外部和法律事务部 (CELA) 和行政事件经理审查的其他异常或极端情况。
- The 72-hour timeline may leave some incident details available. These are provided to customers and regulatory authorities as the investigation proceeds.

Microsoft Azure 向客户提供详细信息，使他们能够执行内部调查，并协助其履行最终用户承诺，而不是过度地延迟通知流程。

个人数据泄露通知将通过 Microsoft 选择的任何途径送达客户，包括通过电子邮件。数据泄露通知会送达 Azure Defender 提供的安全联系人列表，该列表可根据[实施指导原则](https://docs.microsoft.com/azure/security-center/security-center-provide-security-contact-details)进行配置。如果 Azure Defender 未提供联系人信息，通知会发送给 Azure 订阅中的一个或多个管理员。为确保通知成功送达，客户有责任确保每个适用订阅和在线服务门户上管理员联系信息的正确性。

Microsoft Azure 或 Azure 政府版团队还可能选择通知其他 Microsoft 人员，例如客户服务 (CSS) 和客户的客户经理 (AM) 或技术客户经理 (TAM)。 这些人员通常与客户关系密切，因此可加速补救过程

## <a name="microsoft-dynamics-365-built-in-security-features"></a>Microsoft Dynamics 365 内置安全功能

Microsoft Dynamics 365 利用云服务基础结构和内置安全功能，使用安全措施和机制来保护数据。此外，Dynamics 365 还提供了高效的数据访问以及在以下方面与数据完整性及隐私性的协作：[安全标识、数据保护、基于角色的安全性和威胁管理](https://www.microsoft.com/trustcenter/security/dynamics365-security)。

Microsoft Dynamics 365 服务遵循 Microsoft Azure 针对防御数据泄露流程采取的相同技术和组织措施。 所以，“Microsoft Azure 数据泄露”通知文档中记录的任何信息也与 Microsoft Dynamics 365 服务类似。

## <a name="learn-more"></a>了解更多

[Microsoft 信任中心](https://www.microsoft.com/trust-center/privacy/gdpr-overview)
