---
title: 不需要的软件
ms.reviewer: ''
description: 了解不需要的软件如何在未经你同意的情况下更改默认设置，以及如何保护自己。
keywords: 安全，恶意软件，保护，不需要，软件，更改，感染，不需要的软件，软件捆绑程序，浏览器修饰符，隐私，安全，计算经验，防止感染，解决方案，WDSI，MMPC，Microsoft 恶意软件防护中心，病毒研究威胁，研究恶意软件，电脑保护，计算机感染，病毒感染，说明，修正，最新威胁
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
ms.openlocfilehash: 654730571de934552d983e1135f24a3299567741
ms.sourcegitcommit: 85ce5fd0698b6f00ea1ea189634588d00ea13508
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/06/2022
ms.locfileid: "64666671"
---
# <a name="unwanted-software"></a>不需要的软件

不需要的软件是未经许可或控制更改Windows体验的程序。 这可以采用修改后的浏览体验、对下载和安装缺乏控制、误导性消息或未经授权更改Windows设置的形式。

## <a name="how-unwanted-software-works"></a>不需要的软件的工作原理

当用户从 Internet 搜索和下载应用程序时，可以引入不需要的软件。 某些应用程序是软件捆绑程序，这意味着它们已打包到其他应用程序中。 因此，下载原始应用程序时可能会无意中安装其他程序。

下面是不需要的软件的一些指示：

- 有些程序未安装，可能难以卸载

- 浏览器功能或设置已更改，无法查看或修改它们

- 有关设备运行状况或文件和程序的过多消息

- 有些广告无法轻松关闭

某些指标更难识别，因为它们的破坏性较低，但仍不需要。 例如，不需要的软件可以修改网页以显示特定广告、监视浏览活动或删除对浏览器的控制。

Microsoft 使用广泛的 [评估条件](criteria.md) 来识别不需要的软件。

## <a name="how-to-protect-against-unwanted-software"></a>如何防范不需要的软件

若要防止不需要的软件感染，请仅从官方网站或Microsoft Store下载软件。 警惕从第三方网站下载软件。

浏览 Internet 时使用[Microsoft Edge](/microsoft-edge/deploy/index)。 Microsoft Edge包含可有效阻止浏览器修饰符以更改浏览器设置的其他保护。 Microsoft Edge还阻止使用 Internet Explorer [) 使用的Windows Defender SmartScreen](/microsoft-edge/deploy/index) (托管不需要软件的已知网站。

在[Windows 10](/microsoft-365/security/defender-endpoint/microsoft-defender-antivirus-in-windows-10)中启用Microsoft Defender 防病毒。 它提供针对威胁的实时保护，并检测和删除已知不需要的软件。

在 Vista [Windows](https://www.microsoft.com/download/details.aspx?id=5201) 7 或Windows下载用于实时保护的Microsoft Security Essentials。

有关更多常规提示，请参阅 [防止恶意软件感染](prevent-malware-infection.md)。

### <a name="what-should-i-do-if-my-device-is-infected"></a>如果我的设备被感染，我该怎么办？ 

如果你怀疑自己有不需要的软件，可以 [提交文件进行分析](https://www.microsoft.com/wdsi/filesubmission)。

某些不需要的软件添加卸载条目，这意味着可以 **使用设置将其删除**。
1. 选择"开始"按钮
2. 转到 **设置 >应用>应用&功能**。
3. 选择要卸载的应用，然后单击 **"卸载**"。

如果你最近才注意到不需要的软件感染症状，请考虑按安装日期对应用进行排序，然后卸载未安装的最新应用。

可能还需要 **删除浏览器中的浏览器加载项** ，例如 Internet Explorer、Firefox 或 Chrome。

如果威胁删除不成功，请阅读有关 [恶意软件检测和删除问题的疑难解答](https://support.microsoft.com/help/4466982/windows-10-troubleshoot-problems-with-detecting-and-removing-malware)。