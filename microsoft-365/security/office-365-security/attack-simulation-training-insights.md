---
title: 通过攻击模拟培训获得见解
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: 管理员可以了解 Microsoft 365 安全中心中的攻击模拟培训如何影响员工，并可以从模拟和培训结果中获得见解。
ms.openlocfilehash: c283819550872691d8dd23d3921c22cb23637633
ms.sourcegitcommit: df58fd8ebe14ca98fc1be84dbfb9c29ef7ab1d62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/15/2021
ms.locfileid: "49870951"
---
# <a name="gain-insights-through-attack-simulation-training"></a><span data-ttu-id="71c14-103">通过攻击模拟培训获得见解</span><span class="sxs-lookup"><span data-stu-id="71c14-103">Gain insights through Attack simulation training</span></span>

<span data-ttu-id="71c14-104">在攻击模拟培训中，Microsoft 根据员工经过的模拟和培训的结果为您提供见解。</span><span class="sxs-lookup"><span data-stu-id="71c14-104">Within Attack simulation training, Microsoft provides you with insights based on outcomes of simulations and trainings that employees went through.</span></span> <span data-ttu-id="71c14-105">这些见解将帮助你了解员工的威胁准备进度，并推荐下一步，以更好地让员工和环境做好应对攻击的准备。</span><span class="sxs-lookup"><span data-stu-id="71c14-105">These insights will help keep you informed on the threat readiness progress of your employees, as well as recommend next steps to better prepare your employees and your environment for attacks.</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="71c14-106">我们正在不断扩展可供你获取的见解。</span><span class="sxs-lookup"><span data-stu-id="71c14-106">We are continuously working on expanding the insights that are available to you.</span></span> <span data-ttu-id="71c14-107">行为影响和推荐操作当前可用。</span><span class="sxs-lookup"><span data-stu-id="71c14-107">Behavior impact and recommended actions are currently available.</span></span> <span data-ttu-id="71c14-108">若要开始，请前往 [Microsoft 365 安全中心进行攻击模拟培训](https://security.microsoft.com/attacksimulator?viewid=overview)。</span><span class="sxs-lookup"><span data-stu-id="71c14-108">To start, head over to [Attack simulation training in the Microsoft 365 security center](https://security.microsoft.com/attacksimulator?viewid=overview).</span></span>

## <a name="behavior-impact-on-compromise-rate"></a><span data-ttu-id="71c14-109">行为对泄露率的影响</span><span class="sxs-lookup"><span data-stu-id="71c14-109">Behavior impact on compromise rate</span></span>

<span data-ttu-id="71c14-110">在 **攻击** 模拟培训的"概述"选项卡上，你将发现对入侵 **率卡的行为** 影响。</span><span class="sxs-lookup"><span data-stu-id="71c14-110">On the **Overview** tab of Attack simulation training, you'll find the **behavior impact on compromise rate** card.</span></span> <span data-ttu-id="71c14-111">此卡显示员工如何处理你运行与预测的泄露率相反 **的模拟**。</span><span class="sxs-lookup"><span data-stu-id="71c14-111">This card shows how employees dealt with the simulations you ran in contrast to the **predicted compromise rate**.</span></span> <span data-ttu-id="71c14-112">通过针对同一个员工组运行多个模拟，可以使用这些见解跟踪员工威胁准备情况的进度。</span><span class="sxs-lookup"><span data-stu-id="71c14-112">You can use these insights to track progress in employees threat readiness by running multiple simulations against the same groups of employees.</span></span>

<span data-ttu-id="71c14-113">在图中，你可以看到：</span><span class="sxs-lookup"><span data-stu-id="71c14-113">In the graph you can see:</span></span>

- <span data-ttu-id="71c14-114">**预测的泄露** 率，反映使用攻击模拟培训的其他 Microsoft 365 租户中使用相同负载类型的模拟的平均泄露率。</span><span class="sxs-lookup"><span data-stu-id="71c14-114">**Predicted compromise rate** which reflects the average compromise rate for simulations using the same type of payload across other Microsoft 365 tenants that use Attack simulation training.</span></span>
- <span data-ttu-id="71c14-115">**实际泄露** 率反映了为模拟而牺牲的员工百分比。</span><span class="sxs-lookup"><span data-stu-id="71c14-115">**Actual compromise rate** reflects the percentage of employees that fell for the simulation.</span></span>

<span data-ttu-id="71c14-116">此外，还反映了受攻击威胁的实际员工数与预测的入侵率 `<number> less susceptible to phishing` 之间的差异。</span><span class="sxs-lookup"><span data-stu-id="71c14-116">Additionally, `<number> less susceptible to phishing` reflects the difference between actual number of employees compromised by the attack and the predicted compromise rate.</span></span> <span data-ttu-id="71c14-117">此员工数量将来不太可能受到类似攻击的攻击，同时指示员工的整体行为与预测的入侵率 `<percent%> better than predicted rate` 的对比。</span><span class="sxs-lookup"><span data-stu-id="71c14-117">This number of employees is less likely to be compromised by similar attacks in the future, while `<percent%> better than predicted rate` indicates how employees did overall in contrast with the predicted compromise rate.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="71c14-118">![攻击模拟培训概述中的行为影响卡片](../../media/attack-sim-preview-behavior-impact-card.png)</span><span class="sxs-lookup"><span data-stu-id="71c14-118">![Behavior impact card on Attack simulation training overview](../../media/attack-sim-preview-behavior-impact-card.png)</span></span>

<span data-ttu-id="71c14-119">若要查看更详细的报告，请单击 **"查看模拟和培训报表"。**</span><span class="sxs-lookup"><span data-stu-id="71c14-119">To see a more detailed report, click **View simulations and training efficacy report**.</span></span> <span data-ttu-id="71c14-120">此报告提供与模拟本身的其他上下文相同的信息 (例如，模拟技术和目标用户总数) 。</span><span class="sxs-lookup"><span data-stu-id="71c14-120">This report provides the same information with additional context from the simulation itself (for example, simulation technique and total users targeted).</span></span>

## <a name="recommended-actions"></a><span data-ttu-id="71c14-121">建议的操作</span><span class="sxs-lookup"><span data-stu-id="71c14-121">Recommended actions</span></span>

<span data-ttu-id="71c14-122">在 [**"模拟"** 选项卡](https://security.microsoft.com/attacksimulator?viewid=simulations)上，选择模拟将你找到模拟详细信息，你将在这里找到"建议的操作 **"** 部分。</span><span class="sxs-lookup"><span data-stu-id="71c14-122">On the [**Simulations** tab](https://security.microsoft.com/attacksimulator?viewid=simulations), selecting a simulation will take you to the simulation details, where you'll find the **Recommended actions** section.</span></span>

<span data-ttu-id="71c14-123">建议的操作部分详细介绍了 Microsoft 安全分数 [中提供的建议](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-secure-score)。</span><span class="sxs-lookup"><span data-stu-id="71c14-123">The recommended actions section details recommendations as available in [Microsoft Secure Score](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-secure-score).</span></span> <span data-ttu-id="71c14-124">这些建议基于模拟中使用的有效负载，有助于保护员工和环境。</span><span class="sxs-lookup"><span data-stu-id="71c14-124">These recommendations are based on the payload used in the simulation, and will help you protect your employees and your environment.</span></span> <span data-ttu-id="71c14-125">单击每个改进操作将让你了解其详细信息。</span><span class="sxs-lookup"><span data-stu-id="71c14-125">Clicking on each improvement action will take you to its details.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="71c14-126">![攻击模拟培训的建议操作部分](../../media/attack-sim-preview-recommended-actions.png)</span><span class="sxs-lookup"><span data-stu-id="71c14-126">![Recommendation actions section on Attack simulation training](../../media/attack-sim-preview-recommended-actions.png)</span></span>

## <a name="related-links"></a><span data-ttu-id="71c14-127">相关链接</span><span class="sxs-lookup"><span data-stu-id="71c14-127">Related Links</span></span>

[<span data-ttu-id="71c14-128">开始使用攻击模拟培训</span><span class="sxs-lookup"><span data-stu-id="71c14-128">Get started using Attack simulation training</span></span>](attack-simulation-training-get-started.md)

[<span data-ttu-id="71c14-129">创建网络钓鱼攻击模拟</span><span class="sxs-lookup"><span data-stu-id="71c14-129">Create a phishing attack simulation</span></span>](attack-simulation-training.md)

[<span data-ttu-id="71c14-130">创建用于培训人员的有效负载</span><span class="sxs-lookup"><span data-stu-id="71c14-130">create a payload for training your people</span></span>](attack-simulation-training-payloads.md)
