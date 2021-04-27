---
title: Contoso Corporation 最高机密项目的隔离团队
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: dansimp
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
description: 摘要：Contoso 如何使用具有最高机密项目安全隔离的团队来开发一套新的产品和服务。
ms.openlocfilehash: 751bf3972d148219a6cc341067c0bf34cd581447
ms.sourcegitcommit: e02cf5702af178ddd2968877a808874ecb49ed2c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2021
ms.locfileid: "52029012"
---
# <a name="isolated-team-for-a-top-secret-project-of-the-contoso-corporation"></a><span data-ttu-id="3db44-103">Contoso Corporation 最高机密项目的隔离团队</span><span class="sxs-lookup"><span data-stu-id="3db44-103">Isolated team for a top-secret project of the Contoso Corporation</span></span>

<span data-ttu-id="3db44-104">在公司外执行人员之后，Contoso 的 CEO 订购了一套新的产品和服务的开发，这些产品和服务在接下来五年内可能会使 Contoso 利润翻倍。</span><span class="sxs-lookup"><span data-stu-id="3db44-104">After an executive offsite, Contoso’s CEO ordered the development of a new suite of products and services that could double Contoso’s profits in the next five years.</span></span> <span data-ttu-id="3db44-105">开发业务、工程和市场计划的顶级机密项目名为 **Project 2X，** 公司中的主要员工已招聘。</span><span class="sxs-lookup"><span data-stu-id="3db44-105">The top-secret project to develop the business, engineering, and market plan was named **Project 2X** and key staff across the company were recruited.</span></span> 

<span data-ttu-id="3db44-106">研发的日程表很紧，这意味着协作必须高效，并提供安全会议、正在进行的对话和文件存储。</span><span class="sxs-lookup"><span data-stu-id="3db44-106">The timelines for research and development were tight, which meant that collaboration had to be efficient and provide for secure meetings, ongoing conversations, and file storage.</span></span>

<span data-ttu-id="3db44-107">Project 2X 生成的可交付结果为业务计划、产品和工程规范，以及 Word、Excel 和 PowerPoint 文件形式的营销材料及计划。</span><span class="sxs-lookup"><span data-stu-id="3db44-107">The resulting deliverables for Project 2X were business plans, product and engineering specifications, and marketing materials and schedules in the form of Word, Excel, and PowerPoint files.</span></span> 

<span data-ttu-id="3db44-108">由于这些文件的敏感性质，对这些文件的访问包括：</span><span class="sxs-lookup"><span data-stu-id="3db44-108">Due to their sensitive nature, access to these files were:</span></span>

- <span data-ttu-id="3db44-109">仅限于 Project 2X 团队成员和高层领导。</span><span class="sxs-lookup"><span data-stu-id="3db44-109">Restricted to Project 2X team members and senior leadership.</span></span>
- <span data-ttu-id="3db44-110">使用允许仅访问 Project 2X 团队成员和高层领导的权限进行加密和保护，即使文件分发到其安全文件夹之外。</span><span class="sxs-lookup"><span data-stu-id="3db44-110">Encrypted and protected with permissions to allow access only to Project 2X team members and senior leadership, even if the files were distributed outside of their secured folders.</span></span>

<span data-ttu-id="3db44-111">Contoso IT 员工使用具有 Project 2X [安全](secure-teams-security-isolation.md) 隔离和这些步骤的团队。</span><span class="sxs-lookup"><span data-stu-id="3db44-111">Contoso IT staff used a [team with security isolation](secure-teams-security-isolation.md) for Project 2X and these steps.</span></span>

## <a name="step-1-created-a-private-team"></a><span data-ttu-id="3db44-112">步骤 1：创建了私人团队</span><span class="sxs-lookup"><span data-stu-id="3db44-112">Step 1: Created a private team</span></span>

<span data-ttu-id="3db44-113">首先，为了保护团队对基础 SharePoint 网站的访问，Contoso IT 管理员配置了建议的 [SharePoint 访问策略](../security/office-365-security/sharepoint-file-access-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="3db44-113">First, to protect access to the underlying SharePoint site for the team, Contoso IT administrators configured the [recommended SharePoint access policies](../security/office-365-security/sharepoint-file-access-policies.md).</span></span>

<span data-ttu-id="3db44-114">接下来，Contoso IT 管理员创建了一个名为 Project 2X 的新专用团队，并添加了 Project 2X 员工的用户帐户作为成员。</span><span class="sxs-lookup"><span data-stu-id="3db44-114">Next, a Contoso IT administrator created a new private team named Project 2X and added the user accounts of Project 2X staff as members.</span></span> <span data-ttu-id="3db44-115">他们还配置了团队，以便只有 Project 2X 团队所有者可以创建私人频道。</span><span class="sxs-lookup"><span data-stu-id="3db44-115">They also configured the team so that only Project 2X team owners can create private channels.</span></span>

<span data-ttu-id="3db44-116">有关配置的详细信息，请参阅 [创建私人团队](secure-teams-security-isolation.md#create-a-private-team)。</span><span class="sxs-lookup"><span data-stu-id="3db44-116">For the configuration details, see [Create a private team](secure-teams-security-isolation.md#create-a-private-team).</span></span>

## <a name="step-2-created-a-sensitivity-label-for-the-project-2x-team"></a><span data-ttu-id="3db44-117">步骤 2：为 Project 2X 团队创建了敏感度标签</span><span class="sxs-lookup"><span data-stu-id="3db44-117">Step 2: Created a sensitivity label for the Project 2X team</span></span>

<span data-ttu-id="3db44-118">Contoso 管理员创建了一个名为 **Project 2X** 的新敏感度标签，该标签：</span><span class="sxs-lookup"><span data-stu-id="3db44-118">Contoso admins created a new sensitivity label named **Project 2X** that:</span></span>

- <span data-ttu-id="3db44-119">启用加密。</span><span class="sxs-lookup"><span data-stu-id="3db44-119">Enabled encryption.</span></span>
- <span data-ttu-id="3db44-120">允许Co-Author Project 2X Microsoft 365 组的权限。</span><span class="sxs-lookup"><span data-stu-id="3db44-120">Allowed Co-Author permissions for the Project 2X Microsoft 365 group.</span></span>
- <span data-ttu-id="3db44-121">Senior Leadership 组允许的查看者权限。</span><span class="sxs-lookup"><span data-stu-id="3db44-121">Allowed Viewer permissions for the Senior Leadership group.</span></span>
- <span data-ttu-id="3db44-122">阻止访问非托管设备。</span><span class="sxs-lookup"><span data-stu-id="3db44-122">Blocked access to unmanaged devices.</span></span>

<span data-ttu-id="3db44-123">基础 Project  2X SharePoint 网站的"文档"部分中的文件受以下保护：</span><span class="sxs-lookup"><span data-stu-id="3db44-123">Files in the **Documents** section of the underlying Project 2X SharePoint site were protected by:</span></span>

- <span data-ttu-id="3db44-124">网站权限，仅允许对 Project 2X Microsoft 365 组的成员具有完全权限，并且对 Senior Leadership 组具有读取权限。</span><span class="sxs-lookup"><span data-stu-id="3db44-124">The site permissions, which only allow full permissions to members of the Project 2X Microsoft 365 group and read permissions to the Senior Leadership group.</span></span>
- <span data-ttu-id="3db44-125">Project 2X 敏感度标签，如果从网站移动或复制文件，则其加密和权限随文件一起移动。</span><span class="sxs-lookup"><span data-stu-id="3db44-125">The Project 2X sensitivity label, with encryption and permissions that travel with the file if it is moved or copied from the site.</span></span>

<span data-ttu-id="3db44-126">有关配置的详细信息，请参阅 [创建敏感度标签](secure-teams-security-isolation.md#create-a-sensitivity-label)。</span><span class="sxs-lookup"><span data-stu-id="3db44-126">For the configuration details, see [Create a sensitivity label](secure-teams-security-isolation.md#create-a-sensitivity-label).</span></span>

## <a name="step-3-configured-the-underlying-sharepoint-site"></a><span data-ttu-id="3db44-127">步骤 3：配置基础 SharePoint 网站</span><span class="sxs-lookup"><span data-stu-id="3db44-127">Step 3: Configured the underlying SharePoint site</span></span>

<span data-ttu-id="3db44-128">首先，为了保护团队对基础 SharePoint 网站的访问，Contoso IT 管理员配置了建议的 [SharePoint 访问策略](../security/office-365-security/sharepoint-file-access-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="3db44-128">First, to protect access to the underlying SharePoint site for the team, Contoso IT administrators configured the [recommended SharePoint access policies](../security/office-365-security/sharepoint-file-access-policies.md).</span></span>

<span data-ttu-id="3db44-129">接下来，他们为网站配置了其他权限设置：</span><span class="sxs-lookup"><span data-stu-id="3db44-129">Next, they configured additional permission settings for the site:</span></span>

- <span data-ttu-id="3db44-130">阻止 Project 2X 组的成员共享对网站的访问权限。</span><span class="sxs-lookup"><span data-stu-id="3db44-130">To prevent Project 2X group members from sharing access to the site.</span></span> <span data-ttu-id="3db44-131">有关配置的详细信息，请参阅 [安全隔离团队的 SharePoint 设置](secure-teams-security-isolation.md#sharepoint-settings)。</span><span class="sxs-lookup"><span data-stu-id="3db44-131">For the configuration details, see [SharePoint settings for a team with security isolation](secure-teams-security-isolation.md#sharepoint-settings).</span></span>
- <span data-ttu-id="3db44-132">对于 Senior Leadership 组的读取权限。</span><span class="sxs-lookup"><span data-stu-id="3db44-132">For Read permissions for the Senior Leadership group.</span></span>

<span data-ttu-id="3db44-133">接下来，他们为网站配置了其他权限设置，以防止 Project 2X 组的成员共享对网站的访问权限。</span><span class="sxs-lookup"><span data-stu-id="3db44-133">Next, they configured additional permission settings for the site to prevent Project 2X group members from sharing access to the site.</span></span> 

<span data-ttu-id="3db44-134">创建 Project 2X 私人频道后，组所有者禁用了来宾共享，将默认共享链接设置为 **"特定人员"** 值。</span><span class="sxs-lookup"><span data-stu-id="3db44-134">As private channels for the Project 2X were created, the group owner disabled guest sharing and set the default sharing link to the **Specific people** value.</span></span>

<span data-ttu-id="3db44-135">下面是具有安全隔离的 Project 2X 团队的配置结果。</span><span class="sxs-lookup"><span data-stu-id="3db44-135">Here is the resulting configuration of the Project 2X team with security isolation.</span></span>

![生成的 Project 2X 团队配置](../media/contoso-team-for-top-secret-project.png)

 ## <a name="step-4-trained-project-2x-team-members"></a><span data-ttu-id="3db44-137">步骤 4：经过培训的 Project 2X 团队成员</span><span class="sxs-lookup"><span data-stu-id="3db44-137">Step 4: Trained Project 2X team members</span></span>

<span data-ttu-id="3db44-138">Contoso 安全人员通过必填课程对 Project 2X 团队成员进行培训，以通过以下方式进行介绍：</span><span class="sxs-lookup"><span data-stu-id="3db44-138">Contoso security staff trained the Project 2X team members in a mandatory course that stepped them through:</span></span>

- <span data-ttu-id="3db44-139">如何访问新的 Project 2X 团队、使用会议和聊天，以及如何协作处理工作组文件。</span><span class="sxs-lookup"><span data-stu-id="3db44-139">How to access the new Project 2X team, use meetings and chats, and how to collaborate on team files.</span></span>
- <span data-ttu-id="3db44-140">如何在团队中创建新文件并上载在本地创建的新文件。</span><span class="sxs-lookup"><span data-stu-id="3db44-140">How to create new files in the team and upload new files created locally.</span></span>
- <span data-ttu-id="3db44-141">如何使用 Project 2X 敏感度标签标记文件。</span><span class="sxs-lookup"><span data-stu-id="3db44-141">How to label files with the Project 2X sensitivity label.</span></span>
- <span data-ttu-id="3db44-142">演示 Project 2X 标签如何保护文件，即使文件离开团队。</span><span class="sxs-lookup"><span data-stu-id="3db44-142">A demonstration of how the Project 2X  label protects a file even when it leaves the team.</span></span>

<span data-ttu-id="3db44-143">最终结果是一个安全环境，Project 2X 团队成员在安全环境中协作处理聊天、会议和文件。</span><span class="sxs-lookup"><span data-stu-id="3db44-143">The end result was a secure environment in which Project 2X team members collaborated in a secure environment for chats, meetings, and files.</span></span>

<span data-ttu-id="3db44-144">下面是一个在基础 Project 2X 网站中存储并分配了 Project 2X 敏感度标签的文件示例。</span><span class="sxs-lookup"><span data-stu-id="3db44-144">Here is an example of a file stored in the underlying Project 2X site with the Project 2X sensitivity label assigned.</span></span>

![存储在基础 Project 2X 网站中的文件示例](../media/contoso-team-for-top-secret-project-example.png)

<span data-ttu-id="3db44-146">在一些实例中，Project 2X 团队成员将受 Project 2X 标签保护的文件下载到本地驱动器以脱机工作。</span><span class="sxs-lookup"><span data-stu-id="3db44-146">In a couple of instances, Project 2X team members downloaded files protected by the Project 2X label to a local drive for offline work.</span></span> 

<span data-ttu-id="3db44-147">但是，在打开凭据时提示输入凭据后，他们意识到自己的错误并将其删除。</span><span class="sxs-lookup"><span data-stu-id="3db44-147">However, after being prompted for credentials when opening them, they realized their mistake and deleted them.</span></span>

<span data-ttu-id="3db44-148">由于 Teams 的协作环境和 Microsoft 365 的安全功能，Project 2X 的详细信息在项目期间一直保密。</span><span class="sxs-lookup"><span data-stu-id="3db44-148">Because of the collaboration environment of Teams and the security features of Microsoft 365, the details of Project 2X were kept secret for the duration of the project.</span></span> <span data-ttu-id="3db44-149">Contoso 宣布其计划，并正在推出新产品和服务，以令其客户和对手的满意以及其竞争对手的 <6>念。</span><span class="sxs-lookup"><span data-stu-id="3db44-149">Contoso announced its plans and is in the process of rolling out the new products and services to the delight of its customers and investors and the chagrin of its competitors.</span></span>

## <a name="next-step"></a><span data-ttu-id="3db44-150">后续步骤</span><span class="sxs-lookup"><span data-stu-id="3db44-150">Next step</span></span>

<span data-ttu-id="3db44-151">[在组织中部署具有安全隔离](secure-teams-security-isolation.md) 的团队。</span><span class="sxs-lookup"><span data-stu-id="3db44-151">[Deploy a team with security isolation](secure-teams-security-isolation.md) in your organization.</span></span>

