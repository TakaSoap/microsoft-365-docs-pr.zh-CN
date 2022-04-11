---
title: 设计数据丢失防护策略
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: 了解如何设计 DLP) 策略 (数据丢失防护
ms.openlocfilehash: af09197784607dd6c8f8d939f4d091b365d51799
ms.sourcegitcommit: 9ba00298cfa9ae293e4a57650965fdb3e8ffe07b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/11/2022
ms.locfileid: "64760594"
---
# <a name="design-a-data-loss-prevention-policy"></a>设计数据丢失防护策略

在实施策略之前，花些时间设计策略会使你更快地获得所需的结果，并且意外问题更少，而不是创建策略，然后单独通过试用和错误进行优化。 记录策略设计也有助于进行通信、策略评审、故障排除和进一步优化。

<!--, but excessive tuning to get the intended results can be time consuming.

 if you have to do a lot of tuning to get a policy to yield the intended results can be time consuming .-->

如果你不新Microsoft 365 DLP，在开始设计策略之前，请先完成这些文章：

- [了解数据丢失防护](dlp-learn-about-dlp.md#learn-about-data-loss-prevention) - 本文介绍数据丢失防护规则和 Microsoft 对 DLP 的实施
- [规划 DLP)  (数据丢失防护 ](dlp-overview-plan-for-dlp.md#plan-for-data-loss-prevention-dlp) - 通过本文，你将执行以下操作：
  - [确定利益干系人](dlp-overview-plan-for-dlp.md#identify-stakeholders)
  - [描述要保护的敏感信息的类别](dlp-overview-plan-for-dlp.md#describe-the-categories-of-sensitive-information-to-protect)
  - [设置目标和策略](dlp-overview-plan-for-dlp.md#set-goals-and-strategy)
- [数据丢失防护策略参考](dlp-policy-reference.md#data-loss-prevention-policy-reference) - 本文介绍 DLP 策略的所有组件，以及每个组件如何影响策略的行为

## <a name="policy-design-overview"></a>策略设计概述

[设计策略](#policy-design-process) 主要是为了明确 [定义业务需求，在策略意向语句中记录这些需求](#define-intent-for-the-policy) ，然后 [将这些需求映射到策略配置](#map-business-needs-to-policy-configuration)。 你将使用在规划阶段所做的决策来通知你的一些策略设计决策。

### <a name="define-intent-for-the-policy"></a>定义策略的意向

应该能够汇总单个语句中每个策略的业务意向。 开发此语句将推动组织中的对话，并且在完全充实后，此语句会将策略直接链接到业务用途，并为策略设计提供路线图。 “ [数据丢失防护计划” (DLP) ](dlp-overview-plan-for-dlp.md#overview-of-planning-process) 一文中的步骤将帮助你开始使用策略意向语句。

请从 [DLP 策略配置概述](dlp-learn-about-dlp.md#dlp-policy-configuration-overview) 中记住，所有 DLP 策略都需要你：

- 选择要监视的内容
- 选择要监视的位置
- 选择要应用到项的策略必须匹配的条件
- 选择在满足策略条件时要执行的操作

例如，下面是意向声明的虚构初稿，其中提供了所有四个问题的答案：

*“我们是一个基于美国的组织，我们需要检测Office包含 HIPPA 所涵盖的敏感医疗保健信息的文档，这些信息存储在OneDrive/SharePoint中，并防止在聊天和频道消息 Teams中共享这些信息，并限制每个人与未经授权的第三方共享这些信息”。*

开发策略设计时，可能会修改和扩展语句。

### <a name="map-business-needs-to-policy-configuration"></a>映射业务需要策略配置

让我们将示例草稿语句分解并将其映射到 DLP 策略配置点。

|语句  |配置问题解答和配置映射  |
|---------|---------|
| “我们是一个基于美国的组织，我们需要检测包含 HIPPA 所涵盖的敏感医疗保健信息的Office文档......  |- **要监视的内容**：Office文档，使用 [美国健康保险法案 (HIPAA)](what-the-dlp-policy-templates-include.md#us-health-insurance-act-hipaa)模板 </br>- **匹配的条件**： (预配置但可编辑的) - 项包含美国 SSN 和药物执法局 (DEA) 编号、国际疾病分类 (ICD-9-CM) 、国际疾病分类 (ICD-10-CM) ，内容与组织外部人员共享  </br> - 驱动对话来阐明检测的触发阈值，例如 [置信度，](sensitive-information-type-learn-about.md#more-on-confidence-levels)实 [例计数](dlp-policy-reference.md#content-contains) (称为泄漏容错) 。|
|...存储在OneDrive/SharePoint中并防止在聊天和频道消息Teams共享这些信息... |- **监视位置**：[位置范围，](dlp-policy-reference.md#locations)包括或排除OneDrive和SharePoint网站以及Teams聊天/频道帐户或通讯组。 |
|...并限制每个人与未经授权的第三方共享这些项目。  | - **要执行的操作**：[添加](dlp-policy-reference.md#actions)*限制访问权限或加密Microsoft 365位置中的内容* </br> - 推动有关触发策略时要采取的操作的对话，包括保护性操作（如共享限制、通知和警报等感知操作）以及允许用户替代阻止操作等用户授权操作 |

此示例不涵盖 DLP 策略的所有配置点，需要扩展它。 但是，当你开发自己的 DLP 策略意向语句时，它应该让你朝着正确的方向思考。

> [!IMPORTANT]
> 请记住，选择的位置 () 会影响是否可以使用敏感信息类型、敏感度标签和保留标签以及可用的操作。 请参阅 [数据丢失防护策略参考](dlp-policy-reference.md#data-loss-prevention-policy-reference)。

## <a name="policy-design-process"></a>策略设计过程

1. 完成 [DLP)  (数据丢失防护计划 ](dlp-overview-plan-for-dlp.md#plan-for-data-loss-prevention-dlp) 中的步骤 - 通过本文，你将执行以下操作：
   1. [确定利益干系人](dlp-overview-plan-for-dlp.md#identify-stakeholders)
   1. [描述要保护的敏感信息的类别](dlp-overview-plan-for-dlp.md#describe-the-categories-of-sensitive-information-to-protect)
   1. [设置目标和策略](dlp-overview-plan-for-dlp.md#set-goals-and-strategy)
   1. [定义策略部署计划](dlp-overview-plan-for-dlp.md#policy-deployment)

2. 熟悉 [数据丢失防护策略参考](dlp-policy-reference.md#data-loss-prevention-policy-reference) ，以便了解 DLP 策略的所有组件以及每个组件如何影响策略的行为。

3. 熟悉 [DLP 策略模板包括的内容](what-the-dlp-policy-templates-include.md#what-the-dlp-policy-templates-include)。

4. 与主要利益干系人一起开发策略意向声明。 请参阅本文前面的示例。

5. 确定此策略如何适应整个 DLP 策略策略。

   > [!IMPORTANT]
   > 创建策略后，无法重命名策略。 如果必须重命名策略，则必须创建一个具有所需名称的新策略，然后停用旧策略。 因此，请决定所有策略现在将使用的命名结构。

6. 将策略意向语句中的项映射到配置选项。

7. 确定要从哪个策略模板开始、预定义或自定义。

8. 在创建策略之前，请浏览模板并汇集所需的所有信息。 可能会发现策略意向语句中未涵盖一些配置点。 没关系。 返回利益干系人来解决任何缺少的配置点的要求。

9. 记录所有策略设置的配置，并与利益干系人一起查看这些设置。 可以重新使用策略意向语句映射到配置点，现在配置点已完全充实。

10. [创建策略](create-test-tune-dlp-policy.md#create-test-and-tune-a-dlp-policy) 草稿并参考策略 [部署](dlp-overview-plan-for-dlp.md#policy-deployment) 计划。

<!--## Policy design examples

|Customer business needs description  | approach  |
|---------|---------|
|**Contoso Bank** is in a highly regulated industry and has  many different types of sensitive items in many different locations. </br> - knows which types of sensitive information are top priority. </br> - must minimize business disruption as policies are rolled out. </br> -  has IT resources and can hire experts to help plan, design deploy </br> - has a premier support contract with Microsoft| - Take the time to understand what regulations they must comply with and how they are going to comply. </br> -Take the time to understand the better together value of the Microsoft 365 Information Protection stack </br> - Develop sensitivity labeling scheme for prioritized items and apply </br> - Involve business process owners </br>- Design/code policies, deploy in test mode, train users </br>- repeat|
|**TailSpin Toys** doesn’t know what they have or where it is, and have little to no resource depth. They use Teams, OneDrive for Business and Exchange extensively.     |- Start with simple policies on the prioritized locations. </br>- Monitor what gets identified </br>- Apply sensitivity labels accordingly </br>- Refine policies, train users       |
|**Fabrikam** is a small startup and wants to protect its intellectual property, and must move quickly. They are willing to dedicate some resources, but can't afford to hire outside experts. </br>- Sensitive items are all in Microsoft 365 OneDrive for Business/SharePoint </br>- Adoption of OneDrive for Business and SharePoint is slow, employees/shadow IT use DropBox and Google drive to share/store items </br>- Employees value speed of work over data protection discipline </br>- Customer splurged and bought all 18 employees new Windows 10 devices     |- Take advantage of the default DLP policy in Teams </br>- Use restricted by default setting for SharePoint items </br>- Deploy policies that prevent external sharing </br>- Deploy policies to prioritized locations </br>- Deploy policies to Windows 10 devices </br>- Block uploads to non-OneDrive for Business cloud storage      |


1. For example:
    1. Identify your volume thresholds that your company deems to be low-risk (leakage tolerance), perhaps from unintentional sharing and is an opportunity to educate users and the threshold that is concerning or high-risk for your company that may need immediate attention.
    - example volume: “Low risk” for Contoso is 1 credit card number, perhaps it was a personal card that was shared carelessly
    - example volume: “High risk” for Contoso is 2 or more credit card numbers. It doesn’t feel like a common scenario that an employee would engage in accidentally



–   For each of the sensitive information types listed out, list out **who should have access to that data when it’s generated** and **what type of activities should be allowable with that data**


  <!--(Perhaps this is where we can provide some basic categories, templates, activities and actions that are supported by Microsoft. Some of these items are not discoverable until you are deeper within a policy creation flow. If we provide, we should time stamp it for “last updated” or “as of xx/xx/xxx”)
–   (Show table with parent-child relationships between categories, templates and sensitive info types that Microsoft supports) Should be gathered from GA Compliance environment-->

<!--


> [!TIP] The more locations you include ensures broader application of the policy and more consistent coverage. If you include locations that are mostly used for internal collaboration, the responsiveness of collaboration may be impacted.


- whether the protective actions you need are supported throught the associated location or if you need to compromise to extend coverage
    - also usefule for identifying the most restrictive actions available
    - (we shouldn't mention here that the "content contains" condition is the primary staple for a DLP policy and should be utilized as a starting point for policy creation. The other workload-specific conditions can be ustilized as an extended or granular control of company's DLP policy. Useful for when "too much" data is being restricted and known sensitive data typically falls under certain conditions.)
    - (We can mention here that their quantitative goal such as "protect X% of data across all locations while maintaining x productivity" can be monitored throught alerts or reports. If protection is too high of working against their established goals, they can come back to policy and tweak their conditions/actions)
- Finally, you should have a union of what, hwo and when to be covered which will easily map to generating a live policy via Microsoft DLP.
-
5. At this stage you should asses how you should start this policy. ***LINK OUT TO DEPLOYING A POLICY COVERED IN THE PLANNING TOPIC TOO***
    - Test: your company is very large, conservative or the actions established are pretty restrictive
    - Test w/ notifications: same as above, but you get to test out investigation cadence or volume
    - Live: immediately start this policy in your environment. Useful for when data protection is needed immediately, such as a reactive policy creation, or if you're confident in your planning, or if the risk is low (liek audit actions, etc.)
    - keep it off:
-->

<!--## Policy Design Examples

Here are some examples of more detailed policy intent statement to configuration mappings.

*We are a national healthcare provider based in the U.S. We need to protect our patient’s personal information and prevent it from egressing outside of our company’s borders. We want to limit access to our patient’s personal information to only authorized personnel, like our physicians and billing department from our on-premises devices. We've determined that any single instance of any of each information type in any item is not a data risk, but it is a risk when two or more occur in a single item. We have a Microsoft 365 E5 subscription and want to protect all locations and first party apps that are available to us because we can’t afford to have any data leaks. If an event occurs or is prevented, we want to alert our compliance admin and educate our end-users where necessary.*

|Statement  |Configuration question answered and configuration mapping  |
|---------|---------|
| We are a national healthcare provider based in the U.S. We need to protect our patient’s personal information...|- **What to monitor**: All available item types, use the [U.S. Health Insurance Act (HIPAA)](what-the-dlp-policy-templates-include.md#us-health-insurance-act-hipaa) template. </br>- **Conditions for a match**: (preconfigured but editable) - item contains full names, physical addresses, driver's license number, U.S. SSN
| ...and prevent it from egressing outside of our company’s borders... |- **Actions to take**: Block anyone outside the organization from accessing items, block unintentional sharing by internal users with anyone outside the org.|
|...We want to limit access to our patient’s personal information to only authorized personnel, like our physicians and billing department from our on-premises devices...| - **Actions to take**: - Block access to items, block all activities (upload to cloud, copy to clipboard, copy to USB, copy to network share, access by restricted app, print, copy/move via Bluetooth, copy/move via remote desktop) from Windows devices.  </br> - **Where to monitor**: in all Microsoft 365 locations
| ...We've determined that any single instance of any of each information type in any item is not a data risk, but it is a risk when two or more occur in a single item....| - **Conditions for a match**: (preconfigured but editable) any single item contains more than one of these or any two or more of these:  Full Name, U.S. Social Security Number, Drug Enforcement Agency (DEA) number, International Classification of Diseases (ICD-9-CM), International Classification of Diseases (ICD-10-CM), Physical Address, U.S. driver's license number. For example, two instanced of Full Name or one instance of a U.S. Social Security Number along with one instance of Drug Enforcement Agency (DEA) number will trigger a match.

   , content is shared with people outside my organization  </br> - drives conversations to clarify the triggering threshold for detection like [confidence levels](sensitive-information-type-learn-about.md#more-on-confidence-levels), and [instance count](dlp-policy-reference.md#content-contains) (called leakage tolerance).|
|...that are stored in OneDrive/SharePoint and protect against that information being shared Teams chat and channel messages... |- **Where to monitor**:  [Location scoping](dlp-policy-reference.md#locations) by including or excluding OneDrive and SharePoint sites and Teams chat/channel accounts or distribution groups. |
|...and restrict everyone from sharing those items with unauthorized third parties."  | - **Actions to take**: [You add](dlp-policy-reference.md#actions) *Restrict access or encrypt the content in Microsoft 365 locations* </br> - drives conversation on what actions to take when a policy is triggered including protective actions like sharing restrictions, awareness actions like notifications and alerts, and user empowerment actions like allow user overrides of a blocking action |

-->

## <a name="see-also"></a>另请参阅

- [了解数据丢失防护](dlp-learn-about-dlp.md#learn-about-data-loss-prevention)
- [规划数据丢失防护 (DLP) ](dlp-overview-plan-for-dlp.md#plan-for-data-loss-prevention-dlp)
- [数据丢失防护策略参考](dlp-policy-reference.md#data-loss-prevention-policy-reference)
- [数据丢失防护策略提示参考](dlp-policy-tips-reference.md#data-loss-prevention-policy-tips-reference)
- [创建、测试和优化 DLP 策略](create-test-tune-dlp-policy.md#create-test-and-tune-a-dlp-policy)