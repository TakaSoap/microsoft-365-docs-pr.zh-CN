---
title: 在 Microsoft Edge 中使用 Office 365 电子数据展示导出工具
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ROBOTS: NOINDEX, NOFOLLOW
description: 您必须启用 ClickOnce 支持，才能使用 Microsoft Edge 在安全与合规中心中导出内容搜索和电子数据展示中的搜索结果。
ms.openlocfilehash: f3e0442fe349aa3364594e07873b229f3205fb5e
ms.sourcegitcommit: d656fd58e5491cfb7fee16b55dc7a58904ed128d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/06/2019
ms.locfileid: "39891123"
---
# <a name="use-the-office-365-ediscovery-export-tool-in-microsoft-edge"></a>在 Microsoft Edge 中使用 Office 365 电子数据展示导出工具

由于对 Microsoft Edge 的最近更改的结果，默认情况下 ClickOnce 支持不再启用。 若要继续使用 Microsoft Office 365 电子数据展示导出工具下载内容搜索或电子数据展示搜索结果，您需要使用[Microsoft Internet Explorer](https://support.microsoft.com/help/17621/internet-explorer-downloads)或在 microsoft Edge 中启用 ClickOnce 支持。

## <a name="how-to-enable-clickonce-support-in-microsoft-edge"></a>如何在 Microsoft Edge 中启用 ClickOnce 支持

1. 在 Microsoft Edge 中，导航到 "edge://flags/"，**然后单击 "#edge"**。

2. 如果在下拉列表中将现有值设置为 "**默认**" 或 "**禁用**"，请将其更改为 "**启用**"。
    
   ![](media/ClickOnceimage1.png)

3. 向下滚动到浏览器窗口的底部，然后单击 "**重新启动**" 以重新启动边缘。

   ![](media/ClickOnceimage2.png)

**注意：** 组织可以使用组策略禁用 ClickOnce 支持。 若要检查是否存在 ClickOnce 支持的组织策略，请导航到**edge://policy**。 下面的屏幕截图显示在整个组织中启用 ClickOnce。 如果将此策略值设置为**false**，则需要与组织中的管理员联系。

![](media/ClickOnceimage3.png)

## <a name="install-and-run-the-office-365-ediscovery-export-tool"></a>安装和运行 Office 365 电子数据展示导出工具

1. 单击 "在内容搜索中导出" 的飞出页面或电子数据展示事例中的 "**下载结果**"。

   ![单击弹出页面上的 "下载结果" 以下载搜索结果](media/ClickOnceExport1.png)

2. 系统将提示您确认启动该工具，请单击 "**打开**"。

   ![单击 "打开" 以启动电子数据展示导出工具](media/ClickOnceimage4.png)

   如果未安装 Microsoft Office 365 电子数据展示导出工具，则系统会提示您提供安全警告， 

   ![单击 "安装" 以安装电子数据展示导出工具](media/ClickOnceimage5.png)

3. 单击“**安装**”。 安装完成后，"导出" 工具将自动启动。

有关详细信息，请参阅下列主题：

- [导出内容搜索结果](export-search-results.md)

- [如何在 Microsoft Edge 中启用实验标志](https://microsoftedgesupport.microsoft.com/hc/articles/360034075294-How-to-enable-experiment-flags-in-Microsoft-Edge-Insider-channels)
