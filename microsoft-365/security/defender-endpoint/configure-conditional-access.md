---
title: 在 Microsoft Defender for Endpoint 中配置条件访问
description: 了解在 Intune、Microsoft 365 Defender 和 Azure 中实现条件访问需要执行的步骤
keywords: 条件访问， 条件， 访问， 设备风险， 风险级别， 集成， intune 集成
search.product: eADQiWindows 10XVcnh
search.appverid: met150
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
ms.openlocfilehash: 75b74024b7f4e94d1b24b2f926bfe488a8e594b1
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60192987"
---
# <a name="configure-conditional-access-in-microsoft-defender-for-endpoint"></a>在 Microsoft Defender for Endpoint 中配置条件访问

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要体验适用于终结点的 Defender？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-assignaccess-abovefoldlink)。

本节指导您完成正确实现条件访问需要执行的所有步骤。

## <a name="before-you-begin"></a>准备工作

> [!WARNING]
> 需要注意的是，此方案不支持已注册 Azure AD 的设备。</br>
> 仅支持 Intune 注册的设备。

你需要确保所有设备都注册到 Intune 中。 可以使用以下任一选项在 Intune 中注册设备：

- IT 管理员：若要详细了解如何启用自动注册，请参阅Windows[注册](/intune/windows-enroll#enable-windows-10-automatic-enrollment)
- 最终用户：若要详细了解如何在 Intune 中注册 Windows 10 设备，请参阅在[Intune 中](/intune/quickstart-enroll-windows-device)注册 Windows 10 设备
- 最终用户替代：若要详细了解如何加入 Azure AD 域，请参阅如何：规划 [Azure AD 加入实现](/azure/active-directory/devices/azureadjoin-plan)。

在应用、Intune 门户和 Azure AD Microsoft 365 Defender需要执行一些步骤。

请注意访问这些门户和实现条件访问所需的角色：

- **Microsoft 365 Defender** - 你需要使用一个 全局管理员角色 登录门户，以打开集成。
- **Intune** - 你需要使用具有管理权限的安全管理员权限登录门户。
- **Azure AD 门户** - 你需要以全局管理员、安全管理员或条件访问管理员登录。

> [!NOTE]
> 你将需要一个Microsoft Intune环境，并且 Intune 托管和 Azure AD 已加入Windows 10设备。

执行以下步骤以启用条件访问：

- 步骤 1：打开Microsoft Intune连接Microsoft 365 Defender
- 步骤 2：在 Intune 中打开 Defender for Endpoint 集成
- 步骤 3：在 Intune 中创建合规性策略
- 步骤 4：分配策略 
- 步骤 5：创建 Azure AD 条件访问策略

### <a name="step-1-turn-on-the-microsoft-intune-connection"></a>步骤 1：打开Microsoft Intune连接

1. 在导航窗格中，**选择"设置** \>  \> **终结点""** \> **常规高级Microsoft Intune** \> **连接"。**
2. 将"Microsoft Intune"设置为 **"打开"。**
3. 单击 **保存首选项**。

### <a name="step-2-turn-on-the-defender-for-endpoint-integration-in-intune"></a>步骤 2：在 Intune 中打开 Defender for Endpoint 集成

1. 登录到 [Azure 门户](https://portal.azure.com)。
2. 选择 **设备合规性** \> **Microsoft Defender ATP**。
3. 将 **连接 Windows 10.0.15063+ 设备设置为"打开"。。** 
4. 单击“**保存**”。

### <a name="step-3-create-the-compliance-policy-in-intune"></a>步骤 3：在 Intune 中创建合规性策略

1. 在 [Azure 门户中，](https://portal.azure.com)选择 **"所有服务"，** 筛选 **Intune，** 然后选择"Microsoft Intune"。 
2. 选择 **"设备合规性** \> **策略** \> **""创建策略"。**
3. 输入"**名称"** 和"**说明"。**
4. 在 **平台** 中，选择 **Windows 10和更高版本**。
5. 在 **"设备运行状况** "设置中，将"要求设备位于设备威胁级别或以下设备威胁级别 **"设置为首选** 级别：

   - **Secured：** 此级别是最安全级别。 设备无法具有任何现有威胁，并且仍访问公司资源。 如果发现任何威胁，则评估设备不相容。
   - **低**：如果仅存在低级别威胁，则设备合规。 具有中等或高威胁级别的设备不兼容。
   - **中**：如果设备上发现的威胁较低或中等，则设备合规。 如果检测到高级威胁，则设备被确定为不符合要求。
   - **高**：此级别最不安全，允许所有威胁级别。 因此，具有高、中或低威胁级别的设备被视为兼容设备。

6. 选择 **"确定**"和" **创建** "以保存 (并创建策略) 。

### <a name="step-4-assign-the-policy"></a>步骤 4：分配策略

1. 在 [Azure 门户中，](https://portal.azure.com)选择 **"所有服务"，** 筛选 **Intune，** 然后选择"Microsoft Intune"。 
2. 选择 **设备合规性** \> **策略**>选择适用于终结点的 Microsoft Defender 合规性策略。
3. 选择“**分配**”。
4. 包括或排除 Azure AD 组，以为其分配策略。
5. 若要将策略部署到组，请选择"保存 **"。** 针对策略的目标用户设备进行评估是否符合合规性。

### <a name="step-5-create-an-azure-ad-conditional-access-policy"></a>步骤 5：创建 Azure AD 条件访问策略

1. 在 [Azure 门户中，](https://portal.azure.com)打开 **Azure Active Directory** \> **条件访问** \> **新策略"。**
2. 输入策略"**名称"，** 然后选择"**用户和组"。** 使用包含或排除选项为策略添加组，**然后选择完成。**
3. 选择 **"云** 应用"，然后选择要保护的应用。 例如，选择 **选择应用，** 然后选择Office 365 SharePoint **在线****和Office 365 Exchange Online。** 选择“**完成**”以保存更改。

4. 选择 \> **条件 客户端应用**，将策略应用于应用和浏览器。 例如，选择"**是"，** 然后启用 **"浏览器** 和 **移动应用和桌面客户端"。** 选择“**完成**”以保存更改。

5. 选择 **"授予** "以基于设备合规性应用条件访问。 例如，选择"**授予访问权限** \> **要求设备标记为合规"。** 选择 **"选择** "保存更改。

6. 选择 **"启用策略**"，然后选择" **创建** "保存更改。

有关详细信息，请参阅在 Intune 中强制执行 [Microsoft Defender for Endpoint 的合规性和条件访问](/intune/advanced-threat-protection)。

> 想要体验适用于终结点的 Defender？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-conditionalaccess-belowfoldlink)。
