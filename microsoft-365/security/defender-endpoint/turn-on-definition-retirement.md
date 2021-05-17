---
title: 打开定义停用功能Microsoft Defender 防病毒
description: 打开定义停用以用于Microsoft Defender 防病毒。
keywords: Microsoft Defender 防病毒， 反恶意软件， 安全性， defender， 定义停用
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
ms.openlocfilehash: 66b2e882a0f6de21e27dabb3a4bfe2fe113bcb32
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2021
ms.locfileid: "52296465"
---
# <a name="turn-on-definition-retirement"></a><span data-ttu-id="e7b61-104">启用定义停用</span><span class="sxs-lookup"><span data-stu-id="e7b61-104">Turn on definition retirement</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="e7b61-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="e7b61-105">**Applies to:**</span></span>

- [<span data-ttu-id="e7b61-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="e7b61-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="e7b61-107">可以使用组策略配置定义停用。</span><span class="sxs-lookup"><span data-stu-id="e7b61-107">You can configure definition retirement using Group Policy.</span></span> <span data-ttu-id="e7b61-108">定义停用检查计算机是否具有必要的安全更新，以保护计算机免受特定漏洞的影响。</span><span class="sxs-lookup"><span data-stu-id="e7b61-108">Definition retirement checks to see if a computer has the required security updates necessary to protect it against a particular vulnerability.</span></span> <span data-ttu-id="e7b61-109">如果系统不易受定义检测到的漏洞攻击，则该定义将"停用"。</span><span class="sxs-lookup"><span data-stu-id="e7b61-109">If the system is not vulnerable to the exploit detected by a definition, then that definition is "retired".</span></span> <span data-ttu-id="e7b61-110">如果给定协议的所有安全智能都停用，则不再分析该协议。</span><span class="sxs-lookup"><span data-stu-id="e7b61-110">If all security intelligence for a given protocol are retired then that protocol is no longer parsed.</span></span> <span data-ttu-id="e7b61-111">启用此功能有助于提高性能。</span><span class="sxs-lookup"><span data-stu-id="e7b61-111">Enabling this feature helps to improve performance.</span></span> <span data-ttu-id="e7b61-112">在具有所有最新安全更新的计算机上，网络保护不会影响网络性能。</span><span class="sxs-lookup"><span data-stu-id="e7b61-112">On a computer that is up-to-date with all the latest security updates, network protection will have no impact on network performance.</span></span>

## <a name="use-group-policy-to-configure-definition-retirement"></a><span data-ttu-id="e7b61-113">使用组策略配置定义停用</span><span class="sxs-lookup"><span data-stu-id="e7b61-113">Use Group Policy to configure definition retirement</span></span>

1. <span data-ttu-id="e7b61-114">在组策略管理终结点上，打开组 [策略管理控制台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))。</span><span class="sxs-lookup"><span data-stu-id="e7b61-114">On your Group Policy management endpoint, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).</span></span>

2. <span data-ttu-id="e7b61-115">转到计算机 **配置**  >  **管理模板**  >  **Windows组件**  >  **Microsoft Defender 防病毒**  >  **网络检查系统 。**</span><span class="sxs-lookup"><span data-stu-id="e7b61-115">Go to **Computer Configuration** > **Administrative Templates** > **Windows Components** > **Microsoft Defender Antivirus** > **Network Inspection System**.</span></span> 

3. <span data-ttu-id="e7b61-116">选择 **启用定义停用**。</span><span class="sxs-lookup"><span data-stu-id="e7b61-116">Select **Turn on definition retirement**.</span></span> <span data-ttu-id="e7b61-117">默认情况下，启用此策略。</span><span class="sxs-lookup"><span data-stu-id="e7b61-117">By default, this policy is enabled.</span></span> <span data-ttu-id="e7b61-118">如果设置为 **"未配置"，** 则启用定义停用。</span><span class="sxs-lookup"><span data-stu-id="e7b61-118">If set **Not configured**, definition retirement is enabled.</span></span> 

4. <span data-ttu-id="e7b61-119">若要编辑策略，请选择 **"编辑策略设置"** 链接。</span><span class="sxs-lookup"><span data-stu-id="e7b61-119">To edit the policy, select the **edit policy setting** link.</span></span>

5. <span data-ttu-id="e7b61-120">选择 **"已启用**"，然后选择"确定 **"。**</span><span class="sxs-lookup"><span data-stu-id="e7b61-120">Select **Enabled**, and then select **OK**.</span></span>

6. <span data-ttu-id="e7b61-121">部署更新的组策略对象。</span><span class="sxs-lookup"><span data-stu-id="e7b61-121">Deploy your updated Group Policy Object.</span></span> <span data-ttu-id="e7b61-122">请参阅 [组策略管理控制台](/windows/win32/srvnodes/group-policy)。</span><span class="sxs-lookup"><span data-stu-id="e7b61-122">See [Group Policy Management Console](/windows/win32/srvnodes/group-policy).</span></span>

> [!TIP]
> <span data-ttu-id="e7b61-123">是否在本地使用组策略对象？</span><span class="sxs-lookup"><span data-stu-id="e7b61-123">Are you using Group Policy Objects on premises?</span></span> <span data-ttu-id="e7b61-124">查看它们在云中如何转换。</span><span class="sxs-lookup"><span data-stu-id="e7b61-124">See how they translate in the cloud.</span></span> <span data-ttu-id="e7b61-125">[在预览版中，使用组策略分析Microsoft Endpoint Manager本地组策略对象](/mem/intune/configuration/group-policy-analytics)。</span><span class="sxs-lookup"><span data-stu-id="e7b61-125">[Analyze your on-premises group policy objects using Group Policy analytics in Microsoft Endpoint Manager - Preview](/mem/intune/configuration/group-policy-analytics).</span></span> 
  
## <a name="related-articles"></a><span data-ttu-id="e7b61-126">相关文章</span><span class="sxs-lookup"><span data-stu-id="e7b61-126">Related articles</span></span>

- [<span data-ttu-id="e7b61-127">Windows 10 中的 Microsoft Defender 防病毒</span><span class="sxs-lookup"><span data-stu-id="e7b61-127">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
 
- [<span data-ttu-id="e7b61-128">启用云保护</span><span class="sxs-lookup"><span data-stu-id="e7b61-128">Enable cloud-delivered protection</span></span>](enable-cloud-protection-microsoft-defender-antivirus.md)

- [<span data-ttu-id="e7b61-129">如何创建和部署反恶意软件策略：云保护服务</span><span class="sxs-lookup"><span data-stu-id="e7b61-129">How to create and deploy antimalware policies: Cloud-protection service</span></span>](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service)