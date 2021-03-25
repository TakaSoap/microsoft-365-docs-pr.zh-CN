---
title: 从 Microsoft 365 商业版迁移到 Microsoft 365 E3
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: 5b4ba843-24b8-4526-8e1f-f9b9eab89d06
description: 了解如何将企业从 Microsoft 365 商业高级版移动到 Microsoft 365 E3。
ms.openlocfilehash: 10630671f3deb7eff0ad0f601d301b90743ee35f
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/24/2021
ms.locfileid: "51164505"
---
# <a name="migrate-from-microsoft-365-business-premium-to-microsoft-365-e3"></a>从 Microsoft 365 商业高级版迁移到 Microsoft 365 E3

Microsoft 365 商业高级版具有小型企业所需的一切，将一流的基于云的生产力应用与简单的设备管理和安全性相结合，使员工能够最好地工作。 但在某些情况下，可能需要将 Microsoft 365 商业高级版订阅迁移到 Microsoft 365 E3。 

例如，你的业务已增长，并且需要 300 (许可证，这一点) 。

或者，你的企业需要企业功能，例如 Microsoft 365 企业应用版、Windows 10 企业版 E3 或企业客户端访问许可证 (CAL) 。

升级非常简单：可以从管理中心 [开始升级](../commerce/subscriptions/upgrade-to-different-plan.md)。 将保留当前订阅中所有数据和配置。 除了利用新功能之外，您不执行任何操作来准备迁移，之后不执行任何操作。

>[!Note]
>还可以将 Microsoft 365 商业高级版订阅用于最多 300 个席位，并获取超过 300 个席位的 Microsoft 365 E3 订阅。 但是，Microsoft 365 E3 不包含 Microsoft Defender for Office 365。 若要持续进行威胁防护，应添加其他 Defender for Office 365 许可证，以便许可 Defender for Office 365 政策范围内的所有用户。
>

## <a name="differences-between-microsoft-365-business-premium-and-microsoft-365-enterprise"></a>Microsoft 365 商业高级版和 Microsoft 365 企业版之间的差异

此表显示了 Microsoft 365 商业高级版和 Microsoft 365 E3 之间的差异。

| 功能    | Microsoft 365 商业高级版中的支持    | Microsoft 365 E3 中的支持 | 
|:-------|:-----|:-----|
| **本地**        | | | 
| Windows 10    | Windows 10 企业版  |     Windows 10 企业版 E3| 
| Office 应用*    | [Microsoft 365 商业应用版](#office-365-business)    | Microsoft 365 企业应用版 | 
| **云生产力应用**        | | | 
| Exchange Online 和 Outlook    | 每个邮箱 50 GB 存储限制和无限制 Exchange Online 存档    | 每个邮箱 100 GB 存储限制和无限制 Exchange Online 存档 | 
| Teams    | ![包含在 Microsoft 365 商业高级版中](../media/check-mark.png)    | ![随 Microsoft 365 E3 一起提供](../media/check-mark.png) | 
| OneDrive for Business    | 每个用户 1 TB 存储限制    | 无限制 | 
| Yammer、SharePoint Online、Planner、Stream    | ![包含在 Microsoft 365 商业高级版中](../media/check-mark.png)    | ![随 Microsoft 365 E3 一起提供](../media/check-mark.png) | 
| **威胁防护**        | | | 
| 攻击面减少功能    | [查看此列表](#threat-protection) | Microsoft Edge 基于硬件的隔离的企业管理 | 
| Defender for Office 365 计划 1 | ![包含在 Microsoft 365 商业高级版中](../media/check-mark.png)    | 不包含，但可添加到 | 
| **身份管理**        | | | 
| 混合 Azure Active Directory (Azure AD) 帐户、Azure AD 多重身份验证 (MFA) 、条件访问、本地标识的密码写回|     ![包含在 Microsoft 365 商业高级版中](../media/check-mark.png)    | ![随 Microsoft 365 E3 一起提供](../media/check-mark.png) | 
| Cloud App Discovery， Azure AD Connect Health    |     | ![随 Microsoft 365 E3 一起提供](../media/check-mark.png) | 
| Azure AD Office 365 应用 单一 Sign-On (SSO) ：每个用户 10 个应用 (库 SaaS 应用（如 Salesforce) * | ![包含在 Microsoft 365 商业高级版中](../media/check-mark.png)    | ![随 Microsoft 365 E3 一起提供](../media/check-mark.png) | 
| Azure AD Premium 1 SSO： (Azure AD 应用程序代理和非库应用使用 Azure AD 应用程序集成模板Self-Service本地应用)     |     | ![随 Microsoft 365 E3 一起提供](../media/check-mark.png) | 
| **设备和应用管理**        | | | 
| Microsoft Intune、Windows Autopilot|     ![包含在 Microsoft 365 商业高级版中](../media/check-mark.png)    | ![随 Microsoft 365 E3 一起提供](../media/check-mark.png) | 
|虚拟桌面访问 (VDA)     |  |     ![随 Microsoft 365 E3 一起提供](../media/check-mark.png) | 
|Windows 虚拟桌面 (WVD)     | ![包含在 Microsoft 365 商业高级版中](../media/check-mark.png) |     ![随 Microsoft 365 E3 一起提供](../media/check-mark.png) | 
|共享计算机激活 (SCA)     | ![包含在 Microsoft 365 商业高级版中](../media/check-mark.png) |     ![随 Microsoft 365 E3 一起提供](../media/check-mark.png) | 
| Microsoft 桌面优化程序包    | |     ![随 Microsoft 365 E3 一起提供](../media/check-mark.png) | 
| **信息保护**        | | | 
| Office 365 数据丢失防护、Azure 信息保护计划 1    | ![包含在 Microsoft 365 商业高级版中](../media/check-mark.png)    | ![随 Microsoft 365 E3 一起提供](../media/check-mark.png) | 
| 终结点 DLP 的窗口信息保护    | ![包含在 Microsoft 365 商业高级版中](../media/check-mark.png)    | ![随 Microsoft 365 E3 一起提供](../media/check-mark.png) | 
| **客户端访问许可证 (CAL 权限)**    | | |     
| Enterprise CAL Suite (Exchange、SharePoint、Skype、Windows、Microsoft Endpoint Configuration Manager、Windows Rights Management) | |         ![随 Microsoft 365 E3 一起提供](../media/check-mark.png) | 
| **合规性**        | | | 
| 无限制电子邮件存档    | ![包含在 Microsoft 365 商业高级版中](../media/check-mark.png)    | ![随 Microsoft 365 E3 一起提供](../media/check-mark.png) | 
| 合规性管理器    | ![包含在 Microsoft 365 商业高级版中](../media/check-mark.png)    | ![随 Microsoft 365 E3 一起提供](../media/check-mark.png) | 
| 电子数据展示    | ![包含在 Microsoft 365 商业高级版中](../media/check-mark.png)    | ![随 Microsoft 365 E3 一起提供](../media/check-mark.png) | 
| 就地保留和诉讼保留    | ![包含在 Microsoft 365 商业高级版中](../media/check-mark.png)    | ![随 Microsoft 365 E3 一起提供](../media/check-mark.png) | 
| 邮件传递记录管理 (MRM) 保留标记和保留策略    | ![包含在 Microsoft 365 商业高级版中](../media/check-mark.png)    | ![随 Microsoft 365 E3 一起提供](../media/check-mark.png) | 
||||

\* 已分配 SaaS 应用访问权限的用户可以获取最多 10 个应用的 SSO 访问权限。 管理员可以配置 SSO 并更改用户对不同 SaaS 应用的访问权限，但每次每个用户只能访问 10 个应用。 所有 Office 365 应用都计为单个应用。

## <a name="migration"></a>迁移

若要迁移，请与合作伙伴合作，将 Microsoft 365 商业高级版订阅和许可证迁移到具有其许可证的合适 Microsoft 365 E3 订阅。

以下各节介绍您需要进行哪些更改（如果有）以及您可以在迁移后执行哪些操作。

### <a name="microsoft-365-subscription-configuration-and-data"></a>Microsoft 365 订阅配置和数据

在迁移之前，无需对当前订阅或数据做出任何更改，其中包括：

- 订阅配置，例如 DNS 域名。
- 用户和组帐户以及身份验证设置，如多重身份验证或条件访问策略。
- 生产力服务配置及其数据，例如 Teams、Exchange Online 邮箱、SharePoint Online 网站、OneDrive for Business 文件夹和 OneNote 笔记本。

现在，用户可以在 Exchange Online 邮箱和 OneDrive for Business 文件夹中享受无限存储空间。

你可以开始对 10 多个应用使用 Cloud App Discovery、Azure AD Connect Health 和 SSO。

<a name="threat-protection"></a>
### <a name="threat-protection"></a>威胁防护

Windows 10 商业版本包括以下保护：

- 操作系统启动过程的完整性强制
- 敏感操作组件的完整性实施
- 高级漏洞和零日攻击缓解
- Microsoft Edge、Internet Explorer 和 Chrome 基于信誉的网络保护
- 基于主机的防火墙
- 勒索软件缓解
- Microsoft Edge 基于硬件的隔离
- 由 Intelligent Security Graph 控制的应用程序控制
- USB (设备) 
- 针对基于 Web 的威胁的网络保护
- 主机入侵防护规则

Windows 10 企业版 E3 还包括 Microsoft Edge 基于硬件的隔离的企业管理。

>[!Note]
>迁移到 Microsoft 365 E3 的用户都需要 Microsoft Defender for Office 365 许可证，才能持续进行威胁防护。 请务必购买其他 Defender for Office 365 许可证，以便许可你的 Defender for Office 365 范围内的所有用户。 
>

### <a name="device-management-with-intune"></a>使用 Intune 进行设备管理

在迁移之前，无需对当前的 Intune 配置做出任何更改，其中包括已注册的设备以及设备和应用设置。

### <a name="windows-10"></a>Windows 10

Microsoft 365 商业高级版包括 Windows 10 商业版，你可以将其与 Windows AutoPilot 一起安装。 迁移到 Microsoft 365 E3 时，每个用户许可证都包括 Windows 10 企业版 E3，也可随 Windows Autopilot 一起安装。

<a name="office-365-business"></a>
###  <a name="microsoft-365-apps-for-business"></a>Microsoft 365 商业应用版

设备上安装的 Microsoft 365 商业应用版客户端将自动开始使用 Microsoft 365 企业应用版的功能。 迁移后，你现在可以使用：

 - 组策略支持
 - 电子表格比较和查询
 - 商业智能

