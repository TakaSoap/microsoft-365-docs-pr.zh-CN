---
title: 管理 IT 管理员Office文档中的活动内容
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: tutorial
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
ROBOTS: NOINDEX,NOFOLOW
description: 管理员可以了解如何创建策略以阻止文档中的活动Office内容
ms.openlocfilehash: 5bc187caaeac2fb83cb7d5a8026af2e1548c5622
ms.sourcegitcommit: dd6514ae173f1c821d4ec25298145df6cb232e2e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/19/2022
ms.locfileid: "62074662"
---
# <a name="manage-active-content-in-office-documents"></a>管理 Office 文档中的活动内容

> [!NOTE]
> 本文中介绍的功能为预览版，不可供所有人使用，并且可能会更改。

Office文档包含活动内容时，可自动刷新、更新或 _执行这些文档_。 活动内容的示例包括宏、ActiveX控件Office加载项。活动内容可以为用户提供强大且有用的功能，但攻击者也可使用活动内容传送恶意软件。

管理员可以创建组织策略 (组策略或云) 组策略，以将活动内容的使用限制为特定用户集，或完全禁用活动内容。 用户可以在文件选项信任中心的 Office 应用中配置自己的Office安全和 \>  \> **隐私设置**。

以前，当用户将文档标识为受信任的文档时，用户的选择将允许运行活动内容，即使管理员配置了策略来阻止文档中的活动Office内容。 现在，管理员设置的策略优先于受信任文档的用户标识。 此行为更改可能会导致用户问题。

更新的信任中心逻辑如下图所示：

:::image type="content" source="../media/office-trust-center-flow.png" alt-text="描述门户中信任中心逻辑Microsoft 365 Defender示例" lightbox="../media/office-trust-center-flow.png":::

1. 用户打开一个Office活动内容的文档。

2. 如果文档来自受信任位置，则打开文档时启用活动内容。 如果文档不是来自受信任位置，则继续评估。

3. 这是更新的行为生效的地方：
   - 以前，如果用户将该文档标识为受信任的文档，则下一个已评估设置。 如果已打开，文档将在启用活动内容后打开。
   - 现在，用户是否将文档标识为受信任文档未在此处 (步骤 8) 。

     这是行为的基本更改：云策略 (步骤 4) 、组策略 (步骤 6) 和本地设置 (step 7) ，然后再考虑用户指定受信任文档。  如果其中任一步骤阻止访问活动内容，并且任何步骤均不允许用户重写，则用户将文档标识为受信任的文档基本上不相关。

4. 检查云策略以查看是否允许或阻止此类活动内容。 如果未阻止活动内容，则评估将继续执行步骤 6。

   如果策略阻止活动内容，则步骤 5 中将介绍此体验。

5. 在信任栏中阻止打开文档，并发送通知。 接下来会发生什么情况由用户替代策略中的设置控制：a. **不允许用户替代**：用户无法打开文档，评估将停止。
   b. **允许用户** 替代：用户可以单击信任栏中的链接以打开启用了活动内容的文档。

6. 检查组策略以查看是否允许或阻止此类活动内容。 如果未阻止活动内容，则评估将继续执行步骤 7。

   如果策略阻止活动内容，则步骤 5 中将介绍此体验。

7. 检查本地设置以查看是否允许或阻止此类型的活动内容。 如果活动内容被阻止，则通过信任栏中的通知阻止打开文档。 如果未阻止活动内容，则继续评估。

8. 如果用户之前将文档标识为受信任的文档，则打开文档时启用活动内容。 如果不是，则阻止打开文档。

## <a name="what-is-a-trusted-document"></a>什么是受信任的文档？

受信任文档Office打开的文档，无需任何安全提示即可打开ActiveX控件和文档中的其他类型的活动内容。 受保护的视图或应用程序防护不用于打开文档。 当用户打开受信任的文档，并且所有活动内容都已启用时。 即使文档包含新的活动内容或对现有活动内容的更新，用户也不会在下次打开文档时收到安全提示。

由于此行为，只有在用户信任文档源时，他们才应明确信任文档。

如果管理员使用策略阻止活动内容，或者用户设置了阻止活动内容的信任中心设置，则活动内容仍将被阻止。

有关详细信息，请参阅以下文章：

- [受信任的文档](https://support.microsoft.com/topic/trusted-documents-cf872bd8-47ec-4c02-baa5-1fdba1a11b53)
- [添加、删除或更改受信任位置](https://support.microsoft.com/topic/add-remove-or-change-a-trusted-location-7ee1cdc2-483e-4cbb-bcb3-4e7c67147fb4)
- [文件中的活动内容类型](https://support.microsoft.com/topic/active-content-types-in-your-files-b7ff2e8a-4055-47d4-8c7d-541e19f62bea)

## <a name="configure-trusted-document-settings-in-office-policies"></a>在策略中配置受信任Office设置

管理员有许多方法在组织中Office配置策略。 例如：

- **Office云策略** 服务：设置基于用户的策略，该策略适用于使用其 Azure AD 帐户访问 Office 应用中文件的任何Azure AD用户。 请参阅在云[策略服务Office云策略Office](/DeployOffice/overview-office-cloud-policy-service)[的步骤](https://config.office.com/officeSettings/officePolicies)。
- **Office Intune** 中的策略：使用 Intune 设置 目录或管理模板将 HKCU 策略部署到 Windows 10 电脑：在 [MEM](https://endpoint.microsoft.com/#blade/Microsoft_Intune_DeviceSettings/DevicesMenu/configurationProfiles)管理中心的 **"设备** 配置文件" \> **下**。
  - ***管理模板***：请参阅使用管理Windows 10配置 [管理模板的说明](/mem/intune/configuration/administrative-templates-windows)。
  - ***设置目录 (预览) ：*** 请参阅使用预览设置目录 [ () 。](/mem/intune/configuration/settings-catalog)
- **组策略**：使用本地 Active Directory 将组策略对象 (GPO) 用户和计算机。 若要为此设置创建 GPO，请下载适用于[Microsoft 365 企业应用版、Office 2019 和 Office 2016 的最新管理模板文件 (ADMX/ADML) ](https://www.microsoft.com/download/details.aspx?id=49030)和 Office 自定义工具。

## <a name="known-issues"></a>已知问题

- 当策略 **VBA** 宏通知 (Access、PowerPoint、Visio、Word) 或宏通知 **(Excel)** 设置为值 Disable **all except digitally signed macros** 时，不会显示预期的信任栏，并且 backstage 中的安全信息不会列出阻止的宏的详细信息，即使该设置按预期工作。  Office团队正在努力解决此问题。

## <a name="admin-options-for-restricting-active-content"></a>用于限制活动内容的管理员选项

与用户从 Internet 下载的内容相比，内部创建的内容的信任级别存在很大差异。 请考虑允许内部文档中的活动内容，并且全局不允许来自 Internet 的文档中的活动内容。

如果用户不需要特定类型的活动内容，最安全的选项是使用策略来关闭用户对活动内容的访问，并根据需要允许例外。

以下策略可用：

- **关闭"受信任位置**：可用的组例外"。
- **关闭"受信任的文档**：可用的组例外"。
- **关闭所有活动内容**：个人例外。

以下各节中的表介绍了控制活动内容的设置。 这些策略（如果应用于用户）将在受信任的文档上强制执行，并且以前的最终用户体验可能不同。 这些表还包括建议的安全基线设置，并确定用户提示进行覆盖的其他设置 (以允许用户启用活动内容) 。

### <a name="hkey_current_user-settings"></a>HKEY_CURRENT_USER设置

<p>

****
|类别|应用|策略名称|安全基线<br>setting (recommended) |使用用户提示进行设置<br>和 替代可用？|
|---|---|---|---|---|
|ActiveX|Office|ActiveX控件初始化|**6**|**对于** 以下值，为"是"： <ul><li>**3**</li><li>**4**</li><li>**5**</li><li>**6**</li></ul>|
|ActiveX|Office|允许活动 X 一次窗体|**仅加载 Outlook 控件**|否|
|ActiveX|Office|检查 ActiveX 对象|不是安全基线设置。|否|
|ActiveX|Office|禁用所有 ActiveX|不是安全基线设置。|**对于** 以下值，为"是"： <ul><li>**Disabled**</li><li>**未配置**</li></ul>|
|ActiveX|Office|在 Forms3 中加载控件|**1**|**对于** 以下值，为"是"： <ul><li>**2**</li><li>**3**</li></ul>|
|外接程序&可扩展性|Excel <p> PowerPoint <p> Project <p> Publisher <p> Visio <p> Word|禁用未签名应用程序加载项的信任栏通知并阻止它们|**Enabled**|**是** ，表示值 **Disabled**。|
|外接程序&可扩展性|Excel <p> PowerPoint <p> Project <p> Publisher <p> Visio <p> Word|要求由受信任发布者签署应用程序加载项|**Enabled**|否|
|外接程序&可扩展性|Excel|不显示自动重新发布警告警告|**Disabled**|否|
|外接程序&可扩展性|Excel|WEBSERVICE 函数通知设置|**禁用所有宏，并发出通知**|**对于** 以下值，为"是"： <ul><li>**禁用所有宏，并发出通知**</li><li>**Disabled**</li><li>**未配置**</li></ul>|
|外接程序&可扩展性|Office|禁止Office客户端轮询 SharePoint Server 中的链接|**Disabled**|否|
|外接程序&可扩展性|Office|禁用文档和模板中的 UI 扩展|在 Word 中禁止 = True <p> 不允许在 Project = False <p> 不允许在 Excel = True <p> 不允许在 Visio= False <p> 不允许在 PowerPoint = True <p> Access 中禁止访问 = True <p> 不允许在 Outlook = True <p> 不允许在 Publisher = True <p> 在 InfoPath 中不允许 = True|否|
|外接程序&可扩展性|Outlook|配置访问通讯簿时的 Outlook 对象模型提示|**自动拒绝**|**对于** 以下值，为"是"： <ul><li>**提示用户**</li><li>**根据计算机安全设置提示用户**</li><li>**Disabled**</li><li>**未配置**</li></ul>|
|外接程序&可扩展性|Outlook|配置Outlook对象模型提示 访问 UserProperty 对象的 Formula 属性时|**自动拒绝**|**对于** 以下值，为"是"： <ul><li>**提示用户**</li><li>**根据计算机安全设置提示用户**</li><li>**Disabled**</li><li>**未配置**</li></ul>|
|外接程序&可扩展性|Outlook|配置执行“另存为”操作时的 Outlook 对象模型提示|**自动拒绝**|**对于** 以下值，为"是"： <ul><li>**提示用户**</li><li>**根据计算机安全设置提示用户**</li><li>**Disabled**</li><li>**未配置**</li></ul>|
|外接程序&可扩展性|Outlook|配置读取地址信息时的 Outlook 对象模型提示|**自动拒绝**|**对于** 以下值，为"是"： <ul><li>**提示用户**</li><li>**根据计算机安全设置提示用户**</li><li>**Disabled**</li><li>**未配置**</li></ul>|
|外接程序&可扩展性|Outlook|配置响应会议和任务要求时的 Outlook 对象模型提示|**自动拒绝**|**对于** 以下值，为"是"： <ul><li>**提示用户**</li><li>**根据计算机安全设置提示用户**</li><li>**Disabled**</li><li>**未配置**</li></ul>|
|外接程序&可扩展性|Outlook|配置发送邮件时的 Outlook 对象模型提示|**自动拒绝**|**对于** 以下值，为"是"： <ul><li>**提示用户**</li><li>**根据计算机安全设置提示用户**</li><li>**Disabled**</li><li>**未配置**</li></ul>|
|外接程序&可扩展性|Outlook|设置Outlook模型自定义操作执行提示|**自动拒绝**|**对于** 以下值，为"是"： <ul><li>**提示用户**</li><li>**根据计算机安全设置提示用户**</li><li>**Disabled**</li><li>**未配置**</li></ul>|
|外接程序&可扩展性|PowerPoint|运行程序|**禁用 (运行任何程序)**|**"是** "表示值 **"启用 (提示用户，然后再运行)**|
|外接程序&可扩展性|Word <p> Excel|禁用智能文档的清单使用|**Enabled**|否|
|DDE|Excel|不允许动态数据Exchange (DDE) 服务器启动Excel|**Enabled**|**"是**"表示 **值"未配置"。**|
|DDE|Excel|不允许动态数据Exchange (DDE) 服务器查找Excel|**Enabled**|**对于** 以下值，为"是"： <ul><li>**Disabled**</li><li>**未配置**</li></ul>|
|DDE|Word|动态Exchange|**Disabled**|否|
|Jscript & VBScript|Outlook|允许使用一次性 Outlook 窗体中的脚本 |**Disabled**|否|
|Jscript & VBScript|Outlook|不允许对Outlook运行对象模型脚本|**Enabled**|否|
|Jscript & VBScript|Outlook|不允许为Outlook运行对象模型脚本|**Enabled**|否|
|宏|Excel|宏通知|**禁用无数字签署的所有宏**|**对于** 以下值，为"是"： <ul><li>**Disabled**</li><li>**未配置**</li></ul>|
|宏|访问 <p> PowerPoint <p> Project <p> Publisher <p> Visio <p> Word|VBA 宏通知设置|**禁用无数字签署的所有宏** <p> 和 <p> **要求由受信任的发布者签署宏**|**对于** 以下值，为"是"： <ul><li>**Disabled**</li><li>**未配置**</li></ul>|
|宏|Access <p> Excel <p> PowerPoint <p> Visio <p> Word|阻止宏在 internet Office文件内运行|**Enabled**|**对于** 以下值，为"是"： <ul><li>**Disabled**</li><li>**未配置**</li></ul>|
|宏|Excel|扫描 Open XML 工作簿Excel加密的宏|**扫描加密的宏 (默认)**|否|
|宏|Office|允许 VBA 按不受信任的 Intranet 位置的路径加载类型库引用|**Disabled**|否|
|宏|Office|自动化安全性|**使用应用程序宏安全级别**|否|
|宏|Office|对可能引用本地计算机上不安全位置的 VBA 库引用禁用其他安全检查|**Disabled**|否|
|宏|Office|宏运行时扫描范围|**启用所有文档**|否|
|宏|Office|仅信任使用 V3 签名的 VBA 宏|不是安全基线设置。|否|
|宏|Outlook|Outlook安全模式|**使用Outlook安全组策略**|启用所有 GPO Outlook必需。 <p> 作为依赖关系 (此策略不会阻止活动内容本身) 。|
|宏|Outlook|宏的安全策略设置|**已签名、禁用未签名的警告**|**对于** 以下值，为"是"： <ul><li>**始终警告**</li><li>**已签名、禁用未签名的警告**</li><li>**Disabled**</li><li>**未配置**</li></ul>|
|宏|PowerPoint|扫描 Open XML 演示文稿PowerPoint加密的宏|**扫描加密的宏 (默认)**|否|
|宏|Publisher|Publisher自动化安全级别|**按用户指令(提示)**|否|
|宏|Word|扫描 Word Open XML 文档中的加密宏|**扫描加密的宏 (默认)**|否|
|

### <a name="hkey_local_machine-settings"></a>HKEY_LOCAL_MACHINE设置

<p>

****
|类别|应用|策略名称|安全基线<br>设置 (推荐) |使用用户提示进行设置<br>和 替代可用？|
|---|---|---|---|---|
|ActiveX|Office|限制 ActiveX 安装 |excel.exe = True <p> exprwd.exe = True <p> groove.exe = True <p> msaccess.exe = True <p> mse7.exe = True <p> mspub.exe = True <p> onent.exe = True <p> outlook.exe = True <p> powerpnt.exe = True <p> pptview.exe = True <p> spDesign.exe = True <p> visio.exe = True <p> winproj.exe = True <p> winword.exe = True|否|
|外接程序&可扩展性|Office|加载项管理 |excel.exe = True <p> exprwd.exe = True <p> groove.exe = True <p> msaccess.exe = True <p> mse7.exe = True <p> mspub.exe = True <p> onent.exe = True <p> outlook.exe = True <p> powerpnt.exe = True <p> pptview.exe = True <p> spDesign.exe = True <p> visio.exe = True <p> winproj.exe = True <p> winword.exe = True|否|
|外接程序&可扩展性|Office|阻止在文档中Office Flash 激活|请参阅 Microsoft 安全指南 ADMX/ADML 文件，了解阻止在应用中对 Flash 进行所有激活的 COM Microsoft 365列表。 适用于企业安全基线的 ADMX/ADML 文件在安全与合规[Toolkit。](https://www.microsoft.com/download/details.aspx?id=55319)|否|
|Jscript & VBScript|Office|限制旧版JScript执行Office|**已启用**： <p> 访问：69632 <p> Excel： 69632 <p> OneNote： 69632 <p> Outlook： 69632 <p> PowerPoint： 69632 <p> Project： 69632 <p> Publisher：69632 <p> Visio： 69632 <p> Word：69632|否|
|Jscript & VBScript|Office|脚本化 Window 安全限制 |excel.exe = True <p> exprwd.exe = True <p> groove.exe = True <p> msaccess.exe = True <p> mse7.exe = True <p> mspub.exe = True <p> onent.exe = True <p> outlook.exe = True <p> powerpnt.exe = True <p> pptview.exe = True <p> spDesign.exe = True <p> visio.exe = True <p> winproj.exe = True <p> winword.exe = True|否|
|
