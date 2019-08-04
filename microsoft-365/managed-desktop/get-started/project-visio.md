---
title: 在 Microsoft 托管桌面设备上安装 Microsoft Project 或 Microsoft Visio
description: Microsoft 托管桌面设备上有关安装 Microsoft Project 或 Microsoft Visio 的信息
keywords: Microsoft 托管桌面, Microsoft 365, microsoft Project, Microsoft Visio
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.date: 03/07/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: 203db332e1fcd7861f40c69b138ac8274544dceb
ms.sourcegitcommit: 6cabf0226de1c95bff6ddb1852dac5ecdb2d6b96
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/23/2019
ms.locfileid: "35830470"
---
# <a name="install-microsoft-project-or-microsoft-visio-on-microsoft-managed-desktop-devices"></a><span data-ttu-id="dcea0-104">在 Microsoft 托管桌面设备上安装 Microsoft Project 或 Microsoft Visio</span><span class="sxs-lookup"><span data-stu-id="dcea0-104">Install Microsoft Project or Microsoft Visio on Microsoft Managed Desktop devices</span></span>

<span data-ttu-id="dcea0-105">Microsoft Project 和 Microsoft Visio 要求在 Microsoft 托管桌面设备上安装特定步骤。</span><span class="sxs-lookup"><span data-stu-id="dcea0-105">Microsoft Project and Microsoft Visio require specific steps to be installed on Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="dcea0-106">本主题介绍了这些应用程序的先决条件和安装过程。</span><span class="sxs-lookup"><span data-stu-id="dcea0-106">This topic documents the prerequisites and installation process for these applications.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="dcea0-107">先决条件</span><span class="sxs-lookup"><span data-stu-id="dcea0-107">Prerequisites</span></span>

<span data-ttu-id="dcea0-108">管理员应验证它们是否符合以下先决条件:</span><span class="sxs-lookup"><span data-stu-id="dcea0-108">Admins should verify that they meet these prerequisites:</span></span>
- <span data-ttu-id="dcea0-109">**许可证数量**-您的用户必须能够使用的 microsoft Project 和 microsoft Visio 许可证的正确数量。</span><span class="sxs-lookup"><span data-stu-id="dcea0-109">**License quantities** - The correct amount of Microsoft Project and Microsoft Visio licenses must be available for your users.</span></span> <span data-ttu-id="dcea0-110">Microsoft 托管桌面目前仅支持这些应用程序的64位版本。</span><span class="sxs-lookup"><span data-stu-id="dcea0-110">Microsoft Managed Desktop currently only supports 64-bit versions of these applications.</span></span> 
- <span data-ttu-id="dcea0-111">**许可证名称**-这些应用程序的相应许可证名称为:</span><span class="sxs-lookup"><span data-stu-id="dcea0-111">**License names** - The appropriate license names for these applications are:</span></span>
    - <span data-ttu-id="dcea0-112">**Microsoft project** -Project online Professional 或 Project Online 高级版</span><span class="sxs-lookup"><span data-stu-id="dcea0-112">**Microsoft Project** - Project Online Professional or Project Online Premium</span></span>
    - <span data-ttu-id="dcea0-113">**Microsoft visio** -Visio Online 计划2</span><span class="sxs-lookup"><span data-stu-id="dcea0-113">**Microsoft Visio** - Visio Online Plan 2</span></span>
- <span data-ttu-id="dcea0-114">**公司门户**-公司门户必须在你的租户中可用, 你的用户才能安装这些应用程序。</span><span class="sxs-lookup"><span data-stu-id="dcea0-114">**Company Portal** -  The Company Portal must be available in your tenant for your users to install these applications.</span></span> <span data-ttu-id="dcea0-115">如果公司门户未部署在你的租户中, 请参阅[公司门户](company-portal.md)。</span><span class="sxs-lookup"><span data-stu-id="dcea0-115">If the Company Portal isn’t deployed in your tenant, see [Company Portal](company-portal.md).</span></span>

## <a name="deploy-project-and-visio-for-microsoft-managed-desktop-devices"></a><span data-ttu-id="dcea0-116">部署 Microsoft 托管桌面设备的 Project 和 Visio</span><span class="sxs-lookup"><span data-stu-id="dcea0-116">Deploy Project and Visio for Microsoft Managed Desktop devices</span></span>
<span data-ttu-id="dcea0-117">提交你的支持请求后, Microsoft 托管桌面将通过 Microsoft Intune 创建三个 Azure AD 组和三个应用程序部署, 以将应用程序部署到你的租户。</span><span class="sxs-lookup"><span data-stu-id="dcea0-117">After you submit your support request, Microsoft Managed Desktop will create three Azure AD groups and three application deployments through Microsoft Intune to deploy the apps to your tenant.</span></span>  

<span data-ttu-id="dcea0-118">**部署 Project 和 Visio**</span><span class="sxs-lookup"><span data-stu-id="dcea0-118">**To deploy Project and Visio**</span></span>
1. <span data-ttu-id="dcea0-119">**File a 支持请求**IT 管理员需要将支持请求文件, 以使这些应用程序可供其用户使用。</span><span class="sxs-lookup"><span data-stu-id="dcea0-119">**File a support request** IT administrators need to file a support request to make these applications available their users.</span></span> <span data-ttu-id="dcea0-120">有关联系 Microsoft 托管桌面的信息, 请参阅[Microsoft 托管桌面的管理员支持](../working-with-managed-desktop/admin-support.md)。</span><span class="sxs-lookup"><span data-stu-id="dcea0-120">For information on contacting Microsoft Managed Desktop, see [Admin support for Microsoft Managed Desktop](../working-with-managed-desktop/admin-support.md).</span></span>
2. <span data-ttu-id="dcea0-121">**将用户分配给新的 AZURE AD 组**Microsoft 托管桌面将在你的租户和3个对应的应用程序部署中创建3个 Azure AD 组。</span><span class="sxs-lookup"><span data-stu-id="dcea0-121">**Assign users to new Azure AD groups** Microsoft Managed Desktop will create 3 Azure AD groups in your tenant and 3 corresponding application deployments.</span></span> <span data-ttu-id="dcea0-122">IT 管理员需要将用户分配给适当的组。</span><span class="sxs-lookup"><span data-stu-id="dcea0-122">IT admins need to assign the users to the appropriate groups.</span></span>

>[!NOTE]
><span data-ttu-id="dcea0-123">仅将用户分配给这些 Azure AD 组中的一个。</span><span class="sxs-lookup"><span data-stu-id="dcea0-123">Assign users to only one of these Azure AD groups.</span></span> 

<span data-ttu-id="dcea0-124">Azure AD 组名称</span><span class="sxs-lookup"><span data-stu-id="dcea0-124">Azure AD Group name</span></span> | <span data-ttu-id="dcea0-125">要分配哪些用户？</span><span class="sxs-lookup"><span data-stu-id="dcea0-125">Which users to assign?</span></span>   
 --- | ---
<span data-ttu-id="dcea0-126">新式工作区-Office-项目-安装</span><span class="sxs-lookup"><span data-stu-id="dcea0-126">Modern Workplace-Office-Project-Install</span></span> | <span data-ttu-id="dcea0-127">仅需要项目的用户</span><span class="sxs-lookup"><span data-stu-id="dcea0-127">Users needing only Project</span></span>
<span data-ttu-id="dcea0-128">新式工作区-Office-Visio-安装</span><span class="sxs-lookup"><span data-stu-id="dcea0-128">Modern Workplace-Office-Visio-Install</span></span> | <span data-ttu-id="dcea0-129">仅需要 Visio 的用户</span><span class="sxs-lookup"><span data-stu-id="dcea0-129">Users needing only Visio</span></span>
<span data-ttu-id="dcea0-130">新式工作区-Office-项目和 Visio-安装</span><span class="sxs-lookup"><span data-stu-id="dcea0-130">Modern Workplace-Office-Project and Visio-Install</span></span> | <span data-ttu-id="dcea0-131">需要 Project 和 Visio 的用户</span><span class="sxs-lookup"><span data-stu-id="dcea0-131">Users needing both Project and Visio</span></span>

<span data-ttu-id="dcea0-132">一旦分配给这些组, 应用程序将在公司门户中可用。</span><span class="sxs-lookup"><span data-stu-id="dcea0-132">Once assigned to these groups, applications will be available in the Company Portal.</span></span> <span data-ttu-id="dcea0-133">同步可能需要几分钟时间, 但随后你的用户可以从公司门户安装应用程序。</span><span class="sxs-lookup"><span data-stu-id="dcea0-133">It may take a few minutes to sync, but then your users can install the apps from Company Portal.</span></span> 

## <a name="communicate-changes"></a><span data-ttu-id="dcea0-134">传达更改</span><span class="sxs-lookup"><span data-stu-id="dcea0-134">Communicate changes</span></span>
<span data-ttu-id="dcea0-135">IT 管理员必须让用户知道如何安装 Project 和 Visio, 这一点非常重要。</span><span class="sxs-lookup"><span data-stu-id="dcea0-135">It’s important for IT administrators to let their users know how to install Project and Visio.</span></span> <span data-ttu-id="dcea0-136">具体包括：</span><span class="sxs-lookup"><span data-stu-id="dcea0-136">This includes:</span></span> 
- <span data-ttu-id="dcea0-137">当用户可使用这些应用程序时通知用户。</span><span class="sxs-lookup"><span data-stu-id="dcea0-137">Notifying users when these applications are available to them.</span></span> 
- <span data-ttu-id="dcea0-138">有关如何从公司门户安装这些应用程序的说明。</span><span class="sxs-lookup"><span data-stu-id="dcea0-138">Instructions on how to install these applications from the Company Portal.</span></span>

>[!NOTE]
><span data-ttu-id="dcea0-139">用户必须先关闭所有 Office 应用程序, 然后才能从公司门户安装 Microsoft Project 或 Microsoft Visio。</span><span class="sxs-lookup"><span data-stu-id="dcea0-139">Users must close all Office applications before installing Microsoft Project or Microsoft Visio from Company Portal.</span></span> 
