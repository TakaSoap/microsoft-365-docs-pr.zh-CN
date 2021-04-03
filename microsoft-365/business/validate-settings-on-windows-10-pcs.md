---
title: 验证 Windows 10 电脑上的应用保护设置
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: fae8819d-7235-495f-9f07-d016f545887f
description: 了解如何验证 Microsoft 365 商业版应用保护设置是否对用户的 Windows 10 设备生效。
ms.openlocfilehash: fcb463fd98f692f7d4802689e0c03fe4e3e648a1
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579834"
---
# <a name="validate-device-protection-settings-on-windows-10-pcs"></a>验证 Windows 10 PC 上的设备保护设置

## <a name="verify-that-windows-10-device-policies-are-set"></a>验证 Windows 10 设备策略是否设置

设置 [设备策略后](protection-settings-for-windows-10-pcs.md)，策略可能需要几个小时才能在用户的设备上生效。 可以通过查看用户设备上的各个 Windows 设置屏幕来确认策略是否生效。 由于用户将无法修改 Windows 更新，Windows Defender Windows 10 设备上禁用防病毒设置，因此许多选项将灰显。
  
1. 转到"**设置** \> **&amp; ""更新安全性** \> **""Windows** 更新 \> ""重启"选项，并确认所有设置都显示为灰色。 
    
    ![所有"重启"选项都灰显。](../media/31308da9-18b0-47c5-bbf6-d5fa6747c376.png)
  
2. 转到设置 \> **更新 &amp; 安全性** \> **Windows 更新** \> **高级选项** 并确认所有设置都灰显。 
    
    ![Windows 高级更新选项全部灰显。](../media/049cf281-d503-4be9-898b-c0a3286c7fc2.png)
  
3. 转到设置 \> **更新 &amp; 安全性** \> **Windows 更新** \> **高级选项** \> **选择如何传递更新**。
    
    确认你能看到红色 (显示) 某些设置被组织隐藏或管理，并且所有选项都显示为灰色。
    
    ![选择更新的传递方式页面指示组织隐藏或管理设置。](../media/6b3e37c5-da41-4afd-9983-b4f406216b59.png)
  
4. 若要打开Windows Defender安全中心"，请转到"设置""更新Windows Defender"打开Windows Defender病毒线程保护 \> **&amp;** \>  \>  \> **&amp;** \> **病毒 &amp; 威胁防护设置"。** 
    
5. 验证所有选项是否灰显。 
    
    ![病毒和威胁防护设置灰显。](../media/9ca68d40-a5d9-49d7-92a4-c581688b5926.png)
  
## <a name="related-topics"></a>相关主题

[Microsoft 365 商业版文档和资源](./index.yml)
  
[Microsoft 365 商业版入门](microsoft-365-business-overview.md)
  
[管理 Microsoft 365 商业版](manage.md)
  
[设置 Windows 10 电脑的设备配置](protection-settings-for-windows-10-pcs.md)
