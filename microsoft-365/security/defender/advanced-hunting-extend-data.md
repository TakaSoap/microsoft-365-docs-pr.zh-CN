---
title: 使用正确的设置扩展高级搜寻范围
description: 检查 Windows 设备上审核设置和其他设置，以帮助确保你在高级搜寻中获得最全面的数据
keywords: 高级搜寻， 事件， 透视， 实体， 审核设置， 用户帐户管理， 安全组管理， 威胁搜寻， 网络威胁搜寻， 搜索， 查询， 遥测， Microsoft 365， Microsoft 威胁防护
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 1fc4635b71e68bb56fa7ec54c9c7b1263b83446b
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/01/2021
ms.locfileid: "51498235"
---
# <a name="extend-advanced-hunting-coverage-with-the-right-settings"></a><span data-ttu-id="820b8-104">使用正确的设置扩展高级搜寻范围</span><span class="sxs-lookup"><span data-stu-id="820b8-104">Extend advanced hunting coverage with the right settings</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="820b8-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="820b8-105">**Applies to:**</span></span>
- <span data-ttu-id="820b8-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="820b8-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="820b8-107">[高级搜寻](advanced-hunting-overview.md) 依赖于来自各种源的数据，包括你的设备、Office 365 工作区、Azure AD 和 Microsoft Defender for Identity。</span><span class="sxs-lookup"><span data-stu-id="820b8-107">[Advanced hunting](advanced-hunting-overview.md) relies on data coming from various sources, including your devices, your Office 365 workspaces, Azure AD, and Microsoft Defender for Identity.</span></span> <span data-ttu-id="820b8-108">若要尽可能获取最全面的数据，请确保在相应的数据源中具有正确的设置。</span><span class="sxs-lookup"><span data-stu-id="820b8-108">To get the most comprehensive data possible, ensure that you have the correct settings in the corresponding data sources.</span></span>

## <a name="advanced-security-auditing-on-windows-devices"></a><span data-ttu-id="820b8-109">Windows 设备上的高级安全审核</span><span class="sxs-lookup"><span data-stu-id="820b8-109">Advanced security auditing on Windows devices</span></span>
<span data-ttu-id="820b8-110">打开这些高级审核设置，以确保获取有关设备上活动的数据，包括本地帐户管理、本地安全组管理和服务创建。</span><span class="sxs-lookup"><span data-stu-id="820b8-110">Turn on these advanced auditing settings to ensure you get data about activities on your devices, including local account management, local security group management, and service creation.</span></span>

| <span data-ttu-id="820b8-111">Data</span><span class="sxs-lookup"><span data-stu-id="820b8-111">Data</span></span> | <span data-ttu-id="820b8-112">说明</span><span class="sxs-lookup"><span data-stu-id="820b8-112">Description</span></span> | <span data-ttu-id="820b8-113">架构表</span><span class="sxs-lookup"><span data-stu-id="820b8-113">Schema table</span></span> | <span data-ttu-id="820b8-114">如何配置</span><span class="sxs-lookup"><span data-stu-id="820b8-114">How to configure</span></span> |
| --- | --- | --- | --- |
| <span data-ttu-id="820b8-115">帐户管理</span><span class="sxs-lookup"><span data-stu-id="820b8-115">Account management</span></span> | <span data-ttu-id="820b8-116">捕获为指示本地帐户创建、删除和其他与帐户相关的活动 `ActionType` 的各种值的事件</span><span class="sxs-lookup"><span data-stu-id="820b8-116">Events captured as various `ActionType` values indicating local account creation, deletion, and other account-related activities</span></span> | [<span data-ttu-id="820b8-117">DeviceEvents</span><span class="sxs-lookup"><span data-stu-id="820b8-117">DeviceEvents</span></span>](advanced-hunting-deviceevents-table.md) | <span data-ttu-id="820b8-118">- 部署高级安全审核策略 [：审核用户帐户管理](/windows/security/threat-protection/auditing/audit-user-account-management)</span><span class="sxs-lookup"><span data-stu-id="820b8-118">- Deploy an advanced security audit policy: [Audit User Account Management](/windows/security/threat-protection/auditing/audit-user-account-management)</span></span><br> <span data-ttu-id="820b8-119">- [了解高级安全审核策略](/windows/security/threat-protection/auditing/advanced-security-auditing)</span><span class="sxs-lookup"><span data-stu-id="820b8-119">- [Learn about advanced security audit policies](/windows/security/threat-protection/auditing/advanced-security-auditing)</span></span> |
| <span data-ttu-id="820b8-120">安全组管理</span><span class="sxs-lookup"><span data-stu-id="820b8-120">Security group management</span></span> | <span data-ttu-id="820b8-121">捕获为指示本地安全组创建和其他本地组管理活动 `ActionType` 的各种值的事件</span><span class="sxs-lookup"><span data-stu-id="820b8-121">Events captured as various `ActionType` values indicating local security group creation and other local group management activities</span></span> | [<span data-ttu-id="820b8-122">DeviceEvents</span><span class="sxs-lookup"><span data-stu-id="820b8-122">DeviceEvents</span></span>](advanced-hunting-deviceevents-table.md) | <span data-ttu-id="820b8-123">- 部署高级安全审核策略： [审核安全组管理](/windows/security/threat-protection/auditing/audit-security-group-management)</span><span class="sxs-lookup"><span data-stu-id="820b8-123">- Deploy an advanced security audit policy: [Audit Security Group Management](/windows/security/threat-protection/auditing/audit-security-group-management)</span></span><br> <span data-ttu-id="820b8-124">- [了解高级安全审核策略](/windows/security/threat-protection/auditing/advanced-security-auditing)</span><span class="sxs-lookup"><span data-stu-id="820b8-124">- [Learn about advanced security audit policies](/windows/security/threat-protection/auditing/advanced-security-auditing)</span></span> |
| <span data-ttu-id="820b8-125">服务安装</span><span class="sxs-lookup"><span data-stu-id="820b8-125">Service installation</span></span> | <span data-ttu-id="820b8-126">使用 值 捕获的事件 `ActionType` `ServiceInstalled` ，指示已创建服务</span><span class="sxs-lookup"><span data-stu-id="820b8-126">Events captured with the `ActionType` value `ServiceInstalled`, indicating that a service has been created</span></span> | [<span data-ttu-id="820b8-127">DeviceEvents</span><span class="sxs-lookup"><span data-stu-id="820b8-127">DeviceEvents</span></span>](advanced-hunting-deviceevents-table.md) | <span data-ttu-id="820b8-128">- 部署高级安全审核策略： [审核安全系统扩展](/windows/security/threat-protection/auditing/audit-security-system-extension)</span><span class="sxs-lookup"><span data-stu-id="820b8-128">- Deploy an advanced security audit policy: [Audit Security System Extension](/windows/security/threat-protection/auditing/audit-security-system-extension)</span></span><br> <span data-ttu-id="820b8-129">- [了解高级安全审核策略](/windows/security/threat-protection/auditing/advanced-security-auditing)</span><span class="sxs-lookup"><span data-stu-id="820b8-129">- [Learn about advanced security audit policies](/windows/security/threat-protection/auditing/advanced-security-auditing)</span></span> |

## <a name="microsoft-defender-for-identity-sensor-on-the-domain-controller"></a><span data-ttu-id="820b8-130">域控制器上的 Microsoft Defender for Identity 传感器</span><span class="sxs-lookup"><span data-stu-id="820b8-130">Microsoft Defender for Identity sensor on the domain controller</span></span>
<span data-ttu-id="820b8-131">如果你正在本地运行 Active Directory，则需要在域控制器上安装 Microsoft Defender for Identity 传感器，才能获取 Microsoft Defender for Identity 的数据。</span><span class="sxs-lookup"><span data-stu-id="820b8-131">If you're running Active Directory on premises, you need to install the Microsoft Defender for Identity sensor on the domain controller to get data for Microsoft Defender for Identity.</span></span> <span data-ttu-id="820b8-132">安装并正确配置后，此数据还将通过 Microsoft Defender for Identity 馈送到高级搜寻中，并提供标识信息和网络中事件的更全面的图片。</span><span class="sxs-lookup"><span data-stu-id="820b8-132">When installed and properly configured, this data also feeds into advanced hunting through Microsoft Defender for Identity and provides a more holistic picture of identity information and events in your network.</span></span> <span data-ttu-id="820b8-133">此数据还增强了 Microsoft Defender for Identity 生成高级搜寻也涵盖的相关警报的能力。</span><span class="sxs-lookup"><span data-stu-id="820b8-133">This data also enhances the ability of Microsoft Defender for Identity to generate relevant alerts that are also covered by advanced hunting.</span></span> 

| <span data-ttu-id="820b8-134">Data</span><span class="sxs-lookup"><span data-stu-id="820b8-134">Data</span></span> | <span data-ttu-id="820b8-135">说明</span><span class="sxs-lookup"><span data-stu-id="820b8-135">Description</span></span> | <span data-ttu-id="820b8-136">架构表</span><span class="sxs-lookup"><span data-stu-id="820b8-136">Schema table</span></span> | <span data-ttu-id="820b8-137">如何配置</span><span class="sxs-lookup"><span data-stu-id="820b8-137">How to configure</span></span> |
| --- | --- | --- | --- |
| <span data-ttu-id="820b8-138">域控制器</span><span class="sxs-lookup"><span data-stu-id="820b8-138">Domain controller</span></span> | <span data-ttu-id="820b8-139">从本地 Active Directory 发送到 Microsoft Defender for Identity 的数据，丰富了与标识有关的信息，例如帐户详细信息、登录活动和 Active Directory 查询</span><span class="sxs-lookup"><span data-stu-id="820b8-139">Data from on-premises Active Directory sent to Microsoft Defender for Identity, enriching identity-related information, such as account details, logon activity, and Active Directory queries</span></span> | <span data-ttu-id="820b8-140">多个表，包括[IdentityInfo、IdentityLogonEvents](advanced-hunting-identitylogonevents-table.md)和[IdentityQueryEvents](advanced-hunting-identityqueryevents-table.md) [](advanced-hunting-identityinfo-table.md)</span><span class="sxs-lookup"><span data-stu-id="820b8-140">Multiple tables, including [IdentityInfo](advanced-hunting-identityinfo-table.md), [IdentityLogonEvents](advanced-hunting-identitylogonevents-table.md), and [IdentityQueryEvents](advanced-hunting-identityqueryevents-table.md)</span></span>  | <span data-ttu-id="820b8-141">- [安装 Microsoft Defender for Identity 传感器](/azure-advanced-threat-protection/install-atp-step4)</span><span class="sxs-lookup"><span data-stu-id="820b8-141">- [Install the Microsoft Defender for Identity sensor](/azure-advanced-threat-protection/install-atp-step4)</span></span><br><span data-ttu-id="820b8-142">- [打开相关的 Windows 事件](/azure-advanced-threat-protection/configure-event-collection)</span><span class="sxs-lookup"><span data-stu-id="820b8-142">- [Turn on relevant Windows Events](/azure-advanced-threat-protection/configure-event-collection)</span></span> |

## <a name="related-topics"></a><span data-ttu-id="820b8-143">相关主题</span><span class="sxs-lookup"><span data-stu-id="820b8-143">Related topics</span></span>
- [<span data-ttu-id="820b8-144">高级搜寻概述</span><span class="sxs-lookup"><span data-stu-id="820b8-144">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="820b8-145">了解架构</span><span class="sxs-lookup"><span data-stu-id="820b8-145">Understand the schema</span></span>](advanced-hunting-schema-tables.md)