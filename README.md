# UX Design Reviewer

一个面向 UX / UI 设计师的 AI 设计评审 Skill。

UX Design Reviewer 不只是检查“设计稿好不好看”，而是基于 PRD / 需求文档与设计稿，对设计进行系统化评审：

- 需求覆盖度
- 用户任务
- 交互逻辑
- 页面流程
- 状态完整性
- 异常与边界场景
- UX 风险
- AI 交互体验
- 体验优化机会

核心目标：

> 帮助设计师发现“自己没有想到的问题”，而不是重复描述设计稿中已经存在的内容。

---

## ✨ Features

### 1. Requirement Coverage

从 PRD 中提取可验证的 Requirement Unit，并逐项检查设计稿是否覆盖。

不仅检查：

> 有没有这个功能？

还会检查：

> 用户如何进入？
>
> 如何操作？
>
> 系统如何响应？
>
> 成功后发生什么？
>
> 失败后怎么办？

---

### 2. Coverage Score

根据 Requirement Unit 计算设计稿覆盖度：

- Fully Covered：完整覆盖
- Partially Covered：部分覆盖
- Not Covered：未覆盖
- Needs Confirmation：需要确认

输出类似：

> **本次设计稿需求覆盖度为 92%，整体基本合格；核心流程已覆盖，但异常状态和部分边界场景仍存在遗漏。**

---

### 3. Evidence-based Review

不会因为设计稿里“看起来有一个按钮”就直接判定需求已覆盖。

需要进一步确认：

- UI 是否存在
- 默认状态是什么
- 什么条件下出现
- 什么条件下消失
- 用户操作后发生什么
- 是否存在异常状态
- 是否存在完整交互闭环

例如：

PRD：

> 自动识别默认关闭。

不能仅因为设计稿存在“自动识别”按钮，就判定为完整覆盖。

需要确认：

> 是否有证据证明首次进入时默认状态为 OFF？

---

### 4. Interaction Logic Review

检查：

- 用户操作路径
- 页面跳转
- 操作反馈
- 状态变化
- 返回逻辑
- 成功后的下一步
- 失败后的恢复路径
- 是否存在流程死路

---

### 5. State Completeness

检查与当前业务相关的：

- 默认状态
- Loading
- 成功
- 空状态
- 错误
- 权限
- 网络异常
- 超时
- 重试
- 取消
- 返回
- AI生成状态

不会机械要求所有项目都具备所有状态。

---

### 6. Edge Cases

主动检查：

- 空输入
- 非法输入
- 连续点击
- 重复提交
- 中途取消
- 中途返回
- 数据为空
- 网络异常
- 请求超时
- 权限拒绝
- AI生成失败

---

### 7. AI UX Review

针对 AI 产品额外检查：

- AI 是否正在处理
- 用户是否知道当前状态
- 长时间等待如何反馈
- 用户是否可以中断
- AI失败后如何恢复
- AI结果为空怎么办
- 是否支持重新生成
- 是否支持继续操作
- 多轮交互状态是否完整

---

## 📊 Review Output

评审开始时优先给出一句话结论：

> **本次设计稿需求覆盖度为 XX%，整体基本合格 / 基本合格但建议优化 / 存在明显风险 / 暂不合格；主要问题集中在 XXX。**

随后输出完整 UX Design Review Report：

1. Summary Overview
2. Requirement Coverage
3. Interaction Logic
4. State Completeness
5. Edge Cases
6. UX Risks
7. Experience Optimization
8. Priority Summary

问题按照：

- P0：阻断问题
- P1：高风险问题
- P2：体验优化

进行分级。

---

## 🚀 Usage

将 `ux-design-reviewer` Skill 安装到支持 Skills 的 AI 编程 / Agent 环境后，即可使用。

典型使用方式：

```text
使用 ux-design-reviewer 评审这个需求。

请检查：
- 需求覆盖
- 交互逻辑
- 状态完整性
- 边界场景
- UX 风险
