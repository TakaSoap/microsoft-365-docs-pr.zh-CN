---
title: 内部风险管理入门
description: 在组织中配置内部风险管理。
keywords: Microsoft 365， 内部风险管理， 风险管理， 合规性
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
ms.openlocfilehash: a995b6fdbbff36c6466f5e55cda9d7e196fa2c02
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50927026"
---
# <a name="get-started-with-insider-risk-management"></a>内部风险管理入门

使用内部风险管理策略来确定风险活动和管理工具，以对组织的风险警报采取行动。 完成以下步骤以设置先决条件并配置内部风险管理策略。

>[!IMPORTANT]
>Microsoft 365 内部风险管理解决方案提供租户级选项，帮助客户促进用户级别的内部治理。 租户级管理员可以设置权限，为组织成员提供对此解决方案的访问权限，在 Microsoft 365 合规中心中设置数据连接器以导入相关的数据，以支持用户级别识别可能存在风险的活动。 客户确认与个人用户的行为、字符或绩效相关的见解（与雇佣关系相关）由管理员计算，并提供给组织其他人使用。 此外，客户确认他们必须自行执行与个人用户行为、字符或与雇佣相关的性能方面的完全调查，而不只是依赖于内部风险管理服务的见解。 客户应单独负责使用 Microsoft 365 内部风险管理服务以及符合所有适用法律（包括与个人用户标识相关的法律以及任何补救措施）的任何关联功能或服务。

有关内部风险策略如何有助于管理组织中风险的信息，请参阅 [Microsoft 365](insider-risk-management.md)中的内部风险管理。

## <a name="subscriptions-and-licensing"></a>订阅和许可

在开始内部风险管理之前，应先确认 [Microsoft 365](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans) 订阅和任何加载项。 若要访问和使用内部风险管理，你的组织必须拥有以下订阅或加载项之一：

- Microsoft 365 E5 订阅（付费或试用版本）
- Microsoft 365 E3 订阅 + Microsoft 365 E5 合规加载项
- Microsoft 365 E3 订阅 + Microsoft 365 E5 预览体验成员风险管理加载项
- Microsoft 365 A5 订阅（付费或试用版本）
- Microsoft 365 A3 订阅 + Microsoft 365 A5 合规加载项
- Microsoft 365 A3 订阅 + Microsoft 365 A5 预览体验成员风险管理加载项
- Microsoft 365 G5 订阅（付费或试用版本）
- Microsoft 365 G3 订阅 + Microsoft 365 G5 合规性加载项
- Microsoft 365 G3 订阅 + Microsoft 365 G5 内部风险管理加载项
- Office 365 E3 订阅 + 企业移动性和安全性 E3 + Microsoft 365 E5 合规性加载项

必须为包含在内部风险管理策略中的用户分配上述许可证之一。

如果你没有现有的 Microsoft 365 企业版 E5 计划，并且想要尝试内部风险管理，可以将[Microsoft 365](/office365/admin/try-or-buy-microsoft-365)添加到现有订阅或注册[](https://www.microsoft.com/microsoft-365/enterprise)Microsoft 365 企业版 E5 的试用版。

## <a name="step-1-enable-permissions-for-insider-risk-management"></a>步骤 1：为内部风险管理启用权限

>[!Important]
>配置角色组之后，可能需要长达 30 分钟时间将角色组权限应用到整个组织的已分配用户。

有四个角色组用于配置管理内部风险管理功能的权限。 若要继续这些配置步骤，租户管理员必须先将你分配到 **预览** 体验成员风险管理或 **内部风险管理管理员角色** 组。 若要在初始配置后访问和管理内部风险管理功能，用户必须至少是一个内部风险管理角色组的成员。

根据合规性管理团队的结构，你可以将用户分配到特定角色组来管理不同的内部风险管理功能集。 若要查看 Office  365 安全与合规中心中的"权限"选项卡&管理角色组，您需要被分配到组织管理角色组，或需要分配有"*角色管理"角色*。 配置内部风险管理时，请从以下角色组选项中进行选择：

| **角色组** | **角色权限** |
| :------------- | :------------------- |
| **内部风险管理** | 使用此角色组在单个组中管理组织的内部风险管理。 通过添加指定管理员、分析师、研究人员和审核员的所有用户帐户，可以在单个组中配置内部风险管理权限。 此角色组包含所有内部风险管理权限角色和相关权限。 此配置是快速开始使用内部风险管理的最简单方法，非常适合不需要为单独的用户组定义单独权限的组织。 |
| **内部风险管理管理员** | 使用此角色组最初配置内部风险管理，稍后再将内部风险管理员隔离到定义的组中。 此角色组的用户可启用和查看分析见解，并创建、读取、更新和删除内部风险管理策略、全局设置和角色组分配。 |
| **预览体验计划风险管理分析员** | 使用此组向将充当内部风险案例分析员的用户分配权限。 此角色组的用户可以访问和查看所有内部风险管理警报、案例、分析见解和通知模板。 他们无法访问内部风险内容资源管理器。 |
| **预览体验计划风险管理调查员** | 使用此组向将充当内部风险数据调查者的用户分配权限。 此角色组的用户可以访问所有事例的内部风险管理警报、案例、通知模板和内容资源管理器。 |
| **内部风险管理审核员** | 使用此组向将审核内部风险管理活动的用户分配权限。 此角色组的用户可以访问内部风险审核日志。 |

> [!NOTE]
> 这些角色组当前在 Privileged Identity Management (PIM) 。 若要了解有关 PIM 的信息，请参阅 [Privileged Identity Management 中的分配 Azure AD 角色](/azure/active-directory/privileged-identity-management/pim-how-to-add-role-to-user)。

### <a name="add-users-to-an-insider-risk-management-role-group"></a>将用户添加到内部风险管理角色组

完成以下步骤以将用户添加到内部风险管理角色组：

1. 使用 Microsoft 365 组织中的管理员账户凭据登录 [https://protection.office.com/permissions](https://protection.office.com/permissions)。

2. 在安全 &amp; 合规中心中，转到“**权限**”。 选择链接以查看和管理 Office 365 中的角色。

3. 选择要添加用户的内部风险管理角色组，然后选择"编辑 **角色组"。**

4. 从左侧导航窗格中选择“**选择成员**”，然后选择“**编辑**”。

5. 选择“**添加**”，然后选中希望添加到角色组的所有用户的复选框。

6. 选择“**添加**”，然后选择“**完成**”。

7. 选择“**保存**”以将用户添加到角色组。 选择“**关闭**”以完成步骤。

## <a name="step-2-enable-the-microsoft-365-audit-log"></a>步骤 2：启用 Microsoft 365 审核日志

内部风险管理使用 Microsoft 365 审核日志获取策略和分析见解中标识的用户见解和活动。 Microsoft 365 审核日志是组织中所有活动的摘要，内部风险管理策略可能会使用这些活动生成策略见解。

有关启用审核的逐步操作说明，请参阅 [打开或关闭审核日志搜索](turn-audit-log-search-on-or-off.md)。 打开审核之后，将显示一条消息，内容为正在准备审核日志，你可以在准备完成后几个小时内运行搜索。 此操作只需要执行一次。 有关使用 Microsoft 365 审核日志， [请参阅搜索](search-the-audit-log-in-security-and-compliance.md)审核日志。

## <a name="step-3-enable-and-view-insider-risk-analytics-insights-optional"></a>步骤 3：启用和查看内部风险分析见解 (可选) 

通过内部风险管理分析，你可以对组织中潜在的内部风险进行评估，而无需配置任何内部风险策略。 此评估可帮助你的组织确定潜在的用户风险领域，并帮助确定你可能考虑配置的内部风险管理策略的类型和范围。 此评估还可以帮助您确定对现有策略进行其他许可或未来优化的需求。 分析扫描结果最多可能需要 48 小时，才能将见解作为报告提供进行审阅。 若要了解有关分析见解的详细信息，请参阅预览体验成员风险管理设置：分析 ([预览) 。 ](insider-risk-management-settings.md#analytics-preview)

若要启用内部风险分析，你必须是 *内部* 风险管理、内部风险管理管理员或 Microsoft 365 *全局管理员角色组* 的成员。

完成以下步骤以启用内部风险分析：

1. 在 [Microsoft 365 合规中心](https://compliance.microsoft.com)中，转到 **"内部风险管理"。**
2. 在 **"内部** 风险管理概述"选项卡上的"扫描 **组织卡中的** 内部风险"中选择" **运行扫描** "。此操作将打开组织的分析扫描。 您还可以在组织中打开扫描，方法为导航到"内部风险设置""分析 (预览版) 并启用"扫描租户的用户活动  >  **"，** 以确定 **潜在的内部风险**。
3. 在" **分析详细信息"** 窗格中，选择" **运行扫描"开始组织的扫描**。 分析扫描结果最多可能需要 24 小时，才能将见解作为报告提供进行审阅。

查看分析见解后，选择内部风险策略并配置最符合组织的内部风险缓解策略的相关先决条件。

## <a name="step-4-configure-prerequisites-for-policies"></a>步骤 4：配置策略的先决条件

大多数内部风险管理策略的先决条件必须为策略指示器进行配置，以生成相关活动警报。 根据计划为组织配置的策略配置相应的先决条件。

### <a name="configure-microsoft-365-hr-connector"></a>配置 Microsoft 365 HR 连接器

内部风险管理支持导入从第三方风险管理和人力资源平台导入的用户和日志数据。 Microsoft 365 人力资源 (HR) 数据连接器允许你从 CSV 文件中提取人力资源数据，包括用户终止日期、上次雇佣日期、绩效改善计划通知、绩效考核操作和工作级别更改状态。 此数据有助于推动内部风险管理策略中的警报指示器，是在你的组织中配置完全风险管理覆盖的重要部分。 如果为组织配置多个 HR 连接器，内部风险管理将自动拉取所有 HR 连接器中的指示器。

使用下列策略模板时，需要 Microsoft 365 HR 连接器：

- 脱离用户数据盗窃
- 离开用户违反安全策略
- 解除限制的用户违反安全策略
- 解除限制的用户泄露数据

有关 [为组织配置](import-hr-data.md) Microsoft 365 HR 连接器的分步指南，请参阅设置连接器以导入 HR 数据文章。 配置 HR 连接器后，返回到这些配置步骤。

### <a name="configure-data-loss-prevention-dlp-policies"></a>配置 DLP 策略 (数据丢失) 防护

内部风险管理支持使用 DLP 策略来帮助识别针对高严重性级别 DLP 警报向不需要方泄露敏感信息的有意或意外行为。 使用任何"数据泄露"模板配置内部风险管理策略时，必须为该策略分配特定的 DLP 策略。

DLP 策略可帮助识别用户，以在针对敏感信息的高风险性 DLP 警报的内部风险管理中激活风险评分，这是在组织中配置完全风险管理覆盖的重要部分。 有关内部风险管理和 DLP 策略集成以及规划注意事项的信息，请参阅 [预览体验成员风险管理策略](insider-risk-management-policies.md#general-data-leaks)。

>[!IMPORTANT]
>确保已完成以下操作：
>
>- 您可以在 DLP 和内部风险管理策略中了解并正确配置范围内用户，以生成预期策略范围。
>- 确保 DLP 策略 **中** 用于这些模板的内部风险管理的"事件报告"设置已针对高严重性级别警报进行配置。 不会从 DLP 策略生成内部风险管理警报，"事件报告"字段设置为 *"低*"或"中 *"。*

使用下列策略模板时需要 DLP 策略：

- 常规数据泄露
- 按优先级用户的数据泄露

有关 [为组织配置 DLP](create-test-tune-dlp-policy.md) 策略的分步指南，请参阅创建、测试和调整 DLP 策略一文。 配置 DLP 策略后，返回到这些配置步骤。

### <a name="configure-priority-user-groups"></a>配置优先级用户组

内部风险管理包括对向策略分配优先用户组的支持，以帮助标识具有关键职位、高级数据和网络访问或过去风险行为历史记录的用户的唯一风险活动。 创建优先级用户组并将用户分配到组帮助将策略的范围确定为这些用户呈现的独特情况。

使用下列策略模板时需要优先级用户组：

- 优先级用户违反安全策略
- 按优先级用户的数据泄露

有关 [创建优先用户组](insider-risk-management-settings.md#priority-user-groups-preview) 的分步指南，请参阅内部风险管理设置入门文章。 配置优先级用户组后，返回到这些配置步骤。

### <a name="configure-physical-badging-connector-optional"></a>配置物理保护连接器 (可选) 

内部风险管理支持从物理控制和访问平台导入用户和日志数据。 物理密码连接器允许你从 JSON 文件拉取访问数据，包括用户 ID、访问点 ID、访问时间和日期以及访问状态。 此数据有助于推动内部风险管理策略中的警报指示器，是在你的组织中配置完全风险管理覆盖的重要部分。 如果为组织配置了多个物理标记连接器，内部风险管理会自动从所有物理标记连接器提取指示器。 使用所有内部风险策略模板时，物理保护连接器的信息会补充其他内部风险信号。

>[!IMPORTANT]
>若要让内部风险管理策略使用与离开和终止用户相关的信号数据，并将该数据与物理控制和访问平台的事件数据关联，还必须配置 Microsoft 365 HR 连接器。 如果在未启用 Microsoft 365 HR 连接器的情况下启用物理保护连接器，内部风险管理策略将仅处理针对组织中用户的未经授权的物理访问的事件。

有关 [为组织](import-physical-badging-data.md) 配置物理保护连接器的分步指南，请参阅设置连接器以导入物理保护数据一文。 配置连接器后，返回到这些配置步骤。

### <a name="configure-microsoft-defender-for-endpoint-optional"></a>为终结点配置 Microsoft Defender (可选) 

[Microsoft Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) 是一个企业终结点安全平台，旨在帮助企业网络预防、检测、调查和响应高级威胁。 为了更好地查看组织中安全违规的情况，你可以导入并筛选 Defender for Endpoint 警报，以用于从内部风险管理安全违反策略模板创建的策略中使用的活动。

如果你创建违反安全策略，则需要在你的组织中配置 Microsoft Defender for Endpoint，并启用 Defender for Endpoint 以实现 Defender 安全中心中的内部风险管理集成，以导入安全违反警报。 有关要求详细信息，请参阅 Microsoft [Defender for Endpoints](/windows/security/threat-protection/microsoft-defender-atp/minimum-requirements) 的最低要求文章。

请参阅 [在 Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/advanced-features#share-endpoint-alerts-with-microsoft-compliance-center) 中配置高级功能一文，了解为内部风险管理集成配置 Defender for Endpoint 的分步指南。 配置适用于终结点的 Microsoft Defender 后，返回到这些配置步骤。

## <a name="step-5-configure-insider-risk-settings"></a>步骤 5：配置内部风险设置

[内部风险设置](insider-risk-management-settings.md) 适用于所有内部风险管理策略，无论你在创建策略时选择了哪个模板。 设置使用位于所有内部 **风险管理** 选项卡顶部的内部风险设置控件进行配置。 这些设置控制隐私、指示器、监视窗口和智能检测。

在配置策略之前，请定义以下内部风险设置：

1. 在[Microsoft 365](https://compliance.microsoft.com)合规中心中，转到"内部风险管理"，然后从任意页面右上角选择"内部风险设置"。
2. 在 **"隐私** "页上，选择用于显示策略通知的用户名的隐私设置。
3. 在 **"指示器"** 页上，选择要应用于所有内部风险策略的警报指示器。

    >[!IMPORTANT]
    >为了接收策略中定义的风险活动的警报，必须选择一个或多个指示器。 如果未在"设置"中配置指示器，则这些指示器在内部风险策略中将不可选择。

4. 在 **"策略时间范围**"页上，选择要在 [](insider-risk-management-settings.md#policy-timeframes)触发内部风险策略匹配时为用户生效的策略时间范围。
5. 在 **"智能检测"** 页上，为内部风险策略配置以下设置：
    - [文件类型排除项](insider-risk-management-settings.md#file-type-exclusions)
    - [异常文件活动的阈值](insider-risk-management-settings.md#threshold-for-unusual-file-activity)
    - [警报音量级别](insider-risk-management-settings.md#alert-volume)
    - [Microsoft Defender for Endpoint 警报状态](insider-risk-management-settings.md#microsoft-defender-for-endpoint-preview)
    - [域设置](insider-risk-management-settings.md#domains-preview)
6. 在" **导出警报"** 页上，根据需要使用 Office 365 管理 API 导出内部风险警报信息。
7. 在" **优先级用户组"** 页上，创建优先级用户组，如果未在步骤 3 中创建，则 **添加用户**。
8. 在 **"Power Automate 流"** 页上，配置来自内部风险流模板的流或创建新流。 有关 [分步指南](insider-risk-management-settings.md#power-automate-flows-preview) ，请参阅内部风险管理设置入门文章。
9. 在" **优先级资源"页上**，配置优先级资源以使用物理保护连接器导入的物理控制和访问平台的数据。 有关 [分步指南](insider-risk-management-settings.md#priority-physical-assets-preview) ，请参阅内部风险管理设置入门文章。
10. 在 **Microsoft Teams** 页面上，启用 Microsoft Teams 与内部风险管理的集成，以自动为案例或用户协作创建团队。 有关 [分步指南](insider-risk-management-settings.md#microsoft-teams-preview) ，请参阅内部风险管理设置入门文章。
11. 选择 **"保存** "，为内部风险策略启用这些设置。

## <a name="step-6-create-an-insider-risk-management-policy"></a>步骤 6：创建内部风险管理策略

内部风险管理策略包括分配的用户，并定义为警报配置了哪些类型的风险指标。 必须先配置策略，活动才能触发警报。 使用策略向导创建新的内部风险管理策略。

1. 在 [Microsoft 365](https://compliance.microsoft.com)合规中心中，转到 **"内部风险管理** "并选择" **策略"** 选项卡。
2. 选择 **"创建策略** "以打开策略向导。
3. 在" **策略模板** "页上，选择一个策略类别，然后选择新策略的模板。 这些模板由定义要检测和调查的风险活动的条件和指示器所决定。 查看模板先决条件、触发事件和检测到的活动，以确认此策略模板符合你的需求。

    >[!IMPORTANT]
    >某些策略模板具有必须为策略配置以生成相关警报的先决条件。 如果尚未配置适用的策略先决条件，请参阅上面的 **步骤 4。**

4. 选择 **"下一** 步"继续。
5. 在" **名称和说明"页上** ，填写下列字段：
    - **需要 (名称) ：** 输入策略的友好名称。 创建策略后，无法更改此名称。
    - **说明 (可选) ：** 输入策略的说明。

6. 选择 **"下一** 步"继续。
7. 在"**用户和** 组"页上，选择"包括所有用户和组"或"包括特定用户和组"以定义策略中包括哪些用户或组，或者如果你选择了基于用户的优先级模板;选择 **"添加或编辑优先级用户组"。** 选择 **"包括所有用户和** 组"将查找组织中所有用户和组的触发事件，以开始分配策略的风险评分。 选择 **"包括特定用户和组** "可定义要分配给策略的用户和组。
8. 选择 **"下一** 步"继续。
9. 在" **要** 设置优先级的内容"页上， (根据需要) 源分配优先级，这会增加为这些源生成高严重性警报的可能性。 选择下列选项之一：

    - **我希望将 SharePoint 网站、敏感度标签和/或敏感信息类型指定为优先内容**。 选择此选项将在向导中启用详细信息页面以配置这些通道。
    - **现在，我不想指定** 优先级内容 (可以在创建策略后) 。 选择此选项将跳过向导中的频道详细信息页面。

10. 选择 **"下一** 步"继续。

11. 如果在上一步中选择了"我希望将 **SharePoint** 网站、敏感度标签和/或敏感信息类型指定为优先内容"，你将看到 *有关 SharePoint* 网站、敏感信息类型和敏感度标签的详细信息 *页面。* 使用这些详细信息页定义 SharePoint、敏感信息类型和敏感度标签，以在策略中设置优先级。

    - **SharePoint 网站**： **选择"添加 SharePoint** 网站"，然后选择有权访问并想要确定优先级的 SharePoint 网站。 例如 *，"group1@contoso.sharepoint.com/sites/group1"。*
    - **敏感信息类型**：选择 **"添加敏感信息类型** "，然后选择要确定优先级的敏感度类型。 例如 *，"美国银行帐号"* 和 *"信用卡号"。*
    - **敏感度标签**：选择 **"添加敏感度** 标签"，然后选择要设置优先级的标签。 例如 *，"机密"和**"机密"。*

12. 选择 **"下一** 步"继续。
13. 在 **"指示器和触发事件**"页面上，你将在"内部风险设置指示器 [](insider-risk-management-settings.md#indicators)"页面上看到已定义为可用的  >  指示器。 如果在向导开始时选择了"数据泄露"模板，则必须从 DLP 策略下拉列表中选择 **DLP** 策略，以启用策略的触发指示器或选择内置触发事件。

    >[!IMPORTANT]
    >如果无法选择此页面上的指示器，则需要选择要针对所有策略启用的指示器。 可以使用向导 **中的"打开** 指示器"按钮，或在"**内部** 风险管理设置策略指示器"页上选择  >    >  指示器。

    选择要应用于策略的指示器。 如果您不希望使用这些指示器的默认策略阈值设置，请禁用"使用 **Microsoft** 建议的默认阈值"，并输入每个选定指示器的阈值。

    - 如果已选择至少一个 *Office* 或 *设备* 指示器，请根据情况 **选择** 风险评分分数。 风险评分评估仅适用于所选指标。
    - 如果选择了"*数据盗窃"* 或"数据泄露"策略模板，请选择一个或多个序列检测方法和累积泄漏检测方法以应用于策略。 

14. 选择 **"下一** 步"继续。
15. 在" **指示器阈值"** 页上，选择使用默认指示器阈值或指定单个指示器的自定义阈值的选项。 对于每个指示器，选择相应的级别以生成所需的活动提醒级别。
16. 选择 **"下一** 步"继续。
17. 在 **"审阅** "页上，查看为策略选择的设置以及所选内容的任何建议或警告。 选择 **"** 编辑"以更改任何策略值，或选择" **提交** "以创建和激活策略。

## <a name="next-steps"></a>后续步骤

完成这些步骤以创建首个内部风险管理策略后，你将在大约 24 小时后开始从活动指示器接收警报。 使用本文步骤 4 中的指导或创建新的内部风险策略 中的步骤根据需要配置 [其他策略](insider-risk-management-policies.md#create-a-new-policy)。

若要详细了解如何调查内部风险警报和 **警报仪表板**，请参阅 [预览体验成员风险管理警报](insider-risk-management-alerts.md)。
