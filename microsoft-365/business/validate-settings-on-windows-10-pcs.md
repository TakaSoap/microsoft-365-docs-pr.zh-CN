---
title: 验证 Windows 10 电脑上的应用保护设置
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
ms.custom: OKR_SMB_M365
search.appverid:
- BCS160
- MET150
ms.assetid: fae8819d-7235-495f-9f07-d016f545887f
description: 了解如何在 Windows 10 设备中验证 Microsoft 365 商业应用保护设置。
ms.openlocfilehash: 66e83df19e44419b37bcc1c5678ab13317162dbc
ms.sourcegitcommit: 6003d6da0a85c97357eb3dba3918eb145f381fe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/27/2019
ms.locfileid: "37288587"
---
# <a name="validate-device-protection-settings-on-windows-10-pcs"></a>验证 Windows 10 电脑上的设备保护设置

## <a name="verify-that-windows-10-device-policies-are-set"></a>验证是否已设置 Windows 10 设备策略

[设置设备策略](protection-settings-for-windows-10-pcs.md)后，可能需要几个小时才能使策略在用户的设备上生效。 您可以通过查看用户设备上的各种 Windows 设置屏幕来确认这些策略是否生效。 由于用户无法修改其 Windows 10 设备上的 Windows Update 和 Windows Defender 防病毒设置，因此许多选项都将灰显。
  
1. 转到 "**设置** \> " " ** &amp;更新安全** **** \> \> Windows 更新**重新启动选项**"，并确认所有设置都将灰显。 
    
    ![所有重新启动选项都将灰显。](media/31308da9-18b0-47c5-bbf6-d5fa6747c376.png)
  
2. 转到 "**设置** \> " "**更新&amp;安全** **** \> \> Windows 更新**高级选项**"，并确认所有设置都将灰显。 
    
    ![Windows 高级更新选项都将灰显。](media/049cf281-d503-4be9-898b-c0a3286c7fc2.png)
  
3. 转到**设置** \> **更新&amp;安全** \> **Windows 更新** \> **高级选项** \> **选择如何传递更新**。
    
    确认您可以看到某些设置已被组织隐藏或管理的邮件（红色），所有选项都将灰显。
    
    ![选择如何传递更新页面指示你的组织隐藏或管理的设置。](media/6b3e37c5-da41-4afd-9983-b4f406216b59.png)
  
4. 若要打开 windows defender 安全中心，请转**到设置** \> ** &amp;更新安全** \> \> **Windows defender**单击**打开 windows defender 安全中心** \> **病毒&amp;线程保护** \> **病毒&amp;威胁防护设置**。 
    
5. 验证所有选项是否都已灰显。 
    
    !["病毒和威胁防护" 设置将灰显。](media/9ca68d40-a5d9-49d7-92a4-c581688b5926.png)
  
## <a name="related-topics"></a>相关主题

[Microsoft 365 Business documentation and resources](https://go.microsoft.com/fwlink/p/?linkid=853701)（Microsoft 365 Business 文档和资源）
  
[Microsoft 365 Business 入门](microsoft-365-business-overview.md)
  
[管理 Microsoft 365 Business](manage.md)
  
[设置 Windows 10 电脑的设备配置](protection-settings-for-windows-10-pcs.md)
  

