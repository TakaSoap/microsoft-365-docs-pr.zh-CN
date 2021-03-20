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
ms.openlocfilehash: 6ab1aaabf0e7651a5a84642c178c28961430eea0
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50906476"
---
# <a name="configure-smime-settings-in-exchange-online-for-outlook-on-the-web"></a>在 Exchange Online 中为 Outlook 网页版配置 S/MIME 设置

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用对象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 计划 1 和计划 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

作为 Exchange Online 的管理员，你可以设置 Outlook 网页版 (以前称为 Outlook Web App) ，以允许发送和接收受 S/MIME 保护的邮件。 使用 **Get-SmimeConfig** 和 **Set-SmimeConfig** cmdlet 在 Exchange Online PowerShell 中查看和管理此功能。 若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。

有关语法和参数的详细信息，请参阅[Get-SmimeConfig](/powershell/module/exchange/get-smimeconfig)和[Set-SmimeConfig。](/powershell/module/exchange/set-smimeconfig)

## <a name="considerations-for-new-microsoft-edge-chromium-based"></a>基于 Chromium 的新 Microsoft Edge (的注意事项) 

若要在新的 [Microsoft Edge](https://www.microsoft.com/windows/microsoft-edge) Web 浏览器中使用 Outlook 网页中的 S/MIME， (或其他管理员) 必须设置和配置名为 **ExtensionInstallForcelist** 的 Microsoft Edge 浏览器策略，才能在新的 Microsoft Edge 中安装 Microsoft S/MIME 扩展。 策略值为 `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx` 。 请注意，应用此策略需要加入域或加入 Azure AD 的设备，因此，在新的 Microsoft Edge 浏览器中有效地使用 S/MIME 需要加入域或加入 Azure AD 的设备。

有关 **ExtensionInstallForcelist** 策略的详细信息，请参阅 [ExtensionInstallForcelist](/DeployEdge/microsoft-edge-policies#extensioninstallforcelist)。

此步骤是使用新 Microsoft Edge 的先决条件;它不会替换用户安装的 S/MIME 控件。 用户首次使用 S/MIME 时，系统会提示用户在 Outlook 网页中下载和安装 S/MIME 控件。 或者，用户可以在 Outlook 网页设置中主动转到 **S/MIME，** 获取控件的下载链接。

## <a name="considerations-for-chrome"></a>Chrome 的注意事项

若要在 Google Chrome Web 浏览器的 Outlook 网页版中使用 S/MIME， (或其他管理员) 必须设置和配置名为 **ExtensionInstallForcelist** 的 Chromium 策略，才能在 Chrome 中安装 Microsoft S/MIME 扩展。 策略值为 `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx` 。 请注意，应用此策略需要加入域的计算机，因此在 Chrome 中有效地使用 S/MIME 需要加入域的计算机。

有关 **ExtensionInstallForcelist** 策略的详细信息，请参阅 [ExtensionInstallForcelist](https://cloud.google.com/docs/chrome-enterprise/policies/?policy=ExtensionInstallForcelist)。

此步骤是使用 Chrome 的先决条件;它不会替换用户安装的 S/MIME 控件。 用户首次使用 S/MIME 时，系统会提示用户在 Outlook 网页中下载和安装 S/MIME 控件。 或者，用户可以在 Outlook 网页设置中主动转到 **S/MIME，** 获取控件的下载链接。

## <a name="for-more-information"></a>详细信息

[邮件签名和加密的 S/MIME](s-mime-for-message-signing-and-encryption.md)