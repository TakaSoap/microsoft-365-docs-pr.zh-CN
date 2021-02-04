---
title: 内部风险管理策略
description: 了解 Microsoft 365 中的内部风险管理策略
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
ms.collection: m365-security-compliance
ms.openlocfilehash: 1093d664e58f77d94db9f6f922a1a5072f4d3982
ms.sourcegitcommit: c0cfb9b354db56fdd329aec2a89a9b2cf160c4b0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/03/2021
ms.locfileid: "50094695"
---
# <a name="insider-risk-management-policies"></a>内部风险管理策略

内部风险管理策略确定哪些用户位于范围内，以及为警报配置了哪些类型的风险指标。 您可以快速创建适用于组织中所有用户的策略，或定义单个用户或组以在策略中管理。 策略支持内容优先级，以将策略条件集中在多个或特定的 Microsoft Teams、SharePoint 网站、数据敏感度类型和数据标签上。 使用模板，可以选择特定风险指标并自定义策略指示器的事件阈值，从而有效地自定义风险评分以及警报级别和频率。 此外，风险评分提高和异常检测有助于识别重要性更高或更异常的用户活动。 策略窗口允许你定义将策略应用于提醒活动的时间范围，并用于确定策略在激活后的持续时间。

## <a name="policy-dashboard"></a>策略仪表板

通过 **策略** 仪表板，可以快速查看组织中策略以及与每个策略关联的警报的当前状态。

- **策略名称**：在策略向导中分配给策略的名称。
- **活动警报**：每个策略的活动警报数。
- **已确认的** 警报：过去 365 天内策略中导致出现案例的警报总数。
- **对警报采取的操作**：过去 365 天内已确认或消除的警报总数。
- **策略有效性**：由确认的警报总数除以对警报采取的总操作数 (该百分比是过去一年确认或消除的警报) 。
- **活动**：大小写状态 *，是或**否*。

![内部风险管理策略仪表板](../media/insider-risk-policy-dashboard.png)

## <a name="policy-templates"></a>策略模板

内部风险管理模板是预定义的策略条件，用于定义策略使用的风险指标和风险评分模型的类型。 创建策略之前，每个策略都必须在策略创建向导中分配一个模板。 内部风险管理支持每个策略模板最多五个策略。 使用策略向导创建新的内部风险策略时，你将从以下策略模板之一中选择：

### <a name="data-theft-by-departing-users"></a>离开用户的数据盗窃

当用户离开组织时，通常会有一些特定风险指标与离职用户的数据盗窃相关联。 此策略模板使用风险评分指示器，并重点关注此风险领域的检测和警报。 离职用户的数据盗窃可能包括从 SharePoint Online 下载文件、打印文件，以及将数据复制到接近雇佣和结束日期的个人云消息和存储服务。 此模板开始对与这些活动及其与用户雇佣状态相关的风险指标进行评分。

>[!IMPORTANT]
>使用此模板时，必须配置 Microsoft 365 HR 连接器，以定期导入组织中用户的终止日期和终止日期信息。 有关 [为组织配置](import-hr-data.md) Microsoft 365 HR 连接器的分步指南，请参阅"使用 HR 连接器导入数据"一文。

### <a name="general-data-leaks"></a>常规数据泄露

保护数据和防止数据泄露是大多数组织的一个持续挑战，尤其是用户、设备和服务所创建的新数据的快速增长。 用户可以跨服务和设备创建、存储和共享信息，这会使管理数据泄露变得更加复杂和困难。 数据泄露可能包括在组织外部意外过度共享信息或恶意窃取数据。 此模板与分配的数据丢失防护 (DLP) 策略结合使用，开始对可疑 SharePoint Online 数据下载、文件和文件夹共享、打印文件以及将数据复制到个人云消息和存储服务进行实时检测。

使用数据 **泄露** 模板时，必须分配 DLP 策略，以触发组织中高严重性警报的内部风险策略中的指示器。 每当将 DLP 策略规则生成高严重性警报添加到 Office 365 审核日志时，使用此模板创建的内部风险策略将自动检查高严重性 DLP 警报。 如果警报包含内部风险策略中定义的作用域内用户，则内部风险策略将警报作为新警报进行处理，并分配有内部风险严重性和风险评分。 此策略允许你在上下文中与案例中包含的其他活动一起评估此警报。

#### <a name="data-leaks-policy-guidelines"></a>数据泄露策略指南

创建或修改 DLP 策略以用于内部风险管理策略时，请考虑以下准则：

- 在 DLP 策略中配置规则时，确定数据外报事件的优先级，并将事件报告设置分配给"高"时具有选择性。 例如，将敏感文档通过电子邮件发送给已知安全机制应为高警报级别过滤事件。 过度分配其他 DLP策略规则中的"事件报告"设置中的"高级"可能会增加内部风险管理警报工作流中的干扰，并且使数据调查人员和分析人员更难正确评估这些警报。 例如， *分配高警报* 级别以访问 DLP 策略中的拒绝活动使评估真正有风险的用户行为和活动更具挑战性。
- 确保在 DLP 和内部风险管理策略中了解并正确配置范围内用户。 只有使用"数据泄露"模板定义为内部风险管理策略范围内的用户才能处理高严重性 DLP 策略警报。 此外，内部风险管理策略将仅检查在高严重性 DLP 警报规则中定义为范围内的用户，以便进行考虑。 在 DLP 和内部风险策略中，不要以冲突的方式在无意中配置范围内用户，这一点很重要。

     例如，如果您的 DLP 策略规则的范围仅针对销售团队的用户，并且通过"数据泄露"模板创建的内部风险策略将所有用户定义为范围内，则内部风险策略实际上只会处理销售团队中用户的高严重性 DLP 警报。 内部风险策略不会收到任何高优先级 DLP 警报，供用户处理本例中的 DLP 规则未定义。 相反，如果根据数据泄露模板创建的内部风险管理策略的范围仅针对销售团队中的用户，并且分配的 DLP 策略的范围为所有用户，则内部风险策略将仅处理针对销售团队成员的高严重性 DLP 警报。 内部风险管理策略将忽略针对未在销售团队的所有用户的高严重性 DLP 警报。

- 确保 **用于此内部** 风险管理模板的 DLP 策略中的事件报告规则设置已针对高严重性级别警报进行配置。 高 *严重性* 级别是触发事件，内部风险管理警报不会从 DLP 策略中的规则生成，"事件报告"字段设置为"*低*"或"*中"。*

    ![DLP 策略警报设置](../media/insider-risk-DLP-policy-high-severity.png)

     >[!NOTE]
     >使用内置模板创建新 DLP 策略时，需要选择"创建或自定义高级 **DLP** 规则"选项，以配置高严重性级别的"事件报告"设置。 

从数据泄露模板创建的每个内部风险管理 **策略只能分配** 一个 DLP 策略。 请考虑创建一个专用 DLP 策略，该策略结合了要检测的不同活动，并充当使用"数据泄露"模板的内部风险策略的 **触发事件。**

有关 [为组织](create-test-tune-dlp-policy.md) 配置 DLP 策略的分步指南，请参阅"创建、测试和调整 DLP 策略"一文。

### <a name="data-leaks-by-priority-users-preview"></a>按优先级用户的数据泄露 (预览) 

保护数据和防止组织中用户的数据泄露可能取决于他们的位置、敏感信息的访问级别或风险历史记录。 数据泄露可能包括在组织外部意外过度共享高度敏感信息或恶意窃取数据。 此模板与分配的数据丢失防护 (DLP) 策略结合使用，开始对可疑活动实时检测进行评分，并提高了内部风险警报和严重性级别较高的警报的可能性。 优先级用户在 [内部](insider-risk-management-settings.md#priority-user-groups-preview) 风险管理设置区域中配置的优先级用户组中定义。

与" **常规数据泄露**"模板一样，您必须分配 DLP 策略以触发组织中高严重性警报的内部风险策略中的指示器。 使用此模板创建策略时，请遵循上述数据泄露策略指南。 此外，还需要将"内部风险管理设置"中创建的优先级用户组  >  **分配给**  >  策略。

### <a name="data-leaks-by-disgruntled-users-preview"></a>在预览版中，由 (用户泄露) 

当用户遇到雇佣压力时，他们可能会变得不知情，这会增加内部风险活动的可能性。 当标识与取消记录关联的指示器时，此模板将开始为用户活动评分。 示例包括性能改进通知、性能评审不佳或作业级别状态更改。 对于不工作的用户，数据泄露可能包括从 SharePoint Online 下载文件，以及将数据复制到个人云消息和存储服务（接近雇佣压力事件）。

使用此模板时，还必须配置 Microsoft 365 HR 连接器，以定期为组织用户导入性能改进通知、性能考核状态不佳或作业级别更改信息。 有关 [为组织配置](import-hr-data.md) Microsoft 365 HR 连接器的分步指南，请参阅"使用 HR 连接器导入数据"一文。

### <a name="general-security-policy-violations-preview"></a>预览版中 (违反) 

在许多组织中，用户有权在设备上安装软件或修改设备设置以帮助完成其任务。 无论是无意还是恶意，用户可能会安装恶意软件或禁用有助于保护其设备或网络资源上的信息的重要安全功能。 此策略模板使用来自 Microsoft Defender for Endpoint 的安全警报开始对这些活动进行评分，并针对此风险区域进行焦点检测和警报。 在用户可能拥有安全策略违反历史记录（可能是内部风险指示器）的情况下，使用此模板提供安全策略违反的见解。

你需要在你的组织中配置 Microsoft Defender for Endpoint，并启用 Defender for Endpoint，以便 Defender 安全中心中的内部风险管理集成导入安全违反警报。 有关为 Endpoint 配置 Defender 进行内部风险管理集成的信息，请参阅在 Defender for Endpoint 中 [配置高级功能](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-features#share-endpoint-alerts-with-microsoft-compliance-center)。

### <a name="security-policy-violations-by-departing-users-preview"></a>通过离开用户或预览版 (违反) 

离职用户（无论留下正面或负面术语）都可能是违反安全策略的较高风险。 为了帮助防止因疏忽或恶意违反离开用户的安全，此策略模板使用 Defender for Endpoint 警报提供与安全相关的活动的见解。 这些活动包括用户安装恶意软件或其他可能有害的应用程序，以及禁用其设备上的安全性功能。 在用户具有从 Microsoft 365 HR 连接器导入的提前或终止日期作为触发事件后，将激活策略指示器。

使用此模板时，必须配置 Microsoft 365 HR 连接器，以定期导入组织中用户的终止日期和终止日期信息。 有关 [为组织配置](import-hr-data.md) Microsoft 365 HR 连接器的分步指南，请参阅"使用 HR 连接器导入数据"一文。

你需要在你的组织中配置 Microsoft Defender for Endpoint，并启用 Defender for Endpoint，以便 Defender 安全中心中的内部风险管理集成导入安全违反警报。 有关为 Endpoint 配置 Defender 进行内部风险管理集成的信息，请参阅在 Defender for Endpoint 中 [配置高级功能](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-features#share-endpoint-alerts-with-microsoft-compliance-center)。

### <a name="security-policy-violations-by-priority-users-preview"></a>预览版中优先级用户违反 (违反) 

防止组织中用户的安全违规可能取决于他们的位置、敏感信息的访问级别或风险历史记录。 由于优先级用户违反安全规定可能会对组织的关键区域产生过大的影响，因此此策略模板开始在这些指示器上评分，并使用 Microsoft Defender for Endpoint 警报为这些用户提供与安全相关的活动的见解。 这些可能包括优先用户安装恶意软件或其他可能有害的应用程序，并禁用其设备上的安全性功能。 优先级用户在内部风险管理设置区域中配置的优先级用户组中定义。

你需要在你的组织中配置 Microsoft Defender for Endpoint，并启用 Defender for Endpoint，以便 Defender 安全中心中的内部风险管理集成导入安全违反警报。 有关为 Endpoint 配置 Defender 进行内部风险管理集成的信息，请参阅在 Defender for Endpoint 中 [配置高级功能](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-features#share-endpoint-alerts-with-microsoft-compliance-center)。 此外，还需要将"内部风险管理设置"中创建的优先级用户组  >  **分配给**  >  策略。

### <a name="security-policy-violations-by-disgruntled-users-preview"></a>取消注册的用户在预览版中违反 (违反) 

遇到雇佣压力的用户可能由于无意或恶意违反安全策略而面临更高的风险。 这些压力因素可能包括被置于绩效改善计划、性能考核状态不佳或从当前职位降级的用户。 此策略模板基于这些指示器和与这些事件相关的活动为这些用户启动风险评分。

使用此模板时，还必须配置 Microsoft 365 HR 连接器，以定期为组织用户导入性能改进通知、性能考核状态不佳或作业级别更改信息。 有关 [为组织配置](import-hr-data.md) Microsoft 365 HR 连接器的分步指南，请参阅"使用 HR 连接器导入数据"一文。

你还需要在组织中配置 Microsoft Defender for Endpoint，并启用 Defender for Endpoint，以便 Defender 安全中心中的内部风险管理集成导入安全违反警报。 有关为 Endpoint 配置 Defender 进行内部风险管理集成的信息，请参阅在 Defender for Endpoint 中 [配置高级功能](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-features#share-endpoint-alerts-with-microsoft-compliance-center)。

### <a name="policy-template-prerequisites-and-triggering-events"></a>策略模板先决条件和触发事件

根据为内部风险管理策略选择的模板，触发事件和策略先决条件会有所不同。 触发事件是确定用户是否对内部风险管理策略处于活动状态的先决条件。 如果用户已添加到内部风险管理策略，但没有触发事件，则策略不会评估用户活动，除非在用户仪表板中手动添加用户活动。 策略先决条件是必需项，以便策略接收评估风险所需的信号或活动。

下表列出了从每个内部风险管理策略模板创建的策略的触发事件和先决条件：

| **策略模板** | **触发策略事件** | **先决条件** |
| :------------------ | :--------------------------------- | :---------------- |
| 离开用户的数据盗窃 | HR 连接器的提前或终止日期指示器 | 为终止和终止日期指示器配置的 Microsoft 365 HR 连接器 |
| 常规数据泄露 | 创建高严重性警报的数据泄露策略活动 | 针对高严重性警报配置的 DLP 策略 |
| 按优先级用户的数据泄露 | 创建高严重性警报的数据泄露策略活动 | 针对高严重性警报配置的 DLP 策略 <br><br> 在内部风险设置中配置的优先用户组 |
| 解除限制的用户泄露数据 | 来自 HR 连接器的性能改进、性能不佳或作业级别更改指示器 | 为解除限制指示器配置的 Microsoft 365 HR 连接器 |
| 一般安全策略违反 | Microsoft Defender for Endpoint 检测到的安全控件或不需要的软件的防御者 | Active Microsoft Defender for Endpoint 订阅 <br><br> 配置了 Microsoft Defender for Endpoint 与 Microsoft 365 合规中心集成 |
| 离开用户违反安全策略 | HR 连接器中的提前或终止日期指示器 | 为终止和终止日期指示器配置的 Microsoft 365 HR 连接器 <br><br> Active Microsoft Defender for Endpoint 订阅 <br><br> 配置了 Microsoft Defender for Endpoint 与 Microsoft 365 合规中心集成 |
| 优先级用户违反安全策略 | Microsoft Defender for Endpoint 检测到的安全控件或不需要的软件的防御者 | Active Microsoft Defender for Endpoint 订阅 <br><br> 配置了 Microsoft Defender for Endpoint 与 Microsoft 365 合规中心集成 <br><br> 在内部风险设置中配置的优先用户组 |
| 解除权限的用户违反安全策略 | 来自 HR 连接器的性能改进、性能不佳或作业级别更改指示器 | 为解除限制指示器配置的 Microsoft 365 HR 连接器 <br><br> Active Microsoft Defender for Endpoint 订阅 <br><br> 配置了 Microsoft Defender for Endpoint 与 Microsoft 365 合规中心集成 |

## <a name="prioritize-content-in-policies"></a>确定策略中内容的优先级

内部风险管理策略支持为内容指定更高的优先级，具体取决于内容的存储位置或分类方式。 将内容指定为优先级会增加任何关联活动的风险评分，进而增加生成高严重性警报的可能性。 但是，某些活动不会生成警报，除非相关内容包含内置或自定义敏感信息类型或在策略中指定为优先级。

例如，您的组织有一个专用于高度机密项目的 SharePoint 网站。 此 SharePoint 网站中信息的数据泄露可能会损害项目，并会对项目的成功产生显著影响。 通过设置数据泄露策略中此 SharePoint 网站的优先级，将自动增加符合条件的活动的风险评分。 此优先顺序会增加这些活动生成内部风险警报的可能性，并提升警报的严重性级别。

在策略向导中创建内部风险管理策略时，可以从以下优先级中选择：

- **SharePoint 网站**：任何与已定义 SharePoint 网站中所有文件类型关联的活动都将被分配较高的风险评分。 
- **敏感信息类型**：任何与包含敏感信息类型的内容关联的活动都 [](sensitive-information-type-entity-definitions.md)将被分配较高的风险评分。
- **敏感度标签**：任何与应用了特定敏感度标签的内容关联的活动 [](sensitivity-labels.md)都将被分配较高的风险评分。

## <a name="create-a-new-policy"></a>创建新策略

若要创建新的内部风险管理策略，你将使用 Microsoft 365 合规中心内部风险管理解决方案中的策略向导。

完成以下步骤以创建新策略：

1. 在 [Microsoft 365 合规中心](https://compliance.microsoft.com)，转到 **"内部风险管理** "并选择" **策略"** 选项卡。
2. 选择 **"创建策略** "以打开策略向导
3. 在 **"新建内部风险策略** "页上，填写以下字段：
    - **Name (required)**： Enter a friendly name for the policy.
    - **说明 (可选) ：** 输入策略的说明。
    - **选择策略 (策略) ：** 选择其中一个策略模板来定义受策略监视的风险 [](insider-risk-management-policies.md#policy-templates)指示器类型。

    >[!IMPORTANT]
    >大多数策略模板具有必须配置的先决条件，策略必须配置这些必备组件以生成相关警报。 如果尚未配置适用的策略先决条件，请参阅内部 [风险管理入门](insider-risk-management-configure.md#step-3-configure-prerequisites-for-templates)。

4. 选择 **"下一** 步"继续。
5. 在"**用户**"页上，选择"添加用户或组"或"选择优先级"用户组以定义策略中包含的用户或优先级用户组，具体取决于所选的策略模板。 如果 **适用，请** 选中"所有用户和启用邮件的组"复选框 (如果尚未选择基于用户的优先级模板) 。 选择 **"下一** 步"继续。
6. 在 **"指定要设置优先级的内容 (可选**) 页上，您可以分配源，以针对增加的风险分数确定优先级。 但是，某些活动不会生成警报，除非相关内容包含内置或自定义敏感信息类型或在此页面上指定为优先级：
    - **SharePoint 网站**： **选择"添加 SharePoint 网站** "，然后选择要确定优先级的 SharePoint 组织。 例如 *，"group1@contoso.sharepoint.com/sites/group1"。*
    - **敏感信息类型**： **选择"添加敏感信息类型** "，然后选择要设置优先级的敏感度类型。 例如 *，"美国银行帐号*"和 *"信用卡号"。*
    - **敏感度标签**： **选择"添加敏感度标签** "，然后选择要设置优先级的标签。 例如 *，"机密"和**"机密"。*
7. 选择 **"下一** 步"继续。
8. 在 **"选择策略** 指示器"页上，你将在"内部风险 [](insider-risk-management-settings.md#indicators)设置指示器"页上看到已定义为可用的  >  指示器。 如果在向导的开头选择了"数据泄露"模板，则必须从 DLP 策略下拉列表中选择 **DLP** 策略，以启用该策略的触发指示器。 选择要应用于策略的指示器。 如果不希望使用这些指示器的默认策略阈值设置，请禁用 **Microsoft** 建议的"使用默认阈值"，并输入每个选定指示器的阈值。 如果已至少选择了一个 *Office* 或 *设备* 指示器，请根据情况选择 **风险分数。** 风险评分指标仅适用于所选指标。

    >[!IMPORTANT]
    >如果无法选择此页面上的指示器，则需要在"内部风险管理设置策略指示器"页上选择要为所有策略启用  >    >  的指示器。

9. 选择 **"下一** 步"继续。
10. 在 **"策略时间范围**"页上，你将在"内部风险 [](insider-risk-management-settings.md#policy-timeframes)设置策略时间范围"页上看到策略的激活窗口  >  条件。
11. 选择 **"下一** 步"继续。
12. 在 **"** 审阅"页上，查看为策略选择的设置。 选择 **"** 编辑"可更改任何策略值，或 **选择"** 提交"以创建和激活策略。

## <a name="update-a-policy"></a>更新策略

若要更新现有内部风险管理策略，你将使用 Microsoft 365合规中心内部风险管理解决方案中的策略向导。

完成以下步骤以管理现有策略：

1. 在 [Microsoft 365 合规中心](https://compliance.microsoft.com)，转到 **"内部风险管理** "并选择" **策略"** 选项卡。
2. 在策略仪表板上，选择要管理的策略。
3. 在策略详细信息页上，选择 **"编辑策略"**
4. 在策略向导中，无法编辑以下字段：
    - **名称**：策略的友好名称
    - **选择策略模板**：用于定义策略监视的风险指示器类型的模板。
5. 在"说明"字段中输入 **策略的新说明** 。 
6. 选择 **"下一** 步"继续。
7. 在"**用户**"页上，选择"添加用户或组"或"选择优先级"用户组以定义策略中包含的用户或优先级用户组，具体取决于所选的策略模板。 如果 **适用，请** 选中"所有用户和启用邮件的组"复选框 (如果尚未选择基于用户的优先级模板) 。 选择 **"下一** 步"继续。
8. 在 **"指定要设置优先级的内容 (可选**) 页上，您可以分配源，以针对增加的风险分数确定优先级。 但是，某些活动不会生成警报，除非相关内容包含内置或自定义敏感信息类型或在此页面上指定为优先级：
    - **SharePoint 网站**： **选择"添加 SharePoint 网站** "，然后选择要确定优先级的 SharePoint 组织。 例如 *，"group1@contoso.sharepoint.com/sites/group1"。*
    - **敏感信息类型**： **选择"添加敏感信息类型** "，然后选择要设置优先级的敏感度类型。 例如 *，"美国银行帐号*"和 *"信用卡号"。*
    - **敏感度标签**： **选择"添加敏感度标签** "，然后选择要设置优先级的标签。 例如 *，"机密"和**"机密"。*
9. 选择 **"下一** 步"继续。
10. 在 **"选择策略** 指示器"页上，你将在"内部风险 [](insider-risk-management-settings.md#indicators)设置指示器"页上看到已定义为可用的  >  指示器。 如果在向导的开头选择了"数据泄露"模板，则必须从 DLP 策略下拉列表中选择 **DLP** 策略，以启用该策略的触发指示器。 选择要应用于策略的指示器。 如果不希望使用这些指示器的默认策略阈值设置，请禁用 **Microsoft** 建议的"使用默认阈值"，并输入每个选定指示器的阈值。 如果已至少选择了一个 *Office* 或 *设备* 指示器，请根据情况选择 **风险分数。** 风险评分指标仅适用于所选指标。

    >[!IMPORTANT]
    >如果无法选择此页面上的指示器，则需要在"内部风险管理设置策略指示器"页上选择要为所有策略启用  >    >  的指示器。

11. 选择 **"下一** 步"继续。
12. 在 **"策略时间范围**"页上，你将在"内部风险 [](insider-risk-management-settings.md#policy-timeframes)设置策略时间范围"页上看到策略的激活窗口  >  条件。
13. 选择 **"下一** 步"继续。
14. 在 **"审阅** "页上，查看已针对策略更新的设置。 选择 **"** 编辑"可更改任何策略值，或 **选择"** 提交"以更新和激活策略。

## <a name="delete-a-policy"></a>删除策略

>[!NOTE]
>删除策略不会删除从策略生成的活动或存档的警报。

若要删除现有的内部风险管理策略，请完成以下步骤：

1. 在 [Microsoft 365 合规中心](https://compliance.microsoft.com)，转到 **"内部风险管理** "并选择" **策略"** 选项卡。
2. 在策略仪表板上，选择要删除的策略。
3. 选择 **仪表板** 工具栏上的"删除"。
4. 在 **"删除** " **对话框中，选择** "是"删除策略，或 **选择"** 取消"关闭该对话框。
