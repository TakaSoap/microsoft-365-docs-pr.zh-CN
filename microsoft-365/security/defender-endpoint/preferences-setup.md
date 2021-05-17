---
title: 配置Microsoft Defender 安全中心设置
description: 使用设置页配置常规设置、权限、api 和规则。
keywords: 设置， 常规设置， 权限， api， 规则
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
ms.openlocfilehash: 5869e8406158eb6d6b2f48b3083cb9011bb3951d
ms.sourcegitcommit: dc1ac43a57fac6f57438859dd668f927d94fdf34
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/07/2021
ms.locfileid: "51604341"
---
# <a name="configure-microsoft-defender-security-center-settings"></a><span data-ttu-id="05d37-104">配置Microsoft Defender 安全中心设置</span><span class="sxs-lookup"><span data-stu-id="05d37-104">Configure Microsoft Defender Security Center settings</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="05d37-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="05d37-105">**Applies to:**</span></span>
- [<span data-ttu-id="05d37-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="05d37-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="05d37-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="05d37-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="05d37-108">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="05d37-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="05d37-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="05d37-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-prefsettings-abovefoldlink)

<span data-ttu-id="05d37-110">使用设置 **菜单** 修改常规设置、高级功能、启用预览体验、电子邮件通知和自定义威胁情报功能。</span><span class="sxs-lookup"><span data-stu-id="05d37-110">Use the **Settings** menu to modify general settings, advanced features, enable the preview experience, email notifications, and the custom threat intelligence feature.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="05d37-111">本节内容</span><span class="sxs-lookup"><span data-stu-id="05d37-111">In this section</span></span>

<span data-ttu-id="05d37-112">主题</span><span class="sxs-lookup"><span data-stu-id="05d37-112">Topic</span></span> | <span data-ttu-id="05d37-113">说明</span><span class="sxs-lookup"><span data-stu-id="05d37-113">Description</span></span>
:---|:---
<span data-ttu-id="05d37-114">常规设置</span><span class="sxs-lookup"><span data-stu-id="05d37-114">General settings</span></span> | <span data-ttu-id="05d37-115">修改之前在载入过程中定义的常规设置。</span><span class="sxs-lookup"><span data-stu-id="05d37-115">Modify your general settings that were previously defined as part of the onboarding process.</span></span>
<span data-ttu-id="05d37-116">Permissions</span><span class="sxs-lookup"><span data-stu-id="05d37-116">Permissions</span></span> | <span data-ttu-id="05d37-117">使用 RBAC 和设备组管理门户访问。</span><span class="sxs-lookup"><span data-stu-id="05d37-117">Manage portal access using RBAC as well as device groups.</span></span>
<span data-ttu-id="05d37-118">API</span><span class="sxs-lookup"><span data-stu-id="05d37-118">APIs</span></span> | <span data-ttu-id="05d37-119">启用威胁情报和 SIEM 集成。</span><span class="sxs-lookup"><span data-stu-id="05d37-119">Enable the threat intel and SIEM integration.</span></span>
<span data-ttu-id="05d37-120">Rules</span><span class="sxs-lookup"><span data-stu-id="05d37-120">Rules</span></span> | <span data-ttu-id="05d37-121">配置抑制规则和自动化设置。</span><span class="sxs-lookup"><span data-stu-id="05d37-121">Configure suppressions rules and automation settings.</span></span>
<span data-ttu-id="05d37-122">设备管理</span><span class="sxs-lookup"><span data-stu-id="05d37-122">Device management</span></span> | <span data-ttu-id="05d37-123">载入和载出设备。</span><span class="sxs-lookup"><span data-stu-id="05d37-123">Onboard and offboard devices.</span></span>
<span data-ttu-id="05d37-124">网络评估</span><span class="sxs-lookup"><span data-stu-id="05d37-124">Network assessments</span></span> | <span data-ttu-id="05d37-125">选择要定期扫描并添加到设备清单的设备。</span><span class="sxs-lookup"><span data-stu-id="05d37-125">Choose devices to be scanned regularly and added to the device inventory.</span></span>
