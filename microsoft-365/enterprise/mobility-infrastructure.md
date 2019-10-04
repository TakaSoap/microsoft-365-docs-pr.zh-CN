---
title: 第5阶段-移动设备管理
description: Microsoft 365 企业版包括使用 Microsoft Intune 的移动设备管理。 查看要求和先决条件、使用 Azure Active Directory 资源设置 Intune、注册 iOS、macOS、Android 和 Windows 设备、部署应用、创建配置配置文件、使用合规性策略，以及为移动启用条件访问Microsoft 365 企业版的设备管理。
keywords: Microsoft 365，Microsoft 365 企业版，Microsoft 365 文档，移动设备管理，Intune
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 10/03/2019
ms.topic: conceptual
ms.prod: microsoft-365-enterprise
ms.service: ''
ms.technology: ''
ms.assetid: fb4182e6-5e78-45d0-9641-d791c4519441
audience: ITPro
ms.custom: microsoft-intune
ms.openlocfilehash: dd73f32ff3c830104777aeefb1271178031a5b0d
ms.sourcegitcommit: d4aa94716b33e6c270ae7adfbdc4c19cf4a0087d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/03/2019
ms.locfileid: "37386139"
---
# <a name="phase-5-mobile-device-management-for-microsoft-365-enterprise"></a>第5阶段： Microsoft 365 企业版的移动设备管理

![第5阶段：移动设备管理](./media/deploy-foundation-infrastructure/mobiledevicemgmt_icon.png)

*此功能适用于 Microsoft 365 企业版的 E3 和 E5 版本*

Microsoft 365 企业版包括帮助管理组织内的设备及其应用程序的功能。 使用 Microsoft Intune，可以管理 iOS、Android、macOS 和 Windows 设备，以保护对组织的资源（包括您的数据）的访问。 

在此阶段中，您将在 Intune 中注册设备，并创建并强制实施策略以帮助保持数据的安全和受保护。 完整的 Intune 文档库[可在线使用](https://docs.microsoft.com/intune)。 在开始之前，最好先查看[Intune 部署规划、设计和实施指南](https://docs.microsoft.com/intune/planning-guide)。

## <a name="step-1-plan-for-your-scenario"></a>步骤1：规划方案

管理移动设备的主要原因之一是保护组织的资源。 [使用 Microsoft Intune 的常用方法](https://docs.microsoft.com/intune/common-scenarios)列出了一些实际示例，包括保护 Office 365 电子邮件和数据。

Intune 为你提供了使用移动设备管理（MDM）或移动应用管理（MAM）管理对你的组织的访问权限的选项。 MDM 是用户在 Intune 中 "注册" 其设备。 注册后，它们就是受管理的设备，并且可以接收组织使用的任何策略、规则和设置。 例如，您可以安装特定应用程序，创建密码策略，安装 VPN 连接，等等。

拥有自己的个人设备的用户可能不希望注册其设备，也不能由 Intune 和你的策略进行管理。 但您仍需要保护您组织的资源和数据。 在这种情况下，您可以使用 MAM 保护您的应用程序。 例如，您可以使用一个 MAM 策略，该策略要求用户在设备上访问 SharePoint 时输入 PIN。

您还将确定如何管理个人或组织拥有的设备。 您可能需要以不同的方式处理设备，具体取决于设备的用途。 例如，您可能需要针对人力资源（HR）中的用户或 Sales 中的用户提供不同的计划。 [确定移动设备管理使用案例方案](https://docs.microsoft.com/intune/planning-guide-scenarios)可以开始，并在这些不同的方案中提供了一些指导。

## <a name="step-2-get-your-prerequisites"></a>步骤2：获取必备组件

接下来，根据你的要求和在上一步中创建的方案，获取你的必备组件。 [实施您的计划](https://docs.microsoft.com/intune/planning-guide-onboarding)将列出所有要求。 以下是 Intune 使用 Microsoft 365 时所需的重要项目：

- **Intune 订阅**： microsoft 365 附带提供了在[Azure 门户](https://portal.azure.com)中对 Microsoft Intune 的访问权限
- **Office 365 订阅**：包含在 Microsoft 365 中，用于 Office 应用程序，包括电子邮件
- **Azure Active Directory （AZURE AD） premium**：包含在 Microsoft 365 中，用于创建用户或安全组。 这些组将接收你创建的 Intune 策略，如强制密码长度以解锁设备。 可以使用在[第2阶段： Identity](https://docs.microsoft.com/microsoft-365/enterprise/identity-infrastructure)中创建的组。

可能还有一些其他要求，具体取决于您的组织的需求。 例如，如果你要管理 iOS 设备，你将需要 Apple MDM 推送证书。 如果使用的是本地 Exchange，则需要内部部署 Exchange 连接器。 当您执行这些步骤时，将概述这些附加要求。

## <a name="step-3-set-up-intune"></a>步骤3：设置 Intune

Intune 使用 Azure AD 中的许多功能，包括您的域、用户和组。 您还可以创建新的用户和新组来满足您的公司需求。 例如，您可以创建一个名为**iOS 设备**或**所有 HR 用户**的组。  利用[动态组](https://docs.microsoft.com/intune/groups-add)，您可以根据简单或高级规则构建用户或设备组。

此步骤侧重于设置 Intune 并让你可以管理设备。

1. **[确认设备是否受支持](https://docs.microsoft.com/intune/supported-devices-browsers)**。 确认 Intune 支持你的 iOS、macOS、Android、Galaxy 和 Windows 设备。 如果您的组织包括不受支持的设备，则这些策略不会应用于这些设备。

2. **[自定义您的域名](https://docs.microsoft.com/intune/custom-domain-name-configure)**。 默认情况下，在 Azure AD 中会自动创建一个名为 your-domain.onmicrosoft.com 的域，如 " **** "。 可以为您的组织自定义**onmicrosoft.com** 。 自定义时，它还会在连接到 Intune 和使用资源时向用户提供熟悉的域。

3. **[登录到 Intune](https://docs.microsoft.com/intune/account-sign-up)**。 登录后，可能会提示您输入您的组织的相关信息。 Intune 包含在 Microsoft 365 中，可以直接从[microsoft 365 管理中心](https://admin.microsoft.com)打开。 您还可以直接从[Azure 门户](https://portal.azure.com)打开 Intune。

4. **[选择您的移动设备管理配置](https://docs.microsoft.com/intune/mdm-authority-set)**。 第一次使用 Intune 时，必须启用设备管理。 Intune 可用作仅云服务、与 Intune 和 System Center Configuration Manager 的混合，或使用适用于 Office 365 的移动设备管理。 你可以选择最适合你的组织的设置。

5. **[添加用户](https://docs.microsoft.com/intune/users-add)** 并**[添加组](https://docs.microsoft.com/intune/groups-add)**。 

   您可以手动添加用户或使用混合标识和 Azure AD Connect 将本地用户帐户与 Intune 同步。 您还可以向特定用户提供管理员角色。 用户是必需的，除非您的设备是 "userless" 设备，例如 kiosk 设备。

   Azure AD 组用于简化在 Intune 中管理设备和用户的方式。 使用组可以执行许多不同的任务。 例如，您的组织希望在 Android 设备上需要特定的应用程序。 您可以创建 Android 设备组，并将此应用程序的策略部署到组。

    在 Intune 中，可以添加在[第2阶段](https://docs.microsoft.com/microsoft-365/enterprise/identity-infrastructure)中创建的用户或组： Identity

6. **[分配许可证](https://docs.microsoft.com/intune/licenses-assign)**。 对于要在 Intune 中注册的用户或设备，它们需要启用了 Intune 服务的 Microsoft 365 许可证才能访问 Intune 服务。 您分配了 microsoft Intune 服务在 Microsoft 365 管理中心或 PowerShell 中默认启用的 Microsoft 365 许可证。

## <a name="step-4-enroll-devices"></a>步骤4：注册设备

若要管理设备，必须在 Intune 中注册设备。 作为管理员，你将为你的用户和设备设置注册限制和策略。 每个设备平台（iOS、Android、macOS 和 Windows）都有多种选项。 你可以让你的用户自行注册。 或者，您可以自动执行注册，以便用户只需登录设备即可。

注册是使用 Intune 时的关键步骤。 [注册设备](https://docs.microsoft.com/intune/device-enrollment)列出了不同设备的步骤。

|||
|:-------|:-----|
|![Microsoft 云测试实验室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [测试实验室指南： iOS 和 Android 设备注册](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md) |
|||


## <a name="step-5-add-and-deploy-apps"></a>步骤5：添加和部署应用程序

移动设备上的应用程序通常是用户获得对公司资源的访问权限的最快方法。 

由于存在不同的设备（包括个人设备和公司设备），因此使用应用程序会面临一些挑战。 此外，还需要保护组织的资源及其数据，同时确保用户的工作效率。

Intune 可以管理应用程序，包括添加应用程序、将其分配给不同的用户或组，并查看其他关键的详细信息。 例如，您可以查看哪些应用程序安装失败、检查应用程序的版本等。

当用户获取移动设备时，第一项任务是访问组织的电子邮件和文档。 使用 Intune，可以使用设备上预先安装的电子邮件应用程序[创建和部署电子邮件设置](https://docs.microsoft.com/intune/email-settings-configure)。 

"[添加应用程序](https://docs.microsoft.com/intune/apps/apps-add)" 一文中列出了在您的组织内的设备上添加、部署、监视、配置和保护应用程序的步骤。

|||
|:-------|:-----|
|![Microsoft 云测试实验室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [测试实验室指南：设备合规性策略](mam-policies-for-your-microsoft-365-enterprise-dev-test-environment.md) |
|||

## <a name="step-6-turn-on-compliance-and-conditional-access"></a>步骤6：启用合规性和条件访问

在前面的步骤中，你将设置你的环境并启用 Intune。 现在，你已准备好使用合规性和条件访问创建一些策略。

合规性和条件访问对于管理设备非常重要。 创建[合规性策略](https://docs.microsoft.com/intune/device-compliance-get-started)以帮助保护组织的资源。 创建合规性策略时，您要定义设备必须具有的内容的标准或 "基准"。 例如，您可以选择一个可接受（或不可接受）的威胁级别、阻止越狱的设备、需要密码长度，等等。 如果这些设备不符合你的规则，这意味着它们不合规，则可以阻止对你的资源的访问。

此 "阻止" 引入了[条件访问](https://docs.microsoft.com/intune/conditional-access)。 如果设备被视为不兼容，则可以阻止对电子邮件、SharePoint 等的访问。

在[Azure 门户](https://portal.azure.com)中，你可以创建这些策略并将其应用到你的用户和设备的 Intune。 作为最佳实践，请先启动小型并使用暂存方法。 例如，创建阻止已越狱设备的 iOS 策略。 应用（在 Intune 中称为 "分配"）将策略应用于试点或测试组。 在初始测试后，向试点组添加更多用户。 使用暂存方法，可以从各种用户类型获取反馈。

请参阅[开始使用设备合规性策略](https://docs.microsoft.com/intune/device-compliance-get-started)并[了解条件访问和 Intune？](https://docs.microsoft.com/intune/conditional-access)可帮助你入门。

## <a name="step-7-apply-features-and-settings"></a>步骤7：应用功能和设置

这些功能和设置通常被视为 Intune 的 "酷" 部分，且功能非常强大。 在使用条件访问成功强制实施某些合规性策略后，即可创建**设备配置文件**。

在[Azure 门户](https://portal.azure.com)中，你可以基于设备平台-IOS、MacOS、Android 和 Windows 创建不同的配置文件。 例如，你能够：

- 在 Windows 10 设备上使用 Endpoint protection 启用不同的 BitLocker 选项，包括加密。
- 使用 iOS 设备上的 "受限制的应用" 功能创建可安装的已批准应用程序的列表。 或者，创建禁止的应用程序的列表。
- 使用展台设置可选择可在展台模式下运行的 Android 设备上使用的应用程序。
- 在运行 macOS 的设备上应用 Wlan 连接及其设置，包括安全类型。

[使用设备配置文件在设备上应用功能和设置](https://docs.microsoft.com/intune/device-profiles)是阅读有关配置文件的绝佳位置，请参阅 how to create a profile 等。

请记住，启动小型，并使用暂存方法。 将配置文件分配给试点或测试组。 然后，将配置文件分配给更多的试点组。

## <a name="step-8-get-to-know-the-other-features"></a>步骤8：了解其他功能

Intune 是一项功能强大的服务，包括许多功能。 以下是您可以使用 Intune 执行的一些其他任务：

- 管理 Windows[设备](https://docs.microsoft.com/intune/windows-update-for-business-configure) & [电脑](https://docs.microsoft.com/intune/keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune)和[iOS](https://docs.microsoft.com/intune/software-updates-ios)设备上的软件和更新
- 在 Windows 10 设备上启用[Microsoft Defender 高级威胁防护（ATP）](https://docs.microsoft.com/intune/advanced-threat-protection) ，并使用合规性和条件访问来保护对公司资源（如 SharePoint 或 Exchange Online）的访问
- 使用[寻找](https://docs.microsoft.com/intune/lookout-mobile-threat-defense-connector)、 [Symantec](https://docs.microsoft.com/intune/skycure-mobile-threat-defense-connector)和其他移动防御威胁合作伙伴
- 添加[合作伙伴证书颁发机构（CA）](https://docs.microsoft.com/intune/certificate-authority-add-scep-overview)以颁发和续订证书
- [向最终用户提供](https://docs.microsoft.com/intune/end-user-educate)有关公司门户应用程序、获取应用程序等的指导
- 监视[应用程序](https://docs.microsoft.com/intune/apps-monitor)和[设备合规性和配置文件](https://docs.microsoft.com/intune/compliance-policy-monitor)，以及使用审核日志的更多遥测。 您还可以连接到[Intune 数据仓库](https://docs.microsoft.com/intune/reports-nav-create-intune-reports)，并使用 Power BI 以获得更多报告需求。


## <a name="identity-and-device-access-recommendations"></a>标识和设备访问建议

Microsoft 提供了一组有关[身份和设备访问](microsoft-365-policies-configurations.md)的建议，以确保全体员工安全且高效地工作。 对于设备访问，请使用以下文章中的建议和设置以及此阶段中的步骤：

- [先决条件](identity-access-prerequisites.md)
- [常见标识和设备访问策略](identity-access-policies.md)

## <a name="how-microsoft-does-microsoft-365-enterprise"></a>Microsoft 如何对 Microsoft 365 企业版执行操作

了解 Microsoft IT 专家如何[使用 EMS 管理设备](https://www.microsoft.com/en-us/itshowcase/deploying-and-managing-microsoft-365#primaryR8)。

## <a name="how-contoso-did-microsoft-365-enterprise"></a>Contoso 是如何使用 Microsoft 365 企业版的

了解 Contoso Corporation （一个虚构但具有代表性的多国企业）如何使用 Microsoft 365 云服务[部署其移动设备管理基础结构](contoso-mdm.md)。

![Contoso Corporation](./media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a>后续步骤

[移动设备管理基础结构退出条件](mobility-infrastructure-exit-criteria.md)

