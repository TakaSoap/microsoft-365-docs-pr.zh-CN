---
title: 共享设备
description: 如何以及何时使用共享设备模式
keywords: Microsoft 托管桌面, Microsoft 365, 服务, 文档
ms.service: m365-md
author: tiaraquan
ms.author: tiaraquan
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
manager: dougeby
ms.topic: article
ms.openlocfilehash: ad9cb5e69585f0c014050b51b719e539111cf9fa
ms.sourcegitcommit: 2f6a0096038d09f0e43e1231b01c19e0b40fb358
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/06/2022
ms.locfileid: "64687176"
---
# <a name="shared-devices"></a>共享设备

Microsoft 托管桌面允许你在"共享设备模式"中注册设备，类似于[Microsoft Intune](/mem/intune/configuration/shared-user-device-settings)提供的共享设备模式。

此模式下的设备针对用户未绑定到单个桌面且经常更改设备的情况进行了优化。 例如，一线工作人员，如银行出纳员或护理人员。 可以将任何Microsoft 托管桌面[配置文件](profiles.md)应用到此模式下的设备。 在此模式下注册的设备存在一些重要差异：

- [设备存储](#device-storage) 针对共享用户进行了优化。
- [将删除非活动帐户](#deletion-of-inactive-accounts) 。
- 默认情况下不支持[来宾帐户](#guest-accounts)。
- [Microsoft 365](#microsoft-365-apps-for-enterprise)企业许可应用程序针对共享设备进行了优化。

由于可以选择在Microsoft 托管桌面注册时使用共享设备模式，因此，如果以后要从此模式中进行更改，则必须取消注册并重新注册。

## <a name="when-to-use-shared-device-mode"></a>何时使用共享设备模式

用户经常更改设备的任何情况。

例如，银行出纳员可能位于管理存款的一个位置，但转到后台帮助客户获得抵押贷款。 在每个位置，设备运行不同的应用程序，并针对这些任务进行优化，尽管这些任务由多人使用。

护理人员通常在与患者互动时在房间和办公室之间移动。 他们可以登录到办公室的工作站，但连接到远程桌面并做笔记，并与不同的患者在另一个房间重复此过程。

## <a name="when-not-to-use-shared-device-mode"></a>何时不使用共享设备模式

在这些情况下，共享设备模式不是一个不错的选择：

- 当用户的文件需要存储在本地而不是云中时
- 如果设备上的不同用户的用户体验需要不同
- 如果每个用户需要的应用程序集存在很大差异

## <a name="register-new-devices-in-shared-device-mode"></a>在共享设备模式下注册新设备

从 2203 开始，无论你还是合作伙伴正在处理设备注册，都可以选择在Microsoft 托管桌面中使用 [Windows Autopilot 自部署模式](/mem/autopilot/self-deploying)配置文件。

如果自行注册设备，则必须将新设备导入Windows"Autopilot 设备"边栏选项卡中。

**若要将新设备导入Windows Autopilot 设备边栏选项卡：**

1. 收集要为其分配Windows Autopilot 自部署模式配置文件的新设备的[硬件哈希](../get-started/manual-registration.md#obtain-the-hardware-hash)。
2. 转到[Microsoft Endpoint Manager门户](https://endpoint.microsoft.com)。
2. 从左侧导航菜单中选择 **"设备** "。
3. 在"**By platform**"部分中，选择 **Windows**。 然后，选择 **Windows注册**。
4. 在 **"Windows Autopilot Deployment计划**"部分中，选择 **"设备**"。
5. [导](../get-started/manual-registration.md#register-devices-by-using-the-admin-portal) 入包含步骤 #1 中收集的所有硬件哈希的.CSV文件。
6. 上传 Windows Autopilot 设备后，必须编辑导入设备的组标记属性，以便Microsoft 托管桌面可以使用 Windows Autopilot 自部署模式配置文件注册它们。 请参阅下面的组标记属性。 必须追加 **-共享** 到组标记，如下表所示：

| 设备配置文件 | Autopilot 组标记 (标准模式)  | 共享设备模式 (组标记)  |
| ----- | ----- | ----- |
| 敏感数据 | Microsoft365Managed_SensitiveData |  Microsoft365Managed_SensitiveData-Shared |
| Power user | Microsoft365Managed_PowerUser | 不支持 |
| 标准  | Microsoft365Managed_Standard | Microsoft365Managed_Standard-Shared |

> [!WARNING]
> 请勿尝试通过将 **-Shared** 附加到以前导入到 Windows Autopilot 的设备来编辑组选项卡属性。 已导入 Windows Autopilot 的设备（使用Microsoft365Managed_开头的Microsoft 托管桌面组标记之 *一，但* 最初未追加 **-Shared**）已是其他Azure Active Directory组的一部分。 此Azure Active Directory组未分配Windows Autopilot 自部署模式配置文件。 如果必须将现有设备重新设置为共享设备，则必须再次删除设备并将设备重新注册到 autopilot Windows。

如果有合作伙伴注册设备，请按照 [合作伙伴注册](../get-started/partner-registration.md)中的步骤操作，但追加 **-共享** 到组标记，如上表所示。

## <a name="consequences-of-shared-device-mode"></a>共享设备模式的后果

### <a name="device-storage"></a>设备存储

共享设备的用户必须将其数据备份到云中，以便可以将其跟踪到其他设备。 在共享设备模式下注册设备后，请务必启用OneDrive的按[需文件](https://support.microsoft.com/office/save-disk-space-with-onedrive-files-on-demand-for-windows-10-0e6860d3-d9f3-4971-b321-7092438fb38e#:~:text=%20Turn%20on%20Files%20On-Demand%20%201%20Make,files%20as%20you%20use%20them%20box.%20More%20)和[已知文件夹重定向](/onedrive/redirect-known-folders)功能。 此方法可最大程度地减少每个用户配置文件对设备存储的影响。 如果可用磁盘空间低于 25%，则处于共享设备模式的设备会自动删除用户配置文件。 此活动安排在设备的本地时间午夜，除非存储受到严重限制。

Microsoft 托管桌面使用 [SharedPC](/mem/intune/configuration/shared-user-device-settings-windows) CSP 执行这些操作，因此请确保不要自行使用这些 CSP。

> [!IMPORTANT]
> 训练用户，在下载大型文件后，应在注销前确认他们在文件上看到绿色复选图标。如果他们的帐户作为清理操作的一部分被删除，并且文件未在OneDrive中完全上传，则文件将永久丢失。

### <a name="deletion-of-inactive-accounts"></a>删除非活动帐户

共享设备模式会删除任何已登录超过 30 天的帐户。

### <a name="guest-accounts"></a>来宾帐户

处于共享设备模式的设备仅允许加入域的帐户。 如果需要设备上的来宾帐户，可以提交 [更改请求](../working-with-managed-desktop/admin-support.md) 以请求启用这些帐户。

### <a name="microsoft-365-apps-for-enterprise"></a>Microsoft 365 企业应用版

[Microsoft 365 企业应用版](/microsoft-365/managed-desktop/get-started/m365-apps)通常允许给定用户同时在五台设备上安装这些应用。 在共享设备模式下，应用不按限制进行计数，因此它们可以在设备之间漫游时使用它们。 Microsoft 365 企业应用版的部署和更新照常工作。

### <a name="device-profiles"></a>设备配置文件

在共享设备模式下，在给定设备上只能有一个 [设备配置文件](profiles.md) 。 此外，共享设备模式当前不支持 Power 用户设备配置文件。

### <a name="apps-and-policies-assigned-to-users"></a>分配给用户的应用和策略

在共享设备上，应将自己管理的任何应用或策略分配给 *设备组*，而不是用户组。 分配到设备组可确保每个用户具有更一致的体验。 异常[公司门户](#deploying-apps-with-company-portal)。

## <a name="limitations-of-shared-device-mode"></a>共享设备模式的限制

### <a name="windows-hello"></a>Windows Hello

Windows Hello使用智能卡仿真来安全[缓存用户 PIN](/windows/security/identity-protection/hello-for-business/hello-faq)，将用户进行身份验证的次数降至最低。 但是，Windows一次只允许在给定设备上使用 10 张智能卡。 当第 11 个用户首次登录时，其中一个现有帐户将丢失其智能卡。 他们将能够登录，但不会缓存其 PIN。

### <a name="universal-print"></a>通用打印

当通用打印在共享设备上为单个用户安装打印机时，打印机将可供该设备的所有用户使用。 无法在共享设备上的用户之间隔离打印机。

## <a name="limitations-of-shared-device-mode-in-the-public-preview-release"></a>公共预览版中共享设备模式的限制

### <a name="primary-user"></a>主要用户

每个Microsoft Intune设备都有一个主用户，该用户由 Autopilot 设置设备时分配。 但是，当设备共享时，Intune要求删除主要用户。

> [!IMPORTANT]
> 共享设备模式处于公共预览状态时，请务必按照以下步骤删除主用户：登录Microsoft Endpoint Manager管理中心，选择 **DevicesAll**> **设备**，选择设备，然后选择 **PropertiesRemove**> 主用户，并删除其中列出的用户。

### <a name="deploying-apps-with-company-portal"></a>使用公司门户部署应用

某些应用可能不需要存在于所有设备上，因此您可能更希望用户仅在需要这些应用时从[公司门户](/mem/intune/user-help/install-apps-cpapp-windows)安装这些应用。

Microsoft 托管桌面默认情况下禁用共享设备模式下的设备的公司门户。 如果希望启用公司门户，可以提交[更改请求](../working-with-managed-desktop/admin-support.md)。 但是，在此公共预览版中，应注意此功能的一些限制：

- 若要将应用提供给公司门户中的用户，请在Intune中[将用户组分配](/mem/intune/apps/apps-deploy)给该应用，然后将每个用户添加到该用户组。
- 设备不能有 [主用户](#primary-user)。
- 若要卸载用户通过公司门户安装的应用，必须从该设备上的所有用户卸载该应用。

> [!CAUTION]
> 公司门户不支持按可用方式分配给设备组的应用程序。

### <a name="redeployment-of-microsoft-365-apps-for-enterprise"></a>为Enterprise重新部署Microsoft 365 应用版

在公共预览期间，如果必须重新部署Microsoft 365 应用版，则用户必须联系其本地支持人员，请求代理提升并重新安装该设备上的Microsoft 365 企业应用版。

### <a name="microsoft-teams"></a>Microsoft Teams

当用户首次启动Teams时，系统会提示他们更新应用，然后才能使用它。 允许更新后，Teams会在后台进行更新。
