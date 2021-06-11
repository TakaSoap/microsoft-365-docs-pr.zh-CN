---
title: 将 Microsoft Defender for Office 365 Microsoft Defender for Endpoint 一起使用
f1.keywords:
- NOCSH
keywords: 集成， Microsoft Defender， Microsoft Defender for Endpoint
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
description: 将 Microsoft Defender for Office 365与 Microsoft Defender for Endpoint 一起，获取有关针对你的设备和电子邮件内容的威胁的更多详细信息。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 3f1d92d2433267b89398c7f7f582a8d1ee8cdba5
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/10/2021
ms.locfileid: "52878600"
---
# <a name="use-microsoft-defender-for-office-365-together-with-microsoft-defender-for-endpoint"></a>将 Microsoft Defender for Office 365 Microsoft Defender for Endpoint 一起使用

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


[Microsoft Defender for Office 365](defender-for-office-365.md)可以配置为与[Microsoft Defender for Endpoint 一起运行](/windows/security/threat-protection)。

将 Microsoft Defender for Office 365 Microsoft Defender for Endpoint 可帮助你的安全操作团队监视用户设备存在风险并快速采取措施。 例如，启用集成后，安全运营团队将能够看到受检测到的电子邮件潜在影响的设备，以及 Microsoft Defender for Endpoint 中为这些设备生成的最近警报数。

下图描述了启用 Microsoft Defender  for Endpoint 集成后"设备"选项卡的外观：

![启用 Microsoft Defender for Endpoint 后，你可以看到具有警报的设备列表。](../../media/fec928ea-8f0c-44d7-80b9-a2e0a8cd4e89.PNG)

在此例中，可以看到检测到的电子邮件的收件人有四个设备，一个设备具有警报。 单击设备的链接将打开设备在 <https://securitycenter.windows.com> Microsoft Defender 安全中心 () 。

> [!TIP]
> **[详细了解也称为Microsoft Defender 安全中心 (](/windows/security/threat-protection/microsoft-defender-atp/use)** Microsoft Defender for Endpoint 门户的 ) 

## <a name="requirements"></a>要求

- 你的组织必须具有 Microsoft Defender for Office 365 (或 Office 365 E5) 和 Microsoft Defender for Endpoint。

- 您必须是全局管理员或具有安全管理员角色 (例如安全) 安全与合规& [分配的安全管理员](https://protection.office.com)。  (请参阅 [安全与合规中心&中的权限](permissions-in-the-security-and-compliance-center.md)) 

- 你必须能够访问[安全中心 (安全与合规](threat-explorer.md)) 中的 Explorer & 或实时Microsoft Defender 安全中心。

## <a name="to-integrate-microsoft-defender-for-office-365-with-microsoft-defender-for-endpoint"></a>将 Microsoft Defender for Office 365与 Microsoft Defender for Endpoint 集成

将 Microsoft Defender for Office 365 与 Microsoft Defender for Endpoint 集成是通过使用安全与合规&和 Microsoft Defender 安全中心。

1. 作为全局管理员或安全管理员，转到 <https://protection.office.com> 并登录。  (这会将你Office 365安全&中心。) 

2. 在导航窗格中，选择"**威胁管理资源管理器** \> **"。**

   ![威胁管理菜单中的资源管理器](../../media/ThreatMgmt-Explorer-nav.png)

3. In the upper right corner of the screen， choose **Defender for Endpoint 设置 (MDE 设置)**.

4. 在 Microsoft Defender for Endpoint 连接对话框中 **，连接 Microsoft Defender for Endpoint。**

   ![Microsoft Defender for Endpoint 连接](../../media/Explorer-WDATPConnection-dialog.png)

5. 转到 <https://securitycenter.windows.com> Microsoft Defender 安全中心 () 。

6. 在导航栏中，选择 **"设置"。** 然后，在"常规 **"** 下，选择 **"高级功能"。**

7. 向下滚动到 **Office 365智能连接，** 然后打开该连接。

   ![Office 365威胁情报连接](../../media/mdatp-oatptoggle.png)

## <a name="related-articles"></a>相关文章

[威胁调查和响应功能在Office 365](office-365-ti.md)

[Microsoft Defender for Office 365](defender-for-office-365.md)

[Microsoft Defender for Endpoint](/windows/security/threat-protection)
