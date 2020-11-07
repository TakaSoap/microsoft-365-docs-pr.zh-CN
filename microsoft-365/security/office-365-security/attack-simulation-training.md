---
title: 模拟使用 Microsoft Defender 进行的网络钓鱼攻击
ms.author: daniha
author: danihalfin
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
description: 了解如何通过 Microsoft Defender for Office 365 中的攻击模拟培训来模拟网络钓鱼攻击并向用户提供网络仿冒防御的培训。
ms.openlocfilehash: b9b8a431fc28942f5e11bc7ce2e805ca082cf36b
ms.sourcegitcommit: dab50e1cc5bba920720b80033c93457f5ca1c330
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2020
ms.locfileid: "48944428"
---
# <a name="simulate-a-phishing-attack"></a><span data-ttu-id="cca48-103">模拟网络钓鱼攻击</span><span class="sxs-lookup"><span data-stu-id="cca48-103">Simulate a phishing attack</span></span>

<span data-ttu-id="cca48-104">通过 Microsoft Defender for Office 365 的攻击模拟器培训使您能够在组织中运行良性的网络攻击模拟，以测试安全策略和做法，并培训组织的员工以提高其知名度并降低对攻击的敏感程度。</span><span class="sxs-lookup"><span data-stu-id="cca48-104">Attack simulator training through Microsoft Defender for Office 365 lets you run benign cyber attack simulations on your organization to test your security policies and practices, as well as train the employees of your organization to increase their awareness and decrease their susceptibility to attacks.</span></span> <span data-ttu-id="cca48-105">下面将引导您使用攻击模拟器培训模拟网络钓鱼攻击。</span><span class="sxs-lookup"><span data-stu-id="cca48-105">The following walks you through simulating a phishing attack using attack simulator training.</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="cca48-106">若要启动模拟的网络钓鱼攻击，请导航到 [Microsoft 365 安全中心](https://security.microsoft.com/)。</span><span class="sxs-lookup"><span data-stu-id="cca48-106">To launch a simulated phishing attack, navigate to the [Microsoft 365 security center](https://security.microsoft.com/).</span></span> <span data-ttu-id="cca48-107">在 " **电子邮件 & 协作** " 下，单击 " **攻击模拟器** " 并切换到 " [**模拟**](https://security.microsoft.com/attacksimulator?viewid=simulations) " 选项卡。</span><span class="sxs-lookup"><span data-stu-id="cca48-107">Under **Email & collaboration** click on **Attack simulator** and switch to the [**Simulations**](https://security.microsoft.com/attacksimulator?viewid=simulations) tab.</span></span>

<span data-ttu-id="cca48-108">在 " **模拟** " 下 **，选择 + 启动模拟** 。</span><span class="sxs-lookup"><span data-stu-id="cca48-108">Under **Simulations** select **+ Launch a simulation**.</span></span>

![在 Microsoft 365 安全中心中启动模拟按钮](../../media/attack-sim-preview-launch.png)

> [!NOTE]
> <span data-ttu-id="cca48-110">在模拟创建过程中的任何时候，都可以保存和关闭，以便以后继续配置模拟。</span><span class="sxs-lookup"><span data-stu-id="cca48-110">At any point during simulation creation you can save and close to continue configuring the simulation at a later time.</span></span>

## <a name="selecting-a-social-engineering-technique"></a><span data-ttu-id="cca48-111">选择社会工程技术</span><span class="sxs-lookup"><span data-stu-id="cca48-111">Selecting a social engineering technique</span></span>

<span data-ttu-id="cca48-112">从4种不同的技术中进行选择，curated 从 [MITRE ATT&CK® framework](https://attack.mitre.org/techniques/enterprise/)。</span><span class="sxs-lookup"><span data-stu-id="cca48-112">Select from 4 different techniques, curated from the [MITRE ATT&CK® framework](https://attack.mitre.org/techniques/enterprise/).</span></span> <span data-ttu-id="cca48-113">不同的负载可用于不同的技术。</span><span class="sxs-lookup"><span data-stu-id="cca48-113">Different payloads are available for different techniques.</span></span>

- <span data-ttu-id="cca48-114">**凭据收集** 将尝试通过将用户带到已知的外观网站（包含输入框来提交用户名和密码）来收集员工的凭据。</span><span class="sxs-lookup"><span data-stu-id="cca48-114">**Credential harvest** attempts to collect credentials from employees by taking them to a well-known looking website with input boxes to submit a username and password.</span></span>
- <span data-ttu-id="cca48-115">**恶意软件附件** 将恶意附件添加到邮件中。</span><span class="sxs-lookup"><span data-stu-id="cca48-115">**Malware attachment** adds a malicious attachment to a message.</span></span> <span data-ttu-id="cca48-116">打开时，此附件将运行一些可帮助攻击者危害目标设备的任意代码。</span><span class="sxs-lookup"><span data-stu-id="cca48-116">When opened, this attachment will run some arbitrary code that will help the attacker compromise the target's device.</span></span>
- <span data-ttu-id="cca48-117">**附件中的链接** 是一种凭据搜集混合类型。</span><span class="sxs-lookup"><span data-stu-id="cca48-117">**Link in attachment** is a type of credential harvest hybrid.</span></span> <span data-ttu-id="cca48-118">攻击者将 URL 插入到电子邮件附件中。</span><span class="sxs-lookup"><span data-stu-id="cca48-118">An attacker inserts a URL into an email attachment.</span></span> <span data-ttu-id="cca48-119">附件中的 URL 遵循与凭据搜集相同的技术。</span><span class="sxs-lookup"><span data-stu-id="cca48-119">The URL within the attachment follows the same technique as credential harvest.</span></span>
- <span data-ttu-id="cca48-120">**链接到恶意软件** 将通过在已知文件共享网站上托管的文件运行某些任意代码。</span><span class="sxs-lookup"><span data-stu-id="cca48-120">**Link to malware** will run some arbitrary code from a file hosted on a well-known file-sharing site.</span></span> <span data-ttu-id="cca48-121">指向此恶意文件的链接将添加到发送给目标的邮件中，单击它将运行该文件，并帮助攻击者危害目标设备。</span><span class="sxs-lookup"><span data-stu-id="cca48-121">A link to this malicious file is added to the message sent to the target and clicking it will run the file and help the attacker compromise the target's device.</span></span>

> [!TIP]
> <span data-ttu-id="cca48-122">单击每种技术的说明中的 " **查看详细信息** "，将显示有关该技术的详细信息以及该技术的模拟步骤。</span><span class="sxs-lookup"><span data-stu-id="cca48-122">Clicking on **View details** within the description of each technique will display further information about the technique as well as the simulation steps for that technique.</span></span>
>
> ![Microsoft 365 安全中心内的凭据收集攻击模拟培训的模拟步骤](../../media/attack-sim-preview-sim-steps.png)

<span data-ttu-id="cca48-124">选择该技术并单击 " **下一步** " 后，会为模拟提供一个名称和（可选）说明。</span><span class="sxs-lookup"><span data-stu-id="cca48-124">Once you've selected the technique and clicked on **Next** give your simulation a name and optionally a description.</span></span>

## <a name="selecting-a-payload"></a><span data-ttu-id="cca48-125">选择有效负载</span><span class="sxs-lookup"><span data-stu-id="cca48-125">Selecting a payload</span></span>

<span data-ttu-id="cca48-126">接下来，你需要从预先存在的有效负载目录中选择有效负载。</span><span class="sxs-lookup"><span data-stu-id="cca48-126">Next, you'll need to either select a payload from the pre-existing payload catalog.</span></span>

<span data-ttu-id="cca48-127">负载具有许多可帮助您选择的数据点：</span><span class="sxs-lookup"><span data-stu-id="cca48-127">Payloads have a number of data points to help you choose:</span></span>

- <span data-ttu-id="cca48-128">**单击 "汇率计数"** 多少人单击了此有效负载。</span><span class="sxs-lookup"><span data-stu-id="cca48-128">**Click rate** counts how many people clicked this payload.</span></span>
- <span data-ttu-id="cca48-129">**预测的泄露率** 预测基于此有效负载的人员在 Microsoft Defender for Office 365 客户之间的历史数据所占的百分比。</span><span class="sxs-lookup"><span data-stu-id="cca48-129">**Predicted compromise rate** predicts the percentage of people that will get compromised by this payload based on historic data for this payload across Microsoft Defender for Office 365 customers.</span></span>
- <span data-ttu-id="cca48-130">**模拟已启动** 计数此负载在其他模拟中使用的次数。</span><span class="sxs-lookup"><span data-stu-id="cca48-130">**Simulations launched** counts the number of times this payload was used in other simulations.</span></span>
- <span data-ttu-id="cca48-131">通过 **筛选器** 提供的 **复杂性** 是根据有效负载中的指示目标为攻击目标的指示器数计算得出的。</span><span class="sxs-lookup"><span data-stu-id="cca48-131">**Complexity** , available through **filters** , is calculated based on the number of indicators within the payload that clue targets in on it being an attack.</span></span> <span data-ttu-id="cca48-132">更多指标导致较低的复杂性。</span><span class="sxs-lookup"><span data-stu-id="cca48-132">More indicators lead to lower complexity.</span></span>
- <span data-ttu-id="cca48-133">**Source** ，通过 **筛选器** 提供，指示有效负载是否已在你的租户上创建，或者是否是 Microsoft 的已预先存在的有效负载目录 (全局) 的一部分。</span><span class="sxs-lookup"><span data-stu-id="cca48-133">**Source** , available through **filters** , indicates whether the payload was created on your tenant or is a part of Microsoft's pre-existing payload catalog (global).</span></span>

![Microsoft 365 安全中心中的受攻击模拟培训中选定的有效负载](../../media/attack-sim-preview-select-payload.png)

<span data-ttu-id="cca48-135">从列表中选择有效负载，以查看有效负载的预览，并提供有关它的其他信息。</span><span class="sxs-lookup"><span data-stu-id="cca48-135">Select a payload from the list to see a preview of the payload with additional information about it.</span></span>

<span data-ttu-id="cca48-136">如果您想要创建自己的有效负载，请参阅 [创建攻击模拟培训的有效负载](attack-simulation-training-payloads.md)。</span><span class="sxs-lookup"><span data-stu-id="cca48-136">If you'd like to create your own payload, read [create a payload for attack simulation training](attack-simulation-training-payloads.md).</span></span>

## <a name="audience-targeting"></a><span data-ttu-id="cca48-137">访问群体设定</span><span class="sxs-lookup"><span data-stu-id="cca48-137">Audience targeting</span></span>

<span data-ttu-id="cca48-138">现在是时候选择此模拟受众了。</span><span class="sxs-lookup"><span data-stu-id="cca48-138">Now it's time to select this simulation's audience.</span></span> <span data-ttu-id="cca48-139">您可以选择 **包括组织中的所有用户** 或 **仅包括特定的用户和组** 。</span><span class="sxs-lookup"><span data-stu-id="cca48-139">You can choose to **include all users in your organization** or **include only specific users and groups**.</span></span> 

<span data-ttu-id="cca48-140">当您选择 **仅包括特定的用户和组** 时，可以执行以下操作之一：</span><span class="sxs-lookup"><span data-stu-id="cca48-140">When you choose to **include only specific users and groups** you can either:</span></span>

- <span data-ttu-id="cca48-141">**添加用户** ，使您可以利用对租户的搜索以及高级搜索和筛选功能，如将最近3个月内未被模拟的用户作为目标。</span><span class="sxs-lookup"><span data-stu-id="cca48-141">**Add users** , which allows you to leverage search for your tenant, as well as advanced search and filtering capabilities, like targeting users who haven't been targeted by a simulation in the last 3 months.</span></span>
  <span data-ttu-id="cca48-142">![Microsoft 365 安全中心的攻击模拟培训中的用户筛选](../../media/attack-sim-preview-user-targeting.png)</span><span class="sxs-lookup"><span data-stu-id="cca48-142">![User filtering in attack simulation training on Microsoft 365 security center](../../media/attack-sim-preview-user-targeting.png)</span></span>
- <span data-ttu-id="cca48-143">**从 CSV 导入** 允许您导入此模拟的一组预定义用户。</span><span class="sxs-lookup"><span data-stu-id="cca48-143">**Import from CSV** allows you to import a predefined set of users for this simulation.</span></span>

## <a name="assigning-training"></a><span data-ttu-id="cca48-144">分配培训</span><span class="sxs-lookup"><span data-stu-id="cca48-144">Assigning training</span></span>

<span data-ttu-id="cca48-145">我们建议您为每个模拟分配培训，因为参加培训的员工不易受到类似攻击。</span><span class="sxs-lookup"><span data-stu-id="cca48-145">We recommend that you assign training for each simulation, as employees who go through training are less susceptible to similar attacks.</span></span>

<span data-ttu-id="cca48-146">您可以选择为您分配培训，也可以选择 "培训课程和模块"。</span><span class="sxs-lookup"><span data-stu-id="cca48-146">You can either choose to have training assigned for you or select training courses and modules yourself.</span></span>

<span data-ttu-id="cca48-147">选择 **培训截止日期** 以确保员工及时完成其培训。</span><span class="sxs-lookup"><span data-stu-id="cca48-147">Select the **training due date** to make sure employees finish their training in a timely manner.</span></span>

> [!NOTE]
> <span data-ttu-id="cca48-148">如果选择自己选择课程和模块，您仍可以查看推荐的内容以及所有可用的课程和模块。</span><span class="sxs-lookup"><span data-stu-id="cca48-148">If you choose to select courses and modules yourself, you'll still be able to see the recommended content as well as all available courses and modules.</span></span>
>
> ![在 Microsoft 365 安全中心中的攻击模拟培训中添加建议的培训](../../media/attack-sim-preview-add-training.png)

<span data-ttu-id="cca48-150">在接下来的步骤中，您需要 **添加培训** （如果选择自己选择培训）并自定义 "培训" 登录页。</span><span class="sxs-lookup"><span data-stu-id="cca48-150">In the next steps you'll need to **Add trainings** if you opted to select it yourself, and customize your training landing page.</span></span> <span data-ttu-id="cca48-151">您将能够预览 "培训" 登陆页面，还可以更改其标题和正文。</span><span class="sxs-lookup"><span data-stu-id="cca48-151">You'll be able to preview the training landing page, as well as change the header and body of it.</span></span>

## <a name="launch-details-and-review"></a><span data-ttu-id="cca48-152">启动详细信息和评审</span><span class="sxs-lookup"><span data-stu-id="cca48-152">Launch details and review</span></span>

<span data-ttu-id="cca48-153">现在，所有内容都已配置，您可以立即启动此模拟，也可以将其安排在更晚的日期。</span><span class="sxs-lookup"><span data-stu-id="cca48-153">Now that everything is configured, you can launch this simulation immediately or schedule it for a later date.</span></span> <span data-ttu-id="cca48-154">您还需要选择何时结束此模拟。</span><span class="sxs-lookup"><span data-stu-id="cca48-154">You will also need to choose when to end this simulation.</span></span> <span data-ttu-id="cca48-155">我们将在所选时间之后停止捕获与此模拟的交互。</span><span class="sxs-lookup"><span data-stu-id="cca48-155">We will stop capturing interaction with this simulation past the selected time.</span></span> 

<span data-ttu-id="cca48-156">**启用区域感知时区传递** ，以便在员工的工作时间内根据区域将模拟的攻击邮件传递给员工。</span><span class="sxs-lookup"><span data-stu-id="cca48-156">**Enable region aware timezone delivery** to deliver simulated attack messages to your employees during their working hours based on their region.</span></span>

<span data-ttu-id="cca48-157">完成后，单击 " **下一步** " 并查看你的模拟的详细信息。</span><span class="sxs-lookup"><span data-stu-id="cca48-157">Once you're done, click on **Next** and review the details of your simulation.</span></span> <span data-ttu-id="cca48-158">单击任意要返回的部件上的 " **编辑** "，并更改需要更改的任何详细信息。</span><span class="sxs-lookup"><span data-stu-id="cca48-158">Click on **Edit** on any of the parts to go back and change any details that need changing.</span></span> <span data-ttu-id="cca48-159">完成后，单击 " **提交** "。</span><span class="sxs-lookup"><span data-stu-id="cca48-159">Once done, click **Submit**.</span></span>
