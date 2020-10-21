---
title: Contoso 移动设备管理
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 10/01/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: 了解 Contoso 如何使用 Microsoft 365 for enterprise 中的 Microsoft Intune 来管理其设备以及在其上运行的应用程序。
ms.openlocfilehash: d3f973827a9b05a415efe9225a2bdb3d83ccaf38
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/21/2020
ms.locfileid: "48649641"
---
# <a name="mobile-device-management-for-contoso"></a>Contoso 移动设备管理

适用于企业的 Microsoft 365 包括 Intune 和一组支持移动设备和应用程序管理和安全性的 Azure 服务。

Contoso 拥有许多启用了移动的员工。有些办公室在 Contoso 位置，有些则没有办事处。Contoso 需要一种方法来实现员工工作效率，但保留设备、存储在这些设备上的 Contoso 数据以及应用程序行为的安全性。

## <a name="plan"></a>计划

Contoso 确定了适用于企业的 Microsoft 365 移动设备管理的以下 Intune 使用案例：

- 保护 Exchange Online 电子邮件和数据，以便移动设备可以安全地访问这些电子邮件和数据。
- 为 Contoso 员工实施现成的设备 (BYOD) 计划。
- 颁发组织拥有的电话，并将共享平板电脑限制为 Contoso 员工。

Contoso 不使用 Intune 执行以下操作：

- 允许员工从非托管的公共展台安全访问 Microsoft 365。
- 保护本地电子邮件和数据，以便移动设备可以安全地访问它，因为没有本地 Microsoft Exchange 服务器。

## <a name="deploy"></a>部署

以下是 Contoso 设置其移动设备管理基础结构的方式：

- 将 Intune 设置为移动设备管理 (MDM) 颁发机构，并在 Azure 上使用 Intune 管理内容并管理设备
- 为用于注册和 Intune 设置的设备的 azure AD) 组和基于设备的条件访问策略创建了 Azure Active Directory (的 Azure AD

  有关详细信息，请参阅 [Contoso 条件访问策略](contoso-identity.md#conditional-access-policies-for-identity-and-device-access)。

- 启用 Apple 设备平台以支持员工使用 Ipad、Imac 和 Iphone 以及公司拥有的 Iphone
- 创建了特定于 Contoso 的条款和条件策略，在移动设备上安装 Contoso 的公司门户时会看到这些策略
- 对于未注册的设备，实现一组移动应用程序管理 (MAM) 策略，以要求对 Microsoft 365 服务的访问进行身份验证
- 创建了强制实施以下内容的 Intune 策略：
  - 允许的应用。
  - 设备加密以帮助防止未经授权的访问。
  - 6位数的 PIN 或密码。
  - 非活动超时时间。
  - Windows 10 设备上的 Windows Defender 的防病毒和恶意软件防护以及签名更新。
  - Windows 10 设备上的自动更新，其中包括最新的安全更新。
  - 将证书推送到托管设备。
  - 商业与个人数据的明确区分。用户或管理员可以选择性地擦除设备中的公司数据，而将图片、个人电子邮件帐户和个人文件等个人数据保持不变。

Contoso 通过将 Pc 和公司拥有的智能手机和平板电脑添加到相应的 Intune 设备组来注册它们。 他们还为员工建立了用于注册其个人设备的 BYOD 计划。 已注册的设备接收 Intune 策略，这将导致受管理和安全的设备及其应用程序。 未注册的设备具有指定允许的应用程序 (MAM) 策略中的移动应用程序管理。

下面是 Contoso 移动设备管理部署体系结构。

![Contoso 移动设备管理部署基础结构](../media/contoso-mdm/contoso-mdm-fig1.png)

## <a name="next-step"></a>后续步骤

[了解](contoso-info-protect.md) Contoso 如何使用 Microsoft 365 for enterprise 的信息保护功能来分类、识别和保护整个组织中的重要数字资产。

## <a name="see-also"></a>另请参阅

[适用于 Microsoft 365 的设备管理](device-management-roadmap-microsoft-365.md)

[Microsoft 365 企业版概述](microsoft-365-overview.md)

[测试实验室指南](m365-enterprise-test-lab-guides.md)

