---
title: 编辑或设置 Windows 10 设备的应用程序保护设置
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
f1_keywords:
- Win10AppPolicy
- O365E_Win10AppPolicy
- BCS365_Win10AppPolicy
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 02e74022-44af-414b-9d74-0ebf5c2197f0
description: 了解如何在用户的个人 Windows 10 设备上创建或编辑应用管理策略和保护工作文件。
ms.openlocfilehash: 64c6aa620171a373cd7564c7de3abbf4a4546c4e
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50912814"
---
# <a name="set-or-edit-application-protection-settings-for-windows-10-devices"></a><span data-ttu-id="6172c-103">设置或编辑 Windows 10 设备的应用程序保护设置</span><span class="sxs-lookup"><span data-stu-id="6172c-103">Set or edit application protection settings for Windows 10 devices</span></span>

<span data-ttu-id="6172c-104">本文适用于 Microsoft 365 商业高级版。</span><span class="sxs-lookup"><span data-stu-id="6172c-104">This article applies to Microsoft 365 Business Premium.</span></span>

## <a name="edit-an-app-management-policy-for-windows-10"></a><span data-ttu-id="6172c-105">编辑 Windows 10 的应用管理策略</span><span class="sxs-lookup"><span data-stu-id="6172c-105">Edit an app management policy for Windows 10</span></span>

1. <span data-ttu-id="6172c-106">转到位于 <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a> 的管理中心。</span><span class="sxs-lookup"><span data-stu-id="6172c-106">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.</span></span>     
2. <span data-ttu-id="6172c-107">在左侧导航中，选择 **"设备策略** \> **"。**</span><span class="sxs-lookup"><span data-stu-id="6172c-107">On the left nav, choose **Devices** \> **Policies** .</span></span>
1. <span data-ttu-id="6172c-108">选择现有的 Windows 应用策略，然后选择"编辑 **"。**</span><span class="sxs-lookup"><span data-stu-id="6172c-108">Choose an existing Windows app policy and then **Edit**.</span></span>
1. <span data-ttu-id="6172c-109">选择 **要** 更改的设置旁边的"编辑"，然后选择"保存 **"。**</span><span class="sxs-lookup"><span data-stu-id="6172c-109">Choose **Edit** next to a setting you want to change and then **Save**.</span></span>

## <a name="create-an-app-management-policy-for-windows-10"></a><span data-ttu-id="6172c-110">创建适用于 Windows 10 的应用管理</span><span class="sxs-lookup"><span data-stu-id="6172c-110">Create an app management policy for Windows 10</span></span>

<span data-ttu-id="6172c-111">如果用户在个人 Windows 10 设备上执行工作任务，也可以在该类设备上保护你的数据。</span><span class="sxs-lookup"><span data-stu-id="6172c-111">If your users have personal Windows 10 devices on which they perform work tasks, you can protect your data on those devices as well.</span></span>
  
1. <span data-ttu-id="6172c-112">转到位于 <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a> 的管理中心。</span><span class="sxs-lookup"><span data-stu-id="6172c-112">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.</span></span> 
2. <span data-ttu-id="6172c-113">在左侧导航上，选择 **"设备策略** \>  \> **""添加"。**</span><span class="sxs-lookup"><span data-stu-id="6172c-113">On the left nav, choose **Devices** \> **Policies** \> **Add**.</span></span>
3. <span data-ttu-id="6172c-114">在" **添加策略**"窗格中，输入此策略的唯一名称。</span><span class="sxs-lookup"><span data-stu-id="6172c-114">On the **Add policy** pane, enter a unique name for this policy.</span></span> 
4. <span data-ttu-id="6172c-115">在" **策略类型**"下，选择" **适用于 Windows 10 的应用程序管理**"。</span><span class="sxs-lookup"><span data-stu-id="6172c-115">Under **Policy type**, choose **Application Management for Windows 10**.</span></span>
5. <span data-ttu-id="6172c-116">在 **"设备类型**"下，选择"**个人"** 或 **"公司拥有"。**</span><span class="sxs-lookup"><span data-stu-id="6172c-116">Under **Device type**, choose either **Personal** or **Company Owned**.</span></span>
6. <span data-ttu-id="6172c-117">将自动打开" **加密工作文件**"。</span><span class="sxs-lookup"><span data-stu-id="6172c-117">The **Encrypt work files** is turned on automatically.</span></span> 
7. <span data-ttu-id="6172c-118">如果不希望用户在其电脑上保存工作文件，请将" **阻止用户将公司数据复制到个人文件，并强制其将工作文件保存到 OneDrive for Business**"设置为" **开**"。</span><span class="sxs-lookup"><span data-stu-id="6172c-118">Set **Prevent users from copying company data to personal files and force them to save work files to OneDrive for Business** to **On** if you don't want the users to save work files on their PC.</span></span> 
9. <span data-ttu-id="6172c-119">展开 **"恢复 Windows 设备上的数据"。**</span><span class="sxs-lookup"><span data-stu-id="6172c-119">Expand **Recover data on Windows devices**.</span></span> <span data-ttu-id="6172c-120">建议将其 **打开。**</span><span class="sxs-lookup"><span data-stu-id="6172c-120">We recommend that you turn it **On**.</span></span>
    <span data-ttu-id="6172c-121">必须先创建一个数据恢复代理证书，才能浏览到该证书的位置。</span><span class="sxs-lookup"><span data-stu-id="6172c-121">Before you can browse to the location of the Data Recovery Agent certificate, you have to first create one.</span></span> <span data-ttu-id="6172c-122">有关说明，请参阅 [Create and verify an Encrypting File System (EFS) Data Recovery Agent (DRA) certificate](/windows/security/information-protection/windows-information-protection/create-and-verify-an-efs-dra-certificate)。</span><span class="sxs-lookup"><span data-stu-id="6172c-122">For instructions, see [Create and verify an Encrypting File System (EFS) Data Recovery Agent (DRA) certificate](/windows/security/information-protection/windows-information-protection/create-and-verify-an-efs-dra-certificate).</span></span>
    
    <span data-ttu-id="6172c-123">默认情况下，使用存储在设备上并与用户配置文件相关联的密钥对工作文件进行加密。</span><span class="sxs-lookup"><span data-stu-id="6172c-123">By default, work files are encrypted using a secret key that is stored on the device and associated with the user's profile.</span></span> <span data-ttu-id="6172c-124">只有该用户可以打开和解密文件。</span><span class="sxs-lookup"><span data-stu-id="6172c-124">Only the user can open and decrypt the file.</span></span> <span data-ttu-id="6172c-125">但是，如果设备丢失或用户被删除，文件可能停滞在加密状态。</span><span class="sxs-lookup"><span data-stu-id="6172c-125">However, if a device is lost or a user is removed, a file can be stuck in an encrypted state.</span></span> <span data-ttu-id="6172c-126">管理员可以使用数据恢复代理 (DRA) 解密文件。</span><span class="sxs-lookup"><span data-stu-id="6172c-126">An admin can use the Data Recovery Agent (DRA) certificate to decrypt the file.</span></span>
    
    ![Browse to Data Recovery Agent certificate.](../media/7d7d664f-b72f-4293-a3e7-d0fa7371366c.png)
  
10. <span data-ttu-id="6172c-128">如果要 **添加其他域** 或 SharePoint Online 位置，请展开"保护其他网络和云位置"，以确保所有列出的应用中的文件都受到保护。</span><span class="sxs-lookup"><span data-stu-id="6172c-128">Expand **Protect additional network and cloud locations** if you want to add additional domains or SharePoint Online locations to make sure that files in all the listed apps are protected.</span></span> <span data-ttu-id="6172c-129">如需为某字段输入多个项，请使用分号 (;) 进行分隔。</span><span class="sxs-lookup"><span data-stu-id="6172c-129">If you need to enter more than one item for either field, use a semicolon (;) between the items.</span></span>
    
    ![Expand Protect additional network and cloud locations, and enter domains or SharePoint Online sites you own.](../media/7afaa0c7-ba53-456d-8c61-312c45e09625.png)
  
11. <span data-ttu-id="6172c-p104">Next decide **Who will get these settings?** If you don't want to use the default **All Users** security group, choose **Change**, choose the security groups who will get these settings \> **Select**.</span><span class="sxs-lookup"><span data-stu-id="6172c-p104">Next decide **Who will get these settings?** If you don't want to use the default **All Users** security group, choose **Change**, choose the security groups who will get these settings \> **Select**.</span></span>
12. <span data-ttu-id="6172c-133">最后，选择" **添加**"以保存该策略，并将其分配到设备。</span><span class="sxs-lookup"><span data-stu-id="6172c-133">Finally, choose **Add** to save the policy, and assign it to devices.</span></span>