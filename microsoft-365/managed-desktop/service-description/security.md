---
title: Microsoft 托管桌面中的安全技术
description: 用于设备安全、标识和访问管理、网络安全和信息安全的技术
keywords: Microsoft 托管桌面, Microsoft 365, 服务, 文档
ms.service: m365-md
author: jaimeo
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 5076ddca6053adc7cebb9599c8d82a42c7ab5a63
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/13/2021
ms.locfileid: "49840909"
---
# <a name="security-technologies-in-microsoft-managed-desktop"></a>Microsoft 托管桌面中的安全技术

<!--Security, also Onboarding doc: data handling/store, privileged account access -->

Microsoft 托管桌面使用多种 Microsoft 技术来帮助保护托管设备和数据。 此外，Microsoft 托管桌面安全操作中心将各种过程 [与这些技术](security-operations.md) 结合使用。

具体来说： 

- [设备安全](#device-security) – Microsoft 托管桌面设备上的安全性和保护
- [标识和访问管理](#identity-and-access-management) – 通过 Azure Active Directory 标识服务管理设备的安全使用
- [网络安全](#network-security) – VPN 信息和 Microsoft 托管桌面建议的解决方案和设置
- [信息安全](#information-security) – 可选可用服务，可进一步保护敏感信息 

有关 Microsoft 托管桌面使用的数据存储、使用情况和安全做法的信息，请参阅我们的白皮书 [https://aka.ms/mmd-data](https://aka.ms/mmd-data) 。


## <a name="device-security"></a>设备安全性

Microsoft 托管桌面确保所有托管设备都受到保护，并尽早使用下列服务检测威胁：

服务 | 说明
--- | ---
防病毒 | 安装和配置 Microsoft Defender AV<br>Microsoft Defender AV 定义是最新的
全卷加密 |    Windows BitLocker 是 Microsoft 托管桌面设备的卷加密解决方案。<br><br>组织载入服务后，设备将使用 Windows BitLocker 和内置信任平台模块 (TPM) 进行加密，以防止在设备进入睡眠模式或关闭时对本地数据进行未经授权的访问。 
监控 |    Microsoft Defender for Endpoint 用于跨所有 Microsoft 托管桌面设备监视安全威胁。 Defender for Endpoint 允许企业客户检测、调查和响应企业网络中高级威胁。 有关详细信息，请参阅 [Microsoft Defender for Endpoint。](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection) 
操作系统更新 |  Microsoft 托管桌面设备始终使用最新的安全更新进行保护。
安全设备配置 |   Microsoft 托管桌面实现 Microsoft 安全基线。 有关详细信息，请参阅 [Windows 安全基线。](https://docs.microsoft.com/windows/security/threat-protection/windows-security-baselines)



## <a name="identity-and-access-management"></a>标识和访问管理

标识和访问管理可保护公司资产和业务关键数据。 Microsoft 托管桌面配置设备以确保与 Azure Active Directory (Azure AD) 安全使用。 客户有责任在 Azure AD 租户中维护准确的信息。 

服务 | 说明
--- | ---
生物识别身份验证 |  Windows Hello 允许用户使用人脸或 PIN 登录，使密码更难忘记或窃取。 客户负责实施其本地 Active Directory 在混合配置中使用此服务的必要先决条件。 有关详细信息，请参阅 [Windows Hello。](https://docs.microsoft.com/windows-hardware/design/device-experiences/windows-hello) 
标准用户权限 |  若要保护系统并使其更安全，将为用户分配标准用户权限。 此权限作为 Windows Autopilot 开箱即用体验的一部分分配。



## <a name="network-security"></a>网络安全性

客户负责网络安全。 

服务 | 说明
--- | ---
VPN | 客户拥有其 VPN 基础结构，以确保有限的公司资源可以在 Intranet 外部公开。<br><br>最低要求：Microsoft 托管桌面需要 Windows 10 兼容和支持的 VPN 解决方案。 如果你的组织需要 VPN 解决方案，它需要支持 Windows 10，并通过 Intune 进行打包和部署。 有关详细信息，请与软件发布者联系。<br><br>建议：<br>- Microsoft 建议使用通过 Intune 轻松部署以推送 VPN 配置文件的新式 VPN 解决方案。 此方法提供一种始终打开、无缝、可靠且安全的方式来访问企业网络。 有关详细信息，请参阅 [[Intune 中的 VPN 设置]](https://docs.microsoft.com/intune/vpn-settings-configure)。<br>- 使用 Microsoft 托管桌面时，Microsoft 不建议使用粗 VPN 客户端或较旧的 VPN 客户端，因为它可能会影响用户环境。<br>- Microsoft 建议传出 Web 流量直接转到 Internet，无需通过 VPN，以避免任何性能问题。<br>- 理想情况下，Microsoft 建议使用 Azure Active Directory 应用代理，而不是 VPN。


## <a name="information-security"></a>信息安全

您可以配置这些可选服务以帮助保护企业高价值资产。 

服务 | 说明
--- | ---
数据恢复  | 存储在设备上密钥文件夹中的信息将备份到 OneDrive for Business。 Microsoft 托管桌面不负责与 OneDrive for Business 不同步的数据。 
Windows 信息保护 |    对于需要高级别信息安全的公司，我们建议 [使用 Windows 信息](https://docs.microsoft.com/windows/threat-protection/windows-information-protection/protect-enterprise-data-using-wip) 保护和 Azure [信息保护](https://www.microsoft.com/cloud-platform/azure-information-protection)。 

