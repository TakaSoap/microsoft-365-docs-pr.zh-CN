---
title: 配置 S/MIME 设置 - 适用于 Web 上的 Outlook 的 Exchange Online
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c7dee22c-9b5b-425c-91a9-d093204ff84e
ms.collection:
- M365-security-compliance
description: 有关 Exchange Online 管理员在 Exchange Online 中查看和配置 Outlook 网页版中的 S/MIME 设置所需执行的操作的简短描述。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 9acd7d4523754c1e07ece8fb0344d9f888c0ee3d
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "46825697"
---
# <a name="configure-smime-settings-in-exchange-online-for-outlook-on-the-web"></a>为 Outlook 网页版配置 Exchange Online 中的 S/MIME 设置

作为 Exchange Online 管理员，可以从以前称为Outlook Web App) 设置 Outlook (网页版应用，以允许发送和接收受 S/MIME 保护的邮件。 在 Exchange Online PowerShell 中使用**Get-SmimeConfig 和 Set-SmimeConfig** cmdlet 来查看和管理此功能。 **Get-SmimeConfig** 若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)。

有关语法和参数的详细信息，请参阅[Get-SmimeConfig](https://docs.microsoft.com/powershell/module/exchange/get-smimeconfig)和[Set-SmimeConfig。](https://docs.microsoft.com/powershell/module/exchange/set-smimeconfig)

## <a name="considerations-for-new-microsoft-edge-chromium-based"></a>新的 Microsoft Edge 基于 Chromium (的注意事) 

若要在[新的 Microsoft Edge](https://www.microsoft.com/windows/microsoft-edge) Web 浏览器中使用 Outlook 网页版中的 S/MIME，必须设置 (或其他管理员) 才能在**ExtensionInstallForcelist**新的 Microsoft Edge 中安装 Microsoft S/MIME 扩展。 策略值为 `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx` 。 另请注意，应用此策略要求已加入域或已加入 Azure AD 的设备，因此在新的 Microsoft Edge 浏览器中使用 S/MIME 可有效地需要已加入域或加入 Azure AD 的设备。

有关**ExtensionInstallForcelist 策略的详细信息，** 请参阅[ExtensionInstallForcelist。](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#extensioninstallforcelist)

此步骤是使用新 Microsoft Edge 的先决条件;不替换用户安装的 S/MIME 控件。 在用户首次使用 S/MIME 期间，会提示用户在 Web 上的 Outlook 中下载和安装 S/MIME 控件。 或者，用户可以主动转到其 Outlook 网页版设置中的 **S/MIME，** 以获取此控件的下载链接。

## <a name="considerations-for-chrome"></a>Chrome 的注意事项

若要在 Google Chrome Web 浏览器的 Outlook 网页版中使用 S/MIME，必须将 (或其他管理员) 设置为 Set and configure the Chromium policy named **ExtensionInstallForcelist** 以在 Chrome 中安装 Microsoft S/MIME 扩展。 策略值为 `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx` 。 请注意，应用此策略需要加入域的计算机，因此在 Chrome 中使用 S/MIME 实际上需要加入域的计算机。

有关**ExtensionInstallForcelist 策略的详细信息，** 请参阅[ExtensionInstallForcelist。](https://cloud.google.com/docs/chrome-enterprise/policies/?policy=ExtensionInstallForcelist)

此步骤是使用 Chrome 的先决条件;不替换用户安装的 S/MIME 控件。 在用户首次使用 S/MIME 期间，会提示用户在 Web 上的 Outlook 中下载和安装 S/MIME 控件。 或者，用户可以主动转到其 Outlook 网页版设置中的 **S/MIME，** 以获取此控件的下载链接。

## <a name="for-more-information"></a>详细信息

[邮件签名和加密的 S/MIME](s-mime-for-message-signing-and-encryption.md)
