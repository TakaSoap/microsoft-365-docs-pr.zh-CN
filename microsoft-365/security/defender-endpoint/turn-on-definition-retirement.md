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
ms.date: 06/10/2021
ms.reviewer: ''
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 505270d319a78de20bf6fed01b7ca79c9fc2b400
ms.sourcegitcommit: 33d19853a38dfa4e6ed21b313976643670a14581
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2021
ms.locfileid: "52903800"
---
# <a name="turn-on-definition-retirement"></a><span data-ttu-id="1f3e0-104">启用定义停用</span><span class="sxs-lookup"><span data-stu-id="1f3e0-104">Turn on definition retirement</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="1f3e0-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="1f3e0-105">**Applies to:**</span></span>

- [<span data-ttu-id="1f3e0-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="1f3e0-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="1f3e0-107">可以使用组策略配置定义停用。</span><span class="sxs-lookup"><span data-stu-id="1f3e0-107">You can configure definition retirement using Group Policy.</span></span> <span data-ttu-id="1f3e0-108">定义停用检查计算机是否具有必要的安全更新，以保护计算机免受特定漏洞的影响。</span><span class="sxs-lookup"><span data-stu-id="1f3e0-108">Definition retirement checks to see if a computer has the required security updates necessary to protect it against a particular vulnerability.</span></span> <span data-ttu-id="1f3e0-109">如果系统不易受定义检测到的漏洞攻击，则该定义将"停用"。</span><span class="sxs-lookup"><span data-stu-id="1f3e0-109">If the system is not vulnerable to the exploit detected by a definition, then that definition is "retired".</span></span> <span data-ttu-id="1f3e0-110">如果给定协议的所有安全智能都停用，则不再分析该协议。</span><span class="sxs-lookup"><span data-stu-id="1f3e0-110">If all security intelligence for a given protocol are retired then that protocol is no longer parsed.</span></span> <span data-ttu-id="1f3e0-111">启用此功能有助于提高性能。</span><span class="sxs-lookup"><span data-stu-id="1f3e0-111">Enabling this feature helps to improve performance.</span></span> <span data-ttu-id="1f3e0-112">在具有所有最新安全更新的计算机上，网络保护不会影响网络性能。</span><span class="sxs-lookup"><span data-stu-id="1f3e0-112">On a computer that is up-to-date with all the latest security updates, network protection will have no impact on network performance.</span></span>

## <a name="use-group-policy-to-configure-definition-retirement"></a><span data-ttu-id="1f3e0-113">使用组策略配置定义停用</span><span class="sxs-lookup"><span data-stu-id="1f3e0-113">Use Group Policy to configure definition retirement</span></span>

1. <span data-ttu-id="1f3e0-114">在组策略管理终结点上，打开组 [策略管理控制台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))。</span><span class="sxs-lookup"><span data-stu-id="1f3e0-114">On your Group Policy management endpoint, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).</span></span>

2. <span data-ttu-id="1f3e0-115">转到计算机 **配置**  >  **管理模板**  >  **Windows组件**  >  **Microsoft Defender 防病毒**  >  **网络检查系统 。**</span><span class="sxs-lookup"><span data-stu-id="1f3e0-115">Go to **Computer Configuration** > **Administrative Templates** > **Windows Components** > **Microsoft Defender Antivirus** > **Network Inspection System**.</span></span> 

3. <span data-ttu-id="1f3e0-116">选择 **启用定义停用**。</span><span class="sxs-lookup"><span data-stu-id="1f3e0-116">Select **Turn on definition retirement**.</span></span> <span data-ttu-id="1f3e0-117">默认情况下，启用此策略。</span><span class="sxs-lookup"><span data-stu-id="1f3e0-117">By default, this policy is enabled.</span></span> <span data-ttu-id="1f3e0-118">如果设置为 **"未配置"，** 则启用定义停用。</span><span class="sxs-lookup"><span data-stu-id="1f3e0-118">If set **Not configured**, definition retirement is enabled.</span></span> 

4. <span data-ttu-id="1f3e0-119">若要编辑策略，请选择 **"编辑策略设置"** 链接。</span><span class="sxs-lookup"><span data-stu-id="1f3e0-119">To edit the policy, select the **edit policy setting** link.</span></span>

5. <span data-ttu-id="1f3e0-120">选择 **"已启用**"，然后选择"确定 **"。**</span><span class="sxs-lookup"><span data-stu-id="1f3e0-120">Select **Enabled**, and then select **OK**.</span></span>

6. <span data-ttu-id="1f3e0-121">部署更新的组策略对象。</span><span class="sxs-lookup"><span data-stu-id="1f3e0-121">Deploy your updated Group Policy Object.</span></span> <span data-ttu-id="1f3e0-122">请参阅 [组策略管理控制台](/windows/win32/srvnodes/group-policy)。</span><span class="sxs-lookup"><span data-stu-id="1f3e0-122">See [Group Policy Management Console](/windows/win32/srvnodes/group-policy).</span></span>

> [!TIP]
> <span data-ttu-id="1f3e0-123">是否在本地使用组策略对象？</span><span class="sxs-lookup"><span data-stu-id="1f3e0-123">Are you using Group Policy Objects on premises?</span></span> <span data-ttu-id="1f3e0-124">查看它们在云中如何转换。</span><span class="sxs-lookup"><span data-stu-id="1f3e0-124">See how they translate in the cloud.</span></span> <span data-ttu-id="1f3e0-125">[在预览版中，使用组策略分析Microsoft Endpoint Manager本地组策略对象](/mem/intune/configuration/group-policy-analytics)。</span><span class="sxs-lookup"><span data-stu-id="1f3e0-125">[Analyze your on-premises group policy objects using Group Policy analytics in Microsoft Endpoint Manager - Preview](/mem/intune/configuration/group-policy-analytics).</span></span> 
  
