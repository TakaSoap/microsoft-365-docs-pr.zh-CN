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
ms.openlocfilehash: bd5bf8533d38337c063acdf0dda073e4961e416a
ms.sourcegitcommit: 787b198765565d54ee73972f664bdbd5023d666b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/24/2020
ms.locfileid: "46867241"
---
# <a name="create-and-track-servicenow-tickets-in-the-microsoft-365-security-center"></a><span data-ttu-id="885e9-104">在 Microsoft 365 安全中心中创建和跟踪 ServiceNow 票证</span><span class="sxs-lookup"><span data-stu-id="885e9-104">Create and track ServiceNow tickets in the Microsoft 365 security center</span></span>

<span data-ttu-id="885e9-105">[Microsoft 365 安全中心](overview-security-center.md)已得到增强，能够在 ServiceNow 中以本机方式创建和跟踪票证。</span><span class="sxs-lookup"><span data-stu-id="885e9-105">The [Microsoft 365 security center](overview-security-center.md) has been enhanced with the ability to natively create and track tickets in ServiceNow.</span></span> [<span data-ttu-id="885e9-106">了解有关 ServiceNow 的详细信息</span><span class="sxs-lookup"><span data-stu-id="885e9-106">Learn more about ServiceNow</span></span>](https://www.servicenow.com/)

<span data-ttu-id="885e9-107">在安全中心中，安全管理员可以直接向 ServiceNow 发送 [Microsoft Secure 得分](microsoft-secure-score.md) 改进操作，并创建一个票证。</span><span class="sxs-lookup"><span data-stu-id="885e9-107">In the security center, security administrators can send a [Microsoft Secure Score](microsoft-secure-score.md) improvement action directly to ServiceNow and create a ticket.</span></span> <span data-ttu-id="885e9-108">可以创建事件管理和变更管理票证。</span><span class="sxs-lookup"><span data-stu-id="885e9-108">Both incident management and change management tickets can be created.</span></span> <span data-ttu-id="885e9-109">跟踪安全中心主页和 ServiceNow 中的票证。</span><span class="sxs-lookup"><span data-stu-id="885e9-109">Track tickets in the security center home page and ServiceNow.</span></span>

- [<span data-ttu-id="885e9-110">**了解先决条件、数据交换和疑难解答**</span><span class="sxs-lookup"><span data-stu-id="885e9-110">**Learn about prerequisites, data exchange, and troubleshooting**</span></span>](tickets.md)
- <span data-ttu-id="885e9-111">**在合规中心中管理 ServiceNow 票证** (即将推出) </span><span class="sxs-lookup"><span data-stu-id="885e9-111">**Manage ServiceNow tickets in the compliance center** (coming soon)</span></span>

## <a name="connect-microsoft-365-security-center-to-servicenow"></a><span data-ttu-id="885e9-112">将 Microsoft 365 安全中心连接到 ServiceNow</span><span class="sxs-lookup"><span data-stu-id="885e9-112">Connect Microsoft 365 security center to ServiceNow</span></span>

<span data-ttu-id="885e9-113">导航到 Microsoft 365 安全中心主页以查看 ServiceNow 连接卡。</span><span class="sxs-lookup"><span data-stu-id="885e9-113">Navigate to the Microsoft 365 security center home page to see the ServiceNow connection card.</span></span>

![您是否使用 ServiceNow](../../media/do-you-use-servicenow-250.png)

<span data-ttu-id="885e9-115">选择 "连接到 ServiceNow" 以转到 "ServiceNow 设置" 页。</span><span class="sxs-lookup"><span data-stu-id="885e9-115">Select "Connect to ServiceNow" to go to the ServiceNow setup page.</span></span> <span data-ttu-id="885e9-116">按照说明授权 Microsoft 365 连接器应用。</span><span class="sxs-lookup"><span data-stu-id="885e9-116">Follow the instructions to authorize the Microsoft 365 Connector app.</span></span>

> [!NOTE]
> <span data-ttu-id="885e9-117">在授权 Microsoft 365 安全中心和 ServiceNow 之间的连接之前，请确保使用您在安装步骤中创建的集成用户登录名和密码。</span><span class="sxs-lookup"><span data-stu-id="885e9-117">Before you authorize the connection between Microsoft 365 security center and ServiceNow, make sure you use the integration user login and password you created in the installation steps.</span></span> <span data-ttu-id="885e9-118">请勿使用你的个人凭据。</span><span class="sxs-lookup"><span data-stu-id="885e9-118">Do not use your personal credentials.</span></span>

<span data-ttu-id="885e9-119">按照说明进行操作并授权连接后，在 Microsoft 365 安全中心连接页和 ServiceNow Microsoft 365 票证发放连接器应用程序体验中查看连接状态。</span><span class="sxs-lookup"><span data-stu-id="885e9-119">After you've followed the directions and authorized the connection, view the connection status in the Microsoft 365 security center connection page and in the ServiceNow Microsoft 365 Ticketing Connector App experience.</span></span> <span data-ttu-id="885e9-120">现在你已设置为开始创建任务！</span><span class="sxs-lookup"><span data-stu-id="885e9-120">Now you're all set to start creating tasks!</span></span>

### <a name="troubleshooting"></a><span data-ttu-id="885e9-121">故障排除</span><span class="sxs-lookup"><span data-stu-id="885e9-121">Troubleshooting</span></span>

<span data-ttu-id="885e9-122">了解可能在连接过程中遇到的常见错误，以及如何在 " [疑难解答" 部分](tickets.md#troubleshooting)中对其进行缓解。</span><span class="sxs-lookup"><span data-stu-id="885e9-122">Learn common errors you may come across in the connection process, and how to mitigate them, in the [troubleshooting section](tickets.md#troubleshooting).</span></span>

## <a name="create-a-task-and-share-it-to-servicenow"></a><span data-ttu-id="885e9-123">创建一个任务并将其共享到 ServiceNow</span><span class="sxs-lookup"><span data-stu-id="885e9-123">Create a task and share it to ServiceNow</span></span>

<span data-ttu-id="885e9-124">建立集成后，基于特定 [Microsoft 安全得分](microsoft-secure-score.md) 改进操作创建 ServiceNow 任务。</span><span class="sxs-lookup"><span data-stu-id="885e9-124">Once the integration is set up, create ServiceNow tasks based on specific [Microsoft Secure Score](microsoft-secure-score.md) improvement actions.</span></span> <span data-ttu-id="885e9-125">转到 Microsoft 365 安全中心中的任何安全得分改进操作，并选择 " **共享**"。</span><span class="sxs-lookup"><span data-stu-id="885e9-125">Go to any Secure Score improvement action in the Microsoft 365 security center, and select **Share**.</span></span> <span data-ttu-id="885e9-126">其中一个下拉选项是 ServiceNow。</span><span class="sxs-lookup"><span data-stu-id="885e9-126">One of the dropdown options is ServiceNow.</span></span>

<span data-ttu-id="885e9-127">将生成一个任务，您可以在其中设置优先级并编辑名称、说明或截止日期。</span><span class="sxs-lookup"><span data-stu-id="885e9-127">A task is generated where you can set the priority and edit the name, description, or due date.</span></span> <span data-ttu-id="885e9-128">填写所有必填字段后，将该任务发送到 ServiceNow。</span><span class="sxs-lookup"><span data-stu-id="885e9-128">Once all the required fields are filled in, send the task to ServiceNow.</span></span>

<span data-ttu-id="885e9-129">在 ServiceNow 中，此任务显示为 Microsoft 365 安全性和配置更改请求。</span><span class="sxs-lookup"><span data-stu-id="885e9-129">The task is visible in ServiceNow as a Microsoft 365 Security and Configuration Change Request.</span></span>

## <a name="track-tickets"></a><span data-ttu-id="885e9-130">跟踪票证</span><span class="sxs-lookup"><span data-stu-id="885e9-130">Track tickets</span></span>

<span data-ttu-id="885e9-131">一旦创建了 ServiceNow 更改管理和事件管理票证，它们就会显示在 Microsoft 365 安全中心主页上的卡片上。</span><span class="sxs-lookup"><span data-stu-id="885e9-131">Once ServiceNow change management and incident management tickets have been created, they're displayed on cards in the Microsoft 365 security center home page.</span></span> <span data-ttu-id="885e9-132">通过这些卡，您可以创建一个票证、查看所有票证或管理 ServiceNow 配置。</span><span class="sxs-lookup"><span data-stu-id="885e9-132">From these cards, you can create a ticket, view all tickets, or manage the ServiceNow configuration.</span></span>

![ServiceNow 更改管理票证](../../media/change-management-375.png)  ![ServiceNow 事件管理票证](../../media/incident-management-375.png)

<span data-ttu-id="885e9-135">若要在 Microsoft 365 安全中心中重新设置或管理你的 ServiceNow 集成，请选择任一卡片上的 " **管理 servicenow 配置** "。</span><span class="sxs-lookup"><span data-stu-id="885e9-135">To reprovision or manage your ServiceNow integration in the Microsoft 365 security center, select **Manage ServiceNow configuration** on either of the cards.</span></span> <span data-ttu-id="885e9-136">在此处，删除当前的 ServiceNow 连接并自定义票证状态名称。</span><span class="sxs-lookup"><span data-stu-id="885e9-136">From there, remove the current ServiceNow connection and customize ticket state names.</span></span>

<span data-ttu-id="885e9-137">借助 Microsoft 365 security center 中显示的 ServiceNow 票证，你的任务可以在某个位置进行跟踪，并在你的其他安全仪表板项目旁边进行操作。</span><span class="sxs-lookup"><span data-stu-id="885e9-137">With ServiceNow tickets visible in the Microsoft 365 security center, your tasks live in a place where they can be tracked and acted upon alongside your other security dashboard items.</span></span>

## <a name="resources"></a><span data-ttu-id="885e9-138">资源</span><span class="sxs-lookup"><span data-stu-id="885e9-138">Resources</span></span>

- [<span data-ttu-id="885e9-139">了解先决条件、数据交换和疑难解答</span><span class="sxs-lookup"><span data-stu-id="885e9-139">Learn about prerequisites, data exchange, and troubleshooting</span></span>](tickets.md)
- [<span data-ttu-id="885e9-140">Microsoft 安全功能分数</span><span class="sxs-lookup"><span data-stu-id="885e9-140">Microsoft Secure Score</span></span>](microsoft-secure-score.md)