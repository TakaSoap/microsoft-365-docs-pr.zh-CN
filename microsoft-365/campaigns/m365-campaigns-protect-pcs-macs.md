---
title: 保护非托管 Windows 10 电脑和 Mac
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
- M365-Campaigns
- m365solution-smb
ms.custom:
- Adm_O365
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
description: 使用 Microsoft 365 保护 BYOD (非托管) 自带设备。
ms.openlocfilehash: 5c27b29b5bb4fb445655e671d8c654ad8e9abc6b
ms.sourcegitcommit: 1b30ac6e05906c8a014b1fed33fc71e1821f6ad2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2021
ms.locfileid: "50044380"
---
# <a name="protect-unmanaged-windows-10-pcs-and-macs"></a>保护非托管 Windows 10 电脑和 Mac

可以通过在 Microsoft Intune 中注册 Windows 10 电脑和 Mac 来管理它们，这允许你在访问环境中的数据之前确保它们正常运行和安全。 但是，许多市场活动和小型企业都包括自带设备办公 (BYOD) ，这将不由组织管理。 对于这些非托管电脑和 Mac，请使用本文确保配置最低安全性功能。

<!--A Windows 10 PC is considered managed after you have completed the following two steps:

1. You (or the admin) set up device and data protection policies in the [setup  wizard](../business/set-up.md).

2. You have [connected your computer to Azure Active Directory](../business/set-up-windows-devices.md) and use your Microsoft 365 username and password to sign in.
3. --> 

## <a name="protect-a-computer-running-windows-10-or-a-mac"></a>保护运行 Windows 10 或 Mac 的计算机

<!--If you have a PC that is running Windows 10 that is not connected to Microsoft 365, or a Mac, the Microsoft 365 protections do not apply to it, but here are some things you can do to keep your data secure on these devices as well:
-->
如果你的 Windows 10 电脑或 Mac 不是由你的组织管理的，请确保配置这些安全功能。

## <a name="windows-10"></a>[Windows 10](#tab/Windows10)

**打开设备加密**<p>

设备加密可在各种 Windows 设备上使用，并且有助于通过加密数据来保护数据。 如果启用设备加密，则只有经过授权的个人才能访问你的设备和数据。 有关 [说明，请参阅"打开设备](https://support.microsoft.com/help/4028713/windows-10-turn-on-device-encryption) 加密"。

 如果设备加密在你的设备上不可用，你可以改为启用标准 [BitLocker](https://support.microsoft.com/help/4028713/windows-10-turn-on-device-encryption) 加密。  (BitLocker 在 Windows 10 家庭版.)  

**使用 Windows 安全保护设备**<p>
如果你拥有 Windows 10，你将使用 Windows 安全版获得最新的防病毒保护。 首次启动 Windows 10 时，Windows 安全将打开并主动帮助保护电脑，通过扫描恶意软件 (恶意软件) 、病毒和安全威胁。 Windows 安全机制使用实时保护扫描你在电脑上下载或运行的所有内容。

Windows 更新网站会自动下载 Windows 安全的更新，以帮助保护电脑的安全，防止其遭到威胁。

如果你拥有早期版本的 Windows 并且正在使用Microsoft Security Essentials，则建议移动到 Windows 安全。 有关详细信息，请参阅 Windows [安全帮助保护我的设备](https://support.microsoft.com/help/17464/windows-10-help-protect-my-device-with-windows-security)。

**打开 Windows 防火墙**<p>
即使已打开另一个防火墙，也应始终运行 Windows 防火墙。 如果具有一个 (防火墙，则关闭 Windows 防火墙可能会让设备) 受到未经授权的访问。 有关 [说明，请参阅"打开或关闭 Windows](https://support.microsoft.com/help/4028544/windows-10-turn-windows-defender-firewall-on-or-off) 防火墙"

## <a name="mac"></a>[Mac](#tab/Mac)

**使用 FileVault 加密 Mac 磁盘**<p>
磁盘加密在设备丢失或被盗时保护数据。 FileVault 全磁盘加密有助于防止未经授权访问启动磁盘上的信息。 有关 [说明，请参阅使用 FileVault](https://support.apple.com/HT204837) 加密 Mac 上的启动磁盘。

**保护 Mac 免受恶意软件的攻击**<p>
Microsoft 建议在 Mac 上安装和使用可靠的防病毒软件。 有关选项列表，请参阅以下文章[：Best Mac 防病毒 2019。 ](https://www.macworld.co.uk/feature/mac-software/mac-antivirus-3672182/)

您还可以通过使用仅来自可靠来源的软件来降低恶意软件的风险。 安全与&首选项中的设置允许你指定安装在 Mac 上的软件源。 有关详细信息，请参阅保护 [Mac 免受恶意软件的攻击](https://support.apple.com/kb/PH25087)。

**打开防火墙保护**<p>
在连接到 Internet 或网络时，使用防火墙设置保护 Mac 免受其他计算机启动的不需要的联系人的干扰。 如果没有此保护，Mac 可能更容易受到未经授权的访问。 有关 [应用程序防火墙的说明，](https://support.apple.com/HT201642) 请参阅。
