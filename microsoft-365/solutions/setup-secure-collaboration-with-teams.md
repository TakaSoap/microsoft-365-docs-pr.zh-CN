---
title: 使用 Microsoft 365 建立安全协作
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-collaboration
- m365solution-securecollab
- m365solution-overview
ms.custom:
- M365solutions
- seo-marvel-jun2020
f1.keywords: NOCSH
description: 了解如何在 Teams 中设置安全内容协作，以基于数据的敏感度保护数据。
ms.openlocfilehash: c92dc6dbf62d3fa0cb00307447b3d5a793830394
ms.sourcegitcommit: a62ac3c01ba700a51b78a647e2301f27ac437c5a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/12/2021
ms.locfileid: "50233852"
---
# <a name="set-up-secure-collaboration-with-microsoft-365"></a><span data-ttu-id="32fd2-103">使用 Microsoft 365 建立安全协作</span><span class="sxs-lookup"><span data-stu-id="32fd2-103">Set up secure collaboration with Microsoft 365</span></span>

<span data-ttu-id="32fd2-104">能够与合适的人员轻松共享信息，同时防止过度共享是组织取得成功的关键。</span><span class="sxs-lookup"><span data-stu-id="32fd2-104">Being able to easily share information with the right people while preventing oversharing is key to an organization's success.</span></span> <span data-ttu-id="32fd2-105">这包括能够仅与应有权访问敏感数据的人安全地共享敏感数据。</span><span class="sxs-lookup"><span data-stu-id="32fd2-105">This includes being able to share sensitive data safely with only those who should have access to it.</span></span> <span data-ttu-id="32fd2-106">根据项目的不同，这可能包括与组织外部人员共享敏感数据。</span><span class="sxs-lookup"><span data-stu-id="32fd2-106">Depending on the project, this might include sharing sensitive data with people outside your organization.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWxMmL?autoplay=false]

<span data-ttu-id="32fd2-107">此协作解决方案指南包括两个可帮助你的组件：</span><span class="sxs-lookup"><span data-stu-id="32fd2-107">This collaboration solution guidance includes two components to help you:</span></span>
- <span data-ttu-id="32fd2-108">为每个项目部署具有正确保护级别的 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="32fd2-108">Deploy Microsoft Teams with the right level of protection for each project</span></span>
- <span data-ttu-id="32fd2-109">使用每个项目的适当安全设置配置外部共享</span><span class="sxs-lookup"><span data-stu-id="32fd2-109">Configure external sharing with appropriate security settings for each project</span></span>

![部署具有适当保护的 Teams，并配置具有适当安全设置的外部共享](..\media\solutions-architecture-center\secure-collaboration-overview.png)

<span data-ttu-id="32fd2-111">如果通用且易于使用的内容协作工具不可用，用户通常通过电子邮件进行协作。</span><span class="sxs-lookup"><span data-stu-id="32fd2-111">If versatile and easy-to-use content collaboration tools aren't available, users will often collaborate by emailing documents.</span></span> <span data-ttu-id="32fd2-112">这是一种繁琐且容易出错的协作方法，并且会增加信息共享不当的风险。</span><span class="sxs-lookup"><span data-stu-id="32fd2-112">This is a tedious and error-prone method of collaboration, and can increase the risk of inappropriate sharing of information.</span></span> <span data-ttu-id="32fd2-113">如果用户发现共享信息太困难，他们可能会恢复为使用不受 IT 监管的消费者产品。</span><span class="sxs-lookup"><span data-stu-id="32fd2-113">If people find sharing information too difficult, they could revert to using consumer products that are not governed by IT.</span></span> <span data-ttu-id="32fd2-114">这会带来更大的风险。</span><span class="sxs-lookup"><span data-stu-id="32fd2-114">This can pose an even greater risk.</span></span>

<span data-ttu-id="32fd2-115">借助 Microsoft 365，可以使用各种配置部署 Teams，帮助：</span><span class="sxs-lookup"><span data-stu-id="32fd2-115">With Microsoft 365, you can deploy Teams with a variety of configurations that help:</span></span>

- <span data-ttu-id="32fd2-116">保护知识产权</span><span class="sxs-lookup"><span data-stu-id="32fd2-116">Protect your intellectual property</span></span>
- <span data-ttu-id="32fd2-117">实现轻松协作</span><span class="sxs-lookup"><span data-stu-id="32fd2-117">Enable easy collaboration</span></span>
- <span data-ttu-id="32fd2-118">在安全性和可用性之间实现平衡，提高用户满意度并降低卷影 IT 的风险</span><span class="sxs-lookup"><span data-stu-id="32fd2-118">Create a balance between security and usability that increases user satisfaction and reduces the risk of shadow IT</span></span>

<span data-ttu-id="32fd2-119">大多数组织都有各种信息，如果信息共享不当，则其敏感度和业务影响程度各不相同。</span><span class="sxs-lookup"><span data-stu-id="32fd2-119">Most organizations have a variety of information, with varying degrees of sensitivity and varying degrees of business impact if the information is inappropriately shared.</span></span> <span data-ttu-id="32fd2-120">根据给定信息的敏感度，您可能需要允许与以下项共享：</span><span class="sxs-lookup"><span data-stu-id="32fd2-120">Depending on the sensitivity of a given piece of information, you may want to allow sharing with:</span></span>

- <span data-ttu-id="32fd2-121">任何 (未经身份验证) </span><span class="sxs-lookup"><span data-stu-id="32fd2-121">Anyone (unauthenticated)</span></span>
- <span data-ttu-id="32fd2-122">组织内部人员</span><span class="sxs-lookup"><span data-stu-id="32fd2-122">People inside the organization</span></span>
- <span data-ttu-id="32fd2-123">组织内部的特定人员</span><span class="sxs-lookup"><span data-stu-id="32fd2-123">Specific people inside the organization</span></span>
- <span data-ttu-id="32fd2-124">组织内外的特定人员</span><span class="sxs-lookup"><span data-stu-id="32fd2-124">Specific people inside and outside the organization</span></span>

<span data-ttu-id="32fd2-125">营销简介等信息旨在广泛在组织外部共享。</span><span class="sxs-lookup"><span data-stu-id="32fd2-125">Information such as marketing brochures are meant for sharing broadly outside the organization.</span></span> <span data-ttu-id="32fd2-126">菜单等信息不用于外部共享，但如果在外部共享，则不会影响业务。</span><span class="sxs-lookup"><span data-stu-id="32fd2-126">Information such as cafeteria menus aren't meant for external sharing, but would have no business impact if they were shared externally.</span></span> <span data-ttu-id="32fd2-127">这些类型的信息几乎不需要保护或不需要保护。</span><span class="sxs-lookup"><span data-stu-id="32fd2-127">These types of information need little or no protection.</span></span>

<span data-ttu-id="32fd2-128">这些相同的营销手册在开发期间可能只能在组织内部共享。</span><span class="sxs-lookup"><span data-stu-id="32fd2-128">Those same marketing brochures, while under development, might only be shared inside the organization.</span></span> <span data-ttu-id="32fd2-129">在这种情况下，Teams 中的默认共享设置可能就足够了。</span><span class="sxs-lookup"><span data-stu-id="32fd2-129">In this case, the default sharing settings in Teams may be sufficient.</span></span>

<span data-ttu-id="32fd2-130">有关正在开发中的新产品的信息可能被视为敏感，即使在组织内部。</span><span class="sxs-lookup"><span data-stu-id="32fd2-130">Information about a new product that is under development might be considered sensitive, even within the organization.</span></span> <span data-ttu-id="32fd2-131">在这种情况下，可能适合使用更大程度的保护。</span><span class="sxs-lookup"><span data-stu-id="32fd2-131">A greater degree of protection might be appropriate in this case.</span></span> <span data-ttu-id="32fd2-132">例如，您可以限制特定团队成员对此信息的访问。</span><span class="sxs-lookup"><span data-stu-id="32fd2-132">You could restrict access to this information to members of a specific team, for example.</span></span> <span data-ttu-id="32fd2-133">根据项目的不同，您可能需要与组织外部人员（如供应商或合作伙伴组织）进行协作。</span><span class="sxs-lookup"><span data-stu-id="32fd2-133">Depending on the project, you may need to collaborate with people outside your organization, such as a vendor or partner organization.</span></span>

<span data-ttu-id="32fd2-134">对于对组织的成功至关重要的信息，或者具有严格的安全或合规性要求的信息，可能需要更高级别的保护。</span><span class="sxs-lookup"><span data-stu-id="32fd2-134">Information that is critical to your organization's success, or has stringent security or compliance requirements might require even greater levels of protection.</span></span>

![风险范围从低 (发行) 高 (敏感业务数据) ](../media/solutions-architecture-center/SecureCollaboration-SensitivityAndBusinessImpactofSharing-fromVisio.png)

<span data-ttu-id="32fd2-136">对于上述所有方案，可以使用 Microsoft Teams 中的团队来存储、共享和协作处理信息。</span><span class="sxs-lookup"><span data-stu-id="32fd2-136">For all the scenarios noted above, you can use teams in Microsoft Teams to store, share, and collaborate on the information.</span></span> 

<span data-ttu-id="32fd2-137">若要配置安全协作，请使用这些 Microsoft 365 功能和特性。</span><span class="sxs-lookup"><span data-stu-id="32fd2-137">To configure secure collaboration, you use these Microsoft 365 capabilities and features.</span></span>

| <span data-ttu-id="32fd2-138">产品或组件</span><span class="sxs-lookup"><span data-stu-id="32fd2-138">Product or component</span></span> | <span data-ttu-id="32fd2-139">功能或特性</span><span class="sxs-lookup"><span data-stu-id="32fd2-139">Capability or feature</span></span> | <span data-ttu-id="32fd2-140">许可</span><span class="sxs-lookup"><span data-stu-id="32fd2-140">Licensing</span></span> |
|:-------|:-----|:-------|
| <span data-ttu-id="32fd2-141">Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="32fd2-141">Microsoft Defender for Office 365</span></span> | <span data-ttu-id="32fd2-142">SPO、OneDrive 和 Teams 的安全附件;安全文档;Teams 的安全链接</span><span class="sxs-lookup"><span data-stu-id="32fd2-142">Safe Attachments for SPO, OneDrive and Teams; Safe Documents; Safe Links for Teams</span></span>    | <span data-ttu-id="32fd2-143">Microsoft 365 E1、E3 和 E5</span><span class="sxs-lookup"><span data-stu-id="32fd2-143">Microsoft 365 E1, E3 and E5</span></span> |
| <span data-ttu-id="32fd2-144">SharePoint</span><span class="sxs-lookup"><span data-stu-id="32fd2-144">SharePoint</span></span>    | <span data-ttu-id="32fd2-145">网站和文件共享策略、网站共享权限、共享链接、访问请求、网站来宾共享设置</span><span class="sxs-lookup"><span data-stu-id="32fd2-145">Site and file sharing policies, Site sharing permissions, Sharing links, Access requests, Site guest sharing settings</span></span> | <span data-ttu-id="32fd2-146">Microsoft 365 E1、E3 和 E5</span><span class="sxs-lookup"><span data-stu-id="32fd2-146">Microsoft 365 E1, E3 and E5</span></span> |
| <span data-ttu-id="32fd2-147">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="32fd2-147">Microsoft Teams</span></span>   | <span data-ttu-id="32fd2-148">来宾访问、私人团队、私人频道</span><span class="sxs-lookup"><span data-stu-id="32fd2-148">Guest access, private teams, private channels</span></span> | <span data-ttu-id="32fd2-149">Microsoft 365 E1、E3 和 E5</span><span class="sxs-lookup"><span data-stu-id="32fd2-149">Microsoft 365 E1, E3 and E5</span></span> |
| <span data-ttu-id="32fd2-150">Microsoft 365 合规中心</span><span class="sxs-lookup"><span data-stu-id="32fd2-150">Microsoft 365 Compliance</span></span>  | <span data-ttu-id="32fd2-151">敏感度标签</span><span class="sxs-lookup"><span data-stu-id="32fd2-151">Sensitivity labels</span></span>    | <span data-ttu-id="32fd2-152">Microsoft 365 E3 和 E5</span><span class="sxs-lookup"><span data-stu-id="32fd2-152">Microsoft 365 E3 and E5</span></span> |

### <a name="using-teams-for-all-kinds-of-data"></a><span data-ttu-id="32fd2-153">对所有类型的数据使用 Teams</span><span class="sxs-lookup"><span data-stu-id="32fd2-153">Using Teams for all kinds of data</span></span>

<span data-ttu-id="32fd2-154">为了管理对不同敏感信息的访问，我们已为 Teams 开发了三个不同的 [保护层](configure-teams-three-tiers-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="32fd2-154">To manage access to information with different sensitivities, we've developed [three different tiers of protection for Teams](configure-teams-three-tiers-protection.md).</span></span> <span data-ttu-id="32fd2-155">您可以自定义这些层中的任意一个，以更好地满足需求或业务。</span><span class="sxs-lookup"><span data-stu-id="32fd2-155">You can customize any of these tiers to better address the needs or your business.</span></span> 

![Teams 逻辑体系结构海报缩略图](../media/solutions-architecture-center/Teams-tiers-of-protection-1.png)


<span data-ttu-id="32fd2-157">这些层（*基线*、敏感和 *高度敏感*）逐渐增加保护，以帮助防止过度共享和潜在信息泄露，如下表所示。</span><span class="sxs-lookup"><span data-stu-id="32fd2-157">These tiers - *baseline*, *sensitive*, and *highly sensitive* - gradually increase the protections that help prevent oversharing and potential information leakage, as shown in the following table.</span></span>

|-|<span data-ttu-id="32fd2-158">**基线层**</span><span class="sxs-lookup"><span data-stu-id="32fd2-158">**Baseline tier**</span></span>|<span data-ttu-id="32fd2-159">**敏感层**</span><span class="sxs-lookup"><span data-stu-id="32fd2-159">**Sensitive tier**</span></span>|<span data-ttu-id="32fd2-160">**高度敏感的层**</span><span class="sxs-lookup"><span data-stu-id="32fd2-160">**Highly sensitive tier**</span></span>|
|:--|:-----------|:------------|:-------------------|
|<span data-ttu-id="32fd2-161">公共团队或私人团队</span><span class="sxs-lookup"><span data-stu-id="32fd2-161">Public or private team</span></span>|<span data-ttu-id="32fd2-162">两者皆可</span><span class="sxs-lookup"><span data-stu-id="32fd2-162">Either</span></span>|<span data-ttu-id="32fd2-163">Private</span><span class="sxs-lookup"><span data-stu-id="32fd2-163">Private</span></span>|<span data-ttu-id="32fd2-164">Private</span><span class="sxs-lookup"><span data-stu-id="32fd2-164">Private</span></span>|
|<span data-ttu-id="32fd2-165">未经身份验证的共享</span><span class="sxs-lookup"><span data-stu-id="32fd2-165">Unauthenticated sharing</span></span>|<span data-ttu-id="32fd2-166">Blocked</span><span class="sxs-lookup"><span data-stu-id="32fd2-166">Blocked</span></span>|<span data-ttu-id="32fd2-167">Blocked</span><span class="sxs-lookup"><span data-stu-id="32fd2-167">Blocked</span></span>|<span data-ttu-id="32fd2-168">Blocked</span><span class="sxs-lookup"><span data-stu-id="32fd2-168">Blocked</span></span>|
|<span data-ttu-id="32fd2-169">文件共享</span><span class="sxs-lookup"><span data-stu-id="32fd2-169">File sharing</span></span>|<span data-ttu-id="32fd2-170">允许</span><span class="sxs-lookup"><span data-stu-id="32fd2-170">Allowed</span></span>|<span data-ttu-id="32fd2-171">允许</span><span class="sxs-lookup"><span data-stu-id="32fd2-171">Allowed</span></span>|<span data-ttu-id="32fd2-172">只有团队所有者才能共享。</span><span class="sxs-lookup"><span data-stu-id="32fd2-172">Only team owners can share.</span></span>|
|<span data-ttu-id="32fd2-173">团队成员身份</span><span class="sxs-lookup"><span data-stu-id="32fd2-173">Team membership</span></span>|<span data-ttu-id="32fd2-174">任何人都可以加入公共团队。</span><span class="sxs-lookup"><span data-stu-id="32fd2-174">Anyone can join public teams.</span></span><br><span data-ttu-id="32fd2-175">加入私人团队需要团队所有者批准。</span><span class="sxs-lookup"><span data-stu-id="32fd2-175">Team owner approval required to join private teams.</span></span>|<span data-ttu-id="32fd2-176">需要团队所有者批准才能加入。</span><span class="sxs-lookup"><span data-stu-id="32fd2-176">Team owner approval required to join.</span></span>|<span data-ttu-id="32fd2-177">需要团队所有者批准才能加入。</span><span class="sxs-lookup"><span data-stu-id="32fd2-177">Team owner approval required to join.</span></span>|
|<span data-ttu-id="32fd2-178">文档加密</span><span class="sxs-lookup"><span data-stu-id="32fd2-178">Document encryption</span></span>|||<span data-ttu-id="32fd2-179">与敏感度标签一起提供</span><span class="sxs-lookup"><span data-stu-id="32fd2-179">Available with sensitivity label</span></span>|
|<span data-ttu-id="32fd2-180">来宾共享</span><span class="sxs-lookup"><span data-stu-id="32fd2-180">Guest sharing</span></span>|<span data-ttu-id="32fd2-181">允许</span><span class="sxs-lookup"><span data-stu-id="32fd2-181">Allowed</span></span>|<span data-ttu-id="32fd2-182">允许或阻止</span><span class="sxs-lookup"><span data-stu-id="32fd2-182">Can be allowed or blocked</span></span>|<span data-ttu-id="32fd2-183">允许或阻止</span><span class="sxs-lookup"><span data-stu-id="32fd2-183">Can be allowed or blocked</span></span>|
|<span data-ttu-id="32fd2-184">非托管设备</span><span class="sxs-lookup"><span data-stu-id="32fd2-184">Unmanaged devices</span></span>|<span data-ttu-id="32fd2-185">无限制</span><span class="sxs-lookup"><span data-stu-id="32fd2-185">No restriction</span></span>|<span data-ttu-id="32fd2-186">仅 Web 访问</span><span class="sxs-lookup"><span data-stu-id="32fd2-186">Web-only access</span></span>|<span data-ttu-id="32fd2-187">Blocked</span><span class="sxs-lookup"><span data-stu-id="32fd2-187">Blocked</span></span>|

<span data-ttu-id="32fd2-188">配置这些层涉及：</span><span class="sxs-lookup"><span data-stu-id="32fd2-188">Configuring these tiers involves:</span></span>

- <span data-ttu-id="32fd2-189">在 Teams 中配置来宾访问和专用频道的设置</span><span class="sxs-lookup"><span data-stu-id="32fd2-189">Configuring settings in Teams for guest access and private channels</span></span>
- <span data-ttu-id="32fd2-190">在团队的关联 SharePoint 网站中为内部共享和来宾共享、访问请求和共享链接配置设置</span><span class="sxs-lookup"><span data-stu-id="32fd2-190">Configuring settings in a team's associated SharePoint site for internal and guest sharing, access requests, and sharing links</span></span>
- <span data-ttu-id="32fd2-191">对于 *敏感和\*\*高度敏感的* 层，配置敏感度标签以对团队进行分类，并控制来宾共享和从非托管设备访问</span><span class="sxs-lookup"><span data-stu-id="32fd2-191">For the *sensitive* and *highly sensitive* tiers, configuring sensitivity labels to classify the teams, and control guest sharing and access from unmanaged devices</span></span>
- <span data-ttu-id="32fd2-192">对于 *高度敏感的* 层，配置敏感度标签以加密应用它的文档</span><span class="sxs-lookup"><span data-stu-id="32fd2-192">For the *highly sensitive* tier, configuring a sensitivity label to encrypt the documents to which it is applied</span></span>

<span data-ttu-id="32fd2-193">从基线层开始，然后根据需要添加使用敏感和 *高度敏感* 层以帮助保护组织中信息的团队。 </span><span class="sxs-lookup"><span data-stu-id="32fd2-193">Start with the baseline tier, and then add teams that use the *sensitive* and *highly sensitive* tiers as needed to help protect the information in your organization.</span></span> <span data-ttu-id="32fd2-194">请参阅以下资源开始：</span><span class="sxs-lookup"><span data-stu-id="32fd2-194">See these resources to get started:</span></span>

- [<span data-ttu-id="32fd2-195">配置具有基线保护的团队</span><span class="sxs-lookup"><span data-stu-id="32fd2-195">Configure teams with baseline protection</span></span>](configure-teams-baseline-protection.md)
- [<span data-ttu-id="32fd2-196">配置具有敏感数据保护的团队</span><span class="sxs-lookup"><span data-stu-id="32fd2-196">Configure teams with protection for sensitive data</span></span>](configure-teams-sensitive-protection.md)
- [<span data-ttu-id="32fd2-197">配置具有高度敏感数据保护的团队</span><span class="sxs-lookup"><span data-stu-id="32fd2-197">Configure teams with protection for highly sensitive data</span></span>](configure-teams-highly-sensitive-protection.md)

<span data-ttu-id="32fd2-198">如果您的高度敏感项目需要额外保护，甚至无需在组织内部共享，您可以配置一个使用自己的敏感度标签对文件进行加密的团队，以便只有团队成员才能读取这些文件。</span><span class="sxs-lookup"><span data-stu-id="32fd2-198">If you have a highly sensitive project that requires additional protection from sharing even within your organization, you can configure a team that uses its own sensitivity label to encrypt files so that only team members can read them.</span></span> <span data-ttu-id="32fd2-199">有关详细信息 [，请参阅配置具有安全隔离](secure-teams-security-isolation.md) 的团队。</span><span class="sxs-lookup"><span data-stu-id="32fd2-199">See [Configure a team with security isolation](secure-teams-security-isolation.md) for details.</span></span>

### <a name="sharing-with-people-outside-your-organization"></a><span data-ttu-id="32fd2-200">与组织外部人员共享</span><span class="sxs-lookup"><span data-stu-id="32fd2-200">Sharing with people outside your organization</span></span>

<span data-ttu-id="32fd2-201">你可能需要 [与组织外部人员共享任何敏感度的信息](collaborate-with-people-outside-your-organization.md)。</span><span class="sxs-lookup"><span data-stu-id="32fd2-201">You may need to [share information of any sensitivity with people outside your organization](collaborate-with-people-outside-your-organization.md).</span></span> <span data-ttu-id="32fd2-202">这可能包括与单个人员共享单个文档，到与大型合作伙伴组织或世界各地的供应商协作处理主要项目。</span><span class="sxs-lookup"><span data-stu-id="32fd2-202">This could range from sharing a single document with a single person to collaborating on a major project with a large partner organization or freelancers from around the world.</span></span> <span data-ttu-id="32fd2-203">在 Microsoft 365 中，可以轻松完成此范围的外部共享，并提供适当的安全措施来帮助保护敏感信息。</span><span class="sxs-lookup"><span data-stu-id="32fd2-203">In Microsoft 365, this range of external sharing can be done easily and with the appropriate safeguards to help protect your sensitive information.</span></span>

<span data-ttu-id="32fd2-204">这些资源将帮助您开始设置环境以与组织外部人员协作：</span><span class="sxs-lookup"><span data-stu-id="32fd2-204">These resources will help you get started with setting up your environment for collaborating with people outside your organization:</span></span>

- <span data-ttu-id="32fd2-205">[协作处理文档](collaborate-on-documents.md) 以共享文件夹的单个文件。</span><span class="sxs-lookup"><span data-stu-id="32fd2-205">[Collaborate on documents](collaborate-on-documents.md) for sharing individual files of folders.</span></span>
- <span data-ttu-id="32fd2-206">[在网站中协作](collaborate-in-site.md) 以与 SharePoint 网站中的来宾协作。</span><span class="sxs-lookup"><span data-stu-id="32fd2-206">[Collaborate in a site](collaborate-in-site.md) for collaborating with guests in a SharePoint site.</span></span>
- <span data-ttu-id="32fd2-207">[作为团队进行协作](collaborate-as-team.md) ，与团队中的来宾协作。</span><span class="sxs-lookup"><span data-stu-id="32fd2-207">[Collaborate as a team](collaborate-as-team.md) for collaborating with guests in a team.</span></span>

<span data-ttu-id="32fd2-208">根据共享信息的敏感度，您可以添加安全措施以帮助防止过度共享。</span><span class="sxs-lookup"><span data-stu-id="32fd2-208">Depending on the sensitivity of the information being shared, you can add safeguards to help prevent oversharing.</span></span> <span data-ttu-id="32fd2-209">这些资源将帮助您设置组织所需的保护：</span><span class="sxs-lookup"><span data-stu-id="32fd2-209">These resources will help you set up the protections that you need for your organization:</span></span>

- [<span data-ttu-id="32fd2-210">有关与未经认证用户共享文件和文件夹的最佳做法</span><span class="sxs-lookup"><span data-stu-id="32fd2-210">Best practices for sharing files and folders with unauthenticated users</span></span>](best-practices-anonymous-sharing.md)
- [<span data-ttu-id="32fd2-211">在与组织外人员共享文件时限制意外公开信息</span><span class="sxs-lookup"><span data-stu-id="32fd2-211">Limit accidental exposure to files when sharing with people outside your organization</span></span>](share-limit-accidental-exposure.md)
- [<span data-ttu-id="32fd2-212">创建安全的来宾共享环境</span><span class="sxs-lookup"><span data-stu-id="32fd2-212">Create a secure guest sharing environment</span></span>](create-secure-guest-sharing-environment.md)

<span data-ttu-id="32fd2-213">如果你有合作伙伴组织的主要项目，可以使用 Azure 权利管理来管理为该项目设置的团队中的来自该组织的来宾。</span><span class="sxs-lookup"><span data-stu-id="32fd2-213">If you have a major project with a partner organization, you can use Azure Entitlement Management to manage the guests from that organization in a team that you set up for the project.</span></span> <span data-ttu-id="32fd2-214">有关详细信息[，请参阅创建包含托管来宾的 B2B Extranet。](b2b-extranet.md)</span><span class="sxs-lookup"><span data-stu-id="32fd2-214">See [Create a B2B extranet with managed guests](b2b-extranet.md) for details.</span></span>

## <a name="deploy-the-secure-collaboration-solution"></a><span data-ttu-id="32fd2-215">部署安全协作解决方案</span><span class="sxs-lookup"><span data-stu-id="32fd2-215">Deploy the secure collaboration solution</span></span>

<span data-ttu-id="32fd2-216">准备好部署此解决方案后，继续执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="32fd2-216">When you're ready to deploy this solution, continue with these steps:</span></span>
1. <span data-ttu-id="32fd2-217">配置 [Teams 的三种不同保护层](configure-teams-three-tiers-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="32fd2-217">Configure the [three different tiers of protection for Teams](configure-teams-three-tiers-protection.md).</span></span>
2. <span data-ttu-id="32fd2-218">配置用于 [与组织外部人员共享任何敏感度信息的设置](collaborate-with-people-outside-your-organization.md)。</span><span class="sxs-lookup"><span data-stu-id="32fd2-218">Configure settings for [sharing information of any sensitivity with people outside your organization](collaborate-with-people-outside-your-organization.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="32fd2-219">另请参阅</span><span class="sxs-lookup"><span data-stu-id="32fd2-219">See also</span></span>

[<span data-ttu-id="32fd2-220">Microsoft 365 安全中心文档</span><span class="sxs-lookup"><span data-stu-id="32fd2-220">Microsoft 365 security documentation</span></span>](https://docs.microsoft.com/microsoft-365/security)

[<span data-ttu-id="32fd2-221">Microsoft 365 合规性文档</span><span class="sxs-lookup"><span data-stu-id="32fd2-221">Microsoft 365 compliance documentation</span></span>](https://docs.microsoft.com/microsoft-365/compliance)

[<span data-ttu-id="32fd2-222">欢迎使用 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="32fd2-222">Welcome to Microsoft Teams</span></span>](https://docs.microsoft.com/MicrosoftTeams/Teams-overview)
