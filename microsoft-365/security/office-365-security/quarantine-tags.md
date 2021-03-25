---
title: 隔离标记
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: ''
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
ROBOTS: NOINDEX
description: 管理员可以了解如何使用隔离标记来控制用户能够对隔离邮件执行哪些操作。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 580cf2bad690d0fc6508d11178527ad218df763b
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/25/2021
ms.locfileid: "51203610"
---
# <a name="quarantine-tags"></a><span data-ttu-id="e8eaa-103">隔离标记</span><span class="sxs-lookup"><span data-stu-id="e8eaa-103">Quarantine tags</span></span>

> [!NOTE]
> <span data-ttu-id="e8eaa-104">本文中介绍的功能目前处于预览阶段，不可供所有人使用，并且可能会更改。</span><span class="sxs-lookup"><span data-stu-id="e8eaa-104">The features that are described in this article are currently in Preview, aren't available to everyone, and are subject to change.</span></span>

<span data-ttu-id="e8eaa-105">Exchange Online Protection (EOP) 中的隔离标记允许管理员根据邮件如何到达隔离区来控制用户能够对隔离邮件执行哪些操作。</span><span class="sxs-lookup"><span data-stu-id="e8eaa-105">Quarantine tags in Exchange Online Protection (EOP) allow admins to control what users are able to do to their quarantined messages based on how the message arrived in quarantine.</span></span>

<span data-ttu-id="e8eaa-106">EOP 在传统上允许或阻止隔离和最终用户垃圾邮件通知中的邮件的某些[交互级别](use-spam-notifications-to-release-and-report-quarantined-messages.md)。 [](find-and-release-quarantined-messages-as-a-user.md)</span><span class="sxs-lookup"><span data-stu-id="e8eaa-106">EOP has traditionally allowed or prevented certain levels of interactivity for messages in [quarantine](find-and-release-quarantined-messages-as-a-user.md) and in [end-user spam notifications](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span></span> <span data-ttu-id="e8eaa-107">例如，最终用户可以查看并释放被反垃圾邮件筛选隔离为垃圾邮件或批量邮件的邮件，但他们无法查看或释放被隔离为高可信度网络钓鱼的邮件。</span><span class="sxs-lookup"><span data-stu-id="e8eaa-107">For example, end-users can view and release messages that were quarantined by anti-spam filtering as spam or bulk, but they can't view or release messages that were quarantined as high confidence phishing.</span></span>

<span data-ttu-id="e8eaa-108">对于 [受支持的保护](#step-2-assign-a-quarantine-tag-to-supported-features)功能，隔离标记指定允许用户在最终用户垃圾邮件通知邮件中和隔离邮件中执行哪些操作 (用户是收件人收件人的邮件) 。</span><span class="sxs-lookup"><span data-stu-id="e8eaa-108">For [supported protection features](#step-2-assign-a-quarantine-tag-to-supported-features), quarantine tags specify what users are allowed to do in end-user spam notification messages and in their quarantined messages in quarantine (messages where the user is a recipient).</span></span> <span data-ttu-id="e8eaa-109">自动分配默认隔离标记，以强制最终用户对已隔离邮件使用历史功能。</span><span class="sxs-lookup"><span data-stu-id="e8eaa-109">Default quarantine tags are automatically assigned to enforce the historical capabilities for end-users on quarantined messages.</span></span> <span data-ttu-id="e8eaa-110">或者，可以创建和分配自定义隔离标记，以允许或阻止最终用户对隔离邮件执行特定操作。</span><span class="sxs-lookup"><span data-stu-id="e8eaa-110">Or, you can create and assign custom quarantine tags to allow or prevent end-users from performing specific actions on quarantined messages.</span></span>

<span data-ttu-id="e8eaa-111">各个权限组合到以下预设权限组中：</span><span class="sxs-lookup"><span data-stu-id="e8eaa-111">The individual permissions are combined into the following preset permission groups:</span></span>

- <span data-ttu-id="e8eaa-112">禁止访问</span><span class="sxs-lookup"><span data-stu-id="e8eaa-112">No access</span></span>
- <span data-ttu-id="e8eaa-113">受限访问</span><span class="sxs-lookup"><span data-stu-id="e8eaa-113">Limited access</span></span>
- <span data-ttu-id="e8eaa-114">完全访问权限</span><span class="sxs-lookup"><span data-stu-id="e8eaa-114">Full access</span></span>

<span data-ttu-id="e8eaa-115">下表介绍了可用的单个权限以及预设权限组中包含或不包含哪些权限：</span><span class="sxs-lookup"><span data-stu-id="e8eaa-115">The available individual permissions and what's included or not included in the preset permission groups are described in the following table:</span></span>

|<span data-ttu-id="e8eaa-116">权限</span><span class="sxs-lookup"><span data-stu-id="e8eaa-116">Permission</span></span>|<span data-ttu-id="e8eaa-117">禁止访问</span><span class="sxs-lookup"><span data-stu-id="e8eaa-117">No access</span></span>|<span data-ttu-id="e8eaa-118">受限访问</span><span class="sxs-lookup"><span data-stu-id="e8eaa-118">Limited access</span></span>|<span data-ttu-id="e8eaa-119">完全访问权限</span><span class="sxs-lookup"><span data-stu-id="e8eaa-119">Full access</span></span>|
|---|:---:|:---:|:---:|
|<span data-ttu-id="e8eaa-120">**允许发件人 (** _PermissionToAllowSender)_</span><span class="sxs-lookup"><span data-stu-id="e8eaa-120">**Allow sender** (_PermissionToAllowSender_)</span></span>|||![复选标记](../../media/checkmark.png)|
|<span data-ttu-id="e8eaa-122">**阻止发件人 (** _PermissionToBlockSender_) </span><span class="sxs-lookup"><span data-stu-id="e8eaa-122">**Block sender** (_PermissionToBlockSender_)</span></span>||![复选标记](../../media/checkmark.png)|![复选标记](../../media/checkmark.png)|
|<span data-ttu-id="e8eaa-125">**删除** (_PermissionToDelete_) </span><span class="sxs-lookup"><span data-stu-id="e8eaa-125">**Delete** (_PermissionToDelete_)</span></span>||![复选标记](../../media/checkmark.png)|![复选标记](../../media/checkmark.png)|
|<span data-ttu-id="e8eaa-128">**预览** (_PermissionToPreview_) </span><span class="sxs-lookup"><span data-stu-id="e8eaa-128">**Preview** (_PermissionToPreview_)</span></span>||![复选标记](../../media/checkmark.png)|![复选标记](../../media/checkmark.png)|
|<span data-ttu-id="e8eaa-131">**允许收件人通过** _PermissionToRelease (隔离邮件)_</span><span class="sxs-lookup"><span data-stu-id="e8eaa-131">**Allow recipients to release a message from quarantine** (_PermissionToRelease_)</span></span>|||![复选标记](../../media/checkmark.png)|
|<span data-ttu-id="e8eaa-133">**允许收件人请求从隔离邮箱** 中释放 (_PermissionToRequestRelease_) </span><span class="sxs-lookup"><span data-stu-id="e8eaa-133">**Allow recipients to request a message to be released from quarantine** (_PermissionToRequestRelease_)</span></span>||![复选标记](../../media/checkmark.png)||
|

<span data-ttu-id="e8eaa-135">如果您不喜欢预设权限组中的默认权限，可以在创建或修改自定义隔离标记时使用自定义权限。</span><span class="sxs-lookup"><span data-stu-id="e8eaa-135">If you don't like the default permissions in the preset permission groups, you can use custom permissions when you create or modify custom quarantine tags.</span></span> <span data-ttu-id="e8eaa-136">有关每个权限执行哪些操作的详细信息，请参阅本文稍后介绍的 [隔离](#quarantine-tag-permission-details) 标记权限详细信息部分。</span><span class="sxs-lookup"><span data-stu-id="e8eaa-136">For more information about what each permission does, see the [Quarantine tag permission details](#quarantine-tag-permission-details) section later in this article.</span></span>

<span data-ttu-id="e8eaa-137">在安全与合规中心或 PowerShell &为具有 Exchange Online 邮箱的 Microsoft 365 (Exchange Online PowerShell 创建和分配隔离标记;EOP 组织中没有 Exchange Online 邮箱的独立 EOP PowerShell) 。</span><span class="sxs-lookup"><span data-stu-id="e8eaa-137">You create and assign quarantine tags in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with Exchange Online Mailboxes; standalone EOP PowerShell in EOP organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="e8eaa-138">开始前，有必要了解什么？</span><span class="sxs-lookup"><span data-stu-id="e8eaa-138">What do you need to know before you begin?</span></span>

- <span data-ttu-id="e8eaa-139">安全与合规中心的打开网址为 <https://protection.office.com/>。</span><span class="sxs-lookup"><span data-stu-id="e8eaa-139">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="e8eaa-140">若要直接转到隔离 **标记页面** ，请打开 <https://protection.office.com/quarantineTags> 。</span><span class="sxs-lookup"><span data-stu-id="e8eaa-140">To go directly to the **Quarantine tags** page, open <https://protection.office.com/quarantineTags>.</span></span>

- <span data-ttu-id="e8eaa-141">若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="e8eaa-141">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="e8eaa-142">若要连接到独立 EOP PowerShell，请参阅[连接到 Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell)。</span><span class="sxs-lookup"><span data-stu-id="e8eaa-142">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="e8eaa-143">若要查看、创建、修改或删除隔离标记，您需要是安全与合规中心内组织管理或安全管理员&[的成员](permissions-in-the-security-and-compliance-center.md)。 </span><span class="sxs-lookup"><span data-stu-id="e8eaa-143">To view, create, modify, or remove quarantine tags, you need to be a member of the **Organization Management** or **Security Administrator** roles in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="step-1-create-quarantine-tags-in-the-security--compliance-center"></a><span data-ttu-id="e8eaa-144">步骤 1：在安全与合规中心&隔离标记</span><span class="sxs-lookup"><span data-stu-id="e8eaa-144">Step 1: Create quarantine tags in the Security & Compliance Center</span></span>

1. <span data-ttu-id="e8eaa-145">在安全&中心，转到"**威胁** 管理策略 \> "，然后选择"隔离 **标记"。**</span><span class="sxs-lookup"><span data-stu-id="e8eaa-145">In the Security & Compliance Center, go to **Threat management** \> **Policy** and then select **Quarantine tags**.</span></span>

2. <span data-ttu-id="e8eaa-146">在"**隔离标记"** 页上，选择"**添加自定义标记"。**</span><span class="sxs-lookup"><span data-stu-id="e8eaa-146">On the **Quarantine tags** page, select **Add custom tag**.</span></span>

3. <span data-ttu-id="e8eaa-147">将 **打开"新建标记** "向导。</span><span class="sxs-lookup"><span data-stu-id="e8eaa-147">The **New tag** wizard opens.</span></span> <span data-ttu-id="e8eaa-148">在" **标记名称"** 页上的"标记名称"字段中输入简短 **但唯一** 的名称。</span><span class="sxs-lookup"><span data-stu-id="e8eaa-148">On the **Tag name** page, enter a brief but unique name in the **Tag name** field.</span></span> <span data-ttu-id="e8eaa-149">你需要在即将推出的步骤中按名称标识和选择标记。</span><span class="sxs-lookup"><span data-stu-id="e8eaa-149">You'll need to identify and select the tag by name in upcoming steps.</span></span> <span data-ttu-id="e8eaa-150">完成后，单击“下一步”。</span><span class="sxs-lookup"><span data-stu-id="e8eaa-150">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="e8eaa-151">在" **收件人邮件访问"** 页上，选择下列值之一：</span><span class="sxs-lookup"><span data-stu-id="e8eaa-151">On the **Recipient message access** page, select one of the following values:</span></span>
   - <span data-ttu-id="e8eaa-152">**禁止访问**</span><span class="sxs-lookup"><span data-stu-id="e8eaa-152">**No access**</span></span>
   - <span data-ttu-id="e8eaa-153">**受限访问**</span><span class="sxs-lookup"><span data-stu-id="e8eaa-153">**Limited access**</span></span>
   - <span data-ttu-id="e8eaa-154">**完全访问权限**</span><span class="sxs-lookup"><span data-stu-id="e8eaa-154">**Full access**</span></span>

   <span data-ttu-id="e8eaa-155">本文前面介绍了这些权限组中包含的单个权限。</span><span class="sxs-lookup"><span data-stu-id="e8eaa-155">The individual permissions that are included in these permission groups are described earlier in this article.</span></span>

   <span data-ttu-id="e8eaa-156">若要指定自定义权限，请选择"使用高级 (设置) **并** 配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="e8eaa-156">To specify custom permissions, select **Set specific access (Advanced)** and configure the following settings:</span></span>

     - <span data-ttu-id="e8eaa-157">**选择发布操作首选项**：选择下列值之一：</span><span class="sxs-lookup"><span data-stu-id="e8eaa-157">**Select release action preference**: Select one of the following values:</span></span>
       - <span data-ttu-id="e8eaa-158">**无发布操作**：这是默认值。</span><span class="sxs-lookup"><span data-stu-id="e8eaa-158">**No release action**: This is the default value.</span></span>
       - <span data-ttu-id="e8eaa-159">**允许收件人从隔离中释放邮件**</span><span class="sxs-lookup"><span data-stu-id="e8eaa-159">**Allow recipients to release a message from quarantine**</span></span>
       - <span data-ttu-id="e8eaa-160">**允许收件人请求从隔离区中释放邮件**</span><span class="sxs-lookup"><span data-stu-id="e8eaa-160">**Allow recipients to request a message to be released from quarantine**</span></span>

     - <span data-ttu-id="e8eaa-161">**选择收件人对隔离邮件** 可以执行的其他操作：选择以下部分值、全部值或下列值之一：</span><span class="sxs-lookup"><span data-stu-id="e8eaa-161">**Select additional actions recipients can take on quarantined messages**: Select some, all, or none of the following values:</span></span>
       - <span data-ttu-id="e8eaa-162">**删除**</span><span class="sxs-lookup"><span data-stu-id="e8eaa-162">**Delete**</span></span>
       - <span data-ttu-id="e8eaa-163">**预览**</span><span class="sxs-lookup"><span data-stu-id="e8eaa-163">**Preview**</span></span>
       - <span data-ttu-id="e8eaa-164">**允许发件人**</span><span class="sxs-lookup"><span data-stu-id="e8eaa-164">**Allow sender**</span></span>
       - <span data-ttu-id="e8eaa-165">**阻止发件人**</span><span class="sxs-lookup"><span data-stu-id="e8eaa-165">**Block sender**</span></span>

   <span data-ttu-id="e8eaa-166">本文稍后的隔离标记权限详细信息部分介绍了这些权限及其对隔离邮件和最终用户垃圾邮件通知的影响。 [](#quarantine-tag-permission-details)</span><span class="sxs-lookup"><span data-stu-id="e8eaa-166">These permissions and their effect on quarantined messages and in end-user spam notifications are described in the [Quarantine tag permission details](#quarantine-tag-permission-details) section later in this article.</span></span>

   <span data-ttu-id="e8eaa-167">完成后，单击“下一步”。</span><span class="sxs-lookup"><span data-stu-id="e8eaa-167">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="e8eaa-168">在 **出现的"摘要"** 页上，查看设置。</span><span class="sxs-lookup"><span data-stu-id="e8eaa-168">On the **Summary** page that appears, review your settings.</span></span> <span data-ttu-id="e8eaa-169">可以单击每个 **设置** 上的"编辑"来修改它。</span><span class="sxs-lookup"><span data-stu-id="e8eaa-169">You can click **Edit** on each setting to modify it.</span></span>

   <span data-ttu-id="e8eaa-170">完成后，单击"提交 **"。**</span><span class="sxs-lookup"><span data-stu-id="e8eaa-170">When you're finished, click **Submit**.</span></span>

6. <span data-ttu-id="e8eaa-171">在 **出现的** 确认页上单击"完成"。</span><span class="sxs-lookup"><span data-stu-id="e8eaa-171">Click **Done** on the confirmation page that appears.</span></span>

<span data-ttu-id="e8eaa-172">现在，您已准备好将隔离标记分配给隔离功能，如步骤 [2](#step-2-assign-a-quarantine-tag-to-supported-features) 部分中所述。</span><span class="sxs-lookup"><span data-stu-id="e8eaa-172">Now you are ready to assign the quarantine tag to a quarantine feature as described in the [Step 2](#step-2-assign-a-quarantine-tag-to-supported-features) section.</span></span>

### <a name="create-quarantine-tags-in-powershell"></a><span data-ttu-id="e8eaa-173">在 PowerShell 中创建隔离标记</span><span class="sxs-lookup"><span data-stu-id="e8eaa-173">Create quarantine tags in PowerShell</span></span>

<span data-ttu-id="e8eaa-174">如果你想要使用 PowerShell 创建隔离标记，请连接到 Exchange Online PowerShell 或 Exchange Online Protection PowerShell 并使用 **New-QuarantineTag** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="e8eaa-174">If you'd rather use PowerShell to create quarantine tags, connect to Exchange Online PowerShell or Exchange Online Protection PowerShell and use the **New-QuarantineTag** cmdlet.</span></span> <span data-ttu-id="e8eaa-175">有两种不同的方法可供选择：</span><span class="sxs-lookup"><span data-stu-id="e8eaa-175">You have two different methods to choose from:</span></span>

- <span data-ttu-id="e8eaa-176">使用 _EndUserQuarantinePermissionsValue_ 参数。</span><span class="sxs-lookup"><span data-stu-id="e8eaa-176">Use the _EndUserQuarantinePermissionsValue_ parameter.</span></span>
- <span data-ttu-id="e8eaa-177">使用 _EndUserQuarantinePermissions_ 参数。</span><span class="sxs-lookup"><span data-stu-id="e8eaa-177">Use the _EndUserQuarantinePermissions_ parameter.</span></span>

<span data-ttu-id="e8eaa-178">以下各节介绍了这些方法。</span><span class="sxs-lookup"><span data-stu-id="e8eaa-178">These methods are described in the following sections.</span></span>

#### <a name="use-the-enduserquarantinepermissionsvalue-parameter"></a><span data-ttu-id="e8eaa-179">使用 EndUserQuarantinePermissionsValue 参数</span><span class="sxs-lookup"><span data-stu-id="e8eaa-179">Use the EndUserQuarantinePermissionsValue parameter</span></span>

<span data-ttu-id="e8eaa-180">若要使用 _EndUserQuarantinePermissionsValue_ 参数创建隔离标记，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="e8eaa-180">To create a quarantine tag using the _EndUserQuarantinePermissionsValue_ parameter, use the following syntax:</span></span>

```powershell
New-QuarantineTag -Name "<UniqueName>" -EndUserQuarantinePermissionsValue <0 to 236>
```

<span data-ttu-id="e8eaa-181">_EndUserQuarantinePermissionsValue_ 参数使用从二进制值转换的十进制值。</span><span class="sxs-lookup"><span data-stu-id="e8eaa-181">The _EndUserQuarantinePermissionsValue_ parameter uses a decimal value that's converted from a binary value.</span></span> <span data-ttu-id="e8eaa-182">二进制值对应于按特定顺序可用的最终用户隔离权限。</span><span class="sxs-lookup"><span data-stu-id="e8eaa-182">The binary value corresponds to the available end-user quarantine permissions in a specific order.</span></span> <span data-ttu-id="e8eaa-183">对于每个权限，值 1 等于 True，值 0 等于 False。</span><span class="sxs-lookup"><span data-stu-id="e8eaa-183">For each permission, the value 1 equals True and the value 0 equals False.</span></span>

<span data-ttu-id="e8eaa-184">下表介绍了预设权限组中各个权限的必需顺序和值：</span><span class="sxs-lookup"><span data-stu-id="e8eaa-184">The required order and values for each individual permission in preset permission groups are described in the following table:</span></span>

****

|<span data-ttu-id="e8eaa-185">权限</span><span class="sxs-lookup"><span data-stu-id="e8eaa-185">Permission</span></span>|<span data-ttu-id="e8eaa-186">禁止访问</span><span class="sxs-lookup"><span data-stu-id="e8eaa-186">No access</span></span>|<span data-ttu-id="e8eaa-187">受限访问</span><span class="sxs-lookup"><span data-stu-id="e8eaa-187">Limited access</span></span>|<span data-ttu-id="e8eaa-188">完全访问权限</span><span class="sxs-lookup"><span data-stu-id="e8eaa-188">Full access</span></span>|
|---|:---:|:---:|:---:|
|<span data-ttu-id="e8eaa-189">PermissionToAllowSender</span><span class="sxs-lookup"><span data-stu-id="e8eaa-189">PermissionToAllowSender</span></span>|<span data-ttu-id="e8eaa-190">0</span><span class="sxs-lookup"><span data-stu-id="e8eaa-190">0</span></span>|<span data-ttu-id="e8eaa-191">0</span><span class="sxs-lookup"><span data-stu-id="e8eaa-191">0</span></span>|<span data-ttu-id="e8eaa-192">1</span><span class="sxs-lookup"><span data-stu-id="e8eaa-192">1</span></span>|
|<span data-ttu-id="e8eaa-193">PermissionToBlockSender</span><span class="sxs-lookup"><span data-stu-id="e8eaa-193">PermissionToBlockSender</span></span>|<span data-ttu-id="e8eaa-194">0</span><span class="sxs-lookup"><span data-stu-id="e8eaa-194">0</span></span>|<span data-ttu-id="e8eaa-195">1</span><span class="sxs-lookup"><span data-stu-id="e8eaa-195">1</span></span>|<span data-ttu-id="e8eaa-196">1</span><span class="sxs-lookup"><span data-stu-id="e8eaa-196">1</span></span>|
|<span data-ttu-id="e8eaa-197">PermissionToDelete</span><span class="sxs-lookup"><span data-stu-id="e8eaa-197">PermissionToDelete</span></span>|<span data-ttu-id="e8eaa-198">0</span><span class="sxs-lookup"><span data-stu-id="e8eaa-198">0</span></span>|<span data-ttu-id="e8eaa-199">1</span><span class="sxs-lookup"><span data-stu-id="e8eaa-199">1</span></span>|<span data-ttu-id="e8eaa-200">1</span><span class="sxs-lookup"><span data-stu-id="e8eaa-200">1</span></span>|
|<span data-ttu-id="e8eaa-201">PermissionToDownload<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e8eaa-201">PermissionToDownload<sup>\*</sup></span></span>|<span data-ttu-id="e8eaa-202">0</span><span class="sxs-lookup"><span data-stu-id="e8eaa-202">0</span></span>|<span data-ttu-id="e8eaa-203">0</span><span class="sxs-lookup"><span data-stu-id="e8eaa-203">0</span></span>|<span data-ttu-id="e8eaa-204">0</span><span class="sxs-lookup"><span data-stu-id="e8eaa-204">0</span></span>|
|<span data-ttu-id="e8eaa-205">PermissionToPreview</span><span class="sxs-lookup"><span data-stu-id="e8eaa-205">PermissionToPreview</span></span>|<span data-ttu-id="e8eaa-206">0</span><span class="sxs-lookup"><span data-stu-id="e8eaa-206">0</span></span>|<span data-ttu-id="e8eaa-207">1</span><span class="sxs-lookup"><span data-stu-id="e8eaa-207">1</span></span>|<span data-ttu-id="e8eaa-208">1</span><span class="sxs-lookup"><span data-stu-id="e8eaa-208">1</span></span>|
|<span data-ttu-id="e8eaa-209">PermissionToRelease<sup>\*\*</sup></span><span class="sxs-lookup"><span data-stu-id="e8eaa-209">PermissionToRelease<sup>\*\*</sup></span></span>|<span data-ttu-id="e8eaa-210">0</span><span class="sxs-lookup"><span data-stu-id="e8eaa-210">0</span></span>|<span data-ttu-id="e8eaa-211">0</span><span class="sxs-lookup"><span data-stu-id="e8eaa-211">0</span></span>|<span data-ttu-id="e8eaa-212">1</span><span class="sxs-lookup"><span data-stu-id="e8eaa-212">1</span></span>|
|<span data-ttu-id="e8eaa-213">PermissionToRequestRelease<sup>\*\*</sup></span><span class="sxs-lookup"><span data-stu-id="e8eaa-213">PermissionToRequestRelease<sup>\*\*</sup></span></span>|<span data-ttu-id="e8eaa-214">0</span><span class="sxs-lookup"><span data-stu-id="e8eaa-214">0</span></span>|<span data-ttu-id="e8eaa-215">1</span><span class="sxs-lookup"><span data-stu-id="e8eaa-215">1</span></span>|<span data-ttu-id="e8eaa-216">0</span><span class="sxs-lookup"><span data-stu-id="e8eaa-216">0</span></span>|
|<span data-ttu-id="e8eaa-217">PermissionToViewHeader<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e8eaa-217">PermissionToViewHeader<sup>\*</sup></span></span>|<span data-ttu-id="e8eaa-218">0</span><span class="sxs-lookup"><span data-stu-id="e8eaa-218">0</span></span>|<span data-ttu-id="e8eaa-219">0</span><span class="sxs-lookup"><span data-stu-id="e8eaa-219">0</span></span>|<span data-ttu-id="e8eaa-220">0</span><span class="sxs-lookup"><span data-stu-id="e8eaa-220">0</span></span>|
|<span data-ttu-id="e8eaa-221">二进制值</span><span class="sxs-lookup"><span data-stu-id="e8eaa-221">Binary value</span></span>|<span data-ttu-id="e8eaa-222">00000000</span><span class="sxs-lookup"><span data-stu-id="e8eaa-222">00000000</span></span>|<span data-ttu-id="e8eaa-223">01101010</span><span class="sxs-lookup"><span data-stu-id="e8eaa-223">01101010</span></span>|<span data-ttu-id="e8eaa-224">11101100</span><span class="sxs-lookup"><span data-stu-id="e8eaa-224">11101100</span></span>|
|<span data-ttu-id="e8eaa-225">使用的小数值</span><span class="sxs-lookup"><span data-stu-id="e8eaa-225">Decimal value to use</span></span>|<span data-ttu-id="e8eaa-226">0</span><span class="sxs-lookup"><span data-stu-id="e8eaa-226">0</span></span>|<span data-ttu-id="e8eaa-227">106</span><span class="sxs-lookup"><span data-stu-id="e8eaa-227">106</span></span>|<span data-ttu-id="e8eaa-228">236</span><span class="sxs-lookup"><span data-stu-id="e8eaa-228">236</span></span>|

<span data-ttu-id="e8eaa-229"><sup>\*</sup> 目前，此值始终为 0。</span><span class="sxs-lookup"><span data-stu-id="e8eaa-229"><sup>\*</sup> Currently, this value is always 0.</span></span> <span data-ttu-id="e8eaa-230">对于 PermissionToViewHeader，值 0 不会在隔离邮件的详细信息中隐藏"查看邮件头"按钮 (该按钮始终) 。</span><span class="sxs-lookup"><span data-stu-id="e8eaa-230">For PermissionToViewHeader, the value 0 doesn't hide the **View message header** button in the details of the quarantined message (the button is always available).</span></span>

<span data-ttu-id="e8eaa-231"><sup>\*\*</sup> 不要将两个值都设置为 1。</span><span class="sxs-lookup"><span data-stu-id="e8eaa-231"><sup>\*\*</sup> Don't set both of these values to 1.</span></span> <span data-ttu-id="e8eaa-232">将一个设置为 1，另一个设置为 0，或同时设置为 0。</span><span class="sxs-lookup"><span data-stu-id="e8eaa-232">Set one to 1 and the other to 0, or set both to 0.</span></span>

<span data-ttu-id="e8eaa-233">本示例创建一个新的隔离标记名称 NoAccess，以分配上表中所述的"无访问权限"权限。</span><span class="sxs-lookup"><span data-stu-id="e8eaa-233">This example creates a new quarantine tag name NoAccess that assigns the No access permissions as described in the previous table.</span></span>

```powershell
New-QuarantineTag -Name NoAccess -EndUserQuarantinePermissionsValue 0
```

<span data-ttu-id="e8eaa-234">对于"受限访问权限"，请使用值 106。</span><span class="sxs-lookup"><span data-stu-id="e8eaa-234">For Limited access permissions, use the value 106.</span></span> <span data-ttu-id="e8eaa-235">对于"完全访问权限"，请使用值 236。</span><span class="sxs-lookup"><span data-stu-id="e8eaa-235">For Full access permissions, use the value 236.</span></span>

<span data-ttu-id="e8eaa-236">对于自定义权限，请使用上表获取与所需的权限对应的二进制值。</span><span class="sxs-lookup"><span data-stu-id="e8eaa-236">For custom permissions, use the previous table to get the binary value that corresponds to the permissions you want.</span></span> <span data-ttu-id="e8eaa-237">将二进制值转换为十进制值，并将小数值用于 _EndUserQuarantinePermissionsValue_ 参数。</span><span class="sxs-lookup"><span data-stu-id="e8eaa-237">Convert the binary value to a decimal value and use the decimal value for the _EndUserQuarantinePermissionsValue_ parameter.</span></span>

<span data-ttu-id="e8eaa-238">有关语法和参数的详细信息，请参阅 [New-QuarantineTag](/powershell/module/exchange/new-quarantinetag)。</span><span class="sxs-lookup"><span data-stu-id="e8eaa-238">For detailed syntax and parameter information, see [New-QuarantineTag](/powershell/module/exchange/new-quarantinetag).</span></span>

#### <a name="use-the-enduserquarantinepermissions-parameter"></a><span data-ttu-id="e8eaa-239">使用 EndUserQuarantinePermissions 参数</span><span class="sxs-lookup"><span data-stu-id="e8eaa-239">Use the EndUserQuarantinePermissions parameter</span></span>

<span data-ttu-id="e8eaa-240">若要使用 _EndUserQuarantinePermissionsValue_ 参数创建隔离标记，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="e8eaa-240">To create a quarantine tag using the _EndUserQuarantinePermissionsValue_ parameter, do the following steps:</span></span>

<span data-ttu-id="e8eaa-241">A.</span><span class="sxs-lookup"><span data-stu-id="e8eaa-241">A.</span></span> <span data-ttu-id="e8eaa-242">使用 **New-QuarantinePermissions** cmdlet 将隔离权限对象存储在变量中。</span><span class="sxs-lookup"><span data-stu-id="e8eaa-242">Store a quarantine permissions object in a variable using the **New-QuarantinePermissions** cmdlet.</span></span>

<p>

<span data-ttu-id="e8eaa-243">B.</span><span class="sxs-lookup"><span data-stu-id="e8eaa-243">B.</span></span> <span data-ttu-id="e8eaa-244">在 **New-QuarantineTag** 命令中将变量用作 _EndUserQuarantinePermissions_ 值。</span><span class="sxs-lookup"><span data-stu-id="e8eaa-244">Use the variable as the _EndUserQuarantinePermissions_ value in the **New-QuarantineTag** command.</span></span>

##### <a name="step-a-store-a-quarantine-permissions-object-in-a-variable"></a><span data-ttu-id="e8eaa-245">步骤 A：将隔离权限对象存储在变量中</span><span class="sxs-lookup"><span data-stu-id="e8eaa-245">Step A: Store a quarantine permissions object in a variable</span></span>

<span data-ttu-id="e8eaa-246">使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="e8eaa-246">Use the following syntax:</span></span>

```powershell
$<VariableName> = New-QuarantinePermissions [-PermissionToAllowSender <$true | $False>] [-PermissionToBlockSender <$true | $False>] [-PermissionToDelete <$true | $False>] [-PermissionToPreview <$true | $False>] [-PermissionToRelease <$true | $False>] [-PermissionToRequestRelease <$true | $False>]
```

<span data-ttu-id="e8eaa-247">任何未使用的参数的默认值都是 ，因此只需使用要将值 `$false` 设置为 的参数 `$true` 。</span><span class="sxs-lookup"><span data-stu-id="e8eaa-247">The default value for any unused parameters is `$false`, so you only need to use the parameters where you want to set value to `$true`.</span></span>

<span data-ttu-id="e8eaa-248">以下示例显示如何创建与预设权限组对应的权限对象：</span><span class="sxs-lookup"><span data-stu-id="e8eaa-248">The following examples show how to create permission objects that correspond to the preset permissions groups:</span></span>

- <span data-ttu-id="e8eaa-249">**无法访问**：</span><span class="sxs-lookup"><span data-stu-id="e8eaa-249">**No access**:</span></span>

  ```powershell
  $NoAccess = New-QuarantinePermissions
  ```

- <span data-ttu-id="e8eaa-250">**受限访问**：</span><span class="sxs-lookup"><span data-stu-id="e8eaa-250">**Limited access**:</span></span>

  ```powershell
  $LimitedAccess = New-QuarantinePermissions -PermissionToBlockSender $true -PermissionToDelete $true -PermissionToPreview $true -PermissionToRequestRelease $true
  ```

- <span data-ttu-id="e8eaa-251">**完全访问权限**：</span><span class="sxs-lookup"><span data-stu-id="e8eaa-251">**Full access**:</span></span>

  ```powershell
  $FullAccess = New-QuarantinePermissions -PermissionToAllowSender $true -PermissionToBlockSender $true -PermissionToDelete $true -PermissionToPreview $true -PermissionToRelease $true
  ```

<span data-ttu-id="e8eaa-252">To see the values that you've set， run the variable name as a command (for example， run the command `$NoAccess`) .</span><span class="sxs-lookup"><span data-stu-id="e8eaa-252">To see the values that you've set, run the variable name as a command (for example, run the command `$NoAccess`).</span></span>

<span data-ttu-id="e8eaa-253">对于自定义权限，不要同时将 _PermissionToRelease_ 和 _PermissionToRequestRelease_ 参数设置为 `$true` 。</span><span class="sxs-lookup"><span data-stu-id="e8eaa-253">For custom permissions, don't set both the _PermissionToRelease_ and _PermissionToRequestRelease_ parameters to `$true`.</span></span> <span data-ttu-id="e8eaa-254">将一个 `$true` 设置为 ，将另一个设置为 `$false` ，或者将两者都保留为 `$false` 。</span><span class="sxs-lookup"><span data-stu-id="e8eaa-254">Set one to `$true` and leave the other as `$false`, or leave both as `$false`.</span></span>

<span data-ttu-id="e8eaa-255">您还可以在创建之后、使用 **Set-QuarantinePermissions** cmdlet 使用之前修改现有 permissions 对象变量。</span><span class="sxs-lookup"><span data-stu-id="e8eaa-255">You can also modify an existing permissions object variable after you create but before you use it by using the **Set-QuarantinePermissions** cmdlet.</span></span>

<span data-ttu-id="e8eaa-256">有关语法和参数的详细信息，请参阅[New-QuarantinePermissions](/powershell/module/exchange/new-quarantinepermissions)和[Set-QuarantinePermissions。](/powershell/module/exchange/set-quarantinepermissions)</span><span class="sxs-lookup"><span data-stu-id="e8eaa-256">For detailed syntax and parameter information, see [New-QuarantinePermissions](/powershell/module/exchange/new-quarantinepermissions) and [Set-QuarantinePermissions](/powershell/module/exchange/set-quarantinepermissions).</span></span>

##### <a name="step-b-use-the-variable-in-the-new-quarantinetag-command"></a><span data-ttu-id="e8eaa-257">步骤 B：在命令中New-QuarantineTag变量</span><span class="sxs-lookup"><span data-stu-id="e8eaa-257">Step B: Use the variable in the New-QuarantineTag command</span></span>

<span data-ttu-id="e8eaa-258">创建权限对象并存储到变量中后，请使用以下 **New-QuarantineTag** 命令中的 _EndUserQuarantinePermission_ 参数值变量：</span><span class="sxs-lookup"><span data-stu-id="e8eaa-258">After you've created and stored the permissions object in a variable, use the variable for the _EndUserQuarantinePermission_ parameter value in the following **New-QuarantineTag** command:</span></span>

```powershell
New-QuarantineTag -Name "<UniqueName>" -EndUserQuarantinePermissions $<VariableName>
```

<span data-ttu-id="e8eaa-259">此示例使用上一步中介绍和创建的权限对象创建名为 LimitedAccess 的新隔离 `$LimitedAccess` 标记。</span><span class="sxs-lookup"><span data-stu-id="e8eaa-259">This example creates a new quarantine tag named LimitedAccess using the `$LimitedAccess` permissions object that was described and created in the previous step.</span></span>

```powershell
New-QuarantineTag -Name LimitedAccess -EndUserQuarantinePermissions $LimitedAccess
```

<span data-ttu-id="e8eaa-260">有关语法和参数的详细信息，请参阅 [New-QuarantineTag](/powershell/module/exchange/new-quarantinetag)。</span><span class="sxs-lookup"><span data-stu-id="e8eaa-260">For detailed syntax and parameter information, see [New-QuarantineTag](/powershell/module/exchange/new-quarantinetag).</span></span>

## <a name="step-2-assign-a-quarantine-tag-to-supported-features"></a><span data-ttu-id="e8eaa-261">步骤 2：向支持的功能分配隔离标记</span><span class="sxs-lookup"><span data-stu-id="e8eaa-261">Step 2: Assign a quarantine tag to supported features</span></span>

<span data-ttu-id="e8eaa-262">在 _可_ 自动隔离邮件或文件的 (或作为可配置操作) ，您可以将隔离标记分配给可用的隔离操作。</span><span class="sxs-lookup"><span data-stu-id="e8eaa-262">In _supported_ protection features that quarantine messages or files (automatically or as a configurable action), you can assign a quarantine tag to the available quarantine actions.</span></span> <span data-ttu-id="e8eaa-263">下表介绍了隔离邮件的功能和隔离标记的可用性：</span><span class="sxs-lookup"><span data-stu-id="e8eaa-263">Features that quarantine messages and the availability of quarantine tags are described in the following table:</span></span>

****

|<span data-ttu-id="e8eaa-264">功能</span><span class="sxs-lookup"><span data-stu-id="e8eaa-264">Feature</span></span>|<span data-ttu-id="e8eaa-265">支持隔离标记？</span><span class="sxs-lookup"><span data-stu-id="e8eaa-265">Quarantine tags supported?</span></span>|<span data-ttu-id="e8eaa-266">使用的默认隔离标记</span><span class="sxs-lookup"><span data-stu-id="e8eaa-266">Default quarantine tags used</span></span>|
|---|:---:|---|
|<span data-ttu-id="e8eaa-267">[反垃圾邮件策略](configure-your-spam-filter-policies.md)：</span><span class="sxs-lookup"><span data-stu-id="e8eaa-267">[Anti-spam policies](configure-your-spam-filter-policies.md):</span></span> <ul><li><span data-ttu-id="e8eaa-268">**Spam** (_SpamAction_) </span><span class="sxs-lookup"><span data-stu-id="e8eaa-268">**Spam** (_SpamAction_)</span></span></li><li><span data-ttu-id="e8eaa-269">**高可信度垃圾邮件** (_HighConfidenceSpamAction_) </span><span class="sxs-lookup"><span data-stu-id="e8eaa-269">**High confidence spam** (_HighConfidenceSpamAction_)</span></span></li><li><span data-ttu-id="e8eaa-270"> _PhishSpamAction_ (钓鱼) </span><span class="sxs-lookup"><span data-stu-id="e8eaa-270">**Phishing email** (_PhishSpamAction_)</span></span></li><li><span data-ttu-id="e8eaa-271"> _HighConfidencePhishAction_ (高可信度网络钓鱼) </span><span class="sxs-lookup"><span data-stu-id="e8eaa-271">**High confidence phishing email** (_HighConfidencePhishAction_)</span></span></li><li><span data-ttu-id="e8eaa-272">**BulkSpamAction** (_批量_ 电子邮件) </span><span class="sxs-lookup"><span data-stu-id="e8eaa-272">**Bulk email** (_BulkSpamAction_)</span></span></li></ul>|<span data-ttu-id="e8eaa-273">是</span><span class="sxs-lookup"><span data-stu-id="e8eaa-273">Yes</span></span>|<ul><li><span data-ttu-id="e8eaa-274">DefaultSpamTag (完全访问权限) </span><span class="sxs-lookup"><span data-stu-id="e8eaa-274">DefaultSpamTag (Full access)</span></span></li><li><span data-ttu-id="e8eaa-275">DefaultHighConfSpamTag (完全访问权限) </span><span class="sxs-lookup"><span data-stu-id="e8eaa-275">DefaultHighConfSpamTag (Full access)</span></span></li><li><span data-ttu-id="e8eaa-276">DefaultPhishTag (完全访问权限) </span><span class="sxs-lookup"><span data-stu-id="e8eaa-276">DefaultPhishTag (Full access)</span></span></li><li><span data-ttu-id="e8eaa-277">DefaultHighConfPhishTag (无法访问) </span><span class="sxs-lookup"><span data-stu-id="e8eaa-277">DefaultHighConfPhishTag (No access)</span></span></li><li><span data-ttu-id="e8eaa-278">DefaultBulkTag (完全访问权限) </span><span class="sxs-lookup"><span data-stu-id="e8eaa-278">DefaultBulkTag (Full access)</span></span></li></ul>
|<span data-ttu-id="e8eaa-279">防钓鱼策略：</span><span class="sxs-lookup"><span data-stu-id="e8eaa-279">Anti-phishing policies:</span></span> <ul><li><span data-ttu-id="e8eaa-280">[](set-up-anti-phishing-policies.md#spoof-settings) _AuthenticationFailAction (反欺骗智能_) </span><span class="sxs-lookup"><span data-stu-id="e8eaa-280">[Spoof intelligence protection](set-up-anti-phishing-policies.md#spoof-settings) (_AuthenticationFailAction_)</span></span></li><li><span data-ttu-id="e8eaa-281">[模拟保护](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)：<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e8eaa-281">[Impersonation protection](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365):<sup>\*</sup></span></span> <ul><li><span data-ttu-id="e8eaa-282">**如果电子邮件是由模拟用户发送 (** _TargetedUserProtectionAction_) </span><span class="sxs-lookup"><span data-stu-id="e8eaa-282">**If email is sent by an impersonated user** (_TargetedUserProtectionAction_)</span></span></li><li><span data-ttu-id="e8eaa-283">**如果电子邮件是由模拟域发送的， (** _TargetedDomainProtectionAction_) </span><span class="sxs-lookup"><span data-stu-id="e8eaa-283">**If email is sent by an impersonated domain** (_TargetedDomainProtectionAction_)</span></span></li><li><span data-ttu-id="e8eaa-284">**邮箱智能** \>**如果电子邮件是由模拟用户通过** _MailboxIntelligenceProtectionAction_ (发送) </span><span class="sxs-lookup"><span data-stu-id="e8eaa-284">**Mailbox intelligence** \> **If email is sent by an impersonated user** (_MailboxIntelligenceProtectionAction_)</span></span></li></ul></li></ul></ul>|<span data-ttu-id="e8eaa-285">否</span><span class="sxs-lookup"><span data-stu-id="e8eaa-285">No</span></span>|<span data-ttu-id="e8eaa-286">无</span><span class="sxs-lookup"><span data-stu-id="e8eaa-286">n/a</span></span>|
|<span data-ttu-id="e8eaa-287">[反恶意软件策略](configure-anti-malware-policies.md)：始终隔离所有检测到的邮件。</span><span class="sxs-lookup"><span data-stu-id="e8eaa-287">[Anti-malware policies](configure-anti-malware-policies.md): All detected messages are always quarantined.</span></span>|<span data-ttu-id="e8eaa-288">否</span><span class="sxs-lookup"><span data-stu-id="e8eaa-288">No</span></span>|<span data-ttu-id="e8eaa-289">无</span><span class="sxs-lookup"><span data-stu-id="e8eaa-289">n/a</span></span>|
|[<span data-ttu-id="e8eaa-290">用于 SharePoint、OneDrive 和 Microsoft Teams 的安全附件</span><span class="sxs-lookup"><span data-stu-id="e8eaa-290">Safe Attachments for SharePoint, OneDrive, and Microsoft Teams</span></span>](mdo-for-spo-odb-and-teams.md)|<span data-ttu-id="e8eaa-291">否</span><span class="sxs-lookup"><span data-stu-id="e8eaa-291">No</span></span>|<span data-ttu-id="e8eaa-292">无</span><span class="sxs-lookup"><span data-stu-id="e8eaa-292">n/a</span></span>|
|<span data-ttu-id="e8eaa-293">[邮件流规则](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (操作) 传输规则： **将** 邮件发送到托管隔离邮箱 (_隔离_) 。</span><span class="sxs-lookup"><span data-stu-id="e8eaa-293">[Mail flow rules](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (also known as transport rules) with the action: **Deliver the message to the hosted quarantine** (_Quarantine_).</span></span>|<span data-ttu-id="e8eaa-294">否</span><span class="sxs-lookup"><span data-stu-id="e8eaa-294">No</span></span>|<span data-ttu-id="e8eaa-295">无</span><span class="sxs-lookup"><span data-stu-id="e8eaa-295">n/a</span></span>|
|

<span data-ttu-id="e8eaa-296"><sup>\*</sup> 模拟保护设置仅适用于 Microsoft Defender for Office 365 中的防钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="e8eaa-296"><sup>\*</sup> Impersonation protection settings are available only in anti-phishing policies in Microsoft Defender for Office 365.</span></span>

<span data-ttu-id="e8eaa-297">如果您对默认隔离标记提供的最终用户权限满意，则无需执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="e8eaa-297">If you're happy with the end-user permissions that are provided by the default quarantine tags, you don't need to do anything.</span></span> <span data-ttu-id="e8eaa-298">如果您希望自定义最终用户功能， (垃圾邮件) 或隔离邮件详细信息中的可用按钮，您可以分配自定义隔离标记。</span><span class="sxs-lookup"><span data-stu-id="e8eaa-298">If you want to customize the end-user capabilities (available buttons) in end-user spam notifications or in quarantined message details, you can assign a custom quarantine tag.</span></span>

### <a name="assign-quarantine-tags-in-anti-spam-policies-in-the-security--compliance-center"></a><span data-ttu-id="e8eaa-299">在安全与合规中心的反垃圾邮件策略中&隔离标记</span><span class="sxs-lookup"><span data-stu-id="e8eaa-299">Assign quarantine tags in anti-spam policies in the Security & Compliance Center</span></span>

<span data-ttu-id="e8eaa-300">有关创建和修改反垃圾邮件策略的完整说明，请参阅在 [EOP 中配置反垃圾邮件策略](configure-your-spam-filter-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="e8eaa-300">Full instructions for creating and modifying anti-spam policies are described in [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

1. <span data-ttu-id="e8eaa-301">在安全&合规中心，转到"**威胁** 管理策略 \>  \> "，然后选择"**反垃圾邮件"。**</span><span class="sxs-lookup"><span data-stu-id="e8eaa-301">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> and then select **Anti-spam**.</span></span> <span data-ttu-id="e8eaa-302">或者，打开 <https://protection.office.com/antispam> 。</span><span class="sxs-lookup"><span data-stu-id="e8eaa-302">Or, open <https://protection.office.com/antispam>.</span></span>

2. <span data-ttu-id="e8eaa-303">查找并选择要编辑的现有反垃圾邮件策略，或创建新的反垃圾邮件策略。</span><span class="sxs-lookup"><span data-stu-id="e8eaa-303">Find and select an existing anti-spam policy to edit, or create a new anti-spam policy.</span></span>

3. <span data-ttu-id="e8eaa-304">在策略详细信息飞出中，展开" **垃圾邮件和批量操作"** 部分。</span><span class="sxs-lookup"><span data-stu-id="e8eaa-304">In the policy details flyout, expand the **Spam and bulk actions** section.</span></span>

4. <span data-ttu-id="e8eaa-305">If you've selected **Quarantine message** for the action of an available spam filtering verdict， the Apply quarantine **policy tag** box is available for you to select the quarantine tag for that verdict.</span><span class="sxs-lookup"><span data-stu-id="e8eaa-305">If you've selected **Quarantine message** for the action of an available spam filtering verdict, the **Apply quarantine policy tag** box is available for you to select the quarantine tag for that verdict.</span></span>

   <span data-ttu-id="e8eaa-306">**注意**：创建新策略时，垃圾邮件筛选裁定的空白隔离标记值表示已使用该裁定的默认隔离标记。</span><span class="sxs-lookup"><span data-stu-id="e8eaa-306">**Note**: When you create a new policy, a blank quarantine tag value for a spam filtering verdict indicates the default quarantine tag for that verdict is used.</span></span> <span data-ttu-id="e8eaa-307">稍后编辑策略时，空白值将替换为实际的默认隔离标记名称，如上表所述。</span><span class="sxs-lookup"><span data-stu-id="e8eaa-307">When you later edit the policy, the blank values are replaced by the actual default quarantine tag names as described in the previous table.</span></span>

   ![反垃圾邮件策略中的隔离标记选择](../../media/quarantine-tags-in-anti-spam-policies.png)

5. <span data-ttu-id="e8eaa-309">完成后，单击“保存”。</span><span class="sxs-lookup"><span data-stu-id="e8eaa-309">When you're finished, click **Save**.</span></span>

#### <a name="assign-quarantine-tags-in-anti-spam-policies-in-powershell"></a><span data-ttu-id="e8eaa-310">在 PowerShell 中的反垃圾邮件策略中分配隔离标记</span><span class="sxs-lookup"><span data-stu-id="e8eaa-310">Assign quarantine tags in anti-spam policies in PowerShell</span></span>

<span data-ttu-id="e8eaa-311">如果希望使用 PowerShell 在反垃圾邮件策略中分配隔离标记，请连接到 Exchange Online PowerShell 或 Exchange Online Protection PowerShell，然后使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="e8eaa-311">If you'd rather use PowerShell to assign quarantine tags in anti-spam policies, connect to Exchange Online PowerShell or Exchange Online Protection PowerShell and use the following syntax:</span></span>

```powershell
<New-HostedContentFilterPolicy -Name "<Unique name>" | Set-HostedContentFilterPolicy -Identity "<Policy name>">  [-SpamAction Quarantine] [-SpamQuarantineTag <QuarantineTagName>] [-HighConfidenceSpamAction Quarantine] [-HighConfidenceSpamQuarantineTag <QuarantineTagName>] [-PhishSpamAction Quarantine] [-PhishQuarantineTag <QuarantineTagName>] [-HighConfidencePhishQuarantineTag <QuarantineTagName>] [-BulkSpamAction Quarantine] [-BulkQuarantineTag <QuarantineTagName>] ...
```

<span data-ttu-id="e8eaa-312">**注意**：</span><span class="sxs-lookup"><span data-stu-id="e8eaa-312">**Notes**:</span></span>

- <span data-ttu-id="e8eaa-313">_HighConfidencePhishAction_ 参数的默认值为 Quarantine，因此无需设置新反垃圾邮件策略中的高可信度网络钓鱼检测的隔离操作。</span><span class="sxs-lookup"><span data-stu-id="e8eaa-313">The default value for the _HighConfidencePhishAction_ parameter is Quarantine, so you don't need to set the Quarantine action for high confidence phishing detections in new anti-spam policies.</span></span> <span data-ttu-id="e8eaa-314">对于新的或现有的反垃圾邮件策略中的所有其他垃圾邮件筛选裁定，隔离标记仅在操作值为 Quarantine 时有效。</span><span class="sxs-lookup"><span data-stu-id="e8eaa-314">For all other spam filtering verdicts in new or existing anti-spam policies, the quarantine tag is only effective if the action value is Quarantine.</span></span> <span data-ttu-id="e8eaa-315">若要查看现有反垃圾邮件策略中的操作值，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="e8eaa-315">To see the action values in existing anti-spam policies, run the following command:</span></span>

  ```powershell
  Get-HostedContentFilterPolicy | Format-Table Name,*SpamAction,HighConfidencePhishAction
  ```

  <span data-ttu-id="e8eaa-316">有关默认操作值以及 Standard 和 Strict 的建议操作值的信息，请参阅 [EOP 反垃圾邮件策略设置](recommended-settings-for-eop-and-office365.md#eop-anti-spam-policy-settings)。</span><span class="sxs-lookup"><span data-stu-id="e8eaa-316">For information about the default action values and the recommended action values for Standard and Strict, see [EOP anti-spam policy settings](recommended-settings-for-eop-and-office365.md#eop-anti-spam-policy-settings).</span></span>

- <span data-ttu-id="e8eaa-317">没有相应的隔离标记参数的垃圾邮件筛选裁定意味着使用该 [裁定的默认](#step-2-assign-a-quarantine-tag-to-supported-features) 隔离标记。</span><span class="sxs-lookup"><span data-stu-id="e8eaa-317">A spam filtering verdict without a corresponding quarantine tag parameter means the [default quarantine tag](#step-2-assign-a-quarantine-tag-to-supported-features) for that verdict is used.</span></span>

  <span data-ttu-id="e8eaa-318">如果您想要更改已隔离邮件的默认最终用户功能，只需将默认隔离标记替换为自定义隔离标记。</span><span class="sxs-lookup"><span data-stu-id="e8eaa-318">You only need to replace a default quarantine tag with a custom quarantine tag if you want to change the default end-user capabilities on quarantined messages.</span></span>

- <span data-ttu-id="e8eaa-319">PowerShell 中的新反垃圾邮件策略需要使用 **New-HostedContentFilterPolicy** cmdlet 和新的垃圾邮件筛选器规则 (收件人筛选器) cmdlet 创建垃圾邮件筛选策略 (设置) 。 </span><span class="sxs-lookup"><span data-stu-id="e8eaa-319">A new anti-spam policy in PowerShell requires a spam filter policy (settings) using the **New-HostedContentFilterPolicy** cmdlet and a new spam filter rule (recipient filters) using the **New-HostedContentFilterRule** cmdlet.</span></span> <span data-ttu-id="e8eaa-320">有关说明，请参阅 [使用 PowerShell 创建反垃圾邮件策略](configure-your-spam-filter-policies.md#use-powershell-to-create-anti-spam-policies)。</span><span class="sxs-lookup"><span data-stu-id="e8eaa-320">For instructions, see [Use PowerShell to create anti-spam policies](configure-your-spam-filter-policies.md#use-powershell-to-create-anti-spam-policies).</span></span>

<span data-ttu-id="e8eaa-321">本示例将创建一个名为"Research Department"的新垃圾邮件筛选策略，并具有以下设置：</span><span class="sxs-lookup"><span data-stu-id="e8eaa-321">This example creates a new spam filter policy named Research Department with the following settings:</span></span>

- <span data-ttu-id="e8eaa-322">所有垃圾邮件筛选裁定的操作均设置为"隔离"。</span><span class="sxs-lookup"><span data-stu-id="e8eaa-322">The action for all spam filtering verdicts is set to Quarantine.</span></span>
- <span data-ttu-id="e8eaa-323">分配"无访问权限"的名为 NoAccess的自定义隔离标记将替换默认情况下尚未分配"无访问权限"的任何默认隔离标记。</span><span class="sxs-lookup"><span data-stu-id="e8eaa-323">The custom quarantine tag named NoAccess that assigns **No access** permissions replaces any default quarantine tags that don't already assign **No access** permissions by default.</span></span>

```powershell
New-HostedContentFilterPolicy -Name Research Department -SpamAction Quarantine -SpamQuarantineTag NoAccess -HighConfidenceSpamAction Quarantine -HighConfidenceSpamQuarantineTag NoAction -PhishSpamAction Quarantine -PhishQuarantineTag NoAction -BulkSpamAction Quarantine -BulkQuarantineTag NoAccess
```

<span data-ttu-id="e8eaa-324">若要详细了解语法和参数，请参阅 [New-HostedContentFilterPolicy](/powershell/module/exchange/new-hostedcontentfilterpolicy)。</span><span class="sxs-lookup"><span data-stu-id="e8eaa-324">For detailed syntax and parameter information, see [New-HostedContentFilterPolicy](/powershell/module/exchange/new-hostedcontentfilterpolicy).</span></span>

<span data-ttu-id="e8eaa-325">此示例修改名为 Human Resources 的现有垃圾邮件筛选器策略。</span><span class="sxs-lookup"><span data-stu-id="e8eaa-325">This example modifies the existing spam filter policy named Human Resources.</span></span> <span data-ttu-id="e8eaa-326">垃圾邮件隔离裁定的操作设置为"隔离"，并分配名为 NoAccess 的自定义隔离标记。</span><span class="sxs-lookup"><span data-stu-id="e8eaa-326">The action for the spam quarantine verdict is set to Quarantine, and the custom quarantine tag named NoAccess is assigned.</span></span>

```powershell
Set-HostedContentFilterPolicy -Identity "Human Resources" -SpamAction Quarantine -SpamQuarantineTag NoAccess
```

<span data-ttu-id="e8eaa-327">若要详细了解语法和参数，请参阅 [Set-HostedContentFilterPolicy](/powershell/module/exchange/set-hostedcontentfilterpolicy)。</span><span class="sxs-lookup"><span data-stu-id="e8eaa-327">For detailed syntax and parameter information, see [Set-HostedContentFilterPolicy](/powershell/module/exchange/set-hostedcontentfilterpolicy).</span></span>

## <a name="configure-global-quarantine-notification-settings-in-the-security--compliance-center"></a><span data-ttu-id="e8eaa-328">在安全与合规中心&全局隔离通知设置</span><span class="sxs-lookup"><span data-stu-id="e8eaa-328">Configure global quarantine notification settings in the Security & Compliance Center</span></span>

<span data-ttu-id="e8eaa-329">隔离标记的全局设置允许您自定义发送到已隔离邮件收件人的最终用户垃圾邮件通知。</span><span class="sxs-lookup"><span data-stu-id="e8eaa-329">The global settings for quarantine tags allow you to customize the end-user spam notifications that are sent to recipients of messages that were quarantined.</span></span> <span data-ttu-id="e8eaa-330">有关这些通知详细信息，请参阅 [最终用户垃圾邮件通知](use-spam-notifications-to-release-and-report-quarantined-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="e8eaa-330">For more information about these notifications, see [End-user spam notifications](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span></span>

1. <span data-ttu-id="e8eaa-331">在安全&中心，转到"**威胁** 管理策略 \> "，然后选择"隔离 **标记"。**</span><span class="sxs-lookup"><span data-stu-id="e8eaa-331">In the Security & Compliance Center, go to **Threat management** \> **Policy** and then select **Quarantine tags**.</span></span>

2. <span data-ttu-id="e8eaa-332">在"**隔离标记"** 页上，选择"**全局设置"。**</span><span class="sxs-lookup"><span data-stu-id="e8eaa-332">On the **Quarantine tags** page, select **Global settings**.</span></span>

3. <span data-ttu-id="e8eaa-333">在打开 **的"隔离** 通知设置"飞出中，配置以下部分或所有设置：</span><span class="sxs-lookup"><span data-stu-id="e8eaa-333">In the **Quarantine notification settings** flyout that opens, configure some or all of the following settings:</span></span>

   - <span data-ttu-id="e8eaa-334">**使用我的公司徽标**：选择此选项可替换最终用户垃圾邮件通知顶部使用的默认 Microsoft 徽标。</span><span class="sxs-lookup"><span data-stu-id="e8eaa-334">**Use my company logo**: Select this option to replace the default Microsoft logo that's use at the top of end-user spam notifications.</span></span> <span data-ttu-id="e8eaa-335">在这样做之前，需要按照自定义 [组织的 Microsoft 365](../../admin/setup/customize-your-organization-theme.md) 主题中的说明上载自定义徽标。</span><span class="sxs-lookup"><span data-stu-id="e8eaa-335">Before you do this, you need to follow the instructions in [Customize the Microsoft 365 theme for your organization](../../admin/setup/customize-your-organization-theme.md) to upload your custom logo.</span></span>

     <span data-ttu-id="e8eaa-336">以下屏幕截图显示了最终用户垃圾邮件通知中的自定义徽标：</span><span class="sxs-lookup"><span data-stu-id="e8eaa-336">The following screenshot shows a custom logo in an end-user spam notification:</span></span>

     ![最终用户垃圾邮件通知中的自定义徽标](../../media/quarantine-tags-esn-customization-logo.png)

   - <span data-ttu-id="e8eaa-338">**选择语言**：最终用户垃圾邮件通知已根据收件人的语言设置进行本地化。</span><span class="sxs-lookup"><span data-stu-id="e8eaa-338">**Choose language**: End-user spam notifications are already localized based on the recipient's language settings.</span></span> <span data-ttu-id="e8eaa-339">您可以为"显示名称"和"免责声明"值指定不同语言的 **自定义** 文本。</span><span class="sxs-lookup"><span data-stu-id="e8eaa-339">You can specify customized text in different languages for the **Display name** and **Disclaimer** values.</span></span>

     <span data-ttu-id="e8eaa-340">至少从第一种语言框中选择一种语言， **然后单击添加**。</span><span class="sxs-lookup"><span data-stu-id="e8eaa-340">Select at least one language from the first language box and then click **Add**.</span></span> <span data-ttu-id="e8eaa-341">可以通过单击每种语言后的" **添加** "来选择多种语言。</span><span class="sxs-lookup"><span data-stu-id="e8eaa-341">You can select multiple languages by clicking **Add** after each one.</span></span> <span data-ttu-id="e8eaa-342">部分语言框显示你选择的所有语言：</span><span class="sxs-lookup"><span data-stu-id="e8eaa-342">A section language box shows all of the languages that you've selected:</span></span>

     ![隔离标记的全局隔离通知设置中第二种语言框中选定的语言](../../media/quarantine-tags-esn-customization-selected-languages.png)

   - <span data-ttu-id="e8eaa-344">**显示名称**：自定义显示名称垃圾邮件通知中使用的发件人地址。</span><span class="sxs-lookup"><span data-stu-id="e8eaa-344">**Display name**: Customize the sender's display name that's used in end-user spam notifications.</span></span>

     <span data-ttu-id="e8eaa-345">对于已添加的每种语言，选择第二种语言框中的语言 (不要单击 X) 请在"显示名称"框中输入您需要 **的文本值。**</span><span class="sxs-lookup"><span data-stu-id="e8eaa-345">For each language that you've added, select the language in the second language box (don't click on the X) and enter the text value you want in the **Display name** box.</span></span>

     <span data-ttu-id="e8eaa-346">以下屏幕截图显示了最终用户显示名称中的自定义邮件：</span><span class="sxs-lookup"><span data-stu-id="e8eaa-346">The following screenshot shows the customized display name in an end-user spam notification:</span></span>

     ![自定义发件人显示名称最终用户垃圾邮件通知中](../../media/quarantine-tags-esn-customization-display-name.png)

   - <span data-ttu-id="e8eaa-348">**免责声明**：将自定义免责声明添加到最终用户垃圾邮件通知的底部。</span><span class="sxs-lookup"><span data-stu-id="e8eaa-348">**Disclaimer**: Add a custom disclaimer to the bottom of end-user spam notifications.</span></span> <span data-ttu-id="e8eaa-349">您组织的本地化文本 **（免责声明：）** 始终先包含，后跟您指定的文本。</span><span class="sxs-lookup"><span data-stu-id="e8eaa-349">The localized text, **A disclaimer from your organization:** is always included first, followed by the text you specify.</span></span>

     <span data-ttu-id="e8eaa-350">对于已添加的每种语言，选择第二种语言框中 (不要单击"X) "，在"免责声明"框中输入 **您需要的文本值** 。</span><span class="sxs-lookup"><span data-stu-id="e8eaa-350">For each language that you've added, select the language in the second language box  (don't click the X) and enter the text value you want in the **Disclaimer** box.</span></span>

     <span data-ttu-id="e8eaa-351">以下屏幕截图显示了最终用户垃圾邮件通知中的自定义免责声明：</span><span class="sxs-lookup"><span data-stu-id="e8eaa-351">The following screenshot shows the customized disclaimer in an end-user spam notification:</span></span>

     ![最终用户垃圾邮件通知底部的自定义免责声明](../../media/quarantine-tags-esn-customization-disclaimer.png)

## <a name="view-quarantine-tags-in-the-security--compliance-center"></a><span data-ttu-id="e8eaa-353">在安全与合规中心&隔离标记</span><span class="sxs-lookup"><span data-stu-id="e8eaa-353">View quarantine tags in the Security & Compliance Center</span></span>

1. <span data-ttu-id="e8eaa-354">在安全&中心，转到"**威胁** 管理策略 \> "，然后选择"隔离 **标记"。**</span><span class="sxs-lookup"><span data-stu-id="e8eaa-354">In the Security & Compliance Center, go to **Threat management** \> **Policy** and then select **Quarantine tags**.</span></span>

- <span data-ttu-id="e8eaa-355">若要查看内置或自定义隔离标记的设置，请从列表中选择隔离标记 (不要选中复选框) 。</span><span class="sxs-lookup"><span data-stu-id="e8eaa-355">To view the settings of built-in or custom quarantine tags, select the quarantine tag from the list (don't select the check box).</span></span>

- <span data-ttu-id="e8eaa-356">若要查看全局设置，请选择" **全局设置"**</span><span class="sxs-lookup"><span data-stu-id="e8eaa-356">To view the global settings, select **Global settings**</span></span>

### <a name="view-quarantine-tags-in-powershell"></a><span data-ttu-id="e8eaa-357">在 PowerShell 中查看隔离标记</span><span class="sxs-lookup"><span data-stu-id="e8eaa-357">View quarantine tags in PowerShell</span></span>

<span data-ttu-id="e8eaa-358">如果你希望使用 PowerShell 查看隔离标记，请执行下列任一步骤：</span><span class="sxs-lookup"><span data-stu-id="e8eaa-358">If you'd rather use PowerShell to view quarantine tags, do any of the following steps:</span></span>

- <span data-ttu-id="e8eaa-359">若要查看所有内置或自定义标记的摘要列表，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="e8eaa-359">To view a summary list of all built-in or custom tags, run the following command:</span></span>

  ```powershell
  Get-QuarantineTag | Format-Table Name
  ```

- <span data-ttu-id="e8eaa-360">若要查看内置或自定义隔离标记的设置，请将 替换为隔离标记的名称， \<TagName\> 然后运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="e8eaa-360">To view the settings of built-in or custom quarantine tags, replace \<TagName\> with the name of the quarantine tag, and run the following command:</span></span>

  ```powershell
  Get-QuarantineTag -Identity "<TagName>"
  ```

- <span data-ttu-id="e8eaa-361">若要查看全局设置，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="e8eaa-361">To view the global settings, run the following command:</span></span>

  ```powershell
  Get-QuarantineTag -QuarantineTagType GlobalQuarantineTag
  ```

<span data-ttu-id="e8eaa-362">若要详细了解语法和参数，请参阅 [Get-HostedContentFilterPolicy](/powershell/module/exchange/get-hostedcontentfilterpolicy)。</span><span class="sxs-lookup"><span data-stu-id="e8eaa-362">For detailed syntax and parameter information, see [Get-HostedContentFilterPolicy](/powershell/module/exchange/get-hostedcontentfilterpolicy).</span></span>

## <a name="remove-quarantine-tags-in-the-security--compliance-center"></a><span data-ttu-id="e8eaa-363">在安全与合规中心&隔离标记</span><span class="sxs-lookup"><span data-stu-id="e8eaa-363">Remove quarantine tags in the Security & Compliance Center</span></span>

<span data-ttu-id="e8eaa-364">**注意**：</span><span class="sxs-lookup"><span data-stu-id="e8eaa-364">**Notes**:</span></span>

- <span data-ttu-id="e8eaa-365">无法删除内置隔离标记。</span><span class="sxs-lookup"><span data-stu-id="e8eaa-365">You can't remove built-in quarantine tags.</span></span>

- <span data-ttu-id="e8eaa-366">在删除自定义隔离标记之前，请验证该标记是否未使用。</span><span class="sxs-lookup"><span data-stu-id="e8eaa-366">Before you remove a custom quarantine tag, verify that it's not being used.</span></span> <span data-ttu-id="e8eaa-367">例如，在 PowerShell 中运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="e8eaa-367">For example, run the following command in PowerShell:</span></span>

  ```powershell
  Get-HostedContentFilterPolicy | Format-List Name,*QuarantineTag
  ```

  <span data-ttu-id="e8eaa-368">如果使用隔离标记， [请替换已分配的隔离](#step-2-assign-a-quarantine-tag-to-supported-features) 标记，然后再删除它。</span><span class="sxs-lookup"><span data-stu-id="e8eaa-368">If the quarantine tag is being used, [replace the assigned quarantine tag](#step-2-assign-a-quarantine-tag-to-supported-features) before you remove it.</span></span>

1. <span data-ttu-id="e8eaa-369">在安全&中心，转到"**威胁** 管理策略 \> "，然后选择"隔离 **标记"。**</span><span class="sxs-lookup"><span data-stu-id="e8eaa-369">In the Security & Compliance Center, go to **Threat management** \> **Policy** and then select **Quarantine tags**.</span></span>

2. <span data-ttu-id="e8eaa-370">在"**隔离标记**"页上，选择要删除的自定义隔离标记，然后单击"删除 **标记"。**</span><span class="sxs-lookup"><span data-stu-id="e8eaa-370">On the **Quarantine tags** page, select the custom quarantine tag that you want to remove, and the click **Delete tag**.</span></span>

3. <span data-ttu-id="e8eaa-371">单击 **出现的** 确认对话框中的"删除标记"。</span><span class="sxs-lookup"><span data-stu-id="e8eaa-371">Click **Remove tag** in the confirmation dialog that appears.</span></span>

### <a name="remove-quarantine-tags-in-powershell"></a><span data-ttu-id="e8eaa-372">在 PowerShell 中删除隔离标记</span><span class="sxs-lookup"><span data-stu-id="e8eaa-372">Remove quarantine tags in PowerShell</span></span>

<span data-ttu-id="e8eaa-373">如果你希望使用 PowerShell 删除自定义隔离标记，请将 替换为隔离标记的名称，然后 \<TagName\> 运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="e8eaa-373">If you'd rather use PowerShell to remove a custom quarantine tag, replace \<TagName\> with the name of the quarantine tag, and run the following command:</span></span>

```powershell
Remove-QuarantineTag -Identity "<TagName>"
```

<span data-ttu-id="e8eaa-374">有关语法和参数的详细信息，请参阅 [Remove-QuarantineTag](/powershell/module/exchange/remove-quarantinetag)。</span><span class="sxs-lookup"><span data-stu-id="e8eaa-374">For detailed syntax and parameter information, see [Remove-QuarantineTag](/powershell/module/exchange/remove-quarantinetag).</span></span>

## <a name="quarantine-tag-permission-details"></a><span data-ttu-id="e8eaa-375">隔离标记权限详细信息</span><span class="sxs-lookup"><span data-stu-id="e8eaa-375">Quarantine tag permission details</span></span>

<span data-ttu-id="e8eaa-376">以下各节介绍预设权限组和个人权限在隔离邮件的详细信息和最终用户垃圾邮件通知中的影响。</span><span class="sxs-lookup"><span data-stu-id="e8eaa-376">The following sections describe the effects of preset permission groups and individual permissions in the details of quarantined messages and in end-user spam notifications.</span></span>

### <a name="preset-permissions-groups"></a><span data-ttu-id="e8eaa-377">预设权限组</span><span class="sxs-lookup"><span data-stu-id="e8eaa-377">Preset permissions groups</span></span>

<span data-ttu-id="e8eaa-378">本文开头的表中列出了预设权限组中包含的单个权限。</span><span class="sxs-lookup"><span data-stu-id="e8eaa-378">The individual permissions that are included in preset permission groups are listed in the table at the beginning of this article.</span></span>

#### <a name="no-access"></a><span data-ttu-id="e8eaa-379">禁止访问</span><span class="sxs-lookup"><span data-stu-id="e8eaa-379">No access</span></span>

<span data-ttu-id="e8eaa-380">如果隔离标记将"无访问权限" (没有权限) ，则用户仍获得一些基线功能：</span><span class="sxs-lookup"><span data-stu-id="e8eaa-380">If the quarantine tag assigns the **No access** permissions (no permissions), users still get some baseline capabilities:</span></span>

- <span data-ttu-id="e8eaa-381">**隔离邮件详细信息\*\*\*\*："查看邮件头**"按钮始终可用。</span><span class="sxs-lookup"><span data-stu-id="e8eaa-381">**Quarantined message details**: The **View message header** button is always available.</span></span>

  ![隔离标记授予用户无访问权限时隔离邮件详细信息中的可用按钮](../../media/quarantine-tags-quarantined-message-details-no-access.png)

- <span data-ttu-id="e8eaa-383">**最终用户垃圾邮件通知**： **将用户** 发送到隔离邮件的"审阅"按钮始终可用。</span><span class="sxs-lookup"><span data-stu-id="e8eaa-383">**End-user spam notifications**: The **Review** button that takes the user to the message in quarantine is always available.</span></span>

  ![如果隔离标记授予用户无访问权限，最终用户垃圾邮件通知中的可用按钮](../../media/quarantine-tags-esn-no-access.png)

#### <a name="limited-access"></a><span data-ttu-id="e8eaa-385">受限访问</span><span class="sxs-lookup"><span data-stu-id="e8eaa-385">Limited access</span></span>

<span data-ttu-id="e8eaa-386">如果隔离标记分配 **了"受限"** 访问权限，则用户会获得以下功能：</span><span class="sxs-lookup"><span data-stu-id="e8eaa-386">If the quarantine tag assigns the **Limited access** permissions, users get the following capabilities:</span></span>

- <span data-ttu-id="e8eaa-387">**隔离邮件详细信息**：以下按钮可用：</span><span class="sxs-lookup"><span data-stu-id="e8eaa-387">**Quarantined message details**: The following buttons are available:</span></span>
  - <span data-ttu-id="e8eaa-388">**请求释放**</span><span class="sxs-lookup"><span data-stu-id="e8eaa-388">**Request release**</span></span>
  - <span data-ttu-id="e8eaa-389">**查看邮件头**</span><span class="sxs-lookup"><span data-stu-id="e8eaa-389">**View message header**</span></span>
  - <span data-ttu-id="e8eaa-390">**预览邮件**</span><span class="sxs-lookup"><span data-stu-id="e8eaa-390">**Preview message**</span></span>
  - <span data-ttu-id="e8eaa-391">**阻止发件人**</span><span class="sxs-lookup"><span data-stu-id="e8eaa-391">**Block sender**</span></span>
  - <span data-ttu-id="e8eaa-392">**从隔离区中删除**</span><span class="sxs-lookup"><span data-stu-id="e8eaa-392">**Remove from quarantine**</span></span>

  ![隔离标记授予用户受限访问权限时隔离邮件详细信息中的可用按钮](../../media/quarantine-tags-quarantined-message-details-limited-access.png)

- <span data-ttu-id="e8eaa-394">**最终用户垃圾邮件通知**：以下按钮可用：</span><span class="sxs-lookup"><span data-stu-id="e8eaa-394">**End-user spam notifications**: The following buttons are available:</span></span>
  - <span data-ttu-id="e8eaa-395">**阻止发件人**</span><span class="sxs-lookup"><span data-stu-id="e8eaa-395">**Block sender**</span></span>
  - <span data-ttu-id="e8eaa-396">**审阅**</span><span class="sxs-lookup"><span data-stu-id="e8eaa-396">**Review**</span></span>

  ![如果隔离标记授予用户受限访问权限，最终用户垃圾邮件通知中的可用按钮](../../media/quarantine-tags-esn-limited-access.png)

#### <a name="full-access"></a><span data-ttu-id="e8eaa-398">完全访问权限</span><span class="sxs-lookup"><span data-stu-id="e8eaa-398">Full access</span></span>

<span data-ttu-id="e8eaa-399">如果隔离标记分配了"完全 **访问权限** (所有可用) ，则用户会获得以下功能：</span><span class="sxs-lookup"><span data-stu-id="e8eaa-399">If the quarantine tag assigns the **Full access** permissions (all available permissions), users get the following capabilities:</span></span>

- <span data-ttu-id="e8eaa-400">**隔离邮件详细信息**：以下按钮可用：</span><span class="sxs-lookup"><span data-stu-id="e8eaa-400">**Quarantined message details**: The following buttons are available:</span></span>
  - <span data-ttu-id="e8eaa-401">**释放邮件**</span><span class="sxs-lookup"><span data-stu-id="e8eaa-401">**Release message**</span></span>
  - <span data-ttu-id="e8eaa-402">**查看邮件头**</span><span class="sxs-lookup"><span data-stu-id="e8eaa-402">**View message header**</span></span>
  - <span data-ttu-id="e8eaa-403">**预览邮件**</span><span class="sxs-lookup"><span data-stu-id="e8eaa-403">**Preview message**</span></span>
  - <span data-ttu-id="e8eaa-404">**阻止发件人**</span><span class="sxs-lookup"><span data-stu-id="e8eaa-404">**Block sender**</span></span>
  - <span data-ttu-id="e8eaa-405">**允许发件人**</span><span class="sxs-lookup"><span data-stu-id="e8eaa-405">**Allow sender**</span></span>
  - <span data-ttu-id="e8eaa-406">**从隔离区中删除**</span><span class="sxs-lookup"><span data-stu-id="e8eaa-406">**Remove from quarantine**</span></span>

  ![隔离标记授予用户完全访问权限时隔离邮件详细信息中的可用按钮](../../media/quarantine-tags-quarantined-message-details-full-access.png)

- <span data-ttu-id="e8eaa-408">**最终用户垃圾邮件通知**：以下按钮可用：</span><span class="sxs-lookup"><span data-stu-id="e8eaa-408">**End-user spam notifications**: The following buttons are available:</span></span>
  - <span data-ttu-id="e8eaa-409">**阻止发件人**</span><span class="sxs-lookup"><span data-stu-id="e8eaa-409">**Block sender**</span></span>
  - <span data-ttu-id="e8eaa-410">**发布**</span><span class="sxs-lookup"><span data-stu-id="e8eaa-410">**Release**</span></span>
  - <span data-ttu-id="e8eaa-411">**审阅**</span><span class="sxs-lookup"><span data-stu-id="e8eaa-411">**Review**</span></span>

  ![如果隔离标记授予用户完全访问权限，最终用户垃圾邮件通知中的可用按钮](../../media/quarantine-tags-esn-full-access.png)

### <a name="individual-permissions"></a><span data-ttu-id="e8eaa-413">个人权限</span><span class="sxs-lookup"><span data-stu-id="e8eaa-413">Individual permissions</span></span>

> [!NOTE]
> <span data-ttu-id="e8eaa-414">请记住，用户始终获取"无法访问"部分 [中描述的](#no-access) 按钮。</span><span class="sxs-lookup"><span data-stu-id="e8eaa-414">Remember, users always get the buttons described in the [No access](#no-access) section.</span></span> <span data-ttu-id="e8eaa-415">这些按钮不包含在单个权限说明中。</span><span class="sxs-lookup"><span data-stu-id="e8eaa-415">These buttons are not included in the individual permission descriptions.</span></span>

#### <a name="allow-sender-permission"></a><span data-ttu-id="e8eaa-416">允许发件人权限</span><span class="sxs-lookup"><span data-stu-id="e8eaa-416">Allow sender permission</span></span>

<span data-ttu-id="e8eaa-417">_PermissionToAllowSender (PermissionToAllowSender_) 控制对按钮的访问权限，该按钮允许用户方便地将隔离的邮件发件人添加到其安全发件人列表。 </span><span class="sxs-lookup"><span data-stu-id="e8eaa-417">The **Allow sender** permission (_PermissionToAllowSender_) controls access to the button that allows users to conveniently add the quarantined message sender to their Safe Senders list.</span></span>

- <span data-ttu-id="e8eaa-418">**隔离邮件详细信息**：</span><span class="sxs-lookup"><span data-stu-id="e8eaa-418">**Quarantined message details**:</span></span>
  - <span data-ttu-id="e8eaa-419">**启用发件人** 权限：" **允许发件人"** 按钮可用。</span><span class="sxs-lookup"><span data-stu-id="e8eaa-419">**Allow sender** permission enabled: The **Allow sender** button is available.</span></span>
  - <span data-ttu-id="e8eaa-420">**禁用发件人** 权限：" **允许发件人"** 按钮不可用。</span><span class="sxs-lookup"><span data-stu-id="e8eaa-420">**Allow sender** permission disabled: The **Allow sender** button is not available.</span></span>

- <span data-ttu-id="e8eaa-421">**最终用户垃圾邮件通知：** 不起作用。</span><span class="sxs-lookup"><span data-stu-id="e8eaa-421">**End-user spam notifications**: No effect.</span></span>

<span data-ttu-id="e8eaa-422">有关安全发件人列表详细信息，请参阅防止受信任发件人[](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077#__toc304379666)被阻止和使用 Exchange Online PowerShell 配置邮箱[的安全列表集合](configure-junk-email-settings-on-exo-mailboxes.md#use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox)。</span><span class="sxs-lookup"><span data-stu-id="e8eaa-422">For more information about the Safe Senders list, see [Prevent trusted senders from being blocked](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077#__toc304379666) and [Use Exchange Online PowerShell to configure the safelist collection on a mailbox](configure-junk-email-settings-on-exo-mailboxes.md#use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox).</span></span>

#### <a name="block-sender-permission"></a><span data-ttu-id="e8eaa-423">阻止发件人权限</span><span class="sxs-lookup"><span data-stu-id="e8eaa-423">Block sender permission</span></span>

<span data-ttu-id="e8eaa-424">_PermissionToBlockSender_ (阻止发件人) 控制对按钮的访问权限，该按钮允许用户便捷地将隔离的邮件发件人添加到其阻止的发件人列表。 </span><span class="sxs-lookup"><span data-stu-id="e8eaa-424">The **Block sender** permission (_PermissionToBlockSender_) controls access to the button that allows users to conveniently add the quarantined message sender to their Blocked Senders list.</span></span>

- <span data-ttu-id="e8eaa-425">**隔离邮件详细信息**：</span><span class="sxs-lookup"><span data-stu-id="e8eaa-425">**Quarantined message details**:</span></span>
  - <span data-ttu-id="e8eaa-426">**阻止发件人** 权限已启用 **："阻止发件人"** 按钮可用。</span><span class="sxs-lookup"><span data-stu-id="e8eaa-426">**Block sender** permission enabled: The **Block sender** button is available.</span></span>
  - <span data-ttu-id="e8eaa-427">**阻止发件人** 权限已禁用：阻止 **发件人** 按钮不可用。</span><span class="sxs-lookup"><span data-stu-id="e8eaa-427">**Block sender** permission disabled: The **Block sender** button is not available.</span></span>

- <span data-ttu-id="e8eaa-428">**最终用户垃圾邮件通知**：</span><span class="sxs-lookup"><span data-stu-id="e8eaa-428">**End-user spam notifications**:</span></span>
  - <span data-ttu-id="e8eaa-429">**阻止发件人** 权限已禁用：阻止 **发件人** 按钮不可用。</span><span class="sxs-lookup"><span data-stu-id="e8eaa-429">**Block sender** permission disabled: The **Block sender** button is not available.</span></span>
  - <span data-ttu-id="e8eaa-430">**阻止发件人** 权限已启用 **："阻止发件人"** 按钮可用。</span><span class="sxs-lookup"><span data-stu-id="e8eaa-430">**Block sender** permission enabled: The **Block sender** button is available.</span></span>

<span data-ttu-id="e8eaa-431">有关阻止的发件人列表的信息，请参阅阻止来自某人的邮件[](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077#__toc304379667)和使用 Exchange Online PowerShell 配置邮箱[的安全列表集合](configure-junk-email-settings-on-exo-mailboxes.md#use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox)。</span><span class="sxs-lookup"><span data-stu-id="e8eaa-431">For more information about the Blocked Senders list, see [Block messages from someone](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077#__toc304379667) and [Use Exchange Online PowerShell to configure the safelist collection on a mailbox](configure-junk-email-settings-on-exo-mailboxes.md#use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox).</span></span>

#### <a name="delete-permission"></a><span data-ttu-id="e8eaa-432">删除权限</span><span class="sxs-lookup"><span data-stu-id="e8eaa-432">Delete permission</span></span>

<span data-ttu-id="e8eaa-433">_PermissionToDelete (PermissionToDelete_) 控制用户能否删除其邮件 (用户是收件人的邮件，) 隔离。 </span><span class="sxs-lookup"><span data-stu-id="e8eaa-433">The **Delete** permission (_PermissionToDelete_) controls the ability to of users to delete their messages (messages where the user is a recipient) from quarantine.</span></span>

- <span data-ttu-id="e8eaa-434">**隔离邮件详细信息**：</span><span class="sxs-lookup"><span data-stu-id="e8eaa-434">**Quarantined message details**:</span></span>
  - <span data-ttu-id="e8eaa-435">**启用** 删除权限：" **从隔离区删除"** 按钮可用。</span><span class="sxs-lookup"><span data-stu-id="e8eaa-435">**Delete** permission enabled: The **Remove from quarantine** button is available.</span></span>
  - <span data-ttu-id="e8eaa-436">**删除** 权限已禁用：" **从隔离区删除"** 按钮不可用。</span><span class="sxs-lookup"><span data-stu-id="e8eaa-436">**Delete** permission disabled: The **Remove from quarantine** button is not available.</span></span>

- <span data-ttu-id="e8eaa-437">**最终用户垃圾邮件通知：** 不起作用。</span><span class="sxs-lookup"><span data-stu-id="e8eaa-437">**End-user spam notifications**: No effect.</span></span>

#### <a name="preview-permission"></a><span data-ttu-id="e8eaa-438">预览权限</span><span class="sxs-lookup"><span data-stu-id="e8eaa-438">Preview permission</span></span>

<span data-ttu-id="e8eaa-439">_PermissionToPreview_ (预览) 控制用户在隔离中预览邮件的能力。 </span><span class="sxs-lookup"><span data-stu-id="e8eaa-439">The **Preview** permission (_PermissionToPreview_) controls the ability to of users to preview their messages in quarantine.</span></span>

- <span data-ttu-id="e8eaa-440">**隔离邮件详细信息**：</span><span class="sxs-lookup"><span data-stu-id="e8eaa-440">**Quarantined message details**:</span></span>
  - <span data-ttu-id="e8eaa-441">**预览** 权限已启用： **预览邮件** 按钮可用。</span><span class="sxs-lookup"><span data-stu-id="e8eaa-441">**Preview** permission enabled: The **Preview message** button is available.</span></span>
  - <span data-ttu-id="e8eaa-442">**预览** 权限已禁用： **预览邮件** 按钮不可用。</span><span class="sxs-lookup"><span data-stu-id="e8eaa-442">**Preview** permission disabled: The **Preview message** button is not available.</span></span>

- <span data-ttu-id="e8eaa-443">**最终用户垃圾邮件通知：** 不起作用。</span><span class="sxs-lookup"><span data-stu-id="e8eaa-443">**End-user spam notifications**: No effect.</span></span>

#### <a name="allow-recipients-to-release-a-message-from-quarantine-permission"></a><span data-ttu-id="e8eaa-444">允许收件人解除邮件隔离权限</span><span class="sxs-lookup"><span data-stu-id="e8eaa-444">Allow recipients to release a message from quarantine permission</span></span>

<span data-ttu-id="e8eaa-445">_PermissionToRelease_) 中的"允许收件人从隔离中释放邮件"权限 (控制用户直接释放隔离邮件的能力，而无需经过管理员批准。 </span><span class="sxs-lookup"><span data-stu-id="e8eaa-445">The **Allow recipients to release a message from quarantine** permission (_PermissionToRelease_) controls the ability of users to release their quarantined messages directly and without the approval of an admin.</span></span>

- <span data-ttu-id="e8eaa-446">**隔离邮件详细信息**：</span><span class="sxs-lookup"><span data-stu-id="e8eaa-446">**Quarantined message details**:</span></span>
  - <span data-ttu-id="e8eaa-447">已启用权限 **："释放邮件"** 按钮可用。</span><span class="sxs-lookup"><span data-stu-id="e8eaa-447">Permission enabled: The **Release message** button is available.</span></span>
  - <span data-ttu-id="e8eaa-448">权限已禁用 **："释放邮件** "按钮不可用。</span><span class="sxs-lookup"><span data-stu-id="e8eaa-448">Permission disabled: The **Release message** button is not available.</span></span>

- <span data-ttu-id="e8eaa-449">**最终用户垃圾邮件通知**：</span><span class="sxs-lookup"><span data-stu-id="e8eaa-449">**End-user spam notifications**:</span></span>
  - <span data-ttu-id="e8eaa-450">已启用权限 **："释放** "按钮可用。</span><span class="sxs-lookup"><span data-stu-id="e8eaa-450">Permission enabled: The **Release** button is available.</span></span>
  - <span data-ttu-id="e8eaa-451">权限已禁用 **："释放** "按钮不可用。</span><span class="sxs-lookup"><span data-stu-id="e8eaa-451">Permission disabled: The **Release** button is not available.</span></span>

#### <a name="allow-recipients-to-request-a-message-to-be-released-from-quarantine-permission"></a><span data-ttu-id="e8eaa-452">允许收件人请求从隔离权限中释放邮件</span><span class="sxs-lookup"><span data-stu-id="e8eaa-452">Allow recipients to request a message to be released from quarantine permission</span></span>

<span data-ttu-id="e8eaa-453">允许 **收件人** 请求从隔离中释放的邮件权限 (_PermissionToRequestRelease_) 控制用户请求释放其隔离邮件的能力。 </span><span class="sxs-lookup"><span data-stu-id="e8eaa-453">The **Allow recipients to request a message to be released from quarantine** permission (_PermissionToRequestRelease_) controls the ability of users to _request_ the release of their quarantined messages.</span></span> <span data-ttu-id="e8eaa-454">邮件仅在管理员批准请求后释放。</span><span class="sxs-lookup"><span data-stu-id="e8eaa-454">The message is only released after an admin approves the request.</span></span>

- <span data-ttu-id="e8eaa-455">**隔离邮件详细信息**：</span><span class="sxs-lookup"><span data-stu-id="e8eaa-455">**Quarantined message details**:</span></span>
  - <span data-ttu-id="e8eaa-456">已启用权限 **："请求释放** "按钮可用。</span><span class="sxs-lookup"><span data-stu-id="e8eaa-456">Permission enabled: The **Request release** button is available.</span></span>
  - <span data-ttu-id="e8eaa-457">权限已禁用 **："请求释放** "按钮不可用。</span><span class="sxs-lookup"><span data-stu-id="e8eaa-457">Permission disabled: The **Request release** button is not available.</span></span>

- <span data-ttu-id="e8eaa-458">**最终用户垃圾邮件通知**：" **释放** "按钮不可用。</span><span class="sxs-lookup"><span data-stu-id="e8eaa-458">**End-user spam notifications**: The **Release** button is not available.</span></span>