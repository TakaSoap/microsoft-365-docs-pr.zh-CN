---
title: 在 Microsoft 威胁防护中创建和管理自定义检测规则
description: 了解如何创建和管理基于高级搜寻查询的自定义检测规则
keywords: 高级搜寻、威胁搜寻、网络威胁搜寻、microsoft 威胁防护、microsoft 365、mtp、m365、搜索、查询、遥测、自定义检测、规则、架构、kusto、microsoft 365、Microsoft 威胁防护、RBAC、权限、Microsoft Defender ATP
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
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
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: e3388bd0d3a7ac6afff0109eb80945d3ddc362fd
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/22/2020
ms.locfileid: "48198893"
---
# <a name="create-and-manage-custom-detections-rules"></a><span data-ttu-id="af541-104">创建和管理自定义检测规则</span><span class="sxs-lookup"><span data-stu-id="af541-104">Create and manage custom detections rules</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="af541-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="af541-105">**Applies to:**</span></span>
- <span data-ttu-id="af541-106">Microsoft 威胁防护</span><span class="sxs-lookup"><span data-stu-id="af541-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="af541-107">自定义检测规则是您可以使用 [高级搜寻](advanced-hunting-overview.md) 查询进行设计和调整的规则。</span><span class="sxs-lookup"><span data-stu-id="af541-107">Custom detection rules are rules you can design and tweak using [advanced hunting](advanced-hunting-overview.md) queries.</span></span> <span data-ttu-id="af541-108">这些规则允许您主动监视各种事件和系统状态，包括可疑的入侵活动和错误配置的终结点。</span><span class="sxs-lookup"><span data-stu-id="af541-108">These rules let you proactively monitor various events and system states, including suspected breach activity and misconfigured endpoints.</span></span> <span data-ttu-id="af541-109">您可以将其设置为定期运行，并在存在匹配项时生成警报和采取响应操作。</span><span class="sxs-lookup"><span data-stu-id="af541-109">You can set them to run at regular intervals, generating alerts and taking response actions whenever there are matches.</span></span>

## <a name="required-permissions-for-managing-custom-detections"></a><span data-ttu-id="af541-110">管理自定义检测项所需的权限</span><span class="sxs-lookup"><span data-stu-id="af541-110">Required permissions for managing custom detections</span></span>

<span data-ttu-id="af541-111">若要管理自定义检测，您需要分配以下角色之一：</span><span class="sxs-lookup"><span data-stu-id="af541-111">To manage custom detections, you need to be assigned one of these roles:</span></span>

- <span data-ttu-id="af541-112">**安全管理员**-具有此 [Azure Active Directory 角色](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) 的用户可以在 Microsoft 365 安全中心和其他门户和服务中管理安全设置。</span><span class="sxs-lookup"><span data-stu-id="af541-112">**Security administrator**—Users with this [Azure Active Directory role](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) can manage security settings in Microsoft 365 security center and other portals and services.</span></span>

- <span data-ttu-id="af541-113">**Security operator**-具有此 [Azure Active Directory 角色](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) 的用户可以管理警报并对安全相关功能（包括 Microsoft 365 安全中心中的所有信息）具有全局只读访问权限。</span><span class="sxs-lookup"><span data-stu-id="af541-113">**Security operator**—Users with this [Azure Active Directory role](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) can manage alerts and have global read-only access to security-related features, including all information in Microsoft 365 security center.</span></span> <span data-ttu-id="af541-114">仅当基于角色的访问控制 (RBAC) 在 Microsoft Defender ATP 中处于关闭状态时，此角色才足够管理自定义检测。</span><span class="sxs-lookup"><span data-stu-id="af541-114">This role is sufficient for managing custom detections only if role-based access control (RBAC) is turned off in Microsoft Defender ATP.</span></span> <span data-ttu-id="af541-115">如果配置了 RBAC，则还需要具有 Microsoft Defender ATP 的 " **管理安全设置** " 权限。</span><span class="sxs-lookup"><span data-stu-id="af541-115">If you have RBAC configured, you also need the **manage security settings** permission for Microsoft Defender ATP.</span></span>

<span data-ttu-id="af541-116">若要管理所需的权限， **全局管理员** 可以执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="af541-116">To manage required permissions, a **global administrator** can:</span></span>

- <span data-ttu-id="af541-117">在**角色**安全管理员下的[Microsoft 365 管理中心](https://admin.microsoft.com/)中分配**安全管理员**或**安全操作员**角色  >  **Security admin**。</span><span class="sxs-lookup"><span data-stu-id="af541-117">Assign the **security administrator** or **security operator** role in [Microsoft 365 admin center](https://admin.microsoft.com/) under **Roles** > **Security admin**.</span></span>
- <span data-ttu-id="af541-118">在 "**设置**权限角色" 下的 " [microsoft defender 安全中心](https://securitycenter.windows.com/)" 中检查 microsoft defender ATP 的 RBAC 设置  >  **Permissions**  >  **Roles**。</span><span class="sxs-lookup"><span data-stu-id="af541-118">Check RBAC settings for Microsoft Defender ATP in [Microsoft Defender Security Center](https://securitycenter.windows.com/) under **Settings** > **Permissions** > **Roles**.</span></span> <span data-ttu-id="af541-119">选择相应的角色以分配 **管理安全设置** 权限。</span><span class="sxs-lookup"><span data-stu-id="af541-119">Select the corresponding role to assign the **manage security settings** permission.</span></span>

> [!NOTE]
> <span data-ttu-id="af541-120">若要管理自定义检测，如果 RBAC 已打开， **安全操作员** 将需要 MICROSOFT Defender ATP 中的 " **管理安全设置** " 权限。</span><span class="sxs-lookup"><span data-stu-id="af541-120">To manage custom detections, **security operators** will need the **manage security settings** permission in Microsoft Defender ATP if RBAC is turned on.</span></span>

## <a name="create-a-custom-detection-rule"></a><span data-ttu-id="af541-121">创建自定义检测规则</span><span class="sxs-lookup"><span data-stu-id="af541-121">Create a custom detection rule</span></span>
### <a name="1-prepare-the-query"></a><span data-ttu-id="af541-122">1. 准备查询。</span><span class="sxs-lookup"><span data-stu-id="af541-122">1. Prepare the query.</span></span>

<span data-ttu-id="af541-123">在 Microsoft 365 安全中心中，转到 " **高级** 搜索"，然后选择一个现有查询或创建新的查询。</span><span class="sxs-lookup"><span data-stu-id="af541-123">In Microsoft 365 security center, go to **Advanced hunting** and select an existing query or create a new query.</span></span> <span data-ttu-id="af541-124">使用新查询时，请运行查询以确定错误并了解可能的结果。</span><span class="sxs-lookup"><span data-stu-id="af541-124">When using a new query, run the query to identify errors and understand possible results.</span></span>

>[!IMPORTANT]
><span data-ttu-id="af541-125">若要防止服务返回过多警报，每个规则都限制为每次运行时仅生成100警报。</span><span class="sxs-lookup"><span data-stu-id="af541-125">To prevent the service from returning too many alerts, each rule is limited to generating only 100 alerts whenever it runs.</span></span> <span data-ttu-id="af541-126">在创建规则之前，请调整您的查询以避免正常的日常活动的警报。</span><span class="sxs-lookup"><span data-stu-id="af541-126">Before creating a rule, tweak your query to avoid alerting for normal, day-to-day activity.</span></span>


#### <a name="required-columns-in-the-query-results"></a><span data-ttu-id="af541-127">查询结果中的必需列</span><span class="sxs-lookup"><span data-stu-id="af541-127">Required columns in the query results</span></span>
<span data-ttu-id="af541-128">若要创建自定义检测规则，查询必须返回以下列：</span><span class="sxs-lookup"><span data-stu-id="af541-128">To create a custom detection rule, the query must return the following columns:</span></span>

- <span data-ttu-id="af541-129">`Timestamp`-用于设置生成的警报的时间戳</span><span class="sxs-lookup"><span data-stu-id="af541-129">`Timestamp`—used to set the timestamp for generated alerts</span></span>
- <span data-ttu-id="af541-130">`ReportId`-启用对原始记录的查找</span><span class="sxs-lookup"><span data-stu-id="af541-130">`ReportId`—enables lookups for the original records</span></span>
- <span data-ttu-id="af541-131">标识特定设备、用户或邮箱的下列各列之一：</span><span class="sxs-lookup"><span data-stu-id="af541-131">One of the following columns that identify specific devices, users, or mailboxes:</span></span>
    - `DeviceId`
    - `DeviceName`
    - `RemoteDeviceName`
    - `RecipientEmailAddress`
    - <span data-ttu-id="af541-132">`SenderFromAddress` (信封发件人或寄信人路径地址) </span><span class="sxs-lookup"><span data-stu-id="af541-132">`SenderFromAddress` (envelope sender or Return-Path address)</span></span>
    - <span data-ttu-id="af541-133">`SenderMailFromAddress` (电子邮件客户端显示的发件人地址) </span><span class="sxs-lookup"><span data-stu-id="af541-133">`SenderMailFromAddress` (sender address displayed by email client)</span></span>
    - `RecipientObjectId`
    - `AccountObjectId`
    - `AccountSid`
    - `AccountUpn`
    - `InitiatingProcessAccountSid`
    - `InitiatingProcessAccountUpn`
    - `InitiatingProcessAccountObjectId`

>[!NOTE]
><span data-ttu-id="af541-134">在向 [高级搜寻架构](advanced-hunting-schema-tables.md)中添加新表时，将添加对其他实体的支持。</span><span class="sxs-lookup"><span data-stu-id="af541-134">Support for additional entities will be added as new tables are added to the [advanced hunting schema](advanced-hunting-schema-tables.md).</span></span>

<span data-ttu-id="af541-135">简单查询（例如，不使用 `project` or `summarize` 运算符自定义或聚合结果的查询）通常返回这些常见的列。</span><span class="sxs-lookup"><span data-stu-id="af541-135">Simple queries, such as those that don't use the `project` or `summarize` operator to customize or aggregate results, typically return these common columns.</span></span>

<span data-ttu-id="af541-136">有多种方法可确保更复杂的查询返回这些列。</span><span class="sxs-lookup"><span data-stu-id="af541-136">There are various ways to ensure more complex queries return these columns.</span></span> <span data-ttu-id="af541-137">例如，如果您更喜欢在一列（如）下按实体进行聚合和计数 `DeviceId` ，则仍可以返回，也可以 `Timestamp` 通过与 `ReportId` 每个唯一涉及的最新事件获取它 `DeviceId` 。</span><span class="sxs-lookup"><span data-stu-id="af541-137">For example, if you prefer to aggregate and count by entity under a column such as `DeviceId`, you can still return `Timestamp` and `ReportId` by getting it from the most recent event involving each unique `DeviceId`.</span></span>

<span data-ttu-id="af541-138">下面的示例查询计算使用防病毒检测 () 的唯一设备的数量 `DeviceId` ，并使用此计数来仅查找具有超过5个检测项的设备。</span><span class="sxs-lookup"><span data-stu-id="af541-138">The sample query below counts the number of unique devices (`DeviceId`) with antivirus detections and uses this count to find only the devices with more than five detections.</span></span> <span data-ttu-id="af541-139">若要返回最新 `Timestamp` 和相应的 `ReportId` ，则将 `summarize` 运算符与函数一起使用 `arg_max` 。</span><span class="sxs-lookup"><span data-stu-id="af541-139">To return the latest `Timestamp` and the corresponding `ReportId`, it uses the `summarize` operator with the `arg_max` function.</span></span>

```kusto
DeviceEvents
| where Timestamp > ago(1d)
| where ActionType == "AntivirusDetection"
| summarize (Timestamp, ReportId)=arg_max(Timestamp, ReportId), count() by DeviceId
| where count_ > 5
```

> [!TIP]
> <span data-ttu-id="af541-140">若要获得更好的查询性能，请设置与规则的预期运行频率相匹配的时间筛选器。</span><span class="sxs-lookup"><span data-stu-id="af541-140">For better query performance, set a time filter that matches your intended run frequency for the rule.</span></span> <span data-ttu-id="af541-141">由于 _每隔24小时_运行最少的运行，因此过去一天的筛选将涵盖所有新数据。</span><span class="sxs-lookup"><span data-stu-id="af541-141">Since the least frequent run is _every 24 hours_, filtering for the past day will cover all new data.</span></span>

### <a name="2-create-new-rule-and-provide-alert-details"></a><span data-ttu-id="af541-142">2. 创建新规则并提供警报详细信息。</span><span class="sxs-lookup"><span data-stu-id="af541-142">2. Create new rule and provide alert details.</span></span>

<span data-ttu-id="af541-143">使用查询编辑器中的查询，选择 " **创建检测规则** "，并指定以下警报详细信息：</span><span class="sxs-lookup"><span data-stu-id="af541-143">With the query in the query editor, select **Create detection rule** and specify the following alert details:</span></span>

- <span data-ttu-id="af541-144">**检测名称**—检测规则的名称</span><span class="sxs-lookup"><span data-stu-id="af541-144">**Detection name**—name of the detection rule</span></span>
- <span data-ttu-id="af541-145">**Frequency**—运行查询和采取操作的时间间隔。</span><span class="sxs-lookup"><span data-stu-id="af541-145">**Frequency**—interval for running the query and taking action.</span></span> [<span data-ttu-id="af541-146">请参阅下面的其他指导</span><span class="sxs-lookup"><span data-stu-id="af541-146">See additional guidance below</span></span>](#rule-frequency)
- <span data-ttu-id="af541-147">**通知标题**—与规则触发的警报一起显示的标题</span><span class="sxs-lookup"><span data-stu-id="af541-147">**Alert title**—title displayed with alerts triggered by the rule</span></span>
- <span data-ttu-id="af541-148">**严重性**—由规则标识的组件或活动的潜在风险</span><span class="sxs-lookup"><span data-stu-id="af541-148">**Severity**—potential risk of the component or activity identified by the rule</span></span>
- <span data-ttu-id="af541-149">**Category**-由规则标识的威胁组件或活动</span><span class="sxs-lookup"><span data-stu-id="af541-149">**Category**—threat component or activity identified by the rule</span></span>
- <span data-ttu-id="af541-150">**MITRE ATT&CK 技术**—由规则标识的一个或多个攻击技术，如 [MITRE ATT&CK framework](https://attack.mitre.org/)中所述。</span><span class="sxs-lookup"><span data-stu-id="af541-150">**MITRE ATT&CK techniques**—one or more attack techniques identified by the rule as documented in the [MITRE ATT&CK framework](https://attack.mitre.org/).</span></span> <span data-ttu-id="af541-151">此部分对于某些警报类别是隐藏的，其中包括恶意软件、勒索软件、可疑活动和不需要的软件</span><span class="sxs-lookup"><span data-stu-id="af541-151">This section is hidden for certain alert categories, including malware, ransomware, suspicious activity, and unwanted software</span></span>
- <span data-ttu-id="af541-152">**说明**—有关由规则标识的组件或活动的详细信息</span><span class="sxs-lookup"><span data-stu-id="af541-152">**Description**—more information about the component or activity identified by the rule</span></span> 
- <span data-ttu-id="af541-153">**建议的操作**，响应者可能会采取的其他操作来响应警报</span><span class="sxs-lookup"><span data-stu-id="af541-153">**Recommended actions**—additional actions that responders might take in response to an alert</span></span>

#### <a name="rule-frequency"></a><span data-ttu-id="af541-154">规则频率</span><span class="sxs-lookup"><span data-stu-id="af541-154">Rule frequency</span></span>
<span data-ttu-id="af541-155">当您保存或编辑新规则时，它会运行并检查来自过去30天数据的匹配项。</span><span class="sxs-lookup"><span data-stu-id="af541-155">When you save or edit a new rule, it runs and checks for matches from the past 30 days of data.</span></span> <span data-ttu-id="af541-156">然后，该规则将按固定的时间间隔再次运行，并根据您选择的频率应用 lookback 持续时间：</span><span class="sxs-lookup"><span data-stu-id="af541-156">The rule then runs again at fixed intervals, applying a lookback duration based on the frequency you choose:</span></span>

- <span data-ttu-id="af541-157">**每24小时一**次，从过去30天中检查数据，每24小时运行一次</span><span class="sxs-lookup"><span data-stu-id="af541-157">**Every 24 hours**—runs every 24 hours, checking data from the past 30 days</span></span>
- <span data-ttu-id="af541-158">**每12个小时一**次，从过去24小时内检查数据，每12小时运行一次</span><span class="sxs-lookup"><span data-stu-id="af541-158">**Every 12 hours**—runs every 12 hours, checking data from the past 24 hours</span></span>
- <span data-ttu-id="af541-159">**每3小时一**次，每3小时运行一次，检查过去6个小时的数据</span><span class="sxs-lookup"><span data-stu-id="af541-159">**Every 3 hours**—runs every 3 hours, checking data from the past 6 hours</span></span>
- <span data-ttu-id="af541-160">**每小时一次—每**小时运行一次，检查过去2个小时内的数据</span><span class="sxs-lookup"><span data-stu-id="af541-160">**Every hour**—runs hourly, checking data from the past 2 hours</span></span>

>[!TIP]
> <span data-ttu-id="af541-161">将查询中的时间筛选器与 lookback 持续时间相匹配。</span><span class="sxs-lookup"><span data-stu-id="af541-161">Match the time filters in your query with the lookback duration.</span></span> <span data-ttu-id="af541-162">Lookback 持续时间之外的结果将被忽略。</span><span class="sxs-lookup"><span data-stu-id="af541-162">Results outside of the lookback duration are ignored.</span></span>  

<span data-ttu-id="af541-163">选择与您要监视检测结果的接近程度相匹配的频率。</span><span class="sxs-lookup"><span data-stu-id="af541-163">Select the frequency that matches how closely you want to monitor detections.</span></span> <span data-ttu-id="af541-164">请考虑贵组织对警报做出响应的能力。</span><span class="sxs-lookup"><span data-stu-id="af541-164">Consider your organization's capacity to respond to the alerts.</span></span>

### <a name="3-choose-the-impacted-entities"></a><span data-ttu-id="af541-165">3. 选择受影响的实体。</span><span class="sxs-lookup"><span data-stu-id="af541-165">3. Choose the impacted entities.</span></span>
<span data-ttu-id="af541-166">确定您希望在其中查找受影响的主要或受影响的实体的查询结果中的列。</span><span class="sxs-lookup"><span data-stu-id="af541-166">Identify the columns in your query results where you expect to find the main affected or impacted entity.</span></span> <span data-ttu-id="af541-167">例如，查询可能会返回发件人 (`SenderFromAddress` 或 `SenderMailFromAddress`) 和收件人 (`RecipientEmailAddress`) 地址。</span><span class="sxs-lookup"><span data-stu-id="af541-167">For example, a query might return sender (`SenderFromAddress` or `SenderMailFromAddress`) and recipient (`RecipientEmailAddress`) addresses.</span></span> <span data-ttu-id="af541-168">确定哪些列代表主要受影响的实体可帮助服务聚合相关警报、关联事件和目标响应操作。</span><span class="sxs-lookup"><span data-stu-id="af541-168">Identifying which of these columns represent the main impacted entity helps the service aggregate relevant alerts, correlate incidents, and target response actions.</span></span>

<span data-ttu-id="af541-169">您只能为每个实体类型 (邮箱、用户或设备) 选择一列。</span><span class="sxs-lookup"><span data-stu-id="af541-169">You can select only one column for each entity type (mailbox, user, or device).</span></span> <span data-ttu-id="af541-170">无法选择查询未返回的列。</span><span class="sxs-lookup"><span data-stu-id="af541-170">Columns that are not returned by your query can't be selected.</span></span>

### <a name="4-specify-actions"></a><span data-ttu-id="af541-171">4. 指定操作。</span><span class="sxs-lookup"><span data-stu-id="af541-171">4. Specify actions.</span></span>
<span data-ttu-id="af541-172">您的自定义检测规则可以对查询返回的设备、文件或用户自动执行操作。</span><span class="sxs-lookup"><span data-stu-id="af541-172">Your custom detection rule can automatically take actions on devices, files, or users that are returned by the query.</span></span>

#### <a name="actions-on-devices"></a><span data-ttu-id="af541-173">对设备的操作</span><span class="sxs-lookup"><span data-stu-id="af541-173">Actions on devices</span></span>
<span data-ttu-id="af541-174">这些操作适用于 `DeviceId` 查询结果列中的设备：</span><span class="sxs-lookup"><span data-stu-id="af541-174">These actions are applied to devices in the `DeviceId` column of the query results:</span></span>
- <span data-ttu-id="af541-175">**隔离设备**—使用 MICROSOFT Defender ATP 应用完全网络隔离，以阻止设备连接到任何应用程序或服务。</span><span class="sxs-lookup"><span data-stu-id="af541-175">**Isolate device**—uses Microsoft Defender ATP to apply full network isolation, preventing the device from connecting to any application or service.</span></span> [<span data-ttu-id="af541-176">了解有关 Microsoft Defender ATP 计算机隔离的详细信息</span><span class="sxs-lookup"><span data-stu-id="af541-176">Learn more about Microsoft Defender ATP machine isolation</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#isolate-devices-from-the-network)
- <span data-ttu-id="af541-177">**收集调查包**—收集 ZIP 文件中的设备信息。</span><span class="sxs-lookup"><span data-stu-id="af541-177">**Collect investigation package**—collects device information in a ZIP file.</span></span> [<span data-ttu-id="af541-178">了解有关 Microsoft Defender ATP 调查包的详细信息</span><span class="sxs-lookup"><span data-stu-id="af541-178">Learn more about the Microsoft Defender ATP investigation package</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#collect-investigation-package-from-devices)
- <span data-ttu-id="af541-179">**运行防病毒扫描**—在设备上执行完整的 Windows Defender 防病毒扫描</span><span class="sxs-lookup"><span data-stu-id="af541-179">**Run antivirus scan**—performs a full Windows Defender Antivirus scan on the device</span></span>
- <span data-ttu-id="af541-180">**启动调查**—启动对设备的[自动调查](mtp-autoir.md)</span><span class="sxs-lookup"><span data-stu-id="af541-180">**Initiate investigation**—initiates an [automated investigation](mtp-autoir.md) on the device</span></span>
- <span data-ttu-id="af541-181">**限制应用程序执行**—将对设备的限制设置为仅允许使用 Microsoft 颁发的证书签名的文件运行。</span><span class="sxs-lookup"><span data-stu-id="af541-181">**Restrict app execution**—sets restrictions on device to allow only files that are signed with a Microsoft-issued certificate to run.</span></span> [<span data-ttu-id="af541-182">了解有关 Microsoft Defender ATP 的应用限制的详细信息</span><span class="sxs-lookup"><span data-stu-id="af541-182">Learn more about app restrictions with Microsoft Defender ATP</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#restrict-app-execution)

#### <a name="actions-on-files"></a><span data-ttu-id="af541-183">对文件执行的操作</span><span class="sxs-lookup"><span data-stu-id="af541-183">Actions on files</span></span>
<span data-ttu-id="af541-184">如果选择此选项，则可以选择对查询结果的、、或列中的文件应用 **隔离文件** 操作 `SHA1` `InitiatingProcessSHA1` `SHA256` `InitiatingProcessSHA256` 。</span><span class="sxs-lookup"><span data-stu-id="af541-184">When selected, you can choose to apply the **Quarantine file** action on files in the `SHA1`, `InitiatingProcessSHA1`, `SHA256`, or `InitiatingProcessSHA256` column of the query results.</span></span> <span data-ttu-id="af541-185">此操作将从文件的当前位置删除文件，并将副本放在 "隔离" 中。</span><span class="sxs-lookup"><span data-stu-id="af541-185">This action deletes the file from its current location and places a copy in quarantine.</span></span>

#### <a name="actions-on-users"></a><span data-ttu-id="af541-186">对用户的操作</span><span class="sxs-lookup"><span data-stu-id="af541-186">Actions on users</span></span>
<span data-ttu-id="af541-187">如果选择此选项，则会对查询结果的、或列中的用户执行 "将 **用户标记为受到威胁** " 操作 `AccountObjectId` `InitiatingProcessAccountObjectId` `RecipientObjectId` 。</span><span class="sxs-lookup"><span data-stu-id="af541-187">When selected, the **Mark user as compromised** action is taken on users in the `AccountObjectId`, `InitiatingProcessAccountObjectId`, or `RecipientObjectId` column of the query results.</span></span> <span data-ttu-id="af541-188">此操作在 Azure Active Directory 中将用户风险级别设置为 "高"，从而触发相应的 [标识保护策略](https://docs.microsoft.com/azure/active-directory/identity-protection/overview-identity-protection)。</span><span class="sxs-lookup"><span data-stu-id="af541-188">This action sets the users risk level to "high" in Azure Active Directory, triggering corresponding [identity protection policies](https://docs.microsoft.com/azure/active-directory/identity-protection/overview-identity-protection).</span></span>

> [!NOTE]
> <span data-ttu-id="af541-189">Microsoft 威胁防护目前不支持自定义检测规则的允许或阻止操作。</span><span class="sxs-lookup"><span data-stu-id="af541-189">The allow or block action for custom detection rules is currently not supported on Microsoft Threat Protection.</span></span>

### <a name="5-set-the-rule-scope"></a><span data-ttu-id="af541-190">5. 设置规则作用域。</span><span class="sxs-lookup"><span data-stu-id="af541-190">5. Set the rule scope.</span></span>
<span data-ttu-id="af541-191">设置作用域以指定规则所涵盖的设备。</span><span class="sxs-lookup"><span data-stu-id="af541-191">Set the scope to specify which devices are covered by the rule.</span></span> <span data-ttu-id="af541-192">作用域会影响检查设备的规则，而不会影响仅检查邮箱和用户帐户或标识的规则。</span><span class="sxs-lookup"><span data-stu-id="af541-192">The scope influences rules that check devices and doesn't affect rules that check only mailboxes and user accounts or identities.</span></span>

<span data-ttu-id="af541-193">设置作用域时，可以选择：</span><span class="sxs-lookup"><span data-stu-id="af541-193">When setting the scope, you can select:</span></span>

- <span data-ttu-id="af541-194">所有设备</span><span class="sxs-lookup"><span data-stu-id="af541-194">All devices</span></span>
- <span data-ttu-id="af541-195">特定设备组</span><span class="sxs-lookup"><span data-stu-id="af541-195">Specific device groups</span></span>

<span data-ttu-id="af541-196">仅会查询范围内设备中的数据。</span><span class="sxs-lookup"><span data-stu-id="af541-196">Only data from devices in scope will be queried.</span></span> <span data-ttu-id="af541-197">此外，操作只会在这些设备上执行。</span><span class="sxs-lookup"><span data-stu-id="af541-197">Also, actions will be taken only on those devices.</span></span>

### <a name="6-review-and-turn-on-the-rule"></a><span data-ttu-id="af541-198">6. 查看并启用规则。</span><span class="sxs-lookup"><span data-stu-id="af541-198">6. Review and turn on the rule.</span></span>
<span data-ttu-id="af541-199">检查规则后，选择 " **创建** " 以保存该规则。</span><span class="sxs-lookup"><span data-stu-id="af541-199">After reviewing the rule, select **Create** to save it.</span></span> <span data-ttu-id="af541-200">自定义检测规则将立即运行。</span><span class="sxs-lookup"><span data-stu-id="af541-200">The custom detection rule immediately runs.</span></span> <span data-ttu-id="af541-201">它将根据配置的频率再次运行，以检查匹配项、生成警报并采取响应操作。</span><span class="sxs-lookup"><span data-stu-id="af541-201">It runs again based on configured frequency to check for matches, generate alerts, and take response actions.</span></span>

## <a name="manage-existing-custom-detection-rules"></a><span data-ttu-id="af541-202">管理现有的自定义检测规则</span><span class="sxs-lookup"><span data-stu-id="af541-202">Manage existing custom detection rules</span></span>
<span data-ttu-id="af541-203">您可以查看现有的自定义检测规则的列表，检查其以前的运行，并查看它们触发的警报。</span><span class="sxs-lookup"><span data-stu-id="af541-203">You can view the list of existing custom detection rules, check their previous runs, and review the alerts they have triggered.</span></span> <span data-ttu-id="af541-204">您还可以按需运行规则并对其进行修改。</span><span class="sxs-lookup"><span data-stu-id="af541-204">You can also run a rule on demand and modify it.</span></span>

### <a name="view-existing-rules"></a><span data-ttu-id="af541-205">查看现有规则</span><span class="sxs-lookup"><span data-stu-id="af541-205">View existing rules</span></span>

<span data-ttu-id="af541-206">若要查看所有现有的自定义检测规则，请导航到 "**搜寻**  >  **自定义**检测"。</span><span class="sxs-lookup"><span data-stu-id="af541-206">To view all existing custom detection rules, navigate to **Hunting** > **Custom detections**.</span></span> <span data-ttu-id="af541-207">页面列出了包含以下运行信息的所有规则：</span><span class="sxs-lookup"><span data-stu-id="af541-207">The page lists all the rules with the following run information:</span></span>

- <span data-ttu-id="af541-208">**上次运行**时间—上次运行规则以检查查询匹配项并生成警报</span><span class="sxs-lookup"><span data-stu-id="af541-208">**Last run**—when a rule was last run to check for query matches and generate alerts</span></span>
- <span data-ttu-id="af541-209">**上次运行状态**—规则是否成功运行</span><span class="sxs-lookup"><span data-stu-id="af541-209">**Last run status**—whether a rule ran successfully</span></span>
- <span data-ttu-id="af541-210">**下次运行**—下一次计划的运行</span><span class="sxs-lookup"><span data-stu-id="af541-210">**Next run**—the next scheduled run</span></span>
- <span data-ttu-id="af541-211">**状态**—是否已打开或关闭规则</span><span class="sxs-lookup"><span data-stu-id="af541-211">**Status**—whether a rule has been turned on or off</span></span>

### <a name="view-rule-details-modify-rule-and-run-rule"></a><span data-ttu-id="af541-212">查看规则详细信息、修改规则和运行规则</span><span class="sxs-lookup"><span data-stu-id="af541-212">View rule details, modify rule, and run rule</span></span>

<span data-ttu-id="af541-213">若要查看有关自定义检测规则的完整信息，请**转到 "** 搜索  >  **自定义检测**"，然后选择规则的名称。</span><span class="sxs-lookup"><span data-stu-id="af541-213">To view comprehensive information about a custom detection rule, go to **Hunting** > **Custom detections** and then select the name of rule.</span></span> <span data-ttu-id="af541-214">然后，您可以查看有关该规则的常规信息，包括信息的运行状态和范围。</span><span class="sxs-lookup"><span data-stu-id="af541-214">You can then view general information about the rule, including information its run status and scope.</span></span> <span data-ttu-id="af541-215">此页面还提供触发的警报和操作的列表。</span><span class="sxs-lookup"><span data-stu-id="af541-215">The page also provides the list of triggered alerts and actions.</span></span>

<span data-ttu-id="af541-216">!["自定义检测规则详细信息" 页](../../media/custom-detection-details.png)</span><span class="sxs-lookup"><span data-stu-id="af541-216">![Custom detection rule details page](../../media/custom-detection-details.png)</span></span><br>
<span data-ttu-id="af541-217">*自定义检测规则详细信息*</span><span class="sxs-lookup"><span data-stu-id="af541-217">*Custom detection rule details*</span></span>

<span data-ttu-id="af541-218">此外，还可以对此页面中的规则执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="af541-218">You can also take the following actions on the rule from this page:</span></span>

- <span data-ttu-id="af541-219">**运行**—立即运行该规则。</span><span class="sxs-lookup"><span data-stu-id="af541-219">**Run**—run the rule immediately.</span></span> <span data-ttu-id="af541-220">这还会重置下一次运行的时间间隔。</span><span class="sxs-lookup"><span data-stu-id="af541-220">This also resets the interval for the next run.</span></span>
- <span data-ttu-id="af541-221">**编辑**—在不更改查询的情况下修改规则</span><span class="sxs-lookup"><span data-stu-id="af541-221">**Edit**—modify the rule without changing the query</span></span>
- <span data-ttu-id="af541-222">**修改查询**—在高级搜寻中编辑查询</span><span class="sxs-lookup"><span data-stu-id="af541-222">**Modify query**—edit the query in advanced hunting</span></span>
- <span data-ttu-id="af541-223">**打开**  / **关闭**—启用或停止运行规则</span><span class="sxs-lookup"><span data-stu-id="af541-223">**Turn on** / **Turn off**—enable the rule or stop it from running</span></span>
- <span data-ttu-id="af541-224">**删除**-关闭规则并将其删除</span><span class="sxs-lookup"><span data-stu-id="af541-224">**Delete**—turn off the rule and remove it</span></span>

### <a name="view-and-manage-triggered-alerts"></a><span data-ttu-id="af541-225">查看和管理触发的警报</span><span class="sxs-lookup"><span data-stu-id="af541-225">View and manage triggered alerts</span></span>

<span data-ttu-id="af541-226">在 "规则详细信息" 屏幕**中 (**  >  搜索**自定义检测**  >  **[规则名称]**) 中，转到 "**触发警报**"，其中列出了与该规则匹配生成的警报。</span><span class="sxs-lookup"><span data-stu-id="af541-226">In the rule details screen (**Hunting** > **Custom detections** > **[Rule name]**), go to  **Triggered alerts**, which lists the alerts generated by matches to the rule.</span></span> <span data-ttu-id="af541-227">选择一个警报以查看有关其的详细信息，并执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="af541-227">Select an alert to view detailed information about it and take the following actions:</span></span>

- <span data-ttu-id="af541-228">通过将警报的状态和分类设置 (true 或 false 警报来管理警报) </span><span class="sxs-lookup"><span data-stu-id="af541-228">Manage the alert by setting its status and classification (true or false alert)</span></span>
- <span data-ttu-id="af541-229">将警报链接到事件</span><span class="sxs-lookup"><span data-stu-id="af541-229">Link the alert to an incident</span></span>
- <span data-ttu-id="af541-230">在高级搜寻中运行触发警报的查询</span><span class="sxs-lookup"><span data-stu-id="af541-230">Run the query that triggered the alert on advanced hunting</span></span>

### <a name="review-actions"></a><span data-ttu-id="af541-231">查看操作</span><span class="sxs-lookup"><span data-stu-id="af541-231">Review actions</span></span>
<span data-ttu-id="af541-232">在 "规则详细信息" 屏幕**中 (**  >  搜索**自定义检测**  >  **[规则名称]**) 中，转到 "**触发操作**"，其中列出了根据与规则匹配而执行的操作。</span><span class="sxs-lookup"><span data-stu-id="af541-232">In the rule details screen (**Hunting** > **Custom detections** > **[Rule name]**), go to **Triggered actions**, which lists the actions taken based on matches to the rule.</span></span>

>[!TIP]
><span data-ttu-id="af541-233">若要快速查看信息并对表中的项目执行操作，请使用表左侧的选择列 [&#10003;]。</span><span class="sxs-lookup"><span data-stu-id="af541-233">To quickly view information and take action on an item in a table, use the selection column [&#10003;] at the left of the table.</span></span>

## <a name="related-topic"></a><span data-ttu-id="af541-234">相关主题</span><span class="sxs-lookup"><span data-stu-id="af541-234">Related topic</span></span>
- [<span data-ttu-id="af541-235">自定义检测概述</span><span class="sxs-lookup"><span data-stu-id="af541-235">Custom detections overview</span></span>](custom-detections-overview.md)
- [<span data-ttu-id="af541-236">高级搜寻概述</span><span class="sxs-lookup"><span data-stu-id="af541-236">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="af541-237">了解高级搜寻查询语言</span><span class="sxs-lookup"><span data-stu-id="af541-237">Learn the advanced hunting query language</span></span>](advanced-hunting-query-language.md)
