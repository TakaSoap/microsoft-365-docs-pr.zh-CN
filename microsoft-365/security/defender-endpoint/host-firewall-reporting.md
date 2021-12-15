---
title: 在 Microsoft Defender for Endpoint 中托管防火墙报告
description: 在门户中承载和查看Microsoft 365 Defender报告。
keywords: windows defender， 防火墙
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
audience: ITPro
ms.topic: article
author: dansimp
ms.author: dansimp
manager: dansimp
ms.technology: mde
ms.collection: m365-security-compliance
ms.custom: admindeeplinkDEFENDER
ms.openlocfilehash: b5aaad7363b42e18a0ca21e4d56d118218cec1a9
ms.sourcegitcommit: 6dcc3b039e0f0b9bae17c386f14ed2b577b453a6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/15/2021
ms.locfileid: "61531794"
---
# <a name="host-firewall-reporting-in-microsoft-defender-for-endpoint"></a>在 Microsoft Defender for Endpoint 中托管防火墙报告

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

如果你是管理员，你现在可以托管防火墙报告到 Microsoft 365 Defender[门户](https://security.microsoft.com)。 此功能使您能够从集中位置查看 Windows 10、Windows 11、Windows Server 2019 和 Windows Server 2022 防火墙报告。

## <a name="what-do-you-need-to-know-before-you-begin"></a>开始前，有必要了解什么？

- 必须运行 Windows 10 Windows 11 Server 2019 Windows或 Windows Server 2022。
- 若要将设备载入到 Microsoft Defender for Endpoint 服务，请参阅 [此处](onboard-configure.md)。
- 若要<a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender</a>开始接收数据，必须启用高级安全防火墙Windows Defender审核事件： 
  - [审核筛选平台数据包丢弃](/windows/security/threat-protection/auditing/audit-filtering-platform-packet-drop)
  - [审核筛选平台连接](/windows/security/threat-protection/auditing/audit-filtering-platform-connection)
- 使用组策略对象编辑器、本地安全策略或命令启用这些事件auditpol.exe命令。 有关详细信息，请参阅 [此处](/windows/win32/fwp/auditing-and-logging)。
  - 两个 PowerShell 命令是：
    - **auditpol /set /subcategory："Filtering Platform Packet Drop" /failure：enable**
    - **auditpol /set /subcategory："Filtering Platform Connection" /failure：enable**

## <a name="the-process"></a>过程

> [!NOTE]
> 请务必按照上述部分中的说明操作，并正确配置设备，以参与早期预览。

- 启用事件后，Microsoft 365 Defender将开始监视数据。
  - 远程 IP、远程端口、本地端口、本地 IP、计算机名称、跨入站和出站连接的进程。
- 管理员现在可以在此处Windows主机防火墙[活动](https://security.microsoft.com/firewall)。
  - 通过下载自定义报告脚本以使用自定义报告[](https://github.com/microsoft/MDATP-PowerBI-Templates/tree/master/Firewall)脚本监视防火墙活动，Windows Defender报告Power BI。
  - 可能需要 12 小时才能反映数据。

## <a name="supported-scenarios"></a>支持的方案

Ring0 Preview 期间支持以下方案。

### <a name="firewall-reporting"></a>防火墙报告

以下是防火墙报告页面的一些示例。 您将在此处找到入站、出站和应用程序活动的摘要。 可以通过访问 直接访问此页面 <https://security.microsoft.com/firewall> 。

> [!div class="mx-imgBorder"]
> !["主机防火墙报告"页。](\images\host-firewall-reporting-page.png)

也可以访问这些报告，方式为，访问位于"防火墙阻止的入站连接 (底部的) 报告安全报告  >    >  **设备**"部分。

### <a name="from-computers-with-a-blocked-connection-to-device"></a>从"连接被阻止的计算机"到设备

卡片支持交互式对象。 可以通过单击设备名称深入了解设备的活动，这将启动新选项卡中的 Microsoft 365 Defender 门户，并直接进入"设备时间线 **"选项卡。**

> [!div class="mx-imgBorder"]
> ![连接被阻止的计算机。](\images\firewall-reporting-blocked-connection.png)

你现在可以选择时间线 **选项卡** ，这将提供与该设备关联的事件列表。

单击 **查看窗格右上角** 的"筛选器"按钮后，选择您想要的事件类型。 在这种情况下，请选择 **"防火墙事件"，** 窗格将筛选为"防火墙事件"。

> [!div class="mx-imgBorder"]
> !["筛选器"按钮。](\images\firewall-reporting-filters-button.png)

### <a name="drill-into-advanced-hunting-preview-refresh"></a>深入了解高级搜寻 (预览刷新) 

防火墙报告支持通过单击"打开高级搜寻"按钮直接从卡钻取到高级 **搜寻**。 查询将预填充。

> [!div class="mx-imgBorder"]
> ![打开高级搜寻按钮。](\images\firewall-reporting-advanced-hunting.png)

现在可以执行查询，并且可以浏览过去 30 天内的所有其他相关防火墙事件。

对于其他报告或自定义更改，可以将查询导出到Power BI进一步分析。 通过下载自定义报告脚本以使用自定义报告[](https://github.com/microsoft/MDATP-PowerBI-Templates/tree/master/Firewall)脚本监视防火墙活动，Windows Defender自定义Power BI。
