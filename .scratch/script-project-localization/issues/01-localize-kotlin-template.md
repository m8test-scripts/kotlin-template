# 01: 本地化 Kotlin 脚本模板

**What to build:** 为 Kotlin 模板增加英文和中文字符串目录，并让项目元数据与示例界面使用宿主语言显示。

**Blocked by:** None

**Status:** resolved
**Type:** task

- [x] 增加英文与中文 BCP 47 字符串目录，提供项目描述和界面文案。
- [x] 入口脚本通过 `_stringResources` 获取按钮、点击后文案和语言标识。
- [x] 在按钮下方显示本地化的 `Kotlin` 语言名称。
- [x] 中文目录覆盖项目名称，英文目录保留项目名称回退值。
- [x] README 说明字符串目录和 Kotlin 全局变量 API。
- [x] 按用户要求跳过 Kotlin 的 Gradle、设备和静态验证。
