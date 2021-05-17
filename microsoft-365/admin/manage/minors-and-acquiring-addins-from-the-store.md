---
title: 次要加载项和从应用商店获取加载项
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
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
description: 了解 GDPR 一般数据保护 () 管理未成年人个人数据的法规。
ms.openlocfilehash: e7f53a5a6b64f29f5029f0080fef44439c926edb
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2021
ms.locfileid: "51580914"
---
# <a name="minors-and-acquiring-add-ins-from-the-store"></a><span data-ttu-id="19b0c-103">次要加载项和从应用商店获取加载项</span><span class="sxs-lookup"><span data-stu-id="19b0c-103">Minors and acquiring add-ins from the Store</span></span>

<span data-ttu-id="19b0c-104">GDPR 一般 (条例) 于 2018 年 5 月 25 日生效的欧盟法规。</span><span class="sxs-lookup"><span data-stu-id="19b0c-104">The General Data Protection Regulation (GDPR) is a European Union regulation that becomes effective May 25, 2018.</span></span> <span data-ttu-id="19b0c-105">它为用户提供了访问和保护其数据的权利。</span><span class="sxs-lookup"><span data-stu-id="19b0c-105">It gives users rights to and protection of their data.</span></span> <span data-ttu-id="19b0c-106">GDPR 的一个方面是，未成年人无法将他们的个人数据发送给其家长或监护人尚未批准的各方。</span><span class="sxs-lookup"><span data-stu-id="19b0c-106">One of the aspects of the GDPR is that minors cannot have their personal data sent to parties that their parent or guardian hasn't approved.</span></span> <span data-ttu-id="19b0c-107">定义为未成年人的特定年龄取决于个人所在的地区。</span><span class="sxs-lookup"><span data-stu-id="19b0c-107">The specific age defined as a minor depends on the region where the individual is located.</span></span>
  
<span data-ttu-id="19b0c-108">具有有关家长同意的法规的区域包括美国、韩国、英国和欧盟。</span><span class="sxs-lookup"><span data-stu-id="19b0c-108">Regions that have statutory regulations about parental consent include the United States, South Korea, the United Kingdom, and the European Union.</span></span> <span data-ttu-id="19b0c-109">对于这些区域，将阻止 (通过 Azure Active Directory) 从应用商店获取任何新的 Office 外接程序并运行之前获取的外接程序。</span><span class="sxs-lookup"><span data-stu-id="19b0c-109">For those regions, a minor will be blocked (via Azure Active Directory) from getting any new Office add-ins from the Store and running add-ins that were previously acquired.</span></span> <span data-ttu-id="19b0c-110">对于没有法规的国家/地区，将没有下载限制。</span><span class="sxs-lookup"><span data-stu-id="19b0c-110">For countries without statutory regulations, there will be no download restrictions.</span></span>
  
<span data-ttu-id="19b0c-111">根据用户记录中指定的数据，将用户确定为Azure Active Directory。</span><span class="sxs-lookup"><span data-stu-id="19b0c-111">A user is determined to be a minor based on data specified in Azure Active Directory.</span></span> <span data-ttu-id="19b0c-112">组织管理员负责声明法定年龄组和该用户的家长同意。</span><span class="sxs-lookup"><span data-stu-id="19b0c-112">The organization admin is responsible for declaring the legal age group and the parental consent for that user.</span></span>
  
<span data-ttu-id="19b0c-113">如果家长/监护人同意使用特定加载项的未成年人，则组织管理员可以使用集中部署将加载项部署到所有获得同意的未成年人。</span><span class="sxs-lookup"><span data-stu-id="19b0c-113">If the parent/guardian consents to a minor using a specific add-In, then the organization admin can use centralized deployment to deploy that add-In to all minors who have consent.</span></span>
  
<span data-ttu-id="19b0c-114">若要使未成年人符合 GDPR，你需要确保学校/组织中部署以下Office版本之一。</span><span class="sxs-lookup"><span data-stu-id="19b0c-114">To be GDPR compliant for minors you need to ensure that one of following builds of Office is deployed in your school/organization.</span></span>
 
 <span data-ttu-id="19b0c-115">**对于 Word、Excel、PowerPoint 和 Project：**</span><span class="sxs-lookup"><span data-stu-id="19b0c-115">**For Word, Excel, PowerPoint, and Project**:</span></span> 

|<span data-ttu-id="19b0c-116">**平台**</span><span class="sxs-lookup"><span data-stu-id="19b0c-116">**Platform**</span></span> <br/> |<span data-ttu-id="19b0c-117">**内部版本号**</span><span class="sxs-lookup"><span data-stu-id="19b0c-117">**Build number**</span></span> <br/> |
|:-----|:-----|
|<span data-ttu-id="19b0c-118">Microsoft 365 企业应用版 (当前频道) </span><span class="sxs-lookup"><span data-stu-id="19b0c-118">Microsoft 365 Apps for enterprise (Current Channel)</span></span>  <br/> |<span data-ttu-id="19b0c-119">9001.2138</span><span class="sxs-lookup"><span data-stu-id="19b0c-119">9001.2138</span></span>   <br/> |
|<span data-ttu-id="19b0c-120">Microsoft 365 企业应用版 (半年频道Enterprise频道) </span><span class="sxs-lookup"><span data-stu-id="19b0c-120">Microsoft 365 Apps for enterprise (Semi-Annual Enterprise Channel)</span></span>  <br/> |<span data-ttu-id="19b0c-121">8431.2159</span><span class="sxs-lookup"><span data-stu-id="19b0c-121">8431.2159</span></span>  <br/> |
|<span data-ttu-id="19b0c-122">Office 2016 for Windows</span><span class="sxs-lookup"><span data-stu-id="19b0c-122">Office 2016 for Windows</span></span>  <br/> |<span data-ttu-id="19b0c-123">16.0.4672.1000</span><span class="sxs-lookup"><span data-stu-id="19b0c-123">16.0.4672.1000</span></span>  <br/> |
|<span data-ttu-id="19b0c-124">Office 2013 for Windows</span><span class="sxs-lookup"><span data-stu-id="19b0c-124">Office 2013 for Windows</span></span>  <br/> |<span data-ttu-id="19b0c-125">15.0.5023.1000</span><span class="sxs-lookup"><span data-stu-id="19b0c-125">15.0.5023.1000</span></span>  <br/> |
|<span data-ttu-id="19b0c-126">Office 2016 for Mac</span><span class="sxs-lookup"><span data-stu-id="19b0c-126">Office 2016 for Mac</span></span>  <br/> |<span data-ttu-id="19b0c-127">16.11.18020200</span><span class="sxs-lookup"><span data-stu-id="19b0c-127">16.11.18020200</span></span>  <br/> |
|<span data-ttu-id="19b0c-128">Office 网页版</span><span class="sxs-lookup"><span data-stu-id="19b0c-128">Office for the web</span></span>  <br/> |<span data-ttu-id="19b0c-129">不适用</span><span class="sxs-lookup"><span data-stu-id="19b0c-129">N/A</span></span>  <br/> |
   
 <span data-ttu-id="19b0c-130">**对于Outlook：**</span><span class="sxs-lookup"><span data-stu-id="19b0c-130">**For Outlook**:</span></span> 
  
|<span data-ttu-id="19b0c-131">**平台**</span><span class="sxs-lookup"><span data-stu-id="19b0c-131">**Platform**</span></span> <br/> |<span data-ttu-id="19b0c-132">**内部版本号**</span><span class="sxs-lookup"><span data-stu-id="19b0c-132">**Build number**</span></span> <br/> |
|:-----|:-----|
|<span data-ttu-id="19b0c-133">Outlook 2016 MSI Windows () </span><span class="sxs-lookup"><span data-stu-id="19b0c-133">Outlook 2016 for Windows (MSI)</span></span>  <br/> |<span data-ttu-id="19b0c-134">生成无 TBD</span><span class="sxs-lookup"><span data-stu-id="19b0c-134">Build No TBD</span></span>  <br/> |
|<span data-ttu-id="19b0c-135">Outlook 2016 C2R Windows () </span><span class="sxs-lookup"><span data-stu-id="19b0c-135">Outlook 2016 for Windows (C2R)</span></span>  <br/> |<span data-ttu-id="19b0c-136">16.0.9323.1000</span><span class="sxs-lookup"><span data-stu-id="19b0c-136">16.0.9323.1000</span></span>  <br/> |
|<span data-ttu-id="19b0c-137">Office 2016 for Mac</span><span class="sxs-lookup"><span data-stu-id="19b0c-137">Office 2016 for Mac</span></span>  <br/> |<span data-ttu-id="19b0c-138">16.0.9318.1000</span><span class="sxs-lookup"><span data-stu-id="19b0c-138">16.0.9318.1000</span></span>  <br/> |
|<span data-ttu-id="19b0c-139">Outlook iOS 移动版</span><span class="sxs-lookup"><span data-stu-id="19b0c-139">Outlook mobile for iOS</span></span>  <br/> |<span data-ttu-id="19b0c-140">2.75.0</span><span class="sxs-lookup"><span data-stu-id="19b0c-140">2.75.0</span></span>  <br/> |
|<span data-ttu-id="19b0c-141">Outlook Android 移动版</span><span class="sxs-lookup"><span data-stu-id="19b0c-141">Outlook mobile for Android</span></span>  <br/> |<span data-ttu-id="19b0c-142">2.2.145</span><span class="sxs-lookup"><span data-stu-id="19b0c-142">2.2.145</span></span>  <br/> |
|<span data-ttu-id="19b0c-143">Outlook.com</span><span class="sxs-lookup"><span data-stu-id="19b0c-143">Outlook.com</span></span>  <br/> |<span data-ttu-id="19b0c-144">不适用</span><span class="sxs-lookup"><span data-stu-id="19b0c-144">N/A</span></span>  <br/> |

 <span data-ttu-id="19b0c-145">**Office 2013 要求**</span><span class="sxs-lookup"><span data-stu-id="19b0c-145">**Office 2013 requirements**</span></span>
  
<span data-ttu-id="19b0c-146">如果启用了 Active Director (y 身份验证库 Excel ADAL Windows，Word、PowerPoint 和 PowerPoint for) 将支持相同的次要检查。</span><span class="sxs-lookup"><span data-stu-id="19b0c-146">Word, Excel, and PowerPoint 2013 for Windows will support the same minors checks if Active Directory Authentication Library (ADAL) is enabled.</span></span> <span data-ttu-id="19b0c-147">有两种合规性选项，如下文说明。</span><span class="sxs-lookup"><span data-stu-id="19b0c-147">There are two options for compliance, as explained next.</span></span>
  
- <span data-ttu-id="19b0c-148">**启用 ADAL**。</span><span class="sxs-lookup"><span data-stu-id="19b0c-148">**Enable ADAL**.</span></span> <span data-ttu-id="19b0c-149">本文介绍如何为 Office 2013 启用 ADAL：Microsoft 365[客户端使用新式Office身份验证](../../enterprise/modern-auth-for-office-2013-and-2016.md)。</span><span class="sxs-lookup"><span data-stu-id="19b0c-149">This article explains how to enable ADAL for Office 2013: [Using Microsoft 365 modern authentication with Office clients](../../enterprise/modern-auth-for-office-2013-and-2016.md).</span></span><br/><span data-ttu-id="19b0c-150">还需要设置注册表项以启用 ADAL，如在 Windows 设备上为[Office 2013 启用新式](../security-and-compliance/enable-modern-authentication.md)验证Windows说明。</span><span class="sxs-lookup"><span data-stu-id="19b0c-150">You also need to set the registry keys to enable ADAL as explained in [Enable Modern Authentication for Office 2013 on Windows devices](../security-and-compliance/enable-modern-authentication.md).</span></span><br/><span data-ttu-id="19b0c-151">此外，还需要安装 2013 年 4 月Office更新：</span><span class="sxs-lookup"><span data-stu-id="19b0c-151">Additionally, you need to install the following April updates for Office 2013:</span></span>
    
  - [<span data-ttu-id="19b0c-152">2013 年 4 月 10 Office安全更新说明</span><span class="sxs-lookup"><span data-stu-id="19b0c-152">Description of the security update for Office 2013: April 10, 2018</span></span>](https://support.microsoft.com/help/4018330/description-of-the-security-update-for-office-2013-april-10-2018)
    
  - [<span data-ttu-id="19b0c-153">2018 年 4 月 3 日，Office 2013 (KB4018333) </span><span class="sxs-lookup"><span data-stu-id="19b0c-153">April 3, 2018, update for Office 2013 (KB4018333)</span></span>](https://support.microsoft.com/help/4018333/april-3-2018-update-for-office-2013-kb4018333)
    
- <span data-ttu-id="19b0c-154">**不要启用 ADAL**。</span><span class="sxs-lookup"><span data-stu-id="19b0c-154">**Don't enable ADAL**.</span></span> <span data-ttu-id="19b0c-155">如果无法在 Office 2013 中启用 ADAL，则建议使用组策略为 Office 关闭应用商店。</span><span class="sxs-lookup"><span data-stu-id="19b0c-155">If you're unable to enable ADAL in Office 2013, then our recommendation is to use Group Policy to turn off the Store for the Office clients.</span></span> <span data-ttu-id="19b0c-156">有关关闭应用以启用Office的信息位于[此处](/previous-versions/office/office-2013-resource-kit/cc178992(v=office.15))。</span><span class="sxs-lookup"><span data-stu-id="19b0c-156">Information on how to turn off the app for Office settings is located [here](/previous-versions/office/office-2013-resource-kit/cc178992(v=office.15)).</span></span>

## <a name="related-articles"></a><span data-ttu-id="19b0c-157">相关文章</span><span class="sxs-lookup"><span data-stu-id="19b0c-157">Related articles</span></span>

[<span data-ttu-id="19b0c-158">在管理中心部署加载项</span><span class="sxs-lookup"><span data-stu-id="19b0c-158">Deploy add-ins in the admin center</span></span>](./manage-deployment-of-add-ins.md)

[<span data-ttu-id="19b0c-159">在管理中心管理加载项</span><span class="sxs-lookup"><span data-stu-id="19b0c-159">Manage add-ins in the admin center</span></span>](./manage-addins-in-the-admin-center.md)
