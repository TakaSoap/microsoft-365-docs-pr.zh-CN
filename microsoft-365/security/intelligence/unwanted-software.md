---
title: 不需要的软件
ms.reviewer: ''
description: 了解不需要的软件如何在未经你的同意的情况下更改你的默认设置，以及你可以如何保护自己。
keywords: 安全， 恶意软件， 保护， 不需要， 软件， 更改， 感染， 不需要的软件， 软件捆绑程序， 浏览器修饰符， 隐私， 安全性， 计算体验， 防止感染， 解决方案， WDSI， MMPC， Microsoft 恶意软件防护中心， 病毒研究威胁， 研究恶意软件， 电脑保护， 计算机感染， 病毒感染， 说明， 修正， 最新威胁
ms.prod: m365-security
ms.mktglfcycl: secure
ms.sitesec: library
ms.localizationpriority: medium
ms.author: dansimp
author: dansimp
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
search.appverid: met150
ms.technology: m365d
ms.openlocfilehash: 94b3bad5b5653420d91cd422d40a0ff7802e6442
ms.sourcegitcommit: b3530441288b2bc44342e00e9025a49721796903
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/20/2022
ms.locfileid: "63683383"
---
# <a name="unwanted-software"></a>不需要的软件

不需要的软件是未经你的同意Windows更改用户体验的程序。 这有可能会修改浏览体验、对下载和安装的控制、误导性消息或未经授权更改Windows设置。

## <a name="how-unwanted-software-works"></a>不需要的软件的工作原理

当用户在 Internet 中搜索和下载应用程序时，可能会引入不需要的软件。 某些应用程序是软件捆绑程序，这意味着它们与其他应用程序打包在一起。 因此，在下载原始应用程序时，可能会无意中安装其他程序。

以下是不需要的软件的一些指示：

- 有一些程序未安装，并且可能难以卸载

- 浏览器功能或设置已更改，你无法查看或修改它们

- 有关设备运行状况或文件和程序的消息过多

- 有些广告无法轻松关闭

某些指示器更难识别，因为它们的干扰性较低，但仍不需要。 例如，不需要的软件可以修改网页以显示特定广告、监视浏览活动或删除对浏览器的控制。

Microsoft 使用广泛的 [评估标准](criteria.md) 来识别不需要的软件。

## <a name="how-to-protect-against-unwanted-software"></a>如何防止不需要的软件

为了防止不必要的软件感染，请仅从官方网站或网站下载Microsoft Store。 请保护从第三方网站下载软件。

在[Microsoft Edge](/microsoft-edge/deploy/index) Internet 时，请使用"安全"。 Microsoft Edge包括可有效阻止可更改浏览器设置的浏览器修饰符的其他保护。 Microsoft Edge还阻止使用 SmartScreen 或 Windows Defender 使用的 [SmartScreen](/microsoft-edge/deploy/index) (托管不需要的软件的已知Internet Explorer) 。

在[Microsoft Defender 防病毒](/microsoft-365/security/defender-endpoint/microsoft-defender-antivirus-in-windows-10)中Windows 10。 它提供实时威胁防护，并检测并删除已知的不需要的软件。

在 [Microsoft Security Essentials](https://www.microsoft.com/download/details.aspx?id=5201) 7 或 vista 中下载Windows实时Windows保护。

有关更多常规提示，请参阅 [防止恶意软件感染](prevent-malware-infection.md)。

### <a name="what-should-i-do-if-my-device-is-infected"></a>如果我的设备受到感染，该怎么办？ 

如果您怀疑您具有不需要的软件，您可以 [提交文件进行分析](https://www.microsoft.com/wdsi/filesubmission)。

一些不需要的软件会添加卸载条目，这意味着您可以使用 **设置**。
1. 选择"开始"按钮
2. 转到设置 >**应用>应用&功能**。
3. 选择要卸载的应用，然后单击"卸载 **"**。

如果你最近刚刚注意到不需要的软件感染症状，请考虑按安装日期对应用进行排序，然后卸载你未安装的最新应用。

您可能还需要删除 **浏览器中** 的浏览器加载项，如 Internet Explorer、Firefox 或 Chrome。

如果威胁删除不成功，请阅读关于恶意软件[检测和删除疑难解答问题。](https://support.microsoft.com/help/4466982/windows-10-troubleshoot-problems-with-detecting-and-removing-malware)