---
title: 解决 Microsoft 威胁防护服务问题
description: 查找已知 Microsoft 威胁防护问题的解决方案和变通方法
keywords: 解决 Microsoft 威胁防护、故障排除、Azure ATP、问题、加载项、设置页面
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: bbc7d5d434765b94b0b2707605be2edfbbc8e423
ms.sourcegitcommit: 2913fd74ad5086c7cac6388447285be9aa5a8e44
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/01/2020
ms.locfileid: "41661978"
---
# <a name="troubleshoot-microsoft-threat-protection-service-issues"></a><span data-ttu-id="dbf1c-104">解决 Microsoft 威胁防护服务问题</span><span class="sxs-lookup"><span data-stu-id="dbf1c-104">Troubleshoot Microsoft Threat Protection service issues</span></span>

<span data-ttu-id="dbf1c-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="dbf1c-105">**Applies to:**</span></span>
- <span data-ttu-id="dbf1c-106">Microsoft 威胁防护</span><span class="sxs-lookup"><span data-stu-id="dbf1c-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="dbf1c-107">本节介绍使用 Microsoft 威胁防护服务时可能会出现的问题。</span><span class="sxs-lookup"><span data-stu-id="dbf1c-107">This section addresses issues that might arise as you use the Microsoft Threat Protection service.</span></span>


## <a name="i-dont-see-microsoft-threat-protection-content"></a><span data-ttu-id="dbf1c-108">我看不到 Microsoft 威胁防护内容</span><span class="sxs-lookup"><span data-stu-id="dbf1c-108">I don't see Microsoft Threat Protection content</span></span>
<span data-ttu-id="dbf1c-109">如果您在门户中看不到导航窗格中的功能（如事件、操作中心或搜寻），则需要验证您的租户是否具有相应的许可证。</span><span class="sxs-lookup"><span data-stu-id="dbf1c-109">If you don't see capabilities on the navigation pane such as the Incidents, Action Center, or Hunting in your portal, you'll need to verify that your tenant has the appropriate licenses.</span></span> 

<span data-ttu-id="dbf1c-110">有关详细信息，请参阅[必备条件](prerequisites.md)。</span><span class="sxs-lookup"><span data-stu-id="dbf1c-110">For more information, see [Prerequisites](prerequisites.md).</span></span>

## <a name="azure-atp-alerts-are-not-showing-up-in-the-microsoft-threat-protection-incidents"></a><span data-ttu-id="dbf1c-111">Azure ATP 警报未在 Microsoft 威胁防护事件中显示</span><span class="sxs-lookup"><span data-stu-id="dbf1c-111">Azure ATP alerts are not showing up in the Microsoft Threat Protection incidents</span></span>
<span data-ttu-id="dbf1c-112">如果在环境中部署了 Azure ATP，但在 Microsoft 威胁防护事件中看不到 Azure ATP 警报，需要确保启用 Microsoft Cloud App Security 和 Azure ATP 集成。</span><span class="sxs-lookup"><span data-stu-id="dbf1c-112">If you have Azure ATP deployed in your environment but you're not seeing Azure ATP alerts as part of Microsoft Threat Protection incidents, you'll need to ensure that the Microsoft Cloud App Security and Azure ATP integration is enabled.</span></span> 

<span data-ttu-id="dbf1c-113">有关详细信息，请参阅[Azure ATP 集成](https://docs.microsoft.com/cloud-app-security/aatp-integration)。</span><span class="sxs-lookup"><span data-stu-id="dbf1c-113">For more information, see [Azure ATP integration](https://docs.microsoft.com/cloud-app-security/aatp-integration).</span></span>

## <a name="is-microsoft-threat-protection-available-for-us-government-community-cloud-gcc-or-gcc-high"></a><span data-ttu-id="dbf1c-114">Microsoft 威胁防护是否可供美国政府社区云（GCC）或 GCC High使用？</span><span class="sxs-lookup"><span data-stu-id="dbf1c-114">Is Microsoft Threat Protection available for US Government Community Cloud (GCC) or GCC High?</span></span>
<span data-ttu-id="dbf1c-115">目前不可用。</span><span class="sxs-lookup"><span data-stu-id="dbf1c-115">At the moment, it is not available.</span></span>

## <a name="where-is-the-settings-page-for-turning-the-service-on"></a><span data-ttu-id="dbf1c-116">打开服务的设置页面在什么位置？</span><span class="sxs-lookup"><span data-stu-id="dbf1c-116">Where is the settings page for turning the service on?</span></span>
<span data-ttu-id="dbf1c-117">若要打开 Microsoft 威胁防护，请访问 Microsoft 365 安全中心中的导航窗格中的**设置**。</span><span class="sxs-lookup"><span data-stu-id="dbf1c-117">To turn on Microsoft Threat Protection, access **Settings** from the navigation pane in the Microsoft 365 security center.</span></span> <span data-ttu-id="dbf1c-118">仅当您具有[必备权限和许可证](mtp-enable.md#check-license-eligibility-and-required-permissions)时，才会看到此导航项。</span><span class="sxs-lookup"><span data-stu-id="dbf1c-118">This navigation item is visible only if you have the [prerequisite permissions and licenses](mtp-enable.md#check-license-eligibility-and-required-permissions).</span></span>

## <a name="can-i-use-an-add-on-instead-of-the-required-e5-licenses"></a><span data-ttu-id="dbf1c-119">我是否可以使用加载项，而不是所需的 E5 许可证？</span><span class="sxs-lookup"><span data-stu-id="dbf1c-119">Can I use an add-on instead of the required E5 licenses?</span></span>
<span data-ttu-id="dbf1c-120">目前没有适用于 Microsoft 威胁防护的加载项。</span><span class="sxs-lookup"><span data-stu-id="dbf1c-120">There are currently no add-ons for Microsoft Threat Protection.</span></span> [<span data-ttu-id="dbf1c-121">请参阅许可要求</span><span class="sxs-lookup"><span data-stu-id="dbf1c-121">See licensing requirements</span></span>](prerequisites.md) 

