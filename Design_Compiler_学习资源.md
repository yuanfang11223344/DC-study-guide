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

### 5. DC综合教程：从RTL代码到门级网表
- 地址：https://wenku.csdn.net/doc/342os2vi9h
- 从 RTL 到门级网表的完整综合流程教程

### 6. Design Compiler逻辑综合与静态时序分析全流程
- 地址：https://wenku.csdn.net/doc/3z8jvythjx
- 数字电路逻辑综合优化技巧全集

### 7. DC综合工具学习教程（chaojiit）
- 地址：https://www.chaojiit.com/home/article/detail/id/337510.html
- 包含：DC 入门总结、Tcl 基础语法、综合库与 DesignWare 库、时序路径约束

### 8. 博客园 — 逻辑综合笔记
- 地址：https://www.cnblogs.com/xuxuxu69/p/18283258
- DC 综合基础概念和操作流程

### 9. CSDN — Design Compiler 全流程指南（2024版）
- 地址：https://blog.csdn.net/weixin_29306261/article/details/158856839
- 从安装到优化的完整 DC User Guide 全流程

### 10. Design Compiler 综合及 Debug 流程
- 地址：https://www.e-com-net.com/article/2051817918592770048.htm
- 完整9步综合流程 + Timing Debug 流程，含 Tcl 示例代码

---

## 二、英文/官方资源

### 11. CMU ECE — A Short Intro to Synopsys Design Compiler
- 地址：http://users.ece.cmu.edu/~jhoe/doku/doku.php?id=a_short_intro_to_synopsys_design_compiler
- 卡内基梅隆大学课程资料
- 涵盖环境设置、综合脚本、时钟约束、时序报告，适合初学者

### 12. Design Compiler User Manual（开源版）
- 地址：https://gitcode.com/Premium-Resources/a40f4
- Synopsys 官方手册，覆盖 HDL-to-gate 综合全流程
- 适合从入门到进阶的所有阶段

### 13. DC 综合 Demo 脚本（GitHub）
- 地址：https://github.com/Giftwen/DC_script
- 完整可运行的 DC 综合脚本，包括：
  - SynFlow.tcl
  - Sdc.tcl
  - main2.py

### 14. 完整低功耗 ASIC 流程（2026版）
- 地址：https://z.shaonianxue.cn/40843.html
- RTL → GDSII 全流程，使用 2025-2026 Synopsys 工具链
- 包含真实的 DC 脚本：compile_ultra -gate_clock -low_power

### 15. DC 环境配置深入指南
- 地址：https://deepwiki.com/akommini/Network-on-Chip-Router/3.1-setup-and-configuration
- .synopsys_dc.setup 引导流程
- setup.tcl 变量说明
- run_synth.tcl 编排脚本
- 库路径配置

---

## 三、GitHub 开源仓库 ⭐可直接使用

### 16. sky130 RTL Design and Synthesis Workshop ⭐强烈推荐
- 地址：https://github.com/kunalg123/sky130RTLDesignAndSynthesisWorkshop
- 最知名的开源 DC 实验仓库，使用 SkyWater 130nm 开源 PDK
- 包含完整 lab 文件、Tcl 脚本、Verilog 示例
- 适合从零开始动手学 DC

### 17. Advanced Synthesis and STA with DC ⭐强烈推荐
- 地址：https://github.com/ireneann713/AdvancedSynthesisandSTAwithDC
- 5天完整工作坊课程（基于资源16的 lab 文件）：
  - Day 1：逻辑综合入门、DC 调用、Design Vision GUI、Tcl 脚本
  - Day 2：STA 基础、.lib 时序文件
  - Day 3：高级约束 — 时钟建模、uncertainty、I/O delay、虚拟时钟
  - Day 4：优化 — 组合逻辑、时序逻辑、边界优化、寄存器重定时、多周期路径
  - Day 5：质量检查 — report_timing、check_timing、check_design

### 18. Synthesis and STA with Synopsys DC Compiler
- 地址：https://github.com/srsapireddy/Synthesis-and-STA-with-Synopsis-DC-Compiler
- 手把手实践教程，涵盖：
  - dc_shell 调用和配置
  - search_path、target_library、link_library 设置
  - Verilog 读入、compile、网表导出
  - 逐步 Lab 示例

### 19. Advance Synthesis using Design Compiler
- 地址：https://github.com/iaakash47/AdvanceSynthesis_using_DesignCompiler
- 综合概念、SDC 约束、STA 基础
- Design Vision 配置、延迟/面积信息、Tcl 脚本
- 进阶约束技巧

---

## 四、推荐学习路径

```
第1步：理解综合概念（什么是综合、三个层次）
       → 看资源3的前两章
第2步：配置 .synopsys_dc.setup 启动文件
       → 看资源15
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
第9步：克隆资源16（sky130 Workshop），跑 Lab
第10步：看资源17的5天课程笔记，深入理解每个步骤
第11步：跑资源13的 Demo 脚本，亲手实践
```

---

## 五、常用命令速查

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

## 六、核心概念速览

| 概念 | 说明 |
|------|------|
| **综合三阶段** | translation（翻译）→ optimization（优化）→ mapping（映射） |
| **SDC 约束** | 时钟定义、input/output delay、false path、multicycle path |
| **库类型** | target_library（目标工艺库）、link_library（链接库）、symbol_library（图形库） |
| **优化目标** | 时序（timing）、面积（area）、功耗（power） |
| **compile_ultra** | DC 最高级别的综合优化命令 |

---

> ⚠️ 注意：DC 软件需要 Synopsys license，请确认学校或公司的 EDA 环境是否可用。
> 开源替代方案：可以使用 Yosys（开源综合工具）+ sky130 PDK 在不依赖 Synopsys license 的情况下练习综合流程。
