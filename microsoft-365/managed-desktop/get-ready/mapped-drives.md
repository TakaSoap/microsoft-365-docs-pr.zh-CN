---
title: 为 Microsoft 托管桌面准备映射的驱动器
description: 确保执行的重要步骤
keywords: Microsoft 托管桌面, Microsoft 365, 服务, 文档
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
ms.openlocfilehash: cd45d6155fc0e01f6a285f6182aa051281d160e0
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50922904"
---
#  <a name="prepare-mapped-drives-for-microsoft-managed-desktop"></a><span data-ttu-id="74cec-104">为 Microsoft 托管桌面准备映射的驱动器</span><span class="sxs-lookup"><span data-stu-id="74cec-104">Prepare mapped drives for Microsoft Managed Desktop</span></span>

<span data-ttu-id="74cec-105">许多企业环境对映射驱动器都有旧要求，以允许其用户或团队共享和存储文件，或本地应用程序。</span><span class="sxs-lookup"><span data-stu-id="74cec-105">Many enterprise environments have legacy requirements for mapped drives to allow their users or teams to share and store files, or for on-premises applications.</span></span> <span data-ttu-id="74cec-106">Microsoft 不建议将映射驱动器与 Microsoft 托管桌面一同使用。</span><span class="sxs-lookup"><span data-stu-id="74cec-106">Microsoft does not recommend the use of mapped drives with the Microsoft Managed Desktop.</span></span> <span data-ttu-id="74cec-107">相反，我们建议你使文件访问解决方案现代化，如下所示：</span><span class="sxs-lookup"><span data-stu-id="74cec-107">Instead, we recommend that you modernize your file access solutions as follows:</span></span>
  
- <span data-ttu-id="74cec-108">将单个用户使用的映射驱动器迁移到 OneDrive for Business。</span><span class="sxs-lookup"><span data-stu-id="74cec-108">Migrate mapped drives used by individual users to OneDrive for Business.</span></span> 
- <span data-ttu-id="74cec-109">将团队用于共享文件的映射驱动器迁移到 SharePoint Online。</span><span class="sxs-lookup"><span data-stu-id="74cec-109">Migrate mapped drives used by teams to share files to SharePoint Online.</span></span> 
- <span data-ttu-id="74cec-110">现代化或替换任何使用本地文件共享的应用程序，以删除该要求。</span><span class="sxs-lookup"><span data-stu-id="74cec-110">Modernize or replace any applications that use on-premises file shares to remove that requirement.</span></span>
  
<span data-ttu-id="74cec-111">现代化这些服务将提供最佳的 Microsoft 托管桌面用户体验。</span><span class="sxs-lookup"><span data-stu-id="74cec-111">Modernizing these services will allow the best user experience with Microsoft Managed Desktop.</span></span> <span data-ttu-id="74cec-112">Microsoft FastTrack Services 可帮助你使用 Microsoft 云服务现代化环境。</span><span class="sxs-lookup"><span data-stu-id="74cec-112">Microsoft FastTrack Services can assist you in modernizing your environment by using Microsoft Cloud Services.</span></span> <span data-ttu-id="74cec-113">你可以检查你是否有资格使用符合条件的服务和计划中的 FastTrack 服务[](/fasttrack/m365-eligible-services-and-plans)，然后直接与他们联系以准备 Microsoft 托管桌面。</span><span class="sxs-lookup"><span data-stu-id="74cec-113">You can check whether you're eligible for FastTrack services at [Eligible Services and Plans](/fasttrack/m365-eligible-services-and-plans) and then contact them directly to prepare for Microsoft Managed Desktop.</span></span> <span data-ttu-id="74cec-114">有关 FastTrack OneDrive for Business 或 SharePoint Online 迁移的背景，请参阅 [数据迁移](/fasttrack/o365-data-migration)。</span><span class="sxs-lookup"><span data-stu-id="74cec-114">For background about FastTrack OneDrive for Business or SharePoint Online Migration, see [Data Migration](/fasttrack/o365-data-migration).</span></span>

## <a name="mapped-drives-on-microsoft-managed-desktop"></a><span data-ttu-id="74cec-115">Microsoft 托管桌面上的映射驱动器</span><span class="sxs-lookup"><span data-stu-id="74cec-115">Mapped drives on Microsoft Managed Desktop</span></span>
 
<span data-ttu-id="74cec-116">如果在某些用例中无法删除或替换映射的驱动器，应在 Microsoft 托管桌面管理门户中提交支持请求，以将其部署到 Microsoft 托管桌面用户。</span><span class="sxs-lookup"><span data-stu-id="74cec-116">If you cannot remove or replace mapped drives for some use cases, you should submit a support request in the Microsoft Managed Desktop admin portal to have them deployed to Microsoft Managed Desktop users.</span></span>
    
<span data-ttu-id="74cec-117">对于此类请求，你必须在支持请求中提供以下详细信息：</span><span class="sxs-lookup"><span data-stu-id="74cec-117">For such a request, you'll have to provide the following details in the support request:</span></span> 

- <span data-ttu-id="74cec-118">需要为 Microsoft 托管桌面设备映射的文件共享位置的所有 UNC 路径</span><span class="sxs-lookup"><span data-stu-id="74cec-118">All UNC paths to file share locations that will need to be mapped for Microsoft Managed Desktop devices</span></span> 
- <span data-ttu-id="74cec-119">需要访问这些文件共享位置的用户组</span><span class="sxs-lookup"><span data-stu-id="74cec-119">User groups that require access to these file share locations</span></span> 
- <span data-ttu-id="74cec-120">需要分配的任何特定驱动器号 (如果需要) </span><span class="sxs-lookup"><span data-stu-id="74cec-120">Any specific drive letter that needs to be assigned (if necessary)</span></span>

<span data-ttu-id="74cec-121">例如：</span><span class="sxs-lookup"><span data-stu-id="74cec-121">For example:</span></span>

| <span data-ttu-id="74cec-122">驱动器号</span><span class="sxs-lookup"><span data-stu-id="74cec-122">Drive letter</span></span> | <span data-ttu-id="74cec-123">UNC 路径</span><span class="sxs-lookup"><span data-stu-id="74cec-123">UNC path</span></span> | <span data-ttu-id="74cec-124">用户组</span><span class="sxs-lookup"><span data-stu-id="74cec-124">User group</span></span> |
|--------------|----------|------------|
| <span data-ttu-id="74cec-125">X：</span><span class="sxs-lookup"><span data-stu-id="74cec-125">X:</span></span>  | <span data-ttu-id="74cec-126">\\\server\share\Marketing</span><span class="sxs-lookup"><span data-stu-id="74cec-126">\\\server\share\Marketing</span></span> | <span data-ttu-id="74cec-127">ContosoMarketing</span><span class="sxs-lookup"><span data-stu-id="74cec-127">ContosoMarketing</span></span> |

<span data-ttu-id="74cec-128">你完全有责任确保用户和组拥有和维护访问文件共享位置所需的正确权限，并确保本地文件服务仍然可访问。</span><span class="sxs-lookup"><span data-stu-id="74cec-128">It's entirely your responsibility to ensure that users and groups have and maintain the right permissions to access file share locations and that the on-premises file services remain accessible.</span></span> <span data-ttu-id="74cec-129">此外，应尽快删除对此类文件共享的要求。</span><span class="sxs-lookup"><span data-stu-id="74cec-129">Also, you should remove your requirements for such file shares as soon as possible.</span></span>

### <a name="to-have-mapped-drives-deployed-in-microsoft-managed-desktop"></a><span data-ttu-id="74cec-130">在 Microsoft 托管桌面中部署映射的驱动器</span><span class="sxs-lookup"><span data-stu-id="74cec-130">To have mapped drives deployed in Microsoft Managed Desktop</span></span>
 
<span data-ttu-id="74cec-131">请确保无法避免映射的驱动器，并且你已仔细查看要求，然后再提交任何服务请求。</span><span class="sxs-lookup"><span data-stu-id="74cec-131">Make sure that mapped drives cannot be avoided and you have carefully reviewed the requirements before submitting any service request.</span></span> <span data-ttu-id="74cec-132">然后按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="74cec-132">Then follow these steps:</span></span>

1. <span data-ttu-id="74cec-133">导航到 [Microsoft Endpoint Manager 并选择](https://endpoint.microsoft.com/) "疑难解答 + 支持"，然后在 Microsoft 托管桌面部分下查找"服务请求"。</span><span class="sxs-lookup"><span data-stu-id="74cec-133">Navigate to [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) and select "Troubleshooting + support" then look for "Service requests" under the Microsoft Managed Desktop section.</span></span>  
2. <span data-ttu-id="74cec-134">提交标题为"映射驱动器部署"的支持请求，并提供所有必需的文件共享详细信息。</span><span class="sxs-lookup"><span data-stu-id="74cec-134">Submit a support request titled “Mapped drives deployment” and provide all the required file share details.</span></span>  
3. <span data-ttu-id="74cec-135">当请求完成时，Microsoft 托管桌面 IT 运营部门将通过使用支持请求更新提供建议。</span><span class="sxs-lookup"><span data-stu-id="74cec-135">Microsoft Managed Desktop IT Operations will advise, by using support request updates, when the request has been completed.</span></span> <span data-ttu-id="74cec-136">最初，此配置将仅部署到"测试"部署组的设备。</span><span class="sxs-lookup"><span data-stu-id="74cec-136">Initially this configuration will only be deployed to devices in the Test deployment group.</span></span>  
4. <span data-ttu-id="74cec-137">您必须测试并确认 Microsoft 托管桌面 IT 操作部署的配置是否按预期工作。</span><span class="sxs-lookup"><span data-stu-id="74cec-137">You must test and confirm whether the configuration deployed by the Microsoft Managed Desktop IT Operations works as you expect.</span></span> <span data-ttu-id="74cec-138">使用相同支持请求的详细信息中的"讨论"选项卡进行回复，以在测试完成后通知 Microsoft 托管桌面 IT 操作。</span><span class="sxs-lookup"><span data-stu-id="74cec-138">Reply using the Discussion tab in the details of the same support request to notify Microsoft Managed Desktop IT Operations once you've completed your testing.</span></span>  
5. <span data-ttu-id="74cec-139">然后，Microsoft 托管桌面 IT 运营团队将配置部署到其他部署组。</span><span class="sxs-lookup"><span data-stu-id="74cec-139">Microsoft Managed Desktop IT Operations team will then deploy the configuration to the other deployment groups.</span></span>