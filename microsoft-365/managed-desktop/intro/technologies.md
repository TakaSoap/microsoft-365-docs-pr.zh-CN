---
title: Microsoft 托管桌面技术
description: 本文列出了本文中使用的技术和Microsoft 托管桌面。
keywords: Microsoft 托管桌面, Microsoft 365, 服务, 文档
ms.service: m365-md
author: jaimeo
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 167c518231b62251637e3deb89fd6a753664af85
ms.sourcegitcommit: 1ef176c79a0e6dbb51834fe30807409d4e94847c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/19/2021
ms.locfileid: "61110339"
---
# <a name="microsoft-managed-desktop-technologies"></a>Microsoft 托管桌面技术

本文列出了本文中使用的技术和Microsoft 托管桌面。

<!-- Microsoft 365 E5; Device as a Service -->
<!-- in O365 table, standard suite, removed this sentence "Please see the Installation of Project/Visio 64bit Click to Run Addendum for important deployment instructions. -->

Microsoft 365 企业版所有用户都需要Microsoft 托管桌面许可。 有关服务的许可要求详细信息，请参阅S [prerequisites for Microsoft 托管桌面](../get-ready/prerequisites.md)。

本文总结了必需许可证中包含的组件Enterprise，并介绍了该服务如何将每个组件与Microsoft 托管桌面一起使用。 本文档详细介绍了每个区域的特定角色Microsoft 托管桌面职责。 

## <a name="office-365-e3-or-e5"></a>Office 365 E3 或 E5

| 产品 |信息 |
--- |--- 
Microsoft 365 企业应用版 (64 位)  | 这些设备Office以下应用程序：Word、Excel、PowerPoint、Outlook、Publisher、Access、Skype for Business、OneNote。<br><br>不包括 64 位完整版本的 Microsoft Project 和 Microsoft Visio。 但是，由于这些应用程序的安装取决于 Microsoft 365 企业应用版 安装，Microsoft 托管桌面 已创建默认的 Microsoft Intune 部署和安全组，然后可以使用它们向许可用户部署这些应用程序。 有关详细信息，请参阅 Install [Microsoft Project or Microsoft Visio on Microsoft 托管桌面 devices](../get-started/project-visio.md)。
OneDrive |Azure Active Directory首次登录用户时，会为用户启用单一OneDrive。<br><br>包含"桌面"、"文档"和"图片"文件夹的已知文件夹重定向;启用和配置Microsoft 托管桌面。
应用商店应用 | Microsoft Sway Power BI未随设备一起提供。 可从以下网站下载这些Microsoft Store。
Win32 应用程序 | Teams未随设备一起提供，但由 Microsoft 打包并Microsoft 托管桌面设备。 Azure 信息保护客户端未随设备一起提供，但你可以打包它进行部署。
Web 应用程序 | Yammer Office，Delve、Flow、StaffHub、Power Apps 和 Planner 不会随设备一起附带。 用户可以使用浏览器访问这些应用程序的 Web 版本。

## <a name="windows-10-enterprise-e5-or-e3-with-microsoft-defender-for-endpoint"></a>Windows 10 企业版 Microsoft Defender for Endpoint 配置 E5 或 E3

建议 IT 管理员配置以下设置。 这些设置不作为自定义设置的一部分包含或Microsoft 托管桌面。

产品  |信息
--- | ---
Windows Hello 企业版 | 应实现 Windows Hello for Business，以将密码替换为适用于Microsoft 托管桌面身份验证。 有关详细信息，请参阅 Windows Hello [for Business。](/windows/security/identity-protection/hello-for-business/hello-identity-verification)
应用程序虚拟化 | 可以使用 Intune Win32 应用 (客户端将 Application Virtualization) App-V 部署包。 有关详细信息，请参阅[Application Virtualization。](/windows/application-management/app-v/appv-technical-reference)
Microsoft 365数据丢失防护 | 应实施Microsoft 365数据丢失防护，以监视对已确定为敏感的项目采取的操作，并帮助防止意外共享这些项目。 有关详细信息，请参阅Microsoft 365[数据丢失防护](../../compliance/endpoint-dlp-learn-about.md)。

作为功能的一部分包含和管理的功能Microsoft 托管桌面：

产品 |信息
--- |---
BitLocker 驱动器加密 | BitLocker 驱动器加密用于加密所有系统驱动器。 有关详细信息，请参阅 [BitLocker 驱动器加密](/windows/security/information-protection/bitlocker/bitlocker-overview)。
Windows Defender System Guard | 在启动时保护系统的完整性并验证系统完整性是否得到真正维护。 有关详细信息，请参阅 Windows Defender [System Guard。](/windows/security/threat-protection/windows-defender-system-guard/system-guard-how-hardware-based-root-of-trust-helps-protect-windows)
Windows Defender Credential Guard | Windows Defender Credential Guard 使用基于虚拟化的安全性来隔离密钥，以便只有特权系统软件才能访问它们。 有关详细信息，请参阅 Windows Defender [System Guard。](/windows/security/threat-protection/windows-defender-system-guard/system-guard-how-hardware-based-root-of-trust-helps-protect-windows)
适用于终结点的 Microsoft Defender - 终结点检测和响应 | Microsoft 托管桌面安全操作响应警报，并采取措施使用终结点检测和响应来修正威胁。 有关详细信息，请参阅 [Microsoft Defender for Endpoint - 终结点检测和响应](/windows/security/threat-protection/microsoft-defender-atp/overview-endpoint-detection-response)。
Microsoft Defender for Endpoint - 威胁专家 | Microsoft 托管桌面目标攻击通知与威胁专家见解和数据集成。 在启用此服务之前，您必须提供额外同意。 有关详细信息，请参阅 [Microsoft Defender for Endpoint - 威胁专家](/windows/security/threat-protection/microsoft-defender-atp/microsoft-threat-experts)。
Microsoft Defender for Endpoint - 威胁和漏洞管理 | 在服务计划中供将来Microsoft 托管桌面必需。 有关详细信息，请参阅 [Microsoft Defender for Endpoint - 威胁和漏洞管理](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)。
Microsoft Defender for Endpoint - 攻击面减少 | 攻击面减少针对经常被攻击者滥用的风险软件行为。 有关详细信息，请参阅 [Microsoft Defender for Endpoint - 攻击面减少](/windows/security/threat-protection/microsoft-defender-atp/attack-surface-reduction)。
Microsoft Defender for Endpoint - Exploit Protection | 通过自动将攻击缓解技术应用于操作系统进程和应用，抵御使用攻击感染设备和传播的恶意软件。 有关详细信息，请参阅适用于终结点 [的 Microsoft Defender - Exploit Protection](/windows/security/threat-protection/microsoft-defender-atp/exploit-protection)。
Microsoft Defender for Endpoint - 网络保护 | 网络保护扩展了Microsoft Defender SmartScreen以阻止所有尝试连接到低信誉源的出站 HTTP 和 HTTPS 流量。 有关详细信息，请参阅 [Microsoft Defender for Endpoint - 网络保护](/windows/security/threat-protection/microsoft-defender-atp/network-protection)。
Microsoft Defender 防篡改保护 | Windows防篡改保护功能用于防止更改安全设置（如防病毒）。 有关详细信息，请参阅 [Microsoft Defender 防篡改保护](/windows/security/threat-protection/microsoft-defender-antivirus/prevent-changes-to-security-settings-with-tamper-protection)。
Microsoft Defender 防病毒基于行为、启发式和实时防病毒保护 | 始终在扫描可能无法检测为恶意软件的文件和进程威胁。 有关详细信息，请参阅Microsoft Defender 防病毒行为、启发式和[实时防病毒保护](../../security/defender-endpoint/microsoft-defender-antivirus-in-windows-10.md)。
Microsoft Defender 防病毒云保护 | 提供针对新威胁和新兴威胁的动态即时自动化保护。 有关详细信息，请参阅云Microsoft Defender 防病毒[保护。](/windows/security/threat-protection/microsoft-defender-antivirus/utilize-microsoft-cloud-protection-microsoft-defender-antivirus)
Microsoft Defender for Endpoint - "首次看到时阻止" | 在检测到可疑或未知文件时Windows检测并阻止新恶意软件。 有关详细信息，请参阅 [Microsoft Defender for Endpoint - 首次看到时阻止](/windows/security/threat-protection/microsoft-defender-antivirus/configure-block-at-first-sight-microsoft-defender-antivirus)。
Microsoft Defender 防病毒可能不需要的应用程序 | 可能不需要的应用程序用于阻止可能导致你的计算机运行缓慢、显示意外广告的应用，或者最差时安装可能意外或不需要的其他软件。 有关详细信息，请参阅Microsoft Defender 防病毒[可能不需要的应用程序](/windows/security/threat-protection/microsoft-defender-antivirus/detect-block-potentially-unwanted-apps-microsoft-defender-antivirus)。
Windows Defender高级安全防火墙 | 基于主机的、针对设备的双向网络流量筛选，Windows Defender防火墙阻止未经授权的网络流量流入或流出本地设备。 有关详细信息，请参阅高级[Windows Defender防火墙](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security)。
用户帐户控制 | 当任务或操作需要管理员帐户类型访问权限时，用户帐户控制将切换到安全桌面。 Microsoft 托管桌面注册时为用户分配标准用户访问权限。 有关详细信息，请参阅 [用户帐户控制](/windows/security/identity-protection/user-account-control/how-user-account-control-works)。


## <a name="enterprise-mobility--security-e5"></a>企业移动性 + 安全性 E5

产品 |信息
 --- | ---
企业移动性 + 安全性 E3<br>Azure Active Directory Premium P2 | 可以使用 mdm 设备的所有企业移动性 + 安全性 E3管理 MDM 设备。 可以将Azure Active Directory Premium P2作为可选功能与Microsoft 托管桌面。
Microsoft Defender for Cloud Apps | 可以将此可选功能与 Microsoft 托管桌面。
Azure 信息保护 P2  | 可以将此可选功能与 Microsoft 托管桌面。
