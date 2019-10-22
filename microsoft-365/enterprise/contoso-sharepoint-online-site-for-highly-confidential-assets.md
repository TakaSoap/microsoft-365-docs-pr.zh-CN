---
title: Contoso Corporation 的高度机密数字资产的 SharePoint 网站
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 10/04/2019
audience: ITPro
ms.topic: overview
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
ms.custom: Ent_Architecture
description: 摘要： Contoso 如何为高度管控的数据实现 SharePoint 网站，以便在研究团队之间实现协作。
ms.openlocfilehash: 08676f9fa89d9cbf932f9d70664ad1d17a153e3b
ms.sourcegitcommit: 80dc9ceb14e3eb3ae61b0fc2c8c3d73d564a7ef9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/21/2019
ms.locfileid: "37617250"
---
# <a name="sharepoint-site-for-highly-confidential-digital-assets-of-the-contoso-corporation"></a><span data-ttu-id="40d7c-103">Contoso Corporation 的高度机密数字资产的 SharePoint 网站</span><span class="sxs-lookup"><span data-stu-id="40d7c-103">SharePoint site for highly confidential digital assets of the Contoso Corporation</span></span>

 <span data-ttu-id="40d7c-104">**摘要：** Contoso 如何为高度管控的数据实现 SharePoint 网站，以便在研究团队之间实现协作。</span><span class="sxs-lookup"><span data-stu-id="40d7c-104">**Summary:** How Contoso implemented a SharePoint site for highly regulated data for easier collaboration between its research teams.</span></span>
  
<span data-ttu-id="40d7c-105">Contoso 最有价值的资产是采用商业机密的知识产权，如专用的制造技术和开发中的产品的设计规范。</span><span class="sxs-lookup"><span data-stu-id="40d7c-105">Contoso's most valuable assets are its intellectual property in the form of trade secrets, such as proprietary manufacturing techniques, and design specifications for products that are in development.</span></span> <span data-ttu-id="40d7c-106">这些资产是数字表单，最初存储为 SharePoint Server 2016 网站上的文件。</span><span class="sxs-lookup"><span data-stu-id="40d7c-106">These assets were in digital form, originally stored as files on a SharePoint Server 2016 site.</span></span> <span data-ttu-id="40d7c-107">当 Contoso 部署了 Microsoft 365 企业版时，他们希望将其本地数字资产转换为云，以便在巴黎、莫斯科、纽约、北京和 Bangalore 的研究团队中实现更轻松的访问和更多的开放协作。</span><span class="sxs-lookup"><span data-stu-id="40d7c-107">When Contoso deployed Microsoft 365 Enterprise, they wanted to transition their on-premises digital assets to the cloud for easier access and more open collaboration across research teams in Paris, Moscow, New York, Beijing, and Bangalore.</span></span> 
  
<span data-ttu-id="40d7c-108">但是，由于其敏感性，对这些文件的访问权限必须为：</span><span class="sxs-lookup"><span data-stu-id="40d7c-108">However, due to their sensitive nature, access to these files must be:</span></span>

- <span data-ttu-id="40d7c-109">限制为允许访问它们的一组用户。</span><span class="sxs-lookup"><span data-stu-id="40d7c-109">Restricted to the set of people who are allowed access them.</span></span> 
- <span data-ttu-id="40d7c-110">使用数据丢失防护（DLP）策略进行保护，以防止用户在网站外部分发这些文件。</span><span class="sxs-lookup"><span data-stu-id="40d7c-110">Protected with a Data Loss Prevention (DLP) policy to prevent users from distributing them outside the site.</span></span>
- <span data-ttu-id="40d7c-111">通过对权限进行加密和保护，以防止未经授权的用户访问其内容，即使这些用户在网站外部分发也是如此。</span><span class="sxs-lookup"><span data-stu-id="40d7c-111">Encrypted and protected with permissions to prevent unauthorized users from accessing their contents, even if they are distributed outside the site.</span></span>

<span data-ttu-id="40d7c-112">Contoso IT 部门的安全性和 SharePoint 管理员决定将[SharePoint 网站用于高度管控的数据](teams-sharepoint-online-sites-highly-regulated-data.md)。</span><span class="sxs-lookup"><span data-stu-id="40d7c-112">Security and SharePoint administrators in Contoso's IT department decided to use a [SharePoint site for highly regulated data](teams-sharepoint-online-sites-highly-regulated-data.md).</span></span>
  
<span data-ttu-id="40d7c-113">Contoso 使用这些步骤为自己的研究团队创建并保护 SharePoint 工作组网站。</span><span class="sxs-lookup"><span data-stu-id="40d7c-113">Contoso used these steps to create and secure a SharePoint team sites for their research teams.</span></span>

## <a name="step-1-created-a-private-sharepoint-team-site"></a><span data-ttu-id="40d7c-114">步骤1：创建了私有 SharePoint 团队网站</span><span class="sxs-lookup"><span data-stu-id="40d7c-114">Step 1: Created a private SharePoint team site</span></span>

<span data-ttu-id="40d7c-115">若要保护对 SharePoint 网站的访问，Contoso IT 配置了[建议的 SharePoint 访问策略](sharepoint-file-access-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="40d7c-115">To protect access to the SharePoint site, Contoso IT configured the [recommended SharePoint access policies](sharepoint-file-access-policies.md).</span></span>

<span data-ttu-id="40d7c-116">接下来，Contoso IT 管理员编译了其巴黎、莫斯科、纽约、北京和 Bangalore 办事处中的研究人员的用户帐户列表。</span><span class="sxs-lookup"><span data-stu-id="40d7c-116">Next, Contoso IT admins compiled a list of the user accounts for the researchers in their Paris, Moscow, New York, Beijing, and Bangalore offices.</span></span> 

<span data-ttu-id="40d7c-117">接下来，Contoso IT 管理员创建了名为 "**信息检索**" 的新私有团队网站，并为其研究人员添加了所有用户帐户。</span><span class="sxs-lookup"><span data-stu-id="40d7c-117">Next, a Contoso IT admin created a new private team site named **Research** and added all of the user accounts for its researchers.</span></span>

<span data-ttu-id="40d7c-118">然后，他们为网站配置了其他权限设置，以防止研究人员共享对网站的访问权限，并阻止非工作人员请求访问网站。</span><span class="sxs-lookup"><span data-stu-id="40d7c-118">Then they configured additional permission settings for the site to prevent researchers from sharing access to the site and to prevent non-researchers from requesting access to the site.</span></span>

## <a name="step-2-configured-the-site-for-a-restrictive-dlp-policy"></a><span data-ttu-id="40d7c-119">步骤2：为受限制的 DLP 策略配置网站</span><span class="sxs-lookup"><span data-stu-id="40d7c-119">Step 2: Configured the site for a restrictive DLP policy</span></span>

<span data-ttu-id="40d7c-120">首先，Contoso 管理员将现有的**高机密**Office 365 保留标签应用于**信息检索**网站的 Documents 文件夹。</span><span class="sxs-lookup"><span data-stu-id="40d7c-120">First, Contoso admins applied the existing **Highly Confidential** Office 365 retention label to the Documents folder of the **Research** site.</span></span>

<span data-ttu-id="40d7c-121">接下来，他们创建了一个名为 "**调查**" 的新 OFFICE 365 DLP 策略：</span><span class="sxs-lookup"><span data-stu-id="40d7c-121">Next, they created a new Office 365 DLP policy named **Research** that:</span></span>

- <span data-ttu-id="40d7c-122">使用 "**高度机密**" Office 365 保留标签。</span><span class="sxs-lookup"><span data-stu-id="40d7c-122">Uses the **Highly Confidential** Office 365 retention label.</span></span> 
- <span data-ttu-id="40d7c-123">当用户尝试在 Contoso 之外的**搜索**网站上共享数字资产时阻止他们。</span><span class="sxs-lookup"><span data-stu-id="40d7c-123">Blocks users when they attempt to share a digital asset on the **Research** site outside of Contoso.</span></span>

<span data-ttu-id="40d7c-124">有关配置的详细信息，请参阅[使用保留标签和 DLP 保护 SharePoint 文件](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-office-365-labels-and-dlp)。</span><span class="sxs-lookup"><span data-stu-id="40d7c-124">For the configuration details, see [Protect SharePoint files with retention labels and DLP](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-office-365-labels-and-dlp).</span></span>

## <a name="step-4-created-an-office-365-sensitivity-sublabel-for-the-site"></a><span data-ttu-id="40d7c-125">步骤4：为网站创建了 Office 365 灵敏度选项</span><span class="sxs-lookup"><span data-stu-id="40d7c-125">Step 4: Created an Office 365 sensitivity sublabel for the site</span></span>

<span data-ttu-id="40d7c-126">Contoso admins 创建了一个新的 Office 365 灵敏度选项，其中的 "**高度机密**" 标签的名称为 "**调查团队**"：</span><span class="sxs-lookup"><span data-stu-id="40d7c-126">Contoso admins created a new Office 365 sensitivity sublabel named **Research Teams** of the **Highly Confidential** label that:</span></span>

- <span data-ttu-id="40d7c-127">需要加密。</span><span class="sxs-lookup"><span data-stu-id="40d7c-127">Requires encryption.</span></span>
- <span data-ttu-id="40d7c-128">允许 "**研究**Office 365" 组的 "共同创作" 权限</span><span class="sxs-lookup"><span data-stu-id="40d7c-128">Allows Co-Author permissions for the **Research** Office 365 group</span></span>
- <span data-ttu-id="40d7c-129">适用于**研究**Office 365 组</span><span class="sxs-lookup"><span data-stu-id="40d7c-129">Applies to the **Research** Office 365 group</span></span>

<span data-ttu-id="40d7c-130">以下是针对高度机密资产的**研究**团队网站的结果配置。</span><span class="sxs-lookup"><span data-stu-id="40d7c-130">Here is the resulting configuration of the **Research** team site for highly confidential assets.</span></span>

![针对高度机密资产的研究团队网站的结果配置](./media/contoso-sharepoint-online-site-for-highly-confidential-assets/final-config.png)

<span data-ttu-id="40d7c-132">**搜索**网站的文件夹中的文件受以下保护：</span><span class="sxs-lookup"><span data-stu-id="40d7c-132">Files in folders of the **Research** site are protected by:</span></span>

- <span data-ttu-id="40d7c-133">网站权限，仅允许访问**研究**Office 365 组的成员。</span><span class="sxs-lookup"><span data-stu-id="40d7c-133">The site permissions, which only allow access to members of the **Research** Office 365 group.</span></span>
- <span data-ttu-id="40d7c-134">**研究**DLP 策略，它使用**高度机密**的保留标签和阻止文件与外部用户共享的设置。</span><span class="sxs-lookup"><span data-stu-id="40d7c-134">The **Research** DLP policy, which uses the **Highly Confidential** retention label and settings that prevent the file from being shared with external users.</span></span>
- <span data-ttu-id="40d7c-135">**研究团队**敏感度选项，其中包含在文件移动或复制到**信息检索**网站时携带的加密和权限。</span><span class="sxs-lookup"><span data-stu-id="40d7c-135">The **Research Teams** sensitivity sublabel, with encryption and permissions that travel with the file if it is moved or copied from the **Research** site.</span></span>

<span data-ttu-id="40d7c-136">下面的示例展示了一个存储在**研究**网站中的文件，其中包含已分配的**研究团队**敏感度选项。</span><span class="sxs-lookup"><span data-stu-id="40d7c-136">Here is an example of a file stored in the **Research** site with the **Research Teams** sensitivity sublabel assigned.</span></span>

![针对高度机密资产的研究团队网站的结果配置](./media/contoso-sharepoint-online-site-for-highly-confidential-assets/final-config-example-file.png)


## <a name="step-5-migrated-the-on-premises-sharepoint-research-data"></a><span data-ttu-id="40d7c-138">步骤5：迁移了本地 SharePoint 研究数据</span><span class="sxs-lookup"><span data-stu-id="40d7c-138">Step 5: Migrated the on-premises SharePoint research data</span></span>

<span data-ttu-id="40d7c-139">Contoso admins 将本地 SharePoint Server 2016 网站中的所有本地研究文件移至新的**研究**SharePoint 网站中的文件夹。</span><span class="sxs-lookup"><span data-stu-id="40d7c-139">Contoso admins moved all of the on-premises research files in the on-premises SharePoint Server 2016 site to folders in the new **Research** SharePoint site.</span></span>

## <a name="step-6-trained-their-researchers"></a><span data-ttu-id="40d7c-140">步骤6：训练有素的研究人员</span><span class="sxs-lookup"><span data-stu-id="40d7c-140">Step 6: Trained their researchers</span></span>

<span data-ttu-id="40d7c-141">Contoso 安全员工在强制性课程中培训了**研究**Office 365 组的成员，其中包括：</span><span class="sxs-lookup"><span data-stu-id="40d7c-141">Contoso security staff trained the members of the **Research** Office 365 group in a mandatory course that stepped them through:</span></span>

- <span data-ttu-id="40d7c-142">如何访问新的**研究**网站及其现有文件。</span><span class="sxs-lookup"><span data-stu-id="40d7c-142">How to access the new **Research** site and its existing files.</span></span>
- <span data-ttu-id="40d7c-143">如何在网站上创建新文件和上传本地存储的新文件。</span><span class="sxs-lookup"><span data-stu-id="40d7c-143">How to create new files on the site and upload new files stored locally.</span></span>
- <span data-ttu-id="40d7c-144">有关**信息检索**DLP 策略如何阻止在外部共享文件的演示。</span><span class="sxs-lookup"><span data-stu-id="40d7c-144">A demonstration of how the **Research** DLP policy blocks files from being shared externally.</span></span>
- <span data-ttu-id="40d7c-145">如何使用**研究团队**敏感度选项标记文件。</span><span class="sxs-lookup"><span data-stu-id="40d7c-145">How to label files with the **Research Teams** sensitivity sublabel.</span></span>
- <span data-ttu-id="40d7c-146">演示如何使用**研究团队**子标签来保护文件，即使它是从网站泄漏的也是如此。</span><span class="sxs-lookup"><span data-stu-id="40d7c-146">A demonstration of how the **Research Teams** sub-label protects a file even when it is leaked from the site.</span></span>

<span data-ttu-id="40d7c-147">最终结果是一个安全的环境，在该环境中，研究人员可以在包含信息检索信息的文件的安全环境中跨 Contoso 进行协作。</span><span class="sxs-lookup"><span data-stu-id="40d7c-147">The end result is a secure environment in which the researchers can collaborate across Contoso in a secure environment on files containing research information.</span></span> 

<span data-ttu-id="40d7c-148">如果与**研究团队**选项的研究文档保留了**信息检索**网站，则只有具有有效用户帐户凭据的**研究**Office 365 组的成员才能对其进行加密和访问。</span><span class="sxs-lookup"><span data-stu-id="40d7c-148">If a research document with the **Research Teams** sublabel leaves the **Research** site, it is encrypted and accessible only to members of the **Research** Office 365 group with valid user account credentials.</span></span>

## <a name="next-step"></a><span data-ttu-id="40d7c-149">后续步骤</span><span class="sxs-lookup"><span data-stu-id="40d7c-149">Next step</span></span>

<span data-ttu-id="40d7c-150">[部署](deploy-microsoft-365-enterprise.md)组织中的 Microsoft 365 企业。</span><span class="sxs-lookup"><span data-stu-id="40d7c-150">[Deploy](deploy-microsoft-365-enterprise.md) Microsoft 365 Enterprise in your organization.</span></span>

## <a name="see-also"></a><span data-ttu-id="40d7c-151">另请参阅</span><span class="sxs-lookup"><span data-stu-id="40d7c-151">See also</span></span>

<span data-ttu-id="40d7c-152">[Microsoft 365 工作效率库](https://aka.ms/productivitylibrary) https://aka.ms/productivitylibrary)</span><span class="sxs-lookup"><span data-stu-id="40d7c-152">[Microsoft 365 Productivity Library](https://aka.ms/productivitylibrary) (https://aka.ms/productivitylibrary)</span></span>
