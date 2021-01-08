---
title: 创建攻击模拟培训的有效负载
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
description: 管理员可以了解如何在 Microsoft Defender for Office 365 中为攻击模拟培训创建自定义负载。
ms.openlocfilehash: c48e6001e6d51c5621d54b3d4149d90b71724fad
ms.sourcegitcommit: ec293978e951b09903b79e6642aa587824935e0c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/07/2021
ms.locfileid: "49780244"
---
# <a name="create-a-custom-payload-for-attack-simulation-training"></a><span data-ttu-id="c4ce8-103">创建用于攻击模拟培训的自定义负载</span><span class="sxs-lookup"><span data-stu-id="c4ce8-103">Create a custom payload for Attack simulation training</span></span>

<span data-ttu-id="c4ce8-104">Microsoft 为各种社交工程技术提供了可靠的有效负载目录，以与攻击模拟培训配对。</span><span class="sxs-lookup"><span data-stu-id="c4ce8-104">Microsoft offers a robust payload catalog for various social engineering techniques to pair with your attack simulation training.</span></span> <span data-ttu-id="c4ce8-105">但是，你可能想要创建自定义有效负载，以更好地为组织工作。</span><span class="sxs-lookup"><span data-stu-id="c4ce8-105">However, you might want to create custom payloads that will work better for your organization.</span></span> <span data-ttu-id="c4ce8-106">本文介绍如何在 Microsoft Defender for Office 365 攻击模拟培训中创建有效负载。</span><span class="sxs-lookup"><span data-stu-id="c4ce8-106">This article describes how to create a payload in Attack simulation training in Microsoft Defender for Office 365.</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="c4ce8-107">可以通过单击专用"有效负载"选项卡或模拟创建向导中的"创建有效负载["来创建有效负载](attack-simulation-training.md#selecting-a-payload)。 [  ](https://security.microsoft.com/attacksimulator?viewid=payload)</span><span class="sxs-lookup"><span data-stu-id="c4ce8-107">You can create a payload by clicking on **Create a payload** in either the [dedicated **Payloads** tab](https://security.microsoft.com/attacksimulator?viewid=payload) or within the [simulation creation wizard](attack-simulation-training.md#selecting-a-payload).</span></span>

<span data-ttu-id="c4ce8-108">向导的第一步是选择有效负载类型。</span><span class="sxs-lookup"><span data-stu-id="c4ce8-108">The first step in the wizard will have you select a payload type.</span></span> <span data-ttu-id="c4ce8-109">**目前，只有电子邮件可用**。</span><span class="sxs-lookup"><span data-stu-id="c4ce8-109">**Currently, only email is available**.</span></span>

<span data-ttu-id="c4ce8-110">接下来，选择关联的技术。</span><span class="sxs-lookup"><span data-stu-id="c4ce8-110">Next, select an associated technique.</span></span> <span data-ttu-id="c4ce8-111">有关选择社交工程 [技术的方法的详细信息，请参阅](attack-simulation-training.md#selecting-a-social-engineering-technique)。</span><span class="sxs-lookup"><span data-stu-id="c4ce8-111">See more details on techniques at [Selecting a social engineering technique](attack-simulation-training.md#selecting-a-social-engineering-technique).</span></span>

<span data-ttu-id="c4ce8-112">在下一步中，命名有效负载。</span><span class="sxs-lookup"><span data-stu-id="c4ce8-112">In the next step name your payload.</span></span> <span data-ttu-id="c4ce8-113">（可选）你可以为它提供说明。</span><span class="sxs-lookup"><span data-stu-id="c4ce8-113">Optionally, you can give it a description.</span></span>

## <a name="configure-payload"></a><span data-ttu-id="c4ce8-114">配置有效负载</span><span class="sxs-lookup"><span data-stu-id="c4ce8-114">Configure payload</span></span>

<span data-ttu-id="c4ce8-115">现在，可以生成有效负载了。</span><span class="sxs-lookup"><span data-stu-id="c4ce8-115">Now it's time to build your payload.</span></span> <span data-ttu-id="c4ce8-116">在"发件人详细信息"部分输入发件人的姓名、电子邮件地址和 **电子邮件** 主题。</span><span class="sxs-lookup"><span data-stu-id="c4ce8-116">Input the sender's name, email address, and the email's subject in the **Sender details** section.</span></span> <span data-ttu-id="c4ce8-117">从提供的列表中选择网络钓鱼 URL。</span><span class="sxs-lookup"><span data-stu-id="c4ce8-117">Pick a phishing URL from the provided list.</span></span> <span data-ttu-id="c4ce8-118">此 URL 稍后将嵌入到邮件正文中。</span><span class="sxs-lookup"><span data-stu-id="c4ce8-118">This URL will later be embedded into the body of the message.</span></span>

> [!TIP]
> <span data-ttu-id="c4ce8-119">你可以选择有效负载的发件人的内部电子邮件，这会使有效负载显示为来自公司的另一名员工。</span><span class="sxs-lookup"><span data-stu-id="c4ce8-119">You can choose an internal email for your payload's sender, which will make the payload appear as coming from another employee of the company.</span></span> <span data-ttu-id="c4ce8-120">这将提高有效负载的易感知性，并帮助员工了解内部威胁的风险。</span><span class="sxs-lookup"><span data-stu-id="c4ce8-120">This will increase susceptibility to the payload and will help educate employees on the risk of internal threats.</span></span>

<span data-ttu-id="c4ce8-121">格式文本编辑器可用于创建有效负载。</span><span class="sxs-lookup"><span data-stu-id="c4ce8-121">A rich text editor is available to create your payload.</span></span> <span data-ttu-id="c4ce8-122">还可以导入预先创建的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="c4ce8-122">You can also import an email that you've created beforehand.</span></span> <span data-ttu-id="c4ce8-123">创建电子邮件正文时，利用动态标记个性化发送到目标的电子邮件。 </span><span class="sxs-lookup"><span data-stu-id="c4ce8-123">As you create the body of the email, take advantage of the **dynamic tags** to personalize the email to your targets.</span></span> <span data-ttu-id="c4ce8-124">单击 **"网络钓鱼"** 链接，将以前选择的网络钓鱼 URL 添加到邮件正文中。</span><span class="sxs-lookup"><span data-stu-id="c4ce8-124">Click **Phishing link** to add the previously selected phishing URL into the body of the message.</span></span>

![在 Microsoft Defender for Office 365 的有效负载创建中突出显示的网络钓鱼链接和动态标记](../../media/attack-sim-preview-payload-email-body.png)

> [!TIP]
> <span data-ttu-id="c4ce8-126">若要节省时间，请切换该选项以将电子邮件中所有 **链接替换为网络钓鱼链接**。</span><span class="sxs-lookup"><span data-stu-id="c4ce8-126">To save time, toggle on the option to **replace all links in the email message with the phishing link**.</span></span>

<span data-ttu-id="c4ce8-127">完成有效负载生成后，单击"下一步 **"。**</span><span class="sxs-lookup"><span data-stu-id="c4ce8-127">Once you're done building the payload to your liking, click **Next**.</span></span>

## <a name="adding-indicators"></a><span data-ttu-id="c4ce8-128">添加指示器</span><span class="sxs-lookup"><span data-stu-id="c4ce8-128">Adding indicators</span></span>

<span data-ttu-id="c4ce8-129">指示器可帮助员工完成攻击模拟，了解他们可以在将来的攻击中查找的线索。</span><span class="sxs-lookup"><span data-stu-id="c4ce8-129">Indicators will help employees going through the attack simulation understand the clue they can look for in future attacks.</span></span> <span data-ttu-id="c4ce8-130">若要开始，请单击 **"添加指示器"。**</span><span class="sxs-lookup"><span data-stu-id="c4ce8-130">To start, click **Add indicator**.</span></span>

<span data-ttu-id="c4ce8-131">从下拉列表中选择一个希望使用的指示器。</span><span class="sxs-lookup"><span data-stu-id="c4ce8-131">Select an indicator you'd like to use from the drop-down list.</span></span> <span data-ttu-id="c4ce8-132">此列表被组织为包含网络钓鱼电子邮件中最常见的线索。</span><span class="sxs-lookup"><span data-stu-id="c4ce8-132">This list is curated to contain the most common clues that appear in phishing email messages.</span></span> <span data-ttu-id="c4ce8-133">选择后，请确保将指示器放置设置为"**从** 电子邮件正文"并单击"**选择文本"。**</span><span class="sxs-lookup"><span data-stu-id="c4ce8-133">Once selected, make sure the indicator placement is set to **From the body of the email** and click on **Select text**.</span></span> <span data-ttu-id="c4ce8-134">突出显示显示此指示器的有效负载部分，然后单击"**选择"。**</span><span class="sxs-lookup"><span data-stu-id="c4ce8-134">Highlight the portion of your payload where this indicator appears and click **Select**.</span></span>

![要添加到攻击模拟培训中的指示器的消息正文中的突出显示文本](../../media/attack-sim-preview-select-text.png)

<span data-ttu-id="c4ce8-136">添加用于描述指示器的自定义说明，然后单击指示器预览帧以查看指示器预览。</span><span class="sxs-lookup"><span data-stu-id="c4ce8-136">Add a custom description to describe the indicator and click within the indicator preview frame to see a preview of your indicator.</span></span> <span data-ttu-id="c4ce8-137">完成后，单击"**添加"。**</span><span class="sxs-lookup"><span data-stu-id="c4ce8-137">Once done, click **Add**.</span></span> <span data-ttu-id="c4ce8-138">重复这些步骤，直到负载中涵盖所有指示器。</span><span class="sxs-lookup"><span data-stu-id="c4ce8-138">Repeat these steps until you've covered all indicators in your payload.</span></span>

## <a name="review-payload"></a><span data-ttu-id="c4ce8-139">查看有效负载</span><span class="sxs-lookup"><span data-stu-id="c4ce8-139">Review payload</span></span>

<span data-ttu-id="c4ce8-140">你已完成有效负载的生成。</span><span class="sxs-lookup"><span data-stu-id="c4ce8-140">You're done building your payload.</span></span> <span data-ttu-id="c4ce8-141">现在，请查看详细信息并查看有效负载的预览。</span><span class="sxs-lookup"><span data-stu-id="c4ce8-141">Now it's time to review the details and see a preview of your payload.</span></span> <span data-ttu-id="c4ce8-142">预览将包括你创建的所有指示器。</span><span class="sxs-lookup"><span data-stu-id="c4ce8-142">The preview will include all indicators that you've created.</span></span> <span data-ttu-id="c4ce8-143">你可以从此步骤编辑负载的每个部分。</span><span class="sxs-lookup"><span data-stu-id="c4ce8-143">You can edit each part of the payload from this step.</span></span> <span data-ttu-id="c4ce8-144">满足后， **提交** 有效负载。</span><span class="sxs-lookup"><span data-stu-id="c4ce8-144">Once satisfied, **Submit** your payload.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c4ce8-145">你创建的负载将租户 **作为** 源。</span><span class="sxs-lookup"><span data-stu-id="c4ce8-145">Payloads that you've created will have **Tenant** as their source.</span></span> <span data-ttu-id="c4ce8-146">选择有效负载时，请确保不筛选出 **租户**。</span><span class="sxs-lookup"><span data-stu-id="c4ce8-146">When selecting payloads, make sure that you don't filter out **Tenant**.</span></span>
