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
ms.openlocfilehash: cea4dbcb42833a14980d092bd0ff168ca97e5934
ms.sourcegitcommit: 9489aaf255f8bf165e6debc574e20548ad82e882
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/11/2020
ms.locfileid: "46632147"
---
# <a name="create-and-manage-custom-detections-rules"></a><span data-ttu-id="76962-104">创建和管理自定义检测规则</span><span class="sxs-lookup"><span data-stu-id="76962-104">Create and manage custom detections rules</span></span>

<span data-ttu-id="76962-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="76962-105">**Applies to:**</span></span>
- <span data-ttu-id="76962-106">Microsoft 威胁防护</span><span class="sxs-lookup"><span data-stu-id="76962-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="76962-107">通过[先进的搜寻](advanced-hunting-overview.md)查询生成的自定义检测规则使您能够主动监视各种事件和系统状态，包括可疑的违规活动和错误配置的终结点。</span><span class="sxs-lookup"><span data-stu-id="76962-107">Custom detection rules built from [Advanced hunting](advanced-hunting-overview.md) queries let you proactively monitor various events and system states, including suspected breach activity and misconfigured endpoints.</span></span> <span data-ttu-id="76962-108">您可以将其设置为定期运行，并在存在匹配项时生成警报和采取响应操作。</span><span class="sxs-lookup"><span data-stu-id="76962-108">You can set them to run at regular intervals, generating alerts and taking response actions whenever there are matches.</span></span>

## <a name="required-permissions-for-managing-custom-detections"></a><span data-ttu-id="76962-109">管理自定义检测项所需的权限</span><span class="sxs-lookup"><span data-stu-id="76962-109">Required permissions for managing custom detections</span></span>

<span data-ttu-id="76962-110">若要管理自定义检测，您需要分配以下角色之一：</span><span class="sxs-lookup"><span data-stu-id="76962-110">To manage custom detections, you need to be assigned one of these roles:</span></span>

- <span data-ttu-id="76962-111">**安全管理员**-安全管理员或安全管理员角色是用于管理 Microsoft 365 安全中心和各种门户和服务中的各种安全设置的[Azure Active Directory 角色](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator)。</span><span class="sxs-lookup"><span data-stu-id="76962-111">**Security administrator** — the security administrator or security admin role is an [Azure Active Directory role](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) for managing various security settings in Microsoft 365 security center and various portals and services.</span></span>

- <span data-ttu-id="76962-112">**安全操作员**—安全操作员角色是用于管理警报的[Azure Active Directory 角色](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator)，它具有与安全相关的功能（包括 Microsoft 365 安全中心中的所有信息）的全局只读访问权限。</span><span class="sxs-lookup"><span data-stu-id="76962-112">**Security operator** —  the security operator role is an [Azure Active Directory role](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) for managing alerts and has global read-only access on security-related features, including all information in Microsoft 365 security center.</span></span> <span data-ttu-id="76962-113">仅当基于角色的访问控制 (RBAC) 在 Microsoft Defender ATP 中处于关闭状态时，此角色才足够管理自定义检测。</span><span class="sxs-lookup"><span data-stu-id="76962-113">This role is sufficient for managing custom detections only if role-based access control (RBAC) is turned off in Microsoft Defender ATP.</span></span> <span data-ttu-id="76962-114">如果配置了 RBAC，则还需要具有 Microsoft Defender ATP 的 "**管理安全设置**" 权限。</span><span class="sxs-lookup"><span data-stu-id="76962-114">If you have RBAC configured, you also need the **manage security settings** permission for Microsoft Defender ATP.</span></span>

<span data-ttu-id="76962-115">若要管理所需的权限，**全局管理员**可以执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="76962-115">To manage required permissions, a **global administrator** can do the following:</span></span>

- <span data-ttu-id="76962-116">在**角色**安全管理员下的[Microsoft 365 管理中心](https://admin.microsoft.com/)中分配**安全管理员**或**安全操作员**角色  >  **Security admin**。</span><span class="sxs-lookup"><span data-stu-id="76962-116">Assign the **security administrator** or **security operator** role in [Microsoft 365 admin center](https://admin.microsoft.com/) under **Roles** > **Security admin**.</span></span>
- <span data-ttu-id="76962-117">在 "**设置**权限角色" 下的 " [microsoft defender 安全中心](https://securitycenter.windows.com/)" 中检查 microsoft defender ATP 的 RBAC 设置  >  **Permissions**  >  **Roles**。</span><span class="sxs-lookup"><span data-stu-id="76962-117">Check RBAC settings for Microsoft Defender ATP in [Microsoft Defender Security Center](https://securitycenter.windows.com/) under **Settings** > **Permissions** > **Roles**.</span></span> <span data-ttu-id="76962-118">选择相应的角色以分配**管理安全设置**权限。</span><span class="sxs-lookup"><span data-stu-id="76962-118">Select the corresponding role to assign the **manage security settings** permission.</span></span>

> [!NOTE]
> <span data-ttu-id="76962-119">若要管理自定义检测，如果 RBAC 已打开，**安全操作员**将需要 MICROSOFT Defender ATP 中的 "**管理安全设置**" 权限。</span><span class="sxs-lookup"><span data-stu-id="76962-119">To manage custom detections, **security operators** will need the **manage security settings** permission in Microsoft Defender ATP if RBAC is turned on.</span></span>

## <a name="create-a-custom-detection-rule"></a><span data-ttu-id="76962-120">创建自定义检测规则</span><span class="sxs-lookup"><span data-stu-id="76962-120">Create a custom detection rule</span></span>
### <a name="1-prepare-the-query"></a><span data-ttu-id="76962-121">1. 准备查询。</span><span class="sxs-lookup"><span data-stu-id="76962-121">1. Prepare the query.</span></span>

<span data-ttu-id="76962-122">在 Microsoft 365 安全中心中，转到 "**高级**搜索"，然后选择一个现有查询或创建新的查询。</span><span class="sxs-lookup"><span data-stu-id="76962-122">In Microsoft 365 security center, go to **Advanced hunting** and select an existing query or create a new query.</span></span> <span data-ttu-id="76962-123">使用新查询时，请运行查询以确定错误并了解可能的结果。</span><span class="sxs-lookup"><span data-stu-id="76962-123">When using a new query, run the query to identify errors and understand possible results.</span></span>

>[!IMPORTANT]
><span data-ttu-id="76962-124">若要防止服务返回过多警报，每个规则都限制为每次运行时仅生成100警报。</span><span class="sxs-lookup"><span data-stu-id="76962-124">To prevent the service from returning too many alerts, each rule is limited to generating only 100 alerts whenever it runs.</span></span> <span data-ttu-id="76962-125">在创建规则之前，请调整您的查询以避免正常的日常活动的警报。</span><span class="sxs-lookup"><span data-stu-id="76962-125">Before creating a rule, tweak your query to avoid alerting for normal, day-to-day activity.</span></span>


#### <a name="required-columns-in-the-query-results"></a><span data-ttu-id="76962-126">查询结果中的必需列</span><span class="sxs-lookup"><span data-stu-id="76962-126">Required columns in the query results</span></span>
<span data-ttu-id="76962-127">若要创建自定义检测规则，查询必须返回以下列：</span><span class="sxs-lookup"><span data-stu-id="76962-127">To create a custom detection rule, the query must return the following columns:</span></span>

- `Timestamp`
- <span data-ttu-id="76962-128">下列设备、用户或邮箱列之一：</span><span class="sxs-lookup"><span data-stu-id="76962-128">One of the following device, user, or mailbox columns:</span></span>
    - `DeviceId`
    - `DeviceName`
    - `RemoteDeviceName`
    - `RecipientEmailAddress`
    - <span data-ttu-id="76962-129">`SenderFromAddress` (信封发件人或寄信人路径地址) </span><span class="sxs-lookup"><span data-stu-id="76962-129">`SenderFromAddress` (envelope sender or Return-Path address)</span></span>
    - <span data-ttu-id="76962-130">`SenderMailFromAddress` (电子邮件客户端显示的发件人地址) </span><span class="sxs-lookup"><span data-stu-id="76962-130">`SenderMailFromAddress` (sender address displayed by email client)</span></span>
    - `RecipientObjectId`
    - `AccountObjectId`
    - `AccountSid`
    - `AccountUpn`
    - `InitiatingProcessAccountSid`
    - `InitiatingProcessAccountUpn`
    - `InitiatingProcessAccountObjectId`
>[!NOTE]
><span data-ttu-id="76962-131">在向[高级搜寻架构](advanced-hunting-schema-tables.md)中添加新表时，将添加对其他实体的支持。</span><span class="sxs-lookup"><span data-stu-id="76962-131">Support for additional entities will be added as new tables are added to the [advanced hunting schema](advanced-hunting-schema-tables.md).</span></span>

<span data-ttu-id="76962-132">简单查询（例如，不使用 `project` or `summarize` 运算符自定义或聚合结果的查询）通常返回这些常见的列。</span><span class="sxs-lookup"><span data-stu-id="76962-132">Simple queries, such as those that don't use the `project` or `summarize` operator to customize or aggregate results, typically return these common columns.</span></span>

<span data-ttu-id="76962-133">有多种方法可确保更复杂的查询返回这些列。</span><span class="sxs-lookup"><span data-stu-id="76962-133">There are various ways to ensure more complex queries return these columns.</span></span> <span data-ttu-id="76962-134">例如，如果您希望在等列下按实体进行聚合和计数 `DeviceId` ，则仍可 `Timestamp` 通过获取每个唯一涉及的最新事件来返回 `DeviceId` 。</span><span class="sxs-lookup"><span data-stu-id="76962-134">For example, if you prefer to aggregate and count by entity under a column such as `DeviceId`, you can still return `Timestamp` by getting it from the most recent event involving each unique `DeviceId`.</span></span>

<span data-ttu-id="76962-135">下面的示例查询计算使用防病毒检测 () 的唯一设备的数量 `DeviceId` ，并使用此计数来仅查找具有超过5个检测项的设备。</span><span class="sxs-lookup"><span data-stu-id="76962-135">The sample query below counts the number of unique devices (`DeviceId`) with antivirus detections and uses this count to find only the devices with more than five detections.</span></span> <span data-ttu-id="76962-136">若要返回最新的 `Timestamp` ，它会将 `summarize` 运算符与函数一起使用 `arg_max` 。</span><span class="sxs-lookup"><span data-stu-id="76962-136">To return the latest `Timestamp`, it uses the `summarize` operator with the `arg_max` function.</span></span>

```kusto
DeviceEvents
| where ActionType == "AntivirusDetection"
| summarize Timestamp = max(Timestamp), count() by DeviceId, SHA1, InitiatingProcessAccountObjectId 
| where count_ > 5
```

### <a name="2-create-new-rule-and-provide-alert-details"></a><span data-ttu-id="76962-137">2. 创建新规则并提供警报详细信息。</span><span class="sxs-lookup"><span data-stu-id="76962-137">2. Create new rule and provide alert details.</span></span>

<span data-ttu-id="76962-138">使用查询编辑器中的查询，选择 "**创建检测规则**"，并指定以下警报详细信息：</span><span class="sxs-lookup"><span data-stu-id="76962-138">With the query in the query editor, select **Create detection rule** and specify the following alert details:</span></span>

- <span data-ttu-id="76962-139">**检测名称**—检测规则的名称</span><span class="sxs-lookup"><span data-stu-id="76962-139">**Detection name** — name of the detection rule</span></span>
- <span data-ttu-id="76962-140">**Frequency** —运行查询和采取操作的时间间隔。</span><span class="sxs-lookup"><span data-stu-id="76962-140">**Frequency** — interval for running the query and taking action.</span></span> [<span data-ttu-id="76962-141">请参阅下面的其他指导</span><span class="sxs-lookup"><span data-stu-id="76962-141">See additional guidance below</span></span>](#rule-frequency)
- <span data-ttu-id="76962-142">**通知标题**—与规则触发的警报一起显示的标题</span><span class="sxs-lookup"><span data-stu-id="76962-142">**Alert title** — title displayed with alerts triggered by the rule</span></span>
- <span data-ttu-id="76962-143">**严重性**—由规则标识的组件或活动的潜在风险</span><span class="sxs-lookup"><span data-stu-id="76962-143">**Severity** — potential risk of the component or activity identified by the rule</span></span>
- <span data-ttu-id="76962-144">**Category** -由规则标识的威胁组件或活动</span><span class="sxs-lookup"><span data-stu-id="76962-144">**Category** — threat component or activity identified by the rule</span></span>
- <span data-ttu-id="76962-145">**MITRE ATT&CK 技术**—由规则标识的一个或多个攻击技术，如[MITRE ATT&CK framework](https://attack.mitre.org/)中所述。</span><span class="sxs-lookup"><span data-stu-id="76962-145">**MITRE ATT&CK techniques** — one or more attack techniques identified by the rule as documented in the [MITRE ATT&CK framework](https://attack.mitre.org/).</span></span> <span data-ttu-id="76962-146">对于某些警报类别（包括恶意软件、勒索软件、可疑活动和不需要的软件），本节不适用且隐藏。</span><span class="sxs-lookup"><span data-stu-id="76962-146">This section does not apply and is hidden for certain alert categories, including malware, ransomware, suspicious activity, and unwanted software</span></span>
- <span data-ttu-id="76962-147">**说明**—有关由规则标识的组件或活动的详细信息</span><span class="sxs-lookup"><span data-stu-id="76962-147">**Description** — more information about the component or activity identified by the rule</span></span> 
- <span data-ttu-id="76962-148">**建议的操作**，响应者可能会采取的其他操作来响应警报</span><span class="sxs-lookup"><span data-stu-id="76962-148">**Recommended actions** — additional actions that responders might take in response to an alert</span></span>

#### <a name="rule-frequency"></a><span data-ttu-id="76962-149">规则频率</span><span class="sxs-lookup"><span data-stu-id="76962-149">Rule frequency</span></span>
<span data-ttu-id="76962-150">保存后，新的或编辑的自定义检测规则会立即运行并检查来自过去30天数据的匹配项。</span><span class="sxs-lookup"><span data-stu-id="76962-150">When saved, a new or edited custom detection rule immediately runs and checks for matches from  the past 30 days of data.</span></span> <span data-ttu-id="76962-151">然后，该规则将根据您选择的频率在固定时间间隔和 lookback 持续时间内再次运行：</span><span class="sxs-lookup"><span data-stu-id="76962-151">The rule then runs again at fixed intervals and lookback durations based on the frequency you choose:</span></span>

- <span data-ttu-id="76962-152">**每24小时一**次，从过去30天中检查数据，每24小时运行一次</span><span class="sxs-lookup"><span data-stu-id="76962-152">**Every 24 hours** — runs every 24 hours, checking data from the past 30 days</span></span>
- <span data-ttu-id="76962-153">**每12个小时一**次，从过去24小时内检查数据，每12小时运行一次</span><span class="sxs-lookup"><span data-stu-id="76962-153">**Every 12 hours** — runs every 12 hours, checking data from the past 24 hours</span></span>
- <span data-ttu-id="76962-154">**每3小时一**次，每3小时运行一次，检查过去6个小时的数据</span><span class="sxs-lookup"><span data-stu-id="76962-154">**Every 3 hours** — runs every 3 hours, checking data from the past 6 hours</span></span>
- <span data-ttu-id="76962-155">**每小时一次—每**小时运行一次，检查过去2个小时内的数据</span><span class="sxs-lookup"><span data-stu-id="76962-155">**Every hour** — runs hourly, checking data from the past 2 hours</span></span>

<span data-ttu-id="76962-156">选择与您要监视检测结果的接近程度相匹配的频率，并考虑组织的容量来响应警报。</span><span class="sxs-lookup"><span data-stu-id="76962-156">Select the frequency that matches how closely you want to monitor detections, and consider your organization's capacity to respond to the alerts.</span></span>

### <a name="3-choose-the-impacted-entities"></a><span data-ttu-id="76962-157">3. 选择受影响的实体。</span><span class="sxs-lookup"><span data-stu-id="76962-157">3. Choose the impacted entities.</span></span>
<span data-ttu-id="76962-158">确定您希望在其中查找受影响的主要或受影响的实体的查询结果中的列。</span><span class="sxs-lookup"><span data-stu-id="76962-158">Identify the columns in your query results where you expect to find the main affected or impacted entity.</span></span> <span data-ttu-id="76962-159">例如，查询可能会返回发件人 (`SenderFromAddress` 或 `SenderMailFromAddress`) 和收件人 (`RecipientEmailAddress`) 地址。</span><span class="sxs-lookup"><span data-stu-id="76962-159">For example, a query might return sender (`SenderFromAddress` or `SenderMailFromAddress`) and recipient (`RecipientEmailAddress`) addresses.</span></span> <span data-ttu-id="76962-160">确定哪些列代表主要受影响的实体可帮助服务聚合相关警报、关联事件和目标响应操作。</span><span class="sxs-lookup"><span data-stu-id="76962-160">Identifying which of these columns represent the main impacted entity helps the service aggregate relevant alerts, correlate incidents, and target response actions.</span></span>

<span data-ttu-id="76962-161">您只能为每个实体类型 (邮箱、用户或设备) 选择一列。</span><span class="sxs-lookup"><span data-stu-id="76962-161">You can select only one column for each entity type (mailbox, user, or device).</span></span> <span data-ttu-id="76962-162">无法选择查询未返回的列。</span><span class="sxs-lookup"><span data-stu-id="76962-162">Columns that are not returned by your query can't be selected.</span></span>

### <a name="4-specify-actions"></a><span data-ttu-id="76962-163">4. 指定操作。</span><span class="sxs-lookup"><span data-stu-id="76962-163">4. Specify actions.</span></span>
<span data-ttu-id="76962-164">您的自定义检测规则可以对查询返回的设备、文件或用户自动执行操作。</span><span class="sxs-lookup"><span data-stu-id="76962-164">Your custom detection rule can automatically take actions on devices, files, or users that are returned by the query.</span></span>

#### <a name="actions-on-devices"></a><span data-ttu-id="76962-165">对设备的操作</span><span class="sxs-lookup"><span data-stu-id="76962-165">Actions on devices</span></span>
<span data-ttu-id="76962-166">这些操作适用于 `DeviceId` 查询结果列中的设备：</span><span class="sxs-lookup"><span data-stu-id="76962-166">These actions are applied to devices in the `DeviceId` column of the query results:</span></span>
- <span data-ttu-id="76962-167">**隔离设备**—使用 MICROSOFT Defender ATP 应用完全网络隔离，以阻止设备连接到任何应用程序或服务。</span><span class="sxs-lookup"><span data-stu-id="76962-167">**Isolate device** — uses Microsoft Defender ATP to apply full network isolation, preventing the device from connecting to any application or service.</span></span> [<span data-ttu-id="76962-168">了解有关 Microsoft Defender ATP 计算机隔离的详细信息</span><span class="sxs-lookup"><span data-stu-id="76962-168">Learn more about Microsoft Defender ATP machine isolation</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#isolate-devices-from-the-network)
- <span data-ttu-id="76962-169">**收集调查包**—收集 ZIP 文件中的设备信息。</span><span class="sxs-lookup"><span data-stu-id="76962-169">**Collect investigation package** — collects device information in a ZIP file.</span></span> [<span data-ttu-id="76962-170">了解有关 Microsoft Defender ATP 调查包的详细信息</span><span class="sxs-lookup"><span data-stu-id="76962-170">Learn more about the Microsoft Defender ATP investigation package</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#collect-investigation-package-from-devices)
- <span data-ttu-id="76962-171">**运行防病毒扫描**—在设备上执行完整的 Windows Defender 防病毒扫描</span><span class="sxs-lookup"><span data-stu-id="76962-171">**Run antivirus scan** — performs a full Windows Defender Antivirus scan on the device</span></span>
- <span data-ttu-id="76962-172">**启动调查**—启动对设备的[自动调查](mtp-autoir.md)</span><span class="sxs-lookup"><span data-stu-id="76962-172">**Initiate investigation** — initiates an [automated investigation](mtp-autoir.md) on the device</span></span>
- <span data-ttu-id="76962-173">**限制应用程序执行**—将对设备的限制设置为仅允许使用 Microsoft 颁发的证书签名的文件运行。</span><span class="sxs-lookup"><span data-stu-id="76962-173">**Restrict app execution** — sets restrictions on device to allow only files that are signed with a Microsoft-issued certificate to run.</span></span> [<span data-ttu-id="76962-174">了解有关 Microsoft Defender ATP 的应用限制的详细信息</span><span class="sxs-lookup"><span data-stu-id="76962-174">Learn more about app restrictions with Microsoft Defender ATP</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#restrict-app-execution)

#### <a name="actions-on-files"></a><span data-ttu-id="76962-175">对文件执行的操作</span><span class="sxs-lookup"><span data-stu-id="76962-175">Actions on files</span></span>
<span data-ttu-id="76962-176">如果选择此选项，则可以选择对查询结果的、、或列中的文件应用**隔离文件**操作 `SHA1` `InitiatingProcessSHA1` `SHA256` `InitiatingProcessSHA256` 。</span><span class="sxs-lookup"><span data-stu-id="76962-176">When selected, you can choose to apply the **Quarantine file** action on files in the `SHA1`, `InitiatingProcessSHA1`, `SHA256`, or `InitiatingProcessSHA256` column of the query results.</span></span> <span data-ttu-id="76962-177">此操作将从文件的当前位置删除文件，并将副本放在 "隔离" 中。</span><span class="sxs-lookup"><span data-stu-id="76962-177">This action deletes the file from its current location and places a copy in quarantine.</span></span>

#### <a name="actions-on-users"></a><span data-ttu-id="76962-178">对用户的操作</span><span class="sxs-lookup"><span data-stu-id="76962-178">Actions on users</span></span>
<span data-ttu-id="76962-179">如果选择此选项，则会对查询结果的、或列中的用户执行 "将**用户标记为受到威胁**" 操作 `AccountObjectId` `InitiatingProcessAccountObjectId` `RecipientObjectId` 。</span><span class="sxs-lookup"><span data-stu-id="76962-179">When selected, the **Mark user as compromised** action is taken on users in the `AccountObjectId`, `InitiatingProcessAccountObjectId`, or `RecipientObjectId` column of the query results.</span></span> <span data-ttu-id="76962-180">此操作在 Azure Active Directory 中将用户风险级别设置为 "高"，从而触发相应的[标识保护策略](https://docs.microsoft.com/azure/active-directory/identity-protection/overview-identity-protection)。</span><span class="sxs-lookup"><span data-stu-id="76962-180">This action sets the users risk level to "high" in Azure Active Directory, triggering corresponding [identity protection policies](https://docs.microsoft.com/azure/active-directory/identity-protection/overview-identity-protection).</span></span>

> [!NOTE]
> <span data-ttu-id="76962-181">Microsoft 威胁防护目前不支持自定义检测规则的允许或阻止操作。</span><span class="sxs-lookup"><span data-stu-id="76962-181">The allow or block action for custom detection rules is currently not supported on Microsoft Threat Protection.</span></span>

### <a name="5-set-the-rule-scope"></a><span data-ttu-id="76962-182">5. 设置规则作用域。</span><span class="sxs-lookup"><span data-stu-id="76962-182">5. Set the rule scope.</span></span>
<span data-ttu-id="76962-183">设置作用域以指定规则所涵盖的设备。</span><span class="sxs-lookup"><span data-stu-id="76962-183">Set the scope to specify which devices are covered by the rule.</span></span> <span data-ttu-id="76962-184">作用域会影响检查设备的规则，而不会影响仅检查邮箱和用户帐户或标识的规则。</span><span class="sxs-lookup"><span data-stu-id="76962-184">The scope influences rules that check devices and doesn't affect rules that check only mailboxes and user accounts or identities.</span></span>

<span data-ttu-id="76962-185">设置作用域时，可以选择：</span><span class="sxs-lookup"><span data-stu-id="76962-185">When setting the scope, you can select:</span></span>

- <span data-ttu-id="76962-186">所有设备</span><span class="sxs-lookup"><span data-stu-id="76962-186">All devices</span></span>
- <span data-ttu-id="76962-187">特定设备组</span><span class="sxs-lookup"><span data-stu-id="76962-187">Specific device groups</span></span>

<span data-ttu-id="76962-188">仅会查询范围内设备中的数据。</span><span class="sxs-lookup"><span data-stu-id="76962-188">Only data from devices in scope will be queried.</span></span> <span data-ttu-id="76962-189">此外，操作只会在这些设备上执行。</span><span class="sxs-lookup"><span data-stu-id="76962-189">Also, actions will be taken only on those devices.</span></span>

### <a name="6-review-and-turn-on-the-rule"></a><span data-ttu-id="76962-190">6. 查看并启用规则。</span><span class="sxs-lookup"><span data-stu-id="76962-190">6. Review and turn on the rule.</span></span>
<span data-ttu-id="76962-191">检查规则后，单击 "**创建**" 以保存该规则。</span><span class="sxs-lookup"><span data-stu-id="76962-191">After reviewing the rule, click **Create** to save it.</span></span> <span data-ttu-id="76962-192">自定义检测规则将立即运行。</span><span class="sxs-lookup"><span data-stu-id="76962-192">The custom detection rule immediately runs.</span></span> <span data-ttu-id="76962-193">它将根据配置的频率再次运行，以检查匹配项、生成警报并采取响应操作。</span><span class="sxs-lookup"><span data-stu-id="76962-193">It runs again based on configured frequency to check for matches, generate alerts, and take response actions.</span></span>

## <a name="manage-existing-custom-detection-rules"></a><span data-ttu-id="76962-194">管理现有的自定义检测规则</span><span class="sxs-lookup"><span data-stu-id="76962-194">Manage existing custom detection rules</span></span>
<span data-ttu-id="76962-195">您可以查看现有的自定义检测规则的列表，检查其以前的运行，并查看它们触发的警报。</span><span class="sxs-lookup"><span data-stu-id="76962-195">You can view the list of existing custom detection rules, check their previous runs, and review the alerts they have triggered.</span></span> <span data-ttu-id="76962-196">您还可以按需运行规则并对其进行修改。</span><span class="sxs-lookup"><span data-stu-id="76962-196">You can also run a rule on demand and modify it.</span></span>

### <a name="view-existing-rules"></a><span data-ttu-id="76962-197">查看现有规则</span><span class="sxs-lookup"><span data-stu-id="76962-197">View existing rules</span></span>

<span data-ttu-id="76962-198">若要查看所有现有的自定义检测规则，请导航到 "**搜寻**  >  **自定义**检测"。</span><span class="sxs-lookup"><span data-stu-id="76962-198">To view all existing custom detection rules, navigate to **Hunting** > **Custom detections**.</span></span> <span data-ttu-id="76962-199">页面列出了包含以下运行信息的所有规则：</span><span class="sxs-lookup"><span data-stu-id="76962-199">The page lists all the rules with the following run information:</span></span>

- <span data-ttu-id="76962-200">**上次运行**时间—上次运行规则以检查查询匹配项并生成警报</span><span class="sxs-lookup"><span data-stu-id="76962-200">**Last run** — when a rule was last run to check for query matches and generate alerts</span></span>
- <span data-ttu-id="76962-201">**上次运行状态**—规则是否成功运行</span><span class="sxs-lookup"><span data-stu-id="76962-201">**Last run status** — whether a rule ran successfully</span></span>
- <span data-ttu-id="76962-202">**下次运行**—下一次计划的运行</span><span class="sxs-lookup"><span data-stu-id="76962-202">**Next run** — the next scheduled run</span></span>
- <span data-ttu-id="76962-203">**状态**—是否已打开或关闭规则</span><span class="sxs-lookup"><span data-stu-id="76962-203">**Status** — whether a rule has been turned on or off</span></span>

### <a name="view-rule-details-modify-rule-and-run-rule"></a><span data-ttu-id="76962-204">查看规则详细信息、修改规则和运行规则</span><span class="sxs-lookup"><span data-stu-id="76962-204">View rule details, modify rule, and run rule</span></span>

<span data-ttu-id="76962-205">若要查看有关自定义检测规则的完整信息，请从 "**搜寻**  >  **自定义检测**" 中的规则列表中选择规则的名称。</span><span class="sxs-lookup"><span data-stu-id="76962-205">To view comprehensive information about a custom detection rule, select the name of rule from the list of rules in **Hunting** > **Custom detections**.</span></span> <span data-ttu-id="76962-206">这将打开有关该规则的常规信息的自定义检测规则页面，包括警报、运行状态和范围的详细信息。</span><span class="sxs-lookup"><span data-stu-id="76962-206">This opens a page about the custom detection rule with general information about the rule, including the details of the alert, run status, and scope.</span></span> <span data-ttu-id="76962-207">它还提供触发警报和触发操作的列表。</span><span class="sxs-lookup"><span data-stu-id="76962-207">It also provides the list of triggered alerts and triggered actions.</span></span>

<span data-ttu-id="76962-208">!["自定义检测规则详细信息" 页](../../media/custom-detection-details.png)</span><span class="sxs-lookup"><span data-stu-id="76962-208">![Custom detection rule details page](../../media/custom-detection-details.png)</span></span><br>
<span data-ttu-id="76962-209">*自定义检测规则详细信息*</span><span class="sxs-lookup"><span data-stu-id="76962-209">*Custom detection rule details*</span></span>

<span data-ttu-id="76962-210">此外，还可以对此页面中的规则执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="76962-210">You can also take the following actions on the rule from this page:</span></span>

- <span data-ttu-id="76962-211">**运行**—立即运行该规则。</span><span class="sxs-lookup"><span data-stu-id="76962-211">**Run** — run the rule immediately.</span></span> <span data-ttu-id="76962-212">这还会重置下一次运行的时间间隔。</span><span class="sxs-lookup"><span data-stu-id="76962-212">This also resets the interval for the next run.</span></span>
- <span data-ttu-id="76962-213">**编辑**—在不更改查询的情况下修改规则</span><span class="sxs-lookup"><span data-stu-id="76962-213">**Edit** — modify the rule without changing the query</span></span>
- <span data-ttu-id="76962-214">**修改查询**—在高级搜寻中编辑查询</span><span class="sxs-lookup"><span data-stu-id="76962-214">**Modify query** — edit the query in advanced hunting</span></span>
- <span data-ttu-id="76962-215">**打开**  / **关闭**—启用或停止运行规则</span><span class="sxs-lookup"><span data-stu-id="76962-215">**Turn on** / **Turn off** — enable the rule or stop it from running</span></span>
- <span data-ttu-id="76962-216">**删除**-关闭规则并将其删除</span><span class="sxs-lookup"><span data-stu-id="76962-216">**Delete** — turn off the rule and remove it</span></span>

### <a name="view-and-manage-triggered-alerts"></a><span data-ttu-id="76962-217">查看和管理触发的警报</span><span class="sxs-lookup"><span data-stu-id="76962-217">View and manage triggered alerts</span></span>

<span data-ttu-id="76962-218">在 "规则详细信息" 屏幕**中 (**  >  搜索**自定义检测**  >  **[规则名称]**) 中，转到 "**触发警报**" 以查看与该规则匹配生成的警报列表。</span><span class="sxs-lookup"><span data-stu-id="76962-218">In the rule details screen (**Hunting** > **Custom detections** > **[Rule name]**), go to **Triggered alerts** to view the list of alerts generated by matches to the rule.</span></span> <span data-ttu-id="76962-219">选择一个警报以查看有关该通知的详细信息，并对该警报执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="76962-219">Select an alert to view detailed information about that alert and take the following actions on that alert:</span></span>

- <span data-ttu-id="76962-220">通过将警报的状态和分类设置 (true 或 false 警报来管理警报) </span><span class="sxs-lookup"><span data-stu-id="76962-220">Manage the alert by setting its status and classification (true or false alert)</span></span>
- <span data-ttu-id="76962-221">将警报链接到事件</span><span class="sxs-lookup"><span data-stu-id="76962-221">Link the alert to an incident</span></span>
- <span data-ttu-id="76962-222">在高级搜寻中运行触发警报的查询</span><span class="sxs-lookup"><span data-stu-id="76962-222">Run the query that triggered the alert on advanced hunting</span></span>

### <a name="review-actions"></a><span data-ttu-id="76962-223">查看操作</span><span class="sxs-lookup"><span data-stu-id="76962-223">Review actions</span></span>
<span data-ttu-id="76962-224">在 "规则详细信息" 屏幕**中 (**  >  搜索**自定义检测**  >  **[规则名称]**) 中，转到 "**触发操作**" 以查看基于与规则的匹配项所执行的操作的列表。</span><span class="sxs-lookup"><span data-stu-id="76962-224">In the rule details screen (**Hunting** > **Custom detections** > **[Rule name]**), go to **Triggered actions** to view the list of actions taken based on matches to the rule.</span></span>

>[!TIP]
><span data-ttu-id="76962-225">若要快速查看信息并对表中的项目执行操作，请使用表左侧的选择列 [&#10003;]。</span><span class="sxs-lookup"><span data-stu-id="76962-225">To quickly view information and take action on an item in a table, use the selection column [&#10003;] at the left of the table.</span></span>

## <a name="related-topic"></a><span data-ttu-id="76962-226">相关主题</span><span class="sxs-lookup"><span data-stu-id="76962-226">Related topic</span></span>
- [<span data-ttu-id="76962-227">自定义检测概述</span><span class="sxs-lookup"><span data-stu-id="76962-227">Custom detections overview</span></span>](custom-detections-overview.md)
- [<span data-ttu-id="76962-228">高级搜寻概述</span><span class="sxs-lookup"><span data-stu-id="76962-228">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="76962-229">了解高级搜寻查询语言</span><span class="sxs-lookup"><span data-stu-id="76962-229">Learn the advanced hunting query language</span></span>](advanced-hunting-query-language.md)