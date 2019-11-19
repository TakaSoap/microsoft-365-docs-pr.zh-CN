---
title: Contoso Corporation 的首要项目的团队
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/18/2019
audience: ITPro
ms.topic: overview
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
ms.custom: Ent_Architecture
description: 摘要： Contoso 如何为首要项目的高管控数据使用团队开发一套新的产品和服务。
ms.openlocfilehash: 23a967ea7ffdb3497d705a3ddda4d3c56e415b8e
ms.sourcegitcommit: 0ceb79a633f7004e82b80e69b6f7a7329ccec7ff
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/18/2019
ms.locfileid: "38699882"
---
# <a name="team-for-a-top-secret-project-of-the-contoso-corporation"></a><span data-ttu-id="c39b4-103">Contoso Corporation 的首要项目的团队</span><span class="sxs-lookup"><span data-stu-id="c39b4-103">Team for a top-secret project of the Contoso Corporation</span></span>

<span data-ttu-id="c39b4-104">在执行异地异地工作时，Contoso 首席执行官订购了一系列新产品和服务，在接下来的五年中，这可能会导致 Contoso 的利润加倍。</span><span class="sxs-lookup"><span data-stu-id="c39b4-104">After an executive offsite, Contoso’s CEO ordered the development of a new suite of products and services that could double Contoso’s profits in the next five years.</span></span> <span data-ttu-id="c39b4-105">开发业务、工程和市场计划的首要项目称为**Project 2x** ，而整个公司的主要员工均为 recruited。</span><span class="sxs-lookup"><span data-stu-id="c39b4-105">The top-secret project to develop the business, engineering, and market plan was named **Project 2X** and key staff across the company were recruited.</span></span> 

<span data-ttu-id="c39b4-106">用于研究和开发的时间线是紧密的，这意味着协作必须高效，并提供安全会议、持续会话和文件存储。</span><span class="sxs-lookup"><span data-stu-id="c39b4-106">The timelines for research and development were tight, which meant that collaboration had to be efficient and provide for secure meetings, ongoing conversations, and file storage.</span></span>

<span data-ttu-id="c39b4-107">项目2的结果可交付项是商业计划、产品和工程规范，以及 Word、Excel 和 PowerPoint 文件的格式的营销材料和计划。</span><span class="sxs-lookup"><span data-stu-id="c39b4-107">The resulting deliverables for Project 2X were business plans, product and engineering specifications, and marketing materials and schedules in the form of Word, Excel, and PowerPoint files.</span></span> 

<span data-ttu-id="c39b4-108">由于其敏感性，对这些文件的访问权限为：</span><span class="sxs-lookup"><span data-stu-id="c39b4-108">Due to their sensitive nature, access to these files were:</span></span>

- <span data-ttu-id="c39b4-109">限制为 Project 2X 工作组成员。</span><span class="sxs-lookup"><span data-stu-id="c39b4-109">Restricted to Project 2X team members.</span></span>
- <span data-ttu-id="c39b4-110">使用数据丢失防护（DLP）策略进行保护，以防止 Project 2X 工作组成员在团队外共享这些成员。</span><span class="sxs-lookup"><span data-stu-id="c39b4-110">Protected with a Data Loss Prevention (DLP) policy to prevent Project 2X team members from sharing them outside the team.</span></span>
- <span data-ttu-id="c39b4-111">使用权限进行加密和保护，仅允许访问 Project 2X 团队成员，即使这些文件是在 Contoso 之外分发的也是如此。</span><span class="sxs-lookup"><span data-stu-id="c39b4-111">Encrypted and protected with permissions to allow access only to Project 2X team members, even if the files were distributed outside of Contoso.</span></span>

<span data-ttu-id="c39b4-112">Contoso IT 员工将团队用于项目2X 和这些步骤的[高管控数据](secure-teams-highly-regulated-data-scenario.md)。</span><span class="sxs-lookup"><span data-stu-id="c39b4-112">Contoso IT staff used a [team for highly-regulated data](secure-teams-highly-regulated-data-scenario.md) for Project 2X and these steps.</span></span>

## <a name="step-1-created-a-private-team-and-locked-down-the-underlying-sharepoint-site"></a><span data-ttu-id="c39b4-113">步骤1：创建了一个私有团队并锁定了基础 SharePoint 网站</span><span class="sxs-lookup"><span data-stu-id="c39b4-113">Step 1: Created a private team and locked down the underlying SharePoint site</span></span>

<span data-ttu-id="c39b4-114">若要保护对团队的基础 SharePoint 网站的访问，Contoso IT 管理员配置了[建议的 SharePoint 访问策略](sharepoint-file-access-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="c39b4-114">To protect access to the underlying SharePoint site for the team, Contoso IT administrators configured the [recommended SharePoint access policies](sharepoint-file-access-policies.md).</span></span>

<span data-ttu-id="c39b4-115">接下来，Contoso IT 管理员创建了一个名为 Project 2 的新私人团队，并将 Project 2X 员工的用户帐户添加为成员。</span><span class="sxs-lookup"><span data-stu-id="c39b4-115">Next, a Contoso IT administrator created a new private team named Project 2X and added the user accounts of Project 2X staff as members.</span></span>

<span data-ttu-id="c39b4-116">接下来，他们为网站配置了其他权限设置，以防止 Project 2 共享对网站的访问权限，并阻止其他人请求访问网站。</span><span class="sxs-lookup"><span data-stu-id="c39b4-116">Next, they configured additional permission settings for the site to prevent Project 2X from sharing access to the site and to prevent other from requesting access to the site.</span></span>

<span data-ttu-id="c39b4-117">有关配置的详细信息，请参阅[适用于高度管控团队的 SharePoint 设置](https://docs.microsoft.com/microsoft-365/security/office-365-security/deploy-teams-three-tiers#highly-confidential-teams)。</span><span class="sxs-lookup"><span data-stu-id="c39b4-117">For the configuration details, see [SharePoint settings for a highly regulated team](https://docs.microsoft.com/microsoft-365/security/office-365-security/deploy-teams-three-tiers#highly-confidential-teams).</span></span>

## <a name="step-2-configured-a-dlp-policy-and-the-underlying-site-for-a-retention-label"></a><span data-ttu-id="c39b4-118">步骤2：为保留标签配置了 DLP 策略和基础网站</span><span class="sxs-lookup"><span data-stu-id="c39b4-118">Step 2: Configured a DLP policy and the underlying site for a retention label</span></span> 

<span data-ttu-id="c39b4-119">首先，Contoso 管理员将现有的**高度机密**Office 365 保留标签应用于项目2组基础 SharePoint 网站的 "**文档**" 部分。</span><span class="sxs-lookup"><span data-stu-id="c39b4-119">First, Contoso admins applied the existing **Highly Confidential** Office 365 retention label to the **Documents** section of the underlying SharePoint site of the Project 2X team.</span></span>

<span data-ttu-id="c39b4-120">接下来，他们创建了一个名为**Project 2x**的新 OFFICE 365 DLP 策略，其中：</span><span class="sxs-lookup"><span data-stu-id="c39b4-120">Next, they created a new Office 365 DLP policy named **Project 2X** that:</span></span>

- <span data-ttu-id="c39b4-121">使用 "高度机密" Office 365 保留标签。</span><span class="sxs-lookup"><span data-stu-id="c39b4-121">Uses the Highly Confidential Office 365 retention label.</span></span>
- <span data-ttu-id="c39b4-122">当用户尝试在 Contoso 之外的 Project 2X 工作组中共享文件时，会阻止用户。</span><span class="sxs-lookup"><span data-stu-id="c39b4-122">Blocks users when they attempt to share a file in the Project 2X team outside of Contoso.</span></span>

<span data-ttu-id="c39b4-123">有关配置的详细信息，请参阅[使用保留标签和 DLP 保护团队中的文件](https://docs.microsoft.com/microsoft-365/security/office-365-security/deploy-teams-retention-dlp)。</span><span class="sxs-lookup"><span data-stu-id="c39b4-123">For the configuration details, see [Protect files in teams with retention labels and DLP](https://docs.microsoft.com/microsoft-365/security/office-365-security/deploy-teams-retention-dlp).</span></span>

## <a name="step-3-created-an-office-365-sensitivity-label-for-the-project-2x-team"></a><span data-ttu-id="c39b4-124">步骤3：为项目2团队创建 Office 365 灵敏度标签</span><span class="sxs-lookup"><span data-stu-id="c39b4-124">Step 3: Created an Office 365 sensitivity label for the Project 2X team</span></span>

<span data-ttu-id="c39b4-125">Contoso admins 创建了一个名为**Project 2x**的新 Office 365 敏感度标签，其类型为：</span><span class="sxs-lookup"><span data-stu-id="c39b4-125">Contoso admins created a new Office 365 sensitivity label named **Project 2X** that:</span></span>

- <span data-ttu-id="c39b4-126">需要加密。</span><span class="sxs-lookup"><span data-stu-id="c39b4-126">Requires encryption.</span></span>
- <span data-ttu-id="c39b4-127">允许 "Project 2X Office 365" 组的 "共同创作" 权限。</span><span class="sxs-lookup"><span data-stu-id="c39b4-127">Allows Co-Author permissions for the Project 2X Office 365 group.</span></span>

<span data-ttu-id="c39b4-128">下面是项目2组的结果配置。</span><span class="sxs-lookup"><span data-stu-id="c39b4-128">Here is the resulting configuration of the Project 2X team.</span></span>

![项目2组的结果配置](./media/contoso-team-for-highly-confidential-assets/final-config.png)
 
<span data-ttu-id="c39b4-130">受以下条件保护的基础 Project 2X SharePoint 网站的 "文档" 部分中的文件：</span><span class="sxs-lookup"><span data-stu-id="c39b4-130">Files in the Documents section of the underlying Project 2X SharePoint site were protected by:</span></span>

- <span data-ttu-id="c39b4-131">网站权限，仅允许访问 Project 2X Office 365 组的成员。</span><span class="sxs-lookup"><span data-stu-id="c39b4-131">The site permissions, which only allow access to members of the Project 2X Office 365 group.</span></span>
- <span data-ttu-id="c39b4-132">高度机密的保留标签，将自动分配给新文件。</span><span class="sxs-lookup"><span data-stu-id="c39b4-132">The  Highly Confidential retention label, which is automatically assigned to new files.</span></span>
- <span data-ttu-id="c39b4-133">一种 DLP 策略，它使用阻止文件与外部用户共享的高度机密保留标签和设置。</span><span class="sxs-lookup"><span data-stu-id="c39b4-133">A DLP policy that uses the Highly Confidential retention label and settings that block the file from being shared with external users.</span></span>
- <span data-ttu-id="c39b4-134">Project 2-2 敏感度标签，带有文件移动或复制到网站时携带的加密和权限。</span><span class="sxs-lookup"><span data-stu-id="c39b4-134">The Project 2X sensitivity label, with encryption and permissions that travel with the file if it is moved or copied from the site.</span></span>

<span data-ttu-id="c39b4-135">下面的示例展示了存储在基础项目2X 网站中的文件，该文件具有高度管控的保留标签和分配的 Project 2/2 敏感度标签。</span><span class="sxs-lookup"><span data-stu-id="c39b4-135">Here is an example of a file stored in the underlying Project 2X site with the Highly Regulated retention label and the Project 2X sensitivity label assigned.</span></span>

![存储在基础项目2X 网站中的文件的示例](./media/contoso-team-for-highly-confidential-assets/final-config-example-file.png)
 
## <a name="step-4-trained-project-2x-team-members"></a><span data-ttu-id="c39b4-137">步骤4：训练有素的项目2组成员</span><span class="sxs-lookup"><span data-stu-id="c39b4-137">Step 4: Trained Project 2X team members</span></span>

<span data-ttu-id="c39b4-138">Contoso 安全员工在强制性课程中培训了 Project 2X 团队成员，其中包括：</span><span class="sxs-lookup"><span data-stu-id="c39b4-138">Contoso security staff trained the Project 2X team members in a mandatory course that stepped them through:</span></span>

- <span data-ttu-id="c39b4-139">如何：访问新的 Project 2X 团队、使用会议和聊天以及如何在团队文件中进行协作。</span><span class="sxs-lookup"><span data-stu-id="c39b4-139">How to access the new Project 2X team, use meetings and chats, and how to collaborate on team files.</span></span>
- <span data-ttu-id="c39b4-140">如何：在团队中创建新文件并上载本地创建的新文件。</span><span class="sxs-lookup"><span data-stu-id="c39b4-140">How to create new files in the team and upload new files created locally.</span></span>
- <span data-ttu-id="c39b4-141">有关 DLP 策略如何阻止在外部共享文件的演示。</span><span class="sxs-lookup"><span data-stu-id="c39b4-141">A demonstration of how the DLP policy blocks files from being shared externally.</span></span>
- <span data-ttu-id="c39b4-142">如何使用 Project 2X 敏感度标签标记文件。</span><span class="sxs-lookup"><span data-stu-id="c39b4-142">How to label files with the Project 2X sensitivity label.</span></span>
- <span data-ttu-id="c39b4-143">演示 Project 2X 标签如何保护文件（即使是在离开团队时）。</span><span class="sxs-lookup"><span data-stu-id="c39b4-143">A demonstration of how the Project 2X  label protects a file even when it leaves the team.</span></span>

<span data-ttu-id="c39b4-144">最终结果是一个安全的环境，在此环境中，Project 2X 团队成员在安全环境中共同参与聊天、会议和文件。</span><span class="sxs-lookup"><span data-stu-id="c39b4-144">The end result was a secure environment in which Project 2X team members collaborated in a secure environment for chats, meetings, and files.</span></span>

<span data-ttu-id="c39b4-145">在几个实例中，Project 2X 工作组成员将受 Project 2X 标签保护的文件下载到本地驱动器以供脱机工作。</span><span class="sxs-lookup"><span data-stu-id="c39b4-145">In a couple of instances, Project 2X team members downloaded files protected by the Project 2X label to a local drive for offline work.</span></span> <span data-ttu-id="c39b4-146">但是，在打开凭据后收到凭据提示时，他们会意识到它们的错误并将其删除。</span><span class="sxs-lookup"><span data-stu-id="c39b4-146">However, after being prompted for credentials when opening them, they realized their mistake and deleted them.</span></span>

<span data-ttu-id="c39b4-147">由于团队的协作环境和 Microsoft 365 的安全功能，project 2X 的详细信息在项目的持续时间内保持秘密。</span><span class="sxs-lookup"><span data-stu-id="c39b4-147">Because of the collaboration environment of Teams and the security features of Microsoft 365, the details of Project 2X were kept secret for the duration of the project.</span></span> <span data-ttu-id="c39b4-148">Contoso 宣布了其计划，正在将新产品和服务推出给其客户和投资者的欣喜及其竞争对手的 chagrin 的过程。</span><span class="sxs-lookup"><span data-stu-id="c39b4-148">Contoso announced its plans and is in the process of rolling out the new products and services to the delight of its customers and investors and the chagrin of its competitors.</span></span>

## <a name="next-step"></a><span data-ttu-id="c39b4-149">后续步骤</span><span class="sxs-lookup"><span data-stu-id="c39b4-149">Next step</span></span>

<span data-ttu-id="c39b4-150">[部署](deploy-microsoft-365-enterprise.md)组织中的 Microsoft 365 企业。</span><span class="sxs-lookup"><span data-stu-id="c39b4-150">[Deploy](deploy-microsoft-365-enterprise.md) Microsoft 365 Enterprise in your organization.</span></span>

## <a name="see-also"></a><span data-ttu-id="c39b4-151">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c39b4-151">See also</span></span>

<span data-ttu-id="c39b4-152">[Microsoft 365 工作效率库](https://aka.ms/productivitylibrary) https://aka.ms/productivitylibrary)</span><span class="sxs-lookup"><span data-stu-id="c39b4-152">[Microsoft 365 Productivity Library](https://aka.ms/productivitylibrary) (https://aka.ms/productivitylibrary)</span></span>
