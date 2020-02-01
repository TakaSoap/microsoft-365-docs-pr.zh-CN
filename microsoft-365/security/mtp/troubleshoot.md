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
ms.openlocfilehash: bbc7d5d434765b94b0b2707605be2edfbbc8e423
ms.sourcegitcommit: 2913fd74ad5086c7cac6388447285be9aa5a8e44
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/01/2020
ms.locfileid: "41661978"
---
# <a name="troubleshoot-microsoft-threat-protection-service-issues"></a>解决 Microsoft 威胁防护服务问题

**适用于：**
- Microsoft 威胁防护

本节介绍使用 Microsoft 威胁防护服务时可能会出现的问题。


## <a name="i-dont-see-microsoft-threat-protection-content"></a>我看不到 Microsoft 威胁防护内容
如果您在门户中看不到导航窗格中的功能（如事件、操作中心或搜寻），则需要验证您的租户是否具有相应的许可证。 

有关详细信息，请参阅[必备条件](prerequisites.md)。

## <a name="azure-atp-alerts-are-not-showing-up-in-the-microsoft-threat-protection-incidents"></a>Azure ATP 警报未在 Microsoft 威胁防护事件中显示
如果在环境中部署了 Azure ATP，但在 Microsoft 威胁防护事件中看不到 Azure ATP 警报，需要确保启用 Microsoft Cloud App Security 和 Azure ATP 集成。 

有关详细信息，请参阅[Azure ATP 集成](https://docs.microsoft.com/cloud-app-security/aatp-integration)。

## <a name="is-microsoft-threat-protection-available-for-us-government-community-cloud-gcc-or-gcc-high"></a>Microsoft 威胁防护是否可供美国政府社区云（GCC）或 GCC High使用？
目前不可用。

## <a name="where-is-the-settings-page-for-turning-the-service-on"></a>打开服务的设置页面在什么位置？
若要打开 Microsoft 威胁防护，请访问 Microsoft 365 安全中心中的导航窗格中的**设置**。 仅当您具有[必备权限和许可证](mtp-enable.md#check-license-eligibility-and-required-permissions)时，才会看到此导航项。

## <a name="can-i-use-an-add-on-instead-of-the-required-e5-licenses"></a>我是否可以使用加载项，而不是所需的 E5 许可证？
目前没有适用于 Microsoft 威胁防护的加载项。 [请参阅许可要求](prerequisites.md) 

