---
title: Microsoft 托管桌面中的安全性
description: ''
keywords: Microsoft 托管桌面，Microsoft 365，服务，文档
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.date: 09/24/2018
ms.openlocfilehash: 8bfd71c4a143dee54ae006c8c54d711a8785480f
ms.sourcegitcommit: 2d664a95b9875f0775f0da44aca73b16a816e1c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/01/2020
ms.locfileid: "44470485"
---
# <a name="security-in-microsoft-managed-desktop"></a>Microsoft 托管桌面中的安全性

<!--Security, also Onboarding doc: data handling/store, privileged account access -->

Microsoft 托管桌面使用几种 Microsoft 技术来帮助保护受管理的设备和数据。 具体来说： 


- [设备安全性](#device-security)– Microsoft 托管桌面设备上的安全性和保护
- [标识和访问管理](#identity-and-access-management)-通过 Azure Active Directory 标识服务管理设备的安全使用
- [网络安全](#network-security)-VPN 信息和 Microsoft 托管桌面建议的解决方案和设置
- [信息安全性](#information-security)–可选的可用服务以进一步保护敏感信息 

有关 Microsoft 托管桌面使用的数据存储、使用情况和安全做法的信息，请下载我们的白皮书 [https://aka.ms/mmd-data](https://aka.ms/mmd-data) 。


## <a name="device-security"></a>设备安全性

Microsoft 托管桌面可确保所有托管设备都受到保护和保护，并使用以下服务尽早检测到威胁：

服务 | 说明
--- | ---
防病毒 | 已安装并配置 Microsoft Defender AV<br>Microsoft Defender AV 定义为最新
全卷加密 |    Windows BitLocker 是 Microsoft 托管桌面设备的卷加密解决方案。<br><br>在将组织载入到服务中后，将使用带有内置信任平台模块（TPM）的 Windows BitLocker 对设备进行加密，以防止在设备处于睡眠模式或关闭时对本地数据进行未经授权的访问。 
监控 |    Microsoft Defender 高级威胁防护（Microsoft Defender ATP）用于跨所有 Microsoft 托管桌面设备进行安全威胁监控。 Microsoft Defender ATP 允许企业客户检测、调查和响应公司网络中的高级威胁。 有关详细信息，请参阅[Microsoft Defender 高级威胁防护。](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection) 
操作系统更新 |  Microsoft 托管桌面设备始终使用最新的安全更新进行保护。
安全设备配置 |   Microsoft 托管桌面实现 Microsoft 安全基准。 有关详细信息，请参阅[Windows 安全基准。](https://docs.microsoft.com/windows/security/threat-protection/windows-security-baselines)



## <a name="identity-and-access-management"></a>标识和访问管理

标识和访问管理保护公司资产和业务关键型数据。 Microsoft 托管桌面配置设备，以确保使用 Azure Active Directory （Azure AD）托管标识进行安全的使用。 客户应负责在 Azure AD 租户中维护准确的信息。 

服务 | 说明
--- | ---
生物识别身份验证 |  Windows Hello 允许用户使用其面孔或 PIN 进行登录，使密码更难遗忘或盗取。 客户负责为其本地 Active Directory 实施必要的先决条件，以在混合配置中使用此服务。 有关详细信息，请参阅[Windows Hello。](https://docs.microsoft.com/windows-hardware/design/device-experiences/windows-hello) 
标准用户权限 |  为了保护系统并使其更安全，将为用户分配标准用户权限。 这是作为 Windows Autopilot 的现成体验的一部分分配的。



## <a name="network-security"></a>网络安全

客户负责网络安全性。 

服务 | 说明
--- | ---
VPN | 客户拥有自己的 VPN 基础结构，以确保有限的公司资源可以在 intranet 外部公开。<br><br>最低要求： Microsoft 托管桌面需要 Windows 10 兼容且受支持的 VPN 解决方案。 如果你的组织需要 VPN 解决方案，则需要支持 Windows 10 并通过 Intune 打包和部署。 有关详细信息，请与软件发布者联系。<br><br>提出<br>-Microsoft 推荐了一个新式 VPN 解决方案，可以通过 Intune 轻松部署到推送 VPN 配置文件。 这提供了访问企业网络的永不间断、无缝、可靠且安全的方式。 有关详细信息，请参阅[[Intune 中的 VPN 设置]](https://docs.microsoft.com/intune/vpn-settings-configure)。<br>-使用 Microsoft 托管桌面时，Microsoft 不建议使用较厚的 VPN 客户端或旧版 VPN 客户端，因为这会影响最终用户环境。<br>-Microsoft 建议传出的 web 流量直接转到 Internet，而无需通过 VPN 即可避免任何性能问题。<br>-理想情况下，Microsoft 建议使用 Azure Active Directory 应用程序代理，而不是 VPN。


## <a name="information-security"></a>信息安全

您可以配置这些可选的服务，以帮助保护公司的高价值资产。 

服务 | 说明
--- | ---
数据恢复  | 将设备上的关键文件夹中存储的信息备份到 OneDrive for business。 Microsoft 托管桌面不负责未与 OneDrive for Business 同步的数据。 
Windows 信息保护 |    对于需要高级别信息安全的公司，我们建议[Windows 信息保护](https://docs.microsoft.com/windows/threat-protection/windows-information-protection/protect-enterprise-data-using-wip)和[Azure 信息保护。](https://www.microsoft.com/cloud-platform/azure-information-protection)。 

