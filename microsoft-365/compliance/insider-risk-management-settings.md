---
title: 内部风险管理设置
description: 了解 Microsoft 365 中的内部风险管理设置
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
ms.openlocfilehash: dd72ded935b9108e4b2699f5ddb6d320f5c32e69
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/13/2021
ms.locfileid: "49841253"
---
# <a name="get-started-with-insider-risk-management-settings"></a>内部风险管理设置入门

内部风险管理设置适用于所有内部风险管理策略，无论你在创建策略时选择哪个模板。 设置使用位于所有内部风险管理选项卡顶部的内部风险设置控制进行配置。 这些设置控制以下方面的策略组件：

- 隐私
- 指示器
- 策略时间线
- 智能检测
- 导出警报 (预览) 
- 预览版 (用户组) 
- 预览版 (优先) 
- Power Automate 流 (预览) 
- Microsoft Teams (预览) 

在开始创建内部风险管理策略之前，了解这些设置并选择最适合组织的合规性需求的设置级别非常重要。

## <a name="privacy"></a>隐私

保护具有策略匹配项的用户的隐私非常重要，并且有助于在针对内部风险警报的数据调查和分析评审中提高对象性。 对于具有内部风险策略匹配的用户，可以选择以下设置之一：

- **显示匿名版本的用户名**：对用户名进行匿名处理，以防止管理员、数据调查人员和审阅者查看与策略警报相关联的人员。 例如，在内部风险管理体验的所有方面，用户"Grace Grace"都会显示随机化假名，如"AnonIS8-988"。 选择此设置可匿名处理具有当前和过去策略匹配项的所有用户，并适用于所有策略。 选择此选项后，内部风险警报中的用户配置文件信息和案例详细信息将不可用。 但是，向现有策略添加新用户或向新策略分配用户时将显示用户名。 如果选择关闭此设置，将为具有当前或过去策略匹配项的所有用户显示用户名。
- **不显示匿名版本的** 用户名：针对警报和事例显示所有当前和过去的策略匹配项的用户名。 用户 (所有内部风险管理警报和案例) 显示的名称、职务、别名和组织或部门信息的用户配置文件信息。

![内部风险管理隐私设置](../media/insider-risk-settings-privacy.png)

## <a name="indicators"></a>指示器

内部风险策略模板定义要检测和调查的风险活动的类型。 每个策略模板都基于与特定触发器和风险活动对应的特定指标。 默认情况下禁用所有指示器，在配置内部风险管理策略之前，必须选择一个或多个策略指示器。

当用户执行与符合所需阈值的策略指示器相关的活动时，策略会触发警报。 内部风险管理使用两种类型的指示器：

- **触发事件**：用于确定用户是否处于活动状态的内部风险管理策略的事件。 如果添加到内部风险管理策略的用户没有触发事件，则策略不会评估用户活动。 例如，通过离开用户策略模板，并且正确配置了策略和 Microsoft 365 HR 连接器，将用户 A 添加到从数据盗窃创建的策略中。 在用户 A 有 HR 连接器报告的终止日期之前，此内部风险管理策略不会评估用户 A 活动的风险。 触发事件的另一个示例是用户使用数据泄露策略时是否具有高严重性 DLP *策略* 警报。
- **策略指标**：内部风险管理策略中包含的指示器，用于确定范围内用户的风险评分。 这些策略指示器仅在用户触发事件发生后激活。 策略指示器的一些示例包括当用户将数据复制到个人云存储服务或便携存储设备时，或者用户是否与未经授权的外部方共享内部文件和文件夹。

策略指示器分为以下几个区域。 在创建内部风险策略时，可以选择指示器来激活和自定义每个指示器级别的指示器事件限制：

- **Office 指示器**：其中包括 SharePoint 网站、Teams 和电子邮件的策略指示器。
- **设备指示器**：其中包括用于活动的策略指示器，例如通过网络或与设备共享文件。 指示器包括涉及文件Microsoft Office活动。CSV 文件和 。PDF 文件。 如果选择设备 **指示器**，则仅处理 Windows 10 版本 1809 或更高版本的设备的活动。 有关配置设备以与内部风险集成的信息，请参阅以下"启用设备指示器和载入 [设备"](insider-risk-management-settings.md#OnboardDevices) 部分。
- **安全策略违反指示器**：其中包括来自 Microsoft Defender for Endpoint 的与未批准或恶意软件安装或绕过安全控制相关的指示器。 若要在内部风险管理中接收警报，必须启用活动的 Defender for Endpoint 许可证和内部风险集成。 有关为 Endpoint 配置 Defender 以用于内部风险管理集成，请参阅 [在 Microsoft Defender for Endpoint 中配置高级功能](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-features\#share-endpoint-alerts-with-microsoft-compliance-center)。
- **风险评分：** 其中包括提高异常活动或过去违反策略的风险评分。 启用风险评分会提高风险评分以及针对这些类型的活动发出警报的可能性。 只有在选择了一个或多个指标时，才能选择风险评分分数。

![内部风险管理指示器设置](../media/insider-risk-settings-indicators.png)

在某些情况下，你可能希望限制应用于组织中内部风险策略的内部风险策略指标。 可以通过禁用特定区域的所有内部风险策略来关闭这些策略指示器。 无法针对内部风险策略模板修改触发事件。

若要定义在所有内部风险策略中启用的内部风险策略指标，请导航到"**内部** 风险设置指示器"，然后选择  >  一个或多个策略指示器。 在策略向导中创建或编辑内部风险策略时，无法单独配置在"指标设置"页上选择的指示器。

>[!NOTE]
>可能需要几个小时，新的手动添加的用户才能显示在用户 **仪表板中**。 这些用户过去 90 天的活动最多可能需要 24 小时才能显示。 若要查看手动添加的用户的活动，请在"用户"仪表板中选择用户，然后打开详细信息窗格上的"用户活动"选项卡。

### <a name="enable-device-indicators-and-onboard-devices"></a>启用设备指示器和载入设备
<a name="OnboardDevices"> </a>

若要启用对设备上的风险活动的监视并包括这些活动的策略指示器，你的设备必须满足以下要求，并且必须完成以下载入步骤。

#### <a name="step-1-prepare-your-endpoints"></a>步骤 1：准备终结点

确保计划在内部风险管理中报告 Windows 10 设备满足这些要求。

1. 必须运行 Windows 10 x64 版本 1809 或更高版本，并且必须已安装 Windows 10 更新 ([OS 版本 17763.1075) ](https://support.microsoft.com/help/4537818/windows-10-update-kb4537818) 2020 年 2 月 20 日。
2. 所有设备必须[已加入 Azure Active Directory (AAD)](https://docs.microsoft.com/azure/active-directory/devices/concept-azure-ad-join) 或已加入混合 Azure AD。
3. 在终结点设备上安装 Microsoft Chromium Edge 浏览器，以监视云上传活动的操作。 请参见[下载基于 Chromium 的新 Microsoft Edge](https://support.microsoft.com/help/4501095/download-the-new-microsoft-edge-based-on-chromium)。

#### <a name="step-2-onboarding-devices"></a>步骤 2：载入设备
<a name="OnboardStep2"> </a>

必须先启用设备监控并载入终结点，然后才能监视设备上的内部风险管理活动。 这两项操作都在 Microsoft 365 合规门户中完成。

当你希望载入尚未载入的设备时，你将下载相应的脚本并按照以下步骤所述进行部署。

已载入到 [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/) 的设备将显示在“托管设备”列表中。 按照[步骤 3：如果你的设备已载入下一节中的 Microsoft Defender for Endpoint。](insider-risk-management-settings.md#OnboardStep3)

在此部署方案中，你将载入尚未载入的设备，并且你只想监视 Windows 10 设备上的内部风险活动。

1. 打开“[Microsoft 合规中心](https://compliance.microsoft.com)”。
2. 打开合规中心设置页面，然后选择“**载入设备**”。

   > [!NOTE]
   > 设备载入通常需要大约 60 秒才能启用，请先等待 30 分钟，然后再与 Microsoft 支持人员接洽。

3. 选择“**设备管理**”，以打开“**设备**”列表。 在载入设备之前，此列表将为空。
4. 选择“**载入**”以开始载入流程。
5. 从部署方法列表中选择你想要部署到这些更多设备的方式，然后 **下载程序包**。 
6. 按照[适用于 Windows 10 计算机的载入工具和方法](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)中的相应程序进行操作。 此链接将你进入登录页面，可以在其中访问与步骤 5 中所选的部署包匹配的 Microsoft Defender for Endpoint 过程：
    - 使用组策略载入 Windows 10 计算机
    - 使用 Microsoft Endpoint Configuration Manager 载入 Windows 10 计算机
    - 使用移动设备管理工具载入 Windows 10 计算机
    - 使用本地脚本载入 Windows 10 计算机
    - 载入非持久性虚拟桌面基础结构 (VDI) 计算机。

完成后，终结点载入后，它应显示在设备列表中，终结点将开始向内部风险管理报告审核活动日志。

> [!NOTE]
> 此体验根据许可证强制实施。 如果没有所需的许可证，数据将不可见或不可访问。

#### <a name="step-3-if-you-have-devices-onboarded-into-microsoft-defender-for-endpoint"></a>步骤 3：如果你的设备已载入 Microsoft Defender for Endpoint
<a name="OnboardStep3"> </a>

如果 Microsoft Defender for Endpoint 已部署并且有终结点报告，所有这些终结点都将显示在托管设备列表中。 你可以继续使用"步骤 [2：](insider-risk-management-settings.md#OnboardStep2) 载入设备"部分将新设备载入内部风险管理，以扩大覆盖范围。

1. 打开“[Microsoft 合规中心](https://compliance.microsoft.com)”。
2. 打开合规中心设置页面，然后选择“**启用设备监视**”。
3. 选择“**设备管理**”，以打开“**设备**”列表。 你应该会看到已经向 Microsoft Defender for Endpoint 报告的设备列表。
4. 如果需要 **载入** 更多设备，请选择"载入"。
5. 从部署方法列表中选择你想要部署到这些更多 **设备的方式，** 然后 **下载程序包**。
6. 按照[适用于 Windows 10 计算机的载入工具和方法](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)中的相应程序进行操作。 此链接将你进入登录页面，可以在其中访问与步骤 5 中所选的部署包匹配的 Microsoft Defender for Endpoint 过程：
    - 使用组策略载入 Windows 10 计算机
    - 使用 Microsoft Endpoint Configuration Manager 载入 Windows 10 计算机
    - 使用移动设备管理工具载入 Windows 10 计算机
    - 使用本地脚本载入 Windows 10 计算机
    - 载入非持久性虚拟桌面基础结构 (VDI) 计算机。

完成后，终结点载入后，它应显示在 **"设备** "表下，终结点将开始向内部风险管理报告审核活动日志。

> [!NOTE]
>此体验根据许可证强制实施。 如果没有所需的许可证，数据将不可见或不可访问。

### <a name="indicator-level-settings-preview"></a>用于预览 (指示器级别) 

在策略向导中创建策略时，可以配置每日风险事件数如何影响内部风险警报的风险评分。 这些指示器设置可帮助您控制组织中发生风险事件的数量对这些事件的风险评分以及因此相关联的警报严重性有何影响。 如果愿意，还可以选择保留 Microsoft 建议的所有已启用指示器的默认事件阈值级别。

例如，您决定在内部风险策略设置中启用 SharePoint 指示器，在配置新的内部风险数据泄露策略的指示器时为 SharePoint 事件设置 *自定义阈值。* 在内部风险策略向导中，您可以为每个 SharePoint 指示器配置三个不同的每日事件级别，以影响与这些事件关联的警报的风险评分。

![内部风险管理自定义指示器设置](../media/insider-risk-custom-indicators.png)

对于第一个每日事件级别，将阈值设置为每天 *10* 个或多个事件，以将影响低于事件的风险分数，每天 *20* 个或多个事件设置为对事件的风险分数有中等影响，每天 *30* 个或多个事件对事件的风险分数影响更大。 这些设置实际上意味着：

- 如果触发事件后发生 1-9 个 SharePoint 事件，风险评分的影响最小，并且通常不会生成警报。
- 如果触发事件后发生 10-19 个 SharePoint 事件，则风险评分本身较低，警报严重性级别将倾向于较低级别。
- 如果触发后发生 20-29 个 SharePoint 事件，则风险评分本身会更高，警报严重性级别通常处于中等级别。
- 如果触发后发生 30 次或更多的 SharePoint 事件，则风险评分本身会更高，警报严重性级别通常较高。

## <a name="policy-timeframes"></a>策略时间范围

策略时间范围允许你根据内部风险管理策略模板的事件和活动定义在策略匹配后触发的过去和将来的审阅阶段。 根据你选择的策略模板，可以使用以下策略时间范围：

- **激活窗口**：激活窗口可用于所有策略模板，它是在触发事件后窗口激活的定义天数。  对于分配到策略的任何用户，该窗口在触发事件发生后的 1 到 30 天内激活。 例如，你已配置内部风险管理策略，将激活 *窗口设置为* 30 天。 自配置策略以来，已经过去几个月，并且策略中包含的用户之一发生了触发事件。 触发事件将激活 *激活* 窗口，并且策略在触发事件发生后的 30 天内为该用户激活。
- **过去的活动** 检测："过去"活动检测可用于所有策略模板，它是在触发事件之前窗口激活的定义天数。  在分配给策略的任何用户触发事件发生前 0 到 180 天，窗口将激活。 例如，你已配置内部风险管理策略，将过去 *的活动检测设置为* 90 天。 自配置策略以来，已经过去几个月，并且策略中包含的用户之一发生了触发事件。 触发事件激活 *"过去"活动检测* ，并且策略在触发事件前 90 天内收集该用户的历史活动。

![内部风险管理时间范围设置](../media/insider-risk-settings-timeframes.png)

## <a name="intelligent-detections"></a>智能检测

智能检测设置有助于优化如何针对警报处理风险活动的检测。 在某些情况下，您可能需要定义要忽略的文件类型，或者希望对文件强制执行检测级别以帮助定义警报的最低条。 使用冒犯性语言策略时，可能需要增加或降低检测敏感度，以控制报告的策略匹配数量。 使用这些设置可控制总体警报量、文件类型排除、文件卷限制和冒犯性语言检测敏感度。

![内部风险管理智能检测设置](../media/insider-risk-settings-detections.png)

### <a name="anomaly-detections"></a>异常检测

异常检测包括文件类型排除和文件卷限制的设置。

- **文件类型排除**：若要从所有内部风险管理策略匹配中排除特定文件类型，请输入以逗号分隔的文件类型扩展名。 例如，若要从策略匹配中排除某些类型的音乐文件，您可以在文件类型排除字段中输入 *aac，mp3，wav，wma。*  所有内部风险管理策略将忽略具有这些扩展名的文件。
- **文件卷截止限制**：若要在内部风险策略中报告活动警报之前定义最低文件级别，请输入文件数。 例如，如果不希望在用户下载 10 个或更少文件时生成内部风险警报，则输入"10"，即使策略认为此活动异常。

### <a name="offensive-language-detections"></a>冒犯性语言检测

>[!IMPORTANT]
>从 2020 年 10 月 16 日起，将无法再使用此模板创建策略。 使用此模板的任何活动策略都将有效，直到 2021 年 1 月永久删除。 我们弃用支持此模板的冒犯性语言内置分类器，因为它一直产生大量误报。 若要解决冒犯性语言的风险问题，我们建议使用 Microsoft 365 [通信合规性](communication-compliance.md) 策略。 有关内置分类器的信息，请参阅可 [训练分类器入门](classifier-get-started-with.md)。

若要调整在电子邮件模板中使用冒犯性语言的策略的冒犯性语言分类器敏感度，请选择以下设置之一：

- **低**：检测冒犯性语言和情绪范围最广的最低敏感度级别。 冒犯性语言匹配误报的可能性提高。
- **中等**：中等级别敏感度级别，具有用于检测冒犯性语言和情绪的平衡范围。 冒犯性语言匹配误报的概率是平均值。
- **高**：检测冒犯性语言和情绪范围较窄的最高敏感度级别。 冒犯性语言匹配误报的可能性较低。

### <a name="alert-volume"></a>警报量

为内部风险策略检测到的用户活动分配特定的风险分数，该分数反过来确定警报严重性 (低、中、高) 。 默认情况下，我们将生成一定数量的低、中和高严重性警报，但你可以增加或减少音量以满足你的需求。 若要调整所有内部风险管理策略的警报量，请选择以下设置之一：

- **较少的警报**：你将看到所有高严重性警报、中等严重性警报和低严重性警报。 此设置级别意味着你可能会错过一些真正的误报。
- **默认卷**：你将看到所有高严重性警报以及中等和低严重性警报的平衡量。
- **更多警报**：你将看到所有中等和高严重性警报以及最低严重性警报。 此设置级别可能会导致更多的误报。

### <a name="microsoft-defender-for-endpoint-preview"></a>Microsoft Defender for Endpoint (预览) 

[Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) 是一个企业终结点安全平台，旨在帮助企业网络预防、检测、调查和响应高级威胁。 为了更好地了解组织中违反安全的行为，你可以导入和筛选 Defender for Endpoint 警报，以针对根据内部风险管理安全违反策略模板创建的策略中使用的活动。

根据你感兴趣的信号类型，你可以选择根据 Defender for Endpoint 警报会审状态将警报导入内部风险管理。 可以在要导入的全局设置中定义以下一个或多个警报会审状态：

- 未知
- 新式
- 正在进行
- 已解决

来自 Defender for Endpoint 的警报每天导入一次。 根据你选择的会审状态，你可能会看到与 Defender for Endpoint 中的会审状态更改相同的警报的多个用户活动。

例如，如果为此设置选择"新建"、"正在进行"和"已解决"，则当生成 Microsoft Defender for Endpoint 警报并且状态为 *"* 新建"时，会为存在内部风险的用户导入初始警报活动。  当 Defender for Endpoint 会审状态更改为"正在进行"时，会为存在内部风险的用户导入此警报的第二个活动。 当设置"已解决"的最终 Defender终结点会审状态时，会为存在内部风险的用户导入此警报的第三个活动。 此功能允许调查人员跟踪 Defender for Endpoint 警报进度，并选择其调查所需的可见性级别。

>[!IMPORTANT]
>你需要在你的组织中配置 Microsoft Defender for Endpoint，并启用 Defender for Endpoint，以便 Defender 安全中心中的内部风险管理集成导入安全违反警报。 有关为 Endpoint 配置 Defender 进行内部风险管理集成的信息，请参阅在 Defender for Endpoint 中 [配置高级功能](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-features\#share-endpoint-alerts-with-microsoft-compliance-center)。

### <a name="domains-preview"></a>域 (预览) 

域设置可帮助您定义与特定域的通信的风险级别。 这些通信包括共享文件、电子邮件或下载内容。 通过指定这些设置中的域，您可以增加或降低使用这些域进行的活动的风险评分。 例如，若要将contoso.com和sales.wingtiptoys.com域，请在"允许域"字段中输入 **"contoso.com sales.wingtiptoys.com"。**

对于以下每个域设置，您最多可以输入 500 个域：

- **不允许的域：** 通过指定不允许的域，使用这些域进行的活动将具有 *更高的* 风险评分。
- **允许的域：** 通过指定设置中的允许域，使用这些域进行的活动的风险分数将较低，并且处理方式与处理内部组织活动的方式类似。 例如，这些域的电子邮件活动的分析方式与分析内部电子邮件活动的方式类似。
- **第三方域：** 第三方域是组织用于业务用途的域，敏感内容可能存储在这些位置。 通过指定第三方域，您可以收到有关这些域上任何有风险活动的警报。

## <a name="export-alerts-preview"></a>导出警报 (预览) 

内部风险管理警报信息可通过 [Office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#security-and-compliance-alerts-schema)管理活动 API 架构导出 (SIEM) 服务的安全信息和事件管理。 您可以使用 Office 365 管理活动 API 将警报信息导出到组织可能用于管理或聚合内部风险信息的其他应用程序。

若要使用 API 查看内部风险警报信息：

1. 在 Insider risk management Settings Export中启用 Office 365 管理活动 API  >    >  **支持**。 默认情况下，为 Microsoft 365 组织禁用此设置。
2. 按 *SecurityComplianceAlerts* 筛选常见的 Office 365 审核活动。
3. 按 *InsiderRiskManagement* 类别筛选 *SecurityComplianceAlerts。*

![内部风险管理导出警报设置](../media/insider-risk-settings-export.png)

警报信息包含来自安全与合规警报架构和 Office 365 管理活动 API 通用架构的信息。

针对安全与合规警报架构的内部风险管理警报导出&字段和值：

| **Alert 参数** | **说明** |
|:------------------|:----------------|
| AlertType | 警报的类型为 *"自定义"。*  |
| AlertId | 警报的 GUID。 内部风险管理警报是可变的。 当警报状态更改时，将生成一个同一 AlertID 的新日志。 此 AlertID 可用于关联警报的更新。 |
| 类别 | 警报的类别是 *InsiderRiskManagement。* 此类别可用于区分这些警报与其他安全与合规&警报。 |
| 备注 | 警报的默认注释。 值是在 *(* 警报更新时记录的新警报) 和 (更新时记录警报更新) 。  使用 AlertID 关联警报的更新。 |
| Data | 警报的数据包括唯一的用户 ID、用户主体名称，以及当用户被触发到策略 (UTC) 日期和时间。 |
| 名称 | 生成警报的内部风险管理策略的策略名称。 |
| PolicyId | 触发警报的内部风险管理策略的 GUID。 |
| Severity | 警报的严重性。 值为 *"高**"、"中"* 或"*低"。* |
| Source | 警报的来源。 值为 *Office 365 安全&合规性*。 |
| 状态 | 警报的状态。 值为"内部 (风险) 中的活动 (审核、*调查 (在* 内部风险中确认的) 、解决的 *(**在* 内部风险) 中已解决、 (在内部风险中) 。  |
| 版本 | 安全性和合规性警报架构的版本。 |

针对 [Office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#common-schema)管理活动 API 通用架构的内部风险管理警报导出以下字段和值。

- UserID
- Id
- RecordType
- CreationTime
- 操作
- OrganizationId
- UserType
- UserKey

## <a name="priority-user-groups-preview"></a>预览版 (用户组) 

您组织中用户可能具有不同的风险级别，具体取决于他们的位置、敏感信息的访问级别或风险历史记录。 确定这些用户活动的检查和评分优先级有助于提醒您注意可能给组织造成更大后果的潜在风险。 内部风险管理中的优先用户组可帮助定义组织中需要更仔细的检查和更敏感的风险评分的用户。 与优先级用户违反安全策略和优先级用户策略模板泄露数据一起，添加到优先级用户组的用户具有更高严重性级别的内部风险警报和警报的可能性。

![内部风险管理优先级用户组设置](../media/insider-risk-settings-priority-users.png)

例如，您需要防止高度机密项目（用户有权访问敏感信息）的数据泄露。 您 *选择为组织中* 处理此项目的用户创建机密项目用户优先级用户组。 使用策略向导和按优先级用户策略模板泄露的数据，您可以创建一个新策略，并将"机密 *项目用户*"优先级用户组分配给该策略。 由策略检查的机密项目用户优先级用户组的成员的活动对风险更为敏感，这些用户的活动更有可能生成警报，并且具有严重性级别更高的警报。

### <a name="create-a-priority-user-group"></a>创建优先级用户组

若要创建新的优先级用户组，你将使用 Microsoft 365 合规中心内部风险管理解决方案中的设置控件。 若要创建优先级用户组，您必须是 *Insider Risk Management* 或 Insider *Risk Management Admin* 角色组的成员。

完成以下步骤以创建优先级用户组：

1. 在 [Microsoft 365 合规中心](https://compliance.microsoft.com)，转到 **"内部** 风险管理"并选择 **"内部风险设置"。**
2. 选择 **"优先级用户组"** 选项卡
3. 在 **"优先级用户组"** 选项卡上，选择 **"创建优先级用户组** "以启动组创建向导。
4. 在" **定义组"** 页上，填写以下字段：
    - **Name (required)**： Enter a friendly name for the priority user group. 完成向导后，不能更改优先级用户组的名称。
    - **说明 (可选) ：** 输入优先级用户组的说明。
5. 选择 **"下一** 步"继续。
6. 在"**选择** 成员"页上，选择"选择要搜索的成员"，然后选择组中包含哪些已启用邮件的用户帐户，或选中"选择所有"复选框以将您组织中所有用户添加到组中。 选择 **"添加** "继续或" **取消** "以关闭，而不向组添加任何用户。
7. 选择 **"下一** 步"继续。
8. 在 **"** 审阅"页上，查看为优先级用户组选择的设置。 选择 **"** 编辑"可更改任何组值，或 **选择"** 提交"以创建并激活优先级用户组。
9. 在确认页上，选择 **"完成** "退出向导。

### <a name="update-a-priority-user-group"></a>更新优先级用户组

若要更新现有优先级用户组，你将使用 Microsoft 365合规中心内部风险管理解决方案中的设置控件。 若要更新优先级用户组，您必须是 *Insider Risk Management* 或 Insider *Risk Management Admin 角色* 组的成员。

完成以下步骤以编辑优先级用户组：

1. 在 [Microsoft 365 合规中心](https://compliance.microsoft.com)，转到 **"内部** 风险管理"并选择 **"内部风险设置"。**
2. 选择 **"优先级用户组"** 选项卡
3. 选择要编辑的优先级用户组，然后选择"编辑 **组"。**
4. 在" **定义组"** 页上，根据需要更新"说明"字段。 无法更新优先级用户组的名称。 选择 **"下一** 步"继续。
5. 在 **"选择成员"** 页上，使用"选择成员"控件将新成员 **添加到** 组中。 若要从组中删除用户，请选择要删除的用户旁边的"X"。 选择 **"下一** 步"继续。
6. 在 **"审阅** "页上，查看为优先级用户组选择的更新设置。 选择 **"** 编辑"可更改任何组值，或 **选择"** 提交"以更新优先级用户组。
7. 在确认页上，选择 **"完成** "退出向导。

### <a name="delete-a-priority-user-group"></a>删除优先级用户组

若要删除现有优先级用户组，你将使用 Microsoft 365合规中心内部风险管理解决方案中的设置控件。 若要删除优先级用户组，您必须是 *Insider Risk Management* 或 Insider *Risk Management Admin 角色* 组的成员。

>[!IMPORTANT]
>删除优先级用户组会将其从分配到的任何活动策略中删除。 如果删除分配给活动策略的优先级用户组，该策略将不包含任何范围内用户，并且实际上处于空闲状态，并且不会创建警报。

完成以下步骤以删除优先级用户组：

1. 在 [Microsoft 365 合规中心](https://compliance.microsoft.com)，转到 **"内部** 风险管理"并选择 **"内部风险设置"。**
2. 选择 **"优先级用户组"** 选项卡
3. 选择要编辑的优先级用户组， **然后从仪表板** 菜单中选择"删除"。
4. 在 **"删除**"对话框中，选择 **"是**"删除优先级用户组，或选择"取消"返回到仪表板。

## <a name="priority-physical-assets-preview"></a>预览版 (优先) 

确定对优先级物理资产的访问权限以及将访问活动与用户事件关联是合规性基础结构的一个重要组件。 这些物理资产表示组织中优先级的位置，例如公司大楼、数据中心或服务器会议室。 内部风险活动可能与在非正常时段工作、试图访问这些未经授权的敏感或安全区域的用户以及请求在没有合法需求的情况下访问高级区域相关联。

启用优先物理资产并配置 [物理](import-physical-badging-data.md) 保护数据连接器后，内部风险管理将来自物理控制和访问系统的信号与其他用户风险活动集成。 通过检查物理访问系统之间的行为模式，以及将这些活动与其他内部风险事件关联，内部风险管理可帮助合规性调查人员和分析人员对警报做出更明智的响应决策。 对优先级物理资产的访问权限的评分和标识在见解中与访问非优先级资产的方式不同。

例如，您的组织具有一个保护系统，用于监视和批准对正常工作和敏感项目区域的物理访问。 您让多个用户处理敏感项目，这些用户在项目完成后将返回到组织的其他区域。 当敏感项目接近完成时，您需要确保项目工作保持机密，并确保严格控制对项目区域的访问权限。

选择在 Microsoft 365 中启用物理保护数据连接器，以从物理保护系统导入访问信息，并指定内部风险管理中优先级的物理资产。 通过从错误系统导入信息，以及将物理访问信息与内部风险管理中确定的其他风险活动关联，你会注意到项目中的一个用户在正常工作时间之后访问项目办公室，并且正在从正常工作区域将大量数据导出到个人云存储服务。 与联机活动关联的此物理访问活动可能指向可能的数据盗窃和合规性调查人员，分析员可以按照此用户的情况执行相应操作。

### <a name="configure-priority-physical-assets"></a>配置优先级物理资产

若要配置优先物理资产，您需要配置物理保护连接器，并使用 Microsoft 365 合规中心内部风险管理解决方案中的设置控件。 若要配置优先物理资产，您必须是 Insider Risk *Management* 或 *Insider Risk Management Admin 角色组的成员*。

完成以下步骤以配置优先级物理资产：

1. 按照内部风险管理入门文章中有关内部风险管理 [的配置](insider-risk-management-configure.md) 步骤操作。 在步骤 3 中，确保配置物理保护连接器。

    >[!IMPORTANT]
    >若要内部风险管理策略使用与离开和终止用户相关的信号数据，并将这些数据与物理控制和访问平台的事件数据关联，还必须配置 Microsoft 365 HR 连接器。 如果在未启用 Microsoft 365 HR 连接器的情况下启用物理保护连接器，内部风险管理策略将仅处理组织中用户的物理访问活动的事件。

2. 在 [Microsoft 365 合规中心](https://compliance.microsoft.com)，转到 **"内部** 风险管理"并选择 **"内部风险设置** 优先级  >  **物理资产"。**
3. 在 **"优先级物理** 资产"页上，您可以手动添加要监视的物理资产 ID，以检查物理损坏连接器导入的资产事件，也可以导入一个 。由物理保护连接器导入的所有物理资产 ID 的 CSV 文件：) 若要手动添加物理资产 ID，请选择"添加优先级物理资产"，输入物理资产 ID，然后选择"添加 **"。**  输入其他物理资产 ID，然后选择"添加 **优先级物理资产** "以保存输入的所有资产。
    b) 添加来自 的物理资产 ID 的列表。CSV 文件，选择 **"导入优先级物理资产"。** 从文件资源管理器对话框中，选择 。要导入的 CSV 文件，然后选择"打开 **"。** 中的物理资产 ID。CSV 文件将添加到列表中。
4. 导航到 **"设置"中的"策略** 指示器"选项卡。
5. 在"**策略指示器"** 页上，导航到"物理访问指示器"部分，选中"终止或无法访问敏感资产后的物理访问 **"复选框**。
6. 选择 **"保存** "以配置并退出。

### <a name="delete-a-priority-physical-asset"></a>删除优先级物理资产

若要删除现有优先级物理资产，你将使用 Microsoft 365 合规中心内部风险管理解决方案中的设置控件。 若要删除优先级物理资产，您必须是 Insider Risk Management 或 Insider Risk Management Admin 角色组的成员。

>[!IMPORTANT]
>删除优先级物理资产会将其从之前包含的任何活动策略检查。 不会删除由与优先级物理资产关联的活动生成的警报。

完成以下步骤以删除优先级物理资产：

1. 在 [Microsoft 365 合规中心](https://compliance.microsoft.com)，转到 **"内部** 风险管理"并选择 **"内部风险设置** 优先级  >  **物理资产"。**
2. 在 **"优先级物理资产** "页上，选择要删除的资产。
3. 在 **操作** 菜单上选择"删除"可删除资源。

## <a name="power-automate-flows-preview"></a>Power Automate 流 (预览) 

[Microsoft Power Automate](https://docs.microsoft.com/power-automate/getting-started) 是一种工作流服务，可自动执行应用程序和服务中的操作。 通过使用模板中的流或手动创建流，可以自动执行与这些应用程序和服务关联的常见任务。 启用 Power Automate 流进行内部风险管理时，可以自动执行事例和用户的重要任务。 可以将 Power Automate 流配置为检索用户、警报和案例信息，并与利益干系人和其他应用程序共享此信息，以及自动执行内部风险管理中的操作，例如发布到案例说明。 Power Automate 流适用于事例和策略范围内的任何用户。

具有包含内部风险管理的 Microsoft 365 订阅的客户不需要其他 Power Automate 许可证来使用建议的内部风险管理 Power Automate 模板。 可以自定义这些模板以支持您的组织并涵盖核心内部风险管理方案。 如果你选择在这些模板中使用高级 Power Automate 功能，使用 Microsoft 365 合规性连接器创建自定义模板，或者为 Microsoft 365 中其他合规性区域使用 Power Automate 模板，你可能需要更多 Power Automate 许可证。

以下 Power Automate 模板提供给客户以支持内部风险管理用户和案例的流程自动化：

- **将用户** 添加到内部风险策略时通知用户：此模板适用于具有内部策略、隐私或法规要求的组织，这些组织在用户受内部风险管理策略的约束时必须收到通知。 在用户页面中为用户配置和选择此流时，当用户添加到内部风险管理策略时，会向用户及其经理发送电子邮件。 此模板还支持更新 SharePoint 网站上托管的 SharePoint 列表，以帮助跟踪通知邮件详细信息，如日期/时间和邮件收件人。 如果你已选择在"隐私"设置中匿名处理用户，则从此模板创建的流将不会如预期方式工作，以便保持用户隐私。 使用此模板的 Power Automate 流在用户 **仪表板上可用**。
- 向 **HR** 或业务请求有关内部风险案例中用户的信息：当对案例采取行动时，内部风险分析员和调查人员可能需要咨询 HR 或其他利益干系人，以了解案例活动的上下文。 当为案例配置和选择此流时，分析员和调查人员会向为此流程配置的 HR 和业务利益干系人发送电子邮件。 向每个收件人发送一封邮件，其中包含预配置或可自定义的响应选项。 当收件人选择响应选项时，该响应将记录为案例注释，并包括收件人和日期/时间信息。 如果你已选择在"隐私"设置中匿名处理用户，则从此模板创建的流将不会如预期方式工作，以便保持用户隐私。 "案例"仪表板上提供了使用此模板的 Power Automate **流**。
- **当用户有内部风险警报** 时通知经理：当用户有内部风险管理警报时，某些组织可能需要立即发送管理通知。 配置和选择此流后，会向案例用户的经理发送一封电子邮件，包含有关所有案例警报的以下信息：
    - 适用于警报的策略
    - 警报的日期/时间
    - 警报的严重性级别

    流自动更新大小写，表明已发送邮件，并且流已激活。 如果你已选择在"隐私"设置中匿名处理用户，则从此模板创建的流将不会如预期方式工作，以便保持用户隐私。 "案例"仪表板上提供了使用此模板的 Power Automate **流**。

- **添加日历提醒以** 跟进内部风险案例：此模板允许风险分析员将事例的日历提醒添加到其 Office 365 Outlook 日历。 此流使用户在处理案例和会审警报时无需退出或退出内部风险管理工作流。 配置和选择此流后，会向 Office 365 Outlook 日历中添加一个提醒，提醒运行该流的用户。 "案例"仪表板上提供了使用此模板的 Power Automate **流**。
- **在 ServiceNow 中为内部** 风险案例创建记录：此模板适用于想要使用其 ServiceNow 解决方案跟踪内部风险管理案例的组织。  在这种情况下，内部风险分析员和调查人员可以在 ServiceNow 中为案例创建记录。 您可以自定义此模板，以根据组织的要求填充 ServiceNow 中的选定字段。 "案例"仪表板上提供了使用此模板的 Power Automate **流**。 有关可用 ServiceNow 字段详细信息，请参阅 [ServiceNow 连接器参考](/connectors/service-now/) 文章。

### <a name="create-a-power-automate-flow-from-insider-risk-management-template"></a>从内部风险管理模板创建 Power Automate 流

若要从建议的内部风险管理模板创建 Power Automate 流，你将使用 Microsoft 365合规中心内部风险管理解决方案中的设置控件，或在直接在"案例"或"用户"仪表板中操作时，使用"自动执行"控件中的"管理 **Power Automate** 流"选项。

若要在设置区域中创建 Power Automate 流，您必须是 *Insider Risk Management* 或 Insider Risk Management *Admin* 角色组的成员。 若要使用"管理 Power Automate 流"选项创建 **Power Automate** 流，必须至少是一个内部风险管理角色组的成员。

完成以下步骤以从建议的内部风险管理模板创建 Power Automate 流：

1. 在 [Microsoft 365 合规中心](https://compliance.microsoft.com/)，转到 **"内部** 风险管理"，然后选择 **"内部风险设置**  >  **"Power Automate 流**。 You can also access from the **Cases** or **Users dashboards** pages by choosing **Automate** Manage Power  >  **Automate flows.**
2. 在 **"Power Automate 流"** 页上，从预览体验成员风险管理模板中选择建议模板， **你可能喜欢该页面上** 的部分。
3. 该流列出了流所需的嵌入连接，并记录连接状态是否可用。 如果需要，请更新任何未显示为可用的连接。 选择 **"继续"。**
4. 默认情况下，建议的流预配置了建议的内部风险管理和 Microsoft 365 服务数据字段，这些字段是完成流的分配任务所需的。 如果需要，使用"显示高级选项"控件和配置流组件的可用属性来自定义流组件。
5. 如果需要，通过选择"新建步骤"按钮将任何其他步骤 **添加到** 流中。 在大多数情况下，建议的默认模板不需要这样做。
6. 选择 **"保存草稿** "保存流以进一步配置， **或选择"** 保存"以完成流的配置。
7. 选择 **"** 关闭"返回到 **"Power Automate 流"** 页。 新模板将在"我的流"选项卡上作为流列出，当为用户创建流处理内部风险管理案例时，会自动从"自动化"下拉列表控件中提供该模板。

>[!IMPORTANT]
>如果组织中其他用户需要访问流，则必须共享流。

### <a name="create-a-custom-power-automate-flow-for-insider-risk-management"></a>为内部风险管理创建自定义 Power Automate 流

您的组织的一些流程和工作流可能超出建议的内部风险管理流模板范围，您可能需要为内部风险管理领域创建自定义 Power Automate 流。 Power Automate 流非常灵活，支持大量自定义，但需要执行一些步骤以与内部风险管理功能集成。

完成以下步骤，为内部风险管理创建自定义 Power Automate 模板：

1. **检查 Power Automate 流许可证**：若要创建使用内部风险管理触发器的自定义 Power Automate 流，需要 Power Automate 许可证。 建议的内部风险管理流模板不需要额外的许可，并作为内部风险管理许可证的一部分包含在内。
2. **创建自动化流**：创建在内部风险管理事件触发后执行一个或多个任务的流。 若要详细了解如何创建自动化流，请参阅在 [Power Automate 中创建流](https://docs.microsoft.com/power-automate/get-started-logic-flow)。
3. **选择 Microsoft 365 合规性连接器**：搜索并选择 Microsoft 365 合规性连接器。 此连接器支持内部风险管理触发器和操作。 有关连接器详细信息，请参阅连接器 [参考概述](https://docs.microsoft.com/connectors/connector-reference/) 文章。
4. **为流程选择** 内部风险管理触发器：内部风险管理有两个触发器可用于自定义 Power Automate 流：
    - **对于选定的内部风险管理案例**：可以从内部风险管理案例仪表板页面选择具有此触发器的流。
    - **对于选定的内部风险管理用户**：可以从内部风险管理用户仪表板页面选择具有此触发器的流。
5. 为流程选择内部风险管理操作：可以从内部风险管理的几个操作中选择，以包括在自定义流中：
    - 获取内部风险管理警报
    - 获取内部风险管理案例
    - 获取内部风险管理用户
    - 获取案例的内部风险管理警报
    - 添加内部风险管理案例注释

### <a name="share-a-power-automate-flow"></a>共享 Power Automate 流

默认情况下，用户创建的 Power Automate 流仅对该用户可用。 若要使其他内部风险管理用户能够访问和使用流，流创建者必须共享该流。 若要共享流，直接在"案例"或"用户"仪表板页面中操作时，将使用 Microsoft 365 合规中心内部风险管理解决方案中的设置控件，或者使用"自动化"控件中的"管理 **Power Automate** 流"**选项**。 共享流后，已共享流的每个人都可以访问"案例"和"用户"仪表板中的"自动化"控件下拉列表 **中的流**。 

若要在设置区域中共享 Power Automate 流，您必须是 *Insider Risk Management* 或 Insider Risk Management *Admin* 角色组的成员。 若要使用"管理 Power Automate 流"选项共享 **Power Automate** 流，必须至少是一个内部风险管理角色组的成员。

完成以下步骤以共享 Power Automate 流：

1. 在 [Microsoft 365 合规中心](htttps://compliance.microsoft.com)，转到 **"内部** 风险管理"，然后选择 **"内部风险设置**  >  **"Power Automate 流**。 You can also access from the **Cases** or **Users dashboards** pages by choosing **Automate** Manage Power  >  **Automate flows.**
2. 在 **"Power Automate 流"** 页上，选择" **我的** 流"或" **团队流"** 选项卡。
3. 选择要共享流 **，然后从** "流选项"菜单中选择"共享"。
4. 在"流共享"页上，输入要添加为流所有者的用户或组的名称。
5. 在 **"连接已** 用"对话框中，选择 **"确定** "确认添加的用户或组将具有对流的完全访问权限。

### <a name="edit-a-power-automate-flow"></a>编辑 Power Automate 流

若要编辑流，在直接在事例或用户仪表板中操作时，将使用 Microsoft 365 合规中心内部风险管理解决方案中的设置控件或自动执行控件中的"管理 **Power** Automate流"**选项。**

若要在设置区域中编辑 Power Automate 流，您必须是 *Insider Risk Management* 或 Insider Risk Management *Admin* 角色组的成员。 若要使用"管理 Power Automate 流"选项编辑 **Power Automate** 流，必须至少是一个内部风险管理角色组的成员。

完成以下步骤以编辑 Power Automate 流：

1. 在 [Microsoft 365 合规中心](htttps://compliance.microsoft.com)，转到 **"内部** 风险管理"，然后选择 **"内部风险设置**  >  **"Power Automate 流**。 You can also access from the **Cases** or **Users dashboards** pages by choosing **Automate** Manage Power  >  **Automate flows.**
2. 在 **"Power Automate 流"** 页上，选择要编辑的流，然后从流控制菜单中选择"编辑"。
3. 选择 **省略号**  >  **"设置**"可更改流组件设置或省略 **号**  >  **"** 删除"以删除流组件。
4. 选择 **"** 保存"， **然后** 关闭以完成对流的编辑。

### <a name="delete-a-power-automate-flow"></a>删除 Power Automate 流

若要删除流，在直接在事例或用户仪表板中操作时，你将使用 Microsoft 365 合规中心内部风险管理解决方案中的设置控件或自动执行控件中的"管理 Power  **Automate** 流"**选项。** 当流被删除时，它将作为所有用户的一个选项删除。

若要删除设置区域中的 Power Automate 流，您必须是 *Insider Risk Management* 或 Insider Risk Management Admin *角色* 组的成员。 若要使用"管理 Power Automate 流"选项删除 **Power Automate** 流，您必须至少是一个内部风险管理角色组的成员。

完成以下步骤以删除 Power Automate 流：

1. 在 [Microsoft 365 合规中心](htttps://compliance.microsoft.com)，转到 **"内部** 风险管理"，然后选择 **"内部风险设置**  >  **"Power Automate 流**。 You can also access from the **Cases** or **Users dashboards** pages by choosing **Automate** Manage Power  >  **Automate flows.**
2. 在 **"Power Automate 流"** 页上，选择要删除的流，然后从流控制菜单中选择"删除"。
3. 在删除确认对话框中， **选择"删除** "以删除流，或 **选择"** 取消"退出删除操作。

## <a name="microsoft-teams-preview"></a>Microsoft Teams (预览) 

合规性分析师和调查人员可以轻松使用 Microsoft Teams 就内部风险管理案例进行协作。 他们可以与 Microsoft Teams 中其他利益干系人进行协调和沟通，以：

- 在专用 Teams 频道中协调并查看案例的响应活动
- 安全地共享和存储与个别案件相关的文件和证据
- 跟踪和审阅分析员和调查人员的响应活动

启用 Microsoft Teams 进行内部风险管理后，每次确认警报并创建案例时，都会创建专门的 Microsoft Teams 团队。 默认情况下，团队自动包括预览体验成员风险管理、内部风险管理分析师和内部风险管理调查人员角色组的所有成员 (最多 100 名初始) 。  创建团队后，可在适当时向团队添加其他组织参与者。 对于在启用 Microsoft Teams 之前创建的现有案例，分析员和调查人员可以选择在需要的情况下创建新 Microsoft Teams 团队。  在内部风险管理中解决相关案例后，团队会自动存档 (移动到隐藏和只读) 。

若要详细了解如何在 Microsoft Teams 中使用团队和频道，请参阅 [Microsoft Teams 中的团队和频道概述](https://docs.microsoft.com/MicrosoftTeams/teams-channels-overview)。

为事例启用 Microsoft Teams 支持快速且易于配置。 若要启用 Microsoft Teams 进行内部风险管理，请完成以下步骤：

1. 在 [Microsoft 365 合规中心](htttps://compliance.microsoft.com)，转到 **"预览** 体验成员风险管理  >  **内部风险设置"。**
2. 选择 **"Microsoft Teams"** 选项卡。
3. 启用 Microsoft Teams 集成以实现内部风险管理。
4. 选择 **"保存** "以配置并退出。

### <a name="create-a-microsoft-teams-team-for-existing-cases"></a>为现有案例创建 Microsoft Teams 团队

如果你在现有案例后启用对内部风险管理的 Microsoft Teams 支持，你将需要根据需要为每个案例手动创建一个团队。 在内部风险管理设置中启用 Microsoft Teams 支持后，新案例将自动创建新的 Microsoft Teams 团队。

用户需要有权在组织中创建 Microsoft 365 组，才能根据情况创建 Microsoft Teams 团队。 有关管理 Microsoft 365 组的权限详细信息，请参阅"管理可以创建[Microsoft 365 组的用户"。](https://docs.microsoft.com/microsoft-365/solutions/manage-creation-of-groups)

若要为案例创建团队，您将在直接处理现有案例时使用"创建 Microsoft 团队"控件。 完成以下步骤以创建新团队：

1. 在 [Microsoft 365](htttps://compliance.microsoft.com)合规中心，转到 **"内部风险管理** 案例"  >  并选择现有案例。
2. 在"案例操作"菜单上，选择 **"创建 Microsoft 团队"。**
3. 在 **"团队名称"** 字段中，输入新 Microsoft Teams 团队的名称。
4. 选择 **"创建 Microsoft 团队**"，然后选择"**关闭"。**

根据分配给内部风险管理角色组的用户数，可能需要 15 分钟才能将所有调查人员和分析师添加到 Microsoft Teams 团队中处理案例。
