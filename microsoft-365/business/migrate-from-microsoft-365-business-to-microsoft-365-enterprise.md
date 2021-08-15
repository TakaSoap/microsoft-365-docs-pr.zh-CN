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
description: 了解如何将业务从Microsoft 365 商业高级版移动到Microsoft 365 E3。
ms.openlocfilehash: d3030518f7f4467c7b2e16897dc7b100764d9d5a36c50169b58f1adcd7bef209
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "53837617"
---
# <a name="migrate-from-microsoft-365-business-premium-to-microsoft-365-e3"></a>从 Microsoft 365 商业高级版迁移到 Microsoft 365 E3

Microsoft 365 商业高级版你的小型企业所需的一切，将一流的基于云的生产力应用与简单的设备管理和安全性相结合，使员工能够最好地完成自己的工作。 但是，在某些情况下，可能需要将你的 Microsoft 365 商业高级版 订阅迁移到Microsoft 365 E3。

例如，你的业务已增长，并且需要 300 (许可证，这一点) 。

或者，您的业务需要企业功能，如 Microsoft 365 企业应用版、Windows 10 企业版 E3 或 Enterprise 客户端访问许可证 (CAL) 。

升级非常简单：可以从管理中心 [开始升级](../commerce/subscriptions/upgrade-to-different-plan.md)。 将保留当前订阅中所有数据和配置。 除了利用新功能之外，您不执行任何操作来准备迁移，之后不执行任何操作。

> [!NOTE]
> 您还可以使用最多 300 个席位的 Microsoft 365 商业高级版 订阅，并获取超过 300 Microsoft 365 E3的订阅。 但是，Microsoft Defender for Office 365不包含在 Microsoft 365 E3 中。 为了持续进行威胁防护，你应该添加其他 Defender for Office 365 许可证，以便你的 Defender for Office 365 范围内的所有用户都获得许可。

## <a name="differences-between-microsoft-365-business-premium-and-microsoft-365-enterprise"></a>Microsoft 365 商业高级版和Microsoft 365 企业版

此表显示了 Microsoft 365 商业高级版 和 Microsoft 365 E3。

| 功能    | 支持Microsoft 365 商业高级版    | 支持Microsoft 365 E3 |
|:-------|:-----|:-----|
| **本地**        | | |
| Windows 10    | Windows 10 企业版  |     Windows 10 企业版E3|
| Office应用*    | [Microsoft 365 商业应用版](#office-365-business)    | Microsoft 365 企业应用版 |
| **云生产力应用**        | | |
| Exchange Online 和 Outlook    | 每个邮箱 50 GB 存储限制和无限制Exchange Online存档    | 每个邮箱 100 GB 存储限制和无限制Exchange Online存档 |
| Teams    | ![包含在Microsoft 365 商业高级版](../media/check-mark.png)    | ![包含在Microsoft 365 E3](../media/check-mark.png) |
| OneDrive for Business    | 每个用户 1 TB 存储限制    | 无限制 |
| Yammer、SharePoint Online、Planner、Stream    | ![包含在Microsoft 365 商业高级版](../media/check-mark.png)    | ![包含在Microsoft 365 E3](../media/check-mark.png) |
| **威胁防护**        | | |
| 攻击面减少功能    | [查看此列表](#threat-protection) | Enterprise基于硬件的隔离的管理Microsoft Edge |
| Defender for Office 365 计划 1 | ![包含在Microsoft 365 商业高级版](../media/check-mark.png)    | 不包含，但可添加到 |
| **身份管理**        | | |
| Azure AD) 帐户的混合 Azure Active Directory (自助服务密码重置、Azure AD 多重身份验证 (MFA) 、条件访问、本地标识的密码写回|     ![包含在Microsoft 365 商业高级版](../media/check-mark.png)    | ![包含在Microsoft 365 E3](../media/check-mark.png) |
| Cloud App Discovery， Azure AD 连接 Health    |     | ![包含在Microsoft 365 E3](../media/check-mark.png) |
| Azure AD Office 365 应用 单一Sign-On (SSO) ：每个用户 10 个应用 (库 SaaS 应用，如 Salesforce) * | ![包含在Microsoft 365 商业高级版](../media/check-mark.png)    | ![包含在Microsoft 365 E3](../media/check-mark.png) |
| Azure AD Premium 1 个 SSO： (Azure AD 应用程序代理和非库应用使用 Azure AD 应用程序集成模板Self-Service本地应用)     |     | ![包含在Microsoft 365 E3](../media/check-mark.png) |
| **设备和应用管理**        | | |
| Microsoft Intune、Windows Autopilot|     ![包含在Microsoft 365 商业高级版](../media/check-mark.png)    | ![包含在Microsoft 365 E3](../media/check-mark.png) |
|虚拟桌面访问 (VDA)     |  |     ![包含在Microsoft 365 E3](../media/check-mark.png) |
|Windows虚拟桌面 (WVD)     | ![包含在Microsoft 365 商业高级版](../media/check-mark.png) |     ![包含在Microsoft 365 E3](../media/check-mark.png) |
|共享计算机激活 (SCA)     | ![包含在Microsoft 365 商业高级版](../media/check-mark.png) |     ![包含在Microsoft 365 E3](../media/check-mark.png) |
| Microsoft 桌面优化程序包    | |     ![包含在Microsoft 365 E3](../media/check-mark.png) |
| **信息保护**        | | |
| Office 365数据丢失防护、Azure 信息保护计划 1    | ![包含在Microsoft 365 商业高级版](../media/check-mark.png)    | ![包含在Microsoft 365 E3](../media/check-mark.png) |
| 终结点 DLP 的窗口信息保护    | ![包含在Microsoft 365 商业高级版](../media/check-mark.png)    | ![包含在Microsoft 365 E3](../media/check-mark.png) |
| **客户端访问许可证 (CAL 权限)**    | | |
| EnterpriseCAL Suite (Exchange、SharePoint、Skype、Windows、Microsoft Endpoint Configuration Manager、Windows Rights Management) | |         ![包含在Microsoft 365 E3](../media/check-mark.png) |
| **合规性**        | | |
| 无限制电子邮件存档    | ![包含在Microsoft 365 商业高级版](../media/check-mark.png)    | ![包含在Microsoft 365 E3](../media/check-mark.png) |
| 合规性管理器    | ![包含在Microsoft 365 商业高级版](../media/check-mark.png)    | ![包含在Microsoft 365 E3](../media/check-mark.png) |
| 电子数据展示    | ![包含在Microsoft 365 商业高级版](../media/check-mark.png)    | ![包含在Microsoft 365 E3](../media/check-mark.png) |
| 就地保留和诉讼保留    | ![包含在Microsoft 365 商业高级版](../media/check-mark.png)    | ![包含在Microsoft 365 E3](../media/check-mark.png) |
| 邮件传递记录管理 (MRM) 保留标记和保留策略    | ![包含在Microsoft 365 商业高级版](../media/check-mark.png)    | ![包含在Microsoft 365 E3](../media/check-mark.png) |
||||

\* 已分配 SaaS 应用访问权限的用户可以获取最多 10 个应用的 SSO 访问权限。 管理员可以配置 SSO 并更改用户对不同 SaaS 应用的访问权限，但每次每个用户只能访问 10 个应用。 所有Office 365应用都计为单个应用。

## <a name="migration"></a>迁移

若要迁移，请与合作伙伴合作，将你的 Microsoft 365 商业高级版 订阅和许可证移动到Microsoft 365 E3许可证的合适订阅。

以下各节介绍您需要进行哪些更改（如果有）以及您可以在迁移后执行哪些操作。

### <a name="microsoft-365-subscription-configuration-and-data"></a>Microsoft 365订阅配置和数据

在迁移之前，无需对当前订阅或数据做出任何更改，其中包括：

- 订阅配置，例如 DNS 域名。
- 用户和组帐户以及身份验证设置，如多重身份验证或条件访问策略。
- 生产力服务配置及其数据，例如Teams、Exchange Online邮箱、SharePoint Online 网站、OneDrive for Business文件夹OneNote笔记本。

现在，用户可以在邮箱和文件夹中Exchange Online无限制OneDrive for Business存储空间。

你可以开始对 10 多个应用使用 Cloud App Discovery、Azure AD 连接 Health 和 SSO。

<a name="threat-protection"></a>
### <a name="threat-protection"></a>威胁防护

Windows 10 商业版包括以下保护：

- 操作系统启动过程的完整性强制
- 敏感操作组件的完整性实施
- 高级漏洞和零日攻击缓解
- 针对 Microsoft Edge、Internet Explorer 和 Chrome 的基于信誉的网络保护
- 基于主机的防火墙
- 勒索软件缓解
- 基于硬件的隔离Microsoft Edge
- 由智能安全中心控制Graph
- USB (设备) 
- 针对基于 Web 的威胁的网络保护
- 主机入侵防护规则

Windows 10 企业版E3 还包括企业对基于硬件的隔离进行企业Microsoft Edge。

> [!NOTE]
> 迁移到 Microsoft 365 E3 用户都需要 Microsoft Defender for Office 365 许可证，才能持续进行威胁防护。 请务必购买其他 Defender for Office 365 许可证，以便你的 Defender for Office 365 范围内的所有用户都获得许可。

### <a name="device-management-with-intune"></a>使用 Intune 进行设备管理

在迁移之前，无需对当前的 Intune 配置做出任何更改，其中包括已注册的设备以及设备和应用设置。

### <a name="windows-10"></a>Windows 10

Microsoft 365 商业高级版包括Windows 10 商业版，你可以将其与 AutoPilot Windows一起安装。 迁移到 Microsoft 365 E3 时，每个用户许可证Windows 10 企业版 E3，也可以随 Autopilot Windows E3。

<a name="office-365-business"></a>
###  <a name="microsoft-365-apps-for-business"></a>Microsoft 365 商业应用版

设备上Microsoft 365 商业应用版的客户端将自动开始使用 Microsoft 365 企业应用版。 迁移后，你现在可以使用：

- 组策略支持
- 电子表格比较和查询
- 商业智能
