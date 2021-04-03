---
title: 在 Microsoft Defender ATP 中创建自定义检测规则
ms.reviewer: ''
description: 了解如何基于高级搜寻查询创建自定义检测规则
keywords: 自定义检测， 创建， 管理， 警报， 编辑， 按需运行， 频率， 间隔， 检测规则， 高级搜寻， 智能寻线， 查询， 响应操作， mdatp， microsoft defender atp
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 09/20/2020
ms.technology: mde
ms.openlocfilehash: 15dec5396a5ba95fe3ec7af5f9a72bbf15e07140
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/01/2021
ms.locfileid: "51500500"
---
# <a name="create-custom-detection-rules"></a><span data-ttu-id="89db3-104">创建自定义检测规则</span><span class="sxs-lookup"><span data-stu-id="89db3-104">Create custom detection rules</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="89db3-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="89db3-105">**Applies to:**</span></span>
- [<span data-ttu-id="89db3-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="89db3-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="89db3-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="89db3-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="89db3-108">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="89db3-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="89db3-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="89db3-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="89db3-110">通过高级搜寻 [查询](advanced-hunting-overview.md) 构建的自定义检测规则，你可以主动监视各种事件和系统状态，包括可疑的泄露活动和错误配置的设备。</span><span class="sxs-lookup"><span data-stu-id="89db3-110">Custom detection rules built from [advanced hunting](advanced-hunting-overview.md) queries let you proactively monitor various events and system states, including suspected breach activity and misconfigured devices.</span></span> <span data-ttu-id="89db3-111">你可以将它们设置为定期运行，从而在有匹配项时生成警报并执行响应操作。</span><span class="sxs-lookup"><span data-stu-id="89db3-111">You can set them to run at regular intervals, generating alerts and taking response actions whenever there are matches.</span></span>

<span data-ttu-id="89db3-112">阅读本文，了解如何创建新的自定义检测规则。</span><span class="sxs-lookup"><span data-stu-id="89db3-112">Read this article to learn how to create new custom detection rules.</span></span> <span data-ttu-id="89db3-113">或者 [，请参阅查看和管理现有规则](custom-detections-manage.md)。</span><span class="sxs-lookup"><span data-stu-id="89db3-113">Or [see viewing and managing existing rules](custom-detections-manage.md).</span></span>

> [!NOTE]
> <span data-ttu-id="89db3-114">若要创建或管理自定义检测， [你的](user-roles.md#create-roles-and-assign-the-role-to-an-azure-active-directory-group) 角色需要具有 **管理安全设置** 权限。</span><span class="sxs-lookup"><span data-stu-id="89db3-114">To create or manage custom detections, [your role](user-roles.md#create-roles-and-assign-the-role-to-an-azure-active-directory-group) needs to have the **manage security settings** permission.</span></span>

## <a name="1-prepare-the-query"></a><span data-ttu-id="89db3-115">1。准备查询。</span><span class="sxs-lookup"><span data-stu-id="89db3-115">1. Prepare the query.</span></span>

<span data-ttu-id="89db3-116">在 Microsoft Defender 安全中心中，转到高级 **搜寻** 并选择现有查询或创建新查询。</span><span class="sxs-lookup"><span data-stu-id="89db3-116">In Microsoft Defender Security Center, go to **Advanced hunting** and select an existing query or create a new query.</span></span> <span data-ttu-id="89db3-117">使用新查询时，运行查询以标识错误并了解可能的结果。</span><span class="sxs-lookup"><span data-stu-id="89db3-117">When using a new query, run the query to identify errors and understand possible results.</span></span>

>[!IMPORTANT]
><span data-ttu-id="89db3-118">为了防止服务返回太多警报，每个规则都限制为每次运行时仅生成 100 个警报。</span><span class="sxs-lookup"><span data-stu-id="89db3-118">To prevent the service from returning too many alerts, each rule is limited to generating only 100 alerts whenever it runs.</span></span> <span data-ttu-id="89db3-119">创建规则之前，请调整查询以避免提醒正常、日常活动。</span><span class="sxs-lookup"><span data-stu-id="89db3-119">Before creating a rule, tweak your query to avoid alerting for normal, day-to-day activity.</span></span>

### <a name="required-columns-in-the-query-results"></a><span data-ttu-id="89db3-120">查询结果中的必需列</span><span class="sxs-lookup"><span data-stu-id="89db3-120">Required columns in the query results</span></span>

<span data-ttu-id="89db3-121">若要对自定义检测规则使用查询，该查询必须返回以下列：</span><span class="sxs-lookup"><span data-stu-id="89db3-121">To use a query for a custom detection rule, the query must return the following columns:</span></span>

- `Timestamp`
- `DeviceId`
- `ReportId`

<span data-ttu-id="89db3-122">简单查询（例如不使用 or 运算符自定义或聚合结果的查询） `project` `summarize` 通常返回这些常用列。</span><span class="sxs-lookup"><span data-stu-id="89db3-122">Simple queries, such as those that don't use the `project` or `summarize` operator to customize or aggregate results, typically return these common columns.</span></span>

<span data-ttu-id="89db3-123">有各种方法可以确保更复杂的查询返回这些列。</span><span class="sxs-lookup"><span data-stu-id="89db3-123">There are various ways to ensure more complex queries return these columns.</span></span> <span data-ttu-id="89db3-124">例如，如果你更喜欢聚合和计数，你仍然可以返回，并且通过从涉及每个设备的最新事件 `DeviceId` `Timestamp` `ReportId` 获取它们。</span><span class="sxs-lookup"><span data-stu-id="89db3-124">For example, if you prefer to aggregate and count by `DeviceId`, you can still return `Timestamp` and `ReportId` by getting them from the most recent event involving each device.</span></span>

<span data-ttu-id="89db3-125">下面的示例查询计算使用防病毒检测 () 的唯一设备数，并使用此查询仅查找具有超过五个检测 `DeviceId` 的设备。</span><span class="sxs-lookup"><span data-stu-id="89db3-125">The sample query below counts the number of unique devices (`DeviceId`) with antivirus detections and uses this to find only those devices with more than five detections.</span></span> <span data-ttu-id="89db3-126">若要返回最新 `Timestamp` 和相应的 `ReportId` ，它将 `summarize` 运算符与 `arg_max` 函数一同使用。</span><span class="sxs-lookup"><span data-stu-id="89db3-126">To return the latest `Timestamp` and the corresponding `ReportId`, it uses the `summarize` operator with the `arg_max` function.</span></span>

```kusto
DeviceEvents
| where Timestamp > ago(7d)
| where ActionType == "AntivirusDetection"
| summarize (Timestamp, ReportId)=arg_max(Timestamp, ReportId), count() by DeviceId
| where count_ > 5
```

> [!TIP]
> <span data-ttu-id="89db3-127">为了提升查询性能，请设置一个与规则预期运行频率相匹配的时间筛选器。</span><span class="sxs-lookup"><span data-stu-id="89db3-127">For better query performance, set a time filter that matches your intended run frequency for the rule.</span></span> <span data-ttu-id="89db3-128">由于运行频率最低，每 24 小时一次，因此对过去一天的筛选将涵盖所有新数据。</span><span class="sxs-lookup"><span data-stu-id="89db3-128">Since the least frequent run is every 24 hours, filtering for the past day will cover all new data.</span></span>

## <a name="2-create-a-new-rule-and-provide-alert-details"></a><span data-ttu-id="89db3-129">2. 创建新规则并提供警报详细信息。</span><span class="sxs-lookup"><span data-stu-id="89db3-129">2. Create a new rule and provide alert details.</span></span>

<span data-ttu-id="89db3-130">使用查询编辑器中的查询，选择 **"创建检测规则** "并指定以下警报详细信息：</span><span class="sxs-lookup"><span data-stu-id="89db3-130">With the query in the query editor, select **Create detection rule** and specify the following alert details:</span></span>

- <span data-ttu-id="89db3-131">**检测名称**— 检测规则的名称</span><span class="sxs-lookup"><span data-stu-id="89db3-131">**Detection name**—name of the detection rule</span></span>
- <span data-ttu-id="89db3-132">**Frequency**— 运行查询和采取措施的时间间隔。</span><span class="sxs-lookup"><span data-stu-id="89db3-132">**Frequency**—interval for running the query and taking action.</span></span> [<span data-ttu-id="89db3-133">请参阅下面的其他指南</span><span class="sxs-lookup"><span data-stu-id="89db3-133">See additional guidance below</span></span>](#rule-frequency)
- <span data-ttu-id="89db3-134">**警报标题**- 显示的标题与规则触发的警报一起显示</span><span class="sxs-lookup"><span data-stu-id="89db3-134">**Alert title**—title displayed with alerts triggered by the rule</span></span>
- <span data-ttu-id="89db3-135">**严重性**- 规则标识的组件或活动的潜在风险。</span><span class="sxs-lookup"><span data-stu-id="89db3-135">**Severity**—potential risk of the component or activity identified by the rule.</span></span> [<span data-ttu-id="89db3-136">阅读警报严重性</span><span class="sxs-lookup"><span data-stu-id="89db3-136">Read about alert severities</span></span>](alerts-queue.md#severity)
- <span data-ttu-id="89db3-137">**类别**— 威胁组件或活动的类型（如果有）。</span><span class="sxs-lookup"><span data-stu-id="89db3-137">**Category**—type of threat component or activity, if any.</span></span> [<span data-ttu-id="89db3-138">阅读有关警报类别</span><span class="sxs-lookup"><span data-stu-id="89db3-138">Read about alert categories</span></span>](alerts-queue.md#understanding-alert-categories)
- <span data-ttu-id="89db3-139">**MITRE ATT&CK** 技术 - 一种或多种攻击技术，由 MITRE ATT 和 CK 框架中记录的规则&攻击技术。</span><span class="sxs-lookup"><span data-stu-id="89db3-139">**MITRE ATT&CK techniques**—one or more attack techniques identified by the rule as documented in the MITRE ATT&CK framework.</span></span> <span data-ttu-id="89db3-140">本部分不适用于某些警报类别，如恶意软件、勒索软件、可疑活动和不需要的软件</span><span class="sxs-lookup"><span data-stu-id="89db3-140">This section is not available with certain alert categories, such as malware, ransomware, suspicious activity, and unwanted software</span></span>
- <span data-ttu-id="89db3-141">**说明**-有关规则标识的组件或活动详细信息</span><span class="sxs-lookup"><span data-stu-id="89db3-141">**Description**—more information about the component or activity identified by the rule</span></span> 
- <span data-ttu-id="89db3-142">**建议的操作**- 响应者为响应警报可能执行的其他操作</span><span class="sxs-lookup"><span data-stu-id="89db3-142">**Recommended actions**—additional actions that responders might take in response to an alert</span></span>

<span data-ttu-id="89db3-143">有关警报详细信息的显示方式的详细信息， [请阅读有关警报队列的信息](alerts-queue.md)。</span><span class="sxs-lookup"><span data-stu-id="89db3-143">For more information about how alert details are displayed, [read about the alert queue](alerts-queue.md).</span></span>

### <a name="rule-frequency"></a><span data-ttu-id="89db3-144">规则频率</span><span class="sxs-lookup"><span data-stu-id="89db3-144">Rule frequency</span></span>

<span data-ttu-id="89db3-145">保存后，新的自定义检测规则会立即运行并检查过去 30 天的数据中的匹配。</span><span class="sxs-lookup"><span data-stu-id="89db3-145">When saved, a new custom detection rule immediately runs and checks for matches from the past 30 days of data.</span></span> <span data-ttu-id="89db3-146">然后，该规则将按固定间隔再次运行，并基于您选择的频率重新运行回看持续时间：</span><span class="sxs-lookup"><span data-stu-id="89db3-146">The rule then runs again at fixed intervals and lookback durations based on the frequency you choose:</span></span>

- <span data-ttu-id="89db3-147">**每 24 小时** 运行一次 ，每 24 小时运行一次，检查过去 30 天的数据</span><span class="sxs-lookup"><span data-stu-id="89db3-147">**Every 24 hours**—runs every 24 hours, checking data from the past 30 days</span></span>
- <span data-ttu-id="89db3-148">**每 12 小时** 运行一次，每 12 小时运行一次，检查过去 24 小时内的数据</span><span class="sxs-lookup"><span data-stu-id="89db3-148">**Every 12 hours**—runs every 12 hours, checking data from the past 24 hours</span></span>
- <span data-ttu-id="89db3-149">**每 3 小时** 运行一次，每 3 小时运行一次，检查过去 6 小时的数据</span><span class="sxs-lookup"><span data-stu-id="89db3-149">**Every 3 hours**—runs every 3 hours, checking data from the past 6 hours</span></span>
- <span data-ttu-id="89db3-150">**每小时** 运行一次，每小时运行一次，检查过去 2 小时的数据</span><span class="sxs-lookup"><span data-stu-id="89db3-150">**Every hour**—runs hourly, checking data from the past 2 hours</span></span>

<span data-ttu-id="89db3-151">编辑规则时，它将在计划的下一个运行时中根据设置的频率运行应用的更改。</span><span class="sxs-lookup"><span data-stu-id="89db3-151">When you edit a rule, it will run with the applied changes in the next run time scheduled according to the frequency you set.</span></span>


> [!TIP]
> <span data-ttu-id="89db3-152">将查询中的时间筛选器与回看持续时间相匹配。</span><span class="sxs-lookup"><span data-stu-id="89db3-152">Match the time filters in your query with the lookback duration.</span></span> <span data-ttu-id="89db3-153">将忽略超出回视持续时间的结果。</span><span class="sxs-lookup"><span data-stu-id="89db3-153">Results outside of the lookback duration are ignored.</span></span>

<span data-ttu-id="89db3-154">选择与您希望监视检测的频率相匹配的频率，并考虑您的组织响应警报的能力。</span><span class="sxs-lookup"><span data-stu-id="89db3-154">Select the frequency that matches how closely you want to monitor detections, and consider your organization's capacity to respond to the alerts.</span></span>

## <a name="3-choose-the-impacted-entities"></a><span data-ttu-id="89db3-155">3. 选择影响的实体。</span><span class="sxs-lookup"><span data-stu-id="89db3-155">3. Choose the impacted entities.</span></span>

<span data-ttu-id="89db3-156">确定查询结果中预期要查找主要受影响或受影响的实体的列。</span><span class="sxs-lookup"><span data-stu-id="89db3-156">Identify the columns in your query results where you expect to find the main affected or impacted entity.</span></span> <span data-ttu-id="89db3-157">例如，查询可能同时返回设备和用户 ID。</span><span class="sxs-lookup"><span data-stu-id="89db3-157">For example, a query might return both device and user IDs.</span></span> <span data-ttu-id="89db3-158">确定哪些列表示主要影响的实体，可帮助服务聚合相关警报、关联事件和目标响应操作。</span><span class="sxs-lookup"><span data-stu-id="89db3-158">Identifying which of these columns represent the main impacted entity helps the service aggregate relevant alerts, correlate incidents, and target response actions.</span></span>

<span data-ttu-id="89db3-159">只能为每种实体类型选择一列。</span><span class="sxs-lookup"><span data-stu-id="89db3-159">You can select only one column for each entity type.</span></span> <span data-ttu-id="89db3-160">无法选择查询未返回的列。</span><span class="sxs-lookup"><span data-stu-id="89db3-160">Columns that are not returned by your query can't be selected.</span></span>

## <a name="4-specify-actions"></a><span data-ttu-id="89db3-161">4. 指定操作。</span><span class="sxs-lookup"><span data-stu-id="89db3-161">4. Specify actions.</span></span>

<span data-ttu-id="89db3-162">自定义检测规则可以自动对查询返回的文件或设备执行操作。</span><span class="sxs-lookup"><span data-stu-id="89db3-162">Your custom detection rule can automatically take actions on files or devices that are returned by the query.</span></span>

### <a name="actions-on-devices"></a><span data-ttu-id="89db3-163">对设备的操作</span><span class="sxs-lookup"><span data-stu-id="89db3-163">Actions on devices</span></span>

<span data-ttu-id="89db3-164">这些操作适用于查询结果 `DeviceId` 列中的设备：</span><span class="sxs-lookup"><span data-stu-id="89db3-164">These actions are applied to devices in the `DeviceId` column of the query results:</span></span>

- <span data-ttu-id="89db3-165">**隔离设备** 应用完全网络隔离，阻止设备连接到任何应用程序或服务，Defender for Endpoint 服务除外。</span><span class="sxs-lookup"><span data-stu-id="89db3-165">**Isolate device**—applies full network isolation, preventing the device from connecting to any application or service, except for the Defender for Endpoint service.</span></span> [<span data-ttu-id="89db3-166">详细了解设备隔离</span><span class="sxs-lookup"><span data-stu-id="89db3-166">Learn more about device isolation</span></span>](respond-machine-alerts.md#isolate-devices-from-the-network)
- <span data-ttu-id="89db3-167">**收集调查包**- 在 ZIP 文件中收集设备信息。</span><span class="sxs-lookup"><span data-stu-id="89db3-167">**Collect investigation package**—collects device information in a ZIP file.</span></span> [<span data-ttu-id="89db3-168">详细了解调查包</span><span class="sxs-lookup"><span data-stu-id="89db3-168">Learn more about the investigation package</span></span>](respond-machine-alerts.md#collect-investigation-package-from-devices)
- <span data-ttu-id="89db3-169">**运行防病毒扫描**- 在设备上执行完全 Microsoft Defender 防病毒扫描</span><span class="sxs-lookup"><span data-stu-id="89db3-169">**Run antivirus scan**—performs a full Microsoft Defender Antivirus scan on the device</span></span>
- <span data-ttu-id="89db3-170">**启动调查**— 在 [设备上](automated-investigations.md) 启动自动调查</span><span class="sxs-lookup"><span data-stu-id="89db3-170">**Initiate investigation**—starts an [automated investigation](automated-investigations.md) on the device</span></span>
- <span data-ttu-id="89db3-171">**限制应用** 执行 — 在设备上设置限制，以仅允许使用 Microsoft 颁发的证书签名的文件运行。</span><span class="sxs-lookup"><span data-stu-id="89db3-171">**Restrict app execution**—sets restrictions on the device to allow only files that are signed with a Microsoft-issued certificate to run.</span></span> [<span data-ttu-id="89db3-172">详细了解如何限制应用执行</span><span class="sxs-lookup"><span data-stu-id="89db3-172">Learn more about restricting app execution</span></span>](respond-machine-alerts.md#restrict-app-execution)

### <a name="actions-on-files"></a><span data-ttu-id="89db3-173">对文件的操作</span><span class="sxs-lookup"><span data-stu-id="89db3-173">Actions on files</span></span>

<span data-ttu-id="89db3-174">这些操作将应用于查询结果的 `SHA1` 或 `InitiatingProcessSHA1` 列中的文件：</span><span class="sxs-lookup"><span data-stu-id="89db3-174">These actions are applied to files in the `SHA1` or the `InitiatingProcessSHA1` column of the query results:</span></span>

- <span data-ttu-id="89db3-175">**允许/** 阻止 — 自动将文件添加到 [自定义指示器](manage-indicators.md) 列表，以便它始终允许运行或阻止运行。</span><span class="sxs-lookup"><span data-stu-id="89db3-175">**Allow/Block**—automatically adds the file to your [custom indicator list](manage-indicators.md) so that it is always allowed to run or blocked from running.</span></span> <span data-ttu-id="89db3-176">你可以设置此操作的范围，以便仅在所选设备组上执行该操作。</span><span class="sxs-lookup"><span data-stu-id="89db3-176">You can set the scope of this action so that it is taken only on selected device groups.</span></span> <span data-ttu-id="89db3-177">此范围与规则的范围无关。</span><span class="sxs-lookup"><span data-stu-id="89db3-177">This scope is independent of the scope of the rule.</span></span>
- <span data-ttu-id="89db3-178">**隔离** 文件 — 从文件的当前位置删除文件，将副本隔离</span><span class="sxs-lookup"><span data-stu-id="89db3-178">**Quarantine file**—deletes the file from its current location and places a copy in quarantine</span></span>

### <a name="actions-on-users"></a><span data-ttu-id="89db3-179">用户操作</span><span class="sxs-lookup"><span data-stu-id="89db3-179">Actions on users</span></span>

- <span data-ttu-id="89db3-180">**将用户标记为已泄露**— 在 Azure Active Directory 中，将用户的风险级别设置为"高"，从而触发相应的 [标识保护策略](https://docs.microsoft.com/azure/active-directory/identity-protection/overview-identity-protection#risk-levels)。</span><span class="sxs-lookup"><span data-stu-id="89db3-180">**Mark user as compromised**—sets the user's risk level to "high" in Azure Active Directory, triggering the corresponding [identity protection policies](https://docs.microsoft.com/azure/active-directory/identity-protection/overview-identity-protection#risk-levels).</span></span>

## <a name="5-set-the-rule-scope"></a><span data-ttu-id="89db3-181">5. 设置规则范围。</span><span class="sxs-lookup"><span data-stu-id="89db3-181">5. Set the rule scope.</span></span>

<span data-ttu-id="89db3-182">设置范围以指定规则涵盖的设备：</span><span class="sxs-lookup"><span data-stu-id="89db3-182">Set the scope to specify which devices are covered by the rule:</span></span>

- <span data-ttu-id="89db3-183">所有设备</span><span class="sxs-lookup"><span data-stu-id="89db3-183">All devices</span></span>
- <span data-ttu-id="89db3-184">特定设备组</span><span class="sxs-lookup"><span data-stu-id="89db3-184">Specific device groups</span></span>

<span data-ttu-id="89db3-185">将仅查询作用域中设备的数据。</span><span class="sxs-lookup"><span data-stu-id="89db3-185">Only data from devices in scope will be queried.</span></span> <span data-ttu-id="89db3-186">此外，将仅在这些设备上执行操作。</span><span class="sxs-lookup"><span data-stu-id="89db3-186">Also, actions will be taken only on those devices.</span></span>

## <a name="6-review-and-turn-on-the-rule"></a><span data-ttu-id="89db3-187">6. 查看并启用规则。</span><span class="sxs-lookup"><span data-stu-id="89db3-187">6. Review and turn on the rule.</span></span>

<span data-ttu-id="89db3-188">查看规则后，选择" **创建"** 以保存它。</span><span class="sxs-lookup"><span data-stu-id="89db3-188">After reviewing the rule, select **Create** to save it.</span></span> <span data-ttu-id="89db3-189">自定义检测规则会立即运行。</span><span class="sxs-lookup"><span data-stu-id="89db3-189">The custom detection rule immediately runs.</span></span> <span data-ttu-id="89db3-190">它根据配置的频率再次运行，以检查匹配项、生成警报以及执行响应操作。</span><span class="sxs-lookup"><span data-stu-id="89db3-190">It runs again based on configured frequency to check for matches, generate alerts, and take response actions.</span></span>

<span data-ttu-id="89db3-191">可以查看 [和管理自定义检测规则](custom-detections-manage.md)，检查其之前的运行，并查看已触发的警报。</span><span class="sxs-lookup"><span data-stu-id="89db3-191">You can [view and manage custom detection rules](custom-detections-manage.md), check their previous runs, and review the alerts they have triggered.</span></span> <span data-ttu-id="89db3-192">您还可以按需运行规则并对其进行修改。</span><span class="sxs-lookup"><span data-stu-id="89db3-192">You can also run a rule on demand and modify it.</span></span>

## <a name="related-topics"></a><span data-ttu-id="89db3-193">相关主题</span><span class="sxs-lookup"><span data-stu-id="89db3-193">Related topics</span></span>

- [<span data-ttu-id="89db3-194">查看和管理自定义检测规则</span><span class="sxs-lookup"><span data-stu-id="89db3-194">View and manage custom detection rules</span></span>](custom-detections-manage.md)
- [<span data-ttu-id="89db3-195">自定义检测概述</span><span class="sxs-lookup"><span data-stu-id="89db3-195">Custom detections overview</span></span>](overview-custom-detections.md)
- [<span data-ttu-id="89db3-196">高级搜寻概述</span><span class="sxs-lookup"><span data-stu-id="89db3-196">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="89db3-197">了解高级搜寻查询语言</span><span class="sxs-lookup"><span data-stu-id="89db3-197">Learn the advanced hunting query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="89db3-198">查看和组织警报</span><span class="sxs-lookup"><span data-stu-id="89db3-198">View and organize alerts</span></span>](alerts-queue.md)
