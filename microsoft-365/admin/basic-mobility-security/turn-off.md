---
title: 关闭基本移动性和安全性
f1.keywords: NOCSH
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
- Adm_TOC
ms.custom: AdminSurgePortfolio
description: 删除组或策略以关闭基本移动性和安全性。
ms.openlocfilehash: 0786ac8ebd190b9af3211c211cc6db2ea9e0ea48
ms.sourcegitcommit: 8849dd6f80217c29f427c7f008d918f30c792240
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/15/2021
ms.locfileid: "49876836"
---
# <a name="turn-off-basic-mobility-and-security"></a><span data-ttu-id="d243b-103">关闭基本移动性和安全性</span><span class="sxs-lookup"><span data-stu-id="d243b-103">Turn off Basic Mobility and Security</span></span>

<span data-ttu-id="d243b-104">若要有效地关闭基本移动性和安全性，请从设备管理策略中删除由安全组定义的用户组，或者删除策略本身。</span><span class="sxs-lookup"><span data-stu-id="d243b-104">To effectively turn off Basic Mobility and Security, you remove groups of people defined by security groups from the device management policies, or remove the policies themselves.</span></span>

- <span data-ttu-id="d243b-105">通过从已创建的设备策略中删除用户安全组来删除用户组。</span><span class="sxs-lookup"><span data-stu-id="d243b-105">Remove groups of users by removing user security groups from the device policies you've created.</span></span>

- <span data-ttu-id="d243b-106">通过删除所有基本移动和安全设备策略，为所有人禁用基本移动性和安全性。</span><span class="sxs-lookup"><span data-stu-id="d243b-106">Disable Basic Mobility and Security for everyone by removing all Basic Mobility and Security device policies.</span></span>

<span data-ttu-id="d243b-107">这些选项可删除组织中设备的基本移动性和安全性强制。</span><span class="sxs-lookup"><span data-stu-id="d243b-107">These options remove Basic Mobility and Security enforcement for devices in your organization.</span></span> <span data-ttu-id="d243b-108">遗憾的是，在设置基本移动性和安全性后，不能简单地"取消设置"。</span><span class="sxs-lookup"><span data-stu-id="d243b-108">Unfortunately, you can't simply "unprovision" Basic Mobility and Security after you've set it up.</span></span> 

>[!IMPORTANT]
><span data-ttu-id="d243b-109">从策略中删除用户安全组或删除策略本身时，请注意对用户设备的影响。</span><span class="sxs-lookup"><span data-stu-id="d243b-109">Be aware of the impact on users' devices when you remove user security groups from policies or remove the policies themselves.</span></span> <span data-ttu-id="d243b-110">例如，电子邮件配置文件和缓存的电子邮件可能会被删除，具体取决于设备。</span><span class="sxs-lookup"><span data-stu-id="d243b-110">For example, email profiles and cached emails might be removed, depending on the device.</span></span> <span data-ttu-id="d243b-111">有关详细信息，请参阅删除策略或从策略中删除用户  [时会发生什么情况？](https://support.microsoft.com/office/create-device-security-policies-in-basic-mobility-and-security-d310f556-8bfb-497b-9bd7-fe3c36ea2fd6#bkmk_changeimpact)</span><span class="sxs-lookup"><span data-stu-id="d243b-111">For more info, see  [What happens when you delete a policy or remove a user from the policy?](https://support.microsoft.com/office/create-device-security-policies-in-basic-mobility-and-security-d310f556-8bfb-497b-9bd7-fe3c36ea2fd6#bkmk_changeimpact)</span></span>

## <a name="remove-user-security-groups-from-basic-mobility-and-security-device-policies"></a><span data-ttu-id="d243b-112">从基本移动和安全设备策略中删除用户安全组</span><span class="sxs-lookup"><span data-stu-id="d243b-112">Remove user security groups from Basic Mobility and Security device policies</span></span>

1. <span data-ttu-id="d243b-113">在浏览器类型中  [https://protection.office.com/devicev2](https://protection.office.com/devicev2) ：。</span><span class="sxs-lookup"><span data-stu-id="d243b-113">In your browser type: [https://protection.office.com/devicev2](https://protection.office.com/devicev2).</span></span>

2. <span data-ttu-id="d243b-114">选择设备策略，然后选择"编辑 **策略"。**</span><span class="sxs-lookup"><span data-stu-id="d243b-114">Select a device policy, and select **Edit policy**.</span></span> 

3. <span data-ttu-id="d243b-115">在" **部署**   "页上，选择"**删除"。**</span><span class="sxs-lookup"><span data-stu-id="d243b-115">On the  **Deployment**  page, select **Remove**.</span></span>

4. <span data-ttu-id="d243b-116">在  **"组"** 下，选择一个安全组。</span><span class="sxs-lookup"><span data-stu-id="d243b-116">Under  **Groups**, select a security group.</span></span>

5. <span data-ttu-id="d243b-117">选择  **"** 删除"，然后选择"**保存"。**</span><span class="sxs-lookup"><span data-stu-id="d243b-117">Select  **Remove**, and select **Save**.</span></span>

## <a name="remove-basic-mobility-and-security-device-policies"></a><span data-ttu-id="d243b-118">删除基本移动和安全设备策略</span><span class="sxs-lookup"><span data-stu-id="d243b-118">Remove Basic Mobility and Security device policies</span></span>

1.  <span data-ttu-id="d243b-119">在浏览器类型中  [https://protection.office.com/devicev2](https://protection.office.com/devicev2) ：。</span><span class="sxs-lookup"><span data-stu-id="d243b-119">In your browser type: [https://protection.office.com/devicev2](https://protection.office.com/devicev2).</span></span> 

2.  <span data-ttu-id="d243b-120">选择设备策略，然后选择"删除 **策略"。**</span><span class="sxs-lookup"><span data-stu-id="d243b-120">Select a device policy, and then select  **Delete policy**.</span></span>
    
3.  <span data-ttu-id="d243b-121">在"警告"对话框中，选择"**是"。**</span><span class="sxs-lookup"><span data-stu-id="d243b-121">In the Warning dialog box, select **Yes**.</span></span>

>[!NOTE]
><span data-ttu-id="d243b-122">有关在组织设备仍处于阻止状态时取消阻止设备的更多步骤，请参阅博客文章"从 [Office 365](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Removing-Access-Control-from-Mobile-Device-Management-for-Office/ba-p/279934)移动设备管理中删除访问控制"。</span><span class="sxs-lookup"><span data-stu-id="d243b-122">For more steps to unblock devices if your organization devices are still in a blocked state,  see the blog post [Removing Access Control from Mobile Device Management for Office 365](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Removing-Access-Control-from-Mobile-Device-Management-for-Office/ba-p/279934).</span></span>
