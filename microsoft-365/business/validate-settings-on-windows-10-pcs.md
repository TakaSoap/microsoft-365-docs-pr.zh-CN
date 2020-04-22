---
title: 验证 Windows 10 电脑上的应用保护设置
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
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
search.appverid:
- BCS160
- MET150
ms.assetid: fae8819d-7235-495f-9f07-d016f545887f
description: 了解如何验证 Microsoft 365 for business 应用保护设置是否在用户的 Windows 10 设备上生效。
ms.openlocfilehash: b63681f040b0fe49127693e9cb7aac7ba6c41af6
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/21/2020
ms.locfileid: "43635696"
---
# <a name="validate-device-protection-settings-on-windows-10-pcs"></a>验证 Windows 10 电脑上的设备保护设置

## <a name="verify-that-windows-10-device-policies-are-set"></a>验证是否已设置 Windows 10 设备策略

[设置设备策略](protection-settings-for-windows-10-pcs.md)后，可能需要几个小时才能使策略在用户的设备上生效。 您可以通过查看用户设备上的各种 Windows 设置屏幕来确认这些策略是否生效。 由于用户无法修改其 Windows 10 设备上的 Windows Update 和 Windows Defender 防病毒设置，因此许多选项将灰显。
  
1. 转到 "**设置** \> " " ** &amp;更新安全** **Windows Update** \> \> Windows 更新**重新启动选项**"，并确认所有设置均显示为灰色。 
    
    ![所有重新启动选项都将灰显。](../media/31308da9-18b0-47c5-bbf6-d5fa6747c376.png)
  
2. 转到 "**设置** \> " "**更新&amp;安全** **Windows Update** \> \> Windows 更新**高级选项**"，并确认所有设置均显示为灰色。 
    
    ![Windows 高级更新选项全部显示为灰色。](../media/049cf281-d503-4be9-898b-c0a3286c7fc2.png)
  
3. 转到**设置** \> **更新&amp;安全** \> **Windows 更新** \> **高级选项** \> **选择如何传递更新**。
    
    确认您可以看到某些设置已被组织隐藏或管理的邮件（红色），所有选项都将灰显。
    
    ![选择如何传递更新页面指示你的组织隐藏或管理的设置。](../media/6b3e37c5-da41-4afd-9983-b4f406216b59.png)
  
4. 若要打开 windows defender 安全中心，请转到**设置** \> **更新&amp;安全** \> \> **Windows defender**单击**打开 windows defender 安全中心** \> **病毒&amp;线程防护** \> ** &amp;病毒防护设置**。 
    
5. 验证所有选项是否都显示为灰色。 
    
    ![病毒和威胁防护设置显示为灰色。](../media/9ca68d40-a5d9-49d7-92a4-c581688b5926.png)
  
## <a name="related-topics"></a>相关主题

[适用于业务的 Microsoft 365 文档和资源](https://go.microsoft.com/fwlink/p/?linkid=853701)
  
[Microsoft 365 商业版入门](microsoft-365-business-overview.md)
  
[管理 Microsoft 365 商业版](manage.md)
  
[设置 Windows 10 电脑的设备配置](protection-settings-for-windows-10-pcs.md)
  

