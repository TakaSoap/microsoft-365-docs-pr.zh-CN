---
title: 新建 Microsoft Edge 应用
description: ''
keywords: 浏览器、Microsoft 托管桌面、Microsoft 365、服务、文档
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 0602d7c6afef6190578268c78994b43ac60d0d2f
ms.sourcegitcommit: 3119b2246001ba06af8264508785352dfb894166
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/19/2020
ms.locfileid: "44820673"
---
# <a name="new-microsoft-edge-app"></a>新建 Microsoft Edge 应用

新的[Microsoft Edge 浏览器](https://www.microsoft.com/edge)在浏览过程中提供了世界一流的性能、更高的隐私、更高的工作效率和更多价值。 Microsoft 托管桌面提供了在您的环境中部署新边缘浏览器的公共预览。

## <a name="initial-deployment"></a>初始部署

若要将 Microsoft 托管桌面设备迁移到新的 Microsoft Edge 浏览器，请通过 Microsoft 托管桌面门户文件提供 IT 支持票证。 在您对票证进行存档时，我们会将边缘稳定通道部署到测试组，然后在每个后续的部署组中每隔24小时部署它。 若要暂停部署，请文件另一个票证请求操作保留。

## <a name="updates-to-microsoft-edge"></a>Microsoft Edge 的更新

Microsoft 托管桌面部署 Microsoft Edge 的[稳定通道](https://docs.microsoft.com/deployedge/microsoft-edge-channels#stable-channel)，每六周自动更新一次。 对稳定通道的更新由 Microsoft Edge 产品组[逐步](https://docs.microsoft.com/deployedge/microsoft-edge-update-progressive-rollout)进行，以确保为客户提供最佳体验。 Microsoft Edge Beta 通道目前不可用。

若要确保 Microsoft Edge 正确更新，请不要修改 Microsoft Edge[更新策略](https://docs.microsoft.com/deployedge/microsoft-edge-update-policies)。

## <a name="settings-managed-by-microsoft-managed-desktop"></a>Microsoft 托管桌面管理的设置

Microsoft 托管桌面已为 Microsoft Edge 创建了一组默认的策略，以保护浏览器的安全。 默认浏览器设置如下所示：

### <a name="microsoft-edge-extensions"></a>Microsoft Edge 扩展

Microsoft 托管桌面设备上 Microsoft Edge 的安全基准设置了两个策略，以禁用所有 Chrome 扩展和安全最终用户。 若要在环境中启用和部署扩展，请参阅管理的设置。 

#### <a name="extension-installation-blocklist"></a>扩展安装阻止列表
**默认值：** 各种

Microsoft 托管桌面设置此策略，以防止在托管终结点上安装 Chrome 扩展。 存在具有 Chromium 扩展模型的已知 risksassociated，其中包括数据丢失保护、隐私和可能危害设备的其他风险。 

#### <a name="allow-user-level-native-messaging-hosts-installed-without-admin-permissions"></a>允许用户级别的本机邮件主机（无需管理员权限即可安装）

**默认值：** 禁用

通过禁用此策略，Microsoft Edge 将仅使用安装在系统级别上的本机邮件主机。 本机邮件主机是 Chrome 扩展的一部分，它允许浏览器与用户终结点的其他部分进行交互，从而产生各种安全问题。  

### <a name="secure-sockets-layer-ssl"></a>安全套接字层 (SSL)

#### <a name="minimum-ssl-version"></a>最低 SSL 版本

**默认值：** 支持的最低 TLS 1。2

如果要使用安全性较低的 TLS 1.1，可以请求这样做。

#### <a name="allows-users-to-proceed-from-the-ssl-warning-page"></a>允许用户从 "SSL 警告" 页继续

**默认值：** 禁用

建议您不要启用此设置，因为它允许用户访问具有 SSL 错误的网站。

### <a name="microsoft-defender-smart-screen"></a>Microsoft Defender 智能屏幕

#### <a name="configure-microsoft-defender-smartscreen"></a>配置 Microsoft Defender SmartScreen

**默认值：** 了

默认情况下启用以帮助保护最终用户。

#### <a name="microsoft-defender-smartscreen-prompts-for-sites"></a>Microsoft Defender SmartScreen 网站提示

**默认值：** 了

建议您不要禁用此设置，因为这将允许用户忽略警告，并继续执行潜在的恶意网站。

#### <a name="prevent-bypassing-of-microsoft-defender-smartscreen-warnings-about-downloads"></a>阻止绕过关于下载的 Microsoft Defender SmartScreen 警告

**默认值：** 了

建议不要禁用此设置，因为这将允许用户忽略警告和完成未验证的下载。

### <a name="adobe-flash"></a>Adobe Flash

#### <a name="default-adobe-flash-setting"></a>默认 Adobe Flash 设置

**默认值：** 禁用

由于相关的安全风险，建议不要使用 Flash。 如果仍有依赖于 Flash 的进程，请设置**[PluginsAllowedForUrls](https://docs.microsoft.com/deployedge/microsoft-edge-policies#pluginsallowedforurls)** 策略以为需要它的网站启用 Flash。 如果无法维护允许的网站列表以使用 Flash，请将更改请求更改为**单击以播放**，这样用户就可以选择何时运行 flash。

### <a name="password-manager"></a>密码管理器

#### <a name="enable-saving-passwords-to-the-password-manager"></a>启用将密码保存到密码管理器

**默认值：** 禁用

建议不要让最终用户在其设备上保存密码。

### <a name="other-settings"></a>其他设置

#### <a name="enable-site-isolation-for-every-site"></a>为每个网站启用网站隔离

**默认值：** 了

如果启用此策略，则用户将无法退出每个网站在其自己的进程中运行的默认行为。

#### <a name="supported-authentication-schemes"></a>支持的身份验证方案

**默认值：** NTLM、协商

Microsoft 托管桌面不支持基本或摘要式身份验证方案。

#### <a name="automatically-import-another-browsers-data-and-settings-at-first-run"></a>首次运行时自动导入另一个浏览器的数据和设置

**默认值：** 从默认浏览器自动导入所有受支持的数据类型和设置 

应用此策略后，首次运行体验将跳过 "导入" 部分，最大限度地减少用户交互。 Microsoft Edge 早期版本中的浏览器数据将始终在首次运行时无提示地迁移，无论此设置如何。 


## <a name="settings-you-manage"></a>您管理的设置

您可以使用 Microsoft Intune 中的 "管理模板" 配置文件，部署先前未介绍的任何 Microsoft 边缘设置。 有关详细信息，请参阅[Configure Microsoft Edge policy settings With Microsoft Intune](https://docs.microsoft.com/deployedge/configure-edge-with-intune)。 如果要评估当前未包含在 Intune 中的 Microsoft Edge 管理模板中的策略，可以在 Intune 中使用 Windows 10 设备的自定义设置。

### <a name="enabling-specific-chrome-extensions"></a>启用特定的部件版式扩展

管理模板提供了使用 Microsoft Intune 部署特定 Chrome 扩展的设置。 您可以在 "**计算机配置 > Microsoft Edge > 扩展中找到它，> 允许安装特定的扩展**。

### <a name="install-extensions-silently"></a>自动安装扩展

您还可以使用管理模板设置 Microsoft Edge 以安装分机，而不向用户发出警告。 您可以在 "**计算机配置" > Microsoft Edge > 扩展中找到它，> 控制自动安装哪些扩展**。

### <a name="other-common-enterprise-policies"></a>其他常见的企业策略

Microsoft Edge 提供了很多其他策略。 以下是一些比较常见的项：
 
- [在企业网站列表和 IE 模式下配置网站](https://docs.microsoft.com/deployedge/edge-ie-mode-sitelist)
- [配置 "启动"、"主页" 和 "新建选项卡页" 设置](https://docs.microsoft.com/deployedge/microsoft-edge-policies#startup-home-page-and-new-tab-page)
- [配置 "冲浪游戏" 设置](https://docs.microsoft.com/deployedge/microsoft-edge-policies#allowsurfgame)
- [配置代理服务器设置](https://docs.microsoft.com/deployedge/microsoft-edge-policies#proxy-server)

