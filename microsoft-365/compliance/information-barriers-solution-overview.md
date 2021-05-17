---
title: 信息障碍Microsoft 365
description: 了解如何在部署中配置Microsoft 365。
keywords: Microsoft 365、内部风险、合规性
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
- m365solution-scenario
ms.openlocfilehash: a4c7b711c0a977e0980cd0c72f9369833e9e5c65
ms.sourcegitcommit: 355bd51ab6a79d5c36a4e4f57df74ae6873eba19
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/04/2021
ms.locfileid: "50423593"
---
# <a name="information-barriers-in-microsoft-365"></a><span data-ttu-id="4c742-104">信息障碍Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="4c742-104">Information barriers in Microsoft 365</span></span>

<span data-ttu-id="4c742-105">Microsoft 365支持各组和组织之间的通信和协作，并支持在必要时限制特定用户组之间的通信和协作的方法。</span><span class="sxs-lookup"><span data-stu-id="4c742-105">Microsoft 365 enables communication and collaboration across groups and organizations and supports ways to restrict communication and collaboration among specific groups of users when necessary.</span></span> <span data-ttu-id="4c742-106">这可能包括您希望限制两个组之间的通信和协作以避免在组织中发生利益冲突的情况。</span><span class="sxs-lookup"><span data-stu-id="4c742-106">This may include situations or scenarios where you want to restrict communication and collaboration between two groups to avoid a conflict of interest from occurring in your organization.</span></span> <span data-ttu-id="4c742-107">这可能包括需要限制组织内部某些人员之间的通信和协作以保护内部信息的情况。</span><span class="sxs-lookup"><span data-stu-id="4c742-107">This may also include situations when you need to restrict communication and collaboration between certain people inside your organization to safeguard internal information.</span></span>

<span data-ttu-id="4c742-108">Microsoft Teams、SharePoint Online 和 OneDrive for Business 支持信息屏障。</span><span class="sxs-lookup"><span data-stu-id="4c742-108">Information barriers are supported in Microsoft Teams, SharePoint Online, and OneDrive for Business.</span></span> <span data-ttu-id="4c742-109">合规性管理员或信息屏障管理员可以定义策略，以允许或阻止用户组中用户组Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="4c742-109">A compliance administrator or information barriers administrator can define policies to allow or prevent communications between groups of users in Microsoft Teams.</span></span> <span data-ttu-id="4c742-110">信息屏障策略可用于类似以下的情况：</span><span class="sxs-lookup"><span data-stu-id="4c742-110">Information barrier policies can be used for situations like these:</span></span>

- <span data-ttu-id="4c742-111">日常分组中的用户不应与营销团队通信或共享文件</span><span class="sxs-lookup"><span data-stu-id="4c742-111">User in the day trader group should not communicate or share files with the marketing team</span></span>
- <span data-ttu-id="4c742-112">处理机密公司信息的财务人员不应与组织内的某些组通信或共享文件</span><span class="sxs-lookup"><span data-stu-id="4c742-112">Finance personnel working on confidential company information should not communicate or share files with certain groups within their organization</span></span>
- <span data-ttu-id="4c742-113">具有商业机密材料的内部团队不应在线呼叫或与组织中某些组的人聊天</span><span class="sxs-lookup"><span data-stu-id="4c742-113">An internal team with trade secret material should not call or chat online with people in certain groups within their organization</span></span>
- <span data-ttu-id="4c742-114">研究团队只能与产品开发团队在线通话或聊天</span><span class="sxs-lookup"><span data-stu-id="4c742-114">A research team should only call or chat online with a product development team</span></span>

## <a name="configure-information-barriers-for-microsoft-365"></a><span data-ttu-id="4c742-115">为用户配置Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="4c742-115">Configure information barriers for Microsoft 365</span></span>

<span data-ttu-id="4c742-116">使用以下步骤为组织配置信息屏障：</span><span class="sxs-lookup"><span data-stu-id="4c742-116">Use the following steps to configure information barriers for your organization:</span></span>

![内部风险解决方案信息屏障步骤](../media/ir-solution-ib-steps.png)

1. <span data-ttu-id="4c742-118">了解[信息障碍](information-barriers.md)Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="4c742-118">Learn about [information barriers](information-barriers.md) in Microsoft 365</span></span>
2. <span data-ttu-id="4c742-119">配置 [先决条件和权限](information-barriers-policies.md#prerequisites)</span><span class="sxs-lookup"><span data-stu-id="4c742-119">Configure [prerequisites and permissions](information-barriers-policies.md#prerequisites)</span></span>
3. <span data-ttu-id="4c742-120">划分 [组织中用户](information-barriers-policies.md#part-1-segment-users)</span><span class="sxs-lookup"><span data-stu-id="4c742-120">Segment [users in your organization](information-barriers-policies.md#part-1-segment-users)</span></span>
4. <span data-ttu-id="4c742-121">创建和配置 [信息屏障策略](information-barriers-policies.md#part-2-define-information-barrier-policies)</span><span class="sxs-lookup"><span data-stu-id="4c742-121">Create and configure [information barrier policies](information-barriers-policies.md#part-2-define-information-barrier-policies)</span></span>
5. <span data-ttu-id="4c742-122">应用 [信息屏障策略](information-barriers-policies.md#part-3-apply-information-barrier-policies)</span><span class="sxs-lookup"><span data-stu-id="4c742-122">Apply [information barrier policies](information-barriers-policies.md#part-3-apply-information-barrier-policies)</span></span>

## <a name="more-information-about-information-barriers"></a><span data-ttu-id="4c742-123">有关信息屏障详细信息</span><span class="sxs-lookup"><span data-stu-id="4c742-123">More information about information barriers</span></span>

- [<span data-ttu-id="4c742-124">信息屏障策略的属性</span><span class="sxs-lookup"><span data-stu-id="4c742-124">Attributes for information barrier policies</span></span>](information-barriers-attributes.md)
- [<span data-ttu-id="4c742-125">编辑或删除信息屏障策略</span><span class="sxs-lookup"><span data-stu-id="4c742-125">Edit or remove information barrier policies</span></span>](information-barriers-edit-segments-policies.md)