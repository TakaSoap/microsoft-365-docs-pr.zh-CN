---
title: Microsoft 365的基本移动性和安全性概述
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
ms.openlocfilehash: b4752a6f1b71c453b3d1b89adeb25f337a65c255
ms.sourcegitcommit: ac0ae5c2888e2b323e36bad041a4abef196c9c96
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/12/2022
ms.locfileid: "64780844"
---
# <a name="overview-of-basic-mobility-and-security-for-microsoft-365"></a>Microsoft 365的基本移动性和安全性概述

使用基本移动性和安全性连接到Microsoft 365组织时，可以管理和保护移动设备。 用于访问工作电子邮件、日历、联系人及文档的移动设备（如智能手机和平板电脑）在确保员工随时随地完成工作方面起着非常重要的作用。 因此，当用户使用设备时，帮助保护组织的信息至关重要。 可以使用基本移动性和安全性设置设备安全策略和访问规则，并在移动设备丢失或被盗时擦除它们。

:::image type="content" source="../../media/basic-mobility-security/bms-3-setup.png" alt-text="基本移动性和安全性设置。":::

## <a name="what-types-of-devices-can-you-manage"></a>您可以管理哪些类型的设备？

可以使用基本移动性和安全性来管理多种类型的移动设备，例如Windows Phone、Android、iPhone和iPad。 若要管理组织中人员使用的移动设备，每个人都必须具有适用的Microsoft 365许可证，并且其设备必须注册到基本移动性和安全性。

若要查看每种类型的设备支持哪些基本移动性和安全性，请参阅 [基本移动性和安全性功能](capabilities.md)。

## <a name="setup-steps-for-basic-mobility-and-security"></a>基本移动性和安全性的设置步骤

Microsoft 365全局管理员必须完成以下步骤才能激活和设置基本移动性和安全性。 有关详细步骤，请按照 [“设置基本移动性和安全性](set-up.md)”中的指导操作。 

下面是步骤的摘要：

**步骤 1：** 按照 [“设置基本移动性和安全性”中的步骤激活基本移动性和安全性](set-up.md)。

**步骤 2：** 设置基本移动性和安全性，例如，创建用于管理 iOS 设备的 APN 证书，并为域添加域的域名系统 (DNS) 记录以支持Windows手机。

**步骤 3：** 创建设备策略并将其应用于用户组。 执行此操作时，用户会在其设备上收到注册消息，完成注册后，其设备会受到为其设置的策略的限制。 有关详细信息，请参阅 [使用基本移动性和安全性注册移动设备](enroll-your-mobile-device.md)。 

:::image type="content" source="../../media/basic-mobility-security/bms-4-policy.png" alt-text="基本的安全性和移动性策略设置。":::

## <a name="device-management-tasks"></a>设备管理任务

设置基本移动性和安全性且用户已注册其设备后，如有必要，可以管理设备、阻止访问或擦除设备。 若要详细了解一些常见的设备管理任务，包括在何处完成任务，请参阅[管理在移动设备管理中注册的设备，以便Microsoft 365](manage-enrolled-devices.md)。

## <a name="other-ways-to-manage-devices-and-apps"></a>管理设备和应用的其他方法

如果你只需要移动应用管理 (MAM) ，也许对于在自己的设备上更新工作项目的用户而言，Intune除了注册和管理设备之外，还提供了另一个选项。 Intune订阅允许使用Azure 门户设置 MAM 策略，即使用户的设备未在Intune中注册。 有关详细信息，请参阅[应用保护策略概述](/mem/intune/apps/app-protection-policy)。

## <a name="related-content"></a>相关内容

[设置基本移动性和安全](set-up.md) 性 (文章) \
[使用基本移动性和安全](enroll-your-mobile-device.md) 性 (文章) \ 注册移动设备
[管理在移动设备管理中注册的设备，Microsoft 365 (](manage-enrolled-devices.md)文章) \
[获取有关基本移动性和安全性管理的设备的详细信息](get-details-about-managed-devices.md) (文章) 