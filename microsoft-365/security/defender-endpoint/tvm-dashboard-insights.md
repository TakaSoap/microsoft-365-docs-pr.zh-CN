---
title: 仪表板见解 - 威胁和漏洞管理
description: 威胁和漏洞管理仪表板可帮助 SecOps 和安全管理员应对网络安全威胁，并构建其组织的安全恢复能力。
keywords: mdatp-tvm， mdatp-tvm 仪表板， 威胁 & 漏洞管理， 威胁和漏洞管理， 基于风险的威胁 & 漏洞管理， 安全配置， Microsoft 设备安全分数， 曝光分数
search.appverid: met150
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 35dd300d828bfa48ad753d7c65f36b2555cf4f60
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/01/2021
ms.locfileid: "51500177"
---
# <a name="dashboard-insights---threat-and-vulnerability-management"></a><span data-ttu-id="65d0d-104">仪表板见解 - 威胁和漏洞管理</span><span class="sxs-lookup"><span data-stu-id="65d0d-104">Dashboard insights - threat and vulnerability management</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="65d0d-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="65d0d-105">**Applies to:**</span></span>

- [<span data-ttu-id="65d0d-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="65d0d-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="65d0d-107">威胁和漏洞管理</span><span class="sxs-lookup"><span data-stu-id="65d0d-107">Threat and vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="65d0d-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="65d0d-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="65d0d-109">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="65d0d-109">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="65d0d-110">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="65d0d-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

<span data-ttu-id="65d0d-111">威胁和漏洞管理是 Defender for Endpoint 的一个组件，可为安全管理员和安全运营团队提供独特的价值，包括：</span><span class="sxs-lookup"><span data-stu-id="65d0d-111">Threat and vulnerability management is a component of Defender for Endpoint, and provides both security administrators and security operations teams with unique value, including:</span></span>


- <span data-ttu-id="65d0d-112">与终结点漏洞相关的实时终结点检测和响应（EDR）见解</span><span class="sxs-lookup"><span data-stu-id="65d0d-112">Real-time endpoint detection and response (EDR) insights correlated with endpoint vulnerabilities</span></span>
- <span data-ttu-id="65d0d-113">事件调查期间有价值的设备漏洞上下文</span><span class="sxs-lookup"><span data-stu-id="65d0d-113">Invaluable device vulnerability context during incident investigations</span></span>
- <span data-ttu-id="65d0d-114">通过 Microsoft Intune 和 Microsoft Endpoint Configuration Manager 的内置修正过程</span><span class="sxs-lookup"><span data-stu-id="65d0d-114">Built-in remediation processes through Microsoft Intune and Microsoft Endpoint Configuration Manager</span></span>  
  
<span data-ttu-id="65d0d-115">可以使用 [Microsoft Defender](https://securitycenter.windows.com/) 安全中心的威胁和漏洞管理功能：</span><span class="sxs-lookup"><span data-stu-id="65d0d-115">You can use the threat and vulnerability management capability in [Microsoft Defender Security Center](https://securitycenter.windows.com/) to:</span></span>

- <span data-ttu-id="65d0d-116">查看设备的曝光分数和 Microsoft 安全分数，以及顶级安全建议、软件漏洞、修正活动和公开的设备</span><span class="sxs-lookup"><span data-stu-id="65d0d-116">View you exposure score and Microsoft Secure Score for Devices, along with top security recommendations, software vulnerability, remediation activities, and exposed devices</span></span>
- <span data-ttu-id="65d0d-117">将 EDR 见解与终结点漏洞关联并处理它们</span><span class="sxs-lookup"><span data-stu-id="65d0d-117">Correlate EDR insights with endpoint vulnerabilities and process them</span></span>
- <span data-ttu-id="65d0d-118">选择修正选项进行会审并跟踪修正任务</span><span class="sxs-lookup"><span data-stu-id="65d0d-118">Select remediation options to triage and track the remediation tasks</span></span>
- <span data-ttu-id="65d0d-119">选择例外选项并跟踪活动异常</span><span class="sxs-lookup"><span data-stu-id="65d0d-119">Select exception options and track active exceptions</span></span>

> [!NOTE]
> <span data-ttu-id="65d0d-120">对于反映组织的威胁和漏洞管理曝光分数和 Microsoft 设备安全分数的数据，未考虑过去 30 天内未处于活动状态的设备。</span><span class="sxs-lookup"><span data-stu-id="65d0d-120">Devices that are not active in the last 30 days are not factored in on the data that reflects your organization's threat and vulnerability management exposure score and Microsoft Secure Score for Devices.</span></span>

<span data-ttu-id="65d0d-121">观看此视频，快速概览威胁和漏洞管理仪表板中是什么内容。</span><span class="sxs-lookup"><span data-stu-id="65d0d-121">Watch this video for a quick overview of what is in the threat and vulnerability management dashboard.</span></span>

>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4r1nv]

## <a name="threat-and-vulnerability-management-dashboard"></a><span data-ttu-id="65d0d-122">威胁和漏洞管理仪表板</span><span class="sxs-lookup"><span data-stu-id="65d0d-122">Threat and vulnerability management dashboard</span></span>

 ![适用于终结点的 Microsoft Defender 门户](images/tvm-dashboard-devices.png)

<span data-ttu-id="65d0d-124">区域</span><span class="sxs-lookup"><span data-stu-id="65d0d-124">Area</span></span> | <span data-ttu-id="65d0d-125">说明</span><span class="sxs-lookup"><span data-stu-id="65d0d-125">Description</span></span>
:---|:---
<span data-ttu-id="65d0d-126">**所选设备组 (#/#)**</span><span class="sxs-lookup"><span data-stu-id="65d0d-126">**Selected device groups (#/#)**</span></span>   | <span data-ttu-id="65d0d-127">按设备组筛选你想要在仪表板和卡片中查看的威胁和漏洞管理数据。</span><span class="sxs-lookup"><span data-stu-id="65d0d-127">Filter the threat and vulnerability management data you want to see in the dashboard and cards by device groups.</span></span> <span data-ttu-id="65d0d-128">在筛选器中选择的内容将应用于整个威胁和漏洞管理页面。</span><span class="sxs-lookup"><span data-stu-id="65d0d-128">What you select in the filter applies throughout the threat and vulnerability management pages.</span></span>
[<span data-ttu-id="65d0d-129">**风险评分**</span><span class="sxs-lookup"><span data-stu-id="65d0d-129">**Exposure score**</span></span>](tvm-exposure-score.md)   | <span data-ttu-id="65d0d-130">查看组织设备面临的威胁和漏洞的当前状态。</span><span class="sxs-lookup"><span data-stu-id="65d0d-130">See the current state of your organization's device exposure to threats and vulnerabilities.</span></span> <span data-ttu-id="65d0d-131">有几个因素会影响组织的曝光评分：在设备中发现的缺点、设备被泄露的可能性、设备对组织的价值，以及设备发现的相关警报。</span><span class="sxs-lookup"><span data-stu-id="65d0d-131">Several factors affect your organization's exposure score: weaknesses discovered in your devices, likelihood of your devices to be breached, value of the devices to your organization, and relevant alerts discovered with your devices.</span></span> <span data-ttu-id="65d0d-132">目标是降低组织的曝光分数，以更安全。</span><span class="sxs-lookup"><span data-stu-id="65d0d-132">The goal is to lower the exposure score of your organization to be more secure.</span></span> <span data-ttu-id="65d0d-133">若要降低分数，需要修正安全建议中列出的相关安全配置问题。</span><span class="sxs-lookup"><span data-stu-id="65d0d-133">To reduce the score, you need to remediate the related security configuration issues listed in the security recommendations.</span></span>
[<span data-ttu-id="65d0d-134">**设备的 Microsoft 安全功能分数**</span><span class="sxs-lookup"><span data-stu-id="65d0d-134">**Microsoft Secure Score for Devices**</span></span>](tvm-microsoft-secure-score-devices.md) | <span data-ttu-id="65d0d-135">查看组织的操作系统、应用程序、网络、帐户和安全控制的安全状态。</span><span class="sxs-lookup"><span data-stu-id="65d0d-135">See the security posture of the operating system, applications, network, accounts, and security controls of your organization.</span></span> <span data-ttu-id="65d0d-136">目标是修正相关的安全配置问题，以增加设备的分数。</span><span class="sxs-lookup"><span data-stu-id="65d0d-136">The goal is to remediate the related security configuration issues to increase your score for devices.</span></span> <span data-ttu-id="65d0d-137">选择条形将你访问" **安全建议"** 页。</span><span class="sxs-lookup"><span data-stu-id="65d0d-137">Selecting the bars will take you to the **Security recommendation** page.</span></span>
<span data-ttu-id="65d0d-138">**设备曝光分布**</span><span class="sxs-lookup"><span data-stu-id="65d0d-138">**Device exposure distribution**</span></span> | <span data-ttu-id="65d0d-139">查看基于其曝光级别公开的设备数。</span><span class="sxs-lookup"><span data-stu-id="65d0d-139">See how many devices are exposed based on their exposure level.</span></span> <span data-ttu-id="65d0d-140">选择圆环图中的某个部分，以转到"设备"列表页并查看受影响的设备名称、曝光级别、风险级别和其他详细信息，如域、操作系统平台、其运行状况、上次查看时间及其标记。</span><span class="sxs-lookup"><span data-stu-id="65d0d-140">Select a section in the doughnut chart to go to the **Devices list** page and view the affected device names, exposure level, risk level, and other details such as domain, operating system platform, its health state, when it was last seen, and its tags.</span></span>
<span data-ttu-id="65d0d-141">**首要安全建议**</span><span class="sxs-lookup"><span data-stu-id="65d0d-141">**Top security recommendations**</span></span> | <span data-ttu-id="65d0d-142">请参阅已排序的安全建议，这些建议根据组织的风险暴露及其需要的紧急程度进行排序和确定优先级。</span><span class="sxs-lookup"><span data-stu-id="65d0d-142">See the collated security recommendations that are sorted and prioritized based on your organization's risk exposure and the urgency that it requires.</span></span> <span data-ttu-id="65d0d-143">选择 **"显示** 更多"以查看列表中的其余安全建议。</span><span class="sxs-lookup"><span data-stu-id="65d0d-143">Select **Show more** to see the rest of the security recommendations in the list.</span></span> <span data-ttu-id="65d0d-144">对于 **具有例外** 的建议列表，选择"显示例外"。</span><span class="sxs-lookup"><span data-stu-id="65d0d-144">Select **Show exceptions** for the list of recommendations that have an exception.</span></span>
<span data-ttu-id="65d0d-145">**最易受攻击的软件**</span><span class="sxs-lookup"><span data-stu-id="65d0d-145">**Top vulnerable software**</span></span> | <span data-ttu-id="65d0d-146">使用在网络设备上安装的易受攻击的软件的堆栈排名列表，以及这些软件如何影响组织曝光分数，实时了解组织的软件清单。</span><span class="sxs-lookup"><span data-stu-id="65d0d-146">Get real-time visibility into your organization's software inventory with a stack-ranked list of vulnerable software installed on your network's devices and how they impact your organizational exposure score.</span></span> <span data-ttu-id="65d0d-147">选择一个项目了解详细信息或 **显示详细信息** ，以查看软件清单页中的其余易受 **攻击的软件** 列表。</span><span class="sxs-lookup"><span data-stu-id="65d0d-147">Select an item for details or **Show more** to see the rest of the vulnerable software list in the **Software inventory** page.</span></span>
<span data-ttu-id="65d0d-148">**首要修正活动**</span><span class="sxs-lookup"><span data-stu-id="65d0d-148">**Top remediation activities**</span></span> | <span data-ttu-id="65d0d-149">跟踪根据安全建议生成的修正活动。</span><span class="sxs-lookup"><span data-stu-id="65d0d-149">Track the remediation activities generated from the security recommendations.</span></span> <span data-ttu-id="65d0d-150">可以选择列表中的每个项目以查看"修正"页中的详细信息，或选择"显示更多"以查看其余修正活动和活动异常。</span><span class="sxs-lookup"><span data-stu-id="65d0d-150">You can select each item on the list to see the details in the **Remediation** page or select **Show more** to view the rest of the remediation activities, and active exceptions.</span></span>
<span data-ttu-id="65d0d-151">**最公开的设备**</span><span class="sxs-lookup"><span data-stu-id="65d0d-151">**Top exposed devices**</span></span> | <span data-ttu-id="65d0d-152">查看公开的设备名称及其曝光级别。</span><span class="sxs-lookup"><span data-stu-id="65d0d-152">View exposed device names and their exposure level.</span></span> <span data-ttu-id="65d0d-153">从列表中选择设备名称以转到设备页面，可在其中查看警报、风险、事件、安全建议、已安装的软件以及发现的与公开的设备关联的漏洞。</span><span class="sxs-lookup"><span data-stu-id="65d0d-153">Select a device name from the list to go to the device page where you can view the alerts, risks, incidents, security recommendations, installed software, and discovered vulnerabilities associated with the exposed devices.</span></span> <span data-ttu-id="65d0d-154">选择 **"显示** 更多"以查看公开设备列表的其余部分。</span><span class="sxs-lookup"><span data-stu-id="65d0d-154">Select **Show more** to see the rest of the exposed devices list.</span></span> <span data-ttu-id="65d0d-155">从设备列表中，你可以管理标记、启动自动调查、启动实时响应会话、收集调查包、运行防病毒扫描、限制应用执行和隔离设备。</span><span class="sxs-lookup"><span data-stu-id="65d0d-155">From the devices list, you can manage tags, initiate automated investigations, initiate a live response session, collect an investigation package, run antivirus scan, restrict app execution, and isolate device.</span></span>

<span data-ttu-id="65d0d-156">有关整个门户中使用的图标详细信息，请参阅 [适用于终结点的 Microsoft Defender 图标](portal-overview.md#microsoft-defender-for-endpoint-icons)。</span><span class="sxs-lookup"><span data-stu-id="65d0d-156">For more information on the icons used throughout the portal, see [Microsoft Defender for Endpoint icons](portal-overview.md#microsoft-defender-for-endpoint-icons).</span></span>


## <a name="related-topics"></a><span data-ttu-id="65d0d-157">相关主题</span><span class="sxs-lookup"><span data-stu-id="65d0d-157">Related topics</span></span>

- [<span data-ttu-id="65d0d-158">威胁和漏洞管理概述</span><span class="sxs-lookup"><span data-stu-id="65d0d-158">Threat and vulnerability management overview</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="65d0d-159">风险评分</span><span class="sxs-lookup"><span data-stu-id="65d0d-159">Exposure score</span></span>](tvm-exposure-score.md)
- [<span data-ttu-id="65d0d-160">设备的 Microsoft 安全功能分数</span><span class="sxs-lookup"><span data-stu-id="65d0d-160">Microsoft Secure Score for Devices</span></span>](tvm-microsoft-secure-score-devices.md)
- [<span data-ttu-id="65d0d-161">安全性建议</span><span class="sxs-lookup"><span data-stu-id="65d0d-161">Security recommendations</span></span>](tvm-security-recommendation.md)
- [<span data-ttu-id="65d0d-162">软件库存</span><span class="sxs-lookup"><span data-stu-id="65d0d-162">Software inventory</span></span>](tvm-software-inventory.md)
- [<span data-ttu-id="65d0d-163">活动日程表</span><span class="sxs-lookup"><span data-stu-id="65d0d-163">Event timeline</span></span>](threat-and-vuln-mgt-event-timeline.md)

