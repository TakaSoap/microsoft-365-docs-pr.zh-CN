---
title: 在基本移动性和安全性中管理设备访问设置
f1.keywords:
- NOCSH
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
ms.custom:
- AdminSurgePortfolio
search.appverid:
- MET150
description: 基本移动性和安全性可帮助您保护和管理移动设备。
ms.openlocfilehash: 0d8f4293c45bcc1dc2a71dbc749641cf3791337e
ms.sourcegitcommit: 2179abfe0b7a8bea917eb1c1057ed3795bdf91e6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/02/2020
ms.locfileid: "47336735"
---
# <a name="manage-device-access-settings-in-basic-mobility-and-security"></a><span data-ttu-id="ca832-103">在基本移动性和安全性中管理设备访问设置</span><span class="sxs-lookup"><span data-stu-id="ca832-103">Manage device access settings in Basic Mobility and Security</span></span>

<span data-ttu-id="ca832-104">如果使用的是基本移动性和安全性，则可能存在无法使用基本移动性和安全性进行管理的设备。</span><span class="sxs-lookup"><span data-stu-id="ca832-104">If you're using Basic Mobility and Security, there might be devices that you can't manage with Basic Mobility and Security.</span></span> <span data-ttu-id="ca832-105">如果是这样，则应阻止 Exchange ActiveSync 应用程序访问 Microsoft 365 电子邮件，以获取基本移动性和安全性不受支持的移动设备。</span><span class="sxs-lookup"><span data-stu-id="ca832-105">If so, you should block Exchange ActiveSync app access to Microsoft 365 email for mobile devices that aren't supported by Basic Mobility and Security.</span></span> <span data-ttu-id="ca832-106">这有助于在更多设备上保护组织信息。</span><span class="sxs-lookup"><span data-stu-id="ca832-106">This helps secure your organization information across more devices.</span></span>

<span data-ttu-id="ca832-107">请按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="ca832-107">Use these steps:</span></span>

1. <span data-ttu-id="ca832-108">使用全局管理员帐户登录到 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="ca832-108">Sign in to  Microsoft 365 with your global admin account.</span></span>
    
2. <span data-ttu-id="ca832-109">在浏览器中，键入：  [https://protection.office.com](https://protection.office.com/) 。</span><span class="sxs-lookup"><span data-stu-id="ca832-109">In your browser, type: [https://protection.office.com](https://protection.office.com/).</span></span>    

    >[!IMPORTANT]
    ><span data-ttu-id="ca832-110">如果这是你第一次使用 MDM for Microsoft 365 商业标准，请在此处激活： [激活移动设备管理](https://admin.microsoft.com/EAdmin/Device/IntuneInventory.aspx)。</span><span class="sxs-lookup"><span data-stu-id="ca832-110">If this is the first time you're using MDM for Microsoft 365 Business Standard, activate it here: [Activate Mobile Device Management](https://admin.microsoft.com/EAdmin/Device/IntuneInventory.aspx).</span></span> <span data-ttu-id="ca832-111">激活后，使用 [Office 365 安全性管理设备 & 合规性](https://protection.office.com/)。</span><span class="sxs-lookup"><span data-stu-id="ca832-111">After you've activated it, manage your devices with [Office 365 Security & Compliance](https://protection.office.com/).</span></span>

3. <span data-ttu-id="ca832-112">转到 "数据丢失防护" > **设备管理**   > " **设备策略**，然后选择" **管理组织范围的设备访问设置**"。</span><span class="sxs-lookup"><span data-stu-id="ca832-112">Go to Data loss prevention > **Device management** > **Device policies**, and select **Manage organization-wide device access settings**.</span></span>
    
4. <span data-ttu-id="ca832-113">选择 " **阻止**"。</span><span class="sxs-lookup"><span data-stu-id="ca832-113">Select **Block**.</span></span>

    :::image type="content" source="../../media/basic-mobility-security/bms-5-block-access.png" alt-text="基本移动性和安全块访问复选框":::

5. <span data-ttu-id="ca832-115">选择 " **保存**"。</span><span class="sxs-lookup"><span data-stu-id="ca832-115">Select **Save**.</span></span> 

<span data-ttu-id="ca832-116">若要了解基本移动性和安全性支持的设备，请参阅 [基本移动性和安全性的功能](capabilities-of-basic-mobility-and-secruity.md)。</span><span class="sxs-lookup"><span data-stu-id="ca832-116">To learn what devices Basic Mobility and Security supports, see [Capabilities of Basic Mobility and Security](capabilities-of-basic-mobility-and-secruity.md).</span></span>