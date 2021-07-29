---
title: Mac 上的 Microsoft Defender for Endpoint
ms.reviewer: ''
description: 了解如何在 Mac 上安装、配置、更新和使用 Microsoft Defender for Endpoint。
keywords: microsoft， defender， Microsoft Defender for Endpoint， mac， 安装， 部署， 卸载， intune， jamf， macos， big sur， catalina， mojave， mde for mac
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 2c2c0ff1cfa84689215272d1fcf5a1f7476ca4d9
ms.sourcegitcommit: 3576c2fee77962b516236cb67dd3df847d61c527
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/28/2021
ms.locfileid: "53621843"
---
# <a name="microsoft-defender-for-endpoint-on-mac"></a>Mac 上的 Microsoft Defender for Endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 希望体验 Microsoft Defender for Endpoint？ [注册免费试用版](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)。

本主题介绍如何在 Mac 上安装、配置、更新和使用 Defender for Endpoint。

> [!CAUTION]
> 在 Mac 上的 Microsoft Defender for Endpoint 旁边运行其他第三方终结点保护产品可能会导致性能问题和不可预知的副作用。 如果非 Microsoft 终结点保护在你的环境中是绝对要求，在将防病毒功能配置为在被动模式下运行后，你仍然可以安全地利用 Mac 上的 Defender for Endpoint EDR[功能。](mac-preferences.md#enable--disable-passive-mode)

## <a name="whats-new-in-the-latest-release"></a>最新版本的新增功能

[Microsoft Defender for Endpoint 中的新增功能](whats-new-in-microsoft-defender-atp.md)

[Mac 上的 Microsoft Defender for Endpoint 的新增功能](mac-whatsnew.md)

> [!TIP]
> 如果你有任何要共享的反馈，请通过在你的设备上打开 Mac 上的 Microsoft Defender for Endpoint 并导航到"帮助发送反馈"来  >  **提交它**。

若要获取最新功能（包括预览功能 (如适用于 Mac 设备的终结点检测和响应) ，请配置运行 Microsoft Defender for Endpoint 的 macOS 设备作为"预览体验成员"设备。

## <a name="how-to-install-microsoft-defender-for-endpoint-on-mac"></a>如何在 Mac 上安装 Microsoft Defender for Endpoint

### <a name="prerequisites"></a>先决条件

- Defender for Endpoint 订阅和访问 Microsoft 365 Defender 门户
- macOS 和 BASH 脚本的初学者级体验
- 手动部署时，设备上 (管理权限) 

### <a name="installation-instructions"></a>安装说明

可以使用多种方法和部署工具在 Mac 上安装和配置 Defender for Endpoint。

- 第三方管理工具：
    - [基于 Microsoft Intune 的部署](mac-install-with-intune.md)
    - [基于 JAMF 的部署](mac-install-with-jamf.md)
    - [其他 MDM 产品](mac-install-with-other-mdm.md)

- 命令行工具：
    - [手动部署](mac-install-manually.md)

### <a name="system-requirements"></a>系统要求

支持 macOS 的三个最新主要版本。

> [!IMPORTANT]
> 在 macOS 11 (Sur) 上，Microsoft Defender for Endpoint 需要额外的配置文件。 如果你是从 macOS 早期版本升级的现有客户，请确保部署 [macOS Catalina](mac-sysext-policies.md)的新配置文件和较新版本的 macOS 中列出的其他配置文件。

> [!IMPORTANT]
> 截至 2021 年 2 月 15 (对) MacOS 10.13) 的支持已终止。

- 11 (大) ，10.15 (加泰罗尼亚语) ，10.14 (Mojave) 
- 磁盘空间：1GB

不支持 macOS 的 Beta 版本。

不支持具有 M1 处理器的 macOS 设备。

启用该服务后，可能需要配置网络或防火墙以允许其与终结点之间的出站连接。

### <a name="licensing-requirements"></a>许可要求

Mac 上的 Microsoft Defender for Endpoint 需要以下 Microsoft 批量许可产品/服务之一：

- Microsoft 365 E5 (M365 E5) 
- Microsoft 365 E5 安全性
- Microsoft 365 A5 (M365 A5) 
- Windows 10 企业版E5
- Microsoft Defender for Endpoint

> [!NOTE]
> 符合条件的许可用户可以在最多五台并发设备上使用 Microsoft Defender for Endpoint。
> Microsoft Defender for Endpoint 还可从云解决方案提供商云解决方案提供商 (购买) 。 通过云解决方案提供商购买时，不需要列出 Microsoft 批量许可产品/服务。

### <a name="network-connections"></a>网络连接

以下可下载的电子表格列出了网络必须能够连接到的服务及其关联 URL。 应确保没有拒绝访问这些 URL 的防火墙或网络筛选规则，或者您可能需要专门为它们创建允许规则。 

|域列表电子表格|说明|
|---|---|
|![适用于终结点 URL 电子表格的 Microsoft Defender 缩略图](images/mdatp-urls.png)|服务位置、地理位置和操作系统的特定 DNS 记录的电子表格。 <p> 在此处下载[电子表格：mdatp-urls.xlsx。 ](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx)

Microsoft Defender for Endpoint 可以通过以下发现方法发现代理服务器：

- PAC (代理) 
- Web 代理自动发现协议 (WPAD)
- 手动静态代理配置

如果代理或防火墙阻止匿名流量，请确保允许匿名流量位于前面列出的 URL 中。

> [!WARNING]
> 不支持经过身份验证的代理。 确保仅使用 PAC、WPAD 或静态代理。
>
> 出于安全考虑，也不支持 SSL 检查和截获代理。 为 SSL 检查和代理服务器配置例外，以将数据从 macOS 上的 Microsoft Defender for Endpoint 直接传递到相关 URL，而不会拦截。 将拦截证书添加到全局存储将不允许拦截。

若要测试连接是否未阻止，请打开 <https://x.cp.wd.microsoft.com/api/report> <https://cdn.x.cp.wd.microsoft.com/ping> ，在浏览器中打开。

如果您更喜欢命令行，还可以在终端中运行以下命令来检查连接：

```bash
curl -w ' %{url_effective}\n' 'https://x.cp.wd.microsoft.com/api/report' 'https://cdn.x.cp.wd.microsoft.com/ping'
```

此命令的输出应类似于以下内容：

 `OK https://x.cp.wd.microsoft.com/api/report`

 `OK https://cdn.x.cp.wd.microsoft.com/ping`

> [!CAUTION]
> 建议在客户端设备上保持 [启用 (](https://support.apple.com/HT204899) SIP) 系统完整性保护。 SIP 是内置的 macOS 安全功能，可防止对操作系统进行低级篡改，并且默认启用。

安装 Microsoft Defender for Endpoint 后，可通过在终端中运行以下命令来验证连接性：

```bash
mdatp connectivity test
```

## <a name="how-to-update-microsoft-defender-for-endpoint-on-mac"></a>如何在 Mac 上更新 Microsoft Defender for Endpoint

Microsoft 会定期发布软件更新，以提高性能、安全性和提供新功能。 若要更新 Mac 上的 Microsoft Defender for Endpoint，使用名为 Microsoft AutoUpdate (MAU) 程序。 若要了解更多信息，请参阅 [在 Mac](mac-updates.md)上部署 Microsoft Defender for Endpoint 更新。

## <a name="how-to-configure-microsoft-defender-for-endpoint-on-mac"></a>如何在 Mac 上配置 Microsoft Defender for Endpoint

有关如何在企业环境中配置产品的指南可在在 Mac 上设置 [Microsoft Defender for Endpoint 的首选项中提供](mac-preferences.md)。

## <a name="macos-kernel-and-system-extensions"></a>macOS 内核和系统扩展

为了与 macOS 演变保持一致，我们正在准备利用系统扩展而非内核扩展的 Mac 上的 Microsoft Defender for Endpoint 更新。 有关相关详细信息，请参阅 Mac 上的 [Microsoft Defender for Endpoint 中的新增功能](mac-whatsnew.md)。

## <a name="resources"></a>资源

- 有关日志记录、卸载或其他主题的信息，请参阅 Mac 上的 [Microsoft Defender for Endpoint 的资源](mac-resources.md)。
- [Mac 上的 Microsoft Defender for Endpoint 的隐私](mac-privacy.md)。
