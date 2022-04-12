---
title: 配置和验证 Microsoft Defender 防病毒软件网络连接
description: 配置并测试与Microsoft Defender 防病毒云保护服务的连接。
keywords: 防病毒， Microsoft Defender 防病毒， 反恶意软件， 安全， defender， 云， 侵略性， 保护级别
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
ms.openlocfilehash: 70360ac3b9ade0e6039239fe257d83c7ba3a2db0
ms.sourcegitcommit: 4f56b4b034267b28c7dd165e78ecfb4b5390087d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/12/2022
ms.locfileid: "64787594"
---
# <a name="configure-and-validate-microsoft-defender-antivirus-network-connections"></a>配置和验证 Microsoft Defender 防病毒软件网络连接

**适用于：**

- [Microsoft Defender for Endpoint 计划 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- Microsoft Defender 防病毒

**平台**
- Windows

为确保Microsoft Defender 防病毒云提供的保护正常工作，安全团队必须将网络配置为允许终结点与某些 Microsoft 服务器之间的连接。 本文列出了必须允许使用防火墙规则的连接。 它还提供有关验证连接的说明。 正确配置保护可确保从云提供的保护服务获得最佳价值。

> [!IMPORTANT]
> 本文包含有关仅为Microsoft Defender 防病毒配置网络连接的信息。 如果使用的Microsoft Defender for Endpoint (包括Microsoft Defender 防病毒) ，请参阅[为 Defender for Endpoint 配置设备代理和 Internet 连接设置](configure-proxy-internet.md)。


> [!NOTE]
> 位于 demo.wd.microsoft.com 处的 Defender for Endpoint 演示网站已弃用，并将在未来删除。

## <a name="allow-connections-to-the-microsoft-defender-antivirus-cloud-service"></a>允许连接到Microsoft Defender 防病毒云服务

Microsoft Defender 防病毒云服务为终结点提供快速且强大的保护。 启用云提供的保护服务是可选的。 建议Microsoft Defender 防病毒云服务，因为它对终结点和网络上的恶意软件提供重要的保护。 有关详细信息，请参阅启[用云提供的保护](enable-cloud-protection-microsoft-defender-antivirus.md)，以便在Windows 安全中心应用中使用Intune、Microsoft Endpoint Configuration Manager、组策略、PowerShell cmdlet 或单个客户端启用服务。

启用服务后，需要配置网络或防火墙以允许网络与终结点之间的连接。 由于保护是云服务，因此计算机必须有权访问 Internet 并访问 Microsoft 云服务。 不要从任何类型的网络检查中排除 URL `*.blob.core.windows.net` 。

> [!NOTE]
> Microsoft Defender 防病毒云服务为网络和终结点提供更新的保护。 不应将云服务视为仅针对存储在云中的文件的保护;相反，云服务使用分布式资源和机器学习以比传统安全智能更新更快的速度为终结点提供保护。

## <a name="services-and-urls"></a>服务和 URL

本部分中的表列出了服务及其关联的网站地址 (URL) 。

确保没有拒绝访问这些 URL 的防火墙或网络筛选规则。 否则，必须专门为这些 URL 创建允许规则 (排除 URL `*.blob.core.windows.net`) 。 下表中的 URL 使用端口 443 进行通信。

<br/><br/>

|服务和说明|URL|
|---|---|
|Microsoft Defender 防病毒云提供的保护服务称为MICROSOFT ACTIVE PROTECTION SERVICE (MAPS) 。<p> Microsoft Defender 防病毒使用 MAPS 服务提供云传递的保护。|`*.wdcp.microsoft.com` <p> `*.wdcpalt.microsoft.com` <p> `*.wd.microsoft.com`|
|MICROSOFT Update Service (MU) 和 Windows 更新 SERVICE (WU)  <p>这些服务将允许安全智能和产品更新。|`*.update.microsoft.com` <p> `*.delivery.mp.microsoft.com`<p> `*.windowsupdate.com` <p> 有关详细信息，请参阅[Windows 更新的连接终结点](/windows/privacy/manage-windows-1709-endpoints#windows-update)|
|安全智能更新 ADL)  (备用下载位置<p>这是Microsoft Defender 防病毒安全智能更新的备用位置，如果安装的安全智能已过期 () 后 7 天或更多天。|`*.download.microsoft.com` <p> `*.download.windowsupdate.com`<p>  `go.microsoft.com`<p> `https://fe3cr.delivery.mp.microsoft.com/ClientWebService/client.asmx`|
|恶意软件提交存储 <p>这是通过提交表单或自动示例提交提交提交到 Microsoft 的文件的上传位置。|`ussus1eastprod.blob.core.windows.net` <p> `ussus2eastprod.blob.core.windows.net` <p> `ussus3eastprod.blob.core.windows.net` <p> `ussus4eastprod.blob.core.windows.net` <p> `wsus1eastprod.blob.core.windows.net` <p> `wsus2eastprod.blob.core.windows.net` <p> `ussus1westprod.blob.core.windows.net` <p> `ussus2westprod.blob.core.windows.net` <p> `ussus3westprod.blob.core.windows.net` <p> `ussus4westprod.blob.core.windows.net` <p> `wsus1westprod.blob.core.windows.net` <p> `wsus2westprod.blob.core.windows.net` <p> `usseu1northprod.blob.core.windows.net` <p> `wseu1northprod.blob.core.windows.net` <p> `usseu1westprod.blob.core.windows.net` <p> `wseu1westprod.blob.core.windows.net` <p> `ussuk1southprod.blob.core.windows.net` <p> `wsuk1southprod.blob.core.windows.net` <p> `ussuk1westprod.blob.core.windows.net` <p> `wsuk1westprod.blob.core.windows.net`|
|CRL)  (证书吊销列表 <p> Windows在创建与 MAPS 的 SSL 连接以更新 CRL 时使用此列表。|`http://www.microsoft.com/pkiops/crl/` <p> `http://www.microsoft.com/pkiops/certs` <p> `http://crl.microsoft.com/pki/crl/products` <p> `http://www.microsoft.com/pki/certs`|
|符号存储 <p>Microsoft Defender 防病毒使用符号存储在修正流期间还原某些关键文件。|`https://msdl.microsoft.com/download/symbols`|
|通用 GDPR 客户端 <p> Windows使用此客户端发送客户端诊断数据。 <p> Microsoft Defender 防病毒将一般数据保护条例用于产品质量和监视目的。|更新使用 SSL (TCP 端口 443) 下载清单并将诊断数据上传到使用以下 DNS 终结点的 Microsoft： <p> `vortex-win.data.microsoft.com` <p> `settings-win.data.microsoft.com`|


## <a name="validate-connections-between-your-network-and-the-cloud"></a>验证网络与云之间的连接

允许列出 URL 后，测试是否已连接到Microsoft Defender 防病毒云服务。 测试 URL 是否正确报告和接收信息，以确保你受到完全保护。

### <a name="use-the-cmdline-tool-to-validate-cloud-delivered-protection"></a>使用 cmdline 工具验证云提供的保护

将以下参数与Microsoft Defender 防病毒命令行实用工具 (`mpcmdrun.exe`) 配合使用，验证网络是否可以与Microsoft Defender 防病毒云服务通信：

```console
"%ProgramFiles%\Windows Defender\MpCmdRun.exe" -ValidateMapsConnection
```

> [!NOTE]
> 以管理员身份打开命令提示符。 右键单击 **“开始”** 菜单中的项，单击 **“以管理员身份运行** ”，然后在权限提示处单击 **“是** ”。 此命令仅适用于Windows 10、版本 1703 或更高版本或Windows 11。

有关详细信息，请参阅[使用mpcmdrun.exe命令行工具管理Microsoft Defender 防病毒](command-line-arguments-microsoft-defender-antivirus.md)。

### <a name="attempt-to-download-a-fake-malware-file-from-microsoft"></a>尝试从 Microsoft 下载假恶意软件文件

如果已正确连接到云，可以下载Microsoft Defender 防病毒检测和阻止的示例文件。 访问 [https://aka.ms/ioavtest](https://aka.ms/ioavtest) 以下载文件。

> [!NOTE]
> 下载的文件不完全是恶意软件。 这是一个假文件，旨在测试是否正确连接到云。

如果连接正确，则会看到警告Microsoft Defender 防病毒通知。

如果使用的是Microsoft Edge，你还将看到一条通知消息：

:::image type="content" source="../../media/wdav-bafs-edge.png" alt-text="在 Edge 中发现恶意软件的通知" lightbox="../../media/wdav-bafs-edge.png":::

如果使用的是 Internet Explorer，则会出现类似的消息：

:::image type="content" source="../../media/wdav-bafs-ie.png" alt-text="发现恶意软件的 Microsoft Defender AV 通知" lightbox="../../media/wdav-bafs-ie.png":::

#### <a name="view-the-fake-malware-detection-in-your-windows-security-app"></a>在Windows 安全中心应用中查看假恶意软件检测

1. 在任务栏上，选择“盾牌”图标，打开 **Windows 安全中心** 应用。 或者，搜索 **“开始** 获取 *安全性*”。

2. 选择 **病毒&威胁防护**，然后选择 **“保护历史记录**”。

3. 在“ **隔离威胁”** 部分下，选择 **“查看完整历史记录** ”以查看检测到的假恶意软件。

   > [!NOTE]
   > 版本 1703 之前的Windows 10版本具有不同的用户界面。 请参阅[Windows 安全中心应用中的Microsoft Defender 防病毒](microsoft-defender-security-center-antivirus.md)。

   Windows事件日志还将显示[Windows Defender客户端事件 ID 1116](troubleshoot-microsoft-defender-antivirus.md)。

    > [!TIP]
    > 如果要查找其他平台的防病毒相关信息，请参阅：
    > - [在 macOS 上设置Microsoft Defender for Endpoint首选项](mac-preferences.md)
    > - [Mac 上的 Microsoft Defender for Endpoint](microsoft-defender-endpoint-mac.md)
    > - [适用于Intune的Microsoft Defender 防病毒的 macOS 防病毒策略设置](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
    > - [在 Linux 上设置Microsoft Defender for Endpoint首选项](linux-preferences.md)
    > - [Microsoft Defender for Endpoint on Linux](microsoft-defender-endpoint-linux.md)
    > - [在 Android 功能上配置 Defender for Endpoint](android-configure.md)
    > - [在 iOS 功能上配置Microsoft Defender for Endpoint](ios-configure-features.md)


## <a name="see-also"></a>另请参阅

- [为Microsoft Defender for Endpoint配置设备代理和 Internet 连接设置](configure-proxy-internet.md)
- [使用组策略设置配置和管理Microsoft Defender 防病毒](use-group-policy-microsoft-defender-antivirus.md)
- [对 Microsoft Active Protection Services 终结点的重要更改](https://techcommunity.microsoft.com/t5/Configuration-Manager-Archive/Important-changes-to-Microsoft-Active-Protection-Service-MAPS/ba-p/274006) 