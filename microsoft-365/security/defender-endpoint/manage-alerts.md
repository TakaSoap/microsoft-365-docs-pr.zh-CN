---
title: 管理 Microsoft Defender for Endpoint 警报
description: 使用"管理警报"菜单更改警报的状态、创建抑制规则以隐藏警报、提交注释并查看单个警报的更改历史记录。
keywords: 管理警报， 管理， 警报， 状态， 新建， 正在进行， 已解决， 解决警报， 抑制， 抑制， 规则， 上下文， 历史记录， 注释， 更改
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
ms.openlocfilehash: 5acec4e9b43c8af7f85fadd31caefbb15e227029
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51054946"
---
# <a name="manage-microsoft-defender-for-endpoint-alerts"></a><span data-ttu-id="8e3e4-104">管理 Microsoft Defender for Endpoint 警报</span><span class="sxs-lookup"><span data-stu-id="8e3e4-104">Manage Microsoft Defender for Endpoint alerts</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="8e3e4-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="8e3e4-105">**Applies to:**</span></span>
- [<span data-ttu-id="8e3e4-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="8e3e4-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="8e3e4-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8e3e4-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> <span data-ttu-id="8e3e4-108">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="8e3e4-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="8e3e4-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="8e3e4-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-managealerts-abovefoldlink)

<span data-ttu-id="8e3e4-110">Defender for Endpoint 通过警报通知你可能的恶意事件、属性和上下文信息。</span><span class="sxs-lookup"><span data-stu-id="8e3e4-110">Defender for Endpoint notifies you of possible malicious events, attributes, and contextual information through alerts.</span></span> <span data-ttu-id="8e3e4-111">新警报的摘要显示在安全操作仪表板中，并且可以访问警报 **队列中的所有警报**。</span><span class="sxs-lookup"><span data-stu-id="8e3e4-111">A summary of new alerts is displayed in the **Security operations dashboard**, and you can access all alerts in the **Alerts queue**.</span></span>

<span data-ttu-id="8e3e4-112">可以通过在警报队列中选择警报或单个设备的设备页面的警报选项卡来管理警报。 </span><span class="sxs-lookup"><span data-stu-id="8e3e4-112">You can manage alerts by selecting an alert in the **Alerts queue**, or the **Alerts** tab of the Device page for an individual device.</span></span>

<span data-ttu-id="8e3e4-113">在任一位置选择警报将打开警报 **管理窗格**。</span><span class="sxs-lookup"><span data-stu-id="8e3e4-113">Selecting an alert in either of those places brings up the **Alert management pane**.</span></span>

![警报管理窗格和警报队列的图像](images/atp-alerts-selected.png)

## <a name="link-to-another-incident"></a><span data-ttu-id="8e3e4-115">链接到其他事件</span><span class="sxs-lookup"><span data-stu-id="8e3e4-115">Link to another incident</span></span>
<span data-ttu-id="8e3e4-116">你可以从警报创建新事件或链接到现有事件。</span><span class="sxs-lookup"><span data-stu-id="8e3e4-116">You can create a new incident from the alert or link to an existing incident.</span></span> 

## <a name="assign-alerts"></a><span data-ttu-id="8e3e4-117">分配警报</span><span class="sxs-lookup"><span data-stu-id="8e3e4-117">Assign alerts</span></span>
<span data-ttu-id="8e3e4-118">如果尚未分配警报，可以选择"分配给 **我** "，将警报分配给自己。</span><span class="sxs-lookup"><span data-stu-id="8e3e4-118">If an alert is not yet assigned, you can select **Assign to me** to assign the alert to yourself.</span></span>


## <a name="suppress-alerts"></a><span data-ttu-id="8e3e4-119">抑制警报</span><span class="sxs-lookup"><span data-stu-id="8e3e4-119">Suppress alerts</span></span>
<span data-ttu-id="8e3e4-120">在某些情况下，可能需要禁止警报显示在 Microsoft Defender 安全中心中。</span><span class="sxs-lookup"><span data-stu-id="8e3e4-120">There might be scenarios where you need to suppress alerts from appearing in Microsoft Defender Security Center.</span></span> <span data-ttu-id="8e3e4-121">通过 Defender for Endpoint，你可以为已知不安全的特定警报（如组织中已知的工具或流程）创建抑制规则。</span><span class="sxs-lookup"><span data-stu-id="8e3e4-121">Defender for Endpoint lets you create suppression rules for specific alerts that are known to be innocuous such as known tools or processes in your organization.</span></span>

<span data-ttu-id="8e3e4-122">可以从现有警报创建抑制规则。</span><span class="sxs-lookup"><span data-stu-id="8e3e4-122">Suppression rules can be created from an existing alert.</span></span> <span data-ttu-id="8e3e4-123">如果需要，可以禁用和重新启用它们。</span><span class="sxs-lookup"><span data-stu-id="8e3e4-123">They can be disabled and reenabled if needed.</span></span>

<span data-ttu-id="8e3e4-124">创建抑制规则时，它将从创建该规则时开始生效。</span><span class="sxs-lookup"><span data-stu-id="8e3e4-124">When a suppression rule is created, it will take effect from the point when the rule is created.</span></span> <span data-ttu-id="8e3e4-125">在规则创建之前，该规则不会影响队列中已有的现有警报。</span><span class="sxs-lookup"><span data-stu-id="8e3e4-125">The rule will not affect existing alerts already in the queue, prior to the rule creation.</span></span> <span data-ttu-id="8e3e4-126">规则将仅应用于满足创建规则后设置的条件的警报。</span><span class="sxs-lookup"><span data-stu-id="8e3e4-126">The rule will only be applied on alerts that satisfy the conditions set after the rule is created.</span></span>

<span data-ttu-id="8e3e4-127">抑制规则有两个上下文可供选择：</span><span class="sxs-lookup"><span data-stu-id="8e3e4-127">There are two contexts for a suppression rule that you can choose from:</span></span>

- <span data-ttu-id="8e3e4-128">**抑制此设备的警报**</span><span class="sxs-lookup"><span data-stu-id="8e3e4-128">**Suppress alert on this device**</span></span>
- <span data-ttu-id="8e3e4-129">**抑制我的组织的警报**</span><span class="sxs-lookup"><span data-stu-id="8e3e4-129">**Suppress alert in my organization**</span></span>

<span data-ttu-id="8e3e4-130">规则的上下文允许你定制门户中显示的内容，并确保门户中只显示真实的安全警报。</span><span class="sxs-lookup"><span data-stu-id="8e3e4-130">The context of the rule lets you tailor what gets surfaced into the portal and ensure that only real security alerts are surfaced into the portal.</span></span>

<span data-ttu-id="8e3e4-131">可以使用下表中的示例来帮助你选择抑制规则的上下文：</span><span class="sxs-lookup"><span data-stu-id="8e3e4-131">You can use the examples in the following table to help you choose the context for a suppression rule:</span></span>

| <span data-ttu-id="8e3e4-132">**Context**</span><span class="sxs-lookup"><span data-stu-id="8e3e4-132">**Context**</span></span>                           | <span data-ttu-id="8e3e4-133">**定义**</span><span class="sxs-lookup"><span data-stu-id="8e3e4-133">**Definition**</span></span>                                                                                                                                              | <span data-ttu-id="8e3e4-134">**示例方案**</span><span class="sxs-lookup"><span data-stu-id="8e3e4-134">**Example scenarios**</span></span>                                                                                                                                                                                                  |
|:--------------------------------------|:------------------------------------------------------------------------------------------------------------------------------------------------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="8e3e4-135">**抑制此设备的警报**</span><span class="sxs-lookup"><span data-stu-id="8e3e4-135">**Suppress alert on this device**</span></span>    | <span data-ttu-id="8e3e4-136">将仅抑制具有相同的警报标题和特定设备的警报。</span><span class="sxs-lookup"><span data-stu-id="8e3e4-136">Alerts with the same alert title and on that specific device only will be suppressed.</span></span> <br /><br /><span data-ttu-id="8e3e4-137">不会抑制该设备上所有其他警报。</span><span class="sxs-lookup"><span data-stu-id="8e3e4-137">All other alerts on that device will not be suppressed.</span></span> | <ul><li><span data-ttu-id="8e3e4-138">安全研究人员正在调查用于攻击组织中其他设备的恶意脚本。</span><span class="sxs-lookup"><span data-stu-id="8e3e4-138">A security researcher is investigating a malicious script that has been used to attack other devices in your organization.</span></span></li><li><span data-ttu-id="8e3e4-139">开发人员定期为团队创建 PowerShell 脚本。</span><span class="sxs-lookup"><span data-stu-id="8e3e4-139">A developer regularly creates PowerShell scripts for their team.</span></span></li></ul> |
| <span data-ttu-id="8e3e4-140">**抑制我的组织的警报**</span><span class="sxs-lookup"><span data-stu-id="8e3e4-140">**Suppress alert in my organization**</span></span> | <span data-ttu-id="8e3e4-141">将抑制任何设备上具有相同的警报标题的警报。</span><span class="sxs-lookup"><span data-stu-id="8e3e4-141">Alerts with the same alert title on any device will be suppressed.</span></span>                                                                                         | <ul><li><span data-ttu-id="8e3e4-142">组织中的每个人都使用良好的管理工具。</span><span class="sxs-lookup"><span data-stu-id="8e3e4-142">A benign administrative tool is used by everyone in your organization.</span></span></li></ul>                                                                                                                               |

### <a name="suppress-an-alert-and-create-a-new-suppression-rule"></a><span data-ttu-id="8e3e4-143">抑制警报并创建新的抑制规则：</span><span class="sxs-lookup"><span data-stu-id="8e3e4-143">Suppress an alert and create a new suppression rule:</span></span>
<span data-ttu-id="8e3e4-144">创建自定义规则以控制何时抑制或解决警报。</span><span class="sxs-lookup"><span data-stu-id="8e3e4-144">Create custom rules to control when alerts are suppressed, or resolved.</span></span> <span data-ttu-id="8e3e4-145">通过指定警报标题、泄露指示器和条件，可以控制何时抑制警报的上下文。</span><span class="sxs-lookup"><span data-stu-id="8e3e4-145">You can control the context for when an alert is suppressed by specifying the alert title, Indicator of compromise, and the conditions.</span></span> <span data-ttu-id="8e3e4-146">指定上下文后，您将能够在警报上配置操作和范围。</span><span class="sxs-lookup"><span data-stu-id="8e3e4-146">After specifying the context, you’ll be able to configure the action and scope on the alert.</span></span> 

1. <span data-ttu-id="8e3e4-147">选择要抑制的警报。</span><span class="sxs-lookup"><span data-stu-id="8e3e4-147">Select the alert you'd like to suppress.</span></span> <span data-ttu-id="8e3e4-148">此时将打开警报 **管理** 窗格。</span><span class="sxs-lookup"><span data-stu-id="8e3e4-148">This brings up the **Alert management** pane.</span></span>

2.  <span data-ttu-id="8e3e4-149">选择 **"创建抑制规则"。**</span><span class="sxs-lookup"><span data-stu-id="8e3e4-149">Select **Create a suppression rule**.</span></span>

    <span data-ttu-id="8e3e4-150">可以使用这些属性创建抑制条件。</span><span class="sxs-lookup"><span data-stu-id="8e3e4-150">You can create a suppression condition using these attributes.</span></span> <span data-ttu-id="8e3e4-151">在每种条件之间应用 AND 运算符，因此仅在满足所有条件时，才进行抑制。</span><span class="sxs-lookup"><span data-stu-id="8e3e4-151">An AND operator is applied between each condition, so suppression occurs only if all conditions are met.</span></span>
    
    * <span data-ttu-id="8e3e4-152">文件 SHA1</span><span class="sxs-lookup"><span data-stu-id="8e3e4-152">File SHA1</span></span>
    * <span data-ttu-id="8e3e4-153">文件名 - 支持通配符</span><span class="sxs-lookup"><span data-stu-id="8e3e4-153">File name - wildcard supported</span></span>
    * <span data-ttu-id="8e3e4-154">文件夹路径 - 支持通配符</span><span class="sxs-lookup"><span data-stu-id="8e3e4-154">Folder path - wildcard supported</span></span>
    * <span data-ttu-id="8e3e4-155">IP 地址</span><span class="sxs-lookup"><span data-stu-id="8e3e4-155">IP address</span></span>
    * <span data-ttu-id="8e3e4-156">URL - 支持通配符</span><span class="sxs-lookup"><span data-stu-id="8e3e4-156">URL - wildcard supported</span></span>
    * <span data-ttu-id="8e3e4-157">命令行 - 支持通配符</span><span class="sxs-lookup"><span data-stu-id="8e3e4-157">Command line - wildcard supported</span></span>

3. <span data-ttu-id="8e3e4-158">选择 **"触发 IOC"。**</span><span class="sxs-lookup"><span data-stu-id="8e3e4-158">Select the **Triggering IOC**.</span></span>
    
4. <span data-ttu-id="8e3e4-159">指定警报的操作和范围。</span><span class="sxs-lookup"><span data-stu-id="8e3e4-159">Specify the action and scope on the alert.</span></span> <br>
   <span data-ttu-id="8e3e4-160">你可以自动解决警报或在门户中隐藏它。</span><span class="sxs-lookup"><span data-stu-id="8e3e4-160">You can automatically resolve an alert or hide it from the portal.</span></span> <span data-ttu-id="8e3e4-161">自动解决的警报将显示在警报队列、警报页面和设备时间线的解析部分中，并且显示为跨 Defender for Endpoint API 解析。</span><span class="sxs-lookup"><span data-stu-id="8e3e4-161">Alerts that are automatically resolved will appear in the resolved section of the alerts queue, alert page, and device timeline and will appear as resolved across Defender for Endpoint APIs.</span></span> <br><br> <span data-ttu-id="8e3e4-162">在设备的关联警报和仪表板上，标记为隐藏的警报都将从整个系统中抑制，并且不会跨 Defender for Endpoint API 流式传输。</span><span class="sxs-lookup"><span data-stu-id="8e3e4-162">Alerts that are marked as hidden will be suppressed from the entire system, both on the device's associated alerts and from the dashboard and will not be streamed across Defender for Endpoint APIs.</span></span>


5. <span data-ttu-id="8e3e4-163">输入规则名称和注释。</span><span class="sxs-lookup"><span data-stu-id="8e3e4-163">Enter a rule name and a comment.</span></span>

6. <span data-ttu-id="8e3e4-164">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="8e3e4-164">Click **Save**.</span></span>

#### <a name="view-the-list-of-suppression-rules"></a><span data-ttu-id="8e3e4-165">查看抑制规则列表</span><span class="sxs-lookup"><span data-stu-id="8e3e4-165">View the list of suppression rules</span></span>

1. <span data-ttu-id="8e3e4-166">在导航窗格中，选择"设置  >  **""警报抑制"。**</span><span class="sxs-lookup"><span data-stu-id="8e3e4-166">In the navigation pane, select **Settings** > **Alert suppression**.</span></span>

2. <span data-ttu-id="8e3e4-167">抑制规则列表显示组织中用户已创建的所有规则。</span><span class="sxs-lookup"><span data-stu-id="8e3e4-167">The list of suppression rules shows all the rules that users in your organization have created.</span></span>

<span data-ttu-id="8e3e4-168">有关管理抑制规则的信息，请参阅 [管理抑制规则](manage-suppression-rules.md)</span><span class="sxs-lookup"><span data-stu-id="8e3e4-168">For more information on managing suppression rules, see [Manage suppression rules](manage-suppression-rules.md)</span></span>

## <a name="change-the-status-of-an-alert"></a><span data-ttu-id="8e3e4-169">更改警报的状态</span><span class="sxs-lookup"><span data-stu-id="8e3e4-169">Change the status of an alert</span></span>

<span data-ttu-id="8e3e4-170">你可以将警报分类为 (、正在进行或已解决) 调查时更改其状态。 </span><span class="sxs-lookup"><span data-stu-id="8e3e4-170">You can categorize alerts (as **New**, **In Progress**, or **Resolved**) by changing their status as your investigation progresses.</span></span> <span data-ttu-id="8e3e4-171">这可帮助你组织和管理团队可以如何响应警报。</span><span class="sxs-lookup"><span data-stu-id="8e3e4-171">This helps you organize and manage how your team can respond to alerts.</span></span>

<span data-ttu-id="8e3e4-172">例如，团队主管可以审阅所有 **新** 警报，并决定将其分配给进行中 **队列** ，以进一步分析。</span><span class="sxs-lookup"><span data-stu-id="8e3e4-172">For example, a team leader can review all **New** alerts, and decide to assign them to the **In Progress** queue for further analysis.</span></span>

<span data-ttu-id="8e3e4-173">或者，如果团队领导知道警报是无害的、来自与安全管理员) 无关的设备（例如属于安全管理员 () 的设备）或正在通过早期警报处理，则他们可以将警报分配给已解决队列。</span><span class="sxs-lookup"><span data-stu-id="8e3e4-173">Alternatively, the team leader might assign the alert to the **Resolved** queue if they know the alert is benign, coming from a device that is irrelevant (such as one belonging to a security administrator), or is being dealt with through an earlier alert.</span></span>



## <a name="alert-classification"></a><span data-ttu-id="8e3e4-174">警报分类</span><span class="sxs-lookup"><span data-stu-id="8e3e4-174">Alert classification</span></span>
<span data-ttu-id="8e3e4-175">可以选择不设置分类，也可以指定警报是真警报还是假警报。</span><span class="sxs-lookup"><span data-stu-id="8e3e4-175">You can choose not to set a classification, or specify whether an alert is a true alert or a false alert.</span></span> <span data-ttu-id="8e3e4-176">提供真正的正/误报分类非常重要。</span><span class="sxs-lookup"><span data-stu-id="8e3e4-176">It's important to provide the classification of true positive/false positive.</span></span> <span data-ttu-id="8e3e4-177">此分类用于监视警报质量，使警报更加准确。</span><span class="sxs-lookup"><span data-stu-id="8e3e4-177">This classification is used to monitor alert quality, and make alerts more accurate.</span></span> <span data-ttu-id="8e3e4-178">"确定"字段定义"真正的正"分类的其他保真度。</span><span class="sxs-lookup"><span data-stu-id="8e3e4-178">The "determination" field defines additional fidelity for a "true positive" classification.</span></span> 

## <a name="add-comments-and-view-the-history-of-an-alert"></a><span data-ttu-id="8e3e4-179">添加注释并查看警报历史记录</span><span class="sxs-lookup"><span data-stu-id="8e3e4-179">Add comments and view the history of an alert</span></span>
<span data-ttu-id="8e3e4-180">你可以添加注释并查看有关警报的历史事件，以查看之前对警报所做的更改。</span><span class="sxs-lookup"><span data-stu-id="8e3e4-180">You can add comments and view historical events about an alert to see previous changes made to the alert.</span></span>

<span data-ttu-id="8e3e4-181">只要对警报进行了更改或注释，就会记录在"注释和历史记录" **部分** 。</span><span class="sxs-lookup"><span data-stu-id="8e3e4-181">Whenever a change or comment is made to an alert, it is recorded in the **Comments and history** section.</span></span>

<span data-ttu-id="8e3e4-182">添加的备注会立即显示在窗格中。</span><span class="sxs-lookup"><span data-stu-id="8e3e4-182">Added comments instantly appear on the pane.</span></span>


## <a name="related-topics"></a><span data-ttu-id="8e3e4-183">相关主题</span><span class="sxs-lookup"><span data-stu-id="8e3e4-183">Related topics</span></span>
- [<span data-ttu-id="8e3e4-184">管理抑制规则</span><span class="sxs-lookup"><span data-stu-id="8e3e4-184">Manage suppression rules</span></span>](manage-suppression-rules.md)
- [<span data-ttu-id="8e3e4-185">查看和组织 Microsoft Defender 终结点警报队列</span><span class="sxs-lookup"><span data-stu-id="8e3e4-185">View and organize the Microsoft Defender for Endpoint Alerts queue</span></span>](alerts-queue.md)
- [<span data-ttu-id="8e3e4-186">调查 Microsoft Defender for Endpoint 警报</span><span class="sxs-lookup"><span data-stu-id="8e3e4-186">Investigate Microsoft Defender for Endpoint alerts</span></span>](investigate-alerts.md)
- [<span data-ttu-id="8e3e4-187">调查与 Microsoft Defender for Endpoint 警报关联的文件</span><span class="sxs-lookup"><span data-stu-id="8e3e4-187">Investigate a file associated with a Microsoft Defender for Endpoint alert</span></span>](investigate-files.md)
- [<span data-ttu-id="8e3e4-188">调查 Microsoft Defender 终结点设备列表中的设备</span><span class="sxs-lookup"><span data-stu-id="8e3e4-188">Investigate devices in the Microsoft Defender for Endpoint Devices list</span></span>](investigate-machines.md)
- [<span data-ttu-id="8e3e4-189">调查与 Microsoft Defender for Endpoint 警报关联的 IP 地址</span><span class="sxs-lookup"><span data-stu-id="8e3e4-189">Investigate an IP address associated with a Microsoft Defender for Endpoint alert</span></span>](investigate-ip.md)
- [<span data-ttu-id="8e3e4-190">调查与 Microsoft Defender for Endpoint 警报关联的域</span><span class="sxs-lookup"><span data-stu-id="8e3e4-190">Investigate a domain associated with a Microsoft Defender for Endpoint alert</span></span>](investigate-domain.md)
- [<span data-ttu-id="8e3e4-191">调查 Microsoft Defender for Endpoint 中的用户帐户</span><span class="sxs-lookup"><span data-stu-id="8e3e4-191">Investigate a user account in Microsoft Defender for Endpoint</span></span>](investigate-user.md)
