---
title: 使用 WMI 配置 Microsoft Defender 防病毒
description: 了解如何使用 WMI 脚本在 Microsoft Defender for Endpoint 中检索、修改和更新设置来配置和管理 Microsoft Defender 防病毒。
keywords: wmi， 脚本， windows management instrumentation， 配置
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
audience: ITPro
ms.topic: how-to
ms.openlocfilehash: 3a47a71c1d8ce416e2eacc9ca3aa47ef6c4bb499
ms.sourcegitcommit: 07dea2aa98daf0c4086f8590375167830027c802
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/13/2021
ms.locfileid: "51749838"
---
# <a name="use-windows-management-instrumentation-wmi-to-configure-and-manage-microsoft-defender-antivirus"></a><span data-ttu-id="0b2df-104">使用 Windows Management Instrumentation (WMI) 配置和管理 Microsoft Defender 防病毒</span><span class="sxs-lookup"><span data-stu-id="0b2df-104">Use Windows Management Instrumentation (WMI) to configure and manage Microsoft Defender Antivirus</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="0b2df-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="0b2df-105">**Applies to:**</span></span>

- [<span data-ttu-id="0b2df-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="0b2df-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="0b2df-107">Windows Management Instrumentation (WMI) 是一个脚本界面，可用于检索、修改和更新设置。</span><span class="sxs-lookup"><span data-stu-id="0b2df-107">Windows Management Instrumentation (WMI) is a scripting interface that allows you to retrieve, modify, and update settings.</span></span>

<span data-ttu-id="0b2df-108">有关 WMI 的更多内容，Microsoft 开发人员网络 [System Administration 库](/windows/win32/wmisdk/wmi-start-page)。</span><span class="sxs-lookup"><span data-stu-id="0b2df-108">Read more about WMI at the [Microsoft Developer Network System Administration library](/windows/win32/wmisdk/wmi-start-page).</span></span>

<span data-ttu-id="0b2df-109">Microsoft Defender 防病毒具有许多特定的 WMI 类，可用于执行与组策略和其他管理工具大多数相同的功能。</span><span class="sxs-lookup"><span data-stu-id="0b2df-109">Microsoft Defender Antivirus has a number of specific WMI classes that can be used to perform most of the same functions as Group Policy and other management tools.</span></span> <span data-ttu-id="0b2df-110">许多类都类似于 Defender [PowerShell cmdlet。](use-powershell-cmdlets-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="0b2df-110">Many of the classes are analogous to [Defender PowerShell cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md).</span></span>

<span data-ttu-id="0b2df-111">[MSDN Windows Defender WMIv2 提供程序](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)参考库列出了 Microsoft Defender 防病毒的可用 WMI 类，并包括示例脚本。</span><span class="sxs-lookup"><span data-stu-id="0b2df-111">The [MSDN Windows Defender WMIv2 Provider reference library](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal) lists the available WMI classes for Microsoft Defender Antivirus, and includes example scripts.</span></span>

<span data-ttu-id="0b2df-112">使用 WMI 所做的更改将影响部署或进行更改的终结点上的本地设置。</span><span class="sxs-lookup"><span data-stu-id="0b2df-112">Changes made with WMI will affect local settings on the endpoint where the changes are deployed or made.</span></span> <span data-ttu-id="0b2df-113">这意味着使用组策略、Microsoft Endpoint Configuration Manager 或 Microsoft Intune 部署策略可能会覆盖使用 WMI 所做的更改。</span><span class="sxs-lookup"><span data-stu-id="0b2df-113">This means that deployments of policy with Group Policy, Microsoft Endpoint Configuration Manager, or Microsoft Intune can overwrite changes made with WMI.</span></span> 

<span data-ttu-id="0b2df-114">你可以 [配置哪些设置可以使用本地策略覆盖在本地覆盖](configure-local-policy-overrides-microsoft-defender-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="0b2df-114">You can [configure which settings can be overridden locally  with local policy overrides](configure-local-policy-overrides-microsoft-defender-antivirus.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="0b2df-115">相关主题</span><span class="sxs-lookup"><span data-stu-id="0b2df-115">Related topics</span></span>

- [<span data-ttu-id="0b2df-116">有关管理和配置工具的参考主题</span><span class="sxs-lookup"><span data-stu-id="0b2df-116">Reference topics for management and configuration tools</span></span>](configuration-management-reference-microsoft-defender-antivirus.md)
- [<span data-ttu-id="0b2df-117">Windows 10 中的 Microsoft Defender 防病毒</span><span class="sxs-lookup"><span data-stu-id="0b2df-117">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)