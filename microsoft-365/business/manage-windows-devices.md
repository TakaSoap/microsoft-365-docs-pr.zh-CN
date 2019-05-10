---
title: 启用要由 Microsoft 365 商业版管理的加入域的 Windows 10 设备
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: 9b4de218-f1ad-41fa-a61b-e9e8ac0cf993
description: 了解如何启用 Microsoft 365 以保护本地 AD 加入 Windows 10 设备。
ms.openlocfilehash: 661e5bf8205a661eb4382b4bdd8fcf3a54ecc12f
ms.sourcegitcommit: db1dfb2df2c2f7beced3b57bc772d106c189e88a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "33660287"
---
# <a name="enable-domain-joined-windows-10-devices-to-be-managed-by-microsoft-365-business"></a><span data-ttu-id="ac698-103">启用要由 Microsoft 365 商业版管理的加入域的 Windows 10 设备</span><span class="sxs-lookup"><span data-stu-id="ac698-103">Enable domain-joined Windows 10 devices to be managed by Microsoft 365 Business</span></span>

<span data-ttu-id="ac698-104">如果您的组织使用的是本地 Windows Server Active Directory, 则可以将 Microsoft 365 商业版设置为保护 Windows 10 设备, 同时仍保持对需要本地身份验证的本地资源的访问权限。</span><span class="sxs-lookup"><span data-stu-id="ac698-104">If your organization uses Windows Server Active Directory on-premises, you can set up Microsoft 365 Business to protect your Windows 10 devices, while still maintaining access to on-premises resources that require local authentication.</span></span> <span data-ttu-id="ac698-105">你可以先将 Active Directory 与 Azure Active Directory 同步, 然后使用 Azure AD 注册 Windows 10 设备, 并注册 Microsoft 365 商业版的移动设备管理, 从而对此进行设置。</span><span class="sxs-lookup"><span data-stu-id="ac698-105">You can set this up by first synchronizing your Active Directory with Azure Active Directory, followed by registering the Windows 10 devices with Azure AD and enrolling them for mobile device management by Microsoft 365 Business.</span></span>
  
## <a name="set-up-domain-joined-devices-to-be-managed-by-microsoft-365-business"></a><span data-ttu-id="ac698-106">设置由 Microsoft 365 商业版管理的加入域的设备</span><span class="sxs-lookup"><span data-stu-id="ac698-106">Set up domain-joined devices to be managed by Microsoft 365 Business</span></span>

<span data-ttu-id="ac698-107">若要将组织的加入域的设备设置为从 Azure Active Directory 提供的功能中受益, 除了本地 Active Directory 之外, 还可以实现混合的**AZURE AD 加入设备**。</span><span class="sxs-lookup"><span data-stu-id="ac698-107">To set up your organization's domain-joined devices to benefit from the capabilities provided by Azure Active Directory in addition to on-premises Active Directory, you can implement **Hybrid Azure AD joined devices**.</span></span> <span data-ttu-id="ac698-108">这些是同时连接到本地 Active Directory 和 Azure Active Directory 的设备。</span><span class="sxs-lookup"><span data-stu-id="ac698-108">These are devices that are joined both to your on-premises Active Directory and your Azure Active Directory.</span></span> <span data-ttu-id="ac698-109">混合 Azure AD 加入的设备可受到 Microsoft 365 商业版的保护和管理。</span><span class="sxs-lookup"><span data-stu-id="ac698-109">Hybrid Azure AD joined devices can be protected and managed by Microsoft 365 Business.</span></span> 
  
<span data-ttu-id="ac698-110">完成以下步骤, 使 Microsoft 365 商业版加入和管理 Windows 10 设备混合的 Azure AD。</span><span class="sxs-lookup"><span data-stu-id="ac698-110">Complete the steps below to make your Windows 10 devices Hybrid Azure AD joined and managed by Microsoft 365 Business.</span></span>
  
1. <span data-ttu-id="ac698-111">若要将您的用户、组和联系人从本地 Active Directory 同步到 Azure Active Directory, 请运行目录同步向导和 Azure Active Directory Connect, 如[设置 Office 365 的 "设置目录同步](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846)" 中所述。</span><span class="sxs-lookup"><span data-stu-id="ac698-111">To synchronize your users, groups and contacts from local Active Directory into Azure Active Directory, run the Directory synchronization wizard and Azure Active Directory Connect as described in [Set up directory synchronization for Office 365](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="ac698-112">对于 Microsoft 365 商业版的步骤完全相同。</span><span class="sxs-lookup"><span data-stu-id="ac698-112">The steps are exactly the same for Microsoft 365 Business.</span></span> 
  
2. <span data-ttu-id="ac698-113">在完成第3步以使 Windows 10 设备成为合并的 Azure AD 之前, 您需要确保满足以下先决条件:</span><span class="sxs-lookup"><span data-stu-id="ac698-113">Before you complete step 3 to enable Windows 10 devices to be Hybrid Azure AD joined, you need to make sure that you meet the following prerequisites:</span></span>

   - <span data-ttu-id="ac698-114">您运行的是最新版本的 Azure AD connect。</span><span class="sxs-lookup"><span data-stu-id="ac698-114">You are running the latest version of Azure AD connect.</span></span>

   - <span data-ttu-id="ac698-115">Azure AD connect 已同步要连接混合 Azure AD 的设备的所有计算机对象。</span><span class="sxs-lookup"><span data-stu-id="ac698-115">Azure AD connect has synchronized all the computer objects of the devices you want to be hybrid Azure AD joined.</span></span> <span data-ttu-id="ac698-116">如果计算机对象属于特定的组织单位 (OU), 请确保将这些 Ou 设置为在 Azure AD connect 中进行同步。</span><span class="sxs-lookup"><span data-stu-id="ac698-116">If the computer objects belong to specific organizational units (OU), then make sure these OUs are set for synchronization in Azure AD connect as well.</span></span>
    
3. <span data-ttu-id="ac698-117">将现有的加入域的 Windows 10 设备注册为混合 Azure AD 加入并注册为 Intune (Microsoft 365 Business) 进行移动设备管理:</span><span class="sxs-lookup"><span data-stu-id="ac698-117">Register existing domain-joined Windows 10 devices to be hybrid Azure AD Joined and enroll them for mobile device management by Intune (Microsoft 365 Business):</span></span>
    
4. <span data-ttu-id="ac698-118">按照[如何配置混合 Azure Active Directory 已加入设备](https://go.microsoft.com/fwlink/p/?linkid=872870)的分步说明操作。</span><span class="sxs-lookup"><span data-stu-id="ac698-118">Follow the step by step instructions in [How to configure hybrid Azure Active Directory joined devices](https://go.microsoft.com/fwlink/p/?linkid=872870).</span></span> <span data-ttu-id="ac698-119">这将启用已加入 Windows 10 计算机的本地 Active Directory 的同步, 并使其成为云就绪状态。</span><span class="sxs-lookup"><span data-stu-id="ac698-119">This will enable the synchronization of your on-premises Active Directory joined Windows 10 computers and make them cloud ready.</span></span>
    
5. <span data-ttu-id="ac698-120">若要为移动设备管理注册 Windows 10 设备, 请参阅[使用组策略向 Intune 注册 windows 10 设备](https://go.microsoft.com/fwlink/p/?linkid=872871), 以获取说明。</span><span class="sxs-lookup"><span data-stu-id="ac698-120">In order to enroll a Windows 10 device for mobile device management, see [Enroll a Windows 10 device with Intune by using a Group Policy](https://go.microsoft.com/fwlink/p/?linkid=872871) for instructions.</span></span> <span data-ttu-id="ac698-121">您可以在本地计算机级别或批量操作中设置组策略, 您可以在域控制器服务器上创建此组策略设置。</span><span class="sxs-lookup"><span data-stu-id="ac698-121">You can set the Group Policy at a local computer level or for bulk operations, you can create this group policy setting on your domain controller server.</span></span>