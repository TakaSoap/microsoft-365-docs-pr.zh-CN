---
title: Microsoft 托管桌面技术
description: 本文列出了 Microsoft 托管桌面中使用的技术和应用。
keywords: Microsoft 托管桌面, Microsoft 365, 服务, 文档
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: cb368939e87ddbbfc8f5386c6fc5d6bff110a7ec
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/13/2021
ms.locfileid: "49840897"
---
# <a name="microsoft-managed-desktop-technologies"></a>Microsoft 托管桌面技术

本文列出了 Microsoft 托管桌面中使用的技术和应用。

<!-- Microsoft 365 E5; Device as a Service -->
<!-- in O365 table, standard suite, removed this sentence "Please see the Installation of Project/Visio 64bit Click to Run Addendum for important deployment instructions. -->

所有 Microsoft 托管桌面用户都需要 Microsoft 365 企业版许可。 有关服务的许可要求详细信息，请参阅["Microsoft 托管桌面的先决条件"。](../get-ready/prerequisites.md)

本文总结了所需企业版许可证中包含的组件，并介绍了该服务如何将每个组件与 Microsoft 托管桌面设备一同使用。 Microsoft 托管桌面文档中详细介绍了每个区域的特定角色和职责。 

## <a name="office-365-e3-or-e5"></a>Office 365 E3 或 E5
 |
 --- | ---
Microsoft 365 企业应用版 (64 位)  | 这些 Office 应用程序将随设备一起提供：Word、Excel、PowerPoint、Outlook、Publisher、Access、Skype for Business、OneNote。<br><br>不包括 64 位完整版本的 Microsoft Project 和 Microsoft Visio。 但是，由于这些应用程序的安装取决于 Microsoft 365 企业应用版安装，因此 Microsoft 托管桌面已创建默认的 Microsoft Intune 部署和安全组，然后可以使用它们向许可用户部署这些应用程序。 有关详细信息，请参阅在 Microsoft 托管桌面设备上安装 Microsoft Project 或[Microsoft Visio。](../get-started/project-visio.md)
OneDrive |当用户首次登录 OneDrive 时，会为用户启用 Azure Active Directory 单一登录。<br><br>包含"桌面"、"文档"和"图片"文件夹的已知文件夹重定向;由 Microsoft 托管桌面启用和配置。
应用商店应用 |    Microsoft Sway 和 Power BI 未随设备一起提供。 这些应用可从 Microsoft Store 下载。
Win32 应用程序 |    Teams 不是随设备一起提供的，而是由 Microsoft 为 Microsoft 托管桌面设备打包和提供。 Azure 信息保护客户端未随设备一起提供，但你可以打包它进行部署。
Web 应用程序 |  Yammer、浏览器中的 Office、Delve、Flow、StaffHub、PowerApps 和 Planner 未随设备一起提供。 用户可以使用浏览器访问这些应用程序的 Web 版本。


## <a name="windows-10-enterprise-e5-or-e3-with-microsoft-defender-for-endpoint"></a>带 Microsoft Defender for Endpoint 的 Windows 10 企业版 E5 或 E3

 |
 --- | ---
Application Virtualization (App-V)  |    客户可以使用 Intune Win32 应用管理客户端部署 App-V 程序包。
Microsoft Defender for Endpoint |    Microsoft 托管桌面使用此产品监视设备安全。 

## <a name="enterprise-mobility--security-e5"></a>企业移动性 + 安全性 E5

 |
 --- | ---
企业移动性 + 安全性 E3<br>Azure Active Directory Premium P2 |    可以使用企业移动性 + 安全性 E3 和 Azure Active Directory Premium P2 的所有功能来管理 MDM 设备。
Microsoft Cloud App Security |  可以将此可选功能与 Microsoft 托管桌面一同使用。
Azure 信息保护 P2  | 可以将此可选功能与 Microsoft 托管桌面一同使用。
