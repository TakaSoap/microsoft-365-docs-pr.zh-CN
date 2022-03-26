---
title: 在设备上为 Office 2013 Windows新式验证
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
ms.openlocfilehash: 468658c3b346c7923937ff9595699a20306ed6a9
ms.sourcegitcommit: d32654bdfaf08de45715dd362a7d42199bdc1ee7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2022
ms.locfileid: "63754174"
---
# <a name="enable-modern-authentication-for-office-2013-on-windows-devices"></a>在设备上为 Office 2013 Windows新式验证

Microsoft Office Microsoft Windows 2013 支持新式验证。 但是，若要启用它，需要配置以下注册表项：

|注册表项|类型|值|
|:---|:---:|:---:|
|HKEY_CURRENT_USER\Software\Microsoft\Exchange\AlwaysUseMSOAuthForAutoDiscover|REG_DWORD|1|
|HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Common\Identity\EnableADAL|REG_DWORD|1|
|HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Common\Identity\Version|REG_DWORD|1|

> [!NOTE]
> 2016 或更高版本Office新式验证。 无需为更高版本的注册表项设置这些注册表Office。

## <a name="enable-modern-authentication-for-office-2013-clients"></a>为 Office 2013 客户端启用新式验证

1. 关闭 Outlook。

2. 将以下文本复制并粘贴到记事本：

   ```text
   Windows Registry Editor Version 5.00

   [HKEY_CURRENT_USER\Software\Microsoft\Exchange]
   "AlwaysUseMSOAuthForAutoDiscover"=dword:00000001

   [HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Common]

   [HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Common\Identity]
   "EnableADAL"=dword:00000001
   "Version"=dword:00000001
   ```

3. 使用文件扩展名 .reg 保存文件，.txt文件保存在易于您查找的位置。 例如，`C:\Data\Office2013_Enable_ModernAuth.reg`。

4. 打开文件资源管理器 (以前称为 Windows Explorer) ，浏览到刚保存的 .reg 文件的位置，然后双击它。

5. 在 **出现的用户帐户控制** 对话框中，单击" **是** "以允许应用对设备进行更改。

6. 在出现的 **注册表编辑器** 警告对话框中，单击" **是** "接受更改。

设置注册表项后，可以将 Office 2013 应用设置为将多重身份验证 (MFA) MFA Microsoft 365。 有关详细信息，请参阅 [设置多重身份验证](set-up-multi-factor-authentication.md)。

如果你当前已登录到任何 Office客户端应用，则需要注销并重新登录，更改生效。 否则，在建立标识之前，MRU 和漫游设置将不可用。

## <a name="disable-modern-authentication-on-devices"></a>在设备上禁用新式验证

在设备上禁用新式验证的过程非常相似，但所需的注册表项较少，需要将其值设置为 0。

|注册表项|类型|值|
|---|:---:|:---:|
|HKEY_CURRENT_USER\Software\Microsoft\Exchange\AlwaysUseMSOAuthForAutoDiscover|REG_DWORD|0|
|HKEY_CURRENT_USER\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL|REG_DWORD|0|

```text
Windows Registry Editor Version 5.00

[HKEY_CURRENT_USER\Software\Microsoft\Exchange]
"AlwaysUseMSOAuthForAutoDiscover"=dword:00000000

[HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Common]

[HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Common\Identity]
"EnableADAL"=dword:00000000
```

## <a name="related-content"></a>相关内容

[使用第二种验证方法登录 Office 2013](https://support.microsoft.com/office/2b856342-170a-438e-9a4f-3c092394d3cb)

[Outlook提示输入密码，并且不使用新式验证连接到Office 365](/outlook/troubleshoot/authentication/outlook-prompt-password-modern-authentication-enabled)
