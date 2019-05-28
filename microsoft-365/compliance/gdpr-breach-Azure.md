---
title: Azure 与 GDPR 泄露通知
description: 介绍了 Azure 如何避免个人数据泄露，以及 Microsoft 如何在出现数据泄露时响应和通知用户。
keywords: Azure, Microsoft 365, Microsoft 365 教育版, Microsoft 365 文档, GDPR
localization_priority: Priority
ms.prod: Microsoft-365-enterprise
ms.topic: article
ms.date: 04/13/2018
ms.author: heicba
author: herviicban
manager: laurawi
audience: itpro
ms.collection: GDPR
ms.openlocfilehash: 5e8c04bcd20f56580e939bc4a2685eb232d5e589
ms.sourcegitcommit: 0dde96d5864e5b16ea24cfb302930b041c7a8091
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/24/2019
ms.locfileid: "34431493"
---
# <a name="azure-and-breach-notification-under-the-gdpr"></a>Azure 与 GDPR 泄露通知

Microsoft Azure 认真遵守《一般数据保护条例》(GDPR) 规定的义务。Microsoft Azure 采取全面的安全措施来防止数据泄露。这些措施包括物理和逻辑安全控制以及自动化安全流程、全面的信息安全和隐私策略，以及针对所有人员的安全和隐私培训。

安全从[安全开发生命周期](https://www.microsoft.com/sdl/)开始就内置于 Microsoft Azure 中，这是一个融合了“通过设计保护隐私”和“默认保护隐私”方法的强制性开发过程。Microsoft 的安全策略指导原则是"假定泄露"，这是深层防护策略的扩展。通过不断挑战 Azure 的安全功能，Microsoft 能够了解新兴威胁。有关 Azure 安全的详细信息，请查看这些[资源](https://www.microsoft.com/trustcenter/security/azure-security)。

Microsoft 拥有全球性的全天候事件响应服务，努力减轻针对 Microsoft Azure 的攻击所造成的影响。Microsoft 通过了多项安全性和合规性审核 (例如 [ISO/IEC 27018](https://www.microsoft.com/trustcenter/compliance/iso-iec-27018)) 的检验，在其数据中心使用严格的操作和流程来防止未经授权的访问，包括全天候视频监控、经过培训的安全人员、智能卡和生物识别控制。

#### <a name="detection-of-potential-breaches"></a>检测潜在泄露
-------------------------------

由于现代云计算的性质，并非所有发生在客户云环境的数据泄露都涉及 Microsoft Azure 服务。Microsoft 对 Azure 服务采用共同责任模型来定义安全和营运责任。在讨论云服务的安全性时，共同责任尤为重要，因为云提供商和客户各自对云安全性的某些部分负责。

Microsoft 不会监控或响应属于客户责任范围的安全事件。仅限客户的漏洞不会作为 Azure 安全事件进行处理，将需要客户租户来管理响应工作。如果指定了适当的服务联系人，客户事件响应部门也可能会与 Microsoft Azure [客户支持](https://azure.microsoft.com/support/options/)部门进行协作。Microsoft Azure 还提供各种服务（例如 [Azure 安全中心](https://azure.microsoft.com/services/security-center/)），客户可以用来开发和管理安全事件响应。

Azure 根据安全事件响应流程响应潜在数据泄露，该流程属于 Microsoft Azure 事件管理计划的一部分。Azure 安全事件响应使用五阶段流程来实现：检测、评估、诊断、稳定和关闭。随着调查的进展，安全事故响应团队可能在诊断和稳定阶段之间切换。安全事件响应流程概述如下：

<table>
<thead>
<tr class="header">
<th align="left"></th>
<th align="left">阶段</th>
<th align="left">说明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">1</td>
<td align="left">检测</td>
<td align="left">潜在事件的第一个指征。</td>
</tr>
<tr class="even">
<td align="left">2</td>
<td align="left">评估</td>
<td align="left">时刻待命的事件响应团队成员评估事件的影响和严重性。根据证据，评估可能会也可能不会导致进一步向安全响应团队上报。</td>
</tr>
<tr class="odd">
<td align="left">3</td>
<td align="left">诊断</td>
<td align="left"><p>安全响应专家开展技术或鉴证调查，确定遏制、缓解和解决方法策略。</p>
<p>如果安全团队认为非法或未经授权的个人可能接触到了客户数据，将开始并行执行客户事件通知流程。</p></td>
</tr>
<tr class="even">
<td align="left">4</td>
<td align="left">稳定和恢复</td>
<td align="left">事件响应团队创建恢复计划以缓解问题。将立即执行危机遏制步骤。例如隔离受影响的系统，同时进行诊断。在即时风险过去之后，还会规划更长期的缓解措施。</td>
</tr>
<tr class="odd">
<td align="left">5</td>
<td align="left">关闭和事后分析</td>
<td align="left">事件响应团队创建事后分析，其中会列出事件详情，目的是修改策略、过程和流程，以防事件再次发生。</td>
</tr>
</tbody>
</table>

[《云中的 Microsoft Azure 安全响应》](https://gallery.technet.microsoft.com/Azure-Security-Response-in-dd18c678)白皮书进一步详细介绍了 Microsoft 如何在 Azure 内调查、管理和响应安全事件。

Microsoft Azure 使用的检测流程旨在发现威胁 Azure 服务机密性、完整性和可用性的事件。多个事件可能会触发调查：

-   自动化系统通过内部监控和警报框架发出警报。这些警报采用反恶意软件和入侵检测等基于签名的警报的形式提供，或者通过专为分析发生异常时的预期活动和警报而设计的算法来提供。

-   来自 Microsoft Azure 和 Azure 政府版上运行的 Microsoft 服务的第一方报告。

-   通过 <secure@microsoft.com> 将安全漏洞报告给 [Microsoft 安全响应中心 (MSRC)](https://technet.microsoft.com/security/dn440717)。MSRC 与全球的合作伙伴和安全研究机构合作，帮助预防安全事件和提高 Microsoft 产品安全性。

-   通过[客户支持门户](http://www.windowsazure.com/support/contact/)或 Microsoft Azure 和 Azure 政府版管理门户提供的客户报告，其中描述了归因于 Azure 基础结构的可疑活动（与客户的责任范围内发生的活动相对）。

-   安全[红队与蓝队](https://azure.microsoft.com/blog/red-teaming-using-cutting-edge-threat-simulation-to-harden-the-microsoft-enterprise-cloud/)活动。此策略使用由技术娴熟的进攻 Microsoft 安全专家组成的红队发现并攻击 Azure 服务中的潜在弱点。安全响应蓝队必须检测和防御红队的活动。红队和蓝队的操作均用来验证 Azure 安全响应工作是否能有效地管理安全事件。安全红队与蓝队活动都是按照参与规则进行的，可帮助确保对客户数据的保护。

-   Azure 服务操作员的上报。Microsoft 员工经过培训，可识别和上报潜在安全问题。

#### <a name="azures-data-breach-response"></a>Azure 的数据泄露响应
----------------------------

Microsoft 将通过确定功能影响、可恢复性和事件的信息影响来调查相应的优先级和严重性级别。随着调查的进行，优先级和严重性可能会基于新发现和结论而发生更改。涉及客户数据所面临的即将发生或已确认的风险的安全事件视为具有高严重性，全天候进行解决。Microsoft Azure 将事件的信息影响分为以下泄露类别：

<table>
<thead>
<tr class="header">
<th align="left">类别</th>
<th align="left">Definition</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">无</td>
<td align="left">没有泄露、更改、删除或以其他方式破坏任何信息。</td>
</tr>
<tr class="even">
<td align="left">隐私泄露</td>
<td align="left">纳税人、员工、受益人等的敏感个人数据被访问或泄露。</td>
</tr>
<tr class="odd">
<td align="left">专有信息泄露</td>
<td align="left">受保护的关键基础机构信息 (PCII) 等未分类专有信息被访问或泄露。</td>
</tr>
<tr class="even">
<td align="left">完整性损失</td>
<td align="left">敏感信息或专有信息被更改或删除。</td>
</tr>
</tbody>
</table>

安全响应团队与 Microsoft Azure 安全工程师和 SME 一起，基于从证据得出的事实性数据对事件进行分类。安全事件可分类为：

-   **误报：** 满足检测条件的事件经查属于正常业务做法的一部分，可能需要筛选。服务团队将确认误报的根本原因，利用检测源以系统方式加以解决并根据需要进行微调。<span id="_Toc350859432" class="anchor"></span>

-   **安全事件：** 非法访问存储在 Microsoft 设备或 Microsoft 设施上的任何客户数据或支持数据，或者未经授权访问此类设备或设施从而导致客户数据或支持数据丢失、泄露或改动的事件。

-   **客户可报告的安全事件 (CRSI)：** 非法或未经授权访问或使用 Microsoft 的系统、设备或设施从而导致客户数据泄露、修改或丢失。

-   **隐私泄露：** 涉及个人数据的安全事件子类型。处理过程与安全事件相同。

要声明 CRSI，Microsoft 必须确定是否很有可能发生了未经授权的客户数据访问，并且/或者具有必须发送通知的法定或合同义务。最好是知道具体客户影响、资源访问及修复步骤，但不是必须这么做。事件通常是安全事件的诊断阶段结束后的声明 CRSI，但是，声明也可能发生在取得所有相关信息的任何时间点。安全事件经理必须建立超出合理怀疑的证据，证明发生了可报告的事件，以便开始执行客户事件通知流程。

在整个调查过程中，安全响应团队与全球法律顾问密切合作，帮助确保取证是根据法律义务和对客户的承诺来执行的。对于各种操作环境中系统和客户数据的查看和处理，还存在重大限制。敏感或机密数据以及客户数据不会转移出生产环境，除非有事件经理的明确书面批准，且记录在对应的事件票证中。

Microsoft 验证是否成功遏制了客户和业务风险并实施了纠正措施。如有必要，会采取紧急缓解步骤来解决与事件直接关联的安全风险。

Microsoft 还会完成数据泄露的内部事后分析。 作为此练习的一部分，会评估响应和操作过程的充分性，并识别和实施安全事件响应 SOP 或相关流程所必需的任何更新。 数据泄露的内部事后分析是高度机密的记录，不会提供给客户。 但是，会汇总事后分析并将其包括在其他客户事件通知中。 作为 Azure 例行审核周期的一部分，会将这些报告提供给外部审计机构进行审阅。

#### <a name="customer-notification"></a>客户通知
---------------------

Microsoft Azure 会根据需要将数据泄露通知客户和监管机构。Microsoft 在 Azure 服务的操作中依赖于大量的内部分隔。数据流日志也很可靠。此设计的一个优点是，大多数事件可以仅限于特定客户。目的是在数据遭到泄漏时向受影响的客户提供准确、可操作和及时的通知。

在声明 CRSI 后，通知流程会在仍考虑快速行动的安全风险时尽可能快地发生。通常，通知起草流程会在事件调查进行中发生。我们会自声明泄露起 72 小时内送达客户通知，以下情况*除外*：

-   Microsoft 认为通知操作将增加其他客户面临的风险。 例如，发送通知可能向对手预警，导致无法进行补救。

-   经 Microsoft 的法律部门公司外部和法律事务部 (CELA) 和行政事件经理审查的其他异常或极端情况。

Microsoft Azure 向客户提供详细信息，使他们能够执行内部调查，并协助其履行最终用户承诺，而不是过度地延迟通知流程。

个人数据泄露通知将通过 Microsoft 选择的任何途径送达客户，包括通过电子邮件。 数据泄露通知会送达 Azure 安全中心提供的安全联系人列表，该列表可根据[实施指导原则](https://docs.microsoft.com/azure/security-center/security-center-provide-security-contact-details)进行配置。 如果 Azure 安全中心未提供联系人信息，通知将发送给 Azure 订阅中的一个或多个管理员。 为确保通知成功送达，客户有责任确保每个适用订阅和在线服务门户上管理员联系信息的正确性。

Microsoft Azure 或 Azure 政府版团队还可能选择通知其他 Microsoft 人员，例如客户服务 (CSS) 和客户的客户经理 (AM) 或技术客户经理 (TAM)。这些人员通常与客户关系密切，因此可加速补救过程。<span id="_Appendix_A" class="anchor"></span>

#### <a name="microsoft-intune-data-breach"></a>Microsoft InTune 数据泄露
----------------------------

Microsoft Intune 是 Microsoft 企业移动性和安全性套件云服务的关键部分。为了支持数据治理战略，所有 Microsoft 云服务都是根据“通过设计保护隐私”和“默认保护隐私和安全性”方法，采用 Microsoft 隐私和安全性开发的。

因此，Microsoft Intune 云服务遵循 Microsoft Azure 针对防御数据泄露流程采取的相同技术和组织措施。 所以，“Microsoft Azure 数据泄露”通知文档中记录的任何信息也与 Microsoft Intune 服务类似。 例如，Microsoft Intune 具有相同的安全事件响应流程和生命周期（阶段 1：检测一直到阶段 5<strong>：</strong>关闭和事后分析）以及相同的客户安全事件通知流程。 此外，Microsoft Intune 还通过直接与 Microsoft O365 团队合作，对使用 Intune 的任何 Microsoft O365 客户履行泄露通知义务。

若要详细了解 Microsoft 如何检测和响应个人数据泄露，请参阅服务信任门户中的 [GDPR 数据泄露通知](https://servicetrust.microsoft.com/ViewPage/GDPRBreach)。


#### <a name="learn-more"></a>了解更多
[Microsoft 信任中心](https://www.microsoft.com/TrustCenter/Privacy/gdpr/default.aspx)
