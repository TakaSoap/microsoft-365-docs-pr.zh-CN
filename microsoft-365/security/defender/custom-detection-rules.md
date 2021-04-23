---
title: 在 Microsoft 365 Defender 中创建自定义检测规则
description: 了解如何创建和管理基于高级搜寻查询的自定义检测规则
keywords: 高级搜寻， 威胁搜寻， 网络威胁搜寻， Microsoft 365 Defender， microsoft 365， m365， 搜索， 查询， 遥测， 自定义检测， 规则， 架构， kusto， RBAC， 权限， Microsoft Defender for Endpoint
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: f37cc63c958331f7c03e09689de92c73fd06b4d4
ms.sourcegitcommit: 7cc2be0244fcc30049351e35c25369cacaaf4ca9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/22/2021
ms.locfileid: "51952556"
---
# <a name="create-and-manage-custom-detections-rules"></a><span data-ttu-id="6c7de-104">创建和管理自定义检测规则</span><span class="sxs-lookup"><span data-stu-id="6c7de-104">Create and manage custom detections rules</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="6c7de-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="6c7de-105">**Applies to:**</span></span>
- <span data-ttu-id="6c7de-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6c7de-106">Microsoft 365 Defender</span></span>
- <span data-ttu-id="6c7de-107">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="6c7de-107">Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="6c7de-108">自定义检测规则是可以使用高级搜寻查询设计和 [调整](advanced-hunting-overview.md) 的规则。</span><span class="sxs-lookup"><span data-stu-id="6c7de-108">Custom detection rules are rules you can design and tweak using [advanced hunting](advanced-hunting-overview.md) queries.</span></span> <span data-ttu-id="6c7de-109">通过这些规则，您可以主动监视各种事件和系统状态，包括可疑的泄露活动和错误配置的终结点。</span><span class="sxs-lookup"><span data-stu-id="6c7de-109">These rules let you proactively monitor various events and system states, including suspected breach activity and misconfigured endpoints.</span></span> <span data-ttu-id="6c7de-110">你可以将它们设置为定期运行，从而在有匹配项时生成警报并执行响应操作。</span><span class="sxs-lookup"><span data-stu-id="6c7de-110">You can set them to run at regular intervals, generating alerts and taking response actions whenever there are matches.</span></span>

## <a name="required-permissions-for-managing-custom-detections"></a><span data-ttu-id="6c7de-111">管理自定义检测所需的权限</span><span class="sxs-lookup"><span data-stu-id="6c7de-111">Required permissions for managing custom detections</span></span>

<span data-ttu-id="6c7de-112">若要管理自定义检测，需要分配有以下角色之一：</span><span class="sxs-lookup"><span data-stu-id="6c7de-112">To manage custom detections, you need to be assigned one of these roles:</span></span>

- <span data-ttu-id="6c7de-113">**安全管理员**- 具有 [此 Azure Active Directory](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) 角色的用户可以在 Microsoft 365 安全中心和其他门户和服务中管理安全设置。</span><span class="sxs-lookup"><span data-stu-id="6c7de-113">**Security administrator**—Users with this [Azure Active Directory role](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) can manage security settings in Microsoft 365 security center and other portals and services.</span></span>

- <span data-ttu-id="6c7de-114">**安全操作员**- 具有 [此 Azure Active Directory](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) 角色的用户可以管理警报，并且对安全相关功能（包括 Microsoft 365 安全中心内的所有信息）具有全局只读访问权限。</span><span class="sxs-lookup"><span data-stu-id="6c7de-114">**Security operator**—Users with this [Azure Active Directory role](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) can manage alerts and have global read-only access to security-related features, including all information in Microsoft 365 security center.</span></span> <span data-ttu-id="6c7de-115">只有在 Microsoft Defender for Endpoint 中关闭基于角色的访问控制 (RBAC) ，此角色才足以管理自定义检测。</span><span class="sxs-lookup"><span data-stu-id="6c7de-115">This role is sufficient for managing custom detections only if role-based access control (RBAC) is turned off in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="6c7de-116">如果已配置 RBAC，则还需要 Defender for Endpoint **的** "管理安全设置"权限。</span><span class="sxs-lookup"><span data-stu-id="6c7de-116">If you have RBAC configured, you also need the **manage security settings** permission for Defender for Endpoint.</span></span>

<span data-ttu-id="6c7de-117">若要管理所需的权限，全局 **管理员可以** ：</span><span class="sxs-lookup"><span data-stu-id="6c7de-117">To manage required permissions, a **global administrator** can:</span></span>

- <span data-ttu-id="6c7de-118">在 **Microsoft** [365](https://admin.microsoft.com/)管理中心中，在角色安全管理员 下分配安全管理员 **或**  >  **安全操作员角色**。</span><span class="sxs-lookup"><span data-stu-id="6c7de-118">Assign the **security administrator** or **security operator** role in [Microsoft 365 admin center](https://admin.microsoft.com/) under **Roles** > **Security admin**.</span></span>
- <span data-ttu-id="6c7de-119">在"设置权限角色"下，在 [Microsoft Defender](https://securitycenter.windows.com/)安全中心中检查适用于终结点的 Microsoft Defender 的 RBAC  >    >  **设置**。</span><span class="sxs-lookup"><span data-stu-id="6c7de-119">Check RBAC settings for Microsoft Defender for Endpoint in [Microsoft Defender Security Center](https://securitycenter.windows.com/) under **Settings** > **Permissions** > **Roles**.</span></span> <span data-ttu-id="6c7de-120">选择相应的角色以分配 **管理安全设置** 权限。</span><span class="sxs-lookup"><span data-stu-id="6c7de-120">Select the corresponding role to assign the **manage security settings** permission.</span></span>

> [!NOTE]
> <span data-ttu-id="6c7de-121">若要管理自定义检测，**如果** RBAC 已打开，安全操作员将需要 Microsoft Defender for Endpoint 中的管理安全设置权限。</span><span class="sxs-lookup"><span data-stu-id="6c7de-121">To manage custom detections, **security operators** will need the **manage security settings** permission in Microsoft Defender for Endpoint if RBAC is turned on.</span></span>

## <a name="create-a-custom-detection-rule"></a><span data-ttu-id="6c7de-122">创建自定义检测规则</span><span class="sxs-lookup"><span data-stu-id="6c7de-122">Create a custom detection rule</span></span>
### <a name="1-prepare-the-query"></a><span data-ttu-id="6c7de-123">1。准备查询。</span><span class="sxs-lookup"><span data-stu-id="6c7de-123">1. Prepare the query.</span></span>

<span data-ttu-id="6c7de-124">在 Microsoft 365 安全中心，转到高级 **搜寻** 并选择现有查询或创建新查询。</span><span class="sxs-lookup"><span data-stu-id="6c7de-124">In Microsoft 365 security center, go to **Advanced hunting** and select an existing query or create a new query.</span></span> <span data-ttu-id="6c7de-125">使用新查询时，运行查询以标识错误并了解可能的结果。</span><span class="sxs-lookup"><span data-stu-id="6c7de-125">When using a new query, run the query to identify errors and understand possible results.</span></span>

>[!IMPORTANT]
><span data-ttu-id="6c7de-126">为了防止服务返回太多警报，每个规则都限制为每次运行时仅生成 100 个警报。</span><span class="sxs-lookup"><span data-stu-id="6c7de-126">To prevent the service from returning too many alerts, each rule is limited to generating only 100 alerts whenever it runs.</span></span> <span data-ttu-id="6c7de-127">创建规则之前，请调整查询以避免提醒正常、日常活动。</span><span class="sxs-lookup"><span data-stu-id="6c7de-127">Before creating a rule, tweak your query to avoid alerting for normal, day-to-day activity.</span></span>


#### <a name="required-columns-in-the-query-results"></a><span data-ttu-id="6c7de-128">查询结果中的必需列</span><span class="sxs-lookup"><span data-stu-id="6c7de-128">Required columns in the query results</span></span>
<span data-ttu-id="6c7de-129">若要创建自定义检测规则，查询必须返回以下列：</span><span class="sxs-lookup"><span data-stu-id="6c7de-129">To create a custom detection rule, the query must return the following columns:</span></span>

- <span data-ttu-id="6c7de-130">`Timestamp`用于设置生成的警报的时间戳</span><span class="sxs-lookup"><span data-stu-id="6c7de-130">`Timestamp`—used to set the timestamp for generated alerts</span></span>
- <span data-ttu-id="6c7de-131">`ReportId`— 启用对原始记录的查找</span><span class="sxs-lookup"><span data-stu-id="6c7de-131">`ReportId`—enables lookups for the original records</span></span>
- <span data-ttu-id="6c7de-132">标识特定设备、用户或邮箱的以下列之一：</span><span class="sxs-lookup"><span data-stu-id="6c7de-132">One of the following columns that identify specific devices, users, or mailboxes:</span></span>
    - `DeviceId`
    - `DeviceName`
    - `RemoteDeviceName`
    - `RecipientEmailAddress`
    - <span data-ttu-id="6c7de-133">`SenderFromAddress` (信封发件人或Return-Path地址) </span><span class="sxs-lookup"><span data-stu-id="6c7de-133">`SenderFromAddress` (envelope sender or Return-Path address)</span></span>
    - <span data-ttu-id="6c7de-134">`SenderMailFromAddress` (客户端邮箱显示发件人) </span><span class="sxs-lookup"><span data-stu-id="6c7de-134">`SenderMailFromAddress` (sender address displayed by email client)</span></span>
    - `RecipientObjectId`
    - `AccountObjectId`
    - `AccountSid`
    - `AccountUpn`
    - `InitiatingProcessAccountSid`
    - `InitiatingProcessAccountUpn`
    - `InitiatingProcessAccountObjectId`

>[!NOTE]
><span data-ttu-id="6c7de-135">将新表添加到高级搜寻架构时，将添加对其他 [实体的支持](advanced-hunting-schema-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="6c7de-135">Support for additional entities will be added as new tables are added to the [advanced hunting schema](advanced-hunting-schema-tables.md).</span></span>

<span data-ttu-id="6c7de-136">简单查询（例如不使用 or 运算符自定义或聚合结果的查询） `project` `summarize` 通常返回这些常用列。</span><span class="sxs-lookup"><span data-stu-id="6c7de-136">Simple queries, such as those that don't use the `project` or `summarize` operator to customize or aggregate results, typically return these common columns.</span></span>

<span data-ttu-id="6c7de-137">有各种方法可以确保更复杂的查询返回这些列。</span><span class="sxs-lookup"><span data-stu-id="6c7de-137">There are various ways to ensure more complex queries return these columns.</span></span> <span data-ttu-id="6c7de-138">例如，如果你更希望按列下的实体（如 ）进行聚合和计数，你仍然可以返回 ，并且通过从涉及每个唯一的 的最新事件获取 `DeviceId` `Timestamp` `ReportId` `DeviceId` 它。</span><span class="sxs-lookup"><span data-stu-id="6c7de-138">For example, if you prefer to aggregate and count by entity under a column such as `DeviceId`, you can still return `Timestamp` and `ReportId` by getting it from the most recent event involving each unique `DeviceId`.</span></span>

<span data-ttu-id="6c7de-139">下面的示例查询计算使用防病毒检测 () 的唯一设备数，并使用此计数仅查找检测次数超过 `DeviceId` 五的设备。</span><span class="sxs-lookup"><span data-stu-id="6c7de-139">The sample query below counts the number of unique devices (`DeviceId`) with antivirus detections and uses this count to find only the devices with more than five detections.</span></span> <span data-ttu-id="6c7de-140">若要返回最新 `Timestamp` 和相应的 `ReportId` ，它将 `summarize` 运算符与 `arg_max` 函数一同使用。</span><span class="sxs-lookup"><span data-stu-id="6c7de-140">To return the latest `Timestamp` and the corresponding `ReportId`, it uses the `summarize` operator with the `arg_max` function.</span></span>

```kusto
DeviceEvents
| where Timestamp > ago(1d)
| where ActionType == "AntivirusDetection"
| summarize (Timestamp, ReportId)=arg_max(Timestamp, ReportId), count() by DeviceId
| where count_ > 5
```

> [!TIP]
> <span data-ttu-id="6c7de-141">为了提升查询性能，请设置一个与规则预期运行频率相匹配的时间筛选器。</span><span class="sxs-lookup"><span data-stu-id="6c7de-141">For better query performance, set a time filter that matches your intended run frequency for the rule.</span></span> <span data-ttu-id="6c7de-142">由于运行频率最低，每 _24 小时_ 一次，因此对过去一天的筛选将覆盖所有新数据。</span><span class="sxs-lookup"><span data-stu-id="6c7de-142">Since the least frequent run is _every 24 hours_, filtering for the past day will cover all new data.</span></span>

### <a name="2-create-new-rule-and-provide-alert-details"></a><span data-ttu-id="6c7de-143">2. 创建新规则并提供警报详细信息。</span><span class="sxs-lookup"><span data-stu-id="6c7de-143">2. Create new rule and provide alert details.</span></span>

<span data-ttu-id="6c7de-144">使用查询编辑器中的查询，选择 **"创建检测规则** "并指定以下警报详细信息：</span><span class="sxs-lookup"><span data-stu-id="6c7de-144">With the query in the query editor, select **Create detection rule** and specify the following alert details:</span></span>

- <span data-ttu-id="6c7de-145">**检测名称**— 检测规则的名称</span><span class="sxs-lookup"><span data-stu-id="6c7de-145">**Detection name**—name of the detection rule</span></span>
- <span data-ttu-id="6c7de-146">**Frequency**— 运行查询和采取措施的时间间隔。</span><span class="sxs-lookup"><span data-stu-id="6c7de-146">**Frequency**—interval for running the query and taking action.</span></span> [<span data-ttu-id="6c7de-147">请参阅下面的其他指南</span><span class="sxs-lookup"><span data-stu-id="6c7de-147">See additional guidance below</span></span>](#rule-frequency)
- <span data-ttu-id="6c7de-148">**警报标题**- 显示的标题与规则触发的警报一起显示</span><span class="sxs-lookup"><span data-stu-id="6c7de-148">**Alert title**—title displayed with alerts triggered by the rule</span></span>
- <span data-ttu-id="6c7de-149">**严重性**- 规则标识的组件或活动的潜在风险</span><span class="sxs-lookup"><span data-stu-id="6c7de-149">**Severity**—potential risk of the component or activity identified by the rule</span></span>
- <span data-ttu-id="6c7de-150">**类别**— 规则标识的威胁组件或活动</span><span class="sxs-lookup"><span data-stu-id="6c7de-150">**Category**—threat component or activity identified by the rule</span></span>
- <span data-ttu-id="6c7de-151">**MITRE ATT&CK** 技术 - 一种或多种攻击技术，由 [MITRE ATT](https://attack.mitre.org/)和 CK 框架中记录的规则&攻击技术。</span><span class="sxs-lookup"><span data-stu-id="6c7de-151">**MITRE ATT&CK techniques**—one or more attack techniques identified by the rule as documented in the [MITRE ATT&CK framework](https://attack.mitre.org/).</span></span> <span data-ttu-id="6c7de-152">本部分对某些警报类别（包括恶意软件、勒索软件、可疑活动和不需要的软件）隐藏</span><span class="sxs-lookup"><span data-stu-id="6c7de-152">This section is hidden for certain alert categories, including malware, ransomware, suspicious activity, and unwanted software</span></span>
- <span data-ttu-id="6c7de-153">**说明**-有关规则标识的组件或活动详细信息</span><span class="sxs-lookup"><span data-stu-id="6c7de-153">**Description**—more information about the component or activity identified by the rule</span></span> 
- <span data-ttu-id="6c7de-154">**建议的操作**- 响应者为响应警报可能执行的其他操作</span><span class="sxs-lookup"><span data-stu-id="6c7de-154">**Recommended actions**—additional actions that responders might take in response to an alert</span></span>

#### <a name="rule-frequency"></a><span data-ttu-id="6c7de-155">规则频率</span><span class="sxs-lookup"><span data-stu-id="6c7de-155">Rule frequency</span></span>
<span data-ttu-id="6c7de-156">保存新规则时，它将运行并检查过去 30 天的数据中的匹配。</span><span class="sxs-lookup"><span data-stu-id="6c7de-156">When you save a new rule, it runs and checks for matches from the past 30 days of data.</span></span> <span data-ttu-id="6c7de-157">然后，该规则以固定间隔再次运行，并基于你选择的频率应用回看持续时间：</span><span class="sxs-lookup"><span data-stu-id="6c7de-157">The rule then runs again at fixed intervals, applying a lookback duration based on the frequency you choose:</span></span>

- <span data-ttu-id="6c7de-158">**每 24 小时** 运行一次 ，每 24 小时运行一次，检查过去 30 天的数据</span><span class="sxs-lookup"><span data-stu-id="6c7de-158">**Every 24 hours**—runs every 24 hours, checking data from the past 30 days</span></span>
- <span data-ttu-id="6c7de-159">**每 12 小时** 运行一次，每 12 小时运行一次，检查过去 24 小时内的数据</span><span class="sxs-lookup"><span data-stu-id="6c7de-159">**Every 12 hours**—runs every 12 hours, checking data from the past 24 hours</span></span>
- <span data-ttu-id="6c7de-160">**每 3 小时** 运行一次，每 3 小时运行一次，检查过去 6 小时的数据</span><span class="sxs-lookup"><span data-stu-id="6c7de-160">**Every 3 hours**—runs every 3 hours, checking data from the past 6 hours</span></span>
- <span data-ttu-id="6c7de-161">**每小时** 运行一次，每小时运行一次，检查过去 2 小时的数据</span><span class="sxs-lookup"><span data-stu-id="6c7de-161">**Every hour**—runs hourly, checking data from the past 2 hours</span></span>

<span data-ttu-id="6c7de-162">编辑规则时，它将在计划的下一个运行时中根据设置的频率运行应用的更改。</span><span class="sxs-lookup"><span data-stu-id="6c7de-162">When you edit a rule, it will run with the applied changes in the next run time scheduled according to the frequency you set.</span></span>



>[!TIP]
> <span data-ttu-id="6c7de-163">将查询中的时间筛选器与回看持续时间相匹配。</span><span class="sxs-lookup"><span data-stu-id="6c7de-163">Match the time filters in your query with the lookback duration.</span></span> <span data-ttu-id="6c7de-164">将忽略超出回视持续时间的结果。</span><span class="sxs-lookup"><span data-stu-id="6c7de-164">Results outside of the lookback duration are ignored.</span></span>  

<span data-ttu-id="6c7de-165">选择与要监视检测的频率相匹配的频率。</span><span class="sxs-lookup"><span data-stu-id="6c7de-165">Select the frequency that matches how closely you want to monitor detections.</span></span> <span data-ttu-id="6c7de-166">考虑组织响应警报的能力。</span><span class="sxs-lookup"><span data-stu-id="6c7de-166">Consider your organization's capacity to respond to the alerts.</span></span>

### <a name="3-choose-the-impacted-entities"></a><span data-ttu-id="6c7de-167">3. 选择影响的实体。</span><span class="sxs-lookup"><span data-stu-id="6c7de-167">3. Choose the impacted entities.</span></span>
<span data-ttu-id="6c7de-168">确定查询结果中预期要查找主要受影响或受影响的实体的列。</span><span class="sxs-lookup"><span data-stu-id="6c7de-168">Identify the columns in your query results where you expect to find the main affected or impacted entity.</span></span> <span data-ttu-id="6c7de-169">例如，查询可能会返回发件人 (`SenderFromAddress` 或) `SenderMailFromAddress` 收件人 () `RecipientEmailAddress` 地址。</span><span class="sxs-lookup"><span data-stu-id="6c7de-169">For example, a query might return sender (`SenderFromAddress` or `SenderMailFromAddress`) and recipient (`RecipientEmailAddress`) addresses.</span></span> <span data-ttu-id="6c7de-170">确定哪些列表示主要影响的实体，可帮助服务聚合相关警报、关联事件和目标响应操作。</span><span class="sxs-lookup"><span data-stu-id="6c7de-170">Identifying which of these columns represent the main impacted entity helps the service aggregate relevant alerts, correlate incidents, and target response actions.</span></span>

<span data-ttu-id="6c7de-171">只能为邮箱、用户或设备 (每个实体类型选择一) 。</span><span class="sxs-lookup"><span data-stu-id="6c7de-171">You can select only one column for each entity type (mailbox, user, or device).</span></span> <span data-ttu-id="6c7de-172">无法选择查询未返回的列。</span><span class="sxs-lookup"><span data-stu-id="6c7de-172">Columns that are not returned by your query can't be selected.</span></span>

### <a name="4-specify-actions"></a><span data-ttu-id="6c7de-173">4. 指定操作。</span><span class="sxs-lookup"><span data-stu-id="6c7de-173">4. Specify actions.</span></span>
<span data-ttu-id="6c7de-174">自定义检测规则可以自动对查询返回的设备、文件或用户执行操作。</span><span class="sxs-lookup"><span data-stu-id="6c7de-174">Your custom detection rule can automatically take actions on devices, files, or users that are returned by the query.</span></span>

#### <a name="actions-on-devices"></a><span data-ttu-id="6c7de-175">对设备的操作</span><span class="sxs-lookup"><span data-stu-id="6c7de-175">Actions on devices</span></span>
<span data-ttu-id="6c7de-176">这些操作适用于查询结果 `DeviceId` 列中的设备：</span><span class="sxs-lookup"><span data-stu-id="6c7de-176">These actions are applied to devices in the `DeviceId` column of the query results:</span></span>
- <span data-ttu-id="6c7de-177">**隔离设备**— 使用 Microsoft Defender for Endpoint 应用完全网络隔离，阻止设备连接到任何应用程序或服务。</span><span class="sxs-lookup"><span data-stu-id="6c7de-177">**Isolate device**—uses Microsoft Defender for Endpoint to apply full network isolation, preventing the device from connecting to any application or service.</span></span> [<span data-ttu-id="6c7de-178">了解有关适用于终结点计算机隔离的 Microsoft Defender 有关详细信息</span><span class="sxs-lookup"><span data-stu-id="6c7de-178">Learn more about Microsoft Defender for Endpoint machine isolation</span></span>](/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#isolate-devices-from-the-network)
- <span data-ttu-id="6c7de-179">**收集调查包**- 在 ZIP 文件中收集设备信息。</span><span class="sxs-lookup"><span data-stu-id="6c7de-179">**Collect investigation package**—collects device information in a ZIP file.</span></span> [<span data-ttu-id="6c7de-180">了解有关适用于终结点的 Microsoft Defender 调查包的更多信息</span><span class="sxs-lookup"><span data-stu-id="6c7de-180">Learn more about the Microsoft Defender for Endpoint investigation package</span></span>](/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#collect-investigation-package-from-devices)
- <span data-ttu-id="6c7de-181">**运行防病毒扫描**- 在Windows Defender执行完全防病毒扫描</span><span class="sxs-lookup"><span data-stu-id="6c7de-181">**Run antivirus scan**—performs a full Windows Defender Antivirus scan on the device</span></span>
- <span data-ttu-id="6c7de-182">**启动调查**— 在 [设备上](m365d-autoir.md) 启动自动调查</span><span class="sxs-lookup"><span data-stu-id="6c7de-182">**Initiate investigation**—initiates an [automated investigation](m365d-autoir.md) on the device</span></span>
- <span data-ttu-id="6c7de-183">**限制应用** 执行 — 在设备上设置限制，以仅允许使用 Microsoft 颁发的证书签名的文件运行。</span><span class="sxs-lookup"><span data-stu-id="6c7de-183">**Restrict app execution**—sets restrictions on device to allow only files that are signed with a Microsoft-issued certificate to run.</span></span> [<span data-ttu-id="6c7de-184">详细了解 Microsoft Defender for Endpoint 的应用限制</span><span class="sxs-lookup"><span data-stu-id="6c7de-184">Learn more about app restrictions with Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/respond-machine-alerts#restrict-app-execution)

#### <a name="actions-on-files"></a><span data-ttu-id="6c7de-185">对文件的操作</span><span class="sxs-lookup"><span data-stu-id="6c7de-185">Actions on files</span></span>
<span data-ttu-id="6c7de-186">选中后，您可以选择对查询结果的、 、 或 列中 `SHA1` 的文件应用隔离 `InitiatingProcessSHA1` `SHA256` `InitiatingProcessSHA256` 文件操作。</span><span class="sxs-lookup"><span data-stu-id="6c7de-186">When selected, you can choose to apply the **Quarantine file** action on files in the `SHA1`, `InitiatingProcessSHA1`, `SHA256`, or `InitiatingProcessSHA256` column of the query results.</span></span> <span data-ttu-id="6c7de-187">此操作将文件从当前位置删除，并隔离副本。</span><span class="sxs-lookup"><span data-stu-id="6c7de-187">This action deletes the file from its current location and places a copy in quarantine.</span></span>

#### <a name="actions-on-users"></a><span data-ttu-id="6c7de-188">用户操作</span><span class="sxs-lookup"><span data-stu-id="6c7de-188">Actions on users</span></span>
<span data-ttu-id="6c7de-189">选中后 **，将针对** 查询结果的 、 或 列中的用户执行"将用户标记为已泄露 `AccountObjectId` `InitiatingProcessAccountObjectId` `RecipientObjectId` "操作。</span><span class="sxs-lookup"><span data-stu-id="6c7de-189">When selected, the **Mark user as compromised** action is taken on users in the `AccountObjectId`, `InitiatingProcessAccountObjectId`, or `RecipientObjectId` column of the query results.</span></span> <span data-ttu-id="6c7de-190">此操作将 Azure Active Directory 中的用户风险级别设置为"高"，从而触发相应的 [标识保护策略](/azure/active-directory/identity-protection/overview-identity-protection)。</span><span class="sxs-lookup"><span data-stu-id="6c7de-190">This action sets the users risk level to "high" in Azure Active Directory, triggering corresponding [identity protection policies](/azure/active-directory/identity-protection/overview-identity-protection).</span></span>

> [!NOTE]
> <span data-ttu-id="6c7de-191">Microsoft 365 Defender 当前不支持自定义检测规则的允许或阻止操作。</span><span class="sxs-lookup"><span data-stu-id="6c7de-191">The allow or block action for custom detection rules is currently not supported on Microsoft 365 Defender.</span></span>

### <a name="5-set-the-rule-scope"></a><span data-ttu-id="6c7de-192">5. 设置规则范围。</span><span class="sxs-lookup"><span data-stu-id="6c7de-192">5. Set the rule scope.</span></span>
<span data-ttu-id="6c7de-193">设置范围以指定规则涵盖的设备。</span><span class="sxs-lookup"><span data-stu-id="6c7de-193">Set the scope to specify which devices are covered by the rule.</span></span> <span data-ttu-id="6c7de-194">作用域影响检查设备的规则，而不影响仅检查邮箱和用户帐户或标识的规则。</span><span class="sxs-lookup"><span data-stu-id="6c7de-194">The scope influences rules that check devices and doesn't affect rules that check only mailboxes and user accounts or identities.</span></span>

<span data-ttu-id="6c7de-195">设置范围时，可以选择：</span><span class="sxs-lookup"><span data-stu-id="6c7de-195">When setting the scope, you can select:</span></span>

- <span data-ttu-id="6c7de-196">所有设备</span><span class="sxs-lookup"><span data-stu-id="6c7de-196">All devices</span></span>
- <span data-ttu-id="6c7de-197">特定设备组</span><span class="sxs-lookup"><span data-stu-id="6c7de-197">Specific device groups</span></span>

<span data-ttu-id="6c7de-198">将仅查询作用域中设备的数据。</span><span class="sxs-lookup"><span data-stu-id="6c7de-198">Only data from devices in scope will be queried.</span></span> <span data-ttu-id="6c7de-199">此外，将仅在这些设备上执行操作。</span><span class="sxs-lookup"><span data-stu-id="6c7de-199">Also, actions will be taken only on those devices.</span></span>

### <a name="6-review-and-turn-on-the-rule"></a><span data-ttu-id="6c7de-200">6. 查看并启用规则。</span><span class="sxs-lookup"><span data-stu-id="6c7de-200">6. Review and turn on the rule.</span></span>
<span data-ttu-id="6c7de-201">查看规则后，选择" **创建"** 以保存它。</span><span class="sxs-lookup"><span data-stu-id="6c7de-201">After reviewing the rule, select **Create** to save it.</span></span> <span data-ttu-id="6c7de-202">自定义检测规则会立即运行。</span><span class="sxs-lookup"><span data-stu-id="6c7de-202">The custom detection rule immediately runs.</span></span> <span data-ttu-id="6c7de-203">它根据配置的频率再次运行，以检查匹配项、生成警报以及执行响应操作。</span><span class="sxs-lookup"><span data-stu-id="6c7de-203">It runs again based on configured frequency to check for matches, generate alerts, and take response actions.</span></span>


>[!Important] 
><span data-ttu-id="6c7de-204">应定期检查自定义检测的效率和有效性。</span><span class="sxs-lookup"><span data-stu-id="6c7de-204">Custom detections should be regularly reviewed for efficiency and effectiveness.</span></span> <span data-ttu-id="6c7de-205">若要确保创建触发真实警报的检测，请花时间按照管理现有自定义检测规则中的步骤检查现有的 [自定义检测](#manage-existing-custom-detection-rules)。</span><span class="sxs-lookup"><span data-stu-id="6c7de-205">To make sure you are creating detections that trigger true alerts, take time to review your existing custom detections by following the steps in [Manage existing custom detection rules](#manage-existing-custom-detection-rules).</span></span> <br>  
<span data-ttu-id="6c7de-206">您可以保持对自定义检测的广泛性和特定性的控制，以便由自定义检测生成的任何假警报可能表示需要修改规则的某些参数。</span><span class="sxs-lookup"><span data-stu-id="6c7de-206">You maintain control over the broadness or specificity of your custom detections so any false alerts generated by custom detections might indicate a need to modify certain parameters of the rules.</span></span>


## <a name="manage-existing-custom-detection-rules"></a><span data-ttu-id="6c7de-207">管理现有自定义检测规则</span><span class="sxs-lookup"><span data-stu-id="6c7de-207">Manage existing custom detection rules</span></span>
<span data-ttu-id="6c7de-208">可以查看现有自定义检测规则的列表，检查其之前的运行，并查看已触发的警报。</span><span class="sxs-lookup"><span data-stu-id="6c7de-208">You can view the list of existing custom detection rules, check their previous runs, and review the alerts they have triggered.</span></span> <span data-ttu-id="6c7de-209">您还可以按需运行规则并对其进行修改。</span><span class="sxs-lookup"><span data-stu-id="6c7de-209">You can also run a rule on demand and modify it.</span></span>

>[!TIP]
> <span data-ttu-id="6c7de-210">通过警报和事件 API 提供由自定义检测引发警报。</span><span class="sxs-lookup"><span data-stu-id="6c7de-210">Alerts raised by custom detections are available over alerts and incident APIs.</span></span> <span data-ttu-id="6c7de-211">有关详细信息，请参阅支持的[Microsoft 365 Defender API。](api-supported.md)</span><span class="sxs-lookup"><span data-stu-id="6c7de-211">For more information, see [Supported Microsoft 365 Defender APIs](api-supported.md).</span></span>

### <a name="view-existing-rules"></a><span data-ttu-id="6c7de-212">查看现有规则</span><span class="sxs-lookup"><span data-stu-id="6c7de-212">View existing rules</span></span>

<span data-ttu-id="6c7de-213">若要查看所有现有的自定义检测规则，请导航到"**搜寻**  >  **自定义检测"。**</span><span class="sxs-lookup"><span data-stu-id="6c7de-213">To view all existing custom detection rules, navigate to **Hunting** > **Custom detections**.</span></span> <span data-ttu-id="6c7de-214">该页列出了包含以下运行信息的所有规则：</span><span class="sxs-lookup"><span data-stu-id="6c7de-214">The page lists all the rules with the following run information:</span></span>

- <span data-ttu-id="6c7de-215">**上次运行**- 上次运行规则以检查查询匹配并生成警报时</span><span class="sxs-lookup"><span data-stu-id="6c7de-215">**Last run**—when a rule was last run to check for query matches and generate alerts</span></span>
- <span data-ttu-id="6c7de-216">**上次运行状态**— 规则是否成功运行</span><span class="sxs-lookup"><span data-stu-id="6c7de-216">**Last run status**—whether a rule ran successfully</span></span>
- <span data-ttu-id="6c7de-217">**下一** 次运行 - 下一个计划运行</span><span class="sxs-lookup"><span data-stu-id="6c7de-217">**Next run**—the next scheduled run</span></span>
- <span data-ttu-id="6c7de-218">**状态**— 规则是已打开还是关闭</span><span class="sxs-lookup"><span data-stu-id="6c7de-218">**Status**—whether a rule has been turned on or off</span></span>

### <a name="view-rule-details-modify-rule-and-run-rule"></a><span data-ttu-id="6c7de-219">查看规则详细信息、修改规则并运行规则</span><span class="sxs-lookup"><span data-stu-id="6c7de-219">View rule details, modify rule, and run rule</span></span>

<span data-ttu-id="6c7de-220">若要查看有关自定义检测规则的综合信息，请转到"搜寻  >  **自定义检测**"，然后选择规则的名称。</span><span class="sxs-lookup"><span data-stu-id="6c7de-220">To view comprehensive information about a custom detection rule, go to **Hunting** > **Custom detections** and then select the name of rule.</span></span> <span data-ttu-id="6c7de-221">然后，您可以查看有关规则的常规信息，包括其运行状态和范围的信息。</span><span class="sxs-lookup"><span data-stu-id="6c7de-221">You can then view general information about the rule, including information its run status and scope.</span></span> <span data-ttu-id="6c7de-222">该页面还提供触发的警报和操作列表。</span><span class="sxs-lookup"><span data-stu-id="6c7de-222">The page also provides the list of triggered alerts and actions.</span></span>

<span data-ttu-id="6c7de-223">![自定义检测规则详细信息页](../../media/custom-detection-details.png)</span><span class="sxs-lookup"><span data-stu-id="6c7de-223">![Custom detection rule details page](../../media/custom-detection-details.png)</span></span><br>
<span data-ttu-id="6c7de-224">*自定义检测规则详细信息*</span><span class="sxs-lookup"><span data-stu-id="6c7de-224">*Custom detection rule details*</span></span>

<span data-ttu-id="6c7de-225">您还可以从此页对规则执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="6c7de-225">You can also take the following actions on the rule from this page:</span></span>

- <span data-ttu-id="6c7de-226">**运行** 立即运行规则。</span><span class="sxs-lookup"><span data-stu-id="6c7de-226">**Run**—run the rule immediately.</span></span> <span data-ttu-id="6c7de-227">这还会重置下次运行的间隔。</span><span class="sxs-lookup"><span data-stu-id="6c7de-227">This also resets the interval for the next run.</span></span>
- <span data-ttu-id="6c7de-228">**编辑** 在不更改查询的情况下修改规则</span><span class="sxs-lookup"><span data-stu-id="6c7de-228">**Edit**—modify the rule without changing the query</span></span>
- <span data-ttu-id="6c7de-229">**修改查询**— 在高级搜寻中编辑查询</span><span class="sxs-lookup"><span data-stu-id="6c7de-229">**Modify query**—edit the query in advanced hunting</span></span>
- <span data-ttu-id="6c7de-230">**打开**  / **关闭**- 启用规则或阻止其运行</span><span class="sxs-lookup"><span data-stu-id="6c7de-230">**Turn on** / **Turn off**—enable the rule or stop it from running</span></span>
- <span data-ttu-id="6c7de-231">**删除**- 关闭并删除规则</span><span class="sxs-lookup"><span data-stu-id="6c7de-231">**Delete**—turn off the rule and remove it</span></span>

### <a name="view-and-manage-triggered-alerts"></a><span data-ttu-id="6c7de-232">查看和管理触发的警报</span><span class="sxs-lookup"><span data-stu-id="6c7de-232">View and manage triggered alerts</span></span>

<span data-ttu-id="6c7de-233">在规则详细信息屏幕中 (搜索自定义检测  >    >  **[规则名称]**) ，转到触发的警报 ，其中列出了规则匹配项生成的警报。</span><span class="sxs-lookup"><span data-stu-id="6c7de-233">In the rule details screen (**Hunting** > **Custom detections** > **[Rule name]**), go to  **Triggered alerts**, which lists the alerts generated by matches to the rule.</span></span> <span data-ttu-id="6c7de-234">选择警报以查看有关它的详细信息，并执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="6c7de-234">Select an alert to view detailed information about it and take the following actions:</span></span>

- <span data-ttu-id="6c7de-235">通过将警报的状态和分类设置为 true 或 false (来管理警报) </span><span class="sxs-lookup"><span data-stu-id="6c7de-235">Manage the alert by setting its status and classification (true or false alert)</span></span>
- <span data-ttu-id="6c7de-236">将警报链接到事件</span><span class="sxs-lookup"><span data-stu-id="6c7de-236">Link the alert to an incident</span></span>
- <span data-ttu-id="6c7de-237">运行触发高级搜寻警报的查询</span><span class="sxs-lookup"><span data-stu-id="6c7de-237">Run the query that triggered the alert on advanced hunting</span></span>

### <a name="review-actions"></a><span data-ttu-id="6c7de-238">查看操作</span><span class="sxs-lookup"><span data-stu-id="6c7de-238">Review actions</span></span>
<span data-ttu-id="6c7de-239">在规则详细信息屏幕中 (搜索自定义检测  >    >  **[规则名称]**) ，转到触发的操作，其中列出了基于规则匹配项采取的操作。</span><span class="sxs-lookup"><span data-stu-id="6c7de-239">In the rule details screen (**Hunting** > **Custom detections** > **[Rule name]**), go to **Triggered actions**, which lists the actions taken based on matches to the rule.</span></span>

>[!TIP]
><span data-ttu-id="6c7de-240">若要快速查看信息并针对表中的项目采取操作，请使用表格左侧的选择列 [&#10003;] 。</span><span class="sxs-lookup"><span data-stu-id="6c7de-240">To quickly view information and take action on an item in a table, use the selection column [&#10003;] at the left of the table.</span></span>

>[!NOTE]
><span data-ttu-id="6c7de-241">本文中的某些列在 Microsoft Defender for Endpoint 中可能不可用。</span><span class="sxs-lookup"><span data-stu-id="6c7de-241">Some columns in this article might not be available in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="6c7de-242">[打开 Microsoft 365 Defender](m365d-enable.md) 以使用更多数据源搜寻威胁。</span><span class="sxs-lookup"><span data-stu-id="6c7de-242">[Turn on Microsoft 365 Defender](m365d-enable.md) to hunt for threats using more data sources.</span></span> <span data-ttu-id="6c7de-243">你可以按照从 Microsoft Defender for Endpoint 迁移高级搜寻查询中的步骤将高级搜寻工作流从 [Microsoft Defender for Endpoint](advanced-hunting-migrate-from-mde.md)移动到 Microsoft 365 Defender。</span><span class="sxs-lookup"><span data-stu-id="6c7de-243">You can move your advanced hunting workflows from Microsoft Defender for Endpoint to Microsoft 365 Defender by following the steps in [Migrate advanced hunting queries from Microsoft Defender for Endpoint](advanced-hunting-migrate-from-mde.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="6c7de-244">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6c7de-244">See also</span></span>
- [<span data-ttu-id="6c7de-245">自定义检测概述</span><span class="sxs-lookup"><span data-stu-id="6c7de-245">Custom detections overview</span></span>](custom-detections-overview.md)
- [<span data-ttu-id="6c7de-246">高级搜寻概述</span><span class="sxs-lookup"><span data-stu-id="6c7de-246">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="6c7de-247">了解高级搜寻查询语言</span><span class="sxs-lookup"><span data-stu-id="6c7de-247">Learn the advanced hunting query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="6c7de-248">从 Microsoft Defender for Endpoint 迁移高级搜寻查询</span><span class="sxs-lookup"><span data-stu-id="6c7de-248">Migrate advanced hunting queries from Microsoft Defender for Endpoint</span></span>](advanced-hunting-migrate-from-mde.md)
