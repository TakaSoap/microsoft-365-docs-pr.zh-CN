---
title: 为Microsoft Defender 防病毒扫描设置排除项
description: 可以排除文件 (包括由指定进程修改的文件，) 和文件夹不被Microsoft Defender 防病毒扫描。 使用 PowerShell 验证排除项。
keywords: ''
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ksarens
manager: dansimp
ms.technology: mde
ms.audience: ITPro
ms.topic: how-to
ms.collection: m365-security-compliance
ms.openlocfilehash: c9796f4e5154fd46d1479f0cbfa25f2afaf4e9bb
ms.sourcegitcommit: 4f56b4b034267b28c7dd165e78ecfb4b5390087d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/12/2022
ms.locfileid: "64787503"
---
# <a name="configure-and-validate-exclusions-for-microsoft-defender-antivirus-scans"></a>配置和验证Microsoft Defender 防病毒扫描的排除项

**适用于：**
- [Microsoft Defender for Endpoint 计划 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- Microsoft Defender 防病毒

**平台**
- Windows

可以从Microsoft Defender 防病毒扫描中排除某些文件、文件夹、进程和进程打开的文件。 此类排除项适用于 [计划的扫描](scheduled-catch-up-scans-microsoft-defender-antivirus.md)、 [按需扫描](run-scan-microsoft-defender-antivirus.md)以及 [始终实时保护和监视](configure-real-time-protection-microsoft-defender-antivirus.md)。 进程打开的文件的排除项仅适用于实时保护。

## <a name="configure-and-validate-exclusions"></a>配置和验证排除

若要配置和验证排除项，请参阅以下内容：

- [根据文件名、扩展名和文件夹位置配置和验证排除](configure-extension-file-exclusions-microsoft-defender-antivirus.md)项。 可以根据文件扩展名、文件名或位置从Microsoft Defender 防病毒扫描中排除文件。

- [配置和验证进程打开的文件的排除项](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md)。 可以从特定进程打开的扫描中排除文件。

## <a name="recommendations-for-defining-exclusions"></a>定义排除项的推荐

> [!IMPORTANT]
> Microsoft Defender 防病毒包括许多基于已知操作系统行为和典型管理文件（例如用于企业管理、数据库管理和其他企业方案和情况）的自动排除项。
>
> 定义排除项会降低Microsoft Defender 防病毒提供的保护。 应始终评估与实现排除项相关联的风险，并且应仅排除你确信不是恶意的文件。

定义排除项时，请记住以下几点：

- 从技术上讲，排除是保护差距。 定义排除项时，请考虑所有选项。 其他选项可以非常简单，例如确保排除的位置具有适当的访问控制列表 (ACL) 或设置策略以审核模式。

- 定期查看排除项。 作为评审过程的一部分，重新检查并重新强制实施缓解措施。

- 理想情况下，请避免在主动时定义排除项。 例如，不要仅仅因为认为将来可能会有问题而排除某些内容。 仅对特定问题（例如与性能或应用程序兼容性相关的问题）使用排除项，排除可以缓解。

- 查看和审核对排除项列表的更改。 安全团队应保留有关添加特定排除项的原因的上下文，以避免以后出现混淆。 安全团队应该能够提供有关存在排除项的原因的特定解答。

> [!TIP]
> 如果要查找其他平台的防病毒相关信息，请参阅：
> - [在 macOS 上设置Microsoft Defender for Endpoint首选项](mac-preferences.md)
> - [Mac 上的 Microsoft Defender for Endpoint](microsoft-defender-endpoint-mac.md)
> - [适用于Intune的Microsoft Defender 防病毒的 macOS 防病毒策略设置](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [在 Linux 上设置Microsoft Defender for Endpoint首选项](linux-preferences.md)
> - [Microsoft Defender for Endpoint on Linux](microsoft-defender-endpoint-linux.md)
> - [在 Android 功能上配置 Defender for Endpoint](android-configure.md)
> - [在 iOS 功能上配置Microsoft Defender for Endpoint](ios-configure-features.md)

## <a name="see-also"></a>另请参阅

- [Microsoft Defender 防病毒Windows Server 2016上的排除项](configure-server-exclusions-microsoft-defender-antivirus.md)
- [定义排除时要避免的常见错误](common-exclusion-mistakes-microsoft-defender-antivirus.md)
