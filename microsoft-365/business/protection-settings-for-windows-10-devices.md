---
title: 设置 Windows 10 设备的应用程序保护设置
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 02e74022-44af-414b-9d74-0ebf5c2197f0
description: 了解如何在 Windows 10 设备上创建应用管理策略并保护工作文件。
ms.openlocfilehash: ca6d789e0242975a0395e6cf5653d3f43f819801
ms.sourcegitcommit: 5d11f516e78ea4a74145e19ba2300f0792c8bac1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/19/2019
ms.locfileid: "38715244"
---
# <a name="set-application-protection-settings-for-windows-10-devices"></a><span data-ttu-id="a5b33-103">设置 Windows 10 设备的应用程序保护设置</span><span class="sxs-lookup"><span data-stu-id="a5b33-103">Set application protection settings for Windows 10 devices</span></span>

## <a name="create-an-app-management-policy-for-windows-10"></a><span data-ttu-id="a5b33-104">创建适用于 Windows 10 的应用管理</span><span class="sxs-lookup"><span data-stu-id="a5b33-104">Create an app management policy for Windows 10</span></span>

<span data-ttu-id="a5b33-105">如果用户在个人 Windows 10 设备上执行工作任务，也可以在该类设备上保护你的数据。</span><span class="sxs-lookup"><span data-stu-id="a5b33-105">If your users have personal Windows 10 devices on which they perform work tasks, you can protect your data on those devices as well.</span></span>
  
1. <span data-ttu-id="a5b33-106">转到位于 <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a> 的管理中心。</span><span class="sxs-lookup"><span data-stu-id="a5b33-106">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.</span></span> 
    
2. <span data-ttu-id="a5b33-107">在左侧导航中，选择 "**设备** \> **策略** \> " "**添加**"。</span><span class="sxs-lookup"><span data-stu-id="a5b33-107">On the left nav, choose **Devices** \> **Policies** \> **Add**.</span></span>

3. <span data-ttu-id="a5b33-108">在" **添加策略**"窗格中，输入此策略的唯一名称。</span><span class="sxs-lookup"><span data-stu-id="a5b33-108">On the **Add policy** pane, enter a unique name for this policy.</span></span> 
    
4. <span data-ttu-id="a5b33-109">在" **策略类型**"下，选择" **适用于 Windows 10 的应用程序管理**"。</span><span class="sxs-lookup"><span data-stu-id="a5b33-109">Under **Policy type**, choose **Application Management for Windows 10**.</span></span>
    
5. <span data-ttu-id="a5b33-110">在 "**设备类型**" 下，选择 "**个人**或**公司所有者**"。</span><span class="sxs-lookup"><span data-stu-id="a5b33-110">Under **Device type**, choose either **Personal** or **Company Owned**.</span></span>
    
6. <span data-ttu-id="a5b33-111">将自动打开" **加密工作文件**"。</span><span class="sxs-lookup"><span data-stu-id="a5b33-111">The **Encrypt work files** is turned on automatically.</span></span> 
    
7. <span data-ttu-id="a5b33-112">如果不希望用户在其电脑上保存工作文件，请将" **阻止用户将公司数据复制到个人文件，并强制其将工作文件保存到 OneDrive for Business**"设置为" **开**"。</span><span class="sxs-lookup"><span data-stu-id="a5b33-112">Set **Prevent users from copying company data to personal files and force them to save work files to OneDrive for Business** to **On** if you don't want the users to save work files on their PC.</span></span> 
    
9. <span data-ttu-id="a5b33-113">扩展**Windows 设备上的恢复数据**。</span><span class="sxs-lookup"><span data-stu-id="a5b33-113">Expand **Recover data on Windows devices**.</span></span> <span data-ttu-id="a5b33-114">我们建议您**将其打开**。</span><span class="sxs-lookup"><span data-stu-id="a5b33-114">We recommend that you turn it **On**.</span></span>
    
    <span data-ttu-id="a5b33-115">必须先创建一个数据恢复代理证书，才能浏览到该证书的位置。</span><span class="sxs-lookup"><span data-stu-id="a5b33-115">Before you can browse to the location of the Data Recovery Agent certificate, you have to first create one.</span></span> <span data-ttu-id="a5b33-116">有关说明，请参阅[创建和验证加密文件系统（EFS）数据恢复代理（DRA）证书](https://go.microsoft.com/fwlink/p/?linkid=853700)。</span><span class="sxs-lookup"><span data-stu-id="a5b33-116">For instructions, see [Create and verify an Encrypting File System (EFS) Data Recovery Agent (DRA) certificate](https://go.microsoft.com/fwlink/p/?linkid=853700).</span></span>
    
    <span data-ttu-id="a5b33-117">默认情况下，使用存储在设备上并与用户配置文件相关联的密钥对工作文件进行加密。</span><span class="sxs-lookup"><span data-stu-id="a5b33-117">By default, work files are encrypted using a secret key that is stored on the device and associated with the user's profile.</span></span> <span data-ttu-id="a5b33-118">只有该用户可以打开和解密文件。</span><span class="sxs-lookup"><span data-stu-id="a5b33-118">Only the user can open and decrypt the file.</span></span> <span data-ttu-id="a5b33-119">但是，如果设备丢失或用户被删除，文件可能停滞在加密状态。</span><span class="sxs-lookup"><span data-stu-id="a5b33-119">However, if a device is lost or a user is removed, a file can be stuck in an encrypted state.</span></span> <span data-ttu-id="a5b33-120">管理员可以使用数据恢复代理（DRA）证书对文件进行解密。</span><span class="sxs-lookup"><span data-stu-id="a5b33-120">An admin can use the Data Recovery Agent (DRA) certificate to decrypt the file.</span></span>
    
    ![Browse to Data Recovery Agent certificate.](media/7d7d664f-b72f-4293-a3e7-d0fa7371366c.png)
  
10. <span data-ttu-id="a5b33-122">如果要添加其他域或 SharePoint Online 位置，请展开 "**保护其他网络和云位置**"，以确保所有列出的应用程序中的文件都受到保护。</span><span class="sxs-lookup"><span data-stu-id="a5b33-122">Expand **Protect additional network and cloud locations** if you want to add additional domains or SharePoint Online locations to make sure that files in all the listed apps are protected.</span></span> <span data-ttu-id="a5b33-123">如需为某字段输入多个项，请使用分号 (;) 进行分隔。</span><span class="sxs-lookup"><span data-stu-id="a5b33-123">If you need to enter more than one item for either field, use a semicolon (;) between the items.</span></span>
    
    ![Expand Protect additional network and cloud locations, and enter domains or SharePoint Online sites you own.](media/7afaa0c7-ba53-456d-8c61-312c45e09625.png)
  
11. <span data-ttu-id="a5b33-p105">Next decide **Who will get these settings?** If you don't want to use the default **All Users** security group, choose **Change**, choose the security groups who will get these settings \> **Select**.</span><span class="sxs-lookup"><span data-stu-id="a5b33-p105">Next decide **Who will get these settings?** If you don't want to use the default **All Users** security group, choose **Change**, choose the security groups who will get these settings \> **Select**.</span></span>
    
12. <span data-ttu-id="a5b33-127">最后，选择" **添加**"以保存该策略，并将其分配到设备。</span><span class="sxs-lookup"><span data-stu-id="a5b33-127">Finally, choose **Add** to save the policy, and assign it to devices.</span></span> 