---
title: Microsoft 365 本地扫描仪数据丢失防护入门（预览）
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 07/21/2020
audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MET150
description: 设置 Microsoft 365 本地扫描仪数据丢失防护
ms.openlocfilehash: e0d7bc9eeae7d701c14aaaeeed7a01cab33829ea
ms.sourcegitcommit: 070724118be25cd83418d2a56863da95582dae65
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/03/2021
ms.locfileid: "50417337"
---
# <a name="get-started-with-the-data-loss-prevention-on-premises-scanner-preview"></a><span data-ttu-id="e933f-103">开始进行本地扫描仪的数据丢失防护（预览）</span><span class="sxs-lookup"><span data-stu-id="e933f-103">Get started with the data loss prevention on-premises scanner (preview)</span></span>

<span data-ttu-id="e933f-104">本文将引导你完成 Microsoft 365 本地扫描仪数据丢失防护的先决条件和配置。</span><span class="sxs-lookup"><span data-stu-id="e933f-104">This article walks you through the prerequisites and configuration for the Microsoft 365 data loss prevention on-premises scanner.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="e933f-105">准备工作</span><span class="sxs-lookup"><span data-stu-id="e933f-105">Before you begin</span></span>

### <a name="skusubscriptions-licensing"></a><span data-ttu-id="e933f-106">SKU/订阅许可</span><span class="sxs-lookup"><span data-stu-id="e933f-106">SKU/subscriptions licensing</span></span>

<span data-ttu-id="e933f-107">在开始使用终结点 DLP 之前，应该先确认 [Microsoft 365 订阅](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)以及任何加载项。</span><span class="sxs-lookup"><span data-stu-id="e933f-107">Before you get started with DLP on-premises scanner, you should confirm your [Microsoft 365 subscription](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1) and any add-ons.</span></span> <span data-ttu-id="e933f-108">若要参与预览版，设置 DLP 规则的管理员帐户必须分配以下其中一个许可证：</span><span class="sxs-lookup"><span data-stu-id="e933f-108">To participate in the preview the admin account that sets up the DLP rules must be assigned one of the following licenses:</span></span>

- <span data-ttu-id="e933f-109">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="e933f-109">Microsoft 365 E5</span></span>
- <span data-ttu-id="e933f-110">Microsoft 365 E5 合规</span><span class="sxs-lookup"><span data-stu-id="e933f-110">Microsoft 365 E5 Compliance</span></span>
- <span data-ttu-id="e933f-111">Microsoft 365 E5 信息保护和管控</span><span class="sxs-lookup"><span data-stu-id="e933f-111">Microsoft 365 E5 Information Protection & Governance</span></span> 


<span data-ttu-id="e933f-112">有关许可的详细信息，请参阅[适用于安全与合规性的 Microsoft 365 许可指南](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)。</span><span class="sxs-lookup"><span data-stu-id="e933f-112">For full licensing details see: [Microsoft 365 licensing guidance for security & compliance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)</span></span>

### <a name="permissions"></a><span data-ttu-id="e933f-113">权限</span><span class="sxs-lookup"><span data-stu-id="e933f-113">Permissions</span></span>


<span data-ttu-id="e933f-114">可在[活动资源管理器](data-classification-activity-explorer.md)中查看终结点 DLP 中的数据。</span><span class="sxs-lookup"><span data-stu-id="e933f-114">Data from DLP on-premises scanner can be viewed in [Activity explorer](data-classification-activity-explorer.md).</span></span> <span data-ttu-id="e933f-115">有四个角色可向活动资源管理器授予权限，用于访问数据的帐户必须是其中任何一个的成员。</span><span class="sxs-lookup"><span data-stu-id="e933f-115">There are four roles that grant permission to activity explorer, the account you use for accessing the data must be a member of any one of them.</span></span>

- <span data-ttu-id="e933f-116">全局管理员</span><span class="sxs-lookup"><span data-stu-id="e933f-116">Global administrator</span></span>
- <span data-ttu-id="e933f-117">合规性管理员</span><span class="sxs-lookup"><span data-stu-id="e933f-117">Compliance administrator</span></span>
- <span data-ttu-id="e933f-118">安全管理员</span><span class="sxs-lookup"><span data-stu-id="e933f-118">Security administrator</span></span>
- <span data-ttu-id="e933f-119">合规性数据管理员</span><span class="sxs-lookup"><span data-stu-id="e933f-119">Compliance data administrator</span></span>

### <a name="dlp-on-premises-scanner-prerequisites"></a><span data-ttu-id="e933f-120">DLP 本地扫描仪先决条件</span><span class="sxs-lookup"><span data-stu-id="e933f-120">DLP on-premises scanner prerequisites</span></span>

- <span data-ttu-id="e933f-121">Azure 信息保护 （AIP） 扫描仪实现 DLP 策略匹配和策略执行。</span><span class="sxs-lookup"><span data-stu-id="e933f-121">The Azure Information Protection (AIP) scanner implements DLP policy matching and policy enforcement.</span></span> <span data-ttu-id="e933f-122">将扫描仪作为 AIP 客户端的一部分进行安装，因此安装必须满足 AIP、AIP 客户端和 AIP 统一标签扫描仪的所有先决条件。</span><span class="sxs-lookup"><span data-stu-id="e933f-122">The scanner is installed as part of the AIP client so your installation must meet all the prerequisites  for AIP, the AIP client, and the AIP unified labeling scanner.</span></span>
- <span data-ttu-id="e933f-123">部署 AIP 客户端和扫描仪。</span><span class="sxs-lookup"><span data-stu-id="e933f-123">Deploy the AIP  client and scanner.</span></span> <span data-ttu-id="e933f-124">若要详细了解 [AIP 统一标签客户端](https://docs.microsoft.com/azure/information-protection/rms-client/install-unifiedlabelingclient-app) 和 []，请参阅 [配置和安装 Azure 信息保护统一标签扫描仪](https://docs.microsoft.com/azure/information-protection/deploy-aip-scanner-configure-install)。</span><span class="sxs-lookup"><span data-stu-id="e933f-124">For more information [Install the AIP unified labeling client](https://docs.microsoft.com/azure/information-protection/rms-client/install-unifiedlabelingclient-app) and [], see [Configuring and installing the Azure Information Protection unified labeling scanner](https://docs.microsoft.com/azure/information-protection/deploy-aip-scanner-configure-install).</span></span>
- <span data-ttu-id="e933f-125">必须至少在租户中发布一个标签和策略，即使所有检测规则都只基于敏感信息类型。</span><span class="sxs-lookup"><span data-stu-id="e933f-125">There must be at least one label and policy published in the tenant, even if all your detection rules are based on sensitive information types only.</span></span>

## <a name="deploy-the-dlp-on-premises-scanner"></a><span data-ttu-id="e933f-126">部署 DLP 本地扫描仪</span><span class="sxs-lookup"><span data-stu-id="e933f-126">Deploy the DLP on-premises scanner</span></span>

1. <span data-ttu-id="e933f-127">请按照 [安装AIP统一标签客户端](https://docs.microsoft.com/azure/information-protection/rms-client/install-unifiedlabelingclient-app)中的过程。</span><span class="sxs-lookup"><span data-stu-id="e933f-127">Follow the procedures in [Install the AIP unified labeling client](https://docs.microsoft.com/azure/information-protection/rms-client/install-unifiedlabelingclient-app).</span></span> 
2. <span data-ttu-id="e933f-128">按照以下过程 [安装 Azure 信息保护统一标签扫描仪](https://docs.microsoft.com/azure/information-protection/deploy-aip-scanner-configure-install) 完成扫描仪安装。</span><span class="sxs-lookup"><span data-stu-id="e933f-128">Follow the procedures in [Configuring and installing the Azure Information Protection unified labeling scanner](https://docs.microsoft.com/azure/information-protection/deploy-aip-scanner-configure-install) to complete the scanner installation.</span></span>
    1. <span data-ttu-id="e933f-129">网络发现作业配置是一个可选步骤。</span><span class="sxs-lookup"><span data-stu-id="e933f-129">Network discovery jobs configuration is an optional step.</span></span> <span data-ttu-id="e933f-130">可以跳过它，并定义要扫描内容扫描作业的特定存储库。</span><span class="sxs-lookup"><span data-stu-id="e933f-130">You can skip it and define specific repositories to be scanned in your content scan job.</span></span>
    2. <span data-ttu-id="e933f-131">必须创建内容扫描作业，并指定 DLP 引擎需要评估的托管文件的存储库。</span><span class="sxs-lookup"><span data-stu-id="e933f-131">You must create content scan job and specify the repositories that host files that need to be evaluated by the DLP engine.</span></span>
    3. <span data-ttu-id="e933f-132">在已创建的内容扫描作业中启用 DLP 规则，将 **强制** 选项设置为 **关闭**，除非想要直接进入 DLP 强制阶段。</span><span class="sxs-lookup"><span data-stu-id="e933f-132">Enable DLP rules in the created Content scan job, and set the **Enforce** option to **Off**, unless you want to proceed directly to the DLP enforcement stage.</span></span>
3. <span data-ttu-id="e933f-133">验证内容扫描作业是否分配给了右群集。</span><span class="sxs-lookup"><span data-stu-id="e933f-133">Verify that you content scan job is assigned to the right cluster.</span></span> <span data-ttu-id="e933f-134">如果仍未创建内容扫描作业，请创建新的扫描作业，将其分配到包含运行公共预览版本的扫描仪节点的群集。</span><span class="sxs-lookup"><span data-stu-id="e933f-134">If you still did not create a content scan job create a new one and assign it to the cluster that contains the scanner nodes that run the public preview version.</span></span>

4. <span data-ttu-id="e933f-135">连接到 Azure 门户 [Azure 信息保护扩展](https://portal.azure.com/#blade/Microsoft_Azure_InformationProtection/DataClassGroupEditBlade/scannerProfilesBlade) 将存储库添加到将执行扫描的内容扫描作业。</span><span class="sxs-lookup"><span data-stu-id="e933f-135">Connect to the [Azure Information Protection extension in Azure portal](https://portal.azure.com/#blade/Microsoft_Azure_InformationProtection/DataClassGroupEditBlade/scannerProfilesBlade) and add your repositories to the content scan job that will perform the scan.</span></span>

5. <span data-ttu-id="e933f-136">执行下列操作之一以运行扫描：</span><span class="sxs-lookup"><span data-stu-id="e933f-136">Do one of the following to run your scan:</span></span>
    1. <span data-ttu-id="e933f-137">设置扫描仪计划</span><span class="sxs-lookup"><span data-stu-id="e933f-137">set the scanner schedule</span></span>
    1. <span data-ttu-id="e933f-138">在门户 **手动** 立即扫描"选项</span><span class="sxs-lookup"><span data-stu-id="e933f-138">use the manual **Scan Now** option in the portal</span></span>
    1. <span data-ttu-id="e933f-139">或运行 **-AIPScan** PowerShell cmdlet</span><span class="sxs-lookup"><span data-stu-id="e933f-139">or run **Start-AIPScan** PowerShell cmdlet</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="e933f-140">请记住，默认情况下，扫描仪运行存储库的增量扫描，并且会跳过在上一扫描周期中扫描的文件，除非文件发生更改或启动完全重新扫描。</span><span class="sxs-lookup"><span data-stu-id="e933f-140">Remember that the scanner runs a delta scan of the repository by default and the files that were already scanned in the previous scan cycle will be skipped unless the file was changed or you initiated a full rescan.</span></span> <span data-ttu-id="e933f-141">可以通过使用UI中的 **“重新扫描所有文件”** 选项或通过运行 **Start-AIPScan-Reset** 来启动完全重新扫描。</span><span class="sxs-lookup"><span data-stu-id="e933f-141">Full rescan can be initiated by using **Rescan all files** option in the UI or by running **Start-AIPScan-Reset**.</span></span>

6.  <span data-ttu-id="e933f-142">在 Microsoft 365 合规性管理中心中，打开“[数据丢失防护页面](https://compliance.microsoft.com/datalossprevention?viewid=policies)”。</span><span class="sxs-lookup"><span data-stu-id="e933f-142">Open the [Data loss prevention page](https://compliance.microsoft.com/datalossprevention?viewid=policies) in the Microsoft 365 Compliance center.</span></span>

7. <span data-ttu-id="e933f-143">选择 **创建策略** 并创建测试 DLP 策略。</span><span class="sxs-lookup"><span data-stu-id="e933f-143">Choose **Create policy** and create a test DLP policy.</span></span> <span data-ttu-id="e933f-144">如果你需要 [帮助创建策略，请参阅](create-a-dlp-policy-from-a-template.md) 模板创建 DLP 策略。</span><span class="sxs-lookup"><span data-stu-id="e933f-144">See [Create a DLP policy from a template](create-a-dlp-policy-from-a-template.md) if you need help creating a policy.</span></span> <span data-ttu-id="e933f-145">请务必在测试中运行它，直到熟悉此功能。</span><span class="sxs-lookup"><span data-stu-id="e933f-145">Be sure to run it in test until you are comfortable with this feature.</span></span> <span data-ttu-id="e933f-146">将以下参数用于策略：</span><span class="sxs-lookup"><span data-stu-id="e933f-146">Use these parameters for your policy:</span></span>
    1. <span data-ttu-id="e933f-147">如有必要，将 DLP 本地扫描仪规则的范围设置到特定位置。</span><span class="sxs-lookup"><span data-stu-id="e933f-147">Scope the DLP on-premises scanner rule to specific locations if needed.</span></span> <span data-ttu-id="e933f-148">如果将扫描 **的位置\*\*\*\*所有**，则通过扫描仪扫描的所有文件将受制于 DLP 规则匹配和强制。</span><span class="sxs-lookup"><span data-stu-id="e933f-148">If you scope **locations** to **All**, all files scanned by the scanner will be subject to the DLP rule matching and enforcement.</span></span>
    1. <span data-ttu-id="e933f-149">指定位置时，可以使用排除列表或包含列表。</span><span class="sxs-lookup"><span data-stu-id="e933f-149">When specifying the locations, you can use either exclusion or inclusion list.</span></span> <span data-ttu-id="e933f-150">在公共预览期间，不能同时设置两者。</span><span class="sxs-lookup"><span data-stu-id="e933f-150">During public preview you cannot set both of them.</span></span> <span data-ttu-id="e933f-151">可定义规则仅与包含列表中列出的其中一个模式相匹配的路径相关，与包含列表中列出的所有文件（与包含列表中列出的模式相匹配的文件除外）的所有文件除外。</span><span class="sxs-lookup"><span data-stu-id="e933f-151">You can either define that the rule is relevant only to paths matching one of the patterns listed in inclusion list or, all files, except the files matching the pattern listed in inclusion list.</span></span> <span data-ttu-id="e933f-152">不支持任何本地路径。</span><span class="sxs-lookup"><span data-stu-id="e933f-152">No local paths are supported.</span></span> <span data-ttu-id="e933f-153">以下是一些有效路径的示例：</span><span class="sxs-lookup"><span data-stu-id="e933f-153">Here are some examples of valid paths:</span></span>
      - <span data-ttu-id="e933f-154">\\\server\share</span><span class="sxs-lookup"><span data-stu-id="e933f-154">\\\server\share</span></span>
      - <span data-ttu-id="e933f-155">\\\server\share\folder1\subfolderabc</span><span class="sxs-lookup"><span data-stu-id="e933f-155">\\\server\share\folder1\subfolderabc</span></span>
      - <span data-ttu-id="e933f-156">\*\\folder1</span><span class="sxs-lookup"><span data-stu-id="e933f-156">\*\\folder1</span></span>
      - <span data-ttu-id="e933f-157">\*secret\*.docx</span><span class="sxs-lookup"><span data-stu-id="e933f-157">\*secret\*.docx</span></span>
      - <span data-ttu-id="e933f-158">\*secret\*.\*</span><span class="sxs-lookup"><span data-stu-id="e933f-158">\*secret\*.\*</span></span>
      - <span data-ttu-id="e933f-159"> https:// sp2010.local/sites/HR</span><span class="sxs-lookup"><span data-stu-id="e933f-159">https:// sp2010.local/sites/HR</span></span>
      - <span data-ttu-id="e933f-160"> https://\*/HR</span><span class="sxs-lookup"><span data-stu-id="e933f-160">https://\*/HR</span></span> 
    3. <span data-ttu-id="e933f-161">以下是使用不可接受的值的一些示例：</span><span class="sxs-lookup"><span data-stu-id="e933f-161">Here are some examples of unacceptable values use:</span></span>
      - \*
      - <span data-ttu-id="e933f-162">\*\\a</span><span class="sxs-lookup"><span data-stu-id="e933f-162">\*\\a</span></span>
      - <span data-ttu-id="e933f-163">Aaa</span><span class="sxs-lookup"><span data-stu-id="e933f-163">Aaa</span></span>
      - <span data-ttu-id="e933f-164">c:</span><span class="sxs-lookup"><span data-stu-id="e933f-164">c:</span></span>\
      - <span data-ttu-id="e933f-165">C:\test</span><span class="sxs-lookup"><span data-stu-id="e933f-165">C:\test</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e933f-166">排除列表优先于包含项列表。</span><span class="sxs-lookup"><span data-stu-id="e933f-166">The exclusion list takes precedence over the inclusions list.</span></span>

### <a name="viewing-dlp-on-premises-scanner-alerts-in-dlp-alerts-management-dashboard"></a><span data-ttu-id="e933f-167">在 DLP Alerts 管理仪表板中查看 DLP 本地扫描仪警报</span><span class="sxs-lookup"><span data-stu-id="e933f-167">Viewing DLP on-premises scanner alerts in DLP Alerts Management dashboard</span></span>

1. <span data-ttu-id="e933f-168">在 Microsoft 365 合规 [打开](https://compliance.microsoft.com/datalossprevention?viewid=policies) 数据丢失防护"页面，然后选择 **警报**。</span><span class="sxs-lookup"><span data-stu-id="e933f-168">Open the [Data loss prevention page](https://compliance.microsoft.com/datalossprevention?viewid=policies) in the Microsoft 365 Compliance center and select **Alerts**.</span></span>

2. <span data-ttu-id="e933f-169">请参阅 [如何配置和查看 DLP 策略的警报](dlp-configure-view-alerts-policies.md) 中的过程，以查看你的终结点 DLP 策略警报。</span><span class="sxs-lookup"><span data-stu-id="e933f-169">Refer to the procedures in [How to configure and view alerts for your DLP policies](dlp-configure-view-alerts-policies.md) to view alerts for your Endpoint DLP policies.</span></span>

### <a name="viewing-dlp-on-premises-scanner-in-activity-explorer-and-audit-log"></a><span data-ttu-id="e933f-170">在活动资源管理器中查看 DLP 本地扫描仪和审核日志</span><span class="sxs-lookup"><span data-stu-id="e933f-170">Viewing DLP on-premises scanner in activity explorer and audit log</span></span>

> [!NOTE]
> <span data-ttu-id="e933f-171">需要启用审核。本地扫描仪需要启用审核。</span><span class="sxs-lookup"><span data-stu-id="e933f-171">The on-premises scanner requires that auditing be enabled.</span></span> <span data-ttu-id="e933f-172">在 Microsoft 365 中，默认启用审核。</span><span class="sxs-lookup"><span data-stu-id="e933f-172">In Microsoft 365 auditing is enabled by default.</span></span>

1. <span data-ttu-id="e933f-173">在 Microsoft 365 合规 [打开域](https://compliance.microsoft.com/dataclassification?viewid=overview) 数据分类页面，然后选择活动资源管理器。</span><span class="sxs-lookup"><span data-stu-id="e933f-173">Open the [Data classification page](https://compliance.microsoft.com/dataclassification?viewid=overview) for your domain in the Microsoft 365 Compliance center and select Activity explorer.</span></span>

2. <span data-ttu-id="e933f-174">请参阅活动 [工具入门](data-classification-activity-explorer.md) 中的过程，以访问和筛选本地扫描仪位置的所有数据。</span><span class="sxs-lookup"><span data-stu-id="e933f-174">Refer to the procedures in [Get started with Activity explorer](data-classification-activity-explorer.md) to access and filter all the data for your on-premises scanner locations.</span></span>

3. <span data-ttu-id="e933f-175">在合规 [中打开"审核"](https://security.microsoft.com/auditlogsearch)。</span><span class="sxs-lookup"><span data-stu-id="e933f-175">Open the [Audit log in the Compliance center](https://security.microsoft.com/auditlogsearch).</span></span> <span data-ttu-id="e933f-176">在公共预览期间，DLP 规则匹配项在审核日志 UI 中可用，或由 [Search-UnifiedAuditLog](https://docs.microsoft.com/powershell/module/exchange/search-unifiedauditlog?view=exchange-ps) PowerShell 访问</span><span class="sxs-lookup"><span data-stu-id="e933f-176">During the public preview the DLP rule matches are available in Audit log UI or accessible by [Search-UnifiedAuditLog](https://docs.microsoft.com/powershell/module/exchange/search-unifiedauditlog?view=exchange-ps) PowerShell</span></span> 


## <a name="next-steps"></a><span data-ttu-id="e933f-177">后续步骤</span><span class="sxs-lookup"><span data-stu-id="e933f-177">Next steps</span></span>
<span data-ttu-id="e933f-178">现在，你已载入设备，并且可以在“活动资源管理器”中查看活动数据，那么就可以继续下一步，在其中创建保护敏感项目的 DLP 策略。</span><span class="sxs-lookup"><span data-stu-id="e933f-178">Now that you have deployed a test policy for DLP on-premises locations and can view the activity data in Activity explorer, you are ready to move on to your next step where you create DLP policies that protect your sensitive items.</span></span>

- [<span data-ttu-id="e933f-179">使用本地 DLP（预览）</span><span class="sxs-lookup"><span data-stu-id="e933f-179">Using DLP on-premises (preview)</span></span>](dlp-on-premises-scanner-use.md)

## <a name="see-also"></a><span data-ttu-id="e933f-180">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e933f-180">See also</span></span>

- [<span data-ttu-id="e933f-181">了解 DLP 本地扫描仪（预览）</span><span class="sxs-lookup"><span data-stu-id="e933f-181">Learn about DLP on-premises scanner (preview)</span></span>](dlp-on-premises-scanner-learn.md)
- [<span data-ttu-id="e933f-182">使用 DLP 本地扫描仪（预览）</span><span class="sxs-lookup"><span data-stu-id="e933f-182">Use DLP on-premises scanner (preview)</span></span>](dlp-on-premises-scanner-use.md)
- [<span data-ttu-id="e933f-183">数据丢失防护概述</span><span class="sxs-lookup"><span data-stu-id="e933f-183">Overview of data loss prevention</span></span>](data-loss-prevention-policies.md)
- [<span data-ttu-id="e933f-184">创建、测试和优化 DLP 策略</span><span class="sxs-lookup"><span data-stu-id="e933f-184">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)
- [<span data-ttu-id="e933f-185">活动资源管理器入门</span><span class="sxs-lookup"><span data-stu-id="e933f-185">Get started with Activity explorer</span></span>](data-classification-activity-explorer.md)
- [<span data-ttu-id="e933f-186">Microsoft 365 订阅</span><span class="sxs-lookup"><span data-stu-id="e933f-186">Microsoft 365 subscription</span></span>](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)
