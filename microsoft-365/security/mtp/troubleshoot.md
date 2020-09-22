---
title: 解决 Microsoft 威胁防护服务问题
description: 查找已知 Microsoft 威胁防护问题的解决方案和变通方法
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
ms.openlocfilehash: bcf5b79fcd2fdf0a5af5648e6f6b7ea65d69594c
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/22/2020
ms.locfileid: "48201283"
---
# <a name="troubleshoot-microsoft-threat-protection-service-issues"></a>解决 Microsoft 威胁防护服务问题

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**适用于：**
- Microsoft 威胁防护

本节介绍使用 Microsoft 威胁防护服务时可能会出现的问题。


## <a name="i-dont-see-microsoft-threat-protection-content"></a>我看不到 Microsoft 威胁防护内容
如果您在门户中看不到导航窗格中的功能（如事件、操作中心或搜寻），则需要验证您的租户是否具有相应的许可证。 

有关详细信息，请参阅[必备条件](prerequisites.md)。

## <a name="azure-atp-alerts-are-not-showing-up-in-the-microsoft-threat-protection-incidents"></a>Azure ATP 警报未在 Microsoft 威胁防护事件中显示
如果在环境中部署了 Azure ATP，但在 Microsoft 威胁防护事件中看不到 Azure ATP 警报，需要确保启用 Microsoft Cloud App Security 和 Azure ATP 集成。 

有关详细信息，请参阅[Azure ATP 集成](https://docs.microsoft.com/cloud-app-security/aatp-integration)。

## <a name="where-is-the-settings-page-for-turning-the-service-on"></a>打开服务的设置页面在什么位置？
若要打开 Microsoft 威胁防护，请访问 Microsoft 365 安全中心中的导航窗格中的 **设置** 。 仅当您具有 [必备权限和许可证](mtp-enable.md#check-license-eligibility-and-required-permissions)时，才会看到此导航项。
 

