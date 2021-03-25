---
title: 配置发送给 MSSP 的警报通知
description: 配置发送给 MSSP 的警报通知
keywords: 托管安全服务提供程序， mssp， 配置， 集成
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 67f7081e72b5ecc8bdb077f0537cf0cf92df38b9
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166049"
---
# <a name="configure-alert-notifications-that-are-sent-to-mssps"></a><span data-ttu-id="6cb23-104">配置发送给 MSSP 的警报通知</span><span class="sxs-lookup"><span data-stu-id="6cb23-104">Configure alert notifications that are sent to MSSPs</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="6cb23-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="6cb23-105">**Applies to:**</span></span>
- [<span data-ttu-id="6cb23-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="6cb23-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="6cb23-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6cb23-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="6cb23-108">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="6cb23-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="6cb23-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="6cb23-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-mssp-support-abovefoldlink)


>[!NOTE]
><span data-ttu-id="6cb23-110">此步骤可通过 MSSP 客户或 MSSP 完成。</span><span class="sxs-lookup"><span data-stu-id="6cb23-110">This step can be done by either the MSSP customer or MSSP.</span></span> <span data-ttu-id="6cb23-111">MSSP 必须被授予适当的权限，才能代表 MSSP 客户进行配置。</span><span class="sxs-lookup"><span data-stu-id="6cb23-111">MSSPs must be granted the appropriate permissions to configure this on behalf of the MSSP customer.</span></span>

<span data-ttu-id="6cb23-112">授予门户访问权限后，可创建通知通知规则，以便创建与租户关联的警报并满足设置条件时，向 MSSP 发送电子邮件。</span><span class="sxs-lookup"><span data-stu-id="6cb23-112">After access the portal is granted, alert notification rules can to be created so that emails are sent to MSSPs when alerts associated with the tenant are created and set conditions are met.</span></span>

 
<span data-ttu-id="6cb23-113">有关详细信息，请参阅创建 [警报通知的规则](configure-email-notifications.md#create-rules-for-alert-notifications)。</span><span class="sxs-lookup"><span data-stu-id="6cb23-113">For more information, see [Create rules for alert notifications](configure-email-notifications.md#create-rules-for-alert-notifications).</span></span>
 

<span data-ttu-id="6cb23-114">必须选中以下复选框：</span><span class="sxs-lookup"><span data-stu-id="6cb23-114">These check boxes must be checked:</span></span>
- <span data-ttu-id="6cb23-115">**包含组织** 名称 - 客户名称将添加到电子邮件通知中</span><span class="sxs-lookup"><span data-stu-id="6cb23-115">**Include organization name** - The customer name will be added to email notifications</span></span>
- <span data-ttu-id="6cb23-116">**包含租户特定的门户链接** - 警报链接 URL 将具有租户特定参数 (tid=target_tenant_id) ，以允许直接访问目标租户门户</span><span class="sxs-lookup"><span data-stu-id="6cb23-116">**Include tenant-specific portal link** - Alert link URL will have tenant specific parameter (tid=target_tenant_id) that allows direct access to target tenant portal</span></span>


## <a name="related-topics"></a><span data-ttu-id="6cb23-117">相关主题</span><span class="sxs-lookup"><span data-stu-id="6cb23-117">Related topics</span></span>
- [<span data-ttu-id="6cb23-118">授予对门户的 MSSP 访问权限</span><span class="sxs-lookup"><span data-stu-id="6cb23-118">Grant MSSP access to the portal</span></span>](grant-mssp-access.md)
- [<span data-ttu-id="6cb23-119">访问 MSSP 客户门户</span><span class="sxs-lookup"><span data-stu-id="6cb23-119">Access the MSSP customer portal</span></span>](access-mssp-portal.md)
- [<span data-ttu-id="6cb23-120">从客户租户提取警报</span><span class="sxs-lookup"><span data-stu-id="6cb23-120">Fetch alerts from customer tenant</span></span>](fetch-alerts-mssp.md)
