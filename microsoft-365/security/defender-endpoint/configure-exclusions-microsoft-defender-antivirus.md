---
title: 设置扫描的Microsoft Defender 防病毒项
description: 你可以排除文件 (包括由指定进程修改的文件) 以及文件夹被Microsoft Defender 防病毒。 使用 PowerShell 验证排除项。
keywords: ''
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ksarens
manager: dansimp
ms.technology: mde
ms.audience: ITPro
ms.topic: how-to
ms.openlocfilehash: a6df318ccf484d750ae8010f34b5c545b115cde0
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/12/2021
ms.locfileid: "59222374"
---
# <a name="configure-and-validate-exclusions-for-microsoft-defender-antivirus-scans"></a>配置并验证扫描Microsoft Defender 防病毒排除项

**适用于：**

- [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)

你可以从扫描中排除某些文件、文件夹、进程和进程打开Microsoft Defender 防病毒文件。 此类排除项适用于 [计划扫描](scheduled-catch-up-scans-microsoft-defender-antivirus.md)、按需 [扫描](run-scan-microsoft-defender-antivirus.md)和 [始终实时保护和监视](configure-real-time-protection-microsoft-defender-antivirus.md)。 进程打开的文件的排除项仅适用于实时保护。

## <a name="configure-and-validate-exclusions"></a>配置和验证排除

若要配置和验证排除项，请参阅以下内容：

- [根据文件名、扩展名和文件夹位置配置并验证排除项](configure-extension-file-exclusions-microsoft-defender-antivirus.md)。 你可以根据文件扩展Microsoft Defender 防病毒文件名或位置，从扫描中排除文件。

- [配置并验证进程打开的文件的排除项](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md)。 你可以从特定进程打开的扫描中排除文件。

## <a name="recommendations-for-defining-exclusions"></a>推荐排除项的定义

> [!IMPORTANT]
> Microsoft Defender 防病毒许多基于已知操作系统行为和典型管理文件（如在企业管理、数据库管理和其他企业方案和情况中使用的那些文件）的自动排除项。
>
> 定义排除项会降低由组织提供的Microsoft Defender 防病毒。 您应始终评估与实施排除项相关的风险，并且只应排除您确信不是恶意的文件。

定义排除项时，请记住以下几点：

- 从技术上说，排除项是一个保护缺陷。 定义排除项时，请考虑所有选项。 其他选项可以非常简单，只需确保排除的位置具有适当的访问控制列表 (ACL 或) 策略以审核模式。

- 定期查看排除项。 在查看过程中重新检查和重新强制执行缓解。

- 理想情况下，为了避免为了主动而定义排除项。 例如，不要仅因为你认为将来可能会出现问题而排除某些内容。 仅将排除项用于特定问题，例如与排除项可以缓解的性能或应用程序兼容性有关的问题。

- 查看并审核对排除项列表的更改。 安全团队应保留有关添加特定排除的原因的上下文，以避免以后混淆。 安全团队应能够提供有关排除原因的特定答案。

## <a name="see-also"></a>另请参阅

- [Microsoft Defender 防病毒排除Windows Server 2016](configure-server-exclusions-microsoft-defender-antivirus.md)
- [定义排除时要避免的常见错误](common-exclusion-mistakes-microsoft-defender-antivirus.md)
