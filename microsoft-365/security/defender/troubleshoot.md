---
title: 解决Microsoft 365 Defender服务问题
description: 查找已知问题的解决方案Microsoft 365 Defender解决方法
keywords: 疑Microsoft 365 Defender， 疑难解答， Microsoft Defender for Identity， 问题， 加载项， 设置页面
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 9b60adc266de6b99f61712d2d8303fc22c4cb9e1bf44d99bdc66f16c2a5a09d0
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "53792599"
---
# <a name="troubleshoot-microsoft-365-defender-service-issues"></a>解决Microsoft 365 Defender服务问题

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**适用于：**
- Microsoft 365 Defender

本节解决使用服务时可能出现的Microsoft 365 Defender问题。

## <a name="i-dont-see-microsoft-365-defender-content"></a>我看不到Microsoft 365 Defender内容

如果在门户中看不到导航窗格上的功能，如事件、操作中心或搜寻，则需要验证租户是否具有相应的许可证。

有关详细信息，请参阅[先决条件](prerequisites.md)。

## <a name="microsoft-defender-for-identity-alerts-are-not-showing-up-in-the-microsoft-365-defender-incidents"></a>Microsoft Defender 标识警报未显示在事件Microsoft 365 Defender中

如果你的环境中已部署 Microsoft Defender for Identity，但没有在 Microsoft 365 Defender 事件中看到 Defender for Identity 警报，则需要确保已启用 Microsoft Cloud App Security 和 Defender for Identity 集成。

有关详细信息，请参阅 [Microsoft Defender 的标识集成](/cloud-app-security/mdi-integration)。

## <a name="where-is-the-settings-page-for-turning-on-the-service"></a>用于打开服务的设置页在哪里？

若要打开Microsoft 365 Defender，设置安全中心中的导航窗格中Microsoft 365权限。 只有拥有必备权限和许可证 时，此 [导航项才可见](m365d-enable.md#check-license-eligibility-and-required-permissions)。

## <a name="how-do-i-create-an-exception-for-my-fileurl"></a>如何为文件/URL 创建异常？

误报是一种文件或 URL，被检测为恶意文件，但不是威胁。 你可以创建指示器并定义排除项以取消阻止并允许某些文件/URL。 请参阅在 Defender for Endpoint 中解决 [误报/负数](/microsoft-365/security/defender-endpoint/defender-endpoint-false-positives-negatives)。
