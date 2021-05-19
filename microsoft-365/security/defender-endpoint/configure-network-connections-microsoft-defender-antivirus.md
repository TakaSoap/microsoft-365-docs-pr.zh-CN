---
title: 配置和验证 Microsoft Defender 防病毒软件网络连接
description: 配置和测试与云保护Microsoft Defender 防病毒的连接。
keywords: 防病毒， Microsoft Defender 防病毒， 反恶意软件， 安全性， defender， 云， 攻击性， 保护级别
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 05/17/2021
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 5e754c2f4b5406d4b91ef624415f3819d3171305
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2021
ms.locfileid: "52536018"
---
# <a name="configure-and-validate-microsoft-defender-antivirus-network-connections"></a>配置和验证 Microsoft Defender 防病毒软件网络连接

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**适用于：**

- [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)

为了确保Microsoft Defender 防病毒保护正常工作，需要配置网络以允许终结点和某些 Microsoft 服务器连接。 本文列出必须允许的连接（如使用防火墙规则）并提供验证连接的说明。 正确配置保护有助于确保从云提供的保护服务获得最佳价值。

有关网络连接的一些详细信息，请参阅博客文章 [对 Microsoft Active Protection Services](https://techcommunity.microsoft.com/t5/Configuration-Manager-Archive/Important-changes-to-Microsoft-Active-Protection-Service-MAPS/ba-p/274006) 终结点的重要更改。

> [!TIP]
> 还可以访问 Microsoft Defender for Endpoint 演示[](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground)网站，demo.wd.microsoft.com 确认以下功能是否正常工作：
>
> - 云端保护
> - 快速学习 (包括首次看到时阻止) 
> - 可能不需要的应用程序阻止

## <a name="allow-connections-to-the-microsoft-defender-antivirus-cloud-service"></a>允许连接到 Microsoft Defender 防病毒 云服务

云Microsoft Defender 防病毒为终结点提供快速、强大的保护。 启用云保护服务是可选的，但强烈建议这样做，因为它可提供针对终结点和整个网络的恶意软件的重要保护。

> [!NOTE]
> Microsoft Defender 防病毒云服务是一种向网络和终结点提供更新保护的机制。 尽管它称为云服务，但它并不仅仅是对存储在云中的文件的保护，而是使用分布式资源和机器学习以比传统安全智能更新快得多的速度为终结点提供保护。

请参阅[启用云保护](enable-cloud-protection-microsoft-defender-antivirus.md)，了解有关使用 Intune、Microsoft Endpoint Configuration Manager、组策略、PowerShell cmdlet 或在 Windows 安全中心 应用中各个客户端上启用服务的详细信息。 

启用该服务后，可能需要配置网络或防火墙以允许其与终结点连接。

由于你的保护是一项云服务，计算机必须能够访问 Internet 并访问 Microsoft Defender，Office 365机器学习服务。 请勿将 URL `*.blob.core.windows.net` 从任何类型的网络检查中排除。 

下表列出了服务及其关联的 URL。 请确保没有防火墙或网络筛选规则拒绝访问这些 URL，或者您可能需要专门为它们创建允许规则 (排除 URL `*.blob.core.windows.net`) 。 下面提及 URL 正在使用端口 443 进行通信。


| **服务**| **说明** |**URL** |
| :--: | :-- | :-- |
| Microsoft Defender 防病毒云提供的保护服务，也称为MICROSOFT ACTIVE PROTECTION SERVICE (MAPS) |由Microsoft Defender 防病毒提供云保护|`*.wdcp.microsoft.com` <br/> `*.wdcpalt.microsoft.com` <br/> `*.wd.microsoft.com`|
| MICROSOFT Update Service (MU)  <br/> Windows更新服务 (WU) |  安全智能和产品更新   |`*.update.microsoft.com` <br/> `*.delivery.mp.microsoft.com`<br/> `*.windowsupdate.com` <br/><br/> 有关详细信息，请参阅[Connection endpoints for Windows Update](/windows/privacy/manage-windows-1709-endpoints#windows-update)|
|安全智能更新 ADL (备用) |   如果安装的安全Microsoft Defender 防病毒在安装后 7 天或 7 (过期，则安全智能更新的备用) |    `*.download.microsoft.com`  </br> `*.download.windowsupdate.com`</br>  `go.microsoft.com`</br> `https://fe3cr.delivery.mp.microsoft.com/ClientWebService/client.asmx`|
| 恶意软件提交存储|Upload提交表单或自动示例提交提交到 Microsoft 的文件的提交位置    | `ussus1eastprod.blob.core.windows.net` <br/>    `ussus2eastprod.blob.core.windows.net` <br/>    `ussus3eastprod.blob.core.windows.net` <br/>    `ussus4eastprod.blob.core.windows.net` <br/>    `wsus1eastprod.blob.core.windows.net` <br/>    `wsus2eastprod.blob.core.windows.net` <br/>    `ussus1westprod.blob.core.windows.net` <br/>    `ussus2westprod.blob.core.windows.net` <br/>    `ussus3westprod.blob.core.windows.net` <br/>    `ussus4westprod.blob.core.windows.net` <br/>    `wsus1westprod.blob.core.windows.net` <br/>    `wsus2westprod.blob.core.windows.net` <br/>    `usseu1northprod.blob.core.windows.net` <br/>    `wseu1northprod.blob.core.windows.net` <br/>    `usseu1westprod.blob.core.windows.net` <br/>    `wseu1westprod.blob.core.windows.net` <br/>    `ussuk1southprod.blob.core.windows.net` <br/>    `wsuk1southprod.blob.core.windows.net` <br/>    `ussuk1westprod.blob.core.windows.net` <br/>    `wsuk1westprod.blob.core.windows.net` |
| CRL (证书吊销) |供Windows创建与 MAPS 的 SSL 连接以更新 CRL 时使用   | `http://www.microsoft.com/pkiops/crl/` <br/> `http://www.microsoft.com/pkiops/certs` <br/>   `http://crl.microsoft.com/pki/crl/products` <br/> `http://www.microsoft.com/pki/certs` |
| 符号存储|由 Microsoft Defender 防病毒在修正流期间还原某些关键文件  | `https://msdl.microsoft.com/download/symbols` |
| 通用遥测客户端| Used by Windows to send client diagnostic data;Microsoft Defender 防病毒遥测来监视产品质量   | 此更新使用 SSL (TCP 端口 443) 下载清单，将诊断数据上载到使用下列 DNS 终结点的 Microsoft：   `vortex-win.data.microsoft.com` <br/>   `settings-win.data.microsoft.com`|

## <a name="validate-connections-between-your-network-and-the-cloud"></a>验证网络和云之间的连接

允许上面列出的 URL 后，你可以测试你是否连接到 Microsoft Defender 防病毒 云服务并正确报告和接收信息，以确保完全受保护。

**使用 cmdline 工具验证云保护：**

将以下参数与 Microsoft Defender 防病毒 命令行实用程序 () 验证网络能否与 Microsoft Defender 防病毒 `mpcmdrun.exe` 云服务通信：

```console
"%ProgramFiles%\Windows Defender\MpCmdRun.exe" -ValidateMapsConnection
```

> [!NOTE]
> 需要打开命令提示符的管理员级别版本。 右键单击"开始"菜单中的项，单击"以管理员角色运行 **"，** 在权限提示符下单击"是"。 此命令仅适用于版本Windows 10版本 1703 或更高版本。

有关详细信息，请参阅使用命令行Microsoft Defender 防病毒[管理mpcmdrun.exe管理。](command-line-arguments-microsoft-defender-antivirus.md)

**尝试从 Microsoft 下载假恶意软件文件：**

你可以下载示例文件，Microsoft Defender 防病毒正确连接到云，将检测并阻止该文件。

通过访问 下载 [https://aka.ms/ioavtest](https://aka.ms/ioavtest) 文件。

> [!NOTE]
> 此文件不是恶意软件的实际部分。 这是一个假文件，旨在测试你是否正确连接到云。

如果连接正确，你将看到一条警告Microsoft Defender 防病毒通知。

如果您使用的是Microsoft Edge，则还会看到一条通知消息：

![Microsoft Edge通知用户已发现恶意软件](images/defender/wdav-bafs-edge.png)

如果您使用以下方法，则会出现Internet Explorer：

![Microsoft Defender 防病毒通知用户已发现恶意软件](images/defender/wdav-bafs-ie.png)

你还在应用扫描历史记录部分中的隔离威胁下看到Windows 安全中心检测：

1. 通过Windows 安全中心任务栏中的防护图标或搜索 Defender 的"开始"菜单打开"开始 **"菜单。**

2. 选择病毒& **威胁** 防护磁贴 (左侧菜单栏上的防护图标) "扫描 **历史记录** "标签：

    !["扫描历史记录"标签在Windows 安全中心屏幕截图](images/defender/wdav-history-wdsc.png)

3. 在" **隔离的威胁"** 部分下， **选择"查看完整历史记录** "以查看检测到的假恶意软件。

   > [!NOTE]
   > 版本 1703 Windows 10版本版本具有不同的用户界面。 请参阅[Microsoft Defender 防病毒应用中Windows 安全中心应用。](microsoft-defender-security-center-antivirus.md)

   事件Windows还会显示客户端Windows Defender ID [1116](troubleshoot-microsoft-defender-antivirus.md)。

## <a name="related-articles"></a>相关文章

- [Windows 10 中的 Microsoft Defender 防病毒](microsoft-defender-antivirus-in-windows-10.md)

- [启用云保护](enable-cloud-protection-microsoft-defender-antivirus.md)

- [命令行参数](command-line-arguments-microsoft-defender-antivirus.md)

- [对 Microsoft Active Protection Services 终结点的重要更改](https://techcommunity.microsoft.com/t5/Configuration-Manager-Archive/Important-changes-to-Microsoft-Active-Protection-Service-MAPS/ba-p/274006)
