---
title: 内部风险管理入门
description: 在组织中配置内部风险管理。
keywords: Microsoft 365- 预览体验计划风险管理、风险管理、合规性
localization_priority: Normal
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: 4ddc063c3388770304667c532585f5242ba93011
ms.sourcegitcommit: a0185d6b0dd091db6e1e1bfae2f68ab0e3cf05e5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/13/2021
ms.locfileid: "58247875"
---
# <a name="get-started-with-insider-risk-management"></a>内部风险管理入门

使用内部风险管理策略来确定风险活动和管理工具，以对组织的风险警报采取行动。 完成以下步骤以设置先决条件并配置内部风险管理策略。

> [!IMPORTANT]
> 内部Microsoft 365管理解决方案提供了租户级选项，帮助客户促进用户级别的内部管理。 租户级别管理员可以设置权限，为组织成员提供对此解决方案的访问权限，在 Microsoft 365 合规中心 中设置数据连接器以导入相关的数据，以支持用户级别识别可能存在风险的活动。 客户确认与个人用户的行为、字符或绩效相关的见解（与雇佣关系相关）由管理员计算，并提供给组织其他人使用。 此外，客户确认他们必须自行执行与个人用户的行为、字符或与雇佣相关的性能方面的完全调查，而不只是依赖于内部风险管理服务的见解。 客户应单独负责使用 Microsoft 365 内部风险管理服务，以及符合所有适用法律（包括与个人用户标识相关的法律以及任何修正操作）的任何关联功能或服务。

有关内部风险策略如何有助于管理组织中风险的信息，请参阅预览体验成员风险管理[Microsoft 365。](insider-risk-management.md)

## <a name="subscriptions-and-licensing"></a>订阅和许可

在开始使用内部风险管理之前，你应该确认你的Microsoft 365[订阅](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans)和任何加载项。 若要访问和使用内部风险管理，你的组织必须拥有以下订阅或加载项之一：

- Microsoft 365 E5 订阅（付费或试用版本）
- Microsoft 365 E3 订阅 + Microsoft 365 E5 合规加载项
- Microsoft 365 E3 订阅 + Microsoft 365 E5 预览体验成员风险管理加载项
- Microsoft 365 A5 订阅（付费或试用版本）
- Microsoft 365 A3 订阅 + Microsoft 365 A5 合规加载项
- Microsoft 365 A3 订阅 + Microsoft 365 A5 预览体验成员风险管理加载项
- Microsoft 365 G5 订阅（付费或试用版本）
- Microsoft 365 G3订阅 + Microsoft 365 G5 合规性加载项
- Microsoft 365 G3订阅 + Microsoft 365 G5 内部风险管理加载项
- Office 365 E3 + Enterprise移动性和安全性 E3 + Microsoft 365 E5 合规加载项

必须为包含在内部风险管理策略中的用户分配上述许可证之一。

如果你没有现有的 Microsoft 365 企业版 E5 计划，并且想要尝试内部风险管理，可以将[Microsoft 365](/office365/admin/try-or-buy-microsoft-365)添加到现有订阅或注册 E5 Microsoft 365 企业版试用版。 [](https://www.microsoft.com/microsoft-365/enterprise)

## <a name="step-1-enable-permissions-for-insider-risk-management"></a>步骤 1：为内部风险管理启用权限

> [!IMPORTANT]
> 配置角色组之后，可能需要长达 30 分钟时间将角色组权限应用到整个组织的已分配用户。

有四个角色组用于配置管理内部风险管理功能的权限。 若要继续这些配置步骤，租户管理员必须先将你分配到 **预览** 体验成员风险管理或 **内部风险管理管理员角色** 组。 若要在初始配置后访问和管理内部风险管理功能，用户必须至少是一个内部风险管理角色组的成员。

>[!IMPORTANT]
>根据你选择的选项 (确保你的内部风险管理或内部风险管理管理员角色组中始终至少有一个用户) 以便你的内部风险管理配置不会进入"零管理员"方案（如果特定用户离开组织）。

根据合规性管理团队的结构，有选项将用户分配到特定角色组，以管理不同的预览体验计划风险管理功能集。 若要查看管理 **角色** 组Microsoft 365 合规中心"权限"选项卡，您需要被分配到组织管理角色组，或需要分配有 *"角色* 管理"角色。 配置内部风险管理时，请从以下角色组选项中进行选择：

| **角色组** | **角色权限** |
| :------------- | :------------------- |
| **内部风险管理** | 使用此角色组来管理单个组中组织的预览体验成员风险管理。 通过添加指定管理员、分析师、研究人员和审核员的所有用户帐户，可以在单个组中配置内部风险管理权限。 此角色组包含所有内部风险管理权限角色和相关权限。 此配置是快速开始使用内部风险管理的最简单方法，非常适合不需要为单独的用户组定义单独权限的组织。 **_使用此_** 配置时，应确保始终为此角色组分配至少一个用户，以确保策略按预期工作，以便用户可以创建和编辑策略、配置解决方案设置以及查看策略运行状况警告。|
| **内部风险管理管理员** | 使用此角色组最初配置内部风险管理，稍后再将内部风险管理员分为一个定义的组。 此角色组的用户可启用和查看分析见解，并创建、读取、更新和删除内部风险管理策略、全局设置和角色组分配。 **_使用此_** 配置时，应确保始终为此角色组分配至少一个用户，以确保策略按预期工作，以便用户可以创建和编辑策略、配置解决方案设置以及查看策略运行状况警告。 |
| **预览体验计划风险管理分析员** | 使用此组为将充当预览体验成员案例分析员的用户分配权限。 此角色组的用户可以访问和查看所有内部风险管理警报、案例、分析见解和通知模板。 他们无法访问内部风险内容资源管理器。 |
| **预览体验计划风险管理调查员** | 使用此组为将充当预览体验成员、风险数据执行者的用户分配权限。 此角色组的用户可以访问所有事例的内部风险管理警报、案例、通知模板和内容资源管理器。 |
| **内部风险管理审核员** | 使用此组向将审核内部风险管理活动的用户分配权限。 此角色组的用户可以访问内部风险审核日志。 |

> [!NOTE]
> 这些角色组当前在 PIM Privileged Identity Management (上) 。 若要了解有关 PIM 的更多信息，请参阅在 Privileged Identity Management 中分配[Azure AD 角色](/azure/active-directory/privileged-identity-management/pim-how-to-add-role-to-user)。

### <a name="add-users-to-an-insider-risk-management-role-group"></a>将用户添加到内部风险管理角色组

完成以下步骤以将用户添加到内部风险管理角色组：

1. 使用 Microsoft 365 组织中的管理员账户凭据登录 [https://compliance.microsoft.com/permissions](https://compliance.microsoft.com/permissions)。

2. 在安全 &amp; 合规中心中，转到“**权限**”。 选择链接以查看和管理 Office 365 中的角色。

3. 选择要添加用户的内部风险管理角色组，然后选择"**编辑角色组"。**

4. 从左侧导航窗格中选择“**选择成员**”，然后选择“**编辑**”。

5. 选择“**添加**”，然后选中希望添加到角色组的所有用户的复选框。

6. 选择“**添加**”，然后选择“**完成**”。

7. 选择“**保存**”以将用户添加到角色组。 选择“**关闭**”以完成步骤。

## <a name="step-2-enable-the-microsoft-365-audit-log"></a>步骤 2：启用Microsoft 365 审核日志

内部风险管理使用Microsoft 365审核日志，获取策略和分析见解中标识的用户见解和活动。 审核Microsoft 365是组织中所有活动的摘要，内部风险管理策略可能会使用这些活动生成策略见解。

有关启用审核的逐步操作说明，请参阅 [打开或关闭审核日志搜索](turn-audit-log-search-on-or-off.md)。 打开审核之后，将显示一条消息，内容为正在准备审核日志，你可以在准备完成后几个小时内运行搜索。 此操作只需要执行一次。 有关使用方法方法[Microsoft 365 审核日志，请参阅](search-the-audit-log-in-security-and-compliance.md)搜索审核日志。

## <a name="step-3-enable-and-view-insider-risk-analytics-insights-optional"></a>步骤 3：启用和查看内部风险分析见解 (可选) 

通过内部风险管理分析，你可以对组织中潜在的内部风险进行评估，而无需配置任何内部风险策略。 此评估可以帮助组织确定用户风险更高的潜在领域，并可帮助确定可能考虑配置的预览体验计划风险管理策略的类型和范围。 此评估还可以帮助您确定对现有策略进行其他许可或未来优化的需求。 分析扫描结果最多可能需要 48 小时，才能将见解作为报告提供进行审阅。 若要了解有关分析见解的详细信息，请参阅预览体验成员风险管理设置：分析 [ (预览) ](insider-risk-management-settings.md#analytics-preview) 并观看 [预览](https://www.youtube.com/watch?v=5c0P5MCXNXk) 体验成员风险管理分析视频，以帮助了解分析如何有助于加快识别潜在内部风险并帮助你快速采取行动。

若要启用内部风险分析，你必须是 *内部* 风险管理、内部风险管理管理员或全局Microsoft 365 *组* 的成员。 

完成以下步骤以启用内部风险分析：

1. In the [Microsoft 365 合规中心，](https://compliance.microsoft.com)go to **Insider risk management**.
2. 在 **"内部** 风险管理概述"选项卡上的"扫描 **组织卡中的** 内部风险"中选择" **运行扫描** "。此操作将打开组织的分析扫描。 您还可以在组织中打开扫描，方法为导航到"内部风险设置""分析 (预览版) 并启用"扫描租户的用户活动  >  **"，** 以确定 **潜在的内部风险**。
3. 在" **分析详细信息"** 窗格中，选择" **运行扫描"开始组织的扫描**。 分析扫描结果最多可能需要 24 小时，才能将见解作为报告提供进行审阅。

查看分析见解后，选择内部风险策略并配置最符合组织的内部风险缓解策略的相关先决条件。

## <a name="step-4-configure-prerequisites-for-policies"></a>步骤 4：配置策略的先决条件

大多数内部风险管理策略都有先决条件，必须为策略指示器配置这些先决条件，以生成相关活动警报。 根据计划为组织配置的策略配置相应的先决条件。

### <a name="configure-microsoft-365-hr-connector"></a>配置Microsoft 365 HR 连接器

内部风险管理支持导入从第三方风险管理和人力资源平台导入的用户和日志数据。 利用 Microsoft 365 Human Resources (HR) 数据连接器，你可以从 CSV 文件中提取人力资源数据，包括用户终止日期、上次雇佣日期、绩效改善计划通知、绩效考核操作和工作级别更改状态。 此数据可帮助预览体验计划风险管理策略中警报指标，是在你的组织中配置完全风险管理范围的重要组成部分。 如果为组织配置多个 HR 连接器，内部风险管理将自动拉取所有 HR 连接器中的指示器。

以下Microsoft 365模板时，需要以下 HR 连接器：

- 脱离用户数据盗窃
- 离职用户的安全策略违规活动
- 心怀不满员工的安全策略违规活动
- 心怀不满用户的数据泄露活动

有关[为组织](import-hr-data.md)配置 HR 连接器的Microsoft 365指南，请参阅设置连接器以导入 HR 数据文章。 配置 HR 连接器后，返回到这些配置步骤。

### <a name="configure-data-loss-prevention-dlp-policies"></a>配置 DLP 策略 (数据丢失) 策略

内部风险管理支持使用 DLP 策略来帮助识别针对高严重性级别 DLP 警报向不需要的各方有意或意外泄露敏感信息。 使用任何"数据泄露"模板配置内部风险管理策略时，必须为该策略分配特定的 DLP 策略。

DLP 策略可帮助识别用户，以在针对敏感信息的高风险性 DLP 警报的内部风险管理中激活风险评分，这是在组织中配置完全风险管理覆盖的重要部分。 有关内部风险管理和 DLP 策略集成以及规划注意事项的信息，请参阅 [预览体验成员风险管理策略](insider-risk-management-policies.md#general-data-leaks)。

> [!IMPORTANT]
>确保已完成以下操作：
>
>- 您可以在 DLP 和内部风险管理策略中了解并正确配置范围内用户，以生成预期策略范围。
>- 确保 DLP **策略中** 用于这些模板的内部风险管理的"事件报告"设置已针对高严重性级别警报进行配置。 内部风险管理警报不会从 DLP 策略生成，"事件报告"字段设置为 *"低*"或"中 *"。*

使用下列策略模板时需要 DLP 策略：

- 常规数据泄露
- 优先用户的数据泄露

有关 [为组织配置 DLP](create-test-tune-dlp-policy.md) 策略的分步指南，请参阅创建、测试和调整 DLP 策略一文。 配置 DLP 策略后，返回到这些配置步骤。

### <a name="configure-priority-user-groups"></a>配置优先级用户组

内部风险管理包括对向策略分配优先用户组的支持，以帮助标识具有关键职位、高级数据和网络访问或过去风险行为历史记录的用户的唯一风险活动。 创建优先级用户组并将用户分配到组帮助将策略的范围确定为这些用户呈现的独特情况。

使用下列策略模板时需要优先级用户组：

- 优先用户的安全策略违规
- 优先用户的数据泄露

有关 [创建优先用户组](insider-risk-management-settings.md#priority-user-groups-preview) 的分步指南，请参阅内部风险管理设置入门文章。 配置优先级用户组后，返回到这些配置步骤。

### <a name="configure-physical-badging-connector-optional"></a>配置物理保护连接器 (可选) 

内部风险管理支持从物理控制和访问平台导入用户和日志数据。 物理密码连接器允许你从 JSON 文件拉取访问数据，包括用户 ID、访问点 ID、访问时间和日期以及访问状态。 此数据可帮助预览体验计划风险管理策略中警报指标，是在你的组织中配置完全风险管理范围的重要组成部分。 如果为组织配置了多个物理标记连接器，内部风险管理会自动从所有物理标记连接器提取指示器。 使用所有内部风险策略模板时，物理保护连接器的信息会补充其他内部风险信号。

> [!IMPORTANT]
> 若要让内部风险管理策略使用与离开和终止用户相关的信号数据，并将这些信号数据与物理控制和访问平台的事件数据关联，还必须配置 Microsoft 365 HR 连接器。 如果在未启用 Microsoft 365 HR 连接器的情况下启用物理保护连接器，内部风险管理策略将仅处理针对组织中用户的未经授权的物理访问的事件。

有关 [为组织](import-physical-badging-data.md) 配置物理保护连接器的分步指南，请参阅设置连接器以导入物理保护数据一文。 配置连接器后，返回到这些配置步骤。

### <a name="configure-microsoft-defender-for-endpoint-optional"></a>为终结点配置 Microsoft Defender (可选) 

[Microsoft Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) 是一个企业终结点安全平台，旨在帮助企业网络预防、检测、调查和响应高级威胁。 为了更好地查看组织中安全违规的情况，你可以导入并筛选 Defender for Endpoint 警报，以用于从内部风险管理安全违反策略模板创建的策略中使用的活动。

如果你创建违反安全策略，则需要在你的组织中配置 Microsoft Defender for Endpoint，并启用 Defender for Endpoint 以在 Defender 安全中心进行内部风险管理集成，以导入安全违反警报。 有关要求详细信息，请参阅 Microsoft [Defender for Endpoints](/windows/security/threat-protection/microsoft-defender-atp/minimum-requirements) 的最低要求文章。

请参阅 [在 Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/advanced-features#share-endpoint-alerts-with-microsoft-compliance-center) 中配置高级功能一文，了解为内部风险管理集成配置 Defender for Endpoint 的分步指南。 配置适用于终结点的 Microsoft Defender 后，返回到这些配置步骤。

## <a name="step-5-configure-insider-risk-settings"></a>步骤 5：配置内部风险设置

[内部风险设置](insider-risk-management-settings.md) 适用于所有内部风险管理策略，无论你在创建策略时选择了哪个模板。 设置使用位于内部风险管理选项卡顶部的 **内部风险管理** 控件进行配置。 这些设置控制隐私、指示器、监视窗口和智能检测。

在配置策略之前，请定义以下内部风险设置：

1. In the [Microsoft 365 合规中心，](https://compliance.microsoft.com)go to **Insider risk management** and select Insider risk **settings** from the top-right corner of any page.
2. 在 **"隐私** "页上，选择用于显示策略通知的用户名的隐私设置。
3. 在 **"指示器"** 页上，选择要应用于所有内部风险策略的警报指示器。

    > [!IMPORTANT]
    > 为了接收策略中定义的风险活动的警报，必须选择一个或多个指示器。 如果未在内部风险策略中设置指示器，则这些指示器在内部风险策略中将不可选择。

4. 在 **"策略时间范围**"页上，选择要在 [](insider-risk-management-settings.md#policy-timeframes)触发内部风险策略匹配时为用户生效的策略时间范围。
5. 在 **"智能检测"** 页上，为内部风险策略配置以下设置：
    - [文件类型排除项](insider-risk-management-settings.md#file-type-exclusions)
    - [异常文件活动的阈值](insider-risk-management-settings.md#threshold-for-unusual-file-activity)
    - [警报音量级别](insider-risk-management-settings.md#alert-volume)
    - [Microsoft Defender for Endpoint 警报状态](insider-risk-management-settings.md#microsoft-defender-for-endpoint-preview)
    - [域设置](insider-risk-management-settings.md#domains-preview)
6. 在"**导出警报"** 页上，根据需要，使用 Office 365 管理 API 导出内部风险警报信息。
7. 在" **优先级用户组"** 页上，创建优先级用户组，如果未在步骤 3 中创建，则 **添加用户**。
8. 在 **"Power Automate** 流"页上，配置来自内部风险流模板的流或创建新流。 有关 [分步指南](insider-risk-management-settings.md#power-automate-flows-preview) ，请参阅内部风险管理设置入门文章。
9. 在" **优先级资源"页上**，配置优先级资源以使用物理保护连接器导入的物理控制和访问平台的数据。 有关 [分步指南](insider-risk-management-settings.md#priority-physical-assets-preview) ，请参阅内部风险管理设置入门文章。
10. 在 **"Microsoft Teams"** 页上，Microsoft Teams与内部风险管理集成，以针对案例或用户协作自动创建团队。 有关 [分步指南](insider-risk-management-settings.md#microsoft-teams-preview) ，请参阅内部风险管理设置入门文章。
11. 选择 **"保存** "，为内部风险策略启用这些设置。

## <a name="step-6-create-an-insider-risk-management-policy"></a>步骤 6：创建内部风险管理策略

预览体验计划风险管理策略包括已分配的用户并定义为警报配置哪些类型的风险指示器。 必须配置策略，活动才能触发警报。 使用策略向导创建新的内部风险管理策略。

1. 在 [Microsoft 365 合规中心](https://compliance.microsoft.com)中，转到 **预览体验计划** ，然后选择" **策略** 选项卡。
2. 选择 **创建策略** 以打开策略向导。
3. 在 **“策略模板”** 页面上，选择一个策略类别，然后为新策略选择模板。 这些模板由定义要检测并调查的风险活动的条件和指标。 查看模板先决条件、触发事件和检测到的活动，以确认此策略模板符合你的需要。

    > [!IMPORTANT]
    > 某些策略模板包含为策略配置以生成相关警报的先决条件。 如果尚未配置适用的策略先决条件，请参阅上面的 **步骤4**。

4. 选择“**下一步**”以继续。
5. 在 **名称和说明** 页上，完成以下字段：
    - **名称（必需）**：输入策略的友好名称。 创建策略后，不能更改此名称。
    - **说明（可选）**：输入策略的说明。

6. 选择“**下一步**”以继续。
7. 在 **用户和组** 页上，选择 **"包括所有用户和组** 或 **包括特定的用户和组** 以定义策略中包含的用户或组，或者选择了基于用户的优先级模板； 选择 **添加或编辑优先级用户组**。 选择此选项 **包括所有用户和组** 将查找触发组织中所有用户和组的事件，以便开始为策略分配风险分数。 通过 **包括特定用户和组** 可定义要分配到该策略的用户和组。
8. 选择“**下一步**”以继续。
9. 在 **“要优先排序的内容”** 页面上，可以分配（如果需要）要优先排序的源，这增加了为这些源生成高严重性警报的机会。 选择下列选项之一：

    - **我希望将 SharePoint 网站、敏感度标签和/或敏感信息类型指定为优先级**。 选择此选项将在向导中启用详细信息页面以配置这些通道。
    - **我不想指定优先级内容（创建策略后你将能够指定）**。 选择此选项将跳过向导中的频道详细信息页面。

10. 选择“**下一步**”以继续。

11. 如果选择 **我想在上一步中将 SharePoint 网站、敏感度标签和/或敏感信息类型指定为优先级内容** ，你将看到 *SharePoint 网站*、 *敏感信息类型* 和 *敏感度标签* 的详细信息页面。 使用这些详细信息页面定义 SharePoint、敏感信息类型和敏感度标签以在策略中确定优先级。

    - **SharePoint** 选项： **添加 SharePoint** ，然后选择你有权访问和要设置优先顺序的 SharePoint 网站。 例如，将 *"group1@contoso.sharepoint.com/sites/group1"*。
    - **敏感信息类型**：选择 **添加敏感信息类型** 并选择要确定优先顺序的敏感度类型。 例如， *"美国银行帐户帐号"* ， *"信用卡号"*。
    - **敏感度标签**： 选择 **添加敏感度标签**，然后选择要设置优先级的标签。 例如， *机密* ， *"机密*。

12. 选择“**下一步**”以继续。
13. 在 **指标及触发事件** 页面上，你将在 **预览体验计划风险设置** > **指标** 页面看到到您定义为可用的 [指标](insider-risk-management-settings.md#indicators)。 如果在向导开头选择了 *数据泄露* 模板，则必须从 **DLP 策略** 下拉列表中选择 DLP 策略，以启用触发策略指示器或选择内置触发事件。

    > [!IMPORTANT]
    > 如果无法选中此页上的指标，需要选择要为所有策略启用的指标。 可使用向导中的 **打开指标** 按钮，或选择 **预览体验计划风险管理** > **设置** > **策略指示器** 标记。

    选择要应用于策略的指标。 如果您不想对这些指标使用默认策略阈值设置，请禁用 **“使用Microsoft建议的使用默认阈值”**，然后为每个选定的指标输入阈值。

    - 如果已选择至少一 *Office* 或 *Device* 指示器，请根据情况选择 **风险评分** 分数。 风险分数仅应用于所选指示器。
    - 如果选择了 *数据盗窃* 或 *数据泄露* 策略模板，请选择一个或多个 **序列检测** 方法以及一种 **累积泄露检测** 方法，以应用到该策略。

14. 选择“**下一步**”以继续。
15. 在" **指示器阈值** 页面上，选择使用默认指示器阈值或为各个指示器指定自定义阈值的选项。 对于每个指标，选择适当的级别以生成所需的活动警报级别。
16. 选择“**下一步**”以继续。
17. 在 **审阅** 页面上，查看为策略选择的设置以及针对你的选择选择的任何建议或警告。 选择 **“编辑”** 以更改任何策略值，或选择 **“提交”** 以创建并激活该策略。

## <a name="next-steps"></a>后续步骤

完成这些步骤以创建首个内部风险管理策略后，你将在大约 24 小时后开始从活动指示器接收警报。 使用本文步骤 4 中的指导或创建新的内部风险策略 中的步骤根据需要配置 [其他策略](insider-risk-management-policies.md#create-a-new-policy)。

若要详细了解如何调查内部风险警报和 **警报仪表板**，请参阅 [预览体验成员风险管理活动](insider-risk-management-activities.md#alert-dashboard)。
