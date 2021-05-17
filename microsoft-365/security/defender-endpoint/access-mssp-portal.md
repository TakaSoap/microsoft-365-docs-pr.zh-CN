---
title: 访问 MSSP Microsoft Defender 安全中心门户
description: 访问 MSSP Microsoft Defender 安全中心门户
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
ms.openlocfilehash: 97122decede91e8b4f059b3b66999ac12b300172
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/24/2021
ms.locfileid: "51164853"
---
# <a name="access-the-microsoft-defender-security-center-mssp-customer-portal"></a><span data-ttu-id="816e9-104">访问 MSSP Microsoft Defender 安全中心门户</span><span class="sxs-lookup"><span data-stu-id="816e9-104">Access the Microsoft Defender Security Center MSSP customer portal</span></span>

<span data-ttu-id="816e9-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="816e9-105">**Applies to:**</span></span>
- [<span data-ttu-id="816e9-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="816e9-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="816e9-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="816e9-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="816e9-108">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="816e9-108">**Applies to:**</span></span>

- [<span data-ttu-id="816e9-109">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="816e9-109">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

><span data-ttu-id="816e9-110">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="816e9-110">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="816e9-111">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="816e9-111">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-mssp-support-abovefoldlink)




>[!NOTE] 
><span data-ttu-id="816e9-112">这些步骤集面向 MSSP。</span><span class="sxs-lookup"><span data-stu-id="816e9-112">These set of steps are directed towards the MSSP.</span></span> 

<span data-ttu-id="816e9-113">默认情况下，MSSP 客户通过以下MICROSOFT DEFENDER 安全中心访问其租户 `https://securitycenter.windows.com` ：。</span><span class="sxs-lookup"><span data-stu-id="816e9-113">By default, MSSP customers access their Microsoft Defender Security Center tenant through the following URL: `https://securitycenter.windows.com`.</span></span>
 

<span data-ttu-id="816e9-114">但是，MSSP 将需要使用以下格式的特定于租户的 URL：  `https://securitycenter.windows.com?tid=customer_tenant_id` 访问 MSSP 客户门户。</span><span class="sxs-lookup"><span data-stu-id="816e9-114">MSSPs however, will need to use a tenant-specific URL in the following format:  `https://securitycenter.windows.com?tid=customer_tenant_id` to access the MSSP customer portal.</span></span> 

<span data-ttu-id="816e9-115">通常，需要将 MSSP 添加到其打算管理的每个 MSSP 客户的 Azure AD。</span><span class="sxs-lookup"><span data-stu-id="816e9-115">In general, MSSPs will need to be added to each of the MSSP customer's Azure AD that they intend to manage.</span></span>


<span data-ttu-id="816e9-116">使用以下步骤获取 MSSP 客户租户 ID，然后使用该 ID 访问租户特定的 URL：</span><span class="sxs-lookup"><span data-stu-id="816e9-116">Use the following steps to obtain the MSSP customer tenant ID and then use the ID to access the tenant-specific URL:</span></span>

1. <span data-ttu-id="816e9-117">作为 MSSP，使用凭据登录到 Azure AD。</span><span class="sxs-lookup"><span data-stu-id="816e9-117">As an MSSP, login to Azure AD with your credentials.</span></span> 

2. <span data-ttu-id="816e9-118">将目录切换到 MSSP 客户的租户。</span><span class="sxs-lookup"><span data-stu-id="816e9-118">Switch directory to the MSSP customer's tenant.</span></span>

3.  <span data-ttu-id="816e9-119">选择 **Azure Active Directory >属性 "。**</span><span class="sxs-lookup"><span data-stu-id="816e9-119">Select **Azure Active Directory > Properties**.</span></span> <span data-ttu-id="816e9-120">你将在"目录 ID"字段中找到租户 ID。</span><span class="sxs-lookup"><span data-stu-id="816e9-120">You'll find the tenant ID in the Directory ID field.</span></span> 

4. <span data-ttu-id="816e9-121">通过替换以下 URL 中的值访问 MSSP `customer_tenant_id` 客户门户 `https://securitycenter.windows.com?tid=customer_tenant_id` ：。</span><span class="sxs-lookup"><span data-stu-id="816e9-121">Access the MSSP customer portal by replacing the `customer_tenant_id` value in the following URL: `https://securitycenter.windows.com?tid=customer_tenant_id`.</span></span>


## <a name="related-topics"></a><span data-ttu-id="816e9-122">相关主题</span><span class="sxs-lookup"><span data-stu-id="816e9-122">Related topics</span></span>
- [<span data-ttu-id="816e9-123">授予 MSSP 对门户的访问权限</span><span class="sxs-lookup"><span data-stu-id="816e9-123">Grant MSSP access to the portal</span></span>](grant-mssp-access.md)
- [<span data-ttu-id="816e9-124">配置警报通知</span><span class="sxs-lookup"><span data-stu-id="816e9-124">Configure alert notifications</span></span>](configure-mssp-notifications.md)
- [<span data-ttu-id="816e9-125">从客户租户获取警报</span><span class="sxs-lookup"><span data-stu-id="816e9-125">Fetch alerts from customer tenant</span></span>](fetch-alerts-mssp.md)
