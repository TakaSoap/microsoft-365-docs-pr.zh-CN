---
title: 访问操作中心以查看修正操作
description: 使用操作中心查看自动调查后的详细信息和结果
keywords: 操作， 中心， autoir， 自动化， 调查， 响应， 修正
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
author: JoeDavies-MSFT
ms.author: josephd
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: how-to
ms.reviewer: ramarom, evaldm, isco, mabraitm, chriggs
ms.date: 01/28/2021
ms.technology: mde
ms.openlocfilehash: cc806678bbb5ac19f7c4e035efb52b6ba7d1edb1
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844906"
---
# <a name="visit-the-action-center-to-see-remediation-actions"></a><span data-ttu-id="02f34-104">访问操作中心以查看修正操作</span><span class="sxs-lookup"><span data-stu-id="02f34-104">Visit the Action center to see remediation actions</span></span>

<span data-ttu-id="02f34-105">在自动调查期间和之后，将确定威胁检测的修正操作。</span><span class="sxs-lookup"><span data-stu-id="02f34-105">During and after an automated investigation, remediation actions for threat detections are identified.</span></span> <span data-ttu-id="02f34-106">根据特定威胁和为组织配置 [Microsoft Defender for Endpoint](/windows/security/threat-protection) 如何，将自动执行一些修正操作，而其他一些需要审批。</span><span class="sxs-lookup"><span data-stu-id="02f34-106">Depending on the particular threat and how [Microsoft Defender for Endpoint](/windows/security/threat-protection) is configured for your organization, some remediation actions are taken automatically, and others require approval.</span></span> <span data-ttu-id="02f34-107">如果你是组织的安全运营团队的一员，可以在操作中心中查看挂起和已完成的 **修正操作**。 [](manage-auto-investigation.md#remediation-actions)</span><span class="sxs-lookup"><span data-stu-id="02f34-107">If you're part of your organization's security operations team, you can view pending and completed [remediation actions](manage-auto-investigation.md#remediation-actions) in the **Action center**.</span></span> 


<span data-ttu-id="02f34-108">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="02f34-108">**Applies to:**</span></span>
- [<span data-ttu-id="02f34-109">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="02f34-109">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="02f34-110">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="02f34-110">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

## <a name="new-a-unified-action-center"></a><span data-ttu-id="02f34-111"> (NEW！) 统一操作中心</span><span class="sxs-lookup"><span data-stu-id="02f34-111">(NEW!) A unified Action center</span></span>


<span data-ttu-id="02f34-112">我们很高兴宣布新的统一操作中心 [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) () ！</span><span class="sxs-lookup"><span data-stu-id="02f34-112">We are pleased to announce a new, unified Action center ([https://security.microsoft.com/action-center](https://security.microsoft.com/action-center))!</span></span>

:::image type="content" source="images/mde-action-center-unified.png" alt-text="安全中心Microsoft 365中心":::

<span data-ttu-id="02f34-114">下表将新的统一操作中心与以前的操作中心进行比较。</span><span class="sxs-lookup"><span data-stu-id="02f34-114">The following table compares the new, unified Action center to the previous Action center.</span></span>

|<span data-ttu-id="02f34-115">新的统一操作中心</span><span class="sxs-lookup"><span data-stu-id="02f34-115">The new, unified Action center</span></span>  |<span data-ttu-id="02f34-116">以前的操作中心</span><span class="sxs-lookup"><span data-stu-id="02f34-116">The previous Action center</span></span>  |
|---------|---------|
|<span data-ttu-id="02f34-117">在一个位置列出设备和电子邮件的挂起和已完成操作</span><span class="sxs-lookup"><span data-stu-id="02f34-117">Lists pending and completed actions for devices and email in one location</span></span> <br/><span data-ttu-id="02f34-118"> (Microsoft [Defender for Endpoint 和](microsoft-defender-endpoint.md) [Microsoft Defender for Office 365) ](/microsoft-365/security/office-365-security/office-365-atp)</span><span class="sxs-lookup"><span data-stu-id="02f34-118">([Microsoft Defender for Endpoint](microsoft-defender-endpoint.md) plus [Microsoft Defender for Office 365](/microsoft-365/security/office-365-security/office-365-atp))</span></span>|<span data-ttu-id="02f34-119">列出设备的挂起和已完成操作</span><span class="sxs-lookup"><span data-stu-id="02f34-119">Lists pending and completed actions for devices</span></span> <br/> <span data-ttu-id="02f34-120"> (Microsoft [Defender for Endpoint) ](microsoft-defender-endpoint.md)</span><span class="sxs-lookup"><span data-stu-id="02f34-120">([Microsoft Defender for Endpoint](microsoft-defender-endpoint.md) only)</span></span>   |
|<span data-ttu-id="02f34-121">位于：</span><span class="sxs-lookup"><span data-stu-id="02f34-121">Is located at:</span></span><br/>[https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)         |<span data-ttu-id="02f34-122">位于：</span><span class="sxs-lookup"><span data-stu-id="02f34-122">Is located at:</span></span><br/>[https://securitycenter.windows.com/action-center](https://securitycenter.windows.com/action-center)     |
| <span data-ttu-id="02f34-123">在安全Microsoft 365，选择"**操作中心"。**</span><span class="sxs-lookup"><span data-stu-id="02f34-123">In the Microsoft 365 security center, choose **Action center**.</span></span> <p>:::image type="content" source="images/action-center-nav-new.png" alt-text="导航到安全中心Microsoft 365操作中心"::: | <span data-ttu-id="02f34-125">In the Microsoft Defender 安全中心， choose **Automated investigations**  >  **Action center**.</span><span class="sxs-lookup"><span data-stu-id="02f34-125">In the Microsoft Defender Security Center, choose **Automated investigations** > **Action center**.</span></span> <p>:::image type="content" source="images/action-center-nav-old.png" alt-text="从导航到操作中心Microsoft Defender 安全中心":::  |

<span data-ttu-id="02f34-127">统一操作中心将跨 Defender for Endpoint 和 Defender for Office 365。</span><span class="sxs-lookup"><span data-stu-id="02f34-127">The unified Action center brings together remediation actions across Defender for Endpoint and Defender for Office 365.</span></span> <span data-ttu-id="02f34-128">它定义所有修正操作的共同语言，并提供统一的调查体验。</span><span class="sxs-lookup"><span data-stu-id="02f34-128">It defines a common language for all remediation actions, and provides a unified investigation experience.</span></span> 

<span data-ttu-id="02f34-129">如果您具有适当的权限以及以下一个或多个订阅，可以使用统一操作中心：</span><span class="sxs-lookup"><span data-stu-id="02f34-129">You can use the unified Action center if you have appropriate permissions and one or more of the following subscriptions:</span></span>
- [<span data-ttu-id="02f34-130">适用于终结点的 Defender</span><span class="sxs-lookup"><span data-stu-id="02f34-130">Defender for Endpoint</span></span>](microsoft-defender-endpoint.md)
- [<span data-ttu-id="02f34-131">Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="02f34-131">Defender for Office 365</span></span>](/microsoft-365/security/office-365-security/office-365-atp)
- [<span data-ttu-id="02f34-132">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="02f34-132">Microsoft 365 Defender</span></span>](/microsoft-365/security/mtp/microsoft-threat-protection) 

> [!TIP]
> <span data-ttu-id="02f34-133">若要了解更多信息，请参阅 [要求](/microsoft-365/security/mtp/prerequisites)。</span><span class="sxs-lookup"><span data-stu-id="02f34-133">To learn more, see [Requirements](/microsoft-365/security/mtp/prerequisites).</span></span>

## <a name="using-the-action-center"></a><span data-ttu-id="02f34-134">使用操作中心</span><span class="sxs-lookup"><span data-stu-id="02f34-134">Using the Action center</span></span>

<span data-ttu-id="02f34-135">若要访问改进的安全中心的统一Microsoft 365中心：</span><span class="sxs-lookup"><span data-stu-id="02f34-135">To get to the unified Action center in the improved Microsoft 365 security center:</span></span>
1. <span data-ttu-id="02f34-136">转到安全Microsoft 365中心 [https://security.microsoft.com](https://security.microsoft.com) () 登录。</span><span class="sxs-lookup"><span data-stu-id="02f34-136">Go to the Microsoft 365 security center ([https://security.microsoft.com](https://security.microsoft.com)) and sign in.</span></span>
2. <span data-ttu-id="02f34-137">在导航窗格中，选择操作 **中心**。</span><span class="sxs-lookup"><span data-stu-id="02f34-137">In the navigation pane, select **Action center**.</span></span> 

<span data-ttu-id="02f34-138">当你访问操作中心时，你将看到两个选项卡：**挂起的操作和\*\*\*\*历史记录**。</span><span class="sxs-lookup"><span data-stu-id="02f34-138">When you visit the Action center, you see two tabs: **Pending actions** and **History**.</span></span> <span data-ttu-id="02f34-139">下表总结了您将在每个选项卡上看到的内容：</span><span class="sxs-lookup"><span data-stu-id="02f34-139">The following table summarizes what you'll see on each tab:</span></span>

|<span data-ttu-id="02f34-140">选项卡</span><span class="sxs-lookup"><span data-stu-id="02f34-140">Tab</span></span>  |<span data-ttu-id="02f34-141">说明</span><span class="sxs-lookup"><span data-stu-id="02f34-141">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="02f34-142">**Pending**</span><span class="sxs-lookup"><span data-stu-id="02f34-142">**Pending**</span></span>     | <span data-ttu-id="02f34-143">显示需要关注的操作的列表。</span><span class="sxs-lookup"><span data-stu-id="02f34-143">Displays a list of actions that require attention.</span></span> <span data-ttu-id="02f34-144">可以一次批准或拒绝一个操作，也可以选择多个操作（如果他们的操作类型与隔离文件 (隔离 **) 。**</span><span class="sxs-lookup"><span data-stu-id="02f34-144">You can approve or reject actions one at a time, or select multiple actions if they have the same type of action (such as **Quarantine file**).</span></span> <br/><span data-ttu-id="02f34-145">**提示**： [确保尽快审阅](manage-auto-investigation.md) (批准或拒绝) 挂起的操作，以便可以及时完成自动调查。</span><span class="sxs-lookup"><span data-stu-id="02f34-145">**TIP**: Make sure to [review and approve (or reject) pending actions](manage-auto-investigation.md) as soon as possible so that your automated investigations can complete in a timely manner.</span></span> |
|<span data-ttu-id="02f34-146">**历史记录**</span><span class="sxs-lookup"><span data-stu-id="02f34-146">**History**</span></span>     | <span data-ttu-id="02f34-147">充当审核日志的操作的一个组，例如：</span><span class="sxs-lookup"><span data-stu-id="02f34-147">Serves as an audit log for actions that were taken, such as:</span></span> <br/><span data-ttu-id="02f34-148">- 由于自动调查而采取的修正操作</span><span class="sxs-lookup"><span data-stu-id="02f34-148">- Remediation actions that were taken as a result of automated investigations</span></span> <br><span data-ttu-id="02f34-149">- 安全运营团队批准的修正操作</span><span class="sxs-lookup"><span data-stu-id="02f34-149">- Remediation actions that were approved by your security operations team</span></span>  <br/><span data-ttu-id="02f34-150">- 运行的命令和在实时响应会话期间应用的修正操作</span><span class="sxs-lookup"><span data-stu-id="02f34-150">- Commands that were run and remediation actions that were applied during Live Response sessions</span></span>  <br/><span data-ttu-id="02f34-151">- Microsoft Defender 防病毒 中威胁防护功能采取的修正Microsoft Defender 防病毒</span><span class="sxs-lookup"><span data-stu-id="02f34-151">- Remediation actions that were taken by threat protection features in Microsoft Defender Antivirus</span></span>  <p><span data-ttu-id="02f34-152">提供了一种撤消某些操作 (请参阅[Undo completed actions) 。](manage-auto-investigation.md#undo-completed-actions)</span><span class="sxs-lookup"><span data-stu-id="02f34-152">Provides a way to undo certain actions (see [Undo completed actions](manage-auto-investigation.md#undo-completed-actions)).</span></span>       |

<span data-ttu-id="02f34-153">可以在操作中心中自定义、排序、筛选和导出数据。</span><span class="sxs-lookup"><span data-stu-id="02f34-153">You can customize, sort, filter, and export data in the Action center.</span></span>

:::image type="content" source="images/new-action-center-columnsfilters.png" alt-text="操作中心中的列和筛选器":::

- <span data-ttu-id="02f34-155">选择列标题以按升序或降序对项目进行排序。</span><span class="sxs-lookup"><span data-stu-id="02f34-155">Select a column heading to sort items in ascending or descending order.</span></span>
- <span data-ttu-id="02f34-156">使用时间段筛选器查看过去一天、一周、30 天或 6 个月的数据。</span><span class="sxs-lookup"><span data-stu-id="02f34-156">Use the time period filter to view data for the past day, week, 30 days, or 6 months.</span></span>
- <span data-ttu-id="02f34-157">选择要查看的列。</span><span class="sxs-lookup"><span data-stu-id="02f34-157">Choose the columns that you want to view.</span></span>
- <span data-ttu-id="02f34-158">指定要包含在每个数据页上的项目数。</span><span class="sxs-lookup"><span data-stu-id="02f34-158">Specify how many items to include on each page of data.</span></span>
- <span data-ttu-id="02f34-159">使用筛选器仅查看要查看的项目。</span><span class="sxs-lookup"><span data-stu-id="02f34-159">Use filters to view just the items you want to see.</span></span>
- <span data-ttu-id="02f34-160">选择 **"** 导出"将结果导出到.csv文件。</span><span class="sxs-lookup"><span data-stu-id="02f34-160">Select **Export** to export results to a .csv file.</span></span> 

## <a name="next-steps"></a><span data-ttu-id="02f34-161">后续步骤</span><span class="sxs-lookup"><span data-stu-id="02f34-161">Next steps</span></span>

- [<span data-ttu-id="02f34-162">查看和批准修正操作</span><span class="sxs-lookup"><span data-stu-id="02f34-162">View and approve remediation actions</span></span>](manage-auto-investigation.md)
- [<span data-ttu-id="02f34-163">请参阅交互式指南：使用 Microsoft Defender for Endpoint 调查和修正威胁</span><span class="sxs-lookup"><span data-stu-id="02f34-163">See the interactive guide: Investigate and remediate threats with Microsoft Defender for Endpoint</span></span>](https://aka.ms/MDATP-IR-Interactive-Guide)
 
## <a name="see-also"></a><span data-ttu-id="02f34-164">另请参阅</span><span class="sxs-lookup"><span data-stu-id="02f34-164">See also</span></span>

- [<span data-ttu-id="02f34-165">解决 Microsoft Defender for Endpoint 中的误报/漏报</span><span class="sxs-lookup"><span data-stu-id="02f34-165">Address false positives/negatives in Microsoft Defender for Endpoint</span></span>](defender-endpoint-false-positives-negatives.md)
