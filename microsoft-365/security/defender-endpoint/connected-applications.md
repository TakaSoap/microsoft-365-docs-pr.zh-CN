---
title: Microsoft Defender for Endpoint 中的已连接应用程序
ms.reviewer: ''
description: 查看使用标准 OAuth 2.0 协议进行身份验证并提供用于 Microsoft Defender for Endpoint API 的令牌的已连接合作伙伴应用程序。
keywords: partners， applications， third-party， connections， sentinelone， lookout， bitdefender， corrata， morphisec， paloalto， ziften， better mobile
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 26c531c0544f92d664bfa0f1a21e4f33a0765d24
ms.sourcegitcommit: 55791ddab9ae484f76b30f0470eec8a4cf7b46d1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/20/2021
ms.locfileid: "51893493"
---
# <a name="connected-applications-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="8bb99-104">Microsoft Defender for Endpoint 中的已连接应用程序</span><span class="sxs-lookup"><span data-stu-id="8bb99-104">Connected applications in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="8bb99-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="8bb99-105">**Applies to:**</span></span>
- [<span data-ttu-id="8bb99-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="8bb99-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="8bb99-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8bb99-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


><span data-ttu-id="8bb99-108">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="8bb99-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="8bb99-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="8bb99-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="8bb99-110">连接的应用程序使用 API 与 Defender for Endpoint 平台集成。</span><span class="sxs-lookup"><span data-stu-id="8bb99-110">Connected applications integrates with the Defender for Endpoint platform using APIs.</span></span> 

<span data-ttu-id="8bb99-111">应用程序使用标准 OAuth 2.0 协议进行身份验证并提供与 Microsoft Defender for Endpoint API 一同使用的令牌。</span><span class="sxs-lookup"><span data-stu-id="8bb99-111">Applications use standard OAuth 2.0 protocol to authenticate and provide tokens for use with Microsoft Defender for Endpoint APIs.</span></span>  <span data-ttu-id="8bb99-112">此外，Azure Active Directory (Azure AD) 应用程序允许租户管理员设置对哪些 API 可以使用相应应用访问的显式控制。</span><span class="sxs-lookup"><span data-stu-id="8bb99-112">In addition, Azure Active Directory (Azure AD) applications allow tenant admins to set explicit control over which APIs can be accessed using the corresponding app.</span></span>
 
<span data-ttu-id="8bb99-113">需要按照以下步骤 [操作，](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/apis-intro) 将 API 与已连接的应用程序一同使用。</span><span class="sxs-lookup"><span data-stu-id="8bb99-113">You'll need to follow [these steps](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/apis-intro) to use the APIs with the connected application.</span></span>
 
## <a name="access-the-connected-application-page"></a><span data-ttu-id="8bb99-114">访问已连接的应用程序页</span><span class="sxs-lookup"><span data-stu-id="8bb99-114">Access the connected application page</span></span>
<span data-ttu-id="8bb99-115">从左侧导航菜单中，选择合作伙伴 **& API**  >  **连接的 AAD 应用程序**。</span><span class="sxs-lookup"><span data-stu-id="8bb99-115">From the left navigation menu, select **Partners & APIs** > **Connected AAD applications**.</span></span>

 
## <a name="view-connected-application-details"></a><span data-ttu-id="8bb99-116">查看连接的应用程序详细信息</span><span class="sxs-lookup"><span data-stu-id="8bb99-116">View connected application details</span></span>
<span data-ttu-id="8bb99-117">"已连接应用程序"页提供有关连接到组织中 Microsoft Defender for Endpoint 的 Azure AD 应用程序的信息。</span><span class="sxs-lookup"><span data-stu-id="8bb99-117">The Connected applications page provides information about the Azure AD applications connected to Microsoft Defender for Endpoint in your organization.</span></span> <span data-ttu-id="8bb99-118">你可以查看已连接应用程序的使用情况：上次查看时间、过去 24 小时内的请求数以及最近 30 天内的请求趋势。</span><span class="sxs-lookup"><span data-stu-id="8bb99-118">You can review the usage of the connected applications: last seen, number of requests in the past 24 hours, and request trends in the last 30 days.</span></span>

![已连接应用的图像](images/connected-apps.png)
 
## <a name="edit-reconfigure-or-delete-a-connected-application"></a><span data-ttu-id="8bb99-120">编辑、重新配置或删除已连接的应用程序</span><span class="sxs-lookup"><span data-stu-id="8bb99-120">Edit, reconfigure, or delete a connected application</span></span>
<span data-ttu-id="8bb99-121">" **打开应用程序设置"** 链接将在 Azure 门户中打开相应的 Azure AD 应用程序管理页面。</span><span class="sxs-lookup"><span data-stu-id="8bb99-121">The **Open application settings** link opens the corresponding Azure AD application management page in the Azure portal.</span></span> <span data-ttu-id="8bb99-122">在 Azure 门户中，你可以管理权限、重新配置或删除已连接的应用程序。</span><span class="sxs-lookup"><span data-stu-id="8bb99-122">From the Azure portal, you can manage permissions, reconfigure, or delete the connected applications.</span></span>
