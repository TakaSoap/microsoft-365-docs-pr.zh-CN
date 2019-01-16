---
title: Contoso 公司的高度机密数字资产的 SharePoint Online 网站
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/01/2018
ms.audience: ITPro
ms.topic: overview
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
ms.custom: Ent_Architecture
description: 摘要： 如何 Contoso 实现的 SharePoint Online 网站高度监管的数据之间其研究更轻松地协作的团队。
ms.openlocfilehash: 697ddb27b56fd529e9c73b89d9f07b8731ad76c3
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/16/2019
ms.locfileid: "26865990"
---
# <a name="sharepoint-online-site-for-highly-confidential-digital-assets-of-the-contoso-corporation"></a><span data-ttu-id="82747-103">Contoso 公司的高度机密数字资产的 SharePoint Online 网站</span><span class="sxs-lookup"><span data-stu-id="82747-103">SharePoint Online site for highly confidential digital assets of the Contoso Corporation</span></span>

 <span data-ttu-id="82747-104">**摘要：** 如何 Contoso 实现其信息检索团队之间的更轻松地协作的高度管控数据的 SharePoint Online 网站。</span><span class="sxs-lookup"><span data-stu-id="82747-104">**Summary:** How Contoso implemented a SharePoint Online site for highly regulated data for easier collaboration between its research teams.</span></span>
  
<span data-ttu-id="82747-p101">Contoso 的最有价值资产其知识产权的交易机密，如专有制造技术的窗体，并设计规范中开发的产品。这些资产相关数字形式，最初存储为 SharePoint Server 2016 网站上的文件。当 Contoso 部署 Microsoft 365 企业版时，他们希望跨研究 リ モ ・ 巴黎、 莫斯科，纽约、 北京和班加罗尔转换到云中更轻松地访问和更多 open 协作其内部部署数字资产。</span><span class="sxs-lookup"><span data-stu-id="82747-p101">Contoso's most valuable assets are its intellectual property in the form of trade secrets, such as proprietary manufacturing techniques, and design specifications for products that are in development. These assets are in digital form, originally stored as files on a SharePoint Server 2016 site. When Contoso deployed Microsoft 365 Enterprise, they wanted to transition their on-premises digital assets to the cloud for easier access and more open collaboration across research teams in Paris, Moscow, New York, Beijing, and Bangalore.</span></span> 
  
<span data-ttu-id="82747-108">但是，由于其敏感性，必须将访问这些文件：</span><span class="sxs-lookup"><span data-stu-id="82747-108">However, due to their sensitive nature, access to these files must be:</span></span>

- <span data-ttu-id="82747-109">限制为一组允许查看或更改它们与持续仅由 SharePoint 管理员管理网站的权限的人员。</span><span class="sxs-lookup"><span data-stu-id="82747-109">Restricted to the set of people who are allowed to view or change them, with ongoing permissions for the site administered only by SharePoint admins.</span></span> 
- <span data-ttu-id="82747-110">保护与数据丢失防护 (DLP) 若要防止用户分发这些外部网站。</span><span class="sxs-lookup"><span data-stu-id="82747-110">Protected with Data Loss Prevention (DLP) to prevent users from distributing them outside the site.</span></span>
- <span data-ttu-id="82747-111">加密和与受保护的访问控制列表以防止未经授权的用户访问其内容，即使它们外部网站分发。</span><span class="sxs-lookup"><span data-stu-id="82747-111">Encrypted and protected with access control lists to prevent unauthorized users from accessing their contents, even if they are distributed outside the site.</span></span>

<span data-ttu-id="82747-112">Contoso 中的安全和 SharePoint 管理员的 IT 部门决定使用[SharePoint Online 网站高度管控数据](teams-sharepoint-online-sites-highly-regulated-data.md)。</span><span class="sxs-lookup"><span data-stu-id="82747-112">Security and SharePoint administrators in Contoso's IT department decided to use a [SharePoint Online site for highly regulated data](teams-sharepoint-online-sites-highly-regulated-data.md).</span></span>
  
<span data-ttu-id="82747-113">Contoso 使用以下步骤来创建和保护其研究团队 SharePoint Online 团队网站。</span><span class="sxs-lookup"><span data-stu-id="82747-113">Contoso used these steps to create and secure a SharePoint Online team sites for their research teams.</span></span>

## <a name="step-1-reviewed-and-verified-the-members-of-research-team-groups"></a><span data-ttu-id="82747-114">步骤 1： 检查和验证的信息检索团队组成员</span><span class="sxs-lookup"><span data-stu-id="82747-114">Step 1: Reviewed and verified the members of research team groups</span></span>

<span data-ttu-id="82747-p102">Contoso IT 管理员执行的安全组设置查看其研究团队。中删除这些人不是一位研究或不需要对研究资产的访问。</span><span class="sxs-lookup"><span data-stu-id="82747-p102">Contoso IT admins performed a review of the set of security groups for their research teams. They removed anyone who was not a researcher or did not need access to research assets.</span></span> 

<span data-ttu-id="82747-117">他们还和创建这些新的安全组：</span><span class="sxs-lookup"><span data-stu-id="82747-117">They also and created these new security groups:</span></span>

- <span data-ttu-id="82747-118">**研究管理员** SharePoint 管理员具有完全控制的网站，其中包括可以修改权限集。</span><span class="sxs-lookup"><span data-stu-id="82747-118">**Research-Admins**  The set of SharePoint admins that have full control over the site, including the ability to modify permissions.</span></span>
- <span data-ttu-id="82747-119">**研究成员** 世界各地的信息检索小组的安全组的集合。</span><span class="sxs-lookup"><span data-stu-id="82747-119">**Research Members**  The set of security groups for the research teams around the world.</span></span>
- <span data-ttu-id="82747-120">**研究查看器** 管理用户，例如，可以查看网站的资产的信息检索组织中的执行官集。</span><span class="sxs-lookup"><span data-stu-id="82747-120">**Research-Viewers**  The set of management users, such as executives in the research organization, that can view the assets on the site.</span></span>

## <a name="step-2-created-an-isolated-sharepoint-online-team-site"></a><span data-ttu-id="82747-121">步骤 2： 创建独立的 SharePoint Online 团队网站</span><span class="sxs-lookup"><span data-stu-id="82747-121">Step 2: Created an isolated SharePoint Online team site</span></span> 

<span data-ttu-id="82747-p103">首次创建新的工作组网站的 Contoso SharePoint admins 名为**研究**。它们然后配置：</span><span class="sxs-lookup"><span data-stu-id="82747-p103">Contoso SharePoint admins first created a new team site named **Research**. They then configured:</span></span>

- <span data-ttu-id="82747-124">要使用的信息检索所有者 SharePoint 组中，上面有**研究管理员**安全组成员身份的完全控制权限级别</span><span class="sxs-lookup"><span data-stu-id="82747-124">The Full Control permission level to use the Research Owners SharePoint group, which has the **Research-Admins** security group as a member</span></span>
- <span data-ttu-id="82747-125">编辑权限级别，以使用研究成员 SharePoint 组中，已作为成员的**信息检索成员**安全组</span><span class="sxs-lookup"><span data-stu-id="82747-125">The Edit permission level to use the Research Members SharePoint group, which has the **Research Members** security group as a member</span></span>
- <span data-ttu-id="82747-126">读取权限级别，若要使用的信息检索访问者 SharePoint 组中，上面有**研究查看者**安全组成员身份</span><span class="sxs-lookup"><span data-stu-id="82747-126">The Read permission level to use the Research Visitors SharePoint group, which has the **Research-Viewers** security group as a member</span></span>

<span data-ttu-id="82747-127">下面是生成的 SharePoint 权限级别、 SharePoint 组和及其成员。</span><span class="sxs-lookup"><span data-stu-id="82747-127">Here are the resulting SharePoint permission levels, SharePoint groups, and their members.</span></span>

![](./media/contoso-sharepoint-online-site-for-highly-confidential-assets/spo-permissions.png)

<span data-ttu-id="82747-128">接下来，它们配置网站的其他限制。</span><span class="sxs-lookup"><span data-stu-id="82747-128">Next, they configured additional restrictions for the site.</span></span>

<span data-ttu-id="82747-129">有关配置的详细信息，请参阅[部署独立的 SharePoint Online 团队网站](https://docs.microsoft.com/office365/enterprise/deploy-an-isolated-sharepoint-online-team-site)。</span><span class="sxs-lookup"><span data-stu-id="82747-129">For the configuration details, see [Deploy an isolated SharePoint Online team site](https://docs.microsoft.com/office365/enterprise/deploy-an-isolated-sharepoint-online-team-site).</span></span>

## <a name="step-3-configured-the-site-for-a-restrictive-office-365-label-dlp-policy"></a><span data-ttu-id="82747-130">步骤 3： 配置严格的 Office 365 标签 DLP 策略的站点</span><span class="sxs-lookup"><span data-stu-id="82747-130">Step 3: Configured the site for a restrictive Office 365 label DLP policy</span></span>

<span data-ttu-id="82747-131">首先，Contoso admins 应用到**Research**网站的**高度机密**的 Office 365 标签。</span><span class="sxs-lookup"><span data-stu-id="82747-131">First, Contoso admins applied the **Highly Confidential** Office 365 label to the **Research** site.</span></span>

<span data-ttu-id="82747-132">接下来，创建一个新 Office 365 DLP 策略名为**Research**的：</span><span class="sxs-lookup"><span data-stu-id="82747-132">Next, they created a new Office 365 DLP policy named **Research** that:</span></span>

- <span data-ttu-id="82747-133">使用**高度机密**的 Office 365 标签。</span><span class="sxs-lookup"><span data-stu-id="82747-133">Uses the **Highly Confidential** Office 365 label.</span></span> 
- <span data-ttu-id="82747-134">应用于**Research**网站。</span><span class="sxs-lookup"><span data-stu-id="82747-134">Is applied to the **Research** site.</span></span>
- <span data-ttu-id="82747-135">防止用户共享文档。</span><span class="sxs-lookup"><span data-stu-id="82747-135">Prevents users from sharing documents.</span></span>

<span data-ttu-id="82747-136">配置详细信息，请参阅[Office 365 标签和 DLP 保护 SharePoint Online 文件](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-office-365-labels-and-dlp)。</span><span class="sxs-lookup"><span data-stu-id="82747-136">For the configuration details, see [Protect SharePoint Online files with Office 365 labels and DLP](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-office-365-labels-and-dlp).</span></span>

## <a name="step-4-created-an-azure-information-protection-sub-label-for-the-site"></a><span data-ttu-id="82747-137">步骤 4： 创建网站 Azure 信息保护子标签</span><span class="sxs-lookup"><span data-stu-id="82747-137">Step 4: Created an Azure Information Protection sub-label for the site</span></span>

<span data-ttu-id="82747-138">创建一个新的 Azure 信息保护子标签的 Contoso admins 名为**Research**的作用域策略中的默认**高度机密**标签的：</span><span class="sxs-lookup"><span data-stu-id="82747-138">Contoso admins created a new Azure Information Protection sub-label named **Research** of the default **Highly Confidential** label in a scoped policy that:</span></span>

- <span data-ttu-id="82747-139">要求加密。</span><span class="sxs-lookup"><span data-stu-id="82747-139">Requires encryption.</span></span>
- <span data-ttu-id="82747-140">允许通过**Research 成员**安全组的成员的完全访问权限。</span><span class="sxs-lookup"><span data-stu-id="82747-140">Allows full access by members of the **Research Members** security group.</span></span>
- <span data-ttu-id="82747-141">允许**研究查看者**安全组的成员的读访问权限。</span><span class="sxs-lookup"><span data-stu-id="82747-141">Allows read access by members of the **Research Viewers** security group.</span></span>

<span data-ttu-id="82747-142">接下来，它们部署到的设备研究小组成员的 Azure 信息保护客户端。</span><span class="sxs-lookup"><span data-stu-id="82747-142">Next, they deployed the Azure Information Protection client to the devices of research team members.</span></span>

<span data-ttu-id="82747-143">有关配置详细信息，请参阅[Azure 信息保护保护 SharePoint Online 文件](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-azure-information-protection)。</span><span class="sxs-lookup"><span data-stu-id="82747-143">For the configuration details, see [Protect SharePoint Online files with Azure Information Protection](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-azure-information-protection).</span></span> 

<span data-ttu-id="82747-144">下面是生成的高度机密资产的**信息检索**网站配置。</span><span class="sxs-lookup"><span data-stu-id="82747-144">Here is the resulting configuration of the **Research** site for highly confidential assets.</span></span>

![](./media/contoso-sharepoint-online-site-for-highly-confidential-assets/final-config.png)

## <a name="step-5-migrated-the-on-premises-sharepoint-research-data"></a><span data-ttu-id="82747-145">步骤 5： 迁移的本地 SharePoint 研究数据</span><span class="sxs-lookup"><span data-stu-id="82747-145">Step 5: Migrated the on-premises SharePoint research data</span></span>

<span data-ttu-id="82747-146">Contoso admins 移动内部部署的所有调查中新的**研究**SharePoint Online 站点中的文件夹的内部部署 SharePoint Server 2016 网站的文件。</span><span class="sxs-lookup"><span data-stu-id="82747-146">Contoso admins moved all of the on-premises research files in the on-premises SharePoint Server 2016 site to folders in the new **Research** SharePoint Online site.</span></span>

## <a name="step-6-trained-their-users"></a><span data-ttu-id="82747-147">步骤 6： 培训用户</span><span class="sxs-lookup"><span data-stu-id="82747-147">Step 6: Trained their users</span></span> 

<span data-ttu-id="82747-148">Contoso 安全人员培训研究 リ モ ・ 强制课程单它们通过执行：</span><span class="sxs-lookup"><span data-stu-id="82747-148">Contoso security staff trained the research teams in a mandatory course that stepped them through:</span></span>

- <span data-ttu-id="82747-149">如何访问新的**研究**SharePoint Online 网站和其现有的文件。</span><span class="sxs-lookup"><span data-stu-id="82747-149">How to access the new **Research** SharePoint Online site and its existing files.</span></span>
- <span data-ttu-id="82747-150">如何在网站上创建新文件和上传本地存储的新文件。</span><span class="sxs-lookup"><span data-stu-id="82747-150">How to create new files on the site and upload new files stored locally.</span></span>
- <span data-ttu-id="82747-151">演示如何的 DLP 策略阻止从外部共享文件。</span><span class="sxs-lookup"><span data-stu-id="82747-151">A demonstration of how the DLP policy blocks files from being shared externally.</span></span>
- <span data-ttu-id="82747-152">如何使用 Azure 信息保护客户端标签研究**信息检索**子标签文件。</span><span class="sxs-lookup"><span data-stu-id="82747-152">How to use the Azure Information Protection client to label research files with the **Research** sub-label.</span></span>
- <span data-ttu-id="82747-153">**研究**子标签如何保护文件，即使它从网站泄露演示。</span><span class="sxs-lookup"><span data-stu-id="82747-153">A demonstration of how the **Research** sub-label protects a file even when it is leaked from the site.</span></span>

<span data-ttu-id="82747-154">最终结果是安全的环境中文档的科学家可以安全环境中在组织内进行协作。</span><span class="sxs-lookup"><span data-stu-id="82747-154">The end result is a secure environment in which the researchers can collaborate across the organization in a secure environment.</span></span> 

<span data-ttu-id="82747-155">如果从**Research**网站被泄露**研究**子标签研究文档，则加密和仅使用有效的凭据的**信息检索成员**和**研究查看者**安全组的成员才能访问。</span><span class="sxs-lookup"><span data-stu-id="82747-155">If a research document with the **Research** sub-label is leaked from the **Research** site, it is encrypted and accessible only to members of the **Research Members** and **Research Viewers** security groups with valid credentials.</span></span>

## <a name="next-step"></a><span data-ttu-id="82747-156">后续步骤</span><span class="sxs-lookup"><span data-stu-id="82747-156">Next step</span></span>

<span data-ttu-id="82747-157">在组织中[部署](deploy-microsoft-365-enterprise.md) Microsoft 365 企业版。</span><span class="sxs-lookup"><span data-stu-id="82747-157">[Deploy](deploy-microsoft-365-enterprise.md) Microsoft 365 Enterprise in your organization.</span></span>

