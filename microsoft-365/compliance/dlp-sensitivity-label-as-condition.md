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
ms.openlocfilehash: b33e6704a3311740c1e386f77f1c751382ee6958
ms.sourcegitcommit: 07e536f1a6e335f114da55048844e4a866fe731b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/25/2021
ms.locfileid: "52651088"
---
# <a name="use-sensitivity-labels-as-conditions-in-dlp-policies"></a><span data-ttu-id="f7770-103">在 DLP 策略中使用敏感度标签作为条件</span><span class="sxs-lookup"><span data-stu-id="f7770-103">Use sensitivity labels as conditions in DLP policies</span></span>

<span data-ttu-id="f7770-104">在以下位置的 DLP 策略中，可使用[敏感度标签](sensitivity-labels.md)作为条件：</span><span class="sxs-lookup"><span data-stu-id="f7770-104">You can use [sensitivity labels](sensitivity-labels.md) as a condition in DLP policies for these location:</span></span>

- <span data-ttu-id="f7770-105">Exchange Online 电子邮件</span><span class="sxs-lookup"><span data-stu-id="f7770-105">Exchange Online email messages</span></span>
- <span data-ttu-id="f7770-106">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="f7770-106">SharePoint Online</span></span>
- <span data-ttu-id="f7770-107">OneDrive for Business 站点</span><span class="sxs-lookup"><span data-stu-id="f7770-107">OneDrive for Business sites</span></span>
- <span data-ttu-id="f7770-108">Windows 10 设备</span><span class="sxs-lookup"><span data-stu-id="f7770-108">Windows 10 devices</span></span>

<span data-ttu-id="f7770-109">敏感度标签作为一个选项出现在 **内容包含** 列表中。</span><span class="sxs-lookup"><span data-stu-id="f7770-109">Sensitivity labels appear as an option in the **Content contains** list.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="f7770-110">![使用敏感度标签作为条件](../media/dlp-sensitivity-label-as-a-condition.png)</span><span class="sxs-lookup"><span data-stu-id="f7770-110">![sensitivity label as a condition](../media/dlp-sensitivity-label-as-a-condition.png)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f7770-111">如果选择 **Teams 聊天和频道消息** 作为应用 DLP 策略的位置，则作为条件的 **灵敏度标签** 将不可用。</span><span class="sxs-lookup"><span data-stu-id="f7770-111">**Sensitivity Labels** as a condition will not be available if you have selected **Teams chat and channel messages** as a location to apply the DLP policy.</span></span>


## <a name="supported-items-scenarios-and-policy-tips"></a><span data-ttu-id="f7770-112">支持的项目、方案和策略提示</span><span class="sxs-lookup"><span data-stu-id="f7770-112">Supported items, scenarios, and policy tips</span></span>

<span data-ttu-id="f7770-113">可在这些项目和方案中使用敏感度标签作为条件。</span><span class="sxs-lookup"><span data-stu-id="f7770-113">You can use sensitivity labels as conditions on these items and in these scenarios.</span></span>

### <a name="supported-items"></a><span data-ttu-id="f7770-114">支持的项目：</span><span class="sxs-lookup"><span data-stu-id="f7770-114">Supported items</span></span>

|<span data-ttu-id="f7770-115">服务</span><span class="sxs-lookup"><span data-stu-id="f7770-115">Service</span></span>  |<span data-ttu-id="f7770-116">项目类型</span><span class="sxs-lookup"><span data-stu-id="f7770-116">Item type</span></span>  |<span data-ttu-id="f7770-117">可用于策略提示</span><span class="sxs-lookup"><span data-stu-id="f7770-117">Available to policy tip</span></span>  |<span data-ttu-id="f7770-118">可强制实施</span><span class="sxs-lookup"><span data-stu-id="f7770-118">Enforceable</span></span>  |
|---------|---------|---------|---------|
|<span data-ttu-id="f7770-119">Exchange</span><span class="sxs-lookup"><span data-stu-id="f7770-119">Exchange</span></span>    |<span data-ttu-id="f7770-120">电子邮件</span><span class="sxs-lookup"><span data-stu-id="f7770-120">email message</span></span>         |<span data-ttu-id="f7770-121">是</span><span class="sxs-lookup"><span data-stu-id="f7770-121">yes</span></span>         |<span data-ttu-id="f7770-122">是</span><span class="sxs-lookup"><span data-stu-id="f7770-122">yes</span></span>         |
|<span data-ttu-id="f7770-123">Exchange</span><span class="sxs-lookup"><span data-stu-id="f7770-123">Exchange</span></span>    |<span data-ttu-id="f7770-124">电子邮件附件</span><span class="sxs-lookup"><span data-stu-id="f7770-124">email attachment</span></span>         |<span data-ttu-id="f7770-125">否</span><span class="sxs-lookup"><span data-stu-id="f7770-125">no</span></span>         |<span data-ttu-id="f7770-126">是 \*\*</span><span class="sxs-lookup"><span data-stu-id="f7770-126">yes \*</span></span>         |
|<span data-ttu-id="f7770-127">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="f7770-127">SharePoint Online</span></span>     |<span data-ttu-id="f7770-128">SharePoint Online 中的列表</span><span class="sxs-lookup"><span data-stu-id="f7770-128">items in SharePoint Online</span></span>         |<span data-ttu-id="f7770-129">是</span><span class="sxs-lookup"><span data-stu-id="f7770-129">yes</span></span>         |<span data-ttu-id="f7770-130">是</span><span class="sxs-lookup"><span data-stu-id="f7770-130">yes</span></span>         |
|<span data-ttu-id="f7770-131">OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="f7770-131">OneDrive for Business</span></span>     |<span data-ttu-id="f7770-132">项目</span><span class="sxs-lookup"><span data-stu-id="f7770-132">items</span></span>         |<span data-ttu-id="f7770-133">是</span><span class="sxs-lookup"><span data-stu-id="f7770-133">yes</span></span>         |<span data-ttu-id="f7770-134">是</span><span class="sxs-lookup"><span data-stu-id="f7770-134">yes</span></span>         |
|<span data-ttu-id="f7770-135">Teams</span><span class="sxs-lookup"><span data-stu-id="f7770-135">Teams</span></span>     |<span data-ttu-id="f7770-136">Teams 聊天和通道消息</span><span class="sxs-lookup"><span data-stu-id="f7770-136">Teams and channel messages</span></span>         |<span data-ttu-id="f7770-137">不适用</span><span class="sxs-lookup"><span data-stu-id="f7770-137">not applicable</span></span>         |<span data-ttu-id="f7770-138">不适用</span><span class="sxs-lookup"><span data-stu-id="f7770-138">not applicable</span></span>         |
|<span data-ttu-id="f7770-139">Teams</span><span class="sxs-lookup"><span data-stu-id="f7770-139">Teams</span></span>     |<span data-ttu-id="f7770-140">attachments</span><span class="sxs-lookup"><span data-stu-id="f7770-140">attachments</span></span>         |<span data-ttu-id="f7770-141">是 \*\*</span><span class="sxs-lookup"><span data-stu-id="f7770-141">yes \*\*</span></span>         |<span data-ttu-id="f7770-142">是 \*\*</span><span class="sxs-lookup"><span data-stu-id="f7770-142">yes \*\*</span></span>         |
|<span data-ttu-id="f7770-143">Windows 10 设备</span><span class="sxs-lookup"><span data-stu-id="f7770-143">Windows 10 devices</span></span>     |<span data-ttu-id="f7770-144">项目</span><span class="sxs-lookup"><span data-stu-id="f7770-144">items</span></span>         |<span data-ttu-id="f7770-145">是</span><span class="sxs-lookup"><span data-stu-id="f7770-145">yes</span></span>         |<span data-ttu-id="f7770-146">是</span><span class="sxs-lookup"><span data-stu-id="f7770-146">yes</span></span>         |
|<span data-ttu-id="f7770-147">MCAS（预览版）</span><span class="sxs-lookup"><span data-stu-id="f7770-147">MCAS (preview)</span></span> |<span data-ttu-id="f7770-148">项目</span><span class="sxs-lookup"><span data-stu-id="f7770-148">items</span></span>         |<span data-ttu-id="f7770-149">是</span><span class="sxs-lookup"><span data-stu-id="f7770-149">yes</span></span>         |<span data-ttu-id="f7770-150">是</span><span class="sxs-lookup"><span data-stu-id="f7770-150">yes</span></span>         |

<span data-ttu-id="f7770-151">\* 仅 Office 文件类型支持对已添加敏感度标签的电子邮件附件进行 DLP 检测。</span><span class="sxs-lookup"><span data-stu-id="f7770-151">\* DLP detection of sensitivity labeled email attachments are supported for Office file types only.</span></span>

<span data-ttu-id="f7770-152">\*\* 在一对一聊天或频道的 Teams 中发送的附件将自动上传到 OneDrive for Business 和 SharePoint。</span><span class="sxs-lookup"><span data-stu-id="f7770-152">\*\* Attachments sent in Teams over 1:1 chat or channels are automatically uploaded to OneDrive for Business and SharePoint.</span></span> <span data-ttu-id="f7770-153">因此，如果你的 DLP 策略中包含 SharePoint Online 或 OneDrive for Business，则在 Teams 中发送的带标签的附件将自动包含在此条件的范围内。</span><span class="sxs-lookup"><span data-stu-id="f7770-153">So if SharePoint Online or OneDrive for Business are included as locations in your DLP policy, then labeled attachments sent in Teams will be automatically included in the scope of this condition.</span></span> <span data-ttu-id="f7770-154">不需要在 DLP 策略中选择用作位置的 Teams。</span><span class="sxs-lookup"><span data-stu-id="f7770-154">Teams as a location does not need to be selected in the DLP policy.</span></span>

### <a name="supported-scenarios"></a><span data-ttu-id="f7770-155">支持的方案</span><span class="sxs-lookup"><span data-stu-id="f7770-155">Supported scenarios</span></span>

- <span data-ttu-id="f7770-156">当 DLP 管理员选择将一个或多个敏感度标签作为条件时，将能够看到租户中所有敏感度标签的列表。</span><span class="sxs-lookup"><span data-stu-id="f7770-156">DLP Admin will be able to see a list of all sensitivity labels in the tenant when they choose to include one or more sensitivity labels as a condition.</span></span>

- <span data-ttu-id="f7770-157">按上述支持矩阵所示，支持在所有工作负载中使用敏感度标签作为条件。</span><span class="sxs-lookup"><span data-stu-id="f7770-157">Using sensitivity labels as a condition is supported across all workloads as indicated in the support matrix above.</span></span>

- <span data-ttu-id="f7770-158">对于包含敏感度标签作为条件的 DLP 策略，将继续跨工作负载（Outlook Win32 除外）显示 DLP 策略提示。</span><span class="sxs-lookup"><span data-stu-id="f7770-158">DLP policy tips will continue to be shown across workloads (except Outlook Win32) for DLP policies which contain sensitivity label as a condition.</span></span>

- <span data-ttu-id="f7770-159">如果与包含敏感度标签的 DLP 策略匹配，则敏感度标签也将显示为事件报告电子邮件的一部分。</span><span class="sxs-lookup"><span data-stu-id="f7770-159">Sensitivity labels will also appear as a part of the incident report email if a DLP policy with sensitivity label as a condition is matched.</span></span>

- <span data-ttu-id="f7770-160">敏感度标签的详细信息也将显示在 DLP 规则匹配审核日志中，该策略包含敏感度标签作为条件。</span><span class="sxs-lookup"><span data-stu-id="f7770-160">Sensitivity label details will also be shown in the DLP rule match audit log for a DLP policy match which contains sensitivity label as a condition.</span></span>


### <a name="support-policy-tips"></a><span data-ttu-id="f7770-161">支持策略提示</span><span class="sxs-lookup"><span data-stu-id="f7770-161">Support policy tips</span></span>


|<span data-ttu-id="f7770-162">工作负载</span><span class="sxs-lookup"><span data-stu-id="f7770-162">Workload</span></span>  |<span data-ttu-id="f7770-163">受支持或不支持的策略提示</span><span class="sxs-lookup"><span data-stu-id="f7770-163">Policy tips supported/not supported</span></span>  |
|---------|---------|
|<span data-ttu-id="f7770-164">OWA</span><span class="sxs-lookup"><span data-stu-id="f7770-164">OWA</span></span> |    <span data-ttu-id="f7770-165">支持</span><span class="sxs-lookup"><span data-stu-id="f7770-165">supported</span></span>     |
|<span data-ttu-id="f7770-166">Outlook Win 32</span><span class="sxs-lookup"><span data-stu-id="f7770-166">Outlook Win 32</span></span>    |  <span data-ttu-id="f7770-167">不支持</span><span class="sxs-lookup"><span data-stu-id="f7770-167">not supported</span></span>       |
|<span data-ttu-id="f7770-168">SharePoint</span><span class="sxs-lookup"><span data-stu-id="f7770-168">SharePoint</span></span>   |   <span data-ttu-id="f7770-169">支持</span><span class="sxs-lookup"><span data-stu-id="f7770-169">supported</span></span>      |
|<span data-ttu-id="f7770-170">OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="f7770-170">OneDrive for Business</span></span>    |    <span data-ttu-id="f7770-171">支持</span><span class="sxs-lookup"><span data-stu-id="f7770-171">supported</span></span>     |
|<span data-ttu-id="f7770-172">终结点设备</span><span class="sxs-lookup"><span data-stu-id="f7770-172">endpoint devices</span></span>   |  <span data-ttu-id="f7770-173">不支持</span><span class="sxs-lookup"><span data-stu-id="f7770-173">not supported</span></span>       |
