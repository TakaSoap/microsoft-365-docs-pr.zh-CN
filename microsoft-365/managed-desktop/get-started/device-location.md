---
title: Windows 10 位置服务
description: 介绍如何为Windows启用定位服务
keywords: 'Microsoft 托管桌面, Microsoft 365, 服务, 文档'
ms.service: m365-md
author: tiaraquan
f1.keywords:
  - NOCSH
ms.author: tiaraquan
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
manager: dougeby
ms.topic: article
audience: Admin
---

# <a name="windows-10-location-service"></a>Windows 10 位置服务

设备中的Microsoft 托管桌面使用 Autopilot Windows注册。 通过此过程，我们Azure Active Directory和Microsoft Intune。

默认情况下，Windows 10设备首次打开时禁用定位服务，除非在"开箱即用体验"期间的隐私设置中启用此功能。 这些设置在 Autopilot 注册期间处于隐藏Microsoft 托管桌面。 要详细了解如何设置 Autopilot，请参阅 [Autopilot 首次运行体验和注册状态页](esp-first-run.md)。

因此，Microsoft 托管桌面设备无法获取其设备位置，并限制多个Windows功能（如时区）的功能。 有关定位服务Windows 10，请参阅Windows 10[定位服务和隐私](https://support.microsoft.com/windows/windows-10-location-service-and-privacy-3a8eee0a-5b0b-dc07-eede-2a5ca1c49088)。

你不必使用定位服务来参与Microsoft 托管桌面。 将限制用户体验。 例如，当用户在不同的时区工作时，设备无法自动确定它们所在时区。

## <a name="enable-the-location-service"></a>启用定位服务

您可以：

- 选择在将设备注册到 Microsoft 托管桌面 服务时使用位置服务，或者
- 注册后，你可以打开或关闭该服务。

### <a name="opt-in-during-enrollment"></a>在注册期间选择加入

您可以让Microsoft 托管桌面启用定位服务。 在注册序列期间，将要求你选择是否要允许在设备上Windows 10定位服务。

### <a name="control-the-location-service-after-enrollment"></a>注册后控制定位服务

通过管理门户提交支持 (，你) 启用或关闭定位[服务](access-admin-portal.md)。[](../working-with-managed-desktop/admin-support.md)

## <a name="how-microsoft-managed-desktop-configures-the-windows-10-location-service"></a>如何Microsoft 托管桌面配置Windows 10定位服务

如果你选择使用定位服务，我们将使用所需的最低设置，而不会影响用户的隐私。 有关详细信息，请参阅Windows 10[服务和隐私](https://support.microsoft.com/windows/windows-10-location-service-and-privacy-3a8eee0a-5b0b-dc07-eede-2a5ca1c49088)。

Microsoft 托管桌面设置中的"位置 **隐私**"**Windows"** 允许 **访问此设备上的位置"**。 用户界面如下所示：

 :::image type="content" source="../../media/MMD-location-services-UI.png" alt-text="设置中Windows设置。":::

> [!NOTE]
> 如果你选择使用定位服务，这仅适用于Windows操作系统本身。 不允许应用使用位置服务。 每个用户都可以选择是否允许应用访问其位置。
