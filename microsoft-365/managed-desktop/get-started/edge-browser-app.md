---
title: 新版 Microsoft Edge
description: 说明如何部署和更新新的 Edge 浏览器
keywords: 浏览器， Microsoft 托管桌面， Microsoft 365， 服务， 文档
ms.service: m365-md
author: tiaraquan
ms.author: tiaraquan
manager: dougeby
audience: ITpro
ms.topic: article
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
ms.openlocfilehash: ed4ec04ebe6ae0aae3a55880190b720b140252a7
ms.sourcegitcommit: a6651b841f111ea2776cab88bf2c80f805fa8e09
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/13/2022
ms.locfileid: "62035470"
---
# <a name="new-microsoft-edge-app"></a>新Microsoft Edge应用

浏览器[Microsoft Edge浏览器](https://www.microsoft.com/edge)提供了世界一流的性能，在浏览时具有更多的隐私性、更高的工作效率和更多价值。 Microsoft 托管桌面提供环境中新边缘浏览器部署的公共预览版。

## <a name="initial-deployment"></a>初始部署

若要将 Microsoft 托管桌面 设备迁移到新的 Microsoft Edge 浏览器，请通过 Microsoft 托管桌面 门户提交 IT 支持票证。 当你提交票证时，我们会将 Edge Stable 渠道部署到测试组，然后每 24 小时在每个后续部署组中部署它。 若要暂停部署，请提出另一个请求操作保留的票证。

还可 [根据](/deployedge/microsoft-edge-channels#beta-channel) 请求在组织中进行代表性验证，使用 Beta 渠道。 Microsoft 托管桌面测试组和第一组部署应用程序，以便所有这些用户除了具有稳定渠道之外，还具有 Beta 渠道。 对于需要访问 Beta 渠道的任何其他用户，请将其添加到"新式工作区 **- Edge Beta** 用户"组，并让他们从 公司门户

## <a name="updates-to-microsoft-edge"></a>更新Microsoft Edge

Microsoft 托管桌面部署稳定[渠道](/deployedge/microsoft-edge-channels#stable-channel)Microsoft Edge，大约每六周自动更新一次。 稳定渠道上的更新由 Microsoft Edge[](/deployedge/microsoft-edge-update-progressive-rollout)产品组逐步推出，以确保为客户提供最佳体验。 

Beta [渠道](/deployedge/microsoft-edge-channels#beta-channel) 将部署到"测试"和"第一组"中的设备，以在组织中进行代表性验证。 此频道完全受支持，大约每六周自动更新一次新功能。

若要确保正确Microsoft Edge，请不要修改更新Microsoft Edge[策略](/deployedge/microsoft-edge-update-policies)。



## <a name="settings-managed-by-microsoft-managed-desktop"></a>设置由 Microsoft 托管桌面

Microsoft 托管桌面创建了一组默认策略，Microsoft Edge保护浏览器的安全。 默认浏览器设置如下所示：

### <a name="microsoft-edge-extensions"></a>Microsoft Edge扩展

在设备上Microsoft Edge安全Microsoft 托管桌面设置两个策略来禁用所有 Chrome 扩展和安全用户。 若要在环境中启用和部署扩展，请参阅设置管理。 

#### <a name="extension-installation-blocklist"></a>扩展安装阻止列表
**默认值：** 全部

Microsoft 托管桌面此策略以防止 Chrome 扩展安装在托管终结点上。 与扩展模型相关的已知风险Chromium包括数据丢失保护、隐私和其他可能损害设备的风险。 

#### <a name="allow-user-level-native-messaging-hosts-installed-without-admin-permissions"></a>允许在没有管理员权限的情况下安装 (级本机消息传递) 

**默认值：** 已禁用

通过禁用此策略，Microsoft Edge将仅使用安装在系统级别的本机消息传递主机。 本机消息传递主机是 Chrome 扩展的一部分，允许浏览器与用户终结点的其他部分进行交互，从而产生各种安全问题。  

### <a name="secure-sockets-layer-tlsssl"></a>TLS/SSL (安全套接字层) 

#### <a name="minimum-tls-version"></a>最低 TLS 版本

**默认值：** 支持的最低 TLS 1.2

如果要使用安全性低的 TLS 1.1，可以提出这样做的请求。

#### <a name="allows-users-to-proceed-from-the-ssl-warning-page"></a>允许用户从 SSL 警告页继续

**默认值：** 已禁用

建议不要启用此设置，因为它允许用户访问具有 TSL 错误的网站。

### <a name="microsoft-defender-smartscreen"></a>Microsoft Defender SmartScreen

#### <a name="configure-windows-defender-smartscreen"></a>配置Windows Defender SmartScreen

**默认值：** 已启用

默认情况下启用以帮助保护用户。

#### <a name="windows-defender-smartscreen-prompts-for-sites"></a>Windows Defender SmartScreen 网站提示

**默认值：** 已启用

建议不要禁用此设置，因为这将允许用户忽略警告并继续访问潜在恶意网站。

#### <a name="prevent-bypassing-of-windows-defender-smartscreen-warnings-about-downloads"></a>阻止绕过有关Windows Defender的 SmartScreen 警告

**默认值：** 已启用

建议不要禁用此设置，因为这将允许用户忽略警告和完成未经验证的下载。

### <a name="adobe-flash"></a>Adobe Flash

#### <a name="default-adobe-flash-setting"></a>默认 Adobe Flash 设置

**默认值：** 已禁用

我们不建议使用 Flash，因为存在相关的安全风险。 如果仍有依赖于 Flash 的进程，请设置 **[PluginsAllowedForUrls](/deployedge/microsoft-edge-policies#pluginsallowedforurls)** 策略，为需要 Flash 的网站启用 Flash。 如果无法维护允许使用 Flash 的站点列表，请提交更改请求以将值更改为"单击播放"，这将允许用户选择何时适合运行 Flash。 

### <a name="password-manager"></a>密码管理器

#### <a name="enable-saving-passwords-to-the-password-manager"></a>允许将密码保存至密码管理器

**默认值：** 已禁用

默认情况下，密码管理器处于禁用状态。 如果你希望启用此功能，请提出支持请求，我们的服务工程师可以在你的环境中启用该设置。

### <a name="internet-explorer-mode-in-microsoft-edge"></a>Internet Explorer模式Microsoft Edge

Microsoft Edge 上的 IE 模式使你能够轻松地在单一浏览器中使用组织所需的所有网站。 它使用与 Chromium 呈现引擎兼容的网站的集成 Chromium 引擎，并且对于不依赖于 IE 功能或依赖 IE 功能的网站，它使用 Internet Explorer 11 (IE11) 中的 Trident MSHTML 引擎。 [了解更多](/DeployEdge/edge-ie-mode)

Microsoft 托管桌面为Internet Explorer启用设备模式。

#### <a name="internet-explorer-mode-integration"></a>Internet Explorer模式集成

**默认值：** Internet Explorer模式

默认情况下，设备设置为使用Internet Explorer模式，但你可以将其设置为改为在独立 Internet Explorer 11 窗口中打开网站。 若要更改此行为，请提出支持请求。

#### <a name="add-sites-to-the-enterprise-mode-site-list"></a>将站点添加到Enterprise站点列表

若要在网站模式下Internet Explorer，必须将它们包括在"网站Enterprise[列表中](/DeployEdge/edge-ie-mode-sitelist)。 维护和部署网站Enterprise由你负责。 有关详细信息，请参阅使用[配置模式站点Enterprise配置](/DeployEdge/edge-ie-mode-policies#configure-using-the-configure-the-enterprise-mode-site-list-policy)

### <a name="other-settings"></a>其他设置

#### <a name="enable-site-isolation-for-every-site"></a>针对每个网站启用网站隔离

**默认值：** 已启用

启用此策略后，用户不能选择退出每个网站在其自己的进程中运行的默认行为。

#### <a name="supported-authentication-schemes"></a>支持的身份验证方案

**默认值：** NTLM、Negotiate

Microsoft 托管桌面基本身份验证或摘要式身份验证方案。

#### <a name="automatically-import-another-browsers-data-and-settings-at-first-run"></a>首次运行时自动导入其他浏览器的数据和设置

**默认值：** 自动从默认浏览器导入所有受支持的数据类型和设置 

应用此策略后，首次运行体验将跳过导入部分，从而最大限度地减少用户交互。 来自旧版浏览器的浏览器数据Microsoft Edge在首次运行时始终以静默方式迁移，无论此设置如何。 


## <a name="settings-you-manage"></a>设置管理

可以使用管理模板Microsoft Edge部署之前未介绍的任何Microsoft Intune。 有关详细信息，请参阅使用 Microsoft Edge[配置策略Microsoft Intune。](/deployedge/configure-edge-with-intune) 如果要评估当前未包含在 Intune Microsoft Edge 管理模板中的策略，可以在 Intune 中为 Windows 10 设备使用自定义设置。

### <a name="enabling-specific-chrome-extensions"></a>启用特定 Chrome 扩展

管理模板提供了一个设置，用于部署特定 Chrome Microsoft Intune。 可以在计算机配置> Microsoft Edge >扩展>允许安装特定 **扩展）中查找。**

### <a name="install-extensions-silently"></a>以静默方式安装扩展

您还可以使用管理模板来设置Microsoft Edge安装扩展而不通知用户。 可以在计算机配置> Microsoft Edge >扩展>控制以静默方式安装哪些 **扩展**。

### <a name="microsoft-edge-update-policies"></a>Microsoft Edge更新策略
若要确保正确Microsoft Edge，请不要修改更新Microsoft Edge[策略](/deployedge/microsoft-edge-update-policies)。

### <a name="other-common-enterprise-policies"></a>其他常见企业策略

Microsoft Edge提供了许多其他策略。 这些是一些更常见的方法：
 
- [在站点列表Enterprise IE 模式下配置站点](/deployedge/edge-ie-mode-sitelist)
- [配置启动、主页和新选项卡页设置](/deployedge/microsoft-edge-policies#startup-home-page-and-new-tab-page)
- [配置"浏览"游戏设置](/deployedge/microsoft-edge-policies#allowsurfgame)
- [配置代理服务器设置](/deployedge/microsoft-edge-policies#proxy-server)
