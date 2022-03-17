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
ms.openlocfilehash: c390e3b9858a4d7d8fc37ea5c5e6f1901d5e20fb
ms.sourcegitcommit: 3fb76db6b34e24569417f4c8a41b99f46a780389
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/17/2022
ms.locfileid: "63525107"
---
# <a name="enable-modern-authentication-for-office-2013-on-windows-devices"></a>在 Windows 设备上启用适用于 Office 2013 的新式验证

若要为安装了 Office 2013 的任何 Windows 设备启用新式验证，需设置特定的注册表项。
  
## <a name="enable-modern-authentication-for-office-2013-clients"></a>为 Office 2013 客户端启用新式验证

> [!NOTE]
> 已为 Office 2016 客户端启用新式验证，无需设置 Office 2016 的注册表项。 
  
若要为运行 Windows 且安装了 Microsoft Office 2013 的任何设备（例如笔记本电脑和平板电脑）启用新式验证，需设置以下注册表项。 需要在要启用新式验证的每台设备上设置密钥：

<br>

****

|注册表项|类型|值|
|:---|:---:|---:|
|HKEY_CURRENT_USER\Software\Microsoft\Exchange\AlwaysUseMSOAuthForAutoDiscover|REG_DWORD|1|
|HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Common\Identity\EnableADAL|REG_DWORD|1|
|HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Common\Identity\Version|REG_DWORD|1|

创建或修改以下注册表项以强制Outlook Web 服务（如 EWS 和自动发现）使用较新的身份验证方法。 我们建议用户强制Outlook新式验证。

1. 退出 Outlook。

2. 根据你的注册表版本，使用下列过程之一启动注册表Windows：

   - **Windows 10、Windows 8.1 和 Windows 8：** 按 Windows 键 + R 打开 **"运行**"对话框。 键入 *regedit.exe*，然后按 **Enter。**
   - **Windows 7：****单击"开始**"，*在regedit.exe* 键入"开始"，然后按 **Enter。**

3. 在注册表编辑器中，找到并单击以下注册表子项：

   ```console
   HKEY_CURRENT_USER\Software\Microsoft\Exchange\
   ```

4. 如果 *缺少 AlwaysUseMSOAuthForAutoDiscover* 项，请在"编辑"菜单上指向 **"新建** "，然后选择 **"DWORD 值"**。 键入 *AlwaysUseMSOAuthForAutoDiscover*，然后按 **Enter。**

5. 右键单击 *AlwaysUseMSOAuthForAutoDiscover*，然后单击修改 **。**

6. 在" **值数据** "框中， **键入 1**，然后单击"确定 **"。**

7. 在注册表编辑器中，找到并单击以下注册表子项：

   ```console
   HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Common\Identity\
   ```

8. 如果 *EnableADAL 和* *Version* 项已存在，请根据需要修改值，然后退出注册表编辑器。 如果没有，请在"编辑"菜单上指向" **新建** "，然后选择 **"DWORD 值** "以创建缺少的键。 

9. 例如，如果 *缺少 EnableADAL* 键，请键入 *EnableADAL*，然后按 **Enter。**

10. 右键单击 *"EnableADAL"*，然后单击"修改 **"。**

11. 在" **值数据** "框中， **键入 1**，然后单击"确定 **"。**

12. 如有必要，请对版本密钥执行相同的过程。 

13. **退出注册表编辑器。**

设置注册表项后，可以将 Office 2013 设备应用设置为将多重身份验证 ([MFA ](set-up-multi-factor-authentication.md)) 与 Microsoft 365。 
  
如果当前登录了任何客户端应用，需注销并重新登录以使更改生效。 否则，在建立标识之前，MRU 和漫游设置将不可用。
  
## <a name="disable-modern-authentication-on-devices"></a>在设备上禁用新式验证

若要在设备上禁用新式验证，请在设备上设置以下注册表项：

<br>

****

|注册表项|类型|值|
|:---|:---:|---:|
|HKEY_CURRENT_USER\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL|REG_DWORD|0|
|HKEY_CURRENT_USER\Software\Microsoft\Exchange\AlwaysUseMSOAuthForAutoDiscover|REG_DWORD|0|
   
## <a name="related-content"></a>相关内容

使用本文Office验证方法登录到 ([2013](https://support.microsoft.com/office/2b856342-170a-438e-9a4f-3c092394d3cb)) \
[Outlook提示输入密码，](/outlook/troubleshoot/authentication/outlook-prompt-password-modern-authentication-enabled)并且不使用新式验证连接到 Office 365 (文章) 
