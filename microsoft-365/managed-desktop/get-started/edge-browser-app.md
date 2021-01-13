---
title: 新版 Microsoft Edge
description: 介绍如何部署和更新新的边缘浏览器
keywords: browser， Microsoft Managed Desktop， Microsoft 365， 服务， 文档
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
manager: laurawi
audience: ITpro
ms.topic: article
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 42ff665e8ba9c369e29eeeafd27affff04b40966
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/13/2021
ms.locfileid: "49841335"
---
# <a name="new-microsoft-edge-app"></a>新的 Microsoft Edge 应用

新的 [Microsoft Edge](https://www.microsoft.com/edge) 浏览器提供了世界一流的性能，在浏览时具有更多隐私、更高的工作效率和更多价值。 Microsoft 托管桌面提供环境中新边缘浏览器部署的公共预览版。

## <a name="initial-deployment"></a>初始部署

若要将 Microsoft 托管桌面设备迁移到新的 Microsoft Edge 浏览器，请通过 Microsoft 托管桌面门户提交 IT 支持票证。 当你提交票证时，我们会将边缘稳定渠道部署到测试组，然后每 24 小时在每个后续部署组中部署它。 若要暂停部署，请提出另一个请求操作保留的票证。

如果 [请求在](https://docs.microsoft.com/deployedge/microsoft-edge-channels#beta-channel) 组织中进行验证，也可使用 Beta 渠道。 Microsoft 托管桌面将按测试和第一组的要求部署应用程序，以便所有这些用户除了具有稳定渠道之外，还具有 Beta 渠道。 对于需要访问 Beta 渠道的其他用户，请将其添加到新式 **工作区 - Edge Beta Users** 组，并让他们从公司门户安装它

## <a name="updates-to-microsoft-edge"></a>Microsoft Edge 更新

Microsoft 托管桌面部署 Microsoft Edge [的 Stable](https://docs.microsoft.com/deployedge/microsoft-edge-channels#stable-channel) 渠道，大约每六周自动更新一次。 稳定渠道上的更新由 Microsoft [](https://docs.microsoft.com/deployedge/microsoft-edge-update-progressive-rollout) Edge 产品组逐步推出，以确保为客户提供最佳体验。 

Beta [渠道](https://docs.microsoft.com/deployedge/microsoft-edge-channels#beta-channel) 将部署到"测试"和"第一组"中的设备，以在组织中进行代表性验证。 此频道完全受支持，大约每六周自动更新一次新功能。

若要确保 Microsoft Edge 正确更新，请不要修改 Microsoft Edge [更新策略](https://docs.microsoft.com/deployedge/microsoft-edge-update-policies)。



## <a name="settings-managed-by-microsoft-managed-desktop"></a>由 Microsoft 托管桌面管理的设置

Microsoft 托管桌面为 Microsoft Edge 创建了一组默认策略，用于保护浏览器安全。 默认浏览器设置如下所示：

### <a name="microsoft-edge-extensions"></a>Microsoft Edge 扩展

Microsoft 托管桌面版设备上 Microsoft Edge 的安全基线设置两个策略，以禁用所有 Chrome 扩展和安全用户。 若要在环境中启用和部署扩展，请参阅你管理的"设置"。 

#### <a name="extension-installation-blocklist"></a>扩展安装阻止列表
**默认值：** 全部

Microsoft 托管桌面设置此策略，以防止在托管终结点上安装 Chrome 扩展。 存在与 Chromium 扩展模型相关的已知风险，包括数据丢失保护、隐私和其他可能会损害设备的风险。 

#### <a name="allow-user-level-native-messaging-hosts-installed-without-admin-permissions"></a>允许在没有管理员权限的情况下安装 (级本机消息传递) 

**默认值：** 已禁用

通过禁用此策略，Microsoft Edge 将仅使用安装在系统级别的本机邮件主机。 本机消息传递主机是 Chrome 扩展的一部分，允许浏览器与用户终结点的其他部分进行交互，从而产生各种安全问题。  

### <a name="secure-sockets-layer-tlsssl"></a>TLS/SSL (安全套接字层) 

#### <a name="minimum-tls-version"></a>最低 TLS 版本

**默认值：** 支持的最低 TLS 1.2

如果要使用安全性不太低的 TLS 1.1，可以提出这样做的请求。

#### <a name="allows-users-to-proceed-from-the-ssl-warning-page"></a>允许用户从 SSL 警告页继续

**默认值：** 已禁用

建议不要启用此设置，因为它允许用户访问具有 TSL 错误的网站。

### <a name="microsoft-defender-smartscreen"></a>Microsoft Defender SmartScreen

#### <a name="configure-windows-defender-smartscreen"></a>配置 Windows Defender SmartScreen

**默认值：** 已启用

默认情况下启用以帮助保护用户。

#### <a name="windows-defender-smartscreen-prompts-for-sites"></a>Windows Defender站点显示 SmartScreen 提示

**默认值：** 已启用

建议不要禁用此设置，因为这样将允许用户忽略警告，并继续访问潜在恶意站点。

#### <a name="prevent-bypassing-of-windows-defender-smartscreen-warnings-about-downloads"></a>阻止绕过有关Windows Defender的 SmartScreen 警告

**默认值：** 已启用

建议不要禁用此设置，因为这将允许用户忽略警告并完成未经验证的下载。

### <a name="adobe-flash"></a>Adobe Flash

#### <a name="default-adobe-flash-setting"></a>默认 Adobe Flash 设置

**默认值：** 已禁用

我们不建议使用 Flash，因为存在相关的安全风险。 如果仍有依赖于 Flash 的进程，请设置 **[PluginsAllowedForUrls](https://docs.microsoft.com/deployedge/microsoft-edge-policies#pluginsallowedforurls)** 策略，为需要 Flash 的网站启用 Flash。 如果无法维护允许的网站列表以使用 Flash，请提交更改请求以将值更改为"单击播放"，从而允许用户选择何时适合运行 Flash。

### <a name="password-manager"></a>密码管理器

#### <a name="enable-saving-passwords-to-the-password-manager"></a>允许将密码保存至密码管理器

**默认值：** 已禁用

建议不要允许用户在设备上保存密码。

### <a name="internet-explorer-mode-in-microsoft-edge"></a>Internet Explorer Microsoft Edge 中的模式
Microsoft Edge 上的 IE 模式使你能够轻松地在单一浏览器中使用组织所需的所有网站。 它使用与 Chromium 呈现引擎兼容的网站的集成 Chromium 引擎，并使用 Internet Explorer 11 (IE11) 中的 Trident MSHTML 引擎来访问不依赖于 IE 功能或依赖 IE 功能的网站。 [了解更多] (https://docs.microsoft.com/DeployEdge/edge-ie-mode) 

默认情况下，Microsoft 托管Internet Explorer为设备启用支持模式 

#### <a name="internet-explorer-mode-integration"></a>Internet Explorer模式集成
**默认值：** Internet Explorer模式

默认情况下，设备设置为使用Internet Explorer模式，但你可以将其设置为改为在独立 Internet Explorer 11 窗口中打开网站。 若要更改此行为，请提交支持请求。

#### <a name="add-sites-to-the-enterprise-mode-site-list"></a>将站点添加到企业模式站点列表
若要使站点在Internet Explorer模式打开，必须在企业站点列表中 [包括这些站点](https://docs.microsoft.com/DeployEdge/edge-ie-mode-sitelist)。 维护和部署企业站点列表由你负责。 有关详细信息，请参阅使用 [配置企业模式站点列表策略进行配置](https://docs.microsoft.com/DeployEdge/edge-ie-mode-policies#configure-using-the-configure-the-enterprise-mode-site-list-policy)

### <a name="other-settings"></a>其他设置

#### <a name="enable-site-isolation-for-every-site"></a>为每个网站启用网站隔离

**默认值：** 已启用

启用此策略后，用户不能选择退出每个网站在其自己的进程中运行的默认行为。

#### <a name="supported-authentication-schemes"></a>支持的身份验证方案

**默认值：** NTLM，协商

Microsoft 托管桌面不支持基本或摘要式身份验证方案。

#### <a name="automatically-import-another-browsers-data-and-settings-at-first-run"></a>首次运行时自动导入其他浏览器的数据和设置

**默认值：** 自动从默认浏览器导入所有受支持的数据类型和设置 

应用此策略后，首次运行体验将跳过导入部分，从而最大程度地减少用户交互。 来自较早版本的 Microsoft Edge 的浏览器数据将始终在首次运行时以静默方式迁移，无论此设置如何。 


## <a name="settings-you-manage"></a>你管理的设置

可以使用 Microsoft Intune 中的管理模板配置文件部署之前未介绍的任何 Microsoft Edge 设置。 有关详细信息，请参阅使用 Microsoft Intune 配置 [Microsoft Edge 策略设置](https://docs.microsoft.com/deployedge/configure-edge-with-intune)。 如果你想要评估当前未包含在 Intune 中的 Microsoft Edge 管理模板中的策略，可以在 Intune 中为 Windows 10 设备使用自定义设置。

### <a name="enabling-specific-chrome-extensions"></a>启用特定 Chrome 扩展

管理模板提供了使用 Microsoft Intune 部署特定 Chrome 扩展的设置。 可以在 Microsoft Edge > Extensions > 的计算机配置 **>"允许安装特定扩展"。**

### <a name="install-extensions-silently"></a>静默安装扩展

您还可以使用管理模板将 Microsoft Edge 设置为安装扩展，而不向用户发出警报。 可以在 Microsoft Edge > 扩展>的计算机配置>控制以静默方式安装的 **扩展**。

### <a name="microsoft-edge-update-policies"></a>Microsoft Edge 更新策略
若要确保 Microsoft Edge 正确更新，请不要修改 Microsoft Edge [更新策略](https://docs.microsoft.com/deployedge/microsoft-edge-update-policies)。

### <a name="other-common-enterprise-policies"></a>其他常见企业策略

Microsoft Edge 提供了许多其他策略。 这些是一些更常见的方法：
 
- [在企业站点列表和 IE 模式下配置站点](https://docs.microsoft.com/deployedge/edge-ie-mode-sitelist)
- [配置启动、主页和新选项卡页设置](https://docs.microsoft.com/deployedge/microsoft-edge-policies#startup-home-page-and-new-tab-page)
- [配置"浏览"游戏设置](https://docs.microsoft.com/deployedge/microsoft-edge-policies#allowsurfgame)
- [配置代理服务器设置](https://docs.microsoft.com/deployedge/microsoft-edge-policies#proxy-server)

