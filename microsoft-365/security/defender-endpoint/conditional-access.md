---
title: 启用条件访问以更好地保护用户、设备和数据
description: 启用条件访问，以防止在将设备视为存在风险且应用程序被确定为不兼容时运行应用程序。
keywords: 条件访问， 阻止应用程序， 安全级别， intune，
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
ms.openlocfilehash: 21d17ee789a4757df10e99514f23cfc26b186405
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166193"
---
# <a name="enable-conditional-access-to-better-protect-users-devices-and-data"></a><span data-ttu-id="1e63f-104">启用条件访问以更好地保护用户、设备和数据</span><span class="sxs-lookup"><span data-stu-id="1e63f-104">Enable Conditional Access to better protect users, devices, and data</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="1e63f-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="1e63f-105">**Applies to:**</span></span>
- [<span data-ttu-id="1e63f-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="1e63f-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="1e63f-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1e63f-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="1e63f-108">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="1e63f-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="1e63f-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="1e63f-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-conditionalaccess-abovefoldlink)

<span data-ttu-id="1e63f-110">条件访问是一项功能，它通过确保只有安全设备有权访问应用程序，来帮助你更好地保护用户和企业信息。</span><span class="sxs-lookup"><span data-stu-id="1e63f-110">Conditional Access is a capability that helps you better protect your users and enterprise information by making sure that only secure devices have access to applications.</span></span>

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4byD1]

<span data-ttu-id="1e63f-111">使用条件访问，可以基于设备的风险级别控制对企业信息的访问。</span><span class="sxs-lookup"><span data-stu-id="1e63f-111">With Conditional Access, you can control access to enterprise information based on the risk level of a device.</span></span> <span data-ttu-id="1e63f-112">这有助于在使用受信任应用程序的受信任设备上保留受信任的用户。</span><span class="sxs-lookup"><span data-stu-id="1e63f-112">This helps keep trusted users on trusted devices using trusted applications.</span></span>

<span data-ttu-id="1e63f-113">你可以定义安全条件，在这些设备和应用程序可以运行和访问来自网络的信息时，通过强制执行策略来阻止应用程序运行，直到设备返回到兼容状态。</span><span class="sxs-lookup"><span data-stu-id="1e63f-113">You can define security conditions under which devices and applications can run and access information from your network by enforcing policies to stop applications from running until a device returns to a compliant state.</span></span> 

<span data-ttu-id="1e63f-114">Defender for Endpoint 中条件访问的实现基于 Microsoft Intune (Intune) 设备合规性策略和 Azure Active Directory (Azure AD) 条件访问策略。</span><span class="sxs-lookup"><span data-stu-id="1e63f-114">The implementation of Conditional Access in Defender for Endpoint is based on Microsoft Intune (Intune) device compliance policies and Azure Active Directory (Azure AD) conditional access policies.</span></span> 

<span data-ttu-id="1e63f-115">合规性策略与条件访问一起用于仅允许满足一个或多个设备合规性策略规则的设备访问应用程序。</span><span class="sxs-lookup"><span data-stu-id="1e63f-115">The compliance policy is used with Conditional Access to allow only devices that fulfill one or more device compliance policy rules to access applications.</span></span> 

## <a name="understand-the-conditional-access-flow"></a><span data-ttu-id="1e63f-116">了解条件访问流</span><span class="sxs-lookup"><span data-stu-id="1e63f-116">Understand the Conditional Access flow</span></span>
<span data-ttu-id="1e63f-117">设置条件访问，以便当在设备上看到威胁时，将阻止对敏感内容的访问，直到该威胁得到修正。</span><span class="sxs-lookup"><span data-stu-id="1e63f-117">Conditional Access is put in place so that when a threat is seen on a device, access to sensitive content is blocked until the threat is remediated.</span></span> 

<span data-ttu-id="1e63f-118">该流程首先会发现设备具有较低、中等或高风险。</span><span class="sxs-lookup"><span data-stu-id="1e63f-118">The flow begins with devices being seen to have a low, medium, or high risk.</span></span> <span data-ttu-id="1e63f-119">然后将这些风险确定发送到 Intune。</span><span class="sxs-lookup"><span data-stu-id="1e63f-119">These risk determinations are then sent to Intune.</span></span> 

<span data-ttu-id="1e63f-120">根据在 Intune 中配置策略方式，可以设置条件访问，以便满足某些条件时应用策略。</span><span class="sxs-lookup"><span data-stu-id="1e63f-120">Depending on how you configure policies in Intune, Conditional Access can be set up so that when certain conditions are met, the policy is applied.</span></span>

<span data-ttu-id="1e63f-121">例如，可以将 Intune 配置为在高风险设备上应用条件访问。</span><span class="sxs-lookup"><span data-stu-id="1e63f-121">For example, you can configure Intune to apply Conditional Access on devices that have a high risk.</span></span>

<span data-ttu-id="1e63f-122">在 Intune 中，设备合规性策略与 Azure AD 条件访问结合使用，以阻止对应用程序的访问。</span><span class="sxs-lookup"><span data-stu-id="1e63f-122">In Intune, a device compliance policy is used in conjunction with Azure AD Conditional Access to block access to applications.</span></span> <span data-ttu-id="1e63f-123">同时，启动自动调查和修正过程。</span><span class="sxs-lookup"><span data-stu-id="1e63f-123">In parallel, an automated investigation and remediation process is launched.</span></span>

 <span data-ttu-id="1e63f-124">在进行自动调查和修正时，用户仍可以使用该设备，但在完全修复威胁之前，将阻止访问企业数据。</span><span class="sxs-lookup"><span data-stu-id="1e63f-124">A user can still use the device while the automated investigation and remediation is taking place, but access to enterprise data is blocked until the threat is fully remediated.</span></span> 

<span data-ttu-id="1e63f-125">若要解决在设备上发现的风险，你需要将设备返回到兼容状态。</span><span class="sxs-lookup"><span data-stu-id="1e63f-125">To resolve the risk found on a device, you'll need to return the device to a compliant state.</span></span> <span data-ttu-id="1e63f-126">设备在未发现任何风险时将返回到兼容状态。</span><span class="sxs-lookup"><span data-stu-id="1e63f-126">A device returns to a compliant state when there is no risk seen on it.</span></span> 

<span data-ttu-id="1e63f-127">有三种方法可以解决风险：</span><span class="sxs-lookup"><span data-stu-id="1e63f-127">There are three ways to address a risk:</span></span>
1. <span data-ttu-id="1e63f-128">使用手动或自动修正。</span><span class="sxs-lookup"><span data-stu-id="1e63f-128">Use Manual or automated remediation.</span></span>
2. <span data-ttu-id="1e63f-129">解决设备上的活动警报。</span><span class="sxs-lookup"><span data-stu-id="1e63f-129">Resolve active alerts on the device.</span></span> <span data-ttu-id="1e63f-130">这将从设备中删除风险。</span><span class="sxs-lookup"><span data-stu-id="1e63f-130">This will remove the risk from the device.</span></span>
3. <span data-ttu-id="1e63f-131">你可以从活动策略中删除设备，因此条件访问不会应用到该设备。</span><span class="sxs-lookup"><span data-stu-id="1e63f-131">You can remove the device from the active policies and consequently, Conditional Access will not be applied on the device.</span></span> 

<span data-ttu-id="1e63f-132">手动修正需要 secops 管理员调查警报并解决在设备上看到的风险。</span><span class="sxs-lookup"><span data-stu-id="1e63f-132">Manual remediation requires a secops admin to investigate an alert and address the risk seen on the device.</span></span> <span data-ttu-id="1e63f-133">自动修正通过下一节"配置条件访问"中提供的配置 [设置进行配置](configure-conditional-access.md)。</span><span class="sxs-lookup"><span data-stu-id="1e63f-133">The automated remediation is configured through configuration settings provided in the following section, [Configure Conditional Access](configure-conditional-access.md).</span></span>

<span data-ttu-id="1e63f-134">通过手动或自动修正来消除风险时，设备将返回到兼容状态，并授予对应用程序的访问权限。</span><span class="sxs-lookup"><span data-stu-id="1e63f-134">When the risk is removed either through manual or automated remediation, the device returns to a compliant state and access to applications is granted.</span></span>

<span data-ttu-id="1e63f-135">下面的示例事件序列说明了操作中的条件访问：</span><span class="sxs-lookup"><span data-stu-id="1e63f-135">The following example sequence of events explains Conditional Access in action:</span></span>

1. <span data-ttu-id="1e63f-136">用户打开恶意文件，并且 Defender for Endpoint 将设备标志为高风险。</span><span class="sxs-lookup"><span data-stu-id="1e63f-136">A user opens a malicious file and Defender for Endpoint flags the device as high risk.</span></span>
2. <span data-ttu-id="1e63f-137">高风险评估将传递到 Intune。</span><span class="sxs-lookup"><span data-stu-id="1e63f-137">The high risk assessment is passed along to Intune.</span></span> <span data-ttu-id="1e63f-138">同时，启动自动调查以修正已识别的威胁。</span><span class="sxs-lookup"><span data-stu-id="1e63f-138">In parallel, an automated investigation is initiated to remediate the identified threat.</span></span> <span data-ttu-id="1e63f-139">还可以执行手动修正来修正已识别的威胁。</span><span class="sxs-lookup"><span data-stu-id="1e63f-139">A manual remediation can also be done to remediate the identified threat.</span></span>
3. <span data-ttu-id="1e63f-140">根据在 Intune 中创建的策略，设备被标记为不兼容。</span><span class="sxs-lookup"><span data-stu-id="1e63f-140">Based on the policy created in Intune, the device is marked as not compliant.</span></span> <span data-ttu-id="1e63f-141">然后，通过 Intune 条件访问策略将评估传达给 Azure AD。</span><span class="sxs-lookup"><span data-stu-id="1e63f-141">The assessment is then communicated to Azure AD by the Intune Conditional Access policy.</span></span> <span data-ttu-id="1e63f-142">在 Azure AD 中，应用相应的策略来阻止对应用程序的访问。</span><span class="sxs-lookup"><span data-stu-id="1e63f-142">In Azure AD, the corresponding policy is applied to block access to applications.</span></span>
4. <span data-ttu-id="1e63f-143">已完成手动或自动调查和修正，并删除威胁。</span><span class="sxs-lookup"><span data-stu-id="1e63f-143">The manual or automated investigation and remediation is completed and the threat is removed.</span></span> <span data-ttu-id="1e63f-144">Defender for Endpoint 发现设备上没有风险，Intune 评估设备是否合规。</span><span class="sxs-lookup"><span data-stu-id="1e63f-144">Defender for Endpoint sees that there is no risk on the device and Intune assesses the device to be in a compliant state.</span></span> <span data-ttu-id="1e63f-145">Azure AD 应用允许访问应用程序的策略。</span><span class="sxs-lookup"><span data-stu-id="1e63f-145">Azure AD applies the policy which allows access to applications.</span></span>
5. <span data-ttu-id="1e63f-146">用户现在可以访问应用程序。</span><span class="sxs-lookup"><span data-stu-id="1e63f-146">Users can now access applications.</span></span>

 
## <a name="related-topic"></a><span data-ttu-id="1e63f-147">相关主题</span><span class="sxs-lookup"><span data-stu-id="1e63f-147">Related topic</span></span>
- [<span data-ttu-id="1e63f-148">在 Microsoft Defender for Endpoint 中配置条件访问</span><span class="sxs-lookup"><span data-stu-id="1e63f-148">Configure Conditional Access in Microsoft Defender for Endpoint</span></span>](configure-conditional-access.md)
