---
title: 通信合规性规划
description: 了解如何规划在组织中使用通信合规性。
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.SupervisoryReview
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
- MOE150
ms.openlocfilehash: c1d55718f93efd9b1053e7ab106c397e0c1d409b
ms.sourcegitcommit: 39838c1a77d4e23df56af74059fb95970223f718
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2022
ms.locfileid: "62187409"
---
# <a name="plan-for-communication-compliance"></a>通信合规性规划

在开始使用 [组织中通信](communication-compliance.md) 合规性之前，信息技术和合规性管理团队应查看重要的规划活动和注意事项。 全面了解和规划以下方面的部署有助于确保实现和使用通信合规性功能顺利进行，并且符合解决方案的最佳实践。

> [!IMPORTANT]
> 通信合规性当前在 Azure 服务依赖项支持的地理区域和国家/地区托管的租户中可用。 若要验证组织是否支持通信合规性，请参阅 Azure[依赖项可用性（按国家/地区）。](/troubleshoot/azure/general/dependency-availability-by-country)

## <a name="transitioning-from-supervision-in-office-365"></a>从监督转换到Office 365

对于在组织中使用监督策略Office 365，您应立即计划转换到 Microsoft 365 通信合规性策略，并需要了解以下要点：

- Office 365中的监督解决方案已被 Microsoft 365 中的通信合规性解决方案完全Microsoft 365。 我们建议在通信合规性中创建新策略，这些策略的设置与现有监督策略相同，以使用新的调查和修正改进。
- 在策略匹配中Office 365保存在监督中的邮件不能移动或共享到 Microsoft 365。
- 对于在转换过程中并行使用这两个解决方案的组织，每个解决方案中使用的策略必须具有唯一的策略名称。 在过渡期间，可以在两种策略之间共享组和自定义关键字词典。

有关停用信息，Office 365，请参阅Microsoft 365[路线图](https://www.microsoft.com/microsoft-365/roadmap)了解详细信息。

## <a name="work-with-stakeholders-in-your-organization"></a>与组织中的利益干系人合作

确定组织中适当的利益干系人，以便协作以对通信合规性警报采取措施。 一些建议的利益干系人是组织以下领域的人员，他们需要考虑包括在初始[](communication-compliance.md#workflow)规划和端到端通信合规性工作流中：

- 信息技术
- 合规性
- 隐私
- 安全性
- 人力资源
- 法律

## <a name="plan-for-the-investigation-and-remediation-workflow"></a>规划调查和修正工作流

### <a name="permissions"></a>权限

选择专门的利益干系人，以定期监视和查看警报和事例[，Microsoft 365 合规中心。](https://compliance.microsoft.com/) 确保您了解如何将用户和利益干系人分配给组织中不同的通信合规性角色组。

> [!IMPORTANT]
> 配置角色组之后，可能需要长达 30 分钟时间将角色组权限应用到整个组织的已分配用户。

有六个角色组用于配置管理通信合规性功能的初始权限。 若要使 **通信** 合规性作为菜单中的菜单选项Microsoft 365 合规中心并继续这些配置步骤，您必须被分配到以下角色或角色组之一：

- Azure Active Directory [*全局管理员*](/azure/active-directory/roles/permissions-reference#global-administrator)角色
- Azure Active Directory [*合规性管理员*](/azure/active-directory/roles/permissions-reference#compliance-administrator)角色
- Microsoft 365 合规中心 [*组织管理*](/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)角色组
- Microsoft 365 合规中心 [*合规性管理员角色*](/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)组
- *通信合规性* 角色组
- *通信合规性管理员* 角色组

以下角色的成员具有 Communication *Compliance Admin* 角色组中包含的相同解决方案权限：

- Azure Active Directory *全局管理员*
- Azure Active Directory *合规性管理员*
- Microsoft 365 合规中心 *组织管理*
- Microsoft 365 合规中心 *合规性管理员*

> [!IMPORTANT]
> 确保通信合规性或通信合规性管理员角色组 (中始终至少有一个用户，具体取决于你选择) ，以便你的通信合规性配置不会进入"零管理员"方案（如果特定用户离开您的组织）。

根据希望管理通信合规性策略和警报的方式，需要将用户分配给特定角色组来管理不同的通信合规性功能集。 可以选择将具有不同合规性职责的用户分配给特定的角色组，以管理不同区域的通信合规性功能。 或者可以决定将指定管理员、分析者、调查者和查看者的所有用户账户分配到 *通信合规性* 角色组。 使用单个角色组或多个角色组，以充分符合你的合规性管理要求。

配置和管理通信合规性时，请从以下解决方案角色组选项中进行选择：

|**角色**|**角色权限**|
|:-----|:-----|
| **通信合规性** | 使用此角色组在单个组中管理组织的通信合规性。 通过添加指定管理员、分析者、调查者和查看者的所有用户账户，可以在单个组中配置通信合规性权限。 此角色组包含所有通信合规性权限角色。 这一配置是通信合规性快速入门的最简单方式，非常适合不需要为单独用户组定义单独权限的组织。 以通信合规性管理员角色创建策略的用户的邮箱必须托管在 Exchange Online。 |
| **通信合规性管理员** | 使用此角色组进行通信合规性初始配置，后期可将通信合规性管理员隔离到已定义组中。 分配到此角色组的用户可以创建、读取、更新和删除通信合规性策略、全局设置和角色组分配。 分配到此角色组的用户无法查看消息警报。 以通信合规性管理员角色创建策略的用户的邮箱必须托管在 Exchange Online。 |
| **通信合规性分析者** | 使用此组向执行通信合规性分析者操作的用户分配权限。 分配到此角色组的用户可以查看分配其为审阅者的策略，查看消息元数据（而不是消息内容）、升级到其他审阅者，或向用户发送通知。 分析者不能解决挂起的警报。 |
| **通信合规性调查者** | 使用此组向执行通信合规性调查者操作的用户分配权限。 分配到此角色组的用户可以查看消息元数据和内容、升级到其他审阅者、升级到高级 eDiscovery 案例、向用户发送通知、以及解决警报。 |
| **通信合规性查看者** | 使用此组向管理通信报告的用户分配权限。 分配到此角色组的用户可以访问通信合规性主页上的所有报告小组件，并且可以查看所有通信合规性报告。 |

### <a name="supervised-users"></a>受监督用户

在开始使用通信合规性之前，必须确定需要审查谁的通信。 在策略中，用户的电子邮件地址可以标记需要接受监管的人员或组。 这些组的一些示例Microsoft 365组、Exchange通讯组列表、Yammer社区以及Microsoft Teams频道。 你也可以设置特定的排除组或排除组列表，将特定的用户或组排除在审查范围外。 有关通信合规性策略中支持的组类型详细信息，请参阅 [通信合规性入门](communication-compliance-configure.md#step-3-optional-set-up-groups-for-communication-compliance)。

> [!IMPORTANT]
> 通信合规性策略涵盖的用户必须具有 Microsoft 365 E5 合规 许可证、Office 365 企业版高级合规性加载项的 E3 许可证，或包含在 Office 365 企业版 E5 订阅中。 如果你没有现有的 E5 Enterprise，并且想要尝试通信合规性，可以注册[E5](https://go.microsoft.com/fwlink/p/?LinkID=698279)Office 365 企业版试用版。

### <a name="reviewers"></a>审阅者

创建通信合规性策略时，必须确定审阅受监督用户消息的用户。 在策略中，用户的电子邮件地址可以标记负责审查通信的人员或组。 所有审阅者都必须在邮箱上托管Exchange Online且必须分配到 *通信* 合规性分析或 *通信合规性调查* 角色。 分析 (或调查人员) 还必须分配 *通信合规性案例管理* 角色。 审阅者添加到策略时，他们会自动收到一封电子邮件，通知他们分配到此策略，并提供有关审阅过程的信息的链接。

### <a name="groups-for-supervised-users-and-reviewers"></a>受监督用户和审阅者的组

若要简化设置，请为需要审阅其通信的人创建组，为审阅这些通信的人创建组。 如果你已经在使用组，可能需要创建若干个组。 例如，如果想要监管两个不同组人员之间的通信，或者指定一个不受监管的组，这时候就需要创建若干个组。 在策略中分配通讯组时，该策略监视来自通讯组中每个用户的所有电子邮件。 在策略中Microsoft 365组时，策略将监视发送到该组的所有电子邮件，而不是每个组的成员收到的单个电子邮件。

向通信合规性策略添加组和通讯组列表是整体条件和规则集的一部分，因此策略支持的最大组和通讯组列表数因也添加到策略中的条件数而异。 每个策略应支持大约 20 个组或通讯组列表，具体取决于策略中出现的其他条件数。

使用下图帮助配置组织中的组以实施通信合规性策略：

| **策略成员** | **支持的组** | **不支持的组** |
|:-----|:-----|:-----|
|受监督用户 <br> 已排除用户 | 通讯组 <br> Microsoft 365 组 | 动态通讯组 <br> 嵌套通讯组 <br> 启用邮件的安全组 <br> Microsoft 365成员资格的组 |
| 审阅者 | 无 | 通讯组 <br> 动态通讯组 <br> 嵌套通讯组 <br> 启用邮件的安全组 |

### <a name="privacy"></a>隐私

保护具有策略匹配项的用户的隐私非常重要，并且有助于在通信合规性警报的数据调查和分析审查中提高对象的性。 此设置仅适用于显示通信合规性解决方案的用户名。 它不会影响名称在其他合规性解决方案或管理中心中的显示方式。

对于通信合规性匹配的用户，可以在通信合规性设置中选择以下 **设置之一**：

- **显示用户名的** 匿名版本：用户名被匿名处理，以防止 *Communication Compliance Analyst* 角色组的用户看到与策略警报相关联的用户。 通信合规 *调查角色* 组的用户将始终看到用户名，而不是匿名版本。 例如，用户在通信合规性体验的所有方面都会显示随机化假名，如"AnonIS8-988"。 选择此设置会匿名处理具有当前和过去策略匹配项的所有用户，并适用于所有策略。 选择此选项后，通信合规性警报详细信息中的用户配置文件信息将不可用。 但是，将新用户添加到现有策略或向新策略分配用户时，将显示用户名。 如果选择关闭此设置，将显示具有当前或过去策略匹配项的所有用户的用户名。
- **不显示用户名的** 匿名版本：将显示通信合规性警报的所有当前和过去策略匹配项的用户名。 用户配置文件信息 (所有通信合规性警报) 显示的名称、职务、别名以及组织或部门信息。

## <a name="plan-for-policies"></a>规划策略

使用针对不当内容、敏感信息和法规遵从性的预定义[](communication-compliance-policies.md#policy-templates)模板，可快速轻松地创建通信合规性策略。 通过自定义通信合规性策略，可以灵活地检测和调查特定于您的组织和要求的问题。

规划通信合规性策略时，请考虑以下方面：

- 请考虑将组织中所有用户添加为通信合规性策略的作用域内用户。 在某些情况下，将特定用户标识为个别策略的作用域内非常有用，但大多数组织应在针对骚扰或非法检测优化的通信合规性策略中包括所有用户。
- 配置 100% 要审阅的通信百分比，以确保策略捕获组织通信中关注的所有问题。
- 您可以扫描来自[第三方源的通信](communication-compliance-channels.md#third-party-sources)，以搜索导入到组织邮箱Microsoft 365的数据。 若要查看这些平台中的通信，需要先配置这些服务的连接器，然后通信策略才能监视满足策略条件的邮件。
- 在自定义通信合规性策略中，策略可以支持监视除英语语言外的语言。 使用[你选择的语言](communication-compliance-policies.md#custom-keyword-dictionaries)生成冒犯性字词的自定义关键字词典，或者使用可训练的分类器在 Microsoft 365[](classifier-get-started-with.md)中构建你自己的机器学习Microsoft 365。
- 所有组织都有不同的通信标准和策略需求。 使用通信合规性策略条件监视特定 [关键字，](communication-compliance-policies.md#conditional-settings) 或监视具有自定义敏感信息 [类型的特定类型的信息](create-a-custom-sensitive-information-type.md)。

## <a name="creating-a-communication-compliance-policy-walkthrough"></a>创建通信合规性策略演练

想要查看有关设置新通信合规性策略和修正警报的深入演练？ 观看以下 15 分钟的视频，了解通信合规性策略如何帮助您检测不当邮件、调查潜在违反和修正合规性问题。
<br>
<br>

>[!VIDEO https://www.microsoft.com/videoplayer/embed/RWNchy]
<br>

## <a name="ready-to-get-started"></a>准备好开始了吗？

若要为 Microsoft 365 组织配置通信合规性，请参阅为[Microsoft 365](communication-compliance-configure.md)配置通信合规性或查看[Contoso](communication-compliance-case-study.md)的案例研究，以及他们如何快速配置通信合规性策略来监视 Microsoft Teams 中的内容，Exchange Online，Yammer通信。
