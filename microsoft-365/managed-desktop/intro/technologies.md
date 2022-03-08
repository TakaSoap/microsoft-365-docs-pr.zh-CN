---
title: Microsoft 托管桌面技术
description: 本文列出了本文中使用的技术和Microsoft 托管桌面。
keywords: Microsoft 托管桌面, Microsoft 365, 服务, 文档
ms.service: m365-md
author: tiaraquan
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
ms.author: tiaraquan
manager: dougeby
ms.topic: article
ms.openlocfilehash: 302666c6b29d2cffd4db641509f14ba616cfd459
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/08/2022
ms.locfileid: "63314961"
---
# <a name="microsoft-managed-desktop-technologies"></a>Microsoft 托管桌面技术

本文列出了本文中使用的技术和Microsoft 托管桌面。

<!-- Microsoft 365 E5; Device as a Service -->
<!-- in O365 table, standard suite, removed this sentence "Please see the Installation of Project/Visio 64bit Click to Run Addendum for important deployment instructions. -->

Microsoft 365 企业版所有用户都需要Microsoft 托管桌面许可。 有关服务的许可要求详细信息，请参阅系统必备[Microsoft 托管桌面](../get-ready/prerequisites.md)。

本文总结了必需许可证中包含的组件Enterprise，以及服务如何将每个组件与 Microsoft 托管桌面设备一起使用。 本文档详细介绍了每个区域的特定角色Microsoft 托管桌面职责。

## <a name="office-365-e3-or-e5"></a>Office 365 E3 或 E5

| 产品 | 信息 |
| ----- | ----- |
| Microsoft 365 企业应用版 (64 位)  | 设备Office以下应用程序：<br><ul><li>Word</li><li>Excel</li><li>PowerPoint</li><li>Outlook</li><li>Publisher</li><li>Access</li><li>Skype for Business</li><li>OneNote</li></ul><br>不包括 64 位完整版本的 Microsoft Project 和 Microsoft Visio。 但是，由于这些应用程序的安装取决于 Microsoft 365 应用版 for Enterprise 安装，Microsoft 托管桌面 创建了默认 Microsoft Intune 部署以及可用于将这些应用程序部署到许可用户的安全组。 有关详细信息，请参阅 Install [Microsoft Project or Microsoft Visio on Microsoft 托管桌面 devices](../get-started/project-visio.md)。 |
| OneDrive | Azure Active Directory首次登录用户时，会为用户启用单一OneDrive。<br><br>包括桌面、文档和图片文件夹的已知文件夹重定向。 这些文件夹由用户启用和Microsoft 托管桌面。 |
| 应用商店应用 | Microsoft Sway Power BI未随设备一起提供。 可从以下版本下载这些Microsoft Store。 |
| Win32 应用程序 | Teams未随设备一起提供，但由 Microsoft 打包并Microsoft 托管桌面设备。 Azure 信息保护客户端未随设备一起提供，但你可以打包它进行部署。 |
| Web 应用程序 | 以下 Web 应用程序未随设备一起提供： <ul><li>Yammer</li><li>Office浏览器中显示</li><li>Delve</li><li>Flow</li><li>StaffHub</li><li>Power Apps</li><li>Planner</li></ul> <br>用户可以使用浏览器访问这些应用程序的 Web 版本。 |

## <a name="windows-10-enterprise-e5-or-e3-with-microsoft-defender-for-endpoint"></a>Windows 10 企业版 Microsoft Defender for Endpoint 配置 E5 或 E3

建议 IT 管理员配置以下设置。

> [!NOTE]
> 这些设置不作为自定义设置的一部分包含或Microsoft 托管桌面。

| 产品 | 信息 |
| ----- | ----- |
| Windows Hello 企业版 | 应实现 Windows Hello for Business，以将密码替换为适用于Microsoft 托管桌面身份验证。 有关详细信息，请参阅 Windows Hello [for Business](/windows/security/identity-protection/hello-for-business/hello-identity-verification)。 |
| 应用程序虚拟化 | 可以使用 Intune Win32 (客户端将 Application Virtualization) App-V 部署包。 有关详细信息，请参阅 [Application Virtualization](/windows/application-management/app-v/appv-technical-reference)。 |
| Microsoft 365数据丢失防护 | 应实施Microsoft 365数据丢失防护，以监视对已确定为敏感的项目采取的操作，并帮助防止意外共享这些项目。 有关详细信息，请参阅Microsoft 365[数据丢失防护](../../compliance/endpoint-dlp-learn-about.md)。 |

作为功能的一部分包含和管理的功能Microsoft 托管桌面：

| 产品 | 信息 |
| ----- | ----- |
| BitLocker 驱动器加密 | BitLocker 驱动器加密用于加密所有系统驱动器。 有关详细信息，请参阅 [BitLocker 驱动器加密](/windows/security/information-protection/bitlocker/bitlocker-overview)。 |
| Windows Defender System Guard | 在启动时保护系统的完整性，并验证系统完整性是否得到真正维护。 有关详细信息，请参阅 Windows Defender [System Guard](/windows/security/threat-protection/windows-defender-system-guard/system-guard-how-hardware-based-root-of-trust-helps-protect-windows)。 |
| Windows Defender Credential Guard | Windows Defender Credential Guard 使用基于虚拟化的安全性来隔离密钥，以便只有特权系统软件才能访问它们。 有关详细信息，请参阅 Windows Defender [System Guard](/windows/security/threat-protection/windows-defender-system-guard/system-guard-how-hardware-based-root-of-trust-helps-protect-windows)。 |
| 适用于终结点的 Microsoft Defender - 终结点检测和响应 | Microsoft 托管桌面安全操作响应警报，并采取措施使用终结点检测和响应来修正威胁。 有关详细信息，请参阅 [Microsoft Defender for Endpoint - 终结点检测和响应](/windows/security/threat-protection/microsoft-defender-atp/overview-endpoint-detection-response)。 |
| Microsoft Defender for Endpoint - 威胁专家 | Microsoft 托管桌面目标攻击通知与威胁专家见解和数据集成。 在启用此服务之前，你必须提供其他同意。 有关详细信息，请参阅 [Microsoft Defender for Endpoint - 威胁专家](/windows/security/threat-protection/microsoft-defender-atp/microsoft-threat-experts)。 |
| Microsoft Defender for Endpoint - 威胁和漏洞管理 | 在服务计划中供将来Microsoft 托管桌面必需。 有关详细信息，请参阅 [Microsoft Defender for Endpoint - 威胁和漏洞管理](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)。 |
| Microsoft Defender for Endpoint - 攻击面减少 | 针对经常被攻击者滥用的风险软件行为。 有关详细信息，请参阅 [Microsoft Defender for Endpoint - 攻击面减少](/windows/security/threat-protection/microsoft-defender-atp/attack-surface-reduction)。 |
| Microsoft Defender for Endpoint - Exploit Protection | 通过自动将攻击缓解技术应用到操作系统进程和应用，防范使用攻击感染设备和传播的恶意软件。 有关详细信息，请参阅 [Microsoft Defender for Endpoint - Exploit Protection](/windows/security/threat-protection/microsoft-defender-atp/exploit-protection)。 |
| Microsoft Defender for Endpoint - 网络保护 | 扩展网站Microsoft Defender SmartScreen以阻止所有尝试连接到低信誉源的出站 HTTP 和 HTTPS 流量。 有关详细信息，请参阅 [Microsoft Defender for Endpoint - 网络保护](/windows/security/threat-protection/microsoft-defender-atp/network-protection)。 |
| Microsoft Defender 防篡改保护 | Windows防篡改保护功能用于防止更改安全设置，如防病毒保护。 有关详细信息，请参阅 [Microsoft Defender 防篡改保护](/windows/security/threat-protection/microsoft-defender-antivirus/prevent-changes-to-security-settings-with-tamper-protection)。 |
| Microsoft Defender 防病毒基于行为、启发式和实时防病毒保护 | 始终打开以扫描可能无法检测为恶意软件的文件和进程威胁。 有关详细信息，请参阅Microsoft Defender 防病毒行为、启发式和[实时防病毒保护](../../security/defender-endpoint/microsoft-defender-antivirus-in-windows-10.md)。 |
| Microsoft Defender 防病毒云保护 | 提供针对新威胁和新兴威胁的动态即时自动化保护。 有关详细信息，请参阅云Microsoft Defender 防病毒[保护](/windows/security/threat-protection/microsoft-defender-antivirus/utilize-microsoft-cloud-protection-microsoft-defender-antivirus)。 |
| Microsoft Defender for Endpoint - "首次看到时阻止" | 在检测到可疑或未知文件时Windows检测并阻止新恶意软件。 有关详细信息，请参阅 [Microsoft Defender for Endpoint - 首次看到时阻止](/windows/security/threat-protection/microsoft-defender-antivirus/configure-block-at-first-sight-microsoft-defender-antivirus)。 |
| Microsoft Defender 防病毒可能不需要的应用程序 | 用于阻止可能导致计算机运行缓慢、显示意外广告的应用，或者最差时安装可能意外或不需要的其他软件。 有关详细信息，请参阅Microsoft Defender 防病毒[不需要的应用程序](/windows/security/threat-protection/microsoft-defender-antivirus/detect-block-potentially-unwanted-apps-microsoft-defender-antivirus)。 |
| Windows Defender高级安全防火墙 | 基于主机的、针对设备的双向网络流量筛选，Windows Defender防火墙阻止未经授权的网络流量流入或流出本地设备。 有关详细信息，请参阅Windows Defender[高级安全防火墙](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security)。 |
| 用户帐户控制 | 当任务或操作需要管理员帐户类型访问权限时，用户帐户控制将切换到安全桌面。 Microsoft 托管桌面注册时为用户分配标准用户访问权限。 有关详细信息，请参阅 [用户帐户控制](/windows/security/identity-protection/user-account-control/how-user-account-control-works)。 |

## <a name="enterprise-mobility--security-e5"></a>企业移动性 + 安全性 E5

| 产品 | 信息 |
| ----- | ----- |
| 企业移动性 + 安全性 E3<br><br>Azure Active Directory Premium P2 | 可以使用 mdm 设备的所有企业移动性 + 安全性 E3管理 MDM 设备。<br><br>可以将Azure Active Directory Premium P2用作可选功能与Microsoft 托管桌面。 |
| Microsoft Defender for Cloud Apps | 可以将此可选功能与 Microsoft 托管桌面。
| Azure 信息保护 P2  | 可以将此可选功能与 Microsoft 托管桌面。
