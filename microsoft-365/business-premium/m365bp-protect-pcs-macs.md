---
title: 保护非托管Windows 10电脑和 Mac Microsoft 365 商业高级版
f1.keywords:
- NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
ms.localizationpriority: medium
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
description: 使用移动设备保护 BYOD (非托管) 自带Microsoft 365 商业高级版。
ms.openlocfilehash: b3d783ba498337af7ff867fe749366abe1734da5
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/08/2022
ms.locfileid: "63330785"
---
# <a name="protect-unmanaged-windows-10-pcs-and-macs-in-microsoft-365-business-premium"></a>保护非托管Windows 10电脑和 Mac Microsoft 365 商业高级版

可以通过在 Microsoft Intune 中注册 Windows 10 和 Mac 来管理这些电脑和 Mac，这允许你在访问环境中的数据之前确保它们正常运行和安全。 但是，许多市场活动和小型企业都包括自带设备办公 (BYOD) ，这将不会由组织管理。 对于这些非托管电脑和 Mac，请使用本文确保配置最低安全性功能。

<!--A Windows 10 PC is considered managed after you have completed the following two steps:

1. You (or the admin) set up device and data protection policies in the [setup  wizard](../business/set-up.md).

2. You have [connected your computer to Azure Active Directory](../business/set-up-windows-devices.md) and use your Microsoft 365 username and password to sign in.
3. --> 

## <a name="protect-a-computer-running-windows-10-or-a-mac"></a>保护运行 Windows 10 Mac 的计算机

<!--If you have a PC that is running Windows 10 that is not connected to Microsoft 365, or a Mac, the Microsoft 365 protections do not apply to it, but here are some things you can do to keep your data secure on these devices as well:
-->
如果你Windows 10电脑或 Mac 不由你的组织管理，请确保配置这些安全功能。

## <a name="windows-10"></a>[Windows 10](#tab/Windows10)

**打开设备加密**<p>

设备加密适用于各种Windows设备，并且有助于通过加密数据来保护数据。 如果启用设备加密，则只有经过授权的个人才能访问你的设备和数据。 有关 [说明，请参阅打开设备](https://support.microsoft.com/help/4028713/windows-10-turn-on-device-encryption) 加密。

 如果设备加密在你的设备上不可用，你可以改为打开标准 [BitLocker](https://support.microsoft.com/help/4028713/windows-10-turn-on-device-encryption) 加密。  (BitLocker 在 Windows 10 家庭版 版本上)  

**使用安全保护Windows 安全中心**<p>
如果已Windows 10，你将使用最新防病毒Windows 安全中心。 首次启动Windows 10时，Windows 安全中心将打开并主动帮助保护电脑，通过扫描恶意软件 (恶意软件) 、病毒和安全威胁。 Windows 安全中心使用实时保护扫描你在电脑上下载或运行的所有内容。

Windows 更新网站会自动下载 Windows 安全的更新，以帮助保护电脑的安全，防止其遭到威胁。

如果你有早期版本的 Windows 并且正在使用Microsoft Security Essentials，则建议移动到 Windows 安全中心。 有关详细信息，请参阅使用帮助[保护我的设备Windows 安全中心](https://support.microsoft.com/help/17464/windows-10-help-protect-my-device-with-windows-security)。

**打开 Windows 防火墙**<p>
即使其他防火墙Windows，也应始终运行防火墙。 如果Windows防火墙， (和网络连接，) 未经授权访问。 有关[说明Windows打开或关闭防火墙](https://support.microsoft.com/help/4028544/windows-10-turn-windows-defender-firewall-on-or-off)。

## <a name="mac"></a>[Mac](#tab/Mac)

**使用 FileVault 加密 Mac 磁盘**<p>
磁盘加密在设备丢失或被盗时保护数据。 FileVault 全磁盘加密有助于防止对启动磁盘上的信息进行未经授权的访问。 有关 [说明，请参阅使用 FileVault 加密 Mac 上的启动](https://support.apple.com/HT204837) 磁盘。

**保护 Mac 免受恶意软件的攻击**<p>
Microsoft 建议在 Mac 上安装和使用可靠的防病毒软件。 有关选项列表，请参阅以下文章： [Best Mac antivirus 2019](https://www.macworld.co.uk/feature/mac-software/mac-antivirus-3672182/)。

您还可以通过使用仅来自可靠来源的软件来降低恶意软件的风险。 安全与&首选项中的设置允许你指定安装在 Mac 上的软件源。 有关详细信息，请参阅 [保护 Mac 免受恶意软件的攻击](https://support.apple.com/kb/PH25087)。

**打开防火墙保护**<p>
当连接到 Internet 或网络时，使用防火墙设置保护 Mac 免受其他计算机启动的不需要的联系人的干扰。 如果没有此保护，Mac 可能更容易受到未经授权的访问。 有关 [说明，请参阅有关应用程序](https://support.apple.com/HT201642) 防火墙。
