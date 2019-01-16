---
title: Microsoft 托管桌面的安全性
description: ''
keywords: Microsoft 托管桌面，Microsoft 365 服务文档
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 09/24/2018
ms.openlocfilehash: 928d01e7386bedc500e984b9c2a3240c6229bb43
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/16/2019
ms.locfileid: "26866024"
---
# <a name="security-in-microsoft-managed-desktop"></a>Microsoft 托管桌面的安全性

<!--Security, also Onboarding doc: data handling/store, privileged account access -->

Microsoft 托管桌面应用一组标准的策略，并使用许多 Microsoft 技术，可帮助 Microsoft 托管桌面的安全设备、 存储的公司数据和详细信息。下面列出的区域的详细进一步：  

- [数据安全性](#data-security)-由 Microsoft 托管桌面和安全地存储位置收集的数据类型
- [设备安全](#device-security)– 安全和保护 Microsoft 托管桌面设备上
- [标识和访问管理](#identity-and-access-management)– 管理安全使用 Azure Active Directory 标识服务通过设备
- [网络安全](#network-security)– VPN 信息和 Microsoft 托管桌面推荐的解决方案和设置
- [信息安全](#information-security)– 可选可用的服务，以进一步保护敏感信息 

## <a name="data-security"></a>数据安全性

从客户租户收集的数据 （以使 Microsoft 托管桌面 IT 服务和操作） 存储在 Microsoft 租户位于美国的 Azure SQL 数据库中。

有关详细信息，请参阅[Microsoft Azure security](https://docs.microsoft.com/azure/security/azure-database-security-overview)。

下面列出了从您的租户传输的数据类型：

- 设备更新、 使用情况和可靠性数据
- 应用程序部署和可靠性数据
- 更新和安全策略部署数据
- 分配给设备的用户



## <a name="device-security"></a>设备安全

Microsoft 托管桌面可确保托管的所有设备安全和保护，并尽可能使用以下服务检测早地威胁：

服务 | 说明
--- | ---
防病毒 | 安装和配置 Windows Defender AV<br>Windows Defender AV 定义是最新
完整批量加密 |    Windows BitLocker 是 Microsoft 托管桌面设备批量加密解决方案。<br><br>到服务 onboarded 组织后，将使用 Windows BitLocker 与内置信任平台模块 (TPM) 设备休眠模式中或关闭时，防止未授权的访问本地数据加密设备。 
监视 |    Windows Defender 高级威胁保护 (Windows Defender ATP) 用于跨所有 Microsoft 托管桌面设备的安全威胁监视。Windows Defender ATP 允许企业客户检测、 调查和响应公司网络中的高级威胁。有关详细信息，请参阅[Windows Defender 高级威胁保护。](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection) 
软件更新 |  Microsoft 托管桌面设备始终安全使用最新的安全更新。
安全的设备配置 |   Microsoft 托管桌面实现 Microsoft 安全基准。有关详细信息，请参阅[Windows 安全基准。](https://docs.microsoft.com/windows/security/threat-protection/windows-security-baselines)



## <a name="identity-and-access-management"></a>标识和访问管理

标识和访问管理保护公司资产和关键业务数据。Microsoft 托管桌面配置设备，以确保安全使用 Azure Active Directory (Azure AD) 托管标识。它是客户的责任维护其 Azure AD 租户中的准确信息。 

服务 | 说明
--- | ---
生物身份验证 |  Windows Hello 允许用户使用其表面或 PIN，进行更加复杂忘记或窃取密码登录。有关详细信息，请参阅[Windows Hello。](https://docs.microsoft.com/windows-hardware/design/device-experiences/windows-hello)
多重身份验证 | Azure 多因素身份验证更紧密通过提供良好，自助服务密码重置为使用移动电话，身份验证的其他级别控制对敏感函数 Microsoft 托管桌面服务的访问。 
标准用户权限 |  保护系统，并使其更安全，用户将分配标准用户权限。这被分配的 Windows 自动执行某些操作的全新体验的一部分。



## <a name="network-security"></a>网络安全

客户负责网络安全。 

服务 | 说明
--- | ---
VPN | 客户拥有其 VPN 基础结构，以确保可以 intranet 外部公开有限的企业资源。<br><br>最低要求： Microsoft 托管桌面需要 Windows 10 兼容和支持 VPN 解决方案。如果您的组织需要 VPN 解决方案，它需要支持 Windows 10 并且已打包和可通过 Intune 部署。有关详细信息，请联系您软件发行者。<br><br>建议：<br>-Microsoft 建议无法轻松地部署通过 Intune 到推送 VPN 配置文件的现代 VPN 解决方案。这样，始终可用的、 无缝、 可靠，安全地访问企业网络。有关详细信息，请参阅[[VPN 设置 Intune]](https://docs.microsoft.com/intune/vpn-settings-configure)。<br>-粗 VPN 客户端或旧 VPN 客户端，不建议使用由 Microsoft 同时使用 Microsoft 托管桌面，因为它会影响最终用户环境。<br>-Microsoft 建议的传出的 web 流量转直接到 Internet，而不经由 VPN 以避免任何性能问题。<br>-理想情况下，Microsoft 建议使用 Azure Active Directory 应用程序代理，而不是 VPN。


## <a name="information-security"></a>信息安全

客户可以配置这些可选的服务，以帮助保护企业高价值资产。 

服务 | 说明
--- | ---
数据恢复  | 到 OneDrive for Business 备份存储在设备上的密钥文件夹中的信息。Microsoft 托管桌面不负责使用 OneDrive for Business 同步的数据。 
Windows 信息保护 |    对于需要高级别的信息安全性的公司，我们建议[Windows 信息保护](https://docs.microsoft.com/windows/threat-protection/windows-information-protection/protect-enterprise-data-using-wip)和[Azure Information Protection。](https://www.microsoft.com/cloud-platform/azure-information-protection)。 

