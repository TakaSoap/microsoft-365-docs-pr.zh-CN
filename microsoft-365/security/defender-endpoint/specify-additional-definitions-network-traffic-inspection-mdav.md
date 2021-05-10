---
title: 为网络通信检查指定其他定义集Microsoft Defender 防病毒
description: 为网络通信检查指定其他定义集Microsoft Defender 防病毒。
keywords: Microsoft Defender 防病毒， 反恶意软件， 安全性， Defender， 网络流量检查
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
ms.openlocfilehash: 82568df0a6ad2225fd31b4c0fa4a654710f1e98b
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2021
ms.locfileid: "52300116"
---
# <a name="specify-additional-definition-sets-for-network-traffic-inspection"></a><span data-ttu-id="bdf93-104">为网络流量检查指定其他定义集</span><span class="sxs-lookup"><span data-stu-id="bdf93-104">Specify additional definition sets for network traffic inspection</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="bdf93-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="bdf93-105">**Applies to:**</span></span>

- [<span data-ttu-id="bdf93-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="bdf93-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="bdf93-107">可以使用组策略为网络流量检查指定其他定义集。</span><span class="sxs-lookup"><span data-stu-id="bdf93-107">You can specify additional definition sets for network traffic inspection using Group Policy.</span></span>

## <a name="use-group-policy-to-specify-additional-definition-sets-for-network-traffic-inspection"></a><span data-ttu-id="bdf93-108">使用组策略指定用于网络流量检查的其他定义集</span><span class="sxs-lookup"><span data-stu-id="bdf93-108">Use Group Policy to specify additional definition sets for network traffic inspection</span></span>

1. <span data-ttu-id="bdf93-109">在组策略管理终结点上，打开组 [策略管理控制台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))。</span><span class="sxs-lookup"><span data-stu-id="bdf93-109">On your Group Policy management endpoint, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).</span></span>

2. <span data-ttu-id="bdf93-110">转到网络 **Windows系统**  >  **Microsoft Defender 防病毒**  >  **组件"。**</span><span class="sxs-lookup"><span data-stu-id="bdf93-110">Go to **Windows Components** > **Microsoft Defender Antivirus** > **Network Inspection System**.</span></span> 

3. <span data-ttu-id="bdf93-111">选择 **指定网络流量检查的其他定义集**。</span><span class="sxs-lookup"><span data-stu-id="bdf93-111">Select **Specify additional definition sets for network traffic inspection**.</span></span> <span data-ttu-id="bdf93-112">默认情况下，此策略设置为"**未配置"。**</span><span class="sxs-lookup"><span data-stu-id="bdf93-112">By default, this policy is set to **Not configured**.</span></span> 

4. <span data-ttu-id="bdf93-113">若要编辑策略，请选择 **"编辑策略设置"** 链接。</span><span class="sxs-lookup"><span data-stu-id="bdf93-113">To edit the policy, select the **edit policy setting** link.</span></span>

5. <span data-ttu-id="bdf93-114">选择 **"已启用**"，然后在"选项 **"部分**，选择"显示 **..."。**</span><span class="sxs-lookup"><span data-stu-id="bdf93-114">Select **Enabled**, and then in the **Options** section, select **Show...**.</span></span>

6. <span data-ttu-id="bdf93-115">将条目添加到列表中，然后选择"确定 **"。**</span><span class="sxs-lookup"><span data-stu-id="bdf93-115">Add entries to the list, and then select **OK**.</span></span> 

   <span data-ttu-id="bdf93-116">每个条目都必须作为名称-值对列出，其中名称是定义集 GUID 的字符串表示形式。</span><span class="sxs-lookup"><span data-stu-id="bdf93-116">Each entry must be listed as a name-value pair, where the name is a string representation of a definition set GUID.</span></span> <span data-ttu-id="bdf93-117">例如，定义集 GUID 以启用测试安全智能定义为 `{b54b6ac9-a737-498e-9120-6616ad3bf590}` ：。</span><span class="sxs-lookup"><span data-stu-id="bdf93-117">As an example, the definition set GUID to enable test security intelligence is defined as: `{b54b6ac9-a737-498e-9120-6616ad3bf590}`.</span></span> <span data-ttu-id="bdf93-118">该值未使用，因此建议将 此值设置为 `0` 。</span><span class="sxs-lookup"><span data-stu-id="bdf93-118">The value is not used, so we recommend setting it to `0`.</span></span> 

7. <span data-ttu-id="bdf93-119">选择 **"确定**"，然后部署更新的组策略对象。</span><span class="sxs-lookup"><span data-stu-id="bdf93-119">Select **OK**, and then deploy your updated Group Policy Object.</span></span> <span data-ttu-id="bdf93-120">请参阅 [组策略管理控制台](/windows/win32/srvnodes/group-policy)。</span><span class="sxs-lookup"><span data-stu-id="bdf93-120">See [Group Policy Management Console](/windows/win32/srvnodes/group-policy).</span></span>

> [!TIP]
> <span data-ttu-id="bdf93-121">是否在本地使用组策略对象？</span><span class="sxs-lookup"><span data-stu-id="bdf93-121">Are you using Group Policy Objects on premises?</span></span> <span data-ttu-id="bdf93-122">查看它们在云中如何转换。</span><span class="sxs-lookup"><span data-stu-id="bdf93-122">See how they translate in the cloud.</span></span> <span data-ttu-id="bdf93-123">[在预览版中，使用组策略分析Microsoft Endpoint Manager本地组策略对象](/mem/intune/configuration/group-policy-analytics)。</span><span class="sxs-lookup"><span data-stu-id="bdf93-123">[Analyze your on-premises group policy objects using Group Policy analytics in Microsoft Endpoint Manager - Preview](/mem/intune/configuration/group-policy-analytics).</span></span> 
  
## <a name="related-articles"></a><span data-ttu-id="bdf93-124">相关文章</span><span class="sxs-lookup"><span data-stu-id="bdf93-124">Related articles</span></span>

- [<span data-ttu-id="bdf93-125">Windows 10 中的 Microsoft Defender 防病毒</span><span class="sxs-lookup"><span data-stu-id="bdf93-125">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
 
- [<span data-ttu-id="bdf93-126">启用云保护</span><span class="sxs-lookup"><span data-stu-id="bdf93-126">Enable cloud-delivered protection</span></span>](enable-cloud-protection-microsoft-defender-antivirus.md)

- [<span data-ttu-id="bdf93-127">如何创建和部署反恶意软件策略：云保护服务</span><span class="sxs-lookup"><span data-stu-id="bdf93-127">How to create and deploy antimalware policies: Cloud-protection service</span></span>](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service)