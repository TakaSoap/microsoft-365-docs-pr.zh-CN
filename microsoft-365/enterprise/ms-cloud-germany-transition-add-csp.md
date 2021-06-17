---
title: 云解决方案提供商的其他信息
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/01/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Ent_TLGs
description: 摘要：与从德国 Microsoft 云迁移相关的云解决方案提供商的其他信息。
ms.openlocfilehash: 843552c55acba57c5c2da4a1a885d65cb4e59d84
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/17/2021
ms.locfileid: "52984912"
---
# <a name="additional-information-for-cloud-solution-providers"></a><span data-ttu-id="fee52-103">云解决方案提供商的其他信息</span><span class="sxs-lookup"><span data-stu-id="fee52-103">Additional information for Cloud Solution Providers</span></span>

<span data-ttu-id="fee52-104">云解决方案 (支持) 的云解决方案提供商需要执行其他步骤，从德国 Microsoft 云迁移到新的德国数据中心区域。</span><span class="sxs-lookup"><span data-stu-id="fee52-104">Cloud Solution Providers (CSPs) supporting customers  need to take additional steps during the migration from Microsoft Cloud Deutschland to the new German datacenter region.</span></span>

## <a name="partner-tenant-migration"></a><span data-ttu-id="fee52-105">合作伙伴租户迁移</span><span class="sxs-lookup"><span data-stu-id="fee52-105">Partner tenant migration</span></span>

<span data-ttu-id="fee52-106">不会迁移德国 Microsoft 云合作伙伴租户。</span><span class="sxs-lookup"><span data-stu-id="fee52-106">Partner Microsoft Cloud Deutschland tenants won't be migrated.</span></span> <span data-ttu-id="fee52-107">相反，将为新的德国Office 365区域的每个 Microsoft 合作伙伴创建一个新的服务租户。</span><span class="sxs-lookup"><span data-stu-id="fee52-107">Instead, a new Office 365 services tenant will be created for each Microsoft Partner in the new German datacenter region.</span></span>

<span data-ttu-id="fee52-108">云解决方案提供商客户租户将迁移到新的德国数据中心区域，并链接到同一合作伙伴的新 Office 365 服务租户。</span><span class="sxs-lookup"><span data-stu-id="fee52-108">CSP customer tenants will be migrated to the new German datacenter region and be linked to the new Office 365 services tenant of the same partner.</span></span> <span data-ttu-id="fee52-109">在客户转换后，合作伙伴可以使用德国数据中心区域的新 Office 365 服务租户管理客户。</span><span class="sxs-lookup"><span data-stu-id="fee52-109">After customer transition, the partner can manage the customer using the new Office 365 services tenant in the German datacenter region.</span></span>

## <a name="missing-subscriptions-in-azure"></a><span data-ttu-id="fee52-110">Azure 中缺少订阅</span><span class="sxs-lookup"><span data-stu-id="fee52-110">Missing subscriptions in Azure</span></span>

<span data-ttu-id="fee52-111">完成 [订阅和许可证 (阶段 3) ， ](ms-cloud-germany-transition-phases.md#phase-3-subscription-transfer) 云解决方案提供商将无法访问 Azure 订阅。</span><span class="sxs-lookup"><span data-stu-id="fee52-111">After [the subscription and license transition (phase 3)](ms-cloud-germany-transition-phases.md#phase-3-subscription-transfer) has been completed, Cloud Solution Providers will not have access to the Azure subscription anymore.</span></span>

<span data-ttu-id="fee52-112">若要恢复访问权限，请按照以下步骤 [提升访问权限，以管理所有 Azure 订阅和管理组](/azure/role-based-access-control/elevate-access-global-admin)。</span><span class="sxs-lookup"><span data-stu-id="fee52-112">To recover access, follow these steps to [elevate access to manage all Azure subscriptions and management groups](/azure/role-based-access-control/elevate-access-global-admin).</span></span>
