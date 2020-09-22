---
title: ATP 安全链接的工作原理
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: Admin
ms.date: ''
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: "\"安全链接\" 功能可提供对 Office 文档中的超链接和电子邮件中的超链接的单击时间验证。 阅读本文，了解 ATP 安全链接的工作原理。"
ms.openlocfilehash: 09357b20173e2609587137764737c8aba044190e
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/22/2020
ms.locfileid: "48201461"
---
# <a name="how-atp-safe-links-works"></a>ATP 安全链接的工作原理

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

> [!IMPORTANT] 
> 为了使 Office 365 ATP 安全链接正常运行，所有服务都必须为同一版本。
         
## <a name="how-atp-safe-links-works"></a>ATP 安全链接的工作原理

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]
 使用电子邮件中的 Url

从较高的层次来看， [ATP 安全链接](atp-safe-links.md) 保护在 Office 365 中托管的电子邮件 (的 url 的工作方式，而不是本地) ：
  
1. 用户接收包含 Url 的电子邮件。
    
2. 所有电子邮件都通过 Exchange Online Protection，其中 internet 协议 (IP) 和信封筛选器、基于签名的恶意软件保护、反垃圾邮件和反恶意软件筛选器均可应用。 
    
3. 电子邮件到达用户的收件箱。
    
4. 用户登录到 Office 365，并转到其电子邮件收件箱。
    
5. 用户打开一封电子邮件，然后单击电子邮件中的 URL。
    
6. ATP 安全链接功能将在打开网站之前立即检查 URL。 该 URL 被标识为 "阻止"、"恶意" 或 "安全"。
        
   - 如果 URL 指向的网站包含在组织的 [自定义阻止 url 列表](set-up-a-custom-blocked-urls-list-atp.md)中，则会打开一个 [警告页面](atp-safe-links-warning-pages.md) 。 
    
   - 如果 URL 指向已确定为恶意的网站，将打开 " [警告" 页](atp-safe-links-warning-pages.md) 。 
    
   - 如果 URL 转到一个可下载的文件，并且您的组织的 [ATP 安全链接策略](set-up-atp-safe-links-policies.md) 已配置为扫描此类内容，则会检查下载的文件。 
    
   - 如果确定该 URL 是安全的，则会打开该网站。
    
## <a name="how-atp-safe-links-works"></a>ATP 安全链接的工作原理

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]
 Office 文档中的 Url 

从较高的层次来看， [ATP 安全链接](atp-safe-links.md) 保护在 Microsoft 365 应用程序中适用于企业或商业高级应用程序的 url 的方式 (当前版本的 Word、Excel 和 PowerPoint 在 Windows、Mac 或浏览器、IOS 或 Android 设备上的 Office 应用、在浏览器) 中的 Visio （OneNote 中）：
  
1. 用户已在其计算机、智能手机或平板电脑上安装了适用于企业或商业高级的 Microsoft 365 应用程序。  (或在其浏览器中使用 Office。 ) 
    
2. 用户在浏览器) 或 Visio (在桌面) 中打开 Word、Excel、PowerPoint、OneNote (，并使用其工作或学校帐户登录到 Office 365 企业版。 文档包含 Url。
    
3. 当用户单击文档中的某个 URL 时，ATP 安全链接服务将检查该链接。
    
   - 如果 URL 指向的网站包含在组织的 [自定义阻止 url 列表](set-up-a-custom-blocked-urls-list-atp.md)中，则会向用户提供一个 [警告页面](atp-safe-links-warning-pages.md)。
    
   - 如果 URL 指向已确定为恶意的网站，则会向用户提供 [警告页面](atp-safe-links-warning-pages.md)。
    
   - 如果 URL 转到可下载的文件，并且已将 [ATP 安全链接策略](set-up-atp-safe-links-policies.md) 配置为扫描此类下载，则会检查可下载的文件。 
    
   - 如果该 URL 被认为是安全的，则会将用户转到该网站。
      
   - 如果 URL 检查失败，安全链接的保护将不会触发。 在桌面客户端上，将在继续进入网站之前警告用户。
      
> [!NOTE]
> 在每个会话开始时可能需要几秒钟的时间来验证用户是否已启用 Office 的 ATP 安全链接。 
      
