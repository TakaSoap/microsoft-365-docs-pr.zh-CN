---
title: 创建、测试和优化 DLP 策略
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.NewPolicyFromTemplate
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
ms.custom:
- seo-marvel-mar2020
ms.assetid: 59414438-99f5-488b-975c-5023f2254369
description: 本文将了解如何根据组织需求创建、测试和调整 DLP 策略。
ms.openlocfilehash: bd4857a2baefb22d789fc713a537d7e4a656718d
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51052080"
---
# <a name="create-test-and-tune-a-dlp-policy"></a><span data-ttu-id="5a356-103">创建、测试和优化 DLP 策略</span><span class="sxs-lookup"><span data-stu-id="5a356-103">Create, test, and tune a DLP policy</span></span>

<span data-ttu-id="5a356-104">DLP (数据丢失) 可帮助您防止意外或意外共享敏感信息。</span><span class="sxs-lookup"><span data-stu-id="5a356-104">Data loss prevention (DLP) helps you prevent the unintentional or accidental sharing of sensitive information.</span></span>

<span data-ttu-id="5a356-105">DLP 检查电子邮件和文件，以查找敏感信息，如信用卡号。</span><span class="sxs-lookup"><span data-stu-id="5a356-105">DLP examines email messages and files for sensitive information, like a credit card number.</span></span> <span data-ttu-id="5a356-106">使用 DLP 可以检测敏感信息，并采取措施，例如：</span><span class="sxs-lookup"><span data-stu-id="5a356-106">Using DLP you can detect sensitive information, and take action such as:</span></span>

- <span data-ttu-id="5a356-107">记录事件以用于审核</span><span class="sxs-lookup"><span data-stu-id="5a356-107">Log the event for auditing purposes</span></span>
- <span data-ttu-id="5a356-108">向发送电子邮件或共享文件的最终用户显示警告</span><span class="sxs-lookup"><span data-stu-id="5a356-108">Display a warning to the end user who is sending the email or sharing the file</span></span>
- <span data-ttu-id="5a356-109">主动阻止电子邮件或文件共享发生</span><span class="sxs-lookup"><span data-stu-id="5a356-109">Actively block the email or file sharing from taking place</span></span>

## <a name="permissions"></a><span data-ttu-id="5a356-110">Permissions</span><span class="sxs-lookup"><span data-stu-id="5a356-110">Permissions</span></span>

<span data-ttu-id="5a356-111">创建 DLP 策略的合规性团队成员需要具有对合规中心的访问权限。</span><span class="sxs-lookup"><span data-stu-id="5a356-111">Members of your compliance team who will create DLP policies need permissions to the Compliance Center.</span></span> <span data-ttu-id="5a356-112">默认情况下，租户管理员将具有访问权限，可授予合规部官员和其他人员访问权限。</span><span class="sxs-lookup"><span data-stu-id="5a356-112">By default, your tenant admin will have access can give compliance officers and other people access.</span></span> <span data-ttu-id="5a356-113">请按以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="5a356-113">Follow these steps:</span></span>
  
1. <span data-ttu-id="5a356-114">在 Microsoft 365 中创建组并向其添加合规部主管。</span><span class="sxs-lookup"><span data-stu-id="5a356-114">Create a group in Microsoft 365 and add compliance officers to it.</span></span>
    
2. <span data-ttu-id="5a356-115">在安全 &amp; 合规中心的“**权限**”页面上创建一个角色组。</span><span class="sxs-lookup"><span data-stu-id="5a356-115">Create a role group on the **Permissions** page of the Security &amp; Compliance Center.</span></span> 

3. <span data-ttu-id="5a356-116">创建角色组时，请使用" **选择** 角色"部分将以下角色添加到角色组 **：DLP Compliance Management**。</span><span class="sxs-lookup"><span data-stu-id="5a356-116">While creating the role group, use the **Choose Roles** section to add the following role to the role group: **DLP Compliance Management**.</span></span>
    
4. <span data-ttu-id="5a356-117">使用“**选择成员**”部分，将先前创建的 Microsoft 365 组添加到角色组中。</span><span class="sxs-lookup"><span data-stu-id="5a356-117">Use the **Choose Members** section to add the Microsoft 365 group you created before to the role group.</span></span>

<span data-ttu-id="5a356-118">使用" **仅查看 DLP 合规性管理** "角色创建具有 DLP 策略和 DLP 报告仅查看权限的角色组。</span><span class="sxs-lookup"><span data-stu-id="5a356-118">Use the **View-Only DLP Compliance Management** role to create role group with view-only privileges to the DLP policies and DLP reports.</span></span>

<span data-ttu-id="5a356-119">有关详细信息，请访问[向用户授予对 Office 365 合规中心的访问权限](../security/defender-365-security/grant-access-to-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="5a356-119">For more information, see [Give users access to the Office 365 Compliance Center](../security/defender-365-security/grant-access-to-the-security-and-compliance-center.md).</span></span>
  
<span data-ttu-id="5a356-120">创建和应用 DLP 策略时需要这些权限，才能不强制执行策略。</span><span class="sxs-lookup"><span data-stu-id="5a356-120">These permissions are required to create and apply a DLP policy not to enforce policies.</span></span>

## <a name="how-sensitive-information-is-detected-by-dlp"></a><span data-ttu-id="5a356-121">DLP 如何检测敏感信息</span><span class="sxs-lookup"><span data-stu-id="5a356-121">How sensitive information is detected by DLP</span></span>

<span data-ttu-id="5a356-122">DLP 通过正则表达式 (RegEx) 模式匹配，以及其他指示器（如某些关键字与匹配模式的邻近度）查找敏感信息。</span><span class="sxs-lookup"><span data-stu-id="5a356-122">DLP finds sensitive information by regular expression (RegEx) pattern matching, in combination with other indicators such as the proximity of certain keywords to the matching patterns.</span></span> <span data-ttu-id="5a356-123">例如，VISA 信用卡号有 16 个数字。</span><span class="sxs-lookup"><span data-stu-id="5a356-123">For example, a VISA credit card number has 16 digits.</span></span> <span data-ttu-id="5a356-124">但是，可以不同方式写入这些数字，例如 1111-1111-1111-1111、1111 1111 1111 1111 或 1111111111111。</span><span class="sxs-lookup"><span data-stu-id="5a356-124">But, those digits can be written in different ways, such as 1111-1111-1111-1111, 1111 1111 1111 1111, or 1111111111111111.</span></span>

<span data-ttu-id="5a356-125">任何 16 位字符串不一定是信用卡号，它可以是技术支持系统的票证号或硬件的序列号。</span><span class="sxs-lookup"><span data-stu-id="5a356-125">Any 16-digit string is not necessarily a credit card number, it could be a ticket number from a help desk system, or a serial number of a piece of hardware.</span></span> <span data-ttu-id="5a356-126">为了区分信用卡号和无害的 16 位数字字符串，将执行 (校验和) ，以确认数字与各种信用卡品牌的已知模式匹配。</span><span class="sxs-lookup"><span data-stu-id="5a356-126">To tell the difference between a credit card number and a harmless 16-digit string, a calculation is performed (checksum) to confirm that the numbers match a known pattern from the various credit card brands.</span></span>

<span data-ttu-id="5a356-127">如果 DLP 找到关键字（如"VISA"或"AMEX"，即可能是信用卡到期日期的接近日期值）时，DLP 还会使用该数据来帮助其确定字符串是否是信用卡号。</span><span class="sxs-lookup"><span data-stu-id="5a356-127">If DLP finds keywords such as "VISA" or "AMEX", near date values that might be the credit card expiry date, DLP also uses that data to help it decide whether the string is a credit card number or not.</span></span>

<span data-ttu-id="5a356-128">换句话说，DLP 足够智能，可以识别电子邮件中这两个文本字符串的区别：</span><span class="sxs-lookup"><span data-stu-id="5a356-128">In other words, DLP is smart enough to recognize the difference between these two strings of text in an email:</span></span>

- <span data-ttu-id="5a356-129">"能否为我订购一台新笔记本电脑。</span><span class="sxs-lookup"><span data-stu-id="5a356-129">"Can you order me a new laptop.</span></span> <span data-ttu-id="5a356-130">使用我的 VISA 号码 1111-1111-1111-1111（2012 年 11 月 22 日到期）并将估计的送达日期发送给我。"</span><span class="sxs-lookup"><span data-stu-id="5a356-130">Use my VISA number 1111-1111-1111-1111, expiry 11/22, and send me the estimated delivery date when you have it."</span></span>
- <span data-ttu-id="5a356-131">"我的笔记本电脑序列号为 2222-2222-2222-2222，于 2010 年 11 月 11 日购买。</span><span class="sxs-lookup"><span data-stu-id="5a356-131">"My laptop serial number is 2222-2222-2222-2222 and it was purchased on 11/2010.</span></span> <span data-ttu-id="5a356-132">路过一下，我的旅行护照是否获得批准？</span><span class="sxs-lookup"><span data-stu-id="5a356-132">By the way, is my travel visa approved yet?"</span></span>

<span data-ttu-id="5a356-133">请参阅 [敏感信息类型实体定义](sensitive-information-type-entity-definitions.md) ，该定义说明了如何检测每个信息类型。</span><span class="sxs-lookup"><span data-stu-id="5a356-133">See [Sensitive information type entity definitions](sensitive-information-type-entity-definitions.md) that explains how each information type is detected.</span></span>

## <a name="where-to-start-with-data-loss-prevention"></a><span data-ttu-id="5a356-134">从数据丢失防护开始</span><span class="sxs-lookup"><span data-stu-id="5a356-134">Where to start with data loss prevention</span></span>

<span data-ttu-id="5a356-135">当数据泄露的风险并不明显时，很难确定应从何处开始实施 DLP。</span><span class="sxs-lookup"><span data-stu-id="5a356-135">When the risks of data leakage aren't entirely obvious, it's difficult to work out where exactly you should start with implementing DLP.</span></span> <span data-ttu-id="5a356-136">幸运的是，DLP 策略可以在"测试模式"中运行，从而允许您在启用它们之前评估其有效性和准确性。</span><span class="sxs-lookup"><span data-stu-id="5a356-136">Fortunately, DLP policies can be run in "test mode", allowing you to gauge their effectiveness and accuracy before you turn them on.</span></span>

<span data-ttu-id="5a356-137">dlp policies for Exchange Online can be managed through the Exchange admin center.</span><span class="sxs-lookup"><span data-stu-id="5a356-137">DLP policies for Exchange Online can be managed through the Exchange admin center.</span></span> <span data-ttu-id="5a356-138">但是，可以通过安全与合规中心配置所有& DLP 策略，以便本文中将使用此策略进行演示。</span><span class="sxs-lookup"><span data-stu-id="5a356-138">But you can configure DLP policies for all workloads through the Security & Compliance Center, so that's what I'll use for demonstrations in this article.</span></span> <span data-ttu-id="5a356-139">在安全&合规中心，您可以在数据丢失防护策略下 **找到** DLP  >  **策略**。</span><span class="sxs-lookup"><span data-stu-id="5a356-139">In the Security & Compliance Center, you'll find the DLP policies under **Data loss prevention** > **Policy**.</span></span> <span data-ttu-id="5a356-140">选择 **"创建策略** "开始。</span><span class="sxs-lookup"><span data-stu-id="5a356-140">Choose **Create a policy** to start.</span></span>

<span data-ttu-id="5a356-141">Microsoft 365提供了一系列可用于创建策略的[DLP](what-the-dlp-policy-templates-include.md)策略模板。</span><span class="sxs-lookup"><span data-stu-id="5a356-141">Microsoft 365 provides a range of [DLP policy templates](what-the-dlp-policy-templates-include.md) you can use to create policies.</span></span> <span data-ttu-id="5a356-142">假设你是澳大利亚企业。</span><span class="sxs-lookup"><span data-stu-id="5a356-142">Let's say that you're an Australian business.</span></span> <span data-ttu-id="5a356-143">可以筛选澳大利亚上的模板，然后选择"财务、医疗与健康"和"隐私"。</span><span class="sxs-lookup"><span data-stu-id="5a356-143">You can filter the templates on Australia, and choose Financial, Medical and Health, and Privacy.</span></span>

![用于选择国家/地区的选项](../media/DLP-create-test-tune-choose-country.png)

<span data-ttu-id="5a356-145">对于本演示，我将选择澳大利亚个人身份信息 (PII) 数据，其中包括澳大利亚税号 (TFN) 和驾驶证号码的信息类型。</span><span class="sxs-lookup"><span data-stu-id="5a356-145">For this demonstration I'll choose Australian Personally Identifiable Information (PII) Data, which includes the information types of Australian Tax File Number (TFN) and Driver's License Number.</span></span>

![用于选择策略模板的选项](../media/DLP-create-test-tune-choose-policy-template.png)

<span data-ttu-id="5a356-147">为新的 DLP 策略命名。</span><span class="sxs-lookup"><span data-stu-id="5a356-147">Give your new DLP policy a name.</span></span> <span data-ttu-id="5a356-148">默认名称将匹配 DLP 策略模板，但您应该选择您自己的更具描述性的名称，因为可以从同一模板创建多个策略。</span><span class="sxs-lookup"><span data-stu-id="5a356-148">The default name will match the DLP policy template, but you should choose a more descriptive name of your own, because multiple policies can be created from the same template.</span></span>

![命名策略的选项](../media/DLP-create-test-tune-name-policy.png)

<span data-ttu-id="5a356-150">选择策略将应用于的位置。</span><span class="sxs-lookup"><span data-stu-id="5a356-150">Choose the locations that the policy will apply to.</span></span> <span data-ttu-id="5a356-151">DLP 策略可应用于 Exchange Online、SharePoint Online 和 OneDrive for Business。</span><span class="sxs-lookup"><span data-stu-id="5a356-151">DLP policies can apply to Exchange Online, SharePoint Online, and OneDrive for Business.</span></span> <span data-ttu-id="5a356-152">我将保留此策略的配置，以应用于所有位置。</span><span class="sxs-lookup"><span data-stu-id="5a356-152">I am going to leave this policy configured to apply to all locations.</span></span>

![选择所有位置的选项](../media/DLP-create-test-tune-choose-locations.png)

<span data-ttu-id="5a356-154">第一 **步设置，** 现在只需接受默认值。</span><span class="sxs-lookup"><span data-stu-id="5a356-154">At the first **Policy Settings** step, just accept the defaults for now.</span></span> <span data-ttu-id="5a356-155">您可以自定义 DLP 策略，但默认设置是很好的开始。</span><span class="sxs-lookup"><span data-stu-id="5a356-155">You can customize DLP policies, but the defaults are a fine place to start.</span></span>

![用于自定义要保护的内容类型的选项](../media/DLP-create-test-tune-default-customization-settings.png)

<span data-ttu-id="5a356-157">单击"下一步"后，\*\*你将看到一个包含更多自定义 **设置** 策略策略页。</span><span class="sxs-lookup"><span data-stu-id="5a356-157">After clicking Next,\*\* you'll be presented with an additional **Policy Settings** page with more customization options.</span></span> <span data-ttu-id="5a356-158">对于你刚刚测试的策略，你可以在这里开始进行一些调整。</span><span class="sxs-lookup"><span data-stu-id="5a356-158">For a policy that you are just testing, here's where you can start to make some adjustments.</span></span>

- <span data-ttu-id="5a356-159">我目前已关闭策略提示，如果你只是测试了一些内容，并且还不想向用户显示任何内容，这是一个合理的步骤。</span><span class="sxs-lookup"><span data-stu-id="5a356-159">I've turned off policy tips for now, which is a reasonable step to take if you're just testing things out and don't want to display anything to users yet.</span></span> <span data-ttu-id="5a356-160">策略提示向用户显示即将违反 DLP 策略的警告。</span><span class="sxs-lookup"><span data-stu-id="5a356-160">Policy tips display warnings to users that they're about to violate a DLP policy.</span></span> <span data-ttu-id="5a356-161">例如，Outlook用户会看到一条警告，提示他们附加的文件包含信用卡号，并会导致其电子邮件被拒绝。</span><span class="sxs-lookup"><span data-stu-id="5a356-161">For example, an Outlook user will see a warning that the file they've attached contains credit card numbers and will cause their email to be rejected.</span></span> <span data-ttu-id="5a356-162">策略提示的目标是在不符合行为发生之前停止该行为。</span><span class="sxs-lookup"><span data-stu-id="5a356-162">The goal of policy tips is to stop the non-compliant behaviour before it happens.</span></span>
- <span data-ttu-id="5a356-163">我还将实例数量从 10 个减少为 1 个，以便此策略将检测澳大利亚 PII 数据的任何共享，而不只是批量共享数据。</span><span class="sxs-lookup"><span data-stu-id="5a356-163">I've also decreased the number of instances from 10 to 1, so that this policy will detect any sharing of Australian PII data, not just bulk sharing of the data.</span></span>
- <span data-ttu-id="5a356-164">我还将另一个收件人添加到事件报告电子邮件中。</span><span class="sxs-lookup"><span data-stu-id="5a356-164">I've also added another recipient to the incident report email.</span></span>

![其他策略设置](../media/DLP-create-test-tune-more-policy-settings.png)

<span data-ttu-id="5a356-166">最后，我最初已配置此策略以在测试模式下运行。</span><span class="sxs-lookup"><span data-stu-id="5a356-166">Finally, I've configured this policy to run in test mode initially.</span></span> <span data-ttu-id="5a356-167">请注意，此处还有一个在测试模式下禁用策略提示的选项。</span><span class="sxs-lookup"><span data-stu-id="5a356-167">Notice there's also an option here to disable policy tips while in test mode.</span></span> <span data-ttu-id="5a356-168">这样，您便能够灵活地在策略中启用策略提示，然后决定在测试期间是显示还是禁止显示它们。</span><span class="sxs-lookup"><span data-stu-id="5a356-168">This gives you the flexibility to have policy tips enabled in the policy, but then decide whether to show or suppress them during your testing.</span></span>

![首先测试策略的选项](../media/DLP-create-test-tune-test-mode.png)

<span data-ttu-id="5a356-170">在最终审阅屏幕上，单击 **"创建** "以完成策略创建。</span><span class="sxs-lookup"><span data-stu-id="5a356-170">On the final review screen click **Create** to finish creating the policy.</span></span>

## <a name="test-a-dlp-policy"></a><span data-ttu-id="5a356-171">测试 DLP 策略</span><span class="sxs-lookup"><span data-stu-id="5a356-171">Test a DLP policy</span></span>

<span data-ttu-id="5a356-172">新的 DLP 策略将在大约 1 小时内开始生效。</span><span class="sxs-lookup"><span data-stu-id="5a356-172">Your new DLP policy will begin to take effect within about 1 hour.</span></span> <span data-ttu-id="5a356-173">你可以坐在一起等待正常用户活动触发它，也可以尝试自己触发它。</span><span class="sxs-lookup"><span data-stu-id="5a356-173">You can sit and wait for it to be triggered by normal user activity, or you can try to trigger it yourself.</span></span> <span data-ttu-id="5a356-174">之前我链接到 ["敏感信息类型"实体](sensitive-information-type-entity-definitions.md)定义，其中提供了有关如何触发 DLP 匹配的信息。</span><span class="sxs-lookup"><span data-stu-id="5a356-174">Earlier I linked to [Sensitive information type entity definitions](sensitive-information-type-entity-definitions.md), which provides you with information about how to trigger DLP matches.</span></span>

<span data-ttu-id="5a356-175">例如，我为本文创建的 DLP 策略将检测澳大利亚税号 (TFN) 。</span><span class="sxs-lookup"><span data-stu-id="5a356-175">As an example, the DLP policy I created for this article will detect Australian tax file numbers (TFN).</span></span> <span data-ttu-id="5a356-176">根据文档，匹配基于以下条件。</span><span class="sxs-lookup"><span data-stu-id="5a356-176">According to the documentation, the match is based on the following criteria.</span></span>

![有关澳大利亚税务文件编号的文档](../media/DLP-create-test-tune-Australia-Tax-File-Number-doc.png)
 
<span data-ttu-id="5a356-178">为了以相当大的方式演示 TFN 检测，字词为"税务文件编号"且邻近使用 9 个数字字符串的电子邮件将经过，而没有任何问题。</span><span class="sxs-lookup"><span data-stu-id="5a356-178">To demonstrate TFN detection in a rather blunt manner, an email with the words "Tax file number" and a 9 digit string in close proximity will sail through without any issues.</span></span> <span data-ttu-id="5a356-179">不触发 DLP 策略的原因是，9 位字符串必须传递校验和，以指示它是有效的 TFN，而不只是一个无害的数字字符串。</span><span class="sxs-lookup"><span data-stu-id="5a356-179">The reason it does not trigger the DLP policy is that the 9-digit string must pass the checksum that indicates it is a valid TFN and not just a harmless string of numbers.</span></span>

![不通过校验和的澳大利亚税号](../media/DLP-create-test-tune-email-test1.png)

<span data-ttu-id="5a356-181">相比之下，包含单词"Tax file number"和通过校验和的有效 TFN 的电子邮件将触发策略。</span><span class="sxs-lookup"><span data-stu-id="5a356-181">In comparison, an email with the words "Tax file number" and a valid TFN that passes the checksum will trigger the policy.</span></span> <span data-ttu-id="5a356-182">对于此处的记录，我使用的 TFN 来自生成有效（但不是正版）TFN 的网站。</span><span class="sxs-lookup"><span data-stu-id="5a356-182">For the record here, the TFN I'm using was taken from a website that generates valid, but not genuine, TFNs.</span></span> <span data-ttu-id="5a356-183">此类网站非常有用，因为测试 DLP 策略时最常见的错误之一是使用 无效 的假数，并且不会传递校验和 (因此不会触发策略) 。</span><span class="sxs-lookup"><span data-stu-id="5a356-183">Such sites are very useful because one of the most common mistakes when testing a DLP policy is using a fake number that's not valid and won't pass the checksum (and therefore won't trigger the policy).</span></span>

![通过校验和的澳大利亚税号](../media/DLP-create-test-tune-email-test2.png)

<span data-ttu-id="5a356-185">事件报告电子邮件包括检测到的敏感信息类型、检测到的实例数以及检测的可信度。</span><span class="sxs-lookup"><span data-stu-id="5a356-185">The incident report email includes the type of sensitive information that was detected, how many instances were detected, and the confidence level of the detection.</span></span>

![显示检测到的税务文件编号的事件报告](../media/DLP-create-test-tune-email-incident-report.png)

<span data-ttu-id="5a356-187">如果您将 DLP 策略保留为测试模式并分析事件报告电子邮件，您可以开始了解 DLP 策略的准确性以及强制执行策略时它的有效度。</span><span class="sxs-lookup"><span data-stu-id="5a356-187">If you leave your DLP policy in test mode and analyze the incident report emails, you can start to get a feel for the accuracy of the DLP policy and how effective it will be when it is enforced.</span></span> <span data-ttu-id="5a356-188">除了事件报告之外，您还可以使用 [DLP](view-the-dlp-reports.md) 报告查看整个租户内策略匹配项的聚合视图。</span><span class="sxs-lookup"><span data-stu-id="5a356-188">In addition to the incident reports, you can [use the DLP reports](view-the-dlp-reports.md) to see an aggregated view of policy matches across your tenant.</span></span>

## <a name="tune-a-dlp-policy"></a><span data-ttu-id="5a356-189">优化 DLP 策略</span><span class="sxs-lookup"><span data-stu-id="5a356-189">Tune a DLP policy</span></span>

<span data-ttu-id="5a356-190">在分析策略命中时，可能需要对策略的行为方式进行一些调整。</span><span class="sxs-lookup"><span data-stu-id="5a356-190">As you analyze your policy hits you might want to make some adjustments to how the policies behave.</span></span> <span data-ttu-id="5a356-191">作为一个简单的示例，你可能会确定电子邮件中的一个 TFN 不是问题 (我认为它仍然是问题，但为了演示) ，让我们使用它，但两个或多个实例是一个问题。</span><span class="sxs-lookup"><span data-stu-id="5a356-191">As a simple example, you might determine that one TFN in email is not a problem (I think it still is, but let's go with it for the sake of demonstration), but two or more instances is a problem.</span></span> <span data-ttu-id="5a356-192">多个实例可能是一个风险场景，例如员工通过电子邮件发送从 HR 数据库到外部方（例如外部会计服务）的 CSV 导出。</span><span class="sxs-lookup"><span data-stu-id="5a356-192">Multiple instances could be a risky scenario such as an employee emailing a CSV export from the HR database to an external party, for example an external accounting service.</span></span> <span data-ttu-id="5a356-193">当然，你更希望检测和阻止某些内容。</span><span class="sxs-lookup"><span data-stu-id="5a356-193">Definitely something you would prefer to detect and block.</span></span>

<span data-ttu-id="5a356-194">在安全&合规中心，可以编辑现有策略以调整行为。</span><span class="sxs-lookup"><span data-stu-id="5a356-194">In the Security & Compliance Center you can edit an existing policy to adjust the behaviour.</span></span>

![编辑策略的选项](../media/DLP-create-test-tune-edit-policy.png)
 
<span data-ttu-id="5a356-196">您可以调整位置设置，以便仅将策略应用于特定工作负荷或特定站点和帐户。</span><span class="sxs-lookup"><span data-stu-id="5a356-196">You can adjust the location settings so that the policy is applied only to specific workloads, or to specific sites and accounts.</span></span>

![选择特定位置的选项](../media/DLP-create-test-tune-edit-locations.png)

<span data-ttu-id="5a356-198">还可以调整策略设置并编辑规则以更好地满足你的需求。</span><span class="sxs-lookup"><span data-stu-id="5a356-198">You can also adjust the policy settings and edit the rules to better suit your needs.</span></span>

![编辑规则的选项](../media/DLP-create-test-tune-edit-rule.png)

<span data-ttu-id="5a356-200">在 DLP 策略中编辑规则时，可以更改：</span><span class="sxs-lookup"><span data-stu-id="5a356-200">When editing a rule within a DLP policy you can change:</span></span>

- <span data-ttu-id="5a356-201">条件，包括将触发规则的敏感数据实例的类型和数量。</span><span class="sxs-lookup"><span data-stu-id="5a356-201">The conditions, including the type and number of instances of sensitive data that will trigger the rule.</span></span>
- <span data-ttu-id="5a356-202">采取的操作，例如限制对内容的访问。</span><span class="sxs-lookup"><span data-stu-id="5a356-202">The actions that are taken, such as restricting access to the content.</span></span>
- <span data-ttu-id="5a356-203">用户通知，这是在用户的电子邮件客户端或 Web 浏览器中显示的策略提示。</span><span class="sxs-lookup"><span data-stu-id="5a356-203">User notifications, which are policy tips that are displayed to the user in their email client or web browser.</span></span>
- <span data-ttu-id="5a356-204">用户替代，确定用户是否可以选择继续其电子邮件或文件共享。</span><span class="sxs-lookup"><span data-stu-id="5a356-204">User overrides, which determines whether users can choose to proceed with their email or file sharing anyway.</span></span>
- <span data-ttu-id="5a356-205">事件报告，以通知管理员。</span><span class="sxs-lookup"><span data-stu-id="5a356-205">Incident reports, to notify administrators.</span></span>

![编辑规则部分的选项](../media/DLP-create-test-tune-editing-options.png)

<span data-ttu-id="5a356-207">对于本演示，我向策略添加了用户通知 (在没有足够用户意识培训) 的情况下执行此操作，并且允许用户使用业务理由或将策略标记为误报来替代策略。</span><span class="sxs-lookup"><span data-stu-id="5a356-207">For this demonstration I've added user notifications to the policy (be careful of doing this without adequate user awareness training), and allowed users to override the policy with a business justification or by flagging it as a false positive.</span></span> <span data-ttu-id="5a356-208">请注意，如果要包含有关组织策略的其他任何信息，也可以自定义电子邮件和策略提示文本，或者提示用户联系支持人员（如果他们有疑问）。</span><span class="sxs-lookup"><span data-stu-id="5a356-208">Note that you can also customize the email and policy tip text if you want to include any additional information about your organization's policies, or prompt users to contact support if they have questions.</span></span>

![用户通知和替代选项](../media/DLP-create-test-tune-user-notifications.png)

<span data-ttu-id="5a356-210">该策略包含用于处理高容量和低音量的两个规则，因此请确保使用您想要的操作编辑这两个规则。</span><span class="sxs-lookup"><span data-stu-id="5a356-210">The policy contains two rules for handling of high volume and low volume, so be sure to edit both with the actions that you want.</span></span> <span data-ttu-id="5a356-211">这是根据其特征以不同方式处理事例的机会。</span><span class="sxs-lookup"><span data-stu-id="5a356-211">This is an opportunity to treat cases differently depending on their characteristics.</span></span> <span data-ttu-id="5a356-212">例如，你可能允许针对低音量冲突进行覆盖，但不允许覆盖高音量冲突。</span><span class="sxs-lookup"><span data-stu-id="5a356-212">For example, you might allow overrides for low volume violations, but not allow overrides for high volume violations.</span></span>

![一个规则用于高容量，一个规则用于低容量](../media/DLP-create-test-tune-two-rules.png)

<span data-ttu-id="5a356-214">此外，如果要实际阻止或限制对违反策略的内容的访问，则需要对规则配置操作以执行该操作。</span><span class="sxs-lookup"><span data-stu-id="5a356-214">Also, if you want to actually block or restrict access to content that is in violation of policy, you need to configure an action on the rule to do so.</span></span>

![限制对内容的访问的选项](../media/DLP-create-test-tune-restrict-access-action.png)

<span data-ttu-id="5a356-216">将这些更改保存为策略设置后，我还需要返回到策略的主设置页面，并启用在策略在测试模式下向用户显示策略提示的选项。</span><span class="sxs-lookup"><span data-stu-id="5a356-216">After saving those changes to the policy settings, I also need to return to the main settings page for the policy and enable the option to show policy tips to users while the policy is in test mode.</span></span> <span data-ttu-id="5a356-217">这是向最终用户介绍 DLP 策略以及进行用户意识培训的有效方式，而不会冒太多影响其工作效率的误报的风险。</span><span class="sxs-lookup"><span data-stu-id="5a356-217">This is an effective way to introduce DLP policies to your end users, and do user awareness training, without risking too many false positives that impact their productivity.</span></span>

![在测试模式下显示策略提示的选项](../media/DLP-create-test-tune-show-policy-tips.png)

<span data-ttu-id="5a356-219">在服务器端 (或云端（如果) ，由于处理间隔不同，更改可能不会立即生效。</span><span class="sxs-lookup"><span data-stu-id="5a356-219">On the server side (or cloud side if you prefer), the change may not take effect immediately, due to various processing intervals.</span></span> <span data-ttu-id="5a356-220">如果要进行向用户显示新策略提示的 DLP 策略更改，用户可能不会看到更改立即在 Outlook 客户端中生效，从而每 24 小时检查一次策略更改。</span><span class="sxs-lookup"><span data-stu-id="5a356-220">If you're making a DLP policy change that will display new policy tips to a user, the user may not see the changes take effect immediately in their Outlook client, which checks for policy changes every 24 hours.</span></span> <span data-ttu-id="5a356-221">如果你想要加快测试速度，可以使用此注册表修补程序从 [PolicyNudges](https://support.microsoft.com/en-au/help/2823261/changes-to-a-data-loss-prevention-policy-don-t-take-effect-in-outlook?__hstc=18650278.46377037dc0a82baa8a30f0ef07a7b2f.1538687978676.1538693509953.1540315763430.3&__hssc=18650278.1.1540315763430&__hsfp=3446956451)项中清除上次下载时间戳。</span><span class="sxs-lookup"><span data-stu-id="5a356-221">If you want to speed things up for testing, you can use this registry fix to [clear the last download time stamp from the PolicyNudges key](https://support.microsoft.com/en-au/help/2823261/changes-to-a-data-loss-prevention-policy-don-t-take-effect-in-outlook?__hstc=18650278.46377037dc0a82baa8a30f0ef07a7b2f.1538687978676.1538693509953.1540315763430.3&__hssc=18650278.1.1540315763430&__hsfp=3446956451).</span></span> <span data-ttu-id="5a356-222">Outlook下一次重启并开始撰写电子邮件时，系统将会下载最新策略信息。</span><span class="sxs-lookup"><span data-stu-id="5a356-222">Outlook will download the latest policy information the next time you restart it and begin composing an email message.</span></span>

<span data-ttu-id="5a356-223">如果已启用策略提示，用户将开始在策略提示Outlook提示，并可以在出现误报时报告误报。</span><span class="sxs-lookup"><span data-stu-id="5a356-223">If you have policy tips enabled, the user will begin to see the tips in Outlook, and can report false positives to you when they occur.</span></span>

![策略提示，提供报告误报的选项](../media/DLP-create-test-tune-policy-tip-in-outlook.png)

## <a name="investigate-false-positives"></a><span data-ttu-id="5a356-225">调查误报</span><span class="sxs-lookup"><span data-stu-id="5a356-225">Investigate false positives</span></span>

<span data-ttu-id="5a356-226">DLP 策略模板并非开箱即用。</span><span class="sxs-lookup"><span data-stu-id="5a356-226">DLP policy templates are not perfect straight out of the box.</span></span> <span data-ttu-id="5a356-227">您可能发现环境中出现一些误报，这就是为什么轻松进入 DLP 部署非常重要的原因，因此请花时间充分测试和调整策略。</span><span class="sxs-lookup"><span data-stu-id="5a356-227">It's likely that you'll find some false positives occurring in your environment, which is why it's so important to ease your way into a DLP deployment, taking the time to adequately test and tune your policies.</span></span>

<span data-ttu-id="5a356-228">下面是一个误报示例。</span><span class="sxs-lookup"><span data-stu-id="5a356-228">Here's an example of a false positive.</span></span> <span data-ttu-id="5a356-229">此电子邮件是无害的。</span><span class="sxs-lookup"><span data-stu-id="5a356-229">This email is quite harmless.</span></span> <span data-ttu-id="5a356-230">用户向某人提供其移动电话号码，并包括其电子邮件签名。</span><span class="sxs-lookup"><span data-stu-id="5a356-230">The user is providing their mobile phone number to someone, and including their email signature.</span></span>

![显示误报信息的电子邮件](../media/DLP-create-test-tune-false-positive-email.png)
 
<span data-ttu-id="5a356-232">但是，用户会看到一条策略提示，警告他们电子邮件包含敏感信息，特别是澳大利亚驾驶证号码。</span><span class="sxs-lookup"><span data-stu-id="5a356-232">But the user sees a policy tip warning them that the email contains sensitive information, specifically, an Australian driver's license number.</span></span>

![在策略提示中报告误报的选项](../media/DLP-create-test-tune-policy-tip-closeup.png)

<span data-ttu-id="5a356-234">用户可以报告误报，管理员可以查看发生误报的原因。</span><span class="sxs-lookup"><span data-stu-id="5a356-234">The user can report the false positive, and the administrator can look into why it has occurred.</span></span> <span data-ttu-id="5a356-235">在事件报告电子邮件中，电子邮件被标记为误报。</span><span class="sxs-lookup"><span data-stu-id="5a356-235">In the incident report email, the email is flagged as a false positive.</span></span>

![显示误报的事件报告](../media/DLP-create-test-tune-false-positive-incident-report.png)

<span data-ttu-id="5a356-237">此驱动程序的许可证案例是一个很好的示例来深入了解。</span><span class="sxs-lookup"><span data-stu-id="5a356-237">This driver's license case is a good example to dig into.</span></span> <span data-ttu-id="5a356-238">出现此误报的原因是，"澳大利亚驾驶证"类型由任何 9 位字符串 (（即使是 10 位字符串) 的一部分）触发，该字符串类型与关键字"driver nsw" (不区分大小写的) 接近 300 个字符。</span><span class="sxs-lookup"><span data-stu-id="5a356-238">The reason this false positive has occurred is that the "Australian Driver's License" type will be triggered by any 9-digit string (even one that is part of a 10-digit string), within 300 characters proximity to the keywords "sydney nsw" (not case sensitive).</span></span> <span data-ttu-id="5a356-239">因此，它由电话号码和电子邮件签名触发，仅仅是因为用户恰好位于北京。</span><span class="sxs-lookup"><span data-stu-id="5a356-239">So it's triggered by the phone number and email signature, only because the user happens to be in Sydney.</span></span>


<span data-ttu-id="5a356-240">一个选项是从策略中删除澳大利亚驾驶证信息类型。</span><span class="sxs-lookup"><span data-stu-id="5a356-240">One option is to remove the Australian driver's license information type from the policy.</span></span> <span data-ttu-id="5a356-241">它就在那里，因为它是 DLP 策略模板的一部分，但不强制我们使用它。</span><span class="sxs-lookup"><span data-stu-id="5a356-241">It's in there because it's part of the DLP policy template, but we're not forced to use it.</span></span> <span data-ttu-id="5a356-242">如果你只对税务文件编号（而不是驱动程序许可证）感兴趣，则只需将其删除。</span><span class="sxs-lookup"><span data-stu-id="5a356-242">If you're only interested in Tax File Numbers and not driver's licenses, you can just remove it.</span></span> <span data-ttu-id="5a356-243">例如，你可以将其从策略中的低容量规则中删除，但将其保留为高容量规则，以便仍检测到多个驱动程序许可证的列表。</span><span class="sxs-lookup"><span data-stu-id="5a356-243">For example, you can remove it from the low volume rule in the policy, but leave it in the high volume rule so that lists of multiple drivers licenses are still detected.</span></span>

![从规则中删除敏感信息类型的选项](../media/DLP-create-test-tune-delete-low-volume-rule.png)
 
<span data-ttu-id="5a356-245">另一个选项是只需增加实例计数，以便仅在存在多个实例时检测到低容量的驱动程序许可证。</span><span class="sxs-lookup"><span data-stu-id="5a356-245">Another option is to simply increase the instance count, so that a low volume of driver's licenses is only detected when there are multiple instances.</span></span>

![编辑实例计数的选项](../media/DLP-create-test-tune-edit-instance-count.png)

<span data-ttu-id="5a356-247">除了更改实例计数之外，还可以调整匹配准确度 (可信度) 。</span><span class="sxs-lookup"><span data-stu-id="5a356-247">In addition to changing the instance count, you can also adjust the match accuracy (or confidence level).</span></span> <span data-ttu-id="5a356-248">如果您的敏感信息类型具有多个模式，您可以调整规则中的匹配准确度，以便规则仅匹配特定模式。</span><span class="sxs-lookup"><span data-stu-id="5a356-248">If your sensitive information type has multiple patterns, you can adjust the match accuracy in your rule, so that your rule matches only specific patterns.</span></span> <span data-ttu-id="5a356-249">例如，为了帮助减少误报，你可以设置规则的匹配准确度，以便它仅匹配可信度最高的模式。</span><span class="sxs-lookup"><span data-stu-id="5a356-249">For example, to help reduce false positives, you can set the match accuracy of your rule so that it matches only the pattern with the highest confidence level.</span></span> <span data-ttu-id="5a356-250">了解可信度的计算方式有点复杂 (超出本文) 的范围，但下面详细说明了如何使用可信度调整 [规则](data-loss-prevention-policies.md#match-accuracy)。</span><span class="sxs-lookup"><span data-stu-id="5a356-250">Understanding how confidence level is calculated is a bit tricky (and beyond the scope of this post), but here's a good explanation of [how to use confidence level to tune your rules](data-loss-prevention-policies.md#match-accuracy).</span></span>

<span data-ttu-id="5a356-251">最后，如果你希望更高级一点，可以自定义任何敏感信息类型，例如，可以从澳大利亚驾驶证号码的关键字列表中删除"澳大利亚 NSW"，以消除上面触发的误报。 [](sensitive-information-type-entity-definitions.md#australia-drivers-license-number)</span><span class="sxs-lookup"><span data-stu-id="5a356-251">Finally, if you want to get even a bit more advanced, you can customize any sensitive information type -- for example, you can remove "Sydney NSW" from the list of keywords for [Australia driver's license number](sensitive-information-type-entity-definitions.md#australia-drivers-license-number), to eliminate the false positive triggered above.</span></span> <span data-ttu-id="5a356-252">若要了解如何使用 XML 和 PowerShell 执行此操作，请参阅自定义内置 [敏感信息类型](customize-a-built-in-sensitive-information-type.md)。</span><span class="sxs-lookup"><span data-stu-id="5a356-252">To learn how to do this by using XML and PowerShell, see [customizing a built-in sensitive information type](customize-a-built-in-sensitive-information-type.md).</span></span>

## <a name="turn-on-a-dlp-policy"></a><span data-ttu-id="5a356-253">启用 DLP 策略</span><span class="sxs-lookup"><span data-stu-id="5a356-253">Turn on a DLP policy</span></span>

<span data-ttu-id="5a356-254">如果您满意您的 DLP 策略准确有效地检测敏感信息类型，并且您的最终用户已准备好处理已制定的策略，您可以启用该策略。</span><span class="sxs-lookup"><span data-stu-id="5a356-254">When you're happy that your DLP policy is accurately and effectively detecting sensitive information types, and that your end users are ready to deal with the policies being in place, then you can enable the policy.</span></span>

![打开策略的选项](../media/DLP-create-test-tune-turn-on-policy.png)
 
<span data-ttu-id="5a356-256">如果你正在等待查看策略何时生效，连接安全&合规中心[PowerShell](/powershell/exchange/connect-to-scc-powershell)并运行[Get-DlpCompliancePolicy cmdlet](/powershell/module/exchange/get-dlpcompliancepolicy)以查看 DistributionStatus。</span><span class="sxs-lookup"><span data-stu-id="5a356-256">If you're waiting to see when the policy will take effect, [Connect to Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell) and run the [Get-DlpCompliancePolicy cmdlet](/powershell/module/exchange/get-dlpcompliancepolicy) to see the DistributionStatus.</span></span>

![在 PowerShell 中运行 cmdlet](../media/DLP-create-test-tune-PowerShell.png)

<span data-ttu-id="5a356-258">启用 DLP 策略后，应运行您自己的一些最终测试，以确保发生预期的策略操作。</span><span class="sxs-lookup"><span data-stu-id="5a356-258">After turning on the DLP policy, you should run some final tests of your own to make sure that the expected policy actions are occurring.</span></span> <span data-ttu-id="5a356-259">如果你尝试测试信用卡数据等内容，则有一些在线网站包含如何生成示例信用卡或其他个人信息的信息，这些信息将传递校验和并触发策略。</span><span class="sxs-lookup"><span data-stu-id="5a356-259">If you're trying to test things like credit card data, there are websites online with information on how to generate sample credit card or other personal information that will pass checksums and trigger your policies.</span></span>

<span data-ttu-id="5a356-260">允许用户替代的策略将在策略提示中向用户显示该选项。</span><span class="sxs-lookup"><span data-stu-id="5a356-260">Policies that allow user overrides will present that option to the user as part of the policy tip.</span></span>

![允许用户替代的策略提示](../media/DLP-create-test-tune-override-option.png)

<span data-ttu-id="5a356-262">限制内容的策略将在策略提示中向用户显示警告，并阻止他们发送电子邮件。</span><span class="sxs-lookup"><span data-stu-id="5a356-262">Policies that restrict content will present the warning to the user as part of the policy tip, and prevent them from sending the email.</span></span>

![内容受限的策略提示](../media/DLP-create-test-tune-restrict-warning.png)

## <a name="summary"></a><span data-ttu-id="5a356-264">摘要</span><span class="sxs-lookup"><span data-stu-id="5a356-264">Summary</span></span>

<span data-ttu-id="5a356-265">数据丢失防护策略对于所有类型的组织都很有用。</span><span class="sxs-lookup"><span data-stu-id="5a356-265">Data loss prevention policies are useful for organizations of all types.</span></span> <span data-ttu-id="5a356-266">测试某些 DLP 策略是一项低风险练习，因为您可以控制策略提示、最终用户替代和事件报告等内容。</span><span class="sxs-lookup"><span data-stu-id="5a356-266">Testing some DLP policies is a low risk exercise due to the control you have over things like policy tips, end user overrides, and incident reports.</span></span> <span data-ttu-id="5a356-267">您可以静默测试某些 DLP 策略以查看组织中已经发生哪种类型的冲突，然后制定低误报率的策略，就允许和不允许的情况向用户进行指导，然后将 DLP 策略推出到组织。</span><span class="sxs-lookup"><span data-stu-id="5a356-267">You can quietly test some DLP policies to see what type of violations are already occurring in your organization, and then craft policies with low false positive rates, educate your users on what is allowed and not allowed, and then roll out your DLP policies to the organization.</span></span>