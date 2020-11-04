---
title: 了解 Microsoft 365 终结点数据丢失防护（预览）
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 07/21/2020
audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MET150
description: 'Microsoft 365 终结点数据丢失防护可将对文件活动的监视和针对这些文件的保护措施扩展到终结点。 在 Microsoft 365 合规解决方案中将文件设为可见 '
ms.openlocfilehash: cbf4a53658885102226d2b874180f5cc5f264a91
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2020
ms.locfileid: "48841858"
---
# <a name="learn-about-microsoft-365-endpoint-data-loss-prevention-preview"></a>了解 Microsoft 365 终结点数据丢失防护（预览）

可以使用 Microsoft 365 数据丢失防护 (DLP) 来监视对确定为敏感的项目执行的操作，并帮助防止意外共享这些项目。 有关 DLP 的更多信息，请参阅[数据丢失防护概述](data-loss-prevention-policies.md)。

**终结点数据丢失防护** （终结点 DLP）可将 DLP 的活动监视和保护功能扩展到 Windows 10 设备上的敏感项目。 将设备加入 Microsoft 365 合规性解决方案中后，即可在[活动资源管理器](data-classification-activity-explorer.md)中看到有关用户对敏感项目执行的操作的信息，你可以通过 [DLP 策略](create-test-tune-dlp-policy.md)对这些项目执行保护性操作。

## <a name="endpoint-activities-you-can-monitor-and-take-action-on"></a>可监视并对其执行操作的终结点活动

Microsoft 终结点 DLP 使你可以审核和管理用户对运行 Windows 10 的设备上的敏感项目进行的以下类型的活动。 这包括：


|项目活动 |可审核/可限制  |
|---------|---------|
|已创建    | 可审核      |
|已重命名    |  可审核       |
|已复制到可移动媒体或已在可移动媒体上创建     |     可审核且可限制|
|已复制到网络共享，例如 \\my-server\fileshare   |     可审核且可限制    |
|已打印 |    可审核且可限制       |
|已通过 Microsoft Chromium Edge 复制到云    |   可审核且可限制        |
|由不允许的应用和浏览器访问    |  可审核且可限制       |

## <a name="whats-different-in-endpoint-dlp"></a>终结点 DLP 中的区别

在深入研究终结点 DLP 之前，你需要了解一些其他概念。

### <a name="enabling-device-management"></a>启用设备管理

设备管理是一项功能，可从设备收集遥测并将其纳入 Microsoft 365 合规解决方案，如终结点 DLP 和[内部风险管理](insider-risk-management.md)。 你需要载入所有要用作 DLP 策略中位置的设备。

![启用设备管理](../media/endpoint-dlp-learn-about-1-enable-device-management.png)

载入和载出通过你从设备管理中心下载的脚本来处理。 中心为每种部署方法提供了自定义脚本：

- 本地脚本（最多 10 台机器）
- 组策略
- System Center Configuration Manager（版本 1610 或更高版本）
- 移动设备管理/Microsoft Intune
- 非持久性计算机的 VDI 载入脚本

![设备载入页面](../media/endpoint-dlp-learn-about-3-device-onboarding-page.png)

 使用 [Microsoft 365 终结点 DLP入门](endpoint-dlp-getting-started.md)中的程序载入设备。

如果你通过 [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/) 载入设备，则这些设备将自动显示在设备列表中。

![托管设备列表](../media/endpoint-dlp-learn-about-2-device-list.png)

### <a name="viewing-endpoint-dlp-data"></a>查看终结点 DLP 数据

 终结点 DLP 会监视基于活动的 om MIME 类型，因此，即使文件扩展名已更改也会捕获活动。 在公共预览版中，它会监视所有：

- Word 文件
- PowerPoint 文件
- Excel 文件
- PDF 文件
- .csv 文件
- .tsv 文件
- c 文件
- class 文件
- cpp 文件
- cs 文件
- h 文件
- java 文件

> [!NOTE]
> 默认情况下，不会审核 .txt 和源代码文件，DLP 根据应用的策略对其进行评估，然后相应地审核或阻止用户操作。

设备一旦载入，有关已审核活动的信息就会流入活动资源管理器，即使在配置和部署将设备作为位置的任何 DLP 策略之前也不例外。

![活动资源管理器中的终结点 DLP 事件](../media/endpoint-dlp-learn-about-4-activity-explorer.png)

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

![复制到 USB 活动属性](../media/endpoint-dlp-learn-about-5-activity-attributes.png)

## <a name="next-steps"></a>后续步骤

现在，你已了解有关终结点 DLP 的内容，接下来要学习：

1) [Microsoft 终结点数据丢失防护（预览）入门](endpoint-dlp-getting-started.md)
2) [使用 Microsoft 终结点数据丢失防护（预览）](endpoint-dlp-using.md)

## <a name="see-also"></a>另请参阅

- [Microsoft 终结点数据丢失防护（预览）入门](endpoint-dlp-getting-started.md)
- [使用 Microsoft 终结点数据丢失防护（预览）](endpoint-dlp-using.md)
- [数据丢失防护概述](data-loss-prevention-policies.md)
- [创建、测试和优化 DLP 策略](create-test-tune-dlp-policy.md)
- [活动资源管理器入门](data-classification-activity-explorer.md)
- [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/)
- [内部风险管理](insider-risk-management.md)