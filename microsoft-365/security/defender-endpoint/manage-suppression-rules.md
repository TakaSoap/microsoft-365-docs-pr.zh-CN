---
title: 管理 Microsoft Defender 终结点抑制规则
description: 你可能需要使用抑制规则阻止警报在门户中显示。 了解如何在 Microsoft Defender for Endpoint 中管理抑制规则。
keywords: 管理抑制， 规则， 规则名称， 范围， 操作， 警报， 打开， 关闭
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: f1549512a02fe3af71d32c6b33c69cc705de99a8
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2021
ms.locfileid: "51862123"
---
# <a name="manage-suppression-rules"></a><span data-ttu-id="1fe82-105">管理点规则</span><span class="sxs-lookup"><span data-stu-id="1fe82-105">Manage suppression rules</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="1fe82-106">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="1fe82-106">**Applies to:**</span></span>
- [<span data-ttu-id="1fe82-107">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="1fe82-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="1fe82-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1fe82-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="1fe82-109">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="1fe82-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="1fe82-110">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="1fe82-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


<span data-ttu-id="1fe82-111">在某些情况下，可能需要禁止警报显示在门户中。</span><span class="sxs-lookup"><span data-stu-id="1fe82-111">There might be scenarios where you need to suppress alerts from appearing in the portal.</span></span> <span data-ttu-id="1fe82-112">你可以为已知不安全的特定警报（如组织中已知的工具或流程）创建抑制规则。</span><span class="sxs-lookup"><span data-stu-id="1fe82-112">You can create suppression rules for specific alerts that are known to be innocuous such as known tools or processes in your organization.</span></span> <span data-ttu-id="1fe82-113">若要详细了解如何抑制警报，请参阅 [抑制警报](manage-alerts.md)。</span><span class="sxs-lookup"><span data-stu-id="1fe82-113">For more information on how to suppress alerts, see [Suppress alerts](manage-alerts.md).</span></span>

<span data-ttu-id="1fe82-114">可以查看所有抑制规则的列表，并可在一个地方管理它们。</span><span class="sxs-lookup"><span data-stu-id="1fe82-114">You can view a list of all the suppression rules and manage them in one place.</span></span> <span data-ttu-id="1fe82-115">还可以打开或关闭警报抑制规则。</span><span class="sxs-lookup"><span data-stu-id="1fe82-115">You can also turn an alert suppression rule on or off.</span></span>


1. <span data-ttu-id="1fe82-116">在导航窗格中，选择"设置  >  **""警报抑制"。**</span><span class="sxs-lookup"><span data-stu-id="1fe82-116">In the navigation pane, select **Settings** > **Alert suppression**.</span></span> <span data-ttu-id="1fe82-117">将显示组织中用户创建的抑制规则列表。</span><span class="sxs-lookup"><span data-stu-id="1fe82-117">The list of suppression rules that users in your organization have created is displayed.</span></span>

2. <span data-ttu-id="1fe82-118">通过单击规则名称旁边的复选框选择规则。</span><span class="sxs-lookup"><span data-stu-id="1fe82-118">Select a rule by clicking on the check-box beside the rule name.</span></span>

3. <span data-ttu-id="1fe82-119">单击 **"打开规则\*\*\*\*"、"编辑** 规则"或"**删除规则"。**</span><span class="sxs-lookup"><span data-stu-id="1fe82-119">Click **Turn rule on**, **Edit rule**, or  **Delete rule**.</span></span> <span data-ttu-id="1fe82-120">更改规则时，可以选择释放已取消的警报，而无论这些警报是否匹配新条件。</span><span class="sxs-lookup"><span data-stu-id="1fe82-120">When making changes to a rule, you can choose to release alerts that it has already suppressed, regardless whether or not these alerts match the new criteria.</span></span> 


## <a name="view-details-of-a-suppression-rule"></a><span data-ttu-id="1fe82-121">查看抑制规则的详细信息</span><span class="sxs-lookup"><span data-stu-id="1fe82-121">View details of a suppression rule</span></span>

1. <span data-ttu-id="1fe82-122">在导航窗格中，选择"设置  >  **""警报抑制"。**</span><span class="sxs-lookup"><span data-stu-id="1fe82-122">In the navigation pane, select **Settings** > **Alert suppression**.</span></span> <span data-ttu-id="1fe82-123">将显示组织中用户创建的抑制规则列表。</span><span class="sxs-lookup"><span data-stu-id="1fe82-123">The list of suppression rules that users in your organization have created is displayed.</span></span>

2. <span data-ttu-id="1fe82-124">单击规则名称。</span><span class="sxs-lookup"><span data-stu-id="1fe82-124">Click on a rule name.</span></span> <span data-ttu-id="1fe82-125">将显示规则的详细信息。</span><span class="sxs-lookup"><span data-stu-id="1fe82-125">Details of the rule is displayed.</span></span> <span data-ttu-id="1fe82-126">你将看到规则详细信息，如状态、范围、操作、匹配警报数、创建时间以及创建规则的日期。</span><span class="sxs-lookup"><span data-stu-id="1fe82-126">You'll see the rule details such as  status, scope, action, number of matching alerts, created by, and date when the rule was created.</span></span> <span data-ttu-id="1fe82-127">您还可以查看关联的警报和规则条件。</span><span class="sxs-lookup"><span data-stu-id="1fe82-127">You can also view associated alerts and the rule conditions.</span></span>

## <a name="related-topics"></a><span data-ttu-id="1fe82-128">相关主题</span><span class="sxs-lookup"><span data-stu-id="1fe82-128">Related topics</span></span>

- [<span data-ttu-id="1fe82-129">管理警报</span><span class="sxs-lookup"><span data-stu-id="1fe82-129">Manage alerts</span></span>](manage-alerts.md)
