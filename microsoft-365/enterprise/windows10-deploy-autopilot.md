---
title: 使用 Windows Autopilot 为新设备部署 Windows 10 企业版
description: 提供有关使用 Windows Autopilot 配置和部署 Windows 10 企业版的指南。
keywords: Microsoft 365，Microsoft 365 Enterprise，Microsoft 365 文档，Windows 10 企业版，部署，Windows Autopilot
author: greg-lindsay
localization_priority: Normal
ms.collection: M365-modern-desktop
audience: microsoft-business
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.date: 08/30/2018
ms.author: greglin
ms.openlocfilehash: 0d85bc51ac3f224b396281ff4e8414541097ed22
ms.sourcegitcommit: 2aeafb631aaabc53eea0a8029711eb891e48d249
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/28/2019
ms.locfileid: "37746538"
---
# <a name="step-3-deploy-windows-10-enterprise-for-new-devices-with-windows-autopilot"></a>步骤3：使用 Windows Autopilot 为新设备部署 Windows 10 企业版

*本文适用于 Microsoft 365 企业版的 E3 和 E5 版本*

![阶段 3：Windows 10 企业版](./media/deploy-foundation-infrastructure/win10enterprise_icon-small.png)

如果你有新的 Windows 10 电脑，则可以使用 Windows Autopilot 为你的组织自定义现成体验（OOBE），并部署具有已配置的应用程序和设置的新系统。 没有要部署的映像，没有要注入的驱动程序，没有要管理的基础结构。 用户可以独立完成部署过程，无需咨询其 IT 管理员。

您可以设置和预配置新的 Windows 10 设备，让它们准备好使用 Windows Autopilot 进行高效使用。 若要了解有关 Windows Autopilot 的详细信息（包括福利和 Windows Autopilot 方案），请参阅[Windows Autopilot 概述](https://docs.microsoft.com/windows/deployment/windows-Autopilot/windows-10-Autopilot)。 准备就绪后，请按照以下部件开始设置新设备。

## <a name="the-windows-autopilot-deployment-process-poster"></a>Windows Autopilot 部署过程海报

Windows Autopilot 海报是纵向模式（11x17）中的两页。 单击下面的图像以在浏览器中查看 PDF。 

[![使用 Autopilot 海报部署 Windows 10](./media/windows10-deploy-autopilot/windows10-autopilot-flowchart.png)](https://opdhsblobprod04.blob.core.windows.net/contents/d0d41f25ce48460387a79ace64acad6b/d00f8fc01db0b512e4953663c8331588?sv=2015-04-05&sr=b&sig=bfzlEl8SrShCQyj8E2QUf6LJfxlKre6ortODE4qHjrc%3D&st=2019-10-24T22%3A18%3A33Z&se=2019-10-25T22%3A28%3A33Z&sp=r)

您还可以下载[PDF](https://github.com/MicrosoftDocs/windows-itpro-docs/raw/public/windows/deployment/media/Windows10AutopilotFlowchart.pdf)或[Visio](https://github.com/MicrosoftDocs/windows-itpro-docs/raw/public/windows/deployment/media/Windows10Autopilotflowchart.vsdx)格式的此海报。

## <a name="part-1-start-windows-autopilot-deployment"></a>第1部分：启动 Windows Autopilot 部署
请参阅[Windows Autopilot 概述](https://docs.microsoft.com/windows/deployment/windows-Autopilot/windows-10-Autopilot)to：

1. 了解并完成 Windows Autopilot 部署的先决条件。 先决条件包括：
    - **设备注册和 OOBE 自定义**

        若要注册设备，您需要获取其硬件 ID 并进行注册。 我们正在与各种硬件供应商合作，让他们为你提供所需的信息，或代表你上传。 您还可以选择使用生成包含设备的硬件 ID 的 .csv 文件的 PowerShell 脚本来捕获此信息。

        注册设备后，可以配置 OOBE 自定义选项，包括跳过隐私设置和 EULA。

    - **针对 OOBE 的公司品牌塑造**

        这使您可以在设备 OOBE 期间添加品牌显示。

    - **Microsoft Intune 中的 MDM 自动注册**
        
        在将设备连接到 Azure AD 时，自动注册允许用户在 Intune 中为设备管理注册其 Windows 10 设备。 若要注册，用户需要将其工作帐户添加到其个人拥有的设备，或将公司拥有的设备加入 Azure AD。 在后台，还会为该设备注册使用 Intune 进行管理。

    - **Windows Autopilot 所使用的云服务的网络连接**

        Windows Autopilot 部署程序使用大量云服务将设备恢复到生产状态，并且必须可从注册为 Windows Autopilot 设备的设备访问这些服务。 

    - **设备必须已预安装 Windows 10 版本 1703 或更高版本**

2. 了解并为您的组织选择 Windows Autopilot 部署计划。 您可以从以下部署程序中进行选择：
    - **适用于企业的 Microsoft Store**
    - **Microsoft Intune**
    - **合作伙伴中心**

## <a name="part-2-set-up-a-windows-10-device-for-microsoft-365"></a>第2部分：为 Microsoft 365 设置 Windows 10 设备
在为 Microsoft 365 用户设置 Windows 设备之前，请确保所有 Windows 设备运行的是 Windows 10、版本1703（创意者更新）或更高版本。

在组织中的所有 Windows 设备都已升级到 Windows 10 创意者更新或已在运行 Windows 10 创意者更新之后，您可以将这些设备加入到组织的 Azure Active Directory 中。

### <a name="set-up-a-brand-new-or-newly-upgraded-windows-10-device"></a>设置全新的或新升级的 Windows 10 设备
按照以下步骤操作，在运行 Windows 10 创意者更新（或更高版本）的全新设备上或在升级到 Windows 10 创意者更新（或更高版本）但尚未通过全新安装程序更新的设备上使用 Windows 10 OOBE 设置设备。

1. 如果没有配置无线网络，请确保通过有线或以太网连接将设备连接到 internet。
2. 请浏览 Windows 设备设置体验。 在新的或重置设备上，安装程序体验将以 "开始" 的 "地区" 开头 **。此权限正确吗？** 闪屏.
3. 完成 Windows 10 设备设置，直到显示" **设置方式**"页面。 在此处，为组织选择 "**设置**"。
4. 使用 Microsoft 365 用户的帐户和密码登录。 根据用户密码设置的不同，可能会提示您更新密码。 
5. 完成 Windows 10 设备设置。

完成后，设备将连接到您的组织的 Azure AD。

### <a name="set-up-a-device-that-has-already-completed-out-of-box-setup"></a>设置已完成的设备的开箱即用安装程序
如果你的设备具有 Windows 10 创意者更新（或更高版本），并且已通过 "开箱即用" 安装程序，请执行以下步骤。

1. 在运行 Windows 10 版本1703（创意者更新）的用户的 Windows 电脑上，选择**Windows**徽标，然后选择 "**设置**" 图标。
2. 2.在" **设置**"中，转到" **帐户**"。
3. 在 "**你的信息**" 页上，选择 "**访问工作或学校** > **连接**"。
4. 在 "**设置工作或学校帐户**" 对话框中的 "**替代操作**" 下，选择 "将**此设备加入 Azure Active Directory**"。
5. 在 "**让你登录**" 页面上，输入你的工作或学校帐户，然后选择 "**下一步**"。
6. 在 "**输入密码**" 页面上，输入您的密码，然后选择 "**登录**"。
7. 在 "**确保这是你的组织**" 页上，验证信息是否正确，然后选择 "**加入**"。
8. 在 "**全是" 设置！** 页面上，选择 "**完成**"。

完成后，用户将连接到您的组织的 Azure AD。

### <a name="verify-the-device-is-connected-to-azure-ad"></a>验证设备是否连接到 Azure AD
按照以下步骤操作，以使用 Azure AD 验证设备的同步状态，然后开始在设备上使用 Microsoft 365 帐户。 

1. 打开 "**设置**"。
2. 在 "**访问工作或学校**" 页面上，选择 "**已连接到<organization name> ** " 区域以显示按钮**信息**并**断开连接**。
3. 选择 "**信息**" 以获取你的同步状态。
4. 在 "**同步状态**" 页上，选择 "**同步**" 以获取电脑上的最新移动设备管理策略。
5. 若要开始使用 Microsoft 365 帐户，请转到 Windows "**开始**" 按钮，右键单击您当前的帐户图片，然后选择 "**切换**帐户"。
6. 使用组织电子邮件和密码进行登录。

如果在企业环境中使用 Windows 10 时遇到问题，可以参阅[主要 Microsoft 支持解决方案，了解最常见的问题](https://docs.microsoft.com/windows/client-management/windows-10-support-solutions)。 这些资源包括知识库文章、更新和库文章。

作为临时检查点，请查看对应于此步骤的[退出条件](windows10-exit-criteria.md#crit-windows10-step3)。

## <a name="next-step"></a>后续步骤

|||
|:-------|:-----|
|![第 4 步](./media/stepnumbers/Step4.png)| [监视设备运行状况和合规性](windows10-enable-windows-analytics.md) |
