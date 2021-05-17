---
title: 打开协议识别Microsoft Defender 防病毒
description: 打开协议识别以识别Microsoft Defender 防病毒。
keywords: Microsoft Defender 防病毒， 反恶意软件， 安全性， defender， 协议识别
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.date: 05/07/2021
ms.reviewer: ''
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 890303a15618a0318db0421c9c80f270583e19bf
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2021
ms.locfileid: "52296464"
---
# <a name="turn-on-protocol-recognition"></a><span data-ttu-id="e836a-104">打开协议识别</span><span class="sxs-lookup"><span data-stu-id="e836a-104">Turn on protocol recognition</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="e836a-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="e836a-105">**Applies to:**</span></span>

- [<span data-ttu-id="e836a-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="e836a-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="e836a-107">此策略设置允许你配置协议识别，以抵御已知漏洞攻击的网络保护。</span><span class="sxs-lookup"><span data-stu-id="e836a-107">This policy setting allows you to configure protocol recognition for network protection against exploits of known vulnerabilities.</span></span> <span data-ttu-id="e836a-108">如果启用或不配置此设置，将启用协议识别。</span><span class="sxs-lookup"><span data-stu-id="e836a-108">If you enable or do not configure this setting, protocol recognition will be enabled.</span></span> <span data-ttu-id="e836a-109">如果禁用此设置，将禁用协议识别。</span><span class="sxs-lookup"><span data-stu-id="e836a-109">If you disable this setting, protocol recognition will be disabled.</span></span>

## <a name="use-group-policy-to-configure-protocol-recognition"></a><span data-ttu-id="e836a-110">使用组策略配置协议识别</span><span class="sxs-lookup"><span data-stu-id="e836a-110">Use Group Policy to configure protocol recognition</span></span>

1. <span data-ttu-id="e836a-111">在组策略管理终结点上，打开组 [策略管理控制台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))。</span><span class="sxs-lookup"><span data-stu-id="e836a-111">On your Group Policy management endpoint, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).</span></span>

2. <span data-ttu-id="e836a-112">转到计算机 **配置**  >  **管理模板**  >  **Windows组件**  >  **Microsoft Defender 防病毒**  >  **网络检查系统 。**</span><span class="sxs-lookup"><span data-stu-id="e836a-112">Go to **Computer Configuration** > **Administrative Templates** > **Windows Components** > **Microsoft Defender Antivirus** > **Network Inspection System**.</span></span> 

3. <span data-ttu-id="e836a-113">选择 **协议识别**。</span><span class="sxs-lookup"><span data-stu-id="e836a-113">Select **protocol recognition**.</span></span> <span data-ttu-id="e836a-114">默认情况下，启用此策略。</span><span class="sxs-lookup"><span data-stu-id="e836a-114">By default, this policy is enabled.</span></span> <span data-ttu-id="e836a-115">如果设置为 **"未配置"，** 则启用定义停用。</span><span class="sxs-lookup"><span data-stu-id="e836a-115">If set **Not configured**, definition retirement is enabled.</span></span> 

4. <span data-ttu-id="e836a-116">若要编辑策略，请选择 **"编辑策略设置"** 链接。</span><span class="sxs-lookup"><span data-stu-id="e836a-116">To edit the policy, select the **edit policy setting** link.</span></span>

5. <span data-ttu-id="e836a-117">选择 **"已启用**"，然后选择"确定 **"。**</span><span class="sxs-lookup"><span data-stu-id="e836a-117">Select **Enabled**, and then select **OK**.</span></span>

6. <span data-ttu-id="e836a-118">部署更新的组策略对象。</span><span class="sxs-lookup"><span data-stu-id="e836a-118">Deploy your updated Group Policy Object.</span></span> <span data-ttu-id="e836a-119">请参阅 [组策略管理控制台](/windows/win32/srvnodes/group-policy)。</span><span class="sxs-lookup"><span data-stu-id="e836a-119">See [Group Policy Management Console](/windows/win32/srvnodes/group-policy).</span></span>

> [!TIP]
> <span data-ttu-id="e836a-120">是否在本地使用组策略对象？</span><span class="sxs-lookup"><span data-stu-id="e836a-120">Are you using Group Policy Objects on premises?</span></span> <span data-ttu-id="e836a-121">查看它们在云中如何转换。</span><span class="sxs-lookup"><span data-stu-id="e836a-121">See how they translate in the cloud.</span></span> <span data-ttu-id="e836a-122">[在预览版中，使用组策略分析Microsoft Endpoint Manager本地组策略对象](/mem/intune/configuration/group-policy-analytics)。</span><span class="sxs-lookup"><span data-stu-id="e836a-122">[Analyze your on-premises group policy objects using Group Policy analytics in Microsoft Endpoint Manager - Preview](/mem/intune/configuration/group-policy-analytics).</span></span> 
  
## <a name="related-articles"></a><span data-ttu-id="e836a-123">相关文章</span><span class="sxs-lookup"><span data-stu-id="e836a-123">Related articles</span></span>

- [<span data-ttu-id="e836a-124">Windows 10 中的 Microsoft Defender 防病毒</span><span class="sxs-lookup"><span data-stu-id="e836a-124">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
 
- [<span data-ttu-id="e836a-125">启用云保护</span><span class="sxs-lookup"><span data-stu-id="e836a-125">Enable cloud-delivered protection</span></span>](enable-cloud-protection-microsoft-defender-antivirus.md)

- [<span data-ttu-id="e836a-126">如何创建和部署反恶意软件策略：云保护服务</span><span class="sxs-lookup"><span data-stu-id="e836a-126">How to create and deploy antimalware policies: Cloud-protection service</span></span>](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service)