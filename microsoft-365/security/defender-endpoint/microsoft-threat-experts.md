---
title: Microsoft 威胁专家
ms.reviewer: ''
description: Microsoft 威胁专家为 Microsoft Defender for Endpoint 提供了另一层专业技能。
keywords: 托管威胁搜寻服务， 托管威胁搜寻， 托管检测和响应 (MDR) 服务， MTE， Microsoft 威胁专家， MTE-TAN， 目标攻击通知， 目标攻击通知
search.product: Windows 10
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 4c61fcdfb452fb075498dcc2858bb7a9b4b81a2f
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/24/2021
ms.locfileid: "51165941"
---
# <a name="microsoft-threat-experts"></a><span data-ttu-id="3fdb7-104">Microsoft 威胁专家</span><span class="sxs-lookup"><span data-stu-id="3fdb7-104">Microsoft Threat Experts</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="3fdb7-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="3fdb7-105">**Applies to:**</span></span>
- [<span data-ttu-id="3fdb7-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="3fdb7-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="3fdb7-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3fdb7-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="3fdb7-108">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="3fdb7-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="3fdb7-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="3fdb7-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


<span data-ttu-id="3fdb7-110">Microsoft 威胁专家是一项托管威胁搜寻服务，可为安全操作中心 (SOC) 提供专家级别的监视和分析，以帮助他们确保不会错过独特环境中的关键威胁。</span><span class="sxs-lookup"><span data-stu-id="3fdb7-110">Microsoft Threat Experts is a managed threat hunting service that provides your Security Operation Centers (SOCs) with expert level monitoring and analysis to help them ensure that critical threats in your unique environments don’t get missed.</span></span>
  
<span data-ttu-id="3fdb7-111">此托管威胁搜寻服务通过以下两项功能提供专家驱动的见解和数据：目标攻击通知和按需访问专家。</span><span class="sxs-lookup"><span data-stu-id="3fdb7-111">This managed threat hunting service provides expert-driven insights and data through these two capabilities: targeted attack notification and access to experts on demand.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="3fdb7-112">准备工作</span><span class="sxs-lookup"><span data-stu-id="3fdb7-112">Before you begin</span></span> 
> [!NOTE]
> <span data-ttu-id="3fdb7-113">在应用于托管威胁搜寻服务之前，与 Microsoft 技术服务提供商和帐户团队讨论资格要求。</span><span class="sxs-lookup"><span data-stu-id="3fdb7-113">Discuss the eligibility requirements with your Microsoft Technical Service provider and account team before you apply to the managed threat hunting service.</span></span>

<span data-ttu-id="3fdb7-114">如果你是适用于终结点的 Microsoft Defender 客户，则需要申请 Microsoft **威胁** 专家 - 目标攻击通知，获取有助于识别环境中最关键威胁的特殊见解和分析，以便快速响应它们</span><span class="sxs-lookup"><span data-stu-id="3fdb7-114">If you're a Microsoft Defender for Endpoint customer, you need to apply for **Microsoft Threat Experts - Targeted Attack Notifications** to get special insights and analysis that help identify the most critical threats in your environment so you can respond to them quickly</span></span>

<span data-ttu-id="3fdb7-115">若要注册 Microsoft 威胁专家 - 目标攻击通知权益，请转到 **设置常规** 高级功能 Microsoft 威胁专家  >    >    >  **- 要应用的目标攻击** 通知。</span><span class="sxs-lookup"><span data-stu-id="3fdb7-115">To enroll to Microsoft Threat Experts - Targeted Attack Notifications benefits, go to **Settings** > **General** > **Advanced features** > **Microsoft Threat Experts - Targeted Attack Notifications** to apply.</span></span> <span data-ttu-id="3fdb7-116">接受后，你将受益于定向攻击通知。</span><span class="sxs-lookup"><span data-stu-id="3fdb7-116">Once accepted, you will get the benefits of Targeted Attack Notifications.</span></span>

<span data-ttu-id="3fdb7-117">联系你的帐户团队或 Microsoft 代表，订阅 **Microsoft 威胁** 专家 - 按需专家，以咨询我们的威胁专家，了解组织面临的相关检测和对手。</span><span class="sxs-lookup"><span data-stu-id="3fdb7-117">Contact your account team or Microsoft representative to subscribe to **Microsoft Threat Experts - Experts on Demand** to consult with our threat experts on relevant detections and adversaries that your organization is facing.</span></span>

<span data-ttu-id="3fdb7-118">有关详细信息 [，请参阅配置 Microsoft 威胁专家](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-microsoft-threat-experts#before-you-begin) 功能。</span><span class="sxs-lookup"><span data-stu-id="3fdb7-118">See [Configure Microsoft Threat Experts capabilities](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-microsoft-threat-experts#before-you-begin) for details.</span></span> 

## <a name="microsoft-threat-experts---targeted-attack-notification"></a><span data-ttu-id="3fdb7-119">Microsoft 威胁专家 - 目标攻击通知</span><span class="sxs-lookup"><span data-stu-id="3fdb7-119">Microsoft Threat Experts - Targeted attack notification</span></span> 
<span data-ttu-id="3fdb7-120">Microsoft 威胁专家 - 目标攻击通知可主动搜寻网络最重要的威胁，包括人为入侵、动手键盘攻击或高级攻击（如网络威胁）。</span><span class="sxs-lookup"><span data-stu-id="3fdb7-120">Microsoft Threat Experts - Targeted attack notification provides proactive hunting for the most important threats to your network, including human adversary intrusions, hands-on-keyboard attacks, or advanced attacks like cyber-espionage.</span></span> <span data-ttu-id="3fdb7-121">这些通知将显示为新警报。</span><span class="sxs-lookup"><span data-stu-id="3fdb7-121">These notifications shows up as a new alert.</span></span> <span data-ttu-id="3fdb7-122">托管搜寻服务包括：</span><span class="sxs-lookup"><span data-stu-id="3fdb7-122">The managed hunting service includes:</span></span>  
- <span data-ttu-id="3fdb7-123">威胁监视和分析，减少停留时间和业务风险</span><span class="sxs-lookup"><span data-stu-id="3fdb7-123">Threat monitoring and analysis, reducing dwell time and risk to the business</span></span> 
- <span data-ttu-id="3fdb7-124">经过专业训练的人工智能，可发现已知和未知攻击并设置其优先级</span><span class="sxs-lookup"><span data-stu-id="3fdb7-124">Hunter-trained artificial intelligence to discover and prioritize both known and unknown attacks</span></span>  
- <span data-ttu-id="3fdb7-125">识别最重要的风险，帮助 SOC 最大限度地利用时间和精力</span><span class="sxs-lookup"><span data-stu-id="3fdb7-125">Identifying the most important risks, helping SOCs maximize time and energy</span></span> 
- <span data-ttu-id="3fdb7-126">泄露范围和可快速传递的上下文，以实现快速 SOC 响应。</span><span class="sxs-lookup"><span data-stu-id="3fdb7-126">Scope of compromise and as much context as can be quickly delivered to enable fast SOC response.</span></span> 
 
## <a name="microsoft-threat-experts---experts-on-demand"></a><span data-ttu-id="3fdb7-127">Microsoft 威胁专家 - 专家按需</span><span class="sxs-lookup"><span data-stu-id="3fdb7-127">Microsoft Threat Experts - Experts on Demand</span></span>
<span data-ttu-id="3fdb7-128">客户可以直接在 Microsoft Defender 安全中心内与我们的安全专家联系，及时准确地做出响应。</span><span class="sxs-lookup"><span data-stu-id="3fdb7-128">Customers can engage our security experts directly from within Microsoft Defender Security Center for timely and accurate response.</span></span> <span data-ttu-id="3fdb7-129">专家提供所需的见解，以便更好地了解影响组织的复杂威胁，包括警报查询、可能受到威胁的设备、可疑网络连接的根本原因，以及有关正在进行的高级永久性威胁活动的其他威胁情报。</span><span class="sxs-lookup"><span data-stu-id="3fdb7-129">Experts provide insights needed to better understand the complex threats affecting your organization, from alert inquiries, potentially compromised devices, root cause of a suspicious network connection, to additional threat intelligence regarding ongoing advanced persistent threat campaigns.</span></span> <span data-ttu-id="3fdb7-130">使用此功能，你可以：</span><span class="sxs-lookup"><span data-stu-id="3fdb7-130">With this capability, you can:</span></span>
- <span data-ttu-id="3fdb7-131">获取有关警报的其他说明，包括事件的根本原因或范围</span><span class="sxs-lookup"><span data-stu-id="3fdb7-131">Get additional clarification on alerts including root cause or scope of the incident</span></span> 
- <span data-ttu-id="3fdb7-132">在遇到高级攻击者时，清楚了解可疑设备行为和下一步步骤</span><span class="sxs-lookup"><span data-stu-id="3fdb7-132">Gain clarity into suspicious device behavior and next steps if faced with an advanced attacker</span></span>  
- <span data-ttu-id="3fdb7-133">确定威胁参与者、活动或新兴攻击者技术的风险和保护</span><span class="sxs-lookup"><span data-stu-id="3fdb7-133">Determine risk and protection regarding threat actors, campaigns, or emerging attacker techniques</span></span> 

<span data-ttu-id="3fdb7-134">门户中的 **多个** 位置提供了"咨询威胁专家"选项，以便你可以与调查方面的专家互动：</span><span class="sxs-lookup"><span data-stu-id="3fdb7-134">The option to **Consult a threat expert** is available in several places in the portal so you can engage with experts in the context of your investigation:</span></span>

- <span data-ttu-id="3fdb7-135"><i>**"帮助和支持"菜单**</i></span><span class="sxs-lookup"><span data-stu-id="3fdb7-135"><i>**Help and support menu**</i></span></span><BR>
<span data-ttu-id="3fdb7-136">![MTE-EOD 菜单选项的屏幕截图](images/mte-eod-menu.png)</span><span class="sxs-lookup"><span data-stu-id="3fdb7-136">![Screenshot of MTE-EOD menu option](images/mte-eod-menu.png)</span></span>

- <span data-ttu-id="3fdb7-137"><i>**设备页面操作菜单**</i></span><span class="sxs-lookup"><span data-stu-id="3fdb7-137"><i>**Device page actions menu**</i></span></span><BR>
<span data-ttu-id="3fdb7-138">![MTE-EOD 设备页面操作菜单选项的屏幕截图](images/mte-eod-machines.png)</span><span class="sxs-lookup"><span data-stu-id="3fdb7-138">![Screenshot of MTE-EOD device page action menu option](images/mte-eod-machines.png)</span></span>

- <span data-ttu-id="3fdb7-139"><i>**警报页面操作菜单**</i></span><span class="sxs-lookup"><span data-stu-id="3fdb7-139"><i>**Alerts page actions menu**</i></span></span><BR>
<span data-ttu-id="3fdb7-140">![MTE-EOD 警报页面操作菜单选项的屏幕截图](images/mte-eod-alerts.png)</span><span class="sxs-lookup"><span data-stu-id="3fdb7-140">![Screenshot of MTE-EOD alert page action menu option](images/mte-eod-alerts.png)</span></span>

- <span data-ttu-id="3fdb7-141"><i>**文件页操作菜单**</i></span><span class="sxs-lookup"><span data-stu-id="3fdb7-141"><i>**File page actions menu**</i></span></span><BR>
<span data-ttu-id="3fdb7-142">![MTE-EOD 文件页面操作菜单选项的屏幕截图](images/mte-eod-file.png)</span><span class="sxs-lookup"><span data-stu-id="3fdb7-142">![Screenshot of MTE-EOD file page action menu option](images/mte-eod-file.png)</span></span>

> [!NOTE]
> <span data-ttu-id="3fdb7-143">如果要通过 Microsoft 服务中心跟踪专家按需案例的状态，请联系你的技术客户经理。</span><span class="sxs-lookup"><span data-stu-id="3fdb7-143">If you would like to track the status of your Experts on Demand cases through Microsoft Services Hub, reach out to your Technical Account Manager.</span></span> 

<span data-ttu-id="3fdb7-144">观看此视频，快速概览 Microsoft 服务中心。</span><span class="sxs-lookup"><span data-stu-id="3fdb7-144">Watch this video for a quick overview of the Microsoft Services Hub.</span></span>

>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4pk9f] 

   
## <a name="related-topic"></a><span data-ttu-id="3fdb7-145">相关主题</span><span class="sxs-lookup"><span data-stu-id="3fdb7-145">Related topic</span></span>
- [<span data-ttu-id="3fdb7-146">配置 Microsoft 威胁专家功能</span><span class="sxs-lookup"><span data-stu-id="3fdb7-146">Configure Microsoft Threat Experts capabilities</span></span>](configure-microsoft-threat-experts.md)
