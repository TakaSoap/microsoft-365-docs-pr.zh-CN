---
title: 部署攻击面减少规则
description: 提供部署攻击面减少规则的指南。
keywords: 攻击面减少规则部署， ASR 部署， 启用 asr 规则， 配置 ASR， 主机入侵防护系统， 保护规则， 反攻击规则， 反攻击， 攻击规则， 感染防护规则， Microsoft Defender for Endpoint， 配置 ASR 规则
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
audience: ITPro
author: jweston-1
ms.author: v-jweston
ms.reviewer: oogunrinde, sugamar, jcedola
manager: dansimp
ms.custom: asr
ms.technology: mde
ms.topic: article
ms.collection: M365-security-compliance
ms.openlocfilehash: f3ab66236697b52f0b267685be5247b9da88219d
ms.sourcegitcommit: 6dbf879f769a825ed7039363f3a91d676e355ee0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/12/2021
ms.locfileid: "60947803"
---
# <a name="attack-surface-reduction-rules-deployment-guide"></a>攻击面减少规则部署指南

## <a name="before-you-begin"></a>开始之前

攻击面是组织易受网络威胁和攻击的所有位置。 组织的攻击面包括攻击者可能破坏组织设备或网络的所有位置。 减少攻击面意味着保护组织的设备和网络，从而让攻击者减少攻击方法。 使用 ASR (配置攻击面) 规则（Microsoft Defender for Endpoint 中的众多安全功能之一）可以提供帮助。

ASR 规则针对某些软件行为，例如：

- 启动尝试下载或运行文件的可执行文件和脚本
- 运行混淆的或可疑的脚本
- 应用在正常日常工作期间通常不会发生的行为

通过减少不同的攻击面，你可以首先帮助防止攻击发生。

在初始准备过程中，了解将放置的系统的功能至关重要。 了解这些功能将帮助您确定哪些 ASR 规则对保护组织最为重要。

>[!IMPORTANT]
>本指南提供了图像和示例，可帮助你确定如何配置 ASR 规则;这些图像和示例可能无法反映适用于您的环境的最佳配置选项。

在启动之前，请查看 [攻击面](overview-attack-surface-reduction.md)减少概述和攻击面减少规则 - 第 [1](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/demystifying-attack-surface-reduction-rules-part-1/ba-p/1306420) 部分，了解基础信息。 若要了解覆盖范围和潜在影响，请熟悉当前的 ASR 规则集;请参阅 [攻击面减少规则](attack-surface-reduction-rules.md)。

ASR 规则只是 Microsoft Defender for Endpoint 中攻击面减少功能的一项功能。 本文档将详细介绍如何有效地部署 ASR 规则，以阻止高级威胁，如人为操作的勒索软件和其他威胁。  

### <a name="rules-by-category"></a>按类别分类的规则

如使用攻击面 [减少规则](attack-surface-reduction.md)防止恶意软件感染所述，MDE 中有多个攻击面减少规则，你可以启用这些规则来保护你的组织。 以下是按类别细分的规则：

<br/>

| 多态威胁 | 横向移动&凭据盗窃 | 生产力应用规则 |  电子邮件规则 | 脚本规则 | 杂项规则 |
|:---|:---|:---|:---|:---|:---|
| 阻止可执行文件运行，除非它们满足 (1000 台计算机) 、年龄 (24 小时) 或受信任的列表条件 | 阻止源自 PSExec 和 WMI 命令的进程创建 | 阻止Office创建可执行内容 | 阻止来自电子邮件客户端和 Webmail 的可执行内容 | 阻止混淆的 JS/VBS/PS/宏代码 | 阻止滥用被攻击的易受攻击的已签名驱动程序 <sup> [[1](#fn1)]<sup></sup>  |
| 阻止从 USB 运行的不受信任的和未签名的进程 | 阻止从本地安全Windows (lsass.exe) <sup> [[2](#fn1)] 中窃取凭据<sup></sup>   | 阻止Office创建子进程 |  仅Office通信应用程序创建子进程 | 阻止 JS/VBS 启动下载的可执行内容 | |
| 使用高级防护抵御勒索软件 | 通过 WMI 事件订阅阻止持久性 | 阻止Office将代码注入其他进程 | 阻止Office应用创建子进程 | | |
| | | 阻止 Adobe Reader 创建子进程 | | | |

 (<a id="fn1">1</a>) MEM终结点安全性中目前未提供阻止滥用被攻击的易受攻击的已签名驱动程序。 可以使用 [MEM OMA-URI](enable-attack-surface-reduction.md#mem)配置此规则。

 (<a id="fn1">2</a>) 某些 ASR 规则会生成大量干扰，但不会阻止功能。 例如，如果你要更新 Chrome;Chrome 将访问lsass.exe;密码存储在设备的 lsass 中。 但是，Chrome 不应访问本地设备lsass.exe。 如果启用规则以阻止对 lsass 的访问，它将生成大量事件。 这些事件是很好的事件，因为软件更新过程不应访问lsass.exe。 启用此规则将阻止 Chrome 更新访问 lsas，但不会阻止 Chrome 更新;对于对应用程序进行不必要的调用的其他应用程序也是如此lsass.exe。 阻止 _访问 lsass_ 规则将阻止对 lsass 的不必要调用，但不阻止应用程序运行。

### <a name="infrastructure-requirements"></a>基础结构要求

虽然实现 ASR 规则的多种方法都可行，但本指南基于由以下各项组成的基础结构：

- Azure Active Directory
- Microsoft Endpoint Management (MEM) 
- Windows 10和Windows 11设备
- 适用于终结点 E5 或 Windows E5 许可证的 Microsoft Defender

若要充分利用 ASR 规则和报告，我们建议使用 Microsoft 365 Defender E5 或 Windows E5 许可证和 A5。 了解更多信息 [：Microsoft Defender for Endpoint 的最低要求](minimum-requirements.md)。

>[!Note]
>有多种方法可配置 ASR 规则。 可以使用以下方法配置 ASR 规则：Microsoft Endpoint Manager (MEM) 、PowerShell、组策略、Microsoft System Center Configuration Manager (SCCM) 、MEM OMA-URI。
>如果你使用的基础结构配置与上面 _)_ 上针对基础结构要求 (列出的基础结构配置不同，你可以在此处了解有关使用其他配置部署攻击面减少规则的信息： [启用攻击](enable-attack-surface-reduction.md)面减少规则。  

### <a name="asr-rules-dependencies"></a>ASR 规则依赖项

Microsoft Defender 防病毒必须启用并配置为主要的防病毒解决方案，并且必须具有以下模式：

- 主防病毒/反恶意软件解决方案  
- 状态：活动模式

Microsoft Defender 防病毒不得在下列任一模式下：

- 被动
- 在阻止模式下使用终结点检测和响应 (EDR) 被动模式
- 有限定期扫描 (LPS) 
- 关闭

请参阅：[云提供的保护和Microsoft Defender 防病毒。](cloud-protection-microsoft-defender-antivirus.md)

### <a name="cloud-protection-maps-must-be-enabled"></a>必须启用 (MAPS) 云保护

Microsoft Defender 防病毒 Microsoft 云服务无缝工作。 这些云保护服务（也称为 Microsoft 高级保护服务 (MAPS) ）增强了标准实时保护，从而可以提供最佳防病毒防护。 云保护对于防止恶意软件的攻击和 ASR 规则的关键组件至关重要。
[在"应用"中启用云Microsoft Defender 防病毒。](enable-cloud-protection-microsoft-defender-antivirus.md)

### <a name="microsoft-defender-antivirus-components-must-be-current-versions"></a>Microsoft Defender 防病毒组件必须是当前版本

以下Microsoft Defender 防病毒组件版本必须不超过两个比当前可用版本大的版本：

- **Microsoft Defender 防病毒平台更新版本**- Microsoft Defender 防病毒每月更新一次。
- **Microsoft Defender 防病毒引擎版本**- Microsoft Defender 防病毒引擎每月更新一次。
- **Microsoft Defender 防病毒安全** 智能 - Microsoft 持续更新 Microsoft Defender 安全 (，也称为定义和签名) ，以解决最新威胁，并优化检测逻辑。

保持Microsoft Defender 防病毒版本有助于减少 ASR 规则误报结果，并改进Microsoft Defender 防病毒检测功能。 有关当前版本以及如何更新不同组件的详细信息，Microsoft Defender 防病毒平台Microsoft Defender 防病毒[支持](manage-updates-baselines-microsoft-defender-antivirus.md)。

## <a name="asr-rules-deployment-phases"></a>ASR 规则部署阶段

与任何可能会影响业务线操作的新、大规模实施一样，在规划和实施时一定有条理。 由于 ASR 规则在阻止恶意软件方面具有强大的功能，因此需要仔细规划和部署这些规则，以确保它们最适合您独特的客户工作流。 若要在环境中工作，您需要仔细规划、测试、实施和操作 ASR 规则。  

> [!div class="mx-imgBorder"]
> ![ASR 规则部署阶段](images/asr-rules-deployment-phases.png)

>[!Note]
>对于使用非 Microsoft HIPS 并且正在过渡到 Microsoft Defender for Endpoint 攻击面减少规则的客户：Microsoft 建议客户在从审核模式转移到阻止模式之前，并行运行其 HIPS 解决方案及其 ASR 规则部署。 请记住，您必须联系第三方防病毒供应商，获得排除建议。  

## <a name="phase-1-plan"></a>阶段 1：计划

开始测试 ASR 规则涉及从正确的业务部门开始。 您需要从特定业务部门中的一小组人员开始。 你可以确定特定业务部门中的一些 ASR 冠军，这些冠军可以为 ASR 规则提供实际影响，并帮助你调整实现。

> [!div class="mx-imgBorder"]
> ![ASR 规则规划步骤](images/asr-rules-planning-steps.png)

### <a name="start-with-the-right-business-unit"></a>从正确的业务部门开始

选择业务部门以推出 ASR 规则部署将取决于以下因素：

- 业务部门的大小
- ASR 规则冠军的可用性  
- 分发和使用：
  - 软件
  - 共享文件夹
  - 脚本的使用
  - Office宏
  - 受 ASR 规则影响的其他实体

根据您的业务需求，您可能决定包含多个业务单位，以广泛采样软件、共享文件夹、脚本、宏等。相反，您可能会决定将首次推出 ASR 规则的范围限制为一个业务部门，然后将整个 ASR 规则推出过程重复到其他业务单位，一次一个。

### <a name="identify-asr--rules-champions"></a>确定 ASR 规则冠军

ASR 规则冠军是贵组织的成员，有助于在初步测试和实施阶段推出初始 ASR 规则。 你的冠军通常是在技术上更擅长的员工，并且不会因间歇性的工作流程中断而受阻碍。 在向组织广泛扩展 ASR 规则部署过程中，冠军的参与将继续。 ASR 规则冠军将首先体验每个级别的 ASR 规则推出。

为 ASR 规则支持者提供反馈和响应渠道非常重要，以提醒你 ASR 规则相关的工作中断，并接收与 ASR 规则推出相关的通信。

### <a name="get-inventory-of-line-of-business-apps-and-understand-the-business-unit-processes"></a>获取业务线应用的清单并了解业务部门流程

全面了解整个组织中使用的应用程序和每个业务部门的过程对于成功部署 ASR 规则至关重要。 此外，必须了解在组织的各个业务部门中如何使用这些应用。
首先，你应该获得经批准在整个组织范围使用的应用的清单。 可以使用管理中心等工具Microsoft 365 应用版清单软件应用程序。 请参阅：[管理中心中的Microsoft 365 应用版概述](/deployoffice/admincenter/inventory)。

### <a name="define-reporting-and-response-team--roles-and-responsibilities"></a>定义报告和响应团队角色和责任

明确分配负责监视和传达 ASR 规则状态和活动的人员的角色和职责是 ASR 维护的核心活动。 因此，确定：

- 负责收集报告的人或团队
- 如何共享报告以及与谁共享报告
- 如何处理由 ASR 规则导致的新标识的威胁或不需要的阻止问题进行升级

典型角色和职责包括：

- IT 管理员：实施 ASR 规则，管理排除项。 在应用和流程上使用不同的业务部门。 组合报告并共享给利益干系人
- CSOC (安全运营) ：负责投资高优先级的阻止流程，以确定威胁是否有效
- CISO (首席) ：负责组织的整体安全状况和运行状况

### <a name="ring-deployment"></a>环形部署

对于大型企业，Microsoft 建议在"圈"中部署 ASR 规则。 圈是视觉上表示为像不重叠树圈一样向外延伸的同心圆的设备组。 成功部署最里层的圈后，你可以将下一个圈转换到测试阶段。 对业务部门、ASR 规则冠军、应用和流程进行全面评估对定义圈至关重要。
在大多数情况下，你的组织将设计部署圈，用于分阶段推出Windows更新。 可以使用现有的圈设计来实现 ASR 规则。
请参阅：[为部署环境创建Windows](/windows/deployment/update/create-deployment-plan)

## <a name="phase-2-test"></a>阶段 2：测试

使用圈 1 开始 ASR 规则部署。

> [!div class="mx-imgBorder"]
> ![ASR 规则测试步骤](images/asr-rules-testing-steps.png)

### <a name="step-1-test-asr-rules-using-audit"></a>步骤 1：使用审核测试 ASR 规则

首先打开 ASR 规则，将规则设置为审核，从圈 1 中的冠军用户或设备开始测试阶段。 通常，建议在审核策略中 (所有规则) 以便可以确定在测试阶段触发哪些规则。 请注意，设置为"审核"的规则通常不会影响应用该规则的一个或多个实体的功能，但会为评估生成记录的事件;对最终用户没有影响。

#### <a name="configure-asr-rules-using-mem"></a>使用 MEM 配置 ASR 规则

You can use Microsoft Endpoint Manager (MEM) Endpoint Security to configure custom ASR rules.

1. 打开[Microsoft Endpoint Manager管理中心](https://endpoint.microsoft.com/#home)
2. 转到终结点 **安全**  >  **攻击面减少**。
3. 选择“创建策略”。
4. 在 **平台** 中 **，Windows 10** 和更高版本，在 **配置文件** 中选择 **攻击面减少规则**。
  
    > [!div class="mx-imgBorder"]
    > ![配置 ASR 规则配置文件](images/asr-mem-create-profile.png)

5. 单击“**创建**”。
6. 在 **"创建配置文件****"窗格的**"基本信息"选项卡的 **"名称**"中，为策略添加名称。 在 **"说明** "中，添加 ASR 规则策略的说明。
7. 在" **配置设置"** 选项卡的 **"攻击面减少规则**"下，将所有规则设置为 **审核模式**。

    > [!div class="mx-imgBorder"]
    > ![将 ASR 规则设置为审核模式](images/asr-mem-configuration-settings.png)

    >[!Note]
    >某些 ASR 规则模式列表存在变化;_阻止和__启用_ 提供相同的功能。

8. [可选]在 **范围标记窗格中** ，你可以将标记信息添加到特定设备。 您还可以使用基于角色的访问控制和范围标记，以确保适当的管理员对正确的 Intune 对象具有适当的访问权限和可见性。 了解更多：在 Intune 中为分布式 IT (RBAC) 和范围标记使用基于 [角色的访问控制](/mem/intune/fundamentals/scope-tags)。
9. 在 **"分配** "窗格中，你可以将配置文件部署或"分配给"用户或设备组。 了解更多信息：[在设备上分配Microsoft Intune](/mem/intune/configuration/device-profile-assign#exclude-groups-from-a-profile-assignment)
10. Review your settings in the **Review + create** pane. 单击 **"创建** "以应用规则。

   > [!div class="mx-imgBorder"]
   > ![激活 ASR 规则策略](images/asr-mem-review-create.png)

适用于 ASR 规则的新攻击面减少策略在终结点安全策略中 **|攻击面减少**。

   > [!div class="mx-imgBorder"]
   > ![列出的 ASR 规则策略](images/asr-mem-my-asr-rules.png)

### <a name="step-2-understand-the-attack-surface-reduction-rules-reporting-page-in-the-microsoft-365-defender-portal"></a>步骤 2：了解安全门户中的攻击面减少规则Microsoft 365 Defender页面

ASR 规则报告页面位于 **报告攻击Microsoft 365 Defender**  >    >  **报告攻击面减少规则中**。 此页面包含三个选项卡：

- Detections
- 配置
- 添加排除项

#### <a name="detections-tab"></a>"检测"选项卡

提供检测到的审核和阻止事件的 30 天时间线。

> [!div class="mx-imgBorder"]
> ![攻击面减少规则检测选项卡](images/asr-defender365-01.png)

攻击面减少规则窗格基于每个规则提供检测到的事件的概述。

>[!Note]
>ASR 规则报告中有一些变化。 Microsoft 正在更新 ASR 规则报告的行为以提供一致的体验。

> [!div class="mx-imgBorder"]
> ![攻击面减少规则规则检测](images/asr-defender365-01b.png)

单击 **"查看检测** "以打开 **"检测"** 选项卡。

> [!div class="mx-imgBorder"]
> [![攻击面减少规则检测 ](images/asr-defender365-reports-detections.png) ](images/asr-defender365-reports-detections.png#lightbox)

**"GroupBy"** 和"**筛选器**"窗格提供以下选项：

**GroupBy** 返回结果集到以下组：

- 无分组
- 检测到的文件
- 审核或阻止
- Rule
- 源应用
- Device
- User
- Publisher

> [!div class="mx-imgBorder"]
> [![攻击面减少规则检测 GroupBy 筛选器 ](images/asr-defender365-reports-detections.png) ](images/asr-defender365-reports-detections.png#lightbox)

**筛选器** 将 **打开"筛选规则** "页，利用该页，您可以仅将结果范围确定为所选的 ASR 规则：

> [!div class="mx-imgBorder"]
> [![攻击面减少规则检测筛选规则 ](images/asr-defender365-filter.png) ](images/asr-defender365-filter.png#lightbox)

>[!Note]
>如果你有 Microsoft Microsoft 365 安全 E5 或 A5、Windows E5 或 A5 许可证，以下链接将打开 Microsoft Defender 365 报告[](https://security.microsoft.com/asr?viewid=detections)> 攻击面减少 > 检测"选项卡。

#### <a name="configuration-tab"></a>"配置"选项卡

基于每台计算机列出 – ASR 规则的聚合状态：关闭、审核、阻止。

> [!div class="mx-imgBorder"]
> [![攻击面减少规则配置选项卡 ](images/asr-defender365-configurations.png) ](images/asr-defender365-configurations.png#lightbox)

在"配置"选项卡上，可以通过选择要查看其 ASR 规则的设备来检查（基于每个设备）启用哪些 ASR 规则以及在哪个模式下。

> [!div class="mx-imgBorder"]
> [![攻击面减少规则已启用和模式 ](images/asr-defender365-configurations.settings.png) ](images/asr-defender365-configurations.settings.png#lightbox)

"**入门**"链接将Microsoft Endpoint Manager管理中心，可在其中为 ASR 创建或修改终结点保护策略：

> [!div class="mx-imgBorder"]
> [![MEM 中的攻击面减少规则 ](images/asr-defender365-05b-mem1.png) ](images/asr-defender365-05b-mem1.png#lightbox)

在终结点安全|概述，选择 **攻击面减少**：

> [!div class="mx-imgBorder"]
> [![MEM 中的攻击面减少 ](images/asr-defender365-05b-mem2.png) ](images/asr-defender365-05b-mem2.png#lightbox)

终结点安全|将打开攻击面减少窗格：

> [!div class="mx-imgBorder"]
> [![终结点安全管理窗格 ](images/asr-defender365-05b-mem3.png) ](images/asr-defender365-05b-mem3.png#lightbox)

>[!Note]
>如果你有 Microsoft Defender 365 E5 (或 Windows E5？) 许可证，此链接将打开 Microsoft Defender 365 报告>攻击面减少 >[配置](https://security.microsoft.com/asr?viewid=configuration)"选项卡。

#### <a name="add-exclusions"></a>添加排除项

此选项卡提供了一种方法来选择检测到的实体 (例如，误报) 排除。 添加排除项后，报告会提供预期影响的摘要。

>[!Note]
> Microsoft Defender 防病毒 ASR 规则遵守 AV 排除项。  请参阅 [配置并验证基于扩展名、名称或位置的排除项](configure-extension-file-exclusions-microsoft-defender-antivirus.md)。

> [!div class="mx-imgBorder"]
> [![终结点安全 Asr 工具 ](Images/asr-defender365-06d.png) ](Images/asr-defender365-06d.png#lightbox)

> [!Note]
>如果你拥有 Microsoft Defender 365 E5 (或 Windows E5？) 许可证，此链接将打开 Microsoft Defender 365 报告>攻击面>[排除"选项卡](https://security.microsoft.com/asr?viewid=exclusions)。

### <a name="step-3-assess-impact"></a>步骤 3：评估影响

#### <a name="review"></a>审阅

使用报告门户中的Microsoft 365 Defender查看哪些 ASR 规则（如果有）已影响业务部门流程。 将来自 ASR 冠军的反馈作为此过程的一部分包含。 查看审核报告，确定哪些规则触发/触发的事件最多，哪些规则触发事件最多。

由于 ASR 规则面向广泛的组件，并且这些组件将采用不同的时间间隔调用，因此很难预测获取组织圈中 ASR 规则触发的事件的有用采样所花的时间;但是，Microsoft 建议至少四周。 例如，某些针对应用程序Microsoft Office ASR 规则的触发可能比 ASR 规则更快、更频繁地触发"使用高级保护抵御勒索软件"。 同样，每个圈可能使用不同的应用程序和受 ASR 规则限制的其他组件，并且频率不同。 您必须根据组织的结果确定测试何时完成。 为了更好地理解，请参阅在启用 ASR 规则之前应在审核模式下测试[该规则多久？。](attack-surface-reduction-faq.yml#how-long-should-i-test-an-asr-rule-in-audit-mode-before-enabling-it-)

#### <a name="create-exclusions"></a>创建排除项

在许多情况下，组织具有一个或多个文件文件夹，例如已知安全的文件，其中可能包含将触发 ASR 规则的各个方面;审核模式将显示此类文件和文件夹。 例如，您的组织可能有一个 Word 或 Excel文档的集合，这些文档启用了特定用途的宏;此类宏可以触发 ASR 规则。 在这种情况下，如果审核模式标识此类文件，您希望排除这些文件或文件夹以防止 ASR 规则捕获它们。 请参阅 [排除文件和文件夹](enable-attack-surface-reduction.md#exclude-files-and-folders-from-asr-rules)

>[!Note]
>请记住，MICROSOFT DEFENDER 防病毒 AV 排除项受 ASR 规则遵守。 请参阅 [配置并验证基于扩展名、名称或位置的排除项](configure-extension-file-exclusions-microsoft-defender-antivirus.md)。

如果您确定某条规则将对业务线操作造成负面影响，您可以将规则保留审核，以便可以继续捕获规则，也可以完全禁用该规则。 在报告攻击面减少规则 **中Microsoft 365 Defender**  >    >  **很容易启用排除。** 只需选择要创建排除项的一个或多个实体。

在报告攻击面减少规则 **中Microsoft 365 Defender**  >    >  **很容易启用排除。** 只需选择要创建排除项的一个或多个实体。

> [!div class="mx-imgBorder"]
> [![ASR 创建排除项 ](images/asr-defender365-06d.png) ](images/asr-defender365-06d.png#lightbox)

#### <a name="create-exclusions-after-review"></a>查看后创建排除项

在许多情况下，组织具有一个或多个文件文件夹，例如已知安全的文件，其中可能包含将触发 ASR 规则的各个方面;审核模式将显示此类文件和文件夹。 例如，您的组织可能有一个 Word 或 Excel文档的集合，这些文档启用了特定用途的宏;此类宏可以触发 ASR 规则。 在这种情况下，如果审核模式标识此类文件，您希望排除这些文件或文件夹以防止 ASR 规则捕获它们。 请参阅 [排除文件和文件夹](enable-attack-surface-reduction.md#exclude-files-and-folders-from-asr-rules)。

>[!Note]
>请记住，MICROSOFT DEFENDER 防病毒 AV 排除项受 ASR 规则遵守。 请参阅 [配置并验证基于扩展名、名称或位置的排除项](configure-extension-file-exclusions-microsoft-defender-antivirus.md)。

## <a name="phase-3-implement"></a>阶段 3：实现

实现阶段将环从测试移动到功能状态。

> [!div class="mx-imgBorder"]
> ![ASR 规则实现步骤](images/asr-rules-implementation-steps.png)

### <a name="step-1-transition-asr-rules-from-audit-to-block"></a>步骤 1：将 ASR 规则从审核转换为阻止

1. 在审核模式下确定所有排除项后，开始将某些 ASR 规则设置为"阻止"模式，从触发事件数最小的规则开始。 请参阅"[启用攻击面减少规则"。](enable-attack-surface-reduction.md)
2. 查看报告门户中的报告Microsoft 365 Defender，请参阅[Microsoft Defender for Endpoint 中的威胁防护报告](threat-protection-reports.md)。 此外，查看来自 ASR 冠军的反馈。
3. 精简排除项或在必要时创建新的排除项。
4. 将有问题的规则切换回审核。

  >[!Note]
  >对于有问题的规则 (规则产生过多干扰) ，最好创建排除项，而不是关闭规则或切换回审核。 您必须确定最适合您的环境。

  >[!Tip]
  >如果可用，利用规则中的警告模式设置来限制中断。 在"警告"模式下启用 ASR 规则，可以捕获触发的事件并查看其潜在的中断，而不会实际阻止最终用户的访问。 了解更多： [针对用户发出警告模式](attack-surface-reduction.md#warn-mode-for-users)。

#### <a name="how-does-warn-mode-work"></a>警告模式如何工作？

警告模式实际上是阻止指令，但用户可以选择"取消阻止"给定流或应用的后续执行。 在设备、用户、文件和进程组合上取消阻止警告模式。 警告模式信息存储在本地，持续时间为 24 小时。

### <a name="step-2-expand-deployment-to-ring-n--1"></a>步骤 2：展开部署以圈 n + 1

当你确信已正确配置圈 1 的 ASR 规则时，你可以将部署范围扩大到下一个圈 (n + 1) 。

每个后续圈的部署过程步骤 1 – 3 基本相同：

1. 审核中的测试规则
2. 在管理门户中查看 ASR 触发的Microsoft 365 Defender事件
3. 创建排除项
4. 查看：根据需要优化、添加或删除排除项
5. 将规则设置为"阻止"
6. 查看报告门户中的Microsoft 365 Defender页面。
7. 创建排除项。
8. 禁用有问题的规则或将其切换回审核。

## <a name="phase-4-operationalize"></a>阶段 4：操作

在将 ASR 规则完全部署到组织后，组织必须制定流程来监视和响应与 ASR 相关的活动，这一点至关重要。

### <a name="manage-false-positives"></a>管理误报

任何威胁防护解决方案（包括 Microsoft Defender for Endpoint）都可能发生误报/负面影响。 在终结点保护解决方案中，误报是检测到实体 (（如文件或进程) ）并标识为恶意实体的情况，尽管实体实际上并不是威胁。 相比之下，漏报是未检测为威胁但实际上是恶意的实体。
有关参加误报和漏报的其他信息，请参阅：在 Microsoft Defender for Endpoint 中解决 [误报/负数](defender-endpoint-false-positives-negatives.md)

### <a name="keeping-up-with-reports"></a>保持与报告保持一起

一致、定期地审阅报告是维护 ASR 规则部署和保持新出现的威胁的一个基本方面。 贵组织应按节奏安排对 ASR 规则事件进行审阅，以使用 ASR 规则报告的事件保持最新。 根据组织的规模，这可能是每天、每小时或持续监视。

### <a name="hunting"></a>搜寻

最强大、最酷的功能之[一是](https://securitycenter.microsoft.com)Microsoft 365 Defender搜寻。 如果你不熟悉高级搜寻，请参阅文档：使用高级搜寻主动搜寻 [威胁](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)。

> [!div class="mx-imgBorder"]
> [![Microsoft 365 Defender高级搜寻 ](images/asr-defender365-advanced-hunting2.png) ](images/asr-defender365-advanced-hunting2.png#lightbox)

高级搜寻是基于查询的 (Kusto 查询语言) 威胁搜寻工具，允许你浏览从你的所有计算机收集的最多 30 天的已捕获 (原始)  (EDR) 数据。 通过高级搜寻，你可以主动检查事件，以便找到有趣的指示器和实体。 灵活访问数据有助于无约束搜寻已知威胁和潜在威胁。

通过高级搜寻，可以提取 ASR 规则信息、创建报告，并获取有关给定 ASR 规则审核或阻止事件的上下文的深入信息。

你可以查询应用门户高级搜寻部分中 DeviceEvents 表中的 ASR 规则Microsoft 365 Defender事件。 例如，如下所示的简单查询可以报告过去 30 天内将 ASR 规则作为数据源的所有事件，并按 ActionType 计数汇总这些事件，在这种情况下，它将是 ASR 规则的实际代码名。

> [!div class="mx-imgBorder"]
> ![Microsoft 365 Defender高级搜寻查询命令行](images/asr-defender365-advanced-hunting3.png)

> [!div class="mx-imgBorder"]
> [![Microsoft 365 Defender高级搜寻查询结果 ](images/asr-defender365-advanced-hunting4.png) ](images/asr-defender365-advanced-hunting4.png#lightbox)

上面显示了为 AsrLsassCredentialTheft (102 注册了 187 个事件，为审核的) 注册了 85 个事件，为审核的 AsrOfficeChildProcess (注册了 2 个事件，为 block) 注册了 1 个事件，为 AsrPsexecWmiChildProcessAudited 注册了 8 个事件。

如果要专注于 AsrOfficeChildProcess 规则，并获取有关实际文件和过程的详细信息，请更改 ActionType 的筛选器，将汇总行替换为需要字段 (的投影，在这种情况下，它们是 DeviceName、FileName、FolderPath 等 ) 。

> [!div class="mx-imgBorder"]
> ![Microsoft 365 Defender高级搜寻查询](images/asr-defender365-advanced-hunting4b.png)

> [!div class="mx-imgBorder"]
> [![Microsoft 365 Defender高级搜寻查询焦点结果 ](images/asr-defender365-advanced-hunting5b.png) ](images/asr-defender365-advanced-hunting5b.png#lightbox)

高级搜寻的真正好处是，你可以将查询塑造成喜欢的形状，以便你可以查看所发生事情的确切情景，无论你是想要在单台计算机中定位某些内容，还是想要从整个环境中提取见解。

有关其他搜寻选项的其他信息，请参阅验证攻击面减少 [规则 - 第 3 部分](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/demystifying-attack-surface-reduction-rules-part-3/ba-p/1360968)。

## <a name="reference"></a>参考

### <a name="blogs"></a>博客

[伪造攻击面减少规则 - 第 1 部分](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/demystifying-attack-surface-reduction-rules-part-1/ba-p/1306420)

[伪造攻击面减少规则 - 第 2 部分](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/demystifying-attack-surface-reduction-rules-part-2/ba-p/1326565)

[伪造攻击面减少规则 - 第 3 部分](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/demystifying-attack-surface-reduction-rules-part-3/ba-p/1360968)

[伪造攻击面减少规则 - 第 4 部分](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/demystifying-attack-surface-reduction-rules-part-4/ba-p/1384425)

### <a name="asr-collection"></a>ASR 集合

[减少攻击面概述](overview-attack-surface-reduction.md)

[使用攻击面减少规则来避免感染恶意软件](attack-surface-reduction.md)

[启用攻击面减少规则](enable-attack-surface-reduction.md)

[攻击面减少规则](attack-surface-reduction-rules.md)

[关于攻击面减少的常见问题解答](attack-surface-reduction-faq.yml)

### <a name="microsoft-defender"></a>Microsoft Defender

[解决 Microsoft Defender for Endpoint 中的误报/漏报](defender-endpoint-false-positives-negatives.md)

[云传递保护和 Microsoft Defender 防病毒软件](cloud-protection-microsoft-defender-antivirus.md)

[在云中打开云保护Microsoft Defender 防病毒](enable-cloud-protection-microsoft-defender-antivirus.md)

[根据扩展名、名称或位置配置和验证排除项](configure-extension-file-exclusions-microsoft-defender-antivirus.md)

[Microsoft Defender 防病毒平台支持](manage-updates-baselines-microsoft-defender-antivirus.md)

[管理中心中的Microsoft 365 应用版概述](/deployoffice/admincenter/inventory)

[为部署环境创建Windows](/windows/deployment/update/create-deployment-plan)

[在 Intune 中为分布式 IT (RBAC) 基于角色的访问控制和范围标记](/mem/intune/fundamentals/scope-tags)

[分配设备配置文件Microsoft Intune](/mem/intune/configuration/device-profile-assign#exclude-groups-from-a-profile-assignment)

### <a name="management-sites"></a>管理网站

[Microsoft Endpoint Manager 管理中心](https://endpoint.microsoft.com/#home)

[减少攻击面](https://security.microsoft.com/asr?viewid=detections)

[ASR 规则 配置](https://security.microsoft.com/asr?viewid=configuration)

[ASR 规则排除项](https://security.microsoft.com/asr?viewid=exclusions)
