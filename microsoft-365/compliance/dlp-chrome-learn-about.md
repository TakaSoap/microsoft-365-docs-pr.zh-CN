---
title: 了解 Microsoft 合规性扩展
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
description: Microsoft 合规性扩展可扩展对 Google Chrome 浏览器文件活动和保护操作的监视和控制
ms.openlocfilehash: ff0df602e68338315becabd0c5b65f981fe4dd43
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60179183"
---
# <a name="learn-about-the-microsoft-compliance-extension"></a>了解 Microsoft 合规性扩展

[终结点数据丢失防护（终结点 DLP）](endpoint-dlp-learn-about.md) 将[Microsoft 365 数据丢失防护 (DLP)](dlp-learn-about-dlp.md) 的活动监视和保护功能扩展到 Windows 10 设备上的敏感项目。 将设备加入 Microsoft 365 合规性解决方案中后，即可在[活动资源管理器](data-classification-activity-explorer.md)中看到有关用户对敏感项目执行的操作的信息，你可以通过 [DLP 策略](create-test-tune-dlp-policy.md)对这些项目执行保护性操作。

在 Windows 10 设备上安装 Microsoft 合规性扩展后，组织可以在用户尝试使用 Google Chrome 访问或将敏感项目上传到云服务时进行监视，并可通过 DLP 执行保护操作。  

## <a name="activities-you-can-monitor-and-take-action-on"></a>可以监视并对其执行操作的活动

Microsoft 终结点 DLP 使你可以审核和管理用户对运行 Windows 10 设备上的敏感项目进行的以下类型活动。

活动 |说明  | 受支持的策略操作|
|---------|---------|---------|
|文件复制到云  | 用户尝试通过 Chrome 浏览器将敏感项目上传到受限服务域时进行检测 |审核、阻止|
|文件打印  |用户尝试将 Chrome 浏览器中打开的敏感项目打印到本地或网络打印机时进行检测 |审核、通过覆盖阻止、阻止|
|文件复制到剪贴板 |用户尝试从在 Chrome 浏览器中查看的敏感项目中复制信息，然后将其粘贴到另一应用、进程或项目时进行检测。 |审核、通过覆盖阻止、阻止|
|文件复制到可移动存储器    | 用户尝试将敏感项目或信息从在 Chrome 浏览器中打开的敏感项目复制到可移动媒体或 USB 设备时进行检测 |审核、通过覆盖阻止、阻止|
|文件复制到网络共享  |用户尝试将敏感项目或信息从 Chrome 浏览器中打开的敏感项目复制到网络共享或映射的网络驱动器时进行检测。|审核、通过覆盖阻止、阻止 |

## <a name="deployment-process"></a>部署过程
1. [终结点数据丢失防护入门](endpoint-dlp-getting-started.md)
2. [Windows 10 设备的装载工具和方法](dlp-configure-endpoints.md)
3. [在 Windows 10 设备上安装扩展](dlp-chrome-get-started.md)
4. [创建或编辑 DLP 策略](create-test-tune-dlp-policy.md)，这些策略限制上传到云服务，或者通过不允许的浏览器操作访问云服务，并将其应用到 Windows 10 设备

## <a name="next-steps"></a>后续步骤

请参阅 [Microsoft 合规性扩展入门](dlp-chrome-get-started.md)，了解完整的部署过程和方案。

## <a name="see-also"></a>另请参阅

- [Microsoft 合规性扩展入门](dlp-chrome-get-started.md)
- [了解 Microsoft 365 终结点数据丢失防护](endpoint-dlp-learn-about.md)
- [Microsoft 终结点数据丢失防护入门](endpoint-dlp-getting-started.md)
- [使用 Microsoft 终结点数据丢失防护](endpoint-dlp-using.md)
- [了解数据丢失防护](dlp-learn-about-dlp.md)
- [创建、测试和优化 DLP 策略](create-test-tune-dlp-policy.md)
- [活动资源管理器入门](data-classification-activity-explorer.md)
- [Microsoft Defender for Endpoint](/windows/security/threat-protection/)
- [内部风险管理](insider-risk-management.md)
