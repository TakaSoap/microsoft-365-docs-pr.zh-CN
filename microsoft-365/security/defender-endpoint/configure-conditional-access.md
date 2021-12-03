---
title: 在 Microsoft Defender for Endpoint 中配置条件访问
description: 了解在 Intune、Microsoft 365 Defender 和 Azure 中实现条件访问需要执行的步骤
keywords: 条件访问， 条件， 访问， 设备风险， 风险级别， 集成， intune 集成
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 8706f756b4e8d0ba87a747396e8f7ef71d66460c
ms.sourcegitcommit: c11d4a2b9cb891ba22e16a96cb9d6389f6482459
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/03/2021
ms.locfileid: "61284369"
---
# <a name="configure-conditional-access-in-microsoft-defender-for-endpoint"></a>在 Microsoft Defender for Endpoint 中配置条件访问

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint 计划 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要体验适用于终结点的 Defender？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-assignaccess-abovefoldlink)。

本节指导您完成正确实现条件访问需要执行的所有步骤。

## <a name="before-you-begin"></a>开始之前

> [!WARNING]
> 需要注意的是，此Azure AD不支持已注册的设备。</br>
> 仅支持 Intune 注册的设备。

你需要确保你的所有设备都注册到 Intune 中。 可以使用以下任一选项在 Intune 中注册设备：

- IT 管理员：若要详细了解如何启用自动注册，请参阅Windows[注册](/intune/windows-enroll#enable-windows-10-automatic-enrollment)
- 最终用户：若要详细了解如何在 Intune 中注册 Windows 10 和 Windows 11 设备，请参阅在[Intune](/intune/quickstart-enroll-windows-device)中注册 Windows 10 设备
- 最终用户替代方法：有关加入域Azure AD，请参阅如何：规划你的Azure AD[加入实现](/azure/active-directory/devices/azureadjoin-plan)。

在应用门户、Intune 门户Microsoft 365 Defender需要执行Azure AD步骤。

请注意访问这些门户和实现条件访问所需的角色：

- **Microsoft 365 Defender** - 你需要使用一个 全局管理员角色 登录门户，以打开集成。
- **Intune** - 你需要使用具有管理权限的安全管理员权限登录门户。
- **Azure AD** 门户 - 你需要以全局管理员、安全管理员或条件访问管理员登录。

> [!NOTE]
> 你将需要一个Microsoft Intune环境，并且 Intune 托管Azure AD设备Windows 10 Windows 11设备。

执行以下步骤以启用条件访问：

- 步骤 1：打开Microsoft Intune连接Microsoft 365 Defender
- 步骤 2：在 Intune 中打开 Defender for Endpoint 集成
- 步骤 3：在 Intune 中创建合规性策略
- 步骤 4：分配策略 
- 步骤 5：创建Azure AD访问策略

### <a name="step-1-turn-on-the-microsoft-intune-connection"></a>步骤 1：打开Microsoft Intune连接

1. 在导航窗格中，**选择"设置** \>  \> **终结点""** \> **常规高级Microsoft Intune** \> **连接"。**
2. 将"Microsoft Intune"设置为 **"打开"。**
3. 单击 **保存首选项**。

### <a name="step-2-turn-on-the-defender-for-endpoint-integration-in-intune"></a>步骤 2：在 Intune 中打开 Defender for Endpoint 集成

1. 登录 [Azure 门户](https://portal.azure.com)。
2. 选择 **设备合规性** \> **Microsoft Defender ATP**。
3. 将 **连接 Windows 10.0.15063+** 设备设置为"打开"Microsoft Defender 高级威胁 **防护**。
4. 单击 **“保存”**。

### <a name="step-3-create-the-compliance-policy-in-intune"></a>步骤 3：在 Intune 中创建合规性策略

1. 在 [Azure 门户中](https://portal.azure.com)，选择 **"所有服务"，** 筛选 **Intune，** 然后选择 **"Microsoft Intune"。**
2. 选择 **"设备合规性** \> **策略** \> **""创建策略"。**
3. 输入"**名称"** 和"**说明"。**
4. 在 **"平台**"中 **，Windows 10"和"更高版本"。**
5. 在 **"设备运行状况** "设置中，将"要求设备位于设备威胁级别或以下设备威胁级别 **"设置为首选** 级别：

   - **安全**：此级别是最安全的威胁级别。 设备无法具有任何现有威胁，并且仍访问公司资源。 如果发现了任何威胁，设备都会被评估为不符合。
   - **低**：如果设备上仅存在低级别威胁，则该设备符合策略。 具有中等或高威胁级别的设备不兼容。
   - **中**：如果设备上发现的威胁为低级别或中等级别，则该设备符合策略。 如果检测到高级别威胁，则设备会被确定为不合规。
   - **高**：此级别最不安全，允许所有威胁级别。 因此，具有高、中或低威胁级别的设备被视为兼容设备。

6. 选择 **"确定**"和" **创建** "以保存 (并创建策略) 。

### <a name="step-4-assign-the-policy"></a>步骤 4：分配策略

1. 在 [Azure 门户中](https://portal.azure.com)，选择 **"所有服务"，** 筛选 **Intune，** 然后选择 **"Microsoft Intune"。**
2. 选择 **设备合规性** \> **策略**>选择适用于终结点的 Microsoft Defender 合规性策略。
3. 选择“**分配**”。
4. 包括或排除Azure AD组，以为其分配策略。
5. 若要将策略部署到组，请选择"保存 **"。** 针对策略的目标用户设备进行评估是否符合合规性。

### <a name="step-5-create-an-azure-ad-conditional-access-policy"></a>步骤 5：创建Azure AD访问策略

1. 在 [Azure 门户中](https://portal.azure.com)，打开 **Azure Active Directory** \> **条件访问** \> **新策略"。**
2. 输入策略"**名称"，** 然后选择"**用户和组"。** 使用“包括”或“排除”选项来添加策略的组，然后选择 **“完成”**。
3. 选择 **"云** 应用"，然后选择要保护的应用。 例如，选取“**选择应用**”，然后选择“**Office 365 SharePoint Online**”和“**Office 365 Exchange Online**”。 选择“**完成**”以保存更改。

4. 选择 \> **条件 客户端应用**，将策略应用于应用和浏览器。 例如，选择“是”，然后启用“浏览器”和“移动应用和桌面客户端”。 选择“**完成**”以保存更改。

5. 选择“授予”，应用基于设备符合性的条件访问。 例如，选择"**授予访问权限** \> **要求设备标记为合规"。** 选取“选择”，保存所做的更改。

6. 选择“**启用策略**”，然后选择“**创建**”以保存更改。

有关详细信息，请参阅[在 Intune 中使用条件访问强制执行 Microsoft Defender for Endpoint 的合规性](/intune/advanced-threat-protection)。

> 想要体验适用于终结点的 Defender？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-conditionalaccess-belowfoldlink)。
