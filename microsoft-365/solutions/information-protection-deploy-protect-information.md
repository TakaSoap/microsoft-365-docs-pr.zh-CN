---
title: 保护受数据隐私法规制约的信息
ms.author: bcarter
author: brendacarter
f1.keywords:
- NOCSH
manager: laurawi
ms.date: 06/09/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- M365solutions
ms.custom: ''
description: 部署 Microsoft 365 安全性和合规性功能，并保护你的个人信息。
ms.openlocfilehash: 2ec8d280d650606921becb6120546b52253620f4
ms.sourcegitcommit: bd5a08785b5ec320b04b02f8776e28bce5fb448f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/23/2020
ms.locfileid: "44844688"
---
# <a name="protect-information-subject-to-data-privacy-regulation"></a>保护受数据隐私法规制约的信息

您可以在订阅中使用大量信息保护控件，以帮助满足数据隐私合规性需求和法规要求。 其中包括常规数据保护法规（GDPR）、HIPAA-高科技（美国卫生保健隐私保护法案）、加利福尼亚州消费者保护法（CCPA）和巴西数据保护法案（LGPD）。

这些控件位于以下解决方案领域中：

- 敏感度标签
- 数据丢失防护 (DLP)
- Office 邮件加密（OME）
- 团队和网站访问控制

>[!Note]
>此解决方案介绍了安全性和合规性功能，以保护受数据隐私法规约束的信息。 有关 Microsoft 365 中安全功能的完整列表，请参阅[microsoft 365 安全文档](https://docs.microsoft.com/microsoft-365/security/)。 有关 Microsoft 365 中合规性功能的完整列表，请参阅[microsoft 365 合规性文档](https://docs.microsoft.com/microsoft-365/compliance/)。
>

## <a name="data-privacy-regulations-that-impact-information-protection-controls"></a>影响信息保护控制的数据隐私法规

下面是可能与信息保护控件相关的数据隐私法规的示例列表：

- GDPR 第5个项目（1）（f））
- GDPR 文章（32）（1）（a）
- LGPD 文章46
- HIPAA-高科技（45 CFR 164.312 （e）（1））
- HIPAA-高科技（45 C.F.R。 164.312 （e）（2）（ii））

有关上述各项的详细信息，请参阅[评估数据隐私风险和标识敏感项目一文](information-protection-deploy-assess.md)。

信息保护的数据隐私法规建议：

- 针对丢失或未经授权的访问、使用和/或传输进行保护。
- 保护机制的基于风险的应用程序。
- 在适当的位置使用加密。

您的组织可能还希望针对其他目的（如其他合规性需求或商业理由）保护 Microsoft 365 内容。 为数据隐私建立信息保护方案应作为整体信息保护规划、实现和管理的一部分来完成。

为了帮助你开始使用 Microsoft 365 中的信息保护方案，以下部分包含适用于 Microsoft 365 的相关功能和改进操作的简短列表。 此列表包含适用于数据隐私法规的功能和改进操作。 但是，如果存在主要取代旧的功能的较新功能，则该列表不包含较旧的技术。 例如，SharePoint 和 OneDrive 的信息权限管理（IRM）不包含在列表中，但包含敏感性标签。

## <a name="managing-information-protection-in-microsoft-365"></a>在 Microsoft 365 中管理信息保护

Microsoft[信息保护解决方案](../compliance/protect-information.md)在 microsoft 365、microsoft Azure 和 microsoft Windows 中提供了许多集成功能。 在 Microsoft 365 中，信息保护解决方案包括：

- [使用客户密钥进行服务加密](../compliance/customer-key-overview.md)
- [敏感信息类型](../compliance/what-the-sensitive-information-types-look-for.md)（在 "[评估数据隐私风险" 和 "确定敏感项目" 文章](information-protection-deploy-assess.md)中介绍）
- [敏感度标签](../compliance/sensitivity-labels.md) 
  - 服务/容器级
  - 客户端/内容级别
  - 在 SharePoint 和 OneDrive 中的静态数据自动化
- 数据丢失防护 (DLP)
- [Office 365 邮件加密的新功能（OME）](../compliance/ome.md)和 OME[高级邮件加密](../compliance/ome-advanced-message-encryption.md)

此外，网站和库级别保护是在任何保护方案中包含的重要机制。

有关 Microsoft 365 之外的其他信息保护功能的信息，请参阅：

- [Microsoft 云应用程序安全性（MCAS）](https://docs.microsoft.com/cloud-app-security/)
- [Azure 信息保护](https://docs.microsoft.com/azure/information-protection/what-is-information-protection)
- [Microsoft 终结点管理器](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager)
- [Windows 信息保护](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/protect-enterprise-data-using-wip)

## <a name="sensitivity-labels"></a>敏感度标签

Microsoft 信息保护框架中的敏感度标签允许您对组织的数据进行分类和保护，而不会阻碍用户的工作效率和协作能力。

![Microsoft 365 中的敏感度标签](../media/information-protection-deploy-protect-information/information-protection-deploy-protect-information-labels.png)

### <a name="prerequisites-for-sensitivity-labels"></a>敏感度标签的先决条件

在实现下面突出显示的任何基于敏感度标签的功能之前，请先完成这些活动：

1. 了解以下内容：
   - **业务要求。** 建立在企业中应用敏感标签的业务原因。 例如，您的信息保护的数据隐私要求。
   - **敏感度标签功能。** 敏感度标签可能会变得复杂，因此请务必在开始前阅读[灵敏度标签文档](../compliance/sensitivity-labels.md)。
   - **需要记住的关键事项**敏感度标签在 Microsoft 合规性管理中心中进行管理，但目标和应用程序选项明显不同。
      - 对于容器级别的网站、组和团队，有敏感性标签（这些设置不适用于容器内的内容）。 这些发布到在设置网站、组或团队时对其应用的用户和组。
      - 有适用于活动内容的敏感度标签。 这些内容还会发布到用户或组，用户或组是手动应用，还是在以下情况下自动应用：
        - 文件将打开/编辑/保存到用户的桌面或 SharePoint 网站。
        - 将拔出并发送一封电子邮件。
      - 在 SharePoint 和 OneDrive 中的 rest 文件以及通过 Exchange 传输的电子邮件中，自动应用程序都有敏感性标签。 它们的目标是所有网站或特定网站，并在这些环境中自动应用于 rest 上的文件。

2. 合理化当前敏感度标签和过去的或替代方法

   - Azure 信息保护

      当前灵敏度标签方案可能需要与任何现有的[Azure 信息保护](../compliance/sensitivity-labels.md#sensitivity-labels-and-azure-information-protection)标记实现协调在一起。
   - OME

      如果您计划使用新式灵敏度标签进行电子邮件保护，并使用现有的电子邮件加密方法（如 OME），则可以共存，但您应了解应应用其中的方案。 请参阅[Office 365 邮件加密新功能（OME）](#office-365-message-encryption-ome-new-capabilities)，其中包括比较新式敏感度标签类型保护和基于 OME 的保护的表格。

3. 规划集成到一个更广泛的信息保护方案中。 在与 OME 共存的同时，可以使用当前敏感度标签（如 Microsoft 365 数据丢失防护（DLP）和 Microsoft 云应用安全性）等并行功能。 请参阅[敏感度标签和 Microsoft 云应用安全](../compliance/sensitivity-labels.md#sensitivity-labels-and-microsoft-cloud-app-security)，以实现与您的数据隐私相关的信息保护目标。

4. 开发灵敏度标签分类和控制方案。 请参阅[数据分类和敏感度标签分类](https://aka.ms/dataclassificationwhitepaper)。

### <a name="general-guidance"></a>一般指导

1. **架构定义。** 在使用技术功能应用标签和保护之前，请在您的组织内工作以定义分类架构。 您可能已有一个分类架构，这使得添加个人数据变得更加容易。 
2. **入门。** 首先确定要实现的标签的编号和名称。 执行此活动，无需担心要使用的技术和标签的应用方式。 在整个组织中通用应用此架构，包括驻留在本地和其他云服务中的数据。
3. **其他建议**在设计和实施策略、标签和条件时，请考虑遵循以下建议：

   - **使用现有分类架构（如果有）。** 许多组织已使用某种形式的数据分类。 请仔细评估现有标签架构，如果可能，请按 "是"。 使用可识别给最终用户的熟悉标签将推动采用。
   - **从小开始。** 实际上，您可以创建的标签数没有限制。 但是，大量标签和子标签可能会降低采用速度。
   - **使用方案和用例。** 确定组织中的常见用例，并使用从您所使用的数据隐私法规派生的方案。 验证预想的标签和分类配置在实践中是否可以正常工作。
   - **对于新标签，请回答每个请求。** 每种方案或用例确实需要新标签，还是可以使用现有的标签？ 将标签数量保持为最小值可提高采用程度。
   - **对关键部门使用子标签。** 有些部门将有需要特定标签的特定需求。 将这些标签定义为现有标签的子标签，并考虑使用分配给用户组的作用域策略，而不是全局。
   - **考虑作用域策略。** 以用户子集为目标的策略将阻止标签超载。 通过作用域策略，可以将角色或特定于部门的标签或子标签分配给仅适用于该特定部门的员工。 
   - **使用有意义的标签名称。** 尽量不要将术语、标准或首字母缩写词用作标签名称。 尝试使用与最终用户 resonate 的名称来改进采用。 除了使用 PII、PCI、HIPAA、LBI、MBI 和 HBI 等标签，请考虑诸如非商业、公共、常规、机密和高度机密的名称。

### <a name="create-and-deploy-sensitivity-labels-for-sites-groups-and-teams"></a>创建和部署网站、组和团队的敏感度标签

在 Microsoft 365 合规性中心创建[敏感度标签](../compliance/sensitivity-labels-teams-groups-sites.md)时，现在可以将它们应用于这些容器：

- Microsoft 团队网站
- Microsoft 365 组（以前称为 Office 365 组）
- SharePoint 网站

使用以下标签设置来帮助保护这些容器中的内容：

- Microsoft 365 组连接的团队网站的隐私（公用或专用）
- 外部用户访问
- 非托管设备的访问

对于数据隐私，若要阻止将用于存储具有敏感个人数据的内容的容器的外部共享，请将包含数据的文件标记为私有，并需要托管设备。

### <a name="create-and-deploy-sensitivity-labels-for-content"></a>创建和部署内容的敏感度标签

应用于文件的敏感度标签允许您对内容进行加密、为内容添加水印并为 Office 应用程序内容定义其他控件，包括 web 上的 Outlook 和 Office。

当您准备好使用敏感度标签来保护您的组织的数据时：

1. **创建应用程序。** 根据组织的分类法为不同敏感度级别的内容创建和命名敏感度标签。 有关开发分类分类的详细信息，请参阅[数据分类和敏感度标签分类](https://aka.ms/dataclassificationwhitepaper)白皮书。
2. **定义每个标签的用途。** 配置要与每个标签关联的保护设置。 例如，您可能希望较低敏感度的内容（如 "常规" 标签）只应用页眉或页脚，而敏感度较高的内容（如 "机密" 标签）应具有水印并启用加密。
3. **发布标签。** 配置灵敏度标签后，使用标签策略发布它们。 确定应该应用标签的用户和组以及要使用的策略设置。 单个标签是可重用的。 你可以定义它一次，然后可以将其包含在分配给不同用户的多个标签策略中。

一旦您从 Microsoft 365 合规性中心发布灵敏度标签，它们就会开始在[Office 应用程序](../compliance/sensitivity-labels-office-apps.md)中显示，以供用户在创建或编辑内容时对其进行分类和保护。

![Microsoft 365 中的敏感度标签部署流](../media/information-protection-deploy-protect-information/information-protection-deploy-protect-information-label-flow.png)

对于数据隐私，您需要手动将敏感度标签与加密和其他规则结合使用，以发送电子邮件或包含敏感个人信息的内容。

>[!Note]
>对已启用加密的敏感度标签应用于电子邮件具有一些与 OME 重叠的功能。 请参阅[安全电子邮件方案与 OME 和敏感度标签比较](#secure-email-scenarios-comparison-with-ome-and-sensitivity-labels)。

### <a name="client-side-auto-labeling-when-users-edit-documents-or-compose-emails"></a>用户编辑文档或撰写电子邮件时的客户端自动标记

当您创建灵敏度标签时，您可以[将该标签自动分配](../compliance/apply-sensitivity-label-automatically.md)给包含您指定的条件的电子邮件的内容。

能否将敏感度标签自动应用于内容非常重要，这是因为：

- 无需为用户提供有关何时使用每种分类的培训。
- 无需依赖用户，即可对全部内容进行正确分类。
- 用户不再需要了解你的策略，反而可以专注于自己的工作。

自动标签支持向用户推荐一个标签，并自动应用标签。 但在这两种情况下，用户都可以决定接受还是拒绝标签，以帮助确保正确标记内容。

此客户端标记的文档延迟最少，因为即使在保存文档之前也可以应用标签。 但是，并非所有客户端应用都支持自动标记。 Azure 信息保护统一标记客户端和[某些版本的 Office 应用](../compliance/sensitivity-labels-office-apps.md#support-for-sensitivity-label-capabilities-in-apps)支持此功能。

有关配置说明，请参阅[如何为 Office 应用程序配置自动标记](../compliance/sensitivity-labels-office-apps.md#support-for-sensitivity-label-capabilities-in-apps)。

对于数据隐私，您将为包含敏感个人信息的内容自动应用敏感度标签。

### <a name="service-side-auto-labeling-when-content-is-already-saved"></a>在内容已保存时服务端自动标记

此方法称为使用敏感度标签自动分类。 您还可能会听到，它称为自动标记静态数据（对于 SharePoint 和 OneDrive 中的文档）和传输中的数据（对于 Exchange 发送或接收的电子邮件）。 对于 Exchange，它不会在静止邮箱中包含电子邮件。
 
由于此标记由服务本身而不是用户应用程序应用，因此无需担心用户拥有哪些应用以及什么版本。 因此，可立即在整个组织中使用此功能，并且适合大规模标记。 自动标记策略不支持推荐的标记，因为用户不与标记过程交互。 相反，管理员将在模拟模式下运行策略，以便在实际应用标签前，帮助确保正确标记内容。

有关配置说明，请参阅[如何为 SharePoint、OneDrive 和 Exchange 配置自动标记策略](../compliance/apply-sensitivity-label-automatically.md#how-to-configure-auto-labeling-policies-for-sharepoint-onedrive-and-exchange)。

若要获取关注网站中的数据隐私性，请将敏感度标签用于自动加密包含敏感个人信息的内容。

## <a name="data-loss-prevention"></a>数据丢失防护 

您可以使用 Microsoft 365 中的[数据丢失防护（DLP）](../compliance/data-loss-prevention-policies.md)来检测、警告和阻止存在风险、无意或不适当的共享，例如在内部和外部共享包含个人信息的数据。

DLP 允许您执行以下操作：

- 识别和监视有风险的共享活动。
- 向用户提供上下文相关指导以做出正确的决策。
- 强制数据在内容上使用策略，而不 inhibiting 工作效率。
- 与分类和标记集成，以便在共享数据时对数据进行检测和保护。

### <a name="supported-workloads-for-dlp"></a>DLP 支持的工作负荷

使用 Microsoft 365 合规性中心的 DLP 策略，可以识别、监视和自动保护 Microsoft 365 中的多个位置的敏感项目，例如 Exchange Online、SharePoint、OneDrive 和 Microsoft 团队。

例如，您可以标识任何包含存储在任何 OneDrive 站点中的信用卡号的文档，也可以仅监视特定人员的 OneDrive 站点。

您还可以监视和保护本地安装的 Excel、PowerPoint 和 Word 版本中的敏感项目，其中包括识别敏感项目并应用 DLP 策略的功能。 当用户共享这些 Office 应用中的内容时，DLP 提供连续监控。

![DLP 支持的工作负荷](../media/information-protection-deploy-protect-information/information-protection-deploy-protect-information-supported-workloads.png)

此图显示了 DLP 保护个人数据的示例。

![使用 DLP 保护个人数据的示例](../media/information-protection-deploy-protect-information/information-protection-deploy-protect-information-dlp-example-use.png)

DLP 用于标识包含健康记录的文档或电子邮件，然后自动阻止对该文档的访问或阻止发送该电子邮件。 然后，DLP 将使用策略提示通知收件人，并向最终用户和管理员发送警报。

### <a name="planning-for-dlp"></a>规划 DLP

为以下项规划 DLP 策略： 

- 您的业务要求。

- 组织的基于风险的评估，如[评估数据隐私风险和标识敏感项目文章](information-protection-deploy-assess.md)中所述。

- 其他信息保护和治理机制就地实施或在规划数据隐私方面。

- 根据评估[数据隐私风险和标识敏感项目文章](information-protection-deploy-assess.md)中所述，您根据评估工作确定的个人数据的敏感信息类型。 DLP 策略条件可以基于敏感信息类型和保留标签。

- 保留标签您需要指定 DLP 条件。 有关详细信息，请参阅[管理您的组织中的数据隐私法规的信息主题](information-protection-deploy-govern.md)一文。

- 持续性的 DLP 策略管理，这要求组织中的人员对敏感信息类型、保留标签、法规和合规性策略中的更改进行操作和调整策略。

[！注意] 尽管不能在 DLP 策略条件中使用敏感度标签，但若要阻止访问，则可以使用仅根据敏感信息类型自动应用的敏感度标签来实现访问。 如果就地设置了强健的灵敏度，请考虑是否应使用 DLP 加强保护，因为：

  - DLP 可以阻止共享文件。 敏感度标签仅可防止访问。

  - DLP 在规则、条件和操作方面具有更精细的控制级别。

  - DLP 策略可应用于团队聊天和频道消息。 敏感度标签仅可应用于文档和电子邮件。


### <a name="dlp-policies"></a>DLP 策略

DLP 策略在 Microsoft 合规性管理中心中配置，并指定保护级别、策略所需的敏感信息类型和目标工作负荷。 它们的基本组件包括标识保护和数据类型。

![Microsoft 365 中的 DLP 策略配置](../media/information-protection-deploy-protect-information/information-protection-deploy-protect-information-dlp-config.png)

下面是一个用于感知 GDPR 的示例 DLP 策略。

![用于感知 GDPR 的 DLP 策略示例](../media/information-protection-deploy-protect-information/information-protection-deploy-protect-information-dlp-example-policy.png)

有关创建和应用 DLP 策略的详细信息，请参阅[本文](../compliance/create-test-tune-dlp-policy.md)。

### <a name="protection-levels-for-data-privacy"></a>数据隐私的保护级别

下表列出了使用 DLP 提高保护的三种配置。

![使用 DLP 保护数据隐私级别](../media/information-protection-deploy-protect-information/information-protection-deploy-protect-information-dlp-protection-levels.png)

第一次配置、感知可用作解决数据隐私法规合规性需求的起点和最低级别的保护。

>[!Note]
>随着保护级别的增加，在某些情况下，用户共享和访问信息的能力将会降低，并且可能会影响他们的工作效率或完成日常任务的能力。
>

为了帮助员工在更安全的环境中继续提高工作效率，在提高保护级别时，请花时间对新的安全策略和过程进行培训并对其进行培训。

### <a name="example-of-using-sensitivity-labels-with-dlp"></a>将敏感度标签与 DLP 结合使用的示例

敏感度标签可以与 DLP 结合使用，以在高度管控的环境中提供数据隐私。 下面是集成部署的关键步骤：

1. 对数据隐私的法规和其他业务要求进行了记录。
2. 目标数据源、类型和所有权的特征相对于数据隐私问题而言。
3. 建立了解决要求和保护和控制数据隐私热点的整体策略。
4. 制定用于解决数据隐私控制策略的分阶段行动计划。

确定这些元素后，可以使用敏感信息类型、敏感度标签分类和 DLP 策略一起使用。 此图显示了一个示例。

![使用 DLP 的敏感度标签示例](../media/information-protection-deploy-protect-information/information-protection-deploy-protect-information-sensitivity-lables-dlp.png)

[查看此图像的更大版本](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/information-protection-deploy-protect-information/information-protection-deploy-protect-information-sensitivity-lables-dlp.png)

下面是使用 DLP 和敏感度标签的一些数据保护方案，如图所示。

| 应用场景 | 流程 |
|:-------|:-----|
| A | <ol><li>内容的敏感度标签由管理员发布到用户和组，以供手动或自动应用到内容和电子邮件。 </li><li>用户 A 在与内容交互时（已应用加密或其他设置）手动或自动应用标签。 </li><li>用户 A 将受保护的电子邮件或文件发送给用户 B，即来宾用户。 </li></ol> |
| B | 管理员向用户 A 发布的 DLP 策略阻止用户 A 向用户 B 发送电子邮件和/或文件。 |
| C |  具有 "所有者无法邀请来宾" 设置的敏感度标签发布给用户 A，该用户负责设置团队团队或 SharePoint 网站。 网站的另一个用户有选择地尝试与用户 B 共享文件，但 DLP 阻止它。 |
| D | 自动应用程序网站内容的敏感度标签将发布到一个或多个网站，从而提供另一层保护，从而导致受保护的网站。 |
|||

## <a name="office-365-message-encryption-ome-new-capabilities"></a>Office 365 邮件加密（OME）的新功能

用户通常使用电子邮件交换敏感项目，如患者健康信息或客户和员工信息。 电子邮件加密有助于确保只有预期的收件人可以查看邮件内容。

通过[OME](../compliance/ome.md)，您可以在组织内部和外部的人员之间发送和接收加密的邮件。 OME 适用于 Outlook.com、Yahoo！、Gmail 和其他电子邮件服务。 OME 帮助确保只有预期的收件人才能查看邮件内容。

对于数据隐私，您可以使用 OME 来保护包含敏感项目的内部邮件。 Office 365 邮件加密是基于 Microsoft Azure 权限管理（Azure RMS）构建的一种在线服务，它是 Azure 信息保护的一部分。 这包括加密、标识和授权策略，以帮助保护您的电子邮件。 您可以使用权限管理模板、"不转发" 和 "仅加密" 选项对邮件进行加密。

您还可以定义邮件流规则以应用此保护。 例如，您可以创建需要对发送到特定收件人的所有邮件加密的规则，或在主题行中包含特定关键字词的邮件，同时指定收件人无法复制或打印邮件的内容。

此外，OME[高级邮件加密](../compliance/ome-advanced-message-encryption.md)还有助于满足要求更灵活地控制外部收件人的合规性义务以及他们对加密电子邮件的访问权限。 使用 Microsoft 365 中的 OME 高级邮件加密，可以控制在组织外部使用检测敏感信息类型的自动策略共享的敏感电子邮件。 

对于数据隐私，如果需要与外部方共享电子邮件，则可以指定过期日期和吊销邮件。 您只能撤销和设置发送给外部收件人的邮件的到期日期。

### <a name="secure-email-scenarios-comparison-with-ome-and-sensitivity-labels"></a>安全电子邮件方案与 OME 和敏感度标签比较

应用于加密电子邮件的 OME 和敏感度标签有一些重叠，因此，了解可能适用于哪些方案，这一点很重要，如下表所示。

| 应用场景 | 敏感度标签 | OME |
|:-------|:-----|:-------|
| 内部 + 合作伙伴 <br> 内部用户与受信任合作伙伴之间的安全通信和协作 | 推荐–使用完全自定义的分类和保护的标签 | 是–仅加密或不转发保护（无分类） |
| 外部方 <br> 与任何外部/消费者用户安全地通信和协作 | 是–预定义标签中的收件人 | 建议–基于收件人的实时保护 |
| 具有过期/撤消的内部 + 合作伙伴 <br> 使用过期和吊销控制对内部用户和受信任合作伙伴的邮件和内容的访问 | 建议-使用 access 持续时间进行完全自定义保护，用户可以手动跟踪和撤消文件 | 否–内部邮件没有吊销或过期 |
| 具有过期/撤消的外部方 <br> 使用过期和吊销控制对具有外部/消费者用户的邮件和内容的访问 | 是–用户可以手动跟踪文件 | 推荐（E5）–管理员可以从安全 & 合规中心撤销邮件 |
| 自动标签 <br> 组织希望自动保护包含特定敏感内容和/或特定收件人的邮件/附件 | 建议（E5）-在 Exchange 和 Outlook 客户端中自动标记，扩大邮件流规则和 DLP 策略 | 是-仅加密或不转发保护的邮件流规则和 DLP 策略 |
||||

在这两种方法之间，最终用户和管理员体验也会有所不同。

## <a name="teams-with-protection-for-highly-sensitive-data"></a>对高度敏感数据进行保护的团队

对于计划将个人数据存储在团队中的数据隐私法规方面的组织，请参阅[Configure a team with security 隔离](secure-teams-security-isolation.md)，其中提供了详细的指导和配置步骤：

- 标识和设备访问
- 创建专用团队
- 锁定基础团队网站权限
- 使用加密的基于组的敏感度标签
