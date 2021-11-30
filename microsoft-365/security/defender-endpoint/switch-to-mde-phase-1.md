---
title: 切换到 Microsoft Defender for Endpoint - 准备
description: 准备好切换到 Microsoft Defender for Endpoint。 更新设备并配置网络连接。
keywords: 迁移， Microsoft Defender for Endpoint， 最佳做法
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-migratetomdatp
- m365solution-mcafeemigrate
- m365solution-symantecmigrate
ms.topic: article
ms.custom:
- migrationguides
- admindeeplinkDEFENDER
ms.date: 11/29/2021
ms.reviewer: jesquive, chventou, jonix, chriggs, owtho
ms.openlocfilehash: 5eb24f439c8f728a8c8d1c156df956451ca25cc2
ms.sourcegitcommit: 4af23696ff8b44872330202fe5dbfd2a69d9ddbf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/30/2021
ms.locfileid: "61221451"
---
# <a name="switch-to-microsoft-defender-for-endpoint---phase-1-prepare"></a>切换到 Microsoft Defender for Endpoint - 阶段 1：准备

**适用于：**
- [Microsoft Defender for Endpoint 计划 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

| ![阶段 1：准备。](images/phase-diagrams/prepare.png)<br/>阶段 1：准备 | [![阶段 2：设置](images/phase-diagrams/setup.png)](switch-to-mde-phase-2.md)<br/>[阶段 2：设置](switch-to-mde-phase-2.md) | [![阶段 3：开始使用](images/phase-diagrams/onboard.png)](switch-to-mde-phase-3.md)<br/>[阶段 3：开始使用](switch-to-mde-phase-3.md) |
|--|--|--|
|*你在这里！*| | |

**欢迎使用切换到 Defender [for Endpoint 的"准备"阶段](switch-to-mde-overview.md#the-migration-process)**。

此迁移阶段包括以下步骤：

1. [在组织设备上获取和部署更新](#get-and-deploy-updates-across-your-organizations-devices)
2. [获取 Defender for Endpoint](#get-microsoft-defender-for-endpoint)。
3. [授予对网站Microsoft 365 Defender的访问权限](#grant-access-to-the-microsoft-365-defender-portal)。
4. [配置设备代理和 Internet 连接设置](#configure-device-proxy-and-internet-connectivity-settings)。

## <a name="get-and-deploy-updates-across-your-organizations-devices"></a>在组织设备上获取和部署更新

最佳做法是使组织的设备和终结点保持最新。 请确保现有终结点保护和防病毒解决方案是最新的，并且组织的操作系统和应用也具有最新的更新。 现在执行此操作有助于防止以后在迁移到 Defender for Endpoint 和 Microsoft Defender 防病毒。

### <a name="make-sure-your-existing-solution-is-up-to-date"></a>确保现有解决方案是最新的

使现有终结点保护解决方案保持最新，并确保组织设备具有最新的安全更新。

需要帮助？ 请参阅解决方案提供商的文档。

### <a name="make-sure-your-organizations-devices-are-up-to-date"></a>确保组织的设备是最新的

需要更新组织设备的帮助？ 参阅以下资源：

<br/><br/>

|操作系统|资源|
|---|---|
|Windows|[Microsoft Update](https://www.update.microsoft.com)|
|macOS|[如何在 Mac 上更新软件](https://support.apple.com/HT201541)|
|iOS|[更新你的iPhone、iPad或 iPod 触摸](https://support.apple.com/HT204204)|
|Android|[检查&你的 Android 版本](https://support.google.com/android/answer/7680439)|
|Linux|[Linux 101：更新系统](https://www.linux.com/training-tutorials/linux-101-updating-your-system)|

## <a name="get-microsoft-defender-for-endpoint"></a>获取 Microsoft Defender for Endpoint

现在，你已更新组织的设备，下一步是获取适用于终结点的 Defender、分配许可证并确保已预配服务。

1. 立即购买或试用 Defender for Endpoint。 [启动免费试用版或请求使用引号](https://aka.ms/mdatp)。

2. 验证许可证是否正确预配。 [检查你的许可证状态](production-deployment.md#check-license-state)。

3. 设置适用于终结点的 Defender 的专用云实例。 请参阅 [Defender for Endpoint setup： Tenant configuration](production-deployment.md#tenant-configuration)。

4. 如果终结点 (，) 使用代理访问 Internet，请参阅 [Defender for Endpoint setup： Network configuration](production-deployment.md#network-configuration)。

此时，你已准备好向将使用安全门户的安全管理员和安全Microsoft 365 Defender<a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">访问权限</a>。

> [!NOTE]
> 该Microsoft 365 Defender门户有时称为 Defender for Endpoint 门户，可在 上访问 <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">https://security.microsoft.com</a> 。 以前的Microsoft Defender 安全中心 (https://securitycenter.windows.com) 将很快重定向到 Microsoft 365 Defender 门户。 若要了解更多信息，请参阅[Microsoft 365 Defender门户概述](portal-overview.md)。

## <a name="grant-access-to-the-microsoft-365-defender-portal"></a>授予对 Microsoft 365 Defender 门户的访问权限

在<a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender</a>门户中，你可以访问和配置 Defender for Endpoint 的特性和功能。 若要了解更多信息，请参阅门户[Microsoft 365 Defender概述](use.md)。

可以使用 RBAC Microsoft 365 Defender基本权限或基于角色的访问控制来授予对 (门户) 。 我们建议使用 RBAC，以便可以更精细地控制权限。

1. 为安全管理员和安全操作员规划角色和权限。 请参阅 [基于角色的访问控制](prepare-deployment.md#role-based-access-control)。

2. 设置和配置 RBAC。 我们建议使用[Intune](/mem/intune/fundamentals/what-is-intune)配置 RBAC，尤其是在组织结合使用 Windows 10、macOS、iOS 和 Android 设备时。 请参阅[使用 Intune 设置 RBAC。](/mem/intune/fundamentals/role-based-access-control)

    如果你的组织需要 Intune 外的其他方法，请选择以下选项之一：

    - [配置管理器](/mem/configmgr/core/servers/deploy/configure/configure-role-based-administration)
    - [高级组策略管理](/microsoft-desktop-optimization-pack/agpm)
    - [Windows Admin Center](/windows-server/manage/windows-admin-center/overview)

3. 授予对网站Microsoft 365 Defender的访问权限。  (需要帮助？ 请参阅 [使用 RBAC 管理门户](rbac.md)) 。

## <a name="configure-device-proxy-and-internet-connectivity-settings"></a>配置设备代理和 Internet 连接设置

若要启用设备和 Defender for Endpoint 之间的通信，请配置代理和 Internet 设置。 下表包含指向可用于为各种操作系统和功能配置代理和 Internet 设置的资源的链接：

<br/><br/>

|功能|操作系统|资源|
|---|---|---|
|[终结点检测和响应](overview-endpoint-detection-response.md) (EDR) |[Windows 10](/windows/release-health/release-information)<br/><br/>[Windows Server 2019](/windows/release-health/status-windows-10-1809-and-windows-server-2019)<br/><br/>Windows Server 2022 <br/><br/>[Windows Server 1803 或更高版本](/windows-server/get-started/whats-new-in-windows-server-1803)|[配置计算机代理和 Internet 连接设置](configure-proxy-internet.md)|
|EDR|[Windows Server 2016](/windows/release-health/status-windows-10-1607-and-windows-server-2016)<br/><br/>[Windows Server 2012 R2](/windows/release-health/status-windows-8.1-and-windows-server-2012-r2)<br/><br/>[Windows Server 2008 R2 SP1](/windows/release-health/status-windows-7-and-windows-server-2008-r2-sp1)<br/><br/>[Windows 8.1](/windows/release-health/status-windows-8.1-and-windows-server-2012-r2)<br/><br/>[Windows 7 SP1](/windows/release-health/status-windows-7-and-windows-server-2008-r2-sp1)|[配置代理和 Internet 连接设置](onboard-downlevel.md#configure-proxy-and-internet-connectivity-settings)|
|EDR|macOS：<br/> 11.3.1 (大 Sur) <br/>10.15 (加泰罗尼亚语) <br/>10.14 (Mojave) |[macOS 上的 Defender for Endpoint：网络连接](microsoft-defender-endpoint-mac.md#network-connections)|
|[Microsoft Defender 防病毒](microsoft-defender-antivirus-in-windows-10.md)|[Windows 10](/windows/release-health/release-information) <br/><br/> [Windows Server 2019](/windows/release-health/status-windows-10-1809-and-windows-server-2019)<br/><br/> Windows Server 2022 <br/><br/> [Windows Server 1803 或更高版本](/windows-server/get-started/whats-new-in-windows-server-1803) <br/><br/> [Windows Server 2016](/windows-server/get-started/whats-new-in-windows-server-2016)|[配置和验证 Microsoft Defender 防病毒软件网络连接](configure-network-connections-microsoft-defender-antivirus.md)|
|防病毒|macOS：<br/> 11.3.1 (大 Sur) <br/>10.15 (加泰罗尼亚语) <br/>10.14 (Mojave) |[macOS 上的 Defender for Endpoint：网络连接](microsoft-defender-endpoint-mac.md#network-connections)|
|防病毒|Linux：<br/> RHEL 7.2+<br/>CentOS Linux 7.2+<br/>Ubuntu 16 LTS 或更高版本 LTS<br/>SLES 12+<br/>Debian 9+<br/>Oracle Linux 7.2|[Linux 上的 Defender for Endpoint：网络连接](microsoft-defender-endpoint-linux.md#network-connections)|


## <a name="next-step"></a>后续步骤

**恭喜！** 你已完成切换到 **Defender** for [Endpoint 的"准备"阶段](switch-to-mde-overview.md#the-migration-process)！

- [继续为终结点设置 Defender。](switch-to-mde-phase-2.md)
