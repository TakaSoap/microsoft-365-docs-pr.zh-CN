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
description: 了解如何将企业从 Microsoft 365 商业高级版迁移到 Microsoft 365 E3。
ms.openlocfilehash: 3f1bb9591e1bd2bac49326325ce6c8c2d6778497
ms.sourcegitcommit: c1dd5be42fe0c5dcc7c05817c941edd9076febf8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2020
ms.locfileid: "49558230"
---
# <a name="migrate-from-microsoft-365-business-premium-to-microsoft-365-e3"></a>从 Microsoft 365 商业高级版迁移到 Microsoft 365 E3

Microsoft 365 商业高级版为小型企业提供了所需的一切，并将一流的基于云的工作效率应用与简单的设备管理和安全性结合起来，使员工能够完成其最佳工作。 但在某些情况下，您可能需要将 Microsoft 365 商业高级版订阅迁移到 Microsoft 365 E3。 

例如，您的企业已增长并需要300个以上的许可证 (祝贺，) 。

或者，您的业务需要企业版功能，如适用于企业的 Microsoft 365 应用、Windows 10 企业版 E3 或企业客户端访问许可证 (Cal) 。

升级非常简单：您可以 [从管理中心](../commerce/subscriptions/upgrade-to-different-plan.md)启动升级。 保留当前订阅中的所有数据和配置。 除了利用新功能之外，无需为迁移做准备，也不做任何操作。

>[!Note]
>您还可以使用 Microsoft 365 商业高级订阅进行最多300个座位，并获取 Microsoft 365 E3 订阅，以获得超过300的座位。 但是 microsoft Defender for Office 365 不包含在 Microsoft 365 E3 中。 若要继续进行威胁防护，应添加其他适用于 Office 365 许可证的 Defender，以便许可证范围365内的所有用户都已获得许可。
>

## <a name="differences-between-microsoft-365-business-premium-and-microsoft-365-enterprise"></a>Microsoft 365 商业高级版与 Microsoft 365 企业版之间的区别

此表显示了 Microsoft 365 商业高级版和 Microsoft 365 E3 之间的差异。

| 功能    | Microsoft 365 商业高级版中的支持    | Microsoft 365 E3 中的支持 | 
|:-------|:-----|:-----|
| **本地**        | | | 
| Windows 10    | Windows 10 企业版  |     Windows 10 企业版 E3| 
| Office 应用程序 *    | [Microsoft 365 商业应用版](#office-365-business)    | Microsoft 365 企业应用版 | 
| **云生产力应用程序**        | | | 
| Exchange Online 和 Outlook    | 每个邮箱 50 GB 存储限制和不受限制的 Exchange Online 存档    | 每个邮箱 100 GB 存储限制和不受限制的 Exchange Online 存档 | 
| Teams    | ![包含在 Microsoft 365 商业高级版中](../media/check-mark.png)    | ![包含在 Microsoft 365 E3 中](../media/check-mark.png) | 
| OneDrive for Business    | 每个用户 1 TB 存储限制    | 无限制 | 
| Yammer、SharePoint Online、Planner、Stream    | ![包含在 Microsoft 365 商业高级版中](../media/check-mark.png)    | ![包含在 Microsoft 365 E3 中](../media/check-mark.png) | 
| MileIQ    | ![包含在 Microsoft 365 商业高级版中](../media/check-mark.png)    | | 
| **威胁防护**        | | | 
| 攻击面减少功能    | [查看此列表](#threat-protection) | Microsoft Edge 基于硬件的隔离的企业管理 | 
| 适用于 Office 的 Defender 365 计划1 | ![包含在 Microsoft 365 商业高级版中](../media/check-mark.png)    | 不包括在内，但可以添加到 | 
| **身份管理**        | | | 
| 混合 Azure Active Directory 的自助服务密码重置 (Azure AD) 帐户、Azure AD 多重身份验证 (MFA) 、条件访问、本地标识的密码写回|     ![包含在 Microsoft 365 商业高级版中](../media/check-mark.png)    | ![包含在 Microsoft 365 E3 中](../media/check-mark.png) | 
| 云应用发现、Azure AD Connect Health    |     | ![包含在 Microsoft 365 E3 中](../media/check-mark.png) | 
| Azure AD Office 365 应用程序单一 Sign-On (SSO) ：每个用户10个应用程序 (库 SaaS 应用程序（如 Salesforce) ） * | ![包含在 Microsoft 365 商业高级版中](../media/check-mark.png)    | ![包含在 Microsoft 365 E3 中](../media/check-mark.png) | 
| Azure AD Premium 1 SSO：通过使用 Self-Service 应用集成模板的 Azure AD 应用程序代理和非库应用程序 (本地应用程序不受限制)     |     | ![包含在 Microsoft 365 E3 中](../media/check-mark.png) | 
| **设备和应用程序管理**        | | | 
| Microsoft Intune、Windows Autopilot|     ![包含在 Microsoft 365 商业高级版中](../media/check-mark.png)    | ![包含在 Microsoft 365 E3 中](../media/check-mark.png) | 
|虚拟桌面访问 (VDA)     |  |     ![包含在 Microsoft 365 E3 中](../media/check-mark.png) | 
|Windows 虚拟桌面 (WVD)     | ![包含在 Microsoft 365 商业高级版中](../media/check-mark.png) |     ![包含在 Microsoft 365 E3 中](../media/check-mark.png) | 
| (SCA) 的共享计算机激活    | ![包含在 Microsoft 365 商业高级版中](../media/check-mark.png) |     ![包含在 Microsoft 365 E3 中](../media/check-mark.png) | 
| Microsoft 桌面优化包    | |     ![包含在 Microsoft 365 E3 中](../media/check-mark.png) | 
| **信息保护**        | | | 
| Office 365 数据丢失防护，Azure 信息保护计划1    | ![包含在 Microsoft 365 商业高级版中](../media/check-mark.png)    | ![包含在 Microsoft 365 E3 中](../media/check-mark.png) | 
| Endpoint DLP 的窗口信息保护    | ![包含在 Microsoft 365 商业高级版中](../media/check-mark.png)    | ![包含在 Microsoft 365 E3 中](../media/check-mark.png) | 
| **客户端访问许可证 (CAL 权限)**    | | |     
| 企业 CAL 套件 (Exchange、SharePoint、Skype、Windows、Microsoft 终结点配置管理器、Windows 权限管理) | |         ![包含在 Microsoft 365 E3 中](../media/check-mark.png) | 
| **合规性**        | | | 
| 无限制的电子邮件存档    | ![包含在 Microsoft 365 商业高级版中](../media/check-mark.png)    | ![包含在 Microsoft 365 E3 中](../media/check-mark.png) | 
| 合规性管理器    | ![包含在 Microsoft 365 商业高级版中](../media/check-mark.png)    | ![包含在 Microsoft 365 E3 中](../media/check-mark.png) | 
| 电子数据展示    | ![包含在 Microsoft 365 商业高级版中](../media/check-mark.png)    | ![包含在 Microsoft 365 E3 中](../media/check-mark.png) | 
| 就地保留和诉讼保留    | ![包含在 Microsoft 365 商业高级版中](../media/check-mark.png)    | ![包含在 Microsoft 365 E3 中](../media/check-mark.png) | 
| 邮件记录管理 (MRM) 保留标记和保留策略    | ![包含在 Microsoft 365 商业高级版中](../media/check-mark.png)    | ![包含在 Microsoft 365 E3 中](../media/check-mark.png) | 
||||

\* 分配了对 SaaS 应用程序的访问权限的用户可以获取最大10个应用程序的 SSO 访问权限。 管理员可以配置 SSO 并更改用户对不同 SaaS 应用程序的访问权限，但每次仅允许对每个用户的10个应用程序进行 SSO 访问。 所有 Office 365 应用程序均计为一个应用程序。

## <a name="migration"></a>迁移

若要迁移，请与合作伙伴合作以将 Microsoft 365 商业高级订阅和许可证移动到合适的 Microsoft 365 E3 订阅及其许可证。

以下各节介绍了需要进行哪些更改（如果有），以及迁移后可以执行的操作。

### <a name="microsoft-365-subscription-configuration-and-data"></a>Microsoft 365 订阅配置和数据

您无需在迁移之前对当前订阅或数据进行任何更改，其中包括：

- 订阅配置，如 DNS 域名。
- 用户和组帐户以及身份验证设置，例如多重因素身份验证或条件访问策略。
- 生产率服务配置及其数据，如团队、Exchange Online 邮箱、SharePoint Online 网站、OneDrive for Business 文件夹和 OneNote 笔记本。

现在，你的用户可以在 Exchange Online 邮箱和 OneDrive for business 文件夹中享受无限存储。

您可以开始对10个以上的应用程序使用云应用发现、Azure AD Connect Health 和 SSO。

>[!Note]
>迁移到 Microsoft 365 E3 的用户无法再使用 MileIQ。
>

<a name="threat-protection"></a>
### <a name="threat-protection"></a>威胁防护

Windows 10 商业版包括以下保护：

- 操作系统启动过程的完整性强制实施
- 敏感操作组件的完整性实施
- 高级漏洞和零日利用缓解措施
- Microsoft Edge、Internet Explorer 和 Chrome 的基于信誉的网络保护
- 基于主机的防火墙
- 勒索软件缓解
- Microsoft Edge 的基于硬件的隔离
- 由智能安全图形支持的应用程序控制
-  (USB) 的设备控件
- 基于 web 的威胁的网络保护
- 主机入侵防护规则

Windows 10 企业版 E3 还包括针对 Microsoft Edge 的基于硬件的隔离的企业管理。

>[!Note]
>迁移到 Microsoft 365 E3 的用户每个用户都需要 Microsoft Defender for Office 365 许可证，以实现持续的威胁防护。 请务必购买适用于 Office 365 许可证的其他 Defender，以便许可证中所有用户的 Office 365 策略。 
>

### <a name="device-management-with-intune"></a>使用 Intune 的设备管理

您无需在迁移前对当前 Intune 配置进行任何更改，包括注册的设备和设备以及应用程序设置。

### <a name="windows-10"></a>Windows 10

Microsoft 365 商业高级版包括 Windows 10 商业版，可以通过 Windows AutoPilot 安装。 在迁移到 Microsoft 365 E3 时，每个用户许可证都包含 Windows 10 企业版 E3，您还可以使用 Windows Autopilot 进行安装。

<a name="office-365-business"></a>
###  <a name="microsoft-365-apps-for-business"></a>Microsoft 365 商业应用版

你的设备上安装的 Microsoft 365 应用程序业务客户端将自动开始使用适用于企业的 Microsoft 365 应用程序的功能。 迁移之后，您现在可以使用：

 - 通过组策略激活卷
 - 应用遥测
 - 更新控件
 - 电子表格比较和查询
 - 商业智能

