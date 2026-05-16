# AFC 学习路线（Transit Payment / AFC Product Architecture）

## 学习目标

从：
- App PM / PO

成长为：
- Transit Digital Architect
- AFC Product Owner
- Transit Payment Solution Designer

---

# 总路线图

```text
Journey
→ Fare
→ AFC System
→ CBT
→ ABT
→ QR
→ EMV
→ Wallet
→ Clearing
→ Offline Risk
```

---

# Phase 1：公共交通业务基础

## 目标

理解：

```text
一次 Journey 是怎么完成的
```

---

## 核心概念

- Tap in
- Tap out
- Zone
- Fare
- Transfer
- Daily cap
- Weekly cap
- Journey completion
- Inspection
- Penalty fare

---

## 必须能回答的问题

```text
用户从 A 到 B，系统如何知道收多少钱？
为什么有些换乘免费？
如果用户没有 Tap out 会发生什么？
```

---

# Phase 2：AFC 系统全景

## 目标

理解：

```text
整个 AFC 系统由哪些模块组成
```

---

## AFC System Landscape

```text
User
 ↓
Card / QR / Wallet / EMV
 ↓
Gate / Validator
 ↓
AFC Back Office
 ↓
Fare Engine
 ↓
Clearing & Settlement
 ↓
Bank / Transport Operator
```

---

## 核心模块

### Fare Media
- Card
- QR
- EMV
- Wallet

### Validation
- Gate
- Validator
- TVM

### Back Office
- Account
- Transaction
- Journey
- Settlement

### Risk
- Blacklist
- Hotlist
- Offline Risk

---

# Phase 3：CBT vs ABT

# CBT（Card Based Ticketing）

## 特点

```text
余额在卡里
规则在卡里
闸机本地判断
```

---

## 优点

- 快
- 离线能力强
- 不依赖后台

---

## 缺点

- 难同步
- 丢卡难处理
- 多渠道困难

---

# ABT（Account Based Ticketing）

## 特点

```text
余额在后台
卡只是 Token
```

---

## 核心概念

- Account
- Token
- Fare Engine
- Journey Calculation
- Multi-device support

---

## 必须理解的问题

```text
为什么 ABT 更适合 QR？
为什么 ABT 更适合 Wallet？
为什么 ABT 更依赖网络和风控？
```

---

# Phase 4：Open Loop vs Closed Loop

# Closed Loop

例如：

- nol
- Oyster
- Octopus

---

## 特点

```text
交通系统自己的卡
```

---

# Open Loop

例如：

- Visa
- Mastercard
- Apple Pay

---

## 特点

```text
直接使用银行卡/手机钱包
```

---

## 必须理解的问题

```text
为什么 Open Loop 会引入银行体系？
为什么需要 Acquirer？
为什么会有 Aggregation？
```

---

# Phase 5：Clearing & Settlement

# 核心目标

理解：

```text
交易 ≠ 钱到账
```

---

# 核心概念

## Transaction
用户发起交易

## Clearing
确认账怎么算

## Settlement
钱最终打给谁

## Reconciliation
差异处理

---

# 必须理解的问题

```text
为什么支付成功不等于 RTA 收到钱？
为什么会有 T+1/T+2？
为什么账单会不一致？
```

---

# Phase 6：Offline & Risk

# 核心目标

理解：

```text
公共交通必须 Offline First
```

---

# 核心概念

- Offline validation
- Deferred authorization
- Blacklist
- Hotlist
- Risk limit
- Debt recovery

---

# 必须理解的问题

```text
为什么 Gate 不能每次实时查后台？
为什么 Validator 要缓存？
为什么 300ms 很重要？
```

---

# 12 周学习计划

# Week 1：Journey Lifecycle

## 输出物

```text
Journey Lifecycle Diagram
```

---

# Week 2：Fare Rule

## 输出物

```text
Fare Rule Decision Tree
```

---

# Week 3：AFC System Landscape

## 输出物

```text
AFC 全景架构图
```

---

# Week 4：CBT

## 输出物

```text
CBT Transaction Flow
```

---

# Week 5：ABT

## 输出物

```text
ABT Transaction Flow
```

---

# Week 6：CBT → ABT Migration

## 输出物

```text
Migration Risk List
```

---

# Week 7：QR Ticketing

## 输出物

```text
QR Ticket Lifecycle
```

---

# Week 8：EMV Transit

## 输出物

```text
EMV Transit Flow
```

---

# Week 9：OEM Wallet

## 输出物

```text
Wallet Provisioning Flow
```

---

# Week 10：Clearing & Settlement

## 输出物

```text
Money Flow + Data Flow
```

---

# Week 11：Offline & Risk

## 输出物

```text
Offline Risk Matrix
```

---

# Week 12：综合案例

## 输出物

```text
RTA NolPay AFC Product Architecture Note
```

---

# 每天学习方法

```text
10分钟：学一个概念
10分钟：画图
10分钟：写3个问题
```

---

# 每周固定复盘问题

```text
1. 这个需求影响 Journey 吗？
2. 这个需求影响 Fare 吗？
3. 这个需求影响 Validation 吗？
4. 这个需求影响 Clearing 吗？
5. 这个需求 Offline 会不会出问题？
```

---

# 推荐研究对象

## Transport for London
研究：
- Oyster
- EMV
- Daily Capping

---

## MTR
研究：
- Octopus
- QR
- Offline

---

## RTA
研究：
- Nol
- CBT → ABT
- Wallet
- QR

---

# 最终目标

```text
不是会写 User Story

而是：

能理解
整个城市交通支付系统
为什么这样设计
```
