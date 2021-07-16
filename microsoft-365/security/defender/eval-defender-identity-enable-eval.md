---
title: 启用 Microsoft Defender 标识评估环境，设置 MDI 实例，安装和配置 MDI 传感器，让 MDI 传感器检测本地管理员
description: 在试用实验室或Microsoft 365 Defender环境中设置 Microsoft Defender for Identity，&配置传感器，并发现其他计算机上的本地管理员。
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
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
ms.openlocfilehash: f739c9897c9c43831cb4ed23cabaa1705c75d712
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/15/2021
ms.locfileid: "53457632"
---
# <a name="enable-the-evaluation-environment-for-microsoft-defender-for-identity"></a><span data-ttu-id="2d156-103">启用 Microsoft Defender 标识评估环境</span><span class="sxs-lookup"><span data-stu-id="2d156-103">Enable the evaluation environment for Microsoft Defender for Identity</span></span>

<span data-ttu-id="2d156-104">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="2d156-104">**Applies to:**</span></span>
- <span data-ttu-id="2d156-105">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2d156-105">Microsoft 365 Defender</span></span>

<span data-ttu-id="2d156-106">本文是设置 Microsoft Defender for Identity 评估环境过程中第 2 步（第 [2](eval-defender-identity-overview.md) 步）。</span><span class="sxs-lookup"><span data-stu-id="2d156-106">This article is [Step 2 of 2](eval-defender-identity-overview.md) in the process of setting up the evaluation environment for Microsoft Defender for Identity.</span></span> <span data-ttu-id="2d156-107">有关此过程详细信息，请参阅 [概述文章](eval-defender-identity-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="2d156-107">For more information about this process, see the [overview article](eval-defender-identity-overview.md).</span></span>

<span data-ttu-id="2d156-108">使用以下步骤设置 Microsoft Defender for Identity 环境。</span><span class="sxs-lookup"><span data-stu-id="2d156-108">Use the following steps to set up your Microsoft Defender for Identity environment.</span></span> 

![在 Microsoft Defender 评估环境中启用 Microsoft Defender 标识的步骤](../../media/defender/m365-defender-identity-eval-enable-steps.png)

- [<span data-ttu-id="2d156-110">步骤 1.设置 Defender for Identity 实例</span><span class="sxs-lookup"><span data-stu-id="2d156-110">Step 1. Set up the Defender for Identity Instance</span></span>](#step-1-set-up-the-defender-for-identity-instance)
- [<span data-ttu-id="2d156-111">步骤 2.安装和配置传感器</span><span class="sxs-lookup"><span data-stu-id="2d156-111">Step 2. Install and configure the sensor</span></span>](#step-2-install-and-configure-the-sensor)
- [<span data-ttu-id="2d156-112">步骤 3.使用传感器在计算机中配置事件日志和代理设置</span><span class="sxs-lookup"><span data-stu-id="2d156-112">Step 3. Configure event log and proxy settings on machines with the sensor</span></span>](#step-3-configure-event-log-and-proxy-settings-on-machines-with-the-sensor)
- [<span data-ttu-id="2d156-113">步骤 4.允许 Defender for Identity 识别其他计算机上的本地管理员</span><span class="sxs-lookup"><span data-stu-id="2d156-113">Step 4. Allow Defender for Identity to identify local admins on other computers</span></span>](#step-4-allow-defender-for-identity-to-identify-local-admins-on-other-computers)

## <a name="step-1-set-up-the-defender-for-identity-instance"></a><span data-ttu-id="2d156-114">步骤 1.</span><span class="sxs-lookup"><span data-stu-id="2d156-114">Step 1.</span></span> <span data-ttu-id="2d156-115">设置 Defender for Identity 实例</span><span class="sxs-lookup"><span data-stu-id="2d156-115">Set up the Defender for Identity Instance</span></span>

<span data-ttu-id="2d156-116">登录到 Defender for Identity 门户以创建实例，然后将此实例连接到 Active Directory 环境。</span><span class="sxs-lookup"><span data-stu-id="2d156-116">Sign in to the Defender for Identity portal to create your instance and then connect this instance to your Active Directory environment.</span></span> 

|  |<span data-ttu-id="2d156-117">步骤</span><span class="sxs-lookup"><span data-stu-id="2d156-117">Step</span></span>     |<span data-ttu-id="2d156-118">详细信息</span><span class="sxs-lookup"><span data-stu-id="2d156-118">More information</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="2d156-119">1</span><span class="sxs-lookup"><span data-stu-id="2d156-119">1</span></span>     | <span data-ttu-id="2d156-120">创建 Defender for Identity 实例</span><span class="sxs-lookup"><span data-stu-id="2d156-120">Create the Defender for Identity instance</span></span>        | [<span data-ttu-id="2d156-121">快速入门：创建 Microsoft Defender for Identity 实例</span><span class="sxs-lookup"><span data-stu-id="2d156-121">Quickstart: Create your Microsoft Defender for Identity instance</span></span>](/defender-for-identity/install-step1)        |
|<span data-ttu-id="2d156-122">2</span><span class="sxs-lookup"><span data-stu-id="2d156-122">2</span></span>     | <span data-ttu-id="2d156-123">连接 Active Directory 林中设置 Defender for Identity 实例</span><span class="sxs-lookup"><span data-stu-id="2d156-123">Connect the Defender for Identity instance to your Active Directory forest</span></span>   | [<span data-ttu-id="2d156-124">快速入门：连接 Active Directory 林</span><span class="sxs-lookup"><span data-stu-id="2d156-124">Quickstart: Connect to your Active Directory Forest</span></span>](/defender-for-identity/install-step2)  |
| | |

## <a name="step-2-install-and-configure-the-sensor"></a><span data-ttu-id="2d156-125">步骤 2.</span><span class="sxs-lookup"><span data-stu-id="2d156-125">Step 2.</span></span> <span data-ttu-id="2d156-126">安装和配置传感器</span><span class="sxs-lookup"><span data-stu-id="2d156-126">Install and configure the sensor</span></span>

<span data-ttu-id="2d156-127">接下来，在本地环境的域控制器和 AD FS 服务器上下载、安装和配置 Defender for Identity 传感器。</span><span class="sxs-lookup"><span data-stu-id="2d156-127">Next, download, install, and configure the Defender for Identity sensor on the domain controllers and AD FS servers in your on-premises environment.</span></span>

|  |<span data-ttu-id="2d156-128">步骤</span><span class="sxs-lookup"><span data-stu-id="2d156-128">Step</span></span>     |<span data-ttu-id="2d156-129">详细信息</span><span class="sxs-lookup"><span data-stu-id="2d156-129">More information</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="2d156-130">1</span><span class="sxs-lookup"><span data-stu-id="2d156-130">1</span></span>     | <span data-ttu-id="2d156-131">确定你需要多少个 Microsoft Defender for Identity 传感器。</span><span class="sxs-lookup"><span data-stu-id="2d156-131">Determine how many Microsoft Defender for Identity sensors you need.</span></span>        | [<span data-ttu-id="2d156-132">规划 Microsoft Defender 标识容量</span><span class="sxs-lookup"><span data-stu-id="2d156-132">Plan capacity for Microsoft Defender for Identity</span></span>](/defender-for-identity/capacity-planning)   |
|<span data-ttu-id="2d156-133">2</span><span class="sxs-lookup"><span data-stu-id="2d156-133">2</span></span>     | <span data-ttu-id="2d156-134">下载传感器安装程序包</span><span class="sxs-lookup"><span data-stu-id="2d156-134">Download the sensor setup package</span></span>  |  [<span data-ttu-id="2d156-135">快速入门：下载 Microsoft Defender for Identity 传感器安装程序包</span><span class="sxs-lookup"><span data-stu-id="2d156-135">Quickstart: Download the Microsoft Defender for Identity sensor setup package</span></span>](/defender-for-identity/install-step3)   |
|<span data-ttu-id="2d156-136">3</span><span class="sxs-lookup"><span data-stu-id="2d156-136">3</span></span>     | <span data-ttu-id="2d156-137">安装 Defender for Identity 传感器</span><span class="sxs-lookup"><span data-stu-id="2d156-137">Install the Defender for Identity sensor</span></span>    |  [<span data-ttu-id="2d156-138">快速入门：安装 Microsoft Defender for Identity 传感器</span><span class="sxs-lookup"><span data-stu-id="2d156-138">Quickstart: Install the Microsoft Defender for Identity sensor</span></span>](/defender-for-identity/install-step4)       |
|<span data-ttu-id="2d156-139">4 </span><span class="sxs-lookup"><span data-stu-id="2d156-139">4</span></span>     | <span data-ttu-id="2d156-140">配置传感器</span><span class="sxs-lookup"><span data-stu-id="2d156-140">Configure the sensor</span></span>       |  [<span data-ttu-id="2d156-141">配置 Microsoft Defender for Identity 传感器设置 </span><span class="sxs-lookup"><span data-stu-id="2d156-141">Configure Microsoft Defender for Identity sensor settings </span></span>](/defender-for-identity/install-step5)   |
|   |         |         |

## <a name="step-3-configure-event-log-and-proxy-settings-on-machines-with-the-sensor"></a><span data-ttu-id="2d156-142">步骤 3.</span><span class="sxs-lookup"><span data-stu-id="2d156-142">Step 3.</span></span> <span data-ttu-id="2d156-143">使用传感器在计算机中配置事件日志和代理设置</span><span class="sxs-lookup"><span data-stu-id="2d156-143">Configure event log and proxy settings on machines with the sensor</span></span>

<span data-ttu-id="2d156-144">在安装了传感器的计算机上安装，Windows事件日志集合和 Internet 代理设置以启用和增强检测功能。</span><span class="sxs-lookup"><span data-stu-id="2d156-144">On the machines that you installed the sensor on, configure Windows event log collection and Internet proxy settings to enable and enhance detection capabilities.</span></span>

|  |<span data-ttu-id="2d156-145">步骤</span><span class="sxs-lookup"><span data-stu-id="2d156-145">Step</span></span>     |<span data-ttu-id="2d156-146">详细信息</span><span class="sxs-lookup"><span data-stu-id="2d156-146">More information</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="2d156-147">1</span><span class="sxs-lookup"><span data-stu-id="2d156-147">1</span></span>     | <span data-ttu-id="2d156-148">配置Windows事件日志集合</span><span class="sxs-lookup"><span data-stu-id="2d156-148">Configure Windows event log collection</span></span>         | [<span data-ttu-id="2d156-149">配置 Windows 事件集合</span><span class="sxs-lookup"><span data-stu-id="2d156-149">Configure Windows Event collection</span></span>](/defender-for-identity/configure-windows-event-collection)        |
|<span data-ttu-id="2d156-150">2</span><span class="sxs-lookup"><span data-stu-id="2d156-150">2</span></span>     | <span data-ttu-id="2d156-151">配置 Internet 代理设置</span><span class="sxs-lookup"><span data-stu-id="2d156-151">Configure Internet proxy settings</span></span>        | [<span data-ttu-id="2d156-152">为 Microsoft Defender for Identity Sensor 配置终结点代理和 Internet 连接设置</span><span class="sxs-lookup"><span data-stu-id="2d156-152">Configure endpoint proxy and Internet connectivity settings for your Microsoft Defender for Identity Sensor</span></span>](/defender-for-identity/configure-proxy)        |
|   |         |         |

## <a name="step-4-allow-defender-for-identity-to-identify-local-admins-on-other-computers"></a><span data-ttu-id="2d156-153">步骤 4.</span><span class="sxs-lookup"><span data-stu-id="2d156-153">Step 4.</span></span> <span data-ttu-id="2d156-154">允许 Defender for Identity 识别其他计算机上的本地管理员</span><span class="sxs-lookup"><span data-stu-id="2d156-154">Allow Defender for Identity to identify local admins on other computers</span></span>

<span data-ttu-id="2d156-155">Microsoft Defender for Identity 横向移动路径检测依赖于标识特定计算机上本地管理员的查询。</span><span class="sxs-lookup"><span data-stu-id="2d156-155">Microsoft Defender for Identity lateral movement path detection relies on queries that identify local admins on specific machines.</span></span> <span data-ttu-id="2d156-156">这些查询通过 SAM-R 协议使用 Defender for Identity Service 帐户执行。</span><span class="sxs-lookup"><span data-stu-id="2d156-156">These queries are performed with the SAM-R protocol, using the Defender for Identity Service account.</span></span> 

<span data-ttu-id="2d156-157">若要Windows客户端和服务器允许 Defender for Identity 帐户执行 SAM-R，除了网络访问策略中列出的配置帐户之外，还必须修改组策略以添加 Defender for Identity 服务帐户。</span><span class="sxs-lookup"><span data-stu-id="2d156-157">To ensure Windows clients and servers allow your Defender for Identity account to perform SAM-R, a modification to Group Policy must be made to add the Defender for Identity service account in addition to the configured accounts listed in the Network access policy.</span></span> <span data-ttu-id="2d156-158">请确保将组策略应用于除 **域控制器 之外的所有计算机**。</span><span class="sxs-lookup"><span data-stu-id="2d156-158">Make sure to apply group policies to all computers **except domain controllers**.</span></span>

<span data-ttu-id="2d156-159">有关如何执行此操作的说明，请参阅配置 [Microsoft Defender for Identity 以对 SAM 进行远程调用](/defender-for-identity/install-step8-samr)。</span><span class="sxs-lookup"><span data-stu-id="2d156-159">For instructions on how to do this, see [Configure Microsoft Defender for Identity to make remote calls to SAM](/defender-for-identity/install-step8-samr).</span></span> 

## <a name="next-steps"></a><span data-ttu-id="2d156-160">后续步骤</span><span class="sxs-lookup"><span data-stu-id="2d156-160">Next steps</span></span>

<span data-ttu-id="2d156-161">步骤 3/3： [试用 Microsoft Defender for Identity](eval-defender-identity-pilot.md)</span><span class="sxs-lookup"><span data-stu-id="2d156-161">Step 3 of 3: [Pilot Microsoft Defender for Identity](eval-defender-identity-pilot.md)</span></span>

<span data-ttu-id="2d156-162">返回到评估 Microsoft [Defender 标识概述](eval-defender-identity-overview.md)</span><span class="sxs-lookup"><span data-stu-id="2d156-162">Return to the overview for [Evaluate Microsoft Defender for Identity](eval-defender-identity-overview.md)</span></span>

<span data-ttu-id="2d156-163">返回到评估和试点[计划概述Microsoft 365 Defender](eval-overview.md)</span><span class="sxs-lookup"><span data-stu-id="2d156-163">Return to the overview for [Evaluate and pilot Microsoft 365 Defender](eval-overview.md)</span></span>