---
title: 共享设备
description: 如何使用共享设备模式以及何时使用
keywords: Microsoft 托管桌面, Microsoft 365, 服务, 文档
ms.service: m365-md
author: tiaraquan
ms.author: tiaraquan
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: dougeby
ms.topic: article
ms.openlocfilehash: 3682087e47db062240b001e8631f73ae8cbc1cda
ms.sourcegitcommit: 966344e1aa442a4d10a0fb05f56badd38c833bb2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2022
ms.locfileid: "62909683"
---
# <a name="shared-devices"></a>共享设备

Microsoft 托管桌面允许你在"共享设备模式"中注册设备，类似于用户提供的共享设备[Microsoft Intune](/mem/intune/configuration/shared-user-device-settings)。

此模式下的设备针对用户不绑定到单个桌面且经常更改设备的情况进行了优化。 例如，一线工作人员（如银行说员或职员）。 你可以在此模式下将Microsoft 托管桌面[配置文件](profiles.md)应用到设备。 在此模式下注册的设备有一些重要区别：

- [设备存储](#device-storage) 已针对共享用户进行了优化。
- [将删除](#deletion-of-inactive-accounts) 非活动帐户。
- [默认情况下](#guest-accounts) 不支持来宾帐户。
- [Microsoft 365](#microsoft-365-apps-for-enterprise)企业许可的应用程序针对共享设备进行了优化。

由于你在 Microsoft 托管桌面 中注册时选择使用共享设备模式，因此，如果你稍后要更改退出此模式，则必须取消注册并再次注册它。

## <a name="when-to-use-shared-device-mode"></a>何时使用共享设备模式

用户频繁更改设备的任何情况。

例如，银行出银机可能位于一个位置管理贷款，但可以转移到后端办公室，以帮助客户进行按揭贷款。 在每个位置，设备运行不同的应用程序并针对这些任务进行优化，尽管它们供多个人使用。

当员工与患者交互时，他们通常会在房间和办公室之间移动。 他们可以登录到办公室的工作站，但连接到远程桌面并做笔记，并使用不同的患者在不同的房间重复此过程。

## <a name="when-not-to-use-shared-device-mode"></a>何时不使用共享设备模式

在这些情况下，共享设备模式不是一个不错的选择：

- 当用户的文件需要存储在本地而非云中时
- 如果设备上不同用户的用户体验需要不同
- 如果每个用户需要的应用程序集差异很大

## <a name="enroll-new-devices-in-shared-device-mode"></a>在共享设备模式下注册新设备

无论你或合作伙伴是否正在处理注册，都可以选择使用共享设备模式。

如果你要自己注册设备，请按照"自己注册新设备"中的 [](../get-started/register-devices-self.md)步骤操作，然后将其添加到"现代 **工作区设备 - 共享设备** 模式"组中。

> [!WARNING]
> 不要尝试将任何现有Microsoft 托管桌面设备转换为共享设备模式，只需将它们添加到此组。 应用的策略可能会导致OneDrive文件永久丢失。

如果你有合作伙伴注册设备，请按照合作伙伴注册设备的步骤中的步骤操作，但 [](../get-started/register-devices-partner.md)向组标记追加 **-Shared**，如下表所示：

| 设备配置文件 | Autopilot 组标记 (模式)  | 组标记 (共享设备模式)  |
| ----- | ----- | ----- |
| 敏感数据 | Microsoft365Managed_SensitiveData |  Microsoft365Managed_SensitiveData-Shared |
| Power user | Microsoft365Managed_PowerUser | 不支持 |
| Standard  | Microsoft365Managed_Standard | Microsoft365Managed_Standard-Shared |

## <a name="consequences-of-shared-device-mode"></a>共享设备模式的后果

### <a name="device-storage"></a>设备存储

共享设备的用户必须将其数据备份到云，以便可以跟踪到其他设备。 在共享设备模式下注册设备后，请确保OneDrive文件按需和已知文件夹[重定向功能](/onedrive/redirect-known-folders)。[](https://support.microsoft.com/office/save-disk-space-with-onedrive-files-on-demand-for-windows-10-0e6860d3-d9f3-4971-b321-7092438fb38e#:~:text=%20Turn%20on%20Files%20On-Demand%20%201%20Make,files%20as%20you%20use%20them%20box.%20More%20) 此方法将每个用户配置文件对设备存储的影响降至最低。 如果可用磁盘空间低于 25%，则共享设备模式下的设备将自动删除用户配置文件。 此活动安排在设备的本地时间午夜，除非存储变得严重受限。

Microsoft 托管桌面[使用 SharedPC](/mem/intune/configuration/shared-user-device-settings-windows) CSP 执行这些操作，因此请确保不要自己使用这些 CSP。

> [!IMPORTANT]
> 培训用户下载大文件后，应先确认在注销前在文件上看到绿色选中图标。如果作为清理操作一部分删除其帐户，并且文件未在 OneDrive 中完全上载，则文件将永久丢失。

### <a name="deletion-of-inactive-accounts"></a>删除非活动帐户

共享设备模式将删除超过 30 天未登录的任何帐户。

### <a name="guest-accounts"></a>来宾帐户

共享设备模式下的设备仅允许加入域的帐户。 如果你需要在设备上使用来宾帐户，你可以 [提出更改请求](../working-with-managed-desktop/admin-support.md) 以请求启用它们。

### <a name="microsoft-365-apps-for-enterprise"></a>Microsoft 365 企业应用版

[Microsoft 365 企业应用版](/microsoft-365/managed-desktop/get-started/m365-apps)通常允许给定用户同时在五台设备上安装这些应用。 在共享设备模式下，应用不计入限制，因此可以在设备之间漫游时使用它们。 部署和更新 Microsoft 365 企业应用版照常工作。

### <a name="device-profiles"></a>设备配置文件

在共享设备模式下，在给定设备上 [只能有一](profiles.md) 个设备配置文件。 此外，Power 用户设备配置文件当前在共享设备模式下不受支持。

### <a name="apps-and-policies-assigned-to-users"></a>分配给用户的应用和策略

在共享设备上，你应该将自己管理的任何应用或策略分配给设备组，而不是用户组。 分配到设备组可确保每个用户的体验更加一致。 例外情况[是公司门户](#deploying-apps-with-company-portal)。

## <a name="limitations-of-shared-device-mode"></a>共享设备模式的限制

### <a name="windows-hello"></a>Windows Hello

Windows Hello智能卡仿真来安全缓存用户 [PIN](/windows/security/identity-protection/hello-for-business/hello-faq)，从而最大限度地减少用户必须进行身份验证次数。 但是，Windows设备上一次只允许 10 个智能卡。 当第 11 个用户首次登录时，其中一个现有帐户将丢失其智能卡。 他们可以登录，但无法缓存其 PIN。

### <a name="universal-print"></a>通用打印

When Universal print installs a printer for a single user on a shared device that printer becomes available to all users of that device. 无法隔离共享设备上用户之间的打印机。

## <a name="limitations-of-shared-device-mode-in-the-public-preview-release"></a>公共预览版中共享设备模式的限制

### <a name="primary-user"></a>主要用户

每台Microsoft Intune都有一个主用户，该用户由 Autopilot 设置设备时分配。 但在共享设备时，Intune 要求删除主要用户。

> [!IMPORTANT]
> 共享设备模式在公共预览版中时，请务必按照以下步骤删除主要用户：登录到 Microsoft Endpoint Manager 管理中心，选择 **"设备**>**"**"所有设备"，选择设备，然后选择"**属性**>**"**"删除主要用户"，然后删除其中列出的用户。

### <a name="deploying-apps-with-company-portal"></a>使用应用程序部署公司门户

某些应用可能不需要存在于所有设备上，因此你可能希望用户仅在需要这些应用时从设备[公司门户。](/mem/intune/user-help/install-apps-cpapp-windows)

Microsoft 托管桌面共享公司门户设备模式的设备默认禁用此功能。 如果希望启用公司门户，可以提出[更改请求](../working-with-managed-desktop/admin-support.md)。 但是，在此公共预览版中，应注意此功能的一些限制：

- 若要使应用可供用户[公司门户，可在](/mem/intune/apps/apps-deploy) Intune 中向该应用分配用户组，然后将每个用户添加到该用户组。
- 设备不能有主 [用户](#primary-user)。
- 若要卸载用户通过 公司门户安装的应用，必须从该设备的所有用户卸载该应用。

> [!CAUTION]
> 公司门户不支持分配给设备组的应用程序（如果可用）。

### <a name="redeployment-of-microsoft-365-apps-for-enterprise"></a>重新部署Microsoft 365 企业应用版

在公共预览版期间，Microsoft 365 应用版重新部署，用户必须联系其本地支持人员，以请求代理提升并重新安装Microsoft 365 企业应用版设备上。

### <a name="microsoft-teams"></a>Microsoft Teams

当用户首次Teams应用时，系统会提示他们更新应用，然后才能使用它。 一旦他们允许更新，Teams将在后台保持自身更新。
