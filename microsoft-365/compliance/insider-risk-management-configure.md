---
title: 内部风险管理入门
description: 在组织中配置内幕风险管理。
keywords: Microsoft 365，内幕风险管理，风险管理，合规性
localization_priority: Normal
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection:
- m365-security-compliance
- m365solution-insiderrisk
- m365initiative-compliance
ms.openlocfilehash: 684e21a8288aee72f6170d54ffc86af3bcb0ece0
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2020
ms.locfileid: "48846260"
---
# <a name="get-started-with-insider-risk-management"></a>内部风险管理入门

使用内幕风险管理策略确定风险的活动和管理工具，以在组织中的风险警报上执行操作。 完成以下步骤以设置系统必备并配置内幕风险管理策略。

>[!IMPORTANT]
>Microsoft 365 内幕风险管理解决方案提供了租户级选项，可帮助客户在用户级别促进内部治理。 租户级别管理员可以设置权限，以便为组织成员提供对此解决方案的访问权限，并在 Microsoft 365 合规性中心内设置数据连接器，以支持用户级别的可能有风险的活动的用户级别标识。 客户确认与与雇用相关的各个用户的行为、字符或性能相关的见解可由管理员进行计算，并可供组织中的其他人使用。 此外，客户也承认他们必须执行与雇用相关的单个用户的行为、字符或性能的完全调查，而不只是依赖于内幕风险管理服务的见解。 客户只负责使用 Microsoft 365 内幕风险管理服务以及任何关联的功能或服务符合所有适用的法律，包括与单个用户标识和任何补救措施相关的法律。

有关内幕风险策略如何帮助您管理组织中的风险的详细信息，请参阅 [Microsoft 365 中的内幕风险管理](insider-risk-management.md)。

## <a name="before-you-begin"></a>准备工作

在开始使用 "内幕风险管理" 之前，应确认你的 [Microsoft 365 订阅](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans) 和任何加载项。 若要访问和使用内幕风险管理，您的组织必须具有以下订阅或加载项之一：

- Microsoft 365 E5 订阅 (付费或试用版) 
- Microsoft 365 E3 订阅 + Microsoft 365 E5 合规性加载项
- Microsoft 365 E3 订阅 + Microsoft 365 E5 内幕人士风险管理加载项
- Microsoft 365 A5 订阅 (付费版或试用版) 
- Microsoft 365 A3 订阅 + Microsoft 365 A5 合规性加载项
- Microsoft 365 A3 订阅 + Microsoft 365 A5 内幕成员风险管理加载项

必须为内幕风险管理策略中包括的用户分配上述许可证之一。

如果您没有现有的 Microsoft 365 企业版 E5 计划，并且想要尝试使用内幕风险管理，则可以 [将 microsoft 365 添加](https://docs.microsoft.com/office365/admin/try-or-buy-microsoft-365) 到现有订阅或注册 Microsoft 365 企业版 e5 的 [试用版](https://www.microsoft.com/microsoft-365/enterprise) 。

## <a name="step-1-enable-permissions-for-insider-risk-management"></a>步骤1：为内部人员风险管理启用权限

>[!Important]
>配置角色组后，最多可能需要30分钟的时间才能将角色组权限应用到组织中分配的用户。

有四个角色组用于配置权限以管理内幕风险管理功能。 若要继续执行这些配置步骤，租户管理员必须首先将您分配给 " **内幕风险管理** " 或 " **内幕风险管理" 管理员** 角色组。 若要在初始配置后访问和管理内幕风险管理功能，用户必须是至少一个 "内幕风险管理" 角色组的成员。

根据合规性管理团队的结构，您可以选择将用户分配给特定角色组，以管理不同的内幕风险管理功能集。 配置内幕风险管理时从这些角色组选项中进行选择：

| **角色组** | **角色权限** |
| :---- | :---------------- |
| **内幕风险管理** | 使用此角色组可在单个组中管理组织的内幕风险管理。 通过添加指定管理员、分析师和调查人员的所有用户帐户，您可以在单个组中配置内幕风险管理权限。 此角色组包含所有内幕风险管理权限角色。 此配置是快速开始使用 "内幕风险管理" 的最简单方法，非常适合于不需要为单独的用户组定义单独权限的组织。|
| **内幕风险管理管理员** | 使用此角色组最初配置内幕风险管理和更高版本，以便将内幕风险管理员与定义的组分离。  此角色组中的用户可以创建、读取、更新和删除内幕风险管理策略、全局设置和角色组分配。 |
| **内幕风险管理分析师** | 使用此组可将权限分配给将充当内幕风险案例分析人员的用户。 此角色组中的用户可以访问所有内幕风险管理警报、案例和通知模板。 他们无法访问内幕风险内容浏览器。 |
| **内幕风险管理调查人员** | 使用此组可将权限分配给将充当内部人员风险数据调查人员的用户。 此角色组中的用户可以访问所有内幕风险管理警报、案例、通知模板和内容浏览器。 |

> [!NOTE]
> 这些角色组目前在特权身份管理 (PIM) 上不受支持。 若要了解有关 PIM 的详细信息，请参阅 [在特权标识管理中分配 AZURE AD 角色](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-how-to-add-role-to-user)。

### <a name="add-users-to-an-insider-risk-management-role-group"></a>将用户添加到 "内幕风险管理" 角色组

完成以下步骤以将用户添加到 "内幕风险管理" 角色组：

1. [https://protection.office.com/permissions](https://protection.office.com/permissions)在 Microsoft 365 组织中使用管理员帐户的凭据进行登录。

2. 在 "安全 &amp; 合规性中心" 中，转到 " **权限** "。 选择用于查看和管理 Office 365 中的角色的链接。

3. 选择要向其添加用户的 "内幕风险管理" 角色组，然后选择 " **编辑角色组** "。

4. 从左侧导航窗格中选择 " **选择成员** "，然后选择 " **编辑** "。

5. 选择 " **添加** "，然后选中要添加到角色组的所有用户的复选框。

6. 选择 " **添加** "，然后选择 " **完成** "。

7. 选择 " **保存** " 将用户添加到角色组。 选择 " **关闭** " 完成这些步骤。

## <a name="step-2-enable-the-audit-log"></a>步骤2：启用审核日志

内幕风险管理对在策略中配置的用户见解和活动使用审核日志。 审核日志汇总了与内幕风险管理策略关联的所有活动，或只要更改了策略。

有关启用审核的分步说明，请参阅 [打开或关闭审核日志搜索](turn-audit-log-search-on-or-off.md)。 启用审核后，会显示一条消息，指出正在准备审核日志，并且您可以在准备完成后的几小时内运行搜索。 您只需执行一次此操作。 有关使用审核日志的详细信息，请参阅 [Search the audit log](search-the-audit-log-in-security-and-compliance.md)。

## <a name="step-3-configure-prerequisites-for-templates"></a>步骤3：配置模板的必备组件

大多数内幕风险管理模板都具有必须为策略指示器配置的先决条件，以生成相关的活动通知。 根据计划为组织配置的策略配置适当的先决条件。

如果使用电子邮件策略模板中的 *冒犯性语言* 配置策略，则可以跳过此步骤，直接转到 **步骤 4** 。

### <a name="configure-microsoft-365-hr-connector"></a>配置 Microsoft 365 HR 连接器

内幕风险管理支持导入从第三方风险管理和人力资源平台导入的用户和日志数据。 Microsoft 365 人力资源 (HR) 数据连接器允许您从 CSV 文件中提取人力资源数据，包括用户终止日期、最后的雇用日期、性能改进计划通知、性能审核操作和作业级更改状态。 此数据可帮助推动内幕风险管理策略中的警报指示器，这是在组织中配置完全风险管理覆盖范围的重要部分。 如果您为您的组织配置了多个 HR 连接器，内幕风险管理将自动从所有 HR 连接器中提取指示器。

使用以下策略模板时，需要使用 Microsoft 365 HR 连接器：

- 脱离用户数据失窃
- 通过去声用户违反安全策略
- 因不满用户而违反安全策略
- 因不满用户而进行的数据泄露

有关为您的组织配置 Microsoft 365 HR 连接器的分步指南，请参阅 [设置连接器以导入 HR 数据一](import-hr-data.md) 文。 配置 HR 连接器后，请返回到这些配置步骤。

### <a name="configure-data-loss-prevention-dlp-policies"></a>配置数据丢失防护 (DLP) 策略

内幕风险管理支持使用 DLP 策略来帮助将敏感信息的有意或无意暴露给不需要的高严重性级别 DLP 警报。 在使用任何 **数据泄漏** 模板配置内幕风险管理策略时，必须向策略分配特定的 DLP 策略。

DLP 策略有助于标识用户在内部人员风险管理中激活风险评分，以实现高严重性 DLP 警报的敏感信息，这是在组织中配置完全风险管理覆盖范围的重要部分。 有关内幕风险管理和 DLP 策略集成和规划注意事项的详细信息，请参阅 [内幕风险管理策略](insider-risk-management-policies.md#general-data-leaks)。

>[!IMPORTANT]
>请确保已完成以下操作：
>
>- 您了解并正确配置了 DLP 和有问必答风险管理策略中的范围内用户，以生成预期的策略覆盖范围。
>- 请确保为使用这些模板的内幕策略管理的 DLP 策略中的 " **事件报告** " 设置配置了 *高* 严重性级别警报。 内幕风险管理警报不会从具有 " **事件报告** " 字段设置为 " *低* " 或 " *中* " 的 DLP 策略生成。

使用以下策略模板时，DLP 策略是必需的：

- 常规数据泄露
- 按优先级用户的数据泄露

有关为您的组织配置 DLP 策略的分步指南，请参阅 [创建、测试和调整 DLP 策略一](create-test-tune-dlp-policy.md) 文。 配置 DLP 策略后，请返回到这些配置步骤。

### <a name="configure-priority-user-groups"></a>配置优先级用户组

内幕风险管理支持将优先级用户组分配给策略，以帮助标识具有关键位置、高级别的数据和网络访问或过去的风险行为历史记录的用户的唯一风险活动。 创建一个优先级用户组，并将用户分配到组帮助范围策略，以满足这些用户呈现的独特情况。

使用以下策略模板时，优先级用户组是必需的：

- 优先级用户违反安全策略
- 按优先级用户的数据泄露

有关创建优先级用户组的分步指南，请参阅 [开始使用内幕风险管理设置](insider-risk-management-settings.md#priority-user-groups-preview) 一文。 配置了优先级用户组之后，请返回这些配置步骤。

### <a name="configure-physical-badging-connector-optional"></a>配置物理徽章连接器 (可选) 

内幕风险管理支持导入从物理控制和访问平台导入的用户和日志数据。 通过物理徽章连接器，可以从 JSON 文件中提取 access 数据，其中包括用户 Id、访问点 Id、访问时间和日期以及访问状态。 此数据可帮助推动内幕风险管理策略中的警报指示器，这是在组织中配置完全风险管理覆盖范围的重要部分。 如果为组织配置了多个物理徽章连接器，内幕风险管理将自动从所有物理徽章连接器中提取指示器。 当使用所有内幕风险策略模板时，物理徽章连接器中的信息将补充其他内幕风险信号。

>[!IMPORTANT]
>若要使用内部风险管理策略并将与传出和终止用户相关的信号数据与您的物理控制和访问平台中的事件数据关联起来，您还必须配置 Microsoft 365 HR 连接器。 如果在不启用 Microsoft 365 HR 连接器的情况下启用物理徽章连接器，则内幕风险管理策略将仅处理组织中用户的未经授权物理访问的事件。

有关为组织配置物理徽章连接器的分步指南，请参阅 [设置连接器以导入物理徽章 data](import-physical-badging-data.md) 一文。 配置连接器后，请返回到这些配置步骤。

## <a name="step-4-configure-insider-risk-settings"></a>步骤4：配置内幕风险设置

[内幕风险设置](insider-risk-management-settings.md) 适用于所有内幕风险管理策略，而不管您在创建策略时选择的模板如何。 设置是使用位于所有内幕风险管理选项卡顶部的 " **内幕风险设置** " 控件配置的。 这些设置控制隐私、指示器、监视窗口和智能检测。

在配置策略之前，请定义以下内幕风险设置：

1. 在 [Microsoft 365 合规性中心](https://compliance.microsoft.com)中，转到 " **内幕风险管理** "，并从任意页面右上角选择 " **内幕风险设置** "。
2. 在 " **隐私** " 页上，选择用于显示策略通知的用户名的隐私设置。
3. 在 " **指标** " 页上，选择要应用于所有内幕风险策略的警报指示器。

    >[!IMPORTANT]
    >为了接收在策略中定义的有风险的活动的警报，您必须选择一个或多个指示器。

4. 在 " **策略时段** " 页上，选择 [策略](insider-risk-management-settings.md#policy-timeframes) 时间段，以便在触发 "内幕风险策略" 的匹配项时对用户生效。
5. 在 " **智能检测** " 页上，为 "内幕风险策略" 配置以下设置：
    - [异常检测](insider-risk-management-settings.md#anomaly-detections)
    - [攻击性语言检测](insider-risk-management-settings.md#offensive-language-detections)
    - [警报音量级别](insider-risk-management-settings.md#alert-volume)
    - [Microsoft Defender for Endpoint 警报状态](insider-risk-management-settings.md#microsoft-defender-for-endpoint-preview)
    - [域设置](insider-risk-management-settings.md#domains-preview)
6. 在 " **导出通知** " 页面上，启用 "使用 Office 365 管理 api 导出内幕风险警报信息（如果需要）"。
7. 在 " **优先级用户组** " 页上，创建一个优先级用户组并添加用户（如果在 **步骤 3** 中未创建）。
8. 在 " **电源自动流** " 页上，配置来自内幕风险流模板的流或创建新流。 有关分步指导，请参阅 " [内幕风险管理设置](insider-risk-management-settings.md#power-automate-flows-preview) " 一文中的 "入门"。
9. 在 " **优先级资产" 页面** 上，配置优先级资产以使用物理控制和物理徽章连接器导入的访问平台中的数据。 有关分步指导，请参阅 " [内幕风险管理设置](insider-risk-management-settings.md#priority-physical-assets-preview) " 一文中的 "入门"。
10. 在 " **Microsoft 团队** " 页面上，启用 microsoft 团队与内幕风险管理的集成，以自动为案例或用户协作创建团队。 有关分步指导，请参阅 " [内幕风险管理设置](insider-risk-management-settings.md#microsoft-teams-preview) " 一文中的 "入门"。
11. 选择 " **保存** " 为您的内幕风险策略启用这些设置。

## <a name="step-5-create-an-insider-risk-management-policy"></a>步骤5：创建内幕风险管理策略

内幕风险管理策略包括分配的用户并定义为通知配置的风险指示器类型。 在活动可以触发通知之前，必须配置策略。

1. 在 [Microsoft 365 合规性中心](https://compliance.microsoft.com)中，转到 " **内幕风险管理** "，然后选择 " **策略** " 选项卡。
2. 选择 " **创建策略** " 以打开策略向导。
3. 在 " **新建内幕风险策略** " 页上，填写下列字段：
    - **Name (必需的)** ：为策略输入一个友好名称。
    - **Description (可选)** ：输入策略的说明。
    - **选择 "策略模板" (必需的)** ：选择一个 [策略模板](insider-risk-management-policies.md#policy-templates) 以定义由策略监视的风险指示器类型。

    >[!IMPORTANT]
    >大多数策略模板都具有必须为策略配置的先决条件，以生成相关警报。 如果尚未配置适用的策略先决条件，请参阅上面的 **步骤 3** 。

    >[!CAUTION]
    >从2020年10月16日开始，你将无法再使用电子邮件模板中的冒犯性语言创建策略。 使用此模板的任何活动策略将一直运行，直到在2021年1月永久删除。

4. 选择 " **下一步** " 继续。
5. 在 " **用户** " 页上，选择 " **添加用户或组** " 或 **选择 "优先级用户组** " 来定义哪些用户或优先级的用户组包括在策略中，具体取决于所选的策略模板。 如果还没有选择基于用户的模板) 的优先级，则选中 " **所有用户和已启用邮件的组** " 复选框（如果适用） (。 选择 " **下一步** " 继续。
6. 在 " **指定要优先处理哪些内容 (可选的)** " 页上，您可以分配源以优先考虑增加的风险分数。 但是，除非相关内容包含内置或自定义敏感信息类型或在此页面上指定为优先级，否则一些活动将不会生成警报：
    - **SharePoint 网站** ：选择 " **添加 SharePoint 网站** "，然后选择要设置优先顺序的 SharePoint 组织。 例如， *"group1@contoso.sharepoint.com/sites/group1"* 。
    - **敏感信息类型** ：选择 " **添加敏感信息类型** "，然后选择要设置优先级的敏感度类型。 例如， *"美国银行帐户号码"* 和 *"信用卡号码"* 。
    - **敏感度标签** ：选择 " **添加灵敏度标签** "，然后选择要设置优先顺序的标签。 例如， *"保密"* 和 *"Secret"* 。
7. 选择 " **下一步** " 继续。
8. 在 " **选择策略指示器** " 页上，您将看到您在 " **内幕风险设置** 指示器" 页上定义为 "可用" 的 [指示器](insider-risk-management-settings.md#indicators)  >  **Indicators** 。 如果在向导的开头选择了 *数据泄露* 模板，则必须从 " **dlp 策略** " 下拉列表中选择一个 DLP 策略，以便为该策略启用触发指示器。 选择要应用于策略的指示器。 如果您不希望对这些指示器使用默认策略阈值设置，请禁用 " **使用 Microsoft 建议的默认阈值** "，并为每个选定的指标输入阈值。 如果已选择至少一个 *办公室* 或 *设备* 指示器，请根据需要选择 **风险分数 boosters** 。 风险分数 boosters 仅适用于所选指示器。

    >[!IMPORTANT]
    >如果无法选择此页上的指标，您需要在 " **内幕风险管理**  >  **设置**  >  **策略指示器** " 页上选择要为所有策略启用的指示器。

9. 选择 " **下一步** " 继续。
10. 在 " **策略时段** " 页面上，您将在 " **内幕风险设置** 策略时间段" 页上看到 "策略" 的 [激活窗口条件](insider-risk-management-settings.md#policy-timeframes)  >  **Policy timeframes** 。
11. 选择 " **下一步** " 继续。
12. 在 " **检查** " 页上，查看您为策略选择的设置。 选择 " **编辑** " 以更改任何策略值，或选择 " **提交** " 以创建并激活策略。

## <a name="next-steps"></a>后续步骤

完成这些步骤以创建第一个 "有问必答" 风险管理策略后，您将在大约24小时后开始接收来自活动指示器的警报。 使用本文步骤4中的指导或 [创建新的内幕风险策略](insider-risk-management-policies.md#create-a-new-policy)中的步骤，根据需要配置其他策略。

若要了解有关调查内幕风险警报和 **警报仪表板** 的详细信息，请参阅 [内幕风险管理警报](insider-risk-management-alerts.md)。
