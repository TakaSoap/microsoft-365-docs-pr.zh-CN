---
title: 内部风险管理入门
description: 在组织中配置内部风险管理。
keywords: Microsoft 365- 预览体验计划风险管理、风险管理、合规性
ms.localizationpriority: medium
ms.service: O365-seccomp
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection:
- m365-security-compliance
- m365solution-insiderrisk
- m365initiative-compliance
ms.custom: admindeeplinkCOMPLIANCE
ms.openlocfilehash: ca858aaf10c453a3fa333288fd5e44c62d20cb08
ms.sourcegitcommit: ac0ae5c2888e2b323e36bad041a4abef196c9c96
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/12/2022
ms.locfileid: "64783900"
---
# <a name="get-started-with-insider-risk-management"></a>内部风险管理入门

使用内部风险管理策略来识别风险活动和管理工具，以处理组织中的风险警报。 完成以下步骤以设置先决条件并配置内部风险管理策略。

> [!IMPORTANT]
> Microsoft 365预览体验成员风险管理解决方案提供了租户级别选项，以帮助客户在用户级别促进内部治理。 租户级别管理员可以设置权限，为组织成员提供对此解决方案的访问权限，并在Microsoft 365 合规中心中设置数据连接器以导入相关数据，以支持用户级别识别潜在风险活动。 客户确认与个人用户的行为、性格或性能有重大关系的见解可由管理员计算，并提供给组织中的其他人。 此外，客户还承认，他们必须对个人用户的行为、性格或性能进行与就业有重大关系的完整调查，而不只是依赖于内部风险管理服务的见解。 客户完全负责使用Microsoft 365预览体验成员风险管理服务，以及符合所有适用法律的任何关联功能或服务，包括与个人用户标识和任何补救措施相关的法律。

有关内部风险策略如何帮助你管理组织中的风险的详细信息，请参阅 [Microsoft 365 中的预览体验成员风险管理](insider-risk-management.md)。

## <a name="subscriptions-and-licensing"></a>订阅和许可

在开始进行内部风险管理之前，应确认[Microsoft 365订阅](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans)和任何加载项。 若要访问和使用内部风险管理，组织必须具有以下订阅或加载项之一：

- Microsoft 365 E5/A5/F5/G5 订阅 (付费版或试用版) 
- Microsoft 365 E3/A3/F3/G3 订阅 + Microsoft 365 E5/A5/F5/G5 合规性加载项
- Microsoft 365 E3/A3/F3/G3 订阅 + Microsoft 365 E5/A5/F5/G5 预览体验成员风险管理加载项
- Office 365 E3 订阅 + 企业移动性和安全性 E3 + Microsoft 365 E5 合规加载项

必须为包含在内部风险管理策略中的用户分配上述许可证之一。

> [!IMPORTANT]
> 预览体验成员风险管理目前在地理区域和 Azure 服务依赖项支持的国家/地区托管的租户中可用。 若要验证组织是否支持内部风险管理，请参阅[按国家/地区提供的 Azure 依赖项。](/troubleshoot/azure/general/dependency-availability-by-country)

如果没有现有的 Microsoft 365 企业版 E5 计划，并且想要尝试内部风险管理，可以将[Microsoft 365添加](/office365/admin/try-or-buy-microsoft-365)到现有订阅或[注册](https://www.microsoft.com/microsoft-365/enterprise)试用版 Microsoft 365 企业版 E5。

## <a name="recommended-actions-preview"></a>建议的操作 (预览) 

建议的操作可帮助组织快速进行内部风险管理。 建议的操作包括在 **“概述** ”页上，可帮助你完成配置和部署策略的步骤。

![内部风险管理推荐操作。](../media/insider-risk-recommended-actions.png)

以下建议可用于帮助你开始使用或最大化内部风险管理配置：

- **启用审核**：启用后，组织中的用户和管理员活动将记录到Microsoft 365审核日志。 预览体验成员风险策略和分析扫描使用此日志来检测风险活动。
- **获取用户风险管理的权** 限：对预览体验成员风险管理功能的访问级别取决于分配的角色组。 若要访问和配置建议的操作，必须将用户分配到 *预览体验成员风险管理* 或 *预览体验成员风险管理管理员* 角色组。
- **选择策略指示器**：指示器实质上是要检测和调查的用户活动。 可以选择指示器来跟踪多个Microsoft 365位置和服务的活动。
- **扫描潜在的内部风险**：运行分析扫描以发现组织中发生的潜在内部风险。评估结果后，查看要设置的建议策略。
- **向其他人分配权限**：如果有其他团队成员负责管理内部风险功能，则需要将其分配给相应的角色组。
- **创建第一个策略**：若要接收有关潜在风险活动的警报，必须根据定义要检测和调查的用户活动的预定义模板设置策略。

此体验中包含的每个建议操作都有四个属性：

- **操作**：建议操作的名称和说明。
- **状态**：建议的操作的状态。 值 *未启动*、 *正在进行*、 *保存以供以后* 使用或 *已完成*。
- **必需或可选**：建议的操作是必需的，还是预览体验成员风险管理功能按预期运行的可选操作。
- **估计完成时间**：估计在数分钟内完成建议操作的时间。

从列表中选择建议，以开始配置内部风险管理。 每项推荐操作都会指导完成建议所需的活动，包括任何要求、预期内容以及在组织中配置功能的影响。   每个建议的操作在配置时会自动标记为已完成，或者需要在配置时手动选择完成的操作。

## <a name="step-1-required-enable-permissions-for-insider-risk-management"></a>步骤 1 (必需): 为内部风险管理启用权限

> [!IMPORTANT]
> 配置角色组之后，可能需要长达 30 分钟时间将角色组权限应用到整个组织的已分配用户。

有六个角色组用于配置内部风险管理功能。 若要在Microsoft 365 合规中心中将 **预览体验成员风险管理** 作为菜单选项提供并继续执行这些配置步骤，必须将你分配给以下角色或角色组之一：

- Azure Active Directory [*全局管理员*](/azure/active-directory/roles/permissions-reference#global-administrator)角色
- Azure Active Directory [*合规性管理员*](/azure/active-directory/roles/permissions-reference#compliance-administrator)角色
- Microsoft 365 合规中心 [*组织管理*](/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)角色组
- Microsoft 365 合规中心 [*合规性管理员*](/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)角色组
- *预览体验成员风险管理* 角色组
- *预览体验成员风险管理管理员* 角色组

根据你希望如何管理内部风险管理策略和警报，你需要将用户分配到特定的角色组，以管理不同的内部风险管理功能集。 可以选择将具有不同合规性责任的用户分配到特定角色组，以管理不同领域的内部风险管理功能。 或者，你可以决定将指定管理员、分析师、调查员和查看者的所有用户帐户分配给预览体验成员风险管理角色组。 使用单个角色组或多个角色组，以充分符合你的合规性管理要求。

使用内部风险管理时，你将从这些角色组选项和解决方案操作中进行选择：

|操作|内部风险管理|预览体验成员风险管理管理员|预览体验计划风险管理分析员|预览体验计划风险管理调查员|预览体验成员风险管理审核员|
|---|---|---|---|---|---|
|配置策略和设置|是|是|否|否|否|
|访问分析见解|是|是|是|否|否|
|访问&调查警报|是|否|是|是|否|
|访问&调查案例|是|否|是|是|否|
|访问&查看内容资源管理器|是|否|否|是|否|
|配置通知模板|是|否|是|是|否|
|查看&导出审核日志|是|否|否|否|是|

> [!IMPORTANT]
> 请确保预 *览体验成员风险管理或预览体验成员风险**管理管理员* 角色组中始终至少有一个用户 (取决于选择) 的选项，以便在特定用户离开组织时，预览体验成员风险管理配置不会进入“零管理员”方案。

以下角色的成员可以将用户分配到预览体验成员风险管理角色组，并具有与 *预览体验成员风险管理管理员* 角色组中包含的相同解决方案权限：

- Azure Active Directory *全局管理员*
- Azure Active Directory *合规性管理员*
- Microsoft 365 合规中心 *组织管理*
- Microsoft 365 合规中心 *合规性管理员*

> [!NOTE]
> PRIVILEGED IDENTITY MANAGEMENT (PIM) 当前不支持这些角色组。 若要了解有关 PIM 的详细信息，请参阅[Privileged Identity Management中分配Azure AD角色](/azure/active-directory/privileged-identity-management/pim-how-to-add-role-to-user)。

### <a name="add-users-to-an-insider-risk-management-role-group"></a>将用户添加到预览体验成员风险管理角色组

完成以下步骤，将用户添加到内部风险管理角色组：

1. 使用[Microsoft 365](https://compliance.microsoft.com)组织中管理员帐户的凭据登录Microsoft 365 合规中心。

2. 在安全 &amp; 合规中心中，转到“**权限**”。 选择链接以查看和管理 Office 365 中的角色。

3. 选择要将用户添加到的内部风险管理角色组，然后选择 **“编辑角色组**”。

4. 从左侧导航窗格中选择“**选择成员**”，然后选择“**编辑**”。

5. 选择“**添加**”，然后选中希望添加到角色组的所有用户的复选框。

6. 选择“**添加**”，然后选择“**完成**”。

7. 选择“**保存**”以将用户添加到角色组。 选择“**关闭**”以完成步骤。

## <a name="step-2-required-enable-the-microsoft-365-audit-log"></a>步骤 2 (所需的) ：启用Microsoft 365审核日志

预览体验成员风险管理对策略和分析见解中标识的用户见解和活动使用Microsoft 365审核日志。 Microsoft 365审核日志是组织内所有活动的摘要，内部风险管理策略可能使用这些活动来生成策略见解。

默认情况下，为 Microsoft 365 组织启用审核。 一些组织可能出于特定原因禁用了审核。 如果组织禁用了审核，则可能是因为其他管理员已将其禁用。 我们建议确认在完成此步骤时可以重新启用审核。

有关启用审核的逐步操作说明，请参阅 [打开或关闭审核日志搜索](turn-audit-log-search-on-or-off.md)。 打开审核之后，将显示一条消息，内容为正在准备审核日志，你可以在准备完成后几个小时内运行搜索。 此操作只需要执行一次。 有关使用 Microsoft 365 审核日志的详细信息，请参阅 [搜索审核日志](search-the-audit-log-in-security-and-compliance.md)。

## <a name="step-3-optional-enable-and-view-insider-risk-analytics-insights"></a>步骤 3 (可选) ：启用和查看内部风险分析见解

内部风险管理分析使你能够在不配置任何内部风险策略的情况下评估组织中的潜在内部风险。 此评估可以帮助组织确定用户风险更高的潜在领域，并可帮助确定可能考虑配置的预览体验计划风险管理策略的类型和范围。 此评估还有助于确定对现有策略进行额外许可或未来优化的需求。 分析扫描结果可能最多需要 48 小时，之后见解才可作为报告可用以供评审。 若要了解有关分析见解的详细信息，请参阅 [预览体验成员风险管理设置：分析](insider-risk-management-settings.md#analytics) 并查看 [预览体验成员风险管理分析视频](https://www.youtube.com/watch?v=5c0P5MCXNXk) ，以帮助了解分析如何帮助加快潜在内部风险的识别，并帮助你快速采取行动。

若要启用内部风险分析，必须是 *预览体验成员风险管理*、*预览体验成员风险管理管理员* 或Microsoft 365 *全局管理员* 角色组的成员。

完成以下步骤以启用内部风险分析：

1. 在 [Microsoft 365 合规中心](https://compliance.microsoft.com)中，转到 **预览体验成员风险管理**。
2. 在“内部风险管理 **概述**”选项卡上的 **“组织卡中的内部风险扫描**”中选择 **“运行扫描**”。此操作启用对组织进行分析扫描。 你还可以通过导航到 **Insider risk settingsAnalytics** >  并启用 **扫描租户的用户活动来识别潜在的内部风险，** 从而在组织中启用扫描。
3. 在 **“分析详细信息** ”窗格上，选择 **“运行扫描”以启动组织的扫描**。 分析扫描结果可能最多需要 48 小时，之后见解才可作为报告可用以供评审。

查看分析见解后，选择内部风险策略，并配置最符合组织内部风险缓解策略的相关先决条件。

## <a name="step-4-recommended-configure-prerequisites-for-policies"></a>步骤 4 (建议) ：为策略配置先决条件

大多数内部风险管理策略都有必须为策略指标配置的先决条件才能生成相关的活动警报。 根据计划为组织配置的策略配置适当的先决条件。

### <a name="configure-microsoft-365-hr-connector"></a>配置 Microsoft 365 HR 连接器

预览体验成员风险管理支持导入从第三方风险管理和人力资源平台导入的用户和日志数据。 Microsoft 365人力资源 (人力资源) 数据连接器允许你从 CSV 文件中提取人力资源数据，包括用户终止日期、上次雇佣日期、性能改进计划通知、性能评审操作和工作级别更改状态。 此数据可帮助预览体验计划风险管理策略中警报指标，是在你的组织中配置完全风险管理范围的重要组成部分。 如果为组织配置了多个 HR 连接器，则内部风险管理会自动从所有 HR 连接器提取指标。

使用以下策略模板时，需要Microsoft 365 HR 连接器：

- 心怀不满用户的数据泄露活动
- 离开用户数据盗窃
- 常规患者数据滥用
- 离职用户的安全策略违规活动
- 心怀不满员工的安全策略违规活动

有关为组织配置 Microsoft 365 HR 连接器的分步指南，请参阅[“设置连接器以导入 HR 数据](import-hr-data.md)”文章。 配置 HR 连接器后，返回到这些配置步骤。

### <a name="configure--a-healthcare-specific-data-connector"></a>配置特定于医疗保健的数据连接器

预览体验成员风险管理支持在现有电子医疗记录 (EMR) 系统上导入从第三方导入的用户和日志数据。 借助 Microsoft Healthcare 和 Epic 数据连接器，可以使用 CSV 文件从 EMR 系统提取活动数据，包括不当的患者记录访问、可疑的卷活动以及编辑和导出活动。 此数据可帮助预览体验计划风险管理策略中警报指标，是在你的组织中配置完全风险管理范围的重要组成部分。

如果为组织配置了多个医疗保健或 Epic 连接器，则内部风险管理会自动支持来自所有医疗保健和 Epic 连接器的事件和活动信号。
使用以下策略模板时，需要使用 Microsoft 365 Healthcare 或 Epic 连接器：

- 常规患者数据滥用

有关为组织配置特定于医疗保健的连接器的分步指南，请参阅 [设置连接器以导入医疗保健数据](import-healthcare-data.md) 或 [设置连接器以导入 Epic EHR 数据](import-epic-data.md) 文章。 配置连接器后，返回到这些配置步骤。

### <a name="configure-data-loss-prevention-dlp-policies"></a>配置数据丢失防护 (DLP) 策略

预览体验成员风险管理支持使用 DLP 策略来帮助识别针对高严重性级别 DLP 警报，将敏感信息有意或意外地暴露给不需要的当事方。 使用任何 **数据泄漏** 模板配置内部风险管理策略时，可以选择为这些类型的警报向策略分配特定的 DLP 策略。

DLP 策略有助于识别用户在内部风险管理中激活针对敏感信息的高严重性 DLP 警报的风险评分，并且是在组织中配置完整风险管理覆盖范围的重要组成部分。 有关内部风险管理和 DLP 策略集成和规划注意事项的详细信息，请参阅 [预览体验成员风险管理策略](insider-risk-management-policies.md#general-data-leaks)。

> [!IMPORTANT]
>确保已完成以下操作：
>
> - 你了解并正确配置 DLP 和预览体验成员风险管理策略中范围内的用户，以生成预期的策略覆盖范围。
> - 确保为与这些模板一起使用的预览体验成员风险管理的 DLP 策略中的 **“事件报告** ”设置配置为 *高* 严重性级别警报。 在“ **事件报告** ”字段设置为 *“低* ”或“ *中*”时，不会从 DLP 策略生成内部风险管理警报。

使用以下策略模板时，DLP 策略是可选的：

- 常规数据泄露
- 优先用户的数据泄露

有关为组织配置 DLP 策略的分步指南，请参阅 [“创建、测试和优化 DLP](create-test-tune-dlp-policy.md) 策略”一文。 配置 DLP 策略后，返回到这些配置步骤。

### <a name="configure-priority-user-groups"></a>配置优先级用户组

预览体验成员风险管理包括支持将优先级用户组分配到策略，以帮助为具有关键位置、数据和网络访问级别较高或过去风险行为历史记录的用户标识唯一风险活动。 创建优先级用户组并将用户分配到组帮助范围策略，以了解这些用户提供的独特情况。

使用以下策略模板时，需要优先级用户组：

- 优先用户的安全策略违规
- 优先用户的数据泄露

有关创建优先级用户组的分步指南，请参阅 [内部风险管理设置](insider-risk-management-settings.md#priority-user-groups-preview) 入门文章。 配置优先级用户组后，返回到这些配置步骤。

### <a name="configure-physical-badging-connector-optional"></a>配置物理损坏连接器 (可选) 

预览体验成员风险管理支持从物理控制和访问平台导入用户和日志数据。 物理错误连接器允许你从 JSON 文件中提取访问数据，包括用户 ID、访问点 ID、访问时间和日期以及访问状态。 此数据可帮助预览体验计划风险管理策略中警报指标，是在你的组织中配置完全风险管理范围的重要组成部分。 如果为组织配置了多个物理损坏连接器，则内部风险管理会自动从所有物理损坏连接器中拉取指示器。 使用所有内部风险策略模板时，来自物理不良连接器的信息会补充其他内部风险信号。

> [!IMPORTANT]
> 若要使用内部风险管理策略并将与离开和终止的用户相关的信号数据与来自物理控制和访问平台的事件数据相关，还必须配置Microsoft 365 HR 连接器。 如果在未启用 Microsoft 365 HR 连接器的情况下启用物理损坏连接器，则内部风险管理策略将仅处理组织中用户未经授权的物理访问事件。

有关为组织配置物理不良连接器的分步指南，请参阅 [“设置连接器以导入物理不良数据](import-physical-badging-data.md) ”文章。 配置连接器后，返回到这些配置步骤。

### <a name="configure-microsoft-defender-for-endpoint-optional"></a>配置Microsoft Defender for Endpoint (可选) 

[Microsoft Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)是一个企业终结点安全平台，旨在帮助企业网络预防、检测、调查和响应高级威胁。 若要更好地了解组织中的安全冲突，可以导入和筛选 Defender for Endpoint 警报，以便在从内部风险管理安全冲突策略模板创建的策略中使用的活动。

如果创建安全违规策略，则需要在组织中配置Microsoft Defender for Endpoint，并在 Defender 安全中心中启用 Defender for Endpoint 进行内部风险管理集成，以导入安全违规警报。 有关要求的详细信息，请参阅[Microsoft Defender for Endpoint文章的最低要求](/windows/security/threat-protection/microsoft-defender-atp/minimum-requirements)。

有关为内部风险管理集成配置 Defender for Endpoint 的分步指南，请参阅 [Defender for Endpoint 文章中的配置高级功能](/windows/security/threat-protection/microsoft-defender-atp/advanced-features#share-endpoint-alerts-with-microsoft-compliance-center) 。 配置Microsoft Defender for Endpoint后，返回到这些配置步骤。

## <a name="step-5-required-configure-insider-risk-settings"></a>步骤 5 (所需的) ：配置预览体验成员风险设置

无论创建策略时选择什么模板，[预览体验成员风险设置](insider-risk-management-settings.md)都适用于所有内部风险管理策略。 设置使用位于内部风险管理选项卡顶部的 **内部风险管理** 控件进行配置。 这些设置控制隐私、指示器、监视窗口和智能检测。

在配置策略之前，请定义以下内部风险设置：

1. 在 [Microsoft 365 合规中心](https://compliance.microsoft.com)中，转到 **预览体验成员风险管理**，并从任何页面的右上角选择 **预览体验成员风险设置**。
2. 在 **“隐私”** 页上，选择用于显示策略警报用户名的隐私设置。
3. 在 **“指标”** 页上，选择要应用于所有内部风险策略的警报指示器。

    > [!IMPORTANT]
    > 若要接收策略中定义的风险活动的警报，必须选择一个或多个指示器。 如果未在设置中配置指标，则在内部风险策略中将无法选择这些指标。

4. 在“ **策略时间范围** ”页上，选择在用户触发内部风险策略匹配时要生效的策略 [时间范围](insider-risk-management-settings.md#policy-timeframes) 。
5. 在 **“智能检测”** 页上，为内部风险策略配置以下设置：
    - [文件类型排除项](insider-risk-management-settings.md#file-type-exclusions)
    - [为提高异常活动的分数而增加的每日事件的最小数目](insider-risk-management-settings.md#minimum-number-of-daily-events-to-boost-score-for-unusual-activity)
    - [警报卷级别](insider-risk-management-settings.md#alert-volume)
    - [Microsoft Defender for Endpoint警报状态](insider-risk-management-settings.md#microsoft-defender-for-endpoint-preview)
    - [域设置](insider-risk-management-settings.md#domains)
6. 在“**导出警报**”页上，根据需要使用Office 365管理 API 启用内部风险警报信息的导出。
7. 在 **“优先级用户组** ”页上，创建优先级用户组，如果未在 **步骤 3** 中创建用户，则添加用户。
8. 在 **Power Automate流** 页上，配置内部风险流模板中的流或创建新流。 有关分步指南，请参阅 [预览体验成员风险管理设置](insider-risk-management-settings.md#power-automate-flows-preview) 入门文章。
9. 在 **“优先级资产”页** 上，将优先级资产配置为使用物理控制和访问平台中由物理损坏连接器导入的数据。 有关分步指南，请参阅 [预览体验成员风险管理设置](insider-risk-management-settings.md#priority-physical-assets-preview) 入门文章。
10. 在 **Microsoft Teams** 页上，启用Microsoft Teams与预览体验成员风险管理的集成，以自动创建用于案例或用户协作的团队。 有关分步指南，请参阅 [预览体验成员风险管理设置](insider-risk-management-settings.md#microsoft-teams-preview) 入门文章。
11. 选择 **“保存** ”可为内部风险策略启用这些设置。

## <a name="step-6-required-create-an-insider-risk-management-policy"></a>步骤 6 (所需的) ：创建内部风险管理策略

预览体验计划风险管理策略包括已分配的用户并定义为警报配置哪些类型的风险指示器。 必须配置策略，活动才能触发警报。 使用策略向导创建新的内部风险管理策略。

1. 在 [Microsoft 365 合规中心](https://compliance.microsoft.com)中，转到 **预览体验计划** ，然后选择" **策略** 选项卡。
2. 选择 **创建策略** 以打开策略向导。
3. 在 **“策略模板”** 页面上，选择一个策略类别，然后为新策略选择模板。 这些模板由定义要检测并调查的风险活动的条件和指标。 查看模板先决条件、触发事件和检测到的活动，以确认此策略模板符合你的需要。

    > [!IMPORTANT]
    > 某些策略模板包含为策略配置以生成相关警报的先决条件。 如果尚未配置适用的策略先决条件，请参阅上面的 **步骤4**。

4. 选择“**下一步**”以继续。
5. 在 **名称和说明** 页上，完成以下字段：
    - **名称（必需）**：输入策略的友好名称。 创建策略后，无法更改此名称。
    - **说明（可选）**：输入策略的说明。

6. 选择“**下一步**”以继续。
7. 在 **用户和组** 页上，选择 **"包括所有用户和组** 或 **包括特定的用户和组** 以定义策略中包含的用户或组，或者选择了基于用户的优先级模板； 选择 **添加或编辑优先级用户组**。 选择此选项 **包括所有用户和组** 将查找触发组织中所有用户和组的事件，以便开始为策略分配风险分数。 通过 **包括特定用户和组** 可定义要分配到该策略的用户和组。 不支持来宾用户帐户。
8. 选择“**下一步**”以继续。
9. 在 **“要优先排序的内容”** 页面上，可以分配（如果需要）要优先排序的源，这增加了为这些源生成高严重性警报的机会。 选择下列选项之一：

    - **我希望将 SharePoint 网站、敏感度标签和/或敏感信息类型指定为优先级**。 选择此选项将在向导中启用详细信息页面以配置这些通道。
    - **我不想指定优先级内容（创建策略后你将能够指定）**。 选择此选项将跳过向导中的频道详细信息页面。

10. 选择“**下一步**”以继续。

11. 如果选择我想要在上一步中 **将SharePoint网站、敏感度标签和/或敏感信息类型指定为优先级内容**，你将看到 *SharePoint网站*、*敏感信息类型* 和 *敏感度标签* 的详细信息页。 使用这些详细信息页面定义 SharePoint、敏感信息类型和敏感度标签以在策略中确定优先级。

    - **SharePoint** 选项： **添加 SharePoint** ，然后选择你有权访问和要设置优先顺序的 SharePoint 网站。 例如，将 *"group1@contoso.sharepoint.com/sites/group1"*。
    - **敏感信息类型**：选择 **添加敏感信息类型** 并选择要确定优先顺序的敏感度类型。 例如， *"美国银行帐户帐号"* ， *"信用卡号"*。
    - **敏感度标签**： 选择 **添加敏感度标签**，然后选择要设置优先级的标签。 例如， *机密* ， *"机密*。

    > [!NOTE]
    > 配置策略并选择优先级 Share Point 网站的用户可以选择他们有权访问的SharePoint网站。 如果当前用户无法在策略中选择SharePoint站点，则具有所需权限的另一个用户稍后可以选择策略的网站，或者应向当前用户授予对所需网站的访问权限。

12. 选择“**下一步**”以继续。
13. 如果已按 *优先级用户* 模板选择常规 *数据泄漏* 或数据泄漏，则会在此策略页的 **“触发器**”中看到自定义触发事件和策略指示器的选项。 可以选择一个 DLP 策略或指示器来触发事件，使分配给策略的用户在活动评分范围内。 如果选择 **“用户”与 DLP) 策略触发事件选项 (数据丢失防护相匹配** ，则必须从 DLP 策略下拉列表中选择一个 DLP 策略，以便为此内部风险管理策略启用 DLP 策略的触发指示器。 如果选择 **用户执行外泄活动触发事件** 选项，则必须为策略触发事件选择一个或多个列出的指示器。

    > [!IMPORTANT]
    > 如果无法选择列出的指示器，那是因为它们未为组织启用。 若要使其可用于选择策略并将其分配给策略，请在 **预览体验成员风险管理** > **设置** > **策略指标** 中启用指标。

    如果选择了其他策略模板，则不支持自定义触发事件。 内置策略触发事件适用，你将继续执行步骤 23，而无需定义策略属性。

14. 选择“**下一步**”以继续。
15. 如果已 *按优先级用户* 模板选择常规 *数据泄漏* 或数据泄漏，并且已选择 **用户执行外泄活动和关联指示器**，则可以选择自定义或默认阈值作为已选择的触发事件的指示器。 选择“ **使用默认阈值 (建议)** 或 **对触发事件使用自定义阈值**。
16. 选择“**下一步**”以继续。
17. 如果已 **为触发事件选择“使用自定义阈值**”，对于在步骤 13 中选择的每个触发事件指示器，请选择适当的级别来生成所需的活动警报级别。
18. 选择“**下一步**”以继续。
19. 在“**策略指示器**”页上，你将在 **“预览体验成员风险设置**”页上看到已定义为可用的 > [指示](insider-risk-management-settings.md#indicators)**器**。 选择要应用于策略的指标。

    > [!IMPORTANT]
    > 如果无法选中此页上的指标，需要选择要为所有策略启用的指标。 可使用向导中的 **打开指标** 按钮，或选择 **预览体验计划风险管理** > **设置** > **策略指示器** 标记。

    如果已选择至少一 *Office* 或 *Device* 指示器，请根据情况选择 **风险评分** 分数。 风险分数仅应用于所选指示器。
    如果选择了 *数据盗窃* 或 *数据泄露* 策略模板，请选择一个或多个 **序列检测** 方法以及一种 **累积泄露检测** 方法，以应用到该策略。

20. 选择“**下一步**”以继续。
21. 在 **“决定是使用默认或自定义指示器阈值** ”页上，选择所选策略指示器的自定义阈值或默认阈值。 选择 **所有指标的“使用默认阈值** ”或指定所选策略指示 **器的自定义阈值** 。 如果已选择“指定自定义阈值”，请选择适当的级别，为每个策略指示器生成所需的活动警报级别。
22. 选择“**下一步**”以继续。
23. 在 **审阅** 页面上，查看为策略选择的设置以及针对你的选择选择的任何建议或警告。 选择 **“编辑”** 以更改任何策略值，或选择 **“提交”** 以创建并激活该策略。

## <a name="next-steps"></a>后续步骤

完成这些步骤以创建第一个预览体验成员风险管理策略后，大约 24 小时后，你将开始收到来自活动指示器的警报。 使用本文第 4 步中的指导或 [创建新的内部风险](insider-risk-management-policies.md#create-a-new-policy)策略中的步骤根据需要配置其他策略。

若要详细了解如何调查内部风险警报和 **警报仪表板**，请参阅 [预览体验成员风险管理活动](insider-risk-management-activities.md#alert-dashboard)。
