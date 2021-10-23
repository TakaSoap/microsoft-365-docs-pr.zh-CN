---
title: 配置和验证 Microsoft Defender 防病毒软件网络连接
description: 配置和测试与云Microsoft Defender 防病毒的连接。
keywords: 防病毒， Microsoft Defender 防病毒， 反恶意软件， 安全性， defender， 云， 攻击性， 保护级别
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.topic: article
ms.custom: nextgen
ms.date: 10/18/2021
ms.reviewer: ''
manager: dansimp
ms.collection: M365-security-compliance
ms.openlocfilehash: 4ded08af0dfa0bf904d83eef43a76bed3dd4cc2f
ms.sourcegitcommit: 3140e2866de36d57a27d27f70d47e8167c9cc907
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/23/2021
ms.locfileid: "60552436"
---
# <a name="configure-and-validate-microsoft-defender-antivirus-network-connections"></a>配置和验证 Microsoft Defender 防病毒软件网络连接

**适用于：**

- [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)

为了确保Microsoft Defender 防病毒保护正常工作，安全团队必须配置网络以允许终结点和某些 Microsoft 服务器之间连接。 本文列出必须允许的连接（如使用防火墙规则）并提供验证连接的说明。 正确配置保护有助于确保从云提供的保护服务获得最佳价值。

有关网络连接的一些详细信息，请参阅博客文章 [对 Microsoft Active Protection Services](https://techcommunity.microsoft.com/t5/Configuration-Manager-Archive/Important-changes-to-Microsoft-Active-Protection-Service-MAPS/ba-p/274006) 终结点的重要更改。

> [!TIP]
> 请访问 Microsoft Defender for Endpoint 演示网站 [，demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) 确认以下功能是否正常工作：
>
> - 云端保护
> - 快速学习 (包括首次看到时阻止) 
> - 可能不需要的应用程序阻止

## <a name="allow-connections-to-the-microsoft-defender-antivirus-cloud-service"></a>允许连接到 Microsoft Defender 防病毒 云服务

云服务Microsoft Defender 防病毒为终结点提供快速、强大的保护。 启用云保护服务是可选的，但强烈建议这样做，因为它可提供针对终结点和整个网络的恶意软件的重要保护。 请参阅[启用云保护](enable-cloud-protection-microsoft-defender-antivirus.md)，了解有关使用 Intune、Microsoft Endpoint Configuration Manager、组策略、PowerShell cmdlet 或在 Windows 安全中心 应用中各个客户端上启用服务的详细信息。

启用该服务后，可能需要配置网络或防火墙以允许其与终结点连接。 由于你的保护是一项云服务，计算机必须能够访问 Internet 并访问 Microsoft Defender，Office 365机器学习服务。 请勿将 URL `*.blob.core.windows.net` 从任何类型的网络检查中排除。

> [!NOTE]
> 云Microsoft Defender 防病毒是一种向网络和终结点提供更新保护的机制。 尽管它称为云服务，但它并不仅仅是对存储在云中的文件的保护，而是使用分布式资源和机器学习以比传统安全智能更新快得多的速度为终结点提供保护。

## <a name="services-and-urls"></a>服务和 URL

本节中的表列出了服务及其关联的网站地址 (URL) 。

确保没有防火墙或网络筛选规则拒绝访问这些 URL。 否则，可能需要专门为他们创建允许规则， (URL `*.blob.core.windows.net`) 。 下表中的 URL 使用端口 443 进行通信。

<br/><br/>

|服务和说明|URL|
|---|---|
|Microsoft Defender 防病毒云保护服务，也称为地图Microsoft Active Protection Service (MAPS) <p>此服务由组织Microsoft Defender 防病毒提供云保护|`*.wdcp.microsoft.com` <p> `*.wdcpalt.microsoft.com` <p> `*.wd.microsoft.com`|
|MICROSOFT Update Service (MU) and Windows Update Service (WU)  <p>这些服务允许安全智能和产品更新|`*.update.microsoft.com` <p> `*.delivery.mp.microsoft.com`<p> `*.windowsupdate.com` <p> 有关详细信息，请参阅[Connection endpoints for Windows Update](/windows/privacy/manage-windows-1709-endpoints#windows-update)|
|安全智能更新 ADL (备用) <p>如果安装的安全智能在 Microsoft Defender 防病毒 7 天或 7 (过期，则这是安全智能更新的备用) |`*.download.microsoft.com` <p> `*.download.windowsupdate.com`<p>  `go.microsoft.com`<p> `https://fe3cr.delivery.mp.microsoft.com/ClientWebService/client.asmx`|
|恶意软件提交存储 <p>这是通过提交表单或自动示例提交提交到 Microsoft 的文件的上传位置|`ussus1eastprod.blob.core.windows.net` <p> `ussus2eastprod.blob.core.windows.net` <p> `ussus3eastprod.blob.core.windows.net` <p> `ussus4eastprod.blob.core.windows.net` <p> `wsus1eastprod.blob.core.windows.net` <p> `wsus2eastprod.blob.core.windows.net` <p> `ussus1westprod.blob.core.windows.net` <p> `ussus2westprod.blob.core.windows.net` <p> `ussus3westprod.blob.core.windows.net` <p> `ussus4westprod.blob.core.windows.net` <p> `wsus1westprod.blob.core.windows.net` <p> `wsus2westprod.blob.core.windows.net` <p> `usseu1northprod.blob.core.windows.net` <p> `wseu1northprod.blob.core.windows.net` <p> `usseu1westprod.blob.core.windows.net` <p> `wseu1westprod.blob.core.windows.net` <p> `ussuk1southprod.blob.core.windows.net` <p> `wsuk1southprod.blob.core.windows.net` <p> `ussuk1westprod.blob.core.windows.net` <p> `wsuk1westprod.blob.core.windows.net`|
|CRL (证书吊销)  <p>在创建与 MAPS 的 SSL Windows更新 CRL 时，系统使用此列表|`http://www.microsoft.com/pkiops/crl/` <p> `http://www.microsoft.com/pkiops/certs` <p> `http://crl.microsoft.com/pki/crl/products` <p> `http://www.microsoft.com/pki/certs`|
|符号存储 <p>符号存储由 Microsoft Defender 防病毒在修正流期间还原某些关键文件|`https://msdl.microsoft.com/download/symbols`|
|通用遥测客户端 <p> 此客户端由 Windows用于发送客户端诊断数据 <p> Microsoft Defender 防病毒遥测进行产品质量监视|此更新使用 SSL (TCP 端口 443) 下载清单，将诊断数据上载到使用下列 DNS 终结点的 Microsoft： <p> `vortex-win.data.microsoft.com` <p> `settings-win.data.microsoft.com`|

## <a name="validate-connections-between-your-network-and-the-cloud"></a>验证网络和云之间的连接

允许上面列出的 URL 后，你可以测试你是否连接到 Microsoft Defender 防病毒 云服务并正确报告和接收信息，以确保完全受保护。

### <a name="use-the-cmdline-tool-to-validate-cloud-delivered-protection"></a>使用 cmdline 工具验证云保护

将以下参数与 Microsoft Defender 防病毒 命令行实用程序 () 验证网络能否与 Microsoft Defender 防病毒 `mpcmdrun.exe` 云服务通信：

```console
"%ProgramFiles%\Windows Defender\MpCmdRun.exe" -ValidateMapsConnection
```

> [!NOTE]
> 需要打开命令提示符的管理员级别版本。 右键单击用户策略中的 **"开始"菜单，** 单击"以管理员角色运行"，在权限提示符下单击"是"。 此命令仅适用于 Windows 10 版本 1703 或更高版本，或 Windows 11。

有关详细信息，请参阅使用命令行Microsoft Defender 防病毒[管理mpcmdrun.exe管理。](command-line-arguments-microsoft-defender-antivirus.md)

### <a name="attempt-to-download-a-fake-malware-file-from-microsoft"></a>尝试从 Microsoft 下载假恶意软件文件

你可以下载示例文件，Microsoft Defender 防病毒正确连接到云，将检测并阻止该文件。

通过访问 下载 [https://aka.ms/ioavtest](https://aka.ms/ioavtest) 文件。

> [!NOTE]
> 此文件不是恶意软件的实际部分。 这是一个假文件，旨在测试你是否正确连接到云。

如果连接正确，你将看到一条警告Microsoft Defender 防病毒通知。

如果使用的是Microsoft Edge，则还会看到一条通知消息：

:::image type="content" source="../../media/wdav-bafs-edge.png" alt-text="在 Edge 中发现恶意软件的通知屏幕截图。":::

如果您使用以下方法，则会出现Internet Explorer：

:::image type="content" source="../../media/wdav-bafs-ie.png" alt-text="发现恶意软件的 Microsoft Defender AV 通知。":::

你还将在应用扫描历史记录部分中的隔离威胁下看到Windows 安全中心检测：

1. 通过单击Windows 安全中心中的防护图标或搜索"安全"的"开始"菜单打开 **应用。**

2. 选择 **病毒&威胁防护，** 然后选择保护 **历史记录**。

3. 在" **隔离的威胁"** 部分下， **选择"查看完整历史记录** "以查看检测到的假恶意软件。

   > [!NOTE]
   > 版本 1703 Windows 10版本版本具有不同的用户界面。 请参阅[Microsoft Defender 防病毒应用中Windows 安全中心应用。](microsoft-defender-security-center-antivirus.md)

   事件Windows还会显示客户端Windows Defender ID [1116](troubleshoot-microsoft-defender-antivirus.md)。

## <a name="see-also"></a>另请参阅

- [配置设备代理和 Internet 连接设置](configure-proxy-internet.md)
- [使用组策略设置配置和管理Microsoft Defender 防病毒](use-group-policy-microsoft-defender-antivirus.md)