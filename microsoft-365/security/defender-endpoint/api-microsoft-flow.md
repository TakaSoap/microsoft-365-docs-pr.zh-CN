---
title: Microsoft Defender for Endpoint Flow 连接器
ms.reviewer: ''
description: 使用 Microsoft Defender for Endpoint Flow 连接器实现安全性自动化，并创建在租户上出现新警报时触发的流。
keywords: 流， 受支持的 api， api， Microsoft 流， 查询， 自动化
search.product: eADQiWindows 10XVcnh
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
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 33a7c7b1907ac761dfdde43a70bfb8f515235150
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/21/2021
ms.locfileid: "51929295"
---
# <a name="microsoft-power-automate-formerly-microsoft-flow-and-azure-functions"></a><span data-ttu-id="2ca09-104">Microsoft Power Automate (Microsoft Flow) 和 Azure Functions</span><span class="sxs-lookup"><span data-stu-id="2ca09-104">Microsoft Power Automate (formerly Microsoft Flow), and Azure Functions</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="2ca09-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="2ca09-105">**Applies to:**</span></span>
- [<span data-ttu-id="2ca09-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="2ca09-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="2ca09-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2ca09-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


- <span data-ttu-id="2ca09-108">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="2ca09-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="2ca09-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="2ca09-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

<span data-ttu-id="2ca09-110">自动执行安全过程是每个新式安全操作中心的标准要求。</span><span class="sxs-lookup"><span data-stu-id="2ca09-110">Automating security procedures is a standard requirement for every modern Security Operations Center.</span></span> <span data-ttu-id="2ca09-111">缺少专业网络防御者会强制 SOC 以最有效的方式工作，自动化是一项必须完成的工作。</span><span class="sxs-lookup"><span data-stu-id="2ca09-111">The lack of professional cyber defenders forces SOC to work in the most efficient way and automation is a must.</span></span> <span data-ttu-id="2ca09-112">Microsoft Power Automate 支持专为这一点构建的不同连接器。</span><span class="sxs-lookup"><span data-stu-id="2ca09-112">Microsoft Power Automate supports different connectors that were built exactly for that.</span></span> <span data-ttu-id="2ca09-113">您可以几分钟内生成端到端过程自动化。</span><span class="sxs-lookup"><span data-stu-id="2ca09-113">You can build an end-to-end procedure automation within a few minutes.</span></span>

<span data-ttu-id="2ca09-114">Microsoft Defender API 具有具有许多功能的官方流连接器。</span><span class="sxs-lookup"><span data-stu-id="2ca09-114">Microsoft Defender API has an official Flow Connector with many capabilities.</span></span>

![编辑凭据的图像1](images/api-flow-0.png)

> [!NOTE]
> <span data-ttu-id="2ca09-116">有关高级连接器许可先决条件的更多详细信息，请参阅 Premium [Connectors 的许可](https://docs.microsoft.com/power-automate/triggers-introduction#licensing-for-premium-connectors)。</span><span class="sxs-lookup"><span data-stu-id="2ca09-116">For more details about premium connectors licensing prerequisites, see [Licensing for premium connectors](https://docs.microsoft.com/power-automate/triggers-introduction#licensing-for-premium-connectors).</span></span>


## <a name="usage-example"></a><span data-ttu-id="2ca09-117">用法示例</span><span class="sxs-lookup"><span data-stu-id="2ca09-117">Usage example</span></span>

<span data-ttu-id="2ca09-118">以下示例演示了如何创建在租户上出现新警报时触发的 Flow。</span><span class="sxs-lookup"><span data-stu-id="2ca09-118">The following example demonstrates how to create a Flow that is triggered any time a new Alert occurs on your tenant.</span></span>

1. <span data-ttu-id="2ca09-119">登录到 [Microsoft Power Automate](https://flow.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="2ca09-119">Log in to [Microsoft Power Automate](https://flow.microsoft.com).</span></span>

2. <span data-ttu-id="2ca09-120">Go to **My flows**  >  **New**  >  **Automated-from blank**.</span><span class="sxs-lookup"><span data-stu-id="2ca09-120">Go to **My flows** > **New** > **Automated-from blank**.</span></span>

    ![编辑凭据的图像2](images/api-flow-1.png)

3. <span data-ttu-id="2ca09-122">选择 Flow 的名称，搜索"Microsoft Defender ATP 触发器"作为触发器，然后选择新的警报触发器。</span><span class="sxs-lookup"><span data-stu-id="2ca09-122">Choose a name for your Flow, search for "Microsoft Defender ATP Triggers" as the trigger, and then select the new Alerts trigger.</span></span>

    ![编辑凭据的图像3](images/api-flow-2.png)

<span data-ttu-id="2ca09-124">现在，你拥有每次出现新警报时都会触发的 Flow。</span><span class="sxs-lookup"><span data-stu-id="2ca09-124">Now you have a Flow that is triggered every time a new Alert occurs.</span></span>

![编辑凭据的图像4](images/api-flow-3.png)

<span data-ttu-id="2ca09-126">现在只需选择下一步。</span><span class="sxs-lookup"><span data-stu-id="2ca09-126">All you need to do now is choose your next steps.</span></span>
<span data-ttu-id="2ca09-127">例如，如果警报的严重性为"高"，你可以隔离设备，并发送关于该设备的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="2ca09-127">For example, you can isolate the device if the Severity of the Alert is High and send an email about it.</span></span>
<span data-ttu-id="2ca09-128">警报触发器仅提供警报 ID 和计算机 ID。</span><span class="sxs-lookup"><span data-stu-id="2ca09-128">The Alert trigger provides only the Alert ID and the Machine ID.</span></span> <span data-ttu-id="2ca09-129">可以使用连接器展开这些实体。</span><span class="sxs-lookup"><span data-stu-id="2ca09-129">You can use the connector to expand these entities.</span></span>

### <a name="get-the-alert-entity-using-the-connector"></a><span data-ttu-id="2ca09-130">使用连接器获取 Alert 实体</span><span class="sxs-lookup"><span data-stu-id="2ca09-130">Get the Alert entity using the connector</span></span>

1. <span data-ttu-id="2ca09-131">选择 **"Microsoft Defender ATP"** 作为新步骤。</span><span class="sxs-lookup"><span data-stu-id="2ca09-131">Choose **Microsoft Defender ATP** for the new step.</span></span>

2. <span data-ttu-id="2ca09-132">选择 **警报 - 获取单个警报 API。**</span><span class="sxs-lookup"><span data-stu-id="2ca09-132">Choose **Alerts - Get single alert API**.</span></span>

3. <span data-ttu-id="2ca09-133">将上 **一步** 中的警报 ID 设置为 **Input**。</span><span class="sxs-lookup"><span data-stu-id="2ca09-133">Set the **Alert ID** from the last step as **Input**.</span></span>

    ![编辑凭据的图像5](images/api-flow-4.png)

### <a name="isolate-the-device-if-the-alerts-severity-is-high"></a><span data-ttu-id="2ca09-135">如果警报严重性为高，则隔离设备</span><span class="sxs-lookup"><span data-stu-id="2ca09-135">Isolate the device if the Alert's severity is High</span></span>

1. <span data-ttu-id="2ca09-136">将 **Condition** 添加为新步骤。</span><span class="sxs-lookup"><span data-stu-id="2ca09-136">Add **Condition** as a new step.</span></span>

2. <span data-ttu-id="2ca09-137">检查警报严重性 **是否等于"高** "。</span><span class="sxs-lookup"><span data-stu-id="2ca09-137">Check if the Alert severity **is equal to** High.</span></span>

   <span data-ttu-id="2ca09-138">如果是，请添加 **Microsoft Defender ATP - 使用** 计算机 ID 和注释隔离计算机操作。</span><span class="sxs-lookup"><span data-stu-id="2ca09-138">If yes, add the **Microsoft Defender ATP - Isolate machine** action with the Machine ID and a comment.</span></span>

    ![编辑凭据的图像6](images/api-flow-5.png)

3. <span data-ttu-id="2ca09-140">添加有关警报和隔离的电子邮件的新步骤。</span><span class="sxs-lookup"><span data-stu-id="2ca09-140">Add a new step for emailing about the Alert and the Isolation.</span></span> <span data-ttu-id="2ca09-141">有多个电子邮件连接器非常易于使用，例如 Outlook 或 Gmail。</span><span class="sxs-lookup"><span data-stu-id="2ca09-141">There are multiple email connectors that are very easy to use, such as Outlook or Gmail.</span></span>

4. <span data-ttu-id="2ca09-142">保存流。</span><span class="sxs-lookup"><span data-stu-id="2ca09-142">Save your flow.</span></span>

<span data-ttu-id="2ca09-143">还可以创建运行 **高级** 搜寻查询等的计划流！</span><span class="sxs-lookup"><span data-stu-id="2ca09-143">You can also create a **scheduled** flow that runs Advanced Hunting queries and much more!</span></span>

## <a name="related-topic"></a><span data-ttu-id="2ca09-144">相关主题</span><span class="sxs-lookup"><span data-stu-id="2ca09-144">Related topic</span></span>
- [<span data-ttu-id="2ca09-145">适用于终结点的 Microsoft Defender API</span><span class="sxs-lookup"><span data-stu-id="2ca09-145">Microsoft Defender for Endpoint APIs</span></span>](apis-intro.md)
