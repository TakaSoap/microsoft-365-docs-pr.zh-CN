---
title: Microsoft 365 业务概述
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.date: 9/20/2018
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
search.appverid:
- BCS160
- MET150
ms.assetid: 496e690b-b75d-4ff5-bf34-cc32905d0364
description: 了解有关 Microsoft 365 业务的详细信息。
ms.openlocfilehash: abd1e8374ef7530a879de71ab7ad0125f1ca4616
ms.sourcegitcommit: 8ca97fa879ae4ea44468be629d6c32b429efeeec
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/16/2019
ms.locfileid: "38676061"
---
# <a name="overview-of-microsoft-365-business"></a>Microsoft 365 业务概述

## <a name="what-is-microsoft-365-business"></a>什么是 Microsoft 365 业务

Microsoft 365 Business 是一款订阅服务，其中包括 Office 365 生产率工具和高级功能，以帮助保护您的业务不受威胁、保护您的数据和管理设备。
  
Microsoft 365 商业版适用于最高300的许可证。 如果你需要更多许可证，请参阅[Microsoft 365 企业版](https://go.microsoft.com/fwlink/p/?linkid=860986)文档以了解详细信息。

有关完整的功能列表，请参阅[Microsoft 365 业务服务说明](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-business-service-description)。
  
## <a name="small-business-security-needs"></a>小型企业安全性需求

您的业务数据可以通过多种方式泄露。 当您使用已损坏的凭据登录或查看不同设备和应用程序上的组织数据时，您和您的用户可能会损害组织的安全性。 更具体地说，你的组织面临的风险来自：

- 已泄露或弱登录凭据。
- 具有弱 pin 的受损设备，或用户拥有的设备。
- 可将组织的数据复制/粘贴或保存到个人应用的用户。
- 安装和使用具有弱安全性的第三方应用程序的用户。
- 电子邮件漏洞，包括共享敏感数据、网络钓鱼尝试、恶意软件等。
- 如果不应的人，则可以使用敏感信息访问文档。

Microsoft 365 商业版可帮助保护其中每个实例中的数据。 下图详细介绍了保护业务数据的安全功能。

![显示 M365B 如何保护您的企业的图。](media/m365businessvalueadd.png)

## <a name="how-your-data-and-devices-are-protected"></a>数据和设备的保护方式

Microsoft 365 Business 通过以下方式帮助**defended 抵御威胁**：

- 实时扫描电子邮件和文档中的链接，以阻止不安全的网站（ATP 安全链接）。

- 在沙盒环境中对电子邮件附件执行高级分析，以检测新开发的恶意软件（ATP 安全附件）。 

- 启用使用机器学习模型和模拟检测的反网络钓鱼策略，以提供针对高级攻击的保护（ATP 反网络钓鱼智能）。 

- 设置禁用来自不受信任位置的访问权限的高级策略，或绕过来自受信任位置（如 office 网络（Azure MFA 包括受信任的 Ip 和条件访问）的多重身份验证。 

- 在组织的所有 Windows 10 设备上强制实施恶意软件保护，并通过勒索软件所做的更改保护关键系统文件夹中的文件（Windows Defender）

您的**业务数据受以下保护**：

- 使用自动检测来帮助防止敏感信息（如社会保险号码或信用卡泄露到公司外部）（数据丢失防护）。 

- 对敏感电子邮件进行加密，以便您可以与组织外部的客户或其他人员进行安全通信。 这样可确保只有预期的收件人才能阅读邮件（Office 365 邮件加密）。

- 通过应用限制（如不**复制**和不**转发**电子邮件和文档（Azure 信息保护、计划1）来控制谁有权访问公司信息。

- 启用无限制云存档，以便您可以保留组织的所有电子邮件，包括以前员工的邮箱（Exchange Online 存档）。

通过以下方式**保护设备**：

- 控制哪些设备和用户可以访问您的 Office 365 数据，以及阻止用户从家庭计算机、未批准的应用程序或工作时间外（有条件访问）登录的选项。

- 应用安全策略以保护 iOS 和 Android 设备上的业务数据。 例如，您可以要求用户提供 PIN 或指纹以访问业务数据，并对移动设备上的数据（Office 相关应用程序保护）进行加密。

- 在批准的 Office 移动应用程序中保留业务文档、电子邮件和其他数据，并防止员工将这些数据保存到未经授权的应用程序和位置（Office 移动应用的应用程序保护）。

- 远程擦除丢失或被盗设备中的业务数据，而不会影响个人信息（Intune 选择性擦除）。

- 使用简化的控件来管理公司中所有 Windows 10 电脑的策略，强制实施 BitLocker 加密并自动安装关键 Windows 更新（强制实施 Windows 更新策略）。

若要查看安全功能的完整列表，请参阅[Microsoft 365 商业安全功能](security-features.md)。 [设置 Microsoft 365 商业](set-up.md)版后，请参阅[设置高级安全策略](set-up-advanced-security.md)以开始使用不作为引导安装程序的一部分的安全功能。 阅读有关如何针对网络罪犯和黑客设置保护的最佳概述，请参阅[保护 Office 365 和 Microsoft 365 商业版计划](https://docs.microsoft.com/office365/admin/security-and-compliance/secure-your-business-data)的十大方法。

## <a name="get-microsoft-365-business"></a>获取 Microsoft 365 商业版

- 如果你有合作伙伴，他们将获得 Microsoft 365 商业版：[从 Microsoft 合作伙伴中心获取 microsoft 365 商业](get-microsoft-365-business.md#get-microsoft-365-business-from-microsoft-partner-center)版。

- 如果你没有合作伙伴并且想要获取 Microsoft 365 商业版，你可以在[此处购买它](https://www.microsoft.com/microsoft-365/business)并按照[注册](sign-up.md)说明进行操作。

- 你还可以转到[Microsoft Store](https://www.microsoft.com/en-us/store/locations/find-a-store?icid=gm_fy18_hol_bopis_feature3&CustomerIntent=Consumer)以购买 Microsoft 365 商业版并获取设置帮助。

    > [!NOTE]
    > 此链接仅适用于美国的商店