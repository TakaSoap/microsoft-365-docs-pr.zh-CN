---
title: 使用Microsoft Defender 防病毒配置Microsoft Endpoint Manager
description: 使用Microsoft Endpoint Manager和Microsoft Intune配置 Microsoft Defender AV 和 Endpoint Protection
keywords: scep， intune， 终结点保护， 配置
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 05/24/2021
ms.reviewer: phuijbr, oogunrinde
manager: dansimp
ms.technology: mde
audience: ITPro
ms.topic: how-to
ms.openlocfilehash: ab77f3ab5ac9385d1ce049061730d2192e3bcb0c
ms.sourcegitcommit: a6fb731fdf726d7d9fe4232cf69510013f2b54ce
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2021
ms.locfileid: "52683747"
---
# <a name="use-microsoft-endpoint-manager-to-configure-and-manage-microsoft-defender-antivirus"></a><span data-ttu-id="adee9-104">使用Microsoft Endpoint Manager配置和管理Microsoft Defender 防病毒</span><span class="sxs-lookup"><span data-stu-id="adee9-104">Use Microsoft Endpoint Manager to configure and manage Microsoft Defender Antivirus</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="adee9-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="adee9-105">**Applies to:**</span></span>

- [<span data-ttu-id="adee9-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="adee9-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="adee9-107">可以使用此[Microsoft Endpoint Manager](/mem/endpoint-manager-overview)配置Microsoft Defender 防病毒扫描。</span><span class="sxs-lookup"><span data-stu-id="adee9-107">You can use [Microsoft Endpoint Manager](/mem/endpoint-manager-overview) to configure Microsoft Defender Antivirus scans.</span></span> <span data-ttu-id="adee9-108">[Microsoft Intune](/mem/intune/fundamentals/what-is-intune)[和 Configuration Manager](/mem/configmgr/core/understand/introduction)现在属于Endpoint Manager。</span><span class="sxs-lookup"><span data-stu-id="adee9-108">[Microsoft Intune](/mem/intune/fundamentals/what-is-intune) and [Configuration Manager](/mem/configmgr/core/understand/introduction) are now part of Endpoint Manager.</span></span>  

## <a name="configure-microsoft-defender-antivirus-scans-in-endpoint-manager"></a><span data-ttu-id="adee9-109">在Microsoft Defender 防病毒中配置Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="adee9-109">Configure Microsoft Defender Antivirus scans in Endpoint Manager</span></span>

1. <span data-ttu-id="adee9-110">转到管理Microsoft Endpoint Manager中心 [https://endpoint.microsoft.com](https://endpoint.microsoft.com) () ，然后登录。</span><span class="sxs-lookup"><span data-stu-id="adee9-110">Go to the Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)), and sign in.</span></span>

2. <span data-ttu-id="adee9-111">导航到 **终结点安全性**。</span><span class="sxs-lookup"><span data-stu-id="adee9-111">Navigate to **Endpoint Security**.</span></span>

3. <span data-ttu-id="adee9-112">在 **"管理"** 下，**选择"防病毒"。**</span><span class="sxs-lookup"><span data-stu-id="adee9-112">Under **Manage**, choose **Antivirus**.</span></span>

4. <span data-ttu-id="adee9-113">选择你的Microsoft Defender 防病毒策略。</span><span class="sxs-lookup"><span data-stu-id="adee9-113">Select your Microsoft Defender Antivirus policy.</span></span> 

5. <span data-ttu-id="adee9-114">在“**管理**”下，选择“**属性**”。</span><span class="sxs-lookup"><span data-stu-id="adee9-114">Under **Manage**, choose **Properties**.</span></span>

6. <span data-ttu-id="adee9-115">选择“**配置设置**”旁的“**编辑**”。</span><span class="sxs-lookup"><span data-stu-id="adee9-115">Next to **Configuration settings**, choose **Edit**.</span></span>

7. <span data-ttu-id="adee9-116">展开扫描 **部分** ，然后查看或编辑扫描设置。</span><span class="sxs-lookup"><span data-stu-id="adee9-116">Expand the **Scan** section, and review or edit your scanning settings.</span></span>

8. <span data-ttu-id="adee9-117">选择 **"审阅 + 保存"**</span><span class="sxs-lookup"><span data-stu-id="adee9-117">Choose **Review + save**</span></span>


> [!TIP]
> <span data-ttu-id="adee9-118">需要帮助?</span><span class="sxs-lookup"><span data-stu-id="adee9-118">Need help?</span></span> <span data-ttu-id="adee9-119">请参阅[管理终结点安全Microsoft Intune。](/mem/intune/protect/endpoint-security)</span><span class="sxs-lookup"><span data-stu-id="adee9-119">See [Manage endpoint security in Microsoft Intune](/mem/intune/protect/endpoint-security).</span></span>


## <a name="related-articles"></a><span data-ttu-id="adee9-120">相关文章</span><span class="sxs-lookup"><span data-stu-id="adee9-120">Related articles</span></span>

- [<span data-ttu-id="adee9-121">有关管理和配置工具的参考文章</span><span class="sxs-lookup"><span data-stu-id="adee9-121">Reference articles for management and configuration tools</span></span>](configuration-management-reference-microsoft-defender-antivirus.md)
- [<span data-ttu-id="adee9-122">Windows 10 中的 Microsoft Defender 防病毒</span><span class="sxs-lookup"><span data-stu-id="adee9-122">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)