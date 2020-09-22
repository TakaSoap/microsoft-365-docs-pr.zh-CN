---
title: 将 Office 365 ATP 与 Microsoft Defender ATP 集成
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.date: 07/08/2020
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 414fa693-d7b7-4a1d-a387-ebc3b6a52889
ms.collection:
- M365-security-compliance
description: 将 Office 365 高级威胁防护与 Microsoft Defender 高级威胁防护集成，以查看更详细的威胁管理信息。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 0906b8b44922084a65999dd9ab10a09c827605c2
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/22/2020
ms.locfileid: "48201967"
---
# <a name="integrate-office-365-advanced-threat-protection-with-microsoft-defender-advanced-threat-protection"></a>将 Office 365 高级威胁防护与 Microsoft Defender 高级威胁防护集成

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


[Office 365 高级威胁防护](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp?view=o365-worldwide) (OFFICE 365 atp) 可以配置为在 MICROSOFT defender ATP)  (使用 [Microsoft Defender 高级威胁防护](https://docs.microsoft.com/windows/security/threat-protection) 。

将 Office 365 ATP 与 Microsoft Defender ATP 集成可帮助你的安全操作团队监控并快速采取行动（如果用户的设备存在风险）。 例如，在启用集成后，安全操作团队将能够查看检测到的电子邮件可能影响的设备，以及这些设备在 Microsoft Defender ATP 中所具有的最近通知数。 

下图描述了 " **设备** " 选项卡的外观，如已启用 MICROSOFT Defender ATP 集成：
  
![启用 Microsoft Defender ATP 后，你可以看到包含警报的设备列表。](../../media/fec928ea-8f0c-44d7-80b9-a2e0a8cd4e89.PNG)
  
在此示例中，可以看到检测到的电子邮件的收件人有四台设备，并且有一个警报。 单击设备的链接将在 Microsoft Defender 安全中心 () 中打开其页面 [https://securitycenter.windows.com](https://securitycenter.windows.com) 。

> [!TIP]
> **[了解有关 Microsoft Defender 安全中心的详细信息](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/use)** (也称为 MICROSOFT defender ATP 门户。 ) 
  
## <a name="requirements"></a>Requirements

- 您的组织必须拥有 Office 365 ATP Plan 2 (或 Office 365 E5) 和 Microsoft Defender ATP。
    
- 您必须是全局管理员或具有安全管理员角色 (如安全 [ &amp; 合规中心](https://protection.office.com)中分配的安全管理员) 。  (查看 [安全 &amp; 合规性中心中的权限](permissions-in-the-security-and-compliance-center.md)) 
    
- 您必须具有对 [资源管理器 (或实时检测) ](threat-explorer.md) 在安全 & 合规中心和 Microsoft Defender 安全中心中的访问权限。
    
## <a name="to-integrate-office-365-atp-with-microsoft-defender-atp"></a>将 Office 365 ATP 与 Microsoft Defender ATP 集成

通过使用安全 & 合规性中心和 Microsoft Defender 安全中心，将 Office 365 ATP 与 Microsoft Defender ATP 集成。
  
1. 作为全局管理员或安全管理员，请转到 [https://protection.office.com](https://protection.office.com) 并登录。  (此操作将转到 Office 365 安全 & 合规中心。 ) 
    
2. 在导航窗格中，选择 "**威胁管理**  >  **资源管理器**"。<br>![威胁管理菜单中的资源管理器](../../media/ThreatMgmt-Explorer-nav.png)<br>
    
3. 在屏幕的右上角，选择 " **WDATP 设置**"。
    
4. 在 "Microsoft Defender ATP 连接" 对话框中，启用 " **连接到 WINDOWS ATP**"。<br>![Microsoft Defender ATP 连接](../../media/Explorer-WDATPConnection-dialog.png)<br>
    
5. 请转到 Microsoft Defender 安全中心 ([https://securitycenter.windows.com](https://securitycenter.windows.com)) 。

6. 在导航栏中，选择 " **设置**"。 然后，在 " **常规**" 下，选择 " **高级功能**"。

7. 向下滚动到 " **Office 365 威胁智能连接**"，然后打开连接。<br/>![Office 365 威胁智能连接](../../media/mdatp-oatptoggle.png)<br>

## <a name="related-articles"></a>相关文章

[Office 365 中的威胁调查和响应功能](office-365-ti.md)
  
[Office 365 高级威胁防护](office-365-atp.md)
  
[Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection)
