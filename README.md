## Commit 记录

| # | 日期 | 版本 | 类型 | 来源需求 | 改动 |
| --- | --- | --- | --- | --- | --- |
| 1 | 2026-10-31 | v1.0 | feat | Omada Guard APP-Event和导航栏优化 | Event 和导航栏首版：底部 Tab 为 Video / Notifications / Devices / Me，Video 支持大小图和自动播放 |
| 2 | 2026-10-31 | v1.0 | chore | Omada Guard APP-Event和导航栏优化 | 新增「五、可交互 Demo」：Demo、源码包、更新规则和版本记录，作为唯一基线 |
| 3 | 2026-10-31 | — | docs | 框架对比 | 旧文档合并进「移动端设计与原型规范」子页，冲突以新文档为准 |
| 4 | 2026-10-31 | — | chore | 设计规范路由 | AI 说明写明：Guard APP 设计用框架页 Skill，VIGI APP 用 VIGI 文档 |
| 5 | 2026-10-31 | v1.1 | feat | Omada Guard APP-Event和导航栏优化 | Notifications 改名 Event；新增 Search Tab；源码包更新规则自动生效 |
| 6 | 2026-10-31 | v1.2 | fix | Omada Guard APP-Event和导航栏优化 | Search 只给企业版和 Fusion 用，只按人 / 车属性检索，去掉文字搜索 |
| 7 | 2026-10-31 | v1.3 | feat | Omada Guard APP-组织与站点管理优化 | 组织列表改为 Systems；页头为头像 + 名称胶囊切换器；个人版新增 Services Tab；Local Mode 切换确认 |
| 8 | 2026-10-31 | v1.4 | style | Omada Guard APP-组织与站点管理优化 | 页头对齐；Site 列表可折叠；Site 行用设备类型图标；Central Site 可切换应用 |
| 9 | 2026-10-31 | v1.5 | feat | Omada Guard APP-组织与站点管理优化 | 切换入口只在首页；新增 Settings Tab；统一过渡动效；新增 Unbind Device；Search 默认显示最近抓拍 |
| 10 | 2026-10-31 | — | chore | Omada Guard APP-Event和导航栏优化 | PRD 中的 Demo 改为同步区块，关联框架页最新 Demo |
| 11 | 2026-10-31 | v1.6 | feat | Omada Guard APP-Video模块优化 | 视图下拉、顶栏状态、卡片 4 种状态、Devices 筛选、发现新设备弹窗 |
| 12 | 2026-10-31 | v1.6a | docs | Omada Guard APP-Video模块优化 | 评审结论写回 PRD V0.2，Demo 不变 |
| 13 | 2026-11-01 | v1.7 | feat | Omada Guard APP-注册登录流程 | 未登录首页改为 Log In；不登录可添加 Fusion；注册实时校验；激活后自动登录；首次登录选择用途 |
| 14 | 2026-11-01 | v1.8 | feat | Omada Guard APP-Device Settings | 设备详情（IPC / NVR）统一为设备卡 + 3 个 Tab + ⋯ |
| 15 | 2026-11-01 | v1.9 | feat | Omada Guard APP-Live View | Live View 按 PRD v0.4 重做，与 PRD 原型共用一份代码 |
| 16 | 2026-11-01 | — | chore | 更新日志 | 新建本页；框架页「更新规则」和 EZ(bot) 新增：每次更新后在本页记录日志 |
| 17 | 2026-11-01 | — | docs | 更新日志 | 新增「原话记录：问题与修改建议」：收录 7 个需求文档中的问题原文和对话中的修改意见原话 |

## 改动清单

### v1.0 – v1.2 · Event 和导航栏（4 轮）

来源：Omada Guard APP-Event和导航栏优化（PRD V0.1 → V0.3）

- **第 1 轮（v1.0）**
    - Notifications 移到底部 Tab，默认显示 Events，可切到 Device Status / System；未读红点最多显示 99+。
    - Video 小图两列、大图一列；可视区内静音自动播放，同时最多 6 路（小图）/ 3 路（大图）；去掉右上角铃铛。
- **第 2 轮（v1.0）**：Demo 源码放进框架页，之后需求都在这份 Demo 上改。
- **第 3 轮（v1.1）**
    - 底部 Tab 改为 Video / Event / Devices / Search / Me。
    - Search 首版：Human / Vehicle、摄像机范围、时间、属性筛选，结果按天分组。
    - EZ(bot) 和两个 PRD 模板加入源码包更新规则。
- **第 4 轮（v1.2）**
    - 个人版去掉 Search，保留 4 个 Tab。
    - Search 改为纯属性检索：人 7 个属性，车 2 个属性。
    - 埋点去掉文字搜索参数，新增 `attr_count`、`org_type`。

### v1.3 – v1.5 · 组织与站点管理（3 轮）

来源：Omada Guard APP-组织与站点管理优化（PRD V0.1 → V0.3）

- **第 1 轮（v1.3）**
    - 新增 Systems 列表（分组 + 类型 Chip + 搜索）；添加分为「创建组织」和「添加 Fusion」。
    - 左上角头像进入 Me，名称胶囊切换系统 / Site。
    - Liquid Glass 在 iOS 18 及以下和 Android 降级为白底阴影（规范例外）。
- **第 2 轮（v1.4），7 条反馈**
    - Systems 标题居中；Video、Dashboard 去掉页面标题。
    - Services 去掉头像和切换入口。
    - Site 列表默认显示 Dashboard 和最多 4 个 Site，其余 Show all 展开。
    - Site 行改用 Camera / NVR / Solar / SightCast 图标。
    - 新增切换应用；新增埋点 `switcher_sites_toggle`、`app_switch`。
- **第 3 轮（v1.5），7 条反馈**
    - 头像和胶囊只在首页显示；统计项改名 Surveillance。
    - Central Site 和 Fusion 第 5 个 Tab 改为 Settings。
    - 统一过渡动效；开启「减少动态效果」时只用 0.2s 淡入淡出。
    - 新增 Unbind Device：NVR 连同通道一起解绑，不恢复出厂、不删录像。
    - Search 默认显示最近 7 天抓拍，顶部 4 类筛选。
- **补充**：Event PRD 中的 Demo 改为同步区块，跟随框架页最新版本。

### v1.6 · Video 模块（2 轮）

来源：Omada Guard APP-Video模块优化（PRD V0.1 → V0.2）

- **第 1 轮（v1.6）**
    - 摄像机数量统计改为视图下拉，默认 All Cameras。
    - 顶栏状态一次一条：Fusion 新固件 › 设备可升级 › 设备离线。
    - 卡片 4 种状态：播放中、播放结束、播放失败、离线；去掉 Privacy mode。
    - 大图名称与近期事件对齐；Fusion 可切换应用，菜单带图标。
    - Devices 新增 Status / Firmware 筛选；Video 首页新增发现新设备弹窗。
    - 模块定义 3.1 / 5.1 / 5.2 / 10.1 标为待评审。
- **第 2 轮（v1.6a，只改 PRD）**
    - 播放 1 分钟后中断，点 Refresh 重新计时；不设计隐私遮蔽状态。
    - 自定义视图与 Web 同步。
    - 新设备检测：个人版和企业版由 APP 本地扫描，Fusion 由 APP 向 Fusion 查询；检测到才弹，最早在进入 Video 2.5 秒后。

### v1.7 · 注册登录流程（1 轮 + 修正）

来源：Omada Guard APP-注册登录流程（PRD V0.1）

- **启动与未登录**
    - 首次打开先同意隐私协议，未登录首页直接是 Log In。
    - Log In 页下方为 Fusion Gateway、Local Mode 两个免账号入口。
    - 新增未登录版 Systems、Add a System、Me。
- **Add Fusion Gateway**
    - 覆盖查找中、结果、无结果、未连 Wi‑Fi、无本地网络权限 5 种状态。
    - Other Setup Options 改名 Add by IP Address。
- **注册**
    - 未填完时 Sign Up 置灰，点击定位到缺失项。
    - 密码规则和强度实时显示，两次密码实时比对。
    - Newsletter 默认不勾（待法务确认）。
- **激活与首次登录**
    - 验证邮件页检测到激活后自动登录。
    - 新账号先选用途：My Omada Guard / Fusion Gateway / Omada Central Organization。
    - Log Out 二次确认。
- **同步**：新建子页 1.1.5 注册 TP-Link ID，相关子页加「待评审」行。
- **修正**：说明板「未连 Wi‑Fi」原误写为误报，已改正（截图中的 5G 为蜂窝网络）。

### v1.8 · Device Settings（调研 → 方案）

来源：Omada Guard APP-Device Settings

- **前置调研**：Omada Network APP 设备配置页；7 款竞品 APP 的 IPC 设置页；Reolink、eufy 的 NVR 设置页。
- **方案**
    - IPC Tab 为 Overview / Smart / Settings，NVR 为 Overview / Channels / Settings。
    - Overview 显示录像与存储，以及 Arming、Night Vision、Siren / Alarm Output 快捷开关。
    - Smart 平铺侦测，直接显示开关、计划和区域。
    - Reboot、Firmware Update、Reset、Forget 只在 ⋯ 菜单；Forget 分为 Forget 和 Forget and Reset。
    - 新增摄像机离线、NVR 无硬盘、通道离线状态。
    - Live View 右上角设置直达 Settings。
- **合并**：基于 v1.7 发布；跨模块问题加入框架页「跨模块待确认」。

### v1.9 · Live View（PRD 4 轮后合并）

来源：Omada Guard APP-Live View（PRD v0.1 → v0.4）

- **调研**：对比 7 款竞品；改用实机截图，删除门铃相关内容，补充 Ring 结论。
- **v0.1**
    - 时间轴常驻，拖动即回看。
    - 对讲不再区分对讲模式和通话模式。
    - 下载默认「下载此片段」；低频功能收进「更多」。
    - 新增失败态和状态互斥两张表。
- **v0.2（10 条意见）**
    - 多画面移到顶栏；时间轴高度约 150 pt → 84 pt。
    - 主操作只显示图标；事件颜色图例改为可点的类型图标。
    - 电子放大只保留双指手势；双画面默认开启，首次进入有引导。
    - 主操作为对讲、抓图、录像、警戒、灯光、云台 + 更多，按设备能力显示。
    - 「更多」新增报警输出和快捷设置；画面控件不再自动隐藏。
- **v0.3（7 条意见）**
    - 放大画面在上、全景在下，加 1x–5x 点状倍数滑杆。
    - 暂停、声音、清晰度移到左侧；「回到直播」移到时间轴右侧。
    - 云台可与双画面同时用；面板为变焦 / 摇杆 / 转速三列，底栏为保存位置、预置位、校准。
    - 智能画框标签改为图标；原型界面改为英文。
- **v0.4（4 条意见）**
    - 顶栏按规范改为 44 pt 玻璃圆 + 玻璃胶囊，标题两行（设备名 +「CHn · NVR」）。
    - 「直播 ›」悬浮在轨道右端，不挤压时间轴，播放头居中。
    - 事件卡文字标签改为类型图标。
    - 合并进框架页 Demo v1.9；新增 9 个 `liveview_*` 埋点；3.2、3、3.3 子页同步更新。
