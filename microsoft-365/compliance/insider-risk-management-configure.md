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
ms.openlocfilehash: e0e24197dbad864fe32fc2e5ce98dface7357c3d
ms.sourcegitcommit: a9ac702c9efc9defded3bfa65618b94bac00c237
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/16/2021
ms.locfileid: "50261375"
---
# <a name="get-started-with-insider-risk-management"></a>内部风险管理入门

使用内部风险管理策略确定风险活动和管理工具，以对组织的风险警报采取行动。 完成以下步骤以设置先决条件并配置内部风险管理策略。

>[!IMPORTANT]
>Microsoft 365 内部风险管理解决方案提供租户级别选项，帮助客户促进用户级别的内部治理。 租户级别管理员可以设置权限，为组织成员提供对此解决方案的访问权限，在 Microsoft 365 合规中心中设置数据连接器以导入相关数据，以支持用户级别识别可能存在风险的活动。 客户确认与单个用户的行为、字符或绩效相关的见解与雇佣关系可由管理员计算，并提供给组织其他人。 此外，客户确认，他们必须自行进行与个人用户的行为、字符或与雇佣相关的性能的完整调查，而不只是依赖于内部风险管理服务的见解。 客户应单独负责使用 Microsoft 365 内部风险管理服务和符合所有适用法律的任何关联功能或服务，包括与个人用户标识相关的法律以及任何修正操作。

有关内部风险策略如何帮助您管理组织中风险的信息，请参阅 [Microsoft 365 中的内部风险管理](insider-risk-management.md)。

## <a name="subscriptions-and-licensing"></a>订阅和许可

在开始内部风险管理之前，应确认 [Microsoft 365](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans) 订阅和任何加载项。 若要访问和使用内部风险管理，组织必须具有以下订阅或加载项之一：

- Microsoft 365 E5 订阅（付费或试用版本）
- Microsoft 365 E3 订阅 + Microsoft 365 E5 合规加载项
- Microsoft 365 E3 订阅 + Microsoft 365 E5 预览体验成员风险管理加载项
- Microsoft 365 A5 订阅（付费或试用版本）
- Microsoft 365 A3 订阅 + Microsoft 365 A5 合规加载项
- Microsoft 365 A3 订阅 + Microsoft 365 A5 预览体验成员风险管理加载项
- Microsoft 365 G5 订阅（付费或试用版本）
- Microsoft 365 G3 订阅 + Microsoft 365 G5 合规性加载项
- Microsoft 365 G3 订阅 + Microsoft 365 G5 Insider Risk Management 加载项
- Office 365 E3 订阅 + 企业移动性和安全性 E3 + Microsoft 365 E5 合规性加载项

必须为包含在内部风险管理策略中的用户分配上述许可证之一。

如果你没有现有的 Microsoft 365 企业版 E5 计划，并且想要尝试内部风险管理，你可以将[Microsoft 365](/office365/admin/try-or-buy-microsoft-365)添加到现有订阅或[](https://www.microsoft.com/microsoft-365/enterprise)注册 Microsoft 365 企业版 E5 试用版。

## <a name="step-1-enable-permissions-for-insider-risk-management"></a>步骤 1：启用内部风险管理权限

>[!Important]
>配置角色组之后，可能需要长达 30 分钟时间将角色组权限应用到整个组织的已分配用户。

有四个角色组用于配置管理内部风险管理功能的权限。 若要继续执行这些配置步骤，租户管理员必须先将你分配到 Insider Risk **Management** 或 **Insider Risk Management Admin 角色** 组。 若要在初始配置后访问和管理内部风险管理功能，用户必须至少是一个内部风险管理角色组的成员。

根据合规性管理团队的结构，你可以将用户分配到特定角色组来管理不同的内部风险管理功能集。 若要查看 Office  365 安全与合规中心中的"权限"选项卡&管理角色组，需要分配给"组织管理"角色组，或者需要分配"角色管理"*角色*。 配置内部风险管理时，请从以下角色组选项中进行选择：

| **角色组** | **角色权限** |
| :---- | :---------------- |
| **内部风险管理** | 使用此角色组在单个组中管理组织的内部风险管理。 通过添加指定管理员、分析师和研究人员的所有用户帐户，可以在单个组中配置内部风险管理权限。 此角色组包含所有内部风险管理权限角色。 此配置是快速开始使用内部风险管理的最简单方法，非常适合不需要为单独的用户组定义单独权限的组织。|
| **内部风险管理管理员** | 使用此角色组最初配置内部风险管理，稍后再将内部风险管理员隔离到定义的组中。  此角色组的用户可以创建、读取、更新和删除内部风险管理策略和全局设置。 |
| **预览体验计划风险管理分析员** | 使用此组向将充当内部风险案例分析员的用户分配权限。 此角色组的用户可以访问所有内部风险管理警报、案例和通知模板。 他们无法访问内部风险内容资源管理器。 |
| **预览体验计划风险管理调查员** | 使用此组向将充当内部风险数据调查者的用户分配权限。 此角色组的用户可以访问所有内部风险管理警报、案例、通知模板和内容资源管理器。 |

> [!NOTE]
> 这些角色组当前在 PRIVILEGEd Identity Management (PIM) 。 若要了解有关 PIM 的信息，请参阅[Privileged Identity Management 中的"分配 Azure AD 角色"。](/azure/active-directory/privileged-identity-management/pim-how-to-add-role-to-user)

### <a name="add-users-to-an-insider-risk-management-role-group"></a>将用户添加到内部风险管理角色组

完成以下步骤以将用户添加到内部风险管理角色组：

1. 使用 Microsoft 365 组织中的管理员账户凭据登录 [https://protection.office.com/permissions](https://protection.office.com/permissions)。

2. 在安全 &amp; 合规中心中，转到“**权限**”。 选择链接以查看和管理 Office 365 中的角色。

3. 选择要将用户添加到的内部风险管理角色组，然后选择"**编辑角色组"。**

4. 从左侧导航窗格中选择“**选择成员**”，然后选择“**编辑**”。

5. 选择“**添加**”，然后选中希望添加到角色组的所有用户的复选框。

6. 选择“**添加**”，然后选择“**完成**”。

7. 选择“**保存**”以将用户添加到角色组。 选择“**关闭**”以完成步骤。

## <a name="step-2-enable-the-audit-log"></a>步骤 2：启用审核日志

内部风险管理将审核日志用于策略中配置的用户见解和活动。 审核日志是与内部风险管理策略或更改策略时关联的所有活动的摘要。

有关启用审核的逐步操作说明，请参阅 [打开或关闭审核日志搜索](turn-audit-log-search-on-or-off.md)。 打开审核之后，将显示一条消息，内容为正在准备审核日志，你可以在准备完成后几个小时内运行搜索。 此操作只需要执行一次。 有关使用审核日志的详细信息，请参阅 [搜索审核日志](search-the-audit-log-in-security-and-compliance.md)。

## <a name="step-3-configure-prerequisites-for-templates"></a>步骤 3：配置模板的先决条件

大多数内部风险管理模板具有必须为策略指示器配置的先决条件，以生成相关活动警报。 根据计划为组织配置的策略配置相应的先决条件。

### <a name="configure-microsoft-365-hr-connector"></a>配置 Microsoft 365 HR 连接器

内部风险管理支持导入从第三方风险管理和人力资源平台导入的用户和日志数据。 Microsoft 365 人力资源 (HR) 数据连接器允许你从 CSV 文件中提取人力资源数据，包括用户终止日期、上次雇佣日期、绩效改善计划通知、绩效考核操作和工作级别更改状态。 此数据有助于推动内部风险管理策略中的警报指示器，是组织中配置完全风险管理覆盖范围的重要部分。 如果为组织配置多个 HR 连接器，内部风险管理将自动从所有 HR 连接器拉取指示器。

以下策略模板使用时需要 Microsoft 365 HR 连接器：

- 离开用户数据盗窃
- 离开用户违反安全策略
- 冲突用户违反安全策略
- 由不命名的用户泄露数据

有关 [为组织](import-hr-data.md) 配置 Microsoft 365 HR 连接器的分步指南，请参阅"设置连接器以导入 HR 数据"文章。 配置 HR 连接器后，返回到这些配置步骤。

### <a name="configure-data-loss-prevention-dlp-policies"></a>配置 DLP (数据丢失) 策略

内部风险管理支持使用 DLP 策略来帮助识别针对高严重性级别 DLP 警报有意或意外向不需要的各方泄露敏感信息。 使用任何数据泄露模板配置内部风险管理策略时，必须为该策略分配特定的 DLP 策略。

DLP 策略可帮助标识用户，以激活针对敏感信息的高风险警报的内部风险管理中的风险评分，并且是组织中配置完全风险管理范围的重要部分。 有关内部风险管理和 DLP 策略集成和规划注意事项详细信息，请参阅 [内部风险管理策略](insider-risk-management-policies.md#general-data-leaks)。

>[!IMPORTANT]
>确保已完成以下操作：
>
>- 您可以在 DLP 和内部风险管理策略中了解并正确配置范围内用户，以生成预期的策略范围。
>- 确保 DLP **策略中** 用于这些模板的内部风险管理的事件报告设置已针对高严重性级别警报进行配置。  内部风险管理警报不会从"事件报告"字段设置为"低"或"中"的DLP 策略 *生成*。

使用以下策略模板时需要 DLP 策略：

- 常规数据泄露
- 按优先级用户的数据泄露

有关 [为组织配置 DLP](create-test-tune-dlp-policy.md) 策略的分步指南，请参阅"创建、测试和调整 DLP 策略"一文。 配置 DLP 策略后，返回到这些配置步骤。

### <a name="configure-priority-user-groups"></a>配置优先级用户组

内部风险管理包括支持将优先用户组分配给策略，以帮助标识具有关键职位、高级数据和网络访问或过去风险行为历史记录的用户的唯一风险活动。 创建优先级用户组并将用户分配给组有助于将策略范围缩小到这些用户呈现的独特情况。

使用以下策略模板时需要优先级用户组：

- 优先级用户违反安全策略
- 按优先级用户的数据泄露

有关 [创建优先级用户组](insider-risk-management-settings.md#priority-user-groups-preview) 的分步指南，请参阅内部风险管理设置入门文章。 配置优先级用户组后，返回到这些配置步骤。

### <a name="configure-physical-badging-connector-optional"></a>配置物理保护连接器 (可选) 

内部风险管理支持导入从物理控制和访问平台导入的用户和日志数据。 物理保护连接器允许你从 JSON 文件拉取访问数据，包括用户 ID、访问点 ID、访问时间和日期以及访问状态。 此数据有助于推动内部风险管理策略中的警报指示器，是组织中配置完全风险管理覆盖范围的重要部分。 如果为组织配置多个物理标记连接器，内部风险管理会自动从所有物理标记连接器提取指示器。 使用所有内部风险策略模板时，来自物理保护连接器的信息会补充其他内部风险信号。

>[!IMPORTANT]
>若要让内部风险管理策略使用和关联与离开和终止用户相关的信号数据与物理控制和访问平台的事件数据，还必须配置 Microsoft 365 HR 连接器。 如果在未启用 Microsoft 365 HR 连接器的情况下启用物理保护连接器，内部风险管理策略将仅处理对组织中用户进行未经授权的物理访问的事件。

有关 [为组织](import-physical-badging-data.md) 配置物理保护连接器的分步指南，请参阅"设置连接器以导入物理错误数据"一文。 配置连接器后，返回到这些配置步骤。

## <a name="step-4-configure-insider-risk-settings"></a>步骤 4：配置内部风险设置

[内部风险设置](insider-risk-management-settings.md) 适用于所有内部风险管理策略，而不考虑在创建策略时选择的模板。 设置使用位于所有内部风险管理选项卡顶部的 Insider **Risk settings** 控件进行配置。 这些设置控制隐私、指示器、监视窗口和智能检测。

在配置策略之前，请定义以下内部风险设置：

1. 在 [Microsoft 365](https://compliance.microsoft.com)合规中心，转到 **"内部** 风险管理"，然后从任意页面右上角选择"预览体验成员风险设置"。 
2. 在 **"** 隐私"页上，选择用于显示策略警报的用户名的隐私设置。
3. 在 **"指示器"** 页上，选择要应用于所有内部风险策略的警报指示器。

    >[!IMPORTANT]
    >为了接收策略中定义的有风险活动的警报，必须选择一个或多个指示器。

4. 在 **"策略时间范围**"页上，选择要在 [](insider-risk-management-settings.md#policy-timeframes)触发内部风险策略匹配时为用户生效的策略时间范围。
5. 在 **"智能检测"** 页上，为内部风险策略配置以下设置：
    - [异常检测](insider-risk-management-settings.md#anomaly-detections)
    - [警报音量级别](insider-risk-management-settings.md#alert-volume)
    - [Microsoft Defender for Endpoint 警报状态](insider-risk-management-settings.md#microsoft-defender-for-endpoint-preview)
    - [域设置](insider-risk-management-settings.md#domains-preview)
6. 在 **"导出警报"** 页上，根据需要使用 Office 365 管理 API 导出内部风险警报信息。
7. 在 **"优先级用户组"** 页上，创建优先级用户组，如果未在步骤 3 中创建，则 **添加用户**。
8. 在 **"Power Automate 流"** 页上，配置来自内部风险流模板的流或创建新流。 有关 [分步指南，请参阅内部风险管理](insider-risk-management-settings.md#power-automate-flows-preview) 设置入门文章。
9. 在 **"优先级资源"页上**，将优先级资产配置为使用物理保护连接器导入的物理控制和访问平台的数据。 有关 [分步指南，请参阅内部风险管理](insider-risk-management-settings.md#priority-physical-assets-preview) 设置入门文章。
10. 在 **Microsoft Teams** 页面上，允许 Microsoft Teams 与内部风险管理集成，以自动创建团队进行案例或用户协作。 有关 [分步指南，请参阅内部风险管理](insider-risk-management-settings.md#microsoft-teams-preview) 设置入门文章。
11. 选择 **"** 保存"，为内部风险策略启用这些设置。

## <a name="step-5-create-an-insider-risk-management-policy"></a>步骤 5：创建内部风险管理策略

内部风险管理策略包括分配的用户，并定义为警报配置了哪些类型的风险指示器。 必须先配置策略，活动才能触发警报。

1. 在 [Microsoft 365 合规](https://compliance.microsoft.com)中心，转到 **"内部** 风险管理"并选择" **策略"** 选项卡。
2. 选择 **"创建策略** "以打开策略向导。
3. 在 **"新建内部风险策略** "页上，填写以下字段：
    - **所需 (名称) ：** 输入策略的友好名称。
    - **说明 (可选) ：** 输入策略的说明。
    - **选择策略 (策略) ：** 选择其中一个策略模板来定义策略监视的风险指示器 [](insider-risk-management-policies.md#policy-templates)类型。

    >[!IMPORTANT]
    >大多数策略模板具有必须为策略配置以生成相关警报的先决条件。 如果尚未配置适用的策略先决条件，请参阅上面的 **步骤 3。**

4. 选择 **"下一** 步"继续。
5. 在 **"用户**"页上，选择"添加用户或组"或"选择优先级"用户组来定义策略中包括哪些用户或优先级用户组，具体取决于所选的策略模板。 如果 **适用，请** 选中"所有用户和启用邮件的组"复选框 (如果尚未选择基于用户的优先级模板) 。 选择 **"下一** 步"继续。
6. 在 **"指定对哪些内容设置优先级 (可选**) 页上，您可以分配源以针对增加的风险分数确定优先级。 但是，某些活动不会生成警报，除非相关内容包含内置或自定义敏感信息类型或在此页面上指定为优先级：
    - **SharePoint 网站**：选择 **"添加 SharePoint 网站** "，然后选择要确定优先级的 SharePoint 组织。 例如 *，"group1@contoso.sharepoint.com/sites/group1"。*
    - **敏感信息类型**： **选择"添加敏感信息类型** "，然后选择要设置优先级的敏感度类型。 例如 *，"美国银行帐号*"和 *"信用卡号"。*
    - **敏感度标签**： **选择"添加敏感度标签** "，然后选择要设置优先级的标签。 例如 *，"机密"和**"机密"。*
7. 选择 **"下一** 步"继续。
8. 在 **"选择策略** 指示器"页上，你将在"预览体验 [](insider-risk-management-settings.md#indicators)成员风险设置指示器"页上看到已定义为可用的  >  指示器。 如果在向导的开头选择了数据泄露模板，则必须从 DLP 策略下拉列表中选择 **DLP** 策略，以启用该策略的触发指示器。 选择要应用于策略的指示器。 如果您不希望使用这些指示器的默认策略阈值设置，请禁用 **Microsoft** 建议的默认阈值，并输入每个选定指示器的阈值。 如果至少选择了一个 *Office* 或 *设备* 指示器，请根据情况选择 **风险分数。** 风险评分指数仅适用于所选指标。

    >[!IMPORTANT]
    >如果无法选择此页面上的指示器，则需要在"内部风险管理设置策略指示器"页上选择要为所有策略启用  >    >  的指示器。

9. 选择 **"下一** 步"继续。
10. 在 **"策略时间范围**"页上，你将在"预览体验 [](insider-risk-management-settings.md#policy-timeframes)成员风险设置策略时间范围"页上看到策略的激活窗口  >  条件。
11. 选择 **"下一** 步"继续。
12. 在 **"审阅** "页上，查看为策略选择的设置。 选择 **"** 编辑"可更改任何策略值，或选择" **提交** "以创建和激活策略。

## <a name="next-steps"></a>后续步骤

完成这些步骤以创建第一个内部风险管理策略后，将在大约 24 小时后开始从活动指示器接收警报。 使用本文第 4 步中的指南或"创建新的内部风险策略"中的步骤根据需要 [配置其他策略](insider-risk-management-policies.md#create-a-new-policy)。

若要了解有关调查内部风险警报和 **警报** 仪表板的更多信息，请参阅 [预览体验成员风险管理警报](insider-risk-management-alerts.md)。
