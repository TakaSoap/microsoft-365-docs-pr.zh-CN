---
title: 使用电子数据展示导出工具Microsoft Edge
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 必须启用ClickOnce支持，才能使用最新版本的 Microsoft Edge 从安全与合规中心的内容搜索和电子数据展示下载搜索结果。
ms.openlocfilehash: bd42ebffce326e4abe4943ff4187fc2bd960ff65
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/12/2021
ms.locfileid: "59169686"
---
# <a name="use-the-ediscovery-export-tool-in-microsoft-edge"></a>使用电子数据展示导出工具Microsoft Edge

由于最近对最新版本的 Microsoft Edge，ClickOnce不再启用支持。 若要继续使用电子数据展示导出工具下载内容搜索或电子数据展示搜索结果，您需要使用[Microsoft Internet Explorer](https://support.microsoft.com/help/17621/internet-explorer-downloads)或在最新版本的 Microsoft Edge 中启用 ClickOnce 支持。

## <a name="enable-clickonce-support-in-microsoft-edge"></a>在ClickOnce中启用Microsoft Edge

1. 在Microsoft Edge中，转到 **"edge://flags/#edge-click-once"。**

2. 如果下拉列表中现有值设置为 **"默认**"或"已禁用"，请更改为"**已启用"。**

   ![从下拉列表中选择已启用。](../media/ClickOnceimage1.png)

3. 向下滚动到浏览器窗口底部，然后单击重启 **以** 重新启动 Edge。

   ![单击"重新启动"。](../media/ClickOnceimage2.png)

**注意：** 组织可以使用组策略禁用ClickOnce支持。 若要检查是否有组织策略支持ClickOnce，请转到 **"edge://policy"。** 以下屏幕截图显示ClickOnce整个组织启用此功能。 如果此策略值设置为 **false，** 你将需要联系你组织的管理员。

![边缘组织策略列表。](../media/ClickOnceimage3.png)

## <a name="install-and-run-the-ediscovery-export-tool"></a>安装和运行电子数据展示导出工具

1. 单击 **内容搜索** 或电子数据展示案例中导出的飞出页面上的"下载结果"。

   ![单击飞出页面上的"下载结果"以下载搜索结果。](../media/ClickOnceExport1.png)

2. 系统将提示你确认启动该工具，单击"打开 **"。**

   ![单击"打开"以启动电子数据展示导出工具。](../media/ClickOnceimage4.png)

   如果未安装电子数据展示导出工具，系统将提示你出现安全警告， 

   ![单击"安装"以安装电子数据展示导出工具。](../media/ClickOnceimage5.png)

3. 单击“**安装**”。 安装后，导出工具将自动启动。

有关详细信息，请参阅下列主题：

- [导出内容搜索结果](export-search-results.md)

- [如何在实验中启用实验Microsoft Edge](https://microsoftedgesupport.microsoft.com/hc/articles/360034075294-How-to-enable-experiment-flags-in-Microsoft-Edge-Insider-channels)
