---
title: 步骤 9：简化密码更新
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/01/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: 了解并配置混合环境的密码写回。
ms.openlocfilehash: 55da101ca729de804ae76dafbe35a46969af9d8d
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2018
ms.locfileid: "26865581"
---
# <a name="step-9-simplify-password-updates"></a><span data-ttu-id="64bc3-103">步骤 9：简化密码更新</span><span class="sxs-lookup"><span data-stu-id="64bc3-103">Step 9: Simplify password updates</span></span>

<span data-ttu-id="64bc3-104">\*\* 此步骤对于混合环境来说是可选的，适用于 Microsoft 365 企业版的 E3 和 E5 版本</span><span class="sxs-lookup"><span data-stu-id="64bc3-104">*This step is optional for hybrid environments and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<span data-ttu-id="64bc3-p101">在此步骤中，将允许用户通过 Azure Active Directory (AD) 重置其密码，然后复制到本地 Windows Server Active Directory (AD)。此过程称为密码写回。通过密码写回，用户不需要通过本地 Windows Server AD（用户帐户及其属性的存储位置）更新其密码。这非常适用于对本地网络没有远程访问连接的漫游或远程用户。</span><span class="sxs-lookup"><span data-stu-id="64bc3-p101">In this step, you'll allow users to reset their passwords through Azure Active Directory (AD), which is then replicated to your local Windows Server Active Directory (AD). This process is known as password writeback. With password writeback, users don’t need to update their passwords through the on-premises Windows Server AD where user accounts and their attributes are stored. This is valuable to roaming or remote users who do not have a remote access connection to the on-premises network.</span></span>

<span data-ttu-id="64bc3-109">需要密码写回才可充分利用 Identity Protection 功能，例如，当检测到高风险的帐户泄露时要求用户更改其本地密码。</span><span class="sxs-lookup"><span data-stu-id="64bc3-109">Password writeback is required to fully utilize Identity Protection feature capabilities, such as requiring users to change their on-premises passwords when there has been a high risk of account compromise detected.</span></span>

<span data-ttu-id="64bc3-110">有关其他信息和配置说明，请参阅 [Azure AD SSPR 密码写回](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-writeback)。</span><span class="sxs-lookup"><span data-stu-id="64bc3-110">For additional information and configuration instructions, see [Azure AD SSPR with password writeback](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-writeback).</span></span>

>[!Note]
><span data-ttu-id="64bc3-p102">升级到最新版本的 Azure AD Connect，以确保即时获取最佳体验和新功能。有关详细信息，请参阅 [Azure AD Connect 自定义安装](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-get-started-custom)。</span><span class="sxs-lookup"><span data-stu-id="64bc3-p102">Upgrade to the latest version of Azure AD Connect to ensure the best possible experience and new features as they are released. For more information, see [Custom installation of Azure AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-get-started-custom).</span></span>
>

<span data-ttu-id="64bc3-113">作为临时检查点，请查看对应于此步骤的[退出条件](identity-exit-criteria.md#crit-identity-pw-writeback)。</span><span class="sxs-lookup"><span data-stu-id="64bc3-113">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-pw-writeback) for this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="64bc3-114">后续步骤</span><span class="sxs-lookup"><span data-stu-id="64bc3-114">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step10.png)| [<span data-ttu-id="64bc3-115">简化用户登录</span><span class="sxs-lookup"><span data-stu-id="64bc3-115">Simplify user sign-in</span></span>](identity-single-sign-on.md) |

