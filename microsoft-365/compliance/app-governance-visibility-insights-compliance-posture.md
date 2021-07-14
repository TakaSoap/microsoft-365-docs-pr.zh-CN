---
title: 确定你的应用合规性状况
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: m365-security-compliance
localization_priority: Priority
search.appverid:
- MOE150
- MET150
description: 确定你的应用合规性状况。
ms.openlocfilehash: 3d7cac319c31bac40a3aad2f6b9a4c16303f6a20
ms.sourcegitcommit: 41c7f7bd5c808ee5ceca0f6efe13d4e67da0262b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/14/2021
ms.locfileid: "53420027"
---
# <a name="determine-your-app-compliance-posture"></a><span data-ttu-id="f4aad-103">确定你的应用合规性状况</span><span class="sxs-lookup"><span data-stu-id="f4aad-103">Determine your app compliance posture</span></span>

><span data-ttu-id="f4aad-104">*[Microsoft 365 安全性与合规性许可指南](https://aka.ms/ComplianceSD)。*</span><span class="sxs-lookup"><span data-stu-id="f4aad-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="f4aad-105">Microsoft 应用治理允许你从 [Microsoft 365 合规中心](https://compliance.microsoft.com/appgovernance)的应用治理概述页面快速评估第三方应用的合规状况及其对 Microsoft 365 租户中数据的访问。</span><span class="sxs-lookup"><span data-stu-id="f4aad-105">Microsoft app governance allows you to quickly assess the compliance posture of the third-party apps and their access to data in your Microsoft 365 tenant from the app governance Overview page in the [Microsoft 365 Compliance Center](https://compliance.microsoft.com/appgovernance).</span></span>

![Microsoft 365 合规中心内的应用治理概述页面](..\media\manage-app-protection-governance\mapg-cc-overview.png)

>[!Note]
> <span data-ttu-id="f4aad-107">若要查看应用治理数据，你的登录帐户必须具有[这些角色](app-governance-get-started.md#administrator-roles)中的一个。</span><span class="sxs-lookup"><span data-stu-id="f4aad-107">Your sign-in account must have one of [these roles](app-governance-get-started.md#administrator-roles) to view any app governance data.</span></span>
>

<span data-ttu-id="f4aad-108">从该页面，你可以看到：</span><span class="sxs-lookup"><span data-stu-id="f4aad-108">From this page, you can see:</span></span>

- <span data-ttu-id="f4aad-109">对于使用 Microsoft Graph API 且已启用 OAuth 的应用：</span><span class="sxs-lookup"><span data-stu-id="f4aad-109">For OAuth-enabled apps that use the Microsoft Graph API:</span></span>

  - <span data-ttu-id="f4aad-110">你的租户中此类应用的数量</span><span class="sxs-lookup"><span data-stu-id="f4aad-110">How many are in your tenant</span></span>
  - <span data-ttu-id="f4aad-111">享有过度特权的应用数</span><span class="sxs-lookup"><span data-stu-id="f4aad-111">How many might be overprivileged</span></span>
  - <span data-ttu-id="f4aad-112">享有高级特权的应用数</span><span class="sxs-lookup"><span data-stu-id="f4aad-112">How many are high privilege</span></span>

  <span data-ttu-id="f4aad-113">根据此信息，你可以确定过度特权和高级特权应用对你的组织造成的风险级别。</span><span class="sxs-lookup"><span data-stu-id="f4aad-113">From this information, you can determine the level of risk to your organization by overprivileged and high privilege apps.</span></span>

- <span data-ttu-id="f4aad-114">对于警报：</span><span class="sxs-lookup"><span data-stu-id="f4aad-114">For alerts:</span></span>

  - <span data-ttu-id="f4aad-115">你的租户的活动警报数</span><span class="sxs-lookup"><span data-stu-id="f4aad-115">How many active alerts your tenant has</span></span>
  - <span data-ttu-id="f4aad-116">基于应用治理检测的警报（**威胁警报**）数量</span><span class="sxs-lookup"><span data-stu-id="f4aad-116">How many are based on app governance detections (**Threat alerts**)</span></span>
  - <span data-ttu-id="f4aad-117">基于你制定的应用策略的警报（**策略警报**）数量</span><span class="sxs-lookup"><span data-stu-id="f4aad-117">How many are based on app policies you have in place (**Policy alerts**)</span></span>
  - <span data-ttu-id="f4aad-118">最近 10 条警报</span><span class="sxs-lookup"><span data-stu-id="f4aad-118">The 10 latest alerts</span></span>

  <span data-ttu-id="f4aad-119">根据此信息，你可以确定生成警报的速度以及检测到的和基于策略的警报的相对数量。</span><span class="sxs-lookup"><span data-stu-id="f4aad-119">From this information, you can determine how quickly alerts are being generated and the relative number of detected and policy-based alerts.</span></span>

- <span data-ttu-id="f4aad-120">对于数据和资源访问：</span><span class="sxs-lookup"><span data-stu-id="f4aad-120">For data and resources access:</span></span>

  - <span data-ttu-id="f4aad-121">过去 90 天内的应用 API 数据访问</span><span class="sxs-lookup"><span data-stu-id="f4aad-121">The application API data access in the last 90 days</span></span>
  - <span data-ttu-id="f4aad-122">热门资源过去 90 天内的使用情况</span><span class="sxs-lookup"><span data-stu-id="f4aad-122">The usage of the top resources in the last 90 days</span></span>

  <span data-ttu-id="f4aad-123">根据此信息，你可以确定对 Microsoft 365 租户中数据的访问是否存在异常峰值。</span><span class="sxs-lookup"><span data-stu-id="f4aad-123">From this information, you can determine if there are anomalous spikes in access to the data in your Microsoft 365 tenant.</span></span>
