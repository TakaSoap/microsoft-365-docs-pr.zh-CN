---
title: 创建用于攻击模拟培训的有效负载
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
description: 了解如何在 Microsoft Defender for Office 365 中创建自定义的攻击负载以实现攻击模拟培训。
ms.openlocfilehash: ffb5397d9b39a35b4cb8bd0fdb3301cd156896e1
ms.sourcegitcommit: dab50e1cc5bba920720b80033c93457f5ca1c330
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2020
ms.locfileid: "48944461"
---
# <a name="create-a-custom-payload-for-attack-simulation-training"></a><span data-ttu-id="52a0f-103">为攻击模拟培训创建自定义有效负载</span><span class="sxs-lookup"><span data-stu-id="52a0f-103">Create a custom payload for Attack simulation training</span></span>

<span data-ttu-id="52a0f-104">Microsoft 为各种社会工程技术提供可靠的有效负载目录，以与您的攻击模拟培训进行配对。</span><span class="sxs-lookup"><span data-stu-id="52a0f-104">Microsoft offer a robust payload catalog for various social engineering techniques to pair with your attack simulation training.</span></span> <span data-ttu-id="52a0f-105">但是，您可能希望创建可更好地为组织工作的自定义负载。</span><span class="sxs-lookup"><span data-stu-id="52a0f-105">However, you might want to create custom payloads that will work better for your organization.</span></span> <span data-ttu-id="52a0f-106">下面介绍如何通过 Microsoft Defender for Office 365 在攻击模拟培训中创建有效负载。</span><span class="sxs-lookup"><span data-stu-id="52a0f-106">The following describes how to create a payload in attack simulation training through Microsoft Defender for Office 365.</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="52a0f-107">您可以通过单击 " [专用 **负载** " 选项卡](https://security.microsoft.com/attacksimulator?viewid=payload)或在 [模拟创建向导](attack-simulation-training.md#selecting-a-payload)中的 " **创建有效负载** " 来创建有效负载。</span><span class="sxs-lookup"><span data-stu-id="52a0f-107">You can create a payload by clicking on **Create a payload** in either the [dedicated **Payloads** tab](https://security.microsoft.com/attacksimulator?viewid=payload) or within the [simulation creation wizard](attack-simulation-training.md#selecting-a-payload).</span></span>

<span data-ttu-id="52a0f-108">向导中的第一步将选择有效负载类型。</span><span class="sxs-lookup"><span data-stu-id="52a0f-108">The first step in the wizard will have you select a payload type.</span></span> <span data-ttu-id="52a0f-109">**目前仅提供电子邮件** 。</span><span class="sxs-lookup"><span data-stu-id="52a0f-109">**Currently only email is available**.</span></span>

<span data-ttu-id="52a0f-110">接下来，选择一种关联的技术。</span><span class="sxs-lookup"><span data-stu-id="52a0f-110">Next, select an associated technique.</span></span> <span data-ttu-id="52a0f-111">有关 [选择社会工程技术](attack-simulation-training.md#selecting-a-social-engineering-technique)的技巧，请参阅更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="52a0f-111">See more details on techniques at [Selecting a social engineering technique](attack-simulation-training.md#selecting-a-social-engineering-technique).</span></span>

<span data-ttu-id="52a0f-112">在下一步中，为你的有效负载命名。</span><span class="sxs-lookup"><span data-stu-id="52a0f-112">In the next step name your payload.</span></span> <span data-ttu-id="52a0f-113">（可选）您可以为其提供说明。</span><span class="sxs-lookup"><span data-stu-id="52a0f-113">Optionally, you can give it a description.</span></span>

## <a name="configure-payload"></a><span data-ttu-id="52a0f-114">配置有效负载</span><span class="sxs-lookup"><span data-stu-id="52a0f-114">Configure payload</span></span>

<span data-ttu-id="52a0f-115">现在是时候生成有效负载了。</span><span class="sxs-lookup"><span data-stu-id="52a0f-115">Now it's time to build your payload.</span></span> <span data-ttu-id="52a0f-116">在 " **发件人详细信息** " 部分中输入发件人的姓名、电子邮件和电子邮件的主题。</span><span class="sxs-lookup"><span data-stu-id="52a0f-116">Input the sender's name, email and the email's subject in the **Sender details** section.</span></span> <span data-ttu-id="52a0f-117">从提供的列表中选择一个仿冒 URL。</span><span class="sxs-lookup"><span data-stu-id="52a0f-117">Pick a phishing URL from the the provided list.</span></span> <span data-ttu-id="52a0f-118">此 URL 稍后将嵌入到邮件正文中。</span><span class="sxs-lookup"><span data-stu-id="52a0f-118">This URL will later be embedded into the body of the message.</span></span>

> [!TIP]
> <span data-ttu-id="52a0f-119">您可以为有效负载的发件人选择内部电子邮件，这将使有效负载显示为来自公司的其他员工。</span><span class="sxs-lookup"><span data-stu-id="52a0f-119">You can choose an internal email for your payload's sender, which will make the payload appear as coming from another employee of the company.</span></span> <span data-ttu-id="52a0f-120">这将提高对有效负载的敏感程度，并帮助员工对内部威胁的风险进行培训。</span><span class="sxs-lookup"><span data-stu-id="52a0f-120">This will increase susceptibility to the payload and will help educate employees on the risk of internal threats.</span></span>

<span data-ttu-id="52a0f-121">可用于创建有效负载的 rtf 文本编辑器。</span><span class="sxs-lookup"><span data-stu-id="52a0f-121">A rich text editor is available to create your payload.</span></span> <span data-ttu-id="52a0f-122">您还可以导入事先创建的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="52a0f-122">You can also import an email you've created beforehand.</span></span> <span data-ttu-id="52a0f-123">在构造电子邮件的正文时，利用 **动态标记** 将电子邮件个性化到目标中。</span><span class="sxs-lookup"><span data-stu-id="52a0f-123">As you structure the body of the email, take advantage of the **dynamic tags** to personalize the email to your targets.</span></span> <span data-ttu-id="52a0f-124">单击 " **仿冒链接** "，将之前选择的仿冒 URL 添加到电子邮件正文中。</span><span class="sxs-lookup"><span data-stu-id="52a0f-124">Click on **Phishing link** to add the previously selected phishing URL into the body of the email.</span></span>

![在 Microsoft Defender for Office 365 的有效负载创建中突出显示的仿冒链接和动态标记](../../media/attack-sim-preview-payload-email-body.png)

> [!TIP]
> <span data-ttu-id="52a0f-126">若要节省时间，请切换到 **替换电子邮件中包含仿冒链接的所有链接** 的选项。</span><span class="sxs-lookup"><span data-stu-id="52a0f-126">To save yourself some time, toggle on the option to **replace all links in the email message with the phishing link**.</span></span>

<span data-ttu-id="52a0f-127">根据需要构建完有效负载后，单击 " **下一步** "。</span><span class="sxs-lookup"><span data-stu-id="52a0f-127">Once you're done building the payload to your liking, click **Next**.</span></span>

## <a name="adding-indicators"></a><span data-ttu-id="52a0f-128">添加指示器</span><span class="sxs-lookup"><span data-stu-id="52a0f-128">Adding indicators</span></span>

<span data-ttu-id="52a0f-129">指示器将帮助员工通过攻击模拟了解他们可以在未来的攻击中查找的线索。</span><span class="sxs-lookup"><span data-stu-id="52a0f-129">Indicators will help employees going through the attack simulation understand clue they can look for in future attacks.</span></span> <span data-ttu-id="52a0f-130">若要开始，请单击 " **添加指示器** "。</span><span class="sxs-lookup"><span data-stu-id="52a0f-130">To start, click **Add indicator**.</span></span>

<span data-ttu-id="52a0f-131">从下拉列表中选择要使用的指示器。</span><span class="sxs-lookup"><span data-stu-id="52a0f-131">Select an indicator you'd like to use from the drop-down list.</span></span> <span data-ttu-id="52a0f-132">此列表为 curated，包含出现在网络钓鱼电子邮件中的最常见线索。</span><span class="sxs-lookup"><span data-stu-id="52a0f-132">This list is curated to contain the most common clues that appear in phishing email messages.</span></span> <span data-ttu-id="52a0f-133">选择后，请确保指示器位置已设置为 **来自电子邮件的正文** ，然后单击 " **选择文本** "。</span><span class="sxs-lookup"><span data-stu-id="52a0f-133">Once selected, make sure the indicator placement is set to **From the body of the email** and click on **Select text**.</span></span> <span data-ttu-id="52a0f-134">突出显示此指示器显示的有效部分，然后单击 " **选择** "。</span><span class="sxs-lookup"><span data-stu-id="52a0f-134">Highlight the portion of your payload where this indicator appears and click **Select**.</span></span>

![要添加到攻击模拟培训中的指标的邮件正文中突出显示的文本](../../media/attack-sim-preview-select-text.png)

<span data-ttu-id="52a0f-136">添加用于描述指示器的自定义说明，并在指示器预览框架内单击以查看指示器预览。</span><span class="sxs-lookup"><span data-stu-id="52a0f-136">Add a custom description to describe the indicator and click within the indicator preview frame to see a preview of your indicator.</span></span> <span data-ttu-id="52a0f-137">完成后，单击 " **添加** "。</span><span class="sxs-lookup"><span data-stu-id="52a0f-137">Once done, click **Add**.</span></span> <span data-ttu-id="52a0f-138">重复这些步骤，直到您在有效负载中覆盖了所有指示器。</span><span class="sxs-lookup"><span data-stu-id="52a0f-138">Repeat these steps until you've covered all indicators in your payload.</span></span>

## <a name="review-payload"></a><span data-ttu-id="52a0f-139">查看有效负载</span><span class="sxs-lookup"><span data-stu-id="52a0f-139">Review payload</span></span>

<span data-ttu-id="52a0f-140">你已经完成了你的有效负载的构建。</span><span class="sxs-lookup"><span data-stu-id="52a0f-140">You're done building your payload.</span></span> <span data-ttu-id="52a0f-141">现在是时候查看详细信息并查看有效负载的预览。</span><span class="sxs-lookup"><span data-stu-id="52a0f-141">Now it's time to review the details and see a preview of your payload.</span></span> <span data-ttu-id="52a0f-142">预览将包含您创建的所有指示器。</span><span class="sxs-lookup"><span data-stu-id="52a0f-142">The preview will include all indicators you've created.</span></span> <span data-ttu-id="52a0f-143">您可以从此步骤中编辑有效负载的每个部分。</span><span class="sxs-lookup"><span data-stu-id="52a0f-143">You can edit each part of the payload from this step.</span></span> <span data-ttu-id="52a0f-144">满足后， **提交** 有效负载。</span><span class="sxs-lookup"><span data-stu-id="52a0f-144">Once satisfied, **Submit** your payload.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="52a0f-145">你创建的负载将把 **租户** 设置为其源。</span><span class="sxs-lookup"><span data-stu-id="52a0f-145">Payloads you've created will have **Tenant** set as their source.</span></span> <span data-ttu-id="52a0f-146">在选择有效负载时，请确保未筛选出 **租户** 。</span><span class="sxs-lookup"><span data-stu-id="52a0f-146">When selecting payloads, make sure you don't have **Tenant** filtered out.</span></span>