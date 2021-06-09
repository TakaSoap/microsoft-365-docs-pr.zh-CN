---
title: 转换到 Microsoft Defender for Endpoint 的迁移指南
description: 了解如何从非 Microsoft 365 Defender 解决方案切换到 Microsoft Defender for Endpoint
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
ms.date: 09/24/2020
ms.technology: mde
ms.openlocfilehash: 7d6d92f3abc79552406c80a46a8c3390b91e31d0
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2021
ms.locfileid: "52843006"
---
# <a name="make-the-switch-to-microsoft-defender-for-endpoint-and-microsoft-defender-antivirus"></a><span data-ttu-id="fe439-103">切换到 Microsoft Defender for Endpoint 并Microsoft Defender 防病毒</span><span class="sxs-lookup"><span data-stu-id="fe439-103">Make the switch to Microsoft Defender for Endpoint and Microsoft Defender Antivirus</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="fe439-104">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="fe439-104">**Applies to:**</span></span>
- [<span data-ttu-id="fe439-105">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="fe439-105">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="fe439-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="fe439-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="fe439-107">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="fe439-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="fe439-108">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="fe439-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

## <a name="migration-guides"></a><span data-ttu-id="fe439-109">迁移指南</span><span class="sxs-lookup"><span data-stu-id="fe439-109">Migration guides</span></span>

<span data-ttu-id="fe439-110">如果你正在考虑从非 Microsoft 365 Defender 解决方案切换到使用 Microsoft Defender 防病毒 的 Microsoft Defender for Endpoint，请查看我们的迁移指南。</span><span class="sxs-lookup"><span data-stu-id="fe439-110">If you're considering switching from a non-Microsoft 365 Defender solution to Microsoft Defender for Endpoint with Microsoft Defender Antivirus, check out our migration guidance.</span></span> <span data-ttu-id="fe439-111">选择最代表部署过程位置的方案，并查看指南。</span><span class="sxs-lookup"><span data-stu-id="fe439-111">Select the scenario that best represents where you are in your deployment process, and see the guidance.</span></span>

|<span data-ttu-id="fe439-112">应用场景</span><span class="sxs-lookup"><span data-stu-id="fe439-112">Scenario</span></span> |<span data-ttu-id="fe439-113">指南</span><span class="sxs-lookup"><span data-stu-id="fe439-113">Guidance</span></span> |
|:--|:--|
|<span data-ttu-id="fe439-114">你还没有终结点保护解决方案，并且想要了解有关 Microsoft Defender for Endpoint & Microsoft Defender 防病毒工作。</span><span class="sxs-lookup"><span data-stu-id="fe439-114">You do not have an endpoint protection solution yet, and you want to know more about how Microsoft Defender for Endpoint & Microsoft Defender Antivirus work.</span></span>  |[<span data-ttu-id="fe439-115">Microsoft Defender for Endpoint 评估实验室</span><span class="sxs-lookup"><span data-stu-id="fe439-115">Microsoft Defender for Endpoint evaluation lab</span></span>](evaluation-lab.md)   |
|<span data-ttu-id="fe439-116">你拥有 Microsoft Defender for Endpoint & Microsoft Defender 防病毒并且需要一些帮助来设置和配置所有内容。</span><span class="sxs-lookup"><span data-stu-id="fe439-116">You have Microsoft Defender for Endpoint & Microsoft Defender Antivirus and need some help getting everything set up and configured.</span></span>  |[<span data-ttu-id="fe439-117">Microsoft Defender for Endpoint 部署指南</span><span class="sxs-lookup"><span data-stu-id="fe439-117">Microsoft Defender for Endpoint deployment guide</span></span>](deployment-phases.md)  |
|<span data-ttu-id="fe439-118">你计划从 McAfee Endpoint Security (McAfee) 迁移到 Microsoft Defender for Endpoint & Microsoft Defender 防病毒。</span><span class="sxs-lookup"><span data-stu-id="fe439-118">You're planning to migrate from McAfee Endpoint Security (McAfee) to Microsoft Defender for Endpoint & Microsoft Defender Antivirus.</span></span> |[<span data-ttu-id="fe439-119">从 McAfee 切换到 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="fe439-119">Switch from McAfee to Microsoft Defender for Endpoint</span></span>](mcafee-to-microsoft-defender-migration.md) |
|<span data-ttu-id="fe439-120">你计划从 Symantec Endpoint Protection (Symantec) 迁移到 Microsoft Defender for Endpoint & Microsoft Defender 防病毒。</span><span class="sxs-lookup"><span data-stu-id="fe439-120">You're planning to migrate from Symantec Endpoint Protection (Symantec) to Microsoft Defender for Endpoint & Microsoft Defender Antivirus.</span></span> |[<span data-ttu-id="fe439-121">从 Symantec 切换到 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="fe439-121">Switch from Symantec to Microsoft Defender for Endpoint</span></span>](symantec-to-microsoft-defender-endpoint-migration.md) |
|<span data-ttu-id="fe439-122">你计划从 McAfee 或 Symantec (非 Microsoft endpoint protection 解决方案) Microsoft Defender for Endpoint & Microsoft Defender 防病毒。</span><span class="sxs-lookup"><span data-stu-id="fe439-122">You're planning to migrate from a non-Microsoft endpoint protection solution (other than McAfee or Symantec) to Microsoft Defender for Endpoint & Microsoft Defender Antivirus.</span></span> |[<span data-ttu-id="fe439-123">转换到 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="fe439-123">Make the switch to Microsoft Defender for Endpoint</span></span>](switch-to-microsoft-defender-migration.md)   |
|<span data-ttu-id="fe439-124">你已迁移到 Microsoft Defender for Endpoint & Microsoft Defender 防病毒，需要有关下一步（如配置其他功能或微调安全设置）的帮助。</span><span class="sxs-lookup"><span data-stu-id="fe439-124">You've migrated to Microsoft Defender for Endpoint & Microsoft Defender Antivirus, and you need help with next steps, such as configuring additional features or fine-tuning your security settings.</span></span> | [<span data-ttu-id="fe439-125">管理 Microsoft Defender for Endpoint，迁移后</span><span class="sxs-lookup"><span data-stu-id="fe439-125">Manage Microsoft Defender for Endpoint, post-migration</span></span>](manage-atp-post-migration.md) |


## <a name="got-feedback"></a><span data-ttu-id="fe439-126">收到反馈？</span><span class="sxs-lookup"><span data-stu-id="fe439-126">Got feedback?</span></span>

<span data-ttu-id="fe439-127">请将你的想法告诉我们！</span><span class="sxs-lookup"><span data-stu-id="fe439-127">Let us know what you think!</span></span> <span data-ttu-id="fe439-128">在页面底部提交反馈。</span><span class="sxs-lookup"><span data-stu-id="fe439-128">Submit your feedback at the bottom of the page.</span></span> <span data-ttu-id="fe439-129">我们将继续改进我们的迁移指南并将其添加到迁移指南中，我们将考虑你的反馈。</span><span class="sxs-lookup"><span data-stu-id="fe439-129">We'll take your feedback into account as we continue to improve and add to our migration guidance.</span></span>

## <a name="see-also"></a><span data-ttu-id="fe439-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fe439-130">See also</span></span>

- [<span data-ttu-id="fe439-131">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="fe439-131">Microsoft Defender for Endpoint</span></span>](/windows/security/threat-protection)
- [<span data-ttu-id="fe439-132">Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="fe439-132">Microsoft Defender for Office 365</span></span>](/microsoft-365/security/office-365-security/office-365-atp)
- [<span data-ttu-id="fe439-133">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="fe439-133">Microsoft 365 Defender</span></span>](/microsoft-365/security/defender/microsoft-threat-protection?) 
