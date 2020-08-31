---
title: 向应用商店中的未成年人和收购外接程序
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 737e8c86-be63-44d7-bf02-492fa7cd9c3f
description: 了解常规数据保护法规 (GDPR) 管理未成年人的个人数据的管理法规。
ms.openlocfilehash: a738e22a0ac0b995c8e44fcf4cc5a2eb47375be5
ms.sourcegitcommit: 555d756c69ac9031d1fb928f2e1f9750beede066
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/29/2020
ms.locfileid: "47306547"
---
# <a name="minors-and-acquiring-add-ins-from-the-store"></a><span data-ttu-id="37330-103">向应用商店中的未成年人和收购外接程序</span><span class="sxs-lookup"><span data-stu-id="37330-103">Minors and acquiring add-ins from the Store</span></span>

<span data-ttu-id="37330-104">一般数据保护法规 (GDPR) 是一种欧洲联合法规，生效时间可能为25，2018。</span><span class="sxs-lookup"><span data-stu-id="37330-104">The General Data Protection Regulation (GDPR) is a European Union regulation that becomes effective May 25, 2018.</span></span> <span data-ttu-id="37330-105">它向用户提供对其数据的权限并加以保护。</span><span class="sxs-lookup"><span data-stu-id="37330-105">It gives users rights to and protection of their data.</span></span> <span data-ttu-id="37330-106">GDPR 的其中一个方面是，未成年人的个人数据不能发送给其家长或监护人尚未批准的当事人。</span><span class="sxs-lookup"><span data-stu-id="37330-106">One of the aspects of the GDPR is that minors cannot have their personal data sent to parties that their parent or guardian hasn't approved.</span></span> <span data-ttu-id="37330-107">定义为次要的特定年龄取决于个人所在的区域。</span><span class="sxs-lookup"><span data-stu-id="37330-107">The specific age defined as a minor depends on the region where the individual is located.</span></span>
  
<span data-ttu-id="37330-108">具有关于家长同意的法令法规的地区包括美国、韩国、英国和欧盟。</span><span class="sxs-lookup"><span data-stu-id="37330-108">Regions that have statutory regulations about parental consent include the United States, South Korea, the United Kingdom, and the European Union.</span></span> <span data-ttu-id="37330-109">对于这些区域，将通过 Azure Active Directory)  (阻止从存储中获取任何新的 Office 外接程序，并运行之前获取的外接程序，从而阻止了次要区域。</span><span class="sxs-lookup"><span data-stu-id="37330-109">For those regions, a minor will be blocked (via Azure Active Directory) from getting any new Office add-ins from the Store and running add-ins that were previously acquired.</span></span> <span data-ttu-id="37330-110">对于没有法令法规的国家/地区，将不提供下载限制。</span><span class="sxs-lookup"><span data-stu-id="37330-110">For countries without statutory regulations, there will be no download restrictions.</span></span>
  
<span data-ttu-id="37330-111">根据 Azure Active Directory 中指定的数据，将用户确定为次要用户。</span><span class="sxs-lookup"><span data-stu-id="37330-111">A user is determined to be a minor based on data specified in Azure Active Directory.</span></span> <span data-ttu-id="37330-112">组织管理员负责声明法律年龄组和该用户的家长同意。</span><span class="sxs-lookup"><span data-stu-id="37330-112">The organization admin is responsible for declaring the legal age group and the parental consent for that user.</span></span>
  
<span data-ttu-id="37330-113">如果父/监护人同意使用特定的外接程序，组织管理员可以使用集中部署将该外接程序部署到所有已同意的未成年人。</span><span class="sxs-lookup"><span data-stu-id="37330-113">If the parent/guardian consents to a minor using a specific add-In, then the organization admin can use centralized deployment to deploy that add-In to all minors who have consent.</span></span>
  
<span data-ttu-id="37330-114">若要符合 GDPR 的要求，您需要确保在学校/组织中部署以下 Office 内部版本之一。</span><span class="sxs-lookup"><span data-stu-id="37330-114">To be GDPR compliant for minors you need to ensure that one of following builds of Office is deployed in your school/organization.</span></span>
 
 <span data-ttu-id="37330-115">**对于 Word、Excel、PowerPoint 和 Project**：</span><span class="sxs-lookup"><span data-stu-id="37330-115">**For Word, Excel, PowerPoint, and Project**:</span></span> 

|<span data-ttu-id="37330-116">**平台**</span><span class="sxs-lookup"><span data-stu-id="37330-116">**Platform**</span></span> <br/> |<span data-ttu-id="37330-117">**内部版本号**</span><span class="sxs-lookup"><span data-stu-id="37330-117">**Build number**</span></span> <br/> |
|:-----|:-----|
|<span data-ttu-id="37330-118">适用于企业版 (当前频道) 的 Microsoft 365 应用程序</span><span class="sxs-lookup"><span data-stu-id="37330-118">Microsoft 365 Apps for enterprise (Current Channel)</span></span>  <br/> |<span data-ttu-id="37330-119">9001.2138</span><span class="sxs-lookup"><span data-stu-id="37330-119">9001.2138</span></span>   <br/> |
|<span data-ttu-id="37330-120">适用于企业版的 Microsoft 365 应用 (半年企业频道) </span><span class="sxs-lookup"><span data-stu-id="37330-120">Microsoft 365 Apps for enterprise (Semi-Annual Enterprise Channel)</span></span>  <br/> |<span data-ttu-id="37330-121">8431.2159</span><span class="sxs-lookup"><span data-stu-id="37330-121">8431.2159</span></span>  <br/> |
|<span data-ttu-id="37330-122">Office 2016 for Windows</span><span class="sxs-lookup"><span data-stu-id="37330-122">Office 2016 for Windows</span></span>  <br/> |<span data-ttu-id="37330-123">16.0.4672.1000</span><span class="sxs-lookup"><span data-stu-id="37330-123">16.0.4672.1000</span></span>  <br/> |
|<span data-ttu-id="37330-124">Office 2013 for Windows</span><span class="sxs-lookup"><span data-stu-id="37330-124">Office 2013 for Windows</span></span>  <br/> |<span data-ttu-id="37330-125">15.0.5023.1000</span><span class="sxs-lookup"><span data-stu-id="37330-125">15.0.5023.1000</span></span>  <br/> |
|<span data-ttu-id="37330-126">Office 2016 for Mac</span><span class="sxs-lookup"><span data-stu-id="37330-126">Office 2016 for Mac</span></span>  <br/> |<span data-ttu-id="37330-127">16.11.18020200</span><span class="sxs-lookup"><span data-stu-id="37330-127">16.11.18020200</span></span>  <br/> |
|<span data-ttu-id="37330-128">Office 网页版</span><span class="sxs-lookup"><span data-stu-id="37330-128">Office for the web</span></span>  <br/> |<span data-ttu-id="37330-129">无</span><span class="sxs-lookup"><span data-stu-id="37330-129">N/A</span></span>  <br/> |
   
 <span data-ttu-id="37330-130">**对于 Outlook**：</span><span class="sxs-lookup"><span data-stu-id="37330-130">**For Outlook**:</span></span> 
  
|<span data-ttu-id="37330-131">**平台**</span><span class="sxs-lookup"><span data-stu-id="37330-131">**Platform**</span></span> <br/> |<span data-ttu-id="37330-132">**内部版本号**</span><span class="sxs-lookup"><span data-stu-id="37330-132">**Build number**</span></span> <br/> |
|:-----|:-----|
|<span data-ttu-id="37330-133">适用于 Windows (MSI) 的 Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="37330-133">Outlook 2016 for Windows (MSI)</span></span>  <br/> |<span data-ttu-id="37330-134">生成不 TBD</span><span class="sxs-lookup"><span data-stu-id="37330-134">Build No TBD</span></span>  <br/> |
|<span data-ttu-id="37330-135">Outlook 2016 for Windows (C2R) </span><span class="sxs-lookup"><span data-stu-id="37330-135">Outlook 2016 for Windows (C2R)</span></span>  <br/> |<span data-ttu-id="37330-136">16.0.9323.1000</span><span class="sxs-lookup"><span data-stu-id="37330-136">16.0.9323.1000</span></span>  <br/> |
|<span data-ttu-id="37330-137">Office 2016 for Mac</span><span class="sxs-lookup"><span data-stu-id="37330-137">Office 2016 for Mac</span></span>  <br/> |<span data-ttu-id="37330-138">16.0.9318.1000</span><span class="sxs-lookup"><span data-stu-id="37330-138">16.0.9318.1000</span></span>  <br/> |
|<span data-ttu-id="37330-139">适用于 iOS 的 Outlook mobile</span><span class="sxs-lookup"><span data-stu-id="37330-139">Outlook mobile for iOS</span></span>  <br/> |<span data-ttu-id="37330-140">2.75.0</span><span class="sxs-lookup"><span data-stu-id="37330-140">2.75.0</span></span>  <br/> |
|<span data-ttu-id="37330-141">Outlook mobile for Android</span><span class="sxs-lookup"><span data-stu-id="37330-141">Outlook mobile for Android</span></span>  <br/> |<span data-ttu-id="37330-142">2.2.145</span><span class="sxs-lookup"><span data-stu-id="37330-142">2.2.145</span></span>  <br/> |
|<span data-ttu-id="37330-143">Outlook.com</span><span class="sxs-lookup"><span data-stu-id="37330-143">Outlook.com</span></span>  <br/> |<span data-ttu-id="37330-144">无</span><span class="sxs-lookup"><span data-stu-id="37330-144">N/A</span></span>  <br/> |

 <span data-ttu-id="37330-145">**Office 2013 要求**</span><span class="sxs-lookup"><span data-stu-id="37330-145">**Office 2013 requirements**</span></span>
  
<span data-ttu-id="37330-146">Word、Excel 和 PowerPoint 2013 for Windows 将支持相同的未成年人检查（如果 Active Directory 身份验证库 (ADAL) 已启用）。</span><span class="sxs-lookup"><span data-stu-id="37330-146">Word, Excel, and PowerPoint 2013 for Windows will support the same minors checks if Active Directory Authentication Library (ADAL) is enabled.</span></span> <span data-ttu-id="37330-147">有两种合规性选项，如下所述。</span><span class="sxs-lookup"><span data-stu-id="37330-147">There are two options for compliance, as explained next.</span></span>
  
- <span data-ttu-id="37330-148">**启用 ADAL**。</span><span class="sxs-lookup"><span data-stu-id="37330-148">**Enable ADAL**.</span></span> <span data-ttu-id="37330-149">本文介绍如何为 Office 2013 启用 ADAL：使用适用 [于 office 客户端的 Microsoft 365 新式验证](https://docs.microsoft.com/microsoft-365/enterprise/modern-auth-for-office-2013-and-2016)。</span><span class="sxs-lookup"><span data-stu-id="37330-149">This article explains how to enable ADAL for Office 2013: [Using Microsoft 365 modern authentication with Office clients](https://docs.microsoft.com/microsoft-365/enterprise/modern-auth-for-office-2013-and-2016).</span></span><br/><span data-ttu-id="37330-150">您还需要将注册表项设置为启用 ADAL，如在 [Windows 设备上为 Office 2013 启用新式验证](../security-and-compliance/enable-modern-authentication.md)中所述。</span><span class="sxs-lookup"><span data-stu-id="37330-150">You also need to set the registry keys to enable ADAL as explained in [Enable Modern Authentication for Office 2013 on Windows devices](../security-and-compliance/enable-modern-authentication.md).</span></span><br/><span data-ttu-id="37330-151">此外，还需要为 Office 2013 安装以下四月份更新：</span><span class="sxs-lookup"><span data-stu-id="37330-151">Additionally, you need to install the following April updates for Office 2013:</span></span>
    
  - [<span data-ttu-id="37330-152">Office 2013 安全更新说明：4月10日，2018</span><span class="sxs-lookup"><span data-stu-id="37330-152">Description of the security update for Office 2013: April 10, 2018</span></span>](https://support.microsoft.com/help/4018330/description-of-the-security-update-for-office-2013-april-10-2018)
    
  - [<span data-ttu-id="37330-153">2018年4月3日，Office 2013 (KB4018333) 的更新 </span><span class="sxs-lookup"><span data-stu-id="37330-153">April 3, 2018, update for Office 2013 (KB4018333)</span></span>](https://support.microsoft.com/help/4018333/april-3-2018-update-for-office-2013-kb4018333)
    
- <span data-ttu-id="37330-154">**不启用 ADAL**。</span><span class="sxs-lookup"><span data-stu-id="37330-154">**Don't enable ADAL**.</span></span> <span data-ttu-id="37330-155">如果无法在 Office 2013 中启用 ADAL，我们建议使用组策略关闭 Office 客户端的存储。</span><span class="sxs-lookup"><span data-stu-id="37330-155">If you're unable to enable ADAL in Office 2013, then our recommendation is to use Group Policy to turn off the Store for the Office clients.</span></span> <span data-ttu-id="37330-156">有关如何关闭 "Office 相关应用程序" 设置的信息位于 [此处](https://technet.microsoft.com/library/cc178992.aspx)。</span><span class="sxs-lookup"><span data-stu-id="37330-156">Information on how to turn off the app for Office settings is located [here](https://technet.microsoft.com/library/cc178992.aspx).</span></span>

## <a name="related-articles"></a><span data-ttu-id="37330-157">相关文章</span><span class="sxs-lookup"><span data-stu-id="37330-157">Related articles</span></span>

[<span data-ttu-id="37330-158">在管理中心部署加载项</span><span class="sxs-lookup"><span data-stu-id="37330-158">Deploy add-ins in the admin center</span></span>](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins)

[<span data-ttu-id="37330-159">在管理中心管理加载项</span><span class="sxs-lookup"><span data-stu-id="37330-159">Manage add-ins in the admin center</span></span>](https://docs.microsoft.com/microsoft-365/admin/manage/manage-addins-in-the-admin-center)
    
