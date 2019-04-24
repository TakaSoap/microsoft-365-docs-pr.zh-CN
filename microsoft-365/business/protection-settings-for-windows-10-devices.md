---
title: 设置 Windows 10 设备的应用程序保护设置
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 02e74022-44af-414b-9d74-0ebf5c2197f0
description: 了解如何在 Windows 10 设备上创建应用管理策略并保护工作文件。
ms.openlocfilehash: 289c6a74f6ccb53f6a833612a7b4a5bcddd3ea56
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32278152"
---
# <a name="set-application-protection-settings-for-windows-10-devices"></a><span data-ttu-id="fd9b5-103">设置 Windows 10 设备的应用程序保护设置</span><span class="sxs-lookup"><span data-stu-id="fd9b5-103">Set application protection settings for Windows 10 devices</span></span>

## <a name="create-an-app-management-policy-for-windows-10"></a><span data-ttu-id="fd9b5-104">创建适用于 Windows 10 的应用管理</span><span class="sxs-lookup"><span data-stu-id="fd9b5-104">Create an app management policy for Windows 10</span></span>

<span data-ttu-id="fd9b5-105">如果用户在个人 Windows 10 设备上执行工作任务，也可以在该类设备上保护你的数据。</span><span class="sxs-lookup"><span data-stu-id="fd9b5-105">If your users have personal Windows 10 devices on which they perform work tasks, you can protect your data on those devices as well.</span></span>
  
1. <span data-ttu-id="fd9b5-106">使用全局管理员凭据登录到[admin center](https://go.microsoft.com/fwlink/p/?linkid=837890) 。</span><span class="sxs-lookup"><span data-stu-id="fd9b5-106">Sign in to [admin center](https://go.microsoft.com/fwlink/p/?linkid=837890) with global admin credentials.</span></span> <span data-ttu-id="fd9b5-107">选择" **管理**"图块，进入管理中心。</span><span class="sxs-lookup"><span data-stu-id="fd9b5-107">Choose the **Admin** tile to go to the admin center.</span></span> 
    
2. <span data-ttu-id="fd9b5-108">在左侧导航中, 选择 "**设备** \> **策略** \> " "**添加**"。</span><span class="sxs-lookup"><span data-stu-id="fd9b5-108">On the left nav, choose **Devices** \> **Policies** \> **Add**.</span></span>

3. <span data-ttu-id="fd9b5-109">在" **添加策略**"窗格中，输入此策略的唯一名称。</span><span class="sxs-lookup"><span data-stu-id="fd9b5-109">On the **Add policy** pane, enter a unique name for this policy.</span></span> 
    
4. <span data-ttu-id="fd9b5-110">在" **策略类型**"下，选择" **适用于 Windows 10 的应用程序管理**"。</span><span class="sxs-lookup"><span data-stu-id="fd9b5-110">Under **Policy type**, choose **Application Management for Windows 10**.</span></span>
    
5. <span data-ttu-id="fd9b5-111">Under \*\* Device type \*\*, choose either **Personal** or **Company Owned**.</span><span class="sxs-lookup"><span data-stu-id="fd9b5-111">Under \*\* Device type \*\*, choose either **Personal** or **Company Owned**.</span></span>
    
6. <span data-ttu-id="fd9b5-112">将自动打开" **加密工作文件**"。</span><span class="sxs-lookup"><span data-stu-id="fd9b5-112">The **Encrypt work files** is turned on automatically.</span></span> 
    
7. <span data-ttu-id="fd9b5-113">如果不希望用户在其电脑上保存工作文件，请将" **阻止用户将公司数据复制到个人文件，并强制其将工作文件保存到 OneDrive for Business**"设置为" **开**"。</span><span class="sxs-lookup"><span data-stu-id="fd9b5-113">Set **Prevent users from copying company data to personal files and force them to save work files to OneDrive for Business** to **On** if you don't want the users to save work files on their PC.</span></span> 
    
8. <span data-ttu-id="fd9b5-114">Expand **Manage how users access Office files on devices** \> configure the settings how you would like.</span><span class="sxs-lookup"><span data-stu-id="fd9b5-114">Expand **Manage how users access Office files on devices** \> configure the settings how you would like.</span></span> <span data-ttu-id="fd9b5-115">The **Manage how users access Office devices on mobile devices** is **Off** by default, but it is recommended that you turn it **On** and accept the default values.</span><span class="sxs-lookup"><span data-stu-id="fd9b5-115">The **Manage how users access Office devices on mobile devices** is **Off** by default, but it is recommended that you turn it **On** and accept the default values.</span></span> <span data-ttu-id="fd9b5-116">有关详细信息, 请参阅[可用设置](#available-settings)。</span><span class="sxs-lookup"><span data-stu-id="fd9b5-116">See [Available settings](#available-settings)for more information.</span></span> 
    
    <span data-ttu-id="fd9b5-117">始终可使用" **重置默认设置**"链接返回到默认设置。</span><span class="sxs-lookup"><span data-stu-id="fd9b5-117">You can always use the **Reset default settings** link to return to the default setting.</span></span> 
    
9. <span data-ttu-id="fd9b5-118">展开" **恢复 Windows 设备上的数据**"，建议将其设置为" **开**"。</span><span class="sxs-lookup"><span data-stu-id="fd9b5-118">Expand **Recover data on Windows devices** and it is recommended that you turn it **On**.</span></span>
    
    <span data-ttu-id="fd9b5-p103">必须先创建一个数据恢复代理证书，才能浏览到该证书的位置。有关说明，请参阅[创建并验证加密文件系统 (EFS) 数据恢复代理 (DRA) 证书](https://go.microsoft.com/fwlink/p/?linkid=853700)。</span><span class="sxs-lookup"><span data-stu-id="fd9b5-p103">Before you can browse to the location of the Data Recovery Agent certificate, you have to first create one. For instructions see, [Create and verify an Encrypting File System (EFS) Data Recovery Agent (DRA) certificate](https://go.microsoft.com/fwlink/p/?linkid=853700).</span></span>
    
    <span data-ttu-id="fd9b5-p104">默认情况下，使用存储在设备上并与用户配置文件相关联的密钥对工作文件进行加密。只有该用户可以打开和解密文件。但是，如果设备丢失或用户被删除，文件可能停滞在加密状态。管理员可以使用数据恢复代理 (DRA) 证书对文件解密。</span><span class="sxs-lookup"><span data-stu-id="fd9b5-p104">By default, work files are encrypted using a secret key that is stored on the device and associated with the user's profile. Only the user can open and decrypt the file. However, if a device is lost or a user is removed, a file can be stuck in an encrypted state. The Data Recovery Agent (DRA) certificate can be used by an admin to decrypt the file.</span></span>
    
    ![Browse to Data Recovery Agent certificate.](media/7d7d664f-b72f-4293-a3e7-d0fa7371366c.png)
  
10. <span data-ttu-id="fd9b5-p105">若要添加其他域或 SharePoint Online 位置，确保所有列出应用中的文件均受到保护，请展开" **保护其他网络和云位置**"。如需为某字段输入多个项，请使用分号 (;) 进行分隔。</span><span class="sxs-lookup"><span data-stu-id="fd9b5-p105">Expand **Protect additional network and cloud locations** if you want to add additional domains or SharePoint Online locations to make sure that files in all the listed apps will be protected. If you need to enter more than one item for either field, use a semicolon (;) between the items.</span></span> 
    
    ![Expand Protect additional network and cloud locations, and enter domains or SharePoint Online sites you own.](media/7afaa0c7-ba53-456d-8c61-312c45e09625.png)
  
11. <span data-ttu-id="fd9b5-p106">Next decide **Who will get these settings?** If you don't want to use the default **All Users** security group, choose **Change**, choose the security groups who will get these settings \> **Select**.</span><span class="sxs-lookup"><span data-stu-id="fd9b5-p106">Next decide **Who will get these settings?** If you don't want to use the default **All Users** security group, choose **Change**, choose the security groups who will get these settings \> **Select**.</span></span>
    
12. <span data-ttu-id="fd9b5-131">最后，选择" **添加**"以保存该策略，并将其分配到设备。</span><span class="sxs-lookup"><span data-stu-id="fd9b5-131">Finally, choose **Add** to save the policy, and assign it to devices.</span></span> 
    
## <a name="available-settings"></a><span data-ttu-id="fd9b5-132">可用设置</span><span class="sxs-lookup"><span data-stu-id="fd9b5-132">Available settings</span></span>

<span data-ttu-id="fd9b5-133">以下设置可用于管理用户访问 Office 工作文件的方式：</span><span class="sxs-lookup"><span data-stu-id="fd9b5-133">The following settings are available to manage how users access Office work files.</span></span>
  
<span data-ttu-id="fd9b5-134">有关详细信息，请参阅 [Microsoft 365 商业版中的保护功能如何映射到 Intune 设置](map-protection-features-to-intune-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="fd9b5-134">For more information, see [How do protection features in Microsoft 365 Business map to Intune settings](map-protection-features-to-intune-settings.md).</span></span>
  
|<span data-ttu-id="fd9b5-135">**设置**</span><span class="sxs-lookup"><span data-stu-id="fd9b5-135">**Setting**</span></span>|<span data-ttu-id="fd9b5-136">**说明**</span><span class="sxs-lookup"><span data-stu-id="fd9b5-136">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="fd9b5-137">需要 PIN 或指纹才能访问 Office 应用</span><span class="sxs-lookup"><span data-stu-id="fd9b5-137">Require a PIN or fingerprint to access Office apps</span></span>  <br/> |<span data-ttu-id="fd9b5-138">如果此设置在" **开**"位置，则用户必须在提供用户名和密码后再提供一种形式的身份验证，才能在其移动设备上使用 Office 应用。</span><span class="sxs-lookup"><span data-stu-id="fd9b5-138">If this settings is **On** users have to provide another form of authentication, in addition to their username and password, before they can use Office apps on their mobile device.</span></span>  <br/> |
|<span data-ttu-id="fd9b5-139">登录失败以下次数后重置 PIN</span><span class="sxs-lookup"><span data-stu-id="fd9b5-139">Reset PIN when login fails this many times</span></span>  <br/> |<span data-ttu-id="fd9b5-140">若要防止未经授权的用户随机猜测 PIN，PIN 将在达到指定的错误输入次数后重置。</span><span class="sxs-lookup"><span data-stu-id="fd9b5-140">To prevent an unauthorized user from randomly guessing a PIN, the PIN will reset after the number of wrong entries that you specify.</span></span>  <br/> |
|<span data-ttu-id="fd9b5-141">要求用户在 Office 应用空闲以下时间后重新登录</span><span class="sxs-lookup"><span data-stu-id="fd9b5-141">Require users to sign in again after Office apps have been idle for</span></span>  <br/> |<span data-ttu-id="fd9b5-142">此设置确定用户保持空闲状态多久后系统会提示再次登录。</span><span class="sxs-lookup"><span data-stu-id="fd9b5-142">This setting determines how long a user can be idle before they are prompted to sign in again.</span></span>  <br/> |
   

