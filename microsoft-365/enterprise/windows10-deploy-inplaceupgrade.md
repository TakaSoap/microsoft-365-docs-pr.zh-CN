---
title: 为就地升级的现有设备部署 Windows 10 Enterprise
description: 提供有关配置和部署 Windows 10 Enterprise 映像使用 System Center Configuration Manager 作为就地升级指南。
keywords: Microsoft 365 Microsoft 365 企业版，Microsoft 365 文档，Windows 10 Enterprise 部署中，在就地升级，Configuration Manager System Center Configuration Manager
author: greg-lindsay
localization_priority: Normal
audience: microsoft-business
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.date: 08/30/2018
ms.author: greglin
ms.openlocfilehash: 3df76c0de7b5a8b12c063113c79f9efa4e33b4c1
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/16/2019
ms.locfileid: "26865921"
---
# <a name="step-2-deploy-windows-10-enterprise-for-existing-devices-as-an-in-place-upgrade"></a>步骤 2： 为就地升级的现有设备部署 Windows 10 Enterprise

*本文适用于 Microsoft 365 企业版 E3 和 E5 版本*

![](./media/deploy-foundation-infrastructure/win10enterprise_icon-small.png)

升级 Windows 10 中当前运行 Windows 7 或 Windows 8.1 的 Pc 的最简单路径是通过就地升级。您可以使用 System Center Configuration Manager （配置管理器） 任务序列完全自动完成的过程。 

如果您具有现有的计算机运行 Windows 7 或 Windows 8.1，我们建议此路径，如果您的组织部署 Windows 10。这将利用 Windows 安装程序 (Setup.exe) 执行就地升级，从而自动保存所有数据、 设置、 应用程序，以及从现有的操作系统版本的驱动程序。这需要最少的 IT 工作，因为没有不需要任何复杂部署基础结构。

按照以下步骤来配置和部署 Configuration Manager 用作就地升级 Windows 10 Enterprise 映像。

## <a name="part-1-verify-readiness-to-upgrade-windows"></a>第 1 部分： 准备升级 Windows 验证

首先，使用的 Windows 分析的升级准备功能提供强大的见解和建议有关计算机、 应用程序，以及贵公司，在无驱动程序额外的成本和无需其他基础结构要求。此新服务将指导您完成使用基于 Microsoft 建议做法的工作流的升级和功能更新项目。最新的库存数据允许您平衡成本和您升级的项目中的风险。

请参阅[管理 Windows 升级的升级准备使用](https://docs.microsoft.com/windows/deployment/upgrade/manage-windows-upgrades-with-upgrade-readiness)，以了解详细信息、 入门、 使用和解决升级准备。

接下来，按照指南以使用 System Center Configuration Manager （当前分支） 升级到 Windows 10 的 Windows 7 或更高版本操作系统。与任何高风险的部署，建议在备份之前的用户数据。OneDrive 云存储已准备好用于授权 Microsoft 365 用户，并可用于安全地存储其文件。有关详细信息，请参阅[OneDrive 快速入门指南](https://aka.ms/ODfBquickstartguide)。若要访问此页，必须以租户管理员或 Office 365 或 Microsoft 365 租户中的全局管理员身份登录。

配置管理器版本和支持的相应 Windows 10 客户端版本的列表，请参阅[支持的 Windows 10 的 System Center Configuration Manager](https://aka.ms/supportforwin10sccm)。

**若要验证升级 Windows 的就绪性**

启动 Windows 10 部署之前查看以下要求：

- **符合条件的 Windows 版本升级**-您设备上必须运行 Windows 7 或 Windows 8.1 的版本升级到 Windows 10 Enterprise 符合条件。有关受支持的版本的列表，请参阅[Windows 10 升级路径](https://aka.ms/win10upgradepaths)。 
- **受支持设备**-与 Windows 8.1 兼容的大多数计算机将与 Windows 10 兼容。您可能需要安装 Windows 10 中正确函数设备更新的驱动程序。有关详细信息，请参阅[Windows 10 规范](https://aka.ms/windows10specifications)。
- **部署准备**-请确保您具有以下开始配置部署之前：
    - 必须在单独的驱动器上，已装入 iso 位于 Windows 10 安装介质的安装介质。从[MSDN 订户下载](https://aka.ms/msdn-subscriber-downloads)或[批量许可服务中心](https://aka.ms/mvlsc)，您可以获取 ISO。
    - 备份的用户数据-但在升级中，将迁移用户数据最佳做法是配置备份的方案。例如，将所有用户数据都导出到 OneDrive 帐户、 BitLocker 转加密 USB 闪存驱动器或网络文件服务器。有关详细信息，请参阅[Back up 或 Windows 中的数据传输](https://aka.ms/backuptransferdatawindows)。
- **环境准备**-将使用现有的配置管理器服务器结构准备操作系统部署。除了基本安装，应配置管理器环境中进行以下配置：
    1. [扩展 Active Directory 架构](https://aka.ms/extendadschema)并[创建系统管理容器](https://aka.ms/createsysmancontainer)。
    2. 启用 Active Directory 林发现和 Active Directory 系统发现。人员的详细信息，请参阅[Configure 发现方法的 System Center Configuration Manager](https://aka.ms/configurediscoverymethods)。
    3. 创建 IP 范围边界和内容和网站分配的边界组。有关详细信息，请参阅[定义站点边界和边界组的 System Center Configuration Manager](https://aka.ms/definesiteboundaries)。
    4. 添加并配置 reporting services 点角色配置管理器。有关详细信息，请参阅[配置报告配置管理器中](https://aka.ms/configurereporting)。
    5. 创建包文件系统文件夹结构。
    6. 创建程序包的 Configuration Manager 控制台文件夹结构。
    7. 安装 System Center Configuration Manager （当前分支） 更新和任何其他 Windows 10 必备组件。

## <a name="part-2-add-a-windows-10-os-image-using-configuration-manager"></a>第 2 部分： 添加使用 Configuration Manager Windows 10 操作系统映像
现在，您需要创建包含完整的 Windows 10 安装媒体操作系统升级程序包。在下列步骤中，您将使用 Configuration Manager 创建 Windows 10 Enterprise x64 升级的程序包。

**若要添加使用 Configuration Manager Windows 10 操作系统映像**

1. 使用 Configuration Manager 控制台中，**软件库**工作区中，右键单击**操作系统升级程序包**节点，然后选择**添加操作系统升级程序包**。
2. 在**数据源**页上，指定 Windows 10 Enterprise x64 媒体的 UNC 路径，然后选择**下一步**。
3. 在**常规**页上，指定**Windows 10 Enterprise x64 升级**，，然后选择**下一步**。 
4. 在**摘要**页中，选择**下一步**，，然后选择**关闭**。 
5. 右键单击创建的**Windows 10 Enterprise x64 更新**包，，然后选择**内容分发**。 
6. 选择分发点。

## <a name="part-3-configure-deployment-settings"></a>第 3 部分： 配置部署设置
在此步骤中，您将配置升级任务序列，其中包含 Windows 10 升级的设置。您将然后确定设备升级，，，然后向这些设备部署任务序列。

### <a name="create-a-task-sequence"></a>创建任务序列
若要创建升级任务序列，请执行以下步骤：
  
1. 在 Configuration Manager 控制台中，在**软件库**区中，展开**操作系统**。 
2. 右键单击**任务序列**节点，然后选择**创建任务序列**。
3. 在**创建新的任务序列**页中，选择**升级操作系统升级的程序包**，，然后选择**下一步**。
4. 在**任务序列信息**页中，指定**Windows 10 Enterprise x64 升级**，，然后选择**下一步**。
5. 在**Windows 操作系统升级**页上，选择**浏览**并选择**Windows 10 Enterprise x64 升级操作系统升级程序包**，选择**确定**，，然后选择**下一步**。
6. 继续根据向导其余页面中，，然后选择**关闭**。

### <a name="create-a-device-collection"></a>创建设备集合
创建升级任务序列后，您需要创建一个集合包含将升级的设备。

> [!NOTE]
> 使用以下设置来测试在一台设备上的部署。您可以使用不同的成员资格规则时要包括的设备组即可。有关详细信息，请参阅[如何创建集 System Center Configuration Manager 中](https://aka.ms/sccm-create-collections)。

1. 在 Configuration Manager 控制台中，在**资产和合规性**区中，右键单击**设备集**，然后选择**创建设备集**。 
2. 创建设备集向导，在**常规**页上，输入以下设置，然后选择**下一步**:
    - 名称： Windows 10 Enterprise x64 升级
    - 限制集合： 所有系统
3. 在**成员资格规则**页上，选择**添加规则** > **直接规则**以启动创建直接成员资格规则向导。
4. 在创建直接成员资格规则向导**欢迎**页中，选择**下一步**。
5. 在**搜索资源**页上，输入要升级的设备的名称中替换占位符**值**文本的以下设置： 
    - 资源类： 系统资源
    - 属性名称： 名称
    - 值： *PC0003*
6. 在**选择资源**页中，选择您的设备，并选择**下一步**。
7. 完成创建直接成员资格规则向导和创建设备集合向导。  
8. 查看 Windows 10 Enterprise x64 升级集合。请不要继续直至您看到机集合中添加。

### <a name="create-an-operating-system-deployment"></a>创建操作系统部署
按照以下步骤以创建部署任务序列。

1. 在 Configuration Manager 控制台中，在**软件库**区中，右键单击您在上一步中创建任务序列，然后选择**部署**。
2. 在**常规**页上，选择**Windows 10 Enterprise x64 升级**的集合中，，然后选择**下一步**。
3. 在**内容**页上，选择**下一步**。
4. 在**部署设置**页上选择以下设置，然后选择**下一步**:

    > [!NOTE]
    > 对于此测试部署，您将设置为**有空**这需要用户干预来启动部署的用途。在生产环境中，您可能希望自动使用所需的目的，这会涉及配置其他选项，如计划部署运行时部署。 

    - 操作： 安装
    - 用途： 可用

5. 在**计划**页上，接受默认设置，，然后选择**下一步**。
6. 在**用户体验**页上，接受默认设置，，然后选择**下一步**。
7. 在**通知**页上，接受默认设置，，然后选择**下一步**。
8. 在**摘要**页中，选择**下一步**，，然后选择**关闭**。

## <a name="part-5-start-the-windows-10-upgrade-task-sequence"></a>第 5 部分： Windows 10 开始升级任务序列
按照以下步骤以您要升级的设备上启动 Windows 10 升级任务序列。
 
1. 登录到 Windows 计算机，并启动**软件中心**。
2. 选择您在上一步中创建任务序列，然后选择**安装**。
3. 任务序列开始时，它自动启动的就地升级过程通过调用所需的命令行参数执行自动的升级，保留所有数据、 设置、 应用程序，与 Windows 安装程序 (Setup.exe) 和驱动程序。
4. 任务序列成功完成后，计算机会完全升级到 Windows 10。

如果您遇到问题，在企业环境中使用 Windows 10 时，您可以参考[的最常见的问题的首要 Microsoft 支持解决方案](https://docs.microsoft.com/windows/client-management/windows-10-support-solutions)。KB 文章、 更新和库文章，这些资源包括。

在您的组织内的更新的推出，过程中使用 Windows 分析更新合规性功能提供了全方位的操作系统更新合规性、 更新部署进度和失败的 Windows 10 设备疑难解答视图。此新的服务使用包括安装进度、 Windows Update 配置和其他信息的诊断数据提供此类见解，在无额外的成本和无需其他基础结构要求。是否适用于商务或其他管理工具，它使用与 Windows Update，您可以确保设备正确更新。

请参阅[监视器 Windows 更新和 Windows Defender 防病毒具有更新合规性了解详细信息，请开始，并使用更新合规性。](https://docs.microsoft.com/windows/deployment/update/update-compliance-monitor)

作为临时检查点，请查看对应于此步骤的[退出条件](windows10-exit-criteria.md#crit-windows10-step2)。

## <a name="next-step"></a>后续步骤

|||
|:-------|:-----|
|![](./media/stepnumbers/Step3.png)| [部署新设备的 Windows 自动执行某些操作 Windows 10 Enterprise](windows10-deploy-autopilot.md) |



<!--

| Phases | Description |
|:--- |:--- |
| [Phase 1: Consideration phase](#phase-1-consideration-phase) | TBD |
| [Phase 2: Testing phase](#phase-2-testing-phase) | TBD |
| [Phase 3: Deployment phase](#phase-3-deployment-phase) | TBD |

## Phase 1: Consideration phase
Before upgrading an OS in an enterprise environment, take the following technical aspects into account:
* [Infrastructure](#step-1-infrastructure)
* [Apps](#step-2-apps)
* [Governance and business processes](#step-3-governance-and-business-processes)

This guide is meant only to provide Microsoft's best recommendations around these assumptions by providing links to existing documentation.

### Step 1: Infrastructure
Consider your organization's collection of hardware, software, policies, networks, and other related technologies as part of the deployment process.

For in-place upgrade with Configuration Manager, these are the infrastructure you need to take into account:

#### Group Policy
Windows 10 introduces many new features and removes and changes many others in Windows 7 and 8.1, including new Group Policy settings which you need to test and implement as part of a Windows 10 migration. Use the examples from the following resources to assess current group policies for Windows, including Group Policy Objects in the Active Directory structure:
* [Manage Windows 10 with administrative templates](https://go.microsoft.com/fwlink/?linkid=860226) - Get step-by-step info on how to manage Windows 10 with administrative templates
* [Group Policy settings that apply to Windows 10](https://docs.microsoft.com/windows/client-management/group-policies-for-enterprise-and-education-editions) - Find out which Group Policy settings apply only to Windows 10 Enterprise

> [!NOTE]
> If you are considering moving to modern management by using MDM instead of Group Policy to manage device configurations, you can start by using the [MDM Migration Analysis Tool (MMAT)](https://github.com/WindowsDeviceManagement/MMAT) to determine what Group Policies are set on the device and report the corresponding settings, if available.

#### Data management
Although in-place upgrades shouldn’t affect user data and apps, a best practice is to configure a backup scenario and back up user data. For example, export all user data to a OneDrive for Business account, BitLocker To Go-encrypted USB flash drive, or network file server. For more details, see:
* [How to back up or transfer your data on a Windows-based computer](https://go.microsoft.com/fwlink/?linkid=860230) - Get step-by-step info on how to manually back up your personal files and settings.
* [Redirect known folders to OneDrive for Business](https://go.microsoft.com/fwlink/?linkid=846620) - Learn how to set a policy at the domain level to make sure users all sync to the same folder when they install the OneDrive sync client and how you can set additional policies to redirect the Documents folder to that sync location.

#### System Center Configuration Manager
This guide assumes you are following Microsoft recommendations and have one of the following versions of System Center Configuration Manager 2012 onward:
* System Center 2012 Configuration Manager with SP2
* System Center 2012, 2012 R2 Configuration Manager with SP1, Current Branch, 1706
    * [Run an in-place upgrade to the latest Configuration Manager](https://go.microsoft.com/fwlink/?linkid=839406)
    * [Updates for Configuration Manager](https://go.microsoft.com/fwlink/?linkid=620343)
* Core Configuration Manager configuration:
    * CONFIGURATION MANAGER accounts
    * Active Directory permissions
    * Source folder structure
    * Active Directory schema
* Configure the following [necessary Configuration Manager components for Windows 10 deployment](https://go.microsoft.com/fwlink/?linkid=860245):
    * **State migration point** - Stores user state migration data during computer replace scenarios
    * **Distribution point** - Stores all packages in Configuration Manager
    * **Software update point** - Updates an OS as part of the deployment process
    * **Reporting services point** - Monitors the OS deployment process
    * **Boot images** - Are Windows Preinstallation Environment (PE) images used by Configuration Manager to start deployments
    * **OS images** - Denotes the production deployment image (mounted OS)
    * **OS installers** - Creates reference images using Microsoft Deployment Toolkit (MDT) Light Touch
    * **Drivers** - Denotes a repository of managed device drivers
    * **Task Sequence** - Is delivered automatically to the client as a policy

#### Network bandwidth
This guide assumes you have enough network bandwidth to support the deployment of Windows 10 Enterprise and Office 365 ProPlus as a unit. As a bundle, network bandwidth is a significant factor.

#### Client machines and in-place upgrade scenario
* Disk encryption - Third-party disk encryption isn't supported in an in-place upgrade scenario.
* User profiles - Only the standard user profile type is supported.
* Legacy BIOS to Unified Extensible Firmware Interface (UEFI) booting - Changing from legacy BIOS to UEFI booting isn't supported.
* Dual-boot - This scenario is not covered in the guide. If you have the FastTrack Benefit, it only covers devices running a single OS.
* Virtual desktop infrastructure (VDI) environments - This scenario is not covered in the guide. If you have the FastTrack Benefit, it doesn't cover configuration or deployment on VDI environments.
* x64 and x86 - Changing from a 32-bit OS to a 64-bit isn't supported. For more info, see [Windows 10 deployment scenario > In-place upgrade](https://docs.microsoft.com/windows/deployment/windows-10-deployment-scenarios#in-place-upgrade).

### Step 2: Apps

#### Security
Security clients (like antivirus, anti-malware, and anti-spam) are typically found on all PCs within an organization. Because these programs hook into the deeper levels of the OS, you may need to perform a compatibility assessment before starting any Windows 10 migrations. You may need to upgrade, reconfigure, or even replace Some software. Not performing this assessment can lead to:
* Native app compatibility checks failing and preventing an in-place upgrade from starting.
* Broken functionality in the security software.
* Instability after upgrading to Windows 10 (like crashing and reduced performance)

**Antivirus**

Assess current antivirus software. Windows 10 comes with Windows Defender Antivirus to protect devices from malware, viruses, and security threats. We recommend Windows Defender Antivirus. To enable Windows Defender Antivirus, see [Windows Defender Antivirus](windows10-enable-security-features.md#windows-defender-antivirus) and [Protect devices with Windows Defender Antivirus](https://go.microsoft.com/fwlink/?linkid=860254).

To learn about antivirus solutions from other providers, see [Consumer antivirus software providers for Windows](https://go.microsoft.com/fwlink/?linkid=67345).

#### App readiness
Each Windows 10 release provides improved app compatibility. However, some apps may not be compatible. Depending on the app, you may need to only do a simple upgrade or configuration update before upgrading to Windows 10. In other circumstances, you may need to remove an app entirely.

Be sure to assess business critical apps and understand the impact of upgrading to the next OS. Prioritize the workloads that impact the least number of people during deployment. 

See the following Upgrade Readiness resources to help with app inventory, driver compatibility issues, and usage information:
* [Manage Windows Upgrades with Upgrade Readiness](https://go.microsoft.com/fwlink/?linkid=860255) - Learn about the tools to help you plan and manage the upgrade process end to end, which allow you to adopt new Windows releases more quickly.
* [Configure Windows diagnostic data](https://go.microsoft.com/fwlink/?linkid=859970) - Find out about the importance of Windows diagnostic data and how Microsoft protects that data.

> [!NOTE]
> Upgrade Readiness may not be able to assess compatibility for custom and line-of-business (LOB) apps in an organization.

#### Language packs
In-place upgrades have have limitations when it comes to language packs. The language stays consistent throughout the upgrade. Verify the language version and make sure it stays consistent. For example, Windows 7 with English as the default won’t change when upgraded to Windows 10. For more info, see:
* [Default language pack on your OS](https://go.microsoft.com/fwlink/?linkid=860282)
* [Finding language packs on each Windows 10 deployment](https://go.microsoft.com/fwlink/?linkid=860283)

For a Microsoft 365 powered device, you'll also need to download Office 365 ProPlus language packs that applies to the client. These come in 32-bit (x86) or 64-bit (x64). A specific language must be installed as the default. You can install other languages later. For more info, see:
* [Choose between 64-bit or 32-bit version of Office](https://go.microsoft.com/fwlink/?linkid=862361) - Helps you decide which version of Office is right for you.
* [Language accessory pack for Office](https://go.microsoft.com/fwlink/?linkid=860280) - Follow the steps to install the language accessory pack for Office.
* [Add an additional language pack](https://go.microsoft.com/fwlink/?linkid=860281) - Get step-by-step info on adding a language or setting language preferences in Office.

### Step 3: Governance and business processes

#### Windows as a service
Windows 10 introduced the concept of Windows as a service. This greatly changes the frequency and style of updates to Windows. Instead of new versions being released every 3-5 years, a more incremental model is used where two smaller updates (Feature Updates) are released yearly. For more info, see:
* [Windows as a service on the Windows IT Pro Center](https://www.microsoft.com/itpro/windows-10/windows-as-a-service)
* [Overview of Windows as a service](https://go.microsoft.com/fwlink/?linkid=860288)
* [Update Windows 10 in the enterprise](https://go.microsoft.com/fwlink/?linkid=860285)

#### Pilot users and deployment rings
Be sure to have a pilot group of users selected from different parts of the business. If you have Microsoft 365 powered devices, Windows 10 and Office 365 ProPlus users should be in these deployment rings. This affects future Windows updates as well (including features and quality). You need to create and edit device collections by deployment rings to help minimize the effect on network bandwidth and simplify future updates. 

For the group of pilot users, create a device collection on Configuration Manager. The list of devices should correspond to the list of the first users upgraded to Windows 10. 

**Windows 10 deployment rings**

There are three servicing channels for OS deployment rings:
* Windows Insider Program - Provides organizations with the opportunity to test and provide feedback on features that are shipped in the next feature update.
* Semi-Annual Channel - Provides new functionality with twice-per-year feature update releases. Organizations can choose when to deploy updates from the Semi-Annual Channel.
* Long-Term Servicing Channel (LTSC) - Used for specialized devices and receives new feature releases about every three years.

For more info, see:
* [Windows Insider Program, Semi-Annual Channel, and Long-Term Servicing Channel](https://go.microsoft.com/fwlink/?linkid=860293)
* [Build deployment rings for Windows 10 updates](https://go.microsoft.com/fwlink/?linkid=860294)
* [Manage software updates using Intune in Azure Portal](https://docs.microsoft.com/intune/windows-update-for-business-configure)

**Office 365 ProPlus**

For Microsoft 365 powered devices, you must also be able to support the six-month update channel for both IT and business users. One way to do so is to have three groups:
* Current Channel
* Deferred Channel
* First-release for Deferred Channel

Each group has different configuration files, as users from the Current Channel are used as a pilot to test earlier updates. For more info, see:
* [Update process for Office 365 ProPlus](https://go.microsoft.com/fwlink/?linkid=860299)
* [Manage updates to Office 365 ProPlus](https://go.microsoft.com/fwlink/?linkid=860300)
* [Configure update settings for Office 365 ProPlus](https://go.microsoft.com/fwlink/?linkid=860301)
* [Update channels for Office 365 ProPlus](https://go.microsoft.com/fwlink/?linkid=860302)
* [Version and build numbers of update channel releases](https://go.microsoft.com/fwlink/?linkid=860304)

For more info, see [Phase 4: Office 365 ProPlus infrastructure for Microsoft 365 Enterprise](office365proplus-infrastructure.md).

## Phase 2: Testing phase
Once you've completed the scenarios and requirements in [Step 1: Consideration phase](#step-1-consideration-phase), you can move to this stage.
* [Networking](#step-1-networking)
* [Identity](#step-2-identity)
* [Client readiness](#step-3-client-readiness)
* [System Center Configuration Manager](#step-4-system-center-configuration-manager)
* [Diagnostic data](#step-5-diagnostic-data)

### Step 1: Networking
Ports to the client need to be opened for Office 365 ProPlus (for a Microsoft 365 powered device) and Configuration Manager. For more details about setting up your Microsoft 365 Enterprise networking infrastructure, see [Phase 1: Networking](networking-infrastructure.md).

When setting up your networking infrastructure as part your in-place upgrade, make sure you complete these steps:
1. Read the best practices for [network planning and improving migration performance for Office 365](http://go.microsoft.com/fwlink/?LinkId=733655).
2. [Plan for network devices that connect to Office 365 services](http://go.microsoft.com/fwlink/?LinkId=733652).
3. [Review network impact of directory synchronization](http://go.microsoft.com/fwlink/?LinkId=733652).
4. Calculate the number of clients to use per IP address and understand [Network Address Translation (NAT) support with Office 365](http://go.microsoft.com/fwlink/?LinkId=733653) and how it impacts the number of users and client devices you can serve with a single IP address.
5. If your organization restricts computers on your network from connecting to the Internet, you'll need to understand the [endpoints (fully qualified domain names (FQDNs), ports, URLs, IPv4, and IPv6 address ranges)](http://go.microsoft.com/fwlink/?LinkID=280129) that you should include in your outbound allow lists to ensure your computers can successfully use Office 365 services.
6. [Create domain name system records for Office 365 at any Domain Name System hosting provider](http://go.microsoft.com/fwlink/?LinkId=733656).
7. [Reduce mail exchange (MX) DNS record time to live (TTL) value](http://go.microsoft.com/fwlink/?LinkId=733656).

### Step 2: Identity
Intelligent security for Microsoft 365 Enterprise, in which the right users have access to the right resources with an appropriate level of access, begins with identity management. For more details about setting up your Microsoft 365 Enterprise identity infrastructure, see [Phase 2: Identity](identity-infrastructure.md).

When setting up your identity infrastructure as part of your in-place upgrade, make sure you complete these tasks:
1. [Add a domain and users to Office 365](http://go.microsoft.com/fwlink/?LinkID=526338).
2. [Install and run the Office 365 IdFix tool](http://go.microsoft.com/fwlink/?LinkId=733662), which scans your on-premises Active Directory environment and identifies problems that might impact directory synchronization and slow your migration to Office 365.
3. Configure Active Directory for directory synchronization with Office 365 and [integrate on-premises directories with Azure AD](http://go.microsoft.com/fwlink/?LinkId=733661).
4. [Prepare to provision users through directory synchronization to Office 365](http://go.microsoft.com/fwlink/?LinkId=733659).
5. Know the [prerequisites for Azure AD Connect](http://go.microsoft.com/fwlink/?LinkId=733663), then install and run the Azure AD Connect tool to synchronize your on-premises Active Directory to the Azure AD service used by Office 365.
6. Determine custom installation of Azure AD Connect (full version of SQL Server for directory synchronization, if required).
7. [Integrate your on-premises identities with Azure AD](http://go.microsoft.com/fwlink/?LinkID=733485).
8. [Sync a list of required attributes with AD Connect](https://go.microsoft.com/fwlink/?linkid=860363) to get all the features in Office 365 and Windows 10.
9. Activate Windows 10 Enterprise licenses, which are checked based on Azure AD credentials.

    This provides a systematic way to assign licenses to end users and groups in your organization. For more info, see [Windows 10 Subscription Activation](https://go.microsoft.com/fwlink/?linkid=860365) and [Deploy Windows 10 licenses](https://go.microsoft.com/fwlink/?linkid=860367).

### Step 3: Client readiness

#### System requirements for Office 365
Confirm that Windows 10 works with Office 365. Be sure you're using the latest OS version and browsers with Office 365 and have updated them with the latest service packs. For more info on Office requirements, see [System requirements for Office](http://go.microsoft.com/fwlink/?LinkID=394412).

### Step 4: System Center Configuration Manager
See [System Center Configuration Manager](#system-center-configuration-manager).

### Step 5: Diagnostic data
Microsoft uses diagnostic data to help keep Windows devices secure by identifying malware trends and other threats and to help us improve the quality of Windows and Microsoft services. You must ensure that the diagnostics service is enabled at a minimum level of Basic on all endpoints in your organization. **By default, this service is enabled and set to the Enhanced level.** However, it’s good practice to check and ensure that they are receiving sensor data. Setting levels through policies overrides device-level settings. 

**Windows 10 operating system diagnostic data levels**

You can configure your operating system diagnostic data settings using the management tools you’re already using, such as Group Policy, MDM, or Windows Provisioning. You can also manually change your settings using Registry Editor. Setting your diagnostic data levels through a management policy overrides any device level settings.

Use the appropriate value in the table below when you configure the management policy.

| Level | Data gathered | Value |
|:--- |:--- |:--- |
| Security | Security data only. | 0 |
| Basic | Security data, and basic system and quality data. | 1 |
| Enhanced | Security data, basic system and quality data, and enhanced insights and advanced reliability data. | 2 |
| Full | Security data, basic system and quality data, enhanced insights and advanced reliability data, and full diagnostics data. | 3 |

You can enable diagnostics data through these methods:
* Microsoft Intune - If you plan to use Intune to manage your devices, you can create a configuration policy to enable diagnostic data by configuring the <a href="https://docs.microsoft.com/windows/client-management/mdm/policy-csp-system#system-allowtelemetry" target="blank">SystemAllowTelemetry</a> system policy. For more info on setting up configuration policies, see [Manage settings and features on your devices with Microsoft Intune policies](https://aka.ms/intuneconfigpolicies).
* Registry Editor - You can use the Registry Editor to manually enable diagnostic data on each device in your organization, or write a script to edit the registry. If a management policy already exists, such as Group Policy or MDM, it will override this registry setting.
* Group Policy - If you do not plan to enroll devices in Intune, you can use a Group Policy object to set your organization’s diagnostic data level.
* Command prompt - You can set Windows 10 diagnostics data and service to automatically start with the command prompt. This method is best if you are testing the service on only a few devices. Enabling the service to start automatically with this command will not configure the diagnostic data level. If you have not configured a diagnostic data level using management tools, the service will operate with the default Enhanced level.

See [Configure Windows diagnostic data in your organization](https://docs.microsoft.com/windows/configuration/configure-windows-diagnostic-data-in-your-organization) to learn more about Windows diagnostic data and how you can enable it based on the method that you choose.

## Phase 3: Deployment phase
When ready, complete these:
* [In-place upgrade to Windows 10 Enterprise](#31-in-place-upgrade-to-windows-10-enterprise)
* [Windows Defender Antivirus](#32-windows-defender-antivirus)

### Step 1: In-place upgrade to Windows 10 Enterprise
1. Integrate System Center Configuration Manager with Microsoft Deployment Tool.

    Be sure to use the Microsoft Deployment Toolkit (MDT) in conjunction with Configuration Manager when deploying an updated version of Windows 10. MDT brings Zero Touch Installation and Light Touch Installation enhancements to help with deployments at no cost to the customer. For more info, see:
    * [Download the latest MDT](https://go.microsoft.com/fwlink/?linkid=860465)
    * [Deploy Windows 10 with the Microsoft Deployment Toolkit](https://go.microsoft.com/fwlink/?linkid=860466)

2. Prepare for zero touch installation.

    As part of zero touch installation, you are responsible for preparing the following:
    * Configuration Manager service accounts
    * Active Directory permissions
    * Source folder structure

    Then, [integrate Configuration Manager with MDT](https://go.microsoft.com/fwlink/?linkid=860035).

3. Create a custom Windows Preinstallation Environment boot image.

    Windows Preinstallation Environment (PE) is a pre-installation environment required for OS deployments. It’s used to prepare a client machine for Windows installation, to copy disk images from a network file server, and to initiate Windows Setup. It’s used for Windows 10 Enterprise editions. For more info, see:
    * [Overview of Windows PE](https://go.microsoft.com/fwlink/?linkid=860468)
    * [Windows PE features, hardware requirements, and limitations](https://go.microsoft.com/fwlink/?linkid=860469)
    * [Create a custom Windows PE boot image with Configuration Manager](https://go.microsoft.com/fwlink/?linkid=860470)

4. Add a Windows 10 OS upgrade image.

    You need to create a Windows 10 reference image with MDT (as needed). Reference images are the foundation of what each of the client machine’s OS looks like. The image should be in a separate folder located with the already-mounted ISO file. The task sequence looks for and then runs “setup.exe”. 

    Follow the steps to create and add a Windows 10 OS upgrade image on Configuration Manager:
    * [Create a Windows 10 reference image](https://go.microsoft.com/fwlink/?linkid=860500)
    * [Add a Windows 10 OS image using Configuration Manager](https://go.microsoft.com/fwlink/?linkid=860501)

5. Create an app to deploy with Windows 10.

    For a Microsoft 365 powered device, you can deploy Office 365 ProPlus with Windows 10 Enterprise using Configuration Manager. You can also add other apps as needed.

    To deploy Office 365 ProPlus, follow the steps in [Phase 4: Office 365 ProPlus infrastructure for Microsoft 365 Enterprise](office365proplus-infrastructure.md). During this phase, make sure you complete these steps:
    
    1. Download the Office 2016 Deployment Tool (ODT) in conjunction with Configuration Manager to help with Office 365 ProPlus deployments. 
    2. Edit the configuration XML file to fit specific deployment needs (like version, language, and product element). 
    
    You can then create apps with Configuration Manager. For more info, see:
    * [Configuration options for ODT](https://go.microsoft.com/fwlink/?linkid=860504)
    * [Create apps in Configuration Manager](https://go.microsoft.com/fwlink/?linkid=761079)
    * [Deploy Office 365 ProPlus with Configuration Manager](https://go.microsoft.com/fwlink/?linkid=860506)

6. Add drivers to a Windows 10 deployment using Windows PE.

    Network drivers need to be created for both Windows PE and Windows 10 to connect deployment shares and storage drivers with local storage on a client computer. Use Configuration Manager to create these drivers required for deployment. For more info, see [Add drivers to a Windows 10 deployment with Windows PE using Configuration Manager](https://go.microsoft.com/fwlink/?linkid=860036).

7. Create a task sequence.

    A task sequence (a collection of commands) is required for MDT Lite Touch Installation (LTI). You need to create and then edit the task sequence for optimal deployment experience. One of the configurations enable support for Unified Extensible Firmware Interface (UEFI). The UEFI environment is a minimal boot OS where devices are booted and the Windows 10 OS runs. For more info, see:
    * [Overview of Windows Boot Manager](https://go.microsoft.com/fwlink/?linkid=860696)
    * [Create the task sequence in Configuration Manager](https://go.microsoft.com/fwlink/?linkid=860697)

8. Finalize the OS configuration for Windows 10 deployment.

    **To finalize the OS configuration**

    1. Enable MDT monitoring
    2. Create and share the Logs folder
    3. Configure the rules
    4. Distribute content to the distribution point (a server running Configuration Manager)
    5. Create a deployment for the task sequence

   For more info, see [Finalize OS configuration with Configuration Manager](https://go.microsoft.com/fwlink/?linkid=860697).

9. Deploy the Windows 10 Enterprise image to a UEFI machine.

    For more info, see [Deploy Windows 10 using Configuration Manager](https://go.microsoft.com/fwlink/?linkid=860697).

10. Monitor the Windows 10 deployment.

    Use Configuration Manager and MDT to monitor your deployment. Deployment Workbench enables access to the computer remotely using the Diagnostics and Recovery Toolset (DaRT) (optional). Deployments can be monitored in Configuration Manager. For more info, see [Monitor the Windows 10 deployment with Configuration Manager](https://go.microsoft.com/fwlink/?linkid=860705).

### Step 2: Windows Defender Antivirus
See [Enable Windows 10 Enterprise security features > Windows Defender Antivirus](windows10-enable-security-features.md#windows-defender-antivirus)

-->
