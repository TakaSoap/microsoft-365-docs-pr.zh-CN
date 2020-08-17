---
title: 了解记录
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: 了解有关记录的信息，以帮助您在 Microsoft 365 中实现记录管理解决方案。
ms.openlocfilehash: e64e91aeef307d05f23c47987a84baaf386324df
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/14/2020
ms.locfileid: "46685438"
---
# <a name="learn-about-records"></a><span data-ttu-id="92fc3-103">了解记录</span><span class="sxs-lookup"><span data-stu-id="92fc3-103">Learn about records</span></span>

><span data-ttu-id="92fc3-104">*[Microsoft 365 安全性与合规性许可指南](https://aka.ms/ComplianceSD)。*</span><span class="sxs-lookup"><span data-stu-id="92fc3-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="92fc3-105">在 Microsoft 365 中管理记录可帮助组织遵守公司策略、法律或法规义务，同时降低风险和法律责任。</span><span class="sxs-lookup"><span data-stu-id="92fc3-105">Managing records in Microsoft 365 helps your organization comply with corporate policies and legal or regulatory obligations, while also reducing risk and legal liability.</span></span>

<span data-ttu-id="92fc3-106">当内容被标记为记录时：</span><span class="sxs-lookup"><span data-stu-id="92fc3-106">When content is marked as a record:</span></span>

- <span data-ttu-id="92fc3-107">会针对[允许或阻止对记录项进行的操作](#compare-restrictions-for-what-actions-are-allowed-or-blocked)施加限制。</span><span class="sxs-lookup"><span data-stu-id="92fc3-107">Restrictions are placed on the items in terms of what [actions are allowed or blocked](#compare-restrictions-for-what-actions-are-allowed-or-blocked).</span></span>

- <span data-ttu-id="92fc3-108">记录了有关该项的其他活动。</span><span class="sxs-lookup"><span data-stu-id="92fc3-108">Additional activities about the item are logged.</span></span>

- <span data-ttu-id="92fc3-109">保留期结束时将其删除时，拥有处置证明。</span><span class="sxs-lookup"><span data-stu-id="92fc3-109">You have proof of disposition when the items are deleted at the end of their retention period.</span></span>

<span data-ttu-id="92fc3-110">使用[保留标签](retention.md#retention-labels)将内容标记为记录。</span><span class="sxs-lookup"><span data-stu-id="92fc3-110">You use [retention labels](retention.md#retention-labels) to mark content as a record.</span></span> <span data-ttu-id="92fc3-111">你可以发布这些标签，以便用户和管理员可以将其应用于内容，或自动应用这些标签到你想标记为记录的内容。</span><span class="sxs-lookup"><span data-stu-id="92fc3-111">You can either publish those labels so that users and administrators can manually apply them to content, or auto-apply those labels to content that you want to mark as a record.</span></span>

<span data-ttu-id="92fc3-112">通过使用保留标签来将内容标记为记录，可在 Microsoft 365 环境中实现单一一致的记录管理策略。</span><span class="sxs-lookup"><span data-stu-id="92fc3-112">By using retention labels to mark content as records, you can implement a single and consistent strategy for managing records across your Microsoft 365 environment.</span></span>

## <a name="compare-restrictions-for-what-actions-are-allowed-or-blocked"></a><span data-ttu-id="92fc3-113">比较对允许或阻止的操作的限制</span><span class="sxs-lookup"><span data-stu-id="92fc3-113">Compare restrictions for what actions are allowed or blocked</span></span>

<span data-ttu-id="92fc3-114">使用以下表格识别应用标准保留标签和将内容标记为记录的保留标签后，对内容施加的限制。</span><span class="sxs-lookup"><span data-stu-id="92fc3-114">Use the following table to identify what restrictions are placed on content as a result of applying a standard retention label, and retention labels that mark content as a record.</span></span> 

<span data-ttu-id="92fc3-115">标准保留标签的配置为无需将内容标记为记录，即可保留数据。</span><span class="sxs-lookup"><span data-stu-id="92fc3-115">A standard retention label has the configuration to retain data without marking content as a record.</span></span>

>[!NOTE] 
> <span data-ttu-id="92fc3-116">为确保完整性，表格包括已锁定和已解锁的记录列，适用于 SharePoint 和 OneDrive，但不适用于 Exchange。</span><span class="sxs-lookup"><span data-stu-id="92fc3-116">For completeness, the table includes columns for a locked and unlocked record, which is applicable to SharePoint and OneDrive, but not Exchange.</span></span> <span data-ttu-id="92fc3-117">锁定和解锁记录的功能使用 Exchange 项目不支持的[记录版本控制](record-versioning.md)功能。</span><span class="sxs-lookup"><span data-stu-id="92fc3-117">The ability to lock and unlock a record uses [record versioning](record-versioning.md) that isn't supported for Exchange items.</span></span> <span data-ttu-id="92fc3-118">因此，对于标记为记录的所有 Exchange 项目，该行为会映射到**记录 - 已锁定**列，而**记录 - 已解锁列**则不相关。</span><span class="sxs-lookup"><span data-stu-id="92fc3-118">So for all Exchange items that are marked as a record, the behavior maps to the **Record - locked** column, and the **Record - unlocked column** is not relevant.</span></span>


|<span data-ttu-id="92fc3-119">操作</span><span class="sxs-lookup"><span data-stu-id="92fc3-119">Action</span></span>| <span data-ttu-id="92fc3-120">保留标签</span><span class="sxs-lookup"><span data-stu-id="92fc3-120">Retention label</span></span> |<span data-ttu-id="92fc3-121">记录 - 已锁定</span><span class="sxs-lookup"><span data-stu-id="92fc3-121">Record - locked</span></span>| <span data-ttu-id="92fc3-122">记录 - 已解锁</span><span class="sxs-lookup"><span data-stu-id="92fc3-122">Record - unlocked</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="92fc3-123">编辑内容</span><span class="sxs-lookup"><span data-stu-id="92fc3-123">Edit contents</span></span>|<span data-ttu-id="92fc3-124">允许</span><span class="sxs-lookup"><span data-stu-id="92fc3-124">Allowed</span></span> | <span data-ttu-id="92fc3-125">**阻止**</span><span class="sxs-lookup"><span data-stu-id="92fc3-125">**Blocked**</span></span> | <span data-ttu-id="92fc3-126">允许</span><span class="sxs-lookup"><span data-stu-id="92fc3-126">Allowed</span></span>|
|<span data-ttu-id="92fc3-127">编辑属性（包括重命名）</span><span class="sxs-lookup"><span data-stu-id="92fc3-127">Edit properties, including rename</span></span>|<span data-ttu-id="92fc3-128">Allowed</span><span class="sxs-lookup"><span data-stu-id="92fc3-128">Allowed</span></span> |<span data-ttu-id="92fc3-129">允许</span><span class="sxs-lookup"><span data-stu-id="92fc3-129">Allowed</span></span> | <span data-ttu-id="92fc3-130">Allowed</span><span class="sxs-lookup"><span data-stu-id="92fc3-130">Allowed</span></span>|
|<span data-ttu-id="92fc3-131">删除</span><span class="sxs-lookup"><span data-stu-id="92fc3-131">Delete</span></span>|<span data-ttu-id="92fc3-132">允许 <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="92fc3-132">Allowed <sup>1</sup></span></span> |<span data-ttu-id="92fc3-133">**阻止**</span><span class="sxs-lookup"><span data-stu-id="92fc3-133">**Blocked**</span></span> | <span data-ttu-id="92fc3-134">**阻止**</span><span class="sxs-lookup"><span data-stu-id="92fc3-134">**Blocked**</span></span>|
|<span data-ttu-id="92fc3-135">复制</span><span class="sxs-lookup"><span data-stu-id="92fc3-135">Copy</span></span>|<span data-ttu-id="92fc3-136">Allowed</span><span class="sxs-lookup"><span data-stu-id="92fc3-136">Allowed</span></span> |<span data-ttu-id="92fc3-137">允许</span><span class="sxs-lookup"><span data-stu-id="92fc3-137">Allowed</span></span> | <span data-ttu-id="92fc3-138">Allowed</span><span class="sxs-lookup"><span data-stu-id="92fc3-138">Allowed</span></span>|
|<span data-ttu-id="92fc3-139">在容器 <sup>2</sup> 中移动</span><span class="sxs-lookup"><span data-stu-id="92fc3-139">Move within container <sup>2</sup></span></span>|<span data-ttu-id="92fc3-140">Allowed</span><span class="sxs-lookup"><span data-stu-id="92fc3-140">Allowed</span></span> |<span data-ttu-id="92fc3-141">允许</span><span class="sxs-lookup"><span data-stu-id="92fc3-141">Allowed</span></span> | <span data-ttu-id="92fc3-142">Allowed</span><span class="sxs-lookup"><span data-stu-id="92fc3-142">Allowed</span></span>|
|<span data-ttu-id="92fc3-143">围绕容器 <sup>2</sup> 移动</span><span class="sxs-lookup"><span data-stu-id="92fc3-143">Move across containers <sup>2</sup></span></span>|<span data-ttu-id="92fc3-144">允许</span><span class="sxs-lookup"><span data-stu-id="92fc3-144">Allowed</span></span> |<span data-ttu-id="92fc3-145">如果从未解锁，则允许</span><span class="sxs-lookup"><span data-stu-id="92fc3-145">Allowed if never unlocked</span></span> | <span data-ttu-id="92fc3-146">允许</span><span class="sxs-lookup"><span data-stu-id="92fc3-146">Allowed</span></span>|
|<span data-ttu-id="92fc3-147">打开/读取</span><span class="sxs-lookup"><span data-stu-id="92fc3-147">Open/Read</span></span>|<span data-ttu-id="92fc3-148">Allowed</span><span class="sxs-lookup"><span data-stu-id="92fc3-148">Allowed</span></span> |<span data-ttu-id="92fc3-149">允许</span><span class="sxs-lookup"><span data-stu-id="92fc3-149">Allowed</span></span> | <span data-ttu-id="92fc3-150">Allowed</span><span class="sxs-lookup"><span data-stu-id="92fc3-150">Allowed</span></span>|
|<span data-ttu-id="92fc3-151">更改标签</span><span class="sxs-lookup"><span data-stu-id="92fc3-151">Change label</span></span>|<span data-ttu-id="92fc3-152">允许</span><span class="sxs-lookup"><span data-stu-id="92fc3-152">Allowed</span></span> |<span data-ttu-id="92fc3-153">允许 - 仅容器管理员</span><span class="sxs-lookup"><span data-stu-id="92fc3-153">Allowed - container admin only</span></span> | <span data-ttu-id="92fc3-154">允许 - 仅容器管理员</span><span class="sxs-lookup"><span data-stu-id="92fc3-154">Allowed - container admin only</span></span>|
|<span data-ttu-id="92fc3-155">删除标签</span><span class="sxs-lookup"><span data-stu-id="92fc3-155">Remove label</span></span>|<span data-ttu-id="92fc3-156">允许</span><span class="sxs-lookup"><span data-stu-id="92fc3-156">Allowed</span></span> |<span data-ttu-id="92fc3-157">允许 - 仅容器管理员</span><span class="sxs-lookup"><span data-stu-id="92fc3-157">Allowed - container admin only</span></span> | <span data-ttu-id="92fc3-158">允许 - 仅容器管理员</span><span class="sxs-lookup"><span data-stu-id="92fc3-158">Allowed - container admin only</span></span>|

<span data-ttu-id="92fc3-159">页脚：</span><span class="sxs-lookup"><span data-stu-id="92fc3-159">Footnotes:</span></span>

<span data-ttu-id="92fc3-160"><sup>1</sup>OneDrive 和 Exchange 支持此功能，方法是在安全位置保留一份副本，但 SharePoint 阻止此功能。</span><span class="sxs-lookup"><span data-stu-id="92fc3-160"><sup>1</sup> Supported by OneDrive and Exchange by retaining a copy in a secured location, but blocked by SharePoint.</span></span>

<span data-ttu-id="92fc3-161">向用户发送一条消息，询问用户是否尝试删除 SharePoint 中带标记的文档：</span><span class="sxs-lookup"><span data-stu-id="92fc3-161">Message a user sees if they try to delete a labeled document in SharePoint:</span></span>

![指明项未从 SharePoint 中删除的消息](../media/d0020726-1593-4a96-b07c-89b275e75c49.png)


<span data-ttu-id="92fc3-163"><sup>2</sup>容器包括 SharePoint 文档库和 Exchange 邮箱。</span><span class="sxs-lookup"><span data-stu-id="92fc3-163"><sup>2</sup> Containers include SharePoint document libraries and Exchange mailboxes.</span></span>

## <a name="next-steps"></a><span data-ttu-id="92fc3-164">后续步骤</span><span class="sxs-lookup"><span data-stu-id="92fc3-164">Next steps</span></span>

<span data-ttu-id="92fc3-165">如果还没有用于记录管理的保留标签，请参阅[开始使用保留策略和保留标签](get-started-with-retention.md)。</span><span class="sxs-lookup"><span data-stu-id="92fc3-165">If you don't yet have retention labels to use for records management, see [Get started with retention policies and retention labels](get-started-with-retention.md).</span></span>

<span data-ttu-id="92fc3-166">若要将内容标记为记录，请参阅[使用保留标签声明记录](declare-records.md)。</span><span class="sxs-lookup"><span data-stu-id="92fc3-166">To mark content as a record, see [Declare records by using retention labels](declare-records.md).</span></span>
