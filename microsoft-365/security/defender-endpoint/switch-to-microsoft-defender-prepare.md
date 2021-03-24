---
title: 切换到 Microsoft Defender for Endpoint - 准备
description: 这是第 1 阶段，准备，用于迁移到 Microsoft Defender for Endpoint。
keywords: 迁移， windows defender 高级威胁防护， atp， edr
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-migratetomdatp
ms.topic: article
ms.custom: migrationguides
ms.date: 03/03/2021
ms.reviewer: jesquive, chventou, jonix, chriggs, owtho
ms.openlocfilehash: faaf8aefca7cb3b2e0583ed080e66f5129488d37
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51056097"
---
# <a name="switch-to-microsoft-defender-for-endpoint---phase-1-prepare"></a>切换到 Microsoft Defender for Endpoint - 阶段 1：准备

**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

| ![阶段 1：准备](images/phase-diagrams/prepare.png)<br/>阶段 1：准备 | [![阶段 2：设置](images/phase-diagrams/setup.png)](switch-to-microsoft-defender-setup.md)<br/>[阶段 2：设置](switch-to-microsoft-defender-setup.md) | [![阶段 3：载入](images/phase-diagrams/onboard.png)](switch-to-microsoft-defender-onboard.md)<br/>[阶段 3：载入](switch-to-microsoft-defender-onboard.md) |
|--|--|--|
|*你在这里！*| | |

**欢迎使用切换到 Microsoft [Defender for Endpoint 的"准备"阶段](switch-to-microsoft-defender-migration.md#the-migration-process)**。 

此迁移阶段包括以下步骤：
1. [在组织设备上获取和部署更新](#get-and-deploy-updates-across-your-organizations-devices)
2. [获取 Microsoft Defender for Endpoint](#get-microsoft-defender-for-endpoint)。
3. [授予对 Microsoft Defender 安全中心的访问权限](#grant-access-to-the-microsoft-defender-security-center)。
4. [配置设备代理和 Internet 连接设置](#configure-device-proxy-and-internet-connectivity-settings)。

## <a name="get-and-deploy-updates-across-your-organizations-devices"></a>在组织设备上获取和部署更新

最佳做法是使组织的设备和终结点保持最新。 请确保现有终结点保护和防病毒解决方案是最新的，并且组织的操作系统和应用也具有最新的更新。 现在执行此操作有助于防止以后迁移到 Microsoft Defender for Endpoint 和 Microsoft Defender 防病毒时出现问题。

### <a name="make-sure-your-existing-solution-is-up-to-date"></a>确保现有解决方案是最新的

使现有终结点保护解决方案保持最新，并确保组织设备具有最新的安全更新。 

需要帮助？ 请参阅解决方案提供商的文档。

### <a name="make-sure-your-organizations-devices-are-up-to-date"></a>确保组织的设备是最新的

需要更新组织设备的帮助？ 参阅以下资源：

|操作系统 | Resource |
|:--|:--|
|Windows |[Microsoft Update](https://www.update.microsoft.com) |
|macOS | [如何在 Mac 上更新软件](https://support.apple.com/HT201541)|
|iOS |[更新 iPhone、iPad 或 iPod 触摸](https://support.apple.com/HT204204)|
|Android |[检查& Android 版本](https://support.google.com/android/answer/7680439) |
|Linux | [Linux 101：更新系统](https://www.linux.com/training-tutorials/linux-101-updating-your-system) |

## <a name="get-microsoft-defender-for-endpoint"></a>获取 Microsoft Defender for Endpoint

现在，你已更新组织的设备，下一步是获取 Microsoft Defender for Endpoint、分配许可证并确保已预配服务。

1. 立即购买或试用 Microsoft Defender for Endpoint。 [启动免费试用版或请求使用引号](https://aka.ms/mdatp)。 
2. 验证许可证是否正确预配。 [检查你的许可证状态](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/production-deployment#check-license-state)。
3. 作为全局管理员或安全管理员，设置 Microsoft Defender for Endpoint 的专用云实例。 请参阅 [Microsoft Defender for Endpoint setup： Tenant configuration](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/production-deployment#tenant-configuration)。
4. 如果终结点 (，) 使用代理访问 Internet，请参阅 [Microsoft Defender for Endpoint setup： Network configuration](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/production-deployment#network-configuration)。
 
此时，你已准备好向将使用 Microsoft Defender 安全中心 () [https://aka.ms/MDATPportal](https://aka.ms/MDATPportal) 的安全管理员和安全操作员授予访问权限。 

> [!NOTE]
> Microsoft Defender 安全中心有时称为 Microsoft Defender 终结点门户，可以在 访问 [https://aka.ms/MDATPportal](https://aka.ms/MDATPportal) 。 

## <a name="grant-access-to-the-microsoft-defender-security-center"></a>授予对 Microsoft Defender 安全中心的访问权限

Microsoft Defender 安全中心 () 访问和配置 [https://aka.ms/MDATPportal](https://aka.ms/MDATPportal) 适用于终结点的 Microsoft Defender 的特性和功能。 若要了解更多信息，请参阅 Microsoft Defender 安全 [中心概述](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/use)。

可以通过使用基本权限或基于角色的访问控制来授予对 Microsoft Defender 安全中心 (RBAC) 。 我们建议使用 RBAC，以便可以更精细地控制权限。

1. 为安全管理员和安全操作员规划角色和权限。 请参阅 [基于角色的访问控制](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/prepare-deployment#role-based-access-control)。
2. 设置和配置 RBAC。 我们建议使用 [Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune) 配置 RBAC，尤其是在你的组织使用 Windows 10、macOS、iOS 和 Android 设备的组合时。 请参阅[使用 Intune 设置 RBAC。](https://docs.microsoft.com/mem/intune/fundamentals/role-based-access-control)
    如果你的组织需要 Intune 外的其他方法，请选择以下选项之一：
    - [配置管理器](https://docs.microsoft.com/mem/configmgr/core/servers/deploy/configure/configure-role-based-administration)
    - [高级组策略管理](https://docs.microsoft.com/microsoft-desktop-optimization-pack/agpm)
    - [Windows Admin Center](https://docs.microsoft.com/windows-server/manage/windows-admin-center/overview)
3. 授予对 Microsoft Defender 安全中心的访问权限。  (需要帮助？ 请参阅 [使用 RBAC 管理门户](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/rbac)) 。

## <a name="configure-device-proxy-and-internet-connectivity-settings"></a>配置设备代理和 Internet 连接设置

若要启用设备和 Microsoft Defender for Endpoint 之间的通信，请配置代理和 Internet 设置。 下表包含指向可用于为各种操作系统和功能配置代理和 Internet 设置的资源的链接：

|功能  | 操作系统 | 资源 |
|--|--|--|
|[终结点检测和响应 (](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/overview-endpoint-detection-response) EDR)  |- [Windows 10](https://docs.microsoft.com/windows/release-health/release-information) <br/>- [Windows Server 2019](https://docs.microsoft.com/windows/release-health/status-windows-10-1809-and-windows-server-2019)<br/>- [Windows Server 1803 或更高版本](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1803)  |[配置计算机代理和 Internet 连接设置](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-proxy-internet) |
|EDR |- [Windows Server 2016](https://docs.microsoft.com/windows/release-health/status-windows-10-1607-and-windows-server-2016) <br/>- [Windows Server 2012 R2](https://docs.microsoft.com/windows/release-health/status-windows-8.1-and-windows-server-2012-r2)<br/>- [Windows Server 2008 R2 SP1](https://docs.microsoft.com/windows/release-health/status-windows-7-and-windows-server-2008-r2-sp1)<br/>- [Windows 8.1](https://docs.microsoft.com/windows/release-health/status-windows-8.1-and-windows-server-2012-r2)<br/>- [Windows 7 SP1](https://docs.microsoft.com/windows/release-health/status-windows-7-and-windows-server-2008-r2-sp1) |[配置代理和 Internet 连接设置](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/onboard-downlevel#configure-proxy-and-internet-connectivity-settings) |
|EDR  |macOS： <br/>- 10.15 (加泰罗尼亚语) <br/>- 10.14 (Mojave)  <br/>- 10.13 (High Sierra)   |[Microsoft Defender for Endpoint for Mac：网络连接](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-defender-atp-mac#network-connections) |
|[Microsoft Defender 防病毒](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10) |- [Windows 10](https://docs.microsoft.com/windows/release-health/release-information) <br/>- [Windows Server 2019](https://docs.microsoft.com/windows/release-health/status-windows-10-1809-and-windows-server-2019)<br/>- [Windows Server 1803 或更高版本](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1803) <br/>- [Windows Server 2016](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-2016) |[配置和验证 Microsoft Defender 防病毒软件网络连接](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-network-connections-microsoft-defender-antivirus)<br/> |
|防病毒 |macOS： <br/>- 10.15 (加泰罗尼亚语) <br/>- 10.14 (Mojave)  <br/>- 10.13 (High Sierra)  |[Microsoft Defender for Endpoint for Mac：网络连接](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-defender-atp-mac#network-connections) |
|防病毒 |Linux： <br/>- RHEL 7.2+<br/>- CentOS Linux 7.2 及以上<br/>- Ubuntu 16 LTS 或更高版本 LTS<br/>- SLES 12+<br/>- Debian 9+<br/>- Oracle Linux 7.2 |[适用于 Linux 的 Microsoft Defender for Endpoint：网络连接](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-defender-atp-linux#network-connections) |

## <a name="next-step"></a>后续步骤

**恭喜！** 你已完成切换到 Microsoft  Defender for Endpoint 的"准备["阶段](switch-to-microsoft-defender-migration.md#the-migration-process)！

- [继续设置适用于终结点的 Microsoft Defender。](switch-to-microsoft-defender-setup.md)
