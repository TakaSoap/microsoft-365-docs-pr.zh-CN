---
title: 使用事件查看器查看事件和错误
description: 获取说明和进一步疑难解答步骤 (如有必要) Microsoft Defender for Endpoint 服务报告的所有事件的说明。
keywords: 疑难解答， 事件查看器， 日志摘要， 故障代码， 失败， Microsoft Defender for Endpoint 服务， 无法启动， 断开， 无法启动
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 05/21/2018
ms.technology: mde
ms.openlocfilehash: 1b8454107b6a2737f1236a066c3a24a2b9c776cb
ms.sourcegitcommit: 1244bbc4a3d150d37980cab153505ca462fa7ddc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/26/2021
ms.locfileid: "51222645"
---
# <a name="review-events-and-errors-using-event-viewer"></a>使用事件查看器查看事件和错误

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**适用于：**
- 事件查看器
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>想要体验 Microsoft Defender for Endpoint？ [注册免费试用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-enablesiem-abovefoldlink)

可以在各个设备上的事件查看器 [中查看](https://msdn.microsoft.com/library/aa745633(v=bts.10).aspx) 事件 ID。

例如，如果设备未显示在"设备"列表中，你可能需要在设备上查找事件 ID。 然后，可以使用此表确定进一步的疑难解答步骤。

**打开事件查看器并查找 Microsoft Defender for Endpoint 服务事件日志：**

1. 单击 **Windows** 菜单上的"开始"，键入 **"事件查看器"，** 然后按 **Enter。**

2. 在日志列表中的"日志 **摘要"下**，滚动到看到 **"Microsoft-Windows-SENSE/Operational"。** 双击该项以打开日志。

   a.  您还可以通过展开"应用程序和服务日志  >  **""Microsoft**  >  **Windows**  >  **SENSE"** 并单击"操作"来访问 **日志**。

   > [!NOTE]
   > SENSE 是内部名称，用于引用支持 Microsoft Defender for Endpoint 的行为传感器。

3. 服务记录的事件将显示在日志中。 有关服务记录的事件的列表，请参阅下表。

<table>
<tbody style="vertical-align:top;">
<tr>
<th>事件 ID</th>
<th>邮件</th>
<th>说明</th>
<th>操作</th>
</tr>
<tr>
<td>1</td>
<td>Microsoft Defender for Endpoint 服务 (版本 <code>variable</code>) 。</td>
<td>在系统启动、关闭和载入期间发生。</td>
<td>正常操作通知;无需任何操作。</td>
</tr>
<tr>
<td>2</td>
<td>Microsoft Defender for Endpoint 服务关闭。</td>
<td>在设备关闭或载出时发生。</td>
<td>正常操作通知;无需任何操作。</td>
</tr>
<tr>
<td>3</td>
<td>Microsoft Defender for Endpoint 服务启动失败。 失败代码 <code>variable</code> ：。</td>
<td>服务未启动。</td>
<td>查看其他消息以确定可能的原因和疑难解答步骤。</td>
</tr>
<tr>
<td>4 </td>
<td>Microsoft Defender for Endpoint 服务与 位于 的服务器联系 <code>variable</code> 。</td>
<td>变量 = 适用于终结点处理服务器的 Defender 的 URL。<br>
此 URL 将匹配防火墙或网络活动中显示的内容。</td>
<td>正常操作通知;无需任何操作。</td>
</tr>
<tr>
<td>5 </td>
<td>Microsoft Defender for Endpoint 服务无法连接到 位于 的服务器 <code>variable</code> 。</td>
<td>变量 = 适用于终结点处理服务器的 Defender 的 URL。<br>
该服务无法通过该 URL 与外部处理服务器联系。</td>
<td>检查与 URL 的连接。 请参阅 <a href="configure-proxy-internet.md" data-raw-source="[Configure proxy and Internet connectivity](configure-proxy-internet.md)">配置代理和 Internet 连接</a>。</td>
</tr>
<tr>
<td>6 </td>
<td>Microsoft Defender for Endpoint 服务未载入，并且未找到任何载入参数。</td>
<td>设备未正确载入，不会向门户报告。</td>
<td>在启动该服务之前，必须运行载入。<br>
检查载入设置和脚本是否正确部署。 尝试重新部署配置包。<br>
请参阅 <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">载入 Windows 10 设备</a>。</td>
</tr>
<tr>
<td>7 </td>
<td>Microsoft Defender for Endpoint 服务无法读取载入参数。 失败 <code>variable</code> ：。</td>
<td>变量 = 详细的错误描述。 设备未正确载入，不会向门户报告。</td>
<td>检查载入设置和脚本是否正确部署。 尝试重新部署配置包。<br>
请参阅 <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">载入 Windows 10 设备</a>。</td>
</tr>
<tr>
<td>8 </td>
<td>Microsoft Defender for Endpoint 服务无法清理其配置。 失败代码 <code>variable</code> ：。</td>
<td><b>载入期间：</b> 服务在载入期间未能清理其配置。 载入过程继续进行。 <br><br> <b>在载出期间：</b> 该服务在载出过程中未能清理其配置。 载出过程已完成，但服务继续运行。
 </td>
<td><b>载入：</b> 无需任何操作。 <br><br> <b>载出：</b> 重新启动系统。<br>
请参阅 <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">载入 Windows 10 设备</a>。</td>
</tr>
<tr>
<td>9 </td>
<td>Microsoft Defender for Endpoint 服务未能更改其启动类型。 失败代码 <code>variable</code> ：。</td>
<td><b>载入期间：</b> 设备未正确载入，不会向门户报告。 <br><br><b>在载出期间：</b> 未能更改服务启动类型。 载出过程继续进行。 </td>
<td>检查载入设置和脚本是否正确部署。 尝试重新部署配置包。<br>
请参阅 <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">载入 Windows 10 设备</a>。</td>
</tr>
<tr>
<td>10  </td>
<td>Microsoft Defender for Endpoint 服务无法保留载入信息。 失败代码 <code>variable</code> ：。</td>
<td>设备未正确载入，不会向门户报告。</td>
<td>检查载入设置和脚本是否正确部署。 尝试重新部署配置包。<br>
请参阅 <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">载入 Windows 10 设备</a>。</td>
</tr>
<tr>
<td>11</td>
<td>已完成 Defender for Endpoint 服务的载入或重新载入。</td>
<td>设备已正确载入。</td>
<td>正常操作通知;无需任何操作。<br>
设备可能需要几个小时才能显示在门户中。</td>
</tr>
<tr>
<td>12 </td>
<td>Microsoft Defender for Endpoint 无法应用默认配置。</td>
<td>服务无法应用默认配置。</td>
<td>此错误应在短时间内解决。</td>
</tr>
<tr>
<td>13</td>
<td>计算得出的 Microsoft Defender for Endpoint 设备 <code>variable</code> ID：。</td>
<td>正常操作过程。</td>
<td>正常操作通知;无需任何操作。</td>
</tr>
<tr>
<td>15 </td>
<td>Microsoft Defender for Endpoint 无法使用 URL 启动命令通道 <code>variable</code> ：。</td>
<td>变量 = 适用于终结点处理服务器的 Defender 的 URL。<br>
该服务无法通过该 URL 与外部处理服务器联系。</td>
<td>检查与 URL 的连接。 请参阅 <a href="configure-proxy-internet.md" data-raw-source="[Configure proxy and Internet connectivity](configure-proxy-internet.md)">配置代理和 Internet 连接</a>。</td>
</tr>
<tr>
<td>17 </td>
<td>Microsoft Defender for Endpoint 服务未能更改连接用户体验和遥测服务位置。 失败代码 <code>variable</code> ：。</td>
<td>Windows 遥测服务出错。</td>
<td><a href="troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy" data-raw-source="[Ensure the diagnostic data service is enabled](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)">确保诊断数据服务已启用</a>。<br>
检查载入设置和脚本是否正确部署。 尝试重新部署配置包。<br>
请参阅 <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">载入 Windows 10 设备</a>。</td>
</tr>
<tr>
<td>18 </td>
<td>OOBE (Windows 欢迎) 已完成。</td>
<td>服务仅在任何 Windows 更新完成安装后启动。</td>
<td>正常操作通知;无需任何操作。</td>
</tr>
<tr>
<td>19</td>
<td>OOBE (Windows 欢迎) 尚未完成。</td>
<td>服务仅在任何 Windows 更新完成安装后启动。</td>
<td>正常操作通知;无需任何操作。<br>
如果在系统重新启动后此错误仍然存在，请确保所有 Windows 更新都已安装完整。</td>
</tr>
<tr>
<td>20</td>
<td>无法等待 OOBE (Windows 欢迎) 完成。 失败代码 <code>variable</code> ：。</td>
<td>内部错误。</td>
<td>如果在系统重新启动后此错误仍然存在，请确保所有 Windows 更新都已安装完整。</td>
</tr>
<tr>
<td>25</td>
<td>Microsoft Defender for Endpoint 服务无法重置注册表中的运行状况状态。 失败代码 <code>variable</code> ：。</td>
<td>设备未正确载入。
它将报告给门户，但该服务可能不会显示为在 SCCM 或注册表中注册。</td>
<td>检查载入设置和脚本是否正确部署。 尝试重新部署配置包。<br>
请参阅 <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">载入 Windows 10 设备</a>。</td>
</tr>
<tr>
<td>26</td>
<td>Microsoft Defender for Endpoint 服务未能在注册表中设置载入状态。 失败代码 <code>variable</code> ：。</td>
<td>设备未正确载入。<br>
它将报告给门户，但该服务可能不会显示为在 SCCM 或注册表中注册。</td>
<td>检查载入设置和脚本是否正确部署。 尝试重新部署配置包。<br>
请参阅 <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">载入 Windows 10 设备</a>。</td>
</tr>
<tr>
<td>27</td>
<td>Microsoft Defender for Endpoint 服务未能在 Microsoft Defender 防病毒中启用 SENSE 感知模式。 载入过程失败。 失败代码 <code>variable</code> ：。</td>
<td>通常情况下，如果另一个实时反恶意软件产品正在设备上正常运行，并且设备向 Defender for Endpoint 报告，Microsoft Defender 防病毒将进入特殊的被动状态。</td>
<td>检查载入设置和脚本是否正确部署。 尝试重新部署配置包。<br>
请参阅 <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">载入 Windows 10 设备</a>。<br>
确保实时反恶意软件保护运行正常。</td>
</tr>
<tr>
<td>28</td>
<td>Microsoft Defender 终结点连接用户体验和遥测服务注册失败。 失败代码 <code>variable</code> ：。</td>
<td>Windows 遥测服务出错。</td>
<td><a href="troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy" data-raw-source="[Ensure the diagnostic data service is enabled](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)">确保诊断数据服务已启用</a>。<br>
检查载入设置和脚本是否正确部署。 尝试重新部署配置包。<br>
请参阅 <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">载入 Windows 10 设备</a>。</td>
</tr>
<tr>
<td>29</td>
<td>未能读取 offboarding参数。 错误类型：%1，错误代码：%2，说明：%3 </td>
<td>当系统无法读取&#39;时，将发生此事件。</td>
<td>确保设备可以访问 Internet，然后再次运行整个载出过程。 确保载出包尚未过期。</td>
</tr>
<tr>
<td>30</td>
<td>Microsoft Defender for Endpoint 服务在 Microsoft Defender 防病毒中未能禁用 SENSE 感知模式。 失败代码 <code>variable</code> ：。</td>
<td>通常情况下，如果另一个实时反恶意软件产品正在设备上正常运行，并且设备向 Defender for Endpoint 报告，Microsoft Defender 防病毒将进入特殊的被动状态。</td>
<td>检查载入设置和脚本是否正确部署。 尝试重新部署配置包。<br>
请参阅 <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">载入 Windows 10 设备</a><br>
确保实时反恶意软件保护运行正常。</td>
</tr>
<tr>
<td>31</td>
<td>Microsoft Defender 终结点连接用户体验和遥测服务注销失败。 失败代码 <code>variable</code> ：。</td>
<td>载入期间 Windows 遥测服务出错。 载出过程继续进行。</td>
<td><a href="troubleshoot-onboarding.md#ensure-the-diagnostic-data-service-is-enabled" data-raw-source="[Check for errors with the Windows telemetry service](troubleshoot-onboarding.md#ensure-the-diagnostic-data-service-is-enabled)">检查 Windows 遥测服务的错误</a>。</td>
</tr>
<tr>
<td>32</td>
<td>Microsoft Defender for Endpoint 服务在离开进程后无法请求自行停止。 失败代码：%1</td>
<td>在载出期间出错。</td>
<td>重新启动设备。</td>
</tr>
<tr>
<td>33</td>
<td>Microsoft Defender for Endpoint 服务无法保留 SENSE GUID。 失败代码 <code>variable</code> ：。</td>
<td>唯一标识符用于表示向门户报告的每个设备。<br>
如果标识符未保留，同一设备可能在门户中出现两次。</td>
<td>检查设备的注册表权限，以确保服务可以更新注册表。</td>
</tr>
<tr>
<td>34</td>
<td>Microsoft Defender for Endpoint 服务无法将自身添加为连接用户体验和遥测服务的依赖项，从而导致载入过程失败。 失败代码 <code>variable</code> ：。</td>
<td>Windows 遥测服务出错。</td>
<td><a href="troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy" data-raw-source="[Ensure the diagnostic data service is enabled](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)">确保诊断数据服务已启用</a>。<br>
检查载入设置和脚本是否正确部署。 尝试重新部署配置包。<br>
请参阅 <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">载入 Windows 10 设备</a>。</td>
</tr>
<tr>
<td>35</td>
<td>Microsoft Defender for Endpoint 服务无法删除自身作为连接用户体验和遥测服务的依赖项。 失败代码 <code>variable</code> ：。</td>
<td>在载出期间 Windows 遥测服务出错。 载出过程继续进行。
</td>
<td>检查 Windows 诊断数据服务的错误。</td>
</tr>
<tr>
<td>36</td>
<td>Microsoft Defender 终结点连接用户体验和遥测服务注册成功。 完成代码 <code>variable</code> ：。</td>
<td>为终结点注册已成功完成连接用户体验和遥测服务的 Defender。</td>
<td>正常操作通知;无需任何操作。</td>
</tr>
<tr>
<td>37</td>
<td>Microsoft Defender for Endpoint A 模块即将超过其配额。 模块：%1，配额：{%2} {%3}，配额使用率百分比：%4。</td>
<td>设备几乎已使用当前 24 小时时段的已分配配额。 即将被限制。</td>
<td>正常操作通知;无需任何操作。</td>
</tr>
<tr>
<td>38</td>
<td>网络连接标识为低。 Microsoft Defender for Endpoint 将每 %1 分钟与服务器联系一次。 按流量计费的连接：%2，Internet 可用：%3，可用网络：%4。</td>
<td>设备使用按流量计费/付费网络，并且与服务器联系的频率将较低。</td>
<td>正常操作通知;无需任何操作。</td>
</tr>
<tr>
<td>39</td>
<td>网络连接被标识为正常连接。 Microsoft Defender for Endpoint 将每 %1 分钟与服务器联系一次。 按流量计费的连接：%2，Internet 可用：%3，可用网络：%4。</td>
<td>设备没有使用按流量计费/付费的连接，将照常与服务器联系。</td>
<td>正常操作通知;无需任何操作。</td>
</tr>
<tr>
<td>40</td>
<td>电池状态标识为低。 Microsoft Defender for Endpoint 将每 %1 分钟与服务器联系一次。 电池状态：%2。</td>
<td>设备具有低电池电量，并且与服务器的联系频率较低。</td>
<td>正常操作通知;无需任何操作。</td>
</tr>
<tr>
<td>41</td>
<td>电池状态标识为正常。 Microsoft Defender for Endpoint 将每 %1 分钟与服务器联系一次。 电池状态：%2。</td>
<td>设备没有低电池电量，将照常与服务器联系。</td>
<td>正常操作通知;无需任何操作。</td>
</tr>
<tr>
<td>42</td>
<td>Microsoft Defender for Endpoint WDATP 组件无法执行该操作。 组件：%1，操作：%2，异常类型：%3，异常消息：%4</td>
<td>内部错误。 服务启动失败。</td>
<td>如果此错误仍然存在，请联系支持人员。</td>
</tr>
<tr>
<td>43</td>
<td>Microsoft Defender for Endpoint WDATP 组件无法执行该操作。 组件：%1，操作：%2，异常类型：%3，异常错误：%4，异常消息：%5</td>
<td>内部错误。 服务启动失败。</td>
<td>如果此错误仍然存在，请联系支持人员。</td>
</tr>
<tr>
<td>44</td>
<td>已完成 Defender for Endpoint Service 的载出。</td>
<td>服务已载出。</td>
<td>正常操作通知;无需任何操作。</td>
</tr>
<tr>
<td>45</td>
<td>未能注册和启动事件跟踪会话 [%1]。 错误代码：%2</td>
<td>创建 ETW 会话时，服务启动出错。 这导致了服务启动失败。</td>
<td>如果此错误仍然存在，请联系支持人员。</td>
</tr>
<tr>
<td>46</td>
<td>由于缺少资源，无法注册和启动事件跟踪会话 [%1]。 错误代码：%2。 这很可能是因为活动事件跟踪会话过多。 该服务将在 1 分钟内重试。</td>
<td>创建 ETW 会话时，服务启动出错，因为缺少资源。 该服务已启动且正在运行，但在启动 ETW 会话之前不会报告任何传感器事件。</td>
<td>正常操作通知;无需任何操作。 该服务将尝试每分钟启动会话。</td>
</tr>
<tr>
<td>47</td>
<td>已成功注册并启动事件跟踪会话 - 在上一次尝试失败后恢复。</td>
<td>在成功启动 ETW 会话后，此事件跟在上一个事件之后。</td>
<td>正常操作通知;无需任何操作。</td>
</tr>
<tr>
<td>48</td>
<td>未能将提供程序 [%1] 添加到事件跟踪会话 [%2]。 错误代码：%3。 这意味着不会报告来自此提供程序的事件。</td>
<td>未能将提供程序添加到 ETW 会话。 因此，不会报告提供程序事件。</td>
<td>检查错误代码。 如果错误仍然存在，请联系支持人员。</td>
</tr>
</tr>
<tr>
   <td>49</td>
   <td>收到并忽略无效的云配置命令。 版本：%1，状态：%2，错误代码：%3，消息：%4</td>
   <td>从已忽略的云服务收到无效的配置文件。</td>
   <td>如果此错误仍然存在，请联系支持人员。</td>
</tr>
<tr>
   <td>50</td>
   <td>已成功应用新的云配置。 版本：%1。</td>
   <td>已成功应用云服务中的新配置。</td>
   <td>正常操作通知;无需任何操作。</td>
</tr>
<tr>
   <td>51</td>
   <td>新云配置应用失败，版本：%1。 已成功应用上一个已知良好的配置版本 %2。</td>
   <td>从云服务收到错误配置文件。 已成功应用上一个已知良好的配置。</td>
   <td>如果此错误仍然存在，请联系支持人员。</td>
</tr>
<tr>
   <td>52</td>
   <td>新云配置应用失败，版本：%1。 还未能应用上一个已知良好的配置版本 %2。 已成功应用默认配置。</td>
   <td>从云服务收到错误配置文件。 未能应用上一个已知的良好配置，并且应用了默认配置。</td>
   <td>该服务将尝试在 5 分钟内下载新的配置文件。 如果看不到事件或#50联系支持人员。</td>
</tr>
<tr>
   <td>53</td>
   <td>从持久性存储加载的云配置，版本：%1。</td>
   <td>配置是在服务启动时从永久性存储加载的。</td>
   <td>正常操作通知;无需任何操作。</td>
</tr>
<tr>
   <td>55</td>
   <td>未能创建安全 ETW 自动记录器。 失败代码：%1</td>
   <td>未能创建安全的 ETW 记录器。</td>
   <td>重新启动设备。 如果此错误仍然存在，请联系支持人员。</td>
</tr>
<tr>
   <td>56</td>
   <td>未能删除安全 ETW 自动记录器。 失败代码：%1</td>
   <td>在载出时未能删除安全 ETW 会话。</td>
   <td>联系支持人员。</td>
</tr>
<tr>
   <td>57</td>
   <td>捕获计算机快照以进行故障排除。</td>
   <td>正在收集调查包（也称为取证包）。</td>
   <td>正常操作通知;无需任何操作。</td>
</tr>
<tr>
   <td>59</td>
   <td>启动命令：%1</td>
   <td>开始执行响应命令。</td>
   <td>正常操作通知;无需任何操作。</td>
</tr>
<tr>
   <td>60</td>
   <td>未能运行命令 %1，错误：%2。</td>
   <td>未能执行响应命令。</td>
   <td>如果此错误仍然存在，请联系支持人员。</td>
</tr>
<tr>
   <td>61</td>
   <td>数据收集命令参数无效：SasUri：%1，compressionLevel：%2。</td>
   <td>无法读取或分析数据集合命令参数， (参数) 。</td>
   <td>如果此错误仍然存在，请联系支持人员。</td>
</tr>
<tr>
   <td>62</td>
   <td>无法启动连接用户体验和遥测服务。 失败代码：%1</td>
   <td>diagtrack 服务 (连接用户体验) 遥测服务失败。 不会从此计算机发送非 Microsoft Defender for Endpoint 遥测。</td>
   <td>在事件日志中查找更多疑难解答提示：Microsoft-Windows-UniversalTelemetryClient/Operational。</td>
</tr>
<tr>
   <td>63</td>
   <td>更新外部服务的启动类型。 名称：%1，实际开始类型：%2，预期开始类型：%3，退出代码：%4</td>
   <td>更新了外部服务的启动类型。</td>
   <td>正常操作通知;无需任何操作。</td>
</tr>
<tr>
   <td>64</td>
   <td>启动已停止的外部服务。 名称：%1，退出代码：%2</td>
   <td>启动外部服务。</td>
   <td>正常操作通知;无需任何操作。</td>
</tr>
<tr>
   <td>65</td>
   <td>未能加载 Microsoft 安全事件组件微筛选器驱动程序。 失败代码：%1</td>
   <td>未能加载MsSecFlt.sys微筛选器。</td>
   <td>重新启动设备。 如果此错误仍然存在，请联系支持人员。</td>
</tr>
<tr>
   <td>66</td>
   <td>策略更新：延迟模式 - %1</td>
   <td>更新C&C 连接频率策略。</td>
   <td>正常操作通知;无需任何操作。</td>
</tr>
<tr>
   <td>68</td>
   <td>服务的启动类型是意外的。 服务名称：%1，实际启动类型：%2，预期启动类型：%3</td>
   <td>意外的外部服务启动类型。</td>
   <td>修复外部服务启动类型。</td>
</tr>
<tr>
   <td>69</td>
   <td>服务已停止。 服务名称：%1</td>
   <td>外部服务已停止。</td>
   <td>启动外部服务。</td>
</tr>
<tr>
   <td>70</td>
   <td>策略更新：允许示例集合 - %1</td>
   <td>示例集合策略已更新。</td>
   <td>正常操作通知;无需任何操作。</td>
</tr>
<tr>
   <td>71</td>
   <td>成功运行命令：%1</td>
   <td>命令已成功执行。</td>
   <td>正常操作通知;无需任何操作。</td>
</tr>
<tr>
   <td>72</td>
   <td>尝试发送第一个完整的计算机配置文件报告。 结果代码：%1</td>
   <td>仅供参考。</td>
   <td>正常操作通知;无需任何操作。</td>
</tr>
<tr>
   <td>73</td>
   <td>从平台开始感知：%1</td>
   <td>仅供参考。</td>
   <td>正常操作通知;无需任何操作。</td>
</tr>
<tr>
   <td>74</td>
   <td>注册表中的设备标记超出长度限制。 标记名称：%2。 长度限制：%1。</td>
   <td>设备标记超出长度限制。</td>
   <td>使用较短的设备标记。</td>
</tr>
<tr>
   <td>81</td>
   <td>创建高级威胁Windows Defender ETW 自动记录器失败。 失败代码：%1</td>
   <td>未能创建 ETW 会话。</td>
   <td>重新启动设备。 如果此错误仍然存在，请联系支持人员。</td>
</tr>
<tr>
   <td>82</td>
   <td>无法删除高级Windows Defender ETW 自动记录器。 失败代码：%1</td>
   <td>未能删除 ETW 会话。</td>
   <td>联系支持人员。</td>
</tr>
<tr>
   <td>84</td>
   <td>设置Windows Defender防病毒运行模式。 强制被动模式：%1，结果代码：%2。</td>
   <td>将 defender 运行模式设置为 (或被动) 。</td>
   <td>正常操作通知;无需任何操作。</td>
</tr>
<tr>
   <td>85</td>
   <td>无法触发高级Windows Defender高级威胁防护可执行文件。 失败代码：%1</td>
   <td>Starring SenseIR 可执行文件失败。</td>
   <td>重新启动设备。 如果此错误仍然存在，请联系支持人员。</td>
</tr>
<tr>
   <td>86</td>
   <td>再次启动已停止应启动的外部服务。 名称：%1，退出代码：%2</td>
   <td>再次启动外部服务。</td>
   <td>正常操作通知;无需任何操作。</td>
</tr>
<tr>
   <td>87</td>
   <td>无法启动外部服务。 名称：%1</td>
   <td>无法启动外部服务。</td>
   <td>联系支持人员。</td>
</tr>
<tr>
   <td>88</td>
   <td>再次更新外部服务的启动类型。 名称：%1，实际开始类型：%2，预期开始类型：%3，退出代码：%4</td>
   <td>更新了外部服务的启动类型。</td>
   <td>正常操作通知;无需任何操作。</td>
</tr>
<tr>
   <td>89</td>
   <td>无法更新外部服务的启动类型。 名称：%1，实际开始类型：%2，预期开始类型：%3</td>
   <td>无法更新外部服务的启动类型。</td>
   <td>联系支持人员。</td>
</tr>
<tr>
   <td>90</td>
   <td>未能将 System Guard 运行时监视器配置为连接到地理位置 %1 中的云服务。 失败代码：%2</td>
   <td>System Guard 运行时监视器不会向云服务发送证明数据。</td>
   <td>检查注册路径上的权限："HKLM\Software\Microsoft\Windows\CurrentVersion\Sgrm"。 如果没有问题，请联系支持人员。</td>
</tr>
<tr>
   <td>91</td>
   <td>未能删除 System Guard 运行时监视器地理位置信息。 失败代码：%1</td>
   <td>System Guard 运行时监视器不会向云服务发送证明数据。</td>
   <td>检查注册路径上的权限："HKLM\Software\Microsoft\Windows\CurrentVersion\Sgrm"。 如果没有问题，请联系支持人员。</td>
</tr>
<tr>
   <td>92</td>
   <td>由于超过数据配额，停止发送传感器网络数据配额。 配额期通过后，将恢复发送。 状态掩码：%1</td>
   <td>超过限制。</td>
   <td>正常操作通知;无需任何操作。</td>
</tr>
<tr>
   <td>93</td>
   <td>恢复发送传感器网络数据。 状态掩码：%1</td>
   <td>恢复网络数据提交。</td>
   <td>正常操作通知;无需任何操作。</td>
</tr>
<tr>
   <td>94</td>
   <td>Windows Defender高级威胁防护可执行文件已启动</td>
   <td>SenseCE 可执行文件已启动。</td>
   <td>正常操作通知;无需任何操作。</td>
</tr>
<tr>
   <td>95</td>
   <td>Windows Defender高级威胁防护可执行文件已结束</td>
   <td>SenseCE 可执行文件已结束。</td>
   <td>正常操作通知;无需任何操作。</td>
</tr>
<tr>
   <td>96</td>
   <td>Windows Defender高级威胁防护 Init 已调用。 结果代码：%2</td>
   <td>SenseCE 可执行文件称为 MCE 初始化。</td>
   <td>正常操作通知;无需任何操作。</td>
</tr>
<tr>
   <td>97</td>
   <td>DLP 方案的云存在连接问题</td>
   <td>存在影响 DLP 分类流的网络连接问题。</td>
   <td>检查网络连接。</td>
</tr>
<tr>
   <td>98</td>
   <td>已还原与 DLP 方案的云的连接</td>
   <td>已还原与网络的连接，DLP 分类流可以继续。</td>
   <td>正常操作通知;无需任何操作。</td>
</tr>
<tr>
   <td>99</td>
   <td>与服务器通信时，Sense 遇到以下错误： (%1) 。 结果： (%2) </td>
   <td>发生通信错误。</td>
   <td>检查事件日志中的以下事件，了解更多详细信息。</td>
</tr>
<tr>
   <td>100</td>
   <td>Windows Defender高级威胁防护可执行文件无法启动。 失败代码：%1</td>
   <td>SenseCE 可执行文件无法启动。</td>
   <td>重新启动设备。 如果此错误仍然存在，请联系支持人员。</td>
</tr>
<tr>
   <td>102</td>
   <td>Windows Defender高级威胁防护网络检测和响应可执行文件已启动</td>
   <td>SenseNdr 可执行文件已启动。</td>
   <td>正常操作通知;无需任何操作。</td>
</tr>
<tr>
   <td>103</td>
   <td>Windows Defender高级威胁防护网络检测和响应可执行文件已结束</td>
   <td>SenseNdr 可执行文件已结束。</td>
   <td>正常操作通知;无需任何操作。</td>
</tr>
</tbody>
</table>

>想要体验 Microsoft Defender for Endpoint？ [注册免费试用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-eventerrorcodes-belowfoldlink)

## <a name="related-topics"></a>相关主题
- [载入 Windows 10 设备](configure-endpoints.md)
- [配置设备代理和 Internet 连接设置](configure-proxy-internet.md)
- [Microsoft Defender for Endpoint 疑难解答](troubleshoot-onboarding.md)
