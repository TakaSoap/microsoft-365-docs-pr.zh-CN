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
description: 基本移动性和安全性可以帮助您保护和管理移动设备。
ms.openlocfilehash: dd9d777798c2c96776a8f9b40a3c4dfe0b95702a
ms.sourcegitcommit: 8849dd6f80217c29f427c7f008d918f30c792240
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/15/2021
ms.locfileid: "49876944"
---
# <a name="manage-device-access-settings-in-basic-mobility-and-security"></a><span data-ttu-id="b1237-103">在基本移动性和安全性中管理设备访问设置</span><span class="sxs-lookup"><span data-stu-id="b1237-103">Manage device access settings in Basic Mobility and Security</span></span>

<span data-ttu-id="b1237-104">如果你使用的是基本移动性和安全性，则可能有一些设备无法通过基本移动性和安全性进行管理。</span><span class="sxs-lookup"><span data-stu-id="b1237-104">If you're using Basic Mobility and Security, there might be devices that you can't manage with Basic Mobility and Security.</span></span> <span data-ttu-id="b1237-105">如果是这样，你应该阻止Exchange ActiveSync移动性和安全性不支持的移动设备访问 Microsoft 365 电子邮件。</span><span class="sxs-lookup"><span data-stu-id="b1237-105">If so, you should block Exchange ActiveSync app access to Microsoft 365 email for mobile devices that aren't supported by Basic Mobility and Security.</span></span> <span data-ttu-id="b1237-106">这有助于跨更多设备保护组织信息。</span><span class="sxs-lookup"><span data-stu-id="b1237-106">This helps secure your organization information across more devices.</span></span>

<span data-ttu-id="b1237-107">使用以下步骤：</span><span class="sxs-lookup"><span data-stu-id="b1237-107">Use these steps:</span></span>

1. <span data-ttu-id="b1237-108">使用全局管理员帐户登录 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="b1237-108">Sign in to  Microsoft 365 with your global admin account.</span></span>

2. <span data-ttu-id="b1237-109">在浏览器中，键入：  [https://protection.office.com](https://protection.office.com/) 。</span><span class="sxs-lookup"><span data-stu-id="b1237-109">In your browser, type: [https://protection.office.com](https://protection.office.com/).</span></span>    

    >[!IMPORTANT]
    ><span data-ttu-id="b1237-110">如果这是第一次使用 Microsoft 365 商业标准版的基本移动性和安全性，请在此处激活：激活基本安全性和 [移动性](https://admin.microsoft.com/EAdmin/Device/IntuneInventory.aspx)。</span><span class="sxs-lookup"><span data-stu-id="b1237-110">If this is the first time you're using Basic Mobility and Security for Microsoft 365 Business Standard, activate it here: [Activate Basic Security and Mobility](https://admin.microsoft.com/EAdmin/Device/IntuneInventory.aspx).</span></span> <span data-ttu-id="b1237-111">激活后，使用 [Office 365](https://protection.office.com/)安全与合规&设备。</span><span class="sxs-lookup"><span data-stu-id="b1237-111">After you've activated it, manage your devices with [Office 365 Security & Compliance](https://protection.office.com/).</span></span>

3. <span data-ttu-id="b1237-112">转到设备管理设备>数据丢失防护， \*\*\*\* 然后选择"管理   >  \*\*\*\* **组织范围内的设备访问设置"。**</span><span class="sxs-lookup"><span data-stu-id="b1237-112">Go to Data loss prevention > **Device management** > **Device policies**, and select **Manage organization-wide device access settings**.</span></span>

4. <span data-ttu-id="b1237-113">选择 **"阻止"。**</span><span class="sxs-lookup"><span data-stu-id="b1237-113">Select **Block**.</span></span>

    :::image type="content" source="../../media/basic-mobility-security/bms-5-block-access.png" alt-text="&quot;基本移动和安全阻止访问&quot;复选框":::

5. <span data-ttu-id="b1237-115">选择 **"保存"。**</span><span class="sxs-lookup"><span data-stu-id="b1237-115">Select **Save**.</span></span>

<span data-ttu-id="b1237-116">若要了解基本移动性和安全性支持哪些设备，请参阅" [基本移动性和安全性的功能"。](capabilities.md)</span><span class="sxs-lookup"><span data-stu-id="b1237-116">To learn what devices Basic Mobility and Security supports, see [Capabilities of Basic Mobility and Security](capabilities.md).</span></span>