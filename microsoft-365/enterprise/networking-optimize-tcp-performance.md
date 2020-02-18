---
title: 步骤 5：优化客户端和 Office 365 服务性能
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/23/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: 配置 TCP 设置和 Office 365 服务以提高性能。
ms.openlocfilehash: e3aefb417330ab791a3dd217e2e34591eba3e1d1
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42066538"
---
# <a name="step-5-optimize-client-and-office-365-service-performance"></a><span data-ttu-id="206f7-103">步骤 5：优化客户端和 Office 365 服务性能</span><span class="sxs-lookup"><span data-stu-id="206f7-103">Step 5: Optimize client and Office 365 service performance</span></span>

<span data-ttu-id="206f7-104">*此步骤可选，它适用于 Microsoft 365 企业版的 E3 和 E5 版本*</span><span class="sxs-lookup"><span data-stu-id="206f7-104">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![阶段 1：网络](../media/deploy-foundation-infrastructure/networking_icon-small.png)

<span data-ttu-id="206f7-106">你可以微调传输控制协议 (TCP) 在客户端设备和 Office 365 服务之间的工作方式，以提高性能。</span><span class="sxs-lookup"><span data-stu-id="206f7-106">You can increase performance by fine tuning the way that the Transmission Control Protocol (TCP) works between client devices and Office 365 services.</span></span>

<span data-ttu-id="206f7-107">对于客户端设备，可以在客户端设备上更改以下 TCP 设置以优化 TCP 性能：</span><span class="sxs-lookup"><span data-stu-id="206f7-107">For client devices, you can change the following TCP settings on client devices to optimize TCP performance:</span></span>

- <span data-ttu-id="206f7-108">[TCP 窗口缩放](https://blogs.technet.microsoft.com/onthewire/2014/03/28/ensuring-your-office-365-network-connection-isnt-throttled-by-your-proxy/)，以使客户端设备在要求确认前发送更多数据</span><span class="sxs-lookup"><span data-stu-id="206f7-108">[TCP window scaling](https://blogs.technet.microsoft.com/onthewire/2014/03/28/ensuring-your-office-365-network-connection-isnt-throttled-by-your-proxy/), so your client device can send more data before requiring an acknowledgement</span></span>
- <span data-ttu-id="206f7-109">[TCP 空闲时间](https://blogs.technet.microsoft.com/onthewire/2014/03/04/network-perimeters-tcp-idle-session-settings-for-outlook-on-office-365/)，以使客户端设备更高效地处理打开的连接</span><span class="sxs-lookup"><span data-stu-id="206f7-109">[TCP idle time](https://blogs.technet.microsoft.com/onthewire/2014/03/04/network-perimeters-tcp-idle-session-settings-for-outlook-on-office-365/), so your client device can handle open connections more efficiently</span></span>
- <span data-ttu-id="206f7-110">[TCP 最大段大小](https://blogs.technet.microsoft.com/onthewire/2014/06/27/checking-your-tcp-packets-are-pulling-their-weight-tcp-max-segment-size-or-mss/)，以使客户端设备在数据包中发送数据的最大块</span><span class="sxs-lookup"><span data-stu-id="206f7-110">[TCP maximum segment size](https://blogs.technet.microsoft.com/onthewire/2014/06/27/checking-your-tcp-packets-are-pulling-their-weight-tcp-max-segment-size-or-mss/), so your client device can send the largest blocks of data in a packet</span></span>
- <span data-ttu-id="206f7-111">[TCP 选择性确认](https://blogs.technet.microsoft.com/onthewire/2014/06/27/ensuring-your-tcp-stack-isnt-throwing-data-away/)，以使客户端设备更高效地确认接收的数据</span><span class="sxs-lookup"><span data-stu-id="206f7-111">[TCP selective acknowledgements](https://blogs.technet.microsoft.com/onthewire/2014/06/27/ensuring-your-tcp-stack-isnt-throwing-data-away/), so your client device can acknowledge received data more efficiently</span></span>

<span data-ttu-id="206f7-112">有关 Office 365 服务，请参阅其他资源以优化性能：</span><span class="sxs-lookup"><span data-stu-id="206f7-112">For Office 365 services, see these additional resources to optimize performance:</span></span>

- [<span data-ttu-id="206f7-113">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="206f7-113">Exchange Online</span></span>](https://docs.microsoft.com/office365/enterprise/tune-exchange-online-performance)
- [<span data-ttu-id="206f7-114">Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="206f7-114">Skype for Business Online</span></span>](https://docs.microsoft.com/office365/enterprise/tune-skype-for-business-online-performance)
- [<span data-ttu-id="206f7-115">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="206f7-115">SharePoint Online</span></span>](https://docs.microsoft.com/office365/enterprise/tune-sharepoint-online-performance)
- [<span data-ttu-id="206f7-116">Project Online 中的 Project Web App</span><span class="sxs-lookup"><span data-stu-id="206f7-116">Project Web App in Project Online</span></span>](https://docs.microsoft.com/ProjectOnline/tune-project-online-performance)

<span data-ttu-id="206f7-117">作为临时检查点，可查看这一步的[退出条件](networking-exit-criteria.md#crit-networking-step5)。</span><span class="sxs-lookup"><span data-stu-id="206f7-117">As an interim checkpoint, you can see the [exit criteria](networking-exit-criteria.md#crit-networking-step5) for this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="206f7-118">后续步骤</span><span class="sxs-lookup"><span data-stu-id="206f7-118">Next step</span></span>

[<span data-ttu-id="206f7-119">网络基础结构退出条件</span><span class="sxs-lookup"><span data-stu-id="206f7-119">Networking infrastructure exit criteria</span></span>](networking-exit-criteria.md)
