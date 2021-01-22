---
title: 在 Microsoft 365 Defender 中创建自定义检测规则
description: 了解如何基于高级搜寻查询创建和管理自定义检测规则
keywords: 高级搜寻， 威胁搜寻， 网络威胁搜寻， Microsoft 威胁防护， microsoft 365， mtp， m365， 搜索， 查询， 遥测， 自定义检测， 规则， 架构， kusto， microsoft 365， Microsoft 威胁防护， RBAC， 权限， Microsoft Defender ATP
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 8c7e47e66f9e5543cc122c5b5154207cae836d2a
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932918"
---
# <a name="create-and-manage-custom-detections-rules"></a><span data-ttu-id="0d936-104">创建和管理自定义检测规则</span><span class="sxs-lookup"><span data-stu-id="0d936-104">Create and manage custom detections rules</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="0d936-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="0d936-105">**Applies to:**</span></span>
- <span data-ttu-id="0d936-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0d936-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="0d936-107">自定义检测规则是可以使用高级搜寻查询设计和 [调整](advanced-hunting-overview.md) 的规则。</span><span class="sxs-lookup"><span data-stu-id="0d936-107">Custom detection rules are rules you can design and tweak using [advanced hunting](advanced-hunting-overview.md) queries.</span></span> <span data-ttu-id="0d936-108">通过这些规则，您可以主动监视各种事件和系统状态，包括可疑的泄露活动和错误配置的终结点。</span><span class="sxs-lookup"><span data-stu-id="0d936-108">These rules let you proactively monitor various events and system states, including suspected breach activity and misconfigured endpoints.</span></span> <span data-ttu-id="0d936-109">你可以将它们设置为定期运行，生成警报，并随时执行响应操作。</span><span class="sxs-lookup"><span data-stu-id="0d936-109">You can set them to run at regular intervals, generating alerts and taking response actions whenever there are matches.</span></span>

## <a name="required-permissions-for-managing-custom-detections"></a><span data-ttu-id="0d936-110">管理自定义检测所需的权限</span><span class="sxs-lookup"><span data-stu-id="0d936-110">Required permissions for managing custom detections</span></span>

<span data-ttu-id="0d936-111">若要管理自定义检测，需要分配以下角色之一：</span><span class="sxs-lookup"><span data-stu-id="0d936-111">To manage custom detections, you need to be assigned one of these roles:</span></span>

- <span data-ttu-id="0d936-112">**安全管理员**- 具有 [此 Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) 角色的用户可以在 Microsoft 365 安全中心和其他门户和服务中管理安全设置。</span><span class="sxs-lookup"><span data-stu-id="0d936-112">**Security administrator**—Users with this [Azure Active Directory role](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) can manage security settings in Microsoft 365 security center and other portals and services.</span></span>

- <span data-ttu-id="0d936-113">**安全操作员**— 具有 [此 Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) 角色的用户可以管理警报，并且对与安全相关的功能（包括 Microsoft 365 安全中心内的所有信息）具有全局只读访问权限。</span><span class="sxs-lookup"><span data-stu-id="0d936-113">**Security operator**—Users with this [Azure Active Directory role](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) can manage alerts and have global read-only access to security-related features, including all information in Microsoft 365 security center.</span></span> <span data-ttu-id="0d936-114">只有在 Microsoft Defender for Endpoint 中关闭基于角色的访问控制 (RBAC) ，此角色才足以管理自定义检测。</span><span class="sxs-lookup"><span data-stu-id="0d936-114">This role is sufficient for managing custom detections only if role-based access control (RBAC) is turned off in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="0d936-115">如果已配置 RBAC，则还需要 Defender for Endpoint **的** 安全设置权限。</span><span class="sxs-lookup"><span data-stu-id="0d936-115">If you have RBAC configured, you also need the **manage security settings** permission for Defender for Endpoint.</span></span>

<span data-ttu-id="0d936-116">若要管理所需的权限，全局 **管理员可以** ：</span><span class="sxs-lookup"><span data-stu-id="0d936-116">To manage required permissions, a **global administrator** can:</span></span>

- <span data-ttu-id="0d936-117">在 **Microsoft** [365](https://admin.microsoft.com/)管理 **中心的**"角色安全管理员"下分配 **安全管理员或**  >  **安全操作员角色**。</span><span class="sxs-lookup"><span data-stu-id="0d936-117">Assign the **security administrator** or **security operator** role in [Microsoft 365 admin center](https://admin.microsoft.com/) under **Roles** > **Security admin**.</span></span>
- <span data-ttu-id="0d936-118">在"设置权限角色"下检查 Microsoft Defender 安全中心中 [适用于终结点的 Microsoft Defender](https://securitycenter.windows.com/)的 RBAC  >    >  **设置**。</span><span class="sxs-lookup"><span data-stu-id="0d936-118">Check RBAC settings for Microsoft Defender for Endpoint in [Microsoft Defender Security Center](https://securitycenter.windows.com/) under **Settings** > **Permissions** > **Roles**.</span></span> <span data-ttu-id="0d936-119">选择相应的角色以分配 **管理安全设置** 权限。</span><span class="sxs-lookup"><span data-stu-id="0d936-119">Select the corresponding role to assign the **manage security settings** permission.</span></span>

> [!NOTE]
> <span data-ttu-id="0d936-120">若要管理自定义检测，如果RBAC 已打开，安全操作员将需要在 Microsoft Defender for Endpoint 中管理安全设置权限。</span><span class="sxs-lookup"><span data-stu-id="0d936-120">To manage custom detections, **security operators** will need the **manage security settings** permission in Microsoft Defender for Endpoint if RBAC is turned on.</span></span>

## <a name="create-a-custom-detection-rule"></a><span data-ttu-id="0d936-121">创建自定义检测规则</span><span class="sxs-lookup"><span data-stu-id="0d936-121">Create a custom detection rule</span></span>
### <a name="1-prepare-the-query"></a><span data-ttu-id="0d936-122">1. 准备查询。</span><span class="sxs-lookup"><span data-stu-id="0d936-122">1. Prepare the query.</span></span>

<span data-ttu-id="0d936-123">在 Microsoft 365 安全中心，转到" **高级** 搜寻"并选择现有查询或创建新查询。</span><span class="sxs-lookup"><span data-stu-id="0d936-123">In Microsoft 365 security center, go to **Advanced hunting** and select an existing query or create a new query.</span></span> <span data-ttu-id="0d936-124">使用新查询时，运行查询以识别错误并了解可能的结果。</span><span class="sxs-lookup"><span data-stu-id="0d936-124">When using a new query, run the query to identify errors and understand possible results.</span></span>

>[!IMPORTANT]
><span data-ttu-id="0d936-125">为了防止服务返回过多警报，每个规则都限制为每次运行时仅生成 100 个警报。</span><span class="sxs-lookup"><span data-stu-id="0d936-125">To prevent the service from returning too many alerts, each rule is limited to generating only 100 alerts whenever it runs.</span></span> <span data-ttu-id="0d936-126">在创建规则之前，请调整查询以避免对正常的日常活动发出警报。</span><span class="sxs-lookup"><span data-stu-id="0d936-126">Before creating a rule, tweak your query to avoid alerting for normal, day-to-day activity.</span></span>


#### <a name="required-columns-in-the-query-results"></a><span data-ttu-id="0d936-127">查询结果中的必需列</span><span class="sxs-lookup"><span data-stu-id="0d936-127">Required columns in the query results</span></span>
<span data-ttu-id="0d936-128">若要创建自定义检测规则，查询必须返回以下列：</span><span class="sxs-lookup"><span data-stu-id="0d936-128">To create a custom detection rule, the query must return the following columns:</span></span>

- <span data-ttu-id="0d936-129">`Timestamp`—用于设置生成的警报的时间戳</span><span class="sxs-lookup"><span data-stu-id="0d936-129">`Timestamp`—used to set the timestamp for generated alerts</span></span>
- <span data-ttu-id="0d936-130">`ReportId`— 启用对原始记录的查找</span><span class="sxs-lookup"><span data-stu-id="0d936-130">`ReportId`—enables lookups for the original records</span></span>
- <span data-ttu-id="0d936-131">标识特定设备、用户或邮箱的以下列之一：</span><span class="sxs-lookup"><span data-stu-id="0d936-131">One of the following columns that identify specific devices, users, or mailboxes:</span></span>
    - `DeviceId`
    - `DeviceName`
    - `RemoteDeviceName`
    - `RecipientEmailAddress`
    - <span data-ttu-id="0d936-132">`SenderFromAddress` (信封发件人或Return-Path地址) </span><span class="sxs-lookup"><span data-stu-id="0d936-132">`SenderFromAddress` (envelope sender or Return-Path address)</span></span>
    - <span data-ttu-id="0d936-133">`SenderMailFromAddress` (客户端服务器显示) </span><span class="sxs-lookup"><span data-stu-id="0d936-133">`SenderMailFromAddress` (sender address displayed by email client)</span></span>
    - `RecipientObjectId`
    - `AccountObjectId`
    - `AccountSid`
    - `AccountUpn`
    - `InitiatingProcessAccountSid`
    - `InitiatingProcessAccountUpn`
    - `InitiatingProcessAccountObjectId`

>[!NOTE]
><span data-ttu-id="0d936-134">当新表添加到高级搜寻架构时，将添加对其他 [实体的支持](advanced-hunting-schema-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="0d936-134">Support for additional entities will be added as new tables are added to the [advanced hunting schema](advanced-hunting-schema-tables.md).</span></span>

<span data-ttu-id="0d936-135">简单查询（如不使用 or 运算符自定义或聚合结果的查询） `project` `summarize` 通常返回这些常用列。</span><span class="sxs-lookup"><span data-stu-id="0d936-135">Simple queries, such as those that don't use the `project` or `summarize` operator to customize or aggregate results, typically return these common columns.</span></span>

<span data-ttu-id="0d936-136">有多种方式可以确保更复杂的查询返回这些列。</span><span class="sxs-lookup"><span data-stu-id="0d936-136">There are various ways to ensure more complex queries return these columns.</span></span> <span data-ttu-id="0d936-137">例如，如果你更希望按列下的实体进行聚合和计数，你仍然可以返回它，并且通过从涉及每个唯一的最近事件获取 `DeviceId` `Timestamp` `ReportId` 它 `DeviceId` 。</span><span class="sxs-lookup"><span data-stu-id="0d936-137">For example, if you prefer to aggregate and count by entity under a column such as `DeviceId`, you can still return `Timestamp` and `ReportId` by getting it from the most recent event involving each unique `DeviceId`.</span></span>

<span data-ttu-id="0d936-138">下面的示例查询对使用防病毒检测 () 设备数进行计数，并使用此计数仅查找检测次数超过 `DeviceId` 五的设备。</span><span class="sxs-lookup"><span data-stu-id="0d936-138">The sample query below counts the number of unique devices (`DeviceId`) with antivirus detections and uses this count to find only the devices with more than five detections.</span></span> <span data-ttu-id="0d936-139">为了返回最新 `Timestamp` 和相应的值 `ReportId` ，它将 `summarize` 运算符与 `arg_max` 函数一同使用。</span><span class="sxs-lookup"><span data-stu-id="0d936-139">To return the latest `Timestamp` and the corresponding `ReportId`, it uses the `summarize` operator with the `arg_max` function.</span></span>

```kusto
DeviceEvents
| where Timestamp > ago(1d)
| where ActionType == "AntivirusDetection"
| summarize (Timestamp, ReportId)=arg_max(Timestamp, ReportId), count() by DeviceId
| where count_ > 5
```

> [!TIP]
> <span data-ttu-id="0d936-140">为了提升查询性能，请设置与规则预期运行频率相匹配的时间筛选器。</span><span class="sxs-lookup"><span data-stu-id="0d936-140">For better query performance, set a time filter that matches your intended run frequency for the rule.</span></span> <span data-ttu-id="0d936-141">由于运行频率最低是 _每 24 小时_ 一次，因此对过去一天的筛选将覆盖所有新数据。</span><span class="sxs-lookup"><span data-stu-id="0d936-141">Since the least frequent run is _every 24 hours_, filtering for the past day will cover all new data.</span></span>

### <a name="2-create-new-rule-and-provide-alert-details"></a><span data-ttu-id="0d936-142">2. 创建新规则并提供警报详细信息。</span><span class="sxs-lookup"><span data-stu-id="0d936-142">2. Create new rule and provide alert details.</span></span>

<span data-ttu-id="0d936-143">使用查询编辑器中的查询，选择 **"创建检测规则** "并指定以下警报详细信息：</span><span class="sxs-lookup"><span data-stu-id="0d936-143">With the query in the query editor, select **Create detection rule** and specify the following alert details:</span></span>

- <span data-ttu-id="0d936-144">**检测名称**- 检测规则的名称</span><span class="sxs-lookup"><span data-stu-id="0d936-144">**Detection name**—name of the detection rule</span></span>
- <span data-ttu-id="0d936-145">**频率**— 运行查询和采取措施的时间间隔。</span><span class="sxs-lookup"><span data-stu-id="0d936-145">**Frequency**—interval for running the query and taking action.</span></span> [<span data-ttu-id="0d936-146">请参阅下面的其他指南</span><span class="sxs-lookup"><span data-stu-id="0d936-146">See additional guidance below</span></span>](#rule-frequency)
- <span data-ttu-id="0d936-147">**警报标题**- 显示由规则触发的警报的标题</span><span class="sxs-lookup"><span data-stu-id="0d936-147">**Alert title**—title displayed with alerts triggered by the rule</span></span>
- <span data-ttu-id="0d936-148">**严重性**- 规则标识的组件或活动的潜在风险</span><span class="sxs-lookup"><span data-stu-id="0d936-148">**Severity**—potential risk of the component or activity identified by the rule</span></span>
- <span data-ttu-id="0d936-149">**类别**— 规则标识的威胁组件或活动</span><span class="sxs-lookup"><span data-stu-id="0d936-149">**Category**—threat component or activity identified by the rule</span></span>
- <span data-ttu-id="0d936-150">**MITRE ATT&CK** 技术 - 一种或多种攻击技术，由 [MITRE ATT](https://attack.mitre.org/)和 CK 框架中记录的规则&攻击技术。</span><span class="sxs-lookup"><span data-stu-id="0d936-150">**MITRE ATT&CK techniques**—one or more attack techniques identified by the rule as documented in the [MITRE ATT&CK framework](https://attack.mitre.org/).</span></span> <span data-ttu-id="0d936-151">本部分对某些警报类别（包括恶意软件、勒索软件、可疑活动和不需要的软件）隐藏</span><span class="sxs-lookup"><span data-stu-id="0d936-151">This section is hidden for certain alert categories, including malware, ransomware, suspicious activity, and unwanted software</span></span>
- <span data-ttu-id="0d936-152">**说明**- 有关规则标识的组件或活动详细信息</span><span class="sxs-lookup"><span data-stu-id="0d936-152">**Description**—more information about the component or activity identified by the rule</span></span> 
- <span data-ttu-id="0d936-153">**建议的操作**- 响应者为响应警报可能执行的其他操作</span><span class="sxs-lookup"><span data-stu-id="0d936-153">**Recommended actions**—additional actions that responders might take in response to an alert</span></span>

#### <a name="rule-frequency"></a><span data-ttu-id="0d936-154">规则频率</span><span class="sxs-lookup"><span data-stu-id="0d936-154">Rule frequency</span></span>
<span data-ttu-id="0d936-155">保存或编辑新规则时，它将运行并检查过去 30 天的数据中的匹配项。</span><span class="sxs-lookup"><span data-stu-id="0d936-155">When you save or edit a new rule, it runs and checks for matches from the past 30 days of data.</span></span> <span data-ttu-id="0d936-156">然后，规则以固定间隔再次运行，并基于你选择的频率应用回发持续时间：</span><span class="sxs-lookup"><span data-stu-id="0d936-156">The rule then runs again at fixed intervals, applying a lookback duration based on the frequency you choose:</span></span>

- <span data-ttu-id="0d936-157">**每 24 小时** 运行一次，每 24 小时运行一次，检查过去 30 天的数据</span><span class="sxs-lookup"><span data-stu-id="0d936-157">**Every 24 hours**—runs every 24 hours, checking data from the past 30 days</span></span>
- <span data-ttu-id="0d936-158">**每 12 小时** 运行一次 ，每 12 小时运行一次，检查过去 24 小时的数据</span><span class="sxs-lookup"><span data-stu-id="0d936-158">**Every 12 hours**—runs every 12 hours, checking data from the past 24 hours</span></span>
- <span data-ttu-id="0d936-159">**每 3 小时** 运行一次，每 3 小时运行一次，检查过去 6 小时的数据</span><span class="sxs-lookup"><span data-stu-id="0d936-159">**Every 3 hours**—runs every 3 hours, checking data from the past 6 hours</span></span>
- <span data-ttu-id="0d936-160">**每小时** 运行一次，检查过去 2 小时的数据</span><span class="sxs-lookup"><span data-stu-id="0d936-160">**Every hour**—runs hourly, checking data from the past 2 hours</span></span>

>[!TIP]
> <span data-ttu-id="0d936-161">将查询中的时间筛选器与回发持续时间相匹配。</span><span class="sxs-lookup"><span data-stu-id="0d936-161">Match the time filters in your query with the lookback duration.</span></span> <span data-ttu-id="0d936-162">将忽略回发持续时间之外的结果。</span><span class="sxs-lookup"><span data-stu-id="0d936-162">Results outside of the lookback duration are ignored.</span></span>  

<span data-ttu-id="0d936-163">选择与要监视检测的频率相匹配的频率。</span><span class="sxs-lookup"><span data-stu-id="0d936-163">Select the frequency that matches how closely you want to monitor detections.</span></span> <span data-ttu-id="0d936-164">考虑组织响应警报的能力。</span><span class="sxs-lookup"><span data-stu-id="0d936-164">Consider your organization's capacity to respond to the alerts.</span></span>

### <a name="3-choose-the-impacted-entities"></a><span data-ttu-id="0d936-165">3. 选择受到影响的实体。</span><span class="sxs-lookup"><span data-stu-id="0d936-165">3. Choose the impacted entities.</span></span>
<span data-ttu-id="0d936-166">在查询结果中标识希望找到主要受影响或受影响的实体的列。</span><span class="sxs-lookup"><span data-stu-id="0d936-166">Identify the columns in your query results where you expect to find the main affected or impacted entity.</span></span> <span data-ttu-id="0d936-167">例如，查询可能返回发件人 (`SenderFromAddress` 或) `SenderMailFromAddress` 收件人 () `RecipientEmailAddress` 地址。</span><span class="sxs-lookup"><span data-stu-id="0d936-167">For example, a query might return sender (`SenderFromAddress` or `SenderMailFromAddress`) and recipient (`RecipientEmailAddress`) addresses.</span></span> <span data-ttu-id="0d936-168">确定哪些列表示主要影响的实体可帮助服务聚合相关警报、关联事件和目标响应操作。</span><span class="sxs-lookup"><span data-stu-id="0d936-168">Identifying which of these columns represent the main impacted entity helps the service aggregate relevant alerts, correlate incidents, and target response actions.</span></span>

<span data-ttu-id="0d936-169">只能为邮箱、用户或设备 (实体类型选择一) 。</span><span class="sxs-lookup"><span data-stu-id="0d936-169">You can select only one column for each entity type (mailbox, user, or device).</span></span> <span data-ttu-id="0d936-170">无法选择查询未返回的列。</span><span class="sxs-lookup"><span data-stu-id="0d936-170">Columns that are not returned by your query can't be selected.</span></span>

### <a name="4-specify-actions"></a><span data-ttu-id="0d936-171">4. 指定操作。</span><span class="sxs-lookup"><span data-stu-id="0d936-171">4. Specify actions.</span></span>
<span data-ttu-id="0d936-172">自定义检测规则可以自动对查询返回的设备、文件或用户执行操作。</span><span class="sxs-lookup"><span data-stu-id="0d936-172">Your custom detection rule can automatically take actions on devices, files, or users that are returned by the query.</span></span>

#### <a name="actions-on-devices"></a><span data-ttu-id="0d936-173">对设备的操作</span><span class="sxs-lookup"><span data-stu-id="0d936-173">Actions on devices</span></span>
<span data-ttu-id="0d936-174">这些操作将应用于查询结果 `DeviceId` 列中的设备：</span><span class="sxs-lookup"><span data-stu-id="0d936-174">These actions are applied to devices in the `DeviceId` column of the query results:</span></span>
- <span data-ttu-id="0d936-175">**隔离设备**— 使用 Microsoft Defender for Endpoint 应用完全网络隔离，阻止设备连接到任何应用程序或服务。</span><span class="sxs-lookup"><span data-stu-id="0d936-175">**Isolate device**—uses Microsoft Defender for Endpoint to apply full network isolation, preventing the device from connecting to any application or service.</span></span> [<span data-ttu-id="0d936-176">了解有关适用于终结点计算机隔离的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="0d936-176">Learn more about Microsoft Defender for Endpoint machine isolation</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#isolate-devices-from-the-network)
- <span data-ttu-id="0d936-177">**收集调查包**— 在 ZIP 文件中收集设备信息。</span><span class="sxs-lookup"><span data-stu-id="0d936-177">**Collect investigation package**—collects device information in a ZIP file.</span></span> [<span data-ttu-id="0d936-178">详细了解 Microsoft Defender for Endpoint 调查包</span><span class="sxs-lookup"><span data-stu-id="0d936-178">Learn more about the Microsoft Defender for Endpoint investigation package</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#collect-investigation-package-from-devices)
- <span data-ttu-id="0d936-179">**运行防病毒扫描**- 在设备上执行Windows Defender防病毒扫描</span><span class="sxs-lookup"><span data-stu-id="0d936-179">**Run antivirus scan**—performs a full Windows Defender Antivirus scan on the device</span></span>
- <span data-ttu-id="0d936-180">**启动调查**— 在 [设备上](mtp-autoir.md) 启动自动调查</span><span class="sxs-lookup"><span data-stu-id="0d936-180">**Initiate investigation**—initiates an [automated investigation](mtp-autoir.md) on the device</span></span>
- <span data-ttu-id="0d936-181">**限制应用** 执行 — 在设备上设置限制以仅允许使用 Microsoft 颁发的证书签名的文件运行。</span><span class="sxs-lookup"><span data-stu-id="0d936-181">**Restrict app execution**—sets restrictions on device to allow only files that are signed with a Microsoft-issued certificate to run.</span></span> [<span data-ttu-id="0d936-182">详细了解 Microsoft Defender for Endpoint 的应用限制</span><span class="sxs-lookup"><span data-stu-id="0d936-182">Learn more about app restrictions with Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#restrict-app-execution)

#### <a name="actions-on-files"></a><span data-ttu-id="0d936-183">对文件的操作</span><span class="sxs-lookup"><span data-stu-id="0d936-183">Actions on files</span></span>
<span data-ttu-id="0d936-184">选择后，可以选择对查询结果的、 或列中的文件应用隔离 `SHA1` `InitiatingProcessSHA1` `SHA256` `InitiatingProcessSHA256` 文件操作。</span><span class="sxs-lookup"><span data-stu-id="0d936-184">When selected, you can choose to apply the **Quarantine file** action on files in the `SHA1`, `InitiatingProcessSHA1`, `SHA256`, or `InitiatingProcessSHA256` column of the query results.</span></span> <span data-ttu-id="0d936-185">此操作将从文件的当前位置删除文件，并隔离副本。</span><span class="sxs-lookup"><span data-stu-id="0d936-185">This action deletes the file from its current location and places a copy in quarantine.</span></span>

#### <a name="actions-on-users"></a><span data-ttu-id="0d936-186">用户操作</span><span class="sxs-lookup"><span data-stu-id="0d936-186">Actions on users</span></span>
<span data-ttu-id="0d936-187">选中后， **将用户标记为** 已泄露，将针对查询结果的 `AccountObjectId` 、 `InitiatingProcessAccountObjectId` 或 `RecipientObjectId` 列中的用户执行该操作。</span><span class="sxs-lookup"><span data-stu-id="0d936-187">When selected, the **Mark user as compromised** action is taken on users in the `AccountObjectId`, `InitiatingProcessAccountObjectId`, or `RecipientObjectId` column of the query results.</span></span> <span data-ttu-id="0d936-188">此操作将 Azure Active Directory 中的用户风险级别设置为"高"，从而触发相应的 [标识保护策略](https://docs.microsoft.com/azure/active-directory/identity-protection/overview-identity-protection)。</span><span class="sxs-lookup"><span data-stu-id="0d936-188">This action sets the users risk level to "high" in Azure Active Directory, triggering corresponding [identity protection policies](https://docs.microsoft.com/azure/active-directory/identity-protection/overview-identity-protection).</span></span>

> [!NOTE]
> <span data-ttu-id="0d936-189">Microsoft 365 Defender 当前不支持自定义检测规则的允许或阻止操作。</span><span class="sxs-lookup"><span data-stu-id="0d936-189">The allow or block action for custom detection rules is currently not supported on Microsoft 365 Defender.</span></span>

### <a name="5-set-the-rule-scope"></a><span data-ttu-id="0d936-190">5. 设置规则范围。</span><span class="sxs-lookup"><span data-stu-id="0d936-190">5. Set the rule scope.</span></span>
<span data-ttu-id="0d936-191">设置范围以指定规则涵盖哪些设备。</span><span class="sxs-lookup"><span data-stu-id="0d936-191">Set the scope to specify which devices are covered by the rule.</span></span> <span data-ttu-id="0d936-192">作用域影响检查设备的规则，而不影响仅检查邮箱和用户帐户或标识的规则。</span><span class="sxs-lookup"><span data-stu-id="0d936-192">The scope influences rules that check devices and doesn't affect rules that check only mailboxes and user accounts or identities.</span></span>

<span data-ttu-id="0d936-193">设置范围时，可以选择：</span><span class="sxs-lookup"><span data-stu-id="0d936-193">When setting the scope, you can select:</span></span>

- <span data-ttu-id="0d936-194">所有设备</span><span class="sxs-lookup"><span data-stu-id="0d936-194">All devices</span></span>
- <span data-ttu-id="0d936-195">特定设备组</span><span class="sxs-lookup"><span data-stu-id="0d936-195">Specific device groups</span></span>

<span data-ttu-id="0d936-196">将仅查询范围内设备的数据。</span><span class="sxs-lookup"><span data-stu-id="0d936-196">Only data from devices in scope will be queried.</span></span> <span data-ttu-id="0d936-197">此外，仅对这些设备执行操作。</span><span class="sxs-lookup"><span data-stu-id="0d936-197">Also, actions will be taken only on those devices.</span></span>

### <a name="6-review-and-turn-on-the-rule"></a><span data-ttu-id="0d936-198">6. 查看并打开规则。</span><span class="sxs-lookup"><span data-stu-id="0d936-198">6. Review and turn on the rule.</span></span>
<span data-ttu-id="0d936-199">查看规则后，选择 **"创建"** 以保存它。</span><span class="sxs-lookup"><span data-stu-id="0d936-199">After reviewing the rule, select **Create** to save it.</span></span> <span data-ttu-id="0d936-200">自定义检测规则会立即运行。</span><span class="sxs-lookup"><span data-stu-id="0d936-200">The custom detection rule immediately runs.</span></span> <span data-ttu-id="0d936-201">它将基于配置的频率再次运行，以检查匹配项、生成警报以及执行响应操作。</span><span class="sxs-lookup"><span data-stu-id="0d936-201">It runs again based on configured frequency to check for matches, generate alerts, and take response actions.</span></span>

## <a name="manage-existing-custom-detection-rules"></a><span data-ttu-id="0d936-202">管理现有自定义检测规则</span><span class="sxs-lookup"><span data-stu-id="0d936-202">Manage existing custom detection rules</span></span>
<span data-ttu-id="0d936-203">您可以查看现有自定义检测规则的列表，检查其之前的运行，并查看已触发的警报。</span><span class="sxs-lookup"><span data-stu-id="0d936-203">You can view the list of existing custom detection rules, check their previous runs, and review the alerts they have triggered.</span></span> <span data-ttu-id="0d936-204">您还可以按需运行规则并对其进行修改。</span><span class="sxs-lookup"><span data-stu-id="0d936-204">You can also run a rule on demand and modify it.</span></span>

### <a name="view-existing-rules"></a><span data-ttu-id="0d936-205">查看现有规则</span><span class="sxs-lookup"><span data-stu-id="0d936-205">View existing rules</span></span>

<span data-ttu-id="0d936-206">若要查看所有现有的自定义检测规则，请导航到 **"搜寻**  >  **自定义检测"。**</span><span class="sxs-lookup"><span data-stu-id="0d936-206">To view all existing custom detection rules, navigate to **Hunting** > **Custom detections**.</span></span> <span data-ttu-id="0d936-207">该页列出了具有以下运行信息的所有规则：</span><span class="sxs-lookup"><span data-stu-id="0d936-207">The page lists all the rules with the following run information:</span></span>

- <span data-ttu-id="0d936-208">**上次运行**- 上次运行规则以检查查询匹配项并生成警报时</span><span class="sxs-lookup"><span data-stu-id="0d936-208">**Last run**—when a rule was last run to check for query matches and generate alerts</span></span>
- <span data-ttu-id="0d936-209">**上次运行状态**— 规则是否成功运行</span><span class="sxs-lookup"><span data-stu-id="0d936-209">**Last run status**—whether a rule ran successfully</span></span>
- <span data-ttu-id="0d936-210">**下一次** 运行 - 下一次计划运行</span><span class="sxs-lookup"><span data-stu-id="0d936-210">**Next run**—the next scheduled run</span></span>
- <span data-ttu-id="0d936-211">**状态**— 规则是已打开还是关闭</span><span class="sxs-lookup"><span data-stu-id="0d936-211">**Status**—whether a rule has been turned on or off</span></span>

### <a name="view-rule-details-modify-rule-and-run-rule"></a><span data-ttu-id="0d936-212">查看规则详细信息、修改规则并运行规则</span><span class="sxs-lookup"><span data-stu-id="0d936-212">View rule details, modify rule, and run rule</span></span>

<span data-ttu-id="0d936-213">若要查看有关自定义检测规则的综合信息，请转到"搜寻  >  **自定义检测**"，然后选择规则的名称。</span><span class="sxs-lookup"><span data-stu-id="0d936-213">To view comprehensive information about a custom detection rule, go to **Hunting** > **Custom detections** and then select the name of rule.</span></span> <span data-ttu-id="0d936-214">然后，您可以查看有关规则的常规信息，包括其运行状态和范围信息。</span><span class="sxs-lookup"><span data-stu-id="0d936-214">You can then view general information about the rule, including information its run status and scope.</span></span> <span data-ttu-id="0d936-215">该页还提供触发的警报和操作的列表。</span><span class="sxs-lookup"><span data-stu-id="0d936-215">The page also provides the list of triggered alerts and actions.</span></span>

<span data-ttu-id="0d936-216">![自定义检测规则详细信息页](../../media/custom-detection-details.png)</span><span class="sxs-lookup"><span data-stu-id="0d936-216">![Custom detection rule details page](../../media/custom-detection-details.png)</span></span><br>
<span data-ttu-id="0d936-217">*自定义检测规则详细信息*</span><span class="sxs-lookup"><span data-stu-id="0d936-217">*Custom detection rule details*</span></span>

<span data-ttu-id="0d936-218">您还可以从此页面对规则执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="0d936-218">You can also take the following actions on the rule from this page:</span></span>

- <span data-ttu-id="0d936-219">**运行**-立即运行规则。</span><span class="sxs-lookup"><span data-stu-id="0d936-219">**Run**—run the rule immediately.</span></span> <span data-ttu-id="0d936-220">这还会重置下一次运行的时间间隔。</span><span class="sxs-lookup"><span data-stu-id="0d936-220">This also resets the interval for the next run.</span></span>
- <span data-ttu-id="0d936-221">**编辑**- 在不更改查询的情况下修改规则</span><span class="sxs-lookup"><span data-stu-id="0d936-221">**Edit**—modify the rule without changing the query</span></span>
- <span data-ttu-id="0d936-222">**修改查询**— 在高级搜寻中编辑查询</span><span class="sxs-lookup"><span data-stu-id="0d936-222">**Modify query**—edit the query in advanced hunting</span></span>
- <span data-ttu-id="0d936-223">**打开**  / **关闭**- 启用规则或阻止其运行</span><span class="sxs-lookup"><span data-stu-id="0d936-223">**Turn on** / **Turn off**—enable the rule or stop it from running</span></span>
- <span data-ttu-id="0d936-224">**删除**- 关闭并删除规则</span><span class="sxs-lookup"><span data-stu-id="0d936-224">**Delete**—turn off the rule and remove it</span></span>

### <a name="view-and-manage-triggered-alerts"></a><span data-ttu-id="0d936-225">查看和管理触发的警报</span><span class="sxs-lookup"><span data-stu-id="0d936-225">View and manage triggered alerts</span></span>

<span data-ttu-id="0d936-226">在规则详细信息屏幕 (搜索自定义检测  >    >  **[规则名称]**) ，转到"触发的警报"，其中列出了规则匹配项生成的警报。</span><span class="sxs-lookup"><span data-stu-id="0d936-226">In the rule details screen (**Hunting** > **Custom detections** > **[Rule name]**), go to  **Triggered alerts**, which lists the alerts generated by matches to the rule.</span></span> <span data-ttu-id="0d936-227">选择警报以查看有关它的详细信息，并执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="0d936-227">Select an alert to view detailed information about it and take the following actions:</span></span>

- <span data-ttu-id="0d936-228">通过将警报的状态和分类设置为 true 或 false (来管理警报) </span><span class="sxs-lookup"><span data-stu-id="0d936-228">Manage the alert by setting its status and classification (true or false alert)</span></span>
- <span data-ttu-id="0d936-229">将警报链接到事件</span><span class="sxs-lookup"><span data-stu-id="0d936-229">Link the alert to an incident</span></span>
- <span data-ttu-id="0d936-230">运行在高级搜寻时触发警报的查询</span><span class="sxs-lookup"><span data-stu-id="0d936-230">Run the query that triggered the alert on advanced hunting</span></span>

### <a name="review-actions"></a><span data-ttu-id="0d936-231">查看操作</span><span class="sxs-lookup"><span data-stu-id="0d936-231">Review actions</span></span>
<span data-ttu-id="0d936-232">在规则详细信息屏幕 (搜索自定义检测  >    >  **[规则名称]**) ，转到"触发的操作"，其中列出了根据规则匹配项采取的操作。</span><span class="sxs-lookup"><span data-stu-id="0d936-232">In the rule details screen (**Hunting** > **Custom detections** > **[Rule name]**), go to **Triggered actions**, which lists the actions taken based on matches to the rule.</span></span>

>[!TIP]
><span data-ttu-id="0d936-233">若要快速查看信息并针对表中的项目采取操作，请使用表格左侧的选择列 [&#10003;] 。</span><span class="sxs-lookup"><span data-stu-id="0d936-233">To quickly view information and take action on an item in a table, use the selection column [&#10003;] at the left of the table.</span></span>

## <a name="related-topic"></a><span data-ttu-id="0d936-234">相关主题</span><span class="sxs-lookup"><span data-stu-id="0d936-234">Related topic</span></span>
- [<span data-ttu-id="0d936-235">自定义检测概述</span><span class="sxs-lookup"><span data-stu-id="0d936-235">Custom detections overview</span></span>](custom-detections-overview.md)
- [<span data-ttu-id="0d936-236">高级搜寻概述</span><span class="sxs-lookup"><span data-stu-id="0d936-236">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="0d936-237">了解高级搜寻查询语言</span><span class="sxs-lookup"><span data-stu-id="0d936-237">Learn the advanced hunting query language</span></span>](advanced-hunting-query-language.md)
