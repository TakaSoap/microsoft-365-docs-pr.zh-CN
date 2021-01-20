---
title: 步骤 1. Microsoft 365 企业版租户
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
- m365solution-tenantmanagement
ms.custom:
- Ent_Solutions
description: 部署和管理单个或多个 Microsoft 365 租户，具有多地理位置和移动位置的选项。
ms.openlocfilehash: 567a2cb46e715ec560bf973a33ab83cfa63d403b
ms.sourcegitcommit: 99a7354e6a6b4d9d5202674ef57852d52a43fef6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/20/2021
ms.locfileid: "49908470"
---
# <a name="step-1-your-microsoft-365-for-enterprise-tenants"></a><span data-ttu-id="0e152-104">步骤 1.</span><span class="sxs-lookup"><span data-stu-id="0e152-104">Step 1.</span></span> <span data-ttu-id="0e152-105">Microsoft 365 企业版租户</span><span class="sxs-lookup"><span data-stu-id="0e152-105">Your Microsoft 365 for enterprise tenants</span></span>

<span data-ttu-id="0e152-106">你的第一个租户决策之一是拥有多少个租户。</span><span class="sxs-lookup"><span data-stu-id="0e152-106">One of your first tenant decisions is how many to have.</span></span> <span data-ttu-id="0e152-107">每个 Microsoft 365 租户各不相同、唯一，并且独立于所有其他 Microsoft 365 租户。</span><span class="sxs-lookup"><span data-stu-id="0e152-107">Each Microsoft 365 tenant is distinct, unique, and separate from all other Microsoft 365 tenants.</span></span> <span data-ttu-id="0e152-108">它相应的 Azure AD 租户也不同、唯一，并且独立于所有其他 Microsoft 365 租户。</span><span class="sxs-lookup"><span data-stu-id="0e152-108">It’s corresponding Azure AD tenant is also distinct, unique, and separate from all other Microsoft 365 tenants.</span></span>

## <a name="single-tenant"></a><span data-ttu-id="0e152-109">单个租户</span><span class="sxs-lookup"><span data-stu-id="0e152-109">Single tenant</span></span>
<span data-ttu-id="0e152-110">拥有一个租户可简化组织对 Microsoft 365 的使用的许多方面。</span><span class="sxs-lookup"><span data-stu-id="0e152-110">Having a single tenant simplifies many aspects of your organization’s use of Microsoft 365.</span></span> <span data-ttu-id="0e152-111">单个租户意味着单个 Azure AD 租户具有一组帐户、组和策略。</span><span class="sxs-lookup"><span data-stu-id="0e152-111">A single tenant means a single Azure AD tenant with a single set of accounts, groups, and policies.</span></span> <span data-ttu-id="0e152-112">可以通过此中央标识提供程序在整个组织中完成资源的权限和共享。</span><span class="sxs-lookup"><span data-stu-id="0e152-112">Permissions and sharing of resources across your organization can be done through this central identity provider.</span></span>

<span data-ttu-id="0e152-113">单个租户为用户提供功能最丰富且简化的协作和工作效率体验。</span><span class="sxs-lookup"><span data-stu-id="0e152-113">A single tenant provides the most feature-rich and simplified collaboration and productivity experience for your users.</span></span>

<span data-ttu-id="0e152-114">下面是显示 Microsoft 365 租户的默认位置和 Azure AD 租户的示例。</span><span class="sxs-lookup"><span data-stu-id="0e152-114">Here is an example showing the default location and Azure AD tenant of a Microsoft 365 tenant.</span></span>

![具有 Azure AD 租户的单个 Microsoft 365 租户](../media/tenant-management-overview/tenant-management-example-tenant.png)

## <a name="multiple-tenants"></a><span data-ttu-id="0e152-116">多个租户</span><span class="sxs-lookup"><span data-stu-id="0e152-116">Multiple tenants</span></span>

<span data-ttu-id="0e152-117">组织可能有多个租户的原因有很多：</span><span class="sxs-lookup"><span data-stu-id="0e152-117">There are many reasons why your organization could have multiple tenants:</span></span>

- <span data-ttu-id="0e152-118">管理隔离</span><span class="sxs-lookup"><span data-stu-id="0e152-118">Administrative isolation</span></span>
- <span data-ttu-id="0e152-119">分散式 IT</span><span class="sxs-lookup"><span data-stu-id="0e152-119">Decentralized IT</span></span>
- <span data-ttu-id="0e152-120">历史决策</span><span class="sxs-lookup"><span data-stu-id="0e152-120">Historical decisions</span></span>
- <span data-ttu-id="0e152-121">合并、收购或资产重组</span><span class="sxs-lookup"><span data-stu-id="0e152-121">Mergers, acquisitions, or divestitures</span></span>
- <span data-ttu-id="0e152-122">为大型组织明确品牌分离</span><span class="sxs-lookup"><span data-stu-id="0e152-122">Clear separation of branding for conglomerate organizations</span></span>
- <span data-ttu-id="0e152-123">预生产、测试或沙盒租户</span><span class="sxs-lookup"><span data-stu-id="0e152-123">Pre-production, test, or sandbox tenants</span></span>

<span data-ttu-id="0e152-124">下面是在同一默认数据中心地理位置 (租户 A 和租户 B) 具有两个租户的组织的示例。</span><span class="sxs-lookup"><span data-stu-id="0e152-124">Here is an example of an organization that has two tenants (Tenant A and Tenant B) in the same default datacenter geo.</span></span> <span data-ttu-id="0e152-125">每个租户作为单独的 Azure AD 租户。</span><span class="sxs-lookup"><span data-stu-id="0e152-125">Each tenant as a separate Azure AD tenant.</span></span>

![具有自己的 Azure AD 租户的多个 Microsoft 365 租户](../media/tenant-management-overview/tenant-management-example-multi-tenant.png)

<span data-ttu-id="0e152-127">当有多个租户时，在管理租户和为用户提供服务时，存在一些限制和其他注意事项。</span><span class="sxs-lookup"><span data-stu-id="0e152-127">When you have multiple tenants, there are restrictions and additional considerations when managing them and providing services to your users.</span></span>

### <a name="inter-tenant-collaboration"></a><span data-ttu-id="0e152-128">租户间协作</span><span class="sxs-lookup"><span data-stu-id="0e152-128">Inter-tenant collaboration</span></span>

<span data-ttu-id="0e152-129">如果希望用户以安全的方式在不同 Microsoft 365 租户之间更有效地协作，租户间协作选项包括使用文件和对话的中心位置、共享日历、使用 IM、音频/视频呼叫进行通信，以及保护对资源和应用程序的访问。</span><span class="sxs-lookup"><span data-stu-id="0e152-129">If you want your users to collaborate more effectively across different Microsoft 365 tenants in a secure manner, inter-tenant collaboration options include using a central location for files and conversations, sharing calendars, using IM, audio/video calls for communication, and securing access to resources and applications.</span></span>

<span data-ttu-id="0e152-130">有关详细信息，请参阅 [Microsoft 365 租户间协作](../enterprise/microsoft-365-inter-tenant-collaboration.md)。</span><span class="sxs-lookup"><span data-stu-id="0e152-130">For more information, see [Microsoft 365 inter-tenant collaboration](../enterprise/microsoft-365-inter-tenant-collaboration.md).</span></span>

### <a name="cross-tenant-mailbox-migration-preview"></a><span data-ttu-id="0e152-131">跨租户邮箱迁移 (预览) </span><span class="sxs-lookup"><span data-stu-id="0e152-131">Cross-tenant mailbox migration (preview)</span></span>

<span data-ttu-id="0e152-132">在预览版) 中跨租户邮箱迁移 (之前，在租户之间移动 Exchange Online 邮箱时，您必须将用户邮箱从当前租户 (源租户) 完全迁移到本地，然后将用户邮箱载入到新租户 (目标租户) 。</span><span class="sxs-lookup"><span data-stu-id="0e152-132">Prior to cross-tenant mailbox migration (in preview), when moving Exchange Online mailboxes between tenants, you have to completely offboard a user mailbox from their current tenant (the source tenant) to on-premises and then onboard them to a new tenant (the target tenant).</span></span> <span data-ttu-id="0e152-133">借助新的跨租户邮箱迁移功能，源租户和目标租户中的租户管理员可以在本地系统中以最少的基础结构依赖项在租户之间移动邮箱。</span><span class="sxs-lookup"><span data-stu-id="0e152-133">With the new cross-tenant mailbox migration feature, tenant administrators in both source and target tenants can move mailboxes between the tenants with minimal infrastructure dependencies in their on-premises systems.</span></span> <span data-ttu-id="0e152-134">这无需离开和载入邮箱。</span><span class="sxs-lookup"><span data-stu-id="0e152-134">This removes the need to off-board and onboard mailboxes.</span></span>

<span data-ttu-id="0e152-135">下面是跨租户邮箱迁移前的两个示例租户及其邮箱。</span><span class="sxs-lookup"><span data-stu-id="0e152-135">Here are two example tenants and their mailboxes before cross-tenant mailbox migration.</span></span>

![多个 Microsoft 365 租户及其邮箱](../media/tenant-management-overview/tenant-management-cross-tenant-mailbox-before.png)

<span data-ttu-id="0e152-137">在此图中，两个单独的租户具有其自己的域和 Exchange 邮箱集。</span><span class="sxs-lookup"><span data-stu-id="0e152-137">In this illustration, two separate tenants have their own domains and set of Exchange mailboxes.</span></span>

<span data-ttu-id="0e152-138">下面是跨租户邮箱 (租户 A) 的目标租户。</span><span class="sxs-lookup"><span data-stu-id="0e152-138">Here is the target tenant (Tenant A) after cross-tenant mailbox migration.</span></span>

![跨租户邮箱迁移后的目标租户](../media/tenant-management-overview/tenant-management-cross-tenant-mailbox-after.png)

<span data-ttu-id="0e152-140">在此图中，单个租户具有域和 Exchange 邮箱集。</span><span class="sxs-lookup"><span data-stu-id="0e152-140">In this illustration, a single tenant has both domains and both sets of Exchange mailboxes.</span></span>

<span data-ttu-id="0e152-141">有关详细信息，请参阅跨 [租户邮箱迁移](../enterprise/cross-tenant-mailbox-migration.md)。</span><span class="sxs-lookup"><span data-stu-id="0e152-141">For more information, see [Cross-tenant mailbox migration](../enterprise/cross-tenant-mailbox-migration.md).</span></span>

### <a name="tenant-to-tenant-migrations"></a><span data-ttu-id="0e152-142">租户到租户迁移</span><span class="sxs-lookup"><span data-stu-id="0e152-142">Tenant-to-tenant migrations</span></span>

<span data-ttu-id="0e152-143">合并、收购、资产重组和其他方案有若干种体系结构方法，可能会导致你将现有 Microsoft 365 租户迁移到新租户。</span><span class="sxs-lookup"><span data-stu-id="0e152-143">There are several architectural approaches for mergers, acquisitions, divestitures, and other scenarios that might lead you to migrate an existing Microsoft 365 tenant to a new tenant.</span></span> 

<span data-ttu-id="0e152-144">有关详细指导，请参阅 [Microsoft 365 租户到租户迁移](../enterprise/microsoft-365-tenant-to-tenant-migrations.md)。</span><span class="sxs-lookup"><span data-stu-id="0e152-144">For detailed guidance, see [Microsoft 365 tenant-to-tenant migrations](../enterprise/microsoft-365-tenant-to-tenant-migrations.md).</span></span>

## <a name="multi-geo-for-a-tenant"></a><span data-ttu-id="0e152-145">租户的多地理位置</span><span class="sxs-lookup"><span data-stu-id="0e152-145">Multi-Geo for a tenant</span></span>

<span data-ttu-id="0e152-146">使用 Microsoft 365 多地理位置，可以在选择满足数据驻留要求的其他数据中心地理位置中预配和存储静止数据，同时为工作人员解锁新式生产力体验的全球推出。</span><span class="sxs-lookup"><span data-stu-id="0e152-146">With Microsoft 365 Multi-Geo, you can provision and store data at rest in the other datacenter geo locations that you've chosen to meet data residency requirements, and at the same time unlock your global rollout of modern productivity experiences to your workers.</span></span>

<span data-ttu-id="0e152-147">在多地理位置环境中，Microsoft 365 租户由最初创建 Microsoft 365 订阅的默认或中心位置以及一个或多个附属位置组成。</span><span class="sxs-lookup"><span data-stu-id="0e152-147">In a Multi-Geo environment, your Microsoft 365 tenant consists of a default or central location where your Microsoft 365 subscription was originally created and one or more satellite locations.</span></span> <span data-ttu-id="0e152-148">在多地理位置租户中，有关地理位置、组和用户信息的信息在全局 Azure AD 租户中掌握。</span><span class="sxs-lookup"><span data-stu-id="0e152-148">In a multi-geo tenant, the information about geo locations, groups, and user information is mastered in a global Azure AD tenant.</span></span> <span data-ttu-id="0e152-149">由于租户信息是集中掌握并同步到每个地理位置的，因此涉及公司中任何人的协作体验将跨位置共享。</span><span class="sxs-lookup"><span data-stu-id="0e152-149">Because your tenant information is mastered centrally and synchronized into each geo location, collaboration experiences involving anyone from your company are shared across the locations.</span></span>

<span data-ttu-id="0e152-150">下面是一个组织的示例，该组织的默认位置位于欧洲，而附属位置位于北美。</span><span class="sxs-lookup"><span data-stu-id="0e152-150">Here is an example of an organization that has its default location in Europe and a satellite location in North America.</span></span> <span data-ttu-id="0e152-151">这两个位置共享单个 Microsoft 365 租户的同一个全局 Azure AD 租户。</span><span class="sxs-lookup"><span data-stu-id="0e152-151">Both locations share the same global Azure AD tenant for the single Microsoft 365 tenant.</span></span>

![多地理位置 Microsoft 365 租户示例](../media/tenant-management-overview/tenant-management-example-multi-geo.png)

<span data-ttu-id="0e152-153">有关详细信息，请参阅 [Microsoft 365 多地理位置](../enterprise/microsoft-365-multi-geo.md)。</span><span class="sxs-lookup"><span data-stu-id="0e152-153">For more information, see [Microsoft 365 Multi-Geo](../enterprise/microsoft-365-multi-geo.md).</span></span>

## <a name="moving-core-data-to-a-new-datacenter-geo"></a><span data-ttu-id="0e152-154">将核心数据移动到新的数据中心地理位置</span><span class="sxs-lookup"><span data-stu-id="0e152-154">Moving core data to a new datacenter geo</span></span>

<span data-ttu-id="0e152-155">Microsoft 继续为 Microsoft 365 服务打开新的数据中心地理位置。</span><span class="sxs-lookup"><span data-stu-id="0e152-155">Microsoft continues to open new datacenter geos for Microsoft 365 services.</span></span> <span data-ttu-id="0e152-156">这些新数据中心地理位置增加了容量和计算资源，以支持我们的持续客户需求和使用增长。</span><span class="sxs-lookup"><span data-stu-id="0e152-156">These new datacenter geos add capacity and compute resources to support our ongoing customer demand and usage growth.</span></span> <span data-ttu-id="0e152-157">此外，新的数据中心地理位置为核心客户数据提供地理位置内数据驻留。</span><span class="sxs-lookup"><span data-stu-id="0e152-157">Additionally, the new datacenter geos offer in-geo data residency for core customer data.</span></span>

<span data-ttu-id="0e152-158">尽管打开新的数据中心地理位置不会影响你和存储在现有数据中心地理位置中的核心数据，但 Microsoft 允许你请求提前将组织的核心客户数据静止迁移到新的数据中心地理位置。</span><span class="sxs-lookup"><span data-stu-id="0e152-158">Although opening a new datacenter geo does not impact you and your core data stored in an already existing datacenter geo, Microsoft allows you to request an early migration of your organization's core customer data at rest to a new datacenter geo.</span></span>

<span data-ttu-id="0e152-159">下面是一个示例，其中 Microsoft 365 租户从欧盟 (欧盟) 数据中心地理位置移动到位于英国 (英国) 。</span><span class="sxs-lookup"><span data-stu-id="0e152-159">Here is an example in which a Microsoft 365 tenant was moved from the European Union (EU) datacenter geo to the one located in the United Kingdom (UK).</span></span>

![在数据中心地理位置之间移动 Microsoft 365 租户的示例](../media/tenant-management-overview/tenant-management-example-tenant-move.png)

<span data-ttu-id="0e152-161">有关详细信息，请参阅将 [核心数据移动到新的 Microsoft 365 数据中心地理位置](../enterprise/moving-data-to-new-datacenter-geos.md)。</span><span class="sxs-lookup"><span data-stu-id="0e152-161">For more information, see [Moving core data to new Microsoft 365 datacenter geos](../enterprise/moving-data-to-new-datacenter-geos.md).</span></span>

## <a name="products-and-licenses-for-a-tenant"></a><span data-ttu-id="0e152-162">租户的产品和许可证</span><span class="sxs-lookup"><span data-stu-id="0e152-162">Products and licenses for a tenant</span></span>

<span data-ttu-id="0e152-163">购买第一个产品（如 Microsoft 365 E3）时，将创建 Microsoft 365 租户。</span><span class="sxs-lookup"><span data-stu-id="0e152-163">Your Microsoft 365 tenant gets created when you purchase your first product, such as Microsoft 365 E3.</span></span> <span data-ttu-id="0e152-164">除了产品外，还有许可证，按月或按年收费。</span><span class="sxs-lookup"><span data-stu-id="0e152-164">Along with the product are licenses, which are charged a monthly or annual fee.</span></span> <span data-ttu-id="0e152-165">然后，管理员直接或通过组成员身份将一个产品中的可用许可证分配给用户帐户。</span><span class="sxs-lookup"><span data-stu-id="0e152-165">An administrator then assigns an available license from one of your products to a user account, either directly or through group membership.</span></span> <span data-ttu-id="0e152-166">根据组织的业务需求，你可能拥有一组产品，每个产品都有其自己的许可证池。</span><span class="sxs-lookup"><span data-stu-id="0e152-166">Depending on your organization's business needs, you might have a set of products, each with their own pool of licenses.</span></span> 

<span data-ttu-id="0e152-167">确定产品集和每个产品的许可证数量需要进行一些规划以：</span><span class="sxs-lookup"><span data-stu-id="0e152-167">Determining the set of products and the number of licenses for each requires some planning to:</span></span>

- <span data-ttu-id="0e152-168">确保你有足够的许可证用于需要高级功能的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="0e152-168">Ensure you have enough licenses for the user accounts that need advanced features.</span></span>
- <span data-ttu-id="0e152-169">根据组织人员配置的变化，防止你使用过多的许可证或拥有过多的未分配许可证。</span><span class="sxs-lookup"><span data-stu-id="0e152-169">Prevent you from running out of licenses or having too many unassigned licenses, based on changes in staffing at your organization.</span></span>


## <a name="results-of-step-1"></a><span data-ttu-id="0e152-170">步骤 1 的结果</span><span class="sxs-lookup"><span data-stu-id="0e152-170">Results of Step 1</span></span>

<span data-ttu-id="0e152-171">对于 Microsoft 365 企业版租户，你已确定：</span><span class="sxs-lookup"><span data-stu-id="0e152-171">For your Microsoft 365 for enterprise tenants, you have determined:</span></span>

- <span data-ttu-id="0e152-172">你拥有或需要多少租户。</span><span class="sxs-lookup"><span data-stu-id="0e152-172">How many tenants you have or need.</span></span>
- <span data-ttu-id="0e152-173">对于每个租户，必须购买哪些产品和许可证。</span><span class="sxs-lookup"><span data-stu-id="0e152-173">For each tenant, which products and licenses must be purchased.</span></span>
- <span data-ttu-id="0e152-174">租户是否需要多地理位置，以满足数据驻留要求。</span><span class="sxs-lookup"><span data-stu-id="0e152-174">Whether a tenant needs to be Multi-Geo to comply with data residency requirements.</span></span>
- <span data-ttu-id="0e152-175">是否需要设置租户间协作。</span><span class="sxs-lookup"><span data-stu-id="0e152-175">Whether you need to set up inter-tenant collaboration.</span></span>
- <span data-ttu-id="0e152-176">是否需要将一个租户迁移到另一个租户。</span><span class="sxs-lookup"><span data-stu-id="0e152-176">Whether you need to migrate one tenant to another.</span></span>
- <span data-ttu-id="0e152-177">是否需要将核心数据从一个数据中心地理位置移动到新数据中心地理位置。</span><span class="sxs-lookup"><span data-stu-id="0e152-177">Whether you need to move core data from one datacenter geo to new one.</span></span>

<span data-ttu-id="0e152-178">下面是新租户的示例。</span><span class="sxs-lookup"><span data-stu-id="0e152-178">Here is an example of a new tenant.</span></span>

![新租户的示例](../media/tenant-management-overview/tenant-management-tenant-build-step1.png)

<span data-ttu-id="0e152-180">在此图中，租户具有：</span><span class="sxs-lookup"><span data-stu-id="0e152-180">In this illustration, the tenant has:</span></span>

- <span data-ttu-id="0e152-181">与 Microsoft 365 数据中心地理位置对应的默认位置。</span><span class="sxs-lookup"><span data-stu-id="0e152-181">A default location corresponding to a Microsoft 365 datacenter geo.</span></span>
- <span data-ttu-id="0e152-182">一组产品和许可证。</span><span class="sxs-lookup"><span data-stu-id="0e152-182">A set of products and licenses.</span></span>
- <span data-ttu-id="0e152-183">云生产力应用集，其中一些特定于产品。</span><span class="sxs-lookup"><span data-stu-id="0e152-183">The set of cloud productivity apps, some of which are specific to products.</span></span>
- <span data-ttu-id="0e152-184">包含全局管理员帐户和初始 DNS 域名的 Azure AD 租户。</span><span class="sxs-lookup"><span data-stu-id="0e152-184">An Azure AD tenant that contains global administrator accounts and an initial DNS domain name.</span></span>

<span data-ttu-id="0e152-185">随着我们完成此解决方案的其他步骤，我们将构建此图。</span><span class="sxs-lookup"><span data-stu-id="0e152-185">As we move through the additional steps of this solution, we will build out this figure.</span></span>

## <a name="ongoing-maintenance-for-tenants"></a><span data-ttu-id="0e152-186">租户持续维护</span><span class="sxs-lookup"><span data-stu-id="0e152-186">Ongoing maintenance for tenants</span></span>

<span data-ttu-id="0e152-187">您可能需要持续执行：</span><span class="sxs-lookup"><span data-stu-id="0e152-187">On an ongoing basis, you might need to:</span></span>

- <span data-ttu-id="0e152-188">添加新租户。</span><span class="sxs-lookup"><span data-stu-id="0e152-188">Add a new tenant.</span></span>
- <span data-ttu-id="0e152-189">向具有初始许可证数量的租户添加新产品。</span><span class="sxs-lookup"><span data-stu-id="0e152-189">Add new products to a tenant with an initial number of licenses.</span></span>
- <span data-ttu-id="0e152-190">更改租户中产品的许可证集，以根据员工需求的变化进行调整。</span><span class="sxs-lookup"><span data-stu-id="0e152-190">Change the set of licenses for a product in a tenant to adjust for changing staff requirements.</span></span>
- <span data-ttu-id="0e152-191">将核心数据从租户移动到新的数据中心地理位置。</span><span class="sxs-lookup"><span data-stu-id="0e152-191">Move your core data from a tenant to a new datacenter geo location.</span></span>
- <span data-ttu-id="0e152-192">添加多地理位置数据驻留要求。</span><span class="sxs-lookup"><span data-stu-id="0e152-192">Add Multi-Geo for data residency requirements.</span></span>
- <span data-ttu-id="0e152-193">设置租户间协作。</span><span class="sxs-lookup"><span data-stu-id="0e152-193">Set up inter-tenant collaboration.</span></span>

## <a name="next-step"></a><span data-ttu-id="0e152-194">后续步骤</span><span class="sxs-lookup"><span data-stu-id="0e152-194">Next step</span></span>

<span data-ttu-id="0e152-195">[![步骤 2.优化租户以用于访问网络](../media/tenant-management-overview/tenant-management-step-grid-networking.png)](tenant-management-networking.md)</span><span class="sxs-lookup"><span data-stu-id="0e152-195">[![Step 2. Optimize your tenant for network for access](../media/tenant-management-overview/tenant-management-step-grid-networking.png)](tenant-management-networking.md)</span></span>

<span data-ttu-id="0e152-196">继续使用 [网络](tenant-management-networking.md) ，从工作人员到 Microsoft 365 云服务提供最佳网络。</span><span class="sxs-lookup"><span data-stu-id="0e152-196">Continue with [networking](tenant-management-networking.md) to provide optimal networking from your workers to Microsoft 365 cloud services.</span></span>
