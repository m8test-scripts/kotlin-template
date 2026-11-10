# Kotlin 模板脚本项目 i18n

Status: resolved
Triage: ready-for-agent

## Problem Statement

Kotlin 模板的示例按钮只有固定英文文案，也没有表明当前界面来自哪个语言模板。项目没有英文/中文字符串目录示例，复制模板的开发者无法直接参考宿主 locale 驱动的脚本 i18n。

## Solution

为 Kotlin 模板添加英文和中文 BCP 47 字符串目录；入口示例使用宿主的 `StringResources` 读取按钮文案、点击后的文案和按钮下方的语言标识。目录也提供本地化项目描述，并通过中文 catalog 覆盖项目名称。README 说明资源目录、Kotlin 全局变量名和 locale 行为。

## Implementation Decisions

- 本次范围只包括 Kotlin 模板仓库；宿主已有的脚本本地化 API 及语言 locale 解析逻辑不变。
- Kotlin 语言注册 `_` 作为全局变量前缀，`StringResources` 的完整名称因此为 `_stringResources`。
- 字符串目录位于 Kotlin 主资源目录的 `strings/` 下，文件使用 `en.json` 和 `zh.json`。
- 英文目录提供描述和完整 UI 文案，但不覆盖项目名称；中文目录提供中文项目名称、描述和 UI 文案。
- 主按钮保持现有点击计数行为；按钮及其下方的语言名称通过垂直布局一起居中显示。
- 根据用户明确要求，Kotlin 模板不运行 `rerunKotlin`、Gradle、ADB 或静态检查。

## Out of Scope

- 修改宿主、Gradle 插件、Kotlin Extension 或其他模板仓库。
- 新增语言选择、格式化 API、插值机制或更多语言目录。
