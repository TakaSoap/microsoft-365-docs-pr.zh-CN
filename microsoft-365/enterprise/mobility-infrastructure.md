---
title: 阶段 5-移动设备管理
description: Microsoft 365 企业版包括使用 Microsoft Intune 的移动设备管理。查看要求和先决条件，设置 Intune 使用 Azure Active Directory 资源，注册 iOS、 macOS、 Android 和 Windows 设备，部署应用程序、 创建配置配置文件、 使用合规性策略，并启用条件移动访问与 Microsoft 365 Enterprise 的设备管理。
keywords: Microsoft 365 Microsoft 365 企业版，Microsoft 365 文档，移动设备管理 Intune
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 09/18/2018
ms.topic: conceptual
audience: ITPro
ms.prod: microsoft-365-enterprise
ms.service: ''
ms.technology: ''
ms.assetid: fb4182e6-5e78-45d0-9641-d791c4519441
ms.custom: microsoft-intune
ms.openlocfilehash: 8d048ec6628cb8f7cb9c5e0d4c7960481bc69de1
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2018
ms.locfileid: "26866056"
---
# <a name="phase-5-mobile-device-management-for-microsoft-365-enterprise"></a>第 5 阶段： Microsoft 365 enterprise 的移动设备管理

![](./media/deploy-foundation-infrastructure/mobiledevicemgmt_icon.png)

*此功能适用于 Microsoft 365 企业版 E3 和 E5 版本*

Microsoft 365 企业版包括可帮助管理设备和其应用程序，贵组织中的功能。使用 Microsoft Intune，您可以管理 iOS、 Android、 macOS 和 Windows 设备来保护对组织的资源，包括您的数据访问。Intune 与 Azure Active Directory (Azure AD)、 集成和 Microsoft 365 启用以下商业应用场景：

- 存储和共享组织内部和外部的文件，以跨组织边界无缝工作
- 随时随地跨设备安全工作，在保持灵活工作方式的同时实现更多功能
- 提供尽可安心的控件和可见性，行业认证达标且符合全球标准
- 保护信息并降低数据丢失的风险
- 检测和防范外部威胁
- 监视、 报告和分析活动迅速做出反应以提供组织的安全
- 保护您的用户和其帐户

有关详细信息，请参阅[使用 Microsoft 365 实现数字化化转型](http://transform.microsoft.com)。 

在此阶段中，您注册您的设备中 Intune，并创建和强制实施策略，以帮助保护您的数据的安全和受保护。Intune 文档的整个库[可用联机](https://docs.microsoft.com/intune)。它也是最好是在开始之前查看[Intune 部署规划、 设计和实施的指南](https://docs.microsoft.com/intune/planning-guide)。

## <a name="step-1-plan-for-your-scenario"></a>步骤 1： 规划您的方案

管理移动设备的主要原因之一是安全和保护组织的资源。[使用 Microsoft Intune 的常用方法](https://docs.microsoft.com/intune/common-scenarios)列出了一些现实世界的示例，包括保护 Office 365 电子邮件和数据。

Intune 为您提供了选项来管理您的组织使用[移动设备管理 (MDM) 或移动应用程序管理 (MAM)](https://docs.microsoft.com/intune/byod-technology-decisions)的访问。用户"注册"Intune 在其设备时 MDM。一旦注册，它们是托管的设备，并且可以接收任何策略、 规则和使用您的组织的设置。例如，可以安装细节应用程序、 创建密码策略、 安装 VPN 连接，等等。

使用自己的个人设备的用户可能不希望注册其设备，或由 Intune 和您的策略。但是，您仍需要保护组织的资源和数据。在此方案中，您可以保护您的应用程序使用 MAM。例如，您可以使用要求用户在设备上访问 SharePoint 时输入 PIN MAM 策略。

您还将决定如何您要管理个人或组织拥有的设备。您可能想要将设备有所不同，具体取决于其使用。例如，您可能需要的不同的计划的用户以人力资源 (HR) 或销售中的用户。[标识移动设备管理用例方案](https://docs.microsoft.com/intune/planning-guide-scenarios)可以帮助您开始，并包括对这些不同方案的一些指导。

## <a name="step-2-get-your-prerequisites"></a>步骤 2： 获取必备组件

接下来，获取必备组件根据要求和您在上一步中创建的方案。[实现您的计划](https://docs.microsoft.com/intune/planning-guide-onboarding)列出所有的要求。下面是与 Microsoft 365 Intune 所需的大量项目：

- **Intune 订阅**： 包含与 Microsoft 365 和[Azure 门户](https://portal.azure.com)中的 Microsoft Intune 访问
- **Office 365 订阅**： 包含与 Microsoft 365，并用于 Office 应用程序，包括电子邮件
- **Azure Active Directory (AD) premium**： 包含与 Microsoft 365 和用于创建用户或安全组。这些组接收 Intune 策略的创建，如强制解锁设备的密码长度。在所创建的组[第 2 阶段： 标识](https://docs.microsoft.com/microsoft-365/enterprise/identity-infrastructure)可用。

可能有一些其他要求，具体取决于您组织的需求。例如，如果您将管理 iOS 设备，您将需要 Apple MDM 推送证书。如果您使用内部部署 Exchange，然后您将需要在本地 Exchange 连接器。当您进入这些步骤概述了这些其他要求。

## <a name="step-3-set-up-intune"></a>步骤 3： 设置 Intune

Intune 使用 Azure AD，包括您的域、 您的用户和组中的许多功能。您还可以创建新用户和新组，以适应公司的需要。例如，您可以创建一个名为**iOS 设备**或**所有 HR 用户**组。 利用[动态组](https://docs.microsoft.com/intune/groups-add)，可用于构建用户或基于简单或高级规则周围的设备组。

此步骤重点介绍设置 Intune，并获取就可以管理您的设备。

1. **[确认您的设备支持](https://docs.microsoft.com/intune/supported-devices-browsers)**。确认您的 iOS macOS，Intune 支持 Android、 生命和 Windows 设备。如果您的组织包括不受支持的设备，策略不会应用到这些设备。

2. **[自定义您的域名](https://docs.microsoft.com/intune/custom-domain-name-configure)**。默认情况下，域命名为类似**your domain.onmicrosoft.com**自动创建 Azure AD 中。可以为组织定制**onmicrosoft.com** 。自定义时，它还为用户提供了熟悉的域连接时 Intune 和使用资源。

3. **[登录到 Intune](https://docs.microsoft.com/intune/account-sign-up)**。您登录时，您可能会提示输入您的组织的信息。Intune 随 Microsoft 365，并且可以直接从[Office 365 管理门户](https://portal.office.com/)中打开。您也可以直接从[Azure 门户](https://portal.azure.com)打开 Intune。

4. **[选择您的移动设备管理配置](https://docs.microsoft.com/intune/mdm-authority-set)**。首次使用 Intune，您必须启用设备管理。Intune 可用作一个仅使用云的服务，与 Intune 和 System Center Configuration Manager，或使用移动设备管理 Office 365 的混合。您可以选择将安装程序适合于您的组织。

5. **[添加用户](https://docs.microsoft.com/intune/users-add)** 并**[添加组](https://docs.microsoft.com/intune/groups-add)**。 

   您可以手动添加用户，或连接到 Azure AD 同步用户与 Intune。您还可以向特定用户授予管理员角色。用户是必需的除非您的设备"userless"设备，如网亭设备。

   Azure AD 组用于简化管理设备和 Intune 中的用户的方式。使用组，您可以执行许多不同的任务。例如，您的组织希望需要 Android 设备上的特定应用程序。可以创建 Android 设备组，和部署到组与此应用程序的策略。

    在 Intune，您可以添加用户或组中创建的[第 2 阶段： 标识](https://docs.microsoft.com/microsoft-365/enterprise/identity-infrastructure)

6. **[分配许可证](https://docs.microsoft.com/intune/licenses-assign)**。为用户或设备 Intune 中注册，他们需要在设备上的许可证。每个用户或 userless 设备需要访问 Intune 服务 Intune 许可证。这些许可证包含与 Microsoft 365，必须在 Intune 分配。

## <a name="step-4-enroll-devices"></a>步骤 4： 注册设备

若要管理设备，必须在 Intune 注册设备。作为管理员，您将设置注册限制和策略为用户和设备。每个设备平台 （iOS、 Android、 macOS 和 Windows） 都有多种选项。您可以让您注册自己的用户。或者，因此用户只需登录到设备，可以自动注册。

注册时使用 Intune 的主要步骤。[注册设备](https://docs.microsoft.com/intune/device-enrollment)列出的不同设备的步骤。

|||
|:-------|:-----|
|![Microsoft 云测试实验室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [测试实验室指南： iOS 和 Android 设备注册](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md) |
|||


## <a name="step-5-add-and-deploy-apps"></a>步骤 5： 添加和部署应用程序

在移动设备上的应用程序通常是最快方式用户有权访问您的企业资源。 

有难题时使用应用程序，如有不同的设备，包括个人设备和公司的设备。然后您想要同时使得确保用户提高生产效率保护组织的资源和其数据。

Intune 可以管理应用程序，包括添加应用程序，将其分配给不同的用户或组，并查看其他关键详细信息。例如，您可以看到的应用程序无法安装，请检查应用程序和更多的版本。

当用户获取移动设备时，第一个任务之一是访问组织的电子邮件和文档。使用 Intune，您可以[创建和部署电子邮件设置](https://docs.microsoft.com/intune/email-settings-configure)使用预安装的电子邮件应用程序在设备上。 

[添加应用程序](https://docs.microsoft.com/intune/app-management)列出了添加、 部署、 监控、 配置和保护您的组织内的设备上的应用程序的步骤

|||
|:-------|:-----|
|![Microsoft 云测试实验室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [测试实验室指南： 移动应用程序管理策略](mam-policies-for-your-microsoft-365-enterprise-dev-test-environment.md) |
|||

## <a name="step-6-turn-on-compliance-and-conditional-access"></a>步骤 6： 启用合规性和条件的访问

在上一步骤中，您可以设置您的环境，并启用 Intune。现在，您就可以创建使用合规性和条件访问一些策略。

合规性和条件访问十分重要管理设备。创建**[合规性策略](https://docs.microsoft.com/intune/device-compliance-get-started)** 来帮助保护贵组织的资源。创建合规性策略时，您定义的标准版或设备必须具有的"基线"。例如，可以选择可接受 （或不可接受） 威胁级别、 阻止 jailbroken 设备、 需要密码长度和更多内容。如果这些设备不能满足您的规则，这意味着它们不兼容，然后您可以阻止访问到您的资源。

此"阻止"介绍**[条件的访问](https://docs.microsoft.com/intune/conditional-access)**。如果设备被视为不兼容，您可以阻止访问电子邮件、 SharePoint、 和的详细信息。

Intune [Azure 门户](https://portal.azure.com)中的可以创建这些策略，并将它们应用于您的用户和设备。作为最佳实践，开始的并使用分阶段的方法。例如，创建 iOS 策略阻止 jailbroken 设备。应用到试验或测试组策略 （称为"分配"Intune 中的）。初始测试后，将更多的用户添加到试用组。使用分阶段的方法，您可以获得各种各样的用户类型的反馈。

[开始使用设备合规性策略](https://docs.microsoft.com/intune/device-compliance-get-started)和[条件访问是什么？](https://docs.microsoft.com/intune/conditional-access)可帮助您开始。

## <a name="step-7-apply-features-and-settings"></a>步骤 7： 应用功能和设置

这些功能和设置通常被视为 Intune 的"很酷"部分，而是非常强大。您已成功实施后使用条件 access 某些法规遵从性策略，您就可以创建**设备配置文件**。

Intune [Azure 门户](https://portal.azure.com)中的，可以创建基于设备平台-iOS、 macOS、 Android 和 Windows 不同的配置文件。例如，您可以：

- 使用 Windows 10 设备上终结点保护启用不同 BitLocker 选项，包括加密。
- 在 iOS 设备上使用受限的应用程序功能创建的已批准可安装的应用程序的列表。或者，创建禁止应用程序的列表。
- 使用网亭设置选择的应用程序可用于在展台模式下运行的 Android 设备。
- 应用 Wi-fi 连接和其设置，包括运行 macOS 设备上的安全类型。
- 等

[Microsoft Intune 设备配置文件是什么？](https://docs.microsoft.com/intune/device-profiles)是很好的阅读有关配置文件，请参阅如何创建一个配置文件和更多内容。

请记住，启动小，以及使用分阶段的方法。将配置文件分配到试验或测试组。然后，将配置文件分配给更多的试点组。

## <a name="step-8-get-to-know-the-other-features"></a>步骤 8： 获取要了解其他功能

Intune 是一个强大的服务，并且包含许多功能。下面是您可以使用 Intune 的某些其他任务：

- 在 Windows[设备](https://docs.microsoft.com/intune/windows-update-for-business-configure)软件和更新管理 & [Pc](https://docs.microsoft.com/intune/keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune)和[iOS](https://docs.microsoft.com/intune/software-updates-ios)设备
- 在[Windows Defender 高级威胁保护 (ATP)](https://docs.microsoft.com/intune/advanced-threat-protection)上打开 Windows 10 设备，并使用合规性和条件访问保护访问公司资源，如 SharePoint 或 Exchange Online
- 使用[开始构想](https://docs.microsoft.com/intune/lookout-mobile-threat-defense-connector)、 [Symantec](https://docs.microsoft.com/intune/skycure-mobile-threat-defense-connector)和其他移动防御威胁合作伙伴
- 添加[合作伙伴证书颁发机构 (CA)](https://docs.microsoft.com/intune/certificate-authority-add-scep-overview)颁发和续订证书
- [向最终用户提供指南](https://docs.microsoft.com/intune/end-user-educate)的公司门户应用程序、 获取应用程序，以及的详细信息
- 监视器[应用程序](https://docs.microsoft.com/intune/apps-monitor)、 监视器[设备合规性](https://docs.microsoft.com/intune/compliance-policy-monitor)、 监视器[配置配置文件](https://docs.microsoft.com/intune/compliance-policy-monitor)，和更多遥测使用审核日志。您还可以连接到[Intune 数据仓库](https://docs.microsoft.com/intune/reports-nav-create-intune-reports)并使用 Power BI 更多的报告需求。


## <a name="identity-and-device-access-recommendations"></a>标识和设备访问建议

Microsoft 提供的一组的[标识和设备的访问](microsoft-365-policies-configurations.md)，以确保安全和高效的劳动力的建议。设备访问使用的建议和设置中的以下文章以及步骤本阶段中：

- [先决条件](identity-access-prerequisites.md)
- [常见标识和设备访问策略](identity-access-policies.md)

## <a name="how-microsoft-does-microsoft-365-enterprise"></a>Microsoft 如何使用 Microsoft 365 企业版

了解如何在 Microsoft 的 IT 专家规划和部署这些资源的 EMS 和设备管理：

- [通过企业移动性 + 安全性管理新式移动效率](https://www.microsoft.com/itshowcase/Article/Content/972/Managing-modern-mobile-productivity-with-Enterprise-Mobility--Security)
- [通过 Microsoft Intune 在 Windows 10 设备上连接到工作内容](https://www.microsoft.com/itshowcase/Article/Content/783/Connecting-to-work-on-your-Windows-10-device-with-Microsoft-Intune)
- [在 Microsoft 推动 iOS、OS X 和 Android 设备的移动效率](https://www.microsoft.com/itshowcase/Article/Content/773/Enabling-mobile-productivity-for-iOS-OS-X-and-Android-devices-at-Microsoft)

## <a name="how-contoso-did-microsoft-365-enterprise"></a>Contoso 是如何使用 Microsoft 365 企业版的

请参阅如何与 Microsoft 365[部署其移动设备管理基础结构](contoso-mdm.md)Contoso Corporation 虚构但代表性跨国企业，云服务。

![](./media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a>后续步骤

[移动设备管理基础结构退出条件](mobility-infrastructure-exit-criteria.md)

