---
name: 问题反馈
about: 报告安装失败 / 运行异常 / 功能问题
labels: bug
body:
  - type: markdown
    attributes:
      value: 感谢反馈！请尽量填写以下信息，加速定位。
  - type: dropdown
    id: platform
    attributes:
      label: 平台
      options:
        - Android（APK）
        - Windows 桌面
        - Linux relay 裸二进制
        - Windows relay 裸二进制
        - dsh 插件（npm）
        - 其他
    validations:
      required: true
  - type: input
    id: version
    attributes:
      label: 版本号
      description: 控制台顶栏可见（如 Relay 142.g7aae070），或安装包文件名中的版本
    validations:
      required: true
  - type: textarea
    id: what-happened
    attributes:
      label: 现象与复现步骤
      description: 发生了什么？做了什么操作？有无报错截图/日志片段
    validations:
      required: true
  - type: textarea
    id: context
    attributes:
      label: 补充信息（可选）
      description: 设备型号 / 系统版本 / 网络环境等
