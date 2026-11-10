# DSH 插件索引源（format 1）

供 DSH「插件」→「发现」标签使用的插件索引，托管在本仓库，经 jsDelivr CDN 提供。

## 索引源 URL（添加到「发现」）

| 优先级 | URL |
| --- | --- |
| 推荐 | `https://cdn.jsdelivr.net/gh/HectorYuan/dsh-plugin-index@main/plugins.json` |
| 备用（Fastly） | `https://fastly.jsdelivr.net/gh/HectorYuan/dsh-plugin-index@main/plugins.json` |
| 备用（Gcore） | `https://gcore.jsdelivr.net/gh/HectorYuan/dsh-plugin-index@main/plugins.json` |

固定到某个提交（内容不再随 `main` 变动）：
`https://cdn.jsdelivr.net/gh/HectorYuan/dsh-plugin-index@<commit-sha>/plugins.json`

## 收录内容（24 个，全部经 npm registry 核对）

### 官方组合包（14，engines.dsh = 0.2.2-alpha.2）

| 推荐度 | 包名 | 版本 | 说明 |
| --- | --- | --- | --- |
| 100 | @deepseek-ai/dsh-experimental-plugin-market-bundle | 0.2.2-alpha.2 | 自定义插件索引（「发现」标签本身） |
| 95 | @deepseek-ai/dsh-experimental-agent-team-profile | 0.2.2-alpha.2 | 智能体团队 |
| 80 | @deepseek-ai/dsh-experimental-voice-input-bundle | 0.2.2-alpha.2 | 语音输入（本地 SenseVoice） |
| 75 | @deepseek-ai/dsh-experimental-forge-bundle | 0.2.2-alpha.2 | 代码变更面板 |
| 70 | @deepseek-ai/dsh-experimental-auto-review | 0.2.2-alpha.2 | 逐工具 LLM 授权评审 |
| 65 | @deepseek-ai/dsh-experimental-session-search | 0.2.2-alpha.2 | 会话检索 |
| 60 | @deepseek-ai/dsh-experimental-terminal-bundle | 0.2.2-alpha.2 | 常驻终端 |
| 50 | @deepseek-ai/dsh-experimental-cot-translation-bundle | 0.2.2-alpha.2 | 推理翻译 |
| 45 | @deepseek-ai/dsh-experimental-badge-skill-bundle | 0.2.2-alpha.2 | 输出徽章 |
| 40 | @deepseek-ai/dsh-experimental-ralph-bundle | 0.2.2-alpha.2 | 重复任务 |
| 35 | @deepseek-ai/dsh-experimental-session-titles-bundle | 0.2.2-alpha.2 | 会话标题刷新 |
| 30 | @deepseek-ai/dsh-experimental-inspector-profile | 0.2.2-alpha.2 | 调试检查器 |
| 25 | @deepseek-ai/dsh-experimental-liveshare | 0.2.2-alpha.2 | 会话共享 |

### 社区第三方包（10，标签 community，均近期维护）

| 推荐度 | 包名 | 版本 | 说明 |
| --- | --- | --- | --- |
| 60 | dsh-image-generation | 0.1.3 | 图像生成（OpenAI / ByteDance） |
| 55 | better-dsh | 0.3.5 | 面向严肃编码任务的组合增强 |
| 45 | dsh-better-sidebar | 0.30.1 | 文件树 / 编辑器 / 变更视图侧边栏 |
| 35 | dsh-config-manager | 0.7.0 | 配置备份、恢复、迁移与同步 |
| 30 | dsh-token-optimizer | 0.2.5 | 工具结果压缩，节省上下文 |
| 28 | dsh-plan-and-execute | 0.6.0 | plan-and-execute 编排 |
| 26 | dsh-session-fork | 0.4.0 | 类 Git 会话分叉 |
| 24 | billion-context-dsh | 0.2.27 | 主动上下文裁剪（ACP） |
| 22 | dsh-timeline | 0.1.5 | 会话时间线导航 |
| 20 | dsh-doctor | 0.4.3 | 环境与依赖诊断 |
| 18 | dsh-web-mobile | 3.3.5 | 手机浏览器访问 DSH |

> 社区包的 `engines.dsh` 统一声明为 `0.2.2-alpha.2` 以便在「发现」页显示为可安装；它们对 DSH 实际版本的兼容性请以各自仓库说明为准，安装前务必核对作者与来源。

## 维护方式

1. 修改 `plugins.json`（保持 `format: 1` 与既有字段结构）。
2. 推送后等待 jsDelivr 缓存刷新（`@main` 通常几分钟内；需要立即生效可改用固定 commit 的 URL）。
3. 新增条目必须先确认 npm 上确实存在对应版本，否则会出现「可安装但没有包」的条目。

## 安全提示

索引本身没有签名，条目中的名称与版本只是索引方的声明；实际安装内容以 bundle manifest 为准。详细说明见工作区文档《DSH插件索引源指南》。
