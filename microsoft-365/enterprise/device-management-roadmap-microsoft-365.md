---
title: Microsoft 365 设备管理指南
keywords: Microsoft 365、Microsoft 365企业版、Microsoft 365文档、移动设备管理、Intune
author: kelleyvice-msft
ms.author: kvice
manager: laurawi
ms.date: 08/10/2020
ms.topic: conceptual
f1.keywords:
- NOCSH
ms.prod: microsoft-365-enterprise
ms.service: ''
ms.technology: ''
ms.assetid: fb4182e6-5e78-45d0-9641-d791c4519441
audience: ITPro
ms.custom: microsoft-intune
description: 为设备设置设备管理的Microsoft 365。
ms.openlocfilehash: 0fef31697657b4694090ae7a1b63516920d8c71b
ms.sourcegitcommit: c6a97f2a5b7a41b74ec84f2f62fabfd65d8fd92a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2022
ms.locfileid: "61933343"
---
# <a name="device-management-roadmap-for-microsoft-365"></a>Microsoft 365 设备管理指南

Microsoft 365企业版包括可帮助在组织中管理设备及其应用的功能。 管理移动设备可帮助您保护组织的资源。

设备管理有两个选项：

- [Microsoft Intune](#microsoft-intune)
- [基本移动性和安全性](#basic-mobility-and-security)

## <a name="microsoft-intune"></a>Microsoft Intune

您可以使用Microsoft Intune管理或移动应用程序管理来管理对组织的访问权限。 移动设备管理是当用户在 Intune 中"注册"其设备时。 注册设备后，它是托管设备;因此，它可以接收组织的策略、规则和设置。 例如，你可以安装特定应用、创建密码策略、安装 VPN 连接等。

拥有其自己的个人设备的用户可能不希望注册其设备或由 Intune 和组织的策略进行管理。 但仍需要保护组织的资源和数据。 在此方案中，可以使用移动应用程序管理来保护应用。 例如，可以使用移动应用程序管理策略，要求用户在访问 SharePoint Online 时输入 PIN。

你还将确定如何管理个人设备和组织拥有的设备。 你可能希望以不同方式处理设备，具体取决于设备的用途。

## <a name="basic-mobility-and-security"></a>基本移动性和安全性

这内置于 Microsoft 365，可帮助你保护和管理用户的移动设备，如 iPhone、iPad、Android 和 Windows 手机。 可以创建和管理设备安全策略，远程擦除设备，以及查看详细的设备报告。

## <a name="choose-between-the-two-options"></a>在两个选项中进行选择

为了帮助你更好地评估最适合你的设备管理选项，请参阅在 [基本移动性安全性和 Intune](/office365/securitycompliance/choose-between-mdm-and-intune)之间选择。

根据你的评估，开始使用：

- [Intune](/microsoft-365/solutions/manage-devices-with-intune-overview)
- [基本移动性和安全性](https://support.microsoft.com/office/set-up-basic-mobility-and-security-dd892318-bc44-4eb1-af00-9db5430be3cd)
 
## <a name="identity-and-device-access-recommendations"></a>标识和设备访问建议

Microsoft 提供了一组有关[身份和设备访问](../security/office-365-security/microsoft-365-policies-configurations.md)的建议，以确保全体员工安全且高效地工作。 对于设备访问，请使用以下文章中的建议和设置：

- [先决条件](../security/office-365-security/identity-access-prerequisites.md)
- [常见标识和设备访问策略](../security/office-365-security/identity-access-policies.md)

## <a name="how-contoso-did-device-management-for-microsoft-365"></a>Contoso 如何管理设备Microsoft 365

有关虚构但具有代表性的跨国家/公司如何使用云服务部署其移动设备管理基础结构Microsoft 365，请参阅[Contoso](contoso-mdm.md)移动设备管理。