# K1 构建说明

本页是构建入口和当前状态说明。具体构建必须在对应仓库和固定工具链中执行；未完成验证的步骤会明确标注。

## 1. 仓库与工具链

| 组件 | 仓库 | 主要环境 | 当前状态 |
|---|---|---|---|
| BSP/Tina | `k1-v851s-bsp` | Linux、V851S Tina SDK、交叉编译工具链 | 板级配置已提供，完整构建未验证 |
| BLE 控制器 | `k1-ble-controller` | ESP-IDF、CMake、Ninja、Python | 源码已提供，目标工具链未固定 |
| Android App | `k1-apps` | Android Studio、JDK、Android SDK 35、Gradle | 工程已提供，未完成构建验证 |
| Python 协议 SDK | `k1-sdk/python` | Python 3.9+ | 可直接运行和测试 |

## 2. BSP/Tina

完整 Tina SDK 体积较大，通过百度网盘获取。当前 GitHub 仓库只包含板级配置、分区、设备树、刷机资料和厂商参考文档，不是可直接独立编译的完整 SDK。

基本流程：

1. 从网盘获取对应版本的 Tina SDK。
2. 按厂商文档安装 Linux 构建依赖和交叉编译工具链。
3. 将 `vendor/v851s-tina/device/config/chips/v851s/configs/perf1` 对应到 SDK 板级配置。
4. 按实际产品配置检查串口、存储、分区和显示相关节点。
5. 执行 `source build/envsetup.sh`、`lunch` 和 `make` 前，先以网盘版本内的脚本为准。

> 当前仓库没有完成干净环境全量编译，不提供“复制命令即可构建成功”的承诺。

## 3. BLE 控制器

基础命令：

```bash
idf.py build
idf.py -p <PORT> flash monitor
```

构建前必须固定 ESP-IDF 版本、目标芯片、Flash 大小和分区表。当前 `docs/build.md` 仍为草案，公开 Release 前必须补充实际版本和构建日志。

## 4. Android App

```bash
./gradlew assembleDebug
```

开发前：

1. 安装 JDK、Android SDK 35 和 Android Studio。
2. 将 `secrets.properties.example` 复制为 `secrets.properties`。
3. 填入自己的高德、百度和 DeepSeek 开发密钥。
4. 不要把 `secrets.properties` 提交到仓库。

生产版不得让 App 直接持有百度 Secret 或 DeepSeek Key，应改为自有服务端代理。

## 5. Python 协议 SDK

```bash
cd k1-sdk/python
python -m unittest -v
```

该实现用于帧构造、解析、错误检查和联调测试，不代表完整 Android SDK。

## 6. 发布标准

一个构建可以标记为可发布，至少需要：

- 固定工具链和依赖版本
- 干净环境构建通过
- 产物哈希和构建日志
- 刷机、启动、BLE、音频、OTA 和恢复测试
- 无密钥、证书、客户数据和内部账号
- 第三方许可证和再分发权确认