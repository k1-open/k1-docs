# K1 开发入口

K1 的构建和开发资料按组件拆分，避免把第三方芯片开发文档或内部工程混入公开仓库。

| 目标 | 入口 |
|---|---|
| Android App | `k1-apps` |
| BLE 协议 | `k1-protocol` |
| Python 协议参考实现 | `k1-sdk/python` |
| BLE 控制器 | `k1-ble-controller` |
| V851S 板级配置 | `k1-v851s-bsp` |
| 刷机和恢复 | `../docs/flashing.md` |
| 构建状态 | `../docs/build.md` |

公开资料不包含不属于 K1 的第三方无线芯片开发文档。此类平台资料由对应芯片供应商渠道提供。