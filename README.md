# 本仓库是 rust_crane 的公开 issue 仓库

## 相关仓库

- 开源代码仓库：[cinvymoe/rust-crane-open](https://github.com/cinvymoe/rust-crane-open) —— Rust + Qt 起重机称重与监测系统源码（以子模块形式挂在下方）
- 构建产物仓库：筹备中，暂未开放

## 如何提交 issue

1. 打开 [Issues 页面](https://github.com/cinvymoe/rust_crane_issues/issues) → **New issue**。
2. 按格式写标题：`[类型] 产品/模块：一句话概述`，例如 `[缺陷] truck：MQTT 断线后不再重连`。
3. 正文复制下方模板填写，尽量填全每一节。
4. 提交即可，无需其他操作：
   - **白名单成员（cinvymoe）**：新 issue 自动成为内部工单，直接进入开发流程。
   - **外部贡献者**：必须在正文或评论中 @ `rust-crane-agent` 才会被受理；受理前会先经过一轮研判评估，不会直接执行。
   - 追加信息、回答机器人的提问：直接在本 issue 下评论即可，任何评论都会更新对应工单（带上 @ `rust-crane-agent` 可确保立即送达）。
5. 机器人的受理回复、完工说明和 PR 链接都会以评论形式出现在本 issue 中；完成的改动还会收到一条完整 diff 镜像评论（含 `<!-- pr-mirror:N -->` 标记），代码本体始终留在本地仓库。

## 触发关键词

| 关键词 | 作用 | 必填？ |
|---|---|---|
| `@rust-crane-agent` | 唤起智能体受理本 issue / 立即送达评论 | 外部贡献者必填；白名单成员可不写 |
| `[需求]` / `[缺陷]` / `[优化]` / `[疑问]` | 标题类型标签：新功能 / bug / 改进 / 咨询（大小写均可，也可用 feature/bug） | 推荐 |
| `truck` / `loader` / `grabber` / `folding` | 产品线，写在标题或正文中帮助定位范围 | 推荐 |

对已有工单 issue 的**任何评论**都会推进该工单，没有额外的指令词要求。

## Issue 模板（复制后填写）

````markdown
### 类型
[需求] / [缺陷] / [优化] / [疑问]（四选一）

### 产品线 / 模块
truck / loader / grabber / folding + 具体模块（如 truck-mqtt、loader-arm）

### 问题描述
缺陷类：期望发生什么？实际发生了什么？什么条件下出现？
需求类：想达到什么效果？为什么要做？

### 复现步骤 / 验收标准
1. 
2. 
（需求类请写清楚"做成什么样算完成"，例如：设备每 10 秒上报一次遥测数据到 ThingsBoard）

### 相关日志 / 截图
（可选。注意脱敏：不要粘贴 token、密码、客户数据。）

@rust-crane-agent
````

## 工作流说明

新 issue → 自动建内部工单 → 机器人在本地仓库分支开发 → 提交 PR → 完工评论（含 PR 链接）→ 完整 diff 镜像到本 issue。全程在本 issue 内可见进度，无需到本地仓库确认。
