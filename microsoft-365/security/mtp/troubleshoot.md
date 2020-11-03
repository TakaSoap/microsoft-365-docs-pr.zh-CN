---
title: 解决 Microsoft 365 Defender 服务问题
description: 查找已知 Microsoft 365 Defender 问题的解决方案和解决办法
keywords: 解决 Microsoft 威胁防护、故障排除、Azure ATP、问题、加载项、设置页面
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: 16cb1116f400c8d0a83ccc4cac23da06cd1be2a4
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2020
ms.locfileid: "48844664"
---
# <a name="troubleshoot-microsoft-365-defender-service-issues"></a>解决 Microsoft 365 Defender 服务问题

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**适用于：**
- Microsoft 365 Defender

本节介绍在使用 Microsoft 365 Defender 服务时可能出现的问题。


## <a name="i-dont-see-microsoft-365-defender-content"></a>我看不到 Microsoft 365 Defender 内容
如果您在门户中看不到导航窗格中的功能（如事件、操作中心或搜寻），则需要验证您的租户是否具有相应的许可证。 

有关详细信息，请参阅[必备条件](prerequisites.md)。

## <a name="microsoft-defender-for-identity-alerts-are-not-showing-up-in-the-microsoft-365-defender-incidents"></a>Microsoft 无法在 Microsoft 365 Defender 事件中显示标识警报的 microsoft Defender
如果你已在你的环境中部署了 Microsoft Defender，但你没有在 Microsoft 365 Defender 事件中看到标识警报的 Defender，则需要确保已启用 Microsoft 云应用安全和 Defender for Identity 集成。 

有关详细信息，请参阅 [Microsoft Defender For Identity integration](https://docs.microsoft.com/cloud-app-security/aatp-integration)。

## <a name="where-is-the-settings-page-for-turning-the-service-on"></a>打开服务的设置页面在什么位置？
若要打开 Microsoft 365 Defender，请访问 Microsoft 365 安全中心导航窗格中的 **设置** 。 仅当您具有 [必备权限和许可证](mtp-enable.md#check-license-eligibility-and-required-permissions)时，才会看到此导航项。
 

