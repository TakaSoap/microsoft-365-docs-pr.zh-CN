---
title: Microsoft 托管桌面的安全性
description: ''
keywords: Microsoft 托管桌面，Microsoft 365 服务文档
ms.service: m365-md
author: jdeckerms
ms.localizationpriority: normal
ms.date: 09/24/2018
ms.openlocfilehash: 0ea0bbc6a8055ee8459fadd85a6fa4ddac14bdb7
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2018
ms.locfileid: "26866024"
---
# <a name="security-in-microsoft-managed-desktop"></a>Microsoft 托管桌面的安全性

<!--Security, also Onboarding doc: data handling/store, privileged account access -->

通过使用许多 Microsoft 技术，我们可以确保 Microsoft 托管桌面设备的安全和 Microsoft 托管桌面安全运营团队可以阻止、 检测和响应高级威胁。不允许第三方安全产品、 应用程序和服务。Microsoft 将应用标准策略基准，以确保设备、 标识、 网络和企业数据安全，并受保护。

以下各节记录了安全实施这些类别：

- [数据安全性](#data-security)-我们如何确保您的数据存储，并且符合要求的 Azure 安全定位
- [设备安全](#device-security)– 我们如何确保 Microsoft 托管桌面设备的安全
- [标识安全性](#identity-security)– 我们如何确保现代工作区中的用户不泄漏
- [网络安全](#network-security)– 我们如何确保安全访问公司资源
- [信息安全](#information-security)– 我们如何确保企业数据是安全
- [特权的帐户访问](#privileged-account-access)-我们限制的访问

## <a name="data-security"></a>数据安全性

从您的租户传输数据存储在 Microsoft 租户位于美国的 Azure SQL 数据库中。您的数据存储，并且符合要求的 Azure 安全定位。 

有关详细信息，请参阅[Microsoft Azure security](https://www.microsoft.com/TrustCenter/Security/azure-security)。

此列表概括了 Microsoft 和您的租户之间传输数据的类型。 

- 从 Microsoft 向您的租户
    - 组名称
    - 配置安全策略
    - 设备订单
    - 用户帐户 （msadmin、 mstest，Microsoft 托管 Desktop_soc_ro、 Microsoft 托管 Desktop_wdgsoc）
    - E5 许可证分配给上面的 4 个用户
    - Windows 更新更新响铃的策略
    - 将来，进一步功能将开发允许发布的其他类型的配置内容包括应用程序、 策略和设置。
- 从 Microsoft 到租户
    - 设备更新、 使用情况和可靠性数据
    - 应用程序部署和可靠性数据
    - 更新和安全策略部署数据
    - 分配给设备的用户



## <a name="device-security"></a>设备安全

若要防止安全违规，务必确保所有 Microsoft 托管桌面设备都都不健康和安全。同样，务必确保我们可以检测不正常的设备并尽可能早地减少风险。

下表列出了提供以确保 Microsoft 托管桌面设备受信任和受保护的正常运行的服务。

服务 | 说明
--- | ---
防病毒 | 我们将确保：<br>安装和配置 Windows Defender AV<br>Windows Defender AV 定义是最新
完整批量加密 |    Windows BitLocker 是 Microsoft 托管桌面设备数据加密解决方案。<br><br>到服务 onboarded 组织后，将使用 Windows BitLocker 与内置信任平台模块 (TPM) 设备休眠模式中或关闭时，防止未授权的访问本地数据加密设备。 
监视 |    Windows Defender 高级威胁保护 (Windows Defender ATP) 是监控解决方案的所有 Microsoft 托管桌面设备安全威胁。Windows Defender ATP 允许企业客户检测、 调查和响应公司网络中的高级威胁。有关详细信息，请参阅[Windows Defender 高级威胁保护。](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection) 
软件更新 |  Microsoft 将确保 Microsoft 托管桌面设备始终安全与 Windows 和 Office，使用 Windows Update for Business 的最新的安全更新。
“恢复” |  企业数据存储在 OneDrive for business，并可以轻松地还原为 Microsoft 托管桌面设备。有关详细信息，请参阅[OneDrive for Business。](https://support.office.com/article/Restore-a-previous-version-of-a-file-in-OneDrive-159cad6d-d76e-4981-88ef-de6e96c93893?ui=en-US&rs=en-US&ad=US) 



## <a name="identity-security"></a>标识安全性

标识和访问管理保护公司资产和关键业务数据。Azure Active Directory (Azure AD) 提供在云中的标识服务并启用基于云的身份验证，以确保只有受信任的个人可以从 Microsoft 托管桌面设备访问企业资源。

服务 | 说明
--- | ---
企业级身份验证提供程序 |  使用 Microsoft azure AD 高级版本为您提供了承载在全球分布数据中心中的高可用性服务。服务处理来自多个 200 万个活动用户每一天的十亿的身份验证，并为您提供了为 99.9 %sla。
生物身份验证 |  Windows Hello 允许用户使用其表面或 PIN，进行更加复杂忘记或窃取密码登录。这可能需要其他配置的工作。有关详细信息，请参阅[Windows Hello。](https://docs.microsoft.com/windows-hardware/design/device-experiences/windows-hello)
多因素身份验证 | Azure 多因素身份验证防止未授权的访问内部部署和云应用程序提供了其他级别的身份验证使用移动电话，以及为自助服务密码重置。 
标准用户权限 |  保护系统，并使其更安全，用户将分配标准用户权限。这被分配的 Windows 自动执行某些操作的全新体验的一部分。



## <a name="network-security"></a>网络安全

客户负责网络安全。 

服务 | 说明
--- | ---
VPN | 客户拥有其 VPN 基础结构，以确保可以 intranet 外部公开有限的企业资源。<br><br>最低要求： Microsoft 托管桌面需要 Windows 10 兼容和支持 VPN 解决方案。如果您的组织需要 VPN 解决方案，它需要支持 Windows 10 并且已打包和可通过 Intune 部署。有关详细信息，请联系您软件发行者。<br><br>建议：<br>-Microsoft 建议无法轻松地部署通过 Intune 到推送 VPN 配置文件的现代 VPN 解决方案。这样，始终可用的、 无缝、 可靠，安全地访问企业网络。有关详细信息，请参阅 VPN 中 Intune 的设置。<br>-粗 VPN 客户端或旧 VPN 客户端，不建议使用由 Microsoft 同时使用 Microsoft 托管桌面，因为它会影响最终用户环境。<br>-Microsoft 建议的传出的 web 流量转直接到 Internet，而不经由 VPN 以避免任何性能问题。<br>-理想情况下，Microsoft 建议使用 Azure Active Directory 应用程序代理，而不是 VPN。


## <a name="information-security"></a>信息安全

客户可以配置这些可选的服务，以帮助保护企业高价值资产。 

服务 | 说明
--- | ---
条件访问 |    仅在兼容设备时，允许访问企业资源和服务。
数据恢复  | 信息存储在设备上的密钥文件夹中备份到 OneDrive for Bbusiness。Microsoft 托管桌面不负责使用 OneDrive for Business 同步的数据。 
Windows 信息保护 |    对于需要高级别的信息安全性的公司，我们建议[Windows 信息保护](https://docs.microsoft.com/windows/threat-protection/windows-information-protection/protect-enterprise-data-using-wip)和[Azure Information Protection。](https://www.microsoft.com/cloud-platform/azure-information-protection)。 


## <a name="privileged-account-access"></a>特权的帐户访问

现在，我们限制访问的客户 MSAdmin 凭据和应用程序通过这些机制：

- **运算符**– Microsoft 完整-时间-员工位于美国已成功完成定期背景和安全检查。
- **运算符标识**– 受到保护根据 Microsoft 设置的标准。有关详细信息，请参阅[管理用户标识和 microsoft 的安全访问](https://www.microsoft.com/itshowcase/Article/Content/931/Managing-user-identities-and-secure-access-at-Microsoft)。 
- 在运算符环境和客户的租户内执行**日志记录**。日志数据和个人信息保留在各自的环境中不遍历环境。 

