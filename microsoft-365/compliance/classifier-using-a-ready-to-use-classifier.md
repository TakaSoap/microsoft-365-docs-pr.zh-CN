---
title: 使用内置分类器（预览）
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Microsoft 365 附带了大量内置分类器，可用于在组织中标识和标记内容。 本主题介绍如何准备使用这些分类器。
ms.openlocfilehash: 2bd36ac42278cfe7b015d03caf2d9e1958908f8f
ms.sourcegitcommit: 13f28aa762e467bab8ab1e95e1917b3ac28931da
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2020
ms.locfileid: "43193500"
---
# <a name="using-a-built-in-classifier-preview"></a><span data-ttu-id="a4d3c-104">使用内置分类器（预览）</span><span class="sxs-lookup"><span data-stu-id="a4d3c-104">Using a built-in classifier (preview)</span></span>

<span data-ttu-id="a4d3c-105">Microsoft 已培训并测试了五个使用非常大的示例数据集的分类器，这有助于确定特定的内容类别。</span><span class="sxs-lookup"><span data-stu-id="a4d3c-105">Microsoft has trained and tested five classifiers using very large sample data sets, which can help to identify certain categories of content.</span></span> <span data-ttu-id="a4d3c-106">请参阅[trainable 分类器的入门（预览）](classifier-getting-started-with.md)。</span><span class="sxs-lookup"><span data-stu-id="a4d3c-106">See [Getting started with trainable classifiers (preview)](classifier-getting-started-with.md).</span></span> <span data-ttu-id="a4d3c-107">默认情况下， `Ready to use`这些分类器显示在组中。</span><span class="sxs-lookup"><span data-stu-id="a4d3c-107">These classifiers show up in the `Ready to use` group by default.</span></span>

<span data-ttu-id="a4d3c-108">Microsoft 365 附带了五个建议的内置分类器：</span><span class="sxs-lookup"><span data-stu-id="a4d3c-108">Microsoft 365 comes with five recommended built-in classifiers:</span></span>

> [!CAUTION]
> <span data-ttu-id="a4d3c-109">我们正在弃用采用**冒犯性语言**的内置分类器，因为它生成了大量误报。</span><span class="sxs-lookup"><span data-stu-id="a4d3c-109">We are deprecating the **Offensive Language** built-in classifier because it has been producing a high number of false positives.</span></span> <span data-ttu-id="a4d3c-110">请勿使用该功能，如果您当前正在使用它，则应将业务流程移出它。</span><span class="sxs-lookup"><span data-stu-id="a4d3c-110">Don't use it and if you are currently using it, you should move your business processes off of it.</span></span> <span data-ttu-id="a4d3c-111">我们建议改为使用**威胁**、**猥亵**和**骚扰**内置分类符。</span><span class="sxs-lookup"><span data-stu-id="a4d3c-111">We recommend using the **Threat**, **Profanity**, and **Harassment** built-in classifiers instead.</span></span>

- <span data-ttu-id="a4d3c-112">**恢复**：检测作为申请人个人、教育、专业资格、工作经验以及其他个人标识信息的文本帐户的项目。</span><span class="sxs-lookup"><span data-stu-id="a4d3c-112">**Resumes**: detects items that are textual accounts of an applicant's personal, educational, professional qualifications, work experience, and other personally identifying information.</span></span>
- <span data-ttu-id="a4d3c-113">**源代码**：检测包含一组由 GitHub 上的前25个使用的计算机编程语言编写的指令和语句的项。</span><span class="sxs-lookup"><span data-stu-id="a4d3c-113">**Source Code**: detects items that contain a set of instructions and statements written in the top 25 used computer programming languages on GitHub.</span></span>

|<span data-ttu-id="a4d3c-114">语言名称</span><span class="sxs-lookup"><span data-stu-id="a4d3c-114">language name</span></span>|||||
|---------|---------|---------|---------|---------|
|<span data-ttu-id="a4d3c-115">ActionScript</span><span class="sxs-lookup"><span data-stu-id="a4d3c-115">ActionScript</span></span>|<span data-ttu-id="a4d3c-116">C</span><span class="sxs-lookup"><span data-stu-id="a4d3c-116">C</span></span>        |<span data-ttu-id="a4d3c-117">C#</span><span class="sxs-lookup"><span data-stu-id="a4d3c-117">C#</span></span>       |<span data-ttu-id="a4d3c-118">C</span><span class="sxs-lookup"><span data-stu-id="a4d3c-118">C++</span></span>     |<span data-ttu-id="a4d3c-119">Clojure</span><span class="sxs-lookup"><span data-stu-id="a4d3c-119">Clojure</span></span>  |
|<span data-ttu-id="a4d3c-120">CoffeeScript</span><span class="sxs-lookup"><span data-stu-id="a4d3c-120">CoffeeScript</span></span>|<span data-ttu-id="a4d3c-121">CSS</span><span class="sxs-lookup"><span data-stu-id="a4d3c-121">CSS</span></span>     |<span data-ttu-id="a4d3c-122">转到</span><span class="sxs-lookup"><span data-stu-id="a4d3c-122">Go</span></span>       |<span data-ttu-id="a4d3c-123">Haskell</span><span class="sxs-lookup"><span data-stu-id="a4d3c-123">Haskell</span></span> |<span data-ttu-id="a4d3c-124">HTML</span><span class="sxs-lookup"><span data-stu-id="a4d3c-124">HTML</span></span>     |
|<span data-ttu-id="a4d3c-125">Java</span><span class="sxs-lookup"><span data-stu-id="a4d3c-125">Java</span></span>     |<span data-ttu-id="a4d3c-126">JavaScript</span><span class="sxs-lookup"><span data-stu-id="a4d3c-126">JavaScript</span></span>|<span data-ttu-id="a4d3c-127">Lua</span><span class="sxs-lookup"><span data-stu-id="a4d3c-127">Lua</span></span>      |<span data-ttu-id="a4d3c-128">MATLAB</span><span class="sxs-lookup"><span data-stu-id="a4d3c-128">MATLAB</span></span>   |<span data-ttu-id="a4d3c-129">Objective-C</span><span class="sxs-lookup"><span data-stu-id="a4d3c-129">Objective-C</span></span>|
|<span data-ttu-id="a4d3c-130">编写</span><span class="sxs-lookup"><span data-stu-id="a4d3c-130">Perl</span></span>     |<span data-ttu-id="a4d3c-131">PHP</span><span class="sxs-lookup"><span data-stu-id="a4d3c-131">PHP</span></span>      |<span data-ttu-id="a4d3c-132">Python</span><span class="sxs-lookup"><span data-stu-id="a4d3c-132">Python</span></span>   |<span data-ttu-id="a4d3c-133">R</span><span class="sxs-lookup"><span data-stu-id="a4d3c-133">R</span></span>        |<span data-ttu-id="a4d3c-134">Ruby</span><span class="sxs-lookup"><span data-stu-id="a4d3c-134">Ruby</span></span>     |
|<span data-ttu-id="a4d3c-135">Scala</span><span class="sxs-lookup"><span data-stu-id="a4d3c-135">Scala</span></span>    |<span data-ttu-id="a4d3c-136">命令行管理程序</span><span class="sxs-lookup"><span data-stu-id="a4d3c-136">Shell</span></span>    |<span data-ttu-id="a4d3c-137">反应</span><span class="sxs-lookup"><span data-stu-id="a4d3c-137">Swift</span></span>    |<span data-ttu-id="a4d3c-138">Tex</span><span class="sxs-lookup"><span data-stu-id="a4d3c-138">Tex</span></span>      |<span data-ttu-id="a4d3c-139">Vim 脚本</span><span class="sxs-lookup"><span data-stu-id="a4d3c-139">Vim Script</span></span>|

- <span data-ttu-id="a4d3c-140">**骚扰**：根据以下特性，检测与针对一个或多个用户的攻击性行为相关的冒犯性语言文本项的特定类别：种族、ethnicity、宗教、民族、性别、色情方向、年龄、残疾。</span><span class="sxs-lookup"><span data-stu-id="a4d3c-140">**Harassment**: detects a specific category of offensive language text items related to offensive conduct targeting one or multiple individuals based on the following traits: race, ethnicity, religion, national origin, gender, sexual orientation, age, disability.</span></span>
- <span data-ttu-id="a4d3c-141">**猥亵**语言：检测包含 embarrass 大多数人的表达式的冒犯性语言文本项的特定类别。</span><span class="sxs-lookup"><span data-stu-id="a4d3c-141">**Profanity**: detects a specific category of offensive language text items that contain expressions that embarrass most people.</span></span>
- <span data-ttu-id="a4d3c-142">**威胁**：检测与威胁相关的冒犯性语言文本项的特定类别，以提交暴力或对人员或财产造成物理伤害或损坏。</span><span class="sxs-lookup"><span data-stu-id="a4d3c-142">**Threat**: detects a specific category of offensive language text items related to threats to commit violence or do physical harm or damage to a person or property,</span></span>

> [!NOTE]
> <span data-ttu-id="a4d3c-143">在分类和标记工作流中使用内置分类器之前，应根据您认为适合类别的组织内容示例对其进行测试，以验证其分类预测是否符合您的预期。</span><span class="sxs-lookup"><span data-stu-id="a4d3c-143">Before using built-in classifiers in your classification and labeling workflow, you should test it against a sample of your organization's content that you feel fits the category to verify that its classification predictions meet your expectations.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a4d3c-144">请注意，冒犯性语言、骚扰、猥亵和威胁分类器仅适用于可搜索文本不详尽或完整。</span><span class="sxs-lookup"><span data-stu-id="a4d3c-144">Please note that the offensive language, harassment, profanity, and threat classifiers only work with searchable text are not exhaustive or complete.</span></span> <span data-ttu-id="a4d3c-145">此外，语言和文化标准不断变化，而在这些现实中，Microsoft 保留在决定时更新这些分类器的权利。</span><span class="sxs-lookup"><span data-stu-id="a4d3c-145">Further, language and cultural standards continually change, and in light of these realities, Microsoft reserves the right to update these classifiers in its discretion.</span></span> <span data-ttu-id="a4d3c-146">虽然分类程序可以帮助组织监视攻击性和其他使用的语言，但分类程序不会解决此类语言的后果，也不能提供组织的唯一方法来监视或响应此类语言的使用。</span><span class="sxs-lookup"><span data-stu-id="a4d3c-146">While the classifiers may assist your organization in monitoring offensive and other language used, the classifiers do not address consequences of such language and are not intended to provide your organization's sole means of monitoring or responding to the use of such language.</span></span> <span data-ttu-id="a4d3c-147">您的组织（而不是 Microsoft 或其子公司）仍负责与监控、强制执行、阻止、删除和保留预先培训的分类器所标识的任何内容相关的所有决策。</span><span class="sxs-lookup"><span data-stu-id="a4d3c-147">Your organization, and not Microsoft or its subsidiaries, remains responsible for all decisions related to monitoring, enforcement, blocking, removal and retention of any content identified by a pre-trained classifier.</span></span>

## <a name="how-to-prepare-for-and-use-a-built-in-classifier"></a><span data-ttu-id="a4d3c-148">如何准备和使用内置类元</span><span class="sxs-lookup"><span data-stu-id="a4d3c-148">How to prepare for and use a built-in classifier</span></span>

1. <span data-ttu-id="a4d3c-149">收集您认为属于内置分类符的类别（正匹配）和您要测试的类别中不应包括的（负匹配）的 "可释放测试内容" 项。</span><span class="sxs-lookup"><span data-stu-id="a4d3c-149">Collect disposable test content items that you feel belong in the category of the built-in classifier (positive matches) and ones that shouldn't be included (negative matches) in the category you're testing.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a4d3c-150">示例项目不能加密且必须为英语。</span><span class="sxs-lookup"><span data-stu-id="a4d3c-150">The sample items must not be encrypted and they must be in English.</span></span>

2. <span data-ttu-id="a4d3c-151">创建专用的 SharePoint Online 文件夹;至少等待1小时，将文件夹添加到搜索索引中。</span><span class="sxs-lookup"><span data-stu-id="a4d3c-151">Create a dedicated SharePoint Online folder; wait at least an hour for the folder to be added to the search index.</span></span> <span data-ttu-id="a4d3c-152">请记下文件夹 URL。</span><span class="sxs-lookup"><span data-stu-id="a4d3c-152">Make note of the folder URL.</span></span>

3. <span data-ttu-id="a4d3c-153">使用合规性管理或安全管理员角色访问和打开**microsoft 365 合规性中心** > **记录管理（预览）** > **标签策略**选项卡登录 microsoft 365 合规中心。</span><span class="sxs-lookup"><span data-stu-id="a4d3c-153">Sign in to Microsoft 365 compliance center with compliance admin or security admin role access and open **Microsoft 365 compliance center** > **Records management (preview)** > **Label policies** tab.</span></span>

4. <span data-ttu-id="a4d3c-154">选择`Auto-apply a label`。</span><span class="sxs-lookup"><span data-stu-id="a4d3c-154">Choose `Auto-apply a label`.</span></span>

5. <span data-ttu-id="a4d3c-155">选择`Choose a label to auto-apply`。</span><span class="sxs-lookup"><span data-stu-id="a4d3c-155">Choose `Choose a label to auto-apply`.</span></span>

6. <span data-ttu-id="a4d3c-156">选择`Create new labels`并创建一个标签，以便在此测试中直接使用。</span><span class="sxs-lookup"><span data-stu-id="a4d3c-156">Choose `Create new labels` and create a label for use just with this test.</span></span> <span data-ttu-id="a4d3c-157">执行此操作时，请`Retention`将设置为 "关闭"。</span><span class="sxs-lookup"><span data-stu-id="a4d3c-157">When you do this, leave `Retention` set to off.</span></span> <span data-ttu-id="a4d3c-158">您不希望启用任何保留或其他操作。</span><span class="sxs-lookup"><span data-stu-id="a4d3c-158">You don't want to turn on any retention or other actions.</span></span> <span data-ttu-id="a4d3c-159">在这种情况下，您将使用保留标签，只是将其用作文本标签，而不会强制执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="a4d3c-159">In this case, you'll be using the retention label simply as a text label, without enforcing any actions.</span></span> <span data-ttu-id="a4d3c-160">例如，您可以创建一个名为 "SourceCode 分类程序测试" 的保留标签，无操作，然后将该保留标签自动应用于将源代码分类器作为条件的内容。</span><span class="sxs-lookup"><span data-stu-id="a4d3c-160">For example, you can create a retention label named "SourceCode classifier test" with no actions, and then auto-apply that retention label to content that has Source code classifier as a condition.</span></span> <span data-ttu-id="a4d3c-161">若要了解有关创建保留标签的详细信息，请参阅[保留标签概述](labels.md)。</span><span class="sxs-lookup"><span data-stu-id="a4d3c-161">To learn more about creating retention labels, see [Overview of retention labels](labels.md).</span></span>
  
7. <span data-ttu-id="a4d3c-162">依次`Auto-apply a label` `Choose a label to auto-apply`选择 "" 和 ""。</span><span class="sxs-lookup"><span data-stu-id="a4d3c-162">Choose `Auto-apply a label` and then `Choose a label to auto-apply`.</span></span> <span data-ttu-id="a4d3c-163">若要了解有关使用基于条件的自动应用标签的详细信息，请参阅[根据条件自动应用保留标签策略](labels.md#applying-a-retention-label-automatically-based-on-conditions)。</span><span class="sxs-lookup"><span data-stu-id="a4d3c-163">To learn more about using condition based auto-apply a label see, [auto-apply retention label policy based on a condition](labels.md#applying-a-retention-label-automatically-based-on-conditions).</span></span>

8. <span data-ttu-id="a4d3c-164">从列表中选择您的测试标签， `Next`然后选择 ""。</span><span class="sxs-lookup"><span data-stu-id="a4d3c-164">Choose your test label from the list and choose `Next`.</span></span>

9. <span data-ttu-id="a4d3c-165">选择`Apply label to content that matches a trainable classifier`。</span><span class="sxs-lookup"><span data-stu-id="a4d3c-165">Choose `Apply label to content that matches a trainable classifier`.</span></span>

![选择类元作为条件](../media/classifier-pre-trained-apply-label-match-trainable-classifier.png)<span data-ttu-id="a4d3c-167">.</span><span class="sxs-lookup"><span data-stu-id="a4d3c-167">.</span></span>

10. <span data-ttu-id="a4d3c-168">从列表中选择分类程序，在此示例中`Source Code`</span><span class="sxs-lookup"><span data-stu-id="a4d3c-168">Choose your classifier from the list, in this case `Source Code`</span></span>

11. <span data-ttu-id="a4d3c-169">为策略命名，例如 "源代码内置分类器测试"。</span><span class="sxs-lookup"><span data-stu-id="a4d3c-169">Name the policy, for example "Source code built-in classifier test".</span></span>

12. <span data-ttu-id="a4d3c-170">选择`Let me choose specific locations`。</span><span class="sxs-lookup"><span data-stu-id="a4d3c-170">Choose `Let me choose specific locations`.</span></span>

13. <span data-ttu-id="a4d3c-171">关闭除和选择`SharePoint sites` `Choose sites`之外的所有位置。</span><span class="sxs-lookup"><span data-stu-id="a4d3c-171">Turn off all locations except `SharePoint sites` and choose `Choose sites`.</span></span>

14. <span data-ttu-id="a4d3c-172">输入步骤2中的网站的 URL。</span><span class="sxs-lookup"><span data-stu-id="a4d3c-172">Enter the URL for the site from step 2.</span></span>

15. <span data-ttu-id="a4d3c-173">完成向导并选择`Auto-apply`</span><span class="sxs-lookup"><span data-stu-id="a4d3c-173">Finish the wizard and choose `Auto-apply`</span></span>

16. <span data-ttu-id="a4d3c-174">将测试项放入专用的 SharePoint Online 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="a4d3c-174">Place the test items into the dedicated SharePoint Online folder.</span></span>

17. <span data-ttu-id="a4d3c-175">为应用标签留一个小时。</span><span class="sxs-lookup"><span data-stu-id="a4d3c-175">Allow an hour for the label to be applied.</span></span>

18. <span data-ttu-id="a4d3c-176">检查标签文档的属性以查看分类器是否包含并排除了您所需的测试内容。</span><span class="sxs-lookup"><span data-stu-id="a4d3c-176">Check the properties of the documents for the label to see if the classifier included and excluded the test content as you expected.</span></span>

19. <span data-ttu-id="a4d3c-177">查看标记的项目。</span><span class="sxs-lookup"><span data-stu-id="a4d3c-177">Review the items that were labeled.</span></span>

20. <span data-ttu-id="a4d3c-178">如果你已完成测试，请删除内容和标签策略。</span><span class="sxs-lookup"><span data-stu-id="a4d3c-178">Delete the content and the label policy if you're done with your testing.</span></span>

<span data-ttu-id="a4d3c-179">另请参阅：</span><span class="sxs-lookup"><span data-stu-id="a4d3c-179">See also:</span></span>

- [<span data-ttu-id="a4d3c-180">可训练分类器入门（预览）</span><span class="sxs-lookup"><span data-stu-id="a4d3c-180">Getting started with trainable classifiers (preview)</span></span>](classifier-getting-started-with.md)
- [<span data-ttu-id="a4d3c-181">保留标签概述</span><span class="sxs-lookup"><span data-stu-id="a4d3c-181">Overview of retention labels</span></span>](labels.md)
- [<span data-ttu-id="a4d3c-182">根据条件自动应用保留标签策略</span><span class="sxs-lookup"><span data-stu-id="a4d3c-182">Auto-apply retention label policy based on a condition</span></span>](labels.md#applying-a-retention-label-automatically-based-on-conditions)
