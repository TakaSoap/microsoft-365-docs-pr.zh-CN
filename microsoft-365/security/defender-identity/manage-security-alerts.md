---
title: Microsoft Defender for Identity 中的安全警报Microsoft 365 Defender
description: 了解如何管理和查看由 Microsoft Defender for Identity 在 Microsoft 365 Defender
ms.date: 05/20/2021
ms.topic: how-to
author: dcurwin
ms.author: dacurwin
ms.service: microsoft-defender-for-identity
manager: raynew
ms.openlocfilehash: c81f14b92b285359bda7e291bd8d3a8b636ae54d
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/30/2021
ms.locfileid: "53228959"
---
# <a name="defender-for-identity-security-alerts-in-microsoft-365-defender"></a><span data-ttu-id="18142-103">Defender for Identity security alerts in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="18142-103">Defender for Identity security alerts in Microsoft 365 Defender</span></span>

<span data-ttu-id="18142-104">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="18142-104">**Applies to:**</span></span>

- <span data-ttu-id="18142-105">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="18142-105">Microsoft 365 Defender</span></span>
- <span data-ttu-id="18142-106">Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="18142-106">Defender for Identity</span></span>

<span data-ttu-id="18142-107">本文介绍了如何在安全中心内使用[Microsoft Defender for Identity](/defender-for-identity)安全警报Microsoft 365[基础知识](/microsoft-365/security/defender/overview-security-center)。</span><span class="sxs-lookup"><span data-stu-id="18142-107">This article explains the basics of how to work with [Microsoft Defender for Identity](/defender-for-identity) security alerts in the [Microsoft 365 security center](/microsoft-365/security/defender/overview-security-center).</span></span>

<span data-ttu-id="18142-108">Defender for Identity 警报已本机集成到具有专用标识[Microsoft 365页面格式](https://security.microsoft.com)的安全中心。</span><span class="sxs-lookup"><span data-stu-id="18142-108">Defender for Identity alerts are natively integrated into the [Microsoft 365 security center](https://security.microsoft.com) with a dedicated Identity alert page format.</span></span> <span data-ttu-id="18142-109">这标记了将完整的[Microsoft Defender for Identity](/defender-for-identity/defender-for-identity-in-microsoft-365-defender)体验引入到 Microsoft 365 Defender。</span><span class="sxs-lookup"><span data-stu-id="18142-109">This marks the first step in the journey to [introduce the full Microsoft Defender for Identity experience into Microsoft 365 Defender](/defender-for-identity/defender-for-identity-in-microsoft-365-defender).</span></span>

<span data-ttu-id="18142-110">新的标识警报页面为 Microsoft Defender for Identity 客户提供更好的跨域信号扩充和新自动标识响应功能。</span><span class="sxs-lookup"><span data-stu-id="18142-110">The new Identity alert page gives Microsoft Defender for Identity customers better cross-domain signal enrichment and new automated identity response capabilities.</span></span> <span data-ttu-id="18142-111">它可确保您保持安全，并有助于提高安全操作的效率。</span><span class="sxs-lookup"><span data-stu-id="18142-111">It ensures that you stay secure and helps improve the efficiency of your security operations.</span></span>

<span data-ttu-id="18142-112">通过 Microsoft 365 Defender 调查警报的一个好处[](/microsoft-365/security/defender/microsoft-365-defender)是，Microsoft Defender for Identity 警报与从套件中的所有其他产品获取的信息进一步关联。</span><span class="sxs-lookup"><span data-stu-id="18142-112">One of the benefits of investigating alerts through [Microsoft 365 Defender](/microsoft-365/security/defender/microsoft-365-defender) is that Microsoft Defender for Identity alerts are further correlated with information obtained from each of the other products in the suite.</span></span> <span data-ttu-id="18142-113">这些增强的警报与其他来自 microsoft Defender for Microsoft 365 Defender 和 Microsoft [Defender for](/microsoft-365/security/office-365-security) Endpoint Office 365警报[格式一致](/microsoft-365/security/defender-endpoint)。</span><span class="sxs-lookup"><span data-stu-id="18142-113">These enhanced alerts are consistent with the other Microsoft 365 Defender alert formats originating from [Microsoft Defender for Office 365](/microsoft-365/security/office-365-security) and [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint).</span></span> <span data-ttu-id="18142-114">新页面实际上无需导航到其他产品门户来调查与标识相关的警报。</span><span class="sxs-lookup"><span data-stu-id="18142-114">The new page effectively eliminates the need to navigate to another product portal to investigate alerts associated with identity.</span></span>

<span data-ttu-id="18142-115">源自 Defender for Identity 的警报现在可以触发 Microsoft 365 Defender 自动调查和响应[ (AIR) ](/microsoft-365/security/defender/m365d-autoir)功能，包括自动修正警报以及缓解可能参与可疑活动的工具和流程。</span><span class="sxs-lookup"><span data-stu-id="18142-115">Alerts originating from Defender for Identity can now trigger the [Microsoft 365 Defender automated investigation and response (AIR)](/microsoft-365/security/defender/m365d-autoir) capabilities, including automatically remediating alerts and the mitigation of tools and processes that can contribute to the suspicious activity.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="18142-116">作为与用户Microsoft 365 Defender的一部分，一些选项和详细信息从他们在 Defender for Identity 门户中的位置发生了更改。</span><span class="sxs-lookup"><span data-stu-id="18142-116">As part of the convergence with Microsoft 365 Defender, some options and details have changed from their location in the Defender for Identity portal.</span></span> <span data-ttu-id="18142-117">请阅读下面的详细信息，了解在哪里可以找到熟悉的新功能和新功能。</span><span class="sxs-lookup"><span data-stu-id="18142-117">Please read the details below to discover where to find both the familiar and new features.</span></span>

## <a name="review-security-alerts"></a><span data-ttu-id="18142-118">查看安全警报</span><span class="sxs-lookup"><span data-stu-id="18142-118">Review security alerts</span></span>

<span data-ttu-id="18142-119">可以从多个位置访问警报，包括警报页面、事件页面、各个设备的页面以及高级 **搜寻页面。** </span><span class="sxs-lookup"><span data-stu-id="18142-119">Alerts can be accessed from multiple locations, including the **Alerts** page, the **Incidents** page, the pages of individual **Devices**, and from the **Advanced hunting** page.</span></span> <span data-ttu-id="18142-120">本示例中，我们将查看警报 **页面**。</span><span class="sxs-lookup"><span data-stu-id="18142-120">In this example, we'll review the **Alerts page**.</span></span>

<span data-ttu-id="18142-121">在安全 [Microsoft 365，](https://security.microsoft.com/)转到"事件 **&警报"，** 然后转到"**警报"。**</span><span class="sxs-lookup"><span data-stu-id="18142-121">In the [Microsoft 365 security center](https://security.microsoft.com/), go to **Incidents & alerts** and then to **Alerts**.</span></span>

![转到"事件和警报"，然后转到"警报"](../../media/defender-identity/incidents-alerts.png)

<span data-ttu-id="18142-123">To see alerts from Defender for Identity， on the top-right select **Filter**， and then under **Service sources** select Microsoft Defender **for Identity，** and select **Apply**：</span><span class="sxs-lookup"><span data-stu-id="18142-123">To see alerts from Defender for Identity, on the top-right select **Filter**, and then under **Service sources** select **Microsoft Defender for Identity**, and select **Apply**:</span></span>

![筛选 Defender for Identity 事件](../../media/defender-identity/filter-defender-for-identity.png)

<span data-ttu-id="18142-125">警报将显示，并包含以下列中的信息：**警报** 名称、标签、严重性、调查状态、**状态**、**类别**、检测源、影响 **的资产**、第一个活动和最后 **一个活动**。 </span><span class="sxs-lookup"><span data-stu-id="18142-125">The alerts are displayed with information in the following columns: **Alert name**, **Tags**, **Severity**, **Investigation state**, **Status**, **Category**, **Detection source**, **Impacted assets**, **First activity**, and **Last activity**.</span></span>

![Defender for Identity 事件](../../media/defender-identity/filtered-alerts.png)

## <a name="manage-alerts"></a><span data-ttu-id="18142-127">管理警报</span><span class="sxs-lookup"><span data-stu-id="18142-127">Manage alerts</span></span>

<span data-ttu-id="18142-128">如果单击 **其中一** 个警报的警报名称，你将转到包含警报详细信息的页面。</span><span class="sxs-lookup"><span data-stu-id="18142-128">If you click the **Alert name** for one of the alerts, you'll go to the page with details about the alert.</span></span> <span data-ttu-id="18142-129">在左窗格中，你将看到"发生了什么 **"的摘要**：</span><span class="sxs-lookup"><span data-stu-id="18142-129">In the left pane, you'll see a summary of **What happened**:</span></span>

![警报中发生的情况](../../media/defender-identity/what-happened.png)

<span data-ttu-id="18142-131">"**发生的情况**"框上方是警报的 **"帐户**"、**目标主机\*\*\*\*和源主机** 的按钮。</span><span class="sxs-lookup"><span data-stu-id="18142-131">Above the **What happened** box are buttons for the **Accounts**, **Destination Host** and **Source Host** of the alert.</span></span> <span data-ttu-id="18142-132">对于其他警报，你可能会看到按钮，了解有关其他主机、帐户、IP 地址、域和安全组的详细信息。</span><span class="sxs-lookup"><span data-stu-id="18142-132">For other alerts, you might see buttons for details about additional hosts, accounts, IP addresses, domains, and security groups.</span></span> <span data-ttu-id="18142-133">选择其中任何一个，获取有关所涉及的实体的更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="18142-133">Select any of them to get more details about the entities involved.</span></span>

<span data-ttu-id="18142-134">在右侧窗格中，你将看到警报 **详细信息**。</span><span class="sxs-lookup"><span data-stu-id="18142-134">On the right pane, you'll see the **Alert details**.</span></span> <span data-ttu-id="18142-135">你可以在此处查看更多详细信息并执行多个任务：</span><span class="sxs-lookup"><span data-stu-id="18142-135">Here you can see more details and perform several tasks:</span></span>

- <span data-ttu-id="18142-136">**对此警报进行分类** - 你可以在此处指定此警报为 **True 警报或** **False 警报**</span><span class="sxs-lookup"><span data-stu-id="18142-136">**Classify this alert** - Here you can designate this alert as a **True alert** or **False alert**</span></span>

    ![对警报进行分类](../../media/defender-identity/classify-alert.png)

- <span data-ttu-id="18142-138">**警报状态**- 在 **"设置分类**"中，可以将警报分类为 **True** 或 **False。**</span><span class="sxs-lookup"><span data-stu-id="18142-138">**Alert state** - In **Set Classification**, you can classify the alert as **True** or **False**.</span></span> <span data-ttu-id="18142-139">在 **"分配到**"中，可以将警报分配给自己，也可以取消分配。</span><span class="sxs-lookup"><span data-stu-id="18142-139">In **Assigned to**, you can assign the alert to yourself or unassign it.</span></span>

    ![警报状态](../../media/defender-identity/alert-state.png)

- <span data-ttu-id="18142-141">警报详细信息 **-** 在警报详细信息下，可以找到有关特定警报的详细信息，按照有关警报类型的文档链接，查看与警报关联的事件，查看链接到此警报类型的任何自动调查，并查看受到影响的设备和用户。 </span><span class="sxs-lookup"><span data-stu-id="18142-141">**Alert details** - Under **Alert details**, you can find more information about the specific alert, follow a link to documentation about the type of alert, see which incident the alert is associated with, review any automated investigations linked to this alert type, and see the impacted devices and users.</span></span>

    ![警报详细信息](../../media/defender-identity/alert-details.png)

- <span data-ttu-id="18142-143">**注释&历史记录** - 你可以在此处向警报添加注释，并查看与警报关联的所有操作历史记录。</span><span class="sxs-lookup"><span data-stu-id="18142-143">**Comments & history** - Here you can add your comments to the alert, and see the history of all actions associated with the alert.</span></span>

    ![注释和历史记录](../../media/defender-identity/comments-history.png)

- <span data-ttu-id="18142-145">**管理警报** - 如果选择" **管理警报**"，你将转到将允许你编辑的窗格：</span><span class="sxs-lookup"><span data-stu-id="18142-145">**Manage alert** - If you select **Manage alert**, you'll go to a pane that will allow you to edit the:</span></span>
  - <span data-ttu-id="18142-146">**状态**- 可以选择"新建 **"、"已解决"** 或"**正在进行"。** </span><span class="sxs-lookup"><span data-stu-id="18142-146">**Status** - You can choose **New**, **Resolved** or **In progress**.</span></span>
  - <span data-ttu-id="18142-147">**分类**- 可以选择"真 **警报"或**"**假警报"。**</span><span class="sxs-lookup"><span data-stu-id="18142-147">**Classification** - You can choose **True alert** or **False alert**.</span></span>
  - <span data-ttu-id="18142-148">**注释** - 可以添加有关警报的注释。</span><span class="sxs-lookup"><span data-stu-id="18142-148">**Comment** - You can add a comment about the alert.</span></span>

    <span data-ttu-id="18142-149">如果选择"管理警报"旁边的三个点，可以咨询威胁专家、将警报导出到Excel 文件或 **链接到其他事件**。 </span><span class="sxs-lookup"><span data-stu-id="18142-149">If you select the three dots next to **Manage alert**, you can **Consult a threat expert**, **Export** the alert to an Excel file, or **Link to another incident**.</span></span>

    ![管理警报](../../media/defender-identity/manage-alert.png)

    > [!NOTE]
    > <span data-ttu-id="18142-151">在 Excel 文件中，你现在有两个链接可用：在 **Microsoft Defender 中查看标识** 和在 Microsoft 365 Defender 中 **查看**。</span><span class="sxs-lookup"><span data-stu-id="18142-151">In the Excel file, you now have two links available: **View in Microsoft Defender for Identity** and **View in Microsoft 365 Defender**.</span></span> <span data-ttu-id="18142-152">每个链接将你带到相关门户，并提供有关警报的信息。</span><span class="sxs-lookup"><span data-stu-id="18142-152">Each link will bring you to the relevant portal, and provide information about the alert there.</span></span>

## <a name="see-also"></a><span data-ttu-id="18142-153">另请参阅</span><span class="sxs-lookup"><span data-stu-id="18142-153">See also</span></span>

- [<span data-ttu-id="18142-154">调查警报Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="18142-154">Investigate alerts in Microsoft 365 Defender</span></span>](../defender/investigate-alerts.md)
