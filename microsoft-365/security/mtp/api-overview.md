---
title: Microsoft 365 Defender Api 概述
description: 了解 Microsoft 365 Defender 中的可用 Api
keywords: api、api、概述、事件、事件、威胁搜寻
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 75a5853e7128667420819c84fbc3c50b07d669b4
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2020
ms.locfileid: "48845004"
---
# <a name="overview-of--microsoft-365-defender-apis"></a><span data-ttu-id="b7444-104">Microsoft 365 Defender Api 概述</span><span class="sxs-lookup"><span data-stu-id="b7444-104">Overview of  Microsoft 365 Defender APIs</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="b7444-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="b7444-105">**Applies to:**</span></span>
- <span data-ttu-id="b7444-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b7444-106">Microsoft 365 Defender</span></span>


>[!IMPORTANT] 
><span data-ttu-id="b7444-107">一些信息与 prereleased 产品相关，在正式发布之前可能会对其进行重大修改。</span><span class="sxs-lookup"><span data-stu-id="b7444-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="b7444-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="b7444-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="b7444-109">Microsoft 365 Defender 解决方案建立在集成就绪平台之上。</span><span class="sxs-lookup"><span data-stu-id="b7444-109">Microsoft 365 Defender solution is built on top of an integration-ready platform.</span></span> 

<span data-ttu-id="b7444-110">使用 lop-exo 级 Microsoft 365 Defender Api，您可以基于共享事件和高级搜寻表自动执行工作流。</span><span class="sxs-lookup"><span data-stu-id="b7444-110">The lop-level Microsoft 365 Defender APIs will enable you to automate workflows based on the shared incident and advanced hunting tables.</span></span>

- <span data-ttu-id="b7444-111">**合并的事件队列** -帮助安全专业人员重点关注关键因素。</span><span class="sxs-lookup"><span data-stu-id="b7444-111">**Combined incidents queue** - Helps security professionals focus on what's critical.</span></span> <span data-ttu-id="b7444-112">帮助确保完全攻击作用域和受影响的资产组合在一起，并在事件 API 下及时出现。</span><span class="sxs-lookup"><span data-stu-id="b7444-112">Helps to ensure that the full attack scope and impacted assets are grouped together and surfaced in a timely manner under the incident API.</span></span>

- <span data-ttu-id="b7444-113">**跨产品威胁搜寻** -安全团队可以通过 api 创建自己的自定义查询，通过 api 通过各种保护产品收集的原始数据创建自己的自定义查询，从而利用其独特的组织知识来寻找危害迹象。</span><span class="sxs-lookup"><span data-stu-id="b7444-113">**Cross-product threat hunting** - Security teams can leverage their unique organizational knowledge to hunt for signs of compromise by creating their own custom queries via APIs over the raw data collected by the various protection products.</span></span> 

<span data-ttu-id="b7444-114">除了这些 Api 集之外，每种不同的保护产品还会公开其他 Api，以帮助您根据每个产品功能进行创新。</span><span class="sxs-lookup"><span data-stu-id="b7444-114">In addition to these set of APIs, each of the various protection products expose additional APIs to help you innovate based on each product capability.</span></span>

## <a name="related-topics"></a><span data-ttu-id="b7444-115">相关主题</span><span class="sxs-lookup"><span data-stu-id="b7444-115">Related topics</span></span>
- [<span data-ttu-id="b7444-116">访问 Microsoft 威胁防护 Api</span><span class="sxs-lookup"><span data-stu-id="b7444-116">Access the Microsoft Threat Protection APIs</span></span>](api-access.md)
- [<span data-ttu-id="b7444-117">其他 API 资源</span><span class="sxs-lookup"><span data-stu-id="b7444-117">Other API resources</span></span>](api-articles.md)
