---
title: 使用保留标签测试内置分类器（预览）
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
ms.openlocfilehash: 2652df8d79b06d6614e2478843195e67de0a8ebb
ms.sourcegitcommit: 87eff6e8a08cec3cb0464a3b765434717584a4a9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/26/2020
ms.locfileid: "44371404"
---
# <a name="testing-built-in-classifiers-using-retention-labels-preview"></a><span data-ttu-id="f6cc5-104">使用保留标签测试内置分类器（预览）</span><span class="sxs-lookup"><span data-stu-id="f6cc5-104">Testing built-in classifiers using retention labels (preview)</span></span>

<span data-ttu-id="f6cc5-105">Microsoft 已培训并测试了五个分类器，可帮助确定特定的内容类别。</span><span class="sxs-lookup"><span data-stu-id="f6cc5-105">Microsoft has trained and tested five classifiers which can help to identify certain categories of content.</span></span> <span data-ttu-id="f6cc5-106">这些类元在 `Ready to use` 默认情况下显示在组中，并使用非常大的示例数据集进行了培训。</span><span class="sxs-lookup"><span data-stu-id="f6cc5-106">These classifiers show up in the `Ready to use` group by default and were trained using very large sample data sets.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f6cc5-107">在分类和标记工作流中使用内置分类器之前，应根据您认为适合类别的组织内容示例对其进行测试，以验证其分类预测是否符合您的预期。</span><span class="sxs-lookup"><span data-stu-id="f6cc5-107">Before using built-in classifiers in your classification and labeling workflow, you should test it against a sample of your organization's content that you feel fits the category to verify that its classification predictions meet your expectations.</span></span>

<span data-ttu-id="f6cc5-108">有关 trainable 类元的详细信息，请参阅[trainable 分类器的入门（预览）](classifier-getting-started-with.md)。</span><span class="sxs-lookup"><span data-stu-id="f6cc5-108">For more information on trainable classifiers, see [Getting started with trainable classifiers (preview)](classifier-getting-started-with.md).</span></span>

<span data-ttu-id="f6cc5-109">Microsoft 365 附带了五个建议的内置分类器：</span><span class="sxs-lookup"><span data-stu-id="f6cc5-109">Microsoft 365 comes with five recommended built-in classifiers:</span></span>

> [!CAUTION]
> <span data-ttu-id="f6cc5-110">我们正在弃用**冒犯性语言**内置分类器，因为它会生成大量误报。</span><span class="sxs-lookup"><span data-stu-id="f6cc5-110">We are deprecating the **Offensive Language** built-in classifier because it has been producing a high number of false positives.</span></span> <span data-ttu-id="f6cc5-111">请勿使用该功能，如果您当前正在使用它，则应将业务流程移出它。</span><span class="sxs-lookup"><span data-stu-id="f6cc5-111">Don't use it and if you are currently using it, you should move your business processes off of it.</span></span> <span data-ttu-id="f6cc5-112">我们建议改为使用**威胁**、**猥亵**和**骚扰**内置分类符。</span><span class="sxs-lookup"><span data-stu-id="f6cc5-112">We recommend using the **Threat**, **Profanity**, and **Harassment** built-in classifiers instead.</span></span>

- <span data-ttu-id="f6cc5-113">**恢复**：检测作为申请人个人、教育、专业资格、工作经验和其他个人身份信息的文本帐户的项目</span><span class="sxs-lookup"><span data-stu-id="f6cc5-113">**Resumes**: detects items that are textual accounts of an applicant's personal, educational, professional qualifications, work experience, and other personally identifying information</span></span>
- <span data-ttu-id="f6cc5-114">**源代码**：检测包含一组由 GitHub 上的前25个使用的计算机编程语言编写的指令和语句的项</span><span class="sxs-lookup"><span data-stu-id="f6cc5-114">**Source Code**: detects items that contain a set of instructions and statements written in the top 25 used computer programming languages on GitHub</span></span>

  |<span data-ttu-id="f6cc5-115">语言名称</span><span class="sxs-lookup"><span data-stu-id="f6cc5-115">language name</span></span>|||||
  |---------|---------|---------|---------|---------|
  |<span data-ttu-id="f6cc5-116">ActionScript</span><span class="sxs-lookup"><span data-stu-id="f6cc5-116">ActionScript</span></span>|<span data-ttu-id="f6cc5-117">C</span><span class="sxs-lookup"><span data-stu-id="f6cc5-117">C</span></span>        |<span data-ttu-id="f6cc5-118">Lc#</span><span class="sxs-lookup"><span data-stu-id="f6cc5-118">C#</span></span>       |<span data-ttu-id="f6cc5-119">C</span><span class="sxs-lookup"><span data-stu-id="f6cc5-119">C++</span></span>     |<span data-ttu-id="f6cc5-120">Clojure</span><span class="sxs-lookup"><span data-stu-id="f6cc5-120">Clojure</span></span>  |
  |<span data-ttu-id="f6cc5-121">CoffeeScript</span><span class="sxs-lookup"><span data-stu-id="f6cc5-121">CoffeeScript</span></span>|<span data-ttu-id="f6cc5-122">CSS</span><span class="sxs-lookup"><span data-stu-id="f6cc5-122">CSS</span></span>     |<span data-ttu-id="f6cc5-123">转到</span><span class="sxs-lookup"><span data-stu-id="f6cc5-123">Go</span></span>       |<span data-ttu-id="f6cc5-124">Haskell</span><span class="sxs-lookup"><span data-stu-id="f6cc5-124">Haskell</span></span> |<span data-ttu-id="f6cc5-125">HTML</span><span class="sxs-lookup"><span data-stu-id="f6cc5-125">HTML</span></span>     |
  |<span data-ttu-id="f6cc5-126">Java</span><span class="sxs-lookup"><span data-stu-id="f6cc5-126">Java</span></span>     |<span data-ttu-id="f6cc5-127">JavaScript</span><span class="sxs-lookup"><span data-stu-id="f6cc5-127">JavaScript</span></span>|<span data-ttu-id="f6cc5-128">Lua</span><span class="sxs-lookup"><span data-stu-id="f6cc5-128">Lua</span></span>      |<span data-ttu-id="f6cc5-129">MATLAB</span><span class="sxs-lookup"><span data-stu-id="f6cc5-129">MATLAB</span></span>   |<span data-ttu-id="f6cc5-130">Objective-C</span><span class="sxs-lookup"><span data-stu-id="f6cc5-130">Objective-C</span></span>|
  |<span data-ttu-id="f6cc5-131">编写</span><span class="sxs-lookup"><span data-stu-id="f6cc5-131">Perl</span></span>     |<span data-ttu-id="f6cc5-132">PHP</span><span class="sxs-lookup"><span data-stu-id="f6cc5-132">PHP</span></span>      |<span data-ttu-id="f6cc5-133">Python</span><span class="sxs-lookup"><span data-stu-id="f6cc5-133">Python</span></span>   |<span data-ttu-id="f6cc5-134">R</span><span class="sxs-lookup"><span data-stu-id="f6cc5-134">R</span></span>        |<span data-ttu-id="f6cc5-135">Ruby</span><span class="sxs-lookup"><span data-stu-id="f6cc5-135">Ruby</span></span>     |
  |<span data-ttu-id="f6cc5-136">Scala</span><span class="sxs-lookup"><span data-stu-id="f6cc5-136">Scala</span></span>    |<span data-ttu-id="f6cc5-137">命令行管理程序</span><span class="sxs-lookup"><span data-stu-id="f6cc5-137">Shell</span></span>    |<span data-ttu-id="f6cc5-138">反应</span><span class="sxs-lookup"><span data-stu-id="f6cc5-138">Swift</span></span>    |<span data-ttu-id="f6cc5-139">Tex</span><span class="sxs-lookup"><span data-stu-id="f6cc5-139">Tex</span></span>      |<span data-ttu-id="f6cc5-140">Vim 脚本</span><span class="sxs-lookup"><span data-stu-id="f6cc5-140">Vim Script</span></span>|

> [!NOTE]
> <span data-ttu-id="f6cc5-141">源代码经过培训，可在大部分文本是源代码时进行检测。</span><span class="sxs-lookup"><span data-stu-id="f6cc5-141">Source Code is trained to detect when the bulk of the text is source code.</span></span> <span data-ttu-id="f6cc5-142">它不检测与纯文本交错的源代码文本。</span><span class="sxs-lookup"><span data-stu-id="f6cc5-142">It does not detect source code text that is interspersed with plain text.</span></span>

- <span data-ttu-id="f6cc5-143">**骚扰**：根据以下特性，检测与针对一个或多个用户的攻击性行为相关的冒犯性语言文本项的特定类别：种族、ethnicity、宗教、国家/地区、性别、色情方向、年龄、残疾</span><span class="sxs-lookup"><span data-stu-id="f6cc5-143">**Harassment**: detects a specific category of offensive language text items related to offensive conduct targeting one or multiple individuals based on the following traits: race, ethnicity, religion, national origin, gender, sexual orientation, age, disability</span></span>
- <span data-ttu-id="f6cc5-144">**猥亵**语言：检测包含 embarrass 大多数人的表达式的冒犯性语言文本项的特定类别</span><span class="sxs-lookup"><span data-stu-id="f6cc5-144">**Profanity**: detects a specific category of offensive language text items that contain expressions that embarrass most people</span></span>
- <span data-ttu-id="f6cc5-145">**威胁**：检测与威胁相关的攻击性语言文本项的特定类别，以提交暴力或对人员或属性造成物理伤害或损坏</span><span class="sxs-lookup"><span data-stu-id="f6cc5-145">**Threat**: detects a specific category of offensive language text items related to threats to commit violence or do physical harm or damage to a person or property</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f6cc5-146">请注意，冒犯性语言、骚扰、猥亵和威胁分类器仅适用于可搜索文本不详尽或完整。</span><span class="sxs-lookup"><span data-stu-id="f6cc5-146">Please note that the offensive language, harassment, profanity, and threat classifiers only work with searchable text are not exhaustive or complete.</span></span> <span data-ttu-id="f6cc5-147">此外，语言和文化标准不断变化，而在这些现实中，Microsoft 保留在决定时更新这些分类器的权利。</span><span class="sxs-lookup"><span data-stu-id="f6cc5-147">Further, language and cultural standards continually change, and in light of these realities, Microsoft reserves the right to update these classifiers in its discretion.</span></span> <span data-ttu-id="f6cc5-148">虽然分类程序可以帮助组织监视攻击性和其他使用的语言，但分类程序不会解决此类语言的后果，也不能提供组织的唯一方法来监视或响应此类语言的使用。</span><span class="sxs-lookup"><span data-stu-id="f6cc5-148">While the classifiers may assist your organization in monitoring offensive and other language used, the classifiers do not address consequences of such language and are not intended to provide your organization's sole means of monitoring or responding to the use of such language.</span></span> <span data-ttu-id="f6cc5-149">您的组织（而不是 Microsoft 或其子公司）仍负责与监控、强制执行、阻止、删除和保留预先培训的分类器所标识的任何内容相关的所有决策。</span><span class="sxs-lookup"><span data-stu-id="f6cc5-149">Your organization, and not Microsoft or its subsidiaries, remains responsible for all decisions related to monitoring, enforcement, blocking, removal and retention of any content identified by a pre-trained classifier.</span></span>

## <a name="how-to-verify-that-a-built-in-classifier-will-meet-your-needs"></a><span data-ttu-id="f6cc5-150">如何验证内置分类器是否满足你的需求</span><span class="sxs-lookup"><span data-stu-id="f6cc5-150">How to verify that a built-in classifier will meet your needs</span></span>

1. <span data-ttu-id="f6cc5-151">收集您认为属于内置分类符的类别（正匹配）和您要测试的类别中不应包括的（负匹配）的 "可释放测试内容" 项。</span><span class="sxs-lookup"><span data-stu-id="f6cc5-151">Collect disposable test content items that you feel belong in the category of the built-in classifier (positive matches) and ones that shouldn't be included (negative matches) in the category you're testing.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="f6cc5-152">示例项目不能加密且必须为英语。</span><span class="sxs-lookup"><span data-stu-id="f6cc5-152">The sample items must not be encrypted and they must be in English.</span></span>

2. <span data-ttu-id="f6cc5-153">创建专用的 SharePoint Online 文件夹;至少等待1小时，将文件夹添加到搜索索引中。</span><span class="sxs-lookup"><span data-stu-id="f6cc5-153">Create a dedicated SharePoint Online folder; wait at least an hour for the folder to be added to the search index.</span></span> <span data-ttu-id="f6cc5-154">请记下文件夹 URL。</span><span class="sxs-lookup"><span data-stu-id="f6cc5-154">Make note of the folder URL.</span></span>

3. <span data-ttu-id="f6cc5-155">使用合规性管理或安全管理员角色访问和打开**microsoft 365 合规性中心**  >  **记录管理（预览）**  >  **标签策略**选项卡登录 microsoft 365 合规中心。</span><span class="sxs-lookup"><span data-stu-id="f6cc5-155">Sign in to Microsoft 365 compliance center with compliance admin or security admin role access and open **Microsoft 365 compliance center** > **Records management (preview)** > **Label policies** tab.</span></span>

4. <span data-ttu-id="f6cc5-156">选择 `Auto-apply a label` 。</span><span class="sxs-lookup"><span data-stu-id="f6cc5-156">Choose `Auto-apply a label`.</span></span>

5. <span data-ttu-id="f6cc5-157">选择 `Choose a label to auto-apply` 。</span><span class="sxs-lookup"><span data-stu-id="f6cc5-157">Choose `Choose a label to auto-apply`.</span></span>

6. <span data-ttu-id="f6cc5-158">选择 `Create new labels` 并创建一个标签，以便在此测试中直接使用。</span><span class="sxs-lookup"><span data-stu-id="f6cc5-158">Choose `Create new labels` and create a label for use just with this test.</span></span> <span data-ttu-id="f6cc5-159">执行此操作时，请将 `Retention` 设置为 `off` 。</span><span class="sxs-lookup"><span data-stu-id="f6cc5-159">When you do this, leave `Retention` set to `off`.</span></span> <span data-ttu-id="f6cc5-160">您不希望启用任何保留或其他操作。</span><span class="sxs-lookup"><span data-stu-id="f6cc5-160">You don't want to turn on any retention or other actions.</span></span> <span data-ttu-id="f6cc5-161">在这种情况下，您将使用保留标签，只是将其用作文本标签，而不会强制执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="f6cc5-161">In this case, you'll be using the retention label simply as a text label, without enforcing any actions.</span></span> <span data-ttu-id="f6cc5-162">例如，您可以创建一个名为 "SourceCode 分类程序测试" 的保留标签，无操作，然后将该保留标签自动应用于将源代码分类器作为条件的内容。</span><span class="sxs-lookup"><span data-stu-id="f6cc5-162">For example, you can create a retention label named "SourceCode classifier test" with no actions, and then auto-apply that retention label to content that has Source code classifier as a condition.</span></span> <span data-ttu-id="f6cc5-163">若要了解有关创建保留标签的详细信息，请参阅[保留标签概述](labels.md)。</span><span class="sxs-lookup"><span data-stu-id="f6cc5-163">To learn more about creating retention labels, see [Overview of retention labels](labels.md).</span></span>
  
7. <span data-ttu-id="f6cc5-164">依次选择 "" 和 "" `Auto-apply a label` `Choose a label to auto-apply` 。</span><span class="sxs-lookup"><span data-stu-id="f6cc5-164">Choose `Auto-apply a label` and then `Choose a label to auto-apply`.</span></span> <span data-ttu-id="f6cc5-165">若要了解有关使用基于条件的自动应用标签的详细信息，请参阅[根据条件自动应用保留标签策略](labels.md#applying-a-retention-label-automatically-based-on-conditions)。</span><span class="sxs-lookup"><span data-stu-id="f6cc5-165">To learn more about using condition based auto-apply a label see, [auto-apply retention label policy based on a condition](labels.md#applying-a-retention-label-automatically-based-on-conditions).</span></span>

8. <span data-ttu-id="f6cc5-166">从列表中选择您的测试标签，然后选择 "" `Next` 。</span><span class="sxs-lookup"><span data-stu-id="f6cc5-166">Choose your test label from the list and choose `Next`.</span></span>

9. <span data-ttu-id="f6cc5-167">选择 `Apply label to content that matches a trainable classifier` 。</span><span class="sxs-lookup"><span data-stu-id="f6cc5-167">Choose `Apply label to content that matches a trainable classifier`.</span></span>

   ![选择类元作为条件](../media/classifier-pre-trained-apply-label-match-trainable-classifier.png)

10. <span data-ttu-id="f6cc5-169">从列表中选择分类程序，在此示例中`Source Code`</span><span class="sxs-lookup"><span data-stu-id="f6cc5-169">Choose your classifier from the list, in this case `Source Code`</span></span>

11. <span data-ttu-id="f6cc5-170">为策略命名，例如 "源代码内置分类器测试"。</span><span class="sxs-lookup"><span data-stu-id="f6cc5-170">Name the policy, for example "Source code built-in classifier test".</span></span>

12. <span data-ttu-id="f6cc5-171">选择 `Let me choose specific locations` 。</span><span class="sxs-lookup"><span data-stu-id="f6cc5-171">Choose `Let me choose specific locations`.</span></span>

13. <span data-ttu-id="f6cc5-172">关闭除和选择之外的所有位置 `SharePoint sites` `Choose sites` 。</span><span class="sxs-lookup"><span data-stu-id="f6cc5-172">Turn off all locations except `SharePoint sites` and choose `Choose sites`.</span></span>

14. <span data-ttu-id="f6cc5-173">输入步骤2中的网站的 URL。</span><span class="sxs-lookup"><span data-stu-id="f6cc5-173">Enter the URL for the site from step 2.</span></span>

15. <span data-ttu-id="f6cc5-174">完成向导并选择`Auto-apply`</span><span class="sxs-lookup"><span data-stu-id="f6cc5-174">Finish the wizard and choose `Auto-apply`</span></span>

16. <span data-ttu-id="f6cc5-175">将测试项放入专用的 SharePoint Online 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="f6cc5-175">Place the test items into the dedicated SharePoint Online folder.</span></span>

17. <span data-ttu-id="f6cc5-176">为应用标签留一个小时。</span><span class="sxs-lookup"><span data-stu-id="f6cc5-176">Allow an hour for the label to be applied.</span></span>

18. <span data-ttu-id="f6cc5-177">检查标签文档的属性以查看分类器是否包含并排除了您所需的测试内容。</span><span class="sxs-lookup"><span data-stu-id="f6cc5-177">Check the properties of the documents for the label to see if the classifier included and excluded the test content as you expected.</span></span>

19. <span data-ttu-id="f6cc5-178">查看标记的项目。</span><span class="sxs-lookup"><span data-stu-id="f6cc5-178">Review the items that were labeled.</span></span>

20. <span data-ttu-id="f6cc5-179">如果你已完成测试，请删除内容和标签策略。</span><span class="sxs-lookup"><span data-stu-id="f6cc5-179">Delete the content and the label policy if you're done with your testing.</span></span>

<span data-ttu-id="f6cc5-180">另请参阅：</span><span class="sxs-lookup"><span data-stu-id="f6cc5-180">See also:</span></span>

- [<span data-ttu-id="f6cc5-181">可训练分类器入门（预览）</span><span class="sxs-lookup"><span data-stu-id="f6cc5-181">Getting started with trainable classifiers (preview)</span></span>](classifier-getting-started-with.md)
- [<span data-ttu-id="f6cc5-182">保留标签概述</span><span class="sxs-lookup"><span data-stu-id="f6cc5-182">Overview of retention labels</span></span>](labels.md)
- [<span data-ttu-id="f6cc5-183">根据条件自动应用保留标签策略</span><span class="sxs-lookup"><span data-stu-id="f6cc5-183">Auto-apply retention label policy based on a condition</span></span>](labels.md#applying-a-retention-label-automatically-based-on-conditions)
