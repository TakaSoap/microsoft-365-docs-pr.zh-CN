---
title: 使用 Microsoft 365 为远程工作者提供强大帮助
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 06/03/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- remotework
- M365solutions
ms.custom: ''
description: 配置安全和服务基础结构，使你的员工能够随时随地进行远程工作。
ms.openlocfilehash: 763c8e745eb54897c1df88ecb5a9064987ed5a13
ms.sourcegitcommit: 9195c83c725a7e6ed395ce0253304da54e2195f0
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/04/2020
ms.locfileid: "44560456"
---
# <a name="empower-remote-workers-with-microsoft-365"></a>使用 Microsoft 365 为远程工作者提供强大帮助

企业可能需要让员工能够从家中安全地访问组织的本地和基于云的信息、工具和资源。 对于许多组织而言，允许员工在离开办公室时无缝、安全地工作非常重要，这有助于：

- 节省办公空间。
- 聘用并留住不愿意调动的员工。
- 减少员工通勤，让他们有更多的时间来提高工作效率并在工作之外进行减压活动。

远程工作（也称为远程办公）可以涵盖以下对象：

- 偶尔离开办公室参加会议或客户会议的员工。
- 一些远程工作的全职员工。
- 没有办公室且所有员工均为远程员工的完全远程运作的组织。

远程员工必须能够随时随地访问：

- 组织资源，例如由本地应用程序数据中心提供的资源。
- Microsoft 365 订阅中基于云的服务和数据，如 Teams、Exchange Online、SharePoint 和 OneDrive。

为获得无缝登录体验，应将 Active Directory 域服务 (AD DS) 用户帐户与 Azure Active Directory (Azure AD) 同步。 若要保护 Windows 10 设备，应在 Intune 中对其进行注册。 下面是基础结构的高级视图。

![面向使用 Microsoft 365 的远程工作者的基本基础结构](../media/empower-people-to-work-remotely/remote-workers-basic-infrastructure.png)


为了支持远程工作者（例如，为了应对 COVID-19 危机），Microsoft 365 中的功能组合可使远程工作者采用高度协作的方式开展工作，例如：

- 在线会议和聊天会话。
- 基于云的文件存储的共享工作区，可实现全球可访问性和实时协作。
- 用于划分工作并完成任务的共享任务和工作流。

为实现强大的安全性，Microsoft 365 包括：

- 强制实施的身份验证要求，用于检测和响应高风险的登录，以及阻止所选应用和不合规的设备。
- 在云中加密的连接和数字资产。
- 用于定义谁可以对文件执行哪些操作的权限。
- 保护 Windows 10 设备的全面安全功能。

若要满足针对远程工作者的这些条件，请使用以下 Microsoft 365 功能和特性。

| 功能或特性 | 说明 | 许可 |
|:-------|:-----|:-------|
| 通过安全性默认设置强制执行 MFA   | 通过请求第二种形式的登录身份验证，抵御遭到入侵的身份和设备的威胁。安全性默认设置要求对所有用户帐户进行 MFA。   | Microsoft 365 E3 和 E5 |
| 通过条件访问强制执行 MFA| 要求基于使用条件访问策略的登录的属性进行 MFA。    | Microsoft 365 E3 和 E5 | 
| 通过基于风险的条件访问强制执行 MFA   | 需要基于使用 Azure 高级威胁防护的用户登录的风险进行 MFA。 | Microsoft 365 E5 或 E3（含 Azure AD Premium P2 许可） | 
| 自助服务密码重置 (SSPR)    | 允许用户重置或解锁其密码或帐户。  | Microsoft 365 E3 和 E5 |
| Azure AD 应用程序代理    | 为 Intranet 服务器上托管的基于 Web 的应用程序提供安全的远程访问权限。   | 需要单独的付费 Azure 订阅 |
| 配置点到站点 VPN   | 通过 Azure 虚拟网络创建从远程工作者的设备到 intranet 的安全连接。   | 需要单独的付费 Azure 订阅 |
| Windows 虚拟桌面   | 支持只能将其个人和非托管设备与在 Azure 中运行的虚拟桌面配合使用的远程工作者。 | 需要单独的付费 Azure 订阅 |
| 远程桌面服务 (RDS) | 允许员工通过 Intranet 连接到基于 Windows 的计算机。 | Microsoft 365 E3 和 E5 | 
| 远程桌面服务网关   | 加密通信，防止 RDS 主机直接向 Internet 公开。 | 需要单独的 Windows Server 许可证 |
| Microsoft Intune | 管理设备和应用程序。   | Microsoft 365 E3 和 E5 | 
| Configuration Manager | 管理设备上的软件安装、更新和设置 | 需要单独的 Configuration Manager 许可证 |
| 桌面分析 | 确定你的 Windows 客户端的更新准备情况。   | 需要单独的 Configuration Manager 许可证 |
| Windows Autopilot | 设置和预配置新的 Windows 10 设备，以便高效使用。   | Microsoft 365 E3 和 E5 |
| Microsoft Teams、Exchange Online、SharePoint Online 和 OneDrive、Microsoft 365 应用版、Microsoft Power Platform、Yammer、Power Apps | 创建、沟通和协作。 | Microsoft 365 E3 和 E5 |
||||

使用以下步骤来保护和优化对组织的服务器、数据和云服务的访问，并实现最大的工作效率。

1. [借助 MFA 提升登录安全性](empower-people-to-work-remotely-secure-sign-in.md)
2. [提供对本地应用和服务的远程访问权限](empower-people-to-work-remotely-remote-access.md)
3. [部署设备、电脑和其他终结点的终结点管理](empower-people-to-work-remotely-manage-endpoints.md)
4. [部署远程工作者生产力应用和服务](empower-people-to-work-remotely-teams-productivity-apps.md)
5. [创建交流平台](empower-people-to-work-remotely-communication-venues.md)
6. [培训远程工作者和处理使用情况反馈](empower-people-to-work-remotely-train-monitor-usage.md)

![使用 Microsoft 365 为远程工作者提供帮助的步骤](../media/empower-people-to-work-remotely/remote-workers-step-grid.png)

有关 Microsoft 提供的关于支持远程工作者的最新信息，请参阅[启用远程工作技术社区网站](https://resources.techcommunity.microsoft.com/enabling-remote-work/)。
