---
title: 了解应用策略
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
description: 了解应用策略。
ms.openlocfilehash: 6d4ff23ca0e09f5e410d32d6ced144afc0c4bb15
ms.sourcegitcommit: 41c7f7bd5c808ee5ceca0f6efe13d4e67da0262b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/14/2021
ms.locfileid: "53420046"
---
# <a name="learn-about-app-policies"></a><span data-ttu-id="5b743-103">了解应用策略</span><span class="sxs-lookup"><span data-stu-id="5b743-103">Learn about app policies</span></span>

><span data-ttu-id="5b743-104">*[Microsoft 365 安全性与合规性许可指南](https://aka.ms/ComplianceSD)。*</span><span class="sxs-lookup"><span data-stu-id="5b743-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="5b743-105">Microsoft 应用治理可检测 Microsoft 365 租户中的异常应用行为，并生成你可以查看、调查和解决的警报。</span><span class="sxs-lookup"><span data-stu-id="5b743-105">Microsoft app governance detects anomalous app behavior in your Microsoft 365 tenant and generates alerts that you can see, investigate, and resolve.</span></span> <span data-ttu-id="5b743-106">除了此内置检测功能外，你还可以使用一组默认模板，创建自己的应用策略来生成其他警报。</span><span class="sxs-lookup"><span data-stu-id="5b743-106">Beyond this built-in detection capability, you can use a set of default templates to create your own app policies that generate other alerts.</span></span>

<span data-ttu-id="5b743-107">这些针对应用和用户模式及行为的策略可以防止用户使用不合规或恶意的应用，并限制有风险的应用访问你的租户数据。</span><span class="sxs-lookup"><span data-stu-id="5b743-107">These policies for app and user patterns and behaviors can protect your users from using non-compliant or malicious apps and limit the access of risky apps to your tenant data.</span></span>

<span data-ttu-id="5b743-108">以下是对应用策略管理所需的管理员角色的快速回顾。</span><span class="sxs-lookup"><span data-stu-id="5b743-108">Here's a quick review of required administrator roles for app policy management.</span></span>

| <span data-ttu-id="5b743-109">角色</span><span class="sxs-lookup"><span data-stu-id="5b743-109">Role</span></span> | <span data-ttu-id="5b743-110">读取策略</span><span class="sxs-lookup"><span data-stu-id="5b743-110">Read policies</span></span> | <span data-ttu-id="5b743-111">创建、更新或删除策略</span><span class="sxs-lookup"><span data-stu-id="5b743-111">Create, update, or delete policies</span></span> |
|:-------|:-----|:-------|
| <span data-ttu-id="5b743-112">合规管理员</span><span class="sxs-lookup"><span data-stu-id="5b743-112">Compliance Administrator</span></span> | ![复选标记](..\media\checkmark.png) | ![复选标记](..\media\checkmark.png) |
| <span data-ttu-id="5b743-115">合规信息读取者</span><span class="sxs-lookup"><span data-stu-id="5b743-115">Compliance Reader</span></span> | ![复选标记](..\media\checkmark.png) |  |
| <span data-ttu-id="5b743-117">全局管理员</span><span class="sxs-lookup"><span data-stu-id="5b743-117">Global Administrator</span></span> | ![复选标记](..\media\checkmark.png) | ![复选标记](..\media\checkmark.png) |
| <span data-ttu-id="5b743-120">全局读取者</span><span class="sxs-lookup"><span data-stu-id="5b743-120">Global Reader</span></span>  | ![复选标记](..\media\checkmark.png) |  |
| <span data-ttu-id="5b743-122">安全管理员</span><span class="sxs-lookup"><span data-stu-id="5b743-122">Security Administrator</span></span> | ![复选标记](..\media\checkmark.png) | ![复选标记](..\media\checkmark.png) |
| <span data-ttu-id="5b743-125">安全信息读取者</span><span class="sxs-lookup"><span data-stu-id="5b743-125">Security Reader</span></span>  | ![复选标记](..\media\checkmark.png) |  |
| <span data-ttu-id="5b743-127">安全操作员</span><span class="sxs-lookup"><span data-stu-id="5b743-127">Security Operator</span></span> | ![复选标记](..\media\checkmark.png) | ![复选标记](..\media\checkmark.png) |
||||

<!--
How app policies are the method by which MAPG detects app anomolies resulting in detection (alerts) and remediation (manual or automatic) 


CFA #2 Scenario 1: As an admin, I can quickly set up policies to govern M365 apps in my tenant using MAPG out-of-the-box templates
CFA #2 Scenario 2: As an admin, I can create customized policies to govern M365 apps in my tenant to meet my organizations requirements.
CFA #2 Scenario 3: As an admin or policy reviewer, I can view all policies created in my environment and quickly see which policies have associated alerts. 
CFA #2 Scenario 4: As an admin, I can adjust policies efficiently to meet changing needs.

App policy templates

- Basic info
- Policy settings and conditions
- Actions
- Status

--> 

## <a name="next-step"></a><span data-ttu-id="5b743-130">后续步骤</span><span class="sxs-lookup"><span data-stu-id="5b743-130">Next step</span></span>

[<span data-ttu-id="5b743-131">开始使用应用策略。</span><span class="sxs-lookup"><span data-stu-id="5b743-131">Get started with app policies.</span></span>](app-governance-app-policies-get-started.md)
