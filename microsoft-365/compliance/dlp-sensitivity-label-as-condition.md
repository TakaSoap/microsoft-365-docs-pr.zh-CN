---
title: 在 DLP 策略中使用敏感度标签作为条件（预览版）
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
ms.openlocfilehash: 561a6cbd7b8aeb9082862319c5cc6419fd79c896
ms.sourcegitcommit: f7ca339bdcad38796c550064fb152ea09687d0f3
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/30/2020
ms.locfileid: "48321107"
---
# <a name="use-sensitivity-labels-as-conditions-in-dlp-policies-preview"></a><span data-ttu-id="9df69-103">在 DLP 策略中使用敏感度标签作为条件（预览版）</span><span class="sxs-lookup"><span data-stu-id="9df69-103">Use sensitivity labels as conditions in DLP policies (preview)</span></span>

<span data-ttu-id="9df69-104">在以下位置的 DLP 策略中，可使用[敏感度标签](sensitivity-labels.md)作为条件：</span><span class="sxs-lookup"><span data-stu-id="9df69-104">You can use [sensitivity labels](sensitivity-labels.md) as a condition in DLP policies for these location:</span></span>

- <span data-ttu-id="9df69-105">Exchange Online 电子邮件</span><span class="sxs-lookup"><span data-stu-id="9df69-105">Exchange Online email messages</span></span>
- <span data-ttu-id="9df69-106">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="9df69-106">SharePoint Online</span></span>
- <span data-ttu-id="9df69-107">OneDrive for Business 站点</span><span class="sxs-lookup"><span data-stu-id="9df69-107">OneDrive for Business sites</span></span>
- <span data-ttu-id="9df69-108">Windows 10 设备</span><span class="sxs-lookup"><span data-stu-id="9df69-108">Windows 10 devices</span></span>

<span data-ttu-id="9df69-109">敏感度标签作为一个选项出现在**内容包含**列表中。</span><span class="sxs-lookup"><span data-stu-id="9df69-109">Sensitivity labels appear as an option in the **Content contains** list.</span></span>

![使用敏感度标签作为条件](../media/dlp-sensitivity-label-as-a-condition.png)

## <a name="supported-items-scenarios-and-policy-tips"></a><span data-ttu-id="9df69-111">支持的项目、方案和策略提示</span><span class="sxs-lookup"><span data-stu-id="9df69-111">Supported items, scenarios, and policy tips</span></span>

<span data-ttu-id="9df69-112">可在这些项目和方案中使用敏感度标签作为条件。</span><span class="sxs-lookup"><span data-stu-id="9df69-112">You can use sensitivity labels as conditions on these items and in these scenarios.</span></span>

### <a name="supported-items"></a><span data-ttu-id="9df69-113">支持的项目：</span><span class="sxs-lookup"><span data-stu-id="9df69-113">Supported items</span></span>

|<span data-ttu-id="9df69-114">服务</span><span class="sxs-lookup"><span data-stu-id="9df69-114">service</span></span>  |<span data-ttu-id="9df69-115">项目类型</span><span class="sxs-lookup"><span data-stu-id="9df69-115">item type</span></span>  |<span data-ttu-id="9df69-116">可用于策略提示</span><span class="sxs-lookup"><span data-stu-id="9df69-116">available to policy tip</span></span>  |<span data-ttu-id="9df69-117">可强制实施</span><span class="sxs-lookup"><span data-stu-id="9df69-117">enforceable</span></span>  |
|---------|---------|---------|---------|
|<span data-ttu-id="9df69-118">Exchange</span><span class="sxs-lookup"><span data-stu-id="9df69-118">Exchange</span></span>    |<span data-ttu-id="9df69-119">电子邮件</span><span class="sxs-lookup"><span data-stu-id="9df69-119">email message</span></span>         |<span data-ttu-id="9df69-120">是</span><span class="sxs-lookup"><span data-stu-id="9df69-120">yes</span></span>         |<span data-ttu-id="9df69-121">是</span><span class="sxs-lookup"><span data-stu-id="9df69-121">yes</span></span>         |
|<span data-ttu-id="9df69-122">Exchange</span><span class="sxs-lookup"><span data-stu-id="9df69-122">Exchange</span></span>    |<span data-ttu-id="9df69-123">电子邮件附件</span><span class="sxs-lookup"><span data-stu-id="9df69-123">email attachment</span></span>         |<span data-ttu-id="9df69-124">否\*</span><span class="sxs-lookup"><span data-stu-id="9df69-124">no \*</span></span>         |<span data-ttu-id="9df69-125">否\*</span><span class="sxs-lookup"><span data-stu-id="9df69-125">no \*</span></span>         |
|<span data-ttu-id="9df69-126">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="9df69-126">SharePoint Online</span></span>     |<span data-ttu-id="9df69-127">SharePoint Online 中的列表</span><span class="sxs-lookup"><span data-stu-id="9df69-127">items in SharePoint Online</span></span>         |<span data-ttu-id="9df69-128">是</span><span class="sxs-lookup"><span data-stu-id="9df69-128">yes</span></span>         |<span data-ttu-id="9df69-129">是</span><span class="sxs-lookup"><span data-stu-id="9df69-129">yes</span></span>         |
|<span data-ttu-id="9df69-130">OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="9df69-130">OneDrive for Business</span></span>     |<span data-ttu-id="9df69-131">项目</span><span class="sxs-lookup"><span data-stu-id="9df69-131">items</span></span>         |<span data-ttu-id="9df69-132">是</span><span class="sxs-lookup"><span data-stu-id="9df69-132">yes</span></span>         |<span data-ttu-id="9df69-133">是</span><span class="sxs-lookup"><span data-stu-id="9df69-133">yes</span></span>         |
|<span data-ttu-id="9df69-134">Teams</span><span class="sxs-lookup"><span data-stu-id="9df69-134">Teams</span></span>     |<span data-ttu-id="9df69-135">Teams 聊天和通道消息</span><span class="sxs-lookup"><span data-stu-id="9df69-135">Teams and channel messages</span></span>         |<span data-ttu-id="9df69-136">不适用</span><span class="sxs-lookup"><span data-stu-id="9df69-136">not applicable</span></span>         |<span data-ttu-id="9df69-137">不适用</span><span class="sxs-lookup"><span data-stu-id="9df69-137">not applicable</span></span>         |
|<span data-ttu-id="9df69-138">Teams</span><span class="sxs-lookup"><span data-stu-id="9df69-138">Teams</span></span>     |<span data-ttu-id="9df69-139">attachments</span><span class="sxs-lookup"><span data-stu-id="9df69-139">attachments</span></span>         |<span data-ttu-id="9df69-140">是 \*\*</span><span class="sxs-lookup"><span data-stu-id="9df69-140">yes \*\*</span></span>         |<span data-ttu-id="9df69-141">是 \*\*</span><span class="sxs-lookup"><span data-stu-id="9df69-141">yes \*\*</span></span>         |
|<span data-ttu-id="9df69-142">Windows 10 设备（预览版）</span><span class="sxs-lookup"><span data-stu-id="9df69-142">Windows 10 devices (preview)</span></span>     |<span data-ttu-id="9df69-143">项目</span><span class="sxs-lookup"><span data-stu-id="9df69-143">items</span></span>         |<span data-ttu-id="9df69-144">是</span><span class="sxs-lookup"><span data-stu-id="9df69-144">yes</span></span>         |<span data-ttu-id="9df69-145">是</span><span class="sxs-lookup"><span data-stu-id="9df69-145">yes</span></span>         |
|<span data-ttu-id="9df69-146">MCAS（预览版）</span><span class="sxs-lookup"><span data-stu-id="9df69-146">MCAS (preview)</span></span> |<span data-ttu-id="9df69-147">项目</span><span class="sxs-lookup"><span data-stu-id="9df69-147">items</span></span>         |<span data-ttu-id="9df69-148">是</span><span class="sxs-lookup"><span data-stu-id="9df69-148">yes</span></span>         |<span data-ttu-id="9df69-149">是</span><span class="sxs-lookup"><span data-stu-id="9df69-149">yes</span></span>         |

<span data-ttu-id="9df69-150">\* 支持 DLP 对电子邮件的敏感度标签进行检测。</span><span class="sxs-lookup"><span data-stu-id="9df69-150">\* DLP detection of sensitivity labels on emails are supported.</span></span> <span data-ttu-id="9df69-151">不支持 DLP 对带有敏感度标签的电子邮件附件进行检测。</span><span class="sxs-lookup"><span data-stu-id="9df69-151">DLP detection of sensitivity labeled email attachments are not.</span></span>

<span data-ttu-id="9df69-152">\*\* 在一对一聊天或频道的 Teams 中发送的附件将自动上传到 OneDrive for Business 和 SharePoint。</span><span class="sxs-lookup"><span data-stu-id="9df69-152">\*\* Attachments sent in Teams over 1:1 chat or channels are automatically uploaded to OneDrive for Business and SharePoint.</span></span> <span data-ttu-id="9df69-153">因此，如果你的 DLP 策略中包含 SharePoint Online 或 OneDrive for Business，则在 Teams 中发送的带标签的附件将自动包含在此条件的范围内。</span><span class="sxs-lookup"><span data-stu-id="9df69-153">So if SharePoint Online or OneDrive for Business are included as locations in your DLP policy, then labeled attachments sent in Teams will be automatically included in the scope of this condition.</span></span> <span data-ttu-id="9df69-154">不需要在 DLP 策略中选择用作位置的 Teams。</span><span class="sxs-lookup"><span data-stu-id="9df69-154">Teams as a location does not need to be selected in the DLP policy.</span></span>

### <a name="supported-scenarios"></a><span data-ttu-id="9df69-155">支持的方案</span><span class="sxs-lookup"><span data-stu-id="9df69-155">Supported scenarios</span></span>

- <span data-ttu-id="9df69-156">当 DLP 管理员选择将一个或多个敏感度标签作为条件时，将能够看到租户中所有敏感度标签的列表。</span><span class="sxs-lookup"><span data-stu-id="9df69-156">DLP Admin will be able to see a list of all sensitivity labels in the tenant when they choose to include one or more sensitivity labels as a condition.</span></span>
- <span data-ttu-id="9df69-157">按上述支持矩阵所示，支持在所有工作负载中使用敏感度标签作为条件</span><span class="sxs-lookup"><span data-stu-id="9df69-157">Using sensitivity labels as a condition is supported across all workloads as indicated in the support matrix above</span></span>
- <span data-ttu-id="9df69-158">对于包含敏感度标签作为条件的 DLP 策略，将继续跨工作负载（Outlook Win32 除外）显示 DLP 策略提示。</span><span class="sxs-lookup"><span data-stu-id="9df69-158">DLP policy tips will continue to be shown across workloads (except Outlook Win32) for DLP policies which contain sensitivity label as a condition.</span></span>
- <span data-ttu-id="9df69-159">如果与包含敏感度标签的 DLP 策略匹配，则敏感度标签也将显示为事件报告电子邮件的一部分。</span><span class="sxs-lookup"><span data-stu-id="9df69-159">Sensitivity labels will also appear as a part of the incident report email if a DLP policy with sensitivity label as a condition is matched.</span></span>
- <span data-ttu-id="9df69-160">敏感度标签的详细信息也将显示在 DLP 规则匹配审核日志中，该策略包含敏感度标签作为条件。</span><span class="sxs-lookup"><span data-stu-id="9df69-160">Sensitivity label details will also be shown in the DLP rule match audit log for a DLP policy match which contains sensitivity label as a condition.</span></span>


### <a name="support-policy-tips"></a><span data-ttu-id="9df69-161">支持策略提示</span><span class="sxs-lookup"><span data-stu-id="9df69-161">Support policy tips</span></span>


|<span data-ttu-id="9df69-162">工作负载</span><span class="sxs-lookup"><span data-stu-id="9df69-162">workload</span></span>  |<span data-ttu-id="9df69-163">受支持或不支持的策略提示</span><span class="sxs-lookup"><span data-stu-id="9df69-163">policy tips supported/not supported</span></span>  |
|---------|---------|
|<span data-ttu-id="9df69-164">OWA</span><span class="sxs-lookup"><span data-stu-id="9df69-164">OWA</span></span> |    <span data-ttu-id="9df69-165">支持</span><span class="sxs-lookup"><span data-stu-id="9df69-165">supported</span></span>     |
|<span data-ttu-id="9df69-166">Outlook Win 32</span><span class="sxs-lookup"><span data-stu-id="9df69-166">Outlook Win 32</span></span>    |  <span data-ttu-id="9df69-167">不支持</span><span class="sxs-lookup"><span data-stu-id="9df69-167">not supported</span></span>       |
|<span data-ttu-id="9df69-168">SharePoint</span><span class="sxs-lookup"><span data-stu-id="9df69-168">SharePoint</span></span>   |   <span data-ttu-id="9df69-169">支持</span><span class="sxs-lookup"><span data-stu-id="9df69-169">supported</span></span>      |
|<span data-ttu-id="9df69-170">OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="9df69-170">OneDrive for Business</span></span>    |    <span data-ttu-id="9df69-171">支持</span><span class="sxs-lookup"><span data-stu-id="9df69-171">supported</span></span>     |
|<span data-ttu-id="9df69-172">终结点设备</span><span class="sxs-lookup"><span data-stu-id="9df69-172">endpoint devices</span></span>   |  <span data-ttu-id="9df69-173">不支持</span><span class="sxs-lookup"><span data-stu-id="9df69-173">not supported</span></span>       |
