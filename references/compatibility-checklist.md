# 适配核对清单

> 原则：**不凭平台名或电压确认适配**。"Light Bee" 四个字不等于能装。

## 通用铁律

1. 客户说"my Light Bee"时，至少还要知道：**年款**、**当前电压/电池**、**是否有改装过控制器或电机**。
2. 客户发来一张整车照片，不足以确认电池舱空间——要**开盖的舱内照**或**尺寸测量**。
3. 客户问"能装吗"，正确回答不是"能"或"不能"，而是"按你这台车的 X 和 Y 来看是/不是，我需要确认 Z"。
4. 资料之间出现型号或适配冲突时，明确说需团队核对，**不自行选一个结论**。

## 电池核对项

| 必核项 | 为什么 | 怎么问 |
|---|---|---|
| 具体车型 + 年款 | 同平台不同年款舱位与接口会变 | "Which year is your Light Bee?" |
| 电池舱尺寸与盒盖形式 | 决定电池外形能不能放进去 | 要开盖照片 + 长宽高 |
| 放电接口类型 | QS8 / QS10 / 原厂接口 | "What connector is on your current pack?" |
| 充电接口类型 | XT60 / XT90 / 其他 | 同上 |
| 当前控制器与电机 | 决定电压和电流能不能吃下 | "Stock controller or upgraded?" |
| 目标电压与功率 | 72V / 80V / 84V / 88V / 96V，目标 kW | "What voltage and power are you targeting?" |
| BMS 通信需求 | 是否需要屏幕数据显示、蓝牙 | "Do you need display data or Bluetooth?" |

**典型回答模板（英语思路）**：
"72V 45Ah fits the Light Bee compartment, but the connector and the BMS protocol depend on your year and whether the controller is stock. Send me a photo of the compartment with the cover off and tell me the year — I'll confirm the exact configuration today."

## 控制器核对项

| 必核项 | 说明 |
|---|---|
| 电池电压范围 | 控制器耐压必须覆盖电池满充电压 |
| 电机类型与参数 | 中置永磁同步 / 轮毂；极对数、额定电流 |
| 线束与接口 | 是否原厂线束、需不需要转接 |
| 安装空间 | 控制器体积与散热空间 |
| 目标功率 | 峰值 kW 与相电流 |
| 功能需求 | Regen、BT App、三速模式、限速 |

## 电机核对项

| 必核项 | 说明 |
|---|---|
| 车架/安装位 | 孔距、轴径、安装角度 |
| 电压 | 72V / 96V 平台 |
| 控制器匹配 | 控制器的相电流与弱磁能力 |
| 传动系统 | 链条/皮带、齿比、链轮 |
| 冷却条件 | 连续高负载下的散热 |

## 充电器核对项

| 必核项 | 说明 |
|---|---|
| 电池化学体系 | 锂离子 / LiFePO4 / 半固态 |
| 串数 / 满充电压 | CH30 支持 10S—27S，30—98V |
| BMS 允许充电电流 | 不能超过 BMS 限流 |
| 充电接口 | XT60 / XT90 / 定制 |
| 目标充电电流 | 20A / 40A / 可调 |

## 分场景回答策略

### 客户给了完整信息 → 直接给结论
确认能装就给明确答复 + 需要他注意的 1 个点 + 下一步（下单/发确认图）。

### 客户只给了车型 → 先给方向性判断，再要 1—2 个关键信息
不要说"我什么都不知道"。可以说"72V 平台我们有对应的包，但要确认舱位和接口"，然后只问年款 + 要照片。

### 客户想自己改（DIY builder）→ 给工程语言
这类客户吃参数。给电压、电流、接口、尺寸、BMS 协议，别给营销话。

### 客户的车不在我们适配清单里 → 诚实说，但给路径
"Our current lineup is built around Light Bee / Ultra Bee / Talaria. If your frame uses a similar compartment, we can look at a custom build — send dimensions and I'll check with engineering."

## 绝对禁止

- ❌ 未确认接口就写 `plug-and-play`
- ❌ 因为客户说"应该是 72V"就当确认了
- ❌ 说"our battery is compatible with all Sur-Ron models"
- ❌ 暗示与 Sur-Ron / Talaria 有官方关系
- ❌ 客户问适配时回"yes, it fits"却没有核对任何一项
