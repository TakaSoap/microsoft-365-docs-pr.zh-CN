---
title: 配置终结点数据丢失防护设置
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
ms.localizationpriority: high
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MET150
description: 了解如何配置终结点数据丢失防护 (DLP) 中心设置。
ms.openlocfilehash: ebe995512769275999e7ec4837e16542ffce7100
ms.sourcegitcommit: b3530441288b2bc44342e00e9025a49721796903
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/20/2022
ms.locfileid: "63680188"
---
# <a name="configure-endpoint-data-loss-prevention-settings"></a>配置终结点数据丢失防护设置

终结点数据丢失防护 (DLP) 行为的许多方面由集中配置的设置控制。 设置将应用于设备的所有 DLP 策略。

![终结点 DLP 设置](../media/endpoint-dlp-1-using-dlp-settings.png)

如果要控制以下设置，则必须配置这些设置：

- 云出口限制
- 针对每个应用程序用户活动的各种类型限制性操作。
- Windows 和 macOS 设备的文件路径排除。
- 浏览器和域限制。
- 替代策略的业务理由在策略提示中的显示方式。
- 如果自动审核 Office、PDF 和 CSV 文件上的活动。

## <a name="dlp-settings"></a>DLP 设置

在开始使用之前，应设置 DLP 设置。 

### <a name="endpoint-dlp-windows-1011-and-macos-settings"></a>终结点 DLP Windows 10/11 和 macOS 设置

|Setting |Windows 10，1809 及更高版本，Windows 11  |macOS Catalina 10.15 或更高版本（预览）  |Notes  |
|---------|---------|---------|---------|
|文件路径排除     |支持         |支持         |macOS 包括默认启用的推荐排除项列表          |
|受限应用     |支持         |支持         |         |
|受限应用组 |支持 |不支持
|不允许的蓝牙应用    |支持         |不支持         |         |
|敏感项目的浏览器和域限制      |支持         |支持         |         |
|终结点 DLP 的其他设置     |支持         |支持         |macOS 设备仅支持默认业务理由         |
|始终审核已载入设备的文件活动     |支持         |支持         |         |
|来自不允许的应用的自动隔离文件 | 支持 | 不支持| |
|高级分类 | 支持 | 不支持| |
|策略提示中的业务理由 | 支持 | 支持| |

### <a name="advanced-classification-scanning-and-protection"></a>高级分类扫描和保护

高级分类扫描和保护允许更高级的 Microsoft 365 基于云的数据分类服务，可扫描项目、对其进行分类，以及将结果返回到本地计算机。 这意味着你可以利用分类技术，如 [精确数据匹配](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md) 分类、[命名实体（预览）](named-entities-learn.md#learn-about-named-entities-preview) 和 DLP 策略中的 [可训练分类器](classifier-learn-about.md#learn-about-trainable-classifiers)。

如果启用高级分类，则将内容从本地设备发送到云服务来进行扫描和分类。 如果需要考虑带宽利用率，则可以设置连续 24 小时内可使用量的限制。 该限制在终结点 DLP 设置中配置，并按设备应用。 如果设置了带宽利用率限制并且超过了该限制，则 DLP 将停止将用户内容发送到云。 此时，数据分类将在设备上本地继续进行，但不能使用精确数据匹配、命名实体（预览版）和可训练分类器进行分类。 当累积带宽利用率降至低于连续 24 小时限制时，将恢复与云服务的通信。

如果带宽利用率不是问题，请选择 **无限制** 以允许无限制的带宽利用率。

这些 Windows 版本支持高级分类扫描和保护：

- Windows 10 版本 20H1/20H2/21H1 (KB 5006738) 
- Windows 10 版本 19H1/19H2 (KB 5007189) 
- Windows 10 RS5 (KB 5006744) 

> [!NOTE]
> Office（Word、Excel、PowerPoint）和 PDF 文件类型支持高级分类。

> [!NOTE]
> DLP 策略评估始终发生在云中，即使未发送用户内容。

### <a name="file-path-exclusions"></a>文件路径排除

打开“[合规中心](https://compliance.microsoft.com)” > “**数据丢失保护**” > “**终节点 DLP 设置**” > “**文件路径排除**”。

你可能希望从设备上的 DLP 监视、DLP 警报和 DLP 策略强制执行中排除某些路径，因为它们太杂乱或不包含你感兴趣的文件。 系统将不会审核这些位置中的文件，并且在这些位置创建或修改的任何文件都将不受 DLP 策略强制执行的约束。 可在 DLP 设置中配置路径排除项。

#### <a name="windows-10-devices"></a>Windows 10 设备

可以使用此逻辑来构造适用于Windows 10 设备的排除路径：

- 以 `\` 结尾的有效文件路径，仅表示直接位于文件夹下的文件。 <br/>例如：`C:\Temp\`

- 以 `\*` 结尾的有效文件路径，仅表示位于子文件夹下的文件，以及直接位于文件夹下方的文件。 <br/>例如：`C:\Temp\*`

- 以 `\` 或 `\*` 结尾的有效文件路径，表示直接位于文件夹和所有子文件夹下的所有文件。 <br/>例如：`C:\Temp`

- 两端的 `\` 之间带有通配符的路径。 <br/>例如：`C:\Users\*\Desktop\`

- 两端 `\` 之间带有通配符，并通过 `(number)` 给出确切的子文件夹数量的路径。 <br/>例如：`C:\Users\*(1)\Downloads\`

- 带有 SYSTEM 环境变量的路径。 <br/>例如：`%SystemDrive%\Test\*`

- 综合了上述所有情况。 <br/>例如：`%SystemDrive%\Users\*\Documents\*(2)\Sub\`

#### <a name="macos-devices-preview"></a>macOS 设备（预览）

与 Windows 10 相似，你可以为 macOS 设备添加自己的排除项。

- 文件路径定义不区分大小写，因此 `User` 与 `user` 相同。

- 支持通配符值。因此，路径定义可以在路径中间或路径末尾包含 `*`。例如：`/Users/*/Library/Application Support/Microsoft/Teams/*`

#####  <a name="recommended-file-path-exclusions-preview"></a>建议的文件路径排除（预览）

出于性能原因，端点 DLP 包括适用于 macOS 设备的推荐文件路径排除列表。 默认情况下，这些排除已启用。 如果需要，可以通过切换“**包括适用于 Mac 的推荐文件路径排除**”开关禁用它们。 该列表包括：

- /Applications/*
- /System/*
- /usr/*
- /Library/*
- /private/*
- /opt/*
- /Users/*/Library/Application Support/Microsoft/Teams/*

### <a name="restricted-apps-and-app-groups"></a>受限应用和应用组

#### <a name="restricted-apps"></a>受限应用

**受限应用**（以前称为 **不允许的应用**）是你创建的应用程序列表。 配置当用户使用列表中的应用 **_访问_** 设备上受 DLP 保护的文件时，DLP 将执行哪些操作。 它适用于 Windows 10 和 macOS 设备（预览）。

当在策略中选择“**由受限制应用访问**”，并且用户使用受限应用列表上的应用访问受保护文件时，将对活动进行 `audited`、`blocked` 或 `blocked with override`，具体取决于配置方式。 也就是说，除非同一应用属于 **受限制应用组**，否则为 **受限制应用组** 中的活动配置的操作将替代为 **受限制应用** 列表的访问活动配置的操作。 所有活动均经过审核，可在活动资源管理器中查看。

> [!IMPORTANT]
> 不包括可执行文件的路径，而仅包括可执行文件的名称（如 browser.exe）。

> [!IMPORTANT]
> 针对受限应用列表上的应用定义的操作（`audit`、`block with override` 或 `block`）仅当用户尝试 ***访问*** 受保护项目时适用。 

#### <a name="file-activities-for-apps-in-restricted-app-groups-preview"></a>受限应用组中应用的文件活动（预览）

受限应用组是在 DLP 设置中创建，然后添加到策略中的规则的应用集合。 将受限应用组添加到策略时，可以执行此表中定义的操作。

|受限应用组选项  |允许你执行的操作  |
|---------|---------|
|不限制文件活动     |告知 DLP 允许用户使用应用组中的应用访问受 DLP 保护的项目，并在用户尝试 **Copy 到剪贴板**、**复制到 USB 可移动驱动器**、**复制到网络驱动器**，以及从应用中 **打印** 时不执行任何操作。          |
|对所有活动应用限制     |当用户尝试使用此应用组中的应用访问受 DLP 保护的项目时，告知 DLP 执行 `Audit only`、`Block with override` 或 `Block`         |
|对特定活动应用限制     |通过此设置，用户可以使用应用组中的应用访问受 DLP 保护的项目，并且可以选择当用户尝试 **复制到剪贴板**、**复制到 USB 可移动驱动器**、**复制到网络驱动器** 和 **打印** 时 DLP 要执行的默认操作（`Audit only`、`Block` 或 `Block with override`）。          |

> [!IMPORTANT]
> 受限应用组中的设置将替代受限应用列表中设置的任何限制（当二者处于同一规则中时）。 因此，如果某个应用位于受限应用列表中，并且是受限应用组的成员，则将应用受限应用组的设置。

#### <a name="how-dlp-applies-restrictions-to-activities"></a>DLP 如何对活动应用限制

**受限应用组中应用的文件活动（预览）**、**所有应用的稳健活动** 和 **受限应用活动** 列表的范围为同一规则。

##### <a name="restricted-app-groups-overrides"></a>受限应用组替代

在 **受限应用组中应用的文件活动** 中定义的配置将替代 **受限应用活动** 列表和同一规则中 **所有应用的文件活动** 中的配置。

##### <a name="restricted-app-activities-and-file-activities-for-all-apps"></a>所有应用的受限应用活动和文件活动

如果为 **受限应用活动** 定义的操作在同一规则中为 `Audit only` 或 `Block with override`，则 **受限应用活动** 和 **所有应用的文件活动** 将协同工作。 这是因为针对 **受限应用活动** 定义的操作仅当用户使用列表中的应用访问文件时才适用。 用户获得访问权限后，则为 **所有应用的文件活动** 中的活动定义的操作适用。 

下面是一个示例：

如果将 Notepad.exe 添加到 **受限应用**，将 **所有应用的文件活动** 配置为 **对特定活动应用限制**，并且两者配置如下所示：

|策略中的设置  |应用名称  |用户活动  |要执行的 DLP 操作  |
|---------|---------|---------|---------|
|受限应用活动     |记事本        |访问受 DLP 保护的项目         |仅审核         |
|所有应用的文件活动   |所有应用        | 复制到剪贴板        |仅审核         |
|所有应用的文件活动     |所有应用         |复制到 USB 可移动设备 | 阻止       |
|所有应用的文件活动     |所有应用         |复制到网络共享         |仅审核         |
|所有应用的文件活动   |所有应用         |打印         |阻止         |
|所有应用的文件活动     |所有应用         |使用未经允许的蓝牙应用复制或移动         |Blocked         |
|所有应用的文件活动     |所有应用         |远程桌面服务         |通过替代阻止         |

用户 A 使用记事本打开受 DLP 保护的文件。 DLP 允许访问和审核活动。 当用户 A 仍在记事本中时，会尝试从受保护项复制到剪贴板，此设置会起作用，并且 DLP 将审核活动。 然后，用户 A 尝试从记事本打印受保护项，但该活动受到阻止。

> [!NOTE]
> 如果将 **受限应用访问** 中要执行的 DLP 操作设置为 `block`，则将阻止所有访问，并且用户无法对文件执行任何活动。
   
##### <a name="file-activities-for-all-apps-only"></a>仅所有应用的文件活动

如果应用不在 **受限应用组中应用的文件活动（预览）**，或不在 **受限应用活动** 列表中，或位于包含操作 `Audit only` 的 **受限应用活动** 列表中，则 **所有应用的文件活动** 中定义的任何限制将应用于同一规则中。  

#### <a name="macos-devices-preview"></a>macOS 设备（预览）

就像在 Windows 设备上一样，你现在能够通过在 **受限应用活动** 列表中定义它们来阻止 macOS 应用访问敏感数据。 

> [!NOTE]
> 请注意，必须通过与在其上面运行的操作系统对应的唯一路径进入跨平台应用程序。

若要查找 Mac 应用程序的完整路径：

1. 在 macOS 设备上，打开“**活动监视器**”。 查找并双击要限制的进程

2. 选择“**打开文件和端口**”选项卡。
  
3. 对于 macOS 应用，需要完整的路径名称，包括应用的名称。

#### <a name="protect-sensitive-data-from-cloud-synchronization-apps"></a>保护敏感数据免受云同步应用的保护

若要防止云同步应用（如 *onedrive.exe*）将敏感项目同步到云，请将云同步应用添加到 **不允许的应用** 列表。 当不允许的云同步应用尝试访问受阻止的 DLP 策略保护的项时，DLP 可能会生成重复的通知。 可以通过在 **不允许的应用** 下启用 **自动隔离** 选项来避免这些重复通知。  

##### <a name="auto-quarantine-preview"></a>自动隔离（预览版）

> [!NOTE]
> 自动隔离仅在 Windows 10 上受支持

启用后，当不允许的应用尝试访问受 DLP 保护的敏感项目时，自动隔离将启动。 自动隔离会将敏感项目移动到管理员配置的文件夹，并且可以将占位符 **.txt** 文件保留在原始文件的位置。 可以将占位符文件中的文本配置为告知用户项目移动到的位置以及其他相关信息。  

可以使用自动隔离来防止用户和管理员出现无休止的 DLP 通知链—请参阅 [方案 4: 使用自动隔离 (预览版) 避免从云同步应用的 DLP 通知循环](endpoint-dlp-using.md#scenario-4-avoid-looping-dlp-notifications-from-cloud-synchronization-apps-with-auto-quarantine-preview)。

### <a name="unallowed-bluetooth-apps"></a>不允许的蓝牙应用

阻止用户通过特定蓝牙应用传输受你的策略保护的文件。

### <a name="browser-and-domain-restrictions-to-sensitive-data"></a>敏感数据的浏览器和域限制

限制与策略匹配的敏感文件与不受限制的云服务域共享。

#### <a name="unallowed-browsers"></a>不允许的浏览器

对于 Windows 设备，如果添加由可执行名称标识的浏览器，浏览器将受到阻止，无法访问与强制实施的 DLP 策略（其中上传到云服务限制设为“阻止”或“阻止替代”）条件匹配的文件。 当阻止这些浏览器访问文件时，最终用户将看到一则 toast 通知，要求他们通过 Microsoft Edge 打开文件。

对于 macOS 设备，必须添加完整的文件路径。 若要查找 Mac 应用程序的完整路径：

1. 在 macOS 设备上，打开“**活动监视器**”。 查找并双击要限制的进程

2. 选择“**打开文件和端口**”选项卡。
  
3. 对于 macOS 应用，需要完整的路径名称，包括应用的名称。

#### <a name="service-domains"></a>服务域

> [!NOTE]
> **服务域** 设置仅适用于使用安装了 [ Microsoft 合规性扩展](dlp-chrome-learn-about.md#learn-about-the-microsoft-compliance-extension) 的 Microsoft Edge 或 Google Chrome 上传的文件。

你可以控制受你的策略保护的敏感文件是否可以从 Microsoft Edge 上传到特定服务域。

如果列表模式设置为“**阻止**”，用户将无法向这些域上传敏感项目。 如果由于某项目符合 DLP 策略而阻止了上载操作，则 DLP 会生成警告或阻止敏感项目的上载。

如果列表模式设置为“**允许**”，则用户将 **_只能_** 将敏感项目上传到这些域，并且不允许对所有其他域的上传访问。

> [!IMPORTANT]
> 服务限制模式设置为“允许”时，在强制执行限制之前，必须至少配置一个服务域。

使用服务域的 FQDN 格式，而不带结尾的 `.` 

例如：

 `www.contoso.com` 

不支持通配符。

### <a name="additional-settings-for-endpoint-dlp"></a>终结点 DLP 的其他设置

#### <a name="business-justification-in-policy-tips"></a>策略提示中的业务理由

可在 DLP 策略提示通知中控制用户与业务理由选项的交互方式。 当用户执行受 DLP 策略中 **以超越阻止** 设置所保护的活动时，将出现此选项。 这是全局设置。 可从下列选项中进行选择：

- **显示默认选项和自定义文本框**：默认情况下，用户可以选择内置理由，也可以输入自己的文本。
- **仅显示默认选项**：用户只能选择内置理由。
- **仅显示自定义文本框**：用户只能输入自己的理由。 最终用户策略提示通知中只显示文本框。 

##### <a name="customizing-the-options-in-the-drop-down-menu"></a>自定义下拉菜单中的选项

通过选择"**自定义选项下拉菜单**"，可以创建多达五个将在用户与策略通知提示交互时显示的自定义选项。 


|选项 |默认文本  |
|---------|---------|
|选项 1    | **这是已建立的业务工作流的一部分**，或者可以输入自定义文本        |
|选项 2  |**我的经理已批准此操作**，或者可以输入自定义文本         |
|选项 3   |**需要紧急访问;我将单独通知我的经理**，或者可以输入自定义文本          |
|显示误报选项     |**这些文件中的信息不敏感**，或者可以输入自定义文本          |
|选项 5    |**其他**，或者可以输入自定义文本         |

### <a name="always-audit-file-activity-for-devices"></a>始终审核已载入设备的文件活动

默认情况下，当设备载入后，将自动审核 Office、PDF 和 CSV 文件的活动，并可在活动资源管理器中审阅。 如果希望仅在活动策略中包含载入设备时审核此活动，请关闭此功能。

将始终对已载入设备的文件活动进行审核，无论其是否包括在活动策略中。

## <a name="see-also"></a>另请参阅

- [了解终结点数据丢失防护](endpoint-dlp-learn-about.md)
- [终结点数据丢失防护入门](endpoint-dlp-getting-started.md)
- [了解数据丢失防护](dlp-learn-about-dlp.md)
- [创建、测试和优化 DLP 策略](create-test-tune-dlp-policy.md)
- [活动资源管理器入门](data-classification-activity-explorer.md)
- [Microsoft Defender for Endpoint](/windows/security/threat-protection/)
- [将 Windows 10 和 Windows 11 设备载入到 Microsoft 365 概述](/microsoft-365/compliance/device-onboarding-overview)
- [Microsoft 365 订阅](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)
- [已加入 Azure Active Directory (AAD)](/azure/active-directory/devices/concept-azure-ad-join)
- [下载基于 Chromium 的新 Microsoft Edge](https://support.microsoft.com/help/4501095/download-the-new-microsoft-edge-based-on-chromium)
- [开始使用默认 DLP 策略](get-started-with-the-default-dlp-policy.md)
- [从模板创建 DLP 策略](create-a-dlp-policy-from-a-template.md)
