---
title: 在 Microsoft Edge 中使用 Office 365 电子数据展示导出工具
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 您必须启用 ClickOnce 支持，才能使用 Microsoft Edge 的最新版本从 "安全与合规中心" 中的内容搜索和电子数据展示下载搜索结果。
ms.openlocfilehash: 80924b124521b24ffabf1e0273802265cd715500
ms.sourcegitcommit: 01ead889086ecc7dcf5d10244bcf67c5a33c8114
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/17/2020
ms.locfileid: "42710341"
---
# <a name="use-the-office-365-ediscovery-export-tool-in-microsoft-edge"></a>在 Microsoft Edge 中使用 Office 365 电子数据展示导出工具

由于最近对 Microsoft Edge 版本所做的更改，ClickOnce 支持在默认情况下不再启用。 若要继续使用 Microsoft Office 365 电子数据展示导出工具下载内容搜索或电子数据展示搜索结果，您需要使用[Microsoft Internet Explorer](https://support.microsoft.com/help/17621/internet-explorer-downloads)或在最新版本的 microsoft Edge 中启用 ClickOnce 支持。

## <a name="enable-clickonce-support-in-microsoft-edge"></a>在 Microsoft Edge 中启用 ClickOnce 支持

1. 在 Microsoft Edge 中，转到 "edge://flags/"，**然后单击 "#edge"**。

2. 如果在下拉列表中将现有值设置为 "**默认**" 或 "**禁用**"，请将其更改为 "**启用**"。

   ![](../media/ClickOnceimage1.png)

3. 向下滚动到浏览器窗口的底部，然后单击 "**重新启动**" 以重新启动边缘。

   ![](../media/ClickOnceimage2.png)

**注意：** 组织可以使用组策略禁用 ClickOnce 支持。 若要检查是否存在 ClickOnce 支持的组织策略，请转到**edge://policy**。 下面的屏幕截图显示在整个组织中启用 ClickOnce。 如果将此策略值设置为**false**，则需要与组织中的管理员联系。

![](../media/ClickOnceimage3.png)

## <a name="install-and-run-the-ediscovery-export-tool"></a>安装和运行电子数据展示导出工具

1. 单击 "在内容搜索中导出" 的飞出页面或电子数据展示事例中的 "**下载结果**"。

   ![单击弹出页面上的 "下载结果" 以下载搜索结果](../media/ClickOnceExport1.png)

2. 系统将提示您确认启动该工具，请单击 "**打开**"。

   ![单击 "打开" 以启动电子数据展示导出工具](../media/ClickOnceimage4.png)

   如果未安装 Microsoft Office 365 电子数据展示导出工具，则系统会提示您提供安全警告， 

   ![单击 "安装" 以安装电子数据展示导出工具](../media/ClickOnceimage5.png)

3. 单击“**安装**”。 安装完成后，"导出" 工具将自动启动。

有关详细信息，请参阅下列主题：

- [导出内容搜索结果](export-search-results.md)

- [如何在 Microsoft Edge 中启用实验标志](https://microsoftedgesupport.microsoft.com/hc/articles/360034075294-How-to-enable-experiment-flags-in-Microsoft-Edge-Insider-channels)
