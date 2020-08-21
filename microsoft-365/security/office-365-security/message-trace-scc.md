---
title: 安全与合规中心内的消息跟踪
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 3e64f99d-ac33-4aba-91c5-9cb4ca476803
ms.custom:
- seo-marvel-apr2020
description: 管理员可以使用安全与合规中心中的&跟踪来了解消息发生了什么。
ms.openlocfilehash: c6e1f8f9280c84ab6ff6a1572d902ed1d4d4caa3
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827047"
---
# <a name="message-trace-in-the-security--compliance-center"></a><span data-ttu-id="e96fd-103">安全与合规中心内的消息跟踪</span><span class="sxs-lookup"><span data-stu-id="e96fd-103">Message trace in the Security & Compliance Center</span></span>

## <a name="message-trace-features"></a><span data-ttu-id="e96fd-104">邮件跟踪功能</span><span class="sxs-lookup"><span data-stu-id="e96fd-104">Message trace features</span></span>

<span data-ttu-id="e96fd-105">安全邮件在&邮件通过 Exchange Online 组织时，遵循电子邮件。</span><span class="sxs-lookup"><span data-stu-id="e96fd-105">Message trace in the Security & Compliance Center follows email messages as they travel through your Exchange Online organization.</span></span> <span data-ttu-id="e96fd-106">您可以确定邮件是否被接收、拒绝、延迟或由服务传递。</span><span class="sxs-lookup"><span data-stu-id="e96fd-106">You can determine if a message was received, rejected, deferred, or delivered by the service.</span></span> <span data-ttu-id="e96fd-107">它还显示邮件在到达最终状态之前对邮件所执行的操作。</span><span class="sxs-lookup"><span data-stu-id="e96fd-107">It also shows what actions were taken on the message before it reached its final status.</span></span>

<span data-ttu-id="e96fd-108">安全与合规中心中的&跟踪改进了 Exchange 管理中心网站原始 (的) 。</span><span class="sxs-lookup"><span data-stu-id="e96fd-108">Message trace in the Security & Compliance Center improves upon the original message trace that was available in the Exchange admin center (EAC).</span></span> <span data-ttu-id="e96fd-109">您可以使用邮件跟踪中的信息有效回答有关邮件所发生事情的用户问题、解决邮件流问题并验证策略更改。</span><span class="sxs-lookup"><span data-stu-id="e96fd-109">You can use the information from message trace to efficiently answer user questions about what happened to messages, troubleshoot mail flow issues, and validate policy changes.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="e96fd-110">若要执行邮件跟踪，您需要是组织管理角色组、合规性管理或技术支持角色组的成员。</span><span class="sxs-lookup"><span data-stu-id="e96fd-110">To do a message trace, you need to be a member of the Organization Management, Compliance Management or Help Desk role groups.</span></span> <span data-ttu-id="e96fd-111">有关详细信息，请参阅[安全与合规中心中的权限](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="e96fd-111">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
>
> - <span data-ttu-id="e96fd-112">结果中显示的邮件的最大数量取决于您选择的报告类型 (请参阅" [选择报告类型"](#choose-report-type) 部分，了解详细信息页面) 。</span><span class="sxs-lookup"><span data-stu-id="e96fd-112">The maximum number of messages that are displayed in the results depends on the report type you selected (see the [Choose report type](#choose-report-type) section for details).</span></span> <span data-ttu-id="e96fd-113">Exchange Online PowerShell [中的 Get-HistoricalSearch](https://docs.microsoft.com/powershell/module/exchange/get-historicalsearch) cmdlet 或独立 EOP PowerShell 将返回结果中的所有邮件。</span><span class="sxs-lookup"><span data-stu-id="e96fd-113">The [Get-HistoricalSearch](https://docs.microsoft.com/powershell/module/exchange/get-historicalsearch) cmdlet in Exchange Online PowerShell or standalone EOP PowerShell returns all messages in the results.</span></span>

## <a name="open-message-trace"></a><span data-ttu-id="e96fd-114">打开邮件跟踪</span><span class="sxs-lookup"><span data-stu-id="e96fd-114">Open message trace</span></span>

1. <span data-ttu-id="e96fd-115">打开"&安全与合规中心 <https://protection.office.com> "。</span><span class="sxs-lookup"><span data-stu-id="e96fd-115">Open the Security & Compliance Center at <https://protection.office.com>.</span></span>

2. <span data-ttu-id="e96fd-116">展开 **"邮件流**"，然后选择"邮件**跟踪"。**</span><span class="sxs-lookup"><span data-stu-id="e96fd-116">Expand **Mail flow**, and then select **Message trace**.</span></span>

## <a name="message-trace-page"></a><span data-ttu-id="e96fd-117">邮件跟踪页面</span><span class="sxs-lookup"><span data-stu-id="e96fd-117">Message trace page</span></span>

<span data-ttu-id="e96fd-118">从此处，你可以通过单击"开始跟踪"按钮 **启动新的默认** 跟踪。</span><span class="sxs-lookup"><span data-stu-id="e96fd-118">From here you can start a new default trace by clicking on the **Start a trace** button.</span></span> <span data-ttu-id="e96fd-119">这将搜索过去两天的所有发件人和收件人的所有邮件。</span><span class="sxs-lookup"><span data-stu-id="e96fd-119">This will search for all messages for all senders and recipients for the last two days.</span></span> <span data-ttu-id="e96fd-120">或者，您可以使用可用查询类别之一来运行这些查询，或者按自己的查询作为起点：</span><span class="sxs-lookup"><span data-stu-id="e96fd-120">Or you can use one of the stored queries from the available query categories and either run them as-is or use them as starting points for your own queries:</span></span>

- <span data-ttu-id="e96fd-121">**默认查询**：Microsoft 365 提供的内置查询。</span><span class="sxs-lookup"><span data-stu-id="e96fd-121">**Default queries**: Built-in queries provided by Microsoft 365.</span></span>

- <span data-ttu-id="e96fd-122">**自定义查询：** 组织中的管理员保存的查询以供将来使用。</span><span class="sxs-lookup"><span data-stu-id="e96fd-122">**Custom queries**: Queries saved by admins in your organization for future use.</span></span>

- <span data-ttu-id="e96fd-123">**自动保存的查询**：最近十个最近运行的查询。</span><span class="sxs-lookup"><span data-stu-id="e96fd-123">**Autosaved queries**: The last ten most recently run queries.</span></span> <span data-ttu-id="e96fd-124">此列表可以让你从中断位置轻松地开始。</span><span class="sxs-lookup"><span data-stu-id="e96fd-124">This list makes it simple to pick up where you left off.</span></span>

<span data-ttu-id="e96fd-125">在此页面上，还 **是你已** 提交请求的可下载报告部分，以及报告本身（如果有可供下载）。</span><span class="sxs-lookup"><span data-stu-id="e96fd-125">Also on this page is a **Downloadable reports** section for the requests you've submitted, as well as the reports themselves when they're are available for download.</span></span>

## <a name="options-for-a-new-message-trace"></a><span data-ttu-id="e96fd-126">新邮件跟踪选项</span><span class="sxs-lookup"><span data-stu-id="e96fd-126">Options for a new message trace</span></span>

### <a name="filter-by-senders-and-recipients"></a><span data-ttu-id="e96fd-127">按发件人和收件人进行筛选</span><span class="sxs-lookup"><span data-stu-id="e96fd-127">Filter by senders and recipients</span></span>

<span data-ttu-id="e96fd-128">默认值是**所有发件人和\*\*\*\*所有收件人**，但可以使用下列字段筛选结果：</span><span class="sxs-lookup"><span data-stu-id="e96fd-128">The default values are **All senders** and **All recipients**, but you can use the following fields to filter the results:</span></span>

- <span data-ttu-id="e96fd-129">**由这些人员**：单击此字段可从组织中选择一个或多个发件人。</span><span class="sxs-lookup"><span data-stu-id="e96fd-129">**By these people**: Click in this field to select one or more senders from your organization.</span></span> <span data-ttu-id="e96fd-130">还可以开始键入名称，然后按您键入的内容筛选列表中的项，这与搜索页的表现在外观很相当。</span><span class="sxs-lookup"><span data-stu-id="e96fd-130">You can also start to type a name and the items in the list will be filtered by what you've typed, much like how a search page behaves.</span></span>

- <span data-ttu-id="e96fd-131">**对这些用户**：单击此字段可选择组织中的一个或多个收件人。</span><span class="sxs-lookup"><span data-stu-id="e96fd-131">**To these people**: Click in this field to select one or more recipients in your organization.</span></span>

> [!NOTE]
> <span data-ttu-id="e96fd-132">您还可以键入外部发件人和收件人的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="e96fd-132">You can also type the email addresses of external senders and recipients.</span></span> <span data-ttu-id="e96fd-133">例如，支持通配 (通 `*@contoso.com`) ，但您不能同时在同一字段中使用多个通配符条目。</span><span class="sxs-lookup"><span data-stu-id="e96fd-133">Wildcards are supported (for example, `*@contoso.com`), but you can't use multiple wildcard entries in the same field at the same time.</span></span> <br/><br/> <span data-ttu-id="e96fd-134">您可粘贴多个发件人或收件人列表，中以分号 `;` () 。</span><span class="sxs-lookup"><span data-stu-id="e96fd-134">You can paste multiple senders or recipients lists separated by semicolons (`;`).</span></span> <span data-ttu-id="e96fd-135">空格 `\s` () 、回车符或下 `\r` () 或下 `\n` () 。</span><span class="sxs-lookup"><span data-stu-id="e96fd-135">spaces (`\s`), carriage returns (`\r`), or next lines (`\n`).</span></span>

### <a name="time-range"></a><span data-ttu-id="e96fd-136">时间范围</span><span class="sxs-lookup"><span data-stu-id="e96fd-136">Time range</span></span>

<span data-ttu-id="e96fd-137">默认值为 2 天 **，** 但可以指定长达 90 天的日期/时间范围。</span><span class="sxs-lookup"><span data-stu-id="e96fd-137">The default value is **2 days**, but you can specify date/time ranges of up to 90 days.</span></span> <span data-ttu-id="e96fd-138">在使用日期/时间范围时，请考虑以下问题：</span><span class="sxs-lookup"><span data-stu-id="e96fd-138">When you use date/time ranges, consider these issues:</span></span>

- <span data-ttu-id="e96fd-139">默认情况下，使用时间线在 **滑块视图中** 选择时间范围。</span><span class="sxs-lookup"><span data-stu-id="e96fd-139">By default, you select the time range in **Slider** view using a time line.</span></span> <span data-ttu-id="e96fd-140">只能选择显示的日期或时间设置。</span><span class="sxs-lookup"><span data-stu-id="e96fd-140">You can only select the day or time settings that are displayed.</span></span> <span data-ttu-id="e96fd-141">尝试选择两个值之间的间隙，会将开始/结束气泡与最匹配的显示设置相加。</span><span class="sxs-lookup"><span data-stu-id="e96fd-141">Trying to select an in-between value will snap the start/end bubble to the nearest displayed setting.</span></span>

  ![安全与合规中心新邮件跟踪中的滑&时间范围](../../media/55a9e9c1-f7d5-4047-b217-824e8b976bcb.png)

  <span data-ttu-id="e96fd-143">但是，您还可以切换到自定义**视图，** 在该视图中你可以指定**开始日期\*\*\*\*和结束**日期值 (包括时间) ），还可以选择日期/时间范围**Time zone**的时区。</span><span class="sxs-lookup"><span data-stu-id="e96fd-143">But, you can also switch to **Custom** view where you can specify the **Start date** and **End date** values (including times), and you can also select the **Time zone** for the date/time range.</span></span> <span data-ttu-id="e96fd-144">请注意， **时区** 设置同时适用于查询输入和查询结果。</span><span class="sxs-lookup"><span data-stu-id="e96fd-144">Note that the **Time zone** setting applies to both your query inputs and your query results.</span></span>

  ![安全与合规中心新邮件跟踪中的&时间范围](../../media/ed4c8d50-9ea5-4694-93f9-ee3ab6660b4f.png)

  <span data-ttu-id="e96fd-146">10 天或更短时，可将结果作为"摘要报告" **即时** 提供。</span><span class="sxs-lookup"><span data-stu-id="e96fd-146">For 10 days or less, the results are available instantly as a **Summary** report.</span></span> <span data-ttu-id="e96fd-147">如果你指定的时间范围甚至少于 10 天，结果将延迟，因为它们只能作为可下载的 CSV 文件提供， (**增强**摘要或扩展报告) 。 **Extended**</span><span class="sxs-lookup"><span data-stu-id="e96fd-147">If you specify a time range that's even slightly greater than 10 days, the results will be delayed as they are only available as a downloadable CSV file ( **Enhanced summary** or **Extended** reports).</span></span>

  <span data-ttu-id="e96fd-148">有关其他报告类型的详细信息，请参阅本主题 [中的"选择报告](#choose-report-type) 类型"部分。</span><span class="sxs-lookup"><span data-stu-id="e96fd-148">For more information about the different report types, see the [Choose report type](#choose-report-type) section in this topic.</span></span>

  <span data-ttu-id="e96fd-149">**注意**：已使用存档的邮件跟踪数据准备了增强的摘要报告和扩展报告，在下载报告之前可能需要几个小时。</span><span class="sxs-lookup"><span data-stu-id="e96fd-149">**Note**: Enhanced summary and Extended reports are prepared using archived message trace data, and it can take up to several hours before your report is available for download.</span></span> <span data-ttu-id="e96fd-150">根据其他管理员也同时提交了报告请求的数量，您可能还会注意到一些延迟，然后再处理您的排队的请求。</span><span class="sxs-lookup"><span data-stu-id="e96fd-150">Depending on how many other admins have also submitted report requests around the same time, you might also notice a delay before processing starts for your queued request.</span></span>

- <span data-ttu-id="e96fd-151">在滑块视图中 **保存查询可** 保存相对时间范围 (例如，从今天开始的 3 天时) 。</span><span class="sxs-lookup"><span data-stu-id="e96fd-151">Saving a query in **Slider** view saves the relative time range (for example, 3 days from today).</span></span> <span data-ttu-id="e96fd-152">在自定义视图中保存 **查询可** 节省绝对日期/时间范围 (例如，2018-05-06 13：00 至 2018-05-08 18：00) 。</span><span class="sxs-lookup"><span data-stu-id="e96fd-152">Saving a query in **Custom** view saves the absolute date/time range (for example, 2018-05-06 13:00 to 2018-05-08 18:00).</span></span>

### <a name="more-search-options"></a><span data-ttu-id="e96fd-153">更多搜索选项</span><span class="sxs-lookup"><span data-stu-id="e96fd-153">More search options</span></span>

#### <a name="delivery-status"></a><span data-ttu-id="e96fd-154">传递状态</span><span class="sxs-lookup"><span data-stu-id="e96fd-154">Delivery status</span></span>

<span data-ttu-id="e96fd-155">您可以将默认值 **保持选中状态** ，或者你可以选择以下值之一来筛选结果：</span><span class="sxs-lookup"><span data-stu-id="e96fd-155">You can leave the default value **All** selected, or you can select one of the following values to filter the results:</span></span>

- <span data-ttu-id="e96fd-156">**已发送**：该邮件已成功送达到目标。</span><span class="sxs-lookup"><span data-stu-id="e96fd-156">**Delivered**: The message was successfully delivered to the intended destination.</span></span>

- <span data-ttu-id="e96fd-157">**挂起**：正尝试或重新尝试传递邮件。</span><span class="sxs-lookup"><span data-stu-id="e96fd-157">**Pending**: Delivery of the message is being attempted or re-attempted.</span></span>

- <span data-ttu-id="e96fd-158">**展开**：在传递至组中的单个成员之前展开通讯组收件人。</span><span class="sxs-lookup"><span data-stu-id="e96fd-158">**Expanded**: A distribution group recipient was expanded before delivery to the individual members of the group.</span></span>

- <span data-ttu-id="e96fd-159">**失败**：未传递邮件。</span><span class="sxs-lookup"><span data-stu-id="e96fd-159">**Failed**: The message was not delivered.</span></span>

- <span data-ttu-id="e96fd-160">**已隔离：邮件**被 (如垃圾邮件、批量邮件或网络钓鱼邮件) 。</span><span class="sxs-lookup"><span data-stu-id="e96fd-160">**Quarantined**: The message was quarantined (as spam, bulk mail, or phishing).</span></span> <span data-ttu-id="e96fd-161">有关详细信息，请参阅 [EOP 中隔离的电子邮件](quarantine-email-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="e96fd-161">For more information, see [Quarantined email messages in EOP](quarantine-email-messages.md).</span></span>

- <span data-ttu-id="e96fd-162">**已被筛选为**垃圾邮件：已将邮件标识为垃圾邮件，被拒绝 (隔离) 。</span><span class="sxs-lookup"><span data-stu-id="e96fd-162">**Filtered as spam**: The message was identified spam, and was rejected or blocked (not quarantined).</span></span>

- <span data-ttu-id="e96fd-163">**获取状态：** 最近是由 Microsoft 365 收到的，但尚未使用其他任何状态数据。</span><span class="sxs-lookup"><span data-stu-id="e96fd-163">**Getting status:** The message was recently received by Microsoft 365, but no other status data is yet available.</span></span> <span data-ttu-id="e96fd-164">在几分钟内重新查看。</span><span class="sxs-lookup"><span data-stu-id="e96fd-164">Check back in a few minutes.</span></span>

<span data-ttu-id="e96fd-165">**注意**："**挂起"、"\*\*\*\*隔离"** 和"**筛选为垃圾邮件"** 的值仅可用于少于 10 天的搜索。</span><span class="sxs-lookup"><span data-stu-id="e96fd-165">**Note**: The values **Pending,** **Quarantined**, and **Filter as spam** are only available for searches less than 10 days.</span></span> <span data-ttu-id="e96fd-166">此外，实际传递状态与报告的传递状态之间可能存在 5 到 10 分钟的延迟。</span><span class="sxs-lookup"><span data-stu-id="e96fd-166">Also, there might be a 5 to 10 minute delay between the actual and reported delivery status.</span></span>

#### <a name="message-id"></a><span data-ttu-id="e96fd-167">邮件 ID</span><span class="sxs-lookup"><span data-stu-id="e96fd-167">Message ID</span></span>

<span data-ttu-id="e96fd-168">这是 Internet 邮件 ID (在邮件头的 **Message-ID：** 头字段) 中找到，亦称为"客户端 ID"列表。</span><span class="sxs-lookup"><span data-stu-id="e96fd-168">This is the internet message ID (also known as the Client ID) that's found in the **Message-ID:** header field in the message header.</span></span> <span data-ttu-id="e96fd-169">用户可以为您提供此值来调查特定邮件。</span><span class="sxs-lookup"><span data-stu-id="e96fd-169">Users can give you this value to investigate specific messages.</span></span>

<span data-ttu-id="e96fd-170">该值在邮件生存期内是常量。</span><span class="sxs-lookup"><span data-stu-id="e96fd-170">This value is constant for the lifetime of the message.</span></span> <span data-ttu-id="e96fd-171">对于在 Microsoft 365 或 Exchange 中创建的邮件，该值的格式为，包括以所使用的角 `<GUID@ServerFQDN>` \< \> () 。</span><span class="sxs-lookup"><span data-stu-id="e96fd-171">For messages created in Microsoft 365 or Exchange, the value is in the format `<GUID@ServerFQDN>`, including the angle brackets (\< \>).</span></span> <span data-ttu-id="e96fd-172">例如，`<d9683b4c-127b-413a-ae2e-fa7dfb32c69d@DM3NAM06BG401.Eop-nam06.prod.protection.outlook.com>`。</span><span class="sxs-lookup"><span data-stu-id="e96fd-172">For example, `<d9683b4c-127b-413a-ae2e-fa7dfb32c69d@DM3NAM06BG401.Eop-nam06.prod.protection.outlook.com>`.</span></span> <span data-ttu-id="e96fd-173">其他邮件系统可能使用不同的语法或值。</span><span class="sxs-lookup"><span data-stu-id="e96fd-173">Other messaging systems might use different syntax or values.</span></span> <span data-ttu-id="e96fd-174">此值应唯一，但并非所有电子邮件系统都严格遵循此要求。</span><span class="sxs-lookup"><span data-stu-id="e96fd-174">This value is supposed to be unique, but not all email systems strictly follow this requirement.</span></span> <span data-ttu-id="e96fd-175">如果 **来自外部源** 的传入邮件不存在或为空，则为该保留的值是任意值。</span><span class="sxs-lookup"><span data-stu-id="e96fd-175">If the **Message-ID:** header field doesn't exist or is blank for incoming messages from external sources, an arbitrary value is assigned.</span></span>

<span data-ttu-id="e96fd-176">使用消息 **ID** 筛选结果时，请确保包含完整字符串，包括任何角括号。</span><span class="sxs-lookup"><span data-stu-id="e96fd-176">When you use **Message ID** to filter the results, be sure to include the full string, including any angle brackets.</span></span>

#### <a name="direction"></a><span data-ttu-id="e96fd-177">Direction</span><span class="sxs-lookup"><span data-stu-id="e96fd-177">Direction</span></span>

<span data-ttu-id="e96fd-178">您可以将默认值设置为 **"所有"默认值，** 或者 **选择发送到您** 组织 (收件人的入站邮件 **) 或从** 组织 (中的用户发送的出站邮件) 来筛选结果。</span><span class="sxs-lookup"><span data-stu-id="e96fd-178">You can leave the default value **All** selected, or you can select **Inbound** (messages sent to recipients in your organization) or **Outbound** (messages sent from users in your organization) to filter the results.</span></span>

#### <a name="original-client-ip-address"></a><span data-ttu-id="e96fd-179">原始客户端 IP 地址</span><span class="sxs-lookup"><span data-stu-id="e96fd-179">Original client IP address</span></span>

<span data-ttu-id="e96fd-180">你可以通过客户端 IP 地址处理结果，调查发送大量垃圾邮件或恶意软件的受损计算机。</span><span class="sxs-lookup"><span data-stu-id="e96fd-180">You can filer the results by client IP address to investigate hacked computers that are sending large amounts of spam or malware.</span></span> <span data-ttu-id="e96fd-181">尽管邮件可能来自多个发件人，但很可能由同一台计算机生成所有邮件。</span><span class="sxs-lookup"><span data-stu-id="e96fd-181">Although the messages might appear to come from multiple senders, it's likely that the same computer is generating all of the messages.</span></span>

<span data-ttu-id="e96fd-182">**注意**：客户端 IP 地址信息仅可查看 10 天，并且仅在**可下载**的 CSV**Extended**文件的增强 (报告或扩展报告) 。</span><span class="sxs-lookup"><span data-stu-id="e96fd-182">**Note**: The client IP address information is only available for 10 days, and is only available in the **Enhanced summary** or **Extended** reports (downloadable CSV files).</span></span>

### <a name="choose-report-type"></a><span data-ttu-id="e96fd-183">选择报表类型</span><span class="sxs-lookup"><span data-stu-id="e96fd-183">Choose report type</span></span>

<span data-ttu-id="e96fd-184">可用的报告类型包括：</span><span class="sxs-lookup"><span data-stu-id="e96fd-184">The available report types are:</span></span>

- <span data-ttu-id="e96fd-185">**摘要**：如果时间范围小于 10 天，并且不需要其他筛选选项，则可用。</span><span class="sxs-lookup"><span data-stu-id="e96fd-185">**Summary**: Available if the time range is less than 10 days, and requires no additional filtering options.</span></span> <span data-ttu-id="e96fd-186">单击"搜索"后，结果将立即 **可用**。</span><span class="sxs-lookup"><span data-stu-id="e96fd-186">The results are available almost immediately after you click **Search**.</span></span> <span data-ttu-id="e96fd-187">报告最多返回 20000 个结果。</span><span class="sxs-lookup"><span data-stu-id="e96fd-187">The report returns up to 20000 results.</span></span>

- <span data-ttu-id="e96fd-188">**增强摘要**或**扩展**：这些报告仅可下载为可下载的 CSV 文件，并需要以下一个或多个筛选选项（与时间范围无处不论 **）：这些人员**、**发送给这些人员**、或**消息 ID。**</span><span class="sxs-lookup"><span data-stu-id="e96fd-188">**Enhanced summary** or **Extended**: These reports are only available as downloadable CSV files, and require one or more of the following filtering options regardless of the time range: **By these people**, **To these people**, or **Message ID**.</span></span> <span data-ttu-id="e96fd-189">可以为发件人或收件人使用通配 (例如 \* ，@contoso.com) 。</span><span class="sxs-lookup"><span data-stu-id="e96fd-189">You can use wildcards for the senders or the recipients (for example, \*@contoso.com).</span></span> <span data-ttu-id="e96fd-190">增强摘要报告将返回多达 50000 个结果。</span><span class="sxs-lookup"><span data-stu-id="e96fd-190">The Enhanced summary report returns up to 50000 results.</span></span> <span data-ttu-id="e96fd-191">"扩展"报告最多返回 1000 个结果。</span><span class="sxs-lookup"><span data-stu-id="e96fd-191">The Extended report returns up to 1000 results.</span></span>

<span data-ttu-id="e96fd-192">**注意**：</span><span class="sxs-lookup"><span data-stu-id="e96fd-192">**Notes**:</span></span>

- <span data-ttu-id="e96fd-193">增强的摘要和扩展报告是使用存档的邮件跟踪数据准备的，并且在下载报告之前可能需要几个小时。</span><span class="sxs-lookup"><span data-stu-id="e96fd-193">Enhanced summary and Extended reports are prepared using archived message trace data, and it can take up to several hours before your report is available to download.</span></span> <span data-ttu-id="e96fd-194">根据其他管理员也同时提交了报告请求的数量，您也可能会注意到在处理队列中的请求之前出现了延迟。</span><span class="sxs-lookup"><span data-stu-id="e96fd-194">Depending on how many other admins have also submitted report requests around the same time, you might also notice a delay before your queued request starts to be processed.</span></span>

- <span data-ttu-id="e96fd-195">虽然可以为任何日期/时间范围选择增强摘要或扩展报告，但通常，最后四小时存档的数据还未可用于这两种类型的报告。</span><span class="sxs-lookup"><span data-stu-id="e96fd-195">While you can select an Enhanced summary or Extended report for any date/time range, commonly the last four hours of archived data will not yet be available for these two types of reports.</span></span>

<span data-ttu-id="e96fd-196">单击" **下一步**"时，会看到摘要页，其中列出了所选的筛选选项、该报告的唯一 (可编辑) 标题以及在邮件跟踪完成后收到通知的电子邮件地址 (也可编辑，并且必须是组织的接受的域) 之一。</span><span class="sxs-lookup"><span data-stu-id="e96fd-196">When you click **Next**, you're presented with a summary page that lists the filtering options that you selected, a unique (editable) title for the report, and the email address that receives the notification when the message trace completes (also editable, and must be in one of your organization's accepted domains).</span></span> <span data-ttu-id="e96fd-197">单击 **"准备** 报告"提交邮件跟踪。</span><span class="sxs-lookup"><span data-stu-id="e96fd-197">Click **Prepare report** to submit the message trace.</span></span> <span data-ttu-id="e96fd-198">在主 **"邮件跟踪** "页面上，您可以在"可下载的报告"部分 **看到报告的** 状态。</span><span class="sxs-lookup"><span data-stu-id="e96fd-198">On the main **Message trace** page, you can see the status of the report in the **Downloadable reports** section.</span></span>

<span data-ttu-id="e96fd-199">有关在不同报告类型中返回的信息的详细信息，请参阅下一节。</span><span class="sxs-lookup"><span data-stu-id="e96fd-199">For more information about the information that's returned in the different report types, see the next section.</span></span>

## <a name="message-trace-results"></a><span data-ttu-id="e96fd-200">邮件跟踪结果</span><span class="sxs-lookup"><span data-stu-id="e96fd-200">Message trace results</span></span>

<span data-ttu-id="e96fd-201">不同的报告类型返回不同级别的信息。</span><span class="sxs-lookup"><span data-stu-id="e96fd-201">The different report types return different levels of information.</span></span> <span data-ttu-id="e96fd-202">不同报告中提供的信息在以下各节中进行了介绍。</span><span class="sxs-lookup"><span data-stu-id="e96fd-202">The information that's available in the different reports is described in the following sections.</span></span>

### <a name="summary-report-output"></a><span data-ttu-id="e96fd-203">摘要报告输出</span><span class="sxs-lookup"><span data-stu-id="e96fd-203">Summary report output</span></span>

<span data-ttu-id="e96fd-204">运行邮件跟踪后，将按最近一次跟踪的降序排序结果，按降序 (排序) 。</span><span class="sxs-lookup"><span data-stu-id="e96fd-204">After running the message trace, the results will be listed, sorted by descending date/time (most recent first).</span></span>

![安全与合规中心内的邮件跟踪的摘要&结果](../../media/0664bafe-0b03-477b-b571-0b046ac8c977.png)

<span data-ttu-id="e96fd-206">摘要报告包含以下信息：</span><span class="sxs-lookup"><span data-stu-id="e96fd-206">The summary report contains the following information:</span></span>

- <span data-ttu-id="e96fd-207">**日期**：服务收到邮件的日期及时间（使用配置的 UTC 时区）。</span><span class="sxs-lookup"><span data-stu-id="e96fd-207">**Date**: The date and time at which the message was received by the service, using the configured UTC time zone.</span></span>

- <span data-ttu-id="e96fd-208">**发件人**：发件人完全\* (域\* @ *domain*) 。</span><span class="sxs-lookup"><span data-stu-id="e96fd-208">**Sender**: The email address of the sender (*alias*@*domain*).</span></span>

- <span data-ttu-id="e96fd-209">**收件人**：收件人电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="e96fd-209">**Recipient**: The email address of the recipient or recipients.</span></span> <span data-ttu-id="e96fd-210">对于发送给多个收件人的邮件，每个收件人每行对应一行。</span><span class="sxs-lookup"><span data-stu-id="e96fd-210">For a message sent to multiple recipients, there's one line per recipient.</span></span> <span data-ttu-id="e96fd-211">如果收件人是通讯组、动态通讯组或已启用邮件的安全组，则该组将第一个收件人，然后组中的每个成员分别位于单独的行。</span><span class="sxs-lookup"><span data-stu-id="e96fd-211">If the recipient is a distribution group, dynamic distribution group, or mail-enabled security group, the group will be the first recipient, and then each member of the group is on a separate line.</span></span>

- <span data-ttu-id="e96fd-212">**Subject：** 邮件主题的前 256 个字符 **：** 字段。</span><span class="sxs-lookup"><span data-stu-id="e96fd-212">**Subject**: The first 256 characters of the message's **Subject:** field.</span></span>

- <span data-ttu-id="e96fd-213">**状态**："送达状态"部分中 [描述了这些](#delivery-status) 值。</span><span class="sxs-lookup"><span data-stu-id="e96fd-213">**Status**: These values are described in the [Delivery status](#delivery-status) section.</span></span>

<span data-ttu-id="e96fd-214">默认情况下，前 250 个结果已加载并就可用。</span><span class="sxs-lookup"><span data-stu-id="e96fd-214">By default, the first 250 results are loaded and readily available.</span></span> <span data-ttu-id="e96fd-215">向下滚动时，随后会有轻微暂停，因为会加载下一批结果。</span><span class="sxs-lookup"><span data-stu-id="e96fd-215">When you scroll down, there's a slight pause as the next batch of results are loaded.</span></span> <span data-ttu-id="e96fd-216">可以单击"全部加载"，以将**Load all**所有结果加载到最多 10，000 个，而不是滚动。</span><span class="sxs-lookup"><span data-stu-id="e96fd-216">Instead of scrolling, you can click **Load all** to load all of the results up to a maximum of 10,000.</span></span>

<span data-ttu-id="e96fd-217">您可以单击列标题，按该列中的值以升序或降序对结果进行排序。</span><span class="sxs-lookup"><span data-stu-id="e96fd-217">You can click on the column headers to sort the results by the values in that column in ascending or descending order.</span></span>

<span data-ttu-id="e96fd-218">可以单击 **"筛选结果** "，按一个或多个列筛选结果。</span><span class="sxs-lookup"><span data-stu-id="e96fd-218">You can click **Filter results** to filter the results by one or more columns.</span></span>

<span data-ttu-id="e96fd-219">选择一个或多个行后，可通过单击"导出结果"，然后选择"**导出**所有结果、导出**已**加载结果"或"导出**Export loaded results\*\*\*\*"选择来导出结果**。</span><span class="sxs-lookup"><span data-stu-id="e96fd-219">You can export the results after you've selected one or more rows by clicking **Export results** and then selecting **Export all results**, **Export loaded results**, or **Export selected**.</span></span>

#### <a name="find-related-records-for-this-message"></a><span data-ttu-id="e96fd-220">查找此邮件的相关记录</span><span class="sxs-lookup"><span data-stu-id="e96fd-220">Find related records for this message</span></span>

<span data-ttu-id="e96fd-221">相关邮件记录是共享同一个邮件 ID 的记录。</span><span class="sxs-lookup"><span data-stu-id="e96fd-221">Related message records are records that shared the same Message ID.</span></span> <span data-ttu-id="e96fd-222">请记住，甚至在两个人员之间发送的一封邮件也可以生成多个记录。</span><span class="sxs-lookup"><span data-stu-id="e96fd-222">Remember, even a single message sent between two people can generate multiple records.</span></span> <span data-ttu-id="e96fd-223">邮件受通讯组扩展、转发、邮件流规则 (也称为传输规则 (等）影响的) 记录数目增加。</span><span class="sxs-lookup"><span data-stu-id="e96fd-223">The number of records increases when the message is affected by distribution group expansion, forwarding, mail flow rules (also known as transport rules), etc.</span></span>

<span data-ttu-id="e96fd-224">选中行的复选框后，可以通过以下方法查找邮件的相关记录：单击出现的 **"查找相关**按钮"，或通过选择"**此**邮件索引的更多查找 ![ ](../../media/1ea52bbf-9d00-48ce-9362-307f7f6fb7fe.png) \> **相关) 。**</span><span class="sxs-lookup"><span data-stu-id="e96fd-224">After you select a row's check box, you can find related records for the message by clicking the **Find related** button that appears, or by selecting **More options** ![More](../../media/1ea52bbf-9d00-48ce-9362-307f7f6fb7fe.png) \> **Find related records for this message**).</span></span>

<span data-ttu-id="e96fd-225">有关邮件 ID 的详细信息，请参阅本主题前面的"邮件 ID"部分。</span><span class="sxs-lookup"><span data-stu-id="e96fd-225">For more information about the Message ID, see the Message ID section earlier in this topic.</span></span>

#### <a name="message-trace-details"></a><span data-ttu-id="e96fd-226">邮件跟踪详细信息</span><span class="sxs-lookup"><span data-stu-id="e96fd-226">Message trace details</span></span>

<span data-ttu-id="e96fd-227">在摘要报告输出中，可以使用下列任一方法查看有关邮件的详细信息：</span><span class="sxs-lookup"><span data-stu-id="e96fd-227">In the summary report output, you can view details about a message by using either of the following methods:</span></span>

- <span data-ttu-id="e96fd-228">选择与 (行之外的任何其他行中的任意) 。</span><span class="sxs-lookup"><span data-stu-id="e96fd-228">Select the row (click anywhere in the row except the check box).</span></span>

- <span data-ttu-id="e96fd-229">选中此行的复选框，然后单击"更多选项**更多选项'** ![ ](../../media/1ea52bbf-9d00-48ce-9362-307f7f6fb7fe.png) \> **更多选项' 邮件详细信息"。**</span><span class="sxs-lookup"><span data-stu-id="e96fd-229">Select the row's check box and click **More options** ![More](../../media/1ea52bbf-9d00-48ce-9362-307f7f6fb7fe.png) \> **View message details**.</span></span>

   ![在安全与合规中心内双击摘要报告邮件跟踪中的&的详细信息](../../media/e50ee7cd-810a-4c06-8b58-e56ffd7028d1.png)

<span data-ttu-id="e96fd-231">邮件跟踪详细信息包含摘要报告中不存在的以下附加信息：</span><span class="sxs-lookup"><span data-stu-id="e96fd-231">The message trace details contain the following additional information that's not present in the summary report:</span></span>

- <span data-ttu-id="e96fd-232">**邮件事件**：本节包含的分类有助于对邮件执行的操作进行分类。</span><span class="sxs-lookup"><span data-stu-id="e96fd-232">**Message events**: This section contains classifications that help categorize the actions that the service takes on messages.</span></span> <span data-ttu-id="e96fd-233">**你可能会遇到的一些更** 有趣的事件包括：</span><span class="sxs-lookup"><span data-stu-id="e96fd-233">**Some of the more interesting events** that you might encounter are:</span></span>

  - <span data-ttu-id="e96fd-234">**接收**：服务已收到邮件。</span><span class="sxs-lookup"><span data-stu-id="e96fd-234">**Receive**: The message was received by the service.</span></span>

  - <span data-ttu-id="e96fd-235">**发送**：服务发送邮件。</span><span class="sxs-lookup"><span data-stu-id="e96fd-235">**Send**: The message was sent by the service.</span></span>

  - <span data-ttu-id="e96fd-236">**失败**：邮件无法送达。</span><span class="sxs-lookup"><span data-stu-id="e96fd-236">**Fail**: The message failed to be delivered.</span></span>

  - <span data-ttu-id="e96fd-237">**传递**：邮件已送达到邮箱。</span><span class="sxs-lookup"><span data-stu-id="e96fd-237">**Deliver**: The message was delivered to a mailbox.</span></span>

  - <span data-ttu-id="e96fd-238">**展开**：邮件已发送到展开的通讯组。</span><span class="sxs-lookup"><span data-stu-id="e96fd-238">**Expand**: The message was sent to a distribution group that was expanded.</span></span>

  - <span data-ttu-id="e96fd-239">**转**移：由于内容转换、邮件收件人限制或代理原因，收件人被移动到分条邮件。</span><span class="sxs-lookup"><span data-stu-id="e96fd-239">**Transfer**: Recipients were moved to a bifurcated message because of content conversion, message recipient limits, or agents.</span></span>

  - <span data-ttu-id="e96fd-240">**延迟**：邮件传递延迟，稍后可能重试。</span><span class="sxs-lookup"><span data-stu-id="e96fd-240">**Defer**: The message delivery was postponed and might be re-attempted later.</span></span>

  - <span data-ttu-id="e96fd-241">**已解决**：邮件已基于 Active Directory 查找重定向到新的收件人地址。</span><span class="sxs-lookup"><span data-stu-id="e96fd-241">**Resolved**: The message was redirected to a new recipient address based on an Active Directory look up.</span></span> <span data-ttu-id="e96fd-242">当发生这种情况时，原始收件人地址会被列在邮件跟踪中的单独一行，包括邮件的最终传递状态。</span><span class="sxs-lookup"><span data-stu-id="e96fd-242">When this happens, the original recipient address is listed in a separate row in the message trace along with the final delivery status for the message.</span></span>

  <span data-ttu-id="e96fd-243">注意：</span><span class="sxs-lookup"><span data-stu-id="e96fd-243">Notes:</span></span>

  - <span data-ttu-id="e96fd-244">一封成功送达的邮件将在邮件跟踪中 **生成** 多个事件条目。</span><span class="sxs-lookup"><span data-stu-id="e96fd-244">An uneventful message that's successfully delivered will generate multiple **Event** entries in the message trace.</span></span>

  - <span data-ttu-id="e96fd-245">此列表并不试图十分混解。</span><span class="sxs-lookup"><span data-stu-id="e96fd-245">This list is not meant to be exhaustive.</span></span> <span data-ttu-id="e96fd-246">有关更多事件的说明，请参阅 [邮件跟踪日志中的事件类型](https://docs.microsoft.com/Exchange/mail-flow/transport-logs/message-tracking#event-types-in-the-message-tracking-log)。</span><span class="sxs-lookup"><span data-stu-id="e96fd-246">For descriptions of more events, see [Event types in the message tracking log](https://docs.microsoft.com/Exchange/mail-flow/transport-logs/message-tracking#event-types-in-the-message-tracking-log).</span></span> <span data-ttu-id="e96fd-247">请注意，此链接Exchange Server (Exchange) 主题。</span><span class="sxs-lookup"><span data-stu-id="e96fd-247">Note that this link is an Exchange Server (on-premises Exchange) topic.</span></span>

- <span data-ttu-id="e96fd-248">**详细信息**：此节包含下列详细信息：</span><span class="sxs-lookup"><span data-stu-id="e96fd-248">**More information**: This section contains the following details:</span></span>

  - <span data-ttu-id="e96fd-249">**邮件 ID：** 此值在本主题前面的"邮件 [ID"](#message-id) 部分中说明。</span><span class="sxs-lookup"><span data-stu-id="e96fd-249">**Message ID**: This value is described in the [Message ID](#message-id) section earlier in this topic.</span></span> <span data-ttu-id="e96fd-250">例如，`<d9683b4c-127b-413a-ae2e-fa7dfb32c69d@DM3NAM06BG401.Eop-nam06.prod.protection.outlook.com>`。</span><span class="sxs-lookup"><span data-stu-id="e96fd-250">For example, `<d9683b4c-127b-413a-ae2e-fa7dfb32c69d@DM3NAM06BG401.Eop-nam06.prod.protection.outlook.com>`.</span></span>

  - <span data-ttu-id="e96fd-251">**邮件大小**</span><span class="sxs-lookup"><span data-stu-id="e96fd-251">**Message size**</span></span>

  - <span data-ttu-id="e96fd-252">**自 IP：** 发送邮件的计算机的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="e96fd-252">**From IP**: The IP address of the computer that sent the message.</span></span> <span data-ttu-id="e96fd-253">对于从 Exchange Online 发送的出站邮件，该值是空值。</span><span class="sxs-lookup"><span data-stu-id="e96fd-253">For outbound messages sent from Exchange Online, this value is blank.</span></span>

  - <span data-ttu-id="e96fd-254">**To IP：** 该服务尝试递送邮件的 IP 地址或地址。</span><span class="sxs-lookup"><span data-stu-id="e96fd-254">**To IP**: The IP address or addresses where the service attempted to deliver the message.</span></span> <span data-ttu-id="e96fd-255">如果邮件有多个收件人，则会显示这些内容。</span><span class="sxs-lookup"><span data-stu-id="e96fd-255">If the message has multiple recipients, these are displayed.</span></span> <span data-ttu-id="e96fd-256">对于发送到 Exchange Online 的入站邮件，该值是空值。</span><span class="sxs-lookup"><span data-stu-id="e96fd-256">For inbound messages sent to Exchange Online, this value is blank.</span></span>

### <a name="enhanced-summary-reports"></a><span data-ttu-id="e96fd-257">增强的摘要报告</span><span class="sxs-lookup"><span data-stu-id="e96fd-257">Enhanced summary reports</span></span>

<span data-ttu-id="e96fd-258">最近 (已) 汇总报告中提供"开始"邮件 **跟踪** 的"可下载报告"部分。</span><span class="sxs-lookup"><span data-stu-id="e96fd-258">Available (completed) Enhanced summary reports are available in the **Downloadable reports** section at the beginning message trace.</span></span> <span data-ttu-id="e96fd-259">报告中包含以下信息：</span><span class="sxs-lookup"><span data-stu-id="e96fd-259">The following information is available in the report:</span></span>

- <span data-ttu-id="e96fd-260">**origin_timestamp：** <sup>\*</sup> 服务使用配置的 UTC 时区获取邮件的最初日期和时间。</span><span class="sxs-lookup"><span data-stu-id="e96fd-260">**origin_timestamp**<sup>\*</sup>: The date and time when the message was initially received by the service, using the configured UTC time zone.</span></span>

- <span data-ttu-id="e96fd-261">**sender_address：** 发件人的电子邮件地址 (*域* @ *) 。*</span><span class="sxs-lookup"><span data-stu-id="e96fd-261">**sender_address**: The sender's email address (*alias*@*domain*).</span></span>

- <span data-ttu-id="e96fd-262">**Recipient_status：** 向收件人传递邮件的状态。</span><span class="sxs-lookup"><span data-stu-id="e96fd-262">**Recipient_status**: The status of the delivery of the message to the recipient.</span></span> <span data-ttu-id="e96fd-263">如果邮件发送至多个收件人，将显示所有收件人和每个收件人的相应状态，格式如下 \<*email address*\> ## \<*status*\> ：。</span><span class="sxs-lookup"><span data-stu-id="e96fd-263">If the message was sent to multiple recipients, it will show all the recipients and the corresponding status for each, in the format: \<*email address*\>##\<*status*\>.</span></span> <span data-ttu-id="e96fd-264">例如：</span><span class="sxs-lookup"><span data-stu-id="e96fd-264">For example:</span></span>

  - <span data-ttu-id="e96fd-265">**##Receive，发送** 表示服务已接收邮件，并发送到预定的目标地址。</span><span class="sxs-lookup"><span data-stu-id="e96fd-265">**##Receive, Send** means the message was received by the service and was sent to the intended destination.</span></span>

  - <span data-ttu-id="e96fd-266">**##Receive，失败** 表示服务已接收邮件，但传递到预定的目标失败。</span><span class="sxs-lookup"><span data-stu-id="e96fd-266">**##Receive, Fail** means the message was received by the service but delivery to the intended destination failed.</span></span>

  - <span data-ttu-id="e96fd-267">**##Receive，** 传递表示服务已接收邮件，并且传递给收件人的邮箱。</span><span class="sxs-lookup"><span data-stu-id="e96fd-267">**##Receive, Deliver** means the message was received by the service and was delivered to the recipient's mailbox.</span></span>

- <span data-ttu-id="e96fd-268">**message_subject：** 邮件"主题"字段中的前 256 **个** 字符。</span><span class="sxs-lookup"><span data-stu-id="e96fd-268">**message_subject**: The first 256 characters of the message's **Subject** field.</span></span>

- <span data-ttu-id="e96fd-269">**total_bytes：** 邮件大小（以字节为单位），包括附件。</span><span class="sxs-lookup"><span data-stu-id="e96fd-269">**total_bytes**: The size of the message in bytes, including attachments.</span></span>

- <span data-ttu-id="e96fd-270">**message_id：** 此值在本主题前面介绍的"邮件 [ID"](#message-id) 部分中所述。</span><span class="sxs-lookup"><span data-stu-id="e96fd-270">**message_id**: This value is described in the [Message ID](#message-id) section earlier in this topic.</span></span> <span data-ttu-id="e96fd-271">例如，`<d9683b4c-127b-413a-ae2e-fa7dfb32c69d@DM3NAM06BG401.Eop-nam06.prod.protection.outlook.com>`。</span><span class="sxs-lookup"><span data-stu-id="e96fd-271">For example, `<d9683b4c-127b-413a-ae2e-fa7dfb32c69d@DM3NAM06BG401.Eop-nam06.prod.protection.outlook.com>`.</span></span>

- <span data-ttu-id="e96fd-272">**network_message_id：** 唯一的邮件 ID 值，因分类或通讯组扩展而创建，在所有邮件副本中均保持有效。</span><span class="sxs-lookup"><span data-stu-id="e96fd-272">**network_message_id**: A unique message ID value that persists across all copies of the message that might be created due to bifurcation or distribution group expansion.</span></span> <span data-ttu-id="e96fd-273">示例值为 `1341ac7b13fb42ab4d4408cf7f55890f` 。</span><span class="sxs-lookup"><span data-stu-id="e96fd-273">An example value is `1341ac7b13fb42ab4d4408cf7f55890f`.</span></span>

- <span data-ttu-id="e96fd-274">**original_client_ip：** 发件人客户端的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="e96fd-274">**original_client_ip**: The IP address of the sender's client.</span></span>

- <span data-ttu-id="e96fd-275">**方向性：** 指示是发送的是发送到组织的入站 (1) 还是从组织发送出站邮件 (2) 步。</span><span class="sxs-lookup"><span data-stu-id="e96fd-275">**directionality**: Indicates whether the message was sent inbound (1) to your organization, or whether it was sent outbound (2) from your organization.</span></span>

- <span data-ttu-id="e96fd-276">**connector_id：** 源或目的地连接器的名称。</span><span class="sxs-lookup"><span data-stu-id="e96fd-276">**connector_id**: The name of the source or destination connector.</span></span> <span data-ttu-id="e96fd-277">有关 Exchange Online 中的连接器的详细信息，请参阅 [在 Office 365 中使用连接器配置邮件流](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)。</span><span class="sxs-lookup"><span data-stu-id="e96fd-277">For more information about connectors in Exchange Online, see [Configure mail flow using connectors in Office 365](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow).</span></span>

- <span data-ttu-id="e96fd-278">**delivery_priority：** <sup>\*</sup> 邮件发送的优先级**是高、\*\*\*\*低\*\*\*\*还是普**通优先级。</span><span class="sxs-lookup"><span data-stu-id="e96fd-278">**delivery_priority**<sup>\*</sup>: Whether the message was sent with **High**, **Low**, or **Normal** priority.</span></span>

<span data-ttu-id="e96fd-279"><sup>\*</sup>这些属性只提供于增强摘要报告。</span><span class="sxs-lookup"><span data-stu-id="e96fd-279"><sup>\*</sup>These properties are only available in Enhanced summary reports.</span></span>

### <a name="extended-reports"></a><span data-ttu-id="e96fd-280">扩展的报表</span><span class="sxs-lookup"><span data-stu-id="e96fd-280">Extended reports</span></span>

<span data-ttu-id="e96fd-281">邮件 (开始) 中的"可下载报告" **部分** 提供已完成的已完成报告。</span><span class="sxs-lookup"><span data-stu-id="e96fd-281">Available (completed) Extended reports are available in the **Downloadable reports** section at the beginning of message trace.</span></span> <span data-ttu-id="e96fd-282">增强报告的大部分信息都适用于扩展报告中的 (例如，**除origin_timestamp和delivery_priority) 。** **delivery_priority**</span><span class="sxs-lookup"><span data-stu-id="e96fd-282">Virtually all of the information from an Enhanced summary report is available in an Extended report (with the exception of **origin_timestamp** and **delivery_priority**).</span></span> <span data-ttu-id="e96fd-283">下面其他信息只适用于扩展报告：</span><span class="sxs-lookup"><span data-stu-id="e96fd-283">The following additional information is only available in an Extended report:</span></span>

- <span data-ttu-id="e96fd-284">**client_ip：** 提交邮件的电子邮件服务器或消息客户端的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="e96fd-284">**client_ip**: The IP address of the email server or messaging client that submitted the message.</span></span>

- <span data-ttu-id="e96fd-285">**client_hostname：** 提交邮件的电子邮件服务器或消息客户端的主机名或 FQDN。</span><span class="sxs-lookup"><span data-stu-id="e96fd-285">**client_hostname**: The host name or FQDN of the email server or messaging client that submitted the message.</span></span>

- <span data-ttu-id="e96fd-286">**server_ip：** 源或目标服务器的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="e96fd-286">**server_ip**: The IP address of the source or destination server.</span></span>

- <span data-ttu-id="e96fd-287">**server_hostname：** 目标服务器的主机名或 FQDN。</span><span class="sxs-lookup"><span data-stu-id="e96fd-287">**server_hostname**: The host name or FQDN of the destination server.</span></span>

- <span data-ttu-id="e96fd-288">**source_context：** 与源字段关联的 **额外** 信息。</span><span class="sxs-lookup"><span data-stu-id="e96fd-288">**source_context**: Extra information associated with the **source** field.</span></span> <span data-ttu-id="e96fd-289">例如：</span><span class="sxs-lookup"><span data-stu-id="e96fd-289">For example:</span></span>

  - `Protocol Filter Agent`

  - `3489061114359050000`

- <span data-ttu-id="e96fd-290">**source：** 负责事件的 Exchange Online 组件。</span><span class="sxs-lookup"><span data-stu-id="e96fd-290">**source**: The Exchange Online component that's responsible for the event.</span></span> <span data-ttu-id="e96fd-291">例如：</span><span class="sxs-lookup"><span data-stu-id="e96fd-291">For example:</span></span>

  - `AGENT`

  - `MAILBOXRULE`

  - `SMTP`

- <span data-ttu-id="e96fd-292">**event_id**：这些对应于此 **邮件部分** 的"查找相关记录"中 [说明的](#find-related-records-for-this-message) Message 事件值。</span><span class="sxs-lookup"><span data-stu-id="e96fd-292">**event_id**: These correspond to the **Message event** values that are explained in the [Find related records for this message](#find-related-records-for-this-message) section.</span></span>

- <span data-ttu-id="e96fd-293">**internal_message_id：** 由当前正在处理该邮件的 Exchange Online 服务器分配的邮件标识符。</span><span class="sxs-lookup"><span data-stu-id="e96fd-293">**internal_message_id**: A message identifier that's assigned by the Exchange Online server that's currently processing the message.</span></span>

- <span data-ttu-id="e96fd-294">**recipient_address：** 邮件收件人的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="e96fd-294">**recipient_address**: The email addresses of the message's recipients.</span></span> <span data-ttu-id="e96fd-295">多个电子邮件地址通过分号字符 (;) 分隔。</span><span class="sxs-lookup"><span data-stu-id="e96fd-295">Multiple email addresses are separated by the semicolon character (;).</span></span>

- <span data-ttu-id="e96fd-296">**recipient_count：** 邮件中的收件人总数。</span><span class="sxs-lookup"><span data-stu-id="e96fd-296">**recipient_count**: The total number of recipients in the message.</span></span>

- <span data-ttu-id="e96fd-297">**related_recipient_address：** 与 `EXPAND` 此 `REDIRECT` 一起 `RESOLVE` 使用，使用和事件显示与该邮件相关联的其他收件人电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="e96fd-297">**related_recipient_address**: Used with `EXPAND`, `REDIRECT`, and `RESOLVE` events to display other recipient email addresses that are associated with the message.</span></span>

- <span data-ttu-id="e96fd-298">**参考**：此字段包含特定类型事件的其他信息。</span><span class="sxs-lookup"><span data-stu-id="e96fd-298">**reference**: This field contains additional information for specific types of events.</span></span> <span data-ttu-id="e96fd-299">例如：</span><span class="sxs-lookup"><span data-stu-id="e96fd-299">For example:</span></span>

  - <span data-ttu-id="e96fd-300">**DSN：** 包含报告链接，如果 **DSN 是在事件发生** 之后生成的，则 message_id该报告链接为相关传递状态通知 (也称为 DSN、未送达报告、NDR 或退回邮件消息) 。</span><span class="sxs-lookup"><span data-stu-id="e96fd-300">**DSN**: Contains the report link, which is the **message_id** value of the associated delivery status notification (also known as a DSN, non-delivery report, NDR, or bounce message) if a DSN is generated subsequent to this event.</span></span> <span data-ttu-id="e96fd-301">如果这是 DSN 邮件，则该 **字段message_id** 为其生成 DSN 的原始邮件的有效值。</span><span class="sxs-lookup"><span data-stu-id="e96fd-301">If this is a DSN message, this field contains the **message_id** value of the original message that the DSN was generated for.</span></span>

  - <span data-ttu-id="e96fd-302">**EXPAND**： **包含related_recipient_address** 的电子邮件的字段值。</span><span class="sxs-lookup"><span data-stu-id="e96fd-302">**EXPAND**: Contains the **related_recipient_address** value of the related messages.</span></span>

  - <span data-ttu-id="e96fd-303">**RECEIVE**：如果邮件 **message_id** 由其他过程（如收件箱规则箱 (过程）生成，可能包含相关) 。</span><span class="sxs-lookup"><span data-stu-id="e96fd-303">**RECEIVE**: Might contain the **message_id** value of the related message if the message was generated by other processes (for example, Inbox rules).</span></span>

  - <span data-ttu-id="e96fd-304">**SEND**：包含 **任意 internal_message_id** DSN 邮件的 internal_message_id 值。</span><span class="sxs-lookup"><span data-stu-id="e96fd-304">**SEND**: Contains the **internal_message_id** value of any DSN messages.</span></span>

  - <span data-ttu-id="e96fd-305">**TRANSFER：\*\*\*\*包含被分 (** 外的邮件的internal_message_id个值，例如通过内容转换、邮件收件人限制或代理) 。</span><span class="sxs-lookup"><span data-stu-id="e96fd-305">**TRANSFER**: Contains the **internal_message_id** value of the message that's being forked (for example, by content conversion, message recipient limits, or agents).</span></span>

  - <span data-ttu-id="e96fd-306">**MAILBOXRULE**：包含 **internal_message_id** 收件箱规则生成出站邮件的入站邮件的字段值。</span><span class="sxs-lookup"><span data-stu-id="e96fd-306">**MAILBOXRULE**: Contains the **internal_message_id** value of the inbound message that caused the Inbox rule to generate the outbound message.</span></span>

    <span data-ttu-id="e96fd-307">对于其他类型的事件，此字段通常为空。</span><span class="sxs-lookup"><span data-stu-id="e96fd-307">For other types of events, this field is usually blank.</span></span>

- <span data-ttu-id="e96fd-308">**return_path：** 由发送邮件的 MAIL **FROM** 命令所指定的返回电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="e96fd-308">**return_path**: The return email address specified by the **MAIL FROM** command that sent the message.</span></span> <span data-ttu-id="e96fd-309">尽管此字段从不为空，但它可以有表示为的空发件人地址值 `<>` 。</span><span class="sxs-lookup"><span data-stu-id="e96fd-309">Although this field is never empty, it can have the null sender address value represented as `<>`.</span></span>

- <span data-ttu-id="e96fd-310">**message_info：** 有关邮件的其他信息。</span><span class="sxs-lookup"><span data-stu-id="e96fd-310">**message_info**: Additional information about the message.</span></span> <span data-ttu-id="e96fd-311">例如：</span><span class="sxs-lookup"><span data-stu-id="e96fd-311">For example:</span></span>

  - <span data-ttu-id="e96fd-312">针对和事件的日期-时间（UTC） `DELIVER` `SEND` 消息。</span><span class="sxs-lookup"><span data-stu-id="e96fd-312">The message origination date-time in UTC for `DELIVER` and `SEND` events.</span></span> <span data-ttu-id="e96fd-313">开始日期-时间是邮件第一次进入 Exchange Online 组织的时间。</span><span class="sxs-lookup"><span data-stu-id="e96fd-313">The origination date-time is the time when the message first entered the Exchange Online organization.</span></span> <span data-ttu-id="e96fd-314">UTC 日期-时间以 ISO 8601 日期时间格式表示 `yyyy-mm-ddThh:mm:ss.fffZ` ：，其中 `yyyy` = 年， `mm` = 月， `dd` = 日， 指示时间 `T` 组件的开始， `hh` = 小时， = 分钟， = 秒， = 秒的分数， `mm` `ss` 表示表示 UTC 的另 `fff` `Z` `Zulu` 一种方式。</span><span class="sxs-lookup"><span data-stu-id="e96fd-314">The UTC date-time is represented in the ISO 8601 date-time format: `yyyy-mm-ddThh:mm:ss.fffZ`, where `yyyy` = year, `mm` = month, `dd` = day, `T` indicates the beginning of the time component, `hh` = hour, `mm` = minute, `ss` = second, `fff` = fractions of a second, and `Z` signifies `Zulu`, which is another way to denote UTC.</span></span>

  - <span data-ttu-id="e96fd-315">身份验证错误。</span><span class="sxs-lookup"><span data-stu-id="e96fd-315">Authentication errors.</span></span> <span data-ttu-id="e96fd-316">例如，您可能看到 `11a` 身份验证出错时所使用的验证的值和身份验证类型。</span><span class="sxs-lookup"><span data-stu-id="e96fd-316">For example, you might see the value `11a` and the type of authentication that was used when the authentication error occurred.</span></span>

- <span data-ttu-id="e96fd-317">**tenant_id：** 一个 GUID 值，表示 Exchange Online (例如 `39238e87-b5ab-4ef6-a559-af54c6b07b42` ，) 。</span><span class="sxs-lookup"><span data-stu-id="e96fd-317">**tenant_id**: A GUID value that represents the Exchange Online organization (for example, `39238e87-b5ab-4ef6-a559-af54c6b07b42`).</span></span>

- <span data-ttu-id="e96fd-318">**original_server_ip：** 原始服务器的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="e96fd-318">**original_server_ip**: The IP address of the original server.</span></span>

- <span data-ttu-id="e96fd-319">**custom_data：** 包含与特定事件类型相关的数据。</span><span class="sxs-lookup"><span data-stu-id="e96fd-319">**custom_data**: Contains data related to specific event types.</span></span> <span data-ttu-id="e96fd-320">有关详细信息，请参阅以下各部分。</span><span class="sxs-lookup"><span data-stu-id="e96fd-320">For more information, see the following sections.</span></span>

#### <a name="custom_data-values"></a><span data-ttu-id="e96fd-321">custom_data值</span><span class="sxs-lookup"><span data-stu-id="e96fd-321">custom_data values</span></span>

<span data-ttu-id="e96fd-322">由 **custom_data** Exchange `AGENTINFO` Online 代理使用事件的索引字段来记录邮件处理详细信息。</span><span class="sxs-lookup"><span data-stu-id="e96fd-322">The **custom_data** field for an `AGENTINFO` event is used by a variety of Exchange Online agents to log message processing details.</span></span> <span data-ttu-id="e96fd-323">以下部分中介绍了一些更有趣的代理。</span><span class="sxs-lookup"><span data-stu-id="e96fd-323">Some of the more interesting agents are described in the following sections.</span></span>

#### <a name="spam-filter-agent"></a><span data-ttu-id="e96fd-324">垃圾邮件筛选器代理</span><span class="sxs-lookup"><span data-stu-id="e96fd-324">Spam filter agent</span></span>

<span data-ttu-id="e96fd-325">**"custom_data**以垃圾邮件筛选器 `S:SFA` 代理开始的邮件值。</span><span class="sxs-lookup"><span data-stu-id="e96fd-325">A **custom_data** value that starts with `S:SFA` is from the spam filter agent.</span></span> <span data-ttu-id="e96fd-326">下表介绍了关键详细信息：</span><span class="sxs-lookup"><span data-stu-id="e96fd-326">The key details are described in the following table:</span></span>

****

|<span data-ttu-id="e96fd-327">值</span><span class="sxs-lookup"><span data-stu-id="e96fd-327">Value</span></span>|<span data-ttu-id="e96fd-328">说明</span><span class="sxs-lookup"><span data-stu-id="e96fd-328">Description</span></span>|
|---|---|
|`SFV=NSPM`|<span data-ttu-id="e96fd-329">邮件被标记为非垃圾邮件并发送给预期收件人。</span><span class="sxs-lookup"><span data-stu-id="e96fd-329">The message was marked as non-spam and was sent to the intended recipients.</span></span>|
|`SFV=SPM`|<span data-ttu-id="e96fd-330">邮件被反垃圾邮件筛选功能和 (内容筛选功能）被) 。</span><span class="sxs-lookup"><span data-stu-id="e96fd-330">The message was marked as spam by anti-spam filtering (also known as content filtering).</span></span>|
|`SFV=BLK`|<span data-ttu-id="e96fd-331">跳过筛选但阻止邮件，因为它是由已阻止发件人发送。</span><span class="sxs-lookup"><span data-stu-id="e96fd-331">Filtering was skipped and the message was blocked because it originated from a blocked sender.</span></span>|
|`SFV=SKS`|<span data-ttu-id="e96fd-332">邮件在被反垃圾邮件筛选处理之前被标记为垃圾邮件。</span><span class="sxs-lookup"><span data-stu-id="e96fd-332">The message was marked as spam prior to being processed by anti-spam filtering.</span></span> <span data-ttu-id="e96fd-333">这包括符合以下邮件流程规则条件（也称为传输规则）的邮件：自动将邮件标记为垃圾邮件并规避其他所有筛选。</span><span class="sxs-lookup"><span data-stu-id="e96fd-333">This includes messages where the message matched a mail flow rule (also known as a transport rule) to automatically mark it as spam and bypass all additional filtering.</span></span>|
|`SCL=<number>`|<span data-ttu-id="e96fd-334">有关不同的 SCL 值及其含义的详细信息，请参阅[垃圾邮件可信度](spam-confidence-levels.md)。</span><span class="sxs-lookup"><span data-stu-id="e96fd-334">For more information about the different SCL values and what they mean, see [Spam confidence levels](spam-confidence-levels.md).</span></span>|
|`PCL=<number>`|<span data-ttu-id="e96fd-p155">邮件的仿冒可能性等级 (PCL) 值。可按照[垃圾邮件可信度](spam-confidence-levels.md)中介绍 SCL 值的方式对这些值做出解释。  </span><span class="sxs-lookup"><span data-stu-id="e96fd-p155">The Phishing Confidence Level (PCL) value of the message. These can be interpreted the same way as the SCL values documented in [Spam confidence levels](spam-confidence-levels.md).</span></span>|
|`DI=SB`|<span data-ttu-id="e96fd-337">已阻止邮件发件人。</span><span class="sxs-lookup"><span data-stu-id="e96fd-337">The sender of the message was blocked.</span></span>|
|`DI=SQ`|<span data-ttu-id="e96fd-338">邮件已隔离。</span><span class="sxs-lookup"><span data-stu-id="e96fd-338">The message was quarantined.</span></span>|
|`DI=SD`|<span data-ttu-id="e96fd-339">邮件已删除。</span><span class="sxs-lookup"><span data-stu-id="e96fd-339">The message was deleted.</span></span>|
|`DI=SJ`|<span data-ttu-id="e96fd-340">邮件已发送至收件人的"垃圾邮件"文件夹。</span><span class="sxs-lookup"><span data-stu-id="e96fd-340">The message was sent to the recipient's Junk Email folder.</span></span>|
|`DI=SN`|<span data-ttu-id="e96fd-341">邮件已通过正常出站传送池路由。</span><span class="sxs-lookup"><span data-stu-id="e96fd-341">The message was routed through the normal outbound delivery pool.</span></span>|
|`DI=SO`|<span data-ttu-id="e96fd-342">邮件已通过高风险传送池路由。</span><span class="sxs-lookup"><span data-stu-id="e96fd-342">The message was routed through the higher risk delivery pool.</span></span> <span data-ttu-id="e96fd-343">有关详细信息，请参阅[出站邮件的高风险传递池](high-risk-delivery-pool-for-outbound-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="e96fd-343">For more information, see [High-risk delivery pool for outbound messages](high-risk-delivery-pool-for-outbound-messages.md).</span></span>|
|`SFS=[a]|SFS=[b]`|<span data-ttu-id="e96fd-344">说明匹配此垃圾邮件规则。</span><span class="sxs-lookup"><span data-stu-id="e96fd-344">This denotes that spam rules were matched.</span></span>|
|`IPV=CAL`|<span data-ttu-id="e96fd-345">邮件已获得垃圾邮件筛选器的允许，因为 IP 地址已在连接筛选器的 IP 允许列表中指定。</span><span class="sxs-lookup"><span data-stu-id="e96fd-345">The message was allowed through the spam filters because the IP address was specified in an IP Allow list in the connection filter.</span></span>|
|`H=<EHLOstring>`|<span data-ttu-id="e96fd-346">连接电子邮件服务器的 HELO 或 EHLO 字符串。</span><span class="sxs-lookup"><span data-stu-id="e96fd-346">The HELO or EHLO string of the connecting email server.</span></span>|
|`PTR=<ReverseDNS>`|<span data-ttu-id="e96fd-347">发送 IP 地址的 PTR 记录，也被称为反向 DNS 地址。</span><span class="sxs-lookup"><span data-stu-id="e96fd-347">The PTR record of the sending IP address, also known as the reverse DNS address.</span></span>|
|

<span data-ttu-id="e96fd-348">筛选 **custom_data** 如下所示的邮件的示例搜索值：</span><span class="sxs-lookup"><span data-stu-id="e96fd-348">An example **custom_data** value for a message that's filtered for spam like this:</span></span>

`S:SFA=SUM|SFV=SPM|IPV=CAL|SRV=BULK|SFS=470454002|SFS=349001|SCL=9|SCORE=-1|LIST=0|DI=SN|RD=ftmail.inc.com|H=ftmail.inc.com|CIP=98.129.140.74|SFP=1501|ASF=1|CTRY=US|CLTCTRY=|LANG=en|LAT=287|LAT=260|LAT=18;`

#### <a name="malware-filter-agent"></a><span data-ttu-id="e96fd-349">恶意软件筛选器代理</span><span class="sxs-lookup"><span data-stu-id="e96fd-349">Malware filter agent</span></span>

<span data-ttu-id="e96fd-350">**"custom_data**数值来自 `S:AMA` 恶意软件筛选器代理。</span><span class="sxs-lookup"><span data-stu-id="e96fd-350">A **custom_data** value that starts with `S:AMA` is from the malware filter agent.</span></span> <span data-ttu-id="e96fd-351">下表介绍了关键详细信息：</span><span class="sxs-lookup"><span data-stu-id="e96fd-351">The key details are described in the following table:</span></span>

****

|<span data-ttu-id="e96fd-352">值</span><span class="sxs-lookup"><span data-stu-id="e96fd-352">Value</span></span>|<span data-ttu-id="e96fd-353">说明</span><span class="sxs-lookup"><span data-stu-id="e96fd-353">Description</span></span>|
|---|---|
|<span data-ttu-id="e96fd-354">`AMA=SUM|v=1|` 或 `AMA=EV|v=1`</span><span class="sxs-lookup"><span data-stu-id="e96fd-354">`AMA=SUM|v=1|` or `AMA=EV|v=1`</span></span>|<span data-ttu-id="e96fd-355">已确定此邮件包含恶意软件。</span><span class="sxs-lookup"><span data-stu-id="e96fd-355">The message was determined to contain malware.</span></span> <span data-ttu-id="e96fd-356">`SUM` 指示恶意软件可能已由任意数量的引擎检测到。</span><span class="sxs-lookup"><span data-stu-id="e96fd-356">`SUM` indicates the malware could've been detected by any number of engines.</span></span> <span data-ttu-id="e96fd-357">`EV` 指示特定引擎检测到恶意软件。</span><span class="sxs-lookup"><span data-stu-id="e96fd-357">`EV` indicates the malware was detected by a specific engine.</span></span> <span data-ttu-id="e96fd-358">引擎检测到恶意软件后，将触发后续操作。</span><span class="sxs-lookup"><span data-stu-id="e96fd-358">When malware is detected by an engine this triggers the subsequent actions.</span></span>|
|`Action=r`|<span data-ttu-id="e96fd-359">邮件已被替换。</span><span class="sxs-lookup"><span data-stu-id="e96fd-359">The message was replaced.</span></span>|
|`Action=p`|<span data-ttu-id="e96fd-360">邮件已被忽略。</span><span class="sxs-lookup"><span data-stu-id="e96fd-360">The message was bypassed.</span></span>|
|`Action=d`|<span data-ttu-id="e96fd-361">邮件已被延迟。</span><span class="sxs-lookup"><span data-stu-id="e96fd-361">The message was deferred.</span></span>|
|`Action=s`|<span data-ttu-id="e96fd-362">邮件已删除。</span><span class="sxs-lookup"><span data-stu-id="e96fd-362">The message was deleted.</span></span>|
|`Action=st`|<span data-ttu-id="e96fd-363">邮件已被忽略。</span><span class="sxs-lookup"><span data-stu-id="e96fd-363">The message was bypassed.</span></span>|
|`Action=sy`|<span data-ttu-id="e96fd-364">邮件已被忽略。</span><span class="sxs-lookup"><span data-stu-id="e96fd-364">The message was bypassed.</span></span>|
|`Action=ni`|<span data-ttu-id="e96fd-365">邮件已被拒绝。</span><span class="sxs-lookup"><span data-stu-id="e96fd-365">The message was rejected.</span></span>|
|`Action=ne`|<span data-ttu-id="e96fd-366">邮件已被拒绝。</span><span class="sxs-lookup"><span data-stu-id="e96fd-366">The message was rejected.</span></span>|
|`Action=b`|<span data-ttu-id="e96fd-367">邮件已被阻止。</span><span class="sxs-lookup"><span data-stu-id="e96fd-367">The message was blocked.</span></span>|
|`Name=<malware>`|<span data-ttu-id="e96fd-368">已检测到的恶意软件的名称。</span><span class="sxs-lookup"><span data-stu-id="e96fd-368">The name of the malware that was detected.</span></span>|
|`File=<filename>`|<span data-ttu-id="e96fd-369">恶意软件中包含的文件名称。</span><span class="sxs-lookup"><span data-stu-id="e96fd-369">The name of the file that contained the malware.</span></span>|
|

<span data-ttu-id="e96fd-370">包含 **custom_data** 的邮件的示例用户示例如下所示：</span><span class="sxs-lookup"><span data-stu-id="e96fd-370">An example **custom_data** value for a message that contains malware looks like this:</span></span>

`S:AMA=SUM|v=1|action=b|error=|atch=1;S:AMA=EV|engine=M|v=1|sig=1.155.974.0|name=DOS/Test_File|file=filename;S:AMA=EV|engine=A|v=1|sig=201707282038|name=Test_File|file=filename`

#### <a name="transport-rule-agent"></a><span data-ttu-id="e96fd-371">传输规则代理</span><span class="sxs-lookup"><span data-stu-id="e96fd-371">Transport Rule agent</span></span>

<span data-ttu-id="e96fd-372">一 **custom_data** 值来自 `S:TRA` 邮件流规则代理，亦称为 (规则代理"的") 。</span><span class="sxs-lookup"><span data-stu-id="e96fd-372">A **custom_data** value that starts with`S:TRA` is from the Transport Rule agent for mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="e96fd-373">下表介绍了关键详细信息：</span><span class="sxs-lookup"><span data-stu-id="e96fd-373">The key details are described in the following table:</span></span>

****

|<span data-ttu-id="e96fd-374">值</span><span class="sxs-lookup"><span data-stu-id="e96fd-374">Value</span></span>|<span data-ttu-id="e96fd-375">说明</span><span class="sxs-lookup"><span data-stu-id="e96fd-375">Description</span></span>|
|---|---|
|`ETR|ruleId=<guid>`|<span data-ttu-id="e96fd-376">匹配的规则 ID。</span><span class="sxs-lookup"><span data-stu-id="e96fd-376">The rule ID that was matched.</span></span>|
|`St=<datetime>`|<span data-ttu-id="e96fd-377">规则匹配时的日期和时间（UTC 时间）。</span><span class="sxs-lookup"><span data-stu-id="e96fd-377">The date and time in UTC when the rule match occurred.</span></span>|
|`Action=<ActionDefinition>`|<span data-ttu-id="e96fd-378">应用的操作。</span><span class="sxs-lookup"><span data-stu-id="e96fd-378">The action that was applied.</span></span> <span data-ttu-id="e96fd-379">有关可取操作的列表，请参阅 [Exchange Online 中的邮件流规则操作](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)。</span><span class="sxs-lookup"><span data-stu-id="e96fd-379">For a list of available actions, see [Mail flow rule actions in Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).</span></span>|
|`Mode=<Mode>`|<span data-ttu-id="e96fd-380">规则模式。</span><span class="sxs-lookup"><span data-stu-id="e96fd-380">The mode of the rule.</span></span> <span data-ttu-id="e96fd-381">有效值为：</span><span class="sxs-lookup"><span data-stu-id="e96fd-381">Valid values are:</span></span><ul><li><span data-ttu-id="e96fd-382">**强制**：将强制实施规则的所有操作。</span><span class="sxs-lookup"><span data-stu-id="e96fd-382">**Enforce**: All actions on the rule will be enforced.</span></span></li><li><span data-ttu-id="e96fd-383">**在使用策略提示的情况下测试：** 将发送所有策略提示操作，但不会作用于其他强制实施操作。</span><span class="sxs-lookup"><span data-stu-id="e96fd-383">**Test with Policy Tips:**: Any Policy Tip actions will be sent, but other enforcement actions will not be acted on.</span></span></li><li><span data-ttu-id="e96fd-384">**在不使用策略提示**的情况下测试：将在活动中列出日志文件但不会以任何方式通知发件人，也不会作用于强制实施操作。</span><span class="sxs-lookup"><span data-stu-id="e96fd-384">**Test without Policy Tips**: Actions will be listed in a log file, but senders will not be notified in any way, and enforcement actions will not be acted on.</span></span></li></ul>|
|

<span data-ttu-id="e96fd-385">示例 **custom_data** 符合邮件流规则条件的邮件的示例如下：</span><span class="sxs-lookup"><span data-stu-id="e96fd-385">An example **custom_data** value for a messages that matches the conditions of a mail flow rule looks like this:</span></span>

`S:TRA=ETR|ruleId=19a25eb2-3e43-4896-ad9e-47b6c359779d|st=7/17/2017 12:31:25 AM|action=ApplyHtmlDisclaimer|sev=1|mode=Enforce`
