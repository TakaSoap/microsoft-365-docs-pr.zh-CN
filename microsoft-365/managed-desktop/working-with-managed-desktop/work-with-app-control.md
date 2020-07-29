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
ms.openlocfilehash: 9efe6ba6704b0e1633973d157c38827221316bbd
ms.sourcegitcommit: 583fd1ac1f385c58b93bda648907a1bd8e0a1950
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/28/2020
ms.locfileid: "45430443"
---
# <a name="work-with-app-control"></a><span data-ttu-id="0e8b6-103">使用应用程序控制</span><span class="sxs-lookup"><span data-stu-id="0e8b6-103">Work with app control</span></span>

<span data-ttu-id="0e8b6-104">一旦在您的环境中部署了应用程序控制，您和 Microsoft 托管的桌面操作都将承担持续的责任。</span><span class="sxs-lookup"><span data-stu-id="0e8b6-104">Once app control has been deployed in your environment, both you and Microsoft Managed Desktop Operations have ongoing responsibilities.</span></span> <span data-ttu-id="0e8b6-105">例如，您可能希望在环境中添加新的应用程序，或添加（或删除）受信任的签名人。</span><span class="sxs-lookup"><span data-stu-id="0e8b6-105">For example, you might want to add a new app in the environment or add (or remove) a trusted signer.</span></span> <span data-ttu-id="0e8b6-106">为了提高安全性，在将所有应用发布到最终用户之前，应对其进行代码签名。</span><span class="sxs-lookup"><span data-stu-id="0e8b6-106">To improve security, all apps should be code-signed before you release them to end users.</span></span> <span data-ttu-id="0e8b6-107">应用的发布者详细信息包括有关签署人的信息。</span><span class="sxs-lookup"><span data-stu-id="0e8b6-107">An app's publisher details includes information about the signer.</span></span>


## <a name="add-a-new-app"></a><span data-ttu-id="0e8b6-108">添加新应用</span><span class="sxs-lookup"><span data-stu-id="0e8b6-108">Add a new app</span></span>

<span data-ttu-id="0e8b6-109">若要添加新应用程序，请按照下列步骤操作：</span><span class="sxs-lookup"><span data-stu-id="0e8b6-109">To add a new app, follow these steps:</span></span>

1. <span data-ttu-id="0e8b6-110">将应用程序添加到[Microsoft Intune](https://docs.microsoft.com/mem/intune/apps/apps-win32-app-management)。</span><span class="sxs-lookup"><span data-stu-id="0e8b6-110">Add the app to [Microsoft Intune](https://docs.microsoft.com/mem/intune/apps/apps-win32-app-management).</span></span>
2. <span data-ttu-id="0e8b6-111">将应用程序部署到测试环中的任何设备。</span><span class="sxs-lookup"><span data-stu-id="0e8b6-111">Deploy the app to any device in the Test ring.</span></span> 
3. <span data-ttu-id="0e8b6-112">根据您的标准业务流程测试您的应用程序。</span><span class="sxs-lookup"><span data-stu-id="0e8b6-112">Test your app according to your standard business processes.</span></span> 
4. <span data-ttu-id="0e8b6-113">检查 "**应用程序和服务" Logs\Microsoft\Windows\AppLocker**下的 "事件查看器"，查找任何**8003**或**8006**事件。</span><span class="sxs-lookup"><span data-stu-id="0e8b6-113">Check Event Viewer under **Application and Services Logs\Microsoft\Windows\AppLocker**, looking for any **8003** or **8006** events.</span></span> <span data-ttu-id="0e8b6-114">这些事件指示应用程序将被阻止。</span><span class="sxs-lookup"><span data-stu-id="0e8b6-114">These events indicate that the app would be blocked.</span></span> <span data-ttu-id="0e8b6-115">有关所有应用程序锁定程序事件及其含义的详细信息，请参阅将[事件查看器与 AppLocker 结合使用](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/using-event-viewer-with-applocker)。</span><span class="sxs-lookup"><span data-stu-id="0e8b6-115">For more information about all App Locker events and their meanings, see [Using Event Viewer with AppLocker](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/using-event-viewer-with-applocker).</span></span>
5. <span data-ttu-id="0e8b6-116">如果找到这些事件中的任何事件，请使用 Microsoft 托管桌面操作打开签名者请求。</span><span class="sxs-lookup"><span data-stu-id="0e8b6-116">If you find any of these events, open a signer request with Microsoft Managed Desktop Operations.</span></span>

## <a name="add-or-remove-a-trusted-signer"></a><span data-ttu-id="0e8b6-117">添加（或删除）受信任的签名人</span><span class="sxs-lookup"><span data-stu-id="0e8b6-117">Add (or remove) a trusted signer</span></span>

<span data-ttu-id="0e8b6-118">打开签名者请求时，需要先提供一些重要的发布者详细信息。</span><span class="sxs-lookup"><span data-stu-id="0e8b6-118">When you open a signer request, you'll need to provide some important publisher details first.</span></span> <span data-ttu-id="0e8b6-119">然后，按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="0e8b6-119">Then follow these steps:</span></span>

1. <span data-ttu-id="0e8b6-120">[收集发布者详细信息](#gather-publisher-details)。</span><span class="sxs-lookup"><span data-stu-id="0e8b6-120">[Gather publisher details](#gather-publisher-details).</span></span>
2. <span data-ttu-id="0e8b6-121">使用 Microsoft 托管桌面操作打开票证以请求签署人规则，并包括以下详细信息：</span><span class="sxs-lookup"><span data-stu-id="0e8b6-121">Open a ticket with Microsoft Managed Desktop Operations to request the signer rule and include following details:</span></span>  
    - <span data-ttu-id="0e8b6-122">应用程序名称</span><span class="sxs-lookup"><span data-stu-id="0e8b6-122">Application name</span></span> 
    - <span data-ttu-id="0e8b6-123">应用程序版本</span><span class="sxs-lookup"><span data-stu-id="0e8b6-123">Application version</span></span> 
    - <span data-ttu-id="0e8b6-124">说明</span><span class="sxs-lookup"><span data-stu-id="0e8b6-124">Description</span></span> 
    - <span data-ttu-id="0e8b6-125">更改类型（"添加" 或 "删除"）</span><span class="sxs-lookup"><span data-stu-id="0e8b6-125">Change type ("add" or "remove")</span></span>  
    - <span data-ttu-id="0e8b6-126">发布者详细信息（例如： "O = <publisher name> ，L = <location> ，S = State，C = 国家/地区"）</span><span class="sxs-lookup"><span data-stu-id="0e8b6-126">Publisher details (for example: “O=<publisher name>,L=<location>,S=State,C=Country”)</span></span> 

> [!NOTE]
> <span data-ttu-id="0e8b6-127">若要删除对应用的信任，请执行相同步骤，但将**更改类型**设置为 "*删除*"。</span><span class="sxs-lookup"><span data-stu-id="0e8b6-127">To remove trust for an app, follow the same steps, but set **Change type** to *remove*.</span></span>

<span data-ttu-id="0e8b6-128">按照此计划，操作将逐步将策略部署到部署组：</span><span class="sxs-lookup"><span data-stu-id="0e8b6-128">Operations will progressively deploy policies to deployment groups following this schedule:</span></span>


|<span data-ttu-id="0e8b6-129">部署组</span><span class="sxs-lookup"><span data-stu-id="0e8b6-129">Deployment group</span></span>  |<span data-ttu-id="0e8b6-130">策略类型</span><span class="sxs-lookup"><span data-stu-id="0e8b6-130">Policy type</span></span>  |<span data-ttu-id="0e8b6-131">Timing</span><span class="sxs-lookup"><span data-stu-id="0e8b6-131">Timing</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="0e8b6-132">测试</span><span class="sxs-lookup"><span data-stu-id="0e8b6-132">Test</span></span>     |  <span data-ttu-id="0e8b6-133">Audit</span><span class="sxs-lookup"><span data-stu-id="0e8b6-133">Audit</span></span>       |  <span data-ttu-id="0e8b6-134">第0天</span><span class="sxs-lookup"><span data-stu-id="0e8b6-134">Day 0</span></span>       |
|<span data-ttu-id="0e8b6-135">First</span><span class="sxs-lookup"><span data-stu-id="0e8b6-135">First</span></span>     | <span data-ttu-id="0e8b6-136">Enforced</span><span class="sxs-lookup"><span data-stu-id="0e8b6-136">Enforced</span></span>        | <span data-ttu-id="0e8b6-137">第 1 天</span><span class="sxs-lookup"><span data-stu-id="0e8b6-137">Day 1</span></span>        |
|<span data-ttu-id="0e8b6-138">快速</span><span class="sxs-lookup"><span data-stu-id="0e8b6-138">Fast</span></span>     | <span data-ttu-id="0e8b6-139">Enforced</span><span class="sxs-lookup"><span data-stu-id="0e8b6-139">Enforced</span></span>        |  <span data-ttu-id="0e8b6-140">第 2 天</span><span class="sxs-lookup"><span data-stu-id="0e8b6-140">Day 2</span></span>       |
|<span data-ttu-id="0e8b6-141">宽泛</span><span class="sxs-lookup"><span data-stu-id="0e8b6-141">Broad</span></span>     | <span data-ttu-id="0e8b6-142">Enforced</span><span class="sxs-lookup"><span data-stu-id="0e8b6-142">Enforced</span></span>        |  <span data-ttu-id="0e8b6-143">第 3 天</span><span class="sxs-lookup"><span data-stu-id="0e8b6-143">Day 3</span></span>       |


<span data-ttu-id="0e8b6-144">可以在首次部署过程中随时暂停或回滚部署。</span><span class="sxs-lookup"><span data-stu-id="0e8b6-144">You can pause or roll back the deployment at any time during the rollout.</span></span> <span data-ttu-id="0e8b6-145">为此，请打开另一个包含操作的服务请求。</span><span class="sxs-lookup"><span data-stu-id="0e8b6-145">To do this, open another service request with Operations.</span></span>

> [!NOTE]
> <span data-ttu-id="0e8b6-146">如果暂停签署人规则，则必须在另一个首展启动前回滚或完成该规则。</span><span class="sxs-lookup"><span data-stu-id="0e8b6-146">If you pause the release of a signer rule, that rule must be either rolled back or completed before another rollout can start.</span></span>

## <a name="gather-publisher-details"></a><span data-ttu-id="0e8b6-147">收集发布者详细信息</span><span class="sxs-lookup"><span data-stu-id="0e8b6-147">Gather publisher details</span></span>

<span data-ttu-id="0e8b6-148">若要访问应用程序的发布者数据，请按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="0e8b6-148">To access the publisher data for an app, follow these steps:</span></span>

1. <span data-ttu-id="0e8b6-149">在应用了审核模式策略的测试环中查找 Microsoft 托管桌面设备。</span><span class="sxs-lookup"><span data-stu-id="0e8b6-149">Find a Microsoft Managed Desktop device in the Test ring that has an Audit Mode policy applied.</span></span> 
2. <span data-ttu-id="0e8b6-150">尝试在设备上安装应用程序。</span><span class="sxs-lookup"><span data-stu-id="0e8b6-150">Attempt to install the app on the device.</span></span>
3. <span data-ttu-id="0e8b6-151">在该设备上打开事件查看器。</span><span class="sxs-lookup"><span data-stu-id="0e8b6-151">Open Event Viewer on that device.</span></span> 
4. <span data-ttu-id="0e8b6-152">在事件查看器中，导航到**Application And service Logs\Microsoft\Windows**，然后选择**AppLocker**。</span><span class="sxs-lookup"><span data-stu-id="0e8b6-152">In Event Viewer, navigate to **Application and Services Logs\Microsoft\Windows**, and then select **AppLocker**.</span></span> 
5. <span data-ttu-id="0e8b6-153">查找任何**8003**或**8006**事件，然后从事件中复制信息：</span><span class="sxs-lookup"><span data-stu-id="0e8b6-153">Find any **8003** or **8006** event, and then copy information from the event:</span></span> 
    - <span data-ttu-id="0e8b6-154">应用程序名称</span><span class="sxs-lookup"><span data-stu-id="0e8b6-154">Application name</span></span> 
    - <span data-ttu-id="0e8b6-155">应用程序版本</span><span class="sxs-lookup"><span data-stu-id="0e8b6-155">Application version</span></span> 
    - <span data-ttu-id="0e8b6-156">说明</span><span class="sxs-lookup"><span data-stu-id="0e8b6-156">Description</span></span> 
    - <span data-ttu-id="0e8b6-157">发布者详细信息（例如： "O = <publisher name> ，L = <location> ，S = State，C = 国家/地区"）</span><span class="sxs-lookup"><span data-stu-id="0e8b6-157">Publisher details (for example: “O=<publisher name>, L=<location>, S=State, C=Country”)</span></span> 
