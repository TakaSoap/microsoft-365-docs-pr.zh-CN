---
title: 启用 Microsoft Defender for Endpoint 评估，激活 MDE 评估
description: 启用Microsoft 365 Defender试用实验室或试验环境，包括检查许可证状态和载入 enpoint
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.date: 07/09/2021
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 48186dbfcde897022ac74dfad604c739a45ab68f
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/15/2021
ms.locfileid: "53457638"
---
# <a name="enable-microsoft-defender-for-endpoint-evaluation-environment"></a><span data-ttu-id="07e23-103">启用 Microsoft Defender for Endpoint 评估环境</span><span class="sxs-lookup"><span data-stu-id="07e23-103">Enable Microsoft Defender for Endpoint evaluation environment</span></span>


<span data-ttu-id="07e23-104">本文将指导你完成使用生产设备为 Microsoft Defender for Endpoint 设置评估环境的步骤。</span><span class="sxs-lookup"><span data-stu-id="07e23-104">This article will guide you through the steps on setting up the evaluation environment for Microsoft Defender for Endpoint using production devices.</span></span> 


>[!TIP]
><span data-ttu-id="07e23-105">Microsoft Defender for Endpoint 还附带了产品内评估实验室，你可以添加预配置的设备并运行模拟来评估平台的功能。</span><span class="sxs-lookup"><span data-stu-id="07e23-105">Microsoft Defender for Endpoint also comes with an in-product evaluation lab where you can add pre-configured devices and run simulations to evaluate the capabilities of the platform.</span></span> <span data-ttu-id="07e23-106">实验室附带简化的设置体验，可帮助快速演示 Microsoft Defender for Enpdoint 的价值，包括高级搜寻和威胁分析等许多功能的指南。</span><span class="sxs-lookup"><span data-stu-id="07e23-106">The lab comes with a simplified set-up experience that can help quickly demonstrate the value of Microsoft Defender for Enpdoint including guidance for many features like advanced hunting and threat analytics.</span></span> <span data-ttu-id="07e23-107">有关详细信息，请参阅 [评估功能](/defender-endpoint/evaluation-lab.md)。</span><span class="sxs-lookup"><span data-stu-id="07e23-107">For more information, see [Evaluate capabilities](/defender-endpoint/evaluation-lab.md).</span></span> <br> <span data-ttu-id="07e23-108">本文中提供的指南与评估实验室之间的主要区别在于评估环境使用存储设备，而评估实验室使用非生产设备。</span><span class="sxs-lookup"><span data-stu-id="07e23-108">The main difference between the guidance provided in this article and the evaluation lab is the evaluation environment uses production devices whereas the evaluation lab uses non-production devices.</span></span> 

<span data-ttu-id="07e23-109">使用以下步骤启用 Microsoft Defender for Endpoint 评估。</span><span class="sxs-lookup"><span data-stu-id="07e23-109">Use the following steps to enable the evaluation for Microsoft Defender for Endpoint.</span></span>

![在 Microsoft Defender 评估环境中启用 Microsoft Defender for Endpoint 的步骤](../../media/defender/m365-defender-endpoint-eval-enable-steps.png)

- [<span data-ttu-id="07e23-111">步骤 1.检查许可证状态</span><span class="sxs-lookup"><span data-stu-id="07e23-111">Step 1. Check license state</span></span>](#step-1-check-license-state)
- [<span data-ttu-id="07e23-112">步骤 2.载入终结点</span><span class="sxs-lookup"><span data-stu-id="07e23-112">Step 2. Onboard endpoints</span></span>](#step-2-onboard-endpoints-using-any-of-the-supported-management-tools)


## <a name="step-1-check-license-state"></a><span data-ttu-id="07e23-113">步骤 1.</span><span class="sxs-lookup"><span data-stu-id="07e23-113">Step 1.</span></span> <span data-ttu-id="07e23-114">检查许可证状态</span><span class="sxs-lookup"><span data-stu-id="07e23-114">Check license state</span></span>

<span data-ttu-id="07e23-115">首先需要检查许可证状态，以验证是否正确预配了许可证状态。</span><span class="sxs-lookup"><span data-stu-id="07e23-115">You'll first need to check the license state to verify that it was properly provisioned.</span></span> <span data-ttu-id="07e23-116">可以通过管理中心或管理中心门户 **Microsoft Azure此操作**。</span><span class="sxs-lookup"><span data-stu-id="07e23-116">You can do this through the admin center or through the **Microsoft Azure portal**.</span></span>


1. <span data-ttu-id="07e23-117">若要查看许可证，请转到 Microsoft Azure **门户** 并导航到"Microsoft Azure [门户许可证"部分](https://portal.azure.com/#blade/Microsoft_AAD_IAM/LicensesMenuBlade/Products)。</span><span class="sxs-lookup"><span data-stu-id="07e23-117">To view your licenses, go to the **Microsoft Azure portal** and navigate to the [Microsoft Azure portal license section](https://portal.azure.com/#blade/Microsoft_AAD_IAM/LicensesMenuBlade/Products).</span></span>

   ![Azure 许可页面的图像](../../media/defender/atp-licensing-azure-portal.png)

1. <span data-ttu-id="07e23-119">或者，在管理中心中，导航到"**帐单**  >  **""订阅"。**</span><span class="sxs-lookup"><span data-stu-id="07e23-119">Alternately, in the admin center, navigate to **Billing** > **Subscriptions**.</span></span>

    <span data-ttu-id="07e23-120">在屏幕上，你将看到所有预配的许可证及其当前 **状态**。</span><span class="sxs-lookup"><span data-stu-id="07e23-120">On the screen, you'll see all the provisioned licenses and their current **Status**.</span></span>

    ![帐单许可证的图像](../../media/defender/atp-billing-subscriptions.png)

## <a name="step-2-onboard-endpoints-using-any-of-the-supported-management-tools"></a><span data-ttu-id="07e23-122">步骤 2.</span><span class="sxs-lookup"><span data-stu-id="07e23-122">Step 2.</span></span> <span data-ttu-id="07e23-123">使用任何受支持的管理工具载入终结点</span><span class="sxs-lookup"><span data-stu-id="07e23-123">Onboard endpoints using any of the supported management tools</span></span>

<span data-ttu-id="07e23-124">确认许可证状态已正确预配后，你可以开始将设备载入服务。</span><span class="sxs-lookup"><span data-stu-id="07e23-124">After verifying that the license state has been provisioned properly, you can start onboarding devices to the service.</span></span> 

<span data-ttu-id="07e23-125">为了评估 Microsoft Defender for Endpoint，我们建议选择Windows 10一组设备进行评估。</span><span class="sxs-lookup"><span data-stu-id="07e23-125">For the purpose of evaluating Microsoft Defender for Endpoint, we recommend choosing a couple of Windows 10 devices to conduct the evaluation on.</span></span> 

<span data-ttu-id="07e23-126">规划 [部署](../defender-endpoint/deployment-strategy.md) 主题概述了部署 Defender for Endpoint 所需的常规步骤。</span><span class="sxs-lookup"><span data-stu-id="07e23-126">The [Plan deployment](../defender-endpoint/deployment-strategy.md) topic outlines the general steps you need to take to deploy Defender for Endpoint.</span></span>  

<span data-ttu-id="07e23-127">观看此视频，快速概览载入过程并了解可用的工具和方法。</span><span class="sxs-lookup"><span data-stu-id="07e23-127">Watch this video for a quick overview of the onboarding process and learn about the available tools and methods.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4bGqr]

### <a name="onboarding-tool-options"></a><span data-ttu-id="07e23-128">载入工具选项</span><span class="sxs-lookup"><span data-stu-id="07e23-128">Onboarding tool options</span></span>

<span data-ttu-id="07e23-129">下表列出了基于需要载入的终结点的可用工具。</span><span class="sxs-lookup"><span data-stu-id="07e23-129">The following table lists the available tools based on the endpoint that you need to onboard.</span></span>

<span data-ttu-id="07e23-130">终结点</span><span class="sxs-lookup"><span data-stu-id="07e23-130">Endpoint</span></span> | <span data-ttu-id="07e23-131">工具选项</span><span class="sxs-lookup"><span data-stu-id="07e23-131">Tool options</span></span>
:---|:---
<span data-ttu-id="07e23-132">**Windows**</span><span class="sxs-lookup"><span data-stu-id="07e23-132">**Windows**</span></span> | <span data-ttu-id="07e23-133">[本地脚本 (最多 10](../defender-endpoint/configure-endpoints-script.md)台设备) 、组策略[、Microsoft Endpoint Manager/](../defender-endpoint/configure-endpoints-mdm.md)移动设备[](../defender-endpoint/configure-endpoints-gp.md)管理器[、Microsoft Endpoint Configuration Manager、VDI](../defender-endpoint/configure-endpoints-sccm.md)[脚本](../defender-endpoint/configure-endpoints-vdi.md)、[与 Azure Defender 集成](../defender-endpoint/configure-server-endpoints.md#integration-with-azure-defender)</span><span class="sxs-lookup"><span data-stu-id="07e23-133">[Local script (up to 10 devices)](../defender-endpoint/configure-endpoints-script.md),  [Group Policy](../defender-endpoint/configure-endpoints-gp.md),  [Microsoft Endpoint Manager/ Mobile Device Manager](../defender-endpoint/configure-endpoints-mdm.md),  [Microsoft Endpoint Configuration Manager](../defender-endpoint/configure-endpoints-sccm.md),  [VDI scripts](../defender-endpoint/configure-endpoints-vdi.md),  [Integration with Azure Defender](../defender-endpoint/configure-server-endpoints.md#integration-with-azure-defender)</span></span>
<span data-ttu-id="07e23-134">**macOS**</span><span class="sxs-lookup"><span data-stu-id="07e23-134">**macOS**</span></span> | <span data-ttu-id="07e23-135">[本地脚本](../defender-endpoint/mac-install-manually.md)、 [Microsoft Endpoint Manager](../defender-endpoint/mac-install-with-intune.md)、 [JAMF Pro](../defender-endpoint/mac-install-with-jamf.md)、[移动设备管理](../defender-endpoint/mac-install-with-other-mdm.md)</span><span class="sxs-lookup"><span data-stu-id="07e23-135">[Local scripts](../defender-endpoint/mac-install-manually.md),  [Microsoft Endpoint Manager](../defender-endpoint/mac-install-with-intune.md),  [JAMF Pro](../defender-endpoint/mac-install-with-jamf.md),  [Mobile Device Management](../defender-endpoint/mac-install-with-other-mdm.md)</span></span>
<span data-ttu-id="07e23-136">**Linux Server**</span><span class="sxs-lookup"><span data-stu-id="07e23-136">**Linux Server**</span></span> | <span data-ttu-id="07e23-137">[本地脚本](../defender-endpoint/linux-install-manually.md)  [、安装](../defender-endpoint/linux-install-with-puppet.md)  [、Ansible](../defender-endpoint/linux-install-with-ansible.md)</span><span class="sxs-lookup"><span data-stu-id="07e23-137">[Local script](../defender-endpoint/linux-install-manually.md),  [Puppet](../defender-endpoint/linux-install-with-puppet.md),  [Ansible](../defender-endpoint/linux-install-with-ansible.md)</span></span>
<span data-ttu-id="07e23-138">**iOS**</span><span class="sxs-lookup"><span data-stu-id="07e23-138">**iOS**</span></span> | [<span data-ttu-id="07e23-139">基于应用</span><span class="sxs-lookup"><span data-stu-id="07e23-139">App-based</span></span>](../defender-endpoint/ios-install.md)
<span data-ttu-id="07e23-140">**Android**</span><span class="sxs-lookup"><span data-stu-id="07e23-140">**Android**</span></span> | [<span data-ttu-id="07e23-141">Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="07e23-141">Microsoft Endpoint Manager</span></span>](../defender-endpoint/android-intune.md)



## <a name="next-step"></a><span data-ttu-id="07e23-142">下一步</span><span class="sxs-lookup"><span data-stu-id="07e23-142">Next step</span></span>
[<span data-ttu-id="07e23-143">设置适用于终结点的 Microsoft Defender 的试点</span><span class="sxs-lookup"><span data-stu-id="07e23-143">Setup the pilot for Microsoft Defender for Endpoint</span></span>](eval-defender-endpoint-pilot.md)
 
<span data-ttu-id="07e23-144">返回到评估 Microsoft [Defender for Endpoint 的概述](eval-defender-endpoint-overview.md)</span><span class="sxs-lookup"><span data-stu-id="07e23-144">Return to the overview for [Evaluate Microsoft Defender for Endpoint](eval-defender-endpoint-overview.md)</span></span>

<span data-ttu-id="07e23-145">返回到评估和试点[计划概述Microsoft 365 Defender](eval-overview.md)</span><span class="sxs-lookup"><span data-stu-id="07e23-145">Return to the overview for [Evaluate and pilot Microsoft 365 Defender](eval-overview.md)</span></span>