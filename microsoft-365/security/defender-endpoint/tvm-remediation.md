---
title: 使用安全修复危险和漏洞管理
description: 修正通过安全建议发现的安全缺陷，并根据需要创建危险和漏洞管理。
keywords: Microsoft Defender for Endpoint tvm 修正， Microsoft Defender for Endpoint tvm， 危险和漏洞管理， 威胁 & 漏洞管理， 威胁 & 漏洞管理 修正， tvm 修正 intune， tvm 修正 sccm
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 602a38d8ad27505e81628db265681ac89218e593
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2021
ms.locfileid: "52840906"
---
# <a name="remediate-vulnerabilities-with-threat-and-vulnerability-management"></a><span data-ttu-id="af9f2-104">使用安全修复危险和漏洞管理</span><span class="sxs-lookup"><span data-stu-id="af9f2-104">Remediate vulnerabilities with threat and vulnerability management</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="af9f2-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="af9f2-105">**Applies to:**</span></span>
- [<span data-ttu-id="af9f2-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="af9f2-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="af9f2-107">威胁和漏洞管理</span><span class="sxs-lookup"><span data-stu-id="af9f2-107">Threat and vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="af9f2-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="af9f2-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="af9f2-109">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="af9f2-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="af9f2-110">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="af9f2-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

## <a name="request-remediation"></a><span data-ttu-id="af9f2-111">请求修正</span><span class="sxs-lookup"><span data-stu-id="af9f2-111">Request remediation</span></span>

<span data-ttu-id="af9f2-112">Microsoft Defender for Endpoint 中的 危险和漏洞管理 功能通过修正请求工作流填补了安全和 IT 管理员之间的空白。</span><span class="sxs-lookup"><span data-stu-id="af9f2-112">The threat and vulnerability management capability in Microsoft Defender for Endpoint bridges the gap between Security and IT administrators through the remediation request workflow.</span></span> <span data-ttu-id="af9f2-113">安全管理员（如你可以请求 IT 管理员将漏洞从安全建议页面修正到Intune）</span><span class="sxs-lookup"><span data-stu-id="af9f2-113">Security admins like you can request for the IT Administrator to remediate a vulnerability from the **Security recommendation** pages to Intune.</span></span>

### <a name="enable-microsoft-intune-connection"></a><span data-ttu-id="af9f2-114">启用Microsoft Intune连接</span><span class="sxs-lookup"><span data-stu-id="af9f2-114">Enable Microsoft Intune connection</span></span>

<span data-ttu-id="af9f2-115">若要使用此功能，请启用Microsoft Intune连接。</span><span class="sxs-lookup"><span data-stu-id="af9f2-115">To use this capability, enable your Microsoft Intune connections.</span></span> <span data-ttu-id="af9f2-116">In the Microsoft Defender 安全中心， navigate to **设置**  >  **General**  >  **Advanced features**.</span><span class="sxs-lookup"><span data-stu-id="af9f2-116">In the Microsoft Defender Security Center, navigate to **Settings** > **General** > **Advanced features**.</span></span> <span data-ttu-id="af9f2-117">向下滚动并查找Microsoft Intune **连接**。</span><span class="sxs-lookup"><span data-stu-id="af9f2-117">Scroll down and look for **Microsoft Intune connection**.</span></span> <span data-ttu-id="af9f2-118">默认情况下，切换处于关闭状态。</span><span class="sxs-lookup"><span data-stu-id="af9f2-118">By default, the toggle is turned off.</span></span> <span data-ttu-id="af9f2-119">打开连接 **Microsoft Intune\*\*\*\*打开。**</span><span class="sxs-lookup"><span data-stu-id="af9f2-119">Turn your **Microsoft Intune connection** toggle **On**.</span></span>

<span data-ttu-id="af9f2-120">**注意**：如果启用了 Intune 连接，则创建修正请求时可以选择创建 Intune 安全任务。</span><span class="sxs-lookup"><span data-stu-id="af9f2-120">**Note**: If you have the Intune connection enabled, you get an option to create an Intune security task when creating a remediation request.</span></span> <span data-ttu-id="af9f2-121">如果未设置连接，则不显示此选项。</span><span class="sxs-lookup"><span data-stu-id="af9f2-121">This option does not appear if the connection is not set.</span></span>

<span data-ttu-id="af9f2-122">有关详细信息 [，请参阅使用 Intune 修正由 Microsoft Defender for Endpoint](/intune/atp-manage-vulnerabilities) 标识的漏洞。</span><span class="sxs-lookup"><span data-stu-id="af9f2-122">See [Use Intune to remediate vulnerabilities identified by Microsoft Defender for Endpoint](/intune/atp-manage-vulnerabilities) for details.</span></span>

### <a name="remediation-request-steps"></a><span data-ttu-id="af9f2-123">修正请求步骤</span><span class="sxs-lookup"><span data-stu-id="af9f2-123">Remediation request steps</span></span>

1. <span data-ttu-id="af9f2-124">转到"危险和漏洞管理导航"菜单中，Microsoft Defender 安全中心"[**安全建议"。**](tvm-security-recommendation.md)</span><span class="sxs-lookup"><span data-stu-id="af9f2-124">Go to the threat and vulnerability management navigation menu in the Microsoft Defender Security Center, and select [**Security recommendations**](tvm-security-recommendation.md).</span></span>

2. <span data-ttu-id="af9f2-125">选择要请求修正的安全建议，然后选择"修正 **选项"。**</span><span class="sxs-lookup"><span data-stu-id="af9f2-125">Select a security recommendation you would like to request remediation for, and then select **Remediation options**.</span></span>

3. <span data-ttu-id="af9f2-126">填写表单，包括请求修正内容、适用的设备组、优先级、截止日期和可选注释。</span><span class="sxs-lookup"><span data-stu-id="af9f2-126">Fill out the form, including what you are requesting remediation for, applicable device groups, priority, due date, and optional notes.</span></span>
    1. <span data-ttu-id="af9f2-127">如果选择"注意必需"修正选项，则选择截止日期将不可用，因为没有任何特定操作。</span><span class="sxs-lookup"><span data-stu-id="af9f2-127">If you choose the "attention required" remediation option, selecting a due date will not be available since there is no specific action.</span></span>

4. <span data-ttu-id="af9f2-128">选择 **"提交请求"。**</span><span class="sxs-lookup"><span data-stu-id="af9f2-128">Select **Submit request**.</span></span> <span data-ttu-id="af9f2-129">提交修正请求将在 危险和漏洞管理创建修正活动项，可用于监视此建议的修正进度。</span><span class="sxs-lookup"><span data-stu-id="af9f2-129">Submitting a remediation request creates a remediation activity item within threat and vulnerability management, which can be used for monitoring the remediation progress for this recommendation.</span></span> <span data-ttu-id="af9f2-130">这不会触发修正或对设备应用任何更改。</span><span class="sxs-lookup"><span data-stu-id="af9f2-130">This will not trigger a remediation or apply any changes to devices.</span></span>

5. <span data-ttu-id="af9f2-131">将新请求通知 IT 管理员，让他们登录到 Intune 以批准或拒绝请求并启动程序包部署。</span><span class="sxs-lookup"><span data-stu-id="af9f2-131">Notify your IT Administrator about the new request and have them log into Intune to approve or reject the request and start a package deployment.</span></span>

6. <span data-ttu-id="af9f2-132">转到" [**修正"**](tvm-remediation.md) 页以查看修正请求的状态。</span><span class="sxs-lookup"><span data-stu-id="af9f2-132">Go to the [**Remediation**](tvm-remediation.md) page to view the status of your remediation request.</span></span>

<span data-ttu-id="af9f2-133">如果你想要检查票证在 Intune 中的显示方式，请参阅使用 [Intune](/intune/atp-manage-vulnerabilities) 修正由 Microsoft Defender for Endpoint 标识的漏洞，了解详细信息。</span><span class="sxs-lookup"><span data-stu-id="af9f2-133">If you want to check how the ticket shows up in Intune, see [Use Intune to remediate vulnerabilities identified by Microsoft Defender for Endpoint](/intune/atp-manage-vulnerabilities) for details.</span></span>

>[!NOTE]
><span data-ttu-id="af9f2-134">如果你的请求涉及修正超过 10，000 台设备，我们只能发送 10，000 台设备以修正 Intune。</span><span class="sxs-lookup"><span data-stu-id="af9f2-134">If your request involves remediating more than 10,000 devices, we can only send 10,000 devices for remediation to Intune.</span></span>

<span data-ttu-id="af9f2-135">确定组织的网络安全弱点并将其映射到可操作的安全建议后，开始创建安全任务。 [](tvm-security-recommendation.md)</span><span class="sxs-lookup"><span data-stu-id="af9f2-135">After your organization's cybersecurity weaknesses are identified and mapped to actionable [security recommendations](tvm-security-recommendation.md), start creating security tasks.</span></span> <span data-ttu-id="af9f2-136">通过与创建修正票证Microsoft Intune集成来创建任务。</span><span class="sxs-lookup"><span data-stu-id="af9f2-136">You can create tasks through the integration with Microsoft Intune where remediation tickets are created.</span></span>

<span data-ttu-id="af9f2-137">通过修正安全建议，降低组织对漏洞的暴露程度，并增加安全配置。</span><span class="sxs-lookup"><span data-stu-id="af9f2-137">Lower your organization's exposure from vulnerabilities and increase your security configuration by remediating the security recommendations.</span></span>

## <a name="view-your-remediation-activities"></a><span data-ttu-id="af9f2-138">查看修正活动</span><span class="sxs-lookup"><span data-stu-id="af9f2-138">View your remediation activities</span></span>

<span data-ttu-id="af9f2-139">当你从"安全建议"页提交修正请求时，它会启动修正活动。</span><span class="sxs-lookup"><span data-stu-id="af9f2-139">When you submit a remediation request from the Security recommendations page, it kicks-off a remediation activity.</span></span> <span data-ttu-id="af9f2-140">将创建一个可在"修正"危险和漏洞管理跟踪的安全任务，并创建一个修正Microsoft Intune。</span><span class="sxs-lookup"><span data-stu-id="af9f2-140">A security task is created that can be tracked in the threat and vulnerability management **Remediation** page, and a remediation ticket is created in Microsoft Intune.</span></span>

<span data-ttu-id="af9f2-141">如果选择"注意需要"修正选项，则没有进度栏、票证状态或截止日期，因为我们可以监视任何实际操作。</span><span class="sxs-lookup"><span data-stu-id="af9f2-141">If you chose the "attention required" remediation option, there will be no progress bar, ticket status, or due date since there is no actual action we can monitor.</span></span>

<span data-ttu-id="af9f2-142">进入"修正"页后，选择要查看的修正活动。</span><span class="sxs-lookup"><span data-stu-id="af9f2-142">Once you are in the Remediation page, select the remediation activity that you want to view.</span></span> <span data-ttu-id="af9f2-143">你可以按照修正步骤、跟踪进度、查看相关建议、导出到 CSV 或标记为完成。</span><span class="sxs-lookup"><span data-stu-id="af9f2-143">You can follow the remediation steps, track progress, view the related recommendation, export to CSV, or mark as complete.</span></span>
<span data-ttu-id="af9f2-144">![包含所选修正活动的"修正"页的示例，以及该活动的列出说明、IT 服务和设备管理工具以及设备修正进度的飞出图。](images/remediation_flyouteolsw.png)</span><span class="sxs-lookup"><span data-stu-id="af9f2-144">![Example of the Remediation page, with a selected remediation activity, and that activity's flyout listing the description, IT service and device management tools, and device remediation progress.](images/remediation_flyouteolsw.png)</span></span>

>[!NOTE]
> <span data-ttu-id="af9f2-145">已完成的修正活动保留期为 180 天。</span><span class="sxs-lookup"><span data-stu-id="af9f2-145">There is a 180 day retention period for completed remediation activities.</span></span> <span data-ttu-id="af9f2-146">若要使"修正"页以最佳方式执行，修正活动将在完成后 6 个月后删除。</span><span class="sxs-lookup"><span data-stu-id="af9f2-146">To keep the Remediation page performing optimally, the remediation activity will be removed 6 months after its completion.</span></span>

### <a name="completed-by-column"></a><span data-ttu-id="af9f2-147">按列完成</span><span class="sxs-lookup"><span data-stu-id="af9f2-147">Completed by column</span></span>

<span data-ttu-id="af9f2-148">使用"修正"页上的"完成者"列跟踪哪些人关闭了修正活动。</span><span class="sxs-lookup"><span data-stu-id="af9f2-148">Track who closed the remediation activity with the "Completed by" column on the Remediation page.</span></span>

- <span data-ttu-id="af9f2-149">**电子邮件地址**：手动完成任务的人的电子邮件</span><span class="sxs-lookup"><span data-stu-id="af9f2-149">**Email address**: The email of the person who manually completed the task</span></span>
- <span data-ttu-id="af9f2-150">**系统确认**：在已修正 (自动完成任务) </span><span class="sxs-lookup"><span data-stu-id="af9f2-150">**System confirmation**: The task was automatically completed (all devices remediated)</span></span>
- <span data-ttu-id="af9f2-151">**N/A：** 信息不可用，因为我们不知道此旧任务的完成情况</span><span class="sxs-lookup"><span data-stu-id="af9f2-151">**N/A**: Information is not available because we don't know how this older task was completed</span></span>

![由具有两行的列创建和完成。](images/tvm-completed-by.png)

### <a name="top-remediation-activities-in-the-dashboard"></a><span data-ttu-id="af9f2-154">仪表板中的热门修正活动</span><span class="sxs-lookup"><span data-stu-id="af9f2-154">Top remediation activities in the dashboard</span></span>

<span data-ttu-id="af9f2-155">在 **仪表板 中查看** 危险和漏洞管理 [活动](tvm-dashboard-insights.md)。</span><span class="sxs-lookup"><span data-stu-id="af9f2-155">View **Top remediation activities** in the [threat and vulnerability management dashboard](tvm-dashboard-insights.md).</span></span> <span data-ttu-id="af9f2-156">选择任意条目以转到"修正 **"** 页。</span><span class="sxs-lookup"><span data-stu-id="af9f2-156">Select any of the entries to go to the **Remediation** page.</span></span> <span data-ttu-id="af9f2-157">可以在 IT 管理员团队修正任务后将修正活动标记为已完成。</span><span class="sxs-lookup"><span data-stu-id="af9f2-157">You can mark the remediation activity as completed after the IT admin team remediates the task.</span></span>

![Top 修正活动卡片的示例，该表列出了根据安全建议生成的顶部活动。](images/tvm-remediation-activities-card.png)

## <a name="related-articles"></a><span data-ttu-id="af9f2-159">相关文章</span><span class="sxs-lookup"><span data-stu-id="af9f2-159">Related articles</span></span>

- [<span data-ttu-id="af9f2-160">威胁和漏洞管理概述</span><span class="sxs-lookup"><span data-stu-id="af9f2-160">Threat and vulnerability management overview</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="af9f2-161">仪表板</span><span class="sxs-lookup"><span data-stu-id="af9f2-161">Dashboard</span></span>](tvm-dashboard-insights.md)
- [<span data-ttu-id="af9f2-162">安全性建议</span><span class="sxs-lookup"><span data-stu-id="af9f2-162">Security recommendations</span></span>](tvm-security-recommendation.md)