---
title: 第 1 步：准备用于 Microsoft 365 的网络
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
description: 了解 Microsoft 365 企业版云服务对 Internet 带宽的需求。
ms.openlocfilehash: a2b5be462747ff269b82304249d46f32837ae2e5
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/21/2020
ms.locfileid: "43631449"
---
# <a name="step-1-prepare-your-network-for-microsoft-365"></a><span data-ttu-id="b2b72-103">第 1 步：准备用于 Microsoft 365 的网络</span><span class="sxs-lookup"><span data-stu-id="b2b72-103">Step 1: Prepare your network for Microsoft 365</span></span>

<span data-ttu-id="b2b72-104">*此步骤是必需的，适用于 Microsoft 365 企业版的 E3 和 E5 版本*</span><span class="sxs-lookup"><span data-stu-id="b2b72-104">*This step is required and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![阶段 1：网络](../media/deploy-foundation-infrastructure/networking_icon-small.png)

<span data-ttu-id="b2b72-106">在第 1 步中，必须：</span><span class="sxs-lookup"><span data-stu-id="b2b72-106">In Step 1, you must:</span></span>

- <span data-ttu-id="b2b72-107">根据 Microsoft 365 企业版云服务的流量，评估和调整内部链接和 Internet 连接的网络带宽。</span><span class="sxs-lookup"><span data-stu-id="b2b72-107">Evaluate and adjust network bandwidth for internal links and Internet connections to account for traffic to Microsoft 365 Enterprise cloud services.</span></span>
- <span data-ttu-id="b2b72-108">让网络与 [Microsoft 365 参考体系结构](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#BKMK_P2)保持一致。</span><span class="sxs-lookup"><span data-stu-id="b2b72-108">Align your network with a [Microsoft 365 reference architecture](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#BKMK_P2).</span></span>
- <span data-ttu-id="b2b72-109">计划更改、试用更改，然后测试该更改是否适合带宽和通信延迟要求。</span><span class="sxs-lookup"><span data-stu-id="b2b72-109">Plan the changes, pilot them, and then test whether the changes fit your bandwidth and traffic latency requirements.</span></span>

<span data-ttu-id="b2b72-110">有关结合使用 ExpressRoute 与 Microsoft 365 和 Microsoft 365 企业版的其他云服务的信息和建议，请参阅[适用于 Microsoft 365 的 Azure ExpressRoute](https://docs.microsoft.com/office365/enterprise/azure-expressroute)。</span><span class="sxs-lookup"><span data-stu-id="b2b72-110">For information and recommendations about using ExpressRoute with Microsoft 365 and the other cloud services of Microsoft 365 Enterprise, see [Azure ExpressRoute for Microsoft 365](https://docs.microsoft.com/office365/enterprise/azure-expressroute).</span></span>

<span data-ttu-id="b2b72-111">作为临时检查点，请查看对应于此步骤的[退出条件](networking-exit-criteria.md#crit-networking-step1)。</span><span class="sxs-lookup"><span data-stu-id="b2b72-111">As an interim checkpoint, you can see the [exit criteria](networking-exit-criteria.md#crit-networking-step1) corresponding to this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="b2b72-112">后续步骤</span><span class="sxs-lookup"><span data-stu-id="b2b72-112">Next step</span></span>

|||
|:-------|:-----|
|![第 2 步](../media/stepnumbers/Step2.png)|[<span data-ttu-id="b2b72-114">配置每个办公室的本地 Internet 连接</span><span class="sxs-lookup"><span data-stu-id="b2b72-114">Configure local Internet connections for each office</span></span>](networking-dns-resolution-same-location.md)|

