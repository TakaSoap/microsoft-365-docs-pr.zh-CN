---
title: 步骤 4：计划 URL 和 IP 地址更改
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/05/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: ''
ms.openlocfilehash: 626d0e242c549fb16880710bbca31db0bdee9029
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32291321"
---
# <a name="step-4-plan-for-url-and-ip-address-changes"></a><span data-ttu-id="dd02b-102">步骤 4：计划 URL 和 IP 地址更改</span><span class="sxs-lookup"><span data-stu-id="dd02b-102">Step 4: Plan for URL and IP address changes</span></span>

<span data-ttu-id="dd02b-103">\*\* 此步骤是可选的，适用于 Microsoft 365 企业版的 E3 和 E5 版本</span><span class="sxs-lookup"><span data-stu-id="dd02b-103">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/networking_icon-small.png)

>[!Note]
><span data-ttu-id="dd02b-p101">此步骤需要完成[步骤 3](networking-configure-proxies-firewalls.md)。如果尚未完成步骤 3，请跳到[步骤 5](networking-optimize-tcp-performance.md)。</span><span class="sxs-lookup"><span data-stu-id="dd02b-p101">This step requires [Step 3](networking-configure-proxies-firewalls.md). If you have not done Step 3, you can skip to [Step 5](networking-optimize-tcp-performance.md).</span></span>
>

<span data-ttu-id="dd02b-p102">全局 Microsoft 365 网络所使用的 URL 和 IP 地址会随时间而更改，因此，请务必要计划这些终结点的更新。例如，可能需要针对以下情况重新配置安全外围设备：</span><span class="sxs-lookup"><span data-stu-id="dd02b-p102">The URLs and IP addresses used by the global Microsoft 365 network change over time, so it’s important to plan for updates to these endpoints. For example, you may need to reconfigure your security perimeter devices with:</span></span>

- <span data-ttu-id="dd02b-108">需要不受阻碍地进行处理的新服务的新 URL</span><span class="sxs-lookup"><span data-stu-id="dd02b-108">New URLs for new services that will need unhindered processing</span></span>
- <span data-ttu-id="dd02b-109">针对已弃用服务删除的 URL</span><span class="sxs-lookup"><span data-stu-id="dd02b-109">Removed URLs for discontinued services</span></span>
- <span data-ttu-id="dd02b-110">针对 Internet 上的新 Microsoft 网络位置和服务器的新 IP 地址范围</span><span class="sxs-lookup"><span data-stu-id="dd02b-110">New IP address ranges for new Microsoft network locations and servers on the Internet</span></span> 
- <span data-ttu-id="dd02b-111">针对不同服务的 IP 地址范围中的更改</span><span class="sxs-lookup"><span data-stu-id="dd02b-111">Changes in IP address ranges for the different services</span></span>

<span data-ttu-id="dd02b-112">有关针对终结点中的更改建立实施计划的详细信息（包括通知更改），请参阅[管理 Office 365 终结点集成](https://support.office.com/article/Managing-Office-365-endpoints-99cab9d4-ef59-4207-9f2b-3728eb46bf9a?ui=en-US#ID0EABAAA=2._Proxies&ID0EAEAAA=3._Integration)和[管理 Office 365 终结点代理](https://support.office.com/article/Managing-Office-365-endpoints-99cab9d4-ef59-4207-9f2b-3728eb46bf9a#ID0EABAAA=2._Proxies&ID0EAEAAA=2._Proxies)。</span><span class="sxs-lookup"><span data-stu-id="dd02b-112">For more information about establishing an implementation plan for changes in endpoints, which includes being notified of changes, see [Managing Office 365 endpoints-Integration](https://support.office.com/article/Managing-Office-365-endpoints-99cab9d4-ef59-4207-9f2b-3728eb46bf9a?ui=en-US#ID0EABAAA=2._Proxies&ID0EAEAAA=3._Integration) and [Managing Office 365 endpoints-Proxies](https://support.office.com/article/Managing-Office-365-endpoints-99cab9d4-ef59-4207-9f2b-3728eb46bf9a#ID0EABAAA=2._Proxies&ID0EAEAAA=2._Proxies).</span></span>

<span data-ttu-id="dd02b-113">作为临时检查点，请查看对应于此步骤的[退出条件](networking-exit-criteria.md#crit-networking-step4)。</span><span class="sxs-lookup"><span data-stu-id="dd02b-113">As an interim checkpoint, you can see the [exit criteria](networking-exit-criteria.md#crit-networking-step4) for this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="dd02b-114">后续步骤</span><span class="sxs-lookup"><span data-stu-id="dd02b-114">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step5.png)|[<span data-ttu-id="dd02b-115">优化客户端和 Office 365 服务性能</span><span class="sxs-lookup"><span data-stu-id="dd02b-115">Optimize client and Office 365 service performance</span></span>](networking-optimize-tcp-performance.md)|
