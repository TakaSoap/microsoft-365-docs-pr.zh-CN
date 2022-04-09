---
title: 排查Microsoft 365 Defender服务问题
description: 查找已知Microsoft 365 Defender问题的解决方案和解决方法
keywords: 排查Microsoft 365 Defender、故障排除、Microsoft Defender for Identity、问题、加载项、设置页
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 656599cf9ec66987119819b2f28f9a8eff1d4e77
ms.sourcegitcommit: 1ef176c79a0e6dbb51834fe30807409d4e94847c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/19/2021
ms.locfileid: "64731661"
---
# <a name="troubleshoot-microsoft-365-defender-service-issues"></a>排查Microsoft 365 Defender服务问题

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**适用于：**
- Microsoft 365 Defender

本部分解决了使用Microsoft 365 Defender服务时可能出现的问题。

## <a name="i-dont-see-microsoft-365-defender-content"></a>我看不到Microsoft 365 Defender内容

如果在门户中的导航窗格（例如"事件"、"操作中心"或"搜寻"）上看不到功能，则需要验证租户是否具有相应的许可证。

有关详细信息，请参阅[先决条件](prerequisites.md)。

## <a name="microsoft-defender-for-identity-alerts-are-not-showing-up-in-the-microsoft-365-defender-incidents"></a>Microsoft Defender for Identity警报未显示在Microsoft 365 Defender事件中

如果在环境中部署了Microsoft Defender for Identity，但未将 Defender for Identity 警报视为Microsoft 365 Defender事件的一部分，则需要确保Microsoft Defender for Cloud Apps 已启用 Defender for Identity 集成。

有关详细信息，请参阅[Microsoft Defender for Identity集成](/cloud-app-security/mdi-integration)。

## <a name="where-is-the-settings-page-for-turning-on-the-service"></a>用于打开服务的"设置"页在哪里？

若要打开Microsoft 365 Defender，**请从Microsoft 365 Defender** 门户中的导航窗格访问设置。 仅当具有 [先决条件权限和许可证](m365d-enable.md#check-license-eligibility-and-required-permissions)时，此导航项才可见。

## <a name="how-do-i-create-an-exception-for-my-fileurl"></a>如何实现为文件/URL 创建异常？

误报是检测为恶意但不是威胁的文件或 URL。 可以创建指示器并定义排除项以取消阻止并允许某些文件/URL。 请参阅 [Defender for Endpoint 中的地址误报/负值](/microsoft-365/security/defender-endpoint/defender-endpoint-false-positives-negatives)。
