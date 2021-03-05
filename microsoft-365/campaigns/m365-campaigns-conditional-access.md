---
title: 设置条件访问策略
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
- M365-Campaigns
- m365solution-smb
ms.custom:
- Adm_O365
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
description: 了解如何要求 MFA 和为 Microsoft 365 商业版设置条件访问策略。
ms.openlocfilehash: e16b7f4ff7d215ee749435806be214a807cc60a4
ms.sourcegitcommit: 375168ee66be862cf3b00f2733c7be02e63408cf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/04/2021
ms.locfileid: "50453665"
---
# <a name="require-multi-factor-authentication-and-set-up-conditional-access-policies"></a><span data-ttu-id="9c89a-103">需要多重身份验证并设置条件访问策略</span><span class="sxs-lookup"><span data-stu-id="9c89a-103">Require multi-factor authentication and set up conditional access policies</span></span>

<span data-ttu-id="9c89a-104">使用多重身份验证和条件访问策略保护对数据的访问。</span><span class="sxs-lookup"><span data-stu-id="9c89a-104">You protect access to your data with multi-factor authentication and conditional access policies.</span></span> <span data-ttu-id="9c89a-105">这可显著增加安全性。</span><span class="sxs-lookup"><span data-stu-id="9c89a-105">These add substantial additional security.</span></span> <span data-ttu-id="9c89a-106">Microsoft 提供了一组建议用于所有客户的基准条件访问策略。</span><span class="sxs-lookup"><span data-stu-id="9c89a-106">Microsoft provides a set of baseline conditional access policies that are recommended for all customers.</span></span> <span data-ttu-id="9c89a-107">基线策略是一组预定义策略，可帮助保护组织免受许多常见攻击。</span><span class="sxs-lookup"><span data-stu-id="9c89a-107">Baseline policies are a set of predefined policies that help protect organizations against many common attacks.</span></span> <span data-ttu-id="9c89a-108">这些常见攻击可能包括密码加密、重播和网络钓鱼。</span><span class="sxs-lookup"><span data-stu-id="9c89a-108">These common attacks can include password spray, replay, and phishing.</span></span>

<span data-ttu-id="9c89a-109">这些策略要求管理员和用户输入第二种形式的身份验证 (称为多重身份验证，或在某些情况下) MFA 身份验证。</span><span class="sxs-lookup"><span data-stu-id="9c89a-109">These policies require admins and users to enter a second form of authentication (called multi-factor authentication, or MFA) under certain conditions.</span></span> <span data-ttu-id="9c89a-110">例如，如果贵组织的用户尝试从不同的国家/地区或未知设备登录 Microsoft 365，则登录可能会被视为有风险。</span><span class="sxs-lookup"><span data-stu-id="9c89a-110">For example, if a user in your organization tries to sign in to Microsoft 365 from a different country or from an unknown device, the sign-in might be considered risky.</span></span> <span data-ttu-id="9c89a-111">用户必须提供一种额外形式的身份验证 (如指纹或代码) 来证明其身份。</span><span class="sxs-lookup"><span data-stu-id="9c89a-111">The user must provide an extra form of authentication (such as a fingerprint or a code) to prove their identity.</span></span>

<span data-ttu-id="9c89a-112">目前，基准策略包括以下策略：</span><span class="sxs-lookup"><span data-stu-id="9c89a-112">Currently, the baseline policies include the following policies:</span></span>

- <span data-ttu-id="9c89a-113">在 Microsoft 365 管理中心中设置：</span><span class="sxs-lookup"><span data-stu-id="9c89a-113">Set up in Microsoft 365 admin center:</span></span>
  - <span data-ttu-id="9c89a-114">**要求管理员使用 MFA：** 要求对特权最大的管理员角色（包括全局管理员）进行多重身份验证。</span><span class="sxs-lookup"><span data-stu-id="9c89a-114">**Require MFA for admins**: Requires multi-factor authentication for the most privileged administrator roles, including global administrator.</span></span>
  - <span data-ttu-id="9c89a-115">**最终用户保护**：仅在登录存在风险时，才要求用户进行多重身份验证。</span><span class="sxs-lookup"><span data-stu-id="9c89a-115">**End-user protection**: Requires multi-factor authentication for users only when a sign-in is risky.</span></span> 
- <span data-ttu-id="9c89a-116">在 Azure Active Directory 门户中设置：</span><span class="sxs-lookup"><span data-stu-id="9c89a-116">Set up in Azure Active Directory portal:</span></span>
  - <span data-ttu-id="9c89a-117">**阻止旧式身份验证**：较旧的客户端应用和一些新应用不使用更新、更安全的身份验证协议。</span><span class="sxs-lookup"><span data-stu-id="9c89a-117">**Block legacy authentication**: Older client apps and some new apps don't use newer, more secure, authentication protocols.</span></span> <span data-ttu-id="9c89a-118">这些较旧的应用可以绕过条件访问策略并获取对环境的未经授权的访问。</span><span class="sxs-lookup"><span data-stu-id="9c89a-118">These older apps can bypass conditional access policies and gain unauthorized access to your environment.</span></span> <span data-ttu-id="9c89a-119">此策略阻止来自不支持条件访问的客户端的访问。</span><span class="sxs-lookup"><span data-stu-id="9c89a-119">This policy blocks access from clients that don't support conditional access.</span></span> 
  - <span data-ttu-id="9c89a-120">**需要 MFA 进行服务管理**：需要多重身份验证，以访问管理工具，包括配置基线策略 (Azure 门户) 。</span><span class="sxs-lookup"><span data-stu-id="9c89a-120">**Require MFA for Service Management**: Requires multi-factor authentication for access to management tools, including Azure portal (where you configure baseline policies).</span></span>

<span data-ttu-id="9c89a-121">我们建议您启用所有这些基线策略。</span><span class="sxs-lookup"><span data-stu-id="9c89a-121">We recommend that you enable all of these baseline policies.</span></span> <span data-ttu-id="9c89a-122">启用这些策略后，将提示管理员和用户注册 Azure AD 多重身份验证。</span><span class="sxs-lookup"><span data-stu-id="9c89a-122">After these policies are enabled, admins and users will be prompted to register for Azure AD Multifactor Authentication.</span></span>

<span data-ttu-id="9c89a-123">有关这些策略详细信息，请参阅 [什么是基线策略](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection)？</span><span class="sxs-lookup"><span data-stu-id="9c89a-123">For more information about these policies, see [What are baseline policies](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection)?</span></span>

## <a name="require-mfa"></a><span data-ttu-id="9c89a-124">需要使用 MFA</span><span class="sxs-lookup"><span data-stu-id="9c89a-124">Require MFA</span></span>

<span data-ttu-id="9c89a-125">若要要求所有用户使用第二种形式的 ID 登录：</span><span class="sxs-lookup"><span data-stu-id="9c89a-125">To require that all users sign in with a second form of ID:</span></span>

1. <span data-ttu-id="9c89a-126">转到管理中心， <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a> 然后选择"设置 **"。**</span><span class="sxs-lookup"><span data-stu-id="9c89a-126">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a> and choose **Setup**.</span></span>

2. <span data-ttu-id="9c89a-127">在"设置"页上 **，选择"\*\*\*\*使登录更安全"卡中的"查看**"。</span><span class="sxs-lookup"><span data-stu-id="9c89a-127">On the Setup page, choose **View** in the **Make sign-in more secure** card.</span></span>

    ![使登录更加安全。](../media/setupmfa.png)
3. <span data-ttu-id="9c89a-129">在"使登录更安全"页上，选择"**开始使用"。**</span><span class="sxs-lookup"><span data-stu-id="9c89a-129">On the Make sign-in more secure page, choose **Get started**.</span></span>

4. <span data-ttu-id="9c89a-130">在"加强登录安全"窗格中，选中"要求管理员进行多重身份验证"和"要求用户注册多重身份验证"旁边的复选框，如果检测到风险，则阻止 **访问**。</span><span class="sxs-lookup"><span data-stu-id="9c89a-130">On the Strengthen sign-in security pane, select the check boxes next to **Require multi-factor authentication for admins** and **Require users to register for multi-factor authentication and block access if risk is detected**.</span></span>
    <span data-ttu-id="9c89a-131">请务必从"查找用户 ["框中的](m365-campaigns-protect-admin-accounts.md#create-an-emergency-admin-account) MFA 要求中排除紧急或"断 **面"管理员** 帐户。</span><span class="sxs-lookup"><span data-stu-id="9c89a-131">Be sure to exclude the [emergency](m365-campaigns-protect-admin-accounts.md#create-an-emergency-admin-account) or "break-glass" admin account from the MFA requirement in the **Find users** box.</span></span>

    ![加强"登录安全"页。](../media/requiremfa.png)

5. <span data-ttu-id="9c89a-133">选择 **页面底部的** "创建策略"。</span><span class="sxs-lookup"><span data-stu-id="9c89a-133">Choose **Create policy** on the bottom of the page.</span></span>

## <a name="set-up-baseline-policies"></a><span data-ttu-id="9c89a-134">设置基线策略</span><span class="sxs-lookup"><span data-stu-id="9c89a-134">Set up baseline policies</span></span>

1. <span data-ttu-id="9c89a-135">转到 [Azure 门户，](https://portal.azure.com)然后导航到 **Azure Active Directory** \> **安全** \> **条件访问** 以创建新 **策略**。</span><span class="sxs-lookup"><span data-stu-id="9c89a-135">Go to the [Azure portal](https://portal.azure.com), and then navigate to **Azure Active Directory** \> **Security** \> **Conditional Access** to create a **new policy**.</span></span>

<span data-ttu-id="9c89a-136">请参阅每个策略的以下特定说明：</span><span class="sxs-lookup"><span data-stu-id="9c89a-136">See the following specific instructions for each policy:</span></span> <br>
    - [<span data-ttu-id="9c89a-137">要求管理员使用 MFA</span><span class="sxs-lookup"><span data-stu-id="9c89a-137">Require MFA for admins</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-administrators) <br>
    - [<span data-ttu-id="9c89a-138">要求用户使用 MFA</span><span class="sxs-lookup"><span data-stu-id="9c89a-138">Require MFA for users</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-end-users) <br>
    - [<span data-ttu-id="9c89a-139">阻止旧式身份验证</span><span class="sxs-lookup"><span data-stu-id="9c89a-139">Block legacy authentication</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-legacy-auth) <br>
    - [<span data-ttu-id="9c89a-140">需要 MFA 进行服务管理</span><span class="sxs-lookup"><span data-stu-id="9c89a-140">Require MFA for service management</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-azure)

> [!NOTE]
> <span data-ttu-id="9c89a-141">预览策略不再存在，用户将需要创建自己的策略。</span><span class="sxs-lookup"><span data-stu-id="9c89a-141">Preview policies no longer exist and users will need to create their own policies.</span></span>

<span data-ttu-id="9c89a-142">你可以设置额外的策略，例如要求批准的客户端应用。</span><span class="sxs-lookup"><span data-stu-id="9c89a-142">You can set up extra policies, such as requiring approved client apps.</span></span> <span data-ttu-id="9c89a-143">有关详细信息，请参阅条件 [访问文档](https://docs.microsoft.com/azure/active-directory/conditional-access/)。</span><span class="sxs-lookup"><span data-stu-id="9c89a-143">For more information, see the [Conditional Access documentation](https://docs.microsoft.com/azure/active-directory/conditional-access/).</span></span>
