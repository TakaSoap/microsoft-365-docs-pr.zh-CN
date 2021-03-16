---
title: Microsoft 365 租户到租户迁移
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-collaboration
- M365-subscription-management
- SPO_Content
search.appverid:
- MET150
- MOE150
ms.assetid: eb45fd8b-1d5d-4b0c-9c5a-479dbb176e7d
f1.keywords:
- NOCSH
description: 了解如何迁移 Microsoft 365 租户。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f6e8277a7ca768db3a4a4acd2488859b7764a40c
ms.sourcegitcommit: 8b1bd7ca8cd81e4270f0c1e06d2b6ca81804a6aa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/15/2021
ms.locfileid: "50819710"
---
# <a name="microsoft-365-tenant-to-tenant-migrations"></a><span data-ttu-id="7b89a-103">Microsoft 365 租户到租户迁移</span><span class="sxs-lookup"><span data-stu-id="7b89a-103">Microsoft 365 tenant-to-tenant migrations</span></span>

<span data-ttu-id="7b89a-104">合并、收购、资产重组和其他方案有几种体系结构方法，这些方法可能会导致你将现有 Microsoft 365 租户迁移到新租户。</span><span class="sxs-lookup"><span data-stu-id="7b89a-104">There are several architecture approaches for mergers, acquisitions, divestitures, and other scenarios that might lead you to migrate an existing Microsoft 365 tenant to a new tenant.</span></span> <span data-ttu-id="7b89a-105">大多数客户与 Microsoft 咨询服务或 Microsoft 合作伙伴合作迁移租户，包括使用第三方工具迁移内容。</span><span class="sxs-lookup"><span data-stu-id="7b89a-105">Most customers work with Microsoft Consulting Services or a Microsoft partner to migrate tenants, including using third-party tools to migrate content.</span></span> 

<span data-ttu-id="7b89a-106">使用 [租户到租户](https://download.microsoft.com/download/b/a/1/ba19dfe7-96e2-4983-8783-4dcff9cebe7b/microsoft-365-tenant-to-tenant-migration.pdf) 迁移体系结构模型可了解如何规划 Microsoft 365 租户到租户迁移以及迁移步骤。</span><span class="sxs-lookup"><span data-stu-id="7b89a-106">Use the [Tenant-to-tenant migration architecture model](https://download.microsoft.com/download/b/a/1/ba19dfe7-96e2-4983-8783-4dcff9cebe7b/microsoft-365-tenant-to-tenant-migration.pdf) to understand how to plan for Microsoft 365 tenant-to-tenant migrations and the steps of a migration.</span></span>

<span data-ttu-id="7b89a-107">[![租户到租户迁移模型](../media/solutions-architecture-center/msft-tenant-to-tenant-migration-thumb.png)](https://download.microsoft.com/download/b/a/1/ba19dfe7-96e2-4983-8783-4dcff9cebe7b/microsoft-365-tenant-to-tenant-migration.pdf)</span><span class="sxs-lookup"><span data-stu-id="7b89a-107">[![Tenant-to-tenant migration model](../media/solutions-architecture-center/msft-tenant-to-tenant-migration-thumb.png)](https://download.microsoft.com/download/b/a/1/ba19dfe7-96e2-4983-8783-4dcff9cebe7b/microsoft-365-tenant-to-tenant-migration.pdf)</span></span> 

<span data-ttu-id="7b89a-108">以 [PDF](https://download.microsoft.com/download/b/a/1/ba19dfe7-96e2-4983-8783-4dcff9cebe7b/microsoft-365-tenant-to-tenant-migration.pdf) 格式下载此模型，并打印在 11 x 17 大小的 (、法律或文) 上。</span><span class="sxs-lookup"><span data-stu-id="7b89a-108">You download this model in [PDF](https://download.microsoft.com/download/b/a/1/ba19dfe7-96e2-4983-8783-4dcff9cebe7b/microsoft-365-tenant-to-tenant-migration.pdf) format and print it on letter, legal, or tabloid (11 x 17) size paper.</span></span>

<span data-ttu-id="7b89a-109">此模型提供了针对以下部分进行规划的指导和起始点：</span><span class="sxs-lookup"><span data-stu-id="7b89a-109">This model provides guidance and a starting-point for planning with sections on:</span></span>

- <span data-ttu-id="7b89a-110">将业务方案映射到体系结构方法</span><span class="sxs-lookup"><span data-stu-id="7b89a-110">Mapping of business scenarios to architecture approaches</span></span>
- <span data-ttu-id="7b89a-111">设计注意事项</span><span class="sxs-lookup"><span data-stu-id="7b89a-111">Design considerations</span></span>

<span data-ttu-id="7b89a-112">此模型还包含以下详细示例：</span><span class="sxs-lookup"><span data-stu-id="7b89a-112">This model also contains detailed examples of:</span></span>

- <span data-ttu-id="7b89a-113">单个事件迁移流</span><span class="sxs-lookup"><span data-stu-id="7b89a-113">A single event migration flow</span></span>
- <span data-ttu-id="7b89a-114">分阶段迁移流</span><span class="sxs-lookup"><span data-stu-id="7b89a-114">A phased migration flow</span></span>
- <span data-ttu-id="7b89a-115">租户移动或拆分流</span><span class="sxs-lookup"><span data-stu-id="7b89a-115">A tenant move or split flow</span></span>
