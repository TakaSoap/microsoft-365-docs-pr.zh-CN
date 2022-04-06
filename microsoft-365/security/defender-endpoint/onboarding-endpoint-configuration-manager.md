---
title: 使用 Microsoft Endpoint Configuration Manager 载入
description: 了解如何使用 Microsoft Defender for Endpoint Microsoft Endpoint Configuration Manager
keywords: 载入， 配置， 部署， 部署， 终结点配置管理器， Microsoft Defender for Endpoint， 集合创建， 终结点检测响应， 下一代保护， 攻击面减少， Microsoft 终结点配置管理器
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-endpointprotect
- m365solution-scenario
ms.custom: admindeeplinkDEFENDER
ms.topic: article
ms.technology: mde
ms.openlocfilehash: b8847fb9132ee037a3103bf86aabd14d21fb482f
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/25/2022
ms.locfileid: "64469418"
---
# <a name="onboarding-using-microsoft-endpoint-configuration-manager"></a>使用 Microsoft Endpoint Configuration Manager 载入

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 希望体验 Microsoft Defender for Endpoint？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)。

本文是部署指南的一部分，并作为示例载入方法。

在 [规划主题](deployment-strategy.md) 中，提供了多种方法将设备载入服务。 本主题介绍共同管理体系结构。

:::image type="content" source="images/co-management-architecture.png" alt-text="云本机体系结构" lightbox="images/co-management-architecture.png":::
*环境体系结构关系图*

尽管 Defender for Endpoint 支持载入各种终结点和工具，但本文并未涵盖它们。 有关使用其他受支持的部署工具和方法进行常规载入的信息，请参阅 [载入概述](onboarding.md)。

本主题指导用户：

- 步骤 1：Windows设备加入服务
- 步骤 2：为终结点功能配置 Defender

本载入指南将指导你完成在使用应用时需要执行Microsoft Endpoint Configuration Manager：

- **在 Microsoft Endpoint Configuration Manager**
- **使用 Microsoft Endpoint Configuration Manager 为终结点配置 Microsoft Defender Microsoft Endpoint Configuration Manager**

> [!NOTE]
> 此示例Windows仅涵盖所有设备。

## <a name="step-1-onboard-windows-devices-using-microsoft-endpoint-configuration-manager"></a>步骤 1：Windows设备载入Microsoft Endpoint Configuration Manager

### <a name="collection-creation"></a>集合创建

若要Windows设备载入Microsoft Endpoint Configuration Manager，部署可以面向现有集合，也可以创建一个新集合进行测试。

使用组策略或手动方法等工具载入不会在系统上安装任何代理。

在Microsoft Endpoint Configuration Manager控制台中，载入过程将配置为控制台中合规性设置的一部分。

只要 Configuration Manager 客户端继续从管理点接收此策略，接收此必需配置的任何系统都将保持该配置。

按照以下步骤使用 Microsoft Endpoint Configuration Manager。

1. 在Microsoft Endpoint Configuration Manager控制台中，导航到 **"资产"和"合规性\>概述"\>"设备集合"**。

    :::image type="content" source="images/configmgr-device-collections.png" alt-text="&quot;Microsoft Endpoint Configuration Manager向导1" lightbox="images/configmgr-device-collections.png":::

2. 右键单击 **设备集合，** 然后选择 **创建设备集合**。

    :::image type="content" source="images/configmgr-create-device-collection.png" alt-text="the Microsoft Endpoint Configuration Manager wizard2" lightbox="images/configmgr-create-device-collection.png":::

3. 提供" **名称"** 和 **"限制集合"**，然后选择"下一 **步"**。

    :::image type="content" source="images/configmgr-limiting-collection.png" alt-text="&quot;Microsoft Endpoint Configuration Manager向导3" lightbox="images/configmgr-limiting-collection.png":::

4. 选择 **"添加规则** "，然后选择" **查询规则"**。

    :::image type="content" source="images/configmgr-query-rule.png" alt-text="&quot;Microsoft Endpoint Configuration Manager向导4" lightbox="images/configmgr-query-rule.png":::

5. 单击 **"直接** 成员身份 **向导"** 上的"下一步"，然后单击" **编辑查询语句"**。

    :::image type="content" source="images/configmgr-direct-membership.png" alt-text="&quot;Microsoft Endpoint Configuration Manager向导5" lightbox="images/configmgr-direct-membership.png":::

6. 选择 **条件** ，然后选择星形图标。

    :::image type="content" source="images/configmgr-criteria.png" alt-text="&quot;Microsoft Endpoint Configuration Manager向导6" lightbox="images/configmgr-criteria.png":::

7. 将条件类型保留为 **简单值**，选择"操作系统 **-** 内部版本号"，运算符等于或大于值 **14393**，然后单击"确定 **"**。

    :::image type="content" source="images/configmgr-simple-value.png" alt-text="&quot;Microsoft Endpoint Configuration Manager向导7" lightbox="images/configmgr-simple-value.png":::

8. 选择 **"下一步** "和" **关闭"**。

    :::image type="content" source="images/configmgr-membership-rules.png" alt-text="&quot;Microsoft Endpoint Configuration Manager向导8" lightbox="images/configmgr-membership-rules.png":::

9. 选择 **下一步**。

    :::image type="content" source="images/configmgr-confirm.png" alt-text="&quot;Microsoft Endpoint Configuration Manager向导9" lightbox="images/configmgr-confirm.png":::

完成此任务后，你现在拥有一个设备集合，Windows环境中的所有终结点。

## <a name="step-2-configure-microsoft-defender-for-endpoint-capabilities"></a>步骤 2：为终结点功能配置 Microsoft Defender

本部分指导你在设备上使用 Microsoft Endpoint Configuration Manager 配置Windows功能：

- [**终结点检测和响应**](#endpoint-detection-and-response)
- [**下一代保护**](#next-generation-protection)
- [**攻击面减少**](#attack-surface-reduction)

### <a name="endpoint-detection-and-response"></a>终结点检测和响应

#### <a name="windows-10-and-windows-11"></a>Windows 10 和 Windows 11

从 Microsoft 365 Defender 门户`.onboarding`中，可以下载可用于在 System Center Configuration Manager 中创建策略的策略，并部署该策略以Windows 10 Windows 11设备。

1. 在"<a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender门户中，</a>选择"[设置"载入"](https://security.microsoft.com/preferences2/onboarding)。

2. 在"部署方法"下，选择支持的版本 **Microsoft Endpoint Configuration Manager**。

    :::image type="content" source="images/mdatp-onboarding-wizard.png" alt-text="the Microsoft Endpoint Configuration Manager wizard10" lightbox="images/mdatp-onboarding-wizard.png":::

3. 选择 **下载程序包**。

   :::image type="content" source="images/mdatp-download-package.png" alt-text="the Microsoft Endpoint Configuration Manager wizard11" lightbox="images/mdatp-download-package.png":::

4. 将程序包保存到可访问的位置。
5. In Microsoft Endpoint Configuration Manager， navigate to： **Assets and Compliance > Overview > Endpoint Protection > Microsoft Defender ATP Policies**.

6. 右键单击 **"Microsoft Defender ATP 策略"** ，然后选择 **"创建 Microsoft Defender ATP 策略"**。

    :::image type="content" source="images/configmgr-create-policy.png" alt-text="the Microsoft Endpoint Configuration Manager wizard12" lightbox="images/configmgr-create-policy.png":::

7. 输入名称和说明，确认 **已选择载入** ，然后选择下一 **步**。

    :::image type="content" source="images/configmgr-policy-name.png" alt-text="the Microsoft Endpoint Configuration Manager wizard13" lightbox="images/configmgr-policy-name.png":::

8. 单击"浏览"。

9. 从上面的步骤 4 导航到已下载文件的位置。

10. 单击“**下一步**”。
11. 使用相应的示例配置代理 (**"无** "或 **"所有文件类型)** "。

    :::image type="content" source="images/configmgr-config-settings.png" alt-text="配置设置1" lightbox="images/configmgr-config-settings.png":::

12. 选择"正常"或 (**"**) **遥测"** ，然后单击"下一步 **"**。

    :::image type="content" source="images/configmgr-telemetry.png" alt-text="配置设置2" lightbox="images/configmgr-telemetry.png":::

13. 验证配置，然后单击"下一 **步"**。

    :::image type="content" source="images/configmgr-verify-configuration.png" alt-text="配置设置3" lightbox="images/configmgr-verify-configuration.png":::

14. 向导 **完成后** ，单击"关闭"。

15. 在 Microsoft Endpoint Configuration Manager控制台中，右键单击刚创建的 Defender for Endpoint 策略，**然后选择部署。**

    :::image type="content" source="images/configmgr-deploy.png" alt-text="配置设置4" lightbox="images/configmgr-deploy.png":::

16. 在右侧面板上，选择之前创建的集合，然后单击"确定 **"**。

    :::image type="content" source="images/configmgr-select-collection.png" alt-text="配置设置5" lightbox="images/configmgr-select-collection.png":::

#### <a name="previous-versions-of-windows-client-windows-7-and-windows-81"></a>早期版本的 Windows Client (Windows 7 和 Windows 8.1) 

按照以下步骤标识 Defender for Endpoint Workspace ID 和工作区密钥，这是载入早期版本的 Windows。

1. 从Microsoft 365 Defender<a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">门户中，</a> \>  \>设置设备管理 (下选择") "。 

2. 在操作系统下，**Windows 7 SP1 和 8.1**。

3. 复制 **工作区 ID 和****工作区密钥并** 保存它们。 稍后将在过程中使用。

   :::image type="content" source="images/91b738e4b97c4272fd6d438d8c2d5269.png" alt-text="初始启用流程" lightbox="images/91b738e4b97c4272fd6d438d8c2d5269.png":::

4. 安装Microsoft Monitoring Agent (MMA) 。

   MMA 当前 (2019 年 1) 以下操作系统Windows支持：

   - 服务器 SKUS：Windows Server 2008 SP1 或更高版本
   - 客户端 SKUS：Windows 7 SP1 及更高版本

   MMA 代理将需要安装在Windows设备上。 若要安装代理，某些系统将需要下载客户体验更新和诊断[](https://support.microsoft.com/help/3080149/update-for-customer-experience-and-diagnostic-telemetry)遥测，以便使用 MMA 收集数据。 这些系统版本包括但不限于：

   - Windows 8.1
   - Windows 7
   - Windows Server 2016
   - Windows Server 2012 R2
   - Windows Server 2008 R2

   具体而言，Windows 7 SP1，必须安装以下修补程序：

   - 安装 [KB4074598](https://support.microsoft.com/help/4074598/windows-7-update-kb4074598)
   - 安装 .NET Framework [4.5](https://www.microsoft.com/download/details.aspx?id=30653) (或更高版本) [KB3154518](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the-net-framework)。 不要在同一个系统中同时安装这两者。

5. 如果使用代理连接到 Internet，请参阅配置代理设置部分。

完成后，你应该在一小时内在门户中看到已载入的终结点。

### <a name="next-generation-protection"></a>下一代保护

Microsoft Defender 防病毒是内置反恶意软件解决方案，为台式机、便携式计算机和服务器提供安全提供下一代防护。

1. 在Microsoft Endpoint Configuration Manager控制台中，**\> \> 导航到"资产和合规性概述Endpoint Protection反恶意软件策略"，\>** 然后选择"**创建反恶意软件策略"**。

   :::image type="content" source="images/9736e0358e86bc778ce1bd4c516adb8b.png" alt-text="反恶意软件策略" lightbox="images/9736e0358e86bc778ce1bd4c516adb8b.png":::

2. 选择 **计划扫描**、**扫描** 设置、**默认** 操作、**实时保护**、**排除** 设置、**高级**、威胁覆盖、**云保护** 服务 **和安全智能更新**，**然后选择确定。**

   :::image type="content" source="images/1566ad81bae3d714cc9e0d47575a8cbd.png" alt-text="下一代保护窗格 1" lightbox="images/1566ad81bae3d714cc9e0d47575a8cbd.png":::

    在某些行业或某些选择的企业中，客户可能对如何配置防病毒有特定需求。

    [快速扫描与完全扫描和自定义扫描](/windows/security/threat-protection/microsoft-defender-antivirus/scheduled-catch-up-scans-microsoft-defender-antivirus#quick-scan-versus-full-scan-and-custom-scan)

    有关详细信息，请参阅配置[Windows 安全中心框架](/windows/security/threat-protection/windows-security-configuration-framework/windows-security-configuration-framework)。
  
    :::image type="content" source="images/cd7daeb392ad5a36f2d3a15d650f1e96.png" alt-text="下一代保护窗格 2" lightbox="images/cd7daeb392ad5a36f2d3a15d650f1e96.png":::

    :::image type="content" source="images/36c7c2ed737f2f4b54918a4f20791d4b.png" alt-text="下一代保护窗格3" lightbox="images/36c7c2ed737f2f4b54918a4f20791d4b.png":::

    :::image type="content" source="images/a28afc02c1940d5220b233640364970c.png" alt-text="下一代保护窗格4" lightbox="images/a28afc02c1940d5220b233640364970c.png":::

    :::image type="content" source="images/5420a8790c550f39f189830775a6d4c9.png" alt-text="下一代保护窗格5" lightbox="images/5420a8790c550f39f189830775a6d4c9.png":::

    :::image type="content" source="images/33f08a38f2f4dd12a364f8eac95e8c6b.png" alt-text="下一代保护窗格6" lightbox="images/33f08a38f2f4dd12a364f8eac95e8c6b.png":::

    :::image type="content" source="images/41b9a023bc96364062c2041a8f5c344e.png" alt-text="下一代保护窗格7" lightbox="images/41b9a023bc96364062c2041a8f5c344e.png":::

    :::image type="content" source="images/945c9c5d66797037c3caeaa5c19f135c.png" alt-text="下一代保护窗格8" lightbox="images/945c9c5d66797037c3caeaa5c19f135c.png":::

    :::image type="content" source="images/3876ca687391bfc0ce215d221c683970.png" alt-text="下一代保护窗格9" lightbox="images/3876ca687391bfc0ce215d221c683970.png":::

3. 右键单击新创建的反恶意软件策略，**然后选择部署。**

    :::image type="content" source="images/f5508317cd8c7870627cb4726acd5f3d.png" alt-text="下一代保护窗格10" lightbox="images/f5508317cd8c7870627cb4726acd5f3d.png":::

4. 将新的反恶意软件策略定向到 Windows 集合，然后单击"确定 **"**。

    :::image type="content" source="images/configmgr-select-collection.png" alt-text="下一代保护窗格11" lightbox="images/configmgr-select-collection.png":::

完成此任务后，现在可以成功配置Windows Defender 防病毒。

### <a name="attack-surface-reduction"></a>攻击面减少

适用于终结点的 Defender 的攻击面减少支柱包括攻击防护下提供的功能集。 攻击面减少 (ASR) 规则、受控文件夹访问权限、网络保护和 Exploit Protection。

所有这些功能都提供审核模式和阻止模式。 在审核模式下，对最终用户没有影响。 它所执行的所有操作是收集其他遥测，并使其在 Microsoft 365 Defender 门户中可用。 部署的目标是将安全控件分步移动到阻止模式。

在审核模式下设置 ASR 规则：

1. 在 Microsoft Endpoint Configuration Manager 控制台中，**\> \> 导航到"资产和合规性概述"Endpoint Protection \> Windows Defender攻击防护"**，然后选择"**创建攻击防护策略"**。

   :::image type="content" source="images/728c10ef26042bbdbcd270b6343f1a8a.png" alt-text="Microsoft Endpoint Configuration Manager控制台 0" lightbox="images/728c10ef26042bbdbcd270b6343f1a8a.png":::

2. 选择 **攻击面减少**。

3. 将规则设置为 **"审核"，** 然后单击"下一 **步"**。

   :::image type="content" source="images/d18e40c9e60aecf1f9a93065cb7567bd.png" alt-text="控制台Microsoft Endpoint Configuration Manager 1" lightbox="images/d18e40c9e60aecf1f9a93065cb7567bd.png":::

4. 通过单击"下一步"确认新的攻击 **防护策略**。

   :::image type="content" source="images/0a6536f2c4024c08709cac8fcf800060.png" alt-text="控制台Microsoft Endpoint Configuration Manager 2" lightbox="images/0a6536f2c4024c08709cac8fcf800060.png":::

5. 创建策略后，单击"关闭 **"**。

   :::image type="content" source="images/95d23a07c2c8bc79176788f28cef7557.png" alt-text="Microsoft Endpoint Configuration Manager控制台 3" lightbox="images/95d23a07c2c8bc79176788f28cef7557.png":::

6. 右键单击新创建的策略，**然后选择部署。**

   :::image type="content" source="images/8999dd697e3b495c04eb911f8b68a1ef.png" alt-text="控制台Microsoft Endpoint Configuration Manager 4" lightbox="images/8999dd697e3b495c04eb911f8b68a1ef.png":::

7. 将策略定向到新创建的 Windows 集合，然后单击"确定 **"**。

   :::image type="content" source="images/0ccfe3e803be4b56c668b220b51da7f7.png" alt-text="the Microsoft Endpoint Configuration Manager console5" lightbox="images/0ccfe3e803be4b56c668b220b51da7f7.png":::

完成此任务后，现在可以在审核模式下成功配置 ASR 规则。

下面是验证 ASR 规则是否已正确应用到终结点的其他步骤。  (这可能需要几分钟) 

1. 在 Web 浏览器中，转到"Microsoft 365 Defender<a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">"</a>。

2. 从 **左侧菜单中选择** 配置管理。

3. 单击 **攻击面管理面板中的** 转到攻击面管理。

   :::image type="content" source="images/security-center-attack-surface-mgnt-tile.png" alt-text="攻击面管理" lightbox="images/security-center-attack-surface-mgnt-tile.png":::

4. 单击 **攻击面** 减少规则报告中的"配置"选项卡。 它显示每台设备的 ASR 规则配置概述和 ASR 规则状态。

   :::image type="content" source="images/f91f406e6e0aae197a947d3b0e8b2d0d.png" alt-text="攻击面减少规则报告1" lightbox="images/f91f406e6e0aae197a947d3b0e8b2d0d.png":::

5. 单击每台设备可显示 ASR 规则的配置详细信息。

   :::image type="content" source="images/24bfb16ed561cbb468bd8ce51130ca9d.png" alt-text="攻击面减少规则报告2" lightbox="images/24bfb16ed561cbb468bd8ce51130ca9d.png":::

有关 [更多详细信息，请参阅优化 ASR 规则](/microsoft-365/security/defender-endpoint/configure-machines-asr) 部署和检测。

#### <a name="set-network-protection-rules-in-audit-mode"></a>在审核模式下设置网络保护规则

1. 在 Microsoft Endpoint Configuration Manager 控制台中，**\> \> 导航到"资产和合规性概述"Endpoint Protection \> Windows Defender攻击防护"**，然后选择"**创建攻击防护策略"**。

   :::image type="content" source="images/728c10ef26042bbdbcd270b6343f1a8a.png" alt-text="System Center Configuration Manager1" lightbox="images/728c10ef26042bbdbcd270b6343f1a8a.png":::

2. 选择 **"网络保护"**。

3. 将设置设置为" **审核"，** 然后单击"下一 **步"**。

   :::image type="content" source="images/c039b2e05dba1ade6fb4512456380c9f.png" alt-text="System Center Configuration Manager2" lightbox="images/c039b2e05dba1ade6fb4512456380c9f.png":::

4. 通过单击"下一步"确认新的攻击 **防护策略**。

   :::image type="content" source="images/0a6536f2c4024c08709cac8fcf800060.png" alt-text="攻击防护策略1" lightbox="images/0a6536f2c4024c08709cac8fcf800060.png":::

5. 创建策略后，单击"关闭 **"**。

   :::image type="content" source="images/95d23a07c2c8bc79176788f28cef7557.png" alt-text="攻击防护策略 2" lightbox="images/95d23a07c2c8bc79176788f28cef7557.png":::

6. 右键单击新创建的策略，**然后选择部署。**

   :::image type="content" source="images/8999dd697e3b495c04eb911f8b68a1ef.png" alt-text="the Microsoft Endpoint Configuration Manager-1" lightbox="images/8999dd697e3b495c04eb911f8b68a1ef.png":::

7. 选择新创建的组策略Windows选择"确定 **"**。

   :::image type="content" source="images/0ccfe3e803be4b56c668b220b51da7f7.png" alt-text="Microsoft Endpoint Configuration Manager-2" lightbox="images/0ccfe3e803be4b56c668b220b51da7f7.png":::

完成此任务后，现在可以在审核模式下成功配置网络保护。

#### <a name="to-set-controlled-folder-access-rules-in-audit-mode"></a>在审核模式下设置受控文件夹访问权限规则

1. 在 Microsoft Endpoint Configuration Manager 控制台中，导航到"资产和 **合规性** > **""** > 查看 **Endpoint Protection** >  **Windows Defender攻击防护**"，然后选择"**创建攻击防护策略"**。

   :::image type="content" source="images/728c10ef26042bbdbcd270b6343f1a8a.png" alt-text="Microsoft Endpoint Configuration Manager-3" lightbox="images/728c10ef26042bbdbcd270b6343f1a8a.png":::

2. 选择 **受控文件夹访问权限**。

3. 将配置设置为" **审核"，** 然后单击"下一 **步"**。

   :::image type="content" source="images/a8b934dab2dbba289cf64fe30e0e8aa4.png" alt-text="The Microsoft Endpoint Configuration Manager-4" lightbox="images/a8b934dab2dbba289cf64fe30e0e8aa4.png":::

4. 通过单击"下一步"确认新的攻击防护 **策略**。

   :::image type="content" source="images/0a6536f2c4024c08709cac8fcf800060.png" alt-text="Microsoft Endpoint Configuration Manager-5" lightbox="images/0a6536f2c4024c08709cac8fcf800060.png":::

5. 创建策略后，单击"关闭 **"**。

   :::image type="content" source="images/95d23a07c2c8bc79176788f28cef7557.png" alt-text="the Microsoft Endpoint Configuration Manager-6" lightbox="images/95d23a07c2c8bc79176788f28cef7557.png":::

6. 右键单击新创建的策略，**然后选择部署。**

   :::image type="content" source="images/8999dd697e3b495c04eb911f8b68a1ef.png" alt-text="The Microsoft Endpoint Configuration Manager-7" lightbox="images/8999dd697e3b495c04eb911f8b68a1ef.png":::


7. 将策略定向到新创建的 Windows 集合，然后单击"确定 **"**。


:::image type="content" source="images/0ccfe3e803be4b56c668b220b51da7f7.png" alt-text="the Microsoft Endpoint Configuration Manager-8" lightbox="images/0ccfe3e803be4b56c668b220b51da7f7.png":::

现在，你已成功在审核模式下配置受控文件夹访问权限。

## <a name="related-topic"></a>相关主题

- [使用 Microsoft Endpoint Manager 载入](onboarding-endpoint-manager.md)
