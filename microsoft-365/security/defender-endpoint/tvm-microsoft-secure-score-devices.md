---
title: Microsoft 设备安全分数
description: 你的设备分数显示设备在应用程序、操作系统、网络、帐户和安全控件中的统一安全配置状态。
keywords: Microsoft 设备安全分数， mdatp Microsoft 设备安全分数， 安全分数， 配置分数， 威胁和漏洞管理， 安全控制， 改进机会， 一段时间的安全配置分数， 安全状况， 基线
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: ellevin
author: levinec
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: d9ccd4f7dcc8b1546772a756aaf850dadfc87905
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51055330"
---
# <a name="microsoft-secure-score-for-devices"></a><span data-ttu-id="696ae-104">Microsoft 设备安全分数</span><span class="sxs-lookup"><span data-stu-id="696ae-104">Microsoft Secure Score for Devices</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="696ae-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="696ae-105">**Applies to:**</span></span>

- [<span data-ttu-id="696ae-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="696ae-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="696ae-107">威胁和漏洞管理</span><span class="sxs-lookup"><span data-stu-id="696ae-107">Threat and vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="696ae-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="696ae-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="696ae-109">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="696ae-109">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="696ae-110">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="696ae-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 


>[!NOTE]
> <span data-ttu-id="696ae-111">配置分数现在是威胁和漏洞管理的一部分，作为 Microsoft 设备安全分数。</span><span class="sxs-lookup"><span data-stu-id="696ae-111">Configuration score is now part of threat and vulnerability management as Microsoft Secure Score for Devices.</span></span>

<span data-ttu-id="696ae-112">你的设备分数显示在 Microsoft Defender[](tvm-dashboard-insights.md)安全中心的威胁和漏洞管理仪表板中。</span><span class="sxs-lookup"><span data-stu-id="696ae-112">Your score for devices is visible in the [threat and vulnerability management dashboard](tvm-dashboard-insights.md) of the Microsoft Defender Security Center.</span></span> <span data-ttu-id="696ae-113">设备的 Microsoft 安全分数越高，你的终结点就更能够抵御网络安全威胁攻击。</span><span class="sxs-lookup"><span data-stu-id="696ae-113">A higher Microsoft Secure Score for Devices means your endpoints are more resilient from cybersecurity threat attacks.</span></span> <span data-ttu-id="696ae-114">它反映你的设备跨以下类别的安全配置状态：</span><span class="sxs-lookup"><span data-stu-id="696ae-114">It reflects the collective security configuration state of your devices across the following categories:</span></span>

- <span data-ttu-id="696ae-115">Application</span><span class="sxs-lookup"><span data-stu-id="696ae-115">Application</span></span>
- <span data-ttu-id="696ae-116">操作系统</span><span class="sxs-lookup"><span data-stu-id="696ae-116">Operating system</span></span>
- <span data-ttu-id="696ae-117">网络</span><span class="sxs-lookup"><span data-stu-id="696ae-117">Network</span></span>
- <span data-ttu-id="696ae-118">帐户</span><span class="sxs-lookup"><span data-stu-id="696ae-118">Accounts</span></span>
- <span data-ttu-id="696ae-119">安全控件</span><span class="sxs-lookup"><span data-stu-id="696ae-119">Security controls</span></span>

<span data-ttu-id="696ae-120">选择类别以转到" [**安全建议"页**](tvm-security-recommendation.md) 并查看相关建议。</span><span class="sxs-lookup"><span data-stu-id="696ae-120">Select a category to go to the [**Security recommendations**](tvm-security-recommendation.md) page and view the relevant recommendations.</span></span>

## <a name="turn-on-the-microsoft-secure-score-connector"></a><span data-ttu-id="696ae-121">打开 Microsoft 安全分数连接器</span><span class="sxs-lookup"><span data-stu-id="696ae-121">Turn on the Microsoft Secure Score connector</span></span>

<span data-ttu-id="696ae-122">转发 Microsoft Defender for Endpoint 信号，使 Microsoft 安全分数能够查看设备安全状态。</span><span class="sxs-lookup"><span data-stu-id="696ae-122">Forward Microsoft Defender for Endpoint signals, giving Microsoft Secure Score visibility into the device security posture.</span></span> <span data-ttu-id="696ae-123">转发数据的存储和处理位置与 Microsoft 安全分数数据位于同一位置。</span><span class="sxs-lookup"><span data-stu-id="696ae-123">Forwarded data is stored and processed in the same location as your Microsoft Secure Score data.</span></span>

<span data-ttu-id="696ae-124">更改可能需要几个小时才能反映在仪表板中。</span><span class="sxs-lookup"><span data-stu-id="696ae-124">Changes might take up to a few hours to reflect in the dashboard.</span></span>

1. <span data-ttu-id="696ae-125">在导航窗格中，**转到"设置**  >  **""高级功能"**</span><span class="sxs-lookup"><span data-stu-id="696ae-125">In the navigation pane, go to **Settings** > **Advanced features**</span></span> 

2. <span data-ttu-id="696ae-126">向下滚动到 **Microsoft 安全分数**，将设置切换为 **"打开"。**</span><span class="sxs-lookup"><span data-stu-id="696ae-126">Scroll down to **Microsoft Secure Score** and toggle the setting to **On**.</span></span>

3. <span data-ttu-id="696ae-127">选择 **保存首选项**。</span><span class="sxs-lookup"><span data-stu-id="696ae-127">Select **Save preferences**.</span></span>

## <a name="how-it-works"></a><span data-ttu-id="696ae-128">运作方式</span><span class="sxs-lookup"><span data-stu-id="696ae-128">How it works</span></span>

>[!NOTE]
> <span data-ttu-id="696ae-129">Microsoft 设备安全分数当前支持通过组策略设置的配置。</span><span class="sxs-lookup"><span data-stu-id="696ae-129">Microsoft Secure Score for Devices currently supports configurations set via Group Policy.</span></span> <span data-ttu-id="696ae-130">由于当前部分 Intune 支持，可能通过 Intune 设置的配置可能会显示为错误配置。</span><span class="sxs-lookup"><span data-stu-id="696ae-130">Due to the current partial Intune support, configurations which might have been set through Intune might show up as misconfigured.</span></span> <span data-ttu-id="696ae-131">如果组织使用 Intune 进行安全配置管理，请与 IT 管理员联系以验证实际配置状态。</span><span class="sxs-lookup"><span data-stu-id="696ae-131">Contact your IT Administrator to verify the actual configuration status in case your organization is using Intune for secure configuration management.</span></span>

<span data-ttu-id="696ae-132">Microsoft 设备安全分数卡中的数据是不断发现漏洞的过程的产品。</span><span class="sxs-lookup"><span data-stu-id="696ae-132">The data in the Microsoft Secure Score for Devices card is the product of meticulous and ongoing vulnerability discovery process.</span></span> <span data-ttu-id="696ae-133">它将与配置发现评估聚合，持续：</span><span class="sxs-lookup"><span data-stu-id="696ae-133">It is aggregated with configuration discovery assessments that continuously:</span></span>

- <span data-ttu-id="696ae-134">将收集的配置与收集的基准进行比较以发现配置不当的资产</span><span class="sxs-lookup"><span data-stu-id="696ae-134">Compare collected configurations to the collected benchmarks to discover misconfigured assets</span></span>
- <span data-ttu-id="696ae-135">将配置映射到可修正或部分修复的漏洞 (风险) </span><span class="sxs-lookup"><span data-stu-id="696ae-135">Map configurations to vulnerabilities that can be remediated or partially remediated (risk reduction)</span></span>
- <span data-ttu-id="696ae-136">收集和维护最佳做法配置基准 (供应商、安全源、内部研究团队) </span><span class="sxs-lookup"><span data-stu-id="696ae-136">Collect and maintain best practice configuration benchmarks (vendors, security feeds, internal research teams)</span></span>
- <span data-ttu-id="696ae-137">收集并监视来自所有资产的安全控制配置状态更改</span><span class="sxs-lookup"><span data-stu-id="696ae-137">Collect and monitor changes of security control configuration state from all assets</span></span>

## <a name="improve-your-security-configuration"></a><span data-ttu-id="696ae-138">改进安全配置</span><span class="sxs-lookup"><span data-stu-id="696ae-138">Improve your security configuration</span></span>

<span data-ttu-id="696ae-139">通过修正安全建议列表中的问题来改进安全配置。</span><span class="sxs-lookup"><span data-stu-id="696ae-139">Improve your security configuration by remediating issues from the security recommendations list.</span></span> <span data-ttu-id="696ae-140">当你这样做时，你的 Microsoft 设备安全分数会提高，并且你的组织可以更加抵御网络安全威胁和漏洞。</span><span class="sxs-lookup"><span data-stu-id="696ae-140">As you do so, your Microsoft Secure Score for Devices improves and your organization becomes more resilient against cybersecurity threats and vulnerabilities.</span></span>

1. <span data-ttu-id="696ae-141">从威胁和漏洞管理仪表板中的"Microsoft 设备安全分数"卡中，选择其中一个类别。</span><span class="sxs-lookup"><span data-stu-id="696ae-141">From the Microsoft Secure Score for Devices card in the threat and vulnerability management dashboard, select the one of the categories.</span></span> <span data-ttu-id="696ae-142">您将查看与类别相关的建议列表。</span><span class="sxs-lookup"><span data-stu-id="696ae-142">You'll view the list of recommendations related to that category.</span></span> <span data-ttu-id="696ae-143">它将你访问" [**安全建议"**](tvm-security-recommendation.md) 页。</span><span class="sxs-lookup"><span data-stu-id="696ae-143">It will take you to the [**Security recommendations**](tvm-security-recommendation.md) page.</span></span> <span data-ttu-id="696ae-144">如果要查看所有安全建议，在进入"安全建议"页面后，清除搜索字段。</span><span class="sxs-lookup"><span data-stu-id="696ae-144">If you want to see all security recommendations, once you get to the Security recommendations page, clear the search field.</span></span>

2. <span data-ttu-id="696ae-145">在列表中选择一个项。</span><span class="sxs-lookup"><span data-stu-id="696ae-145">Select an item on the list.</span></span> <span data-ttu-id="696ae-146">该飞出面板将打开，并包含与建议相关的详细信息。</span><span class="sxs-lookup"><span data-stu-id="696ae-146">The flyout panel will open with details related to the recommendation.</span></span> <span data-ttu-id="696ae-147">选择 **修正选项**。</span><span class="sxs-lookup"><span data-stu-id="696ae-147">Select **Remediation options**.</span></span>

   ![安全控制相关的安全建议](images/tvm_security_controls.png)

3. <span data-ttu-id="696ae-149">阅读说明，了解问题的上下文以及下一步要执行哪些操作。</span><span class="sxs-lookup"><span data-stu-id="696ae-149">Read the description to understand the context of the issue and what to do next.</span></span> <span data-ttu-id="696ae-150">选择截止日期、添加备注，然后选择"将所有修正 **活动** 数据导出到 CSV"，以便你可以将其附加到电子邮件进行跟踪。</span><span class="sxs-lookup"><span data-stu-id="696ae-150">Select a due date, add notes, and select **Export all remediation activity data to CSV** so you can attach it to an email for follow-up.</span></span>

4. <span data-ttu-id="696ae-151">**提交请求**。</span><span class="sxs-lookup"><span data-stu-id="696ae-151">**Submit request**.</span></span> <span data-ttu-id="696ae-152">你将看到一条确认消息，表明已创建修正任务。</span><span class="sxs-lookup"><span data-stu-id="696ae-152">You'll see a confirmation message that the remediation task has been created.</span></span>
   <span data-ttu-id="696ae-153">![修正任务创建确认](images/tvm_remediation_task_created.png)</span><span class="sxs-lookup"><span data-stu-id="696ae-153">![Remediation task creation confirmation](images/tvm_remediation_task_created.png)</span></span>

5. <span data-ttu-id="696ae-154">保存 CSV 文件。</span><span class="sxs-lookup"><span data-stu-id="696ae-154">Save your CSV file.</span></span>
   <span data-ttu-id="696ae-155">![保存 csv 文件](images/tvm_save_csv_file.png)</span><span class="sxs-lookup"><span data-stu-id="696ae-155">![Save csv file](images/tvm_save_csv_file.png)</span></span>

6. <span data-ttu-id="696ae-156">向 IT 管理员发送后续电子邮件，并允许分配修正时间在系统中传播。</span><span class="sxs-lookup"><span data-stu-id="696ae-156">Send a follow-up email to your IT Administrator and allow the time that you've allotted for the remediation to propagate in the system.</span></span>

7. <span data-ttu-id="696ae-157">再次查看 **仪表板上的 Microsoft 设备** 安全分数卡。</span><span class="sxs-lookup"><span data-stu-id="696ae-157">Review the **Microsoft Secure Score for Devices** card again on the dashboard.</span></span> <span data-ttu-id="696ae-158">安全控制建议的数量将减少。</span><span class="sxs-lookup"><span data-stu-id="696ae-158">The number of security controls recommendations will decrease.</span></span> <span data-ttu-id="696ae-159">选择"**安全控件**"返回到"安全建议"页时，已解决的项目不会再列出。</span><span class="sxs-lookup"><span data-stu-id="696ae-159">When you select **Security controls** to go back to the **Security recommendations** page, the item that you've addressed won't be listed there anymore.</span></span> <span data-ttu-id="696ae-160">你的 Microsoft 设备安全分数应增加。</span><span class="sxs-lookup"><span data-stu-id="696ae-160">Your Microsoft Secure Score for Devices should increase.</span></span>

>[!IMPORTANT]
><span data-ttu-id="696ae-161">若要提高漏洞评估检测速率，请下载以下必需的安全更新，然后将它们部署到网络中：</span><span class="sxs-lookup"><span data-stu-id="696ae-161">To boost your vulnerability assessment detection rates, download the following mandatory security updates and deploy them in your network:</span></span>
>- <span data-ttu-id="696ae-162">19H1 客户| [KB 4512941](https://support.microsoft.com/help/4512941/windows-10-update-kb4512941)</span><span class="sxs-lookup"><span data-stu-id="696ae-162">19H1 customers | [KB 4512941](https://support.microsoft.com/help/4512941/windows-10-update-kb4512941)</span></span>
>- <span data-ttu-id="696ae-163">RS5 客户| [KB 4516077](https://support.microsoft.com/help/4516077/windows-10-update-kb4516077)</span><span class="sxs-lookup"><span data-stu-id="696ae-163">RS5 customers | [KB 4516077](https://support.microsoft.com/help/4516077/windows-10-update-kb4516077)</span></span>
>- <span data-ttu-id="696ae-164">RS4 客户| [KB 4516045](https://support.microsoft.com/help/4516045/windows-10-update-kb4516045)</span><span class="sxs-lookup"><span data-stu-id="696ae-164">RS4 customers | [KB 4516045](https://support.microsoft.com/help/4516045/windows-10-update-kb4516045)</span></span>
>- <span data-ttu-id="696ae-165">RS3 客户| [KB 4516071](https://support.microsoft.com/help/4516071/windows-10-update-kb4516071)</span><span class="sxs-lookup"><span data-stu-id="696ae-165">RS3 customers | [KB 4516071](https://support.microsoft.com/help/4516071/windows-10-update-kb4516071)</span></span>
>
><span data-ttu-id="696ae-166">若要下载安全更新，请执行以下措施：</span><span class="sxs-lookup"><span data-stu-id="696ae-166">To download the security updates:</span></span>
>1. <span data-ttu-id="696ae-167">转到 [Microsoft 更新目录](https://www.catalog.update.microsoft.com/home.aspx)。</span><span class="sxs-lookup"><span data-stu-id="696ae-167">Go to [Microsoft Update Catalog](https://www.catalog.update.microsoft.com/home.aspx).</span></span>
>2. <span data-ttu-id="696ae-168">需要下载的安全更新 KB 编号的键，然后单击"搜索 **"。**</span><span class="sxs-lookup"><span data-stu-id="696ae-168">Key-in the security update KB number that you need to download, then click **Search**.</span></span>  

## <a name="related-topics"></a><span data-ttu-id="696ae-169">相关主题</span><span class="sxs-lookup"><span data-stu-id="696ae-169">Related topics</span></span>

- [<span data-ttu-id="696ae-170">威胁和漏洞管理概述</span><span class="sxs-lookup"><span data-stu-id="696ae-170">Threat and vulnerability management overview</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="696ae-171">仪表板</span><span class="sxs-lookup"><span data-stu-id="696ae-171">Dashboard</span></span>](tvm-dashboard-insights.md)
- [<span data-ttu-id="696ae-172">曝光分数</span><span class="sxs-lookup"><span data-stu-id="696ae-172">Exposure score</span></span>](tvm-exposure-score.md)
- [<span data-ttu-id="696ae-173">安全性建议</span><span class="sxs-lookup"><span data-stu-id="696ae-173">Security recommendations</span></span>](tvm-security-recommendation.md)
