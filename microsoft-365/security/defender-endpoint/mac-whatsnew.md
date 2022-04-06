---
title: Mac 上Microsoft Defender for Endpoint的新增功能
description: 了解 Mac 上以前版本的 Microsoft Defender for Endpoint 的主要更改。
keywords: microsoft， defender， Microsoft Defender for Endpoint， mac， 安装， macos， whatsnew
ms.prod: m365-security
ms.mktglfcycl: security
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: reference
ms.technology: mde
ms.openlocfilehash: d36d05a4abe36ffe63e53eb8e164e248755de0ec
ms.sourcegitcommit: 85ce5fd0698b6f00ea1ea189634588d00ea13508
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/06/2022
ms.locfileid: "64665901"
---
# <a name="whats-new-in-microsoft-defender-for-endpoint-on-mac"></a>Mac 上Microsoft Defender for Endpoint的新增功能

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 希望体验 Microsoft Defender for Endpoint？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)。

## <a name="1016169-20122022161690"></a>101.61.69 (20.122022.16169.0) 

- 错误修补程序

## <a name="1016091-20122021160910"></a>101.60.91 (20.122021.16091.0) 

- 此版本包含 [CVE-2022-23278](https://msrc-blog.microsoft.com/2022/03/08/guidance-for-cve-2022-23278-spoofing-in-microsoft-defender-for-endpoint/) 的安全更新

## <a name="1015950-20122021159500"></a>101.59.50 (20.122021.15950.0) 

- 此版本添加了对 macOS 12.3 的支持。 从 macOS 12.3 开始， [Apple 将删除 Python 2.7](https://developer.apple.com/documentation/macos-release-notes/macos-12_3-release-notes)。 默认情况下，macOS 上不会预安装 Python 版本。 **需要执行的操作**： 
  - 在将设备更新到 macOS Monterey 12.3 (或更新) 之前，用户必须将 Mac Microsoft Defender for Endpoint更新为版本 101.59.50 (或更高) 。 此最小版本 101.59.50 是消除 macOS Monterey 上的 mac Microsoft Defender for Endpoint的 Python 相关问题的先决条件。
  - 对于远程部署，必须将现有 MDM 设置更新为 Microsoft Defender for Endpoint for Mac 版本 101.59.50 (或更新) 。 通过 MDM 将较旧的 Microsoft Defender for Endpoint for Mac 版本推送到 macOS Monterey 12.3 (或更高) 将导致安装失败。

## <a name="1015910-20122012159100"></a>101.59.10 (20.122012.15910.0) 

- 命令行工具现在支持将隔离的文件还原到最初检测到文件的位置之外的位置。 这可以通过 。`mdatp threat quarantine restore --id [threat-id] --path [destination-folder]`
- 用于处理通过 Thunderbolt 3 连接的设备的扩展设备控件
- 改进了包含无效供应商 ID 和产品 ID 的设备控制策略的处理。 在此版本之前，如果策略包含一个或多个无效 ID，则会忽略整个策略。 从此版本开始，仅忽略策略的无效部分。 有关策略的问题会通过 `mdatp device-control removable-media policy list`这些问题浮出水面。
- 错误修补程序

## <a name="1015662-20121122156620"></a>101.56.62 (20.121122.15662.0) 

- 错误修补程序

## <a name="1015635-20121121156350"></a>101.56.35 (20.121121.15635.0) 

- 应用程序已从"Microsoft Defender ATP"重命名为"Microsoft Defender"。 最终用户将观察以下更改：
  - 应用程序安装路径已从 `/Application/Microsoft Defender ATP.app` 更改为 `/Applications/Microsoft Defender.app`。
  - 在用户体验中，"Microsoft Defender ATP"的出现已被替换为"Microsoft Defender"
- 解决了某些 VPN 应用程序由于使用 Microsoft Defender for Endpoint for Mac 分发的网络内容筛选器而无法连接的问题
- 解决了在 macOS 12.2 beta 2 中发现的问题：由于操作系统 (操作系统) 发生更改，导致无法打开安装包，从而阻止安装具有特定特征的包。 虽然此操作系统更改似乎未包含在 macOS 12.2 的最终版本中，但很可能它将在将来的 macOS 版本中重新引入。 因此，我们鼓励所有企业管理员在其管理控制台中将Microsoft Defender for Endpoint包刷新到此产品版本 (或更新版本) 。
- 解决了某些 M1 设备上出现的问题：产品停滞在无效的反恶意软件定义中，并且无法成功更新到一组工作定义。
- `mdatp health`输出已通过调`full_disk_access_enabled`用的附加属性进行扩展，该属性可用于确定是否已向 Microsoft Defender for Endpoint for Mac 的所有组件授予完全磁盘访问权限。
- 性能改进& bug 修复

## <a name="1015416-20121111154160"></a>101.54.16 (20.121111.15416.0) 

- 不再支持 macOS 10.14 (Mojave) 
- 在管理员通过 MDM 停止管理产品设置后，它现在将还原为在最终用户本地配置的值 (管理之前的值，或者如果未显式提供此类本地值，则产品使用的默认值) 。 在此更改之前，在停止管理设置后，其托管值会保留，并且仍由产品使用。
- 性能改进& bug 修复

## <a name="1014925-20121092149250"></a>101.49.25 (20.121092.14925.0) 

- 向命令行工具添加了一个新开关，用于控制是否在按需扫描期间扫描存档。 这可以通过以下方式进行配置 `mdatp config scan-archives --value [enabled/disabled]`。 默认情况下，此设置为 `enabled`。
- 错误修补程序

## <a name="1014727-20121082147270"></a>101.47.27 (20.121082.14727.0) 

- 修复了在 macOS Mojave 和 macOS Catalina 上关闭时发生的系统冻结问题

## <a name="1014384-20121082143840"></a>101.43.84 (20.121082.14384.0) 

- macOS 12 (蒙特利) 候选版本
- 错误修补程序

## <a name="1014110-20121072141100"></a>101.41.10 (20.121072.14110.0) 

- 向命令行工具添加了新开关：
  - 控制按需扫描的并行度。 这可以通过以下方式进行配置 `mdatp config maximum-on-demand-scan-threads --value [number-between-1-and-64]`。 默认情况下，使用并行度 `2` 。
  - 控制是否在启用或禁用安全智能更新后进行扫描。 这可以通过以下方式进行配置 `mdatp config scan-after-definition-update --value [enabled/disabled]`。 默认情况下，此设置为 `enabled`。
- 更改产品日志级别现在需要提升
- 性能改进& bug 修复

## <a name="1014084-20121071140840"></a>101.40.84 (20.121071.14084.0) 

- M1 芯片本机支持
- 性能改进& bug 修复

## <a name="1013797-20121062137970"></a>101.37.97 (20.121062.13797.0) 

- 性能改进& bug 修复

## <a name="1013428-20121061134280"></a>101.34.28 (20.121061.13428.0) 

- 错误修补程序

## <a name="1013427-20121052134270"></a>101.34.27 (20.121052.13427.0) 

- 错误修补程序

## <a name="1013420-20121051134200"></a>101.34.20 (20.121051.13420.0) 

- [macOS 的设备控制](mac-device-control-overview.md) 现已正式发布
- 解决了无法从 macOS 11 上的状态菜单启动快速扫描的问题 (Big Sur) 
- 其他 bug 修复

## <a name="1013269-20121042132690"></a>101.32.69 (20.121042.13269.0) 

- 解决了从Microsoft Defender for Endpoint和其他应用程序并发访问密钥链可能导致密钥链损坏的问题。

## <a name="1012964-20121042129640"></a>101.29.64 (20.121042.12964.0) 

- 从此版本开始，会自动修正通过命令行客户端触发的按需防病毒扫描期间检测到的威胁。 通过用户界面触发的扫描期间检测到的威胁仍需要手动操作。
- `mdatp diagnostic real-time-protection-statistics` 现在支持另外两个交换机：
  - `--sort`：按扫描的文件总数对输出降序进行排序
  - `--top N`：仅 `--sort` 当还指定了 N 个结果时，才会显示前 N 个结果 () 
- 性能改进 (专用于在 bug 修复) &使用 YARN 时

## <a name="1012750-20121022127500"></a>101.27.50 (20.121022.12750.0) 

- 修复了适用于 macOS Catalina 及更早版本的 Apple 证书过期问题。 此修补程序还原威胁&漏洞管理 (TVM) 功能。

## <a name="1012569-20121022125690"></a>101.25.69 (20.121022.12569.0) 

- macOS 上的Microsoft Defender for Endpoint现已为美国政府客户提供预览版。 有关详细信息，请参阅[美国政府客户的Microsoft Defender for Endpoint](gov.md)。
- 性能改进 (专门针对使用 XCode 模拟器应用) & bug 修复的情况。

## <a name="1012364-20121021123640"></a>101.23.64 (20.121021.12364.0) 

- 向命令行工具添加了一个新选项，用于查看有关上次按需扫描的信息。 若要查看有关上次按需扫描的信息，请运行 `mdatp health --details antivirus`
- 性能改进& bug 修复

## <a name="1012279-20121012122790"></a>101.22.79 (20.121012.12279.0) 

- 性能改进& bug 修复

## <a name="1011988-20121011119880"></a>101.19.88 (20.121011.11988.0) 

- 性能改进& bug 修复

## <a name="1011948-20120121119480"></a>101.19.48 (20.120121.11948.0) 

> [!NOTE]
> 此版本已弃用旧的命令行工具语法。 有关新语法的信息，请参阅 ["资源](mac-resources.md#configuring-from-the-command-line)"。

- 添加了一个新的命令行开关以禁用网络扩展： `mdatp system-extension network-filter disable`。 此命令可用于排查可能与 Mac 上的Microsoft Defender for Endpoint相关的网络问题
- 性能改进& bug 修复

## <a name="1011921-20120101119210"></a>101.19.21 (20.120101.11921.0) 

- 错误修补程序

## <a name="1011526-20120102115260"></a>101.15.26 (20.120102.11526.0) 

- 提高了在 macOS 11 Big Sur 上运行时代理的可靠性
- 添加了一个新的命令行开关 (`--ignore-exclusions`) 以忽略自定义扫描期间的 AV 排除项 () `mdatp scan custom`
- 性能改进& bug 修复

## <a name="1011375-20120101113750"></a>101.13.75 (20.120101.11375.0) 

- 删除了Microsoft Defender for Endpoint触发 macOS 11 (Big Sur) 出现内核恐慌的 bug 的情况
- 修复了在 mac 11 上运行时 Endpoint Security 系统扩展的内存泄漏 (Big Sur) 
- 错误修补程序

## <a name="1011072"></a>101.10.72

- 错误修补程序

## <a name="1010961"></a>101.09.61

- 添加了新的托管首选项 [，用于禁用发送反馈的选项](mac-preferences.md#show--hide-option-to-send-feedback)
- 状态菜单图标现在在管理产品设置时显示正常状态。 以前，状态菜单图标显示警告或错误状态，即使产品设置由管理员管理
- 性能改进& bug 修复

## <a name="1010950"></a>101.09.50

- 此产品版本已在 macOS Big Sur 11 beta 9 上验证

- 命令行工具的新语 `mdatp` 法现在是默认语法。 有关新语法的详细信息，请参阅 [macOS 上用于Microsoft Defender for Endpoint的资源](mac-resources.md#configuring-from-the-command-line)

  > [!NOTE]
  > 旧命令行工具语法将于 **2021 年 1 月 1 日从** 产品中删除。

- 使用允许将诊断日志保存到其他目录的新参数 (`--path [directory]`) 进行扩展`mdatp diagnostic create`
- 性能改进& bug 修复

## <a name="1010949"></a>101.09.49

- 用户界面改进，用于区分 IT 管理员管理的排除项与本地用户定义的排除项
- 改进了按需扫描期间的 CPU 利用率
- 性能改进& bug 修复

## <a name="1010723"></a>101.07.23

- 为检查被动模式状态和EDR组 ID 的`mdatp --health`输出添加了新字段

  > [!NOTE]
  > `mdatp --health` 将在将来的产品更新中替换 `mdatp health` 为。

- 修复了未在用户界面中将自动示例提交标记为托管的 bug
- 添加了用于控制防病毒扫描历史记录中项保留的新设置。 现在可以 [指定在扫描历史记录中保留项的天数](mac-preferences.md#antivirus-scan-history-retention-in-days) ，并 [指定扫描历史记录中的最大项数](mac-preferences.md#maximum-number-of-items-in-the-antivirus-scan-history)
- 错误修补程序

## <a name="1010663"></a>101.06.63

- 解决了版本 `101.05.17`中引入的性能回归问题。 回归是随修复措施一起引入的，旨在消除一些客户在访问 SMB 共享时观察到的内核恐慌。 我们已还原此代码更改，并正在研究消除内核恐慌的替代方法。

## <a name="1010517"></a>101.05.17

> [!IMPORTANT]
> 我们正在为 `mdatp` 命令行工具开发新的增强型语法。 新语法目前是预览体验成员快速更新和预览体验计划慢更新频道中的默认语法。 我们鼓励你使用这种新语法来自我解答。
>
> 我们将继续支持旧语法与新语法并行使用，并将在未来几个月内就旧语法的弃用计划提供更多沟通。

- 解决了访问 SMB 文件共享时有时发生的内核恐慌问题
- 性能改进& bug 修复

## <a name="1010516"></a>101.05.16

- 对快速扫描逻辑的改进可显著减少扫描的文件数
- 添加了对命令行工具的[自动完成支持](mac-resources.md#how-to-enable-autocompletion)
- 错误修补程序

## <a name="1010312"></a>101.03.12

- 性能改进& bug 修复

## <a name="1010154"></a>101.01.54

- 有关与时间计算机兼容性的改进
- 辅助功能改进
- 性能改进& bug 修复

## <a name="1010031"></a>101.00.31

- 改进[了Intune用户的产品载入体验](/mem/intune/apps/apps-advanced-threat-protection-macos)
- 防病毒 [排除项现在支持通配符](mac-exclusions.md#supported-exclusion-types)
- 添加了从 macOS 上下文菜单触发防病毒扫描的功能。 现在，可以在 Finder 中右键单击文件或文件夹，然后选择 **"扫描Microsoft Defender for Endpoint**
- 安装程序现在明确禁止就地产品降级。 如果需要降级，请先卸载现有版本并重新配置设备
- 其他性能改进& bug 修复

## <a name="1009027"></a>100.90.27

- 现在可以在 macOS 上[为Microsoft Defender for Endpoint设置](mac-updates.md#set-the-channel-name)与系统范围的更新通道不同的更新通道
- 新产品图标
- 其他用户体验改进
- 错误修补程序

## <a name="1008692"></a>100.86.92

- 有关与时间计算机兼容性的改进
- 解决了卸载期间产品有时未清理所有文件 `/Library/Application Support/Microsoft/Defender` 的问题
- 通过 Microsoft AutoUpdate 更新 Microsoft 产品时降低产品的 CPU 使用率
- 其他性能改进& bug 修复

## <a name="1008691"></a>100.86.91

> [!CAUTION]
> 为了确保对 macOS 设备提供最完整的保护，并使 Apple 停止向早于 [当前 - 2] 的 OS 版本交付 macOS 本机安全更新，macOS Sierra [10.12] 将不再支持 MDATP for Mac 部署和更新。 MDATP for Mac 更新和增强功能将交付给运行 Catalina [10.15]、Mojave [10.14] 和 High Sierra [10.13] 版本的设备。
>
> 如果已将 MDATP for Mac 部署到 Sierra [10.12] 设备，请升级到最新的 macOS 版本，以消除失去保护的风险。

- 性能改进& bug 修复

## <a name="1008373"></a>100.83.73

- 为 IT 管理员添加了有关[排除项管理](mac-preferences.md#exclusion-merge-policy)、[威胁类型设置管理和](mac-preferences.md#threat-type-settings-merge-policy)[不允许的威胁操作](mac-preferences.md#disallowed-threat-actions)的更多控件
- 当设备上未启用"完全磁盘访问"时，状态菜单中现在会显示警告
- 性能改进& bug 修复

## <a name="1008260"></a>100.82.60

- 解决了产品在定义更新后无法启动的问题。

## <a name="1008042"></a>100.80.42

- 错误修补程序

## <a name="1007942"></a>100.79.42

- 修复了 Mac 上Microsoft Defender for Endpoint有时干扰时间计算机的问题
- 向命令行实用工具添加了一个新开关，用于测试后端服务的连接

  ```bash
  mdatp connectivity test
  ```

- 添加了在用户界面中查看完整威胁历史记录的功能， (可从 **保护历史记录** 视图访问) 
- 性能改进& bug 修复

## <a name="1007215"></a>100.72.15

- 错误修补程序

## <a name="1007099"></a>100.70.99

- 解决了在启用实时保护时影响某些用户升级到 macOS Catalina 的能力的问题。 此零星问题是由Microsoft Defender for Endpoint锁定 Catalina 升级包中的文件，同时对其进行威胁扫描，导致升级序列中出现故障。

## <a name="1006899"></a>100.68.99

- 添加了将防病毒功能配置为在[被动模式](mac-preferences.md#enforcement-level-for-antivirus-engine)下运行的功能
- 性能改进& bug 修复

## <a name="1006528"></a>100.65.28

- 添加了对 macOS Catalina 的支持

  > [!CAUTION]
  > macOS 10.15 (Catalina) 包含新的安全和隐私增强功能。 从此版本开始，默认情况下，应用程序无法访问磁盘 (的某些位置，例如文档、下载、桌面等，) 未经明确同意。 如果没有此许可，Microsoft Defender for Endpoint无法完全保护设备。
  >
  > 授予此许可的机制取决于部署Microsoft Defender for Endpoint的方式：
  >
  > - 有关手动部署，请参阅 [手动部署](mac-install-manually.md#how-to-allow-full-disk-access) 主题中的更新说明。
  > - 有关托管部署，请参阅[基于 JAMF 的部署](mac-install-with-jamf.md)和[基于Microsoft Intune的部署](mac-install-with-intune.md#create-system-configuration-profiles)主题中的更新说明。

- 性能改进& bug 修复
