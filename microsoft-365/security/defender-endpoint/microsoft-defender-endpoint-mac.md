---
title: Mac 上的 Microsoft Defender for Endpoint
ms.reviewer: ''
description: 了解如何在 Mac 上安装、配置、更新和使用Microsoft Defender for Endpoint应用程序。
keywords: microsoft， defender， Microsoft Defender for Endpoint， mac， 安装， 部署， 卸载， intune， jamf， macos，reyrey， big sur， catalina， mojave， mde for mac
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365-initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 2e982a32826906feb65b05837506ff2f513eb27e
ms.sourcegitcommit: bcbcbd4ddc72ad2fed629619d23fac5827d072bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/29/2022
ms.locfileid: "64507292"
---
# <a name="microsoft-defender-for-endpoint-on-mac"></a>Mac 上的 Microsoft Defender for Endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint 计划 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 希望体验 Microsoft Defender for Endpoint？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)。

本主题介绍如何在 Mac 上安装、配置、更新和使用 Defender for Endpoint。

> [!CAUTION]
> 在 Mac 上运行其他第三Microsoft Defender for Endpoint保护产品可能会导致性能问题和不可预知的副作用。 如果非 Microsoft 终结点保护在你的环境中是绝对要求，在将防病毒功能配置为在被动模式下运行后，你仍然可以安全地利用 Mac EDR 上的 Defender for [Endpoint 功能](mac-preferences.md#enforcement-level-for-antivirus-engine)。

## <a name="whats-new-in-the-latest-release"></a>最新版本的新增功能

[Microsoft Defender for Endpoint 中的新增功能](whats-new-in-microsoft-defender-endpoint.md)

[Mac 上 Microsoft Defender for Endpoint 的新增功能](mac-whatsnew.md)

> [!TIP]
> 如果有任何要共享的反馈，请通过打开Microsoft Defender for Endpoint Mac  \> 上的"帮助""发送反馈"来 **提交反馈**。

若要获取最新功能，包括预览功能 (如适用于 Mac) 的 终结点检测和响应，请配置运行 Microsoft Defender for Endpoint 的 macOS 设备为"预览体验成员"设备。

## <a name="how-to-install-microsoft-defender-for-endpoint-on-mac"></a>如何在 Mac Microsoft Defender for Endpoint安装程序

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
> 在 macOS 11 (及) ，Microsoft Defender for Endpoint需要其他配置文件。 如果您是从 macOS 早期版本升级的现有客户，请确保部署 [macOS Catalina 和较新版本的 macOS](mac-sysext-policies.md) 的新配置文件中列出的其他配置文件。

- 12 (Rey) ，11 (Big Sur) ，10.15 (加泰罗尼亚语) 
- 磁盘空间：1GB

不支持 macOS 的 Beta 版本。

自代理版本 101.40.84 起，正式支持具有基于 M1 芯片的处理器的 macOS 设备。

启用该服务后，可能需要配置网络或防火墙以允许其与终结点之间的出站连接。

### <a name="licensing-requirements"></a>许可要求

Microsoft Defender for Endpoint Mac 上的许可需要以下 Microsoft 批量许可产品/服务之一：

- Microsoft 365 E5 (M365 E5) 
- Microsoft 365 E5 安全性
- Microsoft 365 A5 (M365 A5) 
- Windows 10 企业版 E5
- Microsoft 365 商业高级版
- Windows 11 企业版 E5
- Microsoft Defender for Endpoint

> [!NOTE]
> 符合条件的许可用户可以在最多五Microsoft Defender for Endpoint设备上使用许可证。
> Microsoft Defender for Endpoint也可以从云解决方案提供商云解决方案提供商 (购买) 。 通过云解决方案提供商购买时，不需要列出 Microsoft 批量许可产品/服务。

### <a name="configuring-exclusions"></a>配置排除项

添加排除项时，请注意用于添加[Microsoft Defender 防病毒](/microsoft-365/security/defender-endpoint/common-exclusion-mistakes-microsoft-defender-antivirus)。

### <a name="network-connections"></a>网络连接

以下可下载的电子表格列出了网络必须能够连接到的服务及其关联 URL。 应确保没有拒绝访问这些 URL 的防火墙或网络筛选规则，或者您可能需要专门为它们创建允许规则。


|域列表的电子表格| 说明|
|---|---|
|Microsoft Defender for Endpoint客户的 URL 列表| 服务位置、地理位置和商业客户操作系统的特定 DNS 记录的电子表格。 <p> [在此处下载电子表格。](https://download.microsoft.com/download/6/b/f/6bfff670-47c3-4e45-b01b-64a2610eaefa/mde-urls-commercial.xlsx)
| Microsoft Defender for Endpoint Gov/GCC/DoD 的 URL 列表 | Gov/GCC/DoD 客户的服务位置、地理位置和操作系统的特定 DNS 记录的电子表格。 <p> [在此处下载电子表格。](https://download.microsoft.com/download/6/a/0/6a041da5-c43b-4f17-8167-79dfdc10507f/mde-urls-gov.xlsx)

Microsoft Defender for Endpoint以下发现方法发现代理服务器：

- PAC (代理) 
- Web 代理自动发现协议 (WPAD)
- 手动静态代理配置

如果代理或防火墙阻止匿名流量，请确保前面列出的 URL 中允许匿名流量。

> [!WARNING]
> 不支持经过身份验证的代理。 确保仅使用 PAC、WPAD 或静态代理。
>
> 出于安全考虑，也不支持 SSL 检查和截获代理。 为 SSL 检查和代理服务器配置例外，以直接将数据从 macOS Microsoft Defender for Endpoint传递到相关 URL，而不会拦截。 将拦截证书添加到全局存储将不允许拦截。

若要测试连接是否未阻止，请打开 <https://x.cp.wd.microsoft.com/api/report> ，在 <https://cdn.x.cp.wd.microsoft.com/ping> 浏览器中打开。

如果您更喜欢命令行，还可以在终端中运行以下命令来检查连接：

```bash
curl -w ' %{url_effective}\n' 'https://x.cp.wd.microsoft.com/api/report' 'https://cdn.x.cp.wd.microsoft.com/ping'
```

此命令的输出应类似于以下内容：

 `OK https://x.cp.wd.microsoft.com/api/report`

 `OK https://cdn.x.cp.wd.microsoft.com/ping`

> [!CAUTION]
> 建议在客户端设备上保持 [启用 (SIP](https://support.apple.com/HT204899)) 系统完整性保护。 SIP 是内置的 macOS 安全功能，可防止对操作系统进行低级篡改，并且默认启用。

安装Microsoft Defender for Endpoint后，可通过在终端中运行以下命令来验证连接性：

```bash
mdatp connectivity test
```

## <a name="how-to-update-microsoft-defender-for-endpoint-on-mac"></a>如何在 Mac Microsoft Defender for Endpoint更新

Microsoft 会定期发布软件更新，以提高性能、安全性和提供新功能。 若要在 Mac Microsoft Defender for Endpoint，使用名为 Microsoft AutoUpdate (MAU) 程序。 若要了解更多信息，请参阅[在 Mac Microsoft Defender for Endpoint更新](mac-updates.md)。

## <a name="how-to-configure-microsoft-defender-for-endpoint-on-mac"></a>如何在 Mac Microsoft Defender for Endpoint配置设备

有关如何在企业环境中配置产品的指南，可在在 Mac 上设置产品Microsoft Defender for Endpoint[设置首选项](mac-preferences.md)。

## <a name="macos-kernel-and-system-extensions"></a>macOS 内核和系统扩展

为了与 macOS 演变保持一致，我们Microsoft Defender for Endpoint Mac 更新，该更新利用系统扩展而不是内核扩展。 有关相关详细信息，请参阅 [Mac 上 Microsoft Defender for Endpoint的新增功能](mac-whatsnew.md)。

## <a name="resources"></a>资源

- 有关日志记录、卸载或其他主题的信息，请参阅 Mac [上的 Microsoft Defender for Endpoint 资源](mac-resources.md)。
- [Mac Microsoft Defender for Endpoint隐私](mac-privacy.md)。
