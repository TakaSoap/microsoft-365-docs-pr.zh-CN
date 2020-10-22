---
title: Contoso Corporation 的主要机密项目的独立团队
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/14/2020
audience: ITPro
ms.topic: overview
ms.prod: microsoft-365-enterprise
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
ms.custom: Ent_Architecture
description: 摘要： Contoso 如何使用安全隔离的团队对主要项目进行安全隔离，以开发一套新的产品和服务。
ms.openlocfilehash: b8794502afcb77a8e597a1b05dfc92acd093f23a
ms.sourcegitcommit: 3b1bd8aa1430bc9565743a446bbc27b199f30f73
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/22/2020
ms.locfileid: "48656061"
---
# <a name="isolated-team-for-a-top-secret-project-of-the-contoso-corporation"></a><span data-ttu-id="84e2d-103">Contoso Corporation 的主要机密项目的独立团队</span><span class="sxs-lookup"><span data-stu-id="84e2d-103">Isolated team for a top-secret project of the Contoso Corporation</span></span>

<span data-ttu-id="84e2d-104">在执行异地异地工作时，Contoso 首席执行官订购了一系列新产品和服务，在接下来的五年中，这可能会导致 Contoso 的利润加倍。</span><span class="sxs-lookup"><span data-stu-id="84e2d-104">After an executive offsite, Contoso’s CEO ordered the development of a new suite of products and services that could double Contoso’s profits in the next five years.</span></span> <span data-ttu-id="84e2d-105">开发业务、工程和市场计划的首要项目称为 **Project 2x** ，而整个公司的主要员工均为 recruited。</span><span class="sxs-lookup"><span data-stu-id="84e2d-105">The top-secret project to develop the business, engineering, and market plan was named **Project 2X** and key staff across the company were recruited.</span></span> 

<span data-ttu-id="84e2d-106">用于研究和开发的时间线是紧密的，这意味着协作必须高效，并提供安全会议、持续会话和文件存储。</span><span class="sxs-lookup"><span data-stu-id="84e2d-106">The timelines for research and development were tight, which meant that collaboration had to be efficient and provide for secure meetings, ongoing conversations, and file storage.</span></span>

<span data-ttu-id="84e2d-107">项目2的结果可交付项是商业计划、产品和工程规范，以及 Word、Excel 和 PowerPoint 文件的格式的营销材料和计划。</span><span class="sxs-lookup"><span data-stu-id="84e2d-107">The resulting deliverables for Project 2X were business plans, product and engineering specifications, and marketing materials and schedules in the form of Word, Excel, and PowerPoint files.</span></span> 

<span data-ttu-id="84e2d-108">由于其敏感性，对这些文件的访问权限为：</span><span class="sxs-lookup"><span data-stu-id="84e2d-108">Due to their sensitive nature, access to these files were:</span></span>

- <span data-ttu-id="84e2d-109">限制为项目2个团队成员和高级领导。</span><span class="sxs-lookup"><span data-stu-id="84e2d-109">Restricted to Project 2X team members and senior leadership.</span></span>
- <span data-ttu-id="84e2d-110">使用权限进行加密和保护，以仅允许访问 Project 2X 团队成员和高级领导，即使这些文件是在其安全文件夹之外分发的也是如此。</span><span class="sxs-lookup"><span data-stu-id="84e2d-110">Encrypted and protected with permissions to allow access only to Project 2X team members and senior leadership, even if the files were distributed outside of their secured folders.</span></span>

<span data-ttu-id="84e2d-111">Contoso IT 员工使用项目2的 [安全隔离团队](secure-teams-security-isolation.md) 和这些步骤。</span><span class="sxs-lookup"><span data-stu-id="84e2d-111">Contoso IT staff used a [team with security isolation](secure-teams-security-isolation.md) for Project 2X and these steps.</span></span>

## <a name="step-1-created-a-private-team"></a><span data-ttu-id="84e2d-112">步骤1：创建专用团队</span><span class="sxs-lookup"><span data-stu-id="84e2d-112">Step 1: Created a private team</span></span>

<span data-ttu-id="84e2d-113">首先，为了保护对团队的基础 SharePoint 网站的访问，Contoso IT 管理员配置了 [建议的 SharePoint 访问策略](../security/office-365-security/sharepoint-file-access-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="84e2d-113">First, to protect access to the underlying SharePoint site for the team, Contoso IT administrators configured the [recommended SharePoint access policies](../security/office-365-security/sharepoint-file-access-policies.md).</span></span>

<span data-ttu-id="84e2d-114">接下来，Contoso IT 管理员创建了一个名为 Project 2 的新私人团队，并将 Project 2X 员工的用户帐户添加为成员。</span><span class="sxs-lookup"><span data-stu-id="84e2d-114">Next, a Contoso IT administrator created a new private team named Project 2X and added the user accounts of Project 2X staff as members.</span></span> <span data-ttu-id="84e2d-115">他们还配置了团队，以便只有项目2组的所有者才能创建专用频道。</span><span class="sxs-lookup"><span data-stu-id="84e2d-115">They also configured the team so that only Project 2X team owners can create private channels.</span></span>

<span data-ttu-id="84e2d-116">有关配置的详细信息，请参阅 [创建专用团队](secure-teams-security-isolation.md#create-a-private-team)。</span><span class="sxs-lookup"><span data-stu-id="84e2d-116">For the configuration details, see [Create a private team](secure-teams-security-isolation.md#create-a-private-team).</span></span>

## <a name="step-2-created-a-sensitivity-label-for-the-project-2x-team"></a><span data-ttu-id="84e2d-117">步骤2：为项目2组创建敏感度标签</span><span class="sxs-lookup"><span data-stu-id="84e2d-117">Step 2: Created a sensitivity label for the Project 2X team</span></span>

<span data-ttu-id="84e2d-118">Contoso admins 创建了一个名为 " **Project 2** " 的新敏感度标签，其类型为：</span><span class="sxs-lookup"><span data-stu-id="84e2d-118">Contoso admins created a new sensitivity label named **Project 2X** that:</span></span>

- <span data-ttu-id="84e2d-119">已启用加密。</span><span class="sxs-lookup"><span data-stu-id="84e2d-119">Enabled encryption.</span></span>
- <span data-ttu-id="84e2d-120">允许项目2个 Microsoft 365 组的 Co-Author 权限。</span><span class="sxs-lookup"><span data-stu-id="84e2d-120">Allowed Co-Author permissions for the Project 2X Microsoft 365 group.</span></span>
- <span data-ttu-id="84e2d-121">允许高级领导组的查看器权限。</span><span class="sxs-lookup"><span data-stu-id="84e2d-121">Allowed Viewer permissions for the Senior Leadership group.</span></span>
- <span data-ttu-id="84e2d-122">阻止了对非托管设备的访问。</span><span class="sxs-lookup"><span data-stu-id="84e2d-122">Blocked access to unmanaged devices.</span></span>

<span data-ttu-id="84e2d-123">受以下条件保护的基础 Project 2X SharePoint 网站的 " **文档** " 部分中的文件：</span><span class="sxs-lookup"><span data-stu-id="84e2d-123">Files in the **Documents** section of the underlying Project 2X SharePoint site were protected by:</span></span>

- <span data-ttu-id="84e2d-124">网站权限，仅允许对项目2个 Microsoft 365 组的成员拥有完全权限，并为高级领导组读取权限。</span><span class="sxs-lookup"><span data-stu-id="84e2d-124">The site permissions, which only allow full permissions to members of the Project 2X Microsoft 365 group and read permissions to the Senior Leadership group.</span></span>
- <span data-ttu-id="84e2d-125">Project 2-2 敏感度标签，带有文件移动或复制到网站时携带的加密和权限。</span><span class="sxs-lookup"><span data-stu-id="84e2d-125">The Project 2X sensitivity label, with encryption and permissions that travel with the file if it is moved or copied from the site.</span></span>

<span data-ttu-id="84e2d-126">有关配置的详细信息，请参阅 [创建灵敏度标签](secure-teams-security-isolation.md#create-a-sensitivity-label)。</span><span class="sxs-lookup"><span data-stu-id="84e2d-126">For the configuration details, see [Create a sensitivity label](secure-teams-security-isolation.md#create-a-sensitivity-label).</span></span>

## <a name="step-3-configured-the-underlying-sharepoint-site"></a><span data-ttu-id="84e2d-127">步骤3：配置基础 SharePoint 网站</span><span class="sxs-lookup"><span data-stu-id="84e2d-127">Step 3: Configured the underlying SharePoint site</span></span>

<span data-ttu-id="84e2d-128">首先，为了保护对团队的基础 SharePoint 网站的访问，Contoso IT 管理员配置了 [建议的 SharePoint 访问策略](../security/office-365-security/sharepoint-file-access-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="84e2d-128">First, to protect access to the underlying SharePoint site for the team, Contoso IT administrators configured the [recommended SharePoint access policies](../security/office-365-security/sharepoint-file-access-policies.md).</span></span>

<span data-ttu-id="84e2d-129">接下来，他们为网站配置了其他权限设置：</span><span class="sxs-lookup"><span data-stu-id="84e2d-129">Next, they configured additional permission settings for the site:</span></span>

- <span data-ttu-id="84e2d-130">以防止项目2X 组成员共享对网站的访问权限。</span><span class="sxs-lookup"><span data-stu-id="84e2d-130">To prevent Project 2X group members from sharing access to the site.</span></span> <span data-ttu-id="84e2d-131">有关配置的详细信息，请参阅 [具有安全隔离的团队的 SharePoint 设置](secure-teams-security-isolation.md#sharepoint-settings)。</span><span class="sxs-lookup"><span data-stu-id="84e2d-131">For the configuration details, see [SharePoint settings for a team with security isolation](secure-teams-security-isolation.md#sharepoint-settings).</span></span>
- <span data-ttu-id="84e2d-132">用于高级领导组的读取权限。</span><span class="sxs-lookup"><span data-stu-id="84e2d-132">For Read permissions for the Senior Leadership group.</span></span>

<span data-ttu-id="84e2d-133">接下来，他们为网站配置了其他权限设置，以防止 Project 2X 组成员共享对网站的访问权限。</span><span class="sxs-lookup"><span data-stu-id="84e2d-133">Next, they configured additional permission settings for the site to prevent Project 2X group members from sharing access to the site.</span></span> 

<span data-ttu-id="84e2d-134">由于已创建项目2X 的专用通道，组所有者禁用了来宾共享，并将默认共享链接设置为 " **特定人员** " 值。</span><span class="sxs-lookup"><span data-stu-id="84e2d-134">As private channels for the Project 2X were created, the group owner disabled guest sharing and set the default sharing link to the **Specific people** value.</span></span>

<span data-ttu-id="84e2d-135">下面是具有安全隔离的 Project 2X 团队的结果配置。</span><span class="sxs-lookup"><span data-stu-id="84e2d-135">Here is the resulting configuration of the Project 2X team with security isolation.</span></span>

![项目2组的结果配置](../media/contoso-team-for-top-secret-project.png)

 ## <a name="step-4-trained-project-2x-team-members"></a><span data-ttu-id="84e2d-137">步骤4：训练有素的项目2组成员</span><span class="sxs-lookup"><span data-stu-id="84e2d-137">Step 4: Trained Project 2X team members</span></span>

<span data-ttu-id="84e2d-138">Contoso 安全员工在强制性课程中培训了 Project 2X 团队成员，其中包括：</span><span class="sxs-lookup"><span data-stu-id="84e2d-138">Contoso security staff trained the Project 2X team members in a mandatory course that stepped them through:</span></span>

- <span data-ttu-id="84e2d-139">如何：访问新的 Project 2X 团队、使用会议和聊天以及如何在团队文件中进行协作。</span><span class="sxs-lookup"><span data-stu-id="84e2d-139">How to access the new Project 2X team, use meetings and chats, and how to collaborate on team files.</span></span>
- <span data-ttu-id="84e2d-140">如何：在团队中创建新文件并上载本地创建的新文件。</span><span class="sxs-lookup"><span data-stu-id="84e2d-140">How to create new files in the team and upload new files created locally.</span></span>
- <span data-ttu-id="84e2d-141">如何使用 Project 2X 敏感度标签标记文件。</span><span class="sxs-lookup"><span data-stu-id="84e2d-141">How to label files with the Project 2X sensitivity label.</span></span>
- <span data-ttu-id="84e2d-142">演示 Project 2X 标签如何保护文件（即使是在离开团队时）。</span><span class="sxs-lookup"><span data-stu-id="84e2d-142">A demonstration of how the Project 2X  label protects a file even when it leaves the team.</span></span>

<span data-ttu-id="84e2d-143">最终结果是一个安全的环境，在此环境中，Project 2X 团队成员在安全环境中共同参与聊天、会议和文件。</span><span class="sxs-lookup"><span data-stu-id="84e2d-143">The end result was a secure environment in which Project 2X team members collaborated in a secure environment for chats, meetings, and files.</span></span>

<span data-ttu-id="84e2d-144">下面的示例展示了存储在基础项目2X 网站中的文件，并分配了 Project 2/2 敏感度标签。</span><span class="sxs-lookup"><span data-stu-id="84e2d-144">Here is an example of a file stored in the underlying Project 2X site with the Project 2X sensitivity label assigned.</span></span>

![存储在基础项目2X 网站中的文件的示例](../media/contoso-team-for-top-secret-project-example.png)

<span data-ttu-id="84e2d-146">在几个实例中，Project 2X 工作组成员将受 Project 2X 标签保护的文件下载到本地驱动器以供脱机工作。</span><span class="sxs-lookup"><span data-stu-id="84e2d-146">In a couple of instances, Project 2X team members downloaded files protected by the Project 2X label to a local drive for offline work.</span></span> 

<span data-ttu-id="84e2d-147">但是，在打开凭据后收到凭据提示时，他们会意识到它们的错误并将其删除。</span><span class="sxs-lookup"><span data-stu-id="84e2d-147">However, after being prompted for credentials when opening them, they realized their mistake and deleted them.</span></span>

<span data-ttu-id="84e2d-148">由于团队的协作环境和 Microsoft 365 的安全功能，project 2X 的详细信息在项目的持续时间内保持秘密。</span><span class="sxs-lookup"><span data-stu-id="84e2d-148">Because of the collaboration environment of Teams and the security features of Microsoft 365, the details of Project 2X were kept secret for the duration of the project.</span></span> <span data-ttu-id="84e2d-149">Contoso 宣布了其计划，正在将新产品和服务推出给其客户和投资者的欣喜及其竞争对手的 chagrin 的过程。</span><span class="sxs-lookup"><span data-stu-id="84e2d-149">Contoso announced its plans and is in the process of rolling out the new products and services to the delight of its customers and investors and the chagrin of its competitors.</span></span>

## <a name="next-step"></a><span data-ttu-id="84e2d-150">后续步骤</span><span class="sxs-lookup"><span data-stu-id="84e2d-150">Next step</span></span>

<span data-ttu-id="84e2d-151">在您的组织中[部署具有安全隔离的团队](secure-teams-security-isolation.md)。</span><span class="sxs-lookup"><span data-stu-id="84e2d-151">[Deploy a team with security isolation](secure-teams-security-isolation.md) in your organization.</span></span>

