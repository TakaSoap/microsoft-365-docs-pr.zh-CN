---
title: 隔离策略
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
description: 管理员可以了解如何使用隔离策略来控制用户可以对隔离邮件执行哪些操作。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 96dc1e2158787457884ca6a3c6f27bf76e83a369
ms.sourcegitcommit: fa9efab24a84f71fec7d001f2ad8949125fa8eee
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/22/2021
ms.locfileid: "53055208"
---
# <a name="quarantine-policies"></a><span data-ttu-id="8e470-103">隔离策略</span><span class="sxs-lookup"><span data-stu-id="8e470-103">Quarantine policies</span></span>

> [!NOTE]
> <span data-ttu-id="8e470-104">本文中介绍的功能目前处于预览阶段，不可供所有人使用，并且可能会更改。</span><span class="sxs-lookup"><span data-stu-id="8e470-104">The features that are described in this article are currently in Preview, aren't available to everyone, and are subject to change.</span></span>

<span data-ttu-id="8e470-105"> (EOP) 中以前称为隔离标记 Exchange Online Protection () 的隔离策略允许管理员根据邮件如何到达隔离区来控制用户能够对隔离邮件执行哪些操作。</span><span class="sxs-lookup"><span data-stu-id="8e470-105">Quarantine policies (formerly known as quarantine tags) in Exchange Online Protection (EOP) allow admins to control what users are able to do to their quarantined messages based on how the message arrived in quarantine.</span></span>

<span data-ttu-id="8e470-106">EOP 在传统上允许或阻止隔离和最终用户垃圾邮件通知中的邮件的某些[交互级别](use-spam-notifications-to-release-and-report-quarantined-messages.md)。 [](find-and-release-quarantined-messages-as-a-user.md)</span><span class="sxs-lookup"><span data-stu-id="8e470-106">EOP has traditionally allowed or prevented certain levels of interactivity for messages in [quarantine](find-and-release-quarantined-messages-as-a-user.md) and in [end-user spam notifications](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span></span> <span data-ttu-id="8e470-107">例如，用户可以查看并释放被反垃圾邮件筛选隔离为垃圾邮件或批量邮件的邮件，但他们无法查看或释放被隔离为高可信度网络钓鱼的邮件 (只有管理员才能执行) 。</span><span class="sxs-lookup"><span data-stu-id="8e470-107">For example, users can view and release messages that were quarantined by anti-spam filtering as spam or bulk, but they can't view or release messages that were quarantined as high confidence phishing (only admins can do that).</span></span>

<span data-ttu-id="8e470-108">对于 [受支持的保护](#step-2-assign-a-quarantine-policy-to-supported-features)功能，隔离策略指定允许用户在最终用户垃圾邮件通知邮件中和隔离邮件中执行哪些操作 (用户是收件人收件人的邮件) 。</span><span class="sxs-lookup"><span data-stu-id="8e470-108">For [supported protection features](#step-2-assign-a-quarantine-policy-to-supported-features), quarantine policies specify what users are allowed to do in end-user spam notification messages and in their quarantined messages in quarantine (messages where the user is a recipient).</span></span> <span data-ttu-id="8e470-109">自动分配默认隔离策略，以对隔离邮件的用户强制实施历史功能。</span><span class="sxs-lookup"><span data-stu-id="8e470-109">Default quarantine policies are automatically assigned to enforce the historical capabilities for users on quarantined messages.</span></span> <span data-ttu-id="8e470-110">或者，可以创建和分配自定义隔离策略，以允许或阻止最终用户对隔离邮件执行特定操作。</span><span class="sxs-lookup"><span data-stu-id="8e470-110">Or, you can create and assign custom quarantine policies to allow or prevent end users from performing specific actions on quarantined messages.</span></span>

<span data-ttu-id="8e470-111">各个权限组合到以下预设权限组中：</span><span class="sxs-lookup"><span data-stu-id="8e470-111">The individual permissions are combined into the following preset permission groups:</span></span>

- <span data-ttu-id="8e470-112">禁止访问</span><span class="sxs-lookup"><span data-stu-id="8e470-112">No access</span></span>
- <span data-ttu-id="8e470-113">受限访问</span><span class="sxs-lookup"><span data-stu-id="8e470-113">Limited access</span></span>
- <span data-ttu-id="8e470-114">完全访问权限</span><span class="sxs-lookup"><span data-stu-id="8e470-114">Full access</span></span>

<span data-ttu-id="8e470-115">下表介绍了可用的单个权限以及预设权限组中包含或不包含哪些权限：</span><span class="sxs-lookup"><span data-stu-id="8e470-115">The available individual permissions and what's included or not included in the preset permission groups are described in the following table:</span></span>

<br>

****

|<span data-ttu-id="8e470-116">权限</span><span class="sxs-lookup"><span data-stu-id="8e470-116">Permission</span></span>|<span data-ttu-id="8e470-117">禁止访问</span><span class="sxs-lookup"><span data-stu-id="8e470-117">No access</span></span>|<span data-ttu-id="8e470-118">受限访问</span><span class="sxs-lookup"><span data-stu-id="8e470-118">Limited access</span></span>|<span data-ttu-id="8e470-119">完全访问权限</span><span class="sxs-lookup"><span data-stu-id="8e470-119">Full access</span></span>|
|---|:---:|:---:|:---:|
|<span data-ttu-id="8e470-120">**允许发件人 (** _PermissionToAllowSender)_</span><span class="sxs-lookup"><span data-stu-id="8e470-120">**Allow sender** (_PermissionToAllowSender_)</span></span>|||![复选标记](../../media/checkmark.png)|
|<span data-ttu-id="8e470-122">**阻止发件人 (** _PermissionToBlockSender_) </span><span class="sxs-lookup"><span data-stu-id="8e470-122">**Block sender** (_PermissionToBlockSender_)</span></span>||![复选标记](../../media/checkmark.png)|![复选标记](../../media/checkmark.png)|
|<span data-ttu-id="8e470-125">**删除** (_PermissionToDelete_) </span><span class="sxs-lookup"><span data-stu-id="8e470-125">**Delete** (_PermissionToDelete_)</span></span>||![复选标记](../../media/checkmark.png)|![复选标记](../../media/checkmark.png)|
|<span data-ttu-id="8e470-128">**预览** (_PermissionToPreview_) </span><span class="sxs-lookup"><span data-stu-id="8e470-128">**Preview** (_PermissionToPreview_)</span></span>||![复选标记](../../media/checkmark.png)|![复选标记](../../media/checkmark.png)|
|<span data-ttu-id="8e470-131">**允许收件人通过** _PermissionToRelease (隔离邮件)_</span><span class="sxs-lookup"><span data-stu-id="8e470-131">**Allow recipients to release a message from quarantine** (_PermissionToRelease_)</span></span>|||![复选标记](../../media/checkmark.png)|
|<span data-ttu-id="8e470-133">**允许收件人请求从隔离邮箱** 中释放 (_PermissionToRequestRelease_) </span><span class="sxs-lookup"><span data-stu-id="8e470-133">**Allow recipients to request a message to be released from quarantine** (_PermissionToRequestRelease_)</span></span>||![复选标记](../../media/checkmark.png)||
|

<span data-ttu-id="8e470-135">如果您不喜欢预设权限组中的默认权限，可以在创建或修改自定义隔离策略时使用自定义权限。</span><span class="sxs-lookup"><span data-stu-id="8e470-135">If you don't like the default permissions in the preset permission groups, you can use custom permissions when you create or modify custom quarantine policies.</span></span> <span data-ttu-id="8e470-136">有关每个权限执行哪些操作的详细信息，请参阅本文稍后[](#quarantine-policy-permission-details)介绍的隔离策略权限详细信息部分。</span><span class="sxs-lookup"><span data-stu-id="8e470-136">For more information about what each permission does, see the [Quarantine policy permission details](#quarantine-policy-permission-details) section later in this article.</span></span>

<span data-ttu-id="8e470-137">在邮箱门户或 PowerShell Microsoft 365 Defender PowerShell (Exchange Online邮箱Microsoft 365分配隔离Exchange Online策略;EOP 组织中独立的 EOP PowerShell，Exchange Online邮箱) 。</span><span class="sxs-lookup"><span data-stu-id="8e470-137">You create and assign quarantine policies in the Microsoft 365 Defender portal or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with Exchange Online Mailboxes; standalone EOP PowerShell in EOP organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="8e470-138">开始前，有必要了解什么？</span><span class="sxs-lookup"><span data-stu-id="8e470-138">What do you need to know before you begin?</span></span>

- <span data-ttu-id="8e470-139">访问 <https://security.microsoft.com> 打开 Microsoft 365 Defender 门户。</span><span class="sxs-lookup"><span data-stu-id="8e470-139">You open the Microsoft 365 Defender portal at <https://security.microsoft.com>.</span></span> <span data-ttu-id="8e470-140">或者，若要直接转到隔离 **策略页面** ，请打开 <https://security.microsoft.com/quarantineTags> 。</span><span class="sxs-lookup"><span data-stu-id="8e470-140">Or to go directly to the **Quarantine policies** page, open <https://security.microsoft.com/quarantineTags>.</span></span>

- <span data-ttu-id="8e470-141">若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="8e470-141">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="8e470-142">若要连接到独立 EOP PowerShell，请参阅[连接到 Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell)。</span><span class="sxs-lookup"><span data-stu-id="8e470-142">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="8e470-143">若要查看、创建、修改或删除隔离策略，您需要是组织管理或安全管理员角色在 Microsoft 365 Defender的成员。 </span><span class="sxs-lookup"><span data-stu-id="8e470-143">To view, create, modify, or remove quarantine policies, you need to be a member of the **Organization Management** or **Security Administrator** roles in the Microsoft 365 Defender portal.</span></span> <span data-ttu-id="8e470-144">有关详细信息，请参阅 [Microsoft 365 Defender 门户中的权限](permissions-microsoft-365-security-center.md)。</span><span class="sxs-lookup"><span data-stu-id="8e470-144">For more information, see [Permissions in the Microsoft 365 Defender portal](permissions-microsoft-365-security-center.md).</span></span>

## <a name="step-1-create-quarantine-policies-in-the-microsoft-365-defender-portal"></a><span data-ttu-id="8e470-145">步骤 1：在管理门户Microsoft 365 Defender隔离策略</span><span class="sxs-lookup"><span data-stu-id="8e470-145">Step 1: Create quarantine policies in the Microsoft 365 Defender portal</span></span>

1. <span data-ttu-id="8e470-146">在 Microsoft 365 Defender 门户中，转到"电子邮件&协作威胁策略"部分"**隔离** 策略"， \>  \>  \> 然后选择"隔离 **策略"。**</span><span class="sxs-lookup"><span data-stu-id="8e470-146">In the Microsoft 365 Defender portal, go to **Email & collaboration** \>**Threat policies** \> **Rules** section \> **Quarantine policies** and then select **Quarantine policies**.</span></span>

2. <span data-ttu-id="8e470-147">在"**隔离策略"页上**，单击" ![ 添加自定义策略"图标 ](../../media/m365-cc-sc-create-icon.png) **"添加自定义策略"。**</span><span class="sxs-lookup"><span data-stu-id="8e470-147">On the **Quarantine policy** page, click ![Add custom policy icon](../../media/m365-cc-sc-create-icon.png) **Add custom policy**.</span></span>

3. <span data-ttu-id="8e470-148">将 **打开"新建策略** "向导。</span><span class="sxs-lookup"><span data-stu-id="8e470-148">The **New policy** wizard opens.</span></span> <span data-ttu-id="8e470-149">在" **策略名称"** 页上，在"策略名称"框中输入简短但 **唯一** 的名称。</span><span class="sxs-lookup"><span data-stu-id="8e470-149">On the **Policy name** page, enter a brief but unique name in the **Policy name** box.</span></span> <span data-ttu-id="8e470-150">你需要在即将推出的步骤中按名称标识并选择隔离策略。</span><span class="sxs-lookup"><span data-stu-id="8e470-150">You'll need to identify and select the quarantine policy by name in upcoming steps.</span></span> <span data-ttu-id="8e470-151">完成后，单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="8e470-151">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="8e470-152">在" **收件人邮件访问"** 页上，选择下列值之一：</span><span class="sxs-lookup"><span data-stu-id="8e470-152">On the **Recipient message access** page, select one of the following values:</span></span>
   - <span data-ttu-id="8e470-153">**禁止访问**</span><span class="sxs-lookup"><span data-stu-id="8e470-153">**No access**</span></span>
   - <span data-ttu-id="8e470-154">**受限访问**</span><span class="sxs-lookup"><span data-stu-id="8e470-154">**Limited access**</span></span>
   - <span data-ttu-id="8e470-155">**完全访问权限**</span><span class="sxs-lookup"><span data-stu-id="8e470-155">**Full access**</span></span>

   <span data-ttu-id="8e470-156">本文前面介绍了这些权限组中包含的单个权限。</span><span class="sxs-lookup"><span data-stu-id="8e470-156">The individual permissions that are included in these permission groups are described earlier in this article.</span></span>

   <span data-ttu-id="8e470-157">若要指定自定义权限，请选择"使用高级 (设置) 并配置以下显示设置：</span><span class="sxs-lookup"><span data-stu-id="8e470-157">To specify custom permissions, select **Set specific access (Advanced)** and the configure the following settings that appear:</span></span>

     - <span data-ttu-id="8e470-158">**选择发布操作首选项**：选择下列值之一：</span><span class="sxs-lookup"><span data-stu-id="8e470-158">**Select release action preference**: Select one of the following values:</span></span>
       - <span data-ttu-id="8e470-159">**无发布操作**：这是默认值。</span><span class="sxs-lookup"><span data-stu-id="8e470-159">**No release action**: This is the default value.</span></span>
       - <span data-ttu-id="8e470-160">**允许收件人从隔离中释放邮件**</span><span class="sxs-lookup"><span data-stu-id="8e470-160">**Allow recipients to release a message from quarantine**</span></span>
       - <span data-ttu-id="8e470-161">**允许收件人请求从隔离区中释放邮件**</span><span class="sxs-lookup"><span data-stu-id="8e470-161">**Allow recipients to request a message to be released from quarantine**</span></span>
     - <span data-ttu-id="8e470-162">**选择收件人对隔离邮件** 可以执行的其他操作：选择以下部分值、全部值或下列值之一：</span><span class="sxs-lookup"><span data-stu-id="8e470-162">**Select additional actions recipients can take on quarantined messages**: Select some, all, or none of the following values:</span></span>
       - <span data-ttu-id="8e470-163">**删除**</span><span class="sxs-lookup"><span data-stu-id="8e470-163">**Delete**</span></span>
       - <span data-ttu-id="8e470-164">**预览**</span><span class="sxs-lookup"><span data-stu-id="8e470-164">**Preview**</span></span>
       - <span data-ttu-id="8e470-165">**阻止发件人**</span><span class="sxs-lookup"><span data-stu-id="8e470-165">**Block sender**</span></span>

   <span data-ttu-id="8e470-166">本文稍后的隔离策略权限详细信息部分介绍了这些权限及其对隔离邮件和最终用户垃圾邮件通知的影响。 [](#quarantine-policy-permission-details)</span><span class="sxs-lookup"><span data-stu-id="8e470-166">These permissions and their effect on quarantined messages and in end-user spam notifications are described in the [Quarantine policy permission details](#quarantine-policy-permission-details) section later in this article.</span></span>

   <span data-ttu-id="8e470-167">完成后，单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="8e470-167">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="8e470-168">在出现的 **"查看** 策略"页上，查看设置。</span><span class="sxs-lookup"><span data-stu-id="8e470-168">On the **Review policy** page that appears, review your settings.</span></span> <span data-ttu-id="8e470-169">可以在每个部分中选择“**编辑**”来修改该部分中的设置。</span><span class="sxs-lookup"><span data-stu-id="8e470-169">You can select **Edit** in each section to modify the settings within the section.</span></span> <span data-ttu-id="8e470-170">或者，可以单击“**返回**”或选择向导中的特定页面。</span><span class="sxs-lookup"><span data-stu-id="8e470-170">Or you can click **Back** or select the specific page in the wizard.</span></span>

   <span data-ttu-id="8e470-171">完成后，单击"提交 **"。**</span><span class="sxs-lookup"><span data-stu-id="8e470-171">When you're finished, click **Submit**.</span></span>

6. <span data-ttu-id="8e470-172">在出现的确认页面上，单击“**完成**”。</span><span class="sxs-lookup"><span data-stu-id="8e470-172">On the confirmation page that appears, click **Done**.</span></span>

<span data-ttu-id="8e470-173">现在，你已准备好将隔离策略分配给隔离功能，如步骤 [2](#step-2-assign-a-quarantine-policy-to-supported-features) 部分中所述。</span><span class="sxs-lookup"><span data-stu-id="8e470-173">Now you're ready to assign the quarantine policy to a quarantine feature as described in the [Step 2](#step-2-assign-a-quarantine-policy-to-supported-features) section.</span></span>

### <a name="create-quarantine-policies-in-powershell"></a><span data-ttu-id="8e470-174">在 PowerShell 中创建隔离策略</span><span class="sxs-lookup"><span data-stu-id="8e470-174">Create quarantine policies in PowerShell</span></span>

<span data-ttu-id="8e470-175">如果你希望使用 PowerShell 创建隔离策略，请连接到 Exchange Online PowerShell 或 Exchange Online Protection PowerShell 并使用 **New-QuarantineTag** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="8e470-175">If you'd rather use PowerShell to create quarantine policies, connect to Exchange Online PowerShell or Exchange Online Protection PowerShell and use the **New-QuarantineTag** cmdlet.</span></span> <span data-ttu-id="8e470-176">有两种不同的方法可供选择：</span><span class="sxs-lookup"><span data-stu-id="8e470-176">You have two different methods to choose from:</span></span>

- <span data-ttu-id="8e470-177">使用 _EndUserQuarantinePermissionsValue_ 参数。</span><span class="sxs-lookup"><span data-stu-id="8e470-177">Use the _EndUserQuarantinePermissionsValue_ parameter.</span></span>
- <span data-ttu-id="8e470-178">使用 _EndUserQuarantinePermissions_ 参数。</span><span class="sxs-lookup"><span data-stu-id="8e470-178">Use the _EndUserQuarantinePermissions_ parameter.</span></span>

<span data-ttu-id="8e470-179">以下各节介绍了这些方法。</span><span class="sxs-lookup"><span data-stu-id="8e470-179">These methods are described in the following sections.</span></span>

#### <a name="use-the-enduserquarantinepermissionsvalue-parameter"></a><span data-ttu-id="8e470-180">使用 EndUserQuarantinePermissionsValue 参数</span><span class="sxs-lookup"><span data-stu-id="8e470-180">Use the EndUserQuarantinePermissionsValue parameter</span></span>

<span data-ttu-id="8e470-181">若要使用 _EndUserQuarantinePermissionsValue_ 参数创建隔离策略，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="8e470-181">To create a quarantine policy using the _EndUserQuarantinePermissionsValue_ parameter, use the following syntax:</span></span>

```powershell
New-QuarantineTag -Name "<UniqueName>" -EndUserQuarantinePermissionsValue <0 to 236>
```

<span data-ttu-id="8e470-182">_EndUserQuarantinePermissionsValue_ 参数使用从二进制值转换的十进制值。</span><span class="sxs-lookup"><span data-stu-id="8e470-182">The _EndUserQuarantinePermissionsValue_ parameter uses a decimal value that's converted from a binary value.</span></span> <span data-ttu-id="8e470-183">二进制值对应于按特定顺序可用的最终用户隔离权限。</span><span class="sxs-lookup"><span data-stu-id="8e470-183">The binary value corresponds to the available end-user quarantine permissions in a specific order.</span></span> <span data-ttu-id="8e470-184">对于每个权限，值 1 等于 True，值 0 等于 False。</span><span class="sxs-lookup"><span data-stu-id="8e470-184">For each permission, the value 1 equals True and the value 0 equals False.</span></span>

<span data-ttu-id="8e470-185">下表介绍了预设权限组中各个权限的必需顺序和值：</span><span class="sxs-lookup"><span data-stu-id="8e470-185">The required order and values for each individual permission in preset permission groups are described in the following table:</span></span>

<br>

****

|<span data-ttu-id="8e470-186">权限</span><span class="sxs-lookup"><span data-stu-id="8e470-186">Permission</span></span>|<span data-ttu-id="8e470-187">禁止访问</span><span class="sxs-lookup"><span data-stu-id="8e470-187">No access</span></span>|<span data-ttu-id="8e470-188">受限访问</span><span class="sxs-lookup"><span data-stu-id="8e470-188">Limited access</span></span>|<span data-ttu-id="8e470-189">完全访问权限</span><span class="sxs-lookup"><span data-stu-id="8e470-189">Full access</span></span>|
|---|:---:|:---:|:---:|
|<span data-ttu-id="8e470-190">PermissionToAllowSender</span><span class="sxs-lookup"><span data-stu-id="8e470-190">PermissionToAllowSender</span></span>|<span data-ttu-id="8e470-191">0</span><span class="sxs-lookup"><span data-stu-id="8e470-191">0</span></span>|<span data-ttu-id="8e470-192">0</span><span class="sxs-lookup"><span data-stu-id="8e470-192">0</span></span>|<span data-ttu-id="8e470-193">1</span><span class="sxs-lookup"><span data-stu-id="8e470-193">1</span></span>|
|<span data-ttu-id="8e470-194">PermissionToBlockSender</span><span class="sxs-lookup"><span data-stu-id="8e470-194">PermissionToBlockSender</span></span>|<span data-ttu-id="8e470-195">0</span><span class="sxs-lookup"><span data-stu-id="8e470-195">0</span></span>|<span data-ttu-id="8e470-196">1</span><span class="sxs-lookup"><span data-stu-id="8e470-196">1</span></span>|<span data-ttu-id="8e470-197">1</span><span class="sxs-lookup"><span data-stu-id="8e470-197">1</span></span>|
|<span data-ttu-id="8e470-198">PermissionToDelete</span><span class="sxs-lookup"><span data-stu-id="8e470-198">PermissionToDelete</span></span>|<span data-ttu-id="8e470-199">0</span><span class="sxs-lookup"><span data-stu-id="8e470-199">0</span></span>|<span data-ttu-id="8e470-200">1</span><span class="sxs-lookup"><span data-stu-id="8e470-200">1</span></span>|<span data-ttu-id="8e470-201">1</span><span class="sxs-lookup"><span data-stu-id="8e470-201">1</span></span>|
|<span data-ttu-id="8e470-202">PermissionToDownload<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="8e470-202">PermissionToDownload<sup>\*</sup></span></span>|<span data-ttu-id="8e470-203">0</span><span class="sxs-lookup"><span data-stu-id="8e470-203">0</span></span>|<span data-ttu-id="8e470-204">0</span><span class="sxs-lookup"><span data-stu-id="8e470-204">0</span></span>|<span data-ttu-id="8e470-205">0</span><span class="sxs-lookup"><span data-stu-id="8e470-205">0</span></span>|
|<span data-ttu-id="8e470-206">PermissionToPreview</span><span class="sxs-lookup"><span data-stu-id="8e470-206">PermissionToPreview</span></span>|<span data-ttu-id="8e470-207">0</span><span class="sxs-lookup"><span data-stu-id="8e470-207">0</span></span>|<span data-ttu-id="8e470-208">1</span><span class="sxs-lookup"><span data-stu-id="8e470-208">1</span></span>|<span data-ttu-id="8e470-209">1</span><span class="sxs-lookup"><span data-stu-id="8e470-209">1</span></span>|
|<span data-ttu-id="8e470-210">PermissionToRelease<sup>\*\*</sup></span><span class="sxs-lookup"><span data-stu-id="8e470-210">PermissionToRelease<sup>\*\*</sup></span></span>|<span data-ttu-id="8e470-211">0</span><span class="sxs-lookup"><span data-stu-id="8e470-211">0</span></span>|<span data-ttu-id="8e470-212">0</span><span class="sxs-lookup"><span data-stu-id="8e470-212">0</span></span>|<span data-ttu-id="8e470-213">1</span><span class="sxs-lookup"><span data-stu-id="8e470-213">1</span></span>|
|<span data-ttu-id="8e470-214">PermissionToRequestRelease<sup>\*\*</sup></span><span class="sxs-lookup"><span data-stu-id="8e470-214">PermissionToRequestRelease<sup>\*\*</sup></span></span>|<span data-ttu-id="8e470-215">0</span><span class="sxs-lookup"><span data-stu-id="8e470-215">0</span></span>|<span data-ttu-id="8e470-216">1</span><span class="sxs-lookup"><span data-stu-id="8e470-216">1</span></span>|<span data-ttu-id="8e470-217">0</span><span class="sxs-lookup"><span data-stu-id="8e470-217">0</span></span>|
|<span data-ttu-id="8e470-218">PermissionToViewHeader<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="8e470-218">PermissionToViewHeader<sup>\*</sup></span></span>|<span data-ttu-id="8e470-219">0</span><span class="sxs-lookup"><span data-stu-id="8e470-219">0</span></span>|<span data-ttu-id="8e470-220">0</span><span class="sxs-lookup"><span data-stu-id="8e470-220">0</span></span>|<span data-ttu-id="8e470-221">0</span><span class="sxs-lookup"><span data-stu-id="8e470-221">0</span></span>|
|<span data-ttu-id="8e470-222">二进制值</span><span class="sxs-lookup"><span data-stu-id="8e470-222">Binary value</span></span>|<span data-ttu-id="8e470-223">00000000</span><span class="sxs-lookup"><span data-stu-id="8e470-223">00000000</span></span>|<span data-ttu-id="8e470-224">01101010</span><span class="sxs-lookup"><span data-stu-id="8e470-224">01101010</span></span>|<span data-ttu-id="8e470-225">11101100</span><span class="sxs-lookup"><span data-stu-id="8e470-225">11101100</span></span>|
|<span data-ttu-id="8e470-226">使用的小数值</span><span class="sxs-lookup"><span data-stu-id="8e470-226">Decimal value to use</span></span>|<span data-ttu-id="8e470-227">0</span><span class="sxs-lookup"><span data-stu-id="8e470-227">0</span></span>|<span data-ttu-id="8e470-228">106</span><span class="sxs-lookup"><span data-stu-id="8e470-228">106</span></span>|<span data-ttu-id="8e470-229">236</span><span class="sxs-lookup"><span data-stu-id="8e470-229">236</span></span>|
|

<span data-ttu-id="8e470-230"><sup>\*</sup> 目前，此值始终为 0。</span><span class="sxs-lookup"><span data-stu-id="8e470-230"><sup>\*</sup> Currently, this value is always 0.</span></span> <span data-ttu-id="8e470-231">对于 PermissionToViewHeader，值 0 不会在隔离邮件的详细信息中隐藏"查看邮件头"按钮 (该按钮始终) 。</span><span class="sxs-lookup"><span data-stu-id="8e470-231">For PermissionToViewHeader, the value 0 doesn't hide the **View message header** button in the details of the quarantined message (the button is always available).</span></span>

<span data-ttu-id="8e470-232"><sup>\*\*</sup> 不要将两个值都设置为 1。</span><span class="sxs-lookup"><span data-stu-id="8e470-232"><sup>\*\*</sup> Don't set both of these values to 1.</span></span> <span data-ttu-id="8e470-233">将一个设置为 1，另一个设置为 0，或同时设置为 0。</span><span class="sxs-lookup"><span data-stu-id="8e470-233">Set one to 1 and the other to 0, or set both to 0.</span></span>

<span data-ttu-id="8e470-234">此示例创建一个新的隔离策略名称 NoAccess，该名称分配"无访问权限"权限，如上表所述。</span><span class="sxs-lookup"><span data-stu-id="8e470-234">This example creates a new quarantine policy name NoAccess that assigns the No access permissions as described in the previous table.</span></span>

```powershell
New-QuarantineTag -Name NoAccess -EndUserQuarantinePermissionsValue 0
```

<span data-ttu-id="8e470-235">对于"受限访问权限"，请使用值 106。</span><span class="sxs-lookup"><span data-stu-id="8e470-235">For Limited access permissions, use the value 106.</span></span> <span data-ttu-id="8e470-236">对于"完全访问权限"，请使用值 236。</span><span class="sxs-lookup"><span data-stu-id="8e470-236">For Full access permissions, use the value 236.</span></span>

<span data-ttu-id="8e470-237">对于自定义权限，请使用上表获取与所需的权限对应的二进制值。</span><span class="sxs-lookup"><span data-stu-id="8e470-237">For custom permissions, use the previous table to get the binary value that corresponds to the permissions you want.</span></span> <span data-ttu-id="8e470-238">将二进制值转换为十进制值，并将小数值用于 _EndUserQuarantinePermissionsValue_ 参数。</span><span class="sxs-lookup"><span data-stu-id="8e470-238">Convert the binary value to a decimal value and use the decimal value for the _EndUserQuarantinePermissionsValue_ parameter.</span></span>

<span data-ttu-id="8e470-239">有关语法和参数的详细信息，请参阅 [New-QuarantineTag](/powershell/module/exchange/new-quarantinetag)。</span><span class="sxs-lookup"><span data-stu-id="8e470-239">For detailed syntax and parameter information, see [New-QuarantineTag](/powershell/module/exchange/new-quarantinetag).</span></span>

#### <a name="use-the-enduserquarantinepermissions-parameter"></a><span data-ttu-id="8e470-240">使用 EndUserQuarantinePermissions 参数</span><span class="sxs-lookup"><span data-stu-id="8e470-240">Use the EndUserQuarantinePermissions parameter</span></span>

<span data-ttu-id="8e470-241">若要使用 _EndUserQuarantinePermissionsValue_ 参数创建隔离策略，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="8e470-241">To create a quarantine policy using the _EndUserQuarantinePermissionsValue_ parameter, do the following steps:</span></span>

<span data-ttu-id="8e470-242">A.</span><span class="sxs-lookup"><span data-stu-id="8e470-242">A.</span></span> <span data-ttu-id="8e470-243">使用 **New-QuarantinePermissions** cmdlet 将隔离权限对象存储在变量中。</span><span class="sxs-lookup"><span data-stu-id="8e470-243">Store a quarantine permissions object in a variable using the **New-QuarantinePermissions** cmdlet.</span></span>

<p>

<span data-ttu-id="8e470-244">B.</span><span class="sxs-lookup"><span data-stu-id="8e470-244">B.</span></span> <span data-ttu-id="8e470-245">在 **New-QuarantineTag** 命令中将变量用作 _EndUserQuarantinePermissions_ 值。</span><span class="sxs-lookup"><span data-stu-id="8e470-245">Use the variable as the _EndUserQuarantinePermissions_ value in the **New-QuarantineTag** command.</span></span>

##### <a name="step-a-store-a-quarantine-permissions-object-in-a-variable"></a><span data-ttu-id="8e470-246">步骤 A：将隔离权限对象存储在变量中</span><span class="sxs-lookup"><span data-stu-id="8e470-246">Step A: Store a quarantine permissions object in a variable</span></span>

<span data-ttu-id="8e470-247">使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="8e470-247">Use the following syntax:</span></span>

```powershell
$<VariableName> = New-QuarantinePermissions [-PermissionToAllowSender <$true | $False>] [-PermissionToBlockSender <$true | $False>] [-PermissionToDelete <$true | $False>] [-PermissionToPreview <$true | $False>] [-PermissionToRelease <$true | $False>] [-PermissionToRequestRelease <$true | $False>]
```

<span data-ttu-id="8e470-248">任何未使用的参数的默认值都是 ，因此只需使用要将值 `$false` 设置为 的参数 `$true` 。</span><span class="sxs-lookup"><span data-stu-id="8e470-248">The default value for any unused parameters is `$false`, so you only need to use the parameters where you want to set value to `$true`.</span></span>

<span data-ttu-id="8e470-249">以下示例显示如何创建与预设权限组对应的权限对象：</span><span class="sxs-lookup"><span data-stu-id="8e470-249">The following examples show how to create permission objects that correspond to the preset permissions groups:</span></span>

- <span data-ttu-id="8e470-250">**无法访问**：</span><span class="sxs-lookup"><span data-stu-id="8e470-250">**No access**:</span></span>

  ```powershell
  $NoAccess = New-QuarantinePermissions
  ```

- <span data-ttu-id="8e470-251">**受限访问**：</span><span class="sxs-lookup"><span data-stu-id="8e470-251">**Limited access**:</span></span>

  ```powershell
  $LimitedAccess = New-QuarantinePermissions -PermissionToBlockSender $true -PermissionToDelete $true -PermissionToPreview $true -PermissionToRequestRelease $true
  ```

- <span data-ttu-id="8e470-252">**完全访问权限**：</span><span class="sxs-lookup"><span data-stu-id="8e470-252">**Full access**:</span></span>

  ```powershell
  $FullAccess = New-QuarantinePermissions -PermissionToAllowSender $true -PermissionToBlockSender $true -PermissionToDelete $true -PermissionToPreview $true -PermissionToRelease $true
  ```

<span data-ttu-id="8e470-253">To see the values that you've set， run the variable name as a command (for example， run the command `$NoAccess`) .</span><span class="sxs-lookup"><span data-stu-id="8e470-253">To see the values that you've set, run the variable name as a command (for example, run the command `$NoAccess`).</span></span>

<span data-ttu-id="8e470-254">对于自定义权限，不要同时将 _PermissionToRelease_ 和 _PermissionToRequestRelease_ 参数设置为 `$true` 。</span><span class="sxs-lookup"><span data-stu-id="8e470-254">For custom permissions, don't set both the _PermissionToRelease_ and _PermissionToRequestRelease_ parameters to `$true`.</span></span> <span data-ttu-id="8e470-255">将一个 `$true` 设置为 ，将另一个设置为 `$false` ，或者将两者都保留为 `$false` 。</span><span class="sxs-lookup"><span data-stu-id="8e470-255">Set one to `$true` and leave the other as `$false`, or leave both as `$false`.</span></span>

<span data-ttu-id="8e470-256">您还可以在创建之后、使用 **Set-QuarantinePermissions** cmdlet 使用之前修改现有 permissions 对象变量。</span><span class="sxs-lookup"><span data-stu-id="8e470-256">You can also modify an existing permissions object variable after you create but before you use it by using the **Set-QuarantinePermissions** cmdlet.</span></span>

<span data-ttu-id="8e470-257">有关语法和参数的详细信息，请参阅[New-QuarantinePermissions](/powershell/module/exchange/new-quarantinepermissions)和[Set-QuarantinePermissions。](/powershell/module/exchange/set-quarantinepermissions)</span><span class="sxs-lookup"><span data-stu-id="8e470-257">For detailed syntax and parameter information, see [New-QuarantinePermissions](/powershell/module/exchange/new-quarantinepermissions) and [Set-QuarantinePermissions](/powershell/module/exchange/set-quarantinepermissions).</span></span>

##### <a name="step-b-use-the-variable-in-the-new-quarantinetag-command"></a><span data-ttu-id="8e470-258">步骤 B：在命令中New-QuarantineTag变量</span><span class="sxs-lookup"><span data-stu-id="8e470-258">Step B: Use the variable in the New-QuarantineTag command</span></span>

<span data-ttu-id="8e470-259">创建权限对象并存储到变量中后，请使用以下 **New-QuarantineTag** 命令中的 _EndUserQuarantinePermission_ 参数值变量：</span><span class="sxs-lookup"><span data-stu-id="8e470-259">After you've created and stored the permissions object in a variable, use the variable for the _EndUserQuarantinePermission_ parameter value in the following **New-QuarantineTag** command:</span></span>

```powershell
New-QuarantineTag -Name "<UniqueName>" -EndUserQuarantinePermissions $<VariableName>
```

<span data-ttu-id="8e470-260">此示例使用上一步中介绍和创建的权限对象创建名为 LimitedAccess 的新 `$LimitedAccess` 隔离策略。</span><span class="sxs-lookup"><span data-stu-id="8e470-260">This example creates a new quarantine policy named LimitedAccess using the `$LimitedAccess` permissions object that was described and created in the previous step.</span></span>

```powershell
New-QuarantineTag -Name LimitedAccess -EndUserQuarantinePermissions $LimitedAccess
```

<span data-ttu-id="8e470-261">有关语法和参数的详细信息，请参阅 [New-QuarantineTag](/powershell/module/exchange/new-quarantinetag)。</span><span class="sxs-lookup"><span data-stu-id="8e470-261">For detailed syntax and parameter information, see [New-QuarantineTag](/powershell/module/exchange/new-quarantinetag).</span></span>

## <a name="step-2-assign-a-quarantine-policy-to-supported-features"></a><span data-ttu-id="8e470-262">步骤 2：将隔离策略分配给支持的功能</span><span class="sxs-lookup"><span data-stu-id="8e470-262">Step 2: Assign a quarantine policy to supported features</span></span>

<span data-ttu-id="8e470-263">在 _可_ 自动隔离邮件或文件的 (或作为可配置操作) ，您可以将隔离策略分配给可用的隔离操作。</span><span class="sxs-lookup"><span data-stu-id="8e470-263">In _supported_ protection features that quarantine messages or files (automatically or as a configurable action), you can assign a quarantine policy to the available quarantine actions.</span></span> <span data-ttu-id="8e470-264">下表介绍了隔离邮件的功能和隔离策略的可用性：</span><span class="sxs-lookup"><span data-stu-id="8e470-264">Features that quarantine messages and the availability of quarantine policies are described in the following table:</span></span>

<br>

****

|<span data-ttu-id="8e470-265">功能</span><span class="sxs-lookup"><span data-stu-id="8e470-265">Feature</span></span>|<span data-ttu-id="8e470-266">支持隔离策略？</span><span class="sxs-lookup"><span data-stu-id="8e470-266">Quarantine policies supported?</span></span>|<span data-ttu-id="8e470-267">使用的默认隔离策略</span><span class="sxs-lookup"><span data-stu-id="8e470-267">Default quarantine policies used</span></span>|
|---|:---:|---|
|<span data-ttu-id="8e470-268">[反垃圾邮件策略](configure-your-spam-filter-policies.md)：</span><span class="sxs-lookup"><span data-stu-id="8e470-268">[Anti-spam policies](configure-your-spam-filter-policies.md):</span></span> <ul><li><span data-ttu-id="8e470-269">**Spam** (_SpamAction_) </span><span class="sxs-lookup"><span data-stu-id="8e470-269">**Spam** (_SpamAction_)</span></span></li><li><span data-ttu-id="8e470-270">**高可信度垃圾邮件** (_HighConfidenceSpamAction_) </span><span class="sxs-lookup"><span data-stu-id="8e470-270">**High confidence spam** (_HighConfidenceSpamAction_)</span></span></li><li><span data-ttu-id="8e470-271">**Phishing** (_PhishSpamAction_) </span><span class="sxs-lookup"><span data-stu-id="8e470-271">**Phishing** (_PhishSpamAction_)</span></span></li><li><span data-ttu-id="8e470-272">**高可信度网络钓鱼** (_HighConfidencePhishAction_) </span><span class="sxs-lookup"><span data-stu-id="8e470-272">**High confidence phishing** (_HighConfidencePhishAction_)</span></span></li><li><span data-ttu-id="8e470-273">**批量** (_BulkSpamAction_) </span><span class="sxs-lookup"><span data-stu-id="8e470-273">**Bulk** (_BulkSpamAction_)</span></span></li></ul>|<span data-ttu-id="8e470-274">是</span><span class="sxs-lookup"><span data-stu-id="8e470-274">Yes</span></span>|<ul><li><span data-ttu-id="8e470-275">DefaultSpamTag (完全访问权限) </span><span class="sxs-lookup"><span data-stu-id="8e470-275">DefaultSpamTag (Full access)</span></span></li><li><span data-ttu-id="8e470-276">DefaultHighConfSpamTag (完全访问权限) </span><span class="sxs-lookup"><span data-stu-id="8e470-276">DefaultHighConfSpamTag (Full access)</span></span></li><li><span data-ttu-id="8e470-277">DefaultPhishTag (完全访问权限) </span><span class="sxs-lookup"><span data-stu-id="8e470-277">DefaultPhishTag (Full access)</span></span></li><li><span data-ttu-id="8e470-278">DefaultHighConfPhishTag (无法访问) </span><span class="sxs-lookup"><span data-stu-id="8e470-278">DefaultHighConfPhishTag (No access)</span></span></li><li><span data-ttu-id="8e470-279">DefaultBulkTag (完全访问权限) </span><span class="sxs-lookup"><span data-stu-id="8e470-279">DefaultBulkTag (Full access)</span></span></li></ul>
|<span data-ttu-id="8e470-280">防钓鱼策略：</span><span class="sxs-lookup"><span data-stu-id="8e470-280">Anti-phishing policies:</span></span> <ul><li><span data-ttu-id="8e470-281">[](set-up-anti-phishing-policies.md#spoof-settings) _AuthenticationFailAction (反欺骗智能_) </span><span class="sxs-lookup"><span data-stu-id="8e470-281">[Spoof intelligence protection](set-up-anti-phishing-policies.md#spoof-settings) (_AuthenticationFailAction_)</span></span></li><li><span data-ttu-id="8e470-282">[模拟保护](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)：<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="8e470-282">[Impersonation protection](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365):<sup>\*</sup></span></span> <ul><li><span data-ttu-id="8e470-283">**如果邮件被检测为** _TargetedUserProtectionAction_ (模拟) </span><span class="sxs-lookup"><span data-stu-id="8e470-283">**If message is detected as an impersonated user** (_TargetedUserProtectionAction_)</span></span></li><li><span data-ttu-id="8e470-284">**如果邮件被检测为** _TargetedDomainProtectionAction_ (模拟) </span><span class="sxs-lookup"><span data-stu-id="8e470-284">**If message is detected as an impersonated domain** (_TargetedDomainProtectionAction_)</span></span></li><li><span data-ttu-id="8e470-285">**如果邮箱智能检测到并模拟** _MailboxIntelligenceProtectionAction (MailboxIntelligenceProtectionAction_) </span><span class="sxs-lookup"><span data-stu-id="8e470-285">**If mailbox intelligence detects and impersonated user** (_MailboxIntelligenceProtectionAction_)</span></span></li></ul></li></ul></ul>|<span data-ttu-id="8e470-286">否</span><span class="sxs-lookup"><span data-stu-id="8e470-286">No</span></span>|<span data-ttu-id="8e470-287">不适用</span><span class="sxs-lookup"><span data-stu-id="8e470-287">n/a</span></span>|
|<span data-ttu-id="8e470-288">[反恶意软件策略](configure-anti-malware-policies.md)：始终隔离所有检测到的邮件。</span><span class="sxs-lookup"><span data-stu-id="8e470-288">[Anti-malware policies](configure-anti-malware-policies.md): All detected messages are always quarantined.</span></span>|<span data-ttu-id="8e470-289">否</span><span class="sxs-lookup"><span data-stu-id="8e470-289">No</span></span>|<span data-ttu-id="8e470-290">不适用</span><span class="sxs-lookup"><span data-stu-id="8e470-290">n/a</span></span>|
|[<span data-ttu-id="8e470-291">用于 SharePoint、OneDrive 和 Microsoft Teams 的安全附件</span><span class="sxs-lookup"><span data-stu-id="8e470-291">Safe Attachments for SharePoint, OneDrive, and Microsoft Teams</span></span>](mdo-for-spo-odb-and-teams.md)|<span data-ttu-id="8e470-292">否</span><span class="sxs-lookup"><span data-stu-id="8e470-292">No</span></span>|<span data-ttu-id="8e470-293">不适用</span><span class="sxs-lookup"><span data-stu-id="8e470-293">n/a</span></span>|
|<span data-ttu-id="8e470-294">[邮件流规则](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (操作) 传输规则： **将** 邮件发送到托管隔离邮箱 (_隔离_) 。</span><span class="sxs-lookup"><span data-stu-id="8e470-294">[Mail flow rules](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (also known as transport rules) with the action: **Deliver the message to the hosted quarantine** (_Quarantine_).</span></span>|<span data-ttu-id="8e470-295">否</span><span class="sxs-lookup"><span data-stu-id="8e470-295">No</span></span>|<span data-ttu-id="8e470-296">不适用</span><span class="sxs-lookup"><span data-stu-id="8e470-296">n/a</span></span>|
|

<span data-ttu-id="8e470-297"><sup>\*</sup>模拟保护设置仅在 Microsoft Defender for Office 365 中的反网络钓鱼策略中Office 365。</span><span class="sxs-lookup"><span data-stu-id="8e470-297"><sup>\*</sup> Impersonation protection settings are available only in anti-phishing policies in Microsoft Defender for Office 365.</span></span>

<span data-ttu-id="8e470-298">如果您对默认隔离策略提供的最终用户权限满意，则无需执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="8e470-298">If you're happy with the end-user permissions that are provided by the default quarantine policies, you don't need to do anything.</span></span> <span data-ttu-id="8e470-299">如果要自定义最终用户功能 (最终用户垃圾邮件) 或隔离邮件详细信息中的可用按钮，您可以分配自定义隔离策略。</span><span class="sxs-lookup"><span data-stu-id="8e470-299">If you want to customize the end-user capabilities (available buttons) in end-user spam notifications or in quarantined message details, you can assign a custom quarantine policy.</span></span>

### <a name="assign-quarantine-policies-in-anti-spam-policies-in-the-microsoft-365-defender-portal"></a><span data-ttu-id="8e470-300">在门户中的反垃圾邮件策略中分配Microsoft 365 Defender策略</span><span class="sxs-lookup"><span data-stu-id="8e470-300">Assign quarantine policies in anti-spam policies in the Microsoft 365 Defender portal</span></span>

<span data-ttu-id="8e470-301">有关创建和修改反垃圾邮件策略的完整说明，请参阅在 [EOP 中配置反垃圾邮件策略](configure-your-spam-filter-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="8e470-301">Full instructions for creating and modifying anti-spam policies are described in [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

1. <span data-ttu-id="8e470-302">In the Microsoft 365 Defender portal， go to **Email & collaboration** Policies & \> **rules** \> **Policies** section \> **Anti-spam**.</span><span class="sxs-lookup"><span data-stu-id="8e470-302">In the Microsoft 365 Defender portal, go to **Email & collaboration** \> **Policies & rules** \> **Policies** section \> **Anti-spam**.</span></span> <span data-ttu-id="8e470-303">或者，打开 <https://security.microsoft.com/antispam> 。</span><span class="sxs-lookup"><span data-stu-id="8e470-303">Or, open <https://security.microsoft.com/antispam>.</span></span>

2. <span data-ttu-id="8e470-304">在 **"反垃圾邮件策略"** 页上，执行下列步骤之一：</span><span class="sxs-lookup"><span data-stu-id="8e470-304">On the **Anti-spam policies** page, do one of the following steps:</span></span>
   - <span data-ttu-id="8e470-305">查找并选择现有的 **入站** 反垃圾邮件策略。</span><span class="sxs-lookup"><span data-stu-id="8e470-305">Find and select an existing **inbound** anti-spam policy.</span></span>
   - <span data-ttu-id="8e470-306">创建新的 **入站** 反垃圾邮件策略。</span><span class="sxs-lookup"><span data-stu-id="8e470-306">Create a new **inbound** anti-spam policy.</span></span>

3. <span data-ttu-id="8e470-307">采取以下步骤之一：</span><span class="sxs-lookup"><span data-stu-id="8e470-307">Do one of the following steps:</span></span>
   - <span data-ttu-id="8e470-308">**编辑现有的反垃圾邮件策略**：在策略详细信息飞出控件中，转到"**操作**"部分，然后单击"编辑 **操作"。**</span><span class="sxs-lookup"><span data-stu-id="8e470-308">**Edit existing anti-spam policy**: In the policy details flyout, go to the **Actions** section and then click **Edit actions**.</span></span>
   - <span data-ttu-id="8e470-309">**创建新的反垃圾邮件策略**：在新建策略向导中，转到" **操作"** 页面。</span><span class="sxs-lookup"><span data-stu-id="8e470-309">**Create new anti-spam policy**: In the new policy wizard, go to the **Actions** page.</span></span>

4. <span data-ttu-id="8e470-310">在" **操作"** 页上。</span><span class="sxs-lookup"><span data-stu-id="8e470-310">On the **Actions** page.</span></span> <span data-ttu-id="8e470-311">每个具有"隔离邮件 **"操作** 裁定还将具有" **选择** 隔离策略"框，供你选择相应的隔离策略。</span><span class="sxs-lookup"><span data-stu-id="8e470-311">every verdict that has the **Quarantine message** action will also have the **Select quarantine policy** box for you to select a corresponding quarantine policy.</span></span>

   <span data-ttu-id="8e470-312">**注意**：创建新策略时，空白选择隔离策略值表示已使用该裁定的默认隔离策略。</span><span class="sxs-lookup"><span data-stu-id="8e470-312">**Note**: When you create a new policy, a blank **Select quarantine policy** value indicates the default quarantine policy for that verdict is used.</span></span> <span data-ttu-id="8e470-313">以后编辑策略时，空白值将替换为实际的默认隔离策略名称，如上表所述。</span><span class="sxs-lookup"><span data-stu-id="8e470-313">When you later edit the policy, the blank values are replaced by the actual default quarantine policy names as described in the previous table.</span></span>

   ![反垃圾邮件策略中的隔离策略选择](../../media/quarantine-tags-in-anti-spam-policies.png)

5. <span data-ttu-id="8e470-315">完成后，单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="8e470-315">When you're finished, click **Save**.</span></span>

#### <a name="assign-quarantine-policies-in-anti-spam-policies-in-powershell"></a><span data-ttu-id="8e470-316">在 PowerShell 中的反垃圾邮件策略中分配隔离策略</span><span class="sxs-lookup"><span data-stu-id="8e470-316">Assign quarantine policies in anti-spam policies in PowerShell</span></span>

<span data-ttu-id="8e470-317">如果您更希望使用 PowerShell 在反垃圾邮件策略中分配隔离策略，请连接到 Exchange Online PowerShell 或 Exchange Online Protection PowerShell 并使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="8e470-317">If you'd rather use PowerShell to assign quarantine policies in anti-spam policies, connect to Exchange Online PowerShell or Exchange Online Protection PowerShell and use the following syntax:</span></span>

```powershell
<New-HostedContentFilterPolicy -Name "<Unique name>" | Set-HostedContentFilterPolicy -Identity "<Policy name>">  [-SpamAction Quarantine] [-SpamQuarantineTag <QuarantineTagName>] [-HighConfidenceSpamAction Quarantine] [-HighConfidenceSpamQuarantineTag <QuarantineTagName>] [-PhishSpamAction Quarantine] [-PhishQuarantineTag <QuarantineTagName>] [-HighConfidencePhishQuarantineTag <QuarantineTagName>] [-BulkSpamAction Quarantine] [-BulkQuarantineTag <QuarantineTagName>] ...
```

<span data-ttu-id="8e470-318">**注意**：</span><span class="sxs-lookup"><span data-stu-id="8e470-318">**Notes**:</span></span>

- <span data-ttu-id="8e470-319">_HighConfidencePhishAction_ 参数的默认值为 Quarantine，因此无需设置新反垃圾邮件策略中的高可信度网络钓鱼检测的隔离操作。</span><span class="sxs-lookup"><span data-stu-id="8e470-319">The default value for the _HighConfidencePhishAction_ parameter is Quarantine, so you don't need to set the Quarantine action for high confidence phishing detections in new anti-spam policies.</span></span> <span data-ttu-id="8e470-320">对于新的或现有的反垃圾邮件策略中的所有其他垃圾邮件筛选裁定，隔离策略仅在操作值为 Quarantine 时有效。</span><span class="sxs-lookup"><span data-stu-id="8e470-320">For all other spam filtering verdicts in new or existing anti-spam policies, the quarantine policy is only effective if the action value is Quarantine.</span></span> <span data-ttu-id="8e470-321">若要查看现有反垃圾邮件策略中的操作值，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="8e470-321">To see the action values in existing anti-spam policies, run the following command:</span></span>

  ```powershell
  Get-HostedContentFilterPolicy | Format-Table Name,*SpamAction,HighConfidencePhishAction
  ```

  <span data-ttu-id="8e470-322">有关默认操作值以及 Standard 和 Strict 的建议操作值的信息，请参阅 [EOP 反垃圾邮件策略设置](recommended-settings-for-eop-and-office365.md#eop-anti-spam-policy-settings)。</span><span class="sxs-lookup"><span data-stu-id="8e470-322">For information about the default action values and the recommended action values for Standard and Strict, see [EOP anti-spam policy settings](recommended-settings-for-eop-and-office365.md#eop-anti-spam-policy-settings).</span></span>

- <span data-ttu-id="8e470-323">没有相应的隔离策略参数的垃圾邮件筛选裁定意味着使用该 [裁定的默认](#step-2-assign-a-quarantine-policy-to-supported-features) 隔离策略。</span><span class="sxs-lookup"><span data-stu-id="8e470-323">A spam filtering verdict without a corresponding quarantine policy parameter means the [default quarantine policy](#step-2-assign-a-quarantine-policy-to-supported-features) for that verdict is used.</span></span>

  <span data-ttu-id="8e470-324">如果希望更改隔离邮件的默认最终用户功能，只需将默认隔离策略替换为自定义隔离策略。</span><span class="sxs-lookup"><span data-stu-id="8e470-324">You only need to replace a default quarantine policy with a custom quarantine policy if you want to change the default end-user capabilities on quarantined messages.</span></span>

- <span data-ttu-id="8e470-325">PowerShell 中的新反垃圾邮件策略需要使用 **New-HostedContentFilterPolicy** cmdlet 和新的垃圾邮件筛选器规则 (收件人筛选器) cmdlet 创建垃圾邮件筛选策略 (设置) 。 </span><span class="sxs-lookup"><span data-stu-id="8e470-325">A new anti-spam policy in PowerShell requires a spam filter policy (settings) using the **New-HostedContentFilterPolicy** cmdlet and a new spam filter rule (recipient filters) using the **New-HostedContentFilterRule** cmdlet.</span></span> <span data-ttu-id="8e470-326">有关说明，请参阅 [使用 PowerShell 创建反垃圾邮件策略](configure-your-spam-filter-policies.md#use-powershell-to-create-anti-spam-policies)。</span><span class="sxs-lookup"><span data-stu-id="8e470-326">For instructions, see [Use PowerShell to create anti-spam policies](configure-your-spam-filter-policies.md#use-powershell-to-create-anti-spam-policies).</span></span>

<span data-ttu-id="8e470-327">本示例将创建一个名为"Research Department"的新垃圾邮件筛选策略，并具有以下设置：</span><span class="sxs-lookup"><span data-stu-id="8e470-327">This example creates a new spam filter policy named Research Department with the following settings:</span></span>

- <span data-ttu-id="8e470-328">所有垃圾邮件筛选裁定的操作均设置为"隔离"。</span><span class="sxs-lookup"><span data-stu-id="8e470-328">The action for all spam filtering verdicts is set to Quarantine.</span></span>
- <span data-ttu-id="8e470-329">分配"无访问权限"的名为 NoAccess的自定义隔离策略将替换默认情况下尚未分配"无访问权限"的任何默认隔离策略。</span><span class="sxs-lookup"><span data-stu-id="8e470-329">The custom quarantine policy named NoAccess that assigns **No access** permissions replaces any default quarantine policies that don't already assign **No access** permissions by default.</span></span>

```powershell
New-HostedContentFilterPolicy -Name Research Department -SpamAction Quarantine -SpamQuarantineTag NoAccess -HighConfidenceSpamAction Quarantine -HighConfidenceSpamQuarantineTag NoAction -PhishSpamAction Quarantine -PhishQuarantineTag NoAction -BulkSpamAction Quarantine -BulkQuarantineTag NoAccess
```

<span data-ttu-id="8e470-330">若要详细了解语法和参数，请参阅 [New-HostedContentFilterPolicy](/powershell/module/exchange/new-hostedcontentfilterpolicy)。</span><span class="sxs-lookup"><span data-stu-id="8e470-330">For detailed syntax and parameter information, see [New-HostedContentFilterPolicy](/powershell/module/exchange/new-hostedcontentfilterpolicy).</span></span>

<span data-ttu-id="8e470-331">此示例修改名为 Human Resources 的现有垃圾邮件筛选器策略。</span><span class="sxs-lookup"><span data-stu-id="8e470-331">This example modifies the existing spam filter policy named Human Resources.</span></span> <span data-ttu-id="8e470-332">垃圾邮件隔离裁定的操作设置为"隔离"，并分配名为 NoAccess 的自定义隔离策略。</span><span class="sxs-lookup"><span data-stu-id="8e470-332">The action for the spam quarantine verdict is set to Quarantine, and the custom quarantine policy named NoAccess is assigned.</span></span>

```powershell
Set-HostedContentFilterPolicy -Identity "Human Resources" -SpamAction Quarantine -SpamQuarantineTag NoAccess
```

<span data-ttu-id="8e470-333">若要详细了解语法和参数，请参阅 [Set-HostedContentFilterPolicy](/powershell/module/exchange/set-hostedcontentfilterpolicy)。</span><span class="sxs-lookup"><span data-stu-id="8e470-333">For detailed syntax and parameter information, see [Set-HostedContentFilterPolicy](/powershell/module/exchange/set-hostedcontentfilterpolicy).</span></span>

## <a name="configure-global-quarantine-notification-settings-in-the-microsoft-365-defender-portal"></a><span data-ttu-id="8e470-334">在门户中配置全局隔离Microsoft 365 Defender设置</span><span class="sxs-lookup"><span data-stu-id="8e470-334">Configure global quarantine notification settings in the Microsoft 365 Defender portal</span></span>

<span data-ttu-id="8e470-335">隔离策略的全局设置允许您自定义发送到已隔离邮件收件人的最终用户垃圾邮件通知。</span><span class="sxs-lookup"><span data-stu-id="8e470-335">The global settings for quarantine policies allow you to customize the end-user spam notifications that are sent to recipients of messages that were quarantined.</span></span> <span data-ttu-id="8e470-336">有关这些通知详细信息，请参阅 [最终用户垃圾邮件通知](use-spam-notifications-to-release-and-report-quarantined-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="8e470-336">For more information about these notifications, see [End-user spam notifications](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span></span>

1. <span data-ttu-id="8e470-337">在 Microsoft 365 Defender 门户中，转到"电子邮件&协作威胁策略"部分"**隔离** 策略"， \>  \>  \> 然后选择"隔离 **策略"。**</span><span class="sxs-lookup"><span data-stu-id="8e470-337">In the Microsoft 365 Defender portal, go to **Email & collaboration** \>**Threat policies** \> **Rules** section \> **Quarantine policies** and then select **Quarantine policies**.</span></span>

2. <span data-ttu-id="8e470-338">在"**隔离策略"页上**，选择"**全局设置"。**</span><span class="sxs-lookup"><span data-stu-id="8e470-338">On the **Quarantine policy** page, select **Global settings**.</span></span>

3. <span data-ttu-id="8e470-339">在打开 **的"隔离** 通知设置"飞出中，配置以下部分或所有设置：</span><span class="sxs-lookup"><span data-stu-id="8e470-339">In the **Quarantine notification settings** flyout that opens, configure some or all of the following settings:</span></span>

   - <span data-ttu-id="8e470-340">**显示名称**：自定义显示名称垃圾邮件通知中使用的发件人地址。</span><span class="sxs-lookup"><span data-stu-id="8e470-340">**Display name**: Customize the sender's display name that's used in end-user spam notifications.</span></span>

     <span data-ttu-id="8e470-341">对于已添加的每种语言，选择第二种语言框中的语言 (不要单击 X) 请在"显示名称"框中输入您需要 **的文本值。**</span><span class="sxs-lookup"><span data-stu-id="8e470-341">For each language that you've added, select the language in the second language box (don't click on the X) and enter the text value you want in the **Display name** box.</span></span>

     <span data-ttu-id="8e470-342">以下屏幕截图显示了最终用户显示名称中的自定义邮件：</span><span class="sxs-lookup"><span data-stu-id="8e470-342">The following screenshot shows the customized display name in an end-user spam notification:</span></span>

     ![自定义发件人显示名称最终用户垃圾邮件通知中](../../media/quarantine-tags-esn-customization-display-name.png)

   - <span data-ttu-id="8e470-344">**免责声明**：将自定义免责声明添加到最终用户垃圾邮件通知的底部。</span><span class="sxs-lookup"><span data-stu-id="8e470-344">**Disclaimer**: Add a custom disclaimer to the bottom of end-user spam notifications.</span></span> <span data-ttu-id="8e470-345">您组织的本地化文本 **（免责声明：）** 始终先包含，后跟您指定的文本。</span><span class="sxs-lookup"><span data-stu-id="8e470-345">The localized text, **A disclaimer from your organization:** is always included first, followed by the text you specify.</span></span>

     <span data-ttu-id="8e470-346">对于已添加的每种语言，选择第二种语言框中 (不要单击"X) "，在"免责声明"框中输入 **您需要的文本值** 。</span><span class="sxs-lookup"><span data-stu-id="8e470-346">For each language that you've added, select the language in the second language box  (don't click the X) and enter the text value you want in the **Disclaimer** box.</span></span>

     <span data-ttu-id="8e470-347">以下屏幕截图显示了最终用户垃圾邮件通知中的自定义免责声明：</span><span class="sxs-lookup"><span data-stu-id="8e470-347">The following screenshot shows the customized disclaimer in an end-user spam notification:</span></span>

     ![最终用户垃圾邮件通知底部的自定义免责声明](../../media/quarantine-tags-esn-customization-disclaimer.png)

   - <span data-ttu-id="8e470-349">**选择语言**：最终用户垃圾邮件通知已根据收件人的语言设置进行本地化。</span><span class="sxs-lookup"><span data-stu-id="8e470-349">**Choose language**: End-user spam notifications are already localized based on the recipient's language settings.</span></span> <span data-ttu-id="8e470-350">您可以为"显示名称"和"免责声明"值指定不同语言的 **自定义** 文本。</span><span class="sxs-lookup"><span data-stu-id="8e470-350">You can specify customized text in different languages for the **Display name** and **Disclaimer** values.</span></span>

     <span data-ttu-id="8e470-351">至少从第一种语言框中选择一种语言， **然后单击添加**。</span><span class="sxs-lookup"><span data-stu-id="8e470-351">Select at least one language from the first language box and then click **Add**.</span></span> <span data-ttu-id="8e470-352">可以通过单击每种语言后的" **添加** "来选择多种语言。</span><span class="sxs-lookup"><span data-stu-id="8e470-352">You can select multiple languages by clicking **Add** after each one.</span></span> <span data-ttu-id="8e470-353">部分语言框显示你选择的所有语言：</span><span class="sxs-lookup"><span data-stu-id="8e470-353">A section language box shows all of the languages that you've selected:</span></span>

     ![隔离策略的全局隔离通知设置中第二种语言框中选定的语言](../../media/quarantine-tags-esn-customization-selected-languages.png)

   - <span data-ttu-id="8e470-355">**使用我的公司徽标**：选择此选项可替换最终用户垃圾邮件通知顶部使用的默认 Microsoft 徽标。</span><span class="sxs-lookup"><span data-stu-id="8e470-355">**Use my company logo**: Select this option to replace the default Microsoft logo that's use at the top of end-user spam notifications.</span></span> <span data-ttu-id="8e470-356">在这样做之前，你需要按照自定义组织的自定义Microsoft 365[主题](../../admin/setup/customize-your-organization-theme.md)中的说明上载自定义徽标。</span><span class="sxs-lookup"><span data-stu-id="8e470-356">Before you do this, you need to follow the instructions in [Customize the Microsoft 365 theme for your organization](../../admin/setup/customize-your-organization-theme.md) to upload your custom logo.</span></span>

     <span data-ttu-id="8e470-357">以下屏幕截图显示了最终用户垃圾邮件通知中的自定义徽标：</span><span class="sxs-lookup"><span data-stu-id="8e470-357">The following screenshot shows a custom logo in an end-user spam notification:</span></span>

     ![最终用户垃圾邮件通知中的自定义徽标](../../media/quarantine-tags-esn-customization-logo.png)

## <a name="view-quarantine-policies-in-the-microsoft-365-defender-portal"></a><span data-ttu-id="8e470-359">在门户中查看隔离Microsoft 365 Defender策略</span><span class="sxs-lookup"><span data-stu-id="8e470-359">View quarantine policies in the Microsoft 365 Defender portal</span></span>

1. <span data-ttu-id="8e470-360">在 Microsoft 365 Defender 门户中，转到"电子邮件&协作威胁策略"部分"**隔离** 策略"， \>  \>  \> 然后选择"隔离 **策略"。**</span><span class="sxs-lookup"><span data-stu-id="8e470-360">In the Microsoft 365 Defender portal, go to **Email & collaboration** \>**Threat policies** \> **Rules** section \> **Quarantine policies** and then select **Quarantine policies**.</span></span>

2. <span data-ttu-id="8e470-361">"**隔离策略**"页按名称和上次更新日期 **显示策略** 列表。</span><span class="sxs-lookup"><span data-stu-id="8e470-361">The **Quarantine policy** page shows the list of policies by **Name** and **Last updated** date.</span></span>

3. <span data-ttu-id="8e470-362">若要查看内置或自定义隔离策略的设置，请通过单击名称从列表中选择隔离策略。</span><span class="sxs-lookup"><span data-stu-id="8e470-362">To view the settings of built-in or custom quarantine policies, select the quarantine policy from the list by clicking on the name.</span></span>

4. <span data-ttu-id="8e470-363">若要查看全局设置，请单击" **全局设置"**</span><span class="sxs-lookup"><span data-stu-id="8e470-363">To view the global settings, click **Global settings**</span></span>

### <a name="view-quarantine-policies-in-powershell"></a><span data-ttu-id="8e470-364">在 PowerShell 中查看隔离策略</span><span class="sxs-lookup"><span data-stu-id="8e470-364">View quarantine policies in PowerShell</span></span>

<span data-ttu-id="8e470-365">如果更希望使用 PowerShell 查看隔离策略，请执行以下步骤之一：</span><span class="sxs-lookup"><span data-stu-id="8e470-365">If you'd rather use PowerShell to view quarantine policies, do any of the following steps:</span></span>

- <span data-ttu-id="8e470-366">若要查看所有内置或自定义策略的摘要列表，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="8e470-366">To view a summary list of all built-in or custom policies, run the following command:</span></span>

  ```powershell
  Get-QuarantineTag | Format-Table Name
  ```

- <span data-ttu-id="8e470-367">若要查看内置或自定义隔离策略的设置，请将 替换为隔离策略的名称，然后 \<QuarantinePolicyName\> 运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="8e470-367">To view the settings of built-in or custom quarantine policies, replace \<QuarantinePolicyName\> with the name of the quarantine policy, and run the following command:</span></span>

  ```powershell
  Get-QuarantineTag -Identity "<QuarantinePolicyName>"
  ```

- <span data-ttu-id="8e470-368">若要查看全局设置，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="8e470-368">To view the global settings, run the following command:</span></span>

  ```powershell
  Get-QuarantineTag -QuarantineTagType GlobalQuarantineTag
  ```

<span data-ttu-id="8e470-369">若要详细了解语法和参数，请参阅 [Get-HostedContentFilterPolicy](/powershell/module/exchange/get-hostedcontentfilterpolicy)。</span><span class="sxs-lookup"><span data-stu-id="8e470-369">For detailed syntax and parameter information, see [Get-HostedContentFilterPolicy](/powershell/module/exchange/get-hostedcontentfilterpolicy).</span></span>

## <a name="modify-quarantine-policies-in-the-microsoft-365-defender-portal"></a><span data-ttu-id="8e470-370">修改 Microsoft 365 Defender 门户中的隔离策略</span><span class="sxs-lookup"><span data-stu-id="8e470-370">Modify quarantine policies in the Microsoft 365 Defender portal</span></span>

1. <span data-ttu-id="8e470-371">在 Microsoft 365 Defender 门户中，转到"电子邮件&协作威胁策略"部分"**隔离** 策略"， \>  \>  \> 然后选择"隔离 **策略"。**</span><span class="sxs-lookup"><span data-stu-id="8e470-371">In the Microsoft 365 Defender portal, go to **Email & collaboration** \>**Threat policies** \> **Rules** section \> **Quarantine policies** and then select **Quarantine policies**.</span></span>

2. <span data-ttu-id="8e470-372">在" **隔离策略"** 页上，通过单击名称选择策略。</span><span class="sxs-lookup"><span data-stu-id="8e470-372">On the **Quarantine policies** page, select the policy by clicking on the name.</span></span>

3. <span data-ttu-id="8e470-373">选择该策略后，单击出现的"编辑 ![ 策略"图标 ](../../media/m365-cc-sc-edit-icon.png) "编辑策略图标"。</span><span class="sxs-lookup"><span data-stu-id="8e470-373">After you select the policy, click the ![Edit policy icon](../../media/m365-cc-sc-edit-icon.png) **Edit policy** icon that appears.</span></span>

4. <span data-ttu-id="8e470-374">打开 **的编辑** 策略向导几乎与"新建策略"向导相同，如本文前面在 Microsoft 365 Defender [门户](#step-1-create-quarantine-policies-in-the-microsoft-365-defender-portal)创建隔离策略部分所述。</span><span class="sxs-lookup"><span data-stu-id="8e470-374">The **Edit policy** wizard that opens is virtually identical to the **New policy** wizard as described in the [Create quarantine policies in the Microsoft 365 Defender portal](#step-1-create-quarantine-policies-in-the-microsoft-365-defender-portal) section earlier in this article.</span></span>

   <span data-ttu-id="8e470-375">主要区别在于：无法重命名现有策略。</span><span class="sxs-lookup"><span data-stu-id="8e470-375">The main difference is: you can't rename an existing policy.</span></span>

5. <span data-ttu-id="8e470-376">完成策略修改后，转到摘要页，**然后单击提交**。 </span><span class="sxs-lookup"><span data-stu-id="8e470-376">When you're finished modifying the policy, go to the **Summary** page and click **Submit**.</span></span>

### <a name="modify-quarantine-policies-in-powershell"></a><span data-ttu-id="8e470-377">在 PowerShell 中修改隔离策略</span><span class="sxs-lookup"><span data-stu-id="8e470-377">Modify quarantine policies in PowerShell</span></span>

<span data-ttu-id="8e470-378">如果您更希望使用 PowerShell 修改自定义隔离策略，请将 替换为隔离策略 \<QuarantinePolicyName\> 的名称，并使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="8e470-378">If you'd rather use PowerShell to modify a custom quarantine policy, replace \<QuarantinePolicyName\> with the name of the quarantine policy, and use the following syntax:</span></span>

```powershell
Set-QuarantineTag -Identity "<QuarantinePolicyName>" [Settings]
```

<span data-ttu-id="8e470-379">可用的设置与本文前面介绍的创建隔离策略的设置相同。</span><span class="sxs-lookup"><span data-stu-id="8e470-379">The available settings are the same as described for creating quarantine policies earlier in this article.</span></span>

<span data-ttu-id="8e470-380">有关语法和参数的详细信息，请参阅 [Set-QuarantineTag](/powershell/module/exchange/set-quarantinetag)。</span><span class="sxs-lookup"><span data-stu-id="8e470-380">For detailed syntax and parameter information, see [Set-QuarantineTag](/powershell/module/exchange/set-quarantinetag).</span></span>

## <a name="remove-quarantine-policies-in-the-microsoft-365-defender-portal"></a><span data-ttu-id="8e470-381">删除 Microsoft 365 Defender 门户中的隔离策略</span><span class="sxs-lookup"><span data-stu-id="8e470-381">Remove quarantine policies in the Microsoft 365 Defender portal</span></span>

<span data-ttu-id="8e470-382">**注意**：</span><span class="sxs-lookup"><span data-stu-id="8e470-382">**Notes**:</span></span>

- <span data-ttu-id="8e470-383">无法删除内置隔离策略。</span><span class="sxs-lookup"><span data-stu-id="8e470-383">You can't remove built-in quarantine policies.</span></span>
- <span data-ttu-id="8e470-384">在删除自定义隔离策略之前，请验证该策略是否未使用。</span><span class="sxs-lookup"><span data-stu-id="8e470-384">Before you remove a custom quarantine policy, verify that it's not being used.</span></span> <span data-ttu-id="8e470-385">例如，在 PowerShell 中运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="8e470-385">For example, run the following command in PowerShell:</span></span>

  ```powershell
  Get-HostedContentFilterPolicy | Format-List Name,*QuarantineTag
  ```

  <span data-ttu-id="8e470-386">如果使用隔离策略， [请替换已分配的隔离策略](#step-2-assign-a-quarantine-policy-to-supported-features) ，然后再删除它。</span><span class="sxs-lookup"><span data-stu-id="8e470-386">If the quarantine policy is being used, [replace the assigned quarantine policy](#step-2-assign-a-quarantine-policy-to-supported-features) before you remove it.</span></span>

1. <span data-ttu-id="8e470-387">在 Microsoft 365 Defender 门户中，转到"电子邮件&协作威胁策略"部分"**隔离** 策略"， \>  \>  \> 然后选择"隔离 **策略"。**</span><span class="sxs-lookup"><span data-stu-id="8e470-387">In the Microsoft 365 Defender portal, go to **Email & collaboration** \>**Threat policies** \> **Rules** section \> **Quarantine policies** and then select **Quarantine policies**.</span></span>

2. <span data-ttu-id="8e470-388">在" **隔离策略** "页上，单击名称，选择要删除的自定义隔离策略。</span><span class="sxs-lookup"><span data-stu-id="8e470-388">On the **Quarantine policy** page, select the custom quarantine policy that you want to remove by clicking on the name.</span></span>

3. <span data-ttu-id="8e470-389">选择该策略后，单击出现的"删除策略 ![ "图标 ](../../media/m365-cc-sc-delete-icon.png) **"** 删除策略图标"。</span><span class="sxs-lookup"><span data-stu-id="8e470-389">After you select the policy, click the ![Delete policy icon](../../media/m365-cc-sc-delete-icon.png) **Delete policy** icon that appears.</span></span>

4. <span data-ttu-id="8e470-390">单击 **出现的** 确认对话框中的"删除策略"。</span><span class="sxs-lookup"><span data-stu-id="8e470-390">Click **Remove policy** in the confirmation dialog that appears.</span></span>

### <a name="remove-quarantine-policies-in-powershell"></a><span data-ttu-id="8e470-391">在 PowerShell 中删除隔离策略</span><span class="sxs-lookup"><span data-stu-id="8e470-391">Remove quarantine policies in PowerShell</span></span>

<span data-ttu-id="8e470-392">如果你希望使用 PowerShell 删除自定义隔离策略，请将 替换为隔离策略的名称，然后 \<QuarantinePolicyName\> 运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="8e470-392">If you'd rather use PowerShell to remove a custom quarantine policy, replace \<QuarantinePolicyName\> with the name of the quarantine policy, and run the following command:</span></span>

```powershell
Remove-QuarantineTag -Identity "<QuarantinePolicyName>"
```

<span data-ttu-id="8e470-393">有关语法和参数的详细信息，请参阅 [Remove-QuarantineTag](/powershell/module/exchange/remove-quarantinetag)。</span><span class="sxs-lookup"><span data-stu-id="8e470-393">For detailed syntax and parameter information, see [Remove-QuarantineTag](/powershell/module/exchange/remove-quarantinetag).</span></span>

## <a name="quarantine-policy-permission-details"></a><span data-ttu-id="8e470-394">隔离策略权限详细信息</span><span class="sxs-lookup"><span data-stu-id="8e470-394">Quarantine policy permission details</span></span>

<span data-ttu-id="8e470-395">以下各节介绍预设权限组和个人权限在隔离邮件的详细信息和最终用户垃圾邮件通知中的影响。</span><span class="sxs-lookup"><span data-stu-id="8e470-395">The following sections describe the effects of preset permission groups and individual permissions in the details of quarantined messages and in end-user spam notifications.</span></span>

### <a name="preset-permissions-groups"></a><span data-ttu-id="8e470-396">预设权限组</span><span class="sxs-lookup"><span data-stu-id="8e470-396">Preset permissions groups</span></span>

<span data-ttu-id="8e470-397">本文开头的表中列出了预设权限组中包含的单个权限。</span><span class="sxs-lookup"><span data-stu-id="8e470-397">The individual permissions that are included in preset permission groups are listed in the table at the beginning of this article.</span></span>

#### <a name="no-access"></a><span data-ttu-id="8e470-398">禁止访问</span><span class="sxs-lookup"><span data-stu-id="8e470-398">No access</span></span>

<span data-ttu-id="8e470-399">如果隔离策略将"无访问权限" (没有权限) ，则用户仍获得一些基线功能：</span><span class="sxs-lookup"><span data-stu-id="8e470-399">If the quarantine policy assigns the **No access** permissions (no permissions), users still get some baseline capabilities:</span></span>

- <span data-ttu-id="8e470-400">**隔离邮件详细信息\*\*\*\*："查看邮件头**"按钮始终可用。</span><span class="sxs-lookup"><span data-stu-id="8e470-400">**Quarantined message details**: The **View message header** button is always available.</span></span>

  ![隔离策略授予用户无访问权限时隔离邮件详细信息中的可用按钮](../../media/quarantine-tags-quarantined-message-details-no-access.png)

- <span data-ttu-id="8e470-402">**最终用户垃圾邮件通知**： **将用户** 发送到隔离邮件的"审阅"按钮始终可用。</span><span class="sxs-lookup"><span data-stu-id="8e470-402">**End-user spam notifications**: The **Review** button that takes the user to the message in quarantine is always available.</span></span>

  ![如果隔离策略授予用户无访问权限，最终用户垃圾邮件通知中的可用按钮](../../media/quarantine-tags-esn-no-access.png)

#### <a name="limited-access"></a><span data-ttu-id="8e470-404">受限访问</span><span class="sxs-lookup"><span data-stu-id="8e470-404">Limited access</span></span>

<span data-ttu-id="8e470-405">如果隔离策略分配 **"受限"** 访问权限，则用户会获得以下功能：</span><span class="sxs-lookup"><span data-stu-id="8e470-405">If the quarantine policy assigns the **Limited access** permissions, users get the following capabilities:</span></span>

- <span data-ttu-id="8e470-406">**隔离邮件详细信息**：以下按钮可用：</span><span class="sxs-lookup"><span data-stu-id="8e470-406">**Quarantined message details**: The following buttons are available:</span></span>
  - <span data-ttu-id="8e470-407">**请求释放**</span><span class="sxs-lookup"><span data-stu-id="8e470-407">**Request release**</span></span>
  - <span data-ttu-id="8e470-408">**查看邮件头**</span><span class="sxs-lookup"><span data-stu-id="8e470-408">**View message header**</span></span>
  - <span data-ttu-id="8e470-409">**预览邮件**</span><span class="sxs-lookup"><span data-stu-id="8e470-409">**Preview message**</span></span>
  - <span data-ttu-id="8e470-410">**阻止发件人**</span><span class="sxs-lookup"><span data-stu-id="8e470-410">**Block sender**</span></span>
  - <span data-ttu-id="8e470-411">**从隔离区中删除**</span><span class="sxs-lookup"><span data-stu-id="8e470-411">**Remove from quarantine**</span></span>

  ![隔离策略授予用户受限访问权限时隔离邮件详细信息中的可用按钮](../../media/quarantine-tags-quarantined-message-details-limited-access.png)

- <span data-ttu-id="8e470-413">**最终用户垃圾邮件通知**：以下按钮可用：</span><span class="sxs-lookup"><span data-stu-id="8e470-413">**End-user spam notifications**: The following buttons are available:</span></span>
  - <span data-ttu-id="8e470-414">**阻止发件人**</span><span class="sxs-lookup"><span data-stu-id="8e470-414">**Block sender**</span></span>
  - <span data-ttu-id="8e470-415">**审阅**</span><span class="sxs-lookup"><span data-stu-id="8e470-415">**Review**</span></span>

  ![如果隔离策略授予用户受限访问权限，最终用户垃圾邮件通知中的可用按钮](../../media/quarantine-tags-esn-limited-access.png)

#### <a name="full-access"></a><span data-ttu-id="8e470-417">完全访问权限</span><span class="sxs-lookup"><span data-stu-id="8e470-417">Full access</span></span>

<span data-ttu-id="8e470-418">如果隔离策略 **将"完全** 访问权限" (所有可用) ，则用户会获得以下功能：</span><span class="sxs-lookup"><span data-stu-id="8e470-418">If the quarantine policy assigns the **Full access** permissions (all available permissions), users get the following capabilities:</span></span>

- <span data-ttu-id="8e470-419">**隔离邮件详细信息**：以下按钮可用：</span><span class="sxs-lookup"><span data-stu-id="8e470-419">**Quarantined message details**: The following buttons are available:</span></span>
  - <span data-ttu-id="8e470-420">**释放邮件**</span><span class="sxs-lookup"><span data-stu-id="8e470-420">**Release message**</span></span>
  - <span data-ttu-id="8e470-421">**查看邮件头**</span><span class="sxs-lookup"><span data-stu-id="8e470-421">**View message header**</span></span>
  - <span data-ttu-id="8e470-422">**预览邮件**</span><span class="sxs-lookup"><span data-stu-id="8e470-422">**Preview message**</span></span>
  - <span data-ttu-id="8e470-423">**阻止发件人**</span><span class="sxs-lookup"><span data-stu-id="8e470-423">**Block sender**</span></span>
  - <span data-ttu-id="8e470-424">**允许发件人**</span><span class="sxs-lookup"><span data-stu-id="8e470-424">**Allow sender**</span></span>
  - <span data-ttu-id="8e470-425">**从隔离区中删除**</span><span class="sxs-lookup"><span data-stu-id="8e470-425">**Remove from quarantine**</span></span>

  ![隔离策略授予用户完全访问权限时隔离邮件详细信息中的可用按钮](../../media/quarantine-tags-quarantined-message-details-full-access.png)

- <span data-ttu-id="8e470-427">**最终用户垃圾邮件通知**：以下按钮可用：</span><span class="sxs-lookup"><span data-stu-id="8e470-427">**End-user spam notifications**: The following buttons are available:</span></span>
  - <span data-ttu-id="8e470-428">**阻止发件人**</span><span class="sxs-lookup"><span data-stu-id="8e470-428">**Block sender**</span></span>
  - <span data-ttu-id="8e470-429">**发布**</span><span class="sxs-lookup"><span data-stu-id="8e470-429">**Release**</span></span>
  - <span data-ttu-id="8e470-430">**审阅**</span><span class="sxs-lookup"><span data-stu-id="8e470-430">**Review**</span></span>

  ![如果隔离策略授予用户完全访问权限，最终用户垃圾邮件通知中的可用按钮](../../media/quarantine-tags-esn-full-access.png)

### <a name="individual-permissions"></a><span data-ttu-id="8e470-432">个人权限</span><span class="sxs-lookup"><span data-stu-id="8e470-432">Individual permissions</span></span>

> [!NOTE]
> <span data-ttu-id="8e470-433">请记住，用户始终获取"无法访问"部分 [中描述的](#no-access) 按钮。</span><span class="sxs-lookup"><span data-stu-id="8e470-433">Remember, users always get the buttons described in the [No access](#no-access) section.</span></span> <span data-ttu-id="8e470-434">这些按钮不包含在单个权限说明中。</span><span class="sxs-lookup"><span data-stu-id="8e470-434">These buttons are not included in the individual permission descriptions.</span></span>

#### <a name="allow-sender-permission"></a><span data-ttu-id="8e470-435">允许发件人权限</span><span class="sxs-lookup"><span data-stu-id="8e470-435">Allow sender permission</span></span>

<span data-ttu-id="8e470-436">_PermissionToAllowSender_ ("允许发件人"权限) 控制对按钮的访问，该按钮允许用户方便地将隔离的邮件发件人添加到其"保险箱发件人"列表中。 </span><span class="sxs-lookup"><span data-stu-id="8e470-436">The **Allow sender** permission (_PermissionToAllowSender_) controls access to the button that allows users to conveniently add the quarantined message sender to their Safe Senders list.</span></span>

- <span data-ttu-id="8e470-437">**隔离邮件详细信息**：</span><span class="sxs-lookup"><span data-stu-id="8e470-437">**Quarantined message details**:</span></span>
  - <span data-ttu-id="8e470-438">**启用发件人** 权限：" **允许发件人"** 按钮可用。</span><span class="sxs-lookup"><span data-stu-id="8e470-438">**Allow sender** permission enabled: The **Allow sender** button is available.</span></span>
  - <span data-ttu-id="8e470-439">**禁用发件人** 权限：" **允许发件人"** 按钮不可用。</span><span class="sxs-lookup"><span data-stu-id="8e470-439">**Allow sender** permission disabled: The **Allow sender** button is not available.</span></span>

- <span data-ttu-id="8e470-440">**最终用户垃圾邮件通知：** 不起作用。</span><span class="sxs-lookup"><span data-stu-id="8e470-440">**End-user spam notifications**: No effect.</span></span>

<span data-ttu-id="8e470-441">有关发件人列表保险箱，请参阅防止阻止受信任发件人和使用 Exchange Online [](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077#__toc304379666) PowerShell 配置邮箱[的安全列表集合](configure-junk-email-settings-on-exo-mailboxes.md#use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox)。</span><span class="sxs-lookup"><span data-stu-id="8e470-441">For more information about the Safe Senders list, see [Prevent trusted senders from being blocked](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077#__toc304379666) and [Use Exchange Online PowerShell to configure the safelist collection on a mailbox](configure-junk-email-settings-on-exo-mailboxes.md#use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox).</span></span>

#### <a name="block-sender-permission"></a><span data-ttu-id="8e470-442">阻止发件人权限</span><span class="sxs-lookup"><span data-stu-id="8e470-442">Block sender permission</span></span>

<span data-ttu-id="8e470-443">_PermissionToBlockSender_ (阻止发件人) 控制对按钮的访问权限，该按钮允许用户便捷地将隔离的邮件发件人添加到其阻止的发件人列表。 </span><span class="sxs-lookup"><span data-stu-id="8e470-443">The **Block sender** permission (_PermissionToBlockSender_) controls access to the button that allows users to conveniently add the quarantined message sender to their Blocked Senders list.</span></span>

- <span data-ttu-id="8e470-444">**隔离邮件详细信息**：</span><span class="sxs-lookup"><span data-stu-id="8e470-444">**Quarantined message details**:</span></span>
  - <span data-ttu-id="8e470-445">**阻止发件人** 权限已启用 **："阻止发件人"** 按钮可用。</span><span class="sxs-lookup"><span data-stu-id="8e470-445">**Block sender** permission enabled: The **Block sender** button is available.</span></span>
  - <span data-ttu-id="8e470-446">**阻止发件人** 权限已禁用：阻止 **发件人** 按钮不可用。</span><span class="sxs-lookup"><span data-stu-id="8e470-446">**Block sender** permission disabled: The **Block sender** button is not available.</span></span>

- <span data-ttu-id="8e470-447">**最终用户垃圾邮件通知**：</span><span class="sxs-lookup"><span data-stu-id="8e470-447">**End-user spam notifications**:</span></span>
  - <span data-ttu-id="8e470-448">**阻止发件人** 权限已禁用：阻止 **发件人** 按钮不可用。</span><span class="sxs-lookup"><span data-stu-id="8e470-448">**Block sender** permission disabled: The **Block sender** button is not available.</span></span>
  - <span data-ttu-id="8e470-449">**阻止发件人** 权限已启用 **："阻止发件人"** 按钮可用。</span><span class="sxs-lookup"><span data-stu-id="8e470-449">**Block sender** permission enabled: The **Block sender** button is available.</span></span>

<span data-ttu-id="8e470-450">有关阻止的发件人列表的信息，请参阅阻止来自某人的邮件[](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077#__toc304379667)和使用 Exchange Online PowerShell 配置邮箱[的安全列表集合](configure-junk-email-settings-on-exo-mailboxes.md#use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox)。</span><span class="sxs-lookup"><span data-stu-id="8e470-450">For more information about the Blocked Senders list, see [Block messages from someone](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077#__toc304379667) and [Use Exchange Online PowerShell to configure the safelist collection on a mailbox](configure-junk-email-settings-on-exo-mailboxes.md#use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox).</span></span>

#### <a name="delete-permission"></a><span data-ttu-id="8e470-451">删除权限</span><span class="sxs-lookup"><span data-stu-id="8e470-451">Delete permission</span></span>

<span data-ttu-id="8e470-452">_PermissionToDelete (PermissionToDelete_) 控制用户能否删除其邮件 (用户是收件人的邮件，) 隔离。 </span><span class="sxs-lookup"><span data-stu-id="8e470-452">The **Delete** permission (_PermissionToDelete_) controls the ability to of users to delete their messages (messages where the user is a recipient) from quarantine.</span></span>

- <span data-ttu-id="8e470-453">**隔离邮件详细信息**：</span><span class="sxs-lookup"><span data-stu-id="8e470-453">**Quarantined message details**:</span></span>
  - <span data-ttu-id="8e470-454">**启用** 删除权限：" **从隔离区删除"** 按钮可用。</span><span class="sxs-lookup"><span data-stu-id="8e470-454">**Delete** permission enabled: The **Remove from quarantine** button is available.</span></span>
  - <span data-ttu-id="8e470-455">**删除** 权限已禁用：" **从隔离区删除"** 按钮不可用。</span><span class="sxs-lookup"><span data-stu-id="8e470-455">**Delete** permission disabled: The **Remove from quarantine** button is not available.</span></span>

- <span data-ttu-id="8e470-456">**最终用户垃圾邮件通知：** 不起作用。</span><span class="sxs-lookup"><span data-stu-id="8e470-456">**End-user spam notifications**: No effect.</span></span>

#### <a name="preview-permission"></a><span data-ttu-id="8e470-457">预览权限</span><span class="sxs-lookup"><span data-stu-id="8e470-457">Preview permission</span></span>

<span data-ttu-id="8e470-458">_PermissionToPreview_ (预览) 控制用户在隔离中预览邮件的能力。 </span><span class="sxs-lookup"><span data-stu-id="8e470-458">The **Preview** permission (_PermissionToPreview_) controls the ability to of users to preview their messages in quarantine.</span></span>

- <span data-ttu-id="8e470-459">**隔离邮件详细信息**：</span><span class="sxs-lookup"><span data-stu-id="8e470-459">**Quarantined message details**:</span></span>
  - <span data-ttu-id="8e470-460">**预览** 权限已启用： **预览邮件** 按钮可用。</span><span class="sxs-lookup"><span data-stu-id="8e470-460">**Preview** permission enabled: The **Preview message** button is available.</span></span>
  - <span data-ttu-id="8e470-461">**预览** 权限已禁用： **预览邮件** 按钮不可用。</span><span class="sxs-lookup"><span data-stu-id="8e470-461">**Preview** permission disabled: The **Preview message** button is not available.</span></span>

- <span data-ttu-id="8e470-462">**最终用户垃圾邮件通知：** 不起作用。</span><span class="sxs-lookup"><span data-stu-id="8e470-462">**End-user spam notifications**: No effect.</span></span>

#### <a name="allow-recipients-to-release-a-message-from-quarantine-permission"></a><span data-ttu-id="8e470-463">允许收件人解除邮件隔离权限</span><span class="sxs-lookup"><span data-stu-id="8e470-463">Allow recipients to release a message from quarantine permission</span></span>

<span data-ttu-id="8e470-464">_PermissionToRelease_) 中的"允许收件人从隔离中释放邮件"权限 (控制用户直接释放隔离邮件的能力，而无需经过管理员批准。 </span><span class="sxs-lookup"><span data-stu-id="8e470-464">The **Allow recipients to release a message from quarantine** permission (_PermissionToRelease_) controls the ability of users to release their quarantined messages directly and without the approval of an admin.</span></span>

- <span data-ttu-id="8e470-465">**隔离邮件详细信息**：</span><span class="sxs-lookup"><span data-stu-id="8e470-465">**Quarantined message details**:</span></span>
  - <span data-ttu-id="8e470-466">已启用权限 **："释放邮件"** 按钮可用。</span><span class="sxs-lookup"><span data-stu-id="8e470-466">Permission enabled: The **Release message** button is available.</span></span>
  - <span data-ttu-id="8e470-467">权限已禁用 **："释放邮件** "按钮不可用。</span><span class="sxs-lookup"><span data-stu-id="8e470-467">Permission disabled: The **Release message** button is not available.</span></span>

- <span data-ttu-id="8e470-468">**最终用户垃圾邮件通知**：</span><span class="sxs-lookup"><span data-stu-id="8e470-468">**End-user spam notifications**:</span></span>
  - <span data-ttu-id="8e470-469">已启用权限 **："释放** "按钮可用。</span><span class="sxs-lookup"><span data-stu-id="8e470-469">Permission enabled: The **Release** button is available.</span></span>
  - <span data-ttu-id="8e470-470">权限已禁用 **："释放** "按钮不可用。</span><span class="sxs-lookup"><span data-stu-id="8e470-470">Permission disabled: The **Release** button is not available.</span></span>

#### <a name="allow-recipients-to-request-a-message-to-be-released-from-quarantine-permission"></a><span data-ttu-id="8e470-471">允许收件人请求从隔离权限中释放邮件</span><span class="sxs-lookup"><span data-stu-id="8e470-471">Allow recipients to request a message to be released from quarantine permission</span></span>

<span data-ttu-id="8e470-472">允许 **收件人** 请求从隔离中释放的邮件权限 (_PermissionToRequestRelease_) 控制用户请求释放其隔离邮件的能力。 </span><span class="sxs-lookup"><span data-stu-id="8e470-472">The **Allow recipients to request a message to be released from quarantine** permission (_PermissionToRequestRelease_) controls the ability of users to _request_ the release of their quarantined messages.</span></span> <span data-ttu-id="8e470-473">邮件仅在管理员批准请求后释放。</span><span class="sxs-lookup"><span data-stu-id="8e470-473">The message is only released after an admin approves the request.</span></span>

- <span data-ttu-id="8e470-474">**隔离邮件详细信息**：</span><span class="sxs-lookup"><span data-stu-id="8e470-474">**Quarantined message details**:</span></span>
  - <span data-ttu-id="8e470-475">已启用权限 **："请求释放** "按钮可用。</span><span class="sxs-lookup"><span data-stu-id="8e470-475">Permission enabled: The **Request release** button is available.</span></span>
  - <span data-ttu-id="8e470-476">权限已禁用 **："请求释放** "按钮不可用。</span><span class="sxs-lookup"><span data-stu-id="8e470-476">Permission disabled: The **Request release** button is not available.</span></span>

- <span data-ttu-id="8e470-477">**最终用户垃圾邮件通知**：" **释放** "按钮不可用。</span><span class="sxs-lookup"><span data-stu-id="8e470-477">**End-user spam notifications**: The **Release** button is not available.</span></span>
