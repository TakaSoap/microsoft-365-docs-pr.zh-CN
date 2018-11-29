---
title: 移动设备管理基础结构退出条件
description: Microsoft 365 企业版包括使用 Microsoft Intune 的移动设备管理。查看要求和先决条件，设置 Intune 使用 Azure Active Directory 资源，注册 iOS、 macOS、 Android 和 Windows 设备，部署应用程序、 创建配置配置文件、 使用合规性策略，并启用条件移动访问与 Microsoft 365 Enterprise 的设备管理。
keywords: Microsoft 365 Microsoft 365 企业版，Microsoft 365 文档，移动设备管理 Intune
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 08/10/2018
ms.topic: article
audience: ITPro
ms.prod: microsoft-365-enterprise
ms.service: ''
ms.technology: ''
ms.assetid: fb4182e6-5e78-45d0-9641-d791c4519441
ms.custom: microsoft-intune
ms.openlocfilehash: b511052698f42a07df5fc25aeaad7fc7f00c2a6e
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2018
ms.locfileid: "26865570"
---
# <a name="mobile-device-management-infrastructure-exit-criteria"></a><span data-ttu-id="7f8c6-105">移动设备管理基础结构退出条件</span><span class="sxs-lookup"><span data-stu-id="7f8c6-105">Mobile device management infrastructure exit criteria</span></span>

![](./media/deploy-foundation-infrastructure/mobiledevicemgmt_icon-small.png)

<span data-ttu-id="7f8c6-106">*这适用于 Microsoft 365 企业版 E3 和 E5 版本*</span><span class="sxs-lookup"><span data-stu-id="7f8c6-106">*This applies to the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="7f8c6-107">您将移动到的部署过程的下一个阶段之前，请确保您的配置满足以下移动设备管理基础结构要求。</span><span class="sxs-lookup"><span data-stu-id="7f8c6-107">Before you move on to the next phase in the deployment process, ensure that your configuration meets the following requirements for mobile device management infrastructure.</span></span>

- <span data-ttu-id="7f8c6-108">已设置 Intune，包括通过创建 Azure AD 用户和组为设备应用组织的规则。</span><span class="sxs-lookup"><span data-stu-id="7f8c6-108">Intune is set up, including the creation of Azure AD users and groups to apply your organization's rules for devices.</span></span>
- <span data-ttu-id="7f8c6-109">在 Intune 中有已注册设备，这样设备便能收到你创建的策略。</span><span class="sxs-lookup"><span data-stu-id="7f8c6-109">You have enrolled devices in Intune so that the devices can receive the policies you create.</span></span>
- <span data-ttu-id="7f8c6-110">向设备添加了应用，这样用户便能访问组织的 Microsoft 365 云服务（如 Exchange Online 和 SharePoint Online）。</span><span class="sxs-lookup"><span data-stu-id="7f8c6-110">Apps are added to devices so your users get access to your organization's Microsoft 365 cloud services, such as Exchange Online and SharePoint Online.</span></span>
- <span data-ttu-id="7f8c6-111">已使用你创建的 Azure AD 用户和组来配置功能和设置，并将它们应用于设备，这可能包括启用防病毒功能和限制特定应用。</span><span class="sxs-lookup"><span data-stu-id="7f8c6-111">Features and settings are configured and applied to your devices using the Azure AD users and groups you create, which might include enabling anti-virus and restricting specific apps.</span></span>
- <span data-ttu-id="7f8c6-p102">已制定合规性策略，对设备上的防火墙或密码长度有所要求。如果设备不合规，条件访问就会阻止访问组织的数据。</span><span class="sxs-lookup"><span data-stu-id="7f8c6-p102">Compliance policies are in place to require a firewall or a password length on a device. If devices aren't compliant, conditional access blocks access to your organization's data.</span></span>

## <a name="next-phase"></a><span data-ttu-id="7f8c6-114">下一阶段</span><span class="sxs-lookup"><span data-stu-id="7f8c6-114">Next phase</span></span>

|||
|:-------|:-----|
|![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)| <span data-ttu-id="7f8c6-115">Microsoft 365 企业版的端到端部署过程中您下一阶段是[信息保护](infoprotect-infrastructure.md)。</span><span class="sxs-lookup"><span data-stu-id="7f8c6-115">Your next phase in the end-to-end deployment process for Microsoft 365 Enterprise is [information protection](infoprotect-infrastructure.md).</span></span> |
