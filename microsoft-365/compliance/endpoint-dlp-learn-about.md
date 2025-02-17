---
title: 了解 Microsoft 365 终结点数据丢失防护
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
ms.localizationpriority: high
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MET150
description: 'Microsoft 365 终结点数据丢失防护可将对文件活动的监视和针对这些文件的保护措施扩展到终结点。文件在合规性解决方案中可见 '
ms.openlocfilehash: f32e84434258ff4b4c5ea6af24f69c607952b56a
ms.sourcegitcommit: 1c5f9d17a8b095cd88b23f4874539adc3ae021de
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2022
ms.locfileid: "64714540"
---
# <a name="learn-about-microsoft-365-endpoint-data-loss-prevention"></a>了解 Microsoft 365 终结点数据丢失防护

可使用 Microsoft 365 数据丢失防护 (DLP) 监视对已确定为敏感的项目执行的操作，并帮助防止无意间共享这些项目。有关 DLP 的详细信息，请参阅[了解数据丢失防护](dlp-learn-about-dlp.md)。

**终结点数据丢失防护** （终结点 DLP）将 DLP 的活动监视和保护功能扩展到物理存储在 Windows 10、Windows 11 和 macOS（Catalina 10.15 及更高版本）设备上的敏感项目。 将设备加入 Microsoft 365 合规性解决方案中后，即可在[活动资源管理器](data-classification-activity-explorer.md)中看到有关用户对敏感项目执行的操作的信息，你可以通过 [DLP 策略](create-test-tune-dlp-policy.md)对这些项目执行保护性操作。

> [!TIP]
> 如果正在查找可移动存储的设备控制，请查看 [Microsoft Defender for Endpoint 设备控制可移动存储访问控制](../security/defender-endpoint/device-control-removable-storage-access-control.md#microsoft-defender-for-endpoint-device-control-removable-storage-access-control)。

> [!NOTE]
> 在 Microsoft 365 合规性中，敏感项的 DLP 策略评估会集中进行，因此将策略和策略更新分发到单个设备时不会有时间延迟。 在合规中心更新策略时，通常需要大约一小时才能跨服务同步这些更新。 同步策略更新后，目标设备上的项在下次访问或修改时会自动重新评估。

## <a name="endpoint-activities-you-can-monitor-and-take-action-on"></a>可监视并对其执行操作的终结点活动

Microsoft 终结点 DLP 使你能够审核和管理以下类型的活动，这些活动用户对物理存储在Windows 10、Windows 11 或 macOS 设备上的敏感项目进行审核和管理。

|活动 |说明  |Windows 10 1809 及更高版本/Windows 11| macOS Catalina 10.15 (预览版)  | 可审核/可限制|
|---------|---------|---------|---------|---------|
|上传到云端服务，或通过不允许的浏览器访问    | 当用户试图将项目上传到受限服务域或通过浏览器访问项目时进行检测。  如果他们使用的浏览器在 DLP 中列为不允许的浏览器，则上传活动将被阻止，并且用户将重新定向到使用 Microsoft Edge。 Microsoft Edge 随后将基于 DLP 策略配置允许或阻止上传或访问         |支持 | 支持|可审核且可限制|
|复制至其他应用    |当用户试图从受保护项目中复制信息，然后将其粘贴到另一个应用程序、进程或项目中时进行检测。 该活动无法检测到在同一应用程序、进程或项目中复制和粘贴信息。|支持|支持         | 可审核且可限制|
|复制到 USB 可移动媒体 |检测用户何时尝试将项目或信息复制到可移动媒体或 USB 设备。|支持|支持         | 可审核且可限制|
|拷贝到网络共享    |当用户试图将项目复制到网络共享或映射的网络驱动器时，检测该项目 |支持|支持         |可审核且可限制|
|打印文档    |当用户试图将受保护的项目打印到本地或网络打印机上时，检测该项目。|支持|支持|可审核且可限制         |
|复制到远程会话|检测用户是否尝试将项目复制到远程桌面会话 |支持|不支持|  可审核且可限制|
|复制到蓝牙设备|检测用户尝试将项目复制到未启用的蓝牙应用（如在终结点 DLP 设置中不允许的蓝牙 aps 列表中所定义）。|支持|不支持| 可审核且可限制|
|创建项|当用户创建项目时，检测该项目|支持 | |可审核|
|重命名项|当用户重命名一个项目时，检测该项目|支持 | |可审核|

## <a name="best-practice-for-endpoint-dlp-policies"></a>终结点 DLP 策略的最佳做法

假设你想要阻止包含信用卡号的所有项目离开财务部门用户的终结点。 我们建议：

- 创建策略并将其范围限定到终结点和该用户组。
- 在策略中创建一个规则，用于检测要保护的信息类型。 在这种情况下，**内容包含** 设置为*敏感信息类型**，然后选择 **信用卡**。
- 将每个活动的操作设置为 **阻止**。

有关设计 DLP 策略的更多指导，请参阅[制定数据丢失防护策略](dlp-policy-design.md)。

## <a name="monitored-files"></a>受监视的文件

终结点 DLP 支持监视这些文件类型。 DLP 审核这些文件类型的活动，即使没有策略匹配。 

- Word 文件
- PowerPoint 文件
- Excel 文件
- PDF 文件
- .csv 文件
- .tsv 文件
- .txt 文件
- .rtf 文件
- .c 文件
- .class 文件
- .cpp 文件
- .cs 文件
- .h 文件
- .java 文件
 
如果只想从策略匹配项中监视数据，你可以关闭终结点 DLP 全局设置中的 **始终为设备审核文件活动**。

> [!NOTE]
> 如果 **始终审核设备的审核文件活动** 设置处于打开状态，则即使设备不是任何策略的目标，也始终审核任何 Word、PowerPoint、Excel、PDF 和 .csv 文件上的活动。

> [!TIP]
> 若要确保审核所有受支持的文件类型的活动，请创建[自定义 DLP 策略](create-test-tune-dlp-policy.md)。

终结点 DLP 会监视基于活动的 MIME 类型，因此即使文件扩展名已更改也会捕获活动。

### <a name="file-types-preview"></a>文件类型（预览版）

文件类型是一组文件格式，用于保护特定的工作流或业务区域。 可以在 DLP 策略中将一个或多个文件类型用作条件。

|文件类型 |应用  |受监视的文件扩展名  |
|---------|---------|---------|
|文字处理 |Word、PDF | .doc、.docx、.docm、.dot、.dotx、.dotm、.docb、.pdf |
|电子表格    |Excel、CSV、TSV |.xls、.xlsx、.xlt、.xlm、.xlsm、.xltx、.xltm、.xlsb、.xlw、.csv、.tsv         |
|演示文稿 |PowerPoint|.ppt、.pptx、.pos、.pps、.pptm、.potx、.potm、.ppam、.ppsx|
|archive  |文件存档和压缩工具 | .zip、.zipx、.rar、.7z、.tar、.gz        |
|电子邮件    |Outlook |.pst、.ost、.msg         |

### <a name="file-extensions-preview"></a>文件扩展名（预览版）

如果文件类型不包括作为策略中的条件列出所需的文件扩展名，可以改为使用以逗号分隔的文件扩展名。

> [!IMPORTANT]
> 文件扩展名和文件类型选项不能用作同一规则中的条件。 如果要将它们用作同一策略中的条件，它们必须采用单独的规则。 

> [!IMPORTANT]
> 这些 Windows 版本支持文件类型和文件扩展功能：
>- Windows 10 版本 20H1/20H2/21H1 (KB 5006738) 
>- Windows 10 版本 19H1/19H2 (KB 5007189) 
>- Windows 10 RS5 (KB 5006744) 


## <a name="whats-different-in-endpoint-dlp"></a>终结点 DLP 中的区别

在深入研究终结点 DLP 之前，你需要了解一些其他概念。

### <a name="enabling-device-management"></a>启用设备管理

设备管理是一项功能，可从设备收集遥测并将其纳入 Microsoft 365 合规解决方案，如终结点 DLP 和[内部风险管理](insider-risk-management.md)。 你需要载入所有要用作 DLP 策略中位置的设备。

> [!div class="mx-imgBorder"]
> ![启用设备管理。](../media/endpoint-dlp-learn-about-1-enable-device-management.png)

载入和载出通过你从设备管理中心下载的脚本来处理。 中心为每种部署方法提供了自定义脚本：

- 本地脚本（最多 10 台机器）
- 组策略
- System Center Configuration Manager（版本 1610 或更高版本）
- 移动设备管理/Microsoft Intune
- 非持久性计算机的 VDI 载入脚本

> [!div class="mx-imgBorder"]
> ![设备加入页面。](../media/endpoint-dlp-learn-about-3-device-onboarding-page.png)

 使用 [Microsoft 365 终结点 DLP入门](endpoint-dlp-getting-started.md)中的程序载入设备。

如果你已通过 [Microsoft Defender for Endpoint](/windows/security/threat-protection/) 加入设备，则这些设备将自动显示在设备列表中。 你可以 **打开设备监控** 以使用终结点 DLP。

> [!div class="mx-imgBorder"]
> ![托管设备列表](../media/endpoint-dlp-learn-about-2-device-list.png)。

### <a name="viewing-endpoint-dlp-data"></a>查看终结点 DLP 数据

可通过进入 [DLP 警报管理仪表板](dlp-configure-view-alerts-policies.md)查看与在端点设备上强制实施的 DLP 策略有关的警报。

> [!div class="mx-imgBorder"]
> ![警报信息](../media/Alert-info-1.png)。

你还可以在同一仪表板中查看关联事件的详细信息以及丰富元数据

> [!div class="mx-imgBorder"]
> ![事件信息](../media/Event-info-1.png)。

设备一旦载入，有关已审核活动的信息就会流入活动资源管理器，即使在配置和部署将设备作为位置的任何 DLP 策略之前也不例外。

> [!div class="mx-imgBorder"]
> ![活动资源管理器中的终结点 DLP 事件](../media/endpoint-dlp-learn-about-4-activity-explorer.png)。

终结点 DLP 会收集有关已审核活动的大量信息。

例如，如果将文件复制到可移动 USB 媒体，你将在活动详细信息中看到以下属性：

- 活动类型
- 客户端 IP
- 目标文件路径
- 发生时间戳
- 文件名
- 用户
- 文件扩展名
- 文件大小
- 敏感信息类型定义（如适用）
- sha1 值
- sha256 值
- 以前的文件名
- 位置
- 父级
- filepath
- 源位置类型
- 平台
- 设备名称
- 目标位置类型
- 执行了副本的应用程序
- Microsoft Defender for Endpoint 设备 ID （如适用）
- 可移动媒体设备制造商
- 可移动媒体设备模型
- 可移动媒体设备序列号

> [!div class="mx-imgBorder"]
> ![复制到 USB 活动属性](../media/endpoint-dlp-learn-about-5-activity-attributes.png)。

## <a name="next-steps"></a>后续步骤

现在，你已了解有关终结点 DLP 的内容，接下来要学习：

1. [将 Windows 10 或 Windows 11 设备载入 Microsoft 365 概述](device-onboarding-overview.md)
1. [将 macOS 设备载入 Microsoft 365 概述（预览版）](device-onboarding-macos-overview.md)
1. [配置终结点数据丢失防护设置](dlp-configure-endpoint-settings.md)
1. [使用 Microsoft 终结点数据丢失防护](endpoint-dlp-using.md)

## <a name="see-also"></a>另请参阅

- [Microsoft 终结点数据丢失防护入门](endpoint-dlp-getting-started.md)
- [使用 Microsoft 终结点数据丢失防护](endpoint-dlp-using.md)
- [了解数据丢失防护](dlp-learn-about-dlp.md)
- [创建、测试和优化 DLP 策略](create-test-tune-dlp-policy.md)
- [活动资源管理器入门](data-classification-activity-explorer.md)
- [Microsoft Defender for Endpoint](/windows/security/threat-protection/)
- [内部风险管理](insider-risk-management.md)
