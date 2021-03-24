---
title: 调查 Microsoft 365 安全中心中的用户
description: 调查 Microsoft 365 安全中心中的用户
keywords: 安全， 恶意软件， Microsoft 365， M365， 安全中心， 监视， 报告， 标识， 数据， 设备， 应用
ms.prod: m365-security
ms.mktglfcycl: deploy
localization_priority: Normal
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
ms.date: ''
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
search.appverid: met150
ms.custom: seo-marvel-jun2020
ms.technology: m365d
ms.openlocfilehash: f48716ebd9e25d1f8b24d9276aaa5890a335a808
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51053550"
---
# <a name="investigate-users-in-microsoft-365-security-center"></a><span data-ttu-id="50cad-104">调查 Microsoft 365 安全中心中的用户</span><span class="sxs-lookup"><span data-stu-id="50cad-104">Investigate users in Microsoft 365 security center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

[!INCLUDE [Prerelease](../includes/prerelease.md)]

<span data-ttu-id="50cad-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="50cad-105">**Applies to:**</span></span>

- <span data-ttu-id="50cad-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="50cad-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="50cad-107">作为调查的一部分，你可能会发现用户受到威胁。</span><span class="sxs-lookup"><span data-stu-id="50cad-107">As part of your investigation, you might find that a user has been compromised.</span></span>

<span data-ttu-id="50cad-108">Microsoft 365 安全中心用户页面将来自 Microsoft Defender for Endpoint、Microsoft Defender for Identity 和 Microsoft Cloud App Security (的信息合并在一起，具体取决于你拥有哪些) 。</span><span class="sxs-lookup"><span data-stu-id="50cad-108">The Microsoft 365 security center user page combines information from Microsoft Defender for Endpoint, Microsoft Defender for Identity, and Microsoft Cloud App Security (depending on what licenses you have).</span></span> <span data-ttu-id="50cad-109">此页面是调查用户和潜在事件的理想起点。</span><span class="sxs-lookup"><span data-stu-id="50cad-109">This page is the ideal starting place for investigating users and potential incidents.</span></span>
<span data-ttu-id="50cad-110">![用户页面](../../media/m3d-userpage.png)</span><span class="sxs-lookup"><span data-stu-id="50cad-110">![User page](../../media/m3d-userpage.png)</span></span>

<span data-ttu-id="50cad-111">此页面显示特定于用户的安全风险的信息。</span><span class="sxs-lookup"><span data-stu-id="50cad-111">This page shows information specific to the security risk of a user.</span></span> <span data-ttu-id="50cad-112">这包括一个分数，可帮助评估风险、导致用户的整体风险的最近事件和警报等。</span><span class="sxs-lookup"><span data-stu-id="50cad-112">This includes a score that helps assess risk, recent events and alerts that contributed to the overall risk of the user, and more.</span></span>

<span data-ttu-id="50cad-113">可以从 Microsoft 365 安全中心的多个区域访问此页面。</span><span class="sxs-lookup"><span data-stu-id="50cad-113">You can access this page from multiple areas in the Microsoft 365 security center.</span></span> <span data-ttu-id="50cad-114">可以从"用户"选项卡中的特定事件访问 **此页面** 。某些警报可能会将用户作为特定的受影响资产包含。</span><span class="sxs-lookup"><span data-stu-id="50cad-114">You can access this page from a specific incident in the **Users** tab. Some alerts might include users as a specific affected asset.</span></span> <span data-ttu-id="50cad-115">还可以搜索用户。</span><span class="sxs-lookup"><span data-stu-id="50cad-115">You can also search for users.</span></span>  

<span data-ttu-id="50cad-116">若要详细了解如何调查用户和潜在风险，请在此 [Cloud App Security 教程中了解](/cloud-app-security/tutorial-ueba#:~:text=To%20identify%20who%20your%20riskiest,user%20page%20to%20investigate%20them)。</span><span class="sxs-lookup"><span data-stu-id="50cad-116">Learn more about how to investigate users and potential risk [in this Cloud App Security tutorial](/cloud-app-security/tutorial-ueba#:~:text=To%20identify%20who%20your%20riskiest,user%20page%20to%20investigate%20them).</span></span>

## <a name="related-topics"></a><span data-ttu-id="50cad-117">相关主题</span><span class="sxs-lookup"><span data-stu-id="50cad-117">Related topics</span></span>

- [<span data-ttu-id="50cad-118">事件概述</span><span class="sxs-lookup"><span data-stu-id="50cad-118">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="50cad-119">确定事件优先级</span><span class="sxs-lookup"><span data-stu-id="50cad-119">Prioritize incidents</span></span>](incident-queue.md)
- [<span data-ttu-id="50cad-120">管理事件</span><span class="sxs-lookup"><span data-stu-id="50cad-120">Manage incidents</span></span>](manage-incidents.md)