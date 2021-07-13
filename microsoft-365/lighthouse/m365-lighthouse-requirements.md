---
title: Microsoft 365 Lighthouse
f1.keywords: NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.prod: microsoft-365-lighthouse
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- M365-Lighthouse
search.appverid: MET150
description: 对于托管服务提供商 (MSP) ，获取使用托管服务提供商Microsoft 365 Lighthouse。
ms.openlocfilehash: 9c87744053ffe3bace90534287cd2b81697f3554
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/12/2021
ms.locfileid: "53395072"
---
# <a name="requirements-for-microsoft-365-lighthouse"></a><span data-ttu-id="67cd8-103">Microsoft 365 Lighthouse</span><span class="sxs-lookup"><span data-stu-id="67cd8-103">Requirements for Microsoft 365 Lighthouse</span></span>

> [!NOTE]
> <span data-ttu-id="67cd8-104">本文中所述的功能在预览版中可能会更改，并且仅对满足本文中列出的要求的合作伙伴可用。</span><span class="sxs-lookup"><span data-stu-id="67cd8-104">The features described in this article are in Preview, are subject to change, and are only available to partners who meet the requirements listed in this article.</span></span> <span data-ttu-id="67cd8-105">如果你的组织没有此Microsoft 365 Lighthouse，请参阅[注册Microsoft 365 Lighthouse。](m365-lighthouse-sign-up.md)</span><span class="sxs-lookup"><span data-stu-id="67cd8-105">If your organization does not have Microsoft 365 Lighthouse, see [Sign up for Microsoft 365 Lighthouse](m365-lighthouse-sign-up.md).</span></span>

<span data-ttu-id="67cd8-106">Microsoft 365 Lighthouse是一个管理门户，可帮助托管服务提供商 (MSP) 为中小型商业 (SMB) 客户大规模保护和管理设备、数据和用户。</span><span class="sxs-lookup"><span data-stu-id="67cd8-106">Microsoft 365 Lighthouse is an admin portal that helps Managed Service Providers (MSPs) secure and manage devices, data, and users at scale for small- and medium-sized business (SMB) customers.</span></span>  

<span data-ttu-id="67cd8-107">MSP 必须以间接经销商或直接计费合作伙伴云解决方案提供商 (云解决方案提供商计划) 注册，以使用Microsoft 365 Lighthouse。</span><span class="sxs-lookup"><span data-stu-id="67cd8-107">MSPs must be enrolled in the Cloud Solution Provider (CSP) program as an Indirect Reseller or Direct Bill partner to use Microsoft 365 Lighthouse.</span></span>  

<span data-ttu-id="67cd8-108">此外，每个 MSP 客户租户都必须Microsoft 365 Lighthouse满足以下要求，才有资格使用新租户：</span><span class="sxs-lookup"><span data-stu-id="67cd8-108">In addition, each MSP customer tenant must qualify for Microsoft 365 Lighthouse by meeting the following requirements:</span></span> 
 
- <span data-ttu-id="67cd8-109">MSP 的 (DAP) 委派管理员权限</span><span class="sxs-lookup"><span data-stu-id="67cd8-109">Delegated Admin Privileges (DAP) for the MSP</span></span> 
- <span data-ttu-id="67cd8-110">至少一个Microsoft 365 商业高级版许可证</span><span class="sxs-lookup"><span data-stu-id="67cd8-110">At least one Microsoft 365 Business Premium license</span></span> 
- <span data-ttu-id="67cd8-111">少于 500 个许可用户</span><span class="sxs-lookup"><span data-stu-id="67cd8-111">Fewer than 500 licensed users</span></span>  

## <a name="requirements-for-enablingdevice-management"></a><span data-ttu-id="67cd8-112">启用设备管理的要求</span><span class="sxs-lookup"><span data-stu-id="67cd8-112">Requirements for enabling device management</span></span>   

<span data-ttu-id="67cd8-113">若要在设备管理页面上查看客户租户设备，MSP 必须：</span><span class="sxs-lookup"><span data-stu-id="67cd8-113">To view customer tenant devices on the device management pages, a MSP must:</span></span>    

- <span data-ttu-id="67cd8-114">在 MEM Microsoft Endpoint Manager (注册) 。</span><span class="sxs-lookup"><span data-stu-id="67cd8-114">Enroll all customer devices in Microsoft Endpoint Manager (MEM).</span></span><span data-ttu-id="67cd8-115">有关详细信息，请参阅在 Microsoft Intune[中注册设备](/mem/intune/enrollment/)。</span><span class="sxs-lookup"><span data-stu-id="67cd8-115"> For more information, see [Enroll devices in Microsoft Intune](/mem/intune/enrollment/).</span></span>
- <span data-ttu-id="67cd8-116">将合规性策略分配给所有客户设备。</span><span class="sxs-lookup"><span data-stu-id="67cd8-116">Assign compliance policies to all customer devices.</span></span><span data-ttu-id="67cd8-117">有关详细信息，请参阅 Create [a compliance policy in Microsoft Intune](/mem/intune/protect/create-compliance-policy)。</span><span class="sxs-lookup"><span data-stu-id="67cd8-117"> For more information, see [Create a compliance policy in Microsoft Intune](/mem/intune/protect/create-compliance-policy).</span></span> 

## <a name="requirements-for-enabling-usermanagement"></a><span data-ttu-id="67cd8-118">启用用户管理的要求</span><span class="sxs-lookup"><span data-stu-id="67cd8-118">Requirements for enabling user management</span></span> 

<span data-ttu-id="67cd8-119">若要使客户数据显示在用户管理页面上的报告（包括风险用户、多重身份验证和密码重置）中，客户租户必须具有 Azure Active Directory 高级版 P1 或更高版本的许可证。</span><span class="sxs-lookup"><span data-stu-id="67cd8-119">For customer data to show up in reports on user management pages, including Risky users, Multifactor authentication, and Password reset, customer tenants must have licenses for Azure Active Directory Premium P1 or later.</span></span> <span data-ttu-id="67cd8-120">Azure AD Premium P1包括在Microsoft 365 商业高级版。</span><span class="sxs-lookup"><span data-stu-id="67cd8-120">Azure AD Premium P1 is included with Microsoft 365 Business Premium.</span></span>   

## <a name="requirements-for-enablingthreat-management"></a><span data-ttu-id="67cd8-121">启用威胁管理的要求</span><span class="sxs-lookup"><span data-stu-id="67cd8-121">Requirements for enabling threat management</span></span> 

<span data-ttu-id="67cd8-122">若要在威胁管理页面上查看客户租户设备和威胁，必须在 Microsoft Endpoint Manager (MEM) 注册所有客户租户设备，并运行 Microsoft Defender 防病毒。</span><span class="sxs-lookup"><span data-stu-id="67cd8-122">To view customer tenant devices and threats on the threat management pages, you must enroll all customer tenant devices in Microsoft Endpoint Manager (MEM) and protect them by running Microsoft Defender Antivirus.</span></span>  

<span data-ttu-id="67cd8-123">有关详细信息，请参阅在 Microsoft Intune[中注册设备](/mem/intune/enrollment/)。</span><span class="sxs-lookup"><span data-stu-id="67cd8-123">For more information, see [Enroll devices in Microsoft Intune](/mem/intune/enrollment/).</span></span>  

<span data-ttu-id="67cd8-124">Microsoft Defender 防病毒是 Windows操作系统的一部分，在运行 Windows 10 的设备上默认启用。</span><span class="sxs-lookup"><span data-stu-id="67cd8-124">Microsoft Defender Antivirus is part of the Windows operating system and is enabled by default on devices running Windows 10.</span></span>  

> [!NOTE] 
> <span data-ttu-id="67cd8-125">如果使用的是非 Microsoft 防病毒解决方案，但Microsoft Defender 防病毒，Microsoft Defender 防病毒自动禁用。</span><span class="sxs-lookup"><span data-stu-id="67cd8-125">If you're using a non-Microsoft antivirus solution and not Microsoft Defender Antivirus, Microsoft Defender Antivirus is disabled automatically.</span></span> <span data-ttu-id="67cd8-126">卸载非 Microsoft 防病毒解决方案时，Microsoft Defender 防病毒自动激活，以保护Windows设备免受威胁。</span><span class="sxs-lookup"><span data-stu-id="67cd8-126">When you uninstall the non-Microsoft antivirus solution, Microsoft Defender Antivirus is activated automatically to protect your Windows devices from threats.</span></span>    

## <a name="related-content"></a><span data-ttu-id="67cd8-127">相关内容</span><span class="sxs-lookup"><span data-stu-id="67cd8-127">Related content</span></span>   

<span data-ttu-id="67cd8-128">[Configure Microsoft 365 Lighthouse portal security (](m365-lighthouse-configure-portal-security.md) article) </span><span class="sxs-lookup"><span data-stu-id="67cd8-128">[Configure Microsoft 365 Lighthouse portal security](m365-lighthouse-configure-portal-security.md) (article)</span></span>\
<span data-ttu-id="67cd8-129">[Microsoft 365 Lighthouse设备合规性页面概述 (](m365-lighthouse-device-compliance-page-overview.md)文章) </span><span class="sxs-lookup"><span data-stu-id="67cd8-129">[Microsoft 365 Lighthouse Device compliance page overview](m365-lighthouse-device-compliance-page-overview.md) (article)</span></span>\
<span data-ttu-id="67cd8-130">[Microsoft 365 Lighthouse用户页面概述 (](m365-lighthouse-users-page-overview.md)文章) </span><span class="sxs-lookup"><span data-stu-id="67cd8-130">[Microsoft 365 Lighthouse Users page overview](m365-lighthouse-users-page-overview.md) (article)</span></span>\
<span data-ttu-id="67cd8-131">[Microsoft 365 Lighthouse威胁管理页面概述 (](m365-lighthouse-threat-management-page-overview.md)文章) </span><span class="sxs-lookup"><span data-stu-id="67cd8-131">[Microsoft 365 Lighthouse Threat management page overview](m365-lighthouse-threat-management-page-overview.md) (article)</span></span>\
<span data-ttu-id="67cd8-132">[Microsoft 365 Lighthouse常见问题解答](m365-lighthouse-faq.yml)   (文章) </span><span class="sxs-lookup"><span data-stu-id="67cd8-132">[Microsoft 365 Lighthouse FAQ](m365-lighthouse-faq.yml) (article)</span></span>

