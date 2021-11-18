---
title: 在 Windows 设备上启用适用于 Office 2013 的新式验证
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- okr_smb
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 7dc1c01a-090f-4971-9677-f1b192d6c910
description: 了解如何设置注册表项，为已安装 2013 Microsoft Office新式验证。
ms.openlocfilehash: c5af8daa0538a1eb89521b12d1c85c310df6d012
ms.sourcegitcommit: 7e59802f251da96ec639fb09534aa96acf5d6ce7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/18/2021
ms.locfileid: "61071872"
---
# <a name="enable-modern-authentication-for-office-2013-on-windows-devices"></a>在 Windows 设备上启用适用于 Office 2013 的新式验证

若要为安装了 Office 2013 的任何 Windows 设备启用新式验证，需设置特定的注册表项。
  
## <a name="enable-modern-authentication-for-office-2013-clients"></a>为 Office 2013 客户端启用新式验证

> [!NOTE]
> 已为 Office 2016 客户端启用新式验证，无需设置 Office 2016 的注册表项。 
  
若要为运行 Windows 且安装了 Microsoft Office 2013 的任何设备（例如笔记本电脑和平板电脑）启用新式验证，需设置以下注册表项。 需要在要启用新式验证的每台设备上设置密钥：
  
|**注册表项**|**类型**|**值** |
|:-------|:------:|--------:|
|HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL  |REG_DWORD  |1  |
|HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\Version |REG_DWORD |1 |
   
设置注册表项后，可以将 Office 2013 设备应用设置为将多重身份验证 ([MFA](set-up-multi-factor-authentication.md)) 与 Microsoft 365。 
  
如果当前登录了任何客户端应用，需注销并重新登录以使更改生效。 否则，在建立标识之前，MRU 和漫游设置将不可用。
  
## <a name="disable-modern-authentication-on-devices"></a>在设备上禁用新式验证

若要在设备上禁用新式验证，请在设备上设置以下注册表项：
  
|**注册表项**|**类型**|**值**|
|:-------|:------:|--------:|
|HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL |REG_DWORD|0|
   
## <a name="related-content"></a>相关内容

使用本文Office验证方法登录到 ([2013](https://support.microsoft.com/office/2b856342-170a-438e-9a4f-3c092394d3cb)) \
[Outlook提示输入密码，](/outlook/troubleshoot/authentication/outlook-prompt-password-modern-authentication-enabled)并且不使用新式验证连接到Office 365 (文章) 

