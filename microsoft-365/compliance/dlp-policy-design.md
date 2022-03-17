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
description: 了解如何使用 DLP 策略 (数据丢失) 防护
ms.openlocfilehash: 14e9fbb5efd20ddcf3d0a47da41a0cce89c88cee
ms.sourcegitcommit: 3fb76db6b34e24569417f4c8a41b99f46a780389
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/17/2022
ms.locfileid: "63526314"
---
# <a name="design-a-data-loss-prevention-policy"></a>设计数据丢失防护策略

与仅通过创建策略然后通过试验和错误进行调整相比，在实施策略之前花时间设计策略将更快获得所需结果，并且具有更少的意外问题。 记录策略设计还有助于进行通信、策略审阅、疑难解答和进一步调整。

<!--, but excessive tuning to get the intended results can be time consuming.

 if you have to do a lot of tuning to get a policy to yield the intended results can be time consuming .-->

如果你是使用 DLP Microsoft 365，那么在开始设计策略之前阅读以下文章会很有帮助：

- [了解数据丢失防护](dlp-learn-about-dlp.md#learn-about-data-loss-prevention) - 本文将向您介绍数据丢失防护规范以及 Microsoft 对 DLP 的实现
- [规划 DLP (数据丢失 ](dlp-overview-plan-for-dlp.md#plan-for-data-loss-prevention-dlp)) - 通过阅读本文，您将：
    - [确定利益干系人](dlp-overview-plan-for-dlp.md#identify-stakeholders)
    - [描述要保护的敏感信息类别](dlp-overview-plan-for-dlp.md#describe-the-categories-of-sensitive-information-to-protect)
    - [设置目标和策略](dlp-overview-plan-for-dlp.md#set-goals-and-strategy)
- [数据丢失防护策略参考](dlp-policy-reference.md#data-loss-prevention-policy-reference) - 本文介绍了 DLP 策略的所有组件以及每个组件如何影响策略的行为

## <a name="policy-design-overview"></a>策略设计概述

[设计策略主要](#policy-design-process) 与明确 [定义](#define-intent-for-the-policy) 业务需求有关，将其记录在策略意图声明中，然后将 [这些需求映射到策略配置](#map-business-needs-to-policy-configuration)。 你将使用在规划阶段做出的决策来通知一些策略设计决策。 

### <a name="define-intent-for-the-policy"></a>定义策略的意图 

您应该能够在单个语句中总结每个策略的业务意图。 开发此声明将推动您组织的对话，完全完成时，此声明将直接将策略链接到业务目的，并提供策略设计的路线图。 Plan [for data loss prevention (DLP) ](dlp-overview-plan-for-dlp.md#overview-of-planning-process) 一文的步骤将帮助您开始使用策略意图声明。  

从 [DLP 策略配置概述中请记住](dlp-learn-about-dlp.md#dlp-policy-configuration-overview) ，所有 DLP 策略都要求您：

- 选择要监视的
- 选择要监视的地方
- 选择要应用于项目的策略必须匹配的条件
- 选择在满足策略条件时要执行的操作 

例如，下面是意图声明的虚构第一个草稿，它提供所有四个问题的解答： 

*"We are a u-based organization， and we need to detect Office documents that contain sensitive health care information covered by HIPPA that stored in OneDrive/SharePoint and protect from that information being shared in Teams chat and channel messages and restrict everyone from sharing them with unauthorized third parties".* 

开发策略设计时，可能会修改和扩展语句。

### <a name="map-business-needs-to-policy-configuration"></a>将业务需求映射到策略配置

让我们分解示例草稿语句，并映射到 DLP 策略配置点。

|语句  |已回答的配置问题与配置映射  |
|---------|---------|
| "We are a u-s-based organization， and we need to detect Office documents that contain sensitive health care information covered by HIPPA...  |- **要监视的内容**：Office文档，使用美国健康保险法案 ([HIPAA)](what-the-dlp-policy-templates-include.md#us-health-insurance-act-hipaa)模板 </br>- 匹配条件： (预配置但可编辑的) - 项目包含美国 SSN 和管制局 (DEA) 号码、国际患者分类 (ICD-9-CM) 、国际感染分类 (ICD-10-CM) 、内容与组织外部人员共享  </br> - 驱动对话以阐明检测的触发阈值（如可信度[](sensitive-information-type-learn-about.md#more-on-confidence-levels)）和实例计数[](dlp-policy-reference.md#content-contains) (称为泄漏容错) 。|
|...存储在聊天OneDrive/SharePoint，并防范聊天和Teams消息中共享的信息... |- **要监视的位置**[：通过](dlp-policy-reference.md#locations)包括或排除聊天/频道帐户或通讯OneDrive和SharePoint网站Teams范围。 |
|...并限制所有人与未经授权的第三方共享这些项目。"  | - **要采取的操作**[：添加限制](dlp-policy-reference.md#actions)*访问或加密Microsoft 365位置* </br> - 推动对话，讨论触发策略时要采取的操作，包括保护性操作（如共享限制、通知和警报等感知操作）和用户授权操作（如允许用户替代阻止操作） |

此示例未涵盖 DLP 策略的所有配置点，将需要扩展。 但是，在开发自己的 DLP 策略意图陈述时，应该会进行正确的思考。

> [!IMPORTANT]
> 请记住，你 () 位置会影响你是否可以使用敏感信息类型、敏感度标签和保留标签以及可用的操作。 请参阅数据丢失 [防护策略参考](dlp-policy-reference.md#data-loss-prevention-policy-reference)。

## <a name="policy-design-process"></a>策略设计过程

1. 完成以下步骤：
    1. [规划 DLP (数据丢失 ](dlp-overview-plan-for-dlp.md#plan-for-data-loss-prevention-dlp)) - 通过阅读本文，您将：
        1. [确定利益干系人](dlp-overview-plan-for-dlp.md#identify-stakeholders)
        1. [描述要保护的敏感信息类别](dlp-overview-plan-for-dlp.md#describe-the-categories-of-sensitive-information-to-protect)
        1. [设置目标和策略](dlp-overview-plan-for-dlp.md#set-goals-and-strategy)
        1. [定义策略部署计划](dlp-overview-plan-for-dlp.md#policy-deployment)

1. 熟悉数据丢失 [防护策略参考](dlp-policy-reference.md#data-loss-prevention-policy-reference) ，以便了解 DLP 策略的所有组件以及每个组件如何影响策略的行为。

1. 熟悉 DLP [策略模板包含的内容](what-the-dlp-policy-templates-include.md#what-the-dlp-policy-templates-include)。

1. 与关键利益干系人一起制定策略意图声明。 请参阅本文前面的示例。

1. 确定此策略如何适应整体 DLP 策略策略。

> [!IMPORTANT]
> 策略创建后无法重命名。 如果必须重命名策略，则必须创建具有所需名称的新策略并停用旧策略。 因此，请确定所有策略现在将使用的命名结构。 

6. 将策略意图声明中的项映射到配置选项。

7. 确定从哪个策略模板开始，预定义的还是自定义的。

8. 创建策略之前，请浏览模板并组合所有所需信息。 你很可能会发现策略意图声明中未涵盖某些配置点。 没关系。 返回到利益干系人，以找出缺少的任何配置点的要求。 

9. 记录所有策略设置的配置，然后与利益干系人一起查看这些设置。 可以将策略意图语句映射重新用于配置点，配置点现已完全完成。

10. [创建草稿](create-test-tune-dlp-policy.md#create-test-and-tune-a-dlp-policy) 策略并参考回您的 [策略部署](dlp-overview-plan-for-dlp.md#policy-deployment) 计划。

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
- [规划 DLP (数据丢失) ](dlp-overview-plan-for-dlp.md#plan-for-data-loss-prevention-dlp)
- [数据丢失防护策略参考](dlp-policy-reference.md#data-loss-prevention-policy-reference)
- [数据丢失防护策略提示参考](dlp-policy-tips-reference.md#data-loss-prevention-policy-tips-reference)
- [创建、测试和优化 DLP 策略](create-test-tune-dlp-policy.md#create-test-and-tune-a-dlp-policy)