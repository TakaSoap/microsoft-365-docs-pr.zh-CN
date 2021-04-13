---
title: 从 Symantec 到 Microsoft Defender for Endpoint - 第 1 阶段，正在准备
description: 这是从 Symantec 迁移到 Microsoft Defender for Endpoint 的第 1 阶段，即准备阶段。
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
- m365solution-symantecmigrate
ms.topic: article
ms.date: 03/03/2021
ms.custom: migrationguides
ms.reviewer: depicker, yongrhee, chriggs
ms.openlocfilehash: 4cf22ff668859757d3a3ccf21d81751f526b97f7
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/13/2021
ms.locfileid: "51687633"
---
# <a name="migrate-from-symantec---phase-1-prepare-for-your-migration"></a>从 Symantec 迁移 - 阶段 1：准备迁移

**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

|![阶段 1：准备](images/phase-diagrams/prepare.png)<br/>阶段 1：准备 |[![阶段 2：设置](images/phase-diagrams/setup.png)](symantec-to-microsoft-defender-atp-setup.md)<br/>[阶段 2：设置](symantec-to-microsoft-defender-atp-setup.md) |[![阶段 3：开始使用](images/phase-diagrams/onboard.png)](symantec-to-microsoft-defender-atp-onboard.md)<br/>[阶段 3：开始使用](symantec-to-microsoft-defender-atp-onboard.md) |
|--|--|--|
|*你在这里！*| | |


**欢迎使用从 [Symantec 迁移到 Microsoft Defender for Endpoint 的"准备"阶段](symantec-to-microsoft-defender-endpoint-migration.md#the-migration-process)**。 

此迁移阶段包括以下步骤：
1. [获取 Microsoft Defender for Endpoint](#get-microsoft-defender-for-endpoint)。
2. [授予对 Microsoft Defender 安全中心的访问权限](#grant-access-to-the-microsoft-defender-security-center)。
3. [配置设备代理和 Internet 连接设置](#configure-device-proxy-and-internet-connectivity-settings)。

## <a name="get-microsoft-defender-for-endpoint"></a>获取 Microsoft Defender for Endpoint

若要开始，你必须拥有 Microsoft Defender for Endpoint，并分配并预配许可证。

1. 立即购买或试用 Microsoft Defender for Endpoint。 [访问 Microsoft Defender for Endpoint 以启动免费试用版或请求一个引号](https://aka.ms/mdatp)。 
2. 验证许可证是否正确预配。 [检查你的许可证状态](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/production-deployment#check-license-state)。
3. 作为全局管理员或安全管理员，设置 Microsoft Defender for Endpoint 的专用云实例。 请参阅 [Microsoft Defender for Endpoint setup： Tenant configuration](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/production-deployment#tenant-configuration)。
4. 如果终结点 (，) 使用代理访问 Internet，请参阅 [Microsoft Defender for Endpoint setup： Network configuration](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/production-deployment#network-configuration)。
 
此时，你已准备好向将使用 Microsoft Defender 安全中心 () [https://aka.ms/MDATPportal](https://aka.ms/MDATPportal) 的安全管理员和安全操作员授予访问权限。 

> [!NOTE]
> Microsoft Defender 安全中心有时称为 Microsoft Defender 终结点门户。 

## <a name="grant-access-to-the-microsoft-defender-security-center"></a>授予对 Microsoft Defender 安全中心的访问权限

Microsoft Defender 安全中心 () 访问和配置 [https://aka.ms/MDATPportal](https://aka.ms/MDATPportal) 适用于终结点的 Microsoft Defender 的特性和功能。 若要了解更多信息，请参阅 Microsoft Defender 安全 [中心概述](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/use)。

可以通过使用基本权限或基于角色的访问控制来授予对 Microsoft Defender 安全中心 (RBAC) 。 我们建议使用 RBAC，以便可以更精细地控制权限。

1. 为安全管理员和安全操作员规划角色和权限。 请参阅 [基于角色的访问控制](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/prepare-deployment#role-based-access-control)。
2. 设置和配置 RBAC。 我们建议使用 [Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune) 配置 RBAC，尤其是在你的组织使用 Windows 10、macOS、iOS 和 Android 设备的组合时。 请参阅[使用 Intune 设置 RBAC。](https://docs.microsoft.com/mem/intune/fundamentals/role-based-access-control)<br/>
   如果你的组织需要 Intune 外的其他方法，请选择以下选项之一：
    - [配置管理器](https://docs.microsoft.com/mem/configmgr/core/servers/deploy/configure/configure-role-based-administration)
    - [高级组策略管理](https://docs.microsoft.com/microsoft-desktop-optimization-pack/agpm)
    - [Windows Admin Center](https://docs.microsoft.com/windows-server/manage/windows-admin-center/overview)
3. 授予对 Microsoft Defender 安全中心的访问权限。  (需要帮助？ 请参阅 [使用 RBAC 管理门户](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/rbac)) 。

## <a name="configure-device-proxy-and-internet-connectivity-settings"></a>配置设备代理和 Internet 连接设置

若要启用设备和 Microsoft Defender for Endpoint 之间的通信，请配置代理和 Internet 设置。 下表包含指向可用于为各种操作系统和功能配置代理和 Internet 设置的资源的链接：

|功能  | 操作系统 | 资源 |
|:----|:----|:---|
|[终结点检测和响应 (](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/overview-endpoint-detection-response) EDR)  |- [Windows 10](https://docs.microsoft.com/windows/release-health/release-information/) <br/>- [Windows Server 2019](https://docs.microsoft.com/windows/release-health/status-windows-10-1809-and-windows-server-2019)<br/>- [Windows Server 1803 或更高版本](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1803)  |[配置计算机代理和 Internet 连接设置](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-proxy-internet) |
|EDR |- [Windows Server 2016](https://docs.microsoft.com/windows/release-health/status-windows-10-1607-and-windows-server-2016) <br/>- [Windows Server 2012 R2](https://docs.microsoft.com/windows/release-health/status-windows-8.1-and-windows-server-2012-r2)<br/>- [Windows Server 2008 R2 SP1](https://docs.microsoft.com/windows/release-health/status-windows-7-and-windows-server-2008-r2-sp1)<br/>- [Windows 8.1](https://docs.microsoft.com/windows/release-health/status-windows-8.1-and-windows-server-2012-r2)<br/>- [Windows 7 SP1](https://docs.microsoft.com/windows/release-health/status-windows-7-and-windows-server-2008-r2-sp1) |[配置代理和 Internet 连接设置](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/onboard-downlevel#configure-proxy-and-internet-connectivity-settings) |
|EDR  |macOS： <br/>- 10.15 (加泰罗尼亚语) <br/>- 10.14 (Mojave)  <br/>- 10.13 (High Sierra)   |[macOS 上的 Microsoft Defender for Endpoint：网络连接](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-defender-atp-mac#network-connections) |
|[Microsoft Defender 防病毒](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10) |- [Windows 10](https://docs.microsoft.com/windows/release-health/release-information/) <br/>- [Windows Server 2019](https://docs.microsoft.com/windows/release-health/status-windows-10-1809-and-windows-server-2019)<br/>- [Windows Server 1803 或更高版本](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1803) <br/>- [Windows Server 2016](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-2016) |[配置和验证 Microsoft Defender 防病毒软件网络连接](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-network-connections-microsoft-defender-antivirus)<br/> |
|防病毒 |macOS： <br/>- 10.15 (加泰罗尼亚语) <br/>- 10.14 (Mojave)  <br/>- 10.13 (High Sierra)  |[Microsoft -Defender for Endpoint for Mac：网络连接](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-defender-atp-mac#network-connections) |
|防病毒 |Linux： <br/>- RHEL 7.2+<br/>- CentOS Linux 7.2 及以上<br/>- Ubuntu 16 LTS 或更高版本 LTS<br/>- SLES 12+<br/>- Debian 9+<br/>- Oracle Linux 7.2 |[Linux 上的 Microsoft Defender for Endpoint：网络连接](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-defender-atp-linux#network-connections)  |

## <a name="next-step"></a>后续步骤

**恭喜！** 你已完成从[Symantec](symantec-to-microsoft-defender-endpoint-migration.md#the-migration-process)迁移到 Microsoft Defender for Endpoint 的"准备"阶段！ 
- [继续设置适用于终结点的 Microsoft Defender。](symantec-to-microsoft-defender-atp-setup.md)
