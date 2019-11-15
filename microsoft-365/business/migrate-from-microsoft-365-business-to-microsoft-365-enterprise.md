---
title: 从 Microsoft 365 Business 迁移到 Microsoft 365 企业版
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
search.appverid:
- BCS160
- MET150
ms.assetid: 5b4ba843-24b8-4526-8e1f-f9b9eab89d06
description: 了解如何将企业从 Microsoft 365 企业移动到 Microsoft 365 企业版 E3。
ms.openlocfilehash: 77760aa8ea5b79f39d4c069d86e79a3cec6844e9
ms.sourcegitcommit: 2c2248b03f7753d64490f2f7e56ec644a235b65a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/15/2019
ms.locfileid: "38640781"
---
# <a name="migrate-from-microsoft-365-business-to-microsoft-365-enterprise-e3"></a>从 Microsoft 365 企业版迁移至 Microsoft 365 企业版 E3

Microsoft 365 商业版为小型企业提供了所需的一切，将同类最佳的基于云的工作效率应用与简单的设备管理和安全性相结合，使员工能够完成其最佳工作。 但在某些情况下，可能需要将 Microsoft 365 业务订阅迁移到 Microsoft 365 企业版。 

例如，您的企业增长并需要300以上的许可证（顺便说一下）。

或者，您的业务需要企业版功能，如 Office 365 专业增强版、Windows 10 企业版 E3 或企业客户端访问许可证（Cal）。

升级非常简单：您可以[从管理中心](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/upgrade-to-different-plan?view=o365-worldwide)启动升级。 保留当前订阅中的所有数据和配置。 除了利用新功能之外，无需为迁移做准备，也不做任何操作。 

>[!Note]
>您还可以使用 Microsoft 365 商业版订阅进行最多300个座位，并获取 Microsoft 365 企业版 E3 订阅（适用于超过300的座位）。 但是，Office 365 ATP 不包含在 Microsoft 365 企业版 E3 中。 若要持续进行威胁防护，应添加其他 Office 365 ATP 许可证，以便许可证365范围内的所有用户都可以获得许可。
>

## <a name="differences-between-microsoft-365-business-and-microsoft-365-enterprise"></a>Microsoft 365 商业版与 Microsoft 365 企业版之间的区别

此表显示了 Microsoft 365 商业版和 Microsoft 365 企业版 E3 之间的差异。

| 功能   | Microsoft 365 商业版中的支持 | Microsoft 365 企业版 E3 中的支持 | 
|:-------|:-----|:-----|
| **本地**       | | | 
| Windows 10    | Windows 10 企业版  |    Windows 10 企业版 E3| 
| Office 应用程序 *  | [Office 365 商业版](#office-365-business)   | Office 365 专业增强版 | 
| **云生产力应用程序**       | | | 
| Exchange Online 和 Outlook   | 每个邮箱 50 GB 存储限制和不受限制的 Exchange Online 存档   | 每个邮箱 100 GB 存储限制和不受限制的 Exchange Online 存档 | 
| Teams | ![包含在 Microsoft 365 商业版中](./media/check-mark.png)   | ![包含在 Microsoft 365 企业版 E3 中](./media/check-mark.png) | 
| OneDrive for Business | 每个用户 1 TB 存储限制   | 无限制 | 
| Yammer、SharePoint Online、Planner、Stream    | ![包含在 Microsoft 365 商业版中](./media/check-mark.png)   | ![包含在 Microsoft 365 企业版 E3 中](./media/check-mark.png) | 
| StaffHub  | ![包含在 Microsoft 365 商业版中](./media/check-mark.png)   | ![包含在 Microsoft 365 企业版 E3 中](./media/check-mark.png) | 
| Outlook 客户管理器，MileIQ  | ![包含在 Microsoft 365 商业版中](./media/check-mark.png)   | | 
| **威胁防护**     | | | 
| 攻击面减少功能 | [查看此列表](#threat-protection) | Microsoft Edge 基于硬件的隔离的企业管理 | 
| Office 365 高级威胁防护（ATP）计划1 | ![包含在 Microsoft 365 商业版中](./media/check-mark.png)  | 不包括在内，但可以添加到 | 
| **身份管理**       | | | 
| 混合 Azure Active Directory （Azure AD）帐户、Azure 多重身份验证（MFA）、条件访问、本地标识的密码写回的自助密码重置|    ![包含在 Microsoft 365 商业版中](./media/check-mark.png) | ![包含在 Microsoft 365 企业版 E3 中](./media/check-mark.png) | 
| 云应用发现、Azure AD Connect Health  |   | ![包含在 Microsoft 365 企业版 E3 中](./media/check-mark.png) | 
| Azure AD Office 365 应用单一登录（SSO）：每个用户10个应用程序（库 SaaS 应用程序，如 Salesforce） * | ![包含在 Microsoft 365 商业版中](./media/check-mark.png) | ![包含在 Microsoft 365 企业版 E3 中](./media/check-mark.png) | 
| Azure AD Premium 1 SSO：无限制（通过使用自助式应用集成模板的 Azure AD 应用程序代理和非库应用的内部部署应用）  |   | ![包含在 Microsoft 365 企业版 E3 中](./media/check-mark.png) | 
| **设备和应用程序管理**     | | | 
| Microsoft Intune、Windows Autopilot|  ![包含在 Microsoft 365 商业版中](./media/check-mark.png) | ![包含在 Microsoft 365 企业版 E3 中](./media/check-mark.png) | 
|虚拟桌面访问（VDA）   |  |    ![包含在 Microsoft 365 企业版 E3 中](./media/check-mark.png) | 
|Windows 虚拟桌面（WVD）  | ![包含在 Microsoft 365 商业版中](./media/check-mark.png) |     ![包含在 Microsoft 365 企业版 E3 中](./media/check-mark.png) | 
|共享计算机激活（SCA）   | ![包含在 Microsoft 365 商业版中](./media/check-mark.png) |     ![包含在 Microsoft 365 企业版 E3 中](./media/check-mark.png) | 
| Microsoft 桌面优化包    | |     ![包含在 Microsoft 365 企业版 E3 中](./media/check-mark.png) | 
| **信息保护**        | | | 
| Office 365 数据丢失防护，Azure 信息保护计划1  | ![包含在 Microsoft 365 商业版中](./media/check-mark.png)   | ![包含在 Microsoft 365 企业版 E3 中](./media/check-mark.png) | 
| Endpoint DLP 的窗口信息保护    | ![包含在 Microsoft 365 商业版中](./media/check-mark.png)   | ![包含在 Microsoft 365 企业版 E3 中](./media/check-mark.png) | 
| **客户端访问许可证（CAL 权限）**    | | |   
| 企业 CAL 套件（Exchange、SharePoint、Skype、Windows、System Center Configuration Manager、Windows 权限管理）| |        ![包含在 Microsoft 365 企业版 E3 中](./media/check-mark.png) | 
| **Compliance**        | | | 
| 无限制的电子邮件存档 | ![包含在 Microsoft 365 商业版中](./media/check-mark.png)   | ![包含在 Microsoft 365 企业版 E3 中](./media/check-mark.png) | 
| 合规性管理器    | ![包含在 Microsoft 365 商业版中](./media/check-mark.png)   | ![包含在 Microsoft 365 企业版 E3 中](./media/check-mark.png) | 
| 电子数据展示    | ![包含在 Microsoft 365 商业版中](./media/check-mark.png)   | ![包含在 Microsoft 365 企业版 E3 中](./media/check-mark.png) | 
| 就地保留和诉讼保留 | ![包含在 Microsoft 365 商业版中](./media/check-mark.png)   | ![包含在 Microsoft 365 企业版 E3 中](./media/check-mark.png) | 
| 邮件记录管理（MRM）保留标记和保留策略  | ![包含在 Microsoft 365 商业版中](./media/check-mark.png)   | ![包含在 Microsoft 365 企业版 E3 中](./media/check-mark.png) | 
||||

\*分配了对 SaaS 应用程序的访问权限的用户可以获取最大10个应用程序的 SSO 访问权限。 管理员可以配置 SSO 并更改用户对不同 SaaS 应用程序的访问权限，但每次仅允许对每个用户的10个应用程序进行 SSO 访问。 所有 Office 365 应用程序均计为一个应用程序。

## <a name="migration"></a>迁移

若要迁移，请与合作伙伴合作以将 Microsoft 365 业务订阅和许可证移动到合适的 Microsoft 365 企业版 E3 订阅及其许可证。

以下各节介绍了需要进行哪些更改（如果有），以及迁移后可以执行的操作。

### <a name="microsoft-365-subscription-configuration-and-data"></a>Microsoft 365 订阅配置和数据

您无需在迁移之前对当前订阅或数据进行任何更改，其中包括：

- 订阅配置，如 DNS 域名。
- 用户和组帐户以及身份验证设置，例如多重因素身份验证或条件访问策略。
- 生产率服务配置及其数据，如团队、Exchange Online 邮箱、SharePoint Online 网站、OneDrive for Business 文件夹和 OneNote 笔记本。

现在，你的用户可以在 Exchange Online 邮箱和 OneDrive for business 文件夹中享受无限存储。

您可以开始对10个以上的应用程序使用云应用发现、Azure AD Connect Health 和 SSO。

>[!Note]
>迁移到 Microsoft 365 企业版 E3 的用户无法再使用 Outlook 客户管理器和 MileIQ。
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
- 设备控制（USB）
- 基于 web 的威胁的网络保护
- 主机入侵防护规则

Windows 10 企业版 E3 还包括针对 Microsoft Edge 的基于硬件的隔离的企业管理。

>[!Note]
>迁移到 Microsoft 365 企业版 E3 的用户每个用户都需要一个 Office 365 ATP 许可证以实现持续的威胁防护。 请务必购买其他 Office 365 ATP 许可证，以便许可的 Office 365 ATP 策略范围内的所有用户。 
>

### <a name="device-management-with-intune"></a>使用 Intune 的设备管理

您无需在迁移前对当前 Intune 配置进行任何更改，包括注册的设备和设备以及应用程序设置。

### <a name="windows-10"></a>Windows 10

Microsoft 365 Business 包括 Windows 10 商业版，可以通过 Windows AutoPilot 安装。 当迁移到 Microsoft 365 企业版 E3 时，每个用户许可证都包含 Windows 10 企业版 E3，您还可以使用 Windows Autopilot 进行安装。

<a name="office-365-business"></a>
### <a name="office-365-business"></a>Office 365 商业版

您的设备上安装的 Office 365 业务客户端将自动开始使用 Office 365 专业增强版的功能。 迁移之后，您现在可以使用：

 - 通过组策略激活卷
 - 应用遥测
 - 更新控件
 - 电子表格比较和查询
 - 商业智能

