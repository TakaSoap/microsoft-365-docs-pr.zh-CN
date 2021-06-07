---
title: 配置Microsoft Defender 防病毒阻止超时期限
description: 你可以配置在Microsoft Defender 防病毒确定时阻止文件运行的时间。
keywords: Microsoft Defender 防病毒， 反恶意软件， 安全性， defender， 云， 超时， 阻止， 时间段， 秒
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.date: 06/04/2021
ms.openlocfilehash: dfb75b77119d9550931c3e476323bde67a3b148f
ms.sourcegitcommit: b09aee96a1e2266b33ba81dfe497f24c5300bb56
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/06/2021
ms.locfileid: "52789083"
---
# <a name="configure-the-cloud-block-timeout-period"></a><span data-ttu-id="fe45a-104">配置云块超时时间段</span><span class="sxs-lookup"><span data-stu-id="fe45a-104">Configure the cloud block timeout period</span></span>

<span data-ttu-id="fe45a-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="fe45a-105">**Applies to:**</span></span>

- [<span data-ttu-id="fe45a-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="fe45a-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="fe45a-107">当Microsoft Defender 防病毒发现可疑文件时，它会阻止该文件在查询 Microsoft Defender 防病毒[云服务时运行](cloud-protection-microsoft-defender-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="fe45a-107">When Microsoft Defender Antivirus finds a suspicious file, it can prevent the file from running while it queries the [Microsoft Defender Antivirus cloud service](cloud-protection-microsoft-defender-antivirus.md).</span></span>

<span data-ttu-id="fe45a-108">文件被阻止的默认 [时间段](configure-block-at-first-sight-microsoft-defender-antivirus.md) 为 10 秒。</span><span class="sxs-lookup"><span data-stu-id="fe45a-108">The default period that the file is [blocked](configure-block-at-first-sight-microsoft-defender-antivirus.md) is 10 seconds.</span></span> <span data-ttu-id="fe45a-109">如果您是安全管理员，您可以指定在允许文件运行之前等待的时间。</span><span class="sxs-lookup"><span data-stu-id="fe45a-109">If you're a security administrator, you can specify more time to wait before the file is allowed to run.</span></span> <span data-ttu-id="fe45a-110">延长云阻止超时期有助于确保有足够的时间从云云服务收到Microsoft Defender 防病毒决定。</span><span class="sxs-lookup"><span data-stu-id="fe45a-110">Extending the cloud block timeout period can help ensure there is enough time to receive a proper determination from the Microsoft Defender Antivirus cloud service.</span></span>

## <a name="prerequisites-to-use-the-extended-cloud-block-timeout"></a><span data-ttu-id="fe45a-111">使用扩展云阻止超时的先决条件</span><span class="sxs-lookup"><span data-stu-id="fe45a-111">Prerequisites to use the extended cloud block timeout</span></span>

<span data-ttu-id="fe45a-112">[必须先启用"首次](configure-block-at-first-sight-microsoft-defender-antivirus.md) 看到时阻止"及其先决条件，然后才能指定延长的超时期限。</span><span class="sxs-lookup"><span data-stu-id="fe45a-112">[Block at first sight](configure-block-at-first-sight-microsoft-defender-antivirus.md) and its prerequisites must be enabled before you can specify an extended timeout period.</span></span>

## <a name="specify-the-extended-timeout-period-using-microsoft-endpoint-manager"></a><span data-ttu-id="fe45a-113">使用方法指定延长的超时Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="fe45a-113">Specify the extended timeout period using Microsoft Endpoint Manager</span></span>

<span data-ttu-id="fe45a-114">可以使用终结点安全策略指定云阻止超时[Microsoft Endpoint Manager。](/mem/intune/protect/endpoint-security-policy)</span><span class="sxs-lookup"><span data-stu-id="fe45a-114">You can specify the cloud block timeout period with an [endpoint security policy in Microsoft Endpoint Manager](/mem/intune/protect/endpoint-security-policy).</span></span>

1. <span data-ttu-id="fe45a-115">转到管理Endpoint Manager中心 [https://endpoint.microsoft.com/](https://endpoint.microsoft.com/) () 登录。</span><span class="sxs-lookup"><span data-stu-id="fe45a-115">Go to the Endpoint Manager admin center ([https://endpoint.microsoft.com/](https://endpoint.microsoft.com/)) and sign in.</span></span>

2. <span data-ttu-id="fe45a-116">选择 **"终结点安全性"，** 然后在"管理 **"下**，选择 **"防病毒"。**</span><span class="sxs-lookup"><span data-stu-id="fe45a-116">Select **Endpoint security**, and then under **Manage**, choose **Antivirus**.</span></span>

3. <span data-ttu-id="fe45a-117">选择 (或) 防病毒策略。</span><span class="sxs-lookup"><span data-stu-id="fe45a-117">Select (or create) an antivirus policy.</span></span>

4. <span data-ttu-id="fe45a-118">在"**配置设置"** 部分，展开"**云保护"。**</span><span class="sxs-lookup"><span data-stu-id="fe45a-118">In the **Configuration settings** section, expand **Cloud protection**.</span></span> <span data-ttu-id="fe45a-119">然后，在 **"Defender 云扩展超时（** 秒）"框中，指定从 1 秒到 50 秒的更多时间（以秒表示）。</span><span class="sxs-lookup"><span data-stu-id="fe45a-119">Then, in the **Defender Cloud Extended Timeout In Seconds** box, specify the more time, in seconds, from 1 second to 50 seconds.</span></span> <span data-ttu-id="fe45a-120">您指定的任何时间将添加到默认值 10 秒。</span><span class="sxs-lookup"><span data-stu-id="fe45a-120">Whatever you specify is added to the default 10 seconds.</span></span>

5. <span data-ttu-id="fe45a-121"> (此步骤是可选的) 对防病毒策略进行任何其他更改。</span><span class="sxs-lookup"><span data-stu-id="fe45a-121">(This step is optional) Make any other changes to your antivirus policy.</span></span> <span data-ttu-id="fe45a-122"> (需要帮助？</span><span class="sxs-lookup"><span data-stu-id="fe45a-122">(Need help?</span></span> <span data-ttu-id="fe45a-123">请参阅[设置 .Microsoft Defender 防病毒 中的 Microsoft Intune](/mem/intune/protect/antivirus-microsoft-defender-settings-windows)策略) </span><span class="sxs-lookup"><span data-stu-id="fe45a-123">See [Settings for Microsoft Defender Antivirus policy in Microsoft Intune](/mem/intune/protect/antivirus-microsoft-defender-settings-windows).)</span></span>

6. <span data-ttu-id="fe45a-124">选择 **"下** 一步"，然后完成策略配置。</span><span class="sxs-lookup"><span data-stu-id="fe45a-124">Choose **Next**, and finish configuring your policy.</span></span>

## <a name="specify-the-extended-timeout-period-using-group-policy"></a><span data-ttu-id="fe45a-125">使用组策略指定延长的超时时段</span><span class="sxs-lookup"><span data-stu-id="fe45a-125">Specify the extended timeout period using Group Policy</span></span>

<span data-ttu-id="fe45a-126">可以使用组策略指定云检查的延长超时时间。</span><span class="sxs-lookup"><span data-stu-id="fe45a-126">You can use Group Policy to specify an extended timeout for cloud checks.</span></span>

1. <span data-ttu-id="fe45a-127">在组策略管理计算机上，打开 [组策略管理控制台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))</span><span class="sxs-lookup"><span data-stu-id="fe45a-127">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))</span></span>

2. <span data-ttu-id="fe45a-128">右键单击要配置的组策略对象， **然后选择编辑**。</span><span class="sxs-lookup"><span data-stu-id="fe45a-128">Right-click the Group Policy Object you want to configure and then select **Edit**.</span></span>

3. <span data-ttu-id="fe45a-129">在组 **策略管理编辑器中**，转到"**计算机配置**"，然后选择"**管理模板"。**</span><span class="sxs-lookup"><span data-stu-id="fe45a-129">In the **Group Policy Management Editor**, go to **Computer configuration**, and then select **Administrative templates**.</span></span>

3. <span data-ttu-id="fe45a-130">展开树以Windows   >    >  **MpEngine** Microsoft Defender 防病毒组件。</span><span class="sxs-lookup"><span data-stu-id="fe45a-130">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **MpEngine**.</span></span>

4. <span data-ttu-id="fe45a-131">双击配置 **扩展云检查并确保** 该选项已启用。</span><span class="sxs-lookup"><span data-stu-id="fe45a-131">Double-click **Configure extended cloud check** and ensure the option is enabled.</span></span> 

   <span data-ttu-id="fe45a-132">指定额外时间，以在等待云确定时阻止文件运行。</span><span class="sxs-lookup"><span data-stu-id="fe45a-132">Specify the extra amount of time to prevent the file from running while waiting for a cloud determination.</span></span> <span data-ttu-id="fe45a-133">指定从 1 秒到 50 秒的额外时间（秒）。</span><span class="sxs-lookup"><span data-stu-id="fe45a-133">Specify the extra time, in seconds, from 1 second to 50 seconds.</span></span> <span data-ttu-id="fe45a-134">您指定的任何时间将添加到默认值 10 秒。</span><span class="sxs-lookup"><span data-stu-id="fe45a-134">Whatever you specify is added to the default 10 seconds.</span></span>

5. <span data-ttu-id="fe45a-135">选择“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="fe45a-135">Select **OK**.</span></span>

 