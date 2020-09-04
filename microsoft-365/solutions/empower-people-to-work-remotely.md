---
title: 使用 Microsoft 365 为远程工作者提供强大帮助
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 07/23/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- remotework
- m365solution-remotework
- m365solution-overview
ms.custom: ''
description: 配置安全和服务基础结构，使你的员工能够随时随地进行远程工作。
ms.openlocfilehash: 17cc826f5cf28ff375deaf1e6a4b192700eebf2f
ms.sourcegitcommit: 90efec455336b4cecc06a8cbf0ce287740433523
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2020
ms.locfileid: "46898124"
---
# <a name="empower-remote-workers-with-microsoft-365"></a>使用 Microsoft 365 为远程工作者提供强大帮助

企业可能需要让员工能够从家中安全地访问组织的本地和基于云的信息、工具和资源。 对于许多组织而言，允许员工在离开办公室时工作非常重要，这有助于：

- 节省办公空间。
- 聘用并留住不愿意调动的员工。
- 减少员工通勤，让他们有更多的时间来提高工作效率并在工作之外进行减压活动。

Microsoft 365 提供了帮助员工远程工作的功能。

![使用 Microsoft 365 为远程员工提供强大帮助](../media/empower-people-to-work-remotely/2-m365-remoteworker-solution-businessoverview.png)

| 关键功能 | 描述 |
|:-------|:-----|
| 已连接 | 远程员工能够随时随地访问： <ul><li>Microsoft 365 订阅中基于云的服务和数据。 </li><li>组织资源，例如由本地应用程序数据中心提供的资源。</li></ul> |
| 安全 | 使用 Microsoft 365 和 Windows 10 的多重身份验证 (MFA) 和内置安全功能来保护登录，防止恶意软件、恶意攻击和数据丢失。 |
| 托管 | 可以使用安全设置、允许的应用以及需要与系统运行状况保持一致的方式，从云中管理远程员工的设备。 |
| 协作高效 | 远程员工可采用与本地相媲美的高协作方式实现高效工作，方式如下： <ul><li>通过 Teams 进行的联机会议和聊天会话。 </li><li>基于云的文件存储的共享工作区，可通过 SharePoint 和 OneDrive 实现全球可访问性和实时协作。 </li><li>用于划分工作并完成任务的共享任务和工作流。 </li></ul> |
|||

为获得无缝登录体验，应将本地 Active Directory 域服务 (AD DS) 用户帐户与 Azure Active Directory (Azure AD) 同步。 若要保护 Windows 10 设备，应在 Intune 中对其进行注册。 下面是基础结构的高级视图。

![面向使用 Microsoft 365 的远程工作者的基本基础结构](../media/empower-people-to-work-remotely/remote-workers-basic-infrastructure.png)

若要满足针对远程员工的条件，请使用以下 Microsoft 365 功能和特性。

| 功能或特性 | 说明 | 许可 |
|:-------|:-----|:-------|
| 通过安全性默认设置强制执行 MFA   | 通过请求第二种形式的登录身份验证，抵御遭到入侵的身份和设备的威胁。安全性默认设置要求对所有用户帐户进行 MFA。   | Microsoft 365 E3 或 E5 |
| 通过条件访问强制执行 MFA| 要求基于使用条件访问策略的登录的属性进行 MFA。    | Microsoft 365 E3 或 E5 | 
| 通过基于风险的条件访问强制执行 MFA   | 需要基于使用 Azure 高级威胁防护的用户登录的风险进行 MFA。 | Microsoft 365 E5 或 E3（含 Azure AD Premium P2 许可） | 
| 自助服务密码重置 (SSPR)    | 允许用户重置或解锁其密码或帐户。  | Microsoft 365 E3 或 E5 |
| Azure AD 应用程序代理    | 为 Intranet 服务器上托管的基于 Web 的应用程序提供安全的远程访问权限。   | 需要单独的付费 Azure 订阅 |
| 配置点到站点 VPN   | 通过 Azure 虚拟网络创建从远程工作者的设备到 intranet 的安全连接。   | 需要单独的付费 Azure 订阅 |
| Windows 虚拟桌面   | 支持只能将其个人和非托管设备与在 Azure 中运行的虚拟桌面配合使用的远程工作者。 | 需要单独的付费 Azure 订阅 |
| 远程桌面服务 (RDS) | 允许员工通过 Intranet 连接到基于 Windows 的计算机。 | Microsoft 365 E3 或 E5 | 
| 远程桌面服务网关   | 加密通信，防止 RDS 主机直接向 Internet 公开。 | 需要单独的 Windows Server 许可证 |
| Microsoft Intune | 管理设备和应用程序。   | Microsoft 365 E3 或 E5 | 
| 内容和功能， | 管理设备上的软件安装、更新和设置 | 需要单独的 Configuration Manager 许可证 |
| 桌面分析 | 确定你的 Windows 客户端的更新准备情况。   | 需要单独的 Configuration Manager 许可证 |
| Windows Autopilot | 设置和预配置新的 Windows 10 设备，以便高效使用。   | Microsoft 365 E3 或 E5 |
| Microsoft Teams、Exchange Online、SharePoint Online 和 OneDrive、Microsoft 365 应用版、Microsoft Power Platform、Yammer、Power Apps | 创建、沟通和协作。 | Microsoft 365 E3 或 E5 |
||||

有关安全和合规性条件，请参阅[针对远程工作者的部署安全性与合规性](empower-people-to-work-remotely-security-compliance.md)。

<a name="poster"></a>有关此解决方案的两页摘要，请参阅[“为远程工作者助力”文章](../downloads/empower-remote-workers.pdf)。

[![“为远程工作者提供强大功能”海报](../media/empower-people-to-work-remotely/empower-remote-workers-poster.png)](../downloads/empower-remote-workers.pdf)

你还可以下载 [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/empower-remote-workers.pdf) 或 [PowerPoint](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/empower-remote-workers.pptx) 格式的海报，并以信件、法律或小报 (11 x 17) 的纸型打印。

使用以下步骤来保护和优化对组织的服务器、数据和云服务的访问，并实现最大的工作效率。

1. [借助 MFA 提升登录安全性](empower-people-to-work-remotely-secure-sign-in.md)
2. [提供对本地应用和服务的远程访问权限](empower-people-to-work-remotely-remote-access.md)
3. [部署安全与合规服务](empower-people-to-work-remotely-security-compliance.md)
4. [部署设备、电脑和其他终结点的终结点管理](empower-people-to-work-remotely-manage-endpoints.md)
5. [部署远程工作者生产力应用和服务](empower-people-to-work-remotely-teams-productivity-apps.md)
6. [培训远程工作者和处理使用情况反馈](empower-people-to-work-remotely-train-monitor-usage.md)

![使用 Microsoft 365 为远程工作者提供帮助的步骤](../media/empower-people-to-work-remotely/remote-workers-step-grid.png)

有关 Microsoft 提供的关于支持远程工作者的最新信息，请参阅[启用远程工作技术社区网站](https://resources.techcommunity.microsoft.com/enabling-remote-work/)。
