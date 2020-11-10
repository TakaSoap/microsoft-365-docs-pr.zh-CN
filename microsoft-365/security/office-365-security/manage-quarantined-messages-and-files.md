---
title: 以管理员身份管理隔离的邮件和文件
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 065cc2cf-2f3a-47fd-a434-2a20b8f51d0c
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 管理员可以了解如何在 Exchange Online Protection (EOP) 中查看和管理所有用户的隔离邮件。 具有 Microsoft Defender for Office 365 的组织中的管理员还可以管理 SharePoint Online、OneDrive for Business 和 Microsoft 团队中的隔离文件。
ms.openlocfilehash: 9d58f8c08d994e5e9736c8223239b54e52c4edab
ms.sourcegitcommit: 9bf6a4f77f9af5fd988f6795bad3b240213a51fc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/10/2020
ms.locfileid: "48951043"
---
# <a name="manage-quarantined-messages-and-files-as-an-admin-in-eop"></a><span data-ttu-id="9cdec-104">在 EOP 中以管理员身份管理已隔离邮件和文件</span><span class="sxs-lookup"><span data-stu-id="9cdec-104">Manage quarantined messages and files as an admin in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="9cdec-105">无论是在有 Exchange Online 邮箱的 Microsoft 365 组织中，还是在没有 Exchange Online 邮箱的独立 Exchange Online Protection (EOP) 组织中，隔离功能都会隔离具有潜在危险或不需要的邮件。</span><span class="sxs-lookup"><span data-stu-id="9cdec-105">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, quarantine holds potentially dangerous or unwanted messages.</span></span> <span data-ttu-id="9cdec-106">有关详细信息，请参阅 [EOP 中隔离的电子邮件](quarantine-email-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="9cdec-106">For more information, see [Quarantined email messages in EOP](quarantine-email-messages.md).</span></span>

<span data-ttu-id="9cdec-107">管理员可以查看、释放和删除所有用户的所有类型的隔离邮件。</span><span class="sxs-lookup"><span data-stu-id="9cdec-107">Admins can view, release, and delete all types of quarantined messages for all users.</span></span> <span data-ttu-id="9cdec-108">只有管理员可以管理被隔离为恶意软件、高可信度网络钓鱼或邮件流规则的结果的邮件 (也称为传输规则) 。</span><span class="sxs-lookup"><span data-stu-id="9cdec-108">Only admins can manage messages that were quarantined as malware, high confidence phishing, or as a result of mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="9cdec-109">管理员还可以向 Microsoft 报告误报。</span><span class="sxs-lookup"><span data-stu-id="9cdec-109">Admins can also report false positives to Microsoft.</span></span>

<span data-ttu-id="9cdec-110">具有 Microsoft Defender for Office 365 的组织中的管理员还可以在 SharePoint Online、OneDrive for Business 和 Microsoft 团队中查看、下载和删除隔离的文件。</span><span class="sxs-lookup"><span data-stu-id="9cdec-110">Admins in organizations with Microsoft Defender for Office 365 can also view, download, and delete quarantined files in SharePoint Online, OneDrive for Business, and Microsoft Teams.</span></span>

<span data-ttu-id="9cdec-111">您可以使用 Exchange Online 中的邮箱在安全 & 合规性中心或 PowerShell (Exchange Online PowerShell 中查看和管理隔离的邮件，以用于 Microsoft 365 组织的 Exchange Online PowerShell;没有 Exchange Online 邮箱) 组织的独立 EOP PowerShell。</span><span class="sxs-lookup"><span data-stu-id="9cdec-111">You view and manage quarantined messages in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="9cdec-112">开始前，有必要了解什么？</span><span class="sxs-lookup"><span data-stu-id="9cdec-112">What do you need to know before you begin?</span></span>

- <span data-ttu-id="9cdec-113">若要打开安全与合规中心，请转到 <https://protection.office.com>。</span><span class="sxs-lookup"><span data-stu-id="9cdec-113">To open the Security & Compliance Center, go to <https://protection.office.com>.</span></span> <span data-ttu-id="9cdec-114">若要直接打开“隔离”页，请转到 <https://protection.office.com/quarantine>。</span><span class="sxs-lookup"><span data-stu-id="9cdec-114">To open the Quarantine page directly, go to <https://protection.office.com/quarantine>.</span></span>

- <span data-ttu-id="9cdec-115">若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="9cdec-115">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="9cdec-116">若要连接到独立 EOP PowerShell，请参阅[连接到 Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)。</span><span class="sxs-lookup"><span data-stu-id="9cdec-116">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="9cdec-117">您需要先分配权限，然后才能以管理员身份管理隔离。权限由 Security & 合规中心中的 **隔离** 角色控制。</span><span class="sxs-lookup"><span data-stu-id="9cdec-117">You need to be assigned permissions before you can manage the quarantine as an admin. The permissions are controlled by the **Quarantine** role in the Security & Compliance Center.</span></span> <span data-ttu-id="9cdec-118">默认情况下，此角色分配给 " **组织管理** " (全局管理员) 、" **隔离管理员** " 和 "安全 **管理员** 角色组" 安全 & 合规性中心。</span><span class="sxs-lookup"><span data-stu-id="9cdec-118">By default, this role is assigned to the **Organization Management** (Global admins), **Quarantine Administrator** , and **Security Administrator** role groups in the Security & Compliance Center.</span></span> <span data-ttu-id="9cdec-119">有关详细信息，请参阅[安全与合规中心中的权限](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="9cdec-119">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="9cdec-120">在被自动删除之前，隔离的邮件将保留默认的一段时间：</span><span class="sxs-lookup"><span data-stu-id="9cdec-120">Quarantined messages are retained for a default period of time before they're automatically deleted:</span></span>

  - <span data-ttu-id="9cdec-121">反垃圾邮件策略隔离的邮件 (垃圾邮件、网络钓鱼和批量电子邮件) ：30天。</span><span class="sxs-lookup"><span data-stu-id="9cdec-121">Messages quarantined by anti-spam policies (spam, phishing, and bulk email): 30 days.</span></span> <span data-ttu-id="9cdec-122">这是默认值和最大值。</span><span class="sxs-lookup"><span data-stu-id="9cdec-122">This is the default and maximum value.</span></span> <span data-ttu-id="9cdec-123">若要配置此值，请参阅 [配置反垃圾邮件策略](configure-your-spam-filter-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="9cdec-123">To configure this value, see [Configure anti-spam policies](configure-your-spam-filter-policies.md).</span></span>

  - <span data-ttu-id="9cdec-124">包含恶意软件的邮件：15天。</span><span class="sxs-lookup"><span data-stu-id="9cdec-124">Messages that contain malware: 15 days.</span></span>

  <span data-ttu-id="9cdec-125">当邮件从隔离区中过期时，将无法对其进行恢复。</span><span class="sxs-lookup"><span data-stu-id="9cdec-125">When a message expires from quarantine, you can't recover it.</span></span>

## <a name="use-the-security--compliance-center-to-manage-quarantined-email-messages"></a><span data-ttu-id="9cdec-126">使用安全 & 合规性中心管理隔离的电子邮件</span><span class="sxs-lookup"><span data-stu-id="9cdec-126">Use the Security & Compliance Center to manage quarantined email messages</span></span>

### <a name="view-quarantined-email"></a><span data-ttu-id="9cdec-127">查看隔离的电子邮件</span><span class="sxs-lookup"><span data-stu-id="9cdec-127">View quarantined email</span></span>

1. <span data-ttu-id="9cdec-128">在安全与合规中心内，依次转到“威胁管理”\>“审阅”\>“隔离”。</span><span class="sxs-lookup"><span data-stu-id="9cdec-128">In the Security and Compliance Center, go to **Threat Management** \> **Review** \> **Quarantine**.</span></span>

2. <span data-ttu-id="9cdec-129">验证 " **隔离视图** " 是否已设置为默认值 " **电子邮件** "。</span><span class="sxs-lookup"><span data-stu-id="9cdec-129">Verify that **View quarantined** is set to the default value **email**.</span></span>

3. <span data-ttu-id="9cdec-130">若要对结果进行排序，可以单击可用列标题。</span><span class="sxs-lookup"><span data-stu-id="9cdec-130">You can sort the results by clicking on an available column header.</span></span> <span data-ttu-id="9cdec-131">单击“修改列”最多可显示七列。</span><span class="sxs-lookup"><span data-stu-id="9cdec-131">Click **Modify columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="9cdec-132">默认值标有星号 (<sup>\*</sup>)：</span><span class="sxs-lookup"><span data-stu-id="9cdec-132">The default values are marked with an asterisk (<sup>\*</sup>):</span></span>

   - <span data-ttu-id="9cdec-133">**接收时间**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="9cdec-133">**Received**<sup>\*</sup></span></span>
   - <span data-ttu-id="9cdec-134">**发件人**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="9cdec-134">**Sender**<sup>\*</sup></span></span>
   - <span data-ttu-id="9cdec-135">**主题**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="9cdec-135">**Subject**<sup>\*</sup></span></span>
   - <span data-ttu-id="9cdec-136">**隔离原因**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="9cdec-136">**Quarantine reason**<sup>\*</sup></span></span>
   - <span data-ttu-id="9cdec-137">**释放?**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="9cdec-137">**Released?**<sup>\*</sup></span></span>
   - <span data-ttu-id="9cdec-138">**策略类型**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="9cdec-138">**Policy type**<sup>\*</sup></span></span>
   - <span data-ttu-id="9cdec-139">**Expires**</span><span class="sxs-lookup"><span data-stu-id="9cdec-139">**Expires**</span></span>
   - <span data-ttu-id="9cdec-140">**收件人**</span><span class="sxs-lookup"><span data-stu-id="9cdec-140">**Recipient**</span></span>
   - <span data-ttu-id="9cdec-141">**邮件 ID**</span><span class="sxs-lookup"><span data-stu-id="9cdec-141">**Message ID**</span></span>
   - <span data-ttu-id="9cdec-142">**策略名称**</span><span class="sxs-lookup"><span data-stu-id="9cdec-142">**Policy name**</span></span>
   - <span data-ttu-id="9cdec-143">**大小**</span><span class="sxs-lookup"><span data-stu-id="9cdec-143">**Size**</span></span>
   - <span data-ttu-id="9cdec-144">**方向**</span><span class="sxs-lookup"><span data-stu-id="9cdec-144">**Direction**</span></span>

   <span data-ttu-id="9cdec-145">完成后，单击“保存”单击“设置为默认设置”。</span><span class="sxs-lookup"><span data-stu-id="9cdec-145">When you're finished, click **Save** , or click **Set to default**.</span></span>

4. <span data-ttu-id="9cdec-146">若要筛选结果，请单击“筛选器”。</span><span class="sxs-lookup"><span data-stu-id="9cdec-146">To filter the results, click **Filter**.</span></span> <span data-ttu-id="9cdec-147">以下筛选器可用：</span><span class="sxs-lookup"><span data-stu-id="9cdec-147">The available filters are:</span></span>

   - <span data-ttu-id="9cdec-148">**到期时间** ：按邮件的隔离到期时间筛选：</span><span class="sxs-lookup"><span data-stu-id="9cdec-148">**Expires time** : Filter messages by when they will expire from quarantine:</span></span>
     - <span data-ttu-id="9cdec-149">**今天**</span><span class="sxs-lookup"><span data-stu-id="9cdec-149">**Today**</span></span>
     - <span data-ttu-id="9cdec-150">**未来 2 天**</span><span class="sxs-lookup"><span data-stu-id="9cdec-150">**Next 2 days**</span></span>
     - <span data-ttu-id="9cdec-151">**未来 7 天**</span><span class="sxs-lookup"><span data-stu-id="9cdec-151">**Next 7 days**</span></span>
     - <span data-ttu-id="9cdec-152">**自定义** ：输入“开始日期”和“结束日期”。</span><span class="sxs-lookup"><span data-stu-id="9cdec-152">**Custom** : Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="9cdec-153">**接收时间** ：输入“开始日期”和“结束日期”。</span><span class="sxs-lookup"><span data-stu-id="9cdec-153">**Received time** : Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="9cdec-154">**隔离原因** ：</span><span class="sxs-lookup"><span data-stu-id="9cdec-154">**Quarantine reason** :</span></span>
     - <span data-ttu-id="9cdec-155">**策略** ：邮件与邮件流规则的条件相匹配 (也称为传输规则) 。</span><span class="sxs-lookup"><span data-stu-id="9cdec-155">**Policy** : The message matched the conditions of a mail flow rule (also known as a transport rule).</span></span>
     - <span data-ttu-id="9cdec-156">**大量邮件**</span><span class="sxs-lookup"><span data-stu-id="9cdec-156">**Bulk**</span></span>
     - <span data-ttu-id="9cdec-157">**网络钓鱼** ：垃圾邮件筛选器判定为 **网络钓鱼电子邮件** 或反钓鱼防护隔离了邮件 ( [欺骗设置](set-up-anti-phishing-policies.md#spoof-settings) 或 [模拟保护](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)) 。</span><span class="sxs-lookup"><span data-stu-id="9cdec-157">**Phish** : The spam filter verdict was **Phishing email** or anti-phishing protection quarantined the message ([spoof settings](set-up-anti-phishing-policies.md#spoof-settings) or [impersonation protection](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)).</span></span>
     - <span data-ttu-id="9cdec-158">**恶意软件**</span><span class="sxs-lookup"><span data-stu-id="9cdec-158">**Malware**</span></span>
     - <span data-ttu-id="9cdec-159">**垃圾邮件**</span><span class="sxs-lookup"><span data-stu-id="9cdec-159">**Spam**</span></span>
     - <span data-ttu-id="9cdec-160">**高可信度网络钓鱼**</span><span class="sxs-lookup"><span data-stu-id="9cdec-160">**High Confidence Phish**</span></span>

   - <span data-ttu-id="9cdec-161">**策略类型** ：按策略类型筛选邮件：</span><span class="sxs-lookup"><span data-stu-id="9cdec-161">**Policy Type** : Filter messages by policy type:</span></span>
     - <span data-ttu-id="9cdec-162">**反恶意软件策略**</span><span class="sxs-lookup"><span data-stu-id="9cdec-162">**Anti-malware policy**</span></span>
     - <span data-ttu-id="9cdec-163">**安全附件策略**</span><span class="sxs-lookup"><span data-stu-id="9cdec-163">**Safe Attachments policy**</span></span>
     - <span data-ttu-id="9cdec-164">**反网络钓鱼策略**</span><span class="sxs-lookup"><span data-stu-id="9cdec-164">**Anti-phish policy**</span></span>
     - <span data-ttu-id="9cdec-165"> (反垃圾邮件策略) 的 **托管内容筛选器策略**</span><span class="sxs-lookup"><span data-stu-id="9cdec-165">**Hosted content filter policy** (anti-spam policy)</span></span>
     - <span data-ttu-id="9cdec-166">**传输规则**</span><span class="sxs-lookup"><span data-stu-id="9cdec-166">**Transport rule**</span></span>

   - <span data-ttu-id="9cdec-167">**电子邮件收件人** ：所有用户或仅发送给你的邮件。</span><span class="sxs-lookup"><span data-stu-id="9cdec-167">**Email recipient** : All users or only messages sent to you.</span></span> <span data-ttu-id="9cdec-168">最终用户只能管理发送给他们的隔离邮件。</span><span class="sxs-lookup"><span data-stu-id="9cdec-168">End users can only manage quarantined messages sent to them.</span></span>

   <span data-ttu-id="9cdec-169">若要清除筛选器，请单击“清除”。</span><span class="sxs-lookup"><span data-stu-id="9cdec-169">To clear the filter, click **Clear**.</span></span> <span data-ttu-id="9cdec-170">若要隐藏筛选器浮出控件，请再次单击“筛选器”。</span><span class="sxs-lookup"><span data-stu-id="9cdec-170">To hide the filter flyout, click **Filter** again.</span></span>

5. <span data-ttu-id="9cdec-171">使用“结果排序依据”（默认为“邮件 ID”按钮）和相应值查找特定邮件。</span><span class="sxs-lookup"><span data-stu-id="9cdec-171">Use **Sort results by** (the **Message ID** button by default) and a corresponding value to find specific messages.</span></span> <span data-ttu-id="9cdec-172">不支持通配符。</span><span class="sxs-lookup"><span data-stu-id="9cdec-172">Wildcards aren't supported.</span></span> <span data-ttu-id="9cdec-173">可以按下面的值搜索：</span><span class="sxs-lookup"><span data-stu-id="9cdec-173">You can search by the following values:</span></span>

   - <span data-ttu-id="9cdec-174">**邮件 ID** ：邮件的全局唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="9cdec-174">**Message ID** : The globally unique identifier of the message.</span></span>

     <span data-ttu-id="9cdec-175">例如，使用 [邮件跟踪](message-trace-scc.md) 查找发送到组织中的用户的邮件，并确定邮件已被隔离而不是传递。</span><span class="sxs-lookup"><span data-stu-id="9cdec-175">For example, you used [message trace](message-trace-scc.md) to look for a message that was sent to a user in your organization, and you determine that the message was quarantined instead of delivered.</span></span> <span data-ttu-id="9cdec-176">确保包含完整的邮件 ID 值，其中可能包含尖括号 (\<\>) 。</span><span class="sxs-lookup"><span data-stu-id="9cdec-176">Be sure to include the full message ID value, which might include angle brackets (\<\>).</span></span> <span data-ttu-id="9cdec-177">例如：`<79239079-d95a-483a-aacf-e954f592a0f6@XYZPR00BM0200.contoso.com>`。</span><span class="sxs-lookup"><span data-stu-id="9cdec-177">For example: `<79239079-d95a-483a-aacf-e954f592a0f6@XYZPR00BM0200.contoso.com>`.</span></span>

   - <span data-ttu-id="9cdec-178">**发件人电子邮件地址** ：单个发件人的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="9cdec-178">**Sender email address** : A single sender's email address.</span></span>

   - <span data-ttu-id="9cdec-179">**策略名称** ：使用邮件的完整策略名称。</span><span class="sxs-lookup"><span data-stu-id="9cdec-179">**Policy name** : Use the entire policy name of the message.</span></span> <span data-ttu-id="9cdec-180">搜索不区分大小写。</span><span class="sxs-lookup"><span data-stu-id="9cdec-180">The search is not case-sensitive.</span></span>

   - <span data-ttu-id="9cdec-181">**收件人电子邮件地址** ：单个收件人的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="9cdec-181">**Recipient email address** : A single recipient's email address.</span></span>

   - <span data-ttu-id="9cdec-182">**主题** ：使用邮件的整个主题。</span><span class="sxs-lookup"><span data-stu-id="9cdec-182">**Subject** : Use the entire subject of the message.</span></span> <span data-ttu-id="9cdec-183">搜索不区分大小写。</span><span class="sxs-lookup"><span data-stu-id="9cdec-183">The search is not case-sensitive.</span></span>
  
   - <span data-ttu-id="9cdec-184">**策略名称** ：负责隔离邮件的策略的名称。</span><span class="sxs-lookup"><span data-stu-id="9cdec-184">**Policy name** : The name of the policy that was responsible for quarantining the message.</span></span>

   <span data-ttu-id="9cdec-185">输入搜索条件后，单击“刷新” ![“刷新”按钮](../../media/scc-quarantine-refresh.png) 来筛选结果。</span><span class="sxs-lookup"><span data-stu-id="9cdec-185">After you've entered the search criteria, click ![Refresh button](../../media/scc-quarantine-refresh.png) **Refresh** to filter the results.</span></span>

<span data-ttu-id="9cdec-186">找到特定的已隔离邮件后，选择此邮件即可查看它的详细信息，并对它执行操作（例如，查看、释放、下载或删除邮件）。</span><span class="sxs-lookup"><span data-stu-id="9cdec-186">After you find a specific quarantined message, select the message to view details about it, and to take action on it (for example, view, release, download, or delete the message).</span></span>

#### <a name="view-quarantined-message-details"></a><span data-ttu-id="9cdec-187">查看已隔离邮件的详细信息</span><span class="sxs-lookup"><span data-stu-id="9cdec-187">View quarantined message details</span></span>

<span data-ttu-id="9cdec-188">选择列表中的电子邮件后，可以在“详细信息”浮出控件窗格中看到以下邮件详细信息：</span><span class="sxs-lookup"><span data-stu-id="9cdec-188">When you select an email message in the list, the following message details appear in the **Details** flyout pane:</span></span>

- <span data-ttu-id="9cdec-189">**邮件 ID** ：邮件的全局唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="9cdec-189">**Message ID** : The globally unique identifier for the message.</span></span>

- <span data-ttu-id="9cdec-190">**发件人地址**</span><span class="sxs-lookup"><span data-stu-id="9cdec-190">**Sender address**</span></span>

- <span data-ttu-id="9cdec-191">**接收时间** ：收到邮件的日期/时间。</span><span class="sxs-lookup"><span data-stu-id="9cdec-191">**Received** : The date/time when the message was received.</span></span>

- <span data-ttu-id="9cdec-192">**主题**</span><span class="sxs-lookup"><span data-stu-id="9cdec-192">**Subject**</span></span>

- <span data-ttu-id="9cdec-193">**隔离原因** ：显示邮件是否已被标识为 **垃圾** 邮件、 **批量** 、 **网络钓鱼** 、与邮件流规则匹配 ( **传输规则** ) 或被标识为包含 **恶意软件** 。</span><span class="sxs-lookup"><span data-stu-id="9cdec-193">**Quarantine reason** : Shows if a message has been identified as **Spam** , **Bulk** , **Phish** , matched a mail flow rule ( **Transport rule** ), or was identified as containing **Malware**.</span></span>

- <span data-ttu-id="9cdec-194">**收件人计数**</span><span class="sxs-lookup"><span data-stu-id="9cdec-194">**Recipient count**</span></span>

- <span data-ttu-id="9cdec-195">**收件人** ：如果邮件有多个收件人，需要单击“预览邮件”或“查看邮件头”，以查看完整的收件人列表。</span><span class="sxs-lookup"><span data-stu-id="9cdec-195">**Recipients** : If the message contains multiple recipients, you need to click **Preview message** or **View message header** to see the complete list of recipients.</span></span>

- <span data-ttu-id="9cdec-196">**到期时间** ：邮件自动从隔离中永久删除的日期/时间。</span><span class="sxs-lookup"><span data-stu-id="9cdec-196">**Expires** : The date/time when the message will be automatically and permanently deleted from quarantine.</span></span>

- <span data-ttu-id="9cdec-197">**已释放到的位置** ：邮件已释放到的所有电子邮件地址（若有）。</span><span class="sxs-lookup"><span data-stu-id="9cdec-197">**Released to** : All email addresses (if any) to which the message has been released.</span></span>

- <span data-ttu-id="9cdec-198">**尚未释放到的位置** ：邮件尚未释放到的所有电子邮件地址（若有）。</span><span class="sxs-lookup"><span data-stu-id="9cdec-198">**Not yet released to** : All email addresses (if any) to which the message has not yet been released.</span></span>

### <a name="take-action-on-quarantined-email"></a><span data-ttu-id="9cdec-199">对已隔离电子邮件执行操作</span><span class="sxs-lookup"><span data-stu-id="9cdec-199">Take action on quarantined email</span></span>

<span data-ttu-id="9cdec-200">选择一封邮件后，您有几种方法可用于处理 " **详细信息** " 弹出窗格中的邮件：</span><span class="sxs-lookup"><span data-stu-id="9cdec-200">After you select a message, you have several options for what to do with the messages in the **Details** flyout pane:</span></span>

- <span data-ttu-id="9cdec-201">**释放邮件** ：在出现的弹出窗口中，选择以下选项：</span><span class="sxs-lookup"><span data-stu-id="9cdec-201">**Release message** : In the flyout pane that appears, choose the following options:</span></span>

  - <span data-ttu-id="9cdec-202">**将邮件报告给 Microsoft 进行分析** ：默认情况下，此选项处于选中状态，并将错误隔离的邮件以误报的形式报告给 microsoft。</span><span class="sxs-lookup"><span data-stu-id="9cdec-202">**Report messages to Microsoft for analysis** : This is selected by default, and reports the erroneously quarantined message to Microsoft as a false positive.</span></span> <span data-ttu-id="9cdec-203">如果邮件被隔离为垃圾邮件、批量、网络钓鱼或包含恶意软件，则还会向 Microsoft 垃圾邮件分析团队报告该邮件。</span><span class="sxs-lookup"><span data-stu-id="9cdec-203">If the message was quarantined as spam, bulk, phishing, or containing malware, the message is also reported to the Microsoft Spam Analysis Team.</span></span> <span data-ttu-id="9cdec-204">根据分析的不同，可能会调整服务范围的垃圾邮件筛选器规则，以允许邮件通过。</span><span class="sxs-lookup"><span data-stu-id="9cdec-204">Depending on their analysis, the service-wide spam filter rules might be adjusted to allow the message through.</span></span>

  - <span data-ttu-id="9cdec-205">选择下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="9cdec-205">Choose one of the following options:</span></span>
    - <span data-ttu-id="9cdec-206">**将邮件释放给所有收件人**</span><span class="sxs-lookup"><span data-stu-id="9cdec-206">**Release messages to all recipients**</span></span>
    - <span data-ttu-id="9cdec-207">**将邮件释放给特定收件人**</span><span class="sxs-lookup"><span data-stu-id="9cdec-207">**Release messages to specific recipients**</span></span>
    - <span data-ttu-id="9cdec-208">**向其他人发布邮件**</span><span class="sxs-lookup"><span data-stu-id="9cdec-208">**Release messages to other people**</span></span>

  <span data-ttu-id="9cdec-209">完成后，单击“释放邮件”。</span><span class="sxs-lookup"><span data-stu-id="9cdec-209">When you're finished, click **Release messages**.</span></span>

  <span data-ttu-id="9cdec-210">有关释放邮件的说明：</span><span class="sxs-lookup"><span data-stu-id="9cdec-210">Notes about releasing messages:</span></span>

  - <span data-ttu-id="9cdec-211">不能多次将邮件释放到同一收件人。</span><span class="sxs-lookup"><span data-stu-id="9cdec-211">You can't release a message to the same recipient more than once.</span></span>
  - <span data-ttu-id="9cdec-212">只有未收到邮件的收件人才会显示在潜在收件人列表中。</span><span class="sxs-lookup"><span data-stu-id="9cdec-212">Only recipients who haven't received the message will appear in the list of potential recipients.</span></span>

- <span data-ttu-id="9cdec-213">**查看邮件头** ：选择此链接可查看邮件头文本。</span><span class="sxs-lookup"><span data-stu-id="9cdec-213">**View message header** : Choose this link to see the message header text.</span></span> <span data-ttu-id="9cdec-214">若要深入分析邮件头字段和值，请将邮件头文本复制到剪贴板，然后选择“Microsoft 邮件头分析器”，即可转到远程连接分析器（如果希望在不离开 Microsoft 365 的情况下完成这项任务，请右键单击并选择“在新标签页中打开”）。</span><span class="sxs-lookup"><span data-stu-id="9cdec-214">To analyze the header fields and values in depth, copy the message header text to your clipboard, and then choose **Microsoft Message Header Analyzer** to go to the Remote Connectivity Analyzer (right-click and choose **Open in a new tab** if you don't want to leave Microsoft 365 to complete this task).</span></span> <span data-ttu-id="9cdec-215">将邮件头粘贴到页面上的“邮件头分析器”部分中，然后选择“分析邮件头”：</span><span class="sxs-lookup"><span data-stu-id="9cdec-215">Paste the message header onto the page in the Message Header Analyzer section, and choose **Analyze headers** :</span></span>

- <span data-ttu-id="9cdec-216">**预览邮件** ：在显示的浮出控件窗格中，选择以下选项之一：</span><span class="sxs-lookup"><span data-stu-id="9cdec-216">**Preview message** : In the flyout pane that appears, choose one of the following options:</span></span>

  - <span data-ttu-id="9cdec-217">**源视图** ：显示禁用所有链接的 HTML 版邮件正文。</span><span class="sxs-lookup"><span data-stu-id="9cdec-217">**Source view** : Shows the HTML version of the message body with all links disabled.</span></span>
  - <span data-ttu-id="9cdec-218">**文本视图** ：以纯文本格式显示邮件正文。</span><span class="sxs-lookup"><span data-stu-id="9cdec-218">**Text view** : Shows the message body in plain text.</span></span>

- <span data-ttu-id="9cdec-219">**从隔离区中删除** ：在显示的警告中单击 **"是"** 后，会立即删除邮件，而不会将其发送给原始收件人。</span><span class="sxs-lookup"><span data-stu-id="9cdec-219">**Remove from quarantine** : After you click **Yes** in the warning that appears, the message is immediately deleted without being sent to the original recipients.</span></span>

- <span data-ttu-id="9cdec-220">**下载邮件** ：在显示的浮出控件窗格中，选择“我了解下载此邮件所面临的风险”，以使用 .eml 格式保存邮件的本地副本。</span><span class="sxs-lookup"><span data-stu-id="9cdec-220">**Download message** : In the flyout pane that appears, select **I understand the risks from downloading this message** to save a local copy of the message in .eml format.</span></span>

- <span data-ttu-id="9cdec-221">**提交邮件** ：在出现的弹出窗口中，选择以下选项：</span><span class="sxs-lookup"><span data-stu-id="9cdec-221">**Submit message** : In the flyout pane that appears, choose the following options:</span></span>

  - <span data-ttu-id="9cdec-222">**对象类型** ： **电子邮件** (默认) 、 **URL** 或 **附件** 。</span><span class="sxs-lookup"><span data-stu-id="9cdec-222">**Object type** : **Email** (default), **URL** , or **Attachment**.</span></span>

  - <span data-ttu-id="9cdec-223">**提交格式** ： **网络邮件 id** (默认情况下，在 " **网络邮件 id** " 框中对应的值) 或 **文件** (浏览到本地 .eml 或 .msg 文件) 。</span><span class="sxs-lookup"><span data-stu-id="9cdec-223">**Submission format** : **Network Message ID** (default, with the corresponding value in the **Network Message ID** box) or **File** (browse to a local .eml or .msg file).</span></span> <span data-ttu-id="9cdec-224">请注意，如果选择 " **文件** "，然后选择 " **网络邮件 ID** "，则初始值将不再存在。</span><span class="sxs-lookup"><span data-stu-id="9cdec-224">Note that if you select **File** and then select **Network Message ID** , the initially value is gone.</span></span>

  - <span data-ttu-id="9cdec-225">**收件人** ：键入邮件的原始收件人，或单击 " **全选** " 以标识所有收件人。</span><span class="sxs-lookup"><span data-stu-id="9cdec-225">**Recipients** : Type at lease one original recipient of the message, or click **Select All** to identify all recipients.</span></span> <span data-ttu-id="9cdec-226">也可以单击 " **全选** "，然后有选择地删除各个收件人。</span><span class="sxs-lookup"><span data-stu-id="9cdec-226">You can also click **Select All** and then selectively remove individual recipients.</span></span>

  - <span data-ttu-id="9cdec-227">**提交原因** ： **不应被阻止** (默认) 或应被 **阻止** 。</span><span class="sxs-lookup"><span data-stu-id="9cdec-227">**Reason for submission** : **Should not have been blocked** (default) or **Should have been blocked**.</span></span>

  <span data-ttu-id="9cdec-228">完成后，请单击 " **提交** "。</span><span class="sxs-lookup"><span data-stu-id="9cdec-228">When you're finished, click **Submit**.</span></span>

<span data-ttu-id="9cdec-229">如果你没有释放或删除邮件，它会在默认隔离保持期到期后删除。</span><span class="sxs-lookup"><span data-stu-id="9cdec-229">If you don't release or remove the message, it will be deleted after the default quarantine retention period expires.</span></span>

#### <a name="take-action-on-multiple-quarantined-email-messages"></a><span data-ttu-id="9cdec-230">对多封已隔离电子邮件执行操作</span><span class="sxs-lookup"><span data-stu-id="9cdec-230">Take action on multiple quarantined email messages</span></span>

<span data-ttu-id="9cdec-231">在你选择列表中的多封已隔离邮件（最多 100 封）后，“批量操作”浮出控件窗格随即显示，你可以在其中执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="9cdec-231">When you select multiple quarantined messages in the list (up to 100), the **Bulk actions** flyout pane appears where you can take the following actions:</span></span>

- <span data-ttu-id="9cdec-232">**释放邮件** ：除了无法选择“将邮件释放给特定收件人”之外，可以选择的选项与释放一封邮件时相同，即只能选择“将邮件释放给所有收件人”或“将邮件释放给其他用户”。</span><span class="sxs-lookup"><span data-stu-id="9cdec-232">**Release messages** : The options are the same as when you release a single message, except you can't select **Release messages to specific recipients** ; you can only select **Release message to all recipients** or **Release messages to other people**.</span></span>

  > [!NOTE]
  > <span data-ttu-id="9cdec-233">请考虑以下方案： john@gmail.com 向 faith@contoso.com 和 john@subsidiary.contoso.com 发送一封邮件。</span><span class="sxs-lookup"><span data-stu-id="9cdec-233">Consider the following scenario: john@gmail.com sends a message to faith@contoso.com and john@subsidiary.contoso.com.</span></span> <span data-ttu-id="9cdec-234">Gmail 将此邮件拆分为在 Microsoft 中作为网络钓鱼传送到隔离的两个副本。</span><span class="sxs-lookup"><span data-stu-id="9cdec-234">Gmail bifurcates this message into two copies that are both routed to quarantine as phishing in Microsoft.</span></span> <span data-ttu-id="9cdec-235">管理员将这两个邮件释放到 admin@contoso.com。</span><span class="sxs-lookup"><span data-stu-id="9cdec-235">An admin releases both of these messages to admin@contoso.com.</span></span> <span data-ttu-id="9cdec-236">传递到达管理邮箱的第一个已释放邮件。</span><span class="sxs-lookup"><span data-stu-id="9cdec-236">The first released message that reaches the admin mailbox is delivered.</span></span> <span data-ttu-id="9cdec-237">第二个已释放的邮件被标识为重复传递，并被跳过。</span><span class="sxs-lookup"><span data-stu-id="9cdec-237">The second released message is identified as duplicate delivery and is skipped.</span></span> <span data-ttu-id="9cdec-238">如果邮件具有相同的邮件 ID 和接收时间，则会将其标识为重复。</span><span class="sxs-lookup"><span data-stu-id="9cdec-238">Message are identified as duplicates if they have the same message ID and received time.</span></span>

- <span data-ttu-id="9cdec-239">**删除邮件** ：当你在显示的警告中单击“是”后，邮件会立即删除，而不会发送给原始收件人。</span><span class="sxs-lookup"><span data-stu-id="9cdec-239">**Delete messages** :  After you click **Yes** in the warning that appears, the message are immediately deleted without being sent to the original recipients.</span></span>

<span data-ttu-id="9cdec-240">完成后，单击“关闭”。</span><span class="sxs-lookup"><span data-stu-id="9cdec-240">When you're finished, click **Close**.</span></span>

## <a name="microsoft-defender-for-office-365-only-use-the-security--compliance-center-to-manage-quarantined-files"></a><span data-ttu-id="9cdec-241">仅适用于 Office 365 的 Microsoft Defender：使用安全 & 合规性中心管理隔离的文件</span><span class="sxs-lookup"><span data-stu-id="9cdec-241">Microsoft Defender for Office 365 Only: Use the Security & Compliance Center to manage quarantined files</span></span>

> [!NOTE]
> <span data-ttu-id="9cdec-242">本节中隔离文件的过程仅适用于 Microsoft Defender for Office 365 Plan 1 和 Plan 2 订阅者。</span><span class="sxs-lookup"><span data-stu-id="9cdec-242">The procedures for quarantined files in this section are available only to Microsoft Defender for Office 365 Plan 1 and Plan 2 subscribers.</span></span>

<span data-ttu-id="9cdec-243">在具有 Defender for Office 365 的组织中，管理员可以在 SharePoint Online、OneDrive for Business 和 Microsoft 团队中管理隔离的文件。</span><span class="sxs-lookup"><span data-stu-id="9cdec-243">In organizations with Defender for Office 365, admins can manage quarantined files in SharePoint Online, OneDrive for Business, and Microsoft Teams.</span></span> <span data-ttu-id="9cdec-244">若要对这些文件启用保护，请参阅 [打开适用于 SharePoint、OneDrive 和 Microsoft 团队的 ATP](turn-on-atp-for-spo-odb-and-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="9cdec-244">To enable protection for these files, see [Turn on ATP for SharePoint, OneDrive, and Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md).</span></span>

### <a name="view-quarantined-files"></a><span data-ttu-id="9cdec-245">查看隔离的文件</span><span class="sxs-lookup"><span data-stu-id="9cdec-245">View quarantined files</span></span>

1. <span data-ttu-id="9cdec-246">在安全与合规中心内，依次转到“威胁管理”\>“审阅”\>“隔离”。</span><span class="sxs-lookup"><span data-stu-id="9cdec-246">In the Security and Compliance Center, go to **Threat Management** \> **Review** \> **Quarantine**.</span></span>

2. <span data-ttu-id="9cdec-247">将已 **隔离的视图** 更改为值 **文件** 。</span><span class="sxs-lookup"><span data-stu-id="9cdec-247">Change **View quarantined** to the value **files**.</span></span> <span data-ttu-id="9cdec-248">您可以通过单击可用的列标题对字段进行排序。</span><span class="sxs-lookup"><span data-stu-id="9cdec-248">You can sort on a field by clicking on an available column header.</span></span>

3. <span data-ttu-id="9cdec-249">若要对结果进行排序，可以单击可用列标题。</span><span class="sxs-lookup"><span data-stu-id="9cdec-249">You can sort the results by clicking on an available column header.</span></span> <span data-ttu-id="9cdec-250">单击“修改列”最多可显示七列。</span><span class="sxs-lookup"><span data-stu-id="9cdec-250">Click **Modify columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="9cdec-251">默认列以星号 (<sup>\*</sup>) 标记：</span><span class="sxs-lookup"><span data-stu-id="9cdec-251">The default columns are marked with an asterisk (<sup>\*</sup>):</span></span>

   - <span data-ttu-id="9cdec-252">**用户**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="9cdec-252">**User**<sup>\*</sup></span></span>
   - <span data-ttu-id="9cdec-253">**您的位置**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="9cdec-253">**Location**<sup>\*</sup></span></span>
   - <span data-ttu-id="9cdec-254">**文件名**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="9cdec-254">**File name**<sup>\*</sup></span></span>
   - <span data-ttu-id="9cdec-255">**文件 URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="9cdec-255">**File URL**<sup>\*</sup></span></span>
   - <span data-ttu-id="9cdec-256">**文件大小**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="9cdec-256">**File Size**<sup>\*</sup></span></span>
   - <span data-ttu-id="9cdec-257">**到期时间**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="9cdec-257">**Expires**<sup>\*</sup></span></span>
   - <span data-ttu-id="9cdec-258">**释放?**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="9cdec-258">**Released?**<sup>\*</sup></span></span>
   - <span data-ttu-id="9cdec-259">**检测人**</span><span class="sxs-lookup"><span data-stu-id="9cdec-259">**Detected by**</span></span>
   - <span data-ttu-id="9cdec-260">**修改时间**</span><span class="sxs-lookup"><span data-stu-id="9cdec-260">**Modified by time**</span></span>

4. <span data-ttu-id="9cdec-261">若要筛选结果，请单击“筛选器”。</span><span class="sxs-lookup"><span data-stu-id="9cdec-261">To filter the results, click **Filter**.</span></span> <span data-ttu-id="9cdec-262">以下筛选器可用：</span><span class="sxs-lookup"><span data-stu-id="9cdec-262">The available filters are:</span></span>

   - <span data-ttu-id="9cdec-263">**到期时间** ：按邮件的隔离到期时间筛选：</span><span class="sxs-lookup"><span data-stu-id="9cdec-263">**Expires time** : Filter messages by when they will expire from quarantine:</span></span>
     - <span data-ttu-id="9cdec-264">**今天**</span><span class="sxs-lookup"><span data-stu-id="9cdec-264">**Today**</span></span>
     - <span data-ttu-id="9cdec-265">**未来 2 天**</span><span class="sxs-lookup"><span data-stu-id="9cdec-265">**Next 2 days**</span></span>
     - <span data-ttu-id="9cdec-266">**未来 7 天**</span><span class="sxs-lookup"><span data-stu-id="9cdec-266">**Next 7 days**</span></span>
     - <span data-ttu-id="9cdec-267">自定义日期/时间范围。</span><span class="sxs-lookup"><span data-stu-id="9cdec-267">A custom date/time range.</span></span>
   - <span data-ttu-id="9cdec-268">**接收时间**</span><span class="sxs-lookup"><span data-stu-id="9cdec-268">**Received time**</span></span>
   - <span data-ttu-id="9cdec-269">**隔离原因** ：唯一的可用值是 **恶意软件** 。</span><span class="sxs-lookup"><span data-stu-id="9cdec-269">**Quarantine reason** : The only available value is **Malware**.</span></span>
   - <span data-ttu-id="9cdec-270">**策略类型**</span><span class="sxs-lookup"><span data-stu-id="9cdec-270">**Policy type**</span></span>

<span data-ttu-id="9cdec-271">找到特定的隔离文件后，选择该文件查看其详细信息，并对其执行操作 (例如，查看、释放、下载或删除邮件) 。</span><span class="sxs-lookup"><span data-stu-id="9cdec-271">After you find a specific quarantined file, select the file to view details about it, and to take action on it (for example, view, release, download, or delete the message).</span></span>

#### <a name="view-quarantined-file-details"></a><span data-ttu-id="9cdec-272">查看隔离的文件详细信息</span><span class="sxs-lookup"><span data-stu-id="9cdec-272">View quarantined file details</span></span>

<span data-ttu-id="9cdec-273">当您选择列表中的某个文件时， **详细信息** 弹出窗格中将显示以下文件详细信息：</span><span class="sxs-lookup"><span data-stu-id="9cdec-273">When you select a file in the list, the following file details appear in the **Details** flyout pane:</span></span>

- <span data-ttu-id="9cdec-274">**文件名**</span><span class="sxs-lookup"><span data-stu-id="9cdec-274">**File Name**</span></span>
- <span data-ttu-id="9cdec-275">**文件 url** ：定义文件位置的 url (例如，在 SharePoint Online) 中。</span><span class="sxs-lookup"><span data-stu-id="9cdec-275">**File URL** : URL that defines the location of the file (for example, in SharePoint Online).</span></span>
- <span data-ttu-id="9cdec-276">**在上检测到的恶意内容** 文件被隔离的日期/时间。</span><span class="sxs-lookup"><span data-stu-id="9cdec-276">**Malicious content detected on** The date/time the file was quarantined.</span></span>
- <span data-ttu-id="9cdec-277">**过期** 时间：将从隔离区中删除文件的日期。</span><span class="sxs-lookup"><span data-stu-id="9cdec-277">**Expires** : The date when the file will be deleted from quarantine.</span></span>
- <span data-ttu-id="9cdec-278">**检测依据** ：适用于 Office 365 或 Microsoft 反恶意软件引擎的 Defender。</span><span class="sxs-lookup"><span data-stu-id="9cdec-278">**Detected By** : Defender for Office 365 or Microsoft's anti-malware engine.</span></span>
- <span data-ttu-id="9cdec-279">**释放?**</span><span class="sxs-lookup"><span data-stu-id="9cdec-279">**Released?**</span></span>
- <span data-ttu-id="9cdec-280">**恶意软件名称**</span><span class="sxs-lookup"><span data-stu-id="9cdec-280">**Malware Name**</span></span>
- <span data-ttu-id="9cdec-281">**文档 ID** ：文档的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="9cdec-281">**Document ID** : A unique identifier for the document.</span></span>
- <span data-ttu-id="9cdec-282">**文件大小** ：以 KB (kb) 。</span><span class="sxs-lookup"><span data-stu-id="9cdec-282">**File Size** : In kilobytes (KB).</span></span>
- <span data-ttu-id="9cdec-283">**组织** 您的组织的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="9cdec-283">**Organization** Your organization's unique ID.</span></span>
- <span data-ttu-id="9cdec-284">**上次修改时间**</span><span class="sxs-lookup"><span data-stu-id="9cdec-284">**Last modified**</span></span>
- <span data-ttu-id="9cdec-285">**修改者** ：上次修改文件的用户。</span><span class="sxs-lookup"><span data-stu-id="9cdec-285">**Modified By** : The user who last modified the file.</span></span>
- <span data-ttu-id="9cdec-286">**安全哈希算法 256-bit (SHA-256) 值** ：可以使用此哈希值标识其他信誉存储区中的文件或环境中其他位置的文件。</span><span class="sxs-lookup"><span data-stu-id="9cdec-286">**Secure Hash Algorithm 256-bit (SHA-256) value** : You can use this hash value to identify the file in other reputation stores or in other locations in your environment.</span></span>

### <a name="take-action-on-quarantined-files"></a><span data-ttu-id="9cdec-287">对隔离的文件执行操作</span><span class="sxs-lookup"><span data-stu-id="9cdec-287">Take action on quarantined files</span></span>

<span data-ttu-id="9cdec-288">选择列表中的文件时，可以对 " **详细信息** " 弹出窗口中的文件执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="9cdec-288">When you select a file in the list, you can take the following actions on the file in the **Details** flyout pane:</span></span>

- <span data-ttu-id="9cdec-289">**释放文件** ：选择 (默认值) 或 **将报告文件取消选择 Microsoft 进行分析** ，然后单击 " **释放文件** "。</span><span class="sxs-lookup"><span data-stu-id="9cdec-289">**Release files** : Select (default) or unselect **Report files to Microsoft for analysis** , and then click **Release files**.</span></span>
- <span data-ttu-id="9cdec-290">**下载文件**</span><span class="sxs-lookup"><span data-stu-id="9cdec-290">**Download file**</span></span>
- <span data-ttu-id="9cdec-291">**从隔离区中删除文件**</span><span class="sxs-lookup"><span data-stu-id="9cdec-291">**Remove file from quarantine**</span></span>

<span data-ttu-id="9cdec-292">如果不释放或删除这些文件，则在默认的隔离保留期过期后，这些文件将被删除。</span><span class="sxs-lookup"><span data-stu-id="9cdec-292">If you don't release or remove the files, they will be deleted after the default quarantine retention period expires.</span></span>

#### <a name="actions-on-multiple-quarantined-files"></a><span data-ttu-id="9cdec-293">对多个隔离文件执行的操作</span><span class="sxs-lookup"><span data-stu-id="9cdec-293">Actions on multiple quarantined files</span></span>

<span data-ttu-id="9cdec-294">当您在列表中选择多个隔离文件时 (最多为100个) 时，将显示 " **批量操作** " 浮出控件窗格，可在其中执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="9cdec-294">When you select multiple quarantined files in the list (up to 100), the **Bulk actions** flyout pane appears where you can take the following actions:</span></span>

- <span data-ttu-id="9cdec-295">**释放文件**</span><span class="sxs-lookup"><span data-stu-id="9cdec-295">**Release files**</span></span>
- <span data-ttu-id="9cdec-296">**删除文件** ：在显示的警告中单击 **"是"** 后，会立即删除文件。</span><span class="sxs-lookup"><span data-stu-id="9cdec-296">**Delete files** :  After you click **Yes** in the warning that appears, the files are immediately deleted.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-view-and-manage-quarantined-messages-and-files"></a><span data-ttu-id="9cdec-297">使用 Exchange Online PowerShell 或独立 EOP PowerShell 查看和管理隔离的邮件和文件</span><span class="sxs-lookup"><span data-stu-id="9cdec-297">Use Exchange Online PowerShell or standalone EOP PowerShell to view and manage quarantined messages and files</span></span>

<span data-ttu-id="9cdec-298">用于查看和管理隔离区中的邮件和文件的 cmdlet 为：</span><span class="sxs-lookup"><span data-stu-id="9cdec-298">The cmdlets you use to view and manages messages and files in quarantine are:</span></span>

- [<span data-ttu-id="9cdec-299">删除-Get-quarantinemessage</span><span class="sxs-lookup"><span data-stu-id="9cdec-299">Delete-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/delete-quarantinemessage)

- [<span data-ttu-id="9cdec-300">Export-Get-quarantinemessage</span><span class="sxs-lookup"><span data-stu-id="9cdec-300">Export-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/export-quarantinemessage)

- [<span data-ttu-id="9cdec-301">Get-quarantinemessage</span><span class="sxs-lookup"><span data-stu-id="9cdec-301">Get-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-quarantinemessage)

- <span data-ttu-id="9cdec-302">[Preview-get-quarantinemessage](https://docs.microsoft.com/powershell/module/exchange/preview-quarantinemessage)：请注意，此 cmdlet 仅适用于邮件，而不适用于 SharePoint Online、OneDrive for Business 或团队的 ATP 中的恶意软件文件。</span><span class="sxs-lookup"><span data-stu-id="9cdec-302">[Preview-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/preview-quarantinemessage): Note that this cmdlet is only for messages, not malware files from ATP for SharePoint Online, OneDrive for Business, or Teams.</span></span>

- [<span data-ttu-id="9cdec-303">发布-Get-quarantinemessage</span><span class="sxs-lookup"><span data-stu-id="9cdec-303">Release-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/release-quarantinemessage)
