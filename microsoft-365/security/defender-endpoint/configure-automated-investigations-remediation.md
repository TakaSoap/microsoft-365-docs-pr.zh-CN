---
title: 配置自动调查和修正功能
description: 在 Microsoft Defender for Endpoint 中设置自动调查和修正功能。
keywords: 配置， 设置， 自动化， 调查， 检测， 警报， 修正， 响应
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
author: JoeDavies-MSFT
ms.author: josephd
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: how-to
ms.date: 01/27/2021
ms.reviewer: ramarom, evaldm, isco, mabraitm, chriggs
ms.openlocfilehash: 23d6c8c87a6cbcc7b8060440ba2c0cae6182767d
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274540"
---
# <a name="configure-automated-investigation-and-remediation-capabilities-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="a514e-104">在 Microsoft Defender for Endpoint 中配置自动调查和修正功能</span><span class="sxs-lookup"><span data-stu-id="a514e-104">Configure automated investigation and remediation capabilities in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="a514e-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="a514e-105">**Applies to:**</span></span>
- [<span data-ttu-id="a514e-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="a514e-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="a514e-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a514e-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="a514e-108">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="a514e-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="a514e-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="a514e-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="a514e-110">如果你的组织使用[Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/) (Defender for Endpoint) ，自动调查和修正功能可以节省你的安全操作团队时间和精力。 [](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/automated-investigations)</span><span class="sxs-lookup"><span data-stu-id="a514e-110">If your organization is using [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/) (Defender for Endpoint), [automated investigation and remediation capabilities](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/automated-investigations) can save your security operations team time and effort.</span></span> <span data-ttu-id="a514e-111">如本 [博客文章所述](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/enhance-your-soc-with-microsoft-defender-atp-automatic/ba-p/848946)，这些功能模拟安全分析师调查和修正威胁的理想步骤。</span><span class="sxs-lookup"><span data-stu-id="a514e-111">As outlined in [this blog post](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/enhance-your-soc-with-microsoft-defender-atp-automatic/ba-p/848946), these capabilities mimic the ideal steps that a security analyst takes to investigate and remediate threats.</span></span> <span data-ttu-id="a514e-112">[详细了解自动调查和修正](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/automated-investigations)。</span><span class="sxs-lookup"><span data-stu-id="a514e-112">[Learn more about automated investigation and remediation](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/automated-investigations).</span></span> 

<span data-ttu-id="a514e-113">若要配置自动调查和修正，</span><span class="sxs-lookup"><span data-stu-id="a514e-113">To configure automated investigation and remediation,</span></span>
1. <span data-ttu-id="a514e-114">[打开功能](#turn-on-automated-investigation-and-remediation);和</span><span class="sxs-lookup"><span data-stu-id="a514e-114">[Turn on the features](#turn-on-automated-investigation-and-remediation); and</span></span> 
2. <span data-ttu-id="a514e-115">[设置设备组](#set-up-device-groups)。</span><span class="sxs-lookup"><span data-stu-id="a514e-115">[Set up device groups](#set-up-device-groups).</span></span>

## <a name="turn-on-automated-investigation-and-remediation"></a><span data-ttu-id="a514e-116">启用自动调查和修正</span><span class="sxs-lookup"><span data-stu-id="a514e-116">Turn on automated investigation and remediation</span></span>

1. <span data-ttu-id="a514e-117">作为全局管理员或安全管理员，转到 Microsoft Defender 安全中心 () [https://securitycenter.windows.com](https://securitycenter.windows.com) 登录。</span><span class="sxs-lookup"><span data-stu-id="a514e-117">As a global administrator or security administrator, go to the Microsoft Defender Security Center ([https://securitycenter.windows.com](https://securitycenter.windows.com)) and sign in.</span></span>
2. <span data-ttu-id="a514e-118">在导航窗格中，选择"设置 **"。**</span><span class="sxs-lookup"><span data-stu-id="a514e-118">In the navigation pane, choose **Settings**.</span></span>
3. <span data-ttu-id="a514e-119">在"**常规"** 部分，选择"**高级功能"。**</span><span class="sxs-lookup"><span data-stu-id="a514e-119">In the **General** section, select **Advanced features**.</span></span>
4. <span data-ttu-id="a514e-120">同时启用 **自动调查和\*\*\*\*自动解决警报**。</span><span class="sxs-lookup"><span data-stu-id="a514e-120">Turn on both **Automated Investigation** and **Automatically resolve alerts**.</span></span>

## <a name="set-up-device-groups"></a><span data-ttu-id="a514e-121">设置设备组</span><span class="sxs-lookup"><span data-stu-id="a514e-121">Set up device groups</span></span>

1. <span data-ttu-id="a514e-122">在 Microsoft Defender 安全中心 () "设置"页面上的"权限"下， [https://securitycenter.windows.com](https://securitycenter.windows.com) 选择 **"设备组"。** </span><span class="sxs-lookup"><span data-stu-id="a514e-122">In the Microsoft Defender Security Center ([https://securitycenter.windows.com](https://securitycenter.windows.com)), on the **Settings** page, under **Permissions**, select **Device groups**.</span></span>
2. <span data-ttu-id="a514e-123">选择 **+ 添加设备组**。</span><span class="sxs-lookup"><span data-stu-id="a514e-123">Select **+ Add device group**.</span></span>
3. <span data-ttu-id="a514e-124">创建至少一个设备组，如下所示：</span><span class="sxs-lookup"><span data-stu-id="a514e-124">Create at least one device group, as follows:</span></span>
   - <span data-ttu-id="a514e-125">为设备组指定名称和说明。</span><span class="sxs-lookup"><span data-stu-id="a514e-125">Specify a name and description for the device group.</span></span>
   - <span data-ttu-id="a514e-126">在"**自动化级别"列表中**，选择一个级别，例如 **"完全 - 自动修正威胁"。**</span><span class="sxs-lookup"><span data-stu-id="a514e-126">In the **Automation level list**, select a level, such as **Full – remediate threats automatically**.</span></span> <span data-ttu-id="a514e-127">自动化级别确定是自动执行修正操作，还是仅在批准后执行修正操作。</span><span class="sxs-lookup"><span data-stu-id="a514e-127">The automation level determines whether remediation actions are taken automatically, or only upon approval.</span></span> <span data-ttu-id="a514e-128">若要了解更多信息，请参阅 [自动化调查和修正中的自动化级别](automation-levels.md)。</span><span class="sxs-lookup"><span data-stu-id="a514e-128">To learn more, see [Automation levels in automated investigation and remediation](automation-levels.md).</span></span>
   - <span data-ttu-id="a514e-129">在 **"成员** "部分，使用一个或多个条件来标识和包括设备。</span><span class="sxs-lookup"><span data-stu-id="a514e-129">In the **Members** section, use one or more conditions to identify and include devices.</span></span>
   - <span data-ttu-id="a514e-130">在 **"用户访问"** 选项卡上，选择应有权访问所创建设备组的 [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-manage-groups?context=azure/active-directory/users-groups-roles/context/ugr-context) 组。</span><span class="sxs-lookup"><span data-stu-id="a514e-130">On the **User access** tab, select the [Azure Active Directory groups](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-manage-groups?context=azure/active-directory/users-groups-roles/context/ugr-context) who should have access to the device group you're creating.</span></span>
4. <span data-ttu-id="a514e-131">完成 **设备** 组的设置后，选择"完成"。</span><span class="sxs-lookup"><span data-stu-id="a514e-131">Select **Done** when you're finished setting up your device group.</span></span>

## <a name="next-steps"></a><span data-ttu-id="a514e-132">后续步骤</span><span class="sxs-lookup"><span data-stu-id="a514e-132">Next steps</span></span>

- [<span data-ttu-id="a514e-133">访问操作中心以查看挂起和已完成的修正操作</span><span class="sxs-lookup"><span data-stu-id="a514e-133">Visit the Action Center to view pending and completed remediation actions</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/auto-investigation-action-center#the-action-center)
- [<span data-ttu-id="a514e-134">审阅和批准挂起的操作</span><span class="sxs-lookup"><span data-stu-id="a514e-134">Review and approve pending actions</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/manage-auto-investigation)

## <a name="see-also"></a><span data-ttu-id="a514e-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a514e-135">See also</span></span>

- [<span data-ttu-id="a514e-136">解决 Microsoft Defender for Endpoint 中的误报/漏报</span><span class="sxs-lookup"><span data-stu-id="a514e-136">Address false positives/negatives in Microsoft Defender for Endpoint</span></span>](defender-endpoint-false-positives-negatives.md)
