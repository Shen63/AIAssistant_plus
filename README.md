# AI Assistant (Android)

一款 Android APP自动化操作应用，位用户进行手机的操作，集成大模型对话接口，并提供无障碍服务与前台服务以支持更丰富的交互能力。

## 功能

- 大模型对话：通过 Retrofit 调用兼容 OpenAI 的聊天完成接口。
- 聊天 UI：消息列表、输入框、发送按钮。
- 配置项：API Key、模型名可在设置中配置并持久化。
- 无障碍与前台服务：用于更深度的系统交互能力（需用户授权）。

## 技术栈

- Kotlin
- AndroidX
- Retrofit + OkHttp
- Kotlinx Serialization

## 目录结构

- app/src/main/java/com/example/aiassistant/ui：界面与交互逻辑
- app/src/main/java/com/example/aiassistant/data：网络与数据模型
- app/src/main/java/com/example/aiassistant/services：前台服务、无障碍服务
- app/src/main/java/com/example/aiassistant/config：全局配置

## 运行环境

- minSdk: 26
- targetSdk: 35
- compileSdk: 35
- JDK: 11

## 快速开始

1. 使用 Android Studio 打开项目。
2. 同步 Gradle 依赖。
3. 连接设备或启动模拟器。
4. 运行 app 模块。

## 大模型接口配置

应用默认使用兼容 OpenAI 的 `/chat/completions` 形式接口。

- Base URL 与接口定义：
  - app/src/main/java/com/example/aiassistant/data/RetrofitClient.kt

在设置页面填写 API Key 和模型名称，配置会保存到 SharedPreferences 并在应用启动时加载。

## 权限说明

- INTERNET：访问大模型接口
- FOREGROUND_SERVICE / FOREGROUND_SERVICE_DATA_SYNC：前台服务支持
- POST_NOTIFICATIONS：通知权限
- BIND_ACCESSIBILITY_SERVICE：无障碍服务

## 注意事项

- 建议使用自己的 API Key，避免在源码中硬编码密钥。
- 无障碍服务为敏感权限，发布前请完善隐私说明与用户提示。

## 常见问题

- 无障碍服务未启用：应用会在启动后弹窗引导开启。
- 接口调用失败：请检查 API Key、网络连接与接口兼容性。


