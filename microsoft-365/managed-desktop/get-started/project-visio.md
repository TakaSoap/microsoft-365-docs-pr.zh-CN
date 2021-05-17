---
title: 在 Microsoft 托管桌面设备上安装 Microsoft Project 或 Microsoft Visio
description: 有关在 Microsoft 托管桌面设备上安装 Microsoft Project 或 Microsoft Visio 的信息
keywords: Microsoft 托管桌面、Microsoft 365、Microsoft Project、Microsoft Visio
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.date: 03/07/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: c04bcdf846bafaa7838ef5932c8de595f5035992
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/17/2020
ms.locfileid: "47950528"
---
# <a name="install-microsoft-project-or-microsoft-visio-on-microsoft-managed-desktop-devices"></a><span data-ttu-id="57a79-104">在 Microsoft 托管桌面设备上安装 Microsoft Project 或 Microsoft Visio</span><span class="sxs-lookup"><span data-stu-id="57a79-104">Install Microsoft Project or Microsoft Visio on Microsoft Managed Desktop devices</span></span>

<span data-ttu-id="57a79-105">Microsoft Project 和 Microsoft Visio 要求在 Microsoft 托管桌面设备上安装特定步骤。</span><span class="sxs-lookup"><span data-stu-id="57a79-105">Microsoft Project and Microsoft Visio require specific steps to be installed on Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="57a79-106">本主题介绍这些应用程序的先决条件和安装过程。</span><span class="sxs-lookup"><span data-stu-id="57a79-106">This topic documents the prerequisites and installation process for these applications.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="57a79-107">必备条件</span><span class="sxs-lookup"><span data-stu-id="57a79-107">Prerequisites</span></span>

<span data-ttu-id="57a79-108">管理员应验证他们满足以下先决条件：</span><span class="sxs-lookup"><span data-stu-id="57a79-108">Admins should verify that they meet these prerequisites:</span></span>
- <span data-ttu-id="57a79-109">**许可证数量** - 必须为用户提供正确数量的 Microsoft Project 和 Microsoft Visio 许可证。</span><span class="sxs-lookup"><span data-stu-id="57a79-109">**License quantities** - The correct amount of Microsoft Project and Microsoft Visio licenses must be available for your users.</span></span> <span data-ttu-id="57a79-110">Microsoft 托管桌面当前仅支持这些应用程序的 64 位版本。</span><span class="sxs-lookup"><span data-stu-id="57a79-110">Microsoft Managed Desktop currently only supports 64-bit versions of these applications.</span></span> 
- <span data-ttu-id="57a79-111">**许可证名称** - 这些应用程序的适当许可证名称为：</span><span class="sxs-lookup"><span data-stu-id="57a79-111">**License names** - The appropriate license names for these applications are:</span></span>
    - <span data-ttu-id="57a79-112">**Microsoft Project** - Project Online Professional 或 Project Online 高级版</span><span class="sxs-lookup"><span data-stu-id="57a79-112">**Microsoft Project** - Project Online Professional or Project Online Premium</span></span>
    - <span data-ttu-id="57a79-113">**Microsoft Visio** - Visio Online 计划 2</span><span class="sxs-lookup"><span data-stu-id="57a79-113">**Microsoft Visio** - Visio Online Plan 2</span></span>
- <span data-ttu-id="57a79-114">**公司** 门户 - 公司门户必须在租户中提供，以便用户安装这些应用程序。</span><span class="sxs-lookup"><span data-stu-id="57a79-114">**Company Portal** -  The Company Portal must be available in your tenant for your users to install these applications.</span></span> <span data-ttu-id="57a79-115">如果租户中未部署公司门户，请参阅公司 [门户](company-portal.md)。</span><span class="sxs-lookup"><span data-stu-id="57a79-115">If the Company Portal isn’t deployed in your tenant, see [Company Portal](company-portal.md).</span></span>

## <a name="deploy-project-and-visio-for-microsoft-managed-desktop-devices"></a><span data-ttu-id="57a79-116">部署 Project 和 Visio for Microsoft 托管桌面设备</span><span class="sxs-lookup"><span data-stu-id="57a79-116">Deploy Project and Visio for Microsoft Managed Desktop devices</span></span>
<span data-ttu-id="57a79-117">Microsoft 托管桌面将在 Microsoft Intune 中添加 Microsoft Project 和 Microsoft Visio 作为两个 Win32 应用程序。</span><span class="sxs-lookup"><span data-stu-id="57a79-117">Microsoft Managed Desktop will add Microsoft Project and Microsoft Visio as two Win32 Applications in Microsoft Intune.</span></span> <span data-ttu-id="57a79-118">我们还将在 Azure Active Directory 中创建两个组，这两个组将分配给具有"可用"意图的相应应用程序。</span><span class="sxs-lookup"><span data-stu-id="57a79-118">We will also create two groups in Azure Active Directory which will be assigned to the corresponding application with the "Available" intent.</span></span> 

<span data-ttu-id="57a79-119">**部署 Project 和 Visio** 将用户添加到相应的组，应用程序将在公司门户中可用。</span><span class="sxs-lookup"><span data-stu-id="57a79-119">**To deploy Project and Visio** Add the user to the appropriate group and the application will become available in the Company Portal.</span></span> <span data-ttu-id="57a79-120">可能需要几分钟才能同步，但随后你的用户可以从公司门户安装应用。</span><span class="sxs-lookup"><span data-stu-id="57a79-120">It may take a few minutes to sync, but then your users can install the apps from Company Portal.</span></span> 

<span data-ttu-id="57a79-121">Azure AD 组名称</span><span class="sxs-lookup"><span data-stu-id="57a79-121">Azure AD Group name</span></span> | <span data-ttu-id="57a79-122">要分配哪些用户？</span><span class="sxs-lookup"><span data-stu-id="57a79-122">Which users to assign?</span></span>   
 --- | ---
<span data-ttu-id="57a79-123">现代 Workplace-Office-Project_Install</span><span class="sxs-lookup"><span data-stu-id="57a79-123">Modern Workplace-Office-Project_Install</span></span> | <span data-ttu-id="57a79-124">需要 Project 的用户</span><span class="sxs-lookup"><span data-stu-id="57a79-124">Users needing Project</span></span>
<span data-ttu-id="57a79-125">现代 Workplace-Office-Visio_Install</span><span class="sxs-lookup"><span data-stu-id="57a79-125">Modern Workplace-Office-Visio_Install</span></span> | <span data-ttu-id="57a79-126">需要 Visio 的用户</span><span class="sxs-lookup"><span data-stu-id="57a79-126">Users needing Visio</span></span>

## <a name="communicate-changes"></a><span data-ttu-id="57a79-127">传达更改</span><span class="sxs-lookup"><span data-stu-id="57a79-127">Communicate changes</span></span>
<span data-ttu-id="57a79-128">IT 管理员应让用户了解如何安装 Project 和 Visio，这一点非常重要。</span><span class="sxs-lookup"><span data-stu-id="57a79-128">It’s important for IT administrators to let their users know how to install Project and Visio.</span></span> <span data-ttu-id="57a79-129">这包括：</span><span class="sxs-lookup"><span data-stu-id="57a79-129">This includes:</span></span> 
- <span data-ttu-id="57a79-130">在这些应用程序可供用户使用时通知用户。</span><span class="sxs-lookup"><span data-stu-id="57a79-130">Notifying users when these applications are available to them.</span></span> 
- <span data-ttu-id="57a79-131">有关如何从公司门户安装这些应用程序的说明。</span><span class="sxs-lookup"><span data-stu-id="57a79-131">Instructions on how to install these applications from the Company Portal.</span></span>
