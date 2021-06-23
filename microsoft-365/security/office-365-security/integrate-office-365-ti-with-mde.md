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
ms.openlocfilehash: fed3a04a7a699b4689cd9d6d9d335a8ba51d2fd8
ms.sourcegitcommit: cd55fe6abe25b1e4f5fbe8295d3a99aebd97ce66
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/23/2021
ms.locfileid: "53083375"
---
# <a name="use-microsoft-defender-for-office-365-together-with-microsoft-defender-for-endpoint"></a>将 Microsoft Defender for Office 365 Microsoft Defender for Endpoint 一起使用

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


[Microsoft Defender for Office 365](defender-for-office-365.md)可以配置为与[Microsoft Defender for Endpoint 一起运行](/windows/security/threat-protection)。

将 Microsoft Defender for Office 365 Microsoft Defender for Endpoint 可帮助你的安全操作团队监视用户设备存在风险并快速采取措施。 例如，启用集成后，安全运营团队将能够看到受检测到的电子邮件潜在影响的设备，以及 Microsoft Defender for Endpoint 中为这些设备生成的最近警报数。

下图描述了启用 Microsoft Defender  for Endpoint 集成后"设备"选项卡的外观：

![启用 Microsoft Defender for Endpoint 后，你可以看到具有警报的设备列表。](../../media/fec928ea-8f0c-44d7-80b9-a2e0a8cd4e89.PNG)

在此例中，可以看到检测到的电子邮件的收件人有四个设备，一个设备具有警报。 单击设备的链接将在之前 Microsoft Defender[](../defender-endpoint/microsoft-defender-security-center.md)安全Microsoft 365 Defender门户 (打开其) 。

> [!TIP]
> Microsoft 365 Defender门户将替换Microsoft Defender 安全中心。 请参阅[Microsoft Defender for Endpoint in Microsoft 365 Defender](../defender/microsoft-365-security-center-mde.md)。

## <a name="requirements"></a>Requirements

- 你的组织必须具有 Microsoft Defender for Office 365 (或 Office 365 E5) 和 Microsoft Defender for Endpoint。

- 您必须是全局管理员或具有安全管理员角色 (例如安全管理员) 分配Microsoft 365。 有关详细信息，请参阅 [Microsoft 365 Defender 门户中的权限](permissions-microsoft-365-security-center.md)。

- 你必须有权访问 Explorer ([或实时检测) 。 ](threat-explorer.md)

## <a name="to-integrate-microsoft-defender-for-office-365-with-microsoft-defender-for-endpoint"></a>将 Microsoft Defender for Office 365与 Microsoft Defender for Endpoint 集成

将 Microsoft Defender for Office 365 与 Microsoft Defender for Endpoint 集成在 Defender for Endpoint 和 Defender for Office 365 中设置。

1. 作为全局管理员或安全管理员，打开 Microsoft 365 Defender 门户 () 转到"电子邮件& <https://security.microsoft.com> **协作** \> **资源管理器"。** 若要直接转到资源管理器 **页面** ，请使用 <https://security.microsoft.com/threatexplorer> 。

2. 在 **"资源管理器**"页上的屏幕右上角，单击 **"MDE 设置"。**

3. 在出现的 **Microsoft Defender for Endpoint** 连接飞出中，在 连接 上打开"适用于终结点的 Microsoft **Defender** (切换") ![ ](../../media/scc-toggle-on.png) 然后单击关闭图标"关闭 ![ ](../../media/m365-cc-sc-close-icon.png) **"。**

    :::image type="content" source="../../media/explorer-mdeconnection-dialognew.png" alt-text="MDE 连接":::

4. 返回到导航窗格中，选择 **"设置"。** 在 **"设置"** 页上，选择 **"终结点"**

5. 在打开 **的"终结点**"页上，选择"**高级功能"。**

6. 向下滚动到 **"Office 365** 智能"连接，然后打开" (![ 上的 ](../../media/scc-toggle-on.png) ") "。

   完成后，单击保存 **首选项**。

## <a name="related-articles"></a>相关文章

[威胁调查和响应功能在Office 365](office-365-ti.md)

[Microsoft Defender for Office 365](defender-for-office-365.md)

[Microsoft Defender for Endpoint](/windows/security/threat-protection)
