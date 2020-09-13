---
title: 在 Microsoft Edge 中使用电子数据展示导出工具
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
description: 您必须启用 ClickOnce 支持，才能使用 Microsoft Edge 的最新版本从 "安全与合规中心" 中的内容搜索和电子数据展示下载搜索结果。
ms.openlocfilehash: 60f42d2884c56aaff40bc0a6a979e99698a3cd2e
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/12/2020
ms.locfileid: "47546816"
---
# <a name="use-the-ediscovery-export-tool-in-microsoft-edge"></a><span data-ttu-id="bfb47-103">在 Microsoft Edge 中使用电子数据展示导出工具</span><span class="sxs-lookup"><span data-stu-id="bfb47-103">Use the eDiscovery Export Tool in Microsoft Edge</span></span>

<span data-ttu-id="bfb47-104">由于最近对 Microsoft Edge 版本所做的更改，ClickOnce 支持在默认情况下不再启用。</span><span class="sxs-lookup"><span data-stu-id="bfb47-104">As a result of recent changes to the newest version of Microsoft Edge, ClickOnce support is no longer enabled by default.</span></span> <span data-ttu-id="bfb47-105">若要继续使用电子数据展示导出工具下载内容搜索或电子数据展示搜索结果，您需要使用 [Microsoft Internet Explorer](https://support.microsoft.com/help/17621/internet-explorer-downloads) 或在最新版本的 microsoft Edge 中启用 ClickOnce 支持。</span><span class="sxs-lookup"><span data-stu-id="bfb47-105">To continue using the eDiscovery Export Tool to download Content Search or eDiscovery search results, you either need to use [Microsoft Internet Explorer](https://support.microsoft.com/help/17621/internet-explorer-downloads) or enable ClickOnce support in the newest version of Microsoft Edge.</span></span>

## <a name="enable-clickonce-support-in-microsoft-edge"></a><span data-ttu-id="bfb47-106">在 Microsoft Edge 中启用 ClickOnce 支持</span><span class="sxs-lookup"><span data-stu-id="bfb47-106">Enable ClickOnce support in Microsoft Edge</span></span>

1. <span data-ttu-id="bfb47-107">在 Microsoft Edge 中，转到 "edge://flags/"， **然后单击 "#edge"**。</span><span class="sxs-lookup"><span data-stu-id="bfb47-107">In Microsoft Edge, go to **edge://flags/#edge-click-once**.</span></span>

2. <span data-ttu-id="bfb47-108">如果在下拉列表中将现有值设置为 " **默认** " 或 " **禁用** "，请将其更改为 " **启用**"。</span><span class="sxs-lookup"><span data-stu-id="bfb47-108">If the existing value is set to **Default** or **Disabled** in the dropdown list, change it to **Enabled**.</span></span>

   ![从下拉列表中选择 "启用"](../media/ClickOnceimage1.png)

3. <span data-ttu-id="bfb47-110">向下滚动到浏览器窗口的底部，然后单击 " **重新启动** " 以重新启动边缘。</span><span class="sxs-lookup"><span data-stu-id="bfb47-110">Scroll down to the bottom of the browser window and click **Restart** to restart Edge.</span></span>

   ![单击 "重新启动"](../media/ClickOnceimage2.png)

<span data-ttu-id="bfb47-112">**注意：** 组织可以使用组策略禁用 ClickOnce 支持。</span><span class="sxs-lookup"><span data-stu-id="bfb47-112">**Note:** Organizations can use Group Policy to disable ClickOnce support.</span></span> <span data-ttu-id="bfb47-113">若要检查是否存在 ClickOnce 支持的组织策略，请转到 **edge://policy**。</span><span class="sxs-lookup"><span data-stu-id="bfb47-113">To check if there is an organizational policy for ClickOnce support, go to **edge://policy**.</span></span> <span data-ttu-id="bfb47-114">下面的屏幕截图显示在整个组织中启用 ClickOnce。</span><span class="sxs-lookup"><span data-stu-id="bfb47-114">The following screenshot shows that ClickOnce is enabled across the entire organization.</span></span> <span data-ttu-id="bfb47-115">如果将此策略值设置为 **false**，则需要与组织中的管理员联系。</span><span class="sxs-lookup"><span data-stu-id="bfb47-115">If this policy value is set to **false**, you will need to contact an admin in your organization.</span></span>

![边缘组织策略列表](../media/ClickOnceimage3.png)

## <a name="install-and-run-the-ediscovery-export-tool"></a><span data-ttu-id="bfb47-117">安装和运行电子数据展示导出工具</span><span class="sxs-lookup"><span data-stu-id="bfb47-117">Install and run the eDiscovery Export Tool</span></span>

1. <span data-ttu-id="bfb47-118">单击 "在内容搜索中导出" 的飞出页面或电子数据展示事例中的 " **下载结果** "。</span><span class="sxs-lookup"><span data-stu-id="bfb47-118">Click **Download results** on the flyout page of an export in Content Search or an eDiscovery case.</span></span>

   ![单击弹出页面上的 "下载结果" 以下载搜索结果](../media/ClickOnceExport1.png)

2. <span data-ttu-id="bfb47-120">系统将提示您确认启动该工具，请单击 " **打开**"。</span><span class="sxs-lookup"><span data-stu-id="bfb47-120">You will be prompted with a confirmation to launch the tool, Click **Open**.</span></span>

   ![单击 "打开" 以启动电子数据展示导出工具](../media/ClickOnceimage4.png)

   <span data-ttu-id="bfb47-122">如果未安装电子数据展示导出工具，则系统会提示您提供安全警告，</span><span class="sxs-lookup"><span data-stu-id="bfb47-122">If the eDiscovery Export Tool isn't installed, you will be prompted with a Security Warning,</span></span> 

   ![单击 "安装" 以安装电子数据展示导出工具](../media/ClickOnceimage5.png)

3. <span data-ttu-id="bfb47-124">单击“**安装**”。</span><span class="sxs-lookup"><span data-stu-id="bfb47-124">Click **Install**.</span></span> <span data-ttu-id="bfb47-125">安装完成后，"导出" 工具将自动启动。</span><span class="sxs-lookup"><span data-stu-id="bfb47-125">After it's installed, the export tool will launch automatically.</span></span>

<span data-ttu-id="bfb47-126">有关详细信息，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="bfb47-126">For more information, see the following topics:</span></span>

- [<span data-ttu-id="bfb47-127">导出内容搜索结果</span><span class="sxs-lookup"><span data-stu-id="bfb47-127">Export Content Search results</span></span>](export-search-results.md)

- [<span data-ttu-id="bfb47-128">如何在 Microsoft Edge 中启用实验标志</span><span class="sxs-lookup"><span data-stu-id="bfb47-128">How to enable experiment flags in Microsoft Edge</span></span>](https://microsoftedgesupport.microsoft.com/hc/articles/360034075294-How-to-enable-experiment-flags-in-Microsoft-Edge-Insider-channels)
