---
title: Contoso Corporation 高度机密数字资产的 SharePoint Online 网站
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/15/2019
audience: ITPro
ms.topic: overview
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
ms.custom: Ent_Architecture
description: 摘要： Contoso 如何为高度管控的数据实施 SharePoint Online 网站，以便在研究团队之间更轻松地进行协作。
ms.openlocfilehash: 6c61d02c802a77afeb93a58b59114741c6630f9e
ms.sourcegitcommit: c6eab4a9f1b70e7ff0db6b2a1128a4db2591cbaf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/02/2019
ms.locfileid: "37369523"
---
# <a name="sharepoint-online-site-for-highly-confidential-digital-assets-of-the-contoso-corporation"></a><span data-ttu-id="ba878-103">Contoso Corporation 高度机密数字资产的 SharePoint Online 网站</span><span class="sxs-lookup"><span data-stu-id="ba878-103">SharePoint Online site for highly confidential digital assets of the Contoso Corporation</span></span>

 <span data-ttu-id="ba878-104">**摘要：** Contoso 如何为高度管控的数据实施 SharePoint Online 网站，以便在其研究团队之间实现更好的协作。</span><span class="sxs-lookup"><span data-stu-id="ba878-104">**Summary:** How Contoso implemented a SharePoint Online site for highly regulated data for easier collaboration between its research teams.</span></span>
  
<span data-ttu-id="ba878-105">Contoso 最有价值的资产是采用商业机密的知识产权，如专用的制造技术和开发中的产品的设计规范。</span><span class="sxs-lookup"><span data-stu-id="ba878-105">Contoso's most valuable assets are its intellectual property in the form of trade secrets, such as proprietary manufacturing techniques, and design specifications for products that are in development.</span></span> <span data-ttu-id="ba878-106">这些资产采用数字形式，最初存储为 SharePoint Server 2016 网站上的文件。</span><span class="sxs-lookup"><span data-stu-id="ba878-106">These assets are in digital form, originally stored as files on a SharePoint Server 2016 site.</span></span> <span data-ttu-id="ba878-107">当 Contoso 部署了 Microsoft 365 企业版时，他们希望将其本地数字资产转换为云，以便在巴黎、莫斯科、纽约、北京和 Bangalore 的研究团队中实现更轻松的访问和更多的开放协作。</span><span class="sxs-lookup"><span data-stu-id="ba878-107">When Contoso deployed Microsoft 365 Enterprise, they wanted to transition their on-premises digital assets to the cloud for easier access and more open collaboration across research teams in Paris, Moscow, New York, Beijing, and Bangalore.</span></span> 
  
<span data-ttu-id="ba878-108">但是，由于其敏感性，对这些文件的访问权限必须为：</span><span class="sxs-lookup"><span data-stu-id="ba878-108">However, due to their sensitive nature, access to these files must be:</span></span>

- <span data-ttu-id="ba878-109">限制为允许查看或更改的一组用户，并且仅拥有由 SharePoint 管理员管理的网站的持续权限。</span><span class="sxs-lookup"><span data-stu-id="ba878-109">Restricted to the set of people who are allowed to view or change them, with ongoing permissions for the site administered only by SharePoint admins.</span></span> 
- <span data-ttu-id="ba878-110">受数据丢失防护（DLP）保护，以防止用户在网站外部分发这些文件。</span><span class="sxs-lookup"><span data-stu-id="ba878-110">Protected with Data Loss Prevention (DLP) to prevent users from distributing them outside the site.</span></span>
- <span data-ttu-id="ba878-111">使用访问控制列表进行加密和保护，以防止未经授权的用户访问其内容，即使这些用户在网站外部分发也是如此。</span><span class="sxs-lookup"><span data-stu-id="ba878-111">Encrypted and protected with access control lists to prevent unauthorized users from accessing their contents, even if they are distributed outside the site.</span></span>

<span data-ttu-id="ba878-112">Contoso IT 部门的安全性和 SharePoint 管理员决定将[SharePoint Online 网站用于高度管控的数据](teams-sharepoint-online-sites-highly-regulated-data.md)。</span><span class="sxs-lookup"><span data-stu-id="ba878-112">Security and SharePoint administrators in Contoso's IT department decided to use a [SharePoint Online site for highly regulated data](teams-sharepoint-online-sites-highly-regulated-data.md).</span></span>
  
<span data-ttu-id="ba878-113">Contoso 使用这些步骤为其研究团队创建并保护 SharePoint Online 团队网站。</span><span class="sxs-lookup"><span data-stu-id="ba878-113">Contoso used these steps to create and secure a SharePoint Online team sites for their research teams.</span></span>

## <a name="step-1-reviewed-and-verified-the-members-of-research-team-groups"></a><span data-ttu-id="ba878-114">步骤1：查看并验证了研究团队组的成员</span><span class="sxs-lookup"><span data-stu-id="ba878-114">Step 1: Reviewed and verified the members of research team groups</span></span>

<span data-ttu-id="ba878-115">Contoso IT 管理员对其研究工作组的一组安全组进行了检查。</span><span class="sxs-lookup"><span data-stu-id="ba878-115">Contoso IT admins performed a review of the set of security groups for their research teams.</span></span> <span data-ttu-id="ba878-116">他们删除了不是研究人员或不需要访问调查资产的任何人。</span><span class="sxs-lookup"><span data-stu-id="ba878-116">They removed anyone who was not a researcher or did not need access to research assets.</span></span> 

<span data-ttu-id="ba878-117">它们还创建了以下新的安全组：</span><span class="sxs-lookup"><span data-stu-id="ba878-117">They also and created these new security groups:</span></span>

- <span data-ttu-id="ba878-118">**研究-管理员** 具有对网站的完全控制权限的 SharePoint 管理员集，包括修改权限的能力。</span><span class="sxs-lookup"><span data-stu-id="ba878-118">**Research-Admins**  The set of SharePoint admins that have full control over the site, including the ability to modify permissions.</span></span>
- <span data-ttu-id="ba878-119">**研究-成员** 世界各地的研究团队的一组安全组。</span><span class="sxs-lookup"><span data-stu-id="ba878-119">**Research-Members**  The set of security groups for the research teams around the world.</span></span>
- <span data-ttu-id="ba878-120">**研究-查看者** 一组管理用户（例如，研究组织中的执行人员），它只能查看网站上的资产。</span><span class="sxs-lookup"><span data-stu-id="ba878-120">**Research-Viewers**  The set of management users, such as executives in the research organization, that can only view the assets on the site.</span></span>

## <a name="step-2-created-an-isolated-sharepoint-online-team-site"></a><span data-ttu-id="ba878-121">步骤2：创建了独立的 SharePoint Online 团队网站</span><span class="sxs-lookup"><span data-stu-id="ba878-121">Step 2: Created an isolated SharePoint Online team site</span></span> 

<span data-ttu-id="ba878-122">Contoso SharePoint 管理员首先创建一个名为 "**信息检索**" 的新团队网站。</span><span class="sxs-lookup"><span data-stu-id="ba878-122">Contoso SharePoint admins first created a new team site named **Research**.</span></span> <span data-ttu-id="ba878-123">然后配置它们：</span><span class="sxs-lookup"><span data-stu-id="ba878-123">They then configured:</span></span>

- <span data-ttu-id="ba878-124">使用 "调查所有者" 的 "完全控制" 权限级别，SharePoint 组将 "**研究管理员**" 安全组作为成员</span><span class="sxs-lookup"><span data-stu-id="ba878-124">The Full Control permission level to use the Research Owners SharePoint group, which has the **Research-Admins** security group as a member</span></span>
- <span data-ttu-id="ba878-125">"编辑" 权限级别，以使用 "研究成员" SharePoint 组，其中的 "**调查成员**" 安全组作为成员</span><span class="sxs-lookup"><span data-stu-id="ba878-125">The Edit permission level to use the Research Members SharePoint group, which has the **Research Members** security group as a member</span></span>
- <span data-ttu-id="ba878-126">使用 "搜索访问者" 的 "读取" 权限级别（将 "**调查查看**器" 安全组作为成员）的 SharePoint 组</span><span class="sxs-lookup"><span data-stu-id="ba878-126">The Read permission level to use the Research Visitors SharePoint group, which has the **Research-Viewers** security group as a member</span></span>

<span data-ttu-id="ba878-127">下面是生成的 SharePoint 权限级别、SharePoint 组及其成员。</span><span class="sxs-lookup"><span data-stu-id="ba878-127">Here are the resulting SharePoint permission levels, SharePoint groups, and their members.</span></span>

![SharePoint 权限级别、SharePoint 组及其成员](./media/contoso-sharepoint-online-site-for-highly-confidential-assets/spo-permissions.png)

<span data-ttu-id="ba878-129">接下来，他们配置了对网站的其他限制。</span><span class="sxs-lookup"><span data-stu-id="ba878-129">Next, they configured additional restrictions for the site.</span></span>

<span data-ttu-id="ba878-130">有关配置的详细信息，请参阅[部署独立的 SharePoint Online 团队网站](https://docs.microsoft.com/office365/enterprise/deploy-an-isolated-sharepoint-online-team-site)。</span><span class="sxs-lookup"><span data-stu-id="ba878-130">For the configuration details, see [Deploy an isolated SharePoint Online team site](https://docs.microsoft.com/office365/enterprise/deploy-an-isolated-sharepoint-online-team-site).</span></span>

## <a name="step-3-configured-the-site-for-a-restrictive-dlp-policy"></a><span data-ttu-id="ba878-131">步骤3：为受限制的 DLP 策略配置网站</span><span class="sxs-lookup"><span data-stu-id="ba878-131">Step 3: Configured the site for a restrictive DLP policy</span></span>

<span data-ttu-id="ba878-132">首先，Contoso 管理员将**高度机密**的 Office 365 保留标签应用于**信息检索**网站。</span><span class="sxs-lookup"><span data-stu-id="ba878-132">First, Contoso admins applied the **Highly Confidential** Office 365 retention label to the **Research** site.</span></span>

<span data-ttu-id="ba878-133">接下来，他们创建了一个名为 "**调查**" 的新 OFFICE 365 DLP 策略：</span><span class="sxs-lookup"><span data-stu-id="ba878-133">Next, they created a new Office 365 DLP policy named **Research** that:</span></span>

- <span data-ttu-id="ba878-134">使用 "**高度机密**" Office 365 保留标签。</span><span class="sxs-lookup"><span data-stu-id="ba878-134">Uses the **Highly Confidential** Office 365 retention label.</span></span> 
- <span data-ttu-id="ba878-135">将应用于**信息检索**网站。</span><span class="sxs-lookup"><span data-stu-id="ba878-135">Is applied to the **Research** site.</span></span>
- <span data-ttu-id="ba878-136">当用户尝试在 Contoso 之外的**搜索**网站上共享数字资产时阻止他们。</span><span class="sxs-lookup"><span data-stu-id="ba878-136">Blocks users when they attempt to share a digital asset on the **Research** site outside of Contoso.</span></span>

<span data-ttu-id="ba878-137">有关配置的详细信息，请参阅[使用保留标签和 DLP 保护 SharePoint Online 文件](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-office-365-labels-and-dlp)。</span><span class="sxs-lookup"><span data-stu-id="ba878-137">For the configuration details, see [Protect SharePoint Online files with retention labels and DLP](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-office-365-labels-and-dlp).</span></span>

## <a name="step-4-created-an-azure-information-protection-sub-label-for-the-site"></a><span data-ttu-id="ba878-138">步骤4：为网站创建了 Azure 信息保护子标签</span><span class="sxs-lookup"><span data-stu-id="ba878-138">Step 4: Created an Azure Information Protection sub-label for the site</span></span>

<span data-ttu-id="ba878-139">Contoso admins 在作用域策略中创建了一个新的 Azure 信息保护子标签，其名称为 "**调查**范围策略" 中的默认**高度机密**标签：</span><span class="sxs-lookup"><span data-stu-id="ba878-139">Contoso admins created a new Azure Information Protection sub-label named **Research** of the default **Highly Confidential** label in a scoped policy that:</span></span>

- <span data-ttu-id="ba878-140">需要加密。</span><span class="sxs-lookup"><span data-stu-id="ba878-140">Requires encryption.</span></span>
- <span data-ttu-id="ba878-141">允许由**研究成员**安全组的成员进行完全访问。</span><span class="sxs-lookup"><span data-stu-id="ba878-141">Allows full access by members of the **Research-Members** security group.</span></span>
- <span data-ttu-id="ba878-142">允许由**研究查看者**安全组的成员进行读取访问。</span><span class="sxs-lookup"><span data-stu-id="ba878-142">Allows read access by members of the **Research-Viewers** security group.</span></span>

<span data-ttu-id="ba878-143">接下来，他们将 Azure 信息保护客户端部署到研究团队成员的设备。</span><span class="sxs-lookup"><span data-stu-id="ba878-143">Next, they deployed the Azure Information Protection client to the devices of research team members.</span></span>

<span data-ttu-id="ba878-144">有关配置的详细信息，请参阅[使用 Azure 信息保护保护 SharePoint Online 文件](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-azure-information-protection)。</span><span class="sxs-lookup"><span data-stu-id="ba878-144">For the configuration details, see [Protect SharePoint Online files with Azure Information Protection](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-azure-information-protection).</span></span> 

<span data-ttu-id="ba878-145">以下是针对高度机密资产的**研究**网站的结果配置。</span><span class="sxs-lookup"><span data-stu-id="ba878-145">Here is the resulting configuration of the **Research** site for highly confidential assets.</span></span>

![对高度机密资产的 \* \* 研究 \* \* 网站的结果配置](./media/contoso-sharepoint-online-site-for-highly-confidential-assets/final-config.png)

<span data-ttu-id="ba878-147">**搜索**网站的文件夹中的文件受以下保护：</span><span class="sxs-lookup"><span data-stu-id="ba878-147">Files in folders of the **Research** site are protected by:</span></span>

- <span data-ttu-id="ba878-148">**研究**Azure 信息保护选项，它将加密和 permssions 应用于从**搜索**网站移动或复制文件时携带文件的每个文件。</span><span class="sxs-lookup"><span data-stu-id="ba878-148">The **Research** Azure Information Protection sublabel, which applies encryption and permssions to each file that travel with the file when it is moved or copied from the **Research** site.</span></span>
- <span data-ttu-id="ba878-149">**研究**DLP 策略，它使用**高度敏感**的保留标签和设置，阻止文件与外部用户共享。</span><span class="sxs-lookup"><span data-stu-id="ba878-149">The **Research** DLP policy, which uses the **Highly Sensitive** retention label and settings that prevent the file from being shared with external users.</span></span>
- <span data-ttu-id="ba878-150">一组网站权限，仅允许对**搜索成员**的成员和研究**者**安全组的成员以及**研究管理员**安全组的成员进行管理。</span><span class="sxs-lookup"><span data-stu-id="ba878-150">The set of site permissions, which only allow access to members of the **Research-Members** and **Research-Viewers** security groups and administration by members of the **Research-Admins** security group.</span></span>

## <a name="step-5-migrated-the-on-premises-sharepoint-research-data"></a><span data-ttu-id="ba878-151">步骤5：迁移了本地 SharePoint 研究数据</span><span class="sxs-lookup"><span data-stu-id="ba878-151">Step 5: Migrated the on-premises SharePoint research data</span></span>

<span data-ttu-id="ba878-152">Contoso admins 将本地 SharePoint Server 2016 网站中的所有本地研究文件移至新的**研究**SharePoint Online 网站中的文件夹。</span><span class="sxs-lookup"><span data-stu-id="ba878-152">Contoso admins moved all of the on-premises research files in the on-premises SharePoint Server 2016 site to folders in the new **Research** SharePoint Online site.</span></span>

## <a name="step-6-trained-their-users"></a><span data-ttu-id="ba878-153">步骤6：训练有素的用户</span><span class="sxs-lookup"><span data-stu-id="ba878-153">Step 6: Trained their users</span></span> 

<span data-ttu-id="ba878-154">Contoso 安全员工在强制性课程中培训了研究团队，其中包括：</span><span class="sxs-lookup"><span data-stu-id="ba878-154">Contoso security staff trained the research teams in a mandatory course that stepped them through:</span></span>

- <span data-ttu-id="ba878-155">如何访问新的**研究**SharePoint Online 网站及其现有文件。</span><span class="sxs-lookup"><span data-stu-id="ba878-155">How to access the new **Research** SharePoint Online site and its existing files.</span></span>
- <span data-ttu-id="ba878-156">如何在网站上创建新文件和上传本地存储的新文件。</span><span class="sxs-lookup"><span data-stu-id="ba878-156">How to create new files on the site and upload new files stored locally.</span></span>
- <span data-ttu-id="ba878-157">有关 DLP 策略如何阻止在外部共享文件的演示。</span><span class="sxs-lookup"><span data-stu-id="ba878-157">A demonstration of how the DLP policy blocks files from being shared externally.</span></span>
- <span data-ttu-id="ba878-158">如何使用 Azure 信息保护客户端通过 "**研究**" 子标签为搜索文件添加标签。</span><span class="sxs-lookup"><span data-stu-id="ba878-158">How to use the Azure Information Protection client to label research files with the **Research** sub-label.</span></span>
- <span data-ttu-id="ba878-159">演示如何使用**研究**子标签保护文件，即使它是从网站泄漏的也是如此。</span><span class="sxs-lookup"><span data-stu-id="ba878-159">A demonstration of how the **Research** sub-label protects a file even when it is leaked from the site.</span></span>

<span data-ttu-id="ba878-160">最终结果是一个安全的环境，在该环境中，研究人员可以在安全环境中跨整个组织进行协作。</span><span class="sxs-lookup"><span data-stu-id="ba878-160">The end result is a secure environment in which the researchers can collaborate across the organization in a secure environment.</span></span> 

<span data-ttu-id="ba878-161">如果**与信息检索子标签\*\*\*\*的研究文档**泄露，则仅对使用有效凭据的**搜索成员**和**研究查看者**安全组的成员进行加密和访问。</span><span class="sxs-lookup"><span data-stu-id="ba878-161">If a research document with the **Research** sub-label is leaked from the **Research** site, it is encrypted and accessible only to members of the **Research-Members** and **Research-Viewers** security groups with valid credentials.</span></span>

## <a name="next-step"></a><span data-ttu-id="ba878-162">后续步骤</span><span class="sxs-lookup"><span data-stu-id="ba878-162">Next step</span></span>

<span data-ttu-id="ba878-163">[部署](deploy-microsoft-365-enterprise.md)组织中的 Microsoft 365 企业。</span><span class="sxs-lookup"><span data-stu-id="ba878-163">[Deploy](deploy-microsoft-365-enterprise.md) Microsoft 365 Enterprise in your organization.</span></span>

