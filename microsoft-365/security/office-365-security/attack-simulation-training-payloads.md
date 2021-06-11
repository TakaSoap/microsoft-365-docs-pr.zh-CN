---
title: 创建攻击模拟培训的有效负载
ms.author: daniha
author: danihalfin
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.prod: m365-security
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: 管理员可以了解如何在 Microsoft Defender for Office 365 中为攻击模拟培训创建自定义负载。
ms.technology: mdo
ms.openlocfilehash: ac7963b71c466e8dfdc513a2563776cd4e10af95
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/10/2021
ms.locfileid: "52878756"
---
# <a name="create-a-custom-payload-for-attack-simulation-training"></a><span data-ttu-id="9646f-103">创建用于攻击模拟培训的自定义负载</span><span class="sxs-lookup"><span data-stu-id="9646f-103">Create a custom payload for Attack simulation training</span></span>

<span data-ttu-id="9646f-104">**适用于 Microsoft** [Defender for Office 365计划 2](defender-for-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="9646f-104">**Applies to** [Microsoft Defender for Office 365 plan 2](defender-for-office-365.md)</span></span>

<span data-ttu-id="9646f-105">Microsoft 为各种社交工程技术提供了可靠的有效负载目录，以与攻击模拟培训配对。</span><span class="sxs-lookup"><span data-stu-id="9646f-105">Microsoft offers a robust payload catalog for various social engineering techniques to pair with your attack simulation training.</span></span> <span data-ttu-id="9646f-106">但是，你可能希望创建更适用于你的组织的自定义有效负载。</span><span class="sxs-lookup"><span data-stu-id="9646f-106">However, you might want to create custom payloads that will work better for your organization.</span></span> <span data-ttu-id="9646f-107">本文介绍如何在 Microsoft Defender for Office 365 攻击模拟培训中创建负载。</span><span class="sxs-lookup"><span data-stu-id="9646f-107">This article describes how to create a payload in Attack simulation training in Microsoft Defender for Office 365.</span></span>

<span data-ttu-id="9646f-108">可以通过在专用"有效负载"选项卡或模拟创建向导中单击"创建有效负载"[来创建有效负载](attack-simulation-training.md#selecting-a-payload)。 [  ](https://security.microsoft.com/attacksimulator?viewid=payload)</span><span class="sxs-lookup"><span data-stu-id="9646f-108">You can create a payload by clicking on **Create a payload** in either the [dedicated **Payloads** tab](https://security.microsoft.com/attacksimulator?viewid=payload) or within the [simulation creation wizard](attack-simulation-training.md#selecting-a-payload).</span></span>

<span data-ttu-id="9646f-109">向导的第一步将让你选择有效负载类型。</span><span class="sxs-lookup"><span data-stu-id="9646f-109">The first step in the wizard will have you select a payload type.</span></span> <span data-ttu-id="9646f-110">**目前，只有电子邮件可用**。</span><span class="sxs-lookup"><span data-stu-id="9646f-110">**Currently, only email is available**.</span></span>

<span data-ttu-id="9646f-111">接下来，选择一种关联的技术。</span><span class="sxs-lookup"><span data-stu-id="9646f-111">Next, select an associated technique.</span></span> <span data-ttu-id="9646f-112">有关技术的详细信息，请参阅 [选择社交工程技术](attack-simulation-training.md#selecting-a-social-engineering-technique)。</span><span class="sxs-lookup"><span data-stu-id="9646f-112">See more details on techniques at [Selecting a social engineering technique](attack-simulation-training.md#selecting-a-social-engineering-technique).</span></span>

<span data-ttu-id="9646f-113">在下一步中，将有效负载命名。</span><span class="sxs-lookup"><span data-stu-id="9646f-113">In the next step name your payload.</span></span> <span data-ttu-id="9646f-114">（可选）您可以为它提供说明。</span><span class="sxs-lookup"><span data-stu-id="9646f-114">Optionally, you can give it a description.</span></span>

## <a name="configure-payload"></a><span data-ttu-id="9646f-115">配置有效负载</span><span class="sxs-lookup"><span data-stu-id="9646f-115">Configure payload</span></span>

<span data-ttu-id="9646f-116">现在，可以生成有效负载了。</span><span class="sxs-lookup"><span data-stu-id="9646f-116">Now it's time to build your payload.</span></span> <span data-ttu-id="9646f-117">在"发件人详细信息"部分输入发件人的姓名、电子邮件地址和 **电子邮件主题** 。</span><span class="sxs-lookup"><span data-stu-id="9646f-117">Input the sender's name, email address, and the email's subject in the **Sender details** section.</span></span> <span data-ttu-id="9646f-118">从提供的列表中选择网络钓鱼 URL。</span><span class="sxs-lookup"><span data-stu-id="9646f-118">Pick a phishing URL from the provided list.</span></span> <span data-ttu-id="9646f-119">此 URL 稍后将嵌入到邮件正文中。</span><span class="sxs-lookup"><span data-stu-id="9646f-119">This URL will later be embedded into the body of the message.</span></span>

> [!TIP]
> <span data-ttu-id="9646f-120">你可以为有效负载的发件人选择内部电子邮件，这会使有效负载显示为来自公司的另一名员工。</span><span class="sxs-lookup"><span data-stu-id="9646f-120">You can choose an internal email for your payload's sender, which will make the payload appear as coming from another employee of the company.</span></span> <span data-ttu-id="9646f-121">这将提高有效负载的易读性，并且有助于引导员工了解内部威胁的风险。</span><span class="sxs-lookup"><span data-stu-id="9646f-121">This will increase susceptibility to the payload and will help educate employees on the risk of internal threats.</span></span>

<span data-ttu-id="9646f-122">格式文本编辑器可用于创建有效负载。</span><span class="sxs-lookup"><span data-stu-id="9646f-122">A rich text editor is available to create your payload.</span></span> <span data-ttu-id="9646f-123">还可以导入预先创建的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="9646f-123">You can also import an email that you've created beforehand.</span></span> <span data-ttu-id="9646f-124">创建电子邮件正文时，请利用动态标记将电子邮件个性化到目标。</span><span class="sxs-lookup"><span data-stu-id="9646f-124">As you create the body of the email, take advantage of the **dynamic tags** to personalize the email to your targets.</span></span> <span data-ttu-id="9646f-125">单击 **"网络钓鱼"** 链接，将以前选择的网络钓鱼 URL 添加到邮件正文中。</span><span class="sxs-lookup"><span data-stu-id="9646f-125">Click **Phishing link** to add the previously selected phishing URL into the body of the message.</span></span>

![在 Microsoft Defender for Office 365 的有效负载创建中突出显示的网络钓鱼链接和Office 365](../../media/attack-sim-preview-payload-email-body.png)

> [!TIP]
> <span data-ttu-id="9646f-127">为了节省时间，请切换为将电子邮件中所有链接 **替换为网络钓鱼链接 的选项**。</span><span class="sxs-lookup"><span data-stu-id="9646f-127">To save time, toggle on the option to **replace all links in the email message with the phishing link**.</span></span>

<span data-ttu-id="9646f-128">完成有效负载生成后，单击"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="9646f-128">Once you're done building the payload to your liking, click **Next**.</span></span>

## <a name="adding-indicators"></a><span data-ttu-id="9646f-129">添加指示器</span><span class="sxs-lookup"><span data-stu-id="9646f-129">Adding indicators</span></span>

<span data-ttu-id="9646f-130">指示器可帮助员工完成攻击模拟，了解他们可以在将来的攻击中查找的线索。</span><span class="sxs-lookup"><span data-stu-id="9646f-130">Indicators will help employees going through the attack simulation understand the clue they can look for in future attacks.</span></span> <span data-ttu-id="9646f-131">若要开始，请单击"**添加指示器"。**</span><span class="sxs-lookup"><span data-stu-id="9646f-131">To start, click **Add indicator**.</span></span>

<span data-ttu-id="9646f-132">从下拉列表中选择一个希望使用的指示器。</span><span class="sxs-lookup"><span data-stu-id="9646f-132">Select an indicator you'd like to use from the drop-down list.</span></span> <span data-ttu-id="9646f-133">此列表是为包含网络钓鱼电子邮件中最常见的线索而提供的。</span><span class="sxs-lookup"><span data-stu-id="9646f-133">This list is curated to contain the most common clues that appear in phishing email messages.</span></span> <span data-ttu-id="9646f-134">选择后，请确保将指示器放置设置为 **"从电子邮件正文"，** 然后单击"选择 **文本"。**</span><span class="sxs-lookup"><span data-stu-id="9646f-134">Once selected, make sure the indicator placement is set to **From the body of the email** and click on **Select text**.</span></span> <span data-ttu-id="9646f-135">突出显示显示此指示器的有效负载部分，然后单击"选择 **"。**</span><span class="sxs-lookup"><span data-stu-id="9646f-135">Highlight the portion of your payload where this indicator appears and click **Select**.</span></span>

![要添加到攻击模拟培训中的指示器的邮件正文中的突出显示文本](../../media/attack-sim-preview-select-text.png)

<span data-ttu-id="9646f-137">添加用于描述指示器的自定义说明，然后单击指示器预览框架以查看指示器预览。</span><span class="sxs-lookup"><span data-stu-id="9646f-137">Add a custom description to describe the indicator and click within the indicator preview frame to see a preview of your indicator.</span></span> <span data-ttu-id="9646f-138">完成后，单击"添加 **"。**</span><span class="sxs-lookup"><span data-stu-id="9646f-138">Once done, click **Add**.</span></span> <span data-ttu-id="9646f-139">重复这些步骤，直到负载中涵盖所有指示器。</span><span class="sxs-lookup"><span data-stu-id="9646f-139">Repeat these steps until you've covered all indicators in your payload.</span></span>

## <a name="review-payload"></a><span data-ttu-id="9646f-140">查看有效负载</span><span class="sxs-lookup"><span data-stu-id="9646f-140">Review payload</span></span>

<span data-ttu-id="9646f-141">你已完成有效负载的生成。</span><span class="sxs-lookup"><span data-stu-id="9646f-141">You're done building your payload.</span></span> <span data-ttu-id="9646f-142">现在，该查看详细信息并查看有效负载预览了。</span><span class="sxs-lookup"><span data-stu-id="9646f-142">Now it's time to review the details and see a preview of your payload.</span></span> <span data-ttu-id="9646f-143">预览将包括你创建的所有指示器。</span><span class="sxs-lookup"><span data-stu-id="9646f-143">The preview will include all indicators that you've created.</span></span> <span data-ttu-id="9646f-144">你可以从此步骤编辑负载的每个部分。</span><span class="sxs-lookup"><span data-stu-id="9646f-144">You can edit each part of the payload from this step.</span></span> <span data-ttu-id="9646f-145">一旦满足，你可以 **提交** 负载。</span><span class="sxs-lookup"><span data-stu-id="9646f-145">Once satisfied, you can **Submit** your payload.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9646f-146">你创建的负载将具有 **租户** 作为源。</span><span class="sxs-lookup"><span data-stu-id="9646f-146">Payloads that you've created will have **Tenant** as their source.</span></span> <span data-ttu-id="9646f-147">选择有效负载时，请确保不要筛选出"租户 **"。**</span><span class="sxs-lookup"><span data-stu-id="9646f-147">When selecting payloads, make sure that you don't filter out **Tenant**.</span></span>

## <a name="related-links"></a><span data-ttu-id="9646f-148">相关链接</span><span class="sxs-lookup"><span data-stu-id="9646f-148">Related links</span></span>

[<span data-ttu-id="9646f-149">开始使用攻击模拟培训</span><span class="sxs-lookup"><span data-stu-id="9646f-149">Get started using Attack simulation training</span></span>](attack-simulation-training-get-started.md)

[<span data-ttu-id="9646f-150">创建网络钓鱼攻击模拟</span><span class="sxs-lookup"><span data-stu-id="9646f-150">Create a phishing attack simulation</span></span>](attack-simulation-training.md)

[<span data-ttu-id="9646f-151">通过攻击模拟培训获得见解</span><span class="sxs-lookup"><span data-stu-id="9646f-151">Gain insights through Attack simulation training</span></span>](attack-simulation-training-insights.md)
