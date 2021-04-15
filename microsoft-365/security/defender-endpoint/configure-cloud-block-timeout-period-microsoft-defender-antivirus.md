---
title: 配置 Microsoft Defender 防病毒云阻止超时期限
description: 你可以配置 Microsoft Defender 防病毒在等待云确定时阻止文件运行的时间。
keywords: Microsoft Defender 防病毒， 反恶意软件， 安全性， defender， 云， 超时， 阻止， 时间段， 秒
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 372d679f45d6f87392b612f757e6bdf1c6c6b9ad
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/14/2021
ms.locfileid: "51765799"
---
# <a name="configure-the-cloud-block-timeout-period"></a><span data-ttu-id="dbba6-104">配置云块超时时间段</span><span class="sxs-lookup"><span data-stu-id="dbba6-104">Configure the cloud block timeout period</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="dbba6-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="dbba6-105">**Applies to:**</span></span>

- [<span data-ttu-id="dbba6-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="dbba6-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="dbba6-107">当 Microsoft Defender 防病毒发现可疑文件时，它会阻止该文件在查询 [Microsoft Defender 防病毒云服务时运行](cloud-protection-microsoft-defender-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="dbba6-107">When Microsoft Defender Antivirus finds a suspicious file, it can prevent the file from running while it queries the [Microsoft Defender Antivirus cloud service](cloud-protection-microsoft-defender-antivirus.md).</span></span>

<span data-ttu-id="dbba6-108">文件将被阻止 [的默认时间段为](configure-block-at-first-sight-microsoft-defender-antivirus.md) 10 秒。</span><span class="sxs-lookup"><span data-stu-id="dbba6-108">The default period that the file will be [blocked](configure-block-at-first-sight-microsoft-defender-antivirus.md) is 10 seconds.</span></span> <span data-ttu-id="dbba6-109">您可以指定在允许文件运行之前要等待的一段额外时间。</span><span class="sxs-lookup"><span data-stu-id="dbba6-109">You can specify an additional period of time to wait before the file is allowed to run.</span></span> <span data-ttu-id="dbba6-110">这有助于确保有足够的时间从 Microsoft Defender 防病毒云服务收到正确决定。</span><span class="sxs-lookup"><span data-stu-id="dbba6-110">This can help ensure there is enough time to receive a proper determination from the Microsoft Defender Antivirus cloud service.</span></span>

## <a name="prerequisites-to-use-the-extended-cloud-block-timeout"></a><span data-ttu-id="dbba6-111">使用扩展云阻止超时的先决条件</span><span class="sxs-lookup"><span data-stu-id="dbba6-111">Prerequisites to use the extended cloud block timeout</span></span>

<span data-ttu-id="dbba6-112">[必须先启用"首次](configure-block-at-first-sight-microsoft-defender-antivirus.md) 看到时阻止"及其先决条件，然后才能指定延长的超时期限。</span><span class="sxs-lookup"><span data-stu-id="dbba6-112">[Block at first sight](configure-block-at-first-sight-microsoft-defender-antivirus.md) and its prerequisites must be enabled before you can specify an extended timeout period.</span></span>

## <a name="specify-the-extended-timeout-period"></a><span data-ttu-id="dbba6-113">指定延长的超时期限</span><span class="sxs-lookup"><span data-stu-id="dbba6-113">Specify the extended timeout period</span></span>

<span data-ttu-id="dbba6-114">可以使用组策略指定云检查的延长超时时间。</span><span class="sxs-lookup"><span data-stu-id="dbba6-114">You can use Group Policy to specify an extended timeout for cloud checks.</span></span>

1. <span data-ttu-id="dbba6-115">在组策略管理计算机上，打开组 [策略管理控制台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))，右键单击要配置的组策略对象，**然后单击编辑。**</span><span class="sxs-lookup"><span data-stu-id="dbba6-115">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="dbba6-116">在组 **策略管理编辑器中** ，转到计算机 **配置，** 然后单击 **管理模板**。</span><span class="sxs-lookup"><span data-stu-id="dbba6-116">In the **Group Policy Management Editor** go to **Computer configuration** and click **Administrative templates**.</span></span>

3. <span data-ttu-id="dbba6-117">将树展开到 **Windows 组件> Microsoft Defender 防病毒> MpEngine**</span><span class="sxs-lookup"><span data-stu-id="dbba6-117">Expand the tree to **Windows components > Microsoft Defender Antivirus > MpEngine**</span></span>

4. <span data-ttu-id="dbba6-118">双击配置 **扩展云检查并确保** 该选项已启用。</span><span class="sxs-lookup"><span data-stu-id="dbba6-118">Double-click **Configure extended cloud check** and ensure the option is enabled.</span></span> <span data-ttu-id="dbba6-119">指定在等待云确定时阻止文件运行的额外时间。</span><span class="sxs-lookup"><span data-stu-id="dbba6-119">Specify the additional amount of time to prevent the file from running while waiting for a cloud determination.</span></span> <span data-ttu-id="dbba6-120">可以指定 1 秒到 50 秒的额外时间（以秒表示）。</span><span class="sxs-lookup"><span data-stu-id="dbba6-120">You can specify the additional time, in seconds, from 1 second to 50 seconds.</span></span> <span data-ttu-id="dbba6-121">此时将添加到默认值 10 秒。</span><span class="sxs-lookup"><span data-stu-id="dbba6-121">This time will be added to the default 10 seconds.</span></span>

5. <span data-ttu-id="dbba6-122">单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="dbba6-122">Click **OK**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="dbba6-123">相关主题</span><span class="sxs-lookup"><span data-stu-id="dbba6-123">Related topics</span></span>

- [<span data-ttu-id="dbba6-124">Windows 10 中的 Microsoft Defender 防病毒</span><span class="sxs-lookup"><span data-stu-id="dbba6-124">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
- [<span data-ttu-id="dbba6-125">通过云保护使用下一代防病毒技术</span><span class="sxs-lookup"><span data-stu-id="dbba6-125">Use next-generation antivirus technologies through cloud-delivered protection</span></span>](cloud-protection-microsoft-defender-antivirus.md)
- [<span data-ttu-id="dbba6-126">配置首次看到时阻止</span><span class="sxs-lookup"><span data-stu-id="dbba6-126">Configure block at first sight</span></span>](configure-block-at-first-sight-microsoft-defender-antivirus.md)
- [<span data-ttu-id="dbba6-127">启用云保护</span><span class="sxs-lookup"><span data-stu-id="dbba6-127">Enable cloud-delivered protection</span></span>](enable-cloud-protection-microsoft-defender-antivirus.md)