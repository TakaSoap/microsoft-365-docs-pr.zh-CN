---
title: 在 Microsoft Defender for Endpoint 中托管防火墙报告
description: 在 Microsoft 365 安全中心托管和查看防火墙报告。
keywords: windows defender， 防火墙
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
audience: ITPro
ms.topic: article
author: dansimp
ms.author: dansimp
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 23986024db239da6c8a69792ff8abbd01adc54d87354146d7c3847ee3a9dd539
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "53800266"
---
# <a name="host-firewall-reporting-in-microsoft-defender-for-endpoint"></a>在 Microsoft Defender for Endpoint 中托管防火墙报告

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

如果你是管理员，你现在可以托管向 [Microsoft 365](https://security.microsoft.com)安全中心报告的防火墙。 此功能使你能够在集中的位置查看 Windows 10 和 Windows Server 2019 防火墙报告。 

## <a name="what-do-you-need-to-know-before-you-begin"></a>开始前，有必要了解什么？ 

- 必须运行 Windows 10 或 Windows Server 2019。
- 若要将设备载入到 Microsoft Defender for Endpoint 服务，请参阅 [此处](onboard-configure.md)。 
- 若要让 Microsoft 365 安全中心开始接收数据，必须为高级安全防火墙Windows Defender审核事件： 
    - [审核筛选平台数据包丢弃](/windows/security/threat-protection/auditing/audit-filtering-platform-packet-drop)
    - [审核筛选平台连接](/windows/security/threat-protection/auditing/audit-filtering-platform-connection) 
- 使用组策略对象编辑器、本地安全策略或命令启用这些事件auditpol.exe命令。 有关详细信息，请参阅 [此处](/windows/win32/fwp/auditing-and-logging)。 
    - 两个 PowerShell 命令是：
        - **auditpol /set /subcategory："Filtering Platform Packet Drop" /failure：enable** 
        - **auditpol /set /subcategory："Filtering Platform Connection" /failure：enable** 

## <a name="the-process"></a>过程
> [!NOTE]
> 请务必按照上述部分中的说明操作，并正确配置设备，以参与早期预览。

- 启用事件后，Microsoft 365 安全中心将开始监视数据。
    - 远程 IP、远程端口、本地端口、本地 IP、计算机名称、跨入站和出站连接的进程。
- 管理员现在可以在此处查看 Windows 主机防火墙 [活动](https://security.microsoft.com/firewall)。
    - 通过下载自定义报告脚本来监视使用[](https://github.com/microsoft/MDATP-PowerBI-Templates/tree/master/Firewall)Power BI 的防火墙活动，Windows Defender报告功能。 
    - 可能需要 12 小时才能反映数据。

## <a name="supported-scenarios"></a>支持的方案
Ring0 Preview 期间支持以下方案。 

### <a name="firewall-reporting-in-security-center"></a>安全中心中的防火墙报告

以下是防火墙报告页面的一些示例。 您将在此处找到入站、出站和应用程序活动的摘要。 可以通过访问 直接访问此页面 https://security.microsoft.com/firewall 。 

> [!div class="mx-imgBorder"]
> ![主机防火墙报告页面](\images\host-firewall-reporting-page.png)

也可以访问这些报告，方式为访问位于"防火墙阻止的入站连接 (底部的) 报告安全报告  >    >  **设备**"部分。

### <a name="from-computers-with-a-blocked-connection-to-device"></a>从"连接被阻止的计算机"到设备

卡片支持交互式对象。 可以通过单击设备名称（将在新选项卡中启动）来深入了解设备的活动，并直接进入"设备 https://securitycenter.microsoft.com **时间线** "选项卡。 

> [!div class="mx-imgBorder"]
> ![连接被阻止的计算机](\images\firewall-reporting-blocked-connection.png)

你现在可以选择时间线 **选项卡** ，这将提供与该设备关联的事件列表。 

单击 **查看窗格右上角** 的"筛选器"按钮后，选择您想要的事件类型。 在这种情况下，请选择 **"防火墙事件"，** 窗格将筛选为"防火墙事件"。 

> [!div class="mx-imgBorder"]
> !["筛选器"按钮](\images\firewall-reporting-filters-button.png)

### <a name="drill-into-advanced-hunting-preview-refresh"></a>深入了解高级搜寻 (预览刷新) 

防火墙报告支持通过单击"打开高级搜寻"按钮直接从卡钻取到高级 **搜寻**。 查询将预填充。 

> [!div class="mx-imgBorder"]
> ![打开高级搜寻按钮](\images\firewall-reporting-advanced-hunting.png)

现在可以执行查询，并且可以浏览过去 30 天内的所有其他相关防火墙事件。 

对于其他报告或自定义更改，可以将查询导出到 Power BI 中以进一步分析。 通过下载自定义报告脚本以使用 Power [](https://github.com/microsoft/MDATP-PowerBI-Templates/tree/master/Firewall) BI 监视防火墙活动，Windows Defender实现自定义报告。 

 