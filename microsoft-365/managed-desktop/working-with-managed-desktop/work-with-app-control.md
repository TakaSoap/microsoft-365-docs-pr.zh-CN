---
title: 使用应用程序控制
description: ''
keywords: Microsoft 托管桌面, Microsoft 365, 服务, 文档
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
manager: laurawi
audience: ITpro
ms.topic: article
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 31cc897fe28f557a65cba9c99e5dcecbf7c2b0e5
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50917636"
---
# <a name="work-with-app-control"></a><span data-ttu-id="aa810-103">使用应用程序控制</span><span class="sxs-lookup"><span data-stu-id="aa810-103">Work with app control</span></span>

<span data-ttu-id="aa810-104">在环境中部署应用控制后，你和Microsoft 托管桌面操作将持续承担责任。</span><span class="sxs-lookup"><span data-stu-id="aa810-104">Once app control has been deployed in your environment, both you and Microsoft Managed Desktop Operations have ongoing responsibilities.</span></span> <span data-ttu-id="aa810-105">例如，你可能想要在环境中添加新应用，或者添加 (或删除) 签名者。</span><span class="sxs-lookup"><span data-stu-id="aa810-105">For example, you might want to add a new app in the environment or add (or remove) a trusted signer.</span></span> <span data-ttu-id="aa810-106">为了提高安全性，所有应用都应先进行代码签名，然后再将其发布给用户。</span><span class="sxs-lookup"><span data-stu-id="aa810-106">To improve security, all apps should be code-signed before you release them to users.</span></span> <span data-ttu-id="aa810-107">应用的发布者详细信息包括有关签名者的信息。</span><span class="sxs-lookup"><span data-stu-id="aa810-107">An app's publisher details includes information about the signer.</span></span>


## <a name="add-a-new-app"></a><span data-ttu-id="aa810-108">添加新应用</span><span class="sxs-lookup"><span data-stu-id="aa810-108">Add a new app</span></span>

<span data-ttu-id="aa810-109">若要添加新应用，请按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="aa810-109">To add a new app, follow these steps:</span></span>

1. <span data-ttu-id="aa810-110">将应用添加到[Microsoft Intune](/mem/intune/apps/apps-win32-app-management)。</span><span class="sxs-lookup"><span data-stu-id="aa810-110">Add the app to [Microsoft Intune](/mem/intune/apps/apps-win32-app-management).</span></span>
2. <span data-ttu-id="aa810-111">将应用部署到测试圈中的任意设备。</span><span class="sxs-lookup"><span data-stu-id="aa810-111">Deploy the app to any device in the Test ring.</span></span> 
3. <span data-ttu-id="aa810-112">根据标准业务流程测试应用。</span><span class="sxs-lookup"><span data-stu-id="aa810-112">Test your app according to your standard business processes.</span></span> 
4. <span data-ttu-id="aa810-113">检查 Application **and Services Logs\Microsoft\Windows\AppLocker** 下的事件查看器，查找任何 **8003** 或 **8006** 事件。</span><span class="sxs-lookup"><span data-stu-id="aa810-113">Check Event Viewer under **Application and Services Logs\Microsoft\Windows\AppLocker**, looking for any **8003** or **8006** events.</span></span> <span data-ttu-id="aa810-114">这些事件指示应用将被阻止。</span><span class="sxs-lookup"><span data-stu-id="aa810-114">These events indicate that the app would be blocked.</span></span> <span data-ttu-id="aa810-115">有关所有应用保险箱事件及其含义的信息，请参阅将事件查看器与 [AppLocker 一同使用](/windows/security/threat-protection/windows-defender-application-control/applocker/using-event-viewer-with-applocker)。</span><span class="sxs-lookup"><span data-stu-id="aa810-115">For more information about all App Locker events and their meanings, see [Using Event Viewer with AppLocker](/windows/security/threat-protection/windows-defender-application-control/applocker/using-event-viewer-with-applocker).</span></span>
5. <span data-ttu-id="aa810-116">如果发现其中任何事件，请通过"操作"打开Microsoft 托管桌面请求。</span><span class="sxs-lookup"><span data-stu-id="aa810-116">If you find any of these events, open a signer request with Microsoft Managed Desktop Operations.</span></span>

## <a name="add-or-remove-a-trusted-signer"></a><span data-ttu-id="aa810-117">添加 (或删除) 签名者</span><span class="sxs-lookup"><span data-stu-id="aa810-117">Add (or remove) a trusted signer</span></span>

<span data-ttu-id="aa810-118">打开签名者请求时，需要先提供一些重要的发布者详细信息。</span><span class="sxs-lookup"><span data-stu-id="aa810-118">When you open a signer request, you'll need to provide some important publisher details first.</span></span> <span data-ttu-id="aa810-119">然后按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="aa810-119">Then follow these steps:</span></span>

1. <span data-ttu-id="aa810-120">[收集发布者详细信息](#gather-publisher-details)。</span><span class="sxs-lookup"><span data-stu-id="aa810-120">[Gather publisher details](#gather-publisher-details).</span></span>
2. <span data-ttu-id="aa810-121">使用 Microsoft 托管桌面 操作打开票证以请求签署人规则，并包括以下详细信息：</span><span class="sxs-lookup"><span data-stu-id="aa810-121">Open a ticket with Microsoft Managed Desktop Operations to request the signer rule and include following details:</span></span>  
    - <span data-ttu-id="aa810-122">应用程序名称</span><span class="sxs-lookup"><span data-stu-id="aa810-122">Application name</span></span> 
    - <span data-ttu-id="aa810-123">应用程序版本</span><span class="sxs-lookup"><span data-stu-id="aa810-123">Application version</span></span> 
    - <span data-ttu-id="aa810-124">说明</span><span class="sxs-lookup"><span data-stu-id="aa810-124">Description</span></span> 
    - <span data-ttu-id="aa810-125">更改类型 ("add"或"remove") </span><span class="sxs-lookup"><span data-stu-id="aa810-125">Change type ("add" or "remove")</span></span>  
    - <span data-ttu-id="aa810-126">Publisher详细信息 (例如："O= <publisher name> ，L= <location> ，S=State，C=Country") </span><span class="sxs-lookup"><span data-stu-id="aa810-126">Publisher details (for example: “O=<publisher name>,L=<location>,S=State,C=Country”)</span></span> 

> [!NOTE]
> <span data-ttu-id="aa810-127">若要删除对应用的信任，请按照相同步骤操作，但将 **"更改** 类型"设置为 *删除*。</span><span class="sxs-lookup"><span data-stu-id="aa810-127">To remove trust for an app, follow the same steps, but set **Change type** to *remove*.</span></span>

<span data-ttu-id="aa810-128">按照此计划，操作将逐步将策略部署到部署组：</span><span class="sxs-lookup"><span data-stu-id="aa810-128">Operations will progressively deploy policies to deployment groups following this schedule:</span></span>


|<span data-ttu-id="aa810-129">部署组</span><span class="sxs-lookup"><span data-stu-id="aa810-129">Deployment group</span></span>  |<span data-ttu-id="aa810-130">策略类型</span><span class="sxs-lookup"><span data-stu-id="aa810-130">Policy type</span></span>  |<span data-ttu-id="aa810-131">Timing</span><span class="sxs-lookup"><span data-stu-id="aa810-131">Timing</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="aa810-132">测试</span><span class="sxs-lookup"><span data-stu-id="aa810-132">Test</span></span>     |  <span data-ttu-id="aa810-133">Audit</span><span class="sxs-lookup"><span data-stu-id="aa810-133">Audit</span></span>       |  <span data-ttu-id="aa810-134">第 0 天</span><span class="sxs-lookup"><span data-stu-id="aa810-134">Day 0</span></span>       |
|<span data-ttu-id="aa810-135">First</span><span class="sxs-lookup"><span data-stu-id="aa810-135">First</span></span>     | <span data-ttu-id="aa810-136">Enforced</span><span class="sxs-lookup"><span data-stu-id="aa810-136">Enforced</span></span>        | <span data-ttu-id="aa810-137">第 1 天</span><span class="sxs-lookup"><span data-stu-id="aa810-137">Day 1</span></span>        |
|<span data-ttu-id="aa810-138">快速</span><span class="sxs-lookup"><span data-stu-id="aa810-138">Fast</span></span>     | <span data-ttu-id="aa810-139">Enforced</span><span class="sxs-lookup"><span data-stu-id="aa810-139">Enforced</span></span>        |  <span data-ttu-id="aa810-140">第 2 天</span><span class="sxs-lookup"><span data-stu-id="aa810-140">Day 2</span></span>       |
|<span data-ttu-id="aa810-141">宽泛</span><span class="sxs-lookup"><span data-stu-id="aa810-141">Broad</span></span>     | <span data-ttu-id="aa810-142">Enforced</span><span class="sxs-lookup"><span data-stu-id="aa810-142">Enforced</span></span>        |  <span data-ttu-id="aa810-143">第 3 天</span><span class="sxs-lookup"><span data-stu-id="aa810-143">Day 3</span></span>       |


<span data-ttu-id="aa810-144">可以在推出期间随时暂停或回滚部署。</span><span class="sxs-lookup"><span data-stu-id="aa810-144">You can pause or roll back the deployment at any time during the rollout.</span></span> <span data-ttu-id="aa810-145">为此，请通过 Operations 打开另一个服务请求。</span><span class="sxs-lookup"><span data-stu-id="aa810-145">To do this, open another service request with Operations.</span></span>

> [!NOTE]
> <span data-ttu-id="aa810-146">如果暂停签名者规则的发布，则必须回滚或完成该规则，然后才能开始其他推出。</span><span class="sxs-lookup"><span data-stu-id="aa810-146">If you pause the release of a signer rule, that rule must be either rolled back or completed before another rollout can start.</span></span>

## <a name="gather-publisher-details"></a><span data-ttu-id="aa810-147">收集发布者详细信息</span><span class="sxs-lookup"><span data-stu-id="aa810-147">Gather publisher details</span></span>

<span data-ttu-id="aa810-148">若要访问应用的发布者数据，请按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="aa810-148">To access the publisher data for an app, follow these steps:</span></span>

1. <span data-ttu-id="aa810-149">在Microsoft 托管桌面应用审核模式策略的测试圈中查找设备。</span><span class="sxs-lookup"><span data-stu-id="aa810-149">Find a Microsoft Managed Desktop device in the Test ring that has an Audit Mode policy applied.</span></span> 
2. <span data-ttu-id="aa810-150">尝试在设备上安装应用。</span><span class="sxs-lookup"><span data-stu-id="aa810-150">Attempt to install the app on the device.</span></span>
3. <span data-ttu-id="aa810-151">打开该设备上的事件查看器。</span><span class="sxs-lookup"><span data-stu-id="aa810-151">Open Event Viewer on that device.</span></span> 
4. <span data-ttu-id="aa810-152">在事件查看器中，导航到 **应用程序和服务日志\Microsoft\Windows**，然后选择 **AppLocker**。</span><span class="sxs-lookup"><span data-stu-id="aa810-152">In Event Viewer, navigate to **Application and Services Logs\Microsoft\Windows**, and then select **AppLocker**.</span></span> 
5. <span data-ttu-id="aa810-153">查找任何 **8003** 或 **8006** 事件，然后从事件复制信息：</span><span class="sxs-lookup"><span data-stu-id="aa810-153">Find any **8003** or **8006** event, and then copy information from the event:</span></span> 
    - <span data-ttu-id="aa810-154">应用程序名称</span><span class="sxs-lookup"><span data-stu-id="aa810-154">Application name</span></span> 
    - <span data-ttu-id="aa810-155">应用程序版本</span><span class="sxs-lookup"><span data-stu-id="aa810-155">Application version</span></span> 
    - <span data-ttu-id="aa810-156">说明</span><span class="sxs-lookup"><span data-stu-id="aa810-156">Description</span></span> 
    - <span data-ttu-id="aa810-157">Publisher详细信息 (例如："O= <publisher name> 、L= <location> 、S=State、C=Country") </span><span class="sxs-lookup"><span data-stu-id="aa810-157">Publisher details (for example: “O=<publisher name>, L=<location>, S=State, C=Country”)</span></span>