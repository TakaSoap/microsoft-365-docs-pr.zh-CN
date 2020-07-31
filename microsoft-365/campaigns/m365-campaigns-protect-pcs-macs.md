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
description: 针对针对市场活动的 Microsoft 365 防御网络钓鱼和其他攻击。
ms.openlocfilehash: 3e0c6a52209c56e75c6ff1210f26e6926e4d7d32
ms.sourcegitcommit: 6501e01a9ab131205a3eef910e6cea7f65b3f010
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/30/2020
ms.locfileid: "46527134"
---
# <a name="protect-unmanaged-windows-10-pcs-and-macs"></a>保护非托管 Windows 10 电脑和 Mac

你可以通过在 Microsoft Intune 中注册 Windows 10 电脑和 Mac 来管理这些电脑和 Mac，这使你能够在访问环境中的数据之前确保它们处于健康和安全状态。 但是，许多市场活动和小型公司都包含了自己的设备（byod）的人员，这些设备不会由组织管理。 对于这些非托管电脑和 Mac，请使用本文以确保配置最低安全功能。 

<!--A Windows 10 PC is considered managed after you have completed the following two steps:

1. You (or the admin) set up device and data protection policies in the [setup  wizard](../business/set-up.md).

2. You have [connected your computer to Azure Active Directory](../business/set-up-windows-devices.md) and use your Microsoft 365 username and password to sign in.
3. --> 

## <a name="protect-a-computer-running-windows-10-or-a-mac"></a>保护运行 Windows 10 或 Mac 的计算机

<!--If you have a PC that is running Windows 10 that is not connected to Microsoft 365, or a Mac, the Microsoft 365 protections do not apply to it, but here are some things you can do to keep your data secure on these devices as well:
-->
如果你的 Windows 10 电脑或 Mac 不受你的组织的管理，请确保配置这些安全功能。

## <a name="windows-10"></a>[Windows 10](#tab/Windows10)
**启用设备加密**<p>

设备加密在广泛的 Windows 设备上可用，并通过对其加密来帮助保护您的数据。 如果打开设备加密，只有经过授权的个人才能访问您的设备和数据。 有关说明，请参阅[打开设备加密](https://support.microsoft.com/help/4028713/windows-10-turn-on-device-encryption)。

 如果设备加密在设备上不可用，则可以改为打开标准[BitLocker 加密](https://support.microsoft.com/help/4028713/windows-10-turn-on-device-encryption)。 （BitLocker 在 Windows 10 家庭版中不可用。） 


**使用 Windows 安全保护你的设备**<p>
如果你有 Windows 10，你将获得最新的使用 Windows 安全的防病毒保护。 当您首次启动 Windows 10 时，Windows 安全处于打开状态，并通过扫描恶意软件（恶意软件）、病毒和安全威胁来主动帮助保护你的电脑。 Windows 安全使用实时保护来扫描您在电脑上下载或运行的所有内容。

Windows 更新会自动下载 Windows 安全更新，以帮助确保你的电脑安全并保护其免受威胁的侵扰。

如果你具有早期版本的 Windows 且正在使用 Microsoft 安全概要，最好移动到 Windows 安全。 有关详细信息，请参阅[帮助保护我的设备和 Windows 安全](https://support.microsoft.com/help/17464/windows-10-help-protect-my-device-with-windows-security)。

**启用 Windows 防火墙**<p>
即使已打开另一个防火墙，也应始终运行 Windows 防火墙。 关闭 Windows 防火墙可能会使你的设备（如果你的网络可用）更容易受到未经授权的访问。 请参阅[打开或关闭 Windows 防火墙](https://support.microsoft.com/help/4028544/windows-10-turn-windows-defender-firewall-on-or-off)获取说明

## <a name="mac"></a>[Mac](#tab/Mac)
**使用 FileVault 对您的 Mac 磁盘进行加密**<p>
磁盘加密可在设备丢失或被盗时保护数据。 FileVault 的完整磁盘加密有助于防止对您的启动磁盘上的信息进行未经授权的访问。 有关说明，请参阅[使用 FileVault 对 Mac 上的启动盘进行加密](https://support.apple.com/HT204837)。

**保护 mac 免受恶意软件的攻击**<p>
Microsoft 建议您在 Mac 上安装和使用可靠的防病毒软件。 请参阅以下文章，获取选项列表：[最佳 Mac 防病毒 2019 ](https://www.macworld.co.uk/feature/mac-software/mac-antivirus-3672182/)。

您还可以使用仅来自可靠来源的软件来降低恶意软件的风险。 Security & 隐私首选项中的设置允许您指定 Mac 上安装的软件的来源。 有关详细信息，请参阅[保护 Mac 免受恶意软件的攻击](https://support.apple.com/kb/PH25087)。

**启用防火墙保护**<p>
在连接到 Internet 或网络时，使用防火墙设置来保护 Mac 免受其他计算机启动的不需要的联系人的阻止。 如果没有此保护，你的 Mac 可能更容易受到未经授权的访问。 有关说明，请参阅[关于应用程序防火墙](https://support.apple.com/HT201642)。
