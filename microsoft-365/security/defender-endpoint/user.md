---
title: 用户资源类型
description: 检索最近与用户相关的 Microsoft Defender for Endpoint 警报。
keywords: api， 图形 api， 受支持的 api， 获取， 警报， 最近
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: e3b2a567a953883d1d0ecd062159bfee4135dc85
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51197953"
---
# <a name="user-resource-type"></a><span data-ttu-id="71841-104">用户资源类型</span><span class="sxs-lookup"><span data-stu-id="71841-104">User resource type</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="71841-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="71841-105">**Applies to:**</span></span>
- [<span data-ttu-id="71841-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="71841-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="71841-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="71841-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="71841-108">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="71841-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="71841-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="71841-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


<span data-ttu-id="71841-110">方法</span><span class="sxs-lookup"><span data-stu-id="71841-110">Method</span></span>|<span data-ttu-id="71841-111">返回类型</span><span class="sxs-lookup"><span data-stu-id="71841-111">Return Type</span></span> |<span data-ttu-id="71841-112">说明</span><span class="sxs-lookup"><span data-stu-id="71841-112">Description</span></span>
:---|:---|:---
[<span data-ttu-id="71841-113">列出与用户相关的警报</span><span class="sxs-lookup"><span data-stu-id="71841-113">List User related alerts</span></span>](get-user-related-alerts.md) | <span data-ttu-id="71841-114">[警报](alerts.md)集合</span><span class="sxs-lookup"><span data-stu-id="71841-114">[alert](alerts.md) collection</span></span> |  <span data-ttu-id="71841-115">列出与用户关联的所有 [警报](user.md)。</span><span class="sxs-lookup"><span data-stu-id="71841-115">List all the alerts that are associated with a [user](user.md).</span></span>
[<span data-ttu-id="71841-116">列出与用户相关的设备</span><span class="sxs-lookup"><span data-stu-id="71841-116">List User related devices</span></span>](get-user-related-machines.md) | <span data-ttu-id="71841-117">[计算机](machine.md) 集合</span><span class="sxs-lookup"><span data-stu-id="71841-117">[machine](machine.md) collection</span></span> | <span data-ttu-id="71841-118">列出用户登录的所有 [设备](user.md)。</span><span class="sxs-lookup"><span data-stu-id="71841-118">List all the devices that were logged on by a [user](user.md).</span></span>
