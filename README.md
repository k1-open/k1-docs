# K1 Open Platform Documentation

K1 外挂式智能眼镜开放开发平台的文档入口，说明开放范围、资料下载、开发路径、兼容性和许可证边界。

## 快速入口

- [下载与使用说明](docs/download.md)
- [开放范围](docs/open-scope.md)
- [快速开始](docs/quickstart.md)
- [构建说明](docs/build.md)
- [刷机与恢复](docs/flashing.md)
- [兼容性](docs/compatibility.md)
- [常见问题](docs/faq.md)
- [公开准备状态](docs/release-readiness.md)\n- [K1 开源总体方案（当前版）](planning/K1_开源总体方案_20261125.md)

## 完整开发资料下载

K1 开放开发资料、封版后的系统资料和 V851S/Tina SDK 资料通过百度网盘分发：

- [百度网盘下载](https://pan.baidu.com/s/1eL-c3V66wPL7c91cLX-_5A?pwd=33pb)
- 提取码：`33pb`
- 分享目录：`k1`

> 显示驱动及核心实现已封版，不提供开放源代码；面板初始化时序、Gamma/亮度校准、显示私有固件和生产资料不在开放范围内。显示功能通过官方硬件、显示模组和公开 API 提供。

详细说明见 [下载与使用说明](docs/download.md)。GitHub 与网盘均可直接访问，无需先购买硬件。

## 平台定位

K1 采用“公开开发资料 + 官方硬件销售 + 开发能力开放 + 制造边界保留”的开放开发平台模式。

- 公开资料无需购买、注册或人工审批即可获取。
- 购买官方硬件不是下载资料、开发应用或设计配件的前提。
- 购买官方硬件不授予 PCB 制造、贴片生产、批量制造、OEM/ODM 或商业出货权。
- K1 是 source-available development platform，不应宣传为所有硬件资料均可自由制造的 OSI/OSHWA 开源硬件。

## 当前已提供

| 仓库 | 当前内容 | 状态 |
|---|---|---|
| `k1-docs` | 产品规格、硬件设计方案、测试标准、开发与下载说明 | 可用 |
| `k1-hardware` | 4 份原理图 PDF、硬件设计方案公开版、技术支持说明 | 可用 |
| `k1-mechanical` | 已移除 PCBA/FPC/电子件的纯结构 STEP、拆分说明 | 可用 |
| `k1-protocol` | BLE GATT、Display、Audio、OTA、错误码和内部传输规范 | 草案 |
| `k1-ble-controller` | BLE 控制器参考固件源码 | 待构建与 OTA 验证 |
| `k1-apps` | Android App 示例、构建、权限、API Key 和服务端说明 | 示例代码，需安全审查 |
| `k1-sdk` | Python 协议参考实现、LVGL 界面素材 | Developer Preview |
| `k1-v851s-bsp` | V851S 板级配置、刷机文档、厂商参考资料 | 非显示驱动源码待补充 |

## 当前仍在补充

- Android SDK、设备模拟器和完整 API 文档
- 音频、传感器、触摸、电源等非显示 Linux 驱动源码
- BSP、BLE 固件和 App 的干净环境构建记录
- 协议测试向量、互操作测试和正式兼容矩阵
- `k1-apps` 生产安全改造：服务端代理 API Key、账号数据保护和发布构建验证

当前已进入 Public Developer Preview。以上能力仍会继续补充，未验证项和遗留风险见 [公开发布状态](docs/release-readiness.md)。

## 相关仓库

- `k1-hardware`：原理图、硬件设计方案、接口和支持说明
- `k1-mechanical`：纯结构 STEP、安装尺寸和配件接口
- `k1-v851s-bsp`：V851S 板级配置、刷机资料和非显示驱动
- `k1-protocol`：BLE GATT、Display、Audio、Input、OTA 和诊断规范
- `k1-sdk`：协议参考实现、SDK 和开发工具
- `k1-ble-controller`：BLE、UART、OTA 和音频转发参考实现
- `k1-apps`：Android App 和场景示例

## 许可证

- 文档和协议：CC BY 4.0
- SDK、App 和 BLE 控制器代码：Apache-2.0
- K1 原创 BSP 代码：GPL-2.0-only
- 硬件和结构交换文件：K1 Hardware Development License 1.0

K1 名称、Logo、产品图片和商标不随上述许可证授权，详见 [TRADEMARKS.md](TRADEMARKS.md)。第三方资料继续遵循原始许可证。

## 商业合作与二次开发

- [K1 官方硬件销售与二次开发合作说明（Markdown）](business/K1_官方硬件销售与二次开发合作说明_V1.0.md)
- [K1 官方硬件销售与二次开发合作说明（DOCX）](business/K1_官方硬件销售与二次开发合作说明_V1.0.docx)

需要 K1 官方硬件、显示模组、商业集成、OEM/ODM、分销或联合调试：

- 邮箱：liuzemin@intel-platform.com
- 固定电话：26405693

价格、交付、质保、技术支持和商业授权以正式报价单、订单或合同为准。