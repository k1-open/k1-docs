# K1 公开发布状态

日期：2026-11-26

## 1. 发布结论

K1 的 9 个正式仓库已进入 **Public Developer Preview**。

公开资料可用于应用开发、协议联调、结构适配、配件设计、维修和官方硬件评估。BSP、固件和 App 仍有未完成构建验证项，因此当前公开发布不构成量产级 BSP、完整 Android SDK 或生产 App 承诺。

## 2. 当前公开仓库

| 仓库 | 当前状态 | 遗留风险 |
|---|---|---|
| `.github` | Public Developer Preview | 社区安全策略和自动化仍可继续完善 |
| `k1-docs` | Public Developer Preview | 构建、刷机和兼容文档需随实测更新 |
| `k1-hardware` | Public Developer Preview | 仍需最终电气信息复核 |
| `k1-mechanical` | Public Developer Preview | STEP 已纯结构化，仍需不同 CAD 软件视觉抽查 |
| `k1-protocol` | Public Developer Preview | Input/诊断能力有限，测试向量需随版本维护 |
| `k1-ble-controller` | Public Developer Preview | 固定 ESP-IDF 版本，完成构建、烧录、BLE、OTA 验证 |
| `k1-v851s-bsp` | Public Developer Preview | 缺非显示驱动源码，厂商文档再分发权未确认，全量构建未验证 |
| `k1-sdk` | Public Developer Preview | Python 协议实现可用；Android SDK 和模拟器仍缺失 |
| `k1-apps` | Public Developer Preview | 密码已哈希、Release 默认关闭明文流量；API Key 仍需服务端代理，构建未验证 |

## 3. 已完成的关键修复

- 9 个正式仓库已完成 Git 历史清理，均从单一根提交开始。
- 9 个旧仓库已设置为 Private + Archived 历史归档。
- 新增许可证、商标和第三方边界文件。
- 文档许可证从 CC BY-NC-SA 4.0 调整为 CC BY 4.0。
- 产品规格、硬件设计方案和 R1B 原理图已移除未经授权的无线芯片信息。
- 结构 STEP 已移除 PCBA、FPC、电子元器件和传感器子树。
- 补齐下载、快速开始、构建、刷机、兼容性、FAQ 和公开发布状态文档。
- 增加 Python 协议参考实现及 9 项单元测试。
- App 密码改为 PBKDF2 加盐哈希；Debug 允许本地 HTTP，Release 默认关闭明文流量。

## 4. 公开发布后仍需完成

- 最高权限账号启用 2FA。
- 完善 `main` 分支保护、Secret Scanning 和 Push Protection。
- 持续扫描密钥、Token、手机号、邮箱、客户数据和生产参数。
- 核对 Allwinner 文档、工具和第三方素材的再分发许可。
- 完成 BSP、BLE 固件、App 的固定工具链构建记录。
- 完成 BLE、音频、显示、OTA、恢复和不同手机系统的互操作测试。
- 补齐 Android SDK、设备模拟器和完整 API 文档。
- 创建正式 Release 和版本兼容矩阵。

## 5. 不开放的制造与核心内容

以下内容继续保留，不因仓库公开而授权：

- PCB 源文件、Gerber、钻孔和阻抗文件
- 完整 BOM、贴片坐标、钢网和装配工艺
- 显示驱动、面板时序、Gamma/亮度/颜色校准
- 完整量产固件和生产测试
- 安全启动密钥、签名私钥和设备证书
- 客户数据、供应商报价和内部账号

## 6. Git 历史清理状态

截至 2026-11-26，历史清理已完成。

- 9 个正式仓库的 `main` 分支均只有一个根提交。
- 旧仓库已改名为 `*-private-history-20261125`，设置为 Private + Archived。
- 新仓库不包含旧提交、旧 PCBA STEP、脱敏前 PDF、示例个人信息或不安全账号代码。
- 旧历史仍可在私有归档中用于内部追溯，但不会随公开仓库发布。

注意：本地早期克隆仍包含旧历史，不得直接将这些旧克隆推送到公开仓库。需要修改代码时，应从新的同名仓库重新克隆。
