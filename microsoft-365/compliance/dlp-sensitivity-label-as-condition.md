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
ms.openlocfilehash: bb06ed6919a396bef1e5d1f1cb04731fa11267ae
ms.sourcegitcommit: c1ee4ed3c5826872b57339e1e1aa33b4d2209711
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/23/2020
ms.locfileid: "48235711"
---
# <a name="use-sensitivity-labels-as-conditions-in-dlp-policies-preview"></a><span data-ttu-id="00074-103">在 DLP 策略中使用敏感度标签作为条件（预览版）</span><span class="sxs-lookup"><span data-stu-id="00074-103">Use sensitivity labels as conditions in DLP policies (preview)</span></span>

<span data-ttu-id="00074-104">在以下位置的 DLP 策略中，可使用[敏感度标签](sensitivity-labels.md)作为条件：</span><span class="sxs-lookup"><span data-stu-id="00074-104">You can use [sensitivity labels](sensitivity-labels.md) as a condition in DLP policies for these location:</span></span>

- <span data-ttu-id="00074-105">Exchange Online 电子邮件</span><span class="sxs-lookup"><span data-stu-id="00074-105">Exchange Online email messages</span></span>
- <span data-ttu-id="00074-106">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="00074-106">SharePoint Online</span></span>
- <span data-ttu-id="00074-107">OneDrive for Business 站点</span><span class="sxs-lookup"><span data-stu-id="00074-107">OneDrive for Business sites</span></span>
- <span data-ttu-id="00074-108">Windows 10 设备</span><span class="sxs-lookup"><span data-stu-id="00074-108">Windows 10 devices</span></span>

<span data-ttu-id="00074-109">敏感度标签作为一个选项出现在**内容包含**列表中。</span><span class="sxs-lookup"><span data-stu-id="00074-109">Sensitivity labels appear as an option in the **Content contains** list.</span></span>

![使用敏感度标签作为条件](../media/dlp-sensitivity-label-as-a-condition.png)

## <a name="supported-items-scenarios-and-policy-tips"></a><span data-ttu-id="00074-111">支持的项目、方案和策略提示</span><span class="sxs-lookup"><span data-stu-id="00074-111">Supported items, scenarios, and policy tips</span></span>

<span data-ttu-id="00074-112">可在这些项目和方案中使用敏感度标签作为条件。</span><span class="sxs-lookup"><span data-stu-id="00074-112">You can use sensitivity labels as conditions on these items and in these scenarios.</span></span>

### <a name="supported-items"></a><span data-ttu-id="00074-113">支持的项目：</span><span class="sxs-lookup"><span data-stu-id="00074-113">Supported items</span></span>

|<span data-ttu-id="00074-114">服务</span><span class="sxs-lookup"><span data-stu-id="00074-114">service</span></span>  |<span data-ttu-id="00074-115">项目类型</span><span class="sxs-lookup"><span data-stu-id="00074-115">item type</span></span>  |<span data-ttu-id="00074-116">可用于策略提示</span><span class="sxs-lookup"><span data-stu-id="00074-116">available to policy tip</span></span>  |<span data-ttu-id="00074-117">可强制实施</span><span class="sxs-lookup"><span data-stu-id="00074-117">enforceable</span></span>  |
|---------|---------|---------|---------|
|<span data-ttu-id="00074-118">Exchange</span><span class="sxs-lookup"><span data-stu-id="00074-118">Exchange</span></span>    |<span data-ttu-id="00074-119">电子邮件</span><span class="sxs-lookup"><span data-stu-id="00074-119">email message</span></span>         |<span data-ttu-id="00074-120">是</span><span class="sxs-lookup"><span data-stu-id="00074-120">yes</span></span>         |<span data-ttu-id="00074-121">是</span><span class="sxs-lookup"><span data-stu-id="00074-121">yes</span></span>         |
|<span data-ttu-id="00074-122">Exchange</span><span class="sxs-lookup"><span data-stu-id="00074-122">Exchange</span></span>    |<span data-ttu-id="00074-123">电子邮件附件</span><span class="sxs-lookup"><span data-stu-id="00074-123">email attachment</span></span>         |<span data-ttu-id="00074-124">否\*</span><span class="sxs-lookup"><span data-stu-id="00074-124">no \*</span></span>         |<span data-ttu-id="00074-125">否\*</span><span class="sxs-lookup"><span data-stu-id="00074-125">no \*</span></span>         |
|<span data-ttu-id="00074-126">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="00074-126">SharePoint Online</span></span>     |<span data-ttu-id="00074-127">SharePoint Online 中的列表</span><span class="sxs-lookup"><span data-stu-id="00074-127">items in SharePoint Online</span></span>         |<span data-ttu-id="00074-128">是</span><span class="sxs-lookup"><span data-stu-id="00074-128">yes</span></span>         |<span data-ttu-id="00074-129">是</span><span class="sxs-lookup"><span data-stu-id="00074-129">yes</span></span>         |
|<span data-ttu-id="00074-130">OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="00074-130">OneDrive for Business</span></span>     |<span data-ttu-id="00074-131">项目</span><span class="sxs-lookup"><span data-stu-id="00074-131">items</span></span>         |<span data-ttu-id="00074-132">是</span><span class="sxs-lookup"><span data-stu-id="00074-132">yes</span></span>         |<span data-ttu-id="00074-133">是</span><span class="sxs-lookup"><span data-stu-id="00074-133">yes</span></span>         |
|<span data-ttu-id="00074-134">Teams</span><span class="sxs-lookup"><span data-stu-id="00074-134">Teams</span></span>     |<span data-ttu-id="00074-135">Teams 聊天和通道消息</span><span class="sxs-lookup"><span data-stu-id="00074-135">Teams and channel messages</span></span>         |<span data-ttu-id="00074-136">不适用</span><span class="sxs-lookup"><span data-stu-id="00074-136">not applicable</span></span>         |<span data-ttu-id="00074-137">不适用</span><span class="sxs-lookup"><span data-stu-id="00074-137">not applicable</span></span>         |
|<span data-ttu-id="00074-138">Teams</span><span class="sxs-lookup"><span data-stu-id="00074-138">Teams</span></span>     |<span data-ttu-id="00074-139">附件</span><span class="sxs-lookup"><span data-stu-id="00074-139">attachements</span></span>         |<span data-ttu-id="00074-140">是 \*\*</span><span class="sxs-lookup"><span data-stu-id="00074-140">yes \*\*</span></span>         |<span data-ttu-id="00074-141">是 \*\*</span><span class="sxs-lookup"><span data-stu-id="00074-141">yes \*\*</span></span>         |
|<span data-ttu-id="00074-142">Windows 10 设备（预览版）</span><span class="sxs-lookup"><span data-stu-id="00074-142">Windows 10 devices (preview)</span></span>     |<span data-ttu-id="00074-143">项目</span><span class="sxs-lookup"><span data-stu-id="00074-143">items</span></span>         |<span data-ttu-id="00074-144">是</span><span class="sxs-lookup"><span data-stu-id="00074-144">yes</span></span>         |<span data-ttu-id="00074-145">是</span><span class="sxs-lookup"><span data-stu-id="00074-145">yes</span></span>         |
|<span data-ttu-id="00074-146">MCAS（预览版）</span><span class="sxs-lookup"><span data-stu-id="00074-146">MCAS (preview)</span></span> |<span data-ttu-id="00074-147">项目</span><span class="sxs-lookup"><span data-stu-id="00074-147">items</span></span>         |<span data-ttu-id="00074-148">是</span><span class="sxs-lookup"><span data-stu-id="00074-148">yes</span></span>         |<span data-ttu-id="00074-149">是</span><span class="sxs-lookup"><span data-stu-id="00074-149">yes</span></span>         |

<span data-ttu-id="00074-150">\* 支持 DLP 对电子邮件的敏感度标签进行检测。</span><span class="sxs-lookup"><span data-stu-id="00074-150">\* DLP detection of sensitivity labels on emails are supported.</span></span> <span data-ttu-id="00074-151">不支持 DLP 对带有敏感度标签的电子邮件附件进行检测。</span><span class="sxs-lookup"><span data-stu-id="00074-151">DLP detection of sensitivity labeled email attachments are not.</span></span>

<span data-ttu-id="00074-152">\*\* 在一对一聊天或频道的 Teams 中发送的附件将自动上传到 OneDrive for Business 和 SharePoint。</span><span class="sxs-lookup"><span data-stu-id="00074-152">\*\* Attachments sent in Teams over 1:1 chat or channels are automatically uploaded to One drive for business and SharePoint.</span></span> <span data-ttu-id="00074-153">因此，如果你的 DLP 策略中包含 SharePoint Online 或 OneDrive for Business，则在 Teams 中发送的带标签的附件将自动包含在此条件的范围内。</span><span class="sxs-lookup"><span data-stu-id="00074-153">So if SharePoint Online or One Drive for Business are included as locations in your DLP policy, then labeled attachments sent in Teams will be automatically included in the scope of this condition.</span></span> <span data-ttu-id="00074-154">不需要在 DLP 策略中选择用作位置的 Teams。</span><span class="sxs-lookup"><span data-stu-id="00074-154">Teams as a location does not need to be selected in the DLP policy.</span></span>

### <a name="supported-scenarios"></a><span data-ttu-id="00074-155">支持的方案</span><span class="sxs-lookup"><span data-stu-id="00074-155">Supported scenarios</span></span>

- <span data-ttu-id="00074-156">当 DLP 管理员选择将一个或多个敏感度标签作为条件时，将能够看到租户中所有敏感度标签的列表。</span><span class="sxs-lookup"><span data-stu-id="00074-156">DLP Admin will be able to see a list of all sensitivity labels in the tenant when they choose to include one or more sensitivity labels as a condition.</span></span>
- <span data-ttu-id="00074-157">按上述支持矩阵所示，支持在所有工作负载中使用敏感度标签作为条件</span><span class="sxs-lookup"><span data-stu-id="00074-157">Using sensitivity labels as a condition is supported across all workloads as indicated in the support matrix above</span></span>
- <span data-ttu-id="00074-158">对于包含敏感度标签作为条件的 DLP 策略，将继续跨工作负载（Outlook Win32 除外）显示 DLP 策略提示。</span><span class="sxs-lookup"><span data-stu-id="00074-158">DLP policy tips will continue to be shown across workloads (except Outlook Win32) for DLP policies which contain sensitivity label as a condition.</span></span>
- <span data-ttu-id="00074-159">如果与包含敏感度标签的 DLP 策略匹配，则敏感度标签也将显示为事件报告电子邮件的一部分。</span><span class="sxs-lookup"><span data-stu-id="00074-159">Sensitivity labels will also appear as a part of the incident report email if a DLP policy with sensitivity label as a condition is matched.</span></span>
- <span data-ttu-id="00074-160">敏感度标签的详细信息也将显示在 DLP 规则匹配审核日志中，该策略包含敏感度标签作为条件。</span><span class="sxs-lookup"><span data-stu-id="00074-160">Sensitivity label details will also be shown in the DLP rule match audit log for a DLP policy match which contains sensitivity label as a condition.</span></span>


### <a name="support-policy-tips"></a><span data-ttu-id="00074-161">支持策略提示</span><span class="sxs-lookup"><span data-stu-id="00074-161">Support policy tips</span></span>


|<span data-ttu-id="00074-162">工作负载</span><span class="sxs-lookup"><span data-stu-id="00074-162">workload</span></span>  |<span data-ttu-id="00074-163">受支持或不支持的策略提示</span><span class="sxs-lookup"><span data-stu-id="00074-163">policy tips supported/not supported</span></span>  |
|---------|---------|
|<span data-ttu-id="00074-164">OWA</span><span class="sxs-lookup"><span data-stu-id="00074-164">OWA</span></span> |    <span data-ttu-id="00074-165">支持</span><span class="sxs-lookup"><span data-stu-id="00074-165">supported</span></span>     |
|<span data-ttu-id="00074-166">Outlook Win 32</span><span class="sxs-lookup"><span data-stu-id="00074-166">Outlook Win 32</span></span>    |  <span data-ttu-id="00074-167">不支持</span><span class="sxs-lookup"><span data-stu-id="00074-167">not supported</span></span>       |
|<span data-ttu-id="00074-168">SharePoint</span><span class="sxs-lookup"><span data-stu-id="00074-168">SharePoint</span></span>   |   <span data-ttu-id="00074-169">支持</span><span class="sxs-lookup"><span data-stu-id="00074-169">supported</span></span>      |
|<span data-ttu-id="00074-170">OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="00074-170">OneDrive for Business</span></span>    |    <span data-ttu-id="00074-171">支持</span><span class="sxs-lookup"><span data-stu-id="00074-171">supported</span></span>     |
|<span data-ttu-id="00074-172">终结点设备</span><span class="sxs-lookup"><span data-stu-id="00074-172">endpoint devices</span></span>   |  <span data-ttu-id="00074-173">不支持</span><span class="sxs-lookup"><span data-stu-id="00074-173">not supported</span></span>       |
