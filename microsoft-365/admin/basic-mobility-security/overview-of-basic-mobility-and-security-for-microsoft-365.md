---
title: Microsoft 365 的基本移动性和安全性概述
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
search.appverid:
- MET150
description: 使用基本移动性和安全性设置设备安全策略和访问规则。
ms.openlocfilehash: 7c1a4bc5ddf476463788f99305215ee6853190f1
ms.sourcegitcommit: 2179abfe0b7a8bea917eb1c1057ed3795bdf91e6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/02/2020
ms.locfileid: "47336740"
---
# <a name="overview-of-basic-mobility-and-security-for-microsoft-365"></a>Microsoft 365 的基本移动性和安全性概述

使用基本移动性和安全性连接到 Microsoft 365 组织时，可以管理和保护移动设备。 用于访问工作电子邮件、日历、联系人及文档的移动设备（如智能手机和平板电脑）在确保员工随时随地完成工作方面起着非常重要的作用。 因此，在用户使用设备时，帮助保护组织的信息非常关键。 您可以使用基本移动性和安全性来设置设备安全策略和访问规则，并在移动设备丢失或被盗时将其擦除。

:::image type="content" source="../../media/basic-mobility-security/bms-3-setup.png" alt-text="基本移动性和安全设置":::

## <a name="what-types-of-devices-can-you-manage"></a>您可以管理哪些类型的设备？

您可以使用基本移动性和安全性来管理多种类型的移动设备，如 Windows Phone、Android、iPhone 和 iPad。 若要管理组织中的人员使用的移动设备，每个人都必须具有适用的 Microsoft 365 许可证，并且其设备必须在基本移动性和安全性中进行注册。

若要查看每种类型的设备的基本移动性和安全性支持，请参阅 [基本移动性和安全性的功能](capabilities-of-basic-mobility-and-secruity.md)。

## <a name="setup-steps-for-basic-mobility-and-security"></a>基本移动性和安全性的设置步骤

Microsoft 365 全局管理员必须完成以下步骤才能激活和设置基本移动性和安全性。 有关详细步骤，请按照 [设置基本移动性和安全性](set-up-basic-mobility-and-security.md)中的指导进行操作。 

以下是这些步骤的摘要：

**步骤1：** 按照 [设置基本移动性和安全性](set-up-basic-mobility-and-security.md)中的步骤激活基本移动性和安全性。

**步骤2：** 设置基本移动性和安全性，例如，创建用于管理 iOS 设备的 APNs 证书和添加域名系统 (域的 DNS) 记录以支持 Windows phone。

**步骤3：** 创建设备策略并将其应用到用户组。 在执行此操作时，用户将在其设备上获取注册消息，并在完成注册后，其设备将受到您为其设置的策略的限制。 有关详细信息，请参阅 [使用基本移动性和安全性注册移动设备](enroll-your-mobile-device-using-basic-mobility-and-security.md)。 

:::image type="content" source="../../media/basic-mobility-security/bms-4-policy.png" alt-text="基本安全性和移动性策略设置":::

## <a name="device-management-tasks"></a>设备管理任务

在设置了基本的移动性和安全性并对用户注册了其设备之后，您可以管理设备、阻止访问或擦除设备（如有必要）。 若要了解有关一些常见设备管理任务（包括在何处完成这些任务）的详细信息，请参阅 [管理在 Microsoft 365 的移动设备管理中注册的设备](manage-devices-enrolled-in-mdm-in-microsoft-365.md)。

## <a name="other-ways-to-manage-devices-and-apps"></a>管理设备和应用程序的其他方法

如果只需要移动应用管理 (MAM) （可能是用户在自己的设备上更新工作项目），Intune 除了注册和管理设备之外，还提供另一个选项。 Intune 订阅允许你使用 Azure 门户设置 MAM 策略，即使用户的设备未在 Intune 中注册也是如此。 有关详细信息，请参阅 [App protection 策略概述](https://go.microsoft.com/fwlink/?LinkId=2132517)。

## <a name="related-topics"></a>相关主题

[设置基本移动性和安全性](set-up-basic-mobility-and-security.md)

[使用基本移动性和安全性注册移动设备](enroll-your-mobile-device-using-basic-mobility-and-security.md)

[管理在 Microsoft 365 的移动设备管理中注册的设备](manage-devices-enrolled-in-mdm-in-microsoft-365.md)

[获取有关由基本移动性和安全性管理的设备的详细信息](get-details-about-basic-mobility-and-security-managed-devices.md)