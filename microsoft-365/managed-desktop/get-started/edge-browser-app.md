---
title: Microsoft Edge
description: 介绍如何部署Microsoft Edge浏览器
keywords: 浏览器， Microsoft 托管桌面， Microsoft 365， 服务， 文档
ms.service: m365-md
author: tiaraquan
ms.author: tiaraquan
manager: dougeby
audience: ITpro
ms.topic: article
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
ms.openlocfilehash: aab02ec260f0131ab32d28834152f50b84abce21
ms.sourcegitcommit: d4797cfc15c732f1a7ef21e4f944e672a7170f9a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/08/2022
ms.locfileid: "62444601"
---
# <a name="microsoft-edge"></a>Microsoft Edge

[Microsoft Edge](https://www.microsoft.com/edge)提供了世界一流的性能和价值，包括：

- 更多的隐私和保护，防止外部威胁。
- 提高工作效率，可快速访问Office应用、文件、网站和内置Microsoft 搜索。
- 通过跨平台支持和配置文件跨设备同步，实现无缝体验。

> [!IMPORTANT]
> 2022 Internet Explorer 11 桌面应用程序将停用，2022 年 6 月 15 (有关作用域内内容的列表，请参阅 [常见问题](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/internet-explorer-11-desktop-app-retirement-faq/ba-p/2366549)解答。 现在正在使用的 IE11 应用和网站可以在 Microsoft Edge 的 Internet Explorer 模式下打开。 [在此处了解更多信息](https://blogs.windows.com/windowsexperience/2021/05/19/the-future-of-internet-explorer-on-windows-10-is-in-microsoft-edge/)。

## <a name="updates-to-microsoft-edge"></a>更新Microsoft Edge

Microsoft 托管桌面部署扩展[稳定渠道](/deployedge/microsoft-edge-channels#extended-stable-channel)Microsoft Edge，每八周自动更新一次。 扩展稳定渠道上的更新由 Microsoft Edge 产品组[](/deployedge/microsoft-edge-update-progressive-rollout)逐步推出，以确保为客户提供最佳体验。

Beta [渠道](/deployedge/microsoft-edge-channels#beta-channel) 将部署到"测试"组中设备，以在组织中进行代表性验证。 此频道完全受支持，大约每四周自动更新一次新功能。

> [!IMPORTANT]
> 若要确保Microsoft Edge正确更新，请不要修改Microsoft Edge[策略](/deployedge/microsoft-edge-update-policies)。

## <a name="settings-managed-by-microsoft-managed-desktop"></a>设置由 Microsoft 托管桌面

Microsoft 托管桌面创建了一组默认策略，Microsoft Edge保护浏览器的安全。 默认浏览器设置如下所示：

### <a name="microsoft-edge-extensions"></a>Microsoft Edge扩展

在设备上Microsoft Edge安全Microsoft 托管桌面设置两个策略来禁用所有 Chrome 扩展和安全用户。 若要在环境中启用和部署扩展，请参阅设置[管理。](#settings-you-manage)

| 设置 | 默认值 | 描述 |
| ------ | ------ | ------ |
| 扩展安装阻止列表 | 全部 | Microsoft 托管桌面设置此策略，以防止在托管终结点上安装 Chrome 扩展。 存在与扩展Chromium相关的已知风险，包括数据丢失保护、隐私和其他可能损害设备的风险。 |
| 允许在没有管理员权限的情况下安装 (级本机消息传递)  | 禁用 | 通过禁用此策略，Microsoft Edge将仅使用安装在系统级别的本机消息传递主机。 本机消息传递主机是 Chrome 扩展的一部分，允许浏览器与用户终结点的其他部分进行交互，从而产生各种安全问题。 |

### <a name="secure-sockets-layer-tlsssl"></a>TLS/SSL (安全套接字层) 

| 设置 | 默认值 | 描述
| ------ | ------ | ------ |
| 最低 TLS 版本 | 支持的最低 TLS 1.2 | 如果要使用安全性低的 TLS 1.1，可以提出这样做的请求。 |
| 允许用户从 SSL 警告页继续 | 禁用 | 建议不要启用此设置，因为它允许用户访问具有 TSL 错误的网站。 |

### <a name="microsoft-defender-smartscreen"></a>Microsoft Defender SmartScreen

| 设置 | 默认值 | 描述
| ------ | ------ | ------ |
| 配置Windows Defender SmartScreen | 已启用 | 默认情况下启用以帮助保护用户。 |
| Windows Defender SmartScreen 网站提示 | 已启用 | 建议不要禁用此设置，因为这将允许用户忽略警告并继续访问潜在恶意站点。 |
| 阻止绕过有关Windows Defender的 SmartScreen 警告 | 已启用 | 建议不要禁用此设置，因为这将允许用户忽略警告并完成未经验证的下载。 |

### <a name="adobe-flash"></a>Adobe Flash

| 设置 | 默认值 | 描述
| ------ | ------ | ------ |
| 默认 Adobe Flash 设置 | 禁用 | 我们不建议使用 Flash，因为存在相关的安全风险。 <br><br> 如果仍有依赖于 Flash 的进程，请设置 **[PluginsAllowedForUrls](/deployedge/microsoft-edge-policies#pluginsallowedforurls)** 策略，为需要 Flash 的网站启用 Flash。 如果无法维护允许使用 Flash 的网站列表，请提交更改请求以将值更改为"单击播放"，从而允许用户选择何时适合运行 Flash。 |

### <a name="password-manager"></a>密码管理器

| 设置 | 默认值 | 描述
| ------ | ------ | ------ |
| 允许将密码保存至密码管理器 | 禁用 | 默认情况下，密码管理器处于禁用状态。 如果你希望启用此功能，请提出支持请求，我们的服务工程师可以在你的环境中启用该设置。 |

### <a name="internet-explorer-mode-in-microsoft-edge"></a>Internet Explorer模式Microsoft Edge

Microsoft Edge 上的 IE 模式使你能够轻松地在单一浏览器中使用组织所需的所有网站。 它使用与Chromium引擎兼容的网站的集成Chromium引擎。 Microsoft Edge IE11 Internet Explorer 11 (IE11) Trident MSHTML 引擎，用于不依赖 IE 功能或依赖 IE 功能的网站。 [了解更多](/DeployEdge/edge-ie-mode)

Microsoft 托管桌面为Internet Explorer启用设备模式。

| 设置 | 默认值 | 描述
| ------ | ------ | ------ |
| Internet Explorer模式集成 | Internet Explorer 模式 | 默认情况下，设备设置为使用Internet Explorer模式，但你可以将其设置为改为在独立 Internet Explorer 11 窗口中打开网站。 若要更改此行为，请提出支持请求。 |
| 将站点添加到Enterprise站点列表 | 请参阅说明 | 若要使网站以Internet Explorer模式打开，您必须将其包括在"Enterprise[站点"列表中](/DeployEdge/edge-ie-mode-sitelist)。 维护和部署网站Enterprise由你负责。 有关详细信息，请参阅使用[配置模式站点Enterprise配置](/DeployEdge/edge-ie-mode-policies#configure-using-the-configure-the-enterprise-mode-site-list-policy)。 |

### <a name="other-settings"></a>其他设置

| 设置 | 默认值 | 描述
| ------ | ------ | ------ |
| 针对每个网站启用网站隔离 | 已启用 | 启用此策略后，用户不能选择退出每个网站在其自己的进程中运行的默认行为。 |
| 支持的身份验证方案 | NTLM、Negotiate | Microsoft 托管桌面基本身份验证或摘要式身份验证方案。 |
| 首次运行时自动导入其他浏览器的数据和设置 | 自动从默认浏览器导入所有受支持的数据类型和设置。 | 应用此策略后，首次运行体验将跳过导入部分，从而最大限度地减少用户交互。 来自旧版浏览器的浏览器数据Microsoft Edge首次运行时始终以静默方式迁移，无论此设置如何。 |

## <a name="settings-you-manage"></a>设置管理

可以使用管理Microsoft Edge模板配置文件部署之前未介绍的任何Microsoft Intune。 有关详细信息，请参阅 Configure [Microsoft Edge policy settings with Microsoft Intune](/deployedge/configure-edge-with-intune)。 如果你想要评估当前未包含在 Intune Microsoft Edge 管理模板中的策略，可以在 Intune 中为 Windows 10 设备使用自定义设置。

| 设置 | 说明
| ------ | ------ |
| 启用特定 Chrome 扩展 | 管理模板提供了一个设置，用于部署特定 Chrome Microsoft Intune。 可以在计算机配置> Microsoft Edge >**扩展>允许安装特定扩展）中查找它**。 |
| 以静默方式安装扩展 | 您还可以使用管理模板来设置Microsoft Edge安装扩展而不通知用户。 可以在计算机配置> Microsoft Edge >扩展>控制以静默方式安装哪些 **扩展。** |
| Microsoft Edge更新策略 | 若要确保Microsoft Edge正确，请不要修改更新Microsoft Edge[策略](/deployedge/microsoft-edge-update-policies)。 |
| 其他常见企业策略 | Microsoft Edge提供了许多其他策略。 下面是一些更常见的方法： <ul> <li> [配置站点列表Enterprise IE 模式上的站点](/deployedge/edge-ie-mode-sitelist)</li><li> [配置启动、主页和新选项卡页设置](/deployedge/microsoft-edge-policies#startup-home-page-and-new-tab-page)</li> <li> [配置"浏览"游戏设置](/deployedge/microsoft-edge-policies#allowsurfgame)</li> <li> [配置代理服务器设置](/deployedge/microsoft-edge-policies#proxy-server)</li></ul>
