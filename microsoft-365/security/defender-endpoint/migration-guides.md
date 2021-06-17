---
title: 转换到 Microsoft Defender for Endpoint 的迁移指南
description: 了解如何从非解决方案Microsoft 365 Defender Microsoft Defender for Endpoint
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.prod: m365-security
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-scenario
ms.custom: migrationguides
ms.reviewer: chriggs, depicker, yongrhee
f1.keywords: NOCSH
ms.date: 06/14/2021
ms.technology: mde
ms.openlocfilehash: 010cea14bebd4e29822b1826c0ec4577d53baca7
ms.sourcegitcommit: 1c11035dd4432e34603022740baef0c8f7ff4425
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/16/2021
ms.locfileid: "52964857"
---
# <a name="make-the-switch-to-microsoft-defender-for-endpoint"></a><span data-ttu-id="1d671-103">转换到 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="1d671-103">Make the switch to Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="1d671-104">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="1d671-104">**Applies to:**</span></span>
- [<span data-ttu-id="1d671-105">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="1d671-105">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="1d671-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1d671-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="1d671-107">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="1d671-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="1d671-108">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="1d671-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

## <a name="migration-guides"></a><span data-ttu-id="1d671-109">迁移指南</span><span class="sxs-lookup"><span data-stu-id="1d671-109">Migration guides</span></span>

<span data-ttu-id="1d671-110">如果你正在考虑迁移到 Defender for Endpoint，我们提供了帮助指南。</span><span class="sxs-lookup"><span data-stu-id="1d671-110">If you're considering moving to Defender for Endpoint, we have guidance to help.</span></span> <span data-ttu-id="1d671-111">在下表中，查看这些方案。</span><span class="sxs-lookup"><span data-stu-id="1d671-111">In the following table, review the scenarios.</span></span> <span data-ttu-id="1d671-112">选择最适合你的情况的方案，并查看建议的指导。</span><span class="sxs-lookup"><span data-stu-id="1d671-112">Select the scenario that best represents your situation, and see the recommended guidance.</span></span>

| <span data-ttu-id="1d671-113">应用场景</span><span class="sxs-lookup"><span data-stu-id="1d671-113">Scenario</span></span> | <span data-ttu-id="1d671-114">指南</span><span class="sxs-lookup"><span data-stu-id="1d671-114">Guidance</span></span> |
|:----|:----|
| <span data-ttu-id="1d671-115">你还没有终结点保护解决方案，并且想要了解有关 Defender for Endpoint 的更多信息。</span><span class="sxs-lookup"><span data-stu-id="1d671-115">You don't have an endpoint protection solution in place yet, and you want to know more about Defender for Endpoint.</span></span> <span data-ttu-id="1d671-116">在环境中部署 Defender for Endpoint 之前，你想要了解它的工作原理。</span><span class="sxs-lookup"><span data-stu-id="1d671-116">You want to see how Defender for Endpoint works before rolling it out in your environment.</span></span>  | [<span data-ttu-id="1d671-117">Microsoft Defender for Endpoint 评估实验室</span><span class="sxs-lookup"><span data-stu-id="1d671-117">Microsoft Defender for Endpoint evaluation lab</span></span>](evaluation-lab.md)   |
| <span data-ttu-id="1d671-118">你已拥有适用于终结点的 Defender，并且你需要一些帮助来设置和配置所有内容。</span><span class="sxs-lookup"><span data-stu-id="1d671-118">You already have Defender for Endpoint, and you want some help getting everything set up and configured.</span></span>  | [<span data-ttu-id="1d671-119">Microsoft Defender for Endpoint 部署指南</span><span class="sxs-lookup"><span data-stu-id="1d671-119">Microsoft Defender for Endpoint deployment guide</span></span>](deployment-phases.md)  |
| <span data-ttu-id="1d671-120">你计划从非 Microsoft 终结点保护解决方案切换到 Defender for Endpoint 和 Microsoft Defender 防病毒。</span><span class="sxs-lookup"><span data-stu-id="1d671-120">You're planning to switch from a non-Microsoft endpoint protection solution to Defender for Endpoint and Microsoft Defender Antivirus.</span></span> <span data-ttu-id="1d671-121">您希望大致了解迁移过程以及如何进行切换。</span><span class="sxs-lookup"><span data-stu-id="1d671-121">You want to get an overview of the migration process and how to make the switch.</span></span> |[<span data-ttu-id="1d671-122">转换到 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="1d671-122">Make the switch to Microsoft Defender for Endpoint</span></span>](switch-to-microsoft-defender-migration.md)   |
| <span data-ttu-id="1d671-123">你已迁移或载入到 Defender for Endpoint。</span><span class="sxs-lookup"><span data-stu-id="1d671-123">You've already migrated or onboarded to Defender for Endpoint.</span></span> <span data-ttu-id="1d671-124">需要一些有关下一步的帮助，例如管理安全设置、配置更多功能或微调安全策略。</span><span class="sxs-lookup"><span data-stu-id="1d671-124">You want some help with next steps, such as managing your security settings, configuring more features, or fine-tuning your security policies.</span></span> | [<span data-ttu-id="1d671-125">管理 Microsoft Defender for Endpoint，迁移后</span><span class="sxs-lookup"><span data-stu-id="1d671-125">Manage Microsoft Defender for Endpoint, post-migration</span></span>](manage-atp-post-migration.md) |


## <a name="do-you-have-feedback-for-us"></a><span data-ttu-id="1d671-126">是否向我们提供反馈？</span><span class="sxs-lookup"><span data-stu-id="1d671-126">Do you have feedback for us?</span></span>

<span data-ttu-id="1d671-127">请将你的想法告诉我们！</span><span class="sxs-lookup"><span data-stu-id="1d671-127">Let us know what you think!</span></span> <span data-ttu-id="1d671-128">在页面底部提交反馈。</span><span class="sxs-lookup"><span data-stu-id="1d671-128">Submit your feedback at the bottom of the page.</span></span> <span data-ttu-id="1d671-129">我们将继续改进我们的迁移指南并将其添加到迁移指南中，我们将考虑你的反馈。</span><span class="sxs-lookup"><span data-stu-id="1d671-129">We'll take your feedback into account as we continue to improve and add to our migration guidance.</span></span>

## <a name="see-also"></a><span data-ttu-id="1d671-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1d671-130">See also</span></span>

- [<span data-ttu-id="1d671-131">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="1d671-131">Microsoft Defender for Endpoint</span></span>](/windows/security/threat-protection)
- [<span data-ttu-id="1d671-132">Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="1d671-132">Microsoft Defender for Office 365</span></span>](/microsoft-365/security/office-365-security/office-365-atp)
- [<span data-ttu-id="1d671-133">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1d671-133">Microsoft 365 Defender</span></span>](/microsoft-365/security/defender/microsoft-threat-protection?) 
