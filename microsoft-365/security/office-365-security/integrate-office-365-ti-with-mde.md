---
title: 将 Microsoft Defender for Office 365 Microsoft Defender for Endpoint 一起使用
f1.keywords:
- NOCSH
keywords: 集成， Microsoft Defender， Microsoft Defender for Endpoint
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.date: 06/10/2021
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
ms.openlocfilehash: e59f608a6f732f58002dfd2ff34666865ab23f3d
ms.sourcegitcommit: d904f04958a13a514ce10219ed822b9e4f74ca2d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/19/2021
ms.locfileid: "53028868"
---
# <a name="use-microsoft-defender-for-office-365-together-with-microsoft-defender-for-endpoint"></a>将 Microsoft Defender for Office 365 Microsoft Defender for Endpoint 一起使用

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


[Microsoft Defender for Office 365](defender-for-office-365.md)可以配置为与[Microsoft Defender for Endpoint 一起运行](/windows/security/threat-protection)。

将 Microsoft Defender for Office 365 Microsoft Defender for Endpoint 可帮助你的安全操作团队监视用户设备存在风险并快速采取措施。 例如，启用集成后，安全运营团队将能够看到受检测到的电子邮件潜在影响的设备，以及 Microsoft Defender for Endpoint 中为这些设备生成的最近警报数。

下图描述了启用 Microsoft Defender  for Endpoint 集成后"设备"选项卡的外观：

![启用 Microsoft Defender for Endpoint 后，你可以看到具有警报的设备列表。](../../media/fec928ea-8f0c-44d7-80b9-a2e0a8cd4e89.PNG)

在此例中，可以看到检测到的电子邮件的收件人有四个设备，一个设备具有警报。 单击设备的链接将在之前Microsoft 365 Defender (打开Microsoft Defender 安全中心) 。 [](../defender-endpoint/microsoft-defender-security-center.md)

> [!TIP]
> Microsoft 365 Defender门户将替换Microsoft Defender 安全中心。 请参阅[Microsoft Defender for Endpoint in Microsoft 365 Defender](../defender/microsoft-365-security-center-mde.md)。

## <a name="requirements"></a>要求

- 你的组织必须具有 Microsoft Defender for Office 365 (或 Office 365 E5) 和 Microsoft Defender for Endpoint。

- 您必须是全局管理员或具有安全管理员角色 (例如安全管理员) 分配Microsoft 365。  (请参阅["权限"Microsoft 365 Defender) ](permissions-in-the-security-and-compliance-center.md)

- 你必须有权访问 Explorer ([或实时检测) 。 ](threat-explorer.md)

## <a name="to-integrate-microsoft-defender-for-office-365-with-microsoft-defender-for-endpoint"></a>将 Microsoft Defender for Office 365与 Microsoft Defender for Endpoint 集成

将 Microsoft Defender for Office 365 与 Microsoft Defender for Endpoint 集成在 Defender for Endpoint 和 Defender for Office 365 中设置。

1. 作为全局管理员或安全管理员，转到 [https://security.microsoft.com](https://security.microsoft.com) 并登录。  (这会将你Microsoft 365 Defender门户.) 

2. 在导航窗格中，选择"电子邮件 **&协作** \> **资源管理器"。**

3. 在屏幕右上角，单击 **"MDE 设置"。**

4. 在 Microsoft Defender for Endpoint 连接对话框中 **，连接 Microsoft Defender for Endpoint。**

    :::image type="content" source="../../media/explorer-mdeconnection-dialognew.png" alt-text="MDE 连接":::

5. 转到应用Microsoft 365 Defender门户 [https://security.microsoft.com](https://security.microsoft.com) (。

6. 在导航栏中，选择 **"设置"。** 然后，在"常规 **"** 下，选择 **"高级功能"。**

7. 向下滚动到 **Office 365智能连接，** 然后打开该连接。

   ![Office 365威胁情报连接](../../media/mdatp-oatptoggle.png)

## <a name="related-articles"></a>相关文章

[威胁调查和响应功能在Office 365](office-365-ti.md)

[Microsoft Defender for Office 365](defender-for-office-365.md)

[Microsoft Defender for Endpoint](/windows/security/threat-protection)
