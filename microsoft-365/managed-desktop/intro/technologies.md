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
ms.openlocfilehash: 4932a40455c8ed4d8fdfc0dfae99c8001e582ff4
ms.sourcegitcommit: c0cfb9b354db56fdd329aec2a89a9b2cf160c4b0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/03/2021
ms.locfileid: "50094863"
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
建议
 |
 --- | ---
[Windows Hello 企业版](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-identity-verification) | 建议客户实现 Windows Hello 企业版，将密码替换为 Microsoft 托管桌面设备上使用的强双因素身份验证。
[应用程序虚拟化](https://docs.microsoft.com/windows/application-management/app-v/appv-technical-reference) | 客户可以使用 Intune Win32 (客户端) App-V 应用程序包部署 Application Virtualization。
[Microsoft 365 数据丢失防护](https://docs.microsoft.com/microsoft-365/compliance/endpoint-dlp-learn-about) | 建议客户实施 Microsoft 365 数据丢失防护 (DLP) ，以监视对已确定为敏感的项目采取的操作，并帮助防止意外共享这些项目。   

包含在服务中并进行管理
 |
 --- | ---
[BitLocker 驱动器加密](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-overview) | BitLocker 驱动器加密用于加密所有系统驱动器。 
[Windows Defender System Guard]( https://docs.microsoft.com/windows/security/threat-protection/windows-defender-system-guard/system-guard-how-hardware-based-root-of-trust-helps-protect-windows) | 在启动时保护系统的完整性并验证系统完整性是否确实得到维护。
[Windows Defender Credential Guard]( https://docs.microsoft.com/windows/security/identity-protection/credential-guard/credential-guard) | Windows Defender Credential Guard 使用基于虚拟化的安全性来隔离密钥，以便只有特权系统软件才能访问它们。
[Microsoft Defender for Endpoint | 终结点检测和响应] (https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/overview-endpoint-detection-response) |     Microsoft 托管桌面安全操作响应警报，并采取操作以使用终结点检测和响应修正威胁。
[Microsoft Defender for Endpoint | 威胁专家] (https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-threat-experts) | Microsoft 托管桌面通过目标攻击通知与威胁专家见解和数据集成。 在启用此服务之前，客户需要提供其他同意。  
[Microsoft Defender for Endpoint | 威胁和漏洞管理] (https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) | 将来在 Microsoft 托管桌面服务计划中使用时需要。
[Microsoft Defender for Endpoint | 攻击面减少] (https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/attack-surface-reduction) | 攻击面减少面向经常被攻击者滥用的风险软件行为。
[Microsoft Defender for Endpoint | Exploit Protection] (https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/exploit-protection) | 通过自动将攻击缓解技术应用于操作系统进程和应用，抵御使用攻击感染设备和传播的恶意软件。
[Microsoft Defender for Endpoint | Network Protection] (https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/network-protection) | 网络保护扩展了 Microsoft Defender SmartScreen 的范围，以阻止所有尝试 (低信誉) 的出站 HTTP 流量。
[Microsoft Defender 防篡改保护](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/prevent-changes-to-security-settings-with-tamper-protection) | Windows 防篡改保护用于防止更改安全设置，如防病毒保护。
[基于 Microsoft Defender 防病毒行为的启发式实时防病毒保护]( https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10) | 始终在扫描可能无法被检测为恶意软件的文件和进程威胁。
[Microsoft Defender 防病毒云提供的保护](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/utilize-microsoft-cloud-protection-microsoft-defender-antivirus) | 提供针对新威胁和新兴威胁的动态近即时自动保护。
[首次看到时 Microsoft Defender 阻止](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-block-at-first-sight-microsoft-defender-antivirus) | 当 Windows 检测到可疑或未知文件时，提供检测并阻止新恶意软件。
[Microsoft Defender AV 可能不需要的应用程序](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/detect-block-potentially-unwanted-apps-microsoft-defender-antivirus) | PUA (可能不需要的应用程序) 阻止可能导致计算机运行缓慢、显示意外广告或最差情况下安装其他可能意外或不需要的软件的应用。
[Windows Defender高级安全防火墙](https://docs.microsoft.com/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security) | 基于主机的设备的双向网络流量筛选，Windows Defender防火墙阻止未经授权的网络流量流入或流出本地设备。
[用户帐户控制](https://docs.microsoft.com/windows/security/identity-protection/user-account-control/how-user-account-control-works) | 当任务或操作需要管理员帐户类型访问权限时，用户帐户控制将切换到安全桌面。 Microsoft 托管桌面用户在注册时分配有标准用户访问权限。 


## <a name="enterprise-mobility--security-e5"></a>企业移动性 + 安全性 E5

 |
 --- | ---
企业移动性 + 安全性 E3<br>Azure Active Directory Premium P2 |    可以使用企业移动性 + 安全性 E3 和 Azure Active Directory Premium P2 的所有功能来管理 MDM 设备。
Microsoft Cloud App Security |  可以将此可选功能与 Microsoft 托管桌面一同使用。
Azure 信息保护 P2  | 可以将此可选功能与 Microsoft 托管桌面一同使用。
