---
title: 在 DLP 策略中使用敏感度标签作为条件
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MET150
ms.custom:
- seo-marvel-apr2020
description: 了解可在 DLP 策略中使用敏感度标签作为条件的服务和项目类型
ms.openlocfilehash: 94d5e9f53471f6113dcc755995a3f94e95a58e53
ms.sourcegitcommit: 50f484fc501d81506a714b127a56a6979888d849
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/05/2021
ms.locfileid: "52779839"
---
# <a name="use-sensitivity-labels-as-conditions-in-dlp-policies"></a><span data-ttu-id="965b5-103">在 DLP 策略中使用敏感度标签作为条件</span><span class="sxs-lookup"><span data-stu-id="965b5-103">Use sensitivity labels as conditions in DLP policies</span></span>

<span data-ttu-id="965b5-104">在以下位置的 DLP 策略中，可使用[敏感度标签](sensitivity-labels.md)作为条件：</span><span class="sxs-lookup"><span data-stu-id="965b5-104">You can use [sensitivity labels](sensitivity-labels.md) as a condition in DLP policies for these location:</span></span>

- <span data-ttu-id="965b5-105">Exchange Online 电子邮件</span><span class="sxs-lookup"><span data-stu-id="965b5-105">Exchange Online email messages</span></span>
- <span data-ttu-id="965b5-106">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="965b5-106">SharePoint Online</span></span>
- <span data-ttu-id="965b5-107">OneDrive for Business 站点</span><span class="sxs-lookup"><span data-stu-id="965b5-107">OneDrive for Business sites</span></span>
- <span data-ttu-id="965b5-108">Windows 10 设备</span><span class="sxs-lookup"><span data-stu-id="965b5-108">Windows 10 devices</span></span>

<span data-ttu-id="965b5-109">敏感度标签作为一个选项出现在 **内容包含** 列表中。</span><span class="sxs-lookup"><span data-stu-id="965b5-109">Sensitivity labels appear as an option in the **Content contains** list.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="965b5-110">![使用敏感度标签作为条件](../media/dlp-sensitivity-label-as-a-condition.png)</span><span class="sxs-lookup"><span data-stu-id="965b5-110">![sensitivity label as a condition](../media/dlp-sensitivity-label-as-a-condition.png)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="965b5-111">如果选择 **Teams 聊天和频道消息** 作为应用 DLP 策略的位置，则作为条件的 **灵敏度标签** 将不可用。</span><span class="sxs-lookup"><span data-stu-id="965b5-111">**Sensitivity Labels** as a condition will not be available if you have selected **Teams chat and channel messages** as a location to apply the DLP policy.</span></span>


## <a name="supported-items-scenarios-and-policy-tips"></a><span data-ttu-id="965b5-112">支持的项目、方案和策略提示</span><span class="sxs-lookup"><span data-stu-id="965b5-112">Supported items, scenarios, and policy tips</span></span>

<span data-ttu-id="965b5-113">可在这些项目和方案中使用敏感度标签作为条件。</span><span class="sxs-lookup"><span data-stu-id="965b5-113">You can use sensitivity labels as conditions on these items and in these scenarios.</span></span>

### <a name="supported-items"></a><span data-ttu-id="965b5-114">支持的项目：</span><span class="sxs-lookup"><span data-stu-id="965b5-114">Supported items</span></span>

|<span data-ttu-id="965b5-115">服务</span><span class="sxs-lookup"><span data-stu-id="965b5-115">Service</span></span>  |<span data-ttu-id="965b5-116">项目类型</span><span class="sxs-lookup"><span data-stu-id="965b5-116">Item type</span></span>  |<span data-ttu-id="965b5-117">可用于策略提示</span><span class="sxs-lookup"><span data-stu-id="965b5-117">Available to policy tip</span></span>  |<span data-ttu-id="965b5-118">可强制实施</span><span class="sxs-lookup"><span data-stu-id="965b5-118">Enforceable</span></span>  |
|---------|---------|---------|---------|
|<span data-ttu-id="965b5-119">Exchange</span><span class="sxs-lookup"><span data-stu-id="965b5-119">Exchange</span></span>    |<span data-ttu-id="965b5-120">电子邮件</span><span class="sxs-lookup"><span data-stu-id="965b5-120">email message</span></span>         |<span data-ttu-id="965b5-121">是</span><span class="sxs-lookup"><span data-stu-id="965b5-121">yes</span></span>         |<span data-ttu-id="965b5-122">是</span><span class="sxs-lookup"><span data-stu-id="965b5-122">yes</span></span>         |
|<span data-ttu-id="965b5-123">Exchange</span><span class="sxs-lookup"><span data-stu-id="965b5-123">Exchange</span></span>    |<span data-ttu-id="965b5-124">电子邮件附件</span><span class="sxs-lookup"><span data-stu-id="965b5-124">email attachment</span></span>         |<span data-ttu-id="965b5-125">否</span><span class="sxs-lookup"><span data-stu-id="965b5-125">no</span></span>         |<span data-ttu-id="965b5-126">是 \*\*</span><span class="sxs-lookup"><span data-stu-id="965b5-126">yes \*</span></span>         |
|<span data-ttu-id="965b5-127">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="965b5-127">SharePoint Online</span></span>     |<span data-ttu-id="965b5-128">SharePoint Online 中的列表</span><span class="sxs-lookup"><span data-stu-id="965b5-128">items in SharePoint Online</span></span>         |<span data-ttu-id="965b5-129">是</span><span class="sxs-lookup"><span data-stu-id="965b5-129">yes</span></span>         |<span data-ttu-id="965b5-130">是</span><span class="sxs-lookup"><span data-stu-id="965b5-130">yes</span></span>         |
|<span data-ttu-id="965b5-131">OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="965b5-131">OneDrive for Business</span></span>     |<span data-ttu-id="965b5-132">项目</span><span class="sxs-lookup"><span data-stu-id="965b5-132">items</span></span>         |<span data-ttu-id="965b5-133">是</span><span class="sxs-lookup"><span data-stu-id="965b5-133">yes</span></span>         |<span data-ttu-id="965b5-134">是</span><span class="sxs-lookup"><span data-stu-id="965b5-134">yes</span></span>         |
|<span data-ttu-id="965b5-135">Teams</span><span class="sxs-lookup"><span data-stu-id="965b5-135">Teams</span></span>     |<span data-ttu-id="965b5-136">Teams 聊天和通道消息</span><span class="sxs-lookup"><span data-stu-id="965b5-136">Teams and channel messages</span></span>         |<span data-ttu-id="965b5-137">不适用</span><span class="sxs-lookup"><span data-stu-id="965b5-137">not applicable</span></span>         |<span data-ttu-id="965b5-138">不适用</span><span class="sxs-lookup"><span data-stu-id="965b5-138">not applicable</span></span>         |
|<span data-ttu-id="965b5-139">Teams</span><span class="sxs-lookup"><span data-stu-id="965b5-139">Teams</span></span>     |<span data-ttu-id="965b5-140">attachments</span><span class="sxs-lookup"><span data-stu-id="965b5-140">attachments</span></span>         |<span data-ttu-id="965b5-141">是 \*\*</span><span class="sxs-lookup"><span data-stu-id="965b5-141">yes \*\*</span></span>         |<span data-ttu-id="965b5-142">是 \*\*</span><span class="sxs-lookup"><span data-stu-id="965b5-142">yes \*\*</span></span>         |
|<span data-ttu-id="965b5-143">Windows 10 设备</span><span class="sxs-lookup"><span data-stu-id="965b5-143">Windows 10 devices</span></span>     |<span data-ttu-id="965b5-144">项目</span><span class="sxs-lookup"><span data-stu-id="965b5-144">items</span></span>         |<span data-ttu-id="965b5-145">是</span><span class="sxs-lookup"><span data-stu-id="965b5-145">yes</span></span>         |<span data-ttu-id="965b5-146">是</span><span class="sxs-lookup"><span data-stu-id="965b5-146">yes</span></span>         |
|<span data-ttu-id="965b5-147">MCAS（预览版）</span><span class="sxs-lookup"><span data-stu-id="965b5-147">MCAS (preview)</span></span> |<span data-ttu-id="965b5-148">项目</span><span class="sxs-lookup"><span data-stu-id="965b5-148">items</span></span>         |<span data-ttu-id="965b5-149">是</span><span class="sxs-lookup"><span data-stu-id="965b5-149">yes</span></span>         |<span data-ttu-id="965b5-150">是</span><span class="sxs-lookup"><span data-stu-id="965b5-150">yes</span></span>         |

<span data-ttu-id="965b5-151">\* 仅 Office 文件类型支持对已添加敏感度标签的电子邮件附件进行 DLP 检测。</span><span class="sxs-lookup"><span data-stu-id="965b5-151">\* DLP detection of sensitivity labeled email attachments are supported for Office file types only.</span></span>

<span data-ttu-id="965b5-152">\*\* 在一对一聊天或频道的 Teams 中发送的附件将自动上传到 OneDrive for Business 和 SharePoint。</span><span class="sxs-lookup"><span data-stu-id="965b5-152">\*\* Attachments sent in Teams over 1:1 chat or channels are automatically uploaded to OneDrive for Business and SharePoint.</span></span> <span data-ttu-id="965b5-153">因此，如果你的 DLP 策略中包含 SharePoint Online 或 OneDrive for Business，则在 Teams 中发送的带标签的附件将自动包含在此条件的范围内。</span><span class="sxs-lookup"><span data-stu-id="965b5-153">So if SharePoint Online or OneDrive for Business are included as locations in your DLP policy, then labeled attachments sent in Teams will be automatically included in the scope of this condition.</span></span> <span data-ttu-id="965b5-154">不需要在 DLP 策略中选择用作位置的 Teams。</span><span class="sxs-lookup"><span data-stu-id="965b5-154">Teams as a location does not need to be selected in the DLP policy.</span></span>

> [!NOTE]
> <span data-ttu-id="965b5-155">DLP 在 SharePoint 和 OneDrive for Business 中检测敏感度标签的能力有限。</span><span class="sxs-lookup"><span data-stu-id="965b5-155">DLP's ability to detect sensitivity labels in SharePoint and OneDrive for business is limited.</span></span> <span data-ttu-id="965b5-156">有关详细信息，请参阅 [启用 SharePoint 和 OneDrive 中 Office 文件的敏感度标签](sensitivity-labels-sharepoint-onedrive-files.md#limitations)。</span><span class="sxs-lookup"><span data-stu-id="965b5-156">For more information, see [Enable sensitivity labels for Office files in SharePoint and OneDrive](sensitivity-labels-sharepoint-onedrive-files.md#limitations).</span></span>

### <a name="supported-scenarios"></a><span data-ttu-id="965b5-157">支持的方案</span><span class="sxs-lookup"><span data-stu-id="965b5-157">Supported scenarios</span></span>

- <span data-ttu-id="965b5-158">当 DLP 管理员选择将一个或多个敏感度标签作为条件时，将能够看到租户中所有敏感度标签的列表。</span><span class="sxs-lookup"><span data-stu-id="965b5-158">DLP Admin will be able to see a list of all sensitivity labels in the tenant when they choose to include one or more sensitivity labels as a condition.</span></span>

- <span data-ttu-id="965b5-159">按上述支持矩阵所示，支持在所有工作负载中使用敏感度标签作为条件。</span><span class="sxs-lookup"><span data-stu-id="965b5-159">Using sensitivity labels as a condition is supported across all workloads as indicated in the support matrix above.</span></span>

- <span data-ttu-id="965b5-160">对于包含敏感度标签作为条件的 DLP 策略，将继续跨工作负载（Outlook Win32 除外）显示 DLP 策略提示。</span><span class="sxs-lookup"><span data-stu-id="965b5-160">DLP policy tips will continue to be shown across workloads (except Outlook Win32) for DLP policies which contain sensitivity label as a condition.</span></span>

- <span data-ttu-id="965b5-161">如果与包含敏感度标签的 DLP 策略匹配，则敏感度标签也将显示为事件报告电子邮件的一部分。</span><span class="sxs-lookup"><span data-stu-id="965b5-161">Sensitivity labels will also appear as a part of the incident report email if a DLP policy with sensitivity label as a condition is matched.</span></span>

- <span data-ttu-id="965b5-162">敏感度标签的详细信息也将显示在 DLP 规则匹配审核日志中，该策略包含敏感度标签作为条件。</span><span class="sxs-lookup"><span data-stu-id="965b5-162">Sensitivity label details will also be shown in the DLP rule match audit log for a DLP policy match which contains sensitivity label as a condition.</span></span>


### <a name="support-policy-tips"></a><span data-ttu-id="965b5-163">支持策略提示</span><span class="sxs-lookup"><span data-stu-id="965b5-163">Support policy tips</span></span>


|<span data-ttu-id="965b5-164">工作负载</span><span class="sxs-lookup"><span data-stu-id="965b5-164">Workload</span></span>  |<span data-ttu-id="965b5-165">受支持或不支持的策略提示</span><span class="sxs-lookup"><span data-stu-id="965b5-165">Policy tips supported/not supported</span></span>  |
|---------|---------|
|<span data-ttu-id="965b5-166">OWA</span><span class="sxs-lookup"><span data-stu-id="965b5-166">OWA</span></span> |    <span data-ttu-id="965b5-167">支持</span><span class="sxs-lookup"><span data-stu-id="965b5-167">supported</span></span>     |
|<span data-ttu-id="965b5-168">Outlook Win 32</span><span class="sxs-lookup"><span data-stu-id="965b5-168">Outlook Win 32</span></span>    |  <span data-ttu-id="965b5-169">不支持</span><span class="sxs-lookup"><span data-stu-id="965b5-169">not supported</span></span>       |
|<span data-ttu-id="965b5-170">SharePoint</span><span class="sxs-lookup"><span data-stu-id="965b5-170">SharePoint</span></span>   |   <span data-ttu-id="965b5-171">支持</span><span class="sxs-lookup"><span data-stu-id="965b5-171">supported</span></span>      |
|<span data-ttu-id="965b5-172">OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="965b5-172">OneDrive for Business</span></span>    |    <span data-ttu-id="965b5-173">支持</span><span class="sxs-lookup"><span data-stu-id="965b5-173">supported</span></span>     |
|<span data-ttu-id="965b5-174">终结点设备</span><span class="sxs-lookup"><span data-stu-id="965b5-174">endpoint devices</span></span>   |  <span data-ttu-id="965b5-175">不支持</span><span class="sxs-lookup"><span data-stu-id="965b5-175">not supported</span></span>       |
