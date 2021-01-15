---
title: 使用 Microsoft Defender for Office 365 模拟网络钓鱼攻击
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: 管理员可以了解如何使用 Microsoft Defender for Office 365 中的攻击模拟培训模拟网络钓鱼攻击并培训其用户防钓鱼。
ms.openlocfilehash: dfdd3c93afb1b0fb30cc5b5affc040a369c29447
ms.sourcegitcommit: df58fd8ebe14ca98fc1be84dbfb9c29ef7ab1d62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/15/2021
ms.locfileid: "49870963"
---
# <a name="simulate-a-phishing-attack"></a><span data-ttu-id="d3604-103">模拟网络钓鱼攻击</span><span class="sxs-lookup"><span data-stu-id="d3604-103">Simulate a phishing attack</span></span>

<span data-ttu-id="d3604-104">Microsoft Defender for Office 365 中的攻击模拟培训允许你在组织中运行恶意网络攻击模拟，以测试安全策略和做法，并培训员工提高认知度并减少他们对攻击的敏感性。</span><span class="sxs-lookup"><span data-stu-id="d3604-104">Attack simulation training in Microsoft Defender for Office 365 lets you run benign cyberattack simulations on your organization to test your security policies and practices, as well as train your employees to increase their awareness and decrease their susceptibility to attacks.</span></span> <span data-ttu-id="d3604-105">本文将引导你完成使用攻击模拟培训创建模拟网络钓鱼攻击。</span><span class="sxs-lookup"><span data-stu-id="d3604-105">This article walks you through creating  a simulated phishing attack using attack simulation training.</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="d3604-106">有关攻击模拟培训的入门信息，请参阅 [使用攻击模拟培训入门](attack-simulation-training-get-started.md)。</span><span class="sxs-lookup"><span data-stu-id="d3604-106">For getting started information about Attack simulation training, see [Get started using Attack simulation training](attack-simulation-training-get-started.md).</span></span>

<span data-ttu-id="d3604-107">若要启动模拟网络钓鱼攻击，请打开 Microsoft [365](https://security.microsoft.com/)安全中心，转到"电子邮件&协作攻击 \> **模拟培训**"，然后切换到"[**模拟**](https://security.microsoft.com/attacksimulator?viewid=simulations)"选项卡。</span><span class="sxs-lookup"><span data-stu-id="d3604-107">To launch a simulated phishing attack, open the [Microsoft 365 security center](https://security.microsoft.com/), go to **Email & collaboration** \> **Attack simulation training**, and switch to the [**Simulations**](https://security.microsoft.com/attacksimulator?viewid=simulations) tab.</span></span>

<span data-ttu-id="d3604-108">在 **"模拟"** 下，选择 **" + 启动模拟"。**</span><span class="sxs-lookup"><span data-stu-id="d3604-108">Under **Simulations**, select **+ Launch a simulation**.</span></span>

![在 Microsoft 365 安全中心启动模拟按钮](../../media/attack-sim-preview-launch.png)

> [!NOTE]
> <span data-ttu-id="d3604-110">在模拟创建过程中的任何时间点，你都可以保存并关闭，以稍后继续配置模拟。</span><span class="sxs-lookup"><span data-stu-id="d3604-110">At any point during simulation creation, you can save and close to continue configuring the simulation at a later time.</span></span>

## <a name="selecting-a-social-engineering-technique"></a><span data-ttu-id="d3604-111">选择社交工程技术</span><span class="sxs-lookup"><span data-stu-id="d3604-111">Selecting a social engineering technique</span></span>

<span data-ttu-id="d3604-112">从 CK 的 4 种不同的技术中选择，这些技术 [由 MITRE ATT&设计®设计](https://attack.mitre.org/techniques/enterprise/)。</span><span class="sxs-lookup"><span data-stu-id="d3604-112">Select from 4 different techniques, curated from the [MITRE ATT&CK® framework](https://attack.mitre.org/techniques/enterprise/).</span></span> <span data-ttu-id="d3604-113">不同的有效负载可用于不同的技术：</span><span class="sxs-lookup"><span data-stu-id="d3604-113">Different payloads are available for different techniques:</span></span>

- <span data-ttu-id="d3604-114">**凭据收集** 尝试通过让用户到具有输入框的已知网站来提交用户名和密码来收集凭据。</span><span class="sxs-lookup"><span data-stu-id="d3604-114">**Credential harvest** attempts to collect credentials by taking users to a well-known looking website with input boxes to submit a username and password.</span></span>
- <span data-ttu-id="d3604-115">**恶意软件附件** 向邮件添加恶意附件。</span><span class="sxs-lookup"><span data-stu-id="d3604-115">**Malware attachment** adds a malicious attachment to a message.</span></span> <span data-ttu-id="d3604-116">当用户打开附件时，将运行任意代码，帮助攻击者破坏目标设备。</span><span class="sxs-lookup"><span data-stu-id="d3604-116">When the user opens the attachment, arbitrary code is run that will help the attacker compromise the target's device.</span></span>
- <span data-ttu-id="d3604-117">**附件中的链接** 是凭据获取混合的一种类型。</span><span class="sxs-lookup"><span data-stu-id="d3604-117">**Link in attachment** is a type of credential harvest hybrid.</span></span> <span data-ttu-id="d3604-118">攻击者将 URL 插入到电子邮件附件中。</span><span class="sxs-lookup"><span data-stu-id="d3604-118">An attacker inserts a URL into an email attachment.</span></span> <span data-ttu-id="d3604-119">附件中的 URL 遵循与凭据获取相同的技术。</span><span class="sxs-lookup"><span data-stu-id="d3604-119">The URL within the attachment follows the same technique as credential harvest.</span></span>
- <span data-ttu-id="d3604-120">**指向恶意软件** 的链接将运行一些来自已知文件共享服务上托管的文件的任意代码。</span><span class="sxs-lookup"><span data-stu-id="d3604-120">**Link to malware** will run some arbitrary code from a file hosted on a well-known file sharing service.</span></span> <span data-ttu-id="d3604-121">发送给用户的邮件将包含指向此恶意文件的链接。</span><span class="sxs-lookup"><span data-stu-id="d3604-121">The message sent to the user will contain a link to this malicious file.</span></span> <span data-ttu-id="d3604-122">打开文件并帮助攻击者破坏目标设备。</span><span class="sxs-lookup"><span data-stu-id="d3604-122">Opening the file and help the attacker compromise the target's device.</span></span>

> [!TIP]
> <span data-ttu-id="d3604-123">单击 **每种技术** 的说明中的"查看详细信息"将显示有关该技术的详细信息和模拟步骤。</span><span class="sxs-lookup"><span data-stu-id="d3604-123">Clicking on **View details** within the description of each technique will display further information and the simulation steps for the technique.</span></span>
>
> ![Microsoft 365 安全中心攻击模拟培训中凭据收集的模拟步骤](../../media/attack-sim-preview-sim-steps.png)

<span data-ttu-id="d3604-125">选择该技术并单击"下一步"后，为模拟指定名称和说明（可选）。</span><span class="sxs-lookup"><span data-stu-id="d3604-125">After you've selected the technique and clicked on **Next**, give your simulation a name and optionally a description.</span></span>

## <a name="selecting-a-payload"></a><span data-ttu-id="d3604-126">选择有效负载</span><span class="sxs-lookup"><span data-stu-id="d3604-126">Selecting a payload</span></span>

<span data-ttu-id="d3604-127">接下来，你需要从预先存在的有效负载目录中选择有效负载。</span><span class="sxs-lookup"><span data-stu-id="d3604-127">Next, you'll need to either select a payload from the pre-existing payload catalog.</span></span>

<span data-ttu-id="d3604-128">有效负载具有多个数据点，可帮助你选择：</span><span class="sxs-lookup"><span data-stu-id="d3604-128">Payloads have a number of data points to help you choose:</span></span>

- <span data-ttu-id="d3604-129">**单击率** 计算单击此负载的人数。</span><span class="sxs-lookup"><span data-stu-id="d3604-129">**Click rate** counts how many people clicked this payload.</span></span>
- <span data-ttu-id="d3604-130">**根据 Microsoft** Defender for Office 365 客户有效负载的历史数据，预测受此负载危害的百分比。</span><span class="sxs-lookup"><span data-stu-id="d3604-130">**Predicted compromise rate** predicts the percentage of people that will get compromised by this payload based on historical data for the payload across Microsoft Defender for Office 365 customers.</span></span>
- <span data-ttu-id="d3604-131">**模拟启动** 计算此有效负载在其他模拟中使用的次数。</span><span class="sxs-lookup"><span data-stu-id="d3604-131">**Simulations launched** counts the number of times this payload was used in other simulations.</span></span>
- <span data-ttu-id="d3604-132">**复杂性**（通过筛选器 **提供**）基于有效负载中的指示器数量计算，这些指示器可提示目标受到攻击。</span><span class="sxs-lookup"><span data-stu-id="d3604-132">**Complexity**, available through **filters**, is calculated based on the number of indicators within the payload that clue targets in on it being an attack.</span></span> <span data-ttu-id="d3604-133">指标越多，复杂性越低。</span><span class="sxs-lookup"><span data-stu-id="d3604-133">More indicators lead to lower complexity.</span></span>
- <span data-ttu-id="d3604-134">**源**（通过 **筛选器提供**）指示有效负载是在租户上创建的，还是 Microsoft 预先存在的有效负载目录的一 (全局) 。</span><span class="sxs-lookup"><span data-stu-id="d3604-134">**Source**, available through **filters**, indicates whether the payload was created on your tenant or is a part of Microsoft's pre-existing payload catalog (global).</span></span>

![Microsoft 365 安全中心攻击模拟培训内选定的有效负载](../../media/attack-sim-preview-select-payload.png)

<span data-ttu-id="d3604-136">从列表中选择一个有效负载，以查看有效负载的预览以及有关它的其他信息。</span><span class="sxs-lookup"><span data-stu-id="d3604-136">Select a payload from the list to see a preview of the payload with additional information about it.</span></span>

<span data-ttu-id="d3604-137">如果你想要创建自己的有效负载，请阅读为攻击 [模拟培训创建有效负载](attack-simulation-training-payloads.md)。</span><span class="sxs-lookup"><span data-stu-id="d3604-137">If you'd like to create your own payload, read [create a payload for attack simulation training](attack-simulation-training-payloads.md).</span></span>

## <a name="audience-targeting"></a><span data-ttu-id="d3604-138">访问群体设定</span><span class="sxs-lookup"><span data-stu-id="d3604-138">Audience targeting</span></span>

<span data-ttu-id="d3604-139">现在该选择此模拟的受众了。</span><span class="sxs-lookup"><span data-stu-id="d3604-139">Now it's time to select this simulation's audience.</span></span> <span data-ttu-id="d3604-140">可以选择包括 **组织中所有用户或** 仅 **包括特定用户和组**。</span><span class="sxs-lookup"><span data-stu-id="d3604-140">You can choose to **include all users in your organization** or **include only specific users and groups**.</span></span>

<span data-ttu-id="d3604-141">当你选择仅 **包含特定用户和组时** ，你可以：</span><span class="sxs-lookup"><span data-stu-id="d3604-141">When you choose to **include only specific users and groups** you can either:</span></span>

- <span data-ttu-id="d3604-142">**添加用户**，这允许你利用租户搜索以及高级搜索和筛选功能，例如面向过去 3 个月内未通过模拟定位的用户。</span><span class="sxs-lookup"><span data-stu-id="d3604-142">**Add users**, which allows you to leverage search for your tenant, as well as advanced search and filtering capabilities, like targeting users who haven't been targeted by a simulation in the last 3 months.</span></span>
  <span data-ttu-id="d3604-143">![Microsoft 365 安全中心攻击模拟培训中的用户筛选](../../media/attack-sim-preview-user-targeting.png)</span><span class="sxs-lookup"><span data-stu-id="d3604-143">![User filtering in attack simulation training on Microsoft 365 security center](../../media/attack-sim-preview-user-targeting.png)</span></span>
- <span data-ttu-id="d3604-144">**通过 CSV** 导入，可以导入此模拟的预定义用户集。</span><span class="sxs-lookup"><span data-stu-id="d3604-144">**Import from CSV** allows you to import a predefined set of users for this simulation.</span></span>

## <a name="assigning-training"></a><span data-ttu-id="d3604-145">分配培训</span><span class="sxs-lookup"><span data-stu-id="d3604-145">Assigning training</span></span>

<span data-ttu-id="d3604-146">我们建议你为每个模拟分配培训，因为经过培训的员工不太容易遭受类似攻击。</span><span class="sxs-lookup"><span data-stu-id="d3604-146">We recommend that you assign training for each simulation, as employees who go through training are less susceptible to similar attacks.</span></span>

<span data-ttu-id="d3604-147">可以选择为自己分配培训，也可以自己选择培训课程和模块。</span><span class="sxs-lookup"><span data-stu-id="d3604-147">You can either choose to have training assigned for you or select training courses and modules yourself.</span></span>

<span data-ttu-id="d3604-148">选择 **培训截止日期，** 确保员工及时完成培训。</span><span class="sxs-lookup"><span data-stu-id="d3604-148">Select the **training due date** to make sure employees finish their training in a timely manner.</span></span>

> [!NOTE]
> <span data-ttu-id="d3604-149">如果你选择自己选择课程和模块，你仍然可以看到推荐的内容以及所有可用的课程和模块。</span><span class="sxs-lookup"><span data-stu-id="d3604-149">If you choose to select courses and modules yourself, you'll still be able to see the recommended content as well as all available courses and modules.</span></span>
>
> ![在 Microsoft 365 安全中心的攻击模拟培训中添加建议的培训](../../media/attack-sim-preview-add-training.png)

<span data-ttu-id="d3604-151">在以下步骤中，如果选择自己选择培训，则需要添加培训，并自定义培训登陆页面。</span><span class="sxs-lookup"><span data-stu-id="d3604-151">In the next steps you'll need to **Add trainings** if you opted to select it yourself, and customize your training landing page.</span></span> <span data-ttu-id="d3604-152">你将能够预览培训登陆页面，并更改其标头和正文。</span><span class="sxs-lookup"><span data-stu-id="d3604-152">You'll be able to preview the training landing page, as well as change the header and body of it.</span></span>

## <a name="launch-details-and-review"></a><span data-ttu-id="d3604-153">启动详细信息和查看</span><span class="sxs-lookup"><span data-stu-id="d3604-153">Launch details and review</span></span>

<span data-ttu-id="d3604-154">现在，所有内容已配置完成，你可以立即启动此模拟或安排在以后日期进行。</span><span class="sxs-lookup"><span data-stu-id="d3604-154">Now that everything is configured, you can launch this simulation immediately or schedule it for a later date.</span></span> <span data-ttu-id="d3604-155">你还需要选择何时结束此模拟。</span><span class="sxs-lookup"><span data-stu-id="d3604-155">You will also need to choose when to end this simulation.</span></span> <span data-ttu-id="d3604-156">我们将停止捕获在选定时间后与此模拟的交互。</span><span class="sxs-lookup"><span data-stu-id="d3604-156">We will stop capturing interaction with this simulation past the selected time.</span></span>

<span data-ttu-id="d3604-157">**启用区域感知时区传递** ，以根据员工的区域在工作时间向员工传递模拟攻击消息。</span><span class="sxs-lookup"><span data-stu-id="d3604-157">**Enable region aware timezone delivery** to deliver simulated attack messages to your employees during their working hours based on their region.</span></span>

<span data-ttu-id="d3604-158">完成后，单击 **"下一** 步"并查看模拟的详细信息。</span><span class="sxs-lookup"><span data-stu-id="d3604-158">Once you're done, click on **Next** and review the details of your simulation.</span></span> <span data-ttu-id="d3604-159">单击 **任意** 部件的"编辑"可返回并更改任何需要更改的详细信息。</span><span class="sxs-lookup"><span data-stu-id="d3604-159">Click on **Edit** on any of the parts to go back and change any details that need changing.</span></span> <span data-ttu-id="d3604-160">完成后，单击"**提交"。**</span><span class="sxs-lookup"><span data-stu-id="d3604-160">Once done, click **Submit**.</span></span>
