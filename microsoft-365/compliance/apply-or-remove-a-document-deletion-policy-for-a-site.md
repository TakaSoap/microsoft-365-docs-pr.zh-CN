---
title: 应用或删除网站的文件删除策略
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: 6/29/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- SPO160
- MOE150
- MET150
ms.assetid: e3e92668-f9b2-46ee-8e5e-c623870588b6
ms.custom:
- seo-marvel-apr2020
description: 了解如何在 Office 365 网站集中创建、删除和管理文档删除策略。
ms.openlocfilehash: 7a9cbec25349de02da35f0aaf0cc206774a9b59a
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/05/2020
ms.locfileid: "44034336"
---
# <a name="apply-or-remove-a-document-deletion-policy-for-a-site"></a><span data-ttu-id="094cd-103">应用或删除网站的文件删除策略</span><span class="sxs-lookup"><span data-stu-id="094cd-103">Apply or remove a document deletion policy for a site</span></span>

<span data-ttu-id="094cd-104">组织通常受法规遵从性、法律或其他法规要求，这些法规要求他们在特定时间段内保留文档。</span><span class="sxs-lookup"><span data-stu-id="094cd-104">Organizations are often subject to compliance, legal, or other regulations that require them to retain documents for a certain period of time.</span></span> <span data-ttu-id="094cd-105">不过，如果文档的保留时间长于要求时间，则会给组织带来法律风险。</span><span class="sxs-lookup"><span data-stu-id="094cd-105">However, retaining documents for longer than required can expose the organization to legal risk.</span></span> <span data-ttu-id="094cd-106">出于此原因，您的组织可能已为网站&mdash;创建了文档删除策略。例如，可能需要在创建一般业务文档五年后再将其删除。</span><span class="sxs-lookup"><span data-stu-id="094cd-106">For this reason, your organization may have created a document deletion policy for your site&mdash;for example, general business documents might be required to be deleted five years after they were created.</span></span>
  
<span data-ttu-id="094cd-107">根据组织的情况，文件删除策略可能是：</span><span class="sxs-lookup"><span data-stu-id="094cd-107">Depending on your organization, a document deletion policy might be:</span></span>
  
- <span data-ttu-id="094cd-108">**强制**网站所有者无法退出强制性策略，该策略会自动应用于网站。</span><span class="sxs-lookup"><span data-stu-id="094cd-108">**Mandatory** A site owner can't opt out of a mandatory policy, which is automatically applied to the site.</span></span> 
    
- <span data-ttu-id="094cd-109">**默认** 默认策略自动应用于网站，但网站所有者可以：</span><span class="sxs-lookup"><span data-stu-id="094cd-109">**Default** A default policy is automatically applied to a site, but a site owner can:</span></span> 
    
  - <span data-ttu-id="094cd-110">选择其他策略（如果可用）。</span><span class="sxs-lookup"><span data-stu-id="094cd-110">Choose another policy if available.</span></span>
    
  - <span data-ttu-id="094cd-111">如果该策略与网站中的内容不相关，则将其完全退出。</span><span class="sxs-lookup"><span data-stu-id="094cd-111">Opt out of the policy entirely if it isn't relevant to the content in the site.</span></span>
    
- <span data-ttu-id="094cd-112">**既不强制也不是默认** 在这种情况下，没有策略会自动应用于网站，并且网站所有者需要执行操作来应用一个策略。</span><span class="sxs-lookup"><span data-stu-id="094cd-112">**Neither mandatory nor default** In this case, no policy is automatically applied to the site, and the site owner needs to take action to apply one.</span></span> 
    
<span data-ttu-id="094cd-113">文档删除策略可能包含多个规则&mdash;例如，一个规则可能会在创建文档一年后将其删除一年，但另一条规则可能会在最后一次修改文档后一年的时间内指明删除文档。</span><span class="sxs-lookup"><span data-stu-id="094cd-113">A document deletion policy may contain more than one rule&mdash;for example, one rule might say delete documents one year after they were created, but another rule might say delete documents one year after they were last modified.</span></span> <span data-ttu-id="094cd-114">如果策略包含多个规则，则可以选择最适用于您的网站的规则。</span><span class="sxs-lookup"><span data-stu-id="094cd-114">If a policy contains more than one rule, you can select the rule that best applies to your site.</span></span> <span data-ttu-id="094cd-115">删除规则将应用于网站中的所有库。</span><span class="sxs-lookup"><span data-stu-id="094cd-115">The delete rule will be applied to all libraries within the site.</span></span> <span data-ttu-id="094cd-116">网站中同时只能有一个策略和一个规则处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="094cd-116">Only one policy and one rule can be active in a site at one time.</span></span> <span data-ttu-id="094cd-117">与策略一样，可以将规则设置为默认值，以便在应用策略时自动应用该规则。</span><span class="sxs-lookup"><span data-stu-id="094cd-117">Like a policy, a rule can be set as default, so that it's applied automatically when the policy is applied.</span></span>
  
<span data-ttu-id="094cd-p103">最后，文件删除策略是继承的。当您为网站选择策略或规则时，所有子网站都会继承该选择，尽管子网站的所有者可以通过选择其他策略或规则来中断继承。当您选择策略或规则时，请考虑属于您网站的所有子网站的内容。</span><span class="sxs-lookup"><span data-stu-id="094cd-p103">Finally, document deletion policies are inherited. When you select a policy or rule for your site, that selection is inherited by all subsites, although an owner of a subsite can break inheritance by selecting a different policy or rule. When you select a policy or rule, consider the content of any subsites below your site.</span></span>
  
## <a name="view-the-document-deletion-policies-available-in-a-site-collection"></a><span data-ttu-id="094cd-121">查看网站集中可用的文件删除策略</span><span class="sxs-lookup"><span data-stu-id="094cd-121">View the document deletion policies available in a site collection</span></span>

<span data-ttu-id="094cd-p104">您的组织可能将不同的策略分配到不同的网站集。在网站集级别上，网站集所有者可以查看适用于该网站集的所有文件删除策略。这些策略可能在网站集模板（以及根据此模板创建的所有网站集）或此特定的网站集中可用。</span><span class="sxs-lookup"><span data-stu-id="094cd-p104">Your organization may assign different policies to different site collections. At the site collection level, an owner of a site collection can view all of the document deletion policies that are available to that site collection. The policies may have been made available to the site collection template (and therefore all site collections created from this template) or to this specific site collection.</span></span>
  
1. <span data-ttu-id="094cd-125">在网站集的首要网站中，在右上角选择 "**设置**" [齿轮图标] \> "**网站设置**"。</span><span class="sxs-lookup"><span data-stu-id="094cd-125">In the top-level site in the site collection, in the upper-right corner, choose **Settings** [gear icon] \> **Site Settings**.</span></span>
    
2. <span data-ttu-id="094cd-126">在 "**网站集管理** \> **文档删除策略**" 下。</span><span class="sxs-lookup"><span data-stu-id="094cd-126">Under **Site Collection Administration** \> **Document Deletion Policies**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="094cd-127">除非已将策略分配给网站集，否则不会显示 "**文档删除策略**" 链接。</span><span class="sxs-lookup"><span data-stu-id="094cd-127">The **Document Deletion Policies** link won't appear unless policies have been assigned to the site collection.</span></span> <span data-ttu-id="094cd-128">此外，在将策略分配给网站后，链接不会立即显示出来，在显示 "**文档删除策略**" 链接时，可能需要从策略分配到24小时。</span><span class="sxs-lookup"><span data-stu-id="094cd-128">Also, the link doesn't appear immediately after policies have been assigned to the site — it can take up to 24 hours from when the policies are assigned to when the **Document Deletion Policies** link appears.</span></span> 
  
3. <span data-ttu-id="094cd-129">在本页中，您可以查看：</span><span class="sxs-lookup"><span data-stu-id="094cd-129">On this page you can view:</span></span>
    
  - <span data-ttu-id="094cd-p106">当前分配的策略和相关规则。选择一个策略，以在右侧窗格中查看规则。</span><span class="sxs-lookup"><span data-stu-id="094cd-p106">The currently assigned policies and the associated rules. Select a policy to view the rules in the right pane.</span></span>
    
  - <span data-ttu-id="094cd-132">默认策略（若有）会在“默认”\*\*\*\* 列中显示“是”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="094cd-132">The default policy, if any, displays **Yes** in the **Default** column.</span></span> 
    
  - <span data-ttu-id="094cd-133">如果策略已分配为“强制”\*\*\*\*，则会在列表下方显示一条消息。</span><span class="sxs-lookup"><span data-stu-id="094cd-133">A message is displayed below the list if the policy has been assigned as **Mandatory**.</span></span>
    
<span data-ttu-id="094cd-p107">该列表只能查看，供网站集所有者查看所有可用的策略和规则。若要应用策略，请参阅下一节。</span><span class="sxs-lookup"><span data-stu-id="094cd-p107">This list is view only, for the site collection owner to see all of the available policies and rules. To apply a policy, see the next section.</span></span>
  
![分配给网站集的文档删除策略的视图](../media/f2c0433b-2bb5-407d-a364-ae07c9627176.png)
  
## <a name="apply-or-remove-a-document-deletion-policy-for-a-site"></a><span data-ttu-id="094cd-137">应用或删除网站的文件删除策略</span><span class="sxs-lookup"><span data-stu-id="094cd-137">Apply or remove a document deletion policy for a site</span></span>

<span data-ttu-id="094cd-138">作为网站所有者或网站集所有者，您的组织可能已创建策略，您可以将其应用到网站或选择完全退出。</span><span class="sxs-lookup"><span data-stu-id="094cd-138">As a site owner or site collection owner, your organization may have created policies that you can either apply to your site or opt out of entirely.</span></span>
  
1. <span data-ttu-id="094cd-139">在右上角，选择 "**设置**" [齿轮图标] \> "**网站设置**"。</span><span class="sxs-lookup"><span data-stu-id="094cd-139">In the upper-right corner, choose **Settings** [gear icon] \> **Site Settings**.</span></span>
    
2. <span data-ttu-id="094cd-140">在 "**网站管理** \> **文档删除策略**" 下。</span><span class="sxs-lookup"><span data-stu-id="094cd-140">Under **Site Administration** \> **Document Deletion Policies**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="094cd-141">除非已将策略分配给网站集，否则不会显示 "**文档删除策略**" 链接。</span><span class="sxs-lookup"><span data-stu-id="094cd-141">The **Document Deletion Policies** link won't appear unless policies have been assigned to the site collection.</span></span> <span data-ttu-id="094cd-142">此外，在将策略分配给网站后，链接不会立即显示出来，在显示 "**文档删除策略**" 链接时，可能需要从策略分配到24小时。</span><span class="sxs-lookup"><span data-stu-id="094cd-142">Also, the link doesn't appear immediately after policies have been assigned to the site — it can take up to 24 hours from when the policies are assigned to when the **Document Deletion Policies** link appears.</span></span> 
  
3. <span data-ttu-id="094cd-143">执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="094cd-143">Do one of the following:</span></span>
    
  - <span data-ttu-id="094cd-144">**应用策略**选择策略\>在该策略\> **保存**中选择规则。</span><span class="sxs-lookup"><span data-stu-id="094cd-144">**To apply a policy** Select a policy \> select a rule in that policy \> **Save**.</span></span>
    
    <span data-ttu-id="094cd-p109">网站中同时只能有一个策略和一个规则处于活动状态。您的组织可能提供多个策略和规则以供选择，或者仅提供一个策略或规则。</span><span class="sxs-lookup"><span data-stu-id="094cd-p109">Only one policy and one rule can be active in a site at one time. Your organization may provide several policies and rules to choose from, or only one policy or rule.</span></span>
    
    ![选择策略选项](../media/f7c7c055-fca7-4a4f-bb97-63e35a65beac.png)
  
  - <span data-ttu-id="094cd-148">**退出策略**选择**退出： Do Note Delete** \> **Save**。</span><span class="sxs-lookup"><span data-stu-id="094cd-148">**To opt out of a policy** Choose **Opt-Out: Do Note Delete** \> **Save**.</span></span>
    
    <span data-ttu-id="094cd-149">作为网站所有者，如果确定策略不适用于网站中的内容，则可以选择退出文档删除策略。</span><span class="sxs-lookup"><span data-stu-id="094cd-149">As a site owner, you can opt out of a document deletion policy if you determine that the policy isn't applicable to the content in your site.</span></span> <span data-ttu-id="094cd-150">但是，不能选择退出已标记为**强制**的策略。</span><span class="sxs-lookup"><span data-stu-id="094cd-150">However, you can't opt out of a policy that has been marked as **Mandatory**.</span></span>
    
    ![选择退出选项](../media/efac709c-bef7-4a02-a09d-5bc7d2b4ec63.png)
  
## <a name="document-deletion-policies-override-other-policies"></a><span data-ttu-id="094cd-152">文件删除策略覆盖其他策略</span><span class="sxs-lookup"><span data-stu-id="094cd-152">Document deletion policies override other policies</span></span>

<span data-ttu-id="094cd-153">网站可以使用其他策略来保留和删除内容：</span><span class="sxs-lookup"><span data-stu-id="094cd-153">A site may use other policies for retaining and deleting content:</span></span>
  
- <span data-ttu-id="094cd-154">网站集的内容类型策略。</span><span class="sxs-lookup"><span data-stu-id="094cd-154">Content type policies for the site collection.</span></span>
    
- <span data-ttu-id="094cd-155">列表或库的信息管理策略。</span><span class="sxs-lookup"><span data-stu-id="094cd-155">Information management policies for a list or library.</span></span>
    
<span data-ttu-id="094cd-156">如果您将文件删除策略应用于已使用列表或库的内容类型策略或信息管理策略的网站，则这些策略会在文件删除策略生效时被忽略。</span><span class="sxs-lookup"><span data-stu-id="094cd-156">If you apply a document deletion policy to a site that already uses content type policies or information management policies for a list or library, those policies are ignored while the document deletion policy is in effect.</span></span> <span data-ttu-id="094cd-157">如果忽略其他策略，则会看到消息 "此网站上的内容使用文档删除策略"。</span><span class="sxs-lookup"><span data-stu-id="094cd-157">If other policies are ignored, you'll see the message "Content on this site uses Document Deletion Policies".</span></span>
  
<span data-ttu-id="094cd-158">这表示您应该对网站进行规划，以仅使用针对结构化内容（信息管理策略和内容类型策略）或非结构化内容（文件删除策略）的策略，而非同时使用。</span><span class="sxs-lookup"><span data-stu-id="094cd-158">This means you should plan for a site to use only policies meant for structured content (information management policies and content type policies) or unstructured content (document deletion policies), not both.</span></span> <span data-ttu-id="094cd-159">如果您选择退出文档删除策略，则不会显示该警告，并且其他类型的策略将继续有效。</span><span class="sxs-lookup"><span data-stu-id="094cd-159">If you opt out of a document deletion policy, the warning won't be displayed and other types of policies will continue to work.</span></span>
  
<span data-ttu-id="094cd-160">网站策略不受文件删除策略的影响。</span><span class="sxs-lookup"><span data-stu-id="094cd-160">Site policies are not affected by document deletion policies.</span></span>
  
### <a name="determine-if-content-type-policies-are-being-ignored"></a><span data-ttu-id="094cd-161">确定内容类型策略是否被忽略</span><span class="sxs-lookup"><span data-stu-id="094cd-161">Determine if content type policies are being ignored</span></span>

<span data-ttu-id="094cd-162">如果您的网站曾使用内容类型策略，而您现在看到此信息，则这些策略不再有效。</span><span class="sxs-lookup"><span data-stu-id="094cd-162">If your site was using content type policies and you now see this message, those policies are no longer in effect.</span></span> <span data-ttu-id="094cd-163">若要还原内容类型策略，可以删除网站中的文档删除策略（如前面所述）（如果有选择退出选项）。</span><span class="sxs-lookup"><span data-stu-id="094cd-163">To restore the content type policies, you can remove the document deletion policy from your site, as described earlier, if there's an opt-out option available.</span></span> <span data-ttu-id="094cd-164">如果没有选项可供选择，则文档删除策略是必需的，您需要与组织中的合规性监察官联系。</span><span class="sxs-lookup"><span data-stu-id="094cd-164">If there's no option to opt out, the document deletion policy is mandatory, and you need to contact the compliance officer in your organization.</span></span>
  
1. <span data-ttu-id="094cd-165">在右上角，选择 "**设置**" [齿轮图标] \> "**网站设置**"。</span><span class="sxs-lookup"><span data-stu-id="094cd-165">In the upper-right corner, choose **Settings** [gear icon] \> **Site Settings**.</span></span>
    
2. <span data-ttu-id="094cd-166">在 "**网站管理** \> **内容类型策略模板**" 下。</span><span class="sxs-lookup"><span data-stu-id="094cd-166">Under **Site Administration** \> **Content Type Policy Templates**.</span></span>
    
    ![有关正在使用文档删除策略的网站上的警告](../media/4cc3d703-9aff-4695-9670-f78c291c0010.png)
  
### <a name="determine-if-information-management-policies-are-being-ignored"></a><span data-ttu-id="094cd-168">确定信息管理策略是否被忽略</span><span class="sxs-lookup"><span data-stu-id="094cd-168">Determine if information management policies are being ignored</span></span>

<span data-ttu-id="094cd-169">如果您的网站曾使用信息管理策略，而您现在看到此信息，则这些策略不再有效。</span><span class="sxs-lookup"><span data-stu-id="094cd-169">If your site was using information management policies and you now see this message, those policies are no longer in effect.</span></span> <span data-ttu-id="094cd-170">若要还原信息管理策略，可以删除网站中的文档删除策略（如前面所述）（如果有选择退出选项）。</span><span class="sxs-lookup"><span data-stu-id="094cd-170">To restore the information management policies, you can remove the document deletion policy from your site, as described earlier, if there's an opt-out option available.</span></span> <span data-ttu-id="094cd-171">如果没有选项可供选择，则文档删除策略是必需的，您需要与组织中的合规性监察官联系。</span><span class="sxs-lookup"><span data-stu-id="094cd-171">If there's no option to opt out, the document deletion policy is mandatory, and you need to contact the compliance officer in your organization.</span></span>
  
- <span data-ttu-id="094cd-172">对于\>列表或库，请在 "**权限和管理** \> **信息管理策略设置**" 下的 "功能区**库**" 选项卡\> **库设置** \> 。</span><span class="sxs-lookup"><span data-stu-id="094cd-172">For a list or library, on the Ribbon \> **Library** tab \> **Library Settings** \> under **Permissions and Management** \> **Information Management Policy Settings**.</span></span>
    
    ![有关正在使用文档删除策略的网站上的警告](../media/3f043057-a741-4cd8-a165-6d139b986064.png)
  
## <a name="see-also"></a><span data-ttu-id="094cd-174">另请参阅</span><span class="sxs-lookup"><span data-stu-id="094cd-174">See also</span></span>

[<span data-ttu-id="094cd-175">文档删除策略的概述</span><span class="sxs-lookup"><span data-stu-id="094cd-175">Overview of document deletion policies</span></span>](document-deletion-policies.md)
  
[<span data-ttu-id="094cd-176">创建文档删除策略</span><span class="sxs-lookup"><span data-stu-id="094cd-176">Create a document deletion policy</span></span>](create-a-document-deletion-policy.md)

