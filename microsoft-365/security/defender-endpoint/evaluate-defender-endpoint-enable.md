---
title: 适用于终结点的试点 Defender 评估
description: 启用你的Microsoft 365 Defender试验实验室或试验环境。
keywords: Microsoft 365 Defender试用版， 试用 Microsoft 365 Defender， 评估 Microsoft 365 Defender， Microsoft 365 Defender 评估实验室， Microsoft 365 Defender 试点， 网络安全， 高级永久性威胁， 企业安全， 设备， 设备， 标识， 用户， 数据， 应用程序， 事件， 自动调查和修正， 高级搜寻
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: v-jweston
author: jweston-1
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 4345ac0a2758e87160be83c6abd96cdbaa6822dc
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/15/2021
ms.locfileid: "53457657"
---
# <a name="pilot-mde-evaluation"></a><span data-ttu-id="18956-104">试点 MDE 评估</span><span class="sxs-lookup"><span data-stu-id="18956-104">Pilot MDE Evaluation</span></span>

>[!NOTE]
><span data-ttu-id="18956-105">为了引导您完成典型部署，此方案将仅涉及 Microsoft Endpoint Configuration Manager。</span><span class="sxs-lookup"><span data-stu-id="18956-105">For the purpose of guiding you through a typical deployment, this scenario will only cover the use of Microsoft Endpoint Configuration Manager.</span></span> <span data-ttu-id="18956-106">Defender for Endpoint 支持使用其他载入工具，但不在部署指南中介绍这些方案。</span><span class="sxs-lookup"><span data-stu-id="18956-106">Defender for Endpoint supports the use of other onboarding tools but won't cover those scenarios in the deployment guide.</span></span> <span data-ttu-id="18956-107">有关详细信息，请参阅 [将设备载入到 Microsoft Defender for Endpoint](onboard-configure.md)。</span><span class="sxs-lookup"><span data-stu-id="18956-107">For more information, see [Onboard devices to Microsoft Defender for Endpoint](onboard-configure.md).</span></span>

## <a name="step-1-check-license-state"></a><span data-ttu-id="18956-108">步骤 1.</span><span class="sxs-lookup"><span data-stu-id="18956-108">Step 1.</span></span> <span data-ttu-id="18956-109">检查许可证状态</span><span class="sxs-lookup"><span data-stu-id="18956-109">Check license state</span></span>

<span data-ttu-id="18956-110">可通过管理中心或管理门户检查许可证状态及其是否Microsoft Azure **设置**。</span><span class="sxs-lookup"><span data-stu-id="18956-110">Checking for the license state and whether it got properly provisioned, can be done through the admin center or through the **Microsoft Azure portal**.</span></span>

1. <span data-ttu-id="18956-111">若要查看许可证，请转到 Microsoft Azure **门户** 并导航到"Microsoft Azure [门户许可证"部分](https://portal.azure.com/#blade/Microsoft_AAD_IAM/LicensesMenuBlade/Products)。</span><span class="sxs-lookup"><span data-stu-id="18956-111">To view your licenses, go to the **Microsoft Azure portal** and navigate to the [Microsoft Azure portal license section](https://portal.azure.com/#blade/Microsoft_AAD_IAM/LicensesMenuBlade/Products).</span></span>

   ![Azure 许可页面的图像](images/atp-licensing-azure-portal.png)

1. <span data-ttu-id="18956-113">或者，在管理中心中，导航到"**帐单**  >  **""订阅"。**</span><span class="sxs-lookup"><span data-stu-id="18956-113">Alternately, in the admin center, navigate to **Billing** > **Subscriptions**.</span></span>

    <span data-ttu-id="18956-114">在屏幕上，你将看到所有预配的许可证及其当前 **状态**。</span><span class="sxs-lookup"><span data-stu-id="18956-114">On the screen, you'll see all the provisioned licenses and their current **Status**.</span></span>

    ![帐单许可证的图像](images/atp-billing-subscriptions.png)

## <a name="step-2-onboard-endpoints-using-any-of-the-supported-management-tools"></a><span data-ttu-id="18956-116">步骤 2.</span><span class="sxs-lookup"><span data-stu-id="18956-116">Step 2.</span></span> <span data-ttu-id="18956-117">使用任何受支持的管理工具载入终结点</span><span class="sxs-lookup"><span data-stu-id="18956-117">Onboard endpoints using any of the supported management tools</span></span>

<span data-ttu-id="18956-118">规划 [部署](deployment-strategy.md) 主题概述了部署 Defender for Endpoint 所需的常规步骤。</span><span class="sxs-lookup"><span data-stu-id="18956-118">The [Plan deployment](deployment-strategy.md) topic outlines the general steps you need to take to deploy Defender for Endpoint.</span></span>  

<span data-ttu-id="18956-119">观看此视频，快速概览载入过程并了解可用的工具和方法。</span><span class="sxs-lookup"><span data-stu-id="18956-119">Watch this video for a quick overview of the onboarding process and learn about the available tools and methods.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4bGqr]

<span data-ttu-id="18956-120">确定体系结构后，需要决定使用哪种部署方法。</span><span class="sxs-lookup"><span data-stu-id="18956-120">After identifying your architecture, you'll need to decide which deployment method to use.</span></span> <span data-ttu-id="18956-121">你选择的部署工具会影响将终结点载入到服务中。</span><span class="sxs-lookup"><span data-stu-id="18956-121">The deployment tool you choose influences how you onboard endpoints to the service.</span></span>

### <a name="onboarding-tool-options"></a><span data-ttu-id="18956-122">载入工具选项</span><span class="sxs-lookup"><span data-stu-id="18956-122">Onboarding tool options</span></span>

<span data-ttu-id="18956-123">下表列出了基于需要载入的终结点的可用工具。</span><span class="sxs-lookup"><span data-stu-id="18956-123">The following table lists the available tools based on the endpoint that you need to onboard.</span></span>

| <span data-ttu-id="18956-124">终结点</span><span class="sxs-lookup"><span data-stu-id="18956-124">Endpoint</span></span>     | <span data-ttu-id="18956-125">工具选项</span><span class="sxs-lookup"><span data-stu-id="18956-125">Tool options</span></span>                       |
|--------------|------------------------------------------|
| <span data-ttu-id="18956-126">**Windows**</span><span class="sxs-lookup"><span data-stu-id="18956-126">**Windows**</span></span>  |  [<span data-ttu-id="18956-127">本地脚本 (最多 10 台设备) </span><span class="sxs-lookup"><span data-stu-id="18956-127">Local script (up to 10 devices)</span></span>](../defender-endpoint/configure-endpoints-script.md) <br> [<span data-ttu-id="18956-128">组策略</span><span class="sxs-lookup"><span data-stu-id="18956-128">Group Policy</span></span>](../defender-endpoint/configure-endpoints-gp.md) <br> [<span data-ttu-id="18956-129">Microsoft Endpoint Manager/移动设备管理器</span><span class="sxs-lookup"><span data-stu-id="18956-129">Microsoft Endpoint Manager/ Mobile Device Manager</span></span>](../defender-endpoint/configure-endpoints-mdm.md) <br> [<span data-ttu-id="18956-130">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="18956-130">Microsoft Endpoint Configuration Manager</span></span>](../defender-endpoint/configure-endpoints-sccm.md) <br> [<span data-ttu-id="18956-131">VDI 脚本</span><span class="sxs-lookup"><span data-stu-id="18956-131">VDI scripts</span></span>](../defender-endpoint/configure-endpoints-vdi.md) <br> [<span data-ttu-id="18956-132">与 Azure Defender 集成</span><span class="sxs-lookup"><span data-stu-id="18956-132">Integration with Azure Defender</span></span>](../defender-endpoint/configure-server-endpoints.md#integration-with-azure-defender) |
| <span data-ttu-id="18956-133">**macOS**</span><span class="sxs-lookup"><span data-stu-id="18956-133">**macOS**</span></span>    | [<span data-ttu-id="18956-134">本地脚本</span><span class="sxs-lookup"><span data-stu-id="18956-134">Local scripts</span></span>](../defender-endpoint/mac-install-manually.md) <br> [<span data-ttu-id="18956-135">Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="18956-135">Microsoft Endpoint Manager</span></span>](../defender-endpoint/mac-install-with-intune.md) <br> [<span data-ttu-id="18956-136">JAMF Pro</span><span class="sxs-lookup"><span data-stu-id="18956-136">JAMF Pro</span></span>](../defender-endpoint/mac-install-with-jamf.md) <br> [<span data-ttu-id="18956-137">移动设备管理</span><span class="sxs-lookup"><span data-stu-id="18956-137">Mobile Device Management</span></span>](../defender-endpoint/mac-install-with-other-mdm.md) |
| <span data-ttu-id="18956-138">**Linux Server**</span><span class="sxs-lookup"><span data-stu-id="18956-138">**Linux Server**</span></span> | [<span data-ttu-id="18956-139">本地脚本</span><span class="sxs-lookup"><span data-stu-id="18956-139">Local script</span></span>](../defender-endpoint/linux-install-manually.md) <br> [<span data-ttu-id="18956-140">百分百</span><span class="sxs-lookup"><span data-stu-id="18956-140">Puppet</span></span>](../defender-endpoint/linux-install-with-puppet.md) <br> [<span data-ttu-id="18956-141">Ansible</span><span class="sxs-lookup"><span data-stu-id="18956-141">Ansible</span></span>](../defender-endpoint/linux-install-with-ansible.md)|
| <span data-ttu-id="18956-142">**iOS**</span><span class="sxs-lookup"><span data-stu-id="18956-142">**iOS**</span></span>      | [<span data-ttu-id="18956-143">基于应用</span><span class="sxs-lookup"><span data-stu-id="18956-143">App-based</span></span>](../defender-endpoint/ios-install.md)                                |
| <span data-ttu-id="18956-144">**Android**</span><span class="sxs-lookup"><span data-stu-id="18956-144">**Android**</span></span>  | [<span data-ttu-id="18956-145">Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="18956-145">Microsoft Endpoint Manager</span></span>](../defender-endpoint/android-intune.md)               |
