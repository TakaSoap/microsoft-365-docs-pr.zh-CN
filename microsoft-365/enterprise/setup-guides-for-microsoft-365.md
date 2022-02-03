---
title: Microsoft 365 和 Office 365 服务的设置指南
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- Ent_O365
- M365-subscription-management
- SPO_Content
- m365initiative-coredeploy
f1.keywords:
- CSH
ms.custom: Adm_O365_Setup
search.appverid:
- MET150
- MET150
- BCS160
ms.assetid: 165f46e8-3533-4d76-be57-97f81ebd40f2
description: 获取分步工具，以规划、迁移和实现租户许可证中的功能。 查找设置需要运行的服务或应用的指南。
ms.openlocfilehash: 91b89eeaec3a9d0db5f191cbd10c797a633c633b
ms.sourcegitcommit: e3bff611439354e6339bb666a88682078f32ec13
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/03/2022
ms.locfileid: "62354596"
---
# <a name="setup-guides-for-microsoft-365-and-office-365-services"></a>Microsoft 365 和 Office 365 服务的设置指南

Microsoft 365和Office 365设置指南会提供针对规划和部署租户、应用和服务而定制的指南和资源。 这些指南的创建方式与载入专家Microsoft 365 FastTrack在个人[](https://www.microsoft.com/fasttrack/microsoft-365)交互中共享的最佳方案相同，并且可供 Microsoft 365 管理中心 内的所有管理员使用。 它们提供有关产品设置、启用安全功能、部署协作工具以及提供脚本以加快高级部署的信息。

> [!NOTE]
> 必须分配有全局读取者等管理员角色才能访问Microsoft 365指南。 只有具有全局管理员角色的管理员可以使用指南更改租户中的设置。

## <a name="how-to-access-setup-guides-in-the-microsoft-365-admin-center"></a>如何访问安装程序指南Microsoft 365 管理中心

安装程序指南可从安装程序指南[页中访问](https://aka.ms/setupguidance)Microsoft 365 管理中心。 你可以跟踪进度状态，并随时返回以完成指南。 若要访问" **设置指南"页** ：

1. 在 [Microsoft 365 管理中心](https://admin.microsoft.com/)中，转到 **主页**。

2. 查找 **培训&指南** 卡。

   ![&中的培训指南Microsoft 365 管理中心](../media/setup-guides-for-microsoft-365/adminportal-trainingandguides.png)

3. 选择 **"高级部署指南"** ，然后选择" **所有指南"**。

   !["安装指南"页的屏幕截图Microsoft 365 管理中心](../media/setup-guides-for-microsoft-365/adminportal-setupguidance.png)

## <a name="guides-for-initial-setup"></a>初始设置指南

### <a name="prepare-your-environment"></a>准备环境

准备[环境](https://aka.ms/prepareyourenvironment)指南可帮助你为组织的环境准备Microsoft 365 Office 365服务。 无论你的目标是什么，都需要完成一些任务以确保成功部署。 为了避免在准备环境时出现任何错误，我们会提供连接域、添加用户、分配许可证、使用 Exchange Online 设置电子邮件以及安装或部署 Office 应用的分步说明。

### <a name="email-setup-guide"></a>电子邮件设置指南

电子邮件[设置指南](https://aka.ms/office365setup)提供了为组织配置电子邮件Exchange Online分步指南。 本指南包括设置新的电子邮件帐户、迁移电子邮件和配置电子邮件保护。 若要成功设置电子邮件，请使用此顾问，你将收到基于您组织的当前邮件系统、要迁移的邮箱数以及您希望如何管理用户及其访问权限的建议迁移方法。

### <a name="migrate-gmail-contacts-and-calendar-items"></a>迁移 Gmail 联系人和日历项目

将 Gmail 用户的邮箱迁移到 Microsoft 365时，将迁移电子邮件，但不迁移联系人和日历项目。 Gmail 联系人和日历[顾问](https://aka.ms/gmailcontactscalendar)提供了使用 Outlook.com、Outlook 客户端或 PowerShell 的导入和导出方法将 Google 联系人和 Google 日历项目导入 Microsoft 365 的步骤。

### <a name="microsoft-365-setup-guide"></a>Microsoft 365设置指南

本[Microsoft 365设置](https://aka.ms/microsoft365setupguide)指南提供了有关设置生产力工具、安全策略和设备管理功能的指南。 通过Microsoft 365 商业高级版或Microsoft 365订阅，你可以使用此顾问来设置和配置组织的设备。

你将收到用于启用云服务、将设备更新到受支持的最新 Windows 10 版本以及将设备加入 Azure Active Directory (Azure AD) 的资源指南和访问权限，所有这些操作都位于一个中心位置。

### <a name="remote-work-setup-guide"></a>远程工作设置指南

远程 [工作设置指南](https://aka.ms/remoteworksetup) 为组织提供了所需的提示和资源，以确保用户能够成功远程工作、数据安全并保护用户的凭据。

你将收到有关优化远程工作者对云中 Microsoft 365 资源和组织网络的设备流量的指导，这将减轻远程访问 VPN 基础结构的压力。

### <a name="microsoft-edge-setup-guide"></a>Microsoft Edge设置指南

Microsoft Edge已经过全新构建，可让你获得世界一流的兼容性和性能、值得你享有的安全和隐私以及旨在发挥 Web 最佳效果的新功能。

[Microsoft Edge](https://aka.ms/edgeadvisoradmin) 设置指南将帮助您配置 Enterprise 站点发现，以查看在组织内访问哪些网站可能需要使用 IE 模式、查看和配置重要的安全功能、配置隐私策略和合规性策略以满足组织的要求，以及管理您设备的 Web 访问。 你可以将Microsoft Edge下载到单个设备，或者我们将展示如何使用组策略、Configuration Manager 或 Microsoft Intune 部署到组织中的多个用户。

### <a name="configure-ie-mode-for-microsoft-edge"></a>为用户配置 IE Microsoft Edge

如果你已经部署了 Microsoft Edge并且只想配置 IE 模式，Microsoft Edge 配置 [IE](https://aka.ms/configureiemodeadmin) 模式指南将指导你自动配置 Enterprise 站点发现。 你还将从基于云的工具获取 IE 模式建议，这可帮助你创建Enterprise部署给用户的 IE 模式站点列表。

### <a name="microsoft-search-setup-guide"></a>Microsoft 搜索设置指南

Microsoft 搜索帮助组织找到完成所处理操作所需的功能。 无论组织是搜索人员、文件、组织结构图、网站或常见问题解答，组织都可以Microsoft 搜索工作之一获取答案。

该[Microsoft 搜索设置](https://aka.ms/MicrosoftSearchSetup)指南可帮助你配置Microsoft 搜索是向一组用户试用还是将其推出给组织中的每个人。你将分配搜索管理员和搜索编辑器，然后使用答案和更多选项为用户自定义搜索体验，例如将 必应 扩展添加到 Chrome 或将 必应 设置为默认搜索引擎。

## <a name="guides-for-authentication-and-access"></a>身份验证和访问指南

### <a name="configure-multi-factor-authentication-mfa"></a>配置多重身份验证 (MFA)

Configure [multi-factor authentication (MFA) guide](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/featureexplorer/security/ConditionalAccess) provides information to secure your organization against breaches due to lost or stolen credentials. MFA 通过提示多种形式的验证来在用户登录应用或其他公司资源时证明用户的身份，从而立即提高帐户安全性。 此提示可能是在用户的移动设备上输入代码或提供指纹扫描。 通过条件访问、安全默认值或每用户 MFA 启用 MFA。 本指南将基于你的许可证和现有配置，为组织提供建议的 MFA 选项。

### <a name="identity-security-for-teams"></a>用户的身份Teams

团队 [标识安全](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/teamsidentity)指南可帮助你执行一些基本安全步骤，以确保你的用户是安全的，并且使用 **Teams。**

### <a name="add-or-sync-users-to-microsoft-365"></a>将用户添加或同步到Microsoft 365

[本指南](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/modernonboarding/identitywizard)有助于简化在 Microsoft 365 中设置 **用户帐户的过程**。 根据您的环境和需求，可以选择单独添加用户、使用 Azure AD 云同步或 Azure AD 连接 迁移本地目录，或在必要时解决现有同步问题。

### <a name="azure-ad-setup-guide"></a>Azure AD设置指南

本[Azure AD设置](https://aka.ms/aadpguidance)指南提供了一些信息，以确保您的组织具有强大的安全基础。 在本指南中，你将设置初始功能，如基于 Azure 角色的访问控制 (Azure RBAC) （针对管理员）、Azure AD 连接（针对本地目录）和 Azure AD 连接 运行状况，以便你可以监视自动同步期间混合标识的运行状况。

它还包括有关启用自助服务密码重置、条件访问和集成第三方登录的必需信息，包括可选高级标识保护和用户设置自动化。

### <a name="sync-users-from-your-windows-server-active-directory"></a>同步用户Windows Server Active Directory

Sync [users from your Windows Server Active Directory](https://aka.ms/directorysyncsetup) guide walks you through on directory synchronization. 目录同步将本地和云标识汇集在一起，以便更轻松地访问和简化管理。 解锁新功能，如单一登录、自助服务选项、自动帐户设置、条件访问控制和合规性策略。 这些功能可确保用户能够随时随地访问所需的资源。

### <a name="plan-your-passwordless-deployment"></a>规划无密码部署

升级到允许用户通过以下无密码身份验证方法之一安全地访问其设备的备用登录方法：

- Windows Hello 企业版
- Microsoft Authenticator 应用
- 安全密钥

使用 [规划无密码部署](https://aka.ms/passwordlesssetup) 指南来发现使用的最佳无密码身份验证方法，并接收有关如何部署这些方法的指导。

### <a name="integrate-a-third-party-cloud-app-with-azure-ad"></a>将第三方云应用与 Azure AD

[本指南](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/azureadappintegration) 可帮助 IT 管理员选择和配置应用。

### <a name="plan-your-self-service-password-reset-sspr-deployment"></a>在 SSPR 部署中规划 (密码) 重置

如果用户的帐户被锁定，或者他们忘记密码，而无需联系支持工程师，则允许用户单独更改或重置其密码。

使用 [规划自助服务密码重置部署](https://aka.ms/SSPRSetupGuide) 指南可接收相关文章和说明，以配置适当的 Azure 门户选项，以帮助你在你的环境中部署 SSPR。

### <a name="active-directory-federation-services-ad-fs-deployment-advisor"></a>Active Directory 联合身份验证服务 (AD FS) 顾问

[AD FS](https://aka.ms/adfsguidance) 部署顾问提供有关部署内部部署 AD FS 基础结构的分步指南，该基础结构对用户进行身份验证以使用 Microsoft 365 和 Office 365 服务。 借助本指南，贵组织可以检查 AD FS 组件和要求、获取和安装部署所需的 SSL 证书，以及安装所需的 Web 应用程序代理服务器。

## <a name="guides-for-security-and-compliance"></a>安全性和合规性指南

### <a name="security-analyzer"></a>安全分析器

安全 [分析](https://aka.ms/securityanalyzer) 器将分析你的安全方法，并介绍可改善你安全状况的 Microsoft 集成安全性和合规性解决方案。 你将了解高级功能，例如管理标识和帮助抵御新式攻击。 然后，你可以注册试用版订阅，并指向每个解决方案的相应设置指南。

### <a name="microsoft-intune-setup-guide"></a>Microsoft Intune设置指南

设置Microsoft Intune管理组织中设备的设备。 为了完全控制公司设备，你将使用 Intune 的移动设备管理 (MDM) 功能。 若要在共享和个人设备上管理组织的数据，可以使用 Intune 的移动应用程序管理功能 (MAM) 功能。

借助[Microsoft Intune](https://aka.ms/intunesetupguide)设置指南，你可以设置设备和应用合规性策略、分配应用保护策略，并监视设备和应用保护状态。

### <a name="microsoft-defender-for-endpoint-setup-guide"></a>Microsoft Defender for Endpoint 设置指南

[Microsoft Defender for Endpoint 设置指南](https://aka.ms/mdatpsetup)提供了可帮助企业网络预防、检测、调查和响应高级威胁的说明。 对组织漏洞进行明智评估，并决定最适合的部署包和配置方法。

> [!NOTE]
> Microsoft Defender 终结点需要 Microsoft 批量许可证。

### <a name="exchange-online-protection-setup-guide"></a>Exchange Online Protection设置指南

Microsoft Exchange Online EOP (EOP) 是一种基于云的电子邮件筛选服务，用于防范垃圾邮件和恶意软件，具有保护您的组织免受邮件策略违反攻击的功能。

使用 [Exchange Online Protection](https://aka.ms/EOPguidance) 设置指南通过选择本地邮箱、本地和云) 邮箱混合的混合 (&mdash; 或所有云邮箱中的哪一种部署方案来设置 EOP&mdash;。 本指南提供了用于设置和查看用户许可、在 Microsoft 365 管理中心 中分配权限，以及配置安全与合规中心中的组织的反恶意软件和垃圾邮件策略 &的信息和资源。

### <a name="microsoft-defender-for-office-365-setup-guide"></a>Microsoft Defender for Office 365 设置指南

[Microsoft Defender for Office 365](https://aka.ms/oatpsetup) 设置指南可保护你的组织免受你的环境可能通过电子邮件、链接和第三方协作工具受到的恶意威胁。 本指南提供了资源和信息，可帮助你准备和确定 defender Office 365计划以满足组织的需求。

### <a name="microsoft-defender-for-identity-setup-guide"></a>Microsoft Defender for Identity 设置指南

[Microsoft Defender for Identity 设置指南](https://aka.ms/DefenderforIdentitysetup)提供了安全解决方案设置指南，用于标识、检测和调查可能损害用户标识的高级威胁。 其中包括检测可疑的用户活动和针对你的组织的恶意内部人员操作。 你将创建 Defender for Identity 实例，连接到组织的 Active Directory，然后设置传感器、警报、通知并配置你的唯一门户首选项。

### <a name="insider-risk-solutions-setup-guide"></a>内部风险解决方案设置指南

[预览体验成员风险解决方案](https://aka.ms/Insiderrisksetup)设置指南可帮助你保护组织免受内部风险，这些风险难以识别且难以缓解。 内部风险出现在多个领域，并可能导致组织出现严重问题，包括知识产权丢失和工作场所骚扰等。

本指南中的解决方案将帮助你了解用户活动、操作以及使用本机信号的通信以及来自整个组织的扩充：

* 借助通信合规性解决方案，你可以识别并处理工作场所暴力、内部交易、骚扰、行为准则和违反法规等项目的通信风险。
* 内部风险管理解决方案可帮助你识别、调查和处理知识产权盗窃、敏感数据泄露、安全违规、数据泄漏和保密行为的风险。

### <a name="microsoft-information-protection-setup-guide"></a>Microsoft 信息保护设置指南

大致了解可应用于信息保护策略的功能，以便确信敏感信息受到保护。 使用四个阶段的生命周期方法来发现、分类、保护和监视敏感信息。 [Microsoft 信息保护设置指南](https://aka.ms/mipsetupguide)提供了有关完成每个阶段的指导。

### <a name="microsoft-information-governance-setup-guide"></a>Microsoft 信息治理设置指南

[Microsoft 信息治理设置](https://aka.ms/migsetupguide)指南提供了设置和管理组织的管理策略时需要的信息，以确保根据你设置的特定生命周期指南对数据进行分类和管理。 通过本指南，你将了解如何创建、自动应用或发布应用于组织的可重用内容和合规性记录的标签、标签策略和保留策略。 你还将获取有关使用批量方案的文件计划导入 CSV 文件或手动将其应用到单个文档的信息。

### <a name="microsoft-defender-for-cloud-apps-setup-guide"></a>Microsoft Defender for Cloud Apps 设置指南

[Microsoft Defender for Cloud Apps 设置](https://aka.ms/cloudappsecuritysetup)指南提供了设置云发现解决方案的易于遵循的部署和管理指南。 借助云发现，你可以集成受支持的安全应用，然后使用流量日志动态发现和分析组织使用的云应用。 你还将设置通过 Defender for Cloud Apps 解决方案提供的功能，包括用于标识高风险使用的威胁检测策略、用于定义访问的信息保护策略，以及用于监视活动实时会话控制。 借助这些功能，你的环境可以增强可见性、控制数据移动和分析，以识别和防御所有 Microsoft 和第三方云服务中的网络威胁。

## <a name="guides-for-collaboration"></a>协作指南

### <a name="build-your-employee-experience"></a>构建员工体验

使用员工体验仪表板改变 [员工协同工作方式](https://aka.ms/EmployeeExperienceDashboard)。 为了进行无缝团队合作，Microsoft 365团队，以创建高效、一致的团队，并保持员工与领导层和组织其余人员之间的参与。 帮助你的员工有效参与所有工作活动。 这些指南将提供有关如何使用 SharePoint、Teams 和 Yammer 在组织内部构建协作以帮助提高工作效率的说明。

### <a name="microsoft-365-apps-setup-guide"></a>Microsoft 365 应用版设置指南

Microsoft 365 应用版[设置](https://aka.ms/OPPquickstartguide)指南可帮助你使用户的设备运行最新版本的 Office 产品，如 Word、Excel、PowerPoint 和 OneNote。 你将获取有关各种部署方法的指导，这些方法包括使用管理工具的企业部署轻松自安装选项。 这些说明将帮助您评估环境、确定特定部署要求，以及实施必要的支持工具以确保成功安装。

### <a name="mobile-apps-setup-guide"></a>移动应用设置指南

移动应用[设置指南](https://aka.ms/officeappguidance)提供了在移动设备、iOS 和 Android Office下载和Windows应用的说明。 本指南提供了在手机和平板电脑设备上下载和安装 Microsoft 365 Office 365 应用的分步信息。

### <a name="microsoft-teams-setup-guide"></a>Microsoft Teams设置指南

本[Microsoft Teams设置](https://aka.ms/teamsguidance)指南为贵组织提供了设置团队工作区的指导，这些工作区通过消息传递、通话和音频或视频会议来承载实时对话，用于团队和私人通信。 使用本指南中的工具配置来宾访问、设置哪些人可以创建团队以及从 .csv 文件添加团队成员，所有这些操作都无需打开 PowerShell 会话。 您还可以获得最佳做法，以确定组织的网络要求并确保成功部署Teams部署。

### <a name="sharepoint-setup-guide"></a>SharePoint设置指南

[SharePoint设置](https://aka.ms/spoguidance)指南可帮助你设置 SharePoint 文档存储和内容管理、创建网站、配置外部共享、迁移数据和配置高级设置，以及推动组织内部的用户参与和通信。 您将按照配置内容共享权限策略的步骤操作，选择迁移同步工具，并为您的 SharePoint 环境启用安全设置。

### <a name="onedrive-setup-guide"></a>OneDrive设置指南

使用[OneDrive设置](https://aka.ms/ODfBquickstartguide)指南开始OneDrive文件存储、共享、协作和同步功能。 OneDrive提供了一个中心位置，用户可在这里同步其 Microsoft 365 应用版 文件、配置外部共享、迁移用户数据以及配置高级安全和设备访问设置。 可以使用 OneDrive 订阅或独立 OneDrive 部署 OneDrive 指南。

### <a name="yammer-deployment-advisor"></a>Yammer顾问

连接组织与员工联系Yammer。 部署[Yammer顾问](https://aka.ms/yammerdeploymentguide)通过添加Yammer、定义管理员和合并网络来准备Yammer网络。 你可获取有关部署Yammer，然后自定义外观、配置安全性和合规性以及优化设置的指导。

## <a name="advanced-guides"></a>高级指南

### <a name="in-place-upgrade-with-configuration-manager"></a>使用 Configuration Manager 进行就地升级

在将 Windows 7 [和](https://aka.ms/win10upgradedemo) Windows 8.1 设备升级到最新版本的 Windows 10 时，请使用配置管理器的就地升级指南。 您将使用提供的脚本检查先决条件并自动配置就地升级。

### <a name="deploy-office-to-your-users"></a>将Office部署到用户

从Office部署应用，能够使用 Office 部署工具自定义安装。 ["Office用户](https://aka.ms/proplusodt)部署策略"指南可帮助你使用高级设置Office自定义配置，或者可以使用预先构建的建议配置。 无论你的用户是进行自安装，还是单独还是批量向用户进行部署，此高级指南都为您提供了分步说明，以便为用户提供专为您的组织定制的 Office 安装。

### <a name="deploy-office-to-remote-users"></a>将Office部署到远程用户

现在，远程工作已是标准，用户需要在未连接到内部网络或使用其自己的设备时接收组织的 Office 设置。

使用["Office远程](https://aka.ms/officeremoteinstall)用户"指南创建自定义的 Office 安装，然后向用户发送生成的 PowerShell 脚本，该脚本将Office配置进行无缝安装。

### <a name="deploy-and-update-microsoft-365-apps-with-configuration-manager"></a>使用 Configuration Manager Microsoft 365 应用版和更新策略

对于使用 Configuration Manager 的组织，可以使用使用 [Configuration Manager](https://aka.ms/oppinstall) 顾问部署和更新 Microsoft 365 应用版 来生成一个脚本，该脚本将使用 FastTrack 工程师建议的最佳方案自动配置 Microsoft 365 应用版 部署。 使用本指南构建部署组、自定义 Office 应用和功能、配置动态或精简安装，然后运行脚本以创建面向部署所需的应用程序、自动部署规则和设备集合。

### <a name="intune-configuration-manager-co-management-setup-guide"></a>Intune Configuration Manager 共同管理设置指南

使用 [Intune Configuration Manager](https://aka.ms/comanagementsetup) 共同管理设置指南设置现有 Configuration Manager 客户端设备和组织希望与 Microsoft Intune 和 Configuration Manager 共同管理的基于 Internet 的新设备。 通过共同管理，Windows 10设备，并将新功能添加到组织设备，同时获得这两种解决方案的好处。
