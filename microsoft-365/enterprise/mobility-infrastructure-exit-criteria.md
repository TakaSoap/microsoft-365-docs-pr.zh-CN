---
title: 移动设备管理基础结构退出条件
description: microsoft 365 企业版包括使用 Microsoft Intune 的移动设备管理。 查看要求和先决条件、使用 Azure Active Directory 资源设置 Intune、注册 iOS、macOS、Android 和 Windows 设备、部署应用、创建配置配置文件、使用合规性策略, 以及为移动启用条件访问Microsoft 365 企业版的设备管理。
keywords: microsoft 365, microsoft 365 企业版, microsoft 365 文档, 移动设备管理, Intune
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/05/2019
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.service: ''
ms.technology: ''
ms.assetid: fb4182e6-5e78-45d0-9641-d791c4519441
audience: ITPro
ms.custom: microsoft-intune
ms.openlocfilehash: 14f216fe352d9108fe69028731f4c94dfb9d19f7
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32291229"
---
# <a name="mobile-device-management-infrastructure-exit-criteria"></a><span data-ttu-id="0453a-105">移动设备管理基础结构退出条件</span><span class="sxs-lookup"><span data-stu-id="0453a-105">Mobile device management infrastructure exit criteria</span></span>

![](./media/deploy-foundation-infrastructure/mobiledevicemgmt_icon-small.png)

<span data-ttu-id="0453a-106">*这适用于 Microsoft 365 企业版的 E3 和 E5 版本*</span><span class="sxs-lookup"><span data-stu-id="0453a-106">*This applies to the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="0453a-107">确保您的配置满足以下针对移动设备管理基础结构的要求。</span><span class="sxs-lookup"><span data-stu-id="0453a-107">Ensure that your configuration meets the following requirements for mobile device management infrastructure.</span></span>

- <span data-ttu-id="0453a-108">已设置 Intune，包括通过创建 Azure AD 用户和组为设备应用组织的规则。</span><span class="sxs-lookup"><span data-stu-id="0453a-108">Intune is set up, including the creation of Azure AD users and groups to apply your organization's rules for devices.</span></span>
- <span data-ttu-id="0453a-109">在 Intune 中有已注册设备，这样设备便能收到你创建的策略。</span><span class="sxs-lookup"><span data-stu-id="0453a-109">You have enrolled devices in Intune so that the devices can receive the policies you create.</span></span>
- <span data-ttu-id="0453a-110">向设备添加了应用，这样用户便能访问组织的 Microsoft 365 云服务（如 Exchange Online 和 SharePoint Online）。</span><span class="sxs-lookup"><span data-stu-id="0453a-110">Apps are added to devices so your users get access to your organization's Microsoft 365 cloud services, such as Exchange Online and SharePoint Online.</span></span>
- <span data-ttu-id="0453a-111">已使用你创建的 Azure AD 用户和组来配置功能和设置，并将它们应用于设备，这可能包括启用防病毒功能和限制特定应用。</span><span class="sxs-lookup"><span data-stu-id="0453a-111">Features and settings are configured and applied to your devices using the Azure AD users and groups you create, which might include enabling anti-virus and restricting specific apps.</span></span>
- <span data-ttu-id="0453a-p102">已制定合规性策略，对设备上的防火墙或密码长度有所要求。如果设备不合规，条件访问就会阻止访问组织的数据。</span><span class="sxs-lookup"><span data-stu-id="0453a-p102">Compliance policies are in place to require a firewall or a password length on a device. If devices aren't compliant, conditional access blocks access to your organization's data.</span></span>



## <a name="results-and-next-steps"></a><span data-ttu-id="0453a-114">结果和后续步骤</span><span class="sxs-lookup"><span data-stu-id="0453a-114">Results and next steps</span></span>

<span data-ttu-id="0453a-115">你的设备已在 Intune 中注册并配置了适当的策略。</span><span class="sxs-lookup"><span data-stu-id="0453a-115">Your devices are enrolled in Intune and configured with the appropriate policies.</span></span>

|||
|:-------|:-----|
|![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)| <span data-ttu-id="0453a-116">如果你按照 Microsoft 365 企业版端到端部署的阶段执行, 下一阶段是[信息保护](infoprotect-infrastructure.md)。</span><span class="sxs-lookup"><span data-stu-id="0453a-116">If you're following the phases for the end-to-end deployment of Microsoft 365 Enterprise, your next phase is [information protection](infoprotect-infrastructure.md).</span></span> |
