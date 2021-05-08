---
title: 设置扫描的Microsoft Defender 防病毒项
description: 你可以排除 (文件，包括由指定进程修改) 的文件以及文件夹被Microsoft Defender 防病毒。 使用 PowerShell 验证排除项。
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
ms.openlocfilehash: 7065aa7cd1975b2f5a38e79da8618ba3efdcdac5
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2021
ms.locfileid: "52275116"
---
# <a name="configure-and-validate-exclusions-for-microsoft-defender-antivirus-scans"></a>配置并验证扫描的Microsoft Defender 防病毒项

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**适用于：**

- [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)

你可以从扫描中排除某些文件、文件夹、进程和进程打开Microsoft Defender 防病毒文件。 此类排除项适用于 [计划扫描](scheduled-catch-up-scans-microsoft-defender-antivirus.md)、按需 [扫描](run-scan-microsoft-defender-antivirus.md)和 [始终实时保护和监视](configure-real-time-protection-microsoft-defender-antivirus.md)。 进程打开的文件的排除项仅适用于实时保护。

## <a name="configure-and-validate-exclusions"></a>配置和验证排除

若要配置和验证排除项，请参阅以下内容：

- [根据文件名、扩展名和文件夹位置配置并验证排除项](configure-extension-file-exclusions-microsoft-defender-antivirus.md)。 可以基于文件扩展Microsoft Defender 防病毒文件扩展名、文件名或位置从扫描中排除文件。

- [配置并验证进程打开的文件的排除项](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md)。 你可以从特定进程打开的扫描中排除文件。

## <a name="recommendations-for-defining-exclusions"></a>推荐排除项的定义

> [!IMPORTANT]
> Microsoft Defender 防病毒许多基于已知操作系统行为和典型管理文件（如在企业管理、数据库管理和其他企业方案和情况中使用的那些文件）的自动排除项。  
> 
> 定义排除项会降低由组织提供的Microsoft Defender 防病毒。 您应始终评估与实施排除项相关的风险，并且只应排除您确信不是恶意的文件。

定义排除项时，请记住以下几点：  

- 从技术上说，排除项是一个保护缺陷。 定义排除项时，始终考虑缓解。 其他缓解措施可能非常简单，只需确保排除的位置具有适当的访问控制列表 (ACL) 、审核策略、由最新的软件等进行处理。

- 定期查看排除项。 在审查过程中重新检查和重新强制执行缓解。

- 理想情况下，避免定义旨在主动的排除项。 例如，不要仅因为你认为将来可能会出现问题而排除某些内容。 仅将排除项用于特定问题，例如与排除项可以缓解的性能或应用程序兼容性有关的问题。

- 审核排除列表更改。 安全管理员应保留有关添加特定排除的原因的足够上下文。 您应该能够提供答案，并说明排除特定路径的原因的特定原因。

## <a name="related-articles"></a>相关文章

- [Microsoft Defender 防病毒排除项Windows Server 2016](configure-server-exclusions-microsoft-defender-antivirus.md)
- [定义排除时要避免的常见错误](common-exclusion-mistakes-microsoft-defender-antivirus.md)
