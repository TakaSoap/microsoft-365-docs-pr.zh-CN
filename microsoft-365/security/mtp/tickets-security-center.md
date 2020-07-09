---
title: 在 Microsoft 365 安全中心中创建和跟踪 ServiceNow 票证
description: 了解如何从 Microsoft 365 安全中心创建和跟踪 ServiceNow 中的票证。
keywords: security、Microsoft 365、M365、安全分数、安全中心、ServiceNow、票证、任务
ms.prod: w10
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
ms.openlocfilehash: 48512cf2fff802509ebaa14ca69d3ca02908902e
ms.sourcegitcommit: 41bc923bb31598cea8f02923792c1cd786e39616
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/09/2020
ms.locfileid: "45087908"
---
# <a name="create-and-track-servicenow-tickets-in-the-microsoft-365-security-center"></a><span data-ttu-id="c47f3-104">在 Microsoft 365 安全中心中创建和跟踪 ServiceNow 票证</span><span class="sxs-lookup"><span data-stu-id="c47f3-104">Create and track ServiceNow tickets in the Microsoft 365 security center</span></span>

<span data-ttu-id="c47f3-105">[Microsoft 365 安全中心](overview-security-center.md)已得到增强，能够在 ServiceNow 中以本机方式创建和跟踪票证。</span><span class="sxs-lookup"><span data-stu-id="c47f3-105">The [Microsoft 365 security center](overview-security-center.md) has been enhanced with the ability to natively create and track tickets in ServiceNow.</span></span> [<span data-ttu-id="c47f3-106">了解有关 ServiceNow 的详细信息</span><span class="sxs-lookup"><span data-stu-id="c47f3-106">Learn more about ServiceNow</span></span>](https://www.servicenow.com/)

<span data-ttu-id="c47f3-107">在安全中心中，安全管理员可以直接向 ServiceNow 发送[Microsoft Secure 得分](microsoft-secure-score.md)改进操作，并创建一个票证。</span><span class="sxs-lookup"><span data-stu-id="c47f3-107">In the security center, security administrators can send a [Microsoft Secure Score](microsoft-secure-score.md) improvement action directly to ServiceNow and create a ticket.</span></span> <span data-ttu-id="c47f3-108">可以创建事件管理和变更管理票证。</span><span class="sxs-lookup"><span data-stu-id="c47f3-108">Both incident management and change management tickets can be created.</span></span> <span data-ttu-id="c47f3-109">然后，可以在安全中心主页和 ServiceNow 中跟踪它们。</span><span class="sxs-lookup"><span data-stu-id="c47f3-109">They can then be tracked in the security center home page, and ServiceNow.</span></span>

- [<span data-ttu-id="c47f3-110">**了解先决条件、数据交换和疑难解答**</span><span class="sxs-lookup"><span data-stu-id="c47f3-110">**Learn about prerequisites, data exchange, and troubleshooting**</span></span>](tickets.md)
- <span data-ttu-id="c47f3-111">**在合规中心中管理 ServiceNow 票证**（即将推出）</span><span class="sxs-lookup"><span data-stu-id="c47f3-111">**Manage ServiceNow tickets in the compliance center** (coming soon)</span></span>

## <a name="connect-microsoft-365-security-center-to-servicenow"></a><span data-ttu-id="c47f3-112">将 Microsoft 365 安全中心连接到 ServiceNow</span><span class="sxs-lookup"><span data-stu-id="c47f3-112">Connect Microsoft 365 security center to ServiceNow</span></span>

<span data-ttu-id="c47f3-113">导航到 Microsoft 365 安全中心主页以查看 ServiceNow 连接卡。</span><span class="sxs-lookup"><span data-stu-id="c47f3-113">Navigate to the Microsoft 365 security center home page to see the ServiceNow connection card.</span></span>

![您是否使用 ServiceNow](../../media/do-you-use-servicenow-250.png)

<span data-ttu-id="c47f3-115">选择 "连接到 ServiceNow" 以转到 "ServiceNow 设置" 页。</span><span class="sxs-lookup"><span data-stu-id="c47f3-115">Select "Connect to ServiceNow" to go to the ServiceNow setup page.</span></span> <span data-ttu-id="c47f3-116">按照说明授权 Microsoft 365 连接器应用。</span><span class="sxs-lookup"><span data-stu-id="c47f3-116">Follow the instructions to authorize the Microsoft 365 Connector app.</span></span>

> [!NOTE]
> <span data-ttu-id="c47f3-117">在授权 Microsoft 365 安全中心和 ServiceNow 之间的连接之前，请确保使用您在安装步骤中创建的集成用户登录名和密码。</span><span class="sxs-lookup"><span data-stu-id="c47f3-117">Before you authorize the connection between Microsoft 365 security center and ServiceNow, make sure you use the integration user login and password you created in the installation steps.</span></span> <span data-ttu-id="c47f3-118">请勿使用你的个人凭据。</span><span class="sxs-lookup"><span data-stu-id="c47f3-118">Do not use your personal credentials.</span></span>

<span data-ttu-id="c47f3-119">按照说明进行操作并授权连接后，请查看 Microsoft 365 安全中心连接页和 ServiceNow Microsoft 365 票证发放连接器应用程序体验中的连接状态。</span><span class="sxs-lookup"><span data-stu-id="c47f3-119">After you have followed the directions and authorizing the connection, view the connection status on both the Microsoft 365 security center connection page and in the ServiceNow Microsoft 365 Ticketing Connector App experience.</span></span> <span data-ttu-id="c47f3-120">现在，你已设置为开始创建任务！</span><span class="sxs-lookup"><span data-stu-id="c47f3-120">Now you are all set to start creating tasks!</span></span>

### <a name="troubleshooting"></a><span data-ttu-id="c47f3-121">疑难解答</span><span class="sxs-lookup"><span data-stu-id="c47f3-121">Troubleshooting</span></span>

<span data-ttu-id="c47f3-122">了解在连接过程中可能遇到的常见错误，以及如何在 "[疑难解答" 部分](tickets.md#troubleshooting)中对其进行缓解。</span><span class="sxs-lookup"><span data-stu-id="c47f3-122">Learn common errors you may encounter in the connection process, and how to mitigate them, in the [troubleshooting section](tickets.md#troubleshooting).</span></span>

## <a name="create-a-task-and-share-it-to-servicenow"></a><span data-ttu-id="c47f3-123">创建一个任务并将其共享到 ServiceNow</span><span class="sxs-lookup"><span data-stu-id="c47f3-123">Create a task and share it to ServiceNow</span></span>

<span data-ttu-id="c47f3-124">建立集成后，基于特定 Microsoft 安全得分改进操作创建 ServiceNow 任务。</span><span class="sxs-lookup"><span data-stu-id="c47f3-124">Once the integration is set up, create ServiceNow tasks based on specific Microsoft Secure Score improvement actions.</span></span> <span data-ttu-id="c47f3-125">转到 Microsoft 365 安全中心门户中安全得分的任何改进措施，并选择 "共享" 图标。</span><span class="sxs-lookup"><span data-stu-id="c47f3-125">Go to any improvement action in Secure Score in the Microsoft 365 security center portal, and select the "share" icon.</span></span> <span data-ttu-id="c47f3-126">其中一个下拉选项是 ServiceNow。</span><span class="sxs-lookup"><span data-stu-id="c47f3-126">One of the dropdown options is ServiceNow.</span></span>

![安全分数中的 ServiceNow 共享](../../media/servicenow-share.png)

<span data-ttu-id="c47f3-128">将生成一个任务，您可以在其中设置优先级并编辑名称、说明或截止日期。</span><span class="sxs-lookup"><span data-stu-id="c47f3-128">A task is generated where you can set the priority and edit the name, description, or due date.</span></span> <span data-ttu-id="c47f3-129">填写所有必填字段后，将该任务发送到 ServiceNow。</span><span class="sxs-lookup"><span data-stu-id="c47f3-129">Once all the required fields are filled in, send the task to ServiceNow.</span></span>

<span data-ttu-id="c47f3-130">在 ServiceNow 中，此任务显示为 Microsoft 365 安全性和配置更改请求。</span><span class="sxs-lookup"><span data-stu-id="c47f3-130">The task is visible in ServiceNow as a Microsoft 365 Security and Configuration Change Request.</span></span>

## <a name="track-tickets"></a><span data-ttu-id="c47f3-131">跟踪票证</span><span class="sxs-lookup"><span data-stu-id="c47f3-131">Track tickets</span></span>

<span data-ttu-id="c47f3-132">一旦创建了 ServiceNow 更改管理和事件管理票证，它们就会显示在 Microsoft 365 安全中心主页上的卡片上。</span><span class="sxs-lookup"><span data-stu-id="c47f3-132">Once ServiceNow change management and incident management tickets have been created, they are displayed on cards in the Microsoft 365 security center home page.</span></span> <span data-ttu-id="c47f3-133">通过这些卡，您可以创建一个票证、查看所有票证或管理 ServiceNow 配置。</span><span class="sxs-lookup"><span data-stu-id="c47f3-133">From these cards, you can create a ticket, view all tickets, or manage the ServiceNow configuration.</span></span>

![ServiceNow 更改管理票证](../../media/change-management-375.png)  ![ServiceNow 事件管理票证](../../media/incident-management-375.png)

<span data-ttu-id="c47f3-136">若要在 Microsoft 365 安全中心中重新设置或管理你的 ServiceNow 集成，请选择任一卡片上的 "**管理 servicenow 配置**"。</span><span class="sxs-lookup"><span data-stu-id="c47f3-136">To re-provision or manage your ServiceNow integration in the Microsoft 365 security center, select **Manage ServiceNow configuration** on either of the cards.</span></span> <span data-ttu-id="c47f3-137">在此处，删除当前的 ServiceNow 连接并自定义票证状态名称。</span><span class="sxs-lookup"><span data-stu-id="c47f3-137">From there, remove the current ServiceNow connection and customize ticket state names.</span></span>

<span data-ttu-id="c47f3-138">借助 Microsoft 365 security center 中显示的 ServiceNow 票证，你的任务可以在某个位置进行跟踪，并在你的其他安全仪表板项目旁边进行操作。</span><span class="sxs-lookup"><span data-stu-id="c47f3-138">With ServiceNow tickets visible in the Microsoft 365 security center, your tasks live in a place where they can be tracked and acted upon alongside your other security dashboard items.</span></span>

## <a name="resources"></a><span data-ttu-id="c47f3-139">资源</span><span class="sxs-lookup"><span data-stu-id="c47f3-139">Resources</span></span>

- [<span data-ttu-id="c47f3-140">了解先决条件、数据交换和疑难解答</span><span class="sxs-lookup"><span data-stu-id="c47f3-140">Learn about prerequisites, data exchange, and troubleshooting</span></span>](tickets.md)
- [<span data-ttu-id="c47f3-141">Microsoft 安全功能分数</span><span class="sxs-lookup"><span data-stu-id="c47f3-141">Microsoft Secure Score</span></span>](microsoft-secure-score.md)