---
title: 步骤 5：优化客户端和 Office 365 服务性能
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/13/2018
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: 配置 TCP 设置和 Office 365 服务以提高性能。
ms.openlocfilehash: 9e786b36d7a2afccc3b9112b815cd42a40317c15
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/15/2019
ms.locfileid: "34073182"
---
# <a name="step-5-optimize-client-and-office-365-service-performance"></a><span data-ttu-id="84c39-103">步骤 5：优化客户端和 Office 365 服务性能</span><span class="sxs-lookup"><span data-stu-id="84c39-103">Step 5: Optimize client and Office 365 service performance</span></span>

<span data-ttu-id="84c39-104">\*\* 此步骤是可选的，适用于 Microsoft 365 企业版的 E3 和 E5 版本</span><span class="sxs-lookup"><span data-stu-id="84c39-104">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/networking_icon-small.png)

<span data-ttu-id="84c39-105">你可以微调传输控制协议 (TCP) 在客户端设备和 Office 365 服务之间的工作方式，以提高性能。</span><span class="sxs-lookup"><span data-stu-id="84c39-105">You can increase performance by fine tuning the way that the Transmission Control Protocol (TCP) works between client devices and Office 365 services.</span></span>

<span data-ttu-id="84c39-106">对于客户端设备，可以在客户端设备上更改以下 TCP 设置以优化 TCP 性能：</span><span class="sxs-lookup"><span data-stu-id="84c39-106">For client devices, you can change the following TCP settings on client devices to optimize TCP performance:</span></span>

- <span data-ttu-id="84c39-107">[TCP 窗口缩放](https://blogs.technet.microsoft.com/onthewire/2014/03/28/ensuring-your-office-365-network-connection-isnt-throttled-by-your-proxy/)，以使客户端设备在要求确认前发送更多数据</span><span class="sxs-lookup"><span data-stu-id="84c39-107">[TCP window scaling](https://blogs.technet.microsoft.com/onthewire/2014/03/28/ensuring-your-office-365-network-connection-isnt-throttled-by-your-proxy/), so your client device can send more data before requiring an acknowledgement</span></span>
- <span data-ttu-id="84c39-108">[TCP 空闲时间](https://blogs.technet.microsoft.com/onthewire/2014/03/04/network-perimeters-tcp-idle-session-settings-for-outlook-on-office-365/)，以使客户端设备更高效地处理打开的连接</span><span class="sxs-lookup"><span data-stu-id="84c39-108">[TCP idle time](https://blogs.technet.microsoft.com/onthewire/2014/03/04/network-perimeters-tcp-idle-session-settings-for-outlook-on-office-365/), so your client device can handle open connections more efficiently</span></span>
- <span data-ttu-id="84c39-109">[TCP 最大段大小](https://blogs.technet.microsoft.com/onthewire/2014/06/27/checking-your-tcp-packets-are-pulling-their-weight-tcp-max-segment-size-or-mss/)，以使客户端设备在数据包中发送数据的最大块</span><span class="sxs-lookup"><span data-stu-id="84c39-109">[TCP maximum segment size](https://blogs.technet.microsoft.com/onthewire/2014/06/27/checking-your-tcp-packets-are-pulling-their-weight-tcp-max-segment-size-or-mss/), so your client device can send the largest blocks of data in a packet</span></span>
- <span data-ttu-id="84c39-110">[TCP 选择性确认](https://blogs.technet.microsoft.com/onthewire/2014/06/27/ensuring-your-tcp-stack-isnt-throwing-data-away/)，以使客户端设备更高效地确认接收的数据</span><span class="sxs-lookup"><span data-stu-id="84c39-110">[TCP selective acknowledgements](https://blogs.technet.microsoft.com/onthewire/2014/06/27/ensuring-your-tcp-stack-isnt-throwing-data-away/), so your client device can acknowledge received data more efficiently</span></span>

<span data-ttu-id="84c39-111">有关 Office 365 服务，请参阅其他资源以优化性能：</span><span class="sxs-lookup"><span data-stu-id="84c39-111">For Office 365 services, see these additional resources to optimize performance:</span></span>

- [<span data-ttu-id="84c39-112">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="84c39-112">Exchange Online</span></span>](https://support.office.com/article/Tune-Exchange-Online-performance-026e83cb-a945-4543-97b0-a8af6e80ac61)
- [<span data-ttu-id="84c39-113">Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="84c39-113">Skype for Business Online</span></span>](https://support.office.com/article/Tune-Skype-for-Business-Online-performance-beec23c2-c5d6-4e84-a8af-e82aefca7802)
- [<span data-ttu-id="84c39-114">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="84c39-114">SharePoint Online</span></span>](https://support.office.com/article/Tune-SharePoint-Online-performance-f0522d4a-fbf4-41f9-854e-c9b59555091d)
- [<span data-ttu-id="84c39-115">Project Online</span><span class="sxs-lookup"><span data-stu-id="84c39-115">Project Online</span></span>](https://support.office.com/article/Tune-Project-Online-performance-12ba0ebd-c616-42e5-b9b6-cad570e8409c)

<span data-ttu-id="84c39-116">作为临时检查点，请查看对应于此步骤的[退出条件](networking-exit-criteria.md#crit-networking-step5)。</span><span class="sxs-lookup"><span data-stu-id="84c39-116">As an interim checkpoint, you can see the [exit criteria](networking-exit-criteria.md#crit-networking-step5) for this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="84c39-117">后续步骤</span><span class="sxs-lookup"><span data-stu-id="84c39-117">Next step</span></span>

[<span data-ttu-id="84c39-118">网络基础结构退出条件</span><span class="sxs-lookup"><span data-stu-id="84c39-118">Networking infrastructure exit criteria</span></span>](networking-exit-criteria.md)
