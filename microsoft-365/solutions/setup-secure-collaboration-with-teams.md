---
title: 与 Microsoft 365 建立安全协作
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
ms.audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-collaboration
- M365solutions
ms.custom: ''
f1.keywords: NOCSH
description: 了解如何设置团队以根据其敏感度保护你的数据
ms.openlocfilehash: 8978c8602a00dd9c7caecc30ea4746a01680a236
ms.sourcegitcommit: 92f641cad63379bf16417854a43b16b48a71a30a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/12/2020
ms.locfileid: "44724803"
---
# <a name="set-up-secure-collaboration-with-microsoft-365"></a><span data-ttu-id="94457-103">与 Microsoft 365 建立安全协作</span><span class="sxs-lookup"><span data-stu-id="94457-103">Set up secure collaboration with Microsoft 365</span></span>

<span data-ttu-id="94457-104">能够在阻止 oversharing 的情况下轻松地与适当的人共享信息是组织成功的关键。</span><span class="sxs-lookup"><span data-stu-id="94457-104">Being able to easily share information with the right people while preventing oversharing is key to an organization's success.</span></span> <span data-ttu-id="94457-105">这包括能够安全地与仅有权访问的人共享敏感数据。</span><span class="sxs-lookup"><span data-stu-id="94457-105">This includes being able to share sensitive data safely with only those who should have access to it.</span></span> <span data-ttu-id="94457-106">这可能包括与组织外部的人员共享敏感数据，具体取决于项目。</span><span class="sxs-lookup"><span data-stu-id="94457-106">Depending on the project, this might include sharing sensitive data with people outside your organization.</span></span>

<span data-ttu-id="94457-107">本解决方案指南包括两个组件，可帮助您：</span><span class="sxs-lookup"><span data-stu-id="94457-107">This solution guidance includes two components to help you:</span></span>
- <span data-ttu-id="94457-108">部署具有针对每个项目的适当级别保护的 Microsoft 团队</span><span class="sxs-lookup"><span data-stu-id="94457-108">Deploy Microsoft Teams with the right level of protection for each project</span></span>
- <span data-ttu-id="94457-109">为每个项目配置具有适当安全设置的外部共享</span><span class="sxs-lookup"><span data-stu-id="94457-109">Configure external sharing with appropriate security settings for each project</span></span>

![使用适当的安全设置来部署具有适当保护的团队并配置外部共享](..\media\solutions-architecture-center\secure-collaboration-overview.png)

<span data-ttu-id="94457-111">如果功能丰富且易于使用的协作工具不可用，则用户通常会通过电子邮件进行协作。</span><span class="sxs-lookup"><span data-stu-id="94457-111">If versatile and easy-to-use collaboration tools aren't available, users will often collaborate by emailing documents.</span></span> <span data-ttu-id="94457-112">这是一种单调乏味且容易出错的协作方法，并且可能会增加不适当共享信息的风险。</span><span class="sxs-lookup"><span data-stu-id="94457-112">This is a tedious and error-prone method of collaboration, and can increase the risk of inappropriate sharing of information.</span></span> <span data-ttu-id="94457-113">如果人员发现共享信息过于困难，他们可以使用不受 IT 管理的消费者产品回复。</span><span class="sxs-lookup"><span data-stu-id="94457-113">If people find sharing information too difficult, they could revert to using consumer products that are not governed by IT.</span></span> <span data-ttu-id="94457-114">这可能会带来更大的风险。</span><span class="sxs-lookup"><span data-stu-id="94457-114">This can pose an even greater risk.</span></span>

<span data-ttu-id="94457-115">使用 Microsoft 365，可以部署具有多种配置的团队，以帮助：</span><span class="sxs-lookup"><span data-stu-id="94457-115">With Microsoft 365, you can deploy Teams with a variety of configurations that help:</span></span>

- <span data-ttu-id="94457-116">保护您的知识产权</span><span class="sxs-lookup"><span data-stu-id="94457-116">Protect your intellectual property</span></span>
- <span data-ttu-id="94457-117">实现轻松协作</span><span class="sxs-lookup"><span data-stu-id="94457-117">Enable easy collaboration</span></span>
- <span data-ttu-id="94457-118">在安全性和可用性之间建立平衡，以提高用户满意度并降低阴影风险</span><span class="sxs-lookup"><span data-stu-id="94457-118">Create a balance between security and usability that increases user satisfaction and reduces the risk of shadow IT</span></span>

<span data-ttu-id="94457-119">如果信息不恰当地共享，大多数组织都有各种信息，并且敏感程度各不相同，并且业务影响也各不相同。</span><span class="sxs-lookup"><span data-stu-id="94457-119">Most organizations have a variety of information, with varying degrees of sensitivity and varying degrees of business impact if the information is inappropriately shared.</span></span> <span data-ttu-id="94457-120">根据给定信息的敏感度，您可能希望允许与以下内容共享：</span><span class="sxs-lookup"><span data-stu-id="94457-120">Depending on the sensitivity of a given piece of information, you may want to allow sharing with:</span></span>

- <span data-ttu-id="94457-121">任何人（未经身份验证）</span><span class="sxs-lookup"><span data-stu-id="94457-121">Anyone (unauthenticated)</span></span>
- <span data-ttu-id="94457-122">组织内部的人员</span><span class="sxs-lookup"><span data-stu-id="94457-122">People inside the organization</span></span>
- <span data-ttu-id="94457-123">组织内的特定人员</span><span class="sxs-lookup"><span data-stu-id="94457-123">Specific people inside the organization</span></span>
- <span data-ttu-id="94457-124">组织内部和外部的特定人员</span><span class="sxs-lookup"><span data-stu-id="94457-124">Specific people inside and outside the organization</span></span>

<span data-ttu-id="94457-125">市场营销手册等信息适用于组织外部的共享。</span><span class="sxs-lookup"><span data-stu-id="94457-125">Information such as marketing brochures are meant for sharing broadly outside the organization.</span></span> <span data-ttu-id="94457-126">诸如 "自助" 的信息不是为了外部共享，而是在外部共享时不会对业务产生影响。</span><span class="sxs-lookup"><span data-stu-id="94457-126">Information such as cafeteria menus aren't meant for external sharing, but would have no business impact if they were shared externally.</span></span> <span data-ttu-id="94457-127">这些类型的信息需要很少或无保护。</span><span class="sxs-lookup"><span data-stu-id="94457-127">These types of information need little or no protection.</span></span>

<span data-ttu-id="94457-128">在开发过程中，这些相同的营销手册只能在组织内部共享。</span><span class="sxs-lookup"><span data-stu-id="94457-128">Those same marketing brochures, while under development, might only be shared inside the organization.</span></span> <span data-ttu-id="94457-129">在这种情况下，团队中的默认共享设置可能足够。</span><span class="sxs-lookup"><span data-stu-id="94457-129">In this case, the default sharing settings in Teams may be sufficient.</span></span>

<span data-ttu-id="94457-130">有关正在开发的新产品的信息可能被视为敏感，即使在组织内也是如此。</span><span class="sxs-lookup"><span data-stu-id="94457-130">Information about a new product that is under development might be considered sensitive, even within the organization.</span></span> <span data-ttu-id="94457-131">在这种情况下，可能需要更大程度的保护。</span><span class="sxs-lookup"><span data-stu-id="94457-131">A greater degree of protection might be appropriate in this case.</span></span> <span data-ttu-id="94457-132">例如，您可以将对此信息的访问限制为特定团队的成员。</span><span class="sxs-lookup"><span data-stu-id="94457-132">You could restrict access to this information to members of a specific team, for example.</span></span> <span data-ttu-id="94457-133">根据项目，您可能需要与组织外部的人员（如供应商或合作伙伴组织）进行协作。</span><span class="sxs-lookup"><span data-stu-id="94457-133">Depending on the project, you may need to collaborate with people outside your organization, such as a vendor or partner organization.</span></span>

<span data-ttu-id="94457-134">对组织成功或具有严格的安全性或合规性要求至关重要的信息可能需要更高级别的保护。</span><span class="sxs-lookup"><span data-stu-id="94457-134">Information that is critical to your organization's success, or has stringent security or compliance requirements might require even greater levels of protection.</span></span>

![从低（已发布小册子）到高（敏感业务数据）的风险范围](../media/solutions-architecture-center/SecureCollaboration-SensitivityAndBusinessImpactofSharing-fromVisio.png)

<span data-ttu-id="94457-136">对于以上所述的所有情况，可以使用 Microsoft 团队中的团队来存储、共享和协作处理信息。</span><span class="sxs-lookup"><span data-stu-id="94457-136">For all the scenarios noted above, you can use teams in Microsoft Teams to store, share, and collaborate on the information.</span></span> 

<span data-ttu-id="94457-137">若要配置安全 collabration，请使用以下 Microsoft 365 功能和功能。</span><span class="sxs-lookup"><span data-stu-id="94457-137">To configure secure collabration, you use these Microsoft 365 capabilities and features.</span></span>

| <span data-ttu-id="94457-138">产品或组件</span><span class="sxs-lookup"><span data-stu-id="94457-138">Product or component</span></span> | <span data-ttu-id="94457-139">功能或特性</span><span class="sxs-lookup"><span data-stu-id="94457-139">Capability or feature</span></span> | <span data-ttu-id="94457-140">许可</span><span class="sxs-lookup"><span data-stu-id="94457-140">Licensing</span></span> |
|:-------|:-----|:-------|
| <span data-ttu-id="94457-141">Office 365 高级威胁防护</span><span class="sxs-lookup"><span data-stu-id="94457-141">Office 365 Advanced Threat Protection</span></span> | <span data-ttu-id="94457-142">SPO、OneDrive 和团队的 ATP 安全附件;ATP 安全文档;团队的 ATP 安全链接</span><span class="sxs-lookup"><span data-stu-id="94457-142">ATP Safe Attachments for SPO, OneDrive and Teams; ATP Safe Documents; ATP Safe Links for Teams</span></span>    | <span data-ttu-id="94457-143">Microsoft 365 E1、E3 和 E5</span><span class="sxs-lookup"><span data-stu-id="94457-143">Microsoft 365 E1, E3 and E5</span></span> |
| <span data-ttu-id="94457-144">SharePoint</span><span class="sxs-lookup"><span data-stu-id="94457-144">SharePoint</span></span>    | <span data-ttu-id="94457-145">网站和文件共享策略、网站共享权限、共享链接、访问请求、网站来宾共享设置</span><span class="sxs-lookup"><span data-stu-id="94457-145">Site and file sharing policies, Site sharing permissions, Sharing links, Access requests, Site guest sharing settings</span></span> | <span data-ttu-id="94457-146">Microsoft 365 E1、E3 和 E5</span><span class="sxs-lookup"><span data-stu-id="94457-146">Microsoft 365 E1, E3 and E5</span></span> |
| <span data-ttu-id="94457-147">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="94457-147">Microsoft Teams</span></span>   | <span data-ttu-id="94457-148">来宾访问、专用团队、专用频道</span><span class="sxs-lookup"><span data-stu-id="94457-148">Guest access, private teams, private channels</span></span> | <span data-ttu-id="94457-149">Microsoft 365 E1、E3 和 E5</span><span class="sxs-lookup"><span data-stu-id="94457-149">Microsoft 365 E1, E3 and E5</span></span> |
| <span data-ttu-id="94457-150">Microsoft 365 合规中心</span><span class="sxs-lookup"><span data-stu-id="94457-150">Microsoft 365 Compliance</span></span>  | <span data-ttu-id="94457-151">敏感度标签</span><span class="sxs-lookup"><span data-stu-id="94457-151">Sensitivity labels</span></span>    | <span data-ttu-id="94457-152">Microsoft 365 E3 和 E5</span><span class="sxs-lookup"><span data-stu-id="94457-152">Microsoft 365 E3 and E5</span></span> |

### <a name="using-teams-for-all-kinds-of-data"></a><span data-ttu-id="94457-153">对所有类型的数据使用团队</span><span class="sxs-lookup"><span data-stu-id="94457-153">Using Teams for all kinds of data</span></span>

<span data-ttu-id="94457-154">若要使用不同的 sensitivities 管理对信息的访问，我们[为团队开发了三个不同的保护层](configure-teams-three-tiers-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="94457-154">To manage access to information with different sensitivities, we've developed [three different tiers of protection for Teams](configure-teams-three-tiers-protection.md).</span></span> <span data-ttu-id="94457-155">您可以自定义这些层中的任何一个，以更好地满足需求或业务。</span><span class="sxs-lookup"><span data-stu-id="94457-155">You can customize any of these tiers to better address the needs or your business.</span></span> 

![Teams 逻辑体系结构海报缩略图](../media/solutions-architecture-center/Teams-tiers-of-protection-1.png)


<span data-ttu-id="94457-157">这些分层-*比较基准*、*敏感*和*高度敏感*信息-逐渐提高有助于防止 oversharing 和潜在信息泄露的保护，如下表所示。</span><span class="sxs-lookup"><span data-stu-id="94457-157">These tiers - *baseline*, *sensitive*, and *highly sensitive* - gradually increase the protections that help prevent oversharing and potential information leakage, as shown in the following table.</span></span>

||<span data-ttu-id="94457-158">**基线层**</span><span class="sxs-lookup"><span data-stu-id="94457-158">**Baseline tier**</span></span>|<span data-ttu-id="94457-159">**敏感层**</span><span class="sxs-lookup"><span data-stu-id="94457-159">**Sensitive tier**</span></span>|<span data-ttu-id="94457-160">**高度敏感的层**</span><span class="sxs-lookup"><span data-stu-id="94457-160">**Highly sensitive tier**</span></span>|
|:--|:-----------|:------------|:-------------------|
|<span data-ttu-id="94457-161">公共或专用团队</span><span class="sxs-lookup"><span data-stu-id="94457-161">Public or private team</span></span>|<span data-ttu-id="94457-162">两者皆可</span><span class="sxs-lookup"><span data-stu-id="94457-162">Either</span></span>|<span data-ttu-id="94457-163">Private</span><span class="sxs-lookup"><span data-stu-id="94457-163">Private</span></span>|<span data-ttu-id="94457-164">Private</span><span class="sxs-lookup"><span data-stu-id="94457-164">Private</span></span>|
|<span data-ttu-id="94457-165">未经身份验证的共享</span><span class="sxs-lookup"><span data-stu-id="94457-165">Unauthenticated sharing</span></span>|<span data-ttu-id="94457-166">Blocked</span><span class="sxs-lookup"><span data-stu-id="94457-166">Blocked</span></span>|<span data-ttu-id="94457-167">Blocked</span><span class="sxs-lookup"><span data-stu-id="94457-167">Blocked</span></span>|<span data-ttu-id="94457-168">Blocked</span><span class="sxs-lookup"><span data-stu-id="94457-168">Blocked</span></span>|
|<span data-ttu-id="94457-169">文件共享</span><span class="sxs-lookup"><span data-stu-id="94457-169">File sharing</span></span>|<span data-ttu-id="94457-170">Allowed</span><span class="sxs-lookup"><span data-stu-id="94457-170">Allowed</span></span>|<span data-ttu-id="94457-171">Allowed</span><span class="sxs-lookup"><span data-stu-id="94457-171">Allowed</span></span>|<span data-ttu-id="94457-172">仅工作组所有者可以共享。</span><span class="sxs-lookup"><span data-stu-id="94457-172">Only team owners can share.</span></span>|
|<span data-ttu-id="94457-173">团队成员资格</span><span class="sxs-lookup"><span data-stu-id="94457-173">Team membership</span></span>|<span data-ttu-id="94457-174">任何人都可以加入公共团队。</span><span class="sxs-lookup"><span data-stu-id="94457-174">Anyone can join public teams.</span></span><br><span data-ttu-id="94457-175">需要团队所有者批准才能加入私有团队。</span><span class="sxs-lookup"><span data-stu-id="94457-175">Team owner approval required to join private teams.</span></span>|<span data-ttu-id="94457-176">需要团队所有者批准才能加入。</span><span class="sxs-lookup"><span data-stu-id="94457-176">Team owner approval required to join.</span></span>|<span data-ttu-id="94457-177">需要团队所有者批准才能加入。</span><span class="sxs-lookup"><span data-stu-id="94457-177">Team owner approval required to join.</span></span>|
|<span data-ttu-id="94457-178">文档加密</span><span class="sxs-lookup"><span data-stu-id="94457-178">Document encryption</span></span>|||<span data-ttu-id="94457-179">可使用敏感度标签</span><span class="sxs-lookup"><span data-stu-id="94457-179">Available with sensitivity label</span></span>|
|<span data-ttu-id="94457-180">来宾共享</span><span class="sxs-lookup"><span data-stu-id="94457-180">Guest sharing</span></span>|<span data-ttu-id="94457-181">Allowed</span><span class="sxs-lookup"><span data-stu-id="94457-181">Allowed</span></span>|<span data-ttu-id="94457-182">可以允许或阻止</span><span class="sxs-lookup"><span data-stu-id="94457-182">Can be allowed or blocked</span></span>|<span data-ttu-id="94457-183">可以允许或阻止</span><span class="sxs-lookup"><span data-stu-id="94457-183">Can be allowed or blocked</span></span>|
|<span data-ttu-id="94457-184">非托管设备</span><span class="sxs-lookup"><span data-stu-id="94457-184">Unmanaged devices</span></span>|<span data-ttu-id="94457-185">无限制</span><span class="sxs-lookup"><span data-stu-id="94457-185">No restriction</span></span>|<span data-ttu-id="94457-186">仅 Web 访问</span><span class="sxs-lookup"><span data-stu-id="94457-186">Web-only access</span></span>|<span data-ttu-id="94457-187">Blocked</span><span class="sxs-lookup"><span data-stu-id="94457-187">Blocked</span></span>|

<span data-ttu-id="94457-188">配置这些层涉及：</span><span class="sxs-lookup"><span data-stu-id="94457-188">Configuring these tiers involves:</span></span>

- <span data-ttu-id="94457-189">为来宾访问和专用频道配置团队中的设置</span><span class="sxs-lookup"><span data-stu-id="94457-189">Configuring settings in Teams for guest access and private channels</span></span>
- <span data-ttu-id="94457-190">在团队关联的 SharePoint 网站中配置用于内部和来宾共享、访问请求和共享链接的设置</span><span class="sxs-lookup"><span data-stu-id="94457-190">Configuring settings in a team's associated SharePoint site for internal and guest sharing, access requests, and sharing links</span></span>
- <span data-ttu-id="94457-191">对于*敏感*和*高度敏感*的层，配置敏感度标签以对团队进行分类，并控制非托管设备的来宾共享和访问</span><span class="sxs-lookup"><span data-stu-id="94457-191">For the *sensitive* and *highly sensitive* tiers, configuring sensitivity labels to classify the teams, and control guest sharing and access from unmanaged devices</span></span>
- <span data-ttu-id="94457-192">对于*高度敏感*的层，配置敏感度标签以加密应用它的文档</span><span class="sxs-lookup"><span data-stu-id="94457-192">For the *highly sensitive* tier, configuring a sensitivity label to encrypt the documents to which it is applied</span></span>

<span data-ttu-id="94457-193">从基线层开始，然后根据需要添加使用*敏感*和*高度敏感*的团队，以帮助保护组织中的信息。</span><span class="sxs-lookup"><span data-stu-id="94457-193">Start with the baseline tier, and then add teams that use the *sensitive* and *highly sensitive* tiers as needed to help protect the information in your organization.</span></span> <span data-ttu-id="94457-194">若要开始，请参阅以下资源：</span><span class="sxs-lookup"><span data-stu-id="94457-194">See these resources to get started:</span></span>

- [<span data-ttu-id="94457-195">配置具有基线保护的团队</span><span class="sxs-lookup"><span data-stu-id="94457-195">Configure teams with baseline protection</span></span>](configure-teams-baseline-protection.md)
- [<span data-ttu-id="94457-196">配置具有敏感数据保护的团队</span><span class="sxs-lookup"><span data-stu-id="94457-196">Configure teams with protection for sensitive data</span></span>](configure-teams-sensitive-protection.md)
- [<span data-ttu-id="94457-197">配置具有高度敏感数据保护的团队</span><span class="sxs-lookup"><span data-stu-id="94457-197">Configure teams with protection for highly sensitive data</span></span>](configure-teams-highly-sensitive-protection.md)

<span data-ttu-id="94457-198">如果您有一个高度敏感的项目，该项目需要在组织内进行额外的共享保护，则可以将使用其自己的敏感度标签的团队配置为加密文件，以便只有工作组成员可以读取这些文件。</span><span class="sxs-lookup"><span data-stu-id="94457-198">If you have a highly sensitive project that requires additional protection from sharing even within your organization, you can configure a team that uses its own sensitivity label to encrypt files so that only team members can read them.</span></span> <span data-ttu-id="94457-199">有关详细信息，请参阅[Configure a team with security 隔离](secure-teams-security-isolation.md)。</span><span class="sxs-lookup"><span data-stu-id="94457-199">See [Configure a team with security isolation](secure-teams-security-isolation.md) for details.</span></span>

### <a name="sharing-with-people-outside-your-organization"></a><span data-ttu-id="94457-200">与组织外部的人员共享</span><span class="sxs-lookup"><span data-stu-id="94457-200">Sharing with people outside your organization</span></span>

<span data-ttu-id="94457-201">您可能需要[与组织外部的人员共享任何敏感度的信息](collaborate-with-people-outside-your-organization.md)。</span><span class="sxs-lookup"><span data-stu-id="94457-201">You may need to [share information of any sensitivity with people outside your organization](collaborate-with-people-outside-your-organization.md).</span></span> <span data-ttu-id="94457-202">这可能包括与单个用户共享单个文档，以便在大型合作伙伴组织或来自世界各地的兼职翻译的主要项目上进行协作。</span><span class="sxs-lookup"><span data-stu-id="94457-202">This could range from sharing a single document with a single person to collaborating on a major project with a large partner organization or freelancers from around the world.</span></span> <span data-ttu-id="94457-203">在 Microsoft 365 中，可以轻松地完成这一范围的外部共享，并提供适当的保护措施来帮助保护您的敏感信息。</span><span class="sxs-lookup"><span data-stu-id="94457-203">In Microsoft 365, this range of external sharing can be done easily and with the appropriate safeguards to help protect your sensitive information.</span></span>

<span data-ttu-id="94457-204">这些资源将帮助您开始设置您的环境，以便与组织外部的人员进行协作：</span><span class="sxs-lookup"><span data-stu-id="94457-204">These resources will help you get started with setting up your environment for collaborating with people outside your organization:</span></span>

- <span data-ttu-id="94457-205">[对文档进行协作](collaborate-on-documents.md)，以共享文件夹的各个文件。</span><span class="sxs-lookup"><span data-stu-id="94457-205">[Collaborate on documents](collaborate-on-documents.md) for sharing individual files of folders.</span></span>
- <span data-ttu-id="94457-206">[在网站](collaborate-in-site.md)中进行协作，以便与 SharePoint 网站中的来宾进行协作。</span><span class="sxs-lookup"><span data-stu-id="94457-206">[Collaborate in a site](collaborate-in-site.md) for collaborating with guests in a SharePoint site.</span></span>
- <span data-ttu-id="94457-207">[作为团队协作](collaborate-as-team.md)处理团队中的来宾。</span><span class="sxs-lookup"><span data-stu-id="94457-207">[Collaborate as a team](collaborate-as-team.md) for collaborating with guests in a team.</span></span>

<span data-ttu-id="94457-208">根据所共享的信息的敏感度，您可以添加安全措施来帮助防止 oversharing。</span><span class="sxs-lookup"><span data-stu-id="94457-208">Depending on the sensitivity of the information being shared, you can add safeguards to help prevent oversharing.</span></span> <span data-ttu-id="94457-209">这些资源将帮助您设置您的组织所需的保护：</span><span class="sxs-lookup"><span data-stu-id="94457-209">These resources will help you set up the protections that you need for your organization:</span></span>

- [<span data-ttu-id="94457-210">有关与未经认证用户共享文件和文件夹的最佳做法</span><span class="sxs-lookup"><span data-stu-id="94457-210">Best practices for sharing files and folders with unauthenticated users</span></span>](best-practices-anonymous-sharing.md)
- [<span data-ttu-id="94457-211">在与组织外人员共享文件时限制意外公开信息</span><span class="sxs-lookup"><span data-stu-id="94457-211">Limit accidental exposure to files when sharing with people outside your organization</span></span>](share-limit-accidental-exposure.md)
- [<span data-ttu-id="94457-212">创建安全的来宾共享环境</span><span class="sxs-lookup"><span data-stu-id="94457-212">Create a secure guest sharing environment</span></span>](create-secure-guest-sharing-environment.md)

<span data-ttu-id="94457-213">如果您有一个包含合作伙伴组织的主要项目，您可以使用 Azure 权利管理在您为项目设置的团队中管理来自该组织的来宾。</span><span class="sxs-lookup"><span data-stu-id="94457-213">If you have a major project with a partner organization, you can use Azure Entitlement Management to manage the guests from that organization in a team that you set up for the project.</span></span> <span data-ttu-id="94457-214">有关详细信息，请参阅[Create a B2B extranet with 托管来宾](b2b-extranet.md)。</span><span class="sxs-lookup"><span data-stu-id="94457-214">See [Create a B2B extranet with managed guests](b2b-extranet.md) for details.</span></span>

## <a name="deploy-the-secure-collaboration-solution"></a><span data-ttu-id="94457-215">部署安全协作解决方案</span><span class="sxs-lookup"><span data-stu-id="94457-215">Deploy the secure collaboration solution</span></span>

<span data-ttu-id="94457-216">当您准备好部署此解决方案时，请继续执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="94457-216">When you're ready to deploy this solution, continue with these steps:</span></span>
1. <span data-ttu-id="94457-217">[为团队配置三个不同的保护层](configure-teams-three-tiers-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="94457-217">Configure the [three different tiers of protection for Teams](configure-teams-three-tiers-protection.md).</span></span>
2. <span data-ttu-id="94457-218">配置[与组织外部人员共享任何敏感度的信息](collaborate-with-people-outside-your-organization.md)的设置。</span><span class="sxs-lookup"><span data-stu-id="94457-218">Configure settings for [sharing information of any sensitivity with people outside your organization](collaborate-with-people-outside-your-organization.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="94457-219">另请参阅</span><span class="sxs-lookup"><span data-stu-id="94457-219">See also</span></span>

[<span data-ttu-id="94457-220">Microsoft 365 安全中心文档</span><span class="sxs-lookup"><span data-stu-id="94457-220">Microsoft 365 security documentation</span></span>](https://docs.microsoft.com/microsoft-365/security)

[<span data-ttu-id="94457-221">Microsoft 365 合规性文档</span><span class="sxs-lookup"><span data-stu-id="94457-221">Microsoft 365 compliance documentation</span></span>](https://docs.microsoft.com/microsoft-365/compliance)

[<span data-ttu-id="94457-222">欢迎使用 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="94457-222">Welcome to Microsoft Teams</span></span>](https://docs.microsoft.com/MicrosoftTeams/Teams-overview)
