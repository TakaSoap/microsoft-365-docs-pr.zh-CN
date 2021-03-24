---
title: 了解 Microsoft Defender for Endpoint 中的威胁情报概念
description: 为组织创建自定义威胁警报并了解 Microsoft Defender for Endpoint 中威胁智能的概念
keywords: 威胁情报， 警报定义， 泄露指示器， ioc
search.product: eADQiWindows 10XVcnh
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
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: bb82634c8c2ef11131a43e8e479bf88d5626ed03
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51055913"
---
# <a name="understand-threat-intelligence-concepts"></a><span data-ttu-id="1ac77-104">了解威胁情报概念</span><span class="sxs-lookup"><span data-stu-id="1ac77-104">Understand threat intelligence concepts</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="1ac77-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="1ac77-105">**Applies to:**</span></span>
- [<span data-ttu-id="1ac77-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="1ac77-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="1ac77-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1ac77-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)



><span data-ttu-id="1ac77-108">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="1ac77-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="1ac77-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="1ac77-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-threatindicator-abovefoldlink) 

<span data-ttu-id="1ac77-110">高级网络安全攻击由多个复杂的恶意事件、属性和上下文信息组成。</span><span class="sxs-lookup"><span data-stu-id="1ac77-110">Advanced cybersecurity attacks comprise of multiple complex malicious events, attributes, and contextual information.</span></span> <span data-ttu-id="1ac77-111">确定和确定哪些活动符合可疑条件可能是一项极具挑战性的任务。</span><span class="sxs-lookup"><span data-stu-id="1ac77-111">Identifying and deciding which of these activities qualify as suspicious can be a challenging task.</span></span> <span data-ttu-id="1ac77-112">了解特定于你的行业的已知属性和异常活动是了解何时将观察到的行为称为可疑行为的基础。</span><span class="sxs-lookup"><span data-stu-id="1ac77-112">Your knowledge of known attributes and abnormal activities specific to your industry is fundamental in knowing when to call an observed behavior as suspicious.</span></span>

<span data-ttu-id="1ac77-113">借助 Microsoft Defender for Endpoint，你可以创建自定义威胁警报，以帮助跟踪组织中可能的攻击活动。</span><span class="sxs-lookup"><span data-stu-id="1ac77-113">With Microsoft Defender for Endpoint, you can create custom threat alerts that can help you keep track of possible attack activities in your organization.</span></span> <span data-ttu-id="1ac77-114">你可以标记可疑事件以将线索拼接在一起，并可能停止攻击链。</span><span class="sxs-lookup"><span data-stu-id="1ac77-114">You can flag suspicious events to piece together clues and possibly stop an attack chain.</span></span> <span data-ttu-id="1ac77-115">这些自定义威胁警报将仅出现在你的组织中，并标记你设置为跟踪的事件。</span><span class="sxs-lookup"><span data-stu-id="1ac77-115">These custom threat alerts will only appear in your organization and will flag events that you set it to track.</span></span>

<span data-ttu-id="1ac77-116">创建自定义威胁警报之前，必须了解警报定义和泄露指示器背后的概念 (ICS) 它们之间的关系。</span><span class="sxs-lookup"><span data-stu-id="1ac77-116">Before creating custom threat alerts, it's important to know the concepts behind alert definitions and indicators of compromise (IOCs) and the relationship between them.</span></span>

## <a name="alert-definitions"></a><span data-ttu-id="1ac77-117">警报定义</span><span class="sxs-lookup"><span data-stu-id="1ac77-117">Alert definitions</span></span>
<span data-ttu-id="1ac77-118">警报定义是上下文属性，可用于共同识别有关可能的网络安全攻击的早期线索。</span><span class="sxs-lookup"><span data-stu-id="1ac77-118">Alert definitions are contextual attributes that can be used collectively to identify early clues on a possible cybersecurity attack.</span></span> <span data-ttu-id="1ac77-119">这些指示器通常是攻击者为成功实现攻击目标而执行的活动、特征和操作的组合。</span><span class="sxs-lookup"><span data-stu-id="1ac77-119">These indicators are typically a combination of activities, characteristics, and actions taken by an attacker to successfully achieve the objective of an attack.</span></span> <span data-ttu-id="1ac77-120">监视这些属性组合对于在达到攻击者的目标之前获取攻击点并可能干扰事件链至关重要。</span><span class="sxs-lookup"><span data-stu-id="1ac77-120">Monitoring these combinations of attributes is critical in gaining a vantage point against attacks and possibly interfering with the chain of events before an attacker's objective is reached.</span></span>

## <a name="indicators-of-compromise-ioc"></a><span data-ttu-id="1ac77-121">IOC (泄露) </span><span class="sxs-lookup"><span data-stu-id="1ac77-121">Indicators of compromise (IOC)</span></span>
<span data-ttu-id="1ac77-122">IIC 是单独已知的恶意事件，指示网络或设备已被破坏。</span><span class="sxs-lookup"><span data-stu-id="1ac77-122">IOCs are individually-known malicious events that indicate that a network or device has already been breached.</span></span> <span data-ttu-id="1ac77-123">与警报定义不同，这些指示器被视为泄露的证据。</span><span class="sxs-lookup"><span data-stu-id="1ac77-123">Unlike alert definitions, these indicators are considered as evidence of a breach.</span></span> <span data-ttu-id="1ac77-124">通常，在攻击已执行且达到目标（如外向）之后，它们经常看到。</span><span class="sxs-lookup"><span data-stu-id="1ac77-124">They are often seen after an attack has already been carried out and the objective has been reached, such as exfiltration.</span></span> <span data-ttu-id="1ac77-125">在取证调查期间，跟踪 IIC 也很重要。</span><span class="sxs-lookup"><span data-stu-id="1ac77-125">Keeping track of IOCs is also important during forensic investigations.</span></span> <span data-ttu-id="1ac77-126">尽管它可能不会提供干预攻击链的能力，但是收集这些指示器对于为可能的未来攻击创建更好的防护非常有用。</span><span class="sxs-lookup"><span data-stu-id="1ac77-126">Although it might not provide the ability to intervene with an attack chain, gathering these indicators can be useful in creating better defenses for possible future attacks.</span></span>

## <a name="relationship-between-alert-definitions-and-iocs"></a><span data-ttu-id="1ac77-127">警报定义和 ICS 之间的关系</span><span class="sxs-lookup"><span data-stu-id="1ac77-127">Relationship between alert definitions and IOCs</span></span>
<span data-ttu-id="1ac77-128">在 Microsoft Defender for Endpoint 的上下文中，警报定义是 IOC 的容器并定义警报，包括在进行特定 IOC 匹配时引发元数据。</span><span class="sxs-lookup"><span data-stu-id="1ac77-128">In the context of Microsoft Defender for Endpoint, alert definitions are containers for IOCs and defines the alert, including the metadata that is raised in case of a specific IOC match.</span></span> <span data-ttu-id="1ac77-129">各种元数据作为警报定义的一部分提供。</span><span class="sxs-lookup"><span data-stu-id="1ac77-129">Various metadata is provided as part of the alert definitions.</span></span> <span data-ttu-id="1ac77-130">诸如攻击的警报定义名称、严重性和说明等元数据以及其他选项一起提供。</span><span class="sxs-lookup"><span data-stu-id="1ac77-130">Metadata such as alert definition name of attack, severity, and description is provided along with other options.</span></span>

<span data-ttu-id="1ac77-131">每个 IOC 都基于其类型和值及其操作定义具体的检测逻辑，确定如何匹配它。</span><span class="sxs-lookup"><span data-stu-id="1ac77-131">Each IOC defines the concrete detection logic based on its type and value as well as its action, which determines how it is matched.</span></span> <span data-ttu-id="1ac77-132">它绑定到特定警报定义，该定义定义如何在 Microsoft Defender for Endpoint 控制台上将检测显示为警报。</span><span class="sxs-lookup"><span data-stu-id="1ac77-132">It is bound to a specific alert definition that defines how a detection is displayed as an alert on the Microsoft Defender for Endpoint console.</span></span>

<span data-ttu-id="1ac77-133">下面是 IOC 的示例：</span><span class="sxs-lookup"><span data-stu-id="1ac77-133">Here is an example of an IOC:</span></span>
- <span data-ttu-id="1ac77-134">类型：Sha1</span><span class="sxs-lookup"><span data-stu-id="1ac77-134">Type: Sha1</span></span>
- <span data-ttu-id="1ac77-135">值：92cfceb39d57d914ed8b14d0e37643de0797ae56</span><span class="sxs-lookup"><span data-stu-id="1ac77-135">Value:  92cfceb39d57d914ed8b14d0e37643de0797ae56</span></span>
- <span data-ttu-id="1ac77-136">操作：等于</span><span class="sxs-lookup"><span data-stu-id="1ac77-136">Action: Equals</span></span>

<span data-ttu-id="1ac77-137">IIC 与警报定义具有多对一关系，因此警报定义可以具有许多与其对应的 IPC。</span><span class="sxs-lookup"><span data-stu-id="1ac77-137">IOCs have a many-to-one relationship with alert definitions such that an alert definition can have many IOCs that correspond to it.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="1ac77-138">本节内容</span><span class="sxs-lookup"><span data-stu-id="1ac77-138">In this section</span></span>

<span data-ttu-id="1ac77-139">主题</span><span class="sxs-lookup"><span data-stu-id="1ac77-139">Topic</span></span> | <span data-ttu-id="1ac77-140">说明</span><span class="sxs-lookup"><span data-stu-id="1ac77-140">Description</span></span>
:---|:---
[<span data-ttu-id="1ac77-141">将检测拉取到 SIEM 工具</span><span class="sxs-lookup"><span data-stu-id="1ac77-141">Pull detections to your SIEM tools</span></span>](configure-siem.md)| <span data-ttu-id="1ac77-142">了解拉取检测的不同方法。</span><span class="sxs-lookup"><span data-stu-id="1ac77-142">Learn about different ways to pull detections.</span></span>
[<span data-ttu-id="1ac77-143">在 Microsoft Defender for Endpoint 中启用 SIEM 集成</span><span class="sxs-lookup"><span data-stu-id="1ac77-143">Enable SIEM integration in Microsoft Defender for Endpoint</span></span>](enable-siem-integration.md)| <span data-ttu-id="1ac77-144">了解如何在门户的"设置"页中启用SIEM 集成功能，以便可以使用和生成配置支持的 SIEM 工具所需的信息。</span><span class="sxs-lookup"><span data-stu-id="1ac77-144">Learn about enabling the SIEM integration feature in the **Settings** page in the portal so that you can use and generate the required information to configure supported SIEM tools.</span></span>
[<span data-ttu-id="1ac77-145">配置 Splunk 以拉取 Microsoft Defender 进行终结点检测</span><span class="sxs-lookup"><span data-stu-id="1ac77-145">Configure Splunk to pull Microsoft Defender for Endpoint detections</span></span>](configure-siem.md)| <span data-ttu-id="1ac77-146">了解如何安装 REST API 模块化输入应用和其他配置设置，以使 Splunk 能够拉取 Microsoft Defender for Endpoint 检测。</span><span class="sxs-lookup"><span data-stu-id="1ac77-146">Learn about installing the REST API Modular Input App and other configuration settings to enable Splunk to pull Microsoft Defender for Endpoint detections.</span></span>
[<span data-ttu-id="1ac77-147">配置 HP ArcSight 以拉取 Microsoft Defender 进行终结点检测</span><span class="sxs-lookup"><span data-stu-id="1ac77-147">Configure HP ArcSight to pull Microsoft Defender for Endpoint detections</span></span>](configure-arcsight.md)| <span data-ttu-id="1ac77-148">了解如何安装 HP ArcSight REST FlexConnector 程序包以及配置 ArcSight 以拉取 Microsoft Defender 进行终结点检测所需的文件。</span><span class="sxs-lookup"><span data-stu-id="1ac77-148">Learn about installing the HP ArcSight REST FlexConnector package and the files you need to configure ArcSight to pull Microsoft Defender for Endpoint detections.</span></span>
[<span data-ttu-id="1ac77-149">适用于终结点检测字段的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="1ac77-149">Microsoft Defender for Endpoint Detection fields</span></span>](api-portal-mapping.md) | <span data-ttu-id="1ac77-150">了解哪些数据字段作为警报 API 的一部分公开，以及如何映射到 Microsoft Defender 安全中心。</span><span class="sxs-lookup"><span data-stu-id="1ac77-150">Understand what data fields are exposed as part of the alerts API and how they map to Microsoft Defender Security Center.</span></span>
[<span data-ttu-id="1ac77-151">使用 REST API 拉取 Microsoft Defender 的终结点检测</span><span class="sxs-lookup"><span data-stu-id="1ac77-151">Pull Microsoft Defender for Endpoint detections using REST API</span></span>](pull-alerts-using-rest-api.md) | <span data-ttu-id="1ac77-152">使用客户端凭据 OAuth 2.0 流，使用 REST API 从 Microsoft Defender for Endpoint 拉取检测。</span><span class="sxs-lookup"><span data-stu-id="1ac77-152">Use the Client credentials OAuth 2.0 flow to pull detections from Microsoft Defender for Endpoint using REST API.</span></span>
[<span data-ttu-id="1ac77-153">SIEM 工具集成问题疑难解答</span><span class="sxs-lookup"><span data-stu-id="1ac77-153">Troubleshoot SIEM tool integration issues</span></span>](troubleshoot-siem.md) | <span data-ttu-id="1ac77-154">解决在使用 SIEM 集成功能时可能遇到的问题。</span><span class="sxs-lookup"><span data-stu-id="1ac77-154">Address issues you might encounter when using the SIEM integration feature.</span></span>



## <a name="related-topics"></a><span data-ttu-id="1ac77-155">相关主题</span><span class="sxs-lookup"><span data-stu-id="1ac77-155">Related topics</span></span>
- [<span data-ttu-id="1ac77-156">管理指示器</span><span class="sxs-lookup"><span data-stu-id="1ac77-156">Manage indicators</span></span>](manage-indicators.md)
