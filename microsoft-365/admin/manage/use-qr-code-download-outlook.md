---
title: 使用 QR 代码登录到 Outlook 移动应用
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
description: 了解如何使用 QR 代码对 Outlook 移动版进行身份验证和下载。
ms.openlocfilehash: 2d62a49b93fa7bd5f2d747525de7244e8014e6a7
ms.sourcegitcommit: b8e9b2ecdc4927b67088c5fffb1585424c66fb10
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2021
ms.locfileid: "50050768"
---
# <a name="use-a-qr-code-to-sign-in-to-the-outlook-mobile-apps"></a><span data-ttu-id="c02c1-103">使用 QR 代码登录到 Outlook 移动应用</span><span class="sxs-lookup"><span data-stu-id="c02c1-103">Use a QR code to sign-in to the Outlook mobile apps</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c02c1-104">此 Microsoft 365 功能为公共预览版。</span><span class="sxs-lookup"><span data-stu-id="c02c1-104">This Microsoft 365 feature is in public preview.</span></span> <span data-ttu-id="c02c1-105">公共预览版提供对 Microsoft 365 功能的早期访问。</span><span class="sxs-lookup"><span data-stu-id="c02c1-105">Public preview provides early access to Microsoft 365 features.</span></span>

<span data-ttu-id="c02c1-106">作为 Microsoft 365 管理员，您可以允许用户登录到其移动设备上的 Outlook for Android 或 iOS 应用，而无需输入用户名和密码。</span><span class="sxs-lookup"><span data-stu-id="c02c1-106">As the Microsoft 365 administrator, you can enable your users to sign in to Outlook for Android or iOS app on their mobile devices without having to enter their username and password.</span></span> <span data-ttu-id="c02c1-107">通过扫描 QR 代码，用户可以安全地进行身份验证并登录到 Outlook Mobile。</span><span class="sxs-lookup"><span data-stu-id="c02c1-107">By scanning a QR code, users can securely authenticate and sign in to Outlook mobile.</span></span>

<span data-ttu-id="c02c1-108">在 Outlook 网页版或其他桌面 Outlook 应用程序中，用户可能会看到通知，通知他们可以在移动设备上使用 Outlook。</span><span class="sxs-lookup"><span data-stu-id="c02c1-108">In Outlook on the web or other desktop Outlook applications, users may see notifications informing them that they can use Outlook on their mobile device.</span></span> <span data-ttu-id="c02c1-109">管理员可以使用 Exchange Powershell 管理这些通知。</span><span class="sxs-lookup"><span data-stu-id="c02c1-109">These notifications can be managed by the administrator using Exchange Powershell.</span></span> <span data-ttu-id="c02c1-110">如果用户选择向自己发送短信以在移动设备上下载应用，则 QR 代码将显示在其计算机上。</span><span class="sxs-lookup"><span data-stu-id="c02c1-110">If users choose to send themselves an SMS text message to download the app on their mobile device, a QR code will appear on their computer.</span></span> <span data-ttu-id="c02c1-111">他们将能够扫描 QR 代码以登录到其手机或平板电脑上的 Outlook。</span><span class="sxs-lookup"><span data-stu-id="c02c1-111">They will be able to scan the QR code to log into Outlook on their phone or tablet.</span></span> <span data-ttu-id="c02c1-112">此 QR 代码是只能兑换一次短期令牌。</span><span class="sxs-lookup"><span data-stu-id="c02c1-112">This QR code is a short lived token that can only be redeemed once.</span></span>

> [!NOTE]
> <span data-ttu-id="c02c1-113">在某些情况下，用户必须在计算机上重新进行身份验证，以生成 QR 代码。</span><span class="sxs-lookup"><span data-stu-id="c02c1-113">In some cases, your users will have to re-authenticate on their computer to generate the QR code.</span></span>

## <a name="use-exchange-powershell"></a><span data-ttu-id="c02c1-114">使用 Exchange PowerShell</span><span class="sxs-lookup"><span data-stu-id="c02c1-114">Use Exchange PowerShell</span></span>

<span data-ttu-id="c02c1-115">默认情况下，此体验为打开状态。</span><span class="sxs-lookup"><span data-stu-id="c02c1-115">This experience is on by default.</span></span> <span data-ttu-id="c02c1-116">若要禁用此功能，请按照以下步骤操作。</span><span class="sxs-lookup"><span data-stu-id="c02c1-116">To disable this feature, follow the steps below.</span></span>

1. <span data-ttu-id="c02c1-117">[连接到 Exchange PowerShell。](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps)</span><span class="sxs-lookup"><span data-stu-id="c02c1-117">[Connect to Exchange PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps).</span></span>
2. <span data-ttu-id="c02c1-118">使用 PowerShell，可以禁用通知用户有关 Outlook 移动应用的通知。</span><span class="sxs-lookup"><span data-stu-id="c02c1-118">Using PowerShell, you can disable the notifications informing your users about the Outlook mobile apps.</span></span> <span data-ttu-id="c02c1-119">这还会阻止显示 QR 代码登录流。</span><span class="sxs-lookup"><span data-stu-id="c02c1-119">This will also prevent the QR code sign-in flow from being shown.</span></span>

```powershell
Set-Organization -MobileAppEducationEnabled <Boolean>
```

<span data-ttu-id="c02c1-120">相关主题</span><span class="sxs-lookup"><span data-stu-id="c02c1-120">Related topics</span></span>

[<span data-ttu-id="c02c1-121">Set-OrganizationConfig</span><span class="sxs-lookup"><span data-stu-id="c02c1-121">Set-OrganizationConfig</span></span>](https://docs.microsoft.com/powershell/module/exchange/set-organizationconfig?view=exchange-ps)