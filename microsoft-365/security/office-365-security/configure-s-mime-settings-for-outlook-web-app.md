---
title: 配置 S/MIME 设置 - Exchange Online for Outlook 网页版
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c7dee22c-9b5b-425c-91a9-d093204ff84e
ms.collection:
- M365-security-compliance
description: 简要说明 Exchange Online 管理员在 Exchange Online 的 Outlook 网页版中查看和配置 S/MIME 设置需要执行哪些操作。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a81db5ec933f1d0d6e2944103be53c0169dde62f
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/09/2021
ms.locfileid: "50165675"
---
# <a name="configure-smime-settings-in-exchange-online-for-outlook-on-the-web"></a><span data-ttu-id="feba9-103">在 Exchange Online 中为 Outlook 网页版配置 S/MIME 设置</span><span class="sxs-lookup"><span data-stu-id="feba9-103">Configure S/MIME settings in Exchange Online for Outlook on the web</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="feba9-104">**适用于**</span><span class="sxs-lookup"><span data-stu-id="feba9-104">**Applies to**</span></span>
- [<span data-ttu-id="feba9-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="feba9-105">Exchange Online Protection</span></span>](https://go.microsoft.com/fwlink/?linkid=2148611)
- [<span data-ttu-id="feba9-106">Microsoft Defender for Office 365 计划 1 和计划 2</span><span class="sxs-lookup"><span data-stu-id="feba9-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)
- [<span data-ttu-id="feba9-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="feba9-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="feba9-108">作为 Exchange Online 的管理员，您可以设置 Outlook 网页版 (以前称为 Outlook Web App) ，以允许发送和接收受 S/MIME 保护的邮件。</span><span class="sxs-lookup"><span data-stu-id="feba9-108">As an admin for Exchange Online, you can set up Outlook on the web (formerly known as Outlook Web App) to allow sending and receiving S/MIME-protected messages.</span></span> <span data-ttu-id="feba9-109">使用 **Get-SmimeConfig** 和 **Set-SmimeConfig** cmdlet 在 Exchange Online PowerShell 中查看和管理此功能。</span><span class="sxs-lookup"><span data-stu-id="feba9-109">Use the **Get-SmimeConfig** and **Set-SmimeConfig** cmdlets to view and manage this feature in Exchange Online PowerShell.</span></span> <span data-ttu-id="feba9-110">若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="feba9-110">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

<span data-ttu-id="feba9-111">有关语法和参数的详细信息，请参阅[Get-SmimeConfig](https://docs.microsoft.com/powershell/module/exchange/get-smimeconfig)和[Set-SmimeConfig。](https://docs.microsoft.com/powershell/module/exchange/set-smimeconfig)</span><span class="sxs-lookup"><span data-stu-id="feba9-111">For detailed syntax and parameter information, see [Get-SmimeConfig](https://docs.microsoft.com/powershell/module/exchange/get-smimeconfig) and [Set-SmimeConfig](https://docs.microsoft.com/powershell/module/exchange/set-smimeconfig).</span></span>

## <a name="considerations-for-new-microsoft-edge-chromium-based"></a><span data-ttu-id="feba9-112">基于 Chromium 的新 Microsoft Edge (的注意事项) </span><span class="sxs-lookup"><span data-stu-id="feba9-112">Considerations for new Microsoft Edge (Chromium-based)</span></span>

<span data-ttu-id="feba9-113">若要在新的 [Microsoft Edge](https://www.microsoft.com/windows/microsoft-edge) Web 浏览器中使用 Outlook 网页中的 S/MIME， (或其他管理员) 必须设置和配置名为 **ExtensionInstallForcelist** 的 Microsoft Edge 浏览器策略，才能在新的 Microsoft Edge 中安装 Microsoft S/MIME 扩展。</span><span class="sxs-lookup"><span data-stu-id="feba9-113">To use S/MIME in Outlook on the web in the new [Microsoft Edge](https://www.microsoft.com/windows/microsoft-edge) web browser, you (or another admin) must set and configure the Microsoft Edge browser policy named **ExtensionInstallForcelist** to install the Microsoft S/MIME extension in the new Microsoft Edge.</span></span> <span data-ttu-id="feba9-114">策略值为 `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx` 。</span><span class="sxs-lookup"><span data-stu-id="feba9-114">The policy value is `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx`.</span></span> <span data-ttu-id="feba9-115">请注意，应用此策略需要加入域或加入 Azure AD 的设备，因此，在新的 Microsoft Edge 浏览器中使用 S/MIME 需要加入域或加入 Azure AD 的设备。</span><span class="sxs-lookup"><span data-stu-id="feba9-115">And note that applying this policy requires domain-joined or Azure AD-joined devices, so using S/MIME in the new Microsoft Edge browser effectively requires domain-joined or Azure AD-joined devices.</span></span>

<span data-ttu-id="feba9-116">有关 **ExtensionInstallForcelist** 策略的详细信息，请参阅 [ExtensionInstallForcelist](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#extensioninstallforcelist)。</span><span class="sxs-lookup"><span data-stu-id="feba9-116">For details about the **ExtensionInstallForcelist** policy, see [ExtensionInstallForcelist](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#extensioninstallforcelist).</span></span>

<span data-ttu-id="feba9-117">此步骤是使用新 Microsoft Edge 的先决条件;它不会替换用户安装的 S/MIME 控件。</span><span class="sxs-lookup"><span data-stu-id="feba9-117">This step is a prerequisite for using new Microsoft Edge; it does not replace the S/MIME control that's installed by users.</span></span> <span data-ttu-id="feba9-118">用户首次使用 S/MIME 时，系统会提示用户在 Outlook 网页中下载和安装 S/MIME 控件。</span><span class="sxs-lookup"><span data-stu-id="feba9-118">Users are prompted to download and install the S/MIME control in Outlook on the web during their first use of S/MIME.</span></span> <span data-ttu-id="feba9-119">或者，用户可以在 Outlook 网页设置中主动转到 **S/MIME，** 获取控件的下载链接。</span><span class="sxs-lookup"><span data-stu-id="feba9-119">Or, users can proactively go to **S/MIME** in their Outlook on the web settings to get the download link for the control.</span></span>

## <a name="considerations-for-chrome"></a><span data-ttu-id="feba9-120">Chrome 的注意事项</span><span class="sxs-lookup"><span data-stu-id="feba9-120">Considerations for Chrome</span></span>

<span data-ttu-id="feba9-121">若要在 Google Chrome Web 浏览器的 Outlook 网页版中使用 S/MIME， (或其他管理员) 必须设置和配置名为 **ExtensionInstallForcelist** 的 Chromium 策略，才能在 Chrome 中安装 Microsoft S/MIME 扩展。</span><span class="sxs-lookup"><span data-stu-id="feba9-121">To use S/MIME in Outlook on the web in the Google Chrome web browser, you (or another admin) must set and configure the Chromium policy named **ExtensionInstallForcelist** to install the Microsoft S/MIME extension in Chrome.</span></span> <span data-ttu-id="feba9-122">策略值为 `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx` 。</span><span class="sxs-lookup"><span data-stu-id="feba9-122">The policy value is `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx`.</span></span> <span data-ttu-id="feba9-123">请注意，应用此策略需要加入域的计算机，因此在 Chrome 中有效地使用 S/MIME 需要加入域的计算机。</span><span class="sxs-lookup"><span data-stu-id="feba9-123">And note that applying this policy requires domain-joined computers, so using S/MIME in Chrome effectively requires domain-joined computers.</span></span>

<span data-ttu-id="feba9-124">有关 **ExtensionInstallForcelist** 策略的详细信息，请参阅 [ExtensionInstallForcelist](https://cloud.google.com/docs/chrome-enterprise/policies/?policy=ExtensionInstallForcelist)。</span><span class="sxs-lookup"><span data-stu-id="feba9-124">For details about the **ExtensionInstallForcelist** policy, see [ExtensionInstallForcelist](https://cloud.google.com/docs/chrome-enterprise/policies/?policy=ExtensionInstallForcelist).</span></span>

<span data-ttu-id="feba9-125">此步骤是使用 Chrome 的先决条件;它不会替换用户安装的 S/MIME 控件。</span><span class="sxs-lookup"><span data-stu-id="feba9-125">This step is a prerequisite for using Chrome; it does not replace the S/MIME control that's installed by users.</span></span> <span data-ttu-id="feba9-126">用户首次使用 S/MIME 时，系统会提示用户在 Outlook 网页中下载和安装 S/MIME 控件。</span><span class="sxs-lookup"><span data-stu-id="feba9-126">Users are prompted to download and install the S/MIME control in Outlook on the web during their first use of S/MIME.</span></span> <span data-ttu-id="feba9-127">或者，用户可以在 Outlook 网页设置中主动转到 **S/MIME，** 获取控件的下载链接。</span><span class="sxs-lookup"><span data-stu-id="feba9-127">Or, users can proactively go to **S/MIME** in their Outlook on the web settings to get the download link for the control.</span></span>

## <a name="for-more-information"></a><span data-ttu-id="feba9-128">更多详细信息</span><span class="sxs-lookup"><span data-stu-id="feba9-128">For more information</span></span>

[<span data-ttu-id="feba9-129">邮件签名和加密的 S/MIME</span><span class="sxs-lookup"><span data-stu-id="feba9-129">S/MIME for message signing and encryption</span></span>](s-mime-for-message-signing-and-encryption.md)
