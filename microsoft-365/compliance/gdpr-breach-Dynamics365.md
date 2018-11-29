---
title: Dynamics 365 与 GDPR 泄露通知
description: 介绍了 Dynamics 365 如何避免个人数据泄露，以及 Microsoft 如何在出现数据泄露时响应和通知用户。
keywords: Dynamics 365, Microsoft 365, Microsoft 365 教育版, Microsoft 365 文档, GDPR
author: BrendaCarter
localization_priority: Priority
audience: itpro
ms.prod: Microsoft-365-enterprise
ms.topic: article
ms.date: 04/13/2018
ms.author: bcarter
manager: laurawi
ms.collection: GDPR
ms.openlocfilehash: 5bdaa174a4701466ce9f7bd4975221ab95c1cb45
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2018
ms.locfileid: "26865652"
---
# <a name="dynamics-365-and-breach-notification-under-the-gdpr"></a><span data-ttu-id="4ffd4-104">Dynamics 365 与 GDPR 泄露通知</span><span class="sxs-lookup"><span data-stu-id="4ffd4-104">Dynamics 365 and Breach Notification Under the GDPR</span></span>

<span data-ttu-id="4ffd4-105">Dynamics 365 认真遵守《一般数据保护条例》(GDPR) 规定的义务。Microsoft Dynamics 365 数据泄露</span><span class="sxs-lookup"><span data-stu-id="4ffd4-105">Dynamics 365 takes its obligations under the General Data Protection Regulation (GDPR) seriously.Microsoft Dynamics 365 Data Breach</span></span>

<span data-ttu-id="4ffd4-p101">Microsoft 努力持续为 Dynamics 365 客户提供高度安全的企业级服务。本节中的信息概述了 Microsoft Dynamics 365 如何防范安全事件/数据泄露，以及我们响应并通知我们的客户时所遵循的流程。</span><span class="sxs-lookup"><span data-stu-id="4ffd4-p101">Microsoft works continuously to provide highly secure, enterprise-grade services for Dynamics 365 customers. The information in this section provides a summary of how Microsoft Dynamics 365 protects against security incident/data breach and the process we follow to respond and notify our customers.</span></span>

#### <a name="microsoft-dynamics-365-built-in-security-features"></a><span data-ttu-id="4ffd4-108">Microsoft Dynamics 365 内置安全功能</span><span class="sxs-lookup"><span data-stu-id="4ffd4-108">Microsoft Dynamics 365 Built-In Security Features</span></span>

<span data-ttu-id="4ffd4-p102">Microsoft Dynamics 365 利用云服务基础结构和内置安全功能，使用安全措施和机制来保护数据。此外，Dynamics 365 还提供了高效的数据访问以及在以下方面与数据完整性及隐私性的协作：[安全标识、数据保护、基于角色的安全性和威胁管理](https://www.microsoft.com/trustcenter/security/dynamics365-security)。</span><span class="sxs-lookup"><span data-stu-id="4ffd4-p102">Microsoft Dynamics 365 takes advantage of the cloud service infrastructure and built-in security features to keep data safe using security measures and mechanisms to protect data. In addition, Dynamics 365 provides efficient data access and collaboration with data integrity and privacy in the following areas: [secure identity, data protection, role based security and threat management](https://www.microsoft.com/trustcenter/security/dynamics365-security).</span></span>

#### <a name="incident-response-training"></a><span data-ttu-id="4ffd4-111">事件响应培训</span><span class="sxs-lookup"><span data-stu-id="4ffd4-111">Incident Response Training</span></span>

<span data-ttu-id="4ffd4-p103">使用 Microsoft Dynamics 365 的每个员工都要接受适合其角色的有关安全事件和响应过程的培训。每个 Microsoft Dynamics 365 员工在入职时都会接受培训，此后每年还会接受年度进修培训。该培训旨在让员工对 Microsoft 的方法有基本的了解，以便在培训完成时，所有员工都了解：</span><span class="sxs-lookup"><span data-stu-id="4ffd4-p103">Each employee working on Microsoft Dynamics 365 is provided with training regarding security incidents and response procedures that are appropriate to their role. Every Microsoft Dynamics 365 employee receives training upon joining, and annual refresher training every year thereafter. The training is designed to provide the employee with a basic understanding of Microsoft’s approach to security so that upon completion of training, all employees understand:</span></span>

-   <span data-ttu-id="4ffd4-115">安全事件的定义；</span><span class="sxs-lookup"><span data-stu-id="4ffd4-115">The definition of a security incident;</span></span>

-   <span data-ttu-id="4ffd4-116">所有员工报告安全事件的责任；</span><span class="sxs-lookup"><span data-stu-id="4ffd4-116">The responsibility of all employees to report security incidents;</span></span>

-   <span data-ttu-id="4ffd4-117">如何向 Dynamics 365 安全事件响应团队上报潜在安全事件；</span><span class="sxs-lookup"><span data-stu-id="4ffd4-117">How to escalate a potential security incident to Dynamics 365 Security Incident Response team;</span></span>

-   <span data-ttu-id="4ffd4-118">Dynamics 365 安全事件响应团队如何响应安全事件；</span><span class="sxs-lookup"><span data-stu-id="4ffd4-118">How the Dynamics 365 Security incident Response team responds to security incident;</span></span>

-   <span data-ttu-id="4ffd4-119">有关隐私尤其是客户隐私的特别问题；</span><span class="sxs-lookup"><span data-stu-id="4ffd4-119">Special concerns regarding privacy, particularly customer privacy;</span></span>

-   <span data-ttu-id="4ffd4-120">查找有关安全性和隐私性的其他信息的位置，以及上报联系人。</span><span class="sxs-lookup"><span data-stu-id="4ffd4-120">Where to find additional information about security and privacy, and escalation contacts.</span></span>

#### <a name="how-does-microsoft-dynamics-365-define-security-incident-potential-breaches"></a><span data-ttu-id="4ffd4-121">Microsoft Dynamics 365 如何定义安全事件/潜在泄露</span><span class="sxs-lookup"><span data-stu-id="4ffd4-121">How does Microsoft Dynamics 365 define Security Incident/ Potential Breaches</span></span>

<span data-ttu-id="4ffd4-p104">安全事件/数据泄露是指非法访问存储在 Microsoft 设备或 Microsoft 设施中的客户数据或未经授权访问此类设备或设施从而可能导致客户数据丢失、泄露或改动等事件。Microsoft 在安全事件/数据泄露响应方面的目标是保护客户数据和 Dynamics 365 服务。Microsoft 管理安全事件的方法符合[国家标准和技术](https://www.nist.gov/) (NIST) 特殊出版物 (SP) [800 61](https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-61r2.pdf)。</span><span class="sxs-lookup"><span data-stu-id="4ffd4-p104">A security incident/ data breach refers to events such as unlawful access to customer’s data stored on Microsoft equipment or in Microsoft facilities, or unauthorized access to such equipment or facilities that has the potential to result in the loss, disclosure or alteration of customer data. Microsoft’s goal when responding to security incidents/ data breach is to protect customer data and Dynamics 365 services. Microsoft’s approach to managing a security incident conforms to the [National Institute of Standards and Technology](https://www.nist.gov/) (NIST) Special Publication (SP) [800-61](https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-61r2.pdf).</span></span>

<span data-ttu-id="4ffd4-p105">Microsoft 不会监控或响应属于客户责任范围的安全事件。仅限客户的漏洞不会作为 Dynamics 365 安全事件进行处理，将需要客户租户来管理响应工作。如果指定了适当的服务联系人，客户事件响应部门也可能会与 Microsoft Dynamics 365 客户支持部门进行协作。</span><span class="sxs-lookup"><span data-stu-id="4ffd4-p105">Microsoft does not monitor for or respond to security incidents within the customer’s realm of responsibility. A customer-only security compromise would not be processed as a Dynamics 365 security incident and would require the customer tenant to manage the response effort. Customer incident response may involve collaboration with Microsoft Dynamics 365 customer support, given appropriate service contracts.</span></span>

#### <a name="detection-of-potential-breaches"></a><span data-ttu-id="4ffd4-128">检测潜在泄露</span><span class="sxs-lookup"><span data-stu-id="4ffd4-128">Detection of Potential Breaches</span></span>

<span data-ttu-id="4ffd4-p106">Dynamics 365 根据安全事件响应流程响应潜在数据泄露，该流程属于 Microsoft Dynamics 365 事件管理计划的一部分。Dynamics 365 安全事件响应使用五阶段流程来实现：检测、评估、诊断、稳定和关闭。随着调查的进展，安全事故响应团队可能在诊断和稳定阶段之间切换。安全事件响应流程概述如下：</span><span class="sxs-lookup"><span data-stu-id="4ffd4-p106">Dynamics 365 responds to a potential data breach according to the security incident response process, which is a subset of the Microsoft Dynamics 365 incident management plan. Dynamics 365 security incident response is implemented using a five-stage process: Detect, Assess, Diagnose, Stabilize, and Close. The Security Incident Response Team may alternate between the diagnose and stabilize stages as the investigation progresses. An overview of the security incident response process is below:</span></span>

<table>
<thead>
<tr class="header">
<th align="left"></th>
<th align="left"><span data-ttu-id="4ffd4-133">阶段</span><span class="sxs-lookup"><span data-stu-id="4ffd4-133">Stage</span></span></th>
<th align="left"><span data-ttu-id="4ffd4-134">说明</span><span class="sxs-lookup"><span data-stu-id="4ffd4-134">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="4ffd4-135">1</span><span class="sxs-lookup"><span data-stu-id="4ffd4-135">1</span></span></td>
<td align="left"><span data-ttu-id="4ffd4-136">检测</span><span class="sxs-lookup"><span data-stu-id="4ffd4-136">Detect</span></span></td>
<td align="left"><span data-ttu-id="4ffd4-137">事件调查的第一个指征。</span><span class="sxs-lookup"><span data-stu-id="4ffd4-137">First indication of an event investigation.</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="4ffd4-138">2</span><span class="sxs-lookup"><span data-stu-id="4ffd4-138">2</span></span></td>
<td align="left"><span data-ttu-id="4ffd4-139">评估</span><span class="sxs-lookup"><span data-stu-id="4ffd4-139">Assess</span></span></td>
<td align="left"><span data-ttu-id="4ffd4-p107">时刻待命的事件响应团队成员评估事件的影响和严重性。根据证据，评估可能会也可能不会导致进一步向安全响应团队上报。</span><span class="sxs-lookup"><span data-stu-id="4ffd4-p107">An on-call incident response team member assesses the impact and severity of the event. Based on evidence, the assessment may or may not result in further escalation to the security response team.</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="4ffd4-142">3</span><span class="sxs-lookup"><span data-stu-id="4ffd4-142">3</span></span></td>
<td align="left"><span data-ttu-id="4ffd4-143">诊断/调查</span><span class="sxs-lookup"><span data-stu-id="4ffd4-143">Diagnose/ Investigate</span></span></td>
<td align="left"><p><span data-ttu-id="4ffd4-144">安全响应专家开展技术或鉴证调查，确定遏制、缓解和解决方法策略。</span><span class="sxs-lookup"><span data-stu-id="4ffd4-144">Security response experts conduct the technical or forensic investigation, identify containment, mitigation, and workaround strategies.</span></span></p>
<p><span data-ttu-id="4ffd4-145">如果安全团队认为非法或未经授权的个人可能接触到了客户数据，将开始并行执行客户事件通知流程。</span><span class="sxs-lookup"><span data-stu-id="4ffd4-145">If the security team believes that customer data may have become exposed to an unlawful or unauthorized individual, parallel execution of the Customer Incident Notification process begins in parallel.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="4ffd4-146">4</span><span class="sxs-lookup"><span data-stu-id="4ffd4-146">4</span></span></td>
<td align="left"><span data-ttu-id="4ffd4-147">稳定和恢复</span><span class="sxs-lookup"><span data-stu-id="4ffd4-147">Stabilize and Recover</span></span></td>
<td align="left"><span data-ttu-id="4ffd4-p108">事件响应团队创建恢复计划以缓解问题。将立即执行危机遏制步骤。例如隔离受影响的系统，同时进行诊断。在即时风险过去之后，还会规划更长期的缓解措施。</span><span class="sxs-lookup"><span data-stu-id="4ffd4-p108">The incident response team creates a recovery plan to mitigate the issue. Crisis containment steps such as quarantining impacted systems may occur immediately and in parallel with diagnosis. Longer term mitigations may be planned which occur after the immediate risk has passed.</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="4ffd4-151">5</span><span class="sxs-lookup"><span data-stu-id="4ffd4-151">5</span></span></td>
<td align="left"><span data-ttu-id="4ffd4-152">关闭和事后分析</span><span class="sxs-lookup"><span data-stu-id="4ffd4-152">Close and Post-Mortem</span></span></td>
<td align="left"><span data-ttu-id="4ffd4-153">事件响应团队创建事后分析，其中会列出事件详情，目的是修改策略、过程和流程，以防事件再次发生。</span><span class="sxs-lookup"><span data-stu-id="4ffd4-153">The incident response team creates a post-mortem that outlines the details of the incident, with the intention to revise policies, procedures, and processes to prevent a reoccurrence of the event.</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="4ffd4-154">[《Dynamics 安全事件管理》](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=266d445f-ea95-42de-9124-4b2118a639ee&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers)白皮书进一步详细介绍了 Microsoft 如何在 Dynamics 365 内调查、管理和响应安全事件。</span><span class="sxs-lookup"><span data-stu-id="4ffd4-154">The [Dynamics Security Incident Management](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=266d445f-ea95-42de-9124-4b2118a639ee&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers) white paper further details how Microsoft investigates, manages, and responds to security incidents within Dynamics 365.</span></span>

<span data-ttu-id="4ffd4-p109">Microsoft Dynamics 365 使用的检测流程旨在发现威胁 Dynamics 365 服务机密性、完整性和可用性的事件。多个事件可能会触发调查：</span><span class="sxs-lookup"><span data-stu-id="4ffd4-p109">The detection processes used by Microsoft Dynamics 365 are designed to discover events that risk the confidentiality, integrity, and availability of Dynamics 365 services. Several events can trigger an investigation:</span></span>

-   <span data-ttu-id="4ffd4-p110">自动化系统通过内部监控和警报框架发出警报。这些警报采用反恶意软件和入侵检测等基于签名的警报的形式提供，或者通过专为分析发生异常时的预期活动和警报而设计的算法来提供。</span><span class="sxs-lookup"><span data-stu-id="4ffd4-p110">Automated system alerts via internal monitoring and alerting frameworks. These alerts could come in the way of signature-based alarms such as antimalware, intrusion detection or via algorithms designed to profile expected activity and alert upon anomalies.</span></span>

-   <span data-ttu-id="4ffd4-159">来自部署在公有云中的 Microsoft Dynamics 365 服务和部署在主权云中的 Microsoft Dynamics 365 服务的第一方报告。</span><span class="sxs-lookup"><span data-stu-id="4ffd4-159">First party reports running Microsoft Dynamics 365 services deployed in Public Cloud and Microsoft Dynamics 365 services deployed in Sovereign Cloud.</span></span>

-   <span data-ttu-id="4ffd4-p111">通过 <secure@microsoft.com> 将安全漏洞报告给 [Microsoft 安全响应中心 (MSRC)](https://technet.microsoft.com/security/dn440717)。MSRC 与全球的合作伙伴和安全研究机构合作，帮助预防安全事件和提高 Microsoft 产品安全性。</span><span class="sxs-lookup"><span data-stu-id="4ffd4-p111">Security vulnerabilities are reported to the [Microsoft Security Response Center (MSRC)](https://technet.microsoft.com/security/dn440717) via <secure@microsoft.com>. MSRC works with partners and security researchers around the world to help prevent security incidents and to advance Microsoft product security.</span></span>

-   <span data-ttu-id="4ffd4-162">描述归因于 Microsoft Dynamics 365 服务的可疑活动（与客户责任范围内发生的活动相对）的客户报告。</span><span class="sxs-lookup"><span data-stu-id="4ffd4-162">Customer reports that describe suspicious activity attributed to the Microsoft Dynamics 365 Services (as opposed to activity occurring within the customer’s scope of responsibility).</span></span>

-   <span data-ttu-id="4ffd4-p112">安全[红队与蓝队](https://azure.microsoft.com/blog/red-teaming-using-cutting-edge-threat-simulation-to-harden-the-microsoft-enterprise-cloud/)活动。此策略使用由技术娴熟的进攻安全专家组成的红队发现并攻击 Microsoft Dynamics 365 服务中的潜在弱点。安全响应蓝队必须检测和防御红队的活动。红队和蓝队的操作均用来验证 Microsoft Dynamics 365 安全响应工作是否能有效地管理安全事件。安全红队与蓝队活动都是按照责任要求进行的，可帮助确保对客户数据的保护。</span><span class="sxs-lookup"><span data-stu-id="4ffd4-p112">Security [Red Team and Blue Team](https://azure.microsoft.com/blog/red-teaming-using-cutting-edge-threat-simulation-to-harden-the-microsoft-enterprise-cloud/) activity. This strategy uses a highly-skilled Red team of offensive security experts to uncover and attack potential weaknesses in Microsoft Dynamics 365 services. The security response Blue team must detect and defend against the Red Team’s activity. Both Red and Blue Team actions are used to verify that Microsoft Dynamics 365 security response efforts are effectively managing security incidents. Security Red Team and Blue Team activities are operated under requirements of responsibility to help ensure the protection of customer data.</span></span>

-   <span data-ttu-id="4ffd4-p113">Microsoft Dynamics 365 服务操作员的上报。Microsoft 员工经过培训，可识别和上报潜在安全问题。</span><span class="sxs-lookup"><span data-stu-id="4ffd4-p113">Escalations by operators of Microsoft Dynamics 365 services. Microsoft employees are trained to identify and escalate potential security issues.</span></span>

#### <a name="microsoft-dynamics-365-data-breach-response"></a><span data-ttu-id="4ffd4-170">Microsoft Dynamics 365 数据泄露响应</span><span class="sxs-lookup"><span data-stu-id="4ffd4-170">Microsoft Dynamics 365 Data Breach Response</span></span>

<span data-ttu-id="4ffd4-p114">Microsoft 将通过确定功能影响、可恢复性和事件的信息影响来调查相应的优先级和严重性级别。随着调查的进行，优先级和严重性可能会基于新发现和结论而发生更改。涉及客户数据所面临的即将发生或已确认的风险的安全事件视为具有高严重性，全天候进行解决。Microsoft Dynamics 365 将隐私泄露定义为“联机服务最终用户或 Microsoft 员工的个人数据”的泄露。</span><span class="sxs-lookup"><span data-stu-id="4ffd4-p114">Microsoft assigns the investigation appropriate priority and severity levels by determining the functional impact, recoverability, and information impact of the incident. Both the priority and severity may change over the course of the investigation, based on new findings and conclusions. Security events involving imminent or confirmed risk to customer data are treated as high severity and worked around the clock to resolution. Microsoft Dynamics 365 defines privacy breach as a breach of “personal data of an online service end user or Microsoft employees.”</span></span>

<span data-ttu-id="4ffd4-p115">安全响应团队与 Microsoft Dynamics 365 安全工程师和主题专家 (SME) 一起，基于从证据得出的事实性数据对事件进行分类。安全事件可分类为：</span><span class="sxs-lookup"><span data-stu-id="4ffd4-p115">The Security Response Team works with Microsoft Dynamics 365 Security Engineers and Subject Matter Experts (SMEs) to classify the event based on factual data from the evidence. A security event may be classified as:</span></span>

-   <span data-ttu-id="4ffd4-p116">**误报：** 满足检测条件但被发现属于正常业务实践的一部分的事件，可能需要对事件进行筛选。服务团队将确认误报的根本原因，利用检测源以系统方式加以解决并根据需要进行微调。<span id="_Toc350859432" class="anchor"></span></span><span class="sxs-lookup"><span data-stu-id="4ffd4-p116">**False Positive:** An event that meets detection criteria but is found to be part of a normal business practice and may need to be filtered. The service team will identify the root cause for false positives and will address them in a systematic way leveraging detection sources and fine-<span id="_Toc350859432" class="anchor"></span>tuning them as needed.</span></span>

-   <span data-ttu-id="4ffd4-179">**安全事件：** 非法访问存储在 Microsoft 设备或 Microsoft 设施上的任何客户数据或支持数据，或者未经授权访问此类设备或设施从而导致客户数据或支持数据丢失、泄露或改动的事件。</span><span class="sxs-lookup"><span data-stu-id="4ffd4-179">**Security Incident:** An incident where unlawful access to any Customer Data or Support Data stored on Microsoft’s equipment or in Microsoft’s facilities, or unauthorized access to such equipment or facilities resulting in loss, disclosure, or alteration of Customer Data or Support Data has occurred.</span></span>

-   <span data-ttu-id="4ffd4-180">**客户可报告的安全事件 (CRSI)：** 非法或未经授权访问或使用 Microsoft 的系统、设备或设施从而导致客户数据泄露、修改或丢失。</span><span class="sxs-lookup"><span data-stu-id="4ffd4-180">**Customer-Reportable Security Incident (CRSI):** Unlawful or unauthorized access to or use of Microsoft’s systems, equipment, or facilities resulting in disclosure, modification, or loss of customer data.</span></span>

-   <span data-ttu-id="4ffd4-p117">**隐私事件：** 涉及个人数据的安全事件子类型。处理过程与安全事件相同。</span><span class="sxs-lookup"><span data-stu-id="4ffd4-p117">**Privacy Incident:** A subtype of Security Incident involving personal data. Handling procedures are no different than a security incident.</span></span>

<span data-ttu-id="4ffd4-p118">要声明 CRSI，Microsoft 必须确定是否很有可能发生了未经授权的客户数据访问，并且/或者具有必须发送通知的法定或合同义务。最好是知道具体客户影响、资源访问及修复步骤，但不是必须这么做。事件通常是安全事件的诊断阶段结束后的声明 CRSI，但是，声明也可能发生在取得所有相关信息的任何时间点。安全事件经理必须建立超出合理怀疑的证据，证明发生了可报告的事件，以便开始执行客户事件通知流程。</span><span class="sxs-lookup"><span data-stu-id="4ffd4-p118">For a CRSI to be declared, Microsoft must determine that unauthorized access to customer data has or has very likely occurred and/or that there is a legal or contractual commitment that notification must occur. It is desired, but not required, that specific customer impact, resource access, and repair steps be known. An incident is generally declared CRSI after the conclusion of the Diagnose stage of a security incident; however, the declaration may happen at any point that all pertinent information is available. The security incident manager must establish evidence beyond reasonable doubt that a reportable event has occurred to begin execution of the Customer Incident Notification Process.</span></span>

<span data-ttu-id="4ffd4-p119">在整个调查过程中，安全响应团队与全球法律顾问密切合作，帮助确保取证是根据法律义务和对客户的承诺来执行的。对于各种操作环境中系统和客户数据的查看和处理，还存在重大限制。敏感或机密数据以及客户数据不会转移出生产环境，除非有事件经理的明确书面批准，且记录在对应的事件票证中。</span><span class="sxs-lookup"><span data-stu-id="4ffd4-p119">Throughout the investigation, the security response team works closely with global legal advisors to help ensure that forensics are performed in accordance with legal obligations and commitments to customers. There are also significant restrictions on system and customer data viewing and handling in various operating environments. Sensitive or confidential data, as well as Customer Data, are not transferred out of the production environment without explicit written approval from the Incident Manager recorded in the corresponding incident ticket.</span></span>

<span data-ttu-id="4ffd4-p120">Microsoft 验证是否成功遏制了客户和业务风险并实施了纠正措施。如有必要，会采取紧急缓解步骤来解决与事件直接关联的安全风险。</span><span class="sxs-lookup"><span data-stu-id="4ffd4-p120">Microsoft verifies that customer and business risk is successfully contained, and that corrective measures are implemented. If necessary, emergency mitigation steps to resolve immediate security risks associated with the event are taken.</span></span>

<span data-ttu-id="4ffd4-p121">Microsoft 还会完成数据泄露的内部事后分析。作为此练习的一部分，会评估响应和操作过程的充分性，并识别和实施 Microsoft 的内部安全策略或相关流程所必需的任何更新。数据泄露的内部事后分析是高度机密的记录，不会提供给客户。但是，会汇总事后分析并将其包括在其他客户事件通知中。作为 Dynamics 365 例行审核周期的一部分，会将这些报告提供给外部审计机构进行审阅。</span><span class="sxs-lookup"><span data-stu-id="4ffd4-p121">Microsoft also completes an internal post-mortem for data breaches. As a part of this exercise, sufficiency of response and operating procedures are evaluated, and any updates that may be necessary to Microsoft’s internal security policies or related processes are identified and implemented. Internal post-mortems for data breaches are highly confidential records not available to customers. Post-mortems may, however, be summarized and included in other customer event notifications. These reports are provided to external auditors for review as part of Dynamics 365 routine audit cycle.</span></span>

#### <a name="customer-notification"></a><span data-ttu-id="4ffd4-197">客户通知</span><span class="sxs-lookup"><span data-stu-id="4ffd4-197">Customer Notification</span></span>

<span data-ttu-id="4ffd4-p122">Microsoft Dynamics 365 会根据需要将数据泄露通知客户和监管机构。Microsoft 在 Dynamics 365 服务的操作中依赖于大量的内部分隔。数据流日志也很可靠。此设计的一个优点是，大多数事件可以仅限于特定客户。目的是在数据遭到泄漏时向受影响的客户提供准确、可操作和及时的通知。</span><span class="sxs-lookup"><span data-stu-id="4ffd4-p122">Microsoft Dynamics 365 notifies customers and regulatory authorities of data breaches as required. Microsoft relies on heavy internal compartmentalization in the operation of Dynamics 365 services. Data flow logs are also robust. As a benefit of this design, most incidents can be scoped to specific customers. The goal is to provide impacted customers with an accurate, actionable, and timely notice when their data has been breached.</span></span>

<span data-ttu-id="4ffd4-p123">在声明 CRSI 后，通知流程会在仍考虑快速行动的安全风险时尽可能快地发生。通常，起草通知的流程会在事件调查进行中发生。我们一旦声明了泄露，就会立即送达客户通知，以下情况*除外*：</span><span class="sxs-lookup"><span data-stu-id="4ffd4-p123">The notification process upon a declared CRSI will occur as expeditiously as possible while still considering the security risks of moving quickly. Generally, the process of drafting notifications occurs as the incident investigation is ongoing. Customer notices are delivered promptly from the time we declared a breach *except* for the following circumstances:</span></span>

-   <span data-ttu-id="4ffd4-p124">Microsoft 认为通知操作将增加其他客户面临的风险。例如，发送通知可能向对手预警，导致无法进行补救。</span><span class="sxs-lookup"><span data-stu-id="4ffd4-p124">Microsoft believes the act of performing a notification will increase the risk to other customers. For example, the act of notifying may tip off an adversary causing an inability to remediate.</span></span>

-   <span data-ttu-id="4ffd4-208">经 Microsoft 的法律部门和行政事件经理审查的其他异常或极端情况。</span><span class="sxs-lookup"><span data-stu-id="4ffd4-208">Other unusual or extreme circumstances vetted by Microsoft’s legal department and the Executive Incident Manager.</span></span>

<span data-ttu-id="4ffd4-209">Microsoft Dynamics 365 向客户提供详细信息，使他们能够执行内部调查，并协助其履行最终用户承诺，而不是过度地延迟通知流程。</span><span class="sxs-lookup"><span data-stu-id="4ffd4-209">Microsoft Dynamics 365 provides customers with detailed information enabling them to perform internal investigations and assisting them in meeting end user commitments, while not unduly delaying the notification process.</span></span>

<span data-ttu-id="4ffd4-p125">个人数据泄露通知将通过 Microsoft 选择的任何途径送达客户，包括通过电子邮件。数据泄露通知会送达 Office 安全中心提供的客户联系人/管理员列表（仅受影响的租户），该列表可由客户/租户管理员配置。为确保通知成功送达，客户有责任确保每个适用订阅和在线服务门户上管理员联系信息的正确性。</span><span class="sxs-lookup"><span data-stu-id="4ffd4-p125">Notification of a personal data breach will be delivered to the customer by any means Microsoft selects, including via email. Notification of a data breach will be delivered to the list of customer contacts/ admins (only affected tenants) provided in Office Security Center, which is configurable by the customer/ tenant admin. To ensure that notification can be successfully delivered, it is the customer’s responsibility to ensure that the administrative contact information on each applicable subscription and online services portal is correct.</span></span>

<span data-ttu-id="4ffd4-p126">Microsoft Dynamics 365 团队还可能选择通知其他 Microsoft 人员，例如客户服务 (CSS) 和客户的客户经理 (AM) 或技术客户经理 (TAM)。这些人员通常与客户关系密切，因此可加速补救过程。<span id="_Appendix_A" class="anchor"></span></span><span class="sxs-lookup"><span data-stu-id="4ffd4-p126">The Microsoft Dynamics 365 team may also elect to notify additional Microsoft personnel such as Customer Service (CSS) and the customer’s Account Manager(s) (AM) or Technical Account Manager(s) (TAM). These individuals often have close relationships with the customer and can facilitate faster remediation.<span id="_Appendix_A" class="anchor"></span></span></span>

#### <a name="learn-more"></a><span data-ttu-id="4ffd4-214">了解详细信息</span><span class="sxs-lookup"><span data-stu-id="4ffd4-214">Learn more</span></span>
[<span data-ttu-id="4ffd4-215">Microsoft 信任中心</span><span class="sxs-lookup"><span data-stu-id="4ffd4-215">Microsoft Trust Center</span></span>](https://www.microsoft.com/TrustCenter/Privacy/gdpr/default.aspx)