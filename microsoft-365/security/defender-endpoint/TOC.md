# [Microsoft Defender for Endpoint](index.yml)

## [概述]()
### [什么是 Microsoft Defender for Endpoint?](microsoft-defender-endpoint.md)
### [Compare Defender for Endpoint Plan 1 到计划 2](defender-endpoint-plan-1-2.md)
### [最低要求](minimum-requirements.md)
### [Microsoft Defender for Endpoint 中的新增功能](whats-new-in-microsoft-defender-endpoint.md)
### [预览功能](preview.md)
### [数据存储和隐私](data-storage-privacy.md)
### [Microsoft Defender 安全中心概述](use.md)
### [Defender for Endpoint 计划 1]()
#### [概述](defender-endpoint-plan-1.md)
#### [安装和配置](mde-p1-setup-configuration.md)
#### [入门](mde-plan1-getting-started.md)
#### [维护和操作](mde-p1-maintenance-operations.md)
### [面向美国政府客户的Microsoft Defender for Endpoint](gov.md)
### [非 Windows 平台上的 Microsoft Defender for Endpoint](non-windows.md)


## [评估功能](evaluation-lab.md)

## [计划部署](deployment-strategy.md)

## [部署指南]()
### [部署阶段](deployment-phases.md)
### [阶段 1：准备](prepare-deployment.md)
### [阶段 2：设置](production-deployment.md)
### [阶段 3：开始使用]()
#### [载入概述](onboarding.md)
#### [部署环](deployment-rings.md)
#### [使用 Microsoft Endpoint Configuration Manager 载入](onboarding-endpoint-configuration-manager.md)
#### [使用 Microsoft Endpoint Manager 载入](onboarding-endpoint-manager.md)

## [迁移指南](migration-guides.md)
### [迁移到 Defender for Endpoint](switch-to-mde-overview.md)
#### [阶段 1：准备](switch-to-mde-phase-1.md)
#### [阶段 2：设置](switch-to-mde-phase-2.md)
#### [阶段 3：开始使用](switch-to-mde-phase-3.md)
#### [疑难解答](switch-to-mde-troubleshooting.md)
### [完成迁移后管理 Defender for Endpoint](manage-mde-post-migration.md)
#### [使用 Intune（推荐）](manage-mde-post-migration-intune.md)
#### [使用配置服务器](manage-mde-post-migration-configuration-manager.md)
#### [使用组策略](manage-mde-post-migration-group-policy-objects.md)
#### [使用 PowerShell、WMI 或 MPCmdRun.exe](manage-mde-post-migration-other-tools.md)
#### [服务器迁移方案](server-migration.md)

## [配置和载入设备]()
### [载入设备并配置 Microsoft Defender for Endpoint 功能](onboard-configure.md)


### [Windows 和 Windows Server 上的 Microsoft Defender for Endpoint]()
#### [Windows 终结点的载入工具和方法](configure-endpoints.md)
#### [载入 Windows 设备和 Windows 服务器]()

##### [载入以前版本的 Windows](onboard-downlevel.md)


##### [载入 Windows 设备和 Windows 服务器]()
###### [载入 Windows Server 2012 R2、2016、半年频道、2019 和 2022](configure-server-endpoints.md)
###### [使用本地脚本载入 Windows 设备](configure-endpoints-script.md)
###### [使用组策略载入 Windows 设备](configure-endpoints-gp.md)
###### [使用 Microsoft Endpoint Configuration Manager 载入 Windows 设备](configure-endpoints-sccm.md)
###### [使用移动设备管理工具载入 Windows 设备](configure-endpoints-mdm.md)
###### [载入非永久虚拟桌面基础结构 （VDI） 设备](configure-endpoints-vdi.md)
###### [在 Windows 虚拟桌面中载入 Windows 10 多会话设备](onboard-windows-multi-session-device.md)




#### [与 Microsoft Defender for Cloud 集成](azure-server-integration.md)

#### [无需访问 Internet 载入设备](onboard-offline-machines.md)
#### [在新载入的设备上运行检测测试](run-detection-test.md)
#### [在设备上运行模拟攻击](attack-simulations.md)
#### [配置代理和 Internet 连接设置](configure-proxy-internet.md)
#### [创建载入或载出通知规则](onboarding-notification.md)



### [其他操作系统上的 Microsoft Defender for Endpoint]()
#### [载入非 Windows 设备](configure-endpoints-non-windows.md)

#### [macOS 上的 Microsoft Defender for Endpoint]()
##### [macOS 上的 Microsoft Defender for Endpoint 概述](microsoft-defender-endpoint-mac.md)
##### [新增功能](mac-whatsnew.md)

##### [部署]()
###### [基于 Microsoft Intune 的部署](mac-install-with-intune.md)
###### [基于 JAMF 专业版的部署]()
####### [使用 Jamf Pro 在 macOS 上部署 Microsoft Defender for Endpoint](mac-install-with-jamf.md)
####### [登录 Jamf Pro](mac-install-jamfpro-login.md)
####### [设置设备组](mac-jamfpro-device-groups.md)
####### [设置策略](mac-jamfpro-policies.md)
####### [注册设备](mac-jamfpro-enroll-devices.md)

###### [ 使用不同的移动设备管理(MDM)系统进行部署](mac-install-with-other-mdm.md)
###### [手动部署](mac-install-manually.md)
##### [更新](mac-updates.md)

##### [配置]()
###### [配置和验证排除](mac-exclusions.md)
###### [设置首选项](mac-preferences.md)
###### [检测并阻止可能不需要的应用程序](mac-pua.md)
###### [设备控制]()
####### [设备控制概述](mac-device-control-overview.md)
####### [JAMF 示例](mac-device-control-jamf.md)
####### [Intune 示例](mac-device-control-intune.md)
###### [定期扫描](mac-schedule-scan.md)

##### [疑难解答]()
###### [解决安装问题](mac-support-install.md)
###### [解决性能问题](mac-support-perf.md)
###### [解决云连接问题](troubleshoot-cloud-connect-mdemac.md)
###### [解决核心扩展问题](mac-support-kext.md)
###### [解决许可证问题](mac-support-license.md)

##### [隐私](mac-privacy.md)
##### [资源](mac-resources.md)


#### [Microsoft Defender for Endpoint on Linux]()
##### [Microsoft Defender for Endpoint for Linux 概述](microsoft-defender-endpoint-linux.md)
##### [新增功能](linux-whatsnew.md)
##### [部署]()
###### [手动部署](linux-install-manually.md)
###### [基于模型的部署](linux-install-with-puppet.md)
###### [基于 Ansible 的部署](linux-install-with-ansible.md)
###### [通过 Chef 在 Linux 上部署 Defender for Endpoint](linux-deploy-defender-for-endpoint-with-chef.md)

##### [更新](linux-updates.md)

##### [配置]()
###### [配置和验证排除](linux-exclusions.md)
###### [静态代理配置](linux-static-proxy-configuration.md)
###### [设置首选项](linux-preferences.md)
###### [检测并阻止可能不需要的应用程序](linux-pua.md)
###### [使用 Microsoft Defender for Endpoint on Linux 定期扫描](linux-schedule-scan-mde.md)
###### [计划更新 Microsoft Defender for Endpoint （Linux）](linux-update-MDE-Linux.md)


##### [疑难解答]()
###### [解决安装问题](linux-support-install.md)
###### [调查代理运行状况问题](health-status.md)
###### [解决云连接问题](linux-support-connectivity.md)
###### [排查 RHEL 6 安装问题](linux-support-rhel.md)
###### [解决性能问题](linux-support-perf.md)
###### [解决事件遗漏问题](linux-support-events.md)

##### [隐私](linux-privacy.md)
##### [资源](linux-resources.md)

#### [移动威胁防御]()
##### [移动威胁防御概述](mtd.md)

##### [Android 上的 Microsoft Defender for Endpoint]()
###### [Android 上的 Microsoft Defender for Endpoint 概述](microsoft-defender-endpoint-android.md)
###### [新增功能](android-whatsnew.md)

###### [部署]()
####### [使用 Microsoft Intune 在 Android 上部署 Microsoft Defender for Endpoint](android-intune.md)

###### [配置]()
####### [在 Android 功能上配置 Microsoft Defender for Endpoint](android-configure.md)
####### [使用应用保护策略配置 Microsoft Defender for Endpoint 风险信号](android-configure-mam.md)

###### [隐私]()
####### [Android 上的 Microsoft Defender for Endpoint - 隐私信息](android-privacy.md)

###### [疑难解答]()
####### [解决问题](android-support-signin.md)

##### [iOS 上的 Microsoft Defender for Endpoint]()
###### [iOS 上的 Microsoft Defender for Endpoint 概述](microsoft-defender-endpoint-ios.md)
###### [新增功能](ios-whatsnew.md)

###### [部署]()
####### [通过 Intune 在 iOS 上部署 Microsoft Defender for Endpoint](ios-install.md)
####### [在 iOS 上为未注册的设备部署 Microsoft Defender for Endpoint](ios-install-unmanaged.md)

###### [配置 iOS 功能](ios-configure-features.md)

###### [常见问题和疑难解答](ios-troubleshoot.md)

###### [隐私](ios-privacy.md)


### [使用 Microsoft Endpoint Manager 管理设备上的 Microsoft Defender for Endpoint 配置设置](security-config-management.md)

### [解决载入问题]()
#### [解决载入期间的问题](troubleshoot-onboarding.md)
#### [解决订阅和门户访问问题](troubleshoot-onboarding-error-messages.md)
#### [排查安全配置管理载入问题](troubleshoot-security-config-mgt.md)





### [配置门户设置]()
#### [配置常规 Defender for Endpoint 设置](preferences-setup.md)
#### [常规]()
##### [验证数据存储位置并更新数据保留设置](data-retention-settings.md)
##### [配置警报通知](configure-email-notifications.md)
##### [配置漏洞电子邮件通知](configure-vulnerability-email-notifications.md)
##### [配置高级功能](advanced-features.md)

#### [权限]()
##### [使用基本权限访问门户](basic-permissions.md)
##### [使用 RBAC 管理门户访问](rbac.md)
###### [创建和管理角色](user-roles.md)
###### [创建和管理设备组](machine-groups.md)
###### [创建和管理设备标签](machine-tags.md)

#### [规则]()
##### [管理点规则](manage-suppression-rules.md)
##### [创建指示器](manage-indicators.md)
###### [创建文件指示器](indicator-file.md)
###### [创建 IP 和 URL/域指示器](indicator-ip-domain.md)
###### [创建证书指示器](indicator-certificates.md)
###### [管理指示器](indicator-manage.md)
##### [管理自动化文件上载](manage-automation-file-uploads.md)
##### [管理自动化文件夹排除](manage-automation-folder-exclusions.md)

#### [设备管理]()
##### [载入设备](onboard-configure.md)
##### [载出设备](offboard-machines.md)
##### [确保设备配置正确](configure-machines.md)
##### [监视和增强设备载入](configure-machines-onboarding.md)

#### [配置 Microsoft Defender 安全中心时区设置](time-settings.md)

## [检测威胁并保护终结点]()
### [威胁和漏洞管理]()
#### [概述](next-gen-threat-and-vuln-mgt.md)
#### [入门]()
##### [权限和先决条件](tvm-prerequisites.md)
##### [支持的操作系统平台和功能](tvm-supported-os.md)
##### [分配设备值](tvm-assign-device-value.md)
#### [评估安全状况]()
##### [仪表板见解](tvm-dashboard-insights.md)
##### [风险评分](tvm-exposure-score.md)
##### [设备的 Microsoft 安全功能分数](tvm-microsoft-secure-score-devices.md)
#### [提升安全性并降低风险]()
##### [处理安全建议](tvm-security-recommendation.md)
##### [修正漏洞](tvm-remediation.md)
##### [安全建议异常](tvm-exception.md)
##### [结束支持的软件规划](tvm-end-of-support-software.md)
##### [降低零时差漏洞](tvm-zero-day-vulnerabilities.md)
#### [了解设备上的漏洞]()
##### [软件库存](tvm-software-inventory.md)
##### [我组织中的漏洞](tvm-weaknesses.md)
##### [活动日程表](threat-and-vuln-mgt-event-timeline.md)
##### [易受攻击设备报告](tvm-vulnerable-devices-report.md)
##### [搜索暴露的设备](tvm-hunt-exposed-devices.md)

### [设备发现]()
#### [设备发现概述](device-discovery.md)
#### [配置设备发现](configure-device-discovery.md)
#### [Microsoft Defender for IoT 集成](enable-microsoft-defender-for-iot-integration.md)
#### [启用 Corelight 数据集成](corelight-integration.md)
#### [设备发现常见问题](device-discovery-faq.md)

### [设备清单]()
#### [设备清单](machines-view-overview.md)
#### [排除设备](exclude-devices.md)
#### [设备日程表事件标记](device-timeline-event-flag.md)
#### [管理设备组和标签](machine-tags.md)

### [网络设备](network-devices.md)

### [在 Microsoft Defender for Endpoint 中托管防火墙报告](host-firewall-reporting.md)

### [减少攻击面]()
#### [攻击面减少概述](overview-attack-surface-reduction.md)
#### [攻击面减少（ASR）规则]()
##### [了解 ASR 规则](attack-surface-reduction.md)
##### [攻击面减少 (ASR) 规则部署指南]()
###### [攻击面减少 (ASR) 规则部署概述](attack-surface-reduction-rules-deployment.md)
###### [计划攻击面减少 (ASR) 规则部署](attack-surface-reduction-rules-deployment-plan.md)
###### [测试攻击面减少 (ASR) 规则](attack-surface-reduction-rules-deployment-test.md)
###### [启用攻击面减少 (ASR) 规则](attack-surface-reduction-rules-deployment-implement.md)
###### [操作攻击面减少 (ASR) 规则](attack-surface-reduction-rules-deployment-operationalize.md)
##### [攻击面减少 (ASR) 规则参考](attack-surface-reduction-rules-reference.md)
##### [启用 ASR 规则备用配置方法](enable-attack-surface-reduction.md)
##### [关于攻击面减少的常见问题解答](attack-surface-reduction-faq.yml)
#### [受控文件夹访问]()
##### [保护文件夹](controlled-folders.md)
##### [受控文件夹访问评估](evaluate-controlled-folder-access.md)
##### [启用受控文件夹访问](enable-controlled-folders.md)
##### [自定义受控文件夹访问](customize-controlled-folders.md)
#### [漏洞保护]()
##### [保护设备免遭攻击](exploit-protection.md)
##### [漏洞保护评估](evaluate-exploit-protection.md)
##### [启用漏洞保护](enable-exploit-protection.md)
##### [自定义漏洞保护](customize-exploit-protection.md)
##### [导入、导出和部署 Exploit Protection 配置](import-export-exploit-protection-emet-xml.md)
##### [漏洞保护参考](exploit-protection-reference.md)
#### [网络保护功能]()
##### [保护你的网络](network-protection.md)
##### [网络保护功能评估](evaluate-network-protection.md)
##### [启用网络保护功能](enable-network-protection.md)

### 下一代保护
#### [下一代保护概述](next-generation-protection.md)
##### [Microsoft Defender 防病毒软件概述](microsoft-defender-antivirus-windows.md)
##### [更好地结合：Microsoft Defender 防病毒软件和 Microsoft Defender for Endpoint](why-use-microsoft-defender-antivirus.md)
##### [一起更得心防万一：Microsoft Defender 防病毒软件和 Office 365](office-365-microsoft-defender-antivirus.md)
#### [评估 Microsoft Defender 防病毒软件](evaluate-microsoft-defender-antivirus.md)
#### [配置 Microsoft Defender 防病毒软件功能](configure-microsoft-defender-antivirus-features.md)
#### [云保护和 Microsoft Defender 防病毒软件](cloud-protection-microsoft-defender-antivirus.md)
##### [为什么要启用云保护](why-cloud-protection-should-be-on-mdav.md)
##### [启用云保护](enable-cloud-protection-microsoft-defender-antivirus.md)
##### [指定云保护级别](specify-cloud-protection-level-microsoft-defender-antivirus.md)
##### [云保护和示例提交](cloud-protection-microsoft-antivirus-sample-submission.md)
#### [配置和验证 Microsoft Defender 防病毒软件网络连接](configure-network-connections-microsoft-defender-antivirus.md)
#### [使用篡改保护保护安全设置](prevent-changes-to-security-settings-with-tamper-protection.md)
#### [在首次看到时打开阻止](configure-block-at-first-sight-microsoft-defender-antivirus.md)
#### [配置云块超时时间段](configure-cloud-block-timeout-period-microsoft-defender-antivirus.md)
#### [配置方案、高要求和实时保护](configure-protection-features-microsoft-defender-antivirus.md)
#### [检测并阻止可能不需要的应用程序](detect-block-potentially-unwanted-apps-microsoft-defender-antivirus.md)
#### [在组策略中启用和配置 Microsoft Defender 防病毒软件始终启用保护](configure-real-time-protection-microsoft-defender-antivirus.md)
#### [为 Microsoft Defender 防病毒检测配置修正](configure-remediation-microsoft-defender-antivirus.md)
#### [配置 Microsoft Defender 防病毒扫描](schedule-antivirus-scans.md)
##### [使用组策略计划扫描](schedule-antivirus-scans-group-policy.md)
##### [使用 PowerShell 计划扫描](schedule-antivirus-scans-powershell.md)
##### [使用 WMI 计划扫描](schedule-antivirus-scans-wmi.md)
#### [在 Microsoft Defender 防病毒程序内使用有限的定期扫描](limited-periodic-scanning-microsoft-defender-antivirus.md)
#### [与其他安全产品的兼容性](microsoft-defender-antivirus-compatibility.md)
#### [查找 Microsoft Defender for Endpoint 的恶意软件检测名称](find-defender-malware-name.md)

#### [获取防病毒和反恶意软件更新](manage-updates-baselines-microsoft-defender-antivirus.md)
##### [管理 Microsoft Defender 防病毒软件保护更新源](manage-protection-updates-microsoft-defender-antivirus.md)
##### [管理应下载和应用保护更新的时间日程安排](manage-protection-update-schedule-microsoft-defender-antivirus.md)
##### [管理 Microsoft Defender 更新的逐步推出过程](manage-gradual-rollout.md)
##### [为 Microsoft Defender 更新配置逐步推出过程](configure-updates.md)
##### [管理 Microsoft Defender 防病毒更新并扫描过期的终结点](manage-outdated-endpoints-microsoft-defender-antivirus.md)
##### [管理基于事件的强制更新](manage-event-based-updates-microsoft-defender-antivirus.md)
##### [管理移动设备和虚拟机 （VM） 的更新](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)

#### [为组织管理 Microsoft Defender 防病毒软件](configuration-management-reference-microsoft-defender-antivirus.md)
##### [使用 Microsoft Endpoint Manager 管理 Microsoft Defender 防病毒软件](use-intune-config-manager-microsoft-defender-antivirus.md)
##### [使用组策略设置管理 Microsoft Defender 防病毒软件](use-group-policy-microsoft-defender-antivirus.md)
##### [使用 PowerShell cmdlet 管理 Microsoft Defender 防病毒软件](use-powershell-cmdlets-microsoft-defender-antivirus.md)
##### [使用 Windows Management所 （WMI） 管理 Microsoft Defender 防病毒软件](use-wmi-microsoft-defender-antivirus.md)
##### [使用 mpcmdrun.exe 工具管理 Microsoft Defender 防病毒软件](command-line-arguments-microsoft-defender-antivirus.md)
##### [配置终结点上显示的通知](configure-notifications-microsoft-defender-antivirus.md)
##### [指定用户是否可以本地修改 Microsoft Defender 防病毒软件策略设置](configure-local-policy-overrides-microsoft-defender-antivirus.md)
##### [指定用户能否查看或与 Microsoft Defender 防病毒软件用户界面进行交互](prevent-end-user-interaction-microsoft-defender-antivirus.md)

#### [部署并报告 Microsoft Defender 防病毒软件](deploy-manage-report-microsoft-defender-antivirus.md)
##### [部署和启用 Microsoft Defender 防病毒软件](deploy-microsoft-defender-antivirus.md)
##### [虚拟桌面基础结构 （VDI） 环境中 Microsoft Defender 防病毒软件的部署指南](deployment-vdi-microsoft-defender-antivirus.md)
##### [关于 Microsoft Defender 防病毒软件的报告](report-monitor-microsoft-defender-antivirus.md)

#### [扫描和修正](review-scan-results-microsoft-defender-antivirus.md)
##### [配置并运行按需 Microsoft Defender 防病毒软件扫描](run-scan-microsoft-defender-antivirus.md)
##### [运行并查看 Microsoft Defender 脱机扫描的结果](microsoft-defender-offline.md)
##### [配置 Microsoft Defender 防病毒软件扫描选项](configure-advanced-scan-types-microsoft-defender-antivirus.md)
##### [在 Microsoft Defender 防病毒软件中还原隔离的文件](restore-quarantined-files-microsoft-defender-antivirus.md)

#### [Microsoft Defender 防病毒软件排除](configure-exclusions-microsoft-defender-antivirus.md)
##### [基于文件扩展名和文件夹位置的排除](configure-extension-file-exclusions-microsoft-defender-antivirus.md)
##### [由进程打开的文件的排除](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md)
##### [Windows Server 的排除](configure-server-exclusions-microsoft-defender-antivirus.md)
##### [要避免的常见错误](common-exclusion-mistakes-microsoft-defender-antivirus.md)

#### Microsoft Defender 防病毒的诊断和性能
##### [设备运行状况和合规性报告](machine-reports.md)
##### [排查与实时保护相关的性能问题](troubleshoot-performance-issues.md) 
##### [解决更新合规性中的 Microsoft Defender 防病毒软件报告问题](troubleshoot-reporting.md)
##### [tune 性能Microsoft Defender 防病毒](tune-performance-defender-antivirus.md)

#### Microsoft Defender 防病毒软件疑难解答
##### [查看事件日志和错误代码，解决 Microsoft Defender 防病毒软件问题](troubleshoot-microsoft-defender-antivirus.md)
##### [从第三方解决方案迁移时解决 Microsoft Defender 防病毒软件问题](troubleshoot-microsoft-defender-antivirus-when-migrating.md)

#### [Web 保护功能]()
##### [Web 保护功能概述](web-protection-overview.md)
##### [Web 威胁防护功能]()
###### [Web 威胁防护功能概述](web-threat-protection.md)
###### [监视 web 安全性](web-protection-monitoring.md)
###### [响应 web 威胁](web-protection-response.md)
##### [Web 内容筛选](web-content-filtering.md)

#### [设备控制]()
##### [可移动存储保护](device-control-removable-storage-protection.md)
##### [可移动存储访问控制](device-control-removable-storage-access-control.md)
##### [设备安装](mde-device-control-device-installation.md)
##### [设备控制打印机保护](printer-protection.md)
##### [设备控制报告](device-control-report.md)

#### [行为阻止和控制]()
##### [行为阻止和控制](behavioral-blocking-containment.md)
##### [客户端阻止](client-behavioral-blocking.md)
##### [反馈循环阻止](feedback-loop-blocking.md)


### [解决 Microsoft Defender for Endpoint 中的误报/漏报](defender-endpoint-false-positives-negatives.md)


### [管理设备配置]()

#### [提高安全基线合规性](configure-machines-security-baseline.md)
#### [优化攻击图面减少规则部署和检测](configure-machines-asr.md)

## [调查并响应威胁]()
### [终结点检测和响应]()
#### [终结点检测和响应概述](overview-endpoint-detection-response.md)
#### [安全操作仪表板](security-operations-dashboard.md)
#### [提交文件](admin-submissions-mde.md)
#### [事件队列]()
##### [查看和组织事件队列](view-incidents-queue.md)
##### [管理事件](manage-incidents.md)
##### [调查事件](investigate-incidents.md)

#### [警报队列]()
##### [Microsoft 365 Defender 中的警报队列](alerts-queue-endpoint-detection-response.md)
##### [查看和组织警报队列](alerts-queue.md)
##### [查看警报](review-alerts.md)
##### [管理警报](manage-alerts.md)
##### [调查警报](investigate-alerts.md)
##### [调查文件](investigate-files.md)
##### [调查设备](investigate-machines.md)
##### [调查 IP 地址](investigate-ip.md)
##### [调查域](investigate-domain.md)
###### [调查正向代理背后发生的连接事件](investigate-behind-proxy.md)
##### [调查用户帐户](investigate-user.md)

#### [执行响应操作]()
##### [在设备上执行响应操作]()
###### [设备上的响应操作](respond-machine-alerts.md)
###### [管理标签](respond-machine-alerts.md#manage-tags)
###### [启动自动调查](respond-machine-alerts.md#initiate-automated-investigation)
###### [启动实时响应会话](respond-machine-alerts.md#initiate-live-response-session)
###### [收集调查程序包](respond-machine-alerts.md#collect-investigation-package-from-devices)
###### [运行防病毒扫描](respond-machine-alerts.md#run-microsoft-defender-antivirus-scan-on-devices)
###### [限制应用执行](respond-machine-alerts.md#restrict-app-execution)
###### [将设备从网络隔中离出来](respond-machine-alerts.md#isolate-devices-from-the-network)
###### [咨询威胁专家](respond-machine-alerts.md#consult-a-threat-expert)
###### [在操作中心检查活动详细信息](respond-machine-alerts.md#check-activity-details-in-action-center)

##### [对文件执行响应操作]()
###### [对文件的响应操作](respond-file-alerts.md)
###### [停止并隔离网络中的文件](respond-file-alerts.md#stop-and-quarantine-files-in-your-network)
###### [从隔离区还原文件](respond-file-alerts.md#restore-file-from-quarantine)
###### [添加指示器以阻止或允许文件](respond-file-alerts.md#add-indicator-to-block-or-allow-a-file)
###### [咨询威胁专家](respond-file-alerts.md#consult-a-threat-expert)
###### [在操作中心检查活动详细信息](respond-file-alerts.md#check-activity-details-in-action-center)
###### [下载或收集文件](respond-file-alerts.md#download-or-collect-file)
###### [深度分析](respond-file-alerts.md#deep-analysis)

#### [查看和批准修正操作](manage-auto-investigation.md)
##### [查看自动化调查的详细信息和结果](auto-investigation-action-center.md)

#### [调查使用实时响应的实体]()
##### [调查设备上的实体](live-response.md)
##### [实时响应命令示例](live-response-command-examples.md)

#### [使用敏感度标签确定事件响应的优先级](information-protection-investigation.md)

#### [报告]()
##### [Power BI - 如何使用 API - 示例](api-power-bi.md)
##### [威胁防护报告](threat-protection-reports.md)

### [高级搜寻]()
#### [高级搜寻概述](advanced-hunting-overview.md)
#### [了解架构](advanced-hunting-schema-reference.md)
#### [DeviceAlertEvents](advanced-hunting-devicealertevents-table.md)

### [威胁分析概述](threat-analytics.md)
#### [阅读分析报告](threat-analytics-analyst-reports.md)

### [块模式下的 EDR](edr-in-block-mode.md)

### [自动调查和响应 （AIR）]()
#### [AIR 概述](automated-investigations.md)
#### [AIR 中的自动化级别](automation-levels.md)
#### [配置 AIR 功能](configure-automated-investigations-remediation.md)

### [Microsoft 威胁专家]()
#### [Microsoft 威胁专家概述](microsoft-threat-experts.md)
#### [配置和管理 Microsoft 威胁专家功能](configure-microsoft-threat-experts.md)



## 参考
### [了解威胁智能概念](threat-indicator-concepts.md)
### [配置与其他 Microsoft 解决方案的集成]()
#### [配置条件访问](configure-conditional-access.md)
#### [配置 Microsoft Defender for Cloud Apps 集成](microsoft-cloud-app-security-config.md)
### [管理和 API]()
#### [管理和 API 概述](management-apis.md)
#### [API 发行说明](api-release-notes.md)
#### [Microsoft Defender for Endpoint API]()
##### [入门]()
###### [Microsoft Defender for Endpoint API 许可和条款](api-terms-of-use.md)
###### [访问 Microsoft Defender for Endpoint API](apis-intro.md)
###### [Hello World](api-hello-world.md)
###### [ 通过应用上下文获得访问权限](exposed-apis-create-app-webapp.md)
###### [通过户上下文获得访问权限](exposed-apis-create-app-nativeapp.md)



##### [Microsoft Defender for Endpoint API 架构]()
###### [支持的 Microsoft Defender for Endpoint API](exposed-apis-list.md)
###### [常见的 REST API 错误代码](common-errors.md)
###### [高级搜寻](run-advanced-query-api.md)

###### [提醒]()
####### [警报方法和属性](alerts.md)
####### [列出警报](get-alerts.md)
####### [创建警报](create-alert-by-reference.md)
####### [批量更新警报](batch-update-alerts.md)
####### [更新警报](update-alert.md)
####### [通过 ID 获取警报信息](get-alert-info-by-id.md)
####### [获取有关域信息的警报](get-alert-related-domain-info.md)
####### [获取警报相关文件信息](get-alert-related-files-info.md)
####### [获取通知相关 IP 信息](get-alert-related-ip-info.md)
####### [获取警报相关设备信息](get-alert-related-machine-info.md)
####### [获取警报相关用户信息](get-alert-related-user-info.md)


###### [漏洞和安全配置评估]()
####### [导出评估方法和属性](get-assessment-methods-properties.md)
####### [导出安全配置评估](get-assessment-secure-config.md)
####### [导出软件库存评估](get-assessment-software-inventory.md)
####### [导出软件漏洞评估](get-assessment-software-vulnerabilities.md)

###### [自动调查]()
####### [调查方法和属性](investigation.md)
####### [列表调查](get-investigation-collection.md)
####### [获取调查](get-investigation-object.md)
####### [启动调查](initiate-autoir-investigation.md)

###### [域]()
####### [获取域相关警报](get-domain-related-alerts.md)
####### [获取与域相关的计算机](get-domain-related-machines.md)
####### [获取域统计信息](get-domain-statistics.md)

###### [文件]()
####### [文件方法和属性](files.md)
####### [获取文件信息](get-file-information.md)
####### [获取文件相关警报](get-file-related-alerts.md)
####### [获取与文件相关的计算机](get-file-related-machines.md)
####### [获取文件统计信息](get-file-statistics.md)

###### [指示器]()
####### [指示器方法和属性](ti-indicator.md)
####### [列出指示器](get-ti-indicators-collection.md)
####### [提交指示器](post-ti-indicator.md)
####### [导入指示器](import-ti-indicators.md)
####### [删除指示器](delete-ti-indicator-by-id.md)

###### [IP]()
####### [获取 IP 相关警报](get-ip-related-alerts.md)
####### [获取 IP 统计信息](get-ip-statistics.md)

###### [实时响应库]()
####### [实时响应库方法和属性](live-response-library-methods.md)
####### [列表库文件](list-library-files.md)
####### [上传到实时响应库](upload-library.md)
####### [从库中删除](delete-library.md)


###### [计算机]()
####### [计算机方法和属性](machine.md)
####### [列出计算机](get-machines.md)
####### [按 ID 获取计算机](get-machine-by-id.md)
####### [获取计算机登录用户](get-machine-log-on-users.md)
####### [获取计算机相关警报](get-machine-related-alerts.md)
####### [获取已安装的软件](get-installed-software.md)
####### [发现漏洞](get-discovered-vulnerabilities.md)
####### [获取安全建议](get-security-recommendations.md)
####### [添加或删除计算机标记](add-or-remove-machine-tags.md)
####### [按 IP 查找计算机](find-machines-by-ip.md)
####### [通过标记查找计算机](find-machines-by-tag.md)
####### [查找缺失的 KBS](get-missing-kbs-machine.md)
####### [设置设备值](set-device-value.md)
####### [更新计算机](update-machine-method.md)



###### [计算机操作]()
####### [计算机操作方法和属性](machineaction.md)
####### [列出计算机操作](get-machineactions-collection.md)
####### [获取计算机操作](get-machineaction-object.md)
####### [收集调查程序包](collect-investigation-package.md)
####### [获取调查包 SAS URI](get-package-sas-uri.md)
####### [获得实时响应结果](get-live-response-result.md)
####### [隔离计算机](isolate-machine.md)
####### [从隔离释放计算机](unisolate-machine.md)
####### [限制应用执行](restrict-code-execution.md)
####### [删除应用限制](unrestrict-code-execution.md)
####### [运行防病毒扫描](run-av-scan.md)
####### [运行实时响应](run-live-response.md)
####### [载出计算机](offboard-machine-api.md)
####### [停止和隔离文件](stop-and-quarantine-file.md)
####### [取消计算机操作](cancel-machine-action.md)

###### [建议]()
####### [建议方法和属性](recommendation.md)
####### [列出所有建议](get-all-recommendations.md)
####### [按 ID 获取建议](get-recommendation-by-id.md)
####### [按软件获取建议](list-recommendation-software.md)
####### [按建议列出计算机](get-recommendation-machines.md)
####### [按建议列出漏洞](get-recommendation-vulnerabilities.md)

###### [修正活动]()
####### [修正活动方法和属性](get-remediation-methods-properties.md)
####### [按 ID 获取修正活动](get-remediation-one-activity.md)
####### [列出所有修正活动](get-remediation-all-activities.md)
####### [列出修正活动的暴露设备](get-remediation-exposed-devices-activities.md)

###### [分数]()
####### [分数方法和属性](score.md)
####### [按计算机组列出曝光分数](get-machine-group-exposure-score.md)
####### [获取曝光分数](get-exposure-score.md)
####### [获取设备安全分数](get-device-secure-score.md)

###### [软件]()
####### [软件方法和属性](software.md)
####### [列出软件](get-software.md)
####### [按 ID 获取软件](get-software-by-id.md)
####### [列出软件版本分发](get-software-ver-distribution.md)
####### [按软件列出计算机](get-machines-by-software.md)
####### [按软件列出漏洞](get-vuln-by-software.md)
####### [查找缺失的 KBS](get-missing-kbs-software.md)

###### [用户]()
####### [用户方法](user.md)
####### [获取用户相关警报](get-user-related-alerts.md)
####### [获取用户相关计算机](get-user-related-machines.md)

###### [漏洞]()
####### [漏洞方法和属性](vulnerability.md)
####### [列出漏洞](get-all-vulnerabilities.md)
####### [按计算机和软件列出漏洞](get-all-vulnerabilities-by-machines.md)
####### [通过 ID 查找漏洞](get-vulnerability-by-id.md)
####### [按漏洞列出计算机](get-machines-by-vulnerability.md)

##### [如何使用 API - 示例]()
###### [Power Automate](api-microsoft-flow.md)
###### [Power BI](api-power-bi.md)
###### [通过 Python 高级搜寻](run-advanced-query-sample-python.md)
###### [通过 PowerShell 高级搜寻](run-advanced-query-sample-powershell.md)
###### [使用 OData 查询](exposed-apis-odata-samples.md)


#### [原始数据流式处理 API]()
##### [原始数据流式处理](raw-data-export.md)
##### [将高级搜寻事件流式传输至 Azure 事件中心](raw-data-export-event-hub.md)
##### [将高级搜寻事件流式传输至存储账户](raw-data-export-storage.md)

#### [SIEM 集成]()
##### [使用 Microsoft Defender for Endpoint 创建 SIEM 工具](configure-siem.md)
##### [SIEM 工具集成问题疑难解答](troubleshoot-siem.md)

#### [合作伙伴和 API]()
##### [合作伙伴应用程序](partner-applications.md)
##### [已连接的应用程序](connected-applications.md)
##### [API 资源管理器](api-explorer.md)

#### [基于角色的访问控制]()
##### [使用 RBAC 管理门户访问](rbac.md)
##### [创建和管理角色](user-roles.md)
##### [创建和管理设备组]()
###### [使用设备组](machine-groups.md)
###### [创建和管理设备标签](machine-tags.md)







### [托管安全服务提供商 （MSSP） 集成]()
#### [配置托管的安全服务提供商集成](configure-mssp-support.md)
#### [受支持的安全服务提供商](mssp-list.md)
#### [授予 MSSP 对门户的访问权限](grant-mssp-access.md)
#### [访问 MSSP 客户门户](access-mssp-portal.md)
#### [配置警报通知](configure-mssp-notifications.md)
#### [获取合作伙伴应用程序访问权限](exposed-apis-create-app-partners.md)
#### [从客户租户获取警报](fetch-alerts-mssp.md)
#### [托管安全服务提供商商机](mssp-support.md)
### [合作伙伴集成方案]()
#### [技术合作伙伴商机](partner-integration.md)
#### [成为 Microsoft Defender for Endpoint 合作伙伴](get-started-partner-integration.md)
### [集成]()
#### [Microsoft Defender for Endpoint 集成](threat-protection-integration.md)
#### [通过条件访问保护用户、数据和设备](conditional-access.md)
#### [Microsoft Defender for Cloud Apps 集成概述](microsoft-cloud-app-security-integration.md)

### [Windows 中的信息保护概述]()
#### [Windows 集成](information-protection-in-windows-overview.md)

### [访问 Microsoft Defender for Endpoint 社区中心](community.md)

### [有用资源](helpful-resources.md)

## [疑难解答]()
### [解决传感器状态问题]()
#### [检查传感器状态](check-sensor-status.md)
#### [修复有问题传感器](fix-unhealthy-sensors.md)
#### [非活跃设备](fix-unhealthy-sensors.md#inactive-devices)
#### [配置错误的设备](fix-unhealthy-sensors.md#misconfigured-devices)
#### [使用事件查看器查看计算机上的传感器事件和错误](event-error-codes.md)

### [使用客户端分析器排查传感器运行状况问题]()
#### [客户端分析器概述](overview-client-analyzer.md)
#### [下载并运行分析器](download-client-analyzer.md)
#### [在 Windows 上运行客户端分析器](run-analyzer-windows.md)
#### [在 macOS 或 Linux 上运行客户端分析器](run-analyzer-macos-linux.md)
#### [用于在 Windows 上进行高级故障排除的数据收集](data-collection-analyzer.md)
#### [了解分析器 HTML 报表](analyzer-report.md)
#### [在客户端分析器工具上提供反馈](analyzer-feedback.md)

 

### [Microsoft Defender for Endpoint 服务疑难解答]()
#### [服务疑难解答](troubleshoot-mdatp.md)
#### [联系 Microsoft Defender for Endpoint 客户服务](contact-support.md)

### [实时响应问题疑难解答](troubleshoot-live-response.md)

### [使用 LiveAnalyzer 收集支持日志](troubleshoot-collect-support-log.md)

### [解决攻击面减少问题]()
#### [网络保护](troubleshoot-np.md)
#### [攻击面减少规则](troubleshoot-asr.md)
#### [迁移到"攻击"图面减少规则](migrating-asr-rules.md)

# [Microsoft 365 Defender 文档]()
## [Microsoft 365 Defender](../defender/index.yml)
## [Defender for Office 365](../office-365-security/index.yml)
## [Defender for Identity](/defender-for-identity/)
## [Defender for Cloud Apps](/cloud-app-security/)
## [Defender for Business](../defender-business/index.yml)

