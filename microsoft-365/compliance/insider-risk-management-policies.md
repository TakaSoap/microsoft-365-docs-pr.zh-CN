---
title: 内幕风险管理策略
description: 了解 Microsoft 365 中的内幕风险管理策略
keywords: Microsoft 365，内幕风险管理，风险管理，合规性
localization_priority: Normal
ms.prod: Microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: m365-security-compliance
ms.openlocfilehash: 7701932cdd41b673dcc665c71983df9f4d244a8b
ms.sourcegitcommit: 9489aaf255f8bf165e6debc574e20548ad82e882
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/11/2020
ms.locfileid: "46632171"
---
# <a name="insider-risk-management-policies"></a>内幕风险管理策略

内幕风险管理策略确定哪些用户属于范围以及为警报配置了哪些类型的风险指示器。 您可以快速创建适用于组织中所有用户的策略，或在策略中定义各个用户或组以进行管理。 策略支持将策略条件集中在多个或特定 Microsoft 团队、SharePoint 网站、数据敏感度类型和数据标签上的内容优先级。 使用模板，可以选择特定风险指示器并为策略指示器自定义事件阈值，从而有效地自定义风险分数和警报的级别和频率。 此外，风险分数 boosters 和异常检测有助于确定重要性较高或异常较低的用户活动。 "策略" 窗口允许您定义将策略应用于警报活动的时间段，并用于确定策略在激活后的持续时间。

## <a name="policy-dashboard"></a>策略仪表板

通过**策略仪表板**，可以快速查看组织中的策略以及与每个策略关联的警报的当前状态。

- **策略名称**：在策略向导中分配给策略的名称。
- **主动警报**：每个策略的活动警报数。
- 已**确认的警报**：在过去365天内从策略中产生的警报总数。
- **对通知执行的操作**：最近365天内已确认或已消除的警报总数。
- **策略有效性**：由已确认的警报总数除以警报 (的百分比，这是在过去一年中已确认或消除的警报的总和) 。
- **Active**：案例的状态为 *"是"* 或 "*否*"。

![内幕风险管理策略仪表板](../media/insider-risk-policy-dashboard.png)

## <a name="policy-templates"></a>策略模板

内幕风险管理模板是预定义的策略条件，用于定义策略使用的风险指示器和风险计分模型的类型。 在创建策略之前，每个策略必须在策略创建向导中分配一个模板。 内幕风险管理最高支持每个策略模板的五个策略。 当您使用策略向导创建新的内幕风险策略时，您将从以下策略模板之一中进行选择：

### <a name="data-theft-by-departing-users"></a>通过去声用户窃取数据

当用户离开你的组织时，会有一些特定的风险指标通常与盗窃用户的数据失窃相关联。 此策略模板使用指示器查看风险评分，并将重点检测和警报重点放在此风险领域。 对传出用户的数据盗用可能包括从 SharePoint Online 下载文件、打印文件，以及将数据复制到其雇佣辞职和结束日期附近的个人云消息和存储服务。 此模板开始对与这些活动相关的风险指示器以及它们与用户雇用状态关联的方式进行评分。

>[!IMPORTANT]
>使用此模板时，必须配置 Microsoft 365 HR 连接器以定期为组织中的用户导入辞职和终止日期信息。 有关为您的组织配置 Microsoft 365 HR 连接器的分步指南，请参阅[Import data WITH HR connector](import-hr-data.md)一文。

### <a name="general-data-leaks"></a>常规数据泄露

对于大多数组织来说，保护数据和防止数据泄露是一项持续挑战，尤其是用户、设备和服务创建的新数据的快速增长。 用户能够在服务和设备之间创建、存储和共享信息，从而使管理数据泄露变得越来越复杂和困难。 数据泄露可能包括意外 oversharing 组织外部的信息或恶意的数据窃取。 与已分配的数据丢失防护 (DLP) 策略结合使用时，此模板可开始对可疑 SharePoint Online 数据下载、文件和文件夹共享、打印文件以及将数据复制到个人云邮件和存储服务的实时检测进行评分。

使用**数据泄露**模板时，您必须为组织中的高严重性警报分配一个 DLP 策略，以触发内幕风险策略中的指示器。 只要 DLP 策略规则生成的高严重性警报添加到 Office 365 审核日志，使用此模板创建的内幕风险策略将自动检查高严重性的 DLP 警报。 如果警报包含内幕风险策略中定义的范围内用户，则该警报将由内幕风险策略处理为新警报，并向其分配内幕风险严重性和风险分数。 此策略允许您在上下文中评估此警报，在案例中包含其他活动。

#### <a name="data-leaks-policy-guidelines"></a>数据泄露策略准则

在创建或修改用于内幕风险管理策略的 DLP 策略时，请考虑以下准则：

- 在 DLP 策略中配置规则时，exfiltration 事件的优先级设置为 "高"，并为 "*高*" 分配事件**报告**设置。 例如，对已知竞争对手的电子邮件敏感文档应为*高*警报级别的 exfiltration 事件。 在**事件报告**中分配*高*级别其他 DLP 策略规则中的设置可能会增加内幕风险管理警报工作流中的噪音，并使您的数据调查人员和分析人员更难正确评估这些警报。 例如，分配*高*警报级别来访问 DLP 策略中的拒绝活动，会使评估真正的有风险的用户行为和活动变得更加困难。
- 确保您了解并正确配置了 DLP 和有问必答风险管理策略中的范围内用户。 只有使用**数据泄露**模板定义为内部范围内的内幕风险管理策略的用户才会处理高严重性的 DLP 策略警报。 此外，内幕风险管理策略仅会检查针对高严重性 DLP 警报在规则中定义为范围内的用户，以供考虑。 不要在任何情况中以冲突的方式在 DLP 和内幕风险策略中不知不觉地配置范围内的用户，这一点非常重要。

     例如，如果您的 DLP 策略规则的范围仅限于销售团队中的用户，并且从**数据泄露**模板中创建的内幕风险策略已将所有用户定义为范围内，则内幕风险策略将只为销售团队中的用户实际处理高严重性 DLP 警报。 内幕风险策略不会收到任何高优先级的 DLP 警报，以供用户处理在此示例中未定义的 DLP 规则。 相反，如果从**数据泄露**模板创建的内幕风险管理策略的范围仅限于销售团队中的用户，并且分配的 DLP 策略的范围限定为所有用户，则内幕风险策略将只为销售团队的成员处理高严重性的 DLP 警报。 内幕风险管理策略将忽略不在销售团队中的所有用户的高严重性 DLP 警报。

- 确保对用于此内幕风险管理模板的 DLP 策略中的 "**事件报告**" 规则设置进行了配置，以实现*高*严重性级别警报。 *高*严重性级别是触发事件和内幕风险管理警报不会从 DLP 策略中的规则生成，且**事件报告**字段设置为 "*低*" 或 "*中*"。

    ![DLP 策略警报设置](../media/insider-risk-DLP-policy-high-severity.png)

     >[!NOTE]
     >使用内置模板创建新的 DLP 策略时，需要选择 "**创建或自定义高级 DLP 规则**" 选项，以配置*高*严重性级别的**事件报告**设置。

从**数据泄露**模板创建的每个内幕风险管理策略只能分配一个 DLP 策略。 请考虑创建一个专用的 DLP 策略，将您要检测的不同活动组合起来，并将其用作使用**数据泄露**模板的内幕风险策略的触发事件。

有关为您的组织配置 DLP 策略的分步指南，请参阅[创建、测试和调整 dlp 策略](create-test-tune-dlp-policy.md)主题。

### <a name="data-leaks-by-priority-users-preview"></a>按优先级用户 (预览的数据泄露) 

保护数据并防止组织中用户的数据泄露可能取决于其位置、敏感信息的访问级别或风险历史记录。 数据泄露可能包括意外 oversharing 组织外部的高度敏感信息或恶意数据窃取的情况。 与已分配的数据丢失防护 (DLP) 策略结合使用时，此模板可启动对可疑活动的实时检测，并导致具有较高严重性级别的内幕风险警报和警报的可能性增加。 优先级用户是在 "内幕风险管理设置" 区域中配置的 "[优先级用户组](insider-risk-management-settings.md#priority-user-groups-preview)" 中定义的。

与**常规数据泄露模板**一样，您必须为组织中的高严重性警报分配一个 DLP 策略，以触发内幕风险策略中的指示器。 使用此模板创建策略时，请遵循上面的数据泄露策略准则。 此外，还需要在 "**内幕风险管理**  >  **设置**  >  **优先级" 用户组**中为策略分配创建的优先级用户组。

### <a name="data-leaks-by-disgruntled-users-preview"></a>因不满用户 (预览而进行的数据泄露) 

当用户遇到雇用 stressors 时，他们可能会感到不满，这可能会增加内幕风险活动的机率。 此模板在标识与 disgruntlement 关联的指示器时开始评分用户活动。 示例包括性能改进通知、性能较差的检查或作业级状态的更改。 不满意用户的数据泄露可能包括从 SharePoint Online 下载文件以及将数据复制到员工 stressor 事件的个人云消息和存储服务中。

使用此模板时，您还必须配置 Microsoft 365 HR 连接器，以定期导入性能改进通知、性能较差的检查状态或组织中用户的作业级更改信息。 有关为您的组织配置 Microsoft 365 HR 连接器的分步指南，请参阅[Import data WITH HR connector](import-hr-data.md)一文。

### <a name="general-security-policy-violations-preview"></a> (预览的常规安全策略冲突) 

在许多组织中，用户有权在其设备上安装软件或修改设备设置以帮助他们的任务。 无论是无意还是恶意意向，用户都可以安装恶意软件或禁用有助于保护其设备或网络资源上的信息的重要安全功能。 此策略模板使用来自 Microsoft Defender 高级威胁防护 (ATP) 的安全警报来开始评分这些活动，并将检测和警报集中到此风险区域。 使用此模板可在应用程序可能有可能成为内幕风险指标的安全策略违规历史记录时，提供适用于安全策略冲突的见解。

您需要在组织中配置 Microsoft Defender ATP，并在 "Defender 安全中心" 中启用 Microsoft Defender ATP 以获得内部风险管理集成，以导入安全冲突警报。 有关为内部人员风险管理集成配置 Microsoft Defender ATP 的详细信息，请参阅[在 Microsoft DEFENDER atp 中配置高级功能](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-features#share-endpoint-alerts-with-microsoft-compliance-center)。

### <a name="security-policy-violations-by-departing-users-preview"></a>通过 (preview 中的去声用户进行安全策略违反) 

如果传出的用户不是肯定的或负的术语，则可能会对安全策略违规产生较高的风险。 为了帮助防止对传出用户的意外或恶意安全违规，此策略模板使用 Microsoft Defender ATP 警报来提供与安全相关的活动的见解。 这些活动包括安装恶意软件或其他可能有害的应用程序以及在其设备上禁用安全功能的用户。 在用户将放弃或终止日期作为触发事件从 Microsoft 365 HR 连接器导入后，将激活策略指示器。

使用此模板时，必须配置 Microsoft 365 HR 连接器以定期为组织中的用户导入辞职和终止日期信息。 有关为您的组织配置 Microsoft 365 HR 连接器的分步指南，请参阅[Import data WITH HR connector](import-hr-data.md)一文。

您需要在组织中配置 Microsoft Defender ATP，并在 "Defender 安全中心" 中启用 Microsoft Defender ATP 以获得内部风险管理集成，以导入安全冲突警报。 有关为内部人员风险管理集成配置 Microsoft Defender ATP 的详细信息，请参阅[在 Microsoft DEFENDER atp 中配置高级功能](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-features#share-endpoint-alerts-with-microsoft-compliance-center)。

### <a name="security-policy-violations-by-priority-users-preview"></a>按优先级用户 (预览的安全策略冲突) 

防止组织中用户的安全冲突可能取决于组织的位置、敏感信息的访问级别或风险历史记录。 由于优先级用户可能会对组织的关键领域产生 outsized 影响，因此此策略模板会对这些指标开始评分，并使用 Microsoft Defender ATP 警报为这些用户提供与安全相关的活动的见解。 其中可能包括安装恶意软件或其他可能有害的应用程序以及在其设备上禁用安全功能的优先用户。 优先级用户是在 "内幕风险管理设置" 区域中配置的 "优先级用户组" 中定义的。

您需要在组织中配置 Microsoft Defender ATP，并在 "Defender 安全中心" 中启用 Microsoft Defender ATP 以获得内部风险管理集成，以导入安全冲突警报。 有关为内部人员风险管理集成配置 Microsoft Defender ATP 的详细信息，请参阅[在 Microsoft DEFENDER atp 中配置高级功能](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-features#share-endpoint-alerts-with-microsoft-compliance-center)。 此外，还需要在 "**内幕风险管理**  >  **设置**  >  **优先级" 用户组**中为策略分配创建的优先级用户组。

### <a name="security-policy-violations-by-disgruntled-users-preview"></a>因不满用户 (预览) 而违反安全策略的情况

体验雇用 stressors 的用户可能会受到意外或恶意安全策略冲突的较高风险。 这些 stressors 可能包括将用户置于性能改进计划、性能较差的审核状态或从其当前位置降级。 此策略模板根据与这些用户相关的这些指示和活动启动风险评分。

使用此模板时，您还必须配置 Microsoft 365 HR 连接器，以定期导入性能改进通知、性能较差的检查状态或组织中用户的作业级更改信息。 有关为您的组织配置 Microsoft 365 HR 连接器的分步指南，请参阅[Import data WITH HR connector](import-hr-data.md)一文。

您还需要在您的组织中配置 Microsoft Defender ATP，并在 "Defender 安全中心" 中启用 Microsoft Defender ATP 以获得内部风险管理集成，以导入安全违规警报。 有关为内部人员风险管理集成配置 Microsoft Defender ATP 的详细信息，请参阅[在 Microsoft DEFENDER atp 中配置高级功能](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-features#share-endpoint-alerts-with-microsoft-compliance-center)。

### <a name="offensive-language-in-email"></a>电子邮件中的冒犯性语言

检测并采取措施来防止攻击性和滥用行为是防止风险的关键因素。 Microsoft 365 中的内置分类程序扫描从组织中的 Exchange Online 邮箱发送的电子邮件，了解不同类型的合规性问题。 这些分类器使用人工智能和关键字的组合来识别可能违反反骚扰策略的电子邮件中的语言。 使用此模板可以快速创建一个策略，该策略使用这些分类程序自动检测可能被视为滥用或攻击性的电子邮件内容。 内幕风险管理使用的分类器扫描发送的电子邮件中的英语术语和看法以查找攻击性语言。

### <a name="policy-template-prerequisites-and-triggering-events"></a>策略模板先决条件和触发事件

根据为内幕风险管理策略选择的模板，触发事件和策略先决条件会有所不同。 触发事件是确定用户是否为内部人员风险管理策略处于活动状态的先决条件。 如果将用户添加到内幕风险管理策略中，但不具有触发事件，则策略不会评估用户活动，除非用户在用户仪表板中手动添加了该活动。 策略先决条件是必需项，以便策略接收评估风险所需的信号或活动。

下表列出了从每个内幕风险管理策略模板创建的策略的触发事件和先决条件：

| **策略模板** | **触发策略事件** | **先决条件** |
| :------------------ | :--------------------------------- | :---------------- |
| 通过去声用户窃取数据 | 来自 HR 连接器的辞职或终止日期指示器 | 为终止和放弃日期指示器配置的 Microsoft 365 HR 连接器 |
| 常规数据泄露 | 创建高严重性警报的数据泄漏策略活动 | 为高严重性警报配置的 DLP 策略 |
| 按优先级用户的数据泄露 | 创建高严重性警报的数据泄漏策略活动 | 为高严重性警报配置的 DLP 策略 <br><br> 在内部人员风险设置中配置的优先级用户组 |
| 因不满用户而进行的数据泄露 | HR 连接器的性能改进、性能差或作业级更改指示器 | 为 disgruntlement 指标配置的 Microsoft 365 HR 连接器 |
| 一般安全策略冲突 | Microsoft Defender ATP 检测到的安全控制或不需要的软件的防御性规避 | 活动的 Microsoft Defender ATP 订阅 <br><br> Microsoft Defender ATP 与 Microsoft 365 合规性中心的集成配置 |
| 通过去声用户违反安全策略 | 来自 HR 连接器的辞职或终止日期指示器 | 为终止和放弃日期指示器配置的 Microsoft 365 HR 连接器 <br><br> 活动的 Microsoft Defender ATP 订阅 <br><br> Microsoft Defender ATP 与 Microsoft 365 合规性中心的集成配置 |
| 优先级用户违反安全策略 | Microsoft Defender ATP 检测到的安全控制或不需要的软件的防御性规避 | 活动的 Microsoft Defender ATP 订阅 <br><br> Microsoft Defender ATP 与 Microsoft 365 合规性中心的集成配置 <br><br> 在内部人员风险设置中配置的优先级用户组 |
| 因不满用户而违反安全策略 | HR 连接器的性能改进、性能差或作业级更改指示器 | 为 disgruntlement 指标配置的 Microsoft 365 HR 连接器 <br><br> 活动的 Microsoft Defender ATP 订阅 <br><br> Microsoft Defender ATP 与 Microsoft 365 合规性中心的集成配置 |
| 电子邮件中的冒犯性语言 | 电子邮件中的猥亵、威胁或 harassing 语言 | 活动的 Exchange Online 订阅 |

## <a name="prioritize-content-in-policies"></a>对策略中的内容设置优先级

内幕风险管理策略支持为内容指定更高的优先级，具体取决于存储位置或对其进行分类的方式。 将内容指定为优先级可增加任何关联活动的风险分数，这反过来又会增加生成高严重性警报的可能性。 但是，除非相关内容包含内置或自定义敏感信息类型或在策略中指定为优先级，否则一些活动将不会生成警报。

例如，您的组织具有用于高度机密项目的专用 SharePoint 网站。 此 SharePoint 网站中信息的数据泄漏可能会影响项目，并且会对其成功产生重大影响。 通过在数据泄露策略中设置此 SharePoint 网站的优先级，可自动增加符合条件的活动的风险分数。 这增加了这些活动生成内幕风险警报的可能性，并提升了警报的严重性级别。

当您在策略向导中创建内幕风险管理策略时，可以从以下优先级中进行选择：

- **SharePoint 网站**：与定义的 SharePoint 网站中的所有文件类型相关联的任何活动都分配有更高的风险分数。 
- **敏感信息类型**：与包含[敏感信息类型](sensitive-information-type-entity-definitions.md)的内容关联的任何活动都分配有更高的风险分数。
- **敏感度标签**：与包含应用特定[敏感度标签](sensitivity-labels.md)的内容相关联的任何活动都分配有更高的风险分数。

## <a name="create-a-new-policy"></a>创建新策略

若要创建新的内幕风险管理策略，您将使用 Microsoft 365 合规性中心内的**内幕风险管理**解决方案中的策略向导。

若要创建新策略，请完成以下步骤：

1. 在[Microsoft 365 合规性中心](https://compliance.microsoft.com)中，转到 "**内幕风险管理**"，然后选择 "**策略**" 选项卡。
2. 选择 "**创建策略**" 以打开策略向导
3. 在 "**新建内幕风险策略**" 页上，填写下列字段：
    - **Name (必需的) **：为策略输入一个友好名称。
    - **Description (可选) **：输入策略的说明。
    - **选择 "策略模板" (必需的) **：选择一个[策略模板](insider-risk-management-policies.md#policy-templates)以定义由策略监视的风险指示器类型。

    >[!IMPORTANT]
    >大多数策略模板都具有必须为策略配置的先决条件，以生成相关警报。 如果尚未配置适用的策略先决条件，请参阅[内幕风险管理入门](insider-risk-management-configure.md#step-3-configure-prerequisites-for-templates)。

4. 选择 "**下一步**" 继续。
5. 在 "**用户**" 页上，选择 "**添加用户或组**" 或**选择 "优先级用户组**" 来定义哪些用户或优先级的用户组包括在策略中，具体取决于所选的策略模板。 如果还没有选择基于用户的模板) 的优先级，则选中 "**所有用户和已启用邮件的组**" 复选框（如果适用） (。 选择 "**下一步**" 继续。
6. 在 "**指定要优先处理哪些内容 (可选的) ** " 页上，您可以分配源以优先考虑增加的风险分数。 但是，除非相关内容包含内置或自定义敏感信息类型或在此页面上指定为优先级，否则一些活动将不会生成警报：
    - **SharePoint 网站**：选择 "**添加 SharePoint 网站**"，然后选择要设置优先顺序的 SharePoint 组织。 例如， *"group1@contoso.sharepoint.com/sites/group1"*。
    - **敏感信息类型**：选择 "**添加敏感信息类型**"，然后选择要设置优先级的敏感度类型。 例如， *"美国银行帐户号码"* 和 *"信用卡号码"*。
    - **敏感度标签**：选择 "**添加灵敏度标签**"，然后选择要设置优先顺序的标签。 例如， *"保密"* 和 *"Secret"*。
7. 选择 "**下一步**" 继续。
8. 在 "**选择策略指示器**" 页上，您将看到您在 "**内幕风险设置**指示器" 页上定义为 "可用" 的[指示器](insider-risk-management-settings.md#indicators)  >  **Indicators** 。 如果在向导的开头选择了*数据泄露*模板，则必须从 " **dlp 策略**" 下拉列表中选择一个 DLP 策略，以便为该策略启用触发指示器。 选择要应用于策略的指示器。 如果您不希望对这些指示器使用默认策略阈值设置，请禁用 "**使用 Microsoft 建议的默认阈值**"，并为每个选定的指标输入阈值。 如果已选择至少一个*办公室*或*设备*指示器，请根据需要选择**风险分数 boosters** 。 风险分数 boosters 仅适用于所选指示器。

    >[!IMPORTANT]
    >如果无法选择此页上的指标，您需要在 "**内幕风险管理**  >  **设置**  >  **策略指示器**" 页上选择要为所有策略启用的指示器。

9. 选择 "**下一步**" 继续。
10. 在 "**策略时段**" 页面上，您将在 "**内幕风险设置**策略时间段" 页上看到 "策略" 的[激活窗口条件](insider-risk-management-settings.md#policy-timeframes)  >  **Policy timeframes** 。
11. 选择 "**下一步**" 继续。
12. 在 "**检查**" 页上，查看您为策略选择的设置。 选择 "**编辑**" 以更改任何策略值，或选择 "**提交**" 以创建并激活策略。

## <a name="update-a-policy"></a>更新策略

若要更新现有的内幕风险管理策略，您将使用 Microsoft 365 合规性中心内的**内幕风险管理**解决方案中的策略向导。

完成以下步骤以管理现有策略：

1. 在[Microsoft 365 合规性中心](https://compliance.microsoft.com)中，转到 "**内幕风险管理**"，然后选择 "**策略**" 选项卡。
2. 在 "策略" 仪表板上，选择要管理的策略。
3. 在 "策略详细信息" 页上，选择 "**编辑策略**"
4. 在 "策略向导" 中，无法编辑以下字段：
    - **名称**：策略的友好名称
    - **选择 "策略模板**"：用于定义由策略监视的风险指示器类型的模板。
5. 在 "**说明**" 字段中输入策略的新说明。 
6. 选择 "**下一步**" 继续。
7. 在 "**用户**" 页上，选择 "**添加用户或组**" 或**选择 "优先级用户组**" 来定义哪些用户或优先级的用户组包括在策略中，具体取决于所选的策略模板。 如果还没有选择基于用户的模板) 的优先级，则选中 "**所有用户和已启用邮件的组**" 复选框（如果适用） (。 选择 "**下一步**" 继续。
8. 在 "**指定要优先处理哪些内容 (可选的) ** " 页上，您可以分配源以优先考虑增加的风险分数。 但是，除非相关内容包含内置或自定义敏感信息类型或在此页面上指定为优先级，否则一些活动将不会生成警报：
    - **SharePoint 网站**：选择 "**添加 SharePoint 网站**"，然后选择要设置优先顺序的 SharePoint 组织。 例如， *"group1@contoso.sharepoint.com/sites/group1"*。
    - **敏感信息类型**：选择 "**添加敏感信息类型**"，然后选择要设置优先级的敏感度类型。 例如， *"美国银行帐户号码"* 和 *"信用卡号码"*。
    - **敏感度标签**：选择 "**添加灵敏度标签**"，然后选择要设置优先顺序的标签。 例如， *"保密"* 和 *"Secret"*。
9. 选择 "**下一步**" 继续。
10. 在 "**选择策略指示器**" 页上，您将看到您在 "**内幕风险设置**指示器" 页上定义为 "可用" 的[指示器](insider-risk-management-settings.md#indicators)  >  **Indicators** 。 如果在向导的开头选择了*数据泄露*模板，则必须从 " **dlp 策略**" 下拉列表中选择一个 DLP 策略，以便为该策略启用触发指示器。 选择要应用于策略的指示器。 如果您不希望对这些指示器使用默认策略阈值设置，请禁用 "**使用 Microsoft 建议的默认阈值**"，并为每个选定的指标输入阈值。 如果已选择至少一个*办公室*或*设备*指示器，请根据需要选择**风险分数 boosters** 。 风险分数 boosters 仅适用于所选指示器。

    >[!IMPORTANT]
    >如果无法选择此页上的指标，您需要在 "**内幕风险管理**  >  **设置**  >  **策略指示器**" 页上选择要为所有策略启用的指示器。

11. 选择 "**下一步**" 继续。
12. 在 "**策略时段**" 页面上，您将在 "**内幕风险设置**策略时间段" 页上看到 "策略" 的[激活窗口条件](insider-risk-management-settings.md#policy-timeframes)  >  **Policy timeframes** 。
13. 选择 "**下一步**" 继续。
14. 在 "**检查**" 页上，查看您为策略更新的设置。 选择 "**编辑**" 以更改任何策略值，或选择 "**提交**" 以更新并激活策略。

## <a name="delete-a-policy"></a>删除策略

>[!NOTE]
>删除策略不会删除策略生成的活动或存档警报。

若要删除现有的内幕风险管理策略，请完成以下步骤：

1. 在[Microsoft 365 合规性中心](https://compliance.microsoft.com)中，转到 "**内幕风险管理**"，然后选择 "**策略**" 选项卡。
2. 在 "策略" 仪表板上，选择要删除的策略。
3. 在仪表板工具栏上选择 "**删除**"。
4. 在 "**删除**" 对话框中，选择 **"是"** 以删除策略，或选择 "**取消**" 关闭对话框。
