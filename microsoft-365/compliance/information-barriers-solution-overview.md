---
title: Microsoft 365 中的信息障碍
description: 了解如何在 Microsoft 365 中配置信息障碍。
keywords: Microsoft 365，内幕风险，合规性
localization_priority: Normal
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection:
- m365-security-compliance
- m365solution-insiderrisk
- m365initiative-compliance
ms.openlocfilehash: 74a5b557ae610f8d008ad9d43bd2ccac43179131
ms.sourcegitcommit: a0cddd1f888edb940717e434cda2dbe62e5e9475
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "49613732"
---
# <a name="information-barriers-in-microsoft-365"></a><span data-ttu-id="01fc3-104">Microsoft 365 中的信息障碍</span><span class="sxs-lookup"><span data-stu-id="01fc3-104">Information barriers in Microsoft 365</span></span>

<span data-ttu-id="01fc3-105">Microsoft 365 支持跨组和组织进行通信和协作，并支持在必要时限制特定用户组之间的通信和协作的方法。</span><span class="sxs-lookup"><span data-stu-id="01fc3-105">Microsoft 365 enables communication and collaboration across groups and organizations and supports ways to restrict communication and collaboration among specific groups of users when necessary.</span></span> <span data-ttu-id="01fc3-106">这可能包括要限制两个组之间的通信和协作以避免组织中发生利益冲突的情况或场景。</span><span class="sxs-lookup"><span data-stu-id="01fc3-106">This may include situations or scenarios where you want to restrict communication and collaboration between two groups to avoid a conflict of interest from occurring in your organization.</span></span> <span data-ttu-id="01fc3-107">如果您需要限制组织内部的某些人之间的通信和协作，以保护内部信息，也可能会出现这种情况。</span><span class="sxs-lookup"><span data-stu-id="01fc3-107">This may also include situations when you need to restrict communication and collaboration between certain people inside your organization to safeguard internal information.</span></span>

<span data-ttu-id="01fc3-108">在 Microsoft 团队、SharePoint Online 和 OneDrive for Business 中支持信息障碍。</span><span class="sxs-lookup"><span data-stu-id="01fc3-108">Information barriers are supported in Microsoft Teams, SharePoint Online, and OneDrive for Business.</span></span> <span data-ttu-id="01fc3-109">合规性管理员或信息屏障管理员可以定义策略以允许或阻止 Microsoft 团队中的用户组之间的通信。</span><span class="sxs-lookup"><span data-stu-id="01fc3-109">A compliance administrator or information barriers administrator can define policies to allow or prevent communications between groups of users in Microsoft Teams.</span></span> <span data-ttu-id="01fc3-110">信息屏障策略可用于以下情况：</span><span class="sxs-lookup"><span data-stu-id="01fc3-110">Information barrier policies can be used for situations like these:</span></span>

- <span data-ttu-id="01fc3-111">第一天的用户 trader 组不应与市场营销团队进行通信或与之共享文件</span><span class="sxs-lookup"><span data-stu-id="01fc3-111">User in the day trader group should not communicate or share files with the marketing team</span></span>
- <span data-ttu-id="01fc3-112">从事机密公司信息的财务人员不应与组织内的特定组进行通信或共享文件</span><span class="sxs-lookup"><span data-stu-id="01fc3-112">Finance personnel working on confidential company information should not communicate or share files with certain groups within their organization</span></span>
- <span data-ttu-id="01fc3-113">具有贸易秘密材料的内部团队不应与组织内特定组中的人员进行呼叫或联机聊天</span><span class="sxs-lookup"><span data-stu-id="01fc3-113">An internal team with trade secret material should not call or chat online with people in certain groups within their organization</span></span>
- <span data-ttu-id="01fc3-114">研究团队应仅与产品开发团队进行在线通话或聊天</span><span class="sxs-lookup"><span data-stu-id="01fc3-114">A research team should only call or chat online with a product development team</span></span>

## <a name="configure-information-barriers-for-microsoft-365"></a><span data-ttu-id="01fc3-115">为 Microsoft 365 配置信息障碍</span><span class="sxs-lookup"><span data-stu-id="01fc3-115">Configure information barriers for Microsoft 365</span></span>

<span data-ttu-id="01fc3-116">使用以下步骤为您的组织配置信息障碍：</span><span class="sxs-lookup"><span data-stu-id="01fc3-116">Use the following steps to configure information barriers for your organization:</span></span>

![内幕风险解决方案信息障碍步骤](../media/ir-solution-ib-steps.png)

1. <span data-ttu-id="01fc3-118">了解 Microsoft 365 中的[信息障碍](information-barriers.md)</span><span class="sxs-lookup"><span data-stu-id="01fc3-118">Learn about [information barriers](information-barriers.md) in Microsoft 365</span></span>
2. <span data-ttu-id="01fc3-119">配置 [先决条件和权限](information-barriers-policies.md#prerequisites)</span><span class="sxs-lookup"><span data-stu-id="01fc3-119">Configure [prerequisites and permissions](information-barriers-policies.md#prerequisites)</span></span>
3. <span data-ttu-id="01fc3-120">[对组织中的用户进行](information-barriers-policies.md#part-1-segment-users)分段</span><span class="sxs-lookup"><span data-stu-id="01fc3-120">Segment [users in your organization](information-barriers-policies.md#part-1-segment-users)</span></span>
4. <span data-ttu-id="01fc3-121">创建和配置 [信息屏障策略](information-barriers-policies.md#part-2-define-information-barrier-policies)</span><span class="sxs-lookup"><span data-stu-id="01fc3-121">Create and configure [information barrier policies](information-barriers-policies.md#part-2-define-information-barrier-policies)</span></span>
5. <span data-ttu-id="01fc3-122">应用 [信息屏障策略](information-barriers-policies.md#part-3-apply-information-barrier-policies)</span><span class="sxs-lookup"><span data-stu-id="01fc3-122">Apply [information barrier policies](information-barriers-policies.md#part-3-apply-information-barrier-policies)</span></span>

## <a name="more-information-about-information-barriers"></a><span data-ttu-id="01fc3-123">有关信息障碍的详细信息</span><span class="sxs-lookup"><span data-stu-id="01fc3-123">More information about information barriers</span></span>

- [<span data-ttu-id="01fc3-124">信息屏障策略的属性</span><span class="sxs-lookup"><span data-stu-id="01fc3-124">Attributes for information barrier policies</span></span>](information-barriers-attributes.md)
- [<span data-ttu-id="01fc3-125">编辑或删除信息障碍策略</span><span class="sxs-lookup"><span data-stu-id="01fc3-125">Edit or remove information barrier policies</span></span>](information-barriers-edit-segments-policies.md)