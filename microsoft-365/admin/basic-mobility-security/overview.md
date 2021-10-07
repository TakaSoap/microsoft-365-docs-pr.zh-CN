---
title: 基本移动性和安全性概述Microsoft 365
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- MET150
description: 使用基本移动性和安全性设置设备安全策略和访问规则。
ms.openlocfilehash: 4fb1b8ca467d86259f2608af5140510a2a88b23a
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60165996"
---
# <a name="overview-of-basic-mobility-and-security-for-microsoft-365"></a>基本移动性和安全性概述Microsoft 365

当移动设备连接到您的组织时，您可以使用基本移动性和安全性Microsoft 365移动设备的安全。 用于访问工作电子邮件、日历、联系人及文档的移动设备（如智能手机和平板电脑）在确保员工随时随地完成工作方面起着非常重要的作用。 因此，在用户使用设备时，帮助保护组织的信息至关重要。 您可以使用基本移动性和安全性设置设备安全策略和访问规则，以及擦除丢失或被盗的移动设备。

:::image type="content" source="../../media/basic-mobility-security/bms-3-setup.png" alt-text="基本移动和安装程序。":::

## <a name="what-types-of-devices-can-you-manage"></a>您可以管理哪些类型的设备？

您可以使用基本移动性和安全性来管理许多类型的移动设备，如 Windows Phone、Android、iPhone 和 iPad。 要管理组织中人员使用的移动设备，每个人必须拥有适用的 Microsoft 365 许可证，并且其设备必须在基本移动性和安全性中注册。

若要了解基本移动性和安全性支持每种类型的设备，请参阅 [Capabilities of Basic Mobility and Security。](capabilities.md)

## <a name="setup-steps-for-basic-mobility-and-security"></a>基本移动性和安全性的安装步骤

全局Microsoft 365管理员必须完成以下步骤才能激活和设置基本移动性和安全性。 有关详细步骤，请按照设置基本 [移动性和安全性中的指导操作](set-up.md)。 

以下是步骤的摘要：

**步骤 1：** 按照设置基本移动性和安全性 中的步骤激活  [基本移动性和安全性](set-up.md)。

**步骤 2：** 例如，通过创建用于管理 iOS 设备的 APNs 证书，并添加域的域名系统 (DNS) 记录来支持 Windows 电话，来设置基本移动性和安全性。

**步骤 3：** 创建设备策略，并应用于用户组。 当你这样做时，你的用户会在你的设备上收到注册消息，当他们完成注册后，他们的设备将受限于你为它们设置的策略。 有关详细信息，请参阅使用基本 [移动性和安全性注册移动设备](enroll-your-mobile-device.md)。 

:::image type="content" source="../../media/basic-mobility-security/bms-4-policy.png" alt-text="基本安全和移动策略设置。":::

## <a name="device-management-tasks"></a>设备管理任务

在设置基本移动性和安全性并且用户已注册其设备后，你可以管理设备、阻止访问或擦除设备（如有必要）。 若要了解有关一些常见设备管理任务（包括在何处完成任务）的信息，请参阅管理在移动设备管理中注册的设备[Microsoft 365。](manage-enrolled-devices.md)

## <a name="other-ways-to-manage-devices-and-apps"></a>管理设备和应用的其他方法

如果你只需在 MAM (移动应用) ，也许对于在其自己的设备上更新工作项目的人，Intune 提供了除注册和管理设备之外的另一个选项。 Intune 订阅允许你使用 Azure 门户设置 MAM 策略，即使用户的设备未在 Intune 中注册。 有关详细信息，请参阅应用 [保护策略概述](/mem/intune/apps/app-protection-policy)。

## <a name="related-content"></a>相关内容

[设置基本移动性和安全性](set-up.md) (文章) \
[使用基本移动性和安全性功能](enroll-your-mobile-device.md) 注册移动设备 (文章) \
[管理在移动设备管理中注册的设备Microsoft 365 (](manage-enrolled-devices.md)文章) \
[有关由基本移动性和安全性管理的设备的详细信息， (](get-details-about-managed-devices.md) 文章) 