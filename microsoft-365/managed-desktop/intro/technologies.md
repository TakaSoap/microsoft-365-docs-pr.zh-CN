---
title: Microsoft 托管桌面技术
description: 本主题列出了 Microsoft 托管桌面中使用的技术和应用。
keywords: Microsoft 托管桌面，Microsoft 365，服务，文档
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 8a86220e7fcfe4c2e788b28842c77d238d98fda4
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/21/2020
ms.locfileid: "43636192"
---
# <a name="microsoft-managed-desktop-technologies"></a>Microsoft 托管桌面技术

本主题列出了 Microsoft 托管桌面中使用的技术和应用。

<!-- Microsoft 365 E5; Device as a Service -->
<!-- in O365 table, standard suite, removed this sentence "Please see the Installation of Project/Visio 64bit Click to Run Addendum for important deployment instructions. -->

所有 Microsoft 托管桌面用户都需要 microsoft 365 企业版许可。 有关服务的许可要求的详细信息，请参阅[Microsoft 托管桌面的先决条件](../get-ready/prerequisites.md)。

本主题汇总了所需的企业许可证中包含的组件，并介绍了服务如何将每个组件与 Microsoft 托管桌面设备一起使用。 Microsoft 托管桌面文档中详细介绍了每个领域的具体角色和职责。 

## <a name="office-365-e3-or-e5"></a>Office 365 E3 或 E5
 |
 --- | ---
适用于企业的 Microsoft 365 应用（64位） | 这些 Office 应用程序将随设备一起提供： Word、Excel、PowerPoint、Outlook、Publisher、Access、Skype for Business、OneNote。<br><br>Microsoft Project 和 Microsoft Visio 的64位完整版本不包含在内。 但是，由于安装这些应用程序取决于 Microsoft 365 Apps for enterprise 安装，Microsoft 托管桌面创建了默认的 Microsoft Intune 部署和安全组，然后可以使用这些部署和安全组将这些应用程序部署到许可的最终用户。 有关详细信息，请参阅[在 Microsoft 托管桌面设备上安装 Microsoft Project 或 Microsoft Visio](../get-started/project-visio.md)。
OneDrive for Business |在首次登录 OneDrive for Business 时，将为最终用户启用 Azure Active Directory 单一登录。<br><br>包含 "桌面"、"文档" 和 "图片" 文件夹的 "已知文件夹重定向"。由 Microsoft 托管桌面启用和配置。 
应用商店应用 |    Microsoft Sway 和 Power BI 不随设备一起提供。 这些应用程序可从 Microsoft Store 下载。
Win32 应用程序 |    团队不随设备一起提供，但会打包并由 Microsoft 为 Microsoft 托管桌面设备提供。 Azure 信息保护客户端不随设备附带，但可以将其打包以进行部署。 
Web 应用程序 |  Yammer、Office 在浏览器、Delve、流、StaffHub、PowerApps 和计划器中不随设备一起附带。 用户可以通过浏览器访问这些应用程序的 web 版本。


## <a name="windows-10-enterprise-e3-or-e5"></a>Windows 10 企业版 E3 或 E5

 |
 --- | ---
Application Virtualization （app-v） |    客户可以使用 Intune Win32 应用管理客户端部署 App-v 程序包。
Microsoft Defender 高级威胁防护 |  Microsoft 托管桌面使用此来监视设备安全性。 

## <a name="enterprise-mobility--security-e5"></a>企业移动性 + 安全性 E5

 |
 --- | ---
企业移动性 + 安全 E3<br>Azure Active Directory Premium P2 |    您可以使用企业移动性 + 安全 E3 和 Azure Active Directory 高级 P2 的所有功能来管理 MDM 设备。
Microsoft Cloud App Security |  可以将此可选功能与 Microsoft 托管桌面结合使用。
Azure 信息保护 P2  | 可以将此可选功能与 Microsoft 托管桌面结合使用。
