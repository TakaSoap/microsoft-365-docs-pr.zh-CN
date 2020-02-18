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
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: 了解 Contoso 如何使用 Microsoft 365 企业版中的 Microsoft Intune 来管理其设备及其上运行的应用。
ms.openlocfilehash: 7232c89cc105525cc57facd5a1b9de06426adbca
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42068360"
---
# <a name="mobile-device-management-for-contoso"></a>Contoso 移动设备管理

Microsoft 365 企业版包含 Intune 和一组 Azure 服务，可对移动设备和应用程序的管理和安全性进行支持。

Contoso 拥有许多使用移动设备的员工，其中一些人在 Contoso 办公室有办公位，另一些则没有。Contoso 需要通过一种方法来支持员工高效工作，同时确保设备、存储在这些设备上的 Contoso 数据和应用程序行为的安全性。

## <a name="plan"></a>计划

在刚开始分析 Microsoft 365 企业版的移动设备管理时，Contoso 确定了以下 Intune 用例：

- 保护 Exchange Online 电子邮件和数据，以便通过移动设备安全地访问这些内容
- 为 Contoso 员工实施自带设备 (BYOD) 计划
- 向 Contoso 员工发放组织所拥有的手机和使用受限的共享平板电脑

Contoso 并未使用 Intune 来达到以下目的：

- 允许员工从非托管公共网亭安全访问 Office 365
- 保护本地电子邮件和数据，以便通过移动设备安全地访问这些内容，因为他们已不再使用本地 Microsoft Exchange 服务器。

## <a name="deploy"></a>部署

以下是 Contoso 设置其移动设备管理基础结构的方式：

- 将 Intune 设置为移动设备管理 (MDM) 主管应用，并将在 Azure 上使用 Intune 来管理内容和设备
- 创建了用于进行设备注册的 Azure AD 组以及 Intune 设置和基于设备的条件访问策略

  有关详细信息，请参阅 [Contoso 的条件访问策略](contoso-identity.md#conditional-access-policies-for-identity-and-device-access)。

- 启用了 Apple 设备平台以支持员工使用 ipad、iMac、iPhone 和基于 iPhone 的企业所拥有的手机
- 创建了特定于 Contoso 的条款和条件策略，在移动设备上安装 Contoso 的公司门户时会看到这些策略
- 对于未注册的设备，在用户访问 Office 365 服务时，会有一组移动应用程序管理 (MAM) 策略要求进行身份验证
- 创建了强制实施以下内容的 Intune 策略：
  - 允许的应用
  - 设备加密，以帮助防止未经授权的访问
  - 六位数的 PIN 或密码
  - 不活动超时时间
  - 防病毒和恶意软件保护以及通过 Windows Defender 在 Windows 10 设备上的签名更新
  - Windows 10 设备上的自动更新，其中包含最新安全更新
  - 向管理的设备推送证书
  - 商业与个人数据的明确区分。用户或管理员可以选择性地擦除设备中的公司数据，而将图片、个人电子邮件帐户和个人文件等个人数据保持不变。

部署后，Contoso 通过将相应设备添加到适当的 Intune 设备组注册了电脑和公司所拥有的智能手机和平板电脑，然后为员工推出了 BYOD 计划，以注册他们的私人设备。已注册的设备均收到了 Intune 策略，因而可实现对设备及其应用程序的托管和保护。而对于未注册的设备，则会由移动应用程序管理 (MAM) 策略来指定允许的应用程序。

下面是 Contoso 的移动设备管理部署体系结构。

![Contoso 的移动设备管理部署基础结构](../media/contoso-mdm/contoso-mdm-fig1.png)

## <a name="next-step"></a>后续步骤

[了解](contoso-info-protect.md) Contoso 如何使用 Microsoft 365 企业版的信息保护功能来分类、标识和保护其整个组织内的重要数字资产。

## <a name="see-also"></a>另请参阅

[Microsoft 365 企业版移动设备管理](mobility-infrastructure.md)

[部署指南](deploy-microsoft-365-enterprise.md)

[测试实验室指南](m365-enterprise-test-lab-guides.md)

