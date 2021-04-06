---
title: Microsoft 365 Defender 服务问题疑难解答
description: 查找已知 Microsoft 365 Defender 问题的解决方案和解决方法
keywords: Microsoft 威胁防护疑难解答， 疑难解答， Azure ATP， 问题， 加载项， 设置页面
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
ms.openlocfilehash: a2cd27bf7bf8b1c4931b9d768f3a6b5e5f2a0d93
ms.sourcegitcommit: e0a96e08b7dc29e074065e69a2a86fc3cf0dad01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/06/2021
ms.locfileid: "51592032"
---
# <a name="troubleshoot-microsoft-365-defender-service-issues"></a>Microsoft 365 Defender 服务问题疑难解答

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**适用于：**
- Microsoft 365 Defender

本部分解决使用 Microsoft 365 Defender 服务时可能出现的问题。

## <a name="i-dont-see-microsoft-365-defender-content"></a>我看不到 Microsoft 365 Defender 内容

如果在门户中看不到导航窗格上的功能，如事件、操作中心或搜寻，则需要验证租户是否具有相应的许可证。

有关详细信息，请参阅[必备条件](prerequisites.md)。

## <a name="microsoft-defender-for-identity-alerts-are-not-showing-up-in-the-microsoft-365-defender-incidents"></a>Microsoft 365 Defender 事件中未显示 Microsoft Defender 标识警报

如果你的环境中已部署 Microsoft Defender for Identity，但没有在 Microsoft 365 Defender 事件中看到 Defender for Identity 警报，则需要确保 Microsoft Cloud App Security 和 Defender for Identity 集成已启用。

有关详细信息，请参阅 [Microsoft Defender 的标识集成](/cloud-app-security/mdi-integration)。

## <a name="where-is-the-settings-page-for-turning-on-the-service"></a>用于打开服务的设置页在哪里？

若要打开 Microsoft 365 Defender， **请从** Microsoft 365 安全中心的导航窗格中访问设置。 只有拥有必备权限和许可证 时，此 [导航项才可见](m365d-enable.md#check-license-eligibility-and-required-permissions)。

## <a name="how-do-i-create-an-exception-for-my-fileurl"></a>如何为文件/URL 创建异常？

误报是一种文件或 URL，被检测为恶意文件，但不是威胁。 你可以创建指示器并定义排除项以取消阻止并允许某些文件/URL。 请参阅在 Defender for Endpoint 中解决 [误报/负数](/microsoft-365/security/defender-endpoint/defender-endpoint-false-positives-negatives)。


