---
title: 安装和使用 Microsoft Outlook 的垃圾邮件报告外接程序
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 4650fec1-4ee3-4659-abbc-bf091718cb26
ms.collection:
- M365-security-compliance
description: 了解如何安装和使用 Microsoft 垃圾电子邮件报告加载项将垃圾邮件、非垃圾邮件和网络钓鱼邮件报告给 Microsoft。
ms.openlocfilehash: 096bd83c53149360e6cdd3ba8e73aacce5b1106f
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/22/2020
ms.locfileid: "48199681"
---
# <a name="install-and-use-the-junk-email-reporting-add-in-for-microsoft-outlook"></a>安装和使用 Microsoft Outlook 的垃圾邮件报告外接程序

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!NOTE]
> 如果您当前未使用垃圾电子邮件报告加载项，则建议您改为 [报告邮件加载项](enable-the-report-message-add-in.md) 。 有关详细信息，请参见[向 Microsoft 报告邮件和文件](report-junk-email-messages-to-microsoft.md)。

Microsoft Outlook 的垃圾电子邮件报告外接程序允许用户提交误报 (电子邮件被标记为垃圾邮件) 、漏报 (错误的电子邮件) 和网络钓鱼邮件发送给 Microsoft。 如果您的组织不使用 Exchange Online Protection (例如，本地 Exchange 或除 Exchange Online) 之外的电子邮件服务，则您的垃圾邮件报告提交不会影响垃圾邮件筛选。

本主题说明如何安装和使用垃圾邮件报告加载项。

## <a name="what-do-you-need-to-know-before-you-begin"></a>开始前，有必要了解什么？

- 若要安装垃圾电子邮件报告加载项，请参阅本主题后面的 [安装垃圾电子邮件报告外](#install-the-junk-email-reporting-add-in) 接部分。

- 垃圾电子邮件报告加载项适用于以下版本的 Outlook：

  - Outlook 2013 或更高版本
  - Outlook 包含在适用于企业的 Microsoft 365 应用程序中

- 有关向 Microsoft 报告邮件的详细信息，请参阅 [将邮件和文件报告给 microsoft](report-junk-email-messages-to-microsoft.md)。

## <a name="use-the-junk-email-reporting-add-in-to-report-spam-and-phishing-messages"></a>使用垃圾电子邮件报告加载项报告垃圾邮件和网络钓鱼邮件

1. 对于收件箱中的邮件或除垃圾邮件以外的任何其他电子邮件文件夹中的邮件，请使用以下任何一种方法来报告垃圾邮件和网络钓鱼邮件：

   - 选择邮件或打开邮件。 在功能区的 " **主页** " 或 " **邮件** " 选项卡中，单击 " **垃圾邮件**"，然后选择 " **报告为垃圾邮件** 或 **报告为网络钓鱼**"。

     ![从功能区报告垃圾邮件或仿冒电子邮件](../../media/junk-email-reporting-ribbon.png)

   - 右键单击该邮件，选择 " **垃圾**邮件"，然后选择 " **报告为垃圾** 邮件" 或 " **报告为网络钓鱼**"。

     ![通过右键单击报告垃圾邮件或仿冒电子邮件](../../media/junk-email-reporting-right-click.png)

   - 选择多个邮件，单击鼠标右键，然后选择 " **报告为垃圾** 邮件" 或 " **报告为网络钓鱼**"。

     ![通过右键单击报告多个垃圾邮件或仿冒电子邮件](../../media/junk-email-reporting-right-click-multiple.png)

2. 在出现的对话框中，阅读信息，然后单击 " **报告**"。 如果你改变主意，请单击 " **不报告**"。

   !["报告为垃圾邮件" 对话框](../../media/junk-email-reporting-report-as-junk-dialog.png)

   !["报告为仿冒" 对话框](../../media/junk-email-reporting-report-as-phishing-dialog.png)

3. 选定的邮件将被发送到 Microsoft 进行分析和：

   - 移动到 "垃圾邮件" 文件夹（如果它被报告为垃圾邮件）。
   - 如果报告为网络钓鱼，则删除。
   
   若要确认已提交的邮件，请打开您的“已发送邮件”**** 文件夹查看已提交的邮件。

## <a name="use-the-junk-email-reporting-add-in-to-report-non-spam-and-phishing-messages-from-the-junk-email-folder"></a>使用垃圾电子邮件报告加载项报告垃圾邮件文件夹中的非垃圾邮件和网络钓鱼邮件

1. 在 "垃圾邮件" 文件夹中，使用以下任何一种方法报告垃圾邮件误报或网络钓鱼邮件：

   - 选择邮件或打开邮件。 在功能区的 " **主页** " 或 " **邮件** " 选项卡中，单击 " **非垃圾邮件**"，然后选择 " **报告为非垃圾邮件** " 或 " **报告为仿冒**"

     ![从 "垃圾邮件" 文件夹的功能区报告非垃圾邮件或仿冒电子邮件](../../media/junk-email-reporting-junk-folder-ribbon.png)

   - 右键单击该邮件，单击 " **垃圾**邮件"，然后选择 " **报告为非垃圾邮件** " 或 " **报告为网络钓鱼**"。

     ![不通过在 "垃圾邮件" 文件夹中单击鼠标右键来报告垃圾邮件或仿冒电子邮件](../../media/junk-email-reporting-junk-folder-right-click.png)

   - 选择多个邮件，单击鼠标右键，然后选择 " **报告为非垃圾邮件** " 或 " **报告为网络钓鱼**"。

     ![在 "垃圾邮件" 文件夹中单击鼠标右键，不报告垃圾邮件或仿冒电子邮件](../../media/junk-email-reporting-junk-folder-right-click-multiple.png)

2. 在出现的对话框中，阅读信息，然后单击 " **报告**"。 如果你改变主意，请单击 " **不报告**"。

   !["报告为非垃圾邮件" 对话框](../../media/junk-email-reporting-report-as-not-junk-dialog.png)

   !["报告为仿冒" 对话框](../../media/junk-email-reporting-report-as-phishing-dialog.png)

3. 选定的邮件将被发送到 Microsoft 进行分析和：

   - 移动到 "垃圾邮件" 文件夹（如果它被报告为垃圾邮件）。
   - 如果报告为网络钓鱼，则删除。

   若要确认已提交的邮件，请打开您的“已发送邮件”**** 文件夹查看已提交的邮件。

## <a name="install-the-junk-email-reporting-add-in"></a>安装垃圾电子邮件报告外接

- 您需要在要安装加载项的计算机上拥有管理员权限。

- 转到 <https://www.microsoft.com/download/details.aspx?id=18275> 并将适用于你的 Office 版本的 .msi 文件下载到易于查找的位置：

  - **32 位**： `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi`
  - **64 位**： `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi`

- 对于 Outlook 2013 或更高版本，唯一的先决条件是 Microsoft .NET Framework 2.0。 在 Windows 10 中，不会从下载安装 .NET Framework 2.0。

### <a name="install-the-junk-email-reporting-add-in-using-the-setup-wizard"></a>使用安装向导安装垃圾电子邮件报告外接程序

1. 在您的计算机上关闭 Outlook。

2. 在 Windows 10 中，验证是否已启用 .NET Framework 2.0。 有关说明，请参阅 [在 "控制面板" 中启用 .Net Framework 3.5](https://docs.microsoft.com/dotnet/framework/install/dotnet-35-windows-10#enable-the-net-framework-35-in-control-panel)。

3. 找到已下载的 .msi 文件，然后双击该文件。

4. 在“欢迎使用 Microsoft 垃圾电子邮件报告外接程序安装程序”**** 页面上，单击“下一步”****。

5. 查看许可协议，如果同意条款，请单击 " **我接受许可协议中的条款** "，然后单击 " **下一步**"。

6. 向导完成后，单击“完成”****。 

启动 Outlook。

查找 Outlook 功能区上的 " **垃圾邮件** " 按钮。 现在，可以通过在收件箱中选择垃圾电子邮件并单击“报告垃圾邮件”**** 按钮，向 Microsoft 报告垃圾电子邮件。

如果想要向 Microsoft 报告仿冒垃圾电子邮件，请选择****“垃圾邮件”旁边的向下箭头查看更多选项，如****“报告为仿冒邮件”。如果一封电子邮件被错误识别为垃圾邮件，则在垃圾邮件文件夹中，您还可以选择“报告不是垃圾邮件”****。

### <a name="install-the-junk-email-reporting-add-in-using-silent-mode"></a>使用静默模式安装垃圾电子邮件报告外接程序

1. 在您的计算机上关闭 Outlook。

2. 在 Windows 10 中，通过运行以下命令来安装 .NET Framework 2.0：

   ```dos
   DISM /Online /Enable-Feature /FeatureName:NetFx3 /All
   ```

3. 若要在不进行任何用户交互的情况下安装加载项，请打开命令提示符，并使用以下语法：

   ```dos
   msiexec /qn /i "<PathToMSIFile>\<MSIFile>" [MaxMessageSelection=<1-50>] [BccEmailAddress="<EmailAddress1>; <EmailAddress2>"...]
   ```

   - `MaxMessageSelection` 指定可为单个提交选择的最大邮件数。 有效值为1到50。 默认值为 15。

   - `BccEmailAddress` 指定将接收所有用户提交副本的其他密件抄送收件人。 默认值为空， (不) 其他密件抄送收件人。

   本示例使用默认设置从指定路径安装64位版本的加载项。

   ```dos
   msiexec /qn /i "C:\Downloads\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi"
   ```

   此示例使用以下其他设置从指定路径安装32位版本的外接：

   - 单个提交中最长可选择20封邮件。
   - junkreports@contoso.com 和 hollyd@treyresearch.net 接收所有提交的密件抄送副本。

   ```dos
   msiexec /qn /i "C:\Downloads\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi" MaxMessageSelection=20 BccEmailAddress="junkreports@contoso.com; hollyd@treyresearch.net"
   ```

### <a name="how-do-you-know-this-worked"></a>如何判断是否生效？

若要验证是否已成功安装垃圾电子邮件报告外接程序，请在 Outlook 中执行以下任一步骤：

- 选择邮件或打开邮件。 在功能区的 " **主页** " 或 " **邮件** " 选项卡中，单击 " **垃圾邮件**"，并验证以下选项是否可用：

  - **报告为垃圾邮件**
  - **报告为网络钓鱼**
  - **垃圾报告选项**
  - **报告垃圾联机帮助**

  ![从功能区报告垃圾邮件或仿冒电子邮件](../../media/junk-email-reporting-ribbon.png)

- 右键单击该邮件，选择 " **垃圾**邮件"，并验证以下选项是否可用：

  - **报告为垃圾邮件**
  - **报告为网络钓鱼**
  - **垃圾报告选项**
  - **报告垃圾联机帮助**

  ![通过右键单击报告垃圾邮件或仿冒电子邮件](../../media/junk-email-reporting-right-click.png)

- 选择多个邮件，右键单击，并验证以下选项是否可用：

  - **报告为垃圾邮件**
  - **报告为网络钓鱼**

  ![通过右键单击报告多个垃圾邮件或仿冒电子邮件](../../media/junk-email-reporting-right-click-multiple.png)

- 在 " **垃圾邮件** " 文件夹中执行以前的操作，并验证以前的 **垃圾** 报告选项目前 **不是垃圾**邮件。

  ![从 "垃圾邮件" 文件夹的功能区报告非垃圾邮件或仿冒电子邮件](../../media/junk-email-reporting-junk-folder-ribbon.png)

  ![不通过在 "垃圾邮件" 文件夹中单击鼠标右键来报告垃圾邮件或仿冒电子邮件](../../media/junk-email-reporting-junk-folder-right-click.png)

  ![在 "垃圾邮件" 文件夹中单击鼠标右键，不报告垃圾邮件或仿冒电子邮件](../../media/junk-email-reporting-junk-folder-right-click-multiple.png)

## <a name="uninstall-the-junk-email-reporting-add-in"></a>卸载垃圾电子邮件报告外接程序

关闭 Outlook 后，请使用以下任一过程卸载垃圾电子邮件报告外接程序：

- **"控制面板"**：按 Windows 键 + R。在打开的 " **运行** " 对话框中，输入， `control appwiz.cpl` 然后单击 **"确定"**。

  在列表中查找并选择 **Microsoft 垃圾电子邮件报告加载项** ，然后单击 " **卸载**"。

- **Windows Installer 程序包**：查找或下载相应的 .msi 文件，然后双击该文件。

  - **32 位**： `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi`

  - **64 位**： `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi`

  在出现的对话框中，选择 " **删除适用于 Outlook 的 Microsoft 垃圾电子邮件报告外接程序** "，然后单击 " **下一步**"。

- **静默模式**：查找或下载相应的 .msi 文件。 在命令提示符窗口中，将替换 \<PathToFile\> 为 .msi 文件的位置，然后运行下列命令之一：

  - **32 位**：

    ```dos
    msiexec /x "<PathToFile>\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi" /qn MSIRESTARTMANAGERCONTROL="DisableShutdown"
    ```

  - **64 位**：

    ```dos
    msiexec /x "<PathToFile>\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi" /qn MSIRESTARTMANAGERCONTROL="DisableShutdown"
    ```

当您在卸载后打开 Outlook 时，垃圾邮件、非垃圾邮件和网络钓鱼报告选项应消失。

## <a name="troubleshooting-the-junk-email-reporting-add-in"></a>对垃圾电子邮件报告外接加载项进行故障排除

有时，在添加垃圾电子邮件报告加载项后，Outlook 可能会遇到问题。 本节介绍您可能遇到的问题，以及解决这些问题的提示。

### <a name="troubleshooting-for-users"></a>用户疑难解答

您将遇到以下一个或多个问题：

- Nothing happens when you click **Report Junk**
- 当您选择一封电子邮件之后，Outlook 停止响应
- 由于收到"未送达"回复，报告的垃圾邮件无法传递

若要解决此问题，请执行以下步骤：

1. 关闭并重新启动 Outlook。
2. 创建并发送一封测试邮件，并验证收件人是否收到该邮件。
3. 如果问题仍然存在，请与管理员联系。

有关可用于将邮件提交到 Microsoft 的其他方法，请参阅 [向 Microsoft 报告邮件和文件](report-junk-email-messages-to-microsoft.md)。

### <a name="troubleshooting-for-admins"></a>管理员的故障排除

#### <a name="problem-an-error-message-continually-appears-that-asks-users-to-contact-their-system-administrator"></a>问题：不断出现一条错误消息，询问用户是否联系其系统管理员

1. 验证或将 `LoggingLevel` 注册表项设置为值 "Verbose"：

   - **32 位 Windows 上的32位 Outlook**：

     ```text
     Windows Registry Editor Version 5.00

     [HKEY_LOCAL_MACHINE\Software\Microsoft\Junk Email Reporting\Addins]
     "LoggingLevel"="Verbose"
     ```

   - **64 位 Windows 上的32位 Outlook**：

     ```text
     Windows Registry Editor Version 5.00

     [HKEY_LOCAL_MACHINE\Software\Wow6432Node\Microsoft\Junk Email Reporting\Addins]
     "LoggingLevel"="Verbose"
     ```

   - **64 位 Outlook**：

     ```text
     Windows Registry Editor Version 5.00

     [HKEY_LOCAL_MACHINE\Software\Microsoft\Junk E-mail Reporting\Addins]
     "LoggingLevel"="Verbose"
     ```

2. 重新启动 Outlook 并要求用户在看到错误消息时报告回来。

3. 收集在以下位置找到的日志信息：

   `%LOCALAPPDATA%\Microsoft\Junk Email Reporting Add-in\SpamReporterAddinLog.txt`

4. 联系 Exchange Online Protection 技术支持并向他们提供日志信息。

#### <a name="problem-users-selected-not-to-receive-a-confirmation-prompt-when-they-report-messages-and-now-they-want-the-prompt-back"></a>问题：用户选择在报告邮件时不会收到确认提示，现在他们希望返回提示

1. 创建 `ConfirmReportJunk` 值为 "True" 的注册表项：

   ```text
   Windows Registry Editor Version 5.00

   HKEY_CURRENT_USER\Software\Microsoft\Junk E-mail Reporting\Preferences]
   "ConfirmReportJunk"="True"
   ```

2. 重新启动 Outlook。
