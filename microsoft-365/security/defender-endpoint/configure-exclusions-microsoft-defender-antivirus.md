---
title: 设置 Microsoft Defender 防病毒扫描的排除项
description: 你可以排除文件 (包括由指定进程修改的文件) Microsoft Defender AV 扫描的文件夹。 使用 PowerShell 验证排除项。
keywords: ''
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ksarens
manager: dansimp
ms.technology: mde
ms.audience: ITPro
ms.topic: how-to
ms.openlocfilehash: 08f7f9d4a6e9e70d3ef071f30712b2ae53f4ea52
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/14/2021
ms.locfileid: "51764659"
---
# <a name="configure-and-validate-exclusions-for-microsoft-defender-antivirus-scans"></a>配置并验证 Microsoft Defender 防病毒扫描的排除项

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**适用于：**

- [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)

你可以从 Microsoft Defender 防病毒扫描中排除某些文件、文件夹、进程和进程打开的文件。 此类排除项适用于 [计划扫描](scheduled-catch-up-scans-microsoft-defender-antivirus.md)、按需 [扫描](run-scan-microsoft-defender-antivirus.md)和 [始终实时保护和监视](configure-real-time-protection-microsoft-defender-antivirus.md)。 进程打开的文件的排除项仅适用于实时保护。

## <a name="configure-and-validate-exclusions"></a>配置和验证排除

若要配置和验证排除项，请参阅以下内容：

- [根据文件名、扩展名和文件夹位置配置并验证排除项](configure-extension-file-exclusions-microsoft-defender-antivirus.md)。 这使你能够基于文件扩展名、文件名或位置从 Microsoft Defender 防病毒扫描中排除文件。

- [配置并验证进程打开的文件的排除项](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md)。 这使你可以从特定进程打开的扫描中排除文件。

## <a name="recommendations-for-defining-exclusions"></a>定义排除项的建议
[!IMPORTANT]
Microsoft Defender 防病毒包括许多基于已知操作系统行为和典型管理文件（例如用于企业管理、数据库管理和其他企业方案和情况的文件）的自动排除项。  
定义排除项会降低 Microsoft Defender 防病毒所提供的保护。 您应始终评估与实施排除项相关的风险，并且只应排除您确信不是恶意的文件。

以下是定义排除项时应记住的建议列表：  

- 从技术上说，排除项是一个保护差距，在定义排除项时，始终考虑其他缓解措施。 其他缓解措施可以非常简单，只需确保排除的位置具有适当的访问控制列表 (ACL) 、审核策略、由最新的软件等进行处理。

- 定期查看排除项。 作为审阅过程的一部分，重新检查和重新强制执行缓解。

- 理想情况下，避免定义主动排除项。 例如，不要仅因为你认为将来可能会出现问题而排除某些内容。 仅将排除项用于特定问题（主要围绕性能，有时围绕排除可以缓解的应用程序兼容性）。

- 审核排除列表更改。 安全管理员应保留有关添加特定排除的原因的足够上下文。 您应该能够提供答案，并说明排除特定路径的原因的特定原因。

## <a name="related-articles"></a>相关文章

- [Windows Server 2016 上的 Microsoft Defender 防病毒排除项](configure-server-exclusions-microsoft-defender-antivirus.md)
- [定义排除时要避免的常见错误](common-exclusion-mistakes-microsoft-defender-antivirus.md)
