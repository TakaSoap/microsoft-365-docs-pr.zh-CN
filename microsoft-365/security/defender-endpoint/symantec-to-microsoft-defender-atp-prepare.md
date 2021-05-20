---
title: 从 Symantec 到 Microsoft Defender for Endpoint - 第 1 阶段，正在准备
description: 这是从 Symantec 迁移到 Microsoft Defender for Endpoint 的第 1 阶段，即准备阶段。
keywords: migration， Microsoft Defender for Endpoint， edr
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
ms.date: 05/14/2021
ms.custom: migrationguides
ms.reviewer: depicker, yongrhee, chriggs
ms.openlocfilehash: 7fe0eb8adc90c259d31f237082effc80c5e8622c
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2021
ms.locfileid: "52537975"
---
# <a name="migrate-from-symantec---phase-1-prepare-for-your-migration"></a>从 Symantec 迁移 - 阶段 1：准备迁移

**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

|![阶段 1：准备](images/phase-diagrams/prepare.png)<br/>阶段 1：准备 |[![阶段 2：设置](images/phase-diagrams/setup.png)](symantec-to-microsoft-defender-atp-setup.md)<br/>[阶段 2：设置](symantec-to-microsoft-defender-atp-setup.md) |[![阶段 3：开始使用](images/phase-diagrams/onboard.png)](symantec-to-microsoft-defender-atp-onboard.md)<br/>[阶段 3：开始使用](symantec-to-microsoft-defender-atp-onboard.md) |
|--|--|--|
|*你在这里！*| | |


**欢迎使用从 [Symantec 迁移到 Defender for Endpoint 的"准备"阶段](symantec-to-microsoft-defender-endpoint-migration.md#the-migration-process)**。 

此迁移阶段包括以下步骤：

1. [更新组织的设备](#update-your-organizations-devices)。

2. [获取 Microsoft Defender for Endpoint](#get-microsoft-defender-for-endpoint)。

3. [授予对 Microsoft Defender 安全中心 的访问权限](#grant-access-to-the-microsoft-defender-security-center)。

4. [配置设备代理和 Internet 连接设置](#configure-device-proxy-and-internet-connectivity-settings)

## <a name="update-your-organizations-devices"></a>更新组织设备

最佳做法是使组织的设备和终结点保持最新。 请确保现有终结点保护和防病毒解决方案是最新的，并且组织的操作系统和应用也具有最新的更新。 现在执行此操作有助于防止以后迁移到 Defender for Endpoint 时出现问题。

### <a name="make-sure-symantec-is-up-to-date"></a>确保 Symantec 是最新的

使现有终结点保护解决方案保持最新，并确保组织设备具有最新的安全更新。

需要帮助? 请参阅 Broadcom 的文档[：Symantec Endpoint Protection安装和管理指南](https://techdocs.broadcom.com/us/en/symantec-security-software/endpoint-security-and-management/endpoint-protection/all.html)

### <a name="make-sure-your-endpoints-are-up-to-date"></a>确保终结点是最新的

需要更新组织设备的帮助？ 参阅以下资源：


|操作系统  |Resource  |
|---------|---------|
|Windows     | [Microsoft Update](https://www.update.microsoft.com/)        |
|macOS     | [如何在 Mac 上更新软件](https://support.apple.com/HT201541)         |
|iOS     | [更新你的iPhone、iPad或 iPod 触摸](https://support.apple.com/HT204204)         |
|Android     | [检查& Android 版本](https://support.google.com/android/answer/7680439)        |
|Linux     | [Linux 101：更新系统](https://www.linux.com/training-tutorials/linux-101-updating-your-system)        |


## <a name="get-microsoft-defender-for-endpoint"></a>获取 Microsoft Defender for Endpoint

现在，你已更新组织的设备，下一步是获取适用于终结点的 Defender、分配许可证并确保已预配服务。

1. 立即购买或试用 Defender for Endpoint。 [访问 Defender for Endpoint 以启动免费试用版或请求使用引号](https://aka.ms/mdatp)。 

2. 验证许可证是否正确预配。 [检查你的许可证状态](production-deployment.md#check-license-state)。

3. 作为全局管理员或安全管理员，设置适用于终结点的 Defender 的专用云实例。 请参阅 [Defender for Endpoint setup： Tenant configuration](production-deployment.md#tenant-configuration)。

4. 如果终结点 (，) 使用代理访问 Internet，请参阅 [Defender for Endpoint setup： Network configuration](production-deployment.md#network-configuration)。
 
此时，您已准备好向将使用安全管理策略的安全管理员和安全 [https://aka.ms/MDATPportal](https://aka.ms/MDATPportal) Microsoft Defender 安全中心 () 。 

> [!NOTE]
> 该Microsoft Defender 安全中心有时称为 Defender for Endpoint 门户。 

## <a name="grant-access-to-the-microsoft-defender-security-center"></a>向用户授予Microsoft Defender 安全中心

此 [https://aka.ms/MDATPportal](https://aka.ms/MDATPportal) Microsoft Defender 安全中心 () 访问和配置 Defender for Endpoint 的特性和功能。 若要了解更多信息，请参阅[Microsoft Defender 安全中心 概述](use.md)。

可以使用 RBAC Microsoft Defender 安全中心基本权限或基于角色的访问控制来授予 (权限) 。 我们建议使用 RBAC，以便可以更精细地控制权限。

1. 为安全管理员和安全操作员规划角色和权限。 请参阅 [基于角色的访问控制](prepare-deployment.md#role-based-access-control)。

2. 设置和配置 RBAC。 我们建议使用[Intune](/mem/intune/fundamentals/what-is-intune)配置 RBAC，尤其是在组织结合使用 Windows 10、macOS、iOS 和 Android 设备时。 请参阅[使用 Intune 设置 RBAC。](/mem/intune/fundamentals/role-based-access-control)

   如果你的组织需要 Intune 外的其他方法，请选择以下选项之一：

    - [配置管理器](/mem/configmgr/core/servers/deploy/configure/configure-role-based-administration)

    - [高级组策略管理](/microsoft-desktop-optimization-pack/agpm)

    - [Windows管理中心](/windows-server/manage/windows-admin-center/overview)

3. 向用户授予Microsoft Defender 安全中心。  (需要帮助？ 请参阅 [使用 RBAC 管理门户](rbac.md)) 。

## <a name="configure-device-proxy-and-internet-connectivity-settings"></a>配置设备代理和 Internet 连接设置

若要启用设备和 Defender for Endpoint 之间的通信，请配置代理和 Internet 设置。 下表包含指向可用于为各种操作系统和功能配置代理和 Internet 设置的资源的链接：

|功能  | 操作系统 | 资源 |
|:----|:----|:---|
|[终结点检测和响应](overview-endpoint-detection-response.md) (EDR)  | [Windows 10](/windows/release-health/release-information/) <p> [Windows Server 2019](/windows/release-health/status-windows-10-1809-and-windows-server-2019)<p>[Windows服务器 1803 或更高版本](/windows-server/get-started/whats-new-in-windows-server-1803)  |[配置计算机代理和 Internet 连接设置](configure-proxy-internet.md) |
|EDR | [Windows Server 2016](/windows/release-health/status-windows-10-1607-and-windows-server-2016) <p>[Windows Server 2012 R2](/windows/release-health/status-windows-8.1-and-windows-server-2012-r2)<p>[Windows Server 2008 R2 SP1](/windows/release-health/status-windows-7-and-windows-server-2008-r2-sp1)<p>[Windows 8.1](/windows/release-health/status-windows-8.1-and-windows-server-2012-r2)<p>[Windows 7 SP1](/windows/release-health/status-windows-7-and-windows-server-2008-r2-sp1) |[配置代理和 Internet 连接设置](onboard-downlevel.md#configure-proxy-and-internet-connectivity-settings) |
|EDR  |macOS： <p>11.3.1 (Big Sur) <p>10.15 (加泰罗尼亚语) <p>10.14 (Mojave)  |[macOS 上的 Defender for Endpoint：网络连接](microsoft-defender-endpoint-mac.md#network-connections) |
|[Microsoft Defender 防病毒](microsoft-defender-antivirus-in-windows-10.md) |[Windows 10](/windows/release-health/release-information/)<p>[Windows Server 2019](/windows/release-health/status-windows-10-1809-and-windows-server-2019)<p>[Windows服务器 1803 或更高版本](/windows-server/get-started/whats-new-in-windows-server-1803)<p>[Windows Server 2016](/windows-server/get-started/whats-new-in-windows-server-2016) |[配置和验证 Microsoft Defender 防病毒软件网络连接](configure-network-connections-microsoft-defender-antivirus.md) |
|防病毒 |macOS： <p>11.3.1 (Big Sur) <p>10.15 (加泰罗尼亚语) <p>10.14 (Mojave)   |[Mac 上的 Defender for Endpoint：网络连接](microsoft-defender-endpoint-mac.md#network-connections) |
|防病毒 |Linux： <p>RHEL 7.2+<p>CentOS Linux 7.2+<p>Ubuntu 16 LTS 或更高版本 LTS<p>SLES 12+<p>Debian 9+<p>Oracle Linux 7.2 |[Linux 上的 Defender for Endpoint：网络连接](microsoft-defender-endpoint-linux.md#network-connections)  |

## <a name="next-step"></a>后续步骤

**恭喜！** 你已完成从[Symantec 迁移到 Defender for Endpoint 的"准备"阶段](symantec-to-microsoft-defender-endpoint-migration.md#the-migration-process)！
- [继续为终结点设置 Defender。](symantec-to-microsoft-defender-atp-setup.md)
