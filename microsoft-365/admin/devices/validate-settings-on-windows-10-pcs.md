---
title: 验证电脑的应用Windows 10设置
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
description: 了解如何验证Microsoft 365应用保护设置是否对用户的设备Windows 10生效。
ms.openlocfilehash: 67608c2c4b8396bced350685f439cb15f6378e6a
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/12/2021
ms.locfileid: "59169826"
---
# <a name="validate-device-protection-settings-for-windows-10-pcs"></a>验证电脑的设备Windows 10设置

## <a name="verify-that-windows-10-device-policies-are-set"></a>验证Windows 10策略是否设置

设置 [设备策略后](protection-settings-for-windows-10-pcs.md)，策略可能需要几个小时才能在用户的设备上生效。 通过查看用户设备上的各个Windows 设置，可以确认策略是否生效。 由于用户无法修改 Windows 更新和Windows Defender 防病毒上的 Windows 10 设置，因此许多选项将灰显。
  
1. Go to **设置** \> **Update &amp; security** \> **Windows Update** Restart \> **options** and confirm that all settings are grayed out. 
    
    ![所有"重启"选项都灰显。](../../media/31308da9-18b0-47c5-bbf6-d5fa6747c376.png)
  
2. Go to **设置** \> **Update security &amp; Windows** \> **Update** \> **Advanced options** and confirm that all settings are grayed out. 
    
    ![Windows高级更新选项全部灰显。](../../media/049cf281-d503-4be9-898b-c0a3286c7fc2.png)
  
3. Go to **设置** \> **Update &amp; security** \> **Windows Update** Advanced \> **options** Choose how \> **updates are delivered**.
    
    确认你能看到红色 (显示) 某些设置被组织隐藏或管理，并且所有选项都显示为灰色。
    
    ![选择更新的传递方式页面指示组织隐藏或管理设置。](../../media/6b3e37c5-da41-4afd-9983-b4f406216b59.png)
  
4. 若要打开Windows Defender安全中心，请转到设置更新安全Windows Defender单击打开Windows Defender病毒线程保护病毒威胁防护 \> **&amp;** \>  \>  \> **&amp;** \> **&amp; 设置"**。 
    
5. 验证所有选项是否灰显。 
    
    ![病毒和威胁防护设置灰显。](../../media/9ca68d40-a5d9-49d7-92a4-c581688b5926.png)
  
## <a name="related-content"></a>相关内容

[Microsoft 365文档和资源](./index.yml)\
[设置 Windows 10 电脑的设备配置](protection-settings-for-windows-10-pcs.md)
