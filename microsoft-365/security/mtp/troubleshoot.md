---
title: Microsoft 365 Defender 服务问题疑难解答
description: 查找解决方案并解决已知的 Microsoft 365 Defender 问题
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
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 414743fa5ba25b9d2714c1dd08dd38e34ec94372
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/22/2021
ms.locfileid: "49925714"
---
# <a name="troubleshoot-microsoft-365-defender-service-issues"></a>Microsoft 365 Defender 服务问题疑难解答

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**适用于：**
- Microsoft 365 Defender

本部分介绍使用 Microsoft 365 Defender 服务时可能出现的问题。

## <a name="i-dont-see-microsoft-365-defender-content"></a>我看不到 Microsoft 365 Defender 内容

如果在导航窗格中看不到功能，如门户中的事件、操作中心或搜寻，则需要验证租户是否具有相应的许可证。

有关详细信息，请参阅[必备条件](prerequisites.md)。

## <a name="microsoft-defender-for-identity-alerts-are-not-showing-up-in-the-microsoft-365-defender-incidents"></a>Microsoft 365 Defender 事件中未显示 Microsoft Defender 标识警报

如果你的环境中部署了 Microsoft Defender for Identity，但看不到 Defender for Identity 警报作为 Microsoft 365 Defender 事件的一部分，则需要确保 Microsoft Cloud App Security 和 Defender for Identity 集成已启用。

有关详细信息，请参阅 [Microsoft Defender for Identity 集成](https://docs.microsoft.com/cloud-app-security/mdi-integration)。

## <a name="where-is-the-settings-page-for-turning-the-service-on"></a>用于打开服务的设置页在哪里？

若要打开 Microsoft 365 Defender，请从 Microsoft 365 安全中心的导航窗格中访问"设置"。  只有拥有必备权限和许可证时，才能看到 [此导航项](mtp-enable.md#check-license-eligibility-and-required-permissions)。
