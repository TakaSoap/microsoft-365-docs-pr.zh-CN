---
title: 使用 Microsoft Endpoint Manager 载入
description: 了解如何使用 Microsoft Defender for Endpoint Microsoft Endpoint Manager
keywords: 载入， 配置， 部署， 部署， 终结点管理器， Microsoft Defender for Endpoint， 集合创建， 终结点检测响应， 下一代保护， 攻击面减少， Microsoft 终结点管理器
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-endpointprotect
- m365solution-scenario
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 75bbf7e0d121a7d0ed71124179367243e8aff777
ms.sourcegitcommit: d78553deeba23d2f8238f10e64c2e27f235dc37f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/05/2021
ms.locfileid: "60124801"
---
# <a name="onboarding-using-microsoft-endpoint-manager"></a>使用 Microsoft Endpoint Manager 载入

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


> 希望体验 Microsoft Defender for Endpoint？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)。

本文是部署指南的一部分，并作为示例载入方法。

在 [规划主题](deployment-strategy.md) 中，提供了多种方法将设备载入服务。 本主题介绍云本机体系结构。

![云本机体系结构的图像。 ](images/cloud-native-architecture.png)
*环境体系结构关系图*

尽管 Defender for Endpoint 支持载入各种终结点和工具，但本文并未涵盖它们。 有关使用其他受支持的部署工具和方法进行常规载入的信息，请参阅 [载入概述](onboarding.md)。

[Microsoft Endpoint Manager](/mem/endpoint-manager-overview)是统一多个服务的解决方案平台。 它包括[Microsoft Intune](/mem/intune/fundamentals/what-is-intune)基于云的设备管理。

本主题指导用户：

- 步骤 1：在 MEM 中通过创建组将设备载入服务Microsoft Endpoint Manager () 分配配置
- 步骤 2：使用 Microsoft Endpoint Manager

本载入指南将指导你完成在使用应用时需要执行Microsoft Endpoint Manager：

- [标识目标设备或用户](#identify-target-devices-or-users)
  - 创建用户Azure Active Directory设备 (组) 
- [创建配置文件](#step-2-create-configuration-policies-to-configure-microsoft-defender-for-endpoint-capabilities)
  - 在Microsoft Endpoint Manager中，我们将指导你为每种功能创建单独的策略。

## <a name="resources"></a>资源

以下是此过程的其余部分所需的链接：

- [MEM 门户](https://aka.ms/memac)
- [安全中心](https://securitycenter.windows.com/)
- [Intune 安全基线](/mem/intune/protect/security-baseline-settings-defender-atp#microsoft-defender)

有关此Microsoft Endpoint Manager，请查看以下资源：

- [Microsoft Endpoint Manager页](/mem/)
- [有关 Intune 和 ConfigMgr 聚合的博客文章](https://www.microsoft.com/microsoft-365/blog/2019/11/04/use-the-power-of-cloud-intelligence-to-simplify-and-accelerate-it-and-the-move-to-a-modern-workplace/)
- [MEM 简介视频](https://www.microsoft.com/microsoft-365/blog/2019/11/04/use-the-power-of-cloud-intelligence-to-simplify-and-accelerate-it-and-the-move-to-a-modern-workplace)

## <a name="step-1-onboard-devices-by-creating-a-group-in-mem-to-assign-configurations-on"></a>步骤 1：在 MEM 中创建组以在上分配配置来载入设备

### <a name="identify-target-devices-or-users"></a>确定目标设备或用户

在此部分中，我们将创建一个测试组来分配配置。

> [!NOTE]
> Intune 使用 Azure Active Directory (Azure AD) 组来管理设备和用户。 作为 Intune 管理员，你可以设置组以满足你的组织需求。
>
> 有关详细信息，请参阅添加 [组以组织用户和设备](/mem/intune/fundamentals/groups-add)。

### <a name="create-a-group"></a>创建群组

1. 打开 MEM 门户。

2. 打开 **"组>新建组"。**

    > [!div class="mx-imgBorder"]
    > ![Microsoft Endpoint Manager portal1 的图像。](images/66f724598d9c3319cba27f79dd4617a4.png)

3. 输入详细信息并创建新组。

    > [!div class="mx-imgBorder"]
    > ![Microsoft Endpoint Manager portal2 的图像。](images/b1e0206d675ad07db218b63cd9b9abc3.png)

4. 添加测试用户或设备。

5. 从" **组>所有组"窗格中** ，打开新组。

6. 选择 **">添加成员"。**

7. 查找测试用户或设备并选择它。

    > [!div class="mx-imgBorder"]
    > ![Microsoft Endpoint Manager portal3 的图像。](images/149cbfdf221cdbde8159d0ab72644cd0.png)

8. 你的测试组现在具有要测试的成员。

## <a name="step-2-create-configuration-policies-to-configure-microsoft-defender-for-endpoint-capabilities"></a>步骤 2：创建配置策略以配置 Microsoft Defender 的终结点功能

下一节将创建多个配置策略。

首先，配置策略用于选择哪些用户组或设备将载入到适用于终结点的 Defender：

- [终结点检测和响应](#endpoint-detection-and-response)

然后，继续创建几种不同类型的终结点安全策略：

- [下一代保护](#next-generation-protection)
- [减少攻击面](#attack-surface-reduction---attack-surface-reduction-rules)

### <a name="endpoint-detection-and-response"></a>终结点检测和响应

1. 打开 MEM 门户。

2. 导航到 **终结点安全>终结点检测和响应**。 单击"**创建配置文件"。**

    > [!div class="mx-imgBorder"]
    > ![Microsoft Endpoint Manager portal4 的图像。](images/58dcd48811147feb4ddc17212b7fe840.png)

3. 在 **"平台"下，Windows 10和更高版本、配置文件 - 终结点检测和响应>创建"。**

4. 输入名称和说明，然后选择"下一 **步"。**

    > [!div class="mx-imgBorder"]
    > ![Microsoft Endpoint Manager portal5 的图像。](images/a5b2d23bdd50b160fef4afd25dda28d4.png)

5. 按要求选择设置，然后选择"下一 **步"。**

    > [!div class="mx-imgBorder"]
    > ![Microsoft Endpoint Manager portal6 的图像。](images/cea7e288b5d42a9baf1aef0754ade910.png)

    > [!NOTE]
    > 在此实例中，已自动填充，因为 Defender for Endpoint 已与 Intune 集成。 有关集成详细信息，请参阅在 Intune 中启用[Microsoft Defender for Endpoint。](/mem/intune/protect/advanced-threat-protection-configure#to-enable-microsoft-defender-atp)
    >
    > 下图是 Microsoft Defender for Endpoint 未与 Intune 集成时将看到的示例：
    >
    > ![Microsoft Endpoint Manager portal7 的图像。](images/2466460812371ffae2d19a10c347d6f4.png)

6. 如有必要，添加范围标记，然后选择下一  **步**。

    > [!div class="mx-imgBorder"]
    > ![Microsoft Endpoint Manager portal8 的图像。](images/ef844f52ec2c0d737ce793f68b5e8408.png)

7. 通过单击"选择要包含的 **组**"并选择你的组来添加测试组，然后选择"下一步 **"。**

    > [!div class="mx-imgBorder"]
    > ![Microsoft Endpoint Manager portal9 的图像。](images/fc3525e20752da026ec9f46ab4fec64f.png)

8. 查看并接受，  **然后选择创建**。

    > [!div class="mx-imgBorder"]
    > ![Microsoft Endpoint Manager portal10 的图像。](images/289172dbd7bd34d55d24810d9d4d8158.png)

9. 可以查看已完成的策略。

    > [!div class="mx-imgBorder"]
    > ![Microsoft Endpoint Manager portal11 的图像。](images/5a568b6878be8243ea2b9d82d41ed297.png)

### <a name="next-generation-protection"></a>下一代保护

1. 打开 MEM 门户。

2. 导航到 **终结点安全>防病毒>创建策略。**

    > [!div class="mx-imgBorder"]
    > ![Microsoft Endpoint Manager portal12 的图像。](images/6b728d6e0d71108d768e368b416ff8ba.png)

3. 选择 **平台 - Windows 10和更高版本 - Windows配置文件 - Microsoft Defender 防病毒>创建**。

4. 输入名称和说明，然后选择下一  **步**。

    > [!div class="mx-imgBorder"]
    > ![Microsoft Endpoint Manager portal13 的图像。](images/a7d738dd4509d65407b7d12beaa3e917.png)

5. 在"**配置设置"页**：设置云保护Microsoft Defender 防病毒 (排除项、Real-Time保护和修正) 。

    > [!div class="mx-imgBorder"]
    > ![Microsoft Endpoint Manager portal14 的图像。](images/3840b1576d6f79a1d72eb14760ef5e8c.png)

6. 如有必要，添加范围标记，然后选择下一  **步**。

    > [!div class="mx-imgBorder"]
    > ![Microsoft Endpoint Manager portal15 的图像。](images/2055e4f9b9141525c0eb681e7ba19381.png)

7. 选择要包含的组，分配给你的测试组，然后选择下一  **步**。

    > [!div class="mx-imgBorder"]
    > ![Microsoft Endpoint Manager portal16 的图像。](images/48318a51adee06bff3908e8ad4944dc9.png)

8. 查看并创建，然后选择"创建 **"。**

    > [!div class="mx-imgBorder"]
    > ![Microsoft Endpoint Manager portal17 的图像。](images/dfdadab79112d61bd3693d957084b0ec.png)

9. 你将看到你创建的配置策略。

    > [!div class="mx-imgBorder"]
    > ![Microsoft Endpoint Manager portal18 的图像。](images/38180219e632d6e4ec7bd25a46398da8.png)

### <a name="attack-surface-reduction---attack-surface-reduction-rules"></a>攻击面减少 - 攻击面减少规则

1. 打开 MEM 门户。

2. 导航到 **终结点安全>攻击面减少**。

3. 选择 **"创建策略"。**

4. 选择 **平台 - Windows 10和更高版本 - 配置文件 - 攻击面减少规则>创建**。

    > [!div class="mx-imgBorder"]
    > ![Microsoft Endpoint Manager portal19 的图像。](images/522d9bb4288dc9c1a957392b51384fdd.png)

5. 输入名称和说明，然后选择"下一 **步"。**

    > [!div class="mx-imgBorder"]
    > ![Microsoft Endpoint Manager portal20 的图像。](images/a5a71fd73ec389f3cdce6d1a6bd1ff31.png)

6. 在"**配置设置"页**：设置攻击面减少规则需要的配置，然后选择"下一 **步"。**

    > [!NOTE]
    > 我们将配置所有攻击面减少规则以审核。
    >
    > 有关详细信息，请参阅攻击 [面减少规则](attack-surface-reduction.md)。

    > [!div class="mx-imgBorder"]
    > ![Microsoft Endpoint Manager portal21 的图像。](images/dd0c00efe615a64a4a368f54257777d0.png)

7. 根据需要添加范围标记，然后选择"下一 **步"。**

    > [!div class="mx-imgBorder"]
    > ![Microsoft Endpoint Manager portal22 的图像。](images/6daa8d347c98fe94a0d9c22797ff6f28.png)

8. 选择要包含并分配给测试组的组，然后选择"下一 **步"。**

    > [!div class="mx-imgBorder"]
    > ![Microsoft Endpoint Manager portal23 的图像。](images/45cefc8e4e474321b4d47b4626346597.png)

9. 查看详细信息，然后选择"创建 **"。**

    > [!div class="mx-imgBorder"]
    > ![Microsoft Endpoint Manager portal24 的图像。](images/2c2e87c5fedc87eba17be0cdeffdb17f.png)

10. 查看策略。

    > [!div class="mx-imgBorder"]
    > ![Microsoft Endpoint Manager portal25 的图像。](images/7a631d17cc42500dacad4e995823ffef.png)

### <a name="attack-surface-reduction---web-protection"></a>攻击面减少 - Web 保护

1. 打开 MEM 门户。

2. 导航到 **终结点安全>攻击面减少**。

3. 选择 **"创建策略"。**

4. 选择 **"Windows 10"和"稍后 - Web >创建"。**

    > [!div class="mx-imgBorder"]
    > ![Microsoft Endpoint Manager portal26 的图像。](images/cd7b5a1cbc16cc05f878cdc99ba4c27f.png)

5. 输入名称和说明，然后选择"下一 **步"。**

    > [!div class="mx-imgBorder"]
    > ![Microsoft Endpoint Manager portal27 的图像。](images/5be573a60cd4fa56a86a6668b62dd808.png)

6. 在"**配置设置"页**：设置 Web 保护需要的配置，然后选择"下一步 **"。**

    > [!NOTE]
    > 我们正在将 Web 保护配置为阻止。
    >
    > 有关详细信息，请参阅[Web Protection。](web-protection-overview.md)

    > [!div class="mx-imgBorder"]
    > ![Microsoft Endpoint Manager portal28 的图像。](images/6104aa33a56fab750cf30ecabef9f5b6.png)

7. 根据需要 **在 Next 中添加>标记**。

    > [!div class="mx-imgBorder"]
    > ![Microsoft Endpoint Manager portal29 的图像。](images/6daa8d347c98fe94a0d9c22797ff6f28.png)

8. 选择 **"分配到测试组>下一步"。**

    > [!div class="mx-imgBorder"]
    > ![Microsoft Endpoint Manager portal30 的图像。](images/45cefc8e4e474321b4d47b4626346597.png)

9. 选择 **查看并创建>创建**。

    > [!div class="mx-imgBorder"]
    > ![Microsoft Endpoint Manager portal31 的图像。](images/8ee0405f1a96c23d2eb6f737f11c1ae5.png)

10. 查看策略。

    > [!div class="mx-imgBorder"]
    > ![Microsoft Endpoint Manager portal32 的图像。](images/e74f6f6c150d017a286e6ed3dffb7757.png)

## <a name="validate-configuration-settings"></a>验证配置设置

### <a name="confirm-policies-have-been-applied"></a>确认策略已应用

分配配置策略后，需要一些时间应用。

有关计时的信息，请参阅 [Intune 配置信息](/mem/intune/configuration/device-profile-troubleshoot#how-long-does-it-take-for-devices-to-get-a-policy-profile-or-app-after-they-are-assigned)。

若要确认配置策略已应用于测试设备，请针对每个配置策略执行以下过程。

1. 打开 MEM 门户并导航到相关策略，如上述步骤所示。 以下示例显示了下一代保护设置。

    > [!div class="mx-imgBorder"]
    > [![portal33 Microsoft Endpoint Manager图像。](images/43ab6aa74471ee2977e154a4a5ef2d39.png)](images/43ab6aa74471ee2977e154a4a5ef2d39.png#lightbox)

2. 选择 **配置策略** 以查看策略状态。

    > [!div class="mx-imgBorder"]
    > [![portal34 Microsoft Endpoint Manager图像。](images/55ecaca0e4a022f0e29d45aeed724e6c.png)](images/55ecaca0e4a022f0e29d45aeed724e6c.png#lightbox)

3. 选择  **"设备状态** "以查看状态。

    > [!div class="mx-imgBorder"]
    > [![Microsoft Endpoint Manager portal35 的图像。](images/18a50df62cc38749000dbfb48e9a4c9b.png)](images/18a50df62cc38749000dbfb48e9a4c9b.png#lightbox)

4. 选择  **"用户状态** "以查看状态。

    > [!div class="mx-imgBorder"]
    > [![Microsoft Endpoint Manager portal36 的图像。](images/4e965749ff71178af8873bc91f9fe525.png)](images/4e965749ff71178af8873bc91f9fe525.png#lightbox)

5. 选择  **"每设置状态** "以查看状态。

    > [!TIP]
    > 此视图对于标识与另一个策略冲突的任何设置非常有用。

    > [!div class="mx-imgBorder"]
    > [![Microsoft Endpoint Manager portal37 的图像。](images/42acc69d0128ed09804010bdbdf0a43c.png)](images/42acc69d0128ed09804010bdbdf0a43c.png#lightbox)

### <a name="confirm-endpoint-detection-and-response"></a>确认终结点检测和响应

1. 在应用配置之前，Endpoint Protection Defender for Endpoint Protection服务。

    > [!div class="mx-imgBorder"]
    > [![服务面板 1 的图像。](images/b418a232a12b3d0a65fc98248dbb0e31.png)](images/b418a232a12b3d0a65fc98248dbb0e31.png#lightbox)

2. 应用配置后，应启动 Defender for Endpoint Protection Service。

    > [!div class="mx-imgBorder"]
    > [![服务面板 2 的图像。](images/a621b699899f1b41db211170074ea59e.png)](images/a621b699899f1b41db211170074ea59e.png#lightbox)

3. 在设备上运行服务后，设备将显示在 Microsoft Defender 安全中心中。

    > [!div class="mx-imgBorder"]
    > [![图像Microsoft Defender 安全中心。](images/df0c64001b9219cfbd10f8f81a273190.png)](images/df0c64001b9219cfbd10f8f81a273190.png#lightbox)

### <a name="confirm-next-generation-protection"></a>确认下一代保护

1. 在测试设备上应用策略之前，你应该能够手动管理设置，如下所示。

    > [!div class="mx-imgBorder"]
    > ![设置第 1 页的图像。](images/88efb4c3710493a53f2840c3eac3e3d3.png)

2. 应用策略后，你将无法手动管理设置。

    > [!NOTE]
    > 在下图中 **，"启用云保护** "和 **"** 启用实时保护"将显示为托管保护。

    > [!div class="mx-imgBorder"]
    > ![设置第 2 页的图像。](images/9341428b2d3164ca63d7d4eaa5cff642.png)

### <a name="confirm-attack-surface-reduction---attack-surface-reduction-rules"></a>确认攻击面减少 - 攻击面减少规则

1. 在测试设备上应用该策略之前，笔使用 PowerShell 窗口并键入 `Get-MpPreference` 。

2. 此响应应包含以下行，无内容：

    > AttackSurfaceReductionOnlyExclusions：
    >
    > AttackSurfaceReductionRules_Actions：
    >
    > AttackSurfaceReductionRules_Ids：

    ![命令行 1 的图像。](images/cb0260d4b2636814e37eee427211fe71.png)

3. 在测试设备上应用该策略后，打开 PowerShell Windows键入 `Get-MpPreference` 。

4. 这应该会以以下行作为响应，内容如下所示：

    ![命令行 2 的图像。](images/619fb877791b1fc8bc7dfae1a579043d.png)

### <a name="confirm-attack-surface-reduction---web-protection"></a>确认攻击面减少 - Web 保护

1. 在测试设备上，打开 PowerShell Windows键入 `(Get-MpPreference).EnableNetworkProtection` 。

2. 这应该会以 0 作为响应，如下所示。

    ![命令行 3 的图像。](images/196a8e194ac99d84221f405d0f684f8c.png)

3. 应用该策略后，打开 PowerShell Windows并键入 `(Get-MpPreference).EnableNetworkProtection` 。

4. 响应结果应为 1，如下所示。

    ![命令行 4 的图像。](images/c06fa3bbc2f70d59dfe1e106cd9a4683.png)
