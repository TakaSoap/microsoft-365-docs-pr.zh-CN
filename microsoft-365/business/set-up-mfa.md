---
title: 设置多重身份验证
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- MiniMaven
- MSB365
- OKR_SMB_M365
search.appverid:
- BCS160
- MET150
description: 为 Microsoft 365 商业版设置多重身份验证。
ms.openlocfilehash: 59a3ff7a9494ccfc44fa701c6f605a9bd9eeafcf
ms.sourcegitcommit: 5d11f516e78ea4a74145e19ba2300f0792c8bac1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/19/2019
ms.locfileid: "38715054"
---
# <a name="multi-factor-authentication"></a><span data-ttu-id="26115-103">多重身份验证</span><span class="sxs-lookup"><span data-stu-id="26115-103">Multi-factor authentication</span></span>

<span data-ttu-id="26115-104">多重身份验证（MFA）要求用户使用另一种方法登录，以使用电话呼叫或验证器应用验证其身份。</span><span class="sxs-lookup"><span data-stu-id="26115-104">Multi-factor authentication (MFA) requires users to sign in with a second method to verify their identity with a phone call or with an authenticator app.</span></span>

## <a name="set-up-mfa-in-the-microsoft-365-admin-center"></a><span data-ttu-id="26115-105">在 Microsoft 365 管理中心中设置 MFA</span><span class="sxs-lookup"><span data-stu-id="26115-105">Set up MFA in the Microsoft 365 admin center</span></span>

<span data-ttu-id="26115-106">[![显示管理中心正在更改且你可在 aka.ms/aboutM365preview 找到更多详细信息的标签。](media/m365admincenterchanging.png)](https://docs.microsoft.com/office365/admin/microsoft-365-admin-center-preview)</span><span class="sxs-lookup"><span data-stu-id="26115-106">[![Label to let you know the admin center is changing and you can find more details at aka.ms/aboutM365preview.](media/m365admincenterchanging.png)](https://docs.microsoft.com/office365/admin/microsoft-365-admin-center-preview)</span></span>

1. <span data-ttu-id="26115-107">使用全局管理员凭据登录到[Microsoft 365 管理中心](https://admin.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="26115-107">Sign in to [Microsoft 365 admin center](https://admin.microsoft.com) by using your global admin credentials.</span></span> 
2. <span data-ttu-id="26115-108">在左侧导航中，选择 "**设置**"。</span><span class="sxs-lookup"><span data-stu-id="26115-108">On the left nav, choose **Setup**.</span></span>
3. <span data-ttu-id="26115-109">在 "安装程序" 页上，选择 "**启用多重身份验证（MFA）** " 卡上的 "**查看**"。</span><span class="sxs-lookup"><span data-stu-id="26115-109">On the Setup page, choose **View** on the **Turn on multi-factor authentication (MFA)** card.</span></span>
4. <span data-ttu-id="26115-110">在 "**启用 mfa** " 页上，选择 "**开始**"，或 "**管理**" （如果你已设置 MFA 并想要进行更改）。</span><span class="sxs-lookup"><span data-stu-id="26115-110">On the **Turn on MFA** page, choose **Get started**, or **Manage** if you have already set up MFA and want to make changes.</span></span> 

  <span data-ttu-id="26115-111">:::image type="content" source="media/turnonmfa.png" alt-text="启用 MFA 页面的屏幕截图。":::</span><span class="sxs-lookup"><span data-stu-id="26115-111">:::image type="content" source="media/turnonmfa.png" alt-text="Screenshot of turn on MFA page.":::</span></span>

5. <span data-ttu-id="26115-112">在 "**加强登录安全**" 面板上，选中 "**需要管理员的多因素身份验证**" 或 "**创建策略**"。</span><span class="sxs-lookup"><span data-stu-id="26115-112">On the **Strengthen sign-in security** panel, check both or one of **Require multi-factor authentication for admins**, and then choose **Create policy**.</span></span>
