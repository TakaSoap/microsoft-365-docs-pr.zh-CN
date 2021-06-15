---
title: 在Microsoft Project设备上Visio安装 Microsoft 托管桌面 或 Microsoft Microsoft 托管桌面
description: 有关在 Microsoft Project 设备上Visio Microsoft Microsoft 托管桌面的信息
keywords: Microsoft 托管桌面、Microsoft 365、Microsoft Project、Microsoft Visio
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.localizationpriority: normal
ms.date: 03/07/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: 9fd46410877012d92e847ba7ff8b60cd5acceb1e
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/14/2021
ms.locfileid: "52925535"
---
# <a name="install-microsoft-project-or-microsoft-visio-on-microsoft-managed-desktop-devices"></a><span data-ttu-id="8b3dd-104">在Microsoft Project设备上Visio安装 Microsoft 托管桌面 或 Microsoft Microsoft 托管桌面</span><span class="sxs-lookup"><span data-stu-id="8b3dd-104">Install Microsoft Project or Microsoft Visio on Microsoft Managed Desktop devices</span></span>

<span data-ttu-id="8b3dd-105">Microsoft Project和 Microsoft Visio需要在设备上安装特定Microsoft 托管桌面步骤。</span><span class="sxs-lookup"><span data-stu-id="8b3dd-105">Microsoft Project and Microsoft Visio require specific steps to be installed on Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="8b3dd-106">本主题介绍这些应用程序的先决条件和安装过程。</span><span class="sxs-lookup"><span data-stu-id="8b3dd-106">This topic documents the prerequisites and installation process for these applications.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="8b3dd-107">先决条件</span><span class="sxs-lookup"><span data-stu-id="8b3dd-107">Prerequisites</span></span>

<span data-ttu-id="8b3dd-108">管理员应验证他们满足以下先决条件：</span><span class="sxs-lookup"><span data-stu-id="8b3dd-108">Admins should verify that they meet these prerequisites:</span></span>
- <span data-ttu-id="8b3dd-109">**许可证数量**- 用户Microsoft Project Microsoft Visio许可证的正确数量。</span><span class="sxs-lookup"><span data-stu-id="8b3dd-109">**License quantities** - The correct amount of Microsoft Project and Microsoft Visio licenses must be available for your users.</span></span> <span data-ttu-id="8b3dd-110">Microsoft 托管桌面当前仅支持这些应用程序的 64 位版本。</span><span class="sxs-lookup"><span data-stu-id="8b3dd-110">Microsoft Managed Desktop currently only supports 64-bit versions of these applications.</span></span> 
- <span data-ttu-id="8b3dd-111">**许可证名称** - 这些应用程序的适当许可证名称为：</span><span class="sxs-lookup"><span data-stu-id="8b3dd-111">**License names** - The appropriate license names for these applications are:</span></span>
    - <span data-ttu-id="8b3dd-112">**Microsoft Project** - Project Online Professional 或 Project Online 高级版</span><span class="sxs-lookup"><span data-stu-id="8b3dd-112">**Microsoft Project** - Project Online Professional or Project Online Premium</span></span>
    - <span data-ttu-id="8b3dd-113">**Microsoft Visio** - Visio Online 计划 2</span><span class="sxs-lookup"><span data-stu-id="8b3dd-113">**Microsoft Visio** - Visio Online Plan 2</span></span>
- <span data-ttu-id="8b3dd-114">**公司门户**- 公司门户必须在租户中提供，以便用户安装这些应用程序。</span><span class="sxs-lookup"><span data-stu-id="8b3dd-114">**Company Portal** -  The Company Portal must be available in your tenant for your users to install these applications.</span></span> <span data-ttu-id="8b3dd-115">如果公司门户未在租户中部署[，请参阅](company-portal.md)公司门户。</span><span class="sxs-lookup"><span data-stu-id="8b3dd-115">If the Company Portal isn’t deployed in your tenant, see [Company Portal](company-portal.md).</span></span>

## <a name="deploy-project-and-visio-for-microsoft-managed-desktop-devices"></a><span data-ttu-id="8b3dd-116">为Project Visio部署 Microsoft 托管桌面 和 Microsoft 托管桌面</span><span class="sxs-lookup"><span data-stu-id="8b3dd-116">Deploy Project and Visio for Microsoft Managed Desktop devices</span></span>
<span data-ttu-id="8b3dd-117">Microsoft 托管桌面中，Microsoft Project Microsoft Visio 添加为两个 Win32 Microsoft Intune。</span><span class="sxs-lookup"><span data-stu-id="8b3dd-117">Microsoft Managed Desktop will add Microsoft Project and Microsoft Visio as two Win32 Applications in Microsoft Intune.</span></span> <span data-ttu-id="8b3dd-118">我们还将在应用程序内创建Azure Active Directory组，这两个组将分配给具有"可用"意图的相应应用程序。</span><span class="sxs-lookup"><span data-stu-id="8b3dd-118">We will also create two groups in Azure Active Directory which will be assigned to the corresponding application with the "Available" intent.</span></span> 

<span data-ttu-id="8b3dd-119">**部署Project和Visio** 将用户添加到相应的组，应用程序将在相应的公司门户。</span><span class="sxs-lookup"><span data-stu-id="8b3dd-119">**To deploy Project and Visio** Add the user to the appropriate group and the application will become available in the Company Portal.</span></span> <span data-ttu-id="8b3dd-120">可能需要几分钟才能同步，但随后你的用户可以从 公司门户。</span><span class="sxs-lookup"><span data-stu-id="8b3dd-120">It may take a few minutes to sync, but then your users can install the apps from Company Portal.</span></span> 

<span data-ttu-id="8b3dd-121">Azure AD 组名称</span><span class="sxs-lookup"><span data-stu-id="8b3dd-121">Azure AD Group name</span></span> | <span data-ttu-id="8b3dd-122">要分配哪些用户？</span><span class="sxs-lookup"><span data-stu-id="8b3dd-122">Which users to assign?</span></span>   
 --- | ---
<span data-ttu-id="8b3dd-123">现代 Workplace-Office-Project_Install</span><span class="sxs-lookup"><span data-stu-id="8b3dd-123">Modern Workplace-Office-Project_Install</span></span> | <span data-ttu-id="8b3dd-124">需要用户Project</span><span class="sxs-lookup"><span data-stu-id="8b3dd-124">Users needing Project</span></span>
<span data-ttu-id="8b3dd-125">现代 Workplace-Office-Visio_Install</span><span class="sxs-lookup"><span data-stu-id="8b3dd-125">Modern Workplace-Office-Visio_Install</span></span> | <span data-ttu-id="8b3dd-126">需要用户Visio</span><span class="sxs-lookup"><span data-stu-id="8b3dd-126">Users needing Visio</span></span>

## <a name="communicate-changes"></a><span data-ttu-id="8b3dd-127">传达更改</span><span class="sxs-lookup"><span data-stu-id="8b3dd-127">Communicate changes</span></span>
<span data-ttu-id="8b3dd-128">IT 管理员必须让用户了解如何安装Project Visio。</span><span class="sxs-lookup"><span data-stu-id="8b3dd-128">It’s important for IT administrators to let their users know how to install Project and Visio.</span></span> <span data-ttu-id="8b3dd-129">这包括：</span><span class="sxs-lookup"><span data-stu-id="8b3dd-129">This includes:</span></span> 
- <span data-ttu-id="8b3dd-130">在这些应用程序可供用户使用时通知用户。</span><span class="sxs-lookup"><span data-stu-id="8b3dd-130">Notifying users when these applications are available to them.</span></span> 
- <span data-ttu-id="8b3dd-131">有关如何从客户端安装这些应用程序的公司门户。</span><span class="sxs-lookup"><span data-stu-id="8b3dd-131">Instructions on how to install these applications from the Company Portal.</span></span>
