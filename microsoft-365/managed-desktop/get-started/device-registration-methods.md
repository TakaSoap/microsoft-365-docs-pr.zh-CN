---
title: 设备注册方法Microsoft 托管桌面
description: 有关设备注册方法的信息Microsoft 托管桌面
keywords: Microsoft 托管桌面, Microsoft 365, 服务, 文档
ms.service: m365-md
author: tiaraquan
ms.author: tiaraquan
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
manager: dougeby
ms.topic: article
audience: Admin
ms.openlocfilehash: 7d0cabc0a9d11d337e5adabde568bd2a56ceca86
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/08/2022
ms.locfileid: "63318981"
---
# <a name="device-registration-methods"></a>设备注册方法

Microsoft 必须先向服务注册Microsoft 托管桌面，Microsoft 才能管理设备。

## <a name="registration-process"></a>注册过程

Microsoft 托管桌面由 Windows Autopilot 服务为设备注册工作流提供电源。 成功注册设备需要两个步骤：

1. 将捕获设备的唯一硬件标识（称为硬件哈希）并将其上载到 Autopilot 服务。
1. 设备与租户 ID Azure Active Directory关联。

理想情况下，这两个步骤由购买设备的 OEM、经销商或分销商执行。 OEM 或其他设备提供商使用注册授权过程代表你执行设备注册。

## <a name="registration-methods"></a>注册方法

此外，还可通过从新设备或现有设备收集硬件标识并手动上传，在组织中执行注册。 以下是设备注册方法Microsoft 托管桌面支持：

- OEM 注册
    - [使用合作伙伴门户](partner-registration.md#register-devices-using-the-partner-center)
    - [使用 OEM API](partner-registration.md#register-devices-by-using-the-oem-api)
- [手动注册](manual-registration.md)
- [手动注册现有设备](manual-registration-existing-devices.md)

## <a name="recommended-resources"></a>建议的资源

- [Windows Autopilot 概述](/mem/autopilot/windows-autopilot)
- [Windows Autopilot 注册概述](/mem/autopilot/registration-overview)

## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a>开始使用 Microsoft 托管桌面

1. 访问 [管理员门户](access-admin-portal.md)。
1. [在管理门户中添加和验证管理员联系人](add-admin-contacts.md)。
1. [注册后调整设置](conditional-access.md)。
1. 部署并分配 [Intune 公司门户](company-portal.md)。
1. [分配许可证](assign-licenses.md)。
1. [部署应用](deploy-apps.md)。
1. [准备设备](prepare-devices.md)。
1. 设置 [使用 Autopilot 和注册状态页的首次运行体验](esp-first-run.md)。
1. [启用用户支持功能](enable-support.md)。
1. [让用户做好使用设备的准备](get-started-devices.md)。
1. [开始使用应用控制](get-started-app-control.md)。
