---
title: 使用 QR 代码登录到 Outlook移动应用
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
description: 了解如何使用 QR 代码在移动设备上进行身份验证和Outlook下载。
ms.openlocfilehash: a403fbbed90229300e707653062c552104c47d97
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/03/2021
ms.locfileid: "53286701"
---
# <a name="use-a-qr-code-to-sign-in-to-the-outlook-mobile-apps"></a><span data-ttu-id="dfd3e-103">使用 QR 代码登录到 Outlook移动应用</span><span class="sxs-lookup"><span data-stu-id="dfd3e-103">Use a QR code to sign-in to the Outlook mobile apps</span></span>

> [!IMPORTANT]
> <span data-ttu-id="dfd3e-104">此功能仅适用于已在此版本中打开定向发布Microsoft 365 管理中心。</span><span class="sxs-lookup"><span data-stu-id="dfd3e-104">This feature is only available to organizations that have turned on Targeted Release in the Microsoft 365 admin center.</span></span> <span data-ttu-id="dfd3e-105">若要打开定向发布并了解其工作方式的详细信息，请参阅 [设置标准或定向发布选项](release-options-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="dfd3e-105">To turn on Targeted release and learn more about how it works, see [Set up the Standard or Targeted release options](release-options-in-office-365.md).</span></span> <span data-ttu-id="dfd3e-106">未来几周内，我们将通过公共预览版扩展到更多组织。</span><span class="sxs-lookup"><span data-stu-id="dfd3e-106">We’ll be expanding to more organizations in the coming weeks through public preview.</span></span> <span data-ttu-id="dfd3e-107">公共预览版可提前访问Microsoft 365功能。</span><span class="sxs-lookup"><span data-stu-id="dfd3e-107">Public preview provides early access to Microsoft 365 features.</span></span>

<span data-ttu-id="dfd3e-108">作为Microsoft 365管理员，你可以让用户登录到 Outlook for Android 或 iOS 应用，而无需输入用户名和密码。</span><span class="sxs-lookup"><span data-stu-id="dfd3e-108">As the Microsoft 365 administrator, you can enable your users to sign in to Outlook for Android or iOS app on their mobile devices without having to enter their username and password.</span></span> <span data-ttu-id="dfd3e-109">通过扫描 QR 代码，用户可以安全地进行身份验证并登录到Outlook登录。</span><span class="sxs-lookup"><span data-stu-id="dfd3e-109">By scanning a QR code, users can securely authenticate and sign in to Outlook mobile.</span></span>

<span data-ttu-id="dfd3e-110">在Outlook 网页版或其他桌面Outlook应用程序中，用户可能会看到通知，通知他们可在Outlook设备上使用桌面设备。</span><span class="sxs-lookup"><span data-stu-id="dfd3e-110">In Outlook on the web or other desktop Outlook applications, users may see notifications informing them that they can use Outlook on their mobile device.</span></span> <span data-ttu-id="dfd3e-111">管理员可以使用 Powershell 管理Exchange通知。</span><span class="sxs-lookup"><span data-stu-id="dfd3e-111">These notifications can be managed by the administrator using Exchange Powershell.</span></span> <span data-ttu-id="dfd3e-112">如果用户选择向自己发送短信以在移动设备上下载应用，QR 代码将显示在其计算机上。</span><span class="sxs-lookup"><span data-stu-id="dfd3e-112">If users choose to send themselves an SMS text message to download the app on their mobile device, a QR code will appear on their computer.</span></span> <span data-ttu-id="dfd3e-113">他们将能够扫描 QR 代码，以登录到Outlook或平板电脑上的设备。</span><span class="sxs-lookup"><span data-stu-id="dfd3e-113">They will be able to scan the QR code to log into Outlook on their phone or tablet.</span></span> <span data-ttu-id="dfd3e-114">此 QR 代码是只能兑换一次短期令牌。</span><span class="sxs-lookup"><span data-stu-id="dfd3e-114">This QR code is a short lived token that can only be redeemed once.</span></span>

> [!NOTE]
> <span data-ttu-id="dfd3e-115">在某些情况下，用户必须重新验证其计算机以生成 QR 代码。</span><span class="sxs-lookup"><span data-stu-id="dfd3e-115">In some cases, your users must re-authenticate on their computer to generate the QR code.</span></span>

## <a name="use-exchange-powershell"></a><span data-ttu-id="dfd3e-116">使用 Exchange PowerShell</span><span class="sxs-lookup"><span data-stu-id="dfd3e-116">Use Exchange PowerShell</span></span>

<span data-ttu-id="dfd3e-117">默认情况下，启用此功能。</span><span class="sxs-lookup"><span data-stu-id="dfd3e-117">This feature is on by default.</span></span> <span data-ttu-id="dfd3e-118">若要禁用此功能，请按照以下步骤操作。</span><span class="sxs-lookup"><span data-stu-id="dfd3e-118">To disable this feature, follow the steps below.</span></span>

1. <span data-ttu-id="dfd3e-119">[连接 PowerShell Exchange 。](/powershell/exchange/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="dfd3e-119">[Connect to Exchange PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>
2. <span data-ttu-id="dfd3e-120">使用 PowerShell，可以禁用通知用户有关Outlook通知。</span><span class="sxs-lookup"><span data-stu-id="dfd3e-120">Using PowerShell, you can disable the notifications informing your users about the Outlook mobile apps.</span></span> <span data-ttu-id="dfd3e-121">这还会阻止显示 QR 代码登录流。</span><span class="sxs-lookup"><span data-stu-id="dfd3e-121">This also prevents the QR code sign-in flow from being shown.</span></span>

```powershell
Set-OrganizationConfig -MobileAppEducationEnabled <Boolean>
```

## <a name="related-content"></a><span data-ttu-id="dfd3e-122">相关内容</span><span class="sxs-lookup"><span data-stu-id="dfd3e-122">Related content</span></span>

<span data-ttu-id="dfd3e-123">[设置标准发布选项或定向发布 (](release-options-in-office-365.md) 文章) </span><span class="sxs-lookup"><span data-stu-id="dfd3e-123">[Set up the Standard or Targeted release options](release-options-in-office-365.md) (article)</span></span>\
<span data-ttu-id="dfd3e-124">[Set-OrganizationConfig](/powershell/module/exchange/set-organizationconfig) (文章) </span><span class="sxs-lookup"><span data-stu-id="dfd3e-124">[Set-OrganizationConfig](/powershell/module/exchange/set-organizationconfig) (article)</span></span>