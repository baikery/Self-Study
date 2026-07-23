# Self-Study
How to build control system for myself？
# 🚀 Control Algorithms From Scratch (从零手写控制算法库)

本项目用于记录个人在**控制工程与运动控制**方向的算法设计学习历程。
拒绝直接调用第三方复杂库，所有核心算法均遵循 **“数学建模推导 -> Python 算法原型验证 -> 纯 C 语言工程实现”** 的闭环路径。

## 🎯 核心目标
1. 掌握离散数值计算与运动轨迹规划（S-Curve, 插补）
2. 掌握状态估计与滤波（KF, EKF, 观测器）
3. 掌握进阶控制理论（PID+Feedforward, LADRC, MPC）
4. 建立高可移植性、无依赖的嵌入式 C 语言算法库

checklist

## 📋 12 周进阶实战清单
### Phase 1: 基础设施与轨迹规划 (W1 - W3)
- [ ] **Week 01: 基础工具库开发**
  - [ ] 实现纯 C 语言矩阵基础库 (src/common/math_matrix.c)：加/减/乘/转置/求逆
  - [ ] 实现 RK4（四阶龙格-库塔）微积分数值求解器
  - [ ] 完成 tests/test_matrix.c 单元测试与 CMake 编译

- [ ] **Week 02: 运动轨迹规划**
  - [ ] 完成 S 型（7段式）加减速算法数学推导文档 (docs/02_scurve_planning.md)
  - [ ] 编写 Python 脚本验证轨迹平滑性 (simulation/s_curve_sim.py)
  - [ ] 用 C 语言编写离散化 S 曲线生成器 (src/planning/s_curve.c)

- [ ] **Week 03: 运动控制器插补算法**
  - [ ] 实现双轴逐点比较法/DDA 直线插补算法 (src/planning/interpolation.c)
  - [ ] 实现平面圆弧插补算法，并在 Python 中输出生成轨迹对比图

### Phase 2: 状态估计与滤波算法 (W4 - W6)
- [ ] **Week 04: 标准卡尔曼滤波 (KF)**
  - [ ] 手写 1 维与多维 KF 算法 (src/estimation/kalman.c)
  - [ ] Python 生成高斯噪声数据，输出 KF 滤波效果对比图

- [ ] **Week 05: 扩展卡尔曼滤波 (EKF) 与传感器融合**
  - [ ] 推导非线性系统的雅可比矩阵并手写 EKF 核心代码 (src/estimation/ekf.c)
  - [ ] 完成 IMU（陀螺仪+加速度计）姿态融合算法测试

- [ ] **Week 06: 电机控制/观测器设计**
  - [ ] 编写永磁同步电机（PMSM）离散化数学模型
  - [ ] 实现滑动模态观测器（SMO）或高阶扰动观测器 (src/estimation/smo_observer.c)

### Phase 3: 自抗扰与高级控制算法 (W7 - W9)
- [ ] **Week 07: 经典控制进阶 (PID + 前馈)**
  - [ ] 手写带有位置/速度前馈与积分抗饱和的 C 语言 PID 库 (src/control/pid_ff.c)
  - [ ] 在 Python 中对比“纯 PID”与“PID+前馈”的高频正弦跟踪误差

- [ ] **Week 08: 自抗扰控制 (LADRC)**
  - [ ] 实现扩张状态观测器（ESO）及 LADRC 核心算法 (src/control/ladrc.c)
  - [ ] 仿真测试系统突加外力矩（抗扰动）下 LADRC 与 PID 的超调对比

- [ ] **Week 09: 模型预测控制 (MPC) 入门**
  - [ ] 实现极简二次规划（QP）求解器或移植轻量求解器
  - [ ] 实现带约束的一维 MPC 控制算法 (src/control/mpc_basic.c)

### Phase 4: 源码拆解与项目打包 (W10 - W12)
- [ ] **Week 10-11: 工业级开源项目（ODrive/VESC/OCS2）剖析**
  - [ ] 完成一篇开源电机/机器人算法架构剖析笔记 (docs/10_odrive_analysis.md)

- [ ] **Week 12: 仓库工程化重构**
  - [ ] 规范 C 语言代码风格、补充 API 注释
  - [ ] 完善 README.md，贴上 Python 仿真的效果动图或对比图
