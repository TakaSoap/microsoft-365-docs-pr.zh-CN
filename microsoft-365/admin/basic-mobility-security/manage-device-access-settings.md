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
ms.openlocfilehash: 24eeb1dfccef3d30e577b15ecb9d2fda4d902cdc
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/30/2021
ms.locfileid: "53228155"
---
# <a name="manage-device-access-settings-in-basic-mobility-and-security"></a><span data-ttu-id="afcd2-103">在基本移动性和安全性中管理设备访问设置</span><span class="sxs-lookup"><span data-stu-id="afcd2-103">Manage device access settings in Basic Mobility and Security</span></span>

<span data-ttu-id="afcd2-104">如果使用的是基本移动性和安全性，则有些设备可能无法使用基本移动性和安全性进行管理。</span><span class="sxs-lookup"><span data-stu-id="afcd2-104">If you're using Basic Mobility and Security, there might be devices that you can't manage with Basic Mobility and Security.</span></span> <span data-ttu-id="afcd2-105">如果是这样，应Exchange ActiveSync基本移动性Microsoft 365安全性不支持的移动设备访问电子邮件。</span><span class="sxs-lookup"><span data-stu-id="afcd2-105">If so, you should block Exchange ActiveSync app access to Microsoft 365 email for mobile devices that aren't supported by Basic Mobility and Security.</span></span> <span data-ttu-id="afcd2-106">这有助于跨更多设备保护组织信息。</span><span class="sxs-lookup"><span data-stu-id="afcd2-106">This helps secure your organization information across more devices.</span></span>

<span data-ttu-id="afcd2-107">使用以下步骤：</span><span class="sxs-lookup"><span data-stu-id="afcd2-107">Use these steps:</span></span>

1. <span data-ttu-id="afcd2-108">Sign in to Microsoft 365 with your global admin account.</span><span class="sxs-lookup"><span data-stu-id="afcd2-108">Sign in to  Microsoft 365 with your global admin account.</span></span>

2. <span data-ttu-id="afcd2-109">在浏览器中，键入  [https://protection.office.com](https://protection.office.com/) ：。</span><span class="sxs-lookup"><span data-stu-id="afcd2-109">In your browser, type: [https://protection.office.com](https://protection.office.com/).</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="afcd2-110">如果这是您第一次使用基本移动性和安全性进行Microsoft 365 商业标准版激活它[：Activate Basic Security and Mobility](https://admin.microsoft.com/EAdmin/Device/IntuneInventory.aspx)。</span><span class="sxs-lookup"><span data-stu-id="afcd2-110">If this is the first time you're using Basic Mobility and Security for Microsoft 365 Business Standard, activate it here: [Activate Basic Security and Mobility](https://admin.microsoft.com/EAdmin/Device/IntuneInventory.aspx).</span></span> <span data-ttu-id="afcd2-111">激活后，使用安全与合规Office 365[管理&设备](https://protection.office.com/)。</span><span class="sxs-lookup"><span data-stu-id="afcd2-111">After you've activated it, manage your devices with [Office 365 Security & Compliance](https://protection.office.com/).</span></span>

3. <span data-ttu-id="afcd2-112">转到"数据丢失防护> **设备管理**   >  **设备策略"，** 然后选择" **管理组织范围内的设备访问设置"。**</span><span class="sxs-lookup"><span data-stu-id="afcd2-112">Go to Data loss prevention > **Device management** > **Device policies**, and select **Manage organization-wide device access settings**.</span></span>

4. <span data-ttu-id="afcd2-113">选择" **阻止"。**</span><span class="sxs-lookup"><span data-stu-id="afcd2-113">Select **Block**.</span></span>

    :::image type="content" source="../../media/basic-mobility-security/bms-5-block-access.png" alt-text="&quot;基本移动性和安全性阻止访问&quot;复选框":::

5. <span data-ttu-id="afcd2-115">选择" **保存"。**</span><span class="sxs-lookup"><span data-stu-id="afcd2-115">Select **Save**.</span></span>

<span data-ttu-id="afcd2-116">若要了解基本移动性和安全性支持哪些设备，请参阅 [Capabilities of Basic Mobility and Security。](capabilities.md)</span><span class="sxs-lookup"><span data-stu-id="afcd2-116">To learn what devices Basic Mobility and Security supports, see [Capabilities of Basic Mobility and Security](capabilities.md).</span></span>
