---
title: 在生产环境中为 Microsoft Defender Office 365评估环境
description: 激活 Microsoft Defender 进行Office 365评估的步骤，包括试用许可证、MX 记录处理、&接受域和入站连接的审核。
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
ms.date: 07/01/2021
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-evalutatemtp
ms.topic: how-to
ms.technology: m365d
ms.openlocfilehash: 4d2f77b41dccd5620b96d816869d7d7b6458a798
ms.sourcegitcommit: 6f3bc00a5cf25c48c61eb3835ac069e9f41dc4db
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2022
ms.locfileid: "62172171"
---
# <a name="enable-the-evaluation-environment"></a>启用评估环境

**适用于：**
- Microsoft 365 Defender

本文是设置 Microsoft Defender for Office 365 评估环境过程中的第 2 步（第[3](eval-defender-office-365-overview.md) Office 365）。 有关此过程详细信息，请参阅 [概述文章](eval-defender-office-365-overview.md)。

使用以下步骤启用 Microsoft Defender for Office 365。

![在 Microsoft Defender 评估Office 365启用 Microsoft Defender for Office 365的步骤。](../../media/defender/m365-defender-office-eval-enable-steps.png)

- [步骤 1：激活试用许可证](#step-1-activate-trial-licenses)
- [步骤 2：审核和验证公共 MX 记录](#step-2-audit-and-verify-the-public-mx-record)
- [步骤 3：审核接受的域](#step-3-audit-accepted-domains)
- [步骤 4：审核入站连接器](#step-4-audit-inbound-connectors)
- [步骤 5：激活评估](#step-5-activate-the-evaluation)

## <a name="step-1-activate-trial-licenses"></a>步骤 1：激活试用许可证

登录到现有 Microsoft Defender for Office 365或租户管理门户。

1. 导航到管理门户。
2. 从快速启动中选择"购买服务"。

   :::image type="content" source="../../media/mdo-eval/1_m365-purchase-services.png" alt-text="单击导航窗格上的&quot;购买服务&quot;Office 365。":::

3. 向下滚动到"Add-On"部分 (或搜索"Defender") 找到 Microsoft Defender for Office 365 计划。
4. 单击要评估的计划旁边的"详细信息"。

   :::image type="content" source="../../media/mdo-eval/2_mdo-eval-license-details.png" alt-text="单击&quot;详细信息&quot;按钮，下一步。":::

5. 单击" *开始免费试用"* 链接。

   :::image type="content" source="../../media/mdo-eval/3-m365-purchase-button.png" alt-text="单击此面板上的&quot;开始免费试用 *超链接*&quot;。":::

6. 确认请求并单击"立即 *尝试"* 按钮。

   :::image type="content" source="../../media/mdo-eval/4_mdo-trial-order.png" alt-text="现在，单击&quot;立即尝试 *&quot;按钮*。":::

## <a name="step-2-audit-and-verify-the-public-mx-record"></a>步骤 2：审核和验证公共 MX 记录

若要有效评估 Microsoft Defender Office 365，通过与租户关联的 Exchange Online Protection (EOP) 中继入站外部电子邮件非常重要。

1. 登录到 M365 管理门户，展开"设置"，然后选择"域"。
2. 选择已验证的电子邮件域，然后单击"管理 DNS"。
3. 记下生成并分配给 EOP 租户的 MX 记录。
4. 访问外部 (公共) DNS 区域，并检查与您的电子邮件域关联的主 MX 记录。
    - *如果公共 MX 记录当前与分配的 EOP* 地址相匹配 (例如 tenant-com.mail.protection.outlook.com) ，则不需要进一步路由更改。
    - 如果公共 MX 记录当前解析为第三方或本地 SMTP 网关，可能需要其他路由配置。
    - 如果公共 MX 记录当前解析为本地Exchange则您可能仍在混合模型中，其中某些收件人邮箱尚未迁移到 EXO。

## <a name="step-3-audit-accepted-domains"></a>步骤 3：审核接受的域

1. 登录管理Exchange Online，选择"邮件Flow"，然后单击"接受域"。
2. 在租户中添加并验证的接受域列表中，记下 **主电子邮件域** 的域类型。
    - 如果域类型设置为 ***"*** 权威"，则假定组织的所有收件人邮箱当前都位于Exchange Online。
    - 如果域类型设置为" ***内部*** 中继"，则您可能仍在混合模型中，其中某些收件人邮箱仍驻留在本地。

## <a name="step-4-audit-inbound-connectors"></a>步骤 4：审核入站连接器

1. 登录管理Exchange Online，选择"邮件Flow"，然后单击"连接器"。
2. 从配置的连接器列表中，记下来自合作伙伴组织且可能与第三方 SMTP 网关关联的任何条目。
3. 从已配置的连接器列表中，记下组织的电子邮件服务器中标记的任何条目，这些条目可能指示你仍处于混合方案。

## <a name="step-5-activate-the-evaluation"></a>步骤 5：激活评估

按照此处的说明从 microsoft Defender 门户Office 365 Microsoft Defender Microsoft 365 Defender评估。

1. 使用有权访问租户门户的帐户登录到Microsoft 365 Defender门户。
2. 选择是否要将 Microsoft 365 Defender 门户作为 Microsoft Defender 的默认界面，Office 365管理 (推荐) 。

   :::image type="content" source="../../media/mdo-eval/1_mdo-eval-activate-eval.png" alt-text="单击&quot;打开设置&quot;按钮以使用集中式和改进Microsoft 365 Defender门户进行管理。":::

3. 从导航菜单中，选择电子邮件 **&协作** 下的策略 *&规则*。

   :::image type="content" source="../../media/mdo-eval/2_mdo-eval-activate-eval.png" alt-text="下面是指向策略和&的电子邮件协作菜单&图片。单击该按钮！":::

4. 在策略策略 *&仪表板* 上，单击威胁 **策略**。

   :::image type="content" source="../../media/mdo-eval/3_mdo-eval-activate-eval.png" alt-text="策略策略策略&仪表板的图片和指向威胁策略的箭头。单击下一步！":::

5. 向下滚动到"*其他策略"，* 然后选择"**评估 Defender Office 365** 磁贴。

   :::image type="content" source="../../media/mdo-eval/4_mdo-eval-activate-eval.png" alt-text="Eval Defender for Office 365磁贴显示这是电子邮件和协作矢量的 30 &试用版。单击浏览。":::

6. 现在，选择外部电子邮件Exchange Online直接路由到第三方网关还是服务，然后单击"下一步"。

   :::image type="content" source="../../media/mdo-eval/5_mdo-eval-activate-eval.png" alt-text="Defender for Office 365将评估发送到你的邮箱Exchange Online邮件。提供现在如何路由邮件的详细信息，包括路由邮件的出站连接器的名称。如果您仅Exchange Online Protection (EOP) 您将没有连接器。选择我使用第三方或本地提供商之一，或者我仅使用 EOP。":::

7. 如果使用第三方网关，请从下拉列表中选择供应商名称以及与该解决方案关联的入站连接器。 列出答案后，单击"下一步"。

   :::image type="content" source="../../media/mdo-eval/6-mdo-eval-activate-eval-settings.png" alt-text="在此对话框中，选择组织使用的第三方供应商服务，或选择&quot;*其他*&quot;。下一个对话框中，选择入站连接器。然后单击&quot;下一步&quot;。":::

8. 查看设置并单击"创建 **评估"** 按钮。

   |活动前|活动后|
   |:---:|:---:|
   |:::image type="content" source="../../media/mdo-eval/7-mdo-eval-activate-review.png" alt-text="此窗格有一个下拉列表，用于查看你的设置。如果需要，它还具有&quot;编辑路由类型&quot;的可单击链接。准备好后，单击大蓝色&quot;创建评估&quot;按钮。":::|:::image type="content" source="../../media/mdo-eval/8-mdo-eval-activate-complete.png" alt-text="现在设置已完成。此页面上的蓝色按钮显示&quot;转到评估&quot;。":::|
   |

## <a name="next-steps"></a>后续步骤

步骤 3/3：设置 Microsoft Defender for Office 365

返回到评估 Microsoft [Defender](eval-defender-office-365-overview.md) for Office 365

返回到评估和试点[计划概述Microsoft 365 Defender](eval-overview.md)
