---
title: 将 Microsoft Defender for Office 365 与 Microsoft Defender for Endpoint 一同使用
f1.keywords:
- NOCSH
keywords: integrate， Microsoft Defender， ATP
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.date: 01/21/2021
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
description: 将适用于 Office 365 的 Microsoft Defender 与 Microsoft Defender for Endpoint 一起用于获取有关针对设备和电子邮件内容的威胁的更多详细信息。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 24b81bb4c445c44d7c0228fa1c4440faff642816
ms.sourcegitcommit: ba830e85899f247e5a1e117d63e09e4d5b8a8020
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/22/2021
ms.locfileid: "49939328"
---
# <a name="use-microsoft-defender-for-office-365-together-with-microsoft-defender-for-endpoint"></a>将 Microsoft Defender for Office 365 与 Microsoft Defender for Endpoint 一同使用

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


[Microsoft Defender for Office 365](office-365-atp.md) 可以配置为与 [Microsoft Defender for Endpoint 一起工作](https://docs.microsoft.com/windows/security/threat-protection)。

将 Microsoft Defender for Office 365 与 Microsoft Defender for Endpoint 集成可帮助你的安全操作团队在用户设备存在风险时监视并快速采取措施。 例如，启用集成后，安全运营团队将能够查看受检测到的电子邮件潜在影响的设备，以及 Microsoft Defender for Endpoint 中为这些设备生成的最近警报数。

下图描述了"设备"选项卡启用Microsoft Defender for Endpoint 集成后的外观：

![启用 Microsoft Defender for Endpoint 后，你可以看到具有警报的设备列表。](../../media/fec928ea-8f0c-44d7-80b9-a2e0a8cd4e89.PNG)

在此例中，可以看到检测到的电子邮件的收件人具有四台设备，一个设备具有警报。 单击设备的链接将在 Microsoft Defender 安全中心 <https://securitycenter.windows.com> () 。

> [!TIP]
> **[了解有关 Microsoft Defender 安全中心](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/use)** (也称为 Microsoft Defender for Endpoint 门户。) 

## <a name="requirements"></a>要求

- 你的组织必须具有 Microsoft Defender for Office 365 (Office 365 E5) 和 Microsoft Defender for Endpoint。

- 您必须是全局管理员或具有安全管理员角色 (例如安全) 安全与合规中心& [管理员](https://protection.office.com)。  (安全[与合规中心&权限) ](permissions-in-the-security-and-compliance-center.md)

- 你必须在安全与 ([和 ](threat-explorer.md) Microsoft Defender 安全中心) 资源管理器&或实时检测。

## <a name="to-integrate-microsoft-defender-for-office-365-with-microsoft-defender-for-endpoint"></a>将 Microsoft Defender for Office 365 与 Microsoft Defender for Endpoint 集成

将 Microsoft Defender for Office 365 与 Microsoft Defender for Endpoint 集成是通过使用安全与合规中心& Microsoft Defender 安全中心设置的。

1. 作为全局管理员或安全管理员，请转到 <https://protection.office.com> 并登录。  (这会将你带至 Office 365 安全&合规中心.) 

2. 在导航窗格中，选择 **"威胁管理** \> **资源管理器"。**

   !["威胁管理"菜单中的资源管理器](../../media/ThreatMgmt-Explorer-nav.png)

3. In the upper right corner of the screen， choose **Defender for Endpoint Settings (MDE Settings) .**

4. 在 Microsoft Defender for Endpoint 连接对话框中，打开 **"连接到适用于终结点的 Microsoft Defender"。**

   ![Microsoft Defender for Endpoint 连接](../../media/Explorer-WDATPConnection-dialog.png)

5. 转到 Microsoft Defender 安全中心 <https://securitycenter.windows.com> () 。

6. 在导航栏中，选择"**设置"。** 然后，在 **"常规"** 下，**选择"高级功能"。**

7. 向下滚动到 **Office 365 威胁智能连接**，然后打开该连接。

   ![Office 365 威胁情报连接](../../media/mdatp-oatptoggle.png)

## <a name="related-articles"></a>相关文章

[Office 365 中的威胁调查和响应功能](office-365-ti.md)

[Microsoft Defender for Office 365](office-365-atp.md)

[Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection)
