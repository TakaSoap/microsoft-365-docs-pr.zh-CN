---
title: 安全技术Microsoft 托管桌面
description: 用于设备安全、标识和访问管理、网络安全和信息安全的技术
keywords: Microsoft 托管桌面, Microsoft 365, 服务, 文档
ms.service: m365-md
author: tiaraquan
ms.collection: M365-modern-desktop
ms.author: tiaraquan
manager: dougeby
ms.topic: article
ms.openlocfilehash: 4a6eb73a172ecfb680cbc48367851e40b1a54401
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/08/2022
ms.locfileid: "63315409"
---
# <a name="security-technologies-in-microsoft-managed-desktop"></a>安全技术Microsoft 托管桌面

<!--Security, also Onboarding doc: data handling/store, privileged account access -->

Microsoft 托管桌面使用多种 Microsoft 技术来帮助保护托管设备和数据的安全。 此外，安全Microsoft 托管桌面中心使用[这些技术的各种流程](security-operations.md)。 具体来说：

| 流程 | 说明 |
| ------ | ------ |
| [设备安全性](#device-security)| 安全和保护Microsoft 托管桌面设备上。 |
| [标识和访问管理](#identity-and-access-management) | 通过标识服务管理Azure Active Directory使用。 |
| [网络安全](#network-security)| VPN 信息和Microsoft 托管桌面解决方案和设置。 |
| [信息安全](#information-security)| 可选可用服务，可进一步保护敏感信息。 |

有关应用程序使用的数据存储、使用情况和安全Microsoft 托管桌面，请参阅 我们的白皮书[https://aka.ms/mmd-data](https://aka.ms/mmd-data)。

## <a name="device-security"></a>设备安全性

Microsoft 托管桌面确保所有托管设备都受到保护，并尽早使用下列服务检测威胁：

| 服务 | 说明 |
| ----- | ----- |
| 防病毒 | Microsoft Defender 防病毒和配置<br>Microsoft Defender 防病毒定义是最新的。 |
| 全卷加密 | Windows BitLocker 是适用于设备Microsoft 托管桌面解决方案。<br><br>组织注册服务后，设备会使用 Windows BitLocker 和内置信任平台模块 (TPM) 进行加密，以防止在设备进入睡眠模式或关闭时对本地数据进行未经授权的访问。
| 监控 | Microsoft Defender for Endpoint 用于跨所有设备监视Microsoft 托管桌面威胁。 Defender for Endpoint 允许企业客户检测、调查和响应企业网络中高级威胁。 有关详细信息，请参阅 [Microsoft Defender for Endpoint。](/windows/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection) |
| 操作系统更新 | Microsoft 托管桌面设备始终使用最新的安全更新进行保护。 |
| 安全设备配置 | Microsoft 托管桌面 Microsoft 安全基线。 有关详细信息，请参阅Windows[基线。](/windows/security/threat-protection/windows-security-baselines)|

## <a name="identity-and-access-management"></a>标识和访问管理

标识和访问管理可保护公司资产和业务关键型数据。 Microsoft 托管桌面配置设备以确保与托管标识Azure Active Directory (Azure AD) 安全使用。 客户有责任在租户中维护Azure AD信息。

| 服务 | 说明 |
| ----- | ----- |
| 生物识别身份验证 | Windows Hello允许用户使用人脸或 PIN 登录，使密码更难忘记或窃取。 客户负责实施必要的先决条件，使本地 Active Directory 在混合配置中使用此服务。 有关详细信息，请参阅Windows Hello[。](/windows-hardware/design/device-experiences/windows-hello) |
| 标准用户权限 | 为了保护系统，使其更安全，将为用户分配标准用户权限。 此权限作为 Autopilot Windows体验的一部分分配。

## <a name="network-security"></a>网络安全性

客户负责网络安全。

| 服务 | 说明 |
| ----- | ----- |
| VPN | 客户拥有其 VPN 基础结构，以确保有限的公司资源可在 Intranet 外部公开。<br><br>最低要求：Microsoft 托管桌面需要Windows 10且受支持的 VPN 解决方案。 如果你的组织需要 VPN 解决方案，它需要支持Windows 10并通过 Intune 打包和部署。 有关详细信息，请与软件发布者联系。<br><br>建议：<br><ul><li> Microsoft 推荐了一个通过 Intune 轻松部署以推送 VPN 配置文件的现代 VPN 解决方案。 此方法提供了一种访问企业网络的始终打开、无缝、可靠和安全的方法。 有关详细信息，请参阅 [Intune 中的 VPN 设置](/intune/vpn-settings-configure)。</li><li>使用胖 VPN 客户端或较旧的 VPN 客户端时，Microsoft 不建议Microsoft 托管桌面，因为它会影响用户环境。</li><li>Microsoft 建议传出 Web 流量直接转到 Internet，无需通过 VPN，以避免任何性能问题。</li><li>理想情况下，Microsoft 建议使用Azure Active Directory代理而不是 VPN。</li></ul>

## <a name="information-security"></a>信息安全

您可以配置这些可选服务以帮助保护公司高价值资产。

| 服务 | 说明 |
| ----- | ----- |
| 数据恢复 | 存储在设备上密钥文件夹中的信息将备份到OneDrive for Business。 Microsoft 托管桌面对未与数据同步的数据OneDrive for Business。
| Windows 信息保护 | 对于需要高级别信息安全的公司，我们建议Windows[信息和](/windows/threat-protection/windows-information-protection/protect-enterprise-data-using-wip) [Azure 信息保护。](https://www.microsoft.com/cloud-platform/azure-information-protection)
