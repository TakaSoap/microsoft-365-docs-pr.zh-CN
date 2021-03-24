---
title: 载入问题和错误消息疑难解答
description: 完成 Microsoft Defender for Endpoint 的安装时载入问题和错误消息疑难解答。
keywords: 疑难解答， Azure Active Directory， 载入， 错误消息， 错误消息， microsoft defender for endpoint
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
ms.topic: troubleshooting
ms.technology: mde
ms.openlocfilehash: 63981d985140858cbbda54a10dc94b30f28131e5
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51055606"
---
# <a name="troubleshoot-subscription-and-portal-access-issues"></a><span data-ttu-id="04f32-104">解决订阅和门户访问问题</span><span class="sxs-lookup"><span data-stu-id="04f32-104">Troubleshoot subscription and portal access issues</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="04f32-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="04f32-105">**Applies to:**</span></span>
- [<span data-ttu-id="04f32-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="04f32-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="04f32-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="04f32-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="04f32-108">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="04f32-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="04f32-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="04f32-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-troublshootonboarding-abovefoldlink)

<span data-ttu-id="04f32-110">此页面提供了详细步骤，用于解决设置 Microsoft Defender for Endpoint 服务时可能发生的问题。</span><span class="sxs-lookup"><span data-stu-id="04f32-110">This page provides detailed steps to troubleshoot issues that might occur when setting up your Microsoft Defender for Endpoint service.</span></span>

<span data-ttu-id="04f32-111">如果收到错误消息，Microsoft Defender 安全中心将详细说明问题，并提供相关链接。</span><span class="sxs-lookup"><span data-stu-id="04f32-111">If you receive an error message, Microsoft Defender Security Center will provide a detailed explanation on what the issue is and relevant links will be supplied.</span></span>

## <a name="no-subscriptions-found"></a><span data-ttu-id="04f32-112">未找到订阅</span><span class="sxs-lookup"><span data-stu-id="04f32-112">No subscriptions found</span></span>

<span data-ttu-id="04f32-113">如果在访问 Microsoft Defender 安全中心时收到"未找到订阅"消息，这意味着用于登录门户的 Azure Active Directory (Azure AD) 没有 Microsoft Defender 终结点许可证。</span><span class="sxs-lookup"><span data-stu-id="04f32-113">If while accessing Microsoft Defender Security Center you get a **No subscriptions found** message, it means the Azure Active Directory (Azure AD) used to log in the user to the portal, does not have a Microsoft Defender for Endpoint license.</span></span>

<span data-ttu-id="04f32-114">可能的原因：</span><span class="sxs-lookup"><span data-stu-id="04f32-114">Potential reasons:</span></span>
- <span data-ttu-id="04f32-115">Windows E5 和 Office E5 许可证是分开的。</span><span class="sxs-lookup"><span data-stu-id="04f32-115">The Windows E5 and Office E5 licenses are separate licenses.</span></span>
- <span data-ttu-id="04f32-116">许可证已购买，但没有预配到此 Azure AD 实例。</span><span class="sxs-lookup"><span data-stu-id="04f32-116">The license was purchased but not provisioned to this Azure AD instance.</span></span>
    - <span data-ttu-id="04f32-117">这可能是许可证预配问题。</span><span class="sxs-lookup"><span data-stu-id="04f32-117">It could be a license provisioning issue.</span></span>
    - <span data-ttu-id="04f32-118">可能是你无意中将许可证预配到与用于向服务进行身份验证不同的 Microsoft Azure AD。</span><span class="sxs-lookup"><span data-stu-id="04f32-118">It could be you inadvertently provisioned the license to a different Microsoft Azure AD than the one used for authentication into the service.</span></span>

<span data-ttu-id="04f32-119">对于这两种情况，你应联系 Microsoft 支持部门，地址为 [适用于终结点的一](https://support.microsoft.com/getsupport?wf=0&tenant=ClassicCommercial&oaspworkflow=start_1.0.0.0&locale=en-us&supportregion=en-us&pesid=16055&ccsid=636419533611396913) 般 Microsoft Defender 或 [批量许可证支持](https://www.microsoft.com/licensing/servicecenter/Help/Contact.aspx)。</span><span class="sxs-lookup"><span data-stu-id="04f32-119">For both cases, you should contact Microsoft support at [General Microsoft Defender for Endpoint Support](https://support.microsoft.com/getsupport?wf=0&tenant=ClassicCommercial&oaspworkflow=start_1.0.0.0&locale=en-us&supportregion=en-us&pesid=16055&ccsid=636419533611396913) or [Volume license support](https://www.microsoft.com/licensing/servicecenter/Help/Contact.aspx).</span></span>

![未找到订阅的图像](images/atp-no-subscriptions-found.png)

## <a name="your-subscription-has-expired"></a><span data-ttu-id="04f32-121">你的订阅已过期</span><span class="sxs-lookup"><span data-stu-id="04f32-121">Your subscription has expired</span></span>

<span data-ttu-id="04f32-122">如果在访问 Microsoft Defender 安全中心时收到订阅 **已过期** 消息，则你的联机服务订阅已过期。</span><span class="sxs-lookup"><span data-stu-id="04f32-122">If while accessing Microsoft Defender Security Center you get a **Your subscription has expired** message, your online service subscription has expired.</span></span> <span data-ttu-id="04f32-123">与任何其他联机服务订阅一样，Microsoft Defender for Endpoint 订阅具有到期日期。</span><span class="sxs-lookup"><span data-stu-id="04f32-123">Microsoft Defender for Endpoint subscription, like any other online service subscription, has an expiration date.</span></span> 

<span data-ttu-id="04f32-124">你可以选择随时续订或延长许可证。</span><span class="sxs-lookup"><span data-stu-id="04f32-124">You can choose to renew or extend the license at any point in time.</span></span> <span data-ttu-id="04f32-125">在过期日期后访问门户时，如果选择不续订许可证，将显示你的订阅已过期的消息，你可以选择下载设备载出包。</span><span class="sxs-lookup"><span data-stu-id="04f32-125">When accessing the portal after the expiration date a **Your subscription has expired** message will be presented with an option to download the device offboarding package, should you choose to not renew the license.</span></span>

> [!NOTE]
> <span data-ttu-id="04f32-126">出于安全考虑，用于"载出"设备的程序包将在下载日期 30 天后过期。</span><span class="sxs-lookup"><span data-stu-id="04f32-126">For security reasons, the package used to Offboard devices will expire 30 days after the date it was downloaded.</span></span> <span data-ttu-id="04f32-127">发送到设备的过期载出包将被拒绝。</span><span class="sxs-lookup"><span data-stu-id="04f32-127">Expired offboarding packages sent to a device will be rejected.</span></span> <span data-ttu-id="04f32-128">下载载出包时，你将收到程序包到期日期的通知，该日期也将包含在程序包名称中。</span><span class="sxs-lookup"><span data-stu-id="04f32-128">When downloading an offboarding package you will be notified of the packages expiry date and it will also be included in the package name.</span></span>

![订阅已过期的图像](images/atp-subscription-expired.png)

## <a name="you-are-not-authorized-to-access-the-portal"></a><span data-ttu-id="04f32-130">你无权访问门户</span><span class="sxs-lookup"><span data-stu-id="04f32-130">You are not authorized to access the portal</span></span>

<span data-ttu-id="04f32-131">如果收到"你无权访问门户"，请注意，Microsoft Defender for Endpoint 是一种安全监视、事件调查和响应产品，因此，对它的访问受到用户的限制和控制。</span><span class="sxs-lookup"><span data-stu-id="04f32-131">If you receive a **You are not authorized to access the portal**, be aware that Microsoft Defender for Endpoint is a security monitoring, incident investigation and response product, and as such, access to it is restricted and controlled by the user.</span></span>
<span data-ttu-id="04f32-132">有关详细信息，请参阅分配 [**对门户的用户访问权限**](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/assign-portal-access-windows-defender-advanced-threat-protection)。</span><span class="sxs-lookup"><span data-stu-id="04f32-132">For more information, see, [**Assign user access to the portal**](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/assign-portal-access-windows-defender-advanced-threat-protection).</span></span>

![未授权访问门户的图像](images/atp-not-authorized-to-access-portal.png)

## <a name="data-currently-isnt-available-on-some-sections-of-the-portal"></a><span data-ttu-id="04f32-134">数据当前在门户的一些部分不可用</span><span class="sxs-lookup"><span data-stu-id="04f32-134">Data currently isn't available on some sections of the portal</span></span>
<span data-ttu-id="04f32-135">如果门户仪表板和其他部分显示错误消息，如"数据当前不可用"：</span><span class="sxs-lookup"><span data-stu-id="04f32-135">If the portal dashboard and other sections show an error message such as "Data currently isn't available":</span></span>

![数据图像当前不可用](images/atp-data-not-available.png)

<span data-ttu-id="04f32-137">你需要允许 及其下的所有 `securitycenter.windows.com` 子域。</span><span class="sxs-lookup"><span data-stu-id="04f32-137">You'll need to allow the `securitycenter.windows.com` and all subdomains under it.</span></span> <span data-ttu-id="04f32-138">例如，`*.securitycenter.windows.com`。</span><span class="sxs-lookup"><span data-stu-id="04f32-138">For example, `*.securitycenter.windows.com`.</span></span>


## <a name="portal-communication-issues"></a><span data-ttu-id="04f32-139">门户通信问题</span><span class="sxs-lookup"><span data-stu-id="04f32-139">Portal communication issues</span></span>
<span data-ttu-id="04f32-140">如果在访问门户时遇到问题、缺少数据或对门户部分的访问权限受限，则需要验证是否允许并打开以下 URL 以便通信。</span><span class="sxs-lookup"><span data-stu-id="04f32-140">If you encounter issues with accessing the portal, missing data, or restricted access to portions of the portal, you'll need to verify that the following URLs are allowed and open for communication.</span></span>

- `*.blob.core.windows.net`
- `crl.microsoft.com`
- `https://*.microsoftonline-p.com`
- `https://*.securitycenter.windows.com` 
- `https://automatediracs-eus-prd.securitycenter.windows.com`
- `https://login.microsoftonline.com`
- `https://login.windows.net`
- `https://onboardingpackagescusprd.blob.core.windows.net`
- `https://secure.aadcdn.microsoftonline-p.com` 
- `https://securitycenter.windows.com` 
- `https://static2.sharepointonline.com` 



