---
title: 为远程工作者提供强大功能
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 10/24/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: 配置基础结构和安全性，使你的员工能够随时随地进行远程工作。
ms.openlocfilehash: cfbabfbe0c239ca837356b585171778d40daaa93
ms.sourcegitcommit: 6adfcf042e64b21f09f2b8e072e8eba6d3479e31
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/25/2020
ms.locfileid: "42952050"
---
# <a name="empower-remote-workers"></a>为远程工作者提供强大功能

*此方案适用于 Microsoft 365 企业版的 E3 和 E5 版本*

对于许多组织而言，让员工在远离办公室的地方无缝且安全地工作非常重要，这样做可以节省员工办公空间、雇用和留住不愿搬迁的员工、减少员工上下班的时间，从而让他们有更多时间来提高在外办公的工作效率并减轻压力。

远程工作（也称为远程办公）可以涵盖以下对象：

- 偶尔离开办公室参加会议或客户会议的员工。
- 一些远程工作的全职员工。
- 没有办公室且所有员工均为远程员工的完全远程运作的组织。

为了支持远程工作者，Microsoft 365 企业版中的功能组合可使远程工作者采用高度协作的方式开展工作，例如：

- 在线会议和聊天会话。
- 基于云的文件存储的共享工作区，可实现全球可访问性和实时协作。
- 用于划分工作并完成任务的共享任务和工作流。

为实现强大的安全性，Microsoft 365 企业版包括：

- 强制实施的身份验证要求，用于检测和响应高风险的登录，以及阻止所选应用和不合规的设备。
- 在云中加密的连接和数字资产。
- 用于定义谁可以对文件执行哪些操作的权限。
- 数据丢失防护 (DLP)，用于防止高度管控数据泄露。

若要满足针对远程工作者的这些条件，请使用以下 Microsoft 365 企业版功能：

- 用户标识和登录安全性
  - 使用多重身份验证 (MFA) 的 Azure Active Directory (Azure AD) 用户帐户
  - 要求对有风险的登录进行 MFA 的条件访问策略
- 协作平台
  - Microsoft Teams、SharePoint 和 OneDrive，远程工作者可以使用它们来安排和参加基于视频的在线会议，同时处理相同的文档
- 对资源的安全访问
  - Teams、SharePoint 网站和 OneDrive 的组和权限，只有经过身份验证和允许的用户才能访问
- 保护泄露的文件
  - Office 365 DLP 策略
  - 随文件传输的加密和权限的敏感度标签
- 使用 Microsoft Intune 的设备管理和安全性
  - 托管设备的注册
  - 个人设备的应用设置
  - 设备和应用策略
- 设备的高效应用
  - Office 365 专业增强版应用，可通过 Teams、SharePoint 和 OneDrive 带来协作体验 
- Windows 10 企业版
  - 全面的安全功能，可抵御网络攻击并防止数据泄露
- 对本地应用的访问权限
  - 具有混合标识的组织可使用 Azure AD 应用程序代理，而不是虚拟专用网络 (VPN) 连接

以下阶段将指导你部署 Microsoft 365 企业版功能以实现远程访问并推动远程工作者的采用。 如果你已部署这些阶段的元素，请确保在移到下一个元素之前满足规定的要求。

<a name="poster"></a>有关此方案的 1 页摘要，请参阅[“为远程工作者提供强大功能”海报](../media/empower-people-to-work-remotely/empower-remote-workers-scenario.pdf)。

[![“为远程工作者提供强大功能”海报](../media/empower-people-to-work-remotely/empower-remote-workers-poster.png)](../media/empower-people-to-work-remotely/empower-remote-workers-scenario.pdf)

还可以下载 [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/empower-people-to-work-remotely/empower-remote-workers-scenario.pdf) 或 [PowerPoint](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/empower-people-to-work-remotely/Empower-Remote-Workers-Poster.pptx) 格式的海报，并按 letter、legal 或 tabloid (11 x 17) 大小的纸张打印。


## <a name="phase-1-deploy-microsoft-365-features-and-capabilities-for-remote-workers"></a>阶段 1：为远程工作者部署 Microsoft 365 特性和功能

鉴于此方案所需的特性和功能的广度和数量，我们将逐步指导你完成 [Microsoft 365 企业版部署指南](deploy-microsoft-365-enterprise.md)的底层基础结构和工作负载部分中的所需元素。

### <a name="step-1-foundation-infrastructure-requirements-for-remote-workers"></a>步骤 1：针对远程工作者的底层基础结构要求

在此步骤中，我们将访问[底层基础结构](deploy-foundation-infrastructure.md)的各个阶段，并列出远程工作者所需的元素。

对于[阶段 2：标识](identity-infrastructure.md)，请为用户标识和登录安全性部署以下对象：

- 用于混合标识的从本地 Active Directory 域服务 (AD DS) 同步的用户帐户和组。
- 用于分配权限的已同步组或包含相应成员的 Azure AD 组。
- 身份验证设置，例如要求 MFA。
- 条件访问策略，要求对高风险登录进行 MFA 并阻止不支持新式身份验证的客户端。

下面是最终配置，其中突出显示了标识元素。

![远程工作者的标识元素](../media/empower-people-to-work-remotely/remote-workers-id-phase.png)
 
对于[阶段 3：Windows 10 企业版](windows10-infrastructure.md)，请部署：

- 用于使用 Windows 10 企业版部署新设备以及将 Windows 7 或 Windows 8.1 设备升级到 Windows 10 企业版的基础结构
- 用于实现标识、威胁和信息保护的全面安全功能

下面是 Windows 10 企业版设备的最终配置。

![远程工作者的 Windows 10 企业版元素](../media/empower-people-to-work-remotely/remote-workers-win10-phase.png)
 
对于[阶段 4：Office 365 专业增强版](office365proplus-infrastructure.md)，请部署基础结构以安装 Office 365 专业增强版，或者在组织设备上将当前安装的 Office 套件（如 Office 2010 或 Office 2013）升级到 Office 365 专业增强版。 这将为用户提供最佳的安全性和协作体验。

下面是设备上安装的 Office 365 专业增强版的最终配置。

![远程工作者的 Office 365 专业增强版元素](../media/empower-people-to-work-remotely/remote-workers-proplus-phase.png)
 
对于[阶段 5：移动设备管理](mobility-infrastructure.md)，请部署 Intune 设备和应用管理以：

- 注册 Windows 10 企业版、iOS、macOS、Android 和 Android 企业版设备，以便它们接收组织定义的功能和安全设置。
- 提供应用设置，即使在员工拥有的个人设备上也能提供额外的安全性并允许或阻止相关应用。
- 创建带条件访问的合规性策略，防止连接不合规的设备。

下面是已注册 Intune 的设备的最终配置，其中突出显示了策略。

![远程工作者的移动设备管理元素](../media/empower-people-to-work-remotely/remote-workers-mdm-phase.png)
 
对于[阶段 6：信息保护](infoprotect-infrastructure.md)，通过以下方法为你的数字资产设计和配置保护：

- Office 365 DLP 策略。
- 随文件传输的加密和权限的 Office 365 敏感度标签。

以下是包含 DLP 策略并突出显示了敏感度标签的最终配置。

![远程工作者的信息保护元素](../media/empower-people-to-work-remotely/remote-workers-ip-phase.png)
 
若要访问本地应用，可以使用需要混合标识环境的 [Azure AD 应用程序代理](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy)。

下面是最终配置，其中突出显示了应用程序代理组件。

![远程工作者的应用程序代理元素](../media/empower-people-to-work-remotely/remote-workers-app-proxy.png)
 
### <a name="step-2-workloads-for-remote-workers"></a>步骤 2：远程工作者的工作负载

对于 [Exchange Online](exchangeonline-workload.md)，请为每个用户部署 Exchange Online 邮箱。

对于 [Teams](teams-workload.md)，请为用户和组部署 Teams。

对于 [SharePoint 和 OneDrive](sharepoint-online-onedrive-workload.md)，请部署 SharePoint 团队或通信网站和 OneDrive 文件夹。

下面是最终配置，其中突出显示了工作负载。

![远程工作者的 Microsoft 365 工作负载](../media/empower-people-to-work-remotely/remote-workers-workloads.png)
 
### <a name="deployment-results"></a>部署结果

部署底层基础结构和工作负载并推广 Windows 10 企业版和 Office 365 专业增强版后，远程工作者将：

- 受强身份验证和身份保护的约束。
- 在其 Windows 设备上拥有最新、最安全的 Windows 版本。
- 在其设备上拥有最新、最高效的 Office 套件版本。
- 受应用管理和设备合规性策略的约束。
- 受 DLP 策略和限制条件的约束。
- 可以分配随文件和电子邮件传输的加密和权限的敏感度标签。
- 无需 VPN 连接即可访问本地应用。
- 可通过 Teams 中的聊天、会议和文件以及 SharePoint 和 OneDrive 中的文件，执行其自己的工作并与同事进行实时协作。

脱机（未连接到 Internet）时，远程工作者可以更改文件的本地副本。 当重新连接到 Internet 时，OneDrive 会将本地副本与 Microsoft 365 订阅中存储的文件进行同步。 

下面是使用混合标识时为组织的远程工作者生成的配置。

![具有混合标识的组织的最终配置](../media/empower-people-to-work-remotely/remote-workers-hybrid.png) 
 
下面是使用仅限云标识时为组织的远程工作者生成的配置。

![具有仅限云标识的组织的最终配置](../media/empower-people-to-work-remotely/remote-workers-cloud-only.png)

## <a name="phase-2-drive-user-adoption-for-remote-workers"></a>阶段 2：推动远程工作者的用户采用

现在，底层基础结构和工作负载已部署到位，是时候推动远程工作者采用这些功能了，以便他们能够随时随地保持高效。

### <a name="step-1-train-your-users"></a>步骤 1：培训用户

为远程工作者提供以下方面的培训：

- 正确的登录过程（包括 MFA 注册）以及检测到风险时登录可能面临的挑战。
- 使用设备以及如何使用策略阻止不合规设备的访问。
- 使用允许的应用以及如何使用 Intune 应用策略阻止相关应用。
- Windows 10 企业版安全功能。
- 如何将 Outlook 用于电子邮件和日历。
- 如何使用 [Teams](https://docs.microsoft.com/microsoftteams/training-microsoft-teams-landing-page) 进行聊天、基于视频的会议、文档共享和线程对话。
- 如何使用 SharePoint 团队或通信网站和 OneDrive 文件夹浏览用户库中的文件以及组中包含的文件。
- 对于文件的本地和联机版本，如何为包含敏感或高度管控数据的文件使用和应用敏感度标签。

此培训应包括实践练习，让学员户可以体验这些功能及其结果。

### <a name="step-2-conduct-periodic-reviews-of-usage-and-address-worker-feedback"></a>步骤 2：定期审查使用情况并处理工作者的反馈意见

在培训后的几周内：

- 快速处理远程工作者的反馈意见并微调相关策略和配置。
- 分析 Teams、SharePoint 网站和 OneDrive 文件夹的使用情况，并将其与使用预期进行比较。
- 验证是否已使用适当的敏感度标签正确标记了敏感或高度管控文件。

根据需要重新培训用户。

### <a name="user-adoption-results"></a>用户采用结果

远程工作者可以使用 Windows 10 企业版或其他设备以及 Office 365 专业增强版在安全环境中访问和使用共享的 Microsoft 365 企业版云服务及资源，并且可以实时举行会议、创建和协作。

## <a name="see-also"></a>另请参阅

[工作负载和应用场景](deploy-workloads.md)

[Microsoft 365 工作效率库](https://aka.ms/productivitylibrary) https://aka.ms/productivitylibrary)

[部署指南](deploy-microsoft-365-enterprise.md)
