# Design Compiler 学习资源汇总

> 整理日期：2026-05-24

---

## 一、中文入门教程

### 1. Tcl与Design Compiler 系列（13讲）⭐最推荐
最系统的中文 DC 教程，覆盖从环境配置到综合后处理的完整流程。
- 专栏地址：https://www.cnblogs.com/xh13dream/tag/DC/
- 覆盖内容：
  - 逻辑综合简介、DC 综合与 Tcl 语法结构概述
  - DC 综合流程（准备设计 → 指定库 → 读入设计 → 定义环境 → 设置约束 → 编译 → 分析 → 存储）
  - DC 启动环境设置（.synopsys_dc.setup 配置）
  - 综合库（时序库）和 DC 设计对象
  - 基本时序路径约束（建立/保持时间、时钟约束、输入/输出延时）
  - 环境、设计规则和面积约束
  - DC 逻辑综合与优化（compile_ultra、路径组、关键范围）
  - 综合后形式验证
  - 综合后处理（.sdc/.sdf/.v 文件生成）

### 2. 阿里云开发者社区 — DC Lab 系列
- 地址：https://developer.aliyun.com/article/1207401
- 基于 Synopsys 官方 Lab Guide，手把手实践教学
- 涵盖：启动文件配置 → 库设置 → 读入设计 → 约束 → compile_ultra → 报告查看 → 脚本自动化

### 3. 《综合与Design Compiler》学习笔记
- 地址：https://www.e-com-net.com/article/1691076959997603840.htm
- 内容质量极高：
  - 综合综述（逻辑级 → RTL级 → 行为级综合）
  - Verilog 语言结构到门级的映射规则
  - 完整的环境约束与时序约束写法
  - 完整的 DC 综合 Tcl 脚本示例

### 4. 数字IC设计学习笔记 — GUI 界面入门
- 地址：https://www.e-com-net.com/article/1188401281480368128.htm
- 图文并茂讲解 DC GUI 操作（design_vision）
- 流程：建目录 → 启动 design_vision → 库配置 → 读入 RTL → 约束 → Link → Compile → 保存

### 5. CSDN文库 — Design Compiler 速成课
- 地址：https://wenku.csdn.net/column/3h0sh3z4q3
- 零基础到高级技术的全面掌握指南
- 涵盖：基础理论 → 环境操作 → 高级编译技术 → 脚本自动化 → 案例分析

### 6. 经典 DC 教程文档（可下载）
- 地址：https://download.csdn.net/download/m0_67912929/89481024
- 包含完整的 DC 脚本模板和代码解释

---

## 二、英文/官方资源

### 7. Design Compiler User Manual（开源版）
- 地址：https://gitcode.com/Premium-Resources/a40f4
- Synopsys 官方手册，覆盖 HDL-to-gate 综合全流程
- 适合从入门到进阶的所有阶段

### 8. 一位高手写的 DC 手册
- 地址：https://gitcode.com/open-source-toolkit/30ea3/wiki
- 基础操作 + 高级技巧 + 实战案例

### 9. DC 综合 Demo 脚本（GitHub）
- 地址：https://github.com/Giftwen/DC_script
- 完整可运行的 DC 综合脚本，包括：
  - SynFlow.tcl
  - Sdc.tcl
  - main2.py

### 10. 完整低功耗 ASIC 流程（2026版）
- 地址：https://z.shaonianxue.cn/40843.html
- RTL → GDSII 全流程，使用 2025-2026 Synopsys 工具链
- 包含真实的 DC 脚本：compile_ultra -gate_clock -low_power

### 11. DC 环境配置深入指南
- 地址：https://deepwiki.com/akommini/Network-on-Chip-Router/3.1-setup-and-configuration
- .synopsys_dc.setup 引导流程
- setup.tcl 变量说明
- run_synth.tcl 编排脚本
- 库路径配置

### 12. 韩国崇实大学短期课程（2026年1月）
- 地址：https://www.disu.ac.kr/community/notice?md=down&bbsidx=8479&fileidx=9795
- 3天密集课程："Logic Synthesis with Design Compiler"
- 前提：Verilog-HDL, Digital Logic Design
- 内容：DC 使用、设计划分、综合编码风格、时序约束、静态时序分析、优化

---

## 三、推荐学习路径

```
第1步：理解综合概念（什么是综合、三个层次）
       → 看资源3的前两章
第2步：配置 .synopsys_dc.setup 启动文件
第3步：学会设置 target_library / link_library / symbol_library / search_path
第4步：掌握基本流程命令
       → read → link → source约束 → compile → report → write
第5步：学会写时序约束
       → create_clock, set_input_delay, set_output_delay
第6步：学会写环境约束
       → set_load, set_driving_cell, set_wire_load_model
第7步：理解报告分析
       → report_timing, report_area, report_constraint
第8步：编写自动化 Tcl 脚本
第9步：跑资源9的 Demo 脚本，亲手实践
```

---

## 四、常用命令速查

```tcl
# 启动方式
dc_shell                    # 命令行模式
dc_shell -topo              # 拓扑模式（更真实的时序）
design_vision &             # GUI 模式

# 核心流程命令
read_file -format verilog design.v
current_design TOP
link
source constraints.tcl
compile_ultra
report_timing > timing.rpt
report_area > area.rpt
write -format verilog -output TOP_netlist.v
```

---

## 五、核心概念速览

| 概念 | 说明 |
|------|------|
| **综合三阶段** | translation（翻译）→ optimization（优化）→ mapping（映射） |
| **SDC 约束** | 时钟定义、input/output delay、false path、multicycle path |
| **库类型** | target_library（目标工艺库）、link_library（链接库）、symbol_library（图形库） |
| **优化目标** | 时序（timing）、面积（area）、功耗（power） |
| **compile_ultra** | DC 最高级别的综合优化命令 |

---

> ⚠️ 注意：DC 软件需要 Synopsys license，请确认学校或公司的 EDA 环境是否可用。
