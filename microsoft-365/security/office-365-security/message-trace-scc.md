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
ms.openlocfilehash: 9c3f7e4bc9624b9fae48074203da525d7a504a12
ms.sourcegitcommit: 06d9e056eabfbac8fafe66cc32907b33d4ae8253
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2021
ms.locfileid: "50741571"
---
# <a name="message-trace-in-the-security--compliance-center"></a><span data-ttu-id="2ae26-103">安全与合规中心内的消息跟踪</span><span class="sxs-lookup"><span data-stu-id="2ae26-103">Message trace in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="2ae26-104">**适用对象**</span><span class="sxs-lookup"><span data-stu-id="2ae26-104">**Applies to**</span></span>
- [<span data-ttu-id="2ae26-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="2ae26-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="2ae26-106">Microsoft Defender for Office 365 计划 1 和计划 2</span><span class="sxs-lookup"><span data-stu-id="2ae26-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="2ae26-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2ae26-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

## <a name="message-trace-features"></a><span data-ttu-id="2ae26-108">邮件跟踪功能</span><span class="sxs-lookup"><span data-stu-id="2ae26-108">Message trace features</span></span>

<span data-ttu-id="2ae26-109">安全与合规中心&跟踪电子邮件在通过 Exchange Online 组织时跟踪。</span><span class="sxs-lookup"><span data-stu-id="2ae26-109">Message trace in the Security & Compliance Center follows email messages as they travel through your Exchange Online organization.</span></span> <span data-ttu-id="2ae26-110">您可以确定服务是否接收、拒绝、延迟或传递了邮件。</span><span class="sxs-lookup"><span data-stu-id="2ae26-110">You can determine if a message was received, rejected, deferred, or delivered by the service.</span></span> <span data-ttu-id="2ae26-111">它还显示在邮件达到最终状态之前对邮件采取的操作。</span><span class="sxs-lookup"><span data-stu-id="2ae26-111">It also shows what actions were taken on the message before it reached its final status.</span></span>

<span data-ttu-id="2ae26-112">安全与合规&中心内的邮件跟踪功能在 (Exchange 管理中心和 EAC) 中提供的原始邮件跟踪功能) 。</span><span class="sxs-lookup"><span data-stu-id="2ae26-112">Message trace in the Security & Compliance Center improves upon the original message trace that was available in the Exchange admin center (EAC).</span></span> <span data-ttu-id="2ae26-113">您可以使用邮件跟踪中的信息有效回答用户有关邮件发生的情况的问题、解决邮件流问题并验证策略更改。</span><span class="sxs-lookup"><span data-stu-id="2ae26-113">You can use the information from message trace to efficiently answer user questions about what happened to messages, troubleshoot mail flow issues, and validate policy changes.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="2ae26-114">若要执行邮件跟踪，您必须是组织管理、合规性管理或技术支持角色组的成员。</span><span class="sxs-lookup"><span data-stu-id="2ae26-114">To do a message trace, you need to be a member of the Organization Management, Compliance Management or Help Desk role groups.</span></span> <span data-ttu-id="2ae26-115">有关详细信息，请参阅[安全与合规中心中的权限](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="2ae26-115">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
>
> - <span data-ttu-id="2ae26-116">结果中显示的邮件的最大数量取决于您选择的报告类型 ("选择报告类型"部分了解详细信息) 。 [](#choose-report-type)</span><span class="sxs-lookup"><span data-stu-id="2ae26-116">The maximum number of messages that are displayed in the results depends on the report type you selected (see the [Choose report type](#choose-report-type) section for details).</span></span> <span data-ttu-id="2ae26-117">Exchange Online PowerShell 或独立 EOP PowerShell 中的 [Get-HistoricalSearch](https://docs.microsoft.com/powershell/module/exchange/get-historicalsearch) cmdlet 在结果中返回所有邮件。</span><span class="sxs-lookup"><span data-stu-id="2ae26-117">The [Get-HistoricalSearch](https://docs.microsoft.com/powershell/module/exchange/get-historicalsearch) cmdlet in Exchange Online PowerShell or standalone EOP PowerShell returns all messages in the results.</span></span>

## <a name="open-message-trace"></a><span data-ttu-id="2ae26-118">打开邮件跟踪</span><span class="sxs-lookup"><span data-stu-id="2ae26-118">Open message trace</span></span>

1. <span data-ttu-id="2ae26-119">在 打开安全&合规中心 <https://protection.office.com> 。</span><span class="sxs-lookup"><span data-stu-id="2ae26-119">Open the Security & Compliance Center at <https://protection.office.com>.</span></span>

2. <span data-ttu-id="2ae26-120">展开 **"邮件流**"，然后选择"**邮件跟踪"。**</span><span class="sxs-lookup"><span data-stu-id="2ae26-120">Expand **Mail flow**, and then select **Message trace**.</span></span>

## <a name="message-trace-page"></a><span data-ttu-id="2ae26-121">邮件跟踪页</span><span class="sxs-lookup"><span data-stu-id="2ae26-121">Message trace page</span></span>

<span data-ttu-id="2ae26-122">从此处，可以通过单击"启动跟踪"按钮来 **启动新的默认** 跟踪。</span><span class="sxs-lookup"><span data-stu-id="2ae26-122">From here you can start a new default trace by clicking on the **Start a trace** button.</span></span> <span data-ttu-id="2ae26-123">这将搜索过去两天内所有发件人和收件人的所有邮件。</span><span class="sxs-lookup"><span data-stu-id="2ae26-123">This will search for all messages for all senders and recipients for the last two days.</span></span> <span data-ttu-id="2ae26-124">或者，您可以使用可用查询类别中的其中一个存储的查询，并像现在一样运行它们，或者将它们用作您自己的查询的起点：</span><span class="sxs-lookup"><span data-stu-id="2ae26-124">Or you can use one of the stored queries from the available query categories and either run them as-is or use them as starting points for your own queries:</span></span>

- <span data-ttu-id="2ae26-125">**默认查询**：Microsoft 365 提供的内置查询。</span><span class="sxs-lookup"><span data-stu-id="2ae26-125">**Default queries**: Built-in queries provided by Microsoft 365.</span></span>

- <span data-ttu-id="2ae26-126">**自定义查询**：由组织中管理员保存供将来使用的查询。</span><span class="sxs-lookup"><span data-stu-id="2ae26-126">**Custom queries**: Queries saved by admins in your organization for future use.</span></span>

- <span data-ttu-id="2ae26-127">**自动保存的查询**：最近运行的十个查询。</span><span class="sxs-lookup"><span data-stu-id="2ae26-127">**Autosaved queries**: The last ten most recently run queries.</span></span> <span data-ttu-id="2ae26-128">此列表使你能够轻松从你离开的地方继续操作。</span><span class="sxs-lookup"><span data-stu-id="2ae26-128">This list makes it simple to pick up where you left off.</span></span>

<span data-ttu-id="2ae26-129">此页面还包括针对已提交请求的可下载报告部分，以及可供下载时的报告本身。</span><span class="sxs-lookup"><span data-stu-id="2ae26-129">Also on this page is a **Downloadable reports** section for the requests you've submitted, as well as the reports themselves when they're are available for download.</span></span>

## <a name="options-for-a-new-message-trace"></a><span data-ttu-id="2ae26-130">新邮件跟踪的选项</span><span class="sxs-lookup"><span data-stu-id="2ae26-130">Options for a new message trace</span></span>

### <a name="filter-by-senders-and-recipients"></a><span data-ttu-id="2ae26-131">按发件人和收件人筛选</span><span class="sxs-lookup"><span data-stu-id="2ae26-131">Filter by senders and recipients</span></span>

<span data-ttu-id="2ae26-132">默认值为" **所有发件人"** 和" **所有** 收件人"，但可以使用以下字段筛选结果：</span><span class="sxs-lookup"><span data-stu-id="2ae26-132">The default values are **All senders** and **All recipients**, but you can use the following fields to filter the results:</span></span>

- <span data-ttu-id="2ae26-133">**通过这些人员**：单击此字段以从组织选择一个或多个发件人。</span><span class="sxs-lookup"><span data-stu-id="2ae26-133">**By these people**: Click in this field to select one or more senders from your organization.</span></span> <span data-ttu-id="2ae26-134">还可以开始键入名称，列表中的项目将按键入的内容进行筛选，与搜索页面的行为方式很类似。</span><span class="sxs-lookup"><span data-stu-id="2ae26-134">You can also start to type a name and the items in the list will be filtered by what you've typed, much like how a search page behaves.</span></span>

- <span data-ttu-id="2ae26-135">**对于这些人员**：单击此字段可选择您的组织中的一个或多个收件人。</span><span class="sxs-lookup"><span data-stu-id="2ae26-135">**To these people**: Click in this field to select one or more recipients in your organization.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="2ae26-136">您还可以键入外部发件人和收件人的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="2ae26-136">You can also type the email addresses of external senders and recipients.</span></span> <span data-ttu-id="2ae26-137">支持通配符 (例如，) ，但不能同时在同一字段中使用多个 `*@contoso.com` 通配符条目。</span><span class="sxs-lookup"><span data-stu-id="2ae26-137">Wildcards are supported (for example, `*@contoso.com`), but you can't use multiple wildcard entries in the same field at the same time.</span></span>
>
> - <span data-ttu-id="2ae26-138">您可以粘贴多个发件人或收件人列表，这些列表用分号 `;` () 。</span><span class="sxs-lookup"><span data-stu-id="2ae26-138">You can paste multiple senders or recipients lists separated by semicolons (`;`).</span></span> <span data-ttu-id="2ae26-139">空格 `\s` () 、回车符 () 或 `\r` 下一 `\n` () 。</span><span class="sxs-lookup"><span data-stu-id="2ae26-139">spaces (`\s`), carriage returns (`\r`), or next lines (`\n`).</span></span>

### <a name="time-range"></a><span data-ttu-id="2ae26-140">时间范围</span><span class="sxs-lookup"><span data-stu-id="2ae26-140">Time range</span></span>

<span data-ttu-id="2ae26-141">默认值为 **2 天**，但可以指定最多 90 天的日期/时间范围。</span><span class="sxs-lookup"><span data-stu-id="2ae26-141">The default value is **2 days**, but you can specify date/time ranges of up to 90 days.</span></span> <span data-ttu-id="2ae26-142">使用日期/时间范围时，请考虑这些问题：</span><span class="sxs-lookup"><span data-stu-id="2ae26-142">When you use date/time ranges, consider these issues:</span></span>

- <span data-ttu-id="2ae26-143">默认情况下，使用时间线在 **Slider** 视图中选择时间范围。</span><span class="sxs-lookup"><span data-stu-id="2ae26-143">By default, you select the time range in **Slider** view using a time line.</span></span> <span data-ttu-id="2ae26-144">只能选择显示的一个或多个时间设置。</span><span class="sxs-lookup"><span data-stu-id="2ae26-144">You can only select the day or time settings that are displayed.</span></span> <span data-ttu-id="2ae26-145">尝试选择一个介于两者之间的值将起始/结束气泡贴靠到最近显示的设置。</span><span class="sxs-lookup"><span data-stu-id="2ae26-145">Trying to select an in-between value will snap the start/end bubble to the nearest displayed setting.</span></span>

  ![安全与合规中心内新邮件跟踪中的滑块&范围](../../media/55a9e9c1-f7d5-4047-b217-824e8b976bcb.png)

  <span data-ttu-id="2ae26-147">但是，您也可以切换到"自定义"视图，可在其中指定开始日期和结束日期值 (包括) ，还可以选择日期/时间范围的时区。 </span><span class="sxs-lookup"><span data-stu-id="2ae26-147">But, you can also switch to **Custom** view where you can specify the **Start date** and **End date** values (including times), and you can also select the **Time zone** for the date/time range.</span></span> <span data-ttu-id="2ae26-148">请注意， **时区** 设置适用于查询输入和查询结果。</span><span class="sxs-lookup"><span data-stu-id="2ae26-148">Note that the **Time zone** setting applies to both your query inputs and your query results.</span></span>

  ![安全与合规中心内新邮件跟踪中的&范围](../../media/ed4c8d50-9ea5-4694-93f9-ee3ab6660b4f.png)

  <span data-ttu-id="2ae26-150">在 10 天或更近的时间，结果可立即作为摘要 **报告** 提供。</span><span class="sxs-lookup"><span data-stu-id="2ae26-150">For 10 days or less, the results are available instantly as a **Summary** report.</span></span> <span data-ttu-id="2ae26-151">如果指定的时间范围甚至超过 10 天，结果将延迟，因为它们仅作为可下载的 CSV 文件 (增强摘要或扩展报告) 。  </span><span class="sxs-lookup"><span data-stu-id="2ae26-151">If you specify a time range that's even slightly greater than 10 days, the results will be delayed as they are only available as a downloadable CSV file ( **Enhanced summary** or **Extended** reports).</span></span>

  <span data-ttu-id="2ae26-152">有关不同报告类型的信息，请参阅本文中的选择报告[](#choose-report-type)类型部分。</span><span class="sxs-lookup"><span data-stu-id="2ae26-152">For more information about the different report types, see the [Choose report type](#choose-report-type) section in this article.</span></span>

  > [!NOTE]
  > <span data-ttu-id="2ae26-153">增强摘要和扩展报告是使用存档的邮件跟踪数据准备的，可能需要几个小时才能下载报告。</span><span class="sxs-lookup"><span data-stu-id="2ae26-153">Enhanced summary and Extended reports are prepared using archived message trace data, and it can take up to several hours before your report is available for download.</span></span> <span data-ttu-id="2ae26-154">根据多少其他管理员还在同一时间提交了报告请求，您可能还注意到在处理队列请求之前有延迟。</span><span class="sxs-lookup"><span data-stu-id="2ae26-154">Depending on how many other admins have also submitted report requests around the same time, you might also notice a delay before processing starts for your queued request.</span></span>

- <span data-ttu-id="2ae26-155">在 Slider 视图中 **保存** 查询可保存相对 (例如，从今天开始 3) 。</span><span class="sxs-lookup"><span data-stu-id="2ae26-155">Saving a query in **Slider** view saves the relative time range (for example, 3 days from today).</span></span> <span data-ttu-id="2ae26-156">在 **自定义视图中保存** 查询可保存绝对日期/时间范围 (例如，2018-05-06 13：00 至 2018-05-08 18：00) 。</span><span class="sxs-lookup"><span data-stu-id="2ae26-156">Saving a query in **Custom** view saves the absolute date/time range (for example, 2018-05-06 13:00 to 2018-05-08 18:00).</span></span>

### <a name="more-search-options"></a><span data-ttu-id="2ae26-157">更多搜索选项</span><span class="sxs-lookup"><span data-stu-id="2ae26-157">More search options</span></span>

#### <a name="delivery-status"></a><span data-ttu-id="2ae26-158">传递状态</span><span class="sxs-lookup"><span data-stu-id="2ae26-158">Delivery status</span></span>

<span data-ttu-id="2ae26-159">您可以将默认值 **"全部"** 保留为选中状态，也可以选择下列值之一来筛选结果：</span><span class="sxs-lookup"><span data-stu-id="2ae26-159">You can leave the default value **All** selected, or you can select one of the following values to filter the results:</span></span>

- <span data-ttu-id="2ae26-160">**已** 传递：邮件已成功传递到预期目标。</span><span class="sxs-lookup"><span data-stu-id="2ae26-160">**Delivered**: The message was successfully delivered to the intended destination.</span></span>

- <span data-ttu-id="2ae26-161">**挂起**：正在尝试或重新尝试传递邮件。</span><span class="sxs-lookup"><span data-stu-id="2ae26-161">**Pending**: Delivery of the message is being attempted or re-attempted.</span></span>

- <span data-ttu-id="2ae26-162">**展开**：在将通讯组收件人发送给该组的单个成员之前展开。</span><span class="sxs-lookup"><span data-stu-id="2ae26-162">**Expanded**: A distribution group recipient was expanded before delivery to the individual members of the group.</span></span>

- <span data-ttu-id="2ae26-163">**失败**：邮件未送达。</span><span class="sxs-lookup"><span data-stu-id="2ae26-163">**Failed**: The message was not delivered.</span></span>

- <span data-ttu-id="2ae26-164">**已隔离**：邮件被隔离 (垃圾邮件、批量邮件或网络钓鱼邮件) 。</span><span class="sxs-lookup"><span data-stu-id="2ae26-164">**Quarantined**: The message was quarantined (as spam, bulk mail, or phishing).</span></span> <span data-ttu-id="2ae26-165">有关详细信息，请参阅 [EOP 中的隔离电子邮件](quarantine-email-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="2ae26-165">For more information, see [Quarantined email messages in EOP](quarantine-email-messages.md).</span></span>

- <span data-ttu-id="2ae26-166">**筛选为垃圾邮件**：邮件被标识为垃圾邮件，并且被拒绝或阻止 (未隔离) 。</span><span class="sxs-lookup"><span data-stu-id="2ae26-166">**Filtered as spam**: The message was identified spam, and was rejected or blocked (not quarantined).</span></span>

- <span data-ttu-id="2ae26-167">**获取状态：** 此邮件最近由 Microsoft 365 接收，但尚没有其他状态数据可用。</span><span class="sxs-lookup"><span data-stu-id="2ae26-167">**Getting status:** The message was recently received by Microsoft 365, but no other status data is yet available.</span></span> <span data-ttu-id="2ae26-168">请几分钟后重新检查。</span><span class="sxs-lookup"><span data-stu-id="2ae26-168">Check back in a few minutes.</span></span>

> [!NOTE]
> <span data-ttu-id="2ae26-169">值 **Pending、Quarantined** 和 **Filter as spam** 仅适用于少于 10 天的搜索。</span><span class="sxs-lookup"><span data-stu-id="2ae26-169">The values **Pending,** **Quarantined**, and **Filter as spam** are only available for searches less than 10 days.</span></span> <span data-ttu-id="2ae26-170">此外，实际和报告的传递状态之间可能有 5 到 10 分钟的延迟。</span><span class="sxs-lookup"><span data-stu-id="2ae26-170">Also, there might be a 5 to 10 minute delay between the actual and reported delivery status.</span></span>

#### <a name="message-id"></a><span data-ttu-id="2ae26-171">邮件 ID</span><span class="sxs-lookup"><span data-stu-id="2ae26-171">Message ID</span></span>

<span data-ttu-id="2ae26-172">This is the internet message ID (also known as the Client ID) that's found in the **Message-ID：** header field in the message header.</span><span class="sxs-lookup"><span data-stu-id="2ae26-172">This is the internet message ID (also known as the Client ID) that's found in the **Message-ID:** header field in the message header.</span></span> <span data-ttu-id="2ae26-173">用户可以为您提供此值以调查特定邮件。</span><span class="sxs-lookup"><span data-stu-id="2ae26-173">Users can give you this value to investigate specific messages.</span></span>

<span data-ttu-id="2ae26-174">该值在邮件生存期内是常量。</span><span class="sxs-lookup"><span data-stu-id="2ae26-174">This value is constant for the lifetime of the message.</span></span> <span data-ttu-id="2ae26-175">对于在 Microsoft 365 或 Exchange 中创建的邮件，该值的格式为 ，包括尖括号 `<GUID@ServerFQDN>` \< \> () 。</span><span class="sxs-lookup"><span data-stu-id="2ae26-175">For messages created in Microsoft 365 or Exchange, the value is in the format `<GUID@ServerFQDN>`, including the angle brackets (\< \>).</span></span> <span data-ttu-id="2ae26-176">例如，`<d9683b4c-127b-413a-ae2e-fa7dfb32c69d@DM3NAM06BG401.Eop-nam06.prod.protection.outlook.com>`。</span><span class="sxs-lookup"><span data-stu-id="2ae26-176">For example, `<d9683b4c-127b-413a-ae2e-fa7dfb32c69d@DM3NAM06BG401.Eop-nam06.prod.protection.outlook.com>`.</span></span> <span data-ttu-id="2ae26-177">其他邮件系统可能使用不同的语法或值。</span><span class="sxs-lookup"><span data-stu-id="2ae26-177">Other messaging systems might use different syntax or values.</span></span> <span data-ttu-id="2ae26-178">此值应该是唯一的，但并非所有电子邮件系统都严格遵循此要求。</span><span class="sxs-lookup"><span data-stu-id="2ae26-178">This value is supposed to be unique, but not all email systems strictly follow this requirement.</span></span> <span data-ttu-id="2ae26-179">如果 **Message-ID：** 头字段不存在或对于来自外部源的传入邮件为空，则分配一个任意值。</span><span class="sxs-lookup"><span data-stu-id="2ae26-179">If the **Message-ID:** header field doesn't exist or is blank for incoming messages from external sources, an arbitrary value is assigned.</span></span>

<span data-ttu-id="2ae26-180">使用消息 **ID** 筛选结果时，请确保包含完整字符串，包括任何尖括号。</span><span class="sxs-lookup"><span data-stu-id="2ae26-180">When you use **Message ID** to filter the results, be sure to include the full string, including any angle brackets.</span></span>

#### <a name="direction"></a><span data-ttu-id="2ae26-181">Direction</span><span class="sxs-lookup"><span data-stu-id="2ae26-181">Direction</span></span>

<span data-ttu-id="2ae26-182">可以将默认值"全部"保留为选中状态，也可以选择"发送到组织中收件人的入站 **(** 邮件") 或"从组织用户发送的出站 **(** 邮件") 以筛选结果。</span><span class="sxs-lookup"><span data-stu-id="2ae26-182">You can leave the default value **All** selected, or you can select **Inbound** (messages sent to recipients in your organization) or **Outbound** (messages sent from users in your organization) to filter the results.</span></span>

#### <a name="original-client-ip-address"></a><span data-ttu-id="2ae26-183">原始客户端 IP 地址</span><span class="sxs-lookup"><span data-stu-id="2ae26-183">Original client IP address</span></span>

<span data-ttu-id="2ae26-184">你可以按客户端 IP 地址提交结果，以调查发送大量垃圾邮件或恶意软件的黑客计算机。</span><span class="sxs-lookup"><span data-stu-id="2ae26-184">You can filer the results by client IP address to investigate hacked computers that are sending large amounts of spam or malware.</span></span> <span data-ttu-id="2ae26-185">虽然邮件可能看起来来自多个发件人，但同一台计算机很可能生成所有邮件。</span><span class="sxs-lookup"><span data-stu-id="2ae26-185">Although the messages might appear to come from multiple senders, it's likely that the same computer is generating all of the messages.</span></span>

> [!NOTE]
> <span data-ttu-id="2ae26-186">客户端 IP 地址信息仅在 10 天内可用，并且仅在增强摘要或扩展报告中可用， (可下载的 CSV) 。 </span><span class="sxs-lookup"><span data-stu-id="2ae26-186">The client IP address information is only available for 10 days, and is only available in the **Enhanced summary** or **Extended** reports (downloadable CSV files).</span></span>

### <a name="choose-report-type"></a><span data-ttu-id="2ae26-187">选择报告类型</span><span class="sxs-lookup"><span data-stu-id="2ae26-187">Choose report type</span></span>

<span data-ttu-id="2ae26-188">可用的报告类型包括：</span><span class="sxs-lookup"><span data-stu-id="2ae26-188">The available report types are:</span></span>

- <span data-ttu-id="2ae26-189">**摘要：** 如果时间范围小于 10 天且不需要其他筛选选项，则可用。</span><span class="sxs-lookup"><span data-stu-id="2ae26-189">**Summary**: Available if the time range is less than 10 days, and requires no additional filtering options.</span></span> <span data-ttu-id="2ae26-190">在单击"搜索"后，结果几乎会立即 **提供**。</span><span class="sxs-lookup"><span data-stu-id="2ae26-190">The results are available almost immediately after you click **Search**.</span></span> <span data-ttu-id="2ae26-191">报告最多返回 20000 个结果。</span><span class="sxs-lookup"><span data-stu-id="2ae26-191">The report returns up to 20000 results.</span></span>

- <span data-ttu-id="2ae26-192">**增强\*\*\*\*摘要或扩展**：这些报告仅作为可下载的 CSV 文件提供，并且需要以下一个或多个筛选选项，而不考虑时间范围：按这些人员、收件人或邮件 **ID。**</span><span class="sxs-lookup"><span data-stu-id="2ae26-192">**Enhanced summary** or **Extended**: These reports are only available as downloadable CSV files, and require one or more of the following filtering options regardless of the time range: **By these people**, **To these people**, or **Message ID**.</span></span> <span data-ttu-id="2ae26-193">您可以对发件人或收件人使用通配符 (例如 \* @contoso.com) 。</span><span class="sxs-lookup"><span data-stu-id="2ae26-193">You can use wildcards for the senders or the recipients (for example, \*@contoso.com).</span></span> <span data-ttu-id="2ae26-194">增强摘要报告最多返回 50000 个结果。</span><span class="sxs-lookup"><span data-stu-id="2ae26-194">The Enhanced summary report returns up to 50000 results.</span></span> <span data-ttu-id="2ae26-195">扩展报告最多返回 1000 个结果。</span><span class="sxs-lookup"><span data-stu-id="2ae26-195">The Extended report returns up to 1000 results.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="2ae26-196">增强摘要和扩展报告是使用存档的邮件跟踪数据准备的，可能需要几个小时才能下载报告。</span><span class="sxs-lookup"><span data-stu-id="2ae26-196">Enhanced summary and Extended reports are prepared using archived message trace data, and it can take up to several hours before your report is available to download.</span></span> <span data-ttu-id="2ae26-197">根据多少其他管理员还在同一时间提交了报告请求，你还可能会注意到排队请求开始处理之前有延迟。</span><span class="sxs-lookup"><span data-stu-id="2ae26-197">Depending on how many other admins have also submitted report requests around the same time, you might also notice a delay before your queued request starts to be processed.</span></span>
>
> - <span data-ttu-id="2ae26-198">尽管您可以为任意日期/时间范围选择"增强摘要"或"扩展报告"，但通常，这两种类型的报告通常不会提供过去四小时的存档数据。</span><span class="sxs-lookup"><span data-stu-id="2ae26-198">While you can select an Enhanced summary or Extended report for any date/time range, commonly the last four hours of archived data will not yet be available for these two types of reports.</span></span>
>
> - <span data-ttu-id="2ae26-199">可下载报告的最大大小为 500 MB。</span><span class="sxs-lookup"><span data-stu-id="2ae26-199">The maximum size for a downloadable report is 500 MB.</span></span> <span data-ttu-id="2ae26-200">如果可下载的报告超过 500 MB，则不能打开 Excel 或记事本中的报表。</span><span class="sxs-lookup"><span data-stu-id="2ae26-200">If a downloadable report exceeds 500 MB, you can't open the report in Excel or Notepad.</span></span>

<span data-ttu-id="2ae26-201">单击"下一步"时，将显示一个摘要页，其中列出了所选的筛选选项、报告的唯一 (可编辑) 标题，以及邮件跟踪完成 (且可编辑且必须在你的组织的接受域) 之一中时收到通知的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="2ae26-201">When you click **Next**, you're presented with a summary page that lists the filtering options that you selected, a unique (editable) title for the report, and the email address that receives the notification when the message trace completes (also editable, and must be in one of your organization's accepted domains).</span></span> <span data-ttu-id="2ae26-202">单击 **"准备报告** "提交邮件跟踪。</span><span class="sxs-lookup"><span data-stu-id="2ae26-202">Click **Prepare report** to submit the message trace.</span></span> <span data-ttu-id="2ae26-203">在主 **"邮件跟踪"** 页上，您可以在"可下载的报告"部分查看 **报告** 的状态。</span><span class="sxs-lookup"><span data-stu-id="2ae26-203">On the main **Message trace** page, you can see the status of the report in the **Downloadable reports** section.</span></span>

<span data-ttu-id="2ae26-204">有关不同报告类型中返回的信息详细信息，请参阅下一节。</span><span class="sxs-lookup"><span data-stu-id="2ae26-204">For more information about the information that's returned in the different report types, see the next section.</span></span>

## <a name="message-trace-results"></a><span data-ttu-id="2ae26-205">邮件跟踪结果</span><span class="sxs-lookup"><span data-stu-id="2ae26-205">Message trace results</span></span>

<span data-ttu-id="2ae26-206">不同的报告类型返回不同级别的信息。</span><span class="sxs-lookup"><span data-stu-id="2ae26-206">The different report types return different levels of information.</span></span> <span data-ttu-id="2ae26-207">以下各节介绍了不同报告中的信息。</span><span class="sxs-lookup"><span data-stu-id="2ae26-207">The information that's available in the different reports is described in the following sections.</span></span>

### <a name="summary-report-output"></a><span data-ttu-id="2ae26-208">摘要报告输出</span><span class="sxs-lookup"><span data-stu-id="2ae26-208">Summary report output</span></span>

<span data-ttu-id="2ae26-209">运行邮件跟踪后，将列出结果，并按最近的第一次 (日期/时间) 。</span><span class="sxs-lookup"><span data-stu-id="2ae26-209">After running the message trace, the results will be listed, sorted by descending date/time (most recent first).</span></span>

![安全与合规中心内邮件跟踪&摘要报告结果](../../media/0664bafe-0b03-477b-b571-0b046ac8c977.png)

<span data-ttu-id="2ae26-211">摘要报告包含以下信息：</span><span class="sxs-lookup"><span data-stu-id="2ae26-211">The summary report contains the following information:</span></span>

- <span data-ttu-id="2ae26-212">**日期**：服务使用配置的 UTC 时区接收邮件的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="2ae26-212">**Date**: The date and time at which the message was received by the service, using the configured UTC time zone.</span></span>

- <span data-ttu-id="2ae26-213">**发件人**：别名域的发件人 ( @ *电子邮件地址) 。*</span><span class="sxs-lookup"><span data-stu-id="2ae26-213">**Sender**: The email address of the sender (*alias*@*domain*).</span></span>

- <span data-ttu-id="2ae26-214">**收件人**：收件人的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="2ae26-214">**Recipient**: The email address of the recipient or recipients.</span></span> <span data-ttu-id="2ae26-215">对于发送给多个收件人的邮件，每个收件人有一行。</span><span class="sxs-lookup"><span data-stu-id="2ae26-215">For a message sent to multiple recipients, there's one line per recipient.</span></span> <span data-ttu-id="2ae26-216">如果收件人是通讯组、动态通讯组或启用邮件的安全组，则该组将是第一个收件人，然后该组的每个成员位于单独的行上。</span><span class="sxs-lookup"><span data-stu-id="2ae26-216">If the recipient is a distribution group, dynamic distribution group, or mail-enabled security group, the group will be the first recipient, and then each member of the group is on a separate line.</span></span>

- <span data-ttu-id="2ae26-217">**主题**：邮件的 **Subject：** 字段的前 256 个字符。</span><span class="sxs-lookup"><span data-stu-id="2ae26-217">**Subject**: The first 256 characters of the message's **Subject:** field.</span></span>

- <span data-ttu-id="2ae26-218">**状态**：这些值在"传递状态 ["部分](#delivery-status) 进行介绍。</span><span class="sxs-lookup"><span data-stu-id="2ae26-218">**Status**: These values are described in the [Delivery status](#delivery-status) section.</span></span>

<span data-ttu-id="2ae26-219">默认情况下，前 250 个结果已加载且随时可用。</span><span class="sxs-lookup"><span data-stu-id="2ae26-219">By default, the first 250 results are loaded and readily available.</span></span> <span data-ttu-id="2ae26-220">向下滚动时，加载下一批结果时，会稍微暂停。</span><span class="sxs-lookup"><span data-stu-id="2ae26-220">When you scroll down, there's a slight pause as the next batch of results are loaded.</span></span> <span data-ttu-id="2ae26-221">你可以单击"全部加载"以加载最多 10，000 个结果，而不是滚动。</span><span class="sxs-lookup"><span data-stu-id="2ae26-221">Instead of scrolling, you can click **Load all** to load all of the results up to a maximum of 10,000.</span></span>

<span data-ttu-id="2ae26-222">您可以单击列标题以按该列中的值以升序或降序对结果进行排序。</span><span class="sxs-lookup"><span data-stu-id="2ae26-222">You can click on the column headers to sort the results by the values in that column in ascending or descending order.</span></span>

<span data-ttu-id="2ae26-223">可以单击 **"筛选结果** "按一列或多列筛选结果。</span><span class="sxs-lookup"><span data-stu-id="2ae26-223">You can click **Filter results** to filter the results by one or more columns.</span></span>

<span data-ttu-id="2ae26-224">You can export the results after you've selected one or more rows by clicking **Export results** and then selecting Export **all results**， Export loaded **results**， or **Export selected**.</span><span class="sxs-lookup"><span data-stu-id="2ae26-224">You can export the results after you've selected one or more rows by clicking **Export results** and then selecting **Export all results**, **Export loaded results**, or **Export selected**.</span></span>

#### <a name="find-related-records-for-this-message"></a><span data-ttu-id="2ae26-225">查找此邮件的相关记录</span><span class="sxs-lookup"><span data-stu-id="2ae26-225">Find related records for this message</span></span>

<span data-ttu-id="2ae26-226">相关邮件记录是共享相同邮件 ID 的记录。</span><span class="sxs-lookup"><span data-stu-id="2ae26-226">Related message records are records that shared the same Message ID.</span></span> <span data-ttu-id="2ae26-227">请记住，即使在两个人之间发送的单个邮件也可以生成多个记录。</span><span class="sxs-lookup"><span data-stu-id="2ae26-227">Remember, even a single message sent between two people can generate multiple records.</span></span> <span data-ttu-id="2ae26-228">当邮件受通讯组扩展、转发、邮件流规则（也称为传输规则 (传输规则等影响）时，记录) 增加。</span><span class="sxs-lookup"><span data-stu-id="2ae26-228">The number of records increases when the message is affected by distribution group expansion, forwarding, mail flow rules (also known as transport rules), etc.</span></span>

<span data-ttu-id="2ae26-229">选中行的复选框后，可以通过单击出现的"查找相关"按钮或选择"更多选项""查找此邮件的相关记录"来查找 ![ ](../../media/1ea52bbf-9d00-48ce-9362-307f7f6fb7fe.png) \> ) 。</span><span class="sxs-lookup"><span data-stu-id="2ae26-229">After you select a row's check box, you can find related records for the message by clicking the **Find related** button that appears, or by selecting **More options** ![More](../../media/1ea52bbf-9d00-48ce-9362-307f7f6fb7fe.png) \> **Find related records for this message**).</span></span>

<span data-ttu-id="2ae26-230">有关邮件 ID 详细信息，请参阅本文前面部分的消息 ID 部分。</span><span class="sxs-lookup"><span data-stu-id="2ae26-230">For more information about the Message ID, see the Message ID section earlier in this article.</span></span>

#### <a name="message-trace-details"></a><span data-ttu-id="2ae26-231">邮件跟踪详细信息</span><span class="sxs-lookup"><span data-stu-id="2ae26-231">Message trace details</span></span>

<span data-ttu-id="2ae26-232">在摘要报告输出中，可以使用以下任一方法查看有关邮件的详细信息：</span><span class="sxs-lookup"><span data-stu-id="2ae26-232">In the summary report output, you can view details about a message by using either of the following methods:</span></span>

- <span data-ttu-id="2ae26-233">Select the row (click anywhere in the row except the check box) .</span><span class="sxs-lookup"><span data-stu-id="2ae26-233">Select the row (click anywhere in the row except the check box).</span></span>

- <span data-ttu-id="2ae26-234">选中该行的复选框，然后单击"更多 **选项** ![ "" ](../../media/1ea52bbf-9d00-48ce-9362-307f7f6fb7fe.png) \> **查看邮件详细信息"。**</span><span class="sxs-lookup"><span data-stu-id="2ae26-234">Select the row's check box and click **More options** ![More](../../media/1ea52bbf-9d00-48ce-9362-307f7f6fb7fe.png) \> **View message details**.</span></span>

   ![在安全与合规中心内双击摘要报告邮件跟踪结果中的&的详细信息](../../media/e50ee7cd-810a-4c06-8b58-e56ffd7028d1.png)

<span data-ttu-id="2ae26-236">邮件跟踪详细信息包含摘要报告中未包含的以下附加信息：</span><span class="sxs-lookup"><span data-stu-id="2ae26-236">The message trace details contain the following additional information that's not present in the summary report:</span></span>

- <span data-ttu-id="2ae26-237">**邮件事件**：此部分包含分类，可帮助对服务对邮件采取的操作进行分类。</span><span class="sxs-lookup"><span data-stu-id="2ae26-237">**Message events**: This section contains classifications that help categorize the actions that the service takes on messages.</span></span> <span data-ttu-id="2ae26-238">**您可能遇到的一些** 更有趣的事件是：</span><span class="sxs-lookup"><span data-stu-id="2ae26-238">**Some of the more interesting events** that you might encounter are:</span></span>

  - <span data-ttu-id="2ae26-239">**接收**：邮件已由服务接收。</span><span class="sxs-lookup"><span data-stu-id="2ae26-239">**Receive**: The message was received by the service.</span></span>

  - <span data-ttu-id="2ae26-240">**发送**：邮件由服务发送。</span><span class="sxs-lookup"><span data-stu-id="2ae26-240">**Send**: The message was sent by the service.</span></span>

  - <span data-ttu-id="2ae26-241">**失败**：邮件无法传递。</span><span class="sxs-lookup"><span data-stu-id="2ae26-241">**Fail**: The message failed to be delivered.</span></span>

  - <span data-ttu-id="2ae26-242">**传递**：邮件已传递到邮箱。</span><span class="sxs-lookup"><span data-stu-id="2ae26-242">**Deliver**: The message was delivered to a mailbox.</span></span>

  - <span data-ttu-id="2ae26-243">**展开**：邮件已发送到已展开的通讯组。</span><span class="sxs-lookup"><span data-stu-id="2ae26-243">**Expand**: The message was sent to a distribution group that was expanded.</span></span>

  - <span data-ttu-id="2ae26-244">**传输**：由于内容转换、邮件收件人限制或代理原因，收件人已移动到已进行收件人转换的邮件。</span><span class="sxs-lookup"><span data-stu-id="2ae26-244">**Transfer**: Recipients were moved to a bifurcated message because of content conversion, message recipient limits, or agents.</span></span>

  - <span data-ttu-id="2ae26-245">**延迟**：邮件传递延迟，稍后可能会重新尝试。</span><span class="sxs-lookup"><span data-stu-id="2ae26-245">**Defer**: The message delivery was postponed and might be re-attempted later.</span></span>

  - <span data-ttu-id="2ae26-246">**已** 解决：邮件已基于 Active Directory 查找重定向到新的收件人地址。</span><span class="sxs-lookup"><span data-stu-id="2ae26-246">**Resolved**: The message was redirected to a new recipient address based on an Active Directory look up.</span></span> <span data-ttu-id="2ae26-247">当发生这种情况时，原始收件人地址会被列在邮件跟踪中的单独一行，包括邮件的最终传递状态。</span><span class="sxs-lookup"><span data-stu-id="2ae26-247">When this happens, the original recipient address is listed in a separate row in the message trace along with the final delivery status for the message.</span></span>

  > [!NOTE]
  > 
  > - <span data-ttu-id="2ae26-248">成功传递的无事件邮件将在邮件 **跟踪** 中生成多个事件条目。</span><span class="sxs-lookup"><span data-stu-id="2ae26-248">An uneventful message that's successfully delivered will generate multiple **Event** entries in the message trace.</span></span>
  > 
  > - <span data-ttu-id="2ae26-249">此列表并不详尽。</span><span class="sxs-lookup"><span data-stu-id="2ae26-249">This list is not meant to be exhaustive.</span></span> <span data-ttu-id="2ae26-250">有关更多事件的说明，请参阅 [邮件跟踪日志中的事件类型](https://docs.microsoft.com/Exchange/mail-flow/transport-logs/message-tracking#event-types-in-the-message-tracking-log)。</span><span class="sxs-lookup"><span data-stu-id="2ae26-250">For descriptions of more events, see [Event types in the message tracking log](https://docs.microsoft.com/Exchange/mail-flow/transport-logs/message-tracking#event-types-in-the-message-tracking-log).</span></span> <span data-ttu-id="2ae26-251">请注意，此链接是Exchange Server (Exchange) 主题。</span><span class="sxs-lookup"><span data-stu-id="2ae26-251">Note that this link is an Exchange Server (on-premises Exchange) topic.</span></span>

- <span data-ttu-id="2ae26-252">**详细信息 ：** 此部分包含以下详细信息：</span><span class="sxs-lookup"><span data-stu-id="2ae26-252">**More information**: This section contains the following details:</span></span>

  - <span data-ttu-id="2ae26-253">**邮件 ID：** 此值在本文前面的消息 [ID](#message-id) 部分中介绍。</span><span class="sxs-lookup"><span data-stu-id="2ae26-253">**Message ID**: This value is described in the [Message ID](#message-id) section earlier in this article.</span></span> <span data-ttu-id="2ae26-254">例如，`<d9683b4c-127b-413a-ae2e-fa7dfb32c69d@DM3NAM06BG401.Eop-nam06.prod.protection.outlook.com>`。</span><span class="sxs-lookup"><span data-stu-id="2ae26-254">For example, `<d9683b4c-127b-413a-ae2e-fa7dfb32c69d@DM3NAM06BG401.Eop-nam06.prod.protection.outlook.com>`.</span></span>

  - <span data-ttu-id="2ae26-255">**邮件大小**</span><span class="sxs-lookup"><span data-stu-id="2ae26-255">**Message size**</span></span>

  - <span data-ttu-id="2ae26-256">**来自 IP：** 发送邮件的计算机的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="2ae26-256">**From IP**: The IP address of the computer that sent the message.</span></span> <span data-ttu-id="2ae26-257">对于从 Exchange Online 发送的出站邮件，该值是空值。</span><span class="sxs-lookup"><span data-stu-id="2ae26-257">For outbound messages sent from Exchange Online, this value is blank.</span></span>

  - <span data-ttu-id="2ae26-258">**To IP**：服务尝试传递邮件的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="2ae26-258">**To IP**: The IP address or addresses where the service attempted to deliver the message.</span></span> <span data-ttu-id="2ae26-259">如果邮件有多个收件人，则显示这些收件人。</span><span class="sxs-lookup"><span data-stu-id="2ae26-259">If the message has multiple recipients, these are displayed.</span></span> <span data-ttu-id="2ae26-260">对于发送到 Exchange Online 的入站邮件，该值是空值。</span><span class="sxs-lookup"><span data-stu-id="2ae26-260">For inbound messages sent to Exchange Online, this value is blank.</span></span>

### <a name="enhanced-summary-reports"></a><span data-ttu-id="2ae26-261">增强摘要报告</span><span class="sxs-lookup"><span data-stu-id="2ae26-261">Enhanced summary reports</span></span>

<span data-ttu-id="2ae26-262">可在 (跟踪) **可下载** 报告"部分查看已完成的增强摘要报告。</span><span class="sxs-lookup"><span data-stu-id="2ae26-262">Available (completed) Enhanced summary reports are available in the **Downloadable reports** section at the beginning message trace.</span></span> <span data-ttu-id="2ae26-263">报告中提供了以下信息：</span><span class="sxs-lookup"><span data-stu-id="2ae26-263">The following information is available in the report:</span></span>

- <span data-ttu-id="2ae26-264">**origin_timestamp：** 服务最初使用配置的 UTC 时区接收邮件 <sup>\*</sup> 的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="2ae26-264">**origin_timestamp**<sup>\*</sup>: The date and time when the message was initially received by the service, using the configured UTC time zone.</span></span>

- <span data-ttu-id="2ae26-265">**sender_address：** 发件人的电子邮件地址 (*域名* @ *) 。*</span><span class="sxs-lookup"><span data-stu-id="2ae26-265">**sender_address**: The sender's email address (*alias*@*domain*).</span></span>

- <span data-ttu-id="2ae26-266">**Recipient_status：** 邮件送达收件人的状态。</span><span class="sxs-lookup"><span data-stu-id="2ae26-266">**Recipient_status**: The status of the delivery of the message to the recipient.</span></span> <span data-ttu-id="2ae26-267">如果邮件已发送给多个收件人，它将以以下格式显示所有收件人和每个收件人的相应状态 \<*email address*\> ## \<*status*\> ： 。</span><span class="sxs-lookup"><span data-stu-id="2ae26-267">If the message was sent to multiple recipients, it will show all the recipients and the corresponding status for each, in the format: \<*email address*\>##\<*status*\>.</span></span> <span data-ttu-id="2ae26-268">例如：</span><span class="sxs-lookup"><span data-stu-id="2ae26-268">For example:</span></span>

  - <span data-ttu-id="2ae26-269">**##Receive，"** 发送"表示服务已接收邮件并发送到预期目标。</span><span class="sxs-lookup"><span data-stu-id="2ae26-269">**##Receive, Send** means the message was received by the service and was sent to the intended destination.</span></span>

  - <span data-ttu-id="2ae26-270">**##Receive，Fail** 表示服务已接收邮件，但发送到预期目标失败。</span><span class="sxs-lookup"><span data-stu-id="2ae26-270">**##Receive, Fail** means the message was received by the service but delivery to the intended destination failed.</span></span>

  - <span data-ttu-id="2ae26-271">**##Receive，"** 传递"表示服务已接收邮件，并且已传递到收件人的邮箱。</span><span class="sxs-lookup"><span data-stu-id="2ae26-271">**##Receive, Deliver** means the message was received by the service and was delivered to the recipient's mailbox.</span></span>

- <span data-ttu-id="2ae26-272">**message_subject**：邮件的 Subject 字段的前 256 **个字符。**</span><span class="sxs-lookup"><span data-stu-id="2ae26-272">**message_subject**: The first 256 characters of the message's **Subject** field.</span></span>

- <span data-ttu-id="2ae26-273">**total_bytes：** 邮件的大小（以字节为单位，包括附件）。</span><span class="sxs-lookup"><span data-stu-id="2ae26-273">**total_bytes**: The size of the message in bytes, including attachments.</span></span>

- <span data-ttu-id="2ae26-274">**message_id：** 此值在本文前面的消息 [ID](#message-id) 部分中介绍。</span><span class="sxs-lookup"><span data-stu-id="2ae26-274">**message_id**: This value is described in the [Message ID](#message-id) section earlier in this article.</span></span> <span data-ttu-id="2ae26-275">例如，`<d9683b4c-127b-413a-ae2e-fa7dfb32c69d@DM3NAM06BG401.Eop-nam06.prod.protection.outlook.com>`。</span><span class="sxs-lookup"><span data-stu-id="2ae26-275">For example, `<d9683b4c-127b-413a-ae2e-fa7dfb32c69d@DM3NAM06BG401.Eop-nam06.prod.protection.outlook.com>`.</span></span>

- <span data-ttu-id="2ae26-276">**network_message_id：** 唯一的邮件 ID 值，因混淆或通讯组扩展而创建的邮件的所有副本中均保留。</span><span class="sxs-lookup"><span data-stu-id="2ae26-276">**network_message_id**: A unique message ID value that persists across all copies of the message that might be created due to bifurcation or distribution group expansion.</span></span> <span data-ttu-id="2ae26-277">示例值为 `1341ac7b13fb42ab4d4408cf7f55890f` 。</span><span class="sxs-lookup"><span data-stu-id="2ae26-277">An example value is `1341ac7b13fb42ab4d4408cf7f55890f`.</span></span>

- <span data-ttu-id="2ae26-278">**original_client_ip**：发件人客户端的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="2ae26-278">**original_client_ip**: The IP address of the sender's client.</span></span>

- <span data-ttu-id="2ae26-279">**方向** 性：指示邮件是 (1) 发送到组织的入站邮件，还是从组织 (2) 出站邮件。</span><span class="sxs-lookup"><span data-stu-id="2ae26-279">**directionality**: Indicates whether the message was sent inbound (1) to your organization, or whether it was sent outbound (2) from your organization.</span></span>

- <span data-ttu-id="2ae26-280">**connector_id**：源连接器或目标连接器的名称。</span><span class="sxs-lookup"><span data-stu-id="2ae26-280">**connector_id**: The name of the source or destination connector.</span></span> <span data-ttu-id="2ae26-281">有关 Exchange Online 中的连接器详细信息，请参阅 [在 Office 365](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)中配置使用连接器的邮件流。</span><span class="sxs-lookup"><span data-stu-id="2ae26-281">For more information about connectors in Exchange Online, see [Configure mail flow using connectors in Office 365](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow).</span></span>

- <span data-ttu-id="2ae26-282">**delivery_priority：** <sup>*</sup> 邮件是使用高、\*\*低还是*\* 普通优先级 **发送**。</span><span class="sxs-lookup"><span data-stu-id="2ae26-282">**delivery_priority**<sup>\*</sup>: Whether the message was sent with **High**, **Low**, or **Normal** priority.</span></span>

<span data-ttu-id="2ae26-283"><sup>\*</sup> 这些属性仅在增强摘要报告中可用。</span><span class="sxs-lookup"><span data-stu-id="2ae26-283"><sup>\*</sup> These properties are only available in Enhanced summary reports.</span></span>

### <a name="extended-reports"></a><span data-ttu-id="2ae26-284">扩展报告</span><span class="sxs-lookup"><span data-stu-id="2ae26-284">Extended reports</span></span>

<span data-ttu-id="2ae26-285">Available (completed) Extended reports are available in the **Downloadable reports** section at the beginning of message trace.</span><span class="sxs-lookup"><span data-stu-id="2ae26-285">Available (completed) Extended reports are available in the **Downloadable reports** section at the beginning of message trace.</span></span> <span data-ttu-id="2ae26-286">实际上，"增强摘要"报告中的所有信息都可用于扩展 (，origin_timestamp和 **delivery_priority) 。** </span><span class="sxs-lookup"><span data-stu-id="2ae26-286">Virtually all of the information from an Enhanced summary report is available in an Extended report (with the exception of **origin_timestamp** and **delivery_priority**).</span></span> <span data-ttu-id="2ae26-287">以下附加信息仅在扩展报告中可用：</span><span class="sxs-lookup"><span data-stu-id="2ae26-287">The following additional information is only available in an Extended report:</span></span>

- <span data-ttu-id="2ae26-288">**client_ip**：提交邮件的电子邮件服务器或邮件客户端的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="2ae26-288">**client_ip**: The IP address of the email server or messaging client that submitted the message.</span></span>

- <span data-ttu-id="2ae26-289">**client_hostname**：提交邮件的电子邮件服务器或邮件客户端的主机名或 FQDN。</span><span class="sxs-lookup"><span data-stu-id="2ae26-289">**client_hostname**: The host name or FQDN of the email server or messaging client that submitted the message.</span></span>

- <span data-ttu-id="2ae26-290">**server_ip**：源服务器或目标服务器的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="2ae26-290">**server_ip**: The IP address of the source or destination server.</span></span>

- <span data-ttu-id="2ae26-291">**server_hostname**：目标服务器的主机名或 FQDN。</span><span class="sxs-lookup"><span data-stu-id="2ae26-291">**server_hostname**: The host name or FQDN of the destination server.</span></span>

- <span data-ttu-id="2ae26-292">**source_context：** 与源字段关联的 **额外** 信息。</span><span class="sxs-lookup"><span data-stu-id="2ae26-292">**source_context**: Extra information associated with the **source** field.</span></span> <span data-ttu-id="2ae26-293">例如：</span><span class="sxs-lookup"><span data-stu-id="2ae26-293">For example:</span></span>

  - `Protocol Filter Agent`

  - `3489061114359050000`

- <span data-ttu-id="2ae26-294">**source**：负责事件的 Exchange Online 组件。</span><span class="sxs-lookup"><span data-stu-id="2ae26-294">**source**: The Exchange Online component that's responsible for the event.</span></span> <span data-ttu-id="2ae26-295">例如：</span><span class="sxs-lookup"><span data-stu-id="2ae26-295">For example:</span></span>

  - `AGENT`

  - `MAILBOXRULE`

  - `SMTP`

- <span data-ttu-id="2ae26-296">**event_id：** 这些值对应于"查找此邮件的相关记录"部分中介绍的 **Message** [事件](#find-related-records-for-this-message) 值。</span><span class="sxs-lookup"><span data-stu-id="2ae26-296">**event_id**: These correspond to the **Message event** values that are explained in the [Find related records for this message](#find-related-records-for-this-message) section.</span></span>

- <span data-ttu-id="2ae26-297">**internal_message_id：** 由当前正在处理邮件的 Exchange Online 服务器分配的邮件标识符。</span><span class="sxs-lookup"><span data-stu-id="2ae26-297">**internal_message_id**: A message identifier that's assigned by the Exchange Online server that's currently processing the message.</span></span>

- <span data-ttu-id="2ae26-298">**recipient_address：** 邮件收件人的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="2ae26-298">**recipient_address**: The email addresses of the message's recipients.</span></span> <span data-ttu-id="2ae26-299">多个电子邮件地址通过分号字符 (;) 分隔。</span><span class="sxs-lookup"><span data-stu-id="2ae26-299">Multiple email addresses are separated by the semicolon character (;).</span></span>

- <span data-ttu-id="2ae26-300">**recipient_count：** 邮件中的收件人总数。</span><span class="sxs-lookup"><span data-stu-id="2ae26-300">**recipient_count**: The total number of recipients in the message.</span></span>

- <span data-ttu-id="2ae26-301">**related_recipient_address：** 与 、 和 事件一起用来显示与邮件关联的其他 `EXPAND` `REDIRECT` `RESOLVE` 收件人电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="2ae26-301">**related_recipient_address**: Used with `EXPAND`, `REDIRECT`, and `RESOLVE` events to display other recipient email addresses that are associated with the message.</span></span>

- <span data-ttu-id="2ae26-302">**参考**：此字段包含特定类型事件的其他信息。</span><span class="sxs-lookup"><span data-stu-id="2ae26-302">**reference**: This field contains additional information for specific types of events.</span></span> <span data-ttu-id="2ae26-303">例如：</span><span class="sxs-lookup"><span data-stu-id="2ae26-303">For example:</span></span>

  - <span data-ttu-id="2ae26-304">**DSN：** 包含报告链接，如果 DSN 是在此事件之后生成的，则报告链接是关联的传递状态通知 (的 **message_id** 值，也称为 DSN、未送达报告、NDR 或退回邮件) 。</span><span class="sxs-lookup"><span data-stu-id="2ae26-304">**DSN**: Contains the report link, which is the **message_id** value of the associated delivery status notification (also known as a DSN, non-delivery report, NDR, or bounce message) if a DSN is generated subsequent to this event.</span></span> <span data-ttu-id="2ae26-305">如果这是 DSN 邮件，则此字段message_id生成DSN 的原始邮件的默认值。</span><span class="sxs-lookup"><span data-stu-id="2ae26-305">If this is a DSN message, this field contains the **message_id** value of the original message that the DSN was generated for.</span></span>

  - <span data-ttu-id="2ae26-306">**EXPAND**：包含 **related_recipient_address** 邮件的默认值。</span><span class="sxs-lookup"><span data-stu-id="2ae26-306">**EXPAND**: Contains the **related_recipient_address** value of the related messages.</span></span>

  - <span data-ttu-id="2ae26-307">**RECEIVE：** 如果message_id由其他进程生成，则可能包含相关邮件的 (，例如收件箱规则) 。</span><span class="sxs-lookup"><span data-stu-id="2ae26-307">**RECEIVE**: Might contain the **message_id** value of the related message if the message was generated by other processes (for example, Inbox rules).</span></span>

  - <span data-ttu-id="2ae26-308">**SEND**：包含 **internal_message_id** DSN 邮件的默认值。</span><span class="sxs-lookup"><span data-stu-id="2ae26-308">**SEND**: Contains the **internal_message_id** value of any DSN messages.</span></span>

  - <span data-ttu-id="2ae26-309">**TRANSFER：\*\*\*\*包含internal_message_id** 分叉的邮件的 (值，例如，按内容转换、邮件收件人限制或代理) 。</span><span class="sxs-lookup"><span data-stu-id="2ae26-309">**TRANSFER**: Contains the **internal_message_id** value of the message that's being forked (for example, by content conversion, message recipient limits, or agents).</span></span>

  - <span data-ttu-id="2ae26-310">**MAILBOXRULE：\*\*\*\*包含internal_message_id** 收件箱规则生成出站邮件的入站邮件的邮箱值。</span><span class="sxs-lookup"><span data-stu-id="2ae26-310">**MAILBOXRULE**: Contains the **internal_message_id** value of the inbound message that caused the Inbox rule to generate the outbound message.</span></span>

    <span data-ttu-id="2ae26-311">对于其他类型的事件，此字段通常为空。</span><span class="sxs-lookup"><span data-stu-id="2ae26-311">For other types of events, this field is usually blank.</span></span>

- <span data-ttu-id="2ae26-312">**return_path**：发送邮件的 **MAIL FROM** 命令指定的返回电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="2ae26-312">**return_path**: The return email address specified by the **MAIL FROM** command that sent the message.</span></span> <span data-ttu-id="2ae26-313">尽管此字段从不为空，但它可以将空发件人地址值表示为 `<>` 。</span><span class="sxs-lookup"><span data-stu-id="2ae26-313">Although this field is never empty, it can have the null sender address value represented as `<>`.</span></span>

- <span data-ttu-id="2ae26-314">**message_info：** 有关邮件的其他信息。</span><span class="sxs-lookup"><span data-stu-id="2ae26-314">**message_info**: Additional information about the message.</span></span> <span data-ttu-id="2ae26-315">例如：</span><span class="sxs-lookup"><span data-stu-id="2ae26-315">For example:</span></span>

  - <span data-ttu-id="2ae26-316">和 事件的邮件来源日期-时间 `DELIVER` `SEND` （UTC）。</span><span class="sxs-lookup"><span data-stu-id="2ae26-316">The message origination date-time in UTC for `DELIVER` and `SEND` events.</span></span> <span data-ttu-id="2ae26-317">起始日期-时间是邮件首次进入 Exchange Online 组织的时间。</span><span class="sxs-lookup"><span data-stu-id="2ae26-317">The origination date-time is the time when the message first entered the Exchange Online organization.</span></span> <span data-ttu-id="2ae26-318">UTC 日期-时间以 ISO 8601 日期-时间格式表示：，其中 = 年， = 月， = 天，表示时间部分的开始 `yyyy-mm-ddThh:mm:ss.fffZ` `yyyy` `mm` `dd` `T` `hh` ，= 小时， `mm` = 分钟， `ss` = 秒， `fff` = `Z` `Zulu` 秒的小数，并指示 ，这是表示 UTC 的另一种方式。</span><span class="sxs-lookup"><span data-stu-id="2ae26-318">The UTC date-time is represented in the ISO 8601 date-time format: `yyyy-mm-ddThh:mm:ss.fffZ`, where `yyyy` = year, `mm` = month, `dd` = day, `T` indicates the beginning of the time component, `hh` = hour, `mm` = minute, `ss` = second, `fff` = fractions of a second, and `Z` signifies `Zulu`, which is another way to denote UTC.</span></span>

  - <span data-ttu-id="2ae26-319">身份验证错误。</span><span class="sxs-lookup"><span data-stu-id="2ae26-319">Authentication errors.</span></span> <span data-ttu-id="2ae26-320">例如，您可能会看到身份验证出错时所使用的值 `11a` 和身份验证类型。</span><span class="sxs-lookup"><span data-stu-id="2ae26-320">For example, you might see the value `11a` and the type of authentication that was used when the authentication error occurred.</span></span>

- <span data-ttu-id="2ae26-321">**tenant_id：** 表示 Exchange Online 组织的 GUID (例如 `39238e87-b5ab-4ef6-a559-af54c6b07b42` ，) 。</span><span class="sxs-lookup"><span data-stu-id="2ae26-321">**tenant_id**: A GUID value that represents the Exchange Online organization (for example, `39238e87-b5ab-4ef6-a559-af54c6b07b42`).</span></span>

- <span data-ttu-id="2ae26-322">**original_server_ip**：原始服务器的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="2ae26-322">**original_server_ip**: The IP address of the original server.</span></span>

- <span data-ttu-id="2ae26-323">**custom_data：** 包含与特定事件类型相关的数据。</span><span class="sxs-lookup"><span data-stu-id="2ae26-323">**custom_data**: Contains data related to specific event types.</span></span> <span data-ttu-id="2ae26-324">有关详细信息，请参阅以下部分。</span><span class="sxs-lookup"><span data-stu-id="2ae26-324">For more information, see the following sections.</span></span>

#### <a name="custom_data-values"></a><span data-ttu-id="2ae26-325">custom_data值</span><span class="sxs-lookup"><span data-stu-id="2ae26-325">custom_data values</span></span>

<span data-ttu-id="2ae26-326">事件的 **custom_data** 字段由各种 Exchange Online 代理用于 `AGENTINFO` 记录邮件处理详细信息。</span><span class="sxs-lookup"><span data-stu-id="2ae26-326">The **custom_data** field for an `AGENTINFO` event is used by a variety of Exchange Online agents to log message processing details.</span></span> <span data-ttu-id="2ae26-327">以下各节介绍了一些更有趣的代理。</span><span class="sxs-lookup"><span data-stu-id="2ae26-327">Some of the more interesting agents are described in the following sections.</span></span>

#### <a name="spam-filter-agent"></a><span data-ttu-id="2ae26-328">垃圾邮件筛选器代理</span><span class="sxs-lookup"><span data-stu-id="2ae26-328">Spam filter agent</span></span>

<span data-ttu-id="2ae26-329">以 **custom_data** 开头 `S:SFA` 的一个值来自垃圾邮件筛选器代理。</span><span class="sxs-lookup"><span data-stu-id="2ae26-329">A **custom_data** value that starts with `S:SFA` is from the spam filter agent.</span></span> <span data-ttu-id="2ae26-330">下表介绍了关键详细信息：</span><span class="sxs-lookup"><span data-stu-id="2ae26-330">The key details are described in the following table:</span></span>

****

|<span data-ttu-id="2ae26-331">值</span><span class="sxs-lookup"><span data-stu-id="2ae26-331">Value</span></span>|<span data-ttu-id="2ae26-332">说明</span><span class="sxs-lookup"><span data-stu-id="2ae26-332">Description</span></span>|
|---|---|
|`SFV=NSPM`|<span data-ttu-id="2ae26-333">邮件被标记为非垃圾邮件并发送给预期收件人。</span><span class="sxs-lookup"><span data-stu-id="2ae26-333">The message was marked as non-spam and was sent to the intended recipients.</span></span>|
|`SFV=SPM`|<span data-ttu-id="2ae26-334">邮件被反垃圾邮件筛选功能标记为垃圾邮件 (也称为内容筛选) 。</span><span class="sxs-lookup"><span data-stu-id="2ae26-334">The message was marked as spam by anti-spam filtering (also known as content filtering).</span></span>|
|`SFV=BLK`|<span data-ttu-id="2ae26-335">跳过筛选但阻止邮件，因为它是由已阻止发件人发送。</span><span class="sxs-lookup"><span data-stu-id="2ae26-335">Filtering was skipped and the message was blocked because it originated from a blocked sender.</span></span>|
|`SFV=SKS`|<span data-ttu-id="2ae26-336">在反垃圾邮件筛选处理邮件之前，邮件被标记为垃圾邮件。</span><span class="sxs-lookup"><span data-stu-id="2ae26-336">The message was marked as spam prior to being processed by anti-spam filtering.</span></span> <span data-ttu-id="2ae26-337">这包括符合以下邮件流程规则条件（也称为传输规则）的邮件：自动将邮件标记为垃圾邮件并规避其他所有筛选。</span><span class="sxs-lookup"><span data-stu-id="2ae26-337">This includes messages where the message matched a mail flow rule (also known as a transport rule) to automatically mark it as spam and bypass all additional filtering.</span></span>|
|`SCL=<number>`|<span data-ttu-id="2ae26-338">有关不同的 SCL 值及其含义的详细信息，请参阅[垃圾邮件可信度](spam-confidence-levels.md)。</span><span class="sxs-lookup"><span data-stu-id="2ae26-338">For more information about the different SCL values and what they mean, see [Spam confidence levels](spam-confidence-levels.md).</span></span>|
|`PCL=<number>`|<span data-ttu-id="2ae26-p156">邮件的仿冒可能性等级 (PCL) 值。可按照[垃圾邮件可信度](spam-confidence-levels.md)中介绍 SCL 值的方式对这些值做出解释。  </span><span class="sxs-lookup"><span data-stu-id="2ae26-p156">The Phishing Confidence Level (PCL) value of the message. These can be interpreted the same way as the SCL values documented in [Spam confidence levels](spam-confidence-levels.md).</span></span>|
|`DI=SB`|<span data-ttu-id="2ae26-341">已阻止邮件发件人。</span><span class="sxs-lookup"><span data-stu-id="2ae26-341">The sender of the message was blocked.</span></span>|
|`DI=SQ`|<span data-ttu-id="2ae26-342">邮件已隔离。</span><span class="sxs-lookup"><span data-stu-id="2ae26-342">The message was quarantined.</span></span>|
|`DI=SD`|<span data-ttu-id="2ae26-343">邮件已删除。</span><span class="sxs-lookup"><span data-stu-id="2ae26-343">The message was deleted.</span></span>|
|`DI=SJ`|<span data-ttu-id="2ae26-344">邮件已发送至收件人的"垃圾邮件"文件夹。</span><span class="sxs-lookup"><span data-stu-id="2ae26-344">The message was sent to the recipient's Junk Email folder.</span></span>|
|`DI=SN`|<span data-ttu-id="2ae26-345">邮件已通过正常出站传送池路由。</span><span class="sxs-lookup"><span data-stu-id="2ae26-345">The message was routed through the normal outbound delivery pool.</span></span>|
|`DI=SO`|<span data-ttu-id="2ae26-346">邮件已通过高风险传送池路由。</span><span class="sxs-lookup"><span data-stu-id="2ae26-346">The message was routed through the higher risk delivery pool.</span></span> <span data-ttu-id="2ae26-347">有关详细信息，请参阅[出站邮件的高风险传递池](high-risk-delivery-pool-for-outbound-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="2ae26-347">For more information, see [High-risk delivery pool for outbound messages](high-risk-delivery-pool-for-outbound-messages.md).</span></span>|
|`SFS=[a]|SFS=[b]`|<span data-ttu-id="2ae26-348">说明匹配此垃圾邮件规则。</span><span class="sxs-lookup"><span data-stu-id="2ae26-348">This denotes that spam rules were matched.</span></span>|
|`IPV=CAL`|<span data-ttu-id="2ae26-349">邮件已获得垃圾邮件筛选器的允许，因为 IP 地址已在连接筛选器的 IP 允许列表中指定。</span><span class="sxs-lookup"><span data-stu-id="2ae26-349">The message was allowed through the spam filters because the IP address was specified in an IP Allow list in the connection filter.</span></span>|
|`H=<EHLOstring>`|<span data-ttu-id="2ae26-350">连接电子邮件服务器的 HELO 或 EHLO 字符串。</span><span class="sxs-lookup"><span data-stu-id="2ae26-350">The HELO or EHLO string of the connecting email server.</span></span>|
|`PTR=<ReverseDNS>`|<span data-ttu-id="2ae26-351">发送 IP 地址的 PTR 记录，也被称为反向 DNS 地址。</span><span class="sxs-lookup"><span data-stu-id="2ae26-351">The PTR record of the sending IP address, also known as the reverse DNS address.</span></span>|
|

<span data-ttu-id="2ae26-352">例如 **custom_data** 垃圾邮件筛选的邮件的值，如下所示：</span><span class="sxs-lookup"><span data-stu-id="2ae26-352">An example **custom_data** value for a message that's filtered for spam like this:</span></span>

`S:SFA=SUM|SFV=SPM|IPV=CAL|SRV=BULK|SFS=470454002|SFS=349001|SCL=9|SCORE=-1|LIST=0|DI=SN|RD=ftmail.inc.com|H=ftmail.inc.com|CIP=98.129.140.74|SFP=1501|ASF=1|CTRY=US|CLTCTRY=|LANG=en|LAT=287|LAT=260|LAT=18;`

#### <a name="malware-filter-agent"></a><span data-ttu-id="2ae26-353">恶意软件筛选器代理</span><span class="sxs-lookup"><span data-stu-id="2ae26-353">Malware filter agent</span></span>

<span data-ttu-id="2ae26-354">以 **custom_data** 的值 `S:AMA` 来自恶意软件筛选器代理。</span><span class="sxs-lookup"><span data-stu-id="2ae26-354">A **custom_data** value that starts with `S:AMA` is from the malware filter agent.</span></span> <span data-ttu-id="2ae26-355">下表介绍了关键详细信息：</span><span class="sxs-lookup"><span data-stu-id="2ae26-355">The key details are described in the following table:</span></span>

****

|<span data-ttu-id="2ae26-356">值</span><span class="sxs-lookup"><span data-stu-id="2ae26-356">Value</span></span>|<span data-ttu-id="2ae26-357">说明</span><span class="sxs-lookup"><span data-stu-id="2ae26-357">Description</span></span>|
|---|---|
|<span data-ttu-id="2ae26-358">`AMA=SUM|v=1|` 或 `AMA=EV|v=1`</span><span class="sxs-lookup"><span data-stu-id="2ae26-358">`AMA=SUM|v=1|` or `AMA=EV|v=1`</span></span>|<span data-ttu-id="2ae26-359">已确定此邮件包含恶意软件。</span><span class="sxs-lookup"><span data-stu-id="2ae26-359">The message was determined to contain malware.</span></span> <span data-ttu-id="2ae26-360">`SUM` 指示恶意软件可能已被任意数目的引擎检测到。</span><span class="sxs-lookup"><span data-stu-id="2ae26-360">`SUM` indicates the malware could've been detected by any number of engines.</span></span> <span data-ttu-id="2ae26-361">`EV` 指示恶意软件被特定引擎检测到。</span><span class="sxs-lookup"><span data-stu-id="2ae26-361">`EV` indicates the malware was detected by a specific engine.</span></span> <span data-ttu-id="2ae26-362">引擎检测到恶意软件后，将触发后续操作。</span><span class="sxs-lookup"><span data-stu-id="2ae26-362">When malware is detected by an engine this triggers the subsequent actions.</span></span>|
|`Action=r`|<span data-ttu-id="2ae26-363">邮件已被替换。</span><span class="sxs-lookup"><span data-stu-id="2ae26-363">The message was replaced.</span></span>|
|`Action=p`|<span data-ttu-id="2ae26-364">邮件已被忽略。</span><span class="sxs-lookup"><span data-stu-id="2ae26-364">The message was bypassed.</span></span>|
|`Action=d`|<span data-ttu-id="2ae26-365">邮件已被延迟。</span><span class="sxs-lookup"><span data-stu-id="2ae26-365">The message was deferred.</span></span>|
|`Action=s`|<span data-ttu-id="2ae26-366">邮件已删除。</span><span class="sxs-lookup"><span data-stu-id="2ae26-366">The message was deleted.</span></span>|
|`Action=st`|<span data-ttu-id="2ae26-367">邮件已被忽略。</span><span class="sxs-lookup"><span data-stu-id="2ae26-367">The message was bypassed.</span></span>|
|`Action=sy`|<span data-ttu-id="2ae26-368">邮件已被忽略。</span><span class="sxs-lookup"><span data-stu-id="2ae26-368">The message was bypassed.</span></span>|
|`Action=ni`|<span data-ttu-id="2ae26-369">邮件已被拒绝。</span><span class="sxs-lookup"><span data-stu-id="2ae26-369">The message was rejected.</span></span>|
|`Action=ne`|<span data-ttu-id="2ae26-370">邮件已被拒绝。</span><span class="sxs-lookup"><span data-stu-id="2ae26-370">The message was rejected.</span></span>|
|`Action=b`|<span data-ttu-id="2ae26-371">邮件已被阻止。</span><span class="sxs-lookup"><span data-stu-id="2ae26-371">The message was blocked.</span></span>|
|`Name=<malware>`|<span data-ttu-id="2ae26-372">已检测到的恶意软件的名称。</span><span class="sxs-lookup"><span data-stu-id="2ae26-372">The name of the malware that was detected.</span></span>|
|`File=<filename>`|<span data-ttu-id="2ae26-373">恶意软件中包含的文件名称。</span><span class="sxs-lookup"><span data-stu-id="2ae26-373">The name of the file that contained the malware.</span></span>|
|

<span data-ttu-id="2ae26-374">包含 **custom_data** 邮件的默认值示例如下所示：</span><span class="sxs-lookup"><span data-stu-id="2ae26-374">An example **custom_data** value for a message that contains malware looks like this:</span></span>

`S:AMA=SUM|v=1|action=b|error=|atch=1;S:AMA=EV|engine=M|v=1|sig=1.155.974.0|name=DOS/Test_File|file=filename;S:AMA=EV|engine=A|v=1|sig=201707282038|name=Test_File|file=filename`

#### <a name="transport-rule-agent"></a><span data-ttu-id="2ae26-375">传输规则代理</span><span class="sxs-lookup"><span data-stu-id="2ae26-375">Transport Rule agent</span></span>

<span data-ttu-id="2ae26-376">一 **custom_data** 一个值来自邮件流规则的传输规则代理 (`S:TRA` 传输规则) 。</span><span class="sxs-lookup"><span data-stu-id="2ae26-376">A **custom_data** value that starts with`S:TRA` is from the Transport Rule agent for mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="2ae26-377">下表介绍了关键详细信息：</span><span class="sxs-lookup"><span data-stu-id="2ae26-377">The key details are described in the following table:</span></span>

****

|<span data-ttu-id="2ae26-378">值</span><span class="sxs-lookup"><span data-stu-id="2ae26-378">Value</span></span>|<span data-ttu-id="2ae26-379">说明</span><span class="sxs-lookup"><span data-stu-id="2ae26-379">Description</span></span>|
|---|---|
|`ETR|ruleId=<guid>`|<span data-ttu-id="2ae26-380">匹配的规则 ID。</span><span class="sxs-lookup"><span data-stu-id="2ae26-380">The rule ID that was matched.</span></span>|
|`St=<datetime>`|<span data-ttu-id="2ae26-381">规则匹配发生时的日期和时间（UTC）。</span><span class="sxs-lookup"><span data-stu-id="2ae26-381">The date and time in UTC when the rule match occurred.</span></span>|
|`Action=<ActionDefinition>`|<span data-ttu-id="2ae26-382">应用的操作。</span><span class="sxs-lookup"><span data-stu-id="2ae26-382">The action that was applied.</span></span> <span data-ttu-id="2ae26-383">有关可用操作的列表，请参阅[Mail flow rule actions in Exchange Online。](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)</span><span class="sxs-lookup"><span data-stu-id="2ae26-383">For a list of available actions, see [Mail flow rule actions in Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).</span></span>|
|`Mode=<Mode>`|<span data-ttu-id="2ae26-384">规则模式。</span><span class="sxs-lookup"><span data-stu-id="2ae26-384">The mode of the rule.</span></span> <span data-ttu-id="2ae26-385">有效值为：</span><span class="sxs-lookup"><span data-stu-id="2ae26-385">Valid values are:</span></span><ul><li><span data-ttu-id="2ae26-386">**强制**：将强制执行对规则执行的所有操作。</span><span class="sxs-lookup"><span data-stu-id="2ae26-386">**Enforce**: All actions on the rule will be enforced.</span></span></li><li><span data-ttu-id="2ae26-387">**使用策略提示进行测试：** 将发送任何策略提示操作，但不执行其他强制操作。</span><span class="sxs-lookup"><span data-stu-id="2ae26-387">**Test with Policy Tips:**: Any Policy Tip actions will be sent, but other enforcement actions will not be acted on.</span></span></li><li><span data-ttu-id="2ae26-388">**不带策略提示的测试**：操作将列在日志文件，但不会以任何方式通知发件人，并且不会对强制操作采取行动。</span><span class="sxs-lookup"><span data-stu-id="2ae26-388">**Test without Policy Tips**: Actions will be listed in a log file, but senders will not be notified in any way, and enforcement actions will not be acted on.</span></span></li></ul>|
|

<span data-ttu-id="2ae26-389">与 **custom_data** 规则条件匹配的邮件的示例值如下所示：</span><span class="sxs-lookup"><span data-stu-id="2ae26-389">An example **custom_data** value for a messages that matches the conditions of a mail flow rule looks like this:</span></span>

`S:TRA=ETR|ruleId=19a25eb2-3e43-4896-ad9e-47b6c359779d|st=7/17/2017 12:31:25 AM|action=ApplyHtmlDisclaimer|sev=1|mode=Enforce`
