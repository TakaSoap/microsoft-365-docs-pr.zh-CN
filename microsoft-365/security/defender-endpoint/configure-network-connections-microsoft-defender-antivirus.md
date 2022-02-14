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
ms.date: 02/03/2022
ms.reviewer: mkaminska; pahuijbr
manager: dansimp
ms.collection: M365-security-compliance
ms.openlocfilehash: f29cf5f77acd52a4ff3ccc8384f3c64861e48b64
ms.sourcegitcommit: 355ab75eb7b604c6afbe9a5a1b97ef16a1dec4fc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/14/2022
ms.locfileid: "62806032"
---
# <a name="configure-and-validate-microsoft-defender-antivirus-network-connections"></a>配置和验证 Microsoft Defender 防病毒软件网络连接

**适用于：**

- [Microsoft Defender for Endpoint 计划 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

为了确保Microsoft Defender 防病毒保护正常工作，安全团队必须将网络配置为允许终结点和某些 Microsoft 服务器连接。 本文列出了必须允许使用防火墙规则的连接。 它还提供有关验证连接的说明。 正确配置保护将确保从云提供的保护服务获得最佳价值。

> [!IMPORTANT]
> 本文包含有关仅为用户配置网络连接Microsoft Defender 防病毒。 如果你使用的是 Microsoft Defender for Endpoint (包括Microsoft Defender 防病毒) ，请参阅为 Defender for Endpoint 配置设备代理和 [Internet 连接设置](configure-proxy-internet.md)。


> [!NOTE]
> 位于 Demo.wd.microsoft.com 的 Defender for Endpoint 演示网站已弃用，将在未来删除。

## <a name="allow-connections-to-the-microsoft-defender-antivirus-cloud-service"></a>允许连接到 Microsoft Defender 防病毒 云服务

云Microsoft Defender 防病毒为终结点提供快速而强大的保护。 可以选择启用云保护服务。 Microsoft Defender 防病毒云服务，因为它提供针对终结点和网络恶意软件的重要保护。 有关详细信息，请参阅启用云[](enable-cloud-protection-microsoft-defender-antivirus.md)保护以使用 Intune、Microsoft Endpoint Configuration Manager、组策略、PowerShell cmdlet 或 Windows 安全中心 应用中的单个客户端启用服务。

启用该服务后，需要配置网络或防火墙以允许网络与终结点之间的连接。 由于保护是一项云服务，因此计算机必须有权访问 Internet 并访问 Microsoft 云服务。 请勿将 URL 从 `*.blob.core.windows.net` 任何类型的网络检查中排除。

> [!NOTE]
> 云服务Microsoft Defender 防病毒为网络和终结点提供更新的保护。 不应将云服务视为仅保护存储在云中的文件;相反，云服务使用分布式资源和机器学习以比传统安全智能更新更快的速度为终结点提供保护。

## <a name="services-and-urls"></a>服务和 URL

本节中的表列出了服务及其关联的网站地址 (URL) 。

确保没有防火墙或网络筛选规则拒绝访问这些 URL。 否则，您必须专门为这些 URL 创建允许规则， (URL `*.blob.core.windows.net`) 。 下表中的 URL 使用端口 443 进行通信。

<br/><br/>

|服务和说明|URL|
|---|---|
|Microsoft Defender 防病毒云保护服务称为 MAPS Microsoft Active Protection Service (MAPS) 。<p> 该Microsoft Defender 防病毒使用 MAPS 服务来提供云保护。|`*.wdcp.microsoft.com` <p> `*.wdcpalt.microsoft.com` <p> `*.wd.microsoft.com`|
|MICROSOFT Update Service (WU) Windows 更新服务 (WU)  <p>这些服务将允许安全智能和产品更新。|`*.update.microsoft.com` <p> `*.delivery.mp.microsoft.com`<p> `*.windowsupdate.com` <p> 有关详细信息，请参阅 [Connection endpoints for Windows Update](/windows/privacy/manage-windows-1709-endpoints#windows-update)|
|安全智能更新 ADL (备用) <p>如果安装的安全智能在 Microsoft Defender 防病毒七天或七天后过期，则此位置 (安全智能更新的) 。|`*.download.microsoft.com` <p> `*.download.windowsupdate.com`<p>  `go.microsoft.com`<p> `https://fe3cr.delivery.mp.microsoft.com/ClientWebService/client.asmx`|
|恶意软件提交存储 <p>这是通过提交表单或自动示例提交提交到 Microsoft 的文件的上载位置。|`ussus1eastprod.blob.core.windows.net` <p> `ussus2eastprod.blob.core.windows.net` <p> `ussus3eastprod.blob.core.windows.net` <p> `ussus4eastprod.blob.core.windows.net` <p> `wsus1eastprod.blob.core.windows.net` <p> `wsus2eastprod.blob.core.windows.net` <p> `ussus1westprod.blob.core.windows.net` <p> `ussus2westprod.blob.core.windows.net` <p> `ussus3westprod.blob.core.windows.net` <p> `ussus4westprod.blob.core.windows.net` <p> `wsus1westprod.blob.core.windows.net` <p> `wsus2westprod.blob.core.windows.net` <p> `usseu1northprod.blob.core.windows.net` <p> `wseu1northprod.blob.core.windows.net` <p> `usseu1westprod.blob.core.windows.net` <p> `wseu1westprod.blob.core.windows.net` <p> `ussuk1southprod.blob.core.windows.net` <p> `wsuk1southprod.blob.core.windows.net` <p> `ussuk1westprod.blob.core.windows.net` <p> `wsuk1westprod.blob.core.windows.net`|
|CRL (证书吊销)  <p> Windows创建与 MAPS 的 SSL 连接以更新 CRL 时，请使用此列表。|`http://www.microsoft.com/pkiops/crl/` <p> `http://www.microsoft.com/pkiops/certs` <p> `http://crl.microsoft.com/pki/crl/products` <p> `http://www.microsoft.com/pki/certs`|
|符号存储 <p>Microsoft Defender 防病毒在修正流期间使用符号存储还原某些关键文件。|`https://msdl.microsoft.com/download/symbols`|
|通用 GDPR 客户端 <p> Windows使用此客户端发送客户端诊断数据。 <p> Microsoft Defender 防病毒《一般数据保护条例》进行产品质量和监视。|此更新使用 SSL (TCP 端口 443) 下载清单，将诊断数据上载到使用下列 DNS 终结点的 Microsoft： <p> `vortex-win.data.microsoft.com` <p> `settings-win.data.microsoft.com`|


## <a name="validate-connections-between-your-network-and-the-cloud"></a>验证网络和云之间的连接

允许列出的 URL 后，测试你是否连接到 Microsoft Defender 防病毒 云服务。 测试 URL 是否正确报告和接收信息，以确保完全受保护。

### <a name="use-the-cmdline-tool-to-validate-cloud-delivered-protection"></a>使用 cmdline 工具验证云保护

将以下参数与 Microsoft Defender 防病毒 命令行`mpcmdrun.exe`实用程序 () 验证网络能否与 Microsoft Defender 防病毒 云服务通信：

```console
"%ProgramFiles%\Windows Defender\MpCmdRun.exe" -ValidateMapsConnection
```

> [!NOTE]
> 以管理员角色打开命令提示符。 右键单击"开始"**菜单中的项**，**单击"以** 管理员角色运行"，在权限提示符下单击"是"。 此命令仅适用于 Windows 10 版本 1703 或更高版本，或 Windows 11。

有关详细信息，请参阅使用 Microsoft Defender 防病毒 [命令行mpcmdrun.exe管理命令行工具](command-line-arguments-microsoft-defender-antivirus.md)。

### <a name="attempt-to-download-a-fake-malware-file-from-microsoft"></a>尝试从 Microsoft 下载假恶意软件文件

你可以下载示例文件，Microsoft Defender 防病毒正确连接到云，将检测并阻止该文件。 访问 [https://aka.ms/ioavtest](https://aka.ms/ioavtest) 以下载文件。

> [!NOTE]
> 下载的文件不完全是恶意软件。 这是一个假文件，旨在测试你是否正确连接到云。

如果连接正确，你将看到一条警告Microsoft Defender 防病毒通知。

如果你使用的是Microsoft Edge，你还将看到一条通知消息：

:::image type="content" source="../../media/wdav-bafs-edge.png" alt-text="在 Edge 中发现恶意软件的通知Azure IoT屏幕截图。":::

如果您使用以下方法，则会出现Internet Explorer：

:::image type="content" source="../../media/wdav-bafs-ie.png" alt-text="发现恶意软件的 Microsoft Defender AV 通知。":::

#### <a name="view-the-fake-malware-detection-in-your-windows-security-app"></a>查看应用中的假恶意软件Windows 安全中心检测

1. 在任务栏上，选择"防护线"图标，**打开Windows 安全中心应用**。 或者，搜索 **"开始"** "安全 *"*。

2. 选择 **病毒&威胁防护，** 然后选择保护 **历史记录**。

3. 在" **隔离的威胁"** 部分下， **选择"查看完整历史记录** "以查看检测到的假恶意软件。

   > [!NOTE]
   > 1703 Windows 10版本之前的版本具有不同的用户界面。 请参阅[Microsoft Defender 防病毒应用中Windows 安全中心应用](microsoft-defender-security-center-antivirus.md)。

   事件Windows还将显示客户端[Windows Defender ID 1116](troubleshoot-microsoft-defender-antivirus.md)。

## <a name="see-also"></a>另请参阅

- [为 Microsoft Defender for Endpoint 配置设备代理和 Internet 连接设置](configure-proxy-internet.md)
- [使用组策略设置配置和管理Microsoft Defender 防病毒](use-group-policy-microsoft-defender-antivirus.md)
- [对 Microsoft Active Protection Services 终结点的重要更改](https://techcommunity.microsoft.com/t5/Configuration-Manager-Archive/Important-changes-to-Microsoft-Active-Protection-Service-MAPS/ba-p/274006) 