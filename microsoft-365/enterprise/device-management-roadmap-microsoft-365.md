---
title: Microsoft 365 的设备管理路线图
keywords: Microsoft 365，Microsoft 365 for enterprise，Microsoft 365 文档，移动设备管理，Intune
author: JoeDavies-MSFT
ms.author: josephd
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
description: 为 Microsoft 365 设置设备管理的路线图。
ms.openlocfilehash: 1c5a06c75ede11697e2ecf17c47eb035e78dcd27
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/14/2020
ms.locfileid: "46687818"
---
# <a name="device-management-roadmap-for-microsoft-365"></a>Microsoft 365 的设备管理路线图


适用于企业的 Microsoft 365 包括帮助管理组织内的设备及其应用程序的功能。 管理移动设备可帮助您保护组织的资源。

设备管理有两个选项。

## <a name="microsoft-intune"></a>Microsoft Intune

Intune 为你提供了使用移动设备管理 (MDM) 或移动应用程序管理 (MAM) 管理对组织的访问权限的选项。 MDM 是用户在 Intune 中 "注册" 其设备。 注册后，它们就是受管理的设备，并且可以接收组织使用的任何策略、规则和设置。 例如，您可以安装特定应用程序，创建密码策略，安装 VPN 连接，等等。

拥有自己的个人设备的用户可能不希望注册其设备，也不能由 Intune 和你的策略进行管理。 但您仍需要保护您组织的资源和数据。 在这种情况下，您可以使用 MAM 保护您的应用程序。 例如，您可以使用一个 MAM 策略，该策略要求用户在设备上访问 SharePoint 时输入 PIN。

您还将确定如何管理个人或组织拥有的设备。 您可能需要以不同的方式处理设备，具体取决于设备的用途。 

从 [这里](https://docs.microsoft.com/mem/intune/fundamentals/planning-guide)开始。

## <a name="basic-mobility-and-security"></a>基本移动性和安全性
 
此功能内置于 Microsoft 365 中，可帮助您保护和管理用户的移动设备，如 Iphone、Ipad、Androids 和 Windows phone。 可以创建和管理设备安全策略，远程擦除设备，以及查看详细的设备报告。 

从 [这里](https://support.microsoft.com/office/set-up-basic-mobility-and-security-dd892318-bc44-4eb1-af00-9db5430be3cd)开始。
 
## <a name="identity-and-device-access-recommendations"></a>标识和设备访问建议

Microsoft 提供了一组有关[身份和设备访问](microsoft-365-policies-configurations.md)的建议，以确保全体员工安全且高效地工作。 对于设备访问，请使用以下文章中的建议和设置以及此阶段中的步骤：

- [先决条件](identity-access-prerequisites.md)
- [常见标识和设备访问策略](identity-access-policies.md)

## <a name="how-microsoft-does-device-management-for-microsoft-365"></a>Microsoft 如何将设备管理用于 Microsoft 365

了解 Microsoft IT 专家如何 [使用 EMS 管理设备](https://www.microsoft.com/itshowcase/deploying-and-managing-microsoft-365#primaryR8)。

## <a name="how-contoso-did-device-management-for-microsoft-365"></a>Contoso 如何为 Microsoft 365 进行设备管理

了解 Contoso Corporation （一个虚构但具有代表性的多国企业）如何使用 Microsoft 365 云服务 [部署其移动设备管理基础结构](contoso-mdm.md) 。

![Contoso Corporation](../media/contoso-overview/contoso-icon.png)
