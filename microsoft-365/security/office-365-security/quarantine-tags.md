---
title: 隔离标记
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: ''
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
ROBOTS: NOINDEX
description: 管理员可以了解如何使用隔离标记来控制用户能够对其隔离邮件执行的操作。
ms.openlocfilehash: 68f28e2dff3bdeada2685ef6806489f5e57f5daf
ms.sourcegitcommit: d81c7cea85af6ad5fef81d3c930514a51464368c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/04/2020
ms.locfileid: "49572665"
---
# <a name="quarantine-tags"></a><span data-ttu-id="3fe6b-103">隔离标记</span><span class="sxs-lookup"><span data-stu-id="3fe6b-103">Quarantine tags</span></span>

> [!NOTE]
> <span data-ttu-id="3fe6b-104">本文中所述的功能目前处于预览阶段，不可用于所有人，并且可能会发生更改。</span><span class="sxs-lookup"><span data-stu-id="3fe6b-104">The features that are described in this article are currently in Preview, aren't available to everyone, and are subject to change.</span></span>

<span data-ttu-id="3fe6b-105">Exchange Online Protection (EOP 中的隔离标记) 允许管理员根据邮件到达隔离的方式来控制哪些用户能够对隔离邮件执行的操作。</span><span class="sxs-lookup"><span data-stu-id="3fe6b-105">Quarantine tags in Exchange Online Protection (EOP) allow admins to control what users are able to do to their quarantined messages based on how the message arrived in quarantine.</span></span>

<span data-ttu-id="3fe6b-106">EOP 传统上允许或阻止了 [隔离](find-and-release-quarantined-messages-as-a-user.md) 和 [最终用户垃圾邮件通知](use-spam-notifications-to-release-and-report-quarantined-messages.md)中的邮件的特定级别的交互。</span><span class="sxs-lookup"><span data-stu-id="3fe6b-106">EOP has traditionally allowed or prevented certain levels of interactivity for messages in [quarantine](find-and-release-quarantined-messages-as-a-user.md) and in [end-user spam notifications](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span></span> <span data-ttu-id="3fe6b-107">例如，最终用户可以查看和释放反垃圾邮件筛选隔离为垃圾邮件或批量的邮件，但不能查看或释放被隔离为高可信度网络钓鱼的邮件。</span><span class="sxs-lookup"><span data-stu-id="3fe6b-107">For example, end-users can view and release messages that were quarantined by anti-spam filtering as spam or bulk, but they can't view or release messages that were quarantined as high confidence phishing.</span></span>

<span data-ttu-id="3fe6b-108">对于 [受支持的保护功能](#step-2-assign-a-quarantine-tag-to-supported-features)，隔离标记指定了允许哪些用户在最终用户的垃圾邮件通知邮件以及隔离邮件的隔离邮件中执行的操作 (用户是其收件人) 的邮件。</span><span class="sxs-lookup"><span data-stu-id="3fe6b-108">For [supported protection features](#step-2-assign-a-quarantine-tag-to-supported-features), quarantine tags specify what users are allowed to do in end-user spam notification messages and in their quarantined messages in quarantine (messages where the user is a recipient).</span></span> <span data-ttu-id="3fe6b-109">将自动分配默认隔离标记，以针对隔离邮件强制实施最终用户的历史功能。</span><span class="sxs-lookup"><span data-stu-id="3fe6b-109">Default quarantine tags are automatically assigned to enforce the historical capabilities for end-users on quarantined messages.</span></span> <span data-ttu-id="3fe6b-110">或者，您可以创建自定义隔离标记并将其分配给最终用户，以允许或阻止最终用户对隔离邮件执行特定操作。</span><span class="sxs-lookup"><span data-stu-id="3fe6b-110">Or, you can create and assign custom quarantine tags to allow or prevent end-users from performing specific actions on quarantined messages.</span></span>

<span data-ttu-id="3fe6b-111">各个权限组合到以下预设权限组中：</span><span class="sxs-lookup"><span data-stu-id="3fe6b-111">The individual permissions are combined into the following preset permission groups:</span></span>

- <span data-ttu-id="3fe6b-112">禁止访问</span><span class="sxs-lookup"><span data-stu-id="3fe6b-112">No access</span></span>
- <span data-ttu-id="3fe6b-113">受限访问</span><span class="sxs-lookup"><span data-stu-id="3fe6b-113">Limited access</span></span>
- <span data-ttu-id="3fe6b-114">完全访问</span><span class="sxs-lookup"><span data-stu-id="3fe6b-114">Full access</span></span>

<span data-ttu-id="3fe6b-115">下表介绍了可用的个人权限以及预置权限组中包括或未包括的内容：</span><span class="sxs-lookup"><span data-stu-id="3fe6b-115">The available individual permissions and what's included or not included in the preset permission groups are described in the following table:</span></span>

|<span data-ttu-id="3fe6b-116">权限</span><span class="sxs-lookup"><span data-stu-id="3fe6b-116">Permission</span></span>|<span data-ttu-id="3fe6b-117">禁止访问</span><span class="sxs-lookup"><span data-stu-id="3fe6b-117">No access</span></span>|<span data-ttu-id="3fe6b-118">受限访问</span><span class="sxs-lookup"><span data-stu-id="3fe6b-118">Limited access</span></span>|<span data-ttu-id="3fe6b-119">完全访问</span><span class="sxs-lookup"><span data-stu-id="3fe6b-119">Full access</span></span>|
|---|:---:|:---:|:---:|
|<span data-ttu-id="3fe6b-120">**允许发件人** (_PermissionToAllowSender_) </span><span class="sxs-lookup"><span data-stu-id="3fe6b-120">**Allow sender** (_PermissionToAllowSender_)</span></span>|||![复选标记](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|<span data-ttu-id="3fe6b-122">**阻止发件人** (_PermissionToBlockSender_) </span><span class="sxs-lookup"><span data-stu-id="3fe6b-122">**Block sender** (_PermissionToBlockSender_)</span></span>||![复选标记](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![复选标记](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|<span data-ttu-id="3fe6b-125">**删除** (_PermissionToDelete_) </span><span class="sxs-lookup"><span data-stu-id="3fe6b-125">**Delete** (_PermissionToDelete_)</span></span>||![复选标记](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![复选标记](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|<span data-ttu-id="3fe6b-128"> (_PermissionToPreview_) **预览**</span><span class="sxs-lookup"><span data-stu-id="3fe6b-128">**Preview** (_PermissionToPreview_)</span></span>||![复选标记](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![复选标记](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|<span data-ttu-id="3fe6b-131">**允许收件人释放来自隔离** (_PermissionToRelease_ 的邮件) </span><span class="sxs-lookup"><span data-stu-id="3fe6b-131">**Allow recipients to release a message from quarantine** (_PermissionToRelease_)</span></span>|||![复选标记](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|<span data-ttu-id="3fe6b-133">**允许收件人请求从隔离区发布邮件** (_PermissionToRequestRelease_) </span><span class="sxs-lookup"><span data-stu-id="3fe6b-133">**Allow recipients to request a message to be released from quarantine** (_PermissionToRequestRelease_)</span></span>||![复选标记](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
|

<span data-ttu-id="3fe6b-135">如果您不喜欢预设权限组中的默认权限，则可以在创建或修改自定义隔离标记时使用自定义权限。</span><span class="sxs-lookup"><span data-stu-id="3fe6b-135">If you don't like the default permissions in the preset permission groups, you can use custom permissions when you create or modify custom quarantine tags.</span></span> <span data-ttu-id="3fe6b-136">有关每个权限执行的操作的详细信息，请参阅本文后面的 [隔离标记权限详细信息](#quarantine-tag-permission-details) 部分。</span><span class="sxs-lookup"><span data-stu-id="3fe6b-136">For more information about what each permission does, see the [Quarantine tag permission details](#quarantine-tag-permission-details) section later in this article.</span></span>

<span data-ttu-id="3fe6b-137">在使用 Exchange Online 邮箱的 Microsoft 365 组织的 "安全 & 合规中心" 或 "PowerShell (Exchange Online PowerShell" 中创建和分配隔离标记;EOP 组织中的独立 EOP PowerShell，不) Exchange Online 邮箱。</span><span class="sxs-lookup"><span data-stu-id="3fe6b-137">You create and assign quarantine tags in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with Exchange Online Mailboxes; standalone EOP PowerShell in EOP organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="3fe6b-138">开始前，有必要了解什么？</span><span class="sxs-lookup"><span data-stu-id="3fe6b-138">What do you need to know before you begin?</span></span>

- <span data-ttu-id="3fe6b-139">安全与合规中心的打开网址为 <https://protection.office.com/>。</span><span class="sxs-lookup"><span data-stu-id="3fe6b-139">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="3fe6b-140">若要直接转到 " **隔离标记** " 页，请打开 <https://protection.office.com/quarantineTags> 。</span><span class="sxs-lookup"><span data-stu-id="3fe6b-140">To go directly to the **Quarantine tags** page, open <https://protection.office.com/quarantineTags>.</span></span>

- <span data-ttu-id="3fe6b-141">若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="3fe6b-141">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="3fe6b-142">若要连接到独立 EOP PowerShell，请参阅[连接到 Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)。</span><span class="sxs-lookup"><span data-stu-id="3fe6b-142">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="3fe6b-143">若要查看、创建、修改或删除隔离标记，您需要是 [安全 & 合规性中心](permissions-in-the-security-and-compliance-center.md)中的 "**组织管理**" 或 "**安全管理员**" 角色的成员。</span><span class="sxs-lookup"><span data-stu-id="3fe6b-143">To view, create, modify, or remove quarantine tags, you need to be a member of the **Organization Management** or **Security Administrator** roles in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="step-1-create-quarantine-tags-in-the-security--compliance-center"></a><span data-ttu-id="3fe6b-144">步骤1：在安全 & 合规中心中创建隔离标记</span><span class="sxs-lookup"><span data-stu-id="3fe6b-144">Step 1: Create quarantine tags in the Security & Compliance Center</span></span>

1. <span data-ttu-id="3fe6b-145">在安全 & 合规性中心中，转到 " **威胁管理** \> **策略** "，然后选择 " **隔离标记**"。</span><span class="sxs-lookup"><span data-stu-id="3fe6b-145">In the Security & Compliance Center, go to **Threat management** \> **Policy** and then select **Quarantine tags**.</span></span>

2. <span data-ttu-id="3fe6b-146">在 " **隔离标记** " 页上，选择 " **添加自定义标记**"。</span><span class="sxs-lookup"><span data-stu-id="3fe6b-146">On the **Quarantine tags** page, select **Add custom tag**.</span></span>

3. <span data-ttu-id="3fe6b-147">将打开 " **新建标记** " 向导。</span><span class="sxs-lookup"><span data-stu-id="3fe6b-147">The **New tag** wizard opens.</span></span> <span data-ttu-id="3fe6b-148">在 " **标记名称** " 页上，在 " **标记名称** " 字段中输入一个简短但唯一的名称。</span><span class="sxs-lookup"><span data-stu-id="3fe6b-148">On the **Tag name** page, enter a brief but unique name in the **Tag name** field.</span></span> <span data-ttu-id="3fe6b-149">在后面的步骤中，您需要确定并按名称选择标记。</span><span class="sxs-lookup"><span data-stu-id="3fe6b-149">You'll need to identify and select the tag by name in upcoming steps.</span></span> <span data-ttu-id="3fe6b-150">完成后，单击“下一步”。</span><span class="sxs-lookup"><span data-stu-id="3fe6b-150">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="3fe6b-151">在 " **收件人邮件访问** " 页上，选择下列值之一：</span><span class="sxs-lookup"><span data-stu-id="3fe6b-151">On the **Recipient message access** page, select one of the following values:</span></span>
   - <span data-ttu-id="3fe6b-152">**禁止访问**</span><span class="sxs-lookup"><span data-stu-id="3fe6b-152">**No access**</span></span>
   - <span data-ttu-id="3fe6b-153">**受限访问**</span><span class="sxs-lookup"><span data-stu-id="3fe6b-153">**Limited access**</span></span>
   - <span data-ttu-id="3fe6b-154">**完全访问**</span><span class="sxs-lookup"><span data-stu-id="3fe6b-154">**Full access**</span></span>

   <span data-ttu-id="3fe6b-155">本文前面将介绍这些权限组中包含的各个权限。</span><span class="sxs-lookup"><span data-stu-id="3fe6b-155">The individual permissions that are included in these permission groups are described earlier in this article.</span></span>

   <span data-ttu-id="3fe6b-156">若要指定自定义权限，请选择 " **设置特定访问权限 (高级)** "，并配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="3fe6b-156">To specify custom permissions, select **Set specific access (Advanced)** and configure the following settings:</span></span>

     - <span data-ttu-id="3fe6b-157">**选择 "释放操作" 首选项**：选择下列值之一：</span><span class="sxs-lookup"><span data-stu-id="3fe6b-157">**Select release action preference**: Select one of the following values:</span></span>
       - <span data-ttu-id="3fe6b-158">**无发布操作**：这是默认值。</span><span class="sxs-lookup"><span data-stu-id="3fe6b-158">**No release action**: This is the default value.</span></span>
       - <span data-ttu-id="3fe6b-159">**允许收件人从隔离区中释放邮件**</span><span class="sxs-lookup"><span data-stu-id="3fe6b-159">**Allow recipients to release a message from quarantine**</span></span>
       - <span data-ttu-id="3fe6b-160">**允许收件人请求从隔离区中释放邮件**</span><span class="sxs-lookup"><span data-stu-id="3fe6b-160">**Allow recipients to request a message to be released from quarantine**</span></span>

     - <span data-ttu-id="3fe6b-161">**选择 "其他操作收件人可对隔离邮件执行操作**"：选择以下任何值：</span><span class="sxs-lookup"><span data-stu-id="3fe6b-161">**Select additional actions recipients can take on quarantined messages**: Select some, all, or none of the following values:</span></span>
       - <span data-ttu-id="3fe6b-162">**删除**</span><span class="sxs-lookup"><span data-stu-id="3fe6b-162">**Delete**</span></span>
       - <span data-ttu-id="3fe6b-163">**预览**</span><span class="sxs-lookup"><span data-stu-id="3fe6b-163">**Preview**</span></span>
       - <span data-ttu-id="3fe6b-164">**允许发件人**</span><span class="sxs-lookup"><span data-stu-id="3fe6b-164">**Allow sender**</span></span>
       - <span data-ttu-id="3fe6b-165">**阻止发件人**</span><span class="sxs-lookup"><span data-stu-id="3fe6b-165">**Block sender**</span></span>

   <span data-ttu-id="3fe6b-166">这些权限以及它们对隔离邮件和最终用户垃圾邮件通知中的影响将在本文后面的 [隔离标记权限详细信息](#quarantine-tag-permission-details) 部分中进行介绍。</span><span class="sxs-lookup"><span data-stu-id="3fe6b-166">These permissions and their effect on quarantined messages and in end-user spam notifications are described in the [Quarantine tag permission details](#quarantine-tag-permission-details) section later in this article.</span></span>

   <span data-ttu-id="3fe6b-167">完成后，单击“下一步”。</span><span class="sxs-lookup"><span data-stu-id="3fe6b-167">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="3fe6b-168">在出现的 **摘要** 页上，查看您的设置。</span><span class="sxs-lookup"><span data-stu-id="3fe6b-168">On the **Summary** page that appears, review your settings.</span></span> <span data-ttu-id="3fe6b-169">您可以在每个设置上单击 " **编辑** " 以修改它。</span><span class="sxs-lookup"><span data-stu-id="3fe6b-169">You can click **Edit** on each setting to modify it.</span></span>

   <span data-ttu-id="3fe6b-170">完成后，请单击 " **提交**"。</span><span class="sxs-lookup"><span data-stu-id="3fe6b-170">When you're finished, click **Submit**.</span></span>

6. <span data-ttu-id="3fe6b-171">在出现的确认页上单击 " **完成** "。</span><span class="sxs-lookup"><span data-stu-id="3fe6b-171">Click **Done** on the confirmation page that appears.</span></span>

<span data-ttu-id="3fe6b-172">现在您已准备好将隔离标记分配给隔离功能，如 " [步骤 2](#step-2-assign-a-quarantine-tag-to-supported-features) " 一节中所述。</span><span class="sxs-lookup"><span data-stu-id="3fe6b-172">Now you are ready to assign the quarantine tag to a quarantine feature as described in the [Step 2](#step-2-assign-a-quarantine-tag-to-supported-features) section.</span></span>

### <a name="create-quarantine-tags-in-powershell"></a><span data-ttu-id="3fe6b-173">在 PowerShell 中创建隔离标记</span><span class="sxs-lookup"><span data-stu-id="3fe6b-173">Create quarantine tags in PowerShell</span></span>

<span data-ttu-id="3fe6b-174">如果您更愿意使用 PowerShell 创建隔离标记，请连接到 Exchange Online PowerShell 或 Exchange Online Protection PowerShell，并使用 **QuarantineTag** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="3fe6b-174">If you'd rather use PowerShell to create quarantine tags, connect to Exchange Online PowerShell or Exchange Online Protection PowerShell and use the **New-QuarantineTag** cmdlet.</span></span> <span data-ttu-id="3fe6b-175">有两种不同的方法可供选择：</span><span class="sxs-lookup"><span data-stu-id="3fe6b-175">You have two different methods to choose from:</span></span>

- <span data-ttu-id="3fe6b-176">使用 _EndUserQuarantinePermissionsValue_ 参数。</span><span class="sxs-lookup"><span data-stu-id="3fe6b-176">Use the _EndUserQuarantinePermissionsValue_ parameter.</span></span>
- <span data-ttu-id="3fe6b-177">使用 _EndUserQuarantinePermissions_ 参数。</span><span class="sxs-lookup"><span data-stu-id="3fe6b-177">Use the _EndUserQuarantinePermissions_ parameter.</span></span>

<span data-ttu-id="3fe6b-178">以下各节介绍了这些方法。</span><span class="sxs-lookup"><span data-stu-id="3fe6b-178">These methods are described in the following sections.</span></span>

#### <a name="use-the-enduserquarantinepermissionsvalue-parameter"></a><span data-ttu-id="3fe6b-179">使用 EndUserQuarantinePermissionsValue 参数</span><span class="sxs-lookup"><span data-stu-id="3fe6b-179">Use the EndUserQuarantinePermissionsValue parameter</span></span>

<span data-ttu-id="3fe6b-180">若要使用 _EndUserQuarantinePermissionsValue_ 参数创建隔离标记，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="3fe6b-180">To create a quarantine tag using the _EndUserQuarantinePermissionsValue_ parameter, use the following syntax:</span></span>

```powershell
New-QuarantineTag -Name "<UniqueName>" -EndUserQuarantinePermissionsValue <0 to 236>
```

<span data-ttu-id="3fe6b-181">_EndUserQuarantinePermissionsValue_ 参数使用从二进制值转换而来的十进制值。</span><span class="sxs-lookup"><span data-stu-id="3fe6b-181">The _EndUserQuarantinePermissionsValue_ parameter uses a decimal value that's converted from a binary value.</span></span> <span data-ttu-id="3fe6b-182">二进制值对应于可用的最终用户隔离权限，以特定顺序排列。</span><span class="sxs-lookup"><span data-stu-id="3fe6b-182">The binary value corresponds to the available end-user quarantine permissions in a specific order.</span></span> <span data-ttu-id="3fe6b-183">对于每个权限，值1等于 True，值0等于 False。</span><span class="sxs-lookup"><span data-stu-id="3fe6b-183">For each permission, the value 1 equals True and the value 0 equals False.</span></span>

<span data-ttu-id="3fe6b-184">下表介绍了预置权限组中每个单独权限的必需顺序和值：</span><span class="sxs-lookup"><span data-stu-id="3fe6b-184">The required order and values for each individual permission in preset permission groups are described in the following table:</span></span>

****

|<span data-ttu-id="3fe6b-185">权限</span><span class="sxs-lookup"><span data-stu-id="3fe6b-185">Permission</span></span>|<span data-ttu-id="3fe6b-186">禁止访问</span><span class="sxs-lookup"><span data-stu-id="3fe6b-186">No access</span></span>|<span data-ttu-id="3fe6b-187">受限访问</span><span class="sxs-lookup"><span data-stu-id="3fe6b-187">Limited access</span></span>|<span data-ttu-id="3fe6b-188">完全访问</span><span class="sxs-lookup"><span data-stu-id="3fe6b-188">Full access</span></span>|
|---|:---:|:---:|:---:|
|<span data-ttu-id="3fe6b-189">PermissionToAllowSender</span><span class="sxs-lookup"><span data-stu-id="3fe6b-189">PermissionToAllowSender</span></span>|<span data-ttu-id="3fe6b-190">0</span><span class="sxs-lookup"><span data-stu-id="3fe6b-190">0</span></span>|<span data-ttu-id="3fe6b-191">0</span><span class="sxs-lookup"><span data-stu-id="3fe6b-191">0</span></span>|<span data-ttu-id="3fe6b-192">1 </span><span class="sxs-lookup"><span data-stu-id="3fe6b-192">1</span></span>|
|<span data-ttu-id="3fe6b-193">PermissionToBlockSender</span><span class="sxs-lookup"><span data-stu-id="3fe6b-193">PermissionToBlockSender</span></span>|<span data-ttu-id="3fe6b-194">0</span><span class="sxs-lookup"><span data-stu-id="3fe6b-194">0</span></span>|<span data-ttu-id="3fe6b-195">1 </span><span class="sxs-lookup"><span data-stu-id="3fe6b-195">1</span></span>|<span data-ttu-id="3fe6b-196">1 </span><span class="sxs-lookup"><span data-stu-id="3fe6b-196">1</span></span>|
|<span data-ttu-id="3fe6b-197">PermissionToDelete</span><span class="sxs-lookup"><span data-stu-id="3fe6b-197">PermissionToDelete</span></span>|<span data-ttu-id="3fe6b-198">0</span><span class="sxs-lookup"><span data-stu-id="3fe6b-198">0</span></span>|<span data-ttu-id="3fe6b-199">1 </span><span class="sxs-lookup"><span data-stu-id="3fe6b-199">1</span></span>|<span data-ttu-id="3fe6b-200">1 </span><span class="sxs-lookup"><span data-stu-id="3fe6b-200">1</span></span>|
|<span data-ttu-id="3fe6b-201">PermissionToDownload<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="3fe6b-201">PermissionToDownload<sup>\*</sup></span></span>|<span data-ttu-id="3fe6b-202">0</span><span class="sxs-lookup"><span data-stu-id="3fe6b-202">0</span></span>|<span data-ttu-id="3fe6b-203">0</span><span class="sxs-lookup"><span data-stu-id="3fe6b-203">0</span></span>|<span data-ttu-id="3fe6b-204">0</span><span class="sxs-lookup"><span data-stu-id="3fe6b-204">0</span></span>|
|<span data-ttu-id="3fe6b-205">PermissionToPreview</span><span class="sxs-lookup"><span data-stu-id="3fe6b-205">PermissionToPreview</span></span>|<span data-ttu-id="3fe6b-206">0</span><span class="sxs-lookup"><span data-stu-id="3fe6b-206">0</span></span>|<span data-ttu-id="3fe6b-207">1 </span><span class="sxs-lookup"><span data-stu-id="3fe6b-207">1</span></span>|<span data-ttu-id="3fe6b-208">1 </span><span class="sxs-lookup"><span data-stu-id="3fe6b-208">1</span></span>|
|<span data-ttu-id="3fe6b-209">PermissionToRelease<sup>\*\*</sup></span><span class="sxs-lookup"><span data-stu-id="3fe6b-209">PermissionToRelease<sup>\*\*</sup></span></span>|<span data-ttu-id="3fe6b-210">0</span><span class="sxs-lookup"><span data-stu-id="3fe6b-210">0</span></span>|<span data-ttu-id="3fe6b-211">0</span><span class="sxs-lookup"><span data-stu-id="3fe6b-211">0</span></span>|<span data-ttu-id="3fe6b-212">1 </span><span class="sxs-lookup"><span data-stu-id="3fe6b-212">1</span></span>|
|<span data-ttu-id="3fe6b-213">PermissionToRequestRelease<sup>\*\*</sup></span><span class="sxs-lookup"><span data-stu-id="3fe6b-213">PermissionToRequestRelease<sup>\*\*</sup></span></span>|<span data-ttu-id="3fe6b-214">0</span><span class="sxs-lookup"><span data-stu-id="3fe6b-214">0</span></span>|<span data-ttu-id="3fe6b-215">1 </span><span class="sxs-lookup"><span data-stu-id="3fe6b-215">1</span></span>|<span data-ttu-id="3fe6b-216">0</span><span class="sxs-lookup"><span data-stu-id="3fe6b-216">0</span></span>|
|<span data-ttu-id="3fe6b-217">PermissionToViewHeader<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="3fe6b-217">PermissionToViewHeader<sup>\*</sup></span></span>|<span data-ttu-id="3fe6b-218">0</span><span class="sxs-lookup"><span data-stu-id="3fe6b-218">0</span></span>|<span data-ttu-id="3fe6b-219">0</span><span class="sxs-lookup"><span data-stu-id="3fe6b-219">0</span></span>|<span data-ttu-id="3fe6b-220">0</span><span class="sxs-lookup"><span data-stu-id="3fe6b-220">0</span></span>|
|<span data-ttu-id="3fe6b-221">二进制值</span><span class="sxs-lookup"><span data-stu-id="3fe6b-221">Binary value</span></span>|<span data-ttu-id="3fe6b-222">00000000</span><span class="sxs-lookup"><span data-stu-id="3fe6b-222">00000000</span></span>|<span data-ttu-id="3fe6b-223">01101010</span><span class="sxs-lookup"><span data-stu-id="3fe6b-223">01101010</span></span>|<span data-ttu-id="3fe6b-224">11101100</span><span class="sxs-lookup"><span data-stu-id="3fe6b-224">11101100</span></span>|
|<span data-ttu-id="3fe6b-225">要使用的十进制值</span><span class="sxs-lookup"><span data-stu-id="3fe6b-225">Decimal value to use</span></span>|<span data-ttu-id="3fe6b-226">0</span><span class="sxs-lookup"><span data-stu-id="3fe6b-226">0</span></span>|<span data-ttu-id="3fe6b-227">106</span><span class="sxs-lookup"><span data-stu-id="3fe6b-227">106</span></span>|<span data-ttu-id="3fe6b-228">236</span><span class="sxs-lookup"><span data-stu-id="3fe6b-228">236</span></span>|

<span data-ttu-id="3fe6b-229"><sup>\*</sup> 目前，此值始终为0。</span><span class="sxs-lookup"><span data-stu-id="3fe6b-229"><sup>\*</sup> Currently, this value is always 0.</span></span> <span data-ttu-id="3fe6b-230">对于 PermissionToViewHeader，值0不会在隔离邮件的详细信息中隐藏 " **查看邮件标题** " 按钮 (该按钮始终) 可用。</span><span class="sxs-lookup"><span data-stu-id="3fe6b-230">For PermissionToViewHeader, the value 0 doesn't hide the **View message header** button in the details of the quarantined message (the button is always available).</span></span>

<span data-ttu-id="3fe6b-231"><sup>\*\*</sup> 请勿将这两个值都设置为1。</span><span class="sxs-lookup"><span data-stu-id="3fe6b-231"><sup>\*\*</sup> Don't set both of these values to 1.</span></span> <span data-ttu-id="3fe6b-232">将1设置为1，将另一个设置为0，或将两者都设置为0。</span><span class="sxs-lookup"><span data-stu-id="3fe6b-232">Set one to 1 and the other to 0, or set both to 0.</span></span>

<span data-ttu-id="3fe6b-233">本示例创建一个新的隔离标记名称 NoAccess，该名称分配了上表中描述的 "无访问权限"。</span><span class="sxs-lookup"><span data-stu-id="3fe6b-233">This example creates a new quarantine tag name NoAccess that assigns the No access permissions as described in the previous table.</span></span>

```powershell
New-QuarantineTag -Name NoAccess -EndUserQuarantinePermissionsValue 0
```

<span data-ttu-id="3fe6b-234">对于受限制的访问权限，请使用值106。</span><span class="sxs-lookup"><span data-stu-id="3fe6b-234">For Limited access permissions, use the value 106.</span></span> <span data-ttu-id="3fe6b-235">若要获取完全访问权限，请使用值236。</span><span class="sxs-lookup"><span data-stu-id="3fe6b-235">For Full access permissions, use the value 236.</span></span>

<span data-ttu-id="3fe6b-236">对于自定义权限，请使用上表获取与所需权限对应的二进制值。</span><span class="sxs-lookup"><span data-stu-id="3fe6b-236">For custom permissions, use the previous table to get the binary value that corresponds to the permissions you want.</span></span> <span data-ttu-id="3fe6b-237">将二进制值转换为十进制值，并使用 _EndUserQuarantinePermissionsValue_ 参数的十进制值。</span><span class="sxs-lookup"><span data-stu-id="3fe6b-237">Convert the binary value to a decimal value and use the decimal value for the _EndUserQuarantinePermissionsValue_ parameter.</span></span>

<span data-ttu-id="3fe6b-238">有关语法和参数的详细信息，请参阅 [QuarantineTag](https://docs.microsoft.com/powershell/module/exchange/new-quarantinetag)。</span><span class="sxs-lookup"><span data-stu-id="3fe6b-238">For detailed syntax and parameter information, see [New-QuarantineTag](https://docs.microsoft.com/powershell/module/exchange/new-quarantinetag).</span></span>

#### <a name="use-the-enduserquarantinepermissions-parameter"></a><span data-ttu-id="3fe6b-239">使用 EndUserQuarantinePermissions 参数</span><span class="sxs-lookup"><span data-stu-id="3fe6b-239">Use the EndUserQuarantinePermissions parameter</span></span>

<span data-ttu-id="3fe6b-240">若要使用 _EndUserQuarantinePermissionsValue_ 参数创建隔离标记，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="3fe6b-240">To create a quarantine tag using the _EndUserQuarantinePermissionsValue_ parameter, do the following steps:</span></span>

<span data-ttu-id="3fe6b-241">A.</span><span class="sxs-lookup"><span data-stu-id="3fe6b-241">A.</span></span> <span data-ttu-id="3fe6b-242">使用 **QuarantinePermissions** cmdlet 将隔离权限对象存储在变量中。</span><span class="sxs-lookup"><span data-stu-id="3fe6b-242">Store a quarantine permissions object in a variable using the **New-QuarantinePermissions** cmdlet.</span></span>
<br/>
<span data-ttu-id="3fe6b-243">B.</span><span class="sxs-lookup"><span data-stu-id="3fe6b-243">B.</span></span> <span data-ttu-id="3fe6b-244">将变量用作 **QuarantineTag** 命令中的 _EndUserQuarantinePermissions_ 值。</span><span class="sxs-lookup"><span data-stu-id="3fe6b-244">Use the variable as the _EndUserQuarantinePermissions_ value in the **New-QuarantineTag** command.</span></span>

##### <a name="step-a-store-a-quarantine-permissions-object-in-a-variable"></a><span data-ttu-id="3fe6b-245">步骤 A：将隔离权限对象存储在变量中</span><span class="sxs-lookup"><span data-stu-id="3fe6b-245">Step A: Store a quarantine permissions object in a variable</span></span>

<span data-ttu-id="3fe6b-246">使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="3fe6b-246">Use the following syntax:</span></span>

```powershell
$<VariableName> = New-QuarantinePermissions [-PermissionToAllowSender <$true | $False>] [-PermissionToBlockSender <$true | $False>] [-PermissionToDelete <$true | $False>] [-PermissionToPreview <$true | $False>] [-PermissionToRelease <$true | $False>] [-PermissionToRequestRelease <$true | $False>]
```

<span data-ttu-id="3fe6b-247">任何未使用的参数的默认值为 `$false` ，因此您只需要使用要将值设置为的参数 `$true` 。</span><span class="sxs-lookup"><span data-stu-id="3fe6b-247">The default value for any unused parameters is `$false`, so you only need to use the parameters where you want to set value to `$true`.</span></span>

<span data-ttu-id="3fe6b-248">下面的示例展示了如何创建与预置权限组对应的权限对象：</span><span class="sxs-lookup"><span data-stu-id="3fe6b-248">The following examples show how to create permission objects that correspond to the preset permissions groups:</span></span>

- <span data-ttu-id="3fe6b-249">**无访问权限**：</span><span class="sxs-lookup"><span data-stu-id="3fe6b-249">**No access**:</span></span>

  ```powershell
  $NoAccess = New-QuarantinePermissions
  ```

- <span data-ttu-id="3fe6b-250">**受限访问**：</span><span class="sxs-lookup"><span data-stu-id="3fe6b-250">**Limited access**:</span></span>

  ```powershell
  $LimitedAccess = New-QuarantinePermissions -PermissionToBlockSender $true -PermissionToDelete $true -PermissionToPreview $true -PermissionToRequestRelease $true
  ```

- <span data-ttu-id="3fe6b-251">**完全访问**：</span><span class="sxs-lookup"><span data-stu-id="3fe6b-251">**Full access**:</span></span>

  ```powershell
  $FullAccess = New-QuarantinePermissions -PermissionToAllowSender $true -PermissionToBlockSender $true -PermissionToDelete $true -PermissionToPreview $true -PermissionToRelease $true
  ```

<span data-ttu-id="3fe6b-252">若要查看已设置的值，请将变量名称作为命令运行 (例如，运行命令 `$NoAccess`) 。</span><span class="sxs-lookup"><span data-stu-id="3fe6b-252">To see the values that you've set, run the variable name as a command (for example, run the command `$NoAccess`).</span></span>

<span data-ttu-id="3fe6b-253">对于自定义权限，请勿将 _PermissionToRelease_ 和 _PermissionToRequestRelease_ 参数都设置为 `$true` 。</span><span class="sxs-lookup"><span data-stu-id="3fe6b-253">For custom permissions, don't set both the _PermissionToRelease_ and _PermissionToRequestRelease_ parameters to `$true`.</span></span> <span data-ttu-id="3fe6b-254">将一个设置为，将另一个设置为 `$true` `$false` ，或将两者都保留 `$false` 。</span><span class="sxs-lookup"><span data-stu-id="3fe6b-254">Set one to `$true` and leave the other as `$false`, or leave both as `$false`.</span></span>

<span data-ttu-id="3fe6b-255">您还可以在创建现有的权限对象变量之后，在使用 **QuarantinePermissions** cmdlet 之前对其进行修改。</span><span class="sxs-lookup"><span data-stu-id="3fe6b-255">You can also modify an existing permissions object variable after you create but before you use it by using the **Set-QuarantinePermissions** cmdlet.</span></span>

<span data-ttu-id="3fe6b-256">有关语法和参数的详细信息，请参阅 [QuarantinePermissions](https://docs.microsoft.com/powershell/module/exchange/new-quarantinepermissions) 和 [QuarantinePermissions](https://docs.microsoft.com/powershell/module/exchange/set-quarantinepermissions)。</span><span class="sxs-lookup"><span data-stu-id="3fe6b-256">For detailed syntax and parameter information, see [New-QuarantinePermissions](https://docs.microsoft.com/powershell/module/exchange/new-quarantinepermissions) and [Set-QuarantinePermissions](https://docs.microsoft.com/powershell/module/exchange/set-quarantinepermissions).</span></span>

##### <a name="step-b-use-the-variable-in-the-new-quarantinetag-command"></a><span data-ttu-id="3fe6b-257">步骤 B：在 New-QuarantineTag 命令中使用变量</span><span class="sxs-lookup"><span data-stu-id="3fe6b-257">Step B: Use the variable in the New-QuarantineTag command</span></span>

<span data-ttu-id="3fe6b-258">在变量中创建并存储了权限对象后，在下面的 **QuarantineTag** 命令中使用 _EndUserQuarantinePermission_ 参数值的变量：</span><span class="sxs-lookup"><span data-stu-id="3fe6b-258">After you've created and stored the permissions object in a variable, use the variable for the _EndUserQuarantinePermission_ parameter value in the following **New-QuarantineTag** command:</span></span>

```powershell
New-QuarantineTag -Name "<UniqueName>" -EndUserQuarantinePermissions $<VariableName>
```

<span data-ttu-id="3fe6b-259">本示例使用 `$LimitedAccess` 在上一步中描述和创建的权限对象创建一个名为 LimitedAccess 的新的隔离标记。</span><span class="sxs-lookup"><span data-stu-id="3fe6b-259">This example creates a new quarantine tag named LimitedAccess using the `$LimitedAccess` permissions object that was described and created in the previous step.</span></span>

```powershell
New-QuarantineTag -Name LimitedAccess -EndUserQuarantinePermissions $LimitedAccess
```

<span data-ttu-id="3fe6b-260">有关语法和参数的详细信息，请参阅 [QuarantineTag](https://docs.microsoft.com/powershell/module/exchange/new-quarantinetag)。</span><span class="sxs-lookup"><span data-stu-id="3fe6b-260">For detailed syntax and parameter information, see [New-QuarantineTag](https://docs.microsoft.com/powershell/module/exchange/new-quarantinetag).</span></span>

## <a name="step-2-assign-a-quarantine-tag-to-supported-features"></a><span data-ttu-id="3fe6b-261">步骤2：将隔离标记分配给支持的功能</span><span class="sxs-lookup"><span data-stu-id="3fe6b-261">Step 2: Assign a quarantine tag to supported features</span></span>

<span data-ttu-id="3fe6b-262">在 (自动或作为可配置动作) 隔离邮件或文件的 _受支持_ 的保护功能中，可以为可用的隔离操作分配隔离标记。</span><span class="sxs-lookup"><span data-stu-id="3fe6b-262">In _supported_ protection features that quarantine messages or files (automatically or as a configurable action), you can assign a quarantine tag to the available quarantine actions.</span></span> <span data-ttu-id="3fe6b-263">下表介绍了隔离邮件的功能和隔离标记的可用性：</span><span class="sxs-lookup"><span data-stu-id="3fe6b-263">Features that quarantine messages and the availability of quarantine tags are described in the following table:</span></span>

****

|<span data-ttu-id="3fe6b-264">功能</span><span class="sxs-lookup"><span data-stu-id="3fe6b-264">Feature</span></span>|<span data-ttu-id="3fe6b-265">是否支持隔离标记？</span><span class="sxs-lookup"><span data-stu-id="3fe6b-265">Quarantine tags supported?</span></span>|<span data-ttu-id="3fe6b-266">使用的默认隔离标记</span><span class="sxs-lookup"><span data-stu-id="3fe6b-266">Default quarantine tags used</span></span>|
|---|:---:|---|
|<span data-ttu-id="3fe6b-267">[反垃圾邮件策略](configure-your-spam-filter-policies.md)：</span><span class="sxs-lookup"><span data-stu-id="3fe6b-267">[Anti-spam policies](configure-your-spam-filter-policies.md):</span></span> <ul><li><span data-ttu-id="3fe6b-268">**垃圾邮件** (_SpamAction_) </span><span class="sxs-lookup"><span data-stu-id="3fe6b-268">**Spam** (_SpamAction_)</span></span></li><li><span data-ttu-id="3fe6b-269">**高可信度垃圾邮件** (_HighConfidenceSpamAction_) </span><span class="sxs-lookup"><span data-stu-id="3fe6b-269">**High confidence spam** (_HighConfidenceSpamAction_)</span></span></li><li><span data-ttu-id="3fe6b-270">**网络钓鱼电子邮件** (_PhishSpamAction_) </span><span class="sxs-lookup"><span data-stu-id="3fe6b-270">**Phishing email** (_PhishSpamAction_)</span></span></li><li><span data-ttu-id="3fe6b-271">**高可信度网络钓鱼电子邮件** (_HighConfidencePhishAction_) </span><span class="sxs-lookup"><span data-stu-id="3fe6b-271">**High confidence phishing email** (_HighConfidencePhishAction_)</span></span></li><li><span data-ttu-id="3fe6b-272">**批量电子邮件** (_BulkSpamAction_) </span><span class="sxs-lookup"><span data-stu-id="3fe6b-272">**Bulk email** (_BulkSpamAction_)</span></span></li></ul>|<span data-ttu-id="3fe6b-273">是</span><span class="sxs-lookup"><span data-stu-id="3fe6b-273">Yes</span></span>|<ul><li><span data-ttu-id="3fe6b-274">DefaultSpamTag (完全访问) </span><span class="sxs-lookup"><span data-stu-id="3fe6b-274">DefaultSpamTag (Full access)</span></span></li><li><span data-ttu-id="3fe6b-275">DefaultHighConfSpamTag (完全访问) </span><span class="sxs-lookup"><span data-stu-id="3fe6b-275">DefaultHighConfSpamTag (Full access)</span></span></li><li><span data-ttu-id="3fe6b-276">DefaultPhishTag (完全访问) </span><span class="sxs-lookup"><span data-stu-id="3fe6b-276">DefaultPhishTag (Full access)</span></span></li><li><span data-ttu-id="3fe6b-277">DefaultHighConfPhishTag (无访问权限) </span><span class="sxs-lookup"><span data-stu-id="3fe6b-277">DefaultHighConfPhishTag (No access)</span></span></li><li><span data-ttu-id="3fe6b-278">DefaultBulkTag (完全访问) </span><span class="sxs-lookup"><span data-stu-id="3fe6b-278">DefaultBulkTag (Full access)</span></span></li></ul>
|<span data-ttu-id="3fe6b-279">反网络钓鱼策略：</span><span class="sxs-lookup"><span data-stu-id="3fe6b-279">Anti-phishing policies:</span></span> <ul><li><span data-ttu-id="3fe6b-280"> (_AuthenticationFailAction_) 的 [欺骗性智能保护](set-up-anti-phishing-policies.md#spoof-settings)</span><span class="sxs-lookup"><span data-stu-id="3fe6b-280">[Spoof intelligence protection](set-up-anti-phishing-policies.md#spoof-settings) (_AuthenticationFailAction_)</span></span></li><li><span data-ttu-id="3fe6b-281">[模拟保护](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)：<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="3fe6b-281">[Impersonation protection](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365):<sup>\*</sup></span></span> <ul><li><span data-ttu-id="3fe6b-282">**如果模拟用户发送电子邮件** (_TargetedUserProtectionAction_) </span><span class="sxs-lookup"><span data-stu-id="3fe6b-282">**If email is sent by an impersonated user** (_TargetedUserProtectionAction_)</span></span></li><li><span data-ttu-id="3fe6b-283">**如果由模拟域发送的电子邮件** (_TargetedDomainProtectionAction_) </span><span class="sxs-lookup"><span data-stu-id="3fe6b-283">**If email is sent by an impersonated domain** (_TargetedDomainProtectionAction_)</span></span></li><li><span data-ttu-id="3fe6b-284">**邮箱智能** \>**如果模拟用户发送电子邮件** (_MailboxIntelligenceProtectionAction_) </span><span class="sxs-lookup"><span data-stu-id="3fe6b-284">**Mailbox intelligence** \> **If email is sent by an impersonated user** (_MailboxIntelligenceProtectionAction_)</span></span></li></ul></li></ul></ul>|<span data-ttu-id="3fe6b-285">否</span><span class="sxs-lookup"><span data-stu-id="3fe6b-285">No</span></span>|<span data-ttu-id="3fe6b-286">不适用</span><span class="sxs-lookup"><span data-stu-id="3fe6b-286">n/a</span></span>|
|<span data-ttu-id="3fe6b-287">[反恶意软件策略](configure-anti-malware-policies.md)：始终隔离所有检测到的邮件。</span><span class="sxs-lookup"><span data-stu-id="3fe6b-287">[Anti-malware policies](configure-anti-malware-policies.md): All detected messages are always quarantined.</span></span>|<span data-ttu-id="3fe6b-288">否</span><span class="sxs-lookup"><span data-stu-id="3fe6b-288">No</span></span>|<span data-ttu-id="3fe6b-289">不适用</span><span class="sxs-lookup"><span data-stu-id="3fe6b-289">n/a</span></span>|
|[<span data-ttu-id="3fe6b-290">适用于 SharePoint、OneDrive 和 Microsoft Teams 的 ATP</span><span class="sxs-lookup"><span data-stu-id="3fe6b-290">ATP for SharePoint, OneDrive, and Microsoft Teams</span></span>](atp-for-spo-odb-and-teams.md)|<span data-ttu-id="3fe6b-291">否</span><span class="sxs-lookup"><span data-stu-id="3fe6b-291">No</span></span>|<span data-ttu-id="3fe6b-292">不适用</span><span class="sxs-lookup"><span data-stu-id="3fe6b-292">n/a</span></span>|
|<span data-ttu-id="3fe6b-293">[邮件流规则](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (也称为传输规则) 与操作：将 **邮件传递到托管隔离** (_隔离_) 。</span><span class="sxs-lookup"><span data-stu-id="3fe6b-293">[Mail flow rules](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (also known as transport rules) with the action: **Deliver the message to the hosted quarantine** (_Quarantine_).</span></span>|<span data-ttu-id="3fe6b-294">否</span><span class="sxs-lookup"><span data-stu-id="3fe6b-294">No</span></span>|<span data-ttu-id="3fe6b-295">不适用</span><span class="sxs-lookup"><span data-stu-id="3fe6b-295">n/a</span></span>|
|

<span data-ttu-id="3fe6b-296"><sup>\*</sup> 模拟保护设置仅适用于 Microsoft Defender for Office 365 中的反网络钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="3fe6b-296"><sup>\*</sup> Impersonation protection settings are available only in anti-phishing policies in Microsoft Defender for Office 365.</span></span>

<span data-ttu-id="3fe6b-297">如果你对由默认隔离标记提供的最终用户权限感到满意，则无需执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="3fe6b-297">If you're happy with the end-user permissions that are provided by the default quarantine tags, you don't need to do anything.</span></span> <span data-ttu-id="3fe6b-298">如果要自定义最终用户功能 (可用按钮) 在最终用户垃圾邮件通知或隔离邮件的详细信息中，则可以分配自定义隔离标记。</span><span class="sxs-lookup"><span data-stu-id="3fe6b-298">If you want to customize the end-user capabilities (available buttons) in end-user spam notifications or in quarantined message details, you can assign a custom quarantine tag.</span></span>

### <a name="assign-quarantine-tags-in-anti-spam-policies-in-the-security--compliance-center"></a><span data-ttu-id="3fe6b-299">在安全 & 合规性中心中的反垃圾邮件策略中分配隔离标记</span><span class="sxs-lookup"><span data-stu-id="3fe6b-299">Assign quarantine tags in anti-spam policies in the Security & Compliance Center</span></span>

<span data-ttu-id="3fe6b-300">有关创建和修改反垃圾邮件策略的完整说明，请参阅在 [EOP 中配置反垃圾邮件策略](configure-your-spam-filter-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="3fe6b-300">Full instructions for creating and modifying anti-spam policies are described in [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

1. <span data-ttu-id="3fe6b-301">在安全 & 合规性中心中，转到 " **威胁管理** \> **策略**"， \> 然后选择 " **反垃圾邮件**"。</span><span class="sxs-lookup"><span data-stu-id="3fe6b-301">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> and then select **Anti-spam**.</span></span> <span data-ttu-id="3fe6b-302">或者，打开 <https://protection.office.com/antispam> 。</span><span class="sxs-lookup"><span data-stu-id="3fe6b-302">Or, open <https://protection.office.com/antispam>.</span></span>

2. <span data-ttu-id="3fe6b-303">查找并选择要编辑的现有反垃圾邮件策略，或创建新的反垃圾邮件策略。</span><span class="sxs-lookup"><span data-stu-id="3fe6b-303">Find and select an existing anti-spam policy to edit, or create a new anti-spam policy.</span></span>

3. <span data-ttu-id="3fe6b-304">在 "策略详细信息" 浮出控件中，展开 " **垃圾邮件和批量操作** " 部分。</span><span class="sxs-lookup"><span data-stu-id="3fe6b-304">In the policy details flyout, expand the **Spam and bulk actions** section.</span></span>
  
4. <span data-ttu-id="3fe6b-305">如果已为可用垃圾邮件筛选判定的操作选择了 " **隔离邮件** "，则可以使用 " **应用隔离策略标记** " 框来选择该判定的隔离标记。</span><span class="sxs-lookup"><span data-stu-id="3fe6b-305">If you've selected **Quarantine message** for the action of an available spam filtering verdict, the **Apply quarantine policy tag** box is available for you to select the quarantine tag for that verdict.</span></span>

   <span data-ttu-id="3fe6b-306">**注意**：创建新策略时，垃圾邮件筛选判定的空隔离标记值表示使用该判定的默认隔离标记。</span><span class="sxs-lookup"><span data-stu-id="3fe6b-306">**Note**: When you create a new policy, a blank quarantine tag value for a spam filtering verdict indicates the default quarantine tag for that verdict is used.</span></span> <span data-ttu-id="3fe6b-307">当您随后编辑策略时，空值将被实际的默认隔离标记名称替换，如上表中所述。</span><span class="sxs-lookup"><span data-stu-id="3fe6b-307">When you later edit the policy, the blank values are replaced by the actual default quarantine tag names as described in the previous table.</span></span>
  
   ![反垃圾邮件策略中的隔离标记选择](../../media/quarantine-tags-in-anti-spam-policies.png)

5. <span data-ttu-id="3fe6b-309">完成时，请单击“保存”。</span><span class="sxs-lookup"><span data-stu-id="3fe6b-309">When you're finished, click **Save**.</span></span>

#### <a name="assign-quarantine-tags-in-anti-spam-policies-in-powershell"></a><span data-ttu-id="3fe6b-310">在 PowerShell 中的反垃圾邮件策略中分配隔离标记</span><span class="sxs-lookup"><span data-stu-id="3fe6b-310">Assign quarantine tags in anti-spam policies in PowerShell</span></span>

<span data-ttu-id="3fe6b-311">如果您希望使用 PowerShell 在反垃圾邮件策略中分配隔离标记，请连接到 Exchange Online PowerShell 或 Exchange Online Protection PowerShell，并使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="3fe6b-311">If you'd rather use PowerShell to assign quarantine tags in anti-spam policies, connect to Exchange Online PowerShell or Exchange Online Protection PowerShell and use the following syntax:</span></span>

```powershell
<New-HostedContentFilterPolicy -Name "<Unique name>" | Set-HostedContentFilterPolicy -Identity "<Policy name>">  [-SpamAction Quarantine] [-SpamQuarantineTag <QuarantineTagName>] [-HighConfidenceSpamAction Quarantine] [-HighConfidenceSpamQuarantineTag <QuarantineTagName>] [-PhishSpamAction Quarantine] [-PhishQuarantineTag <QuarantineTagName>] [-HighConfidencePhishQuarantineTag <QuarantineTagName>] [-BulkSpamAction Quarantine] [-BulkQuarantineTag <QuarantineTagName>] ...
```

<span data-ttu-id="3fe6b-312">**注意**：</span><span class="sxs-lookup"><span data-stu-id="3fe6b-312">**Notes**:</span></span>

- <span data-ttu-id="3fe6b-313">_HighConfidencePhishAction_ 参数的默认值为 "隔离"，因此您无需为新的反垃圾邮件策略中的高可信度网络钓鱼检测设置隔离操作。</span><span class="sxs-lookup"><span data-stu-id="3fe6b-313">The default value for the _HighConfidencePhishAction_ parameter is Quarantine, so you don't need to set the Quarantine action for high confidence phishing detections in new anti-spam policies.</span></span> <span data-ttu-id="3fe6b-314">对于新的或现有的反垃圾邮件策略中的所有其他垃圾邮件筛选 verdicts，只有在 action 值为 "隔离" 的情况下，隔离标记才有效。</span><span class="sxs-lookup"><span data-stu-id="3fe6b-314">For all other spam filtering verdicts in new or existing anti-spam policies, the quarantine tag is only effective if the action value is Quarantine.</span></span> <span data-ttu-id="3fe6b-315">若要查看现有反垃圾邮件策略中的操作值，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="3fe6b-315">To see the action values in existing anti-spam policies, run the following command:</span></span>

  ```powershell
  Get-HostedContentFilterPolicy | Format-Table Name,*SpamAction,HighConfidencePhishAction
  ```

  <span data-ttu-id="3fe6b-316">有关默认操作值以及标准和严格的建议操作值的信息，请参阅 [EOP 反垃圾邮件策略设置](recommended-settings-for-eop-and-office365-atp.md#eop-anti-spam-policy-settings)。</span><span class="sxs-lookup"><span data-stu-id="3fe6b-316">For information about the default action values and the recommended action values for Standard and Strict, see [EOP anti-spam policy settings](recommended-settings-for-eop-and-office365-atp.md#eop-anti-spam-policy-settings).</span></span>

- <span data-ttu-id="3fe6b-317">垃圾邮件筛选判定如果没有对应的隔离标记参数，则表示已使用该结论的 [默认隔离标记](#step-2-assign-a-quarantine-tag-to-supported-features) 。</span><span class="sxs-lookup"><span data-stu-id="3fe6b-317">A spam filtering verdict without a corresponding quarantine tag parameter means the [default quarantine tag](#step-2-assign-a-quarantine-tag-to-supported-features) for that verdict is used.</span></span>

  <span data-ttu-id="3fe6b-318">如果要更改隔离邮件的默认最终用户功能，则只需将默认的隔离标记替换为自定义隔离标记。</span><span class="sxs-lookup"><span data-stu-id="3fe6b-318">You only need to replace a default quarantine tag with a custom quarantine tag if you want to change the default end-user capabilities on quarantined messages.</span></span>

- <span data-ttu-id="3fe6b-319">PowerShell 中的新反垃圾邮件策略要求使用 **set-hostedcontentfilterpolicy** cmdlet 的垃圾邮件筛选器策略 (设置) 使用 **disable-hostedcontentfilterrule** cmdlet) 收件人筛选器使用新的垃圾邮件筛选规则 (收件人筛选器。</span><span class="sxs-lookup"><span data-stu-id="3fe6b-319">A new anti-spam policy in PowerShell requires a spam filter policy (settings) using the **New-HostedContentFilterPolicy** cmdlet and a new spam filter rule (recipient filters) using the **New-HostedContentFilterRule** cmdlet.</span></span> <span data-ttu-id="3fe6b-320">有关说明，请参阅 [使用 PowerShell 创建反垃圾邮件策略](configure-your-spam-filter-policies.md#use-powershell-to-create-anti-spam-policies)。</span><span class="sxs-lookup"><span data-stu-id="3fe6b-320">For instructions, see [Use PowerShell to create anti-spam policies](configure-your-spam-filter-policies.md#use-powershell-to-create-anti-spam-policies).</span></span>

<span data-ttu-id="3fe6b-321">本示例使用以下设置创建名为 "研究部门" 的新垃圾邮件筛选器策略：</span><span class="sxs-lookup"><span data-stu-id="3fe6b-321">This example creates a new spam filter policy named Research Department with the following settings:</span></span>

- <span data-ttu-id="3fe6b-322">所有垃圾邮件筛选 verdicts 的操作都设置为 "隔离"。</span><span class="sxs-lookup"><span data-stu-id="3fe6b-322">The action for all spam filtering verdicts is set to Quarantine.</span></span>
- <span data-ttu-id="3fe6b-323">名为 NoAccess 的自定义隔离标记（分配 **无访问** 权限）将替换默认情况下尚未分配 " **无访问** 权限" 的任何默认隔离标记。</span><span class="sxs-lookup"><span data-stu-id="3fe6b-323">The custom quarantine tag named NoAccess that assigns **No access** permissions replaces any default quarantine tags that don't already assign **No access** permissions by default.</span></span>

```powershell
New-HostedContentFilterPolicy -Name Research Department -SpamAction Quarantine -SpamQuarantineTag NoAccess -HighConfidenceSpamAction Quarantine -HighConfidenceSpamQuarantineTag NoAction -PhishSpamAction Quarantine -PhishQuarantineTag NoAction -BulkSpamAction Quarantine -BulkQuarantineTag NoAccess
```

<span data-ttu-id="3fe6b-324">若要详细了解语法和参数，请参阅 [New-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/new-hostedcontentfilterpolicy)。</span><span class="sxs-lookup"><span data-stu-id="3fe6b-324">For detailed syntax and parameter information, see [New-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/new-hostedcontentfilterpolicy).</span></span>

<span data-ttu-id="3fe6b-325">本示例修改名为 "人力资源" 的现有垃圾邮件筛选器策略。</span><span class="sxs-lookup"><span data-stu-id="3fe6b-325">This example modifies the existing spam filter policy named Human Resources.</span></span> <span data-ttu-id="3fe6b-326">垃圾邮件隔离判定的操作将设置为 "隔离"，并分配名为 "NoAccess" 的自定义隔离标记。</span><span class="sxs-lookup"><span data-stu-id="3fe6b-326">The action for the spam quarantine verdict is set to Quarantine, and the custom quarantine tag named NoAccess is assigned.</span></span>

```powershell
Set-HostedContentFilterPolicy -Identity "Human Resources" -SpamAction Quarantine -SpamQuarantineTag NoAccess
```

<span data-ttu-id="3fe6b-327">若要详细了解语法和参数，请参阅 [Set-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/set-hostedcontentfilterpolicy)。</span><span class="sxs-lookup"><span data-stu-id="3fe6b-327">For detailed syntax and parameter information, see [Set-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/set-hostedcontentfilterpolicy).</span></span>

## <a name="configure-global-quarantine-notification-settings-in-the-security--compliance-center"></a><span data-ttu-id="3fe6b-328">在安全 & 合规中心中配置全局隔离通知设置</span><span class="sxs-lookup"><span data-stu-id="3fe6b-328">Configure global quarantine notification settings in the Security & Compliance Center</span></span>

<span data-ttu-id="3fe6b-329">通过 "隔离标记的全局设置"，可以自定义向已隔离邮件的收件人发送的最终用户垃圾邮件通知。</span><span class="sxs-lookup"><span data-stu-id="3fe6b-329">The global settings for quarantine tags allow you to customize the end-user spam notifications that are sent to recipients of messages that were quarantined.</span></span> <span data-ttu-id="3fe6b-330">有关这些通知的详细信息，请参阅 [最终用户垃圾邮件通知](use-spam-notifications-to-release-and-report-quarantined-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="3fe6b-330">For more information about these notifications, see [End-user spam notifications](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span></span>

1. <span data-ttu-id="3fe6b-331">在安全 & 合规性中心中，转到 " **威胁管理** \> **策略** "，然后选择 " **隔离标记**"。</span><span class="sxs-lookup"><span data-stu-id="3fe6b-331">In the Security & Compliance Center, go to **Threat management** \> **Policy** and then select **Quarantine tags**.</span></span>

2. <span data-ttu-id="3fe6b-332">在 " **隔离标记** " 页上，选择 " **全局设置**"。</span><span class="sxs-lookup"><span data-stu-id="3fe6b-332">On the **Quarantine tags** page, select **Global settings**.</span></span>

3. <span data-ttu-id="3fe6b-333">在打开的 " **隔离通知设置** " 浮出控件中，配置以下部分或所有设置：</span><span class="sxs-lookup"><span data-stu-id="3fe6b-333">In the **Quarantine notification settings** flyout that opens, configure some or all of the following settings:</span></span>

   - <span data-ttu-id="3fe6b-334">**使用 "我的公司徽标**"：选择此选项可替换最终用户垃圾邮件通知顶部使用的默认 Microsoft 徽标。</span><span class="sxs-lookup"><span data-stu-id="3fe6b-334">**Use my company logo**: Select this option to replace the default Microsoft logo that's use at the top of end-user spam notifications.</span></span> <span data-ttu-id="3fe6b-335">在执行此操作之前，您需要按照 [自定义您的组织的 Microsoft 365 主题](https://docs.microsoft.com/microsoft-365/admin/setup/customize-your-organization-theme) 中的说明上传您的自定义徽标。</span><span class="sxs-lookup"><span data-stu-id="3fe6b-335">Before you do this, you need to follow the instructions in [Customize the Microsoft 365 theme for your organization](https://docs.microsoft.com/microsoft-365/admin/setup/customize-your-organization-theme) to upload your custom logo.</span></span>

     <span data-ttu-id="3fe6b-336">下面的屏幕截图显示最终用户垃圾邮件通知中的自定义徽标：</span><span class="sxs-lookup"><span data-stu-id="3fe6b-336">The following screenshot shows a custom logo in an end-user spam notification:</span></span>

     ![最终用户垃圾邮件通知中的自定义徽标](../../media/quarantine-tags-esn-customization-logo.png)

   - <span data-ttu-id="3fe6b-338">**选择语言**：最终用户垃圾邮件通知已根据收件人的语言设置进行本地化。</span><span class="sxs-lookup"><span data-stu-id="3fe6b-338">**Choose language**: End-user spam notifications are already localized based on the recipient's language settings.</span></span> <span data-ttu-id="3fe6b-339">您可以为 **显示名称** 和 **免责声明** 值指定不同语言的自定义文本。</span><span class="sxs-lookup"><span data-stu-id="3fe6b-339">You can specify customized text in different languages for the **Display name** and **Disclaimer** values.</span></span>

     <span data-ttu-id="3fe6b-340">从 "第一种语言" 框中选择至少一种语言，然后单击 " **添加**"。</span><span class="sxs-lookup"><span data-stu-id="3fe6b-340">Select at least one language from the first language box and then click **Add**.</span></span> <span data-ttu-id="3fe6b-341">您可以通过在每个语言后面单击 " **添加** " 来选择多种语言。</span><span class="sxs-lookup"><span data-stu-id="3fe6b-341">You can select multiple languages by clicking **Add** after each one.</span></span> <span data-ttu-id="3fe6b-342">"部分语言" 框显示已选择的所有语言：</span><span class="sxs-lookup"><span data-stu-id="3fe6b-342">A section language box shows all of the languages that you've selected:</span></span>

     ![隔离标记全局隔离通知设置中的第二个语言框中的选定语言](../../media/quarantine-tags-esn-customization-selected-languages.png)

   - <span data-ttu-id="3fe6b-344">**显示名称**：自定义在最终用户垃圾邮件通知中使用的发件人的显示名称。</span><span class="sxs-lookup"><span data-stu-id="3fe6b-344">**Display name**: Customize the sender's display name that's used in end-user spam notifications.</span></span>

     <span data-ttu-id="3fe6b-345">对于已添加的每种语言，在 "第二语言" 框中选择语言 (不单击 X) 并在 " **显示名称** " 框中输入所需的文本值。</span><span class="sxs-lookup"><span data-stu-id="3fe6b-345">For each language that you've added, select the language in the second language box (don't click on the X) and enter the text value you want in the **Display name** box.</span></span>

     <span data-ttu-id="3fe6b-346">下面的屏幕截图显示最终用户垃圾邮件通知中自定义的显示名称：</span><span class="sxs-lookup"><span data-stu-id="3fe6b-346">The following screenshot shows the customized display name in an end-user spam notification:</span></span>

     ![最终用户垃圾邮件通知中的自定义发件人显示名称](../../media/quarantine-tags-esn-customization-display-name.png)

   - <span data-ttu-id="3fe6b-348">**免责声明**：将自定义免责声明添加到最终用户垃圾邮件通知的底部。</span><span class="sxs-lookup"><span data-stu-id="3fe6b-348">**Disclaimer**: Add a custom disclaimer to the bottom of end-user spam notifications.</span></span> <span data-ttu-id="3fe6b-349">本地化后的文本、 **组织中的免责声明：** 总是首先包括您指定的文本。</span><span class="sxs-lookup"><span data-stu-id="3fe6b-349">The localized text, **A disclaimer from your organization:** is always included first, followed by the text you specify.</span></span>

     <span data-ttu-id="3fe6b-350">对于已添加的每种语言，在 "第二语言" 框中选择语言 (不单击 X) 并在 " **免责声明** " 框中输入所需的文本值。</span><span class="sxs-lookup"><span data-stu-id="3fe6b-350">For each language that you've added, select the language in the second language box  (don't click the X) and enter the text value you want in the **Disclaimer** box.</span></span>

     <span data-ttu-id="3fe6b-351">下面的屏幕截图显示最终用户垃圾邮件通知中的自定义免责声明：</span><span class="sxs-lookup"><span data-stu-id="3fe6b-351">The following screenshot shows the customized disclaimer in an end-user spam notification:</span></span>

     ![最终用户垃圾邮件通知底部的自定义免责声明](../../media/quarantine-tags-esn-customization-disclaimer.png)

## <a name="view-quarantine-tags-in-the-security--compliance-center"></a><span data-ttu-id="3fe6b-353">查看安全 & 合规中心内的隔离标记</span><span class="sxs-lookup"><span data-stu-id="3fe6b-353">View quarantine tags in the Security & Compliance Center</span></span>

1. <span data-ttu-id="3fe6b-354">在安全 & 合规性中心中，转到 " **威胁管理** \> **策略** "，然后选择 " **隔离标记**"。</span><span class="sxs-lookup"><span data-stu-id="3fe6b-354">In the Security & Compliance Center, go to **Threat management** \> **Policy** and then select **Quarantine tags**.</span></span>

- <span data-ttu-id="3fe6b-355">若要查看内置或自定义隔离标记的设置，请从列表中选择隔离标记 (不要选中该复选框) 。</span><span class="sxs-lookup"><span data-stu-id="3fe6b-355">To view the settings of built-in or custom quarantine tags, select the quarantine tag from the list (don't select the check box).</span></span>

- <span data-ttu-id="3fe6b-356">若要查看全局设置，请选择 "**全局设置**"</span><span class="sxs-lookup"><span data-stu-id="3fe6b-356">To view the global settings, select **Global settings**</span></span>

### <a name="view-quarantine-tags-in-powershell"></a><span data-ttu-id="3fe6b-357">查看 PowerShell 中的隔离标记</span><span class="sxs-lookup"><span data-stu-id="3fe6b-357">View quarantine tags in PowerShell</span></span>

<span data-ttu-id="3fe6b-358">如果您希望使用 PowerShell 查看隔离标记，请执行以下任一步骤：</span><span class="sxs-lookup"><span data-stu-id="3fe6b-358">If you'd rather use PowerShell to view quarantine tags, do any of the following steps:</span></span>

- <span data-ttu-id="3fe6b-359">若要查看所有内置或自定义标记的摘要列表，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="3fe6b-359">To view a summary list of all built-in or custom tags, run the following command:</span></span>

  ```powershell
  Get-QuarantineTag | Format-Table Name
  ```

- <span data-ttu-id="3fe6b-360">若要查看内置或自定义隔离标记的设置，请将替换 \<TagName\> 为隔离标记的名称，然后运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="3fe6b-360">To view the settings of built-in or custom quarantine tags, replace \<TagName\> with the name of the quarantine tag, and run the following command:</span></span>

  ```powershell
  Get-QuarantineTag -Identity "<TagName>"
  ```

- <span data-ttu-id="3fe6b-361">若要查看全局设置，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="3fe6b-361">To view the global settings, run the following command:</span></span>

  ```powershell
  Get-QuarantineTag -QuarantineTagType GlobalQuarantineTag
  ```

<span data-ttu-id="3fe6b-362">若要详细了解语法和参数，请参阅 [Get-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/get-hostedcontentfilterpolicy)。</span><span class="sxs-lookup"><span data-stu-id="3fe6b-362">For detailed syntax and parameter information, see [Get-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/get-hostedcontentfilterpolicy).</span></span>

## <a name="remove-quarantine-tags-in-the-security--compliance-center"></a><span data-ttu-id="3fe6b-363">在安全 & 合规中心中删除隔离标记</span><span class="sxs-lookup"><span data-stu-id="3fe6b-363">Remove quarantine tags in the Security & Compliance Center</span></span>

<span data-ttu-id="3fe6b-364">**注意**：</span><span class="sxs-lookup"><span data-stu-id="3fe6b-364">**Notes**:</span></span>

- <span data-ttu-id="3fe6b-365">无法删除内置隔离标记。</span><span class="sxs-lookup"><span data-stu-id="3fe6b-365">You can't remove built-in quarantine tags.</span></span>

- <span data-ttu-id="3fe6b-366">在删除自定义隔离标记之前，请确认未使用该标记。</span><span class="sxs-lookup"><span data-stu-id="3fe6b-366">Before you remove a custom quarantine tag, verify that it's not being used.</span></span> <span data-ttu-id="3fe6b-367">例如，在 PowerShell 中运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="3fe6b-367">For example, run the following command in PowerShell:</span></span>

  ```powershell
  Get-HostedContentFilterPolicy | Format-List Name,*QuarantineTag
  ```

  <span data-ttu-id="3fe6b-368">如果正在使用隔离标记，则在删除之前 [将其替换为已分配的隔离标记](#step-2-assign-a-quarantine-tag-to-supported-features) 。</span><span class="sxs-lookup"><span data-stu-id="3fe6b-368">If the quarantine tag is being used, [replace the assigned quarantine tag](#step-2-assign-a-quarantine-tag-to-supported-features) before you remove it.</span></span>

1. <span data-ttu-id="3fe6b-369">在安全 & 合规性中心中，转到 " **威胁管理** \> **策略** "，然后选择 " **隔离标记**"。</span><span class="sxs-lookup"><span data-stu-id="3fe6b-369">In the Security & Compliance Center, go to **Threat management** \> **Policy** and then select **Quarantine tags**.</span></span>

2. <span data-ttu-id="3fe6b-370">在 " **隔离标记** " 页上，选择要删除的自定义隔离标记，然后单击 " **删除标记**"。</span><span class="sxs-lookup"><span data-stu-id="3fe6b-370">On the **Quarantine tags** page, select the custom quarantine tag that you want to remove, and the click **Delete tag**.</span></span>

3. <span data-ttu-id="3fe6b-371">在出现的确认对话框中，单击 " **删除标记** "。</span><span class="sxs-lookup"><span data-stu-id="3fe6b-371">Click **Remove tag** in the confirmation dialog that appears.</span></span>

### <a name="remove-quarantine-tags-in-powershell"></a><span data-ttu-id="3fe6b-372">删除 PowerShell 中的隔离标记</span><span class="sxs-lookup"><span data-stu-id="3fe6b-372">Remove quarantine tags in PowerShell</span></span>

<span data-ttu-id="3fe6b-373">如果您希望使用 PowerShell 删除自定义隔离标记，请将 \<TagName\> 其替换为隔离标记的名称，然后运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="3fe6b-373">If you'd rather use PowerShell to remove a custom quarantine tag, replace \<TagName\> with the name of the quarantine tag, and run the following command:</span></span>

```powershell
Remove-QuarantineTag -Identity "<TagName>"
```

<span data-ttu-id="3fe6b-374">有关语法和参数的详细信息，请参阅 [QuarantineTag](https://docs.microsoft.com/powershell/module/exchange/remove-quarantinetag)。</span><span class="sxs-lookup"><span data-stu-id="3fe6b-374">For detailed syntax and parameter information, see [Remove-QuarantineTag](https://docs.microsoft.com/powershell/module/exchange/remove-quarantinetag).</span></span>

## <a name="quarantine-tag-permission-details"></a><span data-ttu-id="3fe6b-375">隔离标记权限详细信息</span><span class="sxs-lookup"><span data-stu-id="3fe6b-375">Quarantine tag permission details</span></span>

<span data-ttu-id="3fe6b-376">以下各节介绍了在隔离邮件的详细信息和最终用户垃圾邮件通知中，预置权限组和各个权限的影响。</span><span class="sxs-lookup"><span data-stu-id="3fe6b-376">The following sections describe the effects of preset permission groups and individual permissions in the details of quarantined messages and in end-user spam notifications.</span></span>

### <a name="preset-permissions-groups"></a><span data-ttu-id="3fe6b-377">预设权限组</span><span class="sxs-lookup"><span data-stu-id="3fe6b-377">Preset permissions groups</span></span>

<span data-ttu-id="3fe6b-378">[！注意] 本文开头的表中列出了 "预置权限" 组中包含的各个权限。</span><span class="sxs-lookup"><span data-stu-id="3fe6b-378">The individual permissions that are included in preset permission groups are listed in the table at the beginning of this article.</span></span>

#### <a name="no-access"></a><span data-ttu-id="3fe6b-379">禁止访问</span><span class="sxs-lookup"><span data-stu-id="3fe6b-379">No access</span></span>

<span data-ttu-id="3fe6b-380">如果隔离标记分配了 " **无访问** 权限" (不) 任何权限，则用户仍会获得一些基准功能：</span><span class="sxs-lookup"><span data-stu-id="3fe6b-380">If the quarantine tag assigns the **No access** permissions (no permissions), users still get some baseline capabilities:</span></span>

- <span data-ttu-id="3fe6b-381">**隔离的邮件详细信息**： " **查看邮件头** " 按钮始终可用。</span><span class="sxs-lookup"><span data-stu-id="3fe6b-381">**Quarantined message details**: The **View message header** button is always available.</span></span>

  ![隔离邮件详细信息中的可用按钮（如果隔离标记向用户授予无访问权限）](../../media/quarantine-tags-quarantined-message-details-no-access.png)

- <span data-ttu-id="3fe6b-383">**最终用户垃圾邮件通知**：将用户带到隔离区中的邮件的 " **审阅** " 按钮始终可用。</span><span class="sxs-lookup"><span data-stu-id="3fe6b-383">**End-user spam notifications**: The **Review** button that takes the user to the message in quarantine is always available.</span></span>

  ![最终用户垃圾邮件通知中的可用按钮（如果隔离标记向用户授予无访问权限）](../../media/quarantine-tags-esn-no-access.png)

#### <a name="limited-access"></a><span data-ttu-id="3fe6b-385">受限访问</span><span class="sxs-lookup"><span data-stu-id="3fe6b-385">Limited access</span></span>

<span data-ttu-id="3fe6b-386">如果隔离标记分配了 **有限的访问** 权限，则用户将获得以下功能：</span><span class="sxs-lookup"><span data-stu-id="3fe6b-386">If the quarantine tag assigns the **Limited access** permissions, users get the following capabilities:</span></span>

- <span data-ttu-id="3fe6b-387">**隔离的邮件详细信息**：以下按钮可用：</span><span class="sxs-lookup"><span data-stu-id="3fe6b-387">**Quarantined message details**: The following buttons are available:</span></span>
  - <span data-ttu-id="3fe6b-388">**请求释放**</span><span class="sxs-lookup"><span data-stu-id="3fe6b-388">**Request release**</span></span>
  - <span data-ttu-id="3fe6b-389">**查看邮件头**</span><span class="sxs-lookup"><span data-stu-id="3fe6b-389">**View message header**</span></span>
  - <span data-ttu-id="3fe6b-390">**预览邮件**</span><span class="sxs-lookup"><span data-stu-id="3fe6b-390">**Preview message**</span></span>
  - <span data-ttu-id="3fe6b-391">**阻止发件人**</span><span class="sxs-lookup"><span data-stu-id="3fe6b-391">**Block sender**</span></span>
  - <span data-ttu-id="3fe6b-392">**从隔离区中删除**</span><span class="sxs-lookup"><span data-stu-id="3fe6b-392">**Remove from quarantine**</span></span>

  ![隔离邮件详细信息中的可用按钮（如果隔离标记向用户授予限制访问权限）](../../media/quarantine-tags-quarantined-message-details-limited-access.png)

- <span data-ttu-id="3fe6b-394">**最终用户垃圾邮件通知**：可使用以下按钮：</span><span class="sxs-lookup"><span data-stu-id="3fe6b-394">**End-user spam notifications**: The following buttons are available:</span></span>
  - <span data-ttu-id="3fe6b-395">**阻止发件人**</span><span class="sxs-lookup"><span data-stu-id="3fe6b-395">**Block sender**</span></span>
  - <span data-ttu-id="3fe6b-396">审阅</span><span class="sxs-lookup"><span data-stu-id="3fe6b-396">**Review**</span></span>

  ![最终用户垃圾邮件通知中的可用按钮（如果隔离标记向用户授予限制访问权限）](../../media/quarantine-tags-esn-limited-access.png)

#### <a name="full-access"></a><span data-ttu-id="3fe6b-398">完全访问</span><span class="sxs-lookup"><span data-stu-id="3fe6b-398">Full access</span></span>

<span data-ttu-id="3fe6b-399">如果隔离标记分配了所有可用权限) 的 **完全访问** 权限 (，则用户将获得以下功能：</span><span class="sxs-lookup"><span data-stu-id="3fe6b-399">If the quarantine tag assigns the **Full access** permissions (all available permissions), users get the following capabilities:</span></span>

- <span data-ttu-id="3fe6b-400">**隔离的邮件详细信息**：以下按钮可用：</span><span class="sxs-lookup"><span data-stu-id="3fe6b-400">**Quarantined message details**: The following buttons are available:</span></span>
  - <span data-ttu-id="3fe6b-401">**释放邮件**</span><span class="sxs-lookup"><span data-stu-id="3fe6b-401">**Release message**</span></span>
  - <span data-ttu-id="3fe6b-402">**查看邮件头**</span><span class="sxs-lookup"><span data-stu-id="3fe6b-402">**View message header**</span></span>
  - <span data-ttu-id="3fe6b-403">**预览邮件**</span><span class="sxs-lookup"><span data-stu-id="3fe6b-403">**Preview message**</span></span>
  - <span data-ttu-id="3fe6b-404">**阻止发件人**</span><span class="sxs-lookup"><span data-stu-id="3fe6b-404">**Block sender**</span></span>
  - <span data-ttu-id="3fe6b-405">**允许发件人**</span><span class="sxs-lookup"><span data-stu-id="3fe6b-405">**Allow sender**</span></span>
  - <span data-ttu-id="3fe6b-406">**从隔离区中删除**</span><span class="sxs-lookup"><span data-stu-id="3fe6b-406">**Remove from quarantine**</span></span>

  ![隔离邮件详细信息中的可用按钮（如果隔离标记向用户授予 "完全访问" 权限）](../../media/quarantine-tags-quarantined-message-details-full-access.png)

- <span data-ttu-id="3fe6b-408">**最终用户垃圾邮件通知**：可使用以下按钮：</span><span class="sxs-lookup"><span data-stu-id="3fe6b-408">**End-user spam notifications**: The following buttons are available:</span></span>
  - <span data-ttu-id="3fe6b-409">**阻止发件人**</span><span class="sxs-lookup"><span data-stu-id="3fe6b-409">**Block sender**</span></span>
  - <span data-ttu-id="3fe6b-410">**发布**</span><span class="sxs-lookup"><span data-stu-id="3fe6b-410">**Release**</span></span>
  - <span data-ttu-id="3fe6b-411">审阅</span><span class="sxs-lookup"><span data-stu-id="3fe6b-411">**Review**</span></span>

  ![如果隔离标记向用户授予 "完全访问" 权限，则为最终用户垃圾邮件通知中的可用按钮。](../../media/quarantine-tags-esn-full-access.png)

### <a name="individual-permissions"></a><span data-ttu-id="3fe6b-413">单个权限</span><span class="sxs-lookup"><span data-stu-id="3fe6b-413">Individual permissions</span></span>

> [!NOTE]
> <span data-ttu-id="3fe6b-414">请记住，用户始终会收到 " [无访问](#no-access) " 部分中所述的按钮。</span><span class="sxs-lookup"><span data-stu-id="3fe6b-414">Remember, users always get the buttons described in the [No access](#no-access) section.</span></span> <span data-ttu-id="3fe6b-415">这些按钮不包含在各个权限说明中。</span><span class="sxs-lookup"><span data-stu-id="3fe6b-415">These buttons are not included in the individual permission descriptions.</span></span>

#### <a name="allow-sender-permission"></a><span data-ttu-id="3fe6b-416">允许发件人权限</span><span class="sxs-lookup"><span data-stu-id="3fe6b-416">Allow sender permission</span></span>

<span data-ttu-id="3fe6b-417">" **允许发件人** " 权限 (_PermissionToAllowSender_ ") 控制对按钮的访问，使用户可以方便地将隔离邮件发件人添加到其安全发件人列表。</span><span class="sxs-lookup"><span data-stu-id="3fe6b-417">The **Allow sender** permission (_PermissionToAllowSender_) controls access to the button that allows users to conveniently add the quarantined message sender to their Safe Senders list.</span></span>

- <span data-ttu-id="3fe6b-418">**隔离的邮件详细信息**：</span><span class="sxs-lookup"><span data-stu-id="3fe6b-418">**Quarantined message details**:</span></span>
  - <span data-ttu-id="3fe6b-419">启用 "**允许发件人**" 权限： "**允许发件人**" 按钮可用。</span><span class="sxs-lookup"><span data-stu-id="3fe6b-419">**Allow sender** permission enabled: The **Allow sender** button is available.</span></span>
  - <span data-ttu-id="3fe6b-420">禁用 "**允许发件人**" 权限： "**允许发件人**" 按钮不可用。</span><span class="sxs-lookup"><span data-stu-id="3fe6b-420">**Allow sender** permission disabled: The **Allow sender** button is not available.</span></span>

- <span data-ttu-id="3fe6b-421">**最终用户垃圾邮件通知**：不起作用。</span><span class="sxs-lookup"><span data-stu-id="3fe6b-421">**End-user spam notifications**: No effect.</span></span>

<span data-ttu-id="3fe6b-422">有关安全发件人列表的详细信息，请参阅 [阻止受信任发件人被阻止](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077#__toc304379666) 并 [使用 Exchange Online PowerShell 在邮箱上配置安全列表集合](configure-junk-email-settings-on-exo-mailboxes.md#use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox)。</span><span class="sxs-lookup"><span data-stu-id="3fe6b-422">For more information about the Safe Senders list, see [Prevent trusted senders from being blocked](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077#__toc304379666) and [Use Exchange Online PowerShell to configure the safelist collection on a mailbox](configure-junk-email-settings-on-exo-mailboxes.md#use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox).</span></span>

#### <a name="block-sender-permission"></a><span data-ttu-id="3fe6b-423">阻止发件人权限</span><span class="sxs-lookup"><span data-stu-id="3fe6b-423">Block sender permission</span></span>

<span data-ttu-id="3fe6b-424"> (_PermissionToBlockSender_) 的 **阻止发件人** 权限控制对按钮的访问，从而使用户可以方便地将隔离邮件发件人添加到其阻止的发件人列表。</span><span class="sxs-lookup"><span data-stu-id="3fe6b-424">The **Block sender** permission (_PermissionToBlockSender_) controls access to the button that allows users to conveniently add the quarantined message sender to their Blocked Senders list.</span></span>

- <span data-ttu-id="3fe6b-425">**隔离的邮件详细信息**：</span><span class="sxs-lookup"><span data-stu-id="3fe6b-425">**Quarantined message details**:</span></span>
  - <span data-ttu-id="3fe6b-426">**阻止发件人** 权限已启用： " **阻止发件人** " 按钮可用。</span><span class="sxs-lookup"><span data-stu-id="3fe6b-426">**Block sender** permission enabled: The **Block sender** button is available.</span></span>
  - <span data-ttu-id="3fe6b-427">**阻止发件人** 权限已禁用： " **阻止发件人** " 按钮不可用。</span><span class="sxs-lookup"><span data-stu-id="3fe6b-427">**Block sender** permission disabled: The **Block sender** button is not available.</span></span>

- <span data-ttu-id="3fe6b-428">**最终用户垃圾邮件通知**：</span><span class="sxs-lookup"><span data-stu-id="3fe6b-428">**End-user spam notifications**:</span></span>
  - <span data-ttu-id="3fe6b-429">**阻止发件人** 权限已禁用： " **阻止发件人** " 按钮不可用。</span><span class="sxs-lookup"><span data-stu-id="3fe6b-429">**Block sender** permission disabled: The **Block sender** button is not available.</span></span>
  - <span data-ttu-id="3fe6b-430">**阻止发件人** 权限已启用： " **阻止发件人** " 按钮可用。</span><span class="sxs-lookup"><span data-stu-id="3fe6b-430">**Block sender** permission enabled: The **Block sender** button is available.</span></span>

<span data-ttu-id="3fe6b-431">有关阻止发件人列表的详细信息，请参阅 [阻止来自某人的邮件](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077#__toc304379667) ，并 [使用 Exchange Online PowerShell 在邮箱上配置安全列表集合](configure-junk-email-settings-on-exo-mailboxes.md#use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox)。</span><span class="sxs-lookup"><span data-stu-id="3fe6b-431">For more information about the Blocked Senders list, see [Block messages from someone](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077#__toc304379667) and [Use Exchange Online PowerShell to configure the safelist collection on a mailbox](configure-junk-email-settings-on-exo-mailboxes.md#use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox).</span></span>

#### <a name="delete-permission"></a><span data-ttu-id="3fe6b-432">删除权限</span><span class="sxs-lookup"><span data-stu-id="3fe6b-432">Delete permission</span></span>

<span data-ttu-id="3fe6b-433">**Delete** 权限 (_PermissionToDelete_) 控制用户能否删除其邮件 (邮件，而用户是从隔离) 的收件人。</span><span class="sxs-lookup"><span data-stu-id="3fe6b-433">The **Delete** permission (_PermissionToDelete_) controls the ability to of users to delete their messages (messages where the user is a recipient) from quarantine.</span></span>

- <span data-ttu-id="3fe6b-434">**隔离的邮件详细信息**：</span><span class="sxs-lookup"><span data-stu-id="3fe6b-434">**Quarantined message details**:</span></span>
  - <span data-ttu-id="3fe6b-435">已启用 **删除** 权限：可以使用 "**从隔离中删除**" 按钮。</span><span class="sxs-lookup"><span data-stu-id="3fe6b-435">**Delete** permission enabled: The **Remove from quarantine** button is available.</span></span>
  - <span data-ttu-id="3fe6b-436">禁用 **删除** 权限： "**从隔离中删除**" 按钮不可用。</span><span class="sxs-lookup"><span data-stu-id="3fe6b-436">**Delete** permission disabled: The **Remove from quarantine** button is not available.</span></span>

- <span data-ttu-id="3fe6b-437">**最终用户垃圾邮件通知**：不起作用。</span><span class="sxs-lookup"><span data-stu-id="3fe6b-437">**End-user spam notifications**: No effect.</span></span>

#### <a name="preview-permission"></a><span data-ttu-id="3fe6b-438">预览权限</span><span class="sxs-lookup"><span data-stu-id="3fe6b-438">Preview permission</span></span>

<span data-ttu-id="3fe6b-439"> (_PermissionToPreview_) 的 **预览** 权限控制用户在隔离中预览其邮件的能力。</span><span class="sxs-lookup"><span data-stu-id="3fe6b-439">The **Preview** permission (_PermissionToPreview_) controls the ability to of users to preview their messages in quarantine.</span></span>

- <span data-ttu-id="3fe6b-440">**隔离的邮件详细信息**：</span><span class="sxs-lookup"><span data-stu-id="3fe6b-440">**Quarantined message details**:</span></span>
  - <span data-ttu-id="3fe6b-441">已启用 **预览** 权限： "**预览邮件**" 按钮可用。</span><span class="sxs-lookup"><span data-stu-id="3fe6b-441">**Preview** permission enabled: The **Preview message** button is available.</span></span>
  - <span data-ttu-id="3fe6b-442">已禁用 **预览** 权限： "**预览邮件**" 按钮不可用。</span><span class="sxs-lookup"><span data-stu-id="3fe6b-442">**Preview** permission disabled: The **Preview message** button is not available.</span></span>

- <span data-ttu-id="3fe6b-443">**最终用户垃圾邮件通知**：不起作用。</span><span class="sxs-lookup"><span data-stu-id="3fe6b-443">**End-user spam notifications**: No effect.</span></span>

#### <a name="allow-recipients-to-release-a-message-from-quarantine-permission"></a><span data-ttu-id="3fe6b-444">允许收件人释放隔离权限中的邮件</span><span class="sxs-lookup"><span data-stu-id="3fe6b-444">Allow recipients to release a message from quarantine permission</span></span>

<span data-ttu-id="3fe6b-445">" **允许收件人从隔离权限发布邮件** " (_PermissionToRelease_ ") 控制用户在不审批管理员的情况下直接释放隔离邮件的能力。</span><span class="sxs-lookup"><span data-stu-id="3fe6b-445">The **Allow recipients to release a message from quarantine** permission (_PermissionToRelease_) controls the ability of users to release their quarantined messages directly and without the approval of an admin.</span></span>

- <span data-ttu-id="3fe6b-446">**隔离的邮件详细信息**：</span><span class="sxs-lookup"><span data-stu-id="3fe6b-446">**Quarantined message details**:</span></span>
  - <span data-ttu-id="3fe6b-447">已启用权限： " **释放邮件** " 按钮可用。</span><span class="sxs-lookup"><span data-stu-id="3fe6b-447">Permission enabled: The **Release message** button is available.</span></span>
  - <span data-ttu-id="3fe6b-448">禁用了权限： " **释放邮件** " 按钮不可用。</span><span class="sxs-lookup"><span data-stu-id="3fe6b-448">Permission disabled: The **Release message** button is not available.</span></span>
  
- <span data-ttu-id="3fe6b-449">**最终用户垃圾邮件通知**：</span><span class="sxs-lookup"><span data-stu-id="3fe6b-449">**End-user spam notifications**:</span></span>
  - <span data-ttu-id="3fe6b-450">已启用权限： **释放** 按钮可用。</span><span class="sxs-lookup"><span data-stu-id="3fe6b-450">Permission enabled: The **Release** button is available.</span></span>
  - <span data-ttu-id="3fe6b-451">已禁用权限： **释放** 按钮不可用。</span><span class="sxs-lookup"><span data-stu-id="3fe6b-451">Permission disabled: The **Release** button is not available.</span></span>

#### <a name="allow-recipients-to-request-a-message-to-be-released-from-quarantine-permission"></a><span data-ttu-id="3fe6b-452">允许收件人请求从隔离权限中释放邮件</span><span class="sxs-lookup"><span data-stu-id="3fe6b-452">Allow recipients to request a message to be released from quarantine permission</span></span>

<span data-ttu-id="3fe6b-453">" **允许收件人请求从隔离权限发布邮件** " (_PermissionToRequestRelease_) 控制用户 _请求_ 释放隔离邮件的能力。</span><span class="sxs-lookup"><span data-stu-id="3fe6b-453">The **Allow recipients to request a message to be released from quarantine** permission (_PermissionToRequestRelease_) controls the ability of users to _request_ the release of their quarantined messages.</span></span> <span data-ttu-id="3fe6b-454">仅在管理员批准请求后才发布邮件。</span><span class="sxs-lookup"><span data-stu-id="3fe6b-454">The message is only released after an admin approves the request.</span></span>

- <span data-ttu-id="3fe6b-455">**隔离的邮件详细信息**：</span><span class="sxs-lookup"><span data-stu-id="3fe6b-455">**Quarantined message details**:</span></span>
  - <span data-ttu-id="3fe6b-456">已启用权限： " **请求释放** " 按钮可用。</span><span class="sxs-lookup"><span data-stu-id="3fe6b-456">Permission enabled: The **Request release** button is available.</span></span>
  - <span data-ttu-id="3fe6b-457">已禁用权限： " **请求释放** " 按钮不可用。</span><span class="sxs-lookup"><span data-stu-id="3fe6b-457">Permission disabled: The **Request release** button is not available.</span></span>

- <span data-ttu-id="3fe6b-458">**最终用户垃圾邮件通知**： " **释放** " 按钮不可用。</span><span class="sxs-lookup"><span data-stu-id="3fe6b-458">**End-user spam notifications**: The **Release** button is not available.</span></span>
