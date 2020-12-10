---
title: 通过攻击模拟培训获得见解
ms.author: daniha
author: danihalfin
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
description: 了解 Microsoft 365 安全中心中的攻击模拟培训如何影响员工以及如何从模拟和培训结果中获得见解。
ms.openlocfilehash: 772815add47d2e0a61187f2d687ff047a4de9c31
ms.sourcegitcommit: ee39faf3507d0edc9497117b3b2854955c959c6c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "49615176"
---
# <a name="gain-insights-through-attack-simulation-training"></a><span data-ttu-id="5dea7-103">通过攻击模拟培训获得见解</span><span class="sxs-lookup"><span data-stu-id="5dea7-103">Gain insights through Attack simulation training</span></span>

<span data-ttu-id="5dea7-104">在攻击模拟培训中，Microsoft 将根据模拟和员工培训的成果为您提供见解。</span><span class="sxs-lookup"><span data-stu-id="5dea7-104">Within Attack simulation training, Microsoft provides you with insights based on outcomes of simulations and training employees went through.</span></span> <span data-ttu-id="5dea7-105">这些见解将帮助您了解员工在威胁准备方面的进展情况，并建议后续步骤，以便更好地为你的员工和环境提供攻击的准备。</span><span class="sxs-lookup"><span data-stu-id="5dea7-105">These insights will help inform you on progress your employees are doing on threat readiness, as well as recommend next steps to better prepare your employees and your environment for attacks.</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="5dea7-106">我们不断努力为你提供扩大见解，并提供当前可用的行为影响和建议操作。</span><span class="sxs-lookup"><span data-stu-id="5dea7-106">We are continuously working on expanding insights available to you, with behavior impact and recommended actions currently available.</span></span>
<span data-ttu-id="5dea7-107">若要开始，请转到 [Microsoft 365 安全中心上的 "攻击模拟培训](https://security.microsoft.com/attacksimulator?viewid=overview)"。</span><span class="sxs-lookup"><span data-stu-id="5dea7-107">To start, head over to [Attack simulation training on the Microsoft 365 security center](https://security.microsoft.com/attacksimulator?viewid=overview).</span></span>

## <a name="behavior-impact-on-compromise-rate"></a><span data-ttu-id="5dea7-108">对泄露率的行为影响</span><span class="sxs-lookup"><span data-stu-id="5dea7-108">Behavior impact on compromise rate</span></span>

<span data-ttu-id="5dea7-109">在 "攻击模拟培训 **概述** " 选项卡上，你将发现对 **安全降低率卡的行为影响** 。</span><span class="sxs-lookup"><span data-stu-id="5dea7-109">On the Attack simulation training **Overview** tab, you'll find the **behavior impact on compromise rate** card.</span></span> <span data-ttu-id="5dea7-110">此卡片显示了员工如何处理与 **预测的折衷率** 不同的模拟。</span><span class="sxs-lookup"><span data-stu-id="5dea7-110">This card shows how employees dealt with simulation you ran in contrast to the **predicted compromise rate**.</span></span> <span data-ttu-id="5dea7-111">通过对相同的员工组运行多次模拟，可以使用这些见解跟踪员工的威胁就绪情况。</span><span class="sxs-lookup"><span data-stu-id="5dea7-111">You can use these insights to track progress in employees threat readiness by running multiple simulations against the same groups of employees.</span></span>

<span data-ttu-id="5dea7-112">在图中，可以看到：</span><span class="sxs-lookup"><span data-stu-id="5dea7-112">In the graph you can see:</span></span>

- <span data-ttu-id="5dea7-113">**预测的威胁率** ，它反映了使用攻击模拟培训的租户上使用相同类型有效负载进行模拟的平均危害率。</span><span class="sxs-lookup"><span data-stu-id="5dea7-113">**Predicted compromise rate** which reflects the average compromise rate for simulations using the same type of payload across tenants using Attack simulation training.</span></span>
- <span data-ttu-id="5dea7-114">**实际泄露率** 反映了模拟的员工所占的百分比。</span><span class="sxs-lookup"><span data-stu-id="5dea7-114">**Actual compromise rate** reflects the percentage of employees that fell for the simulation.</span></span>

<span data-ttu-id="5dea7-115">此外，还反映了受 `<number> less susceptible to phishing` 攻击影响的实际员工数与预测的威胁率之间的差异。</span><span class="sxs-lookup"><span data-stu-id="5dea7-115">Additionally, `<number> less susceptible to phishing` reflects the difference between actual number of employees compromised by the attack and the predicted compromise rate.</span></span> <span data-ttu-id="5dea7-116">这一数量的员工将来会受到类似攻击的可能性降低，同时 `<percent%> better than predicted rate` 指出了员工如何与预测的安全评级进行总体对比。</span><span class="sxs-lookup"><span data-stu-id="5dea7-116">This number of employees is less likely to be compromised by similar attacks in the future, while `<percent%> better than predicted rate` indicates how employees did overall in contrast with the predicted compromise rate.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="5dea7-117">![攻击模拟培训中的行为影响卡片概述](../../media/attack-sim-preview-behavior-impact-card.png)</span><span class="sxs-lookup"><span data-stu-id="5dea7-117">![Behavior impact card on Attack simulation training overview](../../media/attack-sim-preview-behavior-impact-card.png)</span></span>

<span data-ttu-id="5dea7-118">若要查看更详细的报告，请单击 **查看模拟和培训 efficacy 报告** ，该报告提供的信息与模拟本身的其他上下文相同，如模拟技术和目标用户总数。</span><span class="sxs-lookup"><span data-stu-id="5dea7-118">To see a more detailed report, click on **View simulations and training efficacy report** which provides the same information with additional context from the simulation itself, like simulation technique and total users targeted.</span></span>

## <a name="recommended-actions"></a><span data-ttu-id="5dea7-119">建议的操作</span><span class="sxs-lookup"><span data-stu-id="5dea7-119">Recommended actions</span></span>

<span data-ttu-id="5dea7-120">在 " [**模拟** " 选项卡](https://security.microsoft.com/attacksimulator?viewid=simulations)上，选择任意模拟将转到模拟详细信息。</span><span class="sxs-lookup"><span data-stu-id="5dea7-120">On the [**Simulations** tab](https://security.microsoft.com/attacksimulator?viewid=simulations), selecting any of the simulations will take you to simulation details.</span></span> <span data-ttu-id="5dea7-121">在这里，你将看到 " **建议的操作** " 部分。</span><span class="sxs-lookup"><span data-stu-id="5dea7-121">Here you will find the **Recommended actions** section.</span></span>

<span data-ttu-id="5dea7-122">"建议的操作" 部分详细介绍了 [Microsoft 安全分数](../mtp/microsoft-secure-score.md)中提供的建议。</span><span class="sxs-lookup"><span data-stu-id="5dea7-122">The recommended actions section details recommendations as available in [Microsoft Secure Score](../mtp/microsoft-secure-score.md).</span></span> <span data-ttu-id="5dea7-123">这些建议基于模拟中使用的有效负载，并将帮助您保护员工和环境。</span><span class="sxs-lookup"><span data-stu-id="5dea7-123">These recommendations are based on the payload used in the simulation and will help you protect your employees and your environment.</span></span> <span data-ttu-id="5dea7-124">单击每个改进操作将转到其详细信息。</span><span class="sxs-lookup"><span data-stu-id="5dea7-124">Clicking on each improvement action will take you to its details.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="5dea7-125">![攻击模拟培训的 "建议操作" 部分](../../media/attack-sim-preview-recommended-actions.png)</span><span class="sxs-lookup"><span data-stu-id="5dea7-125">![Recommendation actions section on Attack simulation training](../../media/attack-sim-preview-recommended-actions.png)</span></span>

## <a name="related-links"></a><span data-ttu-id="5dea7-126">相关链接</span><span class="sxs-lookup"><span data-stu-id="5dea7-126">Related Links</span></span>

<span data-ttu-id="5dea7-127">**攻击模拟器**[创建网络钓鱼攻击模拟](attack-simulation-training.md)和 [创建有效负载，以培训您的人员](attack-simulation-training-payloads.md)</span><span class="sxs-lookup"><span data-stu-id="5dea7-127">**Attack Simulator** [Create a phishing attack simulation](attack-simulation-training.md) and [create a payload for training your people](attack-simulation-training-payloads.md)</span></span>
