---
title: 切换到Microsoft Defender for Endpoint - 准备
description: 准备好切换到Microsoft Defender for Endpoint。 更新设备并配置网络连接。
keywords: 迁移，Microsoft Defender for Endpoint，最佳做法
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
ms.date: 04/01/2022
ms.reviewer: jesquive, chventou, jonix, chriggs, owtho
ms.openlocfilehash: c08ab1c96adc2b9d83cc6869573f2f0dbe75ac78
ms.sourcegitcommit: ac0ae5c2888e2b323e36bad041a4abef196c9c96
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/12/2022
ms.locfileid: "64782910"
---
# <a name="switch-to-microsoft-defender-for-endpoint---phase-1-prepare"></a>切换到Microsoft Defender for Endpoint - 阶段 1：准备

**适用于：**
- [Microsoft Defender for Endpoint 计划 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

| ![阶段 1：准备。](images/phase-diagrams/prepare.png#lightbox)<br/>阶段 1：准备 | [![阶段 2：设置](images/phase-diagrams/setup.png#lightbox)](switch-to-mde-phase-2.md)<br/>[阶段 2：设置](switch-to-mde-phase-2.md) | [![阶段 3：开始使用](images/phase-diagrams/onboard.png#lightbox)](switch-to-mde-phase-3.md)<br/>[阶段 3：开始使用](switch-to-mde-phase-3.md) |
|--|--|--|
|*你在这里！*| | |

**欢迎使用 [切换到 Defender for Endpoint 的](switch-to-mde-overview.md#the-migration-process)“准备”阶段**。

此迁移阶段包括以下步骤：

1. [获取和部署组织设备中的更新](#get-and-deploy-updates-across-your-organizations-devices)
2. [获取 Defender for Endpoint](#get-microsoft-defender-for-endpoint)。
3. [授予对Microsoft 365 Defender门户的访问权限](#grant-access-to-the-microsoft-365-defender-portal)。
4. [配置设备代理和 Internet 连接设置](#configure-device-proxy-and-internet-connectivity-settings)。

## <a name="get-and-deploy-updates-across-your-organizations-devices"></a>获取和部署组织设备中的更新

最佳做法是使组织的设备和终结点保持最新。 请确保现有的终结点保护和防病毒解决方案是最新的，并且你的组织的操作系统和应用也具有最新更新。 现在，在迁移到 Defender for Endpoint 并Microsoft Defender 防病毒时，执行此操作有助于防止出现问题。

### <a name="make-sure-your-existing-solution-is-up-to-date"></a>确保现有解决方案是最新的

使现有终结点保护解决方案保持最新，并确保组织的设备具有最新的安全更新。

需要帮助？ 请参阅解决方案提供商的文档。

### <a name="make-sure-your-organizations-devices-are-up-to-date"></a>确保组织的设备是最新的

需要帮助更新组织的设备？ 参阅以下资源：

|操作系统|资源|
|---|---|
|Windows|[Microsoft Update](https://www.update.microsoft.com)|
|macOS|[如何更新 Mac 上的软件](https://support.apple.com/HT201541)|
|iOS|[更新iPhone、iPad或 iPod 触摸](https://support.apple.com/HT204204)|
|Android|[检查&更新 Android 版本](https://support.google.com/android/answer/7680439)|
|Linux|[Linux 101：更新系统](https://www.linux.com/training-tutorials/linux-101-updating-your-system)|

## <a name="get-microsoft-defender-for-endpoint"></a>获取Microsoft Defender for Endpoint

现在，你已更新组织的设备，下一步是获取 Defender for Endpoint，分配许可证，并确保已预配服务。

1. 立即购买或试用 Defender for Endpoint。 [启动免费试用版或请求引号](https://aka.ms/mdatp)。

2. 验证许可证是否已正确预配。 [检查许可证状态](production-deployment.md#check-license-state)。

3. 设置 Defender for Endpoint 的专用云实例。 请参阅 [Defender for Endpoint 安装程序：租户配置](production-deployment.md#tenant-configuration)。

4. 如果组织中 (设备) 等终结点使用代理访问 Internet，请参阅 [Defender for Endpoint 安装程序：网络配置](production-deployment.md#network-configuration)。

此时，你已准备好向将使用<a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender门户</a>的安全管理员和安全操作员授予访问权限。

> [!NOTE]
> Microsoft 365 Defender门户有时称为 Defender for Endpoint 门户，可访问<a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">https://security.microsoft.com</a>。 前Microsoft Defender 安全中心 (https://securitycenter.windows.com)将很快重定向到Microsoft 365 Defender门户。 若要了解详细信息，请参阅[Microsoft 365 Defender门户概述](portal-overview.md)。

## <a name="grant-access-to-the-microsoft-365-defender-portal"></a>授予对Microsoft 365 Defender门户的访问权限

<a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender门户</a>是访问和配置 Defender for Endpoint 的功能的位置。 若要了解详细信息，请参阅[Microsoft 365 Defender门户概述](use.md)。

可以使用基本权限或基于角色的访问控制 (RBAC) 授予对 Microsoft 365 Defender 门户的权限。 建议使用 RBAC，以便更精细地控制权限。

1. 为安全管理员和安全操作员规划角色和权限。 请参阅 [基于角色的访问控制](prepare-deployment.md#role-based-access-control)。

2. 设置和配置 RBAC。 建议使用[Intune](/mem/intune/fundamentals/what-is-intune)来配置 RBAC，尤其是在组织使用 Windows 10、macOS、iOS 和 Android 设备的组合时。 请参阅[使用Intune设置 RBAC](/mem/intune/fundamentals/role-based-access-control)。

    如果组织需要Intune以外的方法，请选择以下选项之一：

    - [配置管理器](/mem/configmgr/core/servers/deploy/configure/configure-role-based-administration)

    - [高级组策略管理](/microsoft-desktop-optimization-pack/agpm)
    
    - [Windows Admin Center](/windows-server/manage/windows-admin-center/overview)

3. 授予对Microsoft 365 Defender门户的访问权限。  (需要帮助？ 请参阅 [使用 RBAC 管理门户访问权限](rbac.md)。

## <a name="configure-device-proxy-and-internet-connectivity-settings"></a>配置设备代理和 Internet 连接设置

若要在设备和 Defender for Endpoint 之间启用通信，请配置代理和 Internet 设置。 下表包含可用于为各种操作系统和功能配置代理和 Internet 设置的资源的链接：

|功能|操作系统|资源|
|---|---|---|
|[终结点检测和响应](overview-endpoint-detection-response.md) (EDR) |[Windows 10](/windows/release-health/release-information)或更高版本<br/><br/>Windows Server 2022 <br/><br/>[Windows Server 2019](/windows/release-health/status-windows-10-1809-and-windows-server-2019)<br/><br/>[Windows服务器 1803 或更高版本](/windows-server/get-started/whats-new-in-windows-server-1803)<br/><br/>[Windows Server 2016*](/windows/release-health/status-windows-10-1607-and-windows-server-2016)<br/><br/>[Windows Server 2012 R2*](/windows/release-health/status-windows-8.1-and-windows-server-2012-r2)|[配置计算机代理和 Internet 连接设置](configure-proxy-internet.md)|
|EDR [Windows服务器 2008 R2 SP1](/windows/release-health/status-windows-7-and-windows-server-2008-r2-sp1)<br/><br/>[Windows 8.1](/windows/release-health/status-windows-8.1-and-windows-server-2012-r2)<br/><br/>[Windows 7 SP1](/windows/release-health/status-windows-7-and-windows-server-2008-r2-sp1)|[配置代理和 Internet 连接设置](onboard-downlevel.md#configure-proxy-and-internet-connectivity-settings)|
|EDR|macOS (查看 [系统要求](microsoft-defender-endpoint-mac.md)|[macOS 上的 Defender for Endpoint：网络连接](microsoft-defender-endpoint-mac.md#network-connections)|
|[Microsoft Defender 防病毒](microsoft-defender-antivirus-in-windows-10.md)|[Windows 10](/windows/release-health/release-information) <br/><br/> [Windows Server 2019](/windows/release-health/status-windows-10-1809-and-windows-server-2019)<br/><br/> Windows Server 2022 <br/><br/> [Windows服务器 1803 或更高版本](/windows-server/get-started/whats-new-in-windows-server-1803) <br/><br/> [Windows Server 2016](/windows-server/get-started/whats-new-in-windows-server-2016)<br/><br/>[Windows Server 2012 R2*](/windows/release-health/status-windows-8.1-and-windows-server-2012-r2)|[配置和验证 Microsoft Defender 防病毒软件网络连接](configure-network-connections-microsoft-defender-antivirus.md)|
|防病毒|macOS (查看 [系统要求](microsoft-defender-endpoint-mac.md)|[macOS 上的 Defender for Endpoint：网络连接](microsoft-defender-endpoint-mac.md#network-connections)|
|防病毒|Linux (请参阅 [系统要求](microsoft-defender-endpoint-linux.md#system-requirements)) |[Linux 上的 Defender for Endpoint：网络连接](microsoft-defender-endpoint-linux.md#network-connections)|

*需要为 Windows Server 2012 R2 和 2016 安装新式统一解决方案。 有关详细信息，请参阅[将Windows服务器载入到Microsoft Defender for Endpoint服务](/microsoft-365/security/defender-endpoint/configure-server-endpoints)。

## <a name="next-step"></a>后续步骤

**恭喜**！ 你已完成 [切换到 Defender for Endpoint](switch-to-mde-overview.md#the-migration-process) 的 **“准备**”阶段！

- [继续设置 Defender for Endpoint](switch-to-mde-phase-2.md)。
