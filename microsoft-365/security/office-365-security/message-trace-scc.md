---
title: 安全与合规中心内的消息跟踪
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
localization_priority: Normal
ms.assetid: 3e64f99d-ac33-4aba-91c5-9cb4ca476803
ms.custom:
- seo-marvel-apr2020
description: 管理员可以使用安全与合规中心&跟踪来了解邮件发生了什么。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 1ce26f7a6cdad15019e2b40eb6f8746e5723d4f0
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290653"
---
# <a name="message-trace-in-the-security--compliance-center"></a><span data-ttu-id="23cc6-103">安全与合规中心内的消息跟踪</span><span class="sxs-lookup"><span data-stu-id="23cc6-103">Message trace in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="23cc6-104">**适用对象**</span><span class="sxs-lookup"><span data-stu-id="23cc6-104">**Applies to**</span></span>
- [<span data-ttu-id="23cc6-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="23cc6-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="23cc6-106">Microsoft Defender for Office 365 计划 1 和计划 2</span><span class="sxs-lookup"><span data-stu-id="23cc6-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="23cc6-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="23cc6-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

## <a name="message-trace-features"></a><span data-ttu-id="23cc6-108">邮件跟踪功能</span><span class="sxs-lookup"><span data-stu-id="23cc6-108">Message trace features</span></span>

<span data-ttu-id="23cc6-109">安全与合规中心&跟踪电子邮件在通过 Exchange Online 组织时跟踪邮件。</span><span class="sxs-lookup"><span data-stu-id="23cc6-109">Message trace in the Security & Compliance Center follows email messages as they travel through your Exchange Online organization.</span></span> <span data-ttu-id="23cc6-110">您可以确定服务是否接收、拒绝、延迟或传递了邮件。</span><span class="sxs-lookup"><span data-stu-id="23cc6-110">You can determine if a message was received, rejected, deferred, or delivered by the service.</span></span> <span data-ttu-id="23cc6-111">它还显示邮件在达到最终状态之前对邮件采取的操作。</span><span class="sxs-lookup"><span data-stu-id="23cc6-111">It also shows what actions were taken on the message before it reached its final status.</span></span>

<span data-ttu-id="23cc6-112">安全与合规&中心中的邮件跟踪在 Exchange 管理中心 EAC (中提供的原始邮件跟踪) 。</span><span class="sxs-lookup"><span data-stu-id="23cc6-112">Message trace in the Security & Compliance Center improves upon the original message trace that was available in the Exchange admin center (EAC).</span></span> <span data-ttu-id="23cc6-113">您可以使用邮件跟踪中的信息来有效回答用户有关邮件发生了什么问题、解决邮件流问题并验证策略更改。</span><span class="sxs-lookup"><span data-stu-id="23cc6-113">You can use the information from message trace to efficiently answer user questions about what happened to messages, troubleshoot mail flow issues, and validate policy changes.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="23cc6-114">若要执行邮件跟踪，你需要是组织管理、合规性管理或技术支持角色组的成员。</span><span class="sxs-lookup"><span data-stu-id="23cc6-114">To do a message trace, you need to be a member of the Organization Management, Compliance Management or Help Desk role groups.</span></span> <span data-ttu-id="23cc6-115">有关详细信息，请参阅[安全与合规中心中的权限](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="23cc6-115">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
>
> - <span data-ttu-id="23cc6-116">结果中显示的邮件的最大数量取决于您选择的报告类型 ("选择报告类型"部分了解详细信息) 。 [](#choose-report-type)</span><span class="sxs-lookup"><span data-stu-id="23cc6-116">The maximum number of messages that are displayed in the results depends on the report type you selected (see the [Choose report type](#choose-report-type) section for details).</span></span> <span data-ttu-id="23cc6-117">Exchange Online PowerShell 或独立 EOP PowerShell 中的 [Get-HistoricalSearch](https://docs.microsoft.com/powershell/module/exchange/get-historicalsearch) cmdlet 将返回结果中的所有邮件。</span><span class="sxs-lookup"><span data-stu-id="23cc6-117">The [Get-HistoricalSearch](https://docs.microsoft.com/powershell/module/exchange/get-historicalsearch) cmdlet in Exchange Online PowerShell or standalone EOP PowerShell returns all messages in the results.</span></span>

## <a name="open-message-trace"></a><span data-ttu-id="23cc6-118">打开邮件跟踪</span><span class="sxs-lookup"><span data-stu-id="23cc6-118">Open message trace</span></span>

1. <span data-ttu-id="23cc6-119">打开安全&合规中心 <https://protection.office.com> 。</span><span class="sxs-lookup"><span data-stu-id="23cc6-119">Open the Security & Compliance Center at <https://protection.office.com>.</span></span>

2. <span data-ttu-id="23cc6-120">展开 **"邮件流**"，然后选择"**邮件跟踪"。**</span><span class="sxs-lookup"><span data-stu-id="23cc6-120">Expand **Mail flow**, and then select **Message trace**.</span></span>

## <a name="message-trace-page"></a><span data-ttu-id="23cc6-121">邮件跟踪页</span><span class="sxs-lookup"><span data-stu-id="23cc6-121">Message trace page</span></span>

<span data-ttu-id="23cc6-122">在这里，可以通过单击"开始跟踪"按钮来启动 **新的默认跟踪** 。</span><span class="sxs-lookup"><span data-stu-id="23cc6-122">From here you can start a new default trace by clicking on the **Start a trace** button.</span></span> <span data-ttu-id="23cc6-123">这将搜索过去两天内所有发件人和收件人的所有邮件。</span><span class="sxs-lookup"><span data-stu-id="23cc6-123">This will search for all messages for all senders and recipients for the last two days.</span></span> <span data-ttu-id="23cc6-124">或者，您可以使用可用查询类别中的其中一个存储查询，并像现在一样运行它们，或者将它们用作你自己的查询的起点：</span><span class="sxs-lookup"><span data-stu-id="23cc6-124">Or you can use one of the stored queries from the available query categories and either run them as-is or use them as starting points for your own queries:</span></span>

- <span data-ttu-id="23cc6-125">**默认查询**：Microsoft 365 提供的内置查询。</span><span class="sxs-lookup"><span data-stu-id="23cc6-125">**Default queries**: Built-in queries provided by Microsoft 365.</span></span>

- <span data-ttu-id="23cc6-126">**自定义查询**：由组织中管理员保存供将来使用的查询。</span><span class="sxs-lookup"><span data-stu-id="23cc6-126">**Custom queries**: Queries saved by admins in your organization for future use.</span></span>

- <span data-ttu-id="23cc6-127">**自动保存的查询**：最近运行的十个查询。</span><span class="sxs-lookup"><span data-stu-id="23cc6-127">**Autosaved queries**: The last ten most recently run queries.</span></span> <span data-ttu-id="23cc6-128">此列表使你能够轻松从你离开的地方继续操作。</span><span class="sxs-lookup"><span data-stu-id="23cc6-128">This list makes it simple to pick up where you left off.</span></span>

<span data-ttu-id="23cc6-129">此外，此页上还有一个可供下载的请求的可下载报告部分，以及可供下载的报告本身。</span><span class="sxs-lookup"><span data-stu-id="23cc6-129">Also on this page is a **Downloadable reports** section for the requests you've submitted, as well as the reports themselves when they're are available for download.</span></span>

## <a name="options-for-a-new-message-trace"></a><span data-ttu-id="23cc6-130">新邮件跟踪的选项</span><span class="sxs-lookup"><span data-stu-id="23cc6-130">Options for a new message trace</span></span>

### <a name="filter-by-senders-and-recipients"></a><span data-ttu-id="23cc6-131">按发件人和收件人筛选</span><span class="sxs-lookup"><span data-stu-id="23cc6-131">Filter by senders and recipients</span></span>

<span data-ttu-id="23cc6-132">默认值为"**所有发件人**"和"所有收件人"，但可以使用下列字段筛选结果：</span><span class="sxs-lookup"><span data-stu-id="23cc6-132">The default values are **All senders** and **All recipients**, but you can use the following fields to filter the results:</span></span>

- <span data-ttu-id="23cc6-133">**通过这些人员**：单击此字段以从组织选择一个或多个发件人。</span><span class="sxs-lookup"><span data-stu-id="23cc6-133">**By these people**: Click in this field to select one or more senders from your organization.</span></span> <span data-ttu-id="23cc6-134">您还可以开始键入名称，列表中的项目将按键入的内容进行筛选，这非常类似于搜索页面的行为方式。</span><span class="sxs-lookup"><span data-stu-id="23cc6-134">You can also start to type a name and the items in the list will be filtered by what you've typed, much like how a search page behaves.</span></span>

- <span data-ttu-id="23cc6-135">**对于这些人员**：单击此字段可选择贵组织中一个或多个收件人。</span><span class="sxs-lookup"><span data-stu-id="23cc6-135">**To these people**: Click in this field to select one or more recipients in your organization.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="23cc6-136">您还可以键入外部发件人和收件人的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="23cc6-136">You can also type the email addresses of external senders and recipients.</span></span> <span data-ttu-id="23cc6-137">通配符 (例如，) ，但不能同时在同一字段中使用多个通配符 `*@contoso.com` 条目。</span><span class="sxs-lookup"><span data-stu-id="23cc6-137">Wildcards are supported (for example, `*@contoso.com`), but you can't use multiple wildcard entries in the same field at the same time.</span></span>
>
> - <span data-ttu-id="23cc6-138">您可以粘贴多个发件人或收件人列表，这些列表用分号 `;` () 。</span><span class="sxs-lookup"><span data-stu-id="23cc6-138">You can paste multiple senders or recipients lists separated by semicolons (`;`).</span></span> <span data-ttu-id="23cc6-139">空格 `\s` () 、回车符 `\r` () 或下一行 `\n` () 。</span><span class="sxs-lookup"><span data-stu-id="23cc6-139">spaces (`\s`), carriage returns (`\r`), or next lines (`\n`).</span></span>

### <a name="time-range"></a><span data-ttu-id="23cc6-140">时间范围</span><span class="sxs-lookup"><span data-stu-id="23cc6-140">Time range</span></span>

<span data-ttu-id="23cc6-141">默认值为 **2 天**，但可以指定最多 90 天的日期/时间范围。</span><span class="sxs-lookup"><span data-stu-id="23cc6-141">The default value is **2 days**, but you can specify date/time ranges of up to 90 days.</span></span> <span data-ttu-id="23cc6-142">使用日期/时间范围时，请考虑这些问题：</span><span class="sxs-lookup"><span data-stu-id="23cc6-142">When you use date/time ranges, consider these issues:</span></span>

- <span data-ttu-id="23cc6-143">默认情况下，使用时间线选择 **滑块** 视图中的时区。</span><span class="sxs-lookup"><span data-stu-id="23cc6-143">By default, you select the time range in **Slider** view using a time line.</span></span> <span data-ttu-id="23cc6-144">只能选择显示的日或时间设置。</span><span class="sxs-lookup"><span data-stu-id="23cc6-144">You can only select the day or time settings that are displayed.</span></span> <span data-ttu-id="23cc6-145">尝试选择一个介于两者之间的值将起始/结束气泡贴靠到最近显示的设置。</span><span class="sxs-lookup"><span data-stu-id="23cc6-145">Trying to select an in-between value will snap the start/end bubble to the nearest displayed setting.</span></span>

  ![安全与合规中心中新邮件跟踪中的滑块&范围](../../media/55a9e9c1-f7d5-4047-b217-824e8b976bcb.png)

  <span data-ttu-id="23cc6-147">但是，还可以切换到自定义视图，可在其中指定开始日期和结束日期值 (包括时间) ，还可以选择日期/时间范围的时区。 </span><span class="sxs-lookup"><span data-stu-id="23cc6-147">But, you can also switch to **Custom** view where you can specify the **Start date** and **End date** values (including times), and you can also select the **Time zone** for the date/time range.</span></span> <span data-ttu-id="23cc6-148">请注意， **时区设置** 适用于查询输入和查询结果。</span><span class="sxs-lookup"><span data-stu-id="23cc6-148">Note that the **Time zone** setting applies to both your query inputs and your query results.</span></span>

  ![安全与合规中心中新邮件跟踪中的&范围](../../media/ed4c8d50-9ea5-4694-93f9-ee3ab6660b4f.png)

  <span data-ttu-id="23cc6-150">在 10 天或更近的时间，结果可立即作为摘要 **报告** 提供。</span><span class="sxs-lookup"><span data-stu-id="23cc6-150">For 10 days or less, the results are available instantly as a **Summary** report.</span></span> <span data-ttu-id="23cc6-151">如果指定的时间范围略大于 10 天，结果将延迟，因为它们仅作为可下载的 CSV 文件 (增强摘要或扩展报告) 。  </span><span class="sxs-lookup"><span data-stu-id="23cc6-151">If you specify a time range that's even slightly greater than 10 days, the results will be delayed as they are only available as a downloadable CSV file ( **Enhanced summary** or **Extended** reports).</span></span>

  <span data-ttu-id="23cc6-152">有关不同报告类型的信息，请参阅本文中的 ["选择](#choose-report-type) 报告类型"部分。</span><span class="sxs-lookup"><span data-stu-id="23cc6-152">For more information about the different report types, see the [Choose report type](#choose-report-type) section in this article.</span></span>

  > [!NOTE]
  > <span data-ttu-id="23cc6-153">使用存档的邮件跟踪数据准备增强摘要和扩展报告，报告可能需要几个小时才能下载。</span><span class="sxs-lookup"><span data-stu-id="23cc6-153">Enhanced summary and Extended reports are prepared using archived message trace data, and it can take up to several hours before your report is available for download.</span></span> <span data-ttu-id="23cc6-154">根据有多少其他管理员还在同一时间提交了报告请求，您可能还注意到在处理排队请求之前出现延迟。</span><span class="sxs-lookup"><span data-stu-id="23cc6-154">Depending on how many other admins have also submitted report requests around the same time, you might also notice a delay before processing starts for your queued request.</span></span>

- <span data-ttu-id="23cc6-155">在 Slider 视图中 **保存** 查询可保存相对 (，例如，从今天开始 3) 。</span><span class="sxs-lookup"><span data-stu-id="23cc6-155">Saving a query in **Slider** view saves the relative time range (for example, 3 days from today).</span></span> <span data-ttu-id="23cc6-156">在 **自定义视图中保存** 查询可保存绝对日期/时间范围 (例如，2018-05-06 13：00 到 2018-05-08 18：00) 。</span><span class="sxs-lookup"><span data-stu-id="23cc6-156">Saving a query in **Custom** view saves the absolute date/time range (for example, 2018-05-06 13:00 to 2018-05-08 18:00).</span></span>

### <a name="more-search-options"></a><span data-ttu-id="23cc6-157">更多搜索选项</span><span class="sxs-lookup"><span data-stu-id="23cc6-157">More search options</span></span>

#### <a name="delivery-status"></a><span data-ttu-id="23cc6-158">传递状态</span><span class="sxs-lookup"><span data-stu-id="23cc6-158">Delivery status</span></span>

<span data-ttu-id="23cc6-159">可以将默认值 **"所有"** 保持选中状态，也可以选择下列值之一来筛选结果：</span><span class="sxs-lookup"><span data-stu-id="23cc6-159">You can leave the default value **All** selected, or you can select one of the following values to filter the results:</span></span>

- <span data-ttu-id="23cc6-160">**已** 传递：邮件已成功传递到预期目标。</span><span class="sxs-lookup"><span data-stu-id="23cc6-160">**Delivered**: The message was successfully delivered to the intended destination.</span></span>

- <span data-ttu-id="23cc6-161">**挂起**：正在尝试或重新尝试传递邮件。</span><span class="sxs-lookup"><span data-stu-id="23cc6-161">**Pending**: Delivery of the message is being attempted or re-attempted.</span></span>

- <span data-ttu-id="23cc6-162">**展开**：在将通讯组收件人发送给该组的单个成员之前，展开通讯组收件人。</span><span class="sxs-lookup"><span data-stu-id="23cc6-162">**Expanded**: A distribution group recipient was expanded before delivery to the individual members of the group.</span></span>

- <span data-ttu-id="23cc6-163">**失败**：邮件未送达。</span><span class="sxs-lookup"><span data-stu-id="23cc6-163">**Failed**: The message was not delivered.</span></span>

- <span data-ttu-id="23cc6-164">**已隔离**：邮件被隔离 (垃圾邮件、批量邮件或网络钓鱼邮件) 。</span><span class="sxs-lookup"><span data-stu-id="23cc6-164">**Quarantined**: The message was quarantined (as spam, bulk mail, or phishing).</span></span> <span data-ttu-id="23cc6-165">有关详细信息，请参阅 [EOP 中的隔离电子邮件](quarantine-email-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="23cc6-165">For more information, see [Quarantined email messages in EOP](quarantine-email-messages.md).</span></span>

- <span data-ttu-id="23cc6-166">**筛选为垃圾邮件**：邮件被标识为垃圾邮件，并且被拒绝或阻止 (未隔离) 。</span><span class="sxs-lookup"><span data-stu-id="23cc6-166">**Filtered as spam**: The message was identified spam, and was rejected or blocked (not quarantined).</span></span>

- <span data-ttu-id="23cc6-167">**获取状态：** 该邮件最近由 Microsoft 365 接收，但尚没有其他状态数据可用。</span><span class="sxs-lookup"><span data-stu-id="23cc6-167">**Getting status:** The message was recently received by Microsoft 365, but no other status data is yet available.</span></span> <span data-ttu-id="23cc6-168">几分钟后重新检查。</span><span class="sxs-lookup"><span data-stu-id="23cc6-168">Check back in a few minutes.</span></span>

> [!NOTE]
> <span data-ttu-id="23cc6-169">"**挂起"、"\*\*\*\*隔离"** 和"**筛选为** 垃圾邮件"的值仅适用于少于 10 天的搜索。</span><span class="sxs-lookup"><span data-stu-id="23cc6-169">The values **Pending,** **Quarantined**, and **Filter as spam** are only available for searches less than 10 days.</span></span> <span data-ttu-id="23cc6-170">此外，实际传递状态和报告的传递状态之间可能有 5 到 10 分钟的延迟。</span><span class="sxs-lookup"><span data-stu-id="23cc6-170">Also, there might be a 5 to 10 minute delay between the actual and reported delivery status.</span></span>

#### <a name="message-id"></a><span data-ttu-id="23cc6-171">邮件 ID</span><span class="sxs-lookup"><span data-stu-id="23cc6-171">Message ID</span></span>

<span data-ttu-id="23cc6-172">This is the internet message ID (also known as the Client ID) that is found in the **Message-ID：** header field in the message header.</span><span class="sxs-lookup"><span data-stu-id="23cc6-172">This is the internet message ID (also known as the Client ID) that's found in the **Message-ID:** header field in the message header.</span></span> <span data-ttu-id="23cc6-173">用户可以提供此值来调查特定邮件。</span><span class="sxs-lookup"><span data-stu-id="23cc6-173">Users can give you this value to investigate specific messages.</span></span>

<span data-ttu-id="23cc6-174">该值在邮件生存期内是常量。</span><span class="sxs-lookup"><span data-stu-id="23cc6-174">This value is constant for the lifetime of the message.</span></span> <span data-ttu-id="23cc6-175">对于在 Microsoft 365 或 Exchange 中创建的邮件，该值的格式为，包括括号 `<GUID@ServerFQDN>` \< \> () 。</span><span class="sxs-lookup"><span data-stu-id="23cc6-175">For messages created in Microsoft 365 or Exchange, the value is in the format `<GUID@ServerFQDN>`, including the angle brackets (\< \>).</span></span> <span data-ttu-id="23cc6-176">例如，`<d9683b4c-127b-413a-ae2e-fa7dfb32c69d@DM3NAM06BG401.Eop-nam06.prod.protection.outlook.com>`。</span><span class="sxs-lookup"><span data-stu-id="23cc6-176">For example, `<d9683b4c-127b-413a-ae2e-fa7dfb32c69d@DM3NAM06BG401.Eop-nam06.prod.protection.outlook.com>`.</span></span> <span data-ttu-id="23cc6-177">其他邮件系统可能使用不同的语法或值。</span><span class="sxs-lookup"><span data-stu-id="23cc6-177">Other messaging systems might use different syntax or values.</span></span> <span data-ttu-id="23cc6-178">此值应该是唯一的，但并非所有电子邮件系统都严格遵循此要求。</span><span class="sxs-lookup"><span data-stu-id="23cc6-178">This value is supposed to be unique, but not all email systems strictly follow this requirement.</span></span> <span data-ttu-id="23cc6-179">如果 **Message-ID：** header 字段不存在或对于来自外部源的传入邮件为空，则分配任意值。</span><span class="sxs-lookup"><span data-stu-id="23cc6-179">If the **Message-ID:** header field doesn't exist or is blank for incoming messages from external sources, an arbitrary value is assigned.</span></span>

<span data-ttu-id="23cc6-180">使用消息 **ID** 筛选结果时，请务必包含完整字符串，包括任何尖括号。</span><span class="sxs-lookup"><span data-stu-id="23cc6-180">When you use **Message ID** to filter the results, be sure to include the full string, including any angle brackets.</span></span>

#### <a name="direction"></a><span data-ttu-id="23cc6-181">Direction</span><span class="sxs-lookup"><span data-stu-id="23cc6-181">Direction</span></span>

<span data-ttu-id="23cc6-182">可以将默认值 **"** 所有"保留为选中状态，也可以选择"发送到组织中收件人的入站 **(** 邮件") 或"从组织 **)** 用户发送的出站 (邮件"以筛选结果。</span><span class="sxs-lookup"><span data-stu-id="23cc6-182">You can leave the default value **All** selected, or you can select **Inbound** (messages sent to recipients in your organization) or **Outbound** (messages sent from users in your organization) to filter the results.</span></span>

#### <a name="original-client-ip-address"></a><span data-ttu-id="23cc6-183">原始客户端 IP 地址</span><span class="sxs-lookup"><span data-stu-id="23cc6-183">Original client IP address</span></span>

<span data-ttu-id="23cc6-184">你可以按客户端 IP 地址提交结果，以调查发送大量垃圾邮件或恶意软件的黑客计算机。</span><span class="sxs-lookup"><span data-stu-id="23cc6-184">You can filer the results by client IP address to investigate hacked computers that are sending large amounts of spam or malware.</span></span> <span data-ttu-id="23cc6-185">尽管这些邮件可能看起来来自多个发件人，但同一台计算机可能会生成所有邮件。</span><span class="sxs-lookup"><span data-stu-id="23cc6-185">Although the messages might appear to come from multiple senders, it's likely that the same computer is generating all of the messages.</span></span>

> [!NOTE]
> <span data-ttu-id="23cc6-186">客户端 IP 地址信息仅在 10 天内可用，并且仅在"增强摘要"或"扩展报告"中可用， (可下载的 CSV) 。</span><span class="sxs-lookup"><span data-stu-id="23cc6-186">The client IP address information is only available for 10 days, and is only available in the **Enhanced summary** or **Extended** reports (downloadable CSV files).</span></span>

### <a name="choose-report-type"></a><span data-ttu-id="23cc6-187">选择报告类型</span><span class="sxs-lookup"><span data-stu-id="23cc6-187">Choose report type</span></span>

<span data-ttu-id="23cc6-188">可用的报告类型包括：</span><span class="sxs-lookup"><span data-stu-id="23cc6-188">The available report types are:</span></span>

- <span data-ttu-id="23cc6-189">**摘要：** 如果时间范围小于 10 天，并且不需要其他筛选选项，则可用。</span><span class="sxs-lookup"><span data-stu-id="23cc6-189">**Summary**: Available if the time range is less than 10 days, and requires no additional filtering options.</span></span> <span data-ttu-id="23cc6-190">单击"搜索"后，结果几乎会立即 **可用**。</span><span class="sxs-lookup"><span data-stu-id="23cc6-190">The results are available almost immediately after you click **Search**.</span></span> <span data-ttu-id="23cc6-191">报告最多返回 20000 个结果。</span><span class="sxs-lookup"><span data-stu-id="23cc6-191">The report returns up to 20000 results.</span></span>

- <span data-ttu-id="23cc6-192">**增强摘要\*\*\*\*或扩展**：这些报告仅作为可下载的 CSV 文件提供，并且需要以下一个或多个筛选选项，而不考虑时间范围：按这些人员、收件人或邮件 **ID。**</span><span class="sxs-lookup"><span data-stu-id="23cc6-192">**Enhanced summary** or **Extended**: These reports are only available as downloadable CSV files, and require one or more of the following filtering options regardless of the time range: **By these people**, **To these people**, or **Message ID**.</span></span> <span data-ttu-id="23cc6-193">您可以为发件人或收件人使用通配符 (例如 \* @contoso.com) 。</span><span class="sxs-lookup"><span data-stu-id="23cc6-193">You can use wildcards for the senders or the recipients (for example, \*@contoso.com).</span></span> <span data-ttu-id="23cc6-194">增强摘要报告最多返回 50000 个结果。</span><span class="sxs-lookup"><span data-stu-id="23cc6-194">The Enhanced summary report returns up to 50000 results.</span></span> <span data-ttu-id="23cc6-195">扩展报告最多返回 1000 个结果。</span><span class="sxs-lookup"><span data-stu-id="23cc6-195">The Extended report returns up to 1000 results.</span></span>

> [!NOTE]
> 
> - <span data-ttu-id="23cc6-196">使用存档的邮件跟踪数据准备增强摘要和扩展报告，可能需要几个小时才能下载报告。</span><span class="sxs-lookup"><span data-stu-id="23cc6-196">Enhanced summary and Extended reports are prepared using archived message trace data, and it can take up to several hours before your report is available to download.</span></span> <span data-ttu-id="23cc6-197">根据有多少其他管理员还在同一时间提交了报告请求，您可能还注意到排队请求开始处理之前出现延迟。</span><span class="sxs-lookup"><span data-stu-id="23cc6-197">Depending on how many other admins have also submitted report requests around the same time, you might also notice a delay before your queued request starts to be processed.</span></span>
> 
> - <span data-ttu-id="23cc6-198">虽然您可以为任意日期/时间范围选择增强摘要或扩展报告，但通常，这两种类型的报告通常尚无法提供最近四小时的存档数据。</span><span class="sxs-lookup"><span data-stu-id="23cc6-198">While you can select an Enhanced summary or Extended report for any date/time range, commonly the last four hours of archived data will not yet be available for these two types of reports.</span></span>

<span data-ttu-id="23cc6-199">单击"下一步"时，将显示一个摘要页，其中列出了所选的筛选选项、报告的唯一 (可编辑) 标题，以及邮件跟踪完成时接收通知的电子邮件地址 (也可以编辑，并且必须在你的组织的接受域) 之一中。</span><span class="sxs-lookup"><span data-stu-id="23cc6-199">When you click **Next**, you're presented with a summary page that lists the filtering options that you selected, a unique (editable) title for the report, and the email address that receives the notification when the message trace completes (also editable, and must be in one of your organization's accepted domains).</span></span> <span data-ttu-id="23cc6-200">单击 **"准备** 报告"提交邮件跟踪。</span><span class="sxs-lookup"><span data-stu-id="23cc6-200">Click **Prepare report** to submit the message trace.</span></span> <span data-ttu-id="23cc6-201">在主 **"邮件跟踪"** 页上，您可以在"可下载的报告"部分查看 **报告** 的状态。</span><span class="sxs-lookup"><span data-stu-id="23cc6-201">On the main **Message trace** page, you can see the status of the report in the **Downloadable reports** section.</span></span>

<span data-ttu-id="23cc6-202">有关在不同报告类型中返回的信息详细信息，请参阅下一节。</span><span class="sxs-lookup"><span data-stu-id="23cc6-202">For more information about the information that's returned in the different report types, see the next section.</span></span>

## <a name="message-trace-results"></a><span data-ttu-id="23cc6-203">邮件跟踪结果</span><span class="sxs-lookup"><span data-stu-id="23cc6-203">Message trace results</span></span>

<span data-ttu-id="23cc6-204">不同的报告类型返回不同级别的信息。</span><span class="sxs-lookup"><span data-stu-id="23cc6-204">The different report types return different levels of information.</span></span> <span data-ttu-id="23cc6-205">以下各节介绍了不同报告中的信息。</span><span class="sxs-lookup"><span data-stu-id="23cc6-205">The information that's available in the different reports is described in the following sections.</span></span>

### <a name="summary-report-output"></a><span data-ttu-id="23cc6-206">摘要报告输出</span><span class="sxs-lookup"><span data-stu-id="23cc6-206">Summary report output</span></span>

<span data-ttu-id="23cc6-207">运行邮件跟踪后，将列出结果，并按最近第一次 (日期/时间) 。</span><span class="sxs-lookup"><span data-stu-id="23cc6-207">After running the message trace, the results will be listed, sorted by descending date/time (most recent first).</span></span>

![安全与合规中心内邮件跟踪&报告结果](../../media/0664bafe-0b03-477b-b571-0b046ac8c977.png)

<span data-ttu-id="23cc6-209">摘要报告包含以下信息：</span><span class="sxs-lookup"><span data-stu-id="23cc6-209">The summary report contains the following information:</span></span>

- <span data-ttu-id="23cc6-210">**日期**：服务使用配置的 UTC 时区接收邮件的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="23cc6-210">**Date**: The date and time at which the message was received by the service, using the configured UTC time zone.</span></span>

- <span data-ttu-id="23cc6-211">**发件人**：发件人的别名域 ( @ *电子邮件地址) 。*</span><span class="sxs-lookup"><span data-stu-id="23cc6-211">**Sender**: The email address of the sender (*alias*@*domain*).</span></span>

- <span data-ttu-id="23cc6-212">**收件人**：收件人的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="23cc6-212">**Recipient**: The email address of the recipient or recipients.</span></span> <span data-ttu-id="23cc6-213">对于发送给多个收件人的邮件，每个收件人有一行。</span><span class="sxs-lookup"><span data-stu-id="23cc6-213">For a message sent to multiple recipients, there's one line per recipient.</span></span> <span data-ttu-id="23cc6-214">如果收件人是通讯组、动态通讯组或启用邮件的安全组，则该组将是第一个收件人，然后该组的每个成员位于单独的行上。</span><span class="sxs-lookup"><span data-stu-id="23cc6-214">If the recipient is a distribution group, dynamic distribution group, or mail-enabled security group, the group will be the first recipient, and then each member of the group is on a separate line.</span></span>

- <span data-ttu-id="23cc6-215">**Subject**： The first 256 characters of the message's **Subject：** field.</span><span class="sxs-lookup"><span data-stu-id="23cc6-215">**Subject**: The first 256 characters of the message's **Subject:** field.</span></span>

- <span data-ttu-id="23cc6-216">**状态**："传递状态"部分 [介绍了这些值](#delivery-status) 。</span><span class="sxs-lookup"><span data-stu-id="23cc6-216">**Status**: These values are described in the [Delivery status](#delivery-status) section.</span></span>

<span data-ttu-id="23cc6-217">默认情况下，将加载前 250 个结果并随时可用。</span><span class="sxs-lookup"><span data-stu-id="23cc6-217">By default, the first 250 results are loaded and readily available.</span></span> <span data-ttu-id="23cc6-218">向下滚动时，加载下一批结果时，会稍微暂停一次。</span><span class="sxs-lookup"><span data-stu-id="23cc6-218">When you scroll down, there's a slight pause as the next batch of results are loaded.</span></span> <span data-ttu-id="23cc6-219">你可以单击"全部加载"以加载最多 10，000 个结果，而不是滚动。</span><span class="sxs-lookup"><span data-stu-id="23cc6-219">Instead of scrolling, you can click **Load all** to load all of the results up to a maximum of 10,000.</span></span>

<span data-ttu-id="23cc6-220">可以单击列标题以按该列中的值以升序或降序对结果进行排序。</span><span class="sxs-lookup"><span data-stu-id="23cc6-220">You can click on the column headers to sort the results by the values in that column in ascending or descending order.</span></span>

<span data-ttu-id="23cc6-221">可以单击 **"筛选结果** "按一列或多列筛选结果。</span><span class="sxs-lookup"><span data-stu-id="23cc6-221">You can click **Filter results** to filter the results by one or more columns.</span></span>

<span data-ttu-id="23cc6-222">在选择一行或多行之后，可以导出结果，方法是单击"导出结果"，然后选择"导出 **所有** 结果"、"导出加载的结果"或"**导出所选内容"。**</span><span class="sxs-lookup"><span data-stu-id="23cc6-222">You can export the results after you've selected one or more rows by clicking **Export results** and then selecting **Export all results**, **Export loaded results**, or **Export selected**.</span></span>

#### <a name="find-related-records-for-this-message"></a><span data-ttu-id="23cc6-223">查找此邮件的相关记录</span><span class="sxs-lookup"><span data-stu-id="23cc6-223">Find related records for this message</span></span>

<span data-ttu-id="23cc6-224">相关邮件记录是共享相同邮件 ID 的记录。</span><span class="sxs-lookup"><span data-stu-id="23cc6-224">Related message records are records that shared the same Message ID.</span></span> <span data-ttu-id="23cc6-225">请记住，即使在两个人之间发送的单个邮件也可以生成多个记录。</span><span class="sxs-lookup"><span data-stu-id="23cc6-225">Remember, even a single message sent between two people can generate multiple records.</span></span> <span data-ttu-id="23cc6-226">当邮件受通讯组扩展、转发、邮件流规则或 (传输规则等影响时，记录) 增加。</span><span class="sxs-lookup"><span data-stu-id="23cc6-226">The number of records increases when the message is affected by distribution group expansion, forwarding, mail flow rules (also known as transport rules), etc.</span></span>

<span data-ttu-id="23cc6-227">选中行的复选框后，可以通过单击出现的"查找相关"按钮或选择"更多选项更多查找此邮件的相关记录"来查找邮件的相关 ![ ](../../media/1ea52bbf-9d00-48ce-9362-307f7f6fb7fe.png) \> ) 。</span><span class="sxs-lookup"><span data-stu-id="23cc6-227">After you select a row's check box, you can find related records for the message by clicking the **Find related** button that appears, or by selecting **More options** ![More](../../media/1ea52bbf-9d00-48ce-9362-307f7f6fb7fe.png) \> **Find related records for this message**).</span></span>

<span data-ttu-id="23cc6-228">有关邮件 ID 详细信息，请参阅本文前面部分的消息 ID 部分。</span><span class="sxs-lookup"><span data-stu-id="23cc6-228">For more information about the Message ID, see the Message ID section earlier in this article.</span></span>

#### <a name="message-trace-details"></a><span data-ttu-id="23cc6-229">邮件跟踪详细信息</span><span class="sxs-lookup"><span data-stu-id="23cc6-229">Message trace details</span></span>

<span data-ttu-id="23cc6-230">在摘要报告输出中，您可以使用以下任一方法查看有关邮件的详细信息：</span><span class="sxs-lookup"><span data-stu-id="23cc6-230">In the summary report output, you can view details about a message by using either of the following methods:</span></span>

- <span data-ttu-id="23cc6-231">选择单击 (中的任意位置（复选框除外）的) 。</span><span class="sxs-lookup"><span data-stu-id="23cc6-231">Select the row (click anywhere in the row except the check box).</span></span>

- <span data-ttu-id="23cc6-232">选中行的复选框，然后单击"**更多选项查看** ![ ](../../media/1ea52bbf-9d00-48ce-9362-307f7f6fb7fe.png) \> **邮件详细信息"。**</span><span class="sxs-lookup"><span data-stu-id="23cc6-232">Select the row's check box and click **More options** ![More](../../media/1ea52bbf-9d00-48ce-9362-307f7f6fb7fe.png) \> **View message details**.</span></span>

   ![双击摘要报告邮件跟踪中的行后的详细信息将&合规中心](../../media/e50ee7cd-810a-4c06-8b58-e56ffd7028d1.png)

<span data-ttu-id="23cc6-234">邮件跟踪详细信息包含摘要报告中未包含的以下其他信息：</span><span class="sxs-lookup"><span data-stu-id="23cc6-234">The message trace details contain the following additional information that's not present in the summary report:</span></span>

- <span data-ttu-id="23cc6-235">**邮件事件**：此部分包含分类，可帮助分类服务对邮件采取的操作。</span><span class="sxs-lookup"><span data-stu-id="23cc6-235">**Message events**: This section contains classifications that help categorize the actions that the service takes on messages.</span></span> <span data-ttu-id="23cc6-236">**您可能遇到的一些** 更有趣的事件是：</span><span class="sxs-lookup"><span data-stu-id="23cc6-236">**Some of the more interesting events** that you might encounter are:</span></span>

  - <span data-ttu-id="23cc6-237">**接收**：服务已接收邮件。</span><span class="sxs-lookup"><span data-stu-id="23cc6-237">**Receive**: The message was received by the service.</span></span>

  - <span data-ttu-id="23cc6-238">**发送**：邮件由服务发送。</span><span class="sxs-lookup"><span data-stu-id="23cc6-238">**Send**: The message was sent by the service.</span></span>

  - <span data-ttu-id="23cc6-239">**失败**：邮件无法传递。</span><span class="sxs-lookup"><span data-stu-id="23cc6-239">**Fail**: The message failed to be delivered.</span></span>

  - <span data-ttu-id="23cc6-240">**传递**：邮件已传递到邮箱。</span><span class="sxs-lookup"><span data-stu-id="23cc6-240">**Deliver**: The message was delivered to a mailbox.</span></span>

  - <span data-ttu-id="23cc6-241">**展开**：邮件已发送到展开的通讯组。</span><span class="sxs-lookup"><span data-stu-id="23cc6-241">**Expand**: The message was sent to a distribution group that was expanded.</span></span>

  - <span data-ttu-id="23cc6-242">**传输**：由于内容转换、邮件收件人限制或代理，收件人被移动到了分词邮件。</span><span class="sxs-lookup"><span data-stu-id="23cc6-242">**Transfer**: Recipients were moved to a bifurcated message because of content conversion, message recipient limits, or agents.</span></span>

  - <span data-ttu-id="23cc6-243">**延迟**：邮件传递延迟，稍后可能会重新尝试。</span><span class="sxs-lookup"><span data-stu-id="23cc6-243">**Defer**: The message delivery was postponed and might be re-attempted later.</span></span>

  - <span data-ttu-id="23cc6-244">**已** 解决：邮件已基于 Active Directory 查找重定向到新的收件人地址。</span><span class="sxs-lookup"><span data-stu-id="23cc6-244">**Resolved**: The message was redirected to a new recipient address based on an Active Directory look up.</span></span> <span data-ttu-id="23cc6-245">当发生这种情况时，原始收件人地址会被列在邮件跟踪中的单独一行，包括邮件的最终传递状态。</span><span class="sxs-lookup"><span data-stu-id="23cc6-245">When this happens, the original recipient address is listed in a separate row in the message trace along with the final delivery status for the message.</span></span>

  > [!NOTE]
  > 
  > - <span data-ttu-id="23cc6-246">成功传递的不均匀邮件将在邮件跟踪中生成多个事件条目。</span><span class="sxs-lookup"><span data-stu-id="23cc6-246">An uneventful message that's successfully delivered will generate multiple **Event** entries in the message trace.</span></span>
  > 
  > - <span data-ttu-id="23cc6-247">此列表不一定详尽。</span><span class="sxs-lookup"><span data-stu-id="23cc6-247">This list is not meant to be exhaustive.</span></span> <span data-ttu-id="23cc6-248">有关更多事件的说明，请参阅 [邮件跟踪日志中的事件类型](https://docs.microsoft.com/Exchange/mail-flow/transport-logs/message-tracking#event-types-in-the-message-tracking-log)。</span><span class="sxs-lookup"><span data-stu-id="23cc6-248">For descriptions of more events, see [Event types in the message tracking log](https://docs.microsoft.com/Exchange/mail-flow/transport-logs/message-tracking#event-types-in-the-message-tracking-log).</span></span> <span data-ttu-id="23cc6-249">请注意，此链接是Exchange Server (Exchange) 主题。</span><span class="sxs-lookup"><span data-stu-id="23cc6-249">Note that this link is an Exchange Server (on-premises Exchange) topic.</span></span>

- <span data-ttu-id="23cc6-250">**详细信息：** 此部分包含以下详细信息：</span><span class="sxs-lookup"><span data-stu-id="23cc6-250">**More information**: This section contains the following details:</span></span>

  - <span data-ttu-id="23cc6-251">**邮件 ID：** 此值在本文前面部分的消息 [ID](#message-id) 部分中介绍。</span><span class="sxs-lookup"><span data-stu-id="23cc6-251">**Message ID**: This value is described in the [Message ID](#message-id) section earlier in this article.</span></span> <span data-ttu-id="23cc6-252">例如，`<d9683b4c-127b-413a-ae2e-fa7dfb32c69d@DM3NAM06BG401.Eop-nam06.prod.protection.outlook.com>`。</span><span class="sxs-lookup"><span data-stu-id="23cc6-252">For example, `<d9683b4c-127b-413a-ae2e-fa7dfb32c69d@DM3NAM06BG401.Eop-nam06.prod.protection.outlook.com>`.</span></span>

  - <span data-ttu-id="23cc6-253">**邮件大小**</span><span class="sxs-lookup"><span data-stu-id="23cc6-253">**Message size**</span></span>

  - <span data-ttu-id="23cc6-254">**来自 IP：** 发送邮件的计算机的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="23cc6-254">**From IP**: The IP address of the computer that sent the message.</span></span> <span data-ttu-id="23cc6-255">对于从 Exchange Online 发送的出站邮件，该值是空值。</span><span class="sxs-lookup"><span data-stu-id="23cc6-255">For outbound messages sent from Exchange Online, this value is blank.</span></span>

  - <span data-ttu-id="23cc6-256">**收件人 IP：** 服务尝试传递邮件的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="23cc6-256">**To IP**: The IP address or addresses where the service attempted to deliver the message.</span></span> <span data-ttu-id="23cc6-257">如果邮件具有多个收件人，则显示这些收件人。</span><span class="sxs-lookup"><span data-stu-id="23cc6-257">If the message has multiple recipients, these are displayed.</span></span> <span data-ttu-id="23cc6-258">对于发送到 Exchange Online 的入站邮件，该值是空值。</span><span class="sxs-lookup"><span data-stu-id="23cc6-258">For inbound messages sent to Exchange Online, this value is blank.</span></span>

### <a name="enhanced-summary-reports"></a><span data-ttu-id="23cc6-259">增强摘要报告</span><span class="sxs-lookup"><span data-stu-id="23cc6-259">Enhanced summary reports</span></span>

<span data-ttu-id="23cc6-260">" (已完成) 摘要报告可在邮件开始跟踪的"可下载报告"部分获得。 </span><span class="sxs-lookup"><span data-stu-id="23cc6-260">Available (completed) Enhanced summary reports are available in the **Downloadable reports** section at the beginning message trace.</span></span> <span data-ttu-id="23cc6-261">报告中提供了以下信息：</span><span class="sxs-lookup"><span data-stu-id="23cc6-261">The following information is available in the report:</span></span>

- <span data-ttu-id="23cc6-262">**origin_timestamp：** 服务最初使用配置的 UTC 时区接收邮件的 <sup>\*</sup> 日期和时间。</span><span class="sxs-lookup"><span data-stu-id="23cc6-262">**origin_timestamp**<sup>\*</sup>: The date and time when the message was initially received by the service, using the configured UTC time zone.</span></span>

- <span data-ttu-id="23cc6-263">**sender_address：** 发件人的电子邮件地址 ( @ *域名) 。*</span><span class="sxs-lookup"><span data-stu-id="23cc6-263">**sender_address**: The sender's email address (*alias*@*domain*).</span></span>

- <span data-ttu-id="23cc6-264">**Recipient_status**：邮件发送给收件人的状态。</span><span class="sxs-lookup"><span data-stu-id="23cc6-264">**Recipient_status**: The status of the delivery of the message to the recipient.</span></span> <span data-ttu-id="23cc6-265">如果邮件已发送给多个收件人，它将以以下格式显示所有收件人和每个收件人的相应状态 \<*email address*\> ## \<*status*\> ：</span><span class="sxs-lookup"><span data-stu-id="23cc6-265">If the message was sent to multiple recipients, it will show all the recipients and the corresponding status for each, in the format: \<*email address*\>##\<*status*\>.</span></span> <span data-ttu-id="23cc6-266">例如：</span><span class="sxs-lookup"><span data-stu-id="23cc6-266">For example:</span></span>

  - <span data-ttu-id="23cc6-267">**##Receive，发送** 意味着邮件已由服务接收并发送到预期目标。</span><span class="sxs-lookup"><span data-stu-id="23cc6-267">**##Receive, Send** means the message was received by the service and was sent to the intended destination.</span></span>

  - <span data-ttu-id="23cc6-268">**##Receive，"** 失败"表示服务已收到邮件，但目标传递失败。</span><span class="sxs-lookup"><span data-stu-id="23cc6-268">**##Receive, Fail** means the message was received by the service but delivery to the intended destination failed.</span></span>

  - <span data-ttu-id="23cc6-269">**##Receive，"** 传递"表示邮件已由服务接收并传递到收件人的邮箱。</span><span class="sxs-lookup"><span data-stu-id="23cc6-269">**##Receive, Deliver** means the message was received by the service and was delivered to the recipient's mailbox.</span></span>

- <span data-ttu-id="23cc6-270">**message_subject：** 邮件的主题字段的前 256 **个字符。**</span><span class="sxs-lookup"><span data-stu-id="23cc6-270">**message_subject**: The first 256 characters of the message's **Subject** field.</span></span>

- <span data-ttu-id="23cc6-271">**total_bytes：** 邮件的大小（以字节为单位，包括附件）。</span><span class="sxs-lookup"><span data-stu-id="23cc6-271">**total_bytes**: The size of the message in bytes, including attachments.</span></span>

- <span data-ttu-id="23cc6-272">**message_id：** 此值在本文前面部分的消息 [ID](#message-id) 部分中介绍。</span><span class="sxs-lookup"><span data-stu-id="23cc6-272">**message_id**: This value is described in the [Message ID](#message-id) section earlier in this article.</span></span> <span data-ttu-id="23cc6-273">例如，`<d9683b4c-127b-413a-ae2e-fa7dfb32c69d@DM3NAM06BG401.Eop-nam06.prod.protection.outlook.com>`。</span><span class="sxs-lookup"><span data-stu-id="23cc6-273">For example, `<d9683b4c-127b-413a-ae2e-fa7dfb32c69d@DM3NAM06BG401.Eop-nam06.prod.protection.outlook.com>`.</span></span>

- <span data-ttu-id="23cc6-274">**network_message_id：** 一个唯一的邮件 ID 值，它保留由于混淆或通讯组扩展而可能创建的所有邮件副本。</span><span class="sxs-lookup"><span data-stu-id="23cc6-274">**network_message_id**: A unique message ID value that persists across all copies of the message that might be created due to bifurcation or distribution group expansion.</span></span> <span data-ttu-id="23cc6-275">示例值为 `1341ac7b13fb42ab4d4408cf7f55890f` 。</span><span class="sxs-lookup"><span data-stu-id="23cc6-275">An example value is `1341ac7b13fb42ab4d4408cf7f55890f`.</span></span>

- <span data-ttu-id="23cc6-276">**original_client_ip：** 发件人客户端的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="23cc6-276">**original_client_ip**: The IP address of the sender's client.</span></span>

- <span data-ttu-id="23cc6-277">**方向性**：指示邮件是 (1) 1 到组织的入站邮件，还是从组织 (2) 出站邮件。</span><span class="sxs-lookup"><span data-stu-id="23cc6-277">**directionality**: Indicates whether the message was sent inbound (1) to your organization, or whether it was sent outbound (2) from your organization.</span></span>

- <span data-ttu-id="23cc6-278">**connector_id**：源连接器或目标连接器的名称。</span><span class="sxs-lookup"><span data-stu-id="23cc6-278">**connector_id**: The name of the source or destination connector.</span></span> <span data-ttu-id="23cc6-279">有关 Exchange Online 中的连接器详细信息，请参阅 [使用 Office 365](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)中的连接器配置邮件流。</span><span class="sxs-lookup"><span data-stu-id="23cc6-279">For more information about connectors in Exchange Online, see [Configure mail flow using connectors in Office 365](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow).</span></span>

- <span data-ttu-id="23cc6-280">**delivery_priority：** 邮件是使用高优先级、 <sup>\*</sup> **低** 优先级还是 **普通优先级发送**。</span><span class="sxs-lookup"><span data-stu-id="23cc6-280">**delivery_priority**<sup>\*</sup>: Whether the message was sent with **High**, **Low**, or **Normal** priority.</span></span>

<span data-ttu-id="23cc6-281"><sup>\*</sup> 这些属性仅在增强摘要报告中可用。</span><span class="sxs-lookup"><span data-stu-id="23cc6-281"><sup>\*</sup> These properties are only available in Enhanced summary reports.</span></span>

### <a name="extended-reports"></a><span data-ttu-id="23cc6-282">扩展报告</span><span class="sxs-lookup"><span data-stu-id="23cc6-282">Extended reports</span></span>

<span data-ttu-id="23cc6-283">可用 (邮件) 开头的"可下载报告"部分提供已完成的扩展报告。</span><span class="sxs-lookup"><span data-stu-id="23cc6-283">Available (completed) Extended reports are available in the **Downloadable reports** section at the beginning of message trace.</span></span> <span data-ttu-id="23cc6-284">"增强型摘要"报告中几乎所有信息都可用于扩展 (，origin_timestamp和 **delivery_priority) 。** </span><span class="sxs-lookup"><span data-stu-id="23cc6-284">Virtually all of the information from an Enhanced summary report is available in an Extended report (with the exception of **origin_timestamp** and **delivery_priority**).</span></span> <span data-ttu-id="23cc6-285">以下其他信息仅在扩展报告中可用：</span><span class="sxs-lookup"><span data-stu-id="23cc6-285">The following additional information is only available in an Extended report:</span></span>

- <span data-ttu-id="23cc6-286">**client_ip：** 提交邮件的电子邮件服务器或邮件客户端的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="23cc6-286">**client_ip**: The IP address of the email server or messaging client that submitted the message.</span></span>

- <span data-ttu-id="23cc6-287">**client_hostname**：提交邮件的电子邮件服务器或邮件客户端的主机名或 FQDN。</span><span class="sxs-lookup"><span data-stu-id="23cc6-287">**client_hostname**: The host name or FQDN of the email server or messaging client that submitted the message.</span></span>

- <span data-ttu-id="23cc6-288">**server_ip**：源服务器或目标服务器的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="23cc6-288">**server_ip**: The IP address of the source or destination server.</span></span>

- <span data-ttu-id="23cc6-289">**server_hostname**：目标服务器的主机名或 FQDN。</span><span class="sxs-lookup"><span data-stu-id="23cc6-289">**server_hostname**: The host name or FQDN of the destination server.</span></span>

- <span data-ttu-id="23cc6-290">**source_context：** 与源字段关联的 **额外** 信息。</span><span class="sxs-lookup"><span data-stu-id="23cc6-290">**source_context**: Extra information associated with the **source** field.</span></span> <span data-ttu-id="23cc6-291">例如：</span><span class="sxs-lookup"><span data-stu-id="23cc6-291">For example:</span></span>

  - `Protocol Filter Agent`

  - `3489061114359050000`

- <span data-ttu-id="23cc6-292">**source**： 负责事件的 Exchange Online 组件。</span><span class="sxs-lookup"><span data-stu-id="23cc6-292">**source**: The Exchange Online component that's responsible for the event.</span></span> <span data-ttu-id="23cc6-293">例如：</span><span class="sxs-lookup"><span data-stu-id="23cc6-293">For example:</span></span>

  - `AGENT`

  - `MAILBOXRULE`

  - `SMTP`

- <span data-ttu-id="23cc6-294">**event_id：** 这些对应于"查找此邮件的相关记录"部分中介绍的消息 [事件](#find-related-records-for-this-message)值。</span><span class="sxs-lookup"><span data-stu-id="23cc6-294">**event_id**: These correspond to the **Message event** values that are explained in the [Find related records for this message](#find-related-records-for-this-message) section.</span></span>

- <span data-ttu-id="23cc6-295">**internal_message_id：** 当前正在处理邮件的 Exchange Online 服务器分配的邮件标识符。</span><span class="sxs-lookup"><span data-stu-id="23cc6-295">**internal_message_id**: A message identifier that's assigned by the Exchange Online server that's currently processing the message.</span></span>

- <span data-ttu-id="23cc6-296">**recipient_address：** 邮件收件人的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="23cc6-296">**recipient_address**: The email addresses of the message's recipients.</span></span> <span data-ttu-id="23cc6-297">多个电子邮件地址通过分号字符 (;) 分隔。</span><span class="sxs-lookup"><span data-stu-id="23cc6-297">Multiple email addresses are separated by the semicolon character (;).</span></span>

- <span data-ttu-id="23cc6-298">**recipient_count**：邮件中的收件人总数。</span><span class="sxs-lookup"><span data-stu-id="23cc6-298">**recipient_count**: The total number of recipients in the message.</span></span>

- <span data-ttu-id="23cc6-299">**related_recipient_address**：与 和 事件一起用于显示与邮件关联的其他 `EXPAND` `REDIRECT` `RESOLVE` 收件人电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="23cc6-299">**related_recipient_address**: Used with `EXPAND`, `REDIRECT`, and `RESOLVE` events to display other recipient email addresses that are associated with the message.</span></span>

- <span data-ttu-id="23cc6-300">**reference：** This field contains additional information for specific types of events.</span><span class="sxs-lookup"><span data-stu-id="23cc6-300">**reference**: This field contains additional information for specific types of events.</span></span> <span data-ttu-id="23cc6-301">例如：</span><span class="sxs-lookup"><span data-stu-id="23cc6-301">For example:</span></span>

  - <span data-ttu-id="23cc6-302">**DSN：** 包含报告链接，如果 DSN 在此事件之后生成 (，则报告链接是关联的传递状态通知 (的 message_id 值，也称为 DSN、未送达报告、NDR 或退回邮件) 。 </span><span class="sxs-lookup"><span data-stu-id="23cc6-302">**DSN**: Contains the report link, which is the **message_id** value of the associated delivery status notification (also known as a DSN, non-delivery report, NDR, or bounce message) if a DSN is generated subsequent to this event.</span></span> <span data-ttu-id="23cc6-303">如果这是 DSN 邮件，则此字段message_id生成DSN 的原始邮件的默认值。</span><span class="sxs-lookup"><span data-stu-id="23cc6-303">If this is a DSN message, this field contains the **message_id** value of the original message that the DSN was generated for.</span></span>

  - <span data-ttu-id="23cc6-304">**EXPAND：** contains the **related_recipient_address** value of the related messages.</span><span class="sxs-lookup"><span data-stu-id="23cc6-304">**EXPAND**: Contains the **related_recipient_address** value of the related messages.</span></span>

  - <span data-ttu-id="23cc6-305">**RECEIVE**：如果message_id由其他进程生成，则可能包含相关邮件的 (值，例如收件箱规则) 。</span><span class="sxs-lookup"><span data-stu-id="23cc6-305">**RECEIVE**: Might contain the **message_id** value of the related message if the message was generated by other processes (for example, Inbox rules).</span></span>

  - <span data-ttu-id="23cc6-306">**SEND**： contains the **internal_message_id** value of any DSN messages.</span><span class="sxs-lookup"><span data-stu-id="23cc6-306">**SEND**: Contains the **internal_message_id** value of any DSN messages.</span></span>

  - <span data-ttu-id="23cc6-307">**TRANSFER**：包含internal_message_id分叉的邮件的 (值，例如，按内容转换、邮件收件人限制或代理) 。</span><span class="sxs-lookup"><span data-stu-id="23cc6-307">**TRANSFER**: Contains the **internal_message_id** value of the message that's being forked (for example, by content conversion, message recipient limits, or agents).</span></span>

  - <span data-ttu-id="23cc6-308">**MAILBOXRULE：\*\*\*\*包含internal_message_id** 收件箱规则生成出站邮件的入站邮件的邮箱值。</span><span class="sxs-lookup"><span data-stu-id="23cc6-308">**MAILBOXRULE**: Contains the **internal_message_id** value of the inbound message that caused the Inbox rule to generate the outbound message.</span></span>

    <span data-ttu-id="23cc6-309">对于其他类型的事件，此字段通常为空。</span><span class="sxs-lookup"><span data-stu-id="23cc6-309">For other types of events, this field is usually blank.</span></span>

- <span data-ttu-id="23cc6-310">**return_path**：发送邮件的 **MAIL FROM** 命令指定的返回电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="23cc6-310">**return_path**: The return email address specified by the **MAIL FROM** command that sent the message.</span></span> <span data-ttu-id="23cc6-311">尽管此字段从不为空，但它可以将空发件人地址值表示为 `<>` 。</span><span class="sxs-lookup"><span data-stu-id="23cc6-311">Although this field is never empty, it can have the null sender address value represented as `<>`.</span></span>

- <span data-ttu-id="23cc6-312">**message_info：** 有关邮件的其他信息。</span><span class="sxs-lookup"><span data-stu-id="23cc6-312">**message_info**: Additional information about the message.</span></span> <span data-ttu-id="23cc6-313">例如：</span><span class="sxs-lookup"><span data-stu-id="23cc6-313">For example:</span></span>

  - <span data-ttu-id="23cc6-314">和事件的邮件源日期-时间（以 UTC `DELIVER` `SEND` 表示）。</span><span class="sxs-lookup"><span data-stu-id="23cc6-314">The message origination date-time in UTC for `DELIVER` and `SEND` events.</span></span> <span data-ttu-id="23cc6-315">起始日期-时间是邮件首次进入 Exchange Online 组织的时间。</span><span class="sxs-lookup"><span data-stu-id="23cc6-315">The origination date-time is the time when the message first entered the Exchange Online organization.</span></span> <span data-ttu-id="23cc6-316">UTC 日期-时间以 ISO 8601 日期-时间格式表示：，其中 `yyyy-mm-ddThh:mm:ss.fffZ` `yyyy` = `mm` year、= month、= day，指示时间组件的开始 `dd` `T` `hh` ，= 小时 `mm` 、= 分钟 `ss` 、= 秒 `fff` 、= `Z` `Zulu` 秒的小数，并表示 ，这是表示 UTC 的另一种方式。</span><span class="sxs-lookup"><span data-stu-id="23cc6-316">The UTC date-time is represented in the ISO 8601 date-time format: `yyyy-mm-ddThh:mm:ss.fffZ`, where `yyyy` = year, `mm` = month, `dd` = day, `T` indicates the beginning of the time component, `hh` = hour, `mm` = minute, `ss` = second, `fff` = fractions of a second, and `Z` signifies `Zulu`, which is another way to denote UTC.</span></span>

  - <span data-ttu-id="23cc6-317">身份验证错误。</span><span class="sxs-lookup"><span data-stu-id="23cc6-317">Authentication errors.</span></span> <span data-ttu-id="23cc6-318">例如，您可能会看到身份验证出错时所使用的值和 `11a` 身份验证类型。</span><span class="sxs-lookup"><span data-stu-id="23cc6-318">For example, you might see the value `11a` and the type of authentication that was used when the authentication error occurred.</span></span>

- <span data-ttu-id="23cc6-319">**tenant_id**：一个 GUID 值，表示 Exchange Online (例如 `39238e87-b5ab-4ef6-a559-af54c6b07b42` ，) 。</span><span class="sxs-lookup"><span data-stu-id="23cc6-319">**tenant_id**: A GUID value that represents the Exchange Online organization (for example, `39238e87-b5ab-4ef6-a559-af54c6b07b42`).</span></span>

- <span data-ttu-id="23cc6-320">**original_server_ip**：原始服务器的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="23cc6-320">**original_server_ip**: The IP address of the original server.</span></span>

- <span data-ttu-id="23cc6-321">**custom_data：** 包含与特定事件类型相关的数据。</span><span class="sxs-lookup"><span data-stu-id="23cc6-321">**custom_data**: Contains data related to specific event types.</span></span> <span data-ttu-id="23cc6-322">有关详细信息，请参阅以下部分。</span><span class="sxs-lookup"><span data-stu-id="23cc6-322">For more information, see the following sections.</span></span>

#### <a name="custom_data-values"></a><span data-ttu-id="23cc6-323">custom_data值</span><span class="sxs-lookup"><span data-stu-id="23cc6-323">custom_data values</span></span>

<span data-ttu-id="23cc6-324">事件的 **custom_data** 字段由各种 Exchange Online 代理用来 `AGENTINFO` 记录邮件处理详细信息。</span><span class="sxs-lookup"><span data-stu-id="23cc6-324">The **custom_data** field for an `AGENTINFO` event is used by a variety of Exchange Online agents to log message processing details.</span></span> <span data-ttu-id="23cc6-325">以下各节介绍了一些更有趣的代理。</span><span class="sxs-lookup"><span data-stu-id="23cc6-325">Some of the more interesting agents are described in the following sections.</span></span>

#### <a name="spam-filter-agent"></a><span data-ttu-id="23cc6-326">垃圾邮件筛选器代理</span><span class="sxs-lookup"><span data-stu-id="23cc6-326">Spam filter agent</span></span>

<span data-ttu-id="23cc6-327">一 **custom_data** 一个值来自 `S:SFA` 垃圾邮件筛选器代理。</span><span class="sxs-lookup"><span data-stu-id="23cc6-327">A **custom_data** value that starts with `S:SFA` is from the spam filter agent.</span></span> <span data-ttu-id="23cc6-328">下表介绍了关键详细信息：</span><span class="sxs-lookup"><span data-stu-id="23cc6-328">The key details are described in the following table:</span></span>

****

|<span data-ttu-id="23cc6-329">值</span><span class="sxs-lookup"><span data-stu-id="23cc6-329">Value</span></span>|<span data-ttu-id="23cc6-330">说明</span><span class="sxs-lookup"><span data-stu-id="23cc6-330">Description</span></span>|
|---|---|
|`SFV=NSPM`|<span data-ttu-id="23cc6-331">邮件被标记为非垃圾邮件并发送给预期收件人。</span><span class="sxs-lookup"><span data-stu-id="23cc6-331">The message was marked as non-spam and was sent to the intended recipients.</span></span>|
|`SFV=SPM`|<span data-ttu-id="23cc6-332">反垃圾邮件筛选将邮件标记为垃圾邮件 (也称为内容筛选) 。</span><span class="sxs-lookup"><span data-stu-id="23cc6-332">The message was marked as spam by anti-spam filtering (also known as content filtering).</span></span>|
|`SFV=BLK`|<span data-ttu-id="23cc6-333">跳过筛选但阻止邮件，因为它是由已阻止发件人发送。</span><span class="sxs-lookup"><span data-stu-id="23cc6-333">Filtering was skipped and the message was blocked because it originated from a blocked sender.</span></span>|
|`SFV=SKS`|<span data-ttu-id="23cc6-334">在反垃圾邮件筛选处理邮件之前，邮件被标记为垃圾邮件。</span><span class="sxs-lookup"><span data-stu-id="23cc6-334">The message was marked as spam prior to being processed by anti-spam filtering.</span></span> <span data-ttu-id="23cc6-335">这包括符合以下邮件流程规则条件（也称为传输规则）的邮件：自动将邮件标记为垃圾邮件并规避其他所有筛选。</span><span class="sxs-lookup"><span data-stu-id="23cc6-335">This includes messages where the message matched a mail flow rule (also known as a transport rule) to automatically mark it as spam and bypass all additional filtering.</span></span>|
|`SCL=<number>`|<span data-ttu-id="23cc6-336">有关不同的 SCL 值及其含义的详细信息，请参阅[垃圾邮件可信度](spam-confidence-levels.md)。</span><span class="sxs-lookup"><span data-stu-id="23cc6-336">For more information about the different SCL values and what they mean, see [Spam confidence levels](spam-confidence-levels.md).</span></span>|
|`PCL=<number>`|<span data-ttu-id="23cc6-p155">邮件的仿冒可能性等级 (PCL) 值。可按照[垃圾邮件可信度](spam-confidence-levels.md)中介绍 SCL 值的方式对这些值做出解释。  </span><span class="sxs-lookup"><span data-stu-id="23cc6-p155">The Phishing Confidence Level (PCL) value of the message. These can be interpreted the same way as the SCL values documented in [Spam confidence levels](spam-confidence-levels.md).</span></span>|
|`DI=SB`|<span data-ttu-id="23cc6-339">已阻止邮件发件人。</span><span class="sxs-lookup"><span data-stu-id="23cc6-339">The sender of the message was blocked.</span></span>|
|`DI=SQ`|<span data-ttu-id="23cc6-340">邮件已隔离。</span><span class="sxs-lookup"><span data-stu-id="23cc6-340">The message was quarantined.</span></span>|
|`DI=SD`|<span data-ttu-id="23cc6-341">邮件已删除。</span><span class="sxs-lookup"><span data-stu-id="23cc6-341">The message was deleted.</span></span>|
|`DI=SJ`|<span data-ttu-id="23cc6-342">邮件已发送至收件人的"垃圾邮件"文件夹。</span><span class="sxs-lookup"><span data-stu-id="23cc6-342">The message was sent to the recipient's Junk Email folder.</span></span>|
|`DI=SN`|<span data-ttu-id="23cc6-343">邮件已通过正常出站传送池路由。</span><span class="sxs-lookup"><span data-stu-id="23cc6-343">The message was routed through the normal outbound delivery pool.</span></span>|
|`DI=SO`|<span data-ttu-id="23cc6-344">邮件已通过高风险传送池路由。</span><span class="sxs-lookup"><span data-stu-id="23cc6-344">The message was routed through the higher risk delivery pool.</span></span> <span data-ttu-id="23cc6-345">有关详细信息，请参阅[出站邮件的高风险传递池](high-risk-delivery-pool-for-outbound-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="23cc6-345">For more information, see [High-risk delivery pool for outbound messages](high-risk-delivery-pool-for-outbound-messages.md).</span></span>|
|`SFS=[a]|SFS=[b]`|<span data-ttu-id="23cc6-346">说明匹配此垃圾邮件规则。</span><span class="sxs-lookup"><span data-stu-id="23cc6-346">This denotes that spam rules were matched.</span></span>|
|`IPV=CAL`|<span data-ttu-id="23cc6-347">邮件已获得垃圾邮件筛选器的允许，因为 IP 地址已在连接筛选器的 IP 允许列表中指定。</span><span class="sxs-lookup"><span data-stu-id="23cc6-347">The message was allowed through the spam filters because the IP address was specified in an IP Allow list in the connection filter.</span></span>|
|`H=<EHLOstring>`|<span data-ttu-id="23cc6-348">连接电子邮件服务器的 HELO 或 EHLO 字符串。</span><span class="sxs-lookup"><span data-stu-id="23cc6-348">The HELO or EHLO string of the connecting email server.</span></span>|
|`PTR=<ReverseDNS>`|<span data-ttu-id="23cc6-349">发送 IP 地址的 PTR 记录，也被称为反向 DNS 地址。</span><span class="sxs-lookup"><span data-stu-id="23cc6-349">The PTR record of the sending IP address, also known as the reverse DNS address.</span></span>|
|

<span data-ttu-id="23cc6-350">一 **custom_data** 筛选为垃圾邮件的邮件的值示例，如下所示：</span><span class="sxs-lookup"><span data-stu-id="23cc6-350">An example **custom_data** value for a message that's filtered for spam like this:</span></span>

`S:SFA=SUM|SFV=SPM|IPV=CAL|SRV=BULK|SFS=470454002|SFS=349001|SCL=9|SCORE=-1|LIST=0|DI=SN|RD=ftmail.inc.com|H=ftmail.inc.com|CIP=98.129.140.74|SFP=1501|ASF=1|CTRY=US|CLTCTRY=|LANG=en|LAT=287|LAT=260|LAT=18;`

#### <a name="malware-filter-agent"></a><span data-ttu-id="23cc6-351">恶意软件筛选器代理</span><span class="sxs-lookup"><span data-stu-id="23cc6-351">Malware filter agent</span></span>

<span data-ttu-id="23cc6-352">开头 **custom_data** 一个值 `S:AMA` 来自恶意软件筛选器代理。</span><span class="sxs-lookup"><span data-stu-id="23cc6-352">A **custom_data** value that starts with `S:AMA` is from the malware filter agent.</span></span> <span data-ttu-id="23cc6-353">下表介绍了关键详细信息：</span><span class="sxs-lookup"><span data-stu-id="23cc6-353">The key details are described in the following table:</span></span>

****

|<span data-ttu-id="23cc6-354">值</span><span class="sxs-lookup"><span data-stu-id="23cc6-354">Value</span></span>|<span data-ttu-id="23cc6-355">说明</span><span class="sxs-lookup"><span data-stu-id="23cc6-355">Description</span></span>|
|---|---|
|<span data-ttu-id="23cc6-356">`AMA=SUM|v=1|` 或 `AMA=EV|v=1`</span><span class="sxs-lookup"><span data-stu-id="23cc6-356">`AMA=SUM|v=1|` or `AMA=EV|v=1`</span></span>|<span data-ttu-id="23cc6-357">已确定此邮件包含恶意软件。</span><span class="sxs-lookup"><span data-stu-id="23cc6-357">The message was determined to contain malware.</span></span> <span data-ttu-id="23cc6-358">`SUM` 指示恶意软件可能已被任意数目的引擎检测到。</span><span class="sxs-lookup"><span data-stu-id="23cc6-358">`SUM` indicates the malware could've been detected by any number of engines.</span></span> <span data-ttu-id="23cc6-359">`EV` 指示恶意软件已由特定引擎检测到。</span><span class="sxs-lookup"><span data-stu-id="23cc6-359">`EV` indicates the malware was detected by a specific engine.</span></span> <span data-ttu-id="23cc6-360">引擎检测到恶意软件后，将触发后续操作。</span><span class="sxs-lookup"><span data-stu-id="23cc6-360">When malware is detected by an engine this triggers the subsequent actions.</span></span>|
|`Action=r`|<span data-ttu-id="23cc6-361">邮件已被替换。</span><span class="sxs-lookup"><span data-stu-id="23cc6-361">The message was replaced.</span></span>|
|`Action=p`|<span data-ttu-id="23cc6-362">邮件已被忽略。</span><span class="sxs-lookup"><span data-stu-id="23cc6-362">The message was bypassed.</span></span>|
|`Action=d`|<span data-ttu-id="23cc6-363">邮件已被延迟。</span><span class="sxs-lookup"><span data-stu-id="23cc6-363">The message was deferred.</span></span>|
|`Action=s`|<span data-ttu-id="23cc6-364">邮件已删除。</span><span class="sxs-lookup"><span data-stu-id="23cc6-364">The message was deleted.</span></span>|
|`Action=st`|<span data-ttu-id="23cc6-365">邮件已被忽略。</span><span class="sxs-lookup"><span data-stu-id="23cc6-365">The message was bypassed.</span></span>|
|`Action=sy`|<span data-ttu-id="23cc6-366">邮件已被忽略。</span><span class="sxs-lookup"><span data-stu-id="23cc6-366">The message was bypassed.</span></span>|
|`Action=ni`|<span data-ttu-id="23cc6-367">邮件已被拒绝。</span><span class="sxs-lookup"><span data-stu-id="23cc6-367">The message was rejected.</span></span>|
|`Action=ne`|<span data-ttu-id="23cc6-368">邮件已被拒绝。</span><span class="sxs-lookup"><span data-stu-id="23cc6-368">The message was rejected.</span></span>|
|`Action=b`|<span data-ttu-id="23cc6-369">邮件已被阻止。</span><span class="sxs-lookup"><span data-stu-id="23cc6-369">The message was blocked.</span></span>|
|`Name=<malware>`|<span data-ttu-id="23cc6-370">已检测到的恶意软件的名称。</span><span class="sxs-lookup"><span data-stu-id="23cc6-370">The name of the malware that was detected.</span></span>|
|`File=<filename>`|<span data-ttu-id="23cc6-371">恶意软件中包含的文件名称。</span><span class="sxs-lookup"><span data-stu-id="23cc6-371">The name of the file that contained the malware.</span></span>|
|

<span data-ttu-id="23cc6-372">包含 **custom_data** 的邮件的值示例如下所示：</span><span class="sxs-lookup"><span data-stu-id="23cc6-372">An example **custom_data** value for a message that contains malware looks like this:</span></span>

`S:AMA=SUM|v=1|action=b|error=|atch=1;S:AMA=EV|engine=M|v=1|sig=1.155.974.0|name=DOS/Test_File|file=filename;S:AMA=EV|engine=A|v=1|sig=201707282038|name=Test_File|file=filename`

#### <a name="transport-rule-agent"></a><span data-ttu-id="23cc6-373">传输规则代理</span><span class="sxs-lookup"><span data-stu-id="23cc6-373">Transport Rule agent</span></span>

<span data-ttu-id="23cc6-374">一 **custom_data** 一个值来自邮件流规则的传输规则代理 (也称为 `S:TRA` 传输规则) 。</span><span class="sxs-lookup"><span data-stu-id="23cc6-374">A **custom_data** value that starts with`S:TRA` is from the Transport Rule agent for mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="23cc6-375">下表介绍了关键详细信息：</span><span class="sxs-lookup"><span data-stu-id="23cc6-375">The key details are described in the following table:</span></span>

****

|<span data-ttu-id="23cc6-376">值</span><span class="sxs-lookup"><span data-stu-id="23cc6-376">Value</span></span>|<span data-ttu-id="23cc6-377">说明</span><span class="sxs-lookup"><span data-stu-id="23cc6-377">Description</span></span>|
|---|---|
|`ETR|ruleId=<guid>`|<span data-ttu-id="23cc6-378">匹配的规则 ID。</span><span class="sxs-lookup"><span data-stu-id="23cc6-378">The rule ID that was matched.</span></span>|
|`St=<datetime>`|<span data-ttu-id="23cc6-379">规则匹配发生时的日期和时间（以 UTC 表示）。</span><span class="sxs-lookup"><span data-stu-id="23cc6-379">The date and time in UTC when the rule match occurred.</span></span>|
|`Action=<ActionDefinition>`|<span data-ttu-id="23cc6-380">应用的操作。</span><span class="sxs-lookup"><span data-stu-id="23cc6-380">The action that was applied.</span></span> <span data-ttu-id="23cc6-381">有关可用操作的列表，请参阅 Exchange Online 中的邮件 [流规则操作](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)。</span><span class="sxs-lookup"><span data-stu-id="23cc6-381">For a list of available actions, see [Mail flow rule actions in Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).</span></span>|
|`Mode=<Mode>`|<span data-ttu-id="23cc6-382">规则模式。</span><span class="sxs-lookup"><span data-stu-id="23cc6-382">The mode of the rule.</span></span> <span data-ttu-id="23cc6-383">有效值为：</span><span class="sxs-lookup"><span data-stu-id="23cc6-383">Valid values are:</span></span><ul><li><span data-ttu-id="23cc6-384">**强制**：将强制执行对规则的所有操作。</span><span class="sxs-lookup"><span data-stu-id="23cc6-384">**Enforce**: All actions on the rule will be enforced.</span></span></li><li><span data-ttu-id="23cc6-385">**使用策略提示进行测试：** 将发送任何策略提示操作，但不执行其他强制操作。</span><span class="sxs-lookup"><span data-stu-id="23cc6-385">**Test with Policy Tips:**: Any Policy Tip actions will be sent, but other enforcement actions will not be acted on.</span></span></li><li><span data-ttu-id="23cc6-386">**不带策略提示的测试**：操作将列在日志文件中，但不会以任何方式通知发件人，并且不会执行强制操作。</span><span class="sxs-lookup"><span data-stu-id="23cc6-386">**Test without Policy Tips**: Actions will be listed in a log file, but senders will not be notified in any way, and enforcement actions will not be acted on.</span></span></li></ul>|
|

<span data-ttu-id="23cc6-387">与 **custom_data** 规则条件匹配的邮件的示例值如下所示：</span><span class="sxs-lookup"><span data-stu-id="23cc6-387">An example **custom_data** value for a messages that matches the conditions of a mail flow rule looks like this:</span></span>

`S:TRA=ETR|ruleId=19a25eb2-3e43-4896-ad9e-47b6c359779d|st=7/17/2017 12:31:25 AM|action=ApplyHtmlDisclaimer|sev=1|mode=Enforce`
