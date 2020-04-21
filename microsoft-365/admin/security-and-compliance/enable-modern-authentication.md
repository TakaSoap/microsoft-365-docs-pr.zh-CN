---
title: 在 Windows 设备上启用适用于 Office 2013 的新式验证
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
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 7dc1c01a-090f-4971-9677-f1b192d6c910
description: 了解如何设置注册表项以启用安装了 Microsoft Office 2013 的设备的新式验证。
ms.openlocfilehash: 8dec8174d5f39d8fecd6b2a7340d69dbcd421357
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/21/2020
ms.locfileid: "43627724"
---
# <a name="enable-modern-authentication-for-office-2013-on-windows-devices"></a>在 Windows 设备上启用适用于 Office 2013 的新式验证

若要为安装了 Office 2013 的任何 Windows 设备启用新式验证，需设置特定的注册表项。
  
## <a name="enable-modern-authentication-for-office-2013-clients"></a>为 Office 2013 客户端启用新式验证

> [!NOTE]
> 已为 Office 2016 客户端启用新式验证，无需设置 Office 2016 的注册表项。 
  
若要为运行 Windows 且安装了 Microsoft Office 2013 的任何设备（例如笔记本电脑和平板电脑）启用新式验证，需设置以下注册表项。必须在每台要启用新式验证的设备上设置注册表项：
  
|**注册表项**|**类型**|**值** |
|:-------|:------:|--------:|
|HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL  |REG_DWORD  |1  |
|HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\Version |REG_DWORD |1 |
   
设置注册表项后，可以将 Office 2013 设备应用设置为使用具有 Microsoft 365 的[多重身份验证（MFA）](set-up-multi-factor-authentication.md) 。 
  
如果当前登录了任何客户端应用，需注销并重新登录以使更改生效。否则，在建立 ADAL 标识之前，MRU 和漫游设置将不可用。
  
## <a name="disable-modern-authentication-on-devices"></a>在设备上禁用新式验证

若要在设备上禁用新式验证，请在设备上设置以下注册表项：
  
|**注册表项**|**类型**|**值**|
|:-------|:------:|--------:|
|HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL |REG_DWORD|0|
   
## <a name="related-articles"></a>相关文章
[使用第二种验证方法登录 Office 2013](https://support.office.com/article/2b856342-170a-438e-9a4f-3c092394d3cb.aspx)

  

